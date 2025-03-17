---
{"dg-publish":true,"permalink":"/independent-learning/math/analysis/functional-analysis/","created":"2024-12-24T17:22:10.441-07:00","updated":"2025-03-14T20:49:14.000-06:00"}
---

# Overview
>[!question] What is functional analysis?
>


> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Papers
> - A standard reference is ["A Course in Functional Analysis" by Conway](https://link.springer.com/book/10.1007/978-1-4757-4383-8)  

> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - [[Independent Learning/Math/Analysis/Real Analysis\|Real Analysis]]
> - Measure Theory
> - [[Independent Learning/Math/Algebra/Linear Algebra\|Linear Algebra]]
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

# Hilbert Spaces

>[!def] Hilbert Space
>Let $\mathcal{H}$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$ with an [[Independent Learning/Math/Algebra/Linear Algebra#^def-inner-product-space\|inner product]] $\langle \cdot,\cdot\rangle$. Then $\mathcal{H}$ is called a **Hilbert space** if it is [[Independent Learning/Math/Analysis/Real Analysis#^def-complete-metric-space\|complete]] with respect to the inducted [[Independent Learning/Math/Analysis/Real Analysis#^def-metric-space\|metric]] $d:\mathcal{H}\times \mathcal{H} \rightarrow \mathbb{R}$ given by $d(x,y)=\left \lVert x-y \right \rVert_{}=\sqrt{\langle x-y,x-y\rangle}$.

# Banach Spaces

>[!def] Banach Space
>Let $(X,\left \lVert \cdot \right \rVert_{})$ be a normed vector space, then if $X$ is complete with respect to the induced metric then $X$ is called a **Banach Space**.
