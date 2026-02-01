---
title: Cantor-Schroder-Bernstein
created: 2026-01-01
tags:
  - Exercise
draft: false
---
This is a short post which proves the intuitive yet tricky result below. We fully follow the exercise of Leinster which guides through using a fixed point argument, i.e., a special case of the Knaster–Tarski theorem. 

**Theorem (Cantor-Schroder-Bernstein).** Let $A$ and $B$ be sets. If $\lvert A \rvert \leq \lvert B \rvert \leq \lvert A \rvert$ then $A \cong B$. 

***Proof.*** We first prove a lemma. Let $A$ be a set, and $\theta: \mathcal{P}(A) \to \mathcal{P}(A)$ be an order preserving map with respect to inclusion. A fixed point of $\theta$ is an element $S \in \mathcal{P}(A)$ such that $\theta(S) = S$. We claim a fixed point indeed exists. Consider the set below 
$$
S = \bigcup_{R \in \mathcal{P}(A), R \subseteq \theta(R)} R
$$
Note since $\theta$ is order preserving, we have 
$$
\theta(S) = \theta \left( \bigcup_{R \in \mathcal{P}(A), R \subseteq \theta(R)} R \right) \supseteq \bigcup_{R \in \mathcal{P}(A), R \subseteq \theta(R)} \theta(R)
$$
Hence if $s \in S$, then $s \in R$ for some $R$ satisfying the conditions under the union, which implies $s \in \theta(R)$, and by the above, $s \in \theta(S)$, ergo $S \subseteq \theta(S)$. Note however if $s \in \theta(S)$, then since we have concluded $S \subseteq \theta(S)$, we also have $\theta(S) \subseteq \theta^2(S)$ by order preserving, and hence this implies $\theta(S)$ is included under the union defining $S$, i.e., $s \in S$. Thus $\theta(S) = S$, i.e., $S$ is a fixed point. 

Now returning back to the main question, say we have injections $f: A \leftrightarrow B: g$. Consider the map $\theta: \mathcal{P}(A) \to \mathcal{P}(A)$ such that $\theta(S) = A \backslash g(B \backslash f S)$. Clearly the map is order preserving with respect to inclusion. As such by the above lemma, there must exist some fixed point $S$, which implies $g(B \backslash f S) = A \backslash S$. 

Now we can construct a bijection between $A$ and $B$ as follows, $h: A \to B$, 
$$
h(a) = \begin{cases}
f(a) \quad \text{ if } a \in S\\
g^{-1}(a) \quad \text{ if } a \not\in S \iff a \in A \backslash S\\
\end{cases}
\qquad 
i(b) = \begin{cases}
g(b) \quad \text{ if } b \in B \backslash fS \\
f^{-1}(b) \quad \text{ if } b \in fS
\end{cases}
$$
Note these functions can be defined due to the fact that $f, g$ are injections and $g(B \backslash f S) = A \backslash S$. It is not hard to check these are inverses, proving our desired. 

The lemma we proved was the special case of [Knaster-Tarski's theorem](https://en.wikipedia.org/wiki/Knaster%E2%80%93Tarski_theorem). We can replace the power set with any complete lattice, and the theorem claims the set of fixed points themselves is a complete lattice. Our construction of $S$ was actually the construction of the greatest fixed point. The proof of greatest fixed point is essentially the same, and you can find the rest on the link provided. 
