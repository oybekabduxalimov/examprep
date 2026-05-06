# Q06 - Memory Addressing Modes, MOV, LEA, JMP and Conditional Jumps, FOR and WHILE Loops, SWITCH-CASE in Assembly

## 1) Addressing modes
- Immediate mode uses a constant encoded in the instruction.
- Register mode uses a value already in a register.
- Direct or displacement mode uses a memory address plus an offset.
- Indexed addressing combines base, index, scale, and displacement.
- Effective address calculation is central to arrays, pointers, and structures.

## 2) Effective address form
- x86 commonly computes addresses as `base + index * scale + displacement`.
- The scale factor is typically `1`, `2`, `4`, or `8`.
- Base registers often point to arrays, stack frames, or structures.
- Index registers usually select elements or fields.
- Displacement provides constant offsets such as field positions or local variable slots.

## 3) `MOV` and data transfer
- `MOV` copies data from source to destination.
- It does not perform arithmetic or pointer dereference by itself.
- Source and destination sizes must match.
- Direct memory-to-memory `MOV` is restricted in common x86 forms.
- Register choices determine whether the move is byte, word, doubleword, or quadword sized.

## 4) `LEA` as address and arithmetic tool
- `LEA` computes an effective address without reading memory.
- It is used for pointer calculation.
- It is also used for fast arithmetic such as `x + 4*y`.
- `LEA` changes the destination register only.
- `LEA` does not update flags.

## 5) Jumps and conditional control flow
- `JMP` performs an unconditional transfer of control.
- Conditional jumps inspect flags set by `CMP`, `TEST`, or arithmetic instructions.
- Signed and unsigned comparisons use different jump mnemonics.
- A branch changes the next instruction by rewriting the instruction pointer.
- Labels provide the target locations for branches.

## 6) Translating loops
- `while` loops usually test before entering the body.
- `do-while` loops test after executing the body once.
- `for` loops compile into initialization, test, body, and update steps.
- Loop counters often live in registers.
- The loop condition becomes a compare plus conditional jump.

## 7) Translating `switch`
- Small `switch` statements can compile into chains of compares and jumps.
- Dense `switch` ranges often use jump tables.
- A jump table stores target addresses indexed by the case value.
- Bounds checking is needed before indexing the table.
- `default` handles unmatched values.
