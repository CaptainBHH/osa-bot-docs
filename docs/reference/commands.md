# Command Reference

Complete list of every slash command. **S** = Staff required, **A** = Admin required.

---

## Config

| Command | Permission | Description |
|---------|-----------|-------------|
| `/config set option: value:` | A | Set a configuration value |
| `/config view` | A | View all current configuration, grouped by section |

---

## Tickets

| Command | Permission | Description |
|---------|-----------|-------------|
| `/ticket panel` | S | Post the ticket panel in the current channel |
| `/ticket list [status:]` | S | List tickets. Status: `open` (default), `closed`, `all` |
| `/ticket open member: ticket_type:` | S | Manually open a ticket for a user |
| `/ticket add member:` | S | Add a user to the current ticket channel |
| `/ticket remove member:` | S | Remove a user from the current ticket channel |
| `/ticket unclaim` | S | Release your claim on the current ticket |
| `/ticket subclaim add member:` | S | Add a sub-claimer (claimer only) |
| `/ticket subclaim remove member:` | S | Remove a sub-claimer (claimer only) |
| `/ticket rename name:` | S | Rename the ticket channel |
| `/ticket perms target: level:` | S | Set permissions for a user or role |
| `/ticket transcript` | S | Generate an HTML transcript of the ticket |
| `/ticket investigation_panel` | S | Post a standalone Open Investigation button |

### Ticket Admin

| Command | Permission | Description |
|---------|-----------|-------------|
| `/ticketadmin type create` | A | Create a new ticket type (modal) |
| `/ticketadmin type edit type_key:` | A | Edit an existing ticket type (modal) |
| `/ticketadmin type delete type_key:` | A | Delete a ticket type |
| `/ticketadmin type toggle type_key: enabled:` | A | Enable or disable a ticket type |
| `/ticketadmin type reorder type_key: position:` | A | Set the dropdown position of a type |
| `/ticketadmin type list` | A | List all configured ticket types |
| `/ticketadmin type setcategory type_key: category:` | A | Assign a specific category to a ticket type |
| `/ticketadmin type clearcategory type_key:` | A | Remove the per-type category override |
| `/ticketadmin form add type_key:` | A | Add a form field to a ticket type |
| `/ticketadmin form remove type_key: field_number:` | A | Remove a form field |
| `/ticketadmin form list type_key:` | A | List form fields for a ticket type |
| `/ticketadmin staffrole set type_key: role: level:` | A | Assign a role permission level to a ticket type |
| `/ticketadmin staffrole remove type_key: role:` | A | Remove a role assignment |
| `/ticketadmin staffrole list type_key:` | A | List role assignments for a type |
| `/ticketadmin logs channel:` | A | Set the ticket log channel |

---

## Cases

| Command | Permission | Description |
|---------|-----------|-------------|
| `/case create` | S | Open a new investigation case (modal) |
| `/case view case_id:` | S | View full case details with quick-action buttons |
| `/case list [pipeline_status:] [search:]` | S | Paginated case list with search |
| `/case assign case_id: member:` | S | Assign a staff member to a case |
| `/case status case_id: pipeline_status:` | S | Change the pipeline status |
| `/case note case_id:` | S | Add a note to a case (modal) |
| `/case evidence case_id:` | S | Add evidence to a case (modal) |
| `/case evidence_list case_id:` | S | View all evidence for a case |
| `/case suspect case_id: [account_type:]` | S | Add an alt account or associated person |
| `/case checklist case_id:` | S | View and manage the pre-publication checklist |
| `/case approve case_id:` | S | Approve a case (requires different staff member) |
| `/case publish case_id:` | S | Publish a case to the database |
| `/case link_ticket case_id:` | S | Link the current channel to a case |
| `/case remove case_id: reason_type: signed_by:` | S | Remove a published entry (modal) |

---

## Database

| Command | Permission | Description |
|---------|-----------|-------------|
| `/submit` | S | Submit a new database entry (3-step modal) |
| `/lookup query:` | S | Search the database by username or case ID |
| `/update case_id:` | S | Update fields on an existing entry |
| `/bulk file:` | A | Bulk upload entries from a ZIP of JSON files |

---

## Buttons

These are not slash commands but are referenced here for completeness.

| Button | Location | Permission |
|--------|----------|-----------|
| 🤝 Claim | Ticket opening message | S |
| 🔒 Close | Ticket opening message | S |
| 🔍 Open Investigation | Ticket opening message | S |
| 🔓 Reopen | Closed ticket message | S |
| 📄 Transcript | Closed ticket message | S |
| 🗑️ Delete | Closed ticket message | S |
| 👤 Assign to me | `/case view` | S |
| 📝 Add Note | `/case view` | S |
| 🔗 Add Evidence | `/case view` | S |
| « ‹ [page] › » | `/case list` | S |
| ✅/⬜ Checklist items | `/case checklist` | S |
| 🛑 Abort Upload | `/bulk` progress message | A |
