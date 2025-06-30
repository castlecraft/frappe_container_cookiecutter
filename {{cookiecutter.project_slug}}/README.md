# Frappe / ERPNext Project Builds

This repo hosts builds for Frappe and/or ERPNext apps

# Build and Push Container Image with Custom App

## Common Files

- `common/build.env`: common environment variables to pass as build args
- `staging/template-apps.json`: list of apps and their branches for staging environment
- `production/template-apps.json`: list of apps and their branches for production environment
- `scripts/generate_apps_json.py`: script to generate apps.json with username and pat to clone private repos.

## Github

- `.github/workflows/build-and-push.yaml`: common file to build image
- `.github/workflows/staging-build.yaml`: build staging image
- `.github/workflows/production-build.yaml`: build production image

Actions variables:

- `DOCKER_USERNAME`: Container registery user name to push images.
- `REPO_USER`: Repo username to pull frappe apps git repos during image build.

Actions secrets:

- `DOCKER_DEPLOYMENT_TOKEN`: Container registery password to push images.
- `MACHINE_USER_PAT`: Repo PAT to pull frappe apps git repos during image build.

## Gitlab

- `.gitlab-ci.yml`: Gitlab CI File

# Usage

- Change the list of apps and their branches in `staging/template-apps.json` to build staging image.
- Change the list of apps and their branches in `production/template-apps.json` to build production.

# Installation

Installing Docker Swarm, Traefik, Portainer and Custom Frappe/ERPNext stack: https://github.com/castlecraft/custom_containers/blob/main/docs/docker-swarm.md

Portainer GitOps: https://www.youtube.com/watch?v=IZss2CziUnI

Kubernetes: https://github.com/frappe/helm/blob/main/erpnext/README.md
