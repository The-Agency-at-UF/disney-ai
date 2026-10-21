---
name: disney-presentation-transformation
description: Transform basic or minimally formatted PowerPoint presentations into Disney Advertising-aligned presentations using the approved DA_Generic_Template_2025-3.pptx template. Use when a user supplies a source deck and asks to apply the Disney Advertising presentation design system.
---

# Disney Advertising Presentation Transformation

## Purpose
Transform a user-provided PowerPoint presentation containing basic or minimally formatted content into a polished, editable `.pptx` aligned as closely as practical with the approved Disney Advertising presentation template. This is an AI-assisted prototype workflow, not a guarantee of pixel-perfect reproduction. Every output will require human review before distribution.

## Required resources
- **Approved design source:** the validated original `DA_Generic_Template_2025-3.pptx`, or the bundled `assets/Disney_Template_Slim.pptx` fallback (relative to this SKILL.md). See "Template source".
- **Source presentation:** A `.pptx` provided by the user for transformation.
- **Slide map:** `references/template-map.md` lists which template slides to clone for each slide type, the approved palette, and which sections are off limits. Read it before selecting layouts, and re-verify the slide numbers against the template in use.

Do not assume that optional directories contain specific files. Do not infer brand colors, fonts, or layout specifications from the project brief or statement of work; derive them from the actual approved template and any supplied brand guidance.

## Template source
The full original template (`originals/DA_Generic_Template_2025-3.pptx`, about 560 MB) lives in the public `disney-ai` repo (at "https://github.com/The-Agency-at-UF/disney-ai") under Git LFS. A slim copy is bundled at `assets/Disney_Template_Slim.pptx` (chart workbooks removed, some slide-level hero images still grey).

1. Try the original: clone or pull the repo, then run `git lfs pull` for that file. Use only a read-only credential supplied at runtime; never write tokens into the repo or the skill.
2. Validate it before use: the file must be larger than 1 KB, must not start with `version https://git-lfs`, must open in python-pptx, and must have 144 slides.
3. If validation fails or the fetch is blocked, stop using the original. Use `assets/Disney_Template_Slim.pptx` and tell the user that backgrounds are reduced quality and the output needs extra visual review.
4. Never silently build from a pointer file or an unvalidated download.
5. The slim template's Lens_* flare pictures and the divider wedge pictures are grey stubs. When working from the slim copy, flag every slide where a flare or wedge had to be left out so a human can restore it from the original. Do not leave grey boxes in the output.

## Workflow

### 1. Validate inputs
1. Locate and open the validated template from "Template source".
2. Locate and open the user-provided source deck.
3. Verify that both are readable and that a presentation editing/export capability is available.
4. If the approved template or source deck is missing, request the missing file rather than inventing its contents or visual standards.
5. If the source contains unclear, contradictory, or incomplete content that materially affects interpretation, request clarification or mark it for human review.

### 2. Analyze the approved template
Inspect slide dimensions, masters/layouts, theme colors, fonts, title and body hierarchies, spacing, alignment, image treatments, chart/table styles, headers/footers, section dividers, callouts, and recurring compositions. Build an internal layout inventory that maps each supported slide type to an existing approved layout or representative template slide, starting from `references/template-map.md`. Prefer the actual template over generic presentation-design conventions.

**Brand scope (applies to every output).** The client is Disney Advertising, so the deck is built from the Disney Advertising section of the template (blue). Do not use the ESPN (red) or Hulu (green) sections, their `ESPN Cover *` layouts, or their colors, even when the source deck is about an ESPN, Hulu, or other network property. Use them only if the user explicitly asks for that network's look. Do not clone the template's style-guide slides (3-17) into the output.

### 3. Interpret source content
For each source slide, identify:
- Slide title, main message, supporting points, and hierarchy.
- Content type (e.g., title, section divider, text, comparison, timeline, chart, table, image, or summary).
- Data, citations, labels, footnotes, and relevant speaker notes.
- Content or relationships that must remain intact.

Preserve factual claims, figures, units, names, dates, quotations, source attributions, and intended meaning. DO NOT invent facts, statistics, imagery, or brand rules. Do not silently omit source content. Minor copy edits for clarity are permitted only when they do not change meaning; flag substantive changes for approval.

### 4. Select layouts and transform
1. Match each source slide to the most appropriate approved layout based on content and communicative purpose.
2. **Clone, don't imitate.** Build each output slide by duplicating the matching template slide (with its layout, placeholders, background, glow images, and footer) and filling it. Do not assemble a look from blank slides, plain text boxes, or the layout alone, and do not change layouts, fonts, or colors once a template slide is cloned. The result should be recognizable as the template at a glance. When content does not fit a template slide, choose a different template slide or split the content; do not freelance a new design.
3. Apply the template's typography, colors, spacing, alignment, visual hierarchy, and graphical conventions. Keep the "PROPERTY OF DISNEY ADVERTISING SALES, LLC. UNAUTHORIZED DISTRIBUTION PROHIBITED." footer on every slide that has it in the template.

Slide-type rules (details and slide numbers in `references/template-map.md`):

- **Color:** Disney Advertising blues from the template palette (Light Blue `#0BB5DC`, Steel Blue `#004069`, Dark Blue `#021D30`, white). No red or green as deck colors. The only red/green/aqua allowed is the small glow flares that ship with the template's image frames. Leave colors inherited from the layout; set explicit colors only for charts, and only from the palette.
- **Title slide:** use the hero slide (slide 1, dark Disney "D" art with logo and light-blue title/date) or the montage cover (slide 19, five-image row with curved wedge) when at least five usable images are available. Put the deck title and date in the template's title/date positions. No other title treatment.
- **Section dividers / transitions:** use the divider slides (21, 22, or 23): full-bleed image, curved wedge, large light-blue title bottom-left, white subtitle beneath it. Use a source image for the background when one fits; otherwise use an approved background (template slides 131-142) rather than leaving a grey placeholder, and never reuse the template's sample key art. Insert a divider before each major section of the source deck.
- **Images (hard rule, no exceptions):** every image from the source deck must sit in a template picture frame that has the template's rounded corners, glowing border, and Lens_* flare. A bare rectangular picture, a picture with a plain square edge, or a picture on an opaque padded canvas that hides the frame is a defect.
  - **Choose only frames that have the treatment.** Before using any template slide for images, verify its picture frame actually has the rounded, glowing look: open the cloned frame's shape XML (and its layout placeholder) and confirm the rounded geometry and the glow/shadow effect are present, then render the slide and look at it. Layouts differ: for example, the 48/49, 37-40, 55-60 and 69 frames carry the glow, while some tall-frame layouts (53/54) have a plain rectangular frame with no glow. Do not use a frame that lacks the treatment, even if its size fits the image well. Pick a different slide.
  - **Keep the flares.** The Lens_* pictures stay with their frame at the same relative position. If they are grey stubs (slim template), do not silently drop them: flag the slide for human restoration.
  - **Fit by cropping, not padding.** Center-crop to the frame's aspect, keeping faces and key content. Do not letterbox with a padded or recolored canvas to avoid cropping. If cropping would cut important content (charts, text in screenshots), choose a template slide whose frame matches the image's aspect ratio, or flag the slide for human review. Never shrink an image into a small island inside its frame.
  - **Several images:** use the multi-frame slides (48/49, 37-40, 69) when there are two or more images, one image per frame. Do not merge several source images into one composite to fit a single frame; pick a slide with enough frames or split across slides. Delete any frame that has no image, along with its flare picture, or pick a slide with fewer frames. Never leave grey placeholder boxes.
- **Data and charts:** present statistics, percentages, and chart data like template slides 61/62: a rounded glass card with a heading, short body text, a large light-blue `XX%` figure, and a native editable chart (donut or bar) styled from the palette. Use the big-number slides (46/47, 53-60, 63) for stat-led slides, and 126/127 for bar charts. Charts are rebuilt as native charts with the source's exact categories and values; never a screenshot. If the source chart is only an image with no underlying data, place it in a glowing frame and flag it for manual rebuild. Group related figures on one data card instead of spreading them as loose bullets.
- **Text-heavy slides:** use the text-only bullet slides, not a blank slide with a body box, and keep the source's bullet hierarchy. Move key figures from bullets onto a data slide only when the figure and its context stay intact. For every slide with text, ensure that the correct font size is used so that text is legible and readable, as well as ensuring the text box is sized properly to avoid clashing with the background (making it illegible).
4. Fit content without clipping, overlap, or unreadably small text. When necessary, split content across additional slides or recommend a manual redesign rather than deleting information.
5. Preserve charts and tables as editable elements when practical, including their data and labels. Do not change values or chart interpretation.
6. Use only approved or user-supplied images and assets when available. Do not add unapproved Disney artwork, logos, or other branded material.
7. Keep slide dimensions consistent with the approved template unless the user explicitly requests otherwise.

### 5. Generate the output
Create a new editable `.pptx` file; never overwrite the approved template or original source deck. Name the output `<source-name>_T.pptx` unless the user specifies another name. Use presentation tooling available in the environment. If a script exists in `scripts/`, inspect and validate it before use; do not assume it is available or functional. If editable PowerPoint generation is unavailable, disclose the limitation rather than claiming to have created a deck.

### 6. Quality control
Inspect the generated deck slide by slide, preferably by rendering slides for visual review. Verify:
- **Content fidelity:** No unintended omissions, fabricated content, altered figures, or meaning changes.
- **Template alignment:** Correct use of available layouts, fonts, colors, dimensions, and visual conventions. Specifically check that: every slide was cloned from the Disney Advertising section; no ESPN/Hulu layouts or red/green deck colors appear unless asked for; the title slide is the hero or montage cover; dividers use the wedge divider slides; data uses the card-with-chart treatment; and slide 1 of the output does not carry template guide text such as "Template v25.01".
- **Image frames (required check, per image):** go through every image in the output and confirm it has the rounded corners and glowing border, sits in a template picture placeholder, is cropped rather than padded or squeezed, and keeps its Lens_* flare. Any image with a plain square edge or no glow fails QC: switch to a template slide with a glowing frame and rebuild the slide. Do not deliver a deck with a failing image and simply note it, unless the original template assets needed to fix it are unavailable, in which case flag the slide explicitly.
- **Readability:** Clear hierarchy, legible text (make sure the text isnt too small or too large), and appropriate density.
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
- Do not adopt a source property's own branding (e.g., ESPN red) in place of Disney Advertising blue.
- A passable approximation is not enough: follow the template's slides strictly, and when a slide would need to deviate from the template, flag it for review instead.
- Preserve content meaning and organizational intent.
- Do not silently remove content to make a slide fit.
- Do not fabricate sources or data.
- Do not modify the original input or template files.
- Flag cases that require human design judgment or manual intervention.
- Keep confidential client materials within the authorized working environment; do not upload them to external services without authorization.

## Success criteria
A successful run converts a minimally formatted source presentation into a coherent, editable PowerPoint that closely follows the supplied approved template, retains the source's meaning and content hierarchy, shows every image in a rounded, glowing template frame, and includes a clear handoff for human quality control and final adjustments.