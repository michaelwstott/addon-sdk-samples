---
name: daily-brief
description: Morning briefing for East Renewables. Today's diary, emails that need a reply, jobs needing action, and money due in and out. Use for "morning", "what's on today", "catch me up", "daily brief".
---

# Daily brief

Read live, in parallel, then write one short page. Follow the rules in `CLAUDE.md`.

## Gather

1. **Diary.** Google Calendar events for today and tomorrow. ServiceM8 `list_jobs` with
   `filter_scheduled_on` for today and tomorrow. Note clashes, including holidays that
   overlap bookings.
2. **Jobs needing action.** ServiceM8 `get_jobs_in_filter` with `ACTION_REQUIRED:` and
   `FOR_MY_REVIEW:` (summaries). Flag any with an unanswered customer response.
3. **Inbox.** Gmail `in:inbox newer_than:2d -category:promotions -category:social`. Open
   threads from customers, clients, consultants, schemes, suppliers' accounts teams and
   the accountant with `get_thread` before judging them. Skip newsletters.
4. **Money.** Xero `get_cash_position`, `get_aged_receivables`, `get_aged_payables`.
   Only report what changed or what is due within 7 days.

## Write

Keep it under one screen, in this order:

- **Today** - where to be and when, what to bring.
- **Reply today** - each email in one line: who, what they want, suggested answer.
- **Stuck** - jobs waiting on us, oldest first.
- **Money** - bank balance (with the date Xero last refreshed), due in this week, due out this week, anything overdue.
- **Deadlines within 14 days** - scheme, DNO, building control, contract signing, renewals.
- **One thing** - the single most important action today.

Then offer to draft the replies. Do not send anything.
