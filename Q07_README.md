# Q07 - Stack Organization, Assembly Operations with Stack, Procedures, Recursive Functions, Stack Frame

## 1) Stack fundamentals
- The stack stores temporary execution context.
- It normally grows toward lower addresses on x86-family systems.
- The stack pointer marks the current top of stack.
- Each active function call usually owns one stack frame.
- Function nesting creates a stack of frames in call order.

## 2) Core stack instructions
- `PUSH` stores a value on the stack and adjusts the stack pointer.
- `POP` retrieves the top value and adjusts the stack pointer back.
- `CALL` pushes the return address and jumps to the callee.
- `RET` pops the return address and transfers control back.
- These instructions implement function calls at the machine level.

## 3) Stack frame layout
- A stack frame holds return address, saved registers, local variables, and sometimes arguments.
- `EBP` or `RBP` is often used as a stable frame pointer.
- `ESP` or `RSP` changes as values are pushed and popped.
- Negative frame-pointer offsets commonly address locals.
- Positive frame-pointer offsets commonly address arguments in classic layouts.

## 4) Parameter passing and return values
- Arguments may be passed in registers, on the stack, or both.
- Small return values are typically placed in `EAX` or `RAX`.
- Large results may use memory supplied by the caller.
- Caller and callee must agree on the calling convention.
- The calling convention also defines which registers must be preserved.

## 5) Saving execution context
- Caller-saved registers may be overwritten by the callee.
- Callee-saved registers must be restored before returning.
- Prologue code sets up the new frame.
- Epilogue code tears the frame down.
- Incorrect save and restore logic corrupts control flow and data.

## 6) Recursive functions
- Each recursive call gets its own independent frame.
- Local variables from different recursion levels do not share storage.
- The return chain unwinds in last-in, first-out order.
- Recursion depth is limited by stack size.
- A bad base case can cause stack overflow.
