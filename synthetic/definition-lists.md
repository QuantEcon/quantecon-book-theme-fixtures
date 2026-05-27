# Definition lists

The `lecture-python-programming` site doesn't contain `<dl>` elements, so the
existing visual test suite has no coverage for definition-list styling. This
page fills that gap.

## MyST definition list

Term 1
: Definition of the first term. Paragraph text here can be long enough to wrap
  across multiple lines, which exercises the hanging-indent treatment.

Term 2
: Definition of the second term.
: A second definition for the same term — definition lists support multiple
  definitions per term.

Term with **bold**
: Definition with *italic*, `inline code`, and a [link](https://www.quantecon.org).

## Multi-paragraph definitions

Composite term
: First paragraph of the definition.

  Second paragraph of the definition, still indented at the same level. The
  blank line between paragraphs needs to render with consistent spacing.

  - Nested list inside a definition
  - Another nested item

## Glossary block

```{glossary}
random variable
  A measurable function from a probability space to a measurable space, often
  taking values in $\mathbb{R}$.

probability distribution
  An assignment of probabilities to events in a measurable space.

joint distribution
  The probability distribution of two or more random variables considered
  together; written $F(x, y) = \Pr(X \le x, Y \le y)$.

marginal distribution
  The distribution of a single random variable extracted from a joint
  distribution by integrating (or summing) out the others.
```

## Field list

:author: A. Researcher
:date: 2026-05-27
:keywords: typography, definition lists, theme regression
:status: draft

A field list typically appears at the top of a structured document. The theme
should render the field names with consistent weight and alignment to their
values.

## Short definitions in sequence

A
: First letter of the alphabet.

B
: Second letter.

C
: Third letter.

D
: Fourth letter.

Short single-line definitions should pack tightly without excessive vertical
gap between entries.
