# Set Required Fields

{% hint style="warning" %}
**Prerequisites**   
Private network address for your ToastE Instance \(obtained previously\)  
Replace **TOASTE\_API\_URL** with that address in all snippets below.
{% endhint %}

## Basic information

**GitHub App name: `Toast App`**

**Homepage URL: `https://toast.ninja`**

## Identifying and authorizing users

**User authorization callback URL**

```text
{TOASTE_API_URL}/github/oauth-redirect?callback=1
```

## **Post installation**

**Setup URL \(NOT optional\)**

```text
{TOASTE_API_URL}/github/app-install-redirect
```

* [x] **Redirect on update**

## Webhook

* [x] **Active**

**Webhook URL**

```text
{TOASTE_API_URL}/webhooks/github/catch
```

\*\*\*\*

