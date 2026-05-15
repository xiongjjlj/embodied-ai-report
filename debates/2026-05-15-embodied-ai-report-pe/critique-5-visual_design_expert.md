# Round-5 critique — visual_design_expert

**Verdict: PASS.** 两个 round-4 minor 全部 resolved (v4-i1 SST limitation-note 缩进风格统一 / v4-i2 marker 自报与实际 grep 一致性已修正)。Round-5 新加 15 处 markup 内容遵守已建立视觉规约, 无视觉 regression, 无 phantom CSS class 引入。仅记 1 个 minor 观察 (新 SST table caption 过长), 不构成 block。

---

## 这份草稿要做什么

PE 战略 pitch + 行业研究 HTML 单页报告。Round-5 内容大改 (capture-probability 列从 0 到 1 / 6-路径表 → 7-路径表 / per-company g 拆分 / WACC 智元 21% / 宇树 18% 拆分等), 但全部在 markup 端 — `<style>` 块行号 10-274 与 v4 字节级一致, round-5 0 触碰 CSS。我的工作是验证: (a) 新 markup 是否遵守已建立视觉规约, (b) tag 是否仍平衡, (c) 是否引入 phantom CSS class, (d) 旧 minor (v4-i1 缩进 / v4-i2 errata) 是否真 resolved。

## load-bearing 视觉论点

1. Round-3/4 落地的所有 custom CSS class (.thesis-banner / .pullquote / .qa-pair / .qa-challenge / .qa-answer / .limitation-note / .sensitivity-table / .chart-loaded + 30 余个其他) 在 v5 `<style>` 块全部仍定义且 round-5 未触碰 `<style>` 块。
2. v5 TOC 33 href 0 duplicates; 13 个 sec-X-Y granular 锚仍可点击。
3. v5 HTML tag balance 完整 (div 976:976, table 33:33, section 35:35, thead 33:33, tbody 33:33, tr 321:321, strong 785:785, span 640:640, em 30:30, sub 2:2, sup 1:1)。
4. Round-5 新增 capture-probability 列在 SST 表 (line 2680-2691) 结构正确: thead 8 个 th = 每行 8 个 td, 全包在 overflow-x-auto 内。
5. Round-5 §4 新增 ⑦c Apptronik OEM-locked 行 (5 列 / 5 td), 用 border-top:4px solid #7c3aed (purple) 作 visual marker — 复用 L556 / L627 / L705 / L1145 已建立的 purple idiom, 不是 phantom 色值。
6. 30 张 pro 表仍 100% wrap in overflow-x-auto (30 pro 表 + 33 overflow wrapper = 多余 3 个包非 pro 表)。

## Issues

### v5-i1 (minor) — L2681 新 SST table caption 长度 outlier (395 chars vs 同文件中位 ~92 字符)

L2681:
```
<caption>智元 5-yr Returns Analysis — entry $3.6-4.2B (mid $3.9B); 5 macro scenarios 35/35/12.5/12.5/5 = 100% (US-led 25% = Bear-A + Bear-B, 与 §6.3 SoT 同步); 新增 P(智元 captures|scenario) 列 — 反映 China-led / Bifurcation 阵营内 智元 不一定是 winner (7-way Chinese-pole 竞争: 宇树/银河通用/智元/字节/蚂蚁/京东/优必选); Round-5 r4-n1 fix</caption>
```
395 chars。同文件其他 8 个 `<caption>` 长度: L1824 168, L2018 121, L2032 56, L2066 96, L2317 35, L2391 78, L2701 73, L2733 92。中位 ~92, 95-percentile ~170。v5 L2681 是 4× 中位 outlier。

CSS 中 caption-side 默认 top, text-align 默认 center → 在 768px portrait / 手机屏会 wrap 4-5 行, 把 thead 压低, visual hierarchy 上 caption 抢 thead 风头。不破坏 layout, 但 dense。

**What would resolve**: 拆为短 caption (~80 chars, 留主标题 + Round-5 r4-n1 tag) + 下方 `<p class="text-sm">` 装 7-way 竞争 actor 全列举 + Round-5 reasoning。或保留长 caption 但加 inline style `text-align:left; max-width: 60ch`。2 分钟。不 block。

---

## Round-4 issue status

| Issue | Status | 一句解释 |
|---|---|---|
| **v4-i1** L2695 SST limitation-note 缺起始空格 | **resolved** | `grep -n '^ <div class=\"limitation-note\"><strong>Single Source of Truth' v5` → L2696 命中 (1 space + < 起始). round-5 r4-n1 SST footnote 重写时 incidentally 修正. response-5 visual.v4-i1 row 显式 'CONCEDED + REVISED (incidentally)'. |
| **v4-i2** response-4 自称 '22 Round-4 markers' 实际 23 | **resolved** | response-5 line 5 显式 'Round-5 markers: 15. Round-4 markers retained: 23'. grep -c 'Round-4' v5 = 23 ✓; grep -c 'Round-5' v5 = 15 ✓. response-5 visual.v4-i2 row 'ACKNOWLEDGED (errata)' 显式认错并校正. |

## 持续 accepted-limitation (round-6+ carry-forward, builder 显式 acknowledge)

- v3-i2: 7 个 cartesian chart (chartScenarioShipment / chartChinaShipmentBreakdown / chartBomBreakdown / chartPenetration / chartPriceMatrix / chartScenarioCompare / chartPSRComparison) 仍缺 x-axis title。v5.md carry-forward #5。
- v2-new-i11 / i9-r1: 9/30 `<caption>` 覆盖 (30%), round-5 未加新 caption。v5.md carry-forward #6。
- v2-new-i12 / i6-r1: 26 个 new Chart() 仍同步立即执行, 仅 IntersectionObserver fade-in。v5.md carry-forward #3。
- i11-r1: SVG 不可能三角仍无 `<title>/<desc>/role='img'`。v5.md carry-forward #4。
- i14-r1: §3.6 投资动作变更表第 4 列 dense 文字未变。

所有这些 round-5 未改善 0 退化, builder 已显式承认 → 不构成 block。

## Round-5 markup 验证 (grep-based)

- 15 个 'Round-5' marker grep -c 验证 = 15 ✓
- 23 个 'Round-4' marker retained grep -c 验证 = 23 ✓
- `<style>` 块 line 10-274 与 v4 字节级一致 (round-5 未触碰)
- 全部 9 个 `<caption>` 仍存在 (round-5 未加新 caption, 与 response-5 一致)
- 7-路径表新行 (L1174) 5 个 td (= header 5 th); SST 表新列每行 8 td (= header 8 th); 0 column-mismatch
- 0 phantom CSS class 引入 — 36 个 custom 类全部在 `<style>` 块有规则定义

## 结论

PASS。Round-5 markup 大改 (capture-probability 列重建 / 7-路径行 / per-company g 拆分 / WACC 智元 21% / 宇树 18% / 35% bifurcation 校正 / 24×/$0.17B IC intro 同步 / [UNDISCLOSED] 同步) 全部干净落地, 视觉规约一致, tag 平衡完整, 旧 minor 全部 resolved。仅 1 个 cosmetic 观察 (L2681 caption 过长) 标 minor, 不 block。

`persona=visual_design_expert, verdict=pass, prior=2R/0P/0U, new=0F,0S,0M,1m`
