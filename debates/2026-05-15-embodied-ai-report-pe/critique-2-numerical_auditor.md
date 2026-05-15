# Round-2 Critique — `numerical_auditor`

## Verdict: **BLOCK**

Builder 在 round-2 fixed narrative everywhere, 但 5 个关键 source-of-truth 表格 / chart / JSON 未同步更新. **'文字已改, 表格没改'** = round-1 critique 的核心证据仍原地保留在表里, 同一报告内 narrative-vs-table 互相打脸.

Resolved: 5/14 prior issues; Partial: 8/14; Unresolved: 1/14.
New issues: 0 fatal / 5 severe / 4 moderate / 1 minor.

## What this draft is trying to do

商业研究 / PE 视角具身智能产业链报告 v2 (中文). 受众: PE 老板 / IC 委员会. 核心目标: 论证 (a) 中国硬件链是 PE alpha 主战场, (b) 美系一线整机系统性泡沫, (c) 三情景概率配置 + IC Memo 决策框架.

## 关键修复成功的部分 (5 项 resolved)

| Prior ID | 严重度 | Status | 评价 |
|---|---|---|---|
| i3 GDP 10× 错位 | severe | resolved | 0.008% / 0.05% 全部对齐, 算术自洽 ✓ |
| i6 三情景概率不闭合 | severe | resolved | 30-40 / 15-25 / 35-45 / 5%, 中点合 100% ✓ |
| i10 估值分层 5-10× vs 14× | moderate | resolved | 'Pre-IPO 时点 5-14×' 显式 ✓ |
| i11 BOM 2.8× 单源 MS | moderate | resolved | '2.8-4.1× 区间; MS 单源' 显式 ✓ |
| i13 Unit Economics INFERRED | minor | resolved | 5 行 sensitivity 表显式 ✓ |

## 关键修复失败的部分 (主战场)

### N2.i1 [severe] · Comps 表 L1930 Figure 行仍 '790× ($39.5B/$50M)'

```
L1930: <td><strong>790×</strong> ($39.5B/$50M)</td>
```

**全文其他 12+ 处都改为 1,300-2,600×**, 唯独这张 §6.5.2 Comps Quartile 表 Figure 行未改. 这是 round-1 i1 fatal 的原始证据 — Builder response 标 'C 全文同步' 是 over-claim. 同表 L1898 LTM PSR 行写 1,300-2,600×, 同表 L1930 Figure 行写 790×, **同一表格两个 PSR 数字**.

重算: 39000/50 = 780× ≈ 790× (旧数), 39000/22.5 = 1,733× (新中点). 留 790× = 留旧锚.

**修复**: L1930 cell 替换为 `<td>~1,300-2,600× ($39B / [INFERRED] $15-30M; 中点 1,750×)</td>`; NTM 200× 同步重算.

### N2.i2 [severe] · Symbotic 4.5×, 工业 median 3.5× 仍在表中

```
L1937: <td>ABB（瑞士）</td><td>2025</td><td>2.8×</td><td>2.7×</td><td rowspan="4">3.5×</td>
L1940: <td>Symbotic（仓储自动化）</td><td>2025</td><td>4.5×</td><td>3.5×</td>
L1941: <td>Intuitive Surgical（医疗机器人）</td><td>2025</td><td>14×</td>
```

而 L1956 narrative 写: '工业自动化 median 修正 8.1× (Symbotic 4.5×→13×), Intuitive Surgical 仍应单列医疗机器人'.

重算 (Symbotic 修正 13×): median[2.8, 3.2, 13, 14] = (3.2+13)/2 = 8.1× ✓
当前表算: median[2.8, 3.2, 4.5, 14] = (3.2+4.5)/2 = **3.85**× (原本就不是 3.5× — round-1 i9 的算术错也没修)

**下游影响**: L1955 写 '宇树 23×...接近 Symbotic / Intuitive 模式' — 若 Symbotic 真值 13× LTM, 宇树 23× 不是 '接近' 而是 '溢价 77%'.

**修复**: (a) L1940 Symbotic 4.5×→13×, 3.5×→10× NTM; (b) L1937 rowspan 3.5×→8.1×; (c) Intuitive 单列 '医疗机器人' 子板块; (d) L1955 narrative 重写.

### N2.i3 [severe] · EV IPO median rowspan L1934 仍 22×

```
L1934: <td>蔚来（IPO 2018.9）</td>...<td>53×</td><td>15×</td><td rowspan="3">22×</td>
L1935: <td>小鹏</td>...<td>24×</td>...<td>+9%</td>
L1936: <td>理想</td>...<td>15×</td>...<td>-32%</td>
```

narrative 12+ 处改为 24×. 重算 median[15, 24, 53] = 24×. 当前 22× 既非 median 也非 mean (mean=30.67), 来源不明.

下游: 小鹏 vs 22× 给 +9%; 若 vs 24× 应是 0%. 理想 -32% 应 -37.5%. 蔚来 +141% 应 +120.8%.

**修复**: rowspan 22×→24×; '+9%/-32%' 列重算.

### N2.i4 [severe] · DCF 表 L1883 Figure 出货仍 150 台, 与 limitation note + chart 矛盾

```
L1883: ... 按 150 台 × $130K BOM × 30-50% 计提率估算 ...
L1884: <td><strong>2025 出货</strong></td><td>~150 台 (Tech360 2026.1)</td>
L374 (limitation note): 按 250 台（DP023）× $130K BOM × 30-50% 计提率反推 $15-30M
L856: 当前 2025 营收 [INFERRED] $15-30M (250 台 × $130K × 30-50% 计提率)
chartShipmentTop10 L4567: 'Figure AI (~250, DP023)'
```

算术: 150 × $130K × 30-50% = **$5.85-9.75M**, 不可能反推 $15-30M.
250 × $130K × 30-50% = **$9.75-16.25M**, 上限仍只 $16M.
反推 $30M 上沿需要 ~350 台 × 65% (DP140 累计 350+, 截至 2026.05).

**修复**: L1883/L1884 150 台 → 250 台 (DP023; 累计 350+ DP140).

### N2.i5 [severe] · DCF 3×3 g/WACC 敏感性表不存在; '$0.68-1.61B / 31-58×' 自相矛盾

Response 声称 '§6.5.1 新增 3×3 g/WACC 敏感性表 (Figure $0.68-1.61B / 28-65×)'. grep 全文: 此表不存在. 仅 narrative 引用 ('详 3×3 表').

**算术自相矛盾**:
- claim base $0.87B → 39000/870 = **44.8×** ✓ (base 45×)
- claim 上沿 $1.61B → 39000/1610 = **24.2×** ≠ 31× (off by 30%)
- claim 下沿 $0.68B → 39000/680 = **57.4×** ✓ (close to 58×)

要么 $1.61B 上沿错, 要么 31× 错. 我用 (W=12%, g=4%, EBIT $163M) 重算上沿 = $1.40B → 39000/1400 = 27.9×, 也不是 31×. Builder 必须列假设链, 否则读者 unable to verify.

L892 写 '28-65×', L1907 写 '31-58×' — 同一 sensitivity 区间两个数, 内部不自洽.

**修复**: 真正建 3×3 矩阵 (g=2/3/4% × WACC=12/15/18%, 9 cell 显式列 EBIT 与 df 公式); 重新校准上沿 $1.40B 或 $1.61B 取一; reconcile 28-65× vs 31-58×.

## 中等问题 (4 项)

### N2.i6 [moderate] · data_points.json DP098 '日均 >¥5亿' 未同步

```json
{"id": "DP098", ... "fact": "国内具身累计融资额 (截至 2026.05 初) ¥373 亿，日均 >¥5 亿"}
```

HTML L2089 已改 '日均 ¥2.5 亿 × 148 天 ≈ ¥373亿' (算术自洽); 但 JSON source-of-truth 未改. 任何下游 agent 读 JSON 仍读到 '日均 >¥5亿'.

### N2.i7 [moderate] · $39.5B vs $39B 仍并存 5 处

L1005, L1388 (chart subtitle), L1930 (Comps 表), L4287 (验证表), L4553 (chartValuationTop10 数据).
L1896 显式 '$39B (DP009); HTML 部分 KPI 处 $39.5B 同义' — 仅 declared, 未 global-replace.

**修复**: sed 's/\$39.5B/\$39B/g' 一致化, 或 L4553 data 39.5 → 39.0.

### N2.i8 [moderate] · L892 '智元 ¥225 亿' = 银河通用数字, 误属智元

L892: '智元 ¥225 亿 → sanity $0.17B'. 但 ¥225 亿 是银河通用 (大基金首投, L434/L1053), 智元是 ¥200 亿+. Mis-attribution.

并发: L892 写 '28-65×' vs L1907 写 '31-58×' — sensitivity 区间不一致.

### N2.i9 [moderate] · chartPSRComparison 2024 Figure PSR=200× 缺数据基础

L4731 数据 [2024=200, 2025=1750, 2026E=1200, 2027E=600, 2028E=300]. Subtitle '$39B / [INFERRED] $15-30M' 仅描述 2025 口径; 但数据点是 2024-2028 时间序列, 2024 Figure 估值实际是 $2.6B (DP129), 2024 营收 [UNDISCLOSED]. 200× 隐含 $2.6B/$13M, $13M 没有出处. 2026E-2028E 600/300 也无公开 anchor.

## 次要问题 (1 项)

### N2.i10 [minor] · '失败概率 30-40%' (DCF) vs P5 weight 5% (IC Memo) 未 reconcile

L1907 / L1953: '完整 DCF 应纳入失败概率 30-40%'.
A.5 Returns table P5 (True Bear): 5% (per response-2.md).
两处概率差 6-8×. 合理解释 (单标的 vs 组合) 未在文中明示.

## 优先修复顺序 (建议 round-3)

1. **N2.i1 + N2.i4** (Comps 表 Figure 行 + DCF 表 150 台) — 这两个 cell 直接破坏 LBC-4 中央叙事 robust 性
2. **N2.i2 + N2.i3** (Symbotic 表 cell + EV IPO median rowspan) — 跟 LBC-4 对照锚强度直接挂钩
3. **N2.i5** (3×3 g/WACC 敏感性表) — 既然 narrative 已经引用了, 必须把表做出来
4. **N2.i7** ($39.5B 一致化) — sed 一行解决
5. N2.i6 / N2.i8 / N2.i9 / N2.i10 — moderate / minor 收尾

如果 round-3 只能改 5 行, 就改 L1883 (150→250), L1884 (~150→~250), L1930 (790×→1,300-2,600×), L1937 (median rowspan 3.5→8.1), L1934 (median rowspan 22→24). 这 5 行 单点修复就把 4 个 severe 降到 minor.

## Prior issues status table

| ID | Prior severity | Status | 备注 |
|---|---|---|---|
| i1 Figure PSR 锚 | fatal | **partial** | Narrative ✓, Comps 表 cell 未改 (n2.i1), DCF 表 150 台未改 (n2.i4) |
| i2 Symbotic 4.5×→13× | severe | **partial** | Narrative ✓, Comps 表 cell 未改 (n2.i2) |
| i3 GDP 10× 错位 | severe | **resolved** | 全部对齐, 算术 ✓ |
| i4 YTD ¥373亿 / 日均 | severe | **partial** | HTML ✓, data_points.json DP098 未同步 (n2.i6) |
| i5 EV IPO median 22→24 | severe | **partial** | Narrative ✓, Comps 表 rowspan 未改 (n2.i3) |
| i6 三情景概率不闭合 | severe | **resolved** | 中点合 100% ✓ |
| i7 $39.5B vs $39B | moderate | **partial** | Declared ✓, 5 处 $39.5B 残留 (n2.i7) |
| i8 Figure 150 vs 250 vs 350 台 | moderate | **partial** | Chart / narrative ✓, DCF 表未改 (n2.i4) |
| i9 工业 median 3.5×→8.1× | moderate | **partial** | Narrative ✓, Comps 表 cell 未改 (n2.i2) |
| i10 估值分层 5-14× | moderate | **resolved** | 显式 'Pre-IPO 时点 5-14×' ✓ |
| i11 BOM 2.8× 单源 | moderate | **resolved** | '2.8-4.1× 区间; MS 单源' 显式 ✓ |
| i12 宇树 IPO 时点 | minor | **resolved** | Pre-IPO / IPO 两时点拆开 ✓ |
| i13 Unit Economics INFERRED | minor | **resolved** | 5 行 sensitivity 表 ✓ |
| i14 DCF 永续期 90%, 缺敏感性 | minor | **unresolved** | 引用的 3×3 表实际不存在 (n2.i5) |
