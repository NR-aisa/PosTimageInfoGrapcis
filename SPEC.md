# Post Image / Infographic Coloring Spec

Version: 1.2
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
7. All hex codes in this spec are APPROXIMATE, sampled by eye from the three training images. Use them as a starting palette, not as an exact brand colour. The relationships between colours (which colour is dominant, which is accent, which is background) matter more than the exact hex.
8. Colour is never one flat hex. Read Section 2.6 first. Every hero colour must be graded in 3 tones: light, base, dark. A flat-colour image fails the audit, even if the layout and text are correct. This rule was added in v1.2 after image-77 (v6, colouring 6/10) came out flat.

## 1. What this repo is

This repo is a training and reference set for social post images and infographics, mainly cartoon / illustrated posters with a short headline and one clear visual joke or emotion.

It is NOT a realistic photo spec. For realistic photos, use a different spec (unretouched skin, grain, imperfect light, no background faces, separated hands). This spec is for illustrated posts where flat colour, thick black outlines, and a limited palette are the style.

The three training essentials in this repo are the ground truth for this style:

- `training-essentials/image-63-red-quote-card/image-63.png` — Bengali quote card, angry woman, red-dominant.
- `training-essentials/image-64-client-design-idea/image-64.png` — English cartoon, designer vomiting green, yellow / red / green triad.
- `training-essentials/image-65-editorial-satire/image-65.png` — Editorial satire by Andreas Horn, AI jet engine on a broken cart, muted palette, three reactions.

Every rule below is derived from inspecting those three images in depth on 2026-11-08.

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

In this repo, "coloring concept" also means the whole colour discipline of an image: which colour is dominant, which colours support it, how colours repeat, and how colour matches emotion. Sections 3, 4, and 6A define the proven coloring concepts from the training images. Loot coloring (Section 2.1) is a third concept, for tiered content.

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

### 2.6 Graded colouring — the core lesson (added v1.2)

This is the lesson from the detailed audit of image-77 (v6, 2026-11-08). The
layout, text, and mode were mostly right, but the colouring was flat, so the
image scored only 6/10 for colouring. Do not repeat that mistake.

1. **Never use one flat hex per colour.** Every hero colour must appear in
   at least 3 tones: a light tone (highlight), a base tone, and a dark tone
   (fold / shadow). Example: yellow #FFB800 base, #F9B400 light, #E89A00 dark
   in the folds (image-64). Green #7ED321 base, #A8E63F highlight, #5AAE00
   shadow (image-64). Red #E30613 base, brighter for the headline, darker
   for the dress folds (image-63).
2. **Grade the repetition, not just repeat the hex.** When a colour repeats
   in 3 places (Section 2.5), use a different tone in each place: headline
   brighter, dress darker, small detail in the base tone. Repeating the
   exact same hex everywhere is flat and reads as AI-generated.
3. **Break a large colour block with a neutral.** A red dress is never one
   flat red block. Break it with a cream dupatta / scarf with red flowers
   (image-63), or with darker fold shading. A yellow hoodie is never one
   flat yellow block. Break it with darker fold shading and a dark neutral
   (black pants, white shoes).
4. **Skin is graded, not flat peach.** Warm peach base #F7C39A / #F6C193,
   with shading under the chin and cheek, pink on the cheek, and a shadow
   on the nose. Flat peach skin with no shading is a Section 8 AI tell.
5. **Hair is graded, not a solid cap.** Near-black base, with a little
   purple / blue sheen for depth, individual strands in a lighter tone,
   and a darker tone in the bun / shadow. Solid black hair with no sheen
   is flat.
6. **Gold is graded, not flat yellow.** Gold trophy / badge / earring:
   light gold highlight, base gold #F2B705 / #F39C12, dark gold shadow.
   A flat gold shape with a black star on it reads as a sticker.
7. **The lavender blob is graded, not flat.** Pale lavender base #E6DFF7,
   with a slightly darker lavender-grey at the bottom and a soft shadow
   under the feet in the same family. A flat pale blob with a straight
   flat bottom edge looks like a stage.
8. **Line weight varies.** Thick black outlines around the whole figure,
   thin lines for inner details only (Section 7.3). Do not use one uniform
   thick weight for everything, and do not use hatching everywhere. In
   image-63 the line weight varies: thick around the figure, thin inside
   the hair, dress, and face.
9. **Banner is textured, not a clean rectangle.** Mode B banner: red brush
   stroke, rough edge, red bursts at the sides, centre flat for text
   (image-64). A clean inset rounded rectangle with a black outline looks
   corporate and flat. Keep the brush texture only on the edge, keep the
   centre flat for text.
10. **Anger mark is small and on the hair.** Small, about 1–2% of the
    image, on the black hair, with a white outline so it does not disappear
    (image-63 flaw, Section 3.4). Never put it on the forehead on skin
    (it looks like a bindi), never make it huge and floating far from the
    hair (it looks like a separate icon), never duplicate it.
11. **Figures fill the frame.** In image-63 the wife fills the frame,
    cropped at the waist, face very large. In image-64 the man fills the
    frame, bent over, large. White is about 60% in Mode A and 45–50% in
    Mode B, but the figure is large inside that white. Small figures in
    the centre with empty white on both sides (white 65–70%) look empty
    and flat, even if the 60-30-10 numbers are close.
12. **Faces are adult, not a boy.** An adult man has messy hair, light
    stubble, a defined nose and cheek, and a normal face size (image-64).
    A round face, small nose, faint moustache, and eyes closed laughing
    reads as a boy. An angry woman is 3/4 view, wide eyes with white
    showing, open mouth shouting (image-63), not profile with gritted
    teeth and squinting eyes.
13. **Light has one direction, with a soft shadow.** One main light, with
    a soft shadow on one side of the figures and a soft shadow under the
    feet. Do not use perfectly even studio light. Do not use a sharp dark
    grey triangle or a hard geometric shape as a dark corner — that looks
    like a missing piece. Do not remove the dark corner and leave nothing;
    even light is also a fail. Use a soft dark corner / gradient only.

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
| A serious critique or satire — a broken process, a bad idea made faster, a warning about the wrong thing done well | Mode D — Editorial Satire (Section 6A) | One visual metaphor + muted palette + three reactions, not bright colours |
| A realistic photo, a person at work, a slide hero | NOT this spec | Use the realistic-image spec instead. Do not mix cartoon flat colour with realistic skin / light. |
| User did not say | Ask, or pick Mode A | Mode A is the safest default. Never blend A + B + C + D in one image. |

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

## 6A. Mode D — Editorial Satire (image-65, colouring 9.5/10)

Mode D is a new style, different from Modes A, B, and C. It is for a serious
critique or satire, not for a funny joke (Mode B) and not for one emotion
(Mode A). The reference is "GOOD NEWS. WE CAN NOW DO THE WRONG THING A
THOUSAND TIMES FASTER." by Andreas Horn — credit the artist when reusing or
publishing this reference.

### 6A.1 Reference

`training-essentials/image-65-editorial-satire/image-65.png` — landscape,
ink and watercolour, not flat cartoon. A huge, shiny, modern jet engine
labelled "AI" is strapped with rusty straps onto a broken wooden cart
labelled "BROKEN PROCESS". The cart has square wooden wheels, splintered
wood, and loose bolts on the dirt ground. The jet fires with blue flame and
white smoke to the right, but the cart cannot move properly. Three people on
the left: the boss in the middle (blue suit, red tie, laughing, presenting
the engine), the colleague on the far left (grey suit, worried, hand on chin),
the worker at the front (dirty work clothes and a cap, crouching, trying to
fix the broken wheel, red toolbox and wrench on the dirt).

### 6A.2 Palette (approximate)

Muted and textured, not bright and flat: silver grey engine, brown wood cart,
beige dirt ground, pale blue sky, grey suits. Almost no bright colour at all.
Blue suit #2F5D8A (boss — the only person in strong blue), red tie and red
toolbox #C0392B (tiny accents only, linking boss and worker), blue jet flame
#3A7BD5 (the only other blue, repeats the boss's suit), black ink outlines,
white smoke, white speech bubble. Everything else grey, brown, beige.

### 6A.3 Why it works

- **One visual metaphor, not a literal illustration.** Do not draw "AI is
  fast". Draw a jet engine on a broken cart. One strong metaphor is better
  than ten details. The picture proves the words: if the process is broken,
  AI does not fix it, it just makes the same wrong thing faster.
- **Material contrast tells the story.** Shiny new silver engine vs rough old
  brown wood, clean blue suit vs dirty work clothes, fast flame vs square
  wheels that cannot roll.
- **Restraint in colour.** Colour is used only to direct the eye, not to
  decorate. Blue marks the seller (boss's suit, repeated in the jet flame);
  red appears in only two tiny places and links the boss and the worker — the
  boss is selling, the worker is paying for it.
- **Three reactions in one frame.** Excited (boss), worried (colleague),
  exhausted (worker). No extra text is needed to explain who wins and who loses.
- **Detail dense on the hero object, background simple.** Wood grain, rivets,
  bolts, hatching on the suits, dirt, stones, smoke — dense on the engine and
  cart. Background is just pale sky, a few clouds, and dirt ground. Black bars
  top and bottom frame it like a film still and focus the eye in the middle.
- **Eye path:** speech bubble first, then the AI engine (biggest, shiniest
  object), then "BROKEN PROCESS" on the cart below it, then the worker at the
  bottom, the real victim of the joke. The bubble points down to the boss, so
  you know who is speaking. The engine points right, with flame and smoke, so
  you feel speed. The cart is low and heavy, so you feel it cannot move.
- **Text is only 3 pieces:** the speech bubble (the joke), "AI" on the engine,
  "BROKEN PROCESS" on the cart. All black, bold, easy to read. The labels are
  part of the objects, not pasted on top. No extra caption, no logo, no small print.
- **The flaw is visible.** Square wheels, loose bolts, broken wood, a worker
  fixing it. The flaw is the joke — do not hide it or make it pretty.

### 6A.4 What NOT to do in Mode D

- Do not brighten the palette "to make it pop". Brightening it breaks the mood.
- Do not add more people, objects, or text. Three reactions and three text
  pieces are the whole story.
- Do not clean up the mess. Dirt, stones, loose bolts, and broken wood make
  the scene feel real. A tidy version loses the joke.
- Do not use Mode D for a funny joke post. That is Mode B's job. Mode D is
  for satire and critique.
- Do not draw the metaphor literally ("AI is fast" as a fast robot). The
  metaphor must be one object doing the wrong job on top of a broken object.

### 6A.5 When to use Mode D

Use Mode D for: satire about AI, automation, or a new tool making a bad
process worse; a warning that speed is not the same as correctness; an
editorial cartoon for a post about broken processes. Pick ONE metaphor, ONE
muted palette, TWO tiny accents maximum, THREE reactions, THREE text pieces
maximum.

### 6A.6 Exceptions — Mode D breaks the universal rules on purpose

Mode D is an explicit exception to three rules that hold for Modes A, B, and C:
- Section 7.1 (white background): Mode D uses a pale sky + dirt ground scene,
  not plain white, and black film bars top and bottom.
- Section 10.5 negative prompt, "no muted grey-brown colours": muted
  grey, brown, and beige ARE the palette here. When generating Mode D, drop
  that one line from the negative prompt.
- Section 11 background check ("plain white or white + one pale blob"): for
  Mode D the background is the scene itself — pale sky, dirt ground, no clutter.

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
- Thick black outlines, one line weight, around the whole figure. Thin lines for inner details only. Line weight varies: thick around the figure, thin inside hair, dress, and face (Section 2.6).
- Flat colours with a little shading, not realistic shading. One light direction, soft shadow under the feet, not harsh black hatch shading. Every hero colour is graded in 3 tones: light, base, dark (Section 2.6). Never one flat hex per colour.
- Hair: individual strands, messy, not helmet hair. Near-black with a little purple / blue sheen for depth. Skin: warm peach, flat, subtle shading under chin / cheek only, plus pink on the cheek and a shadow on the nose.
- Face: clear expression that matches the emotion and the text. Angry, sick, shocked, happy — one expression only. An angry woman is 3/4 view, wide eyes with white showing, open mouth shouting (image-63), not profile with gritted teeth. An adult man has messy hair, light stubble, a defined nose and cheek (image-64), not a round boy face with a faint moustache.
- Clothing: one hero colour for the main garment, one neutral for pants / shoes. Repeat a small pattern (flowers, stripes) in the hero colour, do not add a new colour for the pattern.
- No background faces. Small background faces become blobs.
- No floating objects without a shadow. Every object on the ground needs a soft shadow under it.

### 7.4 Background and shadow

- Background is either plain white, or plain white + one pale organic blob (lavender, light grey-blue, light peach). The blob must be low saturation and must not touch the text.
- Shadow under the feet is soft, grey or lavender-grey, in the same colour family as the background blob. Never use pure black shadow. Never use a sharp dark grey triangle or hard geometric shape as a dark corner. Light has one direction, with a soft shadow on one side, not perfectly even studio light and not a sharp shape.
- No sun rays, no sparkles, no magic effects, unless the idea is fantasy. Keep it real and clean.

### 7.5 Colour discipline

- Maximum 4 saturated colours per image, plus black, white, skin, and grey. Mode A uses 1 saturated colour. Mode B uses 3. Mode C uses up to 5, but only for tier labels, not for the whole illustration.
- One hero colour, one punchline / accent colour, one background tint. Everything else is neutral.
- Repeat the hero colour in at least 3 places.
- Grade the repetition: use a different tone (light / base / dark) in each place, never the exact same hex everywhere (Section 2.6).
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
- Colours too even, no variation, no muted / non-uniform colour. One flat hex per colour, no grading in light / base / dark tones (Section 2.6).
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

### Mode D — Editorial Satire (muted, textured) — from image-65

Silver grey #B8BEC4, Brown wood #8A6A45, Beige dirt #D9C9A8, Pale sky #DCE8F0, Blue suit #2F5D8A, Red accent #C0392B, Blue flame #3A7BD5, Black ink #1A1A1A, White #FFFFFF

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

### 10.4 Mode D template

```
Mode D — Editorial Satire.
Idea: [one sentence, what is the critique — e.g. a new tool making a broken process faster, not better]
Metaphor: [one object doing the wrong job] on top of [one broken object] — e.g. a shiny AI jet engine strapped onto a broken wooden cart with square wheels.
Layout: landscape, speech bubble at top with exact text "[exact joke]", hero metaphor object in the centre, label "[label 1, e.g. AI]" on the new object, label "[label 2, e.g. BROKEN PROCESS]" on the broken object, black film bars top and bottom.
People: exactly three, each with a different reaction — [excited seller, e.g. boss in blue suit presenting], [worried observer, e.g. colleague in grey suit, hand on chin], [exhausted worker, e.g. crouching, fixing the broken part, red toolbox on the ground].
Palette: muted and textured — silver grey, brown wood, beige dirt, pale blue sky, grey suits. Blue only for [seller's suit + the new object's flame / power], red only in two tiny places [tie + toolbox]. No bright colours anywhere else.
Texture: ink and watercolour, wood grain, rivets, bolts, dirt, stones, smoke, hatching on suits. Dense detail on the hero object, simple background: pale sky, a few clouds, dirt ground.
Text: exactly 3 pieces, all black and bold — the speech bubble, "[label 1]", "[label 2]". Spell them exactly, no extra words, no logo, no caption.
Flaw: keep the flaw visible — [square wheels / loose bolts / broken wood]. Do not hide it or make it pretty.
Style: editorial satire cartoon, serious, like an experienced editorial cartoonist made it, not AI-generated.
Negative prompt for Mode D: same as Section 10.5, BUT drop the "no muted grey-brown colours" line — muted is the palette here.
```

### 10.5 Negative prompt (use for all modes)

```
No garbled text, no misspelled words, no extra text, no watermark, no logo unless the user gave one, no neon colours, no colour fight, no background faces, no merged hands, no extra fingers, no hand-on-hand, no floating objects without shadow, no detailed city background, no glowing bulb in frame, no monitor facing the camera, no robot stare, no perfect even studio light, no sketchy paper background, no muted grey-brown colours.
```

## 11. Pre-generation checklist (must pass before generating)

- [ ] Mode named: A, B, C, or D?
- [ ] Idea in one sentence?
- [ ] Emotion in one word (Mode A/B) or tiers in order (Mode C) or metaphor + three reactions (Mode D)?
- [ ] Dominant / hero colour named with hex, plus its light and dark tones for grading (Section 2.6)?
- [ ] Anger mark named: small, on the hair, white outline, never on the forehead, never huge and floating?
- [ ] Banner named: brush edge for Mode B, centre flat for text, never a clean inset rectangle?
- [ ] Figures named: large, filling the frame, adult faces, not small in the centre and not a boy face?
- [ ] Exact headline text copied exactly from the user, no paraphrase?
- [ ] Layout named: title top, illustration below, eye path described?
- [ ] Background named: plain white or white + one pale blob? (Mode D exception: pale sky + dirt ground scene, black film bars — see Section 6A.6)
- [ ] Person described: age, clothes, pose, expression, hands separated?
- [ ] Accent colour limited to tiny details only?
- [ ] Negative prompt included?
- [ ] If the user rejected the last version, did you name the specific tell and ask whether to retry, simplify, or move on, instead of generating a replacement unprompted?

## 12. Post-generation audit (one FAIL = NOT READY)

Check the generated image against this list. If any item fails, do not present it as finished. Name the fail, fix that one tell, and re-check.

- [ ] Text spelled exactly, no garbled letters, no missing / extra words
- [ ] One dominant colour is clear, no colour fight
- [ ] Every hero colour is graded in 3 tones (light / base / dark), no flat one-hex colour (Section 2.6)
- [ ] Anger mark is small, on the hair, white outline, never on the forehead, never huge and floating
- [ ] Banner is brush-textured on the edge, centre flat for text, never a clean inset rectangle
- [ ] Figures are large and fill the frame, adult faces, white is not 65–70% empty
- [ ] Hero colour repeated in at least 3 places
- [ ] Hierarchy: headline first, illustration second, secondary text last
- [ ] Contrast: headline readable, white on red / black on white, grey secondary text readable on mobile
- [ ] Hands separated, simple pose, no merged / extra fingers
- [ ] Face expression matches emotion / joke, no fake stare, no background-face blobs
- [ ] Background is plain white or one pale blob, no clutter, no detailed city
- [ ] Shadow under feet is soft and in the right colour, no floating objects
- [ ] Light is not perfectly even, one main direction, not studio-perfect
- [ ] No neon, no watermark, no extra logo, no AI tells from Section 8
- [ ] Score: would you give it at least 8/10 against image-63 (9/10), image-64 (8.5/10), and image-65 (9.5/10 for its purpose)? If not, say why, in the user's words, and ask for direction.
- [ ] Mode D only: one metaphor, three reactions, three text pieces maximum, muted palette, flaw visible — if any of these fails, it is not Mode D.

## 13. Training essentials — index

| File | What it teaches | Score | Do not copy |
|---|---|---|---|
| `training-essentials/image-63-red-quote-card/image-63.png` | Mode A, single red, emotion = colour, grey for secondary, gold as tiny accent | 9/10 | The low-contrast grey, the red anger mark lost on black hair |
| `training-essentials/image-64-client-design-idea/image-64.png` | Mode B, yellow hero, green punchline, red banner, lavender cool balance, vertical eye path | 8.5/10 | Yellow exclamation marks blending into the hoodie, red/green placed too close |
| `training-essentials/image-65-editorial-satire/image-65.png` | Mode D, one visual metaphor (AI jet on broken cart), muted textured palette, three reactions, 3 text pieces max | 9.5/10 for its purpose | Do not brighten the muted palette, do not add people or text, do not clean up the mess — the flaw is the joke |

Each training folder has its own README with a full breakdown. Do not overwrite these files. New generations go in a new folder, never in a training folder.

## 14. Version history

- 1.0 — 2026-11-08 — First version. Written from deep inspection of image-63 (Bengali red quote card, 9/10) and image-64 ("After Hearing the Client's Design Idea", 8.5/10), plus the loot coloring system from game UI. Modes A, B, C defined, prompt templates and audit checklists added.
- 1.1 — 2026-11-08 — Mode D added. Written from deep inspection of image-65 ("GOOD NEWS. WE CAN NOW DO THE WRONG THING A THOUSAND TIMES FASTER." by Andreas Horn, colouring 9.5/10 for its purpose). Mode D is Editorial Satire: one visual metaphor, muted textured palette, three reactions, 3 text pieces maximum. Section 6A defines it, Section 5 decision table and Section 9 cheat sheet extended, Section 10.4 template added, Section 10.5 negative prompt renumbered (Mode D drops the "no muted grey-brown colours" line). Training essential saved at `training-essentials/image-65-editorial-satire/` with exact image copy (hash-verified) and README.
- 1.2 — 2026-11-08 — Graded colouring added. Written from the detailed audit of image-77 (v6, colouring 6/10, overall 7.5/10). New Section 2.6: never one flat hex per colour, grade every hero colour in light / base / dark, grade the repetition, break large colour blocks with a neutral, grade skin / hair / gold / lavender, vary line weight, brush banner edge, small anger mark on the hair only, figures fill the frame, adult faces, light with one direction and a soft shadow (no sharp dark triangle, no even studio light). Sections 7.3, 7.4, 7.5, 8, 11, and 12 updated with the same rules. No training image added in v1.2; image-77 is a generation, not a training essential.
