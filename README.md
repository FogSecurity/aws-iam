# AWS IAM Data

Fog Security: https://www.fogsecurity.io/ 

Contact info@fogsecurity.io for help and feedback. Additions or feedback can be submitted here as well.

This repository contains information parsed and processed from AWS IAM

## Tagging

For resources

### Resources with support for aws:ResourceTag

[Resources with support for aws:ResourceTag](tagging/resources_with_aws:ResourceTag_support.json)

#### Explanation

**aws:ResourceTag/tag-key** is a property of the resource.  The tags of the target resource of the request are evaluated.  

#### Methodology 



### Resources with support for aws:TagKeys

[Resources with support for aws:TagKeys](tagging/resources_with_tagKeys_support.json)

#### Explanation

**aws:TagKeys** is a property of the request and not necessarily a property of the resouce in question.  An example of this is when creating a resource, `aws:TagKeys` can be used to limit which tags can be used when creating a resource.  

#### Methodology 

We scanned through the Service Authorization pages of AWS IAM ([Actions, resources, and condition keys for AWS services](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html)) and looked for which IAM Actions supported `aws:TagKeys` in the condition keys section.  From there, we checked the resource types in the table that those actions could be applied to.  

`aws:TagKeys` -> IAM Action -> Supported Resources




### References

[AWS IAM: AWS Global Condition Context Keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html)

## References

https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html#condition-keys-tagkeys
