# Ekeland-Témam Convex Analysis Approach to the Minimax Theorem

## Source
This exposition is based on **Ekeland & Témam, *Convex Analysis and Variational Problems*, Chapter VI: Duality by the Minimax Theorem**

---

## I. Core Ideas Overview

The Ekeland-Témam method differs from Brouwer's fixed point theorem or the KKM lemma — it is **entirely based on tools from convex analysis**:
- Lower semicontinuity (l.s.c.) of convex functions
- Conjugate functions
- Existence of saddle points

**Core Logical Chain**:
```
Optimization problem → Write as sup-inf form → Prove inf sup = sup inf → Saddle point exists → Minimax holds
```

---

## II. Basic Setup and Definitions

### 2.1 Lagrangian Function

Let $L: \mathcal{A} \times \mathcal{B} \to \mathbb{R}$ be a real-valued function defined on $\mathcal{A} \times \mathcal{B}$.

**Proposition 1.1 (Fundamental Inequality)**:
$$\sup_{p \in \mathcal{B}} \inf_{u \in \mathcal{A}} L(u,p) \leq \inf_{u \in \mathcal{A}} \sup_{p \in \mathcal{B}} L(u,p)$$

> 📝 **Proof Idea**: For any $u \in \mathcal{A}$, $p \in \mathcal{B}$, we have $\inf_u L(u,p) \leq L(u,p) \leq \sup_p L(u,p)$. Then take sup and inf on both sides respectively.

### 2.2 Saddle Point Definition

**Definition 1.1 (Saddle Point)**:
A pair $(u, p) \in \mathcal{A} \times \mathcal{B}$ is called a **saddle point** of $L$ on $\mathcal{A} \times \mathcal{B}$ if:
$$L(u, q) \leq L(u, p) \leq L(v, p), \quad \forall v \in \mathcal{A}, \forall q \in \mathcal{B}$$

Equivalently:
- $u$ is the solution to $\min_{v \in \mathcal{A}} L(v, p)$
- $p$ is the solution to $\max_{q \in \mathcal{B}} L(u, q)$

---

## III. Necessary and Sufficient Conditions for Saddle Point Existence

### 3.1 Core Criterion

**Proposition 1.2 (Necessary and Sufficient Condition for Saddle Point Existence)**:

$L$ has a saddle point $(u, p)$ on $\mathcal{A} \times \mathcal{B}$ **if and only if**:
$$\max_{p \in \mathcal{B}} \min_{u \in \mathcal{A}} L(u,p) = \min_{u \in \mathcal{A}} \max_{p \in \mathcal{B}} L(u,p)$$

and both extrema are attained. In this case:
$$L(u, p) = \min_{u} \max_{p} L = \max_{p} \min_{u} L$$

> 📌 **This is the core of the Minimax Theorem**: inf sup = sup inf

### 3.2 Proof Outline

**Necessity** (Saddle point → Equality holds):

If $(u, p)$ is a saddle point, then:
$$\inf_{v} L(v, p) = L(u, p) = \sup_{q} L(u, q)$$

Therefore:
$$\sup_q \inf_v L(v,q) \geq \inf_v L(v,p) = L(u,p) = \sup_q L(u,q) \geq \inf_v \sup_q L(v,q)$$

Combined with the fundamental inequality, we get equality.

**Sufficiency** (Equality holds → Saddle point exists):

Suppose $\min_u \max_p L(u,p)$ is attained at $u$, and $\max_p \min_u L(u,p)$ is attained at $p$. By the equality:
$$L(u, p) \leq \max_q L(u, q) = \min_v \max_q L(v, q) = \max_q \min_v L(v, q) = \min_v L(v, p) \leq L(u, p)$$

All inequalities are equalities, hence $(u, p)$ is a saddle point.

---

## IV. Saddle Point Existence Theorems (Main Results)

### 4.1 Function Assumptions

Let $V$, $Z$ be **reflexive Banach spaces**, satisfying:

**(1.13)** $\mathcal{A} \subseteq V$ is nonempty, closed, and convex  
**(1.14)** $\mathcal{B} \subseteq Z$ is nonempty, closed, and convex  
**(1.15)** $\forall p \in \mathcal{B}$, $u \mapsto L(u, p)$ is **convex** and **lower semicontinuous** (l.s.c.)  
**(1.16)** $\forall u \in \mathcal{A}$, $p \mapsto L(u, p)$ is **concave** and **upper semicontinuous** (u.s.c.)

### 4.2 Main Existence Theorems

**Proposition 2.1 (Bounded Case)**:

If (1.13)-(1.16) hold, and:
$$(2.1) \quad \mathcal{A} \text{ and } \mathcal{B} \text{ are both bounded}$$

Then $L$ has a **saddle point** $(u, p)$ on $\mathcal{A} \times \mathcal{B}$, and:
$$\max_p \min_u L(u,p) = \min_u \max_p L(u,p) = L(u, p)$$

---

**Proposition 2.2 (Coercivity Conditions)**:

If (1.13)-(1.16) hold, and:
$$(2.10) \quad \exists p_0 \in \mathcal{B}: \lim_{\|u\| \to \infty, u \in \mathcal{A}} L(u, p_0) = +\infty$$
$$(2.11) \quad \exists u_0 \in \mathcal{A}: \lim_{\|p\| \to \infty, p \in \mathcal{B}} L(u_0, p) = -\infty$$

Then $L$ has a saddle point.

> 📝 **(2.10)** means: fixing some $p_0$, $L(u, p_0)$ is **coercive** in $u$  
> 📝 **(2.11)** means: fixing some $u_0$, $-L(u_0, p)$ is **coercive** in $p$

---

## V. Detailed Core Proof Steps

### Step 1: Bounded Case + Strict Convexity

Assume additionally:
$$(2.3) \quad \forall p \in \mathcal{B}, \; u \mapsto L(u,p) \text{ is strictly convex}$$

Since $V$ is reflexive, $\mathcal{A}$ bounded, closed, convex → $\mathcal{A}$ is **weakly compact**.

For each $p \in \mathcal{B}$, by convexity + l.s.c. + weak compactness:
$$f(p) := \min_{u \in \mathcal{A}} L(u, p) \text{ exists and is attained at a unique point } e(p)$$

### Step 2: Constructing the Optimization Sequence

The function $p \mapsto f(p) = \min_u L(u, p)$ is:
- **Concave** (as an infimum of concave functions)
- **Weakly upper semicontinuous**

Therefore there exists $\bar{p}$ such that:
$$\max_{p \in \mathcal{B}} f(p) = f(\bar{p}) = \max_p \min_u L(u, p)$$

### Step 3: Key Limit Argument

For $\lambda \in (0, 1)$, define $e_\lambda = e((1-\lambda)\bar{p} + \lambda p)$.

By concavity:
$$L(e_\lambda, (1-\lambda)\bar{p} + \lambda p) \geq (1-\lambda)L(e_\lambda, \bar{p}) + \lambda L(e_\lambda, p)$$

Rearranging:
$$\frac{L(e_\lambda, (1-\lambda)\bar{p} + \lambda p) - L(e_\lambda, \bar{p})}{\lambda} \geq L(e_\lambda, p) - L(e_\lambda, \bar{p})$$

### Step 4: Taking the Limit $\lambda \to 0$

By weak compactness, there exists a subsequence $e_{\lambda_n} \rightharpoonup u$ (weak convergence).

Key observation: this limit $u = e(\bar{p})$, independent of the choice of $p$!

Proof: By the definition of $e_\lambda$ and l.s.c.:
$$L(u, \bar{p}) \leq \liminf L(e_{\lambda_n}, \bar{p}) \leq L(e(\bar{p}), \bar{p}) = f(\bar{p})$$

Therefore $u = e(\bar{p})$.

### Step 5: Obtaining the Saddle Point

Letting $\lambda \to 0$, by u.s.c.:
$$L(u, p) - L(u, \bar{p}) \leq 0, \quad \forall p \in \mathcal{B}$$

That is, $\bar{p}$ is the solution to $\max_p L(u, p)$. Combined with the fact that $u = e(\bar{p})$ is the solution to $\min_u L(u, \bar{p})$, by Proposition 1.3:

$$\boxed{(u, \bar{p}) \text{ is a saddle point of } L}$$

### Step 6: Removing the Strict Convexity Assumption

If (2.3) does not hold, introduce a perturbation:
$$L_\varepsilon(u, p) = L(u, p) + \varepsilon \|u\|^2$$

$L_\varepsilon$ satisfies (2.3) and has a saddle point $(u_\varepsilon, p_\varepsilon)$.

By weak compactness, take a subsequence with $\varepsilon_n \to 0$: $(u_{\varepsilon_n}, p_{\varepsilon_n}) \rightharpoonup (u, p)$.

By preservation of l.s.c. and u.s.c., $(u, p)$ is a saddle point of $L$.

---

## VI. Application to Duality Problems

### 6.1 Primal and Dual Problems

**Primal Problem $\mathcal{P}$**:
$$\inf_{u \in \mathcal{A}} \sup_{p \in \mathcal{B}} L(u, p)$$

**Dual Problem $\mathcal{P}^*$**:
$$\sup_{p \in \mathcal{B}} \inf_{u \in \mathcal{A}} L(u, p)$$

### 6.2 Duality Theorem

By saddle point existence:
$$\inf \mathcal{P} = \sup \mathcal{P}^* = L(u, p)$$

**No duality gap!**

---

## VII. Comparison with Other Methods

| Aspect | Ekeland-Témam (Convex Analysis) | Brouwer/KKM (Topology) | Komiya (Elementary) |
|--------|--------------------------------|------------------------|---------------------|
| **Core Tools** | Weak compactness, l.s.c./u.s.c. | Fixed point theorems | Connectedness |
| **Space Requirements** | Reflexive Banach spaces | Finite-dimensional/compact convex | Compact convex |
| **Generalizability** | Infinite-dimensional optimization | Nash equilibrium | Finite-dimensional |
| **Computability** | Can derive numerical algorithms | Non-constructive | Non-constructive |

---

## VIII. Key References

1. **Ekeland, I. & Témam, R.** (1999). *Convex Analysis and Variational Problems*. SIAM Classics in Applied Mathematics, Chapter VI.

2. **Ky Fan** (1964). "Sur un théorème minimax". *C.R. Acad. Sci. Paris*, 259:3925-3928.

3. **Sion, M.** (1958). "On general minimax theorems". *Pacific J. Math.*, 8(1):171-176.

---

## IX. Summary: Logical Structure of the Proof

```
                    Convex Analysis Tools
                            ↓
    ┌─────────────────────────────────────────┐
    │  Assumptions:                            │
    │  • V, Z reflexive Banach spaces         │
    │  • A, B nonempty, closed, convex        │
    │  • L(·,p) convex, l.s.c.                │
    │  • L(u,·) concave, u.s.c.               │
    │  • Boundedness or coercivity conditions │
    └─────────────────────────────────────────┘
                            ↓
              Weak compactness + Semicontinuity
                            ↓
         ┌────────────────────────────────┐
         │  f(p) = min_u L(u,p) exists    │
         │  f(p) is concave and weakly u.s.c. │
         └────────────────────────────────┘
                            ↓
              max_p f(p) exists at p̄
                            ↓
              Limit argument: u = e(p̄)
                            ↓
    ┌─────────────────────────────────────────┐
    │  Conclusion: (u, p̄) is a saddle point  │
    │  max min L = min max L = L(u, p̄)       │
    └─────────────────────────────────────────┘
```

This is the complete proof framework for the Ekeland-Témam convex analysis approach!
