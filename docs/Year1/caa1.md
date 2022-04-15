---
layout: default
title: Calculus & its Applications
parent: Year 1
nav_order: 2
math: mathjax3
---
# Calculus & its Applications - Concise Notes 1
{: .no_toc }
## MATH40004
{: .no_toc}
**Term 1 Content**

<head>
  <style>
ol.n {list-style-type: none;}
  </style>
</head>
  

<details closed markdown="block">
  <summary>
    <span style="color: RoyalBlue;">PDFs</span>
  </summary>
 
- <a href="/notes/pdfs/Y1Concise/CAA-MATH4004-c.pdf" target="_blank" style="color:#801fff;">**Calculus Concise**</a> - <a href="/notes/pdfs/Y1Concise/CAA-MATH4004-c.pdf" download>**Download**</a>
- <a href="/notes/pdfs/year1/calc/CAA-ConciseL.pdf" target="_blank" style="color:#801fff;">**Calculus Concise Term 1**</a> - <a href="/notes/pdfs/year1/calc/CAA-ConciseL.pdf" download>**Download**</a>
- <a href="/notes/pdfs/year2/AnalysisII.pdf" target="_blank" style="color:#801fff;">**Open Calculus Lecturer - Term 1**</a> - <a href="/notes/pdfs/year2/AnalysisII.pdf" download>**Download**</a>
- <a href="/notes/pdfs/year2/ANALecII.pdf" target="_blank" style="color:#801fff;">**Open Calculus Lecturer - Term 2**</a> - <a href="/notes/pdfs/year2/ANALecII.pdf" download>**Download**</a>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets - Term 1</span>
  </summary>
  
  - <a href="/notes/pdfs/year1/calc/probsheets/term1/CAAPS1.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 1**</a> - <a href="/notes/pdfs/year1/calc/term1/probsheets/CAAPS1-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year1/calc/probsheets/term1/CAAPS2.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 2**</a> - <a href="/notes/pdfs/year1/calc/term1/probsheets/CAAPS2-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year1/calc/probsheets/term1/CAAPS3.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 3**</a> - <a href="/notes/pdfs/year1/calc/term1/probsheets/CAAPS3-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year1/calc/probsheets/term1/CAAPS4.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 4**</a> - <a href="/notes/pdfs/year1/calc/term1/probsheets/CAAPS4-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year1/calc/probsheets/term1/CAAPS5.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 5**</a> - <a href="/notes/pdfs/year1/calc/term1/probsheets/CAAPS5-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year1/calc/probsheets/term1/CAAPS6.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 6**</a> - <a href="/notes/pdfs/year1/calc/term1/probsheets/CAAPS6-Sol.pdf" target="_blank">**Solutions**</a>
  
  - <a href="/notes/pdfs/year1/calc/probsheets/term1/CAAPS7.pdf" target="_blank" style="color:#00ba47;">**Problem Sheet 7**</a> - <a href="/notes/pdfs/year1/calc/term1/probsheets/CAAPS7-Sol.pdf" target="_blank">**Solutions**</a>
  
</details>

<details closed markdown="block">
  <summary>
    <span style="color: #00ba47;">Problem Sheets - Term 2</span>
  </summary>
  
  - <a href="/notes/pdfs/year2/problemsheets/anlaysisSheets/term2/ANAPS1.pdf" target="_blank" style="color:#00ba47;">** PLACE HOLDER LINK **</a> - <a href="/notes/pdfs/year2/problemsheets/anlaysisSheets/term2/ANAPS1-Sol.pdf" target="_blank">**Solutions**</a>
  
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




# Chapter 1, Limits of Functions, continuity


**Definition 1**. $\epsilon - \delta$ Definition of Limit


\
Let $f$ be a function defined at all points near $X_0$, except possible
at $x_0$\
let $l$ be a real number.\
 We say that $l$ is a limit of
$f(x)$ as $x$ approaches $x_0$ if

$$\forall \epsilon >0\ \exists\delta>0 \text{ s.t } |f(x)-l|<\epsilon  
\text{ for  } |x-x_0|<\delta, x\neq x_0$$

We write $lim_{x\rightarrow x_0}f(x)=l$

**Basic Properties of Limits**

1.  *Sum rule*\
    $\lim_{x \to x_0}[f(x)+g(x)]=\lim_{x \to x{0}} f(x) + \lim_{x \to x{0}} g(x)$

2.  *Product rule*\
    $\lim_{x \to x{0}} [f(x)g(x)]=\lim_{x \to x{0}} f(x)\lim_{x \to x{0}} g(x)$

3.  Reciprocal rule\
    if $\lim{x \to x_{0}} f(x)\neq 0$ then\
    $\lim_{x \to x{0}} [1/f(x)] = 1/\lim_{x \to x{0}} f(x)$

4.  *Quotient rule*\
    If $\lim_{x \to x{0}} g(x)\neq 0$ then\
    $\lim_{x \to x{0}} [f(x)/g(x)] = \lim_{x \to x{0}} f(x)/\lim_{x \to x{0}} g(x)$

5.  *Composite function rule*\
     If $h(x)$ is conitnuous at
    $\lim_{x \to x{0}} f(x)$ then\
    $\lim_{x \to x{0}} h(f(x)) = h(\lim_{x \to x{0}} f(x))$


**Definition 2**. The $\epsilon - A$ definition of
$\lim{x \to \infty} f(x)=l$


Let $f(x)$ be defined on a domain containing, the interval $(a,\infty)$.A
real number $l$is the limit of $f(x)$ as $x$ approaches $\infty$ if for
every $\epsilon>0$ there exists a $A>a$, such that $|f(x)-l|<\epsilon$
whenver $x>A$. We write $\\lim{x \to \infty} f(x)=l$


**Definition 3**. $\epsilon - B$ definition of
$\lim_{x \to x{0}} f(x)=\infty$


Let $f(x)$ be a function defined in an interval containing $x_0$ except
possibly at $x=x_0$. We saythat $f(x)$ approaches $\infty$ as $x$
approaches $x_0$, if given any real number $B>0$, there exists
$\epsilon >0$, so that whenever $|x-x_0|<\epsilon$ and $x\neq x_0$, we
have $f(x)>B$. We write $\lim_{x \to x{0}} f(x)=\infty$


**Definition 4**. One-Sided limit


Let $f(x)$ be defined for all $x$ in an interval $(x_0,a)$. We say that
$f(x)$ approaches $l$ as $x$ approaches $x_0$ from the right if for any
$\epsilon>0$ there exists $\delta >0$, such that for all
$x_0 <x<x_0 +\delta$ we have $|f(x)-l|<\epsilon$. We Write
$\lim_{x \to x{0}-} f(x)=l$

**Comparison Test for Limits**

1.  $\lim_{x \to x{0}} f(x)=0$ and $|g(x)\leq |f(x)|$ for all $x$ near
    $x_0$ with $x\neq x_0$, then $\lim_{x \to x{0}} g(x)=0$

2.  $\lim_{x \to \infty} f(x)=0$ and $|g(x)|\leq |f(x)|$ for all large
    enough $x$ then$\lim_{x \to \infty} g(x)=0$

**Two Basic Trigonometric Limits**

$\lim_{h \to 0}\frac{sinh}{h}=1$ $\lim_{h\to 0}\frac{cosh-1}{h}=0$


**Definition 5**. Continuity


We say that $f$ is continuous at $x_0$ if
$\lim_{h \to 0}f(x_0+h) = f(x_0)$ Equivalently
$\lim_{x \to x{0}} f(x)=f(x_0)$ A totally equivalent definition is:
$f(x)$ is continuous at a point $x_0$ if for every $\epsilon>0$ there
exists a number $\delta >0$ such that $|f(x)-f(x_0)|<\epsilon$ for all
$x$ in the domain of $f$ for which $|x-x_0|<\delta$

# Differentiation

## Definition with limits


**Definition 6**. Differentiability


The function $f(x)$ is differentiable at x if \"Newton's quotient\"

$\lim{h \to 0}\frac{f(x+h)-f(x)}{h}$ exists. We call this $f'(x)$ the
derivative of $f$ at point $x$

### Polynomials


**Theorem 1**.


Let $n$ be an integer $\geq 1$ and let $f(x)=x^n$. Then
$f'(x)=\frac{df}{dx}=nx^{n-1}$


**Theorem 2**.


Let $f(x)=x^a$ where $a$ is any real number and $x>0$. Then
$f'(x) = ax^{a-1}$.

## General rules, chain rule, rate of changes

### General rules

1.  If $c$ is a constant $(cf)'(x)=cf'(x)$

2.  if $f(x),g(x)$ are given functions and $f'(x),g'(x)$ exist, then

    $(f+g)'(x)=f'(x)+g'(x)$

3.  $(fg)'(x)=f'(x)g(x)+f(x)g'(x)$

4.  Let g(x) be a function that has a derivative $g'(x)$ and such that
    $g(x)\neq0$\
    Then $\frac{d}{dx}(\frac{1}{g(x)})=-\frac{g'(x)}{(g(x))^2}$

5.  $\frac{d}{dx}\frac{f(x)}{g(x)}=\frac{g(x)f'(x)-f(x)g'(x)}{(g(x))^2}$



### The Chain Rule

$$\frac{d}{dx}(f\circ g)(x)=(f\circ g)'(x)=f'(g(x))g'(x)$$


**Theorem 3**.


If $f(x)$ is differentiable at $x=x_0$ then it is also continuous there.

## Implicit differentiation, related rates of change

Not much notable here. You can prove the derivative of polynomials with
fractional powers using implicit differentiation.

# Mean Value and Intermediate Value Theorems

For a function $f(x)$ which is defined at a point $c$, we say that $c$
is *maximum* of $f$ if

$f(c)\geq f(x) \forall x$ where $f$ is defined

The minimum is obvious


**Theorem 4**.


Let $f$ be a function which is defined and differentiable on the open
interval $(a,b)$. Let $c$ be a number in the interval which is a maximum
for the function. Then $f'(c)=0, f'(c)=0$ also if $c$ is a minimum of
$f$


**Theorem 5**.


Let $f(x)$ be continuous on the close interval \[a,b\]. Then $f(x)$ has
a maximum and a minimum on this interval.


**Theorem 6**.


Let $f(x)$ be continuous over the closed interval$a\leq x \leq b$ and
differentiable on the interval $a<x<b$. Assume also that $f(a)=f(b)=0$.
Then there exists a point $c, a<c<b$ such that $f'(c)=0$


**Theorem 7**.


Suppose $f$ is continuous on $[a,b]$ and differentiable on $a,b$ Then
there exists $a<c<b$ such that $f'(c) = \frac{f(b)-f(a)}{b-a}$


**Definition 7**.


We say that $f$ is increasing over a given interval if given $x_1,x_2$
in the interval with $x_1\leq x_2$, we have $f(x_1)\leq f(x_2)$ If it is
strictly increasing it is the same with $<$ insteaf of $\leq$ Same for
decreasing and strictly decreasing


**Definition 8**.


Let $f(x)$ be continuous in some interval, and differentiable there(even
possible at the end points.)\
If $f'(x)=0$ in the interval(except possible at endpoints) then $f$ is
constant\
If $f'(x)>0$ in the interval(except possible at endpoints) then $f$ is
strictly increasing\
If $f'(x)<0$ in the interval(except possible at endpoints) then $f$ is
striclty decreasing\


**Theorem 8**. Intermediate value theorem


Let $f$ be continuous on the close interval $a\leq x\leq b$. Given any
number $y*$ between $f(a) and f(b)$, there exists a point $x*$ between a
and b such that $f(x*)=y*$

# Inverse Functions


**Definition 9**.


Let $y=f(x)$ be defined on some interval. Given any $y_0$ in the range
of $f$, if we can find a unique value $x_0$ in its domain such that
$f(x_0)=y_0$, then we an define the ***inverse funtion***
$x=g(y)$(sometimes written $x=f^{-1}(y)$


**Theorem 9**.


Let $f(x)$ be strictly increasing or strictly decreasing. Then the
inverse function exists.


**Theorem 10**.


If $f(x)$ is continuous $[a,b]$ and is strictly increasing(or
decreasing), and $f(a)=y_a$ and $f(b)=y_b$, then $x=g(y)$ is defined on
$[y_a,y_b]$\

### Derivative of inverse functions


**Theorem 11**.


let $f(x)$ be differentiable on $(a,b)$ and $f'(x)>0$ or $f'(x)<0$ for
all $x$ in $(a,b)$. Then the inverse function exists and we have

$g'(y)=\frac{d}{dy}f^{-1}(y)=\frac{1}{f'(x)}$

# Exponentials and Logarithms

## Geometrical Definition, Derivative


**Definition 10**.


The quantity $log(x)$ is the area under the curse $\frac{1}{x}$ between
$1$ and $x$ if $x\geq 1$ and the negative the area under the curve
$\frac{1}{x}$ between $1$ and $x$ if $x$ is in the interval $(0,1)$. In
particular $log(1)=0$


**Theorem 12**.


$log(x)$ is differentiable and $\frac{d}{dx}log(x)=\frac{1}{x}$


**Theorem 13**.


If $a,b>0$, then $log(ab)=log(a)+log(b)$


**Theorem 14**.


$log(x)$ is strictly increasing for all $x>0$. Its range is
$(-\infty,\infty)$


**Theorem 15**.


If $n$ is an integer(positive or negative) then $log(a^n)=nlog(a)$ for
all $a>0$

## Exponential as Inverse of $logx$


**Theorem 16**.


If $x_1,x_2$ are two numbers then $exp(x_1+x_2)=exp(x_1)exp(x_2)$


**Theorem 17**.


$exp(x)$is differentiable and $\frac{d}{dx}exp(x)=exp(x)$


**Theorem 18**.


$\frac{d}{dx}a^x=a^x(log(a))$\
\
**Corollary:**\
$\lim_{h\to 0}\frac{a^h-1}{h}=log(a)$ for $a>0$


**Theorem 19**.


Let $a$ be any real number and let $f(x) = x^a$ for $x>0$.Then $f'(x)$
exists and $f'(x)=ax^{a-1}$

## Function estimates for Small and Large Arguments


**Theorem 20**. Let $a$ be any real number. Then
$\frac{(1+a)^n}{n}\to \infty$ as $n \to \infty$


\
**Corollary:**$\frac{e^n}{n}\to \infty$ as $n\to \infty$ since $e=1+a$
for some $a>0$\


**Theorem 21**.


The function $f(x)=\frac{e^x}{x}$ is strictly increasing for $x>1$ and
$\lim_{x\to \infty}f(x)=\infty$\
**Corollary**\
The function $x-log(x)$ becomes arbitrarily large as $x$ becomes
arbitrarily large. x beats log.\
**Corrolary**\
The function $\frac{x}{log(x)}$ becomes large as $x$ becomes large. x
beats log\
 **Corolary**\
As x becomes large $x^{1/x}$ approches the limit 1.


**Theorem 22**. exp(x) beats any power of x


Let $m$ be a positive integer. Then the function $f(x)=\frac{e^x}{x^m}$
is strictly increasing for x>m and becomes arbitrarily large as $x$
becomes arbitrarily large.

## Logarithmic Differentiation

not much here

## L'Hopital's Rule


**Theorem 23**.


If $f,g$ are differnetiable on an open interval containing $x_0$,
$g(x_0) =f(x_0)=0$, and $g'(x_0)\neq 0$, then\
$\lim_{x\to x_0}\frac{f(x)}{g(x)}=\frac{f'(x_0)}{g'(x_0)}$


**Theorem 24**.


Let $f(x)$ and $g(x)$ be a differentiable on an open interval containing
$x_0$(except possible at $x_0$). Assume that $g(x)\neq0$ and
$g'(x)\neq 0$ for $x$ in an interval about $x_0$ but with $x\neq x_0$.
Assume also that $f.g$ are continous at $x_0$ with $f(x_0)=g(x_0)=0$ and
$\lim_{x\to x_0}\frac{f(x)}{g(x)}=l$. Then also:

$\lim_{x \to x_0}\frac{f(x)}{g(x)}=l$


**Theorem 25**. L'Hopital's Rule-general case


To find $lim{x\to x_0}\frac{f(x)}{g(x)}$ when $lim{x\to x_0}f(x)$ and
$\lim{x\to x_0}g(x)$ are both zero or both infinite, differentiate
numberator and denominator and take the limit of the new function.
Repeat as many times as needed as long as it satisfies the conditions.
Note that $x_0$ may be replaced by $\pm\infty$ or $x_0\pm$


**Theorem 26**. Cauchy Mean Value Theorem


Let f,g be continuous on $[a,b]$ and differentiable on $(a,b)$ with
$g(a)\neq g(b)$. Then there exists $c$ in $(a,b)$ such that
$g'(c)\frac{f(b)-f(a)}{g(b)-g(a)}=f'(c)$

# Integration

## Anti-derivative and Geometrical Interpretation


**Definition 11**.


Given $f(x)$ defined over some interval then if we can find a function
$F(x)$ defined over the same interval such that

$F'(x)=f(x)$ then $F(x)$ is the *indefinite integral* of $f$
$\longrightarrow F = \int f(x)dx$. Then

$\frac{d}{dx}(F-G)=0\Rightarrow F(x) = G(x)+ constant$

### Area under a curve


**Theorem 27**.


The function $F(x)$ is differentiable and its derivatives is equal to
$f(x)$. Another way to state this is $\frac{d}{dx}\int^x_af(t)dt=f(x)$


**Definition 12**. Signed Area


If $f(x)<0$ then the area is below the $x-axis$.Define $F(x)$ to be
**minus** the area. This leads to the definite integral.

# The Riemann Sum

Given $f(x),a\leq x\leq b$, take the partition of the interval $[a.b]$
to be $x_i = a+ih$ $i=0,1,\ldots\ldots,n$ $h=\frac{b-a}{n}$ Take any
sub-interval $[x_{i-1},x_i]$ and let $x_i \in [x_{i-1},x_i]$. Then **the
Riemann sum** is $\Sigma^n_{i=1} f(x_i*)h$ There are three ways of
picking $x_i*$

1.  $x_i*=x_i$ the right hand Riemann Summ

2.  $x_i*=x_{i-1}$ left hand RS

3.  $x_i*=\frac{1}{2}(x_i+x_{i-1})$ mid point RS

The Limit as $n\to \infty,h\to0$
$\lim_{n\to \infty}\sum^n_{i=1}f(x_i*)h=\int^b_af(x)dx$ This can be
probed using squeeze theorem between the Lower Riemann sum and Right Sum

# Properties of the definite Integral; Fundamental Theorrem of Calculus

1.  $\int^b_acf(x)dx =c\int^b_af(x)dx$ $c$ a constant

2.  $\int^b_af(x)+g(x)dx = \int^b_af(x)dx+\int^b_ag(x)dx$

3.  If $c\in (a,b)$ then

    $\int^b_af(x)dx=\int^c_af(x)dx+\int^b_cf(x)dx$

4.  If $f(x)\leq g(x)$ for $x\in [a,b]$ then

    $\int^b_af(x)dx\leq \int^b_ag(x)dx$


**Theorem 28**. Suppose $g(x)$ is defined for all $x\in [a,b]$ and is
differentiable on $[a,b]$. Then

$\int^b_ag'(x)dx = g(b)-g(a)$


\


**Theorem 29**. *Fundamental Theorem of Calculus*


Suppose $F$ is differentiable on \[a.b\] and $F'$ is integrable on
$[a,b]$ Then

$\int^b_aF'(x)dx= F(b)-F(a)$

If $f$ is integrable on $[a,b]$ and has *anti-derivative* $F$ then

$\int^b_af(x)dx=F(b)-F(a)$ **Useful Theorem**
$\frac{d}{dx}\int^{g(x)}_af(t)dt=f(g(x))g'(x)$

# Some Application

just do practise questions for these. this aint fucking physics note

# Improper Integrals


**Definition 13**. Improper Integral


$\int^b_af(x)dx$ is an ***improper integral*** if\
(i) $a=-\infty$ and/or $b=\infty$\
(ii) $f(x)\to \pm\infty \text{ in } (a,b)$

# Mean value theorem for Integrals

Given a function $f$ that is integrable on $[a.b]$ we define its average
$\langle f \rangle_{[a,b]}$ by the formula
$\langle f \rangle_{[a,b]} = \frac{1}{b-a}\int^b_af(x)dx$\


**Theorem 30**.


Let $f$ be continuous on $[a,b]$ then there exists a point $x_0\in(a.b)$
such that

 center
$f(x_0)=\frac{1}{b-a}\int^b_af(x)dx$


# Techniques of Integration

lmao it's just integration just get good

# Application of Integration

**Length of Curves** $L = \int^b_a[1+(f'(x))^2]^{1/2}dx$\
$L=\int^{t_1}_{t_0}[(\frac{dx}{dt})^2+(\frac{dy}{dt})^2]^{1/2}dt$
**Volumes of Revolution**

$V=\int^b_a\pi(f(x))^2dx$ Rotating around x-axis\
$V=\int^b_a2\pi xf(x)dx$ Revolving around the y-axis\
swith the x and y for rotating around y-axis

**Surface area of revolution** $S=\int^b_a2\pi f(x)\sqrt{1+(f(x))^2}dx$

## Centre of Mass

1D case-simple If centre of mass is at x=\|x, then we must have zero
total moment

 ecnter
$\Sigma m_k(\bar{x}-x_k)=0$ i.e
$\bar{x}=\frac{\Sigma m_kx_k}{\Sigma m_k}$


2D-case- disrete masses\
If there are n-masses of mass $m_k$ and cordinates $(x_k,y_k)$. Assume
the centre of mass is $(\bar(x),\bar{y})$. So must balance the moments
in $x-axis$ and $y-axis$\
Therefore:\
$\bar{x} = \frac{\Sigma m_ix_i}{\Sigma m_i}$,$\bar{y} = \frac{\Sigma m_iy_i}{\Sigma m_i}$\
Now for continuous mass distribution.\
Define the density per unit area as $\rho(x,y)$\
Dividing the region into small rectangles with sides
$\Delta y, \Delta x$\
So the moment of one of these rectangles about the y-axis is
$x_i\rho(x_i,y_i)\Deltax \Delta y$\
Adding all of them gives $\Sum_i\Sum_jx_i\rho(x_i,y_i)\Deltax \Delta y$\
The moment of the whole plate about the y-axis
$\bar{x\int\int\rho(x,y)dxdy}$\
Therefore $\bar{x}\int\int\rho dxdy = \int\int x \rho dxdy$\
similar result for $\bar{y}$

\


**Theorem 31**. Theorem of Pappus


Let $R$ be a region that lies on one side of line $l$
$A=\text{area of }R$\
$V=$ Volume obtained by rotating about $l$\
$d=$ distane travelled by the centre of mass when $R$ is rotated\
then $V=Ad$

## Mment of Inertia

Consider an object of mass $m$ at a distane $y$ from the x-axis rotating
at an angular velocity of $\omega$.\
Then the velocity of the the object is\
$v=y\omega$\
And thus the kinetic energy of the object is\
$KE=\frac{1}{2}m(y\omega)^2$.\
The coefficient of $\frac{1}{2}\omega^2$ ia defined to be the **moment
of inertia**. Hence for the single particle considered here, we define
the moment of inertia $I$ to be\
$I=my^2$\
And therefore $KE=\frac{1}{2}\omega^2I$\
\
So using this, we an express the moment of inertia of a string.\
Moment of Inertia about $x$-axis -
$I_x = \int^{x_1}_{x_0}\rho (x)y^2\sqrt{1+y^2}$\
Moment of Inertia about $y$-axis -
$I_y = \int^{x_1}_{x_0}\rho (x)x^2\sqrt{1+y^2}$

## Length Of curves and areas ousing polar coorindates

**Length of polar curve**:
$L=\int^{\beta}_{\theta =\alpha}[(\frac{dr}{d\theta})^2+r^2]^{1/2}d\theta$\
**Area of polar curve**\
$A=\frac{1}{2}\int^{\beta}_{alpha} r^2 d\theta$

# Series


**Definition 14**.


Given a sequence ${a_n}_{n\geq1}$of real numbers, define the sequence of
partial sums $S_N=\Sigma^N_{n=1}a_n$ If $S_N\to S$ as $N\to\infty$ we
say the series converges to the sum $S$ $S=\Sigma^{\infty}_{n=1}a_n$


**Theorem 32**.


The series $\sum^{\infty}_{n=1}\frac{1}{n}$ diverges to $+\infty$


**Theorem 33**.


If $\alpha >1$ is a rational number, then
$\sum^{\infty}_{n=1}\frac{1}{n^{\alpha}}$ converges

### Elemental algebraic rules for series


**Theorem 34**.


If the series $\sum^{\infty}_{n=1}a_n$ converges then $a_n \to 0$ as
$n \to \infty$

## Cauchy sequences and convergence of series


**Definition 15**. Cauchy Sequence


Cauchy Sequence if and only if:

$\forall \epsilon>0 \exist N\in \mathbb{N}\text{ such that for any } m,n>N$\
$|S_m-S_n|<\epsilon$


**Theorem 35**. Every cauchy sequence converges


\


**Theorem 36**. The alternating series test


A series thats alternating and $a_n\to 0$ as $n\to \infty$ converges

## Convergence tests


**Theorem 37**. Comparison test


Llet $\sum^{\infty}_{n=1}b_n$ be convergent with $b_n$ non-negative. If
$|a_n|\leq b_n$then the series for $a_n$ converges


**Theorem 38**.


Every absolutely convergent series is convergent


**Theorem 39**. Integral test


Let $f(x)$ be a function which is defined for all $x\geq1$, and is
positive and decreasing. $\sum^{\infty}_{n=1}f(n)$ converges if and only
if the indefinite integral to infinity converges


**Theorem 40**. The ratio test


Let $S= \sum^{\infty}_{n=1}a_n$
$\lim{n\to \infty}|\frac{a_{n+1}}{a_n}|=L$ Then:

1.  If $L<1$ the series converges absolutely

2.  If $L>1$ the series diverges

3.  If $L=1$ the test is inconclusive


**Theorem 41**. The root test


Suppose:

 center
$\lim{n\to \infty}|a_n|^{1/n}=L$


Then:\

1.  If $L<1$ the series converges absolutely

2.  If $L>1$ the series diverges

3.  If $L=1$ the test is inconclusive

# Power Series


**Definition 16**.


let $x$ be a real number and ${a_n}_{n\geq0}$ be a sequence of numbers.
Then we can form the **power series** $\sum^{\infty}_{n=0}a_nx^n$. The
partial sums $S_N$ are polynomials of degree $N$\


**Theorem 42**.


Assume that there is a number $R>0$ such that
$\sum^{\infty}_{n=0}a_nR^n$ converges. Then for all $|x|<R$ the
series$\Sum^{\infty}_{n=0}a_nx^n$ converges absolutely\


**Definition 17**.


The greatest such $R$(mentioned above) is called the ***radius of
convergence***.


**Theorem 43**. Ratio test for power series


Let $\Sum^{\infty}_{n=0}a_n$ be a power series and asuume that
$\lim{n\to\infty}|\frac{a_{n+1}}{a_n}|=L$ exists. Let $R=\frac{1}{L}$\
Then

1.  If $|x|<R$ the series converges absolutely

2.  If $|x|>R$ the serues diverges

3.  If $x=\pm R$ could converge or diverge

\

## Differentiation and integration of power series

We can differentiate power series if $|x|<R$


**Theorem 44**.


Let $f(x)=\sum^{\infty}_{n=0}a_n$\
THen $f'(x)=\sum^{\infty}_{n=0}na_{n-1}$ The integral is the opposite


**Theorem 45**.


If two power series with radi of convergence $R_1,R_2$ are added or
multiplied together then the radi of convergence of the new series is
$min(R_1,R_2)$

# Taylor series


**Theorem 46**. Taylor's theorem with remainder


Let $f$ be a function defined on a closed interval between two numbers
$x_0$ and $x$. Assume that the function has $n+1$ derivatigves on the

 center
$f(x) = f(x_0)+f'(x_0)(x-x_0)+\frac{f^{2}(x_0)}{2!}(x-x_0)+\ldots +\frac{f^{n}(x_0)}{n!}(x-x_0)^n+R_n$


where the remaineder $R_n$ is given by

 center
$R_n= \int^x_{x_0}\frac{(x-t)^n}{n!}f^{n+1}(t)dt$


## Exponentials and logarithms. Binomial theorem

$e^x=1+x+\frac{x^2}{2}+\ldots+\frac{x^n}{n!}+\frac{e^c}{(n+1)!}x^{n+1}$\
$log(1+x)=x-\frac{x^2}{2}+\frac{x^3}{3}+\ldots+(-1)^{n-1}\frac{x^n}{n}+(-1)^{n}\int^x_0\frac{t^n}{1+t}dt$\
$(1+x)^n=\sum^{\infty}_{n=1}\frac{\alpha(\alpha-1)\ldots(\alpha -n+1)}{n!}x^n$

# Orthogonal and orthonormal function spaces


**Definition 18**.


If $f,g$ are real value functions that are Riemann integrabale then the
inner product of $f,g$ are

 center
$(f,g)=\int^b_af(x)g(x)dx$


\


**Definition 19**.


Let $\mathcal{S}={\phi_0,\phi_1,\ldots,}$ be a collection of functions
that are Riemann integrable on \[a,b\] If

 center
$(\phi_n,\phi_m)=0$ whenver $m\neq n$


Then $\mathcal{S}$ is an ***Orthogonal*** system on \[a,b\].
Additionally if $||\phi_n||=1$ then $\mathcal{S}$ is said to be
***Orthonormal***

# Periodic functiuons and periodic extensions

 dfn


At points of discontinuity define

 center
$f(\xi) = \frac{1}{2}[f(\xi _+)+f(\xi_-)]$


\

# Trigonometric polynomials

## Euler's relation

$cos(\theta)+isin(\theta)=e^{i\theta}$ **Orthogonality**
$\int^{\pi}_{-\pi}e^{inx}e^{-imx}dx= 0$ if $n\neqm, =2\pi$if $n=m$

# Fourier series

Consider the trigonetrix polynomial

 center
$f(x)=S_N(x)= \frac{1}{2}a_0+\Sum^N_{n=1}a_ncos(nx)+b_nsin(nx)$\
where $a_n = \frac{1}{\pi}\int^{\pi}_{-\pi}f(x)cos(nx)dx$\
$b_n = \frac{1}{\pi}\int^{\pi}_{-\pi}f(x)sin(nx)dx$


**Orthogonality properties** If $m,n$ are integers then

 center
$\int^{\pi}_{-\pi}sin(mx)sin(nx)dx =\int^{\pi}_{-\pi}cos(mx)cos(nx)dx=0,m\neq n,\pi, m=n$\
$\int^{\pi}_{-\pi}sin(mx)cos(nx)dx=0$



**Theorem 47**. The fourier series formed by the fourier coefficients
converges to the value $f(x)$ for any piecewise continuous function
$f(x)$ over period period $2\pi$ which has piecewise continuous
derivatives of first and second order. At any discontinuities the
function must be defined by $f(x) = \frac{1}{2}[f(x^+)f(x^-)]$


\
If
$c_n(x)=\frac{1}{2}+ cos(x)+cos(2X)+cos(3x)+\ldots = \frac{sin(n+\frac{1}{2})x}{2sin(0.5x)}$
Define the poits where $\frac{1}{2}x = n\pi$ define $c_n$ by $n+1/2$
**Riemann-Lebesgue Lemma**

$I_{\lambda}= \int^b_ag(x)sin(\lambda x)dx$ tends to 0 as
$\lamda \to \infty$

**Lemma 2**

$\int^{\infty}_0\frac{sin(z)}{z}dz=\frac{\pi}{2}$

**Parseval's indentity**\
If $f(x)=S_N(x)= \frac{1}{2}a_0+\sum^N_{n=1}a_ncos(nx)+b_nsin(nx)$\
Then
$\frac{1}{\pi}\int^{\pi}_{-pi}f^2dx=\frac{1}{2}a^2+0+\sum^{\infty}_{n=1}(a_n^2+b_n^2)$

***Fourier Transform pair***

$f(x)=\frac{1}{2\pi}\int^{\infty}_{-\infty}\int^{\infty}_{-\infty}f(t)e^{i\omega t}dte^{i\omega x d\omega}$


