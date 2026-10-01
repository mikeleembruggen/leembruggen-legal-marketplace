# Practice Assistant

An AI assistant for small Australian law practices. It runs in Claude Cowork and connects to your email and documents (Microsoft 365 or Google Workspace). It gives you a morning inbox brief, a live matter dashboard, deadline alerts, matter summaries, filing and drafting from your own precedents.

## Before you start

You need:
- A paid Claude plan (Pro, Max, Team or Enterprise)
- The **Claude desktop app** (download from [claude.ai/download](https://claude.ai/download))
- Your work email on **Microsoft 365** (Outlook) or **Google Workspace** (Gmail)

## Install (about 2 minutes)

1. Open the **Claude desktop app** and sign in.
2. Go to **Customize → Plugins**.
3. Click **Add → Add marketplace**.
4. Paste this and confirm:
   ```
   mikeleembruggen/leembruggen-legal-marketplace
   ```
5. Find **Practice Assistant** in the list and click **Install**.

That's it. You'll get updates automatically.

**If step 4 doesn't work:** [download the plugin file](https://github.com/mikeleembruggen/leembruggen-legal-marketplace/raw/main/practice-assistant.plugin), then in **Customize → Plugins** click **Add → Upload plugin** and choose the file you just downloaded.

## Set up (about 45 minutes)

1. In the Claude desktop app, click **+ New** at the top of the left sidebar.
2. Type: **Set up my practice assistant**
3. Follow along. It goes one step at a time: you name your assistant, turn off model training for privacy, connect your email and documents, choose your daily routines, and test everything on a dummy matter.

You can stop at any point. To pick up where you left off, type **Continue setup**.

## Good to know

- It **never sends emails**. It only drafts them, and you send.
- It **never deletes or overwrites files** unless you ask.
- Any deadline it calculates is marked **"to verify"**. You make the final call.
- It helps with organising and drafting. It doesn't give legal advice.

Need help? Contact Michael Leembruggen.

---

## For the maintainer

Releasing an update:
1. Edit the skills under `practice-assistant/skills/`.
2. Bump `version` in `practice-assistant/.claude-plugin/plugin.json`.
3. Rebuild the upload file: `cd practice-assistant && rm -f ../practice-assistant.plugin && zip -r ../practice-assistant.plugin . -x "*.DS_Store"`
4. Commit and push. Clients who installed through the marketplace get the update when it syncs.

This repo is public. Never commit client data.
