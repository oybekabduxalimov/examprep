# Q12 — Memory Hierarchy: Cache

## Lecture goal
Understand why cache memory is necessary, how it is organized, and how design choices affect performance.

---

## 1) Motivation: CPU–Memory Speed Gap
- CPU runs much faster than DRAM.
- Cache reduces average memory access time by keeping hot data nearby.
- Locality principles:
  - Temporal locality
  - Spatial locality

## 2) Cache Basics and Address Breakdown
- Data stored in cache lines (blocks).
- Hit: found in cache. Miss: fetch from lower level.
- Address split:
  1. Block offset
  2. Set index
  3. Tag

## 3) Mapping Organizations
- Direct-mapped
- Set-associative
- Fully associative
- Tradeoff: complexity vs miss behavior.

## 4) Replacement Policies
- LRU
- FIFO
- Random
- Policy affects miss rate under contention.

## 5) Write Policies
- Write-through vs write-back.
- Write-allocate vs no-write-allocate.
- Tradeoff: traffic, complexity, consistency.

## 6) Miss Types and Metrics
- Compulsory, capacity, conflict misses.
- `AMAT = Hit time + Miss rate * Miss penalty`

## 7) Multi-Level Caches
- L1/L2/L3 hierarchy balances speed and capacity.

## What to emphasize when speaking
1. Locality is the theoretical reason cache works.
2. Tag/set/offset explains lookup mechanics.
3. Associativity/policies determine practical performance.

## Short speaking script (about 1 minute)
This lecture explains cache as a solution to CPU-DRAM speed mismatch.  
A memory address is decomposed into tag, set index, and offset to determine hit/miss quickly.  
Design choices such as associativity, replacement, and write policy directly affect miss behavior and AMAT.  
Multi-level cache hierarchy further improves effective access time.

