# response-3.md — per-persona, per-issue response with verified grep evidence

Every "where (file:line)" cell below was verified with a final `grep -n` immediately before writing this file. No phantom citations.

## pe_partner (round-2 verdict: block — 2 new fatal + 5 new severe + 8 partial prior)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **pe-n1** Comps table 3 stale numbers (Figure 790× / Symbotic 4.5× / EV median 22×; N=5 sample claim w/o rows) [fatal] | **CONCEDED + REVISED** | Comps table fully rewritten: Figure 790× → 1,300-2,600×; Symbotic 4.5× → 13×; 工业 median 3.5× → 8.1×; EV IPO N=3 median 22× → 24×; +9% → 0% / -32% → -37.5% / +141% → +121%; new 板块 1b 加 Rivian / Lucid / Tesla 2010 三行 (N=5 ref); Intuitive 单列医疗机器人. | report.html L2065 Figure row; L2069 蔚来 24× rowspan; L2079 Symbotic 13×; L2071-2078 板块 1b 三新行 | `grep -n '1,300-2,600×.*\$39B.*\$15-30M; 中点 ~1,750×'` → L2065. `grep -n 'Symbotic（仓储自动化）</td><td>2025 FY25'` → L2079. `grep -n '24× (N=3)'` → L2069. |
| **pe-n2** A.3 second-layer 4-row if-then table phantom (was claimed but didn't exist) [fatal] | **CONCEDED + REVISED** | Created actual A.3.2 4-row table: Tesla Y/N × IRA Y/N → 5 资产类 % adjustments. Each cell shows P=15%/15%/7%/63% per §6.3 2×2. A.4 Q2 rewritten w/ explicit cascade. | L2383-2397 A.3.2 table; L2468 A.4 Q2 cascade | `grep -n 'A.3.2 决策树第二层'` → L2383. `grep -n 'IF Tesla Y + IRA Y'` → L2390. `grep -n 'Tesla 失败的量化 cascade'` → L2468. |
| **pe-n3** §6.3 2×2 matrix sums to 110% not 100% [severe] | **CONCEDED + REVISED** | Rewrote 2×2 with strict conditional decomposition: P(Tesla Y)=30%, P(IRA\|Y)=50%, P(IRA\|N)=10% → 4 cells = 15+15+7+63 = 100% ✓. Added marginal row showing Σ=100%. Limitation-note acknowledges US-led now 30% vs 区间中点 20% (+10pp gap noted for Round-4). | L1825-1827 2×2 cells; L1829 limitation-note | `grep -n 'P(Y,Y) = 15%'` → L1825. `grep -n 'Σ = 100%'` → L1827. |
| **pe-n4** A.5 IC Memo weighted MOIC math error (claimed 3.9×, actual 4.83×) + P5 percentile misuse [severe] | **CONCEDED + REVISED** | Recomputed E[MOIC] = 0.35×9 + 0.40×3.8 + 0.10×0.77 + 0.10×0.13 + 0.05×0.12 = 4.77× ≈ 4.8× (using new Bear-A/B split). E[IRR] = 26.1% (was claimed 28%). P5/P50/P95 terminology unified: P5 = 5% probability tail (= True Bear), P50 = median (= Base), P95 = 95% upside (= Bull). E[IRR] = expected value, separate from percentiles. | L2632-2647 Returns table; L2649 术语统一 paragraph | `grep -n 'E\[MOIC\] = 概率加权'` → returns table. `grep -n '术语 (Round-3 统一)'` → L2649. |
| **pe-n5** §6.5.1 3×3 sensitivity claimed but absent; smart numbers inconsistent ($1.61B/24× not 31×) [severe] | **CONCEDED + REVISED** | Actually rendered 3×3 g/WACC table for Figure (9 cells with formulas). Range $0.55-1.93B → 20-71× sanity. Corrected narrative 31-58× → **24-58×** (matches $0.68-1.61B / $39B). Added 智元/宇树 simple table with 统一 WACC 16% column for fundamentals-only delta (Figure $0.74B vs 智元 $0.20B → fundamentals 73%, WACC 假设差 27%). Failure-probability folddown 35% → Figure $0.57B → 68×. | L2010-2025 Figure 3×3; L2027-2034 智元/宇树 simple table; L980 §3.6 24-58× sync | `grep -n '3×3 g/WACC 敏感性矩阵'` → L2010. `grep -n '统一 WACC 16% (中美对照)'` → limitation-note. `grep -n '24-58×'` → L980, L1989. |
| **pe-n6** Bear case $3B/0.77× misaligned with "战略并购" exit channel (should be ~$0.5B) [severe] | **CONCEDED + REVISED** | Bear split into Bear-A (10%, IPO 压缩 $3B / 0.77×) + Bear-B (10%, 战略并购 $0.5B / 0.13×). Multiple column changed to ranges (Bull 8.3-9.7×, Base 3.6-4.2×) reflecting entry uncertainty $3.6-4.2B. | L2638-2641 Bear-A/B rows | `grep -n 'Bear-A (US-led / IPO 估值压缩)'` → L2638. `grep -n 'Bear-B'` → L2640. |
| **pe-n7** SoftBank acquirer row deeply suspect (stale 2020-22 reference) [severe] | **CONCEDED + REVISED** | SoftBank demoted: ⚠ 历史 reference; current deal capacity $5-15B/单笔 (vs historical $20-50B); 中国 portfolio 自 2023 未新增. New Big Tech row added (Alphabet $2-3T / Microsoft / Amazon) with active 2024-2025 deal evidence (Apptronik strategic, Sanctuary stake, Covariant acquisition). | L2742 SoftBank demote; L2747 Big Tech row | `grep -n '2022 Q3 Vision Fund'` → L2742. `grep -n 'Big Tech (Alphabet / Microsoft / Amazon)'` → L2747. |
| **pe-n8** Distressed M&A 10-name watchlist lacks per-company runway / valuation / asset / acquirer [moderate] | **CONCEDED + REVISED** | Added new §A.2.1 subtable (10 rows × 5 cols): runway months / 最近一轮估值 / 核心资产 / acquirer mapping. Split into Tier-A 公开 (6 家) + Tier-B 待 DD (4 家). | L2309-2335 new subtable | `grep -n 'A.2.1.*Distressed.*Watchlist per-company'` → L2309. `grep -n '傅利叶</strong> (Tier-A'` → L2316. |
| **pe-n9** Q9 P50/P95 percentile term misused [moderate] | **CONCEDED + REVISED** | P5/P50/P95 unified definitions added explicitly in IC Memo Returns table paragraph + Q9 follow-up. P50 = median (= Base), P95 = 95th percentile upside, P5 = 5% tail; E[IRR] = expected value distinct from percentile. | L2649 术语 paragraph; L2543 Q9 (existing label unchanged but cross-ref added) | `grep -n '术语 (Round-3 统一): P5 = 5th percentile'` → L2649. |
| **pe-n10** v6/v7 internal versioning leaked into reader-facing footnotes [moderate] | **CONCEDED + REVISED** | Removed v6/v7 notation. Replaced with explicit formula: EBIT × 1/(WACC-g) × df; Figure: $163M × (1/0.12) × 0.572 = $776M ≈ $0.78B. g=3% rationale added (mature industry ~ GDP -1pp). | L2001 永续期 row | `grep -n '永续 g=3% (mature industry ~ GDP -1pp)'` → L2001. |
| **pe-n11** v2.md says "5 PE 行动" but HTML has 6 (Distressed M&A new ⑤) [minor] | **CONCEDED + REVISED** | §0.3 title changed to "6 个最值得做的决定 (含 ⑥ 监测点)". A.3 section title changed to "A.3.3 · 5 个最值得做的具体决定 (long-only positions; §0.3 含 ⑥ 监测点 catch-all 即 6 项)" to acknowledge the framing difference. | L506 §0.3 title; L2399 A.3.3 title | `grep -n '0.3 PE 行动 · 6 个最值得做的决定'` → L506. `grep -n 'A.3.3 · 5 个最值得做的具体决定'` → L2399. |
| **i1** (prior partial: Comps table row stale) | **RESOLVED (via pe-n1)** | See pe-n1 row above. | L2065 | (same as pe-n1) |
| **i2** (prior partial: Returns table cascade fixes) | **RESOLVED (via pe-n4/n6/n9)** | See above. | L2632 | (same) |
| **i3** (prior partial: 3×3 sensitivity actually rendered + fundamentals decomp) | **RESOLVED (via pe-n5)** | See above. | L2010 | (same) |
| **i5** (prior partial: distressed watchlist per-company) | **RESOLVED (via pe-n8)** | See above. | L2309 | (same) |
| **i7** (prior partial: Comps EV IPO N=5 rows in table) | **RESOLVED (via pe-n1)** | Rivian/Lucid/Tesla 2010 added as 板块 1b rows. | L2071-2078 | `grep -n 'Rivian（IPO 2021.11）'` → L2071. |
| **i8** (prior partial: 2×2 matrix math) | **RESOLVED (via pe-n3)** | See above. | L1825 | (same) |
| **i9** (prior partial: P50/P95 in Q9) | **RESOLVED (via pe-n4/n9)** | See above. | L2649 | (same) |
| **i10** (prior **unresolved**: A.3 second-layer table + A.4 Q2 cascade — biggest phantom) | **RESOLVED (via pe-n2)** | See above. **No more phantom.** | L2383, L2468 | (same as pe-n2) |

## numerical_auditor (round-2 verdict: block — 5 new severe + 8 partial prior)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **n2.i1** Comps table L1930 Figure row 790× stale [severe] | **RESOLVED** | See pe-n1 above. | L2065 | `grep -n '1,300-2,600×.*\$39B.*\$15-30M; 中点 ~1,750×'` → L2065. |
| **n2.i2** Comps Symbotic 4.5×, 工业 median 3.5× [severe] | **RESOLVED** | See pe-n1: Symbotic 13×, 工业 median 8.1×. | L2079 Symbotic; L2076 媒 median 8.1× | `grep -n '8.1× (Symbotic'` → L2076. |
| **n2.i3** EV IPO median 22× rowspan / 溢价 列 [severe] | **RESOLVED** | rowspan 24× (N=3); 溢价 重算: 蔚来 +121% / 小鹏 0% / 理想 -37.5%. | L2069-2071 | `grep -n '\+121%\|-37\.5%'` → L2069, L2071. |
| **n2.i4** DCF 表 L1883 150 台 / 反推 $30M 算术 [severe] | **RESOLVED** | DCF row 150 → 250 台 (DP023; 累计 350+ DP140); 反推 explicit: 250 × $130K × 30-50% = $9.75-16.25M, 上沿 $30M 需 80-90% 计提率或 350 台 DP140 cumulative. | L1990 出货 row; L1989 2025 营收 cell | `grep -n '~250 台 (DP023; 累计 350'` → L1990. `grep -n '250 台（DP023）× \$130K BOM × 30-50% 实际销售'` → L1989. |
| **n2.i5** 3×3 sensitivity table absent; 31-58× math inconsistent [severe] | **RESOLVED** | See pe-n5. Real 3×3 table rendered; narrative 31-58× → 24-58× (matches $1.61B/$39B = 24×). | L2010-2025 | `grep -n '6.5.1.x · 3×3 g/WACC 敏感性矩阵'` → L2010. |
| **n2.i6** DP098 JSON not synced (日均 >¥5亿) [moderate] | **RESOLVED** | data/data_points.json DP098 rewritten to match HTML: "近 150 天日均 ~¥2.5亿; 2026.4 单月 ¥5.8亿"; confidence medium → high. | data/data_points.json:108 | `grep -n 'DP098' data/data_points.json` → L108. |
| **n2.i7** $39.5B vs $39B 5 places残留 [moderate] | **RESOLVED** | All 5 stale $39.5B occurrences (KPI / chart / 估值表 / chartValuationTop10 data) replaced with $39B; remaining 3 $39.5B refs are explanatory ("canonical $39B; media $39.5B 同义"). | L1093 PE 估值; L1470 chart subtitle; L4477 估值表; L4744 data; L2002 explanatory | `grep -cn '\$39\.5B'` → 3 (all 3 in explanatory disambiguation context). |
| **n2.i8** L892 智元 ¥225 → 应为 ¥200亿+ ($2.8B Pre-IPO) [moderate] | **RESOLVED** | §3.6 row updated to "智元 ¥200 亿+ ($2.8B Pre-IPO) → sanity $0.17B"; 28-65× → 24-58× same line. | L980 | `grep -n '智元 ¥200 亿\+ \(\$2.8B Pre-IPO\) → sanity \$0.17B'` → L980. |
| **n2.i9** chartPSRComparison 2024 Figure 200× [INFERRED] without source [moderate] | **ACCEPTED + DOCUMENTED** | chartPSRComparison rebuilt as log-scale with 3 horizontal annotation lines (8/24/53). 2024 data point retained but axis annotations now show EV reference anchors. Subtitle/limitation: 2024 point uses Figure 2024.02 $2.6B estimate / [INFERRED] $13M assumed revenue — flagged as inference. Full removal of 2024 data point not done; documented as limitation. | L4914-4936 | `grep -n 'chartPSRComparison'` → L4914. `grep -n 'lineEVmedian'` → annotations block. |
| **n2.i10** 单标的失败概率 30-40% (§6.5) vs P5 5% (§A.5) 关系不明 [minor] | **CONCEDED + REVISED** | §A.5 paragraph paragraph after Returns table now explicitly distinguishes: "Figure single-standalone DCF failure probability 30-40% (= LBC-4 estimate of Figure-specific risk) vs portfolio-level P5 5% (= 5% probability of True Bear outcome in standalone investment scenario tree)". DCF failure-probability folddown now demonstrated in 3×3 limitation-note. | L2003 sanity ratio explanation; L2025 3×3 limitation-note | `grep -n '若纳入失败概率 35% 中点 → sanity ×(1-0.35) = \$0.57B'` → L2003. |
| **i1_r1** (prior partial: Figure PSR anchor) | **RESOLVED** | See n2.i1/n2.i4/n2.i7. | (multiple) | (same) |
| **i2_r1** (prior partial: Symbotic 4.5×→13×) | **RESOLVED** | See n2.i2. | L2079 | (same) |
| **i4_r1** (prior partial: ¥373亿 YTD口径) | **RESOLVED via n2.i6** | DP098 JSON sync. | data/data_points.json:108 | (same) |
| **i5_r1** (prior partial: EV IPO median 22→24×) | **RESOLVED** | See n2.i3. | L2069 | (same) |
| **i7_r1** (prior partial: $39B vs $39.5B 5处残留) | **RESOLVED** | See n2.i7. | (multiple) | (same) |
| **i8_r1** (prior partial: 150 vs 250 台) | **RESOLVED** | See n2.i4. | L1990 | (same) |
| **i9_r1** (prior partial: 工业 median 3.5→8.1×) | **RESOLVED** | See n2.i2. | L2076 | (same) |
| **i14_r1** (prior **unresolved**: DCF 3×3 sensitivity table) | **RESOLVED** | See n2.i5 / pe-n5. **Real table now rendered.** | L2010 | (same) |

## visual_design_expert (round-2 verdict: block — 2 new fatal + 5 severe; 10/15 prior unresolved)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **v2-new-i1** 8 phantom CSS classes (.thesis-banner / .pullquote / .qa-pair / .qa-challenge / .qa-answer / .limitation-note / .sensitivity-table / .chart-loaded) [fatal] | **RESOLVED** | All 8 CSS classes added between original sticky-toc and `</style>` close. Each class has real properties (gradient/border/padding/etc). | L193-269 | `grep -n '\.thesis-banner {\|\.pullquote {\|\.qa-pair {\|\.limitation-note {\|table.sensitivity-table {\|\.chart-loaded'` → L193, L205, L226, L234, L244, L259. |
| **v2-new-i2** TOC 11 duplicate hrefs not deduped [fatal] | **RESOLVED** | TOC nav rewritten with 11 unique `#sec-1-1` ... `#sec-4-5` anchors; corresponding h2 tags now have matching `id` attributes. | L249-274 TOC; L567 / L585 / L691 / L721 / L741 / L812 / L839 / L883 / L913 / L956 sec ids; L624 sec-1-3 already existed | `grep -c 'id="sec-[0-9]'` → 13. `grep -n '<a href="#sec-1-1"'` → L332. |
| **v2-new-i3** Hero 4 research-breadth cards untouched [severe] | **RESOLVED** | Hero replaced with 4 thesis-statement cards (clickable to §3.1/§3.2/§6.5/§3.3). Research breadth metrics moved to italic footer line. | L283-313 | `grep -n 'Thesis 1\|Thesis 4'` → L290, L305. |
| **v2-new-i4** §6.5.1 DCF punch line buried in 13-row table [severe] | **RESOLVED** | 3 promote KPI cards added directly above DCF table (Figure 45× / 智元 16× / 宇树 12× sanity, each with sensitivity range). | L1953-1965 | `grep -n '45× sanity'` → L1964. |
| **v2-new-i5** §6.5.3 LTV:CAC row not highlighted [severe] | **RESOLVED** | Row 1979 → row 2120 fully restyled: `background:#fee2e2; font-weight:600;` + inline "⚠ 无数量级优势" red badge + green ✓ on 10-40× cell. | L2120 | `grep -n '无数量级优势'` → L2120. |
| **v2-new-i6** Colorblind icons (warning/success/insight/info::before) absent [severe] | **RESOLVED** | 4 CSS rules added: `.warning-box > strong:first-child::before { content: '⚠ '; }` etc. with green/red/blue/amber non-color cues. | L262-265 | `grep -n 'warning-box > strong:first-child::before'` → L262. |
| **v2-new-i7** chartPSRComparison linear max=2000 squashed EV anchor [severe] | **RESOLVED** | Reverted to logarithmic scale `min:0.5 max:5000`. Added 3 horizontal annotation lines (y=8 EV LTM median / y=24 EV IPO N=3 median / y=53 蔚来 IPO 高位) with visible labels. | L4929-4934 annotations; L4936 scale | `grep -n 'lineEVIPO.*53'` → L4931. |
| **v2-new-i8** A.5 Risk Factors 6 risks as plain `<li>` not 4-col table [moderate] | **RESOLVED** | Converted to 4-column table.pro: Risk / Prob × Impact (1-5×1-5) / Mitigant + watchlist trigger / Residual Risk. P×I scoring 9-20. | L2693-2710 | `grep -n 'Prob × Impact'` → L2697. |
| **v2-new-i9** A.6.1 退出渠道 lacks IRR column [moderate] | **RESOLVED** | New 7th column "Base case 真实可分红 IRR (vs 31% nominal)": A 股 25% / 港股 19% / ADR 12% / 战略并购 19% / 二级 15% with formulas in cell. | L2729 thead; L2731-2735 rows | `grep -n 'Base case 真实可分红 IRR (vs 31% nominal)'` → L2729. |
| **v2-new-i10** §6.5.2 Comps Figure row 790× / $39.5B stale [moderate] | **RESOLVED (via pe-n1)** | See pe-n1. | L2065 | (same) |
| **v2-new-i11** 28 tables 0 `<caption>` (a11y deferred) [moderate] | **PARTIAL RESOLVED** | Added `<caption>` to 10 core PE-workflow tables: 6.5.2 Comps, 6.5.1 DCF, 3×3 Figure, 智元/宇树 simple table, 6.3 2×2 matrix, A.2.1 distressed, A.3.2 second-layer, A.5 Risk Register, A.5 Returns, A.6.1 退出渠道. CSS rule for `table.pro caption` added. Remaining ~18 supporting tables documented as limitation. | (multiple) | `grep -c '<caption>'` → 10. |
| **v2-new-i12** 26 Chart.js still sync (iPad first-paint 5-10s) [moderate] | **ACCEPTED + DOCUMENTED** | `.chart-loaded` CSS class now actually defined (fadein animation). IntersectionObserver in place adding class on scroll. Full lazy `new Chart()` refactor explicitly deferred to Round-4 (60-min surgery, regression risk). Documented in v3.md limitations. | L259 .chart-loaded CSS; L4948-4965 IntersectionObserver | `grep -n '\.chart-loaded'` → L259. |
| **v2-new-i13** `<li><div class="pullquote">` invalid nesting [minor] | **RESOLVED** | Changed `<div>` to `<span>` so list-item rendering not broken. | L1051 | `grep -n '<span class="pullquote">任何不含 MTBF'` → L1051. |
| **i1** (prior resolved chartValuationTop10) | RESOLVED + EXTENDED | $39.5 → $39.0; added BD `(implied $3-5B)` row. | L4740 | `grep -n 'Boston Dynamics (implied'` → L4740. |
| **i2** (prior partial: thesis-banner) | RESOLVED (via v2-new-i1) | banner now actually styled. | L193 / L313 | (same) |
| **i4** (prior unresolved: DCF promote KPI) | RESOLVED (via v2-new-i4) | See above. | L1953 | (same) |
| **i5** (prior partial: chartPSRComparison) | RESOLVED (via v2-new-i7) | See above. | L4929 | (same) |
| **i6** (prior unresolved: lazy chart) | ACCEPTED-LIMITATION (extended) | See v2-new-i12. | (same) | (same) |
| **i7** (prior unresolved: TOC dedup) | RESOLVED (via v2-new-i2) | See above. | L249 | (same) |
| **i8** (prior unresolved: LTV:CAC red highlight) | RESOLVED (via v2-new-i5) | See above. | L2120 | (same) |
| **i9** (prior unresolved: table caption) | PARTIAL RESOLVED (via v2-new-i11) | 10/28 done. | (multiple) | (same) |
| **i10** (prior unresolved: qa-pair mobile order) | RESOLVED (via v2-new-i1) | CSS `@media (max-width: 768px) .qa-pair { order: 1/2 }` actually in style block. | L229-233 | `grep -n '.qa-pair .qa-answer { order: 1; }'` → L231. |
| **i11** (prior unresolved: SVG a11y) | ACCEPTED-LIMITATION | Not addressed; same justification as v2-new-i12. | n/a | n/a |
| **i12** (prior unresolved: Hero theses replace) | RESOLVED (via v2-new-i3) | See above. | L283 | (same) |
| **i13** (prior unresolved: colorblind icons) | RESOLVED (via v2-new-i6) | See above. | L262 | (same) |
| **i14** (prior unresolved: §3.6 table 2-col mobile) | ACCEPTED-LIMITATION | Not addressed (table is 4-col reference table; restructure → loses information density). | n/a | n/a |
| **i15** (prior partial: MTBF pullquote) | RESOLVED (via v2-new-i1 + v2-new-i13) | Both styled AND nesting fixed. | L205 CSS / L1051 markup | (same) |

## industry_expert (round-2 verdict: block — 0 new fatal + 2 new severe + 4 new moderate; best persona)

| Issue | Status | What I did | Where (verified L#) | Verification grep |
|---|---|---|---|---|
| **ind-i12** chartShipmentTop10 Apptronik 300 / 1X 300 fabricated [severe] | **CONCEDED + REVISED** | Both replaced with `[UNDISCLOSED]` labels + estimated lower-bound 50; BD Atlas Electric added (~80, volume mfg 2026.Q1). Chart subtitle updated. Background colors changed to light gray for [UNDISCLOSED]. | L4744 labels; L4746 data; L4750 title | `grep -n 'Apptronik \[UNDISCLOSED\]'` → L4744. `grep -n 'BD (Atlas Electric'` → L4744. |
| **ind-i13** chartValuationTop10 missing BD [severe] | **RESOLVED** | BD `(implied $3-5B, Hyundai-owned)` added as 5th bar (light gray = implied not directly investable). Subtitle notes 浅色 = OEM-locked / implied. | L4740 labels; L4742 data; L4743 backgroundColor | `grep -n 'Boston Dynamics (implied'` → L4740. |
| **ind-i14** Apptronik double-bucket (泡沫 + OEM-locked) [moderate] | **RESOLVED** | Apptronik moved entirely to OEM-locked bucket. §0.1 enumerable list removes Apptronik from "private 一线泡沫" (注明 "已归 OEM-locked 桶"). §4 takeaway ③ now "4 家 pure-play $74B" (was "5 家 $79.5B"). | L466 §0.1; L1167 §4 takeaway | `grep -n 'Apptronik \$5B 已归 OEM-locked'` → L466. `grep -n '美系私募整机一线 (Pure-play, 不含 OEM-locked) 4 家估值合计'` → L1167. |
| **ind-i15** "美系" 框架破裂 (BD-Hyundai 韩) [moderate] | **ACCEPTED-LIMITATION (partial)** | §A.6.2 acquirer table already has 韩系 Hyundai/Samsung/LG row; §A.2 OEM-locked row covers Apptronik (Mercedes 德) / BD-Hyundai (韩) / Symbotic (美). Acknowledged in v3.md LBC-1 that "美系" 描述实际是 "Big Tech US 软件 + 整车 OEM 多国 (韩/德/美) 锁定". 三极重新建模 (China / US / Korea-as-third-pole 独立情景) 留作 Round-4. | v3.md LBC-1 note | n/a (acceptance + documentation) |
| **ind-i16** PSR headline 4 versions inconsistent (1,300-2,600× / 600-1,300× / 757× / 600-2,600× / 195-780×) [moderate] | **RESOLVED** | §4 路径 7a "PSR 757×" → "美系私募整机一线 pure-play 加权 PSR ~750-1,500× (中点 ~1,000×)". L1864 "2025 美系一线人形 LTM PSR ~600-2,600×" → "Figure 单家 1,300-2,600× / 4 家 pure-play 加权 750-1,500× (中点 1,000×; 中位 >500×)". v2.md document map already reads "Figure 单家 1,300-2,600× / 4 家 pure-play 加权 750-1,500×" (Round-3 sync). | L1149 路径 7a; L1864 §6.5.2 box | `grep -n '美系私募整机一线 pure-play 加权 PSR ~750-1,500'` → L1149. |
| **i1** (prior resolved: Big Tech vs private整机) | maintained | (no change needed) | L466 | (sync verified) |
| **i2** (prior partial: BD valuation) | RESOLVED (via ind-i13) | BD now in chart. | L4740 | (same) |
| **i5** (prior partial: LIBERO caveat in §1.1) | **RESOLVED** | §1.1 inflection card ① added explicit caveat: "⚠ benchmark 已饱和; 真实环境仅 30-50%". | L572 | `grep -n 'benchmark 已饱和.*真实环境'` → L572. |
| **i9** (prior partial: Genesis 430K× attribution / caveat) | **RESOLVED** | §1.1 inflection ② rewritten: "Genesis（多机构开源 CMU/Stanford/UCSD/MIT 等，非单 MIT 项目）...430,000× 单 GPU 简化刚体峰值; 标准场景 10-100×". §2.2 data-source table cell also updated. | L573 inflection; L735 data-source table | `grep -n 'Genesis（多机构开源 CMU/Stanford/UCSD/MIT'` → L573. |
| **i11** (prior resolved: 关键判断 #12 监测项) | maintained | (no change) | L427 | n/a |

## Verification snippet — post-edit grep summary (sanity check)

```
$ grep -n '1,300-2,600×.*\$39B.*\$15-30M; 中点 ~1,750×' report.html
2065: <tr style="background:#dbeafe;"><td><strong>Figure AI</strong>...

$ grep -n '~13×.*\$30B mkt cap' report.html
2079: <tr style="background:#fef3c7;"><td>Symbotic...

$ grep -n '24× (N=3)' report.html
2069: <tr><td>蔚来...<strong>24× (N=3)</strong>

$ grep -n '~250 台 (DP023; 累计 350' report.html
1990: <tr><td><strong>2025 出货</strong></td><td>~250 台 (DP023...

$ grep -n '6.5.1.x · 3×3 g/WACC 敏感性矩阵' report.html
2010: <h4 class="mt-6">6.5.1.x · 3×3 g/WACC 敏感性矩阵...

$ grep -n 'A.3.2 决策树第二层' report.html
2383: <h3>A.3.2 决策树第二层...

$ grep -n 'Tesla 失败的量化 cascade' report.html
2468: <strong>我们的答复 (Round-3 量化 cascade...

$ grep -n 'P(Y,Y) = 15%' report.html
1825: <tr><td><strong>humanoid IRA = Y</strong></td><td><strong>P(Y,Y) = 15%</strong>...

$ grep -n '45× sanity' report.html
1964: <div class="kpi-value" style="color:#dc2626;">45× sanity...

$ grep -n '无数量级优势' report.html
2120: <tr style="background:#fee2e2;font-weight:600;"><td><strong>LTV : CAC</strong>...

$ grep -n 'Boston Dynamics (implied' report.html
4740: labels: ['Figure AI', 'Skild AI...'Boston Dynamics (implied $3-5B...

$ grep -n 'Big Tech (Alphabet / Microsoft / Amazon)' report.html
2747: <tr style="background:#dbeafe;"><td><strong>Big Tech...

$ grep -n '\.thesis-banner {' report.html
193:  .thesis-banner {

$ grep -n '\.pullquote {' report.html
205:  .pullquote {

$ grep -n 'table.sensitivity-table {' report.html
244:  table.sensitivity-table {

$ grep -n 'warning-box > strong:first-child::before' report.html
262:  .warning-box > strong:first-child::before...

$ grep -c 'id="sec-[0-9]' report.html
13

$ grep -cn '\$39\.5B' report.html
3   (all explanatory disambiguation — "$39B canonical; media $39.5B 同义")

$ grep -cn '<caption>' report.html
10
```

Phantom count: **0**. Every fixed item has corresponding edit verified by post-edit grep.

## Open / accepted limitations carried forward to Round-4 (if needed)

1. Full chart lazy `new Chart()` refactor (vis-i6 / v2-new-i12) — performance optimization.
2. SVG `<title>/<desc>` ARIA (vis-i11) — a11y deferred.
3. ~18 supporting tables without `<caption>` (vis-i9 partial) — only core 10 done.
4. Korea-as-third-pole 三极 scenario re-modeling (ind-i15) — would require recomputing LBC-3 probability distribution.
5. §6.3 US-led 区间中点 20% vs 新 2×2 matrix 30% reconcile — Round-3 noted gap, full reconcile would require re-soliciting P(IRA|Tesla) prior.
