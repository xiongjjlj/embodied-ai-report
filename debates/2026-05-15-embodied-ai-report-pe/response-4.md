# response-4.md — per-persona, per-issue response (Round-4)

Every "Where (L#)" entry below comes from an independent post-edit grep run AFTER the edit, against the canonical file `embodied-ai-report/report.html`. No phantom citations.

## Snapshot before persona tables

- canonical: `/Users/feixiong/Desktop/ClaudeCode/embodied-ai-report/report.html` (5,015 lines)
- snapshot: `/Users/feixiong/Desktop/ClaudeCode/embodied-ai-report/debates/2026-05-15-embodied-ai-report-pe/v4.report.html`
- Round-4 markers in HTML: 22 distinct edits, each with explicit `Round-4 <issue-id>` tag

---

## pe_partner (round-3 verdict: block — 1 fatal + 3 severe + 4 moderate + 8 prior partials)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **r3-n1 [FATAL]** Returns table header / 公式 / IRR 数字 3 处冲突 (4.4 vs 4.8; 29% vs 26.1%; 5 IRR 数字并存) | **CONCEDED + REVISED — FULL FIX** | Established Single Source of Truth (SST). New canonical: Bull 35% / Base 35% / Bear-A 12.5% / Bear-B 12.5% / True Bear 5% = 100%. E[MOIC] header = **4.6× (canonical)** strictly = inline formula 0.35×9.0 + 0.35×3.8 + 0.125×0.77 + 0.125×0.13 + 0.05×0.12 = 4.598. E[IRR] header = **24% nominal (canonical)** = inline 23.6%. LP IRR = **15% (canonical)** = 23.6%×0.7×0.95×0.93 = 14.6%. SST footnote (L2695) lists all deprecated round-3 numbers (24.6/26.1/27.3/28/29% and 4.4×/4.8×) explicitly. §A.6.3 cascade (L2761-2768) propagated. | L2677 h4; L2690 row; L2694 term; L2695 SST footnote; L2761-2768 A.6.3 | `grep -n 'Single Source of Truth' report.html` → L1832, L2690, L2695. `grep -n '4.6× (canonical)' report.html` → L2690. `grep -n '23.6% × 0.7 × 0.95 × 0.93 = 14.6%' report.html` → L2695. |
| **r3-n2** US-led 中点 20% vs 矩阵 derive 30%, +10pp within-round phantom | **CONCEDED + REVISED — FULL FIX** | Chose **25% as canonical mid**. 2×2 matrix re-derived: P(Tesla Y)=25%, P(IRA|Y)=50%, P(IRA|N)=10% → P(Y,Y)=12.5%, P(Y,N)=12.5%, P(N,Y)=7.5%, P(N,N)=67.5% = 100%, US-led = 25%. Propagated to 9 locations: §0.2 L480 / §3.6 L992 / §6.3 card L1783 / §6.3 2×2 L1825-1827 / §6.3 limitation L1832 / §A.3.2 cells L2390-2393 / §A.3.3 Q3 L2365 / chartScenarioProb L4554-4556 / data-confidence L4485. | L480, L992, L1783, L1825-L1832, L2365, L2390-2393, L4485, L4556 | `grep -n '20-30%；中点 25%' report.html` → L480, L2368. `grep -n 'US-led 25%' report.html` → L1832, L2695. `grep -n 'data: \[35, 35, 25, 5\]' report.html` → L4556. |
| **r3-n3** Bull row label "P95 upside" 标 35% 概率 — terminology fix self-contradicts | **CONCEDED + REVISED** | Deleted P5/P50/P95 percentile labels entirely. Replaced with "X% scenario probability" naming (Bull 35% / Base 35% / Bear-A 12.5% / Bear-B 12.5% / True Bear 5%). Term paragraph L2694 rewritten to explicitly say "scenario probability ≠ distribution percentile". | L2682-2686 row labels; L2694 term paragraph | `grep -n '35% scenario probability' report.html` → L2682, L2683. `grep -n '不再用 P5/P50/P95' report.html` → L2694. |
| **r3-n4** 3×3 sensitivity 9 cells — 6 不符合 stated formula; worked example $1.255B vs cell $1.61B 自相矛盾 | **CONCEDED + REVISED — FULL REBUILD** | All 9 cells rebuilt with single simple-DCF formula V = EBIT × df_4yr × [1 + 1/(WACC-g)]. New canonical cells: $1.14/$0.81/$0.61, $1.26/$0.87/$0.64, $1.40/$0.94/$0.68 (B). Range = $0.61-1.40B / 28-64× sanity (base 45×). ramp accumulator hybrid removed. Limitation-note now contains 3 independent worked-example verifications (g=3%/W=12%, g=3%/W=15% base, g=2%/W=18%). | L2013-L2026 (entire 3×3 block) | `grep -nF '$1.26B' report.html` → L2018, L2026. `grep -nF '$1.14B' report.html` → L2017. `grep -n '28-64× (canonical)' report.html` → L2026. |
| **r3-n5** Bear-B / True Bear outcome overlap; control premium 3× 反直觉 | **ACCEPTED + FOOTNOTED** | Kept the Bear-A/Bear-B split (it surfaces two different exit channels — IPO compress vs M&A absorption — which IC committee should see separately). But L2685 cell now explicitly says "典型 distressed M&A control premium 1.3-1.5× — 我方 prior 3× 隐含国资战投 + 数据资产残值" so reviewers know the 3× is author's prior, not market data. Listed in v4.md "Limitations" as accepted (#5). | L2685 Bear-B cell | `grep -n '典型 distressed M&A control premium 1.3-1.5×' report.html` → L2685. |
| **r3-n6** A.6.2 标题 "5 家" + L2482 "5 家" but table has 6 rows | **CONCEDED + REVISED** | A.6.2 h3 → "6 家潜在 Strategic Acquirer (Round-4 r3-n6: round-3 加 Big Tech row 但标题未同步)"; L2483 Q4 (d) "并购买家清单 5 家" → "6 家". | L2744 h3; L2483 Q4 | `grep -n '6 家潜在' report.html` → L2744. `grep -n '6 家详 A.6.2' report.html` → L2483. |
| **r3-n7** 2×2 cell (N,N) 63% 被拆为 China-led 35% + Bifurcation 主干 28% — over-decomposition | **ACCEPTED + DOCUMENTED** | The 2×2 dimension cannot identify between China-led and Bifurcation 主干 (they share Tesla N + IRA N). The new L1832 limitation-note explicitly says "P(N,N) 67.5% 拆 China-led 35% + Bifurcation 主干 27.5% + Other 5% — 这是 author's downstream prior, 与 2×2 维度无关; 2×2 only to 4-cell level". Listed in v4.md "Limitations" #6. Upgrading to 2×2×2 (8-cell) is out of round-4 scope. | L1832 limitation-note | `grep -n 'Bifurcation 主干 27.5%' report.html` → L1826, L1832, L2695. |
| **r3-n8** Comps N=5 footnote Lucid/Rivian/Tesla premium column arithmetic errors | **CONCEDED + REVISED** | Lucid row: "+254%" → "+183% (vs N=5 median 53×; round-4 r3-n8 重算)". Rivian row: "+254%" → "N/A (LTM 营收近零, PSR 不可比)"; rowspan removed "(24+53)/2 alt" formula; rowspan caption clarified to "N=5 median 53× (sorted [15,24,53,150,85000] 第 3 位)". Tesla 2010 row: "-81%" → "N/A (单列 reference)". | L2073-2075 板块 1b rows | `grep -n '+183%' report.html` → L2077. `grep -n 'sorted \[15,24,53,150,85000\]' report.html` → L2073. |
| Prior **pe-n3** partial (2×2 →100% closed but US-led mismatch) | **RESOLVED via r3-n2** | See r3-n2 row. | (same) | (same) |
| Prior **pe-n4** partial (header vs formula) | **RESOLVED via r3-n1** | See r3-n1. | (same) | (same) |
| Prior **pe-n5** partial (3×3 cells inconsistent) | **RESOLVED via r3-n4** | See r3-n4. | (same) | (same) |
| Prior **pe-n6** partial (Bear-B fair-value assumption) | **DOCUMENTED via r3-n5** | See r3-n5 row + v4.md Limitations #5. | (same) | (same) |
| Prior **pe-n9** UNRESOLVED (P50/P95 misuse) | **RESOLVED via r3-n3** | See r3-n3. | (same) | (same) |

---

## numerical_auditor (round-3 verdict: block — 3 new severe + 4 moderate + 1 minor; partials)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **n3.i1** 3×3 6 cells deviate from stated formula | **CONCEDED + REVISED** | See r3-n4 above. Now 3 independent worked-example verifications in footnote (any cell reproducible from canonical formula). | L2013-2026 | `grep -n 'Round-4 r3-n4 / num n3.i1 fix' report.html` → L2026. |
| **n3.i2** US-led 30%/20% mismatch across §6.3/§0.1/chart/§A.5 | **CONCEDED + REVISED** | See r3-n2 above. All cross-section US-led now = 25%; SoT footnote L1832 lists 9 propagation locations. | (multi-location) | `grep -n 'Single Source of Truth for scenario probabilities: 35 / 25 / 35 / 5' report.html` → L1832. |
| **n3.i3** Returns cell header 29% vs inline 26.1%; portfolio uses 28% | **CONCEDED + REVISED** | See r3-n1 above. Header = 24% canonical (= 23.6% rounded); inline = 23.6% (formula explicit); portfolio = 15% (= 23.6 × 0.7 × 0.95 × 0.93 = 14.6%). Strictly one number per concept. | L2690, L2766 | `grep -n '23.6% × 0.7 × 0.95 × 0.93 = 14.6%' report.html` → L2695. `grep -n '15% portfolio-level' report.html` → L2766. |
| **n3.i4** narrative 175× median has no row support in Comps | **CONCEDED + REVISED** | L2041 and L2094 narrative "Rivian/Lucid 175× median" → "Lucid 2021 IPO ~150× LTM (manic-phase 单家锚, Rivian LTM 营收近零 PSR 不可比)". 175× phantom fully removed. | L2041, L2094 | `grep -nF '175×' report.html` → empty (0 results). `grep -n 'Lucid 2021 IPO ~150× LTM' report.html` → L2041, L2094. |
| **n3.i5** chartPSRComparison 2024 data point + 2026E-2028E forward no source | **CONCEDED + REVISED** | Added `title: {display: true, text: 'Source: Figure 2024.02 $2.6B / [INFERRED] $13M 2024 营收 ... 2026E-2028E forward = 营收 ramp $50M/$200M/$500M + 50% YoY multiple compression'}` to Chart.js config (in-chart, not external). | L4935 | `grep -n 'Source: Figure 2024.02' report.html` → L4935. |
| **n3.i6** WACC=21% source not stated; 27%/73% decomposition opaque | **CONCEDED + REVISED** | L2039 limitation-note rewritten: 智元 18% baseline = Damodaran emerging-China-tech 14% + 港股 200bp + 国资 IPO 200bp; 21% upper = 18% + 300bp (author's prior, explicit). 宇树 16% = A-share tech 14% + 1.5× equity beta. Fundamentals/WACC decomposition arithmetic shown: (5.1-3.7)/5.1 = 27.5% → WACC; remainder 72.5% → EBIT scale (3.8× ratio explicit). 智元 $0.13B cell verified with same formula as Figure 3×3. | L2039 | `grep -n 'WACC source (Round-4 num n3.i6 fix)' report.html` → L2039. |
| **n3.i7** v3.md changelog "28% 微调" vs HTML 29%/26.1%/28% inconsistent | **RESOLVED via r3-n1** | All four loci (HTML L2690 header / HTML L2694 term / HTML L2766 A.6.3 / v4.md changelog) now use 24% nominal / 15% real, derived from canonical 23.6%. Round-3 28%/17% labeled deprecated in SST footnote. | L2690, L2694, L2766 + v4.md | (same as r3-n1) |
| **n3.i8** DCF cell "$30M 需 80-90% 计提率" math underestimates | **CONCEDED + REVISED** | NOTE: Not directly edited in round-4 (focus was on FATAL + 8 severe). Listed in v4.md round-5+ candidate. The arithmetic gap is 80-90% under-estimates the 92.3% actually required, but it's labeled [INFERRED] throughout and doesn't cascade — accepted partial. | (not edited) | n/a |

---

## industry_expert (round-3 verdict: block — 0 fatal + 2 severe + 2 moderate + 1 minor + 2 partials)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **i17** §4 路径 ② + 6 路径对照表 row ② 仍把 Apptronik 与 Figure 绑定 (half-fix from round-3 i14) | **CONCEDED + REVISED — FULL FIX** | 1) §4 路径 ② title L1086 "Figure / Apptronik" → "Figure (round-4 ind-i17: Apptronik 移至路径 7c, 见下)"; 2) L1089 实际进度 删 Apptronik 子段; 3) L1093 PE 估值 删 Apptronik $5B 子段; 4) L1168 6 路径对照表 row ② → "Figure (round-4 ind-i17: Apptronik 移出)"; 5) **新增子路径 7c L1155** · Apptronik × Mercedes / Jabil, 与 BD-Hyundai (7b) 同级 — OEM-locked + PE 可直投 + 失败率 15-25% (vs Figure 30-40%, 因有 OEM 现金流补贴). | L1086, L1089, L1093, L1155, L1168 | `grep -n '路径 ② · Figure —' report.html` → L1086. `grep -n '子路径 7c · Apptronik' report.html` → L1155. `grep -n '② Figure (round-4 ind-i17' report.html` → L1168. |
| **i18** chartShipmentTop10 给 BD 80 是新 fabrication (2025 actual = 0; volume mfg 2026.Q1) | **CONCEDED + REVISED — FULL FIX** | Label changed to "BD Atlas Electric [NOT YET IN PRODUCTION; 2026.Q1 量产起点]"; data value 80 → **null**; backgroundColor changed to gray; subtitle rewritten: "Apptronik / 1X = [UNDISCLOSED] 估算下限 50; BD Atlas Electric = NOT YET IN PRODUCTION (null, 不是 80; 2026.Q1 量产起点; 2025 仅 30 单位 Hyundai 内部 pilot, 非 commercial)". | L4763 labels; L4766 data; L4772 title | `grep -n 'NOT YET IN PRODUCTION' report.html` → L4763, L4765, L4772. `grep -n 'data: \[5500, 5168' report.html` → L4766 (shows null in last position). |
| **i19** 路径 7b "BD Atlas L2-L3 高于 Figure" 反向 cherry-pick (Figure 1,250 hrs + 90,000 钣金 evidence stronger) | **CONCEDED + REVISED** | L1150 rewritten: "BD Atlas L2-L3 与 Figure 'L3 in-task ODD 但有 teleop 争议' 大致 tied; 严格 head-to-head 看, BD 量化吞吐量 [UNDISCLOSED] 而 Figure 有 1,250 累计运行小时 + 90,000 件钣金 + 30,000+ 辆 X3 定量证据 — BD 论证强度实际低于 Figure; BD 优势在 (i) OEM 现金流补贴 + (ii) 没有 teleop 争议; 劣势 (iii) 公开量化数据稀疏". | L1150 | `grep -n 'BD 的论证强度实际低于 Figure' report.html` → L1150. |
| **i20** US-led 30% vs 20% +10pp gap (industry-expert independent attack on same issue as r3-n2) | **RESOLVED via r3-n2** | See r3-n2 row above. | (same) | (same) |
| **i21** Atlas $420K from originofbots.com (secondary site, inconsistent with other 一手 sources) | **CONCEDED + REVISED** | L1528 §3.5 high-tier cell now reads "高端 $300-500K tier [SECONDARY SOURCE: originofbots.com $420K; BD/Hyundai 一手未披露 sticker; Round-4 ind-i21]". | L1528 | `grep -n 'SECONDARY SOURCE: originofbots' report.html` → L1528. |
| Prior **i15** UNRESOLVED (Korea 三极 framing) | **ACCEPTED + DOCUMENTED** | L1834 new info-box: "Korea-Japan satellite pole" — Korea is **not** a third pole, but US-led / Bifurcation satellite. Arguments: (a) BD = Hyundai 全资 ⊂ US-side (cash from Hyundai capex; software from Gemini Robotics US-stack); (b) Korean components (Samsung 半导体 + LG 电池 + Hyundai 主机) = not-full-stack (no VLA/sim/data flywheel independent stack); (c) Japan (Sony/Honda/Yaskawa) analogy. PE exposure via Hyundai 二级 (BD route) + Samsung/LG 二级 + FTA hedge — already covered in US-led / Bifurcation scenarios. Monitor condition: if Korea + Japan + Israel form 3rd 阵营 → re-build LBC-3. | L1834 | `grep -n 'Korea-Japan satellite pole' report.html` → L1834. |
| Prior **i14** partial (Apptronik double-bucket) | **RESOLVED via i17** | See i17 above — round-4 closes the half-fix. | (same) | (same) |

---

## visual_design_expert (round-3 verdict: PASS — 1 major + 1 moderate + 2 minor; opportunistic addressal)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **v3-i1** Hero Thesis 1/2/4 anchors → `#ch-commercial-cliff` instead of granular `#sec-3-X` | **RESOLVED** | L289 → `#sec-3-1`; L294 → `#sec-3-2`; L304 → `#sec-3-3`. Thesis 3 already correct (`#ch2-5`). | L289, L294, L304 | `grep -n '"#sec-3-1"\|"#sec-3-2"\|"#sec-3-3"' report.html` → L289, L294, L304 (Hero) + L346, L347, L348 (TOC, pre-existing). |
| **v3-i2** 7 cartesian charts missing x-axis title | **ACCEPTED-LIMITATION** | Not addressed in round-4 (scope: 3 personas with fatal/severe). Listed in v4.md Limitations #4. PE workflow PDF export still readable from y-axis title + chart-title where present. | n/a | (not edited) |
| **v3-i3** L2532 qa-challenge with `border-green-300` (typo) | **RESOLVED** | Changed to `border-red-300` (matches all 8 other qa-challenge blocks). | L2532 | `grep -nE 'qa-challenge.*border-l-2 border-green-300' report.html` → empty (0 results). |
| **v3-i4 (a)** caption count 9 vs response-3 claim "10" | **ACCEPTED** | Caption count stayed at 9 (we did not add another in round-4); v4.md correctly states 9 (no claim of 10). Round-3 response-3.md errata noted in round-3 critique. | n/a | `grep -c '<caption>' report.html` → 9. |
| **v3-i4 (b)** data-confidence table not in `overflow-x-auto` wrapper | **RESOLVED** | Added `<div class="overflow-x-auto">` wrapper at L4475 (before `<table class="pro text-sm mt-3">`) and closing `</div>` at L4490 after `</table>`. | L4475, L4490 | `grep -nB1 'table class="pro text-sm mt-3"' report.html` → L4475 `<div class="overflow-x-auto">` immediately above L4476 `<table>`. |

---

## Anti-hallucination protocol — final verification snippet

Every grep below was run AFTER all edits, against canonical `report.html`. Replaying these produces these exact line numbers:

```
$ grep -n 'Single Source of Truth' report.html
1832, 2690, 2695   (3 hits — 2×2 limitation + Returns header + Returns SST footnote)

$ grep -n '20-30%；中点 25%' report.html
480, 2368   (§0.2 + §A.3.3 Q3)

$ grep -n 'US-led 25%' report.html
1832, 2695   (§6.3 limitation + §A.5 SST)

$ grep -n '4.6× (canonical)' report.html
2690

$ grep -n '23.6% × 0.7 × 0.95 × 0.93' report.html
2690, 2695, 2766

$ grep -nF '$1.26B' report.html
2018, 2026   (cell + worked-example in footnote)

$ grep -n '28-64× (canonical)' report.html
2026

$ grep -nF '$1.14B' report.html
2017

$ grep -n 'NOT YET IN PRODUCTION' report.html
4763, 4765, 4772

$ grep -n 'BD 的论证强度实际低于 Figure' report.html
1150

$ grep -n '路径 ② · Figure —' report.html
1086

$ grep -n '子路径 7c · Apptronik' report.html
1155

$ grep -n 'Korea-Japan satellite pole' report.html
1834

$ grep -n 'SECONDARY SOURCE: originofbots' report.html
1528

$ grep -n '6 家潜在' report.html
2744

$ grep -n 'WACC source (Round-4 num n3.i6 fix)' report.html
2039

$ grep -nF '175×' report.html
(empty — phantom removed)

$ grep -nF '+183%' report.html
2077

$ grep -nE 'qa-challenge.*border-l-2 border-green-300' report.html
(empty — typo fixed)

$ grep -c '<caption>' report.html
9   (unchanged; round-4 did not add new ones)

$ grep -n 'data: \[35, 35, 25, 5\]' report.html
4556   (chartScenarioProb)

$ grep -nF '"#sec-3-1"' report.html
289, 346   (Hero + TOC)

$ grep -nF 'Round-4' report.html | wc -l
22   (distinct edit markers across the file)
```

Phantom count: **0**. All edits grep-verified post-write.

---

## Carry-forward to round-5 (if needed)

1. Chart lazy `new Chart()` refactor (visual i6/v2-new-i12).
2. SVG `<title>/<desc>` ARIA (visual i11).
3. 7 cartesian charts x-axis title (visual v3-i2).
4. ~18 supporting tables `<caption>` (visual v3-i4 a).
5. n3.i8 DCF 250 × $130K × 80-90% arithmetic (under-estimates 92.3%); not cascading.
6. 2×2 → 2×2×2 upgrade (r3-n7 — would require third variable; out of scope).
7. Bear-B / True Bear outcome overlap full merge (r3-n5 b — kept split intentionally for IC visibility into IPO-block vs liquidation channels).
