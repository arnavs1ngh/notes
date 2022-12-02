---
layout: default
title: Maths Logic
parent: Year 3
nav_order: 2
math: mathjax3
---

# Mathematical Logic - Concise Notes
{: .no_toc }
## MATH60132
{: .no_toc}

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
  
- <a href="/notes/pdfs/year3/LecNotes/ML-Concise.pdf" target="_blank" style="color:#801fff;">**Open Maths Logic Concise - Incomplete**</a> - <a href="/notes/pdfs/year3/LecNotes/ML-Concise.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets</span>
  </summary>
  
  - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS1.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 1**</a> - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS1-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS2.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 2**</a> - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS2-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS3.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 3**</a> - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS3-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS4.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 4**</a> - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS4-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS5.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 5**</a> - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS5-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS6.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 6**</a> - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS6-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS7.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 7**</a> - <a href="/notes/pdfs/year3/probSheets/ml/ML-PS7-Sol.pdf" target="_blank">**Solutions**</a>

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

# Propositional Logic

## Propositional formula


**Definition 1**. *Proposition - a statement, either **True (T), (1)**
or **False (F), (0)**, represented using **propositional variables**\
Connectives and Truth Tables\
For $\{p, \ldots  , q\}$ a set of propositions, combine them using the
following connectives*

1.  ***Negation** $(\neg  p)$*

2.  ***Conjunction** $(p \wedge q)$*

3.  ***Disjunction** $(p \vee q)$*

4.  ***Implication** $p \to q$*

5.  ***Biconditional** $p \leftrightarrow q$*


| $p$ | $q$ | $p \wedge q$ | $p \vee q$ | $p \to q$ | $p \leftrightarrow q$ |
|:---:|:---:|:------------:|:----------:|:---------:|:---------------------:|
|  0  |  0  |       0      |      0     |     0     |           1           |
|  0  |  1  |       0      |      1     |     1     |           0           |
|  1  |  0  |       0      |      0     |     1     |           0           |
|  1  |  1  |       1      |      0     |     1     |           1           |


**Definition 2**. *A **propositional formula** is obtained in the
following way*

-   *Any propositional variable a formula*

-   If $\phi , \psi$ are formulas then so are

    $$(\neg  \phi ),\ (\phi \vee \psi ),\ (\phi \wedge \psi ),\ (\phi  \to \psi ),\ (\phi \leftrightarrow \psi )$$

-   *Any formula arises this way*



**Definition 3**. *Let $n \in \mathbb{N}$*

-   *A **truth function** of $n$ variables a function
    $f:\{T,F\}^n \to \{T,F\}$*

-   Suppose $\phi$ a formula with variables amongst
    $p_1, \ldots  , p_{n}$ 
    
    $$F_\phi : \{T,F\}^n \to \{T,F\}$$ 
    
    whose values at $\begin{pmatrix} x_1, \ldots ,x_n \end{pmatrix}$ is the
    truth value of $\phi$ when $p_{i}$ has value $x_{i}$ for
    $i = 1, \ldots  ,n$\
    $F_\phi$ the **truth function** of $\phi$*



**Definition 4**. *We have the following*

-   *A propositional formula $\phi$ a **tautology** if its truth
    function $F_\phi$ always has value T*

-   *Say $\phi ,\psi$ are **logically equivalent (LE)** if they have the
    same truth function, $(F_\phi  = F_\psi )$*



**Lemma 5**. *There are $2^{2^n}$ truth functions of $n$ variables*



**Definition 6**. *Say a set of connectives is **adequate** if for every
$n \geq  1$, every truth function of $n$ variables is the truth function
of some formula involving only connectives from the set and variables
$p1, \ldots  ,p_{n}$*



**Theorem 7**. *Set $\{\neg ,\vee ,\wedge \}$ is adequate*



**Corollary 8**. *Suppose $\chi$ a formula whose truth function not
always F. Then $\chi$ logically equivalent to formula in disjunctive
normal form.*



**Corollary 9**. *The following set of connectives are adequate*

-   *$\{\neg ,\vee \}$*

-   *$\{\neg, \wedge \}$*

-   *$\neg , \to$*

*We also have the **(NOR)** connective $\{\downarrow\}$ is adequate*

| $p$ | $q$ | $p \downarrow q$ |
|---|---|---|
| T | T | F |
| T | F | F |
| F | T | F |
| F | F | T |

## A formal system for propositional logic


**Definition 10**.

-   *A **formal deduction system** $\Sigma$ has the following*

    -   *An alphabet $A \neq \varnothing$ of symbols*

    -   *A non-empty set $\mathcal{F}$ of the set of all
        finite sequence, **strings**, of elements of $A$ the
        **formulas** of $\Sigma$*

    -   *A subset
        $\mathcal{A} \subseteq \mathcal{F}$
        called the **axioms** of $\Sigma$*

    -   *A collection of **deduction rules***

-   *A **proof** in $\Sigma$ a finite sequence of formulas in
    $\mathcal{F}$ $\phi_1, \ldots  , \phi_{n}$ such that
    each $\phi_i$ either an axiom, or obtained from
    $\phi_1, \ldots  ,\phi_{i-1}$ using one of the deduction rules.*

-   *The last, or any, formula in a proof a **theorem** of $\Sigma$.
    Write $\vdash_\Sigma \phi$.*



**Definition 11**. *The formal system $\mathcal{L}$ for
propositional logic has the following*

-   *A **Alphabet** consisting of*

    -   *variables, $p_1, \ldots  , p_{n}$*

    -   *connective, $\{\neg ,\to\}$*

    -   *punctuation, $), ($*

-   *Formulas: finite strings of symbols from alphabet as follows*

    -   *any variable $p_{i}$ a formula*

    -   *if $\phi , \psi$ formulas then so are $(\neg \pi )$ and
        $()\phi \to \psi )$*

    -   *Any formula arises this way*

-   *Axioms, suppose $\phi ,\psi ,\chi$ are L-formulas. We have the
    following axioms for $\mathcal{L}$*

    -   *$(\phi \to (\psi \to \phi ))$*

    -   *$((\phi \to( \psi \to \chi)) \to ((\phi \to \psi ) \to (\phi \to \chi )))$*

    -   *$(((\neg \psi ) \to (\neg \phi )) \to (\phi \to \psi ))$*

-   *Deduction rule*

    -   ***Modus Ponens**. From $\phi$ and $(\phi \to \psi )$, deduce
        $\psi$*



**Definition 12**. *Suppose $\Gamma$ a set of L-formulas*

-   *A **deduction** from $\Gamma$ a finite sequence of L-formulas
    $\phi_1, \ldots  , \phi_{n}$ s.t each $\phi_i$ either an axiom, a
    formula in $\Gamma$ or obtained from previous formulas via MP*

-   *Write $\Gamma \vdash_L \phi$ if there is a deduction from $\Gamma$
    ending in $\phi$. Say $\phi$ a **consequence** of $\Gamma$.\
    $\varnothing \vdash_L \phi$ same as $\vdash_L \phi$*



**Theorem 13**. *(Deduction Theorem)\
Suppose $\Gamma$ a set of L-formulas and $\phi ,\psi$ L-formulas.\
Suppose $\Gamma  \cup \{\phi \} \vdash_L \psi$ then
$\Gamma \vdash_L (\phi \to \psi )$*



**Corollary 14**. *(Hypothetical syllogism)\
Suppose $\phi ,\psi ,\chi$ L-formulas, and $\vdash_{L} (\phi \to \psi)$
and $\vdash_{L} (\psi \to \chi )$ Then $\vdash_{L} (\phi \to \chi )$*



**Proposition 15**. *Suppose $\phi ,\psi$ are L-formulas. Then*

1.  *$\vdash_{L} ((\neg  \phi ) \to (\psi \to \phi ))$*

2.  *$\{(\neg \psi) ,\psi \} \vdash_{L} \phi$*

3.  *$\vdash_{L} (((\neg \phi ) \to \phi ) \to \phi )$*


## Soundness and completeness of L


**Theorem 16**. *(Soundness of L)\
Suppose $\phi$ a theorem of L. Then $\phi$ a tautology*



**Definition 17**. *A **propositional valuation** $v$ an assignment of
truth values to the propositional variables $p_1, \ldots  , p_{n}$ So

$$v(p_{i}) = T,F \quad i \in \mathbb{N}$$



**Theorem 18**. *(Generalisation of Soundness)\
Suppose $\Gamma$ a set of formulas and $\phi$ a formula with
$\Gamma \vdash_{L} \phi$ Suppose $v$ a valuation with
$v(\psi ) = T, \forall \psi \in \Gamma$ Then $v(\phi ) = T$*



**Theorem 19**. *(Completeness (adequacy) of L)\
Suppose $\phi$ a tautology, i.e. $v(\phi ) = T, \forall v$. Then
$\vdash_{L} \phi$*



**Definition 20**. *A set $\Gamma$ of L-formulas is **consistent** if
there is no L-formula $\phi$ such that $\Gamma \vdash_{L} \phi$ and
$\Gamma \vdash_{L} (\neg  \phi )$*



**Proposition 21**. *Suppose $\Gamma$ a consistent set of L-formulas and
$\Gamma \not \vdash_{L} \phi$ Then $\Gamma \cup \{(\neg \phi )\}$ is
consistent*



**Proposition 22**. *(Lindenbaum Lemma)\
Suppose $\Gamma$ a set of L-formulas. Then there is a consistent set of
formulas $\Gamma^{\ast} \supseteq \Gamma$ s.t for every $\phi$ either
$\Gamma^{\ast} \vdash_{L} \phi$ or
$\Gamma^{\ast} \vdash_{L} (\neg \phi )$. Say $\Gamma^{\ast}$ is
**complete***



**Lemma 23**. *Let $\Gamma^{\ast}$ as above. Then $\exists$ valuation
$v$ s.t for every L-formula $\phi$, $v(\phi ) = T$ iff
$\Gamma^{\ast} \vdash_{L} \phi$*



**Corollary 24**. *Suppose $\Delta$ a consistent set of L-formulas, and
$\Delta \not \vdash_{L} \phi$ Then there is a valuation $v$ s.t
$v(\Delta ) = T$ and $v(\phi ) = F$*



**Corollary 25**. *Suppose $\Delta$ a set of L-formulas and $\phi$ an
L-formula. Then*

1.  *$\Delta$ consistent iff there is a valuation $v$ with
    $v(\Delta ) = T$, and*

2.  *$\Delta \vdash_{L} \phi$ iff, for every valuation $v$ with
    $v(\Delta ) = T$, we have $v(\phi ) = T$*



**Theorem 26**. *(Compactness theorem for L)\
Suppose $\Delta$ a set of L-formulas. The following are equivalent*

1.  *There is a valuation $v$ s.t $v(\Delta ) = T$*

2.  *For every finite subset $\Delta_0 \subseteq \Delta$, there is a
    valuation $w$ s.t $w(\Delta_0) = T$*


# Predicate Logic

## Structures


**Definition 27**. *Suppose $A$ a set and $n \in \mathbb{N}_{\geq 1}$*

-   *An **$n$-ary** relation on $A$ a subset

    $$\overline{R} \subseteq A^n = \{\begin{pmatrix} a_1, \ldots ,a_n \end{pmatrix} \mid a_{i}\in A\}$$

-   *An **$n$-ary** function on $A$ a function

    $$\overline{f} : A^n \to A$$



**Definition 28**. *A **first-order structure**
$\mathcal{A}$ consists of*

-   *A non-empty set $A$, the domain of $\mathcal{A}$*

-   *A set of relations on $A$

    $$\{\overline{R}_{i}\subseteq A^{n_{i}} \mid  i \in I\}$$

-   *A set of functions on $A$

    $$\{\overline{f}_{j}: A^{m_{j}} \to A \mid j \in J\}$$

-   *A set of constants, elements of $A$

    $$\{\overline{c}_{k}\mid  k \in K\}$$
    
    $I,J,K$ simply indexing sets, which can be empty*

*$$(n_{i} \mid  i \in I),\ (m_{j} \mid  j \in J),\ K$$

called the **signature** of $\mathcal{A}$\
Denote the structure by 

$$\begin{aligned}
        \mathcal{A}  &= \left< A; (\overline{R}_{i} \mid  i \in I), (\overline{f}_{j} \mid  j \in J), (\overline{c}_{k}\mid  k \in K) \right>\\
        &= \left< \text{domain; relations, functions, constants}  \right> 
    \end{aligned}$$


## First-order languages


**Definition 29**. *A **first-order-language**
$\mathcal{L}$ has an alphabet of symbols of the
following types*

  <!-- ------------------------ --------------------- ---------
        *Variables*               *$x_0$*         *$x_1$*
       *Connectives*             *$\neg$*         *$\to$*
       *Punctuation*             *$(\ )$*           *,*
      ***Quantifier***          *$\forall$*      
   ***Relation symbols***   *$R_{i},\ i \in I$*  
   ***Function symbols***    *$f_{j},j \in J$*   
   ***Constant symbols***   *$c_{k}, k \in K$*   
  ------------------------ --------------------- --------- -->

$$ \begin{aligned}
\text{Variables}\quad & x_0 & x_1\\
\text{Connectives}\quad & \neg & \to\\
\text{Punctuation}\quad & ( \ ) & ,\\
\textbf{Quantifier}\quad & \forall\\
\textbf{Relation Symbols}\quad & R_i & i \in I\\
\textbf{Function Symbols}\quad & f_j & j \in J\\
\textbf{Constant Symbols}\quad & c_k & k \in K
\end{aligned}$$

*$I,J,K$ indexing sets, which could have $J,K = \varnothing$*

-   *Each $R_{i}$ comes equipped with arity $n_{i}$*

-   *Each $f_{j}$ comes equipped with arity $m_{j}$*

*$$(n_{i} \mid  i \in I) \quad (m_{j} \mid  j \in J), \quad K$$

Above called the **signature** of $\mathcal{L}$*



**Definition 30**. *A **term** of $\mathcal{L}$ defined
as follows*

-   *Any variable is a term*

-   *Any constant symbol is a term*

-   *If $f$ an $m$-ary function symbol of $\mathcal{L}$
    and $t_1, \ldots  , t_{m}$ are terms then

    $$f(t_1, \ldots  , t_{m})$$ 
    
    also a term

-   *Any term arises this way*



**Definition 31**. *Use previous notation*

-   *An **atomic formula** of $\mathcal{L}$ is of the
    form 
    
    $$R(t_1, \ldots  , t_{n})$$ 
    
    Where $R$ an $n$-ary relation symbol of $\mathcal{L}$ and $t_1, \ldots  , t_{n}$
    are terms*

-   *Formulas of $\mathcal{L}$ are defined as follows*

    -   *Any atomic formula is a formula*

    -   *If $\phi ,\psi$ are L-formulas, then

        $$(\neg \phi ),\ (\phi  \to \psi ),\ (\forall x)\phi$$
        
        are L-formulas, where $x$ is any variable*

    -   *Every L-formula arises in this way*



**Definition 32**. *Suppose $\phi ,\psi$ are L-formulas*

-   *$(\exists x) \phi$ means $(\neg (\forall x)(\neg \phi ))$*

-   *$(\phi \vee  \psi )$ means $((\neg \phi ) \to \psi )$*



**Definition 33**. *(Interpretation)\
Suppose $\mathcal{L}$ a first-order-language with
relation symbols, $R_{i}$ of arity $n_{i}, i \in I$, functions symbols
$f_{j}$ of arity $m_{j}, j \in J$ and constant symbols $c_{k}, k\in K$\
An **$\mathcal{L}$-structure** is a structure

$$\mathcal{A} = \left< A; (\overline{R}_{i}\mid  i \in I), (\overline{f}_{j} \mid  j \in J), (\overline{c}_{k}\mid k\in K) \right>$$

of the same signature as $\mathcal{L}$\
The correspondence

$$R_{i} \leftrightsquigarrow \overline{R_{i}}, \quad f_{j} \leftrightsquigarrow \overline{f_{j}}, \quad c_{k} \leftrightsquigarrow \overline{c_{k}}$$

called an **interpretation** of $\mathcal{L}$*



**Definition 34**. *(Valuation)\
With the same notation, suppose $\mathcal{A}$ an
$\mathcal{L}$-structure. A valuation in
$\mathcal{A}$ is a function $v$ from the set of terms of
$\mathcal{L}$ to $A$ satisfying*

-   *$v(c_{k}) = \overline{c_{k}}$*

-   *if $t_1, \ldots  , t_{m}$ are terms of
    $\mathcal{L}$ and $f$ a $m$-ary function symbol then

    $$v(f(t_1, \ldots  , t_{m})) = \overline{f} (v(t_1),\ldots  ,v(t_{m})),$$

    where $\overline{f}$ an interpretation of $f$ in
    $\mathcal{A}$*



**Lemma 35**. *Suppose $\mathcal{A}$ an
$\mathcal{L}$-structure and $a_0,a_1, \ldots \in A$.
Then there is a unique valuation $v$ in $\mathcal{A}$
with $v(x_{l}) = a_{l}, \forall l \in \mathbb{N}$ where variables of
$\mathcal{L}$ are $x_0,x_1, \ldots$*



**Definition 36**. *Suppose $\mathcal{A}$ an
$\mathcal{L}$-structure and $x_{l}$ any variable.
Suppose $v,w$ are valuations in $\mathcal{A}$. Say $v,w$
are **$x_{l}$-equivalent** if $v(x_{m}) = w(x_{m}),$ whenever
$m \neq l$*



**Definition 37**. *Suppose $\mathcal{A}$ an
$\mathcal{L}$-structure and $v$ a valuation in
$\mathcal{A}$\
Define for an $\mathcal{L}$-formula $\phi$ what is meant
by $v$ satisfies $\phi$ in $\mathcal{A}$*

-   *Atomic formulas. Suppose $R$ an $n-$ary relation symbol and
    $t_1, \ldots  ,t_{n}$ are terms of $\mathcal{L}$
    Then

    $$v \text{ satisfies the atomic formula } R(t_1, \ldots , t_{n}) \iff \overline{R} (v(t_1),\ldots ,v(t_{n}) ) \text{ holds in } \mathcal{A}$$

-   *Suppose $\phi ,\psi$ are $\mathcal{L}$-formulas

    $$\begin{aligned}
                v \text{ satisfies } (\neg A) \text{ in } \mathcal{A} &\iff v \text{ does not satisfy } \phi \text{ in } \mathcal{A} \\
                v \text{ satisfies } (\phi \to \psi ) \text{ in } \mathcal{A} &\iff \text{it is not the case that } v \text{ satisfies } \phi \text{ in } \mathcal{A} \text{ and } v \text{ does not satisfy } \psi \text{ in } \mathcal{A}\\
                v \text{ satisfies } (\forall x_{l})\phi \text{ in } \mathcal{A}  &\iff \text{whenever } w \text{ a valuation in }  \mathcal{A} \text{which is } x_{l}-\text{equivalent to } v \text{, then } w \text{ satisfies } \phi \text{ in } \mathcal{A} 
            \end{aligned}$$


**Notation:**\
If $v$ satisfies $\phi$ write $v[\phi ] = T$ if not write
$v[\phi ] = F$\
If every valuation in $\mathcal{A}$ satisfies $\phi$ say
that $\phi$ is **true** in $\mathcal{A}$ or
$\mathcal{A}$ a model of $\phi$\
Write $A \models \phi$, if $\mathcal{A} \models \phi$
for every $\mathcal{L}$-structure
$\mathcal{A}$ say that $\phi$ is **logically valid**,
and write $\models \phi$


**Definition 38**. *Suppose $\chi$ an
$\mathcal{L}$-formula involving propositional variables
$p_1, \ldots  ,p_{n}$. Suppose $\mathcal{L}$ a
first-order language and $\phi_1, \ldots , \phi_{n}$ are
$\mathcal{L}$-formulas.\
A **substitution instance** of $\chi$ is obtained by replacing each
$p_{i}$ in $\chi$ by $\phi_i$. Call the result $\theta$*



**Theorem 39**. *We have*

-   *$\theta$ an $\mathcal{L}$-formula, and*

-   *if $\chi$ a tautology, then $\theta$ is logically valid*

***Note:** not all logically valid formulas arise this way*


## Bound and free variables in formula


**Definition 40**. *Suppose $\phi , \psi$ are
$\mathcal{L}$-formulas, with $(\forall x_{i}) \phi$
occurring as a sub-formula of $\psi$*

-   *Say $\phi$ the **scope** of a that quantifier $(\forall x_{i})$
    here in $\psi$\
    An occurrence of a variable $x_{j}$ in $\psi$ is **bound** if it is
    in the scope of a quantifier $(\forall x_{j})$ in $\psi$ or it is
    the $x_{j}$ here in $(\forall x_{j})$*

-   *Otherwise, it is a **free** occurrence of $x_{j}$. Variables having
    a free occurrence in $\psi$ are called **free variables** of $\psi$*

-   *A formula with no free variables called a **closed formula** or a
    **sentence**, of $\mathcal{L}$*



**Definition 41**. *If $\psi$ an $\mathcal{L}$-formula
with free variables amongst $x_1, \ldots   , x_{n}$, might write

$$\psi (x_1, \ldots  ,x_{n})$$

instead of $\psi$. If $t_1, \ldots  ,t_{n}$ are terms, by 

$$\psi (t_1, \ldots  ,t_{n})$$

we denote the $\mathcal{L}$-formula obtained by replacing
each free occurrence of $x_{i}$ in $\psi$ by $t_{i}$*



**Theorem 42**. *Suppose $\phi$ closed
$\mathcal{L}$-formula and $\mathcal{A}$
an $\mathcal{L}$-structure. Then either $A \models \phi$
or $A \models (\neg \phi )$.\
More generally if $\phi$ has free variables amongst
$x_1, \ldots  , x_{n}$ and $v,w$ valuations in
$\mathcal{A}$ with

$$v(x_{i}) = w(x_{i}),\quad i =1, \ldots  ,n$$

Then $v[\phi ] = T \iff w[\phi ] =T$. Allow $n = 0,$ for no free variables*



**Remark 43**. *If $\mathcal{A}$ an
$\mathcal{L}$-structure and $\psi (x_1, \ldots  ,x_{n})$
an $\mathcal{L}$-formula, whose free variables are
amongst $x_1, \ldots  ,x_{n}$ and $a_1, \ldots  ,a_{n} \in A$ for domain
$A$,then we write 

$$A \models \psi (a_1, \ldots  ,a_{n})$$

to mean $v[\psi ] = T$ for every valuation $v$ in $\mathcal{A}$
with 

$$v(x_{i}) = a_{i}, \quad i = 1, \ldots  ,n$$



**Definition 44**. *Let $\phi$ an $\mathcal{L}$-formula,
$x_{i}$ a variable, $t$ an $\mathcal{L}$-term.\
Say that $t$ is **free for $x_{i}$** in $\phi$ if there is no variable
$x_{j}$ in $t$ s.t $x_{i}$ has a free occurrence within the scope of a
quantifier $(\forall x_{j})$ in $\phi$*



**Theorem 45**. *Suppose $\phi (x_1)$ an
$\mathcal{L}$-formula, possibly with other free
variables. Let $t$ be a term free for $x_1$ in $\phi$, then

$$\models ((\forall x_1)\phi (x_1) \to \phi (t))$$

In particular, if $\mathcal{A}$ an
$\mathcal{L}$-structure, with
$\mathcal{A} \models (\forall x_{1} \phi (x_1), )$ then
$A \models \phi (t)$*



**Lemma 46**. *Suppose $v$ a valuation in $\mathcal{A}$.
Let $v^\prime$ be the valuation in $\mathcal{A}$ which
is $x_1-$equivalent to $v$ with $v^\prime (x_1) = v(t)$. Then
$v^\prime [\phi (x_1)] = T \iff v[\phi (t)] = T$*


## The formal system $K_{\mathcal{L}}$ 


**Definition 47**. *Suppose $\mathcal{L}$ a first-order
language. The formal system $K_{\mathcal{L} }$ has, as
formulas, $\mathcal{L}$-formulas, and the following*

-   *Axioms. For L-formulas, $\phi ,\psi ,\chi$*

-   *$(\phi \to (\psi \to \phi ))$*

-   *$((\phi \to( \psi \to \chi)) \to ((\phi \to \psi ) \to (\phi \to \chi )))$*

-   *$(((\neg \psi ) \to (\neg \phi )) \to (\phi \to \psi ))$\
    *

-   *$((\forall x_{i})\phi (x_{i}) \to \phi (t))$, where $t$ a term free
    for $x_{i}$ in $\phi$ and $\phi$ can have other free variables*

-   *$((\forall x_{i})(\phi \to \psi) \to (\phi \to (\forall x_{i})\psi ))$,
    if $x_{i}$ is not free in $\phi$*

-   *Deduction rules:*

-   *Modus Ponens. From $\phi$ and $\phi \to \psi$, deduce $\psi$*

-   ***Generalisation**. From $\phi$, deduce $(\forall x_{i})\phi$*

*A **proof** in $K_{\mathcal{L} }$ a finite sequence of
$\mathcal{L}$-formulas, each of which an axiom or
deduced from previous formulas in proof using a deduction rule.\
A **theorem** of $K_{\mathcal{L} }$ the last (or any)
formula in some proof.\
Write: $\vdash_{K_{\mathcal{L} } }$ if $\phi$ a theorem
in $K_{\mathcal{L} }$*



**Definition 48**. *Suppose $\Sigma$ a set of
$\mathcal{L}$-formulas and $\psi$ an
$\mathcal{L}$-formula. A **deduction** of $\psi$ from
$\Sigma$ a finite sequence of formulas, ending with $\psi$,each of which
is one of*

-   *an axiom*

-   *a formula in $\Sigma$*

-   *obtained from earlier formulas using a deduction rule, with
    restriction that when Gen applied, it does not involve a variable
    occurring freely in $\Sigma$*

*Write $\Sigma \vdash_{K_{\mathcal{L} } } \psi$ if there
is a deduction from $\Sigma$ to $\psi$*



**Remark 49**. *We have*

-   *if $\Sigma$ consists of closed formulas, do not need to worry about
    the restriction on Gen*

-   *$\phi \vdash_{K_{\mathcal{L} } } \psi$ if there is
    a deduction from $\Sigma$ to $\psi$*

-   *Without the restriction would have
    $$\{\phi \} \vdash (\forall x_{i}) \phi , \text{ not sensible}$$

-   *Should have, if $\Sigma^\prime \subseteq \Sigma$ and
    $\Sigma^\prime  \vdash \phi \implies \Sigma \vdash \phi$, So we
    modify the definition accordingly*



**Theorem 50**. *Suppose $\phi$ an
$\mathcal{L}$-formula, which is a substitution instance
of a propositional tautology $\chi$, then

$$\vdash_{K_{\mathcal{L} } } \phi$$



**Theorem 51**. *(Soundness of $K_{\mathcal{L} }$ )\
If $\vdash_{K_{\mathcal{L} } } \phi$, then
$\models \phi$, that is it is logically valid*



**Corollary 52**. *(Consistency of $K_{\mathcal{L} }$ )\
There is no formula, $\phi$, with
$\vdash_{K_{\mathcal{L} } } \phi$ and
$\vdash_{K_{\mathcal{L} } } (\neg \phi)$*



**Theorem 53**. *(Deduction theorem)\
Supposed $\mathcal{L}$ a first-order language, $\Sigma$
a set of $\mathcal{L}$-formulas, and $\phi ,\psi$ are
$\mathcal{L}$-formulas.\
Then if
$\Sigma  \cup \{\phi\} \vdash_{K_{\mathcal{L}}} \psi \implies \Sigma \vdash_{K_{\mathcal{L}}} (\phi \to \psi )$*


## Gödel's completeness theorem


**Definition 54**. *A set $\Sigma$ of
$\mathcal{L}$-formulas is **consistent** if there is no
formula $\phi$ with

$$\Sigma \vdash_{K_{\mathcal{L} } } \phi , \quad \Sigma \vdash_{K_{\mathcal{L} } } (\neg \phi )$$

By Soundness/ 2.4.7, $\varnothing$ is consistent so
$K_{\mathcal{L} }$ is consistent*



**Remark 55**. *If $\Sigma$ inconsistent, then

$$\Sigma \vdash_{K_{\mathcal{L} } } \chi,\quad \forall \text{ L-formula } \chi$$



**Proposition 56**. *Suppose $\Sigma$ a consistent set of closed
L-formulas and $\phi$ a closed L-formula.*

1.  *Comparing 1.3.7, if
    $\Sigma \not \vdash_{K_{\mathcal{L}}} \phi$, then
    $\Sigma  \cup \{(\neg \phi )\}$ is consistent*

2.  *Comparing the Lindenbaum lemma (1.3.8), there is a consistent set
    $\Sigma^{\ast} \supseteq \Sigma$ of closed L-formulas such that for
    every closed L-formula $\phi$, either
    $\Sigma^{\ast} \vdash_{K_{\mathcal{L}}} \psi$ or
    $\Sigma^{\ast}  \vdash_{K_{\mathcal{L}}} (\neg \phi )$*



**Theorem 57**. *(Model existence theorem)\
Suppose $\Sigma$ a consistent set of closed L-formulas. Then there is a
countable L-structure $\mathcal{A}$ such that

$$A \models \Sigma, \text{ i.e } A\models \sigma , \forall \sigma  \in \Sigma$$



**Theorem 58**. *Let $\Sigma$ a set of closed L-formulas, $\phi$ a
closed L-formula.\
If every model $\Sigma$ is a model of $\phi$, then
$\Sigma  \vdash_{K_{\mathcal{L}}} \phi$ . That is

$$\text{if } \mathcal{A} \models \Sigma, \text{ or } \mathcal{A} \models \sigma , \forall \sigma \in \Sigma \implies \mathcal{A} \models \phi , \text{ then }  \Sigma 
        \vdash_{K_{\mathcal{L}}} \phi$$



**Theorem 59**. *(Gödel's completeness theorem for
$K_{\mathcal{L} }$ )\
If $\phi$ an L-formula with $\models \phi$, then $\phi$ a theorem of
$K_{\mathcal{L} }$ i.e.
$\vdash_{K_{\mathcal{L}}} \phi$*



**Corollary 60**. *(Compactness theorem for
$K_{\mathcal{L} }$ )\
Suppose $\Sigma$ a set of closed L-formulas and every finite subset of
$\Sigma$ has a model. Then $\Sigma$ has a model.*


## Equality


**Definition 61**. *Suppose $\mathcal{L}^{E}$ a
first-order language with a distinguished binary relation symbol $E$*

-   *An $\mathcal{L}^{E}$-structure in which $E$ is
    interpreted as equality $=$ is a **normal**
    $\mathcal{L}^{E}$-structure*

-   *The following are **axioms of equality**, $\Sigma_E$*

    -   *$(\forall x_1) E(x_1,x_1)$*

    -   *$(\forall x_1)(\forall x_2)(E(x_1,x_2) \to E(x_2,x_1))$*

    -   *$(\forall x_1)(\forall x_2)(\forall x_3)(E(x_1,x_2) \to (E(x_2,x_3) \to E(x_1,x_3)))$*

    -   *For each $n$-ary relation symbol $R$ of
        $\mathcal{L}^{E}$

        $$(\forall x_1, \ldots  ,x_{n})(\forall y_1, \ldots  ,y_{n})((R(x_1, \ldots  ,x_{n}) \wedge E(x_1,y_1) \wedge  \ldots \wedge E(x_{n},y_{n})) \to R(y_1, \ldots , y_{n} ))$$

    -   *For each $m$-ary function symbol $f$ of
        $\mathcal{L}^{E}$

        $$(\forall x_1, \ldots  ,x_{m})(\forall y_1, \ldots  , y_{m})((E(x_1, y_1)) \wedge  \ldots \wedge E(x_{m},y_{m})) \to E(f(x_1,, \ldots  ,x_{m}),f(y_1, \ldots  , y_{m} ))$$



**Remark 62**. *Some remarks/defs*

-   *If $\mathcal{A}$ a normal
    $\mathcal{L}^{E}$-structure, then
    $A \models \Sigma_E$*

-   *Suppose
    $\mathcal{A}  = \left< A; \overline{E} , \ldots   \right>$
    an $\mathcal{L}^{E}$-structure and
    $A \models \Sigma_E$ . Then $\overline{E}$ an equivalence relation
    on $A$\
    Denote for $a \in A$

    $$\hat{a} = \{b\in A \mid  \overline{E} (a,b) \text{ holds} \}$$
    
    the equivalence class of $a$. Let

    $$\hat{A} = \{\hat{a}  \mid a \in A\}$$
    
    Make $\hat{A}$ into an
    $\mathcal{L}^{E}$-structure
    $\hat{\mathcal{A} }$*

    -   *if $R$ an $n$-ary relation symbol,
        $\hat{a}_1, \ldots  , \hat{a}_{n} \in \hat{A}$\
        Say $\overline{R} (\hat{a}_1, \ldots  , \hat{a}_{n})$ holds in
        $\hat{\mathcal{A} } \iff  \overline{R} (a_1, \ldots ,a_{n} )$holds
        in $\mathcal{A}$, this is well defined by
        $\Sigma_E$*

    -   *Similarly, if $f$ an $m-$ary function symbol and
        $\hat{a}_1, \ldots  ,\hat{a}_{m} \in \hat{A}$ let
        $$\overline{f} (\hat{a}_1, \ldots  , \hat{a}_{m})= \overline{f} \widehat{(a_1, \ldots  , a_{m})}$$
        This also well defined by $\Sigma_E$*

    -   *if $c$ a constant symbol, then interpret $c$ as
        $\hat{\overline{c} }$ in $\hat{\mathcal{A} }$,
        where $\overline{c}$ the interpretation in
        $\mathcal{A}$*



**Lemma 63**. *Suppose $\mathcal{A}$ an
$\mathcal{L}^{E}$-structure with
$\mathcal{A} \models \Sigma_E$. Let $v$ a valuation in
$\mathcal{A}$. Let $\hat{\mathcal{A} }$
be as given above. Let $\hat{v}$ be the valuation in
$\hat{\mathcal{A} }$ with

$$\hat{v} (x_{i}) = \widehat{v(x_{i})}$$

Then for every $\mathcal{L}^{E}$-formula, $\phi ,\hat{v}$ satisfies
$\phi$ in $\hat{\mathcal{A} } \iff v$ satisfies $\phi$
in $\mathcal{A}$\
In particular, if $\phi$ is closed, then
$\mathcal{A} \models \phi \iff \hat{\mathcal{A} } \models \phi$*



**Lemma 64**. *Suppose $\Delta$ a set of closed
$\mathcal{L}^{E}$-formulas\
Then $\Delta$ has a **normal model**, that is a normal
$\mathcal{L}^{E}$-structure,
$\mathcal{B}$ with
$\mathcal{B} \models \sigma , \forall \sigma  \in \Delta  \iff \Delta \cup \Sigma_E$
has a model.*



**Theorem 65**. *(Compactness theorem for normal models)\
Suppose $\mathcal{L}^{E}$ a countable language with
equality, and $\Delta$ a set of closed
$\mathcal{L}^{E}$-formulas such that every finite subset
of $\Delta$ has a normal model. Then $\Delta$ has a normal model*


**Notation:** Write $\mathcal{L}^{=}$ instead of
$\mathcal{L}^{E}$ and $x_1 = x_2$ instead of
$E(x_1,x_2)$


**Theorem 66**. *(Countable downward Löwnenheim-Skolem theorem)\
Suppose $\mathcal{L}^{=}$ a countable first-order
language, with equality and $\mathcal{B}$ a normal
$\mathcal{L}^{=}$-structure\
Then there is a countable normal
$\mathcal{L}^{=}$-structure
$\mathcal{A}$ such that, for every closed
$\mathcal{L}^{=}$-formula, $\phi$,
$\mathcal{B} \models \phi  \iff  \mathcal{A} \models \phi$*


## Examples and applications

We let $\mathcal{L}^{=}$ be a first-order language with
equality and binary relation symbol $\leq$


**Definition 67**. *We have*

-   *A **linear order**
    $\mathcal{A}  = \left< A; \leq_A \right>$ a normal
    model of 
    
    $$\begin{aligned}
                \phi_1 &: (\forall x_1)(\forall x_2)(((x_1 \leq  x_2) \wedge (x_2 \leq x_1)) \leftrightarrow (x_1 = x_2))\\
                \phi_2 &: (\forall x_1)(\forall x_2)(\forall x_3)(((x_1 \leq  x_2) \wedge (x_2 \leq x_3)) \to (x_1 \leq  x_3))\\
                \phi_3 &: (\forall x_1)(\forall x_2)((x_1 \leq  x_2) \vee  (x_2 \leq x_1))
            \end{aligned}$$

-   *it is **dense** if also

    $$\phi_4: (\forall x_1)(\forall x_2)(\exists x_3)(\underbrace{(x_1 < x_2)}_{((x_1 \leq x_2) \wedge  (x_1 \neq  x_2))} \to ((x_1 < x_3) \wedge (x_3 < x_2)))$$

-   *it is **without endpoints if** 

    $$\begin{aligned}
                \phi_5 &: (\forall x_1)(\exists x_2)(x_1 < x_2)\\
                \phi_6 &: (\forall x_1)(\exists x_2)(x_2 < x_1)
            \end{aligned}$$

*Let $\Delta  = \{\phi_1, \ldots  , \phi_6\}$*

-   *$\mathcal{Q} = \left< \mathbb{Q} ; \leq  \right>$ a
    normal model of $\Delta$*

-   *$\mathcal{R} = \left< \mathbb{R} ; \leq  \right>$
    also a model of $\Delta$*



**Theorem 68**. *We have*

1.  *For every closed $\mathcal{L}^{=}$-formula $\phi$
    $\mathcal{Q} \models \phi \iff \mathcal{R} \models \phi$*

2.  *There is an algorithm which decides, given a closed
    $\mathcal{L}^{=}$-formula $\phi$, whether
    $\mathcal{Q} \models \phi$ or
    $\mathcal{Q} \not\models \phi$, that is
    $\mathcal{Q} \models (\neg \phi)$ (by 2.3.3)*



**Definition 69**. *We have*

1.  *Linear orders
    $\mathcal{A}  = \left< A; \leq_A \right>$ and
    $\mathcal{B}  = \left< B; \leq_B \right>$ are
    **isomorphic** if there is a bijection $\alpha: A \to B$ such that
    $\forall a,a^\prime \in A, a \leq_A a^\prime \iff \alpha (a) \leq_B \alpha (a^\prime )$*

2.  *if $\mathcal{A} ,\mathcal{B}$
    isomorphic and $\phi$ closed, then
    $\mathcal{A} \models \phi \iff \mathcal{B} \models \phi$*



**Theorem 70**. *(Cantor)\
If $\mathcal{A} , \mathcal{B}$ countable
dense linear orders without endpoints, then
$\mathcal{A} ,\mathcal{B}$ are
isomorphic*



**Lemma 71**. (Los-Vaught test)\
Let $\Sigma = \Sigma_E \cup  \Delta$. Then for every closed
$\mathcal{L}^{=}$-formula $\phi$ we have either

$\Sigma \vdash_{K_{\mathcal{L^{=}}}} \phi$ or $\Sigma \vdash_{K_{\mathcal{L^{=}}}} (\neg\phi)$
Say that $\Sigma$ is **complete**


# Set theory

## Basic set theory

-   Extensionality - Sets $A, B$ are **equal**
    $\iff \forall x, x \in A \iff x \in B$

-   **Natural numbers** ; $\mathbb{N} = \{0,1, \ldots  \}$

    $$0 = \varnothing \quad \ldots  , n +1 = \{0, \ldots  , n\}, \quad \ldots$$

    -   Note that, for $m, n \in \mathbb{N}$

        $$m < n \iff m \in n \iff m \subsetneq n$$

-   Ordered pairs. The **ordered pair** $(x,y)$ is the set
    $\{\{x\},\{x,y\}\}$

    -   For example, for any $x,y,z,w, (x,y) = (z,w) \iff x = z$ and
        $y = w$

    -   If $A, B$ sets then

        $$A \times B = \{(a,b) \mid a \in A, b \in B\}$$

        $$A^0 = \{\varnothing \}, \quad A^1 = A \quad A^{2} = A \times  A, \quad \ldots  \quad A^{n+1} = A^n \times A, \quad \ldots$$

        $$\bigcup_{n\in \mathbb{N}} A^n = \{ \text{finite sequences of elements of }A \}$$

-   Functions. Think of $f: A \to B$ as a subset of $A \times  B$

    $$f: \underbrace{A}_{dom f } \to \underbrace{B}_{ran f }$$

    $X \subseteq A$ define $f[X] = \{f(a) \mid  a \in X\} \subseteq B$\

-   Set of functions from $A$ to $B$ is

    $$B^A \subseteq \mathcal{P} (A \times B)$$ 
    
    where $\mathcal{P}$ is the powerset.

## Cardinality


**Definition 72**. *Sets $A,B$ are **equinumerous**, or of the **same
cardinality**, if there is a bijection $f:A \to B$\
Write $A \thickapprox B$ or $\mid A\mid = \mid B\mid$*



**Definition 73**. *We have*

-   *A set is **finite** if it is equinumerous with some element
    $n = \{0, \ldots  , n-1\}$ of $\mathbb{N}$*

-   *A set $A$ is **countably infinite** if it is equinumerous with
    $\mathbb{N}$*

-   ***Countable** is finite or countably finite*



**Remark 74**. *(Basic facts)*

-   *Every subset of countable set is countable*

-   *A set $A$ is countable $\iff$ there is an injective function
    $f:A \to \mathbb{N}$*

-   *if $A,B$ countable then $A\times B$ countable*

-   *$A_0, A_1, \ldots$ countable, then
    $\bigcup_{i \in \mathbb{N}} A_{i}$ countable. *(requires axiom of
    choice)**



**Theorem 75**. *(Cantor)\
There is no surjective function

$$f: X \to \mathcal{P} (X)$$



**Definition 76**. *For sets $A,B$ write $\mid A\mid \leq \mid B\mid$ or
$A \leq  B$, if there is injective function $f:A \to B$*



**Theorem 77**. *(Schröder-Bernstein)\
Suppose $A,B$ are sets, and $f:A \to B, g: B \to A$ are injective
functions. Then $A\thickapprox B$ i.e if
$\mid A\mid  \leq \mid B\mid , \mid B\mid  \leq \mid A\mid  \implies \mid A\mid  = \mid B\mid$*


## Axioms for set theory

**Zermelo-Fraenkel axioms (ZF)**\
Axioms, that denote how we are allowed to build sets, expressed in a
first-order language, with equality, using a single binary relation
$\in$\
Avoid the **Russell Paradox**

$$S = \{x \mid  x \text{ a set and } x \notin x\}$$ 

If $S$ a set, is $S \in S$?

$$(\exists S)(\forall x)((x\in S) \leftrightarrow (x \notin x))$$

leads to inconsistency!

1.  (Axiom of Extensionality).\
    Two sets are equal $\iff$ they have the same elements

    $$(\forall x)(\forall y)((x = y) \leftrightarrow (\forall z)((z \in x) \leftrightarrow (z \in y)))$$

2.  (Empty set axiom)

    $$(\exists x)(\forall y)(y \notin x)$$
    
    There is a unique set $x$ with this property, $\varnothing$

3.  (Pairing axiom)\
    Given sets $x, y$ we can form $z = \{x,y\}$

    $$(\forall x)(\forall y)(\exists z)(\forall w)((w \in z) \leftrightarrow ((w = x) \vee (w = y)))$$

4.  ( Union Axiom)\
    For any set $A$ there is a set $B = \bigcup A$

    $$(\forall A)(\exists B)(\forall x)((x \in B) \leftrightarrow (\exists z)((z\in A) \wedge (x \in z)))$$

    So 
    
    $$B = \bigcup \{z \mid z \in A\}$$

5.  (Power set axiom)\
    For any set $A$ , there is a set $\mathcal{P} (A)$
    whose elements are the subsets of $A$

    $$(\forall A)(\exists B)(\forall z)((z \in B) \leftrightarrow \underbrace{(z \subseteq A)}_{(\forall y)((y \in z)\to (y \in A))})$$

6.  (Axiom scheme of specfication)\
    Suppose $P(x,y_1, \ldots  ,y_{r})$ a formula in our language then we
    have axiom

    $$(\forall A)(\forall y_1)\ldots  (\forall y_{r})(\exists B)(\forall x)((x\in B)\leftrightarrow ((x\in A)\wedge P(x,y_1, \ldots  ,y_{r})))$$

    This guarantees, we can form subset of $A$

    $$B = \{x \in A \mid P(x,y_1, \ldots  ,y_{r}) \text{ holds} \}$$
    
    for all given sets $A, y_1 , \ldots  , y_{r}$

    
    **Definition 78**. *For set $a$ define **successor** of $a$ as

    $$a^{\dagger} = a \cup  \{a\}$$
    
    A set $A$ **inductive** if

    $$((\varnothing \in A) \wedge (\forall x)((x \in A) \to (x^{\dagger} \in A)))$$
    

7.  (Axiom of infinity)

    $$(\exists A)((\varnothing \in A) \wedge (\forall x)((x \in A) \to (x^{\dagger} \in A)))$$


**Definition 79**. *Let $A$ an inductive set, can form using
specification the set

$$\mathbb{N} = \{x \in A\mid \text{ if } B \text{ is an inductive set then }x \in B \}$$



**Theorem 80**. *We have*

1.  *$\mathbb{N}$ an inductive set, if $B$ an inductive set then
    $\mathbb{N} \subseteq B$*

2.  *Proof by induction works. Suppose $P(x)$ a property of sets, that
    is a formula, such that*

    1.  *$P(\varnothing )$ holds, and*

    2.  *for every $k \in \mathbb{N}$, if $P(k)$ holds, then
        $P(k^{\dagger})$ holds*

*Then $P(n)$ holds for all $n \in \mathbb{N}$*


## Well orderings


**Definition 81**. *A **linear ordering** $\left< A; \leq  \right>$ a
**well orderings** or **woset** of every non-empty subset of $A$ has a
least element

$$(\forall X)(((X \subseteq A) \wedge  (X \neq \varnothing )) \to (\exists x)((x\in X) \wedge (\forall y)((y \in X) \to (x \in y))))$$



**Definition 82**. *Suppose
$\mathcal{A}_1, \mathcal{A}_2$ are
**similar** or **isomorphic** if there is a bijection

$$\alpha : A_1 \to A_2 \text{ s.t. } \forall a,b \in A_1, \text{ if } a<_1 b \iff \alpha(a) <_2 \alpha (b)$$

Write
$\mathcal{A}_1 \backsimeq \mathcal{A}_2$\
Call $\alpha$ a similarity between
$\mathcal{A}_1, \mathcal{A}_2$*



**Definition 83**. *Define the following*

-   *The **reverse-lexicographic product** is

    $$\mathcal{A}_1 \times \mathcal{A}_2 = \left< A_1 \times A_2; \leq  \right>$$

    where
    $(a_1,a_2) \leq  (a^\prime_1,a^\prime_2) \iff a_2 <_2 a^\prime_2 \text{ and } a_1 \leq_1 a^\prime_1$\
    In $\mathcal{A}_2$ replace each element by a copy of
    $\mathcal{A}_1$*

-   *Regard $A_1, A_2$ as disjoint, by replacing them by similar
    orderings on disjoint sets, such as 
    
    $$\begin{aligned}
                A_1 \times \{0\} &= \{(a,0) : a \in A_1\}\\
                A_2 \times \{1\} &= \{(a,1): a \in A_2\}
            \end{aligned}$$
            
    Define sum

    $$\mathcal{A}_1 + \mathcal{A}_2 = \left< A_1 \cup  A_2; \leq  \right>$$

    Where $\leq$ the union of $\leq_1, \leq _2$ and
    $a_1 \leq  a_2, a_1 \in A_1, a_2 \in A_2$*



**Lemma 84**. *With this notation*

1.  *$\mathcal{A}_1 + \mathcal{A}_2, \mathcal{A}_1 \times \mathcal{A}_2$
    are linearly ordered sets*

2.  *If $\mathcal{A}_1, \mathcal{A}_2$
    are wosets then so are
    $\mathcal{A}_1 + \mathcal{A}_2, \mathcal{A}_1 \times \mathcal{A}_2$*


## Ordinals


**Definition 85**. *Define the following*

1.  *A set $X$ a **transitive set** if every element of $X$ is also a
    subset of $X$.\
    That is if $y \in x \in X \implies y \in X$*

2.  *A set $\alpha$ is an **ordinal** If*

    -   *$\alpha$ a transitive set*

    -   *the relation $<$ on $\alpha$ given by, for $x,y \in \alpha$, we
        have that $x < y \iff x \in y$ a strict well ordering on
        $\alpha$*



**Lemma 86**. *If $\alpha$ an ordinal then so is
$a^{\dagger} = a \cup  \{a\}$*



**Proposition 87**. *We have*

1.  *if $n \in \omega$ then $n$ an ordinal*

2.  *$\omega$ a transitive set*



**Proposition 88**. *We have*

1.  *If $\alpha$ an ordinal then $\alpha  \notin  \alpha$*

2.  *If $\alpha$ an ordinal and $\beta \in \alpha$ then $\beta$ an
    ordinal*

3.  *If $\alpha ,\beta$ ordinals and $\alpha \subsetneq \beta$ then
    $\alpha \in \beta$*

4.  *If $\alpha$ an ordinal, then
    $\alpha = \{\beta  \mid \beta  \text{ an ordinal and } \beta  \in \alpha  \}$*



**Definition 89**. *$\alpha ,\beta$ ordinals, write $\alpha  < \beta$ to
mean $\alpha \in \beta$ and
$\alpha \leq \beta \iff \alpha \subseteq \beta$*



**Theorem 90**. *Suppose $\alpha,\beta,\gamma$ are ordinals*

1.  *If $\alpha  < \beta , \beta  < \gamma \implies \alpha <\gamma$*

2.  *If
    $\alpha \leq \beta , \beta  \leq \alpha  \implies \alpha = \beta$*

3.  *Exactly one of the following hold
    $$\alpha  < \beta ,\quad \alpha = \beta,\quad \beta  < \alpha$$

4.  *if $X$ a non-empty set of ordinals, then $X$ has a least element
    $\delta$, and moreover $$\delta  = \bigcap X$$



**Corollary 91**. *We have*

1.  *If $X$ a non-empty set of ordinals, then $\bigcup X$ is an ordinal*

2.  *$\omega$ is an ordinal*



**Theorem 92**. *If $\left< A; \leq  \right>$ a well ordered set, then
there is a unique ordinal $\alpha$ which is similar to
$\left< A; \leq  \right>$*



**Definition 93**. *Suppose $\left< A; \leq  \right>$ a woset. Say
$X \subseteq A$ an **initial segment** of $A$ if whenever $y < x< \in X$
then $y \in X$, it is proper if $X \neq A$*



**Lemma 94**. *Suppose $\left< A, \leq  \right>$ a woset. If
$X \subset A$ is a proper initial segment of $A$ there is $z\in A$ with
$X= A[z]$*



**Proposition 95**. *Suppose $(A; \leq )$ a woset and and $f:A \to A$
which is order preserving and $f[A]$ is an initial segment of $A$, then
$f(x) = x$ for all $x \in A$*


