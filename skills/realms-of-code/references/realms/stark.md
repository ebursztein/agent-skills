# Stark

Infrastructure and operational foundations.

> Winter is Coming.

## The lore

Winterfell prepares while the roads are still clear. Its foundations are written, its stores accounted for, and its restoration rehearsed. Infrastructure must be reproducible from declared plans, so the realm can rebuild when memory, machines or weather fail it.

## Axioms

1. **Infrastructure is declared.** Provision and configure environments through versioned, reviewable definitions.
2. **Rebuilding is a capability.** A clean environment can be recreated from its declared inputs.
3. **Preparation precedes emergency.** Establish capacity, backups, restoration procedures and operational ownership.
4. **Readiness requires rehearsal.** Verify restoration and essential operational procedures before relying on them.

## What to do

1. **Inspect declared infrastructure.** Read the versioned provisioning/configuration and its deployment target. Compare the proposed plan with the existing environment and identify persistent data at risk.
2. **Make provisioning repeatable.** Reuse the project's infrastructure-as-code tools and explicit inputs. Verify a clean isolated environment can be created without undocumented manual steps.
3. **Rehearse recovery.** Restore a representative backup into a disposable target and check usable data. Exercise required rollback/rebuild procedures without overwriting the source.
4. **Record readiness.** Keep configuration, operational ownership and restore instructions current. Add checks for meaningful drift and maintain measured capacity/headroom requirements.

## Evidence

Keep the infrastructure plan/diff, clean-environment result and restoration verification against the intended target.
