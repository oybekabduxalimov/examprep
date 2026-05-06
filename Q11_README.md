# Q11 — Memory Layout of Running Program, Memory Read/Write Transactions

## Lecture goal
Understand process memory regions and how CPU performs memory operations.

---

## 1) Process Address Space Regions
- Text/code segment
- Data and BSS
- Heap
- Stack

## 2) Region Roles
- Code is executable and usually read-only.
- Heap holds dynamically allocated objects.
- Stack holds call frames and local context.

## 3) Runtime Access Behavior
- CPU reads/writes through load/store operations.
- Memory transactions occur at bus/cache line granularity.

## 4) Alignment and Efficiency
- Aligned accesses are generally faster.
- Misaligned/split accesses can increase transaction cost.

## 5) Practical Debugging Relevance
- Segmentation faults, buffer overruns, and leaks are region-related.
- Understanding layout helps reason about crash causes.

## What to emphasize when speaking
1. Memory layout is functional, not just conceptual.
2. Access patterns interact with hardware transaction behavior.
3. Segment understanding helps diagnose low-level bugs.

## Short speaking script (about 1 minute)
This lecture maps a running process into code, data, heap, and stack regions.  
Each region has a specific runtime purpose and access pattern.  
CPU memory operations are not abstract; they become hardware transactions affected by alignment and locality.  
That is why layout knowledge is valuable for both debugging and optimization.
