---
title: Free Cocompletion of Presheaf Categories
tags:
created:
draft: true
---
This post will be following the motivation and proof for the free cocompletion property for presheaf categories, which uses one of my favourite concept of category theory, Kan Extensions. 

**Theorem.** Consider a small category $\mathbf{C}$ and a cocomplete category $\mathbf{E}$. For every functor $F: \mathbf{C} \to \mathbf{E}$, we have a unique cocomplete functor $F_{!}$ from $\mathbf{Psh(C)} \to \mathbf{E}$ such that precomposing with the Yoneda embedding is naturally isomorphic to $F$. 
```tikz 
\usepackage{tikz-cd}

\begin{document}
	\begin{tikzcd}[scale=3]
%% 		    \int F \arrow[rr, "\int \alpha"] \arrow[dr, "p_F"'] & & \int G \arrow[dl, "p_G"]\\
                                                        %% & \cal C & %% %%
	        \mathbf{C} \arrow[d, "Y"] \arrow[dr, "F"] & \\ 
	        \mathbf{Psh(C)} \arrow[r, dashed, "F_{!}"] & \mathbf{E}
	\end{tikzcd}
\end{document}
```

The proof is as follows, note we already have a functor precomposition by the yoneda embedding,
$$
- \circ Y: [\mathbf{Psh(C)}, D] \leftrightarrow [C, D] : \text{Lan}_{Y}
$$
It is well-known that since $D$ is cocomplete, there exists a left kan extension which is left adjoint to the precomposition of yoneda embedding, $(Lan_y \dashv -\circ y)$. An adjoint pair can canonically restrict to an equivalence between subcategories of units and counits being isomorphisms, so it suffices to observe which objects the units and counits are isomorphisms. 
The unit is always an equivalence as yoneda embedding $Y$ is fully faithful, hence $[C, D]$ stays the same
$$
\text{Lan}_{Y}(F) \circ Y \cong F
$$
Counit is equivalence iff $F$ is cocontinuous, forward direction is obvious as Left Kan Extension is defined by colimits and density, reverse is true as $\text{Lan}_{Y}(G)$ is always a cocontinuous functor when $Y$ is yoneda embedding, i.e., preserves colimits. to see this there are multiple methods, the use of ends is the easiest, another motivation is for Lan_Y(G) to be cocontinuous, the source is the presheaf category which is super nice, (i.e. solution set condition), we could think one of our favourite adjoint functor theorems, the Lan_Y(G) should have a left adjoint, which indeed it does, proving its cocontinuous. 
$$
(\text{Lan}_{Y}(G)(X), D) \cong 
$$
$$
\text{colim}_{el(X)} F(H_{A}) \cong F(X)
$$
$$
\text{Lan}_{Y}(F \circ Y) \cong F, \quad F \in [\mathbf{Psh}(C), D]
$$
As such Fix is $\text{Cocont}(Psh(C), D)$, which means we naturally obtain an equivalence $- \circ y : \text{Cocont}(Psh(C), D) \rightarrow [C, D]$, which is precisely the free cocompletion property. 


