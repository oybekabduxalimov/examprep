# Q05 — Assembly Language, Arithmetic Operations in Assembly

## Lecture goal
Build practical understanding of arithmetic instructions and status flags in assembly.

---

## 1) Data Movement Before Arithmetic
- Operands are typically loaded into registers first.
- Operand size must match instruction expectations.

## 2) Core Arithmetic Instructions
- `ADD`, `SUB`, `INC`, `DEC`
- `MUL/IMUL` and `DIV/IDIV`
- Signed and unsigned forms differ in semantics.

## 3) Processor Flags
- `CF`, `OF`, `ZF`, `SF` change after operations.
- Branch decisions often depend on flag state.

## 4) Multiplication/Division Caveats
- Division has strict dividend/register requirements.
- Misconfigured registers can cause faults.

## 5) Expression Translation
- High-level expressions become ordered register operations.
- Instruction ordering and temporary storage matter.

## What to emphasize when speaking
1. Arithmetic correctness includes both value and flags.
2. Signed/unsigned variants are not interchangeable.
3. Division rules are common source of mistakes.

## Short speaking script (about 1 minute)
This lecture focuses on arithmetic at instruction level.  
We perform operations through registers and track how CPU flags change, since those flags control later branches.  
Signed vs unsigned arithmetic must be selected deliberately, especially for multiply/divide instructions.  
The overall skill is converting high-level formulas into safe instruction sequences.

