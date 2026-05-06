# Q08 - NASM Preprocessor, Single-line and Multi-line Macros in NASM

## 1) Preprocessor role
- The NASM preprocessor runs before the assembler proper.
- It performs text substitution and conditional source generation.
- Preprocessing helps remove repetition from assembly programs.
- Macro expansion happens before instruction encoding.
- The preprocessor works on source text, not on run-time values.

## 2) Single-line macro forms
- `%define` creates symbolic text substitution.
- `%xdefine` expands the replacement differently from `%define` in nested cases.
- `%assign` creates numeric preprocessor variables.
- `%undef` removes a macro definition.
- Single-line macros are useful for constants, aliases, and short reusable patterns.

## 3) Multi-line macros
- `%macro` and `%endmacro` define reusable instruction blocks.
- Macro parameters are referenced with placeholders such as `%1`, `%2`, and so on.
- One macro can generate repeated code with different operands.
- Macros reduce copy-paste across procedures or data declarations.
- Expansion is textual, so the generated instructions must still be valid assembly.

## 4) Local labels and macro hygiene
- `%%label` creates labels local to a macro expansion.
- Local labels prevent name collisions across multiple macro uses.
- Macro-generated code must avoid accidentally capturing global names.
- Good macro design keeps parameter meaning explicit.
- Poor macro hygiene can make debugging difficult.

## 5) Conditional assembly support
- `%if`, `%elif`, `%else`, and `%endif` select source text conditionally.
- `%ifdef` and `%ifndef` test whether a symbol is defined.
- `%include` pulls in shared source fragments.
- Conditional assembly supports portability, feature toggles, and configuration.
- These choices are made at assembly time, not at run time.

## 6) Benefits and limitations
- Macros can make assembly shorter and more uniform.
- They can encode calling patterns and repeated boilerplate.
- They do not create true run-time functions.
- Large macro systems can hide what instructions are actually emitted.
- Reading expanded intent still requires understanding the generated assembly.
