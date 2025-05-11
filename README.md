# Basic Public IP Monitoring Stack

## Overview

This stack provides a simple monitoring solution for public servers using:

- **node_exporter** — full system metrics collection
- **Prometheus** — metrics storage and querying
- **Grafana** — dashboards and visualization
- **Traefik** — reverse proxy with automatic HTTPS via Let's Encrypt

---

## Installation Guide

### 1. Clone the repository

```bash
git clone https://github.com/bonesiX/monitoring.git
cd monitoring
```

## 2. Configure your environment

Create and edit the `.env` file with values specific to your setup.

### ✅ Required variables

- **TRAEFIK_ACME_EMAIL** — A valid email address used for Let's Encrypt notifications.  
  _Must be functional and accessible._

```env
TRAEFIK_ACME_EMAIL=example@mail.ru
```

- **GF_SERVER_DOMAIN** - The domain that will be used to access Grafana over HTTPS.
_Must point to your server's public IP and be resolvable from the internet._

```env
GF_SERVER_DOMAIN=grafana.domain.example.com
```

### 🔧 Optional variables (with defaults)

```env
TRAEFIK_IMAGE_TAG=traefik:v3.4.0
PROM_IMAGE_TAG=prom/prometheus:v3.3.1
NODE_IMAGE_TAG=prom/node-exporter:v1.9.1
GF_IMAGE_TAG=grafana/grafana-oss:12.0.0
GF_SECURITY_ADMIN_USER=admin
GF_SECURITY_ADMIN_PASSWORD=admpass
```

## 3. Start the stack

```bash
docker compose up -d
```
