---
description: >-
  Please fill out the information on the page exactly as described below. Don't
  forget to check checkboxes.
---

# Set Required Fields

{% hint style="warning" %}
**Prerequisites:** The `API_URL` in your ENV variables file.  
Replace `API_URL` with that address in all snippets below.
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
Depending on whether `API_URL` uses HTTPS or not, enable or disable SSL verification respectively. \(It is commonly acceptable to disable this option inside private VPN.\)
{% endhint %}

