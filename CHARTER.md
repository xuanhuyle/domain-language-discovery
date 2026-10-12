# Research Charter — Domain Language Discovery
Status: DRAFT — requires owner approval before any research gate is declared passed.
Version: 0.1 (2026-10-12)

## Mission
Identify one narrow, repeatable and economically meaningful operational workflow in which explicit domain-specific semantics, potentially expressed as a new programming language, produce a measurable advantage over the strongest practical alternatives.

This is a discovery program, not a commitment to design a compiler, sell a DSL, or enter any predetermined industry.

## Central falsifiable hypothesis
A domain-specific representation and execution model can materially improve at least one of (a) decision correctness, (b) adaptation to changes in authoritative rules, (c) verifiability, or (d) total cost of implementation and maintenance, without unacceptable trade-offs, versus the best viable baseline.

The hypothesis is NOT that LLMs are incapable, that programming languages are inherently defensible, or that a new syntax is valuable.

## Two possible payoffs
1. Commercial: a narrow workflow product with a clear buyer, spend, distribution path, and differentiated results.
2. Technical: an independently reproducible, reusable semantic/execution primitive even without immediate commercial demand.
Keep these evaluations separate. A technical success is not automatically a startup.

## Non-negotiable principles
- Outcome gap first, not language first.
- Incumbents and frontier labs are baseline evidence, not automatic rejection grounds. Equally, their theoretical future capabilities are not evidence.
- A purpose-built DSL must beat credible alternatives: LLM plus tools; typed JSON/schema and conventional code; and the most relevant mature DSL/rules engine.
- Test the value of semantics, types, constraints, execution, and verification — NOT aesthetics of syntax.
- Separate observed facts, inferences, and assumptions. Cite original sources, dates, and accessibility limitations.
- Admit unknowns. HOLD is not STOP. Lack of discoverable evidence is not evidence of absence.
- Test on unseen cases, with independently established reference outcomes and explicit failure modes.
- Favor reproducible public-domain or legitimately accessible inputs. Do not infer private enterprise data access.
- Respect solo-founder constraints: limited coding background, AI-assisted implementation, limited distribution, and low experiment budget.
- Allow domains outside telecommunications, finance, legal/governance, and enterprise software to rank highly. No inherited winner from other projects.
- Do not transfer an architecture from Sophon or another repository without explicitly justifying why it is needed.
- No language/compiler/platform implementation before G2 approval. Rule sketches and paper prototypes are allowed.
- No self-authorized pivot, no moving experimental goalposts, no retroactive success criteria.
- No claim that our mechanism is proprietary or defensible merely because its syntax is new.

## Scope and timebox
One discovery cycle: target 20–30 credible micro-workflows from >=6 distinct industries; shortlist up to 5; perform up to 2 narrow experiments; then make a portfolio decision.
If 20 credible cases cannot be supported, report the smaller valid number; never fabricate breadth.
Human owner approves gates, changes to charter, test design, budget extensions, and major pivots. Agents may propose edits only as separate reviews or pull requests.

## Definition of progress
Progress means reduction of a specified uncertainty backed by auditable evidence, not number of agents, pages, diagrams, tokens, commits or tests.

## Stopping conditions
Stop or redesign the search if (i) no candidate satisfies the G0–G2 requirements after one documented discovery and screening cycle, (ii) no plausible new semantic invariant survives comparison with existing engines, or (iii) two fair experiments fail to show a meaningful incremental advantage. Explicit owner approval is required for an additional cycle.

## Current position
Pre-G0. No preferred industry, target user, language specification, architecture, or startup thesis has been approved.
