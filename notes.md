# CLAUDE.md — The Harness Books Project

Read this file before doing any work in this project. It is the single source of truth for what the book is, how it sounds, and what is locked.

**2026-07-23: Hard cutover.** The book was rebuilt on six pillars. The old ladder skeleton (legible → runnable → self-correcting → guarded → composable) is retired as the spine. Chapters from the old map survive only where they are explicitly slotted below. Do not resurrect the old structure.

## What this project is

A two-book project on agentic coding, written for working engineers.

- **Book One — the foundation.** Six pillars, one thesis: agents amplify structure, including its absence. The book teaches the reader to build an engineering system that agents cannot degrade and that learns from every agent mistake.
- **Book Two — the frontier.** Operating at scale: orchestration, multi-model setups, long-running agents, entropy and throughput. Register shifts from prescriptive to exploratory. (Thinner after the cutover — the workflow moved into Book One. Book Two's map needs re-cutting.)

The target reader for Book One is the engineer who thinks this is all hype. Win them with rigor, evidence, and restraint — never with enthusiasm.

## The six pillars (the new foundation — locked)

1. **The codebase is the interface.** Mapped modules, ownership, allowed dependencies, progressive disclosure of agent instructions — and all of it enforced in CI, not left to convention. The repository continuously proves an agent can navigate it safely.
2. **Sensors and guides create continuous engineering feedback.** Sensors observe; guides encode what the organization has learned. Recurrence is the signal: one occurrence is noise, repetition is a missing rule. The promotion loop (recurring finding → guide → enforcement) turns mistakes into permanent organizational knowledge.
3. **Traditional software engineering quality still matters — more.** Hammer the types (invalid states unrepresentable). Hammer the interfaces (control surfaces an agent can't exploit). Data-flow maps are now cheap; generate them and check them against the real code. A partially complete, continuously verified map beats a diagram that became fiction six months ago.
4. **Infrastructure matters more than ever.** Controlled runners, sandboxes, worktrees, tested backups, supply-chain rules. Design the environment as though the agent will eventually destroy something, because it will.
5. **Every agent mistake is your fault.** A repeated agent failure is evidence of a missing engineering control. Every incident feeds the flywheel: mistake → analysis → missing control → test/type/interface/guide/sensor/infrastructure improvement. Models will improve; until then, make the lint stricter. Never use future capability as an excuse for weak systems today.
6. **Agentic development requires an explicit workflow.** Research (map first) → grill and align (one-sentence goal) → plan (risk, guardrails, deterministic gates, narrow tickets) → execute (one ticket, isolated, pass or stop) → journal and strengthen. The work is not complete when the patch lands; it is complete when the system has learned from it.

## Voice (locked)

- **Terse, imperative, law-like.** Chapter titles read like laws: "Primitives Before Prompts," "Fail with Instructions," "Every Agent Mistake Is Your Fault," "Hammer Your Types."
- Clipped, rule-stating cadence. Short declarative sentences carry the argument. One hand wrote this book.
- **No history.** No model-release timelines. Chapter 1 states the premise and moves.
- Honest about open problems. The skeptical reader smells overclaiming instantly.
- Prose-first. Minimal bullets in manuscript. **Code and config blocks are now permitted** — the cutover material demands them — but only when they compress, never as decoration; one block should do the work of a page. The ASCII flow diagrams in the source docs become designed figures, not manuscript text.
- Aphorisms are load-bearing: "A backup that has never been restored is only a theory." "Repeated retries without new evidence are not progress." Coin them deliberately; don't dilute them.

## Hard rules (never violate)

1. **Never mention the internal project name, any of the Roman candidate names (Lex Imperium, Custos, Praetor, Vinculum, Ordo, etc.), or the author's internal interface specifics in manuscript text.**
   **Sentinel ruling (default, flip if wrong):** Sentinel is treated as the public companion project and may be named in manuscript. Its *concepts* are book vocabulary — observe/evaluate/render, completed-run-with-failing-verdict vs. faulted run (never conflate), typed findings, recurrence thresholds, guide candidates, code-first configuration. Its implementation internals (package layout, CLI invocations, state-file paths) stay out; show at most one illustrative config block per chapter.
2. Attribute borrowed frameworks by name (OpenAI, Stripe, Anthropic, LangChain) and clearly mark which extensions are the book's own.
3. Never quote sources at length — paraphrase; quotes must stay under 15 words and be rare.
4. Don't rest a thesis on a single vendor's post about its own product; always pair with independent corroboration. Applies to the new examples: Droid CLI agent-readiness and Shai-Hulud both need independent grounding before they carry weight in a chapter.

## Book One map (post-cutover working skeleton)

**Opening**
1. **The Bet** — agents amplify structure, including its absence. Survives unchanged as the opening.

**Part I — The Codebase Is the Interface**
2. **The Map** — module boundaries, ownership, allowed dependencies, DDD-like structure without DDD dogma. (Absorbs old "One Canonical Substrate" territory.)
3. **Progressive Disclosure** — root orientation, module-level instructions, task-level constraints. *Reframes and replaces* "AGENTS.md as the Front Door": the front-door/single-entry-point framing is retired.
4. **Agent Readiness, Enforced** — legibility as CI-checked property: AGENTS.md size limits, ownership rules, structure rules, stale-guide detection. New chapter; nothing important left to convention.
5. **Rails Before Refactors** — making an *existing* codebase the interface; migration lives here now. (Absorbs Parallel-Run Parity's parity discipline as a section, not a chapter.)

**Part II — Sensors and Guides**
6. **Guides and Sensors** — the taxonomy (drafted 2026-07-04). Survives; now a load-bearing wall, not one chapter among many.
7. **Practical Harness Engineering** — drafted. Placement inside Part II confirmed by the cutover.
8. **Fail with Instructions** — sensor output carries self-correction instructions written for model consumption. Survives.
9. **Enforce Without Blocking** — survives.
10. **From Finding to Rule** — recurrence, promotion, guide candidates; the Sentinel chapter (concept-first per rule 1 ruling).

**Part III — Engineering Quality Still Matters**
11. **Hammer Your Types** — invalid states unrepresentable; identity, transitions, protocol versions, external-vs-trusted data.
12. **Contracts at the Boundaries** — survives from the old Rails part; now "hammer your interfaces." Agents exploit ambiguity even when they don't intend to.
13. **Primitives Before Prompts** — survives with locked thesis: the surface sets the ceiling; the primitive set is not finished.
14. **Maps That Are Checked** — cheap data-flow maps, import analysis, AST queries; verified maps over fictional diagrams. (Absorbs "Materialize Decisions, Don't Infer Them.")

**Part IV — Infrastructure**
15. **Runners** — reproducible, limited, logged, cleaned up.
16. **Sandboxes and Worktrees** — minimize blast radius; one bounded workspace per task.
17. **Backups** — automatic, versioned, tested, restorable. A backup never restored is only a theory.
18. **Supply Chain and Security** — Shai-Hulud-class threats; dependency rules as friction at the exact point of risk. (Absorbs old "Security and Review Guardrails.")

**Part V — Every Agent Mistake Is Your Fault**
19. **Every Agent Mistake Is Your Fault** — the incident-to-control flywheel; the fourteen "why" questions.
20. **The Bitter Lesson** — models will improve; strengthen the system anyway. Pairs with Anthropic's "build harnesses to be dismantled."

**Part VI — The Workflow**
21. **Map First** — research produces evidence, not solutions; "just give me the map of X."
22. **Grill and Align** — shared nomenclature; the one-sentence goal; alignment prevents solving a different problem correctly.
23. **Plan for Damage** — risk, guardrails as execution constraints (repo-enforced, not prompt-trusted), deterministic gates, narrow tickets. (Absorbs "Define 'Done' a Machine Could Check" — the junior-engineer ticket standard.)
24. **One Ticket at a Time** — smallest valid change, pass or stop; never weaken a failing check to get green. (Absorbs "Small Chunks, Delete Last.")
25. **Journal and Promote** — the ledger; Tickets v2 = Tickets v1 + Journal + New Guardrails; the task is complete when the system has learned.

**Closing**
26. **The Highest-Leverage Move** — survives: the promotion loop as the human's core act; the complete loop as an operating system for future agents.

**Retired from Book One:** Deterministic Build and Run, The Test Harness Is the Feedback Loop, Style and Validation as Instant Guardrails (their material dissolves into Parts I, II, and IV as sections — they no longer earn chapters), Quarantine the Exceptions (fold into Ch. 12 or cut), Observability as the Agent's Eyes (fold into runners/sensors or Book Two).

## Source canon (the evidence base)

- **Thoughtworks / martinfowler.com** — guides vs. sensors, computational vs. inferential, drift sensors, regulation targets, harnessability, Ashby's Law. The reference definition of "harness."
- **OpenAI, "Harness engineering" (Feb 2026)** — origin of the term as used here. Use with corroboration, never alone.
- **Stripe "Minions"** — unattended agents, 1,000+ merged PRs/week, pre-warmed devboxes, blueprints. Proof of environment investment.
- **Anthropic long-running-agent posts (Nov 2025, Mar 2026)** — session amnesia, structured handoff files, "build harnesses to be dismantled." Backbone of Ch. 20.
- **LangChain Terminal Bench 2.0** — same model, harness as the only variable, 52.8% → 66.5%. The answer to "isn't this just the model getting better?"
- **Vercel tool-deletion result** — deleting 80% of tools improved results.
- **Droid CLI agent-readiness** *(new)* — example of evaluating repo structure for agent consumption. Needs independent corroboration before load-bearing use (rule 4).
- **Shai-Hulud** *(new)* — the supply-chain threat class for Ch. 18. Ground factually; the skeptic will check.
- **Counter-evidence to engage honestly:** METR developer-slowdown study, GitClear churn data, DORA trust findings.
- Full synthesis: `harness-engineering-research-report.md` (July 2026, "Breaking down into principles" chat).

## Open questions the book may claim as territory

Harness coherence as it grows; whether silent sensors mean quality or blindness; a mutation-testing equivalent for harness coverage; the unsolved behavior-regulation problem. The cutover adds: what a complete agent-readiness standard looks like, and whether the finding→guide promotion loop can itself be automated safely.

## Working conventions for Claude in this project

- Search past project conversations before drafting; research and voice decisions live there.
- The two cutover documents ("Radical Book Cutover" and "The Agent Workflow") are source material for Parts I–VI; convert their bullets to prose per the locked voice.
- Deliver chapters as .md files in outputs. Match the locked voice; when in doubt, terser.
- End drafted chapters with a brief source note separating borrowed frame from the book's extensions.
- Flag structural consequences of any new chapter (renumbering, part balance) rather than silently absorbing them.
- Book Two's map is stale post-cutover; re-cut it before drafting anything for Book Two.   q
