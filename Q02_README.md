# Q02 - Encoding Integers, Arithmetic Operations with Integers

## 1) Unsigned integer encoding
- An unsigned `w`-bit integer represents values from `0` to `2^w - 1`.
- Each bit position has a power-of-2 weight.
- The leftmost bit in unsigned representation is just another magnitude bit.
- Overflow wraps around modulo `2^w`.
- Increasing bit width increases the representable range exponentially.

## 2) Two's-complement signed encoding
- Most systems use two's complement for signed integers.
- The most significant bit contributes a negative weight.
- A `w`-bit signed integer represents values from `-2^(w-1)` to `2^(w-1) - 1`.
- Zero has only one representation in two's complement.
- Negation can be viewed as bitwise inversion plus 1.

## 3) Converting between signed and unsigned views
- Signed and unsigned values can share the same bit pattern.
- What changes is the interpretation, not the stored bits.
- Casting between signed and unsigned often preserves the bit pattern.
- Negative signed values become large unsigned values with the same bits.
- Comparing signed and unsigned values in the same expression can produce surprising results.

## 4) Sign extension and truncation
- Expanding an unsigned value adds leading zeros.
- Expanding a signed two's-complement value replicates the sign bit.
- Truncation keeps the low-order bits and discards the rest.
- Truncation can change numeric meaning even when the low bits stay identical.
- Moving between widths is safe only when the target range still contains the value.

## 5) Integer addition and subtraction
- Hardware performs addition on bit patterns regardless of signedness.
- Subtraction is addition with a negated operand.
- `x - y` is equivalent to `x + (-y)` at the bit level.
- Carry-out matters for unsigned arithmetic.
- Overflow matters for signed arithmetic.

## 6) Overflow rules
- Unsigned overflow is wraparound and is well-defined.
- Signed overflow means the mathematical result does not fit in the destination width.
- Adding two positive signed values and getting a negative result indicates overflow.
- Adding two negative signed values and getting a positive result indicates overflow.
- Overflow is about range violation, not just a large-looking number.

## 7) Multiplication, division, and shifts
- Multiplication can require more bits than the operands provide.
- Unsigned and signed multiplication use different interpretations of the same inputs.
- Integer division discards the fractional part.
- Left shift multiplies by powers of 2 when no significant bits are lost.
- Right shift for unsigned values fills with zeros.
- Right shift for signed values is usually arithmetic, preserving the sign bit on common machines.
