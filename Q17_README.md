# Q17 — Processes, Threads, Race Conditions, Background Jobs

## Lecture goal
Understand execution units in operating systems and concurrency hazards.

---

## 1) Process vs Thread
- Process: isolated address space and resources.
- Thread: execution stream inside a process.

## 2) Concurrency Basics
- Multiple threads may interleave or run in parallel.
- Shared memory enables communication and risk.

## 3) Race Conditions
- Result depends on timing/interleaving.
- Unsynchronized shared updates can corrupt state.

## 4) Coordination Needs
- Critical sections require synchronization.
- Correctness must be independent of scheduling order.

## 5) Background Jobs
- Process control concepts for non-foreground execution.
- Lifecycle and scheduling implications.

## What to emphasize when speaking
1. Threads are lighter than processes but share riskier state.
2. Race conditions are correctness, not just performance, problems.
3. Background execution still needs resource/lifecycle management.

## Short speaking script (about 1 minute)
This lecture introduces processes and threads as core OS execution models.  
Threads improve responsiveness and throughput but share memory, which creates race conditions if synchronization is missing.  
Background jobs extend these ideas into practical process management.  
The key takeaway is balancing concurrency benefits with correctness discipline.

