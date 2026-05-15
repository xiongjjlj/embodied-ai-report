# Numerical Auditor — Round 4 Critique

## Verdict: PASS

Round-4 的 SST (Single Source of Truth) 改造真正落地. 7 / 8 个 round-3 issues resolved (+1 explicitly deferred + accepted partial). 报告核心数学链 (3×3 g/WACC + Returns table + 2×2 概率矩阵) 现在三个 SST cell 全部独立可复算. Verdict 从 round-3 block → round-4 pass. 3 处 moderate 残留, 不阻塞 verdict.

## What this draft is trying to do

PE 视角具身智能产业链报告 v4 (中文). Round-4 的核心 brief 是把 round-3 的 5 个不同 E[IRR] 数字 (24.6 / 26.1 / 27.3 / 28 / 29) + 2 个 MOIC 数字 (4.4× / 4.8×) + 3×3 sensitivity 9 cell 中 6 不闭合 cell + US-led 概率 +10pp gap 这一组 fatal/severe 数学不自洽问题, 通过引入 **Single Source of Truth (SST)** 改造收敛为单一 canonical 数字, 并通过 inline 公式 + 独立 worked example 让 reader 可复算.

## Load-bearing claims

1. **LBC-1** 美强软件中强硬件 — BOM 剪刀差 2.8-4.1×
2. **LBC-2** 2030 TAM $30-144 亿 (中位 $75 亿)
3. **LBC-3** 三情景 Bifurcation 35 / China-led 35 / US-led 25 / Other 5 = 100% (**Round-4 SST canonical**)
4. **LBC-4** Figure LTM PSR 1,300-2,600× = 真泡沫; 3×3 sensitivity $0.61-1.40B / 28-64× canonical; 智元 E[MOIC] 4.6× / E[IRR] 23.6% ≈ 24% 名义 / LP 14.6% ≈ 15% real (**Round-4 SST cell**)
5. **LBC-5** 中系核心零部件 + 稀土永磁卡点 alpha; OEM-locked 美系一档单独

## Independent numerical verification (python)

### 3×3 g/WACC sensitivity matrix

Stated formula: V = EBIT × df_4yr × [1 + 1/(WACC-g)], df_4yr = 1/(1+WACC)^4, EBIT = $163M.

| g \ W | 12% | 15% (base) | 18% |
|-------|-----|------------|-----|
| 2%    | published $1.14B / my $1.139B / ratio 34× / mine 34.2 ✓ | $0.81B / $0.810B / 48× / 48.1 ✓ | $0.61B / $0.610B / 64× / 64.0 ✓ |
| 3% (base) | $1.26B / $1.255B / 31× / 31.1 ✓ | **$0.87B / $0.870B / 45× / 44.8 ✓** | $0.64B / $0.645B / 61× / 60.5 ✓ |
| 4%    | $1.40B / $1.398B / 28× / 27.9 ✓ | $0.94B / $0.940B / 41× / 41.5 ✓ | $0.68B / $0.685B / 57× / 57.0 ✓ |

**All 9 cells reproduce within 1%. Range $0.61-1.40B / 28-64× canonical published, matches.**

### MOIC / IRR canonical set

```
E[MOIC] = 0.35×9.0 + 0.35×3.8 + 0.125×0.77 + 0.125×0.13 + 0.05×0.12
       = 3.15 + 1.33 + 0.09625 + 0.01625 + 0.006
       = 4.5985 ≈ 4.6×    ✓ (published 4.6× canonical)

E[IRR] = 0.35×55 + 0.35×31 + 0.125×(-5) + 0.125×(-33) + 0.05×(-35)
      = 19.25 + 10.85 - 0.625 - 4.125 - 1.75
      = 23.6%                ✓ (published 23.6% ≈ 24% nominal canonical)

LP real = 23.6% × 0.7 × 0.95 × 0.93 = 14.595% ≈ 15%   ✓ (published 14.6% ≈ 15%)
```

Bull IRR check: $35B / $3.9B = 8.97× → 8.97^(1/5) - 1 = 55.1% ✓
Base IRR check: $15B / $3.9B = 3.85× → 3.85^(1/5) - 1 = 30.9% ≈ 31% ✓
Bear-A IRR check: $3B / $3.9B = 0.769× → 0.769^(1/5) - 1 = -5.1% ≈ -5% ✓
Bear-B IRR check: $0.5B / $3.9B = 0.128× → -33.7% ≈ -33% ✓

Entry range $3.6-4.2B → E[MOIC] range:
- @ $3.6B: 4.598 × 3.9/3.6 = 4.98× (published 5.0×)
- @ $4.2B: 4.598 × 3.9/4.2 = 4.27× (published 4.3×)
Published 4.3-5.0× ✓

### US-led probability 9 propagation points

| 位置 | 数值 | OK? |
|------|------|-----|
| §0.2 卡 L480 | "20-30%；中点 25%" | ✓ |
| §3.6 L992 | "中点 25%" | ✓ |
| §6.3 卡 L1786 ("US-led") | (题头, 无数字) | ✓ |
| §6.3 2×2 cells L1825-1827 | P(Y,Y)=12.5% + P(Y,N)=12.5% = 25% | ✓ |
| §6.3 limitation L1832 | "US-led 25%" SST | ✓ |
| §A.3.2 L2393-2394 | P=12.5% + P=12.5% = 25% | ✓ |
| §A.3.3 Q3 L2368 | "20-30%；中点 25%" | ✓ |
| chartScenarioProb L4556 | data: [35, 35, **25**, 5] | ✓ |
| data-confidence L4485 | "35/25/35/5" | ✓ |

2×2 内部一致性: P(Y,Y) + P(Y,N) + P(N,Y) + P(N,N) = 12.5 + 12.5 + 7.5 + 67.5 = 100% ✓
Marginal: P(Tesla Y) = 25%, P(Tesla N) = 75%; P(IRA Y) = 20% (= 12.5+7.5), P(IRA N) = 80% (= 12.5+67.5).
Reverse: P(Tesla Y)=0.25 × P(IRA|Y)=0.50 = 0.125 ✓; P(Tesla N)=0.75 × P(IRA|N)=0.10 = 0.075 ✓.
**Fully consistent.**

### 175× phantom EV IPO median

`grep -nF '175×' v4.report.html` → **0 hit** (was 4 hits in v3). Phantom removed.
Lucid +183% verify: (150-53)/53 = 1.8302 → +183% ✓

### chartPSRComparison source disclosure

L4935 Chart.js `title.text` now contains: `'Source: Figure 2024.02 $2.6B / [INFERRED] $13M 2024 营收 ...; 中系 2024 = 智元 $1.5B / ¥3.5亿 [INFERRED]; 2026E-2028E forward = 营收 ramp $50M / $200M / $500M 假设 + 50% YoY multiple compression'`. In-chart, reader-visible.

### 智元 WACC=21% source

L2039 footnote: "智元 base WACC=18% = Damodaran emerging-market China tech 14% + 港股流动性折扣 +200bp + 国资 IPO 时点 +200bp; 上限 21% = 18% + 额外 300bp (author's prior, not market-sourced)". ✓ sourced + sensitivity range explicit.

智元 lower cell $0.13B verify (g=2%, W=21%, EBIT=$43M):
df = 1/1.21^4 = 0.4665; V = 43 × 0.4665 × (1 + 1/0.19) = 43 × 0.4665 × 6.26 = $126M ≈ $0.13B ✓

---

## New issues (Round-4 introduced)

### Issue n4.i1 — moderate
**title**: §A.5 IC Memo intro L2644 漏 propagation — "PSR 20× ≈ EV IPO 中位 22%" 与 "简化 sanity check $0.15B" 是 round-3 残留

L2644 仍含 2 个 stale 数字: "EV IPO 中位 22%" (应为 24× per L2072 + 当前 SST) 和 "$0.15B" (应为 $0.17B per L2004/L2034/L2048). SST canonical 招牌下漏掉 IC Memo intro 这一处 propagation.

**What would resolve**: L2644 一处编辑, ~10 字符: "22%" → "24×"; "$0.15B" → "$0.17B".

### Issue n4.i2 — moderate
**title**: §6.5.1 footnote "unified WACC 16% / g=3%" 三公司锚 ($0.74 / $0.20 / $0.50B) 实际不共用同一 g

L2039 写 "统一 WACC 16% (中美对照): Figure $0.74B / 智元 $0.20B / 宇树 $0.50B". 复算 (g=3%, W=16%):
- Figure: $0.78B (published $0.74B, off 5%) — implied g≈2.15%
- 智元: $0.21B (published $0.20B ✓ rounded)
- 宇树: $0.46B (published $0.50B, off 9%) — implied g≈4.3%

三公司 unified anchor 用了不同 g, 实际并非严格 "fundamentals-only" (因为 g 是 fundamentals 之一). Ratio 3.7× / 1× / 2.5× 中 Figure/智元 一致 ✓, 但 宇树 2.5× 应是 2.19×. 27%/73% 主结论站得住 (取决于 ratio 减法), 但 reader 无法干净 reproduce 三个 anchor.

**What would resolve**: 重发 $0.78 / $0.21 / $0.46B (严格 g=3%/W=16%), 或显式承认 "三公司 perpetual growth 假设不同 (Figure 2.15% 美系成熟低增长 / 宇树 4.3% 中系硬件升周期)".

### Issue n4.i3 — moderate
**title**: 智元/宇树 简表 column header "WACC=21%" 只对智元 row 适用, 宇树 row $0.36B 实际用 W=18%

L2032 column "<th>下沿 (g=2%, WACC=21%)</th>" 跨 智元 (W=21% ✓ → $0.13B) + 宇树 (实际 W=18% → $0.36B). 复算 宇树 g=2%, W=21% 得 $0.28B 而非 $0.36B; $0.36B 对应 W=18%.

L2039 footnote 显式说 "宇树 上限不超 18%", 与表头矛盾. column 命名应 split.

**What would resolve**: column header 改 "下沿 (g=2%; WACC: 智元 21% / 宇树 18%)".

---

## Status of prior issues (Round-3)

| ID | Prior status | Round-4 status | Why |
|---|---|---|---|
| n3.i1 | severe | **resolved** | 3×3 9 cells full rebuild + 3 independent worked examples; 9 cell 全部独立复算 OK |
| n3.i2 | severe | **resolved** | US-led 25% canonical 9 处 propagation 全部 verified; 2×2 内部数学 100% 自洽 |
| n3.i3 | severe | **resolved** | SST: 23.6%/4.6×/14.6% canonical; 4 个 loci 全部统一; 5 个 round-3 数字 explicit deprecated |
| n3.i4 | moderate | **resolved** | 175× phantom 0 hit; Lucid 150× anchor 替代; Lucid +183% 重算 OK |
| n3.i5 | moderate | **resolved** | chartPSRComparison title.text in-chart source disclosure 落地 |
| n3.i6 | moderate | **resolved** | WACC=21% Damodaran + 国资 + author's prior 分解 explicit (但 unified-WACC anchor 不严格 same g — 新 n4.i2) |
| n3.i7 | moderate | **resolved** | 配合 r3-n1 SST, 全文 4 loci 同步 |
| n3.i8 | minor | **unresolved (deferred)** | builder explicit acknowledges round-5+ candidate; 不 cascade 到 SST, 不阻塞 |
| i14 R1 / n2.i5 | partial (R3) | **resolved** | 3×3 table 现在真实落地 + 9 cell 闭合 |

## Final score

verdict = pass
prior = 8R / 1P / 1U (n3.i8 deferred-and-accepted; counted as unresolved-but-not-blocking)
new = 0F + 0S + 3M + 0m

报告 v4 的数学整体性大幅提升: round-1 的 8 issues → round-2 的 10 issues → round-3 的 8 new issues + 11 partials → round-4 的 3 moderate residuals. SST 改造 fundamentally 改变了报告内部 cross-reference 结构, 任一未来 revision 现在有 single canonical cell 锚, 不再 prone to 多源 drift. 这是 round-4 的核心成就.
