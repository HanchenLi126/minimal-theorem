# Komiya: Elementary Proof for Sion's Minimax Theorem (1988)

## Source
**Komiya, H.** (1988). "Elementary Proof for Sion's Minimax Theorem". *Kodai Mathematical Journal*, 11(1):5-7.

Received June 19, 1987.

---

## Overview

This short paper provides an **elementary proof** of Sion's minimax theorem that:
- Does **NOT** use Brouwer's fixed point theorem
- Does **NOT** use the KKM (Knaster-Kuratowski-Mazurkiewicz) theorem
- Uses only **basic analysis**: connectedness and compactness

---

## I. Sion's Minimax Theorem (Statement)

**Theorem (Sion, 1958)**: Let $X$ be a **compact convex** subset of a linear topological space and $Y$ a **convex** subset of a linear topological space. Let $f$ be a real-valued function on $X \times Y$ such that:

**(i)** $f(x, \cdot)$ is **upper semicontinuous** and **quasi-concave** on $Y$ for each $x \in X$

**(ii)** $f(\cdot, y)$ is **lower semicontinuous** and **quasi-convex** on $X$ for each $y \in Y$

**Then**:
$$\min_{x \in X} \sup_{y \in Y} f(x, y) = \sup_{y \in Y} \min_{x \in X} f(x, y)$$

---

## II. Previous Proofs

| Author | Year | Method |
|--------|------|--------|
| Sion | 1958 | KKM theorem (Sperner's lemma) |
| Fan | 1964 | Theorem on sets with convex sections |
| Takahashi | 1976 | Fan-Browder fixed point theorem |

> 📌 **All previous proofs** relied on topological tools like Brouwer FPT or KKM theorem.

---

## III. The Elementary Proof

### Key Lemma 1

**Lemma 1**: Under the same assumptions as Sion's theorem, for any $y_1, y_2 \in Y$ and any real number $\alpha$ with:
$$\alpha < \min_{x \in X} \max(f(x, y_1), f(x, y_2))$$

there exists $y_0 \in [y_1, y_2]$ (the line segment joining $y_1$ and $y_2$) such that:
$$\alpha < \min_{x \in X} f(x, y_0)$$

### Proof of Lemma 1

**Step 1**: Assume for contradiction that $\alpha \geq \min_{x \in X} f(x, y)$ for all $y \in [y_1, y_2]$.

**Step 2**: Choose $\beta$ with:
$$\alpha < \beta < \min_{x \in X} \max(f(x, y_1), f(x, y_2))$$

**Step 3**: Define the following sets for each $z \in [y_1, y_2]$:
$$C_z = \{x \in X : f(x, z) \leq \alpha\}$$
$$C'_z = \{x \in X : f(x, z) \leq \beta\}$$
$$A = C'_{y_1} = \{x \in X : f(x, y_1) \leq \beta\}$$
$$B = C'_{y_2} = \{x \in X : f(x, y_2) \leq \beta\}$$

**Step 4**: Properties of these sets:
- $C_z$, $C'_z$, $A$, $B$ are all **nonempty and closed** (by l.s.c. of $f(\cdot, z)$)
- $A \cap B = \emptyset$ (since $\beta < \min_x \max(f(x, y_1), f(x, y_2))$)

**Step 5**: By **quasi-concavity** of $f(x, \cdot)$:
$$f(x, z) \geq \min(f(x, y_1), f(x, y_2))$$
for $x \in X$ and $z \in [y_1, y_2]$.

Hence $C'_z \subseteq A \cup B$.

**Step 6**: Since $C'_z$ is **convex** (by quasi-convexity of $f(\cdot, z)$) and hence **connected**, and $C'_z \subseteq A \cup B$ with $A \cap B = \emptyset$, we must have:
$$C_z \subseteq C'_z \subseteq A \quad \text{or} \quad C_z \subseteq C'_z \subseteq B$$

**Step 7**: Define:
$$I = \{z \in [y_1, y_2] : C_z \subseteq A\}$$
$$J = \{z \in [y_1, y_2] : C_z \subseteq B\}$$

Then:
- $I$ and $J$ are nonempty ($y_1 \in I$ and $y_2 \in J$)
- $I \cap J = \emptyset$
- $I \cup J = [y_1, y_2]$

**Step 8**: **Claim**: $I$ is **closed** in $[y_1, y_2]$.

Let $\{z_n\}$ be a sequence in $I$ with $\lim z_n = z \in [y_1, y_2]$.

Let $x$ be any point of $C_z$. Then $f(x, z) \leq \alpha < \beta$.

By **upper semicontinuity** of $f(x, \cdot)$:
$$\overline{\lim}_{n \to \infty} f(x, z_n) \leq f(x, z) < \beta$$

Hence there exists integer $m$ with $f(x, z_m) < \beta$, i.e., $x \in C'_{z_m}$.

Since $C_{z_m} \subseteq A$ (because $z_m \in I$), we have $C'_{z_m} \subseteq A$, so $x \in A$.

Thus $C_z \subseteq A$, so $z \in I$. Hence $I$ is closed.

**Step 9**: Similarly, $J$ is **closed**.

**Step 10**: But $[y_1, y_2]$ is **connected**, and we cannot write it as a disjoint union of two nonempty closed sets.

**Contradiction!** ∎

---

### Key Lemma 2

**Lemma 2**: Under the same assumptions, for any finite $y_1, \ldots, y_n \in Y$ and any real number $\alpha$ with:
$$\alpha < \min_{x \in X} \max_{1 \leq i \leq n} f(x, y_i)$$

there exists $y_0 \in Y$ such that:
$$\alpha < \min_{x \in X} f(x, y_0)$$

### Proof of Lemma 2

**By induction on $n$**.

**Base case** ($n = 1$): Trivial.

**Induction step**: Assume the lemma holds for sets of size $< n$.

Let $X' = \{x \in X : f(x, y_n) \leq \alpha\}$, which is a **compact convex set**.

**Case 1**: If $X' = \emptyset$, take $y_0 = y_n$.

**Case 2**: If $X' \neq \emptyset$, since $\alpha < \min_{x \in X} \max_{1 \leq i \leq n} f(x, y_i)$, we have:
$$\alpha < \min_{x \in X'} \max_{1 \leq i \leq n-1} f(x, y_i)$$

Apply the induction hypothesis to $f$ restricted to $X' \times Y$:

There exists $y'_0 \in Y$ with $\alpha < \min_{x \in X'} f(x, y'_0)$.

Hence:
$$\alpha < \min_{x \in X} \max(f(x, y'_0), f(x, y_n))$$

By **Lemma 1**, there exists $y_0 \in Y$ with $\alpha < \min_{x \in X} f(x, y_0)$. ∎

---

### Proof of Sion's Theorem

**Step 1**: It is obvious that:
$$\sup_{y \in Y} \min_{x \in X} f(x, y) \leq \min_{x \in X} \sup_{y \in Y} f(x, y)$$

**Step 2**: We prove the reverse inequality.

Let $\alpha$ be any real number with:
$$\alpha < \min_{x \in X} \sup_{y \in Y} f(x, y)$$

**Step 3**: For each $y \in Y$, define:
$$X_y = \{x \in X : f(x, y) \leq \alpha\}$$

This is a **compact set** (closed subset of compact $X$).

**Step 4**: The condition $\alpha < \min_{x \in X} \sup_{y \in Y} f(x, y)$ implies:
$$\bigcap_{y \in Y} X_y = \emptyset$$

**Step 5**: By **compactness** of $X$, there exist finite $y_1, \ldots, y_n \in Y$ such that:
$$\bigcap_{i=1}^n X_{y_i} = \emptyset$$

Equivalently:
$$\alpha < \min_{x \in X} \max_{1 \leq i \leq n} f(x, y_i)$$

**Step 6**: By **Lemma 2**, there exists $y_0 \in Y$ with:
$$\alpha < \min_{x \in X} f(x, y_0)$$

**Step 7**: Therefore:
$$\alpha < \sup_{y \in Y} \min_{x \in X} f(x, y)$$

**Step 8**: Since this holds for any $\alpha < \min_{x \in X} \sup_{y \in Y} f(x, y)$:
$$\min_{x \in X} \sup_{y \in Y} f(x, y) \leq \sup_{y \in Y} \min_{x \in X} f(x, y)$$

**Q.E.D.** ∎

---

## IV. Key Ideas of the Proof

### What Makes It "Elementary"?

1. **No fixed point theorems**: Avoids Brouwer, Kakutani, Fan-Browder
2. **No KKM/Sperner**: Avoids combinatorial topology
3. **Uses only**:
   - Connectedness of line segments
   - Compactness (finite subcover property)
   - Upper/lower semicontinuity
   - Quasi-convexity/quasi-concavity

### The Core Insight

The proof exploits the **connectedness** of line segments $[y_1, y_2]$:
- Level sets $C_z$ must be contained entirely in $A$ or entirely in $B$
- This creates a partition of $[y_1, y_2]$ into two closed sets
- Connectedness forbids such a partition unless one is empty

---

## V. Comparison with Other Proofs

| Aspect | Komiya (Elementary) | Sion (1958) | Fan (1964) |
|--------|---------------------|-------------|------------|
| **Main Tool** | Connectedness | KKM theorem | Convex sections |
| **Topological Depth** | Minimal | Sperner's lemma | Brouwer FPT |
| **Proof Length** | 3 pages | 6 pages | Relies on other theorems |
| **Constructive?** | More so | No | No |

---

## VI. Summary

**Komiya's contribution**: Showed that Sion's minimax theorem can be proved using only:
1. **Connectedness** of convex sets
2. **Compactness** (finite intersection property)
3. **Semicontinuity** properties

This demystifies the theorem by removing the need for deep topological machinery.

---

## VII. References (from the paper)

1. Fan, K. (1964). "Sur un théorème minimax". *C.R. Acad. Sci. Paris*, 259:3925-3928.

2. Sion, M. (1958). "On general minimax theorems". *Pacific J. Math.*, 8:171-176.

3. Takahashi, W. (1976). "Nonlinear variational inequalities and fixed point theorems". *J. Math. Soc. Japan*, 28:168-181.

4. Terkelsen, F. (1972). "Some minimax theorems". *Math. Scand.*, 31:405-413.
