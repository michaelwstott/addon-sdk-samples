---
name: new-enquiry
description: Turn a new lead (email, call note, web form, referral from another installer) into a ServiceM8 job with a first reply drafted. Use for "new enquiry", "new lead", "someone wants a quote".
---

# New enquiry

1. **Capture.** From the email or the notes given, pull out: name, phone, email, site
   address, what they want, roof type and orientation if known, existing system, annual
   usage, budget or timescale, how they found us. List what is missing.
2. **Check for duplicates.** ServiceM8 `search` on name and address.
3. **Classify.** Own install, contract labour for another installer, or project. Pick
   the template: Solar Quote, MCS Solar & Battery, Solar Contracting, Consumer Unit
   Change, Solar Commercial EICR.
4. **Propose the job.** Show the job description to be created and the queue it will go
   in (own installs: 01 Enquiry Received; contract labour: no pipeline queue, book the date).
   On approval: `create_job`, `send_job_to_queue`, `add_job_note` with the source and
   the missing information.
5. **Draft the first reply.** Thank them, confirm what we understood, ask only for what
   is missing (photos of roof, consumer unit and meter, a recent bill), and offer two
   survey or call slots from `get_availability`. Use a ServiceM8 email template if one
   fits (`list_email_templates`).
6. **Set the follow-up.** If no reply in 3 working days, chase once; after 10, mark for
   a final message.

Target: every enquiry answered the same working day.
