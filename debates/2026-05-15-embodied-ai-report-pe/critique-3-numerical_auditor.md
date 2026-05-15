# Critique Round 3 — numerical_auditor

## Verdict

**BLOCK** — 8/10 round-2 cell-of-record fixes resolved (the comps table, DCF 250 台, DP098 JSON, $39.5B replacement, EV IPO median 24× — these are real), but round-3 introduced **3 new severe arithmetic problems**: (a) the new 3×3 DCF sensitivity table publishes 6 cells that don't match its own stated formula (worked example: $1.255B; cell publishes $1.61B), (b) §6.3 2×2 matrix US-led = 30% vs §0.1/chart/§A.5 US-led = 20% — three places of the report use different probability distributions and only one limitation-note acknowledges the +10pp gap, (c) the IC Memo Returns table cell-header says "E[IRR] ~29%" but the inline calc immediately below it computes 26.1%, and downstream §A.6.3 uses a third number ~28%.

## What this draft is trying to do

PE-grade industry research on embodied AI (humanoid robotics) in Chinese, 5,000+ line HTML report with sensitivity DCF, comps table, IC memo, decision tree, returns table, exit channel matrix. v3 is the round-3 builder response to two prior rounds of multi-persona critique.

## Load-bearing claims

1. **LBC-1** 美强软件 / 中强硬件 — BOM 剪刀差 2.8-4.1× (MS single-source)
2. **LBC-2** 2030 TAM $30-144 亿 (中位 $75 亿)
3. **LBC-3** 三情景 (中点 35/20/40/5 = 100%); §6.3 2×2 矩阵 P(Y,Y)=15%/15%/7%/63% = 100%
4. **LBC-4** Figure LTM PSR 1,300-2,600× = 真泡沫; sanity check base $0.87B / 敏感性 24-58× / 失败概率 35% folddown → 68×; 中系 20-23× ≈ EV IPO N=3 sample median 24×
5. **LBC-5** 中系核心零部件 + 稀土永磁 = PE alpha 主战场; 美系 OEM-locked 桶 (Apptronik / BD / Symbotic) 单列

## Issues (3 severe + 4 moderate + 1 minor)

### Severe

**n3.i1 — 3×3 g/WACC sensitivity table: 9 cells, only 3 match stated formula; worked example self-contradicts cell value**

L2010-2022 publishes the matrix; L2023 limitation-note states the formula:
> cell 公式: EBIT $163M × [df_4yr + 1/(WACC-g) × df_4yr]; 例: g=3%, WACC=12%: EBIT × (0.6355 + 7.06) = $163M × 7.70 = $1.255B → 加 4-yr 折现 cash flow accumulator 后 ~$1.61B (EBIT×4×0.5×df)

Re-computed:
- Worked example: $1.255B (matches my calc) — but the **cell publishes $1.61B**.
- Accumulator patch: $1.255 + 163 × 4 × 0.5 × 0.6355 / 1000 = $1.462B, still not $1.61B.

Full grid (my calc vs published):
| g \ W | 12% | 15% | 18% |
|---|---|---|---|
| 2% | $1.14 / **$1.40** | $0.81 / **$0.81 ✓** | $0.61 / **$0.55** |
| 3% | $1.255 / **$1.61** (worked example contradicts!) | $0.870 / **$0.87 ✓** (base) | $0.645 / **$0.58** |
| 4% | $1.40 / **$1.93** | $0.94 / **$0.95 ✓** | $0.685 / **$0.62** |

Only the W=15% column matches the formula exactly. W=12% column is 23-38% **higher** than formula; W=18% column is 9-10% **lower**. The "ramp adder" rationalization in limitation-note doesn't reproduce 6 of 9 cells.

Additionally: narrative claims **"敏感性 $0.68-1.61B / 24-58×"** (§3.6 L980, §6.5.1 L2041, KPI L1965) — but actual g=3% row of the published table is **$0.58-1.61B / 24-67×**. $0.68B is not a cell value anywhere. The 58× upper bound is wrong; actual upper is 67×.

**Resolution**: (a) publish the real formula reproducing 6 non-W=15% cells; (b) fix narrative "24-58×" → "24-67×" or restate the range; (c) reconcile §3.6 / §6.5.1 / KPI cards together.

---

**n3.i2 — §6.3 2×2 matrix US-led = 30%, but §0.1/chartScenarioProb/§A.5 use US-led = 20%; +10pp gap explicitly admitted but not reconciled**

Three independent places define US-led probability:
- L480 §0.1 card: "US-led (15-25%; 中点 20%)"
- L1825-1826 §6.3 2×2: P(Y,Y)=15% + P(Y,N)=15% = US-led **30%**
- L4548 chartScenarioProb: data [40, 35, **20**, 5]
- L2691 §A.5 IC Memo: "§6.3 US-led 20% = §A.5 Bear-A 10% + Bear-B 10%"

§A.5 explicitly says "§6.3 US-led 20%" — but §6.3 actually computes to 30%. The §6.3 limitation-note L1831 admits: "US-led 30% (= 15% + 15%, 与卡片 15-25% 区间上沿一致; 已上调中点至 25%)" — but (i) range upper is 25 not 30, (ii) §0.1 still shows mid-20%, (iii) §A.5 still computes weighted MOIC using 20% US-led.

Downstream impact: re-weighting E[MOIC] with §6.3's US-led = 30% (instead of §A.5's 20%) gives:
- 0.30×9 + 0.40×3.8 + 0.15×0.77 + 0.15×0.13 + 0 = **4.36×** (vs published 4.77×)
- 9% difference depending on which prior is used.

v3.md "Limitations 5" explicitly defers reconcile to Round-4. But "documented as limitation" ≠ resolved. §A.3.2 decision tree uses §6.3 probabilities (15/15/7/63); §A.5 Returns uses §0.1 probabilities (35/20/40/5). Reader cannot consistently combine them.

**Resolution**: re-calibrate P(IRA|Tesla Y) from 50% → 33% so P(Y,Y)+P(Y,N) = 20% (consistent with cards), OR raise §0.1 card mid to 30% and re-weight §A.5 Returns. Don't carry "two priors" forward — they produce different IC outputs.

---

**n3.i3 — IC Memo Returns table cell header "E[IRR] ~29%" contradicts inline calc "26.1%" in same cell; downstream §A.6.3 uses third number "~28%"**

L2687 cell:
> **E[IRR] ~29% 名义**
> (0.35×55 + 0.40×31 + 0.10×(-5) + 0.10×(-33) + 0.05×(-35) = 19.25 + 12.4 − 0.5 − 3.3 − 1.75 = **26.1% 名义**)
> **~17% 真实 LP 可分红** (E[IRR] × 0.7 × 0.95 × 0.93)

Inline calc is mathematically correct (26.1%). But cell header says 29% — 2.9pp gap, beyond rounding.

L2691 term section gives a fourth number:
> 简化加权 4 行 24.6%, 详细 5 行 26.1%, 取整 ~28%

Also: "名义 IRR 27.3% (= 0.35×55 + 0.40×31 + 0.20×(-19) + 0.05×(-35))" — that expression actually computes to **26.1%**, not 27.3%. Another arithmetic error.

L2762 §A.6.3 uses 28%: "28% × 0.7 × 0.95 × 0.93 = ~17% portfolio-level". Math: 28 × 0.7 × 0.95 × 0.93 = 17.3% ≈ 17% ✓ (if you accept E[IRR]=28%).

But if you use the actual correct 26.1%: 26.1 × 0.7 × 0.95 × 0.93 = **16.1%**, not 17%.

So the report simultaneously shows: 29% (cell header) / 26.1% (inline calc) / 28% ("rounded up") / 27.3% (limitation note misformula). PE IC committee sees 29% in the headline cell, doesn't trust the report.

**Resolution**: pick one number (26.1% or 26%), sync L2687 header + L2691 + L2762 + v3.md changelog. Then recompute portfolio-level real IRR: 26.1 × 0.7 × 0.95 × 0.93 = 16.1% ≈ 16%, not 17%.

### Moderate

**n3.i4 — narrative "EV IPO N=2 Rivian/Lucid 175× median" has no supporting data**

L2041 + L2094: "EV IPO N=3 sample median 24× + N=2 Rivian/Lucid 175× + AI 巨头 OpenAI 50×"

But Comps table N=5 row L2073-2074:
- Rivian LTM ~85,000× (footnote A: PSR approaches infinity due to ~$0 revenue)
- Lucid LTM ~150×

175× is neither median (≈42,575×) nor mean (≈42,575×) of [85000, 150]. NTM values: Rivian ~250×, Lucid ~25× → mean 137.5, also not 175.

Footnote A itself says: "故 LTM PSR 接近无穷 — 此处用 NTM ~250× / LTM 估算 ~85,000× 仅作 manic-phase 类比锚, **不应直接平均到 median**" — yet narrative still cites 175×.

Likely a v2 residual number. Doesn't change core conclusion (Figure 1,300-2,600× is still > any version) but undermines credibility.

**Resolution**: replace "Rivian/Lucid 175×" with either "NTM mean 137×" or "Lucid alone 150× LTM (Rivian unusable due to ~$0 LTM revenue)".

---

**n3.i5 — chartPSRComparison 2024/forward data points have no sourced anchor in chart**

L4914-4938 chart data: Figure [null×6, 2024=200, 2025=1750, 2026E=1200, 2027E=600, 2028E=300]; 中系 [null×6, 2024=30, 2025=22, 2026E=18, 2027E=14, 2028E=10].

2024 Figure: $2.6B (DP129) / [INFERRED] $13M revenue = 200×. The $13M assumption is not sourced anywhere in report.

2026E/2027E/2028E forward: 1200/600/300 (Figure) and 18/14/10 (中系) — no model output disclosed, no displayed assumption for revenue ramp or multiple compression.

Builder response (n2.i9 ACCEPTED + DOCUMENTED): "Full removal of 2024 data point not done; documented as limitation." But the documentation is in v3.md (internal dev note), not in the reader-facing chart. grep finds no inline annotation explaining 2024=200 source.

**Resolution**: chart subtitle annotation: "2024 = Figure 2024.02 $2.6B / [INFERRED] $13M; 2026E-2028E forward assumes revenue ramp + 50% YoY multiple compression"; OR null out 2024 and forward data points (only plot known anchors).

---

**n3.i6 — 智元/宇树 simple sensitivity table uses WACC=21% corner without source**

L2031: "智元 下沿 (g=2%, **WACC=21%**) $0.13B"

Author's WACC table elsewhere: 智元=18% (L1997), 宇树=16%. Figure 3×3 uses W∈{12,15,18}%. Why is 智元 corner suddenly 21%? L2031 doesn't disclose the assumption (e.g., "21% = 18% + port HK liquidity 200bp + 国资 timing risk 100bp").

L2036 also claims "fundamentals-only 反差 73%, WACC 假设差 27%" — the 73/27 decomposition is not derived in the table. Reader cannot verify.

Additionally: 智元 cell formula application is inconsistent with Figure 3×3:
- 智元 base (g=3%, W=18%, EBIT=$43M) cell: $0.17B; my simple formula calc: 43 × 0.5158 + 43 × (1/0.15) × 0.5158 = $170M = **$0.17B ✓**.
- So 智元 base uses simple formula (no ramp adder), but Figure W=12%/W=18% column cells used a different adder. Inconsistent formula application across companies.

**Resolution**: add caption explaining 21% WACC upper bound; show 73/27 decomposition math; apply consistent formula to Figure and 智元/宇树.

---

**n3.i7 — v3.md changelog claims "E[IRR] 26.1% ≈ 27% (from 28% 微调)"; HTML cell still says "~29%"; downstream "~17%" uses 28%**

Four numbers, three reader-facing, all claiming "E[IRR] 名义":
- v3.md L34 (internal): 26.1% ≈ 27%
- HTML L2687 (reader-facing cell header): ~29%
- HTML L2691 (reader-facing): "5 行 detail 26.1%, 取整 ~28%"
- HTML L2762 (reader-facing, §A.6.3): "28% × 0.7 × 0.95 × 0.93 = ~17%"

Math: 28 × 0.7 × 0.95 × 0.93 = 17.32%. If using correct 26.1%: 16.14%. So "17%" downstream depends on accepting 28% E[IRR], which is wrong (correct is 26.1%).

**Resolution**: sync all four references to 26.1% (or 26%); update §A.6.3 downstream to ~16%.

### Minor

**n3.i8 — DCF revenue reverse-derivation: "$30M 上沿需 80-90% 计提率" is understated**

L1989: "250 × $130K × 30-50% = $9.75-16.25M, 上沿 $30M 需 80-90% 计提率"

Re-compute:
- 250 × 130 × 0.90 = **$29.25M** (still below $30M)
- 250 × 130 × 0.923 = $30.00M (need 92.3%)
- 350 × 130 × 0.50 = $22.75M (still below $30M)
- 350 × 130 × 0.66 = $30.03M ≈ $30M (need 350 + 66%)

Cell understates the required calibration to reach $30M upper bound.

**Resolution**: change to "上沿 $30M 需 ~92% 计提率, 或 350 台 cumulative × 66% 计提率, 或 ASP 升至 $150K+".

## Status of prior issues (round-2 → round-3)

| Round-2 issue | Status | Reason |
|---|---|---|
| n2.i1 Comps Figure 790× → 1,300-2,600× | **resolved** | L2065 cell ✓ |
| n2.i2 Symbotic 4.5× → 13×, 工业 median 8.1× | **resolved** | L2079 / L2077 ✓ |
| n2.i3 EV IPO median 22× → 24×, +9% → 0% | **resolved** | L2069-2071 全部对齐 ✓ |
| n2.i4 DCF 表 150 台 → 250 台 | **resolved** | L1990 ✓ (反推算式 minor 不精确, n3.i8) |
| n2.i5 3×3 sensitivity table 缺失 + 算术 | **partial** | 表 L2010 真实落地, 但 6/9 cell 公式不一致 (n3.i1) |
| n2.i6 DP098 JSON sync | **resolved** | data/data_points.json L108 ✓ |
| n2.i7 $39.5B vs $39B 5 处残留 | **resolved** | grep 仅 3 处, 全部 disambiguation context ✓ |
| n2.i8 §3.6 L892 智元 ¥225亿 → ¥200亿+ | **resolved** | L980 ✓ |
| n2.i9 chartPSRComparison 2024 200× source | **partial** | EV annotation lines 加了, 2024 数据点 source 仍未 chart-internal disclose (n3.i5) |
| n2.i10 失败概率 30-40% vs P5 5% reconcile | **resolved** | L2003 + L2023 + L2691 三处显式区分 standalone vs portfolio ✓ |
| i14_round_1 DCF 3×3 sensitivity (round-2 unresolved) | **partial** | 表已落地不是 phantom, 但 cell-formula inconsistent (n3.i1) |

**Summary**: 8 resolved / 2 partial / 0 unresolved. 8 new issues (0 fatal, 3 severe, 4 moderate, 1 minor).
