# Q14 - Memory Hierarchy: HDD and SSD

## 1) Hard disk physical structure
- A hard disk contains spinning platters mounted on a spindle.
- Each platter surface is divided into concentric tracks.
- Tracks are divided into sectors separated by gaps.
- Aligned tracks across platters form a cylinder.
- Read and write heads move together from cylinder to cylinder.

## 2) Disk geometry and capacity
- Capacity depends on bytes per sector, sectors per track, tracks per surface, surfaces, and platters.
- Modern disks use recording zones rather than a single uniform sectors-per-track value.
- Outer tracks can store more sectors than inner tracks.
- The controller hides most geometry details from software.
- Vendor capacity numbers are based on decimal storage units.

## 3) HDD access time components
- Seek time moves the head to the target track.
- Rotational latency waits for the desired sector to rotate under the head.
- Transfer time reads or writes the sector contents.
- Total access time is roughly the sum of these three components.
- For random access, seek and rotational latency dominate far more than transfer time.

## 4) Logical block abstraction and I/O path
- Software usually addresses a disk as a sequence of logical blocks.
- The disk controller maps logical blocks to physical sectors.
- The CPU issues a command with block number and destination memory location.
- The controller can move data into memory using DMA.
- Completion is typically reported back to the CPU with an interrupt.

## 5) SSD organization
- An SSD uses flash memory instead of moving platters.
- Data is read and written in page-sized units.
- Erase happens at block granularity, which is larger than a page.
- Pages belong to erase blocks inside the flash array.
- A flash translation layer maps logical blocks to physical flash locations.

## 6) SSD write constraints
- A page cannot be overwritten in place until its block is erased.
- Random writes can trigger copying of still-valid pages into a new block.
- Garbage collection and wear leveling are part of SSD management.
- Repeated writes wear flash cells out over time.
- Random writes are often much slower than random reads because of erase and relocation work.

## 7) HDD versus SSD tradeoffs
- HDDs rely on mechanical motion, so random access is slow.
- SSDs have no moving parts, so access latency is much lower.
- SSDs are faster, quieter, and more shock-resistant.
- HDDs have traditionally offered cheaper large capacity.
- SSD performance depends heavily on write patterns, controller policy, and flash management.
