---
name: linkedin-comment
description: 'Writes LinkedIn comments on other people''s posts that read human and build relationships with buyers and the people they follow. Each comment quotes something specific from the post, adds the author''s own experience, and ends on a sharp point or a real question. Bans generic praise, pitching and engagement bait. Also works for thread replies in communities and Slack. Triggers: "comment on this post", "LinkedIn comment", "write a comment", "reply to this post", "engage with this post", "my comments for today".'
version: '1.0.0'
license: MIT
---

# LinkedIn comment

Write comments on other people's posts. Comments put the author in front of the poster's audience and start relationships. A good comment is a small post in its own right; a generic one tells everyone it was written by a bot.

## When to use it

- Daily commenting: a handful of thoughtful comments on posts from buyers and the people buyers follow.
- A reply to someone who commented on the author's post.
- Thread replies on other surfaces (communities, Slack, cohort feedback), where the same rules apply.

Not for writing posts (`/linkedin-expert-posts`, `/linkedin-personal-posts`) or for DMs.

## Inputs

| Input | Required? | Where it comes from |
|---|---|---|
| The full post text | Required | The user (text or screenshot) |
| Who the poster is | Recommended | Role and company, from the user |
| Voice | Recommended | the tone-of-voice file in `context/brand/` |
| The author's expertise and stories | Recommended | `context/expert-pov/` |
| Who the buyer is | Recommended | `context/icp/`, to decide whose posts are worth the time |
| Relationship history | Optional | The user |

If the post is cut off, ask for the full text first. If the voice file is missing, ask for two comments the author wrote before and match them.

Agency users: swap `context/` for `clients/<client>/context/`.

## Whose posts

Comment where the buyer is: buyers themselves and the people they follow. Commenting mainly in peer threads teaches the algorithm the wrong audience. Skip politics, drama and pile-ons. When asked for a batch, flag any post that fails this test before drafting.

## The three-sentence shape

1. **Reference.** Quote or name a specific phrase or claim from their post.
2. **Add.** The author's own experience, a data point, a counter-example or a next step. First person: "I've seen...", "On the last project I...".
3. **Close.** A sharp claim, or a question whose answer the author actually wants.

For thread replies, lead with the useful move instead: what the author would do, in first person, with the acknowledgement woven in, not up front.

## Comment types

| Type | Use it when |
|---|---|
| Extend | You can take their point one step further |
| Story | You have a short real moment that proves or complicates it |
| Nuanced agreement | You agree, with a condition they missed |
| Contrarian | You see it differently and can say why, politely |
| Real question | You want to know how they handle a specific part |
| Bridge | You can connect their point to a related problem |

## Steps

1. **Read the post.** Write its point in one sentence and pick 2 to 3 quotable phrases. Produces: the hook into the comment.
2. **Pick the type** that fits the post and the author's real experience. Produces: the angle.
3. **Draft** in the three-sentence shape, in the author's voice. Produces: the comment.
4. **Run the anti-AI rules** below. Produces: the cleaned comment.
5. **Write an alternative** with a different type. Produces: two options to choose from.
6. **Suggest replies.** Two short options in case the poster responds. Produces: thread follow-ups.

## Anti-AI rules (non-negotiable)

- **Specific reference.** The first sentence names something from this post. The 100 posts test: if the comment could sit under 100 other posts, rewrite it.
- **No generic praise.** Never "Great post", "Love this", "So true", "This resonated", "Spot on", "Thanks for sharing".
- **No engagement bait.** Never "Thoughts?", "Agree?", "What do you think?", "Curious to hear your take". Ask only a question you need answered, or end on the claim.
- **No pitching.** No "DM me", "I can help", "We do this at...", "Book a call".
- **No invented experience.** Every story, number and credential is real. If there is none, write a comment that does not need one.
- **No AI rhythm.** No "It's not X, it's Y", no three short parallel sentences, no buzzwords, no emoji strings.
- **Length.** 50 to 150 words. Under 30 adds nothing; over 200 hijacks the thread. Short line breaks for mobile.
- **Vary the shape.** In a batch, no two comments use the same opening or structure.

## What good looks like

- The poster can tell the author actually read the post.
- The comment adds something the post did not have.
- It sounds like a person who does the work, talking to a peer.

## Output

Return in the chat: the post's point in one line, the comment, word count, comment type, the alternative, and two reply options. For a daily batch, number each comment and flag any post you suggest skipping.
