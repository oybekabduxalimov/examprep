# Q16 - Asynchronous and Synchronous Exceptions

## 1) Core idea of an exception
- An exception is a forced pause of the current instruction stream.
- The CPU temporarily stops normal user-code execution.
- Control is transferred into the kernel.
- A handler runs to deal with the event.
- Control then resumes in a controlled way, or the process is terminated.

## 2) Common handling pipeline
- Save CPU state such as instruction pointer, flags, and important registers.
- Switch from user mode to kernel mode.
- Switch to a privileged kernel stack if needed.
- Use the exception or interrupt number to index the `IDT`.
- Jump to the kernel handler associated with that entry.
- After handling, restore state and return with instructions such as `iret` or `sysret`.

## 3) Synchronous exceptions: core meaning
- A synchronous exception is caused directly by the current instruction.
- The event is tied to what the CPU is executing right now.
- The CPU knows exactly which instruction caused the problem.
- This is why synchronous exceptions are called precise.
- Typical examples are divide-by-zero, page fault, invalid opcode, and system call traps.

## 4) Synchronous exception flow
- The program executes an instruction.
- Hardware detects a condition caused by that instruction.
- The CPU stops normal execution immediately.
- The CPU records the exception type and saves execution state.
- The CPU enters kernel mode and dispatches through the `IDT`.
- The kernel handler decides whether to recover, retry, continue, or terminate the process.

## 5) Types of synchronous exceptions
- Traps are intentional synchronous exceptions.
- System calls are a classic trap example.
- Faults are unintentional but may be recoverable.
- A page fault may be fixed by loading the missing page and retrying the instruction.
- Aborts are severe unrecoverable failures and usually terminate the current computation.

## 6) Outcomes of synchronous exceptions
- A recoverable fault may return to the same instruction.
- A trap usually returns to the next instruction.
- An invalid access may cause the OS to deliver a signal such as `SIGSEGV`.
- Divide-by-zero may lead to a signal such as `SIGFPE`.
- If the condition cannot be repaired, the process is terminated instead of resumed.

## 7) Asynchronous exceptions: interrupts
- An asynchronous exception is caused by an external event, not by the current instruction itself.
- Common sources include timer hardware, keyboard input, disk completion, and network arrival.
- The event can occur while almost any instruction stream is running.
- Timing is not determined by one specific user instruction.
- Interrupts are therefore externally triggered rather than instruction-caused.

## 8) Interrupt handling flow
- The CPU is executing normal instructions.
- A device or timer raises an interrupt request.
- The CPU finishes the current instruction first.
- The CPU then saves state and switches into kernel mode.
- The interrupt number is used to locate the correct handler in the `IDT`.
- The handler performs device-specific or scheduling work.

## 9) Typical interrupt handler work
- A timer interrupt may trigger the scheduler.
- The scheduler may save one process context and resume another.
- A keyboard interrupt may read input data into a kernel buffer.
- A disk interrupt may mark an I/O request as completed.
- A network interrupt may move packet data and wake waiting code.

## 10) Return behavior and key distinction
- After an interrupt handler, the CPU may resume the same process or a different one.
- After a synchronous exception, return behavior depends on trap, fault, or abort semantics.
- Both synchronous exceptions and interrupts use the same general kernel-entry mechanism.
- The main difference is who triggered the event: the current instruction or external hardware.
- Synchronous means "the instruction caused it"; asynchronous means "something outside requested attention."
