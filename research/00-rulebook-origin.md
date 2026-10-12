# Origin note — the Rulebook transposition problem (motivating hypothesis)

Date: 2026-10-12. Status: context for discovery; NOT an approved direction, a gate result, or evidence of need or demand.
Sources: owner statement in prompts/02-rulebook-origin-discovery-scope.md (Task 002); github.com/xuanhuyle/rulebook at commit `0e0e1cc` (2026-09-11), files `README.md`, `plan/research-plan-parts-I-V.md` Part IV (§§ IV.1–IV.13), and `execution-01/execution-01-checkpoint-census.md`. The Sophon charter was not consulted and nothing from it is imported.

## 1. Where the idea comes from
The owner's starting point (owner statement, not a Rulebook claim): human-written contractual or regulatory requirements must be located, interpreted, bound to operational data, reconciled, validated, approved, encoded and maintained under amendments. That raised the question whether a purpose-built language for one family of contracts, possibly credit agreements, could cut cost or errors, and whether it could also verify an implementation back against the applicable contract. The owner does not yet know whether a new language is needed, whether an existing legal language suffices, or whether the bottleneck is elsewhere.

Scope caution: Rulebook Part IV is about making AI agents' authority track policies, contracts and service levels. It does not discuss credit agreements, a domain-specific language, or language design. Carrying its analysis over to a contract-family language is the owner's extrapolation.

## 2. What Rulebook says, and what kind of statement each is

| Rulebook statement | Location | Kind |
|---|---|---|
| Turning a policy into a control involves nine steps; "Only one of them is 'encoding'." | plan § IV.2 | Analysis |
| "The bottleneck is interpretation, binding, control-type choice and ownership"; automating encoding alone addresses "the easy tenth". | plan § IV.2 | Analysis |
| Lists what plausibly automates (locating, structural extraction, effective dates, encoding once interpretation and binding are fixed, change detection) and what does not (open-textured terms, missing predicates, priority between documents, accountability). | plan § IV.4 | Analysis |
| "Contracts and service levels are mostly obligations toward counterparties plus a few prohibitions." Contract lifecycle tools did not reach enforcement "because the operational systems had no hooks". | plan § IV.7 | Analysis; no source cited |
| On amendment: "A changed definition alters the meaning of unchanged clauses, so impact is non-local"; effective dates, per-counterparty versions, and "in force" being "a legal fact that is not in the document". | plan § IV.8 | Analysis |
| Nine reasons the thesis could fail, including "The predicates are not in the systems" and "Amendment velocity is low". | plan § IV.9 | Analysis |
| No existing category does "continuous, traceable derivation from the natural-language source to enforceable authority". | plan § IV.10 | Claim; not verified there or here |
| A governance layer must make every decision cite its clauses and map every clause to its controls, and publish the "coverage residual". | plan § IV.11, item 4 | Design requirement |
| A smallest experiment: about 100 rules, about ten amendments, a sealed oracle of about 600 actions, manual versus assisted versus derived arms. | plan § IV.12 | Plan; not run |
| Execution 01 tested Part V's question (the authority share of agent checkpoints), not Part IV. Result: "C. INSUFFICIENT EVIDENCE"; "The census as specified was not executable"; real-item agreement on authority versus not was Cohen's kappa 0.56. | execution-01/execution-01-checkpoint-census.md §§ 5, 8, Status | Observed, about public evidence availability only |

Nothing above is empirical evidence that a new language, or any derivation tool, works, or that buyers want one. README states the plan is "frozen and approved"; that describes Rulebook's own governance, not validation.

## 3. The nine steps, and what a language could address
Rulebook's own automatability verdicts are in plan § IV.2. The last column is this program's working hypothesis, to be tested.

| Step | Nature of the work | Could a language or semantic mechanism help? |
|---|---|---|
| Locate | Retrieval over a bounded corpus | Little; a search and structure problem |
| Interpret | Deciding meaning in context | No. It can only make a chosen interpretation explicit and testable |
| Bind | Mapping predicates to data, or finding none exists | Partly: typed predicate declarations can expose missing data, but cannot create it |
| Choose control type | Risk appetite and policy choice | No |
| Encode | Writing the chosen rule in an executable form | Yes; the step a language targets directly |
| Reconcile | Precedence, exceptions, conflicts | Partly: precedence and exception semantics, conflict checks |
| Validate | Testing intended behaviour | Partly: generated tests; the oracle is still interpretation |
| Own | Named accountability | No |
| Maintain | Detecting change and redoing the above | Partly: effective dating, dependency impact; the redo inherits every row |

Syntax and encoding are one row. Interpretation, missing operational predicates, legal authority (what is in force) and accountability are the residual a language cannot remove.

## 4. Two-way requirement (owner-stated)
- **Forward:** from a document or amendment to the implementation it should change — which calculations, checks or controls, and from when.
- **Reverse:** from a change in the implementation back to the current in-force source — which clauses it implements, and whether it is still compatible with them.
Rulebook's closest analogues are clause-to-control traceability (§ IV.11 item 4) and change propagation (§ IV.8).

## 5. Competing hypotheses
- **H1.** A family-specific language or semantic mechanism has measurable incremental value. Favoured if a family-specific construct, for example agreement-defined terms that change by amendment, makes B and existing legal DSLs need brittle per-use reimplementation, and an experiment shows fewer errors or less amendment effort, or a working reverse check.
- **H2.** An existing legal DSL (for example Catala, L4, Symboleo, the Accord Project), a typed schema plus host-language library, or conventional engineering gives the same advantage. Favoured if their first-party documentation and a paper probe show the construct handled at comparable cost and with comparable checks, or if existing operational tools already do the job.
- **H3.** The main obstacle is interpretation, data binding, process or governance, so a language does not solve it. Favoured if evidence locates most cost or error in disputed meaning, missing data, approvals or ownership, leaving a language only the encoding row.
The three are not mutually exclusive, and none has evidence yet.

## 6. Scope limits
- Credit agreements are a concrete starting case, not an approved winner or a demonstrated need.
- This note does not change any gate, scoring weight, baseline or threshold (RESEARCH_PROTOCOL.md governs).
- Discovery treats this as one stream among two; see prompts/01-discovery.md § Discovery streams.
