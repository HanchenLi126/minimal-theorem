# Nikaidô: *On von Neumann's minimax theorem* (1954) — Proof Extraction

## Source
**Nikaidô, Hukukane** (1954). “On von Neumann’s minimax theorem.” *Pacific Journal of Mathematics*, **4**(1): 65–72.

PDF: `ON VON NEUMANN'S MINIMAX THEOREM.pdf` (uploaded)

---

## Overview (what this paper does)

Nikaidô gives an **alternative proof** of von Neumann’s minimax theorem for **possibly infinite-dimensional** strategy spaces, deriving it **directly from Brouwer’s fixed point theorem** via a **finite-dimensional reduction**—without using infinite-dimensional Kakutani-type fixed point extensions. The proof also yields:

- existence of a **saddle point** (under the paper’s assumptions),
- an explicit **finite approximation** statement (“ε-approximating finite strategy spaces”),
- and a discussion of why a **Kakutani-correspondence** approach may fail when only **separate continuity** is assumed.

(See pp. 65–66 for the motivation and setup.)

---

## Setting and hypotheses

Let \(X\subset L\) and \(Y\subset M\) be **convex compact** sets in **topological linear spaces** (Hausdorff, addition and scalar multiplication continuous).  
Let \(K:X\times Y\to\mathbb{R}\) be a payoff function that is **continuous in each variable separately** (for any fixed value of the other). (pp. 65–66)

### Quasi-structures

- **Quasi-concave in \(x\)** (for each fixed \(y\)): superlevel sets are convex:
  \[
  \{x\in X:K(x,y)\ge \lambda\}\text{ is convex for all }\lambda.
  \]
- **Quasi-convex in \(y\)** (for each fixed \(x\)): sublevel sets are convex:
  \[
  \{y\in Y:K(x,y)\le \mu\}\text{ is convex for all }\mu.
  \]
(pp. 66)

---

## Main theorem (von Neumann minimax in Nikaidô’s form)

### Theorem (von Neumann’s minimax theorem)
If \(K(x,y)\) is quasi-concave in \(x\) and quasi-convex in \(y\), then
\[
\max_{x\in X}\min_{y\in Y}K(x,y)=\min_{y\in Y}\max_{x\in X}K(x,y).
\]
(p. 66)

Nikaidô proves this by showing \(\lambda_0=\mu_0\) for two threshold values defined via uniform level sets (below), which also yields a **saddle point**.

---

## Proof extraction (core steps)

### Step 1: Uniform level sets and threshold values

For real \(\lambda,\mu\), define (p. 67):
\[
E_\lambda=\{x\in X:\ K(x,y)\ge \lambda\ \forall y\in Y\},\qquad
F_\mu=\{y\in Y:\ K(x,y)\le \mu\ \forall x\in X\}.
\]
These are closed (and convex) subsets of \(X\) and \(Y\).

Define the “best uniform levels”:
\[
\lambda_0=\sup\{\lambda: E_\lambda\neq\varnothing\},\qquad
\mu_0=\inf\{\mu: F_\mu\neq\varnothing\}.
\]
Then (for any \(x^0\in E_{\lambda_0}\), \(y^0\in F_{\mu_0}\)) we have
\[
\lambda_0 \le K(x^0,y^0)\le \mu_0.
\]
So if one can show \(\lambda_0=\mu_0\), then \((x^0,y^0)\) is a **saddle point** and minimax follows. (p. 67)

---

### Step 2: Choose an \(\varepsilon>0\) and create “gap-witness” open covers

Fix \(\varepsilon>0\) and define
\[
\bar\lambda=\lambda_0+\varepsilon,\qquad \bar\mu=\mu_0-\varepsilon.
\]
Because \(E_{\lambda_0+\varepsilon}=\varnothing\), for every \(x\in X\) there exists \(y\in Y\) such that
\[
K(x,y)<\bar\lambda. \tag{1}
\]
Because \(F_{\mu_0-\varepsilon}=\varnothing\), for every \(y\in Y\) there exists \(x\in X\) such that
\[
K(x,y)>\bar\mu. \tag{2}
\]
(p. 67–68)

Define open sets (p. 68):
\[
U_y=\{x\in X:K(x,y)<\bar\lambda\},\qquad
V_x=\{y\in Y:K(x,y)>\bar\mu\}.
\]
By separate continuity, \(U_y\) is open in \(X\) and \(V_x\) is open in \(Y\).  
Equations (1)–(2) imply open covers:
\[
X\subset \bigcup_{y\in Y}U_y,\qquad Y\subset \bigcup_{x\in X}V_x.
\]

By compactness, select finite subcovers: there exist finite point sets
\[
A=\{a_i\}_{i=1}^s\subset X,\qquad B=\{b_j\}_{j=1}^t\subset Y
\]
such that
\[
X\subset \bigcup_{j=1}^t U_{b_j},\qquad Y\subset \bigcup_{i=1}^s V_{a_i}. \tag{3–4}
\]
These yield uniform finite inequalities:
\[
\min_j K(x,b_j)<\bar\lambda\ \ \forall x\in X,\qquad
\max_i K(a_i,y)>\bar\mu\ \ \forall y\in Y.
\]
(p. 68)

---

### Step 3: Build a continuous self-map on a finite-dimensional convex set

Define nonnegative “slack” functions (p. 68):
\[
\phi_i(y)=\max\{0,\,K(a_i,y)-\bar\mu\},\qquad
\psi_j(x)=\max\{0,\,\bar\lambda-K(x,b_j)\}.
\]
Using (3–4), for every \(y\in Y\) at least one \(\phi_i(y)>0\), and for every \(x\in X\) at least one \(\psi_j(x)>0\).

Define the mapping (p. 69):
\[
(x,y)\ \longmapsto\ (\hat x,\hat y)
=
\left(
\frac{\sum_i \phi_i(y)a_i}{\sum_i \phi_i(y)}\ ,\
\frac{\sum_j \psi_j(x)b_j}{\sum_j \psi_j(x)}
\right).
\]
This is continuous (the denominators are positive by the covering property).

Let \(C(A)=\mathrm{co}(A)\subset X\) and \(C(B)=\mathrm{co}(B)\subset Y\) be convex hulls.  
The mapping sends \(C(A)\times C(B)\) into itself. Since \(C(A)\times C(B)\) is homeomorphic to a convex compact set in Euclidean space, **Brouwer’s fixed point theorem** applies. Therefore there exists \((\bar x,\bar y)\in C(A)\times C(B)\) such that \((\bar x,\bar y)=(\hat x,\hat y)\). (p. 69)

---

### Step 4: Use quasi-concavity / quasi-convexity to obtain the contradiction inequality

At the fixed point \((\bar x,\bar y)\), by construction:

- if \(\phi_i(\bar y)>0\) then \(K(a_i,\bar y)>\bar\mu\).  
  Because \(\bar x\) is a convex combination of those \(a_i\) with \(\phi_i(\bar y)>0\), **quasi-concavity in \(x\)** implies
  \[
  K(\bar x,\bar y)>\bar\mu. \tag{7}
  \]
- if \(\psi_j(\bar x)>0\) then \(K(\bar x,b_j)<\bar\lambda\).  
  Because \(\bar y\) is a convex combination of those \(b_j\) with \(\psi_j(\bar x)>0\), **quasi-convexity in \(y\)** implies
  \[
  K(\bar x,\bar y)<\bar\lambda. \tag{8}
  \]

Thus \(\bar\mu<\bar\lambda\), i.e.
\[
\mu_0-\varepsilon < \lambda_0+\varepsilon \quad\Rightarrow\quad \mu_0<\lambda_0+2\varepsilon. \tag{9}
\]
Since \(\varepsilon>0\) is arbitrary, \(\mu_0\le \lambda_0\). Together with the always-true \(\lambda_0\le \mu_0\), we get
\[
\lambda_0=\mu_0,
\]
which yields a saddle point and the minimax equality. (p. 69)

---

## Finite approximation corollary (ε-approximating finite strategy spaces)

Nikaidô shows that the convex hulls \(C(A)\) and \(C(B)\) produced above serve as **ε-approximating finite strategy spaces**: the minimax value of the restricted game differs from the original game’s value by at most \(\varepsilon\). This also has an operational meaning: each player can secure (approximately) the game value using strategies supported on a finite set. (p. 70)

---

## Why not just use Kakutani? (separate continuity vs joint continuity)

In §6, Nikaidô compares to the Kakutani-correspondence approach: if \(K\) were jointly continuous on \(X\times Y\), then best-response correspondences
\[
\Phi(x)=\arg\min_{y\in Y}K(x,y),\qquad \Psi(y)=\arg\max_{x\in X}K(x,y)
\]
are upper semicontinuous, and a fixed point of \((x,y)\mapsto \Psi(y)\times\Phi(x)\) gives a saddle point. However, under only **separate continuity**, these correspondences may fail to be upper semicontinuous, so the Kakutani-style method does **not** always apply. Nikaidô provides an example in an infinite-dimensional Hilbert space (unit sphere under weak topology) illustrating this failure. (pp. 70–72)

---

## Minimal “logical skeleton” of the proof

1. Define uniform level sets \(E_\lambda, F_\mu\) and thresholds \(\lambda_0,\mu_0\).
2. Use compactness + separate continuity to extract finite witnesses \(A,B\).
3. Construct a continuous map on \(C(A)\times C(B)\) from slack functions.
4. Apply Brouwer fixed point theorem.
5. Use quasi-concavity/convexity to force \(\mu_0\le \lambda_0\), hence equality.

---

## BibTeX

```bibtex
@article{nikaido1954von,
  author  = {Nikaid{\^o}, Hukukane},
  title   = {On von Neumann's minimax theorem},
  journal = {Pacific Journal of Mathematics},
  year    = {1954},
  volume  = {4},
  number  = {1},
  pages   = {65--72}
}
```
