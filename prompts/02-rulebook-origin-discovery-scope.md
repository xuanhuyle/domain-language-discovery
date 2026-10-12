# Task 002 — Preserve the Rulebook origin and calibrate discovery

Date: 2026-10-12
Repository: xuanhuyle/domain-language-discovery
Working branch: research/initial-charter-protocol (draft PR #1)
Status: PROPOSED TASK; not authorization to freeze v0.2 or conduct discovery.

## Context from owner
The owner's actual starting point is the *transposition problem* encountered in xuanhuyle/rulebook: human-written contractual/regulatory requirements must be located, interpreted, bound to operational data, reconciled, validated, approved, encoded, and maintained under amendments. This inspired the question whether a purpose-built language for one **family of contracts** (possibly credit agreements) could reduce cost or errors. The intended useful capability must also support reverse verification from an operational implementation back to the applicable contract. This motivation was clarified only after the draft generic discovery protocol was composed.

The owner does NOT yet know whether a new language is needed, whether an existing legal language (e.g. Catala, L4, Symboleo) suffices, or whether the bottleneck is interpretation, data binding, accountability or integration rather than syntax/semantics.

## Read first
- CHARTER.md and RESEARCH_PROTOCOL.md DRAFT v0.2
- prompts/01-discovery.md
- DECISION_LOG.md
- reviews/001-v0.2-diff-rationale.md
- xuanhuyle/rulebook/README.md and Part IV (§§ IV.1–IV.13) of plan/research-plan-parts-I-V.md, fetched from its public GitHub repository
- If useful, the currently published Sophon charter's two directions; DO NOT import Sophon architecture or unsupported empirical claims.

Important: Rulebook's Part IV is a **research plan / analysis**, not proof that a new DSL works or that there is buyer demand. Its published checkpoint census reports insufficient deployment evidence. Identify clearly which claims are conceptual and which are actually observed.

## Task (one primary agent, no ultracode or swarm)
Make a small, transparent amendment that records the origin as a **motivating hypothesis** while keeping a genuine outside-contract discovery track.

1. Add a short `research/00-rulebook-origin.md` (aim ~1–2 pages) containing:
   - the specific source-referenced Rulebook observations/claims (with repo path, section);
   - the nine transposition steps, distinguishing automatable syntax/encoding from interpretation, missing operational predicates, legal authority and accountability;
   - two-way requirement: document/amendment -> actual implementation, and implementation change -> compatibility with current authoritative source;
   - H1: a family-specific language/semantic mechanism has measurable incremental value;
   - H2: an existing legal DSL, typed schema + host-language library, or conventional engineering gives the same advantage;
   - H3: the principal obstacle is interpretation, data binding, process, or governance and therefore not solved by a language;
   - what evidence would favor each, and scope limits. The credit-agreement hypothesis is a concrete starting case, NOT an approved winner or an already demonstrated need.
   - Distinguish Part IV's propositions from Rulebook's actual experiment statuses; never convert analysis into empirical proof.

2. Make a *surgical* change to `prompts/01-discovery.md` (NOT to G0/G1/G2 or scoring):
   - Run **two explicit discovery streams** within the existing 20–30 candidates / >=6-industry target and up-to-ten-card cap:
     A. contract-transposition stream: search for evidence-backed, narrow workflows in a few distinct contract families, prioritizing a substantive examination of credit agreements and amendments, plus other potentially higher-yield contract types if evidence supports them;
     B. open stream: unrelated industries and invariant types with equal opportunity to win.
   - As a planning heuristic, seek about 5–8 candidates from stream A **only if credible evidence exists**; spend the rest on stream B. No artificial padding, reserved finalist slots, scoring bonus or exclusion of contract candidates.
   - Candidates within A must name BOTH forward transposition and reverse verification if relevant, and explicitly identify the binding/authority/interpretation residual that a language could not solve.
   - For credit agreements, possible *examples only* include financial covenant calculation under agreement-specific definitions, amendment/effective-date handling, lender consents/waivers, payment waterfalls, or conditions precedent. No claim all are suitable.
   - Investigate Catala, L4, Symboleo, Accord Project or other relevant incumbents from up-to-date first-party docs **as baselines, not presupposed gaps**. Do not assert a new programming language is necessary.
   - Require the report to compare the two streams on the *same* canonical scorecard, with source quality and selection biases disclosed.
   - Preserve all current protocol safeguards and its exact approved/nonapproved status. This is framing of discovery, not premature discovery.

3. If useful, add one compact proposed (NOT APPROVED) DECISION_LOG entry describing the reason for this scope clarification, without altering history. If this would create redundant paperwork, skip and explain.

4. Produce `reviews/002-origin-scope-change.md` (<= 500 words) noting which lines/files were changed, what remains unchanged, any tension with the charter's 'no domain class favored by construction' clause, and why the two-stream framing is not preferential scoring. Report explicitly if the proposed stream A share could skew discovery results.

## Constraints
- Do not edit CHARTER.md, RESEARCH_PROTOCOL.md, scoring weights, gates, baseline definitions or experimental thresholds.
- Do not declare DRAFT v0.2 approved or run prompt 01. No new code, compiler or DSL. No full literature or 55-agent audit.
- One primary agent; no automatic multi-agent orchestration; small textual checks only.
- Check links and quote source sections accurately. Clearly identify unverified or inaccessible references.
- Work on existing research branch, commit and push only the specified changes, leave PR #1 draft and unmerged.

## Completion
Report the path of the new origin note, revised prompt, any decision-log entry, brief explanation of the two-stream discovery design, consistency/accuracy checks and commit SHA. End with the exact owner choices required before approving v0.2 and launching discovery, without inventing a paid budget.
