# The Whisper Network

Observability.

> Make the important signals heard.

## The lore

The little birds follow a request through the passages of the realm. Their reports connect cause to consequence and carry the useful detail to whoever can act. A thousand unconnected whispers are noise; a trustworthy account explains what failed, where and for whom.

## Axioms

1. **Instrument meaningful behavior.** Logs, metrics and traces explain user outcomes and system state.
2. **Make events connectable.** Preserve enough context to reconstruct a workflow across boundaries.
3. **Alerts lead to action.** Define the condition, urgency, owner and useful diagnostic context.
4. **Visibility respects privacy.** Apply the Night's Watch rules to collection, access, redaction and retention.

## What to do

1. **Trace the workflow.** Identify the user outcome, important state changes and failure boundaries. Inspect existing logs, metrics and traces before adding signals.
2. **Make the story connect.** Propagate correlation identifiers and preserve useful failure reasons, with secrets removed. Choose bounded labels and sampling/retention appropriate to volume.
3. **Make alerts actionable.** Define the condition, urgency, owner and diagnostic context. Expose stale or failed sources honestly instead of reporting a healthy partial run.
4. **Verify emitted evidence.** Run a normal path and a controlled failure; follow their signals through the real collection path. Check privacy, cardinality and cost, and add a regression for critical missing/error signals.

## Evidence

Show the correlated success/failure signals and actionable alert result, including relevant privacy and volume checks.
