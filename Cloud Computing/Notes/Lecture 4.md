---
tags:
  - CS
  - Lecture
---
---
# Cloud Infrastructure Managements
### Baremetal Servers
Running components of an app on one or more physcical servers
Static resource assignment even though we will have dynamically changing loads from users

### Cloud Based
This comes with the boost of dynamic resource allocation however... This leads with to management debt!
- Sprawl - creation of virtual resource because its easy leading to more than necessary virtualisation without management
- configuration drift - change of configs that lack documentation
- snowflake servers - similar to above because configs are unique! makes sense cause snowflakes.
Overall it brings tech debt to manage

### Cloud OS
Cloud operating systems - openStack and OpenNebula are open source os for cloud systems.
They manage large pools of physical resources and **provide**:
- Dashboard and APIS for admins and users to use that abstract the infrastructure itself
Basic functions:
- spawning and maintaining vms
- virtual networks
- managing images and virtual disks
Advanced functions:
- orchestration - what is this...
- load balancing
- and auto scaling

Managing the infastructer:
![[Infrastructure Encapsulation.png]]
This encapsulates certain machines and controllers in specific hardware groups.

### Nova
Allows creation of vm on demand from images
Schedules VM to run on physical nodes
defines drivers with underlying virtual mechanisms

### Glance
Registry of virtual disks
users can add new images or snapshots of existing vms
snapshots can be templates for new servers

### Cinder
Provides network-backed virtual block storage
enable live migration of vms

### Neutron
provides api for networking vm and physcial network

interconnects vms
- within one hypervisor
- between several hypervisors
- with the internet

Provides additional network functions
- firewalls
- vpn
- public api

### Virtual switches and SDN
virutal switching enables network automation through programmatic extension and standard protocols

software defined networking 
- simplifing network admistration
- seperation of control plane and data plane
- allow on fly config of switches
![[VirtualNetworking.png]]
VM Snapshots
- point in time copy of vm memory and disk state.
- useful for roll-back or migration

Suspending vs pausing
suspending:
- full vm state is written to disk - only disk and networking
Pausing:
- cpu activity is halted, vm state is still in memory

Suspending resuming is longer than pausing as the disk needs to be pulled back to memory but it is cheaper that pausing

### Live migration
Push
Stop-and-copy
Pull

What is used in industry? - a mixture
XEN uses a mix of push and stop-and-copy
Iterative approach of push followed by short stop and copy
VMware solutions even slow down CPU to ensure network transfer


### Problems Motivation
Manual config of server usally lead to:
- config drift - config servers changes without documentation over time
- leads to snowflake servers...
	- have unique configs
	- are not reproducible when hardware dies - when migrating we cant perfectly replicate the production env
	- hard to mirror and test

How to keep a cluster servers consistent?

Disk snapshots allow to recover or mirror servers but
- still not easy to understand state of server

### Infrastructure as Code
Goal: make system easy to reproduce support test and aid understand configurations.

Solution: One single source of truth, with clear declarative config.
- can be executed
- versioned
- shared

Only use these definitions, never mutate a single server with manual commands.
Using source code to change
- config enviroments
- despendencies with specific version

### Ansible
Automation language and engine
Orchestration
- allocate and provision new servers

Well documented, conventions and best practices

Multiplatform
- OS
- Orchestration tools: LXC, libvirt, VMware
- IaaS services: AWS, Azure

Technologies as foundation:
- python
- ssh
- yaml jinja

**Ansible Tasks**
Declarative
- define the desired state
Implies idempotency (reproducibility)
- applying same config again leads to same state - no config drift

**Playbooks**
Playbook are execution units for ansible and map everything to host:
- Tasks
- roles
- variables
hosts is a key word that allows you to map urls to names/tags using yaml
```
all: 
	hosts: 
		mail.example.com: 
	children: 
		webservers: 
			hosts: 
				w1.example.com:
			    w2.example.com: 
		dbservers: 
			hosts:
				d1.example.com:
				d2.example.com
```

### DevOps - CI/CD
don't need overview

