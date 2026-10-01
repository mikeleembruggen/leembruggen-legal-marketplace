---
name: morning-triage
description: The lawyer's daily inbox triage for their legal practice. Scans recent email (Outlook or Gmail), matches each item to a matter, and produces a prioritised to-do list with deadlines and suggested next steps. Use this whenever the lawyer asks for their morning brief, daily summary, to-do list, "what's in my inbox", "what do I need to do today", "catch me up", or when a scheduled daily task runs, even if they don't say "triage".
---

# Morning Triage

> **Practice settings** (assistant's name, lawyer's name, firm, state, platform — Microsoft 365 or Google Workspace — document store location, matter number format) live in the Practice Assistant project instructions. Read them first, refer to yourself by the assistant's name, and use the email, calendar and document connectors for the platform named there ("the document store" below means their SharePoint site or Google Drive folder). If they're missing, tell the user to run setup ("set up my practice assistant") and stop.

Produce the lawyer's daily action list from their inbox.

## Steps

1. **Read the inbox.** Using the email connector, fetch emails received since the previous working day at 5pm (on Mondays, since Friday 5pm). Include flagged or starred emails still unanswered from earlier.
2. **Skip the noise.** Ignore newsletters, marketing, automated notifications and CPD promotions. Count them and mention the number at the end so the lawyer knows they were seen.
3. **Match to a matter.** For each remaining email:
   - First look for a matter number (e.g. `M26-014`) in the subject or body.
   - Otherwise match sender, client name or other party against the Matter Register in the document store.
   - If you can't match confidently, put it under "Unmatched: please confirm" rather than guessing.
4. **Classify each email** as one of:
   - **Urgent today**: court or tribunal correspondence, anything with a deadline within 3 business days, a distressed client, or an opposing practitioner requiring a response.
   - **This week**: needs a reply or action but not today.
   - **For information**: no action needed.
5. **Extract dates.** Pull out any hearing dates, filing deadlines or response deadlines exactly as stated, with the source email. Never compute a deadline; if one needs calculating, say "deadline to verify" and show the basis.
6. **Check attachments.** List attachments per matter and whether they appear to already be in the matter's folder in the document store.

## Output format

```
MORNING BRIEF: Tue 6 Oct 2026

URGENT TODAY
1. [M26-014 Smith] Directions order from Magistrates Court: affidavit due Fri 9 Oct 2026 (source: email from registry, 5 Oct 3:12pm). Next step: draft affidavit.
...

THIS WEEK
...

FOR INFORMATION
...

UNMATCHED: PLEASE CONFIRM
...

KEY DATES SEEN
| Date | Matter | What | Source |

ATTACHMENTS NOT YET FILED
...

(14 newsletters/notifications skipped)
```

Keep each item to one or two lines. Offer at the end to draft replies for any urgent items; don't draft them unasked. Never send anything.
