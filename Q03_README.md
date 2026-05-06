# Q03 - Encoding Fractional Binary Numbers, Float, Double, Arithmetic Operations, Rounding

## 1) Fractional values in binary
- Digits to the right of the binary point use negative powers of 2.
- Some decimal fractions have exact binary forms.
- Many decimal fractions become repeating binary expansions.
- Finite storage forces approximation for many real numbers.
- Repeating patterns are one reason floating-point arithmetic is not exact.

## 2) IEEE 754 structure
- Floating-point values are split into sign, exponent, and fraction fields.
- `float` uses 32 bits.
- `double` uses 64 bits.
- The exponent is stored with a bias, not as a signed integer.
- The fraction field stores the significant bits after normalization.

## 3) Normalized representation
- Normalized numbers use an implicit leading `1` in the significand.
- The actual significand is `1.fraction`.
- The stored exponent plus bias determines scale.
- Normalization gives more precision than storing the leading `1` explicitly.
- Most nonzero floating-point numbers are stored in normalized form.

## 4) Denormalized and special values
- Denormalized values fill the gap near zero.
- Denormals use the smallest exponent encoding with a leading `0` significand.
- `+0` and `-0` are distinct bit patterns.
- An all-ones exponent with zero fraction encodes infinity.
- An all-ones exponent with nonzero fraction encodes `NaN`.

## 5) Precision and rounding
- Floating-point precision is limited by significand width.
- Many arithmetic results must be rounded to fit back into the format.
- Rounding is usually to nearest, ties to even.
- Rounding error can accumulate across long computations.
- A mathematically tiny difference can disappear if it is smaller than the current precision step.

## 6) Floating-point arithmetic behavior
- Addition aligns exponents before combining significands.
- Multiplication adds exponents and multiplies significands.
- Division subtracts exponents and divides significands.
- Every arithmetic step can introduce a new rounding.
- Reordering operations can change the final result.

## 7) Practical consequences
- Floating-point arithmetic is approximate, not exact real arithmetic.
- Equality comparison is fragile for computed fractions.
- Large values can lose small increments due to scale differences.
- Underflow pushes results toward zero.
- Overflow produces infinities or exceptional results instead of valid finite numbers.
