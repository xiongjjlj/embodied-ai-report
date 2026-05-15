# Critique · pe_partner · Round 1

**Verdict: BLOCK**

如果让 IC 基于这份报告下注 10 亿，IC 会先怼 Figure PSR 790× 的分母——同一张表里 Figure 2025 营收一边写 [INFERRED] $15-30M、一边在 PSR 公式里用 $50M，整个"美系真泡沫 vs 中系合理"的修订核心论点就建立在这一个内部不一致的数字上；第二刀是智元 IC Memo 用 $7B post-money 算 5× MOIC 但前文 current 才 $2.8B，2.5× sell-side markup 自动锁进入场价；第三刀是 ★★★★★ 推荐"金力永磁 Optimus 独家供应商"已被自己脚注承认未确认，但优先级未相应下调。这三条都是 IC 桌上一秒能定的伤口。

---

## 这份报告在做什么

PE/VC 投资判断报告（IC 决策辅助），不是二级卖方研报。受众是 PE/VC 合伙人级。包含：当前格局（中美非对称）+ 5 年三情景 + 5 个 PE 行动 + 31 条 Checklist + 简化 DCF + Comps Quartile + Unit Economics + IC 必问 10 + 智元 IC Memo 样本。

---

## 5 条载重论点

1. **LBC-1**：美强软件、中强硬件（出货 80-95% / BOM 剪刀差 2.8×）
2. **LBC-2**：2030 年度 TAM $30-144 亿（中位 $75 亿）+ 出货 CAGR 69-113%
3. **LBC-3**：三情景概率 China-led 35% / US-led 15-25% / Bifurcation 40%
4. **LBC-4**：美系一线系统性泡沫（Figure PSR 790×），2027-2028 回调 50-70%；中系 IPO PSR 20-23× ≈ EV IPO 中位，无系统性泡沫
5. **LBC-5**：中系核心零部件 + 原材料卡点 = PE alpha 主战场（定价锚 PE 15-25×）

---

## Issues

### FATAL

#### i1 · Figure PSR 790× 分子分母自相矛盾——同一张表内 [INFERRED] $15-30M 与 PSR 公式用 $50M

**攻击对象**：LBC-4

§6.5.1 (L1831) 的"2025 营收"格明写：Figure **$15-30M [INFERRED]**（150 台 × $130K × 30-50% 计提率）。但同一表 L1846"当前 PSR"格写 **790× = $39.5B / $50M**；§6.5.2 Comps (L1878) 也是 $39.5B / $50M；§0.1、§3.5 同步引用。**$50M 既高于 [INFERRED] 区间上限 ($15-30M)，也与同报告 §3.5 RaaS 表 (L829) base case "5 万台 × $50K/年 = $2.5B 2030 收入" 隐含的 2025 量级不一致。**

按表里自己的 [INFERRED] 中位 $22.5M，PSR 应 = 1,755×；按下限 $15M = 2,633×；按上限 $30M = 1,317×。**三个数字都比 790× 显著更高**——意味着泡沫论断方向对、量级被低估。但 PE IC 不会接受"方向对就行"：同一份材料里同一个 anchor 数字给出两个值，IC 会直接质疑数据治理。这条是直接命中 LBC-4 ："美系真泡沫 vs 中系合理"的整个修订核心论点就建立在 790× 这一个数字上，而 790× 是错的。

**怎么消除**：
- (a) 二选一 Figure 2025 营收 anchor：要么坚持 [INFERRED] $15-30M 把 PSR 改为 1,317-2,633× 区间；要么放弃 [INFERRED] 用 PitchBook / The Information / Bloomberg 私募数据的硬数字
- (b) 同步修订执行摘要、§3.5、§6.5.1、§6.5.2、§6.5.3 几处一致
- (c) PSR 计算旁加注："±50% 营收变动 → PSR ±50% 同向变动"

---

#### i2 · IC Memo 智元 IRR 表的入场估值与正文 current valuation 自相矛盾——5× MOIC 是 sell-side 数学

**攻击对象**：LBC-4 / A.5

A.5 (L2420) Deal Terms："Pre-IPO 跟投 $200-300M raise、**$5-7B post-money**"。A.5 (L2429-2432) Returns 表：Bull $35B / 5.0× / IRR 38%；Base $18B / 2.6× / 21%；Bear $5B / 0.7× / -6%。

- **入场矛盾**：5.0× = $35B / $7B 隐含入场 post = $7B，但执行摘要 (L350)、§6.5.1 (L1844) 一致引用智元 current = $2.8B。**从 current $2.8B 到 entry $7B 自动 markup 2.5×**——把"IPO 跟投流动性溢价"锁进入场价，是 sell-side 银行家行为
- **Bear 粉饰**：Bear MOIC 0.7× = $5B / $7B 意味着即使 US-led + 量产延期，exit 仍 $5B / 损失 30%。但同报告 §6.5.1 sanity check 给智元 $0.17B (市场 16× sanity)；真 bear case 若 sanity 是对的，MOIC 应 = $0.17B / $7B = **0.024× / 损失 97.6%**。0.7× 是粉饰过的 bear
- **概率加权**：0.35×5.0 + 0.40×2.6 + 0.25×0.7 = **2.97× ≈ 3.0×**，算术 OK，但 inputs 全部偏 bull，"安全合理"输出是预设答案

这恰好是 sell IC Memo "CONDITIONAL PROCEED $20-30M" 建议的底层数学。PE IC 一秒看穿。

**怎么消除**：
- (a) Entry post-money 要么用当前 $2.8B + 合理 Pre-IPO premium (1.3-1.5× → $3.6-4.2B)，要么明确写"Bull/Base/Bear 均基于 $7B IPO entry，当前 round IRR 需另算"
- (b) Bear 必须包含"量产 yield < 30% + IPO 受阻 + 数据资产清零"，MOIC 0.1-0.3× 区间
- (c) 概率加权 MOIC 旁同时给"P5 MOIC"数字，让 IC 看 VaR 不是 expected value

---

### SEVERE

#### i3 · DCF sanity check 完全缺敏感性——永续期占总估值 ~90%，g/WACC 各 ±1% 就改写核心结论

**攻击对象**：LBC-4

§6.5.1 (L1842) 永续期价值占比：Figure 89.7% / 智元 88.2% / 宇树 87.0%。**三家全部 ~90% 价值来自 terminal——意味着 g 和 WACC 是真正的 driver**。报告给 g=3%, WACC 15/18/16%，0 sensitivity。

IC 必算：
- Figure WACC 12% (Microsoft/NVIDIA/a16z LP，12% 比 15% 更合理)：terminal multiple 8.33× → 11.1×，sanity 从 $0.87B → $1.13B，市场比值 45× → 35×
- g 4% (EV+ 级世代级机会)：terminal 8.33× → 9.09×，sanity → $0.94B，比值 42×
- 智元 WACC 22% (A 股/港股流动性折扣 + 脱钩 premium)：terminal 6.67× → 5.26×，sanity → $0.12B，市场比值 16× → **23× (已进入 Q4)**——"中系无泡沫"结论动摇

LBC-4 的"美系 45× sanity vs 中系 16× sanity"反差是 g/WACC 假设的二阶产物，不是 fundamentals 比较。

**怎么消除**：
- (a) §6.5.1 加 3×3 sensitivity 表（g ∈ {2%, 3%, 4%} × WACC ∈ {12%, 15%, 18%}）
- (b) 结论旁明示"对 ±2pp WACC 敏感；中美 WACC 差异 (15% vs 18%) 解释约 25% 反差"
- (c) 若做不到，至少诚实写"本表不是 fundamentals 比较，是 with author's WACC prior 的 sanity check"

---

#### i4 · 退出路径分析在 IC-grade 报告里几乎为零

**攻击对象**：structural

退出内容仅有：(1) 第四章每条一句"退出: A 股 / 港股 / 战略并购"；(2) A.4 Q3 (L2228-2238) **4 句话**写完中美脱钩下的退出；(3) A.5 智元 Returns 表只有 exit 估值，没有 exit channel、锁定期、ADR 退市定价、CFIUS 影响。

缺失的关键问题：
- A 股 vs 港股具身板块同公司估值差通常 30-60%（宁德港股较 A 股折价 30%+），报告引"宇树 A 股 ¥400 亿 / 智元港股 ¥200 亿"但没换算流动性折扣
- 港股流动性折扣 + 中概股退市风险，美元 LP 真实可分红 IRR 应 -3 至 -5pp
- **并购买家清单完全缺失**：NVIDIA / SoftBank / 比亚迪 / 吉利 / 上汽 / 美的 / 海尔 哪家可能 acquire 哪家？checkout size？历史 deal pattern（美的 KUKA / 海尔 Candy）？
- 二级流动性：A 股具身概念板块 2025-2026 涨幅 / 机构持仓集中度没量化，决定退出时谁接

PE IC 会问："你给我 5y IRR 35%，但没告诉我退出渠道、谁接、退出折扣，我不能下 10 亿。"

**怎么消除**：
- (a) 新增 §A.6 "退出路径方法论"：A 股 IPO / 港股 IPO / 美股 ADR / 战略并购 4 条通道矩阵
- (b) 至少 5 家 strategic acquirer 清单 + rationale + 历史 deal + checkout capacity
- (c) A.4 Q3 重写：基于 base rate 的退出 IRR 调整（如港股流动性折扣 30% → MOIC × 0.7）
- (d) A.5 智元 Returns 表加"退出渠道"一列

---

#### i5 · Tier-2/3 整机厂死亡曲线缺失——A.4 Q5 断言 70% 淘汰但无具体厂商 runway 排序

**攻击对象**：LBC-5 / structural

A.4 Q5 (L2268)："头部 5 家跑出 / 二线 50% 概率被并购 / 三线 (>30 家) 大概率消失"。这是断言不是分析。

- 没有 cash runway 表（融资额 / 月烧钱 / months-of-cash）
- 没有 2024-2026 已爆雷 / 已减员名单
- 没有"谁会被并购 / 谁会被清盘"的具体指认（傅利叶 / 众擎 / 加速进化 / 月泉 / 它石 / 自变量 / 开普勒 / Astribot / 跨维 等都该排序）
- 没有并购买家 mapping

**这丢掉一整条 PE alpha 路径**：distressed 二线整机 0.3-0.5× 价格收购 + 整合人才/数据资产 + 注入头部，是 EV 2018-2020 PE 跑出过的 pattern。LBC-5 现在的 PE alpha 只剩零部件方向，漏掉了"洗牌中的二线 distressed asset 收购"，但 ¥550 亿补贴退坡几乎确定催生这条赛道。

**怎么消除**：
- (a) §5.4 加 distressed-watch list 表：至少 10 家 Tier 2/3 + runway months + 最近估值 + 主要资产 + 潜在 acquirer
- (b) 新增 PE 行动 #6 "Distressed M&A 2027 H2 起"
- (c) A.4 Q5 答案补"三线 30 家具体 list"

---

#### i6 · ★★★★★ 推荐严重依赖未确认的"Tesla 独家"声明，评级与脚注承认的不确定性脱节

**攻击对象**：LBC-5

A.2 (L2084) "基础原材料卡点" ★★★★★：金力永磁（披露为 Optimus 供应商\*）、中研股份（披露为 PEEK 供应商\*）⋯⋯"\* 未经 Tesla 公开确认独家"。**脚注已诚实承认未经确认，但 ★★★★★ 评级未相应下调。**A.4 Q9 (L2339) 同样把金力永磁列为"3 个押 5y IRR > 30%"top picks 之一。

- 金力永磁全公司 2024 营收 ¥55 亿，主营钕铁硼（家电/汽车/风电/电梯），即使 Tesla 100 万台 × 5kg = 5,000 吨 / 现有产能 30,000 吨 = ~17%——但"独家定点"真伪决定 5-15× 价差
- IRR 30-40% 隐含 3 层 conditional：Tesla 独家 + 稀土卡点不被 MP/Lynas 消解 + Optimus 真兑现 100 万。3 个里任一失效，target IRR 全 break
- Tesla 历史多次否认供应商"独家"声明（宁德 / LG 储能均如此）
- PE 行动 #1 + Q9 top pick 同时依赖这一未证实点

**怎么消除**：
- (a) ★★★★★ 旁加"评级受 Tesla 独家声明确认与否影响，若否定降至 ★★★"
- (b) 或把"基础原材料卡点"分两行：★★★★★ 上游（中复神鹰/宝武镁业） + ★★★★ 终端定点未独立确认（金力永磁/中研股份）
- (c) Q9 第二个 pick 需 ≥2 个独立信息源（Tesla 10-K、投资者会议、第三方拆解）否则降到 IRR 20-25%
- (d) IRR 需做"独家失败"敏感性：若 Tesla 加 2 个供应商，单台价值量 ÷3，收益 ÷2

---

#### i7 · Comps EV IPO 中位 22× 用 3 家中国车厂样本，cherry-pick 友善对照

**攻击对象**：LBC-4

§6.5.2 (L1881-1884) EV IPO 板块仅 3 家：蔚来 53× / 小鹏 24× / 理想 15×，median 22×。**遗漏 Rivian (2021.11 IPO, PSR ~200× LTM, $86B) / Lucid (2021.7 SPAC, PSR ~150×) / Polestar / Fisker。**

- Time-symmetric 不对：蔚来 2018 IPO 是 EV "early phase"，Rivian/Lucid 2021 是 "manic phase"，humanoid 2026 更类似 manic phase
- 加入 Rivian/Lucid 后 EV IPO median 跳到 ~30-50×，智元/宇树 PSR 20-23× 反而 below median——"无泡沫"结论变更强，但"cherry-pick 友善样本得出无泡沫"是方法论问题，IC 会怼
- §6.5 (L1813)"2020 EV 中位 8× / 2021 蔚来 15-20×"与 §6.5.2 蔚来 IPO 53× 矛盾（一个 LTM 一个 NTM 峰值，不可对照）

**怎么消除**：
- (a) §6.5.2 EV IPO 样本扩到 6-8 家（+ Rivian/Lucid/Polestar/Fisker/Tesla IPO 2010），重算 median/quartile
- (b) 明确"本节 PSR 全部用 LTM (or NTM)，不混用"
- (c) §6.5 与 §6.5.2 蔚来 PSR 口径差异需明示

---

#### i8 · 三情景概率仍是 author's prior，触发条件高度相关但当 marginal 处理

**攻击对象**：LBC-3

三情景触发：China-led = "中国 ramp + 美国无 IRA"；US-led = "Tesla 100 万 + IRA"；Bifurcation = "双方推动但未脱离"。这不是 mutually exclusive 也不是 collectively exhaustive：

- "Tesla 兑现 + IRA 不推"在哪个情景？Tesla 兑现自动消解 China-led，但没 IRA 又不算 US-led
- "Tesla 失败 + IRA 推出"：政策推出但 Tesla 失败，Figure/Apptronik 受益，中国仍主导出货——不属于任何现有情景
- Tesla 兑现与 IRA 推出之间是相关变量（政策反应于产业），joint probability 远低于 marginal 乘积
- IC Memo 用 35/40/25 (US-led 取 25% 上限) 粉饰 bear；§6.3 卡片说 15-25% 区间——若取 15%，Bear 概率从 25% 降到 15%，加权 IRR 反而上升
- Bifurcation 40% 是典型"剩余概率桶"分配——研究员先定 China 35% + US 25%，剩 40% 给 Bifurcation，不是真实评估

**怎么消除**：
- (a) §6.3 重新表述为 2×2 矩阵：Tesla 兑现 (Y/N) × IRA (Y/N) = 4 cells，每 cell 给 conditional 概率
- (b) IC Memo Returns 用 marginal probability，给 P5/P50/P95 三档
- (c) 明确写出 P(IRA | Tesla 兑现) = X% vs P(IRA | Tesla 失败) = Y%

---

### MODERATE

#### i9 · Q9 "3 picks IRR 30-45%" 与正文情景概率不自洽

**攻击对象**：LBC-5 / A.4

Q9 (L2338) 给宇树 IRR 5y target 35-45%。但：
- §6.5.1 宇树 sanity $0.46B (¥3.2B)，§6.5.2 给 23× LTM PSR 接近 EV IPO 中位——fair value 在 ¥120-400 亿区间，不是确定 ¥400 亿
- IRR 35-45% 隐含 5y MOIC 4.5-6×，需要 enter ¥250 亿 → exit ¥1,000-1,500 亿——Apple/Tesla 级别 long-term 估值
- Q9 与 IC Memo Bull 不自洽：智元 Bull $35B = ¥250 亿 → ¥2,450 亿，两家 fundamentals 宇树 ≤ 智元 (毛利 30% vs 35%、出货 12 万 vs 14 万、ASP $12K vs $8.5K) 但 Q9 宇树 IRR 高于智元 Base 21%

**怎么消除**：
- (a) Q9 改 base-conditional："P50 ~25% / P95 ~45%"
- (b) 每个 pick 加 entry / exit / IRR 三数字
- (c) Q9 与 IC Memo 智元 Returns 对齐 PSR multiple 假设

---

#### i10 · Tesla Optimus 失败下游联动分析缺失，5 个 PE 行动没有 if-then

**攻击对象**：LBC-3 / LBC-4

Q2 (L2217) 一句"Tesla 失败对 Figure/Apptronik 估值是双刃剑"打发。但 §0.3 监测点 ② 是核心变量，5 个 PE 行动 ③"谨慎进入美系一线"没有 Tesla 失败时是减仓还是抄底的 if-then。

Tesla 失败下游链：
- Optimus 100 万产能预算转移到 Figure/Apptronik/Agility，但 Figure 当前仅 150 台/年 scaling 困难——美系总出货上限被打掉
- 美系真泡沫 narrative 加强，Figure $39B 预计 -50-70%
- 中系受益但稀土卡点压力降低（Optimus 是稀土最大单一买家）

§A.3 决策树没有 Tesla 兑现度这个直接 trigger 节点。

**怎么消除**：
- (a) 新增 §A.3.2 决策树第二层："IF Tesla Q3 量产 < 1 万 THEN 美系减仓 / 中系硬件加仓 / 数据基础设施加仓"
- (b) §0.3 PE 行动 ⑤ 监测点 ② 旁加链接"详见 §A.3.2"

---

#### i11 · "中州基地全球首条规模化人形产线" 当事实使用，三个限定词都未独立验证

**攻击对象**：LBC-2

关键判断 #12 (L400) + A.3 均引用此 anchor。但 2025.12 启动到 2026.05 仅 5 个月，是否真正"规模化"(年产 > 5,000 台?) 缺独立验证。"global first 电池厂 + 机器人协同"是公司新闻稿口径——Tesla Fremont/Texas 也是电池+机器人协同。

**怎么消除**：
- (a) #12 加产能限定"截至 2026.05 年化设计产能 X 台 / 实际 Y 台"
- (b) 或将 #12 从"关键判断"降为"2026 H2 监测项"

---

### MINOR

#### i12 · Top 6 出货 sum-check 与"中国 80-95%" 易混淆

**攻击对象**：LBC-1

L4316 chart：Top 6 出货 = 5,500+5,168+1,500+1,200+800+700 = 14,868 (82.6% of 1.8 万)。与 KPI "80-95% 中国全球出货占比"数值相近但语义不同（Top 6 vs 全部中国厂商）。1.8 万 - 14,868 = 3,132 给"所有其他"，含美国 + 中国 Tier 2+3 30+ 家——美国总出货可能 < 500 台。

**怎么消除**：
- (a) KPI 卡注脚加"Top 6 累计 14,868 (82.6%)；中国全部估算 15,300-17,100 (85-95%)"
- (b) 明确 IDC 95% / GGII 85% 是否同一口径（含机器狗 vs 仅人形）

---

## 总结

| Severity | Count |
|---|---|
| Fatal | 2 |
| Severe | 6 |
| Moderate | 3 |
| Minor | 1 |

Verdict 标准：0 fatal + 0 severe 才能 pass。当前 **2 fatal + 6 severe** → **BLOCK**。

最严重伤口排序（IC 桌上最先被怼）：
1. **i1** — PSR 790× 分子分母矛盾，整个泡沫 anchor 失效
2. **i2** — IC Memo 智元 IRR 用 sell-side 入场估值，5× MOIC 是粉饰
3. **i6** — ★★★★★ 推荐建立在自己承认未确认的"Tesla 独家供应商"声明上
4. **i3** — DCF sanity 90% 来自 terminal 但 0 sensitivity，中美反差大半是 WACC prior 差异
5. **i4** — 退出路径分析 4 句话写完，IC 不可能下注

修复优先级建议 builder：先修 i1 + i2 + i6（一晚可改），再补 i3 + i4 + i5（一周量级）。
