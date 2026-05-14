# 架构 v2：报告生成 Pipeline（实战验证版）

> 经过实战验证后的具身智能行业报告生成 pipeline。所有 skill / agent / 工具的"实际有用度"基于本次报告完整生产周期的实测，非理论推荐。

---

## 实战验证的 Pipeline（5 阶段）

```
Phase 1: 框架对标（人工，0.5h）
   ├─ 选定对标参考（弘毅资本电池报告）
   ├─ 提炼框架要素：CR3 / 三段式产业链 / 不可能三角 / 三情景 / IRA 详解
   └─ 设计本报告大纲（适配 AI 层 + 原材料层）

Phase 2: 并行铺底（Round 1，~25 min）
   ├─ 5 个 general-purpose subagent 并行：
   │   ├─ Agent 1: 市场规模 + 渗透率（市场层）
   │   ├─ Agent 2: 上游硬件 10 大零部件（硬件层）
   │   ├─ Agent 3: 中游 AI 模型 / 仿真 / 数据 / 算力（AI 层）
   │   ├─ Agent 4: 下游 44 家整机厂（整机层）
   │   └─ Agent 5: 政策 + 三情景 + 投资框架（框架层）
   └─ 输出：5 个 markdown 分章

Phase 3: 自评 + 补强（Round 2，~10 min）
   └─ 1 个补强 agent 填 4 个缺口：
       ├─ 基础原材料层（稀土/铜/PEEK/碳纤维三段式）
       ├─ 投资项目清单（40+ 项）
       ├─ 中国补贴省级分布（550+ 亿）
       └─ 2026 Q1-Q2 事件年表

Phase 4: 视觉化（HTML 单文件，~30 min 含修订）
   ├─ Tailwind + Chart.js + Mermaid + 自绘 SVG
   ├─ 25+ 图表（饼图/柱图/雷达/折线/散点/时间轴）
   ├─ KPI 卡片 + 信息盒（4 类彩色）
   └─ 可印为 PDF（@media print 优化）

Phase 5: 验证 + 增强（Round 3，~15 min 并行）
   ├─ Agent A: financial-services-plugins 评估（哪些有用）
   ├─ Agent B: References DB 构建（206 refs + 210 data points + 81 companies）
   └─ Agent C: 对抗性评审（debate-critic 子 agent）
   ↓
   合成阶段（~20 min）：
   ├─ 应用 Agent A 推荐的 3 个 Tier 1 skill
   ├─ 集成 Agent B 数据库 + 修正 2 处口径矛盾
   └─ 应用 Agent C 找到的 3 处致命漏洞 + 7 处严重问题 + ERRATA 章节
```

**总时长**：~110 min（含等待并行 agent）

---

## Skill 实战有用度（实测）

### ✅ Tier 1 强烈推荐 · 实际产生增量

| Skill / Tool | 何时使用 | 实测增量 |
|---|---|---|
| **Agent (general-purpose)** | Phase 2-3 | 5 并行 + 1 补强 + 3 验证 = 9 个 agent 是本 pipeline 的骨架 |
| **WebSearch / WebFetch** (subagent 内调用) | Phase 2-3 | 总计 ~150 次搜索，是数据收集的实质 |
| **Anthropic financial-services-plugins**: `/ic-memo` | Phase 5 合成 | 加了智元 1-page IC memo（§3.5）→ "标的级收口"质变 |
| **financial-services-plugins**: `/unit-economics` | Phase 5 合成 | 加了 RaaS / 售卖 / 订阅 三模式 LTV·CAC·NDR 对照（§2.5.Z）→ 解锁"美系估值溢价"的真实根源 |
| **financial-services-plugins**: `/comps-analysis` | Phase 5 合成 | 加了 EV/Sales quartile 对照表（§2.5.Y）→ "780× vs Symbotic 4.5×" 的定位 |
| **debate-critic subagent** | Phase 5 | 找出 3 处致命漏洞 + 7 处严重问题（宇树营收口径错位、出货量 vs 保有量混淆、概率拍脑袋）|
| **References DB 自建（Python 脚本）** | Phase 5 | 206 refs / 210 data points / 81 companies，可追溯 → "PE IC 交付"门槛 |
| **pdftotext (poppler)** | Phase 1 | 读取 Reference PDF |
| **TodoWrite** | 全程 | 任务跟踪 |

### ⬛ Tier 2 部分采用 · 看场景

| Skill / Tool | 状态 | 备注 |
|---|---|---|
| **`/dd-checklist`** | 未应用（时间不够） | 应该补法律 / 运营 / ESG 三个 workstream |
| **`market-researcher` 的 [UNSOURCED] 规范** | 部分应用 | IC memo 内有 [UNSOURCED] 标注；全报告 audit 留待下次 |
| **`/returns-analysis`** | 未应用 | 智元 IC memo 内 returns table 部分借鉴 |
| **`anthropic-skills:canvas-design`** | 未应用 | 应用于做封面 / 概念图 |

### ⬜ Tier 3 不推荐 · 噱头大于实质

- `private-equity/value-creation-plan` / `/portfolio-monitoring` / `/deal-sourcing` / `/deal-screening` / `/dd-meeting-prep` — deal-level 或 post-deal 工具，对 sector report 是 hammer-looking-for-nails
- `equity-research/initiating-coverage` / `/thesis-tracker` — 强行套用反而**有害**（破坏行业视角）
- `investment-banking/cim-builder` — 我们不是在 sell-side
- `product-management:write-spec` — PRD 工具，无关
- `figma:*` — 没有 Figma 账号，且 HTML 已能交付

---

## 关键架构决策（事后回看）

### ✅ 做对的

1. **5 个并行 agent 而不是顺序 1 个** —— Round 1 的 25 min 顺序做要 2+ 小时
2. **拆分维度 = Reference 维度** —— 这样合成时直接映射，不用重组
3. **自评 + 补强 Round 2** —— 找到 4 个缺口比啥也不查直接 v2 稳得多
4. **HTML 单文件而不是 PPT** —— 改一次预览一次比 PPT 工作流快 10×
5. **3 个并行验证 agent（Skill / DB / Adversarial）** —— 一起出，互不阻塞
6. **ERRATA 章节公开承认致命漏洞** —— 这是真正的 PE ethic，比"silently 修订"专业 10×

### ❌ 做错的（已修订）

1. **第一版没用 Anthropic 官方 skill** —— 自己手搓 IC memo / unit economics，质量不如 skill 模板，浪费 30 min
2. **没用 References DB 跑数据点** —— 导致 210 个数据点散落，引用混乱，2 处一手源矛盾未发现
3. **没让 critic agent 评审** —— 导致 3 处致命漏洞自检漏过（宇树营收口径、出货 vs 保有量混淆、概率拍脑袋）
4. **数字交叉验证不足** —— 32 个数据点最终标为 low confidence，"低置信度但用于核心论点"21 个
5. **第一版没做 [UNSOURCED] 标注** —— 数字 sourcing 纪律弱

### 🔄 下次应该的

1. **Phase 5 提前到 Phase 3** —— 把 Skill 评估 + adversarial review 在补强之前做，避免无用功
2. **References DB 在 Phase 2 同步建** —— 每个 subagent 输出时强制要求 JSON refs，省后期 audit
3. **加 Phase 6 = 飞书 / Excel 导出** —— 用 `lark-doc` + `lark-base` + `anthropic-skills:xlsx` 把数据导出成可协作 / 可计算的形态
4. **加 Phase 7 = 一手访谈** —— 联系 3-5 个真实从业者（智元 / 宇树 / Figure ex-employee / 车厂采购）做半小时访谈，补"非公开信号"

---

## 复盘：Skills 浪费 vs 利用

| 阶段 | 实际 token / 时间 | 浪费率 |
|---|---|---|
| Phase 1 框架对标 | 0% 浪费（必需） | 0% |
| Phase 2 5 并行 agent | 实际有效 ~80% / 重复内容 ~20% | 20% |
| Phase 3 1 补强 agent | 实际有效 ~95% | 5% |
| Phase 4 HTML 视觉化 | 实际有效 ~90%；少量布局返工 | 10% |
| Phase 5 3 验证 agent | 实际有效 ~85%；Skill 评估 agent 部分 deal-level skill 是浪费 | 15% |
| **总浪费率** | **~12%** | 主要在 deal-level skill 评估 |

**核心 takeaway**：单纯 Agent + WebSearch 这套"笨办法"覆盖了 70%，Skills 增量 30%（IC memo + unit econ + comps + DB + critic），但这 30% 是质变所在。

---

## 复用：把这个 Pipeline 固化为 Skill

应当用 `anthropic-skills:skill-creator` 将本 pipeline 固化为：

```
skill name: industry-report-generator
inputs:
  --reference <pdf>     # 对标参考报告
  --industry <topic>    # 行业 / 主题
  --depth <basic|deep|pe-grade>
  --rounds <N>          # 迭代轮数
  --skills-on <list>    # ic-memo,unit-economics,comps-analysis,...
output:
  - 6 个分章 markdown
  - 1 个主报告（FULL_REPORT.md）
  - 1 个 HTML（report.html）
  - data/references.json + data/data_points.json + data/companies.json
  - ADVERSARIAL_REVIEW.md
  - SKILL_EVALUATION.md
```

预计**重做下一个行业报告**（如 AI 编程工具、固态电池、商业航天）只需 60 min（从 110 → 60 min，2× 加速）。

---

## 当前文件清单

```
embodied_ai_report/
├── PIPELINE.md                   # v1 初版 pipeline 设计
├── ARCHITECTURE_V2.md            # ★ 本文件 - 实战架构 v2
├── SKILL_EVALUATION.md           # financial-services-plugins 评估报告
├── ADVERSARIAL_REVIEW.md         # 对抗性评审报告（3 致命 + 10 严重）
├── FULL_REPORT_v1.md             # 主报告 v1 留档
├── FULL_REPORT.md                # 主报告 v2（含 ERRATA）
├── report.html                   # ★ HTML 报告（242KB / 28 sections / 25+ 图表）
├── sections/                     # 6 个深度分章 markdown
│   ├── 01_market.md              (27 KB / 6,800 字)
│   ├── 02_upstream_hardware.md   (37 KB / 14,500 字)
│   ├── 03_midstream_ai.md        (30 KB / 7,000 字)
│   ├── 04_downstream_oems.md     (37 KB / 9,000 字)
│   ├── 05_policy_scenarios.md    (36 KB / 11,000 字)
│   └── 06_round2_supplement.md   (25 KB / 6,200 字)
└── data/                         # ★ 结构化数据
    ├── references.json           (206 refs, 63 KB)
    ├── data_points.json          (210 facts, 57 KB)
    ├── companies.json            (81 companies, 32 KB)
    └── references_index.md       (38 KB, 人类可读索引)
```

**总产出**：~530 KB / ~7 万中文字 / ~70 张图表 / 206 引用 / 210 数据点 / 81 公司档案。
