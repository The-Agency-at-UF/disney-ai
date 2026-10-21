# Template slide map (DA_Generic_Template_2025-3.pptx)

Slide numbers are 1 based and identical in the original and in `assets/Disney_Template_Slim.pptx` (144 slides, 26.67 x 15 in). Re-verify with python-pptx before relying on them (layout names below are the check); if the numbering has drifted, re-derive the map from the layout names and update this file.

## Sections of the template

| Slides | Section | Use? |
|---|---|---|
| 1-2 and 18-20 | Hero / title art (`HERO` layout) | Use one of these as a template for the title slide |
| 3-17 | Style guide: logos, palette, fonts, icons, tips | Reference only. Never copy into output |
| 21-24 | Transition slides, use them as the default source for a transition/divider slide |
| 18-78 | **Disney Advertising slide layouts (blue)** | **These are the default source for every output slide**. These slides range from normal title slides to slides with data and image placeholders, use a diverse set of these slides to represent the information in your input deck.  |
| 79-100 | ESPN (red) section, `ESPN Cover *` layouts | **Don't use**, unless the user explicitly asks for an ESPN-branded deck |
| 101-124 | Hulu (green) section | **Don't use**, unless the user explicitly asks for Hulu |
| 125-127 | Graph examples (dark / light) | Use as chart styling reference |
| 128-129 | Device mockups | Optional |
| 130-142 | Approved backgrounds BG #01-#12 | Use as fallback backgrounds when no image is supplied |
| 143-144 | Blank layouts | Use rarely |

The client works for **Disney Advertising**, so the output is Disney Advertising blue even when the subject is an ESPN, Hulu, or other network property. A subject being ESPN does not make the deck an ESPN deck unless specifically asked for, same with Hulu. Network colors appear only as accents that come with the template's glow images (green/red/aqua lens flares).

## Palette (from style-guide slide 10; DO NOT invent others)

- Light Blue `#0BB5DC`, Steel Blue `#004069`, Dark Blue `#021D30`, White `#FFFFFF`
- Bright Aurora `#02D6E8`, Aurora `#136878`, Twilight `#02172A`
- Greyscale: Tungsten `#424242`, Steel `#797979`, Aluminum `#A9A9A9`, Mercury `#EBEBEB`
- Do not use ESPN Red `#F51825`, Deep ESPN Red `#91080A`, Hulu Green, or Slate Black as deck colors unless using the ESPN or Hulu templates when specifically asked for.

Fonts and sizes come from the layouts. Do not override them. Titles are 60 pt+ on covers, subtitles 30 pt.

## Slide type -> template slide to clone

| Need | Clone slide(s) | Look |
|---|---|---|
| **Title slide, hero** | 1 (or 2 for logo only) | Dark Disney "D" art, white Disney Advertising logo left, light-blue title and date text under it. Replace the "Template v25.01" text with the deck title |
| **Title slide, montage** | 19 (20 if no images) | Row of five portrait images, curved blue wedge, centered logo, "Title Text", "DATE GOES HERE" |
| **Section divider / transition** | 21 (dark wedge), 22 (same, image placeholder), 23 (white wedge) | Full-bleed image, curved teal-to-navy wedge from the left, large light-blue title bottom-left, white subtitle under it |
| Three framed images + bullets | 48, 49 | Title, subtitle, bullets on left; three glowing rounded image frames on right (green top-left, red bottom-left, aqua tall right) |
| Five or more framed image cards under a centered title | 37, 38 (8 frames), 39, 40 (7 frames) | UPPERTEXT + two-line light-blue title; cards with glowing blue borders |
| Four framed photo cards with captions | 69 | Centered title/subtitle, four glowing photo cards over a curved blue horizon, header and caption under each |
| Data card: heading, body, big stat, chart | 61, 62 | Rounded glass card; heading and paragraph; big light-blue `XX%`; native donut chart on the right |
| Big-number stat slides | 46, 47, 53-60, 63 | `XXM` / `XX%` figures with captions |
| Stat list beside photo | 66, 67 | Photo left, four rounded stat rows right |
| Chart-only | 126 (dark), 127 (light) | Donut, stacked bar, bar charts on the template background |
| Text-only bullets | 33-36, 41-45 | Title, subtitle, bullets, no imagery |
| Quote | 70, 71 | Large quote with name and role |
| Agenda | 25, 27 | Numbered 01, 02, 03 list |
| Case study | 72 | Header, metrics tiles, objective/solution panels |
| People/bio grids | 73-78 | Name + caption cards |

If a layout is unsure, open the slide and read its shapes. A slide's look is defined by its layout, its picture placeholders (rounded, glowing frame), and the Lens_*.png glow pictures sitting beside them, so clone the whole slide rather than recreating it.

## Glowing image frames

Every image in the output sits inside a template picture placeholder, which supplies the rounded corners and glowing border. The colored flares (`Lens_Green.png`, `Lens_Red.png`, `Lens_Aqua.png`) are separate pictures on the template slide positioned at the frame edges. They must be kept, and kept at the same position relative to their frame. An image dropped onto a slide as a plain rectangular picture is a defect.

When filling a picture placeholder, crop the source image to the placeholder's aspect ratio (center crop, keep faces and subjects) instead of stretching it.
