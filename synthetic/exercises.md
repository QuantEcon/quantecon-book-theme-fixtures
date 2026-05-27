# Exercises

Tests `sphinx-exercise` directives: `exercise`, `exercise-start`/`-end`, and
`solution-start`/`-end` (the form used heavily in QuantEcon lectures).

## Plain exercise

```{exercise}
:label: ex:basic

Prove that for any two events $A$ and $B$,
$\Pr(A \cup B) = \Pr(A) + \Pr(B) - \Pr(A \cap B)$.
```

## Exercise with multi-paragraph content

```{exercise}
:label: ex:multi

Consider a sequence of independent coin flips, each with probability $p$ of
landing heads.

Let $X$ be the number of heads in the first $n$ flips. Show that
$X \sim \text{Binomial}(n, p)$ and compute its mean and variance.

State your assumptions clearly.
```

## Exercise with code-block prompt

````{exercise}
:label: ex:code

Write a Python function that computes the sample mean and sample variance of
a list of floats in a single pass, using Welford's algorithm.

The signature should be:

```python
def welford(xs: list[float]) -> tuple[float, float]:
    ...
```
````

## Exercise + solution pair (start/end form)

```{exercise-start}
:label: ex:pair
```

Compute $\sum_{k=1}^{n} k = ?$ in closed form.

```{exercise-end}
```

```{solution-start} ex:pair
:class: dropdown
```

The classic result:

$$
\sum_{k=1}^{n} k = \frac{n(n+1)}{2} .
$$

Proof by induction on $n$:

- **Base case** ($n = 1$): both sides equal $1$.
- **Inductive step**: assume true for $n$; then
  $\sum_{k=1}^{n+1} k = \frac{n(n+1)}{2} + (n+1) = \frac{(n+1)(n+2)}{2}$.

```{solution-end}
```

## Multiple exercises in sequence

```{exercise}
:label: ex:seq1

First exercise in the sequence.
```

```{exercise}
:label: ex:seq2

Second exercise in the sequence.
```

```{exercise}
:label: ex:seq3

Third exercise in the sequence. Vertical spacing between consecutive
exercise blocks should remain consistent.
```
