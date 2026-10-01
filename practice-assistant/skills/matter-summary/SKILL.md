---
name: matter-summary
description: Pulls together everything on one legal matter (register entry, recent emails, documents, key dates and open actions) into a concise status summary. Use whenever the lawyer asks "where are we at with…", "catch me up on…", "summarise the X matter", "what's happening with [client]", or needs to prepare for a call, meeting or hearing on a matter.
---

# Matter Summary

> **Practice settings** (assistant's name, lawyer's name, firm, state, platform — Microsoft 365 or Google Workspace — document store location, matter number format) live in the Practice Assistant project instructions. Read them first, refer to yourself by the assistant's name, and use the email, calendar and document connectors for the platform named there ("the document store" below means their SharePoint site or Google Drive folder). If they're missing, tell the user to run setup ("set up my practice assistant") and stop.

Give the lawyer a fast, reliable picture of one matter.

## Steps

1. Find the matter in the Matter Register (by number, client or other party). Confirm with the lawyer if more than one could match.
2. Read the matter's folder in the document store: list documents by subfolder and date.
3. Search email for messages containing the matter number, client name or other party's name, most recent first (last 60 days unless the lawyer asks otherwise).
4. Build the summary. Every factual statement should point to its source (email date/sender or document name).

## Output format

```
M26-014: Smith: Property settlement
Status: [from register]   Last activity: [date]

WHERE IT'S AT
2–4 sentences, plain English.

KEY DATES
| Date | Event | Source |
(mark anything computed rather than stated as "to verify")

OPEN ACTIONS
- Who / what / by when

RECENT CORRESPONDENCE (last 5)
- date, from, one-line gist

DOCUMENTS ON FILE
Grouped by subfolder, newest first. Note obvious gaps (e.g. an email attachment not yet filed).
```

If preparing for a hearing or meeting, add a short "Things to raise" list at the end, clearly marked as suggestions for the lawyer to review.
