# Deep Research Prompt 02 — Adversarial finalist review
Status: DRAFT v0.2 — run only after the owner has approved CHARTER.md and RESEARCH_PROTOCOL.md and an explicit shortlist with finalist IDs, each recorded in DECISION_LOG.md.

## Binding method
Read CHARTER.md, RESEARCH_PROTOCOL.md and DECISION_LOG.md first. RESEARCH_PROTOCOL.md is the only source of definitions (arms A–D, LLM roles, reference-outcome provenance E/I/X, primary endpoint, exploratory vs confirmatory) and of the review and preregistration rules (§§ 5–6); where this prompt conflicts with them, they govern and you report the conflict.

Take the approved finalists, their candidate cards, sources and proposed G0–G2 verdicts. Treat the proposed mechanism as unproven until it shows incremental value over strong baselines, while refusing to reject a domain solely because competitors exist.

## For each finalist
1. Reconstruct the exact operational workflow, error costs, rule volatility and buying context; separate verified observations from hypotheses.
2. Review production approaches — best incumbents, open source, standards, DSLs and rules/constraint/workflow engines, LLM plus tools, structured schema plus host code — from their own documentation, and state known evidence limits.
3. Choose arm C by fit (RESEARCH_PROTOCOL § 5) and record why other incumbent classes were not chosen; if no incumbent materially applies, record the search. Never pick a C that is easy to beat.
4. Deepen the G1 paper probe: name mechanism M; for specific counterexamples (exception, conflict, rule change), show where B and C need brittle per-use reimplementation, extra edit sites, missing static checks or weaker auditability, and which endpoint that moves. Label each claimed difference as novel semantics, novel syntax, existing library or integration.
5. Substantiate the reference-outcome path: provenance E or I, who produces and adjudicates labels and when, leakage risks (including public worked examples a model may have memorised), and cost for one solo AI-assisted founder. Confirm or downgrade the provisional G2.
6. Draft experiments/[candidate]/PLAN.md following RESEARCH_PROTOCOL § 6: arms A–D with the LLM role per stage (including build-aid-only where that is the owner's chosen scope), comparable effort and a baseline-steelmanning pass, the D-without-M ablation, one primary endpoint with guardrails, N, uncertainty method and the smallest meaningful difference, and a success rule and kill condition to be frozen before holdout exposure. Mark the experiment exploratory if it cannot detect a meaningful difference.
7. Record early commercial evidence (demand signals, incumbent pricing, buyer reachability, regulatory or data barriers) as a commercial hypothesis, never as validation.
8. Give one suggested recommendation in gate vocabulary — GO to preregistration, HOLD naming the missing evidence and one bounded next action, or STOP the semantic thesis for this finalist — with a reversible rationale. This is a proposal, not a gate decision.

Deliver an evidence ledger with links and dates, the strongest counterargument, the suggested next work item, and the exact fact that would change each recommendation.

Do not implement a DSL or compiler, alter the charter or protocol, approve gates, fabricate interviews, or imply market validation from technical performance.
