# Log Channels

OSA Bot posts structured log messages to four separate channels — one per module. Each message is a Components V2 container with a colour-coded accent strip.

---

## Setting up log channels

```
/config set option:Ticket Log Channel  value:CHANNEL_ID
/config set option:Case Log Channel  value:CHANNEL_ID
/config set option:Database Log Channel  value:CHANNEL_ID
/config set option:Error Log Channel  value:CHANNEL_ID
```

Log channels are optional. If a channel isn't set, that module's events are silently skipped (still saved to `osa.log` on disk).

---

## Ticket log channel 🎫

Accent colour: **Red**

| Event | Triggered by |
|-------|-------------|
| Ticket Opened | Panel dropdown or `/ticket open` |
| Ticket Claimed | Claim button |
| Ticket Unclaimed | `/ticket unclaim` |
| Ticket Closed | Close button |
| Ticket Reopened | Reopen button |
| Transcript Generated | Transcript button or `/ticket transcript` |
| Ticket Deleted | Delete button |
| Member Added | `/ticket add` |
| Member Removed | `/ticket remove` |
| Sub-claimer Added | `/ticket subclaim add` |
| Sub-claimer Removed | `/ticket subclaim remove` |
| Permissions Changed | `/ticket perms` |
| Renamed | `/ticket rename` |

---

## Case log channel 🔍

Accent colour: **Blue**

| Event | Triggered by |
|-------|-------------|
| Case Opened | `/case create` or Open Investigation button |
| Case Assigned | `/case assign` or Assign to me button |
| Status Changed | `/case status` or `/case remove` |
| Note Added | `/case note` |
| Evidence Added | `/case evidence` |
| Suspect Added | `/case suspect` |
| Checklist Updated | `/case checklist` buttons |
| Case Approved | `/case approve` |
| Case Published | `/case publish` |
| Ticket Linked | `/case link_ticket` |

---

## Database log channel 🗄️

Accent colour: **Purple**

| Event | Triggered by |
|-------|-------------|
| Entry Submitted | `/submit` |
| Entry Updated | `/update` |
| Lookup | `/lookup` |
| Bulk Upload Started | `/bulk` |
| Bulk Upload Complete | `/bulk` — success |
| Bulk Upload Aborted | Abort button during `/bulk` |

---

## Error log channel 🚨

Accent colour: **Red**

Receives:

- Any unhandled slash command exception (with command name, user, and truncated traceback)
- Any unhandled event listener exception

!!! tip "Also check osa.log"
    Full tracebacks are always written to `osa.log` on the server regardless of whether an error log channel is configured.

    ```bash
    tail -f ~/osa-bot/osa.log
    ```
