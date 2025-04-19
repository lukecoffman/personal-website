---
{"dg-publish":true,"permalink":"/independent-learning/information-and-coding-theory/introduction-to-classical-information-theory/","created":"2025-02-04T08:27:56.742-07:00","updated":"2025-04-19T17:08:21.037-06:00"}
---

# Overview
> [!question] What is Information Theory?
> The word "information" is rather difficult to define as it acts a place holder for *things* that can be communicated, learned, stored, destroyed, and every action in between. Thus a theory of information is necessarily non-descriptive about what the information being considered *is* as it must capture all of these concepts. While at face value this generality may seem to be a downfall but it is also information theory's greatest strength as even in this generality we can make powerful statements about information. 

> [!abstract] Summary of Topics Covered
> Contents

> [!info] Recommended Readings and Resources
> 1. For a conceptual and philosophical introduction to the field see ["An Introduction to Information Theory: Symbols, Signals and Noise" by Pierce](https://books.google.com/books/about/An_Introduction_to_Information_Theory.html?id=eKvhiI2ogwEC)
> 2. For a concrete and standard reference for the topic see ["Elements of Information Theory" by Cover and Thomas](https://books.google.com/books/about/Elements_of_Information_Theory.html?id=VWq5GG6ycxMC)
> 3. [Claude Shannon](https://en.wikipedia.org/wiki/Claude_Shannon#) is considered the father of information theory or the age of information with his seminal paper ["A Mathematical Theory of Communication"](https://people.math.harvard.edu/~ctm/home/text/others/shannon/entropy/entropy.pdf) largely considered the official founding of the field of information theory as it cemented the mathematical framework and language for the theory.

> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - Introductory Probability Theory
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> At this time I largely focus on placing all of the relevant definitions and materials in one place. The intent is for the readability of this document to increase over time, but at the end of a day to provide one place for myself and the curious reader to outline different ideas while providing background materials for further exploration. This is to say, this is a *living document* subject to change, growth, and inaccuracies which I request are kindly given in the same respect as those with people.

These notes largely follow that of Cover and Thomas as they are the standard reference for fundamental information theory concepts with my own personal context and interpretations. 

# Entropy, Relative Entropy, and Mutual Information


> [!def] Surprisal
> The **surprisal** of a event $x$ occurring with probability $p(x)$ is defined as
> $$
\begin{align}
s(x) = \log \left( \frac{1}{p(x)} \right).
\end{align}
>$$
>^def-surprisal

Surprisal attempts to quantify how "surprised" we are to see a specific event. For instance, if we lived on a planet that has perpetual rain then the event of seeing rain tomorrow $x$ should be of probability $p(x)=1$ leading to no surprisal $s(x)=0$. However, if we lived on the desert planet Arrakis from *Dune* where it does not rain meaning $p(x)=0$ we would be *infinitely* surprised to see rain $s(x)=\infty$. 

> [!def] Entropy
> The **entropy** $H(X)$ of a discrete random variable $X$ which takes values $x$ in the alphabet $\mathcal{X}$ with probability $p(x)$ is defined as
> $$
\begin{align}
H(X) = -\sum_{x\in \mathcal{X}}^{}p(x)\log p(x).
\end{align}
>$$
>^def-entropy

Entropy is the fundamental quantity of interest in information theory as it quantifies the *information content* of a random variable. Notice that entropy is the *expected surprisal* from a random variable $X$ i.e. $\mathbb{E}_{X\sim p(x)}[s(X)]=H(X)$. Since $0\le p(x) \le 1$ it follows that $-\log p(x)\ge 0$ such that $H(X)\geq 0$.

> [!info] Remark
> Its worth noticing that the definition of [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-entropy\|entropy]] captures the first moment of the [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-surprisal\|surprisal]] random variable or $s(X)=-\log p(X)$. Thus, we could think about *information fluctuations* by looking at $\mathrm{Var}[s(X)]$ or higher order moments / cumulants. It could be interesting to use these ideas to study the [[Independent Learning/Classical Probability/Moments, Cumulants, Wick's Theorem, and the Central Limit Theorem#^def-characteristic-function-moment-generating-function\|moment generating function]] or something similar of $s(X)$. (Some way to think about information decompositions is interesting).

> [!def] Joint Entropy
> The **joint entropy** of a pair of discrete random variables $(X,Y)$ with joint distribution $p(x,y)$ is defined as
> $$
\begin{align}
H(X,Y) = - \sum_{x\in \mathcal{X}, y\in \mathcal{Y}}^{} p(x,y) \log p(x,y).
\end{align}
>$$
>^def-joint-entropy

Realistically, this is just a special case of the regular definition of entropy but for a pair of random variables. However, it is useful to write it in this form as it naturally leads to ideas of *conditional entropy* and the *chain rule* as we will now see.

> [!def] Conditional Entropy
> If $(X,Y)\sim p(x,y)$ then the **conditional entropy** $H(Y|X)$ is defined as
> $$
\begin{align}
H(Y|X) = \sum_{x\in \mathcal{X}}^{} p(x)H(Y|X=x) = -\sum_{x\in \mathcal{X}}^{} p(x)\sum_{y\in \mathcal{Y}}^{} p(y|x)\log p(y|x) = -\mathbb{E}[\log p(Y|X)].
\end{align}
>$$
>^def-conditional-entropy

[[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-conditional-entropy\|Conditional Entropy]] quantifies the expected amount of information in $Y$ given we observe an outcome from $X$ (as seen in the first equality of the definition). One would expect that the *total* average information content of $X$ and $Y$ is the amount of information contained in $Y$ given we have information about $X$ plus the information content of $X$ itself. This intuition is precisely the statement of the chain rule for entropy:

> [!thm] Chain Rule
> Let $(X,Y)\sim p(x,y)$ then
> $$
\begin{align}
H(X,Y) = H(Y|X) + H(X)
\end{align}
>$$

> [!proof]-
> The simplest way to see this is as follows:
> $$
H(X,Y)=-\mathbb{E}[\log p(X,Y)]=-\mathbb{E}[\log p(Y|X)p(X)]=-\mathbb{E}[\log p(Y|X)]-\mathbb{E}[\log p(X)] = H(Y|X) + H(X)
>$$


> [!def] Relative Entropy or Kullback-Leibler (KL) divergence
> The **relative entropy** or **KL divergence** between two probability distributions $p(x)$ and $q(x)$ is defined as
> $$
\begin{align}
D(p||q) = \sum_{x\in \mathcal{X}}^{} p(x) \log \frac{p(x)}{q(x)} = \mathbb{E}_{p} \log \frac{p(x)}{q(x)}.
\end{align}
>$$
>^def-relative-entropy-KL-divergence


> [!def] Mutual Information
> Let $X$ and $Y$ be two discrete random variable with joint probability mass function $p(x,y)$ and marginal probability mass functions $p(x)$ and $p(y)$ respectively. Then their **mutual information** is defined as
> $$
\begin{align}
I(X;Y) = D(p(x,y)||p(x)p(y)) = \sum_{x\in \mathcal{X} , y\in \mathcal{Y}}^{} p(x,y) \log \frac{p(x,y)}{p(x)p(y)}.
\end{align}
>$$
>^def-mutual-information

Observe that $I(X;Y) = H(Y)-H(Y|X)=H(X)-H(X|Y)=H(X)+H(Y)-H(X,Y)$


# Data Compression


> [!def] Source Code
> A **source code** $C$ for a random variable $X$ is a mapping from $\mathcal{X}$, the range of $X$, to $\mathcal{D}^{*}$, the set of finite-length strings of symbols from the $D$-ary alphabet. Let $C(x)$ denote the codeword corresponding to $x$ and let $l(x)$ denote the length of $C(x)$.
>
{ #def-source-code}



> [!def] Expected Code Length
> The **expected length** $L(C)$ of a [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-source-code\|source code]] $C(x)$ for a random variable $X$ with probability mass function $p(x)$ is given by
> $$
> L(C)=\sum_{x\in \mathcal{X}}^{} p(x)l(x),
> $$
> where $l(x)$ is the length of the codeword associated with $x$.
>
{ #def-expected-code-length}



> [!def] Nonsingular Codes
> A [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-source-code\|code]] is said to be **nonsingular** if every element of the range of $X$ maps into a different string in $\mathcal{D}^{*}$; that is,
> $$
> x\neq x' \implies C(x)\neq C(x').
> $$
>
{ #def-nonsingular-codes}



> [!def] Code Extension
> The **extension** $C^{*}$ of a [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-source-code\|code]] $C$ is the mapping from finite-length strings of $\mathcal{X}$ to finite-length strings of $\mathcal{D}$, defined by
> $$
> C(x_{1}x_{2}\cdots x_{n})=C(x_{1})C(x_{2})\cdots C(x_{n}),
> $$
> where $C(x_{1})C(x_{2})\cdots C(x_{n})$ indicates concatenation of the corresponding codewords.
>
{ #def-code-extension}



> [!def] Uniquely Decodable Codes
> A [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-source-code\|code]] is called **uniquely decodable** if its [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-code-extension\|extension]] is [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-nonsingular-codes\|nonsingular]].
>
{ #def-uniquely-decodable-codes}



> [!def] Prefix or Instantaneous Codes
> A [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-source-code\|code]] is called a **prefix code** or **instantaneous code** if no codeword is a prefix of any other codeword.
>
{ #def-prefix-or-instantaneous-codes}


> [!thm] Kraft Inequality
> For any [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-prefix-or-instantaneous-codes\|instantaneous code]] over an alphabet of size $D$, the [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-source-code\|codeword lengths]] $l_{1},l_{2},\ldots,l_{m}$ must satisfy the inequality
> $$
> \sum_{i=1}^{m} D^{-l_{i}}\le 1.
> $$
> Conversely, given a set of codeword lengths that satisfy this inequality, there exists an instantaneous code with these word lengths.
>
{ #thm-kraft-inequality}


> [!proof]
> Recall that an [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-prefix-or-instantaneous-codes\|instantaneous code]] is a code such that no codeword is a prefix of any other codeword. Thus, if we have a codeword say $10$ then no other codeword can start with $10$ implying the next codeword must be of a form similar to $110$ for instance. To illustrate this concept, consider a $D$-ary tree in which each node has $D$ children. Let the branches of the tree represent the symbols of the codewords. For instance a $2$-ary tree for binary codes is depicted below:
> <?xml version="1.0" encoding="UTF-8" standalone="no"?><!-- Created with Inkscape (http://www.inkscape.org/) --><svg   width="210mm"   height="297mm"   viewBox="0 0 210 297"   version="1.1"   id="svg1"   xmlns="http://www.w3.org/2000/svg"   xmlns:svg="http://www.w3.org/2000/svg">  <defs     id="defs1" />  <g     id="layer1">    <path       style="fill:none;stroke:#000000;stroke-width:0.572607px;stroke-linecap:butt;stroke-linejoin:miter;stroke-dasharray:1.14521, 1.14521;stroke-dashoffset:0;stroke-opacity:1"       d="M 86.689938,80.426706 128.68942,48.075752 164.10523,64.762038"       id="path87" />    <path       style="display:inline;fill:none;stroke:#000000;stroke-width:0.572607px;stroke-linecap:butt;stroke-linejoin:miter;stroke-dasharray:1.14521, 1.14521;stroke-dashoffset:0;stroke-opacity:1"       d="m 129.14346,48.302779 37.00497,-9.194485"       id="path88" />    <path       style="fill:none;stroke:#000000;stroke-width:0.572607px;stroke-linecap:butt;stroke-linejoin:miter;stroke-dasharray:1.14521, 1.14521;stroke-dashoffset:0;stroke-opacity:1"       d="m 163.0836,131.39366 -35.18876,14.18901 33.14555,12.0323"       id="path89" />    <path       style="fill:none;stroke:#000000;stroke-width:0.572607px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1"       d="m 87.825052,166.46892 43.248128,24.85914 33.71311,-13.96197"       id="path90" />    <path       style="fill:none;stroke:#000000;stroke-width:0.572607px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1"       d="m 131.41371,191.32806 33.48607,14.87011"       id="path91" />    <path       style="fill:none;stroke:#000000;stroke-width:0.572607px;stroke-linecap:butt;stroke-linejoin:miter;stroke-dasharray:1.14521, 1.14521;stroke-dashoffset:0;stroke-opacity:1"       d="M 87.030586,80.313196 128.34888,102.10752"       id="path92" />    <path       style="fill:none;stroke:#000000;stroke-width:0.572607px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1"       d="m 127.78133,146.03673 0.22702,-0.34053 -40.183403,21.11326 h -0.113379 l -46.42648,-43.58868 45.63187,-42.680564 0.113641,-0.22702"       id="path86" />    <text       xml:space="preserve"       style="font-size:8.65826px;font-family:sans-serif;stroke-width:0.216457"       x="20.427906"       y="125.36615"       id="text92"><tspan         id="tspan92"         style="stroke-width:0.216457"         x="20.427906"         y="125.36615">Root</tspan></text>    <text       xml:space="preserve"       style="font-size:8.05825px;font-family:sans-serif;stroke-width:0.201456"       x="89.244804"       y="156.64867"       id="text93-9"       transform="scale(0.95949566,1.0422142)"><tspan         id="tspan93-4"         style="stroke-width:0.201456"         x="89.244804"         y="156.64867">1</tspan></text>    <text       xml:space="preserve"       style="font-size:8.05825px;font-family:sans-serif;stroke-width:0.201456"       x="88.678528"       y="85.75843"       id="text93-9-1"       transform="scale(0.95949566,1.0422142)"><tspan         id="tspan93-4-5"         style="stroke-width:0.201456"         x="88.678528"         y="85.75843">0</tspan></text>    <text       xml:space="preserve"       style="font-size:8.05825px;font-family:sans-serif;stroke-width:0.201456"       x="127.85669"       y="135.53839"       id="text93-9-14"       transform="scale(0.95949566,1.0422142)"><tspan         id="tspan93-4-2"         style="stroke-width:0.201456"         x="127.85669"         y="135.53839">10</tspan></text>    <text       xml:space="preserve"       style="font-size:8.05825px;font-family:sans-serif;stroke-width:0.201456"       x="173.96332"       y="171.9682"       id="text93-9-16"       transform="scale(0.95949566,1.0422142)"><tspan         id="tspan93-4-8"         style="stroke-width:0.201456"         x="173.96332"         y="171.9682">110</tspan></text>    <text       xml:space="preserve"       style="font-size:8.05825px;font-family:sans-serif;stroke-width:0.201456"       x="174.45396"       y="199.70782"       id="text93-9-18"       transform="scale(0.95949566,1.0422142)"><tspan         id="tspan93-4-9"         style="stroke-width:0.201456"         x="174.45396"         y="199.70782">111</tspan></text>    <text       xml:space="preserve"       style="font-size:10.5833px;font-family:sans-serif;stroke-width:0.264583"       x="87.37912"       y="149.61264"       id="text93"><tspan         id="tspan93"         style="stroke-width:0.264583"></tspan></text>  </g></svg>
> The $2$ different branches (or in general $D$ branches) from the root note represent the $2$ possible values of the first symbol of the codeword. Each codeword is represented by a leaf on the tree with symbols obtained by tracing from the root to the leaf. The prefix condition on the codewords implies no codeword is an ancestor of any other codeword on the tree. Hence, each codeword eliminates its descendants as possible codewords. So if $0$ is a codeword, no other codeword can start is $0$ and hence is eliminated from the tree.
> 
> Since we have a finite number of codewords, we only need to think about the tree until we reach the maximum length of a codeword $l_{\rm max}$. Some of the nodes at level $l_{\rm max}$ are codewords (since $l_{\rm max}$ itself corresponds to a codeword), some are the descents of codewords (since all shorter codewords must have already appeared in the tree), and some are neither (junk). We can actually find the number of descendants that a codeword has as a function of its length $l_{i}$. For the node corresponding to our codeword at level $l_{i}$ there are $l_{\rm max}-l_{i}$ levels left until we reach the maximum length $l_{\rm max}$. Each additional level generates $D$ more descents from a given node implying that a codeword at level $l_{i}$ has $D^{l_{\rm max}-l_{i}}$ descendants at level $l_{\rm max}$. Due to the prefix condition, each collection of descendants originating from a specific codeword are disjoint. Otherwise, we could trace a descendant to two (or more) codewords which implies that the codewords are descendants of each other violating the prefix condition. In addition to the sets of descendants being disjoint, we also have that the total number of nodes in these sets must be upper bounded by $D^{l_{\rm max}}$.  Hence, summing over all the codewords, we have
> $$
> \sum_{i=1}^{m}D^{l_{\rm max}-l_{i}} \le D^{l_{\rm max}} \implies \sum_{i=1}^{m} D^{l_{i}} \le 1
> $$
> which is the Kraft inequality. Conversely, given any set of codeword lengths $l_{1},\ldots,l_{m}$ that satisfy the Kraft inequality, we can always construct a tree like the one above. Label the first node of depth $l_{1}$ as codeword $1$, and remove its descendants from the tree. Then label the first remaining node of depth $l_{2}$ as codeword 2, and so on. Proceeding this way, we construct a prefix code with the specified $l_{1},\ldots,l_{m}$.

Saturating the [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^thm-kraft-inequality\|Kraft inequality]] will mean we have an *optimal* [[Independent Learning/Information and Coding Theory/Introduction to Classical Information Theory#^def-prefix-or-instantaneous-codes\|prefix code]] as every node at level $l_{\rm max}$ will be the descendant of some codeword and changing the length of any codeword will cause overlap and violate the prefix condition.