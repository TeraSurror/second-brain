## Foundations
---
Building blocks of a data-intensive application:
1. Data storage - Databases
2. Remember the results of expensive operations - Caches
3. Search data by keyword - search indexes
4. Send a message to another process, handled aync  - stream processing
5. Periodically crunch a large amount of accumulated data - batch processing

Important concerns in a software system:
1. Reliability: System should continue correctly even in the face of adversity
2. Scalability: As system grows, there should be reasonable ways to dealing with that growth.
3. Maintainability


### Reliability
Fault - Things that can go wrong
A reliable system reduces faults as much as possible
Types:
1. Hardware faults
	- Hard disk crash, RAM becomes faulty, the power grid has a blackout
	- First response is to add redundancy so that if one system fails, the backup can act as replacement
	- This is not sufficient anymore as data demands have increases considerably
	- So, software fault tolerant techniques are used in addition to redundancy
2. Software faults
	- Software bugs, process using up some shared resource like CPU, memory, etc
	- No quick solution. Try to prevent as much as possible 
3. Human faults
	- Configuration errors are the leading cause of outages
	- Ways to reduce human errors
		- Design systems in a way that minimizes opportunities for error
		- Decouple the places where people make the most mistakes from the places where they can cause failures
		- Test thoroughly at all levels
		- allow quick and easy recovery from human errors (eg. fast rollback)
		- set up detailed and clear monitoring
		- implement good management practices

### Scalability
It describes a system's ability to cope with increased load.
We need to describe these things to provision for scalability
1. Load
2. Performance

Approaches for dealing with Load:
- **Keep your database in a single node, until you cannot**
- Use an elastic approach (scale out and scale up as needed) for stateless applications

### Maintainability
Majority of the cost of development of the application are in maintenance
Even the software lifecycle is mostly maintenance.
Design principles for software systems:
1. Operability: make it easy for operations teams to keep the system running smoothly
2. Simplicity: make it easy for new engineers to understand the system
3. Evolvability: make it easy for engineers to make changes to the system in the future


## Data Models and Query Languages
---
