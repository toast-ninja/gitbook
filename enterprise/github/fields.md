---
description: >-
  Please fill out the information on the page exactly as described below. Don't
  forget to check checkboxes.
---

# Set Required Fields

{% hint style="warning" %}
**Prerequisites**   
Private network address for your ToastE Instance \(obtained previously\)  
Replace **API\_URL** with that address in all snippets below.
{% endhint %}

## Basic information

**GitHub App name: `Toast`**

**Homepage URL: `https://toast.ninja`**

## Identifying and authorizing users

**User authorization callback URL**

```text
{API_URL}/github/oauth-redirect?callback=1
```

## **Post installation**

**Setup URL \(NOT optional\)**

```text
{API_URL}/github/app-install-redirect
```

* [x] **Redirect on update**

## Webhook

* [x] **Active**

**Webhook URL**

```text
{API_URL}/webhooks/github/catch
```

## **SSL verification**

{% hint style="info" %}
Depending on whether {API\_URL} uses HTTPS or not enable or disable SSL verification. \(Since we are inside private VPN it's often acceptable to disable this option\)
{% endhint %}

