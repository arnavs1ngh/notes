---
layout: default
title: Math Finance - Options
parent: Year 3
nav_order: 4
math: mathjax3
---

# Mathematical Finance: Intro to Options Pricing - Concise Notes
{: .no_toc }
## MATH60132
{: .no_toc}

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
  
- <a href="/notes/pdfs/year3/LecNotes/MF-Concise.pdf" target="_blank" style="color:#801fff;">**Open Math Finance Concise**</a> - <a href="/notes/pdfs/year3/LecNotes/MF-Concise.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets</span>
  </summary>
  
  - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS1.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 1**</a> - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS1-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS2.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 2**</a> - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS2-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS3.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 3**</a> - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS3-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS4.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 4**</a> - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS4-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS5.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 5**</a> - <a href="/notes/pdfs/year3/probSheets/mf/MF-PS5-Sol.pdf" target="_blank">**Solutions**</a>

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

# What are Derivatives

## Forward Contract


**Definition 1** (Forward Contract). *A **forward contract** is an
agreement to buy or sell an asset at a certain future time for a certain
price, paying a **forward price** at **expiry** of the contract.\
Described by parameters $A$ - the **asset** being bought or sold, $K$ -
the **strike price** and $T$ - the **expiry date**.\
The value of the contract at time $t$ is $P_{T}- K$, where $P_{T}$ the
market price of the asset at time $T$.

$$F_{T} = f(P_{T}), \quad \text{ with } f(x) := x - K, \quad x \in \mathbb{R}$$


## The Binary Option


**Definition 2** (Binary Option). *A **binary option** is a contract
that pays out a fixed amount if the price of the underlying asset is
above a certain level at expiry, and nothing otherwise.\
The **payoff** of a binary option is given by

$$f(P_{T}) = f(x) := 100 \cdot  1_{x\geq K},\quad
        1_{x\geq K} =  \begin{cases}
            1 & \text{ if } P_{T} > K\\
            0 & \text{ if } P_{T} \leq K
        \end{cases} \quad 
        \text{ P\&L options } = 
        \begin{cases}
            100 \cdot  A  - A B_0& \text{ if } P_{T} > K\\
            -A B_0 & \text{ otherwise} 
        \end{cases}$$
        
where $B_0$ the intial value, receiving payoff of \$100 for each contract held.


## Speculation


**Definition 3** (Speculation). ***Speculation** is the act of trading
in the hope of making a profit, but with the risk of making a loss.\
**Hedging** is the act of trading to reduce risk.*


# How to price and hedge derivatives in one-period models

## Pricing by replication


**Principle 4**. **(Law of One Price)*\
If there are 2 possible investments which have ,under all possible
market outcomes, the same value at time $T$ , then they must have the
same value also at all previous times.*



**Principle 5**. **(Pricing via replication)*\
At any time $t \in [0,T]$, the derivative's price must equal the value
of the replicating portfolio.*



**Remark 6**. **(Hedging = - Replicating)*\
*


## Pricing a Binary Option

Assume in the market we can only

-   Trade gold, or

-   Borrow/deposit money from/into a bank

Over a short-time span can assume that interest rate $r = 0$.\
We trade binary options with strike price $K = 59$ and expiry $T = 1$,
and the current price of gold is $P_{0} = 58$.\
$$\underbrace{P_{T}(\omega )}_{\text{Price at maturity} } = 
    \begin{cases}
        61, &\text{ if } \omega  = g ;\\
        56, &\text{ if } \omega = b .
    \end{cases}, \quad \Omega = \{g,b\}, \quad \mathbb{P}(\{g\}) = \mathbb{P}(\{b\}) = \frac{1}{2}$$
With the payoff $B_{T}= 100 \cdot  1_{P_{T} \geq 59 }$
$$B_{T}(\omega ) = 
    \begin{cases}
        100, &\text{ if } \omega  = g ;\\
        0, &\text{ if } \omega =b .
    \end{cases}$$ 
    
Price now by replication

$$\underbrace{V_{T}}_{\text{wealth at maturity} } = V_{T}^{x,h} = x - h \cdot  58 + h \cdot  P_{T}$$

where $h$ the amount of gold bought initially at $P_0$ and $V_0 = x$ the
initial wealth.\
Replicating if final wealth is the same as the payoff

$$\begin{cases}
        x + h \cdot (61- 58) = 100\\
        x + h \cdot (56- 58) = 0
    \end{cases} \implies h = 20, x =40$$

So we get the initial value of the binary option is $V_{0} = 40$.

## Model uncertainty


**Definition 7** (Model uncertainty). ***Model uncertainty** is the
uncertainty about the probability distribution of the future asset
price.\
Introduce *model risk* - the risk that the model we use to price the
derivative is not the correct one.*



**Remark 8** (Storage Costs). *In the real world, there are storage
costs for holding the asset for some assets. e.g. gold, oil, etc. but
not for others e.g. stocks, bonds, etc.*



**Remark 9** (Choosing the right mode). *In the real world, we do not
know the true model.\
We choose the model that best fits the data, and use it to price the
derivative.*



**Remark 10** (Counter-party risk). *In the real world, there is
*counter-party risk* - the risk that the other party in the contract
will not be able to pay.*


## What can be used as underlying

-   Commodities

-   Bonds

-   Stocks

-   Stock indices

-   FX rates

-   Other derivatives

## The bank account and the bond

Assume that we can invest in contract - with value $B_{t}$ at time $t$
given by

1.  $B_0 = 1$ , by normalisation

2.  If discrete time: $B_{t+1} = B_{t}(1+R_{t})$, where $R_{t}$ the
    interest rate for period $(t,t+1)$

    $$B_{t} = B_0 \prod\limits_{s=0}^{t-1} (1 + R_{s} )$$
    
    if $R_{t} = r$ constant then, $B_{t} = B_0 ( 1 +r)^t$

3.  If continuous time: satisfy $dB_{t} = B_{t}R_{t}dt$, where $R_{t}$
    the instantaneous spot rate at $t$ . Then
    $B_{t} = B_{0} e^{\int_{0}^{t} R_{s} ds}$, if $R_{t}= r$ constant
    then $B_{t} = B_0 e^{rt}$

## Justification of the law of one price


**Remark 11** (Transaction costs and arbitrage). *In the real world,
there are transaction costs.\
These costs nay be higher than the price imbalance that we are trying to
exploit - hence no arbitrage.*


## The no-arbitrage principle


**Definition 12** (Arbitrage). ***Arbitrage** is the act of making a
profit without risk.\
**Arbitrage opportunity** is a trading strategy that has a positive
initial value and zero probability of a loss.\
It is a portfolio $L$ that starting with $0$ initial capital, and final
value $V_{T}^L$ s.t $V_T^L \geq  0$ a.s., and
$\mathbb{P}(V_{T}^L < 0) = 0, \mathbb{P}(V_{T}^L > 0) > 0$

-   *If there exists arbitrage, law of supply and demand would quickly
    disappear it.*

-   *If the law of one price fails, then there exists arbitrage*



**Proposition 13**. **(Arbitrage and the Binomial model)*\
Given market with one risky asset $S$ the stock and the bond. We assume
that the interest rate is $r > -1$ and the stock price can only take two
values at time $T$, $S_{T} = S_{0} u$ or $S_{T} = S_{0} d$ with
$0 < d < 1 < u$.\
Then there is no arbitrage if and only if $d < 1 + r < u$.


## Dependence of prices on probabilities


**Definition 14** (Equivalent probabilities). *Say
$\mathbb{P}\sim \mathbb{Q}$ are equivalent if they have the same null
sets.*


## Unspoken Modelling assumptions


**Remark 15** (Linear dependence). *Given discrete time, and some model
for the bonds and shares prices, with stochastic processes $K,H$
represent the number of shares and bonds held between $(t, t+1)$, with
$H$ vector valued quantity $H = (H^1, \ldots , H^m )$ with $H^j$ the
number of shares in the stock of type $j$ of price $S^j$, then we take
$$V_{s}^{(K,H)} := K_{t}B_{s} + H_{t} \cdot S_{s}, \quad \text{ for } s = t, t+1$$
the value of portfolio $(K,H)$ where $S = (S^1, \ldots , S^m )$ the
stock prices.\
Assume that $(K,H) \mapsto V^{(K,H)}$ is linear.*

1.  *Anything behaves linearly only does so on first approximation*

2.  *Linear models easy to work with, and often only ones that are
    solvable.*


## Prices of liquid and illiquid goods

Important to distinguish between illiquid markets and liquid ones; the
latter those in which a good is traded a lot, by many possible
participants - cannot use law of one price in illiquid markets.\
Options pricing deals with how to price illiquid derivatives based on a
liquid underlying.

## Modelling the underlying, not the derivative

## Discounting and Numeraire

> *\"A dollar today is worth more than a dollar tomorrow.\"*


**Definition 16**. **(Nominal vs. Real value)*\
Look at value of $W_{t}$ in terms of $B$ the bond instead of a unit of
currency.
$$\underbrace{\overline{W}_{t}}_{\text{real terms} } = \underbrace{W_{t}}_{\text{nominal terms} } / B_{t}$$
Given constants
$B_{0} = 1, B_1 = B_0 ( 1+ r)  > 0 , r > -1, S_0 \in \mathbb{R}^m$ and
the random vector $S_1 \in \mathbb{R}^m$\
Consider portfolio $(k,h)$ with value
$V_{s}^{k,h} = kB_{s} + h \cdot S_{s}$ at time $s \in \{0,1\}$, more
interested in initial capital - look at $(x,h)$ instead with
$x = k + S_0 h$ the initial capital and $h^j$ number of shares of stock
$S^j$\
Value of $(x,h)$ is
$$V_0^{x,h} = x, \quad V_1^{x,h} = x(1+r) + h \cdot (S_1 - S_0(1+r)), \quad (x,h) \in \mathbb{R} \times \mathbb{R}^m$$
Since $\overline{V}_{t}^{x,h} = V_{t}^{x,h} / B_{t}$ find that
$\overline{V}_0^{x,h} = V_0^{x,h} = x$\
So our value in discounted terms becomes
$$\overline{V}_1^{x,h} = \frac{1}{1+r} (x(1+r) + h \cdot (S_1 - S_0 ( 1+r))) = x + h \cdot  
        \left( \frac{S_1}{1+r} - S_0 \right)$$
$$\overline{V}_{t}^{x,h}  = x+ h \cdot  (\overline{S}_1 - \overline{S}_0), \quad t = 0,1$$
In discounted terms the *gains from trade* between times $0, t$ given by
$$\begin{aligned}
        \overline{V}_{t}^{x,h} - \overline{V}_0^{x,h} &= h \cdot (\overline{S}_1 - \overline{S}_0)\\
        \text{Continuous case: } d \overline{V}_{t}^{x,h} &= H_{t} \cdot  d \overline{S}_{t},\qquad 
        \overline{V}_{t}^{x,h} - \overline{V}_0^{x,h} = \int_0^S H_{t} \cdot  d \overline{S}_{t}
    \end{aligned}$$



**Definition 17** (Numeraire). *A *numeraire* is a portfolio $L$ which
has a strictly positive value a.s. and at all times, ie.e s.t.
$V_{t}^L > 0$ a.s. for all $t$


## Finite Probability Spaces

Pretty straightforward stuff here

## How to find arbitrage

Trading strategy $(x,h) \in \mathbb{R} \times \mathbb{R}^m$ is an
arbitrage if $x = 0$ and
$$\mathbb{P}(\overline{V}_1^{0,h} \geq  0) = 1 \quad \text{ and } \quad \mathbb{P}(\overline{V}_1^{0,h} = 0) <1$$
or equivalently
$$\mathbb{P}(\overline{V}_1^{0,h} < 0) = 0 \quad \text{ and } \quad \mathbb{P}(\overline{V}_1^{0,h} > 0) >0$$
Since $x$ taken to be zero, say '$h$ is an arbitrage'.\
$h$ is an arbitrage if $w^h \in \mathbb{R}^n$ corresponding to random
variable
$\overline{V}_1^{0,h} = h \cdot  (\overline{S}_1 - \overline{S}_0 )$,
satisfies $w_{i}^h \geq  0,\ \forall i$ and $w^h \neq  0$\
Denote $W$ the vector space of discounted payoffs replicable at cost 0

$$W := 
    \left\{ 
        \sum_{j=1}^{m} h^j (\overline{S}_1^{j} - \overline{S}_0^{j}): h \in \mathbb{R}^m
    \right\} = 
    \text{span} 
    \left\{ 
        (\overline{S}_1^{j} - \overline{S}_0^{j})_{j = 1}^m
    \right\}$$
    
Find that

$$\text{The set of all arbitrage payoffs is } W \cap (\mathbb{R}^n_+ \setminus \{0\})$$

No arbitrage iff $W \cap (\mathbb{R}^n_+ \setminus \{0\}) = \{0\}$\
The set of discounted payoffs replicable at cost $x$ is
$x + W = \{x+ w : w \in W\}$, since
$\overline{V}_1^{x,h} = x + \overline{V}_1^{0,h}$

## The Fourier-Motzkin Algorithm

### Simple linear equality

Given $x \in \mathbb{R}^n, b \in \mathbb{R}^m$ and a $m\times n$ matrix
$A$ with rows, $a^1, \ldots , ^m$, to solve system $Ax = b$ write
$x = (y,z)$ with
$y = (x_1, \ldots ,x_{n-1} \in \mathbb{R}^{n-1} , z:= x_{n}\in R )$ so
that $a^i \cdot  x = c^i \cdot  y + d^i z$ for some
$c^i \in \mathbb{R}^{n-1} , d^i \in \mathbb{R}$ rewriting the equations
as $$c^i \cdot  y + d^{i} z = b_{i}, i = 1, \ldots, m$$ in the form
$z = e^i \cdot  y + f^i$ or in form $0 = e^i \cdot  y + f^i$ for some
$e^i \in \mathbb{R}^{n-1} , f^i \in \mathbb{R}$ to find the equivalent
system

$$\begin{cases}
        z = e^i \cdot y + f^i, &\text{ for } i \in I_{\neq } := \{i: d^i \neq 0\};\\
        0 = e^i \cdot  y + f^i, &\text{ for } i \in I_{= } := \{i: d^i = 0\} .    
    \end{cases}$$

$I_{\neq } ,I_=$ disjoint subsets whose union is $\{1, \ldots ,m \}$.\
$I_{\neq } = \varnothing$ iff the last system i.e $Ax= b$ doesn't
involve variable $z$\
In this case: take any $y$ solving system
$0 = e^i \cdot y + f^i, i \in I_=$ and any $z \in \mathbb{R}$\
If instead $I_{\neq } \neq  \varnothing$ then fix arbitrarily
$i^{\ast}  \in I_{\neq }$ then all and only the solutions $(y,z)$ of
above found by taking solution $y$ of system

$$\begin{cases}
        e^i \cdot  y + f^i = e^j \cdot y + f^j, &\text{ for } i,j \in I_{\neq }  ;\\
        0  = e^i \cdot  y + f^i, &\text{ for } i \in I_= .
    \end{cases}$$

and taking $z = e^{i^{\ast} } \cdot  y + f^{i^{\ast} }$\
Above equation has no solution iff so does $Ax = b$\
Iterating the above get sequence of linear systems
$A^i x^i = b^i, i = n, n-1, \ldots ,1$\
Deleting the last variable, one at a time, till we get to
$A^1 x^1 = b^1$ in the only variable $x^1 = x_1 \in \mathbb{R}$\
$A^1 x^1 = b^1$ has no solution $\iff$ so does $Ax = b$\
Can construct all solution of $Ax = b$ from solutions of $A^1 x^1 = b^1$
by back substitution.

### System of linear inequalities

Generalise above to system of linear inequalities $Ax \geq  b$\
Rewriting our system instead as

$$\begin{cases}
        z \geq e^i \cdot  y + f^i, &\text{ for } i \in I_> : \{i: d^i > 0\} ;\\
        z \leq e^i \cdot  y + f^i, &\text{ for } i \in I_< : \{i: d^i < 0\} ;\\
        0 \geq e^i \cdot  y + f^i, &\text{ for } i \in I_= : \{i: d^i = 0\} ;\\
    \end{cases}$$

where $I_<, I_>, I_=$ disjoint sets whose union is $\{1, \ldots ,m \}$,
with $I_< \cup I_> = \varnothing$ iff the last system does not involve
variable $z$\
In this case: take any $y$ solving system
$0 \geq e^i \cdot y + f^i, i \in I_=$ and any $z \in \mathbb{R}$\
If instead $I_< \cup I_> \neq  \varnothing$, if $I_> = \varnothing$ then
$I_< \neq \varnothing$ and all and only solutions $(y,z)$ of above found
by taking solution $y$ of system
$0 \geq  d_{i} + f_{i}\cdot y, i \in I_=$ if $I_= \neq \varnothing$ and
taking any
$z \leq  \underset{i \in I_<}{\mathop{\min} }\ d_{i}+f_{i}\cdot y$\
Analogously if $I_< = \varnothing$ then $I_> \neq  \varnothing$ and take
any $y$ solving $0 \geq d_{i}  + f_{i}\cdot y, i \in I_=$ if
$I_= \neq \varnothing$, and any
$z \geq  \underset{i\in I_>}{\mathop{\max} }\ d_{i} + f_{i}\cdot  y$ and
find all and only solutions of the system .\
In case where $I_>, I_<$ both non-empty, all and only solutions
$x = (y,z)$ obtained by: taking solution $y$ of system $$\begin{cases}
        e^i \cdot  y + f^i \geq e^j \cdot  y + f^j, &\text{ for } i \in I_<, j \in I_>  ;\\
        0 \geq e^i \cdot  y + f^i, &\text{ for } i \in I_=,
    \end{cases}$$ and then choose any
$$z \in \left[ \underset{j \in I_>}{\mathop{\max} }\ e^j \cdot y + f^j, \underset{i \in I_<}{\mathop{\min} }\ e^i \cdot y + f^i \right] .$$
Note conventions,
$\sup \varnothing = -\infty , \inf  \varnothing  = \infty$\
When $I_> = \varnothing$ or $I_< = \varnothing$ then system becomes
$z \leq \underset{i \in I_<}{\mathop{\min} }\ d_{i} + f_{i}\cdot  y$ ,
$z \geq \underset{i \in I_>}{\mathop{\max} }\ d_{i} + f_{i}\cdot  y$
respectively.\
And if $I_< \cup  I_> = \varnothing$ then we have $z \in \mathbb{R}$\
$(y,z)$ solves system iff $y$ solves the rewritten system and $z$ solves
the above range.\
Iterating this procedure get sequence of linear systems
$A^i x^i \geq  b^i, i = n, n-1, \ldots ,1$\
Where $i^{th}$ system has variables
$x^i = \begin{pmatrix} x_1, \ldots ,x_i \end{pmatrix}$ , starting from
$x^n$ and deleting until we get to $x^1 = x_1 \in \mathbb{R}$\
$A^1 x^1 \geq  b^1$ has no solution $\iff$ so does $Ax \geq  b$\
Can construct all solution of $Ax \geq  b$ from solutions of
$A^1 x^1 \geq  b^1$ by back substitution.

## Find arbitrage with the FM algorithm

Can find if a finite market has arbitrage, can use FM algorithm to check
whether $W \cap  \mathbb{R}^n_+ = \{0\}$

## The no-arbitrage and the domination principles


**Principle 18** (Weak Domination Principle). *If there are 2 possible
investments, and the first one has, under all possible market outcomes,
a smaller value then hte second at time $T$, then this holds also at all
previous times.*



**Principle 19** (Pricing via super- and sub-replication). *At any time
$t \in [0,T]$, the derivative's price must be smaller (resp. bigger)
than the value of any super-replicating (resp. sub-replicating)
portfolio.\
We can then define the price bounds for the derivative as the smallest
(resp. biggest) initial capital of a super-replicating (resp.
sub-replicating) portfolio. $$u(X) := \inf \left\{ 
            V_{0}^U : V_{T}^U \geq X_{T}
        \right\}, \quad
        d(x) = \sup 
        \left\{ 
            V_0^D : V_T^D \leq X_{T}
        \right\}$$


We also have trivially
$V_{T}\geq  X_{T} \iff \overline{V}_{T} \geq  \overline{X}_{T}$ and
$V_{T} \leq  X_{T} \iff \underline{V}_{T} \leq  \underline{X}_{T}$

$$u(X) = \inf \left\{
        V_{0}^U : \overline{V}_{T}^U \geq \overline{X}_{T}
    \right\}, \quad
    d(X) = \sup \left\{
        V_{0}^D : \overline{V}_{T}^D \leq \overline{X}_{T}
    \right\}$$


**Principle 20** (Domination Principle). *Say that the Strict Domination
Principle holds if, whenever there are two investments $L,M$ such that*

1.  *the first one has a value a.s. smaller than the second, i.e.
    $\mathbb{P}(\{V_{t}^L \leq V_{t}^M\}) =1$

2.  *the first one has a value not a.s. equal to the second i.e.
    $\mathbb{P}(\{V_{t}^L \neq V_{t}^M\}) > 0$

*at time $t = T$, then necessarily items 1 and 2 hold at all previous
times $t \in [0,T]$.\
We will say that the Domination Principle holds if both the law of one
price and the strict domination principle hold.*



**Remark 21**. *When working in one-period models, items 1 and 2 in
principle in principle 34 are just required to hold for $t = 0$. Since
$V_0$ is known at time 0, it is a constant, so items 1 and 2 become more
simply $V_0^L < V_0^M$



**Theorem 22**. *In the linear one-period marker model, the following
are equivalent:*

1.  *The domination principle (34) holds*

2.  *The strict domination principle holds*

3.  *there exists no-arbitrage*



**Theorem 23**. *In the linear multi-period market model, the Weak
Domination principle (32) holds if and only if there exist no uniform
arbitrage.\
Moreover, the domination principle (34) implies the weak domination
principle (32), which implies teh Law of one price, adn the two opposite
implications do not hold.*


## No-arbitrage prices


**Definition 24** (No-arbitrage price). *$p \in \mathbb{R}$ is a *fair
price* of $X$ in the market $(B,S)$ if the enlarged market $(B,S,X)$,
composed of the original market plus the derivative $X$ traded has price
$X_0 = p$ at time $0$, is also arbitrage-free.*



**Lemma 25**. *The infimum and supremum in the definition of $u(X)$ and
$d(X)$ are achieved.*



**Proposition 26**. *In the arbitrage-free one-period market $(B,S)$, if
a derivative $X$ is*

1.  *replicable, then its fair price $X_0$ is unique, it equals the
    initial value $x$ of any replicating portfolio, and
    $u(X) = X_0 = d(X)$

2.  *not replicable, then the set of its fair prices is the open
    interval $(d(X),u(X))$



**Definition 27**. *A market model $(B,S)$ is called complete if any
derivative $X$ is replicable (in such a market); otherwise its called
incomplete.\
In a complete model all derivatives have a unique price.\
*


## Linear programming, option pricing and arbitrage


**Definition 28**. *A set $P \subseteq \mathbb{R}^k$ is called a
polyhedron if it of the form $$P:= \{
            z \in \mathbb{R}^k: Az \geq  b, \quad Cz \leq  d, \quad Ez = f
        \}$$ where $A,C,E$ are matrices and $b,d,f$ are vectors. A
linear optimisation problem (LP) is a problem of the form
$$\text{minimise/maximise} a + c \cdot z \text{ subject to } z \in P$$
where $a\in R ,c ,z$ are vectors and $P$ is a polyhedron.\
Polyhedra are closed, convex sets.*


## Solving LPs with the FM algorithm

Given a polyhedron $P \subseteq \mathbb{R}^n$ and $c \in \mathbb{R}^n$,
and the LP $$\inf c \cdot z \text{ subject to } z \in P$$ Want to find
$z^{\ast}$ such that $c \cdot z^{\ast} = y^{\ast}$ the infimum\
$z^{\ast}$ the optimiser, $y^{\ast}$ the optimal value.\
If optimiser exists, LP called *solvable*\
To solve the LP, define the polyhedron $$R = \{
        (y,z) : y = c \cdot z, z \in P
    \}$$ Use FM to compute projection $\pi^{n+1}_1(R)$ where
$\pi^{n+1}_1 = \pi_{y}$ defined on
$\mathbb{R}_{y}^1 \times \mathbb{R}_{y}^n$


**Theorem 29**. *$\inf \pi^{n+1}_1 (R)$ equals the optimal value
$y^{\ast}$ of the LP, and $z^{\ast}$ solves the LP if and only if
$(y^{\ast},z^{\ast}) \in R$



**Corollary 30**. *A LP solvable iff its optimal value is finite.*


## How to price a derivative using the FM algorithm

## How to find the optimisers of a LP using the FM algorithm

## Foreign Currency

Describe the money market using 'the bond' and 'the stock'\
If we are trading between two currencies, need to consider
$$B_0^d = 1,\quad B_0^f = 1, \quad B_0^d = 1 + r^d, \quad B_0^f = 1 + r^f$$
Where $B^d$ the domestic bond, and $B^f$ the foreign bond, each with
their own interest rate $>-1$ .\
Also required to specify between domestic and foreign assets each priced
in their own currency.\
A European stock has price (in €) $S$ , so its price in £ is $SE$ where
$E := E_{\text{£}}^{\text{€} }$ - the cost of one €
in £.\
Conversely $U$ a British stock its value $UE^\prime$ in €, where
$E^\prime := E_{\text{€}}^{\text{£}}$ - the cost of
one £ in €.\
Where obviously $E = \frac{1}{E^\prime}$\
A british investor may model the market as $(B^d, S^d, EB^f, ES^f)$
where as a euro investor may model the market as
$(B^d / E, S^d /E, B^f, S^f)$, with each using their respective bond as
the numeraire.\
Clear to see that the two models are equivalent, one is arbitrage
free/complete iff the other is too.

## Formulas for the binomial model

Consider the one-period binomial model $(B,S)$ assume that
$S_0 d = S_1 (T) < S_1 (H) = S_0 u$\
Do not assume that $d < 1 + r < u$, (arbitrage free)\
To price a derivative, try to replicate it, i.e find $x,h$ such that
$$\overline{V}_1^{x,h} (H) = \overline{X}_1(H), \quad \overline{V}_1^{x,h} (T) = \overline{X}_1(T)$$
We have
$\overline{V}_1^{x,h} = x + h (\overline{S}_1 - \overline{S}_0)$, this
system of two equations in two unknowns has a unique solution.

We get the following delta-hedging formula
$$h = \frac{\overline{X}_1(H) - \overline{X}_1(T)}{\overline{S}_1(H) - \overline{S}_1(T)}$$
and the following formula for $\widetilde{p}$ the risk-neutral
probability $$\widetilde{p} = \frac{1 + r - d}{u - d}$$ And the
risk-neutral price
$$\overline{X}_0 = \widetilde{p} \overline{X}_1(H) + (1 - \widetilde{p}) \overline{X}_1(T), \quad X_0 = \frac{1}{1+r}E[X_1]$$

## The Fundamental theorem of Asset Pricing

A probability space $(\Omega ,\mathcal{A} ,\mathbb{P})$, if $\mathbb{Q}$
another probability on $(\Omega ,\mathcal{A} )$\
Say $\mathbb{Q}$ *absolutely continuous* with respect to $\mathbb{P}$,
$\mathbb{Q}\ll \mathbb{P}$ if
$\mathbb{P}(A) = 0 \implies \mathbb{Q}(A) = 0, \forall A \in \mathcal{A}$\
If any null set of $\mathbb{P}$ a null set of $\mathbb{Q}$ say they are
equivalent. $\mathbb{Q}\sim \mathbb{P}$ if
$\mathbb{Q} \ll \mathbb{P}, \mathbb{Q} \gg \mathbb{P}$\
If $\Omega$ finite and every singleton $\{w\}, w \in \Omega$ is
measurable, then $\mathbb{Q} \ll \mathbb{P}$ iff
$\mathbb{P}(\{w\}) = 0 \implies \mathbb{Q}(\{w\}) = 0$\
If $\Omega$ finite and $\mathbb{P}(\{w\}) > 0, \forall w \in \Omega$
then any probability $\mathbb{Q}$ satisfies $\mathbb{Q} \ll  \mathbb{P}$
and $\mathbb{Q} \sim \mathbb{P}$ iff
$\mathbb{Q}(\{w\}) > 0, \forall w \in \Omega$

Proved earlier that the one-period binomial model arbitrage free iff
there exists $\mathbb{Q}$ on $\{H,T\}$ that is equivalent to
$\mathbb{P}$ and such that
$\overline{S}_0 = \mathbb{E}^{\mathbb{Q}}\overline{S}_1$ holds\


**Definition 31**. *A probability $\mathbb{Q}$ on
$(\Omega , \mathcal{A} )$ is an $\overline{S}$-Martingale Measure, if
$\mathbb{Q} \ll  \mathbb{P}$ and
$$\overline{S}_1^j \in L^1(\mathbb{Q}), \quad \overline{S}_0^j = \mathbb{E}^{\mathbb{Q}}[\overline{S}_1^j], \quad \forall j = 1, \ldots ,m$$
Denote $$\mathcal{M} (\overline{S} ) := \{
            \mathbb{Q} \sim \mathbb{P}: \text{ eq. (53) holds} 
        \}, \quad
        \mathbb{M}(\overline{S} ) := \{
            \mathbb{Q} \ll  \mathbb{P}: \text{ eq. (53) holds}
        \}$$ We have the families of all EMM (Equivalent Martingale
Measures) and MM (Martingale measure) for $\overline{S}$ abbreviated as
$\mathcal{M} ,\mathbb{M}$



**Remark 32** (MM in finite $\Omega$ ). *Any random variable defined on
a finite $\Omega$ is integrable with respect to any probability; thus,
if $\Omega$ is finite, the assumption
$\overline{S}_1^j \in L^1(\mathbb{Q})$ automatically satisfied.
Moreover, because of our assumption that
$\mathbb{P}(\{w\}) > 0, \forall w \in \Omega , \mathbb{Q} \ll \mathbb{P}$
is satisfied by any probability $\mathbb{Q}$, and
$\mathbb{Q}\sim \mathbb{P}$ holds iff
$\mathbb{Q}(\{w\}) >0 \forall w \in \Omega$



**Theorem 33** (1st Fundamental Theorem of Asset Pricing). *Consider the
linear one-period market model $(B,S)$. This model is free of arbitrage
$\iff \mathcal{M} (\overline{S} ) \neq  \varnothing$



**Theorem 34** (Seperation Theorem). *If $C,K \subseteq \mathbb{R}^n$
are convex, $C$ is closed and $K$ is compact then there exists
$z\in \mathbb{R}^n,a,b \in \mathbb{R}$ s.t
$$x \cdot  z \leq  a< b \leq y \cdot z, \quad \forall x \in C, \forall y \in K$$
In particular, if $C$ is a vector space then
$x \cdot z = 0, \forall x \in C$



**Theorem 35**. *Consider the linear one-period model $(B,S)$ and assume
that $\Omega$ is finite. In this model there exists no uniform arbitrage
$\iff \mathbb{M}(\overline{S} ) \neq  \varnothing$


## The Risk Neutral Pricing Formula


**Corollary 36** (Risk-Neutral Pricing Formula). *The set of
arbitrage-free prices for an illiquid derivative with payoff $X_1$ in a
one-period arbitrage-free market model $(B,S)$ is
$$\mathcal{AFP} (X_1) = \{
        \mathbb{E}^{\mathbb{Q}}[\overline{X}_1] : \mathbb{Q}\in \mathcal{M} (\overline{S} ) \text{ and } \mathbb{E}^{\mathbb{Q}}[\overline{X}_1] < \infty
    \}$$



**Corollary 37** (Risk-Neutral Pricing Formula). *If $(B,S)$ a
one-period market model with no uniform arbitrage, based on a finite
probability space, the set of prices for an illiquid derivative with
payoff $X_1$ for which the extended market $(B,S,X)$ has no uniform
arbitrage equals $$\{
            \mathbb{E}^{\mathbb{Q}}[\overline{X}_1] : \mathbb{Q}\in \mathbb{M}(\overline{S} ) \text{ and } \mathbb{E}^{\mathbb{Q}}[\overline{X}_1] < \infty
        \}$$



**Remark 38**. *It follows from *Corollary 68* and *Proposition 42* that
the price bounds for $X$ are given by $$\begin{aligned}
        u(X) &= \sup \{
            \mathbb{E}^{\mathbb{Q}}(\overline{X}_1) : \mathbb{Q} \in \mathcal{M} (\overline{S} ), \mathbb{E}^{\mathbb{Q}}[\overline{X}_1] < \infty
        \}\\
        d(x) &= \inf \{
            \mathbb{E}^{\mathbb{Q}}[\overline{X}_1] : \mathbb{Q} \in \mathcal{M} (\overline{S} ), \mathbb{E}^{\mathbb{Q}}[\overline{X}_1] < \infty
        \}
    \end{aligned}$$ sup and inf only attained if and only if $X_1$
replicable.*



**Corollary 39** (Characterisation of replicable derivatives). *$X_1$ is
replicable $\iff  \mathbb{E}^{\mathbb{Q}}[\overline{X}_1]$ is constant
across all $\mathbb{Q}\in \mathcal{M} (\overline{S} )$ s.t.
$\mathbb{E}^{\mathbb{Q}}[\overline{X}_1] < \infty$



**Corollary 40**. *Let $(B,S)$ be a market-model free of arbitrage. Then
$(B,S)$ is complete $\iff$ the EMM is unique (i.e.
$\mathcal{M} (\overline{S} )$ a singleton)*


## Dividends

Stocks can issue dividends, and bonds coupons. Dividends generally paid
every 3 months in the same amount.\
Paying out dividends decreases the value of the shares by the same
amount.\
Denote with $\underbrace{S}_{\text{ex/post-dividend} }$ the price of
share just after the dividend $D$ is paid, and
$\underbrace{D}_{cum-dividend}$ the price of one share just before the
dividend is paid. Then clearly

$$\begin{aligned}
    V = S + D, \quad S \geq  0, D \geq 0\end{aligned}$$

Calculate the forward price $F$ of a stock paying dividends in
one-period model. $F$ depends on $D$, forward contract pays $S_1 - F$
but does not depend on $D$, the stock does pay dividends\
If we buy one share at cost $S_0$, while borrowing $\frac{F+D}{1+r}$
from the bank, we replicate the payment of $S_1 - F$ of the forward
contract, since the final wealth is

$$(S_1 + D) - (1+r) \left( \frac{F+D}{1+r} \right) = S_1 - F$$

Since the initial cost of such replicating strategy is
$S_0 - \frac{F+D}{1+r}$ , setting this to 0 shows that the forward price
of $S$ is $F = S_0 ( 1+ r) - D$

# Multi-Period models

## Measurability

Stochastic processes: a family $X = (X_{t})_{t\in I} ,$ i.e. a function
$I \ni t \mapsto X_{t}$ of random numbers or vectors defined on the same
probability space $(\Omega ,\mathcal{A} ,\mathbb{P})$ indexed by set
$I$\
Say $X \leq  Y$ mean that $X_{t} \leq  Y_{t}$ for all $t\in I$
$$P(\{\omega : X_{t}(\omega ) \leq  Y_{t}(\omega ) \forall t \in I\}) = 1 \quad P(\{\omega : X_{t}(\omega ) \leq  Y_{t}(\omega )\}) = 1, \quad \forall t \in I$$


**Lemma 41** (Doob-Dynkin). *Suppose $X,Y$ random vectors with $n, k$
components, defined on measurable space $\Omega ,\mathcal{A}$, then the
following are equivalent*

1.  *There exists a Borel function $f: \mathbb{R}^k \to \mathbb{R}^n$
    such that $X = f(Y)$

2.  *$X$ is $\sigma (Y)$-measurable, i.e.
    $\sigma (X) \subseteq \sigma (Y)$



**Lemma 42**. *Given random vector $X,Y$ on the same measurable space
$\Omega ,\mathcal{A}$ if $Y$ only takes countably many values
$\{y_{n}\}_{n \in \mathbb{N}}$ then the t.f.a.e*

1.  *There exists a function $f: \mathbb{R}^n \to \mathbb{R}^k$ such
    that $X = f(Y)$

2.  *$X$ takes a constant value $x_{n}$ on each set of the form
    $\{Y = y_{n}\}, n \in \mathbb{N}$



**Definition 43**. *A family
$\mathcal{F}  = (\mathcal{F}_{t})_{t\in \mathbb{T}}$ of
$\sigma$-algebras is called a filtration if
$\mathcal{F}_{s} \subseteq \mathcal{F}_{t}$ for all
$s \leq  t,s,t\in\mathbb{T}$



**Definition 44**. *The stochastic process
$X = (X_{t})_{t\in \mathbb{T}}$ is said to be adapted to the filtration
$\mathcal{F} = (\mathcal{F}_{t})_{t\in \mathbb{T}}$ (or
$\mathcal{F}$-adapted) if $X_{t}$ is $\mathcal{F}_{t}$-measurable for
all $t\in \mathbb{T}$\
The natural filtration generated by a process $X$ is the smallest
filtration $\mathcal{F}^X$ to which $X$ is adapted i.e.
$\mathcal{F}_{t}^X = \sigma ((X_{u})_{u\leq t, u \in \mathbb{T}} )$


## Self-financing portfolios

At time $t$ own $H_{t}^j \in \mathbb{R}$ units of $j^{th}$ asset with
price $S_{t}^j$ and $K_{t}$ units of the bond with price $B_{t}$\
At time $t$ the value of the portfolio is
$K_{t}B_{t} + H_{t} \cdot  S_{t}$\
At time $t+1$ the value of the portfolio is
$K_{t}B_{t+1} + H_{t} \cdot  S_{t+1}$\
At $t+1$ readjust the portfolio to $K_{t+1}$ units of the bond and
$H_{t+1}$ units of the stock, between times $t+1, t+2$\
Assume that these values are equal, i.e. the portfolio is self-financing
$$K_{t}B_{t+1} + H_{t} \cdot  S_{t+1} = K_{t+1}B_{t+1} + H_{t+1} \cdot  S_{t+1},\quad t \in \mathbb{T}, t < T$$
Need to choose the values of variables $K_{t}, H_{t}^1, \ldots ,H_{t}^m$
for each $t\in \mathbb{T}, t < T$ not all these random variables are
free ones - they need to satisfy the $T$ constraints of self-financing.\
Can determine $K_{t+1}$ via induction from $K_{t}$ given $B > 0$ (see
notes for clarification)
$$K_{t+1} = \frac{1}{B_{t+1} } \left( K_{t}B_{t+1} + (H_{t} - H_{t+1})  \cdot  S_{t+1} \right)$$
We have
$$V_{t_{i+1} } - V_{t_{i}} = K_{t_{i}}(B_{t_{i+1}} - B_{t_{i}} ) + H_{t_{i}} (S_{t_{i+1} } - S_{t_{i}})$$
$$V_{t_{k}} - V_0 = \sum_{i=0}^{k-1} H_{t_{i}}(S_{t_{i+1} } - S_{t_{i}}) + (V_{t_{i}}- H_{t_{i}}S_{t_{i}})r$$
Which gives a simpler discounted version
$$\overline{V}_{t}^{x,H} = x + (H \cdot \overline{S} )_{t}, \quad t \in \mathbb{T}$$
where we define the 'discrete-time stochastic integral' of $H$ with
respect to $Y$ by
$$(H \cdot Y )_{t} = \sum_{s=0}^{t-1} H_{s}(Y_{s+1} - Y_{s}),\quad t \in \mathbb{T}$$
If we need to calculate $K_{t}$ can do so using $\overline{V}_{t}$
$$K_{t} = \frac{1}{B_{t}} (V_{t} - H_{t} \cdot S_{t}) = \overline{V}_{t} - H_{t} \cdot \overline{S}_{t}$$

## Arbitrage and arbitrage-free prices


**Definition 45**. *An adapted process $(P_{t})_{t\in \mathbb{T}}$ is an
Arbitrage Free Price for the derivative with payoff $X_{T}$ at maturity
$T$ in the arbitrage-free market model $(B_{t},S_{t})_{t\in \mathbb{T}}$
if $P_{t} = X_{T}$ and the enlarged market
$(B_{t},S_{t},P_{t})_{t\in \mathbb{T}}$ is arbitrage-free.*



**Theorem 46**. *In the linear multi-period market model
$(B_{t},S_{t})_{t\in \mathbb{T}}$ in eq. (66), the Domination principle
holds $\iff$ there exists no arbitrage*



**Theorem 47**. *There exists an arbitrage in the multi-period model
$(B_{t},S_{t})_{t\in \mathbb{T}}$ iff there exists a
$s \in \mathbb{T}, s < T$ s.t there exists an arbitrage in the
one-period model $(B_{t},S_{t})_{t=s,s+1}$


## The multi-period binomial model

Define the $N$-period binomial model on the following filtered
probability space $(\Omega ,\mathcal{A} ,\mathcal{F} ,\mathbb{P}_{p})$

1.  $\Omega = \Omega_{N}= \{ \omega = (\omega_{1} ,\ldots ,\omega_{N}) : \omega_{i} \in \{ H,T \} \}$

2.  $\mathcal{A} = \mathcal{P}(\Omega )$ all subsets of $\Omega$

3.  $\mathcal{F} = (\mathcal{F}_{n})_{n = 0}^N = \sigma ((X_{k})_{k < n} )$

4.  $\mathbb{P}_{p}$ is the probability measure on
    $(\Omega ,\mathcal{A} )$ defined by
    $$\mathbb{P}_{p} (\{ \omega \}) = p^{k} (1-p)^{N-k},\quad \omega = (\omega_{1} ,\ldots ,\omega_{N}) \in \Omega ,\quad k = \sum_{i=1}^{N} \mathbb{I}_{\{ \omega_{i} = H \} }$$
    for $p \in (0,1)$

Notice that a process $Y$ is adapted if, for each $n,Y_{n}$ a function
of $X_{n}:= (X_{k})_{k \leq  n}$\
Or equivalently if $Y_{n}(\omega )$ depends *only* on
$\omega(n) = (\omega_1, \ldots ,\omega_{n} )$ does not depend on
$(;w_{n+1} , \ldots , w_{N} )$\
On $(\Omega ,\mathcal{A} ,\mathcal{F} ,\mathbb{P}_{p})$ we build the
binomial market model $(B,S)$ by asking that

-   The bond price process $B$ given by

    $$B_{n} = B_0 \prod\limits_{k=0}^{n-1} (1+R_{k})$$
    
    for each $n \in \mathbb{T}$, where the interest rate process $R > -1$ is $\mathcal{F}$-adapted

-   The price of underlying given by $$S_{n+1} (\omega ) = 
            \begin{cases}
                (S_{n}U_{n})(\omega ), &\text{ if } X_{n+1} (\omega ) = H ;\\
                (S_{n}D_{n})(\omega ), &\text{ if } X_{n+1} (\omega ) = T .
            \end{cases}$$ where the up and down factors $U_{n},D_{n}$
    are $\mathcal{F}$-adapted processes s.t. $0<D<U$


**Theorem 48**. *The multi-period binomial model is arbitrage free
$\iff D < 1 + R< U$


## Derivatives paying a cashflow

Consider derivatives that provide payoff $P_{t}$ at any time
$t = 0,1, \ldots ,T$ where $T \in \mathbb{N}$ the expiry.\
Process $P = (P_{t})_{t = 0, \ldots ,T }$ called the *cashflow* of
derivative\
Require it to be adapted to the filtration $\mathcal{F}$ of the market
model $(B,S)$\
Can see a derivative with cashflow $P$ seen as the sum over
$n = 0 , \ldots ,N$ of derivatives with payoff $P_{n}$ at expiry $n$\
Denote $P^{n}_{k}$ value at time $k \leq  n$ of derivative which only
has payoff $P_{n}$ at expiry $n$\
And take $H_{k}^n$ the number of shares one should hold at time $k$ to
replicate it.\
Value of $P_{k}^n$ only defined for $k \leq  n$, since derivative has
expiry $n$, and analogously $H_{k}^n$ is defined only for $k \leq  n-1$

$$H_{k} = \sum_{n=k+1}^{N} H_{k}^n, \quad V_{k} = \sum_{n=k}^{N} D_{k}$$

## Derivatives with random maturity


**Definition 49**. *A random variable with values in
$I \cup \{\infty \}$ is called a random time.*



**Definition 50**. *A random time $\tau$ is called a *stopping time* if
$\{\tau \leq t\}$ is $\mathcal{F}_{t}$-measurable for all $t \in I$


## Chooser options

*American call option* - gives right to exercise option and receive
payment $(S_{t} - K)^+$, or instead wait for a later more preferable
time.\
*Bermudan call option* - right to choose stopping time $\tau$ at which
receive payoff $(S_\tau - K)^+$, but only among those $\tau$ which take
values in set $D$ of possible exercise dates

## American Options

Consider American option, which has payoff $I_{\tau }$ at time $\tau$
where $\tau$ is a stopping time, $\tau \leq  T$ is chosen by the buyer.\
$I$ the intrinsic value of the derivative, $\tau$ the exercise date, and
$T$ the expiry of the option.\
The buyer can exercise the option at any time $\tau \leq  N$, only
choosing $\tau (\omega ) = t \leq  N$ if $I_{t}(\omega ) \geq  0$\
If $I_{t}(\omega ) < 0 \forall t$, he will choose $\tau = \infty$ and
the option will expire worthless without being exercised, $I_\infty = 0$

## Conditional probability and conditional Expectation


**Theorem 51**.
*$\mathbb{P}(\cdot  \mid B) : \mathcal{A} \to [0,1], \quad \mathbb{P}(A \mid B) := \mathbb{P}(A \cap B) / \mathbb{P}(B), \quad \text{ for } A \in \mathcal{A}$\
$\mathbb{P}(\cdot \mid B)$ a probability on $\mathcal{A}$, and
$$\mathbb{E}^{\mathbb{P}(\cdot  \mid B)}[X] = \mathbb{E}^{\mathbb{P}}[X 1_B] / \mathbb{P}(B)$$
for any random variable $X \geq  0$, and thus for all $X$ s.t.
$\mathbb{E}^{\mathbb{P}}[|X|1_B] < \infty$



**Definition 52**. *An *atom* of a $\sigma$-algebra $\mathcal{F}$ is a
non-empty $A \in \mathcal{F}$ such that
$B \subseteq A, B \in \mathcal{F}$ imply that either $B = \emptyset$ or
$B = A$\
The family of atoms of $\mathcal{F}$ is denoted by
$\mathcal{A} (\mathcal{F} )$



**Theorem 53**. *Assume $\mathcal{F}$ is a finite $\sigma$-algebra on
$\Omega$, and denote with $A_{\mathcal{F} }(\omega )$ the intersection
of all the $A \in \mathcal{F}$ which contains $\omega \in \Omega$\
Then $A_{\mathcal{F} }$ is the smallest $A \in \mathcal{F}$ which
contains $\omega$. The family $\mathcal{A} (\mathcal{F} )$ of atoms of
$\mathcal{F}$ is a finite partition of $\Omega$, and
$$\mathcal{A} (\mathcal{F} ) = \{A_{\mathcal{F} }(\omega ) : \omega \in \Omega \}$$
so $A_{\mathcal{F} }(\omega )$ is the (only) atom of $\mathcal{F}$
containing $\omega \in \Omega$ . The function $\Pi 
    to \sigma (\Pi )$, mapping finite partitions of $\Omega$ to finite
$\sigma$-algebras on $\Omega$, is a bijection and has inverse
$\mathcal{f} \mapsto \mathcal{A} (\mathcal{F} )$; in particular, if
$\mathcal{F} = \sigma (X)$ for some random variable $X$, which satisfies
the below eq. (79), then
$\mathcal{A} (\mathcal{F} ) = \{X = x_{k}\}^n_{k=1}$
$$P(\{X = x_{k}\}) > 0 \quad \forall k = 1, \ldots ,n, \quad \mathbb{P}\left(X \notin \bigcup_{k=1}^n \{x_{k}\}\right) = 0$$


## Properties of the conditional expectation


**Theorem 54**. *For all $X \in L^1$ and $\sigma$-algebra
$\mathcal{G} \subseteq \mathcal{F}$ the net
$(\mathbb{E}[X \mid \mathcal{H} ])_{\mathcal{H}  \in \mathbb{H}(\mathcal{G} )}$
converges in $L^1$.\
Its $L^1$ limit is called the conditional expectation of $X$ given
$\mathcal{G}$, denoted with $\mathbb{E}[X \mid \mathcal{G} ]$



**Theorem 55**. *$Z := \mathbb{E}[X \mid \mathcal{G} ]$ is
$\mathcal{G}$-measurable and satisfies
$$\mathbb{E}[ZW] = \mathbb{E}[XW] \text{ for all } \mathcal{G}-\text{measurable and bounded } W;$$

*moreover, $Z = \mathbb{E}[X \mid \mathcal{G} ]$ is the unique
$\mathcal{G}$-measurable random variable $Z \in L^1$ which satisfies eq.
(83)*


Properties of conditional expectation:

1.  *Linearity:*
    $\mathbb{E}(X + Z \mid  \mathcal{G} ) = \mathbb{E}[X \mid \mathcal{G} ] + \mathbb{E}[Z \mid \mathcal{G} ]$

2.  *Independence:* If $X$ is independent of $\mathcal{G}$, then
    $\mathbb{E}[X \mid \mathcal{G} ] = \mathbb{E}[X]$\
    In particular, any constant $c \in \mathbb{R}$ satisfies
    $\mathbb{E}(c \mid \mathcal{G} ) = c$, and if $\mathcal{G}$ is the
    trivial $\sigma$-algebra $\{\varnothing , \Omega \}$ then any $X$
    satisfies $\mathbb{E}(X\mid \mathcal{G} ) = \mathbb{E}(X)$

3.  *Taking out what is known:* if $X$ is $\mathcal{G}$-measurable then
    $\mathbb{E}(XZ \mid \mathcal{G} ) = X \mathbb{E}(Z \mid \mathcal{G} )$,
    and in particular $\mathbb{E}(X \mid \mathcal{G} ) = X$

4.  *Iterated conditioning:* if $\mathcal{H} \subseteq \mathcal{A}$ a
    $\sigma$-algebra and $\mathcal{G} \subseteq \mathcal{H}$ then
    $\mathbb{E}(\mathbb{E}(X \mid \mathcal{H} ) \mid \mathcal{G} ) = \mathbb{E}(X \mid \mathcal{G} )$;
    in particular
    $\mathbb{E}[\mathbb{E}(X \mid \mathcal{H} )] = \mathbb{E}[X]$

5.  *Jensen inequality:* if $\phi : \mathbb{R}\to \mathbb{R}$ is convex
    then
    $\mathbb{E}[\phi (X) \mid  \mathcal{G} ] \geq \phi \mathbb{E}[X \mid \mathcal{G} ]$


**Theorem 56**. *Assume $X \in L^{2} (\mathcal{A} )$. Then
$\mathbb{E}[X \mid \mathcal{G} ]$ is the unique $C$ minimiser of
$\mathbb{E}[(X-C)^{2}]$ across $C \in L^{2} (\mathcal{A} )$ .\
Equivalently $\mathbb{E}[X \mid \mathcal{G} ]$ is the unique
$C \in L^{2} (\mathcal{A} )$ s.t.
$$\mathbb{E}[(X-C)W] = 0 \text{ for all } W \in L^{2} (\mathcal{G} )$$



**Lemma 57**. *The set $L^{2}  = L^{2} (\mathbb{P})$ of random variables
$X$ s.t. $\mathbb{E}(X^{2} ) < \infty$ is a vector space, and if
$X,Y \in L^{2} (\mathbb{P})$ then $XY \in L^1 (\mathbb{P})$


## The RNPF in the multi-period binomial model

Compute up and down factors $$U_{n}(\omega ) := \frac{
        S_{n+1} ((\omega (n),H))
    }{
        S_{n}( \omega (n))
    }, \quad 
    D_{n}(\omega ) := \frac{
        S_{n+1} ((\omega (n),T))
    }{
        S_{n}( \omega (n))
    }$$ and define risk-neutral transition-probabilities
$\widetilde{P}_{n}$ and $\widetilde{Q}_{n} = 1 - \widetilde{P}_{n}$ by
asking that
$$\overline{S}_{n}(\omega(n)) = \widetilde{P}_{n}(\omega (n)) \overline{S}_{n+1}((\omega (n), H)) + \widetilde{Q}_{n}(\omega (n)) \overline{S}_{n+1}((\omega (n), T))$$
Solving to get $$\begin{aligned}
    \widetilde{P}_{n}(\omega ) = \widetilde{P}_{n}(\omega(n)) &:= 
    \frac{
        (1 + R_{n}) - D_{n}
    }{
        U_{n} - D_{n}
    }(\omega (n)) , \quad n = 0, \ldots , N-1\\
    \widetilde{Q}_{n}(\omega ) = \widetilde{Q}_{n}(\omega(n)) &:=
    \frac{
        U_{n} - (1 + R_{n})
    }{
        U_{n} - D_{n}
    }(\omega (n)) , \quad n = 0, \ldots , N-1\end{aligned}$$

Compute $V_{n} = V_{n}^{x,G}$
$$\overline{V}_{n}(\omega (n)) = \widetilde{P}_{n}(\omega (n)) \overline{V}_{n+1} ((\omega(n), H)) + \widetilde{Q}_{n}(\omega (n)) \overline{V}_{n+1} ((\omega(n), T))$$
$$\begin{aligned}
    \overline{V}_{n}(\omega (n)) &= \mathbb{E}^{\mathbb{Q} \mid \{X(n) = \omega (n)\}} [\overline{V}_{n+1}]\\
    \overline{V}_{n} &= \mathbb{E}^{\mathbb{Q}} [\overline{V}_{n+1} \mid \mathcal{F}_{n} ]\end{aligned}$$


**Lemma 58**. *The map $\mathbb{Q} \mapsto \widetilde{P}$ given by
equation (89) is a bijection between*

1.  *probabilities $\mathbb{Q}$ on $(\Omega ,\mathcal{A} )$

2.  *$\mathcal{F}$-adapted processes
    $\widetilde{P} = (\widetilde{P} )_{n \leq N}$ on
    $(\Omega ,\mathcal{A} )$ with values in $[0,1]$

*Moreover $\mathbb{Q} \sim \mathbb{P} \iff  O < \widetilde{P}  < 1$


## The FTAP in the multi-period setting

As $\widetilde{P}$ is determined by eq. (85) which is eq. (88) with
$V = S$, eq. (91) states that $\mathbb{Q}$ satisfies
$$\overline{S}_{n} = \mathbb{E}^{\mathbb{Q}} [\overline{S}_{n+1} \mid  \mathcal{F}_{n}]$$


**Definition 59**.

1.  *An adapted process $Y = (Y_{t})_{t\in \mathbb{T}}$ a martingale if
    $Y_{t} \in L^{1}(\mathbb{P})$ and
    $\mathbb{E}[Y_{t}\mid \mathcal{F}_{s}]$ for each
    $s \leq t, s,t \in \mathbb{T}$

2.  *A probability $\mathbb{Q}$ on $\mathcal{F}$ is a *Martingale
    Measure* if $\overline{S}$ is a martingale on
    $(\Omega ,\mathcal{A},\mathcal{F} ,\mathbb{Q})$\
    Say $\overline{S}$ a $\mathbb{Q}$-martingale\
    Such $\mathbb{Q}$ is an EMM if $\mathbb{Q} \sim \mathbb{P}$. The set
    of EMM denoted by $\mathcal{M} (\overline{S} )$



**Theorem 60** (1st FTAP). *A multi-period market
$(B_{t},S_{t})_{t\in \mathbb{T}}$ is arbitrage free
$\iff \mathcal{M} (\overline{S} ) \neq  \varnothing$



**Corollary 61**. *Let $(B_{t}, S_{t})_{t \in \mathbb{T}}$ be a
multi-period market free of arbitrage. Then $(B,S)$ is complete $\iff$
the EMM is unique (i,e. $\mathcal{M} (\overline{S} )$ is a singleton)*


## Permutation-invariant processes and recombinant trees

To find AFP $Y := (Y_{n})_{n<N}$ for binomial model - work by backward
induction. Setting
$\overline{V}_{n} = \overline{V}_{n}^{x,G} := \overline{Y}_{n}$ and
using the RNPF eq. (91) to compute
$\overline{V}_  {n} = \mathbb{E}^{\mathbb{Q}}(\overline{V}_{n+1} \mid  \mathcal{F}_{n} )$
and $G_{n}$ for each $0 \leq  n \leq N-1$

**Problem:** amount of computation grows exponentially with $n$ - as its
proportional to the $\#$ of paths
$(\omega_1, \ldots ,:w_{n} ) = \#\{H,T\}^n = 2^n$

**Solution** - consider for $(B,S)$ only those adapted processes $W$
such that for each $n$ , $W_{n}$ takes the same value at the point
$(\omega_1, \ldots, \omega_{n})$ as at the point
$\begin{pmatrix} \sigma(\omega_1), \ldots ,\sigma(\omega_n) \end{pmatrix}$,
where $\sigma$ any permutation of $\Omega_{n} = \{H,T\}^n$\
Call such $W$ *permutation-invariant*\
If $W$ is permutation-invariant $W_{n}$ takes at most $n+1$ possible
values, as it is a function only of the number $k = 0, \ldots, n$ of
coin tosses which results in Heads. As the number of values of $W_{n}$
grows linearly in $n$ - instead of exponentially - the amount of
computation is reduced.

![Recombinant tree](figs/recomb.jpg){width="40%"}

Suppose $(B,S)$ is permutation invariant. If the value
$\overline{Y}_{n}$ of a derivative at time $N$ depended just on
$(B_{N},S_{N})$, i.e. $\overline{Y}_{n} = f_{N}(B_{N},S_{N})$, then we
would only need to keep track of the $N+1$ values of $(B_{N},S_{N})$ to
compute $\overline{Y}_{n}$

For a general derivative we have
$\overline{Y}_{n} = f_{N}((B_{k},S_{k})_{k\leq N} )$, we would still
only need to keep track of
$\sum_{k=0}^{n} (k+1) = \frac{1}{2}(N+1)(N+2) \sim N^{2}$ values - which
is much less than $2^{N}$

## Independence


**Definition 62**. *Given a probability space
$(\Omega ,\mathcal{A} ,\mathbb{P})$, we say two events
$A,B \in \mathcal{A}$ are independent if
$\mathbb{P}(A \cap  B) = \mathbb{P}(A) \mathbb{P}(B)$



**Definition 63**. *Given probability space
$(\Omega ,\mathcal{A} ,\mathbb{P})$ say finitely many events
$F_{i}\in \mathcal{A} , i \in J = \{i_{j}\}_{j=1}^n$ are
$\mathbb{P}$-independent if we have
$$\mathbb{P}(G_{i_1} \cap  \ldots \cap  G_{i_n}) = \prod\limits_{j=1}^{n} \mathbb{P}(G_{i_j})$$
For any $G_{i_j} \in \{F_{i_{j}}, F_{i_{j}}^c\}, j = 1, \ldots, n$



**Definition 64**. *Given probability space
$(\Omega ,\mathcal{F} ,\mathbb{P})$, an arbitrary collection of events
$G_{i}\in \mathcal{A} ,i \in I$ are independent if $\{G_{i}\}_{i\in J}$
are independent for every finite $J \subseteq I$\
Arbitrary collection $\{\mathcal{G}_{i}\}_{i\ni I}$ of
sub-$\sigma$-algebras of $\mathcal{A}$ are independent if for every
choice of sets $G_{i}\in \mathcal{G}_{i}, i \in I$, the sets
$\{G_{i}\}_{i\in I}$ are independent\
An arbitrary collection of random vectors
$X_{i}: \Omega  \to \mathbb{R}^{k_{i}}, i \in I$ are independent if the
$\sigma$-algebras $\{\sigma(X_{i})\}_{i\in I}$ are independent*



**Theorem 65**. *Given random vectors
$X_{j}: \Omega  \to \mathbb{R}^{k_{j}}, j = 1, \ldots ,n$ the following
are equivalent:*

1.  *$(X_{j})_{j}$ are independent*

2.  *$$\begin{aligned}
                \mathbb{E}
                \left[ 
                  \prod\limits_{k=1}^{n} f_{j}(X_{j})
                \right] = \prod\limits_{k=1}^{n} \mathbb{E} [ f_{j} (X_{j})]
              \end{aligned}$$

    *holds for any bounded and Borel functions
    $f_{j}: \mathbb{R}^{k_{j}} \to \mathbb{C}, j = 1, \ldots, n$ of the
    form
    $f_{j}(x) = \exp (i \cdot  t_{j} \cdot x), t_{j} \in \mathbb{R}^{k_{j}}$

3.  *eq. (97) holds for any functions
    $f_{j}: \mathbb{R}^{k_{j}} \to \mathbb{C}, j = 1, \ldots, n$ of the
    form
    $f_{j}(x) = \exp (i \cdot  t_{j} \cdot  x), t_{j} \in \mathbb{R}^{k_{j}}$



**Remark 66**.

1.  *if $X_{j}$ has values in $\mathbb{R}^{+}$ for each $j$ and eq. (97)
    holds for every $f_{j}$ of the form
    $f_{j}(x) = \exp (t_{j}x), t_{j}\in \mathbb{R}$, or*

2.  *if each $X_{j}$ has values in a bounded set $B_{j}$
    ($\mathbb{P}(X_{j} \notin B_{j}) = 0$ ) and eq. (97) holds for every
    $f_{j}$ which is a polynomial*

*Then the $(X_{j})_{j}$ are independent*



**Remark 67**. *For $\mathbb{T} = \{0,1, \ldots, N\}$ or
$\mathbb{T} = \mathbb{N}$

1.  *$(X_{i})_{i\in \mathbb{T}}$ are independent*

2.  *For every $J,K \subseteq \mathbb{T}$ s.t. $J \cap K = \varnothing$
    the two random vectors $Y := (X_{i})_{i\in J}$ and
    $Z:= (X_{i})_{i\in K}$ are independent*

3.  *For every $k \in \mathbb{T} \setminus \{0\}$ , the two random
    vectors $X(k-1):= (X_{i})_{i = 0}^{k-1}$ and $X_{k}$ are
    independent*



**Theorem 68**. *Given two $\sigma$-algebras
$\mathcal{B} ,\mathcal{C} \subseteq \mathcal{A}$, the following are
equivalent:*

1.  *$\mathcal{B} ,\mathcal{C}$ are $\mathbb{P}$-independent*

2.  *for all $B \in \mathcal{B}$ the random variable
    $\mathbb{P}(B \mid \mathcal{C} )$ is constant*

3.  *for every $\mathcal{B}$-measurable $Y \in L^1 (\mathbb{P})$, the
    random variable $\mathbb{E}(Y \mid \mathcal{C} )$is constant*

*and in this case $\mathbb{P}(B \mid \mathcal{C} ) = \mathbb{P}(B)$, and
$\mathbb{E}[Y \mid  \mathcal{C} ] = \mathbb{E}[Y]$



**Theorem 69**. *If two random variables $X,Y$ take finitely many values
$\{x_{i}\}_{i=1}^n ,\{y_{j}\}_{j=1}^m$ then $X,Y$ independent iff, for
each $i,j$ the two sets $\{X = x_{i}\}, \{Y = y_{i}\}$ are independent*



**Remark 70**. *If $\mathcal{B}$ finite, if
$\mathbb{P}(B \mid  \mathcal{C} ) = \mathbb{P}(B)$ holds for every atom
of $B$ of $\mathcal{B}$ then it holds for every finite union of atoms,
i.e. for every $B \in \mathcal{B}$ ; moreover if
$\mathbb{P}(B \mid \mathcal{C} ) = \mathbb{P}(B)$ then
$$\mathbb{P}(B^c \mid C) = 1 - \mathbb{P}(B \mid \mathcal{C} ) = 1 - \mathbb{P}(B) = \mathbb{P}(B^c)$$
Thus, a random variable $X$ which only takes 2 values $x_1,x_2$ is
independent of a $\sigma$-algebra $\mathcal{G}$ iff
$\mathbb{P}(X = x_1 \mid \mathcal{G} )$ is constant*



**Remark 71**. *Combining remarks 116 + 119.\
Follows that random variables $(X_{i})_{i = 1}^N$ with values in
$\{H,T\}$ are $\mathbb{P}$-independent iff, for every
$k \in \{1, \ldots, N-1\}$
$$\mathbb{P}(X_{k+1} = H \mid \sigma \begin{pmatrix} X_1, \ldots ,X_n \end{pmatrix})\quad \text{ is constant}$$



**Remark 72**. *WARNING: if $X,Y,Z$ are pairwise independent, then not
necessarily $X,Y,Z$ are independent*


## Pricing and hedging fast using Markov Processes


**Definition 73**. *An adapted process $X = (X_{t})_{t\in \mathbb{T}}$
on a filtered prob. space
$(\Omega ,\mathcal{A} ,\mathcal{F} ,\mathbb{P})$ is Markov if
$$\forall f \text{ Borel-measurable } ,\forall s \leq t, s,t \in \mathbb{T}, \quad \mathbb{E}(f(X_{t}) \mid \mathcal{F}_{s}) = \mathbb{E}(f(X_{t}) \mid X_{s})$$



**Lemma 74** (Independence Lemma). *If $X$ a $\mathbb{R}^k$-valued, and
$Y$ a $\mathbb{R}^n$-valued random vector on
$(\Omega ,\mathcal{A} ,\mathbb{P}), \mathcal{G}  \subset \mathcal{A}$ a
$\sigma$-algebra,$X$ is $\mathcal{G}$-measurable and $Y$ is independent
of $\mathcal{G}, f: \mathbb{R}^k \times  \mathbb{R}^n \to \mathbb{R}$ a
Borel function, then
$$\mathbb{E}(f(X,Y) \mid \mathcal{G} ) = g(x) \quad \text{for } \quad g(x) = \mathbb{E}(f(x,Y)), \quad g:\mathbb{R}^k \to \mathbb{R}$$



**Corollary 75**. *If a $\mathcal{F}$-adapted process $W$ satisfies
$W_{k+1} = f_k (W_{k},X_{k+1} )$ for each $k \in \mathbb{Z}$, where
$f_{k}$ is some Borel function and $X_{k+1}$ is independent of
$\mathcal{F}_{k}$, then $W$ is Markov and
$\mathbb{E}(f(W_{k+1} \mid \mathcal{F}_{k})) = g(W_{k})$ for all
$k \in \mathbb{Z}$, where $$g(\omega ) := \mathbb{E}[
            f(f(\omega ,X_{k+1} ))
        ]$$


# Continuous Time models

Lol $$NON\ EXAMINABLE\ MATERIAL$$
