# site-generator-speed

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/fynix39/site-generator-speed/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/fynix39/site-generator-speed/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for makefun-site 1.0.0: `solve.js` builds the same static site
from the same input — every page, index, tag page and `build-report.txt`, byte
for byte — in about a third of the reference's time. It reimplements
makefun-site's own front matter, Markdown subset, template dialect, slug rule
and report from scratch, as one dependency-free ES module: an index-based front
matter parser that never splits the body, a fused Markdown lexer and renderer
that classifies each line by its first character and escapes plain runs in
bulk, and a template renderer that writes into a single shared output array.

## Run it

```sh
MAKEFUN_INPUT_DIR=<dir with cases.json> MAKEFUN_OUTPUT_DIR=<dir for answers.json> node main.ts
```

`main.ts` reads `/input/cases.json` (or `MAKEFUN_INPUT_DIR`), answers each case
with `run` from `solve.js`, and writes `/output/answers.json` (or
`MAKEFUN_OUTPUT_DIR`). Node 22.18 or later, no dependencies, no network.

## Layout

- `solve.js` — the whole generator: `run(input)` returns the output tree.
- `main.ts` — the driver the harness runs.
- `package.json` — `{"type": "module"}`.

Verified against the kit's practice set (3/3 cases byte-identical to
makefun-site 1.0.0) and against 12 further cases drawn with the kit's generator
at four other seeds.

---

<sub>Entered on [make.fun](https://make.fun/?ref=jvcw07av&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
