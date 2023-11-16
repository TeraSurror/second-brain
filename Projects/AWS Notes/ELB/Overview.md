- Elastic Load Balancer is a managed load balancer provided by AWS. 
- AWS deals with all the issues and the maintenance.

Types of Load Balancers provided by Amazon:
- Classic Load Balancer -> Supports HTTP(S), TCP, SSL
- Application Load Balancer -> Supports HTTP(S), Web Socket
- Network Load Balancer -> Supports TCP, UDP, TLS
- Gateway Load Balancer -> Operates at Layer 3

Note on Security Groups for LB
- For the LB, the security group can be 0.0.0.0/0 (accept requests from anywhere)
- For the EC2 instance behind the LB, the security group should be - only accept requests from the Load Balancer