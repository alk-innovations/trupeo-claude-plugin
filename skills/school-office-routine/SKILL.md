---
name: school-office-routine
description: Run a school's shared mailbox in Trupeo. Use for a school office, a head teacher or a school staff answering parents' emails about absences, registrations, certificates, canteen, timetables, appointments, documents, complaints or incidents.
---

A school mailbox mixes several jobs in one queue. The routine gives every message a destination, a status and a calm answer.

**Morning: urgent first**

1. `search_conversations` with `view: "unassigned"`. Pull out what concerns today or tomorrow: absences, late arrivals, pick-up changes, a child unwell.
2. Absences: confirm receipt briefly. If the reason is missing, ask for it politely, without suspicion. Record nothing about the child beyond what the parent wrote.

**During the day: route the rest**

- The office: certificates (certificat de scolarité), canteen, timetables, supplies, registration files.
- The head: complaints, incidents, repeated absences, anything about a child's situation.
- The teacher: homework and class matters; reply that the message is passed on, and forward it if the user asks (`forward_conversation`).
Suggest an assignee for each (`list_members`, then `assign_conversation` once the user agrees).

**Writing to parents**

- Courteous even when the parent is not; a parent who writes curtly at 10 pm is first a worried parent.
- Factual: dates, names, nothing assumed about a child or a family.
- Brief: three to six sentences. A reply that needs three paragraphs is a meeting.
- A child's behavior, difficulties, health or a conflict between pupils is never discussed by email: offer an appointment with two or three slots.
- Missing document in a registration file: say exactly which one and how to send it.
Draft, show and send as in `reply-for-the-team`.

**Writing to a whole class**

A notice to the parents of a class (an outing, a closure, a document to return) goes to the class's contact group in Bcc, so no family sees the others' addresses: `list_contact_groups` ("Parents CE2"), `get_contact_group` to check it, then, after the user's go on the text and the group, `send_email` with `to: []` and the group in `bccGroupIds`. At the start of the year, offer to create the class groups (`create_contact_group`, `add_to_contact_group`) and to take out the families who left (`remove_from_contact_group`).

**End of day: what was promised**

`search_conversations` with `view: "in-progress"`: what was promised today and is not yet answered. Mark done what is finished (`set_conversation_status`), and leave a note on what waits until tomorrow (`add_note`).

Answer in the user's language. In French, `vous` to parents.
