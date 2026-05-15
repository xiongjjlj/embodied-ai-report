# Round-2 Critique — industry_expert persona

## Verdict: **BLOCK**

11 条 round-1 issues 中 **8 条 resolved** / **3 条 partial**（i2 BD 在 chart 缺失；i5 LIBERO 97.1% 在 §1.1 拐点卡片仍 misleading；i9 Genesis 430,000× + "MIT-led" 在 §1.1 + §2.2 仍未加 caveat — 与 §5.3 fix 自相矛盾）。Round-2 修订引入 **2 条 severe + 3 条 moderate 新问题**，其中 i12 (chartShipmentTop10 fabricated 数字) + i13 (chartValuationTop10 BD 缺失) 直接动摇玩家盘点诚实度与估值生态完整性。

---

## What this draft is trying to do

商业研究 / 产业链格局分析 / PE 投资判断报告（zh-CN，PE/VC 合伙人级 IC 决策辅助）。Round-2 修订重心：把 Google DeepMind / BD-Hyundai 纳入框架（path ⑦）；细化"美系软件"二层；稀土卡点拆分 alpha / beta；Figure 营收锚改 [INFERRED] $15-30M；引入 hierarchical reasoning 融合趋势叙事。

## Load-bearing claims (round-2 修订后)

1. **LBC-1** · 美强软件、中强硬件 — 美系软件已拆为 (a) Big Tech 基础模型层 + (b) 私募整机层
2. **LBC-2** · 2030 年度新增出货 25-80 万台 / TAM $30-144 亿（中位 $75 亿）/ CAGR 69-113%
3. **LBC-3** · 三情景概率 China-led 30-40% / US-led 15-25% / Bifurcation 35-45% / Other ~5%
4. **LBC-4** · 美系私募整机一线 PSR 1,300-2,600× 系统性泡沫；中系 IPO 全口径已对齐 EV IPO 中位 24×；纯人形 segment 仍接近美系下限
5. **LBC-5** · 中系核心零部件 + 稀土卡点 = PE alpha 主战场 — 稀土拆 (a) 具身专属 alpha + (b) 稀土 beta + (c) 终端定点未确认

---

## 新问题（按严重度排序）

### i12 [severe] · chartShipmentTop10 round-2 重排引入了两条无来源 "玩家盘点" 数字（Apptronik ~300、1X 300）

v1→v2 chartShipmentTop10 (L4565-4578) 在剔除 Tesla 1,000 之后填入：
- `'Apptronik (~300)'` — 2025 全年出货
- `'1X Technologies 300'` — 2025 全年出货

两家均未公开披露 2025 出货量：

- **Apptronik**：报告自己在 §3.1 评分卡 L737 写 "仍处 pilot；商业 scale 目标 2026 H2"；§3.2 订单表 L782 标 [UNDISCLOSED] 且 D (PoC) 级。300 台与"D 级 PoC"矛盾。WebSearch 2026.05 状态确认仍在 Mercedes / GXO / Jabil pilot 阶段。
- **1X**：§4 路径③ L1013 自己写 "NEO 2026.4 投产 Hayward" — 2025 不可能有 300 台真机出货，充其量是工程样机 + alpha 测试机 < 50 台。

修复过程把 selection-bias 错误（v1 把 Tesla 1,000 美化）置换成 fabrication 错误（凭空填 Apptronik 300 + 1X 300）。Chart 是 IC 读者 60 秒拿到的"玩家盘点视觉"，并排条形展示未披露数字 = visual smoking gun，复核失败时全章估值锚都会被怀疑。

更尖锐的是：'Apptronik 300 台' 与 §0.1 / §4 takeaway 把 Apptronik 列为 '$5B 私募一线泡沫' 的论证脱节 — 若真有 300 台出货 + Mercedes 多年合同，$5B 估值反倒比 Figure 更合理；要么估值不是泡沫，要么 300 台不是真实。两者不能同时成立。

**这正是 §3 第三章自己批判的 'demo 当生产力' / 'PR 数字当 KPI' 错误。**

**What would resolve**:
1. chartShipmentTop10 把 'Apptronik (~300)' 和 '1X Technologies 300' 标 [UNDISCLOSED] 灰色虚线，或改为 '< 100 (pilot)' 区间
2. 图表 subtitle 加 '出货数据基于公司公开披露或 IDC，未公开者标 [UNDISCLOSED] 不列入数值排序'
3. 如保留数字，必须给出推算逻辑（类似 Figure $15-30M [INFERRED] 标注）
4. 同步审查 chartOrderTop10 / chartValuationTop10 是否有类似 round-2 引入的 fabrication

---

### i13 [severe] · chartValuationTop10 把 BD 排除 — 与 §4 路径 7b 的 "BD implied $3-5B" 直接矛盾

round-2 修订核心动作是把 BD-Hyundai 纳入路径 7b（L1062 '2028 30K/yr = LBC-2 中位 6% 单一公司锁定' + L1066 'BD 隐含估值 ~$3-5B'）。但 chartValuationTop10 (L4547-4561) 仍是 v1 的 10 家：

```
Figure $39.5B / Skild $14B / PI $11B / Apptronik $5B / Neura $4.4B /
银河通用 $3B / 智元 $2.8B / 星海图 $2.8B / 宇树 $1.7B / 星动 $1.4B
```

BD implied $3-5B 应排在 Apptronik $5B / Neura $4.4B / 银河通用 $3B 同梯队，按中点 $4B 应排第 5-6 位，挤掉的应该是星动纪元 $1.4B 或星海图 $2.8B。**但 chart 完全没有 BD。**

连锁问题：
- IC 读者打开报告先看 chart — 视觉直觉里 BD 仍 invisible，path 7b 的文字补全在视觉层无效
- §4 takeaway ③ 强调 "BD-Hyundai 是美系软件不全是泡沫的反锚"，但 visual evidence 反锚不存在
- Apptronik 在 chart 出现 $5B + 路径 7b 文字把它列入 OEM-locked + takeaway ③ 又算入 '$79.5B 私募一线' — 三处身份冲突（详 i14）

**What would resolve**:
1. chartValuationTop10 加入 'Boston Dynamics (implied $3-5B)' 条形（灰色 + 'implied/not directly investable' tag），与 Apptronik / Neura 同梯队
2. chart subtitle 加 '美系 OEM-locked (BD-Hyundai / Apptronik) 用浅色区分'
3. 同步 chartShipmentTop10 加 BD（公开宣称 '2026 全部产能给 Hyundai + DeepMind, volume manufacturing 已启动'）

---

### i14 [moderate] · Apptronik 同时被归入 "私募一线泡沫" 和 "OEM-locked 非泡沫" 两个互斥桶

Apptronik 在三个地方矛盾出现：

| 位置 | 归类 |
|---|---|
| §0.1 L373 | 列入 '美系估值远高于中系：Figure $39B、Skild $14B、PI $11B、Apptronik $5B' = **私募一线泡沫** |
| §4 路径 7 + A.2 OEM-locked 行 L2159 | 'Apptronik (Mercedes pilot)' = **OEM-locked 非泡沫** |
| §4 takeaway ③ L1094 | "美系私募整机一线 4 家估值合计 ~$79.5B（路径② Figure $39B + Apptronik $5B；路径③ 1X $10B；路径④ PI $11B + Skild $14B）" = **私募一线泡沫**，且 '4 家' 计数与列表 5 家矛盾 |

且 takeaway ③ 句尾说 '不含路径⑦ BD-Hyundai / DeepMind robotics' — 但又包含 Apptronik，而 Apptronik 是路径⑦ 的子路径成员。

对 LBC-4 影响：若 Apptronik 移出 '泡沫 bucket'，'美系私募整机一线 4 家 ~$79.5B' 应改为 '4 家 ~$74.5B'；LTM 营收 [INFERRED] 也需重算；PSR 加权 600-1,300× 数字应同步变化。

**What would resolve**:
1. Apptronik 二选一：若放 OEM-locked，§0.1 + takeaway ③ 移出 $79.5B；若放私募一线，A.2 OEM-locked 行删除 Apptronik
2. takeaway ③ '4 家' / '5 家' 计数与列表对齐
3. 给一条决策规则 — '若 OEM 关系是 multi-year firm order 则进 OEM-locked，pilot 则进私募一线'

---

### i15 [moderate] · 路径 7b 标 "美系 OEM-locked" — 但 Hyundai 是韩国整车 OEM，"美系" 框架破裂

全报告以 '美系 vs 中系' 为基础对立框架。但路径 7b 实际组成：
- 整机 OEM = **Hyundai**（韩国，2021 收购 BD 80% 股权）
- 软件层 = Google DeepMind Gemini Robotics（美系）
- 制造 = 主要在美国 Georgia + 韩国 Hyundai 工厂
- A.2 矩阵 L2159 仍标 '美系 OEM-locked' — 归类不严谨

问题：
1. BD-Hyundai 30K/yr by 2028 若兑现，"中国 80-95% 出货占比" 的统计口径需重新看待 — 韩国-美国混合制造算谁？chartChinaShipmentBreakdown 完全没考虑这个第三方力量
2. Hyundai + Samsung Robot Forward 投 Apptronik / Persona AI + POSCO DX → **'Korean Inc 机器人板块' 是路径⑦ 的真正面貌**，但报告完全没把 Korea 作为独立第三阵营来呈现
3. LBC-3 三情景（中/美/双轨）可能漏掉 'Korea-anchored hybrid' 情景

**What would resolve**:
1. §0.1 / LBC-1 加注 '中美两极外，Korea 通过 Hyundai-BD / Samsung-Apptronik / POSCO-Persona 介入 OEM 锁定路径'
2. A.2 '美系 OEM-locked' 行改为 'US 软件 + Korean/欧 OEM 锁定路径'
3. §6.3 三情景推演加一行 'Korea-anchored hybrid'：若 BD-Hyundai 30K + Apptronik-Mercedes 兑现 → 2028 总 60-100K/yr 可改变 LBC-3 概率分布（Bifurcation +5pp / China-led -5pp）

---

### i16 [moderate] · PSR headline 数字在文档不同位置存在 4 个版本

| 位置 | PSR headline |
|---|---|
| §0.1 L373 | Figure 单家 LTM **1,300-2,600×**（中点 1,750×） |
| §4 takeaway ③ L1094 | 美系私募一线 4 家加权 **600-1,300×**（中点 900×） |
| §4 路径 7a L1061 | 'PSR **757×**' — v1 旧数字未更新 |
| v2.md 文档地图 L83 | '§6.5 PSR 警示 PSR **195-780× → 600-2,600×**' |

757× 仍出现是失修；600-1,300× vs 1,300-2,600× 可解释为 4 家加权 vs Figure 单家，但在没有显式 narrative bridge 下 IC 读者会视为矛盾。v2.md '600-2,600×' 暗示中系剔除了 — 但 §6.5.2 box ⑤ 明示中系 LTM PSR ~22× — 应为 '中系 ~22× / 美系 600-2,600×' 而非单一区间。

**What would resolve**:
1. §4 路径 7a 把 '757×' 改为与 takeaway 一致的 '~600-1,300×' 或 'PSR > 500×'
2. 统一一句 headline：'Figure 单家 LTM PSR 1,300-2,600×（中点 1,750×）；美系私募一线 4 家加权 600-1,300×（中点 900×）；中系一线 LTM PSR ~22× 已对齐 EV IPO 中位'
3. chartPSRComparison 把三个数字分组显示（Figure 单家 / 美系加权 / 中系一线），避免单点 1,750× 视觉孤立

---

## Status of prior issues (round-1 industry_expert.i1-i11)

| ID | 状态 | 简要判断 |
|---|---|---|
| i1 (DeepMind 缺席) | **resolved** | §0.1 两层拆分 + §4 路径⑦ 子路径 7a + §6.5.2 box ⑤ 显式限定；DeepMind 在 v2 出现 18 次（v1 仅 1 次）。框架骨架修复 |
| i2 (BD Atlas Electric 缺席) | **partial** | 路径 7b + A.2 OEM-locked 行 + §3.5 价格矩阵已纳入；但 chartValuationTop10 + chartShipmentTop10 仍未把 BD 加入视觉 Top 10（→ i13）；Apptronik 双重归属（→ i14） |
| i3 (GraspVLA cherry-pick) | **resolved** | §5.3 ⚠ caveat + §2.2 H2 2026 第三方 benchmark gate + China-led -5-10pp 条件 + 大基金溢价标注。falsifiable gate 显式建立 |
| i4 (VLA/世界模型二分过时) | **resolved** | §2.1 重写为三种实现方案（pure VLA / hierarchical S1-S2 / world-model-as-data-source）+ drop binary catalyst + Scaling Law 三源外推说明。WebSearch 验证 GR00T N1.6 (2026.01 CES) 符合 (c) 路径 |
| i5 (LIBERO 97.1% KPI) | **partial** | §5.3 KPI / §2.4 / §A.4 Q&A 都改了，但 **§1.1 第 4 拐点 ① L484 仍写 'SOTA OpenVLA-OFT 在 LIBERO 4 套件 97.1%' 完全无 caveat** — 顶层 inflection narrative 与下游章节矛盾 |
| i6 (稀土权重) | **resolved** | A.2 拆 (a) 具身专属 alpha + (b) 稀土 beta + (c) 终端定点未确认 ★★★★；金力永磁/中研股份从 ★★★★★ 降至 ★★★★ + Tesla 独家失败敏感性（IRR ÷ 2） |
| i7 (Tesla VLA 误归) | **resolved** | §2.1 'Tesla (Optimus AI)：架构未公开' + §6.3 US-led 拆双 gate。捆绑解除 |
| i8 (宇树 60% 非人形) | **resolved** | §6.5.2 box ③ 显式 '人形 segment 30-50% / 人形 PSR 50-80× 接近美系下限' + LBC-1/LBC-4 加 '中系纯人形锚需等智元/银河通用 IPO' |
| i9 (Genesis 430,000× + MIT-led) | **partial** | §5.3 L1364 改 '多机构 CMU/Stanford/UCSD/MIT' + 限定 '单 GPU 简化刚体 + 极小场景峰值 / 标准场景 vs Isaac Lab 10-100×'；但 **§1.1 拐点卡 L487 仍写 'MIT Genesis 430,000× 实时速度开源'** + **§2.2 数据来源表 L643 仍写 'Genesis 430,000× 实时速度'** — 三处中只修了一处 |
| i10 (27 款 VLA vs 8 行表) | **resolved** | v2.md 文档地图反映正确数量（8 款代表）+ accepted-as-limitation。诚实声明落实 |
| i11 (BOM 静态) | **resolved** | §0.1 limitation-note (2) 加 '2026 跨境到岸 +15-30% / 2027 双向反制深化下剪刀差实际收窄至 1.8-2.2×' + KPI 卡区间 '2.8-4.1×' + 'MS single-source' 显式标注 |

**统计**: 11 prior issues → 8 resolved / 3 partial / 0 unresolved

---

## 通过判断

- Pass criteria (industry_expert 域)：0 fatal + 0 severe
- v2 现状：0 fatal + **2 severe (i12 chartShipmentTop10 fabricated; i13 chartValuationTop10 BD 缺失)** + 3 moderate (i14 Apptronik 双重 / i15 Korean 第三极 / i16 PSR headline 多版本) + 3 partial-prior (i2 BD chart 同步 / i5 §1.1 LIBERO / i9 §1.1+§2.2 Genesis)
- **判定 BLOCK**。i12 和 i13 涉及 IC 读者最先看到的 visual anchor（两张全球 Top 10 图表）和报告自己拒绝的 demo-vs-production 标准。i14-i16 是 round-2 修订内在一致性问题，单独均为 moderate，组合表明分类框架尚未稳定。

Round-3 优先：(1) 两张 Top 10 chart 加入 BD + 修正 Apptronik/1X 出货标注；(2) §1.1 第 4 拐点卡 同步 §5.3 / §2.4 / §A.4 已修的 LIBERO 与 Genesis caveat；(3) Apptronik 归类决策 + takeaway ③ 计数对齐；(4) Korea 作为第三极的至少一句话承认 + 三情景概率影响。
