# Deep Research Prompt 01 — Opportunity discovery
Status: READY FOR OWNER REVIEW; DO NOT RUN UNTIL THE CHARTER AND PROTOCOL ARE APPROVED.

## Role
Act as an independent research team combining operations research, programming-language design, enterprise software analysis and adversarial due diligence. You are not selling a DSL or proposing a startup by default.

## Research question
Across unrelated operational domains, where could explicit domain-specific semantics — possibly but not necessarily a new programming language — give AI-driven software a **decisive, measurable** advantage over strong existing solutions in the correctness, updateability, verifiability or economics of repeated decisions?

## Binding method
Read CHARTER.md and RESEARCH_PROTOCOL.md. Respect GO/HOLD/STOP gates and evidence categories. Do not prejudge telecom, contracts, regulation, governance, financial analysis, or any other domain.

## Discovery scope
Investigate at least 6 genuinely distinct industries, including some outside finance, telecom and governance. Aim for 20–30 narrowly specified micro-workflows. Report fewer if sources don't support them — no filler, no speculation presented as fact.

Each micro-workflow must describe who does exactly what, to which inputs, under which governing rules and exceptions, how often, with which consequences for error, and how an independent reviewer can tell whether the result is right.

Gather:
(1) primary domain sources and governing standards;
(2) actual operational pain or spending evidence;
(3) incumbent commercial products, open-source software and existing DSLs/engines;
(4) publicly accessible test cases, or a credible path to an independent oracle;
(5) explicit candidate semantic primitives that differ from a nice-to-have UI syntax.

For every important claim provide a link, publication/version date when known, access date, and what the evidence actually establishes. If a link cannot be verified, say so. Distinguish evidence absence from evidence of absence. Do not invent interviews, market size or pricing.

## Anti-kill and anti-hype rules
- Existing competitors and frontier-model capabilities are evidence to investigate, not a veto.
- Theoretical capability of a frontier model is not established operational performance.
- A model's occasional failure is not evidence that a new DSL will help.
- A new grammar or syntax is not a defensible kernel.
- A problem solvable equally well with typed JSON/conventional code or a mature DSL does not justify new language engineering.
- No candidate gets special treatment because of founder background or previous projects.

## Deliverables
A. Discovery coverage map: industries and source quality; blind spots.
B. A table of 20–30 micro-workflows with precise operator/decision/action, existing solutions, outcome gap, proposed semantic advantage, accessible validation, key uncertainty, source links.
C. Detailed one-page candidate cards for the ten best-evidenced opportunities using research/01-discovery/CANDIDATE_TEMPLATE.md.
D. G0/G1/G2 GO/HOLD/STOP screen with citations and missing evidence, not premature declarations of competitive victory.
E. Ranked up-to-five shortlist using the protocol's weighted scorecard, raw scores, confidence, sensitivity test removing founder-fit weight, and an adversarial case AGAINST each finalist.
F. Specific recommended next fact-finding step for each finalist. Do not propose building a compiler yet.

## Final stress-test
Before concluding, answer:
- What are we assuming that we cannot yet substantiate?
- Which strong incumbents or standards might make the language redundant?
- Would this opportunity remain attractive if frontier AI improved substantially?
- Which candidate looks attractive only because sources are thin?
- What concrete disconfirming evidence would reverse the ranking?

Do not modify charter, freeze gates, or begin implementation. Save raw notes/sources separately from synthesis. Research completion is not gate approval.
