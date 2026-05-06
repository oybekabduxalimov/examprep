# Q10 - Basic Data Types (`db`, `dw`, `dd`, `dq`, etc.), Organization of Arrays including Nested Arrays

## 1) Basic NASM data directives
- `db` defines bytes.
- `dw` defines 2-byte words.
- `dd` defines 4-byte doublewords.
- `dq` defines 8-byte quadwords.
- Other directives select larger fixed-width storage when needed.
- The directive determines how many bytes each initializer occupies.

## 2) Initialized and reserved storage
- Data directives can emit initialized values directly into the object file.
- Reserved-storage directives allocate space without explicit initial contents.
- Strings are stored as byte sequences.
- Numeric initializers are laid out in memory according to the directive width.
- A label marks the address of the first byte of the object.

## 3) One-dimensional arrays
- Array elements are stored contiguously.
- The element address is `base + index * element_size`.
- The index is logical, but the offset is measured in bytes.
- Larger element sizes make stride larger.
- Sequential traversal benefits from contiguous layout.

## 4) Multi-dimensional arrays
- A 2D array is still one linear memory block.
- Rows are placed one after another in row-major order in the common C-style layout.
- A 3D array extends the same idea with one more dimension.
- Address calculation multiplies by row size and plane size.
- Nested arrays are not separate objects unless explicitly stored as pointers.

## 5) Indexing formulas
- For a 2D array, address calculation needs column count.
- For a 3D array, address calculation needs both row and column counts.
- Element size is always part of the final byte offset.
- Wrong dimension math accesses the wrong data even when the base address is correct.
- Assembly code must compute these offsets explicitly.

## 6) Practical layout awareness
- Contiguous layout helps cache and sequential access.
- Element type controls both storage size and address stride.
- Arrays of bytes, words, and doublewords require different indexing scales.
- Nested arrays are simple in concept but easy to mis-index in assembly.
- Reading raw memory requires knowing both base address and element size.
