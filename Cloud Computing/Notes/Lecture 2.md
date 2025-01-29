---
tags:
  - CS
  - Lecture
---
---
# Virtual Machines

### Basic Designs
![[Type1-vs-Type2.png]]
Left - Type 1
Right - Type 2
main difference is where the VMM (Virtual Machine Manager) is reciding
### Type 1
more efficient
requires specific drivers for devices
### Type 2
no special drivers
more overhead

### Fundamental problem
- VMM must have ultimate control and secure - should not allow guest OS to have access to hardware
- guest OS must have percieved autonomy

### recap: instructions
* Privileged instructions
	* only executed by system mode
	* trap when processor is in user mode
	 Examples
		 - Load PSQ
			 - one bit to indicate system mode
			 - maliticous program could modify this bit
		 - Set CPU timer
			 - defines when the program lose cpu privelge

**privileged instructions should not be user program definable**
- Sensitive instruction
	- control sensitive - change config of resource 
	- behaviour sensitive - behaves different depending on resource config
examples:
- Load Real Address - control sensitive
- Pop stack in flag address - beahviour (both?)

**Popek and Goldbergs**
construction of efficient VMM 
![[Privilages.png]]

### Implication of Popek and Goldbergs
**All unprivileged processes run native on user mode**

**if guest os calls** **sensitive instruction**
- instruction traps
- VMM emulates instruction operation

According to this spec Arm and intel AI-32 are not virtualisable
**BUT THEY ARE! THE CLOUD USE DISTRIBUTION SAYS SO**
The 3 ways to do this are described below
### Binary Translation



# OS-Assisted Virtualization
make guest os aware its running in VM
this means source code of OS be changes

most vm are aware of running on VM for IO management

# XEN
![[XEN-architecture.png]]
Dom U shows any vm
Dom 0 shows privelleged guest for control/management

**CPU virtualisation**
- Critical instructions do not trap IA-32
	- guest os is aware of vm so avoids critical calls
- frequent vmm intervention needed for system call and page table update
	- some calls moved to ring 1
	- command batch?
	- mapping hypervisor code into process address spaces
- 