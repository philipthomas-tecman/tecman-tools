# Discovery / requirements-gathering questionnaire

Ask these in **small, grouped batches**, not all at once. After each batch, reflect the answers back briefly and record assumptions and open questions. Do not generate any document until discovery is confirmed. Probe where answers are vague; never assume.

## A. Project identity
- Project name; a short **document code** (3–5 letters) used as `<CODE>` in all document codes and file names.
- One-line description; sponsor; owners and their roles; reviewers.

## B. Business context
- The business problem and its drivers; the current-state process and its pain points; the desired future state; the measurable benefits sought.

## C. Scope & phasing
- In scope and out of scope; what the PoC specifically covers; intended later phases.

## D. AI solution approach
- What the AI does; where it assists versus where deterministic logic or humans decide; the proposed architecture/pipeline and its stages; the human-in-the-loop checkpoints; any reuse of existing solutions or data.

## E. Technology & hosting
- Languages and frameworks; cloud platform and services; model(s) and how they are invoked; hosting/compute choice; integration points and external systems/APIs.

## F. Data
- Inputs and outputs; formats and sources; volumes; sensitivity and any personal data; retention; whether any data is used for model training; lawful basis if relevant.

## G. Constraints & non-functional requirements
- Accuracy/quality targets; latency; security and identity; scalability; compliance considerations (ISO/IEC 42001, NIST AI RMF, UK GDPR / EU AI Act applicability); auditability.

## H. Validation
- How outputs are validated; acceptance criteria; availability of a golden/evaluation dataset; sign-off authorities.

## I. Delivery
- Timeline and milestones; budget/resourcing; key risks, assumptions and dependencies.

## J. Materials & brand assets
- Any existing discovery materials (transcripts, minutes, notes, prior specs) — request them.
- Confirm the brand logo (`tecman_logo.png`) and the Tecman style are available. If missing, request them before producing documents.

## Closing the discovery
Present: (i) a concise requirements summary; (ii) the proposed PoC document list with recommended additions/omissions and reasons; (iii) the project `<CODE>`; (iv) the applicable standards from `standards.md`. Obtain explicit go-ahead before generating any document.
