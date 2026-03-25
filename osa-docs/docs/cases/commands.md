# Case Commands

All commands for managing investigation cases. Require **Staff** unless noted.

---

## Creating cases

### `/case create`
Opens a modal to create a new investigation case. Fields:

- Subject Roblox Username
- Subject Roblox ID
- Subject Discord Username (optional)
- Subject Discord ID (optional)
- Initial notes (optional)

Creates a private thread in the Investigations Channel and optionally queries the Titanite API.

---

## Viewing cases

### `/case view case_id:OSA-ABC123`
Shows full case details including:

- Pipeline status bar
- Subject identity and alt accounts
- Opened by, assigned to, approved by
- Evidence and note counts
- Checklist progress
- Links to investigation thread and forum entry

Also shows three inline quick-action buttons: **Assign to me**, **Add Note**, **Add Evidence**.

### `/case list [pipeline_status:all] [search:query]`
Lists cases with pagination (10 per page). Filterable by pipeline stage. Optional search by Roblox username, Discord username, or case ID.

Navigation buttons — « ‹ [page/total] › » — are built into the message. The page number button opens a modal to jump to a specific page.

---

## Managing a case

### `/case assign case_id:OSA-ABC123 member:@Staff`
Assigns a staff member to the case and adds them to the investigation thread.

### `/case status case_id:OSA-ABC123 pipeline_status:active`
Changes the pipeline status. Posts a notification to the case thread.

### `/case note case_id:OSA-ABC123`
Opens a modal to add a note. Notes are posted to the investigation thread.

### `/case evidence case_id:OSA-ABC123`
Opens a modal to log evidence. Fields: URL and description (both optional but at least one required).

### `/case evidence_list case_id:OSA-ABC123`
Lists all evidence logged for a case with submitter, timestamp, URL, and description.

### `/case suspect case_id:OSA-ABC123 account_type:alt`
Adds an alt account or associated person to the case. Account types: `alt`, `associated`.

### `/case checklist case_id:OSA-ABC123`
Shows the pre-publication checklist. Buttons allow ticking/unticking individual items.

---

## Approval and publication

### `/case approve case_id:OSA-ABC123`
Approves the case. Must be a different staff member to the one who opened it.

### `/case publish case_id:OSA-ABC123`
Publishes the case to the database forum. Requires approved status and a complete checklist.

---

## Linking

### `/case link_ticket case_id:OSA-ABC123`
Links the current channel to a case. Works in OSA Bot ticket channels and old Ticket Tool channels.

---

## Removal

### `/case remove case_id:OSA-ABC123 reason_type:appeal signed_by:MightySTitanite - OSA EXEC`
Removes a published entry. See [Removing Entries](removal.md) for full details.
