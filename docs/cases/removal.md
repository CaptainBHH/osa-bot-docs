# Removing Published Entries

When a subject successfully appeals or an entry needs to be removed for other reasons, use `/case remove` to update the published forum entry in place.

---

## How it works

`/case remove` does the following:

1. Edits the forum thread's **starter message** (the original entry content) with the removal notice
2. Renames the thread to `[APPEALED] Original Name` or `[REMOVED] Original Name`
3. Updates the case pipeline status to `appealed` or `removed`
4. Posts a notification to the investigation thread

The thread itself is **not deleted** — the history is preserved.

---

## Running the command

```
/case remove
  case_id: OSA-ABC123
  reason_type: appeal
  signed_by: MightySTitanite - OSA EXEC
```

A modal opens for you to write the full removal description. On submit, the forum entry is updated immediately.

---

## Reason types

| Type | Status set to | Header |
|------|--------------|--------|
| `appeal` | `appealed` | `<:OSA:emoji>  **APPEAL DESCRIPTION**` |
| `removed` | `removed` | `<:OSA:emoji>  **REMOVAL NOTICE**` |

---

## Message format

The removal notice is posted in the following format:

```
> <:OSA:emoji>  **APPEAL DESCRIPTION**
[Your description text here]
[Signed by line]
```

### Example

```
> <:OSA:1409535230099849227>  **APPEAL DESCRIPTION**
The Investigations Team within the Office of Self-Accountability has
officially accepted the subject's appeal to be removed from the Bureau's
database of perpetrators and offenders. This decision was made because...

MightySTitanite - OSA EXEC
```

---

## Requirements

- The case must have a published forum entry (`forum_thread_id` must be set)
- The case does not need to be in `published` status — you can remove from any status, but it's intended for published entries
- **Staff** permission required

---

!!! warning "Irreversible"
    The starter message edit cannot be undone through the bot. If you need to reverse a removal, you would need to manually edit the forum post.
