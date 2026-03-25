# Ticket System Overview

OSA Bot includes a fully configurable ticket system built on Components V2.

---

## How it works

1. Staff post a **ticket panel** in a public channel using `/ticket panel`
2. Users select a ticket type from the dropdown
3. If the type has form fields configured, a modal opens for the user to fill in
4. A private channel is created in the configured category with the appropriate staff role permissions
5. The opening message contains **Claim**, **Close**, and **Open Investigation** buttons
6. Staff manage the ticket from there

---

## The panel

The panel is a Components V2 message with a dropdown listing all enabled ticket types. It posts as a standalone message (not a reply) and shows your configured OSA emoji in the header.

```
/ticket panel
```

!!! tip "Reposting the panel"
    If you add, remove, or reorder ticket types, re-run `/ticket panel` to get a fresh panel reflecting the changes. The old panel will still work but won't show the updated types.

---

## Ticket channel lifecycle

```
Panel dropdown selected
        ↓
Form modal (if configured)
        ↓
Private channel created
        ↓
Welcome message with Claim / Close / Open Investigation
        ↓
Staff claim + handle
        ↓
Closed → Reopen / Transcript / Delete
```

---

## Ticket numbering

Tickets are numbered sequentially per server starting from 1, formatted as `#0001`, `#0002`, etc. Channel names follow the pattern `ticket-0001-repo` (type truncated to 4 chars).

---

## Duplicate prevention

A user cannot open two tickets of the same type simultaneously. If they try, the bot will tell them their existing ticket channel and refuse to create a new one.
