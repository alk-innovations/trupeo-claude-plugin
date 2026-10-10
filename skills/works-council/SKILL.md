---
name: works-council
description: Run a French works council's (CSE, comité social et économique) shared mailbox in Trupeo. Use when elected members answer employees about activités sociales et culturelles, chèques-vacances, ticketing (billetterie), gift vouchers or reimbursements, deal with suppliers, handle a convocation or a document from management, or hand the mailbox over after an election.
---

A CSE mailbox is shared by elected members who also have a job to do. Every answer leaves in the CSE's name, and employees must get the same answer whoever replies.

**Employees' questions**

1. `search_conversations` with `view: "unassigned"`, then read with `get_conversation`, notes included: another member may already have answered by phone or at the office.
2. The usual cases:
   - **Activities, chèques-vacances, vouchers, ticketing**: give the rules, amounts and dates the user confirms. If the CSE has not decided (a new benefit, an exception, a budget), say the question goes to the next meeting; never answer for the CSE.
   - **Reimbursement**: say what is missing (receipt, form) and when it is usually paid, only if the user gives it. Never confirm an amount nobody checked.
   - **A personal situation** (a conflict with a manager, health, a dispute): no substance by email; offer a meeting with an elected member, two or three slots.
3. Draft, show and send as in `reply-for-the-team`. In French when the employee writes in French, `vous` unless the thread already uses `tu`.

**Employees' personal data stays in the mailbox.** Copy nothing about an employee (pay, family, health) into a note, a label or a contact card beyond what the next member needs to act ("waiting for the receipt", not the reason for the request).

**Suppliers, ticketing, management**

- Quotes and invoices from suppliers and ticketing partners: file them under one label (`create_label`, `set_conversation_label`) so the treasurer finds them.
- A convocation or an information document from management: note the meeting date and what must be prepared (`add_note`), and assign it to the secretary (`assign_conversation`). Nothing is answered to management without the user's go.

**After an election** (mandates usually last four years; check your agreement)

Use `board-handover`: `list_members`, reassign what the outgoing members hold, a note on each pending file, `invite_member` for the new members, then `remove_member` once the user confirms. Check the shared signature still names the right people (`set_mailbox_signature`).

Answer in the user's language, short, no quoted email bodies.
