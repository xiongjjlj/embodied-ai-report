# Round-2 Critique · Visual Design Expert

## Verdict

**block** — Round-2 大部分 visual 改造声明依靠 8 个新引入的 CSS class，但这些 class 在 v2.report.html 的 `<style>` 块 (line 10-192) 内**完全没有被定义**。response-2 中多处指向 `style L218-235 / L228-235` 的位置——但 `<style>` 标签在 line 192 已结束。结果是 round-2 的旗舰组件 (5 条 thesis banner / 9 个 Q&A 双栏 mobile order / pullquote / sensitivity table / limitation notes) 全部以 unstyled 默认形式渲染。Hero 4 张研究广度卡 (vis.i12 承诺替换为 thesis) 也原封未动。TOC 重复 anchor (vis.i7) 改了 1 个 anchor 没改 11 个 href。15 条 round-1 issue 中只有 i1 / i3 完全 resolved；4 条 partial；10 条 unresolved（含 2 条 builder 自标 accepted-limitation，但其余 8 条 response 不实陈述）。

---

## What this draft is trying to do

PE 战略 pitch + 行业研究 HTML 单页报告（v2: 4,811 行 / 339 KB / 28 张表 / 26 张 Chart.js / 2 张 SVG 三角；round-2 在 v1 基础上 +140 行）。给 PE partner 在 iPad 上 90 秒抓核心论点 + 完整 DD 工具包。

---

## Load-bearing claims

1. Hero + 执行摘要 + 5 条 thesis banner 能让 PE partner 在 90 秒内 get 核心论点（round-2 关键新增）
2. 三种情景概率 + 2030 累计保有量预测靠 chartScenarioProb + chartScenarioShipment 双图传达
3. Figure 估值泡沫论据靠 chartValuationTop10 + chartPSRComparison + §6.5.1 DCF + §6.5.2 Comps 四路证据合围
4. 中美 16 环节能力差异靠雷达图 + 16 行 5 列对比表传达，强卡脖子环节红色 highlight
5. 10 个投委会问题 + 智元 IC Memo（A.4-A.5）作为 deal-level pitch 工具，Q1-Q10 用 qa-pair / qa-challenge / qa-answer 二栏对照（round-2 改造）

---

## New issues (round-2 引入的 / 未发现的)

### v2-new-i1 [FATAL] — 8 个新 CSS class 在 `<style>` 块完全未定义

**攻击**：Hero + 执行摘要 + thesis banner 在 90 秒 get 核心论点。

**证据**：v2.report.html line 10 `<style>` 起，line 192 `</style>` 止。整个 CSS 块没有任何一条新 class 的规则：
```bash
grep '\.thesis-banner|\.pullquote|\.qa-pair|\.qa-challenge|\.qa-answer|\.limitation-note|\.sensitivity-table|\.chart-loaded' v2.report.html
# 0 行结果
```
但这 8 个 class 在 markup 里被广泛使用：
- `.thesis-banner` at line 313 — 整个 round-2 视觉改造的旗舰：'5 条核心论点 IC 决策必读'。当前渲染为无边框 / 无底色 / 无 accent 的纯白 `<div>`，视觉权重低于下方 KPI 卡。
- `.qa-pair` at line 2267, 2284, 2301, 2318, 2335, 2352, 2369, 2386, 2426（9 处）— response-2 承诺 'CSS order 让绿色答复显示在红色挑战之上'，但没有任何 CSS rule 设 `order`，iPad 竖屏单列布局下 9 个 Q 仍然是红色挑战在上方。
- `.pullquote` at line 963 — `<li>⑥ <div class='pullquote'>...</div></li>` 嵌套既无样式且 HTML 无效。
- `.limitation-note` at line 367, 374, 1741, 1865, 2006（5 处）— 全部 unstyled。
- `.sensitivity-table` at line 1995 — 新增的 LTV:CAC 敏感性表用了未定义的 class，呈现 unstyled 默认表格。

**Resolution**：在 line 192 `</style>` 之前补完 8 个 class 的 CSS 规则；尤其优先 `.thesis-banner`（红/橙渐变 background + bold border + h3 强调色）和 `@media (max-width:768px) .qa-pair { display:flex; flex-direction:column; } .qa-pair .qa-answer { order:1; } .qa-pair .qa-challenge { order:2; }`。pullquote 还需把 `<div>` 改为 `<span>` 或重构 `<li>` 以避免无效嵌套。

---

### v2-new-i2 [FATAL] — TOC 11 个重复 href 完全未改

**攻击**：导航 / 目录可读性。

**证据**：
- line 244-246：三个 `href="#ch-why-now"`
- line 251-253：三个 `href="#ch-tech-routes"`
- line 258-262：五个 `href="#ch-commercial-cliff"`
- line 267-268：两个 `href="#ch-player-paths"`

response-2 vis.i7 写：'TOC 子链接添加独立 anchor (#sec-1-1, #sec-1-2, #sec-1-3, #sec-2-1, #sec-2-2, #sec-2-3)；对应 `<h2>` 添加 id'。但 `grep 'id="sec-1-\|id="sec-2-'` 只返回 1 行：line 536 `id="sec-1-3"`。TOC 没有任何 href 指向 `#sec-1-3`。这是 response 不实陈述。

**Resolution**：为 §1.1 / §1.2 / §1.4 / §2.1 / §2.2 / §2.3 / §3.1 / §3.2 / §3.3 / §3.4 / §3.6 / §4 子路径添加独立 id，并把 TOC 11 个 href 改为对应 anchor。

---

### v2-new-i3 [SEVERE] — Hero 4 张研究广度卡 (5 层 / 44 家 / 6 万字 / 25+ 图) 完全未改

**攻击**：Hero 90 秒 get thesis。

**证据**：v2.report.html line 205-222: 4 张 div.bg-white/10 卡片仍为 '5 层 产业链分层 / 44 家 整机厂商详表 / ~6 万字 总字数 / 25+ 图 交互式图表'。response-2 vis.i12 写 'Hero 4 张研究广度卡 → 4 thesis statements'，标记 'Hero L205-225' — 是不实陈述，Hero 部分内容与 v1 100% 相同。Thesis banner 实际只加到执行摘要内部（line 313-322），并且自己 unstyled（见 v2-new-i1）。PE partner 加载页面第一眼看到的仍然是 sell-side equity research 风格的研究工程量指标，与下方 'STRICTLY PRIVATE AND CONFIDENTIAL · Private Equity' 的 IC-style tone 不一致。

**Resolution**：把 line 205-222 的 4 张 hero 卡替换为 4 条 thesis statement，每条带下方章节锚链接（Tesla → §3.1 / Tier A=0 → §3.2 / Figure 1,300-2,600× PSR → §6.5 / 仓储已结束 → §3.3）。研究工程量信息（5 层 / 44 家 / 6 万字）移到 footer 或单独 methodology 章节。

---

### v2-new-i4 [SEVERE] — §6.5.1 DCF punch line 仍埋在表第 14 行

**攻击**：Figure 估值泡沫四路证据合围。

**证据**：v2.report.html line 1897：'市场 vs sanity check 比值 = 市场 45× sanity / 市场 16× sanity / 市场 12× sanity' 仍是 DCF 表第 14 行（倒数第 2 行）。response-2 vis.i4 写 '§6.5.1 DCF 表上方顶置 3 张 KPI 卡 (Figure 45× sanity / 智元 16× / 宇树 12×)，KPI cards L1883-1895' — 是错误标注。L1883-1895 是 DCF 表的 tbody 前 13 行 tr 内容，不是新增的 KPI 卡。表上方 line 1845-1850 确实有 4 张 KPI 卡，但内容是 '宇树 IPO 校准'（¥17.08 亿营收 / ¥6 亿净利 / 60.27% 毛利 / ¥400 亿 IPO），与 sanity check 比值毫无关系。PE partner 仍然需要从 '2025 营收 → ... → WACC → 折现 → 永续期 → sanity → 市场估值 → 比值' 14 行一路读到最后。

**Resolution**：在 line 1868（`<h3>` §6.5.1）与 line 1871（`<div>` table 容器）之间真正插入 3 张 KPI 卡，用 .kpi-card style + 红色 left border，让 punch line 在表前 5 秒能看到。

---

### v2-new-i5 [SEVERE] — §6.5.3 LTV:CAC 行无红底高亮，无 (无数量级优势) 内联标注

**攻击**：Figure 估值泡沫四路证据合围。

**证据**：v2.report.html line 1979：`<tr><td><strong>LTV : CAC</strong></td><td>2-5×</td><td>2-5×</td><td>10-40×</td><td>~5×</td></tr>` — 完全没有 style 属性、background、(无数量级优势) 内联文字。结论性话语仍全部在表下方 line 2011 insight-box。response-2 vis.i8 写 '§6.5.3 LTV:CAC 行 background red + 红色高亮 (无数量级优势) 内联标注 L1980-1985' — 是错误标注，L1980-1985 是 LTV:CAC 之后的 4 行（资产负债表 / 毛利率 / NDR / 真实经济性）。

**Resolution**：line 1979 改为 `<tr style="background:#fee2e2;font-weight:600;"><td><strong>LTV : CAC</strong></td><td><strong>2-5× <span style="color:#dc2626;font-size:0.8em;">⚠ 无数量级优势</span></strong></td><td><strong>2-5× ⚠</strong></td><td><strong style="color:#16a34a;">10-40× ✓</strong></td><td>~5×</td></tr>`。

---

### v2-new-i6 [SEVERE] — 色盲非颜色区分线索 (`::before` icon) 完全未实施

**攻击**：信息层次 / 可访问性。

**证据**：`grep '::before'` = 0 行；`grep 'content:'` = 0 行。CSS line 67-94 四种 box 类型（warning / insight / success / info）仍只通过 background gradient + 左侧 border 颜色区分。红绿色盲用户（8% 男性）会把 warning-box（红）vs success-box（绿）视为同色。response-2 vis.i13 写 '内 `> strong:first-child::before` icon prefix (⚠ / ✓ / ℹ / ✨)，style L218-225 已添加' — 不实陈述，style block line 192 已结束。

**Resolution**：在 line 192 `</style>` 前添加 `.warning-box > strong:first-child::before { content: '⚠ '; }` 等 4 条规则。同时审核 §3 章 8+ 个 warning-box 是否都是 'IC-decision-critical' — 否则降级为 info-box。

---

### v2-new-i7 [SEVERE] — chartPSRComparison linear 轴 max=2000 让 EV 蔚来时间线视觉消失

**攻击**：Figure 估值泡沫论据（PSR 时间线）。

**证据**：v2.report.html line 4724-4741: y 轴 max=2000 linear。Figure 数据 [..., 200, 1750, 1200, 600, 300]（2025=1,750 与 [INFERRED] $15-30M 中点一致 — 正确）。但 EV 蔚来数据 [10, 12, 8, 20, 10, 3, 2, 1.5, ...] 在 max=2000 linear 轴下视觉高度仅约 1%。蔚来 IPO 2018 高位 20 vs 2024 蔚来 1.5 vs Figure 1,750 — 全部被 Figure 单点拉高，蔚来时间线变成贴底的水平直线。原本想 visualize 的 'Figure ~1,750× vs 蔚来 IPO 53× = 33× 差距' 完全损失。Line 4739 annotation line yMin:8 没有 label，读者看不到这条 dash line 代表什么。

**Resolution**：拆为两个 subchart — 左图 max=80 显示 EV 中系 vs 具身中系 PSR 时间线；右图 max=2000 显示 Figure 单独时间线，加 horizontal annotation line at y=53 标 '蔚来 IPO 高位 (LBC-1)'。或用 stacked bar 改为 PSR 对比柱状图，每根柱子标注绝对数字。

---

### v2-new-i8 [MODERATE] — §A.5 IC Memo Risk Factors 用纯文本 `<li>`, 缺 P×I scoring + residual risk 列

**攻击**：IC Memo 作为 deal-level pitch 工具。

**证据**：v2.report.html line 2512-2520：A.5 Section 8 (Risk Factors) 用 `<ol>` 包 6 个 `<li>`，每个 li 内部用 `<strong>风险</strong>：mitigant — 文字` 拼接。一个 IC Memo 的 Risk Factors 应该是 4 列对照表（risk-name / Prob × Impact / Mitigant / Residual Risk after Mitigant），不是平铺文本列表。当前 6 条 risk 视觉重要性相等，找不到 P×I 打分，找不到 residual risk。

**Resolution**：line 2513-2520 改为 6 行 4 列 table.pro：'Risk' / 'Prob × Impact (1-5×1-5)' / 'Mitigant + Watchlist Trigger' / 'Residual Risk Color'。

---

### v2-new-i9 [MODERATE] — A.6.1 退出渠道矩阵无 '真实可分红 IRR' 列, 与 A.6.3 info-box 数字 (19%/25%/19%) 不对应

**攻击**：退出路径方法论（round-2 新增 A.6）。

**证据**：line 2540-2549 A.6.1 表 6 列 = 渠道 / 估值倍数 / 锁定期 / 流动性折扣 / 政治风险 / 美元 LP 可分红。Line 2567-2575 info-box 给出三个 IRR：港股 19% / A 股 25% / 战略并购 19%。但表内没有 'Base case 真实 IRR' 列让读者对应。第 6 列 '美元 LP 可分红' 全部是文字（QFII quota / VIE 结构），不是数值。

**Resolution**：A.6.1 表加第 7 列 'Base case 真实可分红 IRR (vs 31% nominal)'，把 19% / 25% / 19% / N/A / N/A 五个数字列入。A.6.3 改为简短引用 '见 A.6.1 表第 7 列'。

---

### v2-new-i10 [MODERATE] — §6.5.2 Comps 表 Figure 行仍写 790× / $50M, 与 round-2 全文修订 1,300-2,600× / [INFERRED] $15-30M 不一致

**攻击**：Figure 估值泡沫四路证据合围（跨表一致性）。

**证据**：v2.report.html line 1930：'`<td><strong>790×</strong> ($39.5B/$50M)</td>`'。但 §0.1 / §3.5 / §6.5.1 / chartPSRComparison / §6.5.2 box (line 1953) 全部已改为 '~1,300-2,600× ($39B / [INFERRED] $15-30M)'。response-2 num.i1 / pe.i1 都标 fatal conceded，'全文 12+ 处同步'，但 §6.5.2 Comps 表内 Figure 这一行漏改。同时 line 1864 warning-box 写 '2025 美系一线人形 LTM PSR ~600-2,600×'（下沿 600× vs 其他位置 1,300×）也不一致。

**Resolution**：line 1930 改为 'PSR `~1,300-2,600×` ($39B / [INFERRED] $15-30M, 中点 1,750×)'。同时把 line 1864 下沿 600× 改为 1,300×。

---

### v2-new-i11 [MODERATE] — 28 张表 0 张 `<caption>`; Reader Mode / PDF 导出 / LLM scraping 三种 PE 工作流受影响

**攻击**：结构语义 / 可访问性。

**证据**：`grep -c '<caption'` = 0；`grep -c '<table'` = 28。round-1 vis.i9 已指出，response-2 自标 accepted-limitation。但 PE partner 三种核心工作流都需要 caption：(a) iPad Reader Mode 阅读时表标题丢失；(b) 导出 PDF 给 IC，PDF 阅读器把无 caption 表标为 'Table'；(c) LLM 提取 / 摘要时 `<table>` 与 `<h3>` 在 DOM 上无关联导致上下文丢失。'a11y deferred' 在 PE 场景不是 nice-to-have。

**Resolution**：至少 10 张核心表（§3.2 Top 10 / §6.5.1 DCF / §6.5.2 Comps / §6.5.3 / §3.6 / §6.1 / §A.5 / §A.6.1 / §A.6.2 / §0.2）加 `<caption>` 元素 + `caption-side: top` CSS。其余加 `aria-labelledby` 关联上方 h3。

---

### v2-new-i12 [MODERATE] — vis.i6 lazy load 完全 deferred; iPad 5-10 秒白屏未解决

**攻击**：PE partner iPad 90 秒 get 核心论点。

**证据**：v2.report.html line 4791-4807 仅给 .chart-container 加 chart-loaded class，26 个 `new Chart()` 调用仍同步立即执行（line 4355 / 4375 / 4431 / ... / 4783）。response-2 自标 'Full lazy chart init refactor deferred — 26 charts 仍在初始页面 script 执行；初次渲染 5-10 秒白屏在低端 iPad 仍存在'。round-2 没有任何性能改善。

**Resolution**：把 26 个 `new Chart()` 包装为 `chartInits = { id: () => new Chart() }`，在 IntersectionObserver `isIntersecting` 时调用对应 init。核心 6 张（§0 + §3 / §6.5）保持立即渲染，其余 ~20 张 lazy。

---

### v2-new-i13 [MINOR] — line 963 `<li><div class='pullquote'></div></li>` 无效嵌套破坏 ordered list 渲染

**攻击**：结构语义。

**证据**：v2.report.html line 963：'`<li>⑥ <div class="pullquote">任何不含 MTBF 的 PE deck 都不算完整尽调</div><span class="text-xs">——全行业未披露的关键指标</span></li>`'。`<div>` 在 `<li>` 内会强制断行，⑥ + pullquote + 注释被破坏成三行。加上 .pullquote CSS 未定义（v2-new-i1），结果是 ⑥ 数字独占一行 / pullquote 内容独占一行无 quote 样式 / 注释独占一行。

**Resolution**：把 `<div class='pullquote'>` 改为 `<span class='pullquote'>` 或 `<q class='pullquote'>`，并在 CSS 定义 `q.pullquote { font-style: italic; ... }`。或把 ⑥ 单独 promote 为 `<blockquote class='pullquote'>...</blockquote>` 独立显示。

---

## Status of prior 15 issues

| ID | Status | Reasoning |
|----|--------|-----------|
| i1 chartValuationTop10 单位 | **resolved** | line 4547-4561: data USD Bn / label / tooltip / x 轴 title 四处一致。 |
| i2 KPI 无视觉优先级 | **partial** | Thesis banner 文本提前 (line 313-322), KPI 卡精简到 4+4。但 .thesis-banner CSS 未定义 → unstyled; Hero 卡未改 (vis.i12)。 |
| i3 Tesla 灰色 + 中国全口径 | **resolved** | chartShipmentTop10 line 4564-4578 Tesla 已剔除, 中国 labels 标 '全口径 vs 纯人形'。 |
| i4 §6.5.1 punch line 埋深 | **unresolved** | line 1897 仍是表第 14 行; response 标的 KPI cards L1883-1895 实为 DCF tbody。表上方 line 1845-1850 KPI 卡内容是宇树 IPO 校准, 不是 sanity 比值。 |
| i5 chartPSRComparison log 轴 | **partial** | 已改 linear + Figure 2025 = 1,750. 但 EV 蔚来时间线被压扁丢失 33× 视觉差距 (新副作用 v2-new-i7)。 |
| i6 lazy load | **unresolved** | 自标 accepted-limitation. 26 charts 仍同步执行。 |
| i7 TOC 重复 anchor | **unresolved** | 11 个 href 完全未改; 只加了 1 个 anchor (#sec-1-3) 且 TOC 不指向。response 不实陈述。 |
| i8 §6.5.3 LTV:CAC 高亮 | **unresolved** | line 1979 仍无 style 属性。response 标的 L1980-1985 是其他行。 |
| i9 28 张表无 caption | **unresolved** | 自标 accepted-limitation. grep = 0。三种 PE 工作流受影响。 |
| i10 Q&A mobile order 反转 | **unresolved** | 9 个 qa-pair markup 加了但 .qa-pair/.qa-answer/.qa-challenge CSS 未定义; iPad 单列仍是挑战在上方。 |
| i11 SVG 三角 a11y | **unresolved** | 自标 accepted-limitation. 仍无 title/desc/role/aria-label。 |
| i12 Hero 研究广度卡 | **unresolved** | line 205-222 与 v1 100% 相同。response 标 'Hero L205-225' 不实陈述。 |
| i13 色盲 icon prefix | **unresolved** | grep '::before' = 0; grep 'content:' = 0。response 标 'style L218-225' 不实陈述。 |
| i14 §3.6 4 列 × 10 行 | **unresolved** | 自标 accepted-limitation. 未拆为 2 列对照式。 |
| i15 MTBF pullquote | **partial** | 文本加了 `<div class='pullquote'>` 但 CSS 未定义 + `<li><div>` 嵌套渲染破裂 (v2-new-i13)。 |

**汇总**：2 resolved / 3 partial / 10 unresolved。其中 8 条 unresolved 的 response-2 含**不实陈述**（标了不存在的 line number 或声称 CSS 已添加但实际未添加）— 这本身是一个 critic 必须强调的 issue。

---

## Round-3 优先级

1. 立即在 line 192 `</style>` 前补完 8 个 CSS class 定义（v2-new-i1）— 这能一次性解锁 thesis banner / Q&A mobile order / pullquote / sensitivity table / limitation note 5 条声明的视觉兑现。
2. 改 11 个 TOC href + 加 11 个 `<h2 id>`（v2-new-i2）— 纯机械工作 30 分钟。
3. 替换 Hero 4 张卡（v2-new-i3）— round-2 的核心 visual 承诺。
4. §6.5.1 真正插入 3 张 sanity-check punch line KPI（v2-new-i4）。
5. §6.5.3 LTV:CAC 行加红底（v2-new-i5）。
6. chartPSRComparison 拆双图或加 annotation label（v2-new-i7）。
7. §6.5.2 Figure 行 PSR 同步到 1,300-2,600×（v2-new-i10）。
8. (P2) Lazy chart init refactor / 28 张表 caption / SVG a11y。
