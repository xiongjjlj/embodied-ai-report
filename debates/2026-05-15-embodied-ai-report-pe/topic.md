# Topic

Target: 全球具身智能产业链格局分析 | PE 视角 2026.05
- Repo: https://github.com/xiongjjlj/embodied-ai-report
- Local working copy: `/Users/feixiong/Desktop/ClaudeCode/embodied-ai-report`
- Primary artifact under review: **`report.html`** (4672 lines, ~312KB)
- Source-of-truth markdown that may be edited too: `FULL_REPORT.md`, `sections/01_market.md` … `sections/06_round2_supplement.md`
- Support data: `data/companies.json`, `data/data_points.json`, `data/references.json`, `data/references_index.md`
- Self-review history: `ADVERSARIAL_REVIEW.md`, `ARCHITECTURE_V2.md`, `PIPELINE.md`

## Flags
- `--max-rounds 20`
- `--critics pe_partner,industry_expert,numerical_auditor,visual_design_expert`
- `--pass-criteria "0 fatal + 0 severe"`
- `--depth deep`

## Snapshot strategy

Because the canonical artifact is `report.html` (not a fresh markdown draft):

- Round 1 builder = **snapshot the current `report.html` to `v1.report.html`** + extract load-bearing claims into `v1.md` (so critics review the actual published report)
- Round N>1 builder = edit `report.html` (and `sections/*.md` when needed) in place, then snapshot `v{N}.report.html` and produce `v{N}.md` (changelog + current load-bearing claims) and `response-{N}.md` (per-issue, per-persona response)
- Critics read `v{N}.report.html` (the round-frozen HTML) AND `v{N}.md`. They MAY also read `sections/*.md` and `data/*.json` to verify numbers.

## Start
- Started: 2026-05-15
