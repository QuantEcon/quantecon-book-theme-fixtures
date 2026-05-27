# Cross-references

Tests internal links, in-page anchors, footnotes, and numbered references to
labelled equations, figures, tables, and theorems.

## In-page links

Anchors below are defined with myst `(label)=` syntax. Each label can be
linked with a plain markdown link to its hash:

- [Jump to Section X](#section-x)
- [Jump to Section Y](#section-y)
- [Jump to Section Z](#section-z)

(section-x)=

## Section X

This section is the target of an in-page link.

(section-y)=

## Section Y

This section is the target of an in-page link.

(section-z)=

## Section Z

This section is the target of an in-page link.

## Cross-page links

- [Math fixture](./math.md)
- [Code blocks fixture](./code-blocks.md)
- [Admonitions fixture](./admonitions.md)

## External links

- [QuantEcon](https://www.quantecon.org)
- [jupyter-book](https://jupyterbook.org)
- [Sphinx](https://www.sphinx-doc.org/)

## Numbered equation reference

$$
e^{i\pi} + 1 = 0
$$ (eq:euler)

Equation {eq}`eq:euler` is Euler's identity.

## Numbered figure reference

(See the [figures](./figures.md) page for figure cross-references via
`{numref}`.)

## Footnotes

This sentence has a footnote.[^note1] So does this one.[^note2] A third
sentence with another footnote.[^note3]

The same footnote can be cited again later.[^note1]

[^note1]: First footnote. Footnotes appear at the bottom of the page,
    numbered automatically.

[^note2]: Second footnote, with **bold**, *italic*, and `inline code`.
    Footnotes can span multiple lines as long as continuation lines are
    indented.

[^note3]: Third footnote, with a [link inside](./typography.md).

## Anchors and labels mixed

(named-anchor)=

### A subsection with an anchor

Linkable via [its label](#named-anchor).

## Link styling in prose

When a paragraph contains [several](#section-x) [links](#section-y)
[next](#section-z) to each other, the theme's underline + colour treatment
should remain readable. Inline `code` next to a [link](#section-x) and
**bold** [link text](#section-y) should also be visually distinct.
