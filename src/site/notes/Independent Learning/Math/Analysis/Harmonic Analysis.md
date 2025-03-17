---
{"dg-publish":true,"permalink":"/independent-learning/math/analysis/harmonic-analysis/","created":"2024-12-25T11:49:33.675-07:00","updated":"2025-03-14T20:49:09.000-06:00"}
---

# Overview

>[!question] What is harmonic analysis?
>Harmonic analysis studies generalizations of the Fourier transform and ways of decomposing functions in terms of their fundamental symmetries.


> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Papers
> - For an advanced undergraduate to first-year graduate introduction see ["A First Course in Harmonic Analysis" by Deitmar](https://link.springer.com/book/10.1007/0-387-27561-4)
> - For a more advanced introduction see ["Principles of Harmonic Analysis" by Deitmar and Echterhoff](https://link.springer.com/book/10.1007/978-3-319-05792-7)


> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - [[Independent Learning/Math/Analysis/Real Analysis\|Real Analysis]]
> - Measure Theory
> - [[Independent Learning/Math/Algebra/Abstract Algebra\|Abstract Algebra]]
> - [[Independent Learning/Math/Algebra/Linear Algebra\|Linear Algebra]]
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

# Review of Fourier Series and Fourier Transform


# Fourier Transform Over Discrete Abelian Groups
Here we consider functions $f\in l^{2}(G)=\left\{ f:G\to\mathbb{C}~:~ \sum_{g\in G}^{} |f(g)|^{2}<\infty \right\}$ where $G$ is a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|discrete abelian group]]. Let $|G|=n$ then from basic abstract algebra we have that $G\cong \mathbb{Z}_{n}$. So if suffices to consider the space $l^{2}(\mathbb{Z}_{n})$.


> [!def] Discrete Dual Group to $G$
> The **Dual Group** $\hat{G}$ of a discrete [[Independent Learning/Math/Algebra/Abstract Algebra#^def-group\|group]] $G$ is defined as the set of [[Independent Learning/Math/Topology and Geometry/Topology#^def-continuous-function\|continuous]] [[Independent Learning/Math/Algebra/Abstract Algebra#^def-homomorphism\|homomorphisms]] from $G$ to $\mathbb{C}$. That is $\hat{G}=\mathrm{Hom}(G,\mathbb{C})=\{\chi:G\to\mathbb{C}~:~\chi\text{ continuous homomorphism}\}$ or the set of [[Independent Learning/Math/Topology and Geometry/Topology#^def-continuous-function\|continuous]] [[Independent Learning/Math/Algebra/Representation Theory#^def-character\|characters]] of $G$.
>
{ #def-discrete-dual-group}







# Fourier Transform Over Locally Compact Abelian (LCA) Groups




> [!thm] Peter-Weyl Theorem
> Let $\tau\ncong \gamma$ be two non-isomorphic irreducible unitary representations of a compact group $G$. To each Hilbert space $V_{\tau}$ associated to the representation $\tau$ fix an orthonormal basis $\{e_{i}\}_{i=1}^{n}$ and let $\tau_{i,j}:G\rightarrow \mathbb{C}$ denote the $(i,j)$-th matrix coefficient associated to an element $g$, i.e. $\tau_{i,j}(g)=\langle \tau(g)e_{i},e_{j}\rangle$. Then $\{\sqrt{\dim(V_{\tau})}\tau_{i,j}\}_{\tau,i,j}$ forms an orthonormal basis for the space $L^{2}(G)$ when equipped the inner product $\langle f,h\rangle=\int_{G}f(g)\overline{h(g)}dg$ where $dg$ denotes the Haar measure on $G$. Additionally, we have that
> $$
L^{2}(G)\cong \widehat{\bigoplus}_{\tau\in \hat{G}_{\mathrm{fin}}}\mathrm{End}(V_{\tau})
>$$
>where $\widehat{\bigoplus}$ denotes the Hilbert space completion and $\hat{G}_{\mathrm{fin}}$ denotes the set of non-isomorphic irreducible unitary representations of $G$. The image of $f\in L^{1}(G)\subset L^{2}(G)$ under this isomorphism is given by
>$$
\begin{align}
\sum_{\tau \in \hat{G}_{\mathrm{fin}}}^{}\tau(f) \quad \tau(f)=\int_{G}f(g)\tau(g)dg.
\end{align}
>$$
>^thm-peter-weyl
