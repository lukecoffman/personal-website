---
{"dg-publish":true,"permalink":"/independent-learning/math/analysis/real-analysis/","created":"2024-12-24T19:32:37.912-07:00","updated":"2025-03-14T20:49:05.000-06:00"}
---

# Overview
>[!question] What is real analysis?

> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Resources
> Undergraduate:
> - ["Analysis 1" by Terence Tao](https://link.springer.com/book/10.1007/978-981-19-7261-4)
>   
> Graduate:
> - 

> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - x
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

# Section 1
>[!def] Metric Space
>Let $X$ be a set and $d:X\times X\rightarrow \mathbb{R}$ be a function satisfying the following properties for $x,y,z\in X$:
>1. $d(x,x)=0$
>2. If $x\neq y$ then $d(x,y)>0$
>3. $d(x,y)=d(y,x)$
>4. $d(x,z) \le d(x,y)+d(y,z)$
>
>then $(X,d)$ is a called a **metric space** and $d$ is called the **metric**.
>^def-metric-space

>[!def]  Cauchy Sequence
>Let $(x_n)_{n\in \mathbb{N}}$ be a sequence in $(X,d)$. The sequence is said to be **Cauchy** if for all $\epsilon >0$ there exists $N\in \mathbb{N}$ such that for all $n,m\ge N$ we have that $d(x_n,x_m)<\epsilon$.
>^def-cauchy-sequence

>[!def] Complete Metric Space
>A **complete metric space** is a metric space $(X,d)$ such that any [[Independent Learning/Math/Analysis/Real Analysis#^def-cauchy-sequence\|Cauchy Sequence]] $(x_n)_{n\in \mathbb{N}}$ there exists $x\in X$ such that $\lim_{n \rightarrow \infty}x_n=x$ that is for all $\epsilon>0$ there exists $N\in \mathbb{N}$ such that for all $n\ge N$ $d(x_n,x)<\epsilon$.
>^def-complete-metric-space

## Multivariable Calculus
Here we outline the main concepts from multivariable calculus as discussed in [Lee's "Introduction to Smooth Manifolds" Appendix C](https://link.springer.com/book/10.1007/978-0-387-21752-9?page=2).

### Total and Partial Derivatives
> [!def] Total Derivative
> Let $V,W$ be finite-dimensional [[Independent Learning/Math/Algebra/Linear Algebra#^def-norm-space\|normed]] [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector spaces]] and $U\subset V$ be an [[Independent Learning/Math/Topology and Geometry/Topology#^def-open-set\|open subset of $V$]]. A map $F:U\to W$ is said to be **differentiable at $a\in U$** if there exists a [[Independent Learning/Math/Algebra/Linear Algebra#^def-linear-map\|linear map]] $L:V\to W$ such that
> $$
\lim_{v\to 0} \frac{\left \lVert F(a+v)-F(a)-L(v) \right \rVert_{W}}{\left \lVert v \right \rVert_{V}}=0.
>$$
>Note: Since all norms on finite-dimensional vector spaces are equivalent, the definition is independent of the choice of norm. The linear map $L$ is often denoted $DF(a)$ and is called the **total derivative of $F$ at $a$**.
>^def-total-derivative

> [!info]- Intuition for Definition of [[Independent Learning/Math/Analysis/Real Analysis#^def-total-derivative\|Total Derivative]]
> In 1D calculus, the derivative at a point is the tangent line at that point.


> [!prop] Chain Rule for Total Derivatives
> Suppose $V,W,X$ are finite-dimensional [[Independent Learning/Math/Algebra/Linear Algebra#^def-norm-space\|normed spaces]], $U\subseteq V$ and $\tilde{U}\subseteq W$ are [[Independent Learning/Math/Topology and Geometry/Topology#^def-open-set\|open subsets]], and $F:U\to \tilde{U}$ and $G:\tilde{U}\to X$ are maps. If $F$ is [[Independent Learning/Math/Analysis/Real Analysis#^def-total-derivative\|differentiable]] at $a\in U$ and $G$ is [[Independent Learning/Math/Analysis/Real Analysis#^def-total-derivative\|differentiable]] at $F(a)\in \tilde{U}$, then $G\circ F$ is [[Independent Learning/Math/Analysis/Real Analysis#^def-total-derivative\|differentiable]] at $a$, and
> $$
D(G\circ F)(a)=DG(F(a))\circ DF(a).
>$$
>^prop-chain-rule-total-derivatives

> [!proof]- of Statement
> Contents


> [!prop] $DF(a)$ is the Jacobian of $F$ at $a$
> Let $U\subseteq \mathbb{R}^{n}$ be [[Independent Learning/Math/Topology and Geometry/Topology#^def-open-set\|open]] and suppose that $F:U\to \mathbb{R}^{n}$ is [[Independent Learning/Math/Analysis/Real Analysis#^def-total-derivative\|differentiable]] at $a\in U$. Then all partial derivatives of $F$ at $a$ exist, and $DF(a)$ is the linear map whose matrix is the Jacobian of $F$ at $a$:
> $$
DF(a)=\left( \frac{\partial F^{j}}{\partial x^{i}}(a)\right).
>$$
>^prop-total-derivative-matrix-is-Jacobian





