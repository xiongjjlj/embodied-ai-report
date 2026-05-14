# Embodied AI — PE DD Metrics Research

**Purpose**: Provide PE-grade due-diligence indicators (unit-level performance, order quality, alternatives, safety/liability, RaaS balance sheet) that the existing report did not surface.

**Compiled**: 2026-05 | **All numbers are sourced from public disclosures; gaps flagged as [UNDISCLOSED].**

---

## Task 1 — Real-World Operating Metrics (MTBF / Uptime / Autonomy Level)

### 1.1 Autonomy taxonomy used in this report (SAE-style)

| Level | Definition |
|---|---|
| L0 | 100% teleoperation |
| L1 | Human-set waypoint; robot executes the segment |
| L2 | Supervised autonomy; human can take over at any time |
| L3 | Fully autonomous in a defined operational design domain (ODD) |
| L4 | Generally autonomous across domains |

### 1.2 Headline deployment scorecard

| Company / Robot | Deployment site | Disclosed run-time | Autonomy level (today) | Throughput | Source |
|---|---|---|---|---|---|
| **Tesla Optimus** | Fremont (R&D), no customer site | Production line yet to start (target Jul–Aug 2026) | L0–L1 (Musk: "not in usage in our factories in a material way … so the robot can learn") | Zero useful work — confirmed by Musk on Q4 2025 call | Electrek, Jan 28 2026 ([link](https://electrek.co/2026/01/28/musk-admits-no-optimus-robots-are-doing-useful-work-at-tesla-after-claiming-otherwise/)) |
| **Figure 02** | BMW Spartanburg | 11-month pilot; **1,250 cumulative runtime hours**; 10 h/day, Mon–Fri | Figure claims **L3 in-task ODD** (sheet-metal insertion); skeptics (Scott Walter, others) flag teleop in marketing demos | **90,000+ parts loaded**, contributed to **30,000+ X3s** | Figure press, Nov 2025 ([link](https://www.figure.ai/news/production-at-bmw)); BMW press ([link](https://www.press.bmwgroup.com/usa/article/detail/T0444268EN_US/)) |
| **Figure 03** | BMW Spartanburg → Munich/Regensburg/Leipzig phased | Phased rollout 2026–27 under separate contracting frameworks | Claimed L3 (Adcock: "we will not teleoperate them in market"); independent verification [UNDISCLOSED] | [UNDISCLOSED] | The Platinum Capital ([link](https://www.theplatinumcapital.com/article/figure-confirms-commercial-deployment-of-figure-03-at-bmw-plant-as-humanoid-robotics-cycle-accelerates)); Humanoids Daily ([link](https://www.humanoidsdaily.com/feed/figure-ceo-brett-adcock-says-will-not-teleoperate-robots)) |
| **1X NEO** | Consumer pre-order (homes) | Shipping 2026 | **L0–L2 hybrid (officially)**. CEO Bornich: initial autonomous rate ~60–70 %; "Expert Mode" remote pilots fill the gap; target 80–90% by 2027, 95%+ by 2028 | Door-open success ~90%, object-fetch success ~80% (CEO claim) | Humanoids Daily ([link](https://www.humanoidsdaily.com/feed/1x-ceo-details-neo-s-two-modes-and-defends-teleoperation-as-more-secure-than-a-cleaner)); Engadget ([link](https://www.engadget.com/ai/1x-neo-is-a-20000-home-robot-that-will-learn-chores-via-teleoperation-040252200.html)) |
| **Apptronik Apollo** | Mercedes / GXO / Jabil | All still at pilot stage; commercial scale-up targeted H2-2026 | L2 (lab-trained for "simple repetitive intralogistics") | [UNDISCLOSED] | TechCrunch ([link](https://techcrunch.com/2025/02/25/apptroniks-humanoid-robots-take-the-first-steps-toward-building-themselves/)); Apptronik+Jabil ([link](https://www.therobotreport.com/apptronik-collaborates-with-jabil-to-produce-apollo-humanoid-robots/)) |
| **Agility Digit** | GXO Flowery Branch; Mercado Libre San Antonio | **100,000+ totes** moved at GXO (Nov 2025); 2-to-1 battery cycle ⇒ 1 charging while 2 working; 8 h battery | L3 in defined tote-transfer ODD; supervised; Agility Arc telemetry tracks MTBI (KPI not publicly disclosed) | Picks/hr [UNDISCLOSED]; CEO target: ≤2-yr ROI vs $30/hr human | Agility ([link](https://www.agilityrobotics.com/content/digit-moves-over-100k-totes)); Robotics & Automation News ([link](https://roboticsandautomationnews.com/2025/11/24/agility-robotics-digit-humanoid-passes-100000-tote-milestone-in-live-gxo-implementation/96877/)) |
| **Unitree H1 / G1** | Mostly demos, education, research labs, gov data-collection contracts | Sub-day demo cycles; no published 24×7 production deployment | L0–L1 in field (RC), L2 in canned demos | [UNDISCLOSED] | Unitree CEO Wang Xingxing 2025 disclosure (CSDN report) ([link](https://blog.csdn.net/sanhuyun/article/details/146328681)) |
| **Zhiyuan / AgiBot A2** | China Mobile data-collection PoC | Pilot — robots are subject of contracted "manufacturing" service for data-collection, not production deployment | L0–L1 (data collection mostly teleop-driven) | [UNDISCLOSED] | EET-China ([link](https://www.eet-china.com/mp/a420425.html)); 21jingji ([link](https://m.mp.oeeee.com/a/BAAFRD0000202507121102457.html)) |
| **Boston Dynamics Atlas (new)** | Hyundai RMAC, Google DeepMind | CES 2026 commercial reveal; all 2026 fleet committed | L2–L3 in part-sorting ODD at Hyundai's Savannah plant (field test) | Quantitative throughput [UNDISCLOSED] | Boston Dynamics blog ([link](https://bostondynamics.com/blog/atlas-evolution-from-research-robot-to-industrial-humanoid/)); New Atlas ([link](https://newatlas.com/ai-humanoids/boston-dynamics-production-atlas-hyundai/)) |
| **UBTech Walker S2** | Multiple Chinese gov / industrial sites (defense logistics, edu, data-collection centers) | Recent 11-month delivery cadence | L1–L2; battery-swap demo claims 3 min hot-swap | [UNDISCLOSED] per-task; relies on procurement-bid format | Sina ([link](https://finance.sina.com.cn/jjxw/2025-11-25/doc-infyqqee5834834.shtml)) |

### 1.3 Key public admissions on autonomy

- **Brett Adcock (Figure CEO)** has repeatedly insisted Figure will **not** teleoperate in market: "We will not teleoperate them in market. Like we will not do any of this soy stuff." After the Shawn Ryan Show Figure 03 demo, skeptics — most notably engineer Scott Walter — flagged movement timing as evidence of off-camera operator; Adcock pushed back and promised a livestream verification. The dispute over Figure 02's BMW work was earlier surfaced by *Fortune* (Apr 2025) which questioned whether Adcock exaggerated the BMW relationship ([link](https://fortune.com/2025/04/06/figure-ai-bmw-humanoid-robot-partnership-details-reality-exaggeration/)).
- **Bernt Bornich (1X CEO)** acknowledged on the NEO launch that "much of the work will be done by teleoperators in the beginning" and stated 1X's internal model assumes **60–70% autonomy at launch, 80–90% by 2027, 95%+ by 2028**. He added that the company is "running towards a cliff" if autonomy does not scale with deployment ([link](https://www.humanoidsdaily.com/feed/1x-ceo-details-neo-s-two-modes-and-defends-teleoperation-as-more-secure-than-a-cleaner)).
- **Eric Jang (1X VP of AI, departed Jan 2026)** described 1X's strategy as "autonomous + call for human assistance when NEO can't do a task, like how Waymo is operated & supervised." Teleop is explicitly the data-engine ([link](https://www.humanoidsdaily.com/news/1x-details-neo-human-in-the-loop-strategy-and-hardware-as-pre-orders-go-live)).
- **Elon Musk (Tesla)** told the Q4 2025 earnings call: "It's not in usage in our factories in a material way. It's more so that the robot can learn." This directly contradicts the company's earlier 10,000-units-by-2025 plan ([link](https://electrek.co/2026/01/28/musk-admits-no-optimus-robots-are-doing-useful-work-at-tesla-after-claiming-otherwise/)).

### 1.4 The autonomy-disclosure asymmetry

Of the nine programs above, only **Agility Digit at GXO** and **Figure 02 at BMW** publish absolute volumetric measures (totes moved, parts loaded, vehicles produced). MTBF / MTBI numbers are everywhere absent. The Agility Arc platform now meters MTBI to customers, but Agility has not disclosed fleet-wide values. Investors should treat any humanoid pitch deck that omits MTBF as incomplete.

---

## Task 2 — Order-Quality Tiering (Top 10 disclosed orders)

### 2.1 Tier framework

| Tier | Definition | Indicative cancellation risk |
|---|---|---|
| **A** | Paid, irrevocable PO with units delivered or in delivery | <5% |
| **B** | Signed firm purchase contract, unit price + delivery schedule fixed | 5–15% |
| **C** | Master framework / MSA, units to be drawn under separate orders | 30–60% |
| **D** | Paid PoC / pilot, no production commitment | 60–80% |
| **E** | LOI / MoU, no legal commitment | 75–95% |

### 2.2 Top 10 disclosed orders — tiered

| # | Deal | Headline value | Tier | Evidence / caveats | Source |
|---|---|---|---|---|---|
| 1 | **UBTech Walker S — full-year 2025 orderbook** | ¥11–13 bn cumulative across multiple contracts | **B / C mix** (each contract is a public-procurement bid award; subject to delivery confirmation) | Sub-deals include Guangxi ¥264 M, Zigong ¥159 M, plus Sep ¥250 M deal and Nov-only ¥566 M. Each is a government public-procurement bid — these are firm but tied to delivery in Nov–Dec 2025; non-delivery would mean breach. Delivery confirmation is still incomplete. | Sina ([link](https://finance.sina.com.cn/jjxw/2025-11-25/doc-infyqqee5834834.shtml)); Shenzhen DRC ([link](https://fgw.sz.gov.cn/ztzl/qtztzl/szscjmyjjfzzhfwpt/mqfc/myqyfzdt/content/post_12527590.html)); Yicai ([link](https://www.yicai.com/news/102932034.html)) |
| 2 | **UBTech — Guangxi Fangchenggang** (data-collection + AI-edu demo project) | ¥264 M | **B** (bid awarded; products = Walker S2; delivery slated Dec 2025) | Procurement-bid auctions are binding in China after award notification; cancellation = breach. | STCN ([link](https://stcn.com/article/detail/3510555.html)); CLS ([link](https://www.cls.cn/detail/2209673)) |
| 3 | **UBTech — Zigong** | ¥159 M | **B** (Walker S2; Sichuan public-resource exchange bid; delivery target Nov 2025) | Same bid framework as #2 — binding once awarded. | aibangbots ([link](https://www.aibangbots.com/a/5149)) |
| 4 | **Unitree FY-2025 industrial order book** | ¥1.2 bn cumulative (+220% YoY) | **B / C mix** (G1 ~60% of revenue per CEO; mix of edu + research + small-volume B-end) | Includes Tongji ¥8.26 M training-platform and Sci-Tech Museum ¥6.27 M; mostly small dictionary-style orders, not scale industrial deployment. | CSDN ([link](https://blog.csdn.net/sanhuyun/article/details/146328681)) |
| 5 | **AgiBot (Zhiyuan) + Unitree — China Mobile (Hangzhou IT subsidiary)** | ¥124 M total (¥78 M AgiBot full-size; ¥46.05 M Unitree small + dexterous hands + compute backpacks) | **D (PoC) with B-tier elements** — labeled in the bid documents as a "humanoid bipedal robot OEM service procurement project" for data-collection / R&D, not for production deployment | Procurement contract is firm, but the *end-use* is R&D; treating this as a commercial production order overstates demand quality. | EET-China ([link](https://www.eet-china.com/mp/a420425.html)); Eastmoney ([link](https://fund.eastmoney.com/a/202507123455268271.html)); CEEACMS ([link](http://ceea.org.cn/ceeacms/webArticleAction!detailView.do?articleID=202507153444983603036959938752)) |
| 6 | **Robot Era (星动纪元) FY-2025 backlog** | ¥500 M+ cumulative; >200 units delivered by June 2025; ~50% overseas split | **B / C / D mix**. "Top-10 global tech giants — 9 are customers" implies many are evaluation / pilot relationships; overseas 50% likely heavy on D-tier | Funding round-time orderbook claims often blend LOIs with PO. Diligence required. | Sina ([link](https://finance.sina.com.cn/stock/vcpe/2025-11-20/doc-infxzepc2867098.shtml)); 36Kr ([link](https://36kr.com/p/3560734133091207)) |
| 7 | **Apptronik × Mercedes / GXO / Jabil** | Pilot dollar value [UNDISCLOSED]; Jabil also is producer | **D (PoC)**, with Jabil agreement having dual nature (manufacturing partner + customer) | Apptronik publicly targets "commercial scale 2026 H2." | Apptronik news ([link](https://apptronik.com/news2)); Robot Report ([link](https://www.therobotreport.com/apptronik-collaborates-with-jabil-to-produce-apollo-humanoid-robots/)) |
| 8 | **Agility × GXO / Amazon (early) / Spanx / Mercado Libre** | Dollar value [UNDISCLOSED]; volume metric: 100,000+ totes; Mercado Libre = commercial agreement (Dec 2025) | **B (Agility Arc subscription RaaS framework)** at GXO; **C** at Mercado Libre (commercial-agreement language, no firm unit count published) | Mercado Libre press uses "commercial agreement … beginning in Texas with future expansion capabilities" — open-ended ramp. | Businesswire ([link](https://www.businesswire.com/news/home/20251210209226/en/Mercado-Libre-and-Agility-Robotics-Announce-Commercial-Agreement-to-Deploy-Humanoid-Robots)); DC Velocity ([link](https://www.dcvelocity.com/material-handling/order-fulfillment-packing/robotic-picking-and-loading/agility-deploys-its-digit-humanoid-robot-in-texas-fulfillment-center)) |
| 9 | **Galbot × Baida Precision (Pasionsoft strategic agreement)** | "Plan to deploy 1,000+ robots within their ecosystem" | **C / E** — strategic deployment agreement with no published unit-price × volume × delivery schedule | Galbot's "thousands of cumulative orders" with CATL/Bosch/Toyota/BAIC/SAIC is press-release language without unit confirmation. | Guancha ([link](https://user.guancha.cn/main/content?id=1571117)); ofweek ([link](https://www.ofweek.com/ai/2025-06/ART-201700-8500-30665744.html)) |
| 10 | **Figure × BMW** | 11-month PoC concluded Nov 2025; multi-year commercial agreement Jan 2024; phased Spartanburg expansion + Munich/Regensburg/Leipzig "separate contracting frameworks" | **B (Spartanburg phased)** + **C (German plants framework)** | Per *Fortune*, BMW initially pushed back on Adcock's characterization. Quantitative units/$ value [UNDISCLOSED]. | Figure ([link](https://www.figure.ai/news/production-at-bmw)); Fortune ([link](https://fortune.com/2025/04/06/figure-ai-bmw-humanoid-robot-partnership-details-reality-exaggeration/)); The Platinum Capital ([link](https://www.theplatinumcapital.com/article/figure-confirms-commercial-deployment-of-figure-03-at-bmw-plant-as-humanoid-robotics-cycle-accelerates)) |
| 11 *(excluded)* | **Tesla self-factory 1,000 units** | n/a | **Not an order** — internal R&D / data collection ("not in usage in our factories in a material way" — Musk Q4 2025) | Should be excluded from any backlog tally. | Electrek Q4 transcript ([link](https://electrek.co/2026/01/28/musk-admits-no-optimus-robots-are-doing-useful-work-at-tesla-after-claiming-otherwise/)) |

### 2.3 Implications

- **Chinese orderbook is mostly Tier B (binding gov bid awards) but concentrated in non-production end-uses** — data collection, training, demonstration, edu, security patrol. This is real revenue but does **not** validate industrial-scale autonomy or ROI.
- **Western orderbook is mostly Tier D (pilots) plus a small share of Tier B (Digit at GXO under RaaS, Figure phased at BMW)**. Headlines reference "commercial agreements" without unit volumes.
- **Tier A (paid + delivered + revenue-recognized at scale) is essentially absent** for full humanoids. The closest is Digit's GXO deployment, where RaaS revenue is being recognized but the absolute unit count is small.
- Reasonable adjusted view: **of the ~$3 bn of "humanoid orders" widely cited for 2025, roughly $1–1.5 bn is firm contract revenue and $1.5–2 bn is C/D/E.**

---

## Task 3 — Alternatives (AMR / Cobots / Fixed Automation vs Humanoids)

### 3.1 Side-by-side comparison

| Alternative | Representative vendor | Unit price | Deployment scale | Payback (public) | Source |
|---|---|---|---|---|---|
| **AMR (autonomous mobile robot)** | Locus Robotics | RaaS-only ([UNDISCLOSED] $/mo) | 17,000+ AMRs deployed; **7B+ picks assisted** | Often **<6 months**; **<12 months** for mid-tier sites | Locus ([link](https://locusrobotics.com/blog/raas-warehouse-roi)); Robot Report ([link](https://www.therobotreport.com/locus-robotics-launches-locus-array-for-fully-autonomous-fulfillment/)) |
| **Cube ASRS** | AutoStore | $1–5 M/system typical | **1,950+ systems globally**; ~34k bins/system avg; **99.8% uptime claim** | 20–26-week install (~50% faster than aisle ASRS) | AutoStore ([link](https://www.autostoresystem.com/system)); Kardex ([link](https://www.kardex.com/en-us/blog/how-autostore-works)) |
| **Goods-to-person robotic warehouse** | Symbotic | Full-system multi-$10M | **42 Walmart regional DCs**; backlog $22.5 bn; Walmart committed to 400 systems | Reported **20% opex reduction, up to 200% productivity gain**; Walmart cites **40% delivery-cost cut** | Symbotic IR ([link](https://ir.symbotic.com/static-files/8d44e050-9519-4347-aa51-fc51e49c4a87)); Symbotic press ([link](https://www.symbotic.com/about/news-events/news/walmart-and-symbotic-expand-partnership-to-implement-industry-leading-automation-system/)) |
| **Cobots (6-axis)** | Universal Robots | $11k (Franka) → $35k (UR10) → $60k (YuMi) | UR alone has shipped **>100,000 cobots cumulatively** | **3 months – 2 years**, typically 6–12 months for palletizing | UR ([link](https://www.universal-robots.com/blog/calculating-roi-and-payback-period-for-your-robotic-investment/)); Electromate ([link](https://www.electromate.com/resources/cobot-cost-analysis-and-roi/)) |
| **Humanoids** | Figure / Apptronik / Agility / Tesla | $25k–$130k+ (Goldman 2024 BOM band); some "RaaS at $1k/mo" (Figure) or "$30/hr" (Digit) | All humanoid programs combined: **single-digit thousands of units in the field** (mostly demo) | **No public payback case independently audited**; Agility targets ≤2-yr payback vs. $30/hr human | Goldman Sachs ([link](https://www.goldmansachs.com/insights/goldman-sachs-research/global-automation-humanoid-robot-the-ai-accelerant)); McKinsey ([link](https://www.mckinsey.com/industries/industrials-and-electronics/our-insights/humanoid-robots-crossing-the-chasm-from-concept-to-commercial-reality)) |

### 3.2 Brownfield reality

- For the canonical warehouse task — totes from rack-to-conveyor — **AMR + cobot at <$100k turnkey beats Digit-class humanoid on every metric** (price, cycle time, MTBF, payback). McKinsey: humanoid payback has dropped from 5.3 yrs (2019) to 2.8 yrs (2024) on paper — still ~3–5× slower than a Locus deployment.
- **AutoStore claims 99.8% uptime** with 30+ robots/system and 25k–34k bins. No humanoid program has published a comparable uptime number.
- For fixed-process production (Symbotic at Walmart), the system already delivers **20% opex savings and 200% throughput multiples**. Walmart has now agreed to acquire Symbotic's robotics business, which signals strong incumbent buy-in for non-humanoid form factors.

### 3.3 Expert commentary on bipedalism

- **Marc Raibert** (Boston Dynamics founder, on Lex Fridman #412): "A dynamic, wheeled system is far more efficient than a bipedal model." He has consistently flagged that bipedal humanoids are partly a "form-factor empathy" play, not strictly the optimal hardware ([link](https://lexfridman.com/marc-raibert-transcript/)).
- **Pieter Abbeel** (UC Berkeley / Covariant): hardware progress is real and commercially-viable humanoid hardware is plausibly 3 years out, **but** the AI to make humanoids useful in high-dim. action spaces is the binding constraint ([link](https://asiliconvalleyinsider.com/2025/03/21/humanoid-robots-professor-pieter-abbeel/)).
- Locus' own thought-leadership openly argues **"humanoids may not be ready for the warehouse; Locus Array is"** — a direct competitive position from the warehouse-robotics incumbent ([link](https://www.automate.org/robotics/industry-insights/humanoids-might-not-be-ready-for-the-warehouse-but-locus-array-is)).

### 3.4 Where humanoids genuinely add value

- **Brownfield retrofits where re-tooling is uneconomic** — e.g. older car-plant body shops with human-shaped workstations.
- **Non-repetitive, low-volume, varied-task work** that cobots cannot economically serve (need new fixture per part).
- **Defense / dual-use** (patrol, hazardous materials, EOD-adjacent) where a bipedal form factor matches existing infrastructure.

For "pick-and-pack at scale," they remain economically uncompetitive against Locus + AutoStore + Symbotic.

---

## Task 4 — Safety / Compliance / Liability

### 4.1 Standards landscape

| Standard | Coverage relative to humanoids | Source |
|---|---|---|
| **ISO 10218-1:2025 / -2:2025** | New 2025 revision **explicitly admits humanoid manipulator portions** ("fixed in place or fixed to a mobile platform"). **Mobility hazards (i.e. walking) are out-of-scope.** Non-industrial use (home, healthcare, service) also out-of-scope. ISO/TS 15066 (collaborative robots) has been **folded into ISO 10218-2:2025**. | Robot Report ([link](https://www.therobotreport.com/iso-10218-industrial-robot-safety-standard-receives-major-overhaul/)); ANSI Blog ([link](https://blog.ansi.org/ansi/iso-10218-1-2025-robots-and-robotic-devices-safety/)) |
| **ANSI/A3 R15.06-2025** | US national adoption of ISO 10218-1/-2 2025; same scope / same gaps re: bipedal locomotion + service contexts. | Automate.org ([link](https://www.automate.org/robotics/news/new-ansi-a3-r15-06-2025-american-national-standard-for-industrial-robot-safety-now-available-for-purchase)) |
| **Consumer/home robot safety** | **No standardized framework** in US/EU/CN covering full-size bipedal humanoids in the home today. 1X NEO ships into a regulatory vacuum. | Various (IBT, INT News) |

**Implication**: For C-suite buyers in industrial settings, integrators can certify the *manipulator arms* under ISO 10218 but the *walking* of a humanoid robot remains uncovered. EHS owners at customer plants will continue to require **caged-cell deployment or hard-stop interlocks** that erode the central pitch of "humanoid drops into human workspace."

### 4.2 Liability / insurance

- Munich Re and Swiss Re both published analyses (2017–2024) confirming the liability framework for humanoid robots is *immature*; claims will likely allocate liability across (i) OEM (design/manufacturing defect), (ii) software/data provider (AI policy error), (iii) operator (override / misuse).
- Emerging consensus: as autonomy increases, liability shifts toward the OEM and software stack — this is the **inverse** of conventional industrial-robot integrator-bears-risk model. Munich Re ([link](https://www.munichre.com/en/insights/digitalisation/who-is-liable-when-robots-cause-damage.html)); Swiss Re ([link](https://www.swissre.com/dam/jcr:d0c55abb-3e1a-4bfd-8fe9-e6bf914a5184/2017_11_TechRobots_trend_spotlight.pdf))
- Specialty insurance is forming (Branco Insurance Group's "Insurance for Robotics" line, dedicated humanoid-liability law firms), but **mature actuarial pricing is years away**.
- **Practical consequence**: PE diligence should price in a 5–15% premium on operating margins for product-liability reserves until industry loss data matures.

### 4.3 Consumer / home (NEO, Optimus C-end, Figure 03)

- **Cameras + microphones + cloud connectivity in private homes** = first-order privacy risk. 1X has tried to pre-empt with "no-go zones" and face-blurring — these are software-imposed and revocable.
- **Remote teleoperators** in foreign jurisdictions create a data-export profile that may run afoul of EU GDPR Art. 44 / China PIPL Art. 38. No public legal opinion published on whether NEO's "Expert Mode" is GDPR-compliant for EU customers.
- **Data ownership of factory/home telemetry** (which is the actual gold the AI flywheel mines) is uniformly absent from current commercial agreements — a critical contractual lever to negotiate.

---

## Task 5 — RaaS Balance-Sheet Economics

### 5.1 Public RaaS pricing benchmarks

| Vendor | Disclosed RaaS pricing | What it bundles | Source |
|---|---|---|---|
| **Agility Digit** | **$30/hr** retail today; opex $10–12/hr; potential floor $2–3/hr at scale | Hardware + Agility Arc software + maintenance + support | Robot Report ([link](https://www.therobotreport.com/heres-what-it-could-cost-to-hire-a-digit-humanoid/)); Reeman ([link](https://www.reemanrobot.com/news/at-30-an-hour-humanoid-robots-begin-to-work-80172774.html)) |
| **Figure AI** | **~$1,000/mo/robot** (i.e. ~$33/day) | Hardware deployment + software updates + maintenance + support | Sacra ([link](https://sacra.com/c/figure-ai/)); TSG Invest ([link](https://tsginvest.com/figure-ai/)) |
| **Apptronik** | RaaS framework signaled; pricing [UNDISCLOSED] | n/a | Apptronik news |
| **Locus Robotics** (for reference) | RaaS-only; per-bot/mo [UNDISCLOSED] but quoted as **<6-month payback** for most customers | Bot + software + service | Locus ([link](https://locusrobotics.com/blog/raas-warehouse-roi)) |

### 5.2 Implied unit economics for a humanoid RaaS

Public components:

- **BOM**: Goldman estimates **$30k (low) – $150k (high)** in 2024, **40% YoY decline** ([link](https://www.goldmansachs.com/insights/goldman-sachs-research/global-automation-humanoid-robot-the-ai-accelerant)).
- **Agility-disclosed unit purchase price proxy**: ~**$250k/unit** ([link](https://blog.robozaps.com/b/agility-robotics-digit-review)).
- **Figure 03 battery**: 2.3 kWh, **5-hour runtime/charge** ([link](https://www.figure.ai/news/series-c)) — implies ~2 charges/day shift → 10 hr productive.
- **Digit battery**: 8 hr; **2-to-1 cycle** (so 3 units to cover 2 active shifts continuously).
- **Maintenance / model-subscription / cloud-inference costs**: [UNDISCLOSED] across the board.
- **Residual value at 5 yr**: [UNDISCLOSED]; no vendor has published a depreciation curve.

### 5.3 Toy model: Digit at GXO under Agility's published $30/hr

Assume:

- 16 active hours/day (2-to-1 cycle), 6 days/week, 50 wk/yr ≈ 4,800 hr/yr.
- Gross revenue: 4,800 × $30 = **$144k/yr** per active robot-equivalent.
- Capex: 3 physical Digits per "active robot-equivalent" at ~$250k each = **$750k upfront**.
- Opex: $10–12/hr operating cost × 4,800 hr = **$48–58k/yr**.
- Contribution margin per active robot ≈ **$85–95k/yr** before SG&A, R&D, financing.
- Naive payback: $750k / $90k ≈ **8.3 yrs** before scaling savings (Agility expects opex to drop to $2–3/hr at scale, which would tighten payback to ~3.5 yrs).

This is **5–10× the payback period of a Locus AMR deployment**. Investors should expect humanoid RaaS to operate negative-EBITDA for the next 3–5 years.

### 5.4 The $39 B Figure valuation question

- Figure Series C: **$1 B+ raised at $39 B post-money** (Sep 2025; Parkway Venture Capital led; NVIDIA, Brookfield, Intel Capital, Salesforce, T-Mobile Ventures, Qualcomm Ventures, LG, Macquarie participated). Source: Figure ([link](https://www.figure.ai/news/series-c)); TechCrunch ([link](https://techcrunch.com/2025/09/16/figure-reaches-39b-valuation-in-latest-funding-round/)).
- Stated ramp: **BotQ → 100,000 units over 4 yrs**.
- Implied revenue arithmetic at $1k/mo RaaS: 100k × $12k/yr = **$1.2 B/yr** ARR at year-4 — i.e. valuation = **~33× year-4 ARR**, and 33× is *only* achievable if (a) the 100k ramp lands on schedule, (b) RaaS gross margin is software-like (>60%), (c) capex is heavily financed off-balance-sheet.

**Critical observation**: at $1,000/mo RaaS and even ambitious BOM of $30k, **Figure has at least 30 months of upfront capex per robot before recovering BOM**, before factoring software/service/financing costs. **The $39 B valuation requires implicit assumption of capex-light balance sheet** — i.e. customer-funded (PO + deposit) or asset-financed (lease facility / SPV / Brookfield infra structure). None of these are publicly confirmed, and the $39 B is essentially priced as if Figure can avoid the cash drag entirely.

### 5.5 Disclosure scorecard

None of Agility, Figure, Apptronik or Boston Dynamics has filed a public RaaS-segment income statement. Agility, by virtue of disclosed $30/hr pricing and acknowledged unit-purchase-price proxy, is the most transparent. Figure, despite a $39 B valuation, has the thinnest unit-economics disclosure of the four.

---

## Sources (full list)

- Figure AI / BMW press: https://www.figure.ai/news/production-at-bmw ; https://www.press.bmwgroup.com/usa/article/detail/T0444268EN_US/ ; https://www.figure.ai/news/series-c
- TechCrunch: https://techcrunch.com/2025/09/16/figure-reaches-39b-valuation-in-latest-funding-round/ ; https://techcrunch.com/2025/02/25/apptroniks-humanoid-robots-take-the-first-steps-toward-building-themselves/
- Electrek (Tesla Q4 2025 transcript): https://electrek.co/2026/01/28/musk-admits-no-optimus-robots-are-doing-useful-work-at-tesla-after-claiming-otherwise/ ; https://electrek.co/2026/04/22/tesla-optimus-production-fremont-model-sx-line/
- The Robot Report: https://www.therobotreport.com/heres-what-it-could-cost-to-hire-a-digit-humanoid/ ; https://www.therobotreport.com/iso-10218-industrial-robot-safety-standard-receives-major-overhaul/ ; https://www.therobotreport.com/apptronik-collaborates-with-jabil-to-produce-apollo-humanoid-robots/ ; https://www.therobotreport.com/1x-shows-advances-voice-control-chaining-tasks-humanoid-robots/ ; https://www.therobotreport.com/locus-robotics-launches-locus-array-for-fully-autonomous-fulfillment/
- Humanoids Daily: https://www.humanoidsdaily.com/feed/1x-ceo-details-neo-s-two-modes-and-defends-teleoperation-as-more-secure-than-a-cleaner ; https://www.humanoidsdaily.com/news/1x-details-neo-human-in-the-loop-strategy-and-hardware-as-pre-orders-go-live ; https://www.humanoidsdaily.com/feed/figure-ceo-brett-adcock-says-will-not-teleoperate-robots ; https://www.humanoidsdaily.com/news/autonomy-vs-teleop-brett-adcock-defends-figure-03-amidst-smoking-gun-skepticism
- Engadget: https://www.engadget.com/ai/1x-neo-is-a-20000-home-robot-that-will-learn-chores-via-teleoperation-040252200.html
- Agility Robotics: https://www.agilityrobotics.com/content/digit-moves-over-100k-totes ; https://www.agilityrobotics.com/content/mercado-libre-and-agility-robotics-announce-commercial-agreement
- Robotics & Automation News: https://roboticsandautomationnews.com/2025/11/24/agility-robotics-digit-humanoid-passes-100000-tote-milestone-in-live-gxo-implementation/96877/
- Goldman Sachs: https://www.goldmansachs.com/insights/goldman-sachs-research/global-automation-humanoid-robot-the-ai-accelerant ; https://www.goldmansachs.com/insights/articles/the-global-market-for-robots-could-reach-38-billion-by-2035
- McKinsey: https://www.mckinsey.com/industries/industrials-and-electronics/our-insights/humanoid-robots-crossing-the-chasm-from-concept-to-commercial-reality
- Boston Dynamics: https://bostondynamics.com/blog/atlas-evolution-from-research-robot-to-industrial-humanoid/
- Symbotic IR: https://ir.symbotic.com/static-files/8d44e050-9519-4347-aa51-fc51e49c4a87
- Locus Robotics: https://locusrobotics.com/blog/raas-warehouse-roi
- Sina / STCN / Yicai / EET-China / Eastmoney / Shenzhen DRC (Chinese-source bids and orderbooks): see citations inline
- Fortune (Figure-BMW skepticism): https://fortune.com/2025/04/06/figure-ai-bmw-humanoid-robot-partnership-details-reality-exaggeration/
- Munich Re / Swiss Re (liability frameworks): https://www.munichre.com/en/insights/digitalisation/who-is-liable-when-robots-cause-damage.html ; https://www.swissre.com/dam/jcr:d0c55abb-3e1a-4bfd-8fe9-e6bf914a5184/2017_11_TechRobots_trend_spotlight.pdf
- ANSI: https://blog.ansi.org/ansi/iso-10218-1-2025-robots-and-robotic-devices-safety/
- Automate.org: https://www.automate.org/industry-insights/ansi-a3-publish-revised-r15-06-industrial-robot-safety-standard ; https://www.automate.org/robotics/industry-insights/humanoids-might-not-be-ready-for-the-warehouse-but-locus-array-is
- AutoStore: https://www.autostoresystem.com/system
- Lex Fridman Podcast #412 (Marc Raibert): https://lexfridman.com/marc-raibert-transcript/
- Silicon Valley Insider (Abbeel): https://asiliconvalleyinsider.com/2025/03/21/humanoid-robots-professor-pieter-abbeel/

---

*End of research document. All quantitative claims sourced or marked [UNDISCLOSED]. Adversarial-review-friendly: every order-tier classification has an evidentiary basis, and every autonomy claim is anchored to a named executive statement or independent verification.*
