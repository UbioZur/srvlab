# Vaultwarden Password Manager

An alternative server implementation of the Bitwarden Client API

## Install Docker

To install docker, follow the [official documentation](https://docs.docker.com/engine/install/).

## Setup Vaultwarden Docker Stack

### Env file

Copy and set restrictive permissions on the environement file

```bash
install -m 600 .env.example .env
```

Modify the env file

* `VAULTWARDEN_ADMIN_TOKEN`: A long and complicated hash used as an admin token
* `VAULTWARDEN_DOMAIN`: Domain used for vaultwarden dashboard
* `VAULTWARDEN_URL`: The URL used for the vaultwarden dashboard
