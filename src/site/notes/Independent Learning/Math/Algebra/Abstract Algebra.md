---
{"dg-publish":true,"permalink":"/independent-learning/math/algebra/abstract-algebra/","created":"2025-01-10T20:42:58.590-07:00","updated":"2025-04-15T15:55:47.000-06:00"}
---

# Overview
{ #6abeec}


>[!question] What is Abstract Algebra?

> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Resources
> -  Undergraduate Introduction: ["Contemporary Abstract Algebra" by Gallian](https://books.google.com/books/about/Contemporary_Abstract_Algebra.html?id=JMUaCgAAQBAJ)
> - Standard Reference: ["Abstract Algebra" by Dummit and Foote](https://books.google.com/books/about/Abstract_Algebra.html?id=KJDBQgAACAAJ)
{ #f41867}


> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - Mathematical Maturity
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents


# Groups


>[!def] Group
>Let $G$ be a set and let $\cdot:G\times G \rightarrow G$ be an operation combining two elements of $G$ which satisfies the following
>1. *(Closure):*  If $g,h\in G$ then $g\cdot h=gh\in G$.
>2. *(Associativity):* If $g,h,m\in G$ then $g\cdot(h\cdot m)=(g\cdot h)\cdot m=ghm$ without ambiguity.
>3. *(Identity):* There exists $1\in G$ such that $1g=g1=g$ for all $g\in G$.
>4. *(Inverses):* For all $g\in G$ there exists $g^{-1}\in G$ such that $gg^{-1}=g^{-1}g=1$.
>
>If the operation $\cdot$ satisfies these conditions then we call the pair $(G,\cdot)$ a **group** or just $G$ a group when the binary operation is understood.
>^def-group

Note that in general $gh \neq hg$ however if this holds for all $g,h\in G$ then we say that $G$ is **abelian**.
>[!lemma] 
>The identity and inverse of a group $G$ are unique.

>[!proof]+
>Suppose that there are two identity elements of $G$ called $1$ and $e$. Observe that $1e=1=e$ since for any $g\in G$ we have that $1g=g1=g$ and $eg=ge=g$ i.e. both are the identity, thus the identities coincide making the identity unique. Similarly, suppose that for $g\in G$ both $m,n\in G$ are its inverse that is $gm=mg=1=gn=ng$. Therefore, $mgn=(1)n=m(1)$ so $n=m$ and inverses are unique.


>[!def] Monoid
>A **monoid** is a set $M$ with a binary operation $\cdot$ such that the following holds:
>1. *(Closure):* If $g,h\in M$ then $g\cdot h=gh\in M$
>2. *(Associativity):* If $g,h,m\in M$ then $g\cdot(h\cdot m)=(g\cdot h)\cdot m=ghm$
>3. *(Identity):* There exists $1\in M$ such that $1g=g1=g$ for all $g\in M$
>
>That is a monoid is a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|group]] without an inverse for every element.
>^def-monoid

>[!def] Homomorphism
>Let $(G,\cdot)$ and $(H,\star)$ be [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|goups]]. A function $\varphi:G\rightarrow H$ is called a **homomorphism** if for all $a,b\in G$ we have that
>$$
>\varphi(a\cdot b)=\varphi(a)\star \varphi(b)
>$$
>^def-homomorphism

>[!def] Isomorphism
>Let $G$ and $H$ be [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|groups]]. A function $\varphi:G\rightarrow H$ is a called an **isomorphism** if $\varphi$ is a bijection and both $\varphi$ and $\varphi^{-1}$ are [[Independent Learning/Math/Algebra/Abstract Algebra#^def-homomorphism\|homomorphisms]].


>[!def] Ring
>A **ring** is a set $R$ with two binary operations $+$ and $\cdot$ such that $(R,+)$ is an [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|abelian group]] and $(R,\cdot)$ is a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-monoid\|monoid]] where multiplication is distributive that is for all $a,b,c\in R$ we have that
>$$
>\begin{align}
a\cdot(b+c)&=(a\cdot b)+(a\cdot c)\\ \\
(b+c)\cdot a &= (b\cdot a)+(c\cdot a)
\end{align}
>$$
>^def-ring

>[!def] Field
>A **field** $\mathbb{F}$ is a
>^def-field



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/independent-learning/math/algebra/linear-algebra/#def-vector-space" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



>[!def] Vector Space
>A **vector space** $V$ over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]]  $\mathbb{F}$ is a set together with an addition operation $+:V\times V\rightarrow V$ and a scalar multiplication operation $\cdot : V\times \mathbb{F}\rightarrow V$ that satisfies the following properties for all $u,v,w\in V$ and $a,b\in \mathbb{F}$:
>1. *(Associativity of $+$):* $u+(v+w)=(u+v+w)$.
>2. *(Commutativity of $+$):* $u+v=v+u$.
>3. *(Identity of $+$):* There exists $0\in V$ such that $0+v=v+0=v$.
>4. *(Inversion of $+$):* For all $v\in V$ there exists $-v\in V$ such that $v+(-v)=(-v)+v=0$.
>5. *(Compatibility with $\cdot$):* $a\cdot(b \cdot v)=(ab)\cdot v=abv$.
>6. *(Identity of $\cdot$):* $1v=v$ where $1$ is the identity of the field $\mathbb{F}$.
>7. *(Distributivity of $\cdot$):* $a(v+u)=av+au$ and $(a+b)v=av+bv$.
>

</div></div>


>[!def] Module
> Let $R$ be a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-ring\|ring]] (not necessarily commutative nor with $1$, but often so). A **left $R$-module** or a **left module over $R$** is an [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|abelian group]] $(M,+)$ and a left action of $R$ on $M$ (a map $R\times M\to M$) denoted $rm$ for $r\in R,m\in M$ that is bilinear, i.e.
> 1. $(r+s)m=rm+sm$
> 2. $(rs)m=r(sm)$
> 3. $r(m+n)=rm+rn$
> 4. $1m=m$ when $R$ has a unit.
>^def-module

# Advanced Concepts / Misc


> [!def] Heisenberg Group $H$
> The **Heisenberg group** $H$, named after Werner Heisenberg, is the [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|group]] of $3\times 3$ upper triangular matrices of the form
> 
>
{ #def-Heisenberg-group}


