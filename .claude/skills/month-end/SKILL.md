---
name: month-end
description: Month-end routine for East Renewables. CIS statements, VAT pack for the accountant, reconciliation queue and a plain-English P&L. Use for "month end", "VAT return", "close the month", "CIS".
---

# Month end

Run in the first week of the month for the month just ended.

1. **Reconciliation.** `get_bank_account_transactions` for the month. List what is
   still unreconciled, with a suggested account for each.
2. **CIS.** The CIS tax month runs 6th to 5th. In Gmail, find each contractor's Payment
   and Deduction Statement for the period. Table: contractor, gross, deduction, net.
   Check each against the invoices paid in Xero. List contractors who paid but sent no
   statement, and draft a request. Total deductions suffered for the accountant.
3. **Sales and purchases.** `show_invoices_summary` for the month; `get_bills` for the
   month. Flag bills with no attachment and invoices without a job reference.
4. **VAT.** If a VAT quarter has ended, assemble the pack: sales, purchases, anything
   unusual (reverse charge, zero-rated installs, large one-offs), and open questions.
   The accountant files; draft the covering email.
5. **P&L.** `get_profit_and_loss` for the month against the previous month, and year to
   date. In plain English: income by stream, gross margin, the three biggest costs,
   what changed and why.
6. **Balance check.** `get_financial_position`: bank, debtors, creditors, VAT and
   PAYE owed, director loan position.
7. **Payroll and pensions.** Confirm the month's run has posted.

Output one page plus the email draft to the accountant.
