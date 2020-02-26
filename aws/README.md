# AWS Quick Launch

"Quick" launch for a static application deployed exclusively on AWS infrastructure.

## Resources Created

- Bucket
- BucketPolicy
- OriginAccessIdentity
- CloudFrontDistribution
- RootDnsRecord
- WwwDnsRecord

## Before you start

If you intend on using a custom domain, you must set it up for use with Route53. To do this, you must add do route 53


### No download deploy
[<img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png">](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=static-fast&templateURL=https://static-fast.s3.amazonaws.com/cloudformation.yml)

### Running It
