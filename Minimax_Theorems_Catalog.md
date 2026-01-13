# Comprehensive Catalog of Minimax Theorems

## Overview

This document provides a systematic catalog of important minimax theorems, organized chronologically and by proof methodology. Each theorem includes precise statement, key assumptions, and primary references.

---

## Part I: Classical Minimax Theorems

### 1. Von Neumann Minimax Theorem (1928)

**Theorem**: Let $X \subseteq \mathbb{R}^m$ and $Y \subseteq \mathbb{R}^n$ be non-empty compact convex sets, and let $f: X \times Y \to \mathbb{R}$ be a function such that:
- $x \mapsto f(x, y)$ is concave and continuous for each $y \in Y$
- $y \mapsto f(x, y)$ is convex and continuous for each $x \in X$

Then:
$$\max_{x \in X} \min_{y \in Y} f(x,y) = \min_{y \in Y} \max_{x \in X} f(x,y)$$

**Primary References**:
- Von Neumann, J. (1928). "Zur Theorie der Gesellschaftsspiele". *Mathematische Annalen*, 100:295-320.
- Von Neumann, J. (1937). "Über ein ökonomisches Gleichungssystem und eine Verallgemeinerung des Brouwerschen Fixpunktsatzes". *Ergebnisse eines mathematischen Kolloquiums*, 8:73-83.

---

### 2. Ville's Theorem (1938)

**Theorem**: In a two-person zero-sum game with finite strategy sets, the minimax theorem holds with mixed strategies (probability distributions over pure strategies).

**Significance**: First published proof of Von Neumann's theorem using only elementary probability arguments.

**Primary Reference**:
- Ville, J. (1938). "Sur la théorie générale des jeux où intervient l'habileté des joueurs". In *Traité du calcul des probabilités et de ses applications* (E. Borel, ed.), Tome IV, Fasc. 2, pp. 105-113.

---

### 3. Kakutani's Generalization (1941)

**Theorem**: Let $X$ and $Y$ be non-empty compact convex subsets of $\mathbb{R}^m$ and $\mathbb{R}^n$. Let $f: X \times Y \to \mathbb{R}$ be continuous, quasi-concave in $x$, and quasi-convex in $y$. Then:
$$\max_{x \in X} \min_{y \in Y} f(x,y) = \min_{y \in Y} \max_{x \in X} f(x,y)$$

**Primary Reference**:
- Kakutani, S. (1941). "A generalization of Brouwer's fixed point theorem". *Duke Mathematical Journal*, 8(3):457-459.

---

### 4. Ky Fan Minimax Theorem (1953)

**Theorem**: Let $X$ be a compact Hausdorff space and $Y$ be a convex subset of a vector space. Let $f: X \times Y \to \mathbb{R}$ satisfy:
- For each $y \in Y$, $x \mapsto f(x, y)$ is lower semicontinuous
- For each $x \in X$, $y \mapsto f(x, y)$ is concave

Then:
$$\min_{x \in X} \sup_{y \in Y} f(x,y) = \sup_{y \in Y} \min_{x \in X} f(x,y)$$

**Primary References**:
- Fan, K. (1953). "Minimax theorems". *Proceedings of the National Academy of Sciences*, 39:42-47.
- Fan, K. (1972). "A minimax inequality and applications". In *Inequalities III* (O. Shisha, ed.), Academic Press, pp. 103-113.

---

### 5. Sion's Minimax Theorem (1958)

**Theorem**: Let $X$ be a compact convex subset of a linear topological space and $Y$ be a convex subset of a linear topological space. Let $f: X \times Y \to \mathbb{R}$ satisfy:
- For each $y \in Y$, $x \mapsto f(x, y)$ is upper semicontinuous and quasi-concave
- For each $x \in X$, $y \mapsto f(x, y)$ is lower semicontinuous and quasi-convex

Then:
$$\max_{x \in X} \inf_{y \in Y} f(x,y) = \inf_{y \in Y} \max_{x \in X} f(x,y)$$

**Significance**: Major generalization allowing quasi-concavity/quasi-convexity instead of concavity/convexity, and one set need not be compact.

**Primary Reference**:
- Sion, M. (1958). "On general minimax theorems". *Pacific Journal of Mathematics*, 8(1):171-176.

---

### 6. Nikaido's Minimax Theorem (1954)

**Theorem**: Let $C$ be a compact convex subset of $\mathbb{R}^m$ and $D$ a convex subset of $\mathbb{R}^n$. If $f: C \times D \to \mathbb{R}$ is concave-convex and upper semicontinuous in the first variable, then:
$$\max_{x \in C} \inf_{y \in D} f(x,y) = \inf_{y \in D} \max_{x \in C} f(x,y)$$

**Primary Reference**:
- Nikaido, H. (1954). "On von Neumann's minimax theorem". *Pacific Journal of Mathematics*, 4:65-72.

---

## Part II: Infinite-Dimensional Extensions

### 7. Kneser's Minimax Theorem (1952)

**Theorem**: Let $X$ be a non-empty convex compact subset of a Hausdorff topological vector space, and $Y$ a non-empty convex set. Let $f: X \times Y \to \mathbb{R}$ be concave-convex such that $f(\cdot, y)$ is upper semicontinuous for each $y$. Then:
$$\max_{x \in X} \inf_{y \in Y} f(x,y) = \inf_{y \in Y} \max_{x \in X} f(x,y)$$

**Primary Reference**:
- Kneser, H. (1952). "Sur un théorème fondamental de la théorie des jeux". *Comptes Rendus de l'Académie des Sciences Paris*, 234:2418-2420.

---

### 8. Ekeland-Témam Saddle Point Theorem (1976/1999)

**Theorem**: Let $V$, $Z$ be reflexive Banach spaces. Let $\mathcal{A} \subseteq V$ and $\mathcal{B} \subseteq Z$ be non-empty, closed, and convex. Let $L: \mathcal{A} \times \mathcal{B} \to \mathbb{R}$ satisfy:
- For each $p \in \mathcal{B}$, $u \mapsto L(u, p)$ is convex and lower semicontinuous
- For each $u \in \mathcal{A}$, $p \mapsto L(u, p)$ is concave and upper semicontinuous
- Either (i) $\mathcal{A}$ and $\mathcal{B}$ are bounded, or (ii) coercivity conditions hold

Then $L$ has a saddle point $(u, p)$ and:
$$\max_p \min_u L(u,p) = \min_u \max_p L(u,p) = L(u, p)$$

**Primary Reference**:
- Ekeland, I. & Témam, R. (1999). *Convex Analysis and Variational Problems*. SIAM Classics in Applied Mathematics, Chapter VI.

---

### 9. Rockafellar's Minimax Theorem (1970)

**Theorem**: Let $K$ be a closed proper concave-convex function on $\mathbb{R}^m \times \mathbb{R}^n$ with effective domain $C \times D$. If either $C$ or $D$ is bounded, or if there are no common directions of recession, then the saddle-value exists:
$$\inf_{v \in D} \sup_{u \in C} K(u, v) = \sup_{u \in C} \inf_{v \in D} K(u, v)$$

**Primary Reference**:
- Rockafellar, R.T. (1970). *Convex Analysis*. Princeton University Press, Part VII (Sections 33-37).

---

### 10. Aubin-Ekeland Minimax Theorem (1984)

**Theorem**: Let $X$ be a compact convex subset of a locally convex space, $Y$ a convex subset, and $f: X \times Y \to \mathbb{R}$ be concave-convex with $f(\cdot, y)$ upper semicontinuous. If $Y$ has a compact base or $f$ satisfies certain coercivity conditions, then the minimax equality holds.

**Primary Reference**:
- Aubin, J.-P. & Ekeland, I. (1984). *Applied Nonlinear Analysis*. Wiley-Interscience, Chapter 6.

---

## Part III: Fixed-Point Based Approaches

### 11. Brouwer-Based Proof (Nash, 1950)

**Approach**: Using Brouwer's fixed point theorem to prove existence of equilibrium in games, which implies minimax for two-player zero-sum games.

**Key Result**: For continuous payoff functions on compact convex strategy spaces, Nash equilibrium exists, and for zero-sum games this yields minimax equality.

**Primary References**:
- Nash, J. (1950). "Equilibrium points in n-person games". *Proceedings of the National Academy of Sciences*, 36:48-49.
- Nash, J. (1951). "Non-cooperative games". *Annals of Mathematics*, 54(2):286-295.

---

### 12. KKM-Based Proof

**Approach**: Using the KKM (Knaster-Kuratowski-Mazurkiewicz) lemma to prove minimax theorems.

**KKM Lemma**: Let $\Delta_n$ be an $n$-simplex with vertices $v_0, \ldots, v_n$. If $C_0, \ldots, C_n$ are closed sets such that every face of $\Delta_n$ is covered by the corresponding $C_i$'s, then $\bigcap_{i=0}^n C_i \neq \emptyset$.

**Primary References**:
- Knaster, B., Kuratowski, C., & Mazurkiewicz, S. (1929). "Ein Beweis des Fixpunktsatzes für n-dimensionale Simplexe". *Fundamenta Mathematicae*, 14:132-137.
- Fan, K. (1961). "A generalization of Tychonoff's fixed point theorem". *Mathematische Annalen*, 142:305-310.

---

### 13. Fan-Browder Fixed Point Theorem Approach

**Theorem (Fan-Browder)**: Let $X$ be a non-empty compact convex subset of a Hausdorff topological vector space, and let $T: X \to 2^X$ be a set-valued map such that:
- For each $x \in X$, $T(x)$ is non-empty and convex
- For each $y \in X$, $T^{-1}(y) = \{x : y \in T(x)\}$ is open

Then $T$ has a fixed point.

**Application**: This implies Ky Fan's minimax theorem and hence Sion's theorem.

**Primary References**:
- Browder, F.E. (1968). "The fixed point theory of multi-valued mappings in topological vector spaces". *Mathematische Annalen*, 177:283-301.
- Takahashi, W. (1976). "Nonlinear variational inequalities and fixed point theorems". *Journal of the Mathematical Society of Japan*, 28:168-181.

---

## Part IV: Elementary Proofs

### 14. Komiya's Elementary Proof (1988)

**Approach**: Proves Sion's minimax theorem using only elementary analysis (connectedness and compactness arguments), avoiding all fixed-point theorems.

**Key Lemma**: For any $y_1, y_2 \in Y$ and $\alpha < \min_x \max(f(x,y_1), f(x,y_2))$, there exists $y_0 \in [y_1, y_2]$ such that $\alpha < \min_x f(x, y_0)$.

**Primary Reference**:
- Komiya, H. (1988). "Elementary proof for Sion's minimax theorem". *Kodai Mathematical Journal*, 11(1):5-7.

---

### 15. Kindler's Elementary Proof (2005)

**Approach**: Another elementary proof avoiding topological methods.

**Primary Reference**:
- Kindler, J. (2005). "A simple proof of Sion's minimax theorem". *American Mathematical Monthly*, 112(4):356-358.

---

### 16. Ghouila-Houri's Proof (1966)

**Approach**: Elementary proof using Helly's theorem on convex sets.

**Primary Reference**:
- Ghouila-Houri, A. (1966). "Sur la généralisation de la notion de commande d'un système guidable". *Revue française d'informatique et de recherche opérationnelle*, 1(4):7-32.

---

## Part V: Equivalence Theorems

### 17. Sperner ⟺ KKM ⟺ Brouwer Equivalence

**Equivalence Chain**:
$$\text{Sperner's Lemma} \Longleftrightarrow \text{KKM Lemma} \Longleftrightarrow \text{Brouwer Fixed Point Theorem}$$

**Historical Development**:
- Sperner → KKM → Brouwer: Knaster, Kuratowski, Mazurkiewicz (1929)
- Brouwer → Sperner: Yoseloff (1974)

**Primary References**:
- Sperner, E. (1928). "Neuer Beweis für die Invarianz der Dimensionszahl und des Gebietes". *Abhandlungen aus dem Mathematischen Seminar der Universität Hamburg*, 6:265-272.
- Yoseloff, M. (1974). "Topological proofs of some combinatorial theorems". *Journal of Combinatorial Theory, Series A*, 17:95-111.

---

### 18. Minimax ⟺ Fixed Point Equivalences

**Key Equivalences**:
- Von Neumann Minimax ⟺ Brouwer Fixed Point (in appropriate settings)
- Ky Fan Minimax ⟺ KKM Lemma
- Sion Minimax ⟺ Fan-Browder Fixed Point

**Primary Reference**:
- Border, K.C. (1985). *Fixed Point Theorems with Applications to Economics and Game Theory*. Cambridge University Press.

---

## Part VI: Generalizations and Extensions

### 19. König's Minimax Theorems (1968, 1992)

**Approach**: Systematic development of minimax theory using convexity structures.

**Primary References**:
- König, H. (1968). "Über das von Neumannsche Minimax-Theorem". *Archiv der Mathematik*, 19:482-487.
- König, H. (1992). "On certain applications of the Hahn-Banach and minimax theorems". *Archiv der Mathematik*, 58:289-302.

---

### 20. Simons' Minimax Theorems (1995)

**Approach**: Uses monotonicity methods and provides unified treatment of various minimax theorems.

**Primary Reference**:
- Simons, S. (1995). "Minimax theorems and their proofs". In *Minimax and Applications* (D.-Z. Du & P.M. Pardalos, eds.), Kluwer, pp. 1-23.

---

### 21. Greco's Minimax Theorem (1984)

**Theorem**: Minimax theorem for functions that are not necessarily concave-convex but satisfy certain intersection properties.

**Primary Reference**:
- Greco, G.H. (1984). "Minimax theorems and saddling transformations". *Journal of Mathematical Analysis and Applications*, 104:409-419.

---

### 22. Ha's Minimax Theorem (1980)

**Theorem**: Extension to functions on arbitrary topological spaces using generalized convexity.

**Primary Reference**:
- Ha, C.W. (1980). "Minimax and fixed point theorems". *Mathematische Annalen*, 248:73-77.

---

### 23. Tuy's Minimax Theorem (1974)

**Approach**: Minimax theorems via separation arguments for non-convex sets.

**Primary Reference**:
- Tuy, H. (1974). "On the general minimax theorem". *Colloquium Mathematicum*, 33:145-158.

---

## Part VII: Applications and Special Cases

### 24. Minimax in Zero-Sum Games

**Classical Application**: Two-player zero-sum games with mixed strategies.

**Primary References**:
- Luce, R.D. & Raiffa, H. (1957). *Games and Decisions*. Wiley, Chapter 4.
- Owen, G. (2013). *Game Theory*. 4th ed., Emerald, Chapters 3-4.

---

### 25. Minimax in Statistical Decision Theory

**Application**: Minimax estimators and decision rules.

**Primary References**:
- Wald, A. (1950). *Statistical Decision Functions*. Wiley.
- Ferguson, T.S. (1967). *Mathematical Statistics: A Decision Theoretic Approach*. Academic Press.

---

### 26. Minimax in Optimization (Duality)

**Connection**: Strong duality in convex optimization is equivalent to minimax equality for the Lagrangian.

**Primary References**:
- Rockafellar, R.T. (1974). *Conjugate Duality and Optimization*. SIAM.
- Boyd, S. & Vandenberghe, L. (2004). *Convex Optimization*. Cambridge University Press, Chapter 5.

---

## Part VIII: Comprehensive References

### Textbooks and Monographs

| Author(s) | Title | Year | Focus |
|-----------|-------|------|-------|
| Aubin & Ekeland | *Applied Nonlinear Analysis* | 1984 | Functional analysis approach |
| Border | *Fixed Point Theorems with Applications* | 1985 | Equivalences, economics |
| Ekeland & Témam | *Convex Analysis and Variational Problems* | 1999 | Infinite-dimensional, optimization |
| Granas & Dugundji | *Fixed Point Theory* | 2003 | Comprehensive fixed point methods |
| Rockafellar | *Convex Analysis* | 1970 | Conjugacy approach |
| Rockafellar & Wets | *Variational Analysis* | 1998 | Modern treatment |
| Simons | *From Hahn-Banach to Monotonicity* | 2008 | Unified approach |
| Zeidler | *Nonlinear Functional Analysis* | 1985 | Vol. III, minimax methods |

### Survey Articles

| Author(s) | Title | Year | Journal/Book |
|-----------|-------|------|--------------|
| Simons | "Minimax theorems and their proofs" | 1995 | *Minimax and Applications* |
| König | "On some basic theorems in convex analysis" | 1999 | *Optimization & Related Topics* |
| Ricceri | "Recent advances in minimax theory" | 2000 | *Pareto Optimality* |

### Key Original Papers (Chronological)

| Year | Author(s) | Title | Significance |
|------|-----------|-------|--------------|
| 1928 | Von Neumann | "Zur Theorie der Gesellschaftsspiele" | Original minimax theorem |
| 1928 | Sperner | "Neuer Beweis für die Invarianz..." | Sperner's lemma |
| 1929 | KKM | "Ein Beweis des Fixpunktsatzes..." | KKM lemma |
| 1938 | Ville | "Sur la théorie générale des jeux..." | First published proof |
| 1941 | Kakutani | "A generalization of Brouwer's fixed point" | Set-valued fixed point |
| 1950 | Nash | "Equilibrium points in n-person games" | Game theory application |
| 1952 | Kneser | "Sur un théorème fondamental..." | Infinite-dimensional |
| 1953 | Ky Fan | "Minimax theorems" | PNAS paper |
| 1958 | Sion | "On general minimax theorems" | Quasi-convexity |
| 1961 | Ky Fan | "A generalization of Tychonoff's..." | KKM generalization |
| 1972 | Ky Fan | "A minimax inequality and applications" | Fan's inequality |
| 1974 | Yoseloff | "Topological proofs..." | Brouwer → Sperner |
| 1988 | Komiya | "Elementary proof for Sion's..." | No fixed points needed |

---

## Part IX: Quick Reference Guide

### By Assumption Strength (Weakest to Strongest)

1. **Sion (1958)**: Quasi-concave/quasi-convex, one compact
2. **Ky Fan (1953)**: Concave-convex, compact Hausdorff
3. **Kneser (1952)**: Concave-convex, compact convex in TVS
4. **Von Neumann (1928)**: Concave-convex, continuous, both compact

### By Proof Method

| Method | Key Theorems | Primary Tools |
|--------|--------------|---------------|
| **Fixed Point** | Nash, KKM-based | Brouwer, Kakutani, KKM |
| **Convex Analysis** | Ekeland-Témam, Rockafellar | Hahn-Banach, conjugacy |
| **Elementary** | Komiya, Kindler | Connectedness, compactness |
| **Algebraic** | König | Convexity structures |

### By Application Domain

| Domain | Relevant Theorems | Key References |
|--------|------------------|----------------|
| **Game Theory** | Von Neumann, Nash | Luce & Raiffa (1957) |
| **Optimization** | Rockafellar, Ekeland-Témam | Boyd & Vandenberghe (2004) |
| **Statistics** | Minimax decision | Wald (1950) |
| **Economics** | Equilibrium theory | Border (1985) |
| **Control Theory** | $H_\infty$ control | Başar & Bernhard (1995) |

---

## Part X: Summary Table

| # | Theorem | Year | Key Assumptions | Proof Type |
|---|---------|------|-----------------|------------|
| 1 | Von Neumann | 1928 | Compact, convex, continuous, concave-convex | Fixed point |
| 2 | Ville | 1938 | Finite strategies, mixed | Probabilistic |
| 3 | Kakutani | 1941 | Compact, convex, quasi-cc | Fixed point |
| 4 | Kneser | 1952 | Compact TVS, concave-convex | Separation |
| 5 | Ky Fan | 1953 | Compact Hausdorff, concave-convex | KKM |
| 6 | Nikaido | 1954 | Compact convex, u.s.c. | Direct |
| 7 | Sion | 1958 | One compact, quasi-cc, s.c. | KKM/Elementary |
| 8 | Rockafellar | 1970 | Closed proper, recession | Conjugacy |
| 9 | Ekeland-Témam | 1976 | Reflexive Banach, coercive | Weak compactness |
| 10 | Komiya | 1988 | Same as Sion | Elementary |

---

*Document compiled for Project 1: Minimax Theorem Proof Methods*
*Last updated: January 2026*
