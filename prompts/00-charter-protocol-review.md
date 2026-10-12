# Task 000 — Adversarial review of the research charter and protocol

Date: 2026-10-12
Target repository: xuanhuyle/domain-language-discovery
Status: executable task prompt; **not** authorization to approve or change research gates.
Branch: research/initial-charter-protocol (draft PR #1).

## Why this task exists
The owner wants to find a narrow operational domain where explicit domain-specific semantics, potentially embodied in a proprietary programming language, produce a decisive, measurable benefit. Past research searches repeatedly killed ideas prematurely because competitors existed or frontier models might eventually solve the problem. We must also avoid the opposite error: inventing a DSL in search of an application.

The first draft of the governing documents has been written and must now be independently audited before freezing and launching deep research.

## Inputs — READ IN FULL
1. README.md
2. CHARTER.md
3. RESEARCH_PROTOCOL.md
4. CLAUDE.md
5. DECISION_LOG.md
6. research/01-discovery/CANDIDATE_TEMPLATE.md
7. prompts/01-discovery.md
8. prompts/02-adversarial-review.md
9. Diff and description of draft PR #1 vs origin/main, if accessible.

Treat these documents as *proposals*, not as already approved policy. Do not skip sections to save context.

## Role and stance
Act as a skeptical research-methodology auditor and technical founder with practical familiarity with DSLs, interpreters, policy engines, and enterprise software economics. Your job is to improve the quality of the research decision, not to produce reassuring feedback.

Prioritize falsifiability, independent evidence, realistic execution for a non-specialist solo founder working with Claude Code, and resistance to both premature rejection and unjustified enthusiasm.

## Required critique
A. **Thesis coherence:** Is the charter looking for a language, a semantic kernel, a workflow product, or a startup? Where are objectives mixed in ways that would permit drift?
B. **Anti-drift effectiveness:** Are the charter, gate conditions, owner approvals, stopping criteria, and decision log precise enough to prevent quiet goalpost movement? Where are they overbureaucratic?
C. **Selection bias:** Do the proposed sources and scoring favor regulation, contracts, finance, and telecom even while claiming neutrality? Are there promising classes of domains we are systematically missing?
D. **Competition methodology:** Is 'competition is evidence, not a veto' operationalized? Do we have an equally strong way to reject a structurally undifferentiated project? Propose disconfirming tests rather than speculative frontier-lab fears.
E. **DSL necessity:** What counts as an improvement from domain semantics rather than syntax or packaging? When is typed JSON, Python, SQL, Cedar/Rego/CEL, a constraints engine, a compiler IR, or a workflow DSL enough? How to compare fairly?
F. **Evidence feasibility:** Will 20–30 cards and an independently verified oracle be realistic? Are source requirements attainable from public information? Are sampling, adjudication, data leakage, and synthetic-test limitations managed?
G. **Experimental validity:** Can four arms A/B/C/D isolate the semantic contribution, or will tooling, developer time and baseline tuning confound it? Challenge the indicative >=30% error / >=50% maintenance thresholds and the rule of 'no critical regressions.'
H. **Economics and go-to-market:** Does the protocol adequately distinguish an open-source technical finding from a buyer-driven business, without requiring enterprise interviews before a small technical experiment?
I. **Resource discipline:** Is the timebox, number of finalists, and number of experiments appropriate? What evidence would genuinely justify ending the *entire* program?
J. **Adversarial red team:** Identify three realistic ways this research could yield apparently attractive results without having found a meaningful or differentiated capability.

## Output requirements
Create `reviews/000-charter-protocol-adversarial-review.md` with:
1. Executive verdict: READY / READY WITH REQUIRED FIXES / NOT READY.
2. The five most important defects ranked by consequence, each with exact document/section, failure mode, and a minimal proposed correction.
3. Explicit strengths worth retaining (no generic praise).
4. A revised minimal gate architecture if the existing one is overcomplicated; do not silently rewrite gates.
5. Concrete edits proposed in patch-like BEFORE / AFTER wording for the affected passages (or exact replacement text).
6. What we should **not** change yet, and why.
7. An owner decision checklist no longer than five decisions.
8. A recommended next command/task after the owner approves the corrections.

Optionally create `reviews/000-proposed-amendments.md` if exact replacement text is long.

## Constraints
- **DO NOT** edit CHARTER.md, RESEARCH_PROTOCOL.md, CLAUDE.md, DECISION_LOG.md or the existing deep research prompts in this task.
- **DO NOT** run deep research, search 30 candidate domains, build language syntax, implement a compiler, create multi-agent infrastructure, spend API credits, or claim gate approval.
- You may consult a small number of current first-party technical references if genuinely needed, but the task is an *internal methodological review*; source limitations must be made explicit. Do not spend most of the effort doing a literature review.
- Never invent external evidence or previous experimental results.
- Distinguish observations from judgments and unknowns.
- Do not merge the pull request.

## Completion
Commit only the review files to the current branch, push to origin if authenticated, and report:
- commit SHA and files changed;
- verdict and top defects;
- whether the draft PR now needs amendments;
- which decisions remain with the owner.

Do not mark the charter approved or start discovery.
