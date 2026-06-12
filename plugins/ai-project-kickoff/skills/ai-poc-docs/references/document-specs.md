# Per-document specifications (PoC package)

For each document, in addition to the Tecman control block, Table of Contents, Assumptions, Open Questions and a Glossary pointer, include the sections below. Cite the standard(s) the document satisfies (see `standards.md`).

## `<CODE>`-CHTR — Project Charter
Vision; objectives; scope summary; governance and stakeholders; high-level approach; indicative phases; success criteria; high-level risks.

## `<CODE>`-BRD — Business Requirements Document (ISO/IEC/IEEE 29148)
Executive summary; business context & problem statement; drivers & objectives; stakeholders; current vs future state; business requirements (`BR-nnn`, MoSCoW); success metrics & benefits; scope; constraints & dependencies; risks.

## `<CODE>`-REQ — Requirements Specification (ISO/IEC/IEEE 29148)
Functional requirements (`FR-nnn`) with acceptance criteria; non-functional requirements (`NFR-nnn`: accuracy, latency, security, scalability, auditability); each traced to a `BR-nnn`; data and interface requirements; constraints.

## `<CODE>`-SDA — Solution Design & Architecture / HLD (ISO/IEC/IEEE 42010; C4/arc42)
Current vs target architecture; component overview; integration points; data flow; NFR summary; phased approach; **architecture diagram**.

## `<CODE>`-LLD — Low-Level Design (ISO/IEC/IEEE 42010)
Component responsibilities (state language and hosting explicitly); data contracts/schemas; processing steps; AI interaction points; validation; error handling; security; an **Execution & Invocation** section; **architecture and execution diagrams**.

## `<CODE>`-AID — AI Design / Prompt + Rules Specification (ISO/IEC 42001; NIST AI RMF)
Design philosophy; prompt architecture; output schemas (Structured Outputs); rules; confidence/validation; guardrails. Schemas identical to the LLD.

## `<CODE>`-AES — AI Evaluation Strategy & Golden Dataset (ISO/IEC 42001; NIST AI RMF; ISO/IEC 23894)
Evaluation objectives; golden dataset composition; metrics; thresholds (e.g. accuracy gate); scoring; regression/drift; human-review sampling; reporting.

## `<CODE>`-DPIA — Data Protection Impact Assessment (UK GDPR / DPA 2018; ISO/IEC 27001/29134)
Data inventory; lawful basis & necessity; data flows & storage; retention & minimisation; access & security controls; risks to data subjects; mitigations; DPO review & sign-off block (`[TBC – DPO]`). State that it is a control document, not legal advice.

## `<CODE>`-RAID — RAID Log (ISO/IEC 23894)
Tabular registers: Risks (`R-nnn`), Assumptions (`A-nnn`), Issues (`I-nnn`), Dependencies (`D-nnn`), with owners. Living document.

## `<CODE>`-ADR — Architecture Decision Records (MADR practice)
One record per significant decision: `ADR-nnn`, status, context, decision, consequences, alternatives. Seed with the foundational decisions (architecture pattern, hosting, AI boundaries, human-in-the-loop gate).

## `<CODE>`-GLOS — Glossary
Canonical term, full name, definition, relevance. The terminology authority for the corpus.
