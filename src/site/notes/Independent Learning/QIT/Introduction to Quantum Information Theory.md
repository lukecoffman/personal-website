---
{"dg-publish":true,"permalink":"/independent-learning/qit/introduction-to-quantum-information-theory/","created":"2025-03-14T19:49:35.777-06:00","updated":"2025-04-12T22:10:54.829-06:00"}
---

# Overview

> [!question] What is Quantum Information Theory (QIT)?
> Broadly speaking, quantum information theory (QIT) is the study of information in quantum systems. Namely, how can we learn, protect, destroy, transmit, quantify, sense, compute, or communicate when we are subjected to the rules of quantum mechanics. The "theory" part of QIT is used to emphasize that the interest is on optimal strategies or asymptotic behavior more than how it be done in the lab. QIT is an umbrella term with many subfields and rapidly growing, spanning physics, mathematics, computer science, statistics, information theory, etc.

> [!abstract] Summary of Topics Covered
> This will be an atypical introduction to QIT compare to other standard references or courses one might take. Typically, an undergraduate course will introduce the basics of quantum mechanics then go through non-local games, Deutsch-Jozsa, Grover's, Shor's and maybe quantum error. This was the outline of the undergraduate course I took and some of the references down below. While this is important, I think it undersells the many different areas of QIT and focuses too much on the algorithms side of QIT. Here, I hope to give a sampling of the following topics:
> - Basic quantum mechanics
> - Non-local games (Bell's inequality)
> - Entanglement Distillation
> - Quantum error-correction (Mixed state entanglement and quantum error correction paper)
> - Quantum complexity (Gottesman-Knill Theorem)
> - Quantum learning theory
> - Quantum sensing
>   
> This is *ambitious*, but can be done in a introductory way that will hopefully dispel the sentiment that QIT is just about algorithms.

> [!info] Recommended Readings and Resources
> There are many fantastic texts for QIT or just quantum mechanics
> - For a high school level introduction to quantum mechanics see the [QSYS IQC Primer Text](https://uwaterloo.ca/institute-for-quantum-computing/sites/default/files/uploads/files/mathematics_qm_v23_qsys.pdf)
> - For an undergraduate level introduction see [Richard Kueng's Quantum Computing Notes](https://www.jku.at/fileadmin/gruppen/180/2024_kueng_quantum_computing.pdf)
> - For a more advanced undergraduate text see ["An introduction to Quantum Computing" by Kaye, Laflamme, and Mosca](https://books.google.com/books/about/An_Introduction_to_Quantum_Computing.html?id=gLFQAAAAMAAJ)
> - For the standard advanced undergraduate to graduate introduction see ["Quantum Computation and Quantum Information" by Nielsen and Chuang](https://www.cambridge.org/highereducation/books/quantum-computation-and-quantum-information/01E10196D0A682A6AEFFEA52D53BE9AE)
> - For an advanced graduate introduction see [John Preskill's "Quantum Information and Quantum Computation" notes](https://www.lorentz.leidenuniv.nl/quantumcomputers/literature/preskill_1_to_6.pdf).
> - For a mathematical emphasis on QIT see ["Quantum Information Theory: Mathematical Foundation" by Hiyashi](https://link.springer.com/book/10.1007/978-3-662-49725-8F) 
> - For a quantum Shannon theory focused text see ["Quantum Information Theory" by Wilde](https://www.cambridge.org/core/books/quantum-information-theory/9DC2CA59F45636D4F0F30D971B677623)


> [!warning] Recommended / Assumed Prerequisite Topics
> This note assumes working knowledge of the following topics:
> - [[Independent Learning/Math/Algebra/Linear Algebra\|Linear Algebra]]
> - Basic - Undergraduate Probability Theory
>
> While the text is written to minimize the required background information, at some points, it will be unavoidable. Hopefully, by following a sufficient number of links one can fill these gaps and return to the topic at a later point.

> [!danger] Disclaimer
> I am human, which means there will be errors, inconsistencies, and somethings that are just wrong.


# Basics of Quantum Mechanics

- Introduce notation and intuition according to classical probability theory
- Weird properties of entanglement
- Density matrices by proposing the problem of maximally mixed states

# Non-Local Games
- Bell's inequality
