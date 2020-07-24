# Expose ToastE API

**ToastE + GitHub Enterprise**

ToastE needs to be able to receive webhooks from your Github Enterprise instance as well as make API calls to read data from GitHub. This is how ToastE stays on top of the latest changes in your pull requests in order to notify others about them. 

As mentioned in the "Getting Started" section, the easiest way to make sure that these services can communicate is by putting them in the same VPN/VPC, but as long as your firewall rules are configured correctly so that they can communicate, there should be no issue.

**ToastE + Slack's Public API**

Similarly to the above ToastE requires bidirectional communication with Slack in order to post messages, as well as read in commands and act on them on behalf of the user.

Slack needs a public IP/URL to be exposed in order for it to communicate back to ToastE. This configuration is generally specific to the cloud provider that you are using, so you should look at the docs for setting up those routes.

{% hint style="info" %}
Even though ToastE is listening over a public connection, there is no security risk here because all messages coming in over that connection are signed by Slack and then verified by ToastE before any action is taken. Any message that fails that check will be thrown out ensuring that only valid content from Slack will be processed.
{% endhint %}



