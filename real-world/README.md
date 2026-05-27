# Real-world fixtures

Captured snapshots of QuantEcon lecture pages that exposed theme bugs. Each
file preserves a specific failure mode so it becomes a permanent regression
check.

## When to add a fixture

Add a real-world fixture whenever:

- A lecture page renders incorrectly in the theme (layout breakage, overflow,
  spacing, dark-mode artefacts, etc.).
- A bug fix in the theme is hard to verify with synthetic content alone — the
  real page has interactions between directives that the synthetic pages miss.
- A community member reports a rendering issue and links to a specific page.

The fixture stays in this repo even after the original lecture gets refactored
upstream. The point is to preserve the *problematic state* as a test case.

## Capture workflow

1. Identify the smallest source file that reproduces the issue.
2. Find the source `.md` / `.ipynb` in the upstream lecture repo (not the
   rendered HTML).
3. Copy into `real-world/from-<source-repo>/<page-name>.{md,ipynb}`.
4. Prepend the **attribution header** (template below).
5. Sanitize:
   - Replace `{doc}\`...\`` cross-references with placeholder links (see below).
   - Replace `{ref}\`...\`` labels that point outside the fixture with plain text.
   - Strip notebook outputs if it's a `.ipynb` (reduces churn in `_build/html/`).
   - Trim aggressively if the file is large — keep only the section that
     triggered the bug, plus enough surrounding context to render naturally.
6. Add the file to `_toc.yml`.
7. Run `jb build .` locally and confirm:
   - No new myst-parser warnings introduced by the fixture.
   - The page renders, and the original bug is reproduced (or fixed, post-fix).
8. Commit, push, and reference in the theme PR that uses it.

## Attribution header template

Prepend this as a HTML comment (or `% ... %` for myst) at the top of every
real-world fixture, so its provenance is traceable:

```markdown
<!--
Real-world fixture: <page name>
Source:   https://github.com/QuantEcon/<source-repo>/blob/<sha>/<path>
Site:     https://<site-name>.quantecon.org/<page>.html
Captured: 2026-05-27
Issue:    <theme issue / PR that triggered capture>
Notes:    <one-line description of what this page exercises in the theme>

Sanitization:
  - {doc} refs replaced with placeholder links
  - Notebook outputs stripped
  - Sections X, Y trimmed (kept Z for reproduction)
-->
```

## Sanitization conventions

### `{doc}` cross-references

`{doc}` references to other lecture pages will not resolve here and emit
"unknown document" warnings during the build. Replace with a markdown link to
a placeholder anchor on the same page, preserving the link text:

```
Before:  See {doc}`linear_models` for background.
After:   See [linear_models](#placeholder-linear-models) for background.
```

Then add a single placeholder section at the bottom of the file:

```markdown
## Placeholder references

The following anchors stand in for cross-references to other lectures in the
original site, so myst-parser does not emit "unknown document" warnings:

(placeholder-linear-models)=
**linear_models** — placeholder for cross-reference.

(placeholder-multivariate-normal)=
**multivariate_normal** — placeholder for cross-reference.
```

### `{ref}` labels pointing outside the fixture

If a `{ref}` target is defined elsewhere (different lecture file), replace with
plain emphasis to avoid the warning:

```
Before:  See {ref}`eq:something` above.
After:   See *eq:something* above.
```

If the target is defined in *this* file, leave it alone — it will resolve fine.

### Bibliography / citations

`{cite}` references without a matching `references.bib` will warn. Either:
- Strip the citation directive, leaving the surrounding text intact, or
- Add a minimal stub `references.bib` to this directory with the cited keys.

## Naming

- `from-<source-repo>/` — preserves provenance at a directory level.
- `<page-name>.{md,ipynb}` — keep the original filename so it's easy to
  cross-reference with the live site.

Example: `from-lecture-python/prob_matrix.md` corresponds to
`https://python.quantecon.org/prob_matrix.html`.

## Current fixtures

| File | Source | Captured | Why |
|------|--------|----------|-----|
| `from-lecture-python/prob_matrix.md` | python.quantecon.org/prob_matrix.html | 2026-05-27 | Long page with mixed math, code, and tables — exercises RHS TOC overflow and content-region spacing |
