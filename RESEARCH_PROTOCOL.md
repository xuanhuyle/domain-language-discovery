# Research Protocol
Status: DRAFT v0.2 (2026-10-12) — proposed; NOT approved. Read with CHARTER.md.
This file is the only home of gate definitions, terms and procedures; CHARTER.md sets thesis, scope, caps and authority. Prompts and templates restate parts for convenience; on any conflict, CHARTER.md and this file govern and the agent stops and reports it.

## 1. Definitions
- **Micro-workflow (unit of search):** For [specific operator/buyer], given [specific inputs and governing rules or constraints], decide or perform [specific action] at [frequency], where wrong outcomes cause [measurable cost], and correctness is established by [reference-outcome path].
- **Semantic mechanism (M):** the named construct a proposal adds — for example an enforced invariant, a type or unit discipline, effective-dated rule versioning, authority/precedence resolution, provenance, exhaustiveness or conflict checking, a solver or checker call, change propagation.
- **Novel semantics vs novel syntax vs existing library vs integration:** novel semantics = M provides a measurable property that the strongest alternatives provide only with brittle per-use reimplementation, or not at all; novel syntax = new notation for a property an existing tool already provides; existing library = M is already available as a library or engine feature; integration = value from connectors, UI, data access or deployment rather than from the representation. Only novel semantics supports the thesis. A language is an optional way to package M.
- **Comparator arms** (used in experiments; see § 6):
  - **A** — frontier LLM with appropriate tools (retrieval over the same source documents, code execution where relevant); no authored domain artifact; the LLM decides at runtime.
  - **B** — LLM plus a robust structured schema and host-language code (typed data, validation, tests): the strong conventional-engineering baseline.
  - **C** — the strongest relevant existing incumbent when one materially applies: a DSL, rules or decision engine, policy language, constraint/optimization solver, workflow engine, domain standard tool, or deployed product/process. Chosen by documented fit, never because it is easy to beat.
  - **D** — the proposed semantic mechanism M, possibly hosted in ordinary code (library, schema, checker, interpreter); new syntax optional.
- **LLM role per stage:** for every arm, state whether the LLM authors the rule artifact from sources, extracts structured inputs, makes the runtime decision, applies rule changes, or is a build aid only (not present at runtime).
- **Reference-outcome provenance:**
  - **E (external):** justified by authoritative material independent of this project — official calculator or reference implementation, published worked example with answer, adjudicated decision, conformance suite, recorded real-world outcome.
  - **I (insulated):** produced from authoritative sources, with citations, by a reviewer or checker insulated from D's implementation — a person, or a separate agent session, that has not been given D's rule model. The solo founder may do this if the labels are fixed from the sources before D's rule model is written.
  - **X (exploratory):** derived from D's specification or produced with D's rule model in view. Usable for development and pilots; never conclusive.
- **Development set / holdout:** all arms are developed and tuned only on a shared development set. The holdout is frozen before any confirmatory run, is never used for tuning, and is scored once per confirmatory run.
- **Exploratory vs confirmatory:** exploratory work (pilots, tuning, X labels, synthetic-only cases) informs design and can yield HOLD, never G3 GO. A confirmatory run uses a frozen success rule, an E/I-labelled holdout and the preregistered arms.
- **Primary endpoint:** exactly one of decision correctness, change/update effort, independent verifiability, or lifecycle cost, chosen per experiment before holdout exposure.
- **Evidence labels:** observed (verifiable in a cited source), inferred, assumed, unknown.
- **Commercial evidence:** a *demand signal* (pain, workarounds, incumbent pricing, spend, buyer reachability) informs ranking; a *commercial hypothesis* is a stated buyer/price/route claim; *validation* is an actual commitment (payment, pilot, written intent). A technical result is none of these.

## 2. Stage 1 — discovery
- Search at least six substantially different industries, including sectors outside founder familiarity (scope numbers: CHARTER § Scope and timebox).
- Discover from operational manuals, SOPs/checklists/forms, regulations, standards, examples/contracts, incident/recall/inspection/enforcement reports, public datasets and tenders, trade-body material, GitHub issues, practitioner complaints, open-source code, vendors, and buyer evidence. Distinguish original sources from marketing claims.
- Record every candidate as one row of the discovery table, with a proposed G0 verdict. Complete research/01-discovery/CANDIDATE_TEMPLATE.md only for the best-evidenced candidates, up to the card limit. Uncarded rows are "discovered — not carded": never STOP, not counted in the cycle stopping condition, and may be carded later.
- For each material claim attach link, publication/version date, access date, a quotation or a paraphrase marked as such, and confidence. If a link cannot be opened, say so.
- Coverage disclosure: industries and source types reached, blind spots, and the split of candidates by primary invariant type (rule-text interpretation; units/quantities; time/sequence; capacity/resources; provenance/authority; spatial/physical safety; other). If rule-text interpretation dominates, state it as a limitation; the owner decides whether a further framed pass is warranted.

## 3. Stage 2 — screening gates (G0–G2)
Each gate verdict is GO / HOLD / STOP, proposed by the agent on the card with date and rationale. Unknown or weakly supported does NOT equal failure; unexplained optimism does NOT equal GO.
- **G0 — real outcome gap:** named operator; concrete inputs → decision → action; frequency; credible evidence of cost, errors, workarounds, spending or demand.
- **G1 — semantic plausibility (not proof):** a named primitive or invariant M with a stated effect on a measurable endpoint. Evidence is a light paper probe: in prose or at most one page of pseudo-code, show how B and the most relevant incumbent would handle M and two or three hard counterexamples (exception, conflict, rule change), and record where they need brittle per-use reimplementation, multiply edit sites, lack static checks, mishandle temporal validity, lose auditability or compose unsafely. GO = plausible measurable advantage with at least one concrete counterexample. HOLD = no probe yet or no concrete case. STOP = the strongest alternative provides the property as a documented feature at comparable cost, or the claimed advantage is syntax or aesthetics only. That an alternative *can* encode the behaviour is not by itself a STOP; hard evidence is required only at G3.
- **G2 — testability (provisional at discovery):** accessible cases; a plausible reference-outcome path of provenance E or I; legal access; feasible solo implementation; rough dataset-construction cost. At discovery G2 is marked provisional; it is confirmed in adversarial review or preregistration once the reference-outcome path is substantiated. A candidate whose only path is X is HOLD at G2. Experiment-fairness rules (§ 6) are not applied at discovery.
- Every HOLD names the missing evidence and one bounded next action. HOLD handling at cycle end: § 9.

## 4. Ranking and shortlist
Score carded G0–G2 survivors 1–5 per category, with evidence and confidence. Scores are prioritization aids, not evidence for the hypothesis.
- Economic value / existing spending: 20% — includes losses, rework and workaround labour, and early demand signals, not only vendor spend.
- Incremental semantic advantage: 20% — argument without a concrete counterexample scores at most 3.
- Workflow repeatability: 15%
- Independent verifiability: 15% — availability of E/I reference outcomes.
- Input and reference data accessibility: 10%
- Demonstrable competitive opening: 10% — a documented gap in the strongest incumbent's capability for this workflow (its own docs, issue tracker or user complaints); never the number of competitors.
- Solo-founder accessibility / founder-market fit: 10%
Publish raw scores, supporting and contradicting observations, unknowns, and ranking sensitivity (including a scenario without the founder-fit category). Propose the shortlist size set in CHARTER § Scope and timebox. Before the owner approves the shortlist, re-open each finalist's key G0 source links and mark them verified / dead / misattributed.

## 5. Adversarial review (approved finalists only)
For each finalist:
- Identify the strongest existing commercial and open-source products, standards, DSLs/engines, academic work and demonstrated AI-agent capabilities, citing their own documentation; state precisely what they do and do not do.
- Choose the candidate arm C by fit and record why other incumbent classes were not chosen; if no incumbent materially applies, record the search.
- Deepen the G1 probe on the specific counterexamples, and label each claimed difference as novel semantics, novel syntax, existing library or integration.
- Substantiate the reference-outcome path (confirm or downgrade G2) and identify adjudication needs, leakage risks and cost.
- Collect early commercial evidence without claiming validation (§ 8).
- Specify the smallest fair experiment that could reverse the ranking, as a draft PLAN.md.
- Recommend GO to preregistration / HOLD (named missing evidence) / STOP the semantic thesis for this finalist — a proposal, not a gate decision.
Do not reject because an incumbent merely exists or an LLM might theoretically do it.

## 6. Experiment preregistration (experiments/[candidate]/PLAN.md, owner-approved before implementation)
1. **Task and cases:** task; unit of analysis; case provenance (real or synthetic); development set; frozen holdout with its size and composition (normal, exception, conflict, rule change/temporal, missing data, adversarial — omit a stratum only with a reason). Synthetic cases are allowed only if the generator is not derived from D's rule model and their labels are E or I; synthetic-only results are disclosed as not establishing real-case performance. Where holdout cases come from public worked examples a frontier model may have seen, include perturbed variants (outcome recomputed) or, where such cases exist, cases effective after the model's training cutoff, and report them separately.
2. **Reference outcomes and adjudication:** provenance (E/I/X) of every holdout label; who produced them and when; who adjudicates disputes and when. Disputes are resolved from authoritative material, never by appeal to D's rule model. Confirmatory holdout labels must be E or I.
3. **Arms and LLM roles:** arms A–D as defined in § 1, with the LLM role per stage for each arm and the model version used. Roles are held the same across B, C and D except where the difference is part of the named mechanism. If C is omitted, record the search and the reason; G3 claims are then limited to the arms run.
4. **Fair comparison:** comparable data, engineering attention and competence across arms; approximate effort per arm logged and any material imbalance reported. Exact equality of tokens, turns or wall-clock is not required. Before freezing the arms, run a documented baseline-steelmanning pass on B and C against their tools' own documentation and idioms (preferably by a separate session) and fix obvious under-engineering. Log deviations from the plan before the holdout run where known, and otherwise disclose them with the result.
5. **Novelty isolation:** name M; state that D with M removed approximates B; run that ablation; list the specific counterexamples and measurable properties on which D is expected to beat B and C. A win over A alone does not establish the need for new semantics or for a language.
6. **Primary endpoint, guardrails and uncertainty:** one primary endpoint (§ 1). For correctness, define an error-severity scale. For change/update effort, use predeclared rule-change scenarios, drawn from real amendments where they exist, applied to every arm; score post-change correctness at the effort spent; report lines changed but do not score them. Name guardrails on the other endpoints (including that D must not introduce a category of critical error the strongest baseline avoids; report critical failures individually). State generalization limits, N, the baseline rate observed on development cases where relevant, the uncertainty method suited to the task (paired comparison on identical cases; repeated runs for nondeterministic arms), and the smallest meaningful difference. If the design cannot detect that difference, label the experiment exploratory.
7. **Success rule and kill condition:** written and frozen before any arm is exposed to the holdout, approved with the plan, and recorded in DECISION_LOG.md. The threshold is justified by what difference matters to the operator, not by D's development results; record the development results seen when it was frozen. Exploratory pilots may tune any arm on the development set; confirmatory runs may not change arms, labels or the rule.

Indicative interesting effects (illustrative reference points, not cutoffs): about 30% fewer material errors, or about 50% less rule-change effort, against the strongest baseline. Small pilots cannot prove production reliability. Changing a frozen success rule requires a new owner-approved plan version before holdout exposure.

## 7. G3 — technical result
- **GO:** a confirmatory run met its frozen success rule on the primary endpoint against the strongest fair alternative (the best-performing of the arms run among A, B and C); the ablation attributes the gain to M rather than to retrieval, tools, prompting or scaffolding absent from the baselines; guardrails held; holdout labels were E or I. Record it as "mechanism M improves endpoint X by Y versus alternative R on task T (holdout N)". A GO validates the mechanism in whatever form D took; it does not validate a language. A claim that a new language is needed requires a separate, later, owner-approved experiment comparing D as a language with D as a host-language library on a benefit stated in advance.
- **HOLD:** exploratory or underpowered result, or a named missing fact, with the next bounded action.
- **STOP:** the frozen rule was not met, or the gain is attributable to something other than M. The semantic thesis stops for this candidate; any remaining commercial interest is recorded as a separate lead (CHARTER § Stopping conditions).

## 8. G4 — strategic result
Evaluate three things separately: the technical result, the commercial hypothesis, and validation (§ 1). Early demand signals collected in discovery and adversarial review inform G0 and ranking. After a G3 GO the owner may pursue deeper buyer outreach; nothing counts as validation without an actual commitment. There is no fixed interview quota, and non-response is evidence about reachability, not an automatic shelving. A technical mechanism can be open-sourced without a buyer. The owner records the portfolio decision (for example pursue a product, release the technical result, continue research, or shelve) with rationale. Never claim market validation from benchmark success.

## 9. Decisions, approvals, HOLD and frozen status
- **Owner-only decisions:** CHARTER § Authority.
- **Valid approval:** an explicit owner statement in conversation, in a PR comment or review, or in a commit. The agent records it accurately in DECISION_LOG.md: date, where it was given, the owner's words or a faithful paraphrase, the object approved and its version. The owner does not need to write the entry personally. No approval by silence, implication or elapsed time; agents never approve their own proposals.
- **Agent proposals:** G0–G2 verdicts, scores, rankings and recommendations are proposals on cards and in reports; they bind only through the owner's approval of the shortlist or plan that relies on them.
- **HOLD:** names the missing evidence and one bounded next action. At the end of a cycle, unresolved HOLDs become **PARKED** with their reopening evidence: not passed, not failed, reopenable when that evidence appears. Every STOP also names reopening evidence.
- **Frozen status:** a governing document or plan is frozen once the owner approves a specific version and its Status line reads APPROVED v<N> (<date>). Later changes need a new owner-approved version recorded in DECISION_LOG.md with what changed and why.

## 10. Integrity and reporting
- Every material factual claim gets a resolvable citation or an explicit evidence gap.
- Never invent interviews, customers, pricing, sources, benchmarks or tool runs.
- State observed / inferred / assumed / unknown separately; date changing external facts.
- Append decisions to DECISION_LOG.md, including rejected alternatives and conditions for reopening; keep proposals separate from owner decisions.
- Any proposed charter, scoring or gate change requires an explicit review and owner approval; never silently edit them.
- Each phase ends with a short summary — outcome, strongest counterargument, cost so far against any owner-set caps, next uncertainty — and a single sources file for that phase.
