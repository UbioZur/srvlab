# N8N Password Manager

The world's most popular workflow automation platform for technical teams

## Install Docker

To install docker, follow the [official documentation](https://docs.docker.com/engine/install/).

## Setup N8N Docker Stack

### Env file

Copy and set restrictive permissions on the environement file

```bash
install -m 600 .env.example .env
```

Modify the env file

* `N8N_DOMAIN`: Domain used for n8n
* `N8N_DOMAIN_URL`: The public/webhook URL used for the n8n
* `N8N_DOMAIN_URL2`: A secondary URL (dashboard) used to access n8n
