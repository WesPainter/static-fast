# Static Fast

A (soon to be) series of infrastructure scripts for launching a static server for multiple service providers.

## What is this?

Who doesn't like easy infrastructure? A survey of how easy it can be to provision production-ready infrastructure across cloud providers.

## Site

Contains the example site that is used to mess around with different providers.

### Acceptance Criteria

- Commands:
  - One to provision all infrastructure with just a domain name (minus name-server setup)
  - One to deploy a pre-built static application
  - No custom deployment code, if possible
- Infrastructure Requirements:
  - Deployment behind a CDN
  - DNS Configuration
  - Application Storage
  - Permission management, if applicable
  - HTTPS with Provisioned Certificate

## Provider List

- AWS
- Cloudflare (next up)
- GCP (on deck)
- Azure (hopefully never)
