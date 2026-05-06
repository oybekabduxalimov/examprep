# Q22 - Parallelism and Synchronization

## 1) Critical sections and unsafe interleavings
- Parallel execution creates many possible trajectories through shared-state code.
- A critical section is a region that must be executed with mutual exclusion relative to some shared resource.
- Unsafe regions correspond to interleavings that violate correctness.
- A safe execution avoids those unsafe states.
- Synchronization exists to rule out bad trajectories, not just to pause threads.

## 2) Semaphores and mutual exclusion
- A semaphore is a non-negative synchronization variable.
- `P` decrements after waiting for availability.
- `V` increments and releases availability.
- A binary semaphore used for exclusion is often called a mutex.
- Counting semaphores can represent pools of available resources.

## 3) Synchronization costs
- Locking and unlocking add overhead.
- Contention can serialize otherwise parallel work.
- Excessive synchronization can erase the benefit of more threads.
- Good design protects only the state that truly needs coordination.
- Scalability depends on both correctness and synchronization granularity.

## 4) Parallel execution for speed
- Parallelism can reduce wall-clock time when independent work is available.
- Multi-core hardware allows truly simultaneous execution.
- Work can be partitioned into subranges, subtasks, or independent stages.
- Speedup is not automatic just because threads exist.
- The program must expose enough independent work to keep cores busy.

## 5) Amdahl's law
- The serial portion of a program limits maximum speedup.
- Even infinite acceleration of the parallel part cannot remove the serial remainder.
- Speedup therefore saturates as more workers are added.
- Measuring the fraction that is parallelizable is essential.
- Performance analysis must include both computation and coordination overhead.

## 6) Forms of parallelism
- Task parallelism runs different tasks at the same time.
- Data parallelism runs the same operation over different data elements.
- SIMD is a form of data parallel execution.
- Vector and array-style hardware exploit regular repeated operations efficiently.
- Thread-level and data-level parallelism solve different kinds of performance problems.

## 7) Hardware support and architecture view
- Out-of-order execution extracts operation-level overlap inside one core.
- Hyperthreading overlaps multiple instruction streams on shared execution resources.
- Flynn's taxonomy distinguishes `SISD`, `SIMD`, `MISD`, and `MIMD`.
- Modern systems combine multiple forms of parallelism at once.
- Synchronization strategy has to match the level of parallelism being exploited.
