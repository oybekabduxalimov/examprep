# Q18 - Signals, Signal Handlers, Nonlocal Jumps

## 1) Signal basics
- A signal is a small asynchronous notification sent to a process.
- The signal number identifies the event type.
- Signals can come from the kernel or from another process.
- Typical examples include `SIGINT`, `SIGCHLD`, `SIGSEGV`, and `SIGALRM`.
- A signal carries its identity, not a large data payload.

## 2) Sending and receiving semantics
- The kernel delivers a signal by updating process signal state.
- A process receives a signal when the kernel forces it to react.
- Default reactions include terminate, stop, ignore, or continue.
- A process may also catch a signal with a custom handler.
- Signal delivery interrupts normal control flow.

## 3) Pending and blocked signals
- A signal can be pending before it is actually handled.
- A process can block selected signals temporarily.
- Blocked signals remain pending until they are unblocked.
- Standard signals are not queued by count in the basic model.
- Multiple arrivals of the same signal type can collapse into one pending instance.

## 4) Signal handlers
- A handler is a user function registered for a signal type.
- The handler runs as an extra logical control flow relative to the main program.
- After the handler returns, execution typically resumes in the interrupted flow.
- Handlers should stay small and predictable.
- Unsafe handler logic can create very subtle bugs.

## 5) Safety concerns
- Signal timing is nondeterministic relative to mainline code.
- Shared state between a handler and normal code needs careful control.
- Many library functions are not safe to call from handlers.
- Reentrancy and async-signal-safety are central concerns.
- Masking signals around critical regions can avoid handler races.

## 6) Reaping children with signals
- `SIGCHLD` notifies a parent that a child changed state.
- Because signals are not queued, one notification may represent multiple child events.
- A correct handler often loops with `waitpid(..., WNOHANG)` to reap all available children.
- Failing to do so can leave zombies behind.
- Signal behavior therefore connects directly to process lifecycle management.

## 7) Nonlocal jumps
- `setjmp` saves a calling context.
- `longjmp` restores that context and jumps back without normal return chaining.
- Nonlocal jumps bypass ordinary stack unwinding structure.
- They can simplify recovery paths but can also skip cleanup logic.
- Program state must still be consistent at the jump target.
