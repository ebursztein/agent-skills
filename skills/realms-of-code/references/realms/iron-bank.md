# The Iron Bank

CI/CD and release proof.

> The Iron Bank will have its due.

## The lore

The Iron Bank accepts evidence in payment. Coverage, integration and the required checks must settle against the very artifact leaving the gates. A deadline cannot erase an unpaid obligation, and a green seal from yesterday cannot guarantee today's release.

## Axioms

1. **Coverage obligations are explicit.** Define and enforce meaningful coverage requirements; coverage percentages alone do not prove correctness.
2. **Integration is required evidence.** Verify components together through their real contracts and relevant public workflows.
3. **Release gates collect the proof.** Required tests, static checks, builds and compatibility checks must pass.
4. **Proof belongs to what ships.** Validate the release candidate and its artifacts; failures remain blocking until resolved.

## What to do

1. **Read the obligations early.** Identify the repository's required tests, coverage, static checks, build and compatibility gates. Include new guards and ratchets introduced by the change.
2. **Collect meaningful proof.** Run focused checks while developing, then the required integration and workflow checks against the candidate. Exercise real contracts; line coverage alone cannot establish correctness.
3. **Enforce the ratchet.** Compare results with the recorded baseline under the same conditions. Block regressions and unexplained budget changes; do not lower coverage floors, raise cost ceilings or remove assertions to get green.
4. **Settle against what ships.** Tie evidence to the commit and artifact being released. Fix failures and rerun affected checks after changes; distinguish checks skipped from checks passed. Verify the deployed version when deployment is authorized.

## Evidence

Record the candidate/artifact, required gate results, coverage and ratchet comparisons; list any unrun checks or unresolved blockers.
