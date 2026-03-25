# Ticket Logs

All ticket events are posted to the configured **Ticket Log Channel**.

---

## Setting the log channel

```
/ticketadmin logs channel:#ticket-logs
```

Or via the main config:

```
/config set option:Ticket Log Channel  value:CHANNEL_ID
```

---

## Events logged

| Event | Triggered by |
|-------|-------------|
| 🎫 Ticket Opened | User selects type from panel or staff runs `/ticket open` |
| 🤝 Ticket Claimed | Staff clicks Claim button |
| 🔓 Ticket Unclaimed | Staff runs `/ticket unclaim` |
| 🔒 Ticket Closed | Staff clicks Close button |
| 🔓 Ticket Reopened | Staff clicks Reopen button |
| 📄 Transcript Generated | Staff clicks Transcript button or runs `/ticket transcript` |
| 🗑️ Ticket Deleted | Staff clicks Delete button |
| ➕ Member Added | Staff runs `/ticket add` |
| ➖ Member Removed | Staff runs `/ticket remove` |
| 👤 Sub-claimer Added | Staff runs `/ticket subclaim add` |
| 👤 Sub-claimer Removed | Staff runs `/ticket subclaim remove` |
| 🔑 Permissions Changed | Staff runs `/ticket perms` |
| ✏️ Renamed | Staff runs `/ticket rename` |

---

## Log format

Each log entry is a Components V2 container with a red accent strip. It shows the ticket number, channel mention, relevant staff member, and a timestamp.

Opening logs also include the first few form responses if the ticket type has form fields configured.
