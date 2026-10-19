# The Dothraki

Load and stress testing.

> Bring the horde.

## The lore

One rider proves the gate opens. The horde reveals whether the realm can feed, shelter and withstand thousands arriving together. The Dothraki bring sustained demand, sudden surges and the pressure of exhaustion. After the dust settles, the realm must recover its strength.

## Axioms

1. **Define the expected demand.** Establish representative workloads and performance targets.
2. **Test the shape of traffic.** Include concurrency, bursts, sustained load and endurance.
3. **Find the breaking point.** Measure saturation, queue growth, error rates and resource exhaustion.
4. **Verify overload and recovery.** Backpressure, load shedding and recovery after the surge are part of the result.

## What to do

1. **Define the workload.** Pick representative operations, data size, concurrency and latency/error targets. Record the environment and a baseline before changing capacity.
2. **Increase pressure deliberately.** Exercise normal traffic, bursts and sustained load; add endurance runs when leaks or accumulation are plausible. Bound duration, spend and target impact.
3. **Measure the bottleneck.** Capture throughput, latency percentiles, errors, queues and resource use together. Check results for correctness so dropped work cannot masquerade as higher throughput.
4. **Verify recovery.** Check backpressure, shedding and drain/recovery after overload. Keep stable representative benchmarks as regression budgets. Production or third-party load requires authorization for that target and load.

## Evidence

Report workload/environment, baseline comparison, latency/throughput/errors and recovery results together.
