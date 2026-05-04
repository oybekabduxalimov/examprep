# Q03 — Fractional Binary Numbers, Float/Double, Rounding

## Lecture goal
Understand floating-point representation and practical implications of finite precision.

---

## 1) IEEE-754 Representation
- Float/double store sign, exponent, and fraction (mantissa).
- Float: lower precision/range than double.
- Binary scientific notation enables very large/small values.

## 2) Precision vs Range
- Exponent controls range.
- Fraction controls precision.
- You trade exactness for wide dynamic range.

## 3) Special Values
- `+inf` / `-inf`
- `NaN`
- Signed zero
- Subnormal values near zero

## 4) Rounding Behavior
- Most operations round to nearest-even by default.
- Some decimal values (e.g., 0.1) are not exact in binary.
- Small errors accumulate across many operations.

## 5) Numerical Stability Concerns
- Equality checks can fail unexpectedly.
- Subtracting nearly equal values loses significant precision.
- Use epsilon/tolerance comparisons.

## What to emphasize when speaking
1. Floating-point is approximate arithmetic.
2. Exact decimal intuition does not transfer directly to binary floats.
3. Robust code accounts for rounding and precision limits.

## Short speaking script (about 1 minute)
This lecture explains binary floating-point representation under IEEE-754.  
A number is stored using sign, exponent, and fraction, which gives huge range but finite precision.  
Because many decimal fractions are inexact in binary, arithmetic includes rounding and tiny errors.  
That is why numerical code should avoid strict equality and use stability-aware methods.

