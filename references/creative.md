# Creative: image, post, comment, and the people around it

The blog post is the source of truth. Nothing in the company post, the comment, a repost or a DM may say what
the post does not. If a main runbook exists, its offer, proof points and honesty constraints apply as they
stand; cite their section instead of restating them.

## 1. Image

| Item | Spec |
| :-- | :-- |
| Size | **1200 × 1200 px**, PNG or JPG, under 5 MB. Square: most feed impressions are mobile |
| Subject | The thing the post is about, shown, not described. A screen from a fictional business when the offer is software |
| Words | At most 8. One line the reader can take in at thumbnail size |
| Look | The host's visual language: its accent colour, its typeface, its cover motif. No campaign look of its own |
| Never | A real customer's material without written clearance |

## 2. Company post text

| Rule | Why |
| :-- | :-- |
| Hook inside the first **140 characters** | That is what a phone shows before "see more". The reason to care goes there |
| **No link in the body** | Kept from the organic post; the link goes in the first comment |
| No hashtags, or at most two at the end | More reads as reach-chasing |
| The post's own caveats, said plainly | If the post says "within 48 hours", never "guaranteed"; if it is a prototype, never a trial or an MVP. A short "what it is not" paragraph earns trust |
| Close by pointing at the comment | "...: link in the first comment." One line, no pitch |
| 900 to 1,300 characters | Long enough to carry the offer and its limits |

No "not X, it's Y" contrast frames, and none of: leverage, seamless, robust, unlock, streamline,
game-changer. Do not reuse the post's opening in the reposts: side by side they read as a template.

## 3. First comment

Posted by the Company Page within one minute of publishing, pinned if LinkedIn offers it.

```
<one line saying what the reader gets by opening the link, in the post's own words>
<POST_URL>?utm_source=linkedin&utm_medium=paid&utm_campaign=post-<short slug>&utm_content=boost-01
```

**`utm_medium=paid` although organic viewers see the same comment.** The boost delivers most of the
impressions, and analytics cannot split one link into two audiences. Say in the runbook: read this link's
sessions as "the boosted post".

## 4. The first 90 minutes

| Rule | What to do |
| :-- | :-- |
| Comments | Two or three teammates, one comment each, **12 or more words**, each with its own angle, spread across the first hour |
| Replies | The page replies to every comment, each reply written fresh |
| Reshares | **None without text**, at any point. They add nothing and read as a pod |
| Edits | None. Once the boost starts, an edit sends the post back to review |
| Owner | One named person lines up the commenters and replies as the page |

## 5. Reposts by the founders

The founders **repost with their own text** ("Repost with your thoughts"), not plain reshares.

| Rule | Why |
| :-- | :-- |
| On different days, a few days apart | The topic stays in their networks for two weeks instead of one morning |
| In their network's language | A network that is mostly Polish reads Polish. Say in the runbook when the site is in another language; the repost does not hide it |
| Each with a different angle | The technical "how is this possible" and the buyer's "screen versus PDF" reach different people |
| The link in **their own** first comment | With `utm_medium=organic` and `utm_content=repost-<name>`, so each repost is measured on its own |
| Drafted, not published | The person's voice skill writes the draft if one is installed; the person says yes or rewrites it. Never published on someone's behalf |
| No claim beyond the post | No client, number or result that is not in the blog post |

The link in each founder's first comment, one `<name>` per founder:

```
<POST_URL>?utm_source=linkedin&utm_medium=organic&utm_campaign=post-<short slug>&utm_content=repost-<name>
```

The runbook carries a table: who, when (date and time), angle, `utm_content`. Then each draft in section 8.

## 6. DMs to the network

| Rule | Why |
| :-- | :-- |
| From day 2 onward, after the boost starts | The post already has comments when the reader arrives |
| **One by one, at most 20 a day per person** | Bulk sends and group messages are what LinkedIn treats as spam |
| A personal first line, or do not send | "[one personal line: how we know each other, or something of theirs you saw recently]". A message without it is a mailing |
| **Never ask for likes or comments** | That is the definition of an engagement pod |
| The ask: forward it, or say what does not convince you | Forwarding to someone who is buying is the outcome that matters; honest objections improve the next post |
| Link the **company post**, not the blog post | Engagement then lands on the boosted ad |

Write the DM in each sender's language, with both brackets left for the sender to fill.

## 7. Audit before anything is published

| Check | How |
| :-- | :-- |
| Traceability | For every sentence in the post, comment, reposts and DMs, name the blog post sentence it comes from. Drop what has no source |
| Hook | Print the first 140 characters of the company post and of each repost. Would you stop scrolling? |
| Contrast frames and vocabulary | Grep for `\bnot\b.{1,40},? (it's|your|but)` and the vocabulary list |
| Links | No link in any post body; every comment link carries the right `utm_medium` and `utm_content` |
| People | Every repost draft marked as needing its author's yes |

## Creative checklist

- [ ] Image spec and the line on the image written down
- [ ] Company post: hook in 140, no link, honesty constraints from the post, ends pointing at the comment
- [ ] First comment with `utm_medium=paid` and `utm_content=boost-01`, and the reason for `paid`
- [ ] First 90 minutes rules, with one named owner
- [ ] Repost table and drafts, each with its own `utm_content`, staggered days, in the right language
- [ ] DM drafts with both brackets left open and the 20-a-day cap
- [ ] Audit done
