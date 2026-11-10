---
name: chase-debtors
description: Draft payment reminders for overdue East Renewables invoices from Xero, with the tone matched to the customer. Use for "who owes me", "chase invoices", "overdue".
---

# Chase debtors

1. Xero `get_aged_receivables` (page to the end). Group by customer.
2. For each customer, check Gmail for the last exchange about payment and any CIS
   statement covering the invoices. Do not chase a balance that is a CIS deduction.
3. Pick the tone:
   - **Not yet due, or under 7 days late:** no chase. List only.
   - **7 to 30 days:** friendly reminder, list invoice numbers, job references and total.
   - **30 to 60 days:** firm, ask for a payment date.
   - **Over 60 days:** final reminder, refer to the terms, propose a call. Flag to the
     user before drafting anything stronger.
   - **Regular trade clients** who pay in batches: one statement-style email covering
     everything outstanding, not one per invoice.
4. Create Gmail drafts (`create_draft`), addressed to the accounts contact held in Xero.
   Never send. Show the list of drafts with totals.
5. Note who has been chased and when in the ServiceM8 job diary once the user confirms
   the emails went.
