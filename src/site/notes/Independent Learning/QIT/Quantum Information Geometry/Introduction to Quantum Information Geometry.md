---
{"dg-publish":true,"permalink":"/independent-learning/qit/quantum-information-geometry/introduction-to-quantum-information-geometry/","created":"2025-02-04T08:27:56.718-07:00","updated":"2025-03-14T20:48:48.550-06:00"}
---

# Overview

> [!question] What is x ?
> Contents

> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Resources
> Some resources for where to start:
> - ["From Classical to Quantum Information Geometry: A Guide for Physicists"](https://arxiv.org/abs/2302.13515)
> - ["Quantum Computation as Geometry"](https://arxiv.org/abs/quant-ph/0603161) 
> - ["Information Geometry and its Applications"](https://link.springer.com/book/10.1007/978-4-431-55978-8)

> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - x
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

The goal of this document is to introduce the basics of quantum information geometry in a way that makes sense to me while trying to not rehash a lot of what has already been said by others.

# From Classical To Quantum Information Geometry: A Guide for Physicists
## Getting our Footing with Some Basics

Consider a collection of $N$ rotors obeying the laws of classical mechanics, with orientations, $\vec{n}$, and angular momenta, $\hat{L}$, in three dimensions given by $x\equiv \{\vec{n}_{1},\ldots,\vec{n}_{n},\hat{L}_{1},\ldots,\hat{L}_{n}\}\in \Omega$  where $\Omega$ is the classical phase space. Since it is intractable (in most cases) to specify the initial conditions for any macroscopic collection of particles, we consider **averages** of the phase-space trajectory $\chi(t)$ either over fixed time intervals or over possible states. Classical systems are thus modelled by a probability distribution $p(x)$ called a **state**. Observable properties are characterized by expectation values
$$
\begin{align}
\langle \Lambda \rangle_{p}=\int p(x)\Lambda(x)~dx
\end{align}
$$
