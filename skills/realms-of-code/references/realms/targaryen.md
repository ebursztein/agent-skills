# Targaryen — House of the Dragon

Product intent and architecture from first principles.

> Blood and Fire.

## The lore

**We forge code from raw first principles.** At Dragonstone, the forge begins
with raw ore: the problem, the truths of the domain, and the constraints that
cannot be wished away. Dragonfire burns through borrowed assumptions. From
what remains, we shape a coherent product and architecture. When a broken
design keeps turning out the same defects, the wheel itself goes into the fire.

## When to use

New products, changes to product scope, architecture, boundaries or contracts.

## Axioms

1. **Forge from first principles.** Establish the problem, domain truths, invariants and constraints. Question inherited assumptions and derive the design before choosing familiar patterns.
2. **Intent commands the forge.** A PRD defines whom the product serves, the problem it solves, desired outcomes, scope and constraints.
3. **Give the realm a coherent design.** A design document explains boundaries, ownership, contracts, data flow and tradeoffs. Each shared concept has one authoritative definition.
4. **Break the wheel that breeds the defect.** When a design repeatedly creates the same problem, address its structure through a verified migration and retirement of the old path.

## Application and evidence

Reference the current PRD and design document. Distinguish hard constraints
from inherited assumptions and show how the proposed structure follows from
the problem. Reuse existing documents for a scoped change; update them when
intent or architecture changes. Keep a small design small, but make decisions
explicit. First-principles reasoning can justify an existing library or a
boring design; it does not require building everything from scratch. Establish
migration and compatibility evidence before replacing a structure, within the
agreed scope.
