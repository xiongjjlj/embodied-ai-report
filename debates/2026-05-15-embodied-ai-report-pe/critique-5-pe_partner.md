# Round-5 critique · pe_partner

## Verdict: **PASS** (0 fatal + 0 severe; 1 minor new + 1 partial-prior immaterial)

r4-n1 (Bull row capture conflation, severe) genuinely resolved via Choice A full revision. r4-n2/r4-n3 also fully resolved. Two minor items (r4-n4 channel breakdown, r4-n5 P(N,N) split) accepted as documented carry-forward, immaterial to bottom line. One minor new issue (r5-n1, ensemble math under-derived) not block-worthy.

---

## What this draft is trying to do

PE/VC IC 决策辅助报告 (Round-5). 圈定 智元机器人 Pre-IPO follow-on $20-30M 跟投决策, 给 IC partners full 5-yr Returns + risk register + exit path methodology, 通过 5 scenario × P(capture) probability factoring 给 E[MOIC] / E[IRR] capture-adjusted canonical.

---

## Load-bearing claims (Round-5 mutation)

1. (LBC-1) 中国具身产业 5-yr 内成为 dominant exporter 或与美 dual-track 平行 (≥ 70% 综合概率, China-led 35% + Bifurcation 35%).
2. (LBC-2) 智元 Pre-IPO entry $3.9B post-money, 5-yr exit base case $15B Bifurcation / $35B China-led ceiling.
3. (LBC-3) 5 macro scenario (35/35/12.5/12.5/5) → P(capture|scenario) prior 0.4-0.6 → E[MOIC] capture-adjusted ~2.55× mid (range 2.0-3.0×), E[IRR] ~21% nominal mid (range 16-24%), LP real ~13% mid (range 10-15%).
4. (LBC-4) 旧 SST canonical 4.6×/24%/15% 现重定义为 "Bull-takes-all ceiling" (假设 P(capture)=1), 不是 expectation.
5. (LBC-5) IC recommendation CONDITIONAL PROCEED $20-30M 即便 LP real 13% 已接近 sub-25% PE growth target 下沿 — 通过 5 个 condition (ratchet + yield audit + DD access + vesting + co-investor info share) 锁定 downside.

---

## Status of prior issues

| Prior | Severity | Status | Note |
|---|---|---|---|
| r4-n1 Bull row capture conflation | severe | **RESOLVED** | Choice A full revision; P(capture) column 添加; 5 row 都填 prior (China-led/Bifurcation 0.5 mid, US-led 0.6 mid, True Bear 1.0); E[MOIC] 2.55× mid; 9-place SST cascade verified; 数学独立 spot-check 全 ✓; 旧 4.6× explicit "Bull-takes-all ceiling DEPRECATED" |
| r4-n2 Q9 P50/P95 与 r3-n3 段落矛盾 | moderate | **RESOLVED** | L2593-2595 3 line item 全部 named-scenario; "Round-5 r4-n2" tag |
| r4-n3 Bull trigger 5万 vs 100万 mismatch | moderate | **RESOLVED** | Via r4-n1 cascade; Bull row trigger 加 "AND 智元 dominant 中国 winner"; 5% nominal share 现 priced as P(capture)=0.5 |
| r4-n4 Channel breakdown 31% vs 21% portfolio anchor | minor | **PARTIAL** | L2769 caveat surface 充分, 但 channel-level 5-row matrix 用 21% 没 duplicate (cosmetic). Accepted carry-forward |
| r4-n5 P(N,N) split prior 27.5%/7.5% | minor | **ACCEPTED + DOCUMENTED** | L1832 不变; r4-n1 让 35% macro 不再 load-bearing, split 灵敏度 ↓ 50% |
| pe-n9 / r3-n3 (P50/P95 on Q9) | residual minor | **RESOLVED** | Via r4-n2 一并 swept |

---

## Independent math spot-check (r4-n1 resolution verification)

Direct recomputation of E[MOIC] formula at L2691 (P=0.5 mid):

```
Bull:      0.35 × 0.5 × 9.0  + 0.35 × 0.5 × 0.5 = 1.575  + 0.0875 = 1.6625
Base:      0.35 × 0.5 × 3.8  + 0.35 × 0.5 × 0.5 = 0.665  + 0.0875 = 0.7525
Bear-A:    0.125 × 0.6 × 0.77 + 0.125 × 0.4 × 0.5 = 0.0578 + 0.025  = 0.0828
Bear-B:    0.125 × 0.6 × 0.13 + 0.125 × 0.4 × 0.5 = 0.0098 + 0.025  = 0.0348
True Bear: 0.05  × 1.0 × 0.12 = 0.006
———————
Total: 1.6625 + 0.7525 + 0.0828 + 0.0348 + 0.006 = 2.5386 ≈ 2.54× ✓
```

IRR back-out: 2.54^(1/5) − 1 = 20.5% ≈ 21% nominal ✓
LP real: 20.5% × 0.7 × 0.95 × 0.93 = 12.7% ≈ 13% ✓

At P=0.4: 2.13× ✓ (matches published)
At P=0.6: 2.95× ✓ (matches published)

数学 fully closes; 反向 spot-check 全 ✓.

---

## SST cascade verification (9 sites)

| Site | Line | Content | Status |
|---|---|---|---|
| §7 header | L2678 | "E[MOIC \| capture=1] 4.6× ceiling; capture-adjusted ~2.0-3.0× (mid 2.55×); E[IRR] ceiling 24% / adjusted 21%; LP real ceiling 15% / adjusted 13%" | ✓ |
| Table caption | L2681 | 加 "新增 P(智元 captures\|scenario) 列 — 7-way Chinese-pole 竞争" | ✓ |
| Column header | L2682 | "P(智元 captures\|scenario)" 列新增 | ✓ |
| Bull row | L2686 | 35% macro + P(capture) 0.4-0.6 mid 0.5 + trigger 加 "AND 智元 dominant 中国 winner" + Exit "$35B (conditional)" | ✓ |
| Base row | L2687 | 35% macro + P(capture) 0.4-0.6 + trigger "AND 智元 mid-pack 兑现" | ✓ |
| Bear-A | L2688 | 12.5% macro + P(capture) 0.5-0.7 | ✓ |
| Bear-B | L2689 | 12.5% macro + P(capture) 0.5-0.7 | ✓ |
| True Bear | L2690 | 5% macro + P(capture) 1.0 (already conditional on 智元 failure) | ✓ |
| E[MOIC] summary | L2691 | 2.55× mid (range 2.0-3.0×) + 旧 4.6× "Bull-takes-all ceiling DEPRECATED 标 r4-n1" + 公式 + 5 row 算式列出 + range P=0.4/0.6 | ✓ |
| SST footnote | L2696 | Category-conflation 解释 + 7-way 竞争 + capture prior derivation + 旧 4.6× DEPRECATED 但 retained as ceiling + 报告内任何 MOIC/IRR 回指此 cell | ✓ |
| §A.6.3 paragraph | L2762 | "Round-4 ceiling 23.6% DEPRECATED; capture-adjusted E[IRR] 21% canonical" | ✓ |
| §A.6.3 bullet | L2767 | "capture-adjusted nominal E[IRR] = ~21%; portfolio real = 20.6%×0.7×0.95×0.93 = ~13% real" | ✓ |
| §A.6.3 caveat | L2769 | "31% conditional vs 21% nominal portfolio; capture-adjusted Base contribution = 0.35×0.5×31% ≈ 5.4% mid" | ✓ |

§0.1 / chartScenarioProb / data-confidence 不需要更新 — 这些位置只承载 macro probabilities (35/25/35/5), 不承载 MOIC/IRR canonical, 与 r4-n1 capture factoring 正交.

---

## New issue (minor)

### 1. [minor] r5-n1 · SST footnote ensemble alternative recommendation ("3-stock 智元+宇树+银河通用 → E[MOIC] 回 3.5-4.2×") 数学 under-derived

**Attacks**: SST footnote L2696 末句 alternative IC action.

**Detail**: L2696 末句 "alternative IC action: 同时 fund 智元 + 宇树 + 银河通用 (3-stock ensemble) 让 capture probability → ~0.85-0.95, E[MOIC] 回到 3.5-4.2× 中位 (但占用基金 ~3× 单笔限额, 需 LP 加注)". ensemble capture prob 0.85-0.95 隐含 independent assumption: 1 - (1-0.5)^3 = 0.875. 但 7-way 竞争中 3 家 capture event **不独立** (同一 macro scenario 下 winner 互斥, 至多 1 家 dominant). 严格 ceiling: P(任一 wins | scenario) ≤ Σ P_i ≤ 1, 实际接近 P(智元 wins) + P(宇树 wins) + P(银河通用 wins) where these probabilities sum to *much less than 1* due to mutual exclusion. 银河通用 funding 远低于宇树/智元 (Series B $3B vs 宇树/智元 Pre-IPO $5.6B/$2.8B), prior 应 < 0.3, ensemble 真实 capture prob ≈ 0.5 (智元) + 0.5 (宇树) - 0.25 (overlap) + 0.2 (银河) - small overlap ≈ 0.85-0.9 上限, 而非 0.95. 数字 directionally 接近但 derivation 没给; LP/IC 会问 "ensemble 怎么算的". 同时 3-stock 占用基金 ~3× 单笔限额 (3 × $20-30M = $60-90M), 基金 3% 上限被打破; footnote surface 了 "LP 加注" 但没量化 ensemble 真实 dilution effect on per-LP-dollar IRR.

**Why minor (not severe)**: ensemble 是 alternative action / reviewer optional, 不是 base recommendation. CONDITIONAL PROCEED $20-30M 单笔 base 不变. footnote 措辞 "Reviewer 可调" 已 explicit framing. cosmetic.

**What would resolve**: (a) ensemble capture math 公式给出 (e.g. 1 - Π(1 - P_i / k) where k = winner 互斥 correction), 明示 simplification 假设; (b) 银河通用 capture prior < 0.3 显式; (c) LP per-dollar IRR 加注后稀释量化 (3× allocation → IRR uplift +50% 不是 +60% due to fund concentration risk premium discount); (d) 或简单加 disclaimer "ensemble 估算用 independence 简化, 真实有 mutual-exclusion correlation, 实际 ensemble 效益 ≤ formula".

---

## Why this passes

The Round-5 revision is a **structural** fix, not cosmetic. The previous SST treated macro scenario probability as if it were the joint probability of (macro scenario AND 智元 = winner of that scenario), which inflated E[MOIC] by ~80%. Round-5 separates these two probability spaces explicitly, gives reviewers a tunable P(capture) prior, retains the old ceiling for traceability (rather than memory-holing it), and propagates the new anchor through all 9 cascade sites consistently. Math closes on independent recomputation.

The capture-adjusted E[MOIC] 2.55× / LP real 13% is admittedly thin for a PE growth fund (typical hurdle 20-25% IRR), but the IC Memo `CONDITIONAL PROCEED $20-30M` recommendation now sits on calibrated economics — and the report surfaces the ensemble alternative with appropriate caveats. The Builder did not pretend the number stayed at 4.6×; the Builder accepted the real economics. That's the discipline the prior critique demanded.

Remaining minor (r4-n4 channel cross-section, r4-n5 N,N split, r5-n1 ensemble math) are all immaterial to bottom-line decision and explicitly listed as round-6 carry-forward. Not block-worthy.

---

## Files

- `/Users/feixiong/Desktop/ClaudeCode/embodied-ai-report/debates/2026-05-15-embodied-ai-report-pe/critique-5-pe_partner.json`
- `/Users/feixiong/Desktop/ClaudeCode/embodied-ai-report/debates/2026-05-15-embodied-ai-report-pe/critique-5-pe_partner.md`
