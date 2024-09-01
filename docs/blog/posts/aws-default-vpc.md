---
# draft: true
date: 2023-07-19
authors:
  - mnye
categories:
  - Cloud Security
  - AWS
  - Virtual Networks
---

# AWS Virtual Networking Default Settings



<!-- more -->
## Default VPCs



## Default Security Groups



# Deleting the Default VPC and Default Subnets

This bash shell script is configured to delete the default VPCs and associated resources across all enabled regions on your account.  Can be particularly useful when creating a new AWS account to eliminate insecure default configurations in your environment.

## Resources Removed

The following resource objects attached to the default VPC, in addition to the VPC itself, are removed in all enabled regions:
- DHCP Options
- Internet Gateway
- Subnets
- Security Groups
- Network ACLs
- Route Table
- Default VPC

## Dependencies

- `awscliv2` installed and configured with a default profile
- `jq` (for parsing JSON output from AWS CLI commands)


## References
https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html
