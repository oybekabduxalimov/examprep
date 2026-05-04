# Q16 — Asynchronous and Synchronous Exceptions

## Lecture goal
Differentiate exception classes and explain OS/CPU exception handling flow.

---

## 1) Exception Concept
- Exception = control transfer due to unusual event.
- Enables safe handling instead of silent failure.

## 2) Synchronous Exceptions
- Caused by current instruction execution.
- Includes faults, traps, abort-like events.

## 3) Asynchronous Exceptions
- Typically hardware interrupts from external events.
- Not tied to a specific currently executing instruction result.

## 4) Dispatch Mechanism
- CPU uses exception vector/table.
- Control transfers to kernel handler.

## 5) Return and Recovery
- Handler may resume, terminate, or alter execution path.

## What to emphasize when speaking
1. Synchronous vs asynchronous distinction is causal.
2. Exception handling is structured control transfer.
3. Privilege transition to kernel is central for safety.

## Short speaking script (about 1 minute)
This lecture classifies exceptions based on origin.  
Synchronous exceptions arise from the executing instruction, while asynchronous interrupts come from external events.  
CPU dispatches handlers through vector tables, usually entering kernel mode for protected handling.  
This mechanism preserves system stability while allowing controlled recovery or termination.

