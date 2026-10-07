# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

An [Agent Skill](https://agentskills.io) package: markdown only, no script, nothing that is part of an
application. It teaches an agent to write the runbook for boosting one LinkedIn Company Page post that
promotes a blog post. It is the sibling of `ad-campaign-runbook`, whose main runbook a boost runbook is a
delta of; the two never run in the same month on one campaign group.

The commands, checklists and Campaign Manager steps in `references/` describe the runbook the agent writes
and the ad account a person will act in, not this repository.

`references/provenance.md` is the ledger of the source runbook: four fixed defects, five deliberate keeps,
three additions. Read it before "simplifying" anything.

## Structure

- `SKILL.md`: entry point, loaded whole, at most 150 lines. Frontmatter `name` and `description` (the trigger
  surface), the required input, architecture, eight critical facts, six hard rules, quick start, reference
  directory, and a closing line naming the sibling.
- `references/*.md`: one topic per file. `adaptation.md` and `inputs.md` are the entry points; `strategy.md`,
  `creative.md`, `campaign-manager.md` and `schedule-and-owners.md` are the working order;
  `runbook-template.md` is the document; `provenance.md` is the ledger.
- `evals/prompts.md`: what an operator types after installing. Add a prompt rather than rewording one that
  has results.

## Editing conventions

- **Identifiers are shared across files**: `BOOST-01` upward, `utm_content=boost-01`,
  `utm_content=repost-<name>`, `utm_medium=paid` on the company comment and `organic` on reposts,
  `utm_campaign=post-<short slug>`, the campaign name `POST | <short slug> | BOOST | <yyyy-mm>`, and every
  `{{PLACEHOLDER}}`. Rename in all files or none.
- **The placeholder table in `inputs.md` and the template are one contract.** Every `{{NAME}}` in
  `runbook-template.md` has a row in `inputs.md`, and the reverse.
- **Section numbers in `runbook-template.md` are fixed.** Add at the end, never renumber.
- **Keep the three tables in sync**: the reference directory and the quick start in `SKILL.md`, the file
  table in `README.md`.
- **Do not remove the odd-looking parts**: the link in the comment, `paid` on a comment organic viewers also
  see, lifetime budget, no changes in week 1, the checklist without build steps. Each is a ledger entry.
- **The numbers that remain are load-bearing**: 140 visible characters, 24 hours before the boost, 20 DMs a
  day per person, 12-word comments, the decision rule thresholds, 0 to 3 conversions. Planning numbers stay
  labelled as assumptions.
- **Mark additions as additions** in `provenance.md`.
- **Never present the non-negotiables as optional.** They are hard rules in `SKILL.md`, non-negotiables in
  `README.md`, and restated in `adaptation.md`.
