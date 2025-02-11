# AWS IAM Data

Fog Security: https://www.fogsecurity.io/ 

Contact info@fogsecurity.io for help and feedback. Additions or feedback can be submitted here as well.

This repository contains information parsed and processed from AWS IAM

## Tagging

For resources

### Resources with support for aws:ResourceTag

[Resources with support for aws:ResourceTag](tagging/resources_with_aws:ResourceTag_support.json)

#### Explanation

**aws:ResourceTag/tag-key** is a property of the resource.  The tags of the target resource of the request are evaluated.  For example, we may want to write a policy that only allows an IAM principal to delete resources that have specific tags on them.  In this case, `aws:ResouceTag/tag-key` would be the condition we want to use.

#### Methodology 

We programmatically scanned through the Service Authorization pages of AWS IAM ([Actions, resources, and condition keys for AWS services](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html)) and looked for which IAM Actions supported `aws:ResourceTag/tag-key`.  From those IAM actions, we checked the resource types in the table that those actions apply to.

`aws:ResouceTag/tag-key` -> IAM Action -> Supported Resources

#### When to Use

Use this condition key when ensuring that an action is only permitted on resources with a certain tag.  For example, only allowing an IAM principal permission to stop ec2 instances with a specific tag.


### Resources with support for aws:TagKeys

[Resources with support for aws:TagKeys](tagging/resources_with_tagKeys_support.json)

#### Explanation

**aws:TagKeys** is a property of the request and not necessarily a property of the resouce in question.  An example of this is when creating a resource, `aws:TagKeys` can be used to limit which tags can be used when creating a resource.  

#### Methodology 

We programmatically scanned through the Service Authorization pages of AWS IAM ([Actions, resources, and condition keys for AWS services](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html)) and looked for which IAM Actions supported `aws:TagKeys` in the condition keys section.  From there, we checked the resource types in the table that those actions could be applied to.  

`aws:TagKeys` -> IAM Action -> Supported Resources

#### When to use

Use this condition key when tags are required.  For example, ensuring that required tags are present when tagging a resource.  Note, this does not check to see what the tag key value may be.  To check for the tag key value in a request, we recommend using `aws:RequestTag/tag-key`.


### References

[AWS IAM: AWS Global Condition Context Keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html)

## References

https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html#condition-keys-tagkeys
