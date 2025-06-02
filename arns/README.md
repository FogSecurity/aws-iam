# AWS IAM ARNs (Resource Identifier) Reference

Contact info@fogsecurity.io for help and feedback. Additions or feedback can be submitted here as well.

## ARNs in AWS

This folder contains a listing of AWS IAM ARNs found in AWS's Service Authorization Reference pages.  These pages are used as IAM references with IAM actions, resources, condition keys, and more.  This can help in least privilege and scoping permissions as well as understanding how IAM actions and AWS APIs can affect resources in AWS.

Current statistics:
- 1,929 Distinct Resource ARN Formats 

Searchable table: https://fogsecurity.io/aws-resources

### [AWS IAM ARNs](aws_resources.json)

#### Methodology

We programmatically went through each service's authorization reference (SRA) on AWS's Documentation.  There is also a programmatic reference listing for each service [provided by AWS here](https://docs.aws.amazon.com/service-authorization/latest/reference/service-reference.html).

### [AWS Service Prefixes](service_prefixes.json)

Listing of 441 AWS Services and the corresponding prefixes for those services.  These service prefixes are used in AWS IAM policies, documentation, and more.
