---
title: Profinite groups
date: 2016-02-23 19:28:34
author: Gau, Syu
categories: Math
tags: [Category Theory, Algebra, Algebraic topology]
---
In this post, we simplily discuss the basic notions of profinite groups.
<!-- more -->

## Profinite spaces

Usually, the prefix ''pro'' is short for ''projective limit'', which is another name of ''limit''. In this sense, ''profinite'' means ''limit of finite''. Then, a **profinite set** should be a limit of finite sets. But in what category? One can take the limit in $\mathrm{Set}$, or in $\mathrm{Top}$ to get a topology on that set. So, we define
**Definition:** A **profinite space** is a limit of finite sets (viewed as discrete sets) in $\mathrm{Top}$.

But how the open sets in a profinite space look like?

### Example: product of finite sets

Recall that the product topology on the Cartesian product $\prod_iX_i$ is given by the basis $$
\prod_i U_i,
$$ where $U_i$ are open sets of $X_i$ and only finitely many $U_i$ are not the entire $X_i$.

From this, one can see the topology of a product of finite sets must be *quasi-compact*, *Hausdorff* and *totally disconnected*.

### Stone spaces

A **Stone space** is a topological space which is quasi-compact, Hausdorff and totally disconnected. Note that all those properties can be inherited by subspaces.

Recall that any limit is a subspace of a product. Then we get
**Proposition:** Profinite spaces are Stone spaces.

Conversely, let $X$ be a Stone space, we expect it to be a limit. So, first of all, we need a system of spaces under $X$, in particualr, a system of quotients of $X$. A possible quotient is the set of connected components. However, as we will see, this set is not always finite. Instead, we consider the set of *closed-open partitions*. A *closed-open partition* of $X$ is a collection of nonempty pairwise disjoint closed-open subsets of $X$ such that their union is $X$. The topology on a closed-open partition $I$ is the quotient topology induced by the projection $X\to I$. Since $X$ is quasi-compact, each $I$ must be finite. As quotients of $X$, there exist canonical projections between those closed-open partitions making them form a cofiltered system of quotients of $X$. Now, we have a canonical continuous map $$
X\longrightarrow \varprojlim I.
$$ This map is injective since the totally disconnectedness implies that any two distinct points can be separated by at least a pair of closed-open sets. This map is also surjective since the compatibility of members of the system implies that for any $(U_I)\in \varprojlim I$, the intersection of any finitely many $U_I$ is nonempty and then the quasi-compactness implies that the intersection of all $U_I$ is nonempty and hence gives the preimage of $(U_I)$. Finally, this map lies in the category of quasi-compact Hausdorff spaces. As this category is *balanced*, we conclude that the map is a homeomorphism.

In this way, we see:
**Proposition:** Stone spaces are profinite spaces.

## Profinite groups

Likewise, a **profinite group** is a limit of finite groups in the category of topological groups. Recall the forgetful functors to $\mathrm{Top}$ and $\mathrm{Grp}$ preserve limits, therefore a profinite group is precisely a topological group whose underlying topological space is a profinite space.

### Open subgroups

Let $G$ be a profinite group. First, consider the following question: what is the intersection of all closed-open neighborhoods of $1$? Of course it should contain the connected component of $1$ which is $\{1\}$. Then, the compactness implies that the intersection of all closed-open neighborhoods of $1$ is connected. Therefore, this intersection must be $\{1\}$.

Next, what's a neighborhood basis of $1$? An obvious one is the system of all closed-open neighborhoods of $1$. The continuousness of operations further implies that the subsystem of all closed-open subgroups of $G$ is also a neighborhood basis of $1$. 

One may noticed that any open subgroup $U$ of $G$ must be also closed since its complement is the union of the cosets of $U$ which are not $U$. Moreover, since $G$ is quasi-compact, there must be only finitely many cosets. Recall that for any subgroup, the intersection of all its conjugates is a normal subgroup. We see that any open subgroup of $G$ contains an open normal subgroup.

Note that for any open norm subgroup $U$ of $G$, $G/U$ is a finite quotient group of $G$. Thus we have a canonical homomoprhism $$
G\longrightarrow\varprojlim G/U.
$$ This homomorphism is injective. As $G$ is Hausdorff, any two elements of $G$ can be separated by two open sets. Since open normal subgroups form a neighborhood basis of $1$, we can shrink the two open sets to two cosets of an open normal subgroup $U$ of $G$. This homomorphism is also surjective by the quasi-compactness. As we are dealing with quasi-compact Hausdorff groups, which form a balanced category, we conclude that the above homomorphism is an isomorphism.

### Morphisms of profintie groups

Let $G, H$ be two profinite groups. Let's consider what's $\mathrm{Hom}(G,H)$?

First, we write $G$ and $H$ as $\varprojlim G/U$ and $\varprojlim H/V$ respectively. Then $$\mathrm{Hom}(G,H) = \mathrm{Hom}(\varprojlim_U G/U,\varprojlim_V H/V) = \varprojlim_V\mathrm{Hom}(\varprojlim_U G/U,H/V).$$

Since each $H/V$ is finite, we conclude that $$\mathrm{Hom}(G,H) = \varprojlim_V\varinjlim_U\mathrm{Hom}(G/U,H/V).$$

The above formula can help us to reduce problems from profinite groups to finite groups. For instance, recall that in the category of finite groups, *monomorphisms* (resp. *epimorphisms*) are injective (resp. surjective) homomorphisms. Thus the same statements hold for profinite groups.

### Indices of closed subgroups

Let $G$ be a profinite group and $H$ a closed subgroup of it. Recall that the **index** $(G:H)$ is defined to be the least common multiple of $(G:U)$ where $U$ goes over the family of open subgroups of $G$ containing $H$. In particular, $\\#G:=(G:1)$ is called the **order** of $G$.

The follwoing results follow from the defiinions and direct computations.

- Let $H,K$ be closed subgroups of $G$, hence also profinite. If $K<H$, then $(G:K) = (G:H)(H:K)$. If moreover, $K$ is normal in $G$, then $(G/K:H/K) = (G:H)$.
- A closed subgroup $H$ in $G$ is open if and only if $(G:H)$ is finite.
- If $\{H_i\}$ is a decreasing filtered family of closed subgroups in $G$ and $H = \bigcap_iH_i$, then $(G:H)$ is the least common multiple of $(G:H_i)$.
- If $G$ is a limit of profinite groups $G_i$ such that each transitaion map is surjective, then $\\#G$ is the least common multiple of $\\#G_i$.

### Pro-$p$-groups

Let $p$ be a prime number. Like profinite groups, a **pro-$p$ group** is a limit of finite *$p$ groups*. Note that this is equivalent to say $\\#G$ is a power of $p$. Then, for a profinite group $G$, the maximal pro-$p$ subgroups are called the **Sylow $p$ subgroups**. In more common setting, a **Sylow $p$ subgroup** is defined to be a closed subgroup $P$ of $G$ which is a pro-$p$ group and $p\nmid(G:P)$. The usual **Sylow Theorems** hold in this setting saying the equivalence of the above two definitions and that any two Sylow $p$ subgroups are conjugate.

## Reference

For the notion of profinite groups and supernatural numbers, see

- Michael D. Fried, Moshe Jarden, *Field Arithmetic*, Ergebnisse der Mathematik und ihrer Grenzgebiete 3, Folge 11 (3rd ed.), Springer-Verlag, 2008.