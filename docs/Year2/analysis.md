---
layout: default
title: Analysis 2
parent: Year 2
nav_order: 0
math: mathjax3
---
# Analysis 2 - Concise Notes 
## MATH50001
**Term 1 Content- ep2?**

{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---
<!-- - [Differentiation in Higher Dimensions](#differentiation-in-higher-dimensions)
  * [Euclidean Spaces](#euclidean-spaces)
    + [Preliminaries](#preliminaries)
    + [Euclidean space of dim. n](#euclidean-space-of-dim-n)
    + [Convergence of Sequences in Euclidean Spaces](#convergence-of-sequences-in-euclidean-spaces)
  * [Continuity](#continuity)
    + [Open sets in Euclidean Spaces](#open-sets-in-euclidean-spaces)
    + [Continuity at a point/on an open set](#continuity-at-a-point-on-an-open-set)
  * [Derivative of a map of Euclidean Spaces](#derivative-of-a-map-of-euclidean-spaces)
    + [Derivative of a linear map](#derivative-of-a-linear-map)
    + [Chain Rule](#chain-rule)
  * [Directional Derivatives](#directional-derivatives)
    + [Rates of change and Partial Derivatives](#rates-of-change-and-partial-derivatives)
    + [Relation between partial derivatives and differentiability](#relation-between-partial-derivatives-and-differentiability)
  * [Higher Derivatives](#higher-derivatives)
    + [Higher derivatives as linear maps](#higher-derivatives-as-linear-maps)
    + [Symmetry of mixed partial derivatives](#symmetry-of-mixed-partial-derivatives)
    + [Taylor's Theorem](#taylor-s-theorem)
  * [Inverse & Implicit Function Theorem](#inverse---implicit-function-theorem)
    + [Inverse Function Theorem](#inverse-function-theorem)
    + [Implicit Function Theorem](#implicit-function-theorem)
    + [Implicit Function Theorem - General Form](#implicit-function-theorem---general-form)
- [Metric and Topological Spaces](#metric-and-topological-spaces)
  * [Metric Spaces](#metric-spaces)
    + [Motivation + Definition](#motivation---definition)
    + [Examples of metrics](#examples-of-metrics)
    + [Normed Vector Spaces](#normed-vector-spaces)
    + [Open sets in metric spaces](#open-sets-in-metric-spaces)
    + [Convergence in Metric Spaces](#convergence-in-metric-spaces)
    + [Closed sets in metric spaces](#closed-sets-in-metric-spaces)
    + [Interior, isolated, limit, and boundary points in metric spaces](#interior--isolated--limit--and-boundary-points-in-metric-spaces)
    + [Continuous maps of metric spaces](#continuous-maps-of-metric-spaces)
  * [Topological Spaces](#topological-spaces)
    + [Topology on a set](#topology-on-a-set)
    + [Convergence, and Hausdorff property](#convergence--and-hausdorff-property)
    + [Closed sets in topological spaces](#closed-sets-in-topological-spaces)
    + [Continuous maps on topological spaces](#continuous-maps-on-topological-spaces)
  * [Connectedness](#connectedness)
    + [Connected sets](#connected-sets)
    + [Continuous maps + Connected sets](#continuous-maps---connected-sets)
    + [Path Connected Sets](#path-connected-sets)
  * [Compactness](#compactness)
    + [Compactness by covers](#compactness-by-covers)
    + [Sequential Compactness](#sequential-compactness)
    + [Continuous maps + Compact Sets](#continuous-maps---compact-sets)
  * [Completeness](#completeness)
    + [Complete metric spaces & Banach space](#complete-metric-spaces---banach-space)
    + [Arzelà-Ascoli](#arzel--ascoli)
    + [Fixed point theorem](#fixed-point-theorem) -->

**Colour Code** - <span style="color: green;">**Definition**</span> are
<span style="color: green;">**green**</span> in these notes,
<span style="color: red;">**Consequences**</span> are <span style="color: red;">**red**</span>
and <span style="color: blue;">**Causes**</span> are <span style="color: blue;">**blue**</span>

*Content from MATH40002 assumed to be known.*


# Differentiation in Higher Dimensions

## Euclidean Spaces

### Preliminaries
<!-- <span style="color: green;">Definition</span> -->
<!-- <span style="color: blue;">Cause</span> -->
<!-- <span style="color: red;">Consequence</span> -->

**Definition** - <span style="color: green;">**Modulus Function**</span>

$$|x| :=
\begin{cases} 
     x, & x\geq 0 \\
     -x, & x \leq 0
\end{cases}
$$

Having the following properties:
1.  $\forall x \in \mathbb{R}, |x| \geq 0, |x| = 0 \iff x = 0$
2.  $\forall x, y \in \mathbb{R}, |xy| = |x||y|$
3.  $\forall x, y \in \mathbb{R}, |x+y| \leq |x| + |y|$ *(Triangle
    inequality)*

### Euclidean space of dim. n

**Define** - <span style="color: green;">**Euclidean Space of dim. $n, \mathbb{R}^{n}$**</span>

Defined as the set of ordered $n$-tuples $(x^{1},\dots,x^{n})$, s.t $\forall i,\ x^{i} \in \mathbb{R}\
$\mathbb{R}^{n}$ a vector space.\

**Define - <span style="color: green;">**Inner Product, $<\cdot,\cdot>,:\mathbb{R}^{n} \times \mathbb{R}^{n} \to \mathbb{R}^$**</span>\
$$<(x^{1},x^{2},\dots,x^{n}),(y^{1},y^{2},\dots,y^{n})> = \sum_{i=1}^{n}x^{i}y^{i}$$

**Define - [**Norm/Lengths, $||\cdot||: \mathbb{R}^{n} \to \mathbb{R}$**]**\
$$||x|| = \sqrt{<x,x>}$$ Having the following properties:

1.  $\forall x \in \mathbb{R}^{n}, ||x|| \geq 0, ||x|| = 0 \iff x = \Vec{0}$
2.  $\forall \lambdax \in \mathbb{R}, x\in \mathbb{R}^{n} ||\lambda x|| = |\lambda|||x||$
3.  $\forall x, y \in \mathbb{R}^{n}, ||x+y|| \leq ||x|| + ||y||$
    *(Triangle inequality)*

**Definition - [**Cauchy-Schwartz
Inequality**]**\
$$|\langle x, y \rangle| \leq ||x||||y||$$\

### Convergence of Sequences in Euclidean Spaces

**Definition - [**Sequence in
$\mathbb{R}^{n}$**]**\
An infinite ordered list, $x_{0}, x_{1},\dots,$ s.t
$x_{i} \in \mathbb{R}^{n} \text{ } \forall  i$. Denoted
$(x_{i})_{i\geq 1} \text{ or } (x_{i})_{i\in \mathbb{N}}$\
Ḏefinition 1.1 - [**Convergence**]\
[**A seq. $(x_{i}) \in \mathbb{R}^{n}$ converges to
$x \in \mathbb{R}^{n}$**] if
[**$\forall \epsilon > 0, \exists N \in \mathbb{N}\text{ s.t } \forall i \geq \mathbb{N}, ||x_{i}-x||<\epsilon$**]\
*Corollary*\
seq. $(x_{i}) \in \mathbb{R}^{n}$ converges to
$x \in \mathbb{R}^{n} \iff$

$$\text{For } x_{i} = (x_{i}^{1},\dots,x_{i}^{n}) \text{ and } x = (x^{1},\dots,x^{n})$$
$$x_{i} \to x \iff \forall k \text{ } x_{i}^{k} \to x^{k} \text{ as } i \to \infty$$

## Continuity

### Open sets in Euclidean Spaces

**Definition - [**Open Ball**]**\
Open ball of radius $r$ is
$$B_{r}(x) = \{y \in \mathbb{R}^{n} : ||x-y||<r\}$$

**Definition 1.2 - [**Open sets**]**\
A set $U \subseteq \mathbb{R}^{n}$ is called
[****open****], if
[**$$\forall x \in U, \exists r > 0 \text{ such that} B_{r}(x) \subseteq U$$**]

### Continuity at a point/on an open set

**Definition 1.3 - [**Continuity at a
point**]**\
Let $A\subset\mathbb{R}^{n}$ an open set, with $f: A \to R^{n}$\
[**$f$ continuous at $p \in A$**] if
[**$$\forall \epsilon > 0, \exists \delta > 0 \text{ s.t } ||x-p|| < \delta \implies ||f(x)-f(p)|| < \epsilon$$**]
$f$ is (pointwise) continuous on $A\subseteq \mathbb{R}^{n} \iff$
continuous $\forall p \in A$, we write $f$ is continuous.\
For small enough $\delta$, we have
$f(B_{\delta}(p)) \subseteq B_{\epsilon}(f(p))$\
**Theorem 1.2 - Composition of continuous functions**\
[ **Let $A \subseteq \mathbb{R}^{n}$ open, $B \subseteq \mathbb{R}^{m}$
open and suppose $f: A \to B$ continuous at $p\in A$, and
$g: B \to \mathbb{R}^{l}$ continuous at $f(p)$** ]

 center
[**Then $g \circ f: A \to \mathbb{R}^{l}$ continuous at
p**]


**Definition 1.4 - [**Limit of a function at a
point**]**\
$A \subseteq \mathbb{R}^{n}$ an open set. $f$ a function
$f: A \to \mathbb{R}^{m}$, with $p \in A$ and $q \in \mathbb{R}^{m}$\
[**Say $\lim_{x\to p}f(x) = q$**] if
[**$\forall \epsilon > 0, \exists \delta > 0 \text{ s.t } \forall x \in A \text{ with } 0 < ||x-p|| <\delta \text{ we have } ||f(x) - p|| < \epsilon$**]
$$f \text{ continuous at } p \iff \lim_{x\to p}f(x) = q$$

**Theorem 1.3 - Algebra of Limits**\
Suppose $A \subseteq \mathbb{R}^{n}$ open, with $p \in A$ and
$f,g: A \to \mathbb{R}^{n}$
[**$$\lim_{x\to p}f(x) = F \text{ and } \lim_{x\to p}g(x) = G$$\
**] Then:

1.  [**$\lim_{x\to p}(f(x) + g(x)) = F + G$**]

2.  [**$\lim_{x\to p}(f(x)g(x)) = FG$**]

3.  [**If, $G\neq 0$ then
    $\lim_{x\to p}\frac{f(x)}{g(x)} = \frac{F}{G}$**]

## Derivative of a map of Euclidean Spaces

### Derivative of a linear map

**Lemma 1.5**\
*The map $f:(a,b) \to \mathbb{R}$ differentiable at
$p \in (a,b) \iff \exists$ map of the form
$A_{\lambda}(x) = \lambda(x-p) + f(p)$ for some $\lambda \in \mathbb{R}$
s.t* $$\lim_{x\to p}\frac{|f(x) - A_{\lambda}(x)|}{|x-p|} = 0$$

**Notation** $$h[v] \text{ for h a linear map, v a vector}$$
$$h(v) \text{ h a map, v a point in domain of h}$$
$$L(\mathbb{R}^{n};\mathbb{R}^{m}) - \text{\textbf{Set of linear maps from }} \mathbb{R}^{n} \to \mathbb{R}^{m}$$

**Definition 1.5 - [**Derivative in higher
dimension**]**\
Suppose $\Omega \subset \mathbb{R}^{n}$ open. [**The map
$f:\Omega \to \mathbb{R}^{m}$
**[**differentiable**]****]
at $p \in \Omega$ if [**$\exists$ a linear map
$\Lambda \in L(\mathbb{R}^{n};R^{m})$**] such that
$$\lim_{x\to p}\frac{||f(x) - (\Lambda[x-p] + f(p))}{||x-p||} = 0$$ We
write $$Df(p) := \Lambda$$ Calling $Df(p)$ the derivative of $f$ at $p$\
$\Lambda$ a $m\times n$ matrix called the
[**Jacobian**]\
**Lemma 1.6 - Differentiable then continuous**\
$\Omega \subset \mathbb{R}^{n}$ open, $f:\Omega \to \mathbb{R}^{m}$
differentiable at $p\in \Omega \implies f$ continuous at $p$\
**Theorem 1.7 - Uniqueness of Derivative**\
*The derivative, [**if it exists**], [**is
unique**]*

### Chain Rule

**Chain rule in $\mathbb{R}$**\
$f,g: \mathbb{R}\to \mathbb{R}, g$ differentiable at $p$, $f$
differentiable at $g(p)$ Then $f \circ g$ differentiable at $p$ with
$$(f\circ g)'(p) = f'(g(p))g'(p)$$

**Theorem 1.8 - Chain rule in higher dim.**\
$\Omega \subset \mathbb{R}^{n}$ open, $\Omega' \subset \mathbb{R}^{m}$
open\
With $g:\Omega \to \Omega'$ differentiable at $p \in \Omega$,
$f:\Omega' \to \mathbb{R}^{l}$ differentiable at $g(p) \in \Omega'$\
Then $h = f \circ g: \Omega \to \mathbb{R}^{l}$, differentiable at $p$,
s.t $$Dh(p) = D(f(g(p))\circ Dg(p)$$

## Directional Derivatives

### Rates of change and Partial Derivatives

**Definition - [**Directional
Derivative**]**\
The [**directional derivative**] of $f$ at
$p$ in the direction $v$ is
$$\frac{\partial f}{\partial v}(p) := \lim_{t\to 0}\frac{1}{t}[f(p+vt)-f(p)] = Df(p)[v]$$
**Definition - [**Partial derivatives**]**\
We can find any directional derivative at $p$, given we know the partial
derivatives of $f$ $$D_{i}f(p) = \frac{\partial f}{\partial e_{i}}(p)$$
In $\mathbb{R}^{3}$ we have, $$Df(p)[v] = 
\begin{pmatrix}
\ D_{1}f(p)\quad  D_{2}f(p)\quad D_{3}f(p)\quad
\end{pmatrix}
\begin{pmatrix}
v^{1}\\
v^{2} \\
v^{3} 
\end{pmatrix}$$

**Definition - [**Gradient**]**\
*Gradient of $f$ at $p$* $$\nabla f(p) = 
\begin{pmatrix}
D_{1}f(p)\\
D_{2}f(p) \\
D_{3}f(p)
\end{pmatrix}\qquad
Df(p) = (\nabla f(p))^{t}$$

**Theorem 1.9 - Jacobian**\
Suppose $\Omega \subset \mathbb{R}^{n}$ open and
$f: \Omega \to \mathbb{R}^{m}$ of the form $$f(x) = 
\begin{pmatrix}
f^{1}(x),f^{2}(x),\dots,f^{m}(x)
\end{pmatrix}$$ [**If $f$ differentiable for some
$p \in \Omega$**] Then [**Jacobian of $f$ at $p$
is:**] $$Df(p) = 
\begin{pmatrix}
D_{1}f^{1}(p) & \dots & D_{n}f^{1}(p)\\
\vdots & \ddots & \vdots\\
D_{1}f^{m}(p) & \dots & D_{n}f^{m}(p)
\end{pmatrix}$$

### Relation between partial derivatives and differentiability

**Theorem 1.12**\
Let $\Omega \subset \mathbb{R}^{n}$ open, $f:\Omega\to \mathbb{R}$.
[**Suppose the partial derivatives:**]
$$D_{i}f(x) := \lim_{t\to 0}\frac{f(x+te_{i}-f(x)}{t}$$ [**exist
$\forall x \in \Omega$, with each map $x \mapsto D_{i}f(x)$ continuous
at $p, \forall i$**]$\implies$ [**$f$ is
differentiable at $p$**]

## Higher Derivatives

### Higher derivatives as linear maps

Can think of the differential of $f$, $Df(p)$ as a map
$$Df: \Omega \to L(R^{n};R^{m}) = \Omega \to \mathbb{R}^{mn}$$
$$\quad p \mapsto Df(p)$$ [**if map $Df$ is
continuous**] $\implies f:\Omega \to \mathbb{R}$ is
**[**continuously differentiable**]**\
**Definition - [**Higher derivative**]**\
If $Df: \Omega \to \mathbb{R}^{mn}$ differentiable at $p$, denote
derivative of $Df$ as $DDf(p): \mathbb{R}^{n} \to \mathbb{R}^{nm}$
$$DDf(p) \in L(\mathbb{R}^{n};\mathbb{R}^{nm}) = L(\mathbb{R}^{n};L(\mathbb{R}^{n};\mathbb{R}^{m}))$$
Where $DDf(p)$ is a linear map
$\mathcal{L} \in L(\mathbb{R}^{n};L(\mathbb{R}^{n};\mathbb{R}^{m}))$,
satisfying:
$$\lim_{x\to p}\frac{||Df(x) - Df(p) - \mathcal{L}[x-p]||}{||x-p||} = 0$$
$DDf(p)$ takes an $n$-vector to a $m\times n$ matrix\
**Definition - [**Continuously
differentiable**]**\
*[**$f:\Omega \to \mathbb{R}^{m}$ is $k$-times dfferentiable with all
continuous derivatives**]* $\implies$ [**$f$ is
$k$-times continuously differentiable**]

**Testing for $k$-times differentiability**\
For $f = \begin{pmatrix}
f^{1}(x),f^{2}(x),\dots,f^{m}(x)
\end{pmatrix}$\
If $f$ differentiable at $p\in \Omega \implies$ we have partial
derivatives $D_{i}f^{j}: \Omega \to \mathbb{R}$.\
If $Df$ differentiable, then $2^{\text{nd}}$ partial derivatives exist
$$D_{k}D_{i}f^{j}(p) := \lim_{t\to 0}\frac{D_{i}f^{j}(p+te_{k})-D_{i}f^{j}(p)}{t}$$
Easy to check these exist and are continuous $\implies$ $k$-times
differentiability at $p$

### Symmetry of mixed partial derivatives

**Theorem 1.13 - Schwartz' Theorem**\
Suppose $\Omega \subset \mathbb{R}^{n}$ open and
$f:\Omega \to \mathbb{R}$ differentiable $\forall p \in \Omega$\
Suppose also, for $i,j \in \{1,\dots,n\}, 2^{\text{nd}}$ partial
derivatives $D_{i}D_{j}f$ and $D_{j}D_{i}f$ exist and are continuous
$\forall p \in \Omega$
[**$$\forall p \in \Omega, D_{i}D_{j}f(p) = D_{j}D_{i}f(p)$$**]

**Definition - [**Hessian**]**\
The matrix of $2^{\text{nd}}$ partial derivatives at the point $p$
$$\text{Hess } f(p) = [D_{i}D_{j}f(p)]_{i,j =1,\dots,n}$$ Schwartz'
Theorem says Hess $f(p$ is a symmetric matrix

### Taylor's Theorem

**Definition - [**Multi-inidices**]**\
Multi-index $\alpha \in (\mathbb{N})^{n}, \alpha = \begin{pmatrix}
\alpha_{1},\dots,\alpha_{n}
\end{pmatrix}$\
We define
[**$|a| = \sum_{i=1}^{n}\alpha_{i}$**] and
[**$$D^{\alpha}f := (D_{1})^{\alpha_{1}}(D_{2})^{\alpha_{2}}\dots(D_{n})^{\alpha_{n}}f,$$**]
And for a vector $h = \begin{pmatrix}
h_{1},\dots,h_{n}
\end{pmatrix}$
[**$$h^{\alpha} := (h^{1})^{\alpha_{1}}(h^{2})^{\alpha_{2}}\dots(h^{n})^{\alpha_{n}}$$**]
Also
[**$$\alpha ! := \alpha_{1}!\alpha_{2}!\dots\alpha_{n}!$$**]\
*helpful examples*

 center
$D^{(0,3,0)}f(p) = D_{2}^{3}f(p)$\
$D^{(1,0,1)}f(p) = D_{1}D_{3}f(p)$\
$(x,y,z)^{(2,1,5)} = x^{2}y^{1}z^{5}$\


\

**Theorem 1.14 - Taylor's Theorem in higher dim.**\
Suppose $p \in \mathbb{R}^{n}$ and $f: B_{r}(p) \to \mathbb{R}$ a
$k$-times continuously differentiable $\forall q \in B_{r}(p)$, for some
$k \geq 1 \in \mathbb{N}$\
Then $\forall h \in \mathbb{R}^{n}$ with $||h|| < r$ We have [
**$$f(p+h) = \sum_{|\alpha| \leq k-1}\frac{h^{\alpha}}{\alpha!}D^{\alpha}f(p) + R_{k}(p,h)$$**
] Sum over all $\alpha = \begin{pmatrix}
\alpha_{1},\dots,\alpha_{n}
\end{pmatrix}$\
with $|\alpha| \leq k-1$ and remainder term
$$R_{k}(p,h) = \sum_{|\alpha| = k}\frac{h^{\alpha}}{\alpha!}D^{a}f(x)$$
for some $x$ s.t $0 < ||x-p||< ||h||$\
Evidently $$\lim_{h\to 0}\frac{|R_{k}(p,h)|}{||h||^{k-1}} = 0$$

## Inverse & Implicit Function Theorem

### Inverse Function Theorem

\
Let $\Omega$ an open set in $\mathbb{R}^{n}$,
$f: \Omega \to \mathbb{R}^{n}$ continuously differentiable on $\Omega$,
$\exists q \in \Omega$ s.t $Df(q)$ invertible\
Then $\exists$ open sets $U \subset \Omega$ and
$V \subset \mathbb{R}^{n}, q \in U, f(q) \in V$ s.t

1.  $f:U \to V$, a bijection

2.  $f^{-1}: V \to U$, continuously differentiable

3.  $\forall y \in V$, $$Df^{-1}(y) = [Df(f^{-1}(y))]^{-1}$$

### Implicit Function Theorem

**Theorem 1.16 - *(Implicit Function Theorem - Simple version)***\
$\Omega \subset \mathbb{R}^{2}$ open\
$F: \Omega \to \mathbb{R}$ continuously differentiable and
$\exists (x',y') \in \Omega$ s.t

1.  $F(x',y') = 0$, and

2.  $D_{2}F(x',y') \neq 0$

$\implies \exists$ open sets $A, B \subset \mathbb{R}$ with
$x' \in A, y' \in B$ with a map $f:A \to B$ s.t
$$(x,y) \in A \times B \text{ satisfies } F(x,y) = 0 \iff y = f(x) \text{for some } x \in A$$
with $f:A \to B$ continuously differentiable.\
**Definition - [
**$C^{1}-$diffeomorphism**]**\
$\Omega,\Omega' \subset \mathbb{R}^{n}$ open.\
Say $f:\Omega \to \Omega'$ a $C^{1}$-diffeormorphism, if
$f:\Omega \to \Omega'$ a and $\forall x \in \Omega, Df(x)$
**invertible**\
$\mathcal{D}$ the set of all $C^{1}-$diffeomorphisms from
$\Omega \to \Omega$, a group under group law; composition.\

### Implicit Function Theorem - General Form

**Theorem 1.17 - *(Implicit Function Theorem)***\
$\Omega \subset \mathbb{R}^{n}, \Omega' \subset \mathbb{R}^{m}$ open
sets\
$F: \Omega \times \Omega' \to \mathbb{R}^{m}$ continuously
differentiable on $\Omega \times \Omega'$ and sps
$\exists (a,b) \in \Omega \times \Omega'$ s.t

1.  $f(p) = 0$ and,

2.  $m \times n$ matrix $$(D_{n+j}f^{i}(p)), \qquad 1 \leq i, j\leq m$$
    invertible

$\implies \exists$ open sets $A \subset \Omega, B \subset \Omega'$ with
$a \in A, b \in B$ with a map $g:A \to B$ s.t
$$g(x,y) = 0 \text{ for some } (x,y) \in A \times B \iff y = g(x) \text{for some } x \in A$$
with $g:A \to B$ continuously differentiable.\

# Metric and Topological Spaces

## Metric Spaces

### Motivation + Definition

**Definition 2.1 - [**Metric**]**\
$X$ an arbitrary set\
Metric a function $d: X \times X \to \mathbb{R}$ satisfying:

1.  $\forall x,y \in X;\ d(x,y) \geq 0, d(x,y) = 0 \iff x = y$
    ***(positivity)***

2.  $\forall x,y \in X;\ d(x,y) = d(y,x)$ ***(symmetry)***

3.  $\forall x,y,z \in X d(x,y) \leq d(x,z) + d(z,y)$ ***(triangle
    inequality)***

**Definition 2.2 - [**Metric space**]**\
Pair of a set and metric; $M = (X,d)$\
Call elements of $X$ points,with $d(x,y)$ distance between $x,y$ w.r.t
$d$\
**Definition**\
$$C([a,b]) = \{f:[a,b] \to \mathbb{R}| f:[a,b] \to \mathbb{R}\text{continuous}\}$$

### Examples of metrics

-   $d_{2}(x,y) = ||x-y||$; Euclidean metric on $\mathbb{R}^{n}$

-   $d_{\text{disc}}(x,y) =$

     cases
    0, & x=y\
    1, & xy
    

-   $d_{\infty}(x,y) = \text{sup}_{k\geq 1}|x^{k} - y^{k}|$

-   $d_{\infty}(f,g) = \text{max}_{a\leq t\leq b}|f(t) - g(t)$ where
    $f,g \in C([a,b])$ ***(supremum/uniform metric)***

 
**Definition 1**. [**Induced metrics**]


\
$(X,d)$ a metric space\
$Y \subseteq X$, define $d|_{Y}: Y \times Y \to \mathbb{R}$ as
$d|_{Y}(x,y) = d(x,y)\ \forall x,y \in Y$

 
**Definition 2**. [**Metric Subspace**]


\
Say $(Y,d|_{Y})$ a metric subspace of $(X,d)$

 
**Definition 3**. [**Product metric space**]


$(X_{1},d_{1})$ and $(X_{2},d_{2})$ metric spaces.\
define metric using
$d_{1},d_{2}$ $d: (X_{1} \times X_{2}) \times (X_{1} \times X_{2}) \to \mathbb{R}$.\
$(X_{1} \times X_{2}, d)$ a product metric space.

### Normed Vector Spaces

 
**Definition 4**. [**Norm in Metric
Spaces**]


$V$ a vector space on $\mathbb{R}$. Say $||\cdot||: V \to \mathbb{R}$ a
[**norm**] on $V$ if

1.  $\forall v \in V,\ ||v|| \geq 0$ and $||v|| = 0 \iff v = 0$

2.  $\forall v \in V, \forall \lambda \in \mathbb{R},\ ||\lambda v|| = |\lambda|\cdot||v||$

3.  $\forall u,v \in V,\ ||u+v|| \leq ||u|| + ||v||$

\
\
A pair of a vector space $(V, ||\cdot||)$\
note $||\cdot||$ is a metric on $V \implies$ normed vector space a
metric space.

### Open sets in metric spaces

 
**Definition 5**. [**Open ball in metric spaces**
]


\
$(X,d)$, with $x \in X, \epsilon \in \mathbb{R}; \epsilon > 0$\
$$\text{Ball radius } \epsilon;\ B_{\epsilon}(x) = \{ x' \in X | d(x,x') < \epsilon\}$$
notation; $B_{\epsilon}(x,X,d)$

 
**Definition 6**. [**Open set in metric
space**]


$(X,d)$ a metric space. $U \subseteq X$ open in $(X,d)$ if:
$$\forall u \in U,\ \exists \delta > 0 \in \mathbb{R}\text{ s.t } B_{\delta}(u) \subset U$$

 
**Definition 7**. [**Topologically
equivalent**]


$d_{1},d_{2}$ metrics on a set $X$ **topologically equivalent** if:
$$\forall\ U \subseteq X,\ U \text{ open in } (X,d_{1}) \iff U \text{ open in }  (X,d_{2})$$

### Convergence in Metric Spaces

 
**Definition 8**. [**Convergence in Metric
Spaces**]


$(X,d)$ a metric space. $(x_{n})_{n\geq 1}$ a sequence in $X$.\
Say $(x_{n}) \to x \in (X,d)$ if
$$\forall\ \epsilon > 0, \exists N \in \mathbb{N}\text{ s.t } \forall\ n \geq N, d(x,x_{n})< \epsilon$$
***Lemma 2.7.*** - if $(x_n)$ converges in $(X,d)$ $\implies$ limit is
unique\
***Corollary*** - $d_{1},d_{2}$ topologically equivalent $\iff (x_n)$
converges in $(X,d_1)$ and $(X,d_2)$

### Closed sets in metric spaces

 
**Definition 9**. [**Closed set in Metric
Spaces**]


$(X,d)$ a metric space. $V \subseteq X$ a set.\
$V$ **closed** in $(X,d)$ if $\forall\ (x_n) \in V$ s.t $(x_n) \to x$
convergent in $(X,d) \implies x \in V$

 
**Theorem 1**.


$(X,d)$ a metric space. $V \subseteq X$\
$$V \text{ closed in } (X,d) \iff X\backslash V \text{ open in } (X,d)$$
***Lemma 2.10***

1.  Intersection of closed sets in $(X,d)$ is a closed set in $(X,d)$

2.  Finite union of closed sets in $(X,d)$ a closed set in $(X,d)$

### Interior, isolated, limit, and boundary points in metric spaces

 
**Definition 10**. **- 2.12.**


$(X,d)$ a metric space, $V \subset X,\ x \in X$

1.  $x$ an [**interior/inner point**] of $V$
    if $$\exists \delta > 0,\ \text{ s.t } B_{\delta}(x) \subset V$$

    1.  [**Interior of $V$; $V^{\circ}$**]
        - $\{v \in V : v \text{ an interior point of } V\}$

    \

2.  $x$ a [**limit/accumulation point**] of
    $V$ if
    $$\forall \delta > 0, (B_{\delta}(x) \cap V)\backslash\{x\} \neq \emptyset$$
    ***Note:** not all limit points of $V$ are in $V$*

    1.  [**Closure of $V$; $\bar{V}$**] -
        $V \cup \{v \text{ a limit point of } V\}$

    \

3.  $x$ a [**boundary point of $V$**] if
    $$\forall \delta > 0, B_{\delta} \cap V \neq \emptyset \text{ and } B_{\delta}(x)\backslash V \neq \emptyset$$

    1.  [**Boundary of $V$; $\partial V$
        -**]
        $\{v \in X : v \text{ a boundary point of } V\}$

    \

4.  $x$ an [**isolated point**] of $V$ if
    $$\exists \delta > 0, \text{ s.t } V \cap B_{\delta}(x) = \{x\}$$

***Lemma 2.11*** $(X,d)$ a metric space, $V \subseteq X$\
$x \in X$ a limit point of $V \iff \exists$ sequence in
$V \backslash \{x\}$ converging to $x$.

 
**Definition 11**. [**Dense and Seperable
subsets**]


$(X,d)$ a metric space

-   $V \subseteq X$ **dense** in $X$ if $\bar{V} = X$

-   $(X,d)$ seperable if, $\exists$ dense countable subset of $X$

### Continuous maps of metric spaces

 
**Definition 12**. [**Continuity in metric
spaces**]


$(X,d_{X}), (Y,d_{Y})$ metric spaces.\
$f: X \to Y$ a map

1.  $f$ [**continuous**] at $x \in X$ if
    $$\forall \epsilon > 0, \exists \delta > 0 \text{ s.t } \forall x' \in X \text{ s.t } d_{X}(x',x) < \delta, d_{Y}(f(x),f(x')) < \epsilon$$

2.  $f: X \to Y$ continuous if $f$ continuous $\forall x \in X$

3.  $f: X \to Y$ uniformly continuous if $f$ continuous
    $\forall x \in X$ with $\delta = \delta(\epsilon)$ not depending on
    $x$

 
**Theorem 2**.


$(A_{1},d_1),(A_2,d_2)$ metric spaces\
$f: A_1 \to A_2$ continuous $\iff$ pre-image of any open set in $A_2$ is
an open set in $A_1$\
$f: A_1 \to A_2$ continuous $\iff$ pre-image of any closed set in $A_2$
is a closed set in $A_1$

 
**Theorem 3**.


$(X,d_X), (Y,d_Y)$ metric spaces\
$f: X \to Y$ a map;
$$f \text{ continuous at } x \in X \iff \text{ for any sequence } (x_n) \to x;\ f(x_n) \to f(x) \text{ in } (Y,d_Y)$$\

 
**Definition 13**. [**Homeomorphism**]


$(X_1,d_1),(X_2,d_2)$ metric spaces.

1.  $f: X_1 \to X_2$ a [**homeomorphism** ]
    if

    -   $f: X_1 \to X_2$ a bijection

    -   $f: X_1 \to X_2$ and $f^{-1}:X_2 \to X_1$ continuous

2.  Say $(X_1,d_1),(X_2,d_2)$
    [**homeomorphic**] if $\exists$
    homeomorphism from $X_1$ to $X_2$

 
**Definition 14**.


$(X,d_X),(Y,d_Y)$ metric spaces with $f:X\to Y$\

1.  $f$ is [**Lipschitz**] if $\exists$
    constant $M > 0$ s.t
    $\forall x_1,x_2 \in X, d_Y(f(x_1),f(x_2)) \leq M \cdot d_X(x_1,x_2)$

2.  $f$ is [**bi-Lipschitz**] if $\exists$
    constants $M_1,M_2 > 0$ s.t $\forall x_1,x_2 \in X$
    $$M_2 \cdot d_X(x_1,x_2) \leq d_Y(f(x_1),f(x_2)) \leq M_1 \cdot d_X(x_1,x_2)$$
    ***Corollary;** any bi-Lipschitz map is injective*

3.  $f$ an [**isometry/distance
    preserving**] if
    $\forall x_1,x_2 \in X;$ $$d_Y(f(x_1),f(x_2)) = d_X(x_1,x_2)$$

## Topological Spaces

### Topology on a set

 
**Definition 15**. [**Topology** ]


$A$ an arbitrary set. $\tau$ a collection of subsets of $A$\
$\tau$ a [**topology**] on $A$ if:

1.  $\emptyset \in \tau$ and $A \in \tau$

2.  $G_{\alpha} \in \tau$ for $\alpha$ in a (finite) set $I$
    $\implies \bigcup_{\alpha \in I}G_{\alpha} \in \tau$

3.  $G_{1},G_{2},\dots,G_{m} \in \tau\implies \bigcap_{i=1}^{m}G_{i} \in \tau$

A [**topological space**]; $(A,\tau)$ a pair
of a set $A$ and topology $\tau$ on $A$. Each element in $\tau$ an open
set in $(A,\tau)$\
$U$ a neighbourhood of $a$ if $U \in \tau$ and $a \in U$

 exmp
**Example 1**. Some Topologies


1.  **Coarse topology -** $A$ arbitrary set, $\tau= \{\emptyset, A\}$

2.  **Induced topology -** $(X,d)$ a metric space, with $\tau$ the
    collection of all open sets in $(X,d)$

3.  **Order Topology -** $A = \mathbb{R}$ with $\tau$ collection of
    subsets of $\mathbb{R}$ of form
    $(a,+\infty),\ a \in \mathbb{R}\cup \{-\infty,+\infty\}, (\+infty,+\infty) := \emptyset$

4.  **Discrete Topology** - $A$ arbitrary, $\tau= \mathcal{P}(A)$

5.  **Product topology** -

**Definition.** [**Metrisable topological
space**]\
Say topological space $(X,\tau)$
[**metrisable**] if $\exists$ metric on $X$
which induces a topology $\tau$.\
**Definition.** [**Induced and Subspace
topology**]\
$(X,\tau)$ a topological space. $Y \subset X$
$$\tau_{Y} = \{U \cap Y | U \in \tau\}$$ $\tau_{Y}$ the [**induced
topology**] on $Y$ from $(X,\tau)$\
$(Y,\tau_{Y})$ has the [**subspace
topology**] induced from $(X,\tau)$

 
**Definition 16**. [**Stronger topology**]


$A$ a set, with $\tau_1,\tau_2$\
Say $\tau_1$ stronger (or finer) than $\tau_2$ if
$\tau_2 \subset \tau_1$

***Lemma 2.14.***\
$(A,\tau)$\
A set $G \subset A$ open $\iff \forall\ x \in G,\ \exists$ neighbourhood
of $x$ contained in $G$

 
**Definition 17**. [**Interior in Topological
space**]


$(A,\tau)$ a topological space. $\Omega \subseteq A$\
$z \in \Omega$ an interior point of $\Omega if$
$$\exists U \in \tau\text{ s.t } z \in U \text{ and } U \subset \Omega$$
[**interior of $\Omega; \Omega^{\circ}$**] =
$\{z \in \Omega | z \text{ an interior point of } \Omega\}$\

-   $S \subset T \implies S^{\circ} \subset T^{\circ}$

-   $S$ open in $A \iff S = S^{\circ}$

-   $S^{\circ}$ largest open set contained in $S$

### Convergence, and Hausdorff property

 
**Definition 18**. [**Convergence in Topological
Spaces**]


$(A,\tau)$ a topological space. $(x_n)_{n\geq1}$ a sequence in $A$\
$(x_n)$ [**converges**] in $(A,\tau)$ if
$$\exists x \in A \text{ s.t } \forall\ G \in \tau\text{ with } x \in G,\ \exists N \in \mathbb{N}, \text{ s.t } \forall n \geq N, x_n \in G$$

 
**Definition 19**. [**Hausdorff**]


$(A,\tau)$ called [**Hausdorff**] if:
$$\forall x,y \in A\ x \neq y,\ \exists \text{ open set } U,V \text{ s.t } x \in U, y \in V \text{ and } U \cap V = \emptyset$$
Say $U$ and $V$ seperate $x$ and $y$

 
**Theorem 4**.


$(A,\tau)$ a Hausdorff topological space. $(x_n)$ a sequence in $A$.\
if $(x_n)$ convergent in $(A,\tau) \implies$ limit is unique.

### Closed sets in topological spaces

 
**Definition 20**. [**Closed set in Topological
space**]


$(A,\tau)$ a topological space.\
$V \subseteq A$. Say $V$ closed in
$(A,\tau) \iff A\backslash V \in \tau$\
***Lemma 2.17.***\
$(A,\tau)$ a topological space $\implies \emptyset$ and $A$ closed in
$(A,\tau)$

1.  intersection of closed sets in $(A,\tau)$ is a closed set in
    $(A,\tau)$

2.  union of a finite number of closed sets in $(A,\tau)$ is a closed
    set in $(A,\tau)$

 
**Definition 21**. [**Limit/Accumulation point in Topological
Spaces**]


$(A,\tau),$ a topological space, $S\subseteq A$\
$x \in A$ a [**limit/accumulation point**]
of $S$ if
$$\forall\ U \text{ a neighbourhood of } x,\ (S \cap U)\backslash\{x\} \neq \emptyset$$
$x$ not necessarily in $S$\
[**Closure of
$S, \bar{S}$**]$= S \cup \{ x \in A | x \text{ a limit point of } S\}$

***Lemma***\
$S$ closed in $(A,\tau) \iff S = \bar{S}$

### Continuous maps on topological spaces

 
**Definition 22**. [**Continuity in topological
space**]


$(X,\tau_X),(Y,\tau_Y)$ with $f: X \to Y$\
$f$ continuous on $X$ if:
$$\forall \text{open sets } U \in Y,\ f^{-1}(U) \text{ open in } X$$

 
**Theorem 5**.


$(X,\tau_X),(Y,\tau_Y)$ with $f: X \to Y$\
$f$ continuous $\iff$ pre-image of closed set in $Y$ is closed in $X$

 
**Theorem 6**.


$(X,\tau_X),(Y,\tau_Y),(Z,\tau_Z)$\
$f: X \to Y, g:Y\to Z$ continuous $\implies g \circ f : X \to Z$
continuous

 
**Definition 23**. [**Homeomorphisms in Topological
space**]


$f X \to Y$ a homeomorphism is $f: X \to Y$ bijective with $f$ and
$f^{-1}$ continuous

 
**Definition 24**. [**Topologically equivalent in Topological
space**]


$(X,\tau_X),(Y,\tau_Y)$ **topologically equivalent/homeomorphic** if
$\exists$ homeomorphism from $X \to Y$

## Connectedness

### Connected sets

 
**Definition 25**. [**Disconnected sets**]


For $(X,d)$ a metric space, consider $T \subseteq X$. $T$
[**disconnected**],if $\exists$ open sets
$U,V \in X$ s.t:

1.  $U \cap V = \emptyset$

2.  $T \subseteq U \cup V$

3.  $T \cap U \neq \emptyset$ and $T \cap V \neq \emptyset$

Set conneted if not disconnected.

**Lemma 2.23.**\
$(X,d)$ a metric space. $T \subseteq X$
$$T  \text{ disconnected } \iff\ \exists \text{ continuous } f:T \to \mathbb{R}\text{ s.t } f(T) = \{0,1\}$$

 
**Theorem 7**.


Consider $(\mathbb{R},d)$, $S \subseteq \mathbb{R}$
$$S \text{ connected } \iff S \text{ an interval }$$

### Continuous maps + Connected sets

 
**Theorem 8**.


$(A,d_{1})$ and $(A,d_{2})$ metric spaces. $f: A_1 \to A_2$ continuous
map\
$S \subset A$ connected $\implies f(S)$ connected

\
$f:(X,d_X) \to (Y,d_Y)$ a homeomorphism\
$$X \text{ connected } \iff Y \text{ connected }$$

 
**Theorem 9**.


$(X,d)$ connected metric space, $f: X \to \mathbb{R}$ continuous. Assume
$\exists a,b \in X$ s.t $f(a) <0, f(b) > 0 \implies \exists c \in X$ s.t
$f(c) = 0$

### Path Connected Sets

 
**Definition 26**. [**Path**]


Under $(X,d)$ given $a,b \in X$\
**Path** from $a \to b$ a continuous map $f: [0,1] \to X$ s.t
$f(0) = a, f(1) = b$

 
**Definition 27**. [**Path Connected**]


$(X,d)$ path connected if $\forall a,b \in X, \exists$ path from
$a\to b$ in $X$

 
**Theorem 10**.


if $(X,d)$ path connected $\implies$ connected

## Compactness

### Compactness by covers

 
**Definition 28**. [**Covers**]


$(X,d)$ a metric space. $Y \subseteq X$

1.  collection $R$ of open subsets of $X$ an [**open
    cover**] for $Y$ if
    $$Y \subseteq \bigcup_{v \in R}v$$

2.  Given open cover $R$ for $Y$\
    Say $C$ a [**sub-cover**] of $R$ for $Y$
    if $C \subseteq R$ and $Y \subseteq \bigcup_{v \in R}v$

3.  Open cover $R$ for $Y$ is a [**finite
    cover**] if $R$ has finitely many
    elements.

 
**Definition 29**. [**Compact**]


$(X,d)$ a metric space\
$Y \subseteq X$ compact in $(X,d)$ if every open cover for $Y$ has a
finite sub-cover.\
**Proposition 2.32.**\
$a,b \in \mathbb{R},\ a \leq b$ in $(R,d_1)$ we have $[a,b]$ compact\
**Proposition 2.33.**\
$(X,d)$ a metric space, $Y \subseteq X$\
$X$ compact, $Y$ closed $\implies Y$ compact.\

 
**Theorem 11**.


$(X,d)$ a metric space $Y \subset X$
$$Y \text{ compact } \implies Y \text{ closed }$$

 
**Theorem 12**.


$(X,d_X),(Y,d_Y)$ metric spaces. Considering $(X\times Y,d)$\
$d((x_{1},y_{1}),(x_{2},y_{2})) = d_{1}(x_1,x_2) + d_2(y_1,y_2)$\
$X, Y$ compact $\implies (X \times Y,d)$ compact

**Corollary.**\
$[a_1,b_1]\times[a_2,b_2]\dots\times[a_{n-1},b_{n-1}]\times[a_n,b_n]$
compact in $\mathbb{R}^{n}$

 
**Definition 30**. [**Bounded**]


$(X,d)$ non-empty metric space, $Z \subseteq X$\
$Z$ [**bounded**] in $(X,d)$ if
$\exists M \in \mathbb{R}$ s.t $\forall x,y \in Z; d(x,y) \leq M$\
$S$ arbitrary set. $f: S \to X$ bounded if $f(S)$ bounded in $X$

**Lemma 2.37.**\
$(X,d)$ compact metric space $\implies X$ bounded

 
**Theorem 13**. [**Heine-Borel**]


Consider $(\mathbb{R}^{n},d_{2})$, $X \subseteq \mathbb{R}^{n}$\
$X$ compact $\iff X$ closed and bounded

### Sequential Compactness

 
**Definition 31**. [**Sequentially
compact**]


$(X,d)$ sequentially compact, if for every sequence in $X$ has
convergent subsequence in $(X,d)$
$$\forall (x_n)_{n\geq 1} \in X,\ \exists (x_{n_k})_{k\geq 1},\ x \in X \text{ s.t } x_{n_k} \to x$$

**Lemma 2.39.**\
$(X,d)$ a metric space. with sequence $(x_n)_{n\geq 1}$ s.t
$\exists (x_{n_k})_{k\geq 1},\ x \in X \text{ s.t } x_{n_k} \to x$.\
$$\iff \exists x \in X \text{ s.t } \forall \epsilon > 0 \text{ there are infinitely many } i \text{ s.t } x_{i} \in B_{\epsilon}(x)$$

 
**Theorem 14**. [**Bolzanno-Weierstrass**]


Any bounded sequence in $\mathbb{R}^{n}$ has convergent subsequence.

 
**Theorem 15**. **+ 2.42.**


$(X,d)$ metric space.
$$X \text{ Compact  }\iff X \text{ Sequentially Compact }$$

### Continuous maps + Compact Sets

 
**Theorem 16**.


$(X,d_X),(Y,d_Y)$ metric spaces.\
$f: X\to Y$ a continuous map if
$$Z \text{ compact in } X \implies f(Z) \text{ compact in }Y$$

**Corollary 2.44.**\
$(X,d_X),(Y,d_Y)$ metric spaces, $f:X \to Y$ a homeomorphism
$$\implies X \text{ compact } \iff Y \text{ compact }$$

 
**Theorem 17**.


Every continuous map from compact metric space to a metric space is
uniformly continuous.

**Corollary 2.46.** $f:[a,b] \to \mathbb{R}$ continuous $\implies$ $f$
uniformly continuous

 
**Theorem 18**.


$(X,d_X)$ compact, $f:X \to \mathbb{R}$ continuous $\implies f$ bounded
above and below attaining its upper & lower bounds

 
**Theorem 19**.


$f:\mathbb{R}\to \mathbb{R}$ continuous w.r.t Euclidean metrics on
domain and range.\
$\forall\ [a,b]$ we have $f([a,b])$ of the form $[m,M]$ for
$m,M \in \mathbb{R}$

## Completeness

### Complete metric spaces & Banach space

 
**Definition 32**. [**Cauchy Sequence**]


$(X,d)$ a metric $(x_{n})_{n\geq 1}$ sequence in $X$\
Say $(x_{n})_{n\geq 1}$ a [**Cauchy
sequence**] in $(X,d)$ if
$$\forall \epsilon > 0, \exists N_{\epsilon} \in \mathbb{N}\text{ s.t } \forall n,m \geq N_{\epsilon} \text{ we have } d(x_{n},x_{m}) < \epsilon$$

 
**Definition 33**. [**Complete & Banach**]


1.  metric space $(X,d)$ [**complete**] if
    every Cauchy sequence in $X$ converges to a limit in $X$

2.  Normed vector space $(V,||\cdot||)$ a [**Banach
    space**] if $V$ with induced metric
    space $d_{|| ||}$ a complete metric space.

 
**Theorem 20**.


Assume $(f_{n} : [a,b] \to \mathbb{R})_{n\geq 1}$ sequence of continuous
functions converging uniformly to
$f:[a,b] \to \mathbb{R}\implies f:[a,b] \to \mathbb{R}$ continuous

 
**Theorem 21**.


Metric space $(C([a,b]),d_{\infty})$ is complete or equivalently
$(C([a,b]),||\cdot||_{\infty})$ a Banach space

 
**Theorem 22**.


$(X,d)$ a compact metric space $\implies (X,d)$ complete

### Arzelà-Ascoli

 
**Definition 34**. [**Uniformly bounded & Uniformly
equi-continuous**]


Let $\mathcal{C}$ a collection of functions $f:[a,b] \to \mathbb{R}$

1.  Say collection $\mathcal{C}$ [**uniformly
    bounded**] if $\exists M$ s.t
    $\forall f \in \mathcal{C}$ and
    $\forall x \in [a,b] \implies |f(x)| < M$

2.  Say collection $\mathcal{C}$ [**uniformly
    equi-continuous**] if
    $\forall \epsilon > 0, \exists \delta > 0$ s.t
    $\forall f \in \mathcal{C}$ and $\forall x_1,x_2 \in [a,b]$ s.t
    $|x_1-x_2| < \delta$ we have $|f(x_1) - f(x_2)| < \epsilon$

 
**Theorem 23**. [**Arzelà-Ascoli**]


Assume $\mathcal{C}$ collection of continuous functions
$f:[a,b] \to \mathbb{R}$ if $\mathcal{C}$ uniformly bounded and
uniformly equi-continuous $\implies$ every sequence in $\mathcal{C}$ has
convergent subsequence in $(C([a,b],d_{\infty})$

### Fixed point theorem

 
**Definition 35**. [**Contracting**]


$(X_{1},d_{1})$ and $(X_{2},d_{2})$, with $f: X_1 \to X_2$\
Say $f$ [**contracting**] if
$\exists K \in (0,1)$ s.t $\forall a,b \in X$ we have
$$d_{2}(f(a),f(b)) \leq K\cdot d_{1}(a,b)$$ Every contracting map is
continuous.

 
**Definition 36**. [**Fixed point**]


$f:X\to X$ say $x \in X$ a [**fixed point**]
of $f$ if $f(x) = x$

 
**Theorem 24**. [**Banach fixed point theorem**]


$(X,d)$ a non-empty complete metric space.\
$f: X \to X$ a contracting map $\implies f$ has unique fixed point in
$X$

