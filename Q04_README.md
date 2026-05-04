# Q04 — Intel x86, AMD/Intel x64, 32-bit and 64-bit Integer Registers

## Lecture goal
Understand processor/register architecture differences between 32-bit and 64-bit modes.

---

## 1) Architecture Lineage
- x86 is the classic 32-bit ISA family.
- x86-64 (AMD64/Intel64) extends register width and address space.

## 2) Register Model
- General-purpose registers have subregister views (`AL/AX/EAX/RAX`).
- Width and naming matter for instruction semantics.

## 3) 32-bit vs 64-bit Mode Differences
- Pointer size changes.
- Register count and calling conventions differ.
- Address space and performance characteristics evolve.

## 4) Instruction Pointer and Control
- `EIP/RIP` controls execution flow.
- Branches and calls modify control path explicitly.

## 5) ABI Relevance
- ABI defines argument passing, return values, and preserved registers.
- Assembly must follow ABI for interop with compiled code.

## What to emphasize when speaking
1. Register width impacts data handling and addressing.
2. Subregister interactions can have side effects.
3. ABI knowledge is essential for correct function-level assembly.

## Short speaking script (about 1 minute)
This lecture compares x86 and x86-64 architecture from a programmer perspective.  
The key practical topic is register organization and how 32-bit and 64-bit modes differ in pointers, conventions, and execution behavior.  
Understanding register hierarchy and ABI rules is required before writing reliable low-level code.

