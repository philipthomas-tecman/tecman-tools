---
name: ai-poc-docs
description: Standard process for starting a new in-house AI project. Run requirements gathering, capture every decision as granular working markdown in docs/ (the version-controlled source of truth), and at each review gate render the Tecman-branded document package (.docx) from that markdown using the tecman-docx plugin. Use when starting a new AI project, kicking off discovery/requirements, or when the user runs /new-ai-project. The PoC gate package includes the LLD; production-only documents are produced at the production gate.
---

# AI project kickoff — two-layer documentation standard

A repeatable, gated process with **two layers** (full detail in `references/gate-taxonomy.md`):

- **Working layer** — granular markdown in `docs/`. The source of truth: version-controlled, updated in the *same turn* a decision is made, read directly by build sessions. All authoring happens here.
- **Gate package** — Tecman-branded `.docx` in `gates/<gate>/`, **rendered from the markdown** at each review gate (PoC, then production) with the `tecman-docx` plugin. Never hand-authored.

## Operating rules

- Precise, structured, **UK English**, serious and concise. AI is assistive; preserve a mandatory human-in-the-loop. Do not fabricate — mark unknowns `[TBC – owner]`.
- **Persist every decision in the relevant `docs/` markdown file in the same turn it is made.** No decision exists until it is written down; never let the docs and the conversation drift.
- Do not pick an architecture or write code until the engineer confirms. Record options and rejected alternatives as ADRs (Nygard format).
- Adhere to `references/standards.md`; cite the relevant standard where it applies.
- **Verify, don't assert** — for Microsoft technologies use the Microsoft Learn MCP tools and check before advising; cite the URLs.
- Render gate packages **only** with the `tecman-docx` plugin. If it is not installed, tell the user and stop.

## Step 1 — Scaffold (turn 1, before discussion)

Create the working structure from `references/gate-taxonomy.md` with placeholder files (a single H1 + `Status: not yet started`), the `adr/` folder, a seeded `CLAUDE.md` (operating principles below), and a short `README.md` pointing into `docs/`. Commit it, so the index is real from the start.

Seed `CLAUDE.md` with at least: verify-don't-assert (name the Microsoft Learn MCP and web search as the verification path); setup friction is a primary requirement; separate before sharing (don't force one primitive to serve two needs); persist decisions in `docs/` in the same turn. Extend it whenever a principle worth preserving is agreed.

## Step 2 — Discovery & capture (ongoing)

Gather requirements (topics in `references/discovery-questionnaire.md`). **Elicitation style is flexible** — one focused question at a time, or grouped batches, as the engineer prefers — but **capture each agreed point into the relevant `docs/` markdown file in the same turn**. Push back on vague answers and on requirements/solution conflation; name the conflation. Surface tradeoffs. Establish the project name and a 3–5 letter document code `<CODE>`.

## Step 3 — Gate render (at each review gate)

When a gate is reached, render the Tecman-branded package from the working markdown per the taxonomy and roll-up mapping in `references/gate-taxonomy.md` and the section outlines in `references/document-specs.md`. Output to `gates/<gate>/`. The PoC gate **includes the LLD**. Re-render the whole package from current markdown; never edit a `.docx` by hand. (The `/render-gate-package` command performs this.)

## Scope

This skill covers discovery → working markdown → PoC gate package, with the production-gate taxonomy defined for later. Production-only documents (security/threat model, test plan, operations, ISO/IEC 42001 alignment, etc.) are produced at the production gate.

## References (read as needed)

- `references/gate-taxonomy.md` — the two-layer model, working structure, gate taxonomy and roll-up rules (**read first**).
- `references/standards.md` — industry standards and best practices to adhere to (**mandatory**).
- `references/discovery-questionnaire.md` — discovery topics.
- `references/document-specs.md` — required sections for each rendered document.
