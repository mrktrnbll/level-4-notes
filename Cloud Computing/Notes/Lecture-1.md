---
tags:
  - Lecture
  - CS
---
---
### Intro
Lauritz and Yehia - NOSE and Systems guys
25% cloud deployment exercise and 25% Cloud systems design 50% exam

---
### Cloud computing intro

### Cluster
Homogenous computing resources used to share compute power
example given at socs was lauritz lab has 22 nodes that have 2 cpus per node shared between a few other research groups. If the group hadn't used clustering then they couldnt access as much power at a given instance.

---
### Grid
hetrogeneous compute resources, connect via slow network.
examples of this are cern hadron colidor thing, you offer compute power via a middleware software

---
### Clouds
definition by NIST (National Institution of Standard and tech) *a commercial infastructure built on top of a cluster* it is based via user 

### Edge
instead of centralised cloud system being called to for decision making by sensors; cars, IoT devices, smart home devices is non edge distributed systems
edge would be when the sensors themselves talk amonst themselves without ofloauding to a large system for decision making
Fog is an intermediate phase
![[Fog-Computing.png]]
---
# Characterstics and services of Cloud
### Characteristics
- On demand self service
- Broad access network access (over internet)
- Resource pooling (shared by users)
- Rapidly elastic
- Measured service
Services
- SaaS (Software as service)
- IaaS (infastructure as service)
- PaaS (Platform as service)


---
# Challenges
Rapid provisoning
Elasticity - infinite resources and cost-effiecient
Isolation of differnt consumer - privacy and security
Performance

# Virtualisation
The solution was **VIRTUALISATION**

Cloud providers give IaaS - allowing users to buy virtualisation of storage, cpu, gpu memory, networking
Virtulisation takes a real system and creates 1 or more virtual systems
formal definition shown:
![[Guest-Host-Process.png]]

V maps the state of guest to the state of host
e maps a state of guest to new state of guest, this has a complementary mpaping of host state to new host state

### Categories
- System
	- hardware assisted (KVM, Hyper-V microsoft) - dont know they run on virtual machine
	- OS-Assisted (XEN, Denali) - aware of virtualisation
	- Full Virtulisation (VMware, virtualbox) - allows running x64 OS on x64 chip
	- Emulation (QEMU (is this a switch one or is it cemu???)) allows running different architecture OS to system archecture, x64 to x82 or whatever
- os level
	- sits at a mix of OS level (docker or some type of container)
- process level
	- used at application level (JVM, .NET)


# VM and Containers
### Virtual Machines
Use case:
- Run different OS from the host machines OS
- Different enviroments - you have family PC that you want to keep profiles completely seperate

### Containers
light os level virtualisation -> a vm but for single applications

Use cases
- Build and ship application 
- have many apps share the resource of a cluster

### Versus
containers:
- containers can only run and build for the host OS
- single app in pre-build enviroment
- reduced isolation
- Live migration is less mature
VMs:
- 