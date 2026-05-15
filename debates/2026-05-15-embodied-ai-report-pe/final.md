# Debate Final Report

**Topic:** 全球具身智能产业链格局分析 | PE 视角 2026.05 — adversarial review of `report.html`
**Repo:** https://github.com/xiongjjlj/embodied-ai-report
**Critics:** `pe_partner`, `industry_expert`, `numerical_auditor`, `visual_design_expert`
**Pass criteria:** `0 fatal + 0 severe`
**Max rounds:** 20
**Rounds run:** 5
**Outcome:** ✅ **PASS** (all 4 personas converged on pass at round 5)
**Folder:** `debates/2026-05-15-embodied-ai-report-pe/`

## Final draft

→ `report.html` (5,016 lines) — also snapshotted at `v5.report.html`.

## Trajectory

| Round | Fatal (new) | Severe (new) | Moderate (new) | Minor (new) | Aggregate |
|-------|-------------|--------------|----------------|-------------|-----------|
| 1 | 7  | 22 | 17 | 6 | block |
| 2 | 4  | 17 | 15 | 2 | block (phantom-fix alert) |
| 3 | 1  | 8  | 11 | 4 | block (visual passes) |
| 4 | 0  | 1  | 7  | 6 | block (numerical passes) |
| 5 | 0  | 0  | 3  | 3 | **PASS** (PE + industry pass) |

Cumulative resolutions: 7/7 fatal, 22/22 severe (round-1 inventory), plus all severe regressions in rounds 2-4. 0 phantom fixes since round 3.

## Per-persona ending state (round 5)

| Persona | Final verdict | Round of first pass | Outstanding fatal | Outstanding severe | Outstanding moderate |
|---------|---------------|---------------------|-------------------|--------------------|----------------------|
| visual_design_expert | pass | 3 | 0 | 0 | 0 (1 minor) |
| numerical_auditor | pass | 4 | 0 | 0 | 3 (cosmetic MOIC rounding, Bear-B residual semantic, KPI stale 40%) |
| industry_expert | pass | 5 | 0 | 0 | 0 (clean) |
| pe_partner | pass | 5 | 0 | 0 | 0 (1 minor: ensemble math under-derived) |

## What the report now contains that round-1 didn't

- **Figure DCF / Comps internally consistent**: PSR 1,300–2,600× (was self-contradicting 790×), Symbotic 13× (was 4.5×), EV IPO median 24× (was 22×); Rivian/Lucid/Tesla rows added to the comps table.
- **MOIC / IRR single source of truth (SST)**: round-1 had 5 different IRR numbers (29% / 26.1% / 28% / 23.6% / etc.) and 2 MOIC numbers — round 5 canonicalizes to E[MOIC] mid 2.54× (with sensitivity 2.13–2.95× under capture-prob 0.4–0.6), E[IRR] 21%, propagated through 9 doc locations with a footnote pointing to the canonical computation.
- **Bull-row capture-probability factor**: round 5 introduced an explicit `P(智元 captures | China-led)` column. Bull's 9× return no longer rides directly on the 35% macro scenario — it discounts through 7-way Chinese pole competition, folding E[MOIC] from 4.6× down to 2.54×. This was the round-1 fatal hidden in the Bull row.
- **3×3 g/WACC sensitivity table**: all 9 cells now derive from a single formula `V = EBIT × df_4yr × [1 + 1/(WACC-g)]` and re-compute within 1% on independent audit ($0.61–1.40B / 28–64× canonical).
- **US-led probability** propagated consistently across 9 doc locations (was 20% vs 30% +10pp gap).
- **chartShipmentTop10** no longer fabricates BD 80 units 2025 shipments (BD commercial launch is 2026 Q1).
- **DeepMind / Gemini Robotics 1.5 / BD × Hyundai Atlas Electric** now in the玩家 framework (round-1 fatals from industry_expert).
- **7th 路径 row (Apptronik OEM-locked)** added to head-to-head failure-rate table — decoupled from the prior Figure/Apptronik bundle.
- **All CSS classes have matching `<style>` rules** (round-2 caught 8 phantom classes). 0 phantom CSS since round 3.
- **TOC dedupe**: 33 hrefs, 0 duplicates (was 11 duplicates).
- **Tables**: 30/30 wrapped in `overflow-x-auto`; all `<table class="pro">` have `<thead>`.
- **Korea-Japan sub-pole**: explicitly framed (BD = Hyundai-owned ⊂ US-side; Korean components ≠ full stack) — info-box callout.

## Outstanding issues (all moderate / minor — non-blocking)

These were noted by critics at round 5 and are documented for a follow-up cleanup:

1. **n5.i1 (mod)** — E[MOIC] mid number written three slightly different ways: header 2.55×, expanded inline 2.53×, v5.md 2.54×. The precise computation is 2.5385. Pick one rounding (2.54×) and propagate.
2. **n5.i2 (mod)** — Bear-B sunk-residual (0.5×) > capture-conditional Bull-of-Bear (0.13×) — semantic inversion, ~1% impact on E[MOIC] but conceptually wrong (failure should not pay more than success).
3. **n5.i3 (mod)** — L499 KPI strip still has "基准情景（40%）"; r4-i22 sweep that propagated 35% missed this line.
4. **pe r5-n1 (minor)** — ensemble math under-derived (mentioned ensemble of 宇树+智元+银河 but didn't show the math).
5. **numerical n5.i4 (minor)** — E[IRR] method silently shifted across rounds (linear-avg 23.6% → MOIC-backout 21%) at L2769; method footnote would close this.
6. **visual v5 minor** — cosmetic indent residual.

## Files in the debate folder

```
topic.md
v1.report.html  v1.md
critique-1-{pe_partner,industry_expert,numerical_auditor,visual_design_expert}.{json,md}
round-1-summary.json
v2.report.html  v2.md  response-2.md
critique-2-…
round-2-summary.json
v3.report.html  v3.md  response-3.md
critique-3-…
round-3-summary.json
v4.report.html  v4.md  response-4.md
critique-4-…
round-4-summary.json
v5.report.html  v5.md  response-5.md
critique-5-…
round-5-summary.json
final.md   ← this file
```

## Skill changes made for this run

The `/debate` skill was upgraded to support **multiple critic personas running in parallel each round**. Concretely:

- `~/.claude/commands/debate.md` — orchestrator now parses `--critics csv` flag, spawns N critics in parallel per round, aggregates verdict via `--pass-criteria` (`"0 fatal + 0 severe"` default for multi-critic).
- `~/.claude/agents/debate-critic.md` — accepts a `persona` parameter, writes `critique-{N}-{persona}.{json,md}`, severity scale updated to `fatal / severe / moderate / minor`. Personas defined: `pe_partner`, `industry_expert`, `numerical_auditor`, `visual_design_expert`, `default`.
- `~/.claude/agents/debate-builder.md` — round-N>1 now reads **all** persona critique JSONs and disambiguates issue IDs by `<persona>.<id>` in `response-{N}.md`.

## Notes

- The biggest single learning: between rounds 2 and 3, multiple personas independently caught "phantom fixes" — the builder claimed edits that never landed (CSS classes with no rules, table rows that didn't exist). Adding an anti-hallucination protocol (grep-verify every edit post-write, embed evidence in response-{N}.md) eliminated these from round 3 onward.
- The hardest fatal to surface: the Bull-row capture conflation (PE r4-n1). It survived rounds 1-3 because every critic was treating it as "macro scenario weight"; only the second pass through the same row caught that 9× returns ride on TWO independent probability terms, not one.
