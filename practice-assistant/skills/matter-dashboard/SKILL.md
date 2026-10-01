---
name: matter-dashboard
description: Builds and refreshes the lawyer's practice dashboard, a clean HTML page showing today's actions, upcoming key dates, open matters by status, emails awaiting a reply and unfiled attachments. Use whenever the lawyer asks for "my dashboard", "refresh the dashboard", "show me everything", "what's coming up", "overview of my matters", or when a scheduled dashboard refresh runs.
---

# Matter Dashboard

> **Practice settings** (assistant's name, lawyer's name, firm, state, platform — Microsoft 365 or Google Workspace — document store location, matter number format) live in the Practice Assistant project instructions. Read them first, refer to yourself by the assistant's name, and use the email, calendar and document connectors for the platform named there ("the document store" below means their SharePoint site or Google Drive folder). If they're missing, tell the user to run setup ("set up my practice assistant") and stop.

One page the lawyer can glance at to see the state of the practice.

## Gather
1. The Matter Register in the document store: every matter not marked Closed.
2. Key dates: from the register's Key Dates column, plus dates found in the last 14 days of email and the calendar for the next 30 days.
3. Emails from clients, courts or other practitioners in the last 10 days that have no reply from the lawyer.
4. Email attachments from the last 7 days that aren't yet in the matching matter folder.
5. The most recent morning brief in this project, if there is one, for today's actions.

## Build
A single self-contained HTML file (inline CSS, no external images or scripts beyond a font), readable on phone and desktop, supporting light and dark mode. Sections in this order:

1. **Header**: "[Firm name]: Practice Dashboard" with "Prepared by [assistant's name]" beneath it and "Updated Tue 6 Oct 2026, 7:02am".
2. **Today**: numbered actions, urgent first, each tagged with its matter number.
3. **Key dates, next 30 days**: table (Date, Matter, Event, Source). Highlight anything within 3 business days. Anything computed rather than stated shows a "to verify" badge.
4. **Open matters**: cards or table grouped by Status, each showing matter number, client, type, next action, days since last activity. Flag matters with no activity in 21+ days as "quiet".
5. **Awaiting reply**: sender, matter, subject, days waiting.
6. **Unfiled attachments**: file name, matter, suggested folder.
7. **Footer**: counts (open matters, dates this fortnight, items awaiting reply) and "Figures drawn from email, calendar and the document store; verify deadlines before relying on them."

Style: calm and professional, one accent colour, generous spacing, no decoration. Every matter number is visible so it can be asked about next.

## Publish
- Deliver it as an artifact. If a dashboard artifact already exists in this project or from a previous run, **update that same one** so the link stays the same; don't create a new one each day.
- It stays private to the lawyer. Never share or publish the link to anyone else; it contains client-confidential information.
- If a data source fails (e.g. the document store is unreachable), still build the page, show that section as "Couldn't load: [reason]", and say so in your reply.
