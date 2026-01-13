# Sion: On General Minimax Theorems (1958)

## Source
**Sion, M.** (1958). "On General Minimax Theorems". *Pacific Journal of Mathematics*, 8(1):171-176.

Received June 26, 1957. Research supported by U.S. Air Force.

---

## Overview

This paper unifies two streams of minimax theorem proofs:
1. **Separation method**: Kneser-Fan theorem for concave-convex functions
2. **Fixed point method**: Nikaidô's theorem for quasi-concave-convex functions

Sion proves a minimax theorem for **quasi-concave-convex** functions that are **u.s.c.-l.s.c.**, using the **KKM theorem** (based on Sperner's lemma).

---

## I. Fundamental Definitions

### 2.1 Concavelike in M

A function $f$ on $M \times N$ is **concavelike in $M$** if for every $\mu_1, \mu_2 \in M$ and $0 \leq t \leq 1$, there is a $\mu \in M$ such that:
$$tf(\mu_1, \nu) + (1-t)f(\mu_2, \nu) \leq f(\mu, \nu) \quad \text{for all } \nu \in N$$

### 2.2 Convexlike in N

A function $f$ on $M \times N$ is **convexlike in $N$** if for every $\nu_1, \nu_2 \in N$ and $0 \leq t \leq 1$, there is a $\nu \in N$ such that:
$$tf(\mu, \nu_1) + (1-t)f(\mu, \nu_2) \geq f(\mu, \nu) \quad \text{for all } \mu \in M$$

### 2.3 Concave-Convexlike

A function $f$ on $M \times N$ is **concave-convexlike** if it is concavelike in $M$ and convexlike in $N$.

### 2.4 Quasi-Concave in M

A function $f$ on $M \times N$ is **quasi-concave in $M$** if:
$$\{\mu : f(\mu, \nu) \geq c\} \text{ is a convex set for any } \nu \in N \text{ and real } c$$

### 2.5 Quasi-Convex in N

A function $f$ on $M \times N$ is **quasi-convex in $N$** if:
$$\{\nu : f(\mu, \nu) \leq c\} \text{ is a convex set for any } \mu \in M \text{ and real } c$$

### 2.6 Quasi-Concave-Convex

A function $f$ is **quasi-concave-convex** if it is quasi-concave in $M$ and quasi-convex in $N$.

### 2.7 u.s.c.-l.s.c.

A function $f$ on $M \times N$ is **u.s.c.-l.s.c.** if:
- $f(\mu, \nu)$ is **upper semi-continuous** in $\mu$ for each $\nu \in N$
- $f(\mu, \nu)$ is **lower semi-continuous** in $\nu$ for each $\mu \in M$

### 2.8-2.10 Notation

$$\sup \inf f = \sup_{\mu \in M} \inf_{\nu \in N} f(\mu, \nu)$$
$$\inf \sup f = \inf_{\nu \in N} \sup_{\mu \in M} f(\mu, \nu)$$
$$\Gamma X = \text{convex hull of } X$$
$$\overline{X} = \text{closure of } X$$

---

## II. Key Tools

### Theorem 3.1 (KKM-type)

**Theorem 3.1**: Let $S$ be an $n$-dimensional simplex with vertices $a_0, \ldots, a_n$. If $A_0, \ldots, A_n$ are **open sets** such that:
1. $S \subset \bigcup_{i=0}^n A_i$
2. $S - A_i$ is **convex**
3. $a_i \notin A_j$ for $i \neq j$

Then $\bigcap_{i=0}^n A_i \neq \emptyset$.

**Proof**: Use KKM theorem (Knaster-Kuratowski-Mazurkiewicz) based on Sperner's lemma.

### Theorem 3.2 (Helly-type)

**Theorem 3.2**: Let $\mathfrak{A} = \{a_0, \ldots, a_n\}$ consist of $n+1$ points in a linear space of dimension $k < n$. Then:
$$\bigcap_{i=0}^n \Gamma(\mathfrak{A} - \{a_i\}) \neq \emptyset$$

**Proof**: By Helly's theorem.

---

## III. Main Results for Quasi-Concave-Convex Functions

### Lemma 3.3

**Lemma 3.3**: Let $M$ be a convex set, $Y$ a finite set, and $f$ a function on $M \times Y$ that is quasi-concave and upper semi-continuous in $M$.

Suppose $Y$ is **minimal** with respect to the property: for each $\mu \in M$ there is a $y \in Y$ with $f(\mu, y) < c$.

**Then** there exists $\mu_0 \in M$ such that $f(\mu_0, y) < c$ for all $y \in Y$.

**Proof**: 
1. Let $Y = \{y_0, \ldots, y_n\}$ and $A_i = \{\mu : f(\mu, y_i) < c\}$
2. The $A_i$ are open (u.s.c.) and $M - A_i$ is convex (quasi-concave)
3. By minimality, for each $i$ there exists $a_i \in M - A_j$ for $j \neq i$
4. If $\bigcap \Gamma(\mathfrak{A} - \{a_i\}) = \emptyset$, then $\mathfrak{A}$ spans an $n$-simplex
5. By Theorem 3.1, $\bigcap_{i=0}^n A_i \neq \emptyset$

### Lemma 3.3' (Dual)

**Lemma 3.3'**: Let $N$ be a convex set, $X$ a finite set, and $f$ a function on $X \times N$ that is quasi-convex and lower semi-continuous in $N$.

Suppose $X$ is **minimal** with respect to the property: for each $\nu \in N$ there is an $x \in X$ with $f(x, \nu) > c$.

**Then** there exists $\nu_0 \in N$ such that $f(x, \nu_0) > c$ for all $x \in X$.

---

### Theorem 3.4 (Main Result)

**Theorem 3.4**: Let $M$ and $N$ be **convex, compact** spaces, and $f$ a function on $M \times N$ that is **quasi-concave-convex** and **u.s.c.-l.s.c.**

**Then**:
$$\sup \inf f = \inf \sup f$$

### Proof of Theorem 3.4

**Step 1**: Suppose for contradiction:
$$\sup \inf f < c < \inf \sup f$$

**Step 2**: Define:
$$A_\mu = \{\nu : f(\mu, \nu) > c\}$$
$$B_\nu = \{\mu : f(\mu, \nu) < c\}$$

The $A_\mu$ are open and cover $N$. Since $N$ is compact, finitely many cover $N$.
Similarly, finitely many $B_\nu$ cover $M$.

**Step 3**: Choose finite subsets $X_1 \subset M$ and $Y_1 \subset N$ such that:
- For each $\nu \in N$ (hence for each $\nu \in \Gamma Y_1$), there is $x \in X_1$ with $f(x, \nu) > c$
- For each $\mu \in M$ (hence for each $\mu \in \Gamma X_1$), there is $y \in Y_1$ with $f(\mu, y) < c$

**Step 4**: **Alternating reduction process**:

Let $X_2$ be a **minimal** subset of $X_1$ such that for each $\nu \in \Gamma Y_1$, there is $x \in X_2$ with $f(x, \nu) > c$.

Next, let $Y_2$ be a **minimal** subset of $Y_1$ such that for each $\mu \in \Gamma X_2$, there is $y \in Y_2$ with $f(\mu, y) < c$.

Repeat this process. After finitely many steps, we get finite $X \subset M$ and $Y \subset N$ such that:
- $X$ is minimal: for each $\nu \in \Gamma Y$, there is $x \in X$ with $f(x, \nu) > c$
- $Y$ is minimal: for each $\mu \in \Gamma X$, there is $y \in Y$ with $f(\mu, y) < c$

**Step 5**: By **Lemma 3.3**, there exists $\mu_0 \in \Gamma X$ such that $f(\mu_0, y) < c$ for all $y \in Y$.

By quasi-convexity: $f(\mu_0, \nu) < c$ for all $\nu \in \Gamma Y$.

**Step 6**: By **Lemma 3.3'**, there exists $\nu_0 \in \Gamma Y$ such that $f(x, \nu_0) > c$ for all $x \in X$.

By quasi-concavity: $f(\mu, \nu_0) > c$ for all $\mu \in \Gamma X$.

**Step 7**: Then $c < f(\mu_0, \nu_0) < c$, which is **impossible**.

**Q.E.D.** ∎

---

### Corollary 3.5

**Corollary 3.5**: Let $M$ and $N$ be convex spaces, **one of which is compact**, and $f$ a function on $M \times N$ that is quasi-concave-convex and u.s.c.-l.s.c.

**Then** $\sup \inf f = \inf \sup f$.

**Proof**: Reduce to Theorem 3.4 by restricting to a finite subset.

---

### Remark 3.6 (Counterexample)

The condition that $f$ be u.s.c.-l.s.c. **cannot be removed** even if $M$, $N$ are finite-dimensional.

**Example**: Let $M = N = [0, 1]$ and:
$$f(\mu, \nu) = \begin{cases} 0 & \text{if } 0 \leq \mu < 1/2 \text{ and } \nu = 0, \text{ or } 1/2 \leq \mu \leq 1 \text{ and } \nu = 1 \\ 1 & \text{otherwise} \end{cases}$$

Then:
- $f$ is quasi-concave-convex
- For each $\mu$, $f(\mu, \nu)$ is l.s.c. in $\nu$
- But $f(\mu, 1)$ is **not u.s.c.** in $\mu$

Result: $\sup \inf f = 0$ but $\inf \sup f = 1$.

---

## IV. Minimax Theorems for Concave-Convexlike Functions

### Theorem 4.1

**Theorem 4.1**: Let $M$ and $N$ be any spaces, $f$ a function on $M \times N$ that is **concave-convexlike**.

If for any $c < \inf \sup f$ there exists a finite subset $X \subset M$ such that for any $\nu \in N$ there is an $x \in X$ with $f(x, \nu) > c$, then:
$$\sup \inf f = \inf \sup f$$

### Theorem 4.1' (Dual)

**Theorem 4.1'**: Let $M, N$ be any spaces, $f$ a function on $M \times N$ that is concave-convexlike.

If for any $c > \sup \inf f$ there exists a finite set $Y \subset N$ such that for any $\mu \in M$ there is a $y \in Y$ with $f(\mu, y) < c$, then:
$$\sup \inf f = \inf \sup f$$

---

### Theorem 4.2 (Kneser-Fan)

**Theorem 4.2 (Kneser, Fan)**: Let $M$ be **compact**, $N$ any space, $f$ a function on $M \times N$ that is **concave-convexlike**.

If $f(\mu, \nu)$ is **upper semi-continuous** in $\mu$ for each $\nu$, then:
$$\sup \inf f = \inf \sup f$$

**Proof**: If $c > \sup \inf f$, let $A_\nu = \{\mu : f(\mu, \nu) < c\}$. The $A_\nu$ are open and cover $M$. By compactness, finitely many cover $M$. Apply Theorem 4.1'.

### Theorem 4.2' (Dual)

**Theorem 4.2'**: Let $M$ be any space, $N$ **compact**, $f$ a function on $M \times N$ that is concave-convexlike.

If $f(\mu, \nu)$ is **lower semi-continuous** in $\nu$ for each $\mu$, then:
$$\sup \inf f = \inf \sup f$$

---

## V. Summary: Logical Structure

```
KKM Theorem (Sperner's Lemma)
        │
        ▼
   Theorem 3.1 (KKM-type)
        │
        ├───────────────┐
        ▼               ▼
   Lemma 3.3       Lemma 3.3'
        │               │
        └───────┬───────┘
                ▼
        Theorem 3.4 (Main)
     (Quasi-concave-convex)
                │
                ▼
        Corollary 3.5
                
        ═══════════════
        
   Von Neumann's Theorem
        │
        ▼
   Theorem 4.1, 4.1'
        │
        ▼
   Theorem 4.2, 4.2' (Kneser-Fan)
```

---

## VI. Comparison of Assumptions

| Theorem | Algebraic Condition | Topological Condition |
|---------|---------------------|----------------------|
| **3.4** | Quasi-concave-convex | u.s.c.-l.s.c., both compact |
| **3.5** | Quasi-concave-convex | u.s.c.-l.s.c., one compact |
| **4.2** | Concave-convexlike | u.s.c. in one variable, one compact |
| **Nikaidô** | Quasi-concave-convex | Continuous in each variable |
| **Kneser-Fan** | Concave-convex | Semi-continuous in one variable |

---

## VII. Key Contributions

1. **Unification**: Combines separation method and fixed point method approaches
2. **Generalization**: Quasi-concave-convex (weaker than concave-convex) with semi-continuity (weaker than continuity)
3. **Novel Proof**: Uses KKM theorem in a new way via alternating reduction
4. **Counterexample**: Shows semi-continuity is necessary

---

## VIII. References (from the paper)

1. *Contributions to the theory of games*, vol. I, Ann. of Math. Studies, No. 24, 1950.
2. Berge, C. (1954). "Sur une convexité régulière...". *Bull. Soc. Math. France*, 82:301-319.
3. Fan, K. (1953). "Minimax Theorems". *Proc. Nat. Acad. Sci.*, 39:42-47.
4. Helly, E. (1923). "Über Mengen konvexer Körper...". *J. Deutsch. Math. Vereinig.*, 32:175-176.
5. Knaster, B., Kuratowski, C., Mazurkiewicz, S. (1929). "Ein Beweis des Fixpunktsatzes...". *Fund. Math.*, 14:132-138.
6. Kneser, H. (1952). "Sur un théorème fondamental...". *C.R. Acad. Sci. Paris*, 234:2418-2420.
7. Nikaidô, H. (1954). "On von Neumann's minimax theorem". *Pacific J. Math.*, 4:65-72.
8. Shiffman, M. (1949). "On the equality min max = max min...". RAND Report RM-243.
9. Ville, J. (1938). "Sur la théorie générale des jeux...". *Traité du calcul des probabilités*, IV, 2:105-113.
10. Von Neumann, J. (1928). "Zur Theorie der Gesellschaftsspiele". *Math. Ann.*, 100:295-320.
11. Wald, A. (1945). "Generalization of a theorem by von Neumann...". *Ann. of Math.*, 46:281-286.
