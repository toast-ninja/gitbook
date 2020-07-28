---
description: >-
  On this step, we are going to collect the required environment variables and
  save them for later use.
---

# Environment Variables

### 1. Variables to capture

![](../../.gitbook/assets/image%20%2815%29.png)

### 3. Save using template

Save the above variables as plain text in a secure location. We will need this later. \(add it to previously saved `API_URL` variable\)

```text
GITHUB_APP_ID=
GITHUB_APP_CLIENT_ID=
GITHUB_APP_CLIENT_SECRET=
GITHUB_APP_URL=
```

### 4. Generate private key

Similarly, generate a private key and save it in a secure location.

![](../../.gitbook/assets/gh-private-key.png)

After you click this button it will start downloading a file that ends with `.private-key.pem` It's a text file that you can open in any text editor. 

Now is the tricky part. The entire contents of this file has to be set as ENV variable, but due to Docker's .env file limitations it has to be a single line string where all new line characters are replaced with `\n` You can use the following handy bash script to do the trick:

```text
awk -v ORS='\\n' '1' \
  your.private-key.pem | \
  rev | cut -c 3- | rev
```

If on OSX, use the following to copy it directly to your clipboard:

```text
awk -v ORS='\\n' '1' \
  your.private-key.pem | \
  rev | cut -c 3- | rev | \
  pbcopy
```

Finally, paste it to your file with other ENV variables, example:

```text
GITHUB_APP_PRIVATE_KEY=-----BEGIN RSA PRIVATE KEY-----\nMIIEpAIBAAKCAQEAxxbActo/leRinr+ngRb9FyfbaLAeTH4hO2DyE8k+6pJiwUPp\nHwCXnF6/80VkInlNUhYoYkfmEdHC3GhBwsg3SP/BI6+RyE/6ygpmx5XOI8XG0hkb\nfnBkKl/TITFJQUbf3j8n9kv3eDuFFxfPWTWv7+Ymn3R+B5p9nsebXoAQwqLRqmKF\n9qD/fPHOIQGjmiaFrWi3MOUbFjFJndE5P2V9sfAiEYciZBwrlzihnk27QW0Q+4Lv\nNZK5TJ+Woydb1JU/lx2GS6ORy1lBP6G3sWc+LrYQtSVB0ESRyvvtfNbOYbQrh/Vx\nrhDiLkcDiVztZ1I3LodaOuzksC26ue4pnrAZ+wIDAQABAoIBAF3QSMtWMJRPVHF9\n2k6oKIbazzcblotw+/PhEPFl6XHbnRF5EMb9HnQe6dCWqELeaiL+MfVt7+oBsBLw\nRdylP/f0HGzWdJmxpnnCQQBXhRWyQqgKELyZ9XlKQlDnyp8p6J/vnsMetPRBB8wD\n+j8NX2RqTVTiLekjUYKaiIoVStCL1+4gtu/dC2nAi5retOMWILv/NPJbtDAhcSzP\nYT1M47gkiMD+aXkfo8b2yUi6hycgyc+UADXX2HKe5Mf2Q0Gouk61iK3bzIe0RVRc\nVPKTbqPaUbpx6SsEhBXya8UaIIjTJ/z37cfvvUvfUvGOkXqcsQSssvf5FHIiSHu8\nB6QTPZECgYEA58hZYg3T5NKNQXtVTKpf/XncyGoZee2mB1Lzu4c6GKCfxjWW8Q4h\nN/0IznUNrSjri38HkAUeV1RTWtssc+T0xttCqsq4vbx0SPEmue176fNtFppdFSdt\nvXiP7vxpphqXKWjN6YQMMGy9aFYJJ5C4fitpCMMwqqmNea1MS6MNtmcCgYEA2+Pr\nntKzgwZ5ZRPOdjCw/0F9gD8SiM4KfmgbO1ScMQRQTTk8jYUwUAsJeZqnXHw2xkIf\n46zdYGhYgdJEZEOvB0lo5Za7St5+NAlMT1Pfpay6lNURuSCxbx5TYFb2a3tsYggT\nqeuq9RIoPwd6rPnpr/tUGq8xQYr0lmpqslQ1u00CgYEAqetRw7WZar4EukWdYgfh\nOSUWe4J0zNMxDVt9vTPEnntaxmdREcUnCzGgPCLJ9PDzxR9KPwXRmXoDZa8Z5pip\n7gKd3DGjv80hfrvzhQiZ+AfyKEjgBnsSU33IHw7CsPf7a2se0ZtxiCqfrJauPWg2\nKKDQbpER43tLcTFfpm+RxO8CgYEAgennC67w4DizAETzdmDOMgE/ZMXe7XTOPmDD\ntgoHPe6OgxGN9Q77vE7JCk+VEc9RjVEEBj/bi1oa8JiKT7KtdmCo2Px1K4bIiXX0\n3+lt+TRUCBrancXzDvObzw+SB26kWkbrVzkliCVyIcsJb6k3qAGVby6Sq2atmzDE\nWRfnpwECgYBY083HpIQogYKebYPSOUI9yWXU4ZzscWIQBGMYQqtpCyJxlymeK03y\nNx5qW9m57//icCqhCZJqJInLnjiKAN0YOjntIceElfkkZUXU7e88+jwYxDEfsQk2\nGAFSzgLOo3103N0aCuMgaGmsnKFu5Vg8E9lIIvF6hbRgvBvURIfLxA==\n-----END RSA PRIVATE KEY-----
```

We've done it! 😅

