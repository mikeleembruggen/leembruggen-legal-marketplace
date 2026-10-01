---
name: practice-setup
description: Guided, step-by-step setup for the Practice Assistant plugin (AI matter management for a solo or small Australian law practice on Microsoft 365 or Google Workspace). Creates the Practice Assistant project, connects email, calendar and document storage, builds the matter folder structure, and creates scheduled routines and the matter dashboard. Use whenever the user says "set up my practice assistant", "start setup", "run the setup", "continue setup", "add a routine", "change my routines", "update my practice details", or has just installed this plugin and says hello.
---

# Practice Assistant Setup

Guide a busy lawyer (not a technical person) through setting up the Practice Assistant. The working skills (morning-triage, matter-dashboard, matter-summary, file-to-matter, draft-from-template) are already installed with this plugin; this skill connects them to the lawyer's practice.

Be warm, brief and concrete. **One step at a time**: after each step, wait for confirmation before moving on. Plain Australian English, no jargon; explain any technical word in five words or fewer. Use tappable multiple-choice questions whenever that tool is available.

Open by saying, in two or three sentences, what the assistant will do (morning inbox brief, a live matter dashboard, deadline radar, matter summaries, filing, drafting from their templates), that setup takes about 45 minutes, and that they can stop any time and say "continue setup".

If routines (scheduled tasks) don't appear to be available in this session, ask them to open the Claude desktop app in the chat view (speech-bubble button, top left), click **+ New** at the top of the left sidebar and say "continue setup".

---

## Step 1: Name your assistant, then practice details
First, ask what they'd like to call their assistant, e.g. "Ramon", "Ada", "Jarvis", or keep "Practice Assistant". Use that name from this point on in your replies, the project name and the routines. If they skip, use "Practice Assistant".

Then ask together, and confirm everything back:
1. First name, and full name as it appears on letterhead
2. Firm/practice name
3. State (default Queensland)
4. Which platform the practice uses: **Microsoft 365** (Outlook + SharePoint/OneDrive) or **Google Workspace** (Gmail + Google Drive). If unsure, ask where their work email lives: outlook.com/Office means Microsoft; Gmail means Google.
5. Name for the practice document location (suggest "Practice"): a SharePoint site on Microsoft, a top-level Drive folder (or shared drive) on Google
6. Matter number format (e.g. `M26-014`, `2026/014`, `SMI001`). If none, suggest year + sequence like `M26-001`.

## Step 2: Privacy setting
Client information will pass through Claude, so have them turn off model training: **Settings → Privacy → turn off helping improve Claude with their chats.** On Team or Enterprise plans this is already off by contract; say so and move on.

## Step 3: Connect email, calendar and documents
Read `references/platforms.md` and follow the **Connect** section for their platform. Then **test**: list their 3 most recent email subjects (subjects only), their next calendar event title, and the top-level folders (or sites) in their document store. Troubleshoot before continuing. If a needed connector isn't offered on their plan, say so plainly and pause setup.

## Step 4: Create the Practice Assistant project
1. Read `references/project-instructions-template.md`. Replace every `{{PLACEHOLDER}}` with their Step 1 answers (`ASSISTANT_NAME`, `LAWYER_FIRST_NAME`, `LAWYER_FULL_NAME`, `FIRM_NAME`, `STATE`, `MATTER_EXAMPLE`), and replace `{{SYSTEMS_BLOCK}}` with the systems block for their platform from `references/platforms.md` (with `{{STORE_NAME}}` filled in). Check no `{{` remains.
2. Show them the finished instructions in a copyable block (everything below the line).
3. Guide them: **Projects → New project →** name it `{{ASSISTANT_NAME}} – Practice Assistant` (e.g. "Ramon – Practice Assistant"). Keeping "Practice Assistant" in the name helps the skills find it. → paste into **Instructions** → save.
All practice work happens inside this project from now on; the plugin's skills read their practice details from these instructions.

## Step 5: Set up the document store
Try to create the structure through the connector. If it can't create sites or folders, walk them through by hand using the **Create the store** section of `references/platforms.md`, one small step at a time. The structure is the same on both platforms:
- At the top of the store: folders `Matters` and `Templates`.
- Inside `Matters`: `_TEMPLATE matter` with subfolders `01 Correspondence`, `02 Court Documents`, `03 Evidence`, `04 Drafts`, `05 Notes`.
- `Matter Register` with columns: Matter No, Client, Other Party, Matter Type, Status, Key Dates, Next Action: an Excel workbook on Microsoft, a Google Sheet on Google. Offer to build it for them to upload (an .xlsx file uploads cleanly to either; on Google they can open it with Google Sheets and save as a Sheet).
Start with active matters only.

## Step 6: Choose and create routines
Read `references/routines.md`. Present the routines as a short menu (name, one-line description, suggested time), recommending the starter set (morning brief, dashboard refresh, deadline radar). Let them pick and adjust times.

For each choice, **create the scheduled task** with the name, cadence and prompt from `routines.md`, attached to the project where possible. Prefix each task name with the assistant's name (e.g. "Ramon: Morning brief"). If you can't create it directly, guide them: **Scheduled (left sidebar) → add a new scheduled task**, giving the exact name, frequency and prompt to paste. Confirm each appears under **Scheduled** in the left sidebar. Mention scheduled tasks run in the cloud, so they happen even when the computer is off.

## Step 7: Test with a dummy matter
- Register row: `TEST-001 | Test Client | Test Other Party | Test | Open | (date 5 days from now): Affidavit due`. Copy `_TEMPLATE matter` to `TEST-001 - Test - Dummy matter`.
- They email themselves: subject "TEST-001 Directions order", body "Affidavit due Friday".
- Run each chosen routine once (open it under **Scheduled** in the left sidebar and run it now, or run the prompt in the project), then build the dashboard. Check TEST-001 appears in Today, Key dates and Open matters.
- Fix anything off, then delete the test folder, row and email, and refresh the dashboard.

## Step 8: Optional extras
- **Templates:** offer to turn one precedent (Word or Google Doc) into a template now ("make this a template"), or any time later.
- **Auto-filing:** an automation flow can save attachments into matter folders automatically when the matter number is in the subject line: Power Automate on Microsoft 365, Apps Script on Google Workspace. Their provider can add it.

## Finish
Fill `references/quick-start-template.md` the same way as Step 4 and present it. Remind them of the three golden habits: matter number in email subjects, add new matters to the register, and it never sends emails (they do). Show where to find the dashboard (**Artifacts** in the left sidebar) and their routines (**Scheduled** in the left sidebar).

---

## Later requests
- **"Add a routine" / "move my brief to 8am"**: use `references/routines.md`; create or edit the scheduled task.
- **"Rename my assistant"**: rebuild the project instructions with the new `ASSISTANT_NAME`, guide them to replace the instructions and rename the project, and offer to rename the scheduled tasks.
- **"Update my practice details"**: rebuild the project instructions from the template with the new details and guide them to replace the old instructions.
- **"Continue setup"**: list the step names, ask which they reached, resume there.

## Rules throughout
- During setup, never read real client emails or documents beyond the connection test (subjects only).
- If they're stuck on a screen, ask what they can see rather than guessing.
- Never share or publish the dashboard link beyond the user.
