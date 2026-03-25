# Managing Entries

---

## Looking up entries

```
/lookup query:ExampleUser
```

Searches across Discord username, Roblox username, and Case ID. Returns up to 10 results showing the case ID, subject names, status, and a link to the forum entry.

The search, query, and result count are logged to the Database Log Channel.

---

## Updating an entry

```
/update case_id:OSA-ABC123
```

Shows the current entry details, then presents a dropdown to select which field to update. Selecting a field opens a **modal pre-filled with the current value** — edit it and submit.

Fields that can be updated:

| Field | Description |
|-------|-------------|
| Discord Username | Subject's Discord username |
| Discord ID | Subject's Discord ID |
| Roblox Username | Subject's Roblox username |
| Roblox ID | Subject's Roblox ID |
| Offence Category | Top-level category |
| Offence Subcategory | Specific offence |
| Offence Description | Brief description |
| Case Details | Full narrative |
| Evidence Links | Evidence URLs |

After updating, the forum thread is re-rendered with the new content and the announcement is updated.

You can update multiple fields in one session — the dropdown stays open after each update.

---

## Removing an entry

See [Removing Entries](../cases/removal.md).

---

## Searching within `/case list`

The `/case list` command also has a `search` parameter:

```
/case list pipeline_status:published search:ExampleUser
```

This searches by Roblox username, Discord username, or case ID within the filtered pipeline stage.
