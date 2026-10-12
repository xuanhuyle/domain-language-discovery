# Decision Log
Append dated decision entries. Never rewrite history; supersede with a new entry.

## 2026-10-12 — Initialize research program (DRAFT)
- Decision: prepare charter, protocol and discovery prompts for owner review.
- Status: Proposed; not frozen or gate-approved.
- Observed: a new research repository exists.
- Inferred: specialized semantics may confer advantages in narrow business workflows.
- Assumed: accessible inputs and independent reference outcomes exist in at least one candidate micro-domain.
- Alternative: immediately build a DSL or a generalized governance platform. Rejected for now because no comparative evidence exists.
- Next review: owner signs off CHARTER.md and RESEARCH_PROTOCOL.md; only then initiate broad discovery.
- Reopen condition: owner explicitly revises scope or sequencing, with rationale documented.

## 2026-10-12 — Propose DRAFT v0.2 of charter and protocol (NOT approved)
- Decision: propose DRAFT v0.2 of CHARTER.md and RESEARCH_PROTOCOL.md, with aligned edits to CLAUDE.md, the candidate template and prompts 01 and 02, as requested by the owner's Task 001 prompt (prompts/01-lean-protocol-v02.md).
- Status: Proposed by an agent; NOT approved. No document is frozen, no gate is passed, and discovery (prompt 01) is not authorized.
- Observed: Review 000 (reviews/000-*) identified oracle circularity, under-built baselines, an undefined arm D, unbound outcome selection and weak statistical specification; it also proposed 50 amendments, several of which Task 001 overrides.
- Inferred: a short protocol with one canonical home for definitions keeps those protections while staying executable by a solo founder working from mobile.
- Assumed: the owner will review reviews/001-v0.2-diff-rationale.md before approving or amending v0.2.
- Alternative: apply all 50 Review 000 amendments. Rejected for this pass as procedurally heavy; adopted, modified and rejected items are listed in reviews/001-v0.2-diff-rationale.md.
- Effect on prior decisions: none yet. The 2026-10-12 initialization entry stands. If approved, v0.2 replaces v0.1 as the governing draft.
- Open owner decisions: listed in reviews/001-v0.2-diff-rationale.md § (d).
- Next review: owner decides those items and either approves v0.2 explicitly (the agent records the approval here) or requests changes.
- Reopen condition: owner revises scope, thresholds or sequencing, with rationale recorded here.

## 2026-10-12 — Propose two-stream discovery framing from the Rulebook origin (NOT approved)
- Decision: record the owner's Rulebook contract-transposition motivation as a hypothesis (research/00-rulebook-origin.md) and frame prompt 01 as two streams: A (contract transposition, credit agreements first) and B (open). Requested by Task 002 (prompts/02-rulebook-origin-discovery-scope.md).
- Status: Proposed by an agent; NOT approved. v0.2 remains unapproved; discovery is not authorized. CHARTER.md, RESEARCH_PROTOCOL.md, gates, scoring, baselines and thresholds are unchanged.
- Observed: Rulebook Part IV is analysis and a plan, not evidence; its only execution (Execution 01) ended "C. INSUFFICIENT EVIDENCE" on a different question.
- Alternative: keep a single undifferentiated search. Not chosen because the owner's actual question would then be sampled only by chance.
- Effect on prior decisions: none; the 2026-10-12 v0.2 proposal stands. Possible tension with CHARTER "No domain class is favored by construction" is set out in reviews/002-origin-scope-change.md for the owner.
- Reopen condition: owner rejects or resizes stream A, or amends the charter clause.

## 2026-10-12 — APPROVED: freeze CHARTER.md and RESEARCH_PROTOCOL.md as v0.3 (Task 003)
- Approver and place: the repository owner, in the Claude Code session message that invoked Task 003 (prompts/03-conditional-freeze-and-merge.md), 2026-10-12. Exact words: "I explicitly approve the owner decisions 1–6 listed in prompts/03-conditional-freeze-and-merge.md." The same message instructed: "Freeze the corrected charter and protocol as v0.3. Record my approval in DECISION_LOG.md. Commit, push, and merge PR #1 if all checks pass. Do not launch discovery or implement a programming language." Recorded by the agent per RESEARCH_PROTOCOL.md § 9; the agent approved nothing itself.
- Object approved: CHARTER.md and RESEARCH_PROTOCOL.md, version APPROVED v0.3 (2026-10-12), as corrected below. Both are frozen from this entry; later changes need a new owner-approved version.
- Owner decisions approved (as listed in prompts/03-conditional-freeze-and-merge.md):
  1. A dedicated contract-transposition search stream is allowed, without any priority in gates, weights, detailed-card selection or final shortlist; a genuine unrelated-domain stream runs alongside it.
  2. Of up to ten detailed cards, at most five contract-stream cards when at least five open-stream candidates warrant cards; any exception due to inadequate evidence must be justified and disclosed. No reserved finalist slots; a contract candidate may win on merits.
  3. LLM runtime participation is decided per candidate/experiment, not globally mandatory.
  4. Scoring weights 20/20/15/15/10/10/10 are kept for the first cycle; sensitivity analysis is published.
  5. Discovery tool: Claude Code with live web/source verification if accessible; if source verification is blocked, report it transparently and STOP the research run rather than fabricate sources. No external paid API calls, purchases or subscriptions without new explicit authorization; use of the existing Claude subscription is allowed. Calendar-duration and owner-hours caps are explicitly deferred for initial discovery; candidate and experiment counts still cap scope. No experiments or cost-bearing work merely because the charter is approved.
  6. Freeze the corrected charter/protocol as APPROVED v0.3, record this approval here, and merge PR #1 if the small checks pass. Executing discovery is NOT authorized by this task.
- Changed passages: CHARTER.md principle on domain classes replaced verbatim (Task 003 change A); prompts/01-discovery.md card-allocation paragraph added after "Planning heuristic" (change B); status/version lines of CHARTER.md and RESEARCH_PROTOCOL.md set to APPROVED v0.3; version-coherence edits to CHARTER.md "Caps" label and "Current position", and to the prompts/01-discovery.md status line. No change to gates G0–G4, comparators, scoring weights, primary endpoint, thresholds or the rest of the protocol.
- Scope and financial authorizations: scope caps are those in CHARTER.md § Scope and timebox. Calendar and owner-hours caps: deferred (decision 5). Additional external paid spend authorized: zero. Spend cap per discovery run and per experiment: not set; any paid run requires new explicit authorization.
- Effect on prior decisions: supersedes the two 2026-10-12 Proposed entries (v0.2 proposal and two-stream framing) by approving them as corrected; resolves the charter tension raised in reviews/002-origin-scope-change.md.
- Next: discovery (prompts/01-discovery.md) may start only on a separate explicit owner instruction, on main after PR #1 is merged.
- Reopen condition: the owner approves a new version, with what changed and why recorded here.
