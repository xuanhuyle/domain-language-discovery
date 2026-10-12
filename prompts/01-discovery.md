# Deep Research Prompt 01 — Opportunity discovery
Status: DRAFT v0.2 — DO NOT RUN until the owner explicitly approves CHARTER.md and RESEARCH_PROTOCOL.md v0.2 and that approval is recorded in DECISION_LOG.md.

## Role
Act as an independent research team combining operations research, programming-language design, enterprise software analysis and adversarial due diligence. You are not selling a DSL or proposing a startup by default.

## Research question
Across unrelated operational domains, where could explicit domain-specific semantics — implemented as a library, checker, schema or, only optionally, a new language — give software a **material, measurable** advantage over strong existing solutions in the correctness, change/update effort, independent verifiability or lifecycle cost of repeated decisions?

## Binding method
Read CHARTER.md, RESEARCH_PROTOCOL.md and DECISION_LOG.md first. RESEARCH_PROTOCOL.md is the only source of gate definitions (G0–G2), terms and procedures; CHARTER.md sets the scope numbers. This prompt restates parts of them for convenience; if anything here conflicts with them, they govern, and you report the conflict. If you cannot read the repository files, say so at the top of your output and follow this prompt.

Do not prejudge any domain for or against. Candidates whose key invariant concerns units, time/sequence, capacity, provenance/authority or physical safety count equally with candidates based on rule-text interpretation.

## Discovery scope (copied from CHARTER § Scope and timebox)
- At least 6 genuinely distinct industries, including several outside telecommunications, finance, legal/governance and enterprise software.
- Aim for 20–30 narrowly specified micro-workflows; report fewer if sources do not support them — no filler, no speculation presented as fact.
- Detailed cards for at most 10 candidates.
- Propose a shortlist of preferably 3 finalists plus up to 2 reserves.

## Discovery streams
The owner's starting point is the contract-transposition problem described in research/00-rulebook-origin.md. Treat it as a motivating hypothesis, not an approved direction. Run two streams inside the scope above (same 20–30 candidates, at least 6 industries, at most 10 cards, same gates and scorecard):
- **Stream A — contract transposition.** Narrow, evidence-backed workflows in a few distinct contract families. Examine credit agreements and their amendments substantively first; add other contract families only where evidence suggests higher yield. Credit-agreement examples, given as examples only and not presumed suitable: financial-covenant calculation under agreement-specific definitions; amendment and effective-date handling; lender consents and waivers; payment waterfalls; conditions precedent. Each stream A candidate names (i) forward transposition, from a clause or amendment to the implementation it should change, and (ii) reverse verification, from a change in the implementation back to compatibility with the current in-force text, where relevant; and (iii) the residual a language could not solve: interpretation, binding to data that may not exist, legal authority and ratification, accountability. Investigate Catala, L4, Symboleo, the Accord Project and other relevant incumbents, including operational tools already used for these workflows, from current first-party documentation as baselines, not as presupposed gaps.
- **Stream B — open.** Unrelated industries and invariant types, with equal opportunity to win.

Planning heuristic: about 5–8 candidates from stream A, only if credible evidence exists; spend the rest on stream B. No padding of stream A, no reserved card or finalist slots, no scoring bonus, and no exclusion of contract candidates. Contract families count toward the industry target only where they belong to genuinely different industries. Tag every row and card with its stream. Do not assert that a new programming language is necessary.

Each micro-workflow must describe who does exactly what, to which inputs, under which governing rules, constraints and exceptions, how often, with which consequences for error, and how correctness can be established without relying on the proposed mechanism's own rules.

Gather:
1. primary domain sources, governing standards, SOPs and recorded outcomes (incident, recall, inspection or enforcement reports; public datasets);
2. operational pain and early demand signals (spend, losses, workarounds, incumbent pricing, buyer reachability) — signals only, never validation;
3. incumbent commercial products, open-source software and existing DSLs, rules, constraint or workflow engines, from their own documentation;
4. publicly accessible test cases or a credible path to reference outcomes of provenance E or I (RESEARCH_PROTOCOL § 1);
5. explicit candidate semantic mechanisms that differ from a nicer syntax.

For every important claim give a link, publication/version date when known, access date, a quotation or a paraphrase marked as such, and what the evidence actually establishes. If a link cannot be opened, say so. Distinguish absence of evidence from evidence of absence. Do not invent interviews, market size or pricing.

## Anti-kill and anti-hype rules
- Competitors and frontier-model capabilities indicate demand and set the baseline; they are neither a veto nor proof of opportunity.
- Theoretical capability of a frontier model is not established operational performance.
- A model's occasional failure is not evidence that new semantics will help.
- A new grammar or syntax is not a defensible kernel.
- That an existing tool *can* encode a behaviour is not enough to reject a candidate; ask at what cost, with what checks, and how robustly under rule change (G1 is plausibility, not proof).
- A problem solved equally well, at comparable cost, by typed code or an existing engine does not justify new semantics or a new language.
- No candidate gets special treatment because of founder background or previous projects.

## Deliverables
A. Coverage map: industries and source types reached, source quality, blind spots, and the split of candidates by primary invariant type and by stream (RESEARCH_PROTOCOL § 2). Disclose selection biases, including that stream A received dedicated search effort and draws mainly on public rule text.
B. A table of all discovered micro-workflows: stream (A or B), operator / decision / action, frequency, existing solutions, outcome gap, demand signals, proposed mechanism, reference-outcome path, key uncertainty, source links, and a proposed G0 verdict.
C. Cards using research/01-discovery/CANDIDATE_TEMPLATE.md for up to 10 best-evidenced candidates, each with a G1 paper probe. Uncarded rows are marked "discovered — not carded" (never STOP).
D. Proposed G0/G1/G2 verdicts for carded candidates, with G2 marked provisional; every HOLD names missing evidence and one bounded next action. These are proposals, not gate decisions.
E. Ranked shortlist proposal (preferably 3 plus up to 2 reserves) using the RESEARCH_PROTOCOL § 4 scorecard: raw scores, confidence, sensitivity without the founder-fit category, re-checked key G0 links, an adversarial case AGAINST each finalist, and a side-by-side comparison of streams A and B on that same scorecard (counts, gate outcomes, scores, source quality).
F. The next fact-finding step for each finalist. Do not propose building a compiler or language.

## Final stress-test
Before concluding, answer:
- What are we assuming that we cannot yet substantiate?
- Which strong incumbents or standards might make the proposed mechanism redundant, and at what cost would they cover it?
- Which part of each finalist's advantage rests on structural properties (determinism, static checks, binding to the authoritative source, auditability, safe change propagation), and which part rests on currently measured model error rates? Name any concrete, currently observable capability that would erode the second part, with a dated source; do not treat speculative future capability as fact.
- Which candidate looks attractive only because sources are thin?
- What concrete disconfirming evidence would reverse the ranking?

Do not modify the charter or protocol, approve gates, or begin implementation. Save raw notes and sources separately from the synthesis. Research completion is not gate approval.
