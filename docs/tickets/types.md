# Managing Ticket Types

Ticket types are the categories users can select from the panel dropdown. They are stored per-server in the database and fully configurable.

---

## Creating a type

```
/ticketadmin type create
```

A modal opens with the following fields:

| Field | Description | Limit |
|-------|-------------|-------|
| Type key | Internal identifier, lowercase, no spaces (e.g. `report`) | 30 chars |
| Display label | Shown in the dropdown (e.g. `Degeneracy Report`) | 30 chars |
| Short description | Shown under the label in the dropdown | 100 chars |
| Emoji | Shown next to the label | Any emoji |
| Intro message | Shown in the ticket welcome message | 1000 chars |

---

## Editing a type

```
/ticketadmin type edit type_key:report
```

Opens the same modal pre-filled with current values.

---

## Deleting a type

```
/ticketadmin type delete type_key:report
```

!!! warning
    Deleting a type also removes all its form fields and staff role assignments. Existing tickets are unaffected.

---

## Enabling and disabling

```
/ticketadmin type toggle type_key:report enabled:True
/ticketadmin type toggle type_key:report enabled:False
```

Disabled types are hidden from the panel dropdown. Existing tickets using that type are unaffected.

---

## Reordering

Types appear in the dropdown in their `sort_order`. Set positions with:

```
/ticketadmin type reorder type_key:report position:1
/ticketadmin type reorder type_key:appeal position:2
```

Re-post the panel after reordering for changes to take effect.

---

## Per-type categories

By default all ticket channels go into the global category set in `/config set → Ticket Category ID`. You can override this per type:

```
/ticketadmin type setcategory type_key:appeal category:@Appeals Category
/ticketadmin type clearcategory type_key:appeal
```

---

## Form fields

Add up to 5 form fields to a ticket type. When a user selects that type, a modal opens with your fields before the ticket is created.

```
/ticketadmin form add type_key:report
/ticketadmin form list type_key:report
/ticketadmin form remove type_key:report field_number:2
```

Form field options:

| Option | Description |
|--------|-------------|
| Label | Question text shown in the modal |
| Placeholder | Ghost text shown inside the input |
| Style | `short` (single line) or `paragraph` (multi-line) |
| Required | Whether the field must be filled |
| Max length | Character limit, up to 1000 |

!!! tip
    Form responses are saved to the ticket and shown in the ticket log channel when the ticket opens.

---

## Staff role assignments

By default, ticket channels give access to the global Staff and Admin roles. You can assign specific roles per ticket type:

```
/ticketadmin staffrole set type_key:report role:@Investigators level:senior
/ticketadmin staffrole remove type_key:report role:@Investigators
/ticketadmin staffrole list type_key:report
```

Permission levels: `viewer`, `handler`, `senior` — see [Permissions](../setup/permissions.md) for what each allows.

---

## Listing all types

```
/ticketadmin type list
```

Shows all configured types with their status (enabled/disabled), description, and assigned category.
