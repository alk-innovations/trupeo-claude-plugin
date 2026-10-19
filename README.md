# Trupeo for Claude

[Trupeo](https://www.trupeo.com) is a shared inbox for small teams, associations, schools, works councils and building committees: several people answer the same email address (contact@, info@, secretariat@) without stepping on each other. This plugin lets Claude work in those shared mailboxes with your own Trupeo account and your own rights, nothing more.

## What it adds

- **The Trupeo connector**: read and search conversations and their attachments, reply, forward, assign, mark done, add team notes, file into folders, labels and scopes, trash, spam and read state, the shared address book, contact groups and writing to a whole group at once (in Bcc by default), signatures and, for mailbox owners, members, invitations and scopes.
- **Nine skills** written from how associations, schools, small businesses, works councils and building committees actually work their shared address:
  - `triage-shared-inbox`: what is waiting, sorted into today, within a working day and no answer needed, and who should take what;
  - `reply-for-the-team`: replies that read the whole conversation and the team's notes, never invent a fact, stay brief and courteous, keep sensitive matters for a meeting, write to a contact group in Bcc rather than to a list of addresses, and wait for your go before sending;
  - `membership-fees`: an association's fee questions and reminders, "I have already paid", families who cannot pay, reminders to a group of members in Bcc, and no tax-receipt promise the association cannot keep;
  - `board-handover`: when a board or a volunteer changes, the weekly review of what waits and who has access, and contact groups kept up to date with who is on the board;
  - `school-office-routine`: parents' emails, from the morning's absences to the end-of-day check, routed to the office, the head or the teacher, and a notice to a class's parents sent to its contact group in Bcc;
  - `customer-requests`: quotes, orders, delays and complaints for a small business, with a next step in every answer;
  - `organise-mailbox`: folders, labels or categories depending on the provider, clean-up, scopes so each person sees only what concerns them, and contact groups for the address book;
  - `works-council`: a French CSE's mailbox, from employees' questions on activities, chèques-vacances and reimbursements to suppliers, convocations from management and the handover after an election, with employees' personal data kept out of notes and their addresses never shown to each other;
  - `strata-committee`: a self-managed strata committee, HOA board or conseil syndical, from owners' questions and repairs to contractors' quotes, the managing agent, notices to all the owners sent to a contact group in Bcc, and decisions taken by email noted for the minutes.

## Use it

1. Install the plugin, then connect the Trupeo connector from the plugin's Connectors tab and sign in to your Trupeo account.
2. Ask in your own words, for example:
   - "What is waiting in our shared mailbox?"
   - "Reply to the registration request that Lucas has a place on Saturdays."
   - "Put all the invoices under an Invoices label."
   - "Our treasurer is leaving at the end of the month: prepare the handover."
   - "Who still hasn't answered about this season's membership fee?"
   - "Put the new members in the Members 2026-2027 group, then write to the group in Bcc about Saturday's general meeting."

Claude asks you to confirm before it sends an email, deletes something, invites or removes someone, or changes what a member can see.

## Requirements

A Trupeo account (free 30-day trial, no credit card) with at least one shared mailbox connected: Gmail, Outlook, Microsoft 365 or any IMAP mailbox.

## Data

The plugin contains only instructions (Markdown) and the address of the Trupeo connector, `https://app.trupeo.com/mcp`. It runs no code on your computer and stores nothing. When Claude uses the connector, Trupeo sends it only what it asks for on your behalf, within your own rights: the conversations, contacts, contact groups, members, labels and settings of the mailboxes you belong to. Signing in uses OAuth on Trupeo's own page, and you can remove Claude's access at any time from Settings, Your account, Assistants in Trupeo.

- Privacy policy: https://www.trupeo.com/privacy/
- Help: https://www.trupeo.com/help/connect-an-assistant/
- Support: https://www.trupeo.com/help/

## Contributing

Corrections and ideas are welcome: see [CONTRIBUTING.md](CONTRIBUTING.md). Report security issues privately, as [SECURITY.md](SECURITY.md) explains.

## License

MIT, see [LICENSE](LICENSE).
