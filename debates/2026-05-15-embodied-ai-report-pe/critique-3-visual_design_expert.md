# Round-3 Critique — visual_design_expert

## Verdict: **pass**

Round-2 的 2 FATAL (phantom CSS / TOC 重复 href) 实质 ship 完成；5 SEVERE (Hero thesis / DCF KPI / LTV:CAC / 色盲 icon / chartPSRComparison) 全部技术 resolved；3 MODERATE (Risk Register / 退出 IRR / Comps 表 stale) resolved。剩 1 个 major 级新 issue (Hero 4 thesis 卡有 3 张落到 chapter-top anchor 而非 granular sec-3-X) + 2 个 minor + 1 个 moderate — 都不构成 block 理由。Round-3 是该 persona 三轮中最高质量交付。

## What this draft is trying to do

PE 战略 pitch + 行业研究 HTML 单页报告 (v3: 5,008 行)，<style> 块 line 10-274 — Round-3 在 line 192-273 实质追加 80+ 行 CSS 修复 8 个 phantom class；markup 端补完了 TOC sec-1-1 ~ sec-4-5 anchor、hero 4 thesis card、DCF KPI 卡、LTV:CAC 红底、退出 IRR 列、风险登记 4 列表。

## Load-bearing claims (Round-3 期承诺)

1. Round-2 标记 FATAL 的 8 个 phantom CSS class (.thesis-banner / .pullquote / .qa-pair / .qa-challenge / .qa-answer / .limitation-note / .sensitivity-table / .chart-loaded) 在 v3 全部已定义并 ship 到 <style> 块。
2. Round-2 标记 FATAL 的 TOC 11 处重复 href 已去重，每个子链接指向独立 sec-X-Y anchor。
3. Hero 4 张研究广度卡已替换为 4 thesis statement 卡，可点击跳到对应 §3.1 / §3.2 / §6.5 / §3.3。
4. §6.5.1 DCF punch line (45× / 16× / 12× sanity) 已 promote 到表上方 3 张 KPI 卡。
5. §6.5.3 LTV:CAC 行已加红底 + ⚠ 无数量级优势 内联标注。
6. 色盲非颜色区分线索 (warning / success / insight / info ::before icon) 已 ship。

## Verification highlights (grep evidence)

```
grep -n '\.thesis-banner {\|\.pullquote {\|\.qa-pair\|\.limitation-note {\|table.sensitivity-table {\|\.chart-loaded' v3.report.html
  → L193 / L205 / L226 / L234 / L244 / L259  (all 8 classes have real rules)

grep -c 'id="sec-[0-9]' v3.report.html
  → 13   (sec-1-1 ... sec-4-5 anchors all present)

sed -n '314,440p' | grep -oE 'href="#[^"]+"' | sort | uniq -c | sort -rn
  → max duplicate inside <section id="toc-section"> = 2 (#ch2-5 referenced from
    both §6 子链接 and Thesis-3 banner, cross-region, acceptable)

grep -n 'warning-box > strong:first-child::before' v3.report.html
  → L262   (colorblind a11y icons ship)

grep -n 'background:#fee2e2.*LTV : CAC.*无数量级优势' v3.report.html
  → L2120  (LTV row red highlight ship)

grep -n '45× sanity' v3.report.html
  → L1964  (DCF KPI cards promoted to top of §6.5.1)

grep -n 'lineEVIPO.*53' v3.report.html
  → L4932  (chartPSRComparison log scale + 3 EV anchor lines)
```

Phantom CSS class count: **0**. TOC duplicate href count: **0** (within TOC nav).

## Issues

### v3-i1 (major) — Hero 4 thesis 卡中 3 张落到 chapter-top anchor 而非 granular sec-3-X

**attacks**: Hero 4 thesis 卡可点击跳到对应章节 (load-bearing claim #3)

**detail**:
- L289 (Thesis 1, Tesla, 文案标 → §3.1): `<a href="#ch-commercial-cliff">` — 应 `#sec-3-1`
- L294 (Thesis 2, $3B Tier A 几乎 0, 文案标 → §3.2): `<a href="#ch-commercial-cliff">` — 应 `#sec-3-2`
- L299 (Thesis 3, PSR 1,300-2,600×, 文案标 → §6.5): `<a href="#ch2-5">` — 正确，保留
- L304 (Thesis 4, 仓储 ROI 5-16×, 文案标 → §3.3): `<a href="#ch-commercial-cliff">` — 应 `#sec-3-3`

granular anchor 在 L812 (#sec-3-1) / L839 (#sec-3-2) / L883 (#sec-3-3) 都已存在 — Round-3 为 TOC 加好了, 但 Hero 4 卡完全没用它们。PE partner 点击 Thesis 4 落到 §3.0 chapter intro, 需手动滚 78 行经过 §3.1 + §3.2 才到 §3.3 仓储 ROI 内容。response-3 v2-new-i3 表里写 'clickable to §3.1/§3.2/§6.5/§3.3' 与实际不一致。

**what would resolve**:
- L289 href `#ch-commercial-cliff` → `#sec-3-1`
- L294 href `#ch-commercial-cliff` → `#sec-3-2`
- L304 href `#ch-commercial-cliff` → `#sec-3-3`

### v3-i2 (moderate) — Chart.js 7 张 cartesian chart 仍缺至少 1 个 axis title

**attacks**: chart 可读性 / PDF export 可解释性

**detail**: Python AST 扫描显示 26 chart 中排除 doughnut/pie/radar 后 17 个 cartesian。其中下列仍缺 scales.{x|y}.title.text:
- chartScenarioShipment (vertical bar, x '情景' 无 title)
- chartChinaShipmentBreakdown (horizontal bar, x value 轴无 title)
- chartBomBreakdown (vertical bar, x '部件' 无 title)
- chartPenetration (line, x 年份无 title)
- chartPriceMatrix (vertical bar, x 玩家无 title)
- chartScenarioCompare (vertical bar, x 情景无 title)
- chartPSRComparison (line, x 年份无 title — y 有 'LTM PSR 倍数 log scale' 已加)

PE partner 把页面 'export to PDF for IC' 时, 黑白印刷 x 轴无标题 → IC reviewer 问 'x 轴是什么'。这是 PE 工作流第二阶段的可读性问题, 不是页面渲染问题。

**what would resolve**: 为 7 张 cartesian chart 各加 1 行 `scales.x.title.text` — 总耗时 ~30 秒。

### v3-i3 (minor) — Line 2532 qa-challenge 误用 border-green-300

**attacks**: qa-pair 视觉一致性

**detail**: v3.report.html L2532 `<div class="qa-challenge bg-red-50 p-3 rounded text-sm border-l-2 border-green-300">` — qa-challenge (反方挑战) 应该全部用 border-red-300 维持 9 个 Q 的视觉一致性 (L2447 / 2464 / 2481 / 2498 / 2515 / 2548 / 2565 / 2582 均 border-red-300)。仅此 1 处误用 border-green-300, 使第 6 个 Q 的反方挑战左边界变绿 — 与下方'我们的答复'(也是绿) 混淆。

**what would resolve**: L2532 `border-green-300` → `border-red-300`。

### v3-i4 (minor) — caption 计数不一致 + 数据置信度表无 overflow-x 保护

**attacks**: table caption a11y 部分完成度 / mobile overflow 一致性

**detail**:
- (a) response-3 v2-new-i11 'Added <caption> to 10 core PE-workflow tables', 实际 `grep -c '<caption>'` = 9。差异在哪张 builder 未说明。不影响功能性, 但 builder 自标 citation 与实际不一致 — response-3 整体精度大幅提升 (R2 有 8 处 phantom; R3 仅此 1 处 errata), 仍未到 0 errata。
- (b) L4471 `<table class="pro text-sm mt-3">` (数据置信度表, 5 列) 不在 `<div class="overflow-x-auto">` wrapper 内 (父 div L4468 是 `<div class="data-card">`), 是 v3 30 张 pro 表中唯一一张缺 overflow-x 保护。iPad 竖屏 768px 下 5 列宽表会强制 overflow document body 触发整页水平滚动条。

**what would resolve**:
- (a) 在 response-4 校对 caption 计数 (9 vs 10)。
- (b) L4470-4471 在 `<table>` 前插入 `<div class="overflow-x-auto">` 并在 `</table>` 后闭合。

## Status of Round-2 issues

| ID | Status | Reason |
|---|---|---|
| v2-new-i1 (8 phantom CSS) | **resolved** | L193-265 全部 8 class 有完整 CSS rule (含 mobile order swap @media) |
| v2-new-i2 (TOC 11 重复 href) | **resolved** | 13 个 sec-X-Y anchor ship, TOC nav 内 0 重复 |
| v2-new-i3 (Hero 替换) | **partial** | 文本 layer ship, 锚链接 layer 失败 (3/4 卡片 → chapter-top) — 详 v3-i1 |
| v2-new-i4 (DCF KPI promote) | **resolved** | L1961-1975 真正插入 3 张 KPI 卡 |
| v2-new-i5 (LTV:CAC 红底) | **resolved** | L2120 红底 + 内联 ⚠ + 绿 ✓ 对照 |
| v2-new-i6 (色盲 icon) | **resolved** | L262-265 4 种 box ::before content icon ship |
| v2-new-i7 (chartPSRComparison) | **resolved** | log scale + 3 EV anchor lines visible |
| v2-new-i8 (Risk Register table) | **resolved** | L2693-2710 4 列 P×I scoring + caption |
| v2-new-i9 (退出 IRR 列) | **resolved** | L2729 第 7 列 + 公式 + traffic-light |
| v2-new-i10 (Comps Figure stale) | **resolved** | L2065 同步 1,300-2,600× / $39B |
| v2-new-i11 (table caption) | **partial** | 9 caption / 30 pro 表 (response 称 10) — 详 v3-i4 |
| v2-new-i12 (lazy chart) | **unresolved** | accepted-limitation, no actual lazy init |
| v2-new-i13 (li/div nesting) | **resolved** | L1051 div→span 改完 |
| i6_round-1 (lazy chart) | **unresolved** | 同 v2-new-i12 |
| i9_round-1 (table caption) | **partial** | 30% 覆盖率, 核心 10 张已加, ~21 张待补 |
| i11_round-1 (SVG a11y) | **unresolved** | accepted-limitation |
| i14_round-1 (§3.6 4 列表) | **unresolved** | accepted-limitation |
