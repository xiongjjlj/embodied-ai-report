# Critique Round-5 — industry_expert

## Verdict

**pass** — 4 项 prior moderates/minors 全部 grep-verified resolved; round-5 修订未引入新 fatal/severe/moderate 级 industry / 玩家层面问题. Pass criteria (0 fatal + 0 severe) 满足.

## What this draft is trying to do

商业研究 / 产业链格局分析 / PE 投资判断报告 (zh-CN, PE/VC 合伙人级 IC 决策辅助材料 — round-5 修订后).

## Load-bearing claims (round-5 status)

1. **LBC-1**: 美强软件 (二层拆分: Big Tech 基础模型层 + 私募整机层) / 中强硬件; Apptronik 在 OEM-locked 桶 (7c) 一致; **6-路径对照表 round-5 升级为 7 行含 ⑦c**.
2. **LBC-2**: 2030 年度 TAM $30-144 亿 (中位 $75 亿); 2025 真实工业部署 < 1,000 台 conceded.
3. **LBC-3**: 三情景 35/25/35/5; **Bifurcation 卡片大字 round-5 由 40% 修正为 35%** 与 SST 一致.
4. **LBC-4**: Figure 单家 LTM PSR 1,300-2,600× / 美系一线 pure-play 4 家 加权 PSR 750-1,500× / 中系 EV IPO N=3 中位 24×.
5. **LBC-5**: 中系核心零部件 + 稀土 alpha + 美系 OEM-locked + Distressed M&A; **Bear-B 触发列与估值列 round-5 统一在 3× control premium**.

## New issues this round

无. (0 fatal / 0 severe / 0 moderate / 0 minor)

## Status of prior (round-4) issues

| ID | Severity | Status | 验证 |
|---|---|---|---|
| i22 | moderate | **resolved** | §6.3 Bifurcation 卡片 L1801 大字 由 '40%' → '35%' + 副标 '(30-40% range; Round-5 r4-i22 SST canonical 中点 35%)'. 与 2×2 矩阵 L1828 derive 出 '27.5% + 7.5% = 35%' 完全一致. grep `r4-i22 SST canonical 中点 35%` → L1801 ✓. 35/25/35/5 = 100% SST 全报告闭合. |
| i23 | moderate | **resolved** | §A.5 Bear-B 行 L2689 触发列改为 'distressed strategic acquire at ~3× DCF sanity (我方 prior 国资战投 + 数据资产残值; 高于 §A.6.1 标准 control premium 1.3-2× — 见 r4-i23 footnote 下)'; Exit 估值列同样 3× 显式同步. 同一 row 两列 control premium 倍数一致. §A.6.1 标准 1.3-2× 保留为市场基准, 智元 Bear-B 的 3× 显式声明为 author's prior 上限. 触发列与估值列的逻辑桥已修复. |
| i24 | minor | **resolved** | chartShipmentTop10 chart title L4773: '30 单位 Hyundai 内部 pilot' 已完全移除, 替换为 '2025 = 0 commercial; pre-production / engineering units 数量未公开 [UNDISCLOSED]'. grep `30 单位 Hyundai` → empty ✓. [UNDISCLOSED] 与同图 Apptronik / 1X 标准对齐. |
| i25 | minor | **resolved** | §4 对照表 caption L1161: '6 种路径对照' → '7 种路径对照'. 新增 row L1174: ⑦c Apptronik OEM-locked, 失败概率 '15-25%（OEM 现金流补贴; 比 Figure 30-40% 低; 同等于 BD-Hyundai 7b）'. border-top 紫色与 path-card 视觉同步. 'OEM-locked 15-25% vs Figure 30-40%' head-to-head 可见性建立. ⑦a / ⑦b 未单独加 row 但 ⑦c 内文已类比 7b, 对 IC 足够 (i25 原 what_would_resolve 第 (1) 条 minimum bar 已满足). |

## Round-5 side-effect scan (新引入问题排查)

Round-5 共 15 处 marker. 重点排查以下 surface:

- **i22 Bifurcation 35%**: §0.2 / §3.6 / chartScenarioProb 全部已显示 35%; round-5 仅修了 §6.3 卡片视觉锚 (差异点); 无 cascade 副作用.
- **i23 Bear-B 3×**: cascade 入 §A.5 E[MOIC] capture-adjusted 公式 — Bear-B 行 conditional MOIC 0.13× 不变 (= 0.5/3.9 = 0.128 ≈ 0.13). r4-n1 cascade 中 Bear-B 贡献 0.125×0.6×0.13 = 0.0098 与 SST cell 总和 2.55× 计算一致. 无算术 break.
- **i24 chart subtitle**: 仅 subtitle 文字替换, 数据值 null 不变 (round-4 已设); 无视觉 / data 副作用.
- **i25 对照表新行**: ⑦c row 引用 '同等于 BD-Hyundai 7b' 失败率 15-25% — §4 path-card 7b 没有显式 stamped 失败率数字, 但其 'OEM-locked + 整车 OEM 现金流补贴' 逻辑与 ⑦c 同源, 类比合理. 非新增问题.
- **r4-n1 capture-probability cascade** (pe_partner 修订): §A.5 SST 由 4.6×/24%/15× 替换为 2.55×/21%/13× (capture-adjusted); OLD 数字保留为 ceiling 标 DEPRECATED. industry/玩家 view 一致 — 7-way Chinese-pole 竞争 framework (宇树 / 银河通用 / 智元 / 字节 / 蚂蚁 / 京东 / 优必选) 与 §3 / §4 玩家 mapping 同步.
- **n4.i1 / n4.i2 / n4.i3 数字修订** (numerical_auditor 修订): IC Memo intro 24× / $0.17B / per-company g & WACC. 与 industry view 无冲突.

无新 fatal / severe / moderate / minor 问题.
