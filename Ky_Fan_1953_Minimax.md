# Ky Fan: Minimax Theorems (1953)

## Source
**Fan, K.** (1953). "Minimax Theorems". *Proceedings of the National Academy of Sciences*, 39:42-47.

Communicated by J. von Neumann, November 17, 1952.

---

## Overview

This paper contains **new minimax theorems involving no linear space structure**. Previous generalizations of von Neumann's minimax theorem (by Ville, Wald, Karlin, Kneser, Fan) all relied on linear space structures. Ky Fan removes this requirement by introducing abstract notions of "convex on X" and "concave on Y".

---

## I. Abstract Convexity Definitions

### Definition: Convex on X

Let $f$ be a real-valued function on $X \times Y$. $f$ is said to be **convex on $X$** if:

For any $x_1, x_2 \in X$ and $\xi_1, \xi_2 \geq 0$ with $\xi_1 + \xi_2 = 1$, there exists $x_0 \in X$ such that:
$$f(x_0, y) \leq \xi_1 f(x_1, y) + \xi_2 f(x_2, y) \quad \text{for all } y \in Y$$

### Definition: Concave on Y

$f$ is said to be **concave on $Y$** if:

For any $y_1, y_2 \in Y$ and $\eta_1, \eta_2 \geq 0$ with $\eta_1 + \eta_2 = 1$, there exists $y_0 \in Y$ such that:
$$f(x, y_0) \geq \eta_1 f(x, y_1) + \eta_2 f(x, y_2) \quad \text{for all } x \in X$$

> 📌 **Key Innovation**: These definitions make sense for arbitrary sets $X, Y$ without any linear structure!

---

## II. Theorem 1 (Main Result)

### Statement

**Theorem 1**: Let $X$, $Y$ be two **compact Hausdorff spaces** and $f$ a real-valued function on $X \times Y$. Suppose:
- For every $y \in Y$, $f(x, y)$ is **lower semi-continuous (l.s.c.)** on $X$
- For every $x \in X$, $f(x, y)$ is **upper semi-continuous (u.s.c.)** on $Y$

Then:

**(i)** The equality
$$\min_{x \in X} \max_{y \in Y} f(x, y) = \max_{y \in Y} \min_{x \in X} f(x, y) \tag{1}$$
holds **if and only if** the following condition is satisfied:

For any two finite sets $\{x_1, x_2, \ldots, x_n\} \subset X$ and $\{y_1, y_2, \ldots, y_m\} \subset Y$, there exist $x_0 \in X$ and $y_0 \in Y$ such that:
$$f(x_0, y_k) \leq f(x_i, y_0) \quad (1 \leq i \leq n, 1 \leq k \leq m) \tag{2}$$

**(ii)** In particular, if $f$ is **convex on $X$** and **concave on $Y$**, then (1) holds.

---

## III. Proof of Theorem 1

### Preliminary Observations

Both sides of (1) are well-defined:
- For each $x \in X$, $f(x, y)$ is u.s.c. on compact $Y$, so $\max_{y \in Y} f(x, y)$ exists
- $\max_{y \in Y} f(x, y)$ is l.s.c. as a function of $x$ (supremum of l.s.c. functions)
- Hence $\min_{x \in X} \max_{y \in Y} f(x, y)$ exists

### Proof of (i): Sufficiency

**Step 1**: From the condition (2), for any finite sets:
$$\min_{x \in X} \max_{1 \leq k \leq m} f(x, y_k) \leq \max_{y \in Y} \min_{1 \leq i \leq n} f(x_i, y)$$

**Step 2**: Any real number $\alpha$ satisfies at least one of:
$$\min_{x \in X} \max_{1 \leq k \leq m} f(x, y_k) \leq \alpha \quad \text{or} \quad \max_{y \in Y} \min_{1 \leq i \leq n} f(x_i, y) \geq \alpha$$

**Step 3**: Define level sets:
$$L(y; \alpha) = \{x \in X \mid f(x, y) \leq \alpha\}, \quad U(x; \alpha) = \{y \in Y \mid f(x, y) \geq \alpha\}$$

These are closed subsets of $X$, $Y$ respectively.

**Step 4**: For any $\alpha$ and finite sets, the intersections $\bigcap_{k=1}^m L(y_k; \alpha)$ and $\bigcap_{i=1}^n U(x_i; \alpha)$ are never both empty.

**Step 5**: By compactness, for any $\alpha$, at least one of $\bigcap_{y \in Y} L(y; \alpha)$ or $\bigcap_{x \in X} U(x; \alpha)$ is non-empty.

**Step 6**: Therefore:
$$\min_{x \in X} \max_{y \in Y} f(x, y) \leq \max_{y \in Y} \min_{x \in X} f(x, y)$$

Combined with the fundamental inequality (reverse direction), we get equality (1).

### Proof of (ii): Convex-Concave Case

**Step 1**: To verify condition (2), apply von Neumann's minimax theorem to the finite matrix game with payoffs $f(x_i, y_k)$.

**Step 2**: There exist weights $\{\xi_1, \ldots, \xi_n\}$ and $\{\eta_1, \ldots, \eta_m\}$ with $\sum \xi_i = \sum \eta_k = 1$ such that:
$$\max_{1 \leq k \leq m} \sum_{i=1}^n \xi_i f(x_i, y_k) \leq \min_{1 \leq i \leq n} \sum_{k=1}^m \eta_k f(x_i, y_k) \tag{3}$$

**Step 3**: By convexity on $X$, there exists $x_0 \in X$ with:
$$f(x_0, y_k) \leq \sum_{i=1}^n \xi_i f(x_i, y_k) \quad (1 \leq k \leq m) \tag{4}$$

**Step 4**: By concavity on $Y$, there exists $y_0 \in Y$ with:
$$f(x_i, y_0) \geq \sum_{k=1}^m \eta_k f(x_i, y_k) \quad (1 \leq i \leq n) \tag{5}$$

**Step 5**: Combining (3), (4), (5) gives condition (2). ∎

---

## IV. Theorem 2 (Kneser's Generalization)

### Statement

**Theorem 2**: Let $X$ be a **compact Hausdorff space** and $Y$ an **arbitrary set** (not topologized). Let $f$ be a real-valued function on $X \times Y$ such that for every $y \in Y$, $f(x, y)$ is l.s.c. on $X$.

If $f$ is **convex on $X$** and **concave on $Y$**, then:
$$\min_{x \in X} \sup_{y \in Y} f(x, y) = \sup_{y \in Y} \min_{x \in X} f(x, y) \tag{6}$$

> 📌 **Note**: Values may be $+\infty$, and $Y$ need not be topologized!

### Proof Outline (Four Steps)

**Step (i)**: If $y_0 \in Y$ is such that $X_0 = \{x \in X \mid f(x, y_0) \leq 0\} \neq \emptyset$, then restricting $f$ to $X_0 \times Y$ preserves all hypotheses.

**Step (ii)**: If $\{y_1, y_2\} \subset Y$ satisfies $\max_{k=1,2} f(x, y_k) > 0$ for all $x \in X$, then there exists $y_0 \in Y$ with $f(x, y_0) > 0$ for all $x \in X$.

*Key argument*: Let $X_k = \{x \in X \mid f(x, y_k) \leq 0\}$ for $k = 1, 2$. These are disjoint closed sets. Define:
$$\mu_1 = \max_{x \in X_1} \frac{-f(x, y_1)}{f(x, y_2)}, \quad \mu_2 = \max_{x \in X_2} \frac{-f(x, y_2)}{f(x, y_1)}$$

One can show $\mu_1 \mu_2 < 1$. Then choose $\eta_1, \eta_2 > 0$ with $\eta_1 + \eta_2 = 1$ such that:
$$\eta_1 f(x, y_1) + \eta_2 f(x, y_2) > 0 \quad \text{for all } x \in X$$

By concavity, there exists $y_0$ with the desired property.

**Step (iii)**: Induction on $m$: If finite set $\{y_1, \ldots, y_m\}$ satisfies $\max_{1 \leq k \leq m} f(x, y_k) > 0$ for all $x \in X$, then there exists $y_0 \in Y$ with $f(x, y_0) > 0$ for all $x \in X$.

**Step (iv)**: For any real $\alpha$: either there exists $x_0 \in X$ with $f(x_0, y) \leq \alpha$ for all $y \in Y$, or there exists $y_0 \in Y$ with $f(x, y_0) > \alpha$ for all $x \in X$.

This implies the right side of (6) is not less than the left side, hence equality.

---

## V. Theorem 3 (Almost Periodic Functions)

### Definition: Almost Periodic

A function $f$ on $X \times Y$ is **right almost periodic** if $f$ is bounded and for any $\varepsilon > 0$, there exists a finite covering $Y = \bigcup_{k=1}^m Y_k$ such that:
$$|f(x, y') - f(x, y'')| < \varepsilon \quad \text{for all } x \in X$$
whenever $y', y''$ belong to the same $Y_k$.

> 📌 Every right almost periodic function is also left almost periodic (and vice versa).

### Statement

**Theorem 3**: Let $f$ be a real-valued **almost periodic function** on $X \times Y$ (arbitrary sets, not topologized). Then:

**(i)** The equality
$$\inf_{x \in X} \sup_{y \in Y} f(x, y) = \sup_{y \in Y} \inf_{x \in X} f(x, y) \tag{16}$$
holds **if and only if**: For any $\varepsilon > 0$ and finite sets $\{x_1, \ldots, x_n\} \subset X$, $\{y_1, \ldots, y_m\} \subset Y$, there exist $x_0 \in X$, $y_0 \in Y$ such that:
$$f(x_0, y_k) - f(x_i, y_0) \leq \varepsilon \quad (1 \leq i \leq n, 1 \leq k \leq m) \tag{17}$$

**(ii)** In particular, if $f$ is convex on $X$ and concave on $Y$, then (16) holds.

---

## VI. Summary of Results

| Theorem | Space $X$ | Space $Y$ | Function Conditions | Conclusion |
|---------|-----------|-----------|---------------------|------------|
| **Thm 1** | Compact Hausdorff | Compact Hausdorff | l.s.c. in $x$, u.s.c. in $y$, convex-concave | min max = max min |
| **Thm 2** | Compact Hausdorff | Arbitrary set | l.s.c. in $x$, convex-concave | min sup = sup min |
| **Thm 3** | Arbitrary set | Arbitrary set | Almost periodic, convex-concave | inf sup = sup inf |

---

## VII. Key Innovations

1. **Abstract Convexity**: Definitions of "convex on $X$" and "concave on $Y$" that work without linear structure

2. **Reduction to Finite Case**: The proof of (ii) reduces to von Neumann's theorem for finite matrix games

3. **Topological Generalization**: Theorem 2 requires topology only on $X$, not on $Y$

4. **Almost Periodic Extension**: Theorem 3 removes all topological requirements

---

## VIII. References (from the paper)

1. Von Neumann, J. (1928). "Zur Theorie der Gesellschaftsspiele". *Math. Annalen*, 100:295-320.
2. Kneser, H. (1952). "Sur un théorème fondamental de la théorie des jeux". *C.R. Acad. Sci. Paris*, 234:2418-2420.
3. Fan, K. (1952). "Fixed-Point and Minimax Theorems in Locally Convex Topological Linear Spaces". *Proc. Nat. Acad. Sci.*, 38:121-126.
