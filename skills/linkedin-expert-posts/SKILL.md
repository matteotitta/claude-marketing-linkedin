---
name: linkedin-expert-posts
description: 'Writes authority LinkedIn posts in the author''s voice: contrarian takes, frameworks, industry analysis, expert breakdowns and predictions. Each post puts proof in the first lines, makes one point, and ends on one belief you want the buyer to hold, so it builds the trust that turns into messages and calls. Triggers: "expert post", "thought leadership post", "hot take", "framework post", "industry take", "contrarian take", "what most people get wrong about". Not for personal stories (use linkedin-personal-posts).'
version: '1.0.0'
license: MIT
---

# LinkedIn expert posts

Write the posts that make a buyer think "this person knows what they are doing": an opinion backed by experience, a framework, a reading of what is changing in the market. These sit between personal stories (which build likeability) and offers (which ask for something).

## When to use it

- The author has a real point of view on a topic the buyer cares about.
- You want posts people save and forward to their team.

Not for personal stories (`/linkedin-personal-posts`), carousels (`/linkedin-carousels`) or comments (`/linkedin-comment`).

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| Topic and the author's position on it | Required | The user or `context/expert-pov/` |
| Who the buyer is | Required | `context/icp/` |
| Voice | Required | the tone-of-voice file in `context/brand/` |
| Proof (results, clients, data, years doing it) | Recommended | `context/expert-pov/`, `context/win-loss/` or the user |
| Positioning | Recommended | `context/positioning/` |
| A hook | Optional | `/linkedin-hooks` |

Check before writing: is there a real position here, not a summary of the obvious? Does the author have standing to say it? If a statistic is used, is the source real? If the expert POV file is missing, ask the user what they believe that most of their peers do not. Note what was missing in the output.

Agency users: swap `context/` for `clients/<client>/context/`.

## Post types

| Type | Use it when | Shape |
|---|---|---|
| Contrarian take | Challenging accepted wisdom | "Everyone says X. Here is what I have seen instead." |
| Framework | Explaining a system you use | "The 3 checks I run before..." |
| Industry analysis | Reading data or a market shift | "This changed. Here is what it means for you." |
| Expert breakdown | Making something hard simple | Step by step, one idea per step |
| Prediction | Forward-looking opinion | "This will stop working. This replaces it." |

## Structure

```
Hook (1-2 lines)       proof + the reader named
Position (1-3 lines)   the author's actual view, stated plainly
Body (2-3 points)      specific problems and what they cost, from experience
Ending (2-3 lines)     lands one belief the reader should now hold
Call to action         only if this is the week's offer post; otherwise end on the belief
```

**Write in this order: hook, then ending, then body.** Decide where the post lands before writing the middle, so the body is a bridge to that belief. It still reads top to bottom.

## Steps

1. **Pick the type** from the table. Produces: the post type and the one point in 10 words or fewer.
2. **Choose the proof line.** The most relevant proof, not the most impressive. Produces: the line that goes in the hook.
3. **Name the belief.** One belief the reader should hold after reading (for example: "a positioning problem looks like a pipeline problem"). Produces: the ending's target.
4. **Write the hook** with the proof and the reader in it. Produces: the first two lines.
5. **Write the ending** that lands the belief. Produces: 2 to 3 closing lines.
6. **Write the body** as the author's own experience ("on the last three projects I..."), naming what goes wrong and what it costs. Insight, not a manual. Produces: the full draft.
7. **Run the checks** below and trim 15 to 20 percent. Produces: the final post.

## Checks

- **Expert test.** Would someone who has never heard of the author conclude they are an expert from this post alone? Proof sits in the first two lines.
- **One thing.** Zoom in on one point. If there are 4 or more numbered steps, each could be its own post.
- **Insight, not manual.** The reader should think "that makes sense", not "now I can do it without help".
- **Broad enough.** It speaks to the whole ICP, not one client's edge case.
- **No false contrasts.** Scan every line for "It's not X, it's Y", "Stop X. Start Y." and two-sentence pairs where the second reverses the first. Rewrite as a plain positive statement.
- **No bait.** No "What's your take?", "Agree?" or "Thoughts?" endings.
- **Links.** If the post needs a link, put it in the post. Never "link in the comments".

## Mistakes to avoid

- Invented statistics or studies. Use `[data point needed]`.
- Using "a client I worked with" when the user gave no such example.
- A framework that is all structure and no view.
- Product mentions in a post meant to build authority.
- Hedging the position until it says nothing.

## Output

Return the post ready to paste, plus: post type, the belief it ends on, the proof used, a visual suggestion (1080 x 1350 portrait if an image helps), and any placeholders to fill. For a batch, save to `outputs/social/linkedin/MMYY-expert-posts.md`.
