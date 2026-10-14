---
name: linkedin-content-audit
description: 'Audits the recent posts of one or more LinkedIn creators (yours, a competitor, or people your buyers follow) and shows what works: hook types, post types, formats, calls to action and engagement, with a comparison across profiles. Diagnostic only; it does not write posts. Triggers: "LinkedIn content audit", "audit LinkedIn profiles", "analyse creator posts", "benchmark LinkedIn creators", "what is working on my LinkedIn", "LinkedIn pattern analysis".'
version: '1.0.0'
license: MIT
---

# LinkedIn content audit

Read a set of LinkedIn posts, classify each one, and find the patterns behind the posts that perform. The output tells you which hooks, formats and calls to action earn engagement for this audience, with evidence from real posts.

## When to use it

- Before planning content, to see what already works on your own profile.
- To benchmark against two to five creators your buyers follow.
- Every quarter, to check whether your mix has drifted.

Not for writing posts (use `/linkedin-expert-posts` or `/linkedin-personal-posts`) or for generating hooks (use `/linkedin-hooks`).

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| 1 to 10 profile URLs | Required | The user |
| The posts themselves | Required | See below |
| Who your buyer is | Recommended | `context/icp/`, so you can judge relevance, not just reach |
| Time window | Optional | Default: the last 6 months |

**Getting the posts.** The simplest route is the user pasting posts or exporting them from a LinkedIn analytics tool as CSV, with likes, comments, reposts and dates. If you have a scraping tool connected (for example an Apify LinkedIn posts actor), you can use it; check the cost before you run it. Screenshots work too. Aim for 50 to 100 posts per profile.

If a profile has fewer than 10 posts, mark it "not enough data" and leave it out of comparisons.

Agency users: swap `context/` for `clients/<client>/context/`.

## Steps

1. **Check inputs.** Confirm the URLs, the window and how many posts per profile. Produces: the list you will audit.
2. **Collect and clean.** Gather post text, date, format and engagement (likes, comments, reposts). Exclude reposts of other people's content. Produces: one table per profile.
3. **Pick the posts to study.** Add up engagement per post, sort, and take the top 25 per profile for deep analysis. Keep the full set for volume and cadence. Produces: top-25 lists plus posting frequency.
4. **Classify the hook.** Read the first line or two. Tag the hook type: bold claim, contrarian take, number or result, question, story opening, list promise, mistake or warning, how-to. Produces: hook mix with average engagement per type.
5. **Classify the post type.** Educational, personal story, promotional, company news or engagement post. Produces: post-type mix per profile.
6. **Classify the format.** Text only, carousel or document, single image, video, poll, article, external link. Produces: format mix with average engagement per format.
7. **Describe the visuals.** For posts with images, describe what they show (screenshot, chart, photo of the person, meme, text on image) from the post text and the image you were given. Never guess from a file name. Produces: visual content notes.
8. **Classify the ending.** Comment prompt, DM invite, link, follow ask, save ask, no call to action, or several. For link posts, note where the link sat (in the post, as a preview card, or in comments). Produces: call-to-action mix with engagement per type.
9. **Cross the data.** Engagement by hook type, by format, by post type and by call to action. List the top 5 posts with a short excerpt each. Produces: the pattern tables.
10. **Compare profiles** (if two or more). Side-by-side format mix, hook mix, engagement benchmarks, posting cadence. Produces: a comparison matrix.
11. **Write the findings.** Patterns to copy and patterns to avoid, each one citing the posts it comes from. Produces: the audit report.

## What good looks like

- Every finding points to specific posts. No finding rests on a hunch.
- Percentages in each category add to 100.
- Small samples are labelled. A pattern seen in three posts is a lead, not a rule.
- The takeaways are things the user can do next week, not general advice.
- Engagement is read against relevance: a post that went viral with the wrong audience is noted as such.

## Mistakes to avoid

- Drawing conclusions from fewer than 10 posts.
- Comparing raw engagement across accounts of very different sizes without saying so.
- Calling a format "the winner" when only two posts used it.
- Inventing engagement numbers or guessing what an image showed.
- Copying a creator's hooks word for word. Take the pattern, not the line.

## Output

Save to `outputs/social/linkedin/`:

- `MMYY-linkedin-audit-<profile>.md` per profile: summary, posting cadence, hook mix, post-type mix, format mix, call-to-action mix, top 5 posts, patterns to copy, patterns to avoid.
- `MMYY-linkedin-audit-comparison.md` if there were two or more profiles: comparison matrix and the 3 to 5 takeaways that matter most.

Feed the findings into `/linkedin-hooks` (which hook types to favour) and `/linkedin-weekly-content` (which formats and post types to plan).
