# Q01 - Binary Representation, Byte-Oriented Memory Organization, Byte Ordering

## 1) Binary and hexadecimal representation
- Binary uses powers of 2.
- Hexadecimal groups 4 bits into 1 digit.
- `1 byte = 8 bits`, so 2 hex digits describe 1 byte.
- Fixed width matters because leading zeros are part of the stored pattern.
- The same value can be written in decimal, binary, or hex while the underlying bits stay the same.

## 2) Bytes, words, and data sizes
- A bit is the smallest stored state.
- A byte is the basic addressable memory unit.
- A word is the processor's natural integer and address size.
- 32-bit systems commonly use 4-byte words.
- 64-bit systems commonly use 8-byte words.
- C type sizes depend on the platform, especially `long` and pointers.

## 3) Byte-oriented memory organization
- Memory is viewed as a large array of bytes.
- Each byte has its own address.
- Multi-byte values occupy consecutive byte addresses.
- A pointer stores a memory address, not the value at that address.
- Processes get private virtual address spaces, so one process cannot directly overwrite another process's memory.

## 4) Word-oriented view
- A word starts at the address of its first byte.
- Successive 32-bit words differ by 4 in address.
- Successive 64-bit words differ by 8 in address.
- Addresses still name bytes even when we talk about words.
- Larger data objects are built from adjacent bytes.

## 5) Bitwise operations
- `AND` keeps bits that are 1 in both operands.
- `OR` keeps bits that are 1 in either operand.
- `XOR` keeps bits that differ.
- `NOT` flips each bit.
- Bit vectors can represent sets, permissions, masks, and flags.

## 6) Byte ordering
- Endianness decides how the bytes of a multi-byte value are laid out in memory.
- Little-endian stores the least significant byte at the lowest address.
- Big-endian stores the most significant byte at the lowest address.
- Single-byte objects are unaffected by endianness.
- A value such as `0x01234567` has the same numeric meaning on both systems but different byte layouts.

## 7) Why byte order matters
- It affects raw memory inspection.
- It affects binary file parsing.
- It affects data exchange across different machine types.
- Network protocols usually define one canonical byte order.
- Bugs appear when the program reads bytes correctly but interprets them with the wrong layout assumption.
