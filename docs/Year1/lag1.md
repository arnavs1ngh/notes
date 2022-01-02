---
layout: default
title: Linear Algebra & Groups
parent: Year 1
nav_order: 1
math: mathjax3
---
# Linear Algebra and Groups 1 - Concise
{: .no_toc }
## MATH40002
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

**Term 1 Content**

**Louis Gibson**

# System of Linear Equations

## Introductions


**Definition 1**.

Given a system of linear equations in n unknowns we can write this in
matrix form as follows:\
$$AX=B$$ where $X = 
\left[
\begin{array}{c}
     x_{1} \\
     x_{2}  \\    
     x_{3}  \\
     \vdots \\
     x_{n}
\end{array}
\right]$ and $B = 
\left[ 
\begin{array}{c}
    b_{1}\\
    b_{2}\\
    \vdots \\
    b_{m}
\end{array}
\right]$ are column matrices, and $A = 
\left[
\begin{array}{cccc}
     a_{11}&a_{12}&\ldots&a_{1n}  \\
     a_{21}&a_{22}&\ldots&a_{2n} \\
     \vdots\\
     a_{m1}&a_{m2}&\ldots&a_{mn}
\end{array}
\right]$ is an $m \times\ n\  matrix$\
We can also use an **Augmented Matrix** to represent the system of
linear equations:\
$$\left(
\begin{array}{cccc|c}
a_ 11 & a_12 &\ldots& a_1n& b_{1} \\
a_21 & a_22 &\ldots& a_2n & b_{2}\\
\vdots &&&& \vdots\\ 
a_m1 & a_m2 &\ldots& a_mn & b_{m}
\end{array}
\right)$$

## Matrix Algebra

Given $A = [a_{ij}]_{m\times n}, B = [b_{ij}]_{m\times n}$

-   [**Matrix Sum:**]{style="color: ForestGreen"}
    $C = A + B,\ c_{ij} = a_{ij} + b_{ij}$

-   [**Scalar Multiplication:**]{style="color: ForestGreen"}
    $\lambda A = [\lambda a_{ij}]$

-   [**Matrix Multiplication:**]{style="color: ForestGreen"}
    $A = [a_{ij}]_{p \times q}, B = [b_{ij}]_{q \times r} \Rightarrow C = AB = [c_{ij}]_{p\times r}$
    where $c_{ij} = \sum_{k=1}^{q}a_{ik}b_{kj}$

**Theorem 2.2.4** Associativity of Matrix Multiplication.

::: center
Let $A, B, C$ be matrices, and
$\alpha \in \mathbb{R} \implies (AB)C=A(BC)$\
:::

**Proof**\
For $A(BC)$ to be defined, we require the respective sizes of the
matrices to be $m \times n$, $n \times p$, $p \times q$ in which case
the product $A(BC)$ is also defined. Calculating the $(i,j)^{\text{th}}$
element of this product, we obtain,
$$[A(BC)]_{ij} = \sum^n_{k=1}a_{ik}[BC]_{kj} = \sum^n_{k=1}a_{ik})(\sum^p_{t=1}b_{kt}c_{tj})\\
= \sum^n_{k=1}\sum^p_{t=1}a_{ik}b_{kt}c_{tj}\\
$$ If we now calculate the $(i,j)^{\text{th}}$ element of $(AB)C$ we
obtain the same result:
$$[(AB)C]_{ij} = \sum^p_{t=1}[AB]_{it}c_{tj} = \sum^p_{t-1}(\sum^n_{k=1}a_{ik}b_{kt})c_tj\\
                                        \\= \sum^p_{t=1}\sum^n_{k=1}a_{ik}b_{kt}c_{tj}$$
$\implies A(BC) = (AB)C$

## Row Operations

**Definition [**Elementary Row
operation**]{style="color: ForestGreen"}** Are performed on an augmented
matrix\
There are three allowable operations:

-   **Multiply** a row by any non zero number

-   **Add to any row a multiple of another row**

-   **Interchange** two rows

**Remark 2.3.3**

1.  Performing row operations preserves the solutions of a linear system

2.  Each row operation has an inverse row operation

**Definition 2.3.5**\
Two systems of linear equations are equivalent if either :

1.  They are both inconsistent

2.  The augmented matrix of the first system can be obtained using row
    operations from the augmented matrix of the second system and vice
    versa

**Remark 2.3.6**\
Equivalently, by Remark 2.3.3 two systems of linear equations are
equivalent $\iff$ they have the same set of solutions\
If a row consists of mainly 0s and 1s it becomes easier to read off the
solutions to the equation\
**Definition 2.3.8**\
We say a matrix is in [**echelon form**]{style="color: ForestGreen"}if
it satisfies the following:

1.  All of the zeros are at the bottom

2.  The first non-zero entry in each row is $1$

3.  The first non-zero entry in row $i$ is strictly to the left of the
    first non-zero entry in row $i+1$

We say a matrix is in [**row reduced echelon
form**]{style="color: ForestGreen"} if it is in echelon form and:

-   The first non-zero entry in row $i$ appears in column $j$, then
    every other element in column $j$ is zero

## Elementary Matrices

**Definition 2.4.1**\
Any matrix that can be obtained from an identity matrix by means of one
elementary row operation is an [**elementary
matrix**]{style="color: ForestGreen"}\
\
There are three types of elementary matrix:

-   The general form of the elementary matrix which multiplies a row by
    any non-zero number, $\alpha$ is of the form $$E_r(\alpha) = 
        \left[
        \begin{array}{ccccc}
             1&\ldots&0&\ldots&0  \\
             \ldots&\ldots&\ldots&\ldots&\ldots  \\
             0&\ldots&\alpha&\ldots&0  \\
             \ldots&\ldots&\ldots&\ldots&\ldots  \\
             0&\ldots&0&\ldots&0  
        \end{array}
        \right]$$

-   The general form of the elementary matrix which adds a multiple of a
    row by any non-zero number $\alpha$ to another is of the form
    $$E_rs(\alpha) = 
        \left[
        \begin{array}{ccccccc}
             1&\ldots&0&\ldots&0&\ldots&0  \\
             \ldots&\ldots&\ldots&\ldots&\ldots&\ldots&\ldots \\
             0&\ldots&1&\ldots&\alpha&\ldots&0  \\
             \ldots&\ldots&\ldots&\ldots&\ldots&\ldots&\ldots  \\
             0&\ldots&0&\ldots&0&\ldots&0
        \end{array}
        \right]$$ where all elements of row s are multiplied by $\alpha$
    and added to row $r$

-   The general form of the elementary matrix which interchanges two
    rows is of the form $E_{rs}$ where r and s are the rows to
    interchange.[**I'm not typing out another bloody matrix fuck
    you**]{style="color: red"}

**Theorem 2.4.4**\
Let $A$ be a $m\times n$ matrix and let $E$ be an elementary
$m \times n$. The matrix multiplication $EA$ applies the same elementary
row operation on $A$ that was performed on the identity matrix to obtain
$E$

## More Matrices

**Definition 2.5.1**\
We say a matrix is square if it has the same number of rows as it does
columns(i.e, it's a member of $M_{n\times n}(\mathbb{F})$ for some field
$\mathbb{F}$)\
**Definition 2.5.2**\
A square matrix $A =a_{ij}\in M_{n\times n}(F)$ is said to be:

1.  [**upper triangular**]{style="color: ForestGreen"} if $a_{ij} = 0$
    wherever $i>j$. $A$ has zeros for all its elements below the
    diagonal

2.  [**lower triangular**]{style="color: ForestGreen"} if $a_{ij}=0$
    wherever $i<j$. $A$ has zeros for all its elements above the
    diagonal.

3.  [**diagonal**]{style="color: ForestGreen"} if $a_{ij}=0$ wherever
    $i\ne j$. This is to say $A$ has zeros for all its elemetns except
    those on the main diagonal.

**Definition 2.5.4**\
The $n\times n$ [**identity matrix**]{style="color: ForestGreen"} is
denoted by $I_n$. An identity matrix has all of its diagonal entries
equal to 1 and all other entries equal to 0. It is called the identity
matrix because it is the multiplicative identity for $n\times n$
matrices\
\
**Definition 2.5.5**\
If, for a square matrix $B$, if there exists another square matrix
$B^{-1}$ such that $BB^{-1}=I=B^{-1}B$, then we say that $B$ is
invertible and $B^{-1}$ **is an
[**inverse**]{style="color: ForestGreen"} of $B$**\
\
**Definition 2.5.6**\
A matrix without an inverse is called a
[**singular**]{style="color: ForestGreen"} matrix.\
\
**Theorem 2.5.8. The inverse of a given matrix is unique.**\
If $\exists A,B,C \in M_{n}(F)$ s.t $AB = I = CA \implies B = C$\
**Proof**\
Suppose that $AB=BA=I$ and $AC=CA=I$ then $$B=BI
=B(AC)
=(BA)C
=IC
=C$$ This theorem shows that if a matrix $A$ is invertible, we can talk
about the inverse of $A$, denoted by $A^{-1}$. In some circumstances, we
can say that a matrix is invertible, and we can find an expression for
its inverse without knowing exactly what the matrix is.\
**Definition 2.5.10.**\
If $A=[a_{ij}]_{m\times n }$ then the [**Transpose of
$A$**]{style="color: ForestGreen"} is $A^T=[a_{ij}]_{n\times m}$\
**Theorem 2.5.13**\
Given an invertible square matrix $A$, then $A^T$ is also invertible,
and $(A^T)^-1=(A^-1)^-T$\
**Proof**\
**From the definition of the inverse**

::: center
$AA^{-1} = I
(AA^{-1})^T=I^T
(A^{-1})^TA^T=I\
$\
Also\
\
$A^{-1}A=I
(A^{-1}A)^T=I^T
A^T(A^{-1})^T=I$
:::

Equation 8 and 8 prove that $(A^{-1})^T$ is the unique inverse of $A^T$,
as required

## Inverse Row Operations

**Theorem 2.6.1**\
Every elementary matrix is invertible and the inverse of also an
elementary matrix.\
**Proof**\
Matrix multiplication can be used to check that

::: center
$E_r(\alpha)E_r(\alpha^{-1}=E_r(\alpha ^{-1})E_r(\alpha)=I\\
    E_{rs}(\alpha)E_{rs}(\alpha ^{-1}=E_{rs}(\alpha ^{-1})E_{rs}(\alpha)=I\\
    E_{rs}(\alpha)E_{rs}(\alpha) = I\\
$
:::

Alternatively, the results can be checked by the corresponding
inverses.\

**Theorem 2.6.2**\
If the square matrix A an be row reduced to an identity matrix by a
sequence of elementary row operations, then $A$ is invertible and the
inverse of $A$ is found by applying the same sequence of elementary row
operations to $I$\
\
**Proof**\
Let A be a square matrix, then A can be row-reduced to I by a sequence
of elementary row operations. Let $E_1,E_2,\ldots,E_r$ be the elementary
matrices corresponding to the elementary row operation, so that

::: center
$E_r\ldots E_2E_1A=1$
:::

But Theorem 2.6.1 states that matrices representing elementary row
operations are invertible. Thus the above equation can be rearranged to
give

::: center
$A^{-1} = (E^{-1}_1E^{-1}_2 \ldots E^{-1}_r)^{-1}$\
$(E_r\ldots E_2E_1)I$
:::

## Geometric Interpretations

As you have seen in the introductory module, vectors in
$\mathbb{R}^2/\mathbb{R}^3$ can be represented as points in 2 or 4
dimensional space. In this section we will at geometric interpretations
of some of the things we have seen so far.\
\
A system of linear equations in n unknowns specifies a set in n-space\
**Definition 2.7.4**\
Let T be a function from $\mathbb{R}^n$ to $\mathbb{R}^m$ then we say
$T$ is a [**linear transformation**]{style="color: ForestGreen"} if for
every $\nu _1,\nu _2 \in \mathbb{R} ^n$ and every
$\alpha , \beta \in \mathbb{R}$ we have:

::: center
$T(\alpha \nu_1 + \beta \nu_2) = \alpha T(\nu _1) + \beta T(\nu_2)$
:::

\
**Proposition 2.7.4**\
Let $A \in M_{n\times m}(\mathbb{R})$ then it can be seen as a map from
$\mathbb{R}^n$ to $\mathbb{R}^m$. $A$ is a linear transformation.\
**Proof**

::: center
$A(\alpha \nu_1 + \beta \nu_2) = A(\alpha \nu_1) + A(\beta \nu_2)\\
    =\alpha A(\nu _1) + \beta A(\nu _2)$\
By distributivity of matrix multiplication
:::

\
**Proposition 2.7.5**\
Let $A \in M_{n\times m}(\mathbb{R})$. The following are equivalent:

1.  $A$ is invertible with inverse $A^-1=A^T$

2.  $A^TA=I_n=AA^T$

3.  A preserves inner products(i.e. for all
    $x,y \in = \mathbb{R}^n\\ (Px)\cdot(Py) = x\cdot y$)

\
**Proof:**\
(i) $\iff$ (ii) is just by definition\
(ii) $\iff$ (iii)\
First note that for $x,y \in \mathbb{R}^n$ $x\cdot y$ as defined in the
intro to maths course is just $x^Ty$ as a matrix multiplication. So $A$
preserves inner products if and only if: $$\begin{aligned}
    \end{aligned}$$

::: center
$(Px)\cdot (Py) = x \cdot y \forallx,y \in \mathbb{R}^n\\
\iff (Px)^T(Py) = x^Ty  \forallx,y \in \mathbb{R}^n\\
\iff x^TP^TPy = x^TI_ny  \forallx,y \in \mathbb{R}^n\\
\iff x^T(P^TP-I_n)y=0  \forallx,y \in \mathbb{R}^n$\
:::

\(ii\) $\implies$ (iii) now trivial (iii) $\implies$ (ii): Let $x_i$ =
$\left(
\begin{array}{}
      0\\
      \vdots\\
      1\\
      \vdots\\
      0
\end{array}
\right)$ i.e column vector with 0's everywhere except the $i^th$ row
where there is a 1. Then we know for each $x_i$ $(x_i)^T(P^TP-I_n)y=0$
so we can conclude that

::: center
$(P^TP-I_n)y=
    \left(
    \begin{array}{}
         0  \\
         \vdots \\
         0 
    \end{array}\right)$
:::

Similarly taking $y_i$ to be the column vector with 0's everywhere
except the $i^{th}$ row where there is a 1 we get $(P^TP-I_N) = 0$ so
$P^TP = I_n$

\
\
**Definition 2.7.6**\
A matrix $A \in M_{n \times n}$ is called
[**Orthogonal**]{style="color: ForestGreen"} if it is such that
$A^-1 = A^T$

## Fields

So far, for both matrices and linear equations we have only been using
entries in $\mathbb{R}$. However, we could have taken entries from any
field.\
Every field has distinguished elements $0$ - **(additive identity)** and
$1$ - **(multiplicative identity)**.\
**Theorem 2.8.3**\
Let $\mathbb{F}_p = {0,1,\ldots,p-1}$, consider $\mathbb{F}_p$ with
addition defined by addition modulo $p$ and multiplication as
multiplication modulo p. Then the structure
($\mathbb(F)_p, +_{\text{mod} p}, \times_{\text{mod} p}$ is a field)\
**Proof:**\
A 1-4 are obvious frop properties of addition in $\mathbb{Z}$\
M1-3 are obvious from properties of addition in $\mathbb{Z}$\
M4: inverse: obviously for $0\leq x < p$ we have $gcd(x,p) = 1$ by Intro
to Uni Maths we have:
$$\exists s,t \in \mathbb{Z}\text{ such that } 1 = sx + tp \text{ then take } x^{-1} = s (\text{mod } p)$$
D1 obvious from properties of addition in $\mathbb{Z}$

# Vector Spaces

## Introduction to Vector Spaces

::: defn
**Definition 2**.
:::

Let $\mathbb{Z}$ be a field. A **vector space** over $\mathbb{F}$ is a
non-empty set V together with the following maps:

1.  **Addition**

    ::: center
    $\oplus : V \times V \mapsto V$\
    $(\nu_1 , \nu_2) \mapsto \nu_1 \oplus \nu_2$
    :::

2.  **Scalar multiplication**

    ::: center
    $\odot :F \times V \mapsto V$\
    $(f,\nu_2) \mapsto f \odot \nu_2$
    :::

$\oplus$ and $\odot$ must satisfy and following Vector Space axioms:

::: multicols
2 **For Vector Addition:**

1.  *Associative law: $(u\oplus v)\oplus w = u\oplus (v \oplus w)$*

2.  *Commutative law*

3.  *Additive identity: $0_V \oplus v=v$*

4.  *Additive inverse*

**For Scalar Multiplication:**

5.  *Distributive law*

6.  *Distributive law v2*

7.  *Associative law*

8.  *Identity for scalar mult.*
:::

::: defn
**Definition 3**.
:::

Let $V$ be a vector space over $\mathbb{F}$:

-   Elements of $V$ are called vectors

-   Elements of $\mathbb{F}$ are called scalars

-   We sometimes refer to $V$ as an $\mathbb{F}$-vector space

## Subspaces

::: defn
**Definition 4**.
:::

A subset $W$ of a vector space $V$ is subspace of $V$ if

1.  $W$ is not empty(i.e $e \in W$)

2.  for $v,w \in W$, then $v\oplus w \in W$ closed under vector addition

3.  close under scalar multiplication.

**Remark 3.2.3**\
Any subspace of $V$ that is not $V$ or the zero vector space is called a
[**proper subspace**]{style="color: ForestGreen"} of V\
**Proposition 3.2.3.**\
Every subspace of an $F$-vector space $V$ must contain the zero vector\

::: thm
**Theorem 1**.
:::

Let $U,W$ be subspaces of $V$. Then $U \cap W$ is a subspace of $V$. In
general, the intersection of any set of subspaces of a vector space $V$
is a subspace of $V$.

## Spanning

::: defn
**Definition 5**.
:::

Let V be an $\mathbb{F}$-vector space. Let $u_1,\ldots,u_m \in$ V then:

::: center
-   A **Linear Combination** of $u_1,\ldots,u_m \in$ is a vector of the
    form $\alpha_1 u_1 + \ldots +\alpha_mu_m$ for scalars
    $\alpha_1,\ldots, \alpha_m \in \mathbb{F}$. Note we can also write
    $\alpha_1 u_1 + \ldots +\alpha_mu_m$ as $\sum^m_{i=1}\alpha_iu_1$

-   **span** of $u_1,\ldots,u_m \in$ is the set of linear combinations
    of $u_1,\ldots,u_m \in$
:::

\
**Lemma 3.3.2**\
Let $V$ be an $\mathbb{F}$ vector space, and $u_{1},\ldots,u_{m} \in V$
then Span($u_1,\ldots,u_m)$ is a subspace of $V$.

::: defn
**Definition 6**.
:::

Let $V$ an $\mathbb{F}$ vector space and suppose $S\subset V$ is such
that *Span($S$)* = $V$ then we say *$S$ spans $V$*, or equivalently $S$
is a *spanning set* set for

## Linear Independence

::: defn
**Definition 7**.
:::

Let $V$ an $\mathbb{F}$ vector space. We say $u_1,\ldots,u_m \in$ V are
*linearly independent* if whenever

::: center
$\alpha_1 u_1 + \ldots +\alpha_mu_m = 0_V$\
\
then it must be that\
\
$\alpha_1 = \cdots = \alpha_m = 0$
:::

We say $u_1,\ldots,u_m \in$ is a *linearly independent set*\
\
Alternatively, a set $u_1,\ldots,u_m \in$ is *linearly dependent* if
$\alpha_1 u_1 + \ldots +\alpha_mu_m = 0_V$ where at least one
$\alpha_i \neq 0$ and a set is linearly independent if it is not
linearly dependent.\
\
**Lemma 3.4.4** Let $_nu_1,\ldots,_nu_n$ be linearly independent in an
$\mathbb{F}$-vector space $V$. Let $v_{n+1}$ be such that
$_nu_{n+1} \notin$ *Span*($_nu_1.\ldots,_nu_n$). Then
$_nu_1.\ldots,_nu_{n+1}$ is linearly independent\
\

## Bases

::: defn
**Definition 8**.
:::

-   Let $V$ be and $\mathbb{F}$-vector space. A basis of $V$ is a
    linearly independent spanning set of $V$.

-   If $V$ has a finite basis then we say $V$ is a *finite dimensional*
    vector space

\
**Proposition 3.5.4** Let V be an $\mathbb{F}$-vector space, let
$S={u_1,\ldots,u_m \in}\subseteq V$ Then $S$ is a basis of $V$ $\iff$
every vector in $V$ has a unique expression as linear combination of
elements of $S$\
**Remark 3.5.5** Let B = ${u_1,\ldots,u_m \in}$ be a basis for an
$\mathbb{F}$-vector space V. By proposition 3.5.4 we see that we have a
bijective map $f$ from V to $\mathbb{F}^m$, for
$_nu = \alpha_1u_1 +\ldots +\alpha_mu_m$ we define
$f(_nu)=(\alpha_1,\ldots,\alpha_m)$ we ca;; $(\alpha_1,\ldots,\alpha_m)$
the coordinates of $_nu$\
**Proposition 3.5.6** Let $V$ be a non-trivial(i.e. not 0)
$\mathbb{F}$-Vector space and suppose $V$ has finite spanning set $S$
then $S$ contains a linearly independent spanning set.\
\

## Dimensions

**Lemma 3.6.1** *Steinitz Exchange Lemma*\
Let B be a vector space over $\mathbb{F}$. Take $X \subseteq V$ and
suppose $u \subseteq \textit{Span}(X)$ but $u \notin$ *Span*$(X\{_{nu})$
for some $_nu \in X$. Let $Y=(X\{_{nu}) \cup {u}$. Then *Span*(X) =
*Span*($Y$).\

::: thm
**Theorem 2**.
:::

Let $V$ be a finite dimensional vector space over $\mathbb{F}$. Let
$S,T$ be finite subsets of $V$. If $S$ is LI and $T$ spans $V$ then
$|S|\leq |T|$. That is, LI sets are at most big as spanning sets. The
proof is simple but the way char\* !\* writes it is absolutely
dogshirt.\

::: defn
**Definition 9**.
:::

$V$ a finite dimensional vector space.Let $S,T$ be bases of $V$ then $S$
and $T$ are both finite and $|S|=|T|$\
**Lemma 3.6.8** Suppose dim$V = n$:

1.  Any spanning set of size $n$ is a basis

2.  Any linearly independent set of size $n$ is a basis

3.  $S$ is a spanning set $\iff$ it contains a basis(as a subset)

4.  $S$ is linearly independent $\iff$ it is contained in a basis

5.  Any subset of $V$ of size $> n$ is linearly dependent

\

## More subspaces

::: defn
**Definition 10**.
:::

Let $V$ be a vector space $U$ and $W$ be subspace of $V$.

::: center
-   The *intersection* of U and W is:\
    $U \cap W = {\nu \in V : \nu \in W and _nu \in U}$

-   The *sum* of U and W is: $U +W={u + w:u \in U, W \in W}$
:::

**Proposition 3.7.5**\
Let $V$ be a vector space over $\mathbb{F}$. Let $U$ and $W$ be
subspaces of $V$, suppose additionally:

-   $U$ = Span$\{u_1,\ldots,u_s \}$

-   $W$ = Span$\{w_1,\ldots,w_r\}$

Then $U+W = Span\{ u_1.\ldots,u_s,w_1,\ldots,w_r \}$ Proof is ez\

::: thm
**Theorem 3**.
:::

Let $V$ be a vector space over $\mathbb{F}$, $U$ and $W$ subspaces of
$V$. Then

::: center
$\textit{dim}(U+W) = \textit{dim}U + \textit{dim}W - \textit{dim}(U\cup W)$
:::

## Rank of Matrix

::: defn
**Definition 11**.
:::

Let $A$ be an $m \times n$ matrix with entries from a field
$\mathbb{F}$. Define:\

::: center
-   The *Row Space* of $A$ $(RSp(A))$ as the span of of the rows of A.
    This is a subspace of $\mathbb{F}^{n}$

-   The Row Rank of $A$ is $dim(RSp(A))$

-   The Column Space of $A$ $(Csp(A))$ as the span of the columns of
    $A$. This is a subspace of $\mathbb{F}^m$

-   The Column Rank of $A$ is $\textit{dim}(CSp(A))$
:::

\

::: defn
**Definition 12**.
:::

For any matrix $A$ the row rank of $A$ is equal to the column rank of
$A$.

::: defn
**Definition 13**.
:::

Let $A$ be a matrix. The rank of $A$ written rank($A$) or $rk(A)$, is
the row rank of $A$\
**Proposition 3.8.11**\
Let $A$ be $n\times n$ matrix with entries in $\mathbb{F}$, then the
following statements are equivalent:

1.  rank($A$)=$n$

2.  The rows of $A$ form a basis for $\mathbb{F}^n$

3.  The columns of $A$ form a basis for $\mathbb{F}^n$

4.  $A$ is invertible

\

# Linear Transformation

::: defn
**Definition 14**.
:::

Suppose $V,W$ are vector spaces over a field $\mathbb{F}$. Let
$T: V \rightarrow W$ be a function from $V to W.$ we say:

-   $T$ preserves addition if for all $\nu_1, \nu_2 \in V$ we have
    $T(\nu_1+\nu_2) = T(\nu_1)+T(\nu_2)$

-   $T$ preserves *scalar multiplicaion* if for all $\nu \in V$,
    $\lambda \in \mathbb{F},T(\lambda\nu)=\lambdaT(\nu)$

-   $T$ is a *linear tranformation (or linear map)* if it:

    1.  preserves addition

    2.  preserves scalar multiplicaion

\
**Proposition 4.1.3.**\
Let $A$ be an $m\times n$ matrix over $\mathbb{F}$. Define
$T: \mathbb{F}^n \rightarrow \mathbb{F}^m$, by $T(\nu)=A\nu$\
**Proposition 4.1.4**\
*Basic Properties of linear transformations*\
Let $T:V\rightarrow W$ be a linear map. Write $0_V,0_W$ for the zero
vectors in $V$ and $W$ respectively, We have:

1.  $T(0_V) = 0_W$

2.  Suppose $\nu = \epsilon_1\nu_1+\ldots+\epsilon_k\nu_k$ for
    $\epsilon_i \in \mathbb{F},\nu_i\in V$. Then
    $T(\nu) = \lambda_1T(\nu_1)+\ldots+\lamda_kT(\nu_k)$

\
**Proposition 4.1.6**\
Let $V$ and $W$ be vector spaces over $\mathbb{F}$. Let
$\nu_1,\ldots,\nu_n$ be a basis for $V$. Let $w_{1},\ldots,w_n$ be any
$n$ vectors from $W$ (not necessarily distinct). Then this is a unique
linear transformation $T:V\to W$ such that $T(\nu_i)=w_i$ for all $i$.\
**Remark 4.1.7**\
This shows that once we know what a linear transformations does to a
basis we know what the transformation is.

## Image and Kernel

::: defn
**Definition 15**.
:::

Let $T:V\rightarrow W$ be a linear transformation:

-   The *Image of T* is the set $ImT$
    $={T(\nu) \in W : \nu \in V} \subseteq W$

-   The *Kernel of T* is the set *KerT*
    $= {\nu \in V :T(\nu)=0_W} \subseteq V$

\
**Proposition 4.2.3**\
Let $T:V\to W$ be a linear transformation. Then:

1.  $ImT$ is a subspace of W

2.  $KerT$ is a subspace of W

\
**Proposition 4.2.5**\
Let $T:V\rightarrow W$ to be a linear transformation and let
$\nu_1,\nu_2 \in V$. Then

::: center
$T(\nu_1) = T(\nu_2) \iff \nu_1 - \nu_2 \in KerT$
:::

\
**Proposition 4.2.6**\
Let $T:V\rightarrow W$ be a linear transformation. Suppose that
$\nu_1,\ldots,\nu_n$ is a basis for V. Then
$ImT=Span{T(\nu_1),\ldots,T(\nu _n)}$\
**Proposition 4.2.7**\
Let $A$ be an $m \times n$o matrix. Let
$\mathbb{F}^n \rightarrow \mathbb{F}^m$ be given by $T(\nu) = A\nu$.
Then:

1.  *Ker$T$* is the solution space to $A\nu = 0$

2.  *Im$T$* is the column space of $A$

3.  *dim(Im$T$)* = *rank$A$*

\

::: thm
**Theorem 4**.
:::

*The Rank Nullity theorem* *Let $T:V\rightarrow W$ be a linear
tranformation. Then*

::: center
$dim(ImT)+dim(KerT)=dim(V)$
:::

\
**Corollary 4.2.10**\
A system of linear equations in n unknowns with co-efficients in
$\mathbb{F}$:

## Representing vectors and transformations with respect to a basis

\
**Definition 4.3.1**\
For $\nu \in V$ with $\nu = \epsilion_1\nu_1+\ldots+\lambda_n\nu_n$ the
vector of $V$ wrt $B$ is\

::: center
$[\nu]_B=
\left[ 
\begin{array}{}
     \lambda_1\\
     \vdots \\
     \lambda_n
\end{array}
\right]$
:::

\
**Proposition 4.3.3** Let $V$ be an $n$-dimensional vector space
over$\mathbb{F}$ with a basis $B$. Then the map:

::: center
$T:V\rightarrow \mathbb{F}^n\\
    T(\nu) = [\nu]_B$
:::

is a bijective linear transformation\
\

::: defn
**Definition 16**.
:::

The Matrix A constructed to map $\mathbb{F}^n \rightarrow \mathbb{F}^m$
is the matrix of T with respect to B and Cm we wrute this
$_{c}T_B[\nu]_B = [T\nu]_C$. If $V=W$ and $B=C$ we sometimes write this
simple as $[T]_B$\
\
**Proposition 4.3.8** Let $V$ be a vector space. Let
$B={\nu_1,\ldots,\nu_n}$ and $C={w_1,\ldots,w_n}$ be bases for V. Then
for $j \in {1,\ldots, n}$ we can write
$\nu_j=\lambda_{ij}+\ldots+\lambda_{nj}w_n$

Let P be the matrix $(\lambda_{ij}) =$ $\left [
\begin{array}{ccc}
     \lambda_{11}&\ldots&\lambda_{1n}  \\
     \vdots&&\vdots  \\
     \lambda_{n1}&\ldots&\lambda_{nn}
\end{array}
\right]$

So the $j^{th}$ column is $[\nu_j]_C$.

1.  $P=[X]_C$ where $X:V\rightarrow V$ is the unique linear
    transformation such that $X(w_j) = \nu_j$ for all $j$

2.  For all $\nu \in V, P[\nu]_B=[\nu_j]_C$

3.  $P = _C[Id]_B$ where $Id$ is the identity transformation of V

\

::: defn
**Definition 17**.
:::

P is the change of basis matrix from B to C.\
\
***WARNING*. THIS IS CONFUSING BECAUSE OF 1 IN PROPOSITION 4.3.8 maps
basis elements to C to those of B- sometimes described the other way
around**\
\
**Proposition 4.3.10**\
Let $V,B,C,P$ as above. Then:

1.  $P$ is invertible, and its inverse is the change of the basis matrix
    from $C$ to $B$

2.  $T:V\rightarrow V$ be a linear transformation, Then
    $[T]_C=P[T]_BP^{-1}$

**Remark. 4.3.12**\
It is a fact that if $P$ is the change of basis matrix $_C[Id]_B$ from
$B$ to $C$ amd $Q$ is the change of basis matrix $_D[Id]_C$(where
$B$,$C$,$D$ and all basis for $\mathbb{F}^n$ then
$QP=_D[Id]_C_C[Id]_B=_D[Id]_B$, the change of basis matrix from $B$ t
$D$.\
This gives us a quick method of calculating change of basis matrices for
$\mathbb{F}^n$
