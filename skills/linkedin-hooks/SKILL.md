---
name: linkedin-hooks
description: 'Writes LinkedIn post hooks (the first one or two lines) aimed at a specific buyer and offer. Two modes: build a hook library across hook types for an ICP, or write 10 hooks for one post you are about to publish and refine the pick. Uses real buyer language from call notes when available. Triggers: "LinkedIn hooks", "hook library", "generate hooks", "hook ideas", "hooks for this post", "opening line for", "first line for my post". Feeds the post skills in this plugin.'
version: '1.0.0'
license: MIT
---

# LinkedIn hooks

Write the first lines of LinkedIn posts. On LinkedIn the hook is the post: readers decide in the two lines before "see more" whether to keep going. A hook that names the reader's problem in their own words beats a clever one.

## When to use it

- **Library mode:** you want a stock of hooks for an ICP to draw on for weeks.
- **Single-post mode:** you know what the post says and need the opening.

Not for writing the full post. Hand the chosen hook to `/linkedin-expert-posts`, `/linkedin-personal-posts` or `/linkedin-carousels`.

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| Who the buyer is, their pains and goals | Required | `context/icp/` |
| The offer | Required | `context/positioning/` or the user |
| Who is posting | Required | The user |
| Voice | Recommended | the tone-of-voice file in `context/brand/` |
| Proof points | Recommended | `context/expert-pov/`, `context/win-loss/` or the user |
| Call notes or transcripts | Optional | Real buyer phrasing beats anything you write |
| Audit findings | Optional | `/linkedin-content-audit` shows which hook types work for this audience |

If the ICP is missing, ask for a one-line description of the buyer and their top 3 to 5 pains before writing. Name what was missing in the output.

Agency users: swap `context/` for `clients/<client>/context/`.

## Hook types

Use these as starting shapes, not fill-in templates.

| Type | What it does |
|---|---|
| Pain mirror | Says the problem the way the buyer says it to themselves |
| Bold claim | States a position the reader may disagree with |
| Contrarian | Challenges something the audience takes for granted |
| Number or result | Leads with a specific, real figure |
| Mistake | Names a common error and its cost |
| Story opening | Drops the reader into a moment ("Last Tuesday a founder told me...") |
| Question | Asks the question the reader is already asking, where the answer is not obvious |
| List promise | Promises a short, specific set ("3 things I check before...") |
| Before and after | Shows the gap between where the reader is and where they want to be |
| Behind the scenes | Shows how something was actually done |

## Steps: library mode

1. **Gather context.** Read the ICP, offer, voice and any call notes. Produces: 3 to 5 buyer pains in the buyer's words, plus available proof.
2. **Score the hook types.** Rate each type high, medium or low for this buyer and offer. Produces: a short scoring table.
3. **Write hooks.** Two or three per high-scoring type, one per medium type, none for low. Produces: 20 to 40 hooks grouped by type.
4. **Rank.** Pick the top 5 and say in one line why each works. Produces: the top-5 list.

## Steps: single-post mode

1. **Name the one thing.** What does the reader get from this post, in one line? Produces: the post's point.
2. **Fix the proof and the reader.** One real proof point and the specific reader (role, stage, situation). Produces: the two anchors every hook carries.
3. **Write 10 hooks** across at least five different types, each two lines at most, with a character count. Produces: 10 numbered hooks.
4. **The user picks one.** Then write 3 variations of it: shorter, more energy, a different detail. Produces: the final hook.

## Writing rules

- Use specific numbers when you have real ones. Never invent them.
- Keep the first sentence short: 5 to 12 words.
- Aim for one emotion: curiosity, worry, desire or surprise.
- Use the buyer's vocabulary from `context/icp/` or call notes, not industry jargon.
- If a hook is a question, the answer must not be obvious.
- No "link in the comments" or "link below" promises.

## What good looks like

- Each hook could only have been written for this buyer.
- A reader in the ICP would recognise their own problem in the first line.
- Proof in the hook is real and traceable.
- The set covers several hook types, not ten versions of one.

## Mistakes to avoid

- Generic openers that fit any post in any industry.
- "Most people think X, but actually Y" without anything specific in it.
- "It's not about X. It's about Y." false contrasts.
- Three short parallel sentences in a row.
- Engagement-bait ("Agree?", "Thoughts?") or emoji decoration.
- Invented stories. Mark `[needs real story]` if none was given.

## Output

Library mode: save to `outputs/social/linkedin/MMYY-hook-library.md` with the scoring table, hooks by type, and the top 5 with reasons.

Single-post mode: return the 10 hooks, the pick and its 3 variations in the chat, ready to paste into the post skill.
