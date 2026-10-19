# The Iron Bank

CI/CD and release proof.

> The Iron Bank will have its due.

## The lore

The Iron Bank accepts evidence in payment. Coverage, integration and the required checks must settle against the very artifact leaving the gates. A deadline cannot erase an unpaid obligation, and a green seal from yesterday cannot guarantee today's release.

## When to use

Validation planning, integration verification, release preparation and shipping decisions.

## Axioms

1. **Coverage obligations are explicit.** Define and enforce meaningful coverage requirements; coverage percentages alone do not prove correctness.
2. **Integration is required evidence.** Verify components together through their real contracts and relevant public workflows.
3. **Release gates collect the proof.** Required tests, static checks, builds and compatibility checks must pass.
4. **Proof belongs to what ships.** Validate the release candidate and its artifacts; failures remain blocking until resolved.

## Application and evidence

Use the repository's declared gates and coverage thresholds; do not invent a universal percentage or lower a budget to make a change pass. Record integration and important workflow evidence alongside unit coverage. Distinguish a focused check from complete release validation. Shipping still requires the authorization applicable to that repository and environment.
