# linkedin-boost

[![Agent Skills](https://img.shields.io/badge/Agent_Skills-open_format-059669)](https://agentskills.io)
[![Claude Code](https://img.shields.io/badge/Claude_Code-compatible-059669)](https://docs.claude.com/en/docs/claude-code/skills)
[![Codex CLI](https://img.shields.io/badge/Codex_CLI-compatible-059669)](https://developers.openai.com/codex/skills)
[![Gemini CLI](https://img.shields.io/badge/Gemini_CLI-compatible-059669)](https://github.com/google-gemini/gemini-cli/blob/main/docs/cli/skills.md)

An [Agent Skill](https://agentskills.io) that teaches an agent to write the runbook for boosting one LinkedIn
Company Page post that promotes a blog post: what a boost buys and what it cannot, a lifetime budget sized to
the run, the image, post text and first comment, the first 90 minutes, founder reposts and network DMs, the
Campaign Manager build, a before-launch checklist with a person on every item, weekly decision rules and the
results row.

**A boost buys reach and engagement, not site visits.** The post body carries no link, so LinkedIn cannot
optimise for clicks to the site, and every conversion depends on readers opening the first comment. So the
skill makes the comment, the image and the people around the post do the work, puts a name on every task,
and moves every date together when one moves.

It is the sibling of [`ad-campaign-runbook`](https://github.com/timerise-ai/ad-campaign-runbook), which writes
the main Website visits runbook for a post; a boost runbook is a delta of it.
[`references/provenance.md`](references/provenance.md) has the record of what the source runbook got wrong.

## Install

```bash
git clone https://github.com/timerise-ai/linkedin-boost.git ~/.claude/skills/linkedin-boost
```

For another agent, clone into its skills directory, or symlink the Claude Code copy. Nothing here is
Claude-specific: `SKILL.md` plus markdown references, no script, no file that calls a model.

## Activation

The skill activates when a task matches its description: boosting a Company Page post, sponsoring a post
with the link in the first comment, planning founder reposts and DMs around it, or moving the post's date.
Invoke it explicitly with `/linkedin-boost` in Claude Code:

```
/linkedin-boost content/blog/en/from-brief-to-prototype.md "3000 PLN, October" docs/runbooks/linkedin-ads-prototype-48h.md
```

Without the post path it stops and asks.

## What's inside

| File | Contents |
|---|---|
| `SKILL.md` | Entry point: the required input, architecture, eight critical facts, six hard rules, quick start, reference directory |
| `references/adaptation.md` | What the host provides, the rename table, languages, the non-negotiables |
| `references/inputs.md` | The required post, the optional main runbook, the inputs to ask for, every placeholder |
| `references/strategy.md` | Boost versus Website visits, one test at a time, lifetime versus daily, planning numbers, bidding, decision rules, month-end decision |
| `references/creative.md` | Image, company post, first comment, first 90 minutes, reposts, DMs, the audit |
| `references/campaign-manager.md` | Why not the Boost button, the ten build steps, a second post in the month, gotchas |
| `references/schedule-and-owners.md` | Owner forms, the unassigned-tasks pass, the date cascade, the before-launch checklist |
| `references/runbook-template.md` | The document to produce, with fixed section numbers |
| `references/provenance.md` | What was fixed, kept and added |
| `evals/prompts.md` | What an operator types after installing |
| `README.md`, `CHANGELOG.md`, `CLAUDE.md`, `LICENSE` | This file, release history, editing conventions, MIT |

## The six non-negotiables

1. **Never run without the post file.** Which content gets the budget is the user's decision.
2. **Never write a claim the post does not make.** The company post, comment, reposts and DMs all trace to
   it.
3. **Never invent a budget, a benchmark or a fact about a person.** Planning numbers are assumptions; repost
   texts need their author's yes.
4. **Never leave a task without a named person.** A team is not an owner; a task nobody takes is deleted.
5. **Never change the ad account without an explicit yes for that action.**
6. **Never leave a placeholder or a stale date.** One moved date runs the cascade.

## Requirements

A blog post of more than 300 words as a markdown file, live at a stable URL. A LinkedIn Company Page and an
ad account. The `ad-campaign-runbook` skill is recommended: its main runbook supplies the audience, the
conversions and the honesty constraints, and its preflight checks the post.

## Not this

| Not this | Use instead |
|---|---|
| A Website visits campaign with link ads | `ad-campaign-runbook` |
| A post on a personal profile | The author's own posting or voice skill |
| Thought Leader Ads, Meta, Google or X | Not covered |
| Creating campaigns through an ads API | This writes a document a person executes |

## Contributing

Pure markdown, no build step. If you change a factual claim about LinkedIn, say how you verified it. Adding,
removing or renaming a reference means updating the quick start and the reference directory in `SKILL.md`
and the file table above. Read `references/provenance.md` before simplifying anything. Commits follow
Conventional Commits; `CLAUDE.md` carries the editing conventions.

## Author

Built and maintained by [Timerise](https://timerise.ai).

## License

MIT. See [LICENSE](LICENSE).
