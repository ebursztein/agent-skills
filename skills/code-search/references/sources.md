# Sources and attribution

The consolidated workflow and portable helper are local additions. Tool binaries,
models and their licenses are separate and are not redistributed in this package.

## Preserved ast-grep material

- `ast-grep/guide.md` and `ast-grep/references/rule_reference.md` preserve the
  official ast-grep skill material from [ast-grep/agent-skill](https://github.com/ast-grep/agent-skill),
  commit `f2175aff21f20cfb8e2db30c28febeb3a2d42b61`.
- `outline.md` adapts that repository's `ast-grep-outline` skill, with local usage
  notes and a quoted changed-file example. The source URL and commit are recorded
  in the guide.
- The maintainers' [README license statement](https://github.com/ast-grep/agent-skill#license)
  says the skill follows ast-grep's MIT license for included documentation/examples.
  The [upstream MIT license](ast-grep/LICENSE) travels with these files.
  Retain this provenance when sharing or refreshing these references.

## Tool documentation

- [ripgrep](https://github.com/BurntSushi/ripgrep)
- [ast-grep CLI and outline](https://ast-grep.github.io/guide/outline-code.html)
- [ColGREP installation/backends](https://github.com/lightonai/next-plaid/tree/main/colgrep)

ColGREP configuration details were checked against 1.8.5 source/help; platform
observations and validation date are recorded in setup.md. Performance and device
placement measurements are observations on the tested Mac, not upstream guarantees.
