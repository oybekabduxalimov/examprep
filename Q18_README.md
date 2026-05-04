# Q18 — Signals, Signal Handlers, Nonlocal Jumps

## Lecture goal
Understand asynchronous signal handling and control transfer beyond normal call/return flow.

---

## 1) Signal Model
- Signals notify a process about asynchronous events.
- Default actions vary: terminate, stop, ignore, continue.

## 2) Custom Handlers
- Processes can register signal handlers.
- Handlers interrupt normal control flow.

## 3) Safety Constraints
- Handler code must be minimal and safe.
- Reentrancy concerns are important.

## 4) Blocking/Delivery Semantics
- Signals can be masked/blocked temporarily.
- Pending signals delivered when unblocked.

## 5) Nonlocal Jumps
- `setjmp/longjmp` allows abrupt control transfer.
- Useful for recovery, but risky if state is inconsistent.

## What to emphasize when speaking
1. Signals are asynchronous and timing-sensitive.
2. Handler safety is a major practical concern.
3. Nonlocal jumps bypass normal stack unwinding patterns.

## Short speaking script (about 1 minute)
This lecture explains Unix-style signals as asynchronous process notifications.  
Signal handlers can react to events, but they run under strict safety constraints because they interrupt normal execution.  
Nonlocal jumps provide powerful recovery paths but must be used carefully to avoid inconsistent program state.  
Overall, correctness depends on disciplined async control design.

