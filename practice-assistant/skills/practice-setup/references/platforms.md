# Platform reference

Use the section for the platform the lawyer chose in Step 1.

---

## Microsoft 365 (Outlook + SharePoint)

### Connect
- **Settings → Connectors → Microsoft 365 → Connect**, sign in with the work account and approve. This one connector covers Outlook mail, calendar, OneDrive and SharePoint.
- If Microsoft asks for administrator approval, that's usually them (or their IT person) in the Microsoft 365 admin centre.

### Create the store
- sharepoint.com → **Create site → Team site**, named as chosen. Use its **Documents** library as the store.
- Solo practitioner who'd rather not use SharePoint: a top-level OneDrive folder with the chosen name works too.

### Systems block (for project instructions)
```
- Platform: Microsoft 365.
- Email and calendar: Outlook, via the Microsoft 365 connector.
- Document store: SharePoint site "{{STORE_NAME}}" (Documents library), via the Microsoft 365 connector.
- Register and templates: Excel workbook; Word documents.
```

---

## Google Workspace (Gmail + Google Drive)

### Connect
- **Settings → Connectors**: connect **Gmail**, **Google Calendar** and **Google Drive** (three separate connectors), signing in with the work Google account each time.
- If the Google Workspace admin has restricted third-party apps, the admin (often them, or their IT person) needs to allow Claude in the Google Admin console.

### Create the store
- drive.google.com → **New → Folder** named as chosen (or a **Shared drive** if others in the practice will need access).

### Systems block (for project instructions)
```
- Platform: Google Workspace.
- Email: Gmail, via the Gmail connector. Calendar: Google Calendar connector.
- Document store: Google Drive folder "{{STORE_NAME}}", via the Google Drive connector.
- Register and templates: Google Sheet; Google Docs (Word files stored in Drive also work).
```
