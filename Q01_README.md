# Q01 — Binary Representation, Byte-Oriented Memory, Byte Ordering

## Lecture goal
Understand how data is represented in bits/bytes and how byte ordering affects interpretation of multi-byte values.

---

## 1) Number Systems Used in Computing
- Decimal is human-friendly; binary/hex are machine-friendly.
- Hex is compact for binary groups (4 bits per hex digit).
- Fixed width (8/16/32/64-bit) determines representable range.

## 2) Bits, Bytes, and Memory Addresses
- A bit is the smallest unit; 8 bits = 1 byte.
- Memory is byte-addressable: each address points to one byte.
- Multi-byte values occupy consecutive addresses.

## 3) Signed vs Unsigned Interpretation
- Same bit pattern can mean different numeric values by type.
- Unsigned treats all bits as magnitude.
- Signed usually uses two's complement interpretation.

## 4) Byte Ordering (Endianness)
- Little-endian: least significant byte at lowest address.
- Big-endian: most significant byte at lowest address.
- Single-byte values are unaffected by endianness.

## 5) Why Endianness Matters
- Binary file parsing
- Network communication (network byte order)
- Cross-platform debugging and reverse engineering

## What to emphasize when speaking
1. Memory is byte-oriented, not integer-oriented.
2. Type interpretation and byte order both matter.
3. Endianness errors can silently produce wrong values.

## Short speaking script (about 1 minute)
This lecture explains how computers store values as bits and bytes in memory.  
The key idea is that memory addresses bytes, and larger values are built from multiple bytes.  
Because of that, byte order becomes important: little-endian and big-endian store the same value in different byte sequences.  
So when reading raw memory, correct interpretation requires both data type and endianness.

