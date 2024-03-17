It is like a virtual network card for a VPC.

https://aws.amazon.com/blogs/aws/new-elastic-network-interfaces-in-the-virtual-private-cloud/

It can have the following attributes:
1. One primary IPv4 and one or more secondary IPv4 addresses
2. One public IPv4
3. One Elastic IPv4 per private IPv4
4. A MAC address
5. One or more security groups

They can be created independently and can be attached to a EC2 instance "on the fly"

Bound to a single AZ
