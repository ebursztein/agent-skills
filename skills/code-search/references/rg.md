# Exact text and filenames

Use `rg` for known strings, error messages and simple identifier occurrences.
Use `rg --files` with globs for filenames. Quote shell patterns and start narrowly.

```bash
rg -n -F 'Connection refused' ./src
rg -n -w 'parseConfig' ./src
rg --files ./src -g '*config*'
```

These are text occurrences, not resolved callers. Regexes do not distinguish code
from comments or strings; use the structural subguide when that distinction matters.
If a result is unexpectedly absent, check scope, case, glob and ignore rules.
