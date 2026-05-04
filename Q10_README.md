# Q10 — Basic Data Types (db/dw/dd/dq), Arrays and Nested Arrays

## Lecture goal
Understand assembly data directives and address calculations for 1D/2D/3D arrays.

---

## 1) NASM Data Directives
- `db`, `dw`, `dd`, `dq` define byte/word/dword/qword elements.
- Chosen directive determines element size and indexing scale.

## 2) Linear Memory Reality
- Arrays occupy contiguous memory.
- Multi-dimensional arrays are flattened linearly.

## 3) Indexing Math
- 1D: `base + index * elem_size`
- 2D row-major: `base + ((i * cols) + j) * elem_size`
- 3D adds another stride level.

## 4) Traversal Order Effects
- Row-major traversal typically improves locality/cache behavior.
- Poor traversal order increases misses and latency.

## 5) Common Mistakes
- Wrong stride
- Off-by-one bounds
- Incorrect element size scaling

## What to emphasize when speaking
1. Multi-dimensional indexing is deterministic offset arithmetic.
2. Element size is always part of address calculation.
3. Access order impacts performance significantly.

## Short speaking script (about 1 minute)
This lecture explains how assembly data types map to memory and how array indexing is translated into address arithmetic.  
Even nested arrays are stored linearly, so indexing formulas use strides and element size scaling.  
Correctness depends on accurate offset math, and performance depends on cache-friendly traversal patterns.

