# Permissions

OSA Bot uses two permission levels configured via `/config set`.

---

## Permission levels

### Staff
Can use all operational commands — tickets, cases, database lookups and submissions, and viewing logs.

### Admin
Everything Staff can do, plus all `/config` and `/ticketadmin` commands, and `/bulk`.

---

## Ticket channel permissions

Within ticket channels, the bot assigns one of three permission levels:

| Level | What it allows |
|-------|---------------|
| `viewer` | Read only — can see the channel but not send messages |
| `handler` | Read + send messages + attach files |
| `senior` | Read + send + manage messages + manage channel |

These can be set per ticket type via `/ticketadmin staffrole set`, or manually per channel with `/ticket perms`.

---

## Bot permissions required

The bot needs these Discord permissions:

- Manage Channels
- Manage Messages
- Send Messages
- Read Message History
- Embed Links
- Attach Files
- Use External Emojis
- View Channels

Make sure the bot's role is above any roles it needs to manage permissions for.
