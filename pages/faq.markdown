---
layout: default
title: FAQ
nav_order: 5
permalink: /faq
---

# FAQ
{: .no_toc }

## Account Recovery

Issue `micro signup --recover --email=youremail` which will email you instructions on how to log in to namespaces you have access to.
Currently there is no password recovery functionality, please contact us on Slack to do that.

## Billing Portal

To access your billing portal to adjust billing info or retrieve invoices run the following command to get your unique link.

```
micro billing portal
```

## Pricing

The Micro Platform is free for developers. Our Business plan is charged at $45/user/month which provdes additional resources and support.

## Additional Users

You can invite up to 5 additional users on the platform. Every additional user added to your account is billed at $45/month. 
Whether you invite them or just plain create the account we'll keep track and invoice this as "Micro Platform Additonal Users" on your invoices. See 
[Get Started > Invite Users](/getting-started/invite-users) to see how to invite them.

## Additional Services

Beyond 10 services, we bill every additional service at $5/month. Additional service meaning anything with a new unique name
e.g users, customers, orders. We'll add a line item on your invoice called "M3O Platform Additional Services" automatically.

## Changing Your Password

Use the following command to change password (you must already be logged in):

```
micro user set password
```

## Developer plan

The Developer plan is a free tier of the Micro Platform for small teams and individuals.

To signup and login see the following.

```
# set the dev env
micro env set dev

# signup for free
micro signup

# login
micro login 
```

The free plan is also subject to fair usage. There are no SLAs or support. The quota is capped at 1 core and 1GB total resources.

## Fair Usage Policy

Our fair usage policy applies caps to usage on a per namespace basis. This is so we can maintain a shared system 
for everyone to use in coordination and have a great experience. The limits are below but may change, vary or include new resource types.

### Developer

The per namespace limits of the free plan

- CPU - 1 core
- Memory - 1 Gb
- Disk - 10 Gb

### Business

The per namespace limits of the paid plan

- CPU - 2 cores
- Memory - 2 Gb
- Disk - 20 Gb

## Cancellation

If you'd like to cancel your subscription please email [support@m3o.com](mailto:support@m3o.com).

## Support

If you're a paying customer you can join #support on [slack](https://slack.m3o.com) or email [support@m3o.com](mailto:support@m3o.com). Otherwise you can join #platform for general discussions around each environment.
