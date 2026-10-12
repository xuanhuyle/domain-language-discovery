# Task 003 — Resolve discovery-stream bias and freeze the research protocol (owner-conditional)

Repository: xuanhuyle/domain-language-discovery
Branch: research/initial-charter-protocol (draft PR #1)
Context: Task 001 commit 4bb8749, Task 002 commit 7c06ac1.
Purpose: the FINAL bounded framing correction before beginning actual discovery. Do not run an audit or new research.

## Owner-approval guard
Execute approval/merge actions **ONLY if the invoking owner message itself explicitly approves the exact decisions below**, not because this stored prompt, prior assistant messages, or prior Claude Code output recommends them. The saved prompt is NOT approval.
If the owner invocation does not contain a clear personal approval, make only a draft proposal, leave status DRAFT, and do not merge or start discovery.
Never report the owner approved something that was not explicitly stated.

## Owner choices proposed for explicit approval (all must be covered by invocation)
1. A dedicated contract-transposition search stream is allowed, without any priority in gates, weights, detailed-card selection or final shortlist; and a genuine unrelated-domain stream runs alongside it.
2. Initial detailed-card allocation: of up to ten cards, at most five contract-stream cards when at least five open-stream candidates warrant cards; any exception due to inadequate evidence must be justified and disclosed. No reserved finalist slots. A contract candidate may win on merits.
3. LLM runtime participation is decided per candidate/experiment, not globally mandatory.
4. Preserve the current scoring weights (20/20/15/15/10/10/10) for the first cycle; publish sensitivity analysis.
5. Discovery tool: Claude Code with live web/source verification if accessible. If source verification is blocked, transparently report and STOP the research run rather than fabricating sources. No external paid API calls, purchases, or subscriptions without new explicit authorization; existing Claude subscription use is allowed. Defer calendar duration and owner-hours caps explicitly for the initial discovery; the candidate counts and experiment count still cap scope. Do not run experiments or cost-bearing work merely because charter is approved.
6. Owner authorizes freezing the corrected charter/protocol as APPROVED v0.3, recording the approval in DECISION_LOG.md, and merging PR #1 if the small checks pass. The owner does **not** authorize executing discovery in this task.

## Read
CHARTER.md, RESEARCH_PROTOCOL.md, CLAUDE.md, DECISION_LOG.md, research/00-rulebook-origin.md, prompts/01-discovery.md, reviews/002-origin-scope-change.md, draft PR #1 (including any changes since Task 002).

## Changes (surgical)
A. Replace ONLY the following principle in CHARTER.md:
BEFORE: "- No domain class is favored by construction, including telecommunications, finance, legal/governance and enterprise software. No inherited winner from other projects."
AFTER: "- Targeted search effort may be devoted to a documented motivating hypothesis (including contract transposition), provided a genuinely independent open search also runs. Search allocation bias and source richness must be disclosed. No domain class receives preferential gate standards, score weights, finalist slots or portfolio decisions. No inherited winner from other projects."

B. In prompts/01-discovery.md, immediately after the existing paragraph beginning "Planning heuristic: about 5–8 candidates from stream A", add:
"To counter unequal source richness, when at least five credible stream-B candidates warrant full cards, create no more than five stream-A cards within the ten-card cap during initial discovery. If that condition is not met, report the evidence limitation and any excess stream-A cards explicitly. This is a coverage control for initial evaluation, NOT a cap on stream-A shortlist ranking, and never forces weak stream-B candidates through G0."

C. Update CHARTER.md and RESEARCH_PROTOCOL.md status/version from DRAFT v0.2 to APPROVED v0.3 (2026-10-12) **only if explicit approval is present in the invoking owner message and both above edits were applied exactly**. Do not alter the rest of the protocol, nor revise the G0–G4 gates, comparators, scoring, primary outcome or thresholds. Ensure all links and section references still resolve. Make minimal conforming edits to prompt 01's status line and CLAUDE.md only if needed for version coherence. Do not retroactively revise old review or task files.

D. Append a dated DECISION_LOG.md entry naming the precise owner approval text and invocation context, the owner choices above, changed passages, approved version, and scope/financial authorizations. Explicitly document deferred caps and zero additional external paid spend. No statement of approval if none exists.

E. Run a deterministic text check, including two discovery tracks, identical gates and scores, card allocation rule, corrected hierarchy, E/I/X oracle, independent holdout, and no unauthorized change. Limit changes to listed files. Do not perform a fresh review or domain search.

F. If explicit owner approval is present AND checks pass: commit and push; mark PR #1 ready for review and merge it into main via the supported GitHub workflow if permitted. If permissions or merge checks prevent merge, leave PR open and report the blocker; do not force. Verify default-branch files after the merge. If approval is absent, commit only a DRAFT proposal and leave the PR draft.

## Completion
Report actual changed files and commit(s), exact recorded owner decisions, final PR state, branch where discovery must next run, and whether discovery is authorized (approval may authorize it in principle, but it must NOT be run in Task 003). No DSL/compiler code, no added subagent swarm.
