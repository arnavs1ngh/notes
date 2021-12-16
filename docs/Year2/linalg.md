---
layout: default
title: Linear Algebra & Numerical Methods 
parent: Year 2
nav_order: 1
math: mathjax3
---

# Linear Algebra & Numerical Methods

## Successive substitution
The most basic method of solving a flash problem is by successive substitution of variables, either $K_i$ component equilibrium variables, or $x_i, y_i$ composition variables.

The basic implementation involves calculating the liquid and vapour fugacities from an initial guess of the compositions, then writing the expression for the compositions from the material balance and definition of the equilibrium constant.

### Substitution algorithm:
1.  Start with $x_i, y_i$
2.  Solve the Rachford-Rice equation
3.  Compute $\phi^V_i, \phi^L_i$
4.  Iterate with the equal fugacity constraint

$$
\begin{align*}
K_i &= \frac{\phi_i^L(x)}{\phi_i^V(y)}\\
x_{i,k+1} &= \frac{z_i}{1+\beta(K_i-1)}\\
y_{i, k+1} &= \frac{z_i}{1+\beta(K_i-1)}\\
\end{align*}
$$

