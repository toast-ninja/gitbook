# Deploy ToastE

{% hint style="warning" %}
**Prerequisites**

* [ToastE `API_URL`](../host.md)\`\`
* [GitHub app variables](../github/env-vars.md)
* [Slack app variables](../slack/app-credentials.md)
* `TOASTE_ID`
* Docker registry access

`TOASTE_ID` and Docker registry credentials are provided with your ToastE Kit.  
Docker sends you a separate invitation to our Docker Hub.  
[Contact us](../../support.md) if you do not have this.  
**Ensure that you have Docker registry access before proceeding.**
{% endhint %}

{% hint style="warning" %}
**Host Prerequisites**

* Docker 19.03.8 or later
* `docker-compose` version 1.25.5 or later
{% endhint %}

We recommend creating a folder named `toast` and copying the `docker-compose.yml` there.

## Set environment variables

Create`.env.external` and paste all collected ENV variables to it.  
Example `.env.external` file:

```text
TOASTE_ID=G027RC2UL5R
API_URL=https://toast.acme.com

SLACK_APP_CLIENT_ID=506995332789.565588071812
SLACK_APP_CLIENT_SECRET=775905b1733b571cf245d456af34f56b
SLACK_APP_VERIFICATION_TOKEN=Zsd6jZcNyWFjlAbelsbGBxll
SLACK_APP_SIGNING_SECRET=42bf6a4d60ebf532ded6b4fce1a37ce4
SLACK_APP_ID=ATHGA23PW

GITHUB_URL=https://github.acme.com
GITHUB_APP_CLIENT_ID=Iv1.ae6b76dfe30b4072
GITHUB_APP_CLIENT_SECRET=56491509c1afdfdd9a7342c9d1c18a123c0f5e42
GITHUB_APP_ID=1
GITHUB_APP_URL=https://github.acme.com/github-apps/toast

GITHUB_APP_PRIVATE_KEY=-----BEGIN RSA PRIVATE KEY-----\nMIIEowIBAAKCAQEAqoF5YAHZcQ+awCMkGrcTFwZ+5mTmZkQiQ89jwz54npQ/9DOO\nk0yfRoF4KBvgIfbIlsc9n9fp71+EhYZ6LcHQidgO3czLw3fkzmN4VfcNCHnnQ394\nP9B2MwpOzXUKGg0DXlIctkHCfPqOkPfNGj/NioSBHHT0XdTvGoKa6oMuOYFOBHst\nJv2XR2ILOQWWA+HsMQWNOj3bVtKxaV2ppgzELaDguMD2PNmDOPFPmmT8pIFSch5m\nFtaWXGNnfaAYXB0hwXhzayOeIpUMglESzgDpmQsvogYtrvw2j4C8H0aazI5g+Yt/\nv/TOmfHTUD+rHxBagz2eKYxdO1Riyn8SovoDNQIDAQABAoIBAAG9kpydSDf0PdMq\nSKsRJVu90DvP2d4/Yc4pZs5Oa/LKdqCqihEM3i9dEPnv1ujh2QhY/lMMZDHyWqr2\nRXcEHHnbv8MZ3RagubA1qbvO6s4kWG0C9xpHqX055LYKNNExQtCKrApcP30BHcVz\nEh/reNCqK5s7wmbWzp4JqUUtk6I4oGwpdODKLQ5IoYzssyMKGZmZ/zuINsEnrMUx\nvH/qS6vyBgraJV+1HQSb9ZPpSDxyr8066wLa87/esPuXY6AnoXd7yDyu0B+JWA6n\nOmK96PFnVfsTUEfF1YlkhtXWxnM6DwsI9d5Cv76HibOZ7ladaIgxtVgiteHD8M+d\ndUQQwsECgYEA1D7aSkN+fsHsoKKU9nOz7rSlmMkX4I/0cJx/riGpuBYPOspKf40q\nkwrQ5PleabY5VYlGuSia34oQ9fQB4eaSrF0qc0CMJcksukgCqTocPWr/BnGmoOqH\nht+XmM9IAtwpMQaDuEipHOlW7OMP1fi3w/xgs962OjzJSzRagJLlsQUCgYEAzafT\nw8yEISWH2PbGUNW7tmzXBptz7sXwREtVfV9Y35x4A7sdN5pzWSKnzo2QRoB8sxZ8\ngorBafmRQZjIOO37GwpIwBWGtQ7+GNRozRS8nSLX+ND6ZCwc8EUfxWux82TpfBAc\netlnPmcGuNYtLVXklenhTRQYVI7f0n6ylU5xYHECgYEAuMGx0b2pKnxzGG4Oj+6u\nLdfQ4wwCHfgSB8kjmBgznkyNm1amvRvMeM2MhBXTKuB2TlA+YUXIc1jDZOawkM3e\n1e4P2t3QYcAakFnI/zjXhltSfnCGZUNjEHQoidu+SscNkGCkXtHZbJJuma0aht+I\nUDGsmEcBh/aMH0wGkC/PhGUCgYAPYrnmERvlevBR3Ax0KblUaYogtWqT930FLvmj\nWonEmOklpk8GROjSR1R0kIS1sZEiuNDx1z2nFwO1+58nGy7JFBjjPfkI/Kkn5GQ+\ny4lc3Cl6NPA2pFI564H3/BmhEvCg1ne6/R7LPVv0YhmZJa7nREsVwCYd1V6LWe00\nXF0BEQKBgF/UykgPfgrqiIXq4AtoXgL6MBn4PifyCpjtya44LCjQFiM8lrPBg4sl\nPufTcDblPPlxTt6ehJXToe80biVC3IMJXX8ICJ8OPsRmWuBKDgyY9Wy+nsbfuiSt\nwmGI+IkkqlMxbB6ylGVgPw1rILDzwO21hKhj+dxf8pba7GM5AEoH\n-----END RSA PRIVATE KEY-----
```

Configure the connection to Toast's private docker registry using credentials you set up. Run:

```text
docker login
```

In the folder with `docker-compose.yml` and `.env.example` file, run:

```text
docker-compose up
```

You may notice some errors and service restarts during the initial warm-up. It's likely normal. There is no easy way for services to wait for one another in the new `docker-compose`, and we implemented it by letting our service restart until it connects to required services. Wait for the output to pause, with these last lines:

```text
toaste_backend | [web][info] Starting web process...
toaste_backend | [web][info] HTTP Server is listening at http://localhost:10451
```

On the next step, we will verify that our setup is working.

