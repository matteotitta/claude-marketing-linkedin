---
name: linkedin-profile
description: 'Audits a LinkedIn profile and rewrites the copy so it speaks to one buyer and earns the click: a scored audit of 8 sections, a number check, three headline options, an About section in long and short form, every Experience entry, a Featured plan and a banner brief. Copy only; it does not render images. Triggers: "LinkedIn profile", "profile audit", "optimise my LinkedIn profile", "rewrite my headline", "fix my About section", "banner copy", "my profile is not converting". Not for posts, comments or carousels (use the other linkedin skills in this plugin).'
version: '1.0.0'
license: MIT
---

# LinkedIn profile

Audit a LinkedIn profile and rewrite every written part of it so a buyer who lands there understands, in a few seconds, who it is for, what it fixes and what to do next.

A profile is where your posts and comments send people. If it talks about you instead of the reader, the click is wasted no matter how good the content was.

## When to use it

- Before starting a posting routine, so the traffic lands somewhere that converts.
- When the person has changed offer, role or audience.
- When the profile gets views but no messages or calls.

Not for writing posts (`/linkedin-expert-posts`, `/linkedin-personal-posts`), comments (`/linkedin-comment`) or carousels (`/linkedin-carousels`). This skill writes copy and a banner brief; a designer or design tool turns the brief into the image.

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| The current profile | Required | PDF export (More, then Save to PDF) or pasted text |
| Who the buyer is | Required | `context/icp/` |
| The offer and the one action you want | Required | Ask the user |
| Positioning | Recommended | `context/positioning/` |
| Voice | Recommended | the tone-of-voice file in `context/brand/` |
| Proof (results, clients, numbers) | Recommended | `context/win-loss/`, `context/expert-pov/` or the user |
| Website or offer page | Recommended | Ask for the URL; read it with web search or Firecrawl if you have it |

If the ICP or offer is missing, ask for them before writing anything. Without them every line is a guess. If other context files are missing, run from what you have and list what was missing at the top of the output.

Agency users: swap `context/` for `clients/<client>/context/`.

## Steps

1. **Gather.** Read the profile, the ICP, positioning, voice and proof. Produces: a short fact sheet of who they help, the offer, and every number they claim.
2. **Number check.** List every figure on the profile (years, clients, revenue, followers, results). Mark each as checked against a source, confirmed by the user, or unverified. Produces: a number table. Unverified numbers do not go into the new copy.
3. **Score the audit.** Score each section against the table below and note the one biggest problem in each. Produces: a score out of 100 and a ranked fix list.
4. **Pick 3 to 5 buyer pains.** Take them from `context/icp/`, in the buyer's own words. Every line you write should serve one of them. Produces: the pain list you write against.
5. **Write the headline.** Three options, each one sentence: who you help, and what they get. Keep the key words in the first 100 characters, since LinkedIn cuts the rest in most views. Produces: three headlines with a recommended pick.
6. **Write the About section.** Open on the reader's pain, in their words, before the "see more" cut. Then what you have seen go wrong, how you help, proof, and end on one low-friction ask (a DM keyword, a link to a resource, a short call). Write a long version and a five-line short version. Produces: About, long and short.
7. **Rewrite every Experience entry.** Current role in depth: who it serves, what changes for them, results. Past roles in the past tense, short. Count the entries in the export and the rewrites; the numbers must match. Produces: every entry rewritten.
8. **Plan the Featured section.** Up to three items, each a link with one statement and one call to action, ordered from lowest to highest commitment. Produces: a Featured plan.
9. **Write the banner brief.** One line of copy that names the category and the buyer, an optional short proof point, and a note to keep the left third clear (the profile photo covers it on desktop and mobile). Produces: banner copy and layout notes for a designer.
10. **Hand over.** Produces the refresh doc below, plus a recommendation request the user can send to two or three past clients.

### Audit table

| Section | Max | What earns the points |
|---|---|---|
| Profile picture | 10 | Face clear at small size, eye contact, good contrast |
| Banner | 15 | One message, names the buyer, nothing under the photo |
| Headline | 15 | Names the buyer and the outcome in their words |
| About | 20 | Opens on a pain, specific, has proof, ends on one ask |
| Featured | 10 | Links not posts, clear calls to action, three at most |
| Experience | 15 | Current role explains the offer, results, correct tenses |
| Recommendations | 10 | Recent, relevant, describe a problem and an outcome |
| Contact link | 5 | Present and points at the one action |

## What good looks like

- A stranger can say who the profile is for and what it fixes after reading only the headline.
- The About opens on the buyer, not on the person's career history.
- Every number on the page is verified or confirmed by the user.
- There is one call to action, repeated consistently across About, Featured and the contact link.
- The copy sounds like the person, using the tone-of-voice file.

## Mistakes to avoid

- A headline that lists five job titles or skills.
- An About that opens with "I am a passionate..." or a career summary.
- Inventing results, client names or testimonials. Use `[need real metric]` instead.
- Keeping copy that sells a business the person no longer runs. Check Experience dates.
- Claims of speed ("in 30 days") that nothing on the page supports.
- Several competing asks. Pick one.

## Output

Save to `outputs/social/linkedin/MMYY-profile-refresh.md`:

1. Audit score out of 100 with the section table and ranked fixes.
2. Number table (verified, confirmed, unverified).
3. Three headlines, with a pick.
4. About: long and short.
5. Every Experience entry.
6. Featured plan.
7. Banner brief.
8. Recommendation request message.
9. Missing context, if any.

After the profile is fixed, plan posts with `/linkedin-weekly-content`.
