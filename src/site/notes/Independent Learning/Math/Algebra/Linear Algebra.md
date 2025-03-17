---
{"dg-publish":true,"permalink":"/independent-learning/math/algebra/linear-algebra/","created":"2024-12-24T18:00:26.115-07:00","updated":"2025-03-14T20:49:22.000-06:00"}
---

# Overview

>[!question] What is linear algebra?


> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Resources
> - While not ideal for a first pass, [Sheldon Axler's "Linear Algebra Done Right"](https://linear.axler.net/) is one of the best books to learn abstract linear algebra 

> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - Mathematical Maturity
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

# Vector Spaces

>[!def] Vector Space
>A **vector space** $V$ over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]]  $\mathbb{F}$ is a set together with an addition operation $+:V\times V\rightarrow V$ and a scalar multiplication operation $\cdot : V\times \mathbb{F}\rightarrow V$ that satisfies the following properties for all $u,v,w\in V$ and $a,b\in \mathbb{F}$:
>1. *(Associativity of $+$):* $u+(v+w)=(u+v+w)$.
>2. *(Commutativity of $+$):* $u+v=v+u$.
>3. *(Identity of $+$):* There exists $0\in V$ such that $0+v=v+0=v$.
>4. *(Inversion of $+$):* For all $v\in V$ there exists $-v\in V$ such that $v+(-v)=(-v)+v=0$.
>5. *(Compatibility with $\cdot$):* $a\cdot(b \cdot v)=(ab)\cdot v=abv$.
>6. *(Identity of $\cdot$):* $1v=v$ where $1$ is the identity of the field $\mathbb{F}$.
>7. *(Distributivity of $\cdot$):* $a(v+u)=av+au$ and $(a+b)v=av+bv$.
>^def-vector-space

For those comfortable with abstract algebra notice that the first view requirements are the statement that $(V,+)$ forms an [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|abelian group]].


> [!def] Vector Subspace or Linear Subspace
> Let $V$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$ and $W\subset V$ be a subset of $V$. Then $W$ is called a **vector subspace** or a **linear subspace** if $W$ is a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] under the operations of $V$. That is, if linear combinations of elements of $W$ remain in $W$.
>
{ #def-vector-subspace}



> [!def] Linear map
> A **linear map** $T:V\to W$ is a map between [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector spaces]] $V,W$ over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$ such that for all $u,v\in V$ and $a,b\in \mathbb{F}$, $T(av+bu)=aT(v)+bT(u)$ holds.
>
{ #def-linear-map}


>[!def] Inner Product Space
>Let $V$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] over the [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$.  An **Inner product** of $V$ is a map $\langle \cdot,\cdot \rangle:V\times V\to \mathbb{F}$ such that for all $\alpha,\beta\in \mathbb{F}$ and $x,y,z\in V$ the following is satisfied:
>1. $\langle \alpha v+\beta y,z\rangle=\alpha \langle v,z\rangle+\beta \langle y,z\rangle$
>2. $\langle x,\alpha y+ \beta z,\rangle=\overline{\alpha}\langle x,y\rangle+\overline{\beta}\langle x,z\rangle$
>3. $\langle x,x\rangle\geq 0$
>4. $\langle x,y\rangle=\overline{\langle y,x\rangle}$
>5. $\langle x,x\rangle=0 \Rightarrow x=0$
>
>Note: If condition 5. is dropped then we have a **semi-inner product**
>^def-inner-product-space


> [!def] Normed Space
> A **normed space** is a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] $V$ over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$ together with a map $\left \lVert \cdot \right \rVert_{}:V\to \mathbb{R}$ such that the following properties hold for all $v,w\in V$ and $\lambda \in \mathbb{F}$:
> 1. Non-negativity: $\left \lVert v \right \rVert_{}\ge 0$.
> 2. Positive definiteness: $\left \lVert v \right \rVert_{}=0 \Leftrightarrow v=0$
> 3. Absolute homogeneity: $\left \lVert \lambda v \right \rVert_{}=|\lambda|\left \lVert v \right \rVert_{}$
> 4. Triangle Inequality: $\left \lVert v+w \right \rVert_{} \le \left \lVert v \right \rVert_{} + \left \lVert w \right \rVert_{}$.
>    
>   (Notice that if we define the map $d:V\times V \to \mathbb{R}$ by $d(v,w)=\left \lVert v-w \right \rVert_{}$ we have a [[Independent Learning/Math/Analysis/Real Analysis#^def-metric-space\|metric]]).
>^def-norm-space


> [!def] Quotient Space
> Let $V$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$ and $N$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-subspace\|subspace]] of $V$. We define an equivalence relation $\sim$ on $V$ by $x\sim y$ iff $x-y\in N$, that is, two vectors are equivalent if one can be obtained from the other by adding an element from $N$. The equivalence class of $x$ or coset of $x$ denoted $[x]$ is defined as: $[x]=\{x+n:n\in N\}=x+N$. The **quotient space** $V / N$ is defined as $V / \sim$ or the set of all equivalence classes induced by $\sim$ on $V$ with the natural vector space operations on equivalence sets defined as:
> 1. $\alpha [x]=[\alpha x]$ for all $\alpha \in \mathbb{F}$ and $x\in V$
> 2. $[x]+[y]=[x+y]$ for all $x,y\in V$.
>^def-quotient-space
