# OSA Bot Documentation

Welcome to the official documentation for the **Office of Self-Accountability** Discord bot — a custom-built moderation and database management bot for the OSA community.

---

## What does OSA Bot do?

OSA Bot is the backbone of OSA's operations. It handles:

- **Tickets** — a fully configurable ticket system with custom types, form fields, per-type categories, and staff role permissions
- **Investigations** — a case pipeline for tracking subjects from initial report through to publication or appeal
- **Database** — a forum-based public record of published offenders, with bulk upload, lookups, and update tools
- **Logging** — per-module structured log channels for tickets, cases, database events, and errors

---

## Quick navigation

<div class="grid cards" markdown>

-   :material-cog: **Getting Started**

    ---

    Set up the bot from scratch — hosting, config, and permissions.

    [:octicons-arrow-right-24: Setup guide](setup/hosting.md)

-   :material-ticket: **Ticket System**

    ---

    Configure ticket types, form fields, categories, and staff roles.

    [:octicons-arrow-right-24: Ticket docs](tickets/overview.md)

-   :material-magnify: **Investigations**

    ---

    Open and manage investigation cases through the full pipeline.

    [:octicons-arrow-right-24: Case docs](cases/overview.md)

-   :material-database: **Database**

    ---

    Submit, update, search, and bulk-upload database entries.

    [:octicons-arrow-right-24: Database docs](database/overview.md)

</div>

---

## Bot at a glance

| Module | Key Commands |
|--------|-------------|
| Tickets | `/ticket panel`, `/ticket list`, `/ticketadmin type create` |
| Investigations | `/case create`, `/case view`, `/case list`, `/case publish` |
| Database | `/submit`, `/lookup`, `/update`, `/bulk` |
| Config | `/config set`, `/config view` |

---

!!! info "Staff vs Admin"
    Throughout this documentation, **Staff** refers to members with the configured Staff Role, and **Admin** refers to members with the configured Admin Role. Most commands require Staff. Configuration commands require Admin.
