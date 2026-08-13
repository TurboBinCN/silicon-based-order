# Silicon‑Based Order / 硅基序纲领

> 把 LLM 当"像人"的启发式来设计，但按机器级约束来治理。
> Treat LLMs heuristically like people for design intuition, but govern them with machine‑grade constraints.

**[中文原稿](./zh/硅基序纲领.md)** · **[English translation](./en/Silicon-Based-Order-Manifesto.md)**

---

## 中文

### 这是什么

一份面向 **LLM 系统工程**的方法论宣言（范式 idea-file）。核心一句话：

> **把它当人看，但按机器管。用意给直觉，执行给严谨。**

大多数人把 LLM 当"高级搜索/补全工具"来用，于是觉得它是玄学、靠运气。这套方法的认知跃迁是：**LLM 不是确定性编译器，它"像一个人"（但只是像）**——用"像人"的启发式视角获得设计直觉，再用工程约束把它治理成一家"数字公司"：员工没有肉体，只有算力与概率。

### 核心框架速览

- **双视图层**：启发层（拟人是设计思考工具）与约束层（执行只信任显式约束：状态机、边界契约、熔断、审计）**必须拆分**，二者永不混战。
- **五条顶层假设**：
  1. LLM 工程 ≠ 传统软件工程，本质是「数字虚拟企业治理 + 系统工程」
  2. 启发层 / 约束层必须拆分
  3. 旧框架不抛弃，确定性组件照用
  4. 方法论不万能，条件式成立（Scope Gate）
  5. LLM 无自律，靠四支柱兜底
- **唯一治理承重主梁**：**硅基版责不可授**——AI 不会主动夺权，但人会主动放权；治理主权（目的锚定 / 护栏规则 / 高危否决 / 审计闭环）必须留在人类手中。
- **四大支柱**：
  - **P1 拓扑边界**（Topology & Boundary）— "你是谁、你在哪"：状态机 + 边界契约 + 禁止越权，消除语义歧义
  - **P2 认知分级**（Cognitive Tiering）— "你怎么想"：Tier1 填表 / Tier2 推理 / Tier3 创造，按复杂度差异化约束
  - **P3 资源与熔断**（Resource & Circuit Breaker）— "你的命脉"：Token 熔断 + 上下文健康监控（距离衰减 / 语义漂移 / 锚点稀释）
  - **P4 闭环与自举**（Closure & Bootstrapping）— "谁监督你"：辩证官 + 反溯审计，形成负反馈回路
- **企业映射表**：把"管理一家公司"落到系统——角色、流程、边界、反馈、顶层锚点，一一对应工程概念。

### 什么时候用它（Scope Gate）

> 如果任务是**确定性输出、单一职责、无发散风险**，一句一致 Prompt 即可；当它**多步 / 概率 / 高副作用 / 需要自举进化**时，升级到四支柱。**杠杆是好锤子，但锤子要分场景，不能逢事就砸。**

### 怎么读这套文档

正文是**结论前置、高密度**的 idea-file，写给 LLM Agent 读的，人类硬啃容易头昏脑涨。省事最优解：**把整篇文档复制丢给大模型**，让它帮你梳理、翻译大白话、按需拆解知识点，有针对性提问效率更高。

提示示例（新手可直接复制发给 AI）：

```
You are a senior AI evangelist and corporate trainer. I will paste a raw document about an
"LLM systems engineering methodology." Please help me with two tasks:

Task 1: Write a "Beginner Guide & Usage Instructions" and place it at the very top of the source
document. The original is dense and conclusion-first; make an approachable intro and include
these three example questions people can copy and send to an AI:
  1. Explain this LLM systems engineering methodology in plain language.
  2. Extract the four pillars and provide a practical step-by-step workflow to implement them.
  3. Convert the methodology into a concise developer checklist the team can adopt.

Task 2: Translate the "Four Pillars" into plain language. For each pillar, provide:
(a) a plain-language explanation avoiding academic jargon;
(b) a short real-world metaphor or business scenario (e.g., "Topology & Boundary -> Give the AI
a work badge that defines its permissions");
(c) one practical starter action the team can implement in 1-2 hours.

If you are ready, reply with "ACK" and I will paste the document.
```

### 文件导航

| 文件 | 说明 |
|---|---|
| `zh/硅基序纲领.md` | **中文原稿**（唯一事实来源，内容以此为准） |
| `en/Silicon-Based-Order-Manifesto.md` | 英文翻译（字面直译风格） |

### 版本更新

**v1.3（2026‑08‑09）新增：**
- 信息治理维度（双支柱：组织治理 × 信息治理）
- 两维度分层（主权通道 G vs 效用通道 M）
- 两层闭环（治理规则层 ↔ 执行底座）
- 碳硅迁移链（人类组织治理 → 数字公司治理映射路径）
- 过滤口诀（跨域判据两问）
- 四支柱细化（授权铁律 / 三元风险参数 / 风险梯度链 / 全链路留痕）
- 唯一治理承重主梁：硅基版责不可授（从"LLM 无自律"推导的核心治理推论）

### 贡献 / 许可

- 编辑请开 PR；翻译变更请加 `translation` label。
- MIT — 见 [LICENSE](./LICENSE)。作者：TurboBinCN

---

## English

### What this is

A **paradigm idea-file / manifesto for LLM systems engineering**. The core claim:

> **Treat LLMs heuristically like people, but govern them with machine-grade constraints.**
> Use the analogy for design intuition; use hard constraints for execution.

Most people use LLMs as "fancy search/autocomplete" — which is why it feels like luck or voodoo.
The core shift: **an LLM is not a deterministic compiler; it "is like a person" (but only like).**
Use the human heuristic to build design intuition, then govern it with engineering constraints as
if running a **digital company**: employees with no body, only compute and probability.

### The framework at a glance

- **Two view layers**: the Heuristic layer (anthropomorphism is a design-thinking tool) and the
  Constraint layer (execution trusts only explicit constraints: state machines, boundary
  contracts, circuit breakers, audits) **must be kept separate**.
- **Five top-level assumptions**:
  1. LLM engineering ≠ traditional software engineering — it is "digital company governance + systems engineering"
  2. The heuristic / constraint layers must be partitioned
  3. Keep old frameworks; reuse them for deterministic components
  4. The methodology is not universal — it holds conditionally (Scope Gate)
  5. LLMs lack self-discipline — the four pillars are the safety net
- **The single governing beam**: **Responsibility must not be delegated** — AI will not seize
  power, but humans will voluntarily hand it over; governance sovereignty (purpose anchoring,
  guardrail rules, high-risk veto, audit loops) stays with humans.
- **The four pillars**:
  - **P1 Topology & Boundary** — "Who are you, where are you": state machines + boundary contracts + forbidden actions
  - **P2 Cognitive Tiering** — "How do you think": Tier1 template / Tier2 reasoning / Tier3 creative
  - **P3 Resource & Circuit Breaker** — "Your lifelines": token circuit breakers + context-health monitoring
  - **P4 Closure & Bootstrapping** — "Who supervises you": critic + traceable audit, a negative feedback loop
- **Enterprise mapping**: map "running a company" onto the system — roles, processes, boundaries,
  feedback, and top-level anchors each map to an engineering concept.

### When to use it (Scope Gate)

> If a task is **deterministic, single-responsibility, with no divergence risk**, a single
> consistent prompt is enough. Escalate to the four pillars when it is **multi-step / probabilistic
> / high-impact / needs self-bootstrapping**. A lever is good; a hammer must match the task — don't
> swing it at everything.

### How to read this repo

The manifesto is **conclusion-first and dense**, written to be read by an LLM Agent. Humans may
find it overwhelming. The best move: **paste the whole document into an LLM** and ask it to
explain, translate into plain language, or break it into pieces on demand.

Example prompt (copy & paste):

```
You are a senior AI evangelist and corporate trainer. I will paste a raw document about an
"LLM systems engineering methodology." Please help me with two tasks:

Task 1: Write a "Beginner Guide & Usage Instructions" and place it at the very top of the source
document. The original is dense and conclusion-first; make an approachable intro and include
these three example questions people can copy and send to an AI:
  1. Explain this LLM systems engineering methodology in plain language.
  2. Extract the four pillars and provide a practical step-by-step workflow to implement them.
  3. Convert the methodology into a concise developer checklist the team can adopt.

Task 2: Translate the "Four Pillars" into plain language. For each pillar, provide:
(a) a plain-language explanation avoiding academic jargon;
(b) a short real-world metaphor or business scenario (e.g., "Topology & Boundary -> Give the AI
a work badge that defines its permissions");
(c) one practical starter action the team can implement in 1-2 hours.

If you are ready, reply with "ACK" and I will paste the document.
```

### Files

| File | Description |
|---|---|
| `zh/硅基序纲领.md` | **Original Chinese idea-file** (source of truth) |
| `en/Silicon-Based-Order-Manifesto.md` | English translation (literal style) |

### Changelog

**v1.3 (2026‑08‑09) additions:**
- Information governance dimension (dual pillars: organizational governance × information governance)
- Two-channel layering (sovereignty channel G vs. utility channel M)
- Two-level closed loop (governance rule layer ↔ execution foundation)
- Carbon→silicon migration chain (human-organization governance → digital-company governance)
- A two-question scope filter
- Four-pillar refinements (authorization iron law / three-variable risk parameters / risk gradient chain / full-chain traceability)
- The single governing beam: responsibility must not be delegated

### Contribute / License

- Prefer opening a PR. Label translation changes `translation`.
- MIT — see [LICENSE](./LICENSE). Author: TurboBinCN
