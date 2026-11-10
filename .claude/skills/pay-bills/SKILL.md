---
name: pay-bills
description: Supplier bills for East Renewables by due date, checked against statements, with a payment run that fits the bank balance. Use for "what do I owe", "bills", "who needs paying".
---

# Pay bills

1. Xero `get_aged_payables` (all pages) and `get_cash_position`. Note when Xero last
   refreshed the bank feed.
2. Gmail: supplier statements and invoices from the last 30 days (wholesalers,
   subscriptions, professional fees). List any bill in the inbox that is not in Xero,
   and any proforma or renewal that needs a keep-or-cancel decision.
3. Check statement totals against Xero per supplier. Old small bills on an otherwise
   paid account are usually a missed allocation: flag them for reconciliation rather
   than payment.
4. **Payment run.** Order by: anything that stops work (account on stop, building
   control, insurance, scheme fees), then oldest overdue, then due within 7 days.
   Show the bank balance before and after, and what is expected in this week.
   If cash will not cover it, say so plainly and propose what to hold and who to call.
5. Payments are made by the user in the bank. Afterwards, check the unreconciled queue
   (`get_bank_account_transactions`).
