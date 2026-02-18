---
name: memory-profiler
description: Identify memory leaks, excessive allocations, and inefficient data structures in application code.
---

# Memory Profiler

## When to use

- When application memory grows over time
- After reports of OOM crashes
- During load testing analysis
- When reviewing long-running process code

## Instructions

1. **Detect memory leaks**
   - Event listeners not removed on cleanup
   - Closures holding large object references
   - Caches without eviction policies (unbounded Maps/Sets)
   - Timers/intervals not cleared
   - Circular references preventing GC

2. **Find excessive allocations**
   - Large objects created in hot loops
   - String concatenation in loops (use array join)
   - Unnecessary array copies (spread in loops)
   - Redundant object cloning

3. **Review data structures**
   - Array used where Set/Map is more efficient
   - Storing full objects when only IDs needed
   - Duplicate data across multiple caches

4. **Node.js specific**
   - Buffer leaks
   - Stream not properly closed
   - `require()` cache misuse

## Output

- Memory leak locations with explanation
- Estimated memory impact
- Fixed code with proper cleanup
- Recommended data structure changes
