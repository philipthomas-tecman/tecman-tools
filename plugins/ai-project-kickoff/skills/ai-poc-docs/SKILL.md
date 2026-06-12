---
name: ai-poc-docs
description: Kick off a new AI project — run a structured requirements-gathering (discovery) exercise with the engineer, then generate the Proof-of-Concept documentation package (Charter, BRD, Requirements, Solution Design, LLD, AI Design/Prompt spec, AI Evaluation Strategy, DPIA, RAID, ADRs, Glossary) to the Tecman house style, adhering to the industry standards and best practices in references/standards.md. Use when starting a new AI project, scaffolding project documentation, or when the user runs /new-ai-project. Defers the production documentation corpus until deployment.
---

# AI project kickoff — discovery to PoC documentation

A repeatable, gated procedure for starting a new AI project: gather requirements, then generate the Proof-of-Concept (PoC) documentation package to the Tecman standard, held to defined industry standards.

## Operating rules

- Be precise, structured, **UK English**, serious and concise. AI is assistive; preserve a mandatory human-in-the-loop. Do not fabricate — mark unknowns `[TBC – owner]`.
- **Adhere to `references/standards.md`** (mandatory) and cite the relevant standard in each document.
- **Format every document with the `tecman-docx` plugin/skill** (A4, Arial, teal palette, logo, Document Control + Change History tables, contents field, branded tables/code, footer). Do not invent a different style. If `tecman-docx` is not installed, tell the user and stop.
- For Microsoft technologies, if the Microsoft Learn MCP tools are available, research current guidance before design decisions and cite the URLs.
- Two phases with a **gate** between them. Do not pass the gate without the engineer's explicit go-ahead.

## Phase 0 — Discovery / requirements gathering (no documents yet)

Interview the engineer using `references/discovery-questionnaire.md`. Ask in small grouped batches; reflect answers back after each; capture assumptions and open questions. Establish the project name and a 3–5 letter document code `<CODE>`. Confirm the brand logo (`tecman_logo.png`) is available.

End Phase 0 by presenting: (i) a concise requirements summary; (ii) the proposed PoC document list with any recommended additions/omissions and reasons; (iii) the project `<CODE>`; and (iv) the standards that apply. **Get explicit go-ahead before Phase 1.**

## Phase 1 — Generate the PoC documentation package (after go-ahead)

Produce the documents below (tailor to the project; justify any omission), each to the Tecman house style and each citing the standard(s) it satisfies. Required sections are in `references/document-specs.md`. Replace `<CODE>` with the project code.

| Code | Document | Primary standard(s) |
|------|----------|---------------------|
| `<CODE>-CHTR` | Project Charter | PMBOK / PRINCE2 practice |
| `<CODE>-BRD` | Business Requirements Document | ISO/IEC/IEEE 29148 |
| `<CODE>-REQ` | Requirements Specification (FR/NFR) | ISO/IEC/IEEE 29148 |
| `<CODE>-SDA` | Solution Design & Architecture (HLD) | ISO/IEC/IEEE 42010; C4 / arc42 |
| `<CODE>-LLD` | Low-Level Design | ISO/IEC/IEEE 42010 |
| `<CODE>-AID` | AI Design / Prompt + Rules Specification | ISO/IEC 42001; NIST AI RMF |
| `<CODE>-AES` | AI Evaluation Strategy & Golden Dataset | ISO/IEC 42001; NIST AI RMF; ISO/IEC 23894 |
| `<CODE>-DPIA` | Data Protection Impact Assessment | UK GDPR / DPA 2018; ISO/IEC 27001 |
| `<CODE>-RAID` | RAID Log (living) | ISO/IEC 23894 (risk) |
| `<CODE>-ADR` | Architecture Decision Records (living) | MADR practice |
| `<CODE>-GLOS` | Glossary | — |

Produce diagrams as **real figures** (Graphviz, brand teal palette) and embed them with numbered captions. **Verify** each document against the house-style checklist and confirm cross-references resolve before presenting. Maintain a short corpus index. Respect the gate.

## Out of scope

The **production documentation corpus** (ICD, data architecture, security/threat model, responsible-AI/model card, AI governance, test strategy, traceability matrix, release/runbook/monitoring/DR/change-management). Generate that later from the project's production-corpus prompt when ready to deploy.

## References (read as needed)

- `references/standards.md` — the industry standards and best practices to adhere to (**mandatory**).
- `references/discovery-questionnaire.md` — the grouped discovery questions.
- `references/document-specs.md` — per-document required sections.
