# Tables

Tests basic markdown tables, list-tables, grid-tables, alignment, and tables
with captions/labels.

## Basic markdown table

| Symbol | Meaning             | Units    |
|--------|---------------------|----------|
| $v$    | velocity            | m/s      |
| $a$    | acceleration        | m/s²     |
| $F$    | force               | N        |
| $E$    | energy              | J        |

## Table with column alignment

| Left-aligned | Centred | Right-aligned |
|:-------------|:-------:|--------------:|
| A            | B       | C             |
| longer text  | mid     | right         |
| short        | x       | 1234567890    |

## Numerical table

| n    | $\sqrt{n}$ | $n^2$  | $\log n$ |
|------|------------|--------|----------|
| 1    | 1.0000     | 1      | 0.0000   |
| 2    | 1.4142     | 4      | 0.6931   |
| 3    | 1.7321     | 9      | 1.0986   |
| 10   | 3.1623     | 100    | 2.3026   |
| 100  | 10.0000    | 10000  | 4.6052   |

## list-table

```{list-table} A list-table with header row
:header-rows: 1
:widths: 25 25 50

* - Column A
  - Column B
  - Column C (wider)
* - Row 1, A
  - Row 1, B
  - Row 1, C — this cell contains a longer block of text to test wrapping.
* - Row 2, A
  - Row 2, B
  - Row 2, C, with **bold** and `code`.
* - Row 3, A
  - Row 3, B
  - Row 3, C.
```

## Table with caption and label

```{table} Sample statistics from three runs.
:name: tab:sample-stats

| Run | $\bar{x}$ | $s^2$  | $n$ |
|-----|-----------|--------|-----|
| 1   | 2.13      | 0.85   | 100 |
| 2   | 2.08      | 0.91   | 100 |
| 3   | 2.20      | 0.78   | 100 |
```

See {numref}`tab:sample-stats` for the summary.

## Wide table

| col1 | col2 | col3 | col4 | col5 | col6 | col7 | col8 | col9 |
|------|------|------|------|------|------|------|------|------|
| a    | b    | c    | d    | e    | f    | g    | h    | i    |
| 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    |

A table wider than the content column tests horizontal scrolling / overflow
treatment.

## Table inside an admonition

```{note}
Tables can appear inside admonitions:

| Key | Value |
|-----|-------|
| a   | 1     |
| b   | 2     |
| c   | 3     |
```
