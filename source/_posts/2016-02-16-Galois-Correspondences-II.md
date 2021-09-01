---
title: Galois Correspondences II
date: 2016-02-16 15:44:18
author: Gau, Syu
categories: Math
tags: [Category Theory, Algebraic Geometry]
---
This time, we consider a more general case: we give the Galois correspondence for schemes over a field.

<!-- more -->

## Preliminaries

First, we recall some notions and facts. 

### Adjunctions and adjoint equivalences

**Definition:** Let $F\colon\mathcal{C}\to\mathcal{D}, G\colon\mathcal{D}\to\mathcal{C}$ be two functors. We call they form an **adjuction** if there exist two natrual transformations $\eta\colon\mathrm{id} \to GF$ (called **unit**) and $\epsilon\colon FG \to \mathrm{id}$ (called **counit**) such that the following two diagrams (called the **triangle identities**) hold. $$
\array{
FGF &
GFG\\\
F\eta\nearrow\qquad\nwarrow\epsilon G &
\eta G\nearrow\qquad\nwarrow F\epsilon \\\
F\quad\stackrel{\mathrm{id}}{\longrightarrow}\quad F &
G\quad\stackrel{\mathrm{id}}{\longrightarrow}\quad G
}
$$ If furthermore both $\eta$ and $\epsilon$ are isomorphisms, then $F,G$ are equivalences of categories and we say they form a pair of **adjoint equivalences**.

**Proposition:** Let $F\colon\mathcal{C}\to\mathcal{D}, G\colon\mathcal{D}\to\mathcal{C}$ be an adjunction with unit $\eta$ and counit $\epsilon$. Let $\mathcal{C}^{\eta}$ be the full subcategory of $\mathcal{C}$ consisting of those objects $X$ such that $\eta_X$ is an isomorphism. Define $\mathcal{D}^{\epsilon}$ likewise. Then $F$ and $G$ give rise to a pair of adjoint equivalences:
$$
\mathcal{C}^{\eta} \cong \mathcal{D}^{\epsilon}.
$$

### $G$-sets and $G$-spaces

**Definition:** Let $G$ be a group. A **$G$-set** is a set $S$ together with a group action $G\times S\to S$. A **$G$-map** is a map of sets between $G$-sets compatible with the group actions. A **$G$-subset** of a $G$-set $S$ is a subset $T$ of $S$ such that the inclusion $T\hookrightarrow S$ is a $G$-map. Let $s\in S$, then

- the $G$-subset $Gs:=\left\\{gs \middle| g\in G\right\\}$ is called the **orbit** of $s$;
- the subgroup $G_s:=\left\\{ g\in G \middle| gs=s \right\\}$ is called the **stabilizer** of $s$;
- $s$ is said to be **$G$-invariant** if $gs=s$ for all $g\in G$.

Let $g\in G$, then

- the $G$-subset $S^g:=\left\\{s\in S\middle|gs=s\right\\}$ is called the set of **fixed point** of $g$.

Finally

- the set of $G$-invariants is denoted by $S^G$, which equals $\cap_{g\in G} S^g$,
- the set of orbits is denoted by $S/G$ and called the **quotient** of the action.

**Fundamental theorem of $G$-sets:**  Let $G$ be a group and $S$ a $G$-set. Then $S$ is a disjoint union of some orbits $Gs$, which, as $G$-set, is isomorphic to the quotient $G/G_s$.

**Remark:** The above stories can be transplanted to some geometric categories $\mathcal{C}$. In this case, we should consider group objects $G$ instead of groups and $G$-spaces instead of $G$-sets. In this case, we call the space of orbits $S/G$ the **orbit space**. Examples include:

- continuous actions of topological groups on topological spaces,
- smooth actions of Lie groups on smooth manifolds, 
- regular actions of algebraic groups on algebraic varieties, and 
- actions of group schemes on schemes.

**Remark:** Let $G$ be a topological group. Then we call a $G$-space $S$ with discrete topology a **$G$-set**. Note that in thise case, the stabiliaer of any point is open.

## Galois Theory For $K$-Schemes

Let $K$ be a field and $G$ be its absolute Galois group.

**Definition:** A **$K$-scheme** is a locally ringed space which is locally the spectrum of a $K$-algebra. Equivalently, a $K$-scheme $X$ is a morphism of schemes $X\to \mathrm{Spec}(K)$. A morphism of $K$-schemes is a morphism of schemes over $\mathrm{Spec}(K)$.

Note that, there exists a continuous $G$-action on each set $\mathrm{Hom}\_{\mathrm{Spec}(K)}(\mathrm{Spec}(K\_{\mathrm{sep}}),X)$ for each $K$-scheme $X$: $$
\array{
G\times\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),X\right) &
\longrightarrow &
\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),X\right) \\\
(g,f) &
\longmapsto &
f\circ\widetilde{g},
}
$$ where $\widetilde{g}$ is the automoprhism of $\mathrm{Spec}(K\_{\mathrm{sep}})$ induced by $g\colon K\_{\mathrm{sep}}\to K\_{\mathrm{sep}}$.

Those actions are compatible with the morphisms of $K$-schemes. Therefore, we get a functor 
$$
K\text{-}\mathrm{Sch} \longrightarrow G\text{-}\mathrm{Set}.
$$

### From $G$-sets to $K$-schemes

Let $H$ be a subgroup of $G$, then $K\_{\mathrm{sep}}^H$ is an $K$-algebra. Since any homomorphism of $K$-algebras $K\_{\mathrm{sep}}^H\to K\_{\mathrm{sep}}$ can be extended to an automorphism of $K\_{\mathrm{sep}}$ over $K$, we have $$
\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),\mathrm{Spec}(K\_{\mathrm{sep}}^H)\right) = \mathrm{Hom}\_K\left(K\_{\mathrm{sep}}^H,K\_{\mathrm{sep}}\right) \cong G/H
$$ as $G$-sets.

Let $S$ be a $G$-set and $$
S = \bigsqcup Gs
$$ be all the distinct orbits of $S$. Then $$
X = \bigsqcup \mathrm{Spec}(K\_{\mathrm{sep}}^{G_s})
$$ is a $K$-scheme. 

Since $\mathrm{Spec}(K\_{\mathrm{sep}})$ is a single point hence connected, the $G$-map $$
\eta\_S\colon S = \bigsqcup Gs \cong \bigsqcup\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),\mathrm{Spec}(K\_{\mathrm{sep}}^{G\_s})\right)\longrightarrow
\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),\bigsqcup\mathrm{Spec}(K\_{\mathrm{sep}}^{G\_s})\right)
$$ is bijective.

Let $f\colon S\to T$ be a $G$-map and let $X, Y$ be the $F$-algebras associated to $S, T$ respectively. Then for any point $s\in S$, the stabilizer of $s$ is a subgroup of $f(s)$. Thus $K\_{\mathrm{sep}}^{G\_{f(s)}}$ is a subalgebra of $K\_{\mathrm{sep}}^{G\_s}$. This induces a morphism of $K$-schemes $X\to Y$.

In this way, we get a functor 
$$
F\colon G\text{-}\mathrm{sets} \longrightarrow K\text{-}\mathrm{Sch}.
$$

### From $K$-schemes to $G$-sets

Let $X$ be a $K$-scheme and $$
\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),X\right) = \bigsqcup Gf
$$ the orbit decomposition. Let $$
Y = \bigsqcup \mathrm{Spec}(K\_{\mathrm{sep}}^{G\_f}).
$$

Let $f\colon\mathrm{Spec}(K\_{\mathrm{sep}})\to X$ be a morphism of $K$-schemes. Then, for any open set $U$ of $X$ containing the image of $f$, the $K$-homomorphism $\mathcal{O}\_X(U)\to K\_{\mathrm{sep}}$ factors through $K\_{\mathrm{sep}}^{G\_f}$. Thus $f$ factors through $\mathrm{Spec}(K\_{\mathrm{sep}}^{G\_f})$.

Therefore we get a canonical morphism of $K$-schemes
$$
\epsilon\_X\colon Y\longrightarrow X.
$$

### The adjunction

From the above discussion, we have seen:

- given a $G$-set $S$, there is a canonical bijective $G$-map $$\eta\_S\colon S\longrightarrow\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),F(S)\right);$$
- given a $K$-scheme $X$, there is a canonical morphism of $K$-schemes $$\epsilon\_X\colon F(\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),X\right))\longrightarrow X.$$

Moreover, one can verify that the above data satisfies the triangle identities. Thus we get an adjunction
$$
F\dashv \mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),-\right).
$$

As $\eta\_S$ is always bijective, we have $(G\text{-}\mathrm{Set})^{\eta} = G\text{-}\mathrm{Set}$. How about $(K\text{-}\mathrm{Sch})^{\epsilon}$?

### Etale schemes

The essential iamge of the functor $F$ can be characterised as follows.
**Definition:** A $K$-scheme is said to be **étale** if it is isomorphic to a disjoint union of sepctra of finite separable extensions of $K$.
This is of course not the original definition. One can image this as a lemma.

By the first Galois correspondence, any finite separable extension of $K$ is of the form $K^H$ where $H$ is an open subgroup of $G$.

Let $X$ be an étale $K$-scheme and
$$
X \cong \bigsqcup \mathrm{Spec}(K\_{\mathrm{sep}}^{H\_i}).
$$

Then we have
$$
\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),X\right)=\bigsqcup\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),\mathrm{Spec}(K\_{\mathrm{sep}}^{H\_i})\right).
$$

Note that each $\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),\mathrm{Spec}(K\_{\mathrm{sep}}^{H\_i})\right)$ must be connected. Therefore $$F(\mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),X\right)) = \bigsqcup \mathrm{Spec}(K\_{\mathrm{sep}}^{H\_i})$$ and hence the canonical morphism $\epsilon\_X$ is an isomophism.

In this way, we see that $(K\text{-}\mathrm{Sch})^{\epsilon}$ consists precisely the étale $K$-schemes.

### Galois correspondence for $K$-schemes

Conclude above, we have
**Theorem:** Let $K$ be a field and $G$ be its absolute Galois group. Then there is a pair of adjoint equivalences of categories $$
F\dashv \mathrm{Hom}\_{\mathrm{Spec}(K)}\left(\mathrm{Spec}(K\_{\mathrm{sep}}),-\right).
$$ between the category of $G$-sets and the category of étale $K$-schemes.

Let $L/K$ be a Galois extension, then the above pair of adjoint equivalences induces a pair of adjoint of equivalences between the category of $\mathrm{Gal}(L/K)$-sets and the category of $K$-schemes which are isomorphic to disjoint unions of sepctra of finite subseparable extensions of $L/K$.

### Galois correspondence for $K$-algebras

Note that finite disjoint union of affine schemes is the same as coproduct of them in the category of affine schemes, hence we have
$$
\bigsqcup_{i=1}^{n}\mathrm{Spec}(L\_i) = \mathrm{Spec}(\prod_{i=1}^{n}L\_i).
$$

Recall that a $K$-algebra is said to be **étale** if it is a finite product of finite separable extensions of $K$ and **splited** by $L$ is all those separable extensions are subextensions of the Galois extension $L/K$. Then one may expect a Galois correspondence for such kind of $K$-algebras. However, a finite disjoint union of $G$-sets may not be finite unless all the components are finite. So we have
**Theorem:** Let $L/K$ be a finite Galois extension. Then the functor $$
\mathrm{Hom}_{K}\left(-,L\right)
$$ is an equivalence between the category of finite $\mathrm{Gal}(L/K)$-sets and the category of finite $K$-algebras splited by $L$.

Note that 

- any Galois extension is a filtered colimit of finite Galois extensions;
- any $K$-algebra is a filtered colimit of finite subalgebras;
- a $G$-space is said to be **profinite** if it is a filtered colimit of finite $G$-sets.

We thus get
**Theorem:** Let $L/K$ be a Galois extension. Then the functor $$
\mathrm{Hom}_{K}\left(-,L\right)
$$ is an equivalence between the category of profinite $\mathrm{Gal}(L/K)$-spaces and the category of $K$-algebras splited by $L$.

### Etale coverings

Recall that
**Definition:** Let $X$ be a scheme. A family of morphisms $\\{f_i\colon Y_i\to X\\}$ is called a **étale covering** if all $f_i$ are étale and the images of $Y\_i$ cover $X$. Equipped such coverings, $\mathrm{Sch}$ becomes a sites, call the **(big) étale site**, and $K\text{-}\mathrm{Sch}$ becomes a sites $\mathrm{Spec}(K)\_{et}$, call the **(small) étale site** of $\mathrm{Spec}(K)$.

One can verify that under the Galois correspondence for $K$-schemes, the étale coverings in the étale site $\mathrm{Spec}(K)\_{et}$ correspond to surjective families of $G$-maps in $G\text{-}\mathrm{Set}$.


Let's stop this post here.

## Reference

For the notion of schemes, one can refer any textbooks such as

- Robin Hartshorne, *Algebraic Geometry*, Graduate Texts in Mathematics 52, New York: Springer-Verlag, 1977.
- Ravi Vakil, [*Math 216: Foundations of algebraic geometry*](https://math216.wordpress.com).
- Johan de Jong, et al., [*Stack project*](http://stacks.math.columbia.edu).