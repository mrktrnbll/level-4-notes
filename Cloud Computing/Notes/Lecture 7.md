---
tags:
  - CS
  - Lecture
---
---
# Recap
Monolithic design
A single tight couple of code.
- scaling hard - vertical only allowed
- limited agility, risky deployment due to large codebase
- tech lock in - difficult to adopt new tech and frameworks
- complex - become hard to maintain

Layering design
Lower layers provide abstracted interface and service for layers above.
OS is a good example, OS integrates with hardware - it give an API for softwares to interact without knowing exactly what happens on hardware level.


Web apps use **teiring**, UI, processing/business logic and then database for persistent states.
Advantages - abstraction, reusability and lose coupling

![[fat-thin-client.png]]
left shows thin client, right shows fat client web applications.

### Load Balancing
User make requests to a auto scaling listener that tracks service instance loads. If overloaded in requests scale out feature

To do this it needs to ask where the bottleneck is and if the component is stateless or stateful.

**Stateless load balancing**
Primarily done at the application level
- 

**Stateful load balancing**
Partition by tenant - put different tenants on different machines
- isolation is 1 a requirement in cloud
- no network traffic between machines - good scalability

Partition Schemes - 