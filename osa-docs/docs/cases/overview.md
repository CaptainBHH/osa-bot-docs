# Investigations Overview

The investigations system lets OSA staff track subjects through a structured case pipeline from initial report to published database entry.

---

## What is a case?

A case is a private investigation record tied to a specific subject. It contains:

- Subject identity (Roblox + Discord usernames and IDs)
- Evidence links and descriptions
- Staff notes
- A pre-publication checklist
- A pipeline status tracking where the case is in the process
- A link to the source ticket (if opened from one)

Each case gets a **private investigation thread** in the configured Investigations Channel, and is identified by a unique **Case ID** (e.g. `OSA-ABC123`).

---

## Opening a case

Cases can be opened two ways:

### From a ticket
Click the **🔍 Open Investigation** button in any ticket's opening message. This pre-links the case to the ticket.

### Directly
```
/case create
```

Both methods open a modal asking for the subject's details.

---

## Case ID format

Case IDs are randomly generated 6-character alphanumeric strings prefixed with `OSA-`, e.g. `OSA-K7X2NP`. They are unique per server.

---

## Titanite API enrichment

When a case is created with a Roblox ID, the bot automatically queries the **Titanite Utils API** to check for existing flags on that account. Results appear in the case thread opening message and the `/case view` output.

Configure the API with:
```
/config set option:Titanite Utils API URL  value:https://...
/config set option:Titanite Utils API Key  value:...
```
