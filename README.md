# Basic monitoring for public IP address
## Spec
- node_exporter full
- prometheus
- grafana
- nginx as a reverse proxy for grafana

## Guide to install

1. Clone repo
   
   ```bash
   git clone <repo_url>
   ```
2. Create certs
   ```bash
   cd monitoring/cert
   openssl genrsa -out ca.key 2048
   openssl req -new -x509 -days 365 -key ca.key -out ca.crt
   ```
3. Specify variables to your environment
   ```bash
   Grafana Login
   export GF_SECURITY_ADMIN_USER=<user>
   Grafana Password
   export GF_SECURITY_ADMIN_PASSWORD=.    <password>
   Server FQDN
   export VPS_DOMAIN=<your-host>
   ```
4. Start compose
   ```bash
   cd ..
   docker compose up -d
   ```
