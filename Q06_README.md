# Q06 — Addressing Modes, MOV/LEA, Jumps, Loops, Switch-Case in Assembly

## Lecture goal
Understand memory addressing and control-flow construction in assembly.

---

## 1) Addressing Modes
- Immediate, register, direct/indirect memory operands.
- Effective address computation with base/index/scale/displacement.

## 2) MOV vs LEA
- `MOV` transfers data.
- `LEA` computes addresses/arithmetic expressions without dereference.

## 3) Branching Basics
- `JMP` for unconditional jumps.
- Conditional jumps rely on prior compare/test results.

## 4) Building Loops
- FOR/WHILE compile into labels + compare + conditional branch.
- Loop correctness depends on update and exit condition ordering.

## 5) Switch-Case Translation
- Dense cases often use jump tables.
- Sparse cases may compile as compare-branch chains.

## What to emphasize when speaking
1. Effective address math is foundational for array/pointer code.
2. Control flow is explicit in assembly.
3. `LEA` is a powerful non-memory arithmetic helper.

## Short speaking script (about 1 minute)
This lecture connects data access and control flow.  
Addressing modes determine where operands come from, while compares and jumps encode logic decisions.  
High-level loops and switch statements are built from labels and branch instructions.  
Understanding this mapping is crucial for reading compiler-generated assembly.

