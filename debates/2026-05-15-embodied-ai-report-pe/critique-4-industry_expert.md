# Round-4 Critique · Industry Expert

## Verdict

**BLOCK** — Round-3 5 条 prior issues 中 i17 / i18 / i19 / i20 / i15 / i21 全部 resolved 或 substantive 论证, 是 round-4 真正修复了 round-3 留下的产业链 framework 矛盾。但 round-4 在修复 r3-n2 (US-led +10pp) 时漏掉 §6.3 Bifurcation 卡片的 '40%' 大字号 (新 +5pp gap), 在 §A.5 Bear-B 行触发列与 Exit 估值列对 control premium 用了两个不同倍数 (1.3-2× vs 3×), 在 chartShipmentTop10 修复 BD 80 fabrication 时 subtitle 新增 '30 单位 Hyundai 内部 pilot' 无引用数字, 6 路径对照表没有 add row 同步 path-card 区域新建的 7a/7b/7c。

## What this draft is trying to do

商业研究 / 产业链格局分析 / PE 投资判断报告 (zh-CN, PE/VC 合伙人级 IC 决策辅助材料 — round-4 修订后)

## Load-bearing claims

1. **LBC-1** · 美强软件 (二层拆分: Big Tech 基础模型层 + 私募整机层) / 中强硬件; round-4 把 Apptronik 整体且一致地移至 OEM-locked 桶, 新建 子路径 7c, §4 路径②标题与 6-路径对照表同步
2. **LBC-2** · 2030 年度 TAM \$30-144 亿 (中位 \$75 亿); 2025 真实工业部署 < 1,000 台 conceded
3. **LBC-3** · 三情景 35/25/35/5 (China-led/US-led/Bifurcation/Other; round-4 SST), 2×2 (P(Tesla Y)=25%, P(IRA|Y)=50%, P(IRA|N)=10%) → 12.5/12.5/7.5/67.5 = 100% reconciled
4. **LBC-4** · Figure 单家 LTM PSR 1,300-2,600× / 美系一线 pure-play 4 家 (不含 Apptronik) 加权 PSR 750-1,500× / 中系 22× = EV IPO N=3 中位 24×
5. **LBC-5** · 中系核心零部件 + 稀土 alpha + 美系 OEM-locked (Apptronik 7c / BD-Hyundai 7b / Symbotic) + Distressed M&A 10 家 per-company subtable; Korea = US-led satellite (非独立第三极)

## Issues

### i22 [moderate] · §6.3 Bifurcation 卡片 L1800 仍显示 '40%' 而 SST 是 35%, builder 'propagated to 9 locations' 漏掉了 §6.3 主卡片本身

**Attacks**: LBC-3 (三情景 SST 35/25/35/5 全报告一致性)

Round-4 r3-n2 fix 把 Bifurcation 从 40% 下调到 35% (为了 US-led 从 20% 上调到 25% 而保持 Σ=100%)。response-4.md 列 9 个 propagated locations, 但漏掉了 §6.3 三情景 **Bifurcation 卡片本身** (L1797-1812): L1800 大字 `<span class="text-3xl font-bold" style="color:#92400e;">40%</span>` 仍是 round-3 的 40%。

这一卡片紧邻 §6.3 2×2 矩阵 (L1820-1832), 矩阵 derive 出 'Bifurcation 主干 27.5% + 偏 US 一支 7.5% = 35%' 与卡片大字 40% 直接矛盾 **+5pp**。

§0.2 L481 已写 'Bifurcation (30-40%；中点 35%, 基准; Round-4 调整：US-led 上调后 Bifurcation 等量下调 5pp 保持 Σ=100%)', 即 builder 明确承认 Bifurcation 中点已下调到 35%; chartScenarioProb data=[35,35,25,5] 也是 35%; 但 §6.3 卡片用大字 40% 而非 35% 或 '30-40%' 区间, 是显式数字与 SST 不符。

builder 在 response-4 强调 'Round-3 +10pp gap fully resolved' 但实际是 round-3 留了 US-led +10pp, round-4 修这个的过程又留了 Bifurcation +5pp。

**What would resolve**:
1. §6.3 Bifurcation 卡片 L1800 大字 '40%' → '35%' 或显示区间 '30-40% 中点 35%';
2. 跑一次 `grep -n '40%' v4.report.html | grep -i bifurcation` 确认 0 残留。

---

### i23 [moderate] · §A.5 Bear-B 行触发列 '1.3-2× DCF sanity' 与 Exit 估值列 '$0.17B × ~3×' 内部自相矛盾 — 同一行用两个 control premium 倍数

**Attacks**: LBC-5 / Distressed M&A control premium 假设的一致性

Round-4 r3-n5 接受 Bear-B / True Bear 拆分, builder 在 L2688 Exit 估值列加 footnote: '$0.5B (= $0.17B DCF sanity × ~3× control premium 假设上限; 注: 典型 distressed M&A control premium 1.3-1.5× — 我方 prior 3× 隐含 国资战投 + 数据资产残值)'. 这部分诚实承认 3× 是 author's prior — OK。

但同一行触发列 (L2688 第 3 个 `<td>`) 仍写 '港股 IPO 失败 + 比亚迪 / 美的 **strategic acquire at 1.3-2× DCF sanity**' — 即触发条件描述里 control premium 是 1.3-2×, Exit 估值列里 control premium 是 3×。同一 row, 两个不同 control premium 数字 (1.3-2× vs 3×), IC 读者无法 reconcile。

如果 Bear-B 真的是 '1.3-2× DCF sanity', Exit valuation 应是 \$0.17B × 1.5 ≈ \$0.26B, MOIC = 0.067×, 而不是当前 0.13× (用 3×)。

参照 §A.6.1 退出渠道 ASP 矩阵 L2738 '战略并购 (Strategic M&A): 1.3-2× 公平价值 (control premium)' — 这一行也是 1.3-2×, 即报告的市场参考标准 = 1.3-2×。Bear-B Exit 估值用 3× 不与 §A.6.1 同步。

**What would resolve**:
1. Bear-B 行触发列改写 'distressed strategic acquire at 3× DCF sanity (我方 prior 国资战投 + 数据资产残值; 高于 §A.6.1 标准 control premium 1.3-2×)';
2. 或 Exit 估值改为 1.3-2× × \$0.17B ≈ \$0.22-0.34B (mid \$0.28B), MOIC 0.07×, IRR ~-40% — 与 §A.6.1 标准一致;
3. 任选其一, 不可两个倍数并存。

---

### i24 [minor] · chartShipmentTop10 subtitle 在修复 BD 80 时新增 '2025 仅 30 单位 Hyundai 内部 pilot' — 30 是无引用新数字 (i18 fix 同模式 mini fabrication)

**Attacks**: LBC-1 / 出货格局 source quality

Round-4 i18 fix 把 BD 数据值 80 → null + 标签 '[NOT YET IN PRODUCTION]' — 正确修复。但 chart title (L4772) 写 'BD Atlas Electric = NOT YET IN PRODUCTION (null, 不是 80; 2026.Q1 量产起点; **2025 仅 30 单位 Hyundai 内部 pilot**, 非 commercial)'.

'30 单位 Hyundai 内部 pilot' 是新引入的数字, 报告其他位置 (§3.1 评分卡 L820-829 / §4 路径 7b L1150 / §6.2 投资项目表 L1619) 都没有 '30 单位'; 也没有 BD/Hyundai 一手 source citation. BD CES 2026 keynote 和 Hyundai 2025 投资者日材料都没有 '30 internal pilot units' — 这是 builder 自己在 subtitle 里 invent 的具体数字。

参照同图其他位置: Apptronik 已标 [UNDISCLOSED]; 1X Tech 已标 [UNDISCLOSED; NEO 投产 2026.4]。BD 应该用同样标准, '2025 = 0 commercial; pre-production units 数量未公开 [UNDISCLOSED]'。

**What would resolve**:
1. chart title '2025 仅 30 单位 Hyundai 内部 pilot' → '2025 = 0 commercial; pre-production / engineering units 数量未公开 [UNDISCLOSED]';
2. 或保留 30 数字但加 source citation。

---

### i25 [minor] · §4 路径 7c 在 path-card 已建立但 '6 种路径对照' 表仍只有 6 行 — IC 读者无法在同一张表内对比 OEM-locked 路径 15-25% vs Figure 路径 30-40%

**Attacks**: LBC-1 / IC actionability 表格完整性

Round-4 i17 fix 在 §4 path-card (L1086-1156) 建立: 路径 ② = Figure only; 子路径 7a = Big Tech 基础模型层; 子路径 7b = BD-Hyundai-DeepMind; 子路径 7c = Apptronik × Mercedes / Jabil. 但 '6 种路径对照' 表 (L1162-1176) 仍只有 6 行, 路径 ⑦ (a/b/c) 不在表里 — IC 读者在同一张表里看到 path ② Figure 30-40% 失败率, 看不到 'OEM-locked Apptronik / BD-Hyundai 15-25%' 在同列对比。

核心 takeaway 第 ⑤ 条 '路径⑦ (DeepMind 间接 + BD-Hyundai) 是非 Scaling-Law-binding 对冲' — IC 读者读到这里想知道路径 ⑦ 失败率, 但对照表里找不到, 必须翻回 path-card 文字。

这是 round-3 i17 'what_would_resolve' 第 (3) 条 '新增对照表 row ⑦b' 没有执行。Severity = minor 因为信息在 path-card 文字里有, 但 IC dashboard 失了一层 actionability。

**What would resolve**:
1. 表 caption '6 种路径对照' → '8 种路径对照';
2. 添加 3 行: '⑦a Big Tech 基础模型层 | 间接 / 不可直投 | 通过 Alphabet 二级 + 战略并购窗口 | 不可量化 (cap-protected)'; '⑦b BD-Hyundai-DeepMind | 整车 OEM + 外购大模型 | Hyundai 2028 30K/yr 兑现度 | 15-25%'; '⑦c Apptronik × Mercedes / Jabil | OEM-locked + Google 投资 | Mercedes pilot → commercial 2026 H2 | 15-25%'。

---

## Status of prior issues

| ID | Status | Reasoning |
|---|---|---|
| **i17** Apptronik 双桶 (round-3 half-fix) | **resolved** | §4 路径 ② 标题 L1086 改 'Figure (Apptronik 移出)'; 6 路径对照表 row ② L1169 同步; 新增子路径 7c L1155 与 BD-Hyundai (7b) 同级; §4 takeaway ③ '4 家 $74B' 排除 Apptronik; §A.2 矩阵 L2302 'Apptronik 单列入 OEM-locked 行'. round-3 half-fix 完整闭合. |
| **i18** chartShipmentTop10 BD '80' fabrication | **resolved** | 数据值 80 → null (L4766); label '[NOT YET IN PRODUCTION]' (L4763); 灰色 backgroundColor (L4767); chart title 明确 '2026.Q1 量产起点; 不是 80' (L4772). 主修复完整. (subtitle 新增 '30 单位' 数字 — 见 i24 minor.) |
| **i19** 路径 7b 'BD 高于 Figure' 反向 cherry-pick | **resolved** | L1150 显式反转: 'BD Atlas L2-L3 与 Figure 大致 tied... BD 的论证强度实际低于 Figure'. 并标 'round-3 路径 7b 文案 \"BD 高于 Figure\" 是反向 cherry-pick, round-4 已修正'. 诚实反转。 |
| **i20** US-led 30% vs 20% +10pp gap | **resolved** | US-led 25% 一致传播到 9 处 (§0.2 / §3.6 / §6.3 卡片 / 2×2 / SST footnote / §A.3.2 / §A.3.3 / chartScenarioProb / data-confidence). SST 显式声明 'Round-3 +10pp gap fully resolved'. (Bifurcation 40% 漏改是 round-4 自己新引入的, 不算 i20 unresolved — 见 i22.) |
| **i15** Korea 三极 framing (round-3 punt) | **resolved** | §6.3 L1834 新增 info-box, 三条 substantive 论据: BD = Hyundai 全资 ⊂ US-side 延伸; Korean component 链 not-full-stack (无 VLA/仿真/数据飞轮独立栈); Japan 类比. PE 暴露三路径在 US-led / Bifurcation 内已覆盖. 监测条件: 若 Korea+Japan+Israel 形成第三阵营则 LBC-3 重建. 这是 'argue against' 而非 punt。 |
| **i21** Atlas \$420K originofbots secondary | **resolved** | §3.5 L1528 标 [SECONDARY SOURCE: originofbots.com $420K; BD/Hyundai 一手未披露 sticker]. source quality 显式 flag, 与一手 source 区分, IC 读者可见 tier 差异。 |

---

`persona=industry_expert, verdict=block, prior=6R/0P/0U, new=0F,0S,2M,2m`
