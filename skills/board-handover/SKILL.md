---
name: board-handover
description: Hand a Trupeo shared mailbox over when people change, or review who has access. Use when an association's board changes, a secretary, treasurer or volunteer leaves or arrives, a school staff member changes, or the user asks who has access, who is handling what, or wants a weekly or monthly review of the mailbox.
---

The mailbox's memory must stay with the organisation, not with the person who leaves. This skill prepares the handover; the user decides each step.

**A handover**

1. `list_members`: who has access, with which role. Ask who leaves, who arrives, and the handover date.
2. For the person who leaves, list what they still hold: `search_conversations` with `query: "assignee:<their email>"` and `view: "open"`.
3. Propose, conversation by conversation:
   - close what is finished (`set_conversation_status` "done");
   - reassign what is open to the person who takes over (`assign_conversation`);
   - add a handover note where the context is not in the emails: what was promised, what was decided by phone or in a meeting, what is waiting on whom (`add_note`).
4. The newcomer: `invite_member` (it emails them an invitation; a third person can move the mailbox to the team price). If they should only see part of the mailbox, offer scopes (`list_scopes`, `set_member_scopes`).
5. After the handover date, and only when the user confirms: `remove_member` for the person who left. Their open conversations go back to the unassigned queue, so reassign first.
6. Check the shared signature still names the right people: `set_mailbox_signature` if the owner wants it changed. Owner-only steps (invite, remove, role, scopes, shared signature) are refused for a member; say so plainly.

**A weekly or monthly review** (thirty minutes for a volunteer secretary)

1. `get_counts`, then what has waited more than a week: `search_conversations` with `view: "open"` and `before:` a week ago.
2. Conversations without an owner: suggest one each.
3. Decisions taken by email ("on valide la salle du 12"): offer to record them as a note on the conversation so the next board finds them.
4. Once a month: `list_members` and `list_invitations`. Is anyone who left the organisation still there? Is an invitation still pending for weeks?

Answer in the user's language, as a short checklist.
