# Q14 — Memory Hierarchy: HDD and SSD

## Lecture goal
Compare HDD and SSD technologies and their performance/engineering tradeoffs.

---

## 1) HDD Basics
- Mechanical storage: platters + moving head.
- Access includes seek time + rotational latency.

## 2) SSD Basics
- Flash-based, no moving parts.
- Faster random access and lower latency.

## 3) Access Pattern Effects
- Sequential vs random I/O behavior differs strongly.
- SSD generally dominates random workloads.

## 4) Flash Management
- Erase-before-write constraints.
- Wear leveling and garbage collection.
- Endurance considerations.

## 5) System-Level Choice
- HDD: cheaper per GB for bulk storage.
- SSD: better responsiveness/performance-sensitive paths.

## What to emphasize when speaking
1. Mechanical vs solid-state design explains speed gap.
2. Performance depends on workload pattern.
3. SSD controller logic is key to durability/performance.

## Short speaking script (about 1 minute)
This lecture compares HDD and SSD in terms of internal mechanics and practical performance.  
HDD latency is dominated by physical movement, while SSD avoids that with flash memory.  
SSD gives strong random I/O performance but has erase/write and endurance constraints handled by controller algorithms.  
System design decisions depend on cost, capacity, and workload profile.

