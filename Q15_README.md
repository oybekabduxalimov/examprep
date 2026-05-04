# Q15 — Linkers, Symbol Types, Symbol Resolution, Static/Dynamic Libraries

## Lecture goal
Understand how object files become executables and how symbol references are resolved.

---

## 1) Compilation vs Linking
- Compilation translates source to object files.
- Linking combines objects and resolves cross-file references.

## 2) Symbols and Relocation
- Symbol table tracks definitions/references.
- Relocation adjusts addresses in final binary layout.

## 3) Symbol Resolution
- Undefined symbols must match definitions.
- Resolution order affects final linking outcome.

## 4) Static Libraries
- Code copied into executable at link time.
- Larger binary, fewer runtime dependencies.

## 5) Dynamic Libraries
- Loaded and linked at runtime.
- Smaller binaries, shared updates, dependency management.

## What to emphasize when speaking
1. Linker is responsible for program composition.
2. Symbol/relocation logic explains many build errors.
3. Static vs dynamic linking is a deployment tradeoff.

## Short speaking script (about 1 minute)
This lecture explains the linker stage that turns separate object files into one runnable program.  
Symbols and relocation are the core mechanisms that bind references to actual addresses.  
Static linking embeds library code at build time, while dynamic linking resolves shared libraries at runtime.  
Most unresolved symbol errors are direct consequences of this resolution process.

