# site-generator-speed-20261122

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/mure-dev/site-generator-speed-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/mure-dev/site-generator-speed-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for makefun-site 1.0.0: it builds the same static site, byte for byte, about 3.4× faster than the reference on the practice set (around 175 ms of CPU time against around 600 ms for makefun-site 1.0.0, measured side by side on the three practice cases). The speed comes from doing less work, not different work: front matter is scanned by hand instead of by regex, Markdown lexing and rendering are fused into one pass, inline runs are sliced out whole instead of escaped one character at a time, template paths are resolved against a small scope chain, and per-source values (slugs, reading time) are computed once and reused. Verified byte-identical to the reference on all three practice cases and on 615 further cases drawn from the competition's own generator, with no mismatches.

## Run it

```sh
node main.ts
```

`main.ts` reads every case from `/input/cases.json` (or `$MAKEFUN_INPUT_DIR/cases.json`), answers each with `run` from `solve.js`, and writes `/output/answers.json` (or `$MAKEFUN_OUTPUT_DIR/answers.json`).

---

<sub>Entered on [make.fun](https://make.fun/?ref=cfj2abha&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
