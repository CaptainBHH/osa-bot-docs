# Initial Setup

Before any features work, you need to configure the bot for your server using `/config set`. All config commands require **Admin**.

---

## Step 1 — Staff and admin roles

These gate access to all bot commands.

```
/config set option:Staff Role ID   value:ROLE_ID
/config set option:Admin Role ID   value:ROLE_ID
```

!!! tip "Getting a role ID"
    Enable Developer Mode in Discord (User Settings → Advanced → Developer Mode), then right-click the role → **Copy Role ID**.

---

## Step 2 — Channels

### Required

| What to set | Option name | Notes |
|-------------|-------------|-------|
| Database entries forum | Forum Channel | Must be a **Forum Channel**, not a text channel |
| New entry announcements | Announcement Channel | Regular text channel |
| Private case threads | Investigations Channel | Staff-only text channel |

```
/config set option:Forum Channel          value:CHANNEL_ID
/config set option:Announcement Channel   value:CHANNEL_ID
/config set option:Investigations Channel value:CHANNEL_ID
```

### Log channels

Create four staff-only channels and set them:

```
/config set option:Ticket Log Channel    value:CHANNEL_ID
/config set option:Case Log Channel      value:CHANNEL_ID
/config set option:Database Log Channel  value:CHANNEL_ID
/config set option:Error Log Channel     value:CHANNEL_ID
```

See [Log Channels](logging.md) for what each one receives.

---

## Step 3 — Ticket category

```
/config set option:Ticket Category ID  value:CATEGORY_ID
```

!!! tip "Getting a category ID"
    Right-click the category in your server → **Copy Category ID**.

---

## Step 4 — Create ticket types

```
/ticketadmin type create
```

See [Managing Ticket Types](../tickets/types.md) for full details.

---

## Step 5 — Post the ticket panel

Navigate to your public tickets channel and run:

```
/ticket panel
```

---

## Step 6 — Verify

```
/config view
```

Shows all settings grouped by section with ✅/⬜ indicators. Channels and roles resolve to mentions.
