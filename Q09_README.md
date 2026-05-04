# Q09 — STRUC, ISTRUC, Alignment Principles

## Lecture goal
Represent structured data in assembly and understand alignment/padding effects.

---

## 1) Structured Layout in NASM
- `STRUC` defines named field offsets.
- Supports safer access than manual byte counting.

## 2) Instance Initialization
- `ISTRUC` initializes structure instances field-by-field.
- Improves readability of static data definitions.

## 3) Alignment and Padding
- Fields may be aligned to boundaries (2/4/8/16 bytes).
- Padding may be inserted between fields.
- Total size may exceed sum of raw field sizes.

## 4) Why Alignment Matters
- Better access efficiency on CPU/memory subsystem.
- Misalignment may cost cycles or fault on some systems.

## 5) ABI/Interop Implications
- Struct layout must match compiler/ABI expectations.
- Critical in mixed C/assembly projects.

## What to emphasize when speaking
1. Offsets should be symbolic whenever possible.
2. Padding is intentional, not accidental waste.
3. Correct layout is required for inter-language compatibility.

## Short speaking script (about 1 minute)
This lecture focuses on describing structured memory layout in assembly.  
`STRUC` and `ISTRUC` make field offsets and initialization explicit and maintainable.  
Alignment rules introduce padding but improve correctness and performance, especially under ABI constraints.  
This topic is central when assembly interacts with C structures.

