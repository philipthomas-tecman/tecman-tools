---
name: tecman-docx
description: Create or restyle Microsoft Word (.docx) documents to the Tecman house style and brand. Use for charters, business requirements documents, requirements specifications, solution designs (HLD), low-level designs (LLD), prompt/rules specifications, AI evaluation strategies, DPIAs, RAID logs, ADRs, glossaries, reports, memos and similar deliverables that must carry Tecman branding. Produces A4 Arial documents with the tecman logo (large on the title page, small right-aligned in the running header), the teal heading palette, a Document Control table, a Change History table, a live Table-of-Contents field, branded tables and code blocks, and a footer carrying the document title and page number. Trigger whenever the user asks for a Tecman-branded Word document, a document "in the Tecman style/standard", or to restyle an existing document to the Tecman standard.
---

# Tecman .docx generation

Generate Microsoft Word documents in the Tecman house style. A python-docx helper
library and the master logo are bundled, so output is consistent and turnkey.

## When to use
Use whenever a deliverable must be a `.docx` in the Tecman brand — new documents or
restyling existing content. For document *content* structure on AI-engineering
projects, combine with the project's documentation prompts; this skill governs
**format and layout only**.

## Bundled assets
- `assets/tecman_logo.png` — master logo; embedded automatically (do not recreate or recolour it).
- `scripts/tecman_docx.py` — helper library implementing the full standard.

## Requirements
- Python 3 with `python-docx` (`pip install python-docx`).
- Optional: Graphviz (`dot`) for diagrams.

## How to generate
Import the helper, set author/reviewers, build the document with the helpers, and save.
The logo, fonts, palette, header and footer are applied automatically.

```python
import sys
sys.path.insert(0, r"<path-to-skill>/scripts")   # e.g. ~/.claude/skills/tecman-docx/scripts
import tecman_docx as T

T.AUTHOR = "Jane Smith"
T.REVIEWERS = "A. Reviewer, B. Reviewer"

T.new_document("AI Handy Mapper — Project Charter")          # sets page, header logo, footer
T.control_block(
    "Project Charter",            # title
    "AIHM-CHTR",                  # document code
    "AI Handy Mapper",            # subtitle
    "1.0",                        # version
    "Draft for review",           # status
    "Phase 1 (PoC)",              # scope / phase
    "BRD; Requirements; Solution Design",   # related documents
    [["1.0", T.DATESTR, T.AUTHOR, "Initial issue."]],        # change history rows
)
T.heading("1. Purpose", 1)
T.para("Body text renders in Arial 11pt.")
T.heading("1.1 Detail", 2)
T.bullets(["First point.", "Second point."])
T.table(["Field", "Detail"], [["A", "1"], ["B", "2"]], [3000, 6026])
T.code('{ "example": true }')
T.figure(r"diagram.png", 6.3, "Figure 1 — Example diagram.")
T.save("Project_Charter.docx")
```

## Helper reference
- `new_document(title)` — new doc with A4 page, Arial base, header logo, footer (title + page number).
- `control_block(title, code, subtitle, version, status, scope, related, change_rows)` — title block + Document Control table + Change History table + Contents field.
- `heading(text, level)` — level 1/2/3 (teal ramp).
- `para(text=..., runs=[(text,bold)...], bold, italic, size, color, align)` — paragraph.
- `bullets(items)` / `numbered(items)` — lists (items may be `[(text,bold),...]` runs).
- `code(src)` — monospaced code box with teal left border.
- `table(headers, rows, widths)` — branded table; widths auto-scale to the content width.
- `figure(path, width_in, caption)` — centred image with italic caption.
- `page_break()`, `save(path)`.
- Module globals: `AUTHOR`, `REVIEWERS` (set before `control_block`); `DATESTR` (defaults to today); `CW` (content width in twips).

## House style (enforced by the library)
- A4, 2.5 cm (1 in) margins; Arial throughout (body 11 pt); Consolas for code.
- Logo: large on the title page, small right-aligned in the header.
- Palette: title `#005F66`; H1 `#1A3234` (16 pt), H2 `#005F66` (13 pt), H3 `#007A83` (12 pt); subtitle `#007A83`; taglines/footer `#5A7C80`; table header fill `#005F66` with white text; alternate rows `#E7F1F2`; code background `#F1F5F6` with `#007A83` left border.
- Structure: title block → Document Control → Change History → Contents field → decimal-numbered body (≤ 3 levels) → Assumptions / Open Questions where relevant.
- Footer: document title (left) + "Page N" (right) in `#5A7C80` 8 pt.

## Diagrams
Produce real figures (not ASCII) with Graphviz in the brand palette, then embed with `figure(...)`. Suggested node roles: deterministic/code `#005F66`; AI/model `#00A5B5`; human-in-the-loop `#1A3234`; external systems `#5A7C80`; inputs/light fills `#E7F1F2`; arrows `#5A7C80`.

## Conventions
- UK English; serious, concise tone. Document codes `<PRJ>-XXX`; traceability IDs `BR-`, `FR-`, `NFR-`, `R-`, `A-`, `ADR-`, `TC-`.
- File naming `<Project>_<ShortName>.docx`; versions `v0.x` draft, `v1.0` first approved.
- The Contents is a live Word field — it must be updated in Word (or on print) to populate page numbers.
