# Research Charter — Domain Language Discovery
Status: APPROVED v0.3 (2026-10-12) — owner-approved and frozen; approval recorded in DECISION_LOG.md. No research gate has been passed.
Version: 0.3 (2026-10-12). Supersedes drafts 0.1 and 0.2; rationale in reviews/001-v0.2-diff-rationale.md and reviews/002-origin-scope-change.md.

This charter sets the thesis and boundaries. Gate definitions, terms and procedures live only in RESEARCH_PROTOCOL.md.

## Mission
Identify one narrow, repeatable and economically meaningful operational workflow in which explicit domain-specific semantics produce a measurable advantage over the strongest practical alternatives. A new programming language is one optional way to implement such semantics, not the outcome sought.

This is a discovery program, not a commitment to design a compiler, sell a DSL, or enter any predetermined industry.

## Central falsifiable hypothesis
For a selected micro-workflow, an explicit domain-specific semantic mechanism (for example types, constraints, temporal or authority rules, execution or checking semantics) materially improves ONE preregistered primary endpoint — decision correctness, change/update effort, independent verifiability, or lifecycle cost — against the strongest fair alternative, without breaching the guardrails preregistered for the other endpoints. The program-level thesis is supported only through such per-candidate tests; an improvement on a non-primary endpoint is exploratory, not confirmation.

The hypothesis is NOT that LLMs are incapable, that programming languages are inherently defensible, that a new syntax is valuable, or that a language must be built.

## Two possible payoffs
1. Commercial: a narrow workflow product with a clear buyer, spend, distribution path, and differentiated results. Early demand evidence may inform discovery and ranking; validation requires an actual commitment (payment, pilot or written intent) and is never inferred from a technical result.
2. Technical: a reproducible semantic/execution mechanism, even without immediate commercial demand. Reproducible means the preregistered result is re-obtained from the published plan, data and code in a clean session or by someone who did not build it.
Keep these evaluations separate. A technical success is not automatically a startup, and a technical result with no buyer is a valid end state.

## Non-negotiable principles
- Outcome gap first, not language first.
- Competitors and frontier labs indicate demand and set the baseline to beat. They are neither an automatic veto nor automatic evidence of opportunity. Their theoretical future capabilities are not evidence.
- A proposed mechanism must beat credible alternatives: LLM plus tools; LLM plus robust schema and host-language code; and the most relevant existing incumbent (DSL, rules, constraint or other engine) where one materially applies.
- Test the value of semantics, types, constraints, execution, and verification — NOT aesthetics of syntax.
- Separate observed facts, inferences, assumptions and unknowns. Cite original sources, dates, and accessibility limitations.
- Admit unknowns. HOLD is not STOP. Lack of discoverable evidence is not evidence of absence.
- Test on unseen cases, with reference outcomes that do not come from the proposed mechanism's own rule model, and with explicit failure modes.
- Favor reproducible public-domain or legitimately accessible inputs. Do not infer private enterprise data access.
- Respect solo-founder constraints: limited coding background, AI-assisted implementation (often from mobile), limited distribution, and low experiment budget.
- Targeted search effort may be devoted to a documented motivating hypothesis (including contract transposition), provided a genuinely independent open search also runs. Search allocation bias and source richness must be disclosed. No domain class receives preferential gate standards, score weights, finalist slots or portfolio decisions. No inherited winner from other projects.
- Do not transfer an architecture from Sophon or another repository without explicitly justifying why it is needed.
- No language/compiler/platform implementation before the owner approves an experiment plan. Rule sketches, paper probes and paper prototypes are allowed earlier.
- No self-authorized pivot, no moving experimental goalposts, no retroactive success criteria.
- No claim that our mechanism is proprietary or defensible merely because its syntax is new.

## Scope and timebox
One initial discovery cycle:
- target 20–30 credible micro-workflows from at least 6 distinct industries; if 20 credible candidates cannot be supported, report the smaller valid number and never fabricate breadth;
- up to 10 detailed candidate cards;
- a shortlist of preferably 3 finalists plus up to 2 reserves;
- at most 2 preregistered experiments;
- then a portfolio decision by the owner.
Any expansion of candidates, finalists, experiments, cycles or budget requires explicit owner approval.

Caps (OWNER-SET; not set as of v0.3): calendar duration of the cycle; owner hours per week; API/tool spend per discovery run and per experiment. Agents never fill these values. Until the owner sets them or explicitly defers them in DECISION_LOG.md, agents report observable usage and ask before any paid run or any work beyond the step the owner has authorized.

## Authority
Only the owner approves: freezing this charter and the protocol; the shortlist; each experiment plan (including its spend); any extension of scope, budget or cycles; any pivot; and G3/G4 verdicts. What counts as a valid approval and how it is recorded is defined in RESEARCH_PROTOCOL.md § 9 (Decisions, approvals, HOLD and frozen status). Agents propose; they never approve, and silence is never approval. Agents may propose edits only as separate reviews or pull requests.

## Definition of progress
Progress means reduction of a specified uncertainty backed by auditable evidence, not number of agents, pages, diagrams, tokens, commits or tests.

## Stopping conditions
- Candidate: the semantic thesis stops for a candidate when its G1 verdict is STOP or a confirmatory experiment fails its frozen success rule (G3 STOP). The domain may remain commercially interesting without a new mechanism; record it as a separate lead and do not pursue it under this charter without owner approval.
- Cycle: if the cycle yields no candidate that passes G0 and G1 with at least a provisional G2, report this with the coverage map. Unresolved HOLDs are PARKED, not failed. The owner then chooses between one redesigned cycle with a documented change of sources or framing, and stopping.
- Program: stop the program, unless the owner approves a new cycle on new evidence, when two fair confirmatory experiments both fail their frozen success rules, or when an owner-set cap is reached without a G3 GO and the owner declines an extension.

## Current position
Pre-G0. No preferred industry, target user, language specification, architecture, or startup thesis has been approved. v0.3 is approved; discovery has not been run.
