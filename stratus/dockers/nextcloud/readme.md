# Nextcloud Cloud Storage

Where are your photos and documents? With Nextcloud you pick a server of your choice, at home, in a data center or at a provider.

## Install Docker

To install docker, follow the [official documentation](https://docs.docker.com/engine/install/).

## Setup Vaultwarden Docker Stack

### Env file

Copy and set restrictive permissions on the environement file

```bash
install -m 600 .env.example .env
```

Modify the env file

* `JWT_SECRET`: A secret for the JWT token
* `NEXTCLOUD_DOMAIN`: Domain used for nextcloud
* `NEXTCLOUD_URL`: The URL used for the nextcloud
