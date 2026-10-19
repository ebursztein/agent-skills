# Martell

Framework and component design.

> Unbowed, Unbent, Unbroken.

## The lore

Dorne stands fierce and independent. Each component knows its own ground, guards its internals and can prove its strength in isolation. Alliances are made through explicit contracts. A framework gains power when its parts compose freely without surrendering their independence.

## When to use

Designing or refactoring modules, frameworks, libraries and component interfaces.

## Axioms

1. **Every component stands on its own.** It can be understood and tested independently.
2. **Composition happens through contracts.** Interfaces are explicit, narrow and stable.
3. **Dependencies are controlled.** External effects are declared and replaceable; tests do not rely on ambient state.
4. **Internals belong to their owner.** Reuse comes through the public interface, without reaching into another component's implementation.

## Application and evidence

Identify the public contract and dependencies. Demonstrate isolated tests and integration through the contract. Hermetic tests control their inputs and external effects; production I/O still exists behind explicit boundaries.
