## Setup

How to actually get this blueprint running. Only populate this file
once the repo carries runnable code — for description-only
blueprints, delete the file or leave the placeholder note.

This section is rendered as the **Setup** block on the
AnyGivenMonday detail page. Keep instructions self-contained: a
developer arriving here should be able to clone and run without
chasing other docs.

### Prerequisites

What needs to be installed on the developer's machine *before*
cloning:

- Tool A version `>=X` — link to install page.
- Tool B version `>=Y`.
- Optional: a credential or account elsewhere.

### Clone and bootstrap

```bash
git clone https://github.com/<org>/<repo>.git
cd <repo>
cp .env.example .env   # fill in the values listed below
```

### Required environment variables

The minimum set to bring the project up:

| Variable           | Purpose                                | Example                              |
| ------------------ | -------------------------------------- | ------------------------------------ |
| `EXAMPLE_VAR`      | What it does                           | `value`                              |
| `SECRET_KEY`       | Cryptographic signing                  | (long random string)                 |

### Run

```bash
docker compose up
```

App should be available at `http://localhost:8000` (or wherever
the compose file exposes the port).

### Run tests

```bash
docker compose exec web pytest
```

### Common gotchas

A short list of the 2-3 things that trip up first-time users. Pull
these from real feedback — don't invent imaginary problems.

- Gotcha 1.
- Gotcha 2.

---

This file is optional. If the blueprint has no runnable code yet,
leave the file out (or replace this content with one line:
`Setup instructions arrive when the blueprint ships a reference
implementation`).
