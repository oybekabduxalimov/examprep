# Q13 — Memory Hierarchy: DRAM

## Lecture goal
Understand DRAM structure, timing behavior, and why refresh/latency matter.

---

## 1) DRAM Cell and Volatility
- Cell stores charge in capacitor.
- Charge leaks over time, so refresh is required.

## 2) Organization
- Cells arranged into rows/columns and banks.
- Access path uses activate, read/write, precharge sequence.

## 3) Row Buffer Behavior
- Row activation loads row into buffer.
- Same-row accesses are faster (row-buffer hits).

## 4) Timing Constraints
- DRAM has strict timing parameters.
- Latency comes from protocol phases, not just distance.

## 5) Controller Impact
- Memory controller scheduling affects throughput and fairness.

## What to emphasize when speaking
1. DRAM is dense/cheap but timing-sensitive.
2. Refresh is fundamental to correctness.
3. Row/bank organization shapes performance.

## Short speaking script (about 1 minute)
This lecture covers DRAM internals and why main memory latency is significant.  
DRAM uses capacitor-based storage, which requires periodic refresh and structured access commands.  
Row-buffer locality and controller scheduling strongly influence real performance.  
So DRAM behavior is architectural, not just “slow RAM.”

