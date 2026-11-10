---
name: invoice-run
description: Friday billing check for East Renewables. Finds finished work that has not been invoiced and reconciles ServiceM8 against Xero. Use for "what haven't I invoiced", "invoice run", "billing check".
---

# Invoice run

1. **Unbilled work.** ServiceM8 `list_jobs` status Completed with `filter_invoice_sent`
   false, and `get_jobs_in_filter` `AWAITING_PAYMENT` (page through all of it). List
   completed jobs with a value, no invoice sent and nothing paid. For each, look in Xero
   (`get_invoices`, the job number is the invoice reference) before calling it unbilled:
   it may have been invoiced there directly.
2. **This week's work.** Jobs completed in the last 7 days: is there an invoice, and
   does the amount match the job?
3. **Staged jobs.** Projects and installs with deposits or valuations: what stage
   payment is now due under the contract.
4. **ServiceM8 against Xero.** ServiceM8 shows contract-labour jobs as part paid because
   the CIS deduction is never recorded there. Sort "awaiting payment" into:
   - **CIS residual** - paid in Xero, shortfall equals the deduction. Not owed. List them
     as a tidy-up batch.
   - **Really unpaid** - also outstanding in Xero. Hand to `chase-debtors`.
   - **Mismatch** - systems disagree. Show both figures.
5. **Report.** Total unbilled, total really unpaid, and the tidy-up count.

Invoices are raised in ServiceM8 by the user so they sync to Xero. Prepare the list and
the wording; do not mark anything invoiced or paid.
