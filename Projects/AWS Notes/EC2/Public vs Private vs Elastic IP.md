By default, an EC2 instance comes with the following:
1. a private IP for the AWS network
2. a public IP for the web

While SSHing, we use the public IP of the instance to connect.

The public IP can change if the instance is stopped and restarted
#### Public IPs:
1. Machine can be accessed on the internet
2. must be unique across the whole world
3. can be geo-located easily

#### Private IPs:
1. Machine can be identified only in a private network.
2. IP must be unique across private networks. (2 diff private networks can have machines with the same private IP)
3. machines connect to WWW using a network proxy
4. only specified range of IPs can be used

#### Elastic IPs:
1. These are used when we want our EC2 instance to have a fixed IP address.
2. They exist as long as the instance is not deleted.
3. We can transfer these IPs between instances.
4. **AVOID USING THEM**
