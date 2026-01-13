# Kakutani: A Generalization of Brouwer's Fixed Point Theorem (1941)

## Source
**Kakutani, S.** (1941). "A Generalization of Brouwer's Fixed Point Theorem". *Duke Mathematical Journal*, 8(3):457-459.

Received January 21, 1941.

---

## Overview

This seminal 3-page paper generalizes Brouwer's fixed point theorem from **point-to-point mappings** to **point-to-set mappings** (set-valued mappings). It then shows how this generalized theorem implies von Neumann's minimax theorem and results in mathematical economics.

---

## I. Brouwer's Fixed Point Theorem (Original)

**Theorem (Brouwer)**: If $x \mapsto \varphi(x)$ is a **continuous point-to-point mapping** of an $r$-dimensional closed simplex $S$ into itself, then there exists $x_0 \in S$ such that:
$$x_0 = \varphi(x_0)$$

---

## II. Kakutani's Generalization

### Notation

Let $\mathfrak{R}(S)$ be the family of all **closed convex subsets** of $S$.

### Definition: Upper Semi-Continuous (Set-Valued)

A point-to-set mapping $x \mapsto \Phi(x) \in \mathfrak{R}(S)$ is called **upper semi-continuous** if:
$$x_n \to x_0, \quad y_n \in \Phi(x_n), \quad y_n \to y_0 \quad \Rightarrow \quad y_0 \in \Phi(x_0)$$

**Equivalent Condition**: The graph of $\Phi$:
$$\text{Graph}(\Phi) = \{(x, y) : y \in \Phi(x)\} = \sum_{x \in S} x \times \Phi(x)$$
is a **closed subset** of $S \times S$.

### Theorem 1 (Kakutani's Fixed Point Theorem)

**Theorem 1**: If $x \mapsto \Phi(x)$ is an **upper semi-continuous point-to-set mapping** of an $r$-dimensional closed simplex $S$ into $\mathfrak{R}(S)$, then there exists $x_0 \in S$ such that:
$$x_0 \in \Phi(x_0)$$

---

## III. Proof of Theorem 1

### Step 1: Approximation by Point-to-Point Mappings

Let $S^{(n)}$ be the $n$-th **barycentric simplicial subdivision** of $S$.

For each vertex $x^n$ of $S^{(n)}$, take an arbitrary point $y^n \in \Phi(x^n)$.

### Step 2: Linear Extension

The mapping $x^n \mapsto y^n$ defined on vertices extends **linearly** inside each simplex of $S^{(n)}$ to give a continuous point-to-point mapping:
$$x \mapsto \varphi_n(x)$$
of $S$ into itself.

### Step 3: Apply Brouwer's Theorem

By Brouwer's fixed point theorem, there exists $x_n \in S$ such that:
$$x_n = \varphi_n(x_n)$$

### Step 4: Extract Convergent Subsequence

Take a subsequence $\{x_{n_\nu}\}$ ($\nu = 1, 2, \ldots$) converging to some $x_0 \in S$.

**Claim**: This $x_0$ is the required fixed point.

### Step 5: Detailed Verification

Let $\Delta_{n_\nu}$ be an $r$-dimensional simplex of $S^{(n_\nu)}$ containing $x_{n_\nu}$.

Let $x_0^{n_\nu}, x_1^{n_\nu}, \ldots, x_r^{n_\nu}$ be the vertices of $\Delta_{n_\nu}$.

Then:
- $\{x_i^{n_\nu}\} \to x_0$ for $i = 0, 1, \ldots, r$ as $\nu \to \infty$
- $x_{n_\nu} = \sum_{i=0}^r \lambda_i^{n_\nu} x_i^{n_\nu}$ for suitable $\lambda_i^{n_\nu} \geq 0$ with $\sum_{i=0}^r \lambda_i^{n_\nu} = 1$

Let $y_i^{n_\nu} = \varphi_{n_\nu}(x_i^{n_\nu}) \in \Phi(x_i^{n_\nu})$.

Then:
$$x_{n_\nu} = \varphi_{n_\nu}(x_{n_\nu}) = \sum_{i=0}^r \lambda_i^{n_\nu} y_i^{n_\nu}$$

### Step 6: Taking Limits

Extract a further subsequence such that $\{y_i^{n_\nu}\}$ and $\{\lambda_i^{n_\nu}\}$ converge for $i = 0, 1, \ldots, r$.

Let $\lim y_i^{n_\nu} = y_i^0$ and $\lim \lambda_i^{n_\nu} = \lambda_i^0$.

Then:
- $\lambda_i^0 \geq 0$ and $\sum_{i=0}^r \lambda_i^0 = 1$
- $x_0 = \sum_{i=0}^r \lambda_i^0 y_i^0$

### Step 7: Upper Semi-Continuity

Since $x_i^{n_\nu} \to x_0$, $y_i^{n_\nu} \in \Phi(x_i^{n_\nu})$, and $y_i^{n_\nu} \to y_i^0$, by **upper semi-continuity**:
$$y_i^0 \in \Phi(x_0) \quad \text{for } i = 0, 1, \ldots, r$$

### Step 8: Convexity

Since $\Phi(x_0)$ is **convex**:
$$x_0 = \sum_{i=0}^r \lambda_i^0 y_i^0 \in \Phi(x_0)$$

**Q.E.D.**

---

## IV. Remark and Corollary

### Remark

Brouwer's theorem is a **special case** of Theorem 1 when each $\Phi(x)$ consists of only one point $\varphi(x)$. In this case, upper semi-continuity of $\Phi(x)$ reduces to ordinary continuity of $\varphi(x)$.

### Corollary

**Corollary**: Theorem 1 is also valid even if $S$ is an **arbitrary bounded closed convex set** in a Euclidean space.

**Proof**: 
1. Take a closed simplex $S'$ containing $S$ as a subset
2. Consider a continuous **retracting mapping** $\psi: S' \to S$ with $\psi(x) = x$ for $x \in S$
3. The mapping $x \mapsto \Phi(\psi(x))$ is upper semi-continuous on $S'$
4. By Theorem 1, there exists $x_0 \in S'$ with $x_0 \in \Phi(\psi(x_0))$
5. Since $\Phi(\psi(x_0)) \subseteq S$, we have $x_0 \in S$
6. By the retracting property, $x_0 \in \Phi(x_0) \subseteq S$. ∎

---

## V. Application: Theorem 2 (Intersection Theorem)

### Statement

**Theorem 2**: Let $K$ and $L$ be two **bounded closed convex sets** in Euclidean spaces $\mathbb{R}^m$ and $\mathbb{R}^n$ respectively. Let $U$ and $V$ be two **closed subsets** of $K \times L$ such that:

1. For any $x_0 \in K$, the set $U_{x_0} = \{y \in L : (x_0, y) \in U\}$ is **non-empty, closed, and convex**
2. For any $y_0 \in L$, the set $V_{y_0} = \{x \in K : (x, y_0) \in V\}$ is **non-empty, closed, and convex**

**Conclusion**: $U$ and $V$ have a **common point**.

### Proof

Set $S = K \times L$ and define a point-to-set mapping:
$$\Phi(z) = V_y \times U_x \quad \text{where } z = (x, y)$$

Since $U$ and $V$ are both closed, $\Phi(z)$ is upper semi-continuous.

By the Corollary of Theorem 1, there exists $z_0 \in K \times L$ such that $z_0 \in \Phi(z_0)$.

This means there exists $(x_0, y_0)$ with:
$$(x_0, y_0) \in V_{y_0} \times U_{x_0}$$

Equivalently: $x_0 \in V_{y_0}$ and $y_0 \in U_{x_0}$, which means:
$$z_0 = (x_0, y_0) \in U \cap V$$

**Q.E.D.**

### Remark

Theorem 2 is due to **J. von Neumann** [3], who proved it using integration in Euclidean spaces. Kakutani's proof via the fixed point theorem is simpler.

---

## VI. Application: Theorem 3 (Minimax Theorem)

### Statement

**Theorem 3**: Let $f(x, y)$ be a **continuous** real-valued function defined for $x \in K$ and $y \in L$, where $K$ and $L$ are bounded closed convex sets in $\mathbb{R}^m$ and $\mathbb{R}^n$.

**Assumptions**:
1. For every $x_0 \in K$ and every $\alpha \in \mathbb{R}$, the set $\{y \in L : f(x_0, y) \leq \alpha\}$ is **convex**
2. For every $y_0 \in L$ and every $\beta \in \mathbb{R}$, the set $\{x \in K : f(x, y_0) \geq \beta\}$ is **convex**

**Conclusion**:
$$\max_{x \in K} \min_{y \in L} f(x, y) = \min_{y \in L} \max_{x \in K} f(x, y)$$

### Proof

Define:
$$U = \{(x_0, y_0) \in K \times L : f(x_0, y_0) = \min_{y \in L} f(x_0, y)\}$$
$$V = \{(x_0, y_0) \in K \times L : f(x_0, y_0) = \max_{x \in K} f(x, y_0)\}$$

Both $U$ and $V$ satisfy the conditions of Theorem 2.

By Theorem 2, there exists $(x_0, y_0) \in U \cap V$, i.e.:
$$f(x_0, y_0) = \min_{y \in L} f(x_0, y) = \max_{x \in K} f(x, y_0)$$

Therefore:
$$\min_{y \in L} \max_{x \in K} f(x, y) \leq \max_{x \in K} f(x, y_0) = f(x_0, y_0) = \min_{y \in L} f(x_0, y) \leq \max_{x \in K} \min_{y \in L} f(x, y)$$

Since clearly $\min_{y} \max_{x} f \geq \max_{x} \min_{y} f$, we have equality. ∎

### Remark

Theorem 3 is one of the **fundamental theorems in game theory** developed by J. von Neumann [2].

---

## VII. Summary: Logical Dependencies

```
Brouwer's Fixed Point Theorem
           │
           ▼
   Theorem 1 (Kakutani's FPT)
           │
           ├──────────────────┐
           ▼                  ▼
   Corollary (General)    Theorem 2 (Intersection)
                              │
                              ▼
                     Theorem 3 (Minimax)
```

---

## VIII. Historical Significance

1. **Foundation for Game Theory**: Kakutani's theorem became a key tool for proving existence of Nash equilibria

2. **Mathematical Economics**: Applications to general equilibrium theory (Arrow-Debreu)

3. **Set-Valued Analysis**: Pioneered the study of correspondences/multifunctions

4. **Simplicity**: The proof is remarkably short (3 pages) yet enormously influential

---

## IX. References (from the paper)

1. Knaster, B., Kuratowski, C., Mazurkiewicz, S. (1929). "Ein Beweis des Fixpunktsatzes für n-dimensionale Simplexe". *Fund. Math.*, 14:132-137.

2. Von Neumann, J. (1928). "Zur Theorie der Gesellschaftsspiele". *Math. Ann.*, 100:295-320.

3. Von Neumann, J. (1937). "Über ein ökonomisches Gleichungssystem und eine Verallgemeinerung des Brouwerschen Fixpunktsatzes". *Erg. Math. Kolloqu.*, 8:73-83.

4. Wallace, A.D. (1941). "A fixed point theorem for trees". *Bull. Amer. Math. Soc.*, 47 (forthcoming).
