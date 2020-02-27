# Static Fast

A (soon to be) series of infrastructure scripts for launching a static server for multiple service providers.

## What is this?

I was making a CloudFormation template for a pet static site project and I wondered how much effort this same task would be with various cloud providers. What follows is a personal journey through several cloud providers with one question: with the end goal of single-command deploys of a static application, which cloud service provider can meet this goal with the least effort.

### Provider List

Roadmap of vendors that have been or will be covered.

- AWS
- Cloudflare (next up)
- GCP (on deck)
- Azure (hopefully never)

### Acceptance Criteria

The static application should be sufficiently set up to run a production workload.* The following criteria is established to meet this requirement.

- Commands:
  - One to provision all infrastructure with just a domain name (minus name-server setup)
  - One to deploy a pre-built static application
  - No custom deployment code, if possible. (Stick to templates)
- Infrastructure Requirements:
  - Deployment behind a CDN
  - DNS Configuration
  - Application Storage
  - HTTPS with automatic certificate management
  - Permission management, if applicable

### Prerequisites

Projects for each cloud provider attempt to utilize tools provided directly by the cloud provider (no 3rd party orchestration, no programming languages) in order to set up the infrastructure. This means that each provider has its own set of requisite dependencies. See the README contained in each provider folder for further instructions.

Additionally, a domain name is needed. It must be configured to utilize name-servers from the given providers in order to work with these scripts.

### Test Site

```
/public
```

The public folder a dummy site built with the [hugo](https://gohugo.io/) framework for constructing static sites. The application is simply the end result of following the [quickstart guide](https://gohugo.io/getting-started/quick-start/).

When testing a static site deployment, you must build a fresh copy of the site into a folder named `public` located inside the desired cloud provider. Make sure to include your custom domain. For example, to prepare to deploy to AWS using the domain `example.com`, you would run:

```
$ hugo -s site -d ../aws/public -b http://example.com  --cleanDestinationDir
```
