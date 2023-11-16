Version: policy language version
Id: id for policy 
Statement: one or more individual statements
	- consists of
		- SID: statement id
		- Effect: whether statement allows or denies access
		- Principal: account/user/role to which the policy applied to
		- Action: list of actions this policy allows or denies
		- Resource: list of resources the actions are applied to
		- Condition: conditions for when this policy is in effect