# Q23 - Virtual Machines

## 1) Why virtualization is used
- Virtualization consolidates multiple workloads onto one machine.
- It improves isolation across performance, security, and configuration.
- It makes provisioning and recovery easier.
- It is a foundation for cloud multi-tenancy.
- The main tradeoff is some extra management and execution overhead for much greater flexibility.

## 2) What a virtual machine represents
- A virtual machine is a software implementation of a machine interface.
- The interface is largely defined by the ISA and related privileged behavior.
- Guest software believes it is running on its own hardware.
- The hypervisor or VMM is the real control layer underneath.
- Virtualization is therefore about reproducing a hardware contract convincingly enough to run existing software.

## 3) Hypervisor role and privilege
- The hypervisor controls the most privileged execution environment.
- Guest operating systems run with restricted authority relative to the VMM.
- Older approaches used privilege rings creatively to contain the guest.
- Modern CPUs support hardware-assisted virtualization modes.
- Sensitive guest operations can trigger VM exits back to the host.

## 4) Virtualization approaches
- Full virtualization runs unmodified guest operating systems.
- Paravirtualization changes the guest interface to simplify or speed up virtualization.
- Binary translation can rewrite sensitive guest instructions on the fly.
- Direct execution lets ordinary non-privileged guest instructions run at near-native speed.
- Hardware virtualization support reduces the amount of software emulation needed.

## 5) Virtual CPU and memory
- A virtual CPU has its own register state and program counter image.
- The hypervisor schedules virtual CPUs onto real CPUs.
- Guest memory addresses are mediated so the guest stays within its assigned RAM.
- Shadow page tables or hardware-assisted nested translation can be used for this.
- Memory virtualization is one of the key mechanisms that enforces guest isolation.

## 6) Device and I/O virtualization
- Guests interact with virtual devices rather than raw physical devices directly.
- The hypervisor or a helper process emulates the expected device behavior.
- I/O requests from the guest are translated into host-side operations.
- Device emulation prevents buggy guest drivers from directly damaging the host environment.
- Virtual hardware also improves portability across different real machines.

## 7) Practical tradeoffs
- Virtual machines improve portability, consolidation, and isolation.
- They add overhead in CPU control, memory translation, and device emulation.
- Hardware support narrows that overhead significantly for common paths.
- Different workloads benefit differently from full emulation, hardware assistance, or paravirtualization.
- Virtualization remains central because the management and isolation gains are often worth the cost.
