---
prompts:
  - prompt: |
      Save the post below as content/blog/en/stop-confirming-bookings-by-phone.md, then write the runbook for boosting our Company Page post about it. 1,500 EUR for November, we post on Tuesday 2026-11-03 at 7:30. Ana publishes and builds the boost, Ben checks tracking, and our two founders repost in Polish. There is no main ads runbook yet.

      ---
      title: Stop confirming bookings by phone
      date: 2026-09-01
      author: Head of Product
      ---

      Most small clinics and studios still confirm every appointment by phone the day before. A receptionist works down a list, leaves voicemails, and marks the ones who answered. It feels like care. It is mostly lost time. [Try automatic confirmations free for 14 days](/signup).

      ## Where the first hour goes

      We looked at how front desks using our booking software spend the first hour of the day. The confirmation calls were the largest single block, larger than check-ins and larger than rescheduling. The calls also reached the fewest people: a client who books online rarely answers an unknown number at work.

      ## What we changed

      So we replaced the call with a message the client can answer in one tap. Two days before the visit they get a text and an email with three buttons: keep, move, or cancel. Keep does nothing. Move opens the calendar at the same service and the same staff member. Cancel frees the slot at once, and the waiting list gets the offer within a minute.

      Three things changed for the clinics that switched. The front desk got its first hour back. Cancellations arrived two days out instead of at the door, which is early enough to fill the slot. And the clients who never answered calls started answering, because a button is easier than a conversation.

      ## What it does not fix

      A client who has decided not to come will not tell you, whatever the channel. A deposit or a cancellation fee is the tool for that, and we do not think a reminder should pretend otherwise. If most of your no-shows come from new clients booking free first visits, start there.

      Setting it up takes about ten minutes. You choose when the message goes out, write the text in your own words, and decide whether a cancellation opens the slot to the waiting list or to everyone. Nothing changes for clients who prefer to call: the phone still works, it just stops being the only way.

      If your desk still starts the day with a call list, try it for two weeks and compare the first hours. [Start the free trial](/signup).
    expect: |
      Boost starts 2026-11-04; lifetime budget; run days and pace computed from it; section 9 written because
      there is no main runbook; every task has Ana or Ben or is asked about (weekly check and results have no
      owner given, so the agent asks or leaves them as open inputs, never "Marketing"); repost texts drafted
      in Polish and marked as needing each founder's yes; no claim beyond the post (no "guaranteed", no
      invented numbers).
    stack: No data store
  - prompt: |
      Write a boost runbook for our latest blog post, 1,000 EUR this month.
    expect: |
      No post path given: the agent stops and asks for the file, and does not pick the latest post.
    stack: No data store
  - prompt: |
      Save the runbook below as docs/runbooks/linkedin-boost-phone-confirmations.md. We moved the Company Page post from Wednesday to Thursday, same time. Update the runbook.

      # Runbook: LinkedIn Boost Post for "Stop confirming bookings by phone"

      **Type:** Short campaign runbook (one boosted Company Page post)
      **Budget:** 1,500 EUR for November 2026, lifetime, ends 2026-11-30
      **Source content:** `content/blog/en/stop-confirming-bookings-by-phone.md`
      **Owner:** Ana (post, comment, first 90 minutes, build); Ben (tracking, weekly check, results)
      **Status:** Draft, not launched
      **Last updated:** 2026-10-20

      ## 2. Budget and schedule

      | Date | What | Who |
      | :-- | :-- | :-- |
      | Mon 2026-11-02 | Image, post text and comment ready; blog post review | Ana |
      | Wed 2026-11-04, 7:30 | Company Page post, first comment with the link | Ana |
      | Thu 2026-11-05 | Boost starts (build step 6 start date); first founder repost; DMs start | Ana, Marek |
      | Mon 2026-11-09 | Second founder repost | Ola |
      | Mon 2026-11-16, 11-23, 11-30 | Weekly check | Ben |
      | Mon 2026-11-30 | Boost ends 23:59; results row | Ben |

      26 days at 1,500 EUR is about **58 EUR a day**, about 404 EUR a week. Use a **lifetime** budget.

      ## 4. Setting up the boost

      **Owner: Ana.** Step 6: lifetime 1,500 EUR from 2026-11-05 to 2026-11-30 23:59.

      ## 6. Weekly check (Mondays, 15 minutes)

      **Owner: Ben.** Spend under 60% of pace (about 404 EUR a week): raise the bid to the middle of the suggested range.
    expect: |
      The date cascade runs: publish Thu 2026-11-05, boost start and build step 6 on 2026-11-06, the first
      repost and the DM start move with it, the Monday rows stay; run days 25, about 60 EUR a day and 420 a
      week in sections 2 and 6; Last updated is today; no 11-04 or old pace left.
    stack: No data store
---

# Prompts

What an operator types after installing this skill, in their own words. An agent eval installs the skill
into an empty Next.js app, gives the agent one of these prompts and no further help, then type-checks and
builds the result; the first prompt runs on every release. This skill writes a runbook rather than code, so
each prompt carries what it works on, and the checks only confirm the agent left the app intact: what a run
shows is in its notes, scored against the hard rules, with `expect` saying what a faithful run does. The
first prompt is a post that should get a boost runbook, the second names no post and scores whether the
agent stops and asks, and the third carries an existing runbook whose publish date moves, and scores the
date cascade. The results are the other files in this folder. Section 10 of
[STANDARD.md](https://github.com/timerise-ai/skills/blob/main/STANDARD.md) says how a run is made. The
prompts and the newest runs are on [the skill's page](https://timerise.ai/skills/linkedin-boost) on
timerise.ai.
