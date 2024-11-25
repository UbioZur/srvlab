# NocoDB Password Manager

NocoDB allows building no-code database solutions with ease of spreadsheets.

## Install Docker

To install docker, follow the [official documentation](https://docs.docker.com/engine/install/).

## Setup NocoDB Docker Stack

### Env file

Copy and set restrictive permissions on the environement file

```bash
install -m 600 .env.example .env
```

Modify the env file

* `NOCODB_DOMAIN`: Domain used for nocodb
* `NOCODB_URL`: The URL used for the nocodb

