# Template: Shiny app using Synapse authentication

### Prerequisites

#### System Requirements

* Python 3
* R

### Local Development Instructions

First, [create and register your OAuth 2.0 client](https://docs.synapse.org/articles/using_synapse_as_an_oauth_server.html). Create one client for local testing and another one for production. (The `create_prod_client()` and `create_local_client()` functions in `connect_to_synapse.py` can be used for this - simply modify them with your own app name and redirect uris.)

To store environment variables, create an .Renvironment file in the project directory with the following format:

```
SYN_USERNAME=<synapse username>
SYN_API_KEY=<synape API key>
CLIENT_ID=<client id>
CLIENT_SECRET=<client id>
CLIENT_ID_LOCAL=<client id for local testing>
CLIENT_SECRET_LOCAL=<client secret for local testing>
```

### Secrets

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
