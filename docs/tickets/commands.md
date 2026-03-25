# Ticket Commands

All ticket management commands. Most require the **Staff** role.

---

## Panel

### `/ticket panel`
Posts the ticket panel in the current channel. The panel is a standalone Components V2 message with a dropdown of all enabled ticket types.

**Requires:** Staff

---

## Managing users

### `/ticket add member:@User`
Adds a user to the current ticket channel with Handler permissions (read + send).

**Requires:** Staff, must be run inside a ticket channel

### `/ticket remove member:@User`
Removes a user's access to the ticket channel entirely.

**Requires:** Staff, must be run inside a ticket channel

### `/ticket perms target:@User level:handler`
Manually sets a specific permission level for a user or role in the ticket.

Levels: `viewer`, `handler`, `senior`, `none` (removes access)

**Requires:** Staff, must be run inside a ticket channel

---

## Claiming

### `/ticket unclaim`
Releases your claim on the current ticket. Only the current claimer can unclaim.

**Requires:** Staff, must be the current claimer

### `/ticket subclaim add member:@Staff`
Adds a sub-claimer to the ticket (gives them Handler access). Only the main claimer can do this.

### `/ticket subclaim remove member:@Staff`
Removes a sub-claimer.

---

## Ticket management

### `/ticket rename name:new-name`
Renames the ticket channel. The name is automatically lowercased and spaces replaced with hyphens.

**Requires:** Staff

### `/ticket transcript`
Generates an HTML transcript of the full ticket conversation and sends it to you as a file.

**Requires:** Staff

### `/ticket open member:@User ticket_type:report`
Manually opens a ticket for another user. The type must match a configured type key.

**Requires:** Staff

### `/ticket list status:open`
Lists all tickets in the server. Filterable by `open`, `closed`, or `all`. Shows up to 20 tickets.

**Requires:** Staff

### `/ticket investigation_panel`
Posts a standalone "Open Investigation" button in the current channel. Useful for old Ticket Tool channels that predate OSA Bot.

**Requires:** Staff

---

## Button reference

These buttons appear in ticket messages and are handled automatically:

| Button | Where | What it does |
|--------|-------|-------------|
| 🤝 Claim | Opening message | Claims the ticket for you, gives you Senior perms |
| 🔒 Close | Opening message | Closes the ticket, hides it from the opener |
| 🔍 Open Investigation | Opening message | Opens the case creation modal |
| 🔓 Reopen | After closing | Reopens the ticket, restores opener access |
| 📄 Transcript | After closing | Generates and sends the HTML transcript |
| 🗑️ Delete | After closing | Deletes the channel after 5 seconds |
