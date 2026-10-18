# Use ast-grep outline

`ast-grep outline` prints a compact structural map of source code with line
numbers: top-level **items** (imports, functions, classes, structs,
interfaces, modules, enums) and their direct **members** (fields, methods,
constructors, enum variants). It is a local, syntax-only view — cheap enough
to run before any full file read.

Read code in stages: find candidate files with search or file names, outline
them, then open only the source range the outline points to. Defaults adapt to
input: a file shows its local structure with member digests; a directory shows
only its exported surface as grouped names.

## When To Use It

**Understand a file before editing.** Get a table of contents, dependencies,
and public entry points before reading implementation details:

```shell
ast-grep outline <file>
ast-grep outline <file> --items imports
ast-grep outline <file> --items exports
```

**Map an unfamiliar directory.** Scan the public surface of a subtree, then
narrow by symbol type when you know what you are looking for:

```shell
ast-grep outline <dir> --items exports
ast-grep outline <dir> --type struct,enum,function
```

**Zoom into a known symbol.** After search finds a likely name, list its
members with line numbers instead of reading the whole body:

```shell
ast-grep outline <file> --match <symbol> --type class --view expanded
```

**Trace dependency direction.** Find which files import a package or module to
decide where a change belongs:

```shell
ast-grep outline <dir> --items imports --view signatures
```

**Review changed files after editing.** Git tells you what changed; outline
summarizes the resulting structure and public surface:

```shell
ast-grep outline "path/to/changed-file.ts" --items exports
```

## Argument Guide

- `--items <KIND>` selects top-level items: `structure` for local declarations
  (file default), `exports` for public API (directory default), `imports` for
  dependencies, `all` when import/export edges matter together.
- `--view <VIEW>` controls detail, from least to most: `names` for directory
  scans, `signatures` for one line per item, `digest` for signatures plus
  member names, `expanded` for one line per member with its line number.
- `--match <REGEX>` filters top-level items by name or signature. Rust regex,
  case-sensitive; it never matches members.
- `--type <TYPE[,TYPE...]>` keeps only some top-level symbol types, such as
  `--type class,function`. Member types like `method,field` never match
  top-level items.
- `--pub-members` hides private members when the view prints members.
- `--json=stream` emits one JSON object per file with precise ranges. Use it
  only to pipe or post-process entries; prefer text for navigation.

## Limits

`outline` shows local syntax structure. It does not resolve references, infer
types, follow re-export chains, or build a call graph. Use `ast-grep run`,
`rg`, or compiler-backed tools for those questions, then outline the candidate
files they surface.

## Local workflow notes

Use an explicit language when useful, for example:

```bash
ast-grep outline ./src --lang typescript --items exports --view names
ast-grep outline ./src/parser.ts --lang typescript --view signatures
```

Keep the first map compact. Expand only candidate files/symbols, then read their
implementation before drawing behavioral conclusions. Import entries show local
syntax, not resolved dependency edges. When a map is empty or incomplete, check
language/extractor support, scope and ignore rules; use rg or direct reads where
outline does not cover the source. Do not infer that missing entries mean no code.

Adapted from the maintainers' `ast-grep-outline` skill:
https://github.com/ast-grep/agent-skill/blob/main/ast-grep/skills/outline/SKILL.md
Source commit: `f2175aff21f20cfb8e2db30c28febeb3a2d42b61`. Kept as an on-demand
subguide so Codex and Claude share a single `code-search` registration.
