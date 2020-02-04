# Template: Shiny app using Synapse authentication

---

### Prerequisites
---
#### System Requirements

* Python 3
* R

### Local Development Instructions

Sensitive data like passwords and secret keys should never be checked into git in cleartext (unencrypted). If you need to store sensitive info you can use the openssl cli.

#### Encrypt a file with shared secret
For local development, ideally we can settle on a single shared secret we'll use for all the encrypted files, ask around.

```
openssl enc -aes256 -base64 -in .Renviron -out .Renviron.encrypted
```

#### Decrypt a file with shared secret

```
openssl enc -d -aes256 -base64 -in .Renviron.encrypted -out .Renviron
```
