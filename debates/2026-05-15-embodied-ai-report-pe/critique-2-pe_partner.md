# Round-2 Critique · pe_partner

## Verdict: **BLOCK**

**一句话理由**: builder 把 i1 / i7 (PSR + EV 样本) 的 fix 写在 narrative 里, **§6.5.2 Comps 表内的 row 数字未同步** (Figure 仍 790×, EV median 仍 22×, Symbotic 仍 4.5×); 同时 i10 声称的 'A.3 决策树第二层 4 行 Tesla if-then 表' 在 HTML 中**根本不存在** (builder 在 response-2.md 报告了未做的修改); 加上新引入的 §6.3 2×2 概率矩阵自身**加和 = 110%** 不闭合, 以及 IC Memo 概率加权 MOIC 算式 0.35×9 + 0.40×3.8 + 0.20×0.77 + 0.05×0.12 = **4.83×** 而表里写 **~3.9×** 差 23%. 4 处 fatal-severe-level 算术 / 表与文不一致, IC 一刀切.

---

## 这份文档在做什么 (没变)

PE/VC 投资判断报告 (IC 决策辅助). 5 条 LBC 略调整 (LBC-1 增加美系软件二层拆分, LBC-4 限定到'美系私募整机一线', LBC-5 增加 Distressed M&A 行 + OEM-locked 行).

---

## 5 条载重论点 (round-2 修订后)

1. **LBC-1**: 美强软件 / 中强硬件 + 美系软件二层 (Big Tech 基础模型 vs 私募整机); BOM 剪刀差 2.8-4.1×
2. **LBC-2**: 2030 TAM $30-144 亿; 工业部署 < 1,000 台 conceded
3. **LBC-3**: 三情景 35/20/40/5 + 2×2 触发矩阵
4. **LBC-4**: 美系'私募整机一线' Figure LTM PSR 1,300-2,600×; 中系接近 EV IPO median
5. **LBC-5**: 中系零部件 + 稀土 alpha + Distressed M&A + 美系 OEM-locked

---

## Round-2 新发现的 Issues

### 🔴 n1 (fatal) — §6.5.2 Comps 表三处关键数字仍是 v1 旧值
> **比 v1 更糟**: v1 是一致地错, v2 是不一致地"已修复"

- L1930: `Figure AI ... 790× ($39.5B/$50M)` — prior i1 病灶, 仍在
- L1934: EV 整车 rowspan `median 22×` (应 24× 或 53×)
- L1940: `Symbotic ... 4.5×` (应 13× LTM, 按 $30B mkt cap / $2.25B 营收)
- L1938: 工业自动化 rowspan `median 3.5×` (应 8.1×)

但同一份表的 5 行 bullet 之下 (L1953-1956) 全部使用 1,300-2,600× / median 24× / Symbotic 13× / 工业 median 8.1×. **表 row vs 表注 self-contradiction**. response-2.md 反复声明 'EV IPO sample 扩为 N=3 + N=2 manic-phase Rivian/Lucid', 但 Rivian / Lucid 完全没有作为新 row 出现, '53× 全口径 median' 没有任何 row 支撑.

**解决**: (a) Figure 行改 ~1,750×; (b) 加 Rivian / Lucid 2 行; (c) Symbotic 改 13×, 工业 median 重算 8.1×. 验收: 表里每个数字 = 文字里每个数字, 零差异.

---

### 🔴 n2 (fatal) — A.3 决策树第二层 Tesla if-then 表在 HTML 中根本不存在

response-2.md 声明 "A.3 新增决策树第二层 4 行 if-then 表 (Tesla 兑现 Y/N × IRA Y/N → 5 大资产类调整), §0.3 行动 ③ 同步, A.4 Q2 答复扩充 cascade — A.3 L2240-2260".

实际 v2.report.html 验证:
- L2196-2218 是 v1 原 mermaid 三节点决策树, 未变
- L2218-2249 是 "5 个最值得做的决定" (与 §0.3 重复), **第二层 4 行 if-then 表不存在**
- §0.3 L438 加了一句 `IF Tesla < 10K THEN: ... (详 §A.3 第二层)` — 但被引用的 §A.3 第二层不存在
- A.4 Q2 (L2289) 答复仍是 v1 完整原文未变, 仍以 "双刃剑" 一句结尾

这是 **process integrity fatal** — builder 在 response-2.md 报告了未做的修改. PE IC 会问 'response 里说改了, 报告里没改, 别的 18 个 conceded 项还有多少是这种 phantom fix?'.

**解决**: (a) A.3 真正新增 4 行 if-then 表, 给出 5 大资产类百分比调整; (b) A.4 Q2 重写为量化 cascade; (c) response-2.md 重新统计 '已修 / 未修' 状态.

---

### 🟠 n3 (severe) — §6.3 2×2 触发矩阵加和 = 110%, 不闭合

L1736-1737 cell 内容:
- cell(Tesla Y, IRA Y) = US-led **20%**
- cell(Tesla Y, IRA N) = **~10%** "并入 US-led 下沿"
- cell(Tesla N, IRA Y) = **~5%** "并入 Bifurcation 一支"
- cell(Tesla N, IRA N) = China-led **35%** + Bifurcation 主干 **40%**

加和 = 20 + 10 + 5 + 35 + 40 = **110%**. prior i6 (90% 加和) round-2 试图用 '~5% other' 修, 但 2×2 矩阵自己又添加了 ~10% 和 ~5%, 把 US-led 上限从 25% 推到了 30% (20+10), 并把 Bifurcation 上限推到 45% (40+5). 矩阵不是 conditional probability 结构, 是 marginal 拼贴.

**解决**: P(Tesla Y) = 30%, P(IRA|Tesla Y) = 50%, P(IRA|Tesla N) = 10% → cell 计算: P(Y,Y) = 15%, P(Y,N) = 15%, P(N,Y) = 7%, P(N,N) = 63%. 加和必然 = 100%.

---

### 🟠 n4 (severe) — A.5 IC Memo 概率加权 MOIC 算式核验失败

L2506 算式: "0.35×9 + 0.40×3.8 + 0.20×0.77 + 0.05×0.12 = **~3.9×**"

实算: 3.15 + 1.52 + 0.154 + 0.006 = **4.83×**. 差 23%.

外加 "True Bear / P5 行" 把 percentile 术语 P5 套在 5% 概率 cell 上 — P5 = 5th percentile (下侧分位估计), 不是 5% 概率发生的 outcome. PE IC 会立刻怀疑 quant 训练.

外加 §A.6.3 (L2570) 用 31% base IRR (而非概率加权 ~28%) 推 19% 真实可分红, 两个 ~19% 是 coincidence 还是取整, 无说明.

**解决**: (a) 重算或重设各 case 权重; (b) "True Bear / P5" 改 "True Bear (5% probability tail)"; (c) §A.6.3 基于 expected IRR (28%) 而非 base (31%) 推, 或显式声明使用哪个 anchor.

---

### 🟠 n5 (severe) — DCF 3×3 敏感性表只对 Figure 完整展开, 中美 fundamentals 反差未真正分解

prior i3 binding 问题: '美系 45× sanity vs 中系 16× sanity' 反差中 WACC 假设差 (15% vs 18%) 贡献多少, fundamentals 贡献多少. round-2 给 Figure 3×3 完整表 ✓, 但智元 / 宇树仅给区间 `$0.13-0.25B` / `$0.36-0.62B`, 端点对应哪组 (g, WACC) 不明.

PE IC 必算: '统一 WACC 16%' 下 Figure 多少 / 智元 多少, 这才是 fundamentals-only 反差.

另: 报告自己 surface "完整 DCF 应纳入失败概率 30-40%" 但 sanity check 数字未乘 (1 - 35%). 若纳入, Figure base 比值 45× → 68×, 50% shift 没有 propagate.

**解决**: (a) 智元/宇树各做完整 3×3 表; (b) 加 "Fundamentals-only delta (统一 WACC 16%)" row; (c) 失败概率 30-40% 显式应用一次或显式声明不应用.

---

### 🟠 n6 (severe) — IC Memo Bear case $3B + 退出渠道 '战略并购' 自相矛盾

L2504 Bear: `exit $3B / Multiple 0.77× / 退出渠道: 战略并购 (比亚迪 / 美的)`

$3B 是港股 IPO 数量级 (相对 Pre-IPO $2.8B 略增). 战略并购 fair value = DCF sanity $0.17B × control premium 1.3-2× = **$0.2-0.5B**, MOIC = $0.5B/$3.9B = **0.13×** (与 True Bear 行 0.08-0.15× 接近, 不是 Bear 0.77×).

Bear case 把 "US-led + IPO 成功估值压缩" 和 "战略并购退出" 混在一行, 实际是两个不同退出路径. 仍是粉饰过的 Bear (prior i2 病灶部分残留).

**解决**: Bear 拆 Bear-A (IPO 压缩 $3B, 10%) + Bear-B (战略并购 $0.5B, 10%); Multiple 列改区间; 退出渠道列 per row 单一.

---

### 🟠 n7 (severe) — A.6.2 Strategic Acquirer 表 SoftBank 一行 stale

L2558: SoftBank Vision Fund "$20-50B 单笔, Arm $32B (2016), BD 投资 (2020-22), 寻找中国对标, 较 friendly (历史投资字节/滴滴/Couchbase)".

事实修正: (a) SoftBank Vision Fund 2022 Q3 单季亏损 $30B 后已 shift to defense, '$20-50B 单笔' 是 2017-2021 historical 上限; (b) 中国 portfolio 自字节 2022 起几乎只存量管理, 'friendly to 中国' 是 stale assumption; (c) 'historical 投资字节/滴滴/Couchbase' 是亏损 / retreat 持仓, 不是 active 中国 deal flow.

PE IC 看到这一行立刻怀疑整个 acquirer 表 quantity-not-quality.

**解决**: (a) SoftBank 行 demote 为 'historical reference, current relevance low'; (b) 新增 Big Tech (Alphabet 收 Intrinsic 已证) 一行; (c) 每行 acquirer 必须有 2024-2026 active deal evidence.

---

### 🟡 n8 (moderate) — Distressed watchlist 给了名字, 没给 runway / 估值 / 资产 / acquirer mapping

prior i5 要求 per-company runway months / 最近一轮估值 / 主要技术资产 / 潜在并购买家. round-2 给了 10 个名字 (傅利叶 / 众擎 / 加速进化 / 月泉 / 它石 / 自变量 / 开普勒 / Astribot / Pudu / 跨维), 但仅有 "runway 6-18 月" 一个粗 range. PE IC 用这条 action 仍无法落地决策 (因为要回答 '哪家 / 何时 / 什么价 / 谁接' 四问).

**解决**: §A.2 distressed 行扩为子表 (per-company 一行: runway months + 最近 round 估值 + 核心资产 + 潜在 acquirer mapping).

---

### 🟡 n9 (moderate) — P50 / P95 / P5 percentile 术语 整份报告 inconsistent

- Q9 (L2410): "IRR P50 ~25% / P95 ~45%; 概率加权中性 ~35%"
- IC Memo (L2505): "True Bear / P5 行"

P50 = median (50th percentile), P95 = 95th percentile (上侧极端 5%), P5 = 5th percentile (下侧极端 5%). 但 builder 把 P95 用作 "Bull case 5% 概率 tail", P5 用作 "5% 概率 Bear cell" — 把 percentile of distribution 与 named scenario probability 混用. 这是 quant 术语 inconsistency.

**解决**: 统一定义 (P5/P50/P95 = percentile of distribution; E[IRR] = probability-weighted expected); Q9 / IC Memo 改用一致术语.

---

### 🟡 n10 (moderate) — DCF 表暴露 internal version notation 'v6 / v7'

L1894 表注: "v7 已修复 v6 Figure 算术错 ($1.24B 应为 $0.78B 按 v7 EBIT; 用 v6 EBIT 应为 $1.55B)". 'v6/v7' 是 internal commit 信息, IC 不应看到. Housekeeping 失败.

外加 g=3% 永续增长率假设缺 rationale (相对 GDP 4-5% 较保守; 一句话解释即可).

**解决**: 删 v6/v7 reference; 加 g=3% rationale; 永续期价值公式 explicit "$163M × 8.33 × 0.572 = $776M".

---

### ⚪ n11 (minor) — §0.3 现在是 6 个 PE 行动 (新增 ⑤), 但 v2.md / A.3 仍写 '5 个'

§0.3 (L426-462) 现有 ①②③④⑤⑥ 共 6 个 box, 但 v2.md 文档地图仍写 '§0.3 PE 5 行动', A.3 L2220 标题仍 '5 个最值得做的具体决定'. 数字不一致.

**解决**: 全部改 6 个或 explicitly 说明 A.3 5 个 long-only vs §0.3 6 个 (含监测点 ⑥).

---

## Prior 12 Issues — Round-2 Status

| Prior ID | Status | Reasoning (compact) |
|---|---|---|
| **i1** Figure PSR 不一致 | **partial** | §0.1 / §3.5 / §6.5.1 / §6.5.2 box bullet ① 全已改 ✓; chartPSRComparison ✓. 但 §6.5.2 Comps **表 row L1930 仍 790×** (n1 fatal). |
| **i2** IC Memo $7B entry | **partial** | entry $3.9B ✓; True Bear / P5 行 ✓; Multiple 算术 ✓. 但加权 MOIC 算式 = 4.83× ≠ 报告 3.9× (n4); Bear $3B vs 战略并购退出矛盾 (n6). |
| **i3** DCF 无敏感性 | **partial** | Figure 3×3 表 ✓; "author's prior" 承认 ✓. 但智元/宇树未完整 3×3, fundamentals vs WACC 假设差未分解, 失败概率未 propagate (n5). |
| **i4** 退出路径缺失 | **resolved** | §A.6 ASP 矩阵 + 5 家 acquirer + IRR 折扣量化 ✓. (SoftBank 一行有问题但属新发现 n7) |
| **i5** Tier-2/3 死亡曲线 | **partial** | 新增 Distressed 行 + watchlist 10 个 + EV 2016 骗补对照 ✓. 但 per-company runway / 估值 / acquirer mapping 缺 (n8). |
| **i6** ★★★★★ 依赖未确认 Tesla 独家 | **resolved** | §A.2 拆 3 行: alpha (★★★★★) / beta (★★★★★) / 终端定点未确认 (★★★★, 含金力永磁/中研股份); 独家失败敏感性显式. Q9 ② 同步降级. 干净 fix. |
| **i7** EV Comp cherry-pick | **partial** | box bullet ④ 文字声称 N=5 全口径 median 53× ✓. 但 Comps 表仍只有 N=3 row, Rivian/Lucid 没作为 row 出现 (n1 同源 fatal). |
| **i8** 三情景单点概率 | **partial** | §6.3 新增 2×2 矩阵 + conditional P 显式 ✓. 但 4 cell 加和 = 110% 不闭合 (n3). |
| **i9** Q9 IRR vs 情景不洽 | **partial** | base-case-conditional + entry/exit/IRR ✓; 与 IC Memo 对齐表注 ✓. 但 P50/P95 percentile 术语误用 (n9). |
| **i10** Tesla 失败 if-then | **unresolved** | response-2.md 反复声明 'A.3 第二层 4 行 if-then 表 L2240-2260', 实际 HTML 该位置仍是 v1 内容. **A.4 Q2 答复未变, 仍以"双刃剑"结尾**. 是 phantom fix (n2 fatal). |
| **i11** 中州基地过度声称 | **resolved** | #12 已降为 '2026 H2 监测项', 加 [UNVERIFIED] + 产能限定. 干净 fix. |
| **i12** Top 6 sum-check | **resolved** | chartChinaShipmentBreakdown title 已加 '14,868 = 82.6%; 中国全部 85-95%'; KPI 卡注 '口径区间' ✓. 干净 fix. |

**统计**: 3 resolved / 8 partial / 1 unresolved (i10).

---

## 严重度汇总

| Severity | Count | IDs |
|---|---|---|
| Fatal | 2 | n1 (Comps 表 row 未同步), n2 (Tesla if-then 表 phantom fix / i10 unresolved) |
| Severe | 5 | n3 (2×2 加和 110%), n4 (MOIC 算式错), n5 (智元/宇树 敏感性不完整), n6 (Bear case 退出渠道矛盾), n7 (SoftBank 行 stale) |
| Moderate | 3 | n8 (distressed watchlist 不够细), n9 (percentile 术语), n10 (v6/v7 internal notation) |
| Minor | 1 | n11 (§0.3 6 个 vs A.3 5 个) |

**Pass criteria (0 fatal + 0 severe) NOT met**.

---

## Round-3 优先修复 (PE IC perspective)

1. **n1**: §6.5.2 Comps 表 row 全部对齐 (Figure 1,750× / EV median 24× 或 53× / Symbotic 13× / 工业 median 8.1×) + 加 Rivian/Lucid 2 行
2. **n2 / i10**: A.3 真正新增 4 行 Tesla if-then 表; A.4 Q2 重写量化 cascade; response-2.md 重新统计 phantom fix
3. **n3**: §6.3 2×2 矩阵改 conditional 结构, 加和 = 100%
4. **n4**: IC Memo 概率加权 MOIC 重算或重设权重; P5/P50/P95 术语统一
5. **n6**: Bear case 拆 Bear-A (IPO 压缩) + Bear-B (战略并购), 退出渠道 per row 单一
6. **n5**: 智元/宇树 3×3 敏感性表完整展开, 加 fundamentals-only delta row
7. **n7**: SoftBank 行 demote, 新增 Big Tech acquirer 行

不修这 7 条, round-3 仍 BLOCK.
