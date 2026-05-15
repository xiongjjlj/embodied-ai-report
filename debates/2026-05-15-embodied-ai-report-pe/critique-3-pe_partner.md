# Round-3 PE Partner Critique

**Verdict**: `block` — 1 fatal + 3 severe + 3 moderate + 1 minor new; pe-n9 prior unresolved; 3 prior partial.

**One-line**: Phantom count dropped from 3 (round-2) to 1 (round-3), but the surviving phantom (US-led 中点 25% claim with unchanged card 20%) plus IC Memo Returns header inconsistency (4.4× header vs 4.8× formula, 29% header vs 26.1% formula) plus P95 label still applied to 35%-probability Bull case make this IC-grade still un-ratifiable.

---

## What changed in round-3 (verified by independent grep on v3.report.html)

| Round-2 fatal/severe | Status (grep-verified) | Evidence |
|---|---|---|
| pe-n1 Comps table 3 stale numbers | RESOLVED | L2065 Figure 1,750×; L2079 Symbotic 13×; L2069 EV median 24×; L2071-2074 Rivian/Lucid/Tesla 三 row |
| pe-n2 A.3.2 4-row if-then table phantom | RESOLVED | L2383-2397 actual table with 4 rows × 6 cols; L2468 Q2 cascade quantified |
| pe-n3 2×2 sums 110% | PARTIAL | sum=100% ✓ but US-led 卡片 20% vs derived 30% remains, claim "已上调中点至 25%" is new phantom |
| pe-n4 MOIC math 3.9 vs 4.83 | PARTIAL | formula explicit 4.8× ✓ but header writes 4.4×; E[IRR] header 29% vs formula 26.1%; 5 different IRR numbers in same paragraph |
| pe-n5 3×3 sensitivity absent | PARTIAL | table rendered ✓ but cell formula inconsistent (base $0.87B simple, off-diagonal $1.61B w/ ramp accumulator); footnote typo |
| pe-n6 Bear $3B mismatch | PARTIAL | Bear-A/B split done ✓ but Bear-B fair value uses 2-3× control premium (typical distressed = 1.3-1.5×); Bear-B / True Bear outcomes overlap |
| pe-n7 SoftBank stale | RESOLVED | L2742 demoted ⚠; L2747 Big Tech row with active 2024 deals |
| pe-n8 Distressed watchlist | RESOLVED | L2309-2335 A.2.1 subtable 10 rows × 5 cols, Tier-A/B split |
| pe-n9 P50/P95 percentile misuse | UNRESOLVED | terminology paragraph correct but row label still "Bull (P95 upside)" at 35% prob; Q9 row ① still uses P50/P95 as scenario names |
| pe-n10 v6/v7 internal notation | RESOLVED | L2001 clean formula, g=3% rationale added |
| pe-n11 5 vs 6 PE actions | RESOLVED | L506 §0.3 "6 个"; L2399 A.3.3 reconciled |

Net: 6 resolved, 4 partial, 1 unresolved out of 11. Material progress vs round-2 (which was 0 resolved on 2 fatal). But the **biggest fatal (pe-n4 IC Memo math)** is only partially fixed — the formula is now in the cell but the header still disagrees.

---

## NEW Round-3 Issues (introduced by phantom-killing pass)

### r3-n1 [fatal] · IC Memo Returns 表 header 与公式三处算术冲突

Cell L2688 row "E[MOIC]" header = **~4.4×** but same cell formula explicit:
`0.35×9.0 + 0.40×3.8 + 0.10×0.77 + 0.10×0.13 + 0.05×0.12 = 4.766 ≈ 4.8×`

Header **4.4×**, formula **4.8×**. Difference 9%. (4.4 is the lower end at entry $4.2B; mid $3.9B basis gives 4.8.) Header is not "mid" of any computed value.

E[IRR] same: header **~29% 名义**, cell formula `0.35×55 + 0.40×31 + 0.10×(-5) + 0.10×(-33) + 0.05×(-35) = 26.1%`. Bottom paragraph (L2691) then offers `27.3%, 24.6%, 26.1%, 取整 ~28%` — **5 different IRR numbers** for the same expected value: 24.6 / 26.1 / 27.3 / 28 / 29. Header 29% is invented, not derived.

Truly-distributable LP IRR ~17% is supposed to be `E[IRR] × 0.7 × 0.95 × 0.93`:
- Using header 29% → 17.9% ✓ (only consistent if you start with 29%)
- Using formula 26.1% → 16.1%
- Using bottom 28% (取整) → 17.3%
- Using detail 26.1% → 16.1%

So **17% reverse-fits the invented 29% header, not the formula**. PE IC sees Returns table header first; this is the load-bearing cell of the entire deal recommendation. Cannot ship.

**To resolve**: header = `~4.8× (mid)` matching formula; E[IRR] = `~26%` (pick 5-row detail OR 4-row simple, not three numbers); recompute real LP IRR = 16.1%. Drop the "取整 ~28%" alt path.

### r3-n2 [severe] · §6.3 limitation-note 声称 "US-led 中点已上调至 25%" 是 within-round-3 phantom

§6.3 2×2 matrix limitation-note (L1831): *"mapping 到 named scenarios: US-led 30% (= 15% + 15%, 与卡片 15-25% 区间上沿一致; **已上调中点至 25%**, 见下)"*.

But independent grep:
- L1783 US-led card: `15-25%` (unchanged)
- L480 §0.2 enumeration: `US-led（15-25%；中点 20%）` (unchanged)
- L992 executive summary: `US-led 概率 15-25%` (unchanged)
- L2691 IC Memo Bear-A+B split: `§6.3 US-led 20% = §A.5 Bear-A 10% + Bear-B 10%` (uses 20%, NOT 30%)

"已上调中点至 25%" is a within-round-3 phantom — the note says the card was upgraded but the card was not. Round-3 set out to kill phantoms; this is a new one. Worse: US-led now appears as **20% in the card + IC Memo, 25% in the note, 30% in the 2×2 derive**. Three different probabilities for the same scenario.

**To resolve**: Pick one number (20 or 25 or 30) and propagate to L480 / L992 / L1783 / L2691 + IC Memo concentration weighting. If 25/30 is correct, Base + Bull + Bear-A/B + True Bear concentrations must re-sum to 100%.

### r3-n3 [severe] · P5/P50/P95 定义统一 但 row label 与定义直接矛盾

L2691 added correct percentile definitions: P95 = 95th percentile (upper 5% tail), P50 = median, P5 = lower 5% tail. But L2682 row label unchanged: **"Bull (P95 upside, China-led) — 35%"**.

A 35%-probability scenario cannot be the 95th percentile. The terminology paragraph and the row label contradict each other. round-2 pe-n9 attack ("percentile misused as scenario name") survives — round-3 added a definition but did not relabel the rows. Q9 L2589 row ① still uses "P50 / P95" as Base/Bull scenario names.

This is **cosmetic** rather than substantive: the writer paid the cost of writing a correct definition, then failed to act on it.

**To resolve**: Rename rows `Bull (35% scenario probability)`, `Base (40%)`, `Bear-A (10%)`, `Bear-B (10%)`, `True Bear (5%)`. Either drop P5/P50/P95 entirely OR add a separate "Distribution percentile summary" table showing real CDF inversions.

### r3-n4 [severe] · 3×3 sensitivity 表 cell 公式 mixed methodology

L2017-2020 cell values:
- g=3%, WACC=15% (base): **$0.87B**
- g=3%, WACC=12%: **$1.61B**
- g=4%, WACC=12%: **$1.93B**

Formula (L2023): `EBIT × [df_4yr + 1/(WACC-g) × df_4yr]`.

Independent computation:
- base: $163M × [0.5718 + 0.5718/0.12] = $163M × 5.337 = **$0.87B** ✓
- g=3%/W=12%: $163M × [0.6355 + 0.6355/0.09] = $163M × 7.697 = **$1.26B** ❌ (table says $1.61B)

footnote self-admits: *"$1.255B → 加 4-yr 折现 cash flow accumulator 后 ~$1.61B (含 ramp 期 cash 简化为 EBIT×4×0.5×df)"*. So off-diagonal cells add a ramp accumulator term; base cell does not. **One formula, 9 cells, two methodologies.**

Also footnote typo: `$1.40B (W=12%/g=4%) — $1.93B (W=12%/g=4%, w/ accumulator)` — both labeled g=4% but $1.40B is actually g=2% per the table grid.

**To resolve**: Pick one methodology (with-or-without ramp), recompute all 9 cells uniformly, fix typo (g=2% not g=4%).

### r3-n5 [moderate] · Bear-B fair value 公式反直觉; Bear-B / True Bear outcome 重叠

Bear-B exit `$0.5B (= $0.17B sanity × 2-3× control premium + IP 残值)`.

PE M&A control premium typical: 1.3-1.5× (healthy targets). Distressed M&A typically priced **at or below** standalone DCF (no premium, sometimes a fire-sale discount). 2-3× control premium on a distressed company is reverse of typical M&A experience.

Recomputing with typical 1.3-1.5× premium: $0.17B × 1.4 = $0.24B fair value, MOIC = 0.062×. That's very close to True Bear (mid 0.12×). Bear-B (10%, MOIC 0.13×) and True Bear (5%, MOIC 0.12×) outcomes already overlap with the inflated 2-3× premium; with correct premium they collapse into one row.

**To resolve**: Either (a) accept distressed = 1.3-1.5× premium → recompute Bear-B = $0.24B, MOIC 0.06×, and merge with True Bear into a single "Bear-B 15% prob, exit $0.2-0.5B, MOIC 0.05-0.13×"; (b) keep 2-3× but cite a comparable distressed-M&A precedent justifying premium-over-DCF.

### r3-n6 [moderate] · A.6.2 标题 "5 家" 与表内 6 行 不一致

L2740 title: "A.6.2 · **5 家**潜在 Strategic Acquirer". Table has 6 rows: NVIDIA / SoftBank / Big Tech (new) / 比亚迪+吉利+上汽 / 美的+海尔 / Hyundai+Samsung+LG. L2482 Q3 reply still references "并购买家清单 5 家".

**To resolve**: Title → "6 家潜在", L2482 → "6 家". One-line edits.

### r3-n7 [moderate] · §6.3 cell (N,N) 63% 拆为 China-led 35% + Bifurcation 主干 28% — 2×2 cannot identify

The 2×2 matrix Tesla×IRA only spans 4 cells. China-led and Bifurcation main both live in cell (N,N) — they are **indistinguishable** in this 2D matrix. Splitting 63% → 35% China-led + 28% Bifurcation main is a downstream prior, not a derivation from the 2×2.

Either (a) introduce a third dimension (e.g., China policy fast/slow) to make 2×2×2 = 8 cells where the split becomes identifiable; (b) explicitly note "cell (N,N) is a joint event; partition into China-led / Bifurcation is author's downstream prior, not implied by 2×2".

### r3-n8 [minor] · Comps table 板块 1b footnote 算术毛糙

L2076 footnote A:
- `N=5 median = sorted [15, 24, 53, 150, 85000] 中位 53×` ✓
- But row "板块 1b" rowspan cell writes `53× (N=5 median; (24+53)/2 alt: 见 footnote)` — `(24+53)/2 = 38.5` is N=2 median, not relevant. Confusing.
- "溢价" column: Rivian +254%, Lucid +254%. Vs 53× median: Rivian = 85,000/53 = 1604× = +160,277%; Lucid = 150/53 - 1 = +183%. Neither is +254%. Numbers fabricated.
- Tesla 2010 row sits inside 板块 1b but footnote says Tesla excluded from median — should be separate "reference" sub-row.

**To resolve**: Strip the `(24+53)/2 alt` term, recompute 溢价 column for Rivian/Lucid against correct median, mark Tesla 2010 as standalone reference outside 板块 1b.

---

## Severity tally

- Fatal: **1** (r3-n1 — IC Memo header math)
- Severe: **3** (r3-n2 US-led phantom, r3-n3 P95 label, r3-n4 3×3 methodology)
- Moderate: **3** (r3-n5 Bear-B premium, r3-n6 5-vs-6 count, r3-n7 over-decomposition)
- Minor: **1** (r3-n8 footnote arithmetic)
- Prior unresolved: pe-n9 (= r3-n3 same root cause)
- Prior partial: pe-n3 / pe-n4 / pe-n5 / pe-n6 (root cause folded into r3-n1, r3-n2, r3-n4, r3-n5)

**Pass requires 0 fatal + 0 severe**. Currently 1 fatal + 3 severe. **Block.**

---

## What's actually good about round-3 (calibration)

Round-3 is materially better than round-2 in mechanical fidelity: 6 of 11 round-2 issues fully resolved with grep-verifiable evidence (vs round-2's 0 of 2 fatal resolved). The Comps table, A.3.2 if-then matrix, A.2.1 distressed watchlist, and Big Tech acquirer row are all real edits with substance. The phantom-fix critique from round-2 was heard and largely actioned.

The remaining issues cluster around **internal consistency** rather than missing content: header vs formula mismatch, terminology vs row labels mismatch, narrative claim ("中点已上调") vs unchanged card mismatch. These are easier to fix than round-2 issues but they break the same trust contract (the IC reader must be able to trust that load-bearing cells reflect the math underneath).

One more pass focused on `header ↔ formula ↔ card ↔ narrative` 全文 reconciliation should land verdict=pass.
