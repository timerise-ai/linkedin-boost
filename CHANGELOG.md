# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.3] - 2026-10-07

Fix release, from scoring the prompt-1 agent eval runs against 0.1.2.

### Changed

- The handover's **Open:** line names each open task and input; a pointer to the runbook is not enough. Codex's
  message said "remaining task owners are listed in the runbook". Quick-start step 10 in `SKILL.md` and
  `references/schedule-and-owners.md`.

## [0.1.2] - 2026-10-07

Fix release, from scoring the prompt-1 agent eval runs against 0.1.1.

### Changed

- The handover is four labelled lines the final message always carries: **Open:**, **Drafts:**,
  **Assumptions:** and **Ad account:**. Codex's short final message left out the founders' yes and the
  planning assumptions. Quick-start step 10 in `SKILL.md` and `references/schedule-and-owners.md` carry it.

## [0.1.1] - 2026-10-07

Fix release, from scoring the prompt-1 agent eval runs against 0.1.0.

### Changed

- A role the user gave nobody is `open` when the agent cannot ask, never a person named for another task, and
  a person the user did not name stays a role: `SKILL.md` (a new paragraph, hard rules 3 and 4),
  `references/inputs.md`, `references/schedule-and-owners.md`, and the README's non-negotiables 3 and 4.
- The runbook header carries a new `**Open:**` line, `{{OPEN_ITEMS}}` in `references/runbook-template.md`
  and `references/inputs.md`.
- `SKILL.md` says the skill uses no credential or environment variable, and that the installed `evals/`
  folder is not an input.
- The boost starts the day after the publish at the publish time, never at 00:00, and the first weekly check
  is the first Monday at least 7 days after the boost start: `SKILL.md`, `references/schedule-and-owners.md`,
  `references/campaign-manager.md`, `references/strategy.md`.
- A tenth quick-start step names what the handover says.
- `references/provenance.md` records the open-owner rule as a fourth addition, found by the evals.

## [0.1.0] - 2026-10-07

Initial release of the `linkedin-boost` skill: the runbook for boosting one
LinkedIn Company Page post that promotes a blog post, written as a delta of the
main runbook from `ad-campaign-runbook`.

### Added

- `SKILL.md` entry point: the required post argument, the architecture, eight
  critical facts, six hard rules, the quick start and the reference directory.
- `references/strategy.md`: boost versus Website visits, one test at a time,
  lifetime versus daily budget, planning numbers, bidding, weekly decision
  rules and the month-end decision.
- `references/creative.md`: image, company post, first comment, first 90
  minutes, founder reposts, network DMs and the audit.
- `references/campaign-manager.md`: why not the Boost button, the ten build
  steps, a second post in the month and the gotchas.
- `references/schedule-and-owners.md`: a named person on every task, the
  unassigned-tasks pass, the date cascade and the before-launch checklist.
- `references/inputs.md`, `references/adaptation.md`,
  `references/runbook-template.md` and `references/provenance.md`.
- `README.md` in the section order of the skill standard, `CLAUDE.md` with the
  editing conventions, and `LICENSE`.
- `evals/prompts.md` with three prompts: a post to boost, a request with no
  post, and a runbook whose publish date moves.
- `.github/workflows/agent-eval.yml`, the caller of the index's eval workflow.
