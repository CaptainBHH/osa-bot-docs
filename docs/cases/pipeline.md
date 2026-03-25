# Case Pipeline

Every case moves through a defined pipeline from creation to resolution. The current stage is shown as a visual progress bar in `/case view`.

---

## Pipeline stages

| Stage | Colour | Description |
|-------|--------|-------------|
| `open` | 🔵 Blue | Case created, initial investigation underway |
| `active` | 🟢 Green | Actively being worked on by assigned staff |
| `pending_review` | 🟡 Amber | Evidence gathered, awaiting peer review |
| `approved` | 🟣 Purple | Approved by a second staff member, ready to publish |
| `published` | 🔴 Red | Entry live in the public database |
| `appealed` | 🟡 Amber | Subject has successfully appealed, entry updated |
| `removed` | ⚫ Grey | Entry removed for other reasons |
| `closed` | ⚫ Grey | Case closed without publication |

---

## Changing the status

```
/case status case_id:OSA-ABC123 pipeline_status:active
```

Any staff member can change the status at any point. Status changes are posted to the case thread and logged to the Case Log Channel.

---

## The checklist

Before a case can be **approved** or **published**, five checklist items must be completed:

1. Evidence reviewed and logged
2. Subject identity confirmed (Roblox + Discord verified)
3. Relevant community leadership notified
4. Reported to authorities (if applicable)
5. Approved by a second staff member

View and tick items with:
```
/case checklist case_id:OSA-ABC123
```

---

## Approval

Approval requires a **different** staff member to the one who opened the case:

```
/case approve case_id:OSA-ABC123
```

This sets the pipeline to `approved` and marks the approver. The case must be fully approved before it can be published.

---

## Publication

Publishing creates a thread in the database forum channel using the stored submission data:

```
/case publish case_id:OSA-ABC123
```

!!! warning "Requirements before publishing"
    - The checklist must be complete
    - The case must be in `approved` status
    - Submission data must be attached (use `/submit` or run `/case publish` which will prompt you)

Once published, the pipeline status is automatically set to `published`.

---

## Appeals and removals

See [Removing Entries](removal.md) for full details on the `/case remove` command.
