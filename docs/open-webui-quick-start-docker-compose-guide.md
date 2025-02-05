# Open WebUI Quick Start Docker Compose Guide

Important Note on User Roles and Privacy:
Admin Creation: The first account created on Open WebUI gains Administrator privileges, controlling user management and system settings.
User Registrations: Subsequent sign-ups start with Pending status, requiring Administrator approval for access.
Privacy and Data Security: All your data, including login details, is locally stored on your device. Open WebUI ensures strict confidentiality and no external requests for enhanced privacy and security.
All models are private by default. Models must be explicitly shared via groups or by being made public. If a model is assigned to a group, only members of that group can see it. If a model is made public, anyone on the instance can see it.
Choose your preferred installation method below:

Using Docker Compose simplifies the management of multi-container Docker applications.

Docker Compose requires an additional package, docker-compose-v2.

Warning: Older Docker Compose tutorials may reference version 1 syntax, which uses commands like docker-compose build. Ensure you use version 2 syntax, which uses commands like docker compose build (note the space instead of a hyphen).

Example docker-compose.yml
Here is an example configuration file for setting up Open WebUI with Docker Compose:

version: '3'
services:
  openwebui:
    image: ghcr.io/open-webui/open-webui:main
    ports:
      - "3000:8080"
    volumes:
      - open-webui:/app/backend/data
volumes:
  open-webui:

Starting the Services
To start your services, run the following command:

docker compose up -d

Helper Script
A useful helper script called run-compose.sh is included with the codebase. This script assists in choosing which Docker Compose files to include in your deployment, streamlining the setup process.

Note: For Nvidia GPU support, add the following to your service definition in the docker-compose.yml file:

deploy:
  resources:
    reservations:
      devices:
        - driver: nvidia
          count: all
          capabilities: [gpu]

This setup ensures that your application can leverage GPU resources when available.