# critique-5 — numerical_auditor (Round-5)

## Verdict: **pass** (0 fatal + 0 severe + 3 moderate + 1 minor)

Round-5 核心数学 (capture-probability factoring) 独立可复算且与发布值对齐. 三个 round-4 moderates 全部 swept. 但 round-5 引入 3 个 moderate 残留 + 1 minor 方法学 disclosure 缺. 这些都是 SST 内部 micro-inconsistency, 不动 LBC-4 结论方向 (E[MOIC] ~2.5× / E[IRR] ~21%), 不阻 verdict.

---

## What this draft is trying to do

商业研究 / PE 视角具身智能产业链报告; 受众为 PE IC; 核心交付物 = 智元 IC Memo + 5 个 LBC + 单笔 $20-30M 跟投建议. Round-5 主要做 r4-n1 重构 — 把 'Bull 35% macro → 9× MOIC' 拆为 'macro 35% × P(智元 captures | macro)', 引入 capture-probability factor 0.4-0.6 mid 0.5.

---

## Load-bearing claims

1. **LBC-1** 美强软件中强硬件 — BOM 剪刀差 2.8-4.1×
2. **LBC-2** 2030 TAM $30-144 亿 (中位 $75 亿)
3. **LBC-3** 三情景 35/35/25/5 SST canonical
4. **LBC-4** (Round-5 重构) 智元 Returns: capture-probability factoring; E[MOIC] ~2.55× mid (range 2.0-3.0×), E[IRR] ~21% nominal mid (range 16-24%), LP real ~13% mid (range 10-15%); OLD 4.6×/24%/15% retained as 'Bull-takes-all ceiling'
5. **LBC-5** 中系核心零部件 + 稀土 + Distressed M&A 10 家 + 美系 OEM-locked (7 路径含 ⑦c) 并列

---

## Independent recomputation of Round-5 capture-adjusted math

Formula (L2691): `E[MOIC] = Σ_i [ macro_i × P(cap)_i × MOIC_cond_i + macro_i × (1-P(cap)_i) × MOIC_sunk ]`, sunk = 0.5× uniform.

### Mid case (P_china = 0.5 for Bull/Base, P_us = 0.6 for Bear-A/B, True Bear = 1.0):

| Scenario | macro | P(cap) | MOIC_cond | cap component | sunk component | row total |
|---|---|---|---|---|---|---|
| Bull | 0.35 | 0.5 | 9.0 | 1.5750 | 0.0875 | **1.6625** |
| Base | 0.35 | 0.5 | 3.8 | 0.6650 | 0.0875 | **0.7525** |
| Bear-A | 0.125 | 0.6 | 0.77 | 0.0578 | 0.0250 | **0.0827** |
| Bear-B | 0.125 | 0.6 | 0.13 | 0.0098 | 0.0250 | **0.0348** |
| True Bear | 0.05 | 1.0 | 0.12 | 0.0060 | 0 | **0.0060** |
| **Total** | | | | | | **2.5385** |

**Precise mid = 2.5385× → 标准 round-to-2dp = 2.54×**

### Sensitivity:

- P=0.4 (P_china=0.4, P_us=0.5): Bull 1.365 + Base 0.637 + Bear-A 0.0794 + Bear-B 0.0394 + TB 0.006 = **2.127×** ✓ (published 2.13)
- P=0.6 (P_china=0.6, P_us=0.7): Bull 1.960 + Base 0.868 + Bear-A 0.0861 + Bear-B 0.0301 + TB 0.006 = **2.950×** ✓ (published 2.95)

### IRR back-out (MOIC^(1/5)-1):

- 2.5385 → 20.60% nominal
- 2.127 → 16.32%
- 2.950 → 24.20%

Published "mid 21% nominal / range 16-24%" ✓.

### LP real:

20.60% × 0.7 × 0.95 × 0.93 = **12.74%** ≈ 13% mid ✓.

---

## §A.6.3 cascade verification (L2762, L2767, L2769)

- L2762: 'capture-adjusted 概率加权 E[IRR] ~21% nominal canonical, 来自 §A.5 SST cell; Round-4 ceiling 23.6% DEPRECATED' ✓
- L2767: 'capture-adjusted nominal E[IRR] = ~21% (range 16-24%); 真实 portfolio-level = 20.6% × 0.7 × 0.95 × 0.93 = ~13% real (range 10-15%); OLD 4.6× / 24% / 15% 是 Bull-takes-all ceiling DEPRECATED' ✓
- L2769: 'capture-adjusted Base contribution to portfolio = 0.35×0.5×31% ≈ 5.4% (mid)' — 数字 ✓ (0.35×0.5×31 = 5.425) 但 method-mixing 见 n5.i4

Cascade 一致, 但 L2769 5.4% 计算混用 linear method 与 SST cell 内 geometric MOIC-backout method.

---

## Round-4 issue sweep status

| Prior | Status | One-line reason |
|---|---|---|
| n4.i1 §A.5 intro 22%/$0.15B 残留 | **resolved** | L2645 改 24× / $0.17B + Round-5 tag |
| n4.i2 unified-WACC g 不齐 | **resolved** | L2040 per-company g 显式: Figure 2.15% / 智元 3% / 宇树 4.3%; 三公式独立复算 ±0.5% |
| n4.i3 column header 跨 row 不一致 | **resolved** | L2033 split 为 '智元 21% / 宇树 18%' |
| n3.i8 DCF 80-90% 算式 (r4 carry) | **unresolved** | v5.md carry-forward 列表第 7 条仍标; [INFERRED] 在位; 不 cascade; 不阻 verdict |

---

## Issues

### n5.i1 (moderate) — E[MOIC] mid headline 三处不一致 (2.55 / 2.53 / 2.54)

**Attack**: LBC-4 内部自洽 — 同一 round-5 SST cell 内, headline 标 2.55×, 数学展开式总和 2.53×, v5.md 用 2.54×. 真实精确值 = 2.5385 → 应统一标 2.54×.

**Where**:
- L2678 §7 header: 'mid 2.55×'
- L2691 summary cell strong text: '~2.55× (capture-adjusted base)'
- L2691 同 cell 展开式: 'Total: ... = 2.53× (mid P=0.5)'
- L2696 SST footnote: 'E[MOIC] ~2.55× mid'
- v5.md L36 (changelog): '2.54× (mid)'

**Why moderate**: 报告自称 SST canonical, 但 SST cell 顶层 headline (2.55) 与同 cell 内数学展开 (2.53) 不齐. reader 算 1.66+0.75+0.083+0.035+0.006 = 2.534 → 2.53, 与 headline 2.55 相差 ~0.8%. 跨文件 v5.md 又显示 2.54. 这是 round-5 新引入的 micro-inconsistency.

**Resolve**: 三处 (L2678 / L2691 / L2696) 统一 2.55× → 2.54×; 表内展开式改 '= 2.53× (mid P=0.5)' 为 '= 2.5385 ≈ 2.54×' 以避免 sum-of-rounded-inputs 截断错觉.

### n5.i2 (moderate) — Bear-B 行 sunk-residual 0.5× > capture-conditional 0.13×, 语义 inversion

**Attack**: LBC-4 (sunk-fund residual prior calibration) — round-5 引入的 sunk-residual uniform 0.5× 在 Bear-B 行造成 '失败比成功好' 的 dominance violation.

**Specifics**:
- L2689 Bear-B capture-conditional MOIC = 0.13× ($0.5B exit / $3.9B entry, 已含 ~3× control premium)
- Sunk residual = 0.5× (uniform)
- → 0.5 > 0.13, 即 '智元 输给 peer 在 Bear-B macro' (sunk recap 0.5×) 比 '智元 成功 in Bear-B' (capture exit 0.13×) 高 4×

**Semantic problem**: PE 模型里 capture-success 应 dominate capture-failure 在同一 macro 下. Bear-B macro 下 (港股 IPO 失败 + distressed M&A), 智元 真正 lose-to-peer 时, peer 也面临 distressed 环境, 智元 应该接近清零, 不可能高于 capture-success 退出值 0.13.

**Quantitative impact**: Bear-B sunk contribution 0.025 占 E[MOIC] mid 的 0.025/2.54 = 0.98%. 若改 sunk = min(0.5, capture_MOIC) = 0.13: contribution 降至 0.0065, E[MOIC] mid 从 2.5385 → 2.5200 (-0.7%, 仍在 2.0-3.0× range). 数量小, 但 concept 错.

**Resolve**: (a) 显式 cap 'sunk = min(0.5, capture-conditional MOIC) per row'; 或 (b) row-specific sunk priors (Bear-A 0.3 / Bear-B 0.1 / Bull-Base 0.5). 任一选都要在 L2696 SST footnote 显式标注 sunk-residual 不是 uniform across rows.

### n5.i3 (moderate) — L499 KPI 段 '基准情景（40%）' 仍为旧值; r4-i22 fix scope 漏扫

**Attack**: LBC-3 (SST 35% propagation completeness) — round-5 r4-i22 只修了 §6.3 Bifurcation 卡片 L1801, 但同报告执行摘要 L499 仍写 '基准情景（40%）'.

**Specifics**:
- L499 (执行摘要 关键判断 12 条 第 2 条): `<li>2. "双轨平行"是基准情景（40%）</li>`
- L481 (同段 §0.2 success-box): 'Bifurcation（30-40%；中点 35%，基准）'  ← 35% canonical
- L1833 (SST footnote): 'Bifurcation 主干 27.5% + ... = 35%'  ← 35% canonical
- L4555 (chartScenarioProb labels): 'Bifurcation 双轨平行（基准 30-40%，中点 35%）'  ← 35% canonical

`grep -n '基准情景（40%' v5.report.html → L499 (1 hit)`.

**Why moderate**: 同段内 L481 与 L499 mid-vs-top 不一致 (5pp gap), 且 r4-i22 应统一 sweep 但漏扫. KPI 段第 2 条是 IC reader 首屏看到的, 与 SST 矛盾.

**Resolve**: L499 改 '基准情景（40%）' → '基准情景（35%）' 或 '基准情景（30-40%；中点 35%）'.

### n5.i4 (minor) — E[IRR] method 切换 (linear-avg → MOIC-backout) 未 disclose

**Attack**: LBC-4 (methodology disclosure) — round-4 23.6% E[IRR] = linear probability-weighted (Σ p×IRR_cond), round-5 21% E[IRR] = MOIC-backout (E[MOIC]^(1/5)-1). 两个方法 by Jensen's inequality 给出不同答案, SST footnote 未明示方法变更.

**Verification**:
- Round-4 linear: 0.35×55 + 0.35×31 + 0.125×(-5) + 0.125×(-33) + 0.05×(-35) = 23.6% ✓
- Round-5 MOIC-backout: 2.54^(1/5) - 1 = 20.5% ≈ 21% ✓
- 若把 Round-5 capture-adjusted 用 round-4 linear method (含 sunk IRR = 0.5^(1/5)-1 = -12.94%) 重算: mid = 4.62%
- 21% 与 4.6% 都是合理 E[IRR] 但定义不同 — 16pp gap 不可调和

**Where method-mixing 在同 cell 出现**:
- L2691 表内 IRR cell: '2.53×^(1/5)−1 = 20.6% nominal' (geometric)
- L2769 同 §A.6.3: '0.35×0.5×31% ≈ 5.4% (mid) Base contribution' (linear, capture-only, 不含 sunk)
- 若把 5 行 linear Base contribution 加起来 ≠ 21% (实际 4.6%) — reader 复算两个方法都失败

**Why minor (not moderate)**: (i) MOIC-backout 是 PE 实务主流 + more conservative, 经济上更合理; (ii) round-4 23.6% 已显式 DEPRECATED as ceiling; (iii) round-5 表内主要使用一致 geometric. 主要是 L2769 把 linear-method 5.4% 与 21% geometric 并列, 不利复算 + 没在 SST footnote disclose 方法 shift.

**Resolve**: L2696 SST footnote 加 1 句 disclose: 'round-4 E[IRR] 23.6% 是 linear probability-weighted (Σ p×IRR_cond); round-5 E[IRR] 21% 是 MOIC-backout (E[MOIC]^(1/5)-1) — 后者 PE 实务更主流, 不可与 linear method 直接比较 (Jensen inequality)'. L2769 删除 '5.4% Base contribution' 或改用 MOIC scale: 'Base 行 contribution to E[MOIC] = 0.35×0.5×3.8 + 0.35×0.5×0.5 = 0.7525, 占 mid total 2.54 的 29.6%'.

---

## Status of prior issues

| Prior issue | Status |
|---|---|
| n4.i1 §A.5 intro 22% / $0.15B | **resolved** (L2645 改 24× / $0.17B + Round-5 tag) |
| n4.i2 unified-WACC g 不齐 | **resolved** (L2040 per-company g explicit, 三公式独立复算 ±0.5%) |
| n4.i3 column header '21%' 跨 row | **resolved** (L2033 split '智元 21% / 宇树 18%') |
| n3.i8 DCF 80-90% (r4 carry) | **unresolved** but [INFERRED] / non-cascading, 不阻 verdict |

---

## Round-5 marker count verification

- `grep -c 'Round-5' v5.report.html` = 15 ✓
- `grep -c 'Round-4' v5.report.html` = 23 ✓ (retained)
- response-5 self-reported counts 与实际 grep 一致.
