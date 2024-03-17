These are fundamental for network security in EC2 instances
They control how traffic is allowed in and out of our EC2 instances

Features security group rules:
- They only contain **allow** rules
- They can be referenced by IP or security group

They are like **firewalls** for our instances

Good to know:
1. Can be attached to multiple instances
2. Locked down to a region/VPC combination
3. Lives "outside" the EC2. Instance in not aware of traffic issues
4. **It is good to maintain a separate group for SSH access**
5. If application is accessible (time out) - Security Group issue.
6. If application is showing "connection refused" - application error (most likely not launced)
7. All inbound traffic is blocked by default
8. All outbound traffic is authorized by default

Ports to know:
1. 22 - SSH - log into a linux shell
2. 21 - FTP - upload file into a file share
3. 22 - SFTP - upload files using SSH
4. 80 - HTTP - access unsecured websites
5. 443 - HTTPS - access secured websites
6. 3389 - RPD (Remote Desktop Protocol) - log into a windows instance