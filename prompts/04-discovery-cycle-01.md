# Task 004 — Discovery Cycle 01: evidence-backed micro-workflows

Repository: xuanhuyle/domain-language-discovery
Default branch: main (APPROVED CHARTER and RESEARCH_PROTOCOL v0.3)
Status: READY TO RUN ONLY ON A SEPARATE EXPLICIT OWNER INSTRUCTION.
This saved task prompt does NOT itself authorize discovery, expenses, shortlist approval, or an experiment.

## Execution authorization
Proceed with the research ONLY when the owner's invoking message explicitly instructs you to start discovery (for example, "I authorize you to run Task 004 discovery now"). A paste of a progress update or a general expression of interest is not authorization.
If no such instruction exists, do not research; merely confirm the prompt is ready.

## Operating mode
- One primary agent; no Ultracode, swarm, massive auditor/refuter setup or invented agent independence. Opus / High effort when available.
- Use the current Claude Code subscription and web capabilities. **No additional paid API calls, purchases, paid data access, subscriptions or spending** without explicit owner authorization.
- Work on a new branch `research/discovery-cycle-01` based on latest origin/main; do not amend, override, or unfreeze approved CHARTER.md or RESEARCH_PROTOCOL.md.
- Read, in full, CHARTER.md, RESEARCH_PROTOCOL.md, CLAUDE.md, DECISION_LOG.md, prompts/01-discovery.md, research/00-rulebook-origin.md, and research/01-discovery/CANDIDATE_TEMPLATE.md.
- Treat Task 002's origin note as motivation **not evidence**. The existing approvals permit research but not any G0–G4 verdict, new language, experiment, pivot or further paid expense.

## Step 0 — prove access to real external evidence (short and decisive)
Before generating any candidate conclusions, verify that you can open and inspect at least three independently hosted primary sources from at least two unrelated domains, with recoverable links, titles and dates. Do not count search snippets, memory-based references or AI summaries as opened sources.
If live source access fails after a bounded attempt, write `research/01-discovery/ACCESS_BLOCKER.md` with attempted URLs, the actual tool error, available fallbacks and why they don't permit source verification; commit and push, then STOP. Do not simulate the literature search or fabricate citations.

## Step 1 — conduct discovery, under the approved protocol
Execute `prompts/01-discovery.md` as written, taking all constraints and definitions from the approved charter/protocol. Keep the total target of 20–30 credible micro-workflow rows across at least 6 genuinely distinct industries; report fewer rather than pad. The objective is **discovery**, not validation of a DSL thesis.

Two search streams within the single existing scope:
- A: ~5–8 evidence-supported candidates in narrow contract-transposition workflows, examining credit agreements and amendments first but not favoring them in scoring. Explicitly distinguish forward contractual requirement -> implementation and reverse implementation change -> current authoritative contract. Model the residual that a language cannot settle: disputed interpretation, data not captured, in-force status, approval/ratification, or accountability. Consider Catala, L4, Symboleo, Accord Project, conventional software and actual deployed incumbent systems from verified first-party sources. Existence of a named project is neither disproof nor evidence of an unsolved gap.
- B: genuinely independent search beyond legal/governance/finance/telecom and across different kinds of invariants (time, sequence, resources, units, safety, provenance, etc.). Aim for at least six industries across the overall program. Do not populate B with variations of the same legal problem under different industry headings.

Use the SAME G0/G1/G2 definitions, E/I/X reference-outcome classification, scoring weights, source quality rules and uncertainty labels for both streams. Up to ten detailed cards total, and no more than five stream-A cards **when five credible stream-B candidates warrant full cards**; no reserved finalist slots or score bonuses. Every candidate must name the user/operator, input, decision/action, failure costs, proposed advantage if any, baseline alternatives and cheapest possible falsification. Record the stream and primary invariant type.

## Evidence discipline
- For each candidate, separate source-grounded observations from extrapolations. Provide resolvable primary-source URLs (and publication/version date where known, access date, exactly what is established); if a source isn't accessible, label it NOT VERIFIED and don't lean on it for a high-confidence conclusion.
- For finalists, actually open and re-check crucial G0 evidence and the relevant first-party incumbent documentation; describe scope and missing capabilities precisely. Incumbent claims from recollection do not count as verified.
- A contract document proves clauses exist, NOT that transposition is expensive or someone would pay for a new language. A working rule representation proves expressibility, NOT that the legal interpretation is correct or approved.
- Do not assert novelty by merely renaming an existing construct. Search for conventional engineering and mature DSL solutions that may provide the same guarantees.
- Do not use source text, code or outputs in a way that violates access rights. No interviews or buyer validation should be invented.
- G2 remains provisional during discovery. A hypothetical self-labelled oracle (X) is not evidence of independent testability.
- Source access blockages and thin evidence produce UNKNOWN/HOLD where appropriate, not automatic STOP.

## Output structure (keep compact and useful)
Write the smallest set of files consistent with prompt 01:
1. `research/01-discovery/SOURCES.md` — deduplicated source ledger with opened/blocked and dates; cite source IDs elsewhere.
2. `research/01-discovery/COVERAGE.md` — sources searched, >=6-industry coverage if attainable, invariant-class and stream breakdown, evidence richness bias, blind spots, time/spend observable.
3. `research/01-discovery/CANDIDATES.md` — master table of 20–30 micro-workflows (or smaller supported number), source IDs, stream and a proposed G0.
4. `research/01-discovery/cards/C###.md` — up to 10 evidence-backed cards using template; per-card paper G1 probe and provisional G2. No full card for every discovered row.
5. `research/01-discovery/SHORTLIST_PROPOSAL.md` — preferably three finalists plus at most two reserves, side-by-side A/B comparison, the seven weighted score categories with raw scores, confidence, sensitivity excluding founder fit, strongest counterargument and one bounded next step per finalist. A proposed shortlist is NOT approved.
6. `research/01-discovery/STATUS.md` — short executive answer: what was observed, inferred, assumed, and unknown; likely technical mechanism(s) if any; what would kill them; whether source verification succeeded; next owner decision.

Incremental commits are permitted when useful for reproducibility. Do not create a new protocol, framework, source database application, agent harness, DSL, compiler, benchmark or experiment. Do not start prompt 02 / adversarial finalist review automatically.

## End-of-task checks
- Verify that each cited source ID resolves and finalist citations actually support the stated claims. Flag any unavailable links without inventing fallback content.
- Check all numeric counts and scoring arithmetic; ensure no implicit industry padding.
- Confirm the ten-card cap and five-card conditional contract limit.
- No edits to approved governing files. No owner gate approvals inferred from research output.
- Commit and push the branch; optionally open a DRAFT discovery PR but **do not merge** it. Do not automatically label the proposed shortlist approved.

## Report back to owner
Give a compact summary with: branch/commit, actual number of supported candidates, industries, cards, verified source coverage, proposed shortlist, two or three most important uncertainties, source-access limitations, spend statement, and the exact single next owner decision needed. State candidly if no candidate has demonstrated advantage yet (that is expected at discovery).
