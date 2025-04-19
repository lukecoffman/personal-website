---
{"dg-publish":true,"permalink":"/independent-learning/math/algebra/representation-theory/","created":"2025-01-10T20:43:08.711-07:00","updated":"2025-03-14T20:49:18.850-06:00"}
---

# Overview
>[!question] What is representation theory?
>Groups are on of the most basic structures in mathematics

> [!abstract] Summary of Topics Covered
> Contents

> [!info] Readings and Resources
> For a gentle introduction: ["Representations and Characters of Groups" by James and Liebeck](https://www.cambridge.org/core/books/representations-and-characters-of-groups/9F525E6ACAC7FFADFDBDECE98C115F40)
> Canonical Texts: ["Representation Theory" by Fulton and Harris](https://link.springer.com/book/10.1007/978-1-4612-0979-9)


> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - [[Independent Learning/Math/Algebra/Linear Algebra\|Linear Algebra]]
> - [[Independent Learning/Math/Algebra/Abstract Algebra\|Abstract Algebra]]
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

# Basics of Representation Theory

>[!def] Representation
>Let $G$ be a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|group]] and $V$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]]. Then $\rho:G\rightarrow \mathrm{End}(V)$ is a **representation** if it is a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-homomorphism\|homomorphism]] in the sense that for all $g,h\in G$ we have that $\rho(a)\rho(b)=\rho(ab$). 
>^def-representation

# $\mathbb{C}G$-modules


> [!def] $\mathbb{C}G$-Module
> Let $V$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] over $\mathbb{C}$ and let $G$ be a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|group]]. Then $V$ is a **$\mathbb{C}G$-module** if we can multiply vectors $v\in V$ by group elements $g\in G$ in a way that satisfies the following rules (where $v,u\in V; g,h\in G; \lambda\in \mathbb{C}$):
> 1. $gv\in V$.
> 2. $(gh)v=g(hv)$.
> 3. $1v=v$.
> 4. $g(\lambda v)=\lambda(gv)$.
> 5. $g(u+v)=gu+gv$.
>^def-CG-module



> [!lemma] Schur's Lemma
> Let $V$ and $W$ be irreducible $\mathbb{C}G$ modules.
> 1. If $\varphi:V \rightarrow W$ is a $\mathbb{C}G$-homomorphism, then either $\varphi$ is either a $\mathbb{C}G$, or $\varphi=0$ is the zero map.
> 2. If $\varphi:V\rightarrow W$ is a $\mathbb{C}G$-homomorphism, then $\varphi$ is a scalar multiple of the identity endomorphism $\mathrm{Id}_{V}$.
>
{ #lemma-schur}


> [!proof] 
> 1. Suppose that $\varphi\neq 0$, then there exists $v\in V$ such that $\varphi(v)\neq 0$. Therefore, $\mathrm{Im}(\varphi)\neq \{0\}$. Since $\mathrm{Im}(\varphi)$ is a $\mathbb{C}G$-submodule of $W$ and $W$ is irreducible, we have that $\mathrm{Im}(\varphi)=W$. On the other hand, since $\varphi\neq 0$ we have that $\ker(\varphi)\neq V$. However, $\ker(\varphi)$ is a $\mathbb{C}G$-submodule of $V$ and $V$ is irreducible so $\ker(\varphi)=\{0\}$. Thus, we conclude that $\varphi$ is a $\mathbb{C}G$-isomorphism.
> 2. Since all endomorphisms on a nonzero vector space have an eigenvalue, there exists $\lambda \in \mathbb{C}$ such that $\ker(\varphi-\lambda\mathrm{Id}_{V})\neq \{0\}$. This is a non-zero $\mathbb{C}G$-submodule of $V$ and hence equal to $V$ as $V$ is irreducible. Thus, $(\varphi-\lambda\mathrm{Id}_{V})(v)=0$ for all $v\in V$ leading to the conclusion that $\varphi=\lambda \mathrm{Id}_{V}$.

# Characters of Groups


> [!info] Intuition
> We have already seen that studying [[Independent Learning/Math/Algebra/Representation Theory#^def-representation\|representations]] of [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|groups]] can allow us to use the full toolbox of [[Independent Learning/Math/Algebra/Linear Algebra\|Linear Algebra]] to study properties of the group. However, it can become quite cumbersome to keep track of all $n^{2}$ elements of a representation for a *single* element. It would be nice to study properties of representations and groups using a much more compact encoding. This is what characters give us.


> [!def] Character of a [[Independent Learning/Math/Algebra/Representation Theory#^def-CG-module\|$\mathbb{C}G$-module]] or a [[Independent Learning/Math/Algebra/Representation Theory#^def-representation\|Representation]].
> Let $V$ be a [[Independent Learning/Math/Algebra/Representation Theory#^def-CG-module\|$\mathbb{C}G$-module]] with a basis $\mathcal{B}$. Then the **character** of $V$ is the function $\chi:G\to \mathbb{C}$ defined by $\chi(g)=\mathrm{Tr}\left[ g \right]_{\mathcal{B}}$. In terms of [[Independent Learning/Math/Algebra/Representation Theory#^def-representation\|representations]], let $V$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] over $\mathbb{C}$, $G$ be a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|group]], and $\rho:G\to \mathrm{End}(V)$ be a [[Independent Learning/Math/Algebra/Representation Theory#^def-representation\|representation]] of $G$ on $V$. Then the **character** of $\rho$ is the function $\chi:G\to \mathbb{C}$ defined by $\chi(g)=\mathrm{Tr}\left[ \rho(g) \right]$.
>
{ #def-character}


Notice that characters of $V$ are basis independent as the trace is a basis independent functional.

> [!def] Irreducible and Reducible Characters of a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|Group]].
> We say that $\chi$ is a **character** of $G$ if $\chi$ is the [[Independent Learning/Math/Algebra/Representation Theory#^def-character\|character]] of some $\mathbb{C}G$-module. Further, $\chi$ is an **irreducible** character of $G$ if its the character of an irreducible $\mathbb{C}G$-module or **reducible** if its the character of a reducible $\mathbb{C}G$-module.
>
{ #def-irreducible-and-reducible-characters}


> [!prop] :
> 1. Isomorphic [[Independent Learning/Math/Algebra/Representation Theory#^def-CG-module\|$\mathbb{C}G$-modules]] have the same character.
> 2. For all [[Independent Learning/Math/Algebra/Representation Theory#^def-character\|characters]] $\chi$ of a group $G$, we have that $\chi(x)=\chi(y)$ for all conjugate elements $x$ and $y$ in $G$.

> [!proof]
> Exercise.



> [!prop] Properties of Characters
> Let $\chi$ be the [[Independent Learning/Math/Algebra/Representation Theory#^def-character\|character]] of a [[Independent Learning/Math/Algebra/Representation Theory#^def-CG-module\|$\mathbb{C}G$-module]] $V$. Suppose that $g\in G$ and $g$ has order $m$. Then
> 1. $\chi(1)=\dim V$
> 2. $\chi(g)$ is a sum of $m$-th roots of unity
> 3. $\chi(g^{-1})=\overline{\chi(g)}$
> 4. $\chi(g)$ is a real number if $g$ is conjugate to $g^{-1}$
>^prop-properties-of-characters


> [!proof]
> 







# Advanced Topics / Misc Topics



> [!thm] Schur-Weyl Theorem
> The space $(\mathbb{C}^{d})^{\otimes n}$ can be decomposed according to the irreducible representations of $S_{n}$ and $U(d)$ as
> $$
(\mathbb{C}^{d})^{\otimes n}\cong\bigoplus_{\lambda \vdash n} \mathcal{H}_{\lambda}^{S_{n}}\otimes \mathcal{H}_{\lambda}^{U(d)}
>$$
>where $\lambda$ is a partition of $n$, $\mathcal{H}_{\lambda}^{S_{n}}$ is an irreducible representation of $S_{n}$, and $\mathcal{H}_{\lambda}^{U(d)}$ is an irreducible representation of $U(d)$.
>^thm-Schur-Weyl
