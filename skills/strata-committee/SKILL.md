---
name: strata-committee
description: Run the shared mailbox of a self-managed strata committee (owners corporation), an HOA board or a French conseil syndical in Trupeo. Use when the user mentions owners' questions, a leak or a repair, a contractor or a quote, the managing agent (syndic), levies or assessments (charges), a vote or a decision taken by email, the minutes, or a change of committee members.
---

A building's mailbox is run by volunteer owners for all the owners. What matters is that every request has an owner, every decision leaves a trace, and nothing is promised that the committee has not decided.

**Owners' questions**

1. `search_conversations` with `view: "unassigned"`. Repairs and leaks first: a water leak or a safety issue is today's.
2. Read the whole thread with `get_conversation`, notes included, and the owner's card (`search_contacts`, `get_contact`).
3. The usual cases:
   - **A repair or a leak**: acknowledge it, say who handles it (the committee, the managing agent, the owner's own insurer) and when, only as the user confirms.
   - **Levies, assessments, charges**: never state an amount, a due date or a penalty the user or the records do not give. Questions on an owner's account usually go to whoever keeps the books; forward them if the user asks (`forward_conversation`).
   - **What the rules allow** (works, pets, rentals, parking): answer from the by-laws or the règlement de copropriété only when the user quotes them; otherwise say the committee will check.
4. Draft, show and send as in `reply-for-the-team`. Neutral and courteous: neighbours read each other's emails.

**Contractors, quotes, managing agent**

- File quotes and invoices under one label per job ("Roof 2026"): `create_label`, `set_conversation_label`.
- Compare quotes for the user, side by side; the choice belongs to the committee or the general meeting, as your statutes say.
- A request to the managing agent: one clear question, a date for the answer, then a follow-up a week later if none comes.

**Decisions taken by email**

When members agree by email ("ok for the second quote"), offer a note on the conversation (`add_note`) with what was decided, by whom and on which date, so it can be recorded in the minutes. Whether an email decision is valid depends on your by-laws or statutes; say so, never decide it.

**Committee turnover**

Use `board-handover` when members change after a general meeting.

Answer in the user's language, short, no quoted email bodies.
