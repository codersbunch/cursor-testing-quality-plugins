---
name: run-benchmark
description: Run performance benchmarks on critical code paths and generate a comparison report.
---

# Run Benchmark

Execute benchmarks and profile memory/CPU usage for critical paths.

## Steps

1. Identify critical functions to benchmark
2. Run benchmarks using appropriate tool:
   - Node.js: `autocannon`, `clinic.js`, `0x`
   - Python: `pytest-benchmark`, `cProfile`
   - Go: `go test -bench=. -benchmem`
3. Profile memory: heap snapshots before/after
4. Run load test on API endpoints
5. Compare results against baseline
6. Generate flamegraph for CPU hotspots
7. Output report to `benchmark-results.md`
