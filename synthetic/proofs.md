# Proofs and formal statements

Tests the `sphinx-proof` directives: `theorem`, `lemma`, `corollary`,
`proposition`, `definition`, `proof`.

## Definition

```{prf:definition}
:label: def:limit

A sequence $\{x_n\}$ in $\mathbb{R}$ **converges** to $L \in \mathbb{R}$ if
for every $\epsilon > 0$ there exists $N \in \mathbb{N}$ such that
$|x_n - L| < \epsilon$ for all $n \ge N$.
```

## Theorem

```{prf:theorem} Bolzano–Weierstrass
:label: thm:bw

Every bounded sequence in $\mathbb{R}^d$ has a convergent subsequence.
```

## Lemma

```{prf:lemma}
:label: lem:cauchy

A sequence in $\mathbb{R}$ is convergent if and only if it is Cauchy.
```

## Corollary

```{prf:corollary} of Bolzano–Weierstrass
:label: cor:bw

Every continuous function $f : K \to \mathbb{R}$ on a closed bounded subset
$K \subset \mathbb{R}^d$ attains its supremum and infimum.
```

## Proposition

```{prf:proposition}
:label: prop:linearity

Expectation is linear: for random variables $X$, $Y$ on the same probability
space, and constants $a, b \in \mathbb{R}$,
$\mathbb{E}[aX + bY] = a\mathbb{E}[X] + b\mathbb{E}[Y]$.
```

## Proof

```{prf:proof}
By {prf:ref}`def:limit`, it suffices to show that for every $\epsilon > 0$
there exists $N$ such that $|x_n - L| < \epsilon$ for all $n \ge N$.

Fix $\epsilon > 0$. Choose $N$ such that ...

The conclusion follows. $\square$
```

## Cross-references to numbered statements

By {prf:ref}`thm:bw`, the sequence has a convergent subsequence. We invoke
{prf:ref}`lem:cauchy` to conclude convergence of the whole sequence.

## Stacked theorems and proofs

```{prf:theorem}
:label: thm:stacked-1

A first theorem.
```

```{prf:proof}
Proof of the first theorem.
```

```{prf:theorem}
:label: thm:stacked-2

A second theorem, immediately following.
```

```{prf:proof}
Proof of the second theorem. Vertical rhythm between consecutive numbered
statements should remain consistent.
```
