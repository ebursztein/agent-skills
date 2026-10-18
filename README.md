# Agent skills

Reusable skills for Codex and Claude Code. Start with one shared local code-search
workflow: outline the relevant code, then choose the tool that fits the question.

## Install code-search

```bash
DO_NOT_TRACK=1 npx skills add ebursztein/agent-skills \
  --skill code-search --agent codex claude-code --global
```

Inspect available skills without installing:

```bash
DO_NOT_TRACK=1 npx skills add ebursztein/agent-skills --list
```

The installer installs agent guidance and the bundled optional helper. It does
not install tool binaries, download embedding models, change global agent
instructions, or enable a background service. `DO_NOT_TRACK=1` disables installer
telemetry.

## The code-search workflow

| Need | Tool |
| --- | --- |
| Orient in an unfamiliar area before a refactor or complex question | Scoped `ast-grep outline` |
| Exact strings, errors, filenames and known identifiers | `rg` |
| Find implementations from descriptions of behavior | ColGREP |
| Structural patterns and repeatable syntax-based transformations | `ast-grep` |

One discoverable skill routes to supporting guides as needed. No extra MCP server,
indexer, memory service, command-rewriting hook or search-planning model is needed.
Ordinary editing, testing and git operations stay with the coding agent's native
tools. Simple known lookups do not need an outline first.

Read the [skill](skills/code-search/SKILL.md) and its
[installation and troubleshooting guide](skills/code-search/references/setup.md)
for binary installation, optional `cgrep` setup, agent instruction pointers,
platform differences and validation. Restart or open fresh agent chats to refresh
cached skill discovery after installation.

### Apple Silicon

The guide documents the configuration tested with ColGREP 1.8.5: one parallel
session, FP32, batch size 1 and static batching. CoreML availability alone does
not prove that every operator runs on the GPU. Observed execution included Metal,
Apple Accelerate and ONNX CPU kernels; Neural Engine execution was not established.
Check the guide before copying GPU flags to another platform or version.

ColGREP indexing and inference run locally after model/runtime downloads. The
coding agent's own provider connection is separate. No source code or indices
are included in this repository.

## Updates

```bash
DO_NOT_TRACK=1 npx skills update code-search --global
```

Update tool binaries separately and recheck their actual flags and backend
behavior. Avoid re-enabling duplicate per-tool skills or hooks alongside this
consolidated workflow.

## License and attribution

Original material is available under the [MIT license](LICENSE). Bundled and
adapted ast-grep guides retain their upstream provenance in
[sources.md](skills/code-search/references/sources.md) and
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Tool binaries and models are
separate projects and are not redistributed here.
