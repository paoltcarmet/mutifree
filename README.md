# V2Ray Cloud Run Multi-backend Proxy

This project deploys an NGINX reverse proxy to Google Cloud Run that forwards traffic to multiple V2Ray backends.

## 🌐 Features

- Load balances across multiple V2Ray backend servers
- Cloud Run compatible (`$PORT` binding)
- GitHub Actions to auto-push Docker image to Docker Hub

## 🚀 Deployment Steps

### 1. Clone & Edit

Edit `default.conf` to change:
- Backend servers
- WebSocket path (e.g. `/TG-@n4vpn`)

### 2. Docker Hub Secrets

Add these to your GitHub repo:
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

### 3. Cloud Run Deployment

After image is pushed:
```bash
gcloud run deploy v2ray-proxy \
  --image=docker.io/n4vpn/v2ray-muti:latest \
  --platform=managed \
  --region=asia-southeast1 \
  --allow-unauthenticated# muti
