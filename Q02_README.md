# Q02 — Encoding Integers, Arithmetic Operations with Integers

## Lecture goal
Understand integer encoding and how arithmetic behaves with fixed-width binary numbers.

---

## 1) Integer Encodings
- Unsigned integers represent non-negative values.
- Signed integers are commonly represented with two's complement.
- Bit width determines maximum/minimum representable values.

## 2) Integer Ranges
- Unsigned n-bit range: `0` to `2^n - 1`
- Signed n-bit range: `-2^(n-1)` to `2^(n-1)-1`
- Signed range is asymmetric due to zero representation.

## 3) Overflow and Wraparound
- Unsigned overflow wraps modulo `2^n`.
- Signed overflow is dangerous and often undefined in C/C++.
- Arithmetic must be reasoned with width limits in mind.

## 4) Extension and Conversions
- Zero extension for unsigned widening.
- Sign extension for signed widening.
- Mixed signed/unsigned operations may cause unexpected results.

## 5) Bitwise/Shift Operations
- Logical vs arithmetic shift behavior differs for signedness.
- Bitwise operations are useful for masks, flags, and low-level control.

## What to emphasize when speaking
1. Bit pattern is fixed; meaning depends on signedness.
2. Overflow is normal at hardware level but risky in software logic.
3. Signed/unsigned mixing causes many real bugs.

## Short speaking script (about 1 minute)
This lecture covers how integers are encoded in fixed-width binary, especially two's complement for signed values.  
The important point is that arithmetic is bounded by width, so overflow behavior must be expected and handled.  
Unsigned operations wrap predictably, while signed overflow can be problematic in language semantics.  
Type conversions and signed/unsigned comparisons are common bug sources in systems programming.

