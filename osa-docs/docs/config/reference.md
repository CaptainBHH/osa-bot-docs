# Configuration Reference

All bot configuration is managed with `/config set` and viewed with `/config view`. Requires **Admin**.

---

## Viewing config

```
/config view
```

Shows all settings grouped by section, with ✅ (set) or ⬜ (not set) indicators. Channels and roles are resolved to mentions. Sensitive values are hidden.

---

## Setting a value

```
/config set option:Option Name  value:VALUE
```

---

## Full config reference

### 📢 Channels

| Option | Config key | Description |
|--------|-----------|-------------|
| Forum Channel | `database_channel` | Forum channel where database entries are posted as threads. Must be a Forum Channel. |
| Announcement Channel | `announcement_channel` | Channel where new entry announcements are posted |
| Investigations Channel | `investigations_channel` | Channel where private case investigation threads are created |

### 📋 Log Channels

| Option | Config key | Description |
|--------|-----------|-------------|
| Ticket Log Channel | `ticket_log_channel` | Ticket lifecycle events |
| Case Log Channel | `case_log_channel` | Investigation case events |
| Database Log Channel | `database_log_channel` | Submission, lookup, and bulk upload events |
| Error Log Channel | `error_log_channel` | Bot errors and unhandled exceptions |

### 👥 Roles

| Option | Config key | Description |
|--------|-----------|-------------|
| Staff Role ID | `staff_role` | Role with Staff-level permissions |
| Admin Role ID | `admin_role` | Role with Admin-level permissions |

### 🎫 Tickets

| Option | Config key | Description |
|--------|-----------|-------------|
| Ticket Category ID | `ticket_category` | Global fallback category for ticket channels. Overridden per ticket type via `/ticketadmin type setcategory`. |

### 🔗 Integrations

| Option | Config key | Description |
|--------|-----------|-------------|
| Titanite Utils API URL | `titanite_api_url` | Base URL for the Titanite network lookup API |
| Titanite Utils API Key | `titanite_api_key` | API key (hidden in config view) |
| OSA Emoji String | `osa_emoji_id` | Custom emoji string used in the ticket panel header and removal notices (e.g. `<:OSA:1409535230099849227>`) |

---

## Getting IDs

Enable **Developer Mode** in Discord (User Settings → Advanced → Developer Mode), then:

- **Channel ID** — right-click the channel → Copy Channel ID
- **Category ID** — right-click the category → Copy Category ID  
- **Role ID** — right-click the role in Server Settings → Copy Role ID
