# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code for this user.

The following preferences follow MoSCoW prioritization:
- **Must** - non-negotiable, essential
- **Should** - important but not critical; high value if it makes sense for the context
- **Could** - desirable but less important; nice-to-haves
- **Won't** - do not do

## Agent preferences
- When creating plans, the filename **must** be representative of the plan being created. The filename **must also** have the date of the plan in `YYYY-MM-DD`. The name _should_ strive to be three-to-five words separated by dashes:
  - **Do not**: `agile-painting-clarke.md`, `eager-splashing-liskov.md`
  - **Do**: `2025-01-24-add-isolation-forest-for-anomoly-detection.md`, `2025-01-24-add-k-means-clustering.md`
- You must always use inclusive language; e.g., `allowlist` / `blocklist`, `primary` / `replica`, `placeholder` / `example`, `main` branch, `conflict-free`, `concurrent` / `parallel`
- When in a project that has a Docker file or `docker-compose.yaml`, you should prefer `docker` commands to bare-metal commands:
  - **Do not**: `npm install`
  - **Do**: `docker compose exec app npm install`

## Tool preferences
- You must use `rg` instead of `grep`
- You must use `fd` instead of `find`
- You must use `gh` when presented with a GitHub URL
- `tree` is installed
- `websocat` is installed

## General development preferences
- You should prefer "outside-in" test-driven development. Start with an integration test--using either an API call, e.g. GraphQL, or a Controller call--then, if the test calls a method that is complicated, drop down to a unit test to test this method.

## Database preferences
### Table preferences
- Table names must use plural `snake_case`, snake_case names, e.g. `users`, `posts`, etc.
- Column names must use `snake_case` for field names within the database.

### Column preferences
- Timestamp columns must follow the convention `*_at`, e.g. `created_at`, `updated_at`, `deleted_at`, etc.
- Columns representative of boolean values must follow the convention `is_*` or `has_*`, e.g. `is_admin`, `has_access`, etc.
- Foreign references must follow the convention of the entity name + `_id`, e.g. `user_id`, `post_id`, etc.
- `id` columns should prefer UUID v7
