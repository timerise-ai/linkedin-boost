# Adaptation: the seam with the host

This skill writes a document. The seam is what the host must already have, the vocabulary the runbook takes
from the host, and where the file lives.

## What the host must provide

| Requirement | Why | If it is missing |
| :-- | :-- | :-- |
| A blog post as a `.md` or `.mdx` file, over 300 words, live at a stable URL | Every sentence of the post, comment, reposts and DMs is traced to it; the comment links to it | Stop and ask for the file. Not live: write the runbook, mark the publish as blocked |
| A LinkedIn Company Page the team can post as | The boost sponsors an existing page post | Not a boost. Use `ad-campaign-runbook` or a personal post |
| An ad account and a campaign group with a cap | The boost is a campaign inside it | The main runbook's build creates them |
| A conversion the business can name, and a list where new ones land | The weekly check matches them; the results row counts them | Section 9 records how to count by hand |
| Named people | Every task has one | Ask; delete tasks nobody takes |
| A runbook folder and its index | The runbook is committed beside the main runbook | Propose `docs/runbooks/` |

Optional and used when present: the main runbook from `ad-campaign-runbook`, a voice skill per founder, a
content standards file, earlier boost results.

## Rename table

| Canonical | What the host substitutes | Appears in |
| :-- | :-- | :-- |
| conversion | brief, demo, trial, quote, application | Header goal, sections 2, 6, 7 |
| outcome | what the team delivers from a conversion: prototype, call, proposal | Section 7 |
| conversion list | where new conversions show up: an internal console, a CRM view | Sections 6, 7 |
| programme | the campaign group name, for example "Blog posts" | Section 4 |
| short slug | the main runbook's short slug | `utm_campaign`, campaign name, runbook file name |
| roles | the people's names | Header, schedule, every `Owner:` line, checklist |

Not renamed: `utm_source=linkedin`, `utm_medium=paid` on the company post's comment and `organic` on the
reposts, `utm_content=boost-01` upward and `repost-<name>`, and the ad names `BOOST-01` upward. They are the
join key between Campaign Manager, analytics and the results row.

## Language

The company post and comment are in the site's language. Reposts and DMs are in each sender's network
language. When they differ, the runbook says so in one sentence, and does not hide that the site is in
another language.

## The non-negotiables, restated

1. **Never run without the post file.**
2. **Never write a claim the post does not make.**
3. **Never invent a budget, a benchmark or a fact about a person.**
4. **Never leave a task without a named person.**
5. **Never change the ad account without an explicit yes for that action.**
6. **Never leave a placeholder or a stale date.**

Everything else is the host's: its vocabulary, its people, its languages, its documents folder and its brand
rules.
