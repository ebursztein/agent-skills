# Installation, portability and gotchas

## Scope and versions

This package contains agent guidance and an optional POSIX helper; binaries,
models and indices are installed separately. Only install/reconfigure them when
requested or already authorized. Normal code search needs no server, watcher,
MCP registration, memory system or extra search-planning model.

Verified on 2026-10-18: ripgrep 15.2.0, ast-grep 0.51.0 and ColGREP 1.8.5 on
Apple Silicon. Check `--help` on other releases. Outline is experimental and
requires a version that supports `ast-grep outline`; check its actual flags rather
than assuming every older binary or language extractor supports this guide.

## Install the tools

### Homebrew (macOS or supported Linux hosts)

```bash
brew install ripgrep ast-grep lightonai/tap/colgrep
rg --version
ast-grep --version
ast-grep outline --help
colgrep --version
colgrep init --help
colgrep settings --help
```

Use the official ColGREP tap for its released binaries. Leave out the optional
`--install-agent` step shown in some upstream quick starts: it downloads a second
2B planning model, which this workflow does not need.

For other platforms use the maintainers' installation instructions:

- [ripgrep](https://github.com/BurntSushi/ripgrep#installation)
- [ast-grep](https://ast-grep.github.io/guide/quick-start.html)
- [ColGREP](https://github.com/lightonai/next-plaid/tree/main/colgrep#installation)

### Select a real supported backend

ColGREP 1.8.5's release/build configuration distinguishes these cases:

| Host/build | Backend guidance |
| --- | --- |
| Official Apple Silicon macOS binary | CoreML embeddings and Apple Accelerate vector math are compiled in. Use the Apple recipe below, then verify runtime execution. |
| Official Intel macOS binary | Apple Accelerate is compiled in; do not assume it has the arm64 CoreML build features. |
| Pre-built Linux/Windows binary | CPU inference. Do not copy Apple `--force-gpu` commands blindly. |
| Custom accelerated Linux/Windows build | Follow upstream feature/runtime requirements (CUDA, TensorRT or DirectML as supported). Confirm initialization before selecting `--force-gpu`. |

Upstream documents Cargo features such as `cuda`, `directml`, `openblas`, and
`accelerate,coreml`. A feature name is not proof that the required driver/runtime
exists or that every operation will use it. Keep custom builds out of routine
setup unless the host actually needs them.

### Verified Apple Silicon recipe

```bash
colgrep settings --parallel 1 --batch-size 1 --fp32
# Run from the target repository root:
colgrep init --force-gpu --static-batch -y .
colgrep search --force-gpu --static-batch -k 8 "a behavior in this repository"
```

These are persistent user settings shared across repositories. They are a verified
working configuration, not a universal optimum. One session avoids duplicating
CoreML model sessions. In our 1.8.5 test, FP32 with dynamic batching failed a CoreML
prediction; FP32, batch size 1 and `--static-batch` completed indexing. Keep static
batching on automatic search updates too, not only the initial `init` command.

On CPU-only builds, retain the build's precision default initially and use
`--force-cpu` for explicit CPU operation. Tune session/batch settings only from
measurements on that host; do not apply Apple-specific settings as a global rule.

## Install this one shared skill for both agents

Install directly from the published repository:

```bash
DO_NOT_TRACK=1 npx skills add ebursztein/agent-skills \
  --skill code-search --agent codex claude-code --global
```

This installs the skill resources; install binaries separately as above. Preserve
existing agent instructions when adding the pointer below. For manual/offline
installation, use the complete directory as follows.

Copy the complete `code-search` directory, including `references/` and `scripts/`,
into `~/.agents/skills/code-search`. A relative reference only works when those
files travel with SKILL.md. Example for a new installation from an unpacked copy:

```bash
# Set this to the directory containing the supplied SKILL.md:
skill_source="/path/to/unpacked/code-search"
test -f "$skill_source/SKILL.md" || exit 1
test ! -e "$HOME/.agents/skills/code-search" || exit 1
test ! -L "$HOME/.agents/skills/code-search" || exit 1
mkdir -p "$HOME/.agents/skills" "$HOME/.claude/skills"
cp -R "$skill_source" "$HOME/.agents/skills/code-search"
ln -s ../../.agents/skills/code-search "$HOME/.claude/skills/code-search"
```

Inspect existing directories/symlinks first. Update an existing installation in
place deliberately; do not create a second nested copy or overwrite other skills.
Codex reads the canonical user-wide skill. Claude Code follows the link to the same
content. Native Windows users can copy the same complete folder to their agents'
supported user skill locations when symlinks are unavailable; keep the copies in
sync and use full CLI commands instead of the POSIX helper.

Add a short pointer to the existing global `~/.codex/AGENTS.md` and
`~/.claude/CLAUDE.md`, preserving their other instructions:

> At coding-session start and before refactors or complex code questions, read
> the shared code-search skill at ~/.agents/skills/code-search/SKILL.md. Follow its
> scoped outline-first workflow and tool selection; reuse current maps.

Resolve `~` to the user's home when opening a file through a tool that does not
expand shell syntax. Start fresh chats to refresh cached skill lists. No startup
or command-rewriting hook is needed. Avoid also registering standalone ast-grep,
ast-grep-outline or ColGREP skills/plugins for the same policy. If an existing
plugin supplies duplicate guidance/hooks, disable only that registration after
preserving its configuration; keep the underlying binary.

### Optional cgrep command

Use full `colgrep` commands, or install the bundled helper without hardcoding a
Homebrew prefix:

```bash
chmod +x "$HOME/.agents/skills/code-search/scripts/cgrep"
mkdir -p "$HOME/.local/bin"
# This intentionally refuses to replace an existing command; inspect it first.
ln -s "$HOME/.agents/skills/code-search/scripts/cgrep" "$HOME/.local/bin/cgrep"
export PATH="$HOME/.local/bin:$PATH"
```

Ensure the agent's noninteractive shell inherits that PATH; changing only an
interactive alias or shell rc file may not affect GUI-launched agents. Test using
`sh -c 'command -v rg; command -v ast-grep; command -v colgrep; command -v cgrep'`.
The helper respects `--force-cpu`, `--force-gpu` and backend environment overrides;
`cgrep --force-cpu "question"` is the explicit CPU alternative on an Apple host.
It does not change model settings, install binaries or initialize a background job.

## Gotchas and diagnosis

### Hardware acceleration is mixed execution

- CoreML availability and successful provider initialization are different checks.
- ColGREP's printed `ONNX ... (CPU)` banner can describe its downloaded runtime
  artifact while CoreML subgraphs still execute. Conversely, `--force-gpu` is not
  a guarantee that all graph operators run on Metal.
- Our process samples showed CoreML prediction -> Espresso MPSEngine -> AGX Metal
  compute/command submission, plus Apple vDSP routines and ONNX CPU MLAS kernels.
  Neural Engine execution was not established. CPU activity alone does not prove
  an unwanted fallback; unsupported operators may still require CPU work.
- On macOS, inspect a live indexing process using `pgrep -fl colgrep`, then
  `sample <PID> 3 -file /tmp/colgrep-sample.txt`. Look for executing prediction/
  compute stacks, not merely loaded library names. Record limitations honestly.
- A CoreML prediction failure on the tested release was fixed by static single-item
  FP32 batching. Do not silently claim acceleration after switching to CPU-only.

### Environment, cache and first-run costs

- First use downloads model weights and may download ONNX Runtime, then compiles
  CoreML shapes. Separate download/compile/index timings from steady search latency.
- ColGREP stores user configuration, indices and model caches outside the checkout.
  On the tested Mac, config/indices live under `~/Library/Application Support/colgrep`
  and compiled CoreML models under `~/Library/Caches/next-plaid/coreml`.
  Use installed-version diagnostics to locate paths on other platforms.
- A constrained agent sandbox may allow reading those paths while blocking index or
  model-cache writes. Allow the required resolved paths through that agent's normal
  configuration; do not mistake a blocked/degraded read for semantic search success.
- Conflicting `FORCE_CPU`/`FORCE_GPU`, `COLGREP_FORCE_*` or `NEXT_PLAID_FORCE_*`
  environment settings can override defaults or fail initialization. Inspect them
  when behavior differs between terminal and agent. The helper preserves overrides.
- Ordinary CLI indexing/inference operates locally; hosted API integrations are a
  separate choice. Validate with networking denied after dependencies are cached
  when verifying local operation. The coding agent's own provider is separate.

### Search correctness and freshness

- Plain ColGREP search is hybrid. Pure semantic ranking may elevate short fragments
  or tests; refine the query, narrow the source directory, or exclude tests when
  the question calls for implementations. Known symbols usually belong in rg.
- Searches update changed files automatically. `--no-update` is useful for diagnosing
  cached retrieval but can return stale source. It is not the normal workflow.
- `rg` matches comments and strings. ast-grep matches syntax but does not resolve
  types or prove runtime behavior. Use the explicit `ast-grep` command; `sg` can
  name an unrelated executable on some systems.
- Outline is experimental, with language/extractor and ignore-rule coverage limits.
  Empty output is not proof of absence. Inspect scope and source as needed.

## Validate a reused installation

1. Check binary versions/help and PATH from the actual agent shell.
2. Confirm both agents point to the same skill (or synchronized Windows copies).
3. Run a narrow `ast-grep outline ./src --items exports --view names`, an exact rg
   lookup, and a behavioral ColGREP query in a representative repository.
4. Verify a temporary structural-rule fixture distinguishes real code from similar
   comments/strings. For a new backend, initialize an index and inspect diagnostics.
5. Edit/remove a temporary indexed fixture and confirm automatic search updates;
   clean it up without changing application code. Record actual memory/latency.

## Updating and sharing

Keep this directory self-contained, keep tool guides as on-demand references, and
retain their [upstream attribution](sources.md) when redistributing. This package
contains no tool binaries, model weights, credentials, personal machine paths or
project indices. Check upstream flags/backends again when upgrading; the recorded
Apple behavior is a versioned observation. Official per-tool integration installers
can restore competing skills/hooks, so update the consolidated guides deliberately.
