# Math

Tests MathJax rendering: inline math, display math, numbered equations,
aligned environments, and the `\argmax` / `\argmin` macros defined in
`_config.yml`.

## Inline math

The expectation of $X$ is $\mathbb{E}[X] = \sum_x x \, p(x)$. A standard
normal variable $Z \sim \mathcal{N}(0, 1)$ has $\mathbb{E}[Z] = 0$ and
$\text{Var}(Z) = 1$. Greek letters $\alpha$, $\beta$, $\gamma$, $\delta$,
$\epsilon$, $\theta$, $\lambda$, $\mu$, $\sigma$, $\pi$ should typeset
correctly inline.

## Display math, unnumbered

$$
f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)
$$

## Display math, numbered

$$
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
$$ (eq:gaussian-integral)

Equation {eq}`eq:gaussian-integral` is the classic Gaussian integral.

## Aligned environment

```{math}
:label: eq:aligned-derivation

\begin{aligned}
\frac{\partial L}{\partial \beta}
  &= \frac{\partial}{\partial \beta} \sum_{i=1}^n (y_i - \beta x_i)^2 \\
  &= -2 \sum_{i=1}^n x_i (y_i - \beta x_i) \\
  &= -2 \sum_{i=1}^n x_i y_i + 2 \beta \sum_{i=1}^n x_i^2 .
\end{aligned}
```

See {eq}`eq:aligned-derivation` for the derivation.

## Cases environment

$$
\text{sign}(x) =
\begin{cases}
+1 & \text{if } x > 0, \\
0  & \text{if } x = 0, \\
-1 & \text{if } x < 0.
\end{cases}
$$

## Matrix

$$
A = \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}
\qquad
b = \begin{pmatrix} \alpha \\ \beta \\ \gamma \end{pmatrix}
$$

## Macros defined in _config.yml

The optimisation problem

$$
\hat{\theta} = \argmax_{\theta \in \Theta} \, \ell(\theta; x)
$$

uses the `\argmax` macro. Its companion:

$$
\theta^* = \argmin_{\theta \in \Theta} \, \mathcal{L}(\theta; x).
$$

## Math inside lists

1. The mean satisfies $\bar{x} = \frac{1}{n}\sum_{i=1}^n x_i$.
2. The variance satisfies
   $$
   s^2 = \frac{1}{n-1} \sum_{i=1}^n (x_i - \bar{x})^2 .
   $$
3. The standard error is $s / \sqrt{n}$.

## Math inside a blockquote

> The Cauchy–Schwarz inequality says
> $$
> \left| \langle u, v \rangle \right|^2 \le \langle u, u \rangle \cdot \langle v, v \rangle
> $$
> for all vectors $u, v$ in an inner-product space.
