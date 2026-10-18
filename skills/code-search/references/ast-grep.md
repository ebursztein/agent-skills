# Structural search with ast-grep

Read the [official ast-grep skill guide](ast-grep/guide.md) for writing and testing
patterns and rules. Its [rule reference](ast-grep/references/rule_reference.md) is
available for nontrivial syntax. Load the rule reference only when needed.

Use the explicit `ast-grep` executable and the correct `--lang` (or YAML `language`).
Start with a narrow file/directory scope. For nontrivial rules, test a matching and
a nonmatching example, including comments/strings when relevant. Validate both the
pattern and file coverage before interpreting zero matches as evidence of absence.
Results describe syntax, not type-resolved references or proof of runtime behavior.

Before a transformation, inspect matches and the proposed diff. Use native agent
editing tools where appropriate, then run the relevant tests and checks. No code
transformation is implied by a search-only request.

The preserved official guide and rule reference came from
https://github.com/ast-grep/agent-skill at commit
`f2175aff21f20cfb8e2db30c28febeb3a2d42b61`. They retain upstream content and relative
links. The user-wide standalone registration was retired to keep one search skill.
When refreshing upstream content, update these references rather than reinstalling
a second top-level skill. Local tool selection and correctness rules above govern
this combined workflow.
