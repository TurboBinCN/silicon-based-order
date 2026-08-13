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
You are a senior AI evangelist and corporate trainer. I will paste a raw document about an "LLM systems engineering methodology." Please help me with two tasks:

Task 1: Write a "Beginner Guide & Usage Instructions" and place it at the very top of the source document. The original is dense and conclusion-first; make an approachable intro and include these three example questions people can copy and send to an AI:
  1. Explain this LLM systems engineering methodology in plain language.
  2. Extract the four pillars and provide a practical step-by-step workflow to implement them.
  3. Convert the methodology into a concise developer checklist the team can adopt.

Task 2: Translate the "Four Pillars" into plain language. For each pillar, provide: (a) a plain-language explanation avoiding academic jargon; (b) a short real-world metaphor or business scenario (e.g., "Topology & Boundary -> Give the AI a work badge that defines its permissions"); (c) one practical starter action the team can implement in 1–2 hours.

If you are ready, reply with "ACK" and I will paste the document.
```

---

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

---

ENGLISH (stacked translation)

README — Quick guide (English)

This repository contains the Silicon‑Based Order manifesto: an LLM systems‑engineering idea file that presents a conclusion‑first, high‑density methodology. The original Chinese source is in `zh/硅基序纲领.md` and an English reader‑oriented translation is available in `en/Silicon-Based-Order-Manifesto.md`.

Quick note — how to read this repo

- The manifesto is written as a paradigm idea‑file: it's intended to be fed to an LLM Agent (Codex / Claude / OpenCode / Pi …) to instantiate concrete implementations. It is not tied to any specific toolkit.
- v1.3 highlights (2026‑08‑09): information governance dimension; two‑channel layering (G: governance, M: management); closed‑loop rule ↔ execution; carbon→silicon mapping; a two‑question scope filter; four‑pillar refinements; core principle: human must retain governance authority.

Important reading note

1. The text is structured conclusion‑first and is dense; reading it directly can be hard for humans. We recommend giving the full document to an LLM and asking it to summarize/translate/extract actionable items.
2. Best practice: paste the whole document into an LLM and ask for a beginner‑friendly guide, a plain‑language translation of the four pillars, and a short developer checklist.

Example prompt (copy & paste)

```
You are a senior AI evangelist and corporate trainer. I will paste a raw document about an "LLM systems engineering methodology." Please help me with two tasks:

Task 1: Write a "Beginner Guide & Usage Instructions" and place it at the very top of the source document. The original is dense and conclusion-first; make an approachable intro and include these three example questions people can copy and send to an AI:
  1. Explain this LLM systems engineering methodology in plain language.
  2. Extract the four pillars and provide a practical step-by-step workflow to implement them.
  3. Convert the methodology into a concise developer checklist the team can adopt.

Task 2: Translate the "Four Pillars" into plain language. For each pillar, provide: (a) a plain-language explanation avoiding academic jargon; (b) a short real-world metaphor or business scenario (e.g., "Topology & Boundary -> Give the AI a work badge that defines its permissions"); (c) one practical starter action the team can implement in 1–2 hours.

If you are ready, reply with "ACK" and I will paste the document.
```

Why this README was updated

- Make onboarding faster for multi‑lingual teams
- Provide a direct “feed-to‑AI” route for high‑density idea files
- Keep README short while linking to full translated sources

Quick checklist (English)

1. Identify high‑risk flows (multi‑step / cross‑role / high‑impact).  
2. Define P1 (Topology & Boundary): state machine, inputs/outputs, forbidden actions, ownership.  
3. Classify tasks under P2 (Cognitive Tiering): Tier1 (templates) / Tier2 (reasoning) / Tier3 (creative).  
4. Configure P3 (Resource & Circuit Breaker): token budgets, chunking, anchor echo frequency, emergency stop thresholds.  
5. Enable P4 (Closure & Bootstrapping): assign a critic (Dialectician), auditing cadence, blind‑sampling checks, feedback to P1/P2.

Files of interest (English)

- `zh/硅基序纲领.md` — original Chinese idea‑file (primary).  
- `en/Silicon-Based-Order-Manifesto.md` — English translation (reader‑oriented).  
- `docs/bilingual-summary.md` — one‑page, side‑by‑side bilingual summary for quick reading.  
- `docs/APPLY.md` — practical step‑by‑step checklist for engineers.  

Contribute / Feedback (English)

- Prefer edits: open a PR. For translation changes, label `translation`.  
- Want a full bilingual side‑by‑side of the entire paper (very large)? Tell me and I will add it as `docs/bilingual-full.md` (warning: very long).

License & Author (English)

- MIT — see `LICENSE`.  
- Author: TurboBinCN

If you'd like, I can:  
- publish a GH‑Pages site for nicer language toggling and readable layout;  
- generate a full side‑by‑side bilingual file (large);  
- add badges or a small CSS for readability.
