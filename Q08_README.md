# Q08 — NASM Preprocessor, Single-Line and Multi-Line Macros

## Lecture goal
Use NASM preprocessing to reduce repetition and improve assembly maintainability.

---

## 1) Why Preprocessing Exists
- Assembly is verbose; repeated patterns are common.
- Preprocessor expands templates before real assembly.

## 2) Single-Line Macros
- Alias constants or repeated token patterns.
- Useful for symbolic readability.

## 3) Multi-Line Macros
- Encapsulate repeated instruction blocks.
- Support parameters for reusable patterns.
- Can include local labels to avoid collisions.

## 4) Conditional Assembly
- Include/exclude code at assemble time.
- Useful for configuration/debug variants.

## 5) Tradeoffs
- Better reuse and shorter source.
- Overuse can hide generated control flow and reduce readability.

## What to emphasize when speaking
1. Macros are compile-time code generation, not runtime calls.
2. Macro design should improve clarity, not obscure logic.
3. Parameterized macros help enforce consistent patterns.

## Short speaking script (about 1 minute)
This lecture introduces NASM preprocessing as a way to write cleaner assembly.  
Single-line macros are good for constants and aliases, while multi-line macros package repeated instruction sequences with parameters.  
Macros expand before assembling, so they improve reuse but can make debugging harder if overly complex.  
The goal is maintainable low-level code with predictable expansion.

