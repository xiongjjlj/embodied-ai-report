# Round-3 Critique — industry_expert

## Verdict: block

i12 / i13 / i9 / i5 真正 resolved。但 i14 (Apptronik 双桶) 是 "声明 resolved 实际 half-fix"：4 处移了 (§0.1 / §4 takeaway / chart / 矩阵), 2 处核心位置 (路径 ② 标题 + 6 路径对照表 row ②) 未移；i15 (Korea 三极) 显式 punt; i16 (PSR 四版本) resolved。Round-3 同步引入 1 条 severe (BD 80 台 2025 出货 fabrication) + 3 条 moderate (路径 7b BD 反向 cherry-pick / US-led 20% vs 30% +10pp 不一致 / Atlas Electric $420K secondary source)。

---

## 报告是什么

商业研究 / 产业链格局分析 / PE 投资判断报告 (zh-CN, PE/VC 合伙人级 IC 决策辅助材料 — round-3 修订后)。

---

## Load-bearing claims (round-3 更新)

1. **LBC-1** · 美强软件 (二层拆分: Big Tech 基础模型层 + 私募整机层) / 中强硬件; Apptronik round-3 声称已 "整体移至 OEM-locked 桶"
2. **LBC-2** · 2030 年度 TAM $30-144 亿 (中位 $75 亿); 2025 真实工业部署 < 1,000 台 conceded
3. **LBC-3** · 三情景中点 China-led 35% / US-led 20% / Bifurcation 40% / Other 5% — 但新 2×2 矩阵给出 US-led = 30% (15+15) 与卡片 20% 中点存在 +10pp 不一致
4. **LBC-4** · Figure 单家 LTM PSR 1,300-2,600× / 美系一线 pure-play 4 家加权 750-1,500× / 中系 22× 已对齐 EV IPO N=3 中位 24×
5. **LBC-5** · 中系核心零部件 + 稀土 alpha + 美系 OEM-locked (Apptronik / BD / Symbotic) + Distressed M&A 10 家 per-company subtable

---

## Round-2 prior issues 状态

| ID | 状态 | 关键事实 |
|---|---|---|
| **i12** (chartShipmentTop10 fabrication) | **resolved** | Apptronik / 1X 改 [UNDISCLOSED] + 估算下限 50, label / 浅色 / subtitle 都已修订 (L4757-4766). 但同步引入 BD '80' 新 fabrication → 见 new i18. |
| **i13** (chartValuationTop10 缺 BD) | **resolved** | L4740 新增 'Boston Dynamics (implied $3-5B, Hyundai-owned)' 浅灰条形; 'Apptronik (OEM-locked)' label 也加. |
| **i14** (Apptronik 双桶) | **partial** | 4 处移了 (§0.1 / takeaway / chart / 矩阵), 2 处未移 (路径 ② 标题 + 6 路径对照表 row ②). 见 new i17. |
| **i15** (Korea 三极 framing) | **partial** | builder 在 response-3.md / v3.md 显式 punt 至 Round-4; §A.2 OEM-locked 行仍标 "美系" 包含 BD-Hyundai (韩) 和 Apptronik-Mercedes (德/美); LBC-3 三极重建未做. |
| **i16** (PSR 四版本) | **resolved** | §4 路径 7a "PSR 757×" 删除 → "pure-play 加权 750-1,500×"; §6.5.2 / §0.1 / chartPSRComparison 全部 sync 至 "Figure 单家 1,300-2,600× / 4 家加权 750-1,500×" 一对 headline. |

Score: 3 resolved / 2 partial / 0 unresolved.

---

## New issues (round-3)

### i17 [severe] · i14 修订未完成 — 路径 ② 标题 + 6 路径对照表 row ② 仍把 Apptronik 与 Figure 绑定

**Attack:** LBC-1 / LBC-4 (Apptronik 单一桶归属决策的内部一致性)

**Detail:** §0.1 (L461)、§4 takeaway ③ (L1182)、chartValuationTop10 (L4740 'Apptronik (OEM-locked)' + 浅色 #93c5fd)、§A.2 矩阵 (L2299-2300) 都把 Apptronik 移出 pure-play 泡沫桶进入 OEM-locked 桶; takeaway ③ 数字 5 家 $79.5B → 4 家 $74B。

但 §4 路径 ② 标题 (L1086) 仍写 **"路径 ② · Figure / Apptronik — 端到端 VLA + B 端 RaaS"** 把 Apptronik 与 Figure 绑定在同一 pure-play 泡沫路径；L1093 'PE 估值: Figure $39B... Apptronik $5B' 与 Figure 同列。§4 章末 6 路径对照表 (L1168) row ② "Figure / Apptronik | VLA 软件 + B 端客户绑定 | $1K/月 RaaS - 8 年回本 naive | BotQ 爬产 + capex-light 验证 | 30-40%(estimate 泡沫风险)" 把 Apptronik 与 Figure 共享 "估值泡沫风险 30-40%"。

builder 在 response-3.md 声明 'CONCEDED + REVISED: Apptronik moved entirely to OEM-locked bucket' 但执行不完整 — 4 处移了, 2 处核心位置未移。同一份报告对同一公司给两个矛盾归类。6 路径对照表 row ② 失败概率 30-40% (估值泡沫风险) 与 §A.2 OEM-locked ★★★★ "非泡沫" 评分直接矛盾。

**What would resolve:**
- §4 路径 ② 标题 'Figure / Apptronik' → '路径 ② · Figure — 端到端 VLA + B 端 RaaS'，Apptronik 删除
- 路径 ② 卡片内 Apptronik 子段移至路径 ⑦ 子路径 7b (与 BD/Symbotic 同列) 或新增子路径 7c
- 6 路径对照表 row ② 改 'Figure'; 新增 row ⑦b 'BD-Hyundai / Apptronik (Mercedes) / Symbotic — OEM-locked + 软件外购 | OEM 整合 | 15-25%'

---

### i18 [severe] · chartShipmentTop10 给 BD '80' 台 2025 出货是新 fabrication

**Attack:** 结构性 / LBC-1 出货格局 (round-3 自己制造的新 fabrication)

**Detail:** Round-2 i12 攻击 chartShipmentTop10 把 Apptronik ~300 / 1X 300 填为 2025 全年出货是 fabrication; round-3 builder 把这两条改为 [UNDISCLOSED] + 估算下限 50, 这是正确的修复。

但 round-3 同时新增了第三条 'BD (Atlas Electric, volume mfg 2026.Q1)' 估值 80, **这是新的 fabrication, 重复了 round-2 同样的错误模式**:

1. §3.1 Autonomy 评分卡 L829: 'Boston Dynamics Atlas (新)... CES 2026 商业揭幕；2026 整年订单已被绑定' — 即 Atlas Electric 是 2026 产品, 2025 全年出货为 0
2. §4 路径 7b L1150: 'Atlas Electric 2026 全部产能给现代 + DeepMind, 2028 目标 30,000 台/年' — 即 2026 才开始产能
3. §6.2 投资项目表 L1619: 'Boston Dynamics: Atlas 商用量产 2026 / 2026 订单 100% 锁定' — 同样 2026 起步
4. chart 自己的 label 'BD (Atlas Electric, volume mfg 2026.Q1)' — 注意 'volume mfg 2026.Q1' 即 volume manufacturing 从 2026.Q1 开始

那么把 '80' 台填在 2025 出货柱状图里, 是把 'volume mfg 2026.Q1' 之前的 engineering 样机当作 2025 commercial shipment — 与同报告 §3.1/§4/§6.2 自相矛盾。chart subtitle 写 'Apptronik / 1X / BD 均 [UNDISCLOSED], 显示为估算下限 50-80' — 但 BD 不是 [UNDISCLOSED], 是 'not yet in production'; 两个状态不能混为一谈。

**What would resolve:**
- chartShipmentTop10 BD 数据 80 → 0 或 'N/A (2026 起量)' 或 [NOT YET IN PRODUCTION]; label 改 'BD Atlas Electric (2026.Q1 量产起点; 2025 = 0)'
- chart subtitle 修订: '[UNDISCLOSED] = 公司未披露 (Apptronik / 1X NEO 投产前)' + '[NOT YET IN PRODUCTION] = 2025 全年无出货 (BD Atlas Electric)'
- 或者把 chart 重构为 '2026E 出货预估' 而非 '2025 出货' — 这样 BD 2026 ramp + 1X NEO 2026.4 投产都能合理纳入

---

### i19 [moderate] · 路径 7b 'BD Atlas 高于 Figure' 与 §3.1 实际证据相反

**Attack:** LBC-1 / LBC-4 (Big Tech 软件 + OEM 锁定路径的论证强度)

**Detail:** §4 路径 7b (L1150) 主张 '§3.1 Autonomy 评分卡 BD Atlas L2-L3 高于 Figure "声称 L3 但有争议" 和 Tesla L0-L1'。

回到 §3.1 评分卡实际证据 (L820-829):
- **Figure 02:** L3 in-task ODD (钣金插入) + 1,250 累计运行小时 + 90,000+ 件钣金 + 30,000+ 辆 X3 (有定量证据但有遥操作质疑)
- **BD Atlas (新):** L2-L3 in part-sorting ODD + CES 2026 商业揭幕 + 量化吞吐量 [UNDISCLOSED]
- **Tesla Optimus:** L0-L1 + Musk 自己说 'not in usage in our factories in a material way'

严格读: BD 'L2-L3' 与 Figure 'L3 但有争议' 大致 tied; BD 优势完全在 'BD 没人喊它 teleop'; Figure 02 有 90,000 件钣金 / 1,250 hours 定量证据, BD 只有 'CES 2026 揭幕' + 量化吞吐量 [UNDISCLOSED]。

这是 cherry-pick: 用 'BD 的 [UNDISCLOSED] 优于 Figure 的有争议量化数据' 来支撑 LBC-1 (BD-Hyundai 是美系软件非泡沫反锚)。报告 §3 自己在 L836 警告 '任何省略 MTBF 的 PE pitch deck 都应视为尽调不完整' — 同样标准应用到自己, BD 'L2-L3 + [UNDISCLOSED]' 论证强度 < Figure 'L3 + 90,000 件钣金'。

如果 BD '高于 Figure' 不成立 → BD-Hyundai 反锚论证强度下调, LBC-1 (a)/(b) 二层拆分 PE actionability 降低。

**What would resolve:**
- §4 路径 7b L1150 改 '§3.1 BD Atlas L2-L3 与 Figure "L3 但有争议" 大致 tied; BD 优势是 (i) 整车 OEM 现金流补贴 + (ii) 没有 teleop 争议; 劣势是 (iii) 量化吞吐量 [UNDISCLOSED]'
- §A.4 加 Q&A '为什么 BD 实际证据更稀疏却仍 ★★★★?' 答案是 'PE actionability = Hyundai 二级可投 + 整车 OEM 现金流; autonomy 评级是次要论据'

---

### i20 [moderate] · §6.3 US-led 30% 新 matrix 与卡片 / pie / TOC / IC Memo 20% 中点 +10pp 不一致

**Attack:** LBC-3 (三情景概率分布的数字一致性 + IC Memo E[MOIC] 算式稳定性)

**Detail:** Round-3 §6.3 (i8 round-2 解决) 新 2×2: P(Y,Y)=15 / P(Y,N)=15 / P(N,Y)=7 / P(N,N)=63 → US-led = 30% (15+15)。

但其他位置 US-led 仍 15-25% 中点 20%:
- §0.1 L480 'US-led (15-25%；中点 20%)'
- §3.6 L992 'US-led 概率 15-25%'
- §6.3 卡片 L1783 '15-25%'
- §A.3.3 决策树 Q3 L2365 'US-led 情景 (15-25%)'
- chartScenarios pie L4548 'US-led (15-25%，中点 20%)'

§6.3 limitation-note L1831 自己写 'mapping... US-led 30% (= 15% + 15%, 与卡片 15-25% 区间上沿一致; 已上调中点至 25%)' — builder 在 round-3 自己承认 +10pp gap 是 Round-4 候选。response-3.md L168 'Round-3 noted gap, full reconcile would require re-soliciting P(IRA|Tesla) prior' — 即承认是未 reconcile 的 IC blocker。

+10pp 不是小数字。§A.5 IC Memo Returns 表 E[MOIC] cascade (L2632) Bull case 35% 概率假设依赖 US-led; US-led 从 20% 上调到 30% 后 Bull 应当 +5pp, E[MOIC] 从 4.77× 上调到约 5.2×, E[IRR] 从 26.1% 上调到约 28-29%。两套数字之间没有显式选择 = IC 读者读 §A.5 看到 E[MOIC] 4.77× 时不知道下面有 +10pp 假设漂移。

**What would resolve:**
- builder 选定一个版本: (a) P(IRA|Tesla Y)=33% 维持 US-led 20% 中点, 或 (b) 全部位置 (卡片 / pie / TOC / IC Memo / 决策树 Q3) 上调至 US-led 30% 中点
- §A.5 IC Memo Returns 表 E[MOIC] 算式必须明确依赖哪个版本
- 不接受 'Round-4 punt' — 这是 round-3 新引入的数学不一致, 应当 Round-3 修复

---

### i21 [minor] · Atlas Electric $420K 价格点来源是 secondary aggregator

**Attack:** LBC-2 价格区间 source quality discipline

**Detail:** §3.5 价格矩阵 L1527 '④ 高端 $300-500K / Atlas Electric (~$420K)' 引用 (L4195) originofbots.com — secondary aggregator, 不是 BD/Hyundai 一手披露。同报告其他价格点 (Tesla $20K / Figure $30K-50K / Unitree / NEO) 都引用一手 (公司公告 / earnings call) — 唯独 Atlas Electric $420K 用 secondary site。source quality 与报告其他位置 'IDC / GGII / MS / BofA / company announcement' 标准不一致。

**What would resolve:**
- $420K → '高端 $300-500K [Hyundai investor day 2024.12 tier]' 或注明 [SECONDARY: originofbots.com]
- 或在 §3.5 BOM 表加 footnote 'BD/Hyundai 一手未披露 sticker 价'
