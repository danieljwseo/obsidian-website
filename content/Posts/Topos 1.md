---
title: Frame and Locales
draft: false
created: 2026-01-01
tags:
  - Topos
  - Cat
---
This will be some notes on Topos Theory pedagogically based on lectures given out by [Joyal](https://www.youtube.com/watch?v=Ro8KoFFdtS4 ). The approach that Joyal has taken is introducing the theory of Frames/Locales prior to the general notion of an elementary topos, a "bottom-up" approach. It indeed can be seen that locales embody most of the phenomena that toposes do and there is a coherent analogy that can be made between posets and categories, in turn toposes. 
## Motivation
Suppose $X$ is a space (topological space, manifold, etc). Often we study these spaces by looking at maps from $X$ to a ring object $R$ in the same category of spaces. Since $R$ is a ring object, we have $\text{Hom}(X, R)$ is a ring where can verify $\text{Hom}(-, R): \mathbf{Space}^\text{op} \to \mathbf{Ring}$ is a functor. Very often one can describe a right adjoint $\text{Spec}: \mathbf{Ring}^\text{op} \to \mathbf{Space}$ such that in a rough sense 
$$
\text{Hom}_{\mathbf{Ring^\text{op}}}(\text{Hom}(X, R), A) \cong \text{Hom}_{\mathbf{Space}}(X, \text{Spec}(A))
$$
It is well-known that adjoint pairs can be canonically restricted to equivalences on full subcategories where the units and counits are isomorphisms; as such this pair gives notions to many famous dualities such as the Stone duality, Gelfand–Naimark duality or the duality in algebraic geometry between commutative rings and affine schemes.  
We will have a similar situation by looking at topological spaces and having frames act like rings. 
## Frames and Locales
Recall the Sierpinski Space $S$ which has points $\{0, 1\}$ with open sets $\{ \emptyset, \{ 1 \}, \{ 0, 1 \} \}$. We know the functor $\mathcal{O} : \mathbf{Top}^\text{op} \to \mathbf{Set}$ which takes open sets of $X$ is representable with representing object $S$. Now note to define a ring object, we need morphisms $R \times R \rightarrow R$ corresponding to the general operations $+, \cdot$. However one can notice that the Sierpinski space can have similar operations $S \times S \to S$ defined by infima and suprema on the underlying set $\{ 0, 1 \}$
$$
\wedge, \vee: S \times S \rightarrow S
$$
which correspond to union and intersection of open sets. More commonly they're referred to as joins and meets. Importantly they behave like addition and multiplication, satisfying the distributive law 
$$
x \wedge (y \vee z) = (x \wedge y) \vee (x \wedge z)
$$
This points us to view the Sierpinski Space as behaving much like a ring object, but note it clearly isn't as we have no additive inverse. This leads us to develop the definition of frames. 

*Def.* A poset is a **complete lattice** if it admits arbitrary suprema and infima. 
Important to note it is sufficient to have all suprema to have all infima since we can express infima as a set of lower bounds, i.e., $\inf(X) = \sup\{\text{lower bounds of }X\}$. 

*Def.* A **frame** is a complete lattice such that the distributivity law holds
$$y \wedge \left(\bigvee_{i \in I} x_i \right) = \bigvee_{i \in I} y \wedge x_i$$

We can see $\mathcal{O}(X)$ is a frame, where the join is just union of open sets and meet is intersection followed by interior operation. Clearly needed to ensure the resulting set is open. 
$$
\bigvee_{i \in I} U_{i} = \bigcup_{i \in I} U_{i}, \quad \bigwedge_{i \in I} U_i = \widehat{\bigcap_{i \in I} U_{i}}
$$
As such $\mathcal{O}(X)^{op}$ is not a frame in general as unions do not distribute over intersections, i.e., 
take $U = (0, 1), V_i = \left( -\frac{1}{n}, \frac{1}{n} \right)$. 

*Def.* A **morphism of frames** is defined as $\phi: A \to B$ where $A, B$ are frames such that $\phi$ preserve arbitrary joins, finite meets, and the unit element for the meet and join. 
$$
\phi(0) = 0,\quad \phi(1) = 1,\quad \phi(x \wedge y) = \phi(x) \wedge \phi(y),\quad \phi \left( \bigvee_{i \in I}x_{i}  \right) = \bigvee_{i \in I} \phi(x_{i})
$$
Now if we have a continuous function $X \xrightarrow{f} Y$, we can define $\mathcal{O}(Y) \xrightarrow{f^*} \mathcal{O}(X)$ taking the preimage of $f$. It is easy to verify that this map is a morphism between frames. As such we have a contravariant functor $\mathcal{O}$ from $\mathbf{Top}$ to $\mathbf{Frm}$. Now as aforementioned in the motivations, we also have a contravariant functor $\text{pt}$ from $\mathbf{Frm}$ to $\mathbf{Top}$ which will be right adjoint defined as 
$$
\text{pt}(A) = \mathbf{Frm}(A, [1])
$$
for frame $A$ and $[1] = \{0, 1\}$, $0 < 1$. The topology is made by the open sets being of the form 
$$
\text{pt}(a) = \{ p \in \text{pt}(A) \mid p(a) = 1\}
$$
for $a \in A$. 
We can indeed prove this is a topology, define $\text{pt}(f)$ in the most natural way, and prove it's continuous, concluding $\text{pt}$ is a functor. 
We have the adjunction as 
$$
\mathbf{Frm}(A, \mathcal{O}(X)) \cong \mathbf{Top}(X, \text{pt}(A))
$$
We define the forward map $\phi$ as 
$$
f: A \to \mathcal{O}(X) \xmapsto{\phi} g(x)(a) = x \in f(a) 
$$
where $x \in f(a)$ implies the value $1$ and otherwise $0$. The reverse map $\psi$ will be defined as  
$$
g: X \to \text{pt}(A) \xmapsto{\psi} f(a) = g^{-1}(\text{pt}(a))
$$
To prove $\phi, \psi$ make a bijection pair, we consider 
$$
f(a) = \psi(\phi(f))(a) = \phi(f)^{-1}(\text{pt}(a))  
$$
Note $x$ is in right hand side iff $\phi(f)(x)(a) = 1$, i.e., $x \in f(a)$, proving our desired. We also consider 
$$
g(x)(a) = \phi(\psi(g))(x)(a) = x \in \psi(g)(a) = g^{-1}(\text{pt}(a)) 
$$
where $x \in g^{-1}(\text{pt}(a))$ is in right hand side iff $g(x)(a) = 1$, proving our desired. 
It remains to show naturality, i.e., the below equations hold true for $f: X' \to X$, $h: A' \to A$,
$$
\psi(g \circ f) = f^* \circ \psi(g), \quad \psi(\text{pt}(h) \circ g) = \psi(g) \circ h
$$
where first can be seen to hold $\psi(g \circ f)(a) = (g \circ f)^{-1}(\text{pt}(a)) = f^{-1}(g^{-1}(\text{pt}(a))) = f^* \circ \psi(g)$ and the second is true $\psi(\text{pt}(h) \circ g)(a') = (\text{pt}(h) \circ g)^{-1}(\text{pt}(a')) = g^{-1}(\text{pt}(h)^{-1}(\text{pt}(a')))$ which can be seen to be the same as $g^{-1}(\text{pt}(h(a')))$. As such we have shown our adjunction. 
One can notice to make this into a traditional adjunction, we need to take the dual of one of the categories. We choose the categories of frames to be dualed and as such, the category of **Locales** is defined as $\mathbf{Frm}^\text{op}$. 
## Quotient Frames 
Motivation by factorization systems, i.e., in category of sets, every function can be decomposed into a surjective then injective function trivially, we also have something similar for morphisms of frames or more generally morphisms between Posets. Lastly establish that there is a bijection between these "quotient" frames $A_{\sigma} = \{ x \mid \sigma(x) = x \}$ and nucleus'. 

A morphism of frames $\phi: A \to B$ has a right adjoint $\phi^*: B \to A$ in the category of posets. 
Note adjoint in category of posets is 
$$
f: P \leftrightarrow Q: g, \quad f \dashv g \quad \text{ iff } \quad f(x) \le y \iff x \le g(y)
$$
$\sigma = gf: P \to P$ is called the **closure** or **monadic** operator, $\sigma(x) \ge x, \sigma^2(x) = \sigma(x)$. Dually the **comonadic** operator if $\rho = fg: Q \to Q$, with $\rho(y) \le y, \rho^2(y) = \rho(y)$. 

## Free Frames
Lastly free frames can be made similar to the usual free forgetful adjunction between algebras, i.e., Set to CMon to CRings, whats more interesting is if we think of the monads induced by each free-forgetful adjunction pair, their composition is also a monad. In general, Beck considered when this is true, a similar result holds in Frame to lower semi lattice to posets where the composition is a monad. 

## References 
* A crash course in topos theory by [Joyal](https://www.youtube.com/watch?v=Ro8KoFFdtS4 )
* Sheaves in Geometry and Logic by Maclane and Moerdjik
* An informal introduction to topos theory by Leinster
