# Q20 — Virtual Memory, Address Translation

## Lecture goal
Explain virtual-to-physical translation and memory protection using paging.

---

## 1) Virtual Memory Purpose
- Process isolation and protection.
- Larger logical address abstraction.

## 2) Pages and Frames
- Virtual addresses split into page number + offset.
- Page tables map virtual pages to physical frames.

## 3) Translation Performance
- TLB caches recent translations.
- TLB misses trigger page-table walk overhead.

## 4) Page Fault Handling
- Missing or invalid mappings raise page faults.
- OS may load page on demand (demand paging).

## 5) Protection and Access Control
- Read/write/execute permissions.
- User vs kernel access boundaries.

## What to emphasize when speaking
1. Virtual memory is about isolation as much as capacity.
2. TLB is crucial for practical translation speed.
3. Page faults are normal control events, not always fatal errors.

## Short speaking script (about 1 minute)
This lecture explains how each process sees virtual addresses while hardware and OS translate them to physical memory.  
Paging, page tables, and TLB together provide protected and efficient access.  
When mappings are absent, page faults invoke OS handling, often enabling demand paging.  
So virtual memory is a core mechanism for both safety and flexibility.

