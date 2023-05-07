---
layout: default
title: Stats Learning
parent: Year 3
nav_order: 3
math: mathjax3
---

# Intro to Statistical Learning - Concise Notes
{: .no_toc }
## MATH60132
{: .no_toc}

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
  
- <a href="/notes/pdfs/year3/LecNotes/SL-Concise.pdf" target="_blank" style="color:#801fff;">**Open Stats Learning Concise**</a> - <a href="/notes/pdfs/year3/LecNotes/SL-Concise.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets</span>
  </summary>
  
  - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS1.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 1**</a> - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS1-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS2.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 2**</a> - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS2-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS3.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 3**</a> - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS3-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS4.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 4**</a> - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS4-Sol.pdf" target="_blank">**Solutions**</a>

  - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS5.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 5**</a> - <a href="/notes/pdfs/year3/probSheets/sl/SL-PS5-Sol.pdf" target="_blank">**Solutions**</a>

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

# Linear Methods for Regression

## Linear Regression Models and Least Squares


**Definition 1**. *The **linear regression model** is given by

$$f(X) = \beta_0 + \sum_{j=1}^{p} X_{j}\beta_{j}$$ 

where $X^T = (X_1, \dots, X_p)$ is the input vector,
$\beta^T = (\beta_0, \dots, \beta_p)$ is the unknown parameter vector,
and $f(X)$ is the output.\
*


Linear model assumes that regression function $E(Y\mid X)$ is linear, or
it is a reasonable approximation.


**Definition 2**. **Multivariate Linear Model* Given $p$ explanatory
variables, $X = (X_1, \ldots ,X_{p} )$, we have the multivariate linear
model
$$Y_{i} = \beta_0 + \beta_1 X_{i,1} + \ldots + \beta_{p} X_{i,p} + \epsilon_{i} = \beta_0 + \sum_{j=1}^{p} X_{ij}\beta_{j} + \epsilon_{i}$$
Given $\beta  = \begin{pmatrix} \beta_1, \ldots ,\beta_p \end{pmatrix}$
and $X = (X_{i,j} )$ the $n \times p$ matrix of $X_{i,j}$ values of $X$
on $i$th individual and $j$th variable. $$Y = X \beta + \epsilon$$
$\epsilon$ the $n \times 1$ vector of errors, with mean 0 and variance
$\sigma^2$.*



**Definition 3**. **(Residuals)* $$e = Y - X \beta$$ *(Residual Sum of
Squares)*
$$RSS(\beta) = e^T e = (Y - X \beta )^T (Y - X \beta ) = Y^T Y - 2 \beta^T X^T Y + \beta^T X^T X \beta$$
*(Least Squares Estimator)*
$$\hat{\beta} = \underset{\beta }{\mathop{\arg \min}}\ RSS(\beta) = \underbrace{(X^T X)^{-1} X^T Y}_{H \text{ - Hat matrix}}$$
We have the fitted values of the model as
$$\hat{Y} = X \hat{\beta} = H Y$$



**Proposition 4**. **(Expectation and Variance of $\beta$ )*
$$E(\hat{\beta}) = \beta$$
$$\text{Var}(\hat{\beta}) = \sigma^2 (X^T X)^{-1}$$
$\text{Var} \hat{\beta}$ a $p\times p$ covariance matrix. If $X$ an
orthogonal matrix then $X^T X = I_{p}$ so $\text{Var} \hat{\beta}$ a
diagonal matrix so for $i \neq j, \hat{\beta}_{i} , \hat{\beta}_{j}$ are
uncorrelated*



**Proposition 5**. **(Distribution of $\hat{\beta}$ )* If $\{e_{i}\}$
are normally distributed, then $\hat{\beta}$ is also normal

$$\hat{\beta} \sim N_{p}(\beta, \sigma^2 (X^T X)^{-1})$$

And if $X$ orthogonal then $\hat{\beta}_{i}$ and $\hat{\beta}_{j}$ are independent
for $i \neq  j$*



**Definition 6**. **(Z-score)*

$$z_{j} = \frac{\hat{\beta}_{j}}{\hat{\sigma} \sqrt{v_{j}} }$$

where $v_{j}$ the $j$th diagonal element of $(X^T X)^{-1}$ and so $\text{var } \hat{\beta}_{j} = \sigma^{2} v_{j}$

$$\hat{\sigma}^{2} = \frac{1}{n-p} \sum_{i=1}^{n} (Y_{i} - \hat{Y}_{i})^{2} \quad E(\hat{\sigma}^{2}) = \sigma^{2}$$

Used to test the hypothesis that $\beta_{j} = 0$, we have that $z_{j}$
distributed as a Student's $t$ distribution with $n-p$ degrees of
freedom, approximated as $N(0,1)$ for large $n$ larger than $p$*



**Definition 7**. **(F-test)*
$$F = \frac{(RSS_{0} - RSS_{1}) / (p_1 - p_0)}{RSS_{1} / (N - p_1 - 1)}$$
where $RSS_{0}$ the residual sum of squares for the smaller model with
$p_0 + 1$ parameters, $RSS_{1}$ the residual sum of squares for the
larger model with $p_1 + 1$ parameters, and $N$ the number of
observations. $$F \sim F_{p_1 - p_0,n-p-1 - 1}$$ The F statistic
measures the change in residual sum-of-squares per additional parameter
in the bigger model, and it is normalized by an estimate of
$\sigma^{2}$*


### The Gauss-Markov Theorem


**Theorem 8**. **(Gauss-Markov Theorem)* If the errors $\epsilon_{i}$
have mean 0, variance $\sigma^{2}$, and are uncorrelated, then the least
squares estimator $\hat{\beta}$ is the best linear unbiased estimator of
$\beta$ (BLUE)*


## Subset Selection

Unsatisfied with the least squares estimates due to

-   *prediction accuracy* - the least squares estimates often have low
    bias but large variance.

-   *interpretation* - With a large number of predictors, we often would
    like to determine a smaller subset that exhibit the strongest
    effects. In order to get the "big picture," we are willing to
    sacrifice some of the small details

## Shrinkage Methods

### Ridge Regression


**Definition 9**. **(Ridge Regression)* $$\begin{aligned}
        \hat{\beta}_{R} &= \underset{\beta }{\mathop{\arg \min}} \left \{\sum_{i=1}^{n} 
        \left( Y_{i}- \beta_0 - \sum_{j=1}^{p} X_{i,j}\beta_{j}  \right)^{2} + \lambda \sum_{j=1}^{p} \beta_{j}^{2}
        \right\}\\
        &= \underset{\beta }{\mathop{\arg \min}} \sum_{i=1}^{n} 
        \left( Y_{i}- \beta_0 - \sum_{j=1}^{p} X_{i,j}\beta_{j}  \right)^{2}
        \quad \text{subject to } \sum_{j=1}^{p} \beta_{j}^{2} \leq t 
    \end{aligned}$$ $\lambda$ a tuning parameter that controls the
amount of shrinkage\
When variables in least squares are highly correlated it can cause
instability in the least squares estimators - ridge regression can help
with this.*



**Proposition 10**. **(Ridge Regression RSS in matrix form)*

$$RSS(\beta) = (Y - X \beta )^T (Y - X \beta ) + \lambda \beta^T \beta$$

Differentiating, setting to 0 and solving this for $\beta$ gives

$$\hat{\beta}_{R} = (X^T X + \lambda I_{p})^{-1} X^T Y$$



**Definition 11**. **(Condition number)*

$$\kappa(A) = \frac{\lambda_{\max}}{\lambda_{\min}}$$

where $\lambda_{\max}$ and $\lambda_{\min}$ are the largest and smallest
eigenvalues of $A$\
$\kappa(A)$ is a measure of how much the solution of a linear system of
equations changes when the coefficients of the equations are slightly
changed.*



**Proposition 12**. **(Bayesian interpretation of ridge regression)**

*If prior $\beta_{j} \sim N(0,\tau^{2} )$ independently for
$j = 1, \dots, p$, and
$Y_{i} \sim N(\beta_0 + x_{i}^T \beta ,\sigma^{2} )$ Then
$\beta \mid Y \sim N$ with posterior mean $\hat{\beta}_{R}$ with
$\lambda = \sigma^{2} / \tau^{2}$*


#### Singular Value Decomposition


**Definition 13**. **(Singular Value Decomposition)* The SVD of a
$n\times p$ (centred) matrix $X$ is $$X = U D V^T$$ where $U, V$ are
$n\times p, p\times p$ orthogonal matrices - columns of $U$ spanning the
column space of $X$ and $V$ spanning the row space\
$D$ is an $p \times p$ diagonal matrix with non-negative entries -
called the singular values of $X$\
If one or more of $d_{j}=0$ then $X$ is singular.*

*$$\begin{aligned}
        \text{if } X &= UDV^T\\
        X^T X &= V D^2 V^T\\
        (X^T X)^{-1} &= (V^T)^{-1} D^{-2} V^{-1}
    \end{aligned}$$

*Can write the least squares fitted vector as

$$X \hat{\beta}_{ls}   = UU^T Y$$

And for ridge regression

$$\begin{aligned}
        X \hat{\beta}_{R}  &= (UDV^T)(VD^2 V^T + \lambda I_p)^{-1}(VD^T U^T Y)\\
        &= UD(D^{2} + \lambda I_p)^{-1} DU^T Y\\
        &= \sum_{j=1}^{p} \mathbf{u}_{j} \frac{d_{j}^{2}}{d_{j}^{2} + \lambda} \mathbf{u}_{j}^T Y \quad \mathbf{u}_{j} \text{ cols of } U
    \end{aligned}$$

*Like linear regression, ridge regression computes the coordinates of
$y$ with respect to the orthonormal basis $U$ . It then shrinks these
coordinates by the factors $\frac{d^{2}_{j}}{d^{2}_{j}+\lambda }$ This
means that a greater amount of shrinkage is applied to the coordinates
of basis vectors with smaller $d^{2}_{j}$\
Ridge regression shrinks coordinates in directions with smaller
variance.*



**Definition 14**. **(Effective) Degrees of freedom*\
$$H_\lambda = X(X^T X + \lambda I_p)^{-1} X^T$$

*is the \"effective\" hat matrix for ridge regression.*

*$$\begin{aligned}
        df(\lambda ) &= \operatorname{tr} (H_\lambda )\\
        &= \sum_{j=1}^{p} \frac{d_{j}^{2}}{d_{j}^{2} + \lambda}
    \end{aligned}$$

*$$df(0) = p$$

*which is the actual degrees of freedom of the least squares fit.*



**Proposition 15**. **(Bias and variance of ridge regression)*\
We have that
$$E(\hat{\beta }_{R} ) = (X^T X + \lambda I_p)^{-1} X^T X \beta$$


### The Lasso


**Definition 16**. **(The Lasso)* $$\begin{aligned}
        \hat{\beta}_{L} &= \underset{\beta }{\mathop{\arg \min}} \left \{\frac{1}{2} \sum_{i=1}^{n} 
        \left( Y_{i}- \beta_0 - \sum_{j=1}^{p} X_{i,j}\beta_{j}  \right)^{2} + \lambda \sum_{j=1}^{p} |\beta_{j}|
        \right\}\\
        &= \underset{\beta }{\mathop{\arg \min}} \sum_{i=1}^{n} 
        \left( Y_{i}- \beta_0 - \sum_{j=1}^{p} X_{i,j}\beta_{j}  \right)^{2}
        \quad \text{subject to } \sum_{j=1}^{p} |\beta_{j}| \leq t 
    \end{aligned}$$

*$\lambda$ a tuning parameter that balances between fidelity of the fit
and size of the coefficients*

*Note*

*$$\hat{\beta}_L (0) = \hat{\beta} \quad \hat{\beta}_L (\lambda ) \to \overline{Y} \text{ as } \lambda \to \infty \quad \beta_{j}\to 0 \text{ for } j \neq  0$$


### Discussion: Subset Selection, Ridge Regression and the Lasso

**Lasso v. Ridge**

$$\text{Different penalties} \sum \beta_{j}^{2} \text{ v. } \sum |\beta_{j}|$$
If $\beta_{j}$ small then $\beta_{j}^{2}$ tiny, but
$\left\vert \beta_{j} \right\vert$ can be considerable larger so is
penalised more.

Lasso has the ability to select variables and shrink coefficients.

#### $X$ orthogonal {#x-orthogonal .unnumbered}

$$\begin{aligned}
    \hat{\beta}_{ls} &= (X^{T} X)^{-1} X^{T} Y = X^T Y\\
    \hat{\beta}_R &= \hat{\beta}_{ls} / (1 + \lambda )\\
    \hat{\beta}_L &= (\hat{\beta}_{ls} - \lambda)\\
    &= (\hat{\beta}_{ls} - \lambda)^+ \\
    &= \text{sign}(\hat{\beta}_{ls} ) (\left\vert \hat{\beta}_{ls} \right\vert - \lambda)^+\end{aligned}$$

## Methods using Derived Input Directions

### Principal Components Regression


**Definition 17**. **(Principal Components Regression)*\
*

1.  *Compute the first $M$ principal components $Z_{1}, \dots, Z_{M}$ of
    $X$ $$z_{m} = X v_{m} \quad m = 1, \dots, p$$ Where $V$ from the
    SVD - the eigenvectors of the sample covariance matrix*

2.  *Regress $Y$ onto $Z_{1}, \dots, Z_{M}$ by least squares*

*PCR can be written as sum of univariate regressions

$$\begin{aligned}
        \hat{y}^{pcr}_{M} &= \overline{Y} \textbf{1}_{n} + \sum_{m=1}^{M} \hat{\theta}_{m}z_{m}\\
        &= \overline{Y} \textbf{1}_{n} + X \sum_{m=1}^{M} \hat{\theta}_{m}v_{m}
    \end{aligned}$$
    
where
$\hat{\theta}_{m} = \frac{\left< z_{m},y \right> }{\left< z_{m},z_{m} \right> }$\
Can think of

$$\hat{\beta}^{pcr} = \sum_{m=1}^{M} \hat{\theta}_{m}v_{m}$$

Usually operate pcr on scaled inputs\
If $M = p$ then back to least squares (same col. space, just a
rotation)\
Works by discarding the $p-M$ smallest components*


# Cluster Analysis

## Scaling


**Definition 18**. **(Scaling Matrices)*\
Define the following $$\begin{aligned}
        e_{m,l}^{2}  &= \sum_{v=1}^{p} (X_{m,v} - X_{l,v}  )^{2}\\
        E &= (e_{m,l} ) \quad \text{ a } n\times n \text{ matrix}\\
        e_{m,l} & = X^T_{(m)} X_{(m)} + X^T_{(l)} X_{(l)} - 2 X^T_{(m)} X_{(l)}\\
    \end{aligned}$$ We form the *inner product matrix**

*$$\begin{aligned}
        B_{X} &= XX^T\\
        e_{m,l} &= b_{m,m} + b_{l,l} - 2b_{m,l} \quad m,l = 1, \dots, n
    \end{aligned}$$



**Proposition 19**. **(Loss of information) - Rotation*\
For $Y = XP$, $P$ an orthogonal $p\times p$ matrix - a rotation matrix

$$B_{Y} = YY^T = XP(XP)^T = XX^T = B_{X}$$

Going from $X \to B$ we lose orientation information.*



**Proposition 20**. **(Loss of information) - Position*\
Suppose $W_{(m)} = X_{(m)} - \mu$ for $\mu$ a arbitrary $p$-vector
$$W^T_{(m)}W_{(l)} = X^T_{(m)}X_{(l)} - X^T_{(m)}\mu  - \mu^T X_{(l)} + \mu^T \mu$$
Forming distances using $W$*

*$$\begin{aligned}
        e_{m,l}^{(W)} &= W^T_{(m)}W_{(m)} + W^T_{(l)}W_{(l)} - 2W^T_{(m)}W_{(l)}\\
        &= e_{m,l}
    \end{aligned}$$

*So going from $B$ to $E$ we lose position information.*



**Theorem 21**. **(Recovering $B$ from $E$ )*\
$$B = -\frac{1}{2}(I_{n} - \textbf{1} \textbf{1}^T / n) E (I_{n} - \textbf{1}  \textbf{1}^T /n)$$
We have that $\textbf{1}_{n}$ an eigenvector of $B$ with eigenvalue $0$*



**Theorem 22**. **(Recovering $X$ from $B$ )*\
$B$ a $n\times n$ matrix, $B = XX^T$, so $B$ is positive semi-definite
and symmetric - so we can form the following eigen-decomposition

$$B = \sum_{i=1}^{n} \lambda_{i} e^{(i)} e^{(i)T}$$

For $\lambda_1 \geq \lambda_2 \geq  \ldots \geq \lambda_{n^\prime }$ and
$\lambda_{n^\prime +1}, \ldots , \lambda_{n} = 0$ and $\{e^{(i)}\}$ are
the eigenvectors of $B$.\
Define the following $n$-vectors $f$

$$f^{(i)} = \sqrt{\lambda_{i}} e^{(i)} \quad i = 1, \dots, n^\prime$$

Then we have that 

$$Y_{n\times n^\prime } = 
        \begin{pmatrix}
            \vdots & \vdots & \ldots   &  \vdots \\
            f^{(1)} & f^{(2)} & \ldots   &  f^{(n^\prime )} \\
            \vdots & \vdots & \ldots   &  \vdots \\
        \end{pmatrix}$$
        
Where $YY^T = XX^T = B$*


## Proximity Matrices

### Proximity Matrices


**Definition 23**. *(Distance Matrix)\

$$\mathbf{D} = (d_{ij}) = d(x_{i}, x_{j})$$

A $N \times N$ matrix $\mathbf{D}$ where $N$ is the number of observations.\
Assume $d_{ij} \geq 0$ and $d_{ii} = 0$.\
Assume $\mathbf{D}$ also symmetric, if not consider
$(\mathbf{D}  + \mathbf{D}^T ) /2$ instead for analysis.*


### Dissimilarites Based on Attributes


**Definition 24**. *(*Dissimilarity* )\
For measurements $x_{ij}$ for $i = 1,2 \ldots ,N$ on variables
$j = 1,2, \ldots ,p$ (attributes) - define the dissimilarity

$$D(x_i, x_{i^\prime}) = \sum_{j=1}^{p} d_{j}(x_{ij} , x_{i^\prime j} )$$

where $d_{j}$ is the dissimilarity on the $j$th attribute.\
Often taken as

$$d_{j}(x_{ij} x_{i^\prime j} ) = (x_{ij} - x_{i^\prime j} )^{2}$$


### Object Dissimilarity


**Definition 25**. *(*Object Dissimilarity*)\

$$D(x_i, x_{i^\prime } ) = \sum_{j=1}^{p} w_{j} \cdot d_{j}(x_{ij} , x_{i^\prime j} ); \quad \sum_{j=1}^{p} w_{j} = 1$$

where $d_{j}$ is the dissimilarity on the $j$th attribute.\
$w_{j}$ is the weight assigned to the $j$th variable.

$$\overline{D} = \frac{1}{N^{2}} \sum_{i=1}^{N} \sum_{i^\prime =1}^{N} D(x_i, x_{i^\prime } ) = \sum_{j=1}^{p} w_{j} \cdot \overline{d}_{j} \qquad
        \overline{d}_{j} = \frac{1}{N^{2}} \sum_{i=1}^{N} \sum_{i^\prime =1}^{N} d_{j}(x_{ij} , x_{i^\prime j} )$$

Setting $w_{j} \sim \overline{d}_{j}$ would give all attributes equal
influence.\
In the Euclidean Case $$\begin{aligned}
        D_{I}(x_i, x_{i^\prime } ) &= \sum_{j=1}^{p} w_{j} \cdot (x_{ij} = x_{i^\prime j} )^{2}\\
        \overline{d}_{j} &= \frac{1}{N^{2} } \sum_{i=1}^{N} \sum_{i^\prime =1}^{N} (x_{ij} - x_{i^\prime j} )^{2} = 2 \cdot var_{j} = \text{ sample estimate of } Var(X_{j}) 
    \end{aligned}$$


### K-means

A popular iterative descent clustering method - used where all variables
quantitative and Euclidean distance used.


**Definition 26**. **(Within-point scatter)* $$\begin{aligned}
        W(C) &= \frac{1}{2} \sum_{k=1}^{K} \sum_{C(i)=k} \sum_{C(i^\prime )=k} \left\vert \left\vert x_{i} - x_{i^\prime } \right\vert  \right\vert^{2}    \\
        &= \sum_{k=1}^{K} N_{k} \sum_{C(i)=k} \left\vert \left\vert x_{i}-\overline{x}_{k} \right\vert  \right\vert^{2}   
    \end{aligned}$$ Where
$\overline{x}_{k} = \begin{pmatrix} \overline{x}_1k, \ldots ,\overline{x}_nk \end{pmatrix}$
the mean vector of cluster $k$, $N_{k} = \sum_{i=1}^{N} I(C(i) = k)$*



**Algorithm 1**. **(K-means Clustering)**

-   *For a given cluster assignment $C$ , the total cluster
    variance (33) is minimized with respect to $\{m_1, \ldots ,m_{K} \}$
    yielding the means of the currently assigned clusters (32)
    $$\underset{C, \{m_{k}\}_{1}^{K} }{\mathop{\min}} \sum_{k=1}^{K} N_{k} \sum_{C(i)=k} \left\vert \left\vert x_{i}-m_{k} \right\vert  \right\vert^{2}$$
    $$\overline{x}_{S}= \underset{m}{\mathop{\arg\ \min}} \sum_{i \in S} \left\vert \left\vert x_{i} - m \right\vert  \right\vert^{2}$$

-   *Given a current set of means $\{m_1, \ldots , m_{K} \}$,(33) is
    minimized by assigning each observation to the closest cluster mean.
    That is,
    $$C(i) = \underset{1 \leq k \leq K}{\mathop{\arg\ \min}} \left\vert \left\vert x_{i}- m_{k} \right\vert  \right\vert^{2}$$

-   *Iterate 1 and 2 until the assignments stop changing.*


## Multidimensional Scaling


**Definition 27**. *Given configuration and set of dissimilarities
$\{\delta_{m,l} \}$ we can form the distances $\{d_{m,l} \}$ and least
squares monotone regression fit $\{\hat{d}_{m,l}\}$ to the $d$ using the
$\delta$s\
Let the residual sum of squares be $$S^{\ast}  = \sum_{m < l} 
    \left( d_{m,l} - \hat{d}_{m,l}   \right)^{2}$$ And

$$T^{\ast}  = \sum_{m < l} d^{2}_{m,l}$$

Then the *stress* of the configuration is

$$S = \sqrt{\frac{S^{\ast} }{T^{\ast} }}$$



**Theorem 28**. **(Differentiation of Stress)*\
The stress function $S$ is differentiable and the partial derivatives
are $$\begin{aligned}
        \frac{\partial S}{\partial x_{i,k} } &= \frac{1}{2S} 
        \left\{ 
            \frac{T^{\ast} \frac{\partial S^{\ast} }{\partial x_{i, k} } - S^{\ast} \frac{\partial T^{\ast} }{\partial x_{i,k} }}{(T^{\ast} )^{2} }
        \right\}\\
        &= \frac{S}{2} 
        \left\{ 
            \frac{1}{S^{\ast} } \frac{\partial S^{\ast} }{\partial x_{i,k} } - \frac{1}{T^{\ast} } \frac{\partial T^{\ast} }{\partial x_{i,k} }
        \right\}\\
        &= \frac{S}{2}
        \left[ 
            \frac{1}{S^{\ast} }
            \left\{ 
                \sum_{m < l} 2 (d_{m,l} - \hat{d}_{m,l}  ) \frac{\partial d_{m,l} }{\partial x_{i,k} }
            \right\}
            - \frac{2}{T^{\ast} }
            \left\{ 
                \sum_{m < l} (x_{m,k} - x_{l,k} ) 
                \left(   
                \frac{\partial x_{m,k} }{\partial x_{i,k} } - \frac{\partial x_{l,k} }{\partial x_{i,k} }
                \right)
            \right\}
        \right]
    \end{aligned}$$



**Theorem 29**. **(Derivative of $T^{\ast}$ )*\
$$\frac{\partial T^{\ast} }{\partial x_{i,k} } = 2 \sum_{m < l} (x_{m,k} - x_{l,k}  ) 
        \left\{
            \frac{\partial x_{m,k} }{\partial x_{i,k} } - \frac{\partial x_{l,k} }{\partial x_{i,k} }
        \right\}$$



**Theorem 30**. **(Derivative of $S^{\ast}$ )*\
$$\frac{\partial S^{\ast} }{\partial x_{i,k} } = 
        \sum_{m < l} 2 (d_{m,l} - \hat{d}_{m,l}  ) \frac{\partial d_{m,l} }{\partial x_{i,k} } 
        -
        \sum_{m < l} 2
        \left( d_{m,l} - \hat{d}_{m,l}  \right)
        \frac{\partial \hat{d}_{m,l} }{\partial x_{i,k} }$$


## Self-Organizing Maps


**Definition 31**. **(SOM)*\
Consider a SOM with 2-dimensional rectangular grid of $K$ prototypes
$m_{j} \in \mathbb{R}^p$ - each prototype parametrized w.r.t an integer
coordinate pair $\ell_{j} \in \mathcal{Q}_1 \times \mathcal{Q}_2$ where
$\mathcal{Q}_i = \{1, \ldots , q_i \}$*



**Algorithm 2**. **(SOM Algorithm)**

1.  *Sample $X_{i} \in \mathbb{R}^p$*

2.  *Find the prototype $m_{j}$ that is closest to $X_{i}$ and the
    closest neighbours $m_{\ell }$ of $m_{j}$ - determined by distance
    $r$*

3.  *move neighbours $m_{k}$ towards $X_{i}$ via
    $$m_{j} \leftarrow m_{j} + \alpha  (X_{i} - m_{j} )$$



**Definition 32**. **(Closeness of configurations)*\
Given $X,Y$ measure their closeness using

$$G(X,Y) = \sum_{k=1}^{K} \sum_{i=1}^{n} (X_{i,k} - Y_{i,k} )^{2}$$ 

Aim to minimise $G$ under the following group actions: translation group,
Euclidean group and similarity group.\
Done in order*

1.  *Match translation - by matching the centroids.*

2.  *Match Rotation*

3.  *Match Scale change*



**Definition 33**. **(Frobenius Norm)*
$$\left< A,B \right>_{F} = \sum_{i,j} \overline{A}_{i,j}  B_{i,j} = \operatorname{tr} (\overline{A}^T B)$$
Consider only real-valued matrices we have
$$\left\vert \left\vert A \right\vert  \right\vert^{2}_{F}= \left< A,A \right>_{F}$$



**Proposition 34**. **(Norm Form)*\
Given $X$ and $A = YP$ configurations, where $P$ a rotation matrix.
$$G(X,A)= \left\vert \left\vert X-A \right\vert  \right\vert^{2}_{F}$$
So we have to minimise $G$ we find $P^{\ast}$ $$\begin{aligned}
        P^{\ast}&= \underset{P}{\mathop{\arg\ \max}} \left< P, Y^T X  \right>_{F}\\
        U \Sigma V^T &= Y^T X \text{ (the SVD of } Y^T X)\\
        P^{\ast} &= VU^T
    \end{aligned}$$



**Definition 35**. **(Procrustes Distance)*\
The minimised distance when $P = P^{\ast}$ $$\begin{aligned}
        \left\vert \left\vert YP^{\ast} - X \right\vert  \right\vert^{2}_{F} &= \left\lVert Y\right\rVert^{2}_{F} + \left\lVert X\right\rVert^{2}_{F} - 2 \underbrace{\left< I, \Sigma  \right>_{F}}_{= \operatorname{tr} (\Sigma )}
    \end{aligned}$$



**Definition 36**. **(Generalised Procrustes Analysis Algorithm)**

1.  *Choose arbitrary configuration $X_{i}$ and set $M = X_{i}$*

2.  *Use Procrustes Analysis to match all configurations to $M$ - giving
    matched configurations $\{Y_{i}\}_{i = 1}^L$ and matching matrices
    $\{R_{\ell } \}^{L}_{\ell }$*

3.  *Compute mean shape of all matched configurations
    $$M \leftarrow L^{-1} \sum_{i=1}^{L} Y_{i}$$

4.  *Compute $S_{\{X_{\ell } \}_{\ell =1}^L} (\{R_{\ell =1 }^L\}, M)$
    and check convergence, if not go to 2.
    $$\text{Defined: }\quad S_{\{X_{\ell } \}_{\ell =1}^L} (\{R_{\ell =1 }^L\}, M) = \sum_{\ell =1}^{L} \left\lVert X_{\ell } R_{\ell } - M\right\rVert^{2}_{F}$$


# Basis Expansions and Regularizations

## Introduction


**Definition 37**. **(Linear basis expansion)*\
Denote by $$h_{m}(X): \mathbb{R}^p \mapsto \mathbb{R}$$ the $m$th
transformation of $X$, $m = 1 , \ldots , M$\
Then model $$f(X) = \sum_{m=1}^{M} \beta_{m}h_{m}(X)$$ Examples*

-   *$h_{m}(X) = X_{m}$ - linear regression*

-   *$h_{m}(X) = X_{m}^{2}$ - quadratic regression*

-   *$h_{m}(X) = \log (X_{m}), \sqrt{X_{j}}$*

-   *$h_{m}(X) = \mathbb{I}( L_{m} \leq  X_{m} \leq  U_{m})$ - can use
    to construct piecewise constant functions*


### Complexity Control

-   Restriction Methods Where we limit class of functions before hand -
    e.g. insist on additive models of the form $$\begin{aligned}
            f(X) &= \sum_{j=1}^{p} f_{j}(X_{j})\\
            &= \sum_{j=1}^{p} \sum_{m=1}^{M_{j}} \beta_{j,m} h_{j,m} (X_{j})
        \end{aligned}$$

    Size of model limited by number of basis functions $M_{j}$ for each
    component function $f_{j}$.

-   Selection Methods: which continually look at the dictionary and put
    in members (basis functions) that improve the fit or remove those
    which are not contributing. For example, variable selection methods
    such as forward stepwise.

-   Regularization methods: where the whole dictionary is included,but
    the coefficients are restricted - e.g. ridge regression or the lasso

## Piecewise Polynomials and Splines


**Definition 38**. **(Piecewise Constant)*
$$f(X) = \sum_{m=1}^{M} \beta_{m} \mathbb{I}( L_{m} \leq  X \leq  U_{m})$$
For some partition of the input space $\{L_{m}, U_{m}\}_{m=1}^M$\
Least squares will yield $\hat{\beta}_{m} = \overline{X}_{m}$ the mean
of $X$ in the $m$th region.*



**Definition 39**. **(Piecewise Linear)*\
We require additional basis functions - for each slice of our partition
we have the polynomial: $\beta_m + \beta_{m+M}X$*

*$$f(X) = \sum_{m=1}^{M} \beta_{m} \mathbb{I}( L_{m} \leq  X \leq  U_{m}) + \beta_{m + M} \mathbb{I}( L_{m} \leq  X \leq  U_{m})X$$



**Definition 40**. **(Continuous Piecewise linear)*\
We start with $2M$ free parameters, but the continuous constraint means
we now have instead $M - 1$ degrees of freedom\
Can alternatively build the constraints into the basis functions
$$h_1 (X) = 1, \quad h_2(X) = X, \quad h_3(X) = (X - \xi_1)_+, \quad h_4(X) = (X - \xi_2)_+, \quad \ldots$$



**Definition 41**. **(Piecewise cubic polynomials)*\
As above but with a cubic on each piece - giving us continuity and
continuity of first and second derivatives - total function called a
**cubic spline** An order-$M$ spline with knots
$\xi_{j}, j = 1, \ldots , K$ a piecewise polynomial of order $M$\
A truncated-power basis set would be*

*$$\begin{aligned}
        h_{j}(X) &= X^{j-1} \quad j = 1, \ldots , M\\
        h_{M+j}(X) &= (X - \xi_{j})_{+}^{M-1} \quad j = 1, \ldots , K
    \end{aligned}$$



**Definition 42**. *A natural cubic spline with $K$ knots represented by
$K$ basis functions
$$N_1(X) = 1, \quad N_2(X) = X, \quad N_{k+2} (X) = d_{k}(X) - d_{K-1}(X)$$
where
$$d_{k}(X)= \frac{(X - \xi_{k})^{3}_{+} - (X - \xi_{K})^{3}_{+}}{\xi_{K} - \xi_{k}}, \quad k = 1 , \ldots , K-2$$


## Smoothing Splines


**Definition 43**. **(Smoothing Splines)*\
A smoothing spline is a function $f$ that minimizes
$$RSS(f,\lambda ) = \sum_{i=1}^{N} \left( y_{i} - f(x_{i})\right)^{2} + \lambda \int f''(t)^{2} dt$$
where $\lambda \geq 0$ is a smoothing parameter.\
First term measures fidelity of fit to the data, second term measures
roughness of $f$ - penalising curvature.*

-   *$\lambda = 0$ - interpolating spline, $f \in \mathcal{F}$ can be
    any function*

-   *$\lambda \rightarrow \infty$ - the simple least squares line fit,
    since no second derivative can be tolerated*

*The solution is a natural spline, can write it as

$$f(x) = \sum_{j=1}^{n} N_{j}(x) \theta_{j}$$ 

where $N_{j}(x)$ a
$n$-dimensional set of basis functions.\
Criterion simplifies to
$$RSS(\theta , \lambda ) = (y - N \theta )^T (y - N \theta ) + \lambda \underbrace{\theta^T \Omega_{n} \theta}_{= \int f''(t)^{2} dt}$$
Where matrix $\{N\}_{i,j} = N_{j}(x_{i})$ and
$(\Omega_{n})_{i,j} = \int N_{i}^{''} (t) N_{j}^{''} (t) dt$\
Fitted smoothing spline is then
$$\hat{f} (x) = \sum_{j=1}^{n} N_{j}(x)\hat{\theta}_{j}, \quad \hat{\theta} = (N^T N + \lambda \Omega_{n})^{-1}  N^T y$$


### Degrees of freedeom and Smoother Matrices

If $\lambda$ prechosen - gives linear smoother spline. This is because
the estimated parameters $\hat{\theta}$ are a linear combination of the
yi.\
Then
$$\hat{f} = N(N^T N + \lambda \Omega_{n})^{-1}  N^T y = S_\lambda y$$

Where $S_\lambda$ the **smoother matrix** - only dependent on $x$ and
$\lambda$


**Definition 44**. **(Effective degrees of freedom for splines)*
$$df_\lambda = \operatorname{tr} (S_\lambda )$$



**Proposition 45**. **(Smoother matrix)*\
$S_\lambda$ is symmetric and positive semidefinite\
Can write it as $$S_\lambda - (I + \lambda K)^{-1}$$ Where $K$
independent of $\lambda$\
Sine $\hat{f}  = S_\lambda y$ solves

$$\mathop{\min}_{f} (y - f)^T (y-f) + \lambda f^T Kf$$

call $K$ the **penalty matrix***

*Eigen-decomposition of $S_\lambda$ is

$$S_\lambda  = \sum_{k=1}^{n} \rho_{k}(\lambda ) u_{k}u_{k}^T$$ 

Where
$u_{k}$ the eigenvectors and $\rho_{k}(\lambda )$ its eigenvalues.\
Can show that $$\rho_{k}(\lambda ) = \frac{1}{1+ \lambda d_{k}}$$
$d_{k}$ the corresponding eigenvalue of $K$*



**Proposition 46**. **(Facts about smoothing spline)**

-   *The eigenvectors are not affected by $\lambda$ , the whole family
    of smoothing splines (for a particular $x$ ) indexed by $\lambda$
    have the same eigenvectors.*

-   *$S_\lambda  y = \sum_{k=1}^{n} u_{k} \rho_{k}(\lambda ) \left< u_{k},y \right>$\
    So, the smoothing spline operation decomposes $y$ into the basis $u$
    and then shrinks the components by $\rho_{k}(\lambda )$ (whereas
    selection does 0-1).*


## Automatic Selection of the Smoothing Parameters


**Definition 47**. **(LOOCV)* - **leave one out cross-validation** to
select $\lambda$.\
Aim to minimise $$\mathbb{E} \left[ 
            \int 
            \left\{ 
                \hat{f}_\lambda (x) - f(x)
            \right\}^{2}  dx
        \right] = \text{MISE}$$ Estimate MISE by
$$\operatorname{CV}(\hat{f}_\lambda ) = \sum_{i=1}^{N} \left( y_{i} - \hat{f}_{\lambda}^{(i)}(x_{i})\right)^{2}$$
where $\hat{f}_{\lambda}^{(i)}(x_{i})$ is the fitted value at $x_{i}$
with the $i$th observation deleted from the data set used to fit the
smoother.\
Can show that
$$\operatorname{CV}(\hat{f}_\lambda ) = \frac{1}{N} \sum_{i=1}^{N} \left( \frac{y_{i} - \hat{f}(x_{i})}{1 - S_{\lambda}(ii)}\right)^{2}$$
where $S_{\lambda}(ii)$ is the $i$th diagonal element of $S_\lambda$\
This is a **generalized cross-validation** (GCV) score.*


# Kernel Smoothing Methods


**Definition 48**. **Kernel function*\
$K\colon \mathbb{R} \to \mathbb{R}$ satisfying*

-   *$K(x) \geq  0, \forall x$*

-   *$\int_{\mathbb{R}} K(x) = 1$*

-   **Usually:* $K(-x) = K(x)$ and $K$ smooth*



**Definition 49**. **(Kernel density estimator)*\
KDE for $X_1, \ldots , X_{n}$ with kernel function $K$ and bandwidth $h$
given by $$\hat{f}_{n,h,K} (x) = \frac{1}{nh} \sum_{i=1}^{n} K 
        \left( 
            \frac{x - X_{i}}{h}
         \right)$$ Choice of bandwidth is important.\
*

-   *$h$ smaller $\rightarrow$ higher variance, lower bias*

-   *$h$ larger $\rightarrow$ higher bias, lower variance*



**Proposition 50**. **(Bias and variance - rectangular kernel)*\
Given observation $X$ what is probability of landing in interval
$(x - \frac{h}{2}, x+\frac{h}{2})$*

*$$\begin{aligned}
        \sum_{i=1}^{n} K (\frac{X_{i}-x}{h}) &\text{ - number of } X_{i} \text{ in interval}\\
        \hat{f}_{n,h,K} (x) &= \frac{1}{nh} \sum_{i=1}^{n} K (\frac{X_{i}-x}{h}) \text{ avg num of points}/h\\
        \underbrace{nh \hat{f}_{n,h} (x)}_{N^{\ast} } &\sim Bin(n,p)\\
        \mathbb{E} \left[ N^{\ast}  \right] = np, &\quad var(N^{\ast} ) = np(1-p)\\
        \mathbb{E}
        \left[ 
            \hat{f}_{n,h} (x) 
        \right] &= \frac{F(x+ \frac{h}{2}) - F(x - \frac{h}{2})}{h} \xrightarrow[h \to 0]{} f(x)\\
        var[nh \hat{f}(x)] &= \frac{1}{nh} \frac{F(x-\frac{h}{2}, x+ \frac{h}{2})}{h} 
        \left\{1 - F\left(x - \frac{h}{2}, x+ \frac{h}{2}\right)\right\}\\
        var(\hat{f} x) &\thickapprox \frac{1}{nh} f(x)
    \end{aligned}$$



**Proposition 51**. **(Finding optimum $h$)*\
Use taylor approximations with assumption that $f$ is twice
differentiable $$\begin{aligned}
        F(x + \frac{h}{2}) &= F(x) + \frac{h}{2}f(x) + \frac{1}{2}f^\prime (x) \left( \frac{h}{2} \right)^{2} + \frac{1}{6}f^{\prime \prime} (x) \left( \frac{h}{2} \right)^{3} + \mathcal{O}(h^4)\\
        F(x - \frac{h}{2}) &= F(x) - \frac{h}{2}f(x) + \frac{1}{2}f^\prime (x) \left( \frac{h}{2} \right)^{2} - \frac{1}{6}f^{\prime \prime} (x) \left( \frac{h}{2} \right)^{3} + \mathcal{O}(h^4)\\
        bias( \hat{f} (x)  ) &= \frac{F(x- h /2, x+ h .2)}{h} - f(x) \thickapprox \frac{1}{24} h^{2} f^{\prime \prime} (x)\\
        MSE( \hat{f}_{n,h,k}(x) ) &\thickapprox C_1 \frac{1}{nh} f(x) + C_2(f^{\prime \prime}(x))^{2} h^4, \quad C_1 = 1, C_2 = \frac{1}{24}^{2} \\
        h^{\ast} &= C^{\ast} n^{-\frac{1}{5}} \text{ where } C^{\ast} = \left[ 
            \frac{C_1}{4C_2} \frac{f(x)}{f^{\prime \prime} (x)^{2} }
        \right]^{1 /5} \text{ the MSE optimal } h
    \end{aligned}$$



**Proposition 52**. **(Properties of optimal bandwidth)**

-   *$h_{n} \xrightarrow[n \to \infty ]{} 0$*

-   *$nh_{n} \propto n^{\frac{4}{5}} \xrightarrow[n \to \infty]{} \infty$*



**Proposition 53**. **(Expectation with general kernel)*
$$\begin{aligned}
        \mathbb{E}[\hat{f} (x)] &= \frac{1}{nh} \sum_{i=1}^{n} \mathbb{E}[K(\frac{X_{i}-x}{h})]\\
        &= hf(x) + \frac{1}{2}C_3 h^3 f^{^\prime\prime }(x) + \mathcal{O}(h^4)\\
        bias\{\hat{f}_{n,h,K}(x) \} &\thickapprox \frac{1}{2}C_3 h^{2} f^{\prime \prime} (x)
    \end{aligned}$$



**Proposition 54**. **(Bounding variance w/ general kernel)*
$$\begin{aligned}
        var\{\hat{f} (x)\} &= \frac{1}{nh^{2} }var \left[ K \left( \frac{X_{i}-x}{h} \right)  \right] \\
        &\leq  \frac{1}{nh}f(x)C_1 + \frac{1}{n}C_4 + \mathcal{O} (\frac{h}{n}) \xrightarrow[n \to \infty ]{} 0\\
        C_4 &= f^\prime (x) \int v K^{2} (v)dv
    \end{aligned}$$


## Kernel density estimation and Classification


**Definition 55**. **(Kernel Regression)*\
Given variables $X,Y$ wish to find $\mathbb{E}[Y\mid X]$*

*$$\begin{aligned}
        \mathbb{E} [Y \mid  X] &= \frac{\int y f(x,y)dy}{f(x)}\\
        \hat{f} (x) &= \frac{1}{n}\sum_{i=1}^{n} K_{h}(x - X_{i})\\
        \hat{\mathbb{E}}( Y \mid  X = x) &= \frac{\sum_{i=1}^{n} K_{h}(x- X_{i}) \int yK_{h}(y - Y_{i})dy}{\sum_{i=1}^{n} K_{h}(x- X_{i})}\\
        &= \frac{\sum_{i=1}^{n} Y_{i} K_{h}(x- X_{i})}{\sum_{i=1}^{n} K_{h}(x- X_{i})}
    \end{aligned}$$ Called the *Nadaraya-Watson estimator**


### (Local polynomial regression)


**Definition 56**. **(Local polynomial estimator)*

$$m_{x_0}(x) = \sum_{j=0}^{p} \beta_{j}(x_0) (x - x_0)^{j}$$

Centred on
$x_0$ or local to $x_0$\
We have weighted RSS

$$RSS(x_0) = \sum_{i=1}^{n} \{ Y_{i} - m_{x_0}(X_{i})\}^{2}  K_{h}(X_{i} - X_0)$$

And the design matrix and weight matrix, $$X = 
        \begin{pmatrix}
            1 & X_1 - x_0 & \ldots   &  (X_1 - x_0)^p \\
            \vdots & \vdots & \ddots & \vdots  \\
            1 & X_{n} - x_0 & \ldots & (X_{n} - x_0)^p  \\
        \end{pmatrix} \quad
        W_{x_0} = \operatorname{diag} \{
        K_{h}(X_1 - x_0), \ldots , K_{h}(X_{n}- x_0)   
        \}$$ Rewriting the RSS and minimising we get
$$RSS(x_0) = (Y - X\beta(x_0))^{T} W_{x_0} (Y - X\beta(x_0)), \quad \hat{\beta}(x_0) = (X^{T} W_{x_0} X)^{-1} X^{T} W_{x_0} Y$$



**Proposition 57**. **(Bias of NW)*\
Take $f(x)$ density of $\{X_{i}\}$ and
$g(x) = \mathbb{E}[Y \mid  X = x]$ the unknown regression function
$$bias_{NW}: h^{2} 
        \left\{ 
            \frac{1}{2} g^{\prime \prime} (x) + \frac{g^\prime (x)f^\prime (x)}{f(x)}
        \right\}
        \int K^{2}(u) du + \mathcal{O}(h^{2} )$$ Bias of local linear is
$$h^{2} \frac{1}{2}g^{\prime \prime} (x) \int u^{2} K(u) du + \mathcal{O}(h^{2} )$$
Generally choose odd polynomial order*


### Orthogonal Series Regression

Given $\{\rho_{v}(x)\}$ an orthogonal series basis for some function
space\
So for all $f$ in this space
$$f(x) = \sum_{v} f_{v}\rho_{v}(x), \quad f_{v} = \left< f, \rho_{v} \right>  = \int f(x) \rho_{v}(x)dx$$
Orthogonality gives
$$\int \rho_{v}(x) \rho_{w}(x)dx = \delta_{vw} \text{( The Kronecker delta)}$$
2D case
$$f(x,y) = \sum_{v} \sum_{u} f_{v,u}  \rho_{v}(x) \rho_{u}(y),\quad f_{v,u} = \int \int f(x,y) \rho_{v}(x) \rho_{u}(y) dx dy$$
Set of basis functions is *complete* for the function space
$$\lim\limits_{m \to \infty} \int 
    \left\{ 
        f(x) - \sum_{r=-m}^{m} f_{r} \rho_{r}(x)
    \right\}^{2} dx = 0, \quad \forall f$$


**Definition 58**. **(Orthogonal series estimator)**

*$$\begin{aligned}
        f_{v} &= \int f(x) \rho_{v} (x)dx = \mathbb{E}[\rho_{v}(X)]\\
        &\thickapprox \frac{1}{n} \sum_{i=1}^{n} \rho_{v}(X_{i})\\
        f_{v,u} &= \mathbb{E}[\rho_{v}(X) \rho_{u}(Y)] = \hat{f}_{v}\\
        &\thickapprox \frac{1}{n} \sum_{i=1}^{n} \rho_{v}(X_{i}) \rho_{u}(Y_{i}) = \hat{f}_{v,u} 
    \end{aligned}$$



**Proposition 59**. **(Properties of OS estimator)*
$$\mathbb{E}[\hat{f} (x)] = \frac{1}{n}\sum_{i=1}^{n} f(x) = f(x)$$
Unbiased - but cant use this to estimate $f(x)$ as $v$ often infinite.\
Estimating only for $v = -m , \ldots ,m$ and
$\hat{f} (x) = \sum_{v=-m}^{m} \hat{f}_{v}\rho_{v}(x)$\
$$\begin{aligned}
        bias(\hat{f} (x)) &= \mathbb{E}[ \hat{f} (x) -f(x)]\\
        &= - \sum_{\left\vert v \right\vert > m} f_{v} \rho_{v}(x)
    \end{aligned}$$ Not necessarily 0.*


# Basis Expansion

## Wavelet Smoothing

### Multiresolution Analysis (MRA)


**Definition 60**. **(MRA)*\
MRA used to examine functions at different scales - indexed by $j$\
Spaces $\{V_{j}\}_{j \in \mathbb{Z}}$ form a ladder
$$\ldots \subset V_{-1} \subset V_{0} \subset V_{1} \subset \ldots, \quad \overline{\bigcup_{j \in \mathbb{Z}} V_{j}} = L_{2}(\mathbb{R})$$
Where $L_2$ functions are those which, over a finite range, have a
finite number of discontinuities.\
Functions get progressively less detailed as $j \to -\infty$ so

$$\bigcap_{j \in \mathbb{Z}} V_{j} = \{0\}$$

the zero function

$$f(x) \in V_{j} \Rightarrow f(2x) \in V_{j+1}, \forall j \in \mathbb{Z}$$

and

$$f(x) \in V_0 \Rightarrow f(x-k) \in V_0, \forall k \in \mathbb{Z}$$

Integer translates of a function in $V_0$ are also in $V_0$

$$\exists \phi (x) \in V_0 \text{ s.t } \{\phi (x-k)\}_{k \in \mathbb{Z}} \text{ is an orthonormal basis for } V_0$$

If $\{V_{j}\}_{j \in \mathbb{Z}   }$ and $\phi$ satisfy the above then
they form a MRA*



**Definition 61**. **(Haar father wavelet)**

*$$\phi_{H}(x) =
        \begin{cases}
            1, &\text{ if } x \in (0,1) ;\\
            0, &\text{ otherwise }  .
        \end{cases}$$

*Given inner product $\left< f,g \right> = \int f(x)g(x) dx$*

*$$\left\lVert \phi_{H}\right\rVert^{2} = \left< \phi_{H},\phi_{H} \right> = \int \phi_{H}^{2}(x) dx = \int_0^1 1 dx = 1$$

*And $$\left< \phi_{H}(x- \ell ), \phi_{H}(x-m) \right> = \delta_{l,m}$$
Different integer translates do not overlap.\
$\{\phi_{H}(x - \ell )\}_{\ell \in \mathbb{Z}}$ form an orthonormal set
and we can set
$V_0 = \text{span}\{\phi_{H}(x - \ell )\}_{\ell \in \mathbb{Z}}$\
*



**Proposition 62**. *Dyadically scale and translate the wavelet by
$$\phi_{j,k} (x) = 2^{\frac{j}{2}} \phi (2^{j}x - k), \quad \forall j,k \in \mathbb{Z}$$
$\{\phi_{j,k} (x)\}_{k \in \mathbb{Z}}$ is an orthonormal basis for
$V_j$\
Show that for function $f(x)$
$$P_{j}f = \sum_{k \in \mathbb{Z}} c_{j,k} \phi_{j,k} (x)$$ For
$j = 5,3,1$ ; the projection of $f(x)$ onto $V_{j}$, where
$$c_{j,k} = \int f(x) \phi_{j,k} (x) dx$$



**Definition 63**. **(Haar mother wavelet)* $$\psi_{H}(x) =
        \begin{cases}
            1, &\text{ if } x \in (0,\frac{1}{2}) ;\\
            -1, &\text{ if } x \in (\frac{1}{2},1) ;\\
            0, &\text{ otherwise }
        \end{cases}$$

*Call space spanned by $\psi(x-k)$ $W_0$ and note that $\psi (x)$
orthonormal to $\phi(x)$ with their respective spaces being orthonormal
too.\
Extend the idea across all scales and locations*

*$$f(x) = \sum_{k \in \mathbb{Z}} c_{j_0,k} \phi_{j_0,k} (x) + \sum_{j=0}^{\infty} \sum_{k \in \mathbb{Z}} d_{j,k} \psi_{j,k} (x)$$

*For function $f(x)$ at scale $j_0$...\
Infinite scales yield*

*$$L_2 = V_{j_0} \bigoplus_{j = j_0}^{\infty} W_j$$

*Call the set $\{d_{j,k} \}$ the **wavelet coefficients***



**Proposition 64**. **(Wavelet coefficients)*\
Given that we have $c_{1,0}, c_{1,1}$ can obtain $$\begin{aligned}
        c_{0,0} &= \frac{1}{\sqrt{2}} (c_{1,1} + c_{1,0})\\
        d_{0,0} &= \frac{1}{\sqrt{2} } (c_{1,1} - c_{1,0})
    \end{aligned}$$ Generalising to $$\begin{aligned}
        c_{j-1,k} &= \frac{1}{\sqrt{2} } (c_{j,2k+1} + c_{j,2k})\\
        d_{j-1,k} &= \frac{1}{\sqrt{2} } (c_{j,2k+1} - c_{j,2k})
    \end{aligned}$$



**Definition 65**. **(Wavelet transform)*\
A wavelet has $m$ vanishing moments if
$$\int x^{j} \psi(x) dx = 0, \quad \forall j = 0,1,\dots,m-1$$


### Wavelet Shrinkage

Suppose we have model
$$y_{i} = f_{i} + \epsilon_{i}, \quad i = 1, \ldots ,n$$ Where we
observe $\{y_{i}\}_{i=1}^n$. Assume $\epsilon_{i}$ are IID random
variables with mean $0$ and var $\sigma^{2}$ - $\epsilon$ vector then
has covariance matrix $\sigma^{2} I_{n}$\
$\{f_{i}\}_{i=1}^n$ are unknown functions and we want to estimate them.\
Wavelet transform $e = W\epsilon$
$$\mathbb{E}[e] = W \mathbb{E}[\epsilon] = 0 \quad var(e) = \mathbb{E}[ee^T] = \sigma^{2} I_{n}$$
Applying $W$ to our model we get $$w= d + e$$ The noise $e$
uncorrelated - gets spread evenly across all coefficients.\
The signal $d$ is sparse - we have that
$\left\lVert d\right\rVert = \left\lVert f\right\rVert$. So $f$ is
sparse in the wavelet domain - improving the signal to noise ratio
greatly.

### Thresholding Types


**Definition 66**. **(Hard Thresholding)*
$$T_{hard} (w, \lambda ) = w \mathbb{I}(\left\lVert w\right\rVert > \lambda )$$



**Definition 67**. **(Soft Thresholding)*
$$T_{soft} (w, \lambda ) = \text{sign}(w) (\left\lVert w\right\rVert - \lambda ) \mathbb{I}(\left\lVert w\right\rVert > \lambda )$$



**Definition 68**. **(Bayesian Wavelet Shrinkage)*\
Natural to think about wavelet coefficients having the prior
distribution
$$d_{j, \cdot } = \gamma_{j}N(0,\tau_{j}^{2}) + (1- \gamma_{j}) \delta_0 (x)$$
$\delta_0 (x)$ is the Dirac delta function at 0, $\gamma_{j}$ a
Bernoulli random variable with parameter $p_{j}$\
Likelihood comes from $w = d+e$, if $e \sim N(0,\sigma^{2} I_{n})$ then
$w \mid d \sim N(d, \sigma^{2} )$\
Can show $$F(d\mid w) = r \Phi 
        \left\{ 
            \frac{d - w \nu^{2} }{\sigma \nu }
        \right\} + (1-r) \mathbb{I}(d>0)$$ where $\Phi$ the CDF of the
standard normal, $\nu^{2} = \tau^{2} (\sigma^{2} + \tau^{2} )^{-1}$ and
$r \in (0,1)$*


# Cluster Analysis

## Independent Component Analysis and Exploratory Projection Pursuit

### Latent Variables and Factor Analysis

Saw the SVD of a $n\times p$ matrix $X$ as
$$X = \underbrace{U}_{n\times p } \underbrace{D}_{p \times p, d_{ii}\geq 0} \underbrace{V^T}_{p \times p}$$
With the $p\times p$ sample covariance matrix $S = n^{-1} X^T X$ as
$$S = n^{-1} X^T X = n^{-1} V D^{2} V^T$$ an eigen-decomposition, with
eigenvectors $v_{j}$ (principal components) with eigenvalues
$d^{2}_{j}$\
Can project the $X$ onto principal components forming
$$z_{n\times 1} = X_{n\times p} v_{p\times 1}$$ With
$Var(z_{i}) = \frac{d_{i}^{2}}{n}$ once projected onto $v_{i}$


**Proposition 69**. **(Projection onto arbitrary vector)*\
Suppose we project onto arbitrary $p$ vector $a$
$$y_{n\times 1}  = X_{n\times p} a$$ Then
$$n^{-1} y^T \mathbf{1} = n^{-1} a^T X^T \mathbf{1} = 0
        ,\quad Var(y_{i}) = S_{y}(a) = n ^{-1} y^T y = a^T S a$$



**Proposition 70**. **(Optimisation formulation of PCA)*
$$\text{ First PC: } \mathop{\max}_{a} S_{y}(a) \text{ given } a^T a = 1$$
$$i\text{th PC} : \mathop{\max}_{a} S_{y}(a) \text{ given } a^T a = 1, a^T v_{j} = 0, \forall j = 1,\dots,i-1$$



**Definition 71**. **(Kullback-Liebler Divergence of $g$ from $f$ )*
$$D_{KL} (f\mid g) = \int g(x) \log \left\{ \frac{g(x)}{f(x)} \right\} dx$$
Easy to see that $D_{KL} (g \mid f) \geq  0$ with equality if and only
if $f=g$\
*



**Definition 72**. **Entropy of density $g$*
$$H(g) = - \int_{\mathbb{R}} g(x) \log g(x) dx$$



**Proposition 73**. **(Gaussian maximises entropy)*\
$f(x)$ density of $N(0,\sigma^{2} )$ and $g$ arbitrary any other density
with mean $0$ and variance $\sigma^{2}$ $$H(g) \leq H(f)$$



**Definition 74**. **(Sphering)*\
Transform matrix so its variance is the identity matrix.
$$S = n^{-1} X^T X \quad R = S^{-1/2} \quad \underbrace{W}_{\text{sphered}} = XR$$
This makes PC redundant as $$var(Wa) = a^T S_{W} a = a^T a = 1$$



**Algorithm 3**. **Process and Optimisation**

1.  *Start with centred and sphered matrix $W$*

2.  *Choose initial unit projection vector $a$*

3.  *Form projected data $u_{a} = Wa$*

4.  *Form density estimate, $\hat{f}_{U,a}(u)$ from
    $u_1, \ldots , u_{n}$*

5.  *Compute entropy $H\{\hat{f}_{U,a}(u) \}$*

6.  *Solve
    $\underset{a: a^T a = 1}{\mathop{\arg\ \min}} H \{\hat{f}_{U,a}(u) \}$*

7.  *Build up multidimensional solutions by optimising over unit $b$
    orthogonal to $a$*



**Definition 75**. **(Factor Analysis Model)*\
$X = UDV^T$ has latent variable representation\
Writing $S = \sqrt{n} U$ and $A^T = DV^T / \sqrt{N}$ we have $X = SA^T$\
$$\begin{aligned}
        X_{i,1} &= a_{1,1} S_{i,1} + \dots + a_{1,p} S_{i,p}\\
        X_{i,2} &= a_{2,1} S_{i,1} + \dots + a_{2,p} S_{i,p}\\
        &\vdots\\
        X_{i,p} &= a_{p,1} S_{i,1} + \dots + a_{p,p} S_{i,p}\\
        X &= AS
    \end{aligned}$$


$X$ will be correlated, but want $S$ to be uncorrelated.\
Assume $X$ centered (so is $S$ )


**Proposition 76**. **(Covariance of S)*
$$n^{-1} S^T S = n^{-1} U^T U = I$$ So $S$uncorrelated\
But for $R$ orthogonal, write
$$X = SA^T = SR R^T A^T = S^{\ast} (A^{\ast} )^T$$ with
$\mathrm{Cov}\left[ S^{\ast}  \right] = I_{p}$\
So there is no unique decomposition into uncorrelated factors
$S_1, \ldots, S_p$*



**Definition 77**. **(Classical Factor Analysis)* $$\begin{aligned}
        X_{i,1} &= a_{1,1} S_{i,1} + \dots + a_{1,q} S_{i,q} + \epsilon_{i,1} \\
        X_{i,2} &= a_{2,1} S_{i,1} + \dots + a_{2,q} S_{i,q} + \epsilon_{i,2}\\
        &\vdots\\
        X_{i,p} &= a_{p,1} S_{i,1} + \dots + a_{p,q} S_{i,q} + \epsilon_{i,p}
    \end{aligned}$$ Here there are $q <p$ factors, $\epsilon$ are zero
mean and uncorrelated and $S$ assumed to be Gaussian*


### Independent Component Analysis


**Definition 78**. **(Independent Component Analysis)*\
$X = AS$ with $A$ unknown and $S$ independent\
$X$ is observed, $A$ is unknown, $S$ is unknown\
Aim to find orthogonal $A$ and $S$ independent\
If $Y$ has pdf $g$ we say that the entropy of $Y$ is
$$H(Y) = H(g) = - \int g(y) \log g(y) dy$$



**Definition 79**. **(Mutual Information)*
$$I(Y) = \sum_{j=1}^{p} H(Y_{j}) - H(Y)$$ Call $I(Y)$ the
Kullback-Lieber distance between the density $g(y)$ of $Y$*



**Proposition 80**. **(Mutual Information)*\
If $X$ has covariance matrix $I$ and $Y = A^T X$ then
$$I(Y) = \sum_{j=1}^{p} H(Y_{j}) - H(Y) - \log \left\vert det\ A \right\vert  = \sum_{j=1}^{p} H(Y_{j}) - H(X)$$
Minimising this over $A$.*


# Neural Networks

## Projection Pursuit Regression


**Definition 81**. **(Projection Pursuit Regression)*\
Here the model is $$f(X) = \sum_{m=1}^{M} g_{m}(\omega_{m}^T X)$$ this
is an additive model on the derived directions $V_{m} = \omega_{m}^T X$
and not the $X$ directly, $\omega_{m}$ are unit vectors\
Call $g_{m}(\omega_{m}^T X)$ the ridge function in $\mathbb{R}^p$ and
only varies in direction $\omega_{m}$\
$V_{m}$ is the projection of $X$ onto $\omega_{m}$ and want to find
$\omega_{m}$ so the model fits will; like projection pursuit.\
If $M$ is taken arbitrarily large, for appropriate choice of $g_{m}$ the
PPR model can approximate any continuous function in $\mathbb{R}^{p}$ -
called *universal approximation property**



**Proposition 82**. **(Fitting PPR models)*\
Suppose we have training data
$(x_{i},y_{i}), i = 1, \ldots,  ; x_{i} \in \mathbb{R}^p$\
Want to find approximate minimisers of error $$E = \sum_{i=1}^{n} 
        \left\{ 
            y_{i} - \sum_{m=1}^{M} g_{m}(\omega_{m}^T x_{i})
        \right\}^{2}$$ over $\{g_{m}\}$ and direction vectors
$\{\omega_{m}\}$\
*

-   *Considering the one term case $M= 1$- given direction vector
    $\omega$ can form the derived variable $v_{i} = w^T x_{i}$. We have
    a 1D smoothing problem, can apply smoothing spline to obtain an
    estimate of $g$*

-   *Or given $g$ can minimise the error $\omega$ using a Gauss-Newton
    Search.*



**Proposition 83**. **(Gauss-Newton Search)*\
Let $\omega_{old}$ be the current estimate for $\omega$, then
$$g(\omega^T x_{i}) \thickapprox g(\omega_{old}^T x_{i}) + g'(\omega_{old}^T x_{i}) (\omega  - \omega_{old})^T x_{i}$$
So that $$E \thickapprox \sum_{i=1}^{n} g^\prime (w_{old}^T x_{i})^{2} 
        \left[ 
            \left\{ 
                w_{old}^T x_{i} + \frac{y_{i}- g(\omega_{old}^T x_{i})}{g^\prime (w_{old}^T x_{i} )}
            \right\} - w^T x_{i}
        \right]^{2}$$ Minimising the RHS requires we carry out a least
squares regression with target
$w_{old}^T x_{i} + \frac{y_{i}- g(\omega_{old}^T x_{i})}{g^\prime (w_{old}^T x_{i} )}$
and predictor $x_{i}$ with weights $g^\prime (w_{old}^T x_{i})^{2}$ and
no intercept - gives $\omega_{new}$*



**Algorithm 4**. *PPR algorithm iterates as follows*

-   *finding good $g$ using current $\omega$*

-   *using $g$ to update current $\omega$ to $\omega$*

-   *Iterate until convergence - only need to examine changes in
    $\omega$*

*Can decide optimal $M$ by cross validation*


## Neural Networks


**Definition 84**. **(Neural Network Model)*\
The model has $X_1 , \ldots, X_{p}$ explanatory variables at the bottom,
with $K$ units at the top - for regression $K = 1$, for classification
we use $K$ units for each class.\
The model is $$\begin{aligned}
        Z_{m} &= \sigma (\alpha_{0,m} + \alpha_{m}^T X), m = 1, \ldots, M\\
        T_{k} &= \beta_{0,k} + \beta_{k}^T Z, k = 1, \ldots, K\\
        f_{k}(X) &= g_{k}(T_{k}), k = 1, \ldots, K
    \end{aligned}$$ where $Z = (Z_1, \ldots, Z_{M})$ and
$T = (T_1, \ldots ,T_{K} )$\
Call $\sigma (v)$ the activation function,
$$\sigma (v) = \frac{1}{1 + e^{-v}}$$ Output function $g_{k}(T)$ permits
final transformation of vector of outputs - for regression
$g_{k}(T) = T_{k}$ and for classification
$g_{k}(T) = \frac{e^{T_{k}}}{\sum_{l=1}^{K} e^{T_{l}}}$ the softmax
function.\
$Z_{m}$ are the hidden units not directly observed - often many hidden
layers.\
If $\sigma$ the identity then back to linear model.*



**Proposition 85**. **(ANN vs. PPR)*\
PPR model uses non-parametric functions $g_{m}(v)$ whereas ANN uses
simpler function based on $\sigma (v)$\
Can write
$$g_{m}(\omega_{m}^T X ) = \beta_{m}\sigma (\alpha_{0,m} + \left\lVert \alpha_{m}\right\rVert (\omega^T X) )$$
where $\omega_{m} = \alpha_{m} / \left\lVert \alpha_{m} \right\rVert$
the $m$th unit vector.\
Since $\sigma$ less complex than $g_{m}$ need more layers to get same
approximative power.*


## Fitting Neural Networks


**Proposition 86**. **(Fitting Neural Networks)*\
Given training data $(x_{i}, y_{i}), i = 1, \ldots, n$ want to find
$$\begin{aligned}
        \{ \alpha_{0,m}, \alpha_{m}: m = 1, \ldots, M\}&, \quad M(p + 1) \text{ weights} \\
        \{ \beta_{0,k}, \beta_{k}: k = 1, \ldots, K  \}&, \quad K(M+1) \text{ weights} 
    \end{aligned}$$ to minimise the error, the usual sum of squares
$$R(\theta ) = \sum_{k=1}^{K} \sum_{i=1}^{n} (y_{ik} - f_{k}(x_{i}))^{2}$$
Typically need constraints to avoid overfitting.*

-   **Backpropagation* - use gradient descent to minimise $R(\theta )$*



**Proposition 87**. **(Backpropagation)*\
Need to compute the gradient of $R(\theta )$ with respect to each
weight.\
$$\begin{aligned}
        \frac{\partial R_{i}(\theta )}{\partial \beta_{k,m}} &= \underbrace{-2 (y_{ik} - f_{k}(x_{i})) g_{k}^\prime (\beta_{k}^T z_{j} + \beta_{0,k} )}_{\delta_{k,i} } z_{m,i} = \delta_{k,i} z_{m,i}  \\
        \frac{\partial R_{i}(\theta )}{\partial \alpha_{m,l} } &= \underbrace{-2 \sum_{k=1}^{K}  (y_{ik} - f_{k}(x_{i})) g_{k}^\prime (\beta_{k}^T z_{i} + \beta_{0,k} ) \beta_{k,m} \sigma^\prime (\alpha_{0,m} + \alpha_{m}^T x_{i})}_{s_{m,i} } x_{il} = s_{m,i} x_{il}
    \end{aligned}$$ Use these to form the gradient descent algorithm by
$$\begin{aligned}
        \beta_{k,m}^{(r+1)} = \beta_{k,m}^{(r)} - \gamma_{r} \frac{\partial R_{i}(\theta )}{\partial \beta^{(r)}_{k,m}}\\
        \alpha_{m,l}^{(r+1)} = \alpha_{m,l}^{(r)} - \gamma_{r} \frac{\partial R_{i}(\theta )}{\partial \alpha^{(r)}_{m,l}}
    \end{aligned}$$ Where $\gamma_{r}$ the learning rate.\
In total we get
$$s_{m,i} = \sigma^\prime (\alpha_{0,m} + \alpha_{m}^T x_{i}) \sum_{k=1}^{K} \delta_{k,i} \beta_{k,m}$$
We have the algorithm in 2 stages*

1.  **Forward pass* - fixed current weights - and predicted values
    $\hat{f}_{k}(x_{i})$ computed*

2.  **Backward pass* - errors $\delta_{k,i}$ and $s_{m,i}$ computed to
    form gradients for the updates.*



**Proposition 88**. **(Issues with fitting ANNs)**

-   *Starting values - usually chosen to be random, but small, near 0.*

-   *Overfitting - need to use cross-validation to choose number of
    hidden units and layers.*

-   *Scaling of inputs - sensitive to input scales, usually centre and
    standardise inputs*


# Additive Models, Trees and Related Methods

## Tree-Based Methods

### Regression Trees


**Proposition 89**. **(Growing a tree)*\
Given data of $p$ inputs and a response for each $N$ observations;
$(x_{i},y_{i}), i = 1, \ldots , N$ with
$x_{i} = \begin{pmatrix} x_{i1} , \ldots ,x_{ip}  \end{pmatrix}$\
Need to decide splitting variables, and split points, and topology of
tree.\
Suppose we have $M$ regions in our partition, $R_1, \ldots ,R_{M}$ model
the response as a constant $c_{m}$ in each region
$$f(x) = \sum_{m=1}^{M} c_{m} I(x \in R_{m})$$ Easy to see that the best
$\hat{c}_{m}$ minimising the sum of squares is the mean of the response
in each region
$$\hat{c}_{m} = ave ( y_{i} \mid  x_{i} \in R_{m})= \frac{1}{n_{m}} \sum_{i: x_{i}\in Rm} y_{i}$$
Apply a greedy algorithm to find the best partitioning of the data.\
*

1.  *Start with all data in one region*

2.  *Find best split of data into 2 regions*

3.  *Repeat for each region until stopping criterion met*

*Consider splitting variable $j = 1, \ldots ,p$ and split point $s$,
define the pair of half-planes
$$R_1 (j,s) = \{x \mid  X_{j} <S\} \text{ and } R_2 (j,s) = \{x \mid  X_{j} \geq S\}$$
Seek splitting variable $j$ and split point $s$ that solves
$$\mathop{\min}_{j,s} 
        \left\{ 
            \underbrace{\mathop{\min}_{c_1}
             \sum_{X_{i} \in R_1(j,s)} (y_{i} - c_{1})^{2}}_{= \hat{c}_1} +
            \underbrace{\mathop{\min}_{c_2} 
            \sum_{X_{i} \in R_2(j,s)} (y_{i} - c_{2})^{2}}_{= \hat{c}_2}
        \right\} =
        \mathop{\min}_{j,s} 
        \left( \sum_{X_{i}\in R_1(j,s)} (y_{i} - \hat{c}_1)^{2} 
        + \sum_{X_{i}\in R_2(j,s)} (y_{i} - \hat{c}_2)^{2}  \right)$$
Can now simply compute all the different values choosing the minimum
$s$, repeating over all $j$. We then repeat after partitioning the data
into the 2 regions.\
*Stopping criterion*\
*

-   *Maximum tree depth*

-   *Minimum number of observations in a region*

-   *Minimum reduction in RSS from splitting*



**Definition 90**. **Cost-complexity pruning*\
Define a subtree $T_{0}$ of $T$ by collapsing any number of its internal
nodes.\
Let $\left\vert T \right\vert$ the number of terminal nodes of tree $T$\
Let $n_{m}$ number of observations in $R_{m}$\
$\hat{c}_{m}= n_{m}^{-1} \sum_{x_{i}\in R_{m}} y_{i}$ and
$Q_{m}(T) = n_{m}^{-1} \sum_{x_{i}\in R_{m}} (y_{i} - \hat{c}_{m})^{2}$\
The cost-complexity criterion is
$$C_\alpha  (T) = \sum_{m=1}^{\left\vert T \right\vert } n_{m}Q_{m}(T) + \alpha \left\vert T \right\vert$$
Idea is to find for each $\alpha$ the subtree $T_\alpha \subseteq T_0$
that minimises $C_\alpha (T)$ and then choose the subtree with the
smallest $\alpha$ that is within one standard error of the minimum.\
*



**Definition 91**. **(Weakest link pruning)*\
Start with the full tree $T_0$ and find the weakest link, the pair of
nodes that when removed gives the smallest increase in
$\sum_{m=1}^{\left\vert T \right\vert } n_{m}Q_{m}(T)$. Until we end up
with a single node tree.\
Can show that this sequence has tree $T_\alpha$ that minimises
$C_\alpha (T)$\
Estimate of $\alpha$ is given by 5 or 10 fold cross-validation.*



**Definition 92**. **(Classification trees)*\
Similar to regression trees, but instead of minimising SSQ, we use
$$\hat{p}_{m,k} = n_{m}^{-1} \sum_{x_{i}
        \in R_{m}} I (Y_{i} = k)$$ the proportion of class $k$
observations in node $m$.\
Classify the observations in node $m$ to class
$k(m) = \underset{k}{\mathop{\arg\ \max}} \hat{p}$ the majority class in
node $m$\
Can use the following alternatives for $Q_{m}(T)$*

-   *Misclassification error;
    $\frac{1}{n_{m}} \sum_{x_{i}\in R_{m}} I (y_{i} \neq k(m)) = 1 - \hat{p}_{m,k(m)}$*

-   *Gini index;
    $\sum_{k=1}^{K} \hat{p}_{m,k} (1 - \hat{p}_{m,k}) =  \sum_{k=1}^{K} \hat{p}_{m,k}(1 - \hat{p}_{m,k})$*

-   *Cross-entropy; $- \sum_{k=1}^{K} \hat{p}_{m,k} \log \hat{p}_{m,k}$*


# Model Inference and Averaging

## The Bootstrap and Maximum Likelihood Methods

### Bootstrap


**Definition 93**. **Bootstrap*\
Let $X_{1}, \ldots ,X_{n}$ be a random sample from a distribution with
unknown distribution function $F$.\
Let $\hat{\theta} = \hat{\theta}(X_{1}, \ldots ,X_{n})$ be an estimator
of statistic $\theta = \theta(F)$ a functional of $F$\
Can estimate $\theta (F)$ replacing $F$ by empirical distribution
function:*

*$$\hat{F}_{n}(x) = n^{-1} \sum_{i=1}^{n} I (X_{i} \leq x)$$

*Can simulate from $\hat{F}_{n}(x)$ as it puts mass $1/n$ at each
$X_{i}$\
Let $X_1^{(1), \ldots , X_{n}^{(1)} }$ be a random sample from
$X_1, \ldots ,X_{n}$ with replacement\
Call $\{X_{i}^{(b)}\}_{i=1}^n$ the $b$th bootstrap sample, and let their
empirical distribution function be $\hat{F}^{(b)}, b = 1 , \ldots , B$*


## Bagging


**Definition 94**. **(Bagging)*\
Suppose we fit model to training data
$Z = \{(x_1,y_1), \ldots , (x_{n}) \}$, and obtain $\hat{f}(x)$\
Can produce $B$ bootstrap samples $Z^{(b)}, b = 1, \ldots ,B$ and give
each an estimate $\hat{f}^{(b)}(x)$\
Bootstrap aggregation, or Bagging, estimate averages these predictions
over many bootstrap samples by*

*$$\hat{f}_{bag} (x) = B^{-1} \sum_{b=1}^{B} \hat{f}^{(b)}(x)$$



**Definition 95**. **(Actual Bagging)*\
Let $\hat{P}$ be distribution that puts mass of $n^{-1}$ onto each of
the $(x_{i},y_{i})$\
The 'true' bagging estimate defined by
$\mathbb{E}_{\hat{P} } \{\hat{f}^{\ast} (x)\}$ where $\hat{f}^{\ast}$ is
obtained from a set
$Z^{\ast}  = \{(x_{i}^{\ast} ,y_{i}^{\ast} )\}_{i=1}^n$ where each
$(x_{i}^{\ast} ,y_{i}^{\ast} ) \sim \hat{P}$\
Then $\hat{f}_{bag} (x)$ an estimate of the true bagging estimate
approaching as $B \to \infty$\
Bagged estimate will only differ when estimator is a non-linear or
adaptive estimator\
If linear then $\hat{f}_{bag} (x) \to \hat{f} (x)$ as $B \to \infty$*



**Proposition 96**. **(Why bagging works)*\
Assume training observations are drawn independently from distribution
$P$\
Ideal bagging estimator
$f_{ag} (x) = \mathbb{E}_{P} \hat{f}^{\ast} (x)$\
Consider $$\mathbb{E}_{P}
        \left[ 
            \left( 
                Y - \hat{f}^{\ast} (x)
            \right)^{2}
        \right] \geq  
        \mathbb{E}_{P}
        \left[ 
            \left( 
                Y - f_{ag} (x)
            \right)^{2} 
        \right]$$ Hence true population aggregate never increases MSE,
suggests bagging will often decrease MSE.*



**Definition 97**. **(Bagging Trees)*\
Bagging trees is a special case of bagging, where we use regression
trees as the base learner.\
Suppose $W_1, \ldots ,W_{B}$ a set of independent random variables with
variance $\sigma^{2}$
$$\overline{W}  = B^{-1} \sum_{b=1}^{B} W_{b}, \quad var(\overline{W} ) = \sigma^{2} /B \xrightarrow[B\to \infty ]{} 0$$
Suppose that
$\mathrm{Cov}\left[ W_{b},W_{d} \right] = \sigma^{2} \rho >0$ for
$b \neq d$ then
$$var(\overline{W} ) =  \rho \sigma^{2} + \frac{1-\rho }{B}\sigma^{2}\ \;\not\!\!\!\!\!\!\xrightarrow[B \to \infty ]{} 0$$
Correlated trees limit the effectiveness of bagging.*



**Algorithm 5**. **(Random Forests)*\
Random forests are a modification of bagging that builds a large
collection of de-correlated trees, and then averages them.\
*

1.  *For $b = 1, \ldots ,B$*

    1.  *Draw a bootstrap sample $Z^{(b)}$ of size $n$ from the training
        data*

    2.  *Grow a random-forest tree $T_{b}$ to the bootstrapped data, by
        recursively repeating the following steps for each terminal node
        of the tree, until the minimum node size $n_{min}$ is reached.*

    3.  *Select $m \leq p$ variables at random from the $p$ variables*

    4.  *Pick the best variable/split-point among the $m$*

    5.  *Split the node into two daughter nodes*

2.  *Output the ensemble of trees $\{T_{b}\}_{b=1}^B$*

*For a prediction at new point $x$*

-   *Regression:
    $\hat{f}_{rf} (x) = \frac{1}{B} \sum_{b=1}^{B} T_{b}(x)$*

-   *Classification: Let $\hat{C}_{b}(x)$ be the class prediction of the
    $b$th random-forest tree.\
    Then
    $\hat{C}_{rf} (x) = \mathrm{majority\ vote} \{\hat{C}_{b}(x)\}_{b=1}^B$*


# Boosting and Additive Trees

## Boosting Methods


**Definition 98**. **Boosting*\
We build sequence of classifiers $G_{m}(x), m = 1, \ldots ,M$ where
$G_1 (x) = G(x)$ and $G_{m}(x)$ depends on previous classifiers.\
Combining them to give $$G^{\ast} (x) = \mathop{sgn}\ 
        \left\{ 
            \sum_{m=1}^{M} \alpha_{m} G_{m}(x)
        \right\}$$ Where the $\{\alpha_{m}\}_{m=1}^M$ are computed by
the boosting algorithm.*



**Proposition 99**. **(Boosting weights)*\
Apply weights $w_1, \ldots ,w_{n}$ to each of the training observations
$(x_{i}, y_{i}) , i = 1 , \ldots ,n$\
Initialise all weights to equal $w_{i} = 1/n$\
Each successive iteration, weights modified and classifier applied to
weighted observations\
Incorrectly classified observations get their weight increased*



**Algorithm 6**.

1.  *Initialise weights $w_{i} = 1/n$ for $i = 1, \ldots ,n$*

2.  *For $m = 1, \ldots ,M$*

    1.  *Fit classifier $G_{m}(x)$ to training data using weights
        $\{w_{i}\}$*

    2.  *Compute $$err_m = 
                        \frac{
                            \sum_{i=1}^{n} w_{i} I(y_{i} \neq G_{m}(x_{i}))
                        }{
                            \sum_{i=1}^{n} w_{i}
                        }$$

    3.  *Compute
        $\alpha_{m} = \log \{(1 - er\mathrm{m} )/er\mathrm{m} \}$*

    4.  *Set
        $w_{i} \leftarrow w_{i} \cdot \exp \{\alpha_{m} I(y_{i} \neq G_{m}(x_{i}))\}$
        for $i = 1, \ldots ,n$*

3.  *Output $$G^{\ast} (x) = \mathop{sgn}\ 
                \left\{ 
                    \sum_{m=1}^{M} \alpha_{m} G_{m}(x)
                \right\}$$


# Ethics

lol
