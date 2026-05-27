# quantecon-book-theme-fixtures

A curated jupyter-book site used as the **single, stable target** for:

1. Visual regression tests of [`quantecon-book-theme`](https://github.com/QuantEcon/quantecon-book-theme)
2. Netlify preview deploys on theme pull requests (the "group review gallery")
3. A growing corpus of edge cases captured from real QuantEcon lectures

Because the content here doesn't move under the theme repo's CI (the theme
pins to a specific fixtures SHA, rather than pulling from a moving lecture
repo each run), every visual diff in a theme PR is attributable to a theme
change — not to upstream content edits.

## Layout

```
quantecon-book-theme-fixtures/
├── _config.yml              # jupyter-book config (extensions, MathJax macros)
├── _toc.yml                 # table of contents
├── intro.md                 # landing page
├── requirements.txt         # pinned jupyter-book + extension versions
├── synthetic/               # minimal, surface-specific pages
│   ├── typography.md        # h1-h6, bold, italic, lists, blockquotes
│   ├── definition-lists.md  # dl / glossary / field-list
│   ├── code-blocks.md       # syntax highlighting, f-strings, captions
│   ├── math.md              # MathJax: inline, display, aligned, numbered
│   ├── admonitions.md       # note/warning/tip/important/danger/dropdown
│   ├── exercises.md         # sphinx-exercise directives
│   ├── proofs.md            # sphinx-proof directives
│   ├── tables.md            # basic, list-table, grid-table
│   ├── figures.md           # images, captions, alignment, video
│   ├── toc-deep-nesting.md  # stress RHS "On this page" overflow (#387)
│   ├── long-page.md         # stress LHS sidebar scrolling
│   └── cross-references.md  # internal refs, footnotes, anchors
└── real-world/              # captured snapshots of lectures that broke things
    ├── README.md            # capture workflow + header convention
    └── from-<source-repo>/
        └── <descriptive-name>.{md,ipynb}
```

## Build flow

The fixtures site is **rebuilt from source on every CI run** in the theme repo
(it is small enough — ~13 pages — that the build takes ~30–60s with pip-only
installs). Pre-built HTML is **not** committed.

This keeps the model simple:

- The theme repo's CI checks out this fixtures repo at a pinned SHA,
  `pip install`s the requirements, `pip install`s the theme PR under test, and
  runs `jb build .`.
- No asset-overlay logic, no committed `_build/html/` to keep in sync.
- The *input* doesn't change between theme PRs (the theme repo pins to a
  fixtures SHA), so visual diffs reflect theme changes only.

To build locally:

```bash
pip install -r requirements.txt
pip install quantecon-book-theme        # or pip install -e ../quantecon-book-theme
jb build .
open _build/html/index.html
```

## Adding fixtures

### Synthetic page

Pick a theme surface that isn't covered yet (or is under-covered). Create one
file under `synthetic/` that exercises *only* that surface — small enough to
debug when something breaks. Add it to `_toc.yml`.

### Real-world page

Capture when a real lecture breaks in the theme. See
[`real-world/README.md`](real-world/README.md) for the header convention and
sanitization requirements (`{doc}`, `{ref}`, `{cite}` need careful handling
to avoid myst-parser warnings).

## Updating snapshots in the theme repo

After changing fixtures, the theme repo's Playwright baselines will diverge.
Open a PR in `quantecon-book-theme` that pins to the new fixtures SHA, then
comment `/update-snapshots` on that PR.

## Migrating the theme repo to use this fixtures repo

See [`MIGRATION.md`](MIGRATION.md) for the step-by-step plan to switch
`quantecon-book-theme`'s CI over from `lecture-python-programming` to this
repo.

## Relationship to `lecture-python-programming`

The full `lecture-python-programming` build is still useful as a **nightly
integration smoke test** to catch jupyter-book / sphinx version drift. That
lives in the theme repo as a non-blocking workflow; this fixtures repo is for
fast per-PR feedback.
