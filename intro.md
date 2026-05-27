# QuantEcon Book Theme Fixtures

This site is the **frozen rendering target** for visual regression tests and
Netlify preview deploys of [`quantecon-book-theme`](https://github.com/QuantEcon/quantecon-book-theme).

It contains two parts:

- **Synthetic fixtures** — minimal pages, one per theme surface (typography,
  code blocks, math, admonitions, tables, etc.).
- **Real-world fixtures** — frozen snapshots of QuantEcon lectures that
  triggered theme bugs, preserved as permanent regression cases.

Use this site to:

1. Eyeball the impact of a theme PR (the Netlify preview link in the PR).
2. Run Playwright visual regression tests against a stable target.
3. Track edge cases over time — the gallery grows with the bug history.

For contribution conventions, see `README.md` in the repository root.
