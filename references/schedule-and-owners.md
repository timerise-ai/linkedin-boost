# Schedule and owners: a person on every line, and dates that move together

A runbook whose tasks belong to "Marketing" gets read, agreed with and not done. And a runbook whose dates
were typed one by one goes stale the first time the publish date moves. Both happened to the runbook this
skill was built from, the same day it was written.

## Every task has a named person

| Where | Form |
| :-- | :-- |
| Header | `**Owner:** <Name> (<what they own>); <Name> (<what they own>)` |
| Schedule table | A `Who` column, one name per row |
| Each section that is a task (first 90 minutes, build, weekly check, results) | First line: `**Owner: <Name>**`, and what the ownership includes |
| Before-launch checklist | Every item starts with `**<Name>:**` |
| Reposts and DMs | The person is the row: who reposts, who sends |

A team, a department or "we" is not an owner. Neither is "the author" when the author is not named.

### The unassigned-tasks pass

Before handing the runbook over, and whenever someone asks "what is unassigned":

1. List every task with no name: schedule rows, checklist items, sections with no `Owner:` line, rules that
   imply work ("a new conversion → match it").
2. For each, say in one or two sentences what it is, how long it takes, and what breaks if nobody does it.
3. Ask the user, in batches of up to four, for a person or **delete**. Deleting is a valid answer: a task
   nobody will do is better gone than left as decoration.
4. Write the answers in, in the forms above. Recheck the header's `Owner:` line against them.

## The date cascade

One date drives the others. When the publish date moves, everything below moves in the same edit.

| Date | Rule |
| :-- | :-- |
| Preparation | Before the publish date; image, post text, comment, and the blog post review |
| **Organic publish** | The driver. A weekday, early morning in the audience's timezone (7:00 to 8:30) |
| First comment with the link | Within one minute of the publish |
| Boost start | **Publish + 1 day**, after 24 hours of organic engagement. Also the start date in build step 6 |
| First founder repost | Not on the publish day; the day of the boost start or later |
| Further reposts | A few days apart, so the topic stays in the networks for about two weeks |
| DMs | From day 2, the boost start, onward |
| Weekly checks | Mondays from the second week; none in the first week |
| Boost end | Unchanged unless the user moves it: the end of the month or run |
| Results | The boost end date |

Then recompute, in the same edit:

```
run_days    = boost end - boost start + 1
daily_pace  = budget / run_days
weekly_pace = daily_pace * 7      # the "60% of pace" decision rule quotes this number
```

Update the header's `Status` and `Last updated`. Grep the runbook for the old dates, in every format used
(`2026-10-07`, `10-07`, `Wed`), and for the old day count and pace, before saying it is done.

## The before-launch checklist

Only checks that are **not** build steps. A setting that the build already sets (audience expansion, Audience
Network) is set and checked in the build section, not ticked twice. Notifying a team is not an item when the
people who receive the conversions are the people named in the runbook.

| Item | Typical owner |
| :-- | :-- |
| Blog post changes from the main runbook live in production (conversion link near the top, the thing shown on the page) | Whoever deploys the site |
| **Blog post review before the organic post goes out**: images and screens render and read well, the text reads easily, SEO holds (title, meta description, headings, links, cover image) | Whoever owns the content |
| The comment URL opens and shows in analytics realtime with `utm_content=boost-01` | Whoever owns tracking |
| The tag is active and the conversions to tick in the build exist | Whoever owns tracking |
| No Website visits campaign for this post running or created | Whoever owns the ad account |
| Baseline written down: post sessions and conversions for the four weeks before launch | Whoever fills the results row |

Items already done when the runbook is written are ticked, with the date.

## Schedule and owners checklist

- [ ] Header `Owner:` names people and what each owns
- [ ] Schedule table has a `Who` column with a name on every row
- [ ] Every task section opens with `**Owner: <Name>**`
- [ ] Every checklist item starts with a name
- [ ] No checklist item repeats a build step
- [ ] Unassigned-tasks pass done; deleted tasks are gone, not commented out
- [ ] Dates follow the cascade; run days, daily and weekly pace match the dates
