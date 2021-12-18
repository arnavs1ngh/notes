---
layout: default
title: Linear Algebra & Numerical Methods 
parent: Year 2
nav_order: 1
math: mathjax3
---
# Linear Algebra and Numerical Methods - Concise
{: .no_toc }
## MATH50003
{: .no_toc}
**Term 1 Content**

<a href="https://arnavs1ngh.github.io/notes/docs/Year2/main/#analysis-2---math50001" style="color:#FF0000;">** PDF** Linear Algebra 2 - Concise Notes - Term 1</a>

<button class="btn js-toggle-dark-mode">Light Mode</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = 'Dark Mode';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = 'Light Mode';
  }
});
</script>

<details closed markdown="block">
  <summary>
    Table of contents
  </summary>
<!--   {: .text-delta } -->
* TOC
{:toc}
</details>

---

**Colour Code** - <span style="color: green;">**Definition**</span> are
<span style="color: green;">**green**</span> in these notes,
<span style="color: red;">**Consequences**</span> are <span style="color: red;">**red**</span>
and <span style="color: RoyalBlue;">**Causes**</span> are <span style="color: blue-000;">**blue**</span>

*Content from MATH40003 assumed to be known.*

# <span style="color: white;">1</span> Prelim

**Definition** - <span style="color: green;">**Similair Matrices**</span>

$A,B \in M_{n}(F)$ similair $(A \sim B)$ if $\exists$ invertible $P \in M_{n}(F)$ s.t $P^{-1}AP = B$\
$\sim$ is an equivalence relation.

*Properties of Similair Matrices*

-   Same Determinant

-   Same Char. Poly.

-   Same eigenvalues

-   Same rank Same Trace

**Definition - **<span style="color: green;">**Companion Matrix**</span>

Let $p(x)$ a monic polynomial of degree $r$;
$p(x) = x^{r} + a_{r-1}x^{r-1} + \dots + a_{0}$.\
Companion matrix of $p(x)$;

<center>
$$C(p(x)) =
\begin{pmatrix}
0 & 0 & 0 & \dots & 0 & -a_{0}\\
1 & 0 & 0 & \dots & 0 & -a_{1}\\
0 & 1 & 0 & \dots & 0 & -a_{2}\\
 & & & \dots & &\\
 0 & 0 & 0 & \dots & 1 & -a_{r-1}
\end{pmatrix}$$
  </center>

***Geometry***\
**Definition** - <span style="color: green;">**Dot Product**</span>
$u = (u_{1},\dots,u_{n})$ and $v = (v_{1},\dots,v{n})$\
<center>
$$u\cdot v = \sum_{i=1}^{n}u_{i}v_{i}$$
  </center>
Length of $u, ||u|| = \sqrt{u\cdot u}$\

Distance between $u$ and $v = \lvert\lvert u-v\rvert\rvert$

-   $P$ orthogonal if $P^{T}P = I, (Pu\cdot Pv) = u\cdot v)$

-   $A$ symmetric if $A^{T} = A, (Au\cdot v  = u\cdot Av)$

*Properties of dot product*

-   linear in $u,v$

-   symmetric; $u\cdot v = v\cdot u$

-   $u \cdot v > 0, \forall u,v$

# <span style="color: white;">3</span> Algebraic and Geometric multiplicities of eigenvalues

**Definition** - <span style="color: green;">**Multiplicity of eigenvalues**</span>

For $T:V \to V$ a linear map with char. poly. $p(x)$ with roots
$\lambda$, Then $\exists$ **$a(\lambda)$** $\in \mathbb{N}$ the **algebraic multiplicity** of $\lambda$ s.t
<center>
$$ p(x) = (x-\lambda)^{a(\lambda)}q(x) $$
</center>

where $\lambda$ not a root of $q(x)$\
<span style="color: green;">**Geometric multiplicity $g(\lambda) = dimE_{\lambda}$**</span>, for $E_{\lambda}$ the eigenspace of $T$

**Theorem 3.2**\
$dim V = n$, Let $T: V\to V$ a linear map with finite distinct eigenvalues $\{\lambda_{i}\}_{i=1}^{r}$\
Characteristic polynomial of $T$ is
<center>
$$p(x) = \prod_{i=1}^{r}(x-\lambda_{i})^{a(\lambda_{i}}$$
</center>
so $(\sum_{i=1}^{r}a(\lambda_{i}) = n$. Following are equivalent

-   $T$ diagonalisable

-   $(\sum_{i=1}^{r}g(\lambda_{i}) = n$

-   $g(\lambda_{i}) = a(\lambda_{i}) \forall i$ (This can be used to
    test for diagonalisability.)

# <span style="color: white;">4</span> Direct Sums

**Define**
For $ \{U_{i}\}_{i=1,\dots,k} $ subspaces of vector space $V$. Sum of these subspaces is:

<center>
$$U_{1} + \dots + U_{k} = \{u_{1}+\dots+u_{k}:u_{i} \in U_{i}, \forall i\}$$
</center>

**Definition - <span style="color: green;">Direct Sums**</span>
$V$ a vector space, $\{V_{i}\}_{i=1,\dots,k}$ subspaces of vector space $V$. [**$V$ a direct sum of $\{V_{i}\}$**] if: 
<center>
$$V = V_{1} \oplus \dots \oplus V_{k}$$
</center>
If $\forall v \in V$ can be expressed as $v = v_{1} + \dots + v_{k}$ for unique vectors $v_{i} \in V_{i}$\

*Corollary*
<center>
$V = V_{1} \oplus \dots \oplus V_{k} \iff  dimV = \sum_{i=1}^{k}dimV_{i}$ and if $B_{i}$ a basis for $V_{i}$}, $B = \bigcup_{i}B_{i}$ is a basis for V$

**Definition - <span style="color: green;">Invariant subspaces**</span>
$T: V\to V$ a linear map, $W$ a subspace of $V$.\

<center>
$W$ is $T$-invariant if $T(W) \subseteq W, T(W) = \{T(w) : w \in W\}$
</center>

Write $T_{W}: W \to W$ for the restriction of $T$ to $W$\
**Notation - Direct sums of matrices**\
  <center>
$$A_{1} \oplus \dots \oplus A_{k} = \begin{pmatrix}
A_{1} & &\\
 & \ddots & \\
 & & A_{k}
\end{pmatrix}$$
  </center>

# <span style="color: white;">5</span> Quotient Spaces

**Definition - <span style="color: green;">Cosets**</span>

$V$ a vector space over $F$, with $W \leq V$ a subspace.\

<center>
Cosets $W + v$ for $v\in V$ $W + v:= \{w+v:w \in W\}$
</center>

<span style="color: green;">**Quotient Space**</span>

Define $V/W$ as a vector space of vectors $W + v$ over $F$

-   Addition; $(W +v_{1}) + (W+ v_{2}) = W+v_{1}+v_{2}$

-   Scalar Multiplication; $\lambda(W+v) = W + \lambda v$

Can verify this using vector space axioms.\
*Dimension of $V/W$*\
$$dimV/W = dimV - dim W$$

**Definition -** [**Quotient Map**]\
$T: V \to V$ a linear map, $W$ a $T$-invariant subspace of V. Quotient
map: $\bar{T}: V/W: \to V/W$ such that
$$\bar{T}(W+v) = W + T(v), \qquad \forall v \in V$$

# <span style="color: white;">6</span> Triangularisation

*Lemma - Diagonal Matrices*\
$$A = 
\begin{pmatrix}
\lambda_{1} &  & & & \\
0 & \lambda_{2} & & * & \\
& & \cdot & &\\
0 & & & \cdot &\\
0 & 0 & & & \lambda_{n}
\end{pmatrix},
B = 
\begin{pmatrix}
\mu_{1} &  & & & \\
0 & \mu_{2} & & * & \\
& & \cdot & &\\
0 & & & \cdot &\\
0 & 0 & & & \mu_{n}
\end{pmatrix}$$

-   Characteristic polynomial of $A$ = $\prod_{i=1}^{n}(x-\lambda_{i})$,
    eigenvalues $=\{\lambda_{i}\}$

-   $detA = \prod_{i=1}^{n}\lambda_{i}$

-   $AB$ also upper triangular, with
    $diag(AB) = \lambda_{1}\mu_{1},\dots,\lambda_{n}\mu_{n}$

**Theorem 6.2 - Triangularisation Theorem**\
$V$ an $n$ dimensional vector space over $F$, $T:V \to V$ a linear map,\
Where $\chi(T) = \prod_{i=1}^{n}(x-\lambda_{i})$, where
$\lambda_{i} \in F \ \forall i$ $\implies \exists$ basis $B$ of $V$ s.t
$[T]_{B}$ upper triangular

# <span style="color: white;">7</span> The Cayley-Hamilton Theorem

**Theorem. 7.1 - *(Cayley-Hamilton Theorem)***\
$V$ a finite dimensional vector space over $F$. $T: V \to V$ a linear
map with char. poly. $p(x)$ $$p(T) = 0$$

# <span style="color: white;">8</span> Polynomials

**Definition -** [**Polynomials over a
field**]\
$F$ a field,$p(x)$ over $F$, for
$p(x) = \sum_{i}a_{i}x^{i}, F[x] = \{ p(x) : a_{i} \in F\}$\
[**Degree of polynomial**]\
$deg(p(x)) =$ the highest power of $x$ in $p(x)$\
[**Euclidean Algorithm**]\
$f,g \in F[x]$ with $deg(g) \geq 1$, Then $\exists q,r \in F[x] s.t$
$$f = gq +r$$ for either $r = 0$ or $deg(r) < deg(g)$

**Definition -** [**Greatest Common Divisor (GCD) of
polynomials**]\
$f,g \in F[x] \backslash \{0\}$, [**Say $d\in F[x]$ the gcd of $f,g$
if:**]

1.  [**$d|f$ and $d|g$**]

2.  [**if $e(x) \in F[x]$ and $e|f$ and $e|g$ Then
    $e|d$**]

Say $f,g$ are co-prime if $gcd(f,g) = 1$\
***Corollary***\
$d = gcd(f,g) \implies \exists r,s \in F[x] \text{ s.t } d = rf + sg$\
**Definiton -** [**Irreducible
polynomials**]\
$p(x) \in F[x]$ irreducible over $F$ if $deg(p) \geq 1$ and $p$ not
factorisable over $F$ as a product of $\{f_{i}\} \in F$ s.t
$deg(f_{i} \leq deg(p)$\
***Corollary***\
$p(x) \in F[x]$ irreducible, $\{g_{i}\} \in F[x]$, if
$p|g_{1}\dots g_{r} \implies p|g_{i} \text{ for some } i$\
**Theorem 8.7 - *(Unique Factorization Theorem)***\
$f(x) \in F[x]$ s.t $deg(f) \geq 1$ $$f = p_{1}\dots p_{r}$$ where each
$p_{i} \in F[x]$ irreducible. **Factorisation of $f$ is unique up to
scalar multiplication**\

# <span style="color: white;">9</span> The minimal polynomial of a linear map

**Definition -**[**Minimal polynomial**]\
Say $m(x) \in F[x]$ a minimal polynomial for $T: V \to V$ if

1.  $m(T) = 0$

2.  $m(x)$ monic

3.  $deg(m)$ is as small as possible s.t (i) and (ii)

***Properties of the minimal polynomial***

-   For $T$ a linear map, its minimal polynomial $m_{T}(x)$ is unique

-   $p(x) \in F[x], p(T) = 0 \iff m_{T}(x)|p(x)$

-   $m_{T}(x)|c_{T}(x)$ the char. poly. of $T$

-   $\lambda \in F$ a root of $c_{T}(x) \implies \lambda$ a root of
    $m_{T}(x)$

-   $A,B \in M_{n}(F)$ s.t $A \sim B \implies m_{A}(x) = m_{B}(x)$

**Theorem 9.3**\
$p(x) \in F[x]$ an irreducible factor of
$c_{T}(x) \implies p(x)|m_{T}(x)$ *Corollaries*\

-   $c_{T}(x) = c_{T_{W}}(x)c_{\bar{T}}(x)$

-   $m_{T_{W}}(x)$ and $m_{\bar{T}}(x)$ both divide $m_{T}(x)$

# <span style="color: white;">10</span> Primary Decomposition

**Theorem 10.1 - *(Primary Decomposition Theorem)***\
$V$ a finite dimensional vector space over $F$, $T:V\to V$ a linear map
with $m_{T}(x)$\
Let factorisation of $m_{T}(x)$ into irreducible polynomials be:
$$m_{T}(x) = \prod_{i=1}^{k}f_{i}(x)^{n_{i}}$$ Where $\{f_{i}(x)\}$ all
distinct irreducible polynomials in $F[x]$\
For $1 \leq i \leq k$, define: $$V_{i} = ker(f_{i}(T)^{n_{i}})$$ Then

1.  $V = V_{1} \oplus \dots \oplus V_{k}$ *(Call this the [**primary
    decomposition**] of $V$ w.r.t $T$)*

2.  each $V_{i}$ is $T$-invariant

3.  each restriction $T_{V_{i}}$ has minimal polynomial
    $f_{i}(x)^{n_{i}}$

In the case where each $f_{i}(x) = (x-\lambda_{i})$
$$\implies m_{T}(x) = \prod_{i=1}^{k}(x-\lambda_{i})^{n_{i}}$$ With
$\lambda_{i}$ distinct eigenvalues of $T$ and
$V_{i} = ker(T-\lambda_{i}I)^{n_{i}}$\
We call $V_{i}$ the [**generalised $\lambda_{i}$-eigenspace of
T**]\
***Corollary***\
A linear map $T:V \to V$ diagonalisable
$\iff m_{T}(x) = \prod_{i=1}^{k}(x-\lambda_{i})$ a product of distinct
linear factors\
***Corollary***\
For $T:V \to V$ a linear map, with $g_{1}(x),g_{2}(x) \in F[x]$ coprime
polynomials s.t $g_{1}(T)g_{2}(T) = 0$

1.  Then $V = V_{1} \oplus V_{2}$, where $V_{i} = ker g_{i}(T), i = 1,2$
    with each $V_{i}$ being $T$-invariant

2.  Suppose
    $m_{T}(x) = g_{1}(x)g_{2}(x) \implies m_{T_{V_{i}}}(x) = g_{i}(x), i = 1,2$

# <span style="color: white;">11</span> Jordan Canonical Form

**Definition -** [**Jordan Block**]\
$F$ a field and let $\lambda \in F$. Define $n\times n$ matrix:
$$J_{n}(\lambda) =
 \begin{pmatrix}
\lambda & 1 & 0 & \dots & 0 & 0 \\
0 & \lambda & 1 & \dots & 0 & 0 \\
0 & 0 & \lambda & \dots & 0 & 0 \\
 &  &  & \dots &  &  \\
0 & 0 & 0 & \dots & \lambda & 1 \\
0 & 0 & 0 & \dots & 0 & \lambda 
\end{pmatrix}$$ ***Properties of the Jordan Blocks***

1.  characteristic and minimal polynomials of $J$, $= (x-\lambda)^{n})$

2.  $\lambda$ the only eigenvalue of $J$, with
    $a(\lambda) = n, g(\lambda) = 1$

3.  $J-\lambda I = J_{n}(0)$, multiplication by $J-\lambda I$ sends
    basis vectors as such:
    $$e_{n} \to e_{n-1} \to \dots \to e_{2} \to e_{1} \to 0$$

4.  $(J-\lambda I)^{n} = 0$, and for $i < n$,
    $rank((J-\lambda I)^{i}) = n-i$. And under multiplication:
    $$e_{n} \to e_{n-i}, e_{n-1} \to e_{n-i-1} \dots$$

***Lemma***\
Let $A = A_{1} \oplus \dots \oplus A_{k}$ for each $i$ let $A_{i}$ have
char. poly $c_{i}(x)$ and min. poly. $m_{i}(x)$.\

-   $c_{A}(x) = \prod_{i=1}^{k}c_{i}(x)$

-   $m_{A}(x) = lcm(m_{1}(x),\dots,m_{k}(x))$

-   $\forall \lambda$ eigenvalues of A,
    $dim E_{\lambda}(A) = \sum_{i=1}^{k}dimE_{\lambda}(A_{i})$

-   $\forall q(x) \in F[x]$,
    $q(A) = q(A_{1}) \oplus \dots \oplus q(A_{k})$

**Theorem 11.3 - *(Jordan Canonical Form)***\
$A \in M_{n}(F)$, suppose $c_{A}(x)$ a product of linear factors over
$F$.\
Then

1.  $A$ similair to matrix of form
    $$J = J_{n_{1}}(\lambda_{1}) \oplus \dots \oplus J_{n_{k}}(\lambda_{k})$$

    ::: center
    [**This is the Jordan Canonical Form (JCF) of
    $A$**]
    :::

2.  Matrix $J$ from above, is uniquely determined by $A$ up to order of
    Jordan blocks

***Computing the JCF***

JCF theorem says $A \sim J$, a JCF matrix.\
$A \sim J \implies$ same characteristic polynomial, eigenvalues,
geometric multiplicities, minimal polynomial and $q(A) \sim q(J)$ for
any polynomial $q$.\
For each eigenvalue $\lambda$, collect all Jordan blocks as such;
$$J = \underbrace{(J_{n_{1}}(\lambda) \oplus \dots \oplus J_{n_{a}}(\lambda))}_{\lambda-\text{blocks of J}}\oplus\underbrace{(J_{m_{1}}(\mu) \oplus \dots \oplus J_{m_{b}}(\mu))}_{\mu-\text{blocks of J}}\oplus \dots$$

***Properties of JCF***\
$J$ as above, $\lambda$ an eigenvalue;

1.  $n_{1} + \dots + n_{a} = a(\lambda)$

2.  $a$ = number of $\lambda$-blocks = $g(\lambda)$

3.  max$(n_{1},\dots,n_{a}) = r$, where $(x-\lambda)^{r}$ the highest
    power of $(x-\lambda)$ dividing $m_{A}(x)$

::: thm
**Theorem 1**.
:::

$T: V \to V$ a linear map s.t $c_{T}(x)$ a product of linear factors
$\implies \exists$ basis $B$ of $V$ s.t $[T]_{B}$ a JCF matrix

**Definition.- [**Nilpotent Matrix**]**\
$A^{k} = 0$ for some $k \in \mathbb{N}$

::: thm
**Theorem 2**.
:::

$S:V \to V$ a nilpotent linear map $\implies \exists$ basis $B$ of $V$
s.t $$[S]_{B} = J_{n_1}(0) \oplus \dots \oplus J_{n_k}(0)$$

***Computing a Jordan Basis***\
Finding the Jordan Basis $B$ as above.\
We have $V = V_{1} \oplus \dots \oplus V_{k}$ by Primary Decomposition
Theorem.\
Take each restriction $T_{V_i}$ each with $1$ eigenvalue.\
Let $S_{i} = T_{V_i} - \lambda_{i}I$ so each $S_{i}$ nilpotent.

-   Compute subspaces\
    $$V \supset S(V) \supset S^{2}(V) \supset \dots \supset S^{r}(V) \supset 0$$
    $S^{r+1}(V) = 0$

-   Find basis of $S^{r}(V)$, Using the following rules extend to basis
    of $S^{r-1}(V)$:

    1.  $u_{1},S(u_{1}),\dots,S^{m_{1}-1}(u_{1}),\dots u_{r},S(u_{r}),\dots,S^{m_{r}-1}(u_{r})$

    2.  for each $i$ add vector $v_i \in V$ s.t $u_i = S({v_i})$

    3.  note $ker(S)$ contains linearly independent vectors
        $$S^{m_{1}-1}(u_{1}),\dots,S^{m_{r}-1}(u_{r})$$ extend to basis
        of $ker(S)$ by adding vectors $w_{1},\dots,w_{s}$ with dim
        $ker(S) = r+s$\
        Yielding
        $$v_{1},S(v_{1}),\dots,S^{m_{1}}(v_{1}),\dots,v_{r},S(v_{r}),\dots,S^{m_{r}}(v_{r}),w_{1},\dots,w_{s}$$

-   Repeat successively finding Jordan bases of $S^{r-2},\dots,S(V),V$

# <span style="color: white;">12</span> Cyclic Decomposition & Rational Canonical Form

**Definition - [**Cyclic Subspaces**]**\
$V$ a finite dimensional vector space over $F$, and $T:V \to V$ a linear
map.\
Let $0 \neq v \in V$ and define $$\begin{aligned}
    Z(v,T) &= \{f(T)(v)\ : \ f(x) \in F[x]\}\\
     &= \text{Sp}(v,T(v),T^{2}(v),\dots)\end{aligned}$$ Say $Z(v,T)$ the
$T$-cyclic subspace of $V$ generated by $v$.\
$Z(v,T)$ is $T-$invariant. Write $T_{v}$

**Definition - [**$T$-annihilator of $v$ and
$Z(v,T)$**]**\
Considering, $v,T(v),T^{2}(V),\dots$ with $T^{k}(v)$ first vector in
span of previous ones
$$\implies T^{k}(v) = -a_{0}v - a_{1}T(v) - \dots - a_{k-1}T(v)$$
$T-$annihilator of $v$ and $Z(v,T)$ is
$$m_{v}(x) = x^{k} + a_{k-1}x^{k} + \dots + a_{0} \in F[x]$$ This is
monic polynomial of smallest degree s.t $m_{v}(T)(v) = 0$ also with
$m_{v}(T)(w) = 0\ \forall w \in Z(v,T)$

::: thm
**Theorem 3**. **(Cyclic Decomposition Theorem)**
:::

$V$ a finite dimensional vector space over $F$\
$T:V \to V$ a linear map. Suppose $m_{T}(x) = f(x)^{k}$ for irreducible
$f(x) \in F[x]$\
$\implies \exists v_{1},\dots,v_{r} \in V$ s.t
$$V + Z(v_1,T) \oplus \dots \oplus Z(v_r,T)$$ where

1.  each $Z(v_{i},T)$ has $T$-annihilator $f(x)^{k_i}$ for
    $1\leq i \leq r,\ k = k_{1} \geq k_{2} \geq \dots \geq k_{r}$

2.  $r$ and $k_{1},\dots,k_{r}$ uniquely determined by $T$

***Corollary 12.3***\
$T$ a finite dimensional vector space over $F$\
$\implies \exists$ basis $B$ of $V$ s.t
$$[T]_{B} = C(f(x)^{k_{1}}) \oplus \dots \oplus C(f(x)^{k_{r}})$$

***Corollary 12.3***\
$A \in M_{n}(F)$, with $m_A(x) = x^{k}$\
$$\implies A \sim C(x^{k_1} \oplus \dots \oplus C(x^{k_r})$$

::: thm
**Theorem 4**. **(Rational Canonical Form Theorem)**
:::

$V$ be finite dimensional over field $F$ with $T:V \to V$ a linear map
with $$m_{T}(x) = \prod_{i=1}^{t}f_{i}(x)^{k_i}$$ with
$\{f_{i}(x)\}_{i=1}^{t} \in F[x]$ set of distinct irreducible
polynomials $\implies \exists$ basis $B$ of $V$ s.t

$$\begin{aligned}
_{B} &= C(f_{1}(x)^{k_{11}}) \oplus \dots \oplus C(f_{1}(x)^{k_{1r_1}}) \oplus \dots\\
    & \oplus C(f_{t}(x)^{k_{t1}}) \oplus \dots \oplus C(f_{t}(x)^{k_{tr_{t}}})\end{aligned}$$
where for each $i$ $$k_{i} = k_{i1} \geq \dots \geq k_{ir_{i}}$$ with
$r_{i}$ and $k_{i1},\dots,k_{ir_{i}}$ uniquely determined by $T$\
***Corollary 12.6***\
$A \in M_{n}(F)$ s.t $m_{A}(x) = \prod_{i=1}^{t}f_{i}(x)^{k_{i}}$
distinct irreducible polynomials.\
$\implies A \sim  C(f_{1}(x)^{k_{11}}) \oplus \dots \oplus C(f_{1}(x)^{k_{1r_1}}) \oplus \dots \oplus C(f_{t}(x)^{k_{t1}}) \oplus \dots \oplus C(f_{t}(x)^{k_{tr_{t}}})$

***Computing the RCF*** $T:V \to V$ we have
$$c_{T}(x) = \prod_{i=1}^{t}f_{i}(x)^{n_i},\quad m_{T}(x) = \prod-{i=1}^{t}f_{i}(x)^{k_i}$$
$\{f_{i}(x)\}$ all distinct irreducible polynomials in $F[x]$\
enough to find;
$rank(f_{i}(T)^{r}) \forall i \in \{1,\dots,t \}, 1\leq r \leq k_{i}$

# <span style="color: white;">13</span> The Dual Space

**Definition - [**Linear functional**]**\
$V$ a vector space over $F$\
A [**linear functional**] on $V$ a linear
map $\phi: V \to F$ s.t
$$\phi(\alpha v_{1} + \beta v_{2}) = \alpha\phi(v_1) + \beta\phi(v_2) \qquad \forall v_i \in V, \forall \alpha,\beta \in F$$
*Operations of linear functionals*

1.  $(\phi_1 + \phi_2)(v) = \phi_1(v) + \phi_2(v), \qquad \forall v \in V$

2.  $(\lambda\phi)(v) = \lambda\phi(v),\qquad \forall \lambda \in F, \forall v \in V$

\
$$V^{*} = \{ \phi | \phi: V\ to F \text{ a linear functional }\}$$
$V^{*}$ a vector space over $F$ w.r.t above multiplication and addition.

***Dimension***\
$\{v_i\}_{i}$ a basis of $V$ with eigenvalues $\{\lambda\}_{i}$\
$\exists! \phi \in V^*$ sending $v_i \to \lambda_i$\
$$\phi(\sum \alpha_i v_i) = \sum \alpha_i \lambda_i$$

**Proposition 13.1**\
Let $n = dim V$ with $\{v_1,\dots,v_n\}$ a basis of $V$\
$\forall i$ define $\phi_i \in V^*$ by $$\phi_i(v_{j}) = \delta_{ij} = 
    \begin{cases} 
        1 & i = j \\
        0 & i \neq j\\
   \end{cases}$$
$\implies \phi_i(\sum \alpha_{j}v_{j}) = \alpha_{i} \implies \{\phi_1,\dots,\phi_n\}$
a basis of $V^*$ the [**dual basis**] of
$B$\
$dim V^* = n = dim V$

**Definition - [**Annihilators**]**\
$V$ a finite dimensional vector space over $F$ and $V^*$ the dual space.
$X \subset V.$ Say annihilator $X^0 of X:$
$$X^0 = \{ \phi \in V^* : \phi(x) = 0 \forall x\in X\}$$ $X^0$ a
subspace of $V^*$

**Proposition 13.2.**\
$W$ subspace of $V \implies dim W^0 = dim V - dim W$

# <span style="color: white;">15</span> Inner Product Spaces

**Definition - [**Inner Product**]**\
$F = \mathbb{R}$ or $\mathbb{C}$. $V$ a vector space over $F$\
Inner product on $V$ a map $(u,v): V \times V \to F$ satisfying

1.  $(\lamdba_1v_1 + \lamdba_2v_2, w) = \lamdba_1(v_1,w) + \lamdba(v_2,w)$

2.  $(w,v) = \bar{(w,v)}$

3.  $(v,v) > 0$ if $v \neq 0$

$\forall v_i,v,w \in V$ and $\lamdba_i \in F$. Call such a vector space
$V$ with inner product $(,)$ an [**inner product
space**].\
***Properties of Inner Product Space***

-   right-linear for $F = \mathbb{R}$;
    $(v, \lamdba_1w_1+\lamdba_2w_2) = \bar{\lamdba_1}(v,w_1) + \bar{\lamdba_2}(v,w_2)$

-   $(v,v) \in \mathbb{R}$

-   $(0,v) = 0 \forall v \in V$

-   symmetry; $F = \mathbb{R}\implies (w,v) = (v,w)$

-   $(v,w) = (v,x) \forall v \in V \implies w=x$

***Matrix of an inner product*** $V$ a finite dimensional inner product
space. $B = \{v_1,\dots,v_n\}$ a basis.\
Defining $a_{ij} = (v_i,v_j)$. So we have $a_{ji} = \bar{a_{ij}}$

1.  $\mathbb{R}\implies A$ symmetric

2.  $\mathbb{C}\implies A$ hermitian

$v,w \in V \implies (v,w) = [v]_{B}^{T}A[\bar{w}]_{B}$\
**Definition - [**Positive definite**]**\
Hermitian matrix $A$ positive-definite if
$x^TA\bar{x} > 0\ \forall \text{ non-zero } x \in F^{n}$\
**Proposition 14.1**\
For $u,v,w \in V$ we have

1.  $|(u,v)| \leq ||u||||v||$ *(Cauchy-Schwarz Inequality)*

2.  $||u+v|| \leq ||u|| + ||v||$

3.  $||u-v|| \leq ||u-w|| + ||w-v||$ *(Triangle inequalities)*

**Dual Space**\
Let $V$ an inner product space over
$F = \mathbb{R}\text{ or }\mathbb{C}$\
$v \in V$ define $$f_v: V \to F$$ $$f_v(w) = (w,v)$$ $\implies f_v$
linear functional $\in V*$\
**Definition - [**$\bar{V}$**]** [V
bar]{style="color: white"}\
$\bar{V}$ has same vectors as $V$

-   Addition in $\bar{V}$ same as $V$

-   Scalar multiplication; $\lambda * v = \bar{\lamdba}v$

**Proposition 14.2.**\
$V$ finite-dimensional. Define $\pi : \bar{V} \to V*$ as
$$\pi(v) = f_v \quad \forall v \in V$$ $\implies \pi$ a vector space
isomorphism\
**Definition - [**Orthogonality**]**\
$\{v_1,\dots,v_k\}$ orthogonal if $(v_i,v_j) = 0\ \forall i,j\ i\neq j$\
Orthonormal if also $||v_i|| = 1\ \forall i$\
**Definition - [**$W^\perp$**]** [W
perp]{style="color: white"}\
$W \subseteq V$ define
$$W^{\perp} = \{u \in V: (u,w) = 0\ \forall w \in W\}$$

**Proposition**\
$V$ a finite dimensional inner product space. $W \leq V$
$$\implies V = W \oplus W^\perp$$

**Theorem 14.5**\
$V$ a finite dimensional inner product space

1.  $V$ has orthonormal basis

2.  Any orthonormal set of vectors $\{w_1,\dots,w_r\}$ can be extended
    to orthonormal basis of $V$

**Gram-Schmidt Process**

1.  Start with basis $\{v_1,\dots,v_n\}$ of $V$

2.  let $u_1 = \frac{v_1}{||v_1||}$ define $w_2 = v_2 - (v_2,u_1)u_1$\
    $\implies (w_2,u1) = 0, \quad$ let $u_{2} = \frac{w_2}{||w_2||}$\
    $\implies \{u_1,u_2\}$ orthonormal

3.  Let $$w_3 = v_3 - (v_3,u_1)u_1 - (v_3,u_2)u_2$$ With
    $u_3 = \frac{w_3}{||w_3||} \implies \{u_1,u_2,u_3\}$

4.  Continue, for $i^{\text{th}}$ step
    $$u_i = \frac{w_i}{||w_i||}\quad w_i = v_i - (v_i,u_1)u_1 - \dots - (v_i,u_{i-1})u_{i-1}$$
    Yielding after $n$ steps an orthonormal basis
    $\{u_{1},\dots,u_{n} \}$ with
    $$\text{Sp}(u_1,\dots,u_i) = \text{Sp}(v_1,\dots,v_i) \quad \forall i \in \{1,\dots,n\}$$

**Projections**\
$V$ an inner product space. $v,w \in V\backslash 0$\
[**Projection of $v$ along $w$**] defined to
be $\lamdba w$ for $\lamdba \frac{(v,w)}{(w,w}$.\
For $W \leq V, v\in V$\
define projection of $V$ along $W$ as follows: $$V = W \oplus W^\perp$$
$$v = w + w'\quad \text{ for unique } w \in W, w' \in W^\perp$$ Define
[**orthogonal projection**] map along $W$.
$$\pi_W: V \to W$$ $$\pi_W(v) = w$$ **Proposition 14.7.**\
$V$ an inner product space. $W \leq V$ with $\pi_W$ orthogonal
projection map along $W$.

1.  $v\in V \implies \pi_W$ vector in $W$ closest to $V$\
    i.e for $w \in W$, $||w-v||$ minimum for $w = \pi_W(v)$

2.  dist$(v,w)$ denotes shortest distance from $v$ to any vector in $W$\
    $\implies \text{dist}(v,w) = ||v - \pi_W(v)$

3.  $\{v_1,\dots,v_r\}$ orthonormal basis of $W$\
    $\implies \pi_W(v) = \sum_{j=1}^{r}(v,v_j)v_j$\

**Change of orthonormal basis**\
**Proposition 14.8**\
$V$ an inner product space. $E = \{e_1,\dots,e_n\}$,
$F = \{f_1,\dots,f_n\}$ orthonormal basis of $V$\
$P = (p_{ij})$ change of basis matrix.
$$f_i = \sum_{j=1}^{n}p_{ji}e_{j} \implies P^{T}\bar{P} = I$$

**Definition**

-   $P \in M_{n}(\mathbb{R}) : P^TP = I \implies$ orthogonal matrix

-   $P \in M_{n}(\mathbb{C}) : P^T\bar{P} = I \implies$ unitary matrix

***Properties of the above matrices***

1.  length-preserving maps of $\mathbb{R}^{n},\mathbb{C}^{n}$
    (isometries)\
    i.e $||Pv|| = ||v|| \quad \forall v$

2.  Set of all isometries form a group - *classical group*\
    *orthogonal group*;
    $O(n,\mathbb{R}) = \{P \in M_{n}(\mathbb{R}) : P^{T}P = I\}$\
    *Unitary Group*;
    $U(n,\mathbb{C}) = \{P \in M_{n}(\mathbb{C}) : P^{T}\bar{P} = I$

# <span style="color: white;">15</span> Linear maps on inner product spaces

**Proposition 15.1.**\
$V$ a finite dimensional inner product space. $T: V\to V$ a linear map\
$\implies \exists!$ linear map $T^*:V \to V$ s.t $\forall u,v \in V$
$$(T(u),v) = (u,T^*(v))$$ Say $T^*$ - [**adjoint of
$T$**]\
$T$ [**self-adjoint**] if $T = T^*$\
**Proposition 15.2.**\
$V$ an inner product space with orthonormal basis
$E = \{v_1,\dots,v_n\}$\
$T:V \to V$ a linear map, $A = [T]_{E}$\
$\implies [T^*]_{E} = \bar{A}^T$ if field $\mathbb{R}\implies A$
symmetric, if field $\mathbb{C}\implies A$ hermitian\
**Theorem 15.3. [**Spectral Theorem**]**\
$V$ an inner product space. $T: V \to V$ a self-adjoint linear map
$\implies V$ has orthonormal basis of $T$-eigenvectors.\
**Corollary 15.4.**

-   $A \in M_n(\mathbb{R}) \implies \exists$ orthogonal $P$ s.t
    $P^{-1}AP$ diagonal

-   $A \in M_n(\mathbb{C}) \implies \exists$ unitary $P$ s.t $P^{-1}AP$
    diagonal

**Lemma 15.5.**\
$T: V\to V$ self-adjoint

1.  eigenvalues of $T$ real

2.  eigenvectors for distinct eigenvalues, orthogonal to each other

3.  If $W \subseteq V$, $T-$invariant $\implies W^\perp$ is also
    $T-$invariant

# <span style="color: white;">16</span> Bilinear & Quadratic Forms

**Definition. - [**Bi-linear form**]**\
$V$ a vector space over $F$\
[**Bi-linear form**] on $V$ a map;
$(,): V\times V \to  F$ which is both right and left-linear.\
i.e $\forall \alpha,\beta \in F$

-   $(\alpha v_1 + \beta v_2, w) = \alpha(v_1,w) + \beta(v_2,w)$

-   $(v,\alpha w_1 + \beta w_2) = \alpha(v,w_1) + \beta(v,w_2)$

***General example***\
$F$ a field, $V = F^n$ with $A \in M_n(F)$\
$\implies (u,v) = u^TAv \quad \forall u,v \in V$ a bilinear form on $V$\
***Matrices***\
$(,)$ a bilinear form on finited dimensional vector space $V$. With
$B = \{v_1,\dots,v_n\}$\
$A$ matrix of $(,)$ w.r.t $B$, So
$(a_{ij}) = (v_i,v_j) \implies \forall u,v \in V\ (u,v) = [u]_{B}^{T}A[v]_B$\
**Definition - [**Symmetric &
Skew-symmetric**]**\
Bilinear form $(,)$ on V is

-   [**Symmetric**] if
    $(u,v) = (v,u)\ \forall u,v \in V$

-   [**Skew symmetric**] if
    $(v,u) = -(u,v)\ \forall u,v \in V$

\
**Definition - [**Characteristic of Field
$F$**]**\
$char$ of field $F$ is the smallest $n \in \mathbb{N}_+$ s.t $n = 0$. if
no such $n$ exists say $char(F) = 0$\
**Lemma 16.1.**\
$V$ a vector space over $F$ with $char(F) \neq 2$\
$(,)$ skew-symmetric bilinear form on
$V \implies (v,v) = 0\ \forall v \in V$
$$(v,v) = -(v,v) \implies 2(v,v) = 0 \iff 2 = 0 \text{ or } (v,v) = 0$$

***Orthogonality***\
**Theorem 16.2**\
bilinear form $(,)$ has property that $$(v,w) = 0 \iff (w,v) = 0$$
$$\iff$$ $$(,) \text{ skew-symmetric or symmetric}$$

**Definition - [**Non-degenerate**]**\
$(,)$ on $V$ [**non-degenerate**] if
$V^\perp = \{0\}$. Where $V^\perp$ defined analogously w.r.t bilinear
forms. $$\forall u \in V,\ (u,v) = 0 \forall v \in V \implies u = 0$$
$V^\perp = \{0\} \iff$ matrix of $(,)$ w.r.t a basis is invertible.

***Dual Space***\
**Proposition 16.3.**\
Suppose $(,)$ non-degenerate bilinear form on a finite dimensional
vector space $V$.

1.  $v\in V$ define $f_v \in V^*$\
    $f_v(u) = (v,u)\quad \forall u \in V$\
    $\implies \phi: V \to V^*$ mapping $v \mapsto f_v \ (v \in V)$ an
    isomorphism

2.  $\forall W \leq V$ we have $dim(W^\perp) = dim(V)-dim(W)$

***Bases***

**Definition**\
$A,B \in M_n(F)$ [**congruent**] if
$\exists$ invertible $P \in M_n(F)$ s.t $$B = P^TAP$$ $A,B$ congruent
$\implies$ bilinear forms $(u,v)_{1} = u^TAv$ and $(u,v)_{2} = u^TBv$
are [**equivalent**]\
**Skew-symmetric bilinear forms**\
**Theorem 16.4.**\
$V$ a finite dimensional vector space over $F$ where $char(F) \neq 2$\
$(,)$ non-degenerate skew-symmetric bilinear form on $V$. Then

1.  $dim(V)$ even

2.  $\exists$ basis $B = \{e_1,f_1,\dots,e_m,f_m\}$ of $V$\
    s.t matrix of $(,)$ w.r.t $B$ is a block-diagonal matrix
    $$J_m = \underbrace{\begin{pmatrix} 0 & 1\\ -1 & 0\end{pmatrix} \oplus \dots \oplus \begin{pmatrix} 0 & 1\\ -1 & 0\end{pmatrix}}_{m \text{ blocks }}$$
    So that $(e_i,f_i) = -(f_i,e_i) = 1$\
    $(e_i,e_j) = (f_i,f_j) = (e_i,f_j)=(f_j,e_i) = 0\quad \forall i \neq j$

**Corollary 16.5.**\
If $A$ invertible skew-symmetric $n \times n$ matrix over $F$ where
$char(F) \neq 2 \implies n$ even and $A$ congruent to $J_m$\
**Symmetric bilinear forms**\
**Theorem 16.6.**\
$V$ a finite dimensional vector space over $F$ where $char(F) \neq 2$\
$(,)$ a non-degenerate symmetric bilinear form on $V$\
$\implies V$ has orthogonal basis $B = \{v_1,\dots,v_n\}$
$$(v_i,v_j) = 0 \quad \text{ for } i \neq j$$
$$(v_i,v_i) = \alpha_i \neq 0 \quad \forall i$$ Matrix of $(,)$ w.r.t
$B$ $=diag(\alpha_1,\dots,\alpha_n)$\
**Corollary 16.7.**\
$A$ invertible symmetric matrix over $F, char(F) \neq 2$\
$\implies A$ congruent to diagonal matrix

***Computing orthogonal basis for 16.6***

1.  find $v_1$ s.t $(v_1,v_1) \neq 0$

2.  Compute $v_{1}^{\perp}$ and find $v_2 \in v_{1}^{\perp}$ s.t
    $(v_2,v_2) \neq 0$

3.  Compute $Sp(v_1,v_2)^\perp$ and find $v_3 \in Sp(v_1,v_2)^\perp$ s.t
    $(v_3,v_3) \neq 0$

4.  Continue until you get orthogonal basis

***Quadratic Form***\
Assume from now $F$ s.t $char(F) \neq 2$, $V$ a finite dimensional
vector space over $F$\
**Definition - [**Quadratic form**]**\
Quadratic form on $V$ a map $Q: V \to F$ of form
$$Q(v) = (v,v)\qquad \forall v\in V$$ $(,)$ a symmetric bilinear form on
$V$\
$Q$ non-degenerate if $(,)$ non-degenerate.\
*Remarks*\

1.  given $Q$ we find $(u,v) = \frac{1}{2}[Q(u+v)-Q(u)-Q(v)]$

2.  $V = F^{n}$ every symmetric bilinear forms s.t
    $$(x,y) = x^TAy \qquad \text{for } A = A^T, (x,y \in V)$$ For
    $\mathbf{x} = (x_1,\dots,x_n)^T$ $$\begin{aligned}
            Q(x) &= x^TAx\\
            &= \sum_{i,j} a_{ij}x_{i}x_{j}\\
            &= \sum_{i=1}^{n}a_{ii}x_{i}^{2} + 2\sum{i<j}a_{ij}x_{i}x_{j}
        \end{aligned}$$ A general homogeneous quadratic polynomial in
    $x_1,\dots,x_n$ ( all terms of degree 2)

***Change of variables***\
**Definition - [**Equivalent Quadratic
Forms**]**\
$V = F^{n},\ Q: V \to F$\
$Q(x) = x^TAx\ \forall x \in V, A$ symmetric\
Take $y = (y_1,\dots,y_n)^T$ s.t $x = Py$ for $P$ invertible\
$\implies Q(x) = y^TP^TAPy = Q'(y)$\
If such a $P$ exists we say $Q,Q'$
[**equivalent**]

*note:*\
Congruent matrices $A, P^TAP$\
$A \sim P^TAP \iff P$ orthogonal\
**Theorem 16.8.**

$V = F^{n}$, $Q:V\to F$ non-degenerate quadratic form

1.  if $F = \mathbb{C}\implies Q$ equivalent to form\
    $$Q_{0}(x) = x_{1}^{2} + \dots + x_{n}^{2} \quad (x\in \mathbb{C}^{n})$$
    Has matrix $I_{n}$

2.  if $F = \mathbb{R}\implies Q$ equivalent to unique
    $Q_{p,q}; p+q = n$
    $$Q_{p,q}(x) = x_{1}^{2} + \dots + x_{p}^{2} - (x_{p+1}^{2} + \dots + x_{p+q}^{2})\quad (x \in \mathbb{C}^{n})$$
    Has matrix $I_{p,q} =$

    ::: pmatrix
    $I_{p}$ & 0\
    0 & $-I_{q}$
    :::

3.  if $F = \mathbb{Q}\implies \exists$ infinitely many inequivalent
    non-degenerate quadratic forms on $\mathbb{Q}^{n}$

**Definition - [**isometry**]**\
$f = (,)$ a non-degenerate symmetric/skew-symmetric bilinear form on
finite dimensional vector space $V$\
[**Isometry**] of $f$ a linear map
$T:V\to V$ s.t $$(T(u),T(v)) = (u,v)\quad \forall u,v \in V$$ $T$
invertible since $f$ non-degenerate.

**Definition - [**Isometry Group**]**\
$$I(V,f) = \{T: T \text{ an isometry }\}$$ forms a subgroup of general
linear group $GL(V)$\
***Equivalently;***\
fix basis $B$ of $V$, $A$ matrix of $f$ w.r.t $B$ if
$[T]_{B} = X \implies T \in I(V,f) \iff X^TAX = A$
$$\implies I(v,f) \cong \{X \in GL(n,F) : X^TAX = A\}$$

-   $f$ skew-symmetric $\implies$ there is only one form (up to
    equivalence) so we get one isometry group; Classical [***symplectic
    group***] Sp$(V,f)$

-   $f$ symmetric $\implies$ there are many forms, forming the isometry
    groups; the classical [***orthogonal
    groups***] $O(V,f)$


