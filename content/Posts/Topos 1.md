---
title: Frame and Locales
draft: false
created: 0001-01-01
tags:
  - Topos
---
This will be some notes on Topos Theory pedagogically based on lectures given out by [Joyal[^1]]. The approach that Joyal has taken is to introduce the theory of Frames/Locales prior to the general notion of an elementary topos, a "bottom-up" approach. It indeed can be seen that locales embody most of the phenomena that toposes do and there is a coherent analogy that can be made between posets and categories, in turn toposes. 
## Motivation
Suppose $X$ is a space (topological space, manifold, etc). Often we study these spaces by looking at maps from $X$ to a ring object $R$ in the same category of spaces. Since $R$ is a ring object, we have $\text{Hom}(X, R)$ is a ring where can verify $\text{Hom}(-, R): \mathbf{Space} \to \mathbf{Ring}$ is a functor. Very often one can describe a left adjoint $\text{Spec}: \mathbf{Ring}^\text{op} \to \mathbf{Space}$ such that 
$$
\text{Hom}_{\mathbf{Space}}(\text{Spec}(A), X) \equiv \text{Hom}_{\mathbf{Ring}^\text{op}}(A, \text{Hom}(X, R))
$$
It is well-known that adjoint pairs can be canonically restricted to equivalences on full-subcategories where units and counits are isomorphisms; as such this pair gives notions to many famous dualities such as the Stone duality, Gelfand–Naimark duality or the duality in algebraic geometry between commutative rings and affine schemes.  
We have a similar situation where Frames will act like Rings and we consider looking from topological spaces. 
## Frames and Locales
Recall the Sierpinski Space $S$ which has points $\{0, 1\}$ with open sets $\{ \emptyset, \{ 1 \}, \{ 0, 1 \} \}$. We know the functor $\mathcal{O} : \mathbf{Top}^\text{op} \to \mathbf{Set}$ which takes open sets of $X$ is representable with representing object $S$. Now notice to define a ring object, we need morphisms $R \times R \rightarrow R$ corresponding to the general operations $+, \cdot$. However one can notice that the Sierpinski space can have similar operations $S \times S \to S$ defined as infima and suprema
$$
\wedge, \vee: S \times S \rightarrow S
$$
which correspond to union and intersection of open sets. More commonly they're referred to as joins and meets. More importantly they behave like addition and multiplication, satisfying the distributive law 
$$
x \wedge (y \vee z) = (x \wedge y) \vee (x \wedge z)
$$
This points us to view the Sierpinski Space as behaving like a ring object, but note it clearly isn't as we have no additive inverse. This leads us to the definition of frames. 

**Def.** A poset is a *complete lattice* if it admits arbitrary suprema and finite infima. 
Important to note it is sufficient to have all suprema to have all infima since we can express infima as a set of lower bounds, i.e., $\inf(S) = \sup\{\text{lower bounds of }S\}$. 

**Def.** A *frame* is a complete lattice such that the distributivity law holds
$$y \wedge \left(\bigvee_{i \in I} x_i \right) = \bigvee_{i \in I} y \wedge x_i$$

We can see $\mathcal{O}(X)$ is a frame, where the join is just union of open sets and meet is intersection followed by interior operation. Clearly needed to ensure the resulting set is open. 
$$
\bigvee_{i \in I} U_{i} = \bigcup_{i \in I} U_{i}, \quad \bigwedge_{i \in I} U_i = \widehat{\bigcap_{i \in I} U_{i}}
$$
As such $\mathcal{O}(X)^{op}$ is not a frame in general as unions do not distribute over intersections, i.e., 
take $U = (0, 1), V_i = \left( -\frac{1}{n}, \frac{1}{n} \right)$. 

**Def.** A *morphism of frames* is defined as $\phi: A \to B$ where $A, B$ are frames such that $\phi$ preserve arbitrary joins and finite meets, with $\phi(1) = 1$, i.e., preserving the unit element for the meet. 

Now if we have a continuous function $X \xrightarrow{f} Y$, we can define $\mathcal{O}(X) \xleftarrow{f^*} \mathcal{O}(Y)$ taking the preimage of $f$. It is easy to verify that this map is a morphism between frames. As such we have a contravariant functor $\mathcal{O}$ from $\mathbf{Top}$ to $\mathbf{Frm}$. 


#### Points of Locales 

#### Quotient Frames 

#### Free Frames



#### References
[^1]:: https://www.youtube.com/watch?v=Ro8KoFFdtS4
[^2]: Sheaves in Geometry and Logic by Maclane and Moerdjik
