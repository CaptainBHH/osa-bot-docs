# Initial Configuration

After the bot is running, you need to configure it for your server before any features will work.

---

## Step 1 — Set staff and admin roles

These roles gate access to all bot commands. Without them, no one can use anything.

```
/config set option:Staff Role ID  value:ROLE_ID
/config set option:Admin Role ID  value:ROLE_ID
```

!!! tip "Getting a role ID"
    Enable Developer Mode in Discord (Settings → Advanced → Developer Mode), then right-click the role and select **Copy Role ID**.

---

## Step 2 — Set up channels

### Required channels

| Channel | Purpose | Config key |
|---------|---------|------------|
| Forum channel | Where database entries are posted as threads | `database_channel` |
| Announcement channel | Where new entry announcements are posted | `announcement_channel` |
| Investigations channel | Where private case threads are created | `investigations_channel` |

```
/config set option:Forum Channel  value:CHANNEL_ID
/config set option:Announcement Channel  value:CHANNEL_ID
/config set option:Investigations Channel  value:CHANNEL_ID
```

!!! info "Forum channel"
    The database channel must be a **Forum Channel**, not a regular text channel. Create one in your server settings first.

---

## Step 3 — Set up log channels

Each module has its own log channel. Create four private staff-only channels and configure them:

```
/config set option:Ticket Log Channel  value:CHANNEL_ID
/config set option:Case Log Channel  value:CHANNEL_ID
/config set option:Database Log Channel  value:CHANNEL_ID
/config set option:Error Log Channel  value:CHANNEL_ID
```

See [Log Channels](../config/logging.md) for a full breakdown of what each channel receives.

---

## Step 4 — Set up tickets

```
/config set option:Ticket Category ID  value:CATEGORY_ID
```

Then create your ticket types:

```
/ticketadmin type create
```

See [Managing Ticket Types](../tickets/types.md) for full details.

---

## Step 5 — Post the ticket panel

Navigate to your tickets channel and run:

```
/ticket panel
```

---

## Step 6 — Verify config

```
/config view
```

This shows all configured values, grouped by section, with ✅/⬜ status indicators.
