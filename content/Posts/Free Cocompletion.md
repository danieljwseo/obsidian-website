---
title: Free Cocompletion of Presheaf Categories
tags:
created:
draft: true
---
This post will be following the motivation and proof of the free cocompletion property for presheaf categories, which uses one of my favourite concept of category theory, Kan Extensions. 

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

The proof is as follows; we already have a functor precomposition by the yoneda embedding,
$$
- \circ Y: [\mathbf{Psh(C)}, \mathbf{E}] \leftrightarrow [\mathbf{C}, \mathbf{E}] : \text{Lan}_{Y}
$$
It is well-known that since $\mathbf{E}$ is cocomplete, there exists a left kan extension which is left adjoint to the precomposition of yoneda embedding, $\text{Lan}_{Y} \dashv -\circ Y$. An adjoint pair can canonically restrict to an equivalence between full subcategories of units and counits being isomorphisms, so it suffices to observe which objects the units and counits are isomorphisms. 
The unit is a natural transformation between the two functors below, 
$$
\text{Lan}_{Y}(F) \circ Y \cong F, \quad F \in [\mathbf{C}, \mathbf{E}]
$$
The unit is always an equivalence as yoneda embedding $Y$ is fully faithful and the pointwise formula for left kan extensions shows initial objects being equivalent to the colimit. Hence the whole category $[\mathbf{C}, \mathbf{E}]$ has unit isomorphism. 
The counit is a natural transformation between the two functors below, 
$$
\text{Lan}_{Y}(F \circ Y) \cong F, \quad F \in [\mathbf{Psh(C)}, \mathbf{E}]
$$
The counit is an equivalence iff $F$ is cocontinuous. The forward direction is obvious as left kan extension is defined by colimits, hence commuting with $F$ and concluding with density. The reverse direction assumes equivalence, i.e., 
$$
\text{colim}_{(C, c) \in \text{el}(X)} F(H_{C}) \cong F(X)
$$
which is a strong condition, but doesn't directly show that $F$ preserves all colimits of any small shapes. But $F$ can be to be cocontinuous as $\text{Lan}_{Y}(G)$ is always a cocontinuous functor when $Y$ is the yoneda embedding and $F$ is equivalent to it. To see this there are multiple methods, the use of ends is the easiest, 
$$
\text{Lan}_{Y}(G)(X) \cong \int^{c \in \mathbf{C}} \mathbf{Psh(C)}(Yc, X) \cdot Gc \cong \int^{c \in \mathbf{C}} Xc \cdot Gc \cong \int^{c \in \mathbf{C}} Xc \times Gc
$$
where the second equivalence holds due to the yoneda lemma and the third is where the tensor/copower is isomorphic to product in the case of Sets. 
Another motivation is for $\text{Lan}_{Y}(G)$ to be cocontinuous, the source is the presheaf category which is a nice behaving category, (i.e., is cocomplete and can actually be seen to satisfy the solution set condition with $F$, take the set as simply $\mathbf{C}$), we could think of GAFT, the $\text{Lan}_{Y}(G)$ should have a left adjoint, which indeed it does, which would also prove it's cocontinuous. 
$$
\begin{align}
(\text{Lan}_{Y}(G)(X), E) \cong \text{lim}_{(C, c) \in \text{el}(X)}(G(C), E) &\cong \text{lim}_{(C, c) \in \text{el}(X)} G^*(D)(C) \\  
&\cong \text{lim}_{(C, c) \in \text{el}(X)} (H_{C}, G^*(D))  \\
&\cong (X, G^*(D))
\end{align}
$$
As such our other desired full subcategory is $\text{Cocont}(\mathbf{Psh(C)}, \mathbf{E})$, the category of cocontinuous functors, which means we naturally obtain an equivalence $- \circ y : \text{Cocont}(\mathbf{Psh(C)}, \mathbf{E}) \rightarrow [\mathbf{C}, \mathbf{E}]$, which is precisely the free cocompletion property. 