---
name: customer-requests
description: Handle customer emails for a small business in Trupeo. Use when the user mentions a quote (devis), an order, a delivery, a missing or damaged item, a complaint, a refund, a delay, a follow-up on a quote, or wants to know which customers are waiting for an answer.
---

In a small team every customer knows who answers. What matters is that no request is forgotten and every answer gives a next step.

**Who is waiting**

1. `search_conversations` with `view: "open"`, oldest first. Flag what blocks a sale or a payment (quote requests, order problems, invoices) as today's.
2. Quotes sent but not answered by the customer: `search_conversations` with `query: "devis OR quote"` and `view: "all"`; a conversation whose last message is the team's and is a week old is a follow-up candidate.

**Answering**

- **Quote request**: thank them, restate what they asked for in one line, give the date the quote will be sent, and ask only for what is missing (quantities, address, deadline). Never give a price the user did not give.
- **Quote follow-up**: one short, friendly email asking if they have questions, a week after sending; a second one at most.
- **Missing or damaged item, late delivery**: apologise once, plainly; say what happens next and when; ask for the order number or a photo only if it is not already in the thread.
- **Complaint**: acknowledge the problem in their words, no excuses and no blame, one concrete fix or a call. Show the draft to the user before anything else.
- **Refund**: never promise one the user has not confirmed.
- **Closed for holidays**: say until when, and who to contact if urgent, if the user gives one.
Write as `reply-for-the-team` says: short, human, the answer first.

**Keeping track**

Offer a label per kind of request ("Devis", "Commandes", "Réclamations") with `create_label` and `set_conversation_label`, and a note on a customer's contact card (`update_contact`) when something should be remembered next time, such as a preferred delivery day.

Answer in the user's language. In French, `vous` to customers unless the thread already uses `tu`.
