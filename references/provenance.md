# Provenance

The ledger for this skill: what the audit changed and how the procedure holds it, what was kept on purpose,
and what was designed here. Read it before simplifying anything.

The earlier implementation was one boost runbook for a B2B marketing site, a delta of a Website visits
runbook written with `ad-campaign-runbook`. It was written on 2026-10-06 and revised on 2026-10-07 while its
tasks were assigned and its publish date moved by one day. **It had not launched when this skill was
written, so every performance number here is a planning assumption and is labelled as one.**

Four entries below are fixed defects, five are deliberate keeps, three are additions.

## Fixed

### 1. Owners that were teams

The header named "Marketing" and "Sales", and no task had a person. Before launch the user had to ask for the
unassigned tasks and go through them one by one: most got a person, a few were deleted as nobody's work.
**Held by:** the hard rule, the owner forms and the unassigned-tasks pass in
[schedule-and-owners.md](schedule-and-owners.md).

### 2. A moved date that needed a manual cascade

Moving the publish by one day moved the boost start, the build's start date, a founder's repost and the DM
start, and changed the run days, the daily pace and the weekly pace quoted in the decision rules. Each was a
separate edit, and a missed one would have left the boost starting before the post. **Held by:** the date
cascade table and the grep for old dates in [schedule-and-owners.md](schedule-and-owners.md).

### 3. Checklist items that repeated build steps

The before-launch list re-checked audience expansion and the Audience Network, which the build unticks, and
asked to notify Sales when the people receiving conversions were already named. Both were deleted by the
user. **Held by:** the checklist rule: only checks that are not build steps, no notification item when the
receivers are named.

### 4. The Boost button

Boosting from the post hides the settings and leaves expansion and the Audience Network on. **Held by:** the
build starts in Campaign Manager from Browse existing content, in [campaign-manager.md](campaign-manager.md).

## Kept deliberately

- **The link stays in the comment, although the boost then cannot optimise for site visits.** A link in the
  body costs organic reach before the boost starts, and the test is whether the audience engages at all.
- **`utm_medium=paid` on a comment that organic viewers also see.** The boost delivers most impressions, and
  analytics cannot split one link. The runbook says how to read it.
- **Lifetime budget on the boost, daily on Website visits.** A fixed month wants a ceiling; an open campaign
  wants even spend between reviews. Both are documented with the rule.
- **No changes in the first week.** At this spend, an earlier change reacts to noise.
- **Section numbers in the template are fixed**, as in the main runbook, because the next boost is a copy.

## Added

Designed in this skill and never run in the earlier implementation.

- The placeholders and the generic roles. The earlier implementation used the host's own people, account
  and currency.
- Section 9, shared setup without a main runbook. The earlier implementation always had one.
- `BOOST-02` added to the same campaign as a second ad. The earlier implementation said only "boost it as
  `BOOST-02` with the remaining budget"; the same-campaign mechanics are an assumption to confirm in the UI.

## Not covered

Thought Leader Ads (sponsoring a person's post), Document and video posts as the boosted format, and every
channel other than LinkedIn.
