---
layout: default
title: Analysis 2
parent: Year 2
nav_order: 0
math: mathjax3
---
# Analysis 2 - Concise Notes 1
{: .no_toc }
## MATH50001
{: .no_toc}
**Term 1 Content**

<head>
  <style>
ol.n {list-style-type: none;}
  </style>
</head>
  

<a href="https://arnavs1ngh.github.io/notes/docs/Year2/main/#analysis-2---math50001" style="color:#FF0000;">** PDF** Analysis 2 - Concise Notes - Term 1</a>

<!-- <button class="btn js-toggle-dark-mode">Light Mode</button>

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
}); -->
<!-- </script> -->

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

*Content from MATH40002 assumed to be known.*



# <span style="color: white;">1</span> Differentiation in Higher Dimensions

## <span style="color: white;">1.1</span> Euclidean Spaces

### <span style="color: white;">1.1.1</span> Preliminaries

**Definition** - <span style="color: green;">**Modulus Function**</span>

$$|x| :=
\begin{cases} 
     x, & x\geq 0 \\
     -x, & x \leq 0
\end{cases}
$$

Having the following properties:

1. $\forall x \in \mathbb{R}, \lvert x \rvert \geq 0, \lvert x \rvert = 0 \iff x = 0$ 

2. $\forall x, y \in \mathbb{R}, \lvert xy \rvert = \lvert x \rvert\lvert y \rvert$

3. $\forall x, y \in \mathbb{R}, \lvert x+y \rvert \leq \lvert x \rvert + \lvert y \rvert$ (Triangle inequality)


### <span style="color: white;">1.1.2</span> Euclidean space of dim. n

**Define** - <span style="color: green;">**Euclidean Space of dim. $n, \mathbb{R}^{n}$**</span>

Defined as the set of ordered $n$-tuples $(x^{1},\dots,x^{n})$, s.t $\forall i,\ x^{i} \in \mathbb{R}$
<center>
  $\mathbb{R}^{n} $ a vector space.
</center>

**Define** - <span style="color: green;">**Inner Product** $ < \cdot,\cdot > : \mathbb{R}^{n} \times \mathbb{R}^{n} \to \mathbb{R}$</span> 
  
$$\langle(x^{1},x^{2},\dots,x^{n}),(y^{1},y^{2},\dots,y^{n})\rangle = \sum_{i=1}^n x^{i}y^{i}$$

**Define - Norm/Lengths**, $\mid\mid\cdot\mid\mid: \mathbb{R}^{n} \to \mathbb{R}$
  
$$||x|| = \sqrt{<x,x>}$$ 

Having the following properties:
  
1. $\forall x \in \mathbb{R}^{n}, \lvert\lvert x\rvert\rvert \geq 0, \lvert\lvert x\rvert\rvert \iff x = \vec{0}$
2. $\forall \lambda x \in \mathbb{R}, x\in \mathbb{R}^{n} \lvert\lvert \lambda x\rvert\rvert = \lvert\lambda\rvert\lvert\lvert x\rvert\rvert$
3. $\forall x, y \in \mathbb{R}^{n}, \lvert\lvert x+y\rvert\rvert \leq \lvert\lvert x\rvert\rvert + \lvert\lvert y\rvert\rvert$ *(Triangle inequality)*
  

**Definition - <span style="color: green;">Cauchy-Schwartz Inequality</span>**

$$|\langle x, y \rangle| \leq ||x||\cdot||y||$$

### <span style="color: white;">1.1.3 </span> Convergence of Sequences in Euclidean Spaces
  

**Definition - <span style="color: green;">Sequence in $\mathbb{R}^{n}$</span>**
  
An infinite ordered list, $x_{0}, x_{1},\dots,$ s.t $x_{i} \in \mathbb{R}^{n} \text{ } \forall i$

Denoted $$ (x_{i})_{i\geq 1}$$ or $$(x_{i})_{i\in \mathbb{N}}$$
  
**Definition 1.1 - <span style="color: green;">Convergence</span>**
  
<span style="color: red;">**A seq. $(x_{i}) \in \mathbb{R}^{n}$ converges to $x \in \mathbb{R}^{n}$** </span> if <span style="color: RoyalBlue;">**$\forall \epsilon > 0, \exists N \in \mathbb{N}\text{ s.t } \forall i \geq \mathbb{N}, ||x_{i}-x||<\epsilon$**</span>
  
***Corollary***
  
Sequence $(x_{i}) \in \mathbb{R}^{n}$ converges to
$x \in \mathbb{R}^{n} \iff$

  <center>
    $$\textrm{For } x_{i} = (x_{i}^{1},\dots,x_{i}^{n}) \textrm{ and } x = (x^{1},\dots,x^{n})$$

    $$x_{i} \to x \iff \forall k \text{ } x_{i}^{k} \to x^{k} \text{ as } i \to \infty$$
  </center>

## <span style="color: white;">1.2</span> Continuity

### <span style="color: white;">1.2.1</span> Open sets in Euclidean Spaces

**Definition - <span style="color: green;">Open Ball</span>**
  
Open ball of radius $r$ is
  
<center>
$$B_{r}(x) = \{y \in \mathbb{R}^{n} : ||x-y||<r\}$$
</center>
  
**Definition 1.2 - <span style="color: green;">Open Sets</span>**
  
A set $U \subseteq \mathbb{R}^{n}$ is called <span style="color: green;">open</span> if

  <center>
  $\forall x \in U, \exists r > 0$ such that $B_{r}(x) \subseteq U$**
  </center>

### <span style="color: white;">1.2.2</span> Continuity at a point/on an open set

**Definition 1.3 - <span style="color: green;">Continuity at a point</span>**
  
Let $A\subset\mathbb{R}^{n}$ an open set, with $f: A \to R^{n}$ <span style="color: red;">$f$ continuous at $p \in A$</span> if 
  <center>
<span style="color: RoyalBlue;">  
$$\forall \epsilon > 0, \exists \delta > 0 \text{ s.t } ||x-p|| < \delta \implies ||f(x)-f(p)|| < \epsilon$$
</span>
   </center>
  
$f$ is (pointwise) continuous on $A\subseteq \mathbb{R}^{n} \iff$ continuous $\forall p \in A$, we write $f$ is continuous.
  
For small enough $\delta$, we have $f(B_{\delta}(p)) \subseteq B_{\epsilon}(f(p))$\
  
**Theorem 1.2 - Composition of continuous functions**\
Let $A \subseteq \mathbb{R}^{n}$ open, $B \subseteq \mathbb{R}^{m}$ open and suppose $f: A \to B$ continuous at $p\in A$, and $g: B \to \mathbb{R}^{l}$ continuous at $f(p)$

  <center>Then $g \circ f: A \to \mathbb{R}^{l}$ continuous at p</center>

**Definition 1.4 - <span style="color: green;">Limit of a function at a point</span>**

$A \subseteq \mathbb{R}^{n}$ an open set. $f$ a function\
$f: A \to \mathbb{R}^{m}$, with $p \in A$ and $q \in \mathbb{R}^{m}$
  
Say $\lim_{x\to p}f(x) = q$ if  
  
$\forall \epsilon > 0, \exists \delta > 0 \text{ s.t } \forall x \in A \text{ with } 0 < \lvert\lvert x-p\rvert\rvert <\delta \text{ we have } \lvert\lvert f(x) - p\rvert\rvert < \epsilon$
                                                                                                                                                                                                                                                                                          <center> $f$ continuous at $p \iff \lim_{x\to p}f(x) = q$ </center>

**Theorem 1.3 - Algebra of Limits**\
Suppose $A \subseteq \mathbb{R}^{n}$ open, with $p \in A$ and
$f,g: A \to \mathbb{R}^{n}$

<center>
  <span style="color: RoyalBlue;">
$\lim_{x\to p}f(x) = F $ and $\lim_{x\to p}g(x) = G$
  </span>
  </center>
Then:
  

1.  <span style="color: red;">**$\lim_{x\to p}(f(x) + g(x)) = F + G$**</span>

2.  <span style="color: red;">**$\lim_{x\to p}(f(x)g(x)) = FG$**</span>

3.  <span style="color: red;">If $G\neq 0$ then $\lim_{x\to p}\frac{f(x)}{g(x)} = \frac{F}{G}$</span>
  

## <span style="color: white;">1.3</span> Derivative of a map of Euclidean Spaces

### <span style="color: white;">1.3.1</span> Derivative of a linear map

**Lemma 1.5**\
*The map $f:(a,b) \to \mathbb{R}$ differentiable at $p \in (a,b) \iff \exists$ map of the form $A_{\lambda}(x) = \lambda(x-p) + f(p)$ for some $\lambda \in \mathbb{R}$ s.t*
  
  $$\lim_{x\to p}\frac{|f(x) - A_{\lambda}(x)|}{|x-p|} = 0$$

**Notation**
  
  <center>
    $h[v]$ for $h$ a linear map, $v$ a vector<br>
    
    $h(v)$, $h$ a map, $v$ a point in domain of $h$<br>
    
    $L(\mathbb{R}^{n};\mathbb{R}^{m})$ - Set of linear maps from $\mathbb{R}^{n} \to \mathbb{R}^{m}$
  </center>

**Definition 1.5** - <span style="color: green;">**Derivative in higher dimension**</span>
  
Suppose $\Omega \subset \mathbb{R}^{n}$ open. <span style="color: red;"> The map $f:\Omega \to \mathbb{R}^{m}$ differentiable at $p \in \Omega$ </span><span style="color: RoyalBlue;">if $\exists$ a linear map $\Lambda \in L(\mathbb{R}^{n};R^{m})$**] such that </span>
  
  <center>
    <span style="color: RoyalBlue;">$$\lim_{x\to p}\frac{||f(x) - (\Lambda[x-p] + f(p))}{||x-p||} = 0$$</span>
  </center>
  We write
  <center>
    $$Df(p) := \Lambda$$ 
  </center>
Calling $Df(p)$ the derivative of $f$ at $p$\
  $\Lambda$ a $m\times n$ matrix called the <span style="color: green;">**Jacobian**</span>
  

**Lemma 1.6 - Differentiable then continuous**\
$\Omega \subset \mathbb{R}^{n}$ open  
$f:\Omega \to \mathbb{R}^{m}$ differentiable at $p\in \Omega \implies f$ continuous at $p$
  
  
**Theorem 1.7 - Uniqueness of Derivative**\
The derivative, <span style="color: RoyalBlue;">**if it exists**</span>, <span style="color: red;">**is unique**<span style="color: white;">

### <span style="color: white;">1.3.2</span> Chain Rule

**Chain rule in $\mathbb{R}$**\
$f,g: \mathbb{R}\to \mathbb{R}, g$ differentiable at $p$, $f$ differentiable at $g(p)$. 

Then $f \circ g$ differentiable at $p$ with
  
  <center> 
    $$(f\circ g)'(p) = f'(g(p))g'(p)$$
  </center>
  
**Theorem 1.8 - Chain rule in higher dim.**\
  
$\Omega \subset \mathbb{R}^{n}$ open, $\Omega' \subset \mathbb{R}^{m}$
open\
With $g:\Omega \to \Omega'$ differentiable at $p \in \Omega$,
$f:\Omega' \to \mathbb{R}^{l}$ differentiable at $g(p) \in \Omega'$\
Then $h = f \circ g: \Omega \to \mathbb{R}^{l}$, differentiable at $p$, s.t 
  
 $$Dh(p) = D(f(g(p))\circ Dg(p)$$

## <span style="color: white;">1.4</span> Directional Derivatives

### <span style="color: white;">1.4.1</span> Rates of change and Partial Derivatives

**Definition** - <span style="color: green;">**Directional Derivative**</span>
  
  The <span style="color: green;">**directional derivative**</span> of $f$ at $p$ in the direction $v$ is
  <center>
    $$\frac{\partial f}{\partial v}(p) := \lim_{t\to 0}\frac{1}{t}[f(p+vt)-f(p)] = Df(p)[v]$$
  </center>
  
**Definition** - <span style="color: green;">**Partial derivatives**</span>
  
We can find any directional derivative at $p$, given we know the partial derivatives of $f$
  
  $$D_{i}f(p) = \frac{\partial f}{\partial e_{i}}(p)$$
  
In $\mathbb{R}^{3}$ we have,
  
  $$Df(p)[v] = 
\begin{pmatrix}
\ D_{1}f(p)\quad  D_{2}f(p)\quad D_{3}f(p)\quad
\end{pmatrix}
\begin{pmatrix}
v^{1}\\
v^{2} \\
v^{3} 
\end{pmatrix}$$

**Definition** - <span style="color: green;">**Gradient**</span>
  
*Gradient of $f$ at $p$*
  <center>
  $$\nabla f(p) = 
\begin{pmatrix}
D_{1}f(p)\\
D_{2}f(p) \\
D_{3}f(p)
\end{pmatrix}\qquad
Df(p) = (\nabla f(p))^{t}$$
  </center>

**Theorem 1.9 - Jacobian**\
Suppose $\Omega \subset \mathbb{R}^{n}$ open and $f: \Omega \to \mathbb{R}^{m}$ of the form 
  <center<
  $$f(x) = 
  \begin{pmatrix}
  f^{1}(x),f^{2}(x),\dots,f^{m}(x)
  \end{pmatrix}$$ 
  </center>
  
  <span style="color: RoyalBlue;">**If $f$ differentiable for some $p \in \Omega$** </span> Then <span style="color: red;">**Jacobian of $f$ at $p$ is:**</span>
  
  <center>
    $$Df(p) = 
    \begin{pmatrix}
    D_{1}f^{1}(p) & \dots & D_{n}f^{1}(p)\\
    \vdots & \ddots & \vdots\\
    D_{1}f^{m}(p) & \dots & D_{n}f^{m}(p)
    \end{pmatrix}$$
  </center>

### <span style="color: white;">1.4.2</span> Relation between partial derivatives and differentiability

**Theorem 1.12**\
Let $\Omega \subset \mathbb{R}^{n}$ open, $f:\Omega\to \mathbb{R}$. <span style="color: RoyalBlue;">**Suppose the partial derivatives:**</span>
  <center>
    $$D_{i}f(x) := \lim_{t\to 0}\frac{f(x+te_{i}-f(x)}{t}$$
  </center>
  <span style="color: RoyalBlue;">**exist $\forall x \in \Omega$, with each map $x \mapsto D_{i}f(x)$ continuous at $p, \forall i$**</span>$\implies$ <span style="color: red;">**$f$ is differentiable at $p$**</span>

## <span style="color: white;">1.5</span> Higher Derivatives

### <span style="color: white;">1.5.1</span> Higher derivatives as linear maps

Can think of the differential of $f$, $Df(p)$ as a map
  <center>
$$Df: \Omega \to L(R^{n};R^{m}) = \Omega \to \mathbb{R}^{mn}$$
  
$$\quad p \mapsto Df(p)$$ 
  </center>
    
  <span style="color: RoyalBlue;">**if map $Df$ is continuous**</span> $\implies f:\Omega \to \mathbb{R}$ is <span style="color: green;">**continuously differentiable**</span>
  
  
**Definition** - <span style="color: green;">**Higher derivative**</span>
  
If $Df: \Omega \to \mathbb{R}^{mn}$ differentiable at $p$, denote derivative of $Df$ as $DDf(p): \mathbb{R}^{n} \to \mathbb{R}^{nm}$
  <center>
$$DDf(p) \in L(\mathbb{R}^{n};\mathbb{R}^{nm}) = L(\mathbb{R}^{n};L(\mathbb{R}^{n};\mathbb{R}^{m}))$$
  </center>
Where $DDf(p)$ is a linear map$\mathcal{L} \in L(\mathbb{R}^{n};L(\mathbb{R}^{n};\mathbb{R}^{m}))$, satisfying:
  <center>
$$\lim_{x\to p}\frac{||Df(x) - Df(p) - \mathcal{L}[x-p]||}{||x-p||} = 0$$
  </center>
$DDf(p)$ takes an $n$-vector to a $m\times n$ matrix\
  
**Definition** - <span style="color: green;">**Continuously differentiable**</span>
  
<span style="color: green;">**$f:\Omega \to \mathbb{R}^{m}$ is $k$-times dfferentiable with all continuous derivatives**</span> $\implies$ <span style="color: red;">$f$ is $k$-times continuously differentiable</span>

**Testing for $k$-times differentiability**\
For $f = \begin{pmatrix}
f^{1}(x),f^{2}(x),\dots,f^{m}(x)
\end{pmatrix}$\
If $f$ differentiable at $p\in \Omega \implies$ we have partial
derivatives $D_{i}f^{j}: \Omega \to \mathbb{R}$.\
If $Df$ differentiable, then $2^{\text{nd}}$ partial derivatives exist
  <center>
    $$D_{k}D_{i}f^{j}(p) := \lim_{t\to 0}\frac{D_{i}f^{j}(p+te_{k})-D_{i}f^{j}(p)}{t}$$
  </center>
Easy to check these exist and are continuous $\implies$ $k$-times differentiability at $p$

### <span style="color: white;">1.5.2</span> Symmetry of mixed partial derivatives

**Theorem 1.13 - Schwartz' Theorem**\
Suppose $\Omega \subset \mathbb{R}^{n}$ open and $f:\Omega \to \mathbb{R}$ differentiable $\forall p \in \Omega$\
Suppose also, for $i,j \in \{1,\dots,n\}, 2^{\text{nd}}$ partial derivatives $D_{i}D_{j}f$ and $D_{j}D_{i}f$ exist and are continuous $\forall p \in \Omega$
  <center>
  $$\forall p \in \Omega, D_{i}D_{j}f(p) = D_{j}D_{i}f(p)$$
  </center>
  
**Definition** - <span style="color: green;">**Hessian**</span>
  
The matrix of $2^{\text{nd}}$ partial derivatives at the point $p$
  <center>
$$\text{Hess } f(p) = [D_{i}D_{j}f(p)]_{i,j =1,\dots,n}$$ 
  </center>
Schwartz' Theorem says Hess $f(p$ is a symmetric matrix

### <span style="color: white;">1.5.3</span> Taylor's Theorem

**Definition** - <span style="color: green;">**Multi-inidices**</span>
  
Multi-index $\alpha \in (\mathbb{N})^{n}, \alpha = \begin{pmatrix}
\alpha_{1},\dots,\alpha_{n}
\end{pmatrix}$
  
We define
  <span style="color: green;">$|a| = \sum_{i=1}^{n}\alpha_{i}$</span> and
  <center>
  $$D^{\alpha}f := (D_{1})^{\alpha_{1}}(D_{2})^{\alpha_{2}}\dots(D_{n})^{\alpha_{n}}f,$$
  </center>
And for a vector $h = \begin{pmatrix}
h_{1},\dots,h_{n}
\end{pmatrix}$
  <center>
  $$h^{\alpha} := (h^{1})^{\alpha_{1}}(h^{2})^{\alpha_{2}}\dots(h^{n})^{\alpha_{n}}$$
  </center>
Also
  <center>
  $$\alpha ! := \alpha_{1}!\alpha_{2}!\dots\alpha_{n}!$$
  </center>
  
***helpful examples***

<center>
  $D^{(0,3,0)}f(p) = D_{2}^{3}f(p)$<br>
  
  $D^{(1,0,1)}f(p) = D_{1}D_{3}f(p)$<br>
  
  $(x,y,z)^{(2,1,5)} = x^{2}y^{1}z^{5}$

</center>

**Theorem 1.14 - Taylor's Theorem in higher dim.**\
Suppose $p \in \mathbb{R}^{n}$ and $f: B_{r}(p) \to \mathbb{R}$ a $k$-times continuously differentiable $\forall q \in B_{r}(p)$, for some $k \geq 1 \in \mathbb{N}$\
  
Then $\forall h \in \mathbb{R}^{n}$ with $||h|| < r$ We have
 <center>
$$f(p+h) = \sum_{|\alpha| \leq k-1}\frac{h^{\alpha}}{\alpha!}D^{\alpha}f(p) + R_{k}(p,h)$$
  </center>
Sum over all $\alpha = \begin{pmatrix}
\alpha_{1},\dots,\alpha_{n}
\end{pmatrix}$\
with $|\alpha| \leq k-1$ and remainder term
  <center>
$$R_{k}(p,h) = \sum_{|\alpha| = k}\frac{h^{\alpha}}{\alpha!}D^{a}f(x)$$
  </center>
for some $x$ s.t $0 < ||x-p||< ||h||$ <br>
Evidently
  <center>
  $$\lim_{h\to 0}\frac{|R_{k}(p,h)|}{||h||^{k-1}} = 0$$
  </center>

## <span style="color: white;">1.6</span> Inverse & Implicit Function Theorem

### <span style="color: white;">1.6.1</span> Inverse Function Theorem

**Theorem 1.15** - (Inverse Function Theorem)
  
Let $\Omega$ an open set in $\mathbb{R}^{n}$, $f: \Omega \to \mathbb{R}^{n}$ continuously differentiable on $\Omega$, $\exists q \in \Omega$ s.t $Df(q)$ invertible\
Then $\exists$ open sets $U \subset \Omega$ and $V \subset \mathbb{R}^{n}, q \in U, f(q) \in V$ s.t

1.  $f:U \to V$, a bijection

2.  $f^{-1}: V \to U$, continuously differentiable

3.  $\forall y \in V$, $$Df^{-1}(y) = [Df(f^{-1}(y))]^{-1}$$

### <span style="color: white;">1.6.2</span> Implicit Function Theorem

**Theorem 1.16 - *(Implicit Function Theorem - Simple version)***\
$\Omega \subset \mathbb{R}^{2}$ open\
$F: \Omega \to \mathbb{R}$ continuously differentiable and
$\exists (x',y') \in \Omega$ s.t

1.  $F(x',y') = 0$, and

2.  $D_{2}F(x',y') \neq 0$

$\implies \exists$ open sets $A, B \subset \mathbb{R}$ with
$x' \in A, y' \in B$ with a map $f:A \to B$ s.t
  <center>
$(x,y) \in A \times B$  satisfies $F(x,y) = 0 \iff y = f(x)$ for some $x \in A$
  </center>
with $f:A \to B$ continuously differentiable.
  
**Definition - <span style="color: green;">$C^{1}-$diffeomorphism**</span>\
$\Omega,\Omega' \subset \mathbb{R}^{n}$ open.\
Say $f:\Omega \to \Omega'$ a $C^{1}$-diffeormorphism, if
$f:\Omega \to \Omega'$ a and $\forall x \in \Omega, Df(x)$
**invertible**\
$\mathcal{D}$ the set of all $C^{1}-$diffeomorphisms from
$\Omega \to \Omega$, a group under group law; composition.

### <span style="color: white;">1.6.4</span> Implicit Function Theorem - General Form

**Theorem 1.17 - *(Implicit Function Theorem)***\
$\Omega \subset \mathbb{R}^{n}, \Omega' \subset \mathbb{R}^{m}$ open
sets\
$F: \Omega \times \Omega' \to \mathbb{R}^{m}$ continuously
differentiable on $\Omega \times \Omega'$ and sps
$\exists (a,b) \in \Omega \times \Omega'$ s.t

1.  $f(p) = 0$ and,

2.  $m \times n$ matrix
  <center>
  $$(D_{n+j}f^{i}(p)), \qquad 1 \leq i, j\leq m$$
  </center>
  invertible

$\implies \exists$ open sets $A \subset \Omega, B \subset \Omega'$ with $a \in A, b \in B$ with a map $g:A \to B$ s.t
  <center>
$g(x,y) = 0 $  for some  $(x,y) \in A \times B \iff y = g(x)$ for some  $x \in A$
  </center>
   
with $g:A \to B$ continuously differentiable.

# <span style="color: white;">2</span> Metric and Topological Spaces
  
  

## <span style="color: white;">2.1</span> Metric Spaces

### <span style="color: white;">2.1.1</span> Motivation + Definition

**Definition 2.1** - <span style="color: green;">**Metric**</span>
  
$X$ an arbitrary set\
Metric a function $d: X \times X \to \mathbb{R}$ satisfying:

1.  $\forall x,y \in X;\ d(x,y) \geq 0, d(x,y) = 0 \iff x = y$
    ***(positivity)***

2.  $\forall x,y \in X;\ d(x,y) = d(y,x)$ ***(symmetry)***

3.  $\forall x,y,z \in X d(x,y) \leq d(x,z) + d(z,y)$ ***(triangle
    inequality)***

**Definition 2.2** - <span style="color: green;">**Metric space**</span>
  
Pair of a set and metric; $M = (X,d)$\
Call elements of $X$ points,with $d(x,y)$ distance between $x,y$ w.r.t $d$
  
  
**Definition**
  <center>
  $C([a,b]) = \{f:[a,b] \to \mathbb{R}| f:[a,b] \to \mathbb{R}$ continuous $\}$
  </center>
  
### <span style="color: white;">2.1.2</span> Examples of metrics

-   $d_{2}(x,y) = \lvert\lvert x-y\rvert\rvert$; Euclidean metric on $\mathbb{R}^{n}$

-   $d_{\text{disc}}(x,y) = \begin{cases} 0, & x=y\\ 1, & x \not = y \end{cases}$
    
-   $d_{\infty}(x,y) = \sup_{k\geq 1}\lvert x^{k} - y^{k}\rvert$

-   $d_{\infty}(f,g) =  \text{max}_{a\leq t\leq b}\lvert f(t) - g(t)\rvert $ where $f,g \in C([a,b])$ (supremum/uniform metric)***

 
**Definition 2.3**. <span style="color: green;">**Induced metrics**</span>

$(X,d)$ a metric space\
$Y \subseteq X$, define $ d\rvert_{Y}: Y \times Y \to \mathbb{R}$ as $d|_{Y}(x,y) = d(x,y)\ \forall x,y \in Y$

 
**Definition 2.3**. <span style="color: green;">**Metric Subspace**</span>

Say $(Y,d\rvert_{Y})$ a metric subspace of $(X,d)$

 
**Definition 2.4**. <span style="color: green;">**Product metric space**</span>


$(X_{1},d_{1})$ and $(X_{2},d_{2})$ metric spaces.\
define metric using
$d_{1},d_{2}$ $d: (X_{1} \times X_{2}) \times (X_{1} \times X_{2}) \to \mathbb{R}$.\
$(X_{1} \times X_{2}, d)$ a product metric space.

### <span style="color: white;">2.1.3</span> Normed Vector Spaces

 
**Definition 2.5**. <span style="color: green;">**Norm in Metric Spaces**</span>

$V$ a vector space on $\mathbb{R}$. Say $||\cdot||: V \to \mathbb{R}$ a
[**norm**] on $V$ if

1.  $\forall v \in V,\ \lvert\lvert v\rvert\rvert \geq 0$ and $\lvert\lvert v\rvert\rvert = 0 \iff v = 0$

2.  $\forall v \in V, \forall \lambda \in \mathbb{R},\ \lvert\lvert\lambda v\rvert\rvert = \lvert\lambda\rvert\cdot\lvert\lvert v\rvert\rvert$

3.  $\forall u,v \in V,\ \lvert\lvert u+v\rvert\rvert \leq \lvert\lvert u\rvert\rvert + \lvert\lvert v\rvert\rvert$

**Definition** - <span style="color: green;">**Normed Vector Space**</span>

A pair of a vector space $(V, ||\cdot||)$\
note $||\cdot||$ is a metric on $V \implies$ normed vector space a
metric space.

### <span style="color: white;">2.1.4</span> Open sets in metric spaces

 
**Definition 2.6**. <span style="color: green;">**Open ball in metric spaces**</span>

$(X,d)$, with $x \in X, \epsilon \in \mathbb{R}; \epsilon > 0$\
  <center>
Ball radius $ \epsilon;\ B_{\epsilon}(x) = \{ x' \in X | d(x,x') < \epsilon\}$
 </center>
***notation;*** $B_{\epsilon}(x,X,d)$
 
**Definition 2.7**. <span style="color: green;">**Open set in metric space**</span>

$(X,d)$ a metric space. $U \subseteq X$ open in $(X,d)$ if:
    <center>
$$\forall u \in U,\ \exists \delta > 0 \in \mathbb{R}\text{ s.t } B_{\delta}(u) \subset U$$
    </center>
 
**Definition 2.8**. <span style="color: green;">**Topologically equivalent**</span>


$d_{1},d_{2}$ metrics on a set $X$ **topologically equivalent** if:
$$\forall\ U \subseteq X,\ U \text{ open in } (X,d_{1}) \iff U \text{ open in }  (X,d_{2})$$

### <span style="color: white;">2.1.5</span> Convergence in Metric Spaces

 
**Definition 2.9**. <span style="color: green;">**Convergence in Metric Spaces**<span style="color: green;">

$(X,d)$ a metric space. $(x_{n})_{n\geq 1}$ a sequence in $X$.

Say $(x_{n}) \to x \in (X,d)$ if
    <center>
$$\forall\ \epsilon > 0, \exists N \in \mathbb{N}\text{ s.t } \forall\ n \geq N, d(x,x_{n})< \epsilon$$
   </center>
***Lemma 2.7.*** - if $(x_n)$ converges in $(X,d)$ $\implies$ limit is unique\
      
***Corollary*** - $d_{1},d_{2}$ topologically equivalent $\iff (x_n)$
converges in $(X,d_1)$ and $(X,d_2)$

### <span style="color: white;">2.1.6</span> Closed sets in metric spaces

 
**Definition 9**. <span style="color: green;">**Closed set in Metric Spaces**</span>

$(X,d)$ a metric space. $V \subseteq X$ a set.\
$V$ **closed** in $(X,d)$ if $\forall\ (x_n) \in V$ s.t $(x_n) \to x$ convergent in $(X,d) \implies x \in V$

 
**Theorem 2.9.**
      
$(X,d)$ a metric space. $V \subseteq X$\
      <center>
$V$ closed in  $(X,d) \iff X\backslash V$  open in $(X,d)$
      </center>
      
***Lemma 2.10***

1.  Intersection of closed sets in $(X,d)$ is a closed set in $(X,d)$

2.  Finite union of closed sets in $(X,d)$ a closed set in $(X,d)$

### Interior, isolated, limit, and boundary points in metric spaces

**Definition 2.11. - 2.12.**

$(X,d)$ a metric space, $V \subset X,\ x \in X$

1.  $x$ an <span style="color: green;">**interior/inner point**</span> of $V$ if 
      <center>
      $$\exists \delta > 0,\ \text{ s.t } B_{\delta}(x) \subset V$$
      </center>
      
      1.  <span style="color: green;">**Interior of $V$; $V^{\circ}$**</span> - $\{v \in V : v \text{ an interior point of } V\}$


2.  $x$ a <span style="color: green;">**limit/accumulation point**</span> of $V$ if
      <center>
    $$\forall \delta > 0, (B_{\delta}(x) \cap V)\backslash\{x\} \neq \emptyset$$
      </center>
    
    ***Note:** not all limit points of $V$ are in $V$*

    1.  <span style="color: green;">**Closure of $V$; $\bar{V}$**</span> - $V \cup \{v \text{ a limit point of } V\}$


3.  $x$ a <span style="color: green;">**boundary point of $V$**</span> if
      <center>
    $$\forall \delta > 0, B_{\delta} \cap V \neq \emptyset \text{ and } B_{\delta}(x)\backslash V \neq \emptyset$$
      </center>
      
    1.  **<span style="color: green;">Boundary of $V$; $\partial V$ -</span>** $\{v \in X : v \text{ a boundary point of } V\}$

4.  $x$ an <span style="color: green;">**isolated point**</span> of $V$ if
      <center>
    $$\exists \delta > 0, \text{ s.t } V \cap B_{\delta}(x) = \{x\}$$
      </center>

***Lemma 2.11*** 
      
$(X,d)$ a metric space, $V \subseteq X$\
$x \in X$ a limit point of $V \iff \exists$ sequence in $V \backslash \{ x \}$ converging to $x$.

 
**Definition 2.13**. <span style="color: green;">**Dense and Seperable subsets**</span>

$(X,d)$ a metric space

-   $V \subseteq X$ **dense** in $X$ if $\bar{V} = X$

-   $(X,d)$ seperable if, $\exists$ dense countable subset of $X$

### <span style="color: white;">2.1.8</span> Continuous maps of metric spaces
 
**Definition 2.14**. <span style="color: green;">**Continuity in metric spaces**</span>

$(X,d_{X}), (Y,d_{Y})$ metric spaces.\
$f: X \to Y$ a map

1.  $f$ <span style="color: green;">**continuous**</span> at $x \in X$ if
    $$\forall \epsilon > 0, \exists \delta > 0 \text{ s.t } \forall x' \in X \text{ s.t } d_{X}(x',x) < \delta, d_{Y}(f(x),f(x')) < \epsilon$$

2.  $f: X \to Y$ continuous if $f$ continuous $\forall x \in X$

3.  $f: X \to Y$ uniformly continuous if $f$ continuous
    $\forall x \in X$ with $\delta = \delta(\epsilon)$ not depending on
    $x$

 
**Theorem 2.12**.


$(A_{1},d_1),(A_2,d_2)$ metric spaces\
$f: A_1 \to A_2$ continuous $\iff$ pre-image of any open set in $A_2$ is
an open set in $A_1$\
$f: A_1 \to A_2$ continuous $\iff$ pre-image of any closed set in $A_2$
is a closed set in $A_1$

 
**Theorem 2.13**.

$(X,d_X), (Y,d_Y)$ metric spaces\
$f: X \to Y$ a map;
$$f \text{ continuous at } x \in X \iff \text{ for any sequence } (x_n) \to x;\ f(x_n) \to f(x) \text{ in } (Y,d_Y)$$

 
**Definition 2.15**. <span style="color: green;">**Homeomorphism**</span>

$(X_1,d_1),(X_2,d_2)$ metric spaces.

1.  $f: X_1 \to X_2$ a <span style="color: green;">**homeomorphism**</span> if

    -   $f: X_1 \to X_2$ a bijection

    -   $f: X_1 \to X_2$ and $f^{-1}:X_2 \to X_1$ continuous

2.  Say $(X_1,d_1),(X_2,d_2)$ <span style="color: green;">**homeomorphic**</span> if $\exists$ homeomorphism from $X_1$ to $X_2$

 
**Definition 2.16**.

$(X,d_X),(Y,d_Y)$ metric spaces with $f:X\to Y$\

1.  $f$ is <span style="color: green;">**Lipschitz**</span> if $\exists$ constant $M > 0$ s.t $\forall x_1,x_2 \in X, d_Y(f(x_1),f(x_2)) \leq M \cdot d_X(x_1,x_2)$

2.  $f$ is <span style="color: green;">**bi-Lipschitz**</span> if $\exists$ constants $M_1,M_2 > 0$ s.t $\forall x_1,x_2 \in X$
    <center>
      $$M_2 \cdot d_X(x_1,x_2) \leq d_Y(f(x_1),f(x_2)) \leq M_1 \cdot d_X(x_1,x_2)$$
    </center>  
    ***Corollary;** any bi-Lipschitz map is injective*

3.  $f$ an <span style="color: green;">**isometry/distance preserving**</span> if $\forall x_1,x_2 \in X;$ 
      <center>
      $$d_Y(f(x_1),f(x_2)) = d_X(x_1,x_2)$$
      </center>
      
## <span style="color: white;">2.2</span> Topological Spaces

### <span style="color: white;">2.2.2</span> Topology on a set

      
**Definition 2.15.**. <span style="color: green;">**Topology**</span>


$A$ an arbitrary set. $\tau$ a collection of subsets of $A$\
$\tau$ a <span style="color: green;">**topology**</span> on $A$ if:

1.  $\emptyset \in \tau$ and $A \in \tau$

2.  $G_{\alpha} \in \tau$ for $\alpha$ in a (finite) set $I$
    $\implies \bigcup_{\alpha \in I}G_{\alpha} \in \tau$

3.  $G_{1},G_{2},\dots,G_{m} \in \tau\implies \bigcap_{i=1}^{m}G_{i} \in \tau$

A <span style="color: green;">**topological space**</span>; $(A,\tau)$ a pair of a set $A$ and topology $\tau$ on $A$. Each element in $\tau$ an open
set in $(A,\tau)$\
$U$ a neighbourhood of $a$ if $U \in \tau$ and $a \in U$

**Example 2.25.**. *Some Topologies*

1.  **Coarse topology -** $A$ arbitrary set, $\tau= \{\emptyset, A\}$

2.  **Induced topology -** $(X,d)$ a metric space, with $\tau$ the
    collection of all open sets in $(X,d)$

3.  **Order Topology -** $A = \mathbb{R}$ with $\tau$ collection of subsets of $\mathbb{R}$ of form $(a,+\infty),\ a \in \mathbb{R}\cup \{-\infty,+\infty\}, (\+infty,+\infty) := \emptyset$

4.  **Discrete Topology** - $A$ arbitrary, $\tau= \mathcal{P}(A)$

5.  **Product topology** -

**Definition.** <span style="color: green;">**Metrisable topological space**</span>
      
Say topological space $(X,\tau)$ <span style="color: green;">**metrisable**</span> if $\exists$ metric on $X$ which induces a topology $\tau$.
      
**Definition.** <span style="color: green;">**Induced and Subspace topology**</span>
      
$(X,\tau)$ a topological space. $Y \subset X$
      <center>
$$\tau_{Y} = \{U \cap Y | U \in \tau\}$$
      </center>

$\tau_{Y}$ the <span style="color: green;">**induced topology**</span> on $Y$ from $(X,\tau)$\
$(Y,\tau_{Y})$ has the <span style="color: green;">**subspace topology**</span> induced from $(X,\tau)$

      
**Definition 2.18**. <span style="color: green;">**Stronger topology**</span>

$A$ a set, with $\tau_1,\tau_2$\
Say $\tau_1$ stronger (or finer) than $\tau_2$ if
$\tau_2 \subset \tau_1$

***Lemma 2.14.***\
$(A,\tau)$\
A set $G \subset A$ open $\iff \forall\ x \in G,\ \exists$ neighbourhood
of $x$ contained in $G$

 
**Definition 2.19**. <span style="color: green;">**Interior in Topological space**</span>

$(A,\tau)$ a topological space. $\Omega \subseteq A$\
$z \in \Omega$ an interior point of $\Omega$ if
      <center>
$$\exists U \in \tau\text{ s.t } z \in U \text{ and } U \subset \Omega$$
      </center>
<span style="color: green;">**interior of $\Omega; \Omega^{\circ}$</span> = $ \{ z \in \Omega | z $ an interior point of $\Omega\} $
      
*Properties of interior*

-   $S \subset T \implies S^{\circ} \subset T^{\circ}$

-   $S$ open in $A \iff S = S^{\circ}$

-   $S^{\circ}$ largest open set contained in $S$

### <span style="color: white;">2.2.3</span> Convergence, and Hausdorff property

 
**Definition 2.20**. <span style="color: green;">**Convergence in Topological Spaces**</span>

$(A,\tau)$ a topological space. $(x_n)_{n\geq1}$ a sequence in $A$\
$(x_n)$ <span style="color: green;">**converges**</span> in $(A,\tau)$ if
      <center>
$$\exists x \in A \text{ s.t } \forall\ G \in \tau\text{ with } x \in G,\ \exists N \in \mathbb{N}, \text{ s.t } \forall n \geq N, x_n \in G$$
      </center>

**Definition 2.21**. <span style="color: green;">**Hausdorff**</span>

$(A,\tau)$ called <span style="color: green;">**Hausdorff**</span> if:
$$\forall x,y \in A\ x \neq y,\ \exists \text{ open set } U,V \text{ s.t } x \in U, y \in V \text{ and } U \cap V = \emptyset$$
Say $U$ and $V$ seperate $x$ and $y$

 
**Theorem 2.14.**

$(A,\tau)$ a Hausdorff topological space. $(x_n)$ a sequence in $A$.\
if $(x_n)$ convergent in $(A,\tau) \implies$ limit is unique.

### <span style="color: white;">2.2.4</span> Closed sets in topological spaces

 
**Definition 2.22**. <span style="color: green;">**Closed set in Topological space**</span>

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

 
**Definition 2.23**. <span style="color: green;">**Limit/Accumulation point in Topological Spaces**</span>

$(A,\tau),$ a topological space, $S\subseteq A$\
$x \in A$ a <span style="color: green;">**limit/accumulation point**</span> of $S$ if
      <center>
$$\forall\ U \text{ a neighbourhood of } x,\ (S \cap U)\backslash\{x\} \neq \emptyset$$
      </center>
$x$ not necessarily in $S$\
<span style="color: green;">**Closure of $S, \bar{S}$**</span>$= S \cup \{ x \in A | x \text{ a limit point of } S\}$

***Lemma***\
$S$ closed in $(A,\tau) \iff S = \bar{S}$

### <span style="color: white;">2.2.5</span> Continuous maps on topological spaces

 
**Definition 2.24**. <span style="color: green;">**Continuity in topological space**</span>

$(X,\tau_X),(Y,\tau_Y)$ with $f: X \to Y$\
$f$ continuous on $X$ if:
      <center>
$\forall$ open sets  $U \in Y,\ f^{-1}(U) \text{ open in } X$$
      </center>
 
**Theorem 2.20**.


$(X,\tau_X),(Y,\tau_Y)$ with $f: X \to Y$\
$f$ continuous $\iff$ pre-image of closed set in $Y$ is closed in $X$

 
**Theorem 2.21**.


$(X,\tau_X),(Y,\tau_Y),(Z,\tau_Z)$\
$f: X \to Y, g:Y\to Z$ continuous $\implies g \circ f : X \to Z$
continuous

 
**Definition 2.25**. <span style="color: green;">**Homeomorphisms in Topological space**</span>


$f: X \to Y$ a homeomorphism is $f: X \to Y$ bijective with $f$ and
$f^{-1}$ continuous

 
**Definition 2.25**. <span style="color: green;">**Topologically equivalent in Topological space**</span>

$(X,\tau_X),(Y,\tau_Y)$ **topologically equivalent/homeomorphic** if $\exists$ homeomorphism from $X \to Y$

## <span style="color: white;">2.3</span> Connectedness

### <span style="color: white;">2.3.1</span> Connected sets

 
**Definition 2.26**. <span style="color: green;">**Disconnected sets**</span>

For $(X,d)$ a metric space, consider $T \subseteq X$. $T$
<span style="color: green;">**disconnected**</span> ,if $\exists$ open sets $U,V \in X$ s.t:

1.  $U \cap V = \emptyset$

2.  $T \subseteq U \cup V$

3.  $T \cap U \neq \emptyset$ and $T \cap V \neq \emptyset$

Set connected if not disconnected. i.e for any 2 of the properties that hold from above the 3rd cannot.

**Lemma 2.23.**\
$(X,d)$ a metric space. $T \subseteq X$
<center>
$T$  disconnected $\iff\ \exists$ continuous $f:T \to \mathbb{R}\text{ s.t } f(T) = \{0,1\}$
</center>
 
**Theorem 2.22**.

Consider $(\mathbb{R},d)$, $S \subseteq \mathbb{R}$
      <center>
$S$ connected  $\iff S$ an interval
      </center>
      
     
### <span style="color: white;">2.3.2</span> Continuous maps + Connected sets

**Theorem 2.27**.

$(A,d_{1})$ and $(A,d_{2})$ metric spaces. $f: A_1 \to A_2$ continuous map
$S \subset A$ connected $\implies f(S)$ connected

***Corollary 2.28***
$f:(X,d_X) \to (Y,d_Y)$ a homeomorphism\
      <center>
$X$ connected $\iff Y$ connected
      </center>
 
**Theorem 2.29**.

$(X,d)$ connected metric space, $f: X \to \mathbb{R}$ continuous. Assume
$\exists a,b \in X$ s.t $f(a) <0, f(b) > 0 \implies \exists c \in X$ s.t
$f(c) = 0$

### <span style="color: white;">2.3.3</span> Path Connected Sets

 
**Definition 2.28**. <span style="color: green;">**Path**</span>

Under $(X,d)$ given $a,b \in X$\
**Path** from $a \to b$ a continuous map $f: [0,1] \to X$ s.t $f(0) = a, f(1) = b$

 
**Definition 2.29**. <span style="color: green;">**Path Connected**</span>


$(X,d)$ path connected if $\forall a,b \in X, \exists$ path from $a\to b$ in $X$

 
**Theorem 2.30**.

if $(X,d)$ path connected $\implies$ connected

## <span style="color: white;">2.4</span> Compactness

### <span style="color: white;">2.4.1</span> Compactness by covers

 
**Definition 2.30**. <span style="color: green;">**Covers**</span>

$(X,d)$ a metric space. $Y \subseteq X$

1.  collection $R$ of open subsets of $X$ an <span style="color: green;">**open cover**</span> for $Y$ if
      <center>
    $$Y \subseteq \bigcup_{v \in R}v$$
      </center>
      
2.  Given open cover $R$ for $Y$\
    Say $C$ a <span style="color: green;">**sub-cover**</span> of $R$ for $Y$
    if $C \subseteq R$ and $Y \subseteq \bigcup_{v \in R}v$

3.  Open cover $R$ for $Y$ is a [**finite
    cover**] if $R$ has finitely many
    elements.

 
**Definition 2.31**. <span style="color: green;">**Compact**</span>

$(X,d)$ a metric space\
$Y \subseteq X$ compact in $(X,d)$ if every open cover for $Y$ has a finite sub-cover.\
      
**Proposition 2.32.**\
$a,b \in \mathbb{R},\ a \leq b$ in $(R,d_1)$ we have $[a,b]$ compact\
      
**Proposition 2.33.**\
$(X,d)$ a metric space, $Y \subseteq X$\
$X$ compact, $Y$ closed $\implies Y$ compact.

 
**Theorem 2.34**.

$(X,d)$ a metric space $Y \subset X$
      <center>
$Y$ compact  $\implies Y $ closed
      </center>
 
**Theorem 2.35**.

$(X,d_X),(Y,d_Y)$ metric spaces. Considering $(X\times Y,d)$\
$d((x_{1},y_{1}),(x_{2},y_{2})) = d_{1}(x_1,x_2) + d_2(y_1,y_2)$\
$X, Y$ compact $\implies (X \times Y,d)$ compact

**Corollary.**\
$[a_1,b_1]\times[a_2,b_2]\dots\times[a_{n-1},b_{n-1}]\times[a_n,b_n]$
compact in $\mathbb{R}^{n}$

 
**Definition 2.32**. <span style="color: green;">**Bounded**</span>

$(X,d)$ non-empty metric space, $Z \subseteq X$\
$Z$ <span style="color: green;">**bounded**</span> in $(X,d)$ if $\exists M \in \mathbb{R}$ s.t $\forall x,y \in Z; d(x,y) \leq M$\
$S$ arbitrary set. $f: S \to X$ bounded if $f(S)$ bounded in $X$

**Lemma 2.37.**\
$(X,d)$ compact metric space $\implies X$ bounded

 
**Theorem 2.36**. <span style="color: red;">**Heine-Borel**</span>

Consider $(\mathbb{R}^{n},d_{2})$, $X \subseteq \mathbb{R}^{n}$\
$X$ compact $\iff X$ closed and bounded

### <span style="color: white;">2.4.2</span> Sequential Compactness

 
**Definition 31**. <span style="color: green;">**Sequentially compact**</span>


$(X,d)$ sequentially compact, if for every sequence in $X$ has convergent subsequence in $(X,d)$
      <center>
$$\forall (x_n)_{n\geq 1} \in X,\ \exists (x_{n_k})_{k\geq 1},\ x \in X \text{ s.t } x_{n_k} \to x$$
      </center>
      
**Lemma 2.39.**\
$(X,d)$ a metric space. with sequence $ (x_{n})_{n\geq 1} \text{ s.t } \exists (x_{n_k})_{k\geq 1},\ x \in X \text{ s.t } x_{n_k} \to x$.\
      <center>
$\iff \exists x \in X$ s.t  $\forall \epsilon > 0$ there are infinitely many  $i$  s.t  $x_{i} \in B_{\epsilon}(x)$
      </center>

**Theorem 2.41**. <span style="color: red;">**Bolzanno-Weierstrass**</span>

Any bounded sequence in $\mathbb{R}^{n}$ has convergent subsequence.

**Theorem 2.40 + 2.42.**

$(X,d)$ metric space.
      <center>
$X$  Compact  $\iff X$  Sequentially Compact
      </center>
      
### <span style="color: white;">2.4.3</span> Continuous maps + Compact Sets
 
**Theorem 2.41**.

$(X,d_X),(Y,d_Y)$ metric spaces.\
$f: X\to Y$ a continuous map if
$$Z \text{ compact in } X \implies f(Z) \text{ compact in }Y$$

**Corollary 2.44.**\
$(X,d_X),(Y,d_Y)$ metric spaces, $f:X \to Y$ a homeomorphism
      <center>
$$\implies X \text{ compact } \iff Y \text{ compact }$$
      </center>
 
**Theorem 2.45**.

Every continuous map from compact metric space to a metric space is
uniformly continuous.

**Corollary 2.46.** $f:[a,b] \to \mathbb{R}$ continuous $\implies$ $f$
uniformly continuous

 
**Theorem 2.47**.

$(X,d_X)$ compact, $f:X \to \mathbb{R}$ continuous $\implies f$ bounded above and below attaining its upper & lower bounds

 
**Theorem 2.48**.

$f:\mathbb{R}\to \mathbb{R}$ continuous w.r.t Euclidean metrics on domain and range.\
$\forall\ [a,b]$ we have $f([a,b])$ of the form $[m,M]$ for $m,M \in \mathbb{R}$

## <span style="color: white;">2.5</span> Completeness

### <span style="color: white;">2.5.1</span> Complete metric spaces & Banach space

 
**Definition 32**. <span style="color: green;">**Cauchy Sequence**</span>

$(X,d)$ a metric $(x_{n})_{n\geq 1}$ sequence in $X$\
      
Say $(x_{n})_{n\geq 1}$ a <span style="color: green;">**Cauchy sequence**</span> in $(X,d)$ if
      <center>
$$\forall \epsilon > 0, \exists N_{\epsilon} \in \mathbb{N}\text{ s.t } \forall n,m \geq N_{\epsilon} d(x_{n},x_{m}) < \epsilon$$
      </center>

**Definition 2.35.** <span style="color: green;">**Complete & Banach**</span>

1.  metric space $(X,d)$ <span style="color: green;">**complete**</span> if every Cauchy sequence in $X$ converges to a limit in $X$

2.  Normed vector space $(V,\lvert\lvert\cdot\rvert\rvert)$ a <span style="color: green;">**Banach space**</span> if $V$ with induced metric space $d_{\lvert\lvert\cdot\rvert\rvert}$ a complete metric space.

 
**Theorem 2.51**.

Assume $(f_{n} : [a,b] \to \mathbb{R})_{n\geq 1}$ sequence of continuous functions converging uniformly to $f:[a,b] \to \mathbb{R}\implies f:[a,b] \to \mathbb{R}$ continuous

 
**Theorem 2.52**.

Metric space $(C([a,b]),d_{\infty})$ is complete or equivalently $(C([a,b]),\lvert\lvert\cdot\rvert\rvert_{\infty})$ a Banach space

 
**Theorem 2.53**.

$(X,d)$ a compact metric space $\implies (X,d)$ complete

### <span style="color: white;">2.5.2</span>  Arzelà-Ascoli

 
**Definition 2.36**. <span style="color: green;">**Uniformly bounded & Uniformly equi-continuous**</span>


Let $\mathcal{C}$ a collection of functions $f:[a,b] \to \mathbb{R}$

1.  Say collection $\mathcal{C}$ <span style="color: green;">**uniformly bounded**</span> if $\exists M$ s.t
    $\forall f \in \mathcal{C}$ and
    $\forall x \in [a,b] \implies |f(x)| < M$

2.  Say collection $\mathcal{C}$ <span style="color: green;">**uniformly equi-continuous**</span> if
    $\forall \epsilon > 0, \exists \delta > 0$ s.t
    $\forall f \in \mathcal{C}$ and $\forall x_1,x_2 \in [a,b]$ s.t
    $|x_1-x_2| < \delta$ we have $|f(x_1) - f(x_2)| < \epsilon$

 
**Theorem 2.54**. <span style="color: red;">**Arzelà-Ascoli**<span>

Assume $\mathcal{C}$ collection of continuous functions
$f:[a,b] \to \mathbb{R}$ if $\mathcal{C}$ uniformly bounded and
uniformly equi-continuous $\implies$ every sequence in $\mathcal{C}$ has
convergent subsequence in $(C([a,b],d_{\infty})$

### <span style="color: white;">2.5.3</span>  Fixed point theorem

 
**Definition 2.37**. <span style="color: green;">**Contracting**</span>

$(X_{1},d_{1})$ and $(X_{2},d_{2})$, with $f: X_1 \to X_2$\
Say $f$ <span style="color: green;">**contracting**</span> if $\exists K \in (0,1)$ s.t $\forall a,b \in X$ we have
      <center>
$$d_{2}(f(a),f(b)) \leq K\cdot d_{1}(a,b)$$
      </center>
Every contracting map is continuous.

 
**Definition 2.37**. <span style="color: green;">**Fixed point**</span>

$f:X\to X$ say $x \in X$ a <span style="color: green;">**fixed point**</span> of $f$ if $f(x) = x$

**Theorem 2.55**. <span style="color: red;">**Banach fixed point theorem**</span>


$(X,d)$ a non-empty complete metric space.\
$f: X \to X$ a contracting map $\implies f$ has unique fixed point in
$X$

