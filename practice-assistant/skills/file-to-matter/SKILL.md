---
name: file-to-matter
description: Files emails and attachments into the correct matter folder in the lawyer's document store (SharePoint or Google Drive), using the firm's folder structure and naming conventions. Use whenever the lawyer asks to file, save, store, archive or put away an email, attachment or document, or asks "where should this go", even if they don't name the matter.
---

# File to Matter

> **Practice settings** (assistant's name, lawyer's name, firm, state, platform — Microsoft 365 or Google Workspace — document store location, matter number format) live in the Practice Assistant project instructions. Read them first, refer to yourself by the assistant's name, and use the email, calendar and document connectors for the platform named there ("the document store" below means their SharePoint site or Google Drive folder). If they're missing, tell the user to run setup ("set up my practice assistant") and stop.

Save correspondence and documents into the right place, consistently.

## Steps

1. **Identify the matter** using the matter number, then the Matter Register. If unsure, ask the lawyer before filing.
2. **Pick the subfolder:**
   - `01 Correspondence`: emails and letters to/from clients, other parties, practitioners.
   - `02 Court Documents`: anything filed with or issued by a court or tribunal (orders, applications, affidavits as filed, notices).
   - `03 Evidence`: photos, statements, records, screenshots, reports.
   - `04 Drafts`: the lawyer's work in progress.
   - `05 Notes`: file notes, call notes, research notes.
3. **Name the file:** `YYYY-MM-DD - [Type] - [From/To] - [Short description].[ext]`
   - e.g. `2026-10-05 - Letter - From OP Solicitors - Response to offer.pdf`
   - e.g. `2026-10-05 - Order - Magistrates Court - Directions.pdf`
   - Use the date on the document, not today's date, where one exists.
4. **Save emails as PDF** where possible, so the record is fixed.
5. **Never overwrite.** If a file with that name exists, add ` (2)`.
6. **Confirm back** with a short list: what was filed, where, and under what name.

## If the connector can't write to the document store
Say so plainly and instead give the lawyer the exact folder path and filename to use, so they can drag it in themselves in seconds. (Routine auto-filing can be handled separately by an automation flow: Power Automate on Microsoft 365, Apps Script on Google Workspace.)
