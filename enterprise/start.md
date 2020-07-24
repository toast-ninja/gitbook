# Getting Started

{% hint style="warning" %}
**Prerequisites**

* Host for running ToastE and dependent services
* ToastE kit
{% endhint %}

Docker Compose file is provided for the convenience of running everything on one VM. It is possible to run services separately if you choose.

The Docker Compose file references the following images: 

* ToastE application backend
* RabbitMQ
* Postgres 
* Redis

#### Host Requirements

* 2 GB RAM
* 5 GB Storage

{% hint style="info" %}
When you spin up the instance, make sure to jot down the instance's private IP, or its url if you set up a route for it internally.
{% endhint %}

**Network Requirements \(summary\)**

ToastE needs bidirectional network access to your GitHub Enterprise instance. Most ToastE customers opt for putting them in the same VPN/VPC.  
ToastE also needs bidirectional network access to Slack API via public IP.

More info to come about this in the "Expose ToastE API step"

