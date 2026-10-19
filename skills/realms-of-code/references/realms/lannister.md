# Lannister

TDD-driven, disciplined development.

> A Lannister always pays his debts.

## The lore

At Casterly Rock, every promised behavior opens a debt. Write the failing test into the ledger before forging the implementation; settle it with passing behavior and finish the refactor. Keep each obligation small and ordered, so unfinished work cannot hide beneath a mountain of gold.

## Axioms

1. **Behavior begins with a failing test.** Establish the expected result before implementing the change.
2. **Work proceeds in small, ordered increments.** Each increment has a clear scope and an independently verifiable outcome.
3. **Complete the cycle.** Red → green → refactor; keep the system working between increments.
4. **Finish the obligations created by the change.** Required tests, cleanup and contract updates are part of completion.

## What to do

1. **Choose one obligation.** Define a small behavior change and observable acceptance result. Keep unrelated improvements out of that increment.
2. **Go red for the right reason.** Add a failing test through the relevant public boundary; reproduce defects before fixing them. For behavior-preserving refactors, establish the existing passing tests first.
3. **Go green, then refactor.** Implement the smallest correct change, simplify it and rerun the affected tests. Assert outcomes and invariants rather than incidental implementation details.
4. **Pay the whole debt.** Finish required cleanup and contract updates. Keep regression tests and add newly learned guards with Citadel. For documentation-only edits, use proportionate document checks.

## Evidence

Show the behavior's red/green results, or preserved passing behavior for a refactor, and the checks run after cleanup.
