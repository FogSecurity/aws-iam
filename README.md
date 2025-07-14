# AWS IAM Reference

Fog Security: https://www.fogsecurity.io/ 

Contact info@fogsecurity.io for help and feedback. Additions or feedback can be submitted here as well.

This repository contains information to help with AWS Identity and Access Management (IAM)

## Service Reference

AWS recently released (late 2024) a programmatic service reference.  This changes IAM workflows as previously one of the only ways was to scrape the Service Authorization Reference web pages. These changes can affect IAM workflows if you're using SAR pages or programmatic references of IAM actions - for example, open source IAM tools or policy and permission level classifications. 

Changes include:
- Multiple categorization of IAM Actions
- Inconsistencies in Action Listings
- Inconsistencies in Classification of IAM Actions
- Categorization Changes

[service_reference](service_reference/)

## ARNs and Resources

Amazon Resource Names (ARNs) uniquely identify AWS resources.  While ARNs follow a general format, each resource may have a different ARN format (such as S3 buckets which do not have an AWS Account ID in the S3 bucket ARN).  This folder contains information on ARN formats and service prefixes to assist with crafting least privilege IAM policies and more.

[ARNs](arns/)

## Tagging in AWS

Certain resources in AWS can be tagged (assigning metadata) to help with security, architecture, visibility, and more.  This folder contains information on IAM Permissions for tagging, which AWS resources support tagging, and more.

[Tagging](tagging/)
