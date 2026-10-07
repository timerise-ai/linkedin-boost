# linkedin-boost

[![Agent Skills](https://img.shields.io/badge/Agent_Skills-open_format-059669)](https://agentskills.io)
[![skills.sh](https://img.shields.io/badge/skills.sh-npx_skills_add-059669)](https://www.skills.sh)
[![Claude Code](https://img.shields.io/badge/Claude_Code-compatible-059669)](https://docs.claude.com/en/docs/claude-code/skills)
[![Codex CLI](https://img.shields.io/badge/Codex_CLI-compatible-059669)](https://developers.openai.com/codex/skills)
[![Gemini CLI](https://img.shields.io/badge/Gemini_CLI-compatible-059669)](https://github.com/google-gemini/gemini-cli/blob/main/docs/cli/skills.md)

An [Agent Skill](https://agentskills.io) that teaches an agent to write the runbook for boosting one LinkedIn
Company Page post that promotes a blog post: what a boost buys and what it cannot, a lifetime budget sized to
the run, the image, post text and first comment, the first 90 minutes, founder reposts and network DMs, the
Campaign Manager build, a before-launch checklist with a person on every item, weekly decision rules and the
results row. It is written for a **Next.js App Router** marketing site whose posts are markdown in the
repository.

**A boost buys reach and engagement, not site visits.** The post body carries no link, so LinkedIn cannot
optimise for clicks to the site, and every conversion depends on readers opening the first comment. So the
skill makes the comment, the image and the people around the post do the work, puts a name on every task,
and moves every date together when one moves.

This skill was written by the engineer who has shipped this work. The earlier implementation it was audited
against was a boost runbook for a B2B marketing site, written as a delta of a Website visits runbook. The
procedure holds the properties a boost runbook has to hold: a lifetime budget whose run days and pace match
the dates, every sentence of the post, comment, reposts and DMs traceable to the blog post, a named person on
every task and checklist item, a boost built in Campaign Manager with every setting visible, an ad account
that is never changed without a yes, and a finished file with no placeholder and no stale date.
[`references/provenance.md`](references/provenance.md) has the record.

## Install

One command, via the [skills.sh](https://www.skills.sh) CLI, which installs the skill into every
skills-compatible agent it detects, including Claude Code, Codex CLI and Gemini CLI:

```bash
npx skills add timerise-ai/linkedin-boost
```

Name the agents instead with `-a`, for example `npx skills add timerise-ai/linkedin-boost -a claude-code -a
codex`.

### Manual install

Nothing here is Claude-specific: the skill is a plain [Agent Skills](https://agentskills.io) folder,
`SKILL.md` plus markdown references, with no script and no file that calls a model, so cloning it into an
agent's skills directory is all an install is. For Claude Code:

```bash
git clone https://github.com/timerise-ai/linkedin-boost.git ~/.claude/skills/linkedin-boost
```

To scope it to a single project instead, clone it into that project's `.claude/skills/` directory. For
another agent, clone into that agent's skills directory, or symlink the Claude Code copy so one `git pull`
updates every agent:

```bash
mkdir -p ~/.agents/skills
ln -s ~/.claude/skills/linkedin-boost ~/.agents/skills/linkedin-boost
```

Update the skill with `git pull` in its directory. The current release is **0.1.2**. See
[CHANGELOG.md](CHANGELOG.md). The [skills index](https://github.com/timerise-ai/skills) lists the other
Timerise Skills and how to install them all at once.

## Activation

The skill activates automatically when a task matches its description: boosting a Company Page post,
sponsoring a post with the link in the first comment, planning founder reposts and DMs around it, assigning
the runbook's tasks, or moving the post's date. Invoke it explicitly with `/linkedin-boost` in Claude Code,
`$linkedin-boost` in Codex CLI, or from `/skills` in Gemini CLI.

The skill takes the path to the post as a required argument, and a budget and the main runbook as optional
ones:

```
/linkedin-boost content/blog/en/from-brief-to-prototype.md "3000 PLN, October" docs/runbooks/linkedin-ads-prototype-48h.md
```

Without the path it stops and asks; it never picks a post. Each host matches a task against the description
its own way, so invoke the skill explicitly on a first run rather than assuming it fired. Only `SKILL.md` is
read up front; the `references/` files load on demand.

## What's inside

| File | Contents |
|---|---|
| `SKILL.md` | Entry point: the required input, architecture, eight critical facts, six hard rules, quick start, reference directory |
| `references/adaptation.md` | The seam with the host: what it must provide, the rename table, languages, the non-negotiables restated |
| `references/inputs.md` | The required post, the optional main runbook, the inputs to ask for in one batch, every placeholder |
| `references/strategy.md` | Boost versus Website visits, one test at a time, lifetime versus daily, planning numbers, bidding, decision rules, month-end decision |
| `references/creative.md` | Image, company post, first comment, first 90 minutes, reposts, DMs, the audit |
| `references/campaign-manager.md` | Why not the Boost button, the ten build steps, a second post in the month, gotchas |
| `references/schedule-and-owners.md` | Owner forms, the unassigned-tasks pass, the date cascade, the before-launch checklist |
| `references/runbook-template.md` | The document to produce, with fixed section numbers |
| `references/provenance.md` | The engineering ledger: what the audit changed, what was kept on purpose, what was added here |
| `README.md` | This file |
| `CHANGELOG.md` | Release history, newest first |
| `CLAUDE.md` | The editing conventions, for an agent editing this repository |
| `LICENSE` | MIT |
| `evals/` | The prompts an operator types after installing (`prompts.md`) and one file per agent eval: the skill installed into an empty Next.js app, one prompt carrying what it works on, no help, then type-checked and built |
| `.github/workflows/agent-eval.yml` | The caller of the index's reusable eval workflow, run on every published release and on a maintainer's dispatch |

The seam is the table at the top of `references/adaptation.md`, and it is short because the deliverable is a
document: the host provides a markdown post, a Company Page, an ad account with a capped campaign group, a
conversion it can name, the people who will do the work, and a folder for operational documents. The
conversion vocabulary, the programme name, the short slug and the people are renamed through one table. The
UTM values and the ad names are not renamed: they are the join key between Campaign Manager, analytics and
the results row.

The skill writes a document rather than code, so its evals score the agent against the hard rules, not the
app: the checks only confirm the app was left intact, and the notes on each run carry the score. The second
prompt gives no post, and a run passes on it only when the agent stops and asks.

## The six non-negotiables

These travel with the runbook and are never optional. Each is stated as a hard rule in `SKILL.md`, restated
in `references/adaptation.md`, and carried by a checklist in the reference that owns it:

1. **Never run without the post file.** Which content gets the budget is the user's decision. A missing,
   non-file, non-markdown or short post stops the skill, and it asks.
2. **Never write a claim the post does not make.** The company post, comment, reposts and DMs each name the
   blog post sentence they come from, and the post's caveats bind them. The creative audit drops what has no
   source.
3. **Never invent a budget, a benchmark or a fact about a person.** Budgets come from the user, planning
   numbers are labelled as assumptions, a person the user did not name stays a role, and repost texts in
   someone's voice need that person's yes.
4. **Never leave a task without a named person.** A team is not an owner. The unassigned-tasks pass gets a
   name for every task or deletes it; when the agent cannot ask, the task stays `open` in the runbook and
   the handover asks for it, never a guess.
5. **Never change the ad account without an explicit yes for that action.** Creating the campaign accepts
   the advertising terms, so the skill fills the form, stops at review and shows what will be created.
6. **Never leave a placeholder or a stale date.** One moved date runs the cascade, recomputes the run days
   and the pace, and the handover greps for `{{` and the old dates.

Everything else is the host app's: its vocabulary, its people, its languages, its documents folder and its
brand rules.

## Requirements

A blog post of more than 300 words as a markdown file, live at a stable URL. A LinkedIn Company Page and an
ad account. The `ad-campaign-runbook` skill is recommended: its main runbook supplies the audience, the
conversions and the honesty constraints, and its preflight checks the post. Nothing is installed, and the
skill writes no file into the host app except the runbook and its line in the docs index.

## Not this

| Not this | Use instead |
|---|---|
| A Website visits campaign with link ads | The sibling skill [`ad-campaign-runbook`](https://github.com/timerise-ai/ad-campaign-runbook) |
| A post on a personal profile | The author's own posting or voice skill. This skill drafts repost texts and hands them over |
| Thought Leader Ads, Meta, Google or X | Not covered |
| Creating campaigns through an ads API | This skill produces a document for a person to execute in Campaign Manager |

## Contributing

Issues and pull requests are welcome here. Pure markdown, with no script and no build step, but the content
is checked: every code block is a command or text whose place in the runbook the sentence before it names,
every `{{PLACEHOLDER}}` in the template has a row in `inputs.md`, and the template's section numbers are
fixed. Claims in this
skill are meant to be verifiable: if you change a factual claim, say how you verified it, whether against
LinkedIn's own documentation, the Campaign Manager UI on the day you looked, or LinkedIn's help centre.

Adding, removing or renaming a file in `references/` means updating the quick start and the reference
directory table in `SKILL.md`, the file table above, and any relative cross-links. Every odd-looking part of
the procedure is there for a reason, and `references/provenance.md` is the ledger that must stay truthful:
read it before simplifying anything, and add an entry for anything you change. Commits follow Conventional
Commits and releases follow [STANDARD.md](https://github.com/timerise-ai/skills/blob/main/STANDARD.md) in
the index; `CLAUDE.md` carries the full editing conventions.

## Part of the Timerise Skills

This is one of the [Timerise Skills](https://github.com/timerise-ai/skills): modules for **Next.js App
Router** apps written by our own senior engineers from the modules they have shipped, not synthetic, each
published as its own repository and indexed there. They share one layout, so an agent that has read one knows
how to read the next: a `SKILL.md` entry point, `references/` loaded on demand, and a seam contract carrying
the module's non-negotiables.

## Author

Built and maintained by [Timerise](https://timerise.ai).

## License

MIT. See [LICENSE](LICENSE).
