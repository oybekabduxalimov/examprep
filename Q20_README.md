# Q20 - Virtual Memory, Address Translation

## 1) Why virtual memory exists
- Virtual memory gives each process a private linear address space.
- It isolates processes from one another.
- It lets RAM act as a cache for a larger address space backed by disk.
- It simplifies programming by separating logical addresses from physical placement.
- Virtual memory is about protection and abstraction, not only about size.

## 2) Pages and frames
- Virtual memory is divided into virtual pages.
- Physical memory is divided into page frames of the same size.
- A virtual address splits into virtual page number and page offset.
- The page offset is preserved during translation.
- Any virtual page can be mapped to a compatible physical frame.

## 3) Page tables
- A page table maps virtual pages to physical pages.
- Each page-table entry stores mapping and status information.
- Common entry information includes valid state, frame number, and permission bits.
- A missing or invalid entry means the page is not currently usable from RAM.
- Page tables are kernel-managed data structures stored in memory.

## 4) Address translation path
- The CPU issues a virtual address.
- The MMU uses the current page table to find the matching physical page.
- The physical address is built from the physical page number plus the original offset.
- If the translation exists, the access proceeds to cache or memory.
- If it does not, the hardware raises a page-fault exception.

## 5) Page faults and demand paging
- A page fault occurs when the referenced page is not currently mapped as valid in memory.
- The OS can choose a victim page to evict if RAM is full.
- Dirty pages may need to be written back before eviction.
- The needed page is loaded from disk into a frame and the page table is updated.
- The faulting instruction is then retried.

## 6) TLB and performance
- The TLB caches recent address translations.
- A TLB hit avoids an extra page-table lookup path.
- A TLB miss triggers more translation work before the memory access can continue.
- Translation speed matters because every memory reference needs an address mapping.
- TLBs make virtual memory practical at processor speed.

## 7) Protection and sharing
- Page-table entries can enforce read, write, and execute permissions.
- Illegal accesses can produce segmentation faults.
- Different processes can map different virtual addresses to the same physical frame when controlled sharing is needed.
- User and kernel memory are separated by protection rules.
- Virtual memory therefore supports both isolation and selective sharing.
