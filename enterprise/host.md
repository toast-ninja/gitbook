# Host Setup

{% hint style="warning" %}
**Prerequisites**

* Host for running ToastE and dependent services
* ToastE kit
* Docker version 19.03.8 or later
* `docker-compose` version 1.25.5 or later \(comes with docker\)
* Text file to start collecting `ENV` variables during setup
{% endhint %}

Docker Compose file \(`docker-compose.yml`\) is provided for the convenience of running everything on one VM. _It is possible to run services separately if you choose._

The Docker Compose file references the following images: 

* ToastE application backend
* RabbitMQ
* Postgres 
* Redis

## Host Requirements

* 2 GB RAM
* 5 GB Storage

### Private **Network Requirements**

ToastE needs bidirectional network access to your GitHub Enterprise instance. Most ToastE customers opt for putting them in the same VPN/VPC. 

{% hint style="info" %}
When you spin up the instance, note the instance's **private IP for the ToastE instance** or its URL if you set up a DNS for it internally. You will need this in the next step.
{% endhint %}

Toast by default runs on port `10451`. So your URL might look like: `http://192.0.0.168:10451`  
It's the first environment variable you'd need to collect:

```text
API_URL=http://192.0.0.168:10451
```

### Public Network **Requirements**

ToastE also needs bidirectional network access to Slack API via public IP. It's possible to set this up using services like [ngrok](https://ngrok.com/) or your cloud provider configuration. **Make sure the public address stays static.** This step can be done later after we get ToastE up and running.

More info in the [Expose ToastE API](expose-toaste-api.md) step.

## **Database**

By default, ToastE uses a dockerized Postgres instance, and stores data on your local file system in the same working directory \(in `./postgres-data`\) where you run the `docker-compose.yml`file. _It is possible to use an externally managed database if you choose._ 

#### Managed database __\(optional\)

* Postgres version 10.11+
* Remove or comment out Postgres section from `docker-compose.yml` file. 
* Remove it from the `depends_on` section for ToastE service as well
* Provide a connection string in the environment variable:

```text
DATABASE_URL=postgres://toast:toast@postgres:5432/toast
```

## Enterprise ID

You are provided with your unique `TOASTE_ID`. Your file should now look something like:

```text
TOASTE_ID=<from email>
API_URL=http://192.0.0.168:10451
```

