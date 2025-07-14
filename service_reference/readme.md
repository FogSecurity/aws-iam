# Service Reference

This folder contains data sourced from the programmatic service reference and other insights.

Release Blog Post: <>

Contact [info@fogsecurity.io](mailto:info@fogsecurity.io) for help and feedback. Feedback can be submitted here as well.

## Overview

In late 2024, AWS released [programmatic service reference information](https://docs.aws.amazon.com/service-authorization/latest/reference/service-reference.html) in json format.  This helps with IAM policy workflows.  Previously, open source libraries and other resources had to rely on the [Service Authorization Reference (SAR) pages](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html).  Tooling that needed to programmatically retrieve information about IAM actions previously had to scrape the web pages. This tooling includes Fog Security's tooling and other tools such as permissions.cloud.

For an overview of the programmatic service reference release, see Rowan Udell's post [here](https://blog.rowanudell.com/programmatic-aws-action-list/).

### AWS Timeline on Programmatic Service Reference Information
- Late 2024: AWS releases Programmatic Service Reference Information
- March 2025: AWS adds resources and condition keys to service reference information.
- June 2025: AWS adds action properties (such as write or list) to service reference information.

## Content

The following resources and insights were pulled and processed via python scripts.

### Complete Listing of Service Reference JSON Files

- Index: [service_ref.json](service_ref.json)
- Service Reference Files (by Service): [services/](services/)

### Actions with Additional Categories

This listing shows IAM actions that have multiple categories now.  In the programmatic listing of IAM Actions, actions could have multiple categories.  This is different than the previous model of Service Authorization Reference pages, where each action could only have 1 category.

- Actions with Addtional Categories: [actions_add_cat.json](actions_add_cat.json)

### Write and Tag Actions

This listing shows IAM actions annotated as both Write and TaggingOnly in the programmatic service reference.

- Actions annotated as both Write and Tag: [write_and_tag.json](write_and_tag.json)

### Permissions Management and Write Actions

This listing shows IAM actions annotated as both Permissions Management and Write in the programmatic service refernece.

- Actions annotated as both Permissions Management and Write: [perm_and_write.json](perm_and_write.json)

### Actions in Programmatic Reference but not in SAR

This listing shows IAM actions that were in the programmatic service reference information, but not listed on AWS's service authorization pages.

- Actions in Programmatic Reference but not in SAR: [actions_in_prog_not_sar.json](actions_in_prog_not_sar.json)

### Duplicates in SAR

This listing shows duplicate IAM actions that show up in multiple service authorization reference pages. 

- Service Authorization Reference Duplicate IAM Actions: [sar_duplicates.json](sar_duplicates.json)

## Resources and References

- [Permissions.Cloud](permissions.cloud)
- [Rowan Udell's Post on Programmatic AWS Service Reference](https://blog.rowanudell.com/programmatic-aws-action-list/)
- [AWS Programmatic Service Reference Information]()
