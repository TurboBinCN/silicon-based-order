# Silicon‑Based Order / 硅基序纲领

[中文 (原文)](./zh/硅基序纲领.md) · [English (translation)](./en/Silicon-Based-Order-Manifesto.md) · [Bilingual one‑page summary](./docs/bilingual-summary.md)

TL;DR

- Treat LLMs heuristically like people for design intuition, but govern them with machine‑grade constraints: explicit roles, boundary contracts, circuit breakers, and audit loops.

阅读须知（必看）

> 这是一份**范式 idea-file**。目的同 `llm-wiki.md`：传达顶层思想，供你的 LLM Agent（Codex / Claude / OpenCode / Pi…）在协作中实例化细节。**它不绑定特定实现**，是一份可被任意 Agent 复用、并随你的领域演进的思想地图。
>
> **v1.3 新增**（治理内化对接 · 2026-08-09）：
> - **信息治理维度**（双支柱：组织治理 × 信息治理）
> - **两维度分层**（主权通道 G vs 效用通道 M）
> - **两层闭环**（治理规则层 ↔ 执行底座）
> - **碳硅迁移链**（人类组织治理 → 数字公司治理映射路径）
> - **过滤口诀**（跨域判据两问）
> - **四支柱细化**（授权铁律/三元风险参数/风险梯度链/全链路留痕）
> - **唯一治理承重主梁：硅基版责不可授**（从"LLM 无自律"推导的核心治理推论）

⚠️ 阅读须知（必看）

1. 这份文稿底层逻辑是给 AI 看的规整规则体系，人类硬啃容易看得头昏脑涨、一头雾水。
2. 此文档因信息密度过高，叙事结构按照结论前置后举证的方式，不适合人类阅读，请喂给你的 AI，让它帮你理解。

省事最优解：整篇复制丢给大模型，让它帮你梳理、翻译大白话、按需拆解知识点，有针对性提问效率更高！

提示示例（新手可直接复制粘贴发给 AI）

```
你现在是一位资深的AI技术布道师兼企业内训专家。我接下来会发给你一份关于“LLM系统工程方法论”的原始文档。请你帮我完成以下两项任务：

**任务一：为原始文档编写一份“新手引导与使用说明”（必须放在文档最开头）**
因为原始文档里的概念比较硬核，为了让团队成员（尤其是新手）能立刻看懂并上手，请在文档开头增加一段引导语，并直接提供以下三个“示例提问”，告诉���家可以直接复制这些问题发给AI：

1. 用大白话完整讲解这套 LLM 系统工程方法论；
2. 提炼四大支柱的落地流程；
3. 简化成团队可直接使用的开发规范。

**任务二：对文档中的“四大支柱”进行“人话翻译”**
原始文档中的四大支柱（拓扑边界、认知分级、强类型接口、防循环依赖）概念太抽象了，像机器码一样难以理解。请你务必在文档中为这四大支柱增加一个“大白话翻译”模块。
要求：

- 摒弃生涩的学术词汇，用最接地气的语言解释它们的根本性原理。
- 必须结合生活比喻或真实的业务场景（比如：把“拓扑边界”翻译成“给AI发工牌定规矩”等），让团队成员看一眼就能get到核心点。

如果你准备好了，请回复“收到”，我接下来会把原始文档发给你。
```

Why this README was updated (style reference: Karpathy gist)

- Short, scannable TL;DR on top
- Clear one‑page summary for quick decisions
- Practical checklist for engineers to apply the method
- Fast language switching links

---

One‑page condensed summary (快速一页摘要)

See the bilingual one‑page: `docs/bilingual-summary.md` for a side‑by‑side short summary in Chinese and English.

Quick application checklist

1. Identify high‑risk flows (multi‑step / cross‑role / high‑impact).  
2. Define P1 (Topology & Boundary): state machine, inputs/outputs, forbidden actions, ownership.  
3. Classify tasks under P2 (Cognitive Tiering): Tier1 (templates) / Tier2 (reasoning) / Tier3 (creative).  
4. Configure P3 (Resource & Circuit Breaker): token budgets, chunking, anchor echo frequency, emergency stop thresholds.  
5. Enable P4 (Closure & Bootstrapping): assign a critic (辩证官), auditing cadence, blind‑sampling checks, feedback to P1/P2.

---

Files of interest

- `zh/硅基序纲领.md` — original Chinese idea‑file (primary).  
- `en/Silicon-Based-Order-Manifesto.md` — English translation (reader‑oriented).  
- `docs/bilingual-summary.md` — one‑page, side‑by‑side bilingual summary for quick reading.  
- `docs/APPLY.md` — practical step‑by‑step checklist for engineers.  

Contribute / Feedback

- Prefer edits: open a PR. For translation changes, label `translation`.  
- Want a full bilingual side‑by‑side of the entire paper (very large)? Tell me and I will add it as `docs/bilingual-full.md` (warning: very long).

License & Author

- MIT — see `LICENSE`.  
- Author: TurboBinCN

---

If you'd like, I can:  
- publish a GH‑Pages site for nicer language toggling and readable layout;  
- generate a full side‑by‑side bilingual file (large);  
- add badges or a small CSS for readability.
