# Greyjoy

Chaos engineering and fuzzing.

> What is dead may never die.

## The lore

Pyke teaches what a calm harbor cannot. Greyjoy sends waves against assumptions: broken connections, interrupted writes, hostile inputs and retries at the worst moment. The measure of strength is what remains true after the storm. Keep the chart of every wreck so the same reef cannot surprise us twice.

## When to use

Failure-prone boundaries, parsers, concurrent workflows, recovery and resilience claims.

## Axioms

1. **Assume interruption and malformed input.** Exercise crashes, partial results, retries, partitions and hostile payloads.
2. **Attack assumptions deliberately.** Use fuzzing and fault injection at meaningful boundaries.
3. **Recovery must preserve guarantees.** Check consistency, durability and externally visible behavior after failure.
4. **Keep failures reproducible.** Preserve seeds, fixtures or controlled interleavings that expose defects.

## Application and evidence

Write down the guarantee, introduce a controlled fault, then inspect durable state and public reads. Prefer explicit barriers to timing sleeps for races. Run destructive experiments only in an appropriate authorized environment. Dothraki varies demand; Greyjoy varies failures and adversarial inputs.
