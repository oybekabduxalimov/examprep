# Q21 — Concurrent Programming

## Lecture goal
Understand how to design correct programs with multiple concurrent execution paths.

---

## 1) Why Concurrency
- Improve responsiveness.
- Increase throughput on multi-core systems.

## 2) Shared-State Risks
- Unsynchronized shared data causes races.
- Operation ordering and visibility matter.

## 3) Synchronization Primitives
- Mutexes, semaphores, condition variables.
- Atomic operations for low-level coordination.

## 4) Liveness Problems
- Deadlock, starvation, livelock.
- Correct design must ensure progress as well as correctness.

## 5) Debugging Difficulty
- Nondeterminism makes bugs intermittent and hard to reproduce.

## What to emphasize when speaking
1. Concurrency needs explicit synchronization strategy.
2. Safety and liveness are separate requirements.
3. Testing concurrent code requires stress and scenario variation.

## Short speaking script (about 1 minute)
This lecture covers programming with concurrent execution and shared resources.  
Without synchronization, race conditions break correctness, so primitives like mutexes and atomics are essential.  
Beyond correctness, programs must avoid deadlock and starvation to guarantee progress.  
Concurrency is powerful but requires careful design and testing discipline.

