# AWS IAM Reference

Fog Security: https://www.fogsecurity.io/ 

Contact info@fogsecurity.io for help and feedback. Additions or feedback can be submitted here as well.

This repository contains information to help with AWS Identity and Access Management (IAM)

## ARNs and Resources

Amazon Resource Names (ARNs) uniquely identify AWS resources.  While ARNs follow a general format, each resource may have a different ARN format (such as S3 buckets which do not have an AWS Account ID in the S3 bucket ARN).  This folder contains information on ARN formats and service prefixes to assist with crafting least privilege IAM policies and more.

[ARNs](arns/)

## Tagging in AWS

Certain resources in AWS can be tagged (assigning metadata) to help with security, architecture, visibility, and more.  This folder contains information on IAM Permissions for tagging, which AWS resources support tagging, and more.

[Tagging](tagging/)
