---
title: Free Cocompletion of Presheaf Categories
tags:
  - KanExtension
  - Cat
created: 2026-01-01
draft: false
---
This post will be following the motivation and proof of the free cocompletion property for presheaf categories using kan extensions, similar ideas and more are discussed on the [nlab](https://ncatlab.org/nlab/show/free+cocompletion)page. 

**Theorem.** Consider a small category $\mathbf{C}$ and a cocomplete category $\mathbf{E}$. For every functor $F: \mathbf{C} \to \mathbf{E}$, we have a unique cocomplete functor $F_{!}$ from $\mathbf{Psh(C)} \to \mathbf{E}$ such that precomposing with the Yoneda embedding is naturally isomorphic to $F$. 
```tikz 
\usepackage{tikz-cd}[row sep=large, column sep=large]

\begin{document}
	\begin{tikzcd}[scale=3]
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
which is a strong condition (cocontinuous on shapes corresponding to category of elements) but isn't obvious to how this directly proves $F$ preserves all colimits of any small shapes. The key observation is $\text{Lan}_{Y}(G)$ is always a cocontinuous functor when $Y$ is the yoneda embedding, which $F$ is equivalent to. To see this there are multiple methods, the use of ends is the easiest, 
$$
\text{Lan}_{Y}(G)(X) \cong \int^{c \in \mathbf{C}} \mathbf{Psh(C)}(Yc, X) \cdot Gc \cong \int^{c \in \mathbf{C}} Xc \cdot Gc \cong \int^{c \in \mathbf{C}} Xc \times Gc
$$
where the second equivalence holds due to the yoneda lemma and the third is where the tensor/copower is isomorphic to product in the case of Sets. Clearly the product by a fixed set has a right adjoint, making it cocontinuous, and coends commute with colimits being defined by colimits, proving our desired. 
Another motivation is following this thought; if $\text{Lan}_{Y}(G)$ is cocontinuous, the source is the presheaf category which is a nice behaving category, (i.e., is cocomplete and can actually be seen to satisfy the solution set condition with $F$, the above "cocontinuous on shapes corresponding to category of elements" is precisely this; take the set as simply $\mathbf{C}$), we could think of GAFT, which should imply the $\text{Lan}_{Y}(G)$ has a left adjoint, proving it's cocontinuous. As such, we display an explicit adjoint as below  
$$
\begin{align}
(\text{Lan}_{Y}(G)(X), E) \cong \text{lim}_{(C, c) \in \text{el}(X)}(G(C), E) &\cong \text{lim}_{(C, c) \in \text{el}(X)} G^*(E)(C) \\  
&\cong \text{lim}_{(C, c) \in \text{el}(X)} (H_{C}, G^*(E))  \\
&\cong (X, G^*(E))
\end{align}
$$
Thus our other desired full subcategory is $\text{Cocont}(\mathbf{Psh(C)}, \mathbf{E})$, the category of cocontinuous functors, which means we naturally obtain an equivalence $- \circ Y : \text{Cocont}(\mathbf{Psh(C)}, \mathbf{E}) \rightarrow [\mathbf{C}, \mathbf{E}]$, which is precisely the free cocompletion property. 

