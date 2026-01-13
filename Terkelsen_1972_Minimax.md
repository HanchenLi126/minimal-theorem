# Terkelsen: Some Minimax Theorems (1972)

## Source
**Terkelsen, F.** (1972). "Some Minimax Theorems". *Mathematica Scandinavica*, 31(2):405-413.

Received April 14, 1972. University of Copenhagen, Denmark.

---

## Overview

This paper approaches minimax problems from the viewpoint of **lower semi-continuous functions on a compact space**, using order-theoretic conditions. It provides:
1. A **Dini-type theorem** (Theorem 1) for directed families
2. A **minimax theorem** (Theorem 2) using weaker order conditions
3. The main **Theorem 3** and its corollaries, including Kneser-Fan

Key innovation: Uses **connectedness** rather than fixed point theorems or KKM lemma.

---

## I. Setup and Fundamental Lemma

### Standing Assumptions

Throughout: $X \neq \emptyset$ and $F \neq \emptyset$.

### The Fundamental Lemma

**Lemma**: Let $X$ be a **compact space**, and let $F$ be a set of **lower semi-continuous** real-valued functions on $X$. The following are **equivalent**:

**(i)** For any $\alpha \in \mathbb{R}$ and any finite non-empty subset $G$ of $F$ such that $\alpha < \min_{x \in X} \max_{f \in G} f(x)$, there exists $h \in F$ with $\alpha \leq \min_{x \in X} h(x)$.

**(ii)** $\sup_{f \in F} \min_{x \in X} f(x) = \min_{x \in X} \sup_{f \in F} f(x)$.

### Proof of Lemma

**Key observation**: For every non-empty $G \subseteq F$, the function $x \mapsto \sup_{f \in G} f(x)$ is **lower semi-continuous** (allowing $+\infty$).

**(i) ⟹ (ii)**: 
1. Choose any $\alpha < \min_{x \in X} \sup_{f \in F} f(x)$
2. Define $A(f) = \{x \in X : f(x) \leq \alpha\}$ for $f \in F$
3. Then $\bigcap_{f \in F} A(f) = \emptyset$
4. By compactness, there exists finite $G \subset F$ with $\bigcap_{f \in G} A(f) = \emptyset$
5. So $\max_{f \in G} f(x) > \alpha$ for each $x \in X$
6. By (i), there exists $h \in F$ with $\alpha \leq \min_{x \in X} h(x) \leq \sup_{f \in F} \min_{x \in X} f(x)$

**(ii) ⟹ (i)**: Trivial.

---

## II. Theorem 1: Directed Families (Dini-Type)

### Definition: Directed

A set $F$ of real-valued functions on $X$ is **directed with respect to $\leq$** if for any $f, g \in F$ there exists $h \in F$ with $f \leq h$ and $g \leq h$.

(Here $f \leq g$ means $f(x) \leq g(x)$ for all $x \in X$.)

### Theorem 1

**Theorem 1**: Let $X$ be a compact space, and let $F$ be a set of lower semi-continuous real-valued functions on $X$ which is **directed with respect to $\leq$**.

**Then**:
$$\sup_{f \in F} \min_{x \in X} f(x) = \min_{x \in X} \sup_{f \in F} f(x)$$

**Proof**: Condition (i) of the Lemma is satisfied: If $G \subset F$ is finite, then there exists $h \in F$ with $f \leq h$ for each $f \in G$.

### Corollary (Dini's Theorem)

**Corollary**: Let $X$ be a compact space, and let $(f_n)$ be a sequence of lower semi-continuous real-valued functions on $X$ with $f_n(x) \leq f_{n+1}(x)$ for $n = 1, 2, \ldots$ and $x \in X$.

**Then**:
$$\lim_{n \to \infty} \min_{x \in X} f_n(x) = \min_{x \in X} \left(\lim_{n \to \infty} f_n(x)\right)$$

---

## III. Theorem 2: Weaker Order Condition

### Motivation

Theorem 1 requires $F$ to be directed: for any $f, g$ there exists $h$ with $f \leq h$ and $g \leq h$.

**Observation**: If $f \leq h$ and $g \leq h$, then $f + g \leq 2h$.

**Question**: Can we weaken to just requiring $f + g \leq 2h$?

### Theorem 2

**Theorem 2**: Let $X$ be a compact space, and let $F$ be a set of lower semi-continuous real-valued functions on $X$ satisfying:

**(i)** For any $f, g \in F$ there exists $h \in F$ such that $f + g \leq 2h$.

**(ii)** Every finite intersection of sets of the form $\{x \in X : f(x) \leq \alpha\}$, with $(f, \alpha) \in F \times \mathbb{R}$, is **connected**.

**Then**:
$$\sup_{f \in F} \min_{x \in X} f(x) = \min_{x \in X} \sup_{f \in F} f(x)$$

### Proof of Theorem 2

**Step (a)**: For any $\alpha \in \mathbb{R}$ and any $f, g \in F$ such that $\alpha < \min_{x \in X} \max(f(x), g(x))$, there exists $h \in F$ with $\alpha < \min_{x \in X} h(x)$.

*Proof of (a)*: Choose $\beta$ with $\alpha < \beta < \min_{x \in X} \max(f(x), g(x))$.

Define:
- $\gamma = \min_{x \in X} f(x)$, $\delta = \min_{x \in X} g(x)$
- $A = \{x \in X : f(x) \leq \beta\}$, $B = \{x \in X : g(x) \leq \beta\}$
- $C = \{x \in X : k(x) \leq \beta\}$ where $f + g \leq 2k$

Then $A$ and $B$ are nonempty closed sets with $A \cap B = \emptyset$.

If $x \notin A \cup B$, then $k(x) \geq \frac{1}{2}(f(x) + g(x)) > \beta$, so $C \subseteq A \cup B$.

By (ii), $C$ is connected. Since $C \subseteq A \cup B$ and $A \cap B = \emptyset$, either $C \subseteq A$ or $C \subseteq B$.

If $C \subseteq A$, set $f_1 = k$, $g_1 = g$; if $C \subseteq B$, set $f_1 = f$, $g_1 = k$.

Then $\beta < \min_{x \in X} \max(f_1(x), g_1(x))$ in each case.

**Iteration**: We can verify either $\gamma_1 > \frac{1}{2}(\gamma + \beta)$ and $\delta_1 = \delta$, or $\gamma_1 = \gamma$ and $\delta_1 > \frac{1}{2}(\beta + \delta)$.

Eventually one of $\gamma_i$ or $\delta_i$ reaches $\beta$, giving the required $h$.

**Step (b)**: By induction: For any $\{f_1, \ldots, f_n\} \subset F$ with $\alpha < \min_{x \in X} \max_{1 \leq i \leq n} f_i(x)$, there exists $h \in F$ with $\alpha < \min_{x \in X} h(x)$.

---

## IV. Theorem 3: Main Minimax Result

### Restating for Product Sets

Setting $F = \{x \mapsto f(x, y) : y \in Y\}$, Theorem 2 becomes:

### Theorem 3

**Theorem 3**: Let $X$ be a **compact connected space**, let $Y$ be a set, and let $f: X \times Y \to \mathbb{R}$ be a function satisfying:

**(i)** For any $y_1, y_2 \in Y$ there exists $y_0 \in Y$ such that:
$$f(x, y_0) \geq \frac{1}{2}(f(x, y_1) + f(x, y_2)) \quad \text{for all } x \in X$$

**(ii)** Every finite intersection of sets of the form $\{x \in X : f(x, y) \leq \alpha\}$, with $(y, \alpha) \in Y \times \mathbb{R}$, is **closed and connected**.

**Then**:
$$\sup_{y \in Y} \min_{x \in X} f(x, y) = \min_{x \in X} \sup_{y \in Y} f(x, y)$$

---

## V. Definitions: Concavelike and Quasi-Convex

### Fan's Concavelike

$f: X \times Y \to \mathbb{R}$ is **convexlike on $X$** if for any $x_1, x_2 \in X$ and $0 < \alpha < 1$, there exists $x_0 \in X$ such that:
$$f(x_0, y) \leq \alpha f(x_1, y) + (1 - \alpha) f(x_2, y) \quad \text{for all } y \in Y$$

$f$ is **concavelike on $Y$** if for any $y_1, y_2 \in Y$ and $0 < \alpha < 1$, there exists $y_0 \in Y$ such that:
$$f(x, y_0) \geq \alpha f(x, y_1) + (1 - \alpha) f(x, y_2) \quad \text{for all } x \in X$$

### Quasi-Convex/Quasi-Concave

$\varphi: X \to \mathbb{R}$ is **quasi-convex** if $\{x \in X : \varphi(x) \leq \alpha\}$ is convex for each $\alpha$.

$\varphi: X \to \mathbb{R}$ is **quasi-concave** if $\{x \in X : \varphi(x) \geq \alpha\}$ is convex for each $\alpha$.

---

## VI. Corollaries of Theorem 3

### Corollary 1 (Weak Topology Version)

**Corollary 1**: Let $X$ be a **weakly compact and convex** subset of a Hausdorff locally convex space $E$, let $Y$ be a set, and let $f: X \times Y \to \mathbb{R}$ satisfy:

**(i)** For any $y_1, y_2 \in Y$ there exists $y_0 \in Y$ such that $f(x, y_0) \geq \frac{1}{2}(f(x, y_1) + f(x, y_2))$ for $x \in X$.

**(ii)** For each $y \in Y$ the function $x \mapsto f(x, y)$ is **lower semi-continuous and quasi-convex** on $X$.

**Then**:
$$\sup_{y \in Y} \min_{x \in X} f(x, y) = \min_{x \in X} \sup_{y \in Y} f(x, y)$$

**Proof**: Sets $\{x \in X : f(x, y) \leq \alpha\}$ are closed, convex, hence weakly closed.

### Corollary 2 (Kneser-Fan Theorem)

**Corollary 2**: Let $X$ be a **compact convex** subset of a topological vector space, let $Y$ be a **convex** subset of a vector space, and let $f: X \times Y \to \mathbb{R}$ satisfy:

**(i)** For each $x \in X$, $y \mapsto f(x, y)$ is **concave** on $Y$.

**(ii)** For each $y \in Y$, $x \mapsto f(x, y)$ is **lower semi-continuous and convex** on $X$.

**Then**:
$$\sup_{y \in Y} \min_{x \in X} f(x, y) = \min_{x \in X} \sup_{y \in Y} f(x, y)$$

### Alternative Proof of Corollary 2

Using **separation of disjoint convex sets** in $\mathbb{R}^n$:

Let $\alpha < \min_{x \in X} \max_{1 \leq i \leq n} f(x, y_i)$.

Let $P \subset \mathbb{R}^n$ be the convex hull of $\{(f(x, y_1), \ldots, f(x, y_n)) : x \in X\}$.

Let $Q = \{(z^1, \ldots, z^n) \in \mathbb{R}^n : z^i \leq \alpha, i = 1, \ldots, n\}$.

Then $P \cap Q = \emptyset$. By separation, there exists $c = (\gamma_1, \ldots, \gamma_n)$ with $\gamma_i \geq 0$, $\sum \gamma_i = 1$ such that:
$$\sup_{z \in Q} c \cdot z \leq \inf_{z \in P} c \cdot z$$

Define $y_0 = \sum_{i=1}^n \gamma_i y_i$. By concavity:
$$f(x, y_0) \geq \sum_{i=1}^n \gamma_i f(x, y_i) \geq \alpha \quad \text{for each } x \in X$$

---

## VII. Examples

### Example 1: Assumptions Necessary

In each case below, all but one assumption of Theorem 3 holds, yet $\sup_y \inf_x f < \inf_x \sup_y f$:

**(a)** $X = (0, 1]$, $Y = [0, +\infty)$, $f(x, y) = xy$. 
- $X$ is **not compact**.

**(b)** $X = Y = [0, 1]$, $f(x, y) = x$ for $y \in [0, 1)$; $f(x, 1) = 1 - 2x$ for $x \in [0, \frac{1}{2}]$; $f(x, 1) = 2x - 1$ for $x \in (\frac{1}{2}, 1]$.
- No $y_0$ exists with $f(x, y_0) \geq \frac{1}{2}(f(x, 0) + f(x, 1))$ for all $x$.

**(c)** $X = Y = [0, 1]$, $f(x, y) = y$ for $x \in [0, 1)$; $f(1, y) = 1 - y$.
- Set $\{x : f(x, 0) \leq 0\}$ is **not closed**.

**(d)** $X = Y = [0, 1]$, $f(x, y) = x + y$ if $x + y \leq 1$; $f(x, y) = 2 - (x + y)$ if $x + y > 1$.
- Set $\{x : f(x, \frac{1}{2}) \leq \frac{1}{2}\}$ is **not connected**.

### Example 2: Disconnected Domain

$X_1 = [-2, -1]$, $X_2 = [1, 2]$, $X = X_1 \cup X_2$, $Y = [-1, 1]$, $f(x, y) = xy/|x|$.

Each restriction satisfies Theorem 3, but $X$ is **not connected**, and minimax fails.

### Example 3: Comparing Three Theorems

Each function below satisfies exactly **one** of Fan's theorem, Sion's theorem, or Theorem 3:

**(a)** Fan only: $X = Y = [0, 1]$, $f(0, y) = f(1, y) = 0$, $f(x, y) = 1$ elsewhere.
- Sets $\{x : f(x, y) \leq 0\}$ not connected (violates Theorem 3 and Sion).

**(b)** Sion only: $X = Y = [0, 1]$, $f(0, y) = y - 1$, $f(x, 0) = x$ for $x \in (0, 1]$, $f(x, y) = 0$ elsewhere.
- No $y_0$ exists for condition (i) (violates Theorem 3 and Fan).

**(c)** Theorem 3 only: $X$ = half-circle, $Y = [0, 1]$, specific $f$.
- $f$ not convexlike on $X$ (violates Fan).
- $x \mapsto f(x, y)$ not quasi-convex since $X$ not convex (violates Sion).

---

## VIII. Summary

| Theorem | Key Condition | Method |
|---------|---------------|--------|
| **Theorem 1** | $F$ directed ($f, g \leq h$) | Dini-type |
| **Theorem 2** | $f + g \leq 2h$ + connectedness | Connectedness |
| **Theorem 3** | Concavelike + closed connected level sets | Main result |
| **Corollary 2** | Concave-convex | = Kneser-Fan |

**Key Innovation**: Uses connectedness instead of fixed points or KKM.

---

## IX. References (from the paper)

1. Berge, C. (1963). *Topological Spaces*. Oliver and Boyd, Edinburgh.
2. Bourbaki, N. (1966). *Elements of Mathematics, General Topology*, Part 2. Hermann, Paris.
3. Fan, K. (1953). "Minimax Theorems". *Proc. Nat. Acad. Sci.*, 39:42-47.
4. Kneser, H. (1952). "Sur un théorème fondamental...". *C.R. Acad. Sci. Paris Sér. A*, 234:2418-2420.
5. Sion, M. (1958). "On general minimax theorems". *Pacific J. Math.*, 8:171-176.
6. Von Neumann, J. (1928). "Zur Theorie der Gesellschaftsspiele". *Math. Ann.*, 100:295-320.
