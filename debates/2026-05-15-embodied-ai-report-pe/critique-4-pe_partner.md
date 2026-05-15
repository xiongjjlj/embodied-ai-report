# Round-4 PE Partner Critique

## Verdict

**block** — Round-4 真正落地了 SST (Single Source of Truth) canonicalization: MOIC/IRR 公式与 header 5 处严格一致, 3×3 sensitivity 9 cell 用单一闭式公式 (3 个 worked example 全可复算), 2×2 矩阵 P(Tesla Y)=25% 跨 9 处 propagation 完成 — 6/8 r3 issue 真 resolved (FATAL r3-n1 ✓ / SEVERE r3-n2 ✓ / SEVERE r3-n4 ✓ / MOD r3-n6 ✓ / MOD r3-n8 ✓ / pe-n10/n11 ✓). 但 SST canonicalization 动作本身 introduce 出新的 severe: Bull row label 把 '智元 公司-level Bull-exit (5万台量产+$35B IPO)' 与 'macro China-led 阵营 35%' 直接 set-equal, 是 category conflation — 应是 multiplicative (P(China-led) × P(智元 capture | China-led)), 真实 capture multiplier 30-50% 折下来 E[MOIC] 跌 ~50% (4.6× → 2.0-3.0×). PE IC 一眼会问. 同时 Q9 L2592-2594 仍写 P50/P95 与 L2694 'round-4 删除 P50/P95' 同文件直接矛盾.

## 文档定性

PE/VC IC 决策辅助报告, Round-4 — 数据治理已达 IC ratifiable 边缘, 唯一阻碍是 r4 新 surface 的 capture-probability conflation 与 1 处 P/X terminology 自相矛盾.

## Load-bearing claims (Round-4 update)

1. **LBC-3 SST**: 三情景 35/25/35/5 (China-led / US-led / Bifurcation / Other) propagated 全文 9 处 ✓
2. **LBC-4 SST canonical Returns**: E[MOIC] 4.6× / E[IRR] 23.6% nominal / LP 14.6% real — 公式 / header 严格一致, 跨 §0.1 / §A.5 / §A.6.3 / chartScenarioProb / data-confidence 同步
3. **LBC-4 3×3 Figure DCF**: 9 cell 用 V = EBIT × df_4yr × [1 + 1/(WACC-g)] 单一公式, 区间 $0.61-1.40B / 28-64× sanity
4. **LBC-5 三桶并列**: 中系核心零部件 + 稀土 alpha + Distressed M&A 10 家 (per-company watchlist) + 美系 OEM-locked

## Issues

### r4-n1 [SEVERE] · SST Bull row 把 "智元 5万量产 + AgiBot World 商业化兑现 → $35B exit" 与 "macro China-led 阵营 35%" 划等号 — category conflation, 折下来 E[MOIC] 4.6× → 2.0-3.0×

**Attacks**: SST canonical E[MOIC] 4.6× / E[IRR] 23.6% (LBC-4 支柱).

L2685 Bull row: "Bull (35% scenario probability, China-led)" — 35% 概率, exit $35B, MOIC 9.0×. L479 §0.2 显式 "China-led 30-40%; 中点 35%; Bull 锚". SST footnote L2695: E[MOIC] = 0.35×9 + ... = 4.598. 即 **Bull contribution 3.15 占 E[MOIC] 4.6× 的 68%** — 整个 Returns 故事的支柱.

问题: China-led 35% 是 **macro 阵营 probability** ("中国凭借硬件成本+场景密度赢得全球"), 但 Bull row trigger 是 **公司-specific** ("智元 2027 量产 5 万 + AgiBot World 商业化"). 两者不是同一个事件:
- China-led 世界可能由 宇树 / 银河通用 / 优必选 take 大头, 智元 拿不到 $35B exit
- Bifurcation 世界下智元可能 underperform $15B Base case
- 任何"macro scenario 兑现 ≠ 公司 capture full exit"

PE 标准模型: P(智元 Bull exit) = P(China-led) × P(智元 wins | China-led). Cluster 中至少 4 家国资+VC 大注 (智元/宇树/银河通用/优必选), capture-given-scenario prior 应 30-50% 中位.

**Folddown 量化**: 若 P(智元 wins | China-led) = 0.4 + 同等 prior 用于 Base:
- Bull effective P = 35% × 0.4 = 14%
- Base effective P = 35% × 0.5 = 17.5%
- Lose-share 47.5% 走"sunk fund value MOIC 0.5×"
- 新 E[MOIC] = 0.14×9 + 0.175×3.8 + 0.125×0.77 + 0.125×0.13 + 0.05×0.12 + 0.475×0.5 ≈ 1.26+0.67+0.10+0.02+0.01+0.24 ≈ **2.30×** vs SST 4.6× (跌 50%)
- 即使温和 P(capture) = 0.6 across: E[MOIC] ≈ 2.96×, 仍跌 36%

**这是 SST 治理 introduce 出的新 severe** — r4 把 Bull row 标 "China-led 35%" 是 r3 没有的明确等号 (r3 是 "P95 upside" 含糊), canonicalization 越严格 conflation 越显眼. PE IC 第一问.

**Resolve**: (a) Bull/Base/Bear-A 三 row 加 "conditional on macro scenario AND 智元 captures full scenario exit"; (b) header 改为 "E[MOIC | full capture] 4.6× / E[MOIC] capture-adjusted (prior 0.4-0.6) 2.0-3.0×" 两条并列; (c) §A.6.3 cascade 同步; (d) 替代方案: 拆 Bull 35% = Bull-A (智元 wins, 12-18%) + Bull-B (China-led 兑现但 智元 lose share, 17-23%, MOIC 1.5×).

---

### r4-n2 [MOD] · §A.5 Q9 (L2592-2594) 三 line item 仍用 IRR P50/P95 — 与 r3-n3 fix paragraph L2694 "round-4 删除 P5/P50/P95" 同章节直接矛盾

**Attacks**: r3-n3 follow-up / 数据治理.

L2694: "**round-4 删除 P5/P50/P95** percentile 术语". L2592-2594 同章节:
- ① 宇树 "exit P50 ¥400 亿 / P95 ¥1,000 亿; IRR P50 ~25% / P95 ~45%"
- ② 金力永磁 "IRR P50 ~20% / P95 ~40%"
- ③ 仿真种子轮 "IRR P50 ~30% / P95 ~80%"

Builder response r3-n3 "Deleted P5/P50/P95 percentile labels entirely" 是 over-stated. Returns table row 改了, Q9 line items 没扫.

技术上 Q9 单笔 IRR distribution percentile P50/P95 statistically 是对的 (单 distribution 的 percentile 不是 scenario probability) — 但 L2694 的禁令没给豁免, 同文同矛盾.

**Resolve**: (a) Q9 改 "IRR Base case ~25% / Bull case ~45%" 等; 或 (b) L2694 加豁免 "单笔投资 IRR distribution 仍可用 P50/P95 percentile, 此处仅禁止把 P50/P95 当 scenario name 用于 portfolio-level Returns table". 二选一.

---

### r4-n3 [MOD] · Bull trigger ("智元 5 万台量产 = China-led 阵营 100 万累计 的 5%") 与 China-led 卡片 capacity 数字不匹配 — 公司 level milestone ≠ industry level scenario

**Attacks**: LBC-3 / LBC-4 mapping consistency.

L1770-1774 §6.3 China-led 卡片: "2030 累计保有量: 中 100 万 / 美 12 万 / 其他 8 万". L2685 IC Memo Bull row: "2027 量产 5 万". 智元 5 万只占 China-led 中国 100 万累计的 5%. **即便 China-led 100% 兑现, 智元拿 5% 也不能保证 $35B exit** (取决于 winner-take-all). 与 r4-n1 相关但 angle 不同 — r4-n1 攻击 capture multiplier 缺失, r4-n3 攻击 Bull trigger description ≠ macro scenario description.

**Resolve**: Bull row trigger 改 "智元 5 万量产兑现 AND 获得 China-led 35-50% market share (5 万 / 100 万 = 5% 仅一阶段, 智元 dominant 假设需 explicit)". 或拆 Bull-A / Bull-B 见 r4-n1.

---

### r4-n4 [MINOR] · §A.6.3 channel breakdown 用 Base case 31% nominal 做分母, portfolio E[IRR] 23.6% 没在 channel 维度展开

**Attacks**: 数据治理 / r3-n1 cascade.

L2735-2739 退出渠道 ASP 矩阵 "Base case 真实可分红 IRR (vs 31% nominal)": A股 ~25% / 港股 ~19% / ADR ~12% / 战略并购 ~19% / 二级 ~15% — 全部基于 31% Base case (single scenario, P=35%). L2766 "用概率加权 E[IRR] 替代: 23.6% × discounts = 15% portfolio-level". L2768 caveat surface 了差异但**没给 portfolio cross-channel breakdown**: 如果 LP 看 A股 channel, portfolio-level 真实 IRR = 23.6 × 0.95 × 0.85 = 19.1% (不是 25%). 标准 PE IC 应两组并列.

**Resolve**: A.6.1 加第 8 列 "Portfolio E[IRR] 真实可分红 (vs 23.6% canonical)" cross-channel: 19/14.6/9.2/14.2/11.7%.

---

### r4-n5 [MINOR] · L1832 limitation-note P(N,N)=67.5% 拆 35:27.5:5 (China-led:Bifurcation主干:Other) 比例无 source — r3-n7 documented 但 split 数字本身仍是 author's prior

**Attacks**: r3-n7 follow-up.

L1827 cell (N,N) 67.5% = China-led 35% + Bifurcation主干 27.5% + Other 5%. Bifurcation 总 35% = 27.5% (N,N 内) + 7.5% (N,Y). 27.5 vs 7.5 = 3.67× — 即"政策推出但 Tesla N"路径 7.5% << "政策也没出 Tesla 也没出"27.5%, 意味 humanoid IRA 推出概率隐含 ~20%. 这个 split prior 没给 1 行 sentence rationale.

**Resolve**: limitation-note 加 "P(N,N) 内 China-led:Bifurcation主干:Other = 35:27.5:5 ≈ 7:5.5:1 是 author prior; 相当于 IRA 推出概率 ~20% 与 中国 winning 略高于双轨 的 joint prior".

---

## 状态: prior r3 issue updates

| r3 issue | status | reasoning |
|---|---|---|
| r3-n1 FATAL (Returns header vs 公式 3 处冲突) | **resolved** | L2690 header 4.6× / 24% / 15% 与 inline 公式 23.6% / 14.6% 严格一致 ✓. SST footnote L2695 deprecated 旧数字 explicit. Math fully closes. 跨 §A.6.3 L2766 propagation 同步. |
| r3-n2 SEVERE (US-led 20% vs 30% +10pp gap) | **resolved** | 9 处 propagation grep-verified (L480/L992/L1784/L1826/L1828/L1832/L2368/L2390/L4485/L4554). P(Tesla Y)=25% 重 derive, Bear-A+B = 25% = US-led 卡片中点 ✓. |
| r3-n3 SEVERE (P5/P50/P95 row label vs definition) | **partial** | Returns table row 改 "X% scenario probability" ✓, paragraph 改 ✓. 但 Q9 L2592-2594 三行仍 P50/P95 — 同章节同矛盾. r4-n2 详. |
| r3-n4 SEVERE (3×3 9 cell 公式混) | **resolved** | 9 cell 用单一公式 V = EBIT × df × [1 + 1/(WACC-g)]; 3 个 worked example 全可复算 ✓. 我独立 spot-check g=4%/W=12% = $1.40B ✓. |
| r3-n5 MOD (Bear-B 3× premium + outcome overlap) | **partial** | 3× premium surface 为 author's prior + 典型 1.3-1.5× 反差 explicit ✓. Bear-B / True Bear outcome 重叠 accepted-deferred (v4.md Limitations #5). Bear-B contribution 0.016 immaterial. |
| r3-n6 MOD (A.6.2 5 vs 6 家) | **resolved** | L2744 "6 家" ✓; L2483 Q4 (d) "6 家" ✓. |
| r3-n7 MOD (cell N,N 拆 over-decomp) | **partial** | L1832 显式承认 "author's downstream prior, 与 2×2 无关" ✓. v4.md #6 accepted. 升级 2×2×2 deferred. split 比例本身 minor 残留 (r4-n5). |
| r3-n8 MINOR (Comps N=5 footnote 溢价算错) | **resolved** | Lucid +183% / Rivian-Tesla N/A ✓; "175×" phantom 全删 ✓. Spot-check 150/53-1=183% ✓. |
| pe-n9 (P50/P95 misuse, r2 carry) | **partial** | Row level resolved (Returns table), Q9 line item unresolved. r4-n2 详. |

---

## Summary line

`persona=pe_partner, verdict=block, prior=6R/3P/0U, new=0F,1S,2M,2m`
