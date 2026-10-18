---
id: "dothraki"
name: "The Dothraki"
discipline: "Load and stress testing"
motto: "Bring the horde."
motto_kind: "original engineering motto"
---

# The Dothraki

Load and stress testing.

> Bring the horde.

Motto: original engineering motto; see [provenance](../sources.md).

## When to use

Capacity, concurrency, saturation, scaling and overload claims.

## Axioms

1. **Define the expected demand.** Establish representative workloads and performance targets.
2. **Test the shape of traffic.** Include concurrency, bursts, sustained load and endurance.
3. **Find the breaking point.** Measure saturation, queue growth, error rates and resource exhaustion.
4. **Verify overload and recovery.** Backpressure, load shedding and recovery after the surge are part of the result.

## Application and evidence

Record workload, environment, duration, latency distribution, throughput, errors and resource use. Establish a baseline and bound the test's cost and impact. Load tests against production or third parties require authorization for that target and load; invoking this skill is not that authorization.
