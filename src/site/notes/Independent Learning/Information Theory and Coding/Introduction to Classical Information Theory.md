---
{"dg-publish":true,"permalink":"/independent-learning/information-theory-and-coding/introduction-to-classical-information-theory/","created":"2025-02-04T08:27:56.742-07:00","updated":"2025-03-13T18:22:35.293-06:00"}
---

> [!abstract] What is Information Theory?
> The word "information" is rather difficult to define as it acts a place holder for *things* that can be communicated, learned, stored, destroyed, and every action in between. Thus a theory of information is necessarily non-descriptive about what the information being considered *is* as it must capture all of these concepts. While at face value this generality may seem to be a downfall but it is also information theory's greatest strength as even in this generality we can make powerful statements about information. 



> [!info] Recommended Readings and Resources
> 1. For a conceptual and philosophical introduction to the field see ["An Introduction to Information Theory: Symbols, Signals and Noise" by Pierce](https://books.google.com/books/about/An_Introduction_to_Information_Theory.html?id=eKvhiI2ogwEC)
> 2. For a concrete and standard reference for the topic see ["Elements of Information Theory" by Cover and Thomas](https://books.google.com/books/about/Elements_of_Information_Theory.html?id=VWq5GG6ycxMC)
> 3. [Claude Shannon](https://en.wikipedia.org/wiki/Claude_Shannon#) is considered the father of information theory or the age of information with his seminal paper ["A Mathematical Theory of Communication"](https://people.math.harvard.edu/~ctm/home/text/others/shannon/entropy/entropy.pdf) largely considered the official founding of the field of information theory as it cemented the mathematical framework and language for the theory.

> [!note] Disclaimer
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
> Its worth noticing that the definition of [[Independent Learning/Information Theory and Coding/Introduction to Classical Information Theory#^def-entropy\|entropy]] captures the first moment of the [[Independent Learning/Information Theory and Coding/Introduction to Classical Information Theory#^def-surprisal\|surprisal]] random variable or $s(X)=-\log p(X)$. Thus, we could think about *information fluctuations* by looking at $\mathrm{Var}[s(X)]$ or higher order moments / cumulants. It could be interesting to use these ideas to study the [[Independent Learning/Classical Probability/Introduction to Moment Generating Function or Characteristic Function#^def-characteristic-function-moment-generating-function\|moment generating function]] or something similar of $s(X)$. (Some way to think about information decompositions is interesting).

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

[[Independent Learning/Information Theory and Coding/Introduction to Classical Information Theory#^def-conditional-entropy\|Conditional Entropy]] quantifies the expected amount of information in $Y$ given we observe an outcome from $X$ (as seen in the first equality of the definition). One would expect that the *total* average information content of $X$ and $Y$ is the amount of information contained in $Y$ given we have information about $X$ plus the information content of $X$ itself. This intuition is precisely the statement of the chain rule for entropy:

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

