---
layout: default
title: Applied Probability
parent: Year 3
nav_order: 1
math: mathjax3
---

# Applied Probability - Concise Notes
{: .no_toc }
## MATH60045
{: .no_toc}

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
  
- <a href="/notes/pdfs/year3/LecNotes/AP-Concise.pdf" target="_blank" style="color:#801fff;">**Open Algebra 3 Concise - Incomplete**</a> - <a href="/notes/pdfs/year3/LecNotes/AP-Concise.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets</span>
  </summary>
  
  - <a href="/notes/pdfs/year2/problemsheets/anlaysisSheets/term1/ANAPS1.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 1**</a> - <a href="/notes/pdfs/year2/problemsheets/anlaysisSheets/term1/ANAPS1-Sol.pdf" target="_blank">**Solutions**</a>

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

# Discrete-time Markov Chains

## Definition of discrete time Markov Chains


**Definition 1**. A discrete-time stochastic process
$X = \{X_n\}_{n \in \mathbb{N}_{0} }$ taking values in countable state
space $E$ a Markov chain if it satisfies the Markov condition

$$P(X_{n} = j \mid  X_{n-1} = i, X_{n-2} = x_{n-2} , \ldots  , X_{0} = x_0) = P(X_{n} = j \mid  X_{n-1} = i), \forall n \in \mathbb{N}\
        \forall x_0, \ldots , x_{n-2}, i ,j \in E$$



**Definition 2**. *(Time Homogenous)*

1.  *Markov Chain $\{X_{n}\}_{n \in \mathbb{N}_{0}}$ is time-homogenous
    if*
    
    $$P(X_{n+1} = j \mid  X_{n} = i ) = P(X_1 = j \mid  X_0 = i),\ \forall n \in \mathbb{N}_0, i,j \in E$$

2.  *Transition matrix $P = (p_{ij} )_{i,j\in E}$ is the $K \times  K$
    matrix of transition probabilities*



**Definition 3**. *(Stochastic Matrix)\
A square matrix $P$ a stochastic matrix if*

1.  $p_{ij} \geq  0, \forall  i,j$

2.  $\sum_{j} p_{ij} =1\ \forall  i$



**Theorem 4**. *Transition matrix $P$ is stochastic*


## The $n$-step transition probabilities and Chapman-Kolmogorov equations


**Definition 5**. $n \in \mathbb{N}$, we have*

$$P_{n} = (p_{ij} (n)) = P(X_{m+n} = j, X_{m}=i),\ m \in \mathbb{N}_0$$

The matrix of $n$-step transition probabilities.



**Lemma 6**. *For discrete markov chain $\{X_{n}\}_{n \geq 0}$ on state
space $E$ we have*

$$P(X_{n+m} = x_{n+m} | X_{n} = x_{n}, \ldots , X_0 = x_0 ) = P(X_{n+m} = x_{n+m} \mid X_{n} = x_{n}),\ m \in \mathbb{N}, \forall x_{n+m}, x_{n}, \ldots , x_0 \in E$$



**Theorem 7**. Let $m\in \mathbb{N}_0, n \in \mathbb{N}$ Then we have
$\forall i,j \in E$

$$p_{ij } (m+n) = \sum_{l\in E} p_{il}(m) p_{lj} (n) \quad P_{m+n}  = P_{m}P_{n} \quad P_{n} = P^n$$



**Remark 8**. Extend definition for case $K = \infty$\
Let $\mathbf{x}$ a $K$-dimensional row vector, $P$ a $K \times  K$
matrix

$$(\mathbf{x} P)_{j} := \sum_{i\in E} x_{i} p_{ij}, \quad (P^{2})_{ik} := \sum_{j\in E} p_{ij} p_{jk}, \ i,j,k \in \mathbb{N}$$

Define $P^n$ similarly and take $(P^0)_{ij} = \delta_{ij}$


## Dynamics of a Markov Chain


**Definition 9**. Denote probability mass function of $X_{n}$ for
$n \in \mathbb{N}_0$ by 

$$\nu_{i}^{(n)} = P(X_{n} = i),\ i \in E$$ 

Take
$K = \mathop{card}(E)$, denote by $\mathbf{\nu}^{(n)}$ the
$K$-dimensional row vector with elements $\nu_{i}^{n}, i \in E$\
Call this the **marginal distribution** of chain at time
$n \in \mathbb{N}_0$



**Theorem 10**. We have

$$\mathbf{\nu}^{(m+n)} = \mathbf{\nu}^{(m)}P_{n}= \mathbf{\nu}^{(m)}P^{n},\ \forall n \in \mathbb{N}, m \in \mathbb{N}_0$$

So

$$\mathbf{\nu}^{(n)} = \nu^{(0)} P_{n} = \mathbf{\nu}^{(0)} P^{n},\ \forall n \in \mathbb{N}$$



**Theorem 11**. Let $X = \{X_{n}\}_{n \in \mathbb{N}_{0}}$ a Markov
chain on countable state space $E$

Then given initial distribution $\mathbf{\nu}^{(0)}$ and transition
matrix $P$, we determine all finite dimensional distributions of Markov
chain.

$\forall 0 \leq n_1 < n_2 < \cdots < n_{k-1} < n_{k} \ (n_{i} \in \mathbb{N}_0, i = 1, \ldots ,k  ), k \in \mathbb{N}, x_1, \ldots ,x_k \in E$

We have 

$$\begin{aligned}
        P(X_{n_1} = x_1, X_{n_2} = x_2, \ldots , X_{n_{k}} = x_{k}) &= 
        (\mathbf{\nu}^{(0)}P^{n_1})_{x_1} (P^{n_2 - n_1})_{x_1 x_2} \cdots (P^{n_{k} - n_{k-1}})x_{k-1} x_{k}\\
        &= (\mathbf{\nu}P^{n_1})x_1 p_{x_1 x_2}(n_2 - n_1) \cdots p_{x_{k-1} x_{k}}(n_{k}-n_{k-1} )
    \end{aligned}$$


## First passage/hitting times


**Definition 12**. Define **first passage/hitting time** of $X$ for
state $j \in E$ as 

$$T_{j} = \mathop{\min} \{n \in N: X_{n}=j\}$$

If $X_{n} \neq  j, \forall n \in \mathbb{N}$ then set $T_{j} = \infty$



**Definition 13**. *For $i,j \in E, n \in \mathbb{N}$ define **first
passage probability**

$$f_{ij} (n) = P(T_{j} = n \mid  X_0 = i) = P(X_{n} = j, X_{n-1} \neq  j, \ldots  , X_1 \neq  j \mid X_0 = i)$$

Probability that we visit state $j$ at time $n$, given we start at $i$
at time $0$

Define $f_{ij} (0) = 0, f_{ij} (1) = p_{ij} , \forall i,j \in E$



**Definition 14**. Define 

$$f_{ij} = P(T_{j} < \infty \mid  X_0 = i)$$

For $i \neq  j$, we have $f_{ij}$ the probability that the chain ever
visits state $j$, starting at $i$

Call $f_{ii}$ the **returning probability***


**Proposition 15**. $\forall  i,j \in E$

$$f_{ij} = \sum_{n=1}^{\infty} f_{ij} (n)$$


**Lemma 16**. $\forall i,j \in E, n \in \mathbb{N}$, we have

$$\begin{aligned}
        p_{ij} (n) &= \sum_{l=0}^{n} f_{ij} (l) p_{jj}(n-l)\\
                   &= \sum_{l=1}^{n} f_{ij} (l) p_{jj}(n-l)
    \end{aligned}$$


## Recurrence and transience


**Definition 17**. Let $\{X_{n}\}_{n \in \mathbb{N}_{0}}$ be a markov
chain on countable state space $E$.

$$j \in E,\ P(X_{n}=j,\text{for some } n \in \mathbb{N}\mid X_0 = j ) = f_{jj}
    \begin{cases}
            1, &\text{ recurrent}  ;\\
            <1, &\text{ transient }  .
    \end{cases}$$



**Theorem 18**. $j \in E$ 

$$\sum_{n=1}^{\infty} p_{ij} (n) =
            \begin{cases}
                \infty , & \iff  \text{ recurrent }  ;\\
                < \infty , & \iff  \text{ transient }  .
            \end{cases}$$


**Define**

$$N_{j} = \sum_{n=0}^{\infty } I_{n}^{(j)}, \quad I_{n}^{(j)} = I_{X_n = j} = \begin{cases}
        1, &\text{ if } X_{n} = j ;\\
        0, &\text{ if } X_{n}\neq j .
    \end{cases}$$


**Theorem 19**. $j \in E$ transient*

1.  $P(N_{j} = n \mid  X_0 = j) = f_{jj}^{n-1} (1 - f_{jj})$ for
    $n \in \mathbb{N}$ *geometric distribution with param $f_{jj}$*

2.  $i \neq  j$

 $$P(N_{j} = n \mid X_0 = i) =
                \begin{cases}
                    1 - f_{ij} , &\text{ if } n=0 ;\\
                    f_{ij} f_{jj}^{n-1}(1-f_{jj}), &\text{ if } n \in \mathbb{N} .
                \end{cases}$$


 
**Corollary 20**. $j \in E$ transient

1.  $$E(N_{j}\mid X_0 = j) = \frac{1}{1-f_{jj}}$$

2.  $i \neq  j$ we have

    $$E(N_{j} \mid X_0 = i) = \frac{f_{ij}}{1 - f_{jj}}$$



**Theorem 21**. *Given $X_0 = j$, we have

$$E(N_{j} \mid X_0 = j) = \sum_{n=0}^{\infty} p_{jj}(n)$$

Sum may diverge to $\infty$


 
**Corollary 22**. $j \in E$ transient then
$p_{ij} (n) \xrightarrow[n\to \infty]{} 0, \forall  i \in E$


### Mean recurrence time, null and positive recurrence


**Definition 23**. The **mean recurrence time** $\mu_{i}$ of state
$i \in E$ defined as $\mu_{i} = E[T_{i} \mid  X_0 = i]$



**Theorem 24**. *Let $i \in E$. We have
$P(T_{i} = \infty  \mid  X_0 = i) > 0$ $\iff i$ transient, where we get

$$\mu_{i} = E[T_{i} \mid X_0 = i = \infty ]$$



**Theorem 25**. *For recurrent state $i \in E$ we have

$$\mu_{i}= E[T_{i}\mid X_0 = i] = \sum_{n=1}^{\infty} n f_{ii}(n)$$

Can be finite or infinite.



**Definition 26**. *A recurrent state $i \in E$ 

$$\mu_{i} = 
        \begin{cases}
            \infty , &\text{ called } \textbf{null} ;\\
            < \infty , &\text{ called } \textbf{positive}  .
        \end{cases}$$



**Theorem 27**. *Recurrent state $i \in E$ null $\iff$
$p_{ii}(n) \xrightarrow[n\to \infty ]{} 0$\
Further, if this holds, then
$p_{ji} (n) \xrightarrow[n\to \infty ]{} 0 , \forall j \in E$


### Generating functions for $p_{ij} (n), f_{ij} (n)$ (READING MATERIAL)

### Example: Null recurrence/transience of a simple random walk (READING MATERIAL)

$$SEE\ FULL\ OFFICIAL\ NOTES$$

## Aperiodicity and ergodicity


**Definition 28**. Period of state $i$ defined by

$$d(i) = gcd\{n : p_{ii}(n) > 0\}$$



**Definition 29**. *A state ergodic if it is positive recurrent and
aperiodic*


## Communicating classes


**Definition 30**. *(Accessible and Communicating)*

1.  $j$ accessible from $i$, $i \to j$, if $\exists m \in \mathbb{N}_0$
    s.t $p_{ij} (m) >0$

2.  $i, j$ communicate, if $i \to j$ and $j \to i$; write
    $i \leftrightarrow j$



**Theorem 31**. *(Communication an equivalence relation)\
Satisfies, reflexivity, symmetry and transitivity*



**Theorem 32**. *If $i \leftrightarrow j$ then*

1.  $i,j$ have same period

2.  $i$ transient/recurrent $\iff$ $j$ transient/recurrent

3.  $i$ null recurrent $\iff$ $j$ null recurrent



**Definition 33**. *Set of states $C$ is*

1.  ***closed** if $\forall i \in C, j \notin C, p_{ij} - 0$

2.  ***irreducible** if $i \leftrightarrow j, \forall  i,j \in C$



**Theorem 34**. *Let $C$ a closed communicating class, transition matrix
$P$ restricted to $C$ is stochastic*


### The decomposition theorem


**Theorem 35**. $C$ a communicating class, consisting of recurrent
states. Then $C$ is closed*



**Theorem 36**. *State-space $E$ can be partitioned uniquely into

$$E = \underbrace{T}_{\text{transient states} } \cup \left( \bigcup\limits_{i} \underbrace{C_{i}}_{\substack{\text{irreducible, closed}\\ \text{set of recurrent states}} }  \right)$$



**Theorem 37**. $K < \infty$ Then at least one state is recurrent and
all recurrent states are positive.



**Theorem 38**. $C$ a finite, closed communicating class $\implies$ all
states in $C$ positive recurrent


### Class properties


| Type of Class | Finite             | Infinite                                      |
|---------------|--------------------|-----------------------------------------------|
| Closed        | positive recurrent | positive recurrent, null recurrent, transient |
| Not Closed    | transient          | transient                                     |


## Application: The gambler's ruin problem

### The problem and the results

![image](figs/ap/gr.jpg)

Consider a gambler with initial fortune $i \in \{0,1, \ldots  , N\}$. At
each play of the game, the gambler has

-   probability $p$ of winning one unit

-   probability $q$ of losing one unit

-   each successive game is independent

**What is the probability, a gambler starting at $i$ units, has their
fortune reach $N$ before $0$ ?**

Let $X_{n}$ denote gamblers fortune at time $n$. Then $\{X_{n}\}_{n \in \mathbb{N}_{0}}$ is a Markov Chain with transition probabilities, shown in diagram above.

This yields 3 communicating classes.

$$\underbrace{C_1 = \{0\}, C_2 = \{N\}}_{\substack{\text{positive recurrent}\\ \text{since finite and closed} } }, T_1 = \{1,2, \ldots  , N-1\}$$

**Define the following for our problem:**\
Define first time $X$ visits state $i$ as

$$V_{i} = \mathop{\min} \{n \in \mathbb{N}_0 : X_{n} = i\}$$

$$h_{i} = h_{i}(N) = P(V_{N}< V_0 \mid  X_0 = i)$$

This yields the following recurrence relation

$$h_{i} = h_{i+1} p + h_{i-1} q,\ i = 1,2, \ldots  , N-1$$


**Theorem 39**. From above we achieve 

$$h_{i}= h_{i}(N) =
        \begin{cases}
            \frac{1-(q /p)^i}{1 - (q /p)^N}, &\text{ if } p \neq  \frac{1}{2} ;\\
            \frac{i}{N}, &\text{ if } p = \frac{1}{2} .
        \end{cases}$$


**Theorem 40**. *We also have

$$\lim\limits_{N \to \infty} h_{i}(N) = h_{i}(\infty ) = 
        \begin{cases}
            1 - (q /p)^i, &\text{ if } p > \frac{1}{2} ;\\
            0, &\text{ if } p \leq  \frac{1}{2} .
        \end{cases}$$

-   $p > \frac{1}{2} \implies \frac{q}{p} < 1 \implies \lim\limits_{N \to \infty} (\frac{q}{p})^N = 0$

-   $p < \frac{1}{2} \implies \frac{q}{p} > 1 \implies \lim\limits_{N \to \infty}  = \infty$


## Stationarity


**Definition 41**. *(Distributions)*

1.  row vector $\mathbf{\lambda}$ a **distribution** on $E$ if

    $$\forall j \in E, \lambda_{j} \geq  0,\ \text{ and } \sum_{j\in E} = 1$$

2.  row vector $\mathbf{\lambda}$ with non-negative entries is called
    **invariant** for transition matrix $P$ if $$\lambda P = \lambda$$

3.  row vector $\mathbf{\pi}$ is **invariant/stationary/equilibrium
    distribution** of Markov chain on $E$ with transition matrix $P$ if

    1.  $\mathbf{\pi}$ a distribution

    2.  *it is invariant*

    $$\pi P^n = \pi$$


### Stationarity distribution for irreducible Markov Chains


**Theorem 42**. *An irreducible chain has stationary distribution $\pi$
$\iff$ all states are positive recurrent.\
$\pi$ unique stationary distribution, s.t
$\pi_i = \mu_{i}^{-1} \forall  i$



**Lemma 43**. *For markov chain $X$ we have
$\forall j \in E, n, m \in \mathbb{N}$

$$f_{jj}(m+n) = \sum_{i\in E, i \neq j} l_{ji} (m) f_{ij} (n)$$

For $l_{ji} (n) = P(X_{n} = i. T_{j} \geq  n \mid X_0 = j)$


 
**Corollary 44**. *For Markov Chain $X$ we have
$\forall i,j \in E, i \neq  j$ and $\forall n,m \in \mathbb{N}$

$$f_{jj}(m+n) \geq l_{ji} (m) f_{ij}  (n)$$



**Lemma 45**. *Let $i \neq  j$ Then $l_{ji} (1) = p_{ji}$, and for
integers $n \geq 2$

$$l_{ji} (n) = \sum_{r\in E: r \neq j} p_{ri} l_{jr} (n-1)$$



**Lemma 46**. $\forall j \in E$ of an irreducible, recurrent chain, the
vector $\mathbf{\rho}(j)$ satisfies $\rho_{i}(j) < \infty\ \forall  i$
and further $\mathbf{\rho} (j) = \mathbf{\rho} (j)P$



**Lemma 47**. *Every irreducible, positive, recurrent chain has a
stationary distribution*



**Theorem 48**. If the chain is irreducible and recurrent, then
$\exists \mathbf{x} > 0$ s.t $\mathbf{x}  = \mathbf{x} \mathbf{P}$
unique up to multiplicative constant. 

$$\text{Chain is } 
        \begin{cases}
            \text{positive recurrent}, &\text{ if } \sum_{i}x_{i} < \infty  ;\\
            \text{null} , &\text{ if }  \sum_{i}x_{i} = \infty  .
        \end{cases}$$



**Lemma 49**. Let $T$ a non-negative integer valued random variable on
probability space $(\Omega ,\mathcal{F} ,P)$, with
$A \in \mathcal{F}$ an event s.t $P(A) > 0$. Can show
that 

$$E(T\mid A) = \sum_{n=1}^{\infty} P(T \geq  n \mid A)$$


**Theorem** *(Dominated convergence theorem)*

Let $\mathcal{I}$ be a countable index set.\
If $\sum_{i \in \mathcal{I}} a_{i}(n)$ is an absolutely
convergent series $\forall  n \in N$ s.t

1.  $\forall i \in \mathcal{I}$ the limit
    $\lim\limits_{n \to \infty} a_{i}(n) = a_{i}$ exists

2.  $\exists$ seq. $(b_{i})_{i\in I}$ s.t $b_{i} \geq  0\, \forall i$
    and $\sum_{i\in \mathcal{I}} b_{i} < \infty$ s.t
    $\forall n, i: |a_{i}(n)| \leq  b_{i}$

Then $\sum_{i\in \mathcal{I}} |a_{i}| < \infty$ and

$$\sum_{i\in I}a_{i} = \sum_{i\in I} \lim\limits_{n \to \infty} a_{i}(n) = \lim\limits_{n \to \infty} \sum_{i\in \mathcal{I}}a_{i}(n)$$

### Limiting distribution


**Definition 50**. A distribution $\pi$ is the limiting distribution of
a discrete-time Markov Chain if, $\forall i,j \in E$ we have

$$\lim\limits_{n \to \infty} p_{ij} (n) = \pi_{j}$$



**Definition 51**. For irreducible aperiodic chain we have

$$\lim\limits_{n \to \infty} p_{ij} (n) = \frac{1}{\mu_{j}}$$


### Ergodic Theorem


**Theorem 52**. *(Ergodic Theorem)\
Suppose we have irreducible Markov chain
$\{X_{n}\}_{n \in \mathbb{N}_{0}}$ with state space $E$. Let $\mu_{i}$
the mean recurrence time to state $i \in E$

$$V_{i}(n) = \sum_{k=0}^{n-1} \mathbf{1}_{\{X_{k}=i\}}$$ 

The number of visits to $i$ before $n$

So we have $V_{i}(n) / n$ the proportion of time before $n$ spent at $i$

$$P        \left(\frac{V_{i}(n)}{n}\to \frac{1}{\mu_{i}}, \text{ as } n \to \infty\right) = 1$$


**Summary: Properties of irreducible Markov Chains**\
3 kinds of irreducible Markov Chains

1.  **Positive recurrent**

    1.  Stationary distribution $\pi$ exists

    2.  Stationary distribution is unique

    3.  All mean recurrence times are finite and
        $\mu_{i} = \frac{1}{\pi_i}$

    4.  $V_{i}(n) / n \xrightarrow[n \to \infty ]{} \pi_i$

    5.  If chain aperiodic

        $$\lim\limits_{n \to \infty} P(X_{n} = i) = \pi_i, \forall  i \in E$$

2.  **Null recurrent**

    1.  Recurrent, but all mean recurrence times are infinite

    2.  No stationary distribution exists

    3.  $V_{i}(n) / n \xrightarrow[n \to \infty ]{} 0$

    4.  $$\lim\limits_{n \to \infty} P(X_{n} = i) = 0, \forall  i \in E$$

3.  **Transient**

    1.  Any particular state is eventually never visited

    2.  No stationary distribution exists

    3.  $V_{i}(n) / n \xrightarrow[n \to \infty ]{} 0$

    4.  $$\lim\limits_{n \to \infty} P(X_{n} = i) = 0, \forall i \in E$$

### Properties of the elements of a stationary distribution associated with transient or null-recurrent states


**Theorem 53**. *Let $X$ a time-homogeneous Markov Chain on countable
state space $E$\
If $\pi$ a stationary distribution of $X$, $i \in E$ either transient or
null-recurrent, then $\pi_i = 0$


### Existence of a stationary distribution on a finite state space


**Theorem 54**. *If state space finite $\implies \exists$ at least one
positive recurrent communicating class*



**Theorem 55**. *Suppose finite state space. The stationary distribution
$\pi$ for transition matrix $P$ unique $\iff$ there is a unique closed
communicating class*


 
**Corollary 56**. Markov chain on finite state space, and $N \geq  2$
closed classes.\
$C_{i}$ the closed classes of Markov chain and $\pi^(i)$ the stationary
distribution associated with class $C_{i}$ using construction

$$\pi_{j}^{(i)} = 
        \begin{cases}
            \pi_{j}^{C_{i}}, &\text{ if } j \in C_{i} ;\\
            0 , &\text{ if } j \notin C_{i} .
        \end{cases}$$ 
        
Then every stationary distribution of Markov Chain
represented as 

$$\sum_{i=1}^{N} \omega_{i}\pi^{(i)}$$ 

For weights $\omega_{i} \geq 0, \sum_{i=1}^{n} \omega _{i} = 1$


### Limiting distributions on a finite state space


**Theorem 57**. *Let $K = |E| < \infty$ Suppose for some $i \in E$ that

$$\lim\limits_{n \to \infty} p_{ij} (n) = \pi_{j}, \quad \forall  j \in E$$

Then $\pi$ a stationary distribution*


## Time reversibility


**Theorem 58**. *For irreducible, positive recurrent Markov chain
$\{X_{n}\}_{n \in 0,1, \ldots , N }, N \in \mathbb{N}$ assume $\pi$ a
stationary distribution, and $P$ a transition matrix, and
$\forall n \in \{0,1, \ldots  , N\}$ the marginal distribution
$\nu^{(n)}= \pi$

$$Y_{n} = X_{N-n}, \quad \text{The reversed chain defined for } n \in \{0,1, \ldots , N\}$$

We have $Y$ a Markov chain, satisfying

$$P(Y_{n+1} = j \mid  Y_{n} = i) = \frac{\pi_{j}}{\pi_i}p_{ji}$$



**Definition 59**. $X = \{X_{n}: n \in \{0,1, \ldots  , N\}\}$ an
irreducible Markov chain with stationary distribution $\pi$ and marginal
distributions $\nu^{(n)} = \pi,\ \forall n \in \{0,1, \ldots  , N\}$\
Markov chain $X$ **time-reversible** if transition matrices of X and its
reversal $Y$ are the same.*



**Theorem 60**. $\{X_{n}\}_{n \in \{0,1, \ldots  , N\}}$
time-reversible $\iff, \forall  i,j \in E$

$$\pi_i p_{ij} = \pi_{j}p_{ji}$$



**Theorem 61**. *For irreducible chain, if $\exists \pi$ s.t *3.10.1*
holds $\forall  i,j \in E$. Then the chain is time-reversible (once in
its stationary regime) and positive recurrent with stationary
distribution $\pi$


# Properties of the Exponential Distribution

## Definition and basic properties


**Definition 62**. *(Exponential distribution)\
A continuous random variable $X$ is $X \sim Exp(\lambda )$ if it has
density function 

$$f_{X}(x) = 
        \begin{cases}
            \lambda e^{-\lambda x}, &\text{ if } x>0 ;\\
            0, &\text{ if } \text{otherwise}  .
        \end{cases}$$
        
Cumulative distribution function 

$$F_{X}(x) = 
        \begin{cases}
            0, &\text{ if } x \leq 0 ;\\
            1-e^{-\lambda x}, &\text{ if } x>0 .
        \end{cases}$$ 
        
Survival function of the exponential distribution is given by 

$$P(X > x) = 
            \begin{cases}
                1, &\text{ if } x \leq 0 ;\\
                e^{-\lambda x}, &\text{ if } x > 0 .
            \end{cases}$$



**Theorem 63**. $X \sim Exp(\lambda )$ for $\lambda  > 0$ Then*

1.  $E(X) = \frac{1}{\lambda }$

2.  $\lambda X \sim Exp(1)$



**Theorem 64**. Let $n \in \mathbb{N}$ and $\lambda > 0$. Consider
independent and identically distributed random variables
$H_{i}\sim Exp(\lambda )$, for $i = 1, \ldots  , n$\
Let $J_{n} := \sum_{i=1}^{n} H_{i}$ Then $J_{n}$ follows the
Gamma($n,\lambda$) distribution, i.e

$$f_{J_{n}}(t) = \frac{\lambda^n}{\Gamma (n)}t^{n-1}e^{-\lambda t}$$



**Theorem 65**. *Let $n \in \mathbb{N}$ and
$\lambda_1, \ldots  , \lambda_n$. Consider independent random variables
$H_{i} \sim Exp(\lambda_{i})$ for $i = 1, \ldots  , n$. Let
$H := \mathop{\min} \{H_1, \ldots  , H_{n}\}$ Then*

1.  $H \sim Exp(\sum_{i=1}^{n} \lambda i)$

2.  *For any
    $k = 1, \ldots  , n, P(H = H_{k}) = \lambda_{k} / \sum_{i=1}^{n} \lambda_{i}$



**Theorem 66**. *Consider a countable index set $E$ and
$\{H_{i}: i \in E\}$ independent random variables with
$H_{i} \sim Exp(\lambda_{i}), \forall i \in E$. Suppose that
$\sum_{i\in E} \lambda_{i}< \infty$ and set $H := \inf_{i\in E} H_{i}$\
Then the infimum is attained at a unique random value $I$ of $E$ with
probability $1$\
$H, I$ are independent, with
$H \sim Exp(\sum_{i\in E}\lambda_{i} < \infty)$ and
$P(I = i) = \lambda_{i} / \sum_{k\in E} \lambda_{k}$



**Remark 67**. *Suppose we have
$X \sim Exp(\lambda_{X}), Y \sim Exp(\lambda_{Y})$, Then

$$P(X < Y) = P(\mathop{\min}\{X,Y\} = X) = \frac{\lambda_{X}}{\lambda_{X} + \lambda_{Y}}$$


## Lack of memory property


**Theorem 68**. *(Lack of memory property)\
A continuous random variable $X: \Omega \to (0,\infty )$ has an
exponential distribution $\iff$ has the lack of memory property

$$P(X > x + y \mid X >x) = P(X >y),\quad \forall x,y > 0$$



**Remark 69**. *A random variable $X: \Omega \to (0,\infty )$ has an
exponential distribution $\iff$ has lack of memory property:

$$P(X > x + y \mid X >x) = P(X >y),\quad \forall x,y > 0$$


## Criterion for the convergence/divergence of an infinite sum of independent exponentially distributed random variables


**Theorem 70**. *Consider sequence of independent random variables
$H_{i}\sim Exp(\lambda_{i})$ for $0 < \lambda_{i}< \infty$ for all
$i \in \mathbb{N}$ and let $J_\infty = \sum_{i=1}^{\infty} H_{i}$,
Then:*

1.  *If
    $\sum_{i=1}^{\infty} \frac{1}{\lambda_{i}} < \infty \implies P(J_\infty < \infty ) = 1$

2.  *If
    $\sum_{i=1}^{\infty} \frac{1}{\lambda_{i}} = \infty \implies P(J_\infty = \infty ) = 1$



**Lemma 71**. *For $x \geq 1$, we have 

$$\log 
        \left( 1 + \frac{1}{x} \right) \geq \log (2)\frac{1}{x}$$

$$\log (1+x) > \frac{x}{x+1}, \quad \text{for } x > -1$$


# Poisson Process

## Remarks on continuous-time stochastic processes on a countable state space

## Some Definitions


**Definition 72**. *A stochastic process $\{N_{t}\}_{t \geq  0}$ a
**counting process** if $N_{t}$ represents the total number of 'events'
that have occurred up to time $t$\
Having the following properties:*

1.  $N_0 = 0$

2.  $\forall  t \geq  0, N_{t}\in \mathbb{N}_0$

3.  *If $0 \leq  s \leq t, N_{s} \leq N_{t}$

4.  *For $s < t, N_{t} - N_{s} =$ the number of events in interval
    $(s,t]$

5.  *Process is piecewise constant and has upward jumps of size 1 i.e
    $N_{t} - N_{t-} \in \{0,1\}$



**Definition 73**. *Let $(J_{n})_{n \in \mathbb{N}_0}$ a strictly
increasing sequence of positive random variables s.t $J_0 = 0$ almost
surely.\
Define process $\{N_{t}\}_{t \geq 0}$ as

$$N_{t} = \sum_{n=1}^{\infty} \mathbf{1}_{\{J_{n}\leq t\}} ,$$ 

Interpret $J_{n}$ as the (random) time at which the $n$th event occurs.\
The $n$th jump time.*


### Poisson Process: First Definition


**Definition 74**. *Define $o(\cdot )$ notation.\
A function $f$ is $o(\delta )$ if

$$\lim\limits_{\delta  \downarrow 0} \frac{f(\delta )}{\delta } = 0$$

With the following properties*

-   if $f,g$ are $o(\delta )$ then so is $f + g$

-   if $f$ is $o(\delta )$ and $c \in \mathbb{R}$ then $cf$ is
    $o(\delta )$



**Definition 75**. *A **Poisson process** $\{N_{t}\}_{t \geq 0}$ of rate
$\lambda >0$ is a non-decreasing stochastic process with values in
$\mathbb{N}_0$ satisfying:*

1.  $N_0 = 0^1$

2.  *Increments are independent, that is given any $n \in \mathbb{N}$
    and $0 \leq  t_0 < t_1 < t_2 < \ldots  < t_n$ random variables
    $N_{t_0}, N_{t_1} - N_{t_0}, N_{t_2} - N_{t_1}, N_{t_3} - N_{t_2}, \ldots , N_{t_n} - N_{t_{n-1}}$
    are independent*

3.  *The increments are stationary, Given any 2 distinct times
    $0 \leq  s <t, \forall k \in \mathbb{N}_0$

    $$P(N_{t}- N_{s} = k) = P(N_{t-s} = k)$$

4.  There is a 'single arrival', i.e
    $\forall t \geq  0, \delta  > 0, d \to 0$: 
    
    $$\begin{aligned}
                P(N_{t+\delta } - N_{t} = 1) &= \lambda \delta + o(\delta )\\
                P(N_{t+\delta } -N_{t} \geq  2) &= o(\delta )
            \end{aligned}$$


### Poisson Process: Second definition


**Definition 76**. *A **Poisson Process** $\{N_{t}\}_{t \geq 0}$ of rate
$\lambda  > 0$ is a stochastic process with values in $\mathbb{N}_0$
satisfying*

1.  $N_0 = 0$

2.  *Increments are independent, that is given any $n \in \mathbb{N}$
    and $0 \leq  t_0 < t_1 < t_2 < \ldots  < t_n$ random variables
    $N_{t_0}, N_{t_1} - N_{t_0}, N_{t_2} - N_{t_1}, N_{t_3} - N_{t_2}, \ldots , N_{t_n} - N_{t_{n-1}}$
    are independent*

3.  *The increments are stationary, Given any 2 distinct times
    $0 \leq  s <t, \forall k \in \mathbb{N}_0$

    $$P(N_{t}- N_{s} = k) = P(N_{t-s} = k)$$

4.  $\forall  t \geq  0, N_{t} \sim \mathop{Poi}(\lambda t)$

    $$\forall  k \in \mathbb{N}_0, P(N_{t} =k) = \frac{(\lambda t)^k}{k !} e^{-\lambda t}$$


### Right-continuous modification


**Definition 77**. *For 2 stochastic processes
$\{X_{t}\}_{t \geq 0},\{Y_{t}\}_{t \geq 0}$, say $X$ a modification of
$Y$ if 

$$X_{t} = Y_{t},\ \text{almost surely for each} t \geq  0$$

$$P(X_{t} = Y_{t}) = 1, \forall t \geq  0$$ 

Can show that for each
Poisson process, $\exists !$ modification which is *càdlàg*, (right
continuous with left limits).*



**Remark 78**. *Note that the jump chain of the Poisson Process given by
$Z = (Z_{n})_{n \in \mathbb{N}_0}$, where
$Z_{n} = n, n \in \mathbb{N}_0$


### Equivalence of definitions


**Theorem 79**. *Definition *5.3.3, 5.3.4* are equivalent*



**Lemma 80**. *Laplace transform of a Poisson random variable of mean
$\lambda t, X\sim \mathop{Poi}(\lambda t)$ for $\lambda >0, t>0$ is
given by

$$\mathcal{L}_{X}(u) = \exp \{\lambda t[e^{-u} -1]\},\quad \forall u > 0$$


## Some properties of Poisson processes

### Inter-arrival time distribution


**Definition 81**. *Let $\{N_{t}\}_{t \geq  0}$ a Poisson process of
rate $\lambda >0$\
Then the inter-arrival times are independently and identically
distributed exponential random variables with parameter $\lambda$


### Time to the $n^{th}$ event


**Theorem 82**. *We have $\forall  n \in \mathbb{N}$, the time to the
$n^{th}$ event $J_{n}$ follows a Gamma$n,\lambda$ distribution, with
density

$$f_{J_n} (t) = \frac{\lambda^n}{\Gamma (n)}t^{n-1} e^{-\lambda t},\ t > 0$$


### Poisson process: Third definition


**Definition 83**. *A **Poisson process** $\{N_t\}_{t \geq  0}$ of rate
$\lambda > 0$ is a stochastic process with values in $\mathbb{N}_0$ s.t*

1.  $H_1,H_2, \ldots$ denote independently and identically
    exponentially distributed random variables with parameter
    $\lambda  > 0$

2.  *Let $J_0 = 0$ and $J_{n} = \sum_{i=1}^{n} H_{i}$

3.  *Define

    $$N_{t} = \sup \{n \in \mathbb{N}_0  : J_{n} \leq  t  \},\quad \forall t \geq  0$$



**Theorem 84**. *Definitions *5.3.3, 5.3.4, 5.4.4* are equivalent*


### Conditional distribution of the arrival times


**Theorem 85**. *Let $\{N_{t}\}_{t \geq  0}$ be a Poisson process of
rate $l > 0$. Then $\forall n \in \mathbb{N}, t > 0$, the conditional
density of $\begin{pmatrix} J_1, \ldots ,J_n \end{pmatrix}$ given by
$N_{t} = n$ is given by

$$f_{\begin{pmatrix} J_1, \ldots ,J_n \end{pmatrix}} \begin{pmatrix} t_1, \ldots ,t_n | N_{t}= n\end{pmatrix} =
        \begin{cases}
            \frac{n! }{t^n}, &\text{ if }  0 < t_1 < \ldots < t_n \leq  t ;\\
            0, &\text{ otherwise }  .
        \end{cases}$$



**Remark 86**. *The above theorem says, conditional on the fact $n$
events have occured in $[0,t]$, the times
$\begin{pmatrix} J_1, \ldots ,J_n \end{pmatrix}$ at which the events
occur, when considered as unordered random variables are independently
and uniformly distributed on $[0,t]$


## Some extensions to Poisson processes

### Superposition


**Theorem 87**. *Given $n$ independent Poisson processes
$\{N_t^(1)\}_{t \geq  0}, \ldots , \{N_{t}^{(n)}\}_{t \geq  0}$ with
respective rates, $\lambda _1, \ldots  , \lambda_{n}>0$ define

$$N_{t} = \sum_{i=1}^{n} N_{t}^{(i)},\quad t \geq  0$$

Then $\{N_{t}\}_{t \geq  0}$ a Poisson process with rate
$\lambda = \sum_{i=1}^{n} \lambda_{i}$ and is called a **superposition
of Poisson processes***


### Thinning


**Theorem 88**. *Let $\{N_{t}\}_{t \geq  0}$ a Poisson process with rate
$\lambda  > 0$. Assume that each arrival, independent of other arrivals,
is marked as a type $k$ event with probability $p_{k}$ for
$k = 1, \ldots  , n$ where $\sum_{i=1}^{n} p_{i} = 1$.\
Let $N_{t}^{(k)}$ denote the number of type $k$ events in $[0,t]$ . Then
$\{N_{t}^{(k)}\}_{t \geq 0}$ a Poisson process with rate $\lambda p_{k}$
and the processes

$$\{N_t^(1)\}_{t \geq  0}, \ldots , \{N_{t}^{(n)}\}_{t \geq  0}$$

are independent. Each process called a **thinned Poisson process***


### Non-homogeneous Poisson processes


**Definition 89**. *Let $\lambda : [0,\infty) \mapsto (0,\infty )$
denote a non-negative and locally integrable function, called the
**intensity function**\
A non-decreasing stochastic process $N = \{N_{t}\}_{t \geq  0}$ with
values in $\mathbb{N}_0$ called a **non-homogeneous Poisson process**
with intensity function $(\lambda (t))_{t \geq  0}$ if it satifies the
following:*

1.  $N_0 = 0$

2.  $N$ has independent increments*

3.  *'Single arrival' property, For $t \geq  0, \delta  > 0$

    $$\begin{aligned}
                P(N_{t+\delta } - N_{t} = 1) &= \lambda (t)\delta  + o(\delta )\\
                P(N_{t+\delta } - N_{t} \geq  2) &= o(\delta )
            \end{aligned}$$

*Note that (3) also implies that

$$P(N_{t+\delta } - N_{t} = 0) =1 - \lambda (t)  + o(\delta )$$



**Theorem 90**. *Let $N = \{N_{t}\}_{t \geq  0}$ denote a
non-homogeneous Poisson process with continuous intensity function
$(\lambda (t))_{t \geq  0}$ Then

$$N_{t}\sim \mathop{Poi}(m(t)),\quad \text{where}\quad m(t) = \int_0^t    \lambda (s) ds$$

i.e. $\forall t \geq  0, n \in \mathbb{N}_0$

$$P(N_{t}= n) = \frac{[m(t)]^n}{n !}e^{-m(t)}$$


### Compound Poisson processes


**Definition 91**. *Let $\{N_{t}\}_{t \geq  0}$ be a Poisson process of
rate $\lambda  > 0$.\
$Y_1,Y_2, \ldots$ be a sequence of independent and identically
distributed random variables, that are independent of
$\{N_{t}\}_{t \geq 0}$. Then the process $\{S_{t}\}_{t \geq  0}$ with

$$S_{t} = \sum\limits_{i=1}^{N_{i}} Y_{i},\quad t \geq  0$$

is a **compound Poisson process***



**Theorem 92**. *Let $\{S_{t}\}_{t \geq  0}$ a compound Poisson process.
Then for $t \geq  0$

$$E(S_{t}) = \lambda t E(Y_1), \quad Var(S_{t}) = \lambda t E(Y_{1}^{2} )$$

as defined in *Definition 5.5.12**


## The Cramér-Lundberg model in insurance mathematics


**Definition 93**. *The **Cramér-Lundberg model** is given by the
following five conditions.*

1.  *Claim size process is denoted by $Y = (Y_{k})_{k \in \mathbb{N}}$,
    for $Y_{k}$ denoting the positive i.i.d random variables with finite
    mean $\mu  = E(Y)1$ and variance
    $\sigma^{2}  = Var(Y_1) \leq  \infty$

2.  *Claim times occur at the random instants of time

    $$0 < J_1 < J_2 < \ldots  a.s..$$

3.  *The claim arrival process is denoted by

    $$N_{t} = \sup \{n \in \mathbb{N}: J_{n} \leq  t\}, t \geq  0$$

    which is the number of claims in the interval $[0,t]$.*

4.  *The inter-arrival times are denoted by

    $$H_1 = J_1, H_{k} = J_{k}- J_{k-1} , k = 2,3, \ldots$$
    
    and are independent and exponentially distributed with parameter $\lambda$

5.  *sequences $(Y_{k},(H_{k}))$ are independent of each other*



**Definition 94**. *The **Total claim amount** is defined as the process
$(S_{t})_{t \geq  0}$ satisfying 

$$S_{t} = 
        \begin{cases}
            \sum_{i=1}^{N_{t}} Y_{i}, &\text{ if } N_{t} > 0 ;\\
            0, &\text{ if } N_{t} =0 .
        \end{cases}$$ 
        
Observe that the total claim amount is modelled as a compound Poisson process.*



**Theorem 95**. *The total claim amount distribution given by

$$P(S_{t}\leq  x) = \sum_{n=0}^{\infty} e^{-\lambda  t} \frac{(\lambda t)^n}{n !}P
        \left( \sum_{i=1}^{n} Y_{i} \leq  x \right), \quad x \geq  0, t \geq  0$$

and $P(S_{t}\leq  x) = 0$ for $x < 0$



**Definition 96**. *The **risk process** $\{U_{t}\}_{t \geq  0}$ is
defined as 

$$U_{t} = u + ct - S_{t},\quad t \geq  0$$

where $u \geq  0$, the **initial capital** and $c > 0$ denotes the **premium income rate***



**Definition 97**. *We have the following definitions\
*

1.  *The **ruin probability in finite time** is given by

    $$\psi (u,T) = P(U_{t} < 0 \ \text{ for some } t \leq  T ),\ 0 < T < \infty, u \geq  0$$

2.  *The **ruin probability in infinite time** is given by

    $$\psi (u) := \psi (u, \infty ), u \geq  0$$



**Theorem 98**.

$$E(U_{t}) = u + ct - \lambda t \mu  + (c - \lambda \mu )t$$

A minimal requirement for choosing the premium could be 

$$c > \lambda \mu$$

referred to as the **net profit condition***


## The coalescent process


