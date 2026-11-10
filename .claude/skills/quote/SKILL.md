---
name: quote
description: Build or follow up a quote for East Renewables. Scope, line items, margin check, cover email, and chasing quotes that have gone quiet. Use for "quote this", "price this job", "follow up quotes".
---

# Quote

## Build

1. Read the job (`get_job_details`, `get_job_diary`) and any design or survey notes.
2. Write the scope in the customer's words: what is installed, where, what is included
   (scaffold, DNO application, MCS certificate, building control notification, bird
   protection, monitoring setup, handover) and what is excluded.
3. Line items: equipment (panels, inverter, battery, mounting, isolators, cable and
   containment), labour days, scaffold, certification and admin, travel. For materials
   use current supplier prices from recent bills in Xero (`get_bills` with line items)
   or ask.
4. **Margin check.** Show cost, price, gross margin in pounds and percent. Compare with
   the year-to-date gross margin from Xero. Flag anything below it.
5. **VAT.** State the VAT treatment assumed and ask for confirmation. Do not decide
   zero-rating or domestic reverse charge yourself; if unsure, write the question for
   the accountant.
6. **Terms.** Deposit and stage payments, validity (30 days), lead time, warranty,
   deposit protection for domestic customers.
7. Draft the cover email. The quote itself is entered and sent from ServiceM8 by the
   user. On approval, move the job to Pending Quotes (or 02 Design & Proposal) and add
   a diary note with the price and date sent.

## Follow up

`get_jobs_in_filter` with `QUOTES:` and the Pending Quotes queue. For each quote sent:

- 3 working days, no response: friendly check-in.
- 10 days: offer a call, answer the usual objections.
- 30 days: last message, then propose marking Unsuccessful with a reason.

Draft each message. Report the win rate when asked: quotes sent against jobs won.
