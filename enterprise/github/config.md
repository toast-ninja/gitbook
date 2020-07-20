# Set Required Fields

{% hint style="warning" %}
**Prerequisites:** Private network address for your ToastE API \(a.k.a **TOASTE\_API\_URL**\).  
Use the variable obtained from previous step for all copy-pasted snippets below.
{% endhint %}

## Basic information

**GitHub App name: `Toast`**

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

