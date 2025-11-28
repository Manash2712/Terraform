### Solution

```
resource "aws_vpc" "datacenter-vpc" {
  cidr_block       = "192.168.0.0/24"
  instance_tenancy = "default"

  tags = {
    Name = "datacenter-vpc"
  }
}
```

#### Note:
Instance tenancy in an AWS Virtual Private Cloud (VPC) determines how your Amazon EC2 instances are provisioned on the underlying physical hardware. There are two primary tenancy options:
- Shared Tenancy (Default):
  - This is the standard and most common tenancy model.
  - Your EC2 instances may share physical hardware with instances from other AWS accounts.
  - While the instances share hardware, they are isolated from each other at the hypervisor level, ensuring logical separation and security.
  - This is generally the most cost-effective option.
- Dedicated Tenancy:
  - Dedicated Instances: Your EC2 instances run on hardware that is dedicated to a single AWS account. This means your instances will not share physical hardware with instances from other AWS accounts. However, they may share hardware with other instances from your own AWS account that are not themselves Dedicated Instances. 
  - Dedicated Hosts: This provides an even higher level of isolation. You provision an entire physical server for your exclusive use. This gives you more control over instance placement and visibility into the underlying hardware, which can be important for certain licensing requirements or compliance regulations.
- Choosing the right tenancy:
  - Shared tenancy is suitable for most general-purpose workloads where cost-effectiveness and scalability are primary concerns, and where logical isolation at the hypervisor level is sufficient.
  - Dedicated tenancy (either Dedicated Instances or Dedicated Hosts) is chosen when specific compliance requirements, licensing models, or security policies necessitate physical isolation of your instances from other AWS customers.
