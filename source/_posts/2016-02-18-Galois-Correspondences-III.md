---
title: Galois Correspondences III
date: 2016-02-18 11:02:19
author: Gau, Syu
categories: Math
tags: [Category Theory, Algebraic Topology]
---
This time, we consider another kind of Galois correspondence: the one for covering spaces. This is actually somehow trivial.
<!-- more -->

## Preliminaries

Let $X$ be a topological space. We first recall some notions in topology.

**Definition:** A **covering space** $Y$ over $X$ is a bundle $p\colon Y\to X$ which is *locally trival* and with *discrete fibers*. In plain words, the condition means for every point $x\in X$, there exists an open neighborhood $U$ such that the pullback $p^{-1}(U)\to U$ is isomorphic to a projection $U\times F\to U$ with $F$ a nonempty discrete set.
$$
\array{
p^{-1}(U) \stackrel{\cong}{\longrightarrow} U\times F \\\
p\searrow\quad\swarrow\mathrm{pr} \\\
U
}
$$

**Definition:** The **fundamental group** $\pi(X,x)$ of $X$ at a point $x\in X$ is the group of homotopy classes of loops through $x$ and lie in $X$.

Under the assumption that $X$ is *connected*, *locally path-connected* and *semi-locally simply-connected*, the group $\pi(X,x)$ is independent of the choice of $x$. In this case, we denote $\pi(X)$ for short. However, we still need to fix a base point $x$. We will keep this assumption throughout this post.

## Galois correspondence for covering spaces

### From covering spaces to $\pi(X)$-sets

Let $p\colon Y\to X$ be a covering space. Then $p^{-1}(x)$ is a $\pi(X)$-set whose action is given as follows: the *unique path-lifting lemma* says that given a point $y_1\in p^{-1}(x)$, any loop $\phi$ in $X$ start at $x$ can be uniquely lifted to a path in $Y$ from $y_1$ to another point $y_2\in p^{-1}(x)$. The homotopic loops give the same point $y_2$, thus we define the result of the action of this homotopy class $[\phi]$ on $y_1$ to be $y_2$.

Let $f\colon Y\to Y'$ be a morphism of covering spaces of $X$. Then it induces a continuous $\pi(X)$-map from $p^{-1}(x)$ to $p'^{-1}(x)$. In this way, we get a functor from the category $\mathrm{Cov}/X$ of covering spaces of $X$ to the category of $\pi(X)$-sets:
$$
\mathcal{F}_x\colon\mathrm{Cov}/X\longrightarrow\pi(X)\text{-}\mathrm{Set}.
$$

### The universal covering space

Let $\widetilde{X}$ be the topological space whose underlying set is the set of all homotopy classes of paths in $X$ starting at the base point $x$ and whose topology is the weakest one making the following map continuous:
$$
p\colon\widetilde{X}\to X,\quad 
[\gamma]\mapsto\gamma(1).
$$

For convenience, we fix the bas point $\tilde{x}$ of $\widetilde{X}$  to be the homotopy class of the trivial loops through $x$.

Then $p\colon\widetilde{X}\to X$ is the **universal covering space** of $X$ in the sense that for any connected covering space $Y\to X$, there exists a morphism of covering spaces of $X$: $$
\array{
\widetilde{X} \stackrel{\exists!}{\longrightarrow} Y \\\
\searrow\quad\swarrow \\\
X
}
$$ and this morphism is unique if we require it to preserve the base points. When we choice $y\in p^{-1}(x)$ to be the base point of $Y$, the morphism is given as follows: the *unique path-lifting lemma* allows us to lift every path $\gamma$ start at $x$ in $X$ to a path start at $y$ in $Y$, we define the image of $[\gamma]$ to be the end of this path.

Note that the universal covering space naturally has a free $\pi(X)$-action given by composition of homotopy classes of paths. For any subgroup $H$ of $\pi(X)$, the orbit space $\widetilde{X}/H$ also gives a connected covering space of $X$ whose fibers are isomorphic to $\pi(X)/H$.

### From $\pi(X)$-sets to covering spaces

Let $S$ be a $\pi(X)$-set. Then, we may write
$$
S = \bigsqcup \pi(X)s.
$$

We define $$
F(S) = \bigsqcup \widetilde{X}/\pi(X)_s,
$$ and the bundle map $p\colon F(S)\to X$ is the one induced from the previous property of universal covering space. One can see the canonical $\pi(X)$-map $$
S\longrightarrow p^{-1}(x)
$$ is bijective.

Note that this induces a functor
$$
F\colon \pi(X)\text{-}\mathrm{Set}\longrightarrow\mathrm{Cov}/X.
$$

### The equivalence

Given a covering space $p\colon Y\to X$, we have a $\pi(X)$-set $p^{-1}(x)$ where $x$ is a point of $X$. Assume $p^{-1}(x) = \bigsqcup \pi(X)y$, we have $$F(p^{-1}(x)) = \bigsqcup \widetilde{X}/\pi(X)_y.$$ 

As elements of $\pi(X)_y$ fix $y\in p^{-1}(x)$, the unique morphism of covering spaces of $X$ from $\widetilde{X}$ to $Y$ mapping $\tilde{x}$ to $y$ factors through $\widetilde{X}/\pi(X)_y$. In this way, we have a canonical morphism of covering spaces of $X$: $$F(p^{-1}(x))\longrightarrow Y.$$

It is not difficult to see that $Y$ is connected if and only if $\pi(X)$ acts transitive on $p^{-1}(x)$. Therefore, the orbit decomposition of $p^{-1}(x)$ corresponds to the connected components decomposition of $Y$. In this way, we see the moprhism $$F(p^{-1}(x))\longrightarrow Y$$ is an isomoprhism.

Now, we get the Galois correspondence for covering spaces.

**Theorem:** Let $X$ be a *connected*, *locally path-connected* and *semi-locally simply-connected* space. Then we have an equivalence of categories $$
\mathrm{Cov}/X\cong\pi(X)\text{-}\mathrm{Set}.
$$

## Rethinking

It is easy to verify that the universal covering space $\widetilde{X}$ represents the functor $\mathcal{F}_x$. Moreover, we have $$\mathrm{Aut}_X(\widetilde{X}) \cong \pi(X),$$ and $$\mathrm{Aut}_X(\widetilde{X}) < \mathrm{Aut}(\mathcal{F}_x).$$ However, $\mathrm{Aut}_X(\widetilde{X})$ is in general not isomorphic to $\mathrm{Aut}(\mathcal{F}_x)$. 

What's more, by only assume $X$ is connected, the functor $\mathcal{F}_x$ still works and is independent of the choice of $x$, while the universal covering $\widetilde{X}$ may not exists.

Let's stop this post here and leave further discussions next time.

## Reference

One can take a loo at 

- Allen Hatcher, *Algebraic Topology*, Cambridge University Press, 2002.