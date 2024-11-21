# Traefik Reverse Proxy

Traefik is a leading modern open source reverse proxy and ingress controller.

## Install Docker

To install docker, follow the [official documentation](https://docs.docker.com/engine/install/).

## Setup Traefik Docker Stack

### Env file

Copy and set restrictive permissions on the environement file

```bash
install -m 600 .env.example .env
```

Modify the env file

* `TRAEFIK_GANDIV5_PERSONAL_ACCESS_TOKEN`: Gandi Personal Accesss Token key applicable
* `TRAEFIK_CF_DNS_API_TOKEN`: Cloudflare DNF API Token if applicable
* `TRAEFIK_ACME_EMAIL`: Email to use for the letsencrypt cerification
* `TRAEFIK_DOMAIN`: Domain used for traefik dashboard
* `TRAEFIK_DASHBOARD_URL`: The URL used for the traefik dashboard
