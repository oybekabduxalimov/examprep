# Q19 — Input/Output, Standard I/O

## Lecture goal
Understand low-level and buffered I/O interfaces and their behavior.

---

## 1) Low-Level I/O
- File descriptors and system calls (`open/read/write/close`).
- Direct control over bytes and error handling.

## 2) Standard Streams
- `stdin`, `stdout`, `stderr` roles.
- Used for interactive input and shell pipelines.

## 3) Buffered I/O (`stdio`)
- Improves performance via buffering.
- Behavior differs for terminal vs file contexts.

## 4) Correctness Concerns
- Partial reads/writes
- EOF vs error distinction
- Flush/close discipline

## 5) Redirection and Composition
- Stream redirection supports composable command workflows.

## What to emphasize when speaking
1. I/O is a contract with the OS, not guaranteed full transfer per call.
2. Buffered and unbuffered APIs trade control vs convenience.
3. Error handling is fundamental for robust programs.

## Short speaking script (about 1 minute)
This lecture introduces system-level I/O and standard C-style buffered I/O.  
File descriptors and system calls provide fine-grained control, while standard streams add convenience and buffering.  
Reliable I/O code must handle partial operations and distinguish EOF from errors.  
These concepts are essential for building dependable tools and services.

