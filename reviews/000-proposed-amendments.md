# Review 000 — Proposed amendments (exact BEFORE / AFTER text)

Date: 2026-10-12
Companion to: `reviews/000-charter-protocol-adversarial-review.md` (read that first for the verdict, ranking and rationale).
Target branch: `research/initial-charter-protocol` at commit `4a9366b` (draft PR #1).
Status: **PROPOSAL.** Nothing in this file has been applied. No governing document was edited by this review. The owner decides which amendments land, in which order, and fills every `[owner sets: …]` placeholder.

## How to read this file

- Each amendment names the document and section, the verbatim **BEFORE** text (or an insertion anchor), the proposed **AFTER** text, a one-sentence rationale, the review defect ids it closes, the cluster it belongs to in the main review (C01–C15), its bureaucracy cost, and whether it is a judgment call reserved to the owner.
- Every BEFORE text and insertion anchor was re-verified with `grep -F` against the files on the branch head before this file was written (count below). The one exception is RD-01, the GitHub repository description, which is repository metadata rather than file content.
- `[owner sets: …]` marks a number the owner must supply. Auditors' suggested defaults appear inline and are judgments, not evidence.
- Amendments are grouped by document and ordered by position within each document. Where two amendments touch neighbouring text, the later one assumes the earlier has landed (see bundle 10 below for ordering).

## Bundles that must land together

These groups must land together so no document contradicts another:
1. Oracle classes: RP-06 (G2 classes 1/2/3) is the definition used by RP-14 (synthetic admissibility), RP-15 (class-1 fallback when no adjudicator), CT-04 (card oracle-class field) and CH-08 Program STOP (a) ('class-1 or class-2 oracle'). None of those four should land without RP-06.
2. G3 binding and thresholds: RP-23 (G3 bound to the preregistered threshold met by the ablated delta), RP-21 (item 7 freeze point 'before any arm is implemented or run'), RP-22 (indicative paragraph: same freeze wording, paired design, comparative regression rule), RP-20 (item 6 strata and detectability; 'pilot counts toward the two-experiment budget') and CH-08 Candidate STOP ('preregistered ablations', 'departure from PLAN.md not recorded before the holdout run') all refer to one another; landing RP-23 without RP-21/RP-22 leaves 'threshold preregistered in the approved PLAN.md' with the old dev-set tuning window.
3. Arms and fairness: RP-17 (D defined vs B and C; LLM roles), RP-16 (four arms, exception rule, non-LLM incumbent disclosure), RP-18 (equal effort, same implementer, freeze), RP-12 (baseline ladder that RP-16 and P2-02 cite as 'ladder rung' / 'baseline ladder') and P2-02 (prompt 02 arms restated with 'same LLM'). RP-16's 'no ladder rung covering the primitive' has no referent without RP-12; P2-02's 'chosen by the baseline ladder' likewise. RP-23's 'strongest fair alternative among A, B and C (in practice the better of B and C)' matches RP-17's 'primary contrast is D versus the better of B and C' and CH-08's wording; the A3 charter principle is left unchanged (do-not-change) so RP-16 carries the disclosure.
4. G1 definitions and their consumers: RP-05 (definitions and expressibility probe) is referenced by RP-09 ('named mechanism class', 'B and C cannot enforce with documented features'), RP-13 ('reuse the G1 probe encodings'), CT-03 ('reference the G1 probe encoding'), RP-10 ('natively supported (which also reopens G1)') and CH-08 Program STOP (a) ('non-trivial invariant (G1)'). RP-05's 'the strongest existing alternatives' presumes the ladder of RP-12 for its 'confirmed against incumbent documentation in the adversarial review' clause.
5. Cards, counts and screening: RP-02 (table row for every candidate, ten cards for G0 GO/HOLD, 'discovered — not carded'), RP-04 (Stage 2 screen scope), P1-04 (Deliverable C) and P1-05 (Deliverable D) state one rule in four places and must land together; CT-05's 'suggested verdict' lines and CT-02's '(G0–G2 survivors only)' assume that rule. RP-03's invariant-class split reads CT-05's new classification field; RP-01's channel list is what CT-05's 'discovery channel' records.
6. Approvals, log, caps and stopping: CH-07 (approval = DECISION_LOG entry; five approval points) is presupposed by RP-07 ('when the owner approves the shortlist'), RP-11 ('shortlist approval entry'), DL-01 (entry fields and frozen status), RP-25 (phase entry as ledger, 'cost so far against the CHARTER caps') and CH-06 (caps recorded in the phase-end ledger; 'from charter approval'). CH-08 Program STOP (c) refers to 'a cap in Scope and timebox', which exists only if CH-06 lands; CH-08 REDESIGN's 'a HOLD still open at shortlist approval counts as not passing' restates RP-07's rule and the two wordings must stay identical. CH-08 absorbs old condition (ii) into Program STOP (a); nothing else in the documents cites '(ii)' by number, and RP-07's reference is to 'the CHARTER stopping conditions' generically so the renumbering is safe.
7. Precedence: CL-01, P1-02 and P2-01 carry the same sentence ('those files govern, CHARTER.md over RESEARCH_PROTOCOL.md'); if the owner rejects the CHARTER-over-PROTOCOL order, all three must change together. P1-03's 'these counts are copies; if CHARTER.md § Scope and timebox differs, the charter governs' depends on that order.
8. Neutrality: CH-03 (sector-neutral principle) must land with RP-03 (measured split) or it becomes intent without mechanism again; P1-02 and P1-03 remove the sector lists from the prompt consistently with CH-03, and P1-03 names the charter's familiar-domain set exactly as CHARTER L30 currently lists it, so if CH-03 lands first the parenthetical in P1-03 is the only remaining copy of that list (acceptable: it is the founder-familiar set, not a preference statement).
9. Hypothesis vocabulary: CH-01 uses 'strongest fair alternative' (the G3 phrase); RP-22 keeps 'strongest baseline' and defines it per metric; RP-23 keeps 'strongest fair alternative'. Remaining variants ('strongest practical alternatives' in the Mission, 'strongest relevant incumbent solutions' in CLAUDE.md) are left as-is and are compatible with the defined terms. P1-01 ('material, measurable') matches CH-01's 'materially improves'.
10. Ordering within CHARTER: CH-05 (cases -> candidates) changes the sentence that CH-06 uses as its insertion anchor; apply CH-05 first and insert CH-06 after the amended sentence. Within the protocol, RP-02 rewrites the sentence RP-03 uses as its anchor; RP-03 is a new paragraph at the end of Stage 1 regardless.
11. Repository description (RD-01) is an owner action in GitHub settings; no README.md amendment survived, and README's 'narrow operational domain' phrasing is left alone because RP-23 fixes the unit at G3 where it matters.
12. Placeholders: CH-06 ([N] weeks, [H] hours/week, [X]/[Y] spend), RP-19 ([N] scenarios), RP-22 ([R] runs, [CI] interval) and RP-24 ([N] operators) must be filled by the owner in the approving DECISION_LOG entry before the corresponding stage runs; auditors' suggested defaults are noted inline and are not facts.

## Amendments

### CHARTER.md

#### CH-01 — § Central falsifiable hypothesis
- Closes defects: A1, K5, K19 (cluster C04, C15)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Keeps the thesis content (same object, same four outcomes) but closes the after-the-fact choice of outcome and names the per-candidate instance as the only falsifiable test; 'strongest fair alternative' is the protocol's own G3 phrase, replacing the fifth undefined comparator wording.

**BEFORE**

```text
A domain-specific representation and execution model can materially improve at least one of (a) decision correctness, (b) adaptation to changes in authoritative rules, (c) verifiability, or (d) total cost of implementation and maintenance, without unacceptable trade-offs, versus the best viable baseline.
```

**AFTER**

```text
For a selected micro-workflow, a domain-specific representation and execution model materially improves ONE primary outcome, named in the preregistered plan from (a) decision correctness, (b) adaptation to changes in authoritative rules, (c) verifiability, or (d) total cost of implementation and maintenance, with no regression on the other three beyond limits that the same plan fixes before holdout results are seen, versus the strongest fair alternative. This program-level thesis is tested only through such per-candidate instances; improvement on a non-primary outcome does not confirm it.
```

#### CH-02 — § Two possible payoffs
- Closes defects: H2 (cluster C13)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Replaces two untestable adjectives with the cheap tests they imply (one clean Claude Code session; a second small case set) and states that a technical payoff without a buyer is a valid end state.

**BEFORE**

```text
2. Technical: an independently reproducible, reusable semantic/execution primitive even without immediate commercial demand.
```

**AFTER**

```text
2. Technical: a semantic/execution primitive whose preregistered G3 effect (same direction, meeting the preregistered threshold) is re-obtained by re-running the published plan, data and code in a clean session or by a party that did not build it, on the holdout cases, with the run logged in the experiment folder. "Reusable" may be claimed only after application to a second small case set from a different workflow in the same domain; until then label it "reusability untested". Adoption is not required, and a technical payoff with no buyer is a valid end state of this program.
```

#### CH-03 — § Non-negotiable principles
- Closes defects: C3, K17, C8 (cluster C11, C15)
- Bureaucracy cost: none. Owner judgment call: yes.
- Rationale: Turns a permissive sentence that names the favored sectors into a sector-neutral principle; the measured split and any second discovery pass live in RESEARCH_PROTOCOL Stage 1 (RP-03) so procedural knobs do not require a charter amendment.

**BEFORE**

```text
- Allow domains outside telecommunications, finance, legal/governance, and enterprise software to rank highly. No inherited winner from other projects.
```

**AFTER**

```text
- No domain class is favored by construction. Diversity of candidates is judged by primary invariant class as well as industry label. No inherited winner from other projects.
```

#### CH-04 — § Non-negotiable principles
- Closes defects: K20 (cluster C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Removes an undefined proper noun without fabricating a definition for it; the generalized rule still covers whatever Sophon is.

**BEFORE**

```text
- Do not transfer an architecture from Sophon or another repository without explicitly justifying why it is needed.
```

**AFTER**

```text
- Do not transfer an architecture from any earlier project or repository (including the owner's own prior work) without explicitly justifying why it is needed.
```

#### CH-05 — § Scope and timebox
- Closes defects: K22 (cluster C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: One-word substitution removing the overload of 'cases' (candidate micro-workflows here, labeled test instances everywhere else).

**BEFORE**

```text
If 20 credible cases cannot be supported
```

**AFTER**

```text
If 20 credible candidates cannot be supported
```

#### CH-06 — § Scope and timebox
- Closes defects: I2, L2 (cluster C09)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Gives the section titled 'timebox' a timebox and gives 'budget extensions' and the protocol's 'cost so far' a baseline, with owner-filled placeholders and a single trigger; no tracker or new artifact. If CH-05 lands first, the anchor sentence reads 'candidates'.

**BEFORE**

```text
(insert after: If 20 credible cases cannot be supported, report the smaller valid number; never fabricate breadth.)
```

**AFTER**

```text
Caps (owner sets before G0 and records consumption against them in each phase-end ledger; agents report only observable usage such as tool runs and shown token counts, otherwise 'unknown'): cycle calendar <= [owner sets: N] weeks from charter approval; owner time <= [owner sets: H] hours/week; API/tool spend <= [owner sets: X] per discovery cycle and <= [owner sets: Y] per experiment. Reaching any cap ends the cycle: no further spend or new research until the owner records continue / redesign / stop in DECISION_LOG.md. Reaching a cap without a G3 GO forces the portfolio decision. An extension is approved only against a named missing fact with a bounded cost or a named positive effect under replication, never against 'more candidates might exist'.
```

#### CH-07 — § Scope and timebox
- Closes defects: L1 (cluster C10)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Defines what an approval is and fixes five phase-level approval points, reducing approvals from ~10–90 to a handful while making each auditable; 'major' is dropped so the qualifier cannot license minor self-authorized pivots.

**BEFORE**

```text
Human owner approves gates, changes to charter, test design, budget extensions, and major pivots. Agents may propose edits only as separate reviews or pull requests.
```

**AFTER**

```text
An approval is a dated DECISION_LOG.md entry committed by the owner (an agent may draft it) that states APPROVED and names its object: a document and version, the shortlist candidate IDs, an experiments/<candidate>/PLAN.md path with its budget, or a G3/G4 verdict. Chat replies, PR comments and merges do not count. Owner approval points: (1) this charter and the protocol, (2) the shortlist, (3) each experiment plan, (4) the G3 verdict, (5) the G4 verdict, plus any charter, scoring, gate or budget change and any pivot. Per-candidate G0–G2 statuses are agent proposals recorded in candidate cards and bind only through the shortlist approval. Agents may propose edits only as separate reviews or pull requests.
```

#### CH-08 — § Stopping conditions
- Closes defects: I1, B2, B1, I3 (cluster C09)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Separates candidate, search and program outcomes with a named trigger and outcome each, caps redesign at one cycle, ties (iii) to the preregistered thresholds, and absorbs the redundant condition (ii) into Program STOP (a); depends on CH-06 for the cap and RP-07 for oracle classes.

**BEFORE**

```text
Stop or redesign the search if (i) no candidate satisfies the G0–G2 requirements after one documented discovery and screening cycle, (ii) no plausible new semantic invariant survives comparison with existing engines, or (iii) two fair experiments fail to show a meaningful incremental advantage. Explicit owner approval is required for an additional cycle.
```

**AFTER**

```text
Candidate STOP (G3): in a preregistered experiment D fails to beat the strongest fair alternative among A, B and C on the primary metric, or the preregistered ablations attribute D's gain to retrieval, tools or prompting; a departure from PLAN.md not recorded before the holdout run does not excuse the result. Outcome: stop the language thesis for that domain only.
REDESIGN the search (at most once per program): a cycle yields no candidate passing G0–G2 (a HOLD still open at shortlist approval counts as not passing) AND the coverage report shows a method defect (fewer than 6 industries actually reached, named source classes unreached, run cut off before screening). Outcome: one further cycle with a documented change of sources or framing, approved by the owner.
Program STOP: (a) two independently framed cycles yield no candidate with both a non-trivial invariant (G1) and a class-1 or class-2 oracle (G2); (b) two preregistered experiments on different candidates both end in Candidate STOP, or one experiment and its preregistered replication both end in Candidate STOP; or (c) a cap in Scope and timebox is reached with no G3 GO. Outcome: close the program; reopening requires new external evidence recorded in DECISION_LOG.md. No third discovery cycle without a G2 GO.
```

### RESEARCH_PROTOCOL.md

#### RP-01 — § Stage 1 — discovery
- Closes defects: C1 (cluster C11)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Extends the channel list with outcome-shaped public sources so the candidate pool is not drawn only from the rule-text and developer/vendor stratum; the per-card channel note is placed in the card (CT-05) rather than here.

**BEFORE**

```text
Discover from operational manuals, regulations, standards, examples/contracts, GitHub issues, practitioner complaints, open-source code, vendors, buyer evidence.
```

**AFTER**

```text
Discover from operational manuals, SOPs/checklists/forms, regulations, standards, examples/contracts, incident/accident/recall reports, inspection, audit and enforcement findings, public datasets, public tenders, trade-body training material, GitHub issues, practitioner complaints, open-source code, vendors, buyer evidence.
```

#### RP-02 — § Stage 1 — discovery
- Closes defects: I6, K7, L4, F6, J5 (cluster C07, C14)
- Bureaucracy cost: none. Owner judgment call: yes.
- Rationale: Resolves the protocol/prompt conflict (card for every candidate vs ten) in the direction one deep-research run can deliver, gives uncarded rows a non-terminal status, and narrows paraphrase without banning it.

**BEFORE**

```text
For each candidate use research/01-discovery/CANDIDATE_TEMPLATE.md. Attach link, access date, applicable publication/version date, quoted or paraphrased source observation, and confidence.
```

**AFTER**

```text
Record every candidate as one row of the discovery table (the columns of prompts/01-discovery.md deliverable B, plus frequency, the G0 verdict with a one-line rationale, and the key source's publication and access dates). Complete research/01-discovery/CANDIDATE_TEMPLATE.md only for the ten best-evidenced candidates whose G0 verdict is GO or HOLD; other candidates remain 'discovered — not carded' with a one-line reason, are never marked STOP, do not count toward the CHARTER stopping conditions, may be carded later, and cannot be proposed for the shortlist. For every claim attach link, access date, applicable publication/version date, a quoted source observation (or a paraphrase marked as such with page/section locator), and confidence.
```

#### RP-03 — § Stage 1 — discovery
- Closes defects: C3 (cluster C11)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Gives CH-03's neutrality principle a measured check at the only point where it can be measured, without a quota and without self-authorizing a paid second run; lands as a new paragraph at the end of Stage 1 regardless of RP-02's rewording of the anchor sentence.

**BEFORE**

```text
(insert after: For each candidate use research/01-discovery/CANDIDATE_TEMPLATE.md.)
```

**AFTER**

```text
Report the split of discovered candidates by primary invariant class (rule-text interpretation; units/dimensions; time/sequence; resource/capacity; provenance/authority; spatial/physical safety), as recorded on each card. If rule-text interpretation dominates, state this as a coverage limitation and propose to the owner one further discovery pass framed around operational constraints and recorded outcomes; the owner decides whether to run it.
```

#### RP-04 — § Stage 2 — shortlist
- Closes defects: F6, K7, I6 (cluster C14)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Aligns the screening scope with RP-02 so 'screen every candidate' is not read as requiring G1/G2 evidence the uncarded rows cannot carry.

**BEFORE**

```text
Screen every candidate for:
```

**AFTER**

```text
Screen every candidate at G0 (on its table row) and every carded candidate at G1 and G2 for:
```

#### RP-05 — § Stage 2 — shortlist
- Closes defects: D1, E2 (cluster C07)
- Bureaucracy cost: medium. Owner judgment call: yes.
- Rationale: Replaces the subjective 'awkwardly' with binding definitions and an expressibility probe that a solo founder can run on paper before G2, giving the anti-hype side the same force as the anti-veto rule while keeping the measurable-outcome clause.

**BEFORE**

```text
G1 (language plausibility): an explicit domain-specific semantic primitive or invariant that baseline tools represent awkwardly or fail to enforce; articulate how this affects measurable outcomes. A syntax idea alone fails.
```

**AFTER**

```text
G1 (language plausibility): an explicit domain-specific semantic primitive or invariant, with a stated effect on measurable outcomes, that baseline tools demonstrably cannot express. A syntax idea alone fails. Definitions (binding for G1, ranking and G3): novel syntax = a new notation for a guarantee that an existing alternative already provides as a documented feature; novel semantics = a named mechanism class (static check, runtime invariant, effective-dated versioning, precedence resolution, provenance, units, totality, formal analysis, change propagation) that the strongest existing alternatives either cannot provide or can provide only by per-use re-implementation, shown by at least one concrete case per alternative (provisional at Stage 2; confirmed against incumbent documentation in the adversarial review); operational integration = value from connectors, UI, data or deployment, not from the representation. Evidence is the expressibility probe attached to the card: one-page (about 60-line) encoding attempts of the invariant and its three hardest counterexamples (exception, conflict, amendment) in (i) the best existing engine named on the card and (ii) a typed host language. A judge who did not write the encodings (owner, or a separately prompted agent instance; if neither is available, say so on the card) records for each encoding whether it (a) rejects the counterexample violations, (b) detects the conflict before execution, (c) confines the amendment to one edit site. If either encoding satisfies (a)–(c): STOP for the language thesis (reopening evidence: a cited counterexample the encoding mishandles). GO only if both encodings fail at least one of (a)–(c) and the card names the mechanism class and the structural property that fails and why it is structural rather than a missing library. No probe, or 'awkward' without a concrete case = HOLD. Probes are required only for carded candidates, not for the full discovery table.
```

#### RP-06 — § Stage 2 — shortlist
- Closes defects: F1 (cluster C01)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Defines 'independent' relative to arm D's authorship, names three oracle classes, makes self-labeling a HOLD rather than a silent pass, and discloses the class-1 preference as a selection filter.

**BEFORE**

```text
G2 (testability): accessible cases, independent truth oracle, fair baseline, legal access, feasible solo implementation. Make task-level dataset construction costs visible.
```

**AFTER**

```text
G2 (testability): accessible cases; a truth oracle whose reference answers are not authored or labeled by any person or artifact that builds arm D, classed as (1) mechanically computable from an authoritative artifact (official calculator, reference implementation, conformance suite, published worked answers, adjudicated decisions), (2) expert-labeled by a named adjudicator with stated cost, or (3) self-labeled by the founder or the model — class 3 cannot pass G2 (HOLD until a class-1 or class-2 oracle is identified); fair baseline; legal access; feasible solo implementation. Record the oracle class on each card. Preferring class 1 is a selection filter toward codified domains; state it in the discovery coverage report. Make task-level dataset construction costs visible in founder-hours and cash.
```

#### RP-07 — § Stage 2 — shortlist
- Closes defects: B1, I3 (cluster C09)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Gives HOLD a resolving fact, a bounded step and a review date, and fixes the cycle-close rule so an all-HOLD cycle neither runs forever nor becomes a mass kill; consistent with 'HOLD is not STOP'.

**BEFORE**

```text
Each gate is GO / HOLD / STOP, with dated rationale and reopening evidence.
```

**AFTER**

```text
Each gate is GO / HOLD / STOP, with dated rationale. A HOLD names the missing fact(s), the bounded step that would obtain each, and a review date no later than the end of the current cycle; a STOP names reopening evidence. A HOLD still open when the owner approves the shortlist counts as not passing G0–G2 for the CHARTER stopping conditions and is recorded as parked with its reopening evidence; parking is not a failure finding.
```

#### RP-08 — § Rank surviving candidates
- Closes defects: K14 (cluster C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Closes the misreading of 'Independent verifiability' (and any category) as evidence for the hypothesis without renaming a category or touching the owner's weight decision.

**BEFORE**

```text
(insert after: Score 1–5 per category, with evidence and confidence:)
```

**AFTER**

```text
Scores describe each candidate's economics, testability and context; a high score is not evidence for hypothesis (a)–(d), which only G3 can supply.
```

#### RP-09 — § Rank surviving candidates
- Closes defects: E6, J5 (cluster C07)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Anchors the 1/3/5 scale to the G1 definitions and puts an evidence floor on scores above 3 without changing the weight or the sensitivity analysis.

**BEFORE**

```text
- Incremental semantic advantage: 20%
```

**AFTER**

```text
- Incremental semantic advantage: 20% (1 = notation or integration only; 3 = named mechanism class that B or C can provide only by per-use re-implementation, i.e. library-sized; 5 = named mechanism class with at least one concrete, link-verified, quoted case — an observed failure or workaround in the current workflow, named tool or manual process — that B and C cannot enforce with documented features; argument alone caps at 3)
```

#### RP-10 — § Rank surviving candidates
- Closes defects: D4 (cluster C07)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Removes the competitor-count reading that smuggles the forbidden veto heuristic into the scorecard and anchors the category to incumbent documentation, while presenting the owner's alternative (delete the category) rather than deciding it.

**BEFORE**

```text
- Demonstrable competitive opening: 10%
```

**AFTER**

```text
- Incumbent coverage gap (technical reading; owner to confirm, else delete the category and redistribute its 10%): scored only from the best incumbent's own documentation or public issue tracker, never from the number of incumbents: 10%. 5 = invariant documented as unsupported or an open feature request; 4 = supported only via a documented workaround; 3 = supported only via custom extension code; 1 = natively supported (which also reopens G1). Not checked or 'not found' = unscored and flagged; publish the weighted total with and without this category.
```

#### RP-11 — § Rank surviving candidates
- Closes defects: L8, J5 (cluster C07, C10)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Bounds founder-side verification to at most five finalists' G0 links and their top semantic-advantage citations, ties it to the shortlist approval entry, and says what happens when a link fails.

**BEFORE**

```text
Up to five G0–G2 contenders advance.
```

**AFTER**

```text
Up to five G0–G2 contenders advance once the owner, or a separate verification run whose output the owner records, has re-opened each finalist's G0 evidence links and each citation supporting a semantic-advantage score of 4 or 5, recording each as verified / dead / misattributed in the shortlist approval entry; an unconfirmed 4–5 score resets to 3, and a finalist whose G0 evidence is dead or misattributed reverts to HOLD with that fact as its reopening evidence. Other links stay marked as agent-reported.
```

#### RP-12 — § Adversarial review
- Closes defects: E3 (cluster C06)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Forces the comparator choice to walk a ladder of tool classes with first-party citations so a solver, SQL or typed-host incumbent is not displaced by a mismatched rules engine; names classes with examples only, not capabilities.

**BEFORE**

```text
(insert after: - Find strongest existing commercial and open-source products, standards, mature DSLs, academic efforts, and actual AI-agent capabilities.)
```

**AFTER**

```text
- Walk the baseline ladder in order and record, with a first-party documentation citation, why each rung is or is not the strongest alternative for the named primitive: (1) typed data + ordinary code in a typed host language; (2) SQL/bitemporal tables or a constraint/SMT solver; (3) policy, rules or workflow engine (e.g., Cedar, OPA/Rego, CEL, DMN/Drools, BPMN/Temporal); (4) mature domain DSL or standard. Arm C is the strongest rung so identified (not necessarily the highest); if the strongest alternative is rung 1 or 2, arm B must be built with it.
```

#### RP-13 — § Adversarial review
- Closes defects: D2 (cluster C07)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Gives the only pre-experiment STOP test for a DSL-in-search-of-an-application a procedure and an artifact, reusing the G1 probe (RP-05) and excluding the speculative LLM-capability kill the charter forbids.

**BEFORE**

```text
- Determine whether product differentiation exists without a new language.
```

**AFTER**

```text
- Configuration-not-language test: reuse the G1 probe encodings to restate the finalist's proposed behaviour as (i) a ruleset or plugin on the best incumbent engine and (ii) a library plus schema in a typed host language; additionally draft (iii) an LLM prompt plus tool schema. If (i) or (ii) behaves identically on the three hardest counterexamples (deterministic behaviour readable from the encoding), record 'differentiation without language: YES' and recommend STOP LANGUAGE THESIS; the domain may remain a product candidate without a DSL (see G3). Draft (iii) is only the preregistered hypothesis for arms A/B and is never a paper STOP trigger. Any claimed difference must be labelled novel semantics or operational integration (CLAUDE.md) and named as a structural property (determinism, static verifiability, binding to the authoritative source, auditability, change propagation), never as elegance or naturalness.
```

#### RP-14 — § Experimental preregistration (before implementation)
- Closes defects: F2, F3 (cluster C01)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Breaks the circular path (rules -> generated cases -> same rules as arm D), renames a train/dev/test split that does not exist in a program that trains no model, and adds the one affordable contamination check.

**BEFORE**

```text
1. Specific task; unit of analysis; real or synthetic provenance; training/development/test separation.
```

**AFTER**

```text
1. Specific task; unit of analysis; real or synthetic provenance (synthetic cases are admissible only when the case generator is not arm D's encoding or derived from it, and their reference answers come from a class-1 or class-2 oracle per G2, never from the generator; the share of synthetic cases per stratum is declared here, and a synthetic-only holdout counts against 'credible unseen-case generalization' at G3); development/holdout separation (list every case used to build any arm; none appears in the holdout), plus a contamination check: the holdout includes perturbed twins of any public case with the oracle recomputed and/or cases governed by rules effective after the model's stated training cutoff; report results on unperturbed and perturbed public cases separately, and treat a gap between them as evidence of memorisation.
```

#### RP-15 — § Experimental preregistration (before implementation)
- Closes defects: J2, F4 (cluster C01)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Defines independence relative to arm D, fixes answers before outputs are seen (the enforceable form of blinding), and surfaces adjudication cost at the only approval point.

**BEFORE**

```text
2. Independent reference answers, qualified human adjudication where needed, uncertainty policy.
```

**AFTER**

```text
2. Reference answers independent of arm D: taken from pre-existing external outcomes, or produced from the authoritative sources alone, before arm D is built and before any arm output is seen, by a person or agent session that has not been shown D's formalization or code. Any synthetic case generator must not share D's rule model or data model. Record who or what produced the answers and when. Adjudication disputes are resolved from the authoritative source, never from D's specification. Where human adjudication is needed, name the adjudicator, their qualification and the estimated hours/cash; if none can be named, the oracle must be class 1 (G2) or the plan is not approvable. Uncertainty policy.
```

#### RP-16 — § Experimental preregistration (before implementation)
- Closes defects: B5, E4, G7, A3 (cluster C06)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Closes the 'where feasible' escape by which the person building D can drop the arm most likely to beat it, keeps a legitimate owner-approved infeasibility exception, states what G3 may then claim, and adds disclosure of an unrun non-LLM incumbent instead of rewriting the charter principle (A3).

**BEFORE**

```text
3. Four comparators where feasible:
```

**AFTER**

```text
3. Four comparators, all run under item 4's equal budgets. Omitting any arm requires a preregistered, owner-approved exception recorded here before implementation, stating either (a) that the adversarial review found, with first-party citations, no ladder rung covering the primitive — then C is recorded as 'no appropriate engine' with the engines considered and the disqualifying fact for each, C merges into B, and any G3 claim is limited to 'versus LLM plus tools and conventional code' — or (b) a documented access/license/cost infeasibility for the strongest rung, in which case the experiment may end in HOLD or STOP at G3 but not GO, G3 may not claim advantage over existing engines, and the DSL-necessity question is recorded as HOLD. Where a deployed non-LLM alternative (the current human process or a deterministic engine with human-authored rules) is plausibly the strongest practical alternative, run it as arm C or an additional arm when feasible; if it is not run, the plan says so and any G3 GO is recorded as conditional on that untested comparison:
```

#### RP-17 — § Experimental preregistration (before implementation)
- Closes defects: A2, G1, A4 (cluster C03)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Defines arm D relative to B and C using the charter's own construct list and fixes the LLM's role per arm, so the headline contrast cannot collapse into 'deterministic execution beats LLM judgment' or 'well-built B beats B'.

**BEFORE**

```text
   D. same LLM + proposed semantics (DSL syntax OPTIONAL).
```

**AFTER**

```text
   D. same LLM + proposed semantics (DSL syntax OPTIONAL). The plan names the construct(s) D adds that B lacks and that C does not already provide (an enforced invariant, a typed effect or rule-version rule, a solver or checker call, or similar) and states that D with those constructs removed is B. The D-versus-B difference measures semantic value; the D-versus-C difference measures novelty over existing engines.
   For every arm, PLAN.md states the LLM's role(s) at each stage: authoring the rule artifact from authoritative sources, extracting structured case inputs, making the runtime decision, applying rule changes. Roles, budgets and instructions are identical across B, C and D except for the named target representation; any difference in role is itself part of the mechanism under test and must be named in the plan before implementation; A's runtime role (LLM decides) is recorded as the difference it is. The primary contrast is D versus the better of B and C on the primary endpoint; D versus A alone is a floor check, not a result.
```

#### RP-18 — § Experimental preregistration (before implementation)
- Closes defects: J1, E5, G3 (cluster C02)
- Bureaucracy cost: medium. Owner judgment call: no.
- Rationale: Equalizes development effort, implementer, ordering and steelmanning across arms — the most probable false-positive route — using tools the founder already has (one agent, git commit hashes) and replacing the unbounded 'where comparable' with a logged exception.

**BEFORE**

```text
4. Same information budget, model access, runtime/tool conditions where comparable. Log exceptions, token/time/cost budgets and retries.
```

**AFTER**

```text
4. Same source documents, pinned model snapshot, runtime/tool conditions, and an equal preregistered implementation budget (agent tokens/turns and wall-clock) per arm; where a condition cannot be equalized, log it in PLAN.md before holdout with its reason and expected direction of bias. The same LLM agent with identical instructions, differing only in the named target representation, implements every arm; the owner reviews but does not hand-edit any arm, and human edits per arm are logged. B and C are built following the incumbents' own documentation, tuned only on the dev set and frozen (commit hash) before D is implemented; D is not revised after any arm's holdout results are seen. Development effort (logged hours and iteration count) on B and on C must each be at least that spent on D, or the shortfall is logged and reported with the result. Record build order; after the last arm is built, give every other arm one equal catch-up round using the same failure list, then freeze all arms before holdout. Before scoring, make one documented attempt to fix each baseline failure class by ordinary configuration or idiomatic use of that tool; failures fixed this way do not count toward D's advantage. Log every budget, retry and exception and report them with the result.
```

#### RP-19 — § Experimental preregistration (before implementation)
- Closes defects: G4, J6 (cluster C05)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Gives the >=50% maintenance threshold a unit, performer, scenario source and post-change correctness requirement, and bars edit-size proxies that a terse notation wins trivially.

**BEFORE**

```text
5. Evaluation: correctness (severity-weighted), unsupported claims, handling changes/amendments, consistency, implement/update effort, operational overhead, cost and auditability.
```

**AFTER**

```text
5. Evaluation: correctness (severity-weighted, weights fixed in PLAN.md), unsupported claims, handling changes/amendments, consistency, implement/update effort, operational overhead, cost and auditability. Maintenance effort is measured on at least [owner sets: N; auditors suggest 5] rule-change scenarios written into PLAN.md before any arm is built, drawn from actual amendments in the authoritative source where they exist and labelled synthetic otherwise, applied to each arm by the same LLM agent with the same amendment text under the same budget. Primary measure: correctness on the post-change holdout slice with no regression on unchanged cases (a scenario that regresses or exhausts the budget counts as effort = budget cap). Secondary: agent tokens/turns to reach that state, then distinct edit sites. Lines or characters changed are reported, never scored.
```

#### RP-20 — § Experimental preregistration (before implementation)
- Closes defects: F5 (cluster C05)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Imports prompt 02's six strata by reference and requires a detectability statement without fixing a universal n, so the preregistered threshold is testable at the obtainable sample size.

**BEFORE**

```text
6. Holdout cases, negative controls, ablations to isolate benefit from semantics vs prompts/tools/retrieval, and failure taxonomy.
```

**AFTER**

```text
6. Holdout cases: count per stratum (normal, exception, conflict, temporal amendment, missing data, adversarial; zero only with a stated reason) and the smallest severity-weighted error difference that count can separate from noise — if the indicative effect is below it, the run is a pilot that can yield HOLD but not GO and still counts toward the charter's two-experiment budget; negative controls, ablations to isolate benefit from semantics vs prompts/tools/retrieval, and failure taxonomy.
```

#### RP-21 — § Experimental preregistration (before implementation)
- Closes defects: B4, J3, K12 (cluster C04)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Closes the dev-set tuning window by aligning the sentence with its own section heading and requires the threshold-bearing terms to be defined where thresholds are already frozen.

**BEFORE**

```text
7. Threshold for continuation and kill conditions fixed before seeing holdout results.
```

**AFTER**

```text
7. Continuation threshold, kill conditions, severity weights and uncertainty policy, plus this task's written definitions of 'material error' (with its severity scale), 'critical regression' and the unseen-case generalization check, all fixed in this PLAN.md before any arm is implemented or run.
```

#### RP-22 — § Experimental preregistration (before implementation)
- Closes defects: G2, G5, B4, J3 (cluster C04, C05)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Keeps the 30%/50% figures as indicative defaults but gives them a form (paired design, repeated runs, per-metric strongest baseline, interval acceptance, comparative regression rule) so a GO/STOP at dozens of cases is not decided by noise or by an asymmetric single critical event; the threshold-change freeze wording now matches item 7.

**BEFORE**

```text
Indicative interesting effects (not universal pass criteria): >=30% reduction in material errors OR >=50% reduction in rule-change maintenance effort against the strongest baseline, with no critical regressions and credible unseen-case generalization. Small pilots cannot prove production reliability. Adjust thresholds only before experiment by recorded owner decision.
```

**AFTER**

```text
Indicative interesting effects (not universal pass criteria): >=30% reduction in material errors OR >=50% reduction in rule-change maintenance effort against the strongest baseline, with D's critical-severity failure count on the paired holdout not exceeding the strongest baseline's (critical classes defined in the failure taxonomy before holdout; each critical failure reported individually), any critical failure class unique to D triggering HOLD with the additional cases needed stated rather than automatic STOP, and credible unseen-case generalization. Small pilots cannot prove production reliability. Adjust thresholds only by recorded owner decision made before any arm is implemented or run.
All arms are scored on the identical holdout case set (paired design). Any arm with a nondeterministic component is run a preregistered number of times per case (minimum [owner sets: R; auditors suggest 3]) with the aggregation rule (mean, majority or worst) fixed in PLAN.md before holdout and applied to every such arm. 'Strongest baseline' is the best-performing of A–C on each metric. PLAN.md states the strongest baseline's observed error rate on development cases, the holdout N, and the acceptance form: point estimate meets the threshold AND the lower bound of a preregistered paired interval (default [owner sets: CI; auditors suggest 90%]) for the difference exceeds zero. Severity weights and the definition of 'material' are fixed before holdout. If correctness is underpowered at the obtainable N, PLAN.md says so and preregisters adaptation as the primary endpoint.
```

#### RP-23 — § G3 — technical result
- Closes defects: J3, E1, K19 (cluster C04, C08)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Binds G3 to the preregistered threshold met by the ablated semantic delta, names the unit (micro-workflow holdout), and scopes what a GO licenses so a library-form win is not read as authorization to build a surface language.

**BEFORE**

```text
GO only if the new semantic mechanism adds measurable benefit on the preregistered task beyond the strongest fair alternative and the effect plausibly generalizes within that narrow domain.
```

**AFTER**

```text
GO only if the effect attributable to the semantic mechanism, not the full pipeline, meets the threshold preregistered in the approved PLAN.md against the strongest fair alternative among A, B and C (in practice the better of B and C; D versus A alone is a floor check): every non-semantic component of D (retrieval, validators, retry loops, tools) is either present in B and C or removed in a preregistered ablation (item 6) whose result is the one scored; and the effect holds on the preregistered holdout cases of the same micro-workflow (item 6); broader generalization claims are out of scope for G3. A G3 GO is recorded as 'mechanism M improves metric X by Y over alternative R on task T (holdout N)'. It validates the semantic mechanism in whatever form D took (library, schema, checker or syntax) and does not validate a surface language. Any claim that a new language is needed requires a separate, later, owner-approved and preregistered experiment comparing D-as-language with D-as-host-library on a benefit stated in advance that a library cannot deliver (e.g., non-programmer authoring, static checks the host cannot express).
```

#### RP-24 — § G4 — strategic result
- Closes defects: H1 (cluster C13)
- Bureaucracy cost: low. Owner judgment call: yes.
- Rationale: Defines 'actual payer' as post-G3 recorded intent, enumerates G4 outcomes so it is the charter's portfolio decision, and prevents an indefinite HOLD when buyers cannot be reached.

**BEFORE**

```text
A technical kernel can be open sourced; a startup requires actual payer, route to delivery, and plausible unit economics.
```

**AFTER**

```text
A technical kernel can be open sourced. A startup thesis requires, after G3 GO and never from discovery evidence alone: (i) dated, recorded (not paraphrased or invented) responses from at least [owner sets: N; auditors suggest 3] operators in the target role who have seen the G3 result and state whether they would pilot or pay, logged as stated intent, not as payment; (ii) a route to delivery this founder can execute without enterprise procurement; (iii) plausible unit economics. G4 is the charter's portfolio decision and is recorded in DECISION_LOG.md as exactly one of STARTUP / OPEN-SOURCE RELEASE / NON-DSL PRODUCT LEAD / SHELVE with dated rationale; if operators cannot be reached within the owner-set window, the outcome is OPEN-SOURCE RELEASE or SHELVE, not an open HOLD.
```

#### RP-25 — § Integrity and reporting
- Closes defects: L6 (cluster C10)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Merges the phase ledger into the decision-log entry and names the one sources file prompt 02 consumes as 'source ledger', deleting two artifact types the founder would stop maintaining.

**BEFORE**

```text
- Each phase ends with a concise evidence ledger, counterargument, cost so far and next uncertainty.
```

**AFTER**

```text
- Each phase ends with one DECISION_LOG.md entry that is its evidence ledger: outcome, strongest counterargument, cost so far against the CHARTER caps, next uncertainty, and the path of the phase's single sources file (research/<phase>/SOURCES.md, or experiments/<candidate>/SOURCES.md for an experiment) listing all links with publication and access dates. No separate ledger documents.
```

### CLAUDE.md

#### CL-01 — § Instructions for AI coding/research agents
- Closes defects: B8 (cluster C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: A one-sentence precedence rule where agents read first is cheaper and safer than de-duplicating five restatements now; CLAUDE.md stays self-sufficient.

**BEFORE**

```text
(insert after: Before substantive work, read CHARTER.md, RESEARCH_PROTOCOL.md, and DECISION_LOG.md in full.)
```

**AFTER**

```text
Where this file or any prompt conflicts with CHARTER.md or RESEARCH_PROTOCOL.md, those files govern, CHARTER.md over RESEARCH_PROTOCOL.md; other copies are restatements.
```

### DECISION_LOG.md

#### DL-01 — § Decision Log
- Closes defects: B6 (cluster C10)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Gives CLAUDE.md's 'frozen criteria' a referent and makes the append-only log auditable with required fields; the entry is also the record of the version bump, so no separate register is needed.

**BEFORE**

```text
Append dated decision entries. Never rewrite history; supersede with a new entry.
```

**AFTER**

```text
Append dated decision entries. Never rewrite history; supersede with a new entry. Each entry states: approver and date (or Proposed); CHARTER/PROTOCOL version after the entry; file, section and before -> after text (or commit reference) of anything changed; entry superseded; effect on prior decisions; reopen condition. A document is frozen when its Status line reads APPROVED v<N> <date>; frozen text changes only by an entry here that bumps that version.
```

### research/01-discovery/CANDIDATE_TEMPLATE.md

#### CT-01 — § Candidate: [specific micro-workflow]
- Closes defects: D7 (cluster C14)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: One informational field that makes the arm-C comparator and the semantics-as-library case evidence-based rather than guessed.

**BEFORE**

```text
(insert after: Operator and economic buyer:)
```

**AFTER**

```text
Who authors and changes the governing rules today, in what artifact (code, decision table, spreadsheet, vendor UI, policy document), and how often:
```

#### CT-02 — § Candidate: [specific micro-workflow]
- Closes defects: K8 (cluster C14)
- Bureaucracy cost: low. Owner judgment call: no.
- Rationale: Adds the datum hypothesis (b) and the maintenance threshold depend on, surfaces oracle cost at G2, and scopes per-card scores to survivors so 20–30 cards are not padded.

**BEFORE**

```text
Frequency and volume:
```

**AFTER**

```text
Frequency and volume:
Rule-change frequency and issuing authority (evidence vs estimate):
Estimated case-set and oracle construction cost (hours, access, money):
Scorecard scores 1–5 per protocol category with confidence (G0–G2 survivors only):
```

#### CT-03 — § Candidate: [specific micro-workflow]
- Closes defects: E7, D5 (cluster C07)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Replaces a one-sided 'might not suffice' field with a named-alternative field and its symmetric counterpart so the card no longer argues only the pro-DSL side.

**BEFORE**

```text
Why LLM + tools / JSON + code / existing DSL might NOT suffice:
```

**AFTER**

```text
Strongest named alternative per ladder rung (typed code / SQL or solver / rules or workflow engine / domain DSL) and one concrete case per rung where it fails or must re-implement the primitive (label each observed / inferred / unknown; do not speculate to fill the line):
Strongest case that an existing engine / typed code / LLM + tools DOES suffice (name the tool, cite its documentation with URL and access date, reference the G1 probe encoding or write 'probe not attempted'):
```

#### CT-04 — § Candidate: [specific micro-workflow]
- Closes defects: F8 (cluster C01)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Mirrors the G2 oracle classes (RP-06) on the card and records the public-since date the preregistration contamination check needs, without adding a field.

**BEFORE**

```text
Potential test oracle and adjudication risks:
```

**AFTER**

```text
Test oracle — class (1 computable / 2 expert-labeled / 3 self-labeled), source, whether cases and reference answers are public and since when, and adjudication risks:
```

#### CT-05 — § Candidate: [specific micro-workflow]
- Closes defects: K8, C1, C3 (cluster C11, C14)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Dates the gate lines as the protocol requires, marks them as agent suggestions per CLAUDE.md, and adds the two classification fields that RP-01 and RP-03 report on; each BEFORE line verified separately.

**BEFORE**

```text
G0 decision and rationale: GO / HOLD / STOP
G1 decision and rationale: GO / HOLD / STOP
G2 decision and rationale: GO / HOLD / STOP
```

**AFTER**

```text
Primary invariant class (rule-text interpretation / units-dimensions / time-sequence / resource-capacity / provenance-authority / spatial-physical safety) and discovery channel (rule text / practitioner-developer / recorded outcomes):
G0 suggested verdict (GO / HOLD / STOP), date, proposer, rationale:
G1 suggested verdict (GO / HOLD / STOP), date, proposer, rationale:
G2 suggested verdict (GO / HOLD / STOP), date, proposer, rationale:
```

### prompts/01-discovery.md

#### P1-01 — § Research question
- Closes defects: K5 (cluster C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Aligns the discovery bar to the charter's adjective so candidates meeting the charter's own hypothesis are not screened against a stricter undefined one.

**BEFORE**

```text
give AI-driven software a **decisive, measurable** advantage over strong existing solutions
```

**AFTER**

```text
give AI-driven software a **material, measurable** advantage (the CHARTER.md hypothesis bar) over strong existing solutions
```

#### P1-02 — § Binding method
- Closes defects: K18, B8, C8 (cluster C11, C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Adds DECISION_LOG.md and the precedence sentence (CL-01) where the research agent actually reads, and replaces the anchoring sector list with named invariant classes while keeping both anti-kill and anti-favour directions.

**BEFORE**

```text
Read CHARTER.md and RESEARCH_PROTOCOL.md. Respect GO/HOLD/STOP gates and evidence categories. Do not prejudge telecom, contracts, regulation, governance, financial analysis, or any other domain.
```

**AFTER**

```text
Read CHARTER.md, RESEARCH_PROTOCOL.md and DECISION_LOG.md. Where this prompt conflicts with CHARTER.md or RESEARCH_PROTOCOL.md, those files govern, CHARTER.md over RESEARCH_PROTOCOL.md. Respect GO/HOLD/STOP gates and evidence categories. Do not prejudge any domain for or against. Candidates whose primitive is units/dimensions, time/sequence, capacity, provenance/authority or physical safety count equally with rule-text interpretation.
```

#### P1-03 — § Discovery scope
- Closes defects: K17, C8, L7 (cluster C11, C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Points the prompt at the charter's familiar-domain list instead of a third variant, names the non-rule-text requirement, and marks the scope numbers as copies so an owner change in the charter cannot be silently overridden by the prompt.

**BEFORE**

```text
Investigate at least 6 genuinely distinct industries, including some outside finance, telecom and governance. Aim for 20–30 narrowly specified micro-workflows. Report fewer if sources don't support them — no filler, no speculation presented as fact.
```

**AFTER**

```text
Investigate at least 6 genuinely distinct industries, including several outside the founder-familiar set named in CHARTER.md (telecommunications, finance, legal/governance, enterprise software) and candidates whose primary invariant is not rule text. Aim for 20–30 narrowly specified micro-workflows; these counts are copies, and if CHARTER.md § Scope and timebox differs, the charter governs and you must report the discrepancy. Report fewer if sources don't support them — no filler, no speculation presented as fact.
```

#### P1-04 — § Deliverables
- Closes defects: K7, I6, L4 (cluster C14)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Binds the card count to the single protocol rule (RP-02) so prompt and protocol cannot disagree.

**BEFORE**

```text
C. Detailed one-page candidate cards for the ten best-evidenced opportunities using research/01-discovery/CANDIDATE_TEMPLATE.md.
```

**AFTER**

```text
C. Detailed one-page candidate cards, using research/01-discovery/CANDIDATE_TEMPLATE.md, for the ten best-evidenced candidates whose G0 verdict is GO or HOLD (RESEARCH_PROTOCOL.md Stage 1 rule).
```

#### P1-05 — § Deliverables
- Closes defects: F6 (cluster C14)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Makes Deliverable D's scope explicit and gives uncarded rows a non-terminal status, matching RP-02 and RP-04.

**BEFORE**

```text
D. G0/G1/G2 GO/HOLD/STOP screen with citations and missing evidence, not premature declarations of competitive victory.
```

**AFTER**

```text
D. G0 verdict for every row of B, and G1/G2 GO/HOLD/STOP screen with citations and missing evidence for every carded candidate from C; each uncarded row of B is marked "discovered — not carded" with a one-line reason (never STOP), does not count toward the CHARTER stopping conditions, and may be carded later. No premature declarations of competitive victory.
```

#### P1-06 — § Final stress-test
- Closes defects: D3, K4 (cluster C12)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Replaces the speculative future-capability question that the charter forbids and that caused the founder's past premature kills with two questions answerable from dated current evidence.

**BEFORE**

```text
- Would this opportunity remain attractive if frontier AI improved substantially?
```

**AFTER**

```text
- Which currently demonstrated frontier-model capability (dated, reproducible source) already makes the proposed semantics redundant, and has it been shown on cases like this workflow's? Do not reason from how models might improve.
- Which part of the claimed advantage rests on structural properties that no model improvement changes (determinism, static verifiability, binding to the authoritative rule source, auditability, single-site change propagation), and which part rests on currently measured model error rates? Report both separately; rank on the structural part and record the model-dependent part as dated, time-sensitive evidence (neither zero nor a projection).
```

### prompts/02-adversarial-review.md

#### P2-01 — § Deep Research Prompt 02 — Adversarial finalist review
- Closes defects: K18, B8 (cluster C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Brings the stage that drafts the experiment design under the governing text, mirroring prompt 01's existing clause.

**BEFORE**

```text
(insert after: Status: HOLD — run only after human-approved shortlist and specific finalist IDs.)
```

**AFTER**

```text
Binding method: read CHARTER.md, RESEARCH_PROTOCOL.md and DECISION_LOG.md first; where this prompt conflicts with them, those files govern. Use the protocol's GO/HOLD/STOP vocabulary and evidence categories.
```

#### P2-02 — § Deep Research Prompt 02 — Adversarial finalist review
- Closes defects: K3 (cluster C03)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Restates the four arms with the 'same LLM' constant inline so a PLAN.md drafted from this prompt cannot confound semantics with LLM presence, and names the ablation the protocol relies on.

**BEFORE**

```text
(A LLM/tools; B LLM + structured code; C best incumbent rules engine/DSL; D proposed semantics)
```

**AFTER**

```text
(four arms exactly as RESEARCH_PROTOCOL.md preregistration item 3: A same frontier LLM + tools and data; B same LLM + structured schema/JSON + ordinary code; C same LLM + best existing DSL/rules engine chosen by the baseline ladder; D same LLM + proposed semantics, DSL syntax optional), with the ablations item 6 of the protocol requires
```

#### P2-03 — § Deep Research Prompt 02 — Adversarial finalist review
- Closes defects: K10 (cluster C15)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Expresses the recommendation in the protocol's GO/HOLD/STOP vocabulary and marks it as a suggestion so a bare 'GO' is not read as gate passage.

**BEFORE**

```text
8. Give one recommendation: EXPERIMENT, HOLD FOR EVIDENCE, or STOP LANGUAGE THESIS, with a reversible rationale.
```

**AFTER**

```text
8. Give one suggested recommendation in gate vocabulary (a proposal, not a gate decision): GO to preregistration, HOLD naming the missing fact, or STOP the language hypothesis for this domain, with a reversible rationale.
```

### GitHub repository description (repository metadata set in GitHub settings; not a file in README.md or elsewhere)

#### RD-01 — § (no heading)
- Closes defects: A7, K16 (cluster C08)
- Bureaucracy cost: none. Owner judgment call: no.
- Rationale: Aligns the most visible one-line framing with README and the charter's 'Outcome gap first, not language first'; owner action in repository settings, not a commit. No README.md file amendment survived review.

**BEFORE**

```text
finding a new programming language
```

**AFTER**

```text
Research program to find a narrow operational workflow where domain-specific semantics (not a language by default) measurably outperform existing AI, rules engines and conventional software. Pre-discovery; no domain or language selected.
```

## Items deliberately left unchanged

See section 6 of the main review for the full list with reasons. In short: the Mission phrase "potentially expressed as a new programming language"; the four-arm A/B/C/D structure and "DSL syntax OPTIONAL"; the two-payoff split; the scorecard weights; the indicative 30% / 50% figures; the scope counts (20–30, >=6, up to 5, up to 2); the charter principle listing the three baseline classes (the LLM-scope question is an owner decision, so disclosure was placed in RP-16 instead); CLAUDE.md's brevity; prompt 02's eight-item structure; the existing DECISION_LOG entry (append-only).

## Verification record

All 51 BEFORE texts and insertion anchors across CHARTER.md (8), RESEARCH_PROTOCOL.md (25), CLAUDE.md (1), DECISION_LOG.md (1), research/01-discovery/CANDIDATE_TEMPLATE.md (7, the three gate lines of CT-05 checked individually), prompts/01-discovery.md (6) and prompts/02-adversarial-review.md (3) were verified verbatim with grep -F against the files on branch research/initial-charter-protocol (HEAD 4a9366b, clean working tree); 51 matched, 0 failed. The one BEFORE that could not be grep-verified is RD-01, the GitHub repository description 'finding a new programming language', which is repository metadata, not file content; it was taken exactly from the task context. No repository file was edited.

Re-verification at file-generation time: 51 BEFORE anchors matched with grep -F; 0 failed.
