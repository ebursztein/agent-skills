---
name: realms-of-code
description: Apply the Realms of Code engineering charter when planning, implementing, refactoring, reviewing or shipping software. Route to PRD and architecture guidance, Sprinty planning, TDD, component design, testing, infrastructure, security, documentation and release evidence as the task requires. Not for unrelated chat or automatic infrastructure setup.
---

# Realms of Code

One charter, seventeen responsibilities. Each realm has a motto, four axioms and
concrete application guidance. Use the names as memorable handles; communicate
technical decisions and evidence in plain language.

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
4. Establish the relevant evidence before implementation. Apply Citadel when
   decisions or lessons need durable protection and Iron Bank when validating
   completion or release. Preserve existing gates; report checks not run honestly.
5. Use the separate `code-search` skill when available for scoped orientation and
   tool selection. Otherwise use the repository's available navigation tools.
   Native tools still own edits, testing and git.

Apply the axioms within the user's requested scope and project instructions.
They do not authorize a purchase, deployment, external load test, deletion or
multi-agent work. Documentation-only work needs proportionate document checks;
behavior changes need TDD. Reuse approved tools and services. Do not install
Sprinty, MCP servers, models or binaries simply because this skill is invoked.

## Realm guides

| Realm | Responsibility |
| --- | --- |
| [Targaryen](references/realms/targaryen.md) | Product intent and architecture |
| [Martell](references/realms/martell.md) | Framework and component design |
| [Tyrell](references/realms/tyrell.md) | Growth through simplicity |
| [Tully](references/realms/tully.md) | User experience and accessibility |
| [Arryn](references/realms/arryn.md) | Standards and interoperability |
| [Braavos](references/realms/braavos.md) | Build versus buy and dependency awareness |
| [The Free Folk](references/realms/free-folk.md) | Supply-chain engineering |
| [Baratheon](references/realms/baratheon.md) | Sprints, spikes and agile delivery |
| [Lannister](references/realms/lannister.md) | TDD-driven, disciplined development |
| [The Faceless Men](references/realms/faceless-men.md) | Test doubles and simulation |
| [Greyjoy](references/realms/greyjoy.md) | Chaos engineering and fuzzing |
| [The Dothraki](references/realms/dothraki.md) | Load and stress testing |
| [Stark](references/realms/stark.md) | Infrastructure and operational foundations |
| [The Night's Watch](references/realms/nights-watch.md) | Security and privacy |
| [The Whisper Network](references/realms/whisper-network.md) | Observability |
| [The Citadel](references/realms/citadel.md) | Documentation and executable guardrails |
| [The Iron Bank](references/realms/iron-bank.md) | CI/CD and release proof |

## Boundaries that prevent duplicated work

- Targaryen shapes the architecture; Martell makes its components independent;
  Tyrell keeps growth and composition simple.
- Baratheon organizes the work; Lannister executes verified increments; Citadel
  preserves contracts and lessons; Iron Bank collects the required release proof.
- Braavos decides whether to build or adopt and considers dependency obligations;
  Free Folk checks and maintains supply-chain trust after adoption.
- Faceless Men supplies controlled doubles; Greyjoy introduces faults and hostile
  inputs; Dothraki increases demand. They establish different kinds of evidence.
- Stark supplies operational foundations; the Whisper Network provides diagnostic
  visibility; the Night's Watch governs security and privacy, including telemetry.

## Installation and provenance

Read [setup](references/setup.md) when installing or updating this shared skill.
Read [sources](references/sources.md) for the distinction between literary
quotations and original engineering mottos. The engineering axioms are this
project's own charter, not claims about the fictional factions' behavior.
