# Code blocks

Tests syntax highlighting, line numbering, captions, and language-specific
token styling (especially f-string interpolation, which previously regressed).

## Python — basic

```python
def fibonacci(n):
    """Return the n-th Fibonacci number."""
    if n < 2:
        return n
    a, b = 0, 1
    for _ in range(n - 1):
        a, b = b, a + b
    return b


print(fibonacci(10))
```

## Python — f-strings (regression target)

The theme previously had a bug where f-string placeholders rendered in
italics. The `.si` (String.Interpol) tokens inside f-strings must render
upright.

```python
name = "world"
x = 42

# Single-quote f-string
greeting = f'hello, {name}!'

# Double-quote f-string with expression
report = f"the value of x is {x} and x squared is {x ** 2}"

# Multi-line f-string with format spec
summary = (
    f"name={name!r}, "
    f"x={x:>5d}, "
    f"x_hex={x:#06x}"
)

print(greeting)
print(report)
print(summary)
```

## Python — with line numbers and caption

```{code-block} python
:caption: Newton's method for square roots
:linenos:

def sqrt_newton(x, tolerance=1e-10):
    if x < 0:
        raise ValueError("input must be non-negative")
    guess = x / 2 if x > 1 else 1.0
    while abs(guess * guess - x) > tolerance:
        guess = (guess + x / guess) / 2
    return guess


for n in [2, 3, 4, 9, 16]:
    print(f"sqrt({n}) = {sqrt_newton(n)}")
```

## Python — with line emphasis

```{code-block} python
:emphasize-lines: 3, 5-6

def process(items):
    total = 0
    for item in items:           # emphasised line
        if item > 0:
            total += item        # emphasised range start
            print(item)          # emphasised range end
    return total
```

## JavaScript

```javascript
const debounce = (fn, delay) => {
  let timeoutId;
  return (...args) => {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn.apply(this, args), delay);
  };
};

const onResize = debounce(() => {
  console.log("window resized to", window.innerWidth, window.innerHeight);
}, 200);

window.addEventListener("resize", onResize);
```

## Bash

```bash
#!/usr/bin/env bash
set -euo pipefail

for file in "$@"; do
    if [[ -f "$file" ]]; then
        echo "processing $file"
        wc -l "$file"
    else
        echo "skipping $file (not a regular file)" >&2
    fi
done
```

## YAML

```yaml
name: example
on:
  push:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - name: Run tests
        run: |
          pip install -r requirements.txt
          pytest -v
```

## Inline code in prose

When discussing `numpy.array` or `pd.DataFrame`, inline `monospace` should sit
on the text baseline without disrupting line height. The function call
`fibonacci(10)` mid-sentence should align with surrounding words.
