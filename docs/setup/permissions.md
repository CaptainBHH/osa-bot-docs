# Permissions & Roles

OSA Bot uses two permission levels, both configured via `/config set`.

---

## Permission levels

### Staff
Members with the **Staff Role** can use all operational commands:

- Opening, managing, and closing tickets
- Creating and managing investigation cases
- Submitting, looking up, and updating database entries
- Viewing case lists and evidence

### Admin
Members with the **Admin Role** can do everything Staff can, plus:

- All `/config set` and `/config view` commands
- All `/ticketadmin` commands (creating types, form fields, staff roles)
- Bulk uploading database entries

!!! note
    Admin does not inherit from Staff automatically in the permission checks. If someone is Admin-only and needs Staff commands too, give them both roles.

---

## Ticket-level permissions

Within individual ticket channels, the bot manages permissions automatically:

| Level | Permissions |
|-------|------------|
| `viewer` | Read only — can see the channel but not send messages |
| `handler` | Read + send messages + attach files |
| `senior` | Read + send + manage messages + manage channel |

These can be assigned per ticket type via `/ticketadmin staffrole set`, or manually adjusted per channel with `/ticket perms`.

---

## Bot permissions

The bot itself needs the following Discord permissions:

- Manage Channels
- Manage Messages
- Send Messages
- Read Message History
- Embed Links
- Attach Files
- Use External Emojis
- View Channels
- Read Members (for the Members intent)

Make sure the bot's role is positioned **above** any roles it needs to manage permissions for.
