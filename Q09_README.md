# Q09 - STRUC and ISTRUC, Alignment Principles

## 1) `STRUC` for structure layout
- `STRUC` defines a named record layout in NASM.
- Each field gets an offset from the start of the structure.
- The structure name can also expose the total size.
- `STRUC` organizes related fields without changing how memory works underneath.
- Field order directly determines offsets.

## 2) Fields and offsets
- Each member occupies a known byte range.
- Small fields can sit next to larger fields in one contiguous block.
- Field access is address plus offset.
- Offset values are compile-time constants.
- Correct offset calculation is essential for mixed-type records.

## 3) `ISTRUC` for initialization
- `ISTRUC` creates an initialized instance that follows a `STRUC` layout.
- `AT` assigns values to named fields.
- `IEND` closes the initialization block.
- `ISTRUC` makes raw data declarations easier to read.
- The final emitted bytes still follow the same linear memory layout.

## 4) Alignment fundamentals
- Alignment means placing data at addresses that are multiples of a chosen boundary.
- Natural alignment often matches object size, such as 4-byte integers on 4-byte boundaries.
- Compilers and assemblers may insert padding to preserve alignment.
- Misaligned data can still be legal but may be slower or less convenient.
- Some hardware or instructions impose stricter alignment expectations than others.

## 5) Padding inside structures
- Padding bytes can appear between fields.
- Padding can also appear at the end of a structure.
- Padding exists to align later fields or repeated structure elements.
- Structure size is not always the sum of logical field sizes.
- Reordering fields can reduce wasted space.

## 6) Why alignment matters
- Aligned accesses often map better to memory transactions.
- Alignment simplifies hardware fetch and store behavior.
- Arrays of structures inherit the alignment needs of each element.
- Binary interfaces depend on exact layout, including padding.
- When layout must match an external format, alignment assumptions must be checked explicitly.
