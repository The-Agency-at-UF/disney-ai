---
name: disney-presentation-transformation
description: Transform basic or minimally formatted PowerPoint presentations into Disney Advertising-aligned presentations using the approved DA_Generic_Template_2025-3.pptx template. Use when a user supplies a source deck and asks to apply the Disney Advertising presentation design system.
---

# Disney Advertising Presentation Transformation

## Purpose
Transform a user-provided PowerPoint presentation containing basic or minimally formatted content into a polished, editable `.pptx` aligned as closely as practical with the approved Disney Advertising presentation template. This is an AI-assisted prototype workflow, not a guarantee of pixel-perfect reproduction. Every output requires human review before distribution.

## Required resources
- **Approved design source:** the validated original `DA_Generic_Template_2025-3.pptx`, or the bundled `assets/Disney_Template_Slim.pptx` fallback (relative to this SKILL.md). See "Template source".
- **Source presentation:** A `.pptx` provided by the user for transformation.
- **Optional:** Additional guidance in `references/`, example input/output decks in `assets/`, and validated utilities in `scripts/` when present.

Do not assume that optional directories contain specific files. Do not infer brand colors, fonts, or layout specifications from the project brief or statement of work; derive them from the actual approved template and any supplied brand guidance.

## Template source
The full original template (`originals/DA_Generic_Template_2025-3.pptx`, about 560 MB) lives in the private `disney-ai` repo under Git LFS. A slim copy is bundled at `assets/Disney_Template_Slim.pptx` (chart workbooks removed, some slide-level hero images still grey).

1. Try the original: clone or pull the repo, then run `git lfs pull` for that file. Use only a read-only credential supplied at runtime; never write tokens into the repo or the skill.
2. Validate it before use: the file must be larger than 1 KB, must not start with `version https://git-lfs`, must open in python-pptx, and must have 144 slides.
3. If validation fails or the fetch is blocked, stop using the original. Use `assets/Disney_Template_Slim.pptx` and tell the user that backgrounds are reduced quality and the output needs extra visual review.
4. Never silently build from a pointer file or an unvalidated download.

## Workflow

### 1. Validate inputs
1. Locate and open the validated template from "Template source".
2. Locate and open the user-provided source deck.
3. Verify that both are readable and that a presentation editing/export capability is available.
4. If the approved template or source deck is missing, request the missing file rather than inventing its contents or visual standards.
5. If the source contains unclear, contradictory, or incomplete content that materially affects interpretation, request clarification or mark it for human review.

### 2. Analyze the approved template
Inspect slide dimensions, masters/layouts, theme colors, fonts, title and body hierarchies, spacing, alignment, image treatments, chart/table styles, headers/footers, section dividers, callouts, and recurring compositions. Build an internal layout inventory that maps each supported slide type to an existing approved layout or representative template slide. Consult any relevant files in `references/` if present. Prefer the actual template over generic presentation-design conventions.

### 3. Interpret source content
For each source slide, identify:
- Slide title, main message, supporting points, and hierarchy.
- Content type (e.g., title, section divider, text, comparison, timeline, chart, table, image, or summary).
- Data, citations, labels, footnotes, and relevant speaker notes.
- Content or relationships that must remain intact.

Preserve factual claims, figures, units, names, dates, quotations, source attributions, and intended meaning. Do not invent facts, statistics, imagery, or brand rules. Do not silently omit source content. Minor copy edits for clarity are permitted only when they do not change meaning; flag substantive changes for approval.

### 4. Select layouts and transform
1. Match each source slide to the most appropriate approved layout based on content and communicative purpose.
2. Prefer reusing approved layouts, slide masters, placeholders, and editable native PowerPoint elements over recreating the appearance from scratch.
3. Apply the template's typography, colors, spacing, alignment, visual hierarchy, and graphical conventions.
4. Fit content without clipping, overlap, or unreadably small text. When necessary, split content across additional slides or recommend a manual redesign rather than deleting information.
5. Preserve charts and tables as editable elements when practical, including their data and labels. Do not change values or chart interpretation.
6. Use only approved or user-supplied images and assets when available. Do not add unapproved Disney artwork, logos, or other branded material.
7. Keep slide dimensions consistent with the approved template unless the user explicitly requests otherwise.

### 5. Generate the output
Create a new editable `.pptx` file; never overwrite the approved template or original source deck. Name the output `<source-name>_Disney_Transformed.pptx` unless the user specifies another name. Use presentation tooling available in the environment. If a script exists in `scripts/`, inspect and validate it before use; do not assume it is available or functional. If editable PowerPoint generation is unavailable, disclose the limitation rather than claiming to have created a deck.

### 6. Quality control
Inspect the generated deck slide by slide, preferably by rendering slides for visual review. Verify:
- **Content fidelity:** No unintended omissions, fabricated content, altered figures, or meaning changes.
- **Template alignment:** Correct use of available layouts, fonts, colors, dimensions, and visual conventions.
- **Readability:** Clear hierarchy, legible text, and appropriate density.
- **Layout integrity:** No overflow, clipping, overlaps, off-slide elements, or misaligned objects.
- **Data integrity:** Charts, tables, labels, units, and citations remain accurate.
- **Consistency:** Similar content uses consistent formatting across slides.
- **Editability:** Text and other elements remain editable where feasible.

Correct issues within tool capabilities. Clearly identify remaining problems and slides requiring manual adjustment.

### 7. Deliver for human review
Provide:
1. The transformed `.pptx` file.
2. A concise summary of what changed.
3. A list of slides requiring manual review, with specific reasons.
4. Any unresolved ambiguities, missing assets, or limitations.

State that the result is **Disney-aligned for human review**, not officially approved by Disney. Do not claim exact template replication or final brand compliance without explicit human confirmation.

## Guardrails
- The approved PowerPoint template is the primary visual authority.
- Do not substitute generic Disney-themed styling for the supplied Disney Advertising template.
- Preserve content meaning and organizational intent.
- Do not silently remove content to make a slide fit.
- Do not fabricate sources or data.
- Do not modify the original input or template files.
- Flag cases that require human design judgment or manual intervention.
- Keep confidential client materials within the authorized working environment; do not upload them to external services without authorization.

## Success criteria
A successful run converts a minimally formatted source presentation into a coherent, editable PowerPoint that closely follows the supplied approved template, retains the source's meaning and content hierarchy, and includes a clear handoff for human quality control and final adjustments.
