---
name: job-closeout
description: Close an East Renewables job properly. Handover pack, notifications, final invoice, review request. Use for "close this job", "handover pack", "job finished".
---

# Job close-out

Given a job number, read `get_job_details` and `get_job_diary`, then tick through:

1. **Commissioning record.** Test results, EIC, photos of array, inverter, battery,
   isolators, labelling, meter and consumer unit, serial numbers.
2. **Notifications.** MCS certificate, DNO, building control. Dates and references in
   the diary. See `compliance` for deadlines.
3. **Handover pack.** System summary and schematic, datasheets, manufacturer warranties
   and registrations, workmanship warranty and insurance policy, certificates,
   monitoring login, how to shut down safely, export tariff guidance, who to call.
   List what is in Drive and what is missing.
4. **Money.** Final invoice raised with the job number as reference, deposit and stage
   payments allocated, balance due date. For contract labour: on the next batch invoice.
5. **Customer.** Draft the handover email with the pack, then a review request a week
   later.
6. **Close.** Propose: move to 11 Handover Sent - Closed, then Completed once paid.
   Add a diary note summarising the above.

A job is closed only when it is paid, notified and handed over. If any of the three is
missing, say which and leave it open.
