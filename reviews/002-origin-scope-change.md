# Review 002 — Origin and discovery-scope change

Date: 2026-10-12. Task: prompts/02-rulebook-origin-discovery-scope.md. Status: proposal; v0.2 is not approved and discovery is not authorized.

## Changed
- **New: research/00-rulebook-origin.md.** Records the Rulebook motivation as a hypothesis, citing rulebook@`0e0e1cc` (README, plan §§ IV.2–IV.13, Execution 01) with each statement labelled analysis, claim, plan or observed. Covers the nine steps, the two-way requirement, H1–H3 and scope limits.
- **prompts/01-discovery.md (10 lines added, 3 changed):**
  - A new "Discovery streams" section defines stream A (contract transposition, credit agreements first) and stream B (open), with a 5–8 planning heuristic for A.
  - Deliverables A, B and E add a split by stream with bias disclosure, a stream column, and a side-by-side comparison on the same scorecard.
- **DECISION_LOG.md:** one appended Proposed entry; earlier entries untouched.

## Unchanged
CHARTER.md, RESEARCH_PROTOCOL.md, G0–G2, scoring weights, baseline arms, thresholds, prompt 01's status line, anti-kill and anti-hype rules, stress test, and prompt 02.

## Why this is not preferential scoring
Stream A changes where the search looks, not how candidates are judged: both streams face the same gates and RESEARCH_PROTOCOL § 4 scorecard. No stream reserves a card or finalist slot, gets a bonus, or is excluded. Stream A is capped by evidence ("only if credible evidence exists") and must name the residual a language cannot solve, which counts against it. Existing legal DSLs are baselines, so H2 and H3 can win.

## Tension with the charter
CHARTER says "No domain class is favored by construction." Dedicated search effort for one domain class is favoring in allocation, even though selection and scoring are neutral. Read strictly, stream A conflicts with it, and the charter governs. This review does not resolve that: the owner should confirm the clause covers selection and scoring only, amend it, or drop stream A.

## Can stream A skew results? Yes, in four ways
1. **Evidence richness.** Contract and regulatory text is public and rule-shaped, and legal DSLs are well documented. Stream A candidates may look "best-evidenced", and the 10 cards go to the best-evidenced, so A could take a disproportionate share of cards.
2. **Breadth.** Up to 8 rows from one domain class is roughly a quarter to two-fifths of a 20–30 table, and narrows stream B.
3. **Invariant type.** Stream A is mostly rule-text interpretation, the class Review 000 found already over-represented.
4. **Framing.** The researcher knows the owner's preferred starting point.

Mitigations in the prompt: stream tagging, a side-by-side comparison on one scorecard, disclosure of the invariant-type split and of biases, the industry-count rule, and no reserved slots. Not mitigated: card allocation by evidence richness. One option for the owner, not adopted here, is a cap on stream A cards, for example at most half.

## Checks
All 15 quoted Rulebook strings matched verbatim, and section numbers were confirmed. Part IV never mentions credit agreements or DSLs; the note says so. Catala, L4, Symboleo and the Accord Project are named, not researched, and no URLs are asserted. The Sophon charter was not consulted.
