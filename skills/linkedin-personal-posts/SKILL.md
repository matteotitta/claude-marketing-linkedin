---
name: linkedin-personal-posts
description: 'Writes personal LinkedIn posts in the author''s own voice: full story posts built from real experiences, plus short formats (behind the work, a quick thought, a life-outside-work post). Each story maps to one buyer pain so it builds trust with the right audience. Never invents stories or numbers. Triggers: "personal post", "story post", "founder story", "credibility post", "personal LinkedIn series", "behind the scenes post". Not for educational or framework posts (use linkedin-expert-posts).'
version: '1.0.0'
license: MIT
---

# LinkedIn personal posts

Write personal posts from the author's real experiences. Personal stories earn the longest reads and the most trust on LinkedIn because they are hard to fake. That is also why every detail must be true.

## When to use it

- A series of 3 to 5 story posts that build credibility with the buyer.
- A single story post for the week's plan.
- Short posts: something mid-build, a quick thought after a call, a post about life outside work.

Not for frameworks, how-tos or opinion pieces (`/linkedin-expert-posts`) or for comments (`/linkedin-comment`).

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| Real story seeds | Required | The user: turning points, failures, a client moment, a lesson |
| Buyer pains and goals | Required | `context/icp/` |
| Voice | Required | the tone-of-voice file in `context/brand/` |
| The offer | Recommended | `context/positioning/` |
| Proof (real numbers, outcomes) | Recommended | The user or `context/win-loss/` |
| A hook | Optional | From `/linkedin-hooks` |

If there are no story seeds, ask for them with questions like: "When did you last change your mind about how to do this work?", "What did a client say that stuck with you?", "What did you get wrong early on?" Do not make stories up.

If the voice file is missing, ask for 3 posts or messages the author wrote, and match those. Say what was missing in the output.

Agency users: swap `context/` for `clients/<client>/context/`.

## The story structure

1. **The shared pain.** Open with a struggle the reader also has, in their words, with a real detail.
2. **A break.** One to three short lines that shift the energy or set up a turn.
3. **What happened.** What it cost to leave the problem alone, what was hard, and what the author did. This is where credibility comes from.
4. **The better place.** What changed, described as the outcome the reader wants.
5. **The ending.** Why the author does this work, or what it means for the reader. Close on a thought, not a neat moral.

## Short formats

| Format | What it is | Rules |
|---|---|---|
| Behind the work | A screenshot or photo of work in progress with 1 to 2 lines of context | No big hook needed. Remove client names unless they agreed |
| Quick thought | 2 to 6 lines after a call or something seen this week | Stays on the author's topics. No politics, drama or hot takes on news |
| Life outside work | A photo and 1 to 5 lines that add an observation | Pick themes that make the right buyer more likely to want to work with the author |

Short formats get no call to action.

## Steps

1. **Collect seeds.** Read the story seeds, ICP and voice. Produces: a list of stories, each with the real details the user gave.
2. **Map each story to one buyer pain.** Produces: a table of story, pain, and the outcome the reader wants.
3. **Write the hook.** Use a hook from `/linkedin-hooks` or write one that opens on the shared pain. Produces: the first two lines.
4. **Draft the post** in the structure above, in the author's voice. Open on "I" where it reads naturally. Produces: the draft.
5. **Scan for AI tells** (table below) and rewrite any hits. Produces: the clean draft.
6. **Trim 15 to 20 percent.** Produces: the final post, with a note on any `[detail needed]` placeholders.

## AI tells to remove

| Pattern | Fix |
|---|---|
| "It's not X. It's Y." | State the point directly |
| A neat moral at the end | End mid-thought or on an open question to yourself |
| "Here's the thing:" | Cut it |
| Same-length paragraphs | Mix one-line beats with longer passages |
| "Looking back, I realise..." | Stay in the moment |
| "I failed... then I crushed it" | Stay in the failure longer |
| "Just start. Take the leap." | Say exactly what you did |

## What good looks like

- Every detail happened and came from the user.
- A buyer in the ICP sees their own situation in the first lines.
- It sounds like the author talking, not like a newsletter.
- One story per post, one point per story.

## Mistakes to avoid

- Inventing or blending stories into a composite.
- Adding emotional details (family, health, money) the author did not share.
- Inventing numbers to make a story land. Use `[your number here]`.
- Ending every post with a lesson in bold.
- "Link in the comments". Put a link in the post if it is needed at all.

## Output

Save to `outputs/social/linkedin/MMYY-personal-posts.md`: each post ready to paste, with the pain it maps to, the hook type, a suggested image if any, and a list of placeholders the user must fill before posting.
