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
  - prompt: |
      Write a boost runbook for our latest blog post, 1,000 EUR this month.
    expect: |
      No post path given: the agent stops and asks for the file, and does not pick the latest post.
  - prompt: |
      We moved the Company Page post in docs/runbooks/linkedin-boost-<slug>.md from Wednesday to Thursday. Update the runbook.
    expect: |
      The date cascade runs: boost start, build step 6 start date, the first repost if it fell on the
      publish day, DM start, run days, daily and weekly pace, Status and Last updated; old dates grepped.
---

# Prompts

What an operator types after installing the skill, in their words. The first prompt is the agent eval; the
second checks the required argument; the third checks the date cascade on an existing runbook.
