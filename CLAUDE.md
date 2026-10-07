# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

An [Agent Skill](https://agentskills.io) package: markdown only, with no script, no `package.json` and
nothing that is part of an application. It teaches an agent to write the runbook for boosting one LinkedIn
Company Page post that promotes a blog post. It is the sibling of `ad-campaign-runbook`, whose main runbook a
boost runbook is a delta of; the two never run in the same month on one campaign group.

Keep the two straight: the commands, checklists and Campaign Manager steps in `references/` describe the
runbook the agent writes, the host app it is written for and the ad account a person will act in, not this
repository. Nothing executes here.

The skill was written by the engineer who has shipped this work; the earlier implementation it was audited
against was a boost runbook for a B2B marketing site, written as a delta of a Website visits runbook.
`references/provenance.md` is the ledger of that audit: four fixed defects with how the procedure holds each
one, five deliberate keeps with the reason each is safe, and four additions designed here that have never
been run. That file is the rationale layer: read it before "simplifying" anything.

## Structure

- `SKILL.md`: entry point, loaded whole on every activation, so it stays between 130 and 160 lines, the
  closing index line aside. The frontmatter is `name` and `description`, and the description is the trigger
  surface. The body carries the required-input contract, the architecture diagram, eight **critical facts**,
  six **hard rules**, the quick-start order, the **reference directory table**, and a closing line linking
  the skills index.
- `README.md`: the human-facing front door, in the section order of the skill standard: install, activation,
  the file table, the six non-negotiables, requirements, the *Not this* table, contributing.
- `references/*.md`: one topic per file, loaded on demand. `adaptation.md` (the seam with the host) and
  `inputs.md` (the required argument and every placeholder) are the entry points; `strategy.md`,
  `creative.md`, `campaign-manager.md` and `schedule-and-owners.md` are the working order;
  `runbook-template.md` is the document to produce; `provenance.md` is the audit ledger.
- `evals/`: `prompts.md` holds what an operator types after installing, in their words, each carrying what it
  works on; the first prompt is the agent eval run on every release. Every other file there is one eval run:
  measured frontmatter that is never edited, then the notes of the person who ran it, scored against the
  hard rules. Add a prompt rather than rewording one that has results. The procedure is section 10 of the
  index's STANDARD.md.
- `.github/workflows/agent-eval.yml`: the caller of the index's reusable eval workflow, run on every
  published release and on a maintainer's dispatch. It is copied verbatim, the same in every skill; do not
  edit it, and never add a trigger on `push` or `pull_request`.

## Editing conventions

- **Code blocks are a command or runbook text.** A command opens with the command itself; a text block is
  pasted into the runbook or onto LinkedIn as is, so it carries no destination comment, and the sentence
  before it names where it goes.
- **Identifiers are shared across files**: `BOOST-01` upward, `utm_content=boost-01`,
  `utm_content=repost-<name>`, `utm_medium=paid` on the company comment and `organic` on reposts,
  `utm_campaign=post-<short slug>`, the campaign name `POST | <short slug> | BOOST | <yyyy-mm>`, and every
  `{{PLACEHOLDER}}`. Rename in all files or none.
- **The placeholder table in `inputs.md` and the template are one contract.** Every `{{NAME}}` in
  `runbook-template.md` has a row in `inputs.md`, and the reverse.
- **Section numbers in `runbook-template.md` are fixed.** Add at the end, never renumber.
- **Keep the three tables in sync** with `references/`: the reference directory and the quick start in
  `SKILL.md`, the file table in `README.md`. Links are relative: `[x.md](references/x.md)` from `SKILL.md`,
  `[x.md](x.md)` between references.
- **Do not remove the odd-looking parts**: the link in the comment, `paid` on a comment organic viewers also
  see, lifetime budget, no changes in week 1, the checklist without build steps. Each is a ledger entry.
- **The numbers that remain are load-bearing**: 140 visible characters, 24 hours before the boost, 20 DMs a
  day per person, 12-word comments, the decision rule thresholds, 0 to 3 conversions, and the ledger's own
  entry counts. Planning numbers stay labelled as assumptions. Figures describing the earlier
  implementation's own content or account do not appear anywhere.
- **Mark additions as additions** in `provenance.md`.
- **Evals are not skill content.** A new prompt or an eval result is committed as `chore(evals): ...`, never
  causes a version bump and never rides in a release commit.
- **Never present the non-negotiables as optional.** They are hard rules in `SKILL.md`, non-negotiables in
  `README.md`, and restated in `adaptation.md`, in the same order.
- The conversion vocabulary, the outcome, the conversion list, the programme name, the short slug and the
  people are renamed by the host through the table in `adaptation.md`. The UTM parameter values and the ad
  names are the join key with Campaign Manager and analytics and are not renamed.
