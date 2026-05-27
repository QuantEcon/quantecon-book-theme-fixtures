# Typography

This page exercises the theme's prose styling: headings, inline emphasis,
lists, blockquotes, horizontal rules.

## Headings

### Third-level heading

#### Fourth-level heading

##### Fifth-level heading

###### Sixth-level heading

## Paragraphs and inline emphasis

This is a regular paragraph with **bold text**, *italic text*, ***bold and
italic text***, ~~strikethrough~~, and `inline code`. The mix of weights and
slants should sit on the baseline without disrupting line spacing.

Links should be distinguishable: [an external link](https://www.quantecon.org)
and [a relative link](./math.md) ought to render with the theme's link colour
and underline style.

Footnotes attach inline[^example] and resolve at the bottom of the page.

[^example]: This is a footnote — see the cross-references page for a richer
    test.

## Blockquotes

> A single-line blockquote.

> A multi-paragraph blockquote.
>
> The second paragraph follows the first, with its own line spacing and the
> theme's left-border treatment.
>
> > A nested blockquote, indented one level deeper, exercises border-on-border
> > rendering and any background-tint stacking.

## Unordered lists

- First item
- Second item with **bold** and *italic*
- Third item
  - Nested item
  - Another nested item
    - Doubly nested
- Fourth item

## Ordered lists

1. First step
2. Second step
   1. Sub-step
   2. Another sub-step
3. Third step

## Mixed nested lists

1. Ordered top-level
   - Unordered nested
   - Another unordered nested
     1. Ordered doubly nested
2. Second ordered item

## Task lists

- [x] A completed task
- [ ] A pending task
- [x] Another completed task with `inline code` and **bold**

## Horizontal rule

Above the rule.

---

Below the rule.

## Long paragraph

This paragraph deliberately runs long to test line-height, justification, and
wrapping behaviour across the theme's content column width. The quick brown
fox jumps over the lazy dog, and continues to jump over many more lazy dogs,
each lazier than the last, until the line wraps and the paragraph continues
on the following line. The width of the content column, the chosen typeface,
and the line-height interact to determine whether this paragraph reads
comfortably or feels cramped — visual snapshots here surface regressions in
any of those dimensions.
