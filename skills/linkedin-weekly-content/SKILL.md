---
name: linkedin-weekly-content
description: 'Plans and drafts a week of LinkedIn posts in two stops: first a plan (3 to 5 posts across personal, expert and carousel types, each tied to a buyer pain and your point of view, with hooks), then full drafts in your voice and a simple posting calendar. Reads your ICP and expert POV, uses the other skills in this plugin for hooks and drafts, and never posts anything. Triggers: "plan my LinkedIn week", "weekly LinkedIn", "LinkedIn content plan", "give me topics for this week", "write the week", "LinkedIn calendar".'
version: '1.0.0'
license: MIT
---

# LinkedIn weekly content

Plan next week's LinkedIn posts, then write them. Batch once a week instead of creating every day: the posts get better and the habit survives busy weeks.

The skill stops twice for the user: after the plan, and after the drafts. Nothing is posted or sent.

## When to use it

- Once a week, ideally a few days before the posting week starts.
- When you want a mix of post types rather than five versions of the same post.

Not for a single post (go straight to `/linkedin-expert-posts`, `/linkedin-personal-posts` or `/linkedin-carousels`).

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| Who the buyer is, pains and goals | Required | `context/icp/` |
| The author's point of view and proof | Required | `context/expert-pov/` |
| Voice | Required | the tone-of-voice file in `context/brand/` |
| Positioning and offer | Recommended | `context/positioning/` |
| Goals (leads, calls, followers) | Recommended | `context/goals/` |
| This week's raw material | Recommended | The user: call notes, wins, things they built, questions clients asked |
| What worked before | Optional | `/linkedin-content-audit` findings |
| Brand colours and fonts | Optional | `context/brand/`, for carousels |

If `context/icp/` or `context/expert-pov/` is missing, ask the user for the buyer in one line and three things they believe about their field that peers would argue with. Run from that and list what was missing at the top of the plan.

Agency users: swap `context/` for `clients/<client>/context/`.

## Stage 1: the plan

1. **Read the context.** ICP, expert POV, voice, goals and the week's raw material. Produces: 3 to 5 buyer pains and 3 to 5 beliefs the author holds.
2. **Choose how many posts.** 3 to 5. Fewer, better posts beat a daily habit that breaks. Produces: the post count and days.
3. **Pick the mix.** Across the week, include at least one personal post and one expert post. Add a carousel when an idea has steps or proof worth showing. Example for 4 posts: expert, personal, carousel, expert. Produces: post types by day.
4. **Pick topics.** For each post: the topic, the buyer pain it serves, the raw material it comes from, and for expert posts the one belief it ends on. Drop any topic the buyer would not care about. Produces: the topic list.
5. **Get hooks.** Run `/linkedin-hooks` in single-post mode for each expert post and carousel: 10 hooks each. For personal posts, suggest 3 hook options from the story itself. Produces: hooks to choose from.
6. **Flag one call to action.** At most one post this week asks for something (a DM keyword, a call, a resource). The rest end on their point. Produces: the flagged post.
7. **Write the plan** and stop. The user picks hooks and edits topics.

## Stage 2: the week

Start only when the user approves the plan.

1. **Draft each post** with the matching skill:
   - Expert posts: `/linkedin-expert-posts` (hook, then ending, then body).
   - Personal posts: `/linkedin-personal-posts`. Open on "I". Only stories the user gave.
   - Carousels: `/linkedin-carousels` (slides, layout brief and caption).
2. **Check the batch.** No belief or proof point repeated within the week. At most one call to action. No two posts with the same hook type back to back.
3. **Run the quality checks** below on every post.
4. **Build the calendar** and stop. The user edits and posts by hand.

## Quality checks

- **Voice.** Each post sounds like the tone-of-voice file, not like a template.
- **No invented facts.** Stories, numbers and client details come from the user or the context files. Otherwise `[fill in]`.
- **Expert test.** On expert posts, proof sits in the first two lines.
- **Buyer test.** Would the buyer trust the author more after reading it? If a post only speaks to peers, cut or rewrite it.
- **AI tells.** No "Here's the thing:", no "It's not X, it's Y", no neat moral endings, no "Thoughts?" closers.
- **Links.** Any link goes in the post itself, never "link in the comments".
- **Wordiness.** Trim 15 to 20 percent from first drafts.

## What good looks like

- Every post maps to a real buyer pain and real raw material.
- The week has variety in type and hook, and one clear ask at most.
- The user can post each draft with small edits.

## Mistakes to avoid

- Five posts on the same theme in the same format.
- A call to action on every post.
- Topics chosen because they are trending, not because the buyer cares.
- Filling a thin week with invented stories. Post fewer instead.
- Skipping the plan stop and writing everything in one go.

## Output

Save to `outputs/social/linkedin/MMYY-week-<n>/`:

- `plan.md`: status line (draft or approved), the mix, and per post: day, type, topic, buyer pain, belief, source material, hooks, call-to-action flag.
- `week.md`: every final post in posting order, with its hook, any image or carousel file, and placeholders to fill.
- A calendar table at the top of `week.md`:

| Day | Type | Topic | Hook | Call to action |
|---|---|---|---|---|
| Mon | Expert | ... | ... | none |
