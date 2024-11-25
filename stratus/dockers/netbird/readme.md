# Netbird Password Manager

NetBird combines a configuration-free peer-to-peer private network and a centralized access control system in a single open-source platform

## Install Docker

To install docker, follow the [official documentation](https://docs.docker.com/engine/install/).

## Setup Netbird Docker Stack

### Env file

Copy and set restrictive permissions on the environement file

```bash
install -m 600 .env.example .env
```

Modify the env file

* `NB_SETUP_KEY`: The Setup Key for Netbird
