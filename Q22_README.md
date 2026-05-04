# Q22 — Parallelism and Synchronization

## Lecture goal
Understand performance-oriented parallel execution and synchronization overhead tradeoffs.

---

## 1) Forms of Parallelism
- Data parallelism: same operation over many elements.
- Task parallelism: different tasks run simultaneously.

## 2) Partitioning Work
- Decompose tasks to maximize independent execution.
- Balance workload to avoid idle cores.

## 3) Synchronization Costs
- Barriers, locks, and communication add overhead.
- Contention limits scalability.

## 4) Speedup Limits
- Amdahl-style constraints from serial portions.
- More threads do not guarantee linear speedup.

## 5) Practical Optimization
- Minimize shared-state contention.
- Increase computation-to-communication ratio.

## What to emphasize when speaking
1. Parallelism is about useful work distribution, not just more threads.
2. Synchronization overhead can dominate at scale.
3. Scalability analysis must include serial bottlenecks.

## Short speaking script (about 1 minute)
This lecture focuses on achieving performance through parallel execution.  
The main challenge is splitting work efficiently while controlling synchronization cost and contention.  
Speedup is bounded by serial parts and coordination overhead, so architecture and algorithm design must be co-optimized.  
Good parallel programs maximize independent work and minimize blocking.

