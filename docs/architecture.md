## Architecture

How this blueprint is put together, at the level of "what talks to
what". One section heading per concern — keep each short, with a
diagram when it helps.

This section is rendered as the **Architecture** block on the
AnyGivenMonday detail page. It comes *after* the README's About
section and the picture cloud, so you can refer to the technologies
shown there by name without re-introducing them.

### Components

For each major component (service / library / data store / external
dependency), one paragraph:

- **What it is** in one phrase.
- **What it does** in this blueprint.
- **Why this one** versus an obvious alternative (one sentence).

Example shape:

> **PostgreSQL** — the primary store. Holds blueprints, users,
> sessions. Picked over MongoDB because the relational shape
> dominates this domain (joins on users × sessions × audit logs).

### Data flow

How information moves between components. A short ASCII diagram or
a numbered list both work. Prefer a numbered list if there are
fewer than ~5 hops; prefer a diagram if there are loops or
branching.

```text
[client] → [nginx] → [gunicorn] → [Django] → [Postgres]
                          │
                          └────── [Redis] (cache)
```

### Boundaries

What this blueprint **does not** include — services it expects to
exist elsewhere (DNS, identity provider, payment gateway, ...) or
deliberate non-goals (no horizontal scaling, no multi-region, etc.).

### Trade-offs

The 1-3 most important judgement calls and what they cost. Helps
the reader decide whether to clone or to pick a different
blueprint:

- *Trade-off* — "we chose X over Y because Z; the cost is W".

---

This file is optional. Delete it if the blueprint is small enough
that the README alone covers the architecture (the detail page just
skips this section if the file is missing or empty).
