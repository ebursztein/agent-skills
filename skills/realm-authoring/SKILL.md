---
name: realm-authoring
description: Write or improve Realms of Code realm guides with practical triggers, concrete actions, evidence and fantasy flavor. Use when authoring the charter itself, not when applying its roles to ordinary software work.
---

# Realm authoring

A realm tells an agent when it is on duty, what to do next, and how to know it
worked. Give that discipline a memorable house voice.

## Before writing

Read the target guide and the charter's trigger table. Preserve the
agreed house assignment and distinguish it from neighboring realms. Work from
real development situations the user wants handled. Name recognizable techniques:
“mocks, stubs and fakes” helps discovery more than “controlled doubles” alone.

## Put selection in the main skill

The main realms-of-code SKILL.md owns **when to use each realm**. Its table
must let an agent choose before loading a guide. Use concrete situations:
testing file deletion, selecting an API standard, or protecting a query-count
improvement. Keep triggers there once, rather than repeating them in each guide.

## Put best practices in the realm guide

- **Name, discipline, motto:** a heading, one concrete scope line and the motto.
- **The lore:** a short, vivid paragraph connecting the faction to its engineering
  role. Make the metaphor explain the work.
- **Axioms:** a few compact principles that guide decisions. Preserve established
  commitments when revising an existing realm.
- **What to do:** practical steps starting with verbs. Identify what to inspect
  or change, how to choose an approach, and what to verify. Use explicit technique
  names and reuse the project's tools. Explain meaningful alternatives and traps.
- **Evidence:** the observable result or artifact that supports completion, plus
  any important limit on what that evidence proves.

Axioms explain the judgment; steps make it executable. Avoid repeating the same
advice in both. Keep each section as short as its job permits. Realm reference
files are plain Markdown: no IDs, duplicate YAML fields, motto-origin labels or
attribution chatter. Only a discoverable SKILL.md needs skill frontmatter.

## Worked correction

For Faceless Men, “controlling dependencies” is too abstract. A useful trigger is
“testing a job that deletes files or calls an external payment service.” The next
action is to isolate that boundary, choose a mock/stub/fake, and exercise success,
failure and retry behavior without unintended live effects. Evidence includes the
intended target and resulting state, plus integration proof where the real
contract matters. A spy that still calls the live service is a trap worth naming.

When the companion realms-of-code skill is available, its
`references/realms/faceless-men.md` is the full worked example.

For Arryn, “choosing protocols” belongs in the main trigger table. Its guide
must say to find existing standards and technology, verify current maintenance
and deprecation status, assess viability, reuse the supported implementation
and test interoperability.

Teach protection during implementation: encode important rules as guardrails
and verified improvements as ratchets. A ratchet records a reproducible baseline,
rejects regressions and tightens after improvement. Citadel builds the protection;
Iron Bank enforces it. Never solve a failing check by silently weakening it.

## Review before publishing

Try two realistic matching tasks and one nearby task belonging to another realm.
Choose the realm from the main table, then identify the first concrete action
and required evidence from its guide. If either step remains ambiguous, revise
the responsible file. Avoid blanket gates unrelated to the task.

Keep the flavor alive in a motto, lore and occasional working phrase such as
“What do we say to bugs? Not today.” Pair it with useful engineering guidance.
Remove words that add neither a decision nor character. Follow the repository's
publication workflow and verify relative links and skill discovery when affected.
