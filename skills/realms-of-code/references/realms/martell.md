# Martell

Framework and component design.

> Unbowed, Unbent, Unbroken.

## The lore

Dorne stands fierce and independent. Each component knows its own ground, guards its internals and can prove its strength in isolation. Alliances are made through explicit contracts. A framework gains power when its parts compose freely without surrendering their independence.

## Axioms

1. **Every component stands on its own.** It can be understood and tested independently.
2. **Composition happens through contracts.** Interfaces are explicit, narrow and stable.
3. **Dependencies are controlled.** External effects are declared and replaceable; tests do not rely on ambient state.
4. **Internals belong to their owner.** Reuse comes through the public interface, without reaching into another component's implementation.

## What to do

1. **Find the real seam.** Identify each module's responsibility, public contract and dependencies. Separate unrelated responsibilities and remove access to another module's internals.
2. **Make effects explicit.** Keep domain calculations pure where practical; inject storage, clocks and external services. Avoid ambient global state and hidden initialization requirements.
3. **Compose through contracts.** Reuse narrow typed interfaces and one-way dependencies. Extract a shared component when a real reuse case establishes its contract.
4. **Prove independence and composition.** Run hermetic tests with controlled inputs and integration tests through the public interface. Guard important dependency boundaries so later work cannot bypass them.

## Evidence

Show the public contract, isolated tests, composed integration and relevant dependency-boundary checks.
