# East Renewables Business OS

This repo holds the operating system for East Renewables Ltd: a business profile, the rules
Claude works under, and a set of routines (skills) that run the working week from the live
systems. Start with `business-os/README.md` for the rhythm and the list of routines.

## The business

- East Renewables Ltd, UK limited company, VAT registered, base currency GBP, Europe/London.
- Electrical contractor specialising in solar PV and battery storage. MCS certified, NAPIT registered.
- Two directors/staff in ServiceM8, plus a generic "Contractor" staff record for subbed labour.
- Three kinds of work, which behave differently for quoting, invoicing and tax:
  1. **Own installs** (domestic and commercial solar, battery, EV, consumer units, EICRs).
     Full pipeline: enquiry, design, survey, DNO, contract and deposit, install, notifications, handover.
  2. **Contract labour** for other solar installers ("Solar Contract Install"). Short jobs,
     invoiced in batches, paid net of CIS deduction. Books to "CIS Labour Income" in Xero.
  3. **Projects** (principal-contractor style jobs such as re-roofs with solar). Formal
     contract, pre-start meetings, building control, CDM paperwork, staged valuations.

## Systems of record

| What | Where | Notes |
|---|---|---|
| Jobs, quotes, job diary, scheduling, customer messages | ServiceM8 | Job numbers look like `25-123E`. The job number is the reference on the Xero invoice. |
| Invoices, bills, bank, VAT, CIS, P&L | Xero | Single organisation. Always fetch the organisation id with `get_connected_organisations`. |
| Email | Gmail | Shared inbox for enquiries, suppliers, schemes and accounts. |
| Diary | Google Calendar ("East Renewables Ltd Jobs") | Meetings, holidays, site days. ServiceM8 holds job bookings. |
| Documents | Google Drive | Proposals, RAMS, certificates, handover packs. |

Never copy data between systems from memory. Read it live each time.

## ServiceM8 conventions

Job templates: Consumer Unit Change, Solar Quote, Solar Contracting, MCS Solar & Battery,
Solar Commercial EICR.

Install pipeline queues, in order. A job should sit in exactly one of these until closed:

1. 01 Enquiry Received
2. 02 Design & Proposal
3. 03 Survey Booked
4. 04 Surveyed - Design Locked
5. 05 DNO Submitted
6. 06 DNO Approved
7. 07 Contract & Deposit Protected
8. 08 Scheduled
9. 09 Installed - Commissioning
10. 10 Notifications Due
11. 11 Handover Sent - Closed

Other queues: Jobs to Quote, Pending Quotes, Parts on Order, Workshop, Aftercare / Complaint.

Look queue and staff ids up with `list_queues` and `list_staff`; do not hard-code them.

## Rules Claude works under

1. **Draft, then ask.** Nothing leaves the business without approval: no email, SMS, quote,
   invoice, status change, queue move, booking or calendar change. Show the draft and what
   it will do, then wait for a yes. Reading is always fine.
2. **Money is read-only.** Xero is for reporting. Never state that a bill has been paid or
   an invoice issued unless Xero shows it.
3. **Say where a number came from** (system and date). If two systems disagree, show both.
4. **CIS.** Contract-labour invoices are paid net of a CIS deduction. A shortfall equal to
   the deduction is not a debt. Check the contractor's CIS statement before chasing.
5. **Regulatory deadlines are firm.** See the `compliance` skill. If a date is at risk, say so first.
6. **Tax and legal questions go to the accountant or the scheme.** Give the facts and the
   question to ask, not a ruling.
7. **No customer data in this repo.** No names, addresses, amounts, email addresses or
   job details in any committed file. This repo holds process only.
8. Plain British English, short, no jargon the customer would not use.
