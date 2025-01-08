# Trilium Next Notes

TriliumNext Notes is a hierarchical note taking application with focus on building large personal knowledge bases.

## Install Docker

To install docker, follow the [official documentation](https://docs.docker.com/engine/install/).

## Setup Trilium Next Docker Stack

### Env file

Copy and set restrictive permissions on the environement file

```bash
install -m 600 .env.example .env
```

Modify the env file

* `TRILIUM_DOMAIN`: Domain used for trilium
* `TRILIUM_URL`: The URL used for trilium
