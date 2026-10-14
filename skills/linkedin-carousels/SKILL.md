---
name: linkedin-carousels
description: 'Plans a LinkedIn carousel people finish reading: the story arc, slide-by-slide copy, a layout brief per slide using your brand colours and fonts, and the post caption, ready to build in Figma, Canva or Google Slides. Five content types: How I, How to, case study, framework, listicle. Triggers: "carousel", "LinkedIn carousel", "slide post for LinkedIn", "document post", "turn this into a carousel", "carousel about".'
version: '1.0.0'
license: MIT
---

# LinkedIn carousels

Turn one idea into a 10 to 15 slide carousel with copy, a layout brief and a caption. A carousel is a document post: readers swipe through it, and every slide has to give them a reason to swipe again.

## When to use it

- The idea has steps, parts or a before and after that reads better as slides than as text.
- You have proof (screenshots, numbers, a result) worth showing, not just telling.

Not for single-image posts or text posts (`/linkedin-expert-posts`, `/linkedin-personal-posts`).

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| Topic and angle | Required | The user |
| Content type | Required | How I, How to, case study, framework or listicle |
| Who it is for | Required | `context/icp/` |
| Brand colours and fonts | Recommended | `context/brand/` |
| Voice | Recommended | the tone-of-voice file in `context/brand/` |
| Proof (metrics, screenshots, quotes) | Recommended | The user or `context/win-loss/` |
| A hook | Optional | `/linkedin-hooks` |

If there is no brand file, ask for two colours and a font, or keep the brief neutral and say so. Do not invent a palette. Note any missing context in the output.

Agency users: swap `context/` for `clients/<client>/context/`.

## The arc

| # | Section | Slides | Job |
|---|---|---|---|
| 1 | Cover | 1 | Hook headline (5 to 10 words), a subline, the author's name |
| 2 | Setup | 1 to 3 | Why this matters and what the reader will get |
| 3 | The teaching | 4 to 6 | One idea per slide. Short lists, not paragraphs |
| 4 | Proof | 1 to 2 | Real metrics, screenshots, before and after |
| 5 | Recap or bonus | 1 | A numbered recap, or one extra tip |
| 6 | Call to action | 1 to 2 | The offer ask, then a follow ask on the last slide |

Target 10 to 15 slides. A listicle can run to 18 if every item earns its slide.

## Slide rules

- **One audience, one problem, one solution** per carousel.
- **Keep them moving.** Arrows, "3 of 6" markers and a transition line at the bottom of each slide ("Here is how it works →"). Navigation is why people finish.
- **Mark sections with colour.** For example, light for cover and setup, dark for the teaching, accent for proof and the call to action.
- **Mobile first.** 1080 x 1350 portrait. Text big enough to read on a phone. Four to five bullets or two to three short sentences per slide, at most.
- **Three text sizes at most:** title, body, label.
- **Plain language.** Short sentences a teenager could follow.

## Steps

1. **Check the idea.** One audience, one problem, one solution. If the topic is three topics, split it. Produces: the one-line promise of the carousel.
2. **Pick the type and plan the arc.** Map content to the six sections. Produces: a slide outline with one line per slide.
3. **Write the cover.** Take the hook from `/linkedin-hooks` or write one that names the result. Produces: cover headline and subline.
4. **Write every slide.** Headline, body, and the navigation cue. Produces: slide-by-slide copy.
5. **Write the layout brief.** Per slide: background, headline style, body style, accent, image or screenshot to use. Use the exact colour codes and fonts from `context/brand/`. Produces: a spec table a designer can follow.
6. **Write the caption.** Two to four lines that repeat the hook and say what is inside. If there is a link, it goes in the caption text. Produces: the post caption.
7. **Review.** Read the slides alone, in order, as a buyer would. Cut any slide that does not move the reader forward. Produces: the final blueprint.

## What good looks like

- The cover works as a hook on its own.
- Each slide makes one point and points to the next.
- The proof slide shows real evidence or is clearly marked as needing it.
- Brand colours and fonts are quoted exactly, not described ("brand orange").
- The whole carousel is readable on a phone.

## Mistakes to avoid

- Walls of text on a slide.
- Invented metrics, testimonials or screenshots. Use `[need real screenshot of X]`.
- A call to action that says "link in the comments".
- More than one primary colour fighting for attention on a slide.
- A teaching section that tries to cover everything.

## Output

Save to `outputs/social/linkedin/MMYY-carousel-<topic>.md`:

1. The promise and the content type.
2. Slide-by-slide copy (headline, body, navigation cue).
3. Layout brief table (one row per slide).
4. Caption.
5. Placeholders the user must fill with real proof.
