# Blueprint title goes here

> One-line elevator pitch: what is this blueprint, who is it for, what
> problem does it solve. Keep this single line — it's the lead the
> AnyGivenMonday detail page displays under the title.

## About

A few paragraphs (2-4) describing the blueprint at a higher level:

- The kind of project this is a starting point for.
- The shape of the architecture in one sentence.
- The mental model — "this is the X for Y" framing.
- Why someone would clone this rather than start from a blank repo.

Keep it readable to a developer who is *evaluating* whether the
blueprint fits their need, not yet to a developer who has decided to
clone. Decision-making content here; how-to content lives in
`docs/setup.md`.

## When to use this

A short bulleted list of situations the blueprint fits:

- Use case 1.
- Use case 2.
- Use case 3.

## When NOT to use this

Equally short. Honest about the boundaries:

- Anti-use-case 1.
- Anti-use-case 2.

## What's in this repo

A short tree-like summary if the repo carries code, or a sentence
explaining "this is descriptive only" if it doesn't.

For a code-bearing blueprint:

```text
.
├── README.md              ← this file
├── docs/
│   ├── architecture.md    ← rendered as the "Architecture" section
│   ├── setup.md           ← rendered as the "Setup" section
│   └── deploy.md          ← rendered as the "Deploy" section
├── src/                   ← the implementation (when present)
├── tests/                 ← the test suite (when present)
└── .github/workflows/     ← CI + audit
```

For a description-only blueprint, simplify to:

```text
.
├── README.md
└── docs/
    ├── architecture.md
    └── setup.md           ← not always populated
```

## Status

Pick one:

- **Description-only**: this blueprint exists as an idea + stack
  description. No runnable code yet. The AnyGivenMonday detail page
  hides the "View on GitHub" CTA for these.
- **Reference implementation**: code, tests, and (where applicable)
  deploy pipeline are in place and verified. The detail page links
  here.

---

This README is fetched live by the AnyGivenMonday detail page for
this blueprint and rendered under the **About** section. Keep the
H1 (`# Blueprint title`) as the first line — the site discards it
because the title is already displayed from the database.
