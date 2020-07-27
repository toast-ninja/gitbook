# Environment Variables

{% hint style="warning" %}
#### Prerequisites

* ToastE API URL
* GitHub app variables
* GitHub app private key
* Slack app credentials
* `TOASTE_ID` Your `TOASTE_ID` is provided to you with your ToastE Kit. [Contact us](https://toast-team.gitbook.io/toast/support) if you do not have this.
{% endhint %}

### In case you missed them...

#### ToastE API URL

{% page-ref page="../host.md" %}

#### GitHub

{% page-ref page="../github/env-vars.md" %}

#### Slack

{% page-ref page="../slack/app-credentials.md" %}

## Set environment variables

Here's what you should have, following the templates:

```text
TOASTE_ID=<provided with ToastE Kit>

GITHUB_URL=<your GitHub Enteprise instance URL>
GITHUB_APP_CLIENT_ID=
GITHUB_APP_CLIENT_SECRET=
GITHUB_APP_ID=
GITHUB_APP_URL=
GITHUB_APP_PRIVATE_KEY=

SLACK_APP_OAUTH_TOKEN=
SLACK_APP_CLIENT_ID=
SLACK_APP_CLIENT_SECRET=
SLACK_APP_VERIFICATION_TOKEN=
SLACK_APP_SIGNING_SECRET=
SLACK_APP_ID=

API_URL=<ToastE Service URL e.g. https://toast.acme.com>
```

#### Save this in the `.env` file.

