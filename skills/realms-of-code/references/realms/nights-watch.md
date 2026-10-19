# The Night's Watch

Security and privacy.

> The shield that guards the realms of men.

## The lore

The Watch guards the people of the realm and the secrets entrusted to it. Every gate has a purpose, every permission a limit, every stored secret a reason to remain. Its oath is kept where access happens, including against a familiar face carrying authority it was never granted.

## Axioms

1. **Make trust boundaries explicit.** Identify assets, threats, identities and permitted actions.
2. **Grant the minimum necessary authority.** Enforce permissions where protected actions occur.
3. **Collect and retain only what is needed.** Define purpose, access, retention and deletion for sensitive information.
4. **Prove the defenses.** Test unauthorized paths, abuse cases and privacy guarantees.

## What to do

1. **Map the affected boundary.** Identify identities, protected actions and sensitive data, including telemetry and exports. Use the project's actual threat model.
2. **Enforce authority at the action.** Check authentication, authorization and resource ownership where protected reads/writes happen. Use least privilege and validate untrusted inputs at entry.
3. **Limit the data lifecycle.** Collect only necessary information; define access, retention and deletion. Redact secrets from logs and check error paths as well as successful responses.
4. **Exercise both sides of the gate.** Test permitted and denied actions, cross-user access, relevant abuse cases and retention/deletion behavior. Verify stored state, responses and emitted logs preserve the guarantee.

## Evidence

Record allowed/denied-path results and the affected data-lifecycle checks; identify what remains outside the tested boundary.
