---
{"dg-publish":true,"permalink":"/independent-learning/math/topology-and-geometry/topology/","created":"2025-01-10T20:42:58.669-07:00","updated":"2025-03-14T20:51:07.422-06:00"}
---

# Overview
>[!question] What is topology?
>Topology

> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Resources
> - ["Topology: A First Course in Topology" by Munkres](https://books.google.com/books/about/Topology.html?id=XjoZAQAAIAAJ)

> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - Undergraduate [[Independent Learning/Math/Analysis/Real Analysis\|Real Analysis]]
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

# Section 1
>[!def] Topological Space
>Let $X$ be a set and let $\mathcal{T}\subset \mathcal{P}(X)$ be a collection of subsets of $X$ that obey the following:
>1. $\emptyset,X \in \mathcal{T}$
>2. If $\{O_i\}_{i\in I} \subset \mathcal{T}$ is an arbitrary collection of subsets then $\bigcup_{i\in I}O_i \in \mathcal{T}$
>3. If $\{O_i\}_{i=0}^\infty\subset \mathcal{T}$ is a countable collection of subsets then $\bigcap_{i=0}^{\infty}O_i\in \mathcal{T}$
>
>Then we say that $\mathcal{T}$ is a **topology** on $X$ and refer to the pair $(X,\mathcal{T})$ as a **topological space**.
>^def-topological-space


> [!def] Open Set
> An **open set** in a [[Independent Learning/Math/Topology and Geometry/Topology#^def-topological-space\|topological space]] $(X,\mathcal{T})$ is a subset $U\subseteq X$ such that $U\in \mathcal{T}$.
>
{ #def-open-set}



>[!def] Standard topology on $\mathbb{R}$
>The standard topology ...

>[!def] Continuous Function
>Let $X$ and $Y$ be [[Independent Learning/Math/Topology and Geometry/Topology#^def-topological-space\|topological spaces]]. A function $f:X\rightarrow Y$ is said to be **continuous** if for all $U\subset Y$ open $f^{-1}(U)$ is open in $X$.
>^def-continuous-function


> [!prop] Properties of Continuous Functions
> 1. Suppose $X,Y,Z$ are [[Independent Learning/Math/Topology and Geometry/Topology#^def-topological-space\|topological spaces]] and $f:X\to Y, g:Y\to Z$ are [[Independent Learning/Math/Topology and Geometry/Topology#^def-continuous-function\|continuous maps]]. Then $f\circ g:X\to Z$ is a [[Independent Learning/Math/Topology and Geometry/Topology#^def-continuous-function\|continuous map]].
> 2. 
>^prop-properties-of-continuous-functions

> [!proof]-
> 1. Suppose the above and let $U\subseteq Z$ be open. Then by the [[Independent Learning/Math/Topology and Geometry/Topology#^def-continuous-function\|continuity]] of $g$, $g^{-1}(U)$ is open in $Y$. Similarly, by the [[Independent Learning/Math/Topology and Geometry/Topology#^def-continuous-function\|continuity]] of $f$ we have that $f^{-1}(g^{-1}(U))$ is open in $X$. Therefore, $(f\circ g)^{-1}(U)=f^{-1}(g^{-1}(U))$ is open in $X$ implying that $f\circ g$ is continuous.




>[!def] Homeomorphism
>Let $X$ and $Y$ be [[Independent Learning/Math/Topology and Geometry/Topology#^def-topological-space\|topological spaces]].  A function $f:X\rightarrow Y$ is said to be a **homeomorphism** if $f$ is a bijection and both $f$ and $f^{-1}$ are [[Independent Learning/Math/Topology and Geometry/Topology#^def-continuous-function\|continuous]]. Symbolically, we write that $X\cong Y$ to say that $X$ is **homeomorphic** to $Y$ when such a function exists.

>[!idea] Category theory view of continuous functions and homemorphisms
>Notice the similar behavior between the definitions and behaviors of the following

>[!idea]+ What is so "standard" about the standard topology on $\mathbb{R}$?
>There are many topologies that can be placed on $\mathbb{R}$, however the standard topology is the *weakest* topology that can be given to $\mathbb{R}$ such that both $+$ and $\cdot$ are continuous operations. If you demand that the field operations are continuous then you obtain the standard topology. If you equip $\mathbb{R}$ with the standard topology it is clear that the field operations are continuous. 
>
>Now suppose $\mathbb{R}$ is equipped with the topology $\mathcal{T}$ and further that under this topology both $+$ and $\cdot$ are continuous. Then the map $T_x:\mathbb{R}\rightarrow \mathbb{R}$ defined by $T_x(y)=x+y$ is continuous. Additionally, observe that $T_{-x}\circ T_x=T_{x}\circ T_{-x}=\mathrm{id}_{\mathbb{R}}$ so $T_x$ is a homeomorphism and $T_x^{-1}=T_{-x}$. Thus, for any open neighborhood $U$ of $0$ in this topology we have that $T_x(U)=\{x+u:u\in U\}$ is a neighborhood of $x$.

