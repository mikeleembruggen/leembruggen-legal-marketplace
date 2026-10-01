---
name: draft-from-template
description: Creates a new document for the lawyer from one of their precedent templates (Word or Google Docs) in the document store, filling in matter details from the Matter Register and correspondence. Use whenever the lawyer asks to draft, prepare or start a letter, cost agreement, file note, affidavit shell, notice or any standard document, or says "use my template for…", even if they don't say "template".
---

# Draft from Template

> **Practice settings** (assistant's name, lawyer's name, firm, state, platform — Microsoft 365 or Google Workspace — document store location, matter number format) live in the Practice Assistant project instructions. Read them first, refer to yourself by the assistant's name, and use the email, calendar and document connectors for the platform named there ("the document store" below means their SharePoint site or Google Drive folder). If they're missing, tell the user to run setup ("set up my practice assistant") and stop.

Turn the lawyer's precedents into ready-to-review drafts.

## Steps

1. **Find the template.** Look in `Templates/` in the document store. If several could fit, list them and ask which one. If none fits, say so and offer to draft from scratch.
2. **Gather the details.** Pull client name, other party, matter number, court file number, addresses and dates from the Matter Register and the matter folder. Placeholders in templates look like `[CLIENT NAME]`, `[MATTER NO]`, `[DATE]`, etc.
3. **Fill it in.** Replace every placeholder you can source. For any you can't, leave it highlighted as `[[TO COMPLETE: CLIENT ADDRESS]]` rather than inventing it.
4. **Keep the lawyer's wording.** Don't rewrite the precedent's legal language. Only fill placeholders and the matter-specific sections the lawyer asks for.
5. **Save as a draft** in the matter's `04 Drafts` folder, named `YYYY-MM-DD - DRAFT - [Document type] - [Short description]`, in the same format as the template (.docx for Word, a Google Doc for Google Docs).
6. **Report back**: where it was saved, which placeholders were filled and from which source, and a list of anything still to complete.

## Creating a new template
If the lawyer says "make this a template", take the document, replace matter-specific details with clear `[PLACEHOLDER]` names, show them the list of placeholders for approval, then save to `Templates/` with a clear name like `Letter - Initial client engagement`.
