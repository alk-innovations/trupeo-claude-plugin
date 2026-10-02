---
name: organise-mailbox
description: Organise a Trupeo shared mailbox. Use when the user wants to file, sort, label, tag, move or clean up conversations, create or rename folders and labels, or set up scopes so each volunteer or colleague only sees the mail that concerns them.
---

How a mailbox is organised depends on its provider. Check before proposing anything.

1. Call `list_mailboxes` to get the provider:
   - **Gmail**: labels. Call `list_labels`; its `capabilities` say what is possible (Gmail labels cannot be renamed from Trupeo, but can be created, coloured and deleted). There are no folders.
   - **Outlook / Microsoft 365**: folders (`list_folders`) and categories, which Trupeo shows as labels (`list_labels`).
   - **IMAP**: folders (`list_folders`) and labels (`list_labels`).
2. Propose a plan in a few lines (for example "a label Invoices for EDF, Bouygues and the jersey quote") and wait for the user's go before changing anything.
3. Apply it:
   - labels: `create_label`, then `set_conversation_label` for each conversation;
   - folders: `create_folder`, then `move_conversation_to_folder`. `list_folders` gives `inboxId` to move a conversation back to the inbox;
   - a just-sent email can only be labelled or moved once its copy reaches the provider, usually within a minute.
4. Scopes decide who sees what, and only an owner of the mailbox can change them:
   - `list_scopes`, then `create_scope` and `set_conversation_scope` to file conversations;
   - `set_member_scopes` to limit a member to some scopes. A member who loses sight of a conversation assigned to them is unassigned from it automatically, so say so before doing it.
5. Cleaning up:
   - newsletters and notifications: `set_conversation_status` "done" archives them; `trash_conversation` moves them to the trash (`restore_conversation` brings one back while the provider keeps it);
   - spam: `set_spam` with `spam: true`, or `false` for a real mail caught by the filter (`search_conversations` with `view: "spam"` lists them);
   - read or unread: `set_read`, for the person and at the provider;
   - two unrelated requests in one conversation: `split_message` moves the later mail into its own conversation.
6. Deleting a folder, a label or a scope, trashing, marking as spam, removing a member or changing a role cannot be undone from Claude, or only partly. Name exactly what will go and ask for a clear yes first.
7. Report what changed as a short list. Answer in the user's language.
