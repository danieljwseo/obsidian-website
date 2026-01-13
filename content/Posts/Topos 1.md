---
title: Topos Theory Introduction
draft: true
created: 0001-01-01
tags:
  - Topos
---
This will be some notes on Topos Theory pedagogically based on lectures given out by [Joyal[^1]]. The approach that Joyal takes is to introduce the theory of Frames/Locales prior to general notion of an elementary topos, i.e., a "bottom-up" approach. It can be seen that locales embody most of the phenomena that toposes do and there is a coherent analogy that can be seen between in general posets and categories, in turn toposes. 

as locales embody most of the phenomena in toposes. It is also known that Localic toposes are easy to work with. 
#### Motivation


#### Frames and Locales

#### Points of Locales 

#### Quotient Frames 

#### Free Frames



Theory of locales - developed in 1950s, Charles Ehressman 
Topos theory - as read in leinster's intro, locales embody most of the phenomena in toposes 
Higher topos theory 
* bottom up approach

Geometry vs Algebra, 
commutative geometry is about studying commutative rings, 
Suppose $X$ is a space (top., manif., etc), often study spaces by looking at maps from $X$ to ring $R$, $R$ is a ring object in the category of spaces (top., manif., etc), 
Hom(X, R) is a ring, Hom(-, R) : Spaces \to Rings, often one can describe adjoint described as Spec from Rings to Spaces, (X, Spec(A)) is bijection with probably (Hom(X, R), A), often used is how adjunctions can restrict to equivalences

In the case of locales, spaces is top. spaces, 
Sierpinski space, {0, 1}, with {1} open, all opens sets of $X$ correspond to maps (cont.) from $X$ into $U$, Sierpsinski space is like the "subobject classifier in Open(X)"
Map(X, S) \equiv Open(X) 
$R \times R \rightarrow R$, operations $+, \cdot$ exist for general rings; considering for the sierpinski space or
the ring of open sets of X can have the infimum and supremum, which satisfies distributivity law just like addition and multiplication expected in general rings, i.e., the notion of frames arise 

| Rings  | Schemes |
| ------ | ------- |
| Frames | Locales |

Frame is defined as a complete lattice such that the distributivity law holds 
$$y \wedge \left(\bigvee_{i \in I} x_i \right) = \bigvee_{i \in I} y \wedge x_i$$
A poset is a complete lattice if it admits arbitrary suprema and infima. Important to note it is enough to have all suprema since $\inf(S) = \sup\{\text{lower bounds of }S\}$. 
$\mathcal{O}(X)$ is a frame, suprema/join is just union, infima/meet is just intersection and taking interior to make sure it is open. As such $\mathcal{O}(X)^{op}$ is not a frame in general. 
Note meet and join refer to finite 
$X \xrightarrow{f} Y$, $\mathcal{O}(X) \xleftarrow{f^*} \mathcal{O}(Y)$ is a morphism between frames, which is defined as 
$\phi: A \to B$ where $A, B$ are frames such that $\phi$ preserves arbitrary joins and finite meets, with $\phi(1) = 1$, i.e., preserving the unit element for the meet, so in this case $X$ would be the unit element.  

We have a functor $\mathcal{O}: \mathrm{Top} \to \mathrm{Frame}^{op}$, this functor has an adjoint 
$\mid - \mid_{top}: \mathrm{Frame}^{op} \to \mathrm{Top}$  which is defined as $\mid A \mid_{top} = Hom(A, [1])$, $[1] = \{0, 1\}$ where $0 < 1$. 
$$Hom(A, \mathcal{O}(X)) \cong Hom(X, \mid A\mid_{top})$$
We often look into the opposite category of Frames, i.e., Locales. 

bijection between points of locales and closed subobjects of locales, 
$A \xrightarrow{\phi} [1], \ker \phi = \{ x \mid \phi(x) = 0 \}, \kappa(\phi) = \bigvee_{x \in \ker \phi} x = u$, $u$ is meet irreducible 

Morphism of frames has a right adjoint in the category of posets, 
closure (monadic) operator and comonadic operator induced by an adjunction between postes, i.e., Galois connection (particular case of monads)
Particularly in frames, the closure operatore also preserves meets, we call this nucleus. Dually, conucleus for comonadic operators which preserve joins(?). 
Motivation by factorization systems, i.e., in category of sets, every function can be decomposed into a surjective then injective function trivially, we also have something similar for morphisms of frames or more generally morphisms between Posets. There is a bijection between these "quotient" frames $A_{\sigma} = \{ x \mid \sigma(x) = x \}$ and nucleus' 
Lastly free frames can be made similar to the usual free forgetful adjunction between algebras, i.e., Set to CMon to CRings, whats more interesting is if we think of the monads induced by each free-forgetful adjunction pair, their composition is also a monad. In general, Beck considered when this is true, a similar result holds in Frame to lower semi lattice to posets. 

```
| Sets   | Abelian Groups | Commutative things |
| Posets | sup-lattices   | Frames             |
| Cat. | Presentable-cat. | Topoi | 
```


#### References
[^1]:: https://www.youtube.com/watch?v=Ro8KoFFdtS4
