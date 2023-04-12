---
layout: default
title: Galois Theory
parent: Year 3
nav_order: 3
math: mathjax3
---

# Galois Theory - Concise Notes
{: .no_toc }
## MATH60037
{: .no_toc}

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
  
- <a href="/notes/pdfs/year3/LecNotes/G-Concise.pdf" target="_blank" style="color:#801fff;">**Open Applied Probability Concise**</a> - <a href="/notes/pdfs/year3/LecNotes/G-Concise.pdf" download>**Download**</a>
- <a href="/notes/pdfs/year3/LecNotes/G-LecNote.pdf" target="_blank" style="color:#801fff;">**Open Applied Probability Lecture Notes**</a> - <a href="/notes/pdfs/year3/LecNotes/G-LecNotes.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets</span>
  </summary>
  
  - <a href="/notes/pdfs/year3/probSheets/ap/AP-PS.pdf" target="_blank" style="color:#00ba47;">**All 5 Problem Sheets**</a>

  - <a href="/notes/pdfs/year3/probSheets/ap/AP-PS1-Sol.pdf"  target="_blank">**PS1 - Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ap/AP-PS2-Sol.pdf"  target="_blank">**PS2 - Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ap/AP-PS3-Sol.pdf"  target="_blank">**PS3 - Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ap/AP-PS4-Sol.pdf"  target="_blank">**PS4 - Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ap/AP-PS5-Sol.pdf"  target="_blank">**PS5 - Solutions**</a>

</details>
</details>

<details closed markdown="block">
  <summary>
    Table of contents
  </summary>
<!--   {: .text-delta } -->
* TOC
{:toc}
</details>

---

# What is Galois Theory?

## Field extensions


**Definition 1**. *A **field homomorphism** a function
$\phi : K_1 \to K_2$ that preserves the field operations
$\forall a,b \in K_1$

$$\phi (a+b) = \phi (a) + \phi (b), \quad \phi (ab) = \phi (a)\phi (b), \quad \phi (0_{K_1}) = 0_{K_2} \quad \phi (1_{K_1}) = \phi 1_{K_2}$$



**Definition 2**. *$\alpha$ **algebraic** over $k$ if $f(\alpha ) = 0$
for some $0 \neq  f \in k[X]$, otherwise $\alpha$ **transcendental**
over $k$

*Extension $k \subset K$ **algebraic** if $\forall \alpha \in K, \alpha$
is algebraic over $k$



**Definition 3**. *Consider field $k$ and $f \in k[X]$. Say
$k \subset K$ a **splitting field** for $f$ if
$$f(X) = a\prod\limits_{i=1}^{n} (X- \lambda_{i}) \in K[X], \quad K = k(\lambda_1, \ldots ,\lambda_{n} )$$


## Galois correspondence


**Theorem 4**. *(Fundamental theorem of Galois Theory, Galois
correspondency)*

*Assume characteristic 0. Let $k \subset K$ be the splitting field of
$f(X) \in k[X]$ Let
$$G = \{\sigma :K \to K \mid  \sigma  \text{ a field automorphism, } \sigma\mid_{k} = id_{k}   \}$$
Call this the **Galois group**. There is a one-to-one correspondence
$$\begin{aligned}
        \{k \subset K_1 \subset K \mid K_1 \text{ a subfield } \} &\leftrightarrow \{H \leq G \mid  H \text{ a subgroup} \}\\
        K_1 &\leftrightarrow \{\sigma \in G \mid  \forall k \in K_1, \sigma (\lambda ) = \lambda \\
        \{\lambda  \in K \mid  \forall  \sigma  \in H, \sigma (\lambda ) = \lambda \} &\leftrightarrow \{H \leq  G\}
    \end{aligned}$$



**Definition 5**. *$K \subset L$ is **finite** if $L$ a
finite-dimensional $K$-vector space. The **degree** of $L$ over $K$ is
$$[L:K] = dim_{K}L$$



**Theorem 6**. *(Tower Law)*

*Let $K \subset L \subset F$ Then $$[F:K] = [F:L] [L:K]$$



**Theorem 7**. *Suppose $f(X) in K[X]$ irreducible such that
$f(\lambda ) =0,$ then $[K(\lambda ):K] = \mathop{deg}f$


# Fundamental theorem of Galois Theory

## Elementary facts


**Definition 8**. *$K \subset L, a\in L$ . We say the **evaluation
homomorphism**

$$e_{a}\colon K[X] \to K[a] \subset L, f(X) \mapsto f(a)$$ 

is a surjective ring homomorphism, where $K[a]$ the smallest subring of $L$
containing $K$ and $a$



**Definition 9**. *$f(X) = a_0 X^n + \ldots  + a_{n} \in K[X]$ is
**monic** if $a_0 = 1$



**Lemma 10**. *.*

-   *If $a$ *transcendental*, $e_{a}$ is injective and it extends to
    $\widetilde{e}_{a}:K(X) \to K(a)$ by $$DIAGRAM HERE$$

-   *If $a$ *algebraic* then $\mathop{ker} e_{a} = \left< f_{a} \right>$
    where $f_{a}\in K[X]$ irreducible or prime, and unique if $f$ monic,
    then called the **minimal polynomial of $a \in L / K$* . In this
    case $$DIARGRAM\ HERE$$



**Corollary 11**. *For $K \subset L$ and $a \in L$ *algebraic* over $K$

-   *$[K(a) :K] = \mathop{deg} f_{a}$, and*

-   *If $K \subset F$ an extension
    $$\mathop{Em}_{K} (K(a), F) = \{ b \in F \mid  f_{a}(b) = 0\}$$



**Corollary 12**. *Let $K$ a field and $f \in K[X]$. Then
$\exists K \subset L$ s.t $f$ has a root in $L$


**REMARK TO ADD HERE**

## Axiomatics


**Proposition 13**. *Fix $k \subset K$ and $k \subset L$ Then
$$\# \mathop{Em}_{k} (K, L) \leq [K:k]$$



**Proposition 14**. *Suppose given 2 field extensions $k \subset K$ and
$k \subset L$. Then there is a non-unique bigger common field containing
both. $$DIAGRAM\ HERE$$ Formally: given $\sigma_1 \in Em(k,K)$ and
$\sigma_2 \in Em(k,L)$ then $\exists \Omega , \phi_1 \in Em(k, \Omega )$
and $\phi_2 \in Em(L, \Omega  )$ such that
$\phi_1 \circ \sigma_1 = \phi_2 \circ \sigma_2$

*Alternatively: $\exists k \subset \Omega$ such that $Em_k (K,\Omega  )$
and $Em_k (L, \Omega  )$ are both non-empty*



**Proposition 15**. *Let $L$ be any field and $G$ a finite group action
on $L$ as automorphism. Let
$$K = G^{\ast} = \mathop{Fix} G = L^G = \{ \lambda \in L \mid \forall \sigma \in G, \sigma (\lambda ) = \lambda \}$$
Consider $\mathop{Aut}_{K}L = K^{\dagger}$. Then the obvious inclusion
$G \subset K^{\dagger} = (G^{\ast} )^{\dagger}$ is an equality, so $G$
is all of $K^{\dagger}$.\
**Remark***

*We have to contextualise half of the Galois correspondence
$$\begin{aligned}
        \{F \mid k \subset F \subset \Omega  \} &\leftrightarrow \{G \mid G \leq \mathop{Aut}_{k}\Omega   \}\\
        F &\leftrightarrow \mathop{Aut}_{k} \Omega  = F^{\dagger}\\
        \mathop{Fix} G = G^{\ast} &\leftrightarrow G
    \end{aligned}$$



**Lemma 16**. *$K \subset L$ a finite extension of degree
$[L:K] \leq \# G$


## Galois correspondence


**Definition 17**. *$k \subset K$ is **normal** if
$$\forall k \subset \Omega , \forall \sigma_1, \sigma_2 \in Em_k (K, \Omega), \exists \sigma \in Em_k (K,K), \sigma_2 = \sigma_1 \circ \sigma$$
Equivalently $k \subset K$ is normal if
$$\forall k \subset \Omega , \forall \sigma_1, \sigma_2 \in Em_k (K, \Omega), \sigma_2(K) \subset \sigma_1(K)$$
**Remark***

*Will see later that $k \subset K$ is normal if and only if
$\exists f(X) \in k[X]$ such that $K$ a splitting field of $f$



**Lemma 18**. *Suppose $k \subset K$ normal. Consider
$k \subset L \subset K$ Then also $L \subset K$ is normal*



**Definition 19**. *$k \subset K$ is **separable** if
$\forall k  \subset K_1 \subset K_2 \subset K$, if $K_1 \neq K_2$ then
$\exists k \subset \Omega$ and embeddings $x \in Em_{k}(K_1, \Omega )$
and $y_1,y_2 \in Em_{k}(K_2,\Omega )$ such that $$DIAGRAM\ HERE$$ That
is $y\mid_{K_1} = x$ but $y_1 \neq y_2$\
We have that embeddings separate fields. Will see that*

-   *in Char 0, everything is separable*

-   *in Char $p$ there are good ways to decide if a field is separable*



**Lemma 20**. *Suppose $k \subset K \subset L$ Then $k \subset L$
separable if and only if $k\subset K, K \subset L$ is separable*



**Theorem 21**. **(Fundamental theorem of Galois theory, Galois
correspondence)*\
Let $k \subset K$ be normal and separable. Let $G = Em_{k}(K,K)$ then
there is a one-to-one correspondence $$\begin{aligned}
    \{k \subset L \subset K\} &\leftrightarrow \{H \leq G\}\\
    L &\rightarrow  L^{\dagger} = \{\sigma  \in G \mid \forall \lambda  \in L, \sigma(\lambda ) = \lambda \}\\
    H^{\ast} = \{\lambda \in K \mid \forall \sigma \in H, \sigma (\lambda ) = \lambda \} &\leftarrow H\end{aligned}$$



**Lemma 22**. *Suppose $k \subset K$ normal. Then for all towers
$k \subset F \subset K \subset \Omega$, the natural restriction

$$\rho : Em_{k}(K,\Omega ) \to Em_{k}(F, \Omega )$$ 

is surjective



**Corollary 23**. *Suppose $k \subset K$ normal. Then for all towers
$k \subset F \subset K \subset \Omega$

$$Em_{k}(F,K) \to Em_{k}(F,\Omega )$$ 

is also surjective*


# Normal and separable extensions

## Normal extensions


**Theorem 24**. *For finite $k \subset K$, the following are equivalent*

1.  *$\forall  f \in k[X]$ irreducible, either $f$ has no roots in $K$
    or $f$ splits completely in $K$

2.  *$\exists f \in k[X]$ not necessarily irreducible such that $K$ is a
    splitting field of $f$

3.  *$k \subset K$ is normal*



**Proposition 25**. *Let $k \subset L$ be a field extension. Then there
exists a tower $k \subset L \subset K$ such that $k \subset K$ is
normal*


## Separable polynomials


**Definition 26**. *A polynomial $f \in k[X]$ is **separable** if it has
$n = deg(f)$ distinct roots in any field $k \subset K$ such that
$f \in K[X]$ splits completely\
**Remark**\
It is not completely obvious that this definition is independent of
$K$ - use the fact that 2 splitting fields are isomorphic.*



**Remark 27**. *Derivative

$$D \colon k[X] \to k[X], X^n \mapsto nX^{n-1}$$

Having the following properties

-   *$D$ is k-linear, that is
    $\forall \lambda ,\mu \in k, \forall f,g \in k[X]$

    $$D(\lambda f + \mu g) = \lambda Df + \mu Dg$$

-   *Leibnitz rule, $\forall f,g \in k[X]$ $$D fg = fDg + gDf$$


**Proposition 28**. *$f(X) \in k[X]$ is separable if and only if
$gcd(f,Df) = 1$



**Lemma 29**. *Let $f,g \in k[X]$ and $c = gcd(f,g) \in k[X]$\
Let $k \subset L$ an extension, then $c = gcd(f,g) \in L[X]$



**Theorem 30**. *$f\in k[X]$ irreducible is inseparable if and only if*

-   *$ch(k) = p > 0$, and*

-   *$\exists h\in k[X]$ such that $f(X) = h(X^p)$



**Definition 31**. *A field $k$ in $ch (k) = p > 0$ is **perfect** if
$\forall a \in k$ there exists $b \in k$ such that $b^p = a$



**Proposition 32**. *If $k$ is perfect then $f \in k[X]$ is irreducible
implies that $f(X)$ is separable*



**Definition 33**. *Consider $k \subset L$. An element $a \in L$ is
**separable** over $k$ if the minimal polynomial $f(X) \in k[X]$ of $a$
is a separable polynomial*


## Separable degree


**Definition 34**. *Let $k \subset K$. Choose $K \subset \Omega$ such
that $k \subset \Omega$ is normal. Define the **separable degree** as

$$[K:k]_{s} = \# Em_{k}(K,\Omega )$$

**Remark**

$[K:k]_{s}$ does not depend on $K \subset \Omega$. Suppose
$k \subset \Omega_1$ and $k \subset \Omega_2$ are normal. Then there
exists a bigger field $\widetilde{\Omega}$ such that
$\Omega_1 \subset \widetilde{\Omega} , \Omega_2 \subset \widetilde{\Omega}$
Then

$$Em_{k}(K,\Omega_1) = Em_{k}(K,\widetilde{\Omega} ) = Em_{k}(K,\Omega_2)$$

**Remark**\
Restate definition of separable extension. Recall $k \subset K$
separable if for all towers $k \subset K_1 \subset K_2 \subset K$ there
exists $\Omega ,y : K_1 \to \Omega , x_1,x_2: K_2 \to \Omega$ such that
$x_1 \neq  x_2$ and $x_1\mid_{K_1} = x_2\mid_{K_2} = y$ so
$[K_2:K_1] \neq  1$. Thus $k \subset K$ separable if for all towers
$k\subset K_1 \subset K_2 \subset K$ $[K_2:K_1]_{s} = 1$ implies that
$K_1 = K_2$



**Theorem 35**. *(Tower Law)\
$\forall k \subset K \subset L$ $$[L:K]_{s} = [L:K]_{s}[K:k]_{s}$$


## Separable extensions

Recall that for $k \subset K$, said $a \in K$ separable if minimal
polynomial of $f(X) \in k[X]$ of $a$ is separable polynomial


**Theorem 36**. *$k \subset K$ is separable if and only if
$[K:k]_{s}= [K:k]$



**Corollary 37**. *For all towers $k \subset K \subset L$ if
$k \subset K$ and $K \subset L$ are separable then $k \subset L$ is
separable*



**Corollary 38**. *$k \subset K$ is separable if and only if
$\forall a \in K$, $a$ is separable over $k$



**Lemma 39**. *Let $k \subset L \subset K$. For $\lambda  \in K$,
$\lambda$ is separable over $k$ implies that $\lambda$ is separable over
$L$


# Examples

## Biquadratic extensions

Let $$K \subset K 
    \left( \sqrt{a \pm \sqrt{b} }  \right) = L, \quad c = a^{2} -b, \quad \beta = \sqrt{b} \not\in K, \quad \alpha = \sqrt{a+ \beta } \in L, \quad \alpha^\prime = \sqrt{a - \beta } \in L$$
We know that $\pm \alpha ,\pm \alpha^\prime$ are roots of

$$f(X) = X^4 - 2aX^{2} +c$$

Not assuming that $f(X)$ is irreducible. Let

$$\delta  = \alpha  + \alpha^\prime \quad \delta^\prime = \alpha - \alpha^\prime, \quad \gamma = \alpha \alpha^\prime = \sqrt{c}$$

Then

$$\gamma^{2} =c, \quad \delta^{2} = 2(\alpha + \gamma ), \quad \delta^{2} = 2(\alpha -\gamma ),\quad \delta \delta^\prime = 2\beta, \quad \alpha = \frac{\delta +\delta^\prime }{2}, \quad \alpha^\prime = \frac{\delta -\delta^\prime }{2}$$

and we have $\pm \delta ,\pm \delta^\prime$ are roots of

$$g(Y) = Y^4 - 4aY^{2} + 4b$$

Then $L$ is the splitting field of $g$.

Assume

1.  $ch(K) \neq  2$ and

2.  $b$ is not a square in $K$ , that is $[K(\beta ):K] =2$

Claim that the extension $K \subset L$ is separable.\
It is the splitting field of $f(X)$ Need to check that $gcd(f,Df) =1$
where $$Df = 4X^{3} - 4aX  = 4X(X^{2} -a)$$ $f,Df$ have no common roots
since $X = 0$ not a root of $f$ and $X = 
\pm \sqrt{a}$ not a root of f, as $b \neq  0$


**Theorem 40**. *Assume 1 and 2 from before*

1.  *Suppose $bc, c$ are not square. Then

    $$[L:K] = 8, \quad G = \mathcal{D}_8$$
    
    and $f(X)$ is irreducible*

2.  *Suppose $bc$ square, so $c$ not square. Then

    $$[L:K] = 4, \quad G = \mathcal{C}_4$$
    
    and $f(X)$ is irreducible*

3.  *Suppose $c$ a square, so $bc$ is not a square. Then*

    -   *either $2(\alpha +\gamma )$ and $2(\alpha -\gamma )$ are both
        not square in $K$ then

        $$[L:K] = 4,  \quad G = \mathcal{C}_2 \times \mathcal{C}_2$$ 
        
        and
        $f(X)$ is irreducible*

    -   *or one of $2(\alpha +\gamma )$ or $2(\alpha -\gamma )$ is a
        square in $K$, but not the other, then

        $$[L:K] = [K(\beta ):K] = 2, \quad G = \mathcal{C}_2$$
        
        and $f(X)$ is reducible*



**Lemma 41**. *Let $B \in F$ and $A \in F$ be not square in $F$. If $B$
is square in $F(\sqrt{A} )$ then either $B$ is square in $F$ or $AB$
square in $F$


## Finite fields


**Theorem 42**. *Fix a prime $p > 0$. Then
$\forall m \in \mathbb{Z}_{\geq 1} \exists$ a unique, up to non-unique
isomorphism, finite field with $q = p^m$ elements. The notation is
$\mathbb{F}_{q}$
$$G = Gal(\mathbb{F}_{q}/\mathbb{F}_{p}) = \mathbb{Z} / m \mathbb{Z}$$


## Symmetric polynomials

Consider

$$f(X) = (X-x_1) \cdots (X-x_n) = X^n - \sigma_1 X^{n-1} + \cdots \pm \sigma_n \in K(x_1, \cdots ,x_n)[X]$$
where
$$\sigma_1 = \sigma_1(x_1, \cdots ,x_n) = \sum_{i \leq i \leq n} x_{i}, \quad \sigma_2 = \sigma_2(x_1, \cdots ,x_n) = \sum_{i \leq i \leq  j \leq  n} x_{i}x_{j}, \quad \cdots$$
Here $\sigma_1 \in K[x_1, \ldots , x_{n} ]$ are the **elementary
symmetric polynomials**. Let
$$\delta  = \prod\limits_{\text{roots of } f} (x_{i} - x_{j}), \quad \Delta = \delta^{2} = \prod\limits_{\text{roots of } f} (x_{i} - x_{j})^{2}$$


**Definition 43**. *$\sigma \in K[x_1, \ldots ,x_{n} ]$ is symmetric if
and only if $\forall  g\in S_{n}$
$$\sigma (x_{g(1)}, \ldots ,x_{g(n)}) = \sigma (x_{1}, \ldots ,x_{n})$$



**Theorem 44**. *Consider a degree $n$ separable polynomial
$f(X) = X^n + a_1 X^{n-1} + \cdots + a_{n-1} X + a_n \in k[x]$. Let
$k \subset L$ be the splitting field of $f$. Then
$G \subset \mathcal{A}_{n}$ if and only if $\Delta$ is a square in $k$



**Theorem 45**. *Consider an irreducible cubic polynomial
$X^{3} - \sigma_1 X^{2} + \sigma_2 X -\sigma_3$ and $k \subset L$ be the
splitting field then $G = \mathcal{S}_3$ iff $\Delta$ is not a square in
$k$, and $G = \mathcal{A}_3 = \mathcal{C}_3$ iff $\Delta$ is square in
$k$


# Irreducible polynomials


**Proposition 46**. *Suppose
$f(X) = a_0 + \ldots + a_{d}X^d \in \mathbb{Z}[X]$ has a root
$\frac{p}{q} \in \mathbb{Q}$ with $gcd(p,q) = 1$ then $[p \mid a_0]$ and
$q \mid  a_{d}$



**Lemma 47**. **(Gauss' Lemma)**

*Suppose $f(X) = a_0 + \ldots + a_{d}X^d \in \mathbb{Z} [X]$ for
$gcd(a_0, \ldots , a_{d} ) = 1$ factorises non-trivially in
$\mathbb{Q} [X]$. Then it factors non-trivially in $\mathbb{Z} [X]$



**Corollary 48**. *if $f(X)$ is prime in $\mathbb{F}_{p}[X]$ for some
$p$, then it is prime in $\mathbb{Q} [X]$



**Corollary 49**. **(Eisenstein)**

*$f(X) = a_0 + \ldots + a_{d}X^d \in \mathbb{Z} [X]$ is irreducible in
$\mathbb{Q} [X]$ if there exists $p$ prime such that $\not \mid a_{d}$
but $p \mid  a_{i}$ for $i < d$ and $p^{2} \not\mid a_0$


# Reduction modulo prime


**Theorem 50**. *Let $f(X) \in \mathbb{Z} [X]$ be monic of degree
$n, \mathbb{Q} \subset K$ be the splitting field of $f$ and
$G = Gal(K / \mathbb{Q} ) \subset S_{n}$. For $p$ prime, denote by
$\overline{f}$ as $f$ viewed in $\mathbb{F}_{p}[X]$. If there exists $p$
such that $\overline{f} \in \mathbb{F}_{p}[X]$ has $n$ distinct roots
ina splitting field and
$\overline{f} = \prod\limits_{i=1}^{k} \overline{f}_{i}(X) \in \mathbb{F}_{p}[X]$
with $\overline{f}_{i} \in \mathbb{F}_{p}[X]$ irreducible of degree
$n_{i}$ then there exists $\sigma \in G \subset \mathcal{S}_{n}$ of
cycle decomposition type $$(n_1) \ldots (n_{k})$$



**Proposition 51**. *Suppose that $r$ is prime and let
$G \subset \mathcal{S}_{r}$ be a subgroup. If $G$ contains an $r$-cycle
and one transposition then $G = \mathcal{S}_{r}$



**Definition 52**. *The **character** of a monoid $P$ to $K$ is
$\chi : P \to K$ such that*

-   *$\chi (0) = 1$, and*

-   *$\chi (a + b) = \chi (a) \chi (b)$ for all $a,b \in P$



**Theorem 53**. **Linear independence of characters, Dedekind
independence theorem*\
Let $K$ a field and $P$ a monoid, such as $P = \mathbb{N}$. Any set of
distinct non-zero characters

$$\chi_1: P \to K, \quad \ldots \quad \chi_{n}: P \to K,  \ldots$$

is linearly independent in the vector space $\{f:P \to K\}$



**Theorem 54**. *Let $f(X) \in \mathbb{Z} [X]$ be degree $n$ monic,
$\mathbb{Q} \subset K$ be the splitting field of $f$ ,
$G = Gal(K / \mathbb{Q} ) \subset \mathcal{S}_{n}$ and
$\lambda_1, \ldots \lambda_{n} \in K$ be the roots of $f(X)$. Let $p$ be
a prime. Denote by $\overline{f}$ the image $f$ modulo $p$. Assume
$\overline{f}$ is separable. Let $\mathbb{F}_{p}
    \subset F$ be a splitting field for $\overline{f}$, so
$\overline{f}$ has $n$ distinct roots in $F$ . Let $R \subset K$ be the
subring generated by the roots of $f$, so
$R = \mathbb{Z} [\lambda_1, \ldots , \lambda_{n} ]$ Then*

1.  *there exists a ring homomorphism $\psi : R \to F$

2.  *if $\psi^\prime : R \to F$ a ring homomorphism then $\psi^\prime$
    induces a bijection
    $$\phi^\prime : \{ \text{roots of } f(X) \text{ in } R\} \to \{ \text{roots of } \overline{f} \text{ in } F\}$$

3.  *$\psi^\prime : R \to F$ a ring homomorphism if and only if there
    exists $\sigma \in G$ such that $\psi^\prime = \psi \circ \sigma$

