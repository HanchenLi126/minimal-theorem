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

#### Detailed Justification for Step 1

**Why does the minimum exist and is attained?**

This conclusion combines three key ingredients:

**Ingredient 1: $\mathcal{A}$ is weakly compact**

The logical chain:
$$V \text{ is reflexive} + \mathcal{A} \text{ bounded, closed, convex}$$
$$\Downarrow \text{ (Kakutani-Eberlein Theorem)}$$
$$\mathcal{A} \text{ is weakly compact}$$

**Ingredient 2: $L(\cdot, p)$ is weakly lower semicontinuous**

We have assumption (1.15): $u \mapsto L(u, p)$ is convex and (strongly) l.s.c.

**Key Fact**: Convex + l.s.c. $\Rightarrow$ **weakly l.s.c.**

*Proof*: A convex function is l.s.c. if and only if its epigraph is closed. By Mazur's theorem, a convex closed set is also weakly closed. Hence the epigraph is weakly closed, which means the function is weakly l.s.c.

**Ingredient 3: Weierstrass Theorem (Generalized)**

**Theorem**: Let $K$ be a compact set in some topology, and let $f: K \to \mathbb{R} \cup \{+\infty\}$ be lower semicontinuous in that topology. Then $f$ attains its minimum on $K$.

**Application to our case**:

| Requirement | Verification |
|-------------|--------------|
| $K$ is compact | $\mathcal{A}$ is compact in the **weak topology** |
| $f$ is l.s.c. | $L(\cdot, p)$ is l.s.c. in the **weak topology** |

**Conclusion**: $f(p) = \min_{u \in \mathcal{A}} L(u, p)$ **exists**!

> **What “weak” changes (and what it does not)**:  
> All compactness/continuity statements above are understood in the **weak topology** on $V$. The Weierstrass argument is the same as in the classical (strong) case: take a minimizing sequence (or net), extract a convergent subsequence (or subnet) using compactness, and use lower semicontinuity to pass to the limit.  
> In some weak topologies, compactness is not necessarily *sequential* compactness; using **nets** makes the statement fully general. Many texts write subsequences for simplicity (e.g. in separable settings or when sequential arguments suffice).

**Ingredient 4: Strict convexity implies uniqueness**

Assumption (2.3) says $u \mapsto L(u, p)$ is **strictly convex**.

**Claim**: The minimizer $e(p)$ is **unique**.

*Proof by contradiction*: Suppose $u_1 \neq u_2$ are both minimizers, i.e.,
$$L(u_1, p) = L(u_2, p) = \min_{u \in \mathcal{A}} L(u, p) = m$$

Let $\bar{u} = \frac{1}{2}(u_1 + u_2) \in \mathcal{A}$ (since $\mathcal{A}$ is convex).

By **strict convexity**:
$$L(\bar{u}, p) = L\left(\frac{1}{2}u_1 + \frac{1}{2}u_2, p\right) < \frac{1}{2}L(u_1, p) + \frac{1}{2}L(u_2, p) = m$$

This contradicts the fact that $m$ is the minimum! Hence the minimizer must be unique. ∎

**Summary of Step 1**:

| To Prove | Conditions Used |
|----------|-----------------|
| $\mathcal{A}$ weakly compact | $V$ reflexive + $\mathcal{A}$ bounded, closed, convex + Kakutani-Eberlein |
| $L(\cdot,p)$ weakly l.s.c. | $L(\cdot,p)$ convex + (strongly) l.s.c. |
| Minimum **exists** | Weak compactness + weak l.s.c. + Weierstrass |
| Minimizer **unique** | Strict convexity (2.3) |

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

Fix an arbitrary $p \in \mathcal{B}$ and, for $\lambda \in (0,1)$, set
$$p_\lambda := (1-\lambda)\bar p + \lambda p,\qquad e_\lambda := e(p_\lambda).$$
By definition of $e(\cdot)$,
$$L(e_\lambda,p_\lambda)=\min_{u\in\mathcal A}L(u,p_\lambda)=:f(p_\lambda).$$
Since $\bar p$ maximizes $f$, we have $f(p_\lambda)\le f(\bar p)$.

Using **concavity** of $p\mapsto L(e_\lambda,p)$ (assumption (1.16) in the main text),
$$L(e_\lambda,p_\lambda)\ge (1-\lambda)L(e_\lambda,\bar p)+\lambda L(e_\lambda,p).$$
Substituting $L(e_\lambda,p_\lambda)=f(p_\lambda)\le f(\bar p)$ and rearranging gives
$$(1-\lambda)L(e_\lambda,\bar p)\le f(\bar p)-\lambda L(e_\lambda,p).$$
Finally, since $f(p)=\min_{u}L(u,p)$, we have the pointwise lower bound $L(e_\lambda,p)\ge f(p)$, hence
\begin{equation}
\label{eq:step4-bound}
L(e_\lambda,\bar p)\le \frac{f(\bar p)-\lambda f(p)}{1-\lambda}.
\end{equation}

Now choose any sequence $\lambda_n\downarrow 0$. The right-hand side of \eqref{eq:step4-bound} converges to $f(\bar p)$, so we may take (for instance) $\limsup$ on the left:
$$\limsup_{n\to\infty}L(e_{\lambda_n},\bar p)\le f(\bar p)\quad\Longrightarrow\quad \liminf_{n\to\infty}L(e_{\lambda_n},\bar p)\le f(\bar p).$$

> **Remark (why $\limsup/\liminf$ appear)**: We do not know that $L(e_{\lambda_n},\bar p)$ converges, so we cannot take an ordinary limit. From a pointwise bound $a_n\le b_n$ we always have $\limsup a_n\le \limsup b_n$ (and also $\liminf a_n\le \liminf b_n$), which is why these operations are used.

By weak compactness of $\mathcal A$, the sequence $(e_{\lambda_n})\subset\mathcal A$ admits a weakly convergent subsequence (still denoted $(e_{\lambda_n})$) such that
$$e_{\lambda_n}\rightharpoonup u\quad\text{in }V.$$
By weak lower semicontinuity of $u\mapsto L(u,\bar p)$ (assumption (1.15)),
$$L(u,\bar p)\le \liminf_{n\to\infty}L(e_{\lambda_n},\bar p)\le f(\bar p).$$
But $f(\bar p)=\min_{u\in\mathcal A}L(u,\bar p)$, so necessarily $L(u,\bar p)=f(\bar p)$, i.e. $u$ is a minimizer of $L(\cdot,\bar p)$ on $\mathcal A$. Under the strict convexity assumption (2.3), that minimizer is unique, hence
$$u=e(\bar p).$$

In particular, **any** weak cluster point of $e_\lambda$ as $\lambda\downarrow 0$ must equal $e(\bar p)$, so the limit in Step 4 is independent of the choice of $p\in\mathcal B$.

### Step 5: Obtaining the Saddle Point

The key inequality used here is that, for every $\lambda\in(0,1)$ and every $p\in\mathcal B$,
\begin{equation}
\label{eq:27}
L(e_\lambda,p)\le f(\bar p).
\end{equation}
(This corresponds to inequality (2.7) in Ekeland–Témam: it follows from concavity in $p$ together with the fact that $\bar p$ maximizes $f$.)

Let $\lambda_n\downarrow 0$ and take a weakly convergent subsequence $e_{\lambda_n}\rightharpoonup u$. Step 4 shows $u=e(\bar p)$. Now fix an arbitrary $p\in\mathcal B$. By weak lower semicontinuity of $u\mapsto L(u,p)$,
$$L(u,p)\le \liminf_{n\to\infty}L(e_{\lambda_n},p).$$
Combining with \eqref{eq:27} gives
$$L(u,p)\le f(\bar p)=L(u,\bar p),\qquad \forall p\in\mathcal B.$$
Equivalently, $\bar p$ maximizes the map $p\mapsto L(u,p)$ on $\mathcal B$. Since also $u=e(\bar p)$ minimizes $u\mapsto L(u,\bar p)$ on $\mathcal A$, we obtain the saddle inequality
$$L(u,p)\le L(u,\bar p)\le L(u',\bar p),\quad \forall u'\in\mathcal A,\ \forall p\in\mathcal B.$$
Therefore,
$$\boxed{(u,\bar p)\ \text{is a saddle point of}\ L.}$$

> **Important note**: the limit passage producing $L(u,p)\le L(u,\bar p)$ uses **l.s.c. in $u$**, not u.s.c. in $p$. (The direction of the inequality matches the l.s.c. $\Rightarrow\ f(\lim)\le \liminf f(\cdot)$ principle.)

### Step 6: Removing the Strict Convexity Assumption

If the strict convexity assumption (2.3) fails, we enforce it by a standard **strongly convex perturbation**:
$$L_\varepsilon(u,p):=L(u,p)+\varepsilon\|u\|^2,\qquad \varepsilon>0.$$

#### 6.1 Why this perturbation is legitimate

1. **It creates strict convexity in $u$.**  
   For each fixed $p$, the map $u\mapsto L(u,p)$ is convex, and $u\mapsto \varepsilon\|u\|^2$ is strictly convex (e.g. on a Hilbert space; in a general reflexive Banach space one may equivalently renorm the space by a strictly convex norm). Hence $u\mapsto L_\varepsilon(u,p)$ is strictly convex, so (2.3) holds for $L_\varepsilon$.

2. **It preserves the other assumptions.**  
   The term $\varepsilon\|u\|^2$ depends only on $u$ and is continuous/convex, so it preserves weak lower semicontinuity in $u$ and does not affect concavity/upper semicontinuity in $p$. Thus $L_\varepsilon$ satisfies the same hypotheses (1.13)–(1.16) as $L$, and additionally (2.3).

Therefore, by Steps 1–5, **for each $\varepsilon>0$ there exists a saddle point $(u_\varepsilon,p_\varepsilon)$ of $L_\varepsilon$** on $\mathcal A\times\mathcal B$, i.e.
\begin{equation}
\label{eq:saddle-eps}
L_\varepsilon(u_\varepsilon,p)\le L_\varepsilon(u_\varepsilon,p_\varepsilon)\le L_\varepsilon(u,p_\varepsilon),
\quad \forall u\in\mathcal A,\ \forall p\in\mathcal B.
\end{equation}

#### 6.2 Passing to the limit $\varepsilon\downarrow 0$

Choose $\varepsilon_n\downarrow 0$ and write
$$u_n:=u_{\varepsilon_n},\quad p_n:=p_{\varepsilon_n},\quad \delta_n:=\varepsilon_n.$$
By weak compactness of $\mathcal A\times\mathcal B$, there exists a subsequence (not relabeled) such that
$$u_n\rightharpoonup u\ \text{in }V,\qquad p_n\rightharpoonup p\ \text{in }Z.$$
We claim that $(u,p)$ is a saddle point of $L$, i.e.
\begin{equation}
\label{eq:saddle-target}
L(u,p')\le L(u,p)\le L(u',p),\quad \forall u'\in\mathcal A,\ \forall p'\in\mathcal B.
\end{equation}

**Left inequality in \eqref{eq:saddle-target}.** Fix $p'\in\mathcal B$. From the left half of \eqref{eq:saddle-eps} we have, for all $n$,
$$L(u_n,p')+\delta_n\|u_n\|^2\le L(u_n,p_n)+\delta_n\|u_n\|^2,$$
hence the perturbation cancels:
\begin{equation}
\label{eq:left-pointwise}
L(u_n,p')\le L(u_n,p_n).
\end{equation}
Taking $\liminf$ and using weak l.s.c. in $u$ (for fixed $p'$) gives
$$L(u,p')\le \liminf_{n}L(u_n,p')\le \liminf_{n}L(u_n,p_n).$$
To bound $\liminf_{n}L(u_n,p_n)$ from above, use the right half of \eqref{eq:saddle-eps} with $u'=u$:
$$L(u_n,p_n)+\delta_n\|u_n\|^2\le L(u,p_n)+\delta_n\|u\|^2.$$
Dropping $\delta_n\|u_n\|^2\ge 0$ and taking $\limsup$, then using weak u.s.c. in $p$ (for fixed $u$), yields
$$\limsup_{n}L(u_n,p_n)\le \limsup_{n}L(u,p_n)\le L(u,p).$$
Since $\liminf\le \limsup$, we obtain $\liminf_{n}L(u_n,p_n)\le L(u,p)$, and therefore
$$L(u,p')\le L(u,p)\quad\forall p'\in\mathcal B.$$

**Right inequality in \eqref{eq:saddle-target}.** Fix $u'\in\mathcal A$. From the right half of \eqref{eq:saddle-eps},
$$L(u_n,p_n)+\delta_n\|u_n\|^2\le L(u',p_n)+\delta_n\|u'\|^2.$$
Dropping $\delta_n\|u_n\|^2\ge 0$ gives
$$L(u_n,p_n)\le L(u',p_n)+\delta_n\|u'\|^2.$$
Taking $\limsup$ and using $\delta_n\|u'\|^2\to 0$ together with weak u.s.c. of $p\mapsto L(u',p)$ gives
\begin{equation}
\label{eq:rhs-limsup}
\limsup_{n}L(u_n,p_n)\le L(u',p).
\end{equation}
On the other hand, taking $p'=p$ in \eqref{eq:left-pointwise} yields $L(u_n,p)\le L(u_n,p_n)$, so
$$\liminf_{n}L(u_n,p)\le \limsup_{n}L(u_n,p_n).$$
By weak l.s.c. of $u\mapsto L(u,p)$,
$$L(u,p)\le \liminf_{n}L(u_n,p),$$
hence
\begin{equation}
\label{eq:lhs-liminf}
L(u,p)\le \limsup_{n}L(u_n,p_n).
\end{equation}
Combining \eqref{eq:lhs-liminf} with \eqref{eq:rhs-limsup} gives
$$L(u,p)\le L(u',p)\quad\forall u'\in\mathcal A.$$

Together, the two parts prove \eqref{eq:saddle-target}. Thus $(u,p)$ is a saddle point of $L$, completing the removal of (2.3).

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

---

## Appendix A: Reflexive Banach Spaces

### A.1 Basic Definitions

**Banach Space**: A complete normed vector space $(V, \|\cdot\|)$.

**Dual Space**: $V^* = \{f: V \to \mathbb{R} \mid f \text{ is continuous and linear}\}$ with norm $\|f\|_{V^*} = \sup_{\|x\| \leq 1} |f(x)|$.

**Double Dual**: $V^{**} = (V^*)^*$ — the dual of the dual space.

### A.2 Canonical Embedding

There is a natural **canonical embedding** $J: V \to V^{**}$ defined by:
$$J(x)(f) = f(x), \quad \forall f \in V^*$$

**Interpretation**: Given any $x \in V$, $J(x)$ is a functional on $V^*$ that "evaluates $f$ at $x$".

**Properties of $J$**:
- **Linear**: $J(\alpha x + \beta y) = \alpha J(x) + \beta J(y)$
- **Isometric**: $\|J(x)\|_{V^{**}} = \|x\|_V$
- **Injective**: $J(x) = J(y) \Rightarrow x = y$

### A.3 Definition of Reflexivity

**Definition**: A Banach space $V$ is **reflexive** if the canonical embedding $J: V \to V^{**}$ is **surjective** (onto).

In other words: $V$ is reflexive if $J(V) = V^{**}$, meaning every element of $V^{**}$ comes from some element of $V$.

### A.4 Why Reflexivity Matters

**Theorem (Kakutani-Eberlein)**: A Banach space $V$ is reflexive **if and only if** every bounded closed convex set in $V$ is **weakly compact**.

This is the key property used in Ekeland-Témam's proof!

### A.5 Examples

**Reflexive Spaces** ✓

| Space | Description |
|-------|-------------|
| $\mathbb{R}^n$ | All finite-dimensional spaces are reflexive |
| $L^p(\Omega)$, $1 < p < \infty$ | Lebesgue spaces |
| $\ell^p$, $1 < p < \infty$ | Sequence spaces |
| $W^{k,p}(\Omega)$, $1 < p < \infty$ | Sobolev spaces |
| Hilbert spaces | $L^2$, $\ell^2$, etc. |

**Non-Reflexive Spaces** ✗

| Space | Reason |
|-------|--------|
| $L^1(\Omega)$ | $(L^1)^* = L^\infty$ but $(L^\infty)^* \supsetneq L^1$ |
| $L^\infty(\Omega)$ | Similar reason |
| $\ell^1$, $\ell^\infty$ | Dual spaces don't match |
| $C[0,1]$ | Dual is space of measures |

---

## Appendix B: Weak Topology and Weak Compactness

### B.0 How Topologies Are Generated (and how the weak topology is defined)

In the most basic topology theory, one **chooses a family of sets** and declares them to be open — but not arbitrarily: the collection of open sets must satisfy the topology axioms (contain $\varnothing$ and $V$, be closed under arbitrary unions and finite intersections).

A common construction is to start from a **subbasis** $\mathcal S\subset\mathcal P(V)$ and generate the smallest topology containing it:
1. Form all **finite intersections** of sets in $\mathcal S$ (these give a basis-like family).
2. Take **arbitrary unions** of those finite intersections. The resulting family is a topology, denoted $\langle\mathcal S\rangle$.

**Weak topology $\sigma(V,V^*)$**: the weak topology on $V$ is the **coarsest** topology making every functional $\varphi\in V^*$ continuous. Equivalently, it is generated by the subbasis
$$\mathcal S=\{\varphi^{-1}(O):\ \varphi\in V^*,\ O\subset\mathbb R\ \text{open}\}.$$
A typical basic weak neighborhood of $x_0\in V$ is
$$\{x\in V:\ |\varphi_i(x-x_0)|<\varepsilon,\ i=1,\dots,n\},$$
for some $\varphi_1,\dots,\varphi_n\in V^*$ and $\varepsilon>0$.

### B.1 Strong vs. Weak Topology

**Strong (Norm) Topology**: The usual topology on a Banach space $V$, defined by the norm. 
- Convergence: $x_n \to x$ means $\|x_n - x\| \to 0$
- This is the "default" topology

**Weak Topology**: The weakest (coarsest) topology on $V$ such that all continuous linear functionals $f \in V^*$ remain continuous.
- Convergence: $x_n \rightharpoonup x$ (weakly) means $f(x_n) \to f(x)$ for all $f \in V^*$
- Has fewer open sets than the strong topology

### B.2 Weak Convergence

**Definition**: A sequence $\{x_n\}$ in $V$ **converges weakly** to $x$, written $x_n \rightharpoonup x$, if:
$$f(x_n) \to f(x), \quad \forall f \in V^*$$

**Key Properties**:
- Strong convergence $\Rightarrow$ Weak convergence (but not conversely in infinite dimensions)
- Weak limits are unique
- Weakly convergent sequences are bounded (Uniform Boundedness Principle)

**Example in $L^2[0,1]$**: The sequence $e_n(t) = \sqrt{2}\sin(n\pi t)$ converges weakly to $0$:
$$\langle e_n, g \rangle = \int_0^1 \sqrt{2}\sin(n\pi t) g(t) dt \to 0, \quad \forall g \in L^2$$
by the Riemann-Lebesgue lemma. But $\|e_n\| = 1$ for all $n$, so $e_n \not\to 0$ strongly.

### B.3 Weak Compactness

**Definition**: A set $K \subseteq V$ is **weakly compact** if every sequence in $K$ has a subsequence that converges weakly to an element of $K$.

> **Remark (sequences vs. nets)**: In a general topological space, compactness is defined via open covers (or equivalently via **nets**), and it does not always coincide with “every sequence has a convergent subsequence”. In the weak topology, many functional analysis texts still state results sequentially for convenience; when needed, replace subsequences by subnets to obtain fully general statements.

**Key Theorem (Kakutani-Eberlein)**: In a reflexive Banach space, a set is weakly compact **if and only if** it is bounded, closed, and convex.

### B.4 Why Weak Compactness is Useful

In infinite-dimensional spaces, bounded closed sets are generally **not** compact in the strong topology (the unit ball in an infinite-dimensional Banach space is never strongly compact).

However, in reflexive spaces, bounded closed convex sets **are** weakly compact. This allows us to:
1. Extract weakly convergent subsequences from minimizing sequences
2. Apply the generalized Weierstrass theorem to guarantee existence of minima

### B.5 Weak Lower Semicontinuity

**Definition**: A function $f: V \to \mathbb{R} \cup \{+\infty\}$ is **weakly lower semicontinuous** if:
$$x_n \rightharpoonup x \Rightarrow f(x) \leq \liminf_{n \to \infty} f(x_n)$$

**Key Theorem**: If $f$ is convex and (strongly) lower semicontinuous, then $f$ is weakly lower semicontinuous.

*Proof idea*: The epigraph $\{(x, t) : f(x) \leq t\}$ is convex and strongly closed. By Mazur's theorem, convex strongly closed sets are also weakly closed. Hence $f$ is weakly l.s.c.

### B.6 Summary: Role in Minimax Proof

| Concept | Role in Proof |
|---------|---------------|
| Reflexive space | Guarantees weak compactness via Kakutani-Eberlein |
| Weak topology | Provides compactness in infinite dimensions |
| Weak compactness | Ensures minimizing sequences have convergent subsequences |
| Weak l.s.c. | Ensures limit of minimizing sequence achieves the minimum |
| Convexity + l.s.c. | Implies weak l.s.c. (key bridge) |
