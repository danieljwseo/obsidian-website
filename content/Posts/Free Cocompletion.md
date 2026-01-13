---
title: Free Cocompletion of Presheaf Categories
tags:
created:
draft: true
---
This post will be outlining some different approaches to proving the free cocompletion property for presheaf categories. 
Proof sketch for $Psh(C)$ is free cocompletion, i.e., $- \circ y: [Psh(C), D] \rightarrow [C, D]$ by LKE has left adjoint $Lan_y$, the adjoint pair $(Lan_y, -\circ y)$ can restrict to an equivalence, well known to be the full subcategories Fix(FG) and Fix(GF) where the unit and counit are isomorphisms, we can prove the unit is already an isomorphism, so $[C, D]$ is the Fix, now counit one can compute to find it is isomorphism iff $G \in [Psh(C), D]$ is cocomplete, as such Fix is $Cocont(Psh(C), D)$, which means we have equivalence $- \circ y : Cocont(Psh(C), D) \rightarrow [C, D]$, which is precisely the free cocompletion property. 
To confirm the cocompleteness, the different approaches will be one elementary using definition of $Lan_y$ to "guess" what the $Lan_y$ must map presheaves to, and the other will be of ends which make the use of "two changing parameters" easier to handle. 