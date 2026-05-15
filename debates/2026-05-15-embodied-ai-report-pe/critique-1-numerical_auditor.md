# Round 1 — numerical_auditor critique

## Verdict

**block** · 1 fatal + 5 severe + 5 moderate + 3 minor = 14 issues.

LBC-4（估值锚）与执行摘要 KPI 卡在数字层面存在多处 self-contradicting，部分 KPI 数值与 `data/data_points.json`（cross-validated, high confidence）冲突；§6.4 与关键判断 #8 的 GDP 比率有 10× 小数点错位；§6.5.2 Comps 板块 median 与样本数学不符且关键 comp（Symbotic）的 PSR 偏低 ~3×。

## 文档分类

商业研究 / PE 视角具身智能产业链报告（zh-CN）；4,672 行 HTML + 数据 JSON 多份。

## 载重论点（已审计）

1. **LBC-1** "美强软件、中强硬件"——BOM 剪刀差 **2.8×**（$46K vs $130K，MS *Humanoid 100*）；中国出货 80-95%。
2. **LBC-2** 2030 TAM **$30-144 亿（中位 $75 亿）** + 出货 **CAGR 69-113%**，由 1.8 万→25-80 万逐年复合。
3. **LBC-3** 三情景概率：China-led **35%** / US-led **15-25%** / Bifurcation **40%**。
4. **LBC-4** Figure LTM PSR **790×（$39.5B/$50M）= 系统性泡沫**；中系 20-23× 接近 EV IPO 中位 **22×**。
5. **LBC-5** 中系核心零部件 + 稀土永磁卡点；谐波 CR3=94%、稀土中国 92%、BOM 0.5%。

---

## 重算结果概览

| 检查项 | 报告值 | 重算值 | 状态 |
|---|---|---|---|
| CAGR 1.8万→25万 (5y) | 69% | 69.25% | ✓ 一致 |
| CAGR 1.8万→80万 (5y) | 113% | 113.58% | ✓ 一致 |
| TAM 25万×$12K | $30 亿 | $3.0B | ✓ |
| TAM 80万×$18K | $144 亿 | $14.4B | ✓ |
| TAM 50万×$15K (中位) | $75 亿 | $7.5B | ✓ |
| Figure DCF perpetuity | $0.78B | $0.777B | ✓ |
| Figure Sanity total | $0.87B | $0.870B | ✓ |
| 智元 sanity | $0.17B | $0.170B | ✓ |
| 宇树 sanity | $0.46B | $0.456B | ✓ |
| 市场 vs sanity 倍数 (Figure) | 45× | 45.4× | ✓ |
| **Figure 2025 营收** | $50M (PSR 分母) **vs** $15-30M [INFERRED] | 矛盾 | **fatal** |
| **YTD ¥373亿 vs 日均 ¥2.5亿×132 天** | ¥330亿 ≠ ¥373亿 | 不一致 | severe |
| **EV IPO median[15,24,53]** | 22× | 24× | severe |
| **工业自动化 median[2.8,3.2,4.5,14]** | 3.5× | 3.85× | moderate |
| **Symbotic LTM EV/Sales** | 4.5× | ~13× ($30B/$2.25B) | severe |
| **具身补贴/GDP** | 0.08% | 0.0082% | severe (10× 错位) |
| **EV 2015 补贴/GDP** | 0.44-0.59% | 0.044-0.059% | severe (10× 错位) |
| 三情景概率加和（下限） | — | 35+15+40 = 90% | severe |
| **谐波 CR3 (Harmonic+绿的+新宝)** | 94% | 82+7+5 = 94 | ✓ |
| Figure $39.5B (HTML) vs data_points.json $39B | $39.5B | $39B | moderate (0.5B 漂移) |
| Figure 出货 150 台 (HTML) vs JSON 250 台 / 350 累计 | 150 | 250-350 | moderate |

---

## Issues

### i1 · FATAL — Figure 2025 营收 DCF 表 self-contradicting

**位置**: L1831 vs L1846 vs L830

L1831 DCF 表 '2025 营收' 单元格写：`$15-30M [INFERRED]（150 台 × $130K BOM × 30-50% 实际销售/RaaS 计提率估算）`。

但同一行末位 'PSR 2025' 写：`790× ($39.5B/$50M)`。

算术：
- $39.5B / $50M = 790× ✓ 内部 OK
- 但 $50M 与同行声称的 $15-30M [INFERRED] 互相矛盾
- 真 PSR (按 $15-30M 中点 ~$22M): 39500/22 = **1,795×**
- 真 PSR (按 $15M 下限): **2,633×**

另一处 L830：`当前 2025 营收估 $20-50M, 2025 PSR 仍 ~790×`——既给区间又锚 790× 单点。

`data/data_points.json` 交叉：
- DP023: Figure 2025 出货 **~250 台**（不是 HTML 用的 150 台）
- DP140: 'Figure 03 累计已下线 **350+ 台 (2026.05)**'（high confidence）

如果用 DP023 的 250 台 × $130K × 30-50% = **$9.75-16.25M**，与 HTML 用的 150×$130K×30-50%=$5.85-19.5M 完全错位。

**为什么 fatal**: LBC-4 整个估值结论 "美系一线 PSR 790× 是真泡沫，中系 20-23× 接近 EV IPO 中位 22× 不是泡沫" 全部建立在 Figure 790× 这个锚上。在同一表格内 (a) 把营收推断为 $15-30M、(b) 把 PSR 分母用 $50M、(c) 把 PSR 喊成 790×——三个数字两两矛盾。任何 DD 阶段的 LP 看到这一行都会问。

**Resolution**: Builder 必须 (a) 把 L1831 与 L1846 分母统一——要么用 $50M 并解释 150×$130K×30-50% 怎么得 $50M（不可能），要么改 PSR 为 1,300-2,000× 并明示 [INFERRED]；(b) 与 DP023 的 250 台对齐；(c) 同步 L830/L1846/L1878 三处的 PSR 倍数。

---

### i2 · SEVERE — Symbotic LTM EV/Sales 4.5× 严重低估，真实 ~13×

**位置**: L1888 Comps Quartile 表

报告：Symbotic 2025 EV/Sales LTM **4.5×**。

外部公开数据（Macrotrends / Yahoo Finance / Companies Market Cap）：
- Symbotic FY2025 (截至 2025-09-27) 营收 **$2.25B**（与报告 L780 一致）
- 2026.05 市值约 **$30B**（2026.02 高点 ~$33B）
- LTM EV/Sales ≈ **13.3×**（市值/营收，EV ≈ 市值因 Symbotic 现金 ~$1B 抵消 debt）

**报告偏低 ~3×**。

后果：
- "工业自动化板块 median 3.5×" 严重失真（修正 Symbotic 后 median = (3.2+13)/2 = 8.1×）
- LBC-4 对照锚 "中系 23× 远高于工业自动化 3.5× → 仍处 EV IPO 中位 22×" 的强度被削弱
- "非人形已赢得仓储战争" 框架（L793/L870）依赖 Symbotic 作为成熟期工业自动化锚，但二级市场已把它按 "AI 加成 + 高成长" 估值（13× 接近 AI 软件板块 40× 的下沿，而不是传统工业 3.5×）

**Resolution**: 重算 Symbotic EV/Sales LTM 与 NTM；重新计算工业自动化 median（建议剔除 Intuitive Surgical）；修订 L1903 "宇树 23×...接近 Symbotic / Intuitive 模式" 的结论。

---

### i3 · SEVERE — GDP 比率全部 10× 错位

**位置**: L1729 + 关键判断 #8 (L396) + L893

L1729 写：
- "¥110 亿/年 / 2025 GDP ¥134 万亿 ≈ **0.08%**"
- "EV 2015 ¥300-400 亿 / ¥68 万亿 ≈ **0.44-0.59%**"

重算：
- 110 亿 / 134 万亿 = 110e8 / 1.34e14 = **0.0082% (≈ 0.008%)**（不是 0.08%，**10× 错位**）
- 300 亿 / 68 万亿 = 3e10 / 6.8e13 = **0.0441%**；400 亿 / 68 万亿 = **0.0588%**——正确是 **0.044-0.059%**（不是 0.44-0.59%，**10× 错位**）

关键判断 #8 (L396) 同步错位："vs EV 2015 高峰 ~0.51%" 应为 ~**0.05%**。

**部分自相矛盾**:
- L893 '中国 550 亿+ 补贴已超 EV 早期占 GDP 比例'（标 '过度声称'）
- L1729 '具身补贴量级约为 EV 2015 高峰的 15-25%，远未"接近"'

两处对同一事实给相反结论。

**相对比例（具身/EV ≈ 15-25%）数学上仍然成立**（0.008/0.044 ≈ 18%）——但绝对水平给读者的印象完全错位：用 0.08% / 0.51% 让读者觉得 "具身已经接近 EV 1/6 量级，相当 substantial"；用真实 0.008% / 0.05% 让读者觉得 "占 GDP 几乎可忽略"。

**Resolution**: 修正 L1729 两组百分比（除以 10）；同步 L396；修订 L893 与 L1729 之间的方向冲突；在执行摘要 KPI 加 "占 GDP 0.008% / EV 2015 高峰为 0.044%" 让绝对水平显化。

---

### i4 · SEVERE — YTD 累计 ¥373 亿 vs 日均 ¥2.5 亿 自相矛盾，且与 JSON 冲突

**位置**: KPI L331-332 + L2020 + data_points.json DP098

L331-332: `¥373 亿 中国具身累计融资（YTD）截至 2026.05；YTD 日均 ¥2.5 亿`
L2020: `国内具身累计融资额（截至 2026.5 初）达 ¥373 亿（YTD 日均 ¥2.5 亿；2026.4 单月日均 ¥5.8 亿）`

算术：
- 2026-01-01 → 2026-05-12 = **132 天**
- ¥2.5 亿 × 132 = **¥330 亿**（不是 ¥373 亿）
- 要 ¥373 亿 / ¥2.5 亿 成立，YTD 起点需是 2025.12.15（149 天）——但 KPI 卡标 "YTD" 强烈暗示 2026 年迄今，这是误导性 framing

`data/data_points.json` DP098: `'国内具身累计融资额（截至 2026.05 初）¥373 亿，日均 >¥5 亿'`——JSON 写 **日均 >¥5 亿**，HTML 写 **¥2.5 亿**——**差 2 倍**。但 5 亿 × 132 = 660 亿 ≠ 373 亿，JSON 内部也矛盾。

再交叉 L1978 / L2020:
- 2026.2 月度 ¥160+ 亿（月度新高） → 5.7 亿/天（28 天）
- 2026.4 单月日均 ¥5.8 亿 → 174 亿（30 天）

如果 2 月就 5.7 亿/天，YTD 日均不可能是 2.5 亿/天。

**Resolution**: (a) 明确 "YTD" 起点；(b) 同步 JSON DP098 与 HTML KPI；(c) 重检 2026.4 vs 2026.2 的月度新高。

---

### i5 · SEVERE — EV IPO median 22× 计算错（应为 24×），且 N=3 + cherry-picked

**位置**: L1882-1884 Comps Quartile

报告：蔚来 IPO 53×、小鹏 IPO 24×、理想 IPO 15×；rowspan median = **22×**。

算术：
- median[15, 24, 53] = **24×**（不是 22×）
- mean[15, 24, 53] = **30.67×**

22× 既不是 median 也不是 mean，无从溯源。

**LBC-4 关键叙事的核心锚**：
- L1902: '智元 20× LTM 接近 EV IPO 中位 22×——市场估值合理'
- L1903: '宇树 23× LTM 同样处于 EV IPO 中位区间'
- L1904: '真正的系统性泡沫在美系一线'

如果 median 修正为 24×：智元 -17%、宇树 -4%；如果用 mean 30.67×：智元 -35%、宇树 -25%（语义变为 "明显低于中位" 而不是 "接近"）。

**更深层方法论问题**: N=3 + 全部中国 EV + 全部成功 IPO：
- 不含 Tesla、Rivian、Lucid（美 EV IPO）
- 不含失败 EV IPO（Lordstown、Faraday、Workhorse）
- 不含 BYD（混动起家，PSR 完全不同）
- 包含蔚来 53× 本身就是 IPO 当日高位泡沫值，把它纳入样本即提高 median

**Resolution**: 重算 median = 24×；扩样到 ≥6 家含 Tesla/Rivian/Lucid 及失败 IPO；改 L1902-1904 表述为 'within ±20% of N=3 sample median'，承认精确度。

---

### i6 · SEVERE — 三情景概率加和下限只 90%，缺 10% 未命名

**位置**: L372-376 / L1640-1672

China-led 35% + US-led **15-25%** + Bifurcation 40%：
- 下限：35 + 15 + 40 = **90%**（缺 10% 概率质量）
- 上限：35 + 25 + 40 = 100%

概率分布必须加和到 1。10% 漂浮的概率质量没有标注归属（"其他/黑天鹅/中美互不主导" 都未命名）。

**影响**: LBC-3 → 附录 A.3 的 "25% / 30% / 15% 配置" 来自概率加权后的预期收益。如果 10% 漂浮，组合权重也漂浮 ±10%。

之前 review (F3) 把 US-led 改为区间，似乎修补了 "单点 prior"，但同时引入了加和不闭合问题。

**Resolution**: (a) 显式命名 "其他/不可预测" 占 10%，或 (b) 让另外两个也改为区间使任意组合加到 100%；(c) §A.3 加注 "区间反映分布不确定性，组合配置按各情景中点加权"。

---

### i7 · MODERATE — Figure 估值 $39.5B vs JSON $39B 漂移

HTML 全篇 `$39.5B`（L327/L356/L1844/L1846/L1878 等十多处）。`data/data_points.json` DP009: `$39B`（cross-validated: Figure official + TechCrunch + Robot Report + Wikipedia, high confidence）。

差 0.5B（1.3%），但对 PSR 计算（790× vs 780×）有 10× 漂移。

**Resolution**: HTML 全部 $39.5B → $39B 与 JSON 对齐，或在 JSON 加注 $39.5B 出处。

---

### i8 · MODERATE — Figure 出货 150 vs JSON 250/350 不一致 + Top10 chart 漏 Figure

L1832 / L4449：Figure 150 台（Tech360 2026.1）。
JSON DP023：~250 台。DP140：累计 350+ 台 (2026.05, high conf, REF021)。

L4446 Top 10 出货 chart labels: `['宇树科技', '智元', '优必选', '众擎', '加速进化', '傅利叶', 'Agility', 'Tesla Optimus*', '1X', 'Apptronik']`——**Figure 完全不在 Top 10 之列**，但 DCF 表又把 Figure 当主要美系玩家用 150 台估算营收。

DCF 推算营收：150 台 × $130K × 30-50% = $5.85-9.75M（极低）；250 台 = $9.75-16.25M；350 台 = $13.65-22.75M。

如果按 DP023 的 250 台修订，PSR 应升到 2,400-4,000×（用 $10-16M 分母）。

**Resolution**: 出货数统一为 DP023/DP140；同步 Top 10 chart；重算 PSR。

---

### i9 · MODERATE — 工业自动化板块 median 3.5× 计算错 + 样本混入医疗机器人

L1886-1889: ABB 2.8×, KUKA/FANUC 3.2×, Symbotic 4.5×, Intuitive 14×; median 3.5×。

算术：median[2.8, 3.2, 4.5, 14] = (3.2+4.5)/2 = **3.85×**。

更严重：Intuitive Surgical 14× 是医疗机器人，不是工业自动化。剔除后 median[2.8, 3.2, 4.5] = **3.2×**。

如果 Symbotic 真值 13×（见 i2），重算 median[2.8, 3.2, 13, 14] = **8.1×**。

**Resolution**: 重算 median；剔除 Intuitive 或拆为独立 "医疗机器人" 板块；加注 "median 对 outlier 极敏感"。

---

### i10 · MODERATE — Figure vs 智元 5-10× 估值分层 vs 14× — 混用估值时点

L350/L356：'资本市场把软件大脑和硬件本体按 **5-10×** 估值分层'。
L1367：'Figure $39B vs 智元 **$8B+** ... 应当 9× 实际 5×'。
L1844：'智元 ¥200亿 = **$2.8B**'。

倍数：
- 用 $8B+: 39/8 = 4.9× ≈ 5×（5-10× 下沿）
- 用 $2.8B: 39.5/2.8 = **14.1×**（超出 5-10× 上限）

智元两个估值（$2.8B pre-IPO、$8B+ 港股 IPO 后预期）相差 2.9×，对应不同时点；报告未明示。

**Resolution**: 同步时点；'5-10× 分层' 改为 'pre-IPO ~14× / IPO 后预期 ~5×'。

---

### i11 · MODERATE — BOM 剪刀差 2.8× 单一来源 + cherry-picked numerator

KPI L323-324：`2.8× / $46K vs $130K (MS)`。L356：`$32K-$46K (BofA/Yole/MS)`。

剪刀差完全依赖 MS Humanoid 100 一个数据点：
- BofA $35K、Yole $32K 都是中国 BOM；只有 MS 给了美国对照 $130K
- '多源验证 BOM' 实际是 numerator 多源、denominator 单源
- 用 $46K (MS 中国) vs $130K (MS 美国) 算出 2.83×；如果用 BofA $35K vs MS $130K，3.71×；用 Yole $32K vs MS $130K，4.06×

实际范围 **2.8-4.1×**，KPI 写 2.8× 是 selected case。

**Resolution**: KPI → "2.8-4.1× 区间"；标注美国对照仅 MS 单源。

---

### i12 · MINOR — 宇树 IPO 估值 ¥400亿 vs Pre-IPO ¥120亿 混用时点

L1844 用 IPO 预期 ¥400亿 = $5.6B 算 PSR 23×。L4432 Top 10 估值 chart 把宇树标为 17 = $1.7B (Pre-IPO ¥120亿)。两个时点。

Top 10 chart ranking 不准：如果用 ¥400亿，宇树应位列 Top 3（超过银河通用、智元），但 chart 中位列第 9。

**Resolution**: 明示用 pre-IPO 还是 IPO 预期；Chart 加注 "宇树 17 (Pre-IPO)" 或更新到 IPO 锚定。

---

### i13 · MINOR — Unit Econ [INFERRED] 链式推断 + 缺敏感性

L1923-1930 RaaS LTV $200-250K / CAC $50-100K / 毛利 30-50% / NDR [UNDISCLOSED] 全部 [INFERRED]。LTV:CAC "2-5×" 这个 narrow 结论夹了三个 [INFERRED] 区间。

LTV $200-250K 在 5y 合约下年化 $40-50K，等于 BMW $25/h × 8h × 250d——**默认假设了 0% 价格涨幅、0% expansion、0% NDR、100% 续约率**——非常乐观且无支撑。如果 250 工作日改 365×24h ≈ 8760h × $25 = $219K/年 → LTV 跳到 $1.1M, LTV:CAC ~10×（颠覆结论）。

**Resolution**: 显化所有假设链；提供敏感性表。

---

### i14 · MINOR — Figure DCF 永续期占 90%，缺 g/WACC 敏感性

L1842-1843：Figure perpetuity $0.78B / total $0.87B = 90% 永续期。

g=3%, WACC=15% 单点。敏感性：
- g=4%: 总 $0.94B (+8%)
- g=2%: 总 $0.81B (-7%)
- WACC=12% (g=3%): 总 $1.25B (+44%)
- WACC=12%, g=4%: 总 $1.39B → 市场倍数 = 39.5/1.39 = **28×**（不是 45×）

"市场 45× sanity = 真泡沫" 在敏感性下应是 "**28-65× 区间**"，false-precision 风险。

**Resolution**: 6×6 敏感性表（g×WACC）；标注 "perpetuity 占 90%，对 g/WACC 极敏感"。

---

## 总结

| Severity | Count | IDs |
|---|---|---|
| fatal | 1 | i1 |
| severe | 5 | i2, i3, i4, i5, i6 |
| moderate | 5 | i7, i8, i9, i10, i11 |
| minor | 3 | i12, i13, i14 |

**Pass requires 0 fatal + 0 severe** → verdict **block**。

修复路径：i1 必须先解决（Figure 营收 / PSR / 出货三个数字必须打钉成一组）；i2/i3/i4/i5/i6 每一个都直接影响 LBC-3 或 LBC-4 的结论强度。i7-i11 修订后大概率能联动解决。
