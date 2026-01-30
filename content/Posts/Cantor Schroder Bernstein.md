---
title:
created:
tags:
draft: true
---
This is a short post which proves intuitive yet tricky result. We fully follow the exercise of leinster which guides through using a fixed point argument, i.e., a special case of the Knaster–Tarski theorem. 

**Theorem (Cantor-Schroder-Bernstein).** Let $A$ and $B$ be sets. If $\lvert A \rvert \leq \lvert B \rvert \leq \lvert A \rvert$ then $A \cong B$. 

***Proof.*** We first prove a lemma. Let $A$ be a set, and $\theta: \mathcal{P}(A) \to \mathcal{P}(A)$ be an order preserving map with respect to inclusion. A fixed point of $\theta$ is an element $S \in \mathcal{P}(A)$ such that $\theta(S) = S$. Consider the set below 
$$
S = \bigcup_{R \in \mathcal{P}(A), R \subseteq \theta(R)} R
$$
Note since $\theta$ is order preserving, we have 
$$
\theta(S) = \theta \left( \bigcup_{R \in \mathcal{P}(A), R \subseteq \theta(R)} R \right) \supseteq \bigcup_{R \in \mathcal{P}(A), R \subseteq \theta(R)} \theta(R)
$$
Hence if $s \in S$, then $s \in R$ for some $R$ satisfying the conditions under the union, which implies $s \in \theta(R)$, and by the above, $s \in \theta(S)$, ergo $S \subseteq \theta(S)$. 