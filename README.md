# PosTimageInfoGrapcis

Post image and infographic coloring spec + training essentials.

Read `SPEC.md` first. It is written so any AI reading it can create a new post image for any idea, in the same coloring style.

## Contents

- `SPEC.md` — The full spec. Four coloring modes, loot coloring, palettes, prompt templates, pre-generation checklist, and post-generation audit.
  - Mode A — Single-Dominant Emotional Coloring (image-63, red, 9/10)
  - Mode B — Warm + Cool Comedy Triad (image-64, yellow / green / red, 8.5/10)
  - Mode C — Loot Coloring for tiered infographics (grey / green / blue / purple / gold / red)
  - Mode D — Editorial Satire (image-65, muted textured, 9.5/10 for its purpose)
- `training-essentials/image-63-red-quote-card/` — Bengali quote card, angry woman in red.
- `training-essentials/image-64-client-design-idea/` — "After Hearing the Client's Design Idea", designer vomiting green.
- `training-essentials/image-65-editorial-satire/` — "GOOD NEWS. WE CAN NOW DO THE WRONG THING A THOUSAND TIMES FASTER." by Andreas Horn, AI jet engine on a broken cart.

## How to use

1. Name the mode first: A, B, C, or D.
2. Fill in the prompt template for that mode in `SPEC.md` Section 10.
3. Run the pre-generation checklist (Section 11) before generating.
4. Run the post-generation audit (Section 12) after generating. One FAIL means NOT READY.

Do not overwrite the training essentials. New generations go in a new folder.
