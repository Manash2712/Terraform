### Solution

```
    resource "aws_vpc" "xfusion_vpc" {
      cidr_block           = "10.0.0.0/16"
       assign_generated_ipv6_cidr_block = true 

      tags = {
        Name = "xfusion-vpc"
      }
    }
```

#### Argument Reference
- cidr_block - (Optional) The IPv4 CIDR block for the VPC. CIDR can be explicitly set or it can be derived from IPAM using ipv4_netmask_length.
- assign_generated_ipv6_cidr_block - (Optional) Requests an Amazon-provided IPv6 CIDR block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or the size of the CIDR block. Default is false. Conflicts with ipv6_ipam_pool_id
