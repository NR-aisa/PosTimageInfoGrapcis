# Post Image / Infographic Coloring Spec

Version: 1.0
Date: 2026-11-08
Repo: https://github.com/NR-aisa/PosTimageInfoGrapcis
Purpose: So any AI (or human) reading this file can create a new post image / infographic in the same coloring style, for any new idea, without guessing.

## 0. How to read this spec (for an AI)

1. Read Section 1 first. Name the coloring mode before you generate anything.
2. If the user did not name a mode, ask, or pick the mode from the decision table in Section 5. Do not blend modes.
3. Fill in the prompt template in Section 10 with the user's exact idea, exact text, and the palette for the chosen mode.
4. Run the pre-generation checklist in Section 11 before generating.
5. Run the post-generation audit in Section 12 after generating. One FAIL means NOT READY. Do not present a failed image as finished.
6. Keep every generation, including rejected ones. Do not overwrite a training essential.
7. All hex codes in this spec are APPROXIMATE, sampled by eye from the two training images. Use them as a starting palette, not as an exact brand colour. The relationships between colours (which colour is dominant, which is accent, which is background) matter more than the exact hex.

## 1. What this repo is

This repo is a training and reference set for social post images and infographics, mainly cartoon / illustrated posters with a short headline and one clear visual joke or emotion.

It is NOT a realistic photo spec. For realistic photos, use a different spec (unretouched skin, grain, imperfect light, no background faces, separated hands). This spec is for illustrated posts where flat colour, thick black outlines, and a limited palette are the style.

The two training essentials in this repo are the ground truth for this style:

- `training-essentials/image-63-red-quote-card/image-63.png` — Bengali quote card, angry woman, red-dominant.
- `training-essentials/image-64-client-design-idea/image-64.png` — English cartoon, designer vomiting green, yellow / red / green triad.

Every rule below is derived from inspecting those two images in depth on 2026-11-08.

## 2. Definitions — read these exactly

### 2.1 Loot coloring (game UI meaning)

Loot coloring is a colour system from games (Diablo, World of Warcraft, and similar) that shows how rare and valuable an item is instantly, without reading text.

Standard tiers:

| Tier | Colour | Hex (approx) | Meaning | Use it for |
|---|---|---|---|---|
| Common | Grey / White | #9AA0A6 / #FFFFFF | Ordinary, low value | Default, background info |
| Uncommon | Green | #2ECC71 | A little better | A small upgrade, a tip |
| Rare | Blue | #3498DB | Valuable | An important point, a pro tip |
| Epic | Purple | #9B59B6 | Very valuable | A key insight, a highlight |
| Legendary | Orange / Gold | #F39C12 / #E67E22 | Best, most exciting | The main takeaway, the hero point |
| Mythic / Special | Red / Pink | #E74C3C / #FF2D78 | Unique, dangerous, urgent | A warning, a mistake, a shock |

Rules for loot coloring:

1. Saturation and brightness rise with value. Common is dull. Legendary is bright and saturated.
2. The same colour always means the same tier in the whole set. Never use purple for Common in one image and for Epic in the next.
3. Never use colour alone. Always add a second signal: an icon, a label, a border, or a shape. This is for colour-blind users and for small screens.
4. Use loot coloring when the post has LEVELS, TIERS, or RANKED items: pricing plans, levels, badges, steps from basic to best, mistakes from small to serious.
5. Do NOT use loot coloring when the post has ONE emotion or ONE joke. For one emotion, use Mode A or Mode B below. Mixing loot tiers into a single-emotion poster creates a colour fight.

### 2.2 Overall coloring concept (the user's phrase)

In this repo, "coloring concept" also means the whole colour discipline of an image: which colour is dominant, which colours support it, how colours repeat, and how colour matches emotion. Sections 3 and 4 define the two proven coloring concepts from the training images. Loot coloring (Section 2.1) is a third concept, for tiered content.

### 2.3 The 60-30-10 rule

Every good image in this repo follows this:

- 60% — Background / dominant neutral. Usually white.
- 30% — Dominant colour. One colour only. This is the hero colour.
- 10% — Accent + outlines + secondary text. Black outlines, one small accent colour, grey secondary text.

If a second colour grows past 30%, it is no longer an accent. It is a second hero, and the image will fight with itself.

### 2.4 Colour fight

A colour fight is when two or more saturated colours compete for attention at the same size and same saturation, with no clear winner. Symptoms: the eye does not know where to look first, the headline and the illustration compete, the image feels loud or messy.

Fix a colour fight by: making one colour bigger, making the other colour paler / smaller / desaturated, or removing one colour entirely.

### 2.5 Repetition

Repeat the dominant colour in at least 3 places: headline, illustration, and one small detail. Repetition is what makes text and illustration feel like one design, not text pasted on a drawing.

Example from image-63: red is in the headline, the logo, the dress, the flowers on the scarf, and the anger mark.
Example from image-64: green is in the vomit stream, the drops, and the puddle on the floor.

## 3. Mode A — Single-Dominant Emotional Coloring (image-63, score 9/10)

Use Mode A when: the post has ONE emotion and ONE message. Anger, sadness, love, pride, warning, apology.

### 3.1 Reference

File: `training-essentials/image-63-red-quote-card/image-63.png`
Text: "অনেক ভুলের হয় না ক্ষমা, বললে স্যরি" — "Many mistakes are not forgiven by saying sorry."
Author: সাবরিন জাওয়াদ ঋতু (Sabrin Jawad Ritu)
Top left: "টাটকা রস" in grey. Top right: red logo.
Illustration: Angry woman, pointing with one finger, other hand on hip, black hair in a bun, red dress, cream scarf with red flowers, gold bangles and earring.

### 3.2 Palette (approximate)

- White background: #FFFFFF — about 60%
- Dominant red: #E30613 / #ED1C24 — about 25–30%
- Black hair and outlines: #1A1A1E — about 8%
- Warm skin peach: #F7C39A — about 5%
- Cream scarf: #FFF3E0 / #FDF0DC — breaks the red dress, not a new hue
- Gold accent: #F2B705 — less than 1%, only earring + 2 bangles
- Grey secondary text: #8A8D93 — about 1–2%, only for author name and top label

### 3.3 Why it works

1. One dominant colour only. Red is the hero.
2. Colour matches emotion. Red = anger, warning, no forgiveness. The quote, the expression, the pointing hand, and the colour all say the same thing.
3. Hierarchy is correct: (1) red headline, biggest and boldest, (2) red illustration, (3) grey author name last. Grey is intentionally low contrast so it does not fight red.
4. No colour fight. No blue, green, or purple competes with red.
5. Cream scarf breaks the red dress so the dress is not one flat red block. Red flowers on the scarf repeat the dress colour.
6. Gold is used in only 3 tiny places. It is warm like skin, it breaks red and black, and it does not become a second hero colour.
7. Skin is warm peach, flat with subtle shading. Hair is near-black with a little purple/blue sheen for depth, but no new hue is added.
8. Lots of white negative space at the top. The image can breathe. The red pops because the background is empty.

### 3.4 Known flaws (do not repeat)

1. The same saturated red is used for headline, logo, and dress, so they compete a little. The headline wins only by size and position. Fix: make the headline red slightly brighter, or the dress red slightly darker.
2. Grey secondary text is a bit washed out, especially the top-left label and the author name. Readable, but low contrast on mobile. Fix: darken grey to #6B6E75 or larger size.
3. The red anger mark on black hair almost disappears. Fix: add a white outline around the anger mark, or make it brighter.
4. The whole image is warm and hot, with no cool colour to balance it. That is intentional for anger, but it can feel heavy. Do not add a cool colour unless the emotion needs it.

### 3.5 When to use Mode A

Use Mode A for: a quote card, a warning, an apology, a love / heartbreak post, a single strong feeling. Pick ONE emotion, pick ONE colour for that emotion, and repeat it.

Emotion-to-colour map for Mode A:

- Anger / warning / no forgiveness: red
- Sadness / calm / trust: blue
- Love / care: pink / soft red
- Growth / fresh start: green
- Happiness / energy: yellow / orange
- Luxury / premium: gold / black

## 4. Mode B — Warm + Cool Comedy Triad (image-64, score 8.5/10)

Use Mode B when: the post is a JOKE, a funny reaction, or a before/after shock. The humour needs more energy than one colour can give.

### 4.1 Reference

File: `training-essentials/image-64-client-design-idea/image-64.png`
Text: Top line "After Hearing the" in black. Second line "Client's Design Idea" in white on a red brush banner.
Illustration: Young man in a yellow hoodie, bent over, hands on knees, vomiting bright green. Messy dark hair, light stubble, black cargo pants, black smartwatch, white sneakers.

### 4.2 Palette (approximate)

- White background: #FFFFFF — about 45–50%
- Yellow hoodie (hero): #FFB800 / #F9B400, darker shade #E89A00 — about 20%
- Black / dark grey pants and hair: #2F2F33 / #3A3A3E — about 15%
- Lime green vomit: #7ED321 / #8AC926, highlight #A8E63F, shadow #5AAE00 — about 8–10%
- Red banner: #D9001B / #E30613 — about 5%
- Pale lavender background blob: #E6DFF7 / #E9E2F5 — low saturation, large area but pale
- Skin peach: #F6C193
- Black outlines: #111111

### 4.3 Why it works

1. Yellow is the hero. Your eye goes to the yellow hoodie first after the title. Yellow is bright and cheerful, and it stands out from white and dark pants.
2. Green is the punchline. Green = sick, disgust. The bright green stream goes straight down from mouth to puddle, creating a vertical eye path. You read the joke in one second: bad idea, designer feels sick.
3. Red is used ONLY for the title banner. Red = alarm, shock. White text on red has very high contrast, so the title is loud, but red does not take over the whole image.
4. Lavender is the cool balance. It is pale and low saturation, so it separates the man from the white background without fighting yellow, green, or red. It cools down all the warm colours. The shadow under the feet is the same lavender-grey, so the feet are grounded, not floating.
5. Thick black outlines unify everything. The same black line weight is used around hoodie, pants, hair, and vomit. That is why it looks like a professional cartoon, not a messy image.
6. White shoes repeat the white background, balance the dark pants, and give the bottom breathing room.
7. Colour tells the story: yellow = happy designer before, green = sick reaction after, red = alarm in the title.
8. Small details repeat colours without adding new ones: black spiral and question mark near the head for confusion, yellow-orange exclamation marks near the back, red small bursts at the sides of the banner.

### 4.4 Known flaws (do not repeat)

1. Six hues (yellow, green, red, lavender, black, white) is riskier than Mode A. Red and green are complementary (opposite on the colour wheel), so together they are very loud. It works here only because they are separated by the yellow hoodie and white space. Do not place saturated red directly next to saturated green.
2. The yellow exclamation marks near his back almost disappear. They are the same yellow-orange as the hoodie. Fix: make them orange-red, or put them on white / lavender, not on the hoodie colour.
3. The red banner has a rough brush texture. Good for energy, but white text on an uneven red edge is a little less clean than flat red. Keep the brush texture only on the banner edge, keep the centre flat for text.
4. Green is very saturated in stream, drops, and puddle. Repetition is good, but if green is any brighter it would overpower the yellow hoodie. Keep green at 8–10% of the image, never more.

### 4.5 When to use Mode B

Use Mode B for: designer jokes, client jokes, reaction memes, "after hearing X" posts, funny infographics. Pick ONE hero colour for the person, ONE punchline colour for the reaction/object, ONE banner colour for the title, and ONE pale cool colour for the background blob. That is the limit. Four colours maximum, plus black, white, and skin.

## 5. Decision table — which mode for which idea

| If the idea is... | Use | Why |
|---|---|---|
| One emotion, one quote, one warning | Mode A | One colour = one feeling, no distraction |
| A joke, a reaction, a shock, a funny story | Mode B | Warm hero + cool balance + punchline colour |
| Ranked levels, tiers, plans, steps, best-to-worst | Mode C — Loot (Section 6) | Each tier needs its own colour |
| A realistic photo, a person at work, a slide hero | NOT this spec | Use the realistic-image spec instead. Do not mix cartoon flat colour with realistic skin / light. |
| User did not say | Ask, or pick Mode A | Mode A is the safest default. Never blend A + B + C in one image. |

Rule: Name the mode first, in the first line of your prompt and in your reply to the user. Example: "Mode B — Warm + Cool Comedy Triad."

## 6. Mode C — Loot Coloring for Infographics (tiered posts)

Use Mode C only for tiered content. This is the loot system from Section 2.1 applied to posts.

### 6.1 How to apply loot colours to a post

1. List the tiers first, in order, from lowest to highest. Example: Free, Basic, Pro, Premium, Legendary.
2. Assign one loot colour per tier, in the standard order. Do not invent a new order.
3. Make higher tiers more saturated and brighter. Lower tiers are duller and greyer.
4. Repeat the tier colour in three places: the tier label, the icon / badge, and the border or background tint for that tier's card.
5. Keep the background white and the text black. Only the tier elements carry the loot colour. If the whole background becomes purple / gold, the post becomes unreadable.
6. Add a label and an icon for each tier, not colour alone. Example: "PRO — blue, star icon" and "LEGENDARY — gold, crown icon."

### 6.2 Example mapping for a pricing / plan infographic

- Free / Common: grey #9AA0A6, circle icon, "Free"
- Starter / Uncommon: green #2ECC71, leaf icon, "Starter"
- Pro / Rare: blue #3498DB, star icon, "Pro"
- Premium / Epic: purple #9B59B6, gem icon, "Premium"
- Best / Legendary: gold #F39C12, crown icon, "Best Value"

### 6.3 What NOT to do in Mode C

- Do not use red for the best tier and gold for a low tier. Red means warning / danger in Mode A, and gold means best in loot. Keep the meaning consistent.
- Do not use more than 5 tiers in one image. If there are more, group them.
- Do not make all tiers equally bright. If everything is bright, nothing is Legendary.

## 7. Universal rules for all modes (do not break these)

### 7.1 Layout

- White background first. Either plain white, or plain white + ONE pale blob behind the subject (Mode B lavender blob). No detailed city, no busy pattern, no gradient sky unless the idea needs it.
- Title at the top, illustration below it. Reading order is top to bottom.
- Keep a clear eye path. In image-64, the eye path is: red banner → yellow hoodie → green stream → green puddle. In image-63, the eye path is: red headline → red illustration → grey author name. Design the eye path before you design the details.
- Lots of white negative space. Do not fill every corner. Empty space makes the hero colour pop.
- Centre the subject, or put the subject on one side and keep the other side empty for text. Never put text over a busy part of the illustration.

### 7.2 Typography and text

- Spell all text EXACTLY as the user wrote it. Bengali and English text must be spelled exactly, with no garbled letters, no missing words, no extra full stops.
- Hierarchy: headline biggest and boldest, second line smaller, author / source smallest and grey.
- Contrast: black text on white, white text on red / dark banner. Grey text only for secondary info, and darken grey to at least #6B6E75 for mobile readability.
- One font system per image. Do not mix 3 fonts.
- No readable text on clothing, monitors, or background objects unless the user asked for it.

### 7.3 Character and illustration

- One main person per image, unless the joke needs two. Start with one, add a second only after one-person images are clean.
- Simple pose, readable in one second. Pointing, bent over, hands on hips, hands on knees — one clear action.
- Hands clearly separated, simple poses. No hand-on-hand, no overlapping / merged hands, no pointing finger that is too detailed to render.
- Face: clear expression that matches the emotion and the text. Angry, sick, shocked, happy — one expression only. No fake wide-eyed shock unless the joke needs it, no robot stare, no direct stare at the camera unless the poster is a portrait.
- Thick black outlines, one line weight, around the whole figure. Thin lines for inner details only.
- Flat colours with a little shading, not realistic shading. One light direction, soft shadow under the feet, not harsh black hatch shading.
- Hair: individual strands, messy, not helmet hair. Skin: warm peach, flat, subtle shading under chin / cheek only.
- Clothing: one hero colour for the main garment, one neutral for pants / shoes. Repeat a small pattern (flowers, stripes) in the hero colour, do not add a new colour for the pattern.
- No background faces. Small background faces become blobs.
- No floating objects without a shadow. Every object on the ground needs a soft shadow under it.

### 7.4 Background and shadow

- Background is either plain white, or plain white + one pale organic blob (lavender, light grey-blue, light peach). The blob must be low saturation and must not touch the text.
- Shadow under the feet is soft, grey or lavender-grey, in the same colour family as the background blob. Never use pure black shadow.
- No sun rays, no sparkles, no magic effects, unless the idea is fantasy. Keep it real and clean.

### 7.5 Colour discipline

- Maximum 4 saturated colours per image, plus black, white, skin, and grey. Mode A uses 1 saturated colour. Mode B uses 3. Mode C uses up to 5, but only for tier labels, not for the whole illustration.
- One hero colour, one punchline / accent colour, one background tint. Everything else is neutral.
- Repeat the hero colour in at least 3 places.
- Do not use neon. Bright is allowed, neon is not. Graded, warm colours are better than flat neon.
- Warm and cool must balance. If the image is all warm (red + yellow + orange), add one pale cool colour (lavender, light blue-grey) as background. If the image is all cool, add one warm accent (gold, skin).

## 8. What makes an image look AI-generated (avoid these)

From the training work in this repo's history, these tells make a cartoon or poster look AI-generated, even when the colours are right:

- Skin too smooth, no pores, no uneven tone, no stray hairs (for realistic images; for cartoons, skin too perfect and plastic).
- Hair too perfect, helmet hair, no individual strands.
- Hands merged, overlapping, extra fingers, thumb in the wrong place.
- Background faces turning into blobs.
- Text garbled, misspelled, extra letters, or a sign that drops a word.
- Monitor facing the camera, or a monitor on the opposite side from the person using it.
- Light too even, no hard shadow, no dark corner, no blown highlight.
- Colours too even, no variation, no muted / non-uniform colour.
- Floating objects with no ground shadow.
- Same face repeated across a set.

If you see one of these, fix that one tell first, before changing anything else.

## 9. Palette cheat sheet (copy this)

### Mode A — Red (anger / warning) — from image-63

White #FFFFFF, Red #E30613, Black #1A1A1E, Skin #F7C39A, Cream #FFF3E0, Gold #F2B705, Grey #6B6E75 (darkened for readability)

### Mode B — Yellow / Green / Red (comedy) — from image-64

White #FFFFFF, Yellow #FFB800, Green #7ED321, Red #D9001B, Lavender #E6DFF7, Dark grey #2F2F33, Skin #F6C193, Black outline #111111

### Mode C — Loot tiers

Grey #9AA0A6, Green #2ECC71, Blue #3498DB, Purple #9B59B6, Gold #F39C12, Red #E74C3C

To make a new Mode A palette, replace Red with the emotion colour from Section 3.5, keep white, black, skin, cream, and gold the same. To make a new Mode B palette, replace Yellow with the new hero colour, replace Green with the new punchline colour, keep red for the banner and lavender for the background, or replace lavender with a pale tint of the hero colour.

## 10. Prompt templates (copy-paste, fill the [brackets])

### 10.1 Mode A template

```
Mode A — Single-Dominant Emotional Coloring.
Idea: [one sentence, what is the message]
Emotion: [one word, e.g. anger]
Dominant colour: [one colour, e.g. red #E30613]
Layout: white background, title at top in [dominant colour], bold, exact text "[exact headline]", author "[exact name]" in grey #6B6E75 below it, illustration below the title, lots of white negative space.
Illustration: one person, [describe person, age, clothes, pose, expression], [dominant colour] clothes, cream scarf / neutral break, gold accent only in [earring / bangles / small detail], black hair, warm peach skin, thick black outlines, flat colours with soft shading, soft grey shadow under feet.
Background: plain white, no details, no city, no pattern.
Text: spell "[exact headline]" exactly, no extra words, no garbled letters.
Style: professional cartoon poster, clean, like an experienced UI/UX designer made it, not AI-generated.
```

### 10.2 Mode B template

```
Mode B — Warm + Cool Comedy Triad.
Idea: [one sentence, what is the joke]
Hero colour: [e.g. yellow #FFB800 for the hoodie]
Punchline colour: [e.g. lime green #7ED321 for the reaction / object]
Banner colour: red #D9001B for the title banner, white text on it.
Background: plain white + one pale lavender blob #E6DFF7 behind the subject, low saturation, soft lavender-grey shadow under feet.
Layout: title at top, "[exact line 1]" in black, "[exact line 2]" in white on red brush banner, illustration below, eye path: banner -> hero colour -> punchline colour -> puddle / object on floor.
Illustration: one person, [describe person, clothes, pose, expression], [hero colour] hoodie / shirt, dark grey pants, white sneakers, thick black outlines, flat colours, simple separated hands, clear expression matching the joke.
Text: spell "[exact line 1]" and "[exact line 2]" exactly.
Style: professional cartoon poster, clean, funny, like an experienced UI/UX designer made it, not AI-generated.
```

### 10.3 Mode C template

```
Mode C — Loot Coloring for Infographics.
Idea: [what is ranked / tiered]
Tiers in order: [Tier 1 Common grey], [Tier 2 Uncommon green], [Tier 3 Rare blue], [Tier 4 Epic purple], [Tier 5 Legendary gold]
Layout: white background, title at top in black, one card per tier in a row / column, each card has its tier colour only in label, icon, and border, text black, background white.
Each tier: label "[tier name]" + icon "[icon name]" + colour "[loot colour]", never colour alone.
Style: clean infographic, professional UI/UX, high contrast, readable on mobile.
```

### 10.4 Negative prompt (use for all modes)

```
No garbled text, no misspelled words, no extra text, no watermark, no logo unless the user gave one, no neon colours, no colour fight, no background faces, no merged hands, no extra fingers, no hand-on-hand, no floating objects without shadow, no detailed city background, no glowing bulb in frame, no monitor facing the camera, no robot stare, no perfect even studio light, no sketchy paper background, no muted grey-brown colours.
```

## 11. Pre-generation checklist (must pass before generating)

- [ ] Mode named: A, B, or C?
- [ ] Idea in one sentence?
- [ ] Emotion in one word (Mode A/B) or tiers in order (Mode C)?
- [ ] Dominant / hero colour named with hex?
- [ ] Exact headline text copied exactly from the user, no paraphrase?
- [ ] Layout named: title top, illustration below, eye path described?
- [ ] Background named: plain white or white + one pale blob?
- [ ] Person described: age, clothes, pose, expression, hands separated?
- [ ] Accent colour limited to tiny details only?
- [ ] Negative prompt included?
- [ ] If the user rejected the last version, did you name the specific tell and ask whether to retry, simplify, or move on, instead of generating a replacement unprompted?

## 12. Post-generation audit (one FAIL = NOT READY)

Check the generated image against this list. If any item fails, do not present it as finished. Name the fail, fix that one tell, and re-check.

- [ ] Text spelled exactly, no garbled letters, no missing / extra words
- [ ] One dominant colour is clear, no colour fight
- [ ] Hero colour repeated in at least 3 places
- [ ] Hierarchy: headline first, illustration second, secondary text last
- [ ] Contrast: headline readable, white on red / black on white, grey secondary text readable on mobile
- [ ] Hands separated, simple pose, no merged / extra fingers
- [ ] Face expression matches emotion / joke, no fake stare, no background-face blobs
- [ ] Background is plain white or one pale blob, no clutter, no detailed city
- [ ] Shadow under feet is soft and in the right colour, no floating objects
- [ ] Light is not perfectly even, one main direction, not studio-perfect
- [ ] No neon, no watermark, no extra logo, no AI tells from Section 8
- [ ] Score: would you give it at least 8/10 against image-63 (9/10) and image-64 (8.5/10)? If not, say why, in the user's words, and ask for direction.

## 13. Training essentials — index

| File | What it teaches | Score | Do not copy |
|---|---|---|---|
| `training-essentials/image-63-red-quote-card/image-63.png` | Mode A, single red, emotion = colour, grey for secondary, gold as tiny accent | 9/10 | The low-contrast grey, the red anger mark lost on black hair |
| `training-essentials/image-64-client-design-idea/image-64.png` | Mode B, yellow hero, green punchline, red banner, lavender cool balance, vertical eye path | 8.5/10 | Yellow exclamation marks blending into the hoodie, red/green placed too close |

Each training folder has its own README with a full breakdown. Do not overwrite these files. New generations go in a new folder, never in a training folder.

## 14. Version history

- 1.0 — 2026-11-08 — First version. Written from deep inspection of image-63 (Bengali red quote card, 9/10) and image-64 ("After Hearing the Client's Design Idea", 8.5/10), plus the loot coloring system from game UI. Modes A, B, C defined, prompt templates and audit checklists added.
