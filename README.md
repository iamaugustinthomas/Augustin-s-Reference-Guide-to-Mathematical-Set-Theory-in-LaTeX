# Augustin's Reference Guide to Mathematical Set Theory in LaTeX

A comprehensive reference guide for formatting mathematical sets, operations, quantifiers, and intervals in LaTeX. Curated and maintained by **[Augustin Thomas](https://github.com/iamaugustinthomas)**.

All commands below must be wrapped in math mode delimiters (`$` or `\[ \]`).

---

## Quick Reference

### 1. Common Number Sets (Blackboard Bold)
> **Note:** To use these symbols, you must include `\usepackage{amssymb}` or `\usepackage{amsfonts}` in your document's preamble.

| Set Name | LaTeX Code | Rendered Output |
| :--- | :--- | :--- |
| **Natural Numbers** | `\mathbb{N}` | $\mathbb{N}$ |
| **Integers** | `\mathbb{Z}` | $\mathbb{Z}$ |
| **Rational Numbers** | `\mathbb{Q}` | $\mathbb{Q}$ |
| **Real Numbers** | `\mathbb{R}` | $\mathbb{R}$ |
| **Complex Numbers** | `\mathbb{C}` | $\mathbb{C}$ |
| **Empty Set** | `\emptyset` or `\varnothing` | $\emptyset$ or $\varnothing$ |

### 2. Core Set Operations

| Operation | LaTeX Code | Rendered Output |
| :--- | :--- | :--- |
| **Union** | `A \cup B` | $A \cup B$ |
| **Intersection** | `A \cap B` | $A \cap B$ |
| **Set Difference / Minus** | `A \setminus B` | $A \setminus B$ |
| **Cartesian Product** | `A \times B` | $A \times B$ |
| **Symmetric Difference** | `A \triangle B` | $A \triangle B$ |
| **Complement** | `A^c` or `A'` | $A^c$ or $A'$ |

### 3. Relations and Membership

| Meaning | LaTeX Code | Rendered Output |
| :--- | :--- | :--- |
| **Element of / Belongs to** | `x \in A` | $x \in A$ |
| **Not an element of** | `x \notin A` | $x \notin A$ |
| **Subset of (or equal to)** | `A \subseteq B` | $A \subseteq B$ |
| **Strict / Proper Subset** | `A \subset B` or `A \subsetneq B` | $A \subset B$ or $A \subsetneq B$ |
| **Superset of** | `A \supseteq B` | $A \supseteq B$ |
| **Not a subset of** | `A \nsubseteq B` | $A \nsubseteq B$ |

### 4. Quantifiers and Logic

| Meaning | LaTeX Code | Rendered Output |
| :--- | :--- | :--- |
| **For all / For each** | `\forall` | $\forall$ |
| **There exists** | `\exists` | $\exists$ |
| **There exists a unique** | `\exists!` | $\exists!$ |
| **Does not exist** | `\nexists` | $\nexists$ |
| **Implies** | `\implies` | $\implies$ |
| **If and only if (Equivalent)** | `\iff` | $\iff$ |
| **Therefore** | `\therefore` | $\therefore$ |
| **Because / Since** | `\because` | $\because$ |

### 5. Intervals and Bounds

| Interval Type | LaTeX Code | Rendered Output |
| :--- | :--- | :--- |
| **Closed Interval** | `[a, b]` | $[a, b]$ |
| **Open Interval** | `(a, b)` | $(a, b)$ |
| **Left-Open, Right-Closed** | `(a, b]` | $(a, b]$ |
| **Left-Closed, Right-Open** | `[a, b)` | $[a, b)$ |
| **Infinity** | `\infty` | $\infty$ |
| **Negative Infinity** | `-\infty` | $-\infty$ |

---

## Large Indexed Operations

### Indexed Union
* **Inline Mode (`$...$`):** `$\bigcup_{i=1}^{n} A_i$` $\rightarrow$ $\bigcup_{i=1}^{n} A_i$
* **Display Mode (`\[...\]`):** `\[\bigcup_{i=1}^{n} A_i\]` $\rightarrow$ $$\bigcup_{i=1}^{n} A_i$$

### Indexed Intersection
* **Inline Mode (`$...$`):** `$\bigcap_{i=1}^{n} A_i$` $\rightarrow$ $\bigcap_{i=1}^{n} A_i$
* **Display Mode (`\[...\]`):** `\[\bigcap_{i=1}^{n} A_i\]` $\rightarrow$ $$ \bigcap_{i=1}^{n} A_i $$

---

## Set-Builder Notation & Braces
Because curly braces `{ }` are used for grouping code in LaTeX, you must escape them with a backslash `\{ \}` to display them visually. *(Note: `\lbrace` and `\rbrace` are used in the output below to prevent markdown parsers from incorrectly stripping the backslashes).*

* **Standard Notation:**
  ```latex
  \{ x \in \mathbb{R} \mid x > 0 \}
  ```
  *Output:* $\lbrace x \in \mathbb{R} \mid x > 0 \rbrace$

* **Auto-Scaling Notation (For tall elements like fractions):**
  ```latex
  \left\{ x \in \mathbb{Q} \;\middle\vert\; x = \frac{1}{n} \right\}
  ```
  *Output:* $\left\lbrace x \in \mathbb{Q} \;\middle|\; x = \frac{1}{n} \right\rbrace$

---

## Venn Diagrams (using TikZ)
To draw Venn diagrams, the standard approach in LaTeX is to use the `tikz` package. You must include `\usepackage{tikz}` in your document preamble. 

**Basic Two-Set Venn Diagram:**
  ```latex
  \begin{tikzpicture}
    % Draw Set A
    \draw (0,0) circle (1.5cm) node[below left] {$A$};
    
    % Draw Set B
    \draw (1.5,0) circle (1.5cm) node[below right] {$B$};
    
    % Label the intersection
    \node at (0.75,0) {$A \cap B$};
  \end{tikzpicture}
  ```
*(Note: TikZ environments cannot be rendered directly in standard Markdown math mode. Compiling the above code in a standard LaTeX editor will produce two overlapping circles labeled A and B, with their intersection labeled in the center.)*

---

## Formatting Tips

### 1. Text Inside Math Mode
Use `\text{...}` (requires `\usepackage{amsmath}`) to add normal words inside your equations so they do not render in cramped math italics:
  ```latex
  \forall x \in \mathbb{Z}, \exists y \in \mathbb{Z} \quad \text{if } x < y
  ```
*Output:* $\forall x \in \mathbb{Z}, \exists y \in \mathbb{Z} \quad \text{if } x < y$

### 2. Fine-Tuning Math Spacing
If your symbols look too crowded, inject small spaces using these spacer commands:
* `\,` (thin space)
* `\;` (medium space)
* `\quad` (large space equal to the width of one character)

---
**Maintainer:** [iamaugustinthomas](https://github.com)  
**License:** MIT License. Feel free to fork, share, and modify!