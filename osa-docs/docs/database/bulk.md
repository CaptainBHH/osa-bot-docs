# Bulk Upload

The `/bulk` command uploads multiple database entries at once from a ZIP file of JSON files.

---

## File format

Each entry is a `.json` file inside the ZIP. Required fields:

```json
{
  "discord_username": "example#0000",
  "discord_id": "123456789012345678",
  "roblox_username": "ExampleUser",
  "roblox_id": "1234567890",
  "offence_category": "Degeneracy",
  "offence_subcategory": "Grooming",
  "offence_description": "Brief description of the offence",
  "case_details": "Full narrative of the case...",
  "evidence_links": "https://link1.com\nhttps://link2.com"
}
```

Optional fields:

```json
{
  "forum_tags": "Degeneracy"
}
```

If `forum_tags` is not set, the bot auto-detects the tag from the offence fields.

---

## Running the bulk upload

```
/bulk file:your-entries.zip
```

The command must be run in a non-ephemeral context (the progress message appears publicly in the channel). Progress is updated as entries are processed.

---

## During upload

A progress message shows:

- How many entries have been processed
- How many succeeded and failed
- An **Abort Upload** button

### Aborting

Clicking **Abort Upload** stops processing immediately and **purges all forum threads** created during that upload. This rolls back the entire batch.

---

## After upload

A summary is posted showing:

- Total successful entries
- Total failed entries
- Number of threads purged (if aborted)
- A list of errors (up to 5 shown)

All results are logged to the Database Log Channel.

---

## Duplicate handling

If a case ID already exists in the database, that entry is skipped and counted as a failure.

---

!!! warning "Large batches"
    Discord rate limits apply. Very large batches (100+ entries) will take time. Do not close Discord during a bulk upload — you need to be able to click Abort if something goes wrong.
