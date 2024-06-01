Link: https://www.youtube.com/watch?v=-W9F__D3oY4

### Vertical Scaling
- Upgrade resources of the machine (more RAM, CPU, etc).
- Throw money at the problem.
Limitations:
- Upper limit to how much a single machine can be upgraded.
- Resources may not be needed
### Horizontal Scaling
- use multiple cheap hardware.
- multiple machine handle the load, instead of one.
Limitations:
- manage multiple machines.

### Load Balancing
- acts as a front-end to the servers.
- routes the requests from the client to the servers as needed.
#### Methods for Load Balancing:
1. Round Robin
	- Route to 1st, 2nd, 3rd and so on.
	- Simple to implement.
	- Can lead to disproportionate distribution of load on servers.
2.  Distribute according to load
	- Check which server is under the least load and send the request to that.
	- Caching and Stateful processes would be disrupted as different servers may have different data.
#### Tech for LB
Software:
1. Elastic Load Balancer AWS
2. HAProxy (High Availability Proxy)
3. Linux Virtual Server
Hardware:
1. Cisco
2. Barracuda


