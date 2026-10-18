# Install and reuse the charter

Install this skill globally for Codex and Claude Code:

```bash
DO_NOT_TRACK=1 npx skills add ebursztein/agent-skills \
  --skill realms-of-code --agent codex claude-code --global
```

Inspect an existing installation first. Keep one canonical copy in
`~/.agents/skills/realms-of-code` and the Claude registration pointing to that
copy. The installer handles the supported agent locations; use its copy option
on platforms where symlinks are unavailable. Preserve unrelated skills and
agent configuration. Never register each realm as an independent skill.

The package includes all seventeen guides. It needs no runtime, background
service, model or extra MCP server. Sprinty is the preferred work tracker when
available; the Baratheon guide explains orientation, repository binding and the
unavailable-tool fallback. The skill itself does not install Sprinty.

For code navigation, optionally install the companion skill:

```bash
DO_NOT_TRACK=1 npx skills add ebursztein/agent-skills \
  --skill code-search --agent codex claude-code --global
```

That skill owns CLI installation, semantic indexing and Apple Silicon backend
gotchas. Its tools are separate from installing agent instructions. Keep those
details in its setup guide rather than copying them into this charter.

## Make the workflow discoverable

The skill's description permits ordinary agent selection. To establish it as a
working habit, merge a short pointer into the user's existing global Codex
`AGENTS.md` and Claude `CLAUDE.md`, preserving other instructions:

> For software planning, implementation, refactoring, review and release work,
> read the shared realms-of-code skill at
> ~/.agents/skills/realms-of-code/SKILL.md. Load only the relevant realm guides
> and follow the repository's instructions and existing sources of truth.

Resolve `~` when a file tool does not expand it. Agent skill lists may refresh
on the next turn or require a fresh chat, depending on the host. Verify that the
skill appears in the actual session rather than assuming an existing chat has
refreshed. No startup or command-rewriting hook is needed.

## Verify and update

```bash
DO_NOT_TRACK=1 npx skills list --global --agent codex claude-code
DO_NOT_TRACK=1 npx skills update realms-of-code --global
```

Confirm the canonical SKILL.md and every relative guide can be opened from both
agents. Updates should preserve one discovery entry for the charter and one for
the optional code-search companion. On an offline machine, copy the complete
skill directory, including its references and license, into the supported skill
locations; do not copy only SKILL.md.

## Keeping the charter reusable

The files in `realms/` are the canonical content. Their frontmatter supplies an
id, name, discipline, motto and motto provenance category for reuse in a field
guide or website. Edit an axiom there once, then update any affected routing.
Keep project paths, credentials, deployment configuration and private project
examples outside this public package.
