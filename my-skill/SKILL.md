---
name: disney-presentation-transformation
description: Transform basic or minimally formatted PowerPoint presentations into Disney Advertising-aligned presentations using the bundled approved Disney Advertising template (`assets/Disney_Template_Slim.pptx`). Use when a user supplies a source deck and asks to apply the Disney Advertising presentation design system.
---

# Disney Advertising Presentation Transformation

## Purpose
Transform a user-provided PowerPoint presentation containing basic or minimally formatted content into a polished, editable `.pptx` aligned as closely as practical with the approved Disney Advertising presentation template. This is an AI-assisted prototype workflow, not a guarantee of pixel-perfect reproduction. Every output will require human review before distribution.

## Required resources
- **Approved design source:** the bundled `assets/Disney_Template_Slim.pptx` (relative to this SKILL.md). See "Template source".
- **Source presentation:** A `.pptx` (preferred) or PDF provided by the user for transformation, meeting the "Minimum input standard".
- **Slide map:** `references/template-map.md` lists which template slides to clone for each slide type, the approved palette, and which sections are off limits. Read it before selecting layouts, and re-verify the slide numbers against the template in use.

Do not assume that optional directories contain specific files. Do not infer brand colors, fonts, or layout specifications from the project brief or statement of work; derive them from the actual approved template and any supplied brand guidance.

## Minimum input standard
This skill only works properly when the source deck meets the standard below. Before doing any other work, restate it to the user and ask them to confirm that their input meets it.

1. **File type:** `.pptx` or PDF only. `.pptx` is strongly preferred, because it carries native text, charts, tables and images; a PDF loses structure and may need more manual rebuilding and review.
2. **Editable text:** text must be real, editable text, not images of text (screenshots, scanned pages, flattened exports). Text that exists only inside an image cannot be reliably extracted, restyled or checked for fidelity.
3. **Attached and open:** the file must be attached to the conversation as a file (not pasted as text, linked, or described) and must not be password protected or encrypted.

Keep this check to a few lines, because busy users skip long warnings. Check what you can yourself (file type, opens without a password, text extracts as editable) and do not narrate those findings. Ask only about what you cannot verify, using a message like this (3 to 5 lines at most):

> Quick check before I start: your deck must be a .pptx (or PDF) with real editable text, not screenshots of text, and not password protected. I can't see inside images, so any text baked into a picture will be flagged, not transcribed. Output is Disney-aligned for human review, not Disney-approved, and needs a visual check. Good to go?

Do not add slide-by-slide summaries, descriptions of how charts or missing art will be handled, or other explanation here; that belongs in the final handoff.

- If the user confirms, continue to "Workflow".
- If any point is not met or is uncertain, do not proceed. Tell the user which point fails and what to fix (for example, re-export from the original PowerPoint, remove the password, or attach the file).
- If, after confirmation, the file turns out not to meet the standard (for example, a page is a flattened image of text, or the file cannot be opened), stop and tell the user rather than guessing at the content. Image-only text must not be transcribed from the picture without telling the user, and any such content must be flagged for human review.

## Template source
Always build from the bundled `assets/Disney_Template_Slim.pptx` (chart workbooks removed, some slide-level hero images still grey). Do not try to fetch any other copy of the template. Tell the user that backgrounds may be of reduced quality and the output needs visual review.

The slim copy contains grey stubs. They must be neutralized, never deleted and never left visible. Follow "Stub handling" below.

### Stub handling
In the slim template the Lens_* flares, the divider wedges (`New Wedge.png`, `New Wedge White.png`) and some sample photos are grey stubs: single-colour 1600x900 images (`placeholder_gray.png`). Detect them by comparing the SHA-1 of each picture's image blob to that file's, not by name alone. A stub must never be visible, and it must never be silently deleted, because a deleted wedge or flare cannot be put back in the right place. For every stub on a slide you keep:
1. Replace its image with a fully transparent PNG of the same pixel size. Leave the picture shape itself (name, position, size, crop, z-order) untouched.
2. If you move or resize the frame it belongs to, move the flare with it using the offsets in `references/template-map.md`.
3. Set its alt text to `RESTORE FROM ORIGINAL TEMPLATE (slide N): <shape name>`, where N is the template slide it was cloned from.
4. Add it to the restore table in the handoff (see "Deliver for human review").

Delete a flare only when its frame is deleted. A sample-photo stub (for example the four card photos on slide 69) is replaced by the source image and never left behind. Restoring the art is then one step: select the invisible picture (Selection Pane, same name) and use Change Picture with the same-named picture from template slide N of the original template (`originals/DA_Generic_Template_2025-3.pptx` in the repo); its size and position are already correct.

## Workflow

### 1. Validate inputs
0. Confirm with the user that the source deck meets the "Minimum input standard".
1. Locate and open the bundled template from "Template source".
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

**Keep each source slide whole.** Text, images, charts, screenshots and tables that appear together on one source slide must appear together on one output slide. The output has one slide per source slide, plus dividers if you add them (a source slide that is only a title and a picture is already a divider: use a divider template for it). Never separate a visual from the text it was presented with, never split a source slide because the template slide has too few frames, and never move content to another slide to make it fit. The only permitted split is a text-only slide whose text cannot fit at the minimum legible size even on the roomiest text layout, and it must be flagged. If no template slide fits a source slide, extend the closest one (see "Several images") or flag the slide for human design.

Preserve factual claims, figures, units, names, dates, quotations, source attributions, and intended meaning. DO NOT invent facts, statistics, imagery, or brand rules. Do not silently omit source content. Minor copy edits for clarity are permitted only when they do not change meaning; flag substantive changes for approval.

### 4. Select layouts and transform
1. Match each source slide to the most appropriate approved layout based on content and communicative purpose.
2. **Clone, don't imitate.** Build each output slide by duplicating the matching template slide (with its layout, placeholders, background, glow images, and footer) and filling it. Do not assemble a look from blank slides, plain text boxes, or the layout alone, and do not change layouts, fonts, or colors once a template slide is cloned. The result should be recognizable as the template at a glance. When content does not fit a template slide, choose a different template slide or extend the closest one as described under "Several images"; never split a source slide's content across slides, and do not freelance a new design.
3. Apply the template's typography, colors, spacing, alignment, visual hierarchy, and graphical conventions. Keep the "PROPERTY OF DISNEY ADVERTISING SALES, LLC. UNAUTHORIZED DISTRIBUTION PROHIBITED." footer on every slide that has it in the template.

Slide-type rules (details and slide numbers in `references/template-map.md`):

- **Color:** Disney Advertising blues from the template palette (Light Blue `#0BB5DC`, Steel Blue `#004069`, Dark Blue `#021D30`, white). No red or green as deck colors. The only red/green/aqua allowed is the small glow flares that ship with the template's image frames. Leave colors inherited from the layout; set explicit colors only for charts, using the series order under "Chart colors" in `references/template-map.md`.
- **One tone per deck:** most template layouts come as a dark (blue) and a light (white) twin; the pairs are listed in `references/template-map.md` under "Deck tone".
  - Clone only the dark versions. The title slide, dividers and data cards are dark too, so the whole deck reads as one color. Never alternate between twins.
  - Use a light slide only if the user asks for a light deck (then use light twins throughout), or when the only fitting layout has no dark version (for example 72, case study). List any such slide under "Needs your attention".
- **Title slide:** use the hero slide (slide 1, dark Disney "D" art with logo and light-blue title/date) or the montage cover (slide 19, five-image row with curved wedge) when at least five usable images are available. Put the deck title and date in the template's title/date positions. No other title treatment.
- **Section dividers / transitions:** use the divider slides (21, 22, or 23): full-bleed image, curved wedge, large light-blue title bottom-left, white subtitle beneath it. Use a source image for the background when one fits; otherwise use an approved background (template slides 131-142) rather than leaving a grey placeholder, and never reuse the template's sample key art. When inserting images into these dividers, ensure that the image subject isn't being blocked by the wave, while covering the entire gray placeholder area with the image (strict requirement). If blockage is unavoidable, notify the user in the recap. Insert a divider before each major section of the source deck. The wedge is a stub (see "Stub handling"), and the wedge is what normally gives the title its contrast, so check the title against the photo: use 22 (light-blue title) when the bottom-left of the photo is dark and 23 (dark title) when it is light, and flag any divider where the title still crosses busy artwork.
- **Images:** by default, every photo from the source deck sits in a template picture frame that has the template's rounded corners, glowing border, and Lens_* flare. A photo shown as a bare rectangle, with a plain square edge, or on an opaque padded canvas that hides the frame is a defect. Two kinds of image are the exception, because a frame makes them look broken (a glowing box floating around a cut-out person, or a border cutting through a chart's labels):
  - **Images with a clear (transparent) background never get a frame.** Cut-outs of people or products, logos, icons, and charts or graphics exported with no background. Detect them by checking the image's alpha channel: if the corners or edges are mostly transparent, it is a clear-background image. Place it directly on the slide where the frame would have been, at its own aspect ratio (no crop, no stretch), with no glow, no border line and no flare. Delete that frame and its flare. Make sure the image's dark or light parts stay readable against the dark background; flag it if they do not.
  - **Be cautious with charts, graphs, tables, diagrams and other data images.** The data matters more than the frame. Frame a data image only when it is an opaque rectangle that fills the frame without cropping any label, legend, axis or value, and the glow does not overlap any of its text. Otherwise place it unframed, as above. Never crop a data image to fit a frame. When in doubt, leave the frame off.
  - Every image that is placed without a frame is listed in the slide map's notes, so the reviewer knows it was deliberate.
  - **Standard corner radius (every opaque source image).** Every image that comes from the source deck, framed or not, gets the same rounded corners, except clear-background images (whose transparent edges already define their shape). Never apply it to the template's own artwork: Lens_* flares, wedges, the hero "D" art, the Disney logo artwork, background images and neutralized stubs keep their geometry, or they get clipped. The template's rounding is fragile: it is a custom outline (`custGeom`) stored on each sample picture on the slide, while the layout placeholder underneath is a plain rectangle. Replacing the picture (for example python-pptx `insert_picture()`), building a new one, or copying a frame from the layout all produce square corners, and the template's outline also distorts on very tall or wide frames. So, as the last step for each image, after cropping and sizing:
    1. Remove any `a:custGeom` or `a:prstGeom` from the picture's `p:spPr`.
    2. Insert `<a:prstGeom prst="roundRect"><a:avLst><a:gd name="adj" fmla="val ADJ"/></a:avLst></a:prstGeom>` directly after `a:xfrm` (before `a:ln` and `a:effectLst`).
    3. Compute `ADJ = min(50000, round(R / min(width, height) × 100000))`, where R is the standard radius in `references/template-map.md` ("Standard corner radius") and width/height are the picture's size in EMU. This keeps the corner the same physical size on every image, whatever its shape.
    The border line and glow follow the picture's outline, so they round too. Recompute ADJ whenever a picture is resized.
  - **Choose only frames that have the treatment.** Before using any template slide for images, verify its picture frame has the glowing look: open the cloned frame's shape XML (and its layout placeholder) and confirm the glow/shadow effect and border line are present, then render the slide and look at it. Rounded corners are applied by the standard-radius step above, not taken from the template. Layouts differ: for example, the 48/49, 37-39, 46, 55-60, 63 and 69 frames carry the glow (40 showed no glow effect in the template's XML, so verify it before use), while some tall-frame layouts (53/54) have a plain rectangular frame with no glow. Do not use a frame that lacks the treatment, even if its size fits the image well. Pick a different slide.
  - **Keep the flares.** The Lens_* pictures stay with their frame at the same relative position. If they are grey stubs, neutralize them as described in "Stub handling" and list them in the restore table. Delete a flare only together with its frame.
  - **Scale the glow with the frame.** A frame's glow (the `outerShdw` blur in its `effectLst`) and its Lens_* flare are fixed sizes, not proportional to the frame, so a frame that is resized, duplicated or regridded keeps a glow and flare that are too large or too small for it (usually too large). Whenever a frame's size differs from the template frame it came from, compute `k = new frame's shorter side / template frame's shorter side` (reference sizes in `references/template-map.md`) and:
    1. Set the glow's `blurRad` (and `dist`, if non-zero) to the template value × k, written on the output shape itself, not left to the layout placeholder.
    2. Scale the flare's width and height by k (keep its aspect ratio) and its offset from the frame by k.
    3. Leave the glow color and the frame's corner rounding as they are.
    Render the slide and check that every frame's glow looks the same thickness relative to its frame as on the template slide; a glow that visibly dominates its image fails QC.
  - **Fit by cropping, not padding.** Center-crop to the frame's aspect, keeping faces and key content. Do not letterbox with a padded or recolored canvas to avoid cropping. If cropping would cut important content (charts, text in screenshots), choose a template slide whose frame matches the image's aspect ratio, or flag the slide for human review. Never shrink an image into a small island inside its frame.
  - **Several images (keep the text with them):** use a slide that has both a text area and picture frames; 48/49 are the default (text left, frames right). One image per frame; never merge several source images into one composite. Count the source images first. If the slide has more frames than images, delete the unused frames and their flares. If it has fewer, duplicate one of that slide's own frames (copy the slide's picture shape, not the layout's; when the frame is a placeholder, copy the layout placeholder's `ln` and `effectLst` onto the copy and drop the `ph` tag; then apply the standard corner radius), give the copy its own flare, and arrange the frames as a grid beside the text (for example 2x2 for four images; recipe in `references/template-map.md`). Do not switch to a frame-only slide (37-40, 69, 75-78) and drop the text, and do not put the images and the text on separate slides. Use the caption slots of 69 or 75-78 only when the source itself pairs each caption with one image. If more than six frames would be needed beside the text, flag the slide for human design judgment instead of splitting it. Never leave grey placeholder boxes.
- **Data and charts:** present statistics, percentages, and chart data like template slides 61/62: a rounded glass card with a heading, short body text, a large light-blue `XX%` figure, and a native editable chart (donut or bar) styled from the palette. Use the big-number slides (46/47, 53-60, 63) for stat-led slides, and 126/127 for bar charts. Charts are rebuilt as native charts with the source's exact categories and values; never a screenshot. If the source chart is only an image with no underlying data, place it following the data-image caution under "Images" (unframed unless a frame fits it cleanly) and flag it for manual rebuild. Group related figures on one data card instead of spreading them as loose bullets.
  - **Charts from text (only when unambiguous).** When a source slide's text states data that a chart would show more clearly, build a native chart from it in Disney Advertising colors (series order in `references/template-map.md`, "Chart colors"). Do this only when every one of these holds:
    1. Every value is stated explicitly as a number in the text. Never estimate, interpolate, round further, or derive a value the text does not state (no "the rest", no "about half").
    2. Every value has a clear label (a category, period or segment), and every label has exactly one value.
    3. All values share one unit and one measure (all percentages of the same base, all dollar amounts, all counts) and come from the same source and time frame as the text presents them.
    4. There are at least three values (two values are better as big-number figures on a stat slide).
    5. The chart type follows from the data without guessing:
       - Parts of one whole that the text says add up to 100%: donut.
       - The same measure compared across categories: bar.
       - The same measure at three or more points in time: column or line.
    If any condition fails, or you would have to choose between two readings of the text, do not chart it. Keep the text, or use a big-number stat layout for standout figures.
  - When you do chart text: keep the original sentences on the slide next to the chart (the chart adds to the text, never replaces it), put the chart on the same output slide, label the values exactly as written in the source (number and unit), and list the slide under "Needs your attention" as "chart built from text, verify values".
- **Text-heavy slides:** pick the layout from the *shape* of the source slide's text, not from what was used last: read the slide, find the matching row in the "Text layout menu" in `references/template-map.md` (statement, agenda/steps, lead-in + bullets, three or four parallel points, four categories, quote, or plain bullets), and clone that slide. Never use a blank slide with a body box.
  - **Variety means structure, not color.** A different layout that suits the content counts as variety; the light twin of the same layout never does.
  - **Fit first, then vary.** Never squeeze content into a layout it does not fit just to be different (for example, do not merge six bullets into four columns).
  - **Restructuring keeps every word and the hierarchy.** Moving a list into 64 or 68 is allowed when each top-level bullet becomes one section and its sub-bullets become that section's body. Nothing is dropped or rewritten beyond minor clarity edits.
  - **Avoid runs.** Do not use the same layout for more than two text slides in a row when the next slide also fits another row in the menu.
  - **Plain bullet slides (33/41) are the fallback.** Text with a clear structure (a statement, steps, 3-4 parallel points, categories) should go on the layout made for that structure. Move key figures from bullets onto a data slide only when the figure and its context stay intact. For every slide with text, ensure that the correct font size is used so that text is legible and readable, as well as ensuring the text box is sized properly to avoid clashing with the background (making it illegible).
4. Fit content without clipping, overlap, or unreadably small text. When necessary, choose a roomier template slide or recommend a manual redesign rather than deleting information. Do not split a slide whose text and visuals belong together (see "Keep each source slide whole").
5. Preserve charts and tables as editable elements when practical, including their data and labels. Do not change values or chart interpretation.
6. Use only approved or user-supplied images and assets when available. Do not add unapproved Disney artwork, logos, or other branded material.
7. Keep slide dimensions consistent with the approved template unless the user explicitly requests otherwise.

### 5. Generate the output
Create a new editable `.pptx` file; never overwrite the approved template or original source deck. Name the output `<source-name>_T.pptx` unless the user specifies another name. Use presentation tooling available in the environment. If a script exists in `scripts/`, inspect and validate it before use; do not assume it is available or functional. If editable PowerPoint generation is unavailable, disclose the limitation rather than claiming to have created a deck.

### 6. Quality control
Inspect the generated deck slide by slide, preferably by rendering slides for visual review. Verify:
- **Content fidelity:** No unintended omissions, fabricated content, altered figures, or meaning changes. Run a word-level comparison of all source text against all output text; every source word must appear, and any extra words (labels, repeated titles) must be intentional.
- **Slide integrity (required):** build a table mapping every source slide to its output slide(s) and to the template slide it was cloned from. Each source slide maps to exactly one output slide (dividers excepted). If a source slide's text and visuals ended up on different output slides, that is a defect: rebuild the slide before delivery.
- **Stub check (required):** no grey stub is visible anywhere (compare each picture's SHA-1 to `placeholder_gray.png`), every neutralized stub carries the restore alt text, and each one is in the restore table.
- **Template alignment:** Correct use of available layouts, fonts, colors, dimensions, and visual conventions. Specifically check that: every slide was cloned from the Disney Advertising section; no ESPN/Hulu layouts or red/green deck colors appear unless asked for; the title slide is the hero or montage cover; dividers use the wedge divider slides; data uses the card-with-chart treatment; every slide is in the same tone (no light twin mixed into a dark deck unless flagged); no layout is used for more than two text slides in a row when another menu layout fits; and slide 1 of the output does not carry template guide text such as "Template v25.01".
- **Image frames (required check, per image):** go through every image in the output.
  - Corners (every opaque source image, not template artwork such as flares): read each picture's XML and confirm it has `prstGeom prst="roundRect"` with the ADJ value that gives the standard radius for its current size. Any `custGeom` or plain `rect` on an opaque image fails QC.
  - Framed photos: confirm each has the glowing border, sits in a template picture placeholder, is cropped rather than padded or squeezed, and keeps its Lens_* flare, with the glow and flare scaled to the frame's size. A photo with a plain square edge or no glow fails QC: switch to a template slide with a glowing frame and rebuild the slide.
  - Clear-background images and data images: confirm no frame, glow or flare surrounds a clear-background image, that no frame crops or overlaps any chart label, legend, axis or value, and that every unframed image is noted in the slide map. A glowing box around a cut-out or a border cutting through a chart fails QC. Do not deliver a deck with a failing image and simply note it, unless the template assets needed to fix it are unavailable, in which case flag the slide explicitly.
- **Readability:** Clear hierarchy, legible text (make sure the text isnt too small or too large), and appropriate density.
- **Layout integrity:** No overflow, clipping, overlaps, off-slide elements, or misaligned objects.
- **Data integrity:** Charts, tables, labels, units, and citations remain accurate. For every chart built from text, check each value and label against the source sentence it came from, and confirm the sentence is still on the slide.
- **Consistency:** Similar content uses consistent formatting across slides.
- **Editability:** Text and other elements remain editable where feasible.

Correct issues within tool capabilities. Clearly identify remaining problems and slides requiring manual adjustment.

### 7. Deliver for human review
Keep the handoff as short as possible while still complete. Busy readers skim it, so lead with what they must act on, use terse bullets and tables instead of prose, and cut anything that does not change what the reviewer does next. No recap of the workflow or praise of the result. Provide, in this order:
1. The transformed `.pptx` file.
2. **Status line:** one sentence, stating that the result is **Disney-aligned for human review**, not officially approved by Disney, and needs a visual check (backgrounds may be reduced quality). Do not claim exact template replication or final brand compliance without explicit human confirmation.
3. **Needs your attention:** one bullet per slide requiring manual review or rebuild, as `Slide N: reason` (a few words each). Include unresolved ambiguities, text found inside images, and chart images flagged for manual rebuild. Write "None" if there are none.
4. **Restore table** (only if stubs were neutralized): output slide, source template slide, invisible picture names (Selection Pane). State the one-step fix once above the table, not per row: Change Picture with the same-named picture from that template slide in the original template.
5. **Slide map:** a compact table of source slide, output slide, template slide cloned. One line of changes summary at most, and only if something was not obvious from the map (for example merged, split or reordered slides).

Aim for a handoff a reader can finish in under a minute, excluding the tables.

## Guardrails
- The approved PowerPoint template is the primary visual authority.
- Do not substitute generic Disney-themed styling for the supplied Disney Advertising template.
- Do not adopt a source property's own branding (e.g., ESPN red) in place of Disney Advertising blue.
- A passable approximation is not enough: follow the template's slides strictly, and when a slide would need to deviate from the template, flag it for review instead.
- Preserve content meaning and organizational intent.
- Do not silently remove content to make a slide fit.
- Never separate content that shares a source slide: text stays with its images, charts and tables.
- Never leave a grey stub visible and never delete one silently; neutralize it and list it for restoration.
- Do not fabricate sources or data.
- Do not modify the original input or template files.
- Flag cases that require human design judgment or manual intervention.
- Keep confidential client materials within the authorized working environment; do not upload them to external services without authorization.

## Success criteria
A successful run converts a minimally formatted source presentation into a coherent, editable PowerPoint that closely follows the supplied approved template, retains the source's meaning and content hierarchy, shows every photo in a rounded, glowing template frame (and clear-background or data images cleanly without one), keeps text and visuals that shared a source slide together on one slide, makes any missing template art invisible and restorable in one step, and includes a clear handoff for human quality control and final adjustments.