---
layout: default
title: Statistical Modelling
parent: Year 2
nav_order: 5
math: mathjax3
---
# Statistical Modelling - Concise notes
{: .no_toc }
## MATH50011
{: .no_toc}


<head>
  <style>
ol.n {list-style-type: none;}
  </style>
</head>

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
  
- <a href="/notes/pdfs/year2/SM-Concise.pdf" target="_blank" style="color:#801fff;">**Open Stats Concise**</a> - <a href="/notes/pdfs/year2/SM-Concise.pdf" download>**Download**</a>
- <a href="/notes/pdfs/year2/SMLec.pdf" target="_blank" style="color:#801fff;">**Open Stats Lecturer**</a> - <a href="/notes/pdfs/year2/SMLec.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets - Class</span>
  </summary>
  
  - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS1.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 1**</a> - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS1-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS2.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 2**</a> - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS2-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS3.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 3**</a> - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS3-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS4.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 4**</a> - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS4-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS5.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 5**</a> - <a href="/notes/pdfs/year2/problemsheets/pfsSheets/given/SMPS5-Sol.pdf" target="_blank">**Solutions**</a>
  
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

**Colour Code** - <span style="color: green;">**Definition**</span> are
<span style="color: green;">**green**</span> in these notes,
<span style="color: red;">**Consequences**</span> are <span style="color: red;">**red**</span>
and <span style="color: RoyalBlue;">**Causes**</span> are <span style="color: blue-000;">**blue**</span>

*Content from MATH40005 assumed to be known.*

# Statistical Models

## Parametric Statistical Models

 
**Definition 1**. *[**Statistical Model**]*


Statistical model; collection of probability distribution
$\{P_{\theta}:\theta \in \Theta\}$ on a given sample space.\
Set $\Theta$ - ([**Parameter Space**]) - set
of all possible parametric values, $\Theta \subset \mathbb{R}^p$

 
**Definition 2**. *[**Identifiable**]*


Statistical model is [**identifiable**] if
map $\theta \mapsto P_\theta$, one-to-one,
$P_{\theta_1} = P_{\theta_2} \implies \theta_1 = \theta_2\quad \forall \theta_1,\theta_2 \in \Theta$

## Using Models

Requirements for a model

1.  Agree with observed data \"reasonable\" well

2.  reasonably simple (no excess parameters)

3.  easy to interpret (parameter have practical meaning)

# Point Estimation

 
**Definition 3**. *[**Statistic**]*


Statistic - function of observable random variable.

 
**Definition 4**.
*[**Estimate/Estimators**]*


$t$ a statistic\
$t(y_1,\dots,y_n)$ called [**estimate**] of
$\theta$\
$T(Y_1,\dots,Y_n)$ an [**estimator**] of
$\Theta$

## Properties of estimators

### Bias

 
**Definition 5**. *[**Bias**]*


$T$ estimator for $\theta \in \Theta \subset \mathbb{R}$
$$bias_{\theta}(T) = E_{\theta}(T)-\theta$$
[**unbiased**] if
$bias_{\theta}(T) = 0,\quad \forall \theta \in \Theta$\
If $\Theta \subset \mathbb{R}^k$ often interested in
$g(\theta),\ g:\theta \to \mathbb{R}$
$$\text{extend } bias_{\theta}(T) = E_{\theta}(T) - g(\theta)$$

### Standard error

 
**Definition 6**.


$T$ estimator for $\theta \in \Theta \subset \mathbb{R}$

$$SE_{\theta}(T) = \sqrt{Var_{\theta}(T)}$$

 Standard error, is standard
deviation of sampling distribution of $T$

### Mean Square Error

 
**Definition 7**.


$T$ estimator for $\theta \in \Theta \subset \mathbb{R}$\
Mean square error of $T$ $$\begin{aligned}
    MSE_{\theta}(T) &= E_{\theta}(T-\theta)^{2}\\
    &= Var_{\theta}(T) + [bias_{\theta}(T)]^2\end{aligned}$$

# The Cramér-Rao Lower Bound

 
**Theorem 1**. *(Cramér-Rao Lower Bound)*


$T = T(X)$ unbiased estimator for $\theta \in \Theta \subset \mathbb{R}$
for $X = (X_1,\dots,X_n)$ with just pdf $f_{\theta}(x)$ under mild
regularity conditions: $$Var_{\theta}(T) \geq \frac{1}{I(\theta}$$ For
$I_{\theta}$ the [**Fisher information of
sample**] $$\begin{aligned}
I(\theta) &= E_{\theta}\left[\left\{ \frac{\partial}{\partial \theta}\log f_{\theta}(x) \right\}^2\right]\\
&= -E_{\theta}\left[\frac{\partial^2}{\partial \theta^2} \log f_\theta (x) \right]\\
I_n(\theta) &= -nE_{\theta}\left[\frac{\partial^2}{\partial \theta^2} \log f_\theta (x) \right]\end{aligned}$$

**Proposition.**\
For a random sample: Fisher info proportional to sample size\
**Jensen's inequality**\
For $X$ a random variable with $\varphi$ a convex function

$$\varphi(E[X])\leq E\left[\varphi (X)\right]$$

Call
$E\left[\varphi (X)\right]-\varphi \left(E[X]\right)$ the [**Jensen
gap**]

# Asymptotic Properties

 
**Definition 8**.


Sequence of estimators $(T_{n})_{n\in\mathbb{N}}$ for $g(\theta)$ called
[**(weakly) consistent**] if
$\forall \theta \in \Theta$
$$T_n \xrightarrow[]{P_{\theta}} g(\theta) \quad (n\to \infty)$$

 
**Definition 9**.


Convergence in probability: $T_n \xrightarrow[]{P_{\theta}} g(\theta)$
$$\forall \epsilon > 0: \lim_{n\to\infty}P_{\theta}(|T_n - g(\theta)| < \epsilon) = 1$$

**Lemma - (Portmanteau Lemma)**\
$X,X_n$ real valued random value.\
Following are equivalent:

1.  $X_n \to X$ as $n \to \infty$

2.  $E[f(X_n)] \to E[f(X)] \quad n \to \infty$ for all bounded +
    continuous functions $f:\mathbb{R}\to \mathbb{R}$

 
**Definition 10**.


Sequence of estimators $(T_n)_{n\in\mathbb{N}}$ for $g(\theta)$
[**asymptotically unbiased**] if
$\forall \theta \in \Theta$

$$E_{\theta} \to g(\theta) \quad n \to \infty$$

**Lemma.**\
$(T_n)$ asymptotically unbiased for $g(\theta)$ and
$\forall \theta \in \Theta$

$$Var_{\theta}(T_n) \to 0 \quad n \to \infty$$

$\implies (T_n)$
consistent for $g(\theta)$

 
**Definition 11**.


Sequence $(T_n)$ of estimators for $\theta \in \mathbb{R}$
[**asymptotically normal**] if

$$\sqrt{n}(T_n - \theta) \xrightarrow[]{d} N(0,\sigma^{2}(\theta))$$

for some $\sigma^2)(\theta)$

 
**Theorem 2**. *(Central Limit Theorem)*


$Y_1,\dots,Y_n$ be iid random variable with
$E(Y_i) = \mu,\ Var(Y_i) = \sigma^2$\
$$\implies \text{sequence } \sqrt{n}(\bar{Y} - \mu) \xrightarrow[]{d} N(0,\sigma^2)$$

**Remark.**\
Under mild regularity conditions for asymptotically normal estimators
$T_n$ $$SE_{\theta}(T_n) \approx \frac{\sigma(T_n)}{\sqrt{n}}$$

**Lemma.** *(Slutsky)*\
$X_n,X,Y_n$ random variables\
If $X_n \xrightarrow[d]{} X$ and $Y_n \xrightarrow[p]{} c$ for constant
$c$

1.  $X_n + Y_n \xrightarrow[d]{} X + c$

2.  $Y_n X_n \xrightarrow[d]{} cX$

3.  $Y_{n}^{-1}X_{n} \xrightarrow[d]{} c^{-1}X\quad$ provided $c \neq 0$

 
**Theorem 3**. *(Delta Method)*


Suppose $T_n$ asymptotically normal estimator of $\theta$ with
$$\sqrt{n}(T_n - \theta) \xrightarrow[d]{} N(0,\sigma^{2}(\theta))$$
$g:\Theta \to \mathbb{R})$ differentiable function with
$g'(\theta) \neq 0$. Then
$$\sqrt{n}[g(T_n) - g(\theta)] \xrightarrow[d]{} N(0,g'(\theta)^2\sigma^{2}(\theta))$$

 
**Theorem 4**. *(Continuous Mapping Theorem)*


$k,m \in \mathbb{N}, X,X_n, \quad \mathbb{R}^k-$valued random variable.\
$g:\mathbb{R}^k \to \mathbb{R}^m$ continuous function at every point of
$C$ s.t $P(X \in C) = 1$

-   If $X_n \xrightarrow[d]{} X \implies g(X_n) \xrightarrow[d]{} g(x)$
    as $n\to\infty$

-   If $X_n \xrightarrow[p]{} X \implies g(X_n) \xrightarrow[p]{} g(X)$
    as $n\to\infty$

-   If
    $X_n \xrightarrow[a.s]{} X \implies g(X_n) \xrightarrow[a.s]{} g(X)$
    as $n\to\infty$

# Maximum Likelihood Estimation

 
**Definition 12**. *(Likelihood function)*


Suppose observer $Y$ with realisation $y$\
[**Likelihood function**]

$$L(\theta) = L(\theta:y) = \begin{cases}
  P(Y=y:\theta) & \text{ discrete data } \\
  f_{Y}(y:\theta) & \text{ absolutely continuous data}
\end{cases}$$ 

Likelihood function is the joint pdf/pmf or observed data
as a function of unknown parameter.\
Random sample $Y = (Y_1,\dots,Y_n)\quad Y_i$ iid.\
If $Y_i$ has pdf $f(\cdot;\theta)$
$$\implies L(\theta) = \prod_{i=1}^{n}f(y_i:\theta)$$

 
**Definition 13**. *(Maximum Likelihood Estimator)*


[**MLE**] of $\theta$ is estimator
$\hat{\theta}$ s.t
$$L(\hat{\theta}) = \sup_{\theta \in \Theta}L(\theta)$$

## Properties of Maximum Likelihood estimators

### MLEs functionally invariant

$g$ bijective function\
$\hat{\theta}$ MLE of $\theta \implies \hat{\phi} = g(\hat{\theta})$ a
MLE of $\phi = g(\theta)$

### Large Sample property

 
**Theorem 5**.


$X_1,X_2,\dots$ iid observations with pdf/pmf $f_{\theta}$\
$\theta \in \Theta,\ \Theta$ an open interval\
$\theta_0 \in \Theta$ - true parameter.\
Under regularity conditions ($\{x:f_{\theta}(x) > 0 \}$ indpendent of
$\theta$). We have

1.  $\exists$ consistent sequence $(\hat{\theta})_{n\in\mathbb{N}}$ of
    MLE

2.  $(\hat{\theta})_{n\in\mathbb{N}}$ consistent sequence of MLEs
    $\implies \sqrt{n}(\hat{\theta}_n - \theta_0) \xrightarrow[]{d} N(0,(I_f(\theta_0))^{-1})$
    *(Asymptotic normality of MLE)*\
    Where $I_f{\theta}$ Fisher information of sample size $=1$

**Remark:** if MLE unique $(\forall n) \implies$ sequence of MLEs
consistent\
**Remark**\
Limiting distribution depends on $I_f(\theta_0)$, which is often unknown
in practical situations. $\implies$ need to estimate $I_f(\theta_0)$\
iid sample; $I_f(\theta_0)$ estimated by

-   $I_f(\hat{\theta})$

-   $\frac{1}{n}\sum_{i=1}^{n}\left( \frac{\partial}{\partial \theta} \log(f(x_i:\theta))\rvert_{\theta = \hat{\theta}} \right)^2$

-   $-\frac{1}{n}\sum_{i=1}^{n} (\frac{\partial}{\partial \theta})^2 \log(f(x_i:\theta))\rvert_{\theta = \hat{\theta}}$

Often consistent $\implies$ converge to $I_f(\theta_0)$ in probability

**Remark**\
Standard error of asymptotically normal MLE $\hat{\theta}_{n}$\
Approximated by
$SE(\hat{\theta}_n) = \sqrt{\hat{I}^{-1}_{n}}/\sqrt{n}\ \hat{I}_n$
estimator from above.\
**Remark -** Multivariate version.

$\Theta \subset \mathbb{R}^k$ open set, $\hat{\mathbf{\theta}}_n$ MLE
based on $n$ observation.
$$\sqrt{n}(\hat{\mathbf{\theta}}_n - \mathbf{\theta}_0) \xrightarrow[]{d} N(0,(I_f(\mathbf{\theta_0})^{-1})$$
$\mathbf{\theta_0}$ the true parameter, $I_f(\mathbf{\theta})$ [**Fisher
information matrix**] $$\begin{aligned}
I_{f}(\mathbf{\theta}) &:= E_{\theta}\left[ (\nabla \log f(X; \mathbf{\theta}))^T(\nabla \log f(X;\theta)) \right]\\
&:= -E_{\theta}\left[ \nabla^T \nabla \log f(X:\theta) \right]\end{aligned}$$

 
**Definition 14**.


[**Converges in distribution**] for random
vector\
$\mathbf{X,X_1,X_2}$ random vectors of dimension $k$

$$\mathbf{X}_n \xrightarrow[]{d} \mathbf{X} \quad (n\to\infty)$$

If
$P(\mathbf{X}_n \leq z) \xrightarrow[n\to\infty]{} P(\mathbf{X} \leq z) \quad \forall z \in \mathbb{R}^k: z \mapsto P(X\leq Z) \text{ continuous}$

# Confidence Regions

 
**Definition 15**. *(Confidence interval)*


$1-\alpha$ [**confidence interval**] for
$\theta$, a random interval $I$ containing 'true' paramter with
probability $\geq 1 - \alpha$
$$P_{\theta \in I} \geq 1-\alpha \quad \forall \theta \in \Theta$$

## Construction of confidence intervals

 
**Definition 16**.


[**Pivotal Quantity**] for $\theta$ a
function $t(Y,\theta)$ of data and $\theta$\
s.t distribution of $t(Y,\theta)$ known (no dependency on unknown
parameters)\
Know distribution of $t(Y,\theta) \implies$ can find constant $a_1,a_2$
s.t $P(a_1 \leq t(Y_1,\theta) \leq a_2) \geq 1 - \alpha$\
$\implies P(h_1(Y) \leq \theta \leq h_2(Y)) \geq 1 - \alpha$\
Call $[h_1(Y),h_2(Y)]$ a [**random
interval**]\
with observed interval $[h_1(y),h_2(y)]$ a [**$1-\alpha$ confidence
interval for $\theta$**]

## Asymptotic confidence intervals

We often know

$$\sqrt{n}(T_n - \theta) \xrightarrow[]{d} N(0,\sigma^2(\theta))$$

$$\implies \underbrace{\sqrt{n}(\frac{T_n - \theta}{\sigma(\theta)})}_{\text{use as pivotal quantity}} \xrightarrow[]{d} N(0,1)$$

 
**Definition 17**.


Sequence of random intervals $I_n$\
an [**asymptotic $1-\alpha$ Confidence
Interval**] if

$$\lim_{n\to\infty} P_{\theta} (\theta \in I_n) \geq 1 - \alpha \quad \theta$$

*Simplification*\
Given consistent estimator $\hat{\sigma}_n$ for
$\sigma(\theta)\ \hat{\sigma}_n \xrightarrow[]{P_\theta} \sigma(\theta) \ \forall \theta$

$$\sqrt{n}(\frac{T_n - \theta}{\sigma(\theta)}) \xrightarrow[]{d} N(0,1)$$

$$T_n \pm c_{\alpha/2}\times\underbrace{\frac{\hat{\sigma}_n}{\sqrt{n}}}_{\text{estimates } SE(T_n)}$$

$$T_n \pm c_{\alpha/2}SE(T_n)$$

**Simplification**.\
$\hat{\sigma}^2 = \frac{Y}{n}(1-\frac{Y}{n}) \quad \hat{\sigma}^2 \xrightarrow[]{P} \theta(1-\theta)$

$$\underbrace{\sqrt{n}\frac{Y/n - \theta}{\sqrt{\frac{Y}{n}(1-\frac{Y}{n})}}}_{\text{pivotal quantity}} \implies \frac{y}{n} \pm \frac{c_{\alpha/2}}{\sqrt{n}}\sqrt{\frac{y}{n}(1-\frac{y}{n}}$$

## Simultaneous Confidence Interval/Confidence regions.

 
**Definition 18**.


$\mathbf{\theta} = (\theta_1,\dots,\theta_k)^T \in \Theta \in \mathbb{R}^k$\
With random intervals $(L_i(\mathbf{Y}),U_i(\mathbf{Y}))$ s.t
$$\forall \mathbf{\theta}: P_{\theta}(L_i(\mathbf{Y} < \theta_i < U_i(\mathbf{Y}), i \in \{1,\dots,k\}) \geq 1 - \alpha$$
$(L_i(\mathbf{y},U_i(\mathbf{y})) \ i \in \{1,\dots,k\}$ a [
**$1-\alpha$ simultaneous confidence
interval**] for $\theta_1,\dots,\theta_k$

**Remark -** (Bonferroni correction)

take $[L_i,U_i]$ a $1-\alpha$ confidence interval for
$\theta_i,\ i \in \{1,\dots,k\}$

# Hypothesis Testing

## Prelim

 
**Definition 19**. *(Hypotheses)*


We have $2$ complementary hypothesis

-   $H_{0}:$ Null hypothesis - consider to be the status quo

-   $H_1$: Alternative hypothesis

 
**Definition 20**. *(Hypthesis Test)*


Hypothesis test a rule that specifies for which valus of a sample
$x_1,\dots,x_n$ a decision is to be made

-   accept $H_0$ as true

-   reject $H_0$ and accept $H_1$

[**Rejection region/Critical region**] -
subset of sample space for which $H_0$ rejected

 
**Definition 21**. *(Types of error)*


                       $H_0$ True                                       $H_0$ False
  -------------------- ------------------------------------------------ -------------------------------------------------
  Don't reject $H_0$   $\checkmark$                                     [**Type II Error**]
  Reject $H_0$         [**Type I Error**]   $\checkmark$

## Power of a Test

 
**Definition 22**. *(Power function)*


$\Theta$ parameter space with
$\Theta_0 \subset \Theta,\ \Theta_1 = \Theta \backslash \Theta_0$\
Consider: $$\begin{aligned}
    H_0: & \theta \in \Theta_0\\
    H_1: & \theta \in \Theta_1\end{aligned}$$ Given a test for this
hypothsis, we have a [**Power function**]
$$\begin{aligned}
    \beta: &\theta \to [0,1]\\
    \beta(\theta) &= P_{\theta}(\text{reject} H_0)\end{aligned}$$
$\theta \in \Theta_0 \implies$ want $\beta(\theta)$ small\
$\theta \in \Theta_1 \implies$ want $\beta(\theta)$ large

## p-Value

 
**Definition 23**. *(p-value)*


$$p = \sup_{\theta \in \Theta_0}P_{\theta}(\text{observing something 'at least as extreme' as the observation})$$
reject $H_0 \iff p \leq \alpha$\
For test based on statistic $T$ with rejection for large value of $T$ we
have $$p = \sup_{\theta \in \Theta_0}P_{\theta}(T\geq t)$$ for $t$ our
observed value

## Connection between tests & confidence intervals

### Constructing a test from confidence region

$Y$ a random observation.\
$A(Y)$ a $1-\alpha$ confidence region for $\theta$
$$P(\theta \in A(Y)) \geq 1 - \alpha \quad \forall \theta \in \Theta$$
Define test for $\begin{aligned}
H_0:& \theta \in \Theta_0\\
H_1:& \theta \not\in \Theta_0
\end{aligned}$ for $\Theta_0 \subset \Theta$ a fixed subset with level
$\alpha$ s.t
$$\text{Reject } H_0 \text{ if } \Theta_0 \cap A(Y) = \emptyset$$
$$\begin{aligned}
P_{\theta}(\text{Type I error}) = P_{\theta}(\text{reject}) &= P_{\theta}(\Theta_0 \cap A(Y) = \emptyset)\\
&\leq P_{\theta}(\theta \not\in A(Y)) \leq \alpha\end{aligned}$$

### Constructing confidence region from tests

Suppose $\forall \theta_0 \in \Theta$ we have a level $\alpha$ test
$\phi_{\theta_0}$ for
$$H^{\theta_0}_0: \theta = \theta_0 \quad \text{vs.} \quad H^{\theta_0}_1: \theta \neq \theta_0$$
A decision rule $\phi_{\theta_0}$ to reject/not reject $H^{\theta_0}_0$
satisfying:
$$P_{\theta_0}(\phi_{\theta_0} \text{ reject } H^{\theta_0}_0) \leq \alpha$$
Consider random set:
$$A:= \left\{ \theta_0 \in \Theta: \phi_{\theta_0} \text{ doesn't reject } H^{\theta_0}_0 \right\}$$
We see $A$ a $1-\alpha$ confidence region for $\theta$\
$\forall \theta \in \Theta\ P_{\theta}(\theta \in A) = P_{\theta}(\phi_\theta \text{ not rejects }) = 1 - P_{\theta}(\phi_\theta \text{ rejects }) \geq 1 - \alpha$

# Likelihood Ratio Tests

*(Numbers don't line up with official notes!!!)*\

 
**Definition 24**. *(Likelihood ratio statistic)*


$$t(\mathbf{y}) = \frac{sup_{\theta \in \Theta}L(\theta;\mathbf{y})}{sup_{\theta \in \Theta_0}L(\theta;\mathbf{y})} = \frac{\text{max likelihood under } H_0 + H_1}{\text{max likelihood under } H_0}$$

 
**Theorem 6**.


$X_1,\dots,X_n \sim N(0,1),\ X_i$ independent
$$\sum_{i=1}^{n}X^{2}_i \sim \chi^{2}_{n}$$

 
**Theorem 7**.


Under regularity conditions
$$2\log t(\mathbf{Y}) \xrightarrow[]{D} \chi^2_{r} \quad (n\to \infty)$$
under $H_0$ where $r$ the number of independent restrictions on
$\mathbf{\theta}$ needed to define $H_0$
