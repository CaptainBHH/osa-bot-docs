# Database Overview

The OSA database is a public record of offenders and incidents, stored as threads in a Discord Forum Channel. Each entry is a forum post with structured content.

---

## Entry structure

Each database entry contains:

| Field | Description |
|-------|-------------|
| Discord Username | Subject's Discord username |
| Discord ID | Subject's Discord user ID |
| Roblox Username | Subject's Roblox username |
| Roblox ID | Subject's Roblox user ID |
| Offence Category | One of: Degeneracy, Cybercrime, General Malice |
| Offence Subcategory | Specific offence type |
| Offence Description | Brief description |
| Case Details | Full case narrative |
| Evidence Links | Supporting evidence |

---

## Forum tags

Entries are automatically tagged in the forum based on their offence category:

| Tag | Auto-detected from |
|-----|--------------------|
| Degeneracy | Keywords: grooming, nsfw, explicit, sexual, minor, etc. |
| Cybercrime | Keywords: hacking, doxxing, blackmail, espionage, etc. |
| General Malice | Default if neither of the above match |

---

## Announcements

When an entry is published, an announcement is posted in the configured Announcement Channel with the subject's name, case ID, offence, and a link to the forum thread.

---

## Case IDs

Every entry is assigned a unique Case ID in the format `OSA-XXXXXX`. This is used to reference the entry in all update, lookup, and removal commands.

---

## How entries get published

There are three ways an entry ends up in the database:

1. **`/submit`** — a staff member fills in the full entry form manually
2. **`/case publish`** — publishing a completed investigation case
3. **`/bulk`** — uploading a ZIP of JSON files for bulk entry

All three automatically set the case pipeline status to `published`.
