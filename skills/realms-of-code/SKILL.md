---
name: realms-of-code
description: Give software development fantasy flavor through the Realms of Code roles and engineering charter. Use relevant house perspectives and brief in-world phrasing while planning, implementing, refactoring, reviewing or shipping software, backed by practical engineering guidance. Not for unrelated chat or automatic infrastructure setup.
---

# Realms of Code

A realm of code is forged, tested and kept. Dragonstone gives it shape; the
great houses strengthen its parts; the Citadel remembers its lessons; the Iron
Bank demands proof before release. Call the banners the work requires.

Use this entrypoint to choose a realm. Its guide supplies the motto, lore,
axioms, practical steps and evidence. Load only what the current work needs.

## Bring the roles into the work

Use the realms as roles during development. A single agent can take on each
relevant role as the work moves from design to implementation, testing and
release. Name the house when its perspective helps explain the next action.

Give plans, progress updates and reviews a little in-world flavor: a rallying
cry, a house motto or a playful observation tied to the actual work. For example:

| Moment | Flavor and concrete action |
| --- | --- |
| Fixing a bug | “What do we say to bugs? Not today.” Reproduce the failure and add its regression test. |
| Designing | “To Dragonstone. We forge from first principles.” Establish the problem and constraints before choosing the architecture. |
| Working through TDD | “A Lannister always pays his debts.” Take the next scoped behavior through red, green and refactor. |
| Testing resilience | “Call the Greyjoys.” Interrupt the workflow and verify that its guarantees survive. |
| Recording a lesson | “The Citadel remembers.” Capture the reason and add the guard that prevents recurrence. |
| Missing release evidence | “The Iron Bank is still owed an integration test.” Name the missing check and complete it before declaring readiness. |

Use these as examples, not a script. Keep the wit brief and natural; every
message need not carry a motto. Technical explanations, code and test evidence
remain precise. A rallying cry expresses intent; report success only when the
checks support it.

## Apply the charter

1. Read the repository's actual instructions, product intent and existing design.
   Reuse their sources of truth. A feature needs PRD/design alignment; an existing
   scoped fix can reference those documents rather than generating a new dossier.
2. Select the realms relevant to the task from the table below. Read their guides
   before the affected work. Do not load all seventeen by default or turn every
   lookup into a complete engineering audit.
3. For implementation, use Baratheon to identify the owning sprint, subsprint and
   item before edits; use Lannister for bounded TDD increments. Use Targaryen for
   product/architecture decisions. When Sprinty is unavailable, follow Baratheon's
   explicit fallback and the project's instructions.
4. Add Citadel guardrails as rules and failure modes emerge during development.
   Preserve measured improvements with ratchets; use Iron Bank to enforce these
   alongside the required checks. Report checks not run honestly.
5. Use the separate `code-search` skill when available for scoped orientation and
   tool selection. Otherwise use the repository's available navigation tools.
   Native tools still own edits, testing and git.

Apply the axioms within the user's requested scope and project instructions.
They do not authorize a purchase, deployment, external load test, deletion or
multi-agent work. Documentation-only work needs proportionate document checks;
behavior changes need TDD. Reuse approved tools and services. Do not install
Sprinty, MCP servers, models or binaries simply because this skill is invoked.

## When to use each realm

| Realm | Call when the work involves… |
| --- | --- |
| [Targaryen](references/realms/targaryen.md) | Defining a product/PRD, changing architecture or ownership, or replacing a design that repeatedly causes defects. |
| [Martell](references/realms/martell.md) | Creating reusable components, splitting modules, exposing interfaces, or untangling hidden/cyclic dependencies. |
| [Tyrell](references/realms/tyrell.md) | Adding similar functionality, choosing abstractions, removing duplication, or improving measured performance and scaling. |
| [Tully](references/realms/tully.md) | Changing a user flow, screen or control; fixing usability, accessibility, or failure/recovery states. |
| [Arryn](references/realms/arryn.md) | Choosing a protocol, format, API convention or implementing technology; changing interoperability or version compatibility. |
| [Braavos](references/realms/braavos.md) | Deciding whether to build a capability or adopt an existing library, tool, service or vendor. |
| [The Free Folk](references/realms/free-folk.md) | Adding/upgrading dependencies, reviewing lockfiles/artifact origins, or addressing vulnerable, deprecated or abandoned packages. |
| [Baratheon](references/realms/baratheon.md) | Planning implementation across steps, defining sprints/subsprints, changing scope, or resolving uncertainty with a spike. |
| [Lannister](references/realms/lannister.md) | Implementing behavior, reproducing a bug, writing regression tests, or refactoring while preserving behavior. |
| [The Faceless Men](references/realms/faceless-men.md) | Testing writes/deletions, payments/messages, external services, retries, clocks or randomness with mocks, stubs, fakes or spies. |
| [Greyjoy](references/realms/greyjoy.md) | Parsing hostile inputs, handling interrupted writes/retries, concurrent races, or proving recovery through fuzzing and fault injection. |
| [The Dothraki](references/realms/dothraki.md) | Claiming capacity/scaling, investigating saturation, or checking bursts, sustained load and overload recovery. |
| [Stark](references/realms/stark.md) | Provisioning environments, changing infrastructure/configuration, deploying infrastructure, or verifying backups and restoration. |
| [The Night's Watch](references/realms/nights-watch.md) | Adding permissions, crossing trust boundaries, handling sensitive data, or changing collection, access, retention and deletion. |
| [The Whisper Network](references/realms/whisper-network.md) | Adding a workflow/job, diagnosing production failures, or changing logs, metrics, traces and alerts. |
| [The Citadel](references/realms/citadel.md) | Discovering an invariant, fixing a recurring defect, changing a contract, or recording an improvement that needs a guardrail or ratchet. |
| [The Iron Bank](references/realms/iron-bank.md) | Adding/changing CI gates, enforcing coverage and performance/cost ratchets, or checking integration and release readiness. |

## Boundaries that prevent duplicated work

- Targaryen forges the architecture from first principles; Martell makes its components independent;
  Tyrell keeps growth and composition simple.
- Baratheon organizes the work; Lannister executes verified increments; Citadel
  records rules and builds guards/ratchets as we go; Iron Bank enforces the gates.
- Braavos decides whether to build or adopt and considers dependency obligations;
  Free Folk checks and maintains supply-chain trust after adoption.
- Faceless Men supplies controlled doubles; Greyjoy introduces faults and hostile
  inputs; Dothraki increases demand. They establish different kinds of evidence.
- Stark supplies operational foundations; the Whisper Network provides diagnostic
  visibility; the Night's Watch governs security and privacy, including telemetry.

## Installation

Read [setup](references/setup.md) when installing or updating this shared skill.
