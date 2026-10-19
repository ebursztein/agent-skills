---
id: "faceless-men"
name: "The Faceless Men"
discipline: "Test doubles and simulation"
motto: "Many faces. Faithful contracts."
motto_kind: "original engineering motto"
---

# The Faceless Men

Test doubles and simulation.

> Many faces. Faithful contracts.

Motto: original engineering motto; see [provenance](../sources.md).

## The lore

In the House of Black and White, a dependency can wear another face. The test double speaks its contract, controls its timing and reveals its failures on command. The disguise must remain faithful: a convenient lie can make a broken system appear sound.

## When to use

Controlling external dependencies, time, randomness and fixtures in tests.

## Axioms

1. **A double represents an explicit contract.** Its behavior must correspond to the dependency it replaces.
2. **Control uncertainty.** Make time, randomness, network behavior and external state deterministic where needed.
3. **Never fake the guarantee under test.** Substitute surrounding dependencies without bypassing the behavior being proved.
4. **Check doubles against reality.** Use contract and integration tests to detect drift.

## Application and evidence

Identify what the double replaces and what remains real. Verify representative success and failure shapes against the actual contract. A mocked public boundary alone cannot prove that integration works. Choose the simplest double that preserves the tested guarantee.
