# response-5.md — per-issue response (Round-5)

All "Where (L#)" entries below come from post-edit grep against canonical `embodied-ai-report/report.html`. No phantom citations. Snapshot: `debates/2026-05-15-embodied-ai-report-pe/v5.report.html` (5,016 lines).

Round-5 markers: 15 distinct `Round-5 ...` tags. Round-4 markers retained: 23.

---

## pe_partner Round-4 — 1 severe + 1 moderate addressed (+ 3 partials cleaned up)

| Issue | Severity | Status | What I did | Where (L#) | Verification grep |
|---|---|---|---|---|---|
| **r4-n1** SST Bull row 把 macro China-led 35% 与 智元-specific Bull-exit-$35B 划等号 — category conflation | severe | **CONCEDED + FULL REVISION (Choice A)** | Introduced explicit `P(智元 captures \| scenario)` column. Prior set: 0.5 mid (range 0.4-0.6) for China-led/Bifurcation rows (7-way Chinese-pole competition), 0.6 mid (0.5-0.7) for US-led rows (国资 backing relatively richer), 1.0 for True Bear (already conditional on 智元 failure). Sunk-fund residual 0.5× MOIC for capture-failure mass. New canonical: E[MOIC] capture-adjusted ~2.55× mid (range 2.0-3.0×) — Bull contribution falls from 3.15 to 1.66 (= 0.35×0.5×9.0 + 0.35×0.5×0.5). E[IRR] capture-adjusted ~21% nominal mid (range 16-24%). LP real ~13% mid (range 10-15%). OLD canonical 4.6×/24%/15% explicitly retained as "Bull-takes-all ceiling — overstates by ~80% on MOIC; DEPRECATED but kept as upper bound." Propagated through 9 SST cascade locations: §7 header (L2678), table caption (L2681), column header (L2682), all 5 row entries (L2686-2690), E[MOIC] summary row (L2691), SST footnote (L2696), §A.6.3 paragraph header (L2762), §A.6.3 bullet (L2767), §A.6.3 caveat (L2769). | L2678, L2681-2691, L2696, L2762, L2767, L2769 | `grep -n 'capture-probability factoring' report.html` → L2678, L2696. `grep -n '2.55× (capture-adjusted base' report.html` → L2691. `grep -n '7-way Chinese-pole 竞争' report.html` → L2681, L2686. `grep -n 'Bull-takes-all ceiling' report.html` → L2691, L2696. |
| **r4-n2** §A.5 Q9 (L2592-2594) 仍写 'IRR P50/P95' 与 r3-n3 fix paragraph 矛盾 | moderate | **CONCEDED + REVISED** | All 3 Q9 line items rewritten with named-scenario language: ① 宇树 "IRR Base case ~25% / Bull case ~45%"; ② 金力 "IRR Base case ~20% / Bull case ~40%"; ③ 仿真种子轮 "IRR Base case ~30% / Bull case ~80%". Each line carries explicit "Round-5 r4-n2: P50/P95 distribution-percentile 术语已替换" tag. | L2593, L2594, L2595 | `grep -n 'IRR Base case ~25% / Bull case ~45%' report.html` → L2593. `grep -n 'IRR Base case ~20% / Bull case ~40%' report.html` → L2594. `grep -n 'IRR Base case ~30% / Bull case ~80%' report.html` → L2595. |
| **r4-n3** Bull 锚 5万台 vs 100万 China-led 不匹配 | moderate | **RESOLVED via r4-n1** | The capture-probability column makes Bull row conditional on "智元 dominant 中国 winner" explicit (= 智元 captures full China-led upside). Reviewer can now see "5 万 / 100 万 = 5% share" mismatch implicitly priced as P(capture) = 0.5. No separate edit needed beyond r4-n1 cascade. | L2686 | (covered by r4-n1) |
| **r4-n4** §A.6.3 channel breakdown 用 31% 与 portfolio 23.6% 两个分母 | minor | **PARTIAL — DOCUMENTED** | §A.6.3 caveat (L2769) now explicit: "Base case is 'LP if Bifurcation AND 智元 wins (P=17.5%)' conditional"; portfolio capture-adjusted E[IRR] = 21% nominal / 13% real. Channel-level cross-section using portfolio-anchored discount not added (would require duplicating 5-row matrix; minor cosmetic). | L2767, L2769 | `grep -n 'capture-adjusted Base contribution' report.html` → L2769. |
| **r4-n5** P(N,N) split prior 27.5% vs 7.5% 来源未说 | minor | **ACCEPTED + DOCUMENTED** (carry-forward) | Existing limitation-note L1832 retains 35:27.5:5 split. r4-n1 capture-probability framing makes the China-led 35% itself less load-bearing (it's now multiplied by 0.5 capture probability), so split's marginal sensitivity to E[MOIC] drops by ~50%. Listed in v5.md round-6+ carry-forward. | L1832 (unchanged) | (carry-forward) |

---

## numerical_auditor Round-4 — 3 moderates addressed

| Issue | Severity | Status | What I did | Where (L#) | Verification grep |
|---|---|---|---|---|---|
| **n4.i1** §A.5 IC Memo intro L2644: '22%' + '$0.15B' round-3 残留 | moderate | **CONCEDED + REVISED** | L2645: "PSR 20× 接近 EV IPO 中位 22%" → "PSR 20× 接近 EV IPO N=3 sample median **24×** (round-3 重算)"; "vs 简化 sanity check $0.15B" → "vs 简化 sanity check **$0.17B (Round-4 canonical, see §6.5.1)**". Added explicit "Round-5 n4.i1: IC Memo intro 同步至 Round-4 SST canonical 24× / $0.17B (前为 round-1 残留 22% / $0.15B)" tag. | L2645 | `grep -n 'EV IPO N=3 sample median <strong>24×</strong>' report.html` → L2645. `grep -nF 'sanity check <strong>$0.17B (Round-4 canonical' report.html` → L2645. |
| **n4.i2** §6.5.1 footnote 'unified g=3%' 实际 per-company g 不同 | moderate | **CONCEDED + REVISED (Choice b — explicit per-company)** | L2040 footnote rewritten with per-company explicit (g, WACC) call-out: "**Figure $0.74B (g≈2.15%, W=16%)** — 美系成熟期低增长 prior; **智元 $0.20B (g=3%, W=16%)** — 中系硬件升周期 base; **宇树 $0.50B (g≈4.3%, W=16%)** — 已盈利 + R1 海外 30% 出口持续 ramp prior. Ratio 3.7× / 1× / 2.5× (per-company g 反映 perpetual growth 假设差异 — not free parameter, reflects 不同公司生命周期)." Ratios unchanged (3.7×/1×/2.5×) because per-company g reflects fundamentals difference. fundamentals 73% / WACC 27% decomposition unchanged. | L2040 | `grep -n 'Figure \$0.74B (g≈2.15%' report.html` → L2040. `grep -n '宇树 \$0.50B (g≈4.3%' report.html` → L2040. |
| **n4.i3** L2032 column header 'WACC=21%' 跨 row 不一致 (宇树 row 实际 W=18%) | moderate | **CONCEDED + REVISED** | L2033: `<th>下沿 (g=2%, WACC=21%)</th>` → `<th>下沿 (g=2%; WACC: 智元 21% / 宇树 18%) <span class="text-xs">(Round-5 n4.i3 split)</span></th>`. Same fix for 统一 WACC column ("per-row g 见 §6.5.1 footnote"). | L2033 | `grep -n '智元 21% / 宇树 18%' report.html` → L2033. |

---

## industry_expert Round-4 — 1 moderate + 2 minor addressed

| Issue | Severity | Status | What I did | Where (L#) | Verification grep |
|---|---|---|---|---|---|
| **i22** §6.3 Bifurcation 卡片 L1800 '40%' 与 SST 35% 矛盾 | moderate | **CONCEDED + REVISED** | L1801: `<span class="text-3xl font-bold" style="color:#92400e;">40%</span>` → `<span class="text-3xl font-bold" style="color:#92400e;">35%</span><span class="text-xs text-amber-700 block">(30-40% range; Round-5 r4-i22 SST canonical 中点 35%)</span>`. Bifurcation card visual anchor now reconciled with SST. | L1801 | `grep -n 'r4-i22 SST canonical 中点 35%' report.html` → L1801. |
| **i23** §A.5 Bear-B 触发 '1.3-2×' 与 Exit '3×' control premium 内部矛盾 | moderate | **CONCEDED + REVISED (Choice 1 — unify on 3×)** | L2689 Bear-B 触发列 rewritten: "港股 IPO 失败 + 比亚迪 / 美的 distressed strategic acquire at **~3× DCF sanity (我方 prior 国资战投 + 数据资产残值; 高于 §A.6.1 标准 control premium 1.3-2× — 见 r4-i23 footnote 下)**". Estimat列 retained 3× control premium, now explicit "触发列与估值列现严格同步 r4-i23 fix". One premium across the row; §A.6.1 standard 1.3-2× cross-referenced as benchmark. | L2689 | `grep -n '触发列与估值列现严格同步 r4-i23 fix' report.html` → L2689. |
| **i24** chartShipmentTop10 subtitle '30 单位 Hyundai 内部 pilot' un-sourced new datapoint | minor | **CONCEDED + REVISED** | L4773 chart title text: "2025 仅 30 单位 Hyundai 内部 pilot, 非 commercial" → "2025 = 0 commercial; pre-production / engineering units 数量未公开 [UNDISCLOSED]". Matches Apptronik/1X [UNDISCLOSED] standard already used in same chart. | L4773 | `grep -n 'pre-production / engineering units' report.html` → L4773. `grep -n '30 单位 Hyundai 内部 pilot' report.html` → empty. |
| **i25** §4 6-路径对照表 missing path ⑦c row | minor | **CONCEDED + REVISED** | L1161 caption changed "6 种路径对照" → "7 种路径对照 (Round-5 r4-i25: 添加路径⑦c Apptronik OEM-locked 行)". New row ⑦c inserted after row ⑥ with explicit `style="border-top:4px solid #7c3aed;"` (matches path-card visual idiom). Failure probability 15-25% (vs Figure 30-40%) shown head-to-head. | L1161, L1174 | `grep -n '7 种路径对照' report.html` → L1161. `grep -n '⑦c Apptronik OEM-locked' report.html` → L1174. |

---

## visual_design_expert Round-4 — 2 minor addressed

| Issue | Severity | Status | What I did | Where (L#) | Verification grep |
|---|---|---|---|---|---|
| **v4-i1** L2695 SST limitation-note 缺起始空格 | minor | **CONCEDED + REVISED (incidentally)** | The new SST footnote (after r4-n1 cascade) starts with ` <div class="limitation-note">` (1 space + <, matching v4's 11 other limitation-note blocks). cosmetic indent restored. | L2696 (was L2695 in v4) | `grep -n '^ <div class="limitation-note"><strong>Single Source of Truth (SST) for 智元 Returns — Round-5' report.html` → L2696. |
| **v4-i2** response-4 self-reported '22 Round-4 markers' but grep -c = 23 | minor | **ACKNOWLEDGED (errata)** | Round-4 marker count is indeed 23 (not 22 as response-4 claimed). response-5 reports actual counts: Round-4 markers = 23 (retained); Round-5 markers = 15 (this round's edits). Both grep-verified. | n/a | `grep -c 'Round-4' report.html` → 23. `grep -c 'Round-5' report.html` → 15. |

---

## Anti-hallucination protocol — final verification snippet (post-edit)

Every grep run AFTER edits against canonical `report.html`:

```
$ grep -n 'capture-probability factoring' report.html
2678, 2696   (2 hits — §7 header + SST footnote)

$ grep -n '7-way Chinese-pole 竞争' report.html
2681, 2686   (caption + Bull row)

$ grep -n '2.55× (capture-adjusted base' report.html
2691

$ grep -n 'capture-adjusted Base contribution' report.html
2769

$ grep -n 'Bull-takes-all ceiling' report.html
2691, 2696

$ grep -n 'IRR Base case ~25% / Bull case ~45%' report.html
2593

$ grep -n 'IRR Base case ~20% / Bull case ~40%' report.html
2594

$ grep -n 'IRR Base case ~30% / Bull case ~80%' report.html
2595

$ grep -nF 'sanity check <strong>$0.17B (Round-4 canonical' report.html
2645

$ grep -n 'EV IPO N=3 sample median <strong>24×</strong>' report.html
2645

$ grep -n 'r4-i22 SST canonical 中点 35%' report.html
1801

$ grep -n '触发列与估值列现严格同步 r4-i23 fix' report.html
2689

$ grep -n 'pre-production / engineering units' report.html
4773

$ grep -n '30 单位 Hyundai 内部 pilot' report.html
(empty — removed)

$ grep -n '7 种路径对照' report.html
1161

$ grep -n '⑦c Apptronik OEM-locked' report.html
1174

$ grep -n 'Figure $0.74B (g≈2.15%' report.html
2040

$ grep -n '宇树 $0.50B (g≈4.3%' report.html
2040

$ grep -n '智元 21% / 宇树 18%' report.html
2033

$ grep -c 'Round-4' report.html
23

$ grep -c 'Round-5' report.html
15
```

Phantom count: **0**. All edits post-write grep-verified.

---

## Numerical sanity check on capture-adjusted E[MOIC]

Direct recomputation of formula in L2691:

```
Bull:      0.35 × 0.5 × 9.0 + 0.35 × 0.5 × 0.5 = 1.575 + 0.0875 = 1.6625
Base:      0.35 × 0.5 × 3.8 + 0.35 × 0.5 × 0.5 = 0.665  + 0.0875 = 0.7525
Bear-A:    0.125 × 0.6 × 0.77 + 0.125 × 0.4 × 0.5 = 0.0578 + 0.025 = 0.0828
Bear-B:    0.125 × 0.6 × 0.13 + 0.125 × 0.4 × 0.5 = 0.0098 + 0.025 = 0.0348
True Bear: 0.05 × 1.0 × 0.12 = 0.006
———————
Total: 1.6625 + 0.7525 + 0.0828 + 0.0348 + 0.006 = 2.5386 ≈ 2.54× (mid P=0.5)

At P=0.4 (China-led/Bifurcation rows; Bear-A/B stay at 0.5):
Bull:      0.35 × 0.4 × 9.0 + 0.35 × 0.6 × 0.5 = 1.26  + 0.105 = 1.365
Base:      0.35 × 0.4 × 3.8 + 0.35 × 0.6 × 0.5 = 0.532 + 0.105 = 0.637
Bear-A:    0.125 × 0.5 × 0.77 + 0.125 × 0.5 × 0.5 = 0.048 + 0.031 = 0.079
Bear-B:    0.125 × 0.5 × 0.13 + 0.125 × 0.5 × 0.5 = 0.008 + 0.031 = 0.039
True Bear: 0.006
Total: 1.365 + 0.637 + 0.079 + 0.039 + 0.006 = 2.126 ≈ 2.13× ✓ (matches published "P=0.4 → ~2.13×")

At P=0.6:
Bull:      0.35 × 0.6 × 9.0 + 0.35 × 0.4 × 0.5 = 1.89 + 0.07 = 1.96
Base:      0.35 × 0.6 × 3.8 + 0.35 × 0.4 × 0.5 = 0.80 + 0.07 = 0.87
Bear-A:    0.125 × 0.7 × 0.77 + 0.125 × 0.3 × 0.5 = 0.067 + 0.019 = 0.086
Bear-B:    0.125 × 0.7 × 0.13 + 0.125 × 0.3 × 0.5 = 0.011 + 0.019 = 0.030
True Bear: 0.006
Total: 1.96 + 0.87 + 0.086 + 0.030 + 0.006 = 2.952 ≈ 2.95× ✓ (matches "P=0.6 → ~2.94×")
```

IRR back-out: 2.54^(1/5) - 1 = 20.5%; 2.13^(1/5) - 1 = 16.3%; 2.95^(1/5) - 1 = 24.2%. Published "21% mid (range 16-24%)" ✓.

LP real (mid): 20.5% × 0.7 × 0.95 × 0.93 = 12.7% ≈ 13% ✓.

---

## Carry-forward to round-6 (if needed)

1. r4-n5 split prior 27.5% vs 7.5% — author prior, would require third dimension (2×2 → 2×2×2).
2. r4-n4 channel-level cross-section using portfolio anchor — would require duplicating 5-row matrix; minor cosmetic.
3. Chart lazy `new Chart()` refactor (visual i6/v2-new-i12).
4. SVG `<title>/<desc>` ARIA (visual i11).
5. 7 cartesian charts x-axis title (visual v3-i2).
6. ~21 supporting tables `<caption>` (visual v3-i4 a).
7. n3.i8 DCF 250 × $130K × 80-90% arithmetic (under-estimates 92.3%); not cascading.
8. Bear-B / True Bear outcome overlap full merge (r3-n5 b — kept split intentionally for IC visibility).
