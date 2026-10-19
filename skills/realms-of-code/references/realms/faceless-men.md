# The Faceless Men

Mocking, stubbing, fakes, spies and service simulation.

> Many faces. Faithful contracts.

## The lore

In the House of Black and White, a dependency can wear another face. The test double speaks its contract, controls its timing and reveals its failures on command. The disguise must remain faithful: a convenient lie can make a broken system appear sound.

## Axioms

1. **A double represents an explicit contract.** Its behavior must correspond to the dependency it replaces.
2. **Control uncertainty.** Make time, randomness, network behavior and external state deterministic where needed.
3. **Never fake the guarantee under test.** Substitute surrounding dependencies without bypassing the behavior being proved.
4. **Check doubles against reality.** Use contract and integration tests to detect drift.

## What to do

1. **Isolate the effects.** Inject the service, storage, clock or random source at its boundary. Use disposable databases, temporary directories or sandbox endpoints for real writes; substitute calls that would affect live systems. Keep the application logic under test real.
2. **Choose the right face.** Use a **stub** for canned responses, a **fake** for a small working implementation, a **mock** for expected interactions, and a **spy** to observe calls. Reuse the project's testing tools. A spy may still run the original function: replace its implementation when the real call would cause an unwanted effect.
3. **Script the relevant outcomes.** Supply realistic success, error and timeout responses. For retries, model sequences such as failure then success. Control time instead of sleeping; reset doubles and fixtures between tests.
4. **Assert the guarantee.** Check returned results and resulting state. For consequential calls, verify their payload, destination and count, including no call when validation fails and no duplicate effect on retry. Avoid assertions about incidental internal call order.
5. **Check the real boundary.** Use contract or integration tests against an appropriate sandbox or local service to catch drift. Prove transactions, constraints and rollback with a real disposable database when those are the guarantee; a fake database cannot establish them.

## Evidence

Show what was replaced, what stayed real, and the passing success/failure checks.
For an external write, include evidence that retries cannot duplicate the effect.
For destructive behavior, verify the intended target and preserved data. A
passing mock test alone does not establish that the real integration works.
