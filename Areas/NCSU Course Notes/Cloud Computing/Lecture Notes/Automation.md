Limitations of traditional infra deplyment:
1. manual and time consuming
2. error prone 
3. inconsistent
4. cofiguration

**Infrastructure as service:**
1. this means the actual services

Problems with infra maintenance:
1. most problems are caused by changes in infra
2. infra is not limited to servers - other things have to be taken into consideration
3. trying to fix a broken server is a painful process


### **Infra as code**:

1. the way we provision and manage the resources
2. refer to slides for definition. TLDR; the YAML files for the kubernetes or jenkins and so on

**IAC with Terraform:**
1. declarative language
2. cloud agnostic
3. large list of providers available
4. source control with git or terraform cloud
5. role based access control workspaces
6. policy as code (approve and reject automation)

**Approaches for IAC:**
1. Declarative approach  - focus on the end goal
2. Imperative approach - focus on the steps

**IaC best practices:**
1. Idempotence
2. version control
3. testing
4. graceful rollbacks

Tools:
1. tools that are responsible for connecting the software and the hardware
2. languages for implementing IaC
4. most tools are open source
5. Examples:
	1. Terraform
	2. Ansible
	3. Salt
	4. Puppet


Deployment strategies:
1. Basic deployment - all nodes within a target environment are updated with the service at the same time
2. Multi-service deployment - all nodes are updated with multiple new services simultaneously
3. Blue / Green deployment - one group with old version and the one group with a new version. staging and prod environments are involved
4. 

