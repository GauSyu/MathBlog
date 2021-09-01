---
title: Connectedness of Schemes
date: 2016-02-13 15:00:23
author: Gau, Syu
categories: Math
tags: [Category Theory, Algebraic Geometry]
---

In this short post, we point out that the notion of connectedness of schemes is previously a special case of connected objects.
<!-- more -->

## Infinitary extensive categories

**Definition:** A category $\mathcal{C}$ is said to be **infinitary extensive** if it has all (small) coproducts such that pullbacks of coproduct injections along arbitrary morphisms exist and finite coproducts are disjoint and stable under pullback.

One can then image coproducts in such kind of categories as generalized disjoint unions. Typical examples are topoi and some geometric categories such as $\mathrm{Top}$ and $\mathrm{Diff}$.

The category $\mathrm{Sch}$ of schemes is also infinitary extensive, see [here](http://ncatlab.org/toddtrimble/published/Dippy+disproof+of+infinitary+extensivity+of+affine+schemes) for discussion on this fact.

## Connected schemes

We now discuss the notion of connectedness for schemes. Note that we always assume that connected spaces are nonempty. Recall that the coproducts in $\mathrm{Top}$ and $\mathrm{Sch}$ are just disjoint unions.

**Definition:** Let $\mathcal{C}$ be an infinitary extensive category. Then an object $X$ is called a **connected object** if the representable functor $$
\mathrm{Hom}(X,−)\colon\mathcal{C}\longrightarrow \mathrm{Set}
$$ preserves binary coproducts. Note that if this is the case, then the above representable functor preserves all coproducts.

**Definition:** A scheme $X$ is said to be **connected** if its underlying topological space is connected.

We want to show
**Theorem:** A scheme is connected if and only if it is a connected object.

To prove this, recall the similar result for topological spaces.
**Lemma:** A topological space is connected if and only if it is a connected object.
**Proof:** Let $X$ be a connected space and $\\{Y_i\\}$ be a family of topological spaces. Then we always have an injective map $$\bigsqcup\mathrm{Hom}(X,Y\_i)\longrightarrow\mathrm{Hom}(X,\bigsqcup Y\_i).$$ As any continuous map must preserve connectedness, this map is also surjective.
Coversely, let $X=Y_1\sqcup Y_2$. Then the map $$\mathrm{Hom}(X,Y\_1)\sqcup\mathrm{Hom}(X,Y\_2)\longrightarrow\mathrm{Hom}(X,X)$$ is not surjective since the identity $\mathrm{id}_{X}$ has no preimage. This shows $X$ can not be a connected object.

Note that, the underlying map of any morphism of schemes is continuous, therefore the above proof works for the theorem with a bit modifocations.

## Reference

https://ncatlab.org/nlab/show/connected+object