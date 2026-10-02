---
name: reply-for-the-team
description: Write and send a reply, a new email or a forward from a Trupeo shared mailbox. Use when the user asks to answer someone, confirm, decline, chase, forward a message, or write to a member, a parent, a customer, a supplier or a town hall on behalf of their association, school or small business.
---

A reply leaves in the organisation's name, from the shared address, and it is read and archived. It has to be right the first time.

**Before writing**

1. Find the conversation with `search_conversations` (subject words, `from:`, a date) and read all of it with `get_conversation`, notes included. A colleague's note often holds the answer, or says someone already replied by phone.
2. If the person matters (a member, a parent, a customer), `search_contacts` then `get_contact` gives the name, role and the team's note about them.
3. Never invent a fact. A date, a price, an amount, an opening hour, a place, a rule or a decision that neither the user nor the thread gives is a question for the user, not a guess.

**How to write**

- The correspondent's language. In French, `vous`, unless the thread already uses `tu`. Address an organisation's list with "Bonjour à toutes et à tous".
- Courteous even when the message received was not. Factual. Brief: three to six sentences, the answer first, then one clear next step.
- Human, not corporate: no "I hope this email finds you well", no marketing words, no emoji unless the correspondent uses them.
- No signature: Trupeo adds the person's and the mailbox's.
- Sensitive matters are not settled by email. A child's behaviour, health or difficulties, a conflict between people, a serious complaint: the email offers a call or a meeting with two or three slots, and says nothing about the substance.
- Associations: never promise a tax receipt or the 66 % tax reduction on a membership fee unless the user confirms the association issues them. A fee that pays for an activity (sport, music, leisure) usually gives no right to one.

**Sending**

1. Show the draft and wait for an explicit go. Say who will receive it.
2. Then:
   - reply: `reply_to_conversation`, with `markDone: true` only if the reply closes the request;
   - new email: `send_email` (a `scopeId` only if Trupeo asks for one);
   - forward: `forward_conversation`, with a short line above; the original's attachments go with it.
   To attach a document already in the mailbox (a form, a price list, a receipt), find it with `get_conversation` and pass its id in `attachmentIds`.
3. Confirm in one line: sent, to whom, and the conversation's new status.

The `text` you send is plain text: blank lines separate paragraphs, single line breaks are kept.
