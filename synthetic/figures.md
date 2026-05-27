# Figures

Tests image rendering, figure captions, alignment, and video embeds. Images
reference the jupyter-book example placeholder hosted in the docs, so no
binary assets need to live in this repo.

## Simple inline image

![QuantEcon logo placeholder](https://quantecon.org/assets/img/qe-logo.png)

## Figure with caption (markdown)

![A figure caption underneath](https://quantecon.org/assets/img/qe-logo.png)
*Figure: a caption rendered as italic prose beneath the image.*

## `figure` directive with label

```{figure} https://quantecon.org/assets/img/qe-logo.png
:name: fig:qe-logo
:alt: QuantEcon logo
:width: 200px

The QuantEcon logo. Referenced as {numref}`fig:qe-logo` in prose.
```

A reference to {numref}`fig:qe-logo` should resolve to "Fig. 1" or similar.

## Figure with alignment

```{figure} https://quantecon.org/assets/img/qe-logo.png
:align: center
:width: 150px

A centred figure.
```

```{figure} https://quantecon.org/assets/img/qe-logo.png
:align: left
:width: 100px

A left-aligned figure. Surrounding text should flow if the theme supports
floats, or sit below if not — either is acceptable, but should be consistent.
```

This paragraph follows a left-aligned figure to test text-wrap behaviour.

## Multiple figures side-by-side

```{figure} https://quantecon.org/assets/img/qe-logo.png
:width: 100px
:align: left

Left figure.
```

```{figure} https://quantecon.org/assets/img/qe-logo.png
:width: 100px
:align: right

Right figure.
```

Lorem ipsum text between, to clear any floats.

## YouTube embed (sphinxcontrib-youtube)

```{youtube} dQw4w9WgXcQ
:width: 480
:height: 270
```

The embed should render with a 16:9 aspect-ratio container that scales to the
content column width on narrow viewports.

## Image inside a list

1. First step:
   ![logo](https://quantecon.org/assets/img/qe-logo.png)
2. Second step.
3. Third step.

## Image with very long caption

```{figure} https://quantecon.org/assets/img/qe-logo.png
:width: 200px

A deliberately long figure caption to exercise multi-line caption layout: the
caption should wrap below the image with consistent line-height and indent.
If the theme indents captions, the second and subsequent lines should align
with the first.
```
