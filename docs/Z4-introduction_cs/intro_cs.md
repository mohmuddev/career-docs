---
sidebar_position: 1
---
# Virtual Private Cloud

## VPC Components

**VPC** is big address based and can be split into smaller addresses which is called **subnet**.

VPC has **Route Table** which takes routing decision, how the traffic go in and out of the VPC. The routing table has roles which decides whether your machine can access through internet or private.

VPC has two level of **firewalls**; 
1. Instance level which is called **Security group**.  
2. subnet level which is called **ACL firewall**

**Internet Gateway** connects internet to the VPC so that anyone can connect machine in the VPC publicly.

**Virtual Private Gateway** allows VPN connection between AWS VPC and premises data-center

**NAT Gateway** is a highly available AWS managed service that makes it easy to connect to the Internet from instances within a private subnet in an Amazon Virtual Private Cloud (Amazon VPC).

## Network Addressing
- Classes IP addressing
- Classless IP Addressing

Basically IPv4 address has 32bit e.g 255.255.255.255

```text title="IP Classes"
┌────────┬──────────┬──────────────────┐
│ Class  │ Range    │ Network Address  │
├────────┼──────────┼──────────────────┤
│ A      │ 0-126    │ XX               │
├────────┼──────────┼──────────────────┤
│ B      │ 128-191  │ XXX.XXX          │
├────────┼──────────┼──────────────────┤
│ C      │ 192-223  │ XXX.XXX.XXX      │
└────────┴──────────┴──────────────────┘
```
**Class A** first bit asign to network addresss

 32 - 8 = 24 hence  Class A is 2 power 24 which is **16777216**

**Class B** first 2 bit asign to network addresss

32 - 16 = 16 hence Class B is 2 power 16 which is **65536**

**Class C** first 3 bit asign to network addresss

32 - 24 = 8 hence Class B is 2 power 8 which is **256**


**CIDR (Classless Inter-Domain Routing)**


```text title="CIDR"
Calculate total host: 10.10.0.0/16
                      32-16 = 16
                      2^16  = 65536
Total host          : 65536

First Address       : 10.10.0.0
Last Addresss       : 10.10.255.255
Total Subnets       : 256
Number of hosts each: 256
Total hosts         : 256 x 256 = 65536

CIDR Notation subnet: subnet = 256 host
                      256 = 2^8
                      32 - 8 = 24
                      10.10.0.0/24
```
 
 ## Rules and guidlines of CIDR
 - CIDR block can be between /16 and /28
 - CIDR block can not be overlap with any existing CIDR block that is associated with the VPC
 - You can increase or decrease the size of an existing CIDR block
 - The first four IP addresses and the last IP address in each subnet CIDR block are not available for your use, and they cannot be assigned to a resource, such as an EC2 instance. For example, in a subnet with CIDR block 10.0.0.0/24, the following five IP addresses are reserved:

    10.0.0.0: Network address.

    10.0.0.1: Reserved by AWS for the VPC router.

    10.0.0.2: Reserved by AWS. The IP address of the DNS server is the base of the VPC network range plus two. For VPCs with multiple CIDR blocks, the IP address of the DNS server is located in the primary CIDR. AWS also reserve the base of each subnet range plus two for all CIDR blocks in the VPC. 

    10.0.0.3: Reserved by AWS for future use.

    10.0.0.255: Network broadcast address. We do not support broadcast in a VPC, therefore we reserve this address.



