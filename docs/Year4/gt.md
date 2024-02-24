---
layout: default
title: Game Theory
parent: Year 4
nav_order: 0
math: mathjax3
---

# Intro to Game Theory - Concise Notes

{: .no_toc }

## MATH70141

{: .no_toc}

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
  
- <a href="/notes/pdfs/year4/game/GT-Concise.pdf" target="_blank" style="color:#801fff;">**Open Game Theory Concise**</a> - <a href="/notes/pdfs/year4/game/GT-Concise.pdf" download>**Download**</a>
- <a href="/notes/pdfs/year4/game/GT-Concise.pdf" target="_blank" style="color:#801fff;">**Open Game Theory Lecture notes**</a> - <a href="/notes/pdfs/year4/game/GT-Concise.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets</span>
  </summary>
  
  - <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS1.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 1**</a> - <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS1-Sol.pdf"  target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS2.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 2**</a> - <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS2-Sol.pdf"  target="_blank">**Solutions**</a>

- <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS3.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 3**</a> - <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS3-Sol.pdf"  target="_blank">**Solutions**</a>

- <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS4.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 4**</a> - <a href="/notes/pdfs/year3/probSheets/alg3/ALG3-PS4-Sol.pdf"  target="_blank">**Solutions**</a>

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

# Prelude

## Strategies

**Definition 1**. A **move** refers to the action a player must make on
their turn to progress from one game position to the next position

**Definition 2**. An **outcome** of a game refers to the final result of
a game once the game has been played

**Definition 3**. A **strategy** for a player involves a complete
description of all the moves that will be made in any game position,
including responses to any random moves, and the opponent's moves. A
strategy is a program which can be followed to play the game
mechanically.

**Definition 4**. A **pure strategy** is a strategy that doesn't involve
any self-imposed random chances of playing any moves.

**Definition 5**. **Finite game** - if all players in the game have a
finite number of pure strategies. If at least one player has an infinite
number of pure strategies, the game is called an **infinite game**.

# Dominance, Best Response and Equilibria

Define the following notation to start with

note
_Note 1_. Player $A$ will have pure strategies
$A_{s} = \{a_1, a_2, \ldots  \}$, the set may be finite or infinite.
Similarly, player $B$ will have pure strategies
$B_{s} = \{b_1, b_2, \ldots  \}$

Denote by $g_{A}(a_{i},b_{j})$ the payoff to player $A$ when player $A$
plays pure strategy $a_{i}$ and player $B$ plays pure strategy $b_{j}$.

**Definition 6**. Strategy $a \in A_{s}$ is **strictly dominated** by
another strategy $a^\prime \in A_{s}$ if
$$g_{A}(a,b) < g_{A}(a^\prime,b) \quad \forall b \in B_{s}$$

**Definition 7**. In an $n$-player game, a strategy $s_{i} \in S_{i}$
for player $i$ is **strictly dominated** by another strategy
$s_{i}^\prime \in S_{i}$ if
$$g_{i}(s_{i},s_{-i}) < g_{i}(s_{i}^\prime,s_{-i}) \quad \forall s_{-i} \in S_{-i}$$
$s_{-i}$ denotes the strategies of all players other than $i$

**Definition 8**. $a \in A_{s}$ is weakly dominated by
$a^\prime \in A_{s}$ if
$$g_{A}(a,b) \leq g_{A}(a^\prime,b) \quad \forall b \in B_{s}$$ and
there exists at least one $b \in B_{s}$ such that the inequality is
strict

**Definition 9**. In an $n$-player game, a strategy $s_{i} \in S_{i}$
for player $i$ is weakly dominated by another strategy
$s_{i}^\prime \in S_{i}$ if
$$g_{i}(s_{i},s_{-i}) \leq g_{i}(s_{i}^\prime,s_{-i}) \quad \forall s_{-i} \in S_{-i}$$
and there exists at least one $s_{-i} \in S_{-i}$ such that the
inequality is strict

**Definition 10**. In an $n$-player game, a strategy $s_{i} \in S_{i}$
for player $i$ is **payoff equivalent** to another strategy
$s_{i}^\prime \in S_{i}$ if
$$g_{i}(s_{i},s_{-i}) = g_{i}(s_{i}^\prime,s_{-i}) \quad \forall s_{-i} \in S_{-i}$$

**Definition 11**. In an $n$-player game, a strategy $s_{i} \in S_{i}$
for player $i$ is a **best response** to a strategy profile
$s_{-i} \in S_{-i}$ if
$$g_{i}(s_{i},s_{-i}) \geq g_{i}(s_{i}^\prime,s_{-i}) \quad \forall s_{i}^\prime \in S_{i}$$

**Proposition 12**. _A dominated strategy is never a best response_

## Equilibria

**Definition 13** (Nash Equilibrium). An **equilibrium** of an
$n$-player game is a strategy profile $s \in S$ such that
$$g_{i}(s_{i},s_{-i}) \geq g_{i}(s_{i}^\prime,s_{-i}) \quad \forall s_{i}^\prime \in S_{i}$$
for all players $i$.

## Iterative Deletion of Dominated Strategies

**Proposition 14**. _In an $N$-player game, with strategy sets
$S_1, S_2, \ldots , S_{N}$, let $s_{i}, s_{i}^\prime$ be two strategies
for player $i$. Suppose $s_{i}^\prime$ weakly dominates or is payoff
equivalent to $s_{i}$. Consider game $G^\prime$ with identical payoffs
as $G$ but where $S_{i}$ is replaced by $S_{i} - \{s_{i}\}$, Then:\_

1.  _Any Nash equilibrium of $G^\prime$ is a Nash equilibrium of $G$_

2.  _If $s_{i}$ is dominated by $s_{i}^\prime$, then $G$ and $G^\prime$
    have the **same** equilibria\_

**Proposition 15**. _Consider game $G$ that upon performing iterative
deletion of dominated strategies, results in game $G^\prime$ with a
single strategy profile. Then, the single strategy profile is the unique
equilibrium of $G$._

# Mixed Equilibria

## Mixed Strategies

**Definition 16**. A **mixed** strategy for a player is a self-imposed
randomization over the player's pure strategies. A mixed strategy is a
probability distribution over the pure strategies. A mixed strategy
$\alpha$ for player $A$ is denoted as $$\begin{aligned}
        \alpha &= (p_1, p_2, \ldots , p_n), \quad \text{or} \\
        \alpha &= p_1 a_1 + p_2 a_2 + \ldots + p_n a_n, \quad \text{where} \quad \sum_{i=1}^{n} p_i = 1, \quad 0 \leq p_i \leq 1
    \end{aligned}$$ We extend the pure strategy set $A_{s}$ to the more
general **mixed strategy set**, $\mathbb{A}_{s}$ - the infinite set of
all possible $\alpha$ for player $A$.

**Definition 17**. Let player $A$ have pure strategy set
$A_{s} = \{a_1, \ldots , a_{n}  \}$ and player $B$ have pure strategy
set $B_{s} = \{b_1, \ldots , b_{m}  \}$.

If player $A$ choses to play the mixed strategy
$\alpha = (p_1, \ldots , p_{n}  ) \in \mathbb{A}_{s}$ and player $B$
choses to play the mixed strategy
$\beta = (q_1, \ldots , q_{m}  ) \in \mathbb{B}_{s}$, then the
**expected payoff** to player $A$ is
$$g_{A}(\alpha,\beta) = \sum_{i=1}^{n} \sum_{j=1}^{m} p_i q_j g_{A}(a_i,b_j)$$
If $A_{s}, B_{s}$ are infinite sets then the summation is replaced by
integration.
$$g_{A}(\alpha ,\beta ) = \int_{x} \int_{y} g_{A}(x,y) f_{A}(x) f_{B}(y)\, dx \, dy$$
where $f_{A}(x), f_{B}(y)$ are the probability density functions of the
mixed strategies $\alpha, \beta$ respectively.

**Definition 18**. A pair of mixed strategies $\alpha^{\ast}$ for $A$
and $\beta^{\ast}$ for $B$, are said to be in mixed equilibrium if

$$
\begin{aligned}
        g_{A}(\alpha^{\ast},\beta^{\ast}) &\geq g_{A}(\alpha,\beta^{\ast}) \quad \forall \alpha \in \mathbb{A}_{s} \\
        \text{and} \quad g_{B}(\alpha^{\ast},\beta^{\ast}) &\geq g_{B}(\alpha^{\ast},\beta) \quad \forall \beta \in \mathbb{B}_{s}
    \end{aligned}
$$

## Finding mixed equilibria by considering Pure strategies

**Proposition 19**. _For any mixed strategies $\alpha^{\ast}$ of player
$A$ and $\beta^{\ast}$ of player $B$, then $$\begin{aligned}
\mathop{\max}_{\alpha \in \mathbb{A}_{s}}\{ g_{A}(\alpha,\beta^{\ast})\} &= \mathop{\max}_{a \in A_{s}}\{ g*{A}(a,\beta^{\ast})\},\\
\mathop{\max}*{\beta \in \mathbb{B}_{s}}\{ g_{B}(\alpha^{\ast},\beta)\} &= \mathop{\max}_{b \in B_{s}}\{ g*{B}(\alpha^{\ast},b)\}
\end{aligned}$$*

**Definition 20**. Let $c$ a constant. A mixed strategy $\alpha^{\ast}$,
for player $A$ is an **equaliser strategy** if
$$g_{A}(\alpha^{\ast},b) = c \quad \forall b \in \mathbb{B}_{s}$$

Similarly for player $B$

**Proposition 21**. _In a 2-player game, if $\alpha^{\ast}$ is an
equaliser strategy for $A$ using $B$'s payoffs and $\beta^{\ast}$ is an
equaliser strategy for $B$ using $A$'s payoffs, then
$(\alpha^{\ast},\beta^{\ast})$ is a mixed equilibrium_

## Geometry of Games

note
_Note 2_. Define the convex hull of a set of points as the smallest
convex set that contains all the points. For a set of points
$\{x_1, \ldots, x_{n} \}$ with each $x_{i} \in \mathbb{R}^m$, form their
convex hull as
$$C = \left\{ \sum_{i=1}^{n} \lambda_{i} x_{i} \mid \lambda_{i} \geq 0, \sum_{i=1}^{n} \lambda_{i} = 1 \right\}$$

## Existence of an equilibrium

**Theorem 22** (Nash, 1951). _Every finite game has at least one mixed
equilibrium_

## Finding equilibria by checking subgames

## The upper envelope method

## Degenerate games

**Definition 23** (Degenerate game). A 2-player game is said to be
**degenerate** if some player has a mixed strategy that assigns positive
probability to exactly $k$ pure strategies so that the other player has
more than $k$ pure strategies.

# Zero-sum games

## Max-min and Min-max Strategies

**Definition 24**. A **max-min** strategy
$\hat{\alpha}  \in \mathbb{A}_{s}$ of player $A$ is a strategy such that
$$\mathop{\min}_{\beta \in \mathbb{B}_{s}}\{ g_{A}(\hat{\alpha},\beta)\} = \mathop{\max}_{\alpha \in \mathbb{A}_{s}} \left\{ \mathop{\min}_{\beta  \in \mathbb{B}_{s}}\{ g_{A}(\alpha,\beta)\} \right\}$$
assuming that the maxima and minima exist. This also defines the
**max-min payoff** to player $A$

**Definition 25**. A **min-max** strategy
$\hat{\beta}  \in \mathbb{B}_{s}$ of player $B$ is a strategy such that
$$\mathop{\max}_{\alpha \in \mathbb{A}_{s}}\{ g_{B}(\alpha,\hat{\beta})\} = \mathop{\min}_{\beta \in \mathbb{B}_{s}} \left\{ \mathop{\max}_{\alpha  \in \mathbb{A}_{s}}\{ g_{B}(\alpha,\beta)\} \right\}$$
This also defines the **min-max payoff** to player $B$

**Proposition 26**. _In a zero-sum game, for
$\alpha \in \mathbb{A}_{s}$, then
$$\mathop{\min}_{\beta \in \mathbb{B}_{s}}\{ g_{A}(\alpha,\beta)\} = \mathop{\min}_{b \in B_{s}}\{ g_{A}(\alpha,b)\}$$
Similarly for $\beta \in \mathbb{B}_{s}$, then
$$\mathop{\max}_{\alpha \in \mathbb{A}_{s}}\{ g_{B}(\alpha,\beta)\} = \mathop{\max}_{a \in A_{s}}\{ g_{B}(a,\beta)\}$$\_

## Relationship of Equilibria and Max-min/Min-max Strategies

**Proposition 27**. \*In a finite zero-sum game with
$\hat{\alpha} \in \mathbb{A}_{s}, \hat{\beta} \in \mathbb{B}_{s}$ then
$(\hat{\alpha},\hat{\beta})$ is a mixed equilibrium if and only if
$\hat{\alpha}$ is a max-min strategy for $A$ and $\hat{\beta}$ is a
min-max strategy for $B$, and

$$
\mathop{\max}_{\alpha \in \mathbb{A}_{s}} \left\{
            \mathop{\min}_{\beta \in \mathbb{B}_{s}}\{ g_{A}(\alpha,\beta)\}
        \right\}
        =
        \mathop{\min}_{\beta \in \mathbb{B}_{s}} \left\{
            \mathop{\max}_{\alpha \in \mathbb{A}_{s}}\{ g_{B}(\alpha,\beta)\}
        \right\}$$*


## The Minimax theorem of Von Neumann


**Theorem 28** (Von Neumann, 1928). *In a finite zero-sum game then
$$\mathop{\max}_{\alpha \in \mathbb{A}_{s}} \left\{
            \mathop{\min}_{\beta \in \mathbb{B}_{s}}\{ g_{A}(\alpha,\beta)\}
        \right\}
        = v =
        \mathop{\min}_{\beta \in \mathbb{B}_{s}} \left\{
            \mathop{\max}_{\alpha \in \mathbb{A}_{s}}\{ g_{B}(\alpha,\beta)\}
        \right\}$$ where $v$ is the unique max-min payoff to $A$ (and
cost to $B$), called the **value** of the game.*


## Finding solutions in small zero-sum games


**Proposition 29**. *Consider 2 zero-sum games $G, G^\prime$, where
$G^\prime$ is obtained from $G$ by deleting a weakly dominated strategy
of one of the players. Then any equilibrium of $G^\prime$ is also an
equilibrium of $G$, and $G$ and $G^\prime$ have the **same value**.*


# Cooperative Games

## Bargaining sets


**Definition 30**. Bargaining (Negotiation) set, $S$, resulting from a
2-player game in strategic form is the convex hull of all payoff pairs,
with the added constraint that
$$\forall (x,y) \in S, \quad x \geq t_{A}, \quad y \geq t_{B}$$ where
$t_{A}, t_{B}$ are the max-min payoff of player $A$ and $B$
respectively. Known as $A$ and $B$'s security level or **threat level**.

Call $(t_{A}, t_{B})$ the **threat point**


## Bargaining Axioms


**Definition 31** (Axioms for bargaining solution). For a bargaining set
$S$ with threat point $(t_{A}, t_{B})$, a **Nash bargaining solution**
$N(S) = (X,Y)$ is said to satisfy the following axioms:

(a) **Efficiency** - $(X,Y) \in S$

(b) **Pareto optimality** - $(X,Y)$ are Pareto optimal, i.e.
    $\forall (x,y) \in S$ if $x \geq X$ and $y \geq Y$, then
    $(x,y) = (X,Y)$

(c) **Invariant under payoff scaling**, meaning if $a,c > 0$ and
    $b,d \in \mathbb{R}$ and we define $S^\prime$ to be the bargaining
    set $$S^\prime  = \{ (ax + b, cy + d) \mid (x,y) \in S\}$$ with
    threat point $(at_{A} + b, ct_{B} + d)$, then
    $N(S^\prime) = (aX + b, cY + d)$

(d) **Symmetry** - If $t_A = t_B$ and $(x,y) \in S$ implies
    $(y,x) \in S$ then we must have $X = Y$

(e) **Independence of irrelevant alternatives** - If $S,T$ are
    bargaining sets with the same threat point and $S \subset T$, then
    either $N(S) = N(T)$ or $N(T) \notin S$


## The Nash Bargaining Solution


**Theorem 32**. *Under the axioms of bargaining solution, (a)-(e) above.
Every bargaining set $S$ that contains a point $(x,y)$ with
$x > t_A, y > t_B$, has a unique Nash bargaining solution
$N(S) = (X,Y)$*

*Obtained as the unique point $(x,y) \in S$ that maximises the **Nash
product** $$(x - t_{A})(y - t_{B})$$*


# Congestion Games

## Components of a Congestion Game


**Definition 33**. A **congestion network** has the following
components:

1.  A finite set of nodes

2.  A finite set of directed edges, each edge, e, an ordered pair
    written $AB$ from node $A$ to node $B$

3.  Each edge $e$ has an associated cost function $c_{e}(x)$ giving
    value when there are $x$ users on edge $e$, with $c_{e}(x)$ weakly
    increasing in $x$ $$x \leq y \implies c_{e}(x) \leq c_{e}(y)$$



**Definition 34**. To form a **congestion game**, we need the following
components:

1.  A congestion network

2.  $N$ users of network with each user having a origin node, $O_{i}$
    and a destination node $D_{i}$

3.  A strategy of user $i$ is a path $P_{i}$ from $O_{i} \to D_{i}$.
    Given strategy $P_{i}$ for each user $i$, the **flow** on edge $e$
    is the number of users using edge $e$
    $$f_{e} = \left\lVert \{i : e \in P_{i}\}\right\rVert$$

4.  The **cost** to user $i$ of using path $P_{i}$ is the sum of the
    costs of the edges in $P_{i}$
    $$\text{Cost}_{i}(P_{i}) = \sum_{e \in P_{i}} c_{e}(f_{e})$$



**Definition 35**. Say $P_{i}$ a **best response** for user $i$ if
against strategies $P_{j}$, $j \neq i$, then
$$\sum_{e \in P_{i}} c_{e}(f_{e}) \leq \sum_{e \in P_{i} \cap Q_{i}} c_{e}(f_{e}) + \sum_{e \in P_{i} / Q_{i}} c_{e}(f_{e} + 1)$$
holds for every possible alternative path $Q_{i}$ for user $i$



**Definition 36**. In a congestion game with $N$ users strategies
$P_1, P_2, \ldots , P_{N}$ of all $N$ users define an **equilibrium** if
each strategy is a best response to the other strategies. i.e if the
above inequality holds for all $i$


## Existence of Equilibrium in Congestion Games


**Theorem 37**. *Every congestion game has at least one equilibrium*


## Price of Anarchy


**Definition 38**. The **price of anarchy** of a congestion game is the
ratio of the cost of the worst equilibrium to the cost of the best
possible solution
$$\text{PoA} = \frac{\text{Worst average cost per user in any equilibrium}}{\text{Average cost per user in social optimum} } = \frac{\max_{P} \sum_{i} \text{Cost}_{i}(P_{i})}{\min_{P} \sum_{i} \text{Cost}_{i}(P_{i})}$$



**Proposition 39**. *For atomic flow congestion games, the price of
anarchy is at most $5/2$*



**Proposition 40**. *For split-able flow congestion games, the price of
anarchy is at most $4/3$*


# Combinatorial Games

These are 2-player, perfect information games with no chance moves. They
come in 2 types:

-   **Partizan games** - where the players have different sets of moves

-   **Impartial games** - where the players have the same set of moves

### The Ending Condition

A combinatorial game ends when there are no legal moves left for any
player. The game is then said to be in a **terminal position**. This is
a necessary condition for a game to be a combinatorial game.

### The Normal Play Convention

The normal play convention is that the player who cannot move loses the
game. This is a necessary condition for a game to be a combinatorial
game.

## Nim and Impartial Games


**Definition 41**. An **option** of a game position in a combinatorial
game is a position that can be reached in one move from the player to
move.


### Winning and Losing Positions

Impartial games, game positions belong to one of 2 classes:

-   **Winning positions** - the player to move has a winning move

-   **Losing positions** - the player to move has no winning move


**Proposition 42**. *In an impartial game, a game position is losing if
and only if all its options are winning positions. A game is winning if
and only if at least one of its options is a losing position; moving to
that position is a winning move.*



**Proposition 43**. *A Nim position is losing if and only if the Nim sum
equals zero for all columns in the binary representation of the
position; such a position is called a **zero position**. A Nim position
is winning if and only if the Nim sum is not zero.*


## Top-down induction

### Partial and Total Orders


**Definition 44**. A binary relation $\simeq$ on a set $S$ is a
**partial order** if, for all $x,y,z \in S$, we have:

-   **Reflexivity** - $x \simeq x$

-   **Antisymmetry** - $x \simeq y$ and $y \simeq x$ implies $x = y$

-   **Transitivity** - $x \simeq y$ and $y \simeq z$ implies
    $x \simeq z$

If in addition to the above, for all $x,y \in S$, we have:

-   **Comparability** - $x \simeq y$ or $y \simeq x$

then $\simeq$ is a **total order**



**Definition 45**. For a given partial order $\simeq$ on a set $S$, we
define the **strict order** $\sim$ corresponding to $\simeq$ by; for all
$x,y \in S$: $$x \sim y \iff x \simeq y \text{ and } x \neq y$$



**Definition 46**. An element $x \in S$ is **maximal** if there is no
$y \in S$ such that $x \sim y$


### Back to Top-Down Induction


**Definition 47**. Consider a set $S$ of games, defined by a starting
game and all the games that can be reached from it via any sequence of
moves of the players. For two games; $G,H \in S$, we call $H$
**simpler** than $G$, denoted with the binary relation $H \leq G$, if
there is a sequence of moves that leads from $G$ to $H$. We allow for
$G = H$ where this sequence is empty.



**Proposition 48**. *The binary relation $\leq$ ('simpler than') on a
set $S$ of games is a partial order*



**Proposition 49**. *Every non-empty subset, $T$, of $S$ has a minimal
element*



**Theorem 50** (Top-down induction). *Consider a set $S$ with a partial
order $\simeq$ such that every non-empty subset of $S$ has a minimal
element. Let $P(x)$ be a statement about an element $x \in S$ that may
be true or false. Assume that $P(x)$ holds whenever $P(y)$ holds for all
$y \in S$ such that $y \sim x$. Then $P(x)$ is true for all $x \in S$.
That is
$$(\forall x :\ ( \forall y \sim x : P(y)) \implies P(x)) \implies (\forall x : P(x))$$*


## Game Sums


**Definition 51**. Suppose that $G$ and $H$ are games with options
$G_1, \ldots , G_n$ and $H_1, \ldots , H_m$ respectively. Then the
**game sum** $G + H$ is the game with options
$G_1 + H, \ldots , G_n + H, G + H_1, \ldots , G + H_m$



**Proposition 52**. *Denoting the losing game with **no options** by
$0$, then for any games $G,H$ and $J$ we have*

-   ***Commutativity of +**: $$G + H = H + G$$*

-   ***Associativity of +**: $$(G + H) + J = G + (H + J)$$*

-   ***Identity of +**: $$G + 0 = G$$*


## Equivalence of Games


**Definition 53**. Two games $G$ and $H$ are called **equivalent**,
written $G \equiv H$, if and only if for any other game $J$, the game
sum $G+J$ is losing if and only if $H + J$ is losing



**Lemma 54**. *The binary relation of equivalence, $\equiv$, is an
equivalence relation between games, this means that it is:*

-   ***Reflexive** - $G \equiv G$*

-   ***Symmetric** - $G \equiv H$ implies $H \equiv G$*

-   ***Transitive** - $G \equiv H$ and $H \equiv J$ implies
    $G \equiv J$*



**Proposition 55**. *Two Nim piles are equivalent if and only if they
have the same size*



**Proposition 56**. *$G$ is a losing game if and only if $G \equiv 0$*



**Corollary 57**. *Any two losing games are equivalent*



**Lemma 58**. *For all games $G,H$ and $K$ we have:
$$G \equiv H \implies G + K \equiv H + K$$*



**Lemma 59**. *Let $J$ be a losing game. Then $G + J \equiv G$ for any
game $G$*



**Proposition 60** (The Copycat Principle). *$G + G \equiv 0$ for any
impartial game $G$*



**Lemma 61**. *For impartial games $G$ and $H$, then $G \equiv H$ if and
only if $G + H \equiv 0$*


## Notation for Nim Piles


**Definition 62**. If $G$ is a **single** Nim pile with $n \geq 0$
tokens in it, then we denote this game by $*n$. This game is specified
by its $n$ options, defined recursively as $$*0, *1, \ldots , *(n-1)$$



**Definition 63**. If $G \equiv *m$ for an impartial game $G$, then $m$
is called the **Nim value** of $G$


## The Mex Rule


**Definition 64**. For a finite set of natural numbers $S$, the
**minimum excluded number** of $S$, written $mex(S)$, is defined as
$$mex(S) = \min \{n \in \mathbb{N}\mid n \notin S\}$$ In other words,
$mex(S)$ is the smallest non-negative integer not contained in $S$ e.g.
$mex(\{0,1,3,4,6\}) = 2$



**Theorem 65** (The Mex Rule). *Any impartial game $G$ has **Nim value**
$m$, where $m$ is uniquely determined as follows; for each option $H$ of
$G$, let $H$ have Nim value $s_{H}$, and let
$S = \{s_{H}: H \text{ is an option of } G\}$. Then $m = mex(S)$, that
is, $G \equiv *(mex(S))$*


## Sums of Nim Piles


**Definition 66**. If $*k \equiv *m + *n$, then we call $k$ the **Nim
sum** of $m$ and $n$, and write $k = m \oplus n$



**Theorem 67**. *Let $n \in \mathbb{Z}^+$, and represent $n$ as a unique
sum of powers of $2$, i.e. write $n = 2^{a} + 2^{b} + 2^{c} + \ldots$,
where $a > b > c > \ldots \geq 0$. Then
$$*n \equiv *2^{a} \oplus *2^{b} \oplus *2^{c} \oplus \ldots$$*


$$
