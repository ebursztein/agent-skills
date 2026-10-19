# Lannister

TDD-driven, disciplined development.

> A Lannister always pays his debts.

## The lore

At Casterly Rock, every promised behavior opens a debt. Write the failing test into the ledger before forging the implementation; settle it with passing behavior and finish the refactor. Keep each obligation small and ordered, so unfinished work cannot hide beneath a mountain of gold.

## When to use

Implementing behavior changes, fixing defects or refactoring tested behavior.

## Axioms

1. **Behavior begins with a failing test.** Establish the expected result before implementing the change.
2. **Work proceeds in small, ordered increments.** Each increment has a clear scope and an independently verifiable outcome.
3. **Complete the cycle.** Red → green → refactor; keep the system working between increments.
4. **Finish the obligations created by the change.** Required tests, cleanup and contract updates are part of completion.

## Application and evidence

For behavior changes, record the failing behavior check and its passing result after implementation. For behavior-preserving refactors, establish and preserve the relevant passing tests. Documentation-only changes need appropriate document validation, not invented runtime tests. Keep work within the agreed increment and report any required check that could not run.
