# Q17 - Processes, Threads, Race Conditions, Background Jobs

## 1) Process abstraction
- A process is an instance of a running program.
- Each process has its own logical control flow.
- Each process appears to own a private virtual address space.
- The OS preserves this illusion with scheduling and virtual memory.
- A program file on disk is not the same thing as a running process.

## 2) Concurrency and context switching
- Concurrent processes overlap in time even on one CPU.
- The kernel switches execution from one process to another through context switches.
- A context switch saves one process state and restores another.
- The kernel is shared OS code, not a separate user process.
- Interleaving creates the user-visible illusion of simultaneous progress.

## 3) Creating and managing processes
- `fork` creates a new child process by duplicating the parent process state.
- The child receives `0` from `fork`, while the parent receives the child PID.
- `execve` replaces the current process image with a new program.
- `wait` and `waitpid` reap terminated children and collect exit status.
- Failure to reap children leaves zombie processes behind.

## 4) Threads inside a process
- A process can contain multiple threads.
- Threads share code, global data, heap, and many kernel resources.
- Each thread still has its own registers, stack, and logical control flow.
- Threads are usually cheaper to create and switch than processes.
- Shared address space makes communication easy but also dangerous.

## 5) Race conditions and shared state
- A race occurs when the result depends on scheduling order.
- Unsynchronized access to shared data can corrupt state.
- Critical sections are code regions that must not overlap unsafely.
- Correctness should not depend on a lucky interleaving.
- Races are correctness bugs even when they appear only rarely.

## 6) Synchronization primitives
- A mutex enforces mutual exclusion so only one thread owns a resource at a time.
- A semaphore allows a fixed number of threads to enter a protected region or use a shared resource.
- A critical section is a fast locking mechanism for threads inside the same process.
- An event lets one thread signal another that some condition or task completion has occurred.
- These primitives exist because shared memory without synchronization leads directly to race conditions.

## 7) Process-based versus thread-based concurrency
- Processes isolate state better and reduce accidental sharing.
- Threads share state directly and make data exchange easier.
- Process-based designs often need IPC for sharing.
- Thread-based designs reduce overhead but increase synchronization risk.
- The choice is a tradeoff among isolation, efficiency, and complexity.

## 8) Background jobs and lifecycle control
- A background job keeps running without occupying the interactive foreground.
- Parent and child process relationships still matter after a background launch.
- Shells and servers must manage termination, cleanup, and status collection.
- Detached execution changes how resources are reclaimed and observed.
- Background work still depends on correct scheduling, reaping, and resource ownership.
