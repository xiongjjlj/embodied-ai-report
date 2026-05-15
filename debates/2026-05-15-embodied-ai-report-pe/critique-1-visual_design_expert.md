# Critique 1 · visual_design_expert

## Verdict: **BLOCK**

执行摘要的 8 个 KPI 卡片堆挤无视觉优先级，导致最核心的 3 条 thesis（Tesla "not in material use" / Tier A ≈ 0 / Figure PSR 790×）在 hero+exec summary 共 12 张卡片中完全缺位。同时 chartValuationTop10 x 轴单位混乱（"亿美元 / 0.1B" 双重标注 + tooltip 除以 10），破坏第 5 章核心估值对比图。一个 PE partner 在 iPad 上 90 秒能拿到的是 "信息密度过载但优先级不清" 的印象，而不是报告本身在第三章揭示的尖锐论点。

---

## What this draft is trying to do

**PE 战略 pitch + 行业研究** —— 4,672 行 HTML 单页报告，包含：
- 26 张 Chart.js（doughnut / bar / radar / scatter / line / logarithmic）
- 24 张 `.pro` 表（最大的 16 行 × 5 列）
- 4 张 mermaid 流程图
- 2 张内嵌 SVG 不可能三角
- 10 张 KPI card 在执行摘要
- 10 个投委会 Q&A + 1 份 IC Memo

目标读者：PE partner（中后台决策者），device anchor 是 iPad（横竖屏可能切换）。

---

## The load-bearing claims

1. 执行摘要 + 8 个 KPI 卡片能让 PE partner 在 **90 秒**内 get 核心论点
2. 三种情景概率（35/15-25/40）+ 2030 累计保有量预测靠 2 张并列图传达
3. **Figure $39B 估值泡沫**论据靠 chartValuationTop10 + chartPSRComparison + §6.5.1 DCF 表 + §6.5.2 Comps 表四路证据合围
4. 中美 16 环节能力差异靠 chartCapabilityRadar + 16 行表传达
5. 10 个投委会问题 + 智元 IC Memo（附录 A.4-A.5）作为 deal-level pitch 工具

---

## Issues

### Fatal

**[i1] chartValuationTop10 x 轴单位混乱（line 4426-4440）**
- attacks: claim 3（Figure 估值泡沫论据）
- 数据是 `[395, 140, 110, 50, 44, 30, 28, 28, 17, 14]`（以"亿美元"为单位，Figure $39.5B = 395 亿美元）
- 但 x 轴 title 写 `估值（亿美元 / 0.1B）` 同时标注两种单位；tooltip 又 `(ctx.parsed.x/10).toFixed(1) + 'B'`
- 中文"亿美元"与英文 B（Billion）相差 10×（1B = 10 亿），读者第一眼看到 395 这个数字会困惑"这是 $395B 吗"
- 这是 PE partner 滚到 §5.4 第一眼看到的 anchor chart——单位错乱直接破坏"美系 5-10× 中系"核心论据
- **Resolve**: 数据全除以 10 改为 $B（39.5, 14, 11, 5...），x 轴改 "Valuation (USD Bn)"，tooltip 改为 `'$' + ctx.parsed.x.toFixed(1) + 'B'`

**[i2] 执行摘要 8 个 KPI 卡片无视觉优先级（line 313-346）**
- attacks: claim 1（90 秒 get 核心论点）
- 8 张卡全部用同样的 .kpi-card 样式横排（2x4 on md+），无层级
- 8 张是：1.8万出货 / 80-95% 中国占比 / 2.8× BOM / $39.5B Figure / ¥373亿融资 / ¥550+亿补贴 / $75亿 TAM / 69-113% CAGR——全部是"行业 anchor"
- 但报告真正改变投资动作的 thesis（Tesla "not in usage" / Tier A=0 / Figure PSR 790× vs 蔚来 IPO 53× / 仓储战争 ROI 差 5-16× / 美系 5 家合计 PSR 757×）**没有一条进入执行摘要的 KPI 卡片**
- PE partner 看完 8 个 KPI 的印象是中性 narrative，完全感受不到第三章的尖锐论点
- **Resolve**: KPI 卡片降为 4 张行业 anchor，新增独立的"5 条 thesis statements"红色高亮卡片组，每条配 1 句 evidence + §章节锚点

### Severe

**[i3] chartShipmentTop10 把 Tesla 1,000 台仍排在第 8 位（line 4443-4457）**
- attacks: claim 2 + claim 3
- 用 #9ca3af 灰色降级 + `* useful work 受质疑` 注释，但 Tesla 仍出现在 Top10 排序中
- §3.2 line 760 已明确"Tesla 自厂 1,000 台——剔除，不是订单"
- chart 与表结论自相矛盾：表里剔除、图里只是灰色，PE partner 视觉锚定先于读 caveat
- 同样问题：chartChinaShipmentBreakdown 把宇树 5,500 + 智元 5,168 当作 Top6 厂商，但 §5.4 line 1354 又承认"含大量非人形（机器狗+工业版+人形全口径）"——图标题不警示，读者会误读
- **Resolve**: chartShipmentTop10 直接剔除 Tesla；chartChinaShipmentBreakdown 改 stacked bar 拆分人形/机器狗/工业版

**[i4] §6.5.1 DCF sanity check 表关键 "市场 vs sanity 比值" 埋在倒数第 3 行（line 1819-1849）**
- attacks: claim 3
- 表有 13 行 5 列。punch line `Figure 市场 45× sanity / 智元 16× / 宇树 12×` 在第 11 行
- PE partner 必须从"2025 营收 → 2025 出货 → 2030 出货 → ASP → 收入 → 毛利率 → 毛利 → EBIT → WACC → 折现 → 永续期 → sanity check → 市场估值 → 比值"13 行才看到结论
- iPad 竖屏需纵向滚动，90 秒读不到第 13 行
- 同样问题 §6.5.2 Comps 表：Figure 790× 这个核心数字与 EV IPO 中位 22× / OpenAI 50× 的比较散落注释
- **Resolve**: 表上方加 3 张 KPI 卡片 promote 比值（Figure 45× / 智元 16× / 宇树 12×）；或在 thead 下方插入红底 bold summary row

**[i5] chartPSRComparison 用对数 y 轴压扁了 Figure vs 蔚来 20× 差距（line 4603-4620）**
- attacks: claim 3
- Figure PSR 400 vs 蔚来 PSR 20 在对数轴上只有 1.3× 视觉高度差，实际是 20× 数量级
- 报告核心论点"Figure 真泡沫"需要 visceral 视觉冲击，对数轴反而弱化
- Figure 2024 PSR=100 → 2025 PSR=400 跳跃 4× 无 caption 解释（应该是 RaaS bookings 没起来 + 估值 jump 双因素）
- **Resolve**: 改 linear 轴 max=500 让 Figure 冲出顶部；或加 horizontal annotation line + 文字标注"20× 蔚来 IPO 高位"

**[i6] 26 张 Chart.js 全部一次性同步渲染，iPad 上初次白屏 5-10 秒（line 4234-4668）**
- attacks: claim 1（90 秒原则）
- 所有 chart init 在文档末同一 `<script>` 块同步执行，无 IntersectionObserver
- 4 个 mermaid 图额外占 1-2 秒
- iPad 上 hero 渲染完 + 白屏滚动 5-10 秒 + chart 跳出——前 10 秒就在等渲染
- **Resolve**: IntersectionObserver 延迟非首屏 chart 到滚入视口前 200px 才 init；执行摘要的 chartScenarioProb + chartScenarioShipment 保留同步

**[i7] TOC 三条不同链接指向同一锚点 #ch-why-now（line 244-247）**
- attacks: claim 1 + 导航
- `为什么是现在` / `顶尖人物 10×5 矩阵` / `5 条核心分歧线` 三个 href 都是 `#ch-why-now`
- §1.2 / §1.3 没有独立 anchor，PE 点击 "顶尖人物矩阵" 跳到 §1.1 顶部需再滚 20 行
- 同样问题 #ch-tech-routes 也是 3 个子项指同一锚点（line 251-253）
- **Resolve**: 为 §1.2 / §1.3 / §2.2 / §2.3 / §2.4 加独立 id，TOC href 分别对应

**[i8] §6.5.3 Unit Economics 表 LTV:CAC 行数据未高亮，punch line 在表外（line 1911-1932）**
- attacks: claim 3
- 4 列 ×8 行表，关键 LTV:CAC 行 `2-5× / 2-5× / 10-40× / ~5×` 无视觉锚点
- 结论"RaaS LTV:CAC 仅 2-5×，相对售卖（10-40×）没有数量级优势"在表外 insight-box
- 表内 [INFERRED] / [UNDISCLOSED] 标记出现 14 次造成视觉嘈杂
- **Resolve**: LTV:CAC 行 #fee2e2 红底高亮 + 在 RaaS 两列加 `⚠️ no order of magnitude advantage`；[INFERRED] 改用统一 icon 系统

**[i9] 24 张表无一使用 `<caption>` 元素，HTML scraper / 屏幕阅读器丢失上下文**
- attacks: a11y + 可移植性
- 24 张表只用上方 `<h3>` 或 `<p>` 描述，没有 DOM 关联
- PE partner 用 Reader Mode 或导出 PDF 时 caption 缺失
- 24 张表全部用同 .pro 样式，没有视觉差异化：tier 表 / 10 行人物矩阵 / 16 行中美对比 三种体量同等权重
- **Resolve**: 加 `<caption>` 或 `aria-labelledby`；核心表（§3.2 / §6.5.1 / §6.5.2）用 .pro-key 突出样式

### Moderate

**[i10] 投委会 Q1-Q10 红/绿对照在 iPad 竖屏会堆叠成 "红挑战 → 绿答复"，10 段红色 critique 主导视觉（line 2188-2369）**
- 全部用 `grid md:grid-cols-2`，md=768px 临界
- iPad mini 竖屏 + iPad 单手竖屏可能落 sm 单列
- 单列模式下"反方挑战"永远在上、"我们答复"在下——10 个 Q 滑下来是 10 段红色 critique 主导
- **Resolve**: 用 CSS `order` 让绿色 box 排在红色 box 上方；或 sm/md 单列用 `<details>` 折叠挑战

**[i11] §6.2 两个 SVG 不可能三角无 axis / 无 quantify / 无 a11y（line 1566-1607）**
- 数据点位置 hardcoded（美国 cx=140 cy=180 等），读者无法 quantify 强度
- 三个圆点都在中部，谁更接近哪个维度仅靠肉眼粗判
- SVG 无 `<title>` / `<desc>` / role='img'，a11y 空白
- **Resolve**: 三角形外加 0-5 量化轴或改用 ternary plot；每个 SVG 加 title + aria-label

**[i12] Hero 4 张卡片传达"研究广度"而非"投资结论"（line 205-222）**
- "5 层 / 44 家 / ~6 万字 / 25+ 图" 是工程量指标
- PE pitch 的 first impression 应是 thesis + risk/return，不是"研究了多少家"
- 与下方 "STRICTLY PRIVATE AND CONFIDENTIAL" PE pitch tone 不一致——hero 风格定位错了
- "25+ 图"在 hero 出现但执行摘要里更应有"美系一线加权 PSR 757× / Tier A=0"
- **Resolve**: 4 张卡片替换为 4 条 thesis statement，每条配章节锚链接；工作量信息放 footer

**[i13] 色彩使用：warning/insight/success/info 四种 box 在 §3.1-3.7 混用 12 次，色盲用户无法区分**
- 仅靠左边框颜色 + 浅背景区分；CTA 文字字号一致，无 icon prefix
- 红绿色盲（8% 男性）会把 warning 与 success 视为同色
- §3 共 8 个 warning-box → 警告太多 dilution，失去 anchor 功能
- **Resolve**: 每种 box 加专属 icon prefix（⚠️ 💡 ✅ ℹ️）；warning 仅用于真正改变 investment action 的结论

**[i14] §3.6 投资动作变更表 4 列 × 10 行无 colgroup，行高 80-120px 导致整表占 1.5 屏（line 845-918）**
- 最后一列"对投资动作的影响"每行 60-120 字
- iPad 横屏每列被挤到 200-280px
- 10 行垂直 1000-1200px，需滚 1.5 屏才读完
- 应该 5 秒抓 takeaway 实际需 60 秒
- **Resolve**: 拆为 2 列对照式（合并"原结论→修订后"为一列）；或加 colgroup 指定 width 20/20/25/35

### Minor

**[i15] §3.7 第六条 takeaway 的 quotable sound bite "任何不含 MTBF 的 PE deck 都不算完整尽调" 仅用 strong 加粗，没有 pull-quote 样式**
- 报告少数可被 PE 直接 quote 到 IC 会议的 sound bite 压在 ol 列表第 6 行
- 整份报告缺少 .pullquote 组件（large italic + 引号 icon）
- **Resolve**: 新增 .pullquote CSS 类，promote 6-8 条最具传播力的论断

---

## Status of prior issues

N/A (Round 1)
