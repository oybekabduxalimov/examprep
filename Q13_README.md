# Q13 - Memory Hierarchy: DRAM

## 1) DRAM storage cell
- DRAM stores each bit as charge in a capacitor.
- One transistor controls access to the cell.
- Charge leaks over time, so the value is not permanent without refresh.
- DRAM is dense and inexpensive compared with SRAM.
- Density is one reason DRAM is used for main memory.

## 2) Refresh and volatility
- DRAM contents must be refreshed periodically.
- Refresh happens on a hardware schedule, typically every tens of milliseconds.
- Refresh preserves correctness, not performance.
- Refresh overhead is built into how DRAM operates.
- Losing refresh means losing stored data.

## 3) Internal organization
- DRAM arrays are organized by rows and columns.
- Access begins by selecting a row.
- The selected row is copied into an internal row buffer.
- A column selection then chooses the desired supercell from that buffered row.
- Accesses to the same open row are faster than accesses that require a different row.

## 4) RAS, CAS, and row-buffer behavior
- `RAS` selects the row.
- `CAS` selects the column after the row is available.
- The row buffer acts like a small staging area inside the chip.
- Row hits benefit from locality within the same row.
- Row conflicts force additional DRAM activity and add latency.

## 5) Memory modules and controllers
- Multiple DRAM chips are combined to build wider memory modules.
- A controller coordinates addresses, timing, and data transfer.
- A 64-bit memory word is often assembled from several chips in parallel.
- Main memory performance depends on both chips and controller policy.
- DRAM access is therefore a system-level behavior, not just a cell-level behavior.

## 6) SRAM versus DRAM
- SRAM uses multi-transistor storage cells and does not need refresh while powered.
- SRAM is faster and more expensive.
- DRAM uses fewer transistors per bit and is cheaper.
- SRAM is commonly used for caches.
- DRAM is commonly used for large main-memory capacity.

## 7) Enhanced DRAM families
- `SDRAM` synchronizes operations with a clock.
- `DDR SDRAM` transfers data on both clock edges.
- Later DDR generations increase prefetch and interface bandwidth.
- The basic storage cell stayed similar while the interface evolved.
- Performance improvements came largely from organization and signaling around the core DRAM array.
