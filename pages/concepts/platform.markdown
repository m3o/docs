---
layout: page
title: Platform
keywords: concepts, platform, m3o
tags: [concepts, platform, m3o]
permalink: /concepts/platform
summary: A cloud native platform built for developers
nav_order: 1
parent: Concepts
toc_list: true
---


# Platform


The [**Micro Platform**](https://m3o.com) is a cloud platform for API driven development.

## Overview

The Platform provides Micro as a Service. We take the open source [**Micro**](https://github.com/micro/micro) framework (v3 and beyond) 
and host it as a service in the cloud. Think managed kubernetes, elasticsearch, etc or how we prefer to see it git 
and github. Git is a phenomenal tool for distributed version control and GitHub provides essentially git hosting as a service.

## Features

We're starting with a Developer plan focused on small teams and individuals. You likely don't want to manage infrastructure 
and want to focus on Go based microservices development in the cloud. That's what we're here for. Where Netlify 
is the frontend. Micro is the backend and Micro Platform is the host.

We're offering a free Developer plan to start which provides the following:

- Fully managed platform
- Public API endpoints
- Private repo support
- Upto 5 collaborators
- Upto 5 services
- Fair usage limits

## Getting Started

Visit the [getting started](/getting-started) guide if you just want to get started.

## How it works

The Micro Platform is a cloud service which lets you use Micro without having to manage infrastructure. We run highly available 
systems on managed kubernetes in the cloud e.g etcd, nats, cockroachdb and then provide a shared multi-tenant 
experience. From your standpoint its simply Micro hosted for you. For us its scratching an itch to fix 
the pain points with using AWS and other cloud providers.

As a developer you should just be able to focus on writing code but not just a single app, multiple applications 
and various design patterns in a way that's not limiting but removes choice and friction in a way that let's 
you be super productive. Micro + Micro Platform is just that!

### Hosting

The Micro Platform hosts Micro in the cloud using various cloud providers in different regions. Initially during the beta phase 
we're starting with Scaleway in Europe so that we can focus primarily on users needs and do it in a cost effective 
manner. Over time we'll move on to AWS, GCP and Azure in the US and Asia.

So how do you access it?

### Environments

Micro has the concept of environments or an "env" built in. These are basically different hosted Micro servers 
you can switch between to do development and run Micro services. Local is your local server running on "127.0.0.1:8081". 
Dev is the free hosted Micro Platform environment in the cloud.

You can swap between the platform and local like so

```
# local environment
micro env set local

# hosted environment
micro env set dev
```

### Services

Micro Platform provides a hosted version of Micro, which means anything built into the open source is available for you to use. 
This includes authentication, config, messaging, service discovery, service-to-service calls, storage, etc.

Micro comes with a pre-initialised Go library to run on a Micro server and the platform basically abstracts 
away the underlying infrastructure so you don't have to worry about it.

## Developer Plan

The Developer plan is free hosted cloud platform. It's a place thats great for small teams and individual developers. 
Our goal is to unlock large scale developer productivity and cross team, cross org collaboration. What GitHub did for source code 
we feel we could do for services.


See [m3o.com/start](https://m3o.com/start) for a quick start guide.

## Pricing

Our paid Business plan is a secure, scalable and supported production environment billed on a subscription pricing 
plan of $45/user/month. For that you get the ability to deploy upto 10 services with 2x the resource limits of Dev, invite 5 
people to collaborate with, support for private git repos and secure public api endpoints for your services. This includes 
support and business day response times.

Cloud and serverless pricing is anxiety inducing in a way that mostly now requires pricing calculators. This 
doesn't make sense to us. We believe to start developers should be given a fair flat subscription price 
and then we charge for additional services you use that are separate to the platform itself. 

### Additional Users

Every additional user added to your platform account is billed at $35/month. Whether you invite them or just plain create the 
account we'll keep track and invoice this as "M3O Platform Additonal Users" on your invoices.

### Additional Services

Beyond 10 services, we bill every additional service at $5/month. Additional service meaning anything with a new unique name 
e.g users, customers, orders. We'll add a line item on your invoice called "Micro Platform Additional Services" automatically.

## Fair Usage Limits

We invoke fair usage limits on the platform by capping everything to sane defaults for all namespaces. Over time we may 
make this configurable or allow you to pay for additional resources. For now the caps are as below per namespace.

### Developer

The per namespace limits of the Developer plan

- CPU - 1 core
- Memory - 1 Gb
- Disk - 10 Gb

### Business

The per namespace limits of the Business plan

- CPU - 2 cores
- Memory - 2 Gb
- Disk - 20 Gb

We apply caps across your namespace to limit overall resource usage. Caps may evolve or change in future to include 
different resource types but the goal is to provide a fair system that can be shared by all. You can cut up these 
resources however you like with 10 services running 1 instance each or 1 service running 10 instances.

## Future 

In the future we'll introduce different pricing tiers for teams and enterprise that include support and SLAs along with 
additional features for metrics, logs, etc. For now we really want to help small teams and individual developers.

## Next Steps

Head to the [signup](https://m3o.com/signup) page to get started or join us on [slack](https://slack.m3o.com) to chat.

To kick the tyres on the open source [Micro](https://github.com/micro/micro) project head to [micro.mu](https://micro.mu).
