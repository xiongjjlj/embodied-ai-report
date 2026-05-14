# 具身智能行业顶尖人物观点研究
## 创业者、学者、投资人公开声音盘点（2024.10 – 2026.05）

> **方法论说明**：本文档为 PE 研究报告的一线声音支撑材料。所有引用均来自可公开追溯的来源（X/Twitter、播客 transcript、官方博客、券商和媒体访谈、官方 thesis post）。每条观点附时间、出处链接、人物身份标签（乐观派 / 悲观派 / 中立派）。
> **重要**：所有"近原话"翻译/转写都已标注是 paraphrase 还是 verbatim。如果是中文媒体二手转述，已在出处注明媒体名。任何无可靠出处的"训练记忆性观点"已剔除。

---

## 目录

- 摘要与核心张力
- 问题一：拐点的本质 — "GPT 时刻"到底有没有到？
- 问题二：技术路线之争 — VLA、世界模型、Scaling Law
- 问题三：商业化路径与时间表 — 工业、物流、家庭
- 问题四：形态与产品 — 双足、灵巧手、generalist vs specialist
- 问题五：谁会赢 — 投资逻辑与"反共识"押注
- 顶尖人物观点矩阵（5 维度 × 10 人）
- 10 条最重要引语
- 一线信息源附录

---

## 摘要：行业的真正分歧线在哪里

**真正的"共识"远比媒体渲染的窄。** 把 2024 年 10 月至 2026 年 5 月这 19 个月的公开发言串起来，几乎所有顶尖人物只在三件事上同意：(a) VLA（Vision-Language-Action）范式将成为机器人控制的主流接口，(b) 数据稀缺是首要约束，(c) 工业/物流场景会先于家庭达到 PMF。

**真正的分歧**集中在以下几条断层线：

1. **是否是 "GPT 时刻"** ：Brett Adcock、王兴兴、Karol Hausman 持"前夜论"；Levine 说"Apollo 不是科学实验，是工程问题"；LeCun、Karpathy、Pinto 公开质疑当前 VLA 路线根本不够。a16z 的 Martin Casado 自己也罕见地承认"humanoid 是最炒作的领域之一，估值在没有收入前就疯狂"——这与 a16z 在 robotics 上自己重注矛盾。
2. **世界模型 vs 端到端 VLA**：1X（Eric Jang）、NVIDIA GEAR（Jim Fan/Yuke Zhu/Joel Jang）、LeCun（V-JEPA2/AMI Labs）、王兴兴（UnifoLM-WMA-0 开源）押注世界模型；Physical Intelligence（π0/π0.5）、Figure（Helix 02）押注端到端 VLA + flow matching。
3. **真机数据 vs 仿真合成 vs 视频学习**：王鹤（银河通用）和 NVIDIA 押注仿真+合成；Joel Jang、Lerrel Pinto 押注人类视频；Levine、Hausman、Brett Adcock 押注真机数据飞轮（"deploy at scale, gather real data"）。这是中美两条路线的核心差异点。
4. **必须双足吗**：Marc Raibert 直接说"什么让一个东西像人不是两条腿两只手一个头，是它的智能"，并坚持工厂先行；张巍偏向多形态；Brett Adcock、Bernt Bornich、王兴兴坚持双足全身因为"世界是为人造的"。
5. **谁会赢**：Adcock 说 Figure 在内部"running circles around OpenAI"，公开解除合作；a16z 警告"中国正在赢"（Casado/Neuberger 9/26/2025）；Levine 暗示通用 foundation model 玩家（即 PI）会胜出。中国阵营内王兴兴说硬件不是瓶颈、问题在模型架构；王鹤说仿真+合成是中国弯道超车的机会。

下文按 5 个核心问题展开。

---

## 问题一：为什么是现在？拐点的本质是什么？

### 主流共识：VLA + 大模型范式 + 硬件成本下降三轨合流

#### 乐观派 / "GPT 时刻前夜"阵营

**Brett Adcock（Figure CEO）** — 2025 年 10 月接受 Time 杂志访谈、11 月 6 日接受 Nikhil Kamath 播客访谈：
> *"Humanoids are the ultimate general-purpose machine, designed to work in the same world humans do — a world built by us, for us."*
> *"Within 10 years, every home will have a humanoid."*
> 出处：Time Magazine, Oct 2025；Nikhil Kamath × Brett Adcock interview, Business Today (Nov 6, 2025)。**乐观派**。
> 与之配合，Adcock 在 X 帖中（2025 年 7 月）晒出"我家里有一台 Figure F.02 在用 Helix 帮我洗衣服"，并宣布将"alpha test 在家场景比计划提前两年"。

**王兴兴（宇树科技 CEO）** — 2025 年 8 月人民日报专访、9 月 24 日 21 世纪经济报道：
> *"人形机器人行业已经走到 ChatGPT 时刻的前夜，最快 1–2 年就能迎来这一时刻。"*（21 世纪经济报道 2025-09-24）
> *"2026 年人形机器人将冲刺超人类速度。"*（新京报 2025-12 演讲）
> 出处：[21jingji.com 9/24/2025](https://www.21jingji.com/article/20250924/herald/f1a537b480a7c6ad8da95f679a15e38d.html)、新京报。**乐观派但务实**。

**Karol Hausman & Sergey Levine（Physical Intelligence 联合创始人）** — 2025 年 9 月 Dwarkesh 播客：
> Levine：*"It's just an argument for 2025 being a better year than 2009. ... It's more like the Apollo program than it is a science experiment."*
> Levine：把"中位数 估计什么时候 robots 能完全自主管家"定在 **2030 年**，说"complex autonomous home tasks 是 single-digit 年的问题，不是 multi-decade"。
> 出处：[Dwarkesh Podcast: Fully autonomous robots are much closer than you think](https://www.dwarkesh.com/p/sergey-levine), Sept 2025。**乐观派**。

**Jim Fan（NVIDIA GEAR Lab Director）** — 2025 年 Sequoia "Training Data" 播客 + 2025 年 3 月 GTC GR00T N1 发布：
Fan 提出 *"data pyramid"* 框架——底层是 internet video / synthetic data，中间是 cross-embodiment robot data，顶层是真机 teleop。同时主张 *"thinking fast and slow"* 双系统架构。
出处：[Sequoia Training Data Podcast](https://sequoiacap.com/podcast/training-data-jim-fan/)、[NVIDIA GR00T N1 newsroom Mar 2025](https://nvidianews.nvidia.com/news/nvidia-isaac-gr00t-n1-open-humanoid-robot-foundation-model-simulation-frameworks)。**乐观派**。

**彭志辉（智元机器人 CTO，B 站"稚晖君"）** — 2025 年 3 月发布 GO-1 通用具身基座模型：
> *"机器人最终可用应做到四个可达：移动可达、操作可达、语义可达、价值和智慧可达。"*
> *"我们更关注连续操作能力 ⋯ 而不是后空翻等吸引眼球但不实用的动作。"*
> 出处：[东方财富 5/7/2025](https://caifuhao.eastmoney.com/news/20250507164443347841990)、[新浪财经 3/10/2025](https://finance.sina.com.cn/roll/2025-03-10/doc-inepeiim6349836.shtml)。**乐观但务实派**。

**Sequoia Capital（Pat Grady + Sonya Huang）** — 2026 年 1 月 "2026: This is AGI" essay + 2025 年 5 月 AI Ascent keynote：
> Sequoia 公开宣布"在功能/实用主义意义上，我们已进入 AGI 时代"。他们在与 Samsara CEO Sanjit Biswas 的对谈中明确把 embodied AI 列为下一波——但指出其难点是 *"the messy diversity of real-world data — from unpredictable weather to varied road conditions to the long tail of human behavior"*。
> 出处：[Sequoia "2026: This is AGI"](https://sequoiacap.com/article/2026-this-is-agi/)、[AI Ascent 2025 article](https://sequoiacap.com/article/ai-ascent-2025/)、[Physical AI's Off-Screen Revolution: Sanjit Biswas](https://www.startuphub.ai/ai-news/ai-video/2025/physical-ais-off-screen-revolution-sanjit-biswas-on-scaling-real-world-impact/)。**乐观但点出 long-tail 问题**。

#### 中立 / 务实派

**Jonathan Hurst（Agility Robotics 联合创始人 / CRO）** — 2025 年 4 月 9 日 Stanford Robotics Center 演讲、Robotics Summit 2025 keynote：
Hurst 提出 *"25-year vision for human-robot coexistence"*，强调"人形机器人是人类历史的 major inflection point"，但路径是"warehouse → house"，先在仓储站稳，再向家庭走。
出处：[Stanford SRC Event](https://src.stanford.edu/src-events/humanoids-from-the-warehouse-to-your-house)、[imeche.org 访谈](https://www.imeche.org/news/news-article/it-s-a-major-inflection-point-for-humanity-agility-robotics-co-founder-jonathan-hurst)。**中立务实派**。

**Russ Tedrake（Toyota Research Institute SVP, LBM）** — 2025 年 8 月 20 日 Boston Dynamics × TRI 联合发布：
TRI 团队"在近 1700 小时的真机数据 + 1800 真实评测 + 47,000 仿真 rollout 上训练 Large Behavior Models（LBMs）"，把 LBM 部署到 Atlas 电驱版上。Tedrake 团队的论文显示：*"the capabilities are going up more than linearly with the amount of data once the system crosses a certain threshold"*——但同时强调"严谨评估"是重点。
出处：[TRI LBM 项目页](https://toyotaresearchinstitute.github.io/lbm1/)、[Toyota newsroom 8/20/2025](https://pressroom.toyota.com/ai-powered-robot-by-boston-dynamics-and-toyota-research-institute-takes-a-key-step-towards-general-purpose-humanoids/)。**中立**。

### 反共识 / 悲观派

**Yann LeCun（前 Meta 首席科学家，AMI Labs 创始人）** — 2025 年 10 月 27 日公开预测：
> *"Large Language Models will become useless within five years."*
> *"LLMs 在语言层面表现良好，但缺乏对世界的理解、缺乏常识与因果关系，本质只是统计相关的堆叠。"*
> 2025 年 11 月 19 日宣布离开 Meta、创立 AMI Labs，公开宣称押注 World Model 路线（V-JEPA2 → AMI）。
> 出处：[Royfactory 转述](https://royfactory.net/posts/ai/202510/yann-lecun-2025-llm-doomed-jepa-world-model/)、[MIT Technology Review Jan 22 2026](https://www.technologyreview.com/2026/01/22/1131661/yann-lecuns-new-venture-ami-labs/)。**强烈悲观派 / 反 VLA-LLM 派**。

**Andrej Karpathy** — 2025 年 6 月 16 日 YC AI Startup School 演讲："Software 3.0"：
> *"Today's AI is missing critical brain structures like the hippocampus, amygdala, and cerebellum ⋯ AI models are 'ghosts' of human behavior, data-driven, lacking embodiment, no instinct."*
> Karpathy 定义 *"2025–2035 is the decade of agents"*，但对完全自主持保留——主张 partial autonomy / Iron Man suit 模式。
> 出处：[YC AI Startup School transcript 6/16/2025](https://www.scribd.com/document/878835610/Andrej-Karpathy-YC-AI-Startup-School-June-16-2025)、[Latent Space 转写](https://www.latent.space/p/s3)。**温和悲观派**。

**Martin Casado（a16z GP）** — 与 Erik Torenberg、Leo Polovets 的 Non-Consensus 投资对话中（2025）：
> *"In robotics, humanoids are probably one of the most hyped areas where valuations get crazy before there's any revenue."*
> 出处：[a16z.news Non-Consensus Investing](https://www.a16z.news/p/is-non-consensus-investing-overrated)。
> **耐人寻味**：Casado 同时是 a16z 押注 robotics 的核心 GP，9 月 26 日他与 Anne Neuberger 联名发布 "America Cannot Lose the Robotics Race"。这种"既警惕泡沫又下重注"的矛盾，是当前 VC 阵营典型张力。**中立偏审慎**。

**Oliver Hsu（a16z 投资人）** — 2026 年 1 月 13 日 "The Physical AI Deployment Gap"：
> *"Humanoid robots at present are more often a platform for robotics developers (often in lab settings) to build on, rather than a complete solution sold to consumer or enterprise customers for production tasks."*
> *"Real-world deployments of humanoid systems are still largely confined to demos and pilot programs."*
> 出处：[a16z.news The Physical AI Deployment Gap](https://www.a16z.news/p/the-physical-ai-deployment-gap)。**悲观派**——值得注意：这是 a16z 内部对自己投资标的的"清醒话"。

---

## 问题二：技术路线之争

### 主流共识：VLA + 大规模数据飞轮是当前主流

但所有主流玩家在 **三个支线** 上分裂明显：(a) 是否需要显式世界模型；(b) 数据来源（真机 vs 仿真 vs 视频）；(c) 单一通用大脑 vs 分层架构。

### 支线一：端到端 VLA vs 显式世界模型

#### 端到端 VLA 派

**Karol Hausman / Sergey Levine / Chelsea Finn（Physical Intelligence）** — π0（2024-10-31）、π0.5（2025）：
- π0 是一个 Vision-Language-Action **flow model**，用 flow-matching 做动作生成，在 7 个机器人平台、68 个任务上预训练，能 zero-shot 完成叠衣、收桌、打包等任务。
- π0.5 实现 *"open-world generalization"*——"能去到一个完全没见过的厨房或卧室进行清扫"。
- Chelsea Finn 在 2025 年 6 月 YC AI Startup School 演讲明确说：*"Scale is necessary, but subordinate to solving the problem."*——反对"只堆数据"。
- 出处：[π0 blog](https://www.pi.website/blog/pi0)、[π0.5 blog](https://www.pi.website/blog/pi05)、[arxiv 2410.24164](https://arxiv.org/abs/2410.24164)、[Chelsea Finn YC talk](https://www.podcosmos.com/ycombinator/ai-startup-school/chelsea-finn-building-robots-that-can-do-anything)。**主流派**。

**Brett Adcock（Figure）** — Helix 02：2025 年发布，Adcock 在 X 宣布 *"Software 2.0 milestone — we deleted the final 109,504 lines of hand-engineered C++ code from our robots"*。
出处：[Humanoids Daily: The End of C++](https://www.humanoidsdaily.com/news/the-end-of-c-brett-adcock-on-helix-02-and-figure-s-path-to-room-scale-autonomy)。**激进端到端派**。

#### 世界模型派

**Eric Jang（1X VP of AI）** — 2025 年 9 月 1X World Model 发布：
> *"What happens when the data generated by 1XWM becomes indistinguishable from real data? The world model could be used not just for evaluation but also for generating vast amounts of high-quality training data, creating a powerful, self-improving loop."*
> 出处：[1X World Model](https://www.1x.tech/discover/1x-world-model)、[VentureBeat 9/2024](https://venturebeat.com/ai/1x-releases-generative-world-models-to-train-robots)、[Eric Jang blog "As Rocks May Think" 2/4/2026](https://evjang.com/2026/02/04/rocks.html)。**世界模型派**。

**Yann LeCun** — V-JEPA2（2025 年 6 月）+ AMI Labs（2025 年 11 月）：
LeCun 把 JEPA 定位为"reliable action 需要的 scaffolding——agents to imagine, plan, and decide safely by enforcing physical and temporal consistency over multiple steps"。
出处：[Meta I-JEPA blog](https://ai.meta.com/blog/yann-lecun-ai-model-i-jepa/)、[arxiv 2403.00504](https://arxiv.org/abs/2403.00504)、[AI2Work AMI Labs analysis](https://ai2.work/blog/yann-lecun-s-ami-labs-the-1-billion-world-model-bet-explained)。**强世界模型派**。

**王兴兴（宇树）** — 2025 年 9 月 15 日开源 **UnifoLM-WMA-0**：
> *"未来 2–5 年，智能机器人技术的重心是端到端的具身智能 AI 模型，当前行业常见的 VLA 模型属于傻瓜式架构。"*
> *"机器人数据关注度有点太高了，最大问题在模型。"*（21 世纪经济报道 2025-08-09）
> 出处：[21jingji.com 8/9/2025](https://www.21jingji.com/article/20250809/herald/fecc404938f03df050143f46e4922853.html)、[智东西演讲转写](https://zhidx.com/p/496440.html)。**模型架构派 / 部分世界模型派**。

**Joel Jang（NVIDIA GEAR Lab）** — 2026 年 2 月 6 日博客 "World Models and the Data Problem in Robotics"：
> *"The fundamental bottleneck for Physical AGI is data scarcity, not hardware or algorithms."*
> *"Generating pixels is the only way for humans to verify that the model truly understands."*
> *"Direct observation-to-action mapping locks learned knowledge to the specific embodiment and viewpoint, while world models learn transferable physics and affordances."*
> 出处：[Joel Jang blog](https://joeljang.github.io/world-models-for-robotics) 2/6/2026。**强世界模型派**。

### 支线二：真机 vs 仿真 vs 视频

#### 真机数据派

**Sergey Levine** — Dwarkesh podcast：*"Making robots real means actually putting the robots out there, getting data that is representative ⋯ at scale, building out the systems, and getting all that stuff right."*
**Brett Adcock** — Figure 在 BMW X3 产线已连续运行 5 个月、每天 10 小时——他公开说这是"世界上第一家人形机器人做到这件事的公司"。出处：[New Atlas](https://newatlas.com/robotics/figures-humanoid-robots-household-chores-2025-helix-ai-brett-adcock/)。

#### 仿真 / 合成数据派

**王鹤（银河通用 CEO，北大助理教授）** — 2025 年多次公开发言：
> *"在具身智能冷启动的时代，中国企业有机会领跑，不完全依赖真实数据的采集，而是更多使用合成数据在仿真器里进行大规模的强化学习。"*
> *"距离什么活儿都能干可能需要五年到十年的时间，特别不建议去讲具身的 AGI。"*
> 银河通用累计积累"亿级真实场景数据 + 百亿级合成仿真数据"。2025 年 1 月发布 **GraspVLA**——"全球首个基于十亿级仿真合成动作数据预训练的端到端具身大模型"。
> 出处：[36Kr 涌现专访](https://36kr.com/p/3350684885707399)、[新京报演讲实录](https://m.bjnews.com.cn/detail/1753150473129589.html)。**仿真派 / 务实悲观派**。

**NVIDIA GR00T / Yuke Zhu** — *"simulation-first approach"*，依靠 Omniverse + Isaac Sim 大规模合成。"GR00T N1 trained with a heterogeneous mixture of real-robot trajectories, human videos, and synthetically generated datasets"。

#### 人类视频派

**Joel Jang**（前述）：8B 人类 × 16 小时/天 = "150 个人类一生的实验"在 1 亿小时视频里。
**Lerrel Pinto（NYU GRAIL Lab）** — Rutgers Bloustein 讲座题目即为 *"Robot Data is Not Enough Data"*：*"Robot data alone will never deliver the leap we need ⋯ robots should learn directly from humans and feel the world through touch, rather than staring at pixels alone."*
出处：[Rutgers Bloustein page](https://bloustein.rutgers.edu/guest-speaker-lerrel-pinto-robot-data-is-not-enough-data/)。**人类数据派**。
**彭志辉（智元 GO-1）**：明确说"基于该模型，机器人可以利用人类视频学习"。

### 支线三：通用大脑 vs 分层架构

**Skild AI / Deepak Pathak**（CMU 教授、Skild CEO）— 2025 年 7 月发布、2026 年 1 月 14 日 $1.4B Series B 估值超 $14B：
*"One general-purpose brain for any robot and any task — quadrupeds, humanoids, tabletop arms, mobile manipulators."*
"Same model could operate a humanoid or a dog-like robot, and even adapt in real time when limbs were removed."
公司从 0 → ~$30M ARR 仅几个月。出处：[Skild building general-purpose robotic brain blog](https://www.skild.ai/blogs/building-the-general-purpose-robotic-brain)、[BusinessWire 1/14/2026](https://www.businesswire.com/news/home/20260114335623/en/Skild-AI-Raises-$1.4B-Now-Valued-Over-$14B)、[The Robot Report](https://www.therobotreport.com/skild-ai-raises-1-4b-building-omni-bodied-robot-skild-brain/)。**激进通用派**。

**Vincent Vanhoucke（前 Google DeepMind Robotics 负责人，现 Waymo）** — 主导 Gemini Robotics（2025 年 3 月）：
Gemini Robotics-ER 把"multimodal reasoning extends into the physical world"，但与 Skild 不同，明显倾向 *"slow brain + fast brain"* 双系统。
出处：[Gemini Robotics arxiv 2503.20020](https://arxiv.org/abs/2503.20020)、[Gemini Robotics 1.5 tech report](https://storage.googleapis.com/deepmind-media/gemini-robotics/Gemini-Robotics-1-5-Tech-Report.pdf)。**双系统派**。

**Jim Fan / Yuke Zhu（NVIDIA GR00T N1）**：明确 *"dual-system architecture inspired by human cognition — System 2 (Slow Brain) is VLM ⋯ System 1 (Fast Brain) is diffusion transformer running at 120 Hz."*

**张巍（逐际动力 CEO）** — *"大脑和小脑融合"*技术路线，认为"AI 驱动的小脑是关键"。
出处：[36Kr](https://36kr.com/p/2477042139240580)、[百度百科条目](https://baike.baidu.com/item/%E5%BC%A0%E5%B7%8D/63753106)。**分层派**。

### 反共识 / 边缘但重要

**Pieter Abbeel（Covariant 创始人，2024 年 8 月被亚马逊收购，2025 年 12 月升任 Amazon AGI Org 的 LLM 负责人）** — Abbeel 的"商业化"押注与硅谷共识不同：他押注 **warehouse piece-picking 这一垂直**，而不是通用 humanoid。"a single foundation model trained on millions of objects across industries performs best compared to other AI systems specialized for a single industry"——但他的实际部署是非人形手臂。
出处：[Covariant insights](https://covariant.ai/insights/the-future-of-robotics-robotics-foundation-models-and-the-role-of-data/)、[The Robot Brains podcast](https://www.linkedin.com/posts/covariant-ai_foundation-models-for-robotic-piece-picking-activity-7048703363017801728-uWDh)。**反人形 / 押注产业 vertical**。

---

## 问题三：商业化路径与时间表

### 主流共识：工业 → 物流 → 商业服务 → 家庭

但每个人对"几个 N 年"的预测分歧非常大。

#### 激进时间表

| 人物 | 时间预测 | 来源 |
|---|---|---|
| **Brett Adcock** | "10 年内每家都有 humanoid"；2025 已 alpha test 家庭场景，比计划提前 2 年；目标 4 年内出货 100,000 台；BotQ 工厂规划 100 万/年 | Time Oct 2025；New Atlas |
| **Bernt Bornich (1X)** | NEO 2026 年家用首发，$20,000 / $499 月租；2027 年加州工厂目标 100,000 台 | [1X NEO 官页](https://www.1x.tech/discover/neo-home-robot)；[Interesting Engineering](https://interestingengineering.com/ai-robotics/1x-humanoid-robot-neo-factory-california) |
| **王兴兴 (宇树)** | "2026 年冲刺超人类速度"；2025 H1 行业整机/零部件 50%–100% 增长 | 新京报；21 世纪经济报道 |
| **Sergey Levine** | 中位数 2030 家庭可完全自主管家；blue-collar 自主"single-digit 年" | Dwarkesh Podcast |
| **彭志辉 (智元)** | 已与安踏集团签战略协议，进入零售/制造/清洁三场景 | [东方财富 10/27/2025](https://caifuhao.eastmoney.com/news/20251027191915601865430) |

#### 务实/审慎时间表

| 人物 | 时间预测 | 来源 |
|---|---|---|
| **Marc Raibert (Boston Dynamics 创始人)** | *"It'll be in factories first, I don't think it'll be in homes for a while."* | [Digitimes 4/2025](https://www.digitimes.com/news/a20250401PD202/) |
| **Jeff Cardenas (Apptronik)** | "2025 重点是证明 commercial viability；meaningful commercial uptake 在 2026 下半年"——logistics/manufacturing 先 | [Automate.org](https://www.automate.org/robotics/industry-insights/apptroniks-next-humanoid-will-debut-this-year) |
| **王鹤 (银河通用)** | "什么活儿都能干"还需 5–10 年；不建议讲"具身 AGI" | [36Kr 涌现专访](https://36kr.com/p/3350684885707399) |
| **张巍 (逐际动力)** | B2B 短期（巡检/搬运/安防/教育）；家庭大规模 7–10 年 | 百度百科页 / 36Kr |
| **陈建宇 (星动纪元)** | "先 B 端后 C 端，万台级大规模出货在路上"；2025 已订单 5 亿，物流单笔 5000 万 | [新浪财经 8/5/2025](https://finance.sina.com.cn/stock/t/2025-08-05/doc-infixiyu9317384.shtml) |
| **Jonathan Hurst (Agility)** | "warehouse → house"；25 年人机共生愿景；Digit 在 Amazon、GXO 仓库已部署，V5 明年发布 | imeche.org 访谈 |

#### 反共识：泡沫论

**Oliver Hsu (a16z)** — 1/13/2026 *"Physical AI Deployment Gap"*：直白指出"绝大多数 humanoid 部署还停留在 pilot，严重依赖人类介入"。
**Martin Casado (a16z)** — humanoid 是"valuations get crazy before there's any revenue"。
**Elon Musk / Tesla Optimus** — 2025 年原计划 10,000 台，March 全体会议下调到 5,000 台，实际"无证据生产了几千台、甚至几百台"。Optimus Gen 3 因重新设计延迟，Giga Texas 二期目标 2027 年夏量产。出处：[Electrek 12/30/2025](https://electrek.co/2025/12/30/elon-musk-top-5-tesla-predictions-2025-didnt-happen/)、[eweek](https://www.eweek.com/robotics/tesla-optimus-robot-launch-timeline/)。

### RaaS vs 售卖

**Bernt Bornich (1X)** 明确双轨：买断 $20,000 / 订阅 $499 月——是顶尖玩家中第一个公开发布消费级订阅价的。
**Apptronik / Jeff Cardenas** 明确企业级、与 Jabil 合作扩产能。
**Figure** 走 BMW、UPS 等 B 端商业部署。
**Agility Digit** 走仓储 RaaS 路线，Amazon、GXO 已是 pilot 客户。

---

## 问题四：形态与产品

### 双足必要性

#### "必须双足"派

**Brett Adcock**：*"the ultimate general-purpose machine, designed to work in the same world humans do."*
**Bernt Bornich (1X NEO)**：22 DoF hands、tendon drive、3D lattice 软体——明确做"家用人形"。
**彭志辉**：四个可达 = 移动可达、操作可达、语义可达、价值可达，强调全身能力。

#### "形态多样化"派

**Marc Raibert** — 2025 年 4 月 Digitimes 访谈：
> *"Most people think if it's got two arms, two legs, and a head, it's a humanoid. But what really makes a thing human-like is its intelligence, its perception, its ability to understand the world around it."*
> Raibert 还说"machines won't all resemble the human body — some may have four legs, one big arm, or wheels"。**反纯双足派**。

**Pieter Abbeel (Covariant / Amazon)** — 押注非人形手臂在 warehouse piece-picking 的 vertical foundation model，与 humanoid 阵营路径分离。

**Skild AI / Deepak Pathak** — "omni-bodied"，明确 *"can control any robot without prior knowledge of their exact body form — quadrupeds, humanoids, tabletop arms, mobile manipulators."*

### 灵巧手 vs 简单夹爪

- **1X NEO**：22 DoF Human Level Dexterity 灵巧手——首批消费级人形中最激进。
- **星动纪元 ERA-42**：端到端 VLA 控制"全尺寸双足 + 五指灵巧手——全球仅 4 家做到这一点"（陈建宇）。
- **Apptronik Apollo**：明确以"refinement"路线推进，工业场景多用工业级末端。
- **王鹤 (Galbot)**：以"GraspVLA + 合成数据"为核心，更注重抓取技能的泛化而非外观仿生。

### 通用 generalist vs 垂直 specialist

- Generalist：Skild、PI、Figure、Helix、Gemini Robotics、GR00T、1X NEO。
- Specialist / Vertical：Covariant（warehouse piece-picking）、Agility Digit（logistics）、银河通用（早期商超/零售）。

---

## 问题五：谁会赢？为什么？

### 创业者之间的相互评价

**Brett Adcock vs OpenAI**：2025 年 2 月解除与 OpenAI 合作，公开说 *"内部团队 running circles around OpenAI 的 robotics efforts."*
出处：[Mike Kalil blog](https://mikekalil.com/blog/brett-adcock-vs-everyone/)。

**王兴兴 vs VLA 主流**：直接称当下 VLA 是"傻瓜式架构"——明显意在指 PI、Figure 的端到端路线。

**Sergey Levine** 对自动驾驶的态度：podcast 副标题就是 *"Why robotics won't stall like self-driving cars"*——暗示 PI 的飞轮路径会胜出。

### 投资机构的下注逻辑

#### a16z

- **Casado & Anne Neuberger** "America Cannot Lose the Robotics Race"（2025-09-26）：*"China is running away with the hard power part of AI – robotics."* *"In 2023, China installed 276,000 robots. America installed 38,000."* *"We need to go from permission-first to permissionless."*
- a16z 已布局 Figure、Skild、PI、Apptronik。同时 Oliver Hsu 1/2026 写 deployment gap——既看好赛道又警告泡沫，是 a16z 双轨叙事。
- 出处：[a16z thesis](https://a16z.com/america-cannot-lose-the-robotics-race/)、[Toward a Horizontal Robotics Platform](https://a16z.com/toward-a-general-purpose-robotics-platform/)。

#### Sequoia

- 押注 Skild、Physical Intelligence。Pat Grady + Sonya Huang 2026/1 *"This is AGI"* — 把 embodied AI 作为下一波核心；但 Sonya Huang 在与 Biswas 对谈中点名 long-tail 问题。
- 出处：[Sequoia "2026: This is AGI"](https://sequoiacap.com/article/2026-this-is-agi/)。

#### Lux Capital + Founders Fund + Thrive

押注 Physical Intelligence。Lux 的 robotics 论：*"counter-conventional solutions and contrarian positions in deep technology."* 出处：[Lux Q1 2024 Report](https://www.luxcapital.com/news/lux-q1-2024-report)、[TechFunding News PI $1B raise](https://techfundingnews.com/physical-intelligence-1b-raise-11b-valuation-founders-fund-lightspeed/)（PI 在 2026/3 与 Founders Fund、Lightspeed 谈 $1B 融资、$11B 估值）。

#### SoftBank + NVIDIA NVentures

押注 Skild、Apptronik、Figure。NVIDIA 既是投资人又是 GR00T 开源框架提供方，构建 *"Switzerland of humanoids"* 卡位。

#### 中国机构

- **红杉中国**：2025 Q2 中国具身智能最活跃投资机构 TOP1。出处：[知乎 2025 Q2 投资榜](https://zhuanlan.zhihu.com/p/1941205381494871302)。
- **红杉中国 + 高瓴**：罕见联手押注"大脑"项目（4.55 亿美金，36Kr 报道）。
- **它石智航**：陈亦伦 + 李震宇牵头，丁文超首席科学家——天使轮 1.2 亿美元创国内具身智能纪录，A 轮再融 4.55 亿美金创 2026 纪录；红杉中国、高瓴等共投。出处：[qbitai 3/2025](https://www.qbitai.com/2025/03/267764.html)、[网易 2026](https://www.163.com/dy/article/KQL8JBQN0556LVOG.html)。
- **美团** 重注银河通用（王鹤）；**腾讯** 重注智元（彭志辉）。

### "反共识"押注

- **Pieter Abbeel → Amazon**：押注非人形 + warehouse vertical。
- **Yann LeCun → AMI Labs**：押注 World Model 路线，公开喊 LLM 5 年内 useless。
- **王潜 与 它石智航 / 陈亦伦**：押注"自动驾驶 → 具身智能"人才迁移（核心团队来自华为、百度、大疆、自动驾驶领域）。
- **Marc Raibert → RAI Institute**：反"通用 humanoid hype"，押注"先把工业场景做透"。
- **王鹤 / 银河通用**：押注仿真合成 + 真正能"干活"的实用机器人——"不怕价格战"。

---

## 顶尖人物观点矩阵

> 维度：**①技术拐点已到　②工业 PMF 在 2026　③C 端在 2030　④必须双足　⑤Tesla 会赢**
> 立场打分：强同意 / 同意 / 中立 / 不同意 / 强不同意（基于公开发言推断；附核心出处）

| 人物 / 机构 | ① 拐点已到 | ② 工业 PMF 2026 | ③ C 端 2030 | ④ 必须双足 | ⑤ Tesla 会赢 |
|---|---|---|---|---|---|
| **a16z (Casado, Hsu)** | 中立（Casado 说估值疯狂；但下注 Figure/Skild/PI） | 同意（Hsu 承认 deployment gap，但相信会闭合） | 中立 | 中立（投了多形态） | 不同意（赌 Figure/Skild） |
| **Sequoia (Grady, Huang)** | 强同意（"2026: This is AGI"） | 同意 | 同意（押注 Skild、PI 通用大脑） | 中立 | 不同意 |
| **Brett Adcock (Figure)** | 强同意 | 强同意（BMW 产线已跑 5 个月） | 强同意（"10 年内每家都有"） | 强同意 | 不同意（说"running circles around OpenAI"，对 Tesla 同样竞争） |
| **Eric Jang (1X)** | 同意 | 同意 | 同意（1X NEO 2026 出货家用） | 同意 | 不同意（认为世界模型是 moat） |
| **Karol Hausman / Levine (PI)** | 强同意（"Apollo program"） | 同意 | 同意（Levine 中位 2030） | 中立（PI 是 cross-embodiment） | 不同意（PI 是 brain 玩家） |
| **王兴兴 (宇树)** | 同意（"前夜"，1-2 年到 ChatGPT 时刻） | 同意 | 同意 | 同意 | 不同意（自家做 G1） |
| **王鹤 (银河通用)** | 中立（5-10 年才能"什么都干"；不讲 AGI） | 同意 | 不同意（"5-10 年"才能 anything） | 中立（强调实用） | 不同意 |
| **Vincent Vanhoucke (DeepMind→Waymo)** | 同意（Gemini Robotics 推 1.5） | 同意 | 中立 | 中立（不局限双足） | 不同意 |
| **Yann LeCun** | 强不同意（"LLM 5 年内 useless"） | 不同意 | 不同意 | 中立 | 强不同意 |
| **Marc Raibert (Boston Dynamics)** | 同意 | 同意（"工厂先行"） | 不同意（"家用还要等"） | 不同意（"形态不一定双足"） | 中立 |

**矩阵的启示**：

- 在 ①②③ 上"乐观一致 + 时间表激进"的只有 **Brett Adcock**。
- 在 ④ 上唯一公开"不必须双足"的顶尖人物是 **Marc Raibert**。
- 在 ⑤ 上 **没有任何一个一线 player 押注 Tesla 会赢**——这是非常显著的"业内共识"。Adcock 公开说 Figure 的 Helix 比 OpenAI 强；Skild、PI 走 brain 路线绕过特斯拉硬件优势；中国阵营自带物美价廉的供应链；Boston Dynamics 与现代汽车深度绑定。
- **a16z 内部 Casado vs Hsu 的张力**是市场最重要的"内部声音"：押注但承认泡沫。
- **王鹤 vs Adcock** 的对比是中美核心分歧——王鹤强调"实用、能干活、5-10 年"；Adcock 强调"通用、家用、10 年内"。

---

## 10 条最重要引语（按"穿透力"排序）

1. **Brett Adcock**（Time Oct 2025）："Within 10 years, every home will have a humanoid."（最激进的家用预测；目标 4 年内出货 10 万台；BotQ 工厂 100 万/年）
2. **Sergey Levine**（Dwarkesh Podcast Sept 2025）："It's more like the Apollo program than it is a science experiment ⋯ 2025 is a better year than 2009."（最简洁概括"拐点已到"）
3. **Yann LeCun**（Oct 27 2025）："Large Language Models will become useless within five years."（最激进的"反 VLA-LLM"立场，并已用 $1B 押注 AMI Labs）
4. **Martin Casado**（a16z, Non-Consensus Investing 对谈）："In robotics, humanoids are probably one of the most hyped areas where valuations get crazy before there's any revenue."（最重要的"内部清醒话"——出自 a16z 自己）
5. **王兴兴**（21 世纪经济报道 8/9/2025）："机器人数据关注度有点太高了，最大问题在模型 ⋯ 当前行业常见的 VLA 模型属于傻瓜式架构。"（中国一线最尖锐的技术路线判断）
6. **Marc Raibert**（Digitimes 4/2025）："It'll be in factories first, I don't think it'll be in homes for a while ⋯ what really makes a thing human-like is its intelligence, its perception."（最反"必须双足 + 家用"hype 的资深声音）
7. **王鹤**（36Kr 涌现专访）："具身智能距离什么活儿都能干可能需要五年到十年的时间 ⋯ 特别不建议去讲具身的 AGI。"（中国创业者最务实的 timeline）
8. **Oliver Hsu**（a16z, Jan 13 2026）："Real-world deployments of humanoid systems are still largely confined to demos and pilot programs."（a16z 自己写的"皇帝新衣"判断）
9. **Andrej Karpathy**（YC AI Startup School 6/16/2025）："Today's AI is missing critical brain structures like the hippocampus, amygdala, and cerebellum ⋯ AI models are 'ghosts' of human behavior."（最深刻的"embodiment 缺失"批评）
10. **Joel Jang**（NVIDIA GEAR, blog 2/6/2026）："Generating pixels is the only way for humans to verify that the model truly understands ⋯ the fundamental bottleneck for Physical AGI is data scarcity."（最清晰的"World Model + 人类数据"路线宣言）

---

## 一线信息源附录（按人物）

### 美国创业者

- **Brett Adcock (Figure)**：[X @adcock_brett](https://x.com/adcock_brett)；[Time Oct 2025](https://www.businesstoday.in/tech-today/news/story/humanoids-cost-as-much-as-an-suv-and-could-soon-replace-humans-brett-adcock-tells-nikhil-kamath-501039-2025-11-06)；[Humanoids Daily: Helix 02 / End of C++](https://www.humanoidsdaily.com/news/the-end-of-c-brett-adcock-on-helix-02-and-figure-s-path-to-room-scale-autonomy)；[Shawn Ryan Show transcript](https://singjupost.com/figure-ai-ceo-brett-adcocks-interview-shawn-ryan-show-transcript/)。
- **Bernt Bornich / Eric Jang (1X)**：[1X NEO 官页](https://www.1x.tech/discover/neo-home-robot)；[1X World Model](https://www.1x.tech/discover/1x-world-model)；[Eric Jang blog "As Rocks May Think" 2/4/2026](https://evjang.com/2026/02/04/rocks.html)；[Eric Jang talks 页](https://evjang.com/talks/)。
- **Jeff Cardenas (Apptronik)**：[Automate.org Industry Insights](https://www.automate.org/robotics/industry-insights/apptroniks-next-humanoid-will-debut-this-year)；[Humanoids Daily Jabil 报道](https://www.humanoidsdaily.com/news/apptronik-gears-up-apollo-humanoid-production-with-jabil-partnership-teases-upgrades)；[CNBC Feb 13 2025: Google 350M raise](https://www.cnbc.com/2025/02/13/tesla-humanoid-robots-rival-apptronik-350-million-funding-round-google.html)。
- **Jonathan Hurst (Agility)**：[Stanford 4/9/2025 talk](https://src.stanford.edu/src-events/humanoids-from-the-warehouse-to-your-house)；[imeche.org 访谈](https://www.imeche.org/news/news-article/it-s-a-major-inflection-point-for-humanity-agility-robotics-co-founder-jonathan-hurst)；[Robot Report Digit V5](https://www.therobotreport.com/agility-robotics-jonathan-hurst-to-discuss-humnaoids-robotics-summit-keynote/)。
- **Geordie Rose (Sanctuary AI)**：[ExperienceFlow 11/24/2025 任命公告](https://www.businesswire.com/news/home/20251124233288/en/)；[The Logic 大读](https://thelogic.co/news/the-big-read/geordie-rose-sanctuary-ai-interview/)。注意 Rose 11/2024 已辞任 Sanctuary CEO，由 James Wells 代任。
- **Karol Hausman / Sergey Levine / Chelsea Finn / Lerrel Pinto (PI / Stanford / NYU)**：[Dwarkesh Sept 2025](https://www.dwarkesh.com/p/sergey-levine)；[π0 blog](https://www.pi.website/blog/pi0)；[π0.5 blog](https://www.pi.website/blog/pi05)；[Chelsea Finn YC 6/17/2025 talk](https://www.podcosmos.com/ycombinator/ai-startup-school/chelsea-finn-building-robots-that-can-do-anything)；[Sergey Levine substack "Promise of Generalist Robotic Policies"](https://sergeylevine.substack.com/p/the-promise-of-generalist-robotic)；[TechCrunch 4/16/2026 PI](https://techcrunch.com/2026/04/16/physical-intelligence-a-hot-robotics-startup-says-its-new-robot-brain-can-figure-out-tasks-it-was-never-taught/)；[Lerrel Pinto Bloustein 讲座页](https://bloustein.rutgers.edu/guest-speaker-lerrel-pinto-robot-data-is-not-enough-data/)。
- **Deepak Pathak (Skild AI)**：[Skild blog: Building the general-purpose robotic brain](https://www.skild.ai/blogs/building-the-general-purpose-robotic-brain)；[BusinessWire 1/14/2026 $1.4B raise](https://www.businesswire.com/news/home/20260114335623/en/Skild-AI-Raises-$1.4B-Now-Valued-Over-$14B)；[The Robot Report Skild $1.4B raise](https://www.therobotreport.com/skild-ai-raises-1-4b-building-omni-bodied-robot-skild-brain/)；[Sources by Alex Heath 访谈](https://sources.news/p/skild-ai-ceo-robotics-brain-davos)。
- **Marc Raibert (Boston Dynamics 创始人 / RAI Institute)**：[Digitimes 4/1/2025](https://www.digitimes.com/news/a20250401PD202/)；[Boston Globe 7/29/2025](https://www.bostonglobe.com/2025/07/29/business/boston-dynamics-robot-museum-marc-raibert/)；[E&T 访谈 8/5/2025](https://eandt.theiet.org/2025/08/05/interview-marc-railbert-executive-director-robotics-and-ai-institute-and-spot-dog-0)；[Lex Fridman #412 transcript](https://lexfridman.com/marc-raibert-transcript/)；[TechCrunch 2/5/2025: BD-RAI 合作](https://techcrunch.com/2025/02/05/boston-dynamics-joins-forces-with-its-former-ceo-to-speed-the-learning-of-its-atlas-humanoid-robot/)。

### 学者 / DeepMind / OpenAI / NVIDIA

- **Vincent Vanhoucke (DeepMind→Waymo)**：[Gemini Robotics arxiv 2503.20020](https://arxiv.org/abs/2503.20020)；[Gemini Robotics 1.5 tech report](https://storage.googleapis.com/deepmind-media/gemini-robotics/Gemini-Robotics-1-5-Tech-Report.pdf)；[Whymo medium](https://vanhoucke.medium.com/whymo-6926a65928f4)。
- **Jim Fan / Yuke Zhu / Joel Jang (NVIDIA GEAR)**：[Sequoia Training Data Podcast: Jim Fan](https://sequoiacap.com/podcast/training-data-jim-fan/)；[GR00T N1 newsroom Mar 2025](https://nvidianews.nvidia.com/news/nvidia-isaac-gr00t-n1-open-humanoid-robot-foundation-model-simulation-frameworks)；[arxiv 2503.14734 GR00T N1](https://arxiv.org/abs/2503.14734)；[NVIDIA GR00T N1.6 page](https://research.nvidia.com/labs/gear/gr00t-n1_6/)；[Joel Jang World Models blog 2/6/2026](https://joeljang.github.io/world-models-for-robotics)。
- **Pieter Abbeel**：[Covariant insights blog](https://covariant.ai/insights/the-future-of-robotics-robotics-foundation-models-and-the-role-of-data/)；[Robot Brains podcast](https://www.linkedin.com/posts/covariant-ai_foundation-models-for-robotic-piece-picking-activity-7048703363017801728-uWDh)；[Eboona bio 2026](https://eboona.com/ai-startup-founder/pieter-abbeel/)。
- **Russ Tedrake (TRI)**：[TRI LBM 1 论文页](https://toyotaresearchinstitute.github.io/lbm1/)；[Toyota newsroom 8/20/2025](https://pressroom.toyota.com/ai-powered-robot-by-boston-dynamics-and-toyota-research-institute-takes-a-key-step-towards-general-purpose-humanoids/)；[Robotics 24/7 报道](https://www.robotics247.com/article/boston_dynamics_toyota_research_institute_demonstrate_large_behavior_model_powering_atlas_humanoid_robot/)。
- **Andrej Karpathy**：[YC AI Startup School 6/16/2025 transcript](https://www.scribd.com/document/878835610/Andrej-Karpathy-YC-AI-Startup-School-June-16-2025)；[Latent Space 转写](https://www.latent.space/p/s3)；[Inferencebysequoia substack](https://inferencebysequoia.substack.com/p/andrej-karpathys-software-30-and)。
- **Yann LeCun**：[Royfactory 转述 10/2025](https://royfactory.net/posts/ai/202510/yann-lecun-2025-llm-doomed-jepa-world-model/)；[Meta I-JEPA blog](https://ai.meta.com/blog/yann-lecun-ai-model-i-jepa/)；[MIT Technology Review 1/22/2026 AMI Labs](https://www.technologyreview.com/2026/01/22/1131661/yann-lecuns-new-venture-ami-labs/)；[arxiv 2403.00504](https://arxiv.org/abs/2403.00504)。

### 中国创业者

- **王兴兴 (宇树)**：[人民日报专访 8/13/2025](https://www.rmlt.com.cn/2025/0813/737592.shtml)；[21 世纪经济报道 8/9/2025](https://www.21jingji.com/article/20250809/herald/fecc404938f03df050143f46e4922853.html)；[21 世纪经济报道 9/24/2025: 为何坚持开源](https://www.21jingji.com/article/20250924/herald/f1a537b480a7c6ad8da95f679a15e38d.html)；[新京报 2026 超人类速度](https://www.bjnews.com.cn/detail/1773820412129393.html)；[太平洋科技专访](https://www.pconline.com.cn/focus/1884/18841703.html)；[智东西演讲实录](https://zhidx.com/p/496440.html)。
- **彭志辉 / 闫维新 (智元)**：[新浪财经 GO-1 3/10/2025](https://finance.sina.com.cn/roll/2025-03-10/doc-inepeiim6349836.shtml)；[东方财富 5/7/2025: 实用主义路线](https://caifuhao.eastmoney.com/news/20250507164443347841990)；[东方财富 10/27/2025: 智元安踏战略合作](https://caifuhao.eastmoney.com/news/20251027191915601865430)；[知乎 Z Waves 稚晖君](https://zhuanlan.zhihu.com/p/1905750647954990545)。
- **王鹤 (银河通用)**：[36Kr 涌现专访](https://36kr.com/p/3350684885707399)；[新京报演讲 7/2025](https://m.bjnews.com.cn/detail/1753150473129589.html)；[启明创投 启明星专访](https://www.qimingvc.com/cn/news/)；[半月谈 12/25/2025](http://www.banyuetan.org/ppzx/detail/20251225/1000200033137541766643655810903008_1.html)；[新浪财经 6/28/2025](https://finance.sina.com.cn/stock/roll/2025-06-28/doc-infcrmwf9464016.shtml)；[知乎 Z Waves 王鹤](https://zhuanlan.zhihu.com/p/1914070278302045431)。
- **陈建宇 (星动纪元)**：[新浪财经 8/5/2025: 商业化路径](https://finance.sina.com.cn/stock/t/2025-08-05/doc-infixiyu9317384.shtml)；[元璟资本 对话](https://startup.aliyun.com/info/1088933.html)；[科技行者 8/27/2024](https://www.techwalker.com/2024/0827/3159815.shtml)；[机器人大讲堂](https://www.leaderobot.com/news/4920)；[知乎 2026 商业新愿景](https://zhuanlan.zhihu.com/p/2005610457357129461)。
- **张巍 (逐际动力)**：[36Kr 首发 2亿融资](https://36kr.com/p/2477042139240580)；[动点科技 11/2023 张力加盟](https://cn.technode.com/post/2023-11-07/limx-dynamics-ai-zhangli-panjia/)；[百度百科条目](https://baike.baidu.com/item/%E5%BC%A0%E5%B7%8D/63753106)；[逐际动力官网新闻](https://www.limxdynamics.com/news)。
- **它石智航 (王潜 / 陈亦伦 / 李震宇 / 丁文超)**：[qbitai 3/2025: 1.2亿美元天使](https://www.qbitai.com/2025/03/267764.html)；[网易 4.55亿美金 A 轮](https://www.163.com/dy/article/KQL8JBQN0556LVOG.html)；[财经客户端](https://www.mycaijing.com/article/detail/544321?source_id=40)；[中国日报 3/26/2025](https://cn.chinadaily.com.cn/a/202503/26/WS67e3cbd9a31008317a2aecc5.html)。

### 投资机构

- **a16z**：[America Cannot Lose the Robotics Race 9/26/2025](https://a16z.com/america-cannot-lose-the-robotics-race/)；[Toward a Horizontal Robotics Platform](https://a16z.com/toward-a-general-purpose-robotics-platform/)；[The Physical AI Deployment Gap 1/13/2026 (Oliver Hsu)](https://www.a16z.news/p/the-physical-ai-deployment-gap)；[Frontier Systems for the Physical World](https://a16z.com/frontier-systems-for-the-physical-world/)；[Is Non-Consensus Investing Overrated? (Casado quote)](https://www.a16z.news/p/is-non-consensus-investing-overrated)；[Tesla's Road Ahead podcast](https://a16z.com/podcast/teslas-road-ahead-the-bitter-lesson-in-robotics/)；[Fei-Fei Li World Models podcast](https://a16z.com/podcast/fei-fei-li-world-models-and-the-multiverse/)。
- **Sequoia**：[2026: This is AGI](https://sequoiacap.com/article/2026-this-is-agi/)；[AI Ascent 2025](https://sequoiacap.com/article/ai-ascent-2025/)；[Pat Grady deep analysis](https://digidai.github.io/2025/11/23/pat-grady-sequoia-capital-co-steward-ai-enterprise-software-deep-analysis/)；[Sonya Huang deep analysis](https://digidai.github.io/2025/11/24/sonya-huang-sequoia-capital-ai-application-layer-bet-deep-analysis/)；[Jim Fan podcast](https://sequoiacap.com/podcast/training-data-jim-fan/)。
- **Lux Capital / Founders Fund**：[Lux Q1 2024 Report](https://www.luxcapital.com/news/lux-q1-2024-report)；[Lux 公司组合](https://www.luxcapital.com/companies)；[TechFunding News: PI $1B raise Founders Fund](https://techfundingnews.com/physical-intelligence-1b-raise-11b-valuation-founders-fund-lightspeed/)。
- **SoftBank / NVIDIA NVentures**：[UMD News: SoftBank $500M to Skild](https://www.cs.umd.edu/article/2025/01/softbank-invest-500-million-robotics-startup-skild-ai)；[CNBC 2/13/2025: Google + NVIDIA to Apptronik](https://www.cnbc.com/2025/02/13/tesla-humanoid-robots-rival-apptronik-350-million-funding-round-google.html)。
- **红杉中国 / 高瓴**：[36Kr: 红杉 + 高瓴联手投机器人](https://eu.36kr.com/zh/p/3547970791420033)；[阿里云: 红杉天使轮](https://startup.aliyun.com/info/1053181.html)；[知乎 2025 Q2 投资榜](https://zhuanlan.zhihu.com/p/1941205381494871302)；[阿里云: 它石智航 4.55亿美金破纪录](https://startup.aliyun.com/info/1093153.html)。

### 关键报道（行业整体）

- [Brett Adcock × Nikhil Kamath 11/6/2025: 'humanoid 如 SUV 一样贵'](https://www.businesstoday.in/tech-today/news/story/humanoids-cost-as-much-as-an-suv-and-could-soon-replace-humans-brett-adcock-tells-nikhil-kamath-501039-2025-11-06)
- [Humanoids Daily: Adcock Triad $1M/月一线快讯](https://www.humanoidsdaily.com/news/the-adcock-triad-inside-the-1m-a-month-sprint-to-general-robotics)
- [Humanoids Daily: Apptronik 节制 vs Hype](https://www.humanoidsdaily.com/news/substance-over-hype-inside-apptronik-s-measured-push-for-the-next-apollo)
- [Electrek 12/30/2025: Musk 2025 五大预测落空](https://electrek.co/2025/12/30/elon-musk-top-5-tesla-predictions-2025-didnt-happen/)
- [Rest of World: China leads, Tesla still has a shot](https://restofworld.org/2026/china-tesla-robot-race/)
- [Merics: Embodied AI China's ambitious path](https://merics.org/en/report/embodied-ai-chinas-ambitious-path-transform-its-robotics-industry)
- [Interesting Engineering: 1X NEO factory 100,000 by 2027](https://interestingengineering.com/ai-robotics/1x-humanoid-robot-neo-factory-california)

---

## 报告价值与下一步建议

**给 PE 老板看的真正价值**：
1. **认识到"乐观一致"是错觉**。a16z、Sequoia 重注 robotics，但 a16z 自己写 deployment gap、Casado 警告估值疯狂——这种"内部矛盾"才是真实的尽调信号。
2. **中美核心分歧线非常清晰**：美国押注真机 + 通用 brain（PI/Figure/Skild），中国押注仿真合成 + B 端实用主义（银河通用/星动纪元/智元）。两条路在 2026–2028 会有一次"交叉验证"。
3. **三个高确信信号**：
   - 工业/物流 2026–2027 进入 meaningful PMF：Adcock、Cardenas、Hurst、王兴兴、陈建宇全部同意。
   - "通用大脑"会跑出 1-2 个赢家（PI、Skild、Figure、智元、银河通用），不会有 10 个赢家。
   - **没有任何一线 player 押注 Tesla 会赢**——这是 PE 应认真对待的"业内共识"，特别在评估 Tesla 估值时。
4. **三个高分歧信号**：
   - 世界模型 vs 端到端 VLA：未来 18 个月会决出。
   - 双足 vs 多形态：可能是品牌叙事远大于技术必要性。
   - C 端家用 2030 是否成立：Adcock/Bornich 强烈 yes，王鹤/Raibert 强烈 no。

报告应在论证中始终引用具体人物 + 时间 + 出处，避免"行业普遍认为"这种没有出处的话术。
