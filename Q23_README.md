# Q23 — Virtual Machines

## Lecture goal
Understand virtualization fundamentals and how VMs provide isolation and flexibility.

---

## 1) Virtualization Purpose
- Consolidate workloads.
- Isolate environments.
- Improve portability and operational control.

## 2) Hypervisor Models
- Type 1 (bare-metal)
- Type 2 (hosted)
- Both abstract hardware for guest systems.

## 3) Guest vs Host Responsibilities
- Guest OS believes it owns virtual hardware.
- Hypervisor schedules and mediates real resources.

## 4) Resource Virtualization
- CPU virtualization
- Memory virtualization
- I/O virtualization

## 5) Performance and Use Cases
- Some overhead exists; modern support reduces it.
- Common in cloud, testing, sandboxing, and legacy support.

## What to emphasize when speaking
1. VMs trade a bit of overhead for strong isolation.
2. Hypervisor design influences performance and management model.
3. Virtualization is foundational for modern cloud infrastructure.

## Short speaking script (about 1 minute)
This lecture introduces virtual machines as a way to run isolated systems on shared physical hardware.  
Hypervisors provide virtualized CPU, memory, and I/O so guest OSes can run independently.  
Although virtualization adds overhead, it enables major benefits in deployment flexibility, security isolation, and cloud scalability.  
That is why VMs remain central in modern systems architecture.

