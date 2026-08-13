# Bilingual One‑page Summary / 双语一页摘要

| 中文（左） | English (right) |
|---|---|
| TL;DR：把 LLM 当“像人”的启发工具，但以机器级约束治理它（显式角色、边界契约、熔断与审计）。 | TL;DR: Treat LLMs heuristically like people for design intuition, but govern them with machine‑grade constraints (explicit roles, boundary contracts, circuit breakers, and audits). |
| 适用场景：多步/高风险/跨角色/需自举演进 | Scope: multi-step, high-risk, cross-role, self-bootstrapping systems |
| 五条顶层假设：1) LLM 工程≠传统软件工程；2) 拆启发层/约束层；3) 兼容旧框架；4) 有适用域（Scope Gate）；5) LLM 无自律，靠四支柱兜底。 | Five top assumptions: 1) LLM engineering ≠ traditional SE; 2) separate heuristic & constraint layers; 3) reuse deterministic frameworks; 4) methods have scope gates; 5) LLMs lack self-discipline—rely on four pillars. |
| 四大支柱（P1~P4）：P1 拓扑边界；P2 认知分级；P3 资源熔断；P4 闭环审计。 | Four pillars (P1–P4): P1 Topology & Boundary; P2 Cognitive Tiering; P3 Resource & Circuit Breaker; P4 Closure & Bootstrapping. |
| P1：状态机 + 接口契约 + 禁止越权。 | P1: state machines + interface contracts + forbidden actions. |
| P2：Tier1 填表级 / Tier2 推理级 / Tier3 创造级。 | P2: Tier1 (template), Tier2 (reasoning), Tier3 (creative). |
| P3：Token预算、锚点回显、熔断阈值。 | P3: token budgets, anchor echoing, circuit-break thresholds. |
| P4：辩证官 + 盲抽样 + 全链路审计。 | P4: critic(s), blind sampling, full‑chain audit. |
| 典型落地顺序：P1 → P2 → P4 (反馈) → P3（按级差异化熔断）。 | Typical rollout: P1 → P2 → P4 (feedback) → P3 (tiered circuit breakers). |
| 快速 checklist：识别高风险流程 → 定边界 → 分级 → 熔断设置 → 启动审计。 | Quick checklist: identify risky flows → define boundaries → tier tasks → set circuit breakers → start audits. |

> 注：这是为快速阅读设计的摘要表。完整论述请参见 `zh/硅基序纲领.md` 与 `en/Silicon-Based-Order-Manifesto.md`。
