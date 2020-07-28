# Expose ToastE API

## **ToastE + GitHub Enterprise**

{% hint style="info" %}
**This step is likely already done. It was required to figure out {API\_URL}.**
{% endhint %}

ToastE needs to be able to receive webhooks from your Github Enterprise instance as well as make API calls to read data from GitHub. This is how ToastE stays on top of the latest changes in your pull requests in order to notify others about them. 

As mentioned in the "Getting Started" section, the easiest way to make sure that these services can communicate is by putting them in the same VPN/VPC, but as long as your firewall rules are configured correctly so that they can communicate, there should be no issue.

## **ToastE + Slack's Public API**

Similarly to the above ToastE requires bidirectional communication with Slack in order to post messages, as well as read in commands and act on them on behalf of the user.

Slack needs a public IP/URL to be exposed in order for it to communicate back to ToastE. This configuration is generally specific to the cloud provider that you are using, so you should look at the docs for setting up those routes.

### ngrok

One quick and popular option is to run ngrok on the host machine. Make sure you specify `subdomain` for the URL to stay the same:

```text
ngrok http -subdomain=acme-toast 10451
```

As a result of the above command service should be avaible at:   
https://acme-toast.ngrok.io 

{% hint style="info" %}
Even though ToastE is listening over a public connection, there is no security risk here because all messages coming in over that connection are signed by Slack and then verified by ToastE using secret verification token before any action is taken. Any message that fails that check will be thrown out ensuring that only valid content from Slack will be processed.
{% endhint %}

### Summary

As a result of this configuration, you should have public URL that toast is available by, we will refer to it as `{TOASTE_API_PUBLIC_URL}`in the following sections. You can verify that it works by accessing:  
`{TOASTE_API_PUBLIC_URL}/start` where you should be able to see the page we've seen before during [Setup Verification](deploy-toaste/setup-verification.md) step.

