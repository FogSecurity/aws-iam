# AWS IAM Tagging Data and Resources

Fog Security: https://www.fogsecurity.io/ 

Contact info@fogsecurity.io for help and feedback. Additions or feedback can be submitted here as well.

This repository contains information to help with tagging and tag compliance in AWS.   

## Tagging in AWS

Certain resources in AWS can be tagged (assigning metadata) to help with security, architecture, visibility, and more.  We won't go into much detail on benefits of tagging here.  AWS provides guidance [here](https://aws.amazon.com/solutions/guidance/tagging-on-aws).

### Statistics

IAM Actions
* 1010 distinct IAM actions for tagging.

AWS classifies IAM actions in 5 categories: read, list, write, permissions management, or tagging.
* 331 IAM actions classified as read or list.
* 17 IAM actions classified as write.
* 662 IAM actions classified as tagging.

AWS Resources
* 1439 Resources that support Resource Tags on an IAM Action.
        

### Full List of Tagging Actions in AWS

File: [json file of actions with 'tag' in the action](tagging_actions.json) 


Example action:
```
{
        "service": "Amazon S3",
        "action": "PutObjectTagging",
        "access_level": "Tagging",
        "description": "Grants permission to set the supplied tag-set to an object that already exists in a bucket",
        "service_prefix": "s3"
},
```

#### Explanation

This file contains all the AWS IAM Actions in a json file that have "tag" in the action.  

#### Methodology

We programmatically scanned through all AWS service authorization pages for each AWS service and pulled a list of actions that contained "Tag" (case insensitive).  We then removed actions that are not directly tied to "tagging".

Removals:
* Cost Explorer CostAllocationTag
* Actions that contain references to staging (stage, staging)
* Resource Groups TagSyncTask
* Cloudfront CreateStreamingDistributionWithTags
* Cognito PrincipalTagAttributeMap
* Lake Formation TagExpression
* Service Catalog TagOption


### IAM Actions with Tag

File: [txt file of IAM Actions with tag](iam_actions_with_tag.txt)

#### Explanation

* 1010 distinct IAM actions for tagging.

This is a stripped down version of the full list of tagging actions above.  It contains a listing of tag actions without additional information.  The full list of tagging actions does not fit within an IAM policy.

#### Methodology

We removed other information to get <service_prefix>:<action> in a txt file.


### View Tagging IAM Actions (Read or List Classifications)

File: [txt file of View IAM Actions with tag](view_tag_actions.txt)

#### Explanation

* 331 Read or List classified IAM actions for tagging.

Similar to above, this is a stripped down version of tagging actions above.  It contains a listing of tag actions that are classified either read or list.  Note: the full list of read or list tagging actions also does not fit within an IAM policy.

#### Methodology

We removed other information to get <service_prefix>:<action> in a txt file.


### Resources with support for aws:ResourceTag

File: [Resources with support for aws:ResourceTag](resources_with_resource_tag_support.json) \
json structure: {service, resource, arn}

#### Explanation

**aws:ResourceTag/tag-key** is a property of the resource.  The tags of the target resource of the request are evaluated.  For example, we may want to write a policy that only allows an IAM principal to delete resources that have specific tags on them.  In this case, `aws:ResouceTag/tag-key` would be the condition we want to use.

#### Methodology 

We programmatically scanned through the Service Authorization pages of AWS IAM ([Actions, resources, and condition keys for AWS services](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html)) and looked for at resource tables and pulled resource types that support `aws:ResourceTag/tag-key`.

`aws:ResourceTag/tag-key` ->  Supported Resources

#### When to Use

Use this condition key when ensuring that an action is only permitted on resources with a certain tag.  For example, only allowing an IAM principal permission to stop ec2 instances with a specific tag.


### Resources with support for aws:TagKeys 

File: [Resources with support for aws:TagKeys](resources_with_tag_keys_support.json) \
json structure: {service, resource, arn}

#### Explanation

**aws:TagKeys** is a property of the request and not necessarily a property of the resouce in question.  An example of this is when creating a resource, `aws:TagKeys` can be used to limit which tags can be used when creating a resource.  

Note: We have seen inconsistencies for whether this is supported in certain AWS IAM Actions.  In some cases, `aws:TagKeys` is listed in the condition keys table on a service authorization page but is not present in the IAM Actions table.

#### Methodology 

We programmatically scanned through the Service Authorization pages of AWS IAM ([Actions, resources, and condition keys for AWS services](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html)) and looked for at resource tables and pulled resource types that support `aws:TagKeys`.

`aws:TagKeys` -> Supported Resources

#### When to use

Use this condition key when tags are required.  For example, ensuring that required tags are present when tagging a resource.  Note, this does not check to see what the tag key value may be.  To check for the tag key value in a request, we recommend using `aws:RequestTag/tag-key`.


### References

[AWS IAM: AWS Global Condition Context Keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html)
