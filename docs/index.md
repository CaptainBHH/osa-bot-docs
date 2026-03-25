# OSA Bot Documentation

Welcome to the official documentation for the **Office of Self-Accountability** Discord bot.

---

## What does OSA Bot do?

OSA Bot manages OSA's core operations directly within Discord:

- :ticket: **Tickets** — A configurable ticket system with custom types, form fields, per-type categories, and staff role permissions
- :mag: **Investigations** — A case pipeline for tracking subjects from initial report through to publication
- :card_file_box: **Database** — A public forum-based record of published entries with search, updates, and bulk upload
- :bell: **Logging** — Structured log channels per module for tickets, cases, database events, and errors

---

## Quick navigation

<div class="grid cards" markdown>

-   :gear: **Configuration**

    ---

    Configure channels, roles, log channels, and integrations.

    [:octicons-arrow-right-24: Config guide](config/setup.md)

-   :ticket: **Ticket System**

    ---

    Configure ticket types, form fields, categories, and staff roles.

    [:octicons-arrow-right-24: Ticket docs](tickets/overview.md)

-   :mag: **Investigations**

    ---

    Open and manage investigation cases through the full pipeline.

    [:octicons-arrow-right-24: Case docs](cases/overview.md)

-   :card_file_box: **Database**

    ---

    Submit, update, search, and bulk-upload database entries.

    [:octicons-arrow-right-24: Database docs](database/overview.md)

</div>

---

## Bot at a glance

| Module | Key Commands |
|--------|-------------|
| Config | `/config set`, `/config view` |
| Tickets | `/ticket panel`, `/ticket list`, `/ticketadmin type create` |
| Investigations | `/case create`, `/case view`, `/case list`, `/case publish` |
| Database | `/submit`, `/lookup`, `/update`, `/bulk` |

---

!!! info "Staff vs Admin"
    Throughout this documentation, **Staff** refers to members with the configured Staff Role, and **Admin** refers to members with the configured Admin Role. Most commands require Staff. Configuration commands require Admin.
