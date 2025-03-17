---
{"dg-publish":true,"permalink":"/independent-learning/math/algebra/lie-algebras/","created":"2025-01-13T20:01:02.267-07:00","updated":"2025-03-14T20:49:26.000-06:00"}
---

# Overview

> [!question] What are Lie Algebras?
> From a geometric perspective, Lie algebras are the study of the tangent vector space at the identity of a Lie group. From a algebraic perspective Lie algebras are a vector space with a bilinear form called a Lie bracket that allows you to combine two elements of the Lie algebra and obtain a new one.

> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Resources
> These notes will largely follow the following two texts:
> 1. ["Introduction to Lie Algebras" by Erdmann and Wildon](https://link.springer.com/book/10.1007/1-84628-490-2)
> 2. ["Lie Algebras of Finite and Affine Type" by Carter](https://www.cambridge.org/core/books/lie-algebras-of-finite-and-affine-type/4E6820728C16DC1F812860C974FBB4F6)
>    [Course details](https://euclid.colorado.edu/~thiemn/PastCourses/8174F10/course.html)


> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - [[Independent Learning/Math/Algebra/Abstract Algebra\|Abstract Algebra]]
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> Contents

# Introduction


> [!def] Lie Algebra
> A **Lie algebra** over a [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$ is a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] space $\mathfrak{g}$ together with a bilinear map called the **Lie bracket** $[\cdot,\cdot]:\mathfrak{g}\times \mathfrak{g} \to \mathfrak{g}$ which satisfies the following properties:
> 1. $[x,x]=0$ for all $x\in \mathfrak{g}$,
> 2. $[x,[y,z]]+[z,[x,y]]+[y,[z,x]]=0$ for all $x,y,z\in \mathfrak{g}$.
>
> Where the last condition is know as the **Jacobi identity**. Note: the Lie bracket is also referred to as the **commutator** of $x$ and $y$.
>
{ #def-lie-algebra}


> [!prop] Antisymmetry of Lie Bracket
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]], then $[x,y]=-[y,x]$ for all $x,y\in \mathfrak{g}$.
>
{ #prop-antisymmetry-of-Lie-bracket}


> [!proof]-
> Let $x,y\in \mathfrak{g}$, then from the properties of the [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie bracket]] we have that
> $$
[x+y,x+y]=0=[x,x]+[y,y]+[x,y]+[y,x] \implies [x,y]=-[y,x].
>$$

> [!def] General Linear Group $\mathfrak{gl}_{n}(\mathbb{F})$
> **The general linear group** $\mathfrak{gl}_{n}(\mathbb{F})$ as a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] is the set of $n\times n$ matrices over the [[Independent Learning/Math/Algebra/Abstract Algebra#^def-field\|field]] $\mathbb{F}$ with the [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie bracket]] defined as $[A,B]=AB-BA$ for $A,B\in \mathfrak{gl}_{n}(\mathbb{F})$.
>
{ #def-general-linear-group}


In general, if $\mathcal{A}$ is an associative algebra then $(\mathcal{A},[\cdot,\cdot])$ is a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] where $[a,b]=ab-ba$ is the **commutator**.


> [!def] Lie Subalgebras
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] and $\mathfrak{h}\subset \mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-subspace\|vector space]] of $\mathfrak{g}$. Then $\mathfrak{h}$ is a **Lie subalgebra** of $\mathfrak{g}$ if $(\mathfrak{h},[\cdot,\cdot])$ is a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] (i.e. $\mathfrak{h}$ is closed under the Lie bracket).
>^def-lie-subalgebras


> [!def] Derived Algebra
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]]. The **derived algebra** of $\mathfrak{g}$ is $D(\mathfrak{g})=[\mathfrak{g},\mathfrak{g}]=\{[x,y]:x,y\in \mathfrak{g}\}$.
>
{ #def-derived-algebra}



> [!def] Center of a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie Algebra]]
> The **center** of a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] $\mathfrak{g}$ is $\mathcal{Z}(\mathfrak{g})=\{x\in\mathfrak{g}: [x,y]=0, \forall y\in \mathfrak{g}\}$.
>
{ #def-center-of-a-lie-algebra}



> [!def] Ideal of a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]]
> An **ideal** $\mathcal{I}\subset\mathfrak{g}$ of a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] $\mathfrak{g}$, is a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-subspace\|vector space]] such that $[\mathcal{I},\mathfrak{g}]\subset \mathcal{I}$ or $\{[y,x]:y\in \mathcal{I},x\in \mathfrak{g}\}\subset \mathcal{I}$.
>
{ #def-ideal-of-a-lie-algebra}


Its worth noting that all ideals of a Lie algebra are two sided, i.e. $[\mathcal{I},\mathfrak{g}]=[\mathfrak{g},\mathcal{I}]$ due to the [[Independent Learning/Math/Algebra/Lie Algebras#^prop-antisymmetry-of-Lie-bracket\|antisymmetry of the Lie bracket]].


> [!prop] Quotient Lie Algebras
> Let $\mathcal{I}$ be an [[Independent Learning/Math/Algebra/Lie Algebras#^def-ideal-of-a-lie-algebra\|ideal]] of a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] $\mathfrak{g}$. Then $(\mathfrak{g} / \mathcal{I}, [\cdot,\cdot])$ is a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] where the bracket is defined as $[x+\mathcal{I},y+\mathcal{I}]=[x,z]+\mathcal{I}$.
>
{ #prop-quotient-Lie-algebra}


> [!proof]-
> Suppose the above assumptions, then since $\mathcal{I}$ is a subspace of $\mathfrak{g}$ we have that $\mathfrak{g} / \mathcal{I}$ is a [[Independent Learning/Math/Algebra/Linear Algebra#^def-quotient-space\|quotient space]], thus we just need to check that the Lie bracket is well-defined (i.e. the definition is independent of our choice of representatives). Suppose $x+\mathcal{I}=x'+\mathcal{I}$ and $y+\mathcal{I}=y'+\mathcal{I}$, then $x-x',y-y'\in \mathcal{I}$. Therefore,
> $$
[x',y']= [x'+(x-x'),y'+(y-')]=[x,y]+[x-x',y']+[x',y-y']+[x-x',y-y'],
>$$
>where the final three terms are all in $\mathcal{I}$.




## Week 4 of Class

> [!prop] Solvability Properties
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie Algebra]] over $\mathbb{F}$.
> 1. If $\mathfrak{g}$ is solvable then so are all of its subalgebras and homomorphic images
> 2. If $\mathcal{I}$ is a solvable [[Independent Learning/Math/Algebra/Lie Algebras#^def-ideal-of-a-lie-algebra\|ideal]] of $\mathfrak{g}$ such that $\mathfrak{g} / \mathcal{I}$ is solvable then so is $\mathfrak{g}$.
> 3. If $\mathcal{I},\mathcal{J}$  are solvable ideals of $\mathfrak{g}$ then $\mathcal{I}+\mathcal{J}$ is also solvable.
{ #dfb910}


> [!proof] 
> 1. $\mathfrak{h}\subset \mathfrak{g}$ then $\mathfrak{h}^{(i)}\subset \mathfrak{g}^{(i)}$ so result follows. For $\varphi$ homomorphism then $\varphi(\mathfrak{g}^{(i)})=\varphi(\mathfrak{g})^{(i)}$ and the result follows.
> 2. Since any ideal is the kernel of a homomorphism, we use that $(\mathfrak{g} / \mathcal{I})^{(n)}=0$ and take the homomorphism $\varphi:\mathfrak{g} \to \mathfrak{g} / \mathcal{I}$. Then at some point $\mathfrak{g}^{n}\subseteq \mathcal{I}$ result follows.
> 3. Third isomorphism theorem: $(\mathcal{I}+\mathcal{J}) / \mathcal{J} \cong \mathcal{I} / (\mathcal{I} \cap \mathcal{J})$. 

Assume that $\dim \mathfrak{g} < \infty$. By 3. of the above proposition, there exists a unique maximal solvable ideal of $\mathfrak{g}$ called the **radical of $\mathfrak{g}$** denoted $\mathrm{rad}~\mathfrak{g}$.


> [!def] Semisimple Lie algebras
> Let $\mathfrak{g}$ be a finite dimensional [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] such that its $\mathrm{rad}~ \mathfrak{g}=0$. Then $\mathfrak{g}$ is called **semisimple**.
>
{ #def-semisimple-lie-algebra}


> [!example] Semisimple Lie algebras
> - $\mathfrak{sl}_{2}(\mathbb{C})$ is simple and thus $\mathrm{ad}(\mathfrak{sl}_{2(\mathbb{C})})=0$.
> - 0 is semisimple
> - $\mathfrak{g}$ simples $\implies$ $\mathfrak{g}$ semisimple. Note: $\mathfrak{sl}_{2}(\mathbb{C})\oplus \mathfrak{sl}_{2}(\mathbb{C})$ is semisimple but not simple.
> - $\mathfrak{g}$ finite-dimensional $\implies$ $\mathfrak{g} / \mathrm{rad(\mathfrak{g})}$ is SS.

> [!example] Non-semisimple Lie algebras
> - The Heisenberg algebra: $[\mathcal{H},\mathcal{H}]=\mathbb{C}z$ thus $\mathrm{rad}(\mathcal{H})=\mathcal{H}$.


> [!def] Descending Central Series
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]]. **The descending central series** is defined by:
> $\mathfrak{g}^{0}=\mathfrak{g},\mathfrak{g}^{1}=[\mathfrak{g},\mathfrak{g}], \mathfrak{g}^{i}=[\mathfrak{g},\mathfrak{g}^{i-1}]$.
>
{ #def-descending-central-series}



> [!def] Nilpotent Lie Algebras
> A [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] is called **nilpotent** if $\mathfrak{g}^{n}=0$ for some $n \ge 0$.
>
{ #def-nilpotent-lie-algebras}


> [!NOTE] Abelian [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebras]] are [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|nilpotent]].

> [!NOTE] [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|Nilpotent]] [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebras]] are solvable.


> [!prop] [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|Nilpotent Lie Algebras]] Properties
> 1. If $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|nilpotent]], so are all [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-subalgebras\|subalgebras]] and homomorphic images.
> 2. $\mathfrak{g} / \mathcal{Z}(\mathfrak{g})$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|nilpotent]] then so is $\mathfrak{g}$.
> 3. If $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|nilpotent]] and $\mathfrak{g}\neq0$ then $\mathcal{Z}(\mathfrak{g})\neq0$.
>
{ #prop-properties-of-nilpotent-Lie-algebras}


> [!proof] 
> Exercise


> [!NOTE] 
> If $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|nilpotent]] then $\exists n\in \mathbb{N}_{0}$ such that
> $$
ad(x_{1})\circ ad(x_{2})\circ \cdots \circ ad(x_{n})(y)=0
>$$
>for all $x_{1},x_{2},\ldots,x_{n},y\in \mathfrak{g}$. 

In particular, $[ad(x)]^{n}=0$ as an endomorphism in $\mathfrak{gl}(\mathfrak{g})=\mathrm{End}(\mathfrak{g})$.



> [!def] Nilpotent Endomorphism
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] and $x\in \mathfrak{g}$, we say that $x$ is ad-nilpotent if $ad(x)$ is a **nilpotent endomorphism**.
>
{ #def-nilpotent-endomorphism}


Remark: If $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|nilpotent]] then every element of $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|ad-nilpotent]].

Preview:
> [!thm] Engel's Theorem
> Let $\mathfrak{g}$ be a **finite dimensional** [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie Algebra]] such that all elements are [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|ad nilpotent]]. Then $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-lie-algebras\|nilpotent]].


> [!lemma] Lemma: 
> Let  $x\in \mathfrak{gl}(V)$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|nilpotent endomorphism]] then $ad(x)$ is nilpotent.

> [!proof]
> Let $\lambda_{x}: \mathfrak{gl}(V)\to \mathfrak{gl}(V)$ where $\lambda_{x}(y)=x.y$ and $\rho_{x}:\mathfrak{gl}(V)\to \mathfrak{gl}(V)$ where $\rho_{x}(y)=y.x$. Then $\lambda_{x},\rho_{x}$ are nilpotent in $\mathfrak{gl}(\mathfrak{gl}(V))$. Note that $\lambda_{x}\circ \rho_{x}=\rho_{x}\circ \lambda_{x}$ thus $\lambda_{x}-\rho_{x}$ is nilpotent, therefore $ad(x)=\lambda_{x}-\rho_{x}$ is nilpotent. 

> [!NOTE] Remark
(Note: $ad(x)$ nilpotent and $x\in \mathfrak{gl}(V)$ does NOT imply that $x$ is nilpotent. Take $x=\mathrm{Id}$.)


> [!thm] Title
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-subalgebras\|subalgebra]] of $\mathfrak{gl}(V)$ where $V$ is finite dimensional. If $\mathfrak{g}$ consists of nilpotent endomorphism and $V\neq 0$, then there exists a non-zero $v\in V$ such that $\mathfrak{g}.v=0$. That is to say, there exists a simultaneous eigenvector with eigenvalue $0$.

> [!proof]
> We proceed by induction on $\dim \mathfrak{g} = n$. If $\dim \mathfrak{g}=0$ or $\dim \mathfrak{g}=1$ the theorem holds. Suppose that $K$ is a maximal proper [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-subalgebras\|subalgebra]] of $\mathfrak{g}$. Then $K \overset{ad}{\to}\mathfrak{gl}(V)$ and $K\overset{\overline{ad}}{\to}\mathfrak{gl}(\mathfrak{g} / K)$ over the vector space $V=\mathfrak{g} / K$. Because $\dim K<\dim \mathfrak{g}$ by inductive hypothesis there exists $x+K\neq K$ such that $ad(K).(x+K)=0$ in $\mathfrak{g} / K$. ($\mathfrak{g}$ consists of nilpotent endomorphisms $K\subseteq \mathfrak{g}$, thus K consists of nilpotent endomorphism, such that $\overline{ad}(K)\subseteq \mathfrak{gl}(\mathfrak{g} / K)$ consists of nilpotent endomorphisms). Since there exists $x+K\in \mathfrak{g} / K$ such that $ad(K)(x+K)=0$ where $x\not\in K$ we have that $[y,x]\in K$ for all $y\in K$. Therefore $K\subset N_{\mathfrak{g}}(K)=\{z\in \mathfrak{g}:[z,K]\subseteq K\}$ (strict). By maximalty of $K$ we obtain $N_{\mathfrak{g}}=\mathfrak{g}$ therefore $K$ is an ideal. Claim: $\dim \mathfrak{g} / K = 1$ as $\pi:\mathfrak{g} \to \mathfrak{g} / K$ take one dim proper subalg of $\mathfrak{g} / K$, pull back that element, don't get all of $\mathfrak{g}$ which contradicts maximality of $K$ or something. Therefore $\mathfrak{g} \cong K \oplus \mathbb{F}z$ for some non-zero $z\in \mathfrak{g}\setminus K$. By induction, $W=\{v\in V: K.v=0\}$ has a non-zero $v$ ad $\dim K < \dim \mathfrak{g}$. Claim: $W$ is a $\mathfrak{g}$-module $\mathfrak{g}.W\subseteq W$. To see this, take $g\in \mathfrak{g}, w\in W$ must show that $g.w\in W$, then let $k\in K$ therefore $k.g.w=gkw-[\mathfrak{g},k]w$ where $[g,k]\in K$ since $K$ is an ideal, further $gkw=0$ so $gw\in W$. Therefore $(K+\mathbb{F}z)W\subseteq W$. Now that $z$ has an eigenvector with eigenvalue $0$ in $W$ by inductive hypothesis. Call it $0\neq v_{0}\in W$ and $zv_{0}=0$. Therefore, $0\neq v_{0}\in V$ and $\mathfrak{g} v_{0}=0$.


> [!thm] Engel's Theorem
> Let $\mathfrak{g}$ be a finite-dimensional [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] such that all elements are [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|ad-nilpotent]]. Then, $\mathfrak{g}$ is nilpotent.

> [!proof]
> If $\mathfrak{g}=0$ then done, otherwise consider $ad(\mathfrak{g})\subseteq \mathfrak{gl}(\mathfrak{g})$. By assumption, $ad(\mathfrak{g})$ consists of [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|nilpotent endomoprhisms]] and $\mathfrak{g} \neq 0$ with $\dim \mathfrak{g} < \infty$. Thus, there exists $x\neq 0$ with $x\in \mathfrak{g}$ such that $ad(\mathfrak{g})x=0$ therefore $x\in \mathcal{Z}(\mathfrak{g})\neq0$. Now consider $\mathfrak{g} / \mathcal{Z}(\mathfrak{g})$ which consists of [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|ad-nilpotent]] elements and $\dim \mathfrak{g} / \mathcal{Z}(\mathfrak{g})< \dim \mathfrak{g}$ such that by the inductive hypothesis $\mathfrak{g} / \mathcal{Z}(\mathfrak{g}) \cong ad(\mathfrak{g})$ is nilpotent. Therefore, $\mathfrak{g}$ is nilpotent.


> [!def] Flag
> A **flag** for a finite-dimensional [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] $V$ is a chain $0=V_{0} \subset V_{1}\subset V_{1} \subset \cdots \subset V_{n}=V$ of subspaces with $\dim V_{i}=i$. We say that $x\in \mathrm{End}(V)$ leaves the flag invariant if $xV_{i}\subset V_{i}$ for all $i$.
>
{ #def-flag}



> [!corollary] title
> If $\mathfrak{g}$ is a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-subalgebras\|subalgebra]] of $\mathfrak{gl}(\mathfrak{g})$ for $V\neq 0$ and $\dim V< \infty$. Consisting of [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|nilpotent endomorphisms]]. Then, there exist a [[Independent Learning/Math/Algebra/Lie Algebras#^def-flag\|flag]] for $V$ stable under $\mathfrak{g}$ with $xV_{i}\subset V_{i}$ for all $i$ and $x\in \mathfrak{g}$. (**Something about upper triangular matrices**)


> [!proof]
> Grab $0\neq v\in V$ such that $gv=0$. Define $V_{1}=\mathbb{F}v$ and $W=V / V_{1}$. Then $\mathfrak{g}$ acts on $V / V_{1}$ as [[Independent Learning/Math/Algebra/Lie Algebras#^def-nilpotent-endomorphism\|nilpotent endomorphisms]] therefore by inductive hypothesis there exists [[Independent Learning/Math/Algebra/Lie Algebras#^def-flag\|flag]] for $W$ stable under $\mathfrak{g}$ such that $\mathfrak{g} W_{i}\subseteq W_{i-1}$. Then $0=W_{0}\subset W_{1}\subset \cdots \subset W_{m}=W$ and consider $\pi:V \to W = V / V_{1}$ such that $0=V_{0}\subseteq V_{1}\subseteq \pi^{-1}(W_{1})\subseteq \pi^{-1}(W_{2})\subseteq \cdots \subseteq \pi^{-1}(W_{m})=V$.

## Week 5 of Class
For today, $\mathbb{F}$ will be algebraically closed and $char \mathbb{F}=0$.

> [!thm] Finite-dimensional Solvable means common eigenvector
> Let $\mathbb{F}$ be algebraically closed field with $char \mathbb{F}=0$. Let $\mathfrak{g}\subset \mathfrak{gl}(V)$ be a solvable subalgebra with $\dim V <\infty$. If $V\neq 0$, then $V$ contains a common eigenvector for all endomorphisms in $\mathfrak{g}$. (i.e. there exists $0\neq v_{0}\in V$ such that $x.v_{0}=\lambda(x)v_{0}$ for $\lambda:\mathfrak{g} \to \mathbb{F}$ linear).

> [!proof] 
> Induction on $\dim \mathfrak{g} = n$. If $\dim g = 0$ then every non-zero vector is an eigenvector, if $\dim \mathfrak{g} = 1$ then $\mathfrak{g} = \mathbb{F} x$ which admits an eigenvector in $V$ since $\mathbb{F}$ is algebraically closed.
> 
> The idea for the proof is as follows:
> 1. Find an ideal $K$ of codimension $1$ in $\mathfrak{g}$.
> 2. Use induction to find $v\in V$ that is a common eigenvector for $K$.
> 3. $\mathfrak{g}. \{\text{simultaneous eigenvectors for K}\}\subseteq \{\text{simultaneous eigenvectors for K}\}$.
> 4. Find an eigenvector for $z$ such that $\mathfrak{g} = K\oplus \mathbb{F}z$ in $\{\text{simultaneous eigenvectors for K}\}$.
> 
> Assume $\dim \mathfrak{g} \ge 2$ (since we've covered the lower dim cases already). Now, since $\mathfrak{g}$ is solvable implies that $[\mathfrak{g},\mathfrak{g}]$  is strictly contained in $\mathfrak{g}$. Also $\mathfrak{g} / [\mathfrak{g},\mathfrak{g}]$ is abelian. Any subspace of $\mathfrak{g} / [\mathfrak{g},\mathfrak{g}]$ is an [[Independent Learning/Math/Algebra/Lie Algebras#^def-ideal-of-a-lie-algebra\|ideal]]. Take a subspace $N$ of $\mathfrak{g} / [\mathfrak{g},\mathfrak{g}]$ of codimension $1$. Then for $\pi:\mathfrak{g} \to [\mathfrak{g},\mathfrak{g}]$ we have that $\pi^{-1}(N)=K$ is an ideal of codimension $1$. $[\mathfrak{g},\mathfrak{g}]\subseteq K$ where $\mathfrak{g} / K \cong \mathfrak{g} / [\mathfrak{g},\mathfrak{g}] / (K / [\mathfrak{g},\mathfrak{g}])\cong \mathfrak{g} / [\mathfrak{g},\mathfrak{g}] / N$.
> 
> For 2., $K$ is solvable $0\neq \dim K < \dim \mathfrak{g}$ such that by inductive hypothesis there exists a non-zero element element $0\neq v\in V$ such that for $k\in K$ we have that $kv=\lambda(k)v$ for $\lambda:K\to \mathbb{F}$ linear. Fix this $\lambda:K \to \mathbb{F}$.
> 
> For 3., define $W_{\lambda} = \{w\in V: kw=\lambda(k)w, \forall k\in K\}$ (which we know is non-zero by part 2). Now we must show that $\mathfrak{g}. W \subseteq W$ **this will be done later**.
> 
> For 4. If we prove 3., then $\mathfrak{g} = K \oplus \mathbb{F}z$ (by 1.) for some $0\neq z\in \mathfrak{g}$ then $z\in \mathfrak{gl}(W)$ (by 3.) and there exists $0\neq v_{0}'\in W$ such that $zv_{0}'=\Lambda v_{0}'$ for some $\Lambda \in \mathbb{F}$. Then define $\overline{\lambda}:\mathfrak{g} \to \mathbb{F}$ by $\overline{\lambda}(x)=\lambda(x)$ if $x\in K$ and $\Lambda$ if $x=z$ which we extend linearly. Then $v_{0}'$ is a common eigenvector for $\mathfrak{g}$ and we obtain the desired result.
> 
> Now back to 3. : We want to show that $\mathfrak{g} . W \subseteq W$. Let $w\in W$ and $x\in \mathfrak{g}$ further let $k\in K$ then $k.x.w=x.(k.w)-[x,k].w=x\lambda(k)w-\lambda([x,k])w$. So we really need to show that $\lambda([x,k])=0$ for all $k\in K$ and $x\in \mathfrak{g}$. Fix $0\neq x\in \mathfrak{g}$ and $w\in W$ then $w,x.w, x^{2}.w, x^{3}.w,\ldots, x^{n}.w$ where $n>0$ is the smallest value such that this is **linearly dependent**. Let $W_{i}=\mathrm{span}\{w,x.w,\ldots,x^{i-1}.w\}$ where $W_{0}=0$, $\dim W_{n}=n$, with $W_{n+i}=W_{n}$. Then $x:W_{n}\to W_{n}$. Let $k\in K$ then $k.W_{i}\subseteq W_{i}$ as $k.w=\lambda(k)w \in W_{i}$, then $kxw=\lambda(k)xw-\lambda([x,k])w$,..., $kx^{i}w=\lambda(k)x^{i}w+w'$ with $w'\in W_{i}$ by induction. Thus, $W_{i}$ is $K$-invariant and $\mathrm{Tr}_{W_{n}}\left[k  \right]=n\lambda(k)$ for all $k\in K$ where we are viewing $k$ as an endomorphism acting on the basis in $W_{n}$. In particular, if $k_{1}\in K$ and $x\in \mathfrak{g}$ then $0=\mathrm{Tr}_{W_{n}}\left[ [x,k_{1}]  \right]=n\lambda([x,k_{1}])$ and since $char(\mathbb{F})=0$, $n\neq 0$ we must have $\lambda([x,k_{1}])=0$. Thus, 3. holds for all $x\in \mathfrak{g}$, $k_{1}\in K$ and the Thm is proved (thank god).



> [!corollary] Lie's Theorem
> Let $\mathfrak{g}$ be a solvable $\mathbb{F}$-subalgebra of $\mathfrak{gl}(V)$ with $\overline{\mathbb{F}}=\mathbb{F}$, $char(\mathbb{F})=0$, and $\dim V=n<\infty$. Then $\mathfrak{g}$ stabilizes some [[Independent Learning/Math/Algebra/Lie Algebras#^def-flag\|flag]] in $V$. (In other words, the matrices of elements of $\mathfrak{g}$ relative to a suitable basis of $V$ are all upper triangular).

> [!proof]
> EXERCISE (QUIZ)


> [!NOTE] Fill in notes from Friday 2/14

## Week 6 of Class
Look into Jordan Canonical Form (see Dummit and Foote)

### Review of Jordan Canonical Form
If $x\in \mathrm{End}(V)$ where $\dim V<\infty$ and $\mathbb{F}=\overline{\mathbb{F}}$ (algebraically closed).
$$
[x] = \begin{bmatrix}
J_{a_{1}}  \\
& J_{a_{2}} \\
&& J_{a_{3}}  \\
&&& J_{a_{k}}
\end{bmatrix}
$$
consists of Jordan blocks of the form
$$
[J_{a}] = \begin{bmatrix}
a& 1 & 0 &\cdots &0\\
& a& 1& \cdots \\
&&a & 1& \cdots
\end{bmatrix}
$$
the diagonal part of this matrix is the simisimple part of $J_{a}$ while the other is the nilpotent part of $J_{a}$.


> [!def] Semisimple Endomorphisms
> Let $x\in \mathrm{End}(V)$ we say that $x$ is **semisimple** if the roots of its minimal polynomial over $\mathbb{F}$ are all distinct.

> [!NOTE] Because $\mathbb{F} = \overline{\mathbb{F}}$, $x$ being semisimple iff $x$ diagonalizable.


> [!Note] Facts
> - Two semisimple endomorphisms that commute can be simultaneously diagonalized
> - The sum of two semisimple endomorphisms that commute is again semisimple


> [!prop] (Fact)
> Let $V$ be a finite-dimensional [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] over $\mathbb{F} = \overline{\mathbb{F}}$ and let $x\in \mathrm{End}(V)$. Then,
> 1. There exists *unique* $x_{s},x_{n}\in \mathrm{End}(V)$ satisfying $x=x_{s}+x_{n}$ where $x_{s}$ is semisimple and $x_{n}$ is nilpotent and $x_{s}x_{n}=x_{n}x_{s}$.
> 2. There exists polynomials $p(z),q(z)$ in one indeterminant without constant term such that $x_{s}=p(x)$ and $x_{n}=q(x)$. In particular, $x_{s}$ and $x_{n}$ commute with any endomorphism that commutes with $x$.
> 3. If $A\subset B\subset V$ are [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-subspace\|subspaces]] and $x(B)\subset A$ then $x_{s}(B)\subset A$ and $x_{n}(B)\subset A$. The decomposition $x=x_{s}+x_{n}$ is called the **Jordan-Chevalley cdeomposition** of $x$.

Let's now use this in Lie theory. Let $\mathfrak{g}\subset \mathfrak{gl}(V)$ be a subalgebra with $\mathbb{F} = \overline{\mathbb{F}}$ and $\dim \mathbb{F} <\infty$. If $x\in \mathfrak{g}$ is nilpotent then $ad(x)$ is nilpotent. If $x\in \mathfrak{g}$ is semisimple then $ad(x)$ is semisimple.


> [!lemma] Lemma
> Let $x\in \mathrm{End}(V)$ ($\dim V<\infty, \mathbb{F} = \overline{\mathbb{F}}$) and let $x=x_{s}+x_{n}$ be its Jordan-Chevalley decomposition. Then $ad(x)\in \mathrm{End}(\mathrm{End}(V))$ has decomposition $ad(x)=ad(x_{s})+ad(x_{n})$ is the J-C decomposition of $ad(x)$.

> [!proof]
> By the previous proposition and that the adjoint map is linear we know that it holds that $ad(x)=ad(x_{s})+ad(x_{n})$. $ad(x_{s})$ is semisimple and $ad(x_{n})$ is nilpotent, further using that $ad$ is a Lie algebra homomorphism we have that $[ad(x_{n}),ad(x_{s})]=ad([x_{n},x_{s}])=0$. Finally, uniqueness from the proposition means this is the Jordan-Chevalley decomposition.


> [!lemma] Lemma
> Let $U$ be a finite-dimensional $\mathbb{F}$-algebra (witih $\mathbb{F} = \overline{\mathbb{F}}$). Then, $\mathrm{Der}~U = \{\delta:U\to U:\delta(uv)=u\delta(v)+\delta(u)v\}$ (set of derivations on $U$) contains the semisimple and nilpotent parts of all its elements.

> [!proof]
> If $\delta \in \mathrm{Der}~U$ let $\sigma, \nu$ be its semisimple and nilpotent parts in $\mathrm{End}(U)$. We want to show that $\sigma,\nu \in \mathrm{Der}~U$. Its enough to show that $\sigma \in \mathrm{Der}~U$ (since linear combinations of derivations are derivations). For $\lambda \in \mathbb{F}$ let $U_{\lambda}=\{x\in U : (\delta-\lambda \mathrm{id})^{n}x=0\text{ for some n=n(x)}\}$ (set of generalized eigenvectors) then $U = \bigoplus_{\substack{\lambda \in \mathbb{F} \\ \lambda \text{ eigenvalue for } \delta}} U_{\lambda}$ and $\sigma \lvert_{U_{\lambda}}=\lambda \mathrm{Id}\lvert_{U_{\lambda}}$. Claim: $U_{\lambda}.U_{\mu}\subseteq U_{\lambda + \mu}$. This follows from $(\delta-(\lambda+\mu)\mathrm{Id})^{n}(xy)=\sum_{i=0}^{n} \binom{n}{i} ((\delta-\lambda \mathrm{id})^{n-i}x)((\delta-\mu \mathrm{Id})^{i}y)$. Therefore, if $x\in U_{\lambda},y\in U_{\mu}$ then $xy\in U_{\lambda+\mu}$. On the other hand $(\sigma x)y+x(\sigma y)=(\lambda +\mu)(xy)$. Thus, $\sigma(xy)=(\sigma x)y+x\sigma(y)$ on $U_{\lambda+\mu}$ for all $\lambda+\mu \in \mathbb{F}$. Therefore, $\sigma$ is a derivation on $U_{r}$ for each $r\in \mathbb{F}$ and hence a derivation on $U=\bigoplus_{r\in \mathbb{F}}U_{r}$.

### Cartan's Criteria for Solvability:
Assume that $\mathfrak{g}$ is finite-dimensional over $\mathbb{F}=\overline{\mathbb{F}}$ and $char(\mathbb{F})=0$. 
1. If $[\mathfrak{g},\mathfrak{g}]$ is nilpotent then $\mathfrak{g}$ is solvable.
		$K=[\mathfrak{g},\mathfrak{g}]$ with $\mathfrak{g}^{(i)}\subseteq K^{i-1}$
2. 


> [!lemma] Lemma
> If $[\mathfrak{g},\mathfrak{g}]$ is nilpotent then $\mathfrak{g}$ is solvable.

> [!proof]
> Hint: $K=[\mathfrak{g},\mathfrak{g}]$ with $\mathfrak{g}^{(i)}\subseteq K^{i-1}$.


> [!lemma] Lemma
> Let $\mathbb{F}=\overline{\mathbb{F}}$, $char(\mathbb{F})=0$ and let $V$ be a finite-dimensional [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] with $\dim V<\infty$. Let $A\subset B \subset \mathfrak{gl}(V)$ (subspaces). Let $M = \{x\in \mathfrak{gl}(V):[x,B]\subset A\}$. Suppose that for $x\in M$, then $\mathrm{Tr}\left[ xy \right]=0$ for all $y\in M$ then $x$ is nilpotent.

The proof of this lemma will come later.

> [!thm] Cartan's Criteria for Solvability
> Let $\mathfrak{g}$ be a [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-subalgebras\|subalgebra]] of $\mathfrak{gl}(V)$ ($V$ as in previous Lemma). If $\mathrm{Tr}\left[ xy \right]=0$ for all $x\in [\mathfrak{g},\mathfrak{g}]$, $y\in \mathfrak{g}$ then $\mathfrak{g}$ is solvable.

> [!proof]
> By a previous lemma it is enough to show that $[\mathfrak{g},\mathfrak{g}]$ is nilpotent. We will show that all $x\in [\mathfrak{g},\mathfrak{g}]$ is a nilpotent endomorphism (using the other lemma) and then note this implies that $\forall x\in [\mathfrak{g},\mathfrak{g}]$ is ad-nilpotent which implies by Engel's theorem that $[\mathfrak{g},\mathfrak{g}]$ is nilpotent.
> 
> Take $A=[\mathfrak{g},\mathfrak{g}]$ and $B=\mathfrak{g}$. Then $M=\{x\in \mathfrak{gl}(V):[x,\mathfrak{g}]\subset [\mathfrak{g},\mathfrak{g}]\}$ where we have that $\mathfrak{g}\subset M$. This is still not enough to use Lemma 2. We would like to have that $\mathrm{Tr}\left[ \tilde{x}.z \right]=0$ for all $\tilde{x}\in[\mathfrak{g},\mathfrak{g}]$ and $z\in M$. Since $\tilde{x}\in [\mathfrak{g},\mathfrak{g}]$ there exists $x,y\in \mathfrak{g}$ such that $\mathrm{Tr}\left[ \tilde{x}.z \right]=\mathrm{Tr}\left[ [x,y].z \right]=\mathrm{Tr}\left[ x.[y,z] \right]$ where $[y,z]\in [\mathfrak{g},\mathfrak{g}]$. Therefore we have that $\mathrm{Tr}\left[ x.[y,z] \right]=0$ which by the Lemma gives that $\tilde{x}$ is a nilpotent endomorphism which gives the result.

## Week 7 of Class
FILL IN THESE NOTES



## Week 8 of Class
Recall:
$\mathfrak{g}$ finite dimensional [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] is [[Independent Learning/Math/Algebra/Lie Algebras#^def-semisimple-lie-algebra\|semisimple]] if $rad(\mathfrak{g})=0$.

Claim: $\mathfrak{g}$ finite dimensional is [[Independent Learning/Math/Algebra/Lie Algebras#^def-semisimple-lie-algebra\|ss]] iff $\mathfrak{g}$ has no nonzero Abelian Ideals.
> [!proof]
> If $rad(\mathfrak{g})\neq 0$ then $\mathfrak{g}$ contains an ideal $J$ that is solvable and can be used to produce a nonzero Abelian ideal of $\mathfrak{g}$.
> 
> Exercise: Complete the proof of this claim

> [!thm]
> Let $\mathfrak{g}$ be a finite dimensional [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] over $\mathbb{F}$ with $\mathbb{F} = \overline{\mathbb{F}}$ and $char(\mathbb{F})=0$. Then, $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-semisimple-lie-algebra\|semisimple]] iff its Killing form is non-degenerate.

> [!proof]
> For the forward direction, assume that $rad(\mathfrak{g})=0$. Let $S_{\kappa}$ be the radical of the killing form of $\mathfrak{g}$. Then $S_{\kappa}=\{x\in \mathfrak{g}:\kappa(x,y)=0\quad \forall y\in \mathfrak{g}\}$ where $\kappa(x,y)=\mathrm{Tr}\left[ ad(x).ad(y) \right]$. Claim: $\mathrm{Tr}\left[ ad(x).ad(y) \right]=0$ for all $x\in S_{\kappa}$ and $y\in \mathfrak{g}$. In particular, $\mathrm{Tr}\left[ ad(x).ad(y) \right]=0$ for all $x\in S_{\kappa}$ and $y\in [S_{\kappa},S_{\kappa}]$. By Cartan's criterion for solvability $ad_{\mathfrak{g}}(S_{\kappa})$ is solvable implies that $S_{\kappa}$ is solvable which implies that $S_{\kappa}\subseteq rad(\mathfrak{g})=0$. Therefore, $\kappa$ is nondegenerate.
> 
> For the reverse direction, assume that $S_{\kappa}=0$. To show that $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-semisimple-lie-algebra\|semisimple]] it's enough to show that $\mathfrak{g}$ has no nonzero Abelian ideals. Suppose there is an Abelian ideal $I\subseteq \mathfrak{g}$. Let's show that $I\subseteq S_{\kappa}=0$. Assume that $x\in I$ and $y\in \mathfrak{g}$. Then $ad(x).ad(y):\mathfrak{g}\to \mathfrak{g}\to I$ and $(ad(x).ad(y))^{2}:\mathfrak{g}\to [I,I]=0$. Thus, $ad(x).ad(y)$ is nilpotent (as an endomorphism) and $0=\mathrm{Tr}\left[ ad(x).ad(y) \right]=\kappa(x,y)$ so $I\subseteq S_{\kappa}=0$.


> [!note] Remarks
> 1. $(\Leftarrow)$ still true if $char(\mathbb{F})=p>0$.
> 2. $S_{\kappa}\subset rad(\mathfrak{g})$ but its not necessarily true that $rad(\mathfrak{g})\subset S_{\kappa}$


> [!def] Direct Sums of Ideals
> For a finite dimensional Lie algebra $\mathfrak{g}$ and ideals $I_{1},I_{2},\ldots, I_{t}$ of $\mathfrak{g}$ we say that $\mathfrak{g}$ is the direct sum of $I_{1},\ldots,I_{t}$ if
> $$
\mathfrak{g}=I_{1}\oplus I_{2}\oplus\cdots\oplus I_{t}
>$$
>as vector spaces. This forces $[I_{i},I_{j}]\subseteq I_{i}\cap I_{j}=0$ for all $i\neq j$.


> [!thm]
> Let $\mathfrak{g}$ be a finite dimensional [[Independent Learning/Math/Algebra/Lie Algebras#^def-lie-algebra\|Lie algebra]] over $\mathbb{F}=\overline{\mathbb{F}}$ and $char(\mathbb{F})=0$. Then, if $\mathfrak{g}$ is [[Independent Learning/Math/Algebra/Lie Algebras#^def-semisimple-lie-algebra\|semisimple]] there exists [[Independent Learning/Math/Algebra/Lie Algebras#^def-ideal-of-a-lie-algebra\|ideals]] $I_{1},\ldots,I_{l}$ of $\mathfrak{g}$ that are simple (as Lie algebras themselves) such that
> $$
\mathfrak{g}=I_{1}\oplus\cdots\oplus I_{l}
>$$
>and ever ideal of $\mathfrak{g}$ is one of the $I_{j}$'s. Moreover, the Killing form satisfies $\kappa\lvert_{I_{i}}=\kappa\lvert_{I_{i}\times I_{i}}$.

> [!proof]
> Let $I$ be any [[Independent Learning/Math/Algebra/Lie Algebras#^def-ideal-of-a-lie-algebra\|ideal]] in $\mathfrak{g}$. Then, $I^{\perp}=\{x\in \mathfrak{g}:\kappa(x,y)=0\quad \forall y\in I\}$. Claim: $I^{\perp}$ is also an [[Independent Learning/Math/Algebra/Lie Algebras#^def-ideal-of-a-lie-algebra\|ideal]] of $\mathfrak{g}$. Observe that $\kappa([x,g],y)=\kappa(x,[g,y])=0$. Using Cartan's criteria on $I\cap I^{\perp}$ shows that $I\cap I^{\perp}$ is solvable (Exercise). Then $I\cap I^{\perp}\subset rad(\mathfrak{g})=0$. Therefore, since $\dim I +\dim I^{\perp}=\dim \mathfrak{g}$ we have that $\mathfrak{g}=I\oplus I^{\perp}$. (To see that $\dim I +\dim I^{\perp}=\mathfrak{g}$, since $\kappa:\mathfrak{g}\times\mathfrak{g}\to \mathbb{F}$ is non-degenerate we have that the map $\Phi_{\kappa}:\mathfrak{g}\to \mathfrak{g}^{*}$ where $\Phi_{\kappa}(x)$ sends $y\mapsto\kappa(x,y)$. Then since $\kappa$ is non-degenerate we have that $\ker\Phi_{\kappa}=0$ that is it is injective. Now grab a basis for $\mathfrak{g}$ and find a dual basis to it. Then take the preimage of this basis then it is dual w.r.t. to the Killing form. This then forms a basis for $I^{\perp}$). If $\mathfrak{g}$ is simple we are done. If not, let $I_{1}$ be a minimal non-zero ideal in $\mathfrak{g}$. Then $\mathfrak{g}=I_{1}\oplus I_{1}^{\perp}$where any idea of $I_{1}$ is also an ideal of $\mathfrak{g}$. Thus, $I_{1}$ has no non-zero Abelian ideal and $I_{1}$ is semisimple and $\dim I_{1}<\dim \mathfrak{g}$. By inductive hypothesis $I_{1}$ is the sum of its simple ideals which together with minimality implies $I_{1}$ is simple. Now $I_{1}^{\perp}$ is semisimple and by inductive hypothesis is the direct sum of its simple ideals. Therefore $\mathfrak{g}$ is the direct sum of $I_{1}$ and the simple ideals of $I_{1}^{\perp}$.
> 
> Uniqueness follows by contradiction. Suppose $J$ is a simple ideal of $\mathfrak{g}$ then $J\cap I_{i}\neq 0$ for some $i$ then $J\cap I_{i}=I_{i}=J$. To see this intersection argument, observe that $[J,\mathfrak{g}]\subseteq J$ is an ideal of $J$ but by simplicity of $J$ we must have equality $J=[J,\mathfrak{g}]$. Now decompose $\mathfrak{g}=I_{1}\oplus\cdots\oplus I_{l}$ such that $J=[J,\mathfrak{g}]=[J,I_{1}]\oplus\cdots \oplus[J,I_{l}]$. Again by simplicity only one of these can be non-zero which gives the result.


> [!cor] :
> If $\mathfrak{g}$ is semisimple, finite-dimensional over $\mathbb{F}=\overline{\mathbb{F}}$ and $char(\mathbb{F})=0$, then $\mathfrak{g}=[\mathfrak{g},\mathfrak{g}]$ and all of its ideals and homomorphic images are semisimple. Morever, ever ideal of $\mathfrak{g}$ is the sum of certain simple ideals of $\mathfrak{g}$.


In general, $ad(\mathfrak{g})$ is an ideal in $Der(\mathfrak{g})$. It turns out that the non-degeneracy of the Killing form implies that $\mathfrak{g}$ is semisimple and that $ad(\mathfrak{g})\cong Der(\mathfrak{g})$. "$\mathfrak{g}$ semisimple implies that all derivations are inner". Exercise.

### Complete Reducibility of Representations

> [!info] Idea
> $\mathfrak{g}$ is semisimple finite-dimensional over $\mathbb{F}=\overline{\mathbb{F}}$ with $char(\mathbb{F})=0$. Study representation theory of $\mathfrak{sl}(2,\mathbb{F})$ and use it to study any semisimple Lie algebra $\mathfrak{g}$.

Recall:

> [!def] $\mathfrak{g}$-Module $V$
> A $\mathfrak{g}$-module $V$ is a [[Independent Learning/Math/Algebra/Linear Algebra#^def-vector-space\|vector space]] together with a map $\mathfrak{g} \times V \to V$ that is bilinear and such that $([x,y]).v=x.(y.v)-y.(x.v)$.


> [!def] A representation of $\mathfrak{g}$
> A representation $(V,\rho)$ of $\mathfrak{g}$ is a homomorphism $\rho:\mathfrak{g} \to \mathfrak{gl}(V)$.


> [!def] Irreducible $\mathfrak{g}$-modules
> A $\mathfrak{g}$-module $V$ is irreducible if it admits precisely 2 $\mathfrak{g}$-modules: $V$ and $0$.


> [!def] Completely Reducible
> A $\mathfrak{g}$-module $V$ is said to be **completely reducible** if it is a direct sum of irreducible $\mathfrak{g}$-modules.


> [!def] $\mathfrak{g}$-Module Homomorphism
> A linear map $\varphi:V\to W$ between $\mathfrak{g}$-modules is a $\mathfrak{g}$-module homomorphism $\varphi(x.v)=x.\varphi(v)$. (Same Lie algebra)


> [!lemma] Schur's Lemma
> Let $\mathfrak{g}$ be a finite dimensional Lie algebra over $\mathbb{F}=\overline{\mathbb{F}}$ and let $\rho:\mathfrak{g} \to \mathfrak{gl}(V)$ be an irreducible finite dimensional representation. Then, the only endomorphisms in $\mathfrak{gl}(V)$ commuting with all $\rho(x)$ are proportional to the identity.

> [!proof]
> Let $T\in \mathfrak{gl}(V)$ such that $T\rho(x)=\rho(x)T$ for all $x\in \mathfrak{g}$ (this exists since identity map would work). Then $T(\rho(x).v)=\rho(x).(T(v))$. Let $w\neq 0$ be an eigenvector for $T$ with eigenvalue $\mu\in \mathbb{F}$ (which exists because the field is closed). Now consider $E_{\mu}=\{v\in V: Tv=\mu v\}$. Then $T\rho(x)w=\mu \rho(x)T$. Then $E_{\mu}$ is a subrepresentation, but $V$ is irreducible so we have that $E_{\mu}=V$. Thus, $T=\mu \mathrm{Id}_{V}$.

## Week 9 of Class

### New $\mathfrak{g}$-modules from old ones
$V$ $\mathfrak{g}$-module finite-dimensional, then $V^{*}=\mathrm{Hom}_{\mathbb{F}}(V,\mathbb{F})$ is a $\mathfrak{g}$-module. For $x\in \mathfrak{g}$ , $\alpha\in V^{*}$ we define $(x.\alpha)(v)=-\alpha(xv)$. 
> [!exercise] Exercise: Show the following
> $[x,y].\alpha=x.(y.\alpha)-y.(x.\alpha)$.

(Secretly, $U(\mathfrak{g})$ is a Hopf Algebra, if you know, you known, but I don't so)
For $V,W$ $\mathfrak{g}$-modules then $V\otimes W$ is a $\mathfrak{g}$-module with action $x(V\otimes W)=(xV)\otimes W+V\otimes(xW)$. Now for $V^{*}\otimes V\to \mathrm{End}(V)$ where $(\alpha,v)\mapsto \alpha(\cdot) v$ is an isomorphism. Then $\mathrm{End}(V)$ is a $\mathfrak{g}$-module.


> [!exercise] Exercise
> Let $T\in \mathrm{End}(V)$ and $x\in \mathfrak{g}$. Show that $(x.T)(w)=x.(Tw)-T(xw)$.

### The Casimir Element
We used Cartan's criterion to show that if $\mathfrak{g}$ is semisimple finite-dimensional over $\mathbb{F}=\overline{\mathbb{F}}$ with $char(\mathbb{F})=0$ implies that $\kappa$ is nondegenerate $\kappa(x,y)=\mathrm{Tr}\left[ ad(x)\circ ad(y) \right]$. We replace $ad$ with any faithful (1-1) representation of $\mathfrak{g}$, $\phi:\mathfrak{g} \to \mathfrak{gl}(V)$ with $V$ finite-dimensional. Then $\beta_{\phi}(x,y)=\mathrm{Tr}\left[ \phi(x)\phi(y) \right]$ is associate (invariant) and $rad~\beta_{\phi}\subseteq \mathfrak{g}$ is a ideal with $\phi(rad~\beta_{\phi})\cong rad \beta_{\phi}$ is solvable.
> [!exercise] Exercise: Prove that the above assertion is true. 

Remark: Let $\{x_{1},x_{2},\ldots,x_{n}\}$ and $\{y_{1},y_{2},\ldots,y_{n}\}$ be bases for $\mathfrak{g}$ such that $\beta(x_{i},y_{j})=\delta_{ij}$ for $\beta$ nondegenerate symmetric, associative, bilinear. For $x\in \mathfrak{g}$ define $a_{ij}\in \mathbb{F}$ by $[x,x_{i}]=\sum_{j}^{}a_{ij}x_{j}$ and $b_{ij}$ by $[x,y_{i}]=\sum_{j}^{}b_{ij}y_{j}$. Then,
$$
a_{ik}=\sum_{j=1}^{n}a_{ij}\beta(x_{j},y_{k})=\cdots=-b_{ki}.
$$

If $\phi:\mathfrak{g}\to\mathfrak{gl}(V)$ is any finite-dimensional representation of $\mathfrak{g}$ then
$$
C_{\phi}(\beta_{\phi})=C_{\phi}=\sum_{i=1}^{n}\phi(x_{i})\phi(y_{i})
$$
for $\{x_{i}\}$ and $\{y_{i}\}$ dual bases for $\mathfrak{g}$ through $\beta_{\phi}$.

> [!exercise] Exercise:
> 1. $[x,y].z+y.[x,z]=[x,y.z]\in \mathfrak{gl}(V)$
> 2. Since $a_{ik}=-b_{ki}$, one can show that for $x\in\mathfrak{g}$ that $[\phi(x),C_{\phi}]=0$. Conclude that $C_{\phi}$ is a Endomorphism that commutes with $\phi(x)$ for all $x\in \mathfrak{g}$.

$C_{\phi}$ is called the **Casimir Element** of $\phi$.

Summary:
If $\mathfrak{g}$ is semisimple with $char(\mathbb{F})=0$ and $\mathbb{F}=\overline{\mathbb{F}}$, and $\phi:\mathfrak{g}\to \mathfrak{gl}(V)$ faithful representation, $\beta_{\phi}(x,y)=\mathrm{Tr}\left[ \phi(x) \phi(y) \right]$. The Casimir element for $\mathfrak{g}.\phi$ is $C_{\phi}=\sum_{i=1}^{n}\phi(x_{i})\phi(y_{i})$ for $\{x_{i}\}$ and $\{y_{i}\}$ dual bases for $\mathfrak{g}$ through $\beta_{\phi}$ $\mathrm{Tr}\left[ C_{\phi} \right]=\dim \mathfrak{g}$. $\phi$ is irreducible (Schur's Lemma) then $C_{\phi}=\lambda \mathrm{Id}_{V}$ where $\lambda=\dim \mathfrak{g} / \dim V$.

Let $\mathfrak{g}=\mathfrak{sl}(2,\mathbb{F})$ and $V=\mathbb{F}^{2}$ over $\mathbb{F}=\overline{\mathbb{F}}$ and $char(\mathbb{F})=0$. Consider $\phi:\mathfrak{sl}(2,\mathbb{F})\to \mathfrak{gl}(\mathbb{F}^{2})$ via $\phi=\mathrm{id}$. Then $\beta_{\phi}(x,y)=\mathrm{Tr}\left[ xy \right]$ we can find the dual basis to $\{e,h,f\}$ as $\{f,h / 2, e\}$. Such that $C_{\phi}=ef+\frac{h^{2}}{2}+fe= \frac{3}{2} I$ where $\frac{3}{2} =\frac{\dim\mathfrak{g}}{\dim \mathbb{F}^{2}}$.
> [!lemma] :
> Let $\phi:\mathfrak{g}\to \mathfrak{gl}(V)$ be a finite-dimensional representation of a finite-dimensional semisimple Lie algebra $\mathfrak{g}$ over $\mathbb{F}=\overline{\mathbb{F}}$, $char(\mathbb{F})=0$. Then $\phi(g)\subseteq \mathfrak{sl}(V)$. In particular, $\mathfrak{g}$ acts trivially on any dimensional representation.

> [!proof]
> Because $\mathfrak{g}$ is semisimple, we have that $\mathfrak{g}=[\mathfrak{g},\mathfrak{g}]$. Therefore, $\phi(\mathfrak{g})=\phi([\mathfrak{g},\mathfrak{g}])=[\phi(\mathfrak{g}),\phi(\mathfrak{g})]\subset [\mathfrak{gl}(V),\mathfrak{gl}(V)]\subset \mathfrak{sl}(V)$.


> [!thm] Weyl's Theorem
> Let $\mathfrak{g}\neq 0$ be a finite-dimensional semisimple Lie algebra over $\mathbb{F}=\overline{\mathbb{F}}$ and $char(\mathbb{F})=0$. Let $\phi:\mathfrak{g}\to \mathfrak{gl}(V)$ be a representation of $\mathfrak{g}$ that is finite-dimensional. Then, $\phi$ is completely reducible.


> [!exercise]
> Show that $(\phi,V)$ is completely reducible if and only if for any $\mathfrak{g}$-submodule $W\subset V$ there exists a $\mathfrak{g}$-submodule $X$ such that $V=W\oplus X$.


> [!proof]
> We will use the fact that $(\phi,V)$ is completely reducible if and only if for any $\mathfrak{g}$-submodule $W\subset V$ there exists a $\mathfrak{g}$-submodule $X$ such that $V=W\oplus X$.
> 1. Assume first that $V$ has a $\mathfrak{g}$-submodule $W$ of codimension $1$. Then $\mathfrak{g}. V / W = 0$ and $V / W \cong \mathbb{F}$ as a $\mathfrak{g}$-module. Therefore we have a short and exact sequence $0\to W\to V\to \mathbb{F} \to 0$. We want to show that the exact sequence splits, i.e., we want to show that there exists a $\mathfrak{g}$-submodule $Y$ of $V$ isomorphic to $\mathbb{F}$ such that $V=W\oplus Y$.
> 	1.1 Claim: By induction on $\dim W$ we can reduce to the case in which $W$ is irreducible. The idea is that for $W'\subset W$ which is a proper $\mathfrak{g}$-submodule of $W$, we have the short exact sequence $0\to W / W' \to V / W' \to \mathbb{F} \to 0$. By inductive hypothesis there exists $\tilde{W} / W' \subset V /W'$ such that $\tilde{W} / W' \cong \mathbb{F}$ and $V / W'= W /W' \oplus \tilde{W} / W'$. We can build a new short exact sequence with $W'$ and $\tilde{W}$: $0\to W'\to \tilde{W} \to \mathbb{F} \to 0$. Then by inductive hypothesis this short exact sequence splits. Therefore, there exists $X\cong F$ such that $\tilde{W}=W'\oplus X$. Recall $V / W' = W / W'  \oplus \tilde{W} / W'$ which implies $W\cap X=0$ such that $V=W\oplus X$.
> Note that we may assume $\phi:\mathfrak{g}\to\mathfrak{gl}(V)$ is faithful. Let $C_{\phi}$ be the Casimir element for $\{x_{i}\}_{i=1}^{n}$ and $\{y_{i}\}_{i=1}^{n}$ (bases of $\mathfrak{g}$): $C_{\phi}=\sum_{i=1}^{n}\phi(x_{i})\phi(y_{i})$. Since $C_{\phi}$ commutes with $\phi(g)$, $C_{\phi}$ is a $\mathfrak{g}$-module homomorphism
> $$
> C_{\phi}:V\to V \quad C_{\phi}(\phi(x)v)=\phi(x)C_{\phi}(v).
> $$
> Also, note that $C_{\phi}(W)\subset W$ as $C_{\phi}$ is a $\mathfrak{g}$-module homomorphism and $W$ is a $\mathfrak{g}$-module. Further, $\ker C_{\phi}\subset V$ is a $\mathfrak{g}$-submodule. Therefore, $\mathfrak{g}$ acts trivially on $V / W \cong \mathbb{F}$ as $\mathfrak{g}$-modules and $\phi(\mathfrak{g}).V\subset W$. Thus, $C_{\phi}$ has trace 0 on $V / W$ and $C_{\phi}=\lambda \mathrm{Id}_{W}$ on $W$ by Schur's lemma for $\lambda \in \mathbb{F}$. But $\lambda \neq 0$ as $\mathrm{Tr}\left[ C_{\phi} \right]=\dim \mathfrak{g}$ ($\lambda = \dim \mathfrak{g} / \dim W$). Therefore, $\ker C_{\phi}$ is a 1-dimensional $\mathfrak{g}$-submodule. Thus, $V = W\oplus\ker C_{\phi}$. This finishes the proof in the case that $V$ has a codimension $1$-submodule.
> 2.  
