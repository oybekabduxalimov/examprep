# Q05 - Assembly Language, Arithmetic Operations in Assembly

## 1) Assembly language role
- Assembly is a human-readable form of machine instructions.
- Each instruction maps closely to processor operations.
- Source code names registers, constants, labels, and memory operands explicitly.
- Assembly exposes data movement and control flow without high-level abstractions.
- Understanding assembly helps explain what compilers generate.

## 2) Operand and instruction basics
- Instructions operate on registers, memory locations, or immediate constants.
- The size of the operation must be known from the opcode or operand type.
- x86 arithmetic often uses a destination register that is updated in place.
- Memory-to-memory arithmetic is generally not allowed directly.
- Labels give symbolic names to code locations.

## 3) Basic integer arithmetic
- `ADD` performs addition.
- `SUB` performs subtraction.
- `INC` and `DEC` adjust a value by 1.
- `NEG` computes arithmetic negation.
- `ADC` and `SBB` use the carry flag for multiword arithmetic.

## 4) Multiplication and division
- `MUL` performs unsigned multiplication.
- `IMUL` performs signed multiplication.
- `DIV` performs unsigned division.
- `IDIV` performs signed division.
- Division uses implicit operand registers and places quotient and remainder in fixed locations.
- Wider results often span register pairs such as `EDX:EAX` or `RDX:RAX`.

## 5) Condition codes after arithmetic
- Arithmetic instructions update processor flags.
- `ZF` signals a zero result.
- `SF` reflects the sign bit of the result.
- `CF` indicates unsigned carry or borrow behavior.
- `OF` indicates signed overflow.
- Later control-flow instructions often depend on these flags.

## 6) Shifts and low-level arithmetic patterns
- Left shift can scale a value by powers of 2.
- Right shift can divide by powers of 2 with format-specific behavior.
- Bitwise operations often support masking and field extraction around arithmetic code.
- Assembly arithmetic requires tracking both the numeric result and the flag side effects.
- Correctness depends on whether the operands are meant to be signed or unsigned.
