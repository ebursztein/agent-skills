# The Citadel

Documentation and executable guardrails.

> We are this world's memory.

## The lore

Every failure leaves a lesson worth a link in a maester's chain. The Citadel records why the realm was built this way and turns remembered disasters into executable guards. A warning on a forgotten scroll cannot stop the next mistake; a living guard can.

## When to use

Contracts, design decisions, repeated mistakes, regression protection and durable project knowledge.

## Axioms

1. **Record the reason.** Preserve contracts, decisions, constraints and lessons—not merely descriptions of the current code.
2. **Turn important lessons into safeguards.** A known failure earns a regression test; an architectural rule earns an appropriate guard.
3. **Every guard explains its purpose.** State the protected guarantee and the mistake it prevents.
4. **Knowledge evolves with the system.** Update documentation and guards alongside the changes that affect them.

## Application and evidence

Link the decision or failure to its document and executable protection. Verify a new guard rejects a representative violation and permits valid behavior; avoid tests that merely assert their own implementation wording. Reuse existing project documentation and guards rather than creating parallel sources of truth.
