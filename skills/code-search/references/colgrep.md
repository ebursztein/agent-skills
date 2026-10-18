# Semantic discovery with ColGREP

Use a behavioral question when the implementation or its symbols are unknown.
Default ranking combines semantic and keyword search; pure semantic ranking can
be noisier. Inspect candidates and refine wording or scope when results drift.

```bash
cgrep "reserve provider credits atomically" ./src
cgrep -k 20 "allocate a daily payout to individual machines" ./src
cgrep --semantic-only "question" ./src
```

The optional [portable helper](../scripts/cgrep) executes `colgrep` from PATH,
defaults to eight results and static batching, and preserves explicit result counts
and backend selections. It selects `--force-gpu` on Apple Silicon when no backend
was specified. Other hosts use the installed binary's default backend. It works
in POSIX noninteractive shells; a shell alias is not required.

Without the helper, use the command appropriate to the verified backend:

```bash
# Official Apple Silicon build:
colgrep search --force-gpu --static-batch -k 8 "question" ./src
colgrep init --force-gpu --static-batch -y .
# CPU-only build, including pre-built Linux/Windows binaries:
colgrep search --force-cpu --static-batch -k 8 "question" ./src
colgrep init --force-cpu --static-batch -y .
```

See [setup](setup.md) before choosing platform settings. Searches automatically
update changed files; no watcher or service is needed. Use `--include="*.ts"` or
`--exclude="*.test.ts"` when that scope suits the question. `--no-update` searches
the current index as-is and can be stale; do not use it for freshness-sensitive work.

CoreML/Metal and CPU kernels can run in the same command. A GPU flag or runtime
banner alone is not proof of full GPU execution. Do not enable `--agent` or install
its optional 2B planner as part of this workflow.

Agent guidance belongs to this shared skill. Standalone ColGREP integrations may
add competing instructions, skills or hooks; inspect existing registrations before
using their installers. This skill needs only the CLI, not an MCP or daemon.
