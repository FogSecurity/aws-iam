# Service Reference

This folder contains data sourced from the programmatic service reference and other insights.

Release Blog Post: <>

Fog Security: [fogsecurity.io](https://www.fogsecurity.io/)

Contact [info@fogsecurity.io](mailto:info@fogsecurity.io) for help and feedback. Feedback can be submitted here as well.

## Overview

In late 2024, AWS released [programmatic service reference information](https://docs.aws.amazon.com/service-authorization/latest/reference/service-reference.html) in json format.  This helps with IAM policy workflows.  Previously, open source libraries and other resources had to rely on the [Service Authorization Reference (SAR) pages](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html).  Tooling that needed to programmatically retrieve information about IAM actions previously had to scrape the web pages. This tooling includes Fog Security's tooling and other tools such as permissions.cloud.

For an overview of the programmatic service reference release, see Rowan Udell's post [here](https://blog.rowanudell.com/programmatic-aws-action-list/).

### AWS Timeline on Programmatic Service Reference Information
- Late 2024: AWS releases Programmatic Service Reference Information
- March 2025: AWS adds resources and condition keys to service reference information.
- June 2025: AWS adds action properties (such as write or list) to service reference information.

## Content

### Complete Listing of Service Reference JSON Files

Index: [service_ref.json](service_ref.json)
Service Reference Files (by Service): [services/](services/)



## Resources and References

- [Permissions.Cloud](permissions.cloud)
- [Rowan Udell's Post on Programmatic AWS Service Reference](https://blog.rowanudell.com/programmatic-aws-action-list/)
- [AWS Programmatic Service Reference Information]()
