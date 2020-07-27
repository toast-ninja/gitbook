# Environment Variables

{% hint style="warning" %}
#### Prerequisites

* GitHub app environment variables
* GitHub app private key
* Slack app credentials
* `TOASTE_ID`\* \* This will be provided to you with your ToastE Kit. [Contact us](https://toast-team.gitbook.io/toast/support) if you have not received this.
{% endhint %}

{% page-ref page="../github/env.md" %}

{% page-ref page="../slack/app-credentials.md" %}

## Set environment variables as follows.

```text
TOASTE_ID=<provided in email>

SLACK_APP_OAUTH_TOKEN=
SLACK_APP_CLIENT_ID=
SLACK_APP_CLIENT_SECRET=
SLACK_APP_VERIFICATION_TOKEN=
SLACK_APP_SIGNING_SECRET=
SLACK_APP_ID=

GITHUB_URL=<your GitHub Enteprise instance url>
GITHUB_APP_CLIENT_ID=
GITHUB_APP_CLIENT_SECRET=
GITHUB_APP_ID=
GITHUB_APP_URL=https://github.com/apps/toast-app-dev
GITHUB_APP_PRIVATE_KEY=

API_URL=<Toast Service URL e.g. https://toast.acme.com>
```



