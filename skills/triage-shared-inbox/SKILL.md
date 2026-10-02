---
name: triage-shared-inbox
description: Triage a Trupeo shared mailbox. Use when the user asks what is waiting, what is urgent, what needs an answer, who should take what, or wants the morning, end-of-day or weekly look at their association's, school's or small team's shared email.
---

Triage reads the mailbox and proposes a plan. It changes nothing until the user agrees, and it marks nothing as read: reading from Claude leaves every conversation new for the team.

1. Call `list_mailboxes`. If the user has several, ask which one, unless they named it or only one fits.
2. Call `get_counts` for the overall picture (unassigned, in progress, assigned to the user, spam), and say it in one line. If `needsReconnect` is true, say so first: nothing new arrives until the owner reconnects the mailbox in Trupeo.
3. List with `search_conversations`: `view: "unassigned"` first, then `view: "assigned-to-me"`, `limit: 50`. Open a conversation with `get_conversation` only when its subject and preview are not enough to judge it.
4. Sort into three levels, the way small teams actually work:
   - **Today**: an absence or a change for today or tomorrow, a payment problem, a complaint, someone waiting on a decision, a request already chased once ("re:", "relance", "toujours pas de réponse"), anything with a date in the next three days.
   - **Within a working day**: membership or registration requests, quotes, documents, appointments, questions with no date.
   - **No answer needed**: newsletters, notifications, receipts, automatic messages. Offer to mark them done (`set_conversation_status`) or move them to the trash (`trash_conversation`).
   One line per conversation: who wrote, what they want, how long it has waited.
5. If the user asks who should take what, call `list_members` and look at who handled similar subjects (`search_conversations` with `view: "all"` and the subject's key words). Suggest an assignee for each conversation, as a suggestion. In a school, the usual split is: the office for absences, certificates, canteen and timetables; the head for complaints, incidents and anything about a child's situation; the teacher for homework.
6. Ask before acting. Then assign (`assign_conversation`), close (`set_conversation_status`, which also archives at Gmail or Outlook), trash, or add a note for whoever takes over (`add_note`). Report what changed in a short list.

Answer in the user's language, short, no quoted email bodies, no ids.
