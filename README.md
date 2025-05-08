# Basic monitoring
## Spec
- node_exporter full
- prometheus
- grafana
- nginx as a reverse proxy for grafana

# Guide to install

1. Clone repo
   
   ```bash
   git clone <repo_url
   ```
2. Create certs
   ```bash
   cd monitoring/cert
   openssl genrsa -out ca.key 2048
   openssl req -new -x509 -days 365 -key ca.key -out ca.crt
   ```
3. Specify variables to you environment
   
