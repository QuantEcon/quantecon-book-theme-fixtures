# Admonitions

Tests the full set of admonition styles, plus custom titles and dropdown
(togglebutton) behaviour.

## Note

```{note}
This is a standard note. It contains a paragraph of prose, **bold** and
*italic* emphasis, and `inline code`.
```

## Warning

```{warning}
A warning admonition signals that something can go wrong. It should render
with a distinct (typically amber or red) accent.
```

## Tip

```{tip}
A tip is a softer call-out — often used for "good to know" pointers that
aren't strictly necessary to read.
```

## Important

```{important}
An important admonition flags information the reader should not skip over.
```

## Danger

```{danger}
A danger admonition signals critical risk — typically rendered with the
strongest red treatment.
```

## Attention

```{attention}
An attention admonition. Visually similar to warning in most themes but
semantically distinct.
```

## Caution

```{caution}
A caution admonition.
```

## Error

```{error}
An error admonition, often used inline to flag code-like failure cases.
```

## Hint

```{hint}
A hint admonition. Common in exercises to nudge the reader without giving
away the answer.
```

## Seealso

```{seealso}
A seealso admonition points to related material. Often contains links.

- [The math fixture](./math.md)
- [The cross-references fixture](./cross-references.md)
```

## Custom title

```{admonition} A custom title goes here
:class: tip

The `admonition` directive with an explicit title and class is a flexible
escape hatch when the built-in categories don't fit.
```

## Dropdown (sphinx-togglebutton)

```{admonition} Click to reveal
:class: dropdown

This admonition is collapsed by default. The dropdown chevron should render
in the title bar, and the body should expand on click without layout shift
elsewhere on the page.
```

## Admonition with rich content

````{note}
Admonitions can contain rich content:

- Lists
- `inline code`
- Math like $e^{i\pi} + 1 = 0$
- Code blocks:

  ```python
  print("hello from inside an admonition")
  ```

- And links to [other pages](./typography.md).
````

## Multiple admonitions in sequence

```{tip}
First admonition.
```

```{warning}
Second admonition immediately after — vertical spacing between adjacent
admonitions matters.
```

```{note}
Third admonition.
```
