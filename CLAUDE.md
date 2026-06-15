# CLAUDE.md — Blueprint repo instructions

This is a **blueprint repo**, cloned from
`anygivenmonday/blueprint-template`. It hosts the descriptive
content + (optionally) the reference implementation for ONE
blueprint of the AnyGivenMonday catalog.

Read and apply these rules at the start of every Claude Code
session in a blueprint repo.

## What this repo is

- A self-contained public GitHub repo.
- Source of truth for the blueprint's **descriptive markdown**
  (README.md, docs/*.md), fetched live and rendered by the
  AnyGivenMonday detail page at `/blueprints/<slug>/`.
- Optionally, a runnable **reference implementation** with code,
  tests, and a deploy flow.

## What this repo is NOT

- Not a Django project. Do not run `python manage.py ...` here.
- Not the meta-site source. The meta-site lives in a separate
  repo (`anygivenmonday`); this repo is just consumed by it.
- Not authoritative for the blueprint's **structural metadata**
  (title, slug, category, technologies, publish flag) — those
  live in the meta-site's database and are edited from
  `/editor/`. This repo only owns the *descriptive content*.

## Language

- **Markdown files**: English.
- **Code**: English identifiers and comments, regardless of
  prompt language.
- **Chat responses**: match the user's prompt language.

## File conventions

| File                       | Required? | What it renders to on the detail page         |
| -------------------------- | --------- | --------------------------------------------- |
| `README.md`                | yes       | "About" section                                |
| `docs/architecture.md`     | optional  | "Architecture" section (skipped if missing)    |
| `docs/setup.md`            | optional  | "Setup" section (skipped if missing)           |
| `docs/deploy.md`           | optional  | "Deploy" section (skipped if missing)          |

If a file isn't there, the corresponding section doesn't render.
That's fine — description-only blueprints often only ship a
README.

## Markdown rules

- **CommonMark** dialect. The meta-site renders with
  `markdown-it-py` then sanitizes with `bleach`.
- **No raw HTML** — `bleach` strips it. Use markdown for every
  formatting need.
- **Code fences** with a language tag for highlighting:
  ` ```python `, ` ```bash `, ` ```yaml `, etc.
- **First-level heading** in `README.md` is the blueprint title.
  The meta-site discards it (the title is already shown from
  the database). Inside `docs/*.md`, start sections at H2
  (`##`) — the meta-site already shows an H2 header for the
  section ("Architecture", "Setup", "Deploy"), so your file
  contents render under it.
- **Relative links** to other files in this repo: write them as
  relative; the meta-site rewrites them to absolute GitHub URLs
  at render time.
- **Images**: inline images aren't supported yet. Link to an
  image hosted elsewhere (e.g., a screenshot already published
  in a GitHub Issue or Discussion) if you need one.

## Workflow

When the user opens this repo in a Claude session (typically
alongside the meta-repo `anygivenmonday/`):

1. **Identify the state**: is the blueprint description-only or
   does it carry code? Check for `src/` or equivalent.
2. **Help edit the `.md` files** following the conventions above.
   For empty / placeholder sections, offer to draft content
   based on the user's description.
3. **For code-bearing blueprints**: also help with code, tests,
   `.github/workflows/test.yml`, etc.
4. **Don't touch `LICENSE`** unless the user explicitly asks.
5. **Don't update meta-site assumptions**: e.g., don't add a
   field to "what the meta-site fetches" — that requires a
   matching change in the meta-repo (`anygivenmonday`).

## After editing

- Commit + push as the user requests.
- The meta-site picks up changes within ~5 minutes via its
  short-TTL cache, or instantly if the curator clicks "Refresh"
  in the editor.

## License

MIT. Don't change unless the user explicitly requests it.

## Reference

The full template + workflow spec lives in the meta-repo at
`docs/blueprint_repos.md`. If anything here conflicts with that
document, the meta-repo wins (this file is a copy maintained to
travel with each blueprint clone).
