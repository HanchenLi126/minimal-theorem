# Ekeland-Témam 凸分析方法证明 Minimax 定理

## 讲解来源
本讲解基于 **Ekeland & Témam, *Convex Analysis and Variational Problems*, Chapter VI: Duality by the Minimax Theorem**

---

## 一、核心思想概述

Ekeland-Témam 的方法与 Brouwer 不动点或 KKM 引理不同，它**完全基于凸分析的工具**：
- 凸函数的下半连续性 (l.s.c.)
- 共轭函数 (conjugate functions)
- 鞍点 (saddle point) 的存在性

**核心逻辑链**：
```
优化问题 → 写成 sup-inf 形式 → 证明 inf sup = sup inf → 鞍点存在 → Minimax 成立
```

---

## 二、基本设定与定义

### 2.1 Lagrangian 函数

设 $L: \mathcal{A} \times \mathcal{B} \to \mathbb{R}$ 是定义在 $\mathcal{A} \times \mathcal{B}$ 上的实值函数。

**Proposition 1.1 (基本不等式)**：
$$\sup_{p \in \mathcal{B}} \inf_{u \in \mathcal{A}} L(u,p) \leq \inf_{u \in \mathcal{A}} \sup_{p \in \mathcal{B}} L(u,p)$$

> 📝 **证明思路**：对任意 $u \in \mathcal{A}$, $p \in \mathcal{B}$，有 $\inf_u L(u,p) \leq L(u,p) \leq \sup_p L(u,p)$，然后对两边分别取 sup 和 inf。

### 2.2 鞍点定义

**Definition 1.1 (Saddle Point)**：
称 $(u, p) \in \mathcal{A} \times \mathcal{B}$ 是 $L$ 在 $\mathcal{A} \times \mathcal{B}$ 上的**鞍点**，如果：
$$L(u, q) \leq L(u, p) \leq L(v, p), \quad \forall v \in \mathcal{A}, \forall q \in \mathcal{B}$$

等价地：
- $u$ 是 $\min_{v \in \mathcal{A}} L(v, p)$ 的解
- $p$ 是 $\max_{q \in \mathcal{B}} L(u, q)$ 的解

---

## 三、鞍点存在的充要条件

### 3.1 核心判据

**Proposition 1.2 (鞍点存在的充要条件)**：

$L$ 在 $\mathcal{A} \times \mathcal{B}$ 上存在鞍点 $(u, p)$ **当且仅当**：
$$\max_{p \in \mathcal{B}} \min_{u \in \mathcal{A}} L(u,p) = \min_{u \in \mathcal{A}} \max_{p \in \mathcal{B}} L(u,p)$$

且两边的极值都能达到。此时：
$$L(u, p) = \min_{u} \max_{p} L = \max_{p} \min_{u} L$$

> 📌 **这就是 Minimax 定理的核心**：inf sup = sup inf

### 3.2 证明要点

**必要性**（鞍点 → 等式成立）：

若 $(u, p)$ 是鞍点，则：
$$\inf_{v} L(v, p) = L(u, p) = \sup_{q} L(u, q)$$

因此：
$$\sup_q \inf_v L(v,q) \geq \inf_v L(v,p) = L(u,p) = \sup_q L(u,q) \geq \inf_v \sup_q L(v,q)$$

结合基本不等式，得到等式成立。

**充分性**（等式成立 → 鞍点存在）：

设 $\min_u \max_p L(u,p)$ 在 $u$ 处达到，$\max_p \min_u L(u,p)$ 在 $p$ 处达到。由等式：
$$L(u, p) \leq \max_q L(u, q) = \min_v \max_q L(v, q) = \max_q \min_v L(v, q) = \min_v L(v, p) \leq L(u, p)$$

所有不等式都是等式，故 $(u, p)$ 是鞍点。

---

## 四、鞍点存在性定理（核心结果）

### 4.1 函数假设

设 $V$, $Z$ 是**自反 Banach 空间** (reflexive Banach spaces)，满足：

**(1.13)** $\mathcal{A} \subseteq V$ 非空、闭、凸  
**(1.14)** $\mathcal{B} \subseteq Z$ 非空、闭、凸  
**(1.15)** $\forall p \in \mathcal{B}$，$u \mapsto L(u, p)$ 是**凸**的、**下半连续** (l.s.c.)  
**(1.16)** $\forall u \in \mathcal{A}$，$p \mapsto L(u, p)$ 是**凹**的、**上半连续** (u.s.c.)

### 4.2 主要存在性定理

**Proposition 2.1 (有界情形)**：

若 (1.13)-(1.16) 成立，且：
$$(2.1) \quad \mathcal{A} \text{ 和 } \mathcal{B} \text{ 都有界}$$

则 $L$ 在 $\mathcal{A} \times \mathcal{B}$ 上**存在鞍点** $(u, p)$，且：
$$\max_p \min_u L(u,p) = \min_u \max_p L(u,p) = L(u, p)$$

---

**Proposition 2.2 (强制性条件)**：

若 (1.13)-(1.16) 成立，且：
$$(2.10) \quad \exists p_0 \in \mathcal{B}: \lim_{\|u\| \to \infty, u \in \mathcal{A}} L(u, p_0) = +\infty$$
$$(2.11) \quad \exists u_0 \in \mathcal{A}: \lim_{\|p\| \to \infty, p \in \mathcal{B}} L(u_0, p) = -\infty$$

则 $L$ 存在鞍点。

> 📝 **(2.10)** 说的是：固定某个 $p_0$，$L(u, p_0)$ 关于 $u$ 是**强制的** (coercive)  
> 📝 **(2.11)** 说的是：固定某个 $u_0$，$-L(u_0, p)$ 关于 $p$ 是**强制的**

---

## 五、证明核心步骤详解

### Step 1: 有界情形 + 严格凸

假设额外有：
$$(2.3) \quad \forall p \in \mathcal{B}, \; u \mapsto L(u,p) \text{ 严格凸}$$

由于 $V$ 自反，$\mathcal{A}$ 有界闭凸 → $\mathcal{A}$ **弱紧** (weakly compact)。

对每个 $p \in \mathcal{B}$，由凸性 + l.s.c. + 弱紧性：
$$f(p) := \min_{u \in \mathcal{A}} L(u, p) \text{ 存在，且在唯一点 } e(p) \text{ 达到}$$

### Step 2: 构造最优化序列

函数 $p \mapsto f(p) = \min_u L(u, p)$ 是：
- **凹函数**（作为凹函数族的下确界）
- **弱上半连续**

因此存在 $\bar{p}$ 使得：
$$\max_{p \in \mathcal{B}} f(p) = f(\bar{p}) = \max_p \min_u L(u, p)$$

### Step 3: 关键极限论证

对 $\lambda \in (0, 1)$，定义 $e_\lambda = e((1-\lambda)\bar{p} + \lambda p)$。

由凹性：
$$L(e_\lambda, (1-\lambda)\bar{p} + \lambda p) \geq (1-\lambda)L(e_\lambda, \bar{p}) + \lambda L(e_\lambda, p)$$

整理得：
$$\frac{L(e_\lambda, (1-\lambda)\bar{p} + \lambda p) - L(e_\lambda, \bar{p})}{\lambda} \geq L(e_\lambda, p) - L(e_\lambda, \bar{p})$$

### Step 4: 取极限 $\lambda \to 0$

由弱紧性，存在子列 $e_{\lambda_n} \rightharpoonup u$（弱收敛）。

关键观察：这个极限 $u = e(\bar{p})$，与 $p$ 的选择无关！

证明：由 $e_\lambda$ 的定义和 l.s.c.：
$$L(u, \bar{p}) \leq \liminf L(e_{\lambda_n}, \bar{p}) \leq L(e(\bar{p}), \bar{p}) = f(\bar{p})$$

因此 $u = e(\bar{p})$。

### Step 5: 得出鞍点

令 $\lambda \to 0$，由 u.s.c.：
$$L(u, p) - L(u, \bar{p}) \leq 0, \quad \forall p \in \mathcal{B}$$

即 $\bar{p}$ 是 $\max_p L(u, p)$ 的解。结合 $u = e(\bar{p})$ 是 $\min_u L(u, \bar{p})$ 的解，由 Proposition 1.3：

$$\boxed{(u, \bar{p}) \text{ 是 } L \text{ 的鞍点}}$$

### Step 6: 去掉严格凸假设

若没有 (2.3)，引入扰动：
$$L_\varepsilon(u, p) = L(u, p) + \varepsilon \|u\|^2$$

$L_\varepsilon$ 满足 (2.3)，有鞍点 $(u_\varepsilon, p_\varepsilon)$。

由弱紧性取 $\varepsilon_n \to 0$ 的子列，$(u_{\varepsilon_n}, p_{\varepsilon_n}) \rightharpoonup (u, p)$。

由 l.s.c. 和 u.s.c. 的保持性，$(u, p)$ 是 $L$ 的鞍点。

---

## 六、应用到对偶问题

### 6.1 原问题与对偶问题

**原问题 $\mathcal{P}$**：
$$\inf_{u \in \mathcal{A}} \sup_{p \in \mathcal{B}} L(u, p)$$

**对偶问题 $\mathcal{P}^*$**：
$$\sup_{p \in \mathcal{B}} \inf_{u \in \mathcal{A}} L(u, p)$$

### 6.2 对偶定理

由鞍点存在性：
$$\inf \mathcal{P} = \sup \mathcal{P}^* = L(u, p)$$

**没有对偶间隙** (duality gap)！

---

## 七、与其他方法的比较

| 方面 | Ekeland-Témam (凸分析) | Brouwer/KKM (拓扑) | Komiya (初等) |
|------|------------------------|-------------------|---------------|
| **核心工具** | 弱紧性、l.s.c./u.s.c. | 不动点定理 | 连通性 |
| **空间要求** | 自反 Banach 空间 | 有限维/紧凸集 | 紧凸集 |
| **可推广性** | 无限维优化 | Nash 均衡 | 有限维 |
| **计算性** | 可导出数值算法 | 非构造性 | 非构造性 |

---

## 八、关键文献

1. **Ekeland, I. & Témam, R.** (1999). *Convex Analysis and Variational Problems*. SIAM Classics in Applied Mathematics, Chapter VI.

2. **Ky Fan** (1964). "Sur un théorème minimax". *C.R. Acad. Sci. Paris*, 259:3925-3928.

3. **Sion, M.** (1958). "On general minimax theorems". *Pacific J. Math.*, 8(1):171-176.

---

## 九、总结：证明的逻辑结构

```
                    凸分析工具
                        ↓
    ┌─────────────────────────────────────┐
    │  假设：                              │
    │  • V, Z 自反 Banach 空间            │
    │  • A, B 非空闭凸                     │
    │  • L(·,p) 凸, l.s.c.                │
    │  • L(u,·) 凹, u.s.c.                │
    │  • 有界性或强制性条件                │
    └─────────────────────────────────────┘
                        ↓
              弱紧性 + 半连续性
                        ↓
         ┌──────────────────────────┐
         │  f(p) = min_u L(u,p) 存在 │
         │  f(p) 凹且弱 u.s.c.       │
         └──────────────────────────┘
                        ↓
              max_p f(p) 存在于 p̄
                        ↓
              极限论证：u = e(p̄)
                        ↓
    ┌─────────────────────────────────────┐
    │  结论：(u, p̄) 是鞍点               │
    │  max min L = min max L = L(u, p̄)   │
    └─────────────────────────────────────┘
```

这就是 Ekeland-Témam 凸分析方法的完整证明框架！
