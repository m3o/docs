---
layout: default
title: Using Micro
nav_order: 5
permalink: /getting-started/using-micro
parent: Get Started
---
# Using Micro

Micro is an open source platform for API driven development.

## Learn Micro

To learn about [Micro](https://github.com/micro/micro) head to the open source website [micro.mu](https://micro.mu).

## Services

The core services available to you are

- Authentication
- Service Discovery
- RPC Communication
- Dynamic Config
- Event Streaming
- Key Value Storage
- Runtime Management

We'll walk through these in more depth in the [Concepts](/concepts) section but basically its the OSS 
Micro v3 provided to you with highly available distributed systems beneath the covers.

## Creating a Service

Services are created using the Go framework provided by Micro. They make use of gRPC and protobuf at the core 
and provide a simpler set of abstractions to build on.

Here's an example. If you want further info see the [helloworld]({{ site.baseurl }}/tutorials/helloworld) example.

Services are defined using protobuf

```proto
syntax = "proto3";

package helloworld;

service Helloworld {
	rpc Call(Request) returns (Response) {}
}

message Request {
	string name = 1;
}

message Response {
	string msg = 1;
}
```

They're then code generated using `protoc` and implemented using Micro

```go
package main

import (
	"context"
  
	"github.com/micro/micro/v3/service"
	"github.com/micro/micro/v3/service/logger"
	pb "github.com/micro/services/helloworld/proto"
)

type Helloworld struct{}

// Call is a single request handler called via client.Call or the generated client code
func (h *Helloworld) Call(ctx context.Context, req *pb.Request, rsp *pb.Response) error {
	logger.Info("Received Helloworld.Call request")
	rsp.Msg = "Hello " + req.Name
	return nil
}

func main() {
	// Create service
	srv := service.New(
		service.Name("helloworld"),
	)

	// Register Handler
	srv.Handle(new(Helloworld))

	// Run the service
	if err := srv.Run(); err != nil {
		logger.Fatal(err)
	}
}
```

## Calling Services

To use the services peak into the [service](https://github.com/micro/micro/tree/master/service) directory on GitHub. 
Micro pre-initialises all the services for you so that all you have to do is import the package and call public 
functions made available to you.

Example. Lets make use of calling a service.

```
import (
	"context"

	"github.com/micro/micro/v3/service/client"
	pb "github.com/micro/services/helloworld/proto"
)

req := client.NewRequest("helloworld", "Helloworld.Call", &pb.Request{Name: "Alice"})
rsp := new(pb.Response)
err := client.Call(context.Background(), req, &rsp)
```

If you want to use code generation

```
hw := pb.NewHelloworldService("helloworld", client.DefaultClient)
rsp, err := hw.Call(context.Background(), &pb.Request{Name: "Alice"})
```

## Publish/Subscribe to Events

What about say publishing events?

```
import "github.com/micro/micro/v3/events"

events.Publish("event-topic", map[string]string{"foo": "bar"})
```

And on the subscribe side

```
eventChan, err := events.Subscribe("event-topic")
```

## Storing and Retrieving Data

```
import (
	// we're fixing this
	kv "github.com/micro/go-micro/v3/store"
	"github.com/micro/micro/v3/store"
)

// write the record
store.Write(&kv.Record{
	Key: "foo",
	Value: []byte(`Bar`),
})

// read the record
rec, err := store.Read("foo")

// delete the record
store.Delete("foo")
```

## Further Documentation

To learn more about [Micro](https://github.com/micro/micro) head to the open source website [micro.mu](https://micro.mu)


