---
layout: default
title: Multi-Variable Calculus & Differential Equations
parent: Year 2
nav_order: 2
math: mathjax3
---
# Multi-variable Calcuus & Differential Equations - Concise Notes 1
{: .no_toc }
## MATH50004
{: .no_toc}
**Term 1 Content**

<head>
  <style>
ol.n {list-style-type: none;}
  </style>
</head>
  

<a href="https://arnavs1ngh.github.io/notes/docs/Year2/main/#analysis-2---math50001" style="color:#FF0000;">PDF MVC  - Concise Notes - Term 1</a>

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

*Content from MATH40004 assumed to be known.*

# Vector Calculus

## Prelim

**Definition 1.1.1 -** **Einstein Summation Convention**
<center>
$$a_{i}x_{i} = \sum_{i=1}^{3}x_{i}$$ 
</center>

**Definition 1.1.2 -** **The Kronecker delta**

<center>
$$\delta_{ij} = 
\begin{cases} 
      1, & i=j \\
      0, & i \neq j
   \end{cases}$$
</center>  

**Definition 1.1.3 -** **The Permutation Symbol**

<center>
$$\epsilon_{ijk} = 
\begin{cases} 
      0, & \text{ if any 2 elements $i,j,k$ equal} \\
      1, & \text{if $i, j, k$ a cyclic permutation of $1, 2, 3$} \\\
      -1, & \text{if $i, j, k$ an acyclic permutation $1, 3, 2$}
   \end{cases}$$ 
</center> 

**Formula -**  **Relation between Kroenecker Delta and Permutation Symbol**
<center>
$$\epsilon_{ijk} \epsilon_{klm} = \delta_{jl} \delta_{km} - \delta_{jm} \delta_{kl}$$
$$\epsilon_{ijk} \epsilon_{ilm} = \delta_{jl} \delta_{km} - \delta_{jm} \delta{kl}$$\
  </center>
  
**Definition 1.1.4 -** **Vector Products**

**Here are some identities:**

-   $\textbf{a} \cdot \textbf{b} = a_{i}b_{i}$

-   $
    [ \mathbf{a} \times \mathbf{b} ]_{i} = \epsilon_{ijk} a_{j} b_{k}
    $

-   $
    \textbf{a} \times \textbf{b} = 
    \begin{vmatrix}
      \textbf{i} & \textbf{j} & \textbf{k}\\
      a_1 & a_2 & a_3 \\
      b_1 & b_2 & b_3
    \end{vmatrix}
    \implies [a \times b]_{i} = epsilon_{ijk} a_j b_k
    $

-   $\textbf{a} \cdot (\textbf{b} \times \textbf{c}) = (\textbf{a} \times \textbf{b}) \cdot \textbf{c} = \epsilon_{ijk} a_i b_j c_k$

-   $\textbf{a} \times (\textbf{b} \times \textbf{c}) = (\textbf{a} \cdot \textbf{c}) \textbf{b} - (\textbf{a} \cdot \textbf{b}) \textbf{c} \Rightarrow [\textbf{a} \times (\textbf{b} \times \textbf{c})]_i = (\textbf{a} \cdot \textbf{c}) b_i - (\textbf{a} \cdot \textbf{b}) c_i$

## Gradient, Div, and Curl

**Definition 1.2 -** **Gradient, Directional Derivatives**

$\phi =$ constant, defines a surface in 3D, varying the constant yields a family of surfaces.\
<center>
$$\hat{\textbf{n}}\frac{\partial \phi}{\partial n} = \nabla = (\frac{\delta}{\delta x}, \frac{\delta}{\delta y}, \frac{\delta}{\delta z}) \Rightarrow \nabla \phi = \frac{\delta \phi}{ \delta x} + \frac{\delta \phi}{ \delta y} + \frac{\delta \phi}{ \delta z}$$
</center>

s = $\frac{\delta \phi}{\delta s} = \nabla \phi \cdot \textbf{\^{s}}$

**$\nabla \phi = \textbf{\^{r}} \frac{\delta \phi}{\delta r} + \frac{\hat{\theta}}{r} \frac{\delta \phi}{\delta \theta} + \textbf{k} \frac{\delta \phi}{\delta z}$**


**Definition 1.2.3 -** [**Tangent Plane to $\phi(P)$**]
<center>
$$(\mathbf{r}-\mathbf{r}_{p})\cdot(\nabla \phi)_{P} = 0$$
$$\left(\frac{\delta \phi}{\delta x}\right)_P (x-x_P) + \left(\frac{\delta \phi}{\delta y}\right)_P (y-y_P) + \left(\frac{\delta \phi}{\delta z}\right)_P (z-z_P) = 0$$
</center>

## Divergence & Curl

**Definition 1.3.1 -** **Divergence and Curl**

**A** a vector function of position
<center>
$$\textcolor{ForestGreen}{\textbf{Div  \textbf{A}}} = \nabla \cdot \textbf{A} = \frac{\delta A_1}{\delta x} + \frac{\delta A_2}{\delta y} + \frac{\delta A_3}{\delta z} \text{ where }A = A_1 \textbf{\^{i}} + A_2 \textbf{\^{j}} + A_3 \textbf{\^{k}}$$

$$\textcolor{ForestGreen}{\textbf{Curl \textbf{A}}} = \nabla \times \textbf{A} = \textbf{\^{i}} \left(\frac{\delta A_3}{\delta y} - \frac{\delta A_2}{\delta z} \right) - \textbf{\^{j}} \left(\frac{\delta A_3}{\delta x} - \frac{\delta A_1}{\delta z} \right) + \textbf{\^{k}} \left(\frac{\delta A_2}{\delta x} - \frac{\delta A_1}{\delta y} \right)$$
</center>

**Definition -** **Laplacian Operator**
<center>
$$\nabla^2 \phi = \text{div}(\nabla \phi) = \frac{\delta^2 \phi}{\delta x^2} + \frac{\delta^2 \phi}{\delta y^2} + \frac{\delta^2 \phi}{\delta z^2}$$
</center>

## Operations with Grad operator

**Resulting Equalities**

1.  $\nabla(\phi_1+\phi_2) = \nabla \phi_1 + \nabla \phi_2$

2.  $\text{div }(\textbf{A} + \textbf{B}) = \text{div }\textbf{A} + \text{div }\textbf{B}$

3.  $\text{curl }(\textbf{A} + \textbf{B}) = \text{curl }\textbf{A} + \text{curl }\textbf{B}$

4.  $\nabla (\phi \psi) = \phi \nabla \psi + \psi \nabla \phi$

5.  $\text{div}(\phi \textbf{A}) = \phi \text{ div }\textbf{A} + \nabla \phi \cdot \textbf{A}$

6.  $\text{curl}(\phi \textbf{A}) = \phi \text{ curl }\textbf{A} + \nabla \phi \times \textbf{A}$

7.  $\text{div}(\textbf{A} \times \textbf{B}) = \textbf{B} \cdot \text{curl }\textbf{A} - \textbf{A} \cdot \text{curl } \textbf{B}$

8.  $\text{curl}(\textbf{A} \times \textbf{B}) = (\textbf{B} \cdot \nabla)\textbf{ A} - \textbf{B}\text{ div }\textbf{A} -(\textbf{A} \cdot \nabla)\textbf{B} + \textbf{A} \text{ div }\textbf{B}$

9.  $\nabla(\textbf{A} \cdot \textbf{B}) = (\textbf{B} \cdot \nabla)\textbf{A}+(\textbf{A} \cdot \nabla)\textbf{B} + \textbf{B} \times \text{curl }\textbf{A} + \textbf{A} \times \text{curl } \textbf{B}$

10. $\text{curl }(\nabla \phi) =  0$

11. $\text{curl }(\text{curl } \textbf{A}) =  \nabla(\text{div } \textbf{A})-\nabla^2 \textbf{A}$

12. $\text{div }(\text{curl } \textbf{A}) =  0$

# Integration

**Definition 1.4.6 - ** **Scalar and Vector Fields**
If at each point of region $V$, scalar function $\phi$ defined -
<center>
**$\phi$ a scalar field over $V$**
</center>

Similarly if vector function $A$ defined $\forall v \in V$, **$A$ a vector field.**

If curl $A = 0$, $A$ is an **irrotational vector field**. If div $A = 0$, $A$ a **solenoidal vector field**

## Path Integrals

**Definition 1.5.1 -** **Definition of a Path Integral**
<center>
$$\lim_{n\rightarrow \infty} \sum_{n=1}^{N} f_{n} \delta s_n = \int_{\gamma}f ds \Rightarrow \int_{\gamma}\textbf{F} \cdot d\textbf{r} \int_{\gamma}\textbf{F}\cdot \textbf{\^{t}} ds $$ where $\^{t}$  is the normalized vector tangent to the path
</center>
  
  
**Definition 1.5.3 -** **Conservative forces**

If [**$F = \nabla \phi$**] for a **differentiable scalar function $\phi$**, **$F$ is said to be a conservative field**, which has the following properties:
<center>
$$\int_{\gamma} \textbf{F} \cdot d\textbf{r} = \phi(B)-\phi(A)$$ 
  </center>
Result independent of path joining **A** and **B**, in particular for $\gamma$ a closed curve ($B \equiv A$) We have:
<center>
$$\oint_{\gamma}\textbf{F}\cdot d\textbf{r} = 0$$ 
</center>
Call this a **circulation of F** around $\gamma$

If a vector field **F** s.t **$\oint_{\gamma}F\cdot dr = 0$**, for any closed curve $\gamma$ say **F a conservative field**, if $\textbf{F} = \nabla\phi \implies \textbf{F}$ conservative.\

If **F** conservative $\implies$ can always find differentiable scalar function $\phi$ s.t **F**$=\nabla\phi$, call $\phi$ the **potential of field F**

**Definition 1.5.4 -**  **Calculation of Path Integrals**

$\textbf{F}=\textbf{F}(x, y, z)$ $\gamma$ $(x(t), y(t), z(t)),$

<center>
$$\textbf{r} = {x(t)\textbf{\^{i}}+y(t)\textbf{\^{j}}+z(t)\textbf{\^{k}}} \Rightarrow d\textbf{r} = \frac{dx}{dt}\textbf{\^{i}}+\frac{dy}{dt}\textbf{\^{j}}+\frac{dz}{dt}\textbf{\^{k}}$$

$$\implies
\int_{\gamma}\textbf{F}\cdot d\textbf{r} = \int_{t_0}^{t_1}\left(\textbf{F}_{1}\frac{dx}{dt}+\textbf{F}_{2}\frac{dy}{dt}+\textbf{F}_{3}\frac{dz}{dt}\right) dt$$
</center>

## Surface Integrals

**Definition 1.6.1 -** **Surface Integral**
Consider a surface $S$,where we find the surface integral of $f = f(P)$ over $S$.\

Dividing $S$ into small elements of area $\delta S_{i}$, with $f_{i}$ the values of $f$ at typical points $P_{i}$ of $\delta S_{i}$

The **surface integral of $f$ over $S$** is
<center>
$$\int_{S}f dS = \lim_{\substack{N \to \infty \\ max(\delta S_{n}) \to 0}}\sum_{n=1}^{N}f_{n}\delta S_{n}$$
</center>
  
$f$ may be a vector or a scalar.

### Types of Surfaces

![image](ClosedSurface.jpeg){width="\\linewidth"}[\[fig:closed\]]{#fig:closed
label="fig:closed"}

![image](OpenSurface.jpeg){width="\\linewidth"}[\[fig:open\]]{#fig:open
label="fig:open"}

![image](Convex.jpeg){width="\\linewidth"}[\[fig:convex\]]{#fig:convex
label="fig:convex"}

![image](notConvex.jpeg){width="\\linewidth"}[\[fig:notconvex\]]{#fig:notconvex
label="fig:notconvex"}

**Definitions**

1.  **Closed Surface** - Divides $3D$ space into $2$ non-connected regions; interior and exterior.

2.  **Open Surface** - Does not divide $3D$ space into 2 non-connected regions - has a rim which can be represented by closed curve.\
    Can think of closed surfaces as sum of 2 open surfaces.

3.  **Convex Surface** - A surface which
    is crossed by a straight line at most twice

### Evaluating surface integrals for plane surfaces in x-y plane

![image](surface.png){width="30%"}

$dS$ infinitesimal area $\implies$ think of as approx. plane.\
**Vector areal element $dS$** is the vector $\hat{\mathbf{n}}dS$ for
$\hat{\mathbf{n}}$ the unit normal vector to $dS$.\
For a plane lying in $z = 0$, we can say $dS = dxdy$\


For a rectangle, $x = a,b$ and $y = c,d$ circumscribing convex $S$. We let
<center>
$$y = 
\begin{cases}
      F_{1}(x) & \text{upper half ADB}\\
      F_{2}(x) & \text{lower half ACB}
\end{cases}$$
  

Area of  $\mathbf{S}= \int_{S}dS = \int_{x=a}^{x=b}\int_{y=F_{2}(x)}^{y=F_{1}(x)}dydx = \int_{a}^{b}[F_{1}(x) -F_{2}(x)]dx $

</center>
For $f(x,y)$ a function of position
<center>
$$\int_{S}fdS = \int_{x=a}^{x=b}\int_{y = F_{2}(x)}^{y=F_{1}(x)}f(x,y)dydx$$
</center>

Equivalently;
<center>
$$x =
\begin{cases}
      G_{1}(x) & \text{right half CBD}\\
      G_{2}(x) & \text{left half CAD}
\end{cases}$$
  
$$\textcolor{red}{\text{\textbf{Area of  }} \mathbf{S} = \int_{S}dS = \int_{c}^{d} G_{1}(y) - G_{2}(y)dy}$$
  
$$\int_{S}fdS =  \int_{y=c}^{y=d}\int_{x = G_{2}(x)}^{x=G_{1}(x)}f(x,y)dxdy$$

</center>

### Projection of an area onto a plane

![Right; Projection of curved surface $S$ onto $x-y$ plane](projection.png){width="55%"}

<center>
$$dS = \frac{d\Sigma}{|\hat{\mathbf{n}}\cdot\hat{\mathbf{k}}|}$$
</center>

### The Projection Theorem

$P$ a point on surface $S$, which at no point is orthogonal to $\mathbf{k}$
<center>
$$\int_{S}f(P)dS = \int_{\Sigma}f(P)\frac{dx\ dy}{|\hat{\mathbf{n}}\cdot\hat{\mathbf{k}}|}$$
</center>
  
For $\Sigma$ a projection of $S$ onto $z= 0$, with $\hat{\mathbf{n}}$ normal to $S$\
For $S$ given by $z = \phi(x,y)$
<center>
$$\int_{S}f(x,y,z)dS = \int_{\Sigma_{z}}f(x,y,\phi(x,y))\frac{dx\ dy}{|\hat{\mathbf{n}}\cdot\hat{\mathbf{k}}|}$$
</center>

Projecting onto $x =0$ or $y = 0$\
<center>
$$\int_{S}f(P)dS = \int_{\Sigma_{x}}f(x,y,\phi(x,y))\frac{dy\ dz}{|\hat{\mathbf{n}}\cdot\hat{\mathbf{i}}|} = \int_{\Sigma_{y}}f(x,y,\phi(x,y))\frac{dx\ dz}{|\hat{\mathbf{n}}\cdot\hat{\mathbf{j}}|}$$
</center>

$\Sigma_{x}$, projection onto $x=0$, $\Sigma_{y}$, projection onto $y=0$

## Volume Integrals

**Definition 1.7.1 -** **Volume Integral**

Considering a volume $\tau$, split into $N$ subregions, $\{\delta \tau_{i}\}$, with $\{P_{i}\}$ typical points of $\{\delta \tau_{i}\}$.

<center>
$$\int_{\tau}f d\tau = \lim_{\substack{N \to \infty \\ max(\delta \tau_{i}) \to 0}}\sum_{i=1}^{N}f(P_{i})\delta \tau_{i}$$
</center>

In Cartesian coordinates, the volume element $d \tau = dxdydz$

## Results relating line,surface and volume integrals

### Green's Theorem in the plane


$R$ a closed plane region bounded by a simple plane closed convex curve
in $x-y$ plane.\
$L,M$ continuous functions of $x,y$ with continuous derivatives
throughout $R$. Then:
<center>
$$\oint_{C}(L\ dx + M\ dy) = \int_{R}(\frac{\partial M}{\partial x} - \frac{\partial L}{\partial y})dxdy,$$
</center>
For $C$ the boundary of $R$ described in the counter-clockwise sense.

### Vector forms of Green's Theorem

*(i) $2D$ Stokes Theorem*\
Let $F = L\mathbf{i} + M\mathbf{j}$ and
$d\mathbf{r} = dx\mathbf{i} + dy\mathbf{j}$. Then

<center>
$$\text{curl }\mathbf{F} = \left(\frac{\partial M}{\partial x} - \frac{\partial L}{\partial y}\right)\mathbf{k}$$
</center>
  
Over region $R$ write $dxdy = dS$. 
<center>
$$\label{eq1}
\begin{split}
\oint_{C}F \cdot dr & = \int_{R}k\cdot \text{curl } F dS\\
& = \int_{R}\text{curl }F \cdot d\mathbf{S}, \qquad d\mathbf{S} = \hat{\mathbf{k}}dS
\end{split}$$
</center>

*(ii) Divergence Theorem in $2D$*\
Let $\mathbf{F} = M\mathbf{i} - L\mathbf{j}$. Then
<center>
$$\text{div }\mathbf{F} = \frac{\partial M}{\partial x} - \frac{\partial L}{\partial y}$$
</center>

So we can rewrite Green's Theorem as
<center>
$$\int_{R}\text{div }\mathbf{F} dxdy  = \oint_{C}F\cdot\hat{\mathbf{n}}ds$$
</center>

Green's Theorem holds for more complicated geometries too, if C not convex we can see it as the composition of 2 or more simple convex closed curves.\
Joining $A$, $A'$ form $C_{1}, C_{2}$ enclosing $R_{1},R_{2}$ s.t
$R_{1} + R_{2} =R$

![A non-convex boundary](boundary.png){width="70%"}

<center>
$$\oint_{C}\mathbf{F}\cdot dr = \oint_{C_{1}}\mathbf{F}\cdot d\mathbf{r} + \oint_{C_{2}}\mathbf{F}\cdot d\mathbf{r} = \int_{R} \text{curl }\mathbf{F}\cdot d\mathbf{S}$$
  

$$\begin{split}
        \oint_{C_{1}} & = \int_{AXA'} + \int_{A'}^{A}\\
        \oint_{C_{2}} & = \int_{A'YA} + \int_{A}^{A'}\\
    \end{split}$$
</center>

### Green's Theorem in multiply-connected regions

![Right; Green's Theorem in multiply-connected
regions](connected.png){width="50%"}


$R$ **simply-connected** if any closed curve in $R$ can be shrunk to a point without leaving $R$.

For $2D$ any region with a hole in it; **not simply connected**, we say it is **multiply-connected**

**Green's theorem still holds in multiply-connected regions**.

$C$ interpreted as the entire inner and outer boundary.

For doubly-connected region, describe outer $C_{0}$ anti-clockwise, $C_{1}$ clockwise, and join them via $A$ on $C_{0}$ and $B$ on $C_{1}$

$R$ now a simply connected region bounded by $(C_{0} + AB + C_{1} + BA)$
<center>
$$\int_{R}\text{curl }\mathbf{F}\cdot d\mathbf{S} = \left(\oint_{C_{0}} + \int_{A}^{B} + \oint_{C_{0}} + \int_{B}^{A}\right)(\mathbf{F}\cdot d\mathbf{r})$$

$$\int_{R}\text{curl }\mathbf{F}\cdot d\mathbf{S} = \left(\oint_{C_{0}} + \oint_{C_{1}} \right)(\mathbf{F}\cdot d\mathbf{r}) = \left( \oint_{C}\mathbf{F}\cdot d\mathbf{r} \right)$$
  
</center>

Where $C = C_{0} + C_{1}$

### Flux

If $S$ is a surface then the flux of $A$ across $S$ is defined as
$$\int_{S}\mathbf{A\cdot \hat{n}}dS$$ If $S$ a closed surface then by
convention draw unit normal $\mathbf{\hat{n}}$ **out** of $S$.

### The divergence theorem

If $\tau$ the volume enclosed by a closed surface $S$ with unit outward normal $\mathbf{\hat{n}}$ and $\mathbf{A}$ is a vector field with continuous derivatives throughout $\tau$, then:
<center>
$$\int_{S}\mathbf{A\cdot \hat{n}}dS = \int_{\tau}div \mathbf{A}d\tau$$
</center>

### The Divergence theorem in more complicated geometries

![The divergence theorem for a non-convex
surface](fig17DivThm.png){width="30%"}


1.  **Non-convex surfaces** *non-convex surface $S$ can be divided by
    surfaces(s) $\sigma$ into 2 (or more) parts $S_{1}$ and $S_{2}$
    which together with $\sigma$ form convex surfaces
    $S_{1} + \sigma, S_{2} + \sigma$*/\
    Applying divergence theorem to the convex parts, upon addition
    yields the same result as before.

2.  **A region with internal boundaries**

    1.  *Simply-connected regions* - e.g space between concentric
        spheres.

        ![Simply-connected regions](fig18-1.png){width="30%"}


        Given interior surface $S_{i}$ and outer surface $S_{o}$. A
        plane $\Pi$ cutting both $S_{o},S_{i}$, divides $S_{o},S_{i}$
        into open $S_{o}^{(1)},S_{o}^{(2)}$ and
        $S_{i}^{(1)},S_{i}^{(2)}$ respectively.\
        Apply divergence theorem to $\tau_{1},\tau_{2}$ bounded by
        closed $S_{o}^{(1)} + S_{i}^{(1)} + \Pi$ and
        $S_{o}^{(2)} + S_{i}^{(2)} + \Pi$. Upon addition contribution
        from $\Pi$ cancels.
        $$\int_{S_{o}+S_{i}}\mathbf{A\cdot \hat{n}}dS = \int_{S}\mathbf{A\cdot \hat{n}}dS = \int_{\tau_{1}}div \mathbf{A}d\tau + \int_{\tau_{2}}div \mathbf{A}d\tau = \int_{\tau}div \mathbf{A}d\tau$$

    2.  *Multiply-connected regions*\

        ![Multiply-connected regions](fig18 - 2.png){width="30%"}

        \

        e.g. region between 2 cyclinders.\
        Given interior surface $S_{i}$ and outer surface $S_{o}$, linked
        by plane $\Pi$.\
        Consider the closed surface, enclosing simply connected region
        $\tau$

        <center>
        $S_{i} +$ side 1 of $\Pi+ S_{o} +$ side 2 of $\Pi$
        </center>

        Applying divergence theorem to $\tau$. Once again gives
        $$\int_{S_{0}+S_{i}}\mathbf{A\cdot\hat{n}}dS = \int_{\tau}div\mathbf{A}d\tau$$

### Green's identity in 3D

For $\phi$ and $\psi$ 2 scalar fields with continuous derivatives. We consider $\mathbf{A} = \phi \nabla \psi$, for which we have
<center>
$$\begin{aligned}
        div\mathbf{A} &= \phi\nabla^{2}\psi + (\underline{\nabla}\phi)\cdot(\underline{\nabla}\psi)\\
        \mathbf{\hat{n}\cdot A} &= \phi(\underline{\nabla}\psi)\cdot\hat{\mathbf{n}} = \phi\frac{\partial \psi}{\partial n}
    \end{aligned}$$
</center>

**Green's first identity**

<center>
$$\int_{S}\left \{ \phi\frac{\partial \psi}{\partial n} \right \} dS = \int_{\tau}\phi\nabla^{2}\psi + (\underline{\nabla}\phi)\cdot(\underline{\nabla}\psi)d\tau$$
</center>

**Green's Second identity**

<center>
$$\int_{S}\left \{ \phi\frac{\partial \psi}{\partial n} - \psi\frac{\partial \phi}{\partial n} \right \} dS = \int_{\tau} \phi \nabla^{2}\psi - \psi\nabla^{2}\phi d\tau$$
</center>

### Green's identities in 2D

Divergence theorem in 2D: $\int_{F}div \mathbf{F}dxdy = \oint_{C}\mathbf{F\cdot\hat{n}}ds$

Giving the following Green's identities:
<center>
$$\oint_{C}\phi\frac{\partial \psi}{\partial n}ds = \int_{R}[\phi \nabla^{2}\psi + (\nabla\psi)\cdot(\nabla\phi)dxdy$$
</center>
and
<center>
$$\oint_{C}\left [\phi\frac{\partial \psi}{\partial n} - \psi\frac{\partial \phi}{\partial n} \right ]ds = \int_{R}\left [ \phi \nabla^{2}\psi - \psi\nabla^{2}\phi \right ] dxdy$$
</center>

**$\int_{R}\phi\nabla^{2}\psi\ dxdy = \oint_{C}\phi \frac{\partial \psi}{\partial n}ds - \int_{R}(\nabla\psi)\cdot(\nabla\phi)dxdy$** - **Looks like Integration by parts**

### Gauss' Flux Theorem

Let $S$ a closed surface with outward unit normal $\mathbf{\hat{n}}$ and let $O$ the origin of the coordinate system.

$\mathbf{A} = \frac{\mathbf{r}}{r^{3}}$ Then:

<center>
$$\int_{S}\frac{\mathbf{\hat{n}}\cdot\mathbf{r}}{r^{3}} =
        \begin{cases}
        0, \text{ if $O$ is exterior to $S$}\\
        $4\pi$, \text{ if $O$ interior to $S$}
        \end{cases}$$
</center>


### Stokes Theorem

![Diagram for proof of Stokes' Theorem](fig20.jpeg){width="30%"}

Suppose $S$ is **open** surface with simple closed curve $\gamma$ forming its boundary.

$A$ a vector field with continuous partial derivatives, Then:

<center>
$$\oint_{\gamma}\mathbf{A}\cdot d\mathbf{r} = \int_{S}curl\mathbf{A\cdot\hat{n}}dS$$
</center>

This holds for **any** open surface with $\gamma$ as a boundary.

**Theorem**\
For $\mathbf{A}$ continuously differentiable and simply connected
region:
<center>
$$\underbrace{\oint_{\gamma}\mathbf{A}\cdot d\mathbf{r} = 0}_{\mathbf{A} \text{ conservative}} \iff curl\mathbf{A} = 0, \text{ throughout region for which $\gamma$ is drawn}$$
</center>

## Curvilinear Coordinates

### Intro + Definition

Consider generally cartesian coordinates: $(x_1,x_2,x_3)$ with each expressible as single-valued differentiable functions of the new coorinates $(u_1,u_2,u_3)$ $$x_i = x_i(u_1,u_2,u_3)
<center>
$$
$$\frac{\partial x_i}{\partial x_j} = \delta_{ij} = \frac{\partial x_i}{\partial u_1}\frac{\partial u_1}{\partial x_j} + \frac{\partial x_i}{\partial u_2}\frac{\partial u_2}{\partial x_j}+ \frac{\partial x_i}{\partial u_3}\frac{\partial u_3}{\partial x_j}$$
With the following matrix equation $$\left(\begin{array}{lll}
            \partial x_{1} / \partial u_{1} & \partial x_{1} / \partial u_{2} & \partial x_{1} / \partial u_{3} \\
            \partial x_{2} / \partial u_{1} & \partial x_{2} / \partial u_{2} & \partial x_{2} / \partial u_{3} \\
            \partial x_{3} / \partial u_{1} & \partial x_{3} / \partial u_{2} & \partial x_{3} / \partial u_{3}
            \end{array}\right)\left(\begin{array}{lll}
            \partial u_{1} / \partial x_{1} & \partial u_{1} / \partial x_{2} & \partial u_{1} / \partial x_{3} \\
            \partial u_{2} / \partial x_{1} & \partial u_{2} / \partial x_{2} & \partial u_{2} / \partial x_{3} \\
            \partial u_{3} / \partial x_{1} & \partial u_{3} / \partial x_{2} & \partial u_{3} / \partial x_{3}
        \end{array}\right)=I$$
</center>

Or more succinctly
<center>
$$J(x_u)\cdot J(u_x) = I$$
</center>
We say $J(x_u)$ the **Jacobian matrix** for the $(x_1,x_2,x_3)$ system.\

<center>
$det\left ( J(x_u) \right)\neq 0\ \implies J(u_x)$ exists
  
$det(J(x_u)) = \frac{1}{det(J(u_x))}$
</center>

We say $(u_1,u_2,u_3)$ define a curvilinear coordinate system.\
With each $u_i =$ constant, defining a family of surfaces, with a member
of each family passing through each $P(x,y,z)$

Let $\mathbf{(\hat{a}_{1},\hat{a}_{2},\hat{a}_{3})}$ unit vectors at $P$ in
the direction normal to $u_i = u_i(P)$, s.t $u_i$ increasing in the
direction $\mathbf{\hat{a}_{i}}}$

<center>
$$\mathbf{\hat{a}_i} = \mathbf{\frac{\nabla u_i}{\lvert \nabla u_i \rvert}}$$
</center>

if we have that $\mathbf{(\hat{a_1},\hat{a_2},\hat{a_3})}$ mutually orthogonal $\implies$ **orthogonal curvilinear coordinate system.**
<center>
$$\frac{\partial \mathbf{r}}{\partial u_i} = \mathbf{\hat{e_{i}}}h_{i}$$
</center>

For which we define $h_{i} = \lvert \partial \mathbf{r}/ \partial u_{i} \rvert$. We call these the **length scales**

### Path element

$\mathbf{r} = \mathbf{r}(u_1,u_2,u_3)$ **path element** $d\mathbf{r}$
given by
<center>
$$\begin{aligned}
        d\mathbf{r} &= \frac{\partial \mathbf{r}}{\partial u_1}du_1 + \frac{\partial \mathbf{r}}{\partial u_2}du_2 + \frac{\partial \mathbf{r}}{\partial u_3}du_3\\
        &= h_{1}du_{1}\hat{e_{1}} + h_{2}du_{2}\hat{e_{2}}+ h_{3}du_{3}\hat{e_{3}}
    \end{aligned}$$
</center>

For an orthongal system
<center>
$$(ds)^{2} = (d\mathbf{r})\cdot(d\mathbf{r}) = h_{1}(du_{1})^{2} + h_{2}(du_{2})^{2} +h_{3}(du_{3})^{2}$$
  
$$\hat{e}_{i} = \hat{a}_{i} = \mathbf{\frac{\nabla u_i}{\lvert \nabla u_i \rvert}}$$
</center>


### Volume Element

<center>
$$\begin{aligned}
        d\tau &= (h_{1}du_{1})(h_{2}du_{2})(h_{3}du_{3})\\
        &= h_1h_2h_3du_1du_2du_3
    \end{aligned}$$
</center>

### Surface element

For $u_1$ constant. $$dS = h_2h_3du_2du_3$$ similarly for $u_2,u_3$

### Properties of various orthogonal coordinates

1.  **Cartesisan coordinates** $(x,y,z)$

    <center>
    $$  
    \begin{aligned}
    d&= dxdydz & d &= dx + dy + dz\
    (ds)\^2 &= (d\mathbf{r})\cdot(d\mathbf{r}) = (dx)\^2 + (dy)\^2 + (dz)\^2
    \end{aligned}
    $$
    </center>

    We have $h_{1} = h_{2} = h_{3}$

2.  **Cylindrical polar coordinates** $(r,\phi,z)$\
    Related to cartesian by
    $$x = r\cos \theta \quad y = r\sin \phi \quad z = z$$

    <center>
    ::: aligned
    &= () + () + () = () + ()\
    &= () + () + () = -(r) + (r)\
    &=


    ::: aligned
    ()() &= 0\
    ()() &= 0\
    ()() &= 0
    :::

    ::: aligned
    h\_1 &= = 1\
    h\_2 &= = r\
    h\_3 &= = 1
    :::
    </center>

    Yielding length and volume elements:

    <center>
    ::: aligned
    (ds)\^2 &= (dr)\^2+r\^2(d)\^2+(dz)\^2
    :::

    ::: aligned
    d= rdrddz
    :::
    </center>

3.  **Spherical polar coordinates** $(r,\theta,\phi)$\
    Related to cartesian by:
    $$x = r\sin\theta\cos\phi \quad y = r\sin\theta\sin\phi \quad z = r\cos\theta$$

    ::: center
    ::: aligned
    &= () + () + ()\
    &= (r) + (r) + (-r)\
    &= (-r) + (r) + (0)
    :::

    ::: aligned
    ()() &= 0\
    ()() &= 0\
    ()() &= 0
    :::

    ::: aligned
    h\_1 &= = 1\
    h\_2 &= = r\
    h\_3 &= = r
    :::
    :::

    Volume element:\
    $$d\tau = r^{2}\sin\theta drd\theta d\phi$$

### Gradient in orthogonal curvilinear coordinates

Let $\nabla \Phi = \lambda_{1}\mathbf{\hat{e}_{1}} + \lambda_{2}\mathbf{\hat{e}_{2}} + \lambda_{3}\mathbf{\hat{e}_{3}}$.

In a general coordinate system for $\lambda_{i}$s to be found.

<center>
$$d\mathbf{r} = h_{1}du_{1}\hat{e}_{1} +  h_{2}du_{2}\hat{e}_{2} + h_{3}du_{3}\hat{e}_{3}$$
  
$$\begin{aligned}
            d\mathbf{\Phi} &= (\frac{\partial \phi}{\partial u_{1}})du_{1} + (\frac{\partial \phi}{\partial u_{2}})du_{2}+ (\frac{\partial \phi}{\partial u_{3}})du_{3}\\
            &= (\frac{\partial \phi}{\partial x})dx + (\frac{\partial \phi}{\partial y})dy+ (\frac{\partial \phi}{\partial z})dz\\
            &= \fbox{(\nabla\Phi)\cdot d\mathbf{r} = \lambda_{1}h_{1}du_{1} + \lambda_{2}h_{2}du_{2} + \lambda_{3}h_{3}du_{3}}
        \end{aligned}$$
</center>

<center>
$$h_{i}\lambda_{i} = \frac{\partial \Phi}{\partial u_{i}}$$
  
$$\implies \nabla \Phi = \frac{\hat{\mathbf{e}}_{1}}{h_{1}}\frac{\partial \Phi}{\partial u_{1}} + \frac{\hat{\mathbf{e}}_{2}}{h_{2}}\frac{\partial \Phi}{\partial u_{2}} + \frac{\hat{\mathbf{e}}_{3}}{h_{3}}\frac{\partial \Phi}{\partial u_{3}}$$
  
</center>

1.  **Cylindrical polars** $(r,\phi,z)$\
    We have: $\begin{aligned}
                    h_{1} &= 1\\
                    h_{2} &= r\\
                    h_{3} &= 1
                    \end{aligned}$
                    $\implies$ 
                    $\begin{aligned} \nabla = \hat{r}\frac{\partial}{\partial r} + \frac{\hat{\phi}}{r}\frac{\partial}{\partial \phi} + \hat{z}\frac{\partial}{\partial z} \end{aligned}$

2.  **Spherical polars** $(r,\theta,\phi)$\
    We have:
    <center>
    \begin{aligned}
    h\_1 &= 1\
    h\_2 &= r\
    h\_3 &= r
    \end{aligned}
    </center>
    
    $\implies$

    ::: aligned
    = + +
    :::

### Expressions for unit vectors

<center>
$$\hat{\mathbf{e}}_{i} =h_{i}\nabla u_{i}$$
</center>

Alternatively, unit vectors orthogonal $\implies$ if we know 2 already then
<center>
$$\hat{\mathbf{e}}_{1} = (\hat{\mathbf{e}}_{2}\times\hat{\mathbf{e}}_{3}) = h_{2}h_{3}(\nabla u_{2} \times \nabla u_{3})$$
</center>

### Divergence in orthogonal curvilinear coordinates

Suppose we have vector field
<center>
$$\mathbf{A} = A_{1}\hat{\mathbf{e}}_{1} + A_{2}\hat{\mathbf{e}}_{2} + A_{3}\hat{\mathbf{e}}_{3}$$
  
$$\implies \nabla\cdot\mathbf{A} = \frac{1}{h_{1}h_{2}h_{3}}\left \{ \frac{\partial}{\partial u_{1}}(A_1h_2h_3) + \frac{\partial}{\partial u_{2}}(A_2h_3h_1) + \frac{\partial}{\partial u_{3}}(A_3h_1h_2) \right \}$$
  
</center>

So we have divergence in other coordinate systems as follows:

### Curl in orthogonal curvilinear coordinates

<center>
$$curl\mathbf{A} = \frac{1}{h_1h_2h_3}
        \begin{vmatrix}
        h_1\hat{e}_{1} & h_2\hat{e}_{2} & h_3\hat{e}_{3}\\
        \frac{\partial}{\partial u_{1}} & \frac{\partial}{\partial u_{2}} & \frac{\partial}{\partial u_{3}}\\
        h_{1}A_{1} & h_{2}A_{2} & h_{3}A_{3}
        \end{vmatrix}$$
</center>

1.  **Cylindrical polars**\
    <center>
    $$curl \mathbf{A} = \frac{1}{r}
                \begin{vmatrix}
                \mathbf{\hat{r}} & r\hat{\phi} & \mathbf{\hat{k}}\\
                \partial/\partial r & \partial/\partial \phi & \partial/\partial z\\
                A_1 & A2 & A_3
                \end{vmatrix}$$
    </center>

2.  **Spherical polars**\
    <center>
    $$curl \mathbf{A} = \frac{1}{r^{2}\sin\theta}
                \begin{vmatrix}
                \mathbf{\hat{r}} & r\hat{\phi} &  r\sin\theta\hat{\phi} \\
                \partial/\partial r & \partial/\partial \phi & \partial/\partial z\\
                A_1 & rA2 & r\sin\theta A_3
                \end{vmatrix}$$
    </center>

### The Laplacian in orthogonal curvilinear coordinates

From the above grad and div;
<center>
$$\nabla^{2}\Phi = \nabla \cdot (\nabla\Phi)$$
  
$$= \frac{1}{h_{1}h_2h_3}\left \{ \frac{\partial}{\partial u_1}\left (\frac{h_2h_3}{h_1}\frac{\partial \Phi}{\partial u_1}\right ) + \frac{\partial}{\partial u_2}\left (\frac{h_1h_3}{h_2}\frac{\partial \Phi}{\partial u_2}\right ) + \frac{\partial}{\partial u_3}\left (\frac{h_1h_2}{h_3}\frac{\partial \Phi}{\partial u_3}\right ) \right \}$$
  
</center>

1.  **Cylindrical polars** $(r,\phi,z)$\
    <center>
    $$\begin{aligned}
                    \nabla^{2}\Phi &= \frac{1}{r}\left \{ \frac{\partial}{\partial r}\left ( r\frac{\partial \Phi}{\partial r} \right ) + \frac{\partial}{\partial \phi}\left ( \frac{1}{r}\frac{\partial \Phi}{\partial \phi} \right ) + \frac{\partial}{\partial z}\left ( r\frac{\partial \Phi}{\partial z} \right ) \right \} \\
                    &= \frac{\partial^{2}\Phi}{\partial r^{2}} + \frac{1}{r}\frac{\partial \Phi}{\partial r} + \frac{1}{r^{2}}\frac{\partial^{2}\Phi}{\partial \phi^{2}} + \frac{\partial^{2}\Phi}{\partial z^{2}}
                \end{aligned}$$
    </center>

2.  **Spherical polars** $(r,\theta,\phi)$\
    <center>
    $$\begin{aligned}
                    \nabla^{2}\Phi &= \frac{1}{r^{2}\sin\theta}\left \{ \frac{\partial}{\partial r}\left ( r^{2}\sin\theta\frac{\partial \Phi}{\partial r} \right ) + \frac{\partial}{\partial \theta}\left ( \sin\theta\frac{\partial \Phi}{\partial \theta} \right ) + \frac{\partial}{\partial \phi}\left ( \frac{1}{\sin\theta}\frac{\partial \Phi}{\partial \phi} \right ) \right \} \\
                    &= \frac{\partial^{2}\Phi}{\partial r^{2}} + \frac{2}{r}\frac{\partial \Phi}{\partial r} + \frac{\cot\theta}{r^{2}}\frac{\partial\Phi}{\partial \theta} + \frac{1}{r^{2}}\frac{\partial^{2}\Phi}{\partial \theta^{2}} + \frac{1}{r^{2}\sin^{2}\theta}\frac{\partial^{2}\Phi}{\partial \phi^{2}}
                \end{aligned}$$
     </center>

## Changes of variables in surface integration

Suppose we have surface $S$, parametrized by quantities $u_1,u_2$. We can write:

<center>
$$x = x(u_1,u_2),\quad y = y(u_1,u_2), \quad z = z(u_1,u_2)$$
</center>

Consider surface to be comprised of arbitrarily small parallelograms,
its sides given by keeping either $u_1$ or $u_2$
<center>
$$\begin{aligned}
        dS &= \text{ Area of parallelogram with sides } \frac{\partial \mathbf{r}}{\partial u_1}du_{1} \text{ and } \frac{\partial \mathbf{r}}{\partial u_2}du_{2}\\
        &= \lvert \mathbf{J} \rvert du_{1}du_{2}
    \end{aligned}$$ 
</center>

**Vector Jacobian** given by $\mathbf{J} = \frac{d\mathbf{r}}{du_1}\times\frac{d\mathbf{r}}{du_2}$.

Useful in substitution of surface integrals:
<center>
$$\int_{S}f(x,y,z)dS = \int_{S}F(u_1,u_2)\lvert \mathbf{J}\rvert du_{1}du_{2]}$$
</center>

$F(u_1,u_2) = f(x(u_1,u_2),y(u_1,u_2),z(u_1,u_2))$

For S a region $R$ in the $x-y$ plane we can write:

<center>
$$\int_{R}f(x,y)dxdy = \int_{R}F(u_1,u_2)\lvert det(J(x_u)) \rvert du_1 du_2$$
  
$$\lvert \mathbf{J}\rvert = \vert \frac{d\mathbf{r}}{du_1}\times\frac{d\mathbf{r}}{du_2}\vert = det(J(x_u))  = 
    \begin{vmatrix}
    \partial x/ \partial u_1 & \partial x/\partial u_2\\
    \partial y/\partial u_1 & \partial y/\partial u_2
    \end{vmatrix}$$
</center>

For a surface described by $z = f(x,y)$. We have $x = u_1, y = u_2$ and $\mathbf{r} = (x,y,f(x,y))$\

We have:

<center>
::: aligned
&= &= +\
&= &= +\
:::
</center>

<center>
$$\begin{aligned}
        \lvert \frac{\partial \mathbf{r}}{\partial u_1} \times \frac{\partial \mathbf{r}}{\partial u_2} \rvert &= 
        \begin{Vmatrix}
        \mathbf{\hat{i}} & \mathbf{\hat{j}} & \mathbf{\hat{k}}\\
        1 & 0 & \partial f/ \partial x\\
        0 & 1 & \partial f/\partial y
        \end{Vmatrix}\\
        &= \sqrt{1 + \lvert \nabla f \rvert^{2}}
    \end{aligned}$$
</center>

So we have area of surface given by
<center>
$$\int_{\Sigma}\sqrt{1 + \lvert \nabla f \rvert^{2}}dxdy$$
</center>

for $\Simga$ the projection of $S$ onto the $x-y$ plane.


