# Strategy: what a boost buys, and what it cannot

Decide this before writing a word of copy. A boost and a Website visits campaign look similar in Campaign
Manager and buy different things.

## Boost or Website visits

| Item | Website visits campaign (`ad-campaign-runbook`) | Boost of a Company Page post |
| :-- | :-- | :-- |
| Ad | Single image ad with a link | The existing Company Page post: text and image, link in the first comment |
| Objective | Website visits | **Engagement** |
| What a paid click buys | A visit to the blog post | An expanded post or an opened image. Not a site visit |
| Path to the conversion | Ad → blog post → conversion page | Post → first comment → blog post → conversion page |
| Social proof | None, every ad starts at zero | Likes and comments collected organically carry into the paid impressions |
| What it teaches | Which hook earns a click | Whether the audience engages with the topic at all, at a lower cost per impression |

Write the consequence into the runbook in one sentence: **LinkedIn cannot optimise for site visits here,
because the post body has no link.** It buys reach and engagement. Conversions depend on readers opening the
comment, so the comment and the image must do the work.

Choose the boost when the budget is small, the post is new, and the team wants to know what the audience
reacts to before paying for clicks. Choose Website visits when an earlier boost showed engagement but the
comment link moved nobody to the site: a link in the ad itself is then the next test.

## One test at a time

**Never run the boost and a Website visits campaign for the same post in the same month.** Both draw on the
same campaign group cap. Name the month in which the Website visits campaign may start, at the earliest the
month after the boost ends, and say that it uses what the boost taught about the audience.

## Budget type

| Run | Budget type | Why |
| :-- | :-- | :-- |
| A boost with a fixed end date (one month) | **Lifetime**, start and end set | LinkedIn may overspend a daily budget on good days, but never a lifetime total. The month's budget is the ceiling |
| An open-ended Website visits campaign with reviews | Daily | The reviews decide whether it continues; a daily budget keeps the spend even between them |

The boost starts one day after the organic publish, so it runs fewer days than the calendar month:

```
run_days     = days from boost start to boost end, both included
daily_pace   = budget / run_days          # for reading spend, not a setting
weekly_pace  = daily_pace * 7             # the "60% of pace" rule below reads this
```

Recompute all three whenever a date moves: [schedule-and-owners.md](schedule-and-owners.md).

## Planning numbers (assumptions, not measurements)

Label every one of these as an assumption in the runbook, or cite the results row it came from.

| Assumption | Planning value | Note |
| :-- | :-- | :-- |
| Engagement CPM, European B2B | about 9 to 28 EUR, in the account currency | The suggested range in the build is the first real data point |
| Impressions | budget / CPM × 1,000 | 3,000 PLN at 40 to 120 PLN buys about 25,000 to 75,000 |
| Comment link clicks | a small fraction of engagements | No planning value exists. The results row produces the first one |
| Conversions | **0 to 3 in the month** | Zero is inside normal variance at this volume |

## Bidding

Optimisation goal **Engagement**, **Maximum delivery** for the first week: one post, no history to bid
from. Switch to **Manual bidding** at the low end of the suggested range only if the CPM runs above the high
planning value.

## Weekly decision rules

Write them into the runbook with the host's numbers before launch. Nothing changes in the first week.

| Signal | Action |
| :-- | :-- |
| Spend under 60% of the weekly pace | Switch to manual bidding, bid 10% above the suggested low end |
| Engagement rate under 1% after 10,000 impressions | The hook is not landing. Publish a new post with a new image, boost it as `BOOST-02` with the remaining budget, pause `BOOST-01` |
| Engagement healthy, comment-link sessions under 1% of clicks | Readers do not find the link. Reply to new comments with a pointer to the pinned comment |
| More than 30% of engagement from agencies, recruiters, students | Add the exclusions from the main runbook's audience section |
| A new conversion in the host's list | Match it to the boost by date and source, record it as `likely`, never `confirmed` |

Do not touch anything else during the month. At this volume, daily numbers are noise.

## Month-end decision

Three outcomes, decided by one fact: **did the comment link move anyone to the conversion page?**

| Comment-link sessions and conversions | Next month |
| :-- | :-- |
| Sessions and at least one conversion | Boost again with a new post, carry the actuals into its planning numbers |
| Engagement healthy, sessions near zero | Move to the Website visits campaign from the main runbook: a link in the ad itself is the next test |
| Engagement under the rule above for the whole month | Stop paid for this topic. Work on the post and the organic reach |

## Strategy checklist

- [ ] The trade-off table is in the runbook, with the one-sentence consequence
- [ ] The month for a Website visits campaign named, never the same month as the boost
- [ ] Lifetime budget, run days, daily and weekly pace computed from the real boost start
- [ ] Every planning number labelled as an assumption
- [ ] Decision rules with thresholds written before launch
- [ ] The month-end decision and its deciding fact written down
