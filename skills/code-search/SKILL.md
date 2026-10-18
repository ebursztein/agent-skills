---
name: code-search
description: Orient in local codebases at the start of coding sessions and before refactors or complex code questions using scoped ast-grep outlines. Choose rg for exact text, ColGREP for behavioral discovery, and ast-grep for structural searches and transformations; not for web research.
---

# Local code search

## Installation and gotchas

Read [setup and troubleshooting](references/setup.md) when tools are missing,
installing this skill on another machine, checking acceleration, or updating it.
Do not install or reconfigure tools just because an ordinary code task invokes
this skill. The optional portable [cgrep helper](scripts/cgrep) supplies search
flags; platform-specific settings and their limits are documented in setup.

## Start with orientation

At the start of a coding session, and before investigating a refactor or complex
code question, read the repository's instructions and relevant project guidance,
then use a scoped outline as the first code-navigation pass before broad source
reads or implementation planning. Read the [outline subguide](references/outline.md).

Choose the smallest relevant package, directory or file; do not outline a whole
monorepo by default. If the area is unknown, use filenames or a focused ColGREP
query to find candidates, then outline them. Reuse an outline already current in
this session; refresh affected files after structural edits. Simple exact lookups,
small changes in already-understood code and non-code chats can proceed directly.
This is a working habit, not a background process or an every-turn scan.

## Choose the next tool

Choose from what is known about the target, and read only the relevant subguide.
These guides belong to this skill, not separate skill registrations.

| Need | Tool | Subguide |
| --- | --- | --- |
| Session orientation, refactor surface or complex code investigation | `ast-grep outline` | [Outline first](references/outline.md) |
| Exact string, error message, filename or simple identifier occurrence | `rg` | [Exact search](references/rg.md) |
| Find an implementation from a description of behavior | ColGREP / `cgrep` | [Semantic discovery](references/colgrep.md) |
| Syntax, relationships within code structure, repeatable syntax-based changes | `ast-grep` | [Structural search](references/ast-grep.md) |

Start with a narrow file or directory scope when the relevant area is known.
It is normal to discover candidates with ColGREP, inspect a known symbol with rg,
and refine a syntactic pattern with ast-grep. Do not run all three automatically.
Use native agent tools for reading/editing files, tests and git operations.

Search results locate candidates; inspect the relevant source before making a
behavioral claim. Do not treat syntactic matches as type-resolved references.

One canonical installation serves Codex and Claude Code. Maintain tool guidance
here; do not reinstall standalone tool skills or activate duplicate search hooks.
