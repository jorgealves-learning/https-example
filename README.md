# HTTPS Implementation Demo

This repository demonstrates how to implement HTTPS using Docker and Docker Compose. It includes two approaches:
1. Using **Nginx** as a reverse proxy with HTTPS.
2. Using **Traefik** as a reverse proxy with HTTPS.

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- Self-signed certificates or valid SSL certificates for testing. [Some Info here](https://devcenter.heroku.com/articles/ssl-certificate-self)

## Directory Structure

```plaintext
https-demo/
├── nginx/
│   ├── docker-compose.yml
│   ├── conf.d/
│   │   └── default.conf
│   └── certs/
│       ├── domain.crt
│       └── domain.key
├── traefik/
│   ├── docker-compose.yml
│   ├── traefik.yml
│   └── certs/
│       ├── domain.crt
│       └── domain.key
└── README.md
```

## Running the Demos
### DNS Preparation

Ensure you update your /etc/hosts file with:

```plaintext
127.0.0.1 nginx.local
127.0.0.1 traefik.local
```

### Nginx

Generate certificates and Run via Makefile:

```bash
make generate-nginx-certs
make start-nginx
```

> Access the application at https://nginx.local.

### Traefik

Generate certificates and Run via Makefile:

```bash
make generate-traefik-certs
make start-traefik
```
> Access the application at https://nginx.local.

This structure ensures clarity and keeps Nginx and Traefik setups separate, making it easier to compare the two approaches.

