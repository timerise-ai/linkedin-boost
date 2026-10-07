# Inputs and the placeholder table

One input is required and cannot be defaulted. Everything else is asked once, in one batch, or read from the
main runbook.

## The required parameter: the blog post

| Rule | Why |
| :-- | :-- |
| The path to the post's `.md` or `.mdx` file must be given by the user | Which content gets the budget is the user's decision, never the agent's |
| No path, not a file, or not markdown: **stop and ask** | A confident runbook for the wrong post is worse than none |
| Under 300 words: stop and say so | A company post, a comment and two reposts with different angles, all traceable, do not come out of a short post |
| A URL instead of a file: ask for the file | Claims are traced to the source text, not a rendered page |

If the `ad-campaign-runbook` skill is installed, run its preflight, which enforces these rules and exits `2`
when the post is unusable:

```bash
python3 <ad-campaign-runbook dir>/assets/preflight.py <post.md> --cta <conversion path> --site <https://site>
```

Otherwise check the four rules by hand and read the post end to end.

## The optional parameter: the main runbook

| With a main runbook | Without one |
| :-- | :-- |
| The boost runbook is a delta. It cites the main runbook's honesty constraints, audience, exclusions, conversions, tracking sheet and matching procedure by section number | Write section 9 of the template: the offer and honesty constraints ([creative.md](creative.md) of `ad-campaign-runbook`), the audience, the conversions that exist, how conversions are counted. Or run `ad-campaign-runbook` first and come back |

Look for it in the host's runbook folder before asking: `<channel>-ads-<short slug>.md`.

## Inputs to ask for

Ask in one batch, after reading the post and the main runbook, so the questions can quote what was found.
Skip any the user already gave.

| Input | Ask | Default if the user declines |
| :-- | :-- | :-- |
| Budget, currency, month | "How much for the boost, in which currency, for which month?" | None. Do not invent a budget |
| Publish date and time | "When does the Company Page post go out?" | The next Tuesday or Wednesday, 7:30 in the audience's timezone, marked as a proposal |
| A person per role | "Who publishes and runs the first 90 minutes, who builds the boost, who owns tracking, who does the weekly check and the results?" | None. Ask again for each gap; see [schedule-and-owners.md](schedule-and-owners.md) |
| Reposting founders | "Who reposts with their own text, in which language, and does any of them have a voice skill?" | No reposts; section 3.5 says so in one line |
| Ad account | "Which account, its currency, which campaign group?" | From the main runbook |
| Where conversions land | "Where do new conversions show up, and what follows from one?" | From the main runbook |

Never ask for credentials, and never sign in on the user's behalf. Reading a signed-in session is fine;
creating or changing anything needs an explicit yes for that action.

## Placeholders

Every `{{NAME}}` in [runbook-template.md](runbook-template.md) is defined here. A placeholder left in a
finished runbook is a defect.

| Placeholder | Source | Example |
| :-- | :-- | :-- |
| `{{RUNBOOK_FILE}}` | `<channel>-boost-<short slug of the main runbook>.md` beside the main runbook | linkedin-boost-brief-to-prototype.md |
| `{{POST_TITLE}}` | post frontmatter | From Brief to Clickable Prototype in 48 Hours |
| `{{POST_PATH}}` | the required parameter, repo-relative | content/blog/en/from-brief-to-prototype.md |
| `{{POST_URL}}` | the live URL, confirmed | https://example.com/blog/from-brief-to-prototype |
| `{{SHORT_SLUG}}` | the main runbook's short slug, or two or three words of the post slug | prototype-48h |
| `{{MAIN_RUNBOOK}}` | the optional parameter; without one, "section 9 of this file" | linkedin-ads-prototype-48h.md |
| `{{TODAY}}` | today, ISO | 2026-10-07 |
| `{{BUDGET}}`, `{{CURRENCY}}`, `{{RUN_MONTH}}` | user input | 3,000, PLN, October 2026 |
| `{{GOAL}}` | the conversion and what follows from it | briefs created, and prototypes sent from them |
| `{{OWNERS}}` | the header form in [schedule-and-owners.md](schedule-and-owners.md) | Ana Kim (post, boost); Ben Ode (tracking) |
| `{{BOOST_START}}`, `{{BOOST_END}}` | the publish date (user input) and the date cascade | 2026-10-09, 2026-10-31 |
| `{{SCHEDULE_TABLE}}` | [schedule-and-owners.md](schedule-and-owners.md), with a `Who` column | |
| `{{RUN_DAYS}}`, `{{DAILY_PACE}}`, `{{WEEKLY_PACE}}` | [strategy.md](strategy.md) formulas | 23, 130, 915 |
| `{{CPM_LOW}}`, `{{CPM_HIGH}}` | planning assumption in the account currency, or the last results row | 40, 120 |
| `{{IMPRESSIONS_LOW}}`, `{{IMPRESSIONS_HIGH}}` | budget / CPM high and low × 1,000 | 25,000, 75,000 |
| `{{WV_MONTH}}` | the month after the boost ends | November |
| `{{CONVERSION_NAME}}`, `{{CONVERSION_PATH}}` | main runbook or host | brief, /brief |
| `{{CONVERSION_LIST}}` | where new conversions show up | the internal briefs list |
| `{{OUTCOME_NAME}}` | what the team delivers from a conversion | Prototypes sent |
| `{{IMAGE_LINE}}` | [creative.md](creative.md), at most 8 words | Your brief. Your prototype. 48 hours. |
| `{{POST_TEXT}}`, `{{COMMENT_LINE}}` | [creative.md](creative.md) | |
| `{{OWNER_FIRST_90}}`, `{{OWNER_BUILD}}`, `{{OWNER_WEEKLY}}`, `{{OWNER_RESULTS}}` | user input, one named person each | |
| `{{REPOST_LANGUAGE}}` | the founders' network language | Polish |
| `{{REPOSTS_TABLE}}`, `{{REPOST_TEXTS}}`, `{{DM_TEXTS}}` | [creative.md](creative.md) | |
| `{{AD_ACCOUNT}}`, `{{CAMPAIGN_GROUP}}`, `{{AUDIENCE_TEMPLATE}}` | main runbook or the account | Example Ltd (123456789), Blog posts, TPL - Buyers EU |
| `{{CONVERSIONS_TO_TICK}}` | the conversions that exist in the account | `Conversion - Brief`, `Brief - submitted` |
| `{{BEFORE_LAUNCH_CHECKLIST}}` | [schedule-and-owners.md](schedule-and-owners.md), a name on every item | |
| `{{TRACKING_SHEET}}` | main runbook's tracking sheet, its monthly tab | the "Monthly" tab of the shared sheet |
| `{{BASELINE_SOURCE}}` | how conversions are counted in the host's own data | the events table, query in the main runbook |
| `{{SHARED_SETUP}}` | only without a main runbook, see above; otherwise delete section 9 | |

## Input checklist

- [ ] The post path came from the user and passed the four rules
- [ ] The main runbook found or its absence noted, with section 9 planned
- [ ] Budget, currency and month came from the user
- [ ] Every role has a named person, or the task was deleted
- [ ] Every open input is listed as open in the runbook, not silently filled
