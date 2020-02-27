# Cloudflare Quick Launch

Quick(!!) launch for a static application deployed exclusively on cloudflare infrastructure.

### Prerequisits

- [Register](https://dash.cloudflare.com/sign-up) a Cloudflare Account.
- [Create](https://support.cloudflare.com/hc/en-us/articles/200167836-Managing-API-Tokens-and-Keys) an API token using the `Edit Cloudflare Workers` permissions template.
- [Download](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) Wrangler and configure it with your API token.
- [Move](https://support.cloudflare.com/hc/en-us/articles/205195708-Changing-your-domain-nameservers-to-Cloudflare) your domain to Cloudflare DNS name-servers.


### Provision AND Deploy

Wrangler provides a very simple method for deploying your static application to Cloudflare. Simply run the following command
