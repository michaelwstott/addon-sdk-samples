# Business OS

A set of routines that run East Renewables from the systems already in use: ServiceM8,
Xero, Gmail, Google Calendar and Drive. Nothing is stored here except the process. Every
routine reads live data, tells you what it found, and drafts the next step for approval.

## How to use it

Open a Claude session on this repo and type the routine name, or just ask in plain words.

| When | Routine | What you get |
|---|---|---|
| Every morning | `/daily-brief` | Today's diary, what needs a reply, what is stuck, money due in and out |
| Monday | `/weekly-review` | The week ahead, the whole pipeline, cash for the next 30 days, three priorities |
| New lead arrives | `/new-enquiry` | Job created, first reply drafted, survey slots offered |
| Pricing a job | `/quote` | Scope, line items, margin check, cover email, follow-up dates |
| Twice a week | `/pipeline` | Every open job by stage, with the next action and anything overdue |
| Friday | `/invoice-run` | Finished work not yet invoiced, and ServiceM8 against Xero |
| Friday | `/chase-debtors` | Who owes what, with reminder emails drafted by tone |
| Friday | `/pay-bills` | Supplier bills by due date and a payment run that fits the bank balance |
| First week of the month | `/month-end` | CIS statements, VAT pack for the accountant, P&L in plain English |
| Monthly, and before audits | `/compliance` | MCS, NAPIT, DNO, building control, insurance and calibration dates |
| Job finished | `/job-closeout` | Handover pack checklist, notifications, review request |

## The working week

- **Daily, 10 minutes:** `/daily-brief`. Reply, approve drafts, move on.
- **Monday, 30 minutes:** `/weekly-review`, then `/pipeline`.
- **Friday, 45 minutes:** `/invoice-run`, `/chase-debtors`, `/pay-bills`. Work done in the week is billed in the week.
- **Month start, 1 hour:** `/month-end`, `/compliance`.

## The three rules that keep it clean

1. Every piece of work is a ServiceM8 job, and every install job sits in one pipeline queue.
2. Every invoice carries the ServiceM8 job number as its reference.
3. A job is not closed until it is paid, notified and handed over.

## Changing it

Each routine is a plain text file in `.claude/skills/<name>/SKILL.md`. Edit the words to
change the behaviour. The business profile and standing rules are in `CLAUDE.md`.
