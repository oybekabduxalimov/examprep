# Q15 - Linkers, Types of Symbols, Symbol Resolution, Static and Dynamic Libraries

## 1) Why linkers exist
- Large programs are built from multiple source files.
- Separate compilation avoids recompiling unchanged modules.
- Libraries collect commonly reused code in reusable form.
- The linker combines independently produced object files into a usable executable or shared object.
- Linking is about both modularity and build efficiency.

## 2) Main linker tasks
- Symbol resolution matches every external reference with one definition.
- Relocation places code and data into final memory positions.
- Section merging combines related sections such as `.text` and `.data`.
- Address-sensitive instructions and pointers must be updated after final placement.
- The linker turns relative object-file layouts into a coherent program image.

## 3) Object-file kinds and sections
- Relocatable object files hold code and data before final linking.
- Executable object files are ready to be loaded and run.
- Shared objects support dynamic linking at load time or run time.
- Common sections include `.text`, `.rodata`, `.data`, `.bss`, `.symtab`, and relocation sections.
- `.bss` represents uninitialized storage without storing explicit bytes in the file image.

## 4) Symbol categories
- Global symbols are defined in one module and can be referenced by others.
- External symbols are referenced in a module but defined elsewhere.
- Local linker symbols are visible only inside one module.
- Functions and global variables commonly appear in symbol tables.
- Automatic local variables on the stack are not normal linker symbols.

## 5) Symbol resolution rules
- Each external reference must resolve to exactly one definition.
- Multiple strong definitions create link-time errors.
- Strong and weak definitions follow precedence rules.
- Missing definitions produce undefined-reference errors.
- Library search order can affect whether a symbol is found.
- % ar -t /usr/lib/libc.a | sort
- % ar -t /usr/lib/libm.a | sort

## 6) Relocation details
- Object files use offsets before final placement is known.
- Relocation entries mark instructions and data that need patching.
- Call targets, global variable addresses, and pointer initializers often require relocation.
- After relocation, the executable contains the final addresses expected at load time.
- Relocation is what turns symbolic references into real addresses.

## 7) Static and dynamic libraries
- Static libraries copy needed object code into the executable during linking.
- Dynamic libraries remain separate and are loaded by the runtime loader.
- Static linking increases executable size but reduces external dependencies.
- Dynamic linking saves memory and disk space across many processes using the same library.
- Dynamic linking introduces loader participation and extra indirection during symbol binding.
