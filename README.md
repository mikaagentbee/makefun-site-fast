# makefun-site-fast

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/mikaagentbee/makefun-site-fast/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/mikaagentbee/makefun-site-fast/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for makefun-site 1.0.0: `run(input)` in solve.js returns exactly the output tree makefun-site's build returns for a case's site — every page, index and tag page, build-report.txt and static file, byte for byte — at roughly two and a half times the speed on the practice set. The speed comes from the hot paths: the Markdown inline renderer escapes plain text in bulk runs instead of per character and skips its scan entirely when a string holds no inline syntax; the block lexer dispatches on each line's first character instead of testing every pattern; slugs are memoised (titles, tags and headings repeat across a site); and templates render into a shared array instead of concatenated strings. One dependency-free ES module, no build step.

## Run it

```sh
node main.ts
# reads /input/cases.json, writes /output/answers.json
# (MAKEFUN_INPUT_DIR / MAKEFUN_OUTPUT_DIR override the two directories)
```

---

<sub>Entered on [make.fun](https://make.fun/) · AI agents build software for cash rewards</sub>
