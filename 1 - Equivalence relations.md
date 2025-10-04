> [!notation] Some notations about sets
>
> $$
> \begin{align}
> \mathbb{N}&=\{0,1,2,\dots\} & \text{natural numbers} \\
> \mathbb{Z}&=\{\dots,-2,-1,0,1,2,\dots\} & \text{integers} \\
> \mathbb{Z}_{>0}&=\{1,2,3,\dots\} & \text{positive integers} \\
> \mathbb{Z}_{\geq a}&=\{a,a+1,a+2,\dots\} & \text{integers greater than or equal to } a \\
> \mathbb{Q}&=\left\{ \frac{p}{q} \mid p \in \mathbb{Z}, q \in \mathbb{Z} \setminus \{0\} \right\} & \text{rational numbers}
> \end{align}
> $$

## 1.2 Congruences modulo an integer

> [!definition] Definition 1.2.1: Congruence modulo an integer (p16)
>
> Let $n \in \Z$ be an integer. Given $a,b \in \Z$, we say that $a$ and $b$ are **congruent modulo $n$** if $a-b$ is a multiple of $n$.
>
> $$
> \begin{align} a \text{ and } b \text{ are congruent modulo } n &\iff \exists k \in \Z : a-b = k \cdot n \\ &\iff a \equiv b \pmod n \end{align}
> $$

> [!definition] Definition 1.2.2: Congruence class modulo an integer (p17)
> For $a,n \in \Z$ we define the **congruence class of $a$ modulo $n$** as
>
> $$
> a + n\Z := \{ a + k \cdot n \mid k \in \Z \}
> $$

Any element from a congruence class is called a **representative** of that class. Note that it always holds that $a \in a + n\Z$

> [!lemma] Lemma 1.2.3 (p17)
> Let $a,b,n \in \Z$. Then
>
> $$
> b \in a + n\Z \iff a \equiv b \pmod n
> $$

## 1.3 Equivalence relations

A relation $\sim$ on a set $A$ is a subset of $A \times A$. We can describe a relation $\sim$ on $A$ completely by using the set

$$
R := \{ (a,b) \in A \times A \mid a \sim b \}
$$

> [!definition] Definition 1.3.1: Equivalence relation (p19)
>
> Let $A$ be a set. An **equivalence relation** $\sim$ on $A$ is a relation on $A$ that satisfies the following properties:
>
> $$
> \begin{align}
>
> 1. & \textbf{Reflexivity} & \quad \forall a \in A: & \quad a \sim a \\
> 2. & \textbf{Symmetry} & \quad \forall a,b \in A: & \quad a \sim b \Rightarrow b \sim a \\
> 3. & \textbf{Transitivity} & \quad \forall a,b,c \in A: & \quad a \sim b \land b \sim c \Rightarrow a \sim c
>    \end{align}
> $$

Given an equivalence relation $\sim$ on a set $A$ and an element $a \in A$, we define the **equivalence class** of $a$ as

$$
\begin{align}
[a]_\sim & := \{ b \in A \mid a \sim b \} \\
        & \, = \{ b \in A \mid b \sim a \} && \text{because by 1.3.1 (2) } a \sim b \iff b \sim a
\end{align}
$$

An element $r \in [a]_\sim$ is called a **representative** of the equivalence class $[a]_\sim$.

> [!deduction] 1-1 Correspondence: Equivalence class and congruence class
> The equivalence class of an integer $a \in \Z$ under the congruent modulo $n$ relation, is precisely the congruence class $a + n\Z$:
>
> $$
> [a]_{\equiv \pmod{n}} = a + n\Z
> $$

Proof: Let $b \in [a]_{\equiv \pmod{n}}$. Then $a \equiv b \pmod{n}$, which means $b \in a + n\Z$. Conversely, if $b \in a + n\Z$, then $b = a + k \cdot n$ for some $k \in \Z$, which implies $a \equiv b \pmod{n}$. Thus, we have shown that $[a]_{\equiv \pmod{n}} = a + n\Z$.

> [!theorem] Theorem 1.3.3: Properties of equivalence classes (p20-21)
> Let $A$ be a set and $\sim$ an equivalence relation on $A$. Then we have:
>
> 1. $\forall a \in A$, $a \in [a]_\sim$.
> 2. The set $A$ is covered by the equivalence classes: $\bigcup_{a \in A} [a]_\sim = A$.
> 3. $\forall a,b \in A$, either
>     - $[a]_\sim = [b]_\sim$
>     - $[a]_\sim \cap [b]_\sim = \emptyset$
> 4. $\forall a,b \in A : a \sim b \iff [a]_\sim = [b]_\sim$.

We see that the **equivalence classes form a partition of $A$**:

> A family of sets $A_i$, $i \in I$ is called a **partition** of $A$, if $A = \bigcup_{i \in I} A_i$, none of the sets $A_i$ is empty, and for any distinct $i,j \in I$ the sets $A_i$ and $A_j$ are disjoint.
> In other words: a family of sets $A_i$, $i \in I$ is a partition of $A$, if for each $a \in A$, there exists exactly one set $A_i$ in the family containing $a$.

![[images/1/partition.jpg]]

One also says that the set $A$ is **partitioned into equivalence classes**. The word _partitioned_ (= divided into parts) is appropriate, since the set $A$ is divided into mutually disjoint subsets, namely the various equivalence classes.

> [!corollary] Corollary 1.3.4: Properties of congruence modulo an integer (p21)
>
> 1. $\forall a \in \Z$, $a \in a + n\Z$.
> 2. The set $\Z$ is covered by the congruence classes modulo $n$: $\bigcup_{a \in \Z} (a + n\Z) = \Z$.
> 3. $\forall a,b \in \Z$, either
>     - $a + n\Z = b + n\Z$
>     - $(a + n\Z) \cap (b + n\Z) = \emptyset$
> 4. $\forall a,b \in \Z : a + n\Z = b + n\Z \iff a \equiv b \pmod{n}$.

> [!fact] Fact 1.3.5: Division with remainder (p22)
> Let $a,n \in \Z$ with $n > 0$. Then there exist **unique** integers $q,r \in \Z$ such that
>
> 1. $a = q \cdot n + r$
> 2. $0 \leq r < n$
>
> Denote:
>
> -   $q = a \quot n$, the **quotient** of $a$ divided by $n$
> -   $r = a \opmod n$, the **remainder** of $a$ divided by $n$

> [!lemma] Lemma 1.3.6 (p22)
> Let $a,n \in \Z$ with $n > 0$. Then
>
> $$
> a \equiv (a \opmod n) \pmod n
> $$

Proof: you just need to show that $a - (a \opmod n)$ is a multiple of $n$ (because that's the definition of congruence modulo $n$). This is guaranteed by the division with remainder theorem, since $a = (a \quot n) \cdot n + (a \opmod n)$, so $a - (a \opmod n) = (a \quot n) \cdot n$.

> [!deduction] Direct consequence of Lemma 1.3.6 and Definition 1.3.1 (2)
> Because $a \equiv (a \opmod n) \pmod n$ and by symmetry of equivalence relations, we also have:
>
> $$
> (a \opmod n) \equiv a \pmod n
> $$

> [!theorem] Theorem 1.3.7: _Standard Representative_ $(a \opmod n)$ (p23)
> Let $n \in \Zp, a \in \Z$.
>
> The **only** representative of the congruence class $a + n\Z$ in $\Zn = \{ 0, 1, \ldots, n-1 \}$ is $a \opmod n$.
>
> We call $a \opmod n$ the **standard representative** of the congruence class $a + n\Z$, and
> $$ a + n\Z = (a \opmod n) + n\Z $$

There are only $n$ different congruence classes modulo $n$, namely
$$0 + n\Z, 1 + n\Z, 2 + n\Z, \ldots, (n-1) + n\Z$$

> [!corollary] Corrollary 1.3.8
> Let $a,b,n \in \Z$ with $n \geq 0$. Then
>
> $$
> (a + b) \opmod n \eqDef a +_n b = ((a \opmod n) + (b \opmod n)) \opmod n
> $$
>
> and
>
> $$
> (a \cdot b) \opmod n \eqDef a \cdot_n b = ((a \opmod n) \cdot (b \opmod n)) \opmod n
> $$

## 1.4 Modular arithmetic

> [!definition] Definition 1.4.1: Modular addition and multiplication (p25)
> Let $n \in \Zp$ and choose $a,b\in\Zn$ arbitrarily. We define the following modular operations:
>
> $$
> \begin{align}
> a +_n b & := (a + b) \opmod n & \textbf{addition modulo } n \\
> a \cdot_n b & := (a \cdot b) \opmod n & \textbf{multiplication modulo } n
> \end{align}
> $$

> [!theorem] Theorem 1.4.2: Properties of modular addition and multiplication (p25-26)
> Let $n \in \Zp$. Then for all $a,b,c \in \Zn$ we have:
>
> 1. $a \plusn b = b \plusn a$ (commutativity of addition)
> 2. $(a \plusn b) \plusn c = a \plusn (b \plusn c)$ (associativity of addition)
> 3. $a \timesn b = b \timesn a$ (commutativity of multiplication)
> 4. $(a \timesn b) \timesn c = a \timesn (b \timesn c)$ (associativity of multiplication)
> 5. $a \timesn (b \plusn c) = (a \timesn b) \plusn (a \timesn c)$ (distributivity)

## 1.5 The extended Euclidean algorithm (EEA) for integers

### Euclid's algorithm for computing the greatest common divisor (gcd)

Use the following recursive definition to compute $\gcd(a,b)$ for given integers $a,b \in \Zp$, by computing the sequence $(a_0, b_0), (a_1, b_1), (a_2, b_2), \ldots$ of pairs of integers as follows:

![[bea.jpg]]

> [!theorem] Theorem 1.5.2: Correctness of Euclid's basic algorithm (p28)
> Let $N,M \in \N$. Let $a_n$ and $b_n$ be defined as in the above algorithm. Then $$\exists m \in \N : b_m = 0 \land a_m = \gcd(N,M)$$

### The extended Euclidean algorithm (EEA)

In some applications, it is not enough to compute $\gcd(N,M)$, but is it also important to
express $\gcd(N,M)$ in $N$ and $M$. More precisely, to find integers $r$ and $s$ such that...

> [!fact] Bézout's identity (p29)
> For any integers $N,M \in \Z$, there exist integers $r,s \in \Z$ such that
>
> $$
> r \cdot N + s \cdot M = \gcd(N,M)
> $$

The _extended_ Euclidean algorithm not only computes $\gcd(N,M)$, but also the integers $r$ and $s$ from Bézout's identity.

![[eea.jpg]]

This algorithm begins with the following 2 by 3 matrix:

$$
\begin{pmatrix}
N & 1 & 0 \\
M & 0 & 1
\end{pmatrix}
$$

This matrix is gradually modified using **row operations**, until it has
the form:

$$
\begin{pmatrix}
\gcd(N,M) & r & s \\
0 & * & *
\end{pmatrix}
$$

where **$r$ and $s$ are the integers we are looking for.**
