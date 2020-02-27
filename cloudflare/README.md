# Cloudflare Quick Launch

Quick(!!) launch for a static application deployed exclusively on cloudflare infrastructure.

### Prerequisits

- [Register](https://dash.cloudflare.com/sign-up) a Cloudflare Account.
- [Create](https://support.cloudflare.com/hc/en-us/articles/200167836-Managing-API-Tokens-and-Keys) an API token using the `Edit Cloudflare Workers` permissions template.
- [Download](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) Wrangler and configure it with your API token.
- [Move](https://support.cloudflare.com/hc/en-us/articles/205195708-Changing-your-domain-nameservers-to-Cloudflare) your domain to Cloudflare DNS name-servers.


### DNS Gotchas (Acceptance Criteria Fail)

#### Dummy DNS record required for domain

You can't find it anywhere in the docs (as of 2/27/20), but [Cloudflare workers require at least an A record](https://github.com/cloudflare/wrangler/issues/93) on the root domain to be present. Since the entire site is served from a worker, there isn't a proper destination IP for the `A` record. This is slightly confusing.

The solution is to create an `A` record on your root domain that points to a dummy IP, like `192.0.2.1`. While you are at it, you can `CNAME` `www` to point toward your root domain. This will ensure you meet the acceptance criteria for this project.

To do so, you can run the following command, which utilizes the Cloudflare API to build a dummy `A` record on the root domain of your choice. Additionally, it will create a `CNAME` record for `www` that points to the root record.

#### Must specify www subdomain as route

In addition to the root domain, one must specify the  `www` subdomain as a route in `wrangler.toml`. Otherwise, your static site will not be accessible via `www.example.com`.

### Provision AND Deploy

Wrangler provides a very simple method for deploying your static application to Cloudflare. Simply run the following command
