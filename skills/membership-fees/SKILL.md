---
name: membership-fees
description: Handle an association's membership fees by email in Trupeo. Use when the user mentions cotisation, adhésion, renewal, a fee reminder or chase, "j'ai déjà payé", a family who cannot pay, a payment link, or a receipt, for a club, a scout group, a parents' association or any non-profit.
---

A membership fee is chased the way you remind a friend, not a customer: warm, short, with the way to pay in the same email.

**Answering a member**

1. Read the conversation (`get_conversation`) and the member's contact card (`search_contacts`, `get_contact`): the treasurer's note may already say they paid.
2. The usual cases:
   - **"How do I pay?"**: give the payment ways the user confirms (link, transfer details, cheque, on site) and the deadline. Ask the user if you do not know them.
   - **"I have already paid"**: thank them, say the treasurer will check, and ask for the date and the way they paid. Never contradict them in the email. Add a note for the treasurer (`add_note`).
   - **A family that cannot pay right now**: answer kindly, without asking for justification. Offer what the user says the association allows (instalments, a reduced fee, a later date); if you do not know, ask the user first.
   - **A receipt**: a payment receipt is always possible. A tax receipt (reçu fiscal, 66 %) only if the user confirms the association issues them; a fee that buys an activity usually gives no right to one.
3. Draft, show, send as in `reply-for-the-team`.

**A fee campaign**

1. Find who wrote about fees: `search_conversations` with `view: "all"` and `cotisation OR adhésion OR renouvellement`, and `after:` the start of the season.
2. Offer to file them under one label (`list_labels`, then `create_label` "Cotisations" if needed, then `set_conversation_label`), so the treasurer sees them in one place.
3. List what is still open, oldest first, with who is handling each one. Suggest the next chase for each, in this order: a first reminder ("sauf erreur de notre part"), a second with a date and a solution, a last notice before membership ends. Never send a reminder to someone who wrote that they paid.
4. Reminders to many members at once are not sent from here one by one without the user's go for each: show the list and the text first.

Answer in the user's language. In French, `vous`.
