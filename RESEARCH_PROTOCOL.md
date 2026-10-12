# Research Protocol
Status: DRAFT v0.1. Read with CHARTER.md. Human owner approves gate progression.

## Unit of search
A micro-workflow, not an industry or product category. Describe it as:
For [specific operator/buyer], given [specific inputs and governing rules], decide or perform [specific action] at [frequency], where wrong outcomes cause [measurable cost], and correctness is established by [independent oracle].

## Stage 1 — discovery
Search at least six substantially different industries. Include sectors outside founder familiarity. Target 20–30 evidence-backed candidates; do not pad results.
Discover from operational manuals, regulations, standards, examples/contracts, GitHub issues, practitioner complaints, open-source code, vendors, buyer evidence. Distinguish original sources from marketing claims.
For each candidate use research/01-discovery/CANDIDATE_TEMPLATE.md. Attach link, access date, applicable publication/version date, quoted or paraphrased source observation, and confidence.

## Stage 2 — shortlist
Screen every candidate for:
G0 (real outcome gap): named operator, concrete inputs -> decision -> action, frequency, and credible evidence of cost, errors, spending or workarounds.
G1 (language plausibility): an explicit domain-specific semantic primitive or invariant that baseline tools represent awkwardly or fail to enforce; articulate how this affects measurable outcomes. A syntax idea alone fails.
G2 (testability): accessible cases, independent truth oracle, fair baseline, legal access, feasible solo implementation. Make task-level dataset construction costs visible.

Each gate is GO / HOLD / STOP, with dated rationale and reopening evidence. Unknown or weakly supported does NOT equal failure; unexplained optimism does NOT equal GO. Do not progress an unresolved mandatory gate.

## Rank surviving candidates
Score 1–5 per category, with evidence and confidence:
- Economic value / existing spending: 20%
- Incremental semantic advantage: 20%
- Workflow repeatability: 15%
- Independent verifiability: 15%
- Input and reference data accessibility: 10%
- Demonstrable competitive opening: 10%
- Solo-founder accessibility / founder-market fit: 10%

A weighted total is a prioritization aid, not proof. Publish raw scores, supporting/contradicting observations, unknowns, and ranking sensitivity (including a scenario without founder-market-fit preference). Up to five G0–G2 contenders advance.

## Adversarial review
For each shortlisted candidate:
- Find strongest existing commercial and open-source products, standards, mature DSLs, academic efforts, and actual AI-agent capabilities.
- Identify precisely what they do and do not do; avoid claims from product category labels.
- Determine whether product differentiation exists without a new language.
- Challenge the reference oracle, data rights, economics, scope, buyer access, and implementation feasibility.
- Specify the smallest baseline-controlled experiment that could reverse the ranking.
Do not reject because an incumbent merely exists or an LLM might theoretically do it.

## Experimental preregistration (before implementation)
Write a dated, owner-approved plan in experiments/[candidate]/PLAN.md:
1. Specific task; unit of analysis; real or synthetic provenance; training/development/test separation.
2. Independent reference answers, qualified human adjudication where needed, uncertainty policy.
3. Four comparators where feasible:
   A. strong frontier LLM + relevant tools and data;
   B. same LLM + structured schema/JSON + ordinary code;
   C. same LLM + best appropriate existing DSL/rules engine;
   D. same LLM + proposed semantics (DSL syntax OPTIONAL).
4. Same information budget, model access, runtime/tool conditions where comparable. Log exceptions, token/time/cost budgets and retries.
5. Evaluation: correctness (severity-weighted), unsupported claims, handling changes/amendments, consistency, implement/update effort, operational overhead, cost and auditability.
6. Holdout cases, negative controls, ablations to isolate benefit from semantics vs prompts/tools/retrieval, and failure taxonomy.
7. Threshold for continuation and kill conditions fixed before seeing holdout results.

Indicative interesting effects (not universal pass criteria): >=30% reduction in material errors OR >=50% reduction in rule-change maintenance effort against the strongest baseline, with no critical regressions and credible unseen-case generalization. Small pilots cannot prove production reliability. Adjust thresholds only before experiment by recorded owner decision.

## G3 — technical result
GO only if the new semantic mechanism adds measurable benefit on the preregistered task beyond the strongest fair alternative and the effect plausibly generalizes within that narrow domain.
Otherwise STOP the custom language hypothesis for that domain, or HOLD for a clearly stated missing fact. A domain product may remain interesting without a DSL.

## G4 — strategic result
Evaluate technical result and buyer/distribution evidence separately. A technical kernel can be open sourced; a startup requires actual payer, route to delivery, and plausible unit economics. Do not claim market validation from benchmark success.

## Integrity and reporting
- Every material factual claim gets a resolvable citation or an explicit evidence gap.
- Never invent interviews, customers, pricing, sources, benchmarks or tool runs.
- State observed / inferred / assumed separately; date changing external facts.
- Append decisions to DECISION_LOG.md, including rejected alternatives and conditions for reopening.
- Any proposed charter, scoring or gate changes require an explicit review and owner approval; never silently edit them.
- Each phase ends with a concise evidence ledger, counterargument, cost so far and next uncertainty.
