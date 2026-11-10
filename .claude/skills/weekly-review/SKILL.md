---
name: weekly-review
description: Monday planning session for East Renewables. Week ahead, full pipeline, 30-day cash view and the three priorities. Use for "plan my week", "weekly review", "Monday".
---

# Weekly review

1. **Week ahead.** Calendar and ServiceM8 bookings for the next 7 days, plus
   `get_availability` to show free days. List what each site day needs: materials
   ordered, RAMS sent, access agreed, scaffold dates, customer confirmed.
2. **Pipeline.** Run the `pipeline` skill and summarise: count per stage, value where
   known, and jobs that have not moved in 14 days.
3. **Last week.** Jobs completed, invoices raised and paid (Xero `get_invoices` for the
   last 7 days), quotes sent and their outcome.
4. **Cash, next 30 days.** Bank balance, receivables by due date, payables by due date,
   known fixed costs (`get_repeating_bills`, payroll, VAT and CIS dates). Show the
   lowest point and the week it falls in.
5. **Year to date.** `get_profit_and_loss`: income split between own sales and CIS
   labour, gross margin, net profit. One sentence on the trend.
6. **Three priorities.** One that brings cash in, one that moves a job forward, one that
   removes a risk. Each with an owner and a day.

Finish by offering to block time in the calendar for the three priorities (ask first).
