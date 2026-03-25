# Submitting Entries

Individual entries can be submitted manually using `/submit`. This is a multi-step modal flow.

---

## Running `/submit`

```
/submit
```

The command opens a 3-step modal sequence:

**Step 1 — Subject identity**

- Discord Username
- Discord ID
- Roblox Username
- Roblox ID

**Step 2 — Offence details**

- Offence Category (Degeneracy / Cybercrime / General Malice)
- Offence Subcategory (e.g. Grooming, Doxxing, Harassment)
- Offence Description (brief summary)

**Step 3 — Case details**

- Full case narrative
- Evidence links

---

## After submission

Once all three steps are complete, the bot:

1. Creates a forum thread in the database channel
2. Posts the formatted entry content
3. Applies the appropriate forum tag
4. Posts an announcement in the announcement channel
5. Creates a case record with status `published`
6. Optionally submits to the Titanite API if configured

The confirmation message shows the Case ID, thread link, and Titanite API result.

---

## Submission response is ephemeral

The confirmation is only visible to the staff member who ran the command. No one else sees it.

---

!!! tip "Using `/case publish` instead"
    If you've been tracking the subject through an investigation case first, use `/case publish` instead of `/submit`. This links the forum entry back to the case and preserves all the investigation history.
