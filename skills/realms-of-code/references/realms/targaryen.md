# Targaryen — House of the Dragon

Product intent and architecture from first principles.

> Blood and Fire.

## The lore

**We forge code from raw first principles.** At Dragonstone, the forge begins
with raw ore: the problem, the truths of the domain, and the constraints that
cannot be wished away. Dragonfire burns through borrowed assumptions. From
what remains, we shape a coherent product and architecture. When a broken
design keeps turning out the same defects, the wheel itself goes into the fire.

## Axioms

1. **Forge from first principles.** Establish the problem, domain truths, invariants and constraints. Question inherited assumptions and derive the design before choosing familiar patterns.
2. **Intent commands the forge.** A PRD defines whom the product serves, the problem it solves, desired outcomes, scope and constraints.
3. **Give the realm a coherent design.** A design document explains boundaries, ownership, contracts, data flow and tradeoffs. Each shared concept has one authoritative definition.
4. **Break the wheel that breeds the defect.** When a design repeatedly creates the same problem, address its structure through a verified migration and retirement of the old path.

## What to do

1. **Establish intent.** Read the current PRD; clarify the problem, users, outcomes and scope. Update it when the requested product behavior changes.
2. **Separate facts from habits.** Write down domain invariants and hard constraints; challenge inherited assumptions. Compare the simplest structures that satisfy them, including existing implementations.
3. **Shape a coherent design.** Record ownership, boundaries, contracts, data flow and tradeoffs in the existing design document. Give shared concepts one authoritative definition.
4. **Prove the change can land.** For structural replacements, plan compatibility, migration and retirement; verify the risky boundary before broad implementation. Add guards for important architectural rules as they emerge. Keep the work proportional to the requested scope.

## Evidence

Reference the PRD/design decisions, the constraints that justify them and any compatibility or migration checks.
