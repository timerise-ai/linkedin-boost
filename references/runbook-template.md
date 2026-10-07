# The runbook template

Copy everything below the line into `{{RUNBOOK_FILE}}` and replace every placeholder. Placeholders are defined
in [inputs.md](inputs.md). Blocks come from the other references; do not shorten a table to a sentence.

Keep the section numbers. People cite "3.5" and "section 6", and the next boost's runbook is a copy of this
one. A section that does not apply stays, with one line saying why. Section 9 exists only when there is no
main runbook.

---

# Runbook: LinkedIn Boost Post for "{{POST_TITLE}}"

**Type:** Short campaign runbook (one boosted Company Page post)
**Budget:** {{BUDGET}} {{CURRENCY}} for {{RUN_MONTH}}, lifetime, ends {{BOOST_END}}
**Source content:** `{{POST_PATH}}`, live at `{{POST_URL}}`
**Goal:** {{GOAL}}
**Owner:** {{OWNERS}}
**Status:** Draft, not launched
**Open:** {{OPEN_ITEMS}}
**Last updated:** {{TODAY}}

> The full playbook (offer, honesty rules, audience, conversions, Campaign Manager basics) is
> `{{MAIN_RUNBOOK}}`. This file covers only what differs for a boosted post. Where the two disagree for
> {{RUN_MONTH}}, this file wins.

---

## 1. What a boost changes

The trade-off table from [strategy.md](strategy.md), with the host's conversion path in the "Path to the
conversion" row. Then the consequence in one bold sentence, and:

**Do not run the Website visits campaign in {{RUN_MONTH}}.** Both draw on the same group cap. The main
runbook's campaign starts in {{WV_MONTH}} at the earliest, using what this boost teaches about the audience.

## 2. Budget and schedule

{{SCHEDULE_TABLE}}

{{RUN_DAYS}} days at {{BUDGET}} {{CURRENCY}} is about **{{DAILY_PACE}} {{CURRENCY}} a day**. Use a
**lifetime** budget, not daily: LinkedIn may overspend a daily budget on good days, but never the lifetime
total.

Planning numbers, not measurements: engagement CPM runs roughly {{CPM_LOW}} to {{CPM_HIGH}} {{CURRENCY}}, so
the budget buys about {{IMPRESSIONS_LOW}} to {{IMPRESSIONS_HIGH}} impressions. Comment link clicks are a small
fraction of engagements. Expect **0 to 3 {{CONVERSION_NAME}}s** in the month. Zero is inside normal variance.

## 3. Creative

### 3.1 Image

The image spec from [creative.md](creative.md). On the image: **"{{IMAGE_LINE}}"**. Never a real customer's
material.

### 3.2 Post text (Company Page voice)

The rules in one paragraph, citing the main runbook's honesty constraints, then:

```
{{POST_TEXT}}
```

### 3.3 First comment (posted by the Company Page, pinned if LinkedIn offers it)

```
{{COMMENT_LINE}}
{{POST_URL}}?utm_source=linkedin&utm_medium=paid&utm_campaign=post-{{SHORT_SLUG}}&utm_content=boost-01
```

The paragraph on why `utm_medium=paid`.

### 3.4 First 90 minutes

**Owner: {{OWNER_FIRST_90}}** (lines up the commenters and replies as the page). The rules from
[creative.md](creative.md).

### 3.5 Founder reposts and network DMs

The repost rules, in {{REPOST_LANGUAGE}}, then:

{{REPOSTS_TABLE}}

The organic URL with `utm_content=repost-<name>`, then the DM rules: from day 2 ({{BOOST_START}}) onward, one
by one, at most 20 a day per person, a personal first line, never "please like or comment", the ask is to
forward or to object, the DM links the company post. Texts are in section 8.

## 4. Setting up the boost

**Owner: {{OWNER_BUILD}}.** The ten steps from [campaign-manager.md](campaign-manager.md) with: account
{{AD_ACCOUNT}}, group `{{CAMPAIGN_GROUP}}`, audience template `{{AUDIENCE_TEMPLATE}}`, campaign name
`POST | {{SHORT_SLUG}} | BOOST | <yyyy-mm>`, lifetime {{BUDGET}} {{CURRENCY}} from {{BOOST_START}} to
{{BOOST_END}}, conversions {{CONVERSIONS_TO_TICK}}, ad name `BOOST-01`.

## 5. Before launch

{{BEFORE_LAUNCH_CHECKLIST}}

## 6. Weekly check (Mondays, 15 minutes)

**Owner: {{OWNER_WEEKLY}}**, including matching new {{CONVERSION_NAME}}s in {{CONVERSION_LIST}}.

The decision rules table from [strategy.md](strategy.md), with "about {{WEEKLY_PACE}} {{CURRENCY}} a week" in
the pace row. Then: do not touch anything else during the month.

## 7. Results (fill on {{BOOST_END}})

**Owner: {{OWNER_RESULTS}}**, including the decision for the next month. Add one row to {{TRACKING_SHEET}}
with `post = {{SHORT_SLUG}} (boost)`, plus:

| Measure | Source |
| :-- | :-- |
| Spend, impressions, CPM | Campaign Manager |
| Engagements, rate, CPE | Campaign Manager |
| Comment link sessions | Analytics, `utm_content=boost-01` (consented visitors only, a floor) |
| {{CONVERSION_NAME}}s created | {{BASELINE_SOURCE}}, versus the baseline |
| {{OUTCOME_NAME}} | {{CONVERSION_LIST}}: {{CONVERSION_NAME}}s created in the run that reached it |
| Cost per {{CONVERSION_NAME}}, per {{OUTCOME_NAME}} | Spend / each of the two above |

Then the month-end decision from [strategy.md](strategy.md): boost again with a new post, move to the
Website visits campaign, or stop. The deciding fact is whether the comment link moved anyone to
`{{CONVERSION_PATH}}`.

## 8. Repost and DM texts

One line: drafts; each needs its author's yes; none claims a client, number or result not in the post.

{{REPOST_TEXTS}}

{{DM_TEXTS}}

## 9. Shared setup (only without a main runbook)

{{SHARED_SETUP}}
