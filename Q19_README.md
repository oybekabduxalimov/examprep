# Q19 - Input/Output, Standard I/O

## 1) Unix I/O model
- Unix treats many resources as files.
- Disk files, terminals, pipes, and sockets use a similar I/O interface.
- A file is fundamentally a sequence of bytes.
- Each open file is referenced through a file descriptor.
- Consistency of interface is one of the main design ideas of Unix I/O.

## 2) Core system calls
- `open` obtains a file descriptor for a file or device.
- `close` releases the descriptor.
- `read` copies bytes from the file into memory.
- `write` copies bytes from memory to the file.
- `lseek` changes the current file position for later reads or writes.

## 3) Short counts and EOF
- `read` and `write` may transfer fewer bytes than requested.
- A short count is not automatically an error.
- End-of-file is reported by a `read` result of zero.
- Signals, terminals, and sockets commonly produce short counts.
- Correct I/O code often loops until the full intended transfer is complete.

## 4) Standard descriptors and redirection
- New processes usually begin with descriptors `0`, `1`, and `2` open.
- These are standard input, standard output, and standard error.
- Shell redirection works by reassigning where those descriptors point.
- Standard streams make pipelines and command composition possible.
- Correct programs distinguish normal output from diagnostic output.

## 5) Kernel view of open files
- Each process has a descriptor table.
- Descriptors point to system-wide open-file entries.
- Open-file entries track current offset and reference count.
- Lower layers hold metadata such as file type, permissions, and disk location.
- Multiple descriptors can refer to the same underlying open file state.

## 6) File metadata
- Metadata describes a file rather than its payload bytes.
- Common metadata includes size, type, permissions, ownership, and timestamps.
- Unix exposes metadata through `stat`, `fstat`, and related calls.
- Directories and device files are represented with file metadata too.
- Programs often need metadata to decide how to process a path safely.

## 7) Standard I/O buffering
- `stdio` builds a buffered interface on top of lower-level file descriptors.
- Buffering reduces system-call overhead.
- Line buffering is common for terminal output.
- Full buffering is common for regular files.
- Mixing raw Unix I/O and `stdio` on the same stream requires care because buffering changes visibility and timing.
