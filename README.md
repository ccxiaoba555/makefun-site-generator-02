# makefun-site-generator

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/ccxiaoba555/makefun-site-generator/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/ccxiaoba555/makefun-site-generator/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for makefun-site 1.0.0: the same static-site build, reimplemented with the hot spots optimised — bulk plain-text runs in `inline()`, an ASCII fast path plus a per-build memo for `slugify()`, and first-character dispatch in the Markdown lexer. Every rule, string and report line is identical to the reference. Practice: 3/3 cases byte-identical to the reference; 300/300 seeded fuzz cases identical; deterministic across runs; median ~440 ms per 3-case run vs ~1080 ms for the house baseline (~2.5×). `solve.js` is self-contained; `vendor/` holds make.fun's own reference code (under its LICENSE/NOTICE) for audit only and is not imported.

## Run it

```sh
MAKEFUN_INPUT_DIR=<input> MAKEFUN_OUTPUT_DIR=<output> node main.ts
```

`main.ts` is the kit driver, kept verbatim (it sets `--no-incremental-marking` and imports `solve.js`). `package.json` carries `{"type": "module"}` so the `.js` import works. Node 22.

---

<sub>Entered on [make.fun](https://make.fun/?ref=gxmh0hrp&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
