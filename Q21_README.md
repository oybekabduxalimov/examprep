# Q21 - Concurrent Programming

## 1) Why concurrent programming is hard
- Human reasoning is naturally sequential.
- Concurrent execution introduces many possible event orderings.
- The same program can behave differently across runs with the same input.
- Nondeterminism makes bugs intermittent and hard to reproduce.
- Correctness has to hold across all legal interleavings, not just the common one.

## 2) Common concurrency failure classes
- Races occur when results depend on scheduling order.
- Deadlock prevents forward progress because resources are held in a circular wait pattern.
- Starvation prevents some work from making progress.
- Livelock keeps threads active without useful completion.
- Fairness issues can matter even when no deadlock exists.

## 3) Main server-side concurrency models
- One process per client gives strong isolation.
- One thread per client reduces overhead and shares memory.
- I/O multiplexing lets one thread manage many flows explicitly.
- Each model trades scheduling control, sharing behavior, and implementation complexity differently.
- Choosing a model is a design decision, not just a coding detail.

## 4) Processes versus threads
- Processes do not normally share ordinary address-space data directly.
- Threads within one process share code, globals, and heap.
- Threads keep separate stacks and register states.
- Processes are heavier to create and reap.
- Threads are easier to share data with, and therefore easier to misuse.

## 5) Thread management concerns
- Threads can be joinable or detached.
- Joinable threads must be reaped explicitly.
- Detached threads release resources automatically on termination.
- Passing pointers to stack-local data across thread boundaries is risky.
- Thread-safe helper functions are required when multiple threads may call them concurrently.

## 6) Shared-state correctness
- Shared data must be protected whenever interleaving could break invariants.
- A critical section is code that must not overlap unsafely with another thread's matching section.
- Correct designs make outcomes independent of timing accidents.
- The more implicit the sharing, the harder the bugs are to spot.
- Testing alone may miss rare but real race outcomes.

## 7) Practical design tradeoffs
- Processes offer safer isolation but higher control overhead.
- Threads offer better sharing and efficiency but more synchronization risk.
- I/O multiplexing offers tighter control with less overhead but more manual state handling.
- Concurrency design affects performance, debuggability, and correctness together.
- The right model depends on workload, sharing needs, and failure tolerance.
