---
tags:
  - CS
  - Lecture
---
---
# Containerisation
Motivation - system level virtuilisatino is to over head heavy, large images and boot times
idea - use the kernal but isolate apps and where they interact
- file system
- devices
- network
- ...

### Before docker
Unix v7 chroot system call (1979)
- would allow system root to be set for processes
- philosophy almost everythin accessed by file system -> almost everything virtualized through chroot
Wave of container technologies in early 2000s
- freebsd, linux VServer,  solaris zone
- different degree of isolation (containerisation)
- mostly linux
- not popular mainly used by prof and sys admins in large companies

List of some tools:
- LXC
- Docker
- rocket
- lxd
- ubuntu snap

### Linux kernel features
chroot
- oldest mechanism for containerisation
- system call that changes the root directory
- sys calls, networking ect ramain unchanged

this shows two "systems" with one nested inside the other, with use of chroot you can change to the container-root system
![[chroot.png]]

**Namespace**
gives a method to group processes and their allowed kernel resources

**cgroups**
allow definition of resource and constraints for processes
used to limit CPU, RAM, network and disk usage for containers

**security policies**
SELinux, appArmor
- optional modules for sec
- allow rule-based restrictions of processes for file and device access
- SELinux is complex but powerful in rule def
- apparmor is a simpler profile

### LXC
library and userspace scripts to access kernel process isoltion features
no daemon, instead containers are viewable at /var/lib/lxc

**Creation**
1. create director at /var/lib/lxc
2. template script executed to populate file system of the container
3. process is spawned and chrooted in file system
4. process isolation is configured
5. main app process is spawned
6. lxc does not rely on image format
7. not much infastructure for sharing images

### Docker
Most popular container tech atm
includes:
- daemon and user space tools for managing local images
- hierarchical image format
- build tool for images .DOCKERFILE
- private and public repos for sharing (Dockerhub)
 
![[Docker-architecture.png]]

**Docker instances**
container instance is a running process started from an image
docker image is a snapshot of a container packaging the app it dependencies and configs
dockerfile instructions for creating images

**dockerfiles**
automatic creation of container images
set of commands that modify files or change config
intermediate steps can be cached resulting in reduced image build times

**docker images**
contain:
- list of layers
- ID
- config data, ports mounts env etc
- meta data
Each image layer contains:
- ID of the laye
- layerfiles (tarball)
- command that was used to create layer

dockerfile example
![[dockerfile.png]]

### Containers vs VMs
