# Campaign Manager: building the boost

Click-by-click steps to paste into the runbook, with the host's names filled in. Menu labels change. Write
each as the **English label** and add the local label when the account's UI is in another language. Use a
browser profile without an ad blocker: with one, Campaign Manager shows a warning banner and blank pages.

Account, conversions, audiences and the campaign group are set up once, by the main runbook. If they do not
exist yet, the `ad-campaign-runbook` skill's build covers them; this file starts at the campaign.

## Why not the Boost button

The **Boost** button on the Company Page post creates the campaign with defaults it does not show: audience
expansion on, LinkedIn Audience Network on, an audience it picks. Both defaults leak budget to people who do
not read the post. **Boost from Campaign Manager**, where every setting below is visible.

## The steps

1. **In Campaign Manager, open the ad account, then the campaign group** for the programme. Check the group
   cap covers the boost budget for the month and that no Website visits campaign for this post is running.
2. **Create, then Campaign**, classic setup. **Decline "Accelerate"** or any AI-assisted setup. Objective
   **Engagement**.
3. Name: `POST | <short slug> | BOOST | <yyyy-mm>`.
4. Audience: load the saved audience template from the main runbook. If it does not exist yet, build it from
   the main runbook's audience section and save it. Attach the exclusions. **Untick "Enable audience
   expansion".**
5. Format **Single image ad**. Placement: **untick LinkedIn Audience Network**.
6. Budget **lifetime**, the month's budget, start the day after the organic publish, end on the last day of
   the run at 23:59.
7. Bidding: optimisation goal **Engagement**, **Maximum delivery** for the first week. Switch to **Manual
   bidding** at the low end of the suggested range only if the CPM runs above the high planning value.
   Note the suggested range in the runbook: it is the first real number against the CPM assumption.
8. Conversion tracking: tick the conversions the main runbook created. Say in the runbook that they report
   **view-through only**, because the ad itself has no link.
9. **Ads, then Browse existing content**, and pick the Company Page post. Name the ad `BOOST-01`, the same
   as the comment link's `utm_content`.
10. Review, then Launch. Creating the campaign accepts the advertising terms, so the account owner clicks it.
    **Do not edit the post** while it is sponsored: an edit sends it back to review.

## A second post in the same month

When the weekly rule calls for a new post, it gets its own first comment with `utm_content=boost-02`, is
added to the **same campaign** as ad `BOOST-02` from Browse existing content, and `BOOST-01` is paused. The
budget stays the lifetime total already set; nothing else changes.

## Gotchas

| Gotcha | Consequence |
| :-- | :-- |
| Boosting from the post's Boost button | Expansion and Audience Network on, settings hidden, demographics unreadable |
| Starting the boost the same minute as the post | No organic comments to carry into paid; the first impressions land on an empty post |
| Editing the sponsored post | It goes back to review and stops delivering until approved |
| A daily budget on a one-month boost | Overspend on good days, and the month's total is no longer the ceiling |
| Ad name and `utm_content` differ | Campaign Manager and analytics cannot be joined in the results row |
| Acting on a signed-in session without a yes | Creating objects accepts terms on the user's behalf. Stop at the review step |

## Build checklist

- [ ] Built from Campaign Manager, not the Boost button
- [ ] Engagement objective, campaign name in the `POST | <short slug> | BOOST | <yyyy-mm>` format
- [ ] Audience template loaded, expansion unticked, Audience Network unticked
- [ ] Lifetime budget, start the day after the organic publish, end set
- [ ] Conversions ticked, noted as view-through only
- [ ] Ad name `BOOST-01` equals the comment link's `utm_content`
