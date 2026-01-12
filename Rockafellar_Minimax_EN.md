# Rockafellar's Convex Analysis Approach to Minimax Theory

## Source
This exposition is based on **R.T. Rockafellar, *Convex Analysis*, Princeton University Press, 1970, Part VII: Saddle-Functions and Minimax Theory (Sections 33-37)**

---

## I. Core Ideas Overview

Rockafellar's approach to minimax theory is fundamentally different from both the Ekeland-Témam functional analytic approach and the topological fixed-point methods. His framework is built on:

- **Saddle-functions** (concave-convex bifunctions)
- **Conjugacy theory** for saddle-functions (extending Fenchel conjugacy)
- **Closure operations** and equivalence classes
- **Subdifferential calculus** for saddle-functions

**Core Logical Chain**:
```
Concave-convex function K → Closure operations cl₁, cl₂ → Equivalence classes Ω(F)
→ Conjugate saddle-functions K*, K̄* → Minimax equality via conjugacy correspondence
```

---

## II. Basic Setup and Definitions

### 2.1 Concave-Convex Functions (Saddle-Functions)

**Definition**: A function $K: R^m \times R^n \to [-\infty, +\infty]$ is called **concave-convex** if:
- For each $v \in R^n$, the function $u \mapsto K(u, v)$ is concave
- For each $u \in R^m$, the function $v \mapsto K(u, v)$ is convex

**Effective Domain**:
$$\text{dom}_1 K = \{u \mid K(u, v) > -\infty, \forall v\}$$
$$\text{dom}_2 K = \{v \mid K(u, v) < +\infty, \forall u\}$$
$$\text{dom } K = \text{dom}_1 K \times \text{dom}_2 K$$

### 2.2 Saddle-Value and Saddle-Point

**Definition (Saddle-Value)**: If the quantities
$$\sup_{u \in C} \inf_{v \in D} K(u, v) \quad \text{and} \quad \inf_{v \in D} \sup_{u \in C} K(u, v)$$
are equal, this common value is called the **saddle-value** (or **minimax value**) of $K$.

**Definition (Saddle-Point)**: A point $(\bar{u}, \bar{v}) \in C \times D$ is a **saddle-point** of $K$ if:
$$K(u, \bar{v}) \leq K(\bar{u}, \bar{v}) \leq K(\bar{u}, v), \quad \forall u \in C, \forall v \in D$$

---

## III. Fundamental Inequality and Saddle-Point Criterion

### 3.1 Lemma 36.1 (Fundamental Inequality)

**Lemma 36.1**: If $K$ is any function from a non-empty product set $C \times D$ to $[-\infty, +\infty]$, then:
$$\sup_{u \in C} \inf_{v \in D} K(u, v) \leq \inf_{v \in D} \sup_{u \in C} K(u, v)$$

**Proof**: Let $f(u) = \inf_{v \in D} K(u, v)$ and $\alpha = \sup_{u \in C} f(u)$. For each $v \in D$, we have $K(u, v) \geq f(u)$ for every $u \in C$, hence $\sup_{u \in C} K(u, v) \geq \alpha$. Therefore $\inf_{v \in D} \sup_{u \in C} K(u, v) \geq \alpha$. ∎

### 3.2 Lemma 36.2 (Saddle-Point Characterization)

**Lemma 36.2**: A point $(\bar{u}, \bar{v})$ is a saddle-point of $K$ (with respect to maximizing over $C$ and minimizing over $D$) **if and only if**:

1. The supremum $\sup_{u \in C} \inf_{v \in D} K(u, v)$ is attained at $\bar{u}$
2. The infimum $\inf_{v \in D} \sup_{u \in C} K(u, v)$ is attained at $\bar{v}$
3. These two extrema are **equal**

In this case, the saddle-value is $K(\bar{u}, \bar{v})$.

---

## IV. Closure Operations and Equivalence Classes

### 4.1 Closure Operations

Rockafellar introduces two closure operations for concave-convex functions:

**Lower Closure** $\text{cl}_1 K$: For each $v$, take the closure of the concave function $K(\cdot, v)$

**Upper Closure** $\text{cl}_2 K$: For each $u$, take the closure of the convex function $K(u, \cdot)$

**Key Property**: In general, $\text{cl}_1 \text{cl}_2 K \neq \text{cl}_2 \text{cl}_1 K$ (the operations don't commute).

### 4.2 Equivalence Classes

**Definition**: Two concave-convex functions $K$ and $L$ on $R^m \times R^n$ are **equivalent** if:
$$\text{cl}_1 K = \text{cl}_1 L \quad \text{and} \quad \text{cl}_2 K = \text{cl}_2 L$$

**Theorem 34.2**: Given any closed convex bifunction $F$ from $R^m$ to $R^n$, let
$$\underline{K}(u, x^*) = \langle Fu, x^* \rangle, \quad \bar{K}(u, x^*) = \langle u, F^*x^* \rangle$$

and let $\Omega(F)$ be the collection of all concave-convex functions $K$ on $R^m \times R^n$ such that $\underline{K} \leq K \leq \bar{K}$. Then $\Omega(F)$ is an **equivalence class** (containing $\underline{K}$ and $\bar{K}$), and all functions in $\Omega(F)$ are closed.

---

## V. Conjugate Saddle-Functions

### 5.1 Definition of Conjugates

For a concave-convex function $K$ on $R^m \times R^n$, Rockafellar defines:

**Lower Conjugate**:
$$\underline{K}^*(u^*, v^*) = \sup_v \inf_u \{\langle u, u^* \rangle + \langle v, v^* \rangle - K(u, v)\}$$

**Upper Conjugate**:
$$\bar{K}^*(u^*, v^*) = \inf_u \sup_v \{\langle u, u^* \rangle + \langle v, v^* \rangle - K(u, v)\}$$

**Key Observation**: By Lemma 36.1, we always have $\underline{K}^* \leq \bar{K}^*$.

### 5.2 Theorem 37.1 (Main Conjugacy Result)

**Theorem 37.1**: Let $F$ be a closed convex bifunction from $R^m$ to $R^n$, and let $K$ be any one of the closed concave-convex functions in the equivalence class $\Omega(F)$ corresponding to $F$, i.e., any concave-convex function on $R^m \times R^n$ such that:
$$\langle Fu, x^* \rangle \leq K(u, x^*) \leq \langle u, F^*x^* \rangle, \quad \forall u, \forall x^*$$

Then, for every $u^* \in R^m$ and $x \in R^n$:
$$\inf_u \sup_{x^*} \{\langle u, u^* \rangle + \langle x, x^* \rangle - K(u, x^*)\} = \langle u^*, F_*x \rangle$$
$$\sup_{x^*} \inf_u \{\langle u, u^* \rangle + \langle x, x^* \rangle - K(u, x^*)\} = \langle F_*^*u^*, x \rangle$$

**Proof Idea**: This follows from the definition of the inverse operation and the properties of the equivalence class $\Omega(F)$ in Theorem 34.2. ∎

---

## VI. Corollary 37.1.1 (Conjugate Equivalence)

**Corollary 37.1.1**: Let $K$ be any closed concave-convex function on $R^m \times R^n$. The lower conjugate $\underline{K}^*$ of $K$ is then a lower closed concave-convex function on $R^m \times R^n$, and the upper conjugate $\bar{K}^*$ of $K$ is an upper closed concave-convex function on $R^m \times R^n$.

Moreover, $\underline{K}^*$ and $\bar{K}^*$ are **equivalent**, and they depend only on the equivalence class containing $K$.

If $K^*$ is any closed concave-convex function equivalent to $\underline{K}^*$ and $\bar{K}^*$, the lower and upper conjugates of $K^*$ are in turn equivalent to $K$.

---

## VII. Main Minimax Existence Theorems

### 7.1 Theorem 36.3 (Minimax for Closed Proper Saddle-Functions)

**Theorem 36.3**: Let $K$ be a closed proper concave-convex function on $R^m \times R^n$, and let $C = \text{dom}_1 K$ and $D = \text{dom}_2 K$. Then:
$$\sup_{u \in R^m} \inf_{v \in R^n} K(u, v) = \sup_{u \in C} \inf_{v \in D} K(u, v)$$
$$\inf_{v \in R^n} \sup_{u \in R^m} K(u, v) = \inf_{v \in D} \sup_{u \in C} K(u, v)$$

**Proof**: For a convex function $f$ on $R^n$, one has:
$$\inf\{f(v) \mid v \in R^n\} = \inf\{f(v) \mid v \in D\}$$
for any set $D$ containing $\text{ri}(\text{dom } f)$ (Corollary 7.3.1). The domain relations in Theorem 34.3 then give the result. ∎

### 7.2 Corollary 37.1.3 (Minimax Equality Criterion)

**Corollary 37.1.3**: Let $K$ be a closed proper concave-convex function on $R^m \times R^n$, and let $C^* \times D^*$ be the common effective domain of the concave-convex functions conjugate to $K$. If either:
- $\text{ri } C^*$ contains the origin of $R^m$, **or**
- $\text{ri } D^*$ contains the origin of $R^n$

then:
$$\inf_v \sup_u K(u, v) = \sup_u \inf_v K(u, v)$$

If **both** conditions hold, this saddle-value must be finite.

### 7.3 Corollary 37.3.1 (Bounded Domain Case)

**Corollary 37.3.1**: Let $K$ be a closed proper concave-convex function on $R^m \times R^n$ with effective domain $C \times D$. If either $C$ or $D$ is **bounded**, the saddle-value of $K$ exists.

**Proof**: The effective domain of $K(u, \cdot)$ is $D$ for every $u \in \text{ri } C$ by Theorem 34.3, so condition (a) [boundedness of $D$] is fulfilled when $D$ is bounded. Similarly, condition (b) is fulfilled when $C$ is bounded. ∎

### 7.4 Corollary 37.3.2 (Classical Minimax Theorem)

**Corollary 37.3.2**: Let $C$ and $D$ be non-empty closed convex sets in $R^m$ and $R^n$, respectively, and let $K$ be a **continuous finite concave-convex function** on $C \times D$. If either $C$ or $D$ is **bounded**, one has:
$$\inf_{v \in D} \sup_{u \in C} K(u, v) = \sup_{u \in C} \inf_{v \in D} K(u, v)$$

**Proof**: Apply Corollary 37.3.1 to the lower (or upper) simple extension of $K$ to all of $R^m \times R^n$, which is a closed proper concave-convex function with effective domain $C \times D$ by Corollary 34.2.4. ∎

> 📌 **This is Rockafellar's version of the Von Neumann Minimax Theorem!**

---

## VIII. Theorem 37.3 (Recession Conditions)

**Theorem 37.3**: Let $K$ be a closed proper concave-convex function on $R^m \times R^n$ with effective domain $C \times D$. Then **either** of the following conditions implies that the saddle-value of $K$ exists. If **both** conditions hold, the saddle-value must be finite.

**(a)** The convex functions $K(u, \cdot)$ for $u \in \text{ri } C$ have **no common direction of recession**.

**(b)** The convex functions $-K(\cdot, v)$ for $v \in \text{ri } D$ have **no common direction of recession**.

**Proof**: This simply combines Corollary 37.1.3 and Corollary 37.2.1. ∎

---

## IX. Subdifferential Characterization of Saddle-Points

### 9.1 Theorem 37.4

**Theorem 37.4**: Let $K$ be a concave-convex function on $R^m \times R^n$. For each $(u, v)$, the subdifferential $\partial K(u, v)$ consists of the pairs $(u^*, v^*)$ such that the concave-convex function:
$$K - \langle \cdot, u^* \rangle - \langle \cdot, v^* \rangle$$
has $(u, v)$ as a saddle-point.

If $K$ is closed and proper, one has:
$$\text{ri}(\text{dom } K) \subset \text{dom } \partial K \subset \text{dom } K$$

### 9.2 Corollary 37.4.1

**Corollary 37.4.1**: If $K$ and $L$ are equivalent saddle-functions on $R^m \times R^n$, then $\partial K = \partial L$. Moreover, the values of $K$ and $L$ agree on the set $\text{dom } \partial K = \text{dom } \partial L$.

**Proof**: For any $(u^*, v^*)$, the saddle-functions $K_0 = K - \langle \cdot, u^* \rangle - \langle \cdot, v^* \rangle$ and $L_0 = L - \langle \cdot, u^* \rangle - \langle \cdot, v^* \rangle$ are equivalent. Since equivalent saddle-functions have the same saddle-value and saddle-points (Theorem 36.4), one has $(u^*, v^*) \in \partial K(u, v)$ if and only if $(u^*, v^*) \in \partial L(u, v)$. ∎

---

## X. Theorem 37.5 (Saddle-Point Equivalence)

**Theorem 37.5**: Let $K$ be a closed proper concave-convex function on $R^m \times R^n$, and let $K^*$ be one of the equivalent concave-convex functions conjugate to $K$. Let $F$ be the (unique) closed proper convex bifunction from $R^m$ to $R^n$ such that $(\text{cl}_2 K)(u, v) = \langle Fu, v \rangle$, and let $f$ be the graph function of $F$ on $R^{m+n}$, i.e.:
$$f(u, v^*) = \sup_v \{\langle v, v^* \rangle - K(u, v)\}$$

Then the following conditions on $(u, v)$ and $(u^*, v^*)$ are **equivalent**:

**(a)** $(u^*, v^*) \in \partial K(u, v)$

**(b)** $(u, v) \in \partial K^*(u^*, v^*)$

**(c)** $(-u^*, v) \in \partial f(u, v^*)$

**(d)** $(Fu)(v^*) - \langle v, v^* \rangle = (F^*v)(u^*) - \langle u, u^* \rangle$

**Proof**: We show (a) implies (d). By definition, $v^* \in \partial_2 K(u, v)$ if and only if the supremum of $\langle \cdot, v^* \rangle - K(u, \cdot)$ on $R^n$ is attained at $v$. This supremum is $(Fu)(v^*)$, since the convex function $Fu$ is conjugate to the closure of $K(u, \cdot)$. Thus $v^* \in \partial_2 K(u, v)$ if and only if:
$$\langle v, v^* \rangle - K(u, v) = (Fu)(v^*)$$

By a dual argument, $u^* \in \partial_1 K(u, v)$ if and only if:
$$\langle u, u^* \rangle - K(u, v) = (F^*v)(u^*)$$

Thus $(u^*, v^*) \in \partial K(u, v)$ if and only if condition (d) holds. The equivalence with (b) and (c) follows similarly. ∎

---

## XI. Summary: Logical Structure of Rockafellar's Proof

```
                    Convex Bifunction Theory
                            ↓
    ┌─────────────────────────────────────────────────┐
    │  Setup:                                          │
    │  • K: R^m × R^n → [-∞, +∞] concave-convex       │
    │  • Closure operations cl₁, cl₂                  │
    │  • Equivalence classes Ω(F)                     │
    │  • Conjugate functions K*, K̄*                   │
    └─────────────────────────────────────────────────┘
                            ↓
              Conjugacy Correspondence (Theorem 37.1)
                            ↓
         ┌────────────────────────────────────────────┐
         │  Key Result: Lower and upper conjugates    │
         │  K* and K̄* are equivalent and depend      │
         │  only on the equivalence class of K        │
         └────────────────────────────────────────────┘
                            ↓
              Domain Characterization (Theorem 37.2)
                            ↓
    ┌─────────────────────────────────────────────────┐
    │  Minimax Criterion (Corollary 37.1.3):          │
    │  If 0 ∈ ri C* or 0 ∈ ri D*, then               │
    │  inf sup K = sup inf K                          │
    └─────────────────────────────────────────────────┘
                            ↓
              Boundedness/Recession Conditions
                            ↓
    ┌─────────────────────────────────────────────────┐
    │  Conclusions:                                    │
    │  • Bounded domain ⟹ saddle-value exists        │
    │  • No common recession direction ⟹ exists      │
    │  • Von Neumann theorem as special case          │
    └─────────────────────────────────────────────────┘
```

---

## XII. Comparison with Other Methods

| Aspect | Rockafellar (Conjugacy) | Ekeland-Témam (Functional) | Brouwer/KKM (Topological) |
|--------|------------------------|---------------------------|--------------------------|
| **Core Framework** | Saddle-function conjugacy | Weak compactness + semicontinuity | Fixed point theorems |
| **Key Tool** | Closure operations cl₁, cl₂ | Reflexive Banach spaces | Brouwer/Kakutani FPT |
| **Minimax Criterion** | 0 ∈ ri(conjugate domain) | Coercivity conditions | Compactness |
| **Space Setting** | Finite-dimensional $R^n$ | Infinite-dimensional Banach | Compact convex sets |
| **Duality Theory** | Central role | Central role | Not used directly |
| **Computational** | Algorithmic (subgradients) | Numerical algorithms | Non-constructive |

---

## XIII. Key References

1. **Rockafellar, R.T.** (1970). *Convex Analysis*. Princeton University Press. Part VII, Sections 33-37.

2. **Rockafellar, R.T.** (1970). "Monotone operators and the proximal point algorithm". *SIAM J. Control Optim.*, 14:877-898.

3. **Fenchel, W.** (1949). "On conjugate convex functions". *Canad. J. Math.*, 1:73-77.

4. **Von Neumann, J.** (1928). "Zur Theorie der Gesellschaftsspiele". *Math. Ann.*, 100:295-320.

---

## XIV. Key Takeaways

1. **Algebraic Approach**: Rockafellar's method is fundamentally algebraic, based on conjugacy operations rather than topological fixed-point theorems or functional-analytic weak compactness.

2. **Equivalence Classes**: The insight that saddle-values and saddle-points depend only on equivalence classes (not individual functions) is powerful and elegant.

3. **Unified Framework**: The conjugacy theory for saddle-functions unifies:
   - Von Neumann minimax theorem
   - Fenchel duality
   - Lagrangian duality in optimization
   - Kuhn-Tucker theory

4. **Finite-Dimensional Focus**: Unlike Ekeland-Témam, Rockafellar works in $R^n$ but achieves great depth through the conjugacy structure.

5. **Subdifferential Connection**: The characterization via subdifferentials (Theorem 37.4, 37.5) provides computable optimality conditions.
