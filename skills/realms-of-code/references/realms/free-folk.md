# The Free Folk

Supply-chain engineering.

> Choose freely. Trust deliberately.

## The lore

Beyond the Wall, independent builders create tools no single house could forge alone. Their work can strengthen the realm. The Free Folk teach us to know each ally's origin, companions and condition, and to maintain that knowledge long after the gates have opened.

## Axioms

1. **Know what enters the system.** Maintain an accurate inventory of dependencies and artifacts.
2. **Know where it came from.** Verify provenance, integrity and appropriate version constraints.
3. **Ownership continues after adoption.** Track vulnerabilities, upstream health, licenses and upgrades.
4. **Keep the supply chain lean.** Remove unused dependencies and unnecessary transitive exposure.

## What to do

1. **Inspect the dependency change.** Review manifests, lockfiles, transitive additions, install scripts and artifact origins. Prefer reproducible versions and verify available integrity/provenance evidence.
2. **Check ongoing trust.** Use the project's vulnerability and license checks; inspect upstream maintenance, security support and deprecation notices. Assess actual exposure before deciding to patch, replace or remove.
3. **Upgrade through the real contract.** Read breaking changes, apply the smallest viable upgrade and run affected integration/build checks. Do not disable a failing check to admit a dependency.
4. **Reduce exposure.** Remove unused packages and unnecessary transitive dependencies. Record unresolved risks with ownership and wire suitable existing dependency checks into CI.

## Evidence

Provide the dependency diff, maintenance/security findings and affected checks; identify unresolved exposure explicitly.
