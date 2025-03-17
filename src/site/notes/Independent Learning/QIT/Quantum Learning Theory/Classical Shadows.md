---
{"dg-publish":true,"permalink":"/independent-learning/qit/quantum-learning-theory/classical-shadows/","created":"2024-12-31T17:53:37.484-07:00","updated":"2025-03-14T21:43:29.000-06:00"}
---

Foundational paper by Haung, Keung, and Preskill[@huang_predicting_2020-1] that allows for the efficient estimation of many observables (typically that only need a single copy) of a quantum state. 

## Outline of Protocol{ #fcd128}

The goal of classical shadows is to estimate the expectation values $\{o_{i}\}_{i=1}^{M}$of a set $\{\mathcal{O}_{i}\}_{i=1}^{M}$ of observables:
$$
o_{i}(\rho)=\mathrm{Tr}\left[ \mathcal{O}_{i}\rho \right] \quad 1\le i\le M
$$
for an $n$-qubit state $\rho$ ($d=2^{n}$) with as few measurements as possible. To do so, we apply randomized measurements to our state by applying $U\sim \mathcal{U}$ from a fixed ensemble such that the corresponding measurement basis is informationally complete.

1. Apply a random unitary to the state $\rho \mapsto U \rho U^{\dagger}$ and measure in the computational-basis. Once we receive the $n$-bit measurement outcome $\hat{b}\in \{0,1\}^{n}$ we store an efficient classical description of $U^{\dagger}| \hat{b} \rangle \langle \hat{b} |U$ in classical memory.
2. In expectation, this process can be viewed as a quantum channel
$$
\mathbb{E}[U^{\dagger}| \hat{b} \rangle \langle \hat{b} |U] = \mathbb{E}_{U\sim \mathcal{U}} \sum_{b\in \{0,1\}^{n}}^{} \bra{b}U\rho U^{\dagger} \ket{b} U^{\dagger} | b \rangle \langle b |U:=\mathcal{M}(\rho).
$$
3. The tomographic completeness of $\mathcal{U}$ guarantees that there exists a unique $\mathcal{M}^{-1}$ which (while not completely positive) can still be applied to the classically stored measurement outcome to obtain a single classical snapshot
$$
\hat{\rho}=\mathcal{M}^{-1}(U^{\dagger}| \hat{b} \rangle \langle \hat{b} | U)
$$
	of the unknown state $\rho$ from a single measurement. By construction this yields the actual state in expectation $\mathbb{E}[\hat{\rho}]=\rho$.
4. Repeating this procedure $N$ times results in an array of $N$ independent, classical snapshots of $\rho$:
$$
S(\rho;N) = \{\hat{\rho}_{1},\ldots, \hat{\rho}_{N}\}
$$
	which is called the *classical shadow* of $\rho$.

From these classical shadows we can estimate *arbitrary linear functionals* of our state $\rho$. The crucial part is that the sample complexity scales as
$$
N = \mathcal{O} \left( \log(M) \max_{i} \left \lVert \mathcal{O}_{i} \right \rVert_{\mathrm{shadow}}^{2} / \epsilon^{2} \right)
$$
where the shadow norm captures the expressiveness and structure of the given measurement ensemble defined as
$$
\left \lVert \mathcal{O} \right \rVert_{\mathrm{shadow}} = \max_{\sigma} \left( \mathbb{E}_{U\sim \mathcal{U}} \sum_{b\in \{0,1\}^{n}}^{} \bra{b}U\sigma U^{\dagger} | b \rangle \langle b | U \mathcal{M}^{-1}(\mathcal{O})U^{\dagger} \ket{b}\right)^{1/2}
$$
**This expression is wrong as is, there is a square somewhere inside, but I'm too lazy to find this rn**.

## Sample Complexity