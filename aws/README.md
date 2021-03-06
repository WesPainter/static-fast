# AWS Quick Launch

Quick(!) launch for a static application deployed exclusively on AWS infrastructure.


### Prerequisits

- [Register](https://portal.aws.amazon.com/billing/signup) an AWS Account.
- [Create](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html#id_users_create_console) an admin user with programmatic access keys.
- [Download](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) and set up AWS cli with your api keys.
- [Move](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/MigratingDNS.html) your domain to route53 DNS name-servers.


### Provision
[<img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png">](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=static-fast&templateURL=https://static-fast.s3.amazonaws.com/cloudformation.yml)

or

```
aws cloudformationcreate-stack --stack-name static-fast \
  --template-url https://static-fast.s3.amazonaws.com/cloudformation.yml \
  --parameters DomainName=<ROOT_DOMAIN>,BucketName=<'' || BUCKET_NAME>
```

### Deploy

```
aws s3 sync . s3://<BUCKET_NAME>
```

### Teardown

```
aws cloudformation delete-stack --stack-name static-fast
```

### Resources Created

- Bucket
- BucketPolicy
- OriginAccessIdentity
- CloudFrontDistribution
- RootDnsRecord
- WwwDnsRecord
