---
name: pipeline
description: Walk every open East Renewables job by pipeline stage, show the next action and flag anything stuck or out of place. Use for "where is everything", "pipeline", "what's stuck", "job board".
---

# Pipeline

1. `list_queues`, then `get_jobs_in_filter` with `QUEUE:*` (summaries), and `list_jobs`
   for status Quote and Work Order.
2. Build one table: job number, stage, days in stage, next action, blocker.
3. **Housekeeping, report every time:**
   - Open jobs that are in no queue.
   - Enquiries held as Work Orders with no accepted quote.
   - Queue dates that have passed.
   - Work Orders that are fully paid, or untouched for 60 days (close or revive).
   - Placeholder jobs (leave, admin) so they are not mistaken for work.

## Next action by stage

| Stage | Done when | Next action |
|---|---|---|
| 01 Enquiry Received | Customer replied with details | Qualify, book survey or desktop design |
| 02 Design & Proposal | Proposal sent | Follow up at 3 and 10 days |
| 03 Survey Booked | Survey done | Roof, electrics, DNO and structural notes into the diary |
| 04 Surveyed - Design Locked | Final design and price agreed | Submit DNO application if required before install |
| 05 DNO Submitted | Reference logged | Chase at the DNO's stated turnaround |
| 06 DNO Approved | Approval on file | Send contract, take deposit |
| 07 Contract & Deposit Protected | Signed, paid, deposit insured | Order materials, book scaffold, schedule |
| 08 Scheduled | Dates confirmed with customer | Materials delivered, RAMS, access |
| 09 Installed - Commissioning | Commissioned, tests recorded | Start notifications the same day |
| 10 Notifications Due | MCS, DNO and building control all lodged | Build handover pack, final invoice |
| 11 Handover Sent - Closed | Pack sent, paid in full | Review request, warranty registered, complete the job |

Propose queue moves as a list and apply them only on approval.
