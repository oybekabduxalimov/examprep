# Q07 — Stack Organization, Stack Operations, Procedures, Recursion, Stack Frame

## Lecture goal
Explain function call mechanics using stack frames and calling conventions.

---

## 1) Stack Fundamentals
- LIFO structure used for call context.
- Stack pointer tracks current top.

## 2) Function Call Sequence
- Caller sets up arguments.
- `CALL` stores return address.
- Callee allocates locals and saves required registers.

## 3) Stack Frame Layout
- Return address, saved frame pointer, locals, temporaries.
- Frame pointer simplifies stable access to frame data.

## 4) Calling Convention Rules
- Caller-saved vs callee-saved responsibilities.
- Return values placed in defined registers.

## 5) Recursion Behavior
- Each recursive call creates a new frame.
- Deep recursion risks stack overflow.

## What to emphasize when speaking
1. Function calls are ABI contracts.
2. Stack/frame discipline prevents corruption.
3. Recursion is just repeated frame creation.

## Short speaking script (about 1 minute)
This lecture shows how procedure calls are implemented on the stack.  
Each call creates a frame containing return and local execution context, and conventions define register/argument responsibilities.  
Recursion works naturally by stacking frames, but depth is limited by stack size.  
Most low-level call bugs come from violating frame or save/restore rules.

