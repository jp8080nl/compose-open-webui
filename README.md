# Open WebUI with Claude

A containerized setup of Open WebUI integrated with Claude 3.5 via API, running behind Traefik reverse proxy.

## Overview
The setup includes:
- Open WebUI container
- Traefik integration for reverse proxy (running separately)
    - SSL/TLS support via Let's Encrypt
    - Cloudflare DNS integration

## Prerequisites
- Docker and Docker Compose
- Traefik reverse proxy (running separately)
- Domain name configured in Cloudflare

## Quick Start
1. Clone this repository
2. Run `docker-compose up -d`
3. Access the UI at your configured domain

## Environment Variables
- `ANTHROPIC_API_KEY`: Your Anthropic API key (If you want to use Claude)
- `DOMAIN`: Your domain name
- `OPENWEBUI_PORT`: Port for the Open WebUI service (default: 3000)

## Architecture
- Open WebUI container connected to Traefik network
- Automatic SSL certificate management
- Cloudflare DNS integration via Traefik

## Development
Follow the standard Git workflow:
1. Create feature branch
2. Make changes
3. Test locally
4. Create pull request
