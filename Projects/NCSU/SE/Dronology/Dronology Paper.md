### Towards a Model-Integrated Runtime Monitoring Infrastructure for Cyber-Physical Systems

Cyber-Physical systems (CPS) -> automated vehicles, UAVs, factory floor robots, etc

Problem: Monitoring CPS is difficult

Solution (acc to authors): Model-Driven Engineering paradigm (MDE)

MDE: Changes are applied to the model and system code is generated automatically

#### Approach

1. Monitoring Meta-Model and Domain Model
2. collecting events and data from the monitored system
3. data aggregation and distribution
4. runtime monitoring infrastructure with support for constraint evaluation


My questions:
what is a model and a system? -> model is like a UML model of the system (Drone, car, etc)
how is monitoring simplifies? -> automatically generates code for constraint management (monitoring API)

Model-Driven Engineering (MDE) is ==a software development methodology that involves creating and using domain models==. Domain models are conceptual models that describe topics related to a specific problem.

Summary: Create Model which creates a monitoring system (API in this case).