# The Citadel

Documentation and executable guardrails.

> We are this world's memory.

## The lore

Every failure leaves a lesson worth a link in a maester's chain. The Citadel records why the realm was built this way and turns remembered disasters into executable guards. A warning on a forgotten scroll cannot stop the next mistake; a living guard can.

## Axioms

1. **Record the reason.** Preserve contracts, decisions, constraints and lessons—not merely descriptions of the current code.
2. **Turn important lessons into safeguards.** A known failure earns a regression test; an architectural rule earns an appropriate guard.
3. **Every guard explains its purpose.** State the protected guarantee and the mistake it prevents.
4. **Knowledge evolves with the system.** Update documentation and guards alongside the changes that affect them.

## What to do

1. **Record the rule where it belongs.** Update the existing specification, decision record or runbook alongside the change. State the guarantee, its reason and the failure it prevents.
2. **Add the guard during development.** Encode stable rules with the smallest suitable type/schema constraint, lint rule, architecture test or regression test. A production defect gets a test at the boundary where it escaped.
3. **Prove the guard works.** Exercise a representative violation and a valid case. Check actual behavior or dependency boundaries rather than matching source wording.
4. **Ratchet measured progress.** Capture a reproducible baseline for a relevant metric: coverage floors, query-count ceilings, bundle size, latency or warnings. Reject regressions; tighten the bound after verified improvement. Use stable fixtures and meaningful tolerances for noisy measurements.
5. **Wire it into routine checks.** Run the guard locally and in the existing CI gates. Preserve the explanation beside it. Never silently weaken a threshold to pass a change; an intentional tradeoff needs an explicit decision and reviewed baseline update.

## Evidence

Link each important rule to its guard; record a rejected violation, accepted valid case and any baseline with its non-regression check.
