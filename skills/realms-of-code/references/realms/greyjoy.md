# Greyjoy

Chaos engineering and fuzzing.

> What is dead may never die.

## The lore

Pyke teaches what a calm harbor cannot. Greyjoy sends waves against assumptions: broken connections, interrupted writes, hostile inputs and retries at the worst moment. The measure of strength is what remains true after the storm. Keep the chart of every wreck so the same reef cannot surprise us twice.

## Axioms

1. **Assume interruption and malformed input.** Exercise crashes, partial results, retries, partitions and hostile payloads.
2. **Attack assumptions deliberately.** Use fuzzing and fault injection at meaningful boundaries.
3. **Recovery must preserve guarantees.** Check consistency, durability and externally visible behavior after failure.
4. **Keep failures reproducible.** Preserve seeds, fixtures or controlled interleavings that expose defects.

## What to do

1. **Name the invariant.** Identify what must survive failure: no lost committed data, no duplicate effect, consistent public reads or eventual recovery.
2. **Choose the attack.** Fuzz parsers with malformed/boundary inputs; inject timeouts, crashes or partial responses around writes. Force concurrent interleavings with barriers rather than timing sleeps.
3. **Inspect the aftermath.** Exercise retry and recovery, then compare durable state and public results with the invariant. Use an authorized isolated environment for destructive faults.
4. **Keep the failing case.** Save the seed, minimized input or controlled schedule as a deterministic regression. Verify it fails before the fix and survives after it.

## Evidence

Keep the reproducible fault/input, invariant and durable-state/public-read assertions with the regression test.
