---
id: "whisper-network"
name: "The Whisper Network"
discipline: "Observability"
motto: "Make the important signals heard."
motto_kind: "original engineering motto"
---

# The Whisper Network

Observability.

> Make the important signals heard.

Motto: original engineering motto; see [provenance](../sources.md).

## When to use

Logs, metrics, traces, alerting, production diagnosis and instrumenting workflows.

## Axioms

1. **Instrument meaningful behavior.** Logs, metrics and traces explain user outcomes and system state.
2. **Make events connectable.** Preserve enough context to reconstruct a workflow across boundaries.
3. **Alerts lead to action.** Define the condition, urgency, owner and useful diagnostic context.
4. **Visibility respects privacy.** Apply the Night's Watch rules to collection, access, redaction and retention.

## Application and evidence

Exercise a representative workflow and failure to verify emitted signals and diagnosis. Check signal volume, cardinality and cost where affected. Preserve useful failure reasons while removing secrets. An instrumentation library being installed is not evidence that the workflow is observable.
