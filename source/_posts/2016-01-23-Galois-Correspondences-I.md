---
layout: post
title:  "Galois Correspondences I"
date:   2016-01-23
author: Gau, Syu
categories: Math
tags: [Category Theory, Algebra]
---

In this post, we discuss the fundamental theorem of Galois theory along the consideration of Galois connections.
<!-- more -->

## Galois Connections

**Definition:** An **(antitone) Galois connection** is a *dual adjunction* between posets. In other words, a Galois connection consists of the following data:

 - Two posets $A, B$,
 - Two order-reversing maps $f:A\to B$ and $g:B\to A$ ,
 such that
 - $a\le g(f(a))$ and $b\le f(g(b))$ for all $a\in A$, $b\in B$.

One can see that $f$ and $g$ automatically satisfy the *triangle identities*: $$f\circ g\circ f = f, \qquad g\circ f\circ g = g,$$ and thus form a dual adjunction between posets.

**Definition:** An **(antitone) Galois correspondence** is a *dual adjoint equivalence* between posets, that is a Galois connection such that  $f\circ g = 1$ and $g\circ f = 1$.

One can verify the following basic fact.
**Proposision:** Any Galois connection $(A,B,f,g)$ induces a Galois correspondence $(g(B),f(A),f,g)$. 
 
Recall that a dual adjoint functor maps colimits to limits and gives canonical morphisms from colimits to the image of limits. Thus we have
**Proposision:** Let $(A,B,f,g)$ be a Galois connection. Then for any $a_i\in A, b_j\in B$, we have
$$
\array{
f(\sup \\{a_i\\}) = \inf\\{f(a_i)\\},
&\quad&
f(\inf\\{a_i\\}) \ge \sup\\{f(a_i)\\},\\\
g(\sup\\{b_j\\}) = \inf\\{g(b_j)\\},
&\quad&
g(\inf\\{b_j\\}) \ge \sup\\{g(b_j)\\}.
}
$$

**Remark:** One can also consider the notions of *monotone Galois connections* and *monotone Galois correspondences*. 

## Galois Groups and Galois Extensions

Now we apply the above to algebraic field extensions. So throughout this section, every field extension is assumed to be algebraic.

### First Galois Correspondence

First, we have the folloing Galois connection: $$
\array{
\\{\text{subgroups of }\mathrm{Aut}(K)\\} & \longleftrightarrow &
\\{\text{subfields of }K\\}.\\\
G &
\longrightarrow &
K^G\\\
\mathrm{Gal}(K/F) &
\longleftarrow &
F.
}
$$ Here we use $\mathrm{Gal}(K/F)$ to denote the group of automorphisms of $K$ fixing $F$.

We define
**Definition:** A subgroup $G$ of $\mathrm{Aut}(K)$ is called a **Galois group** if $G=\mathrm{Gal}(K/F)$, where $F$ is a subfield of $K$. A field extension $K/F$ is called a **Galois extension** if $F=K^G$, where $G$ is a subgroup of $\mathrm{Aut}(K)$.

Then we obtain the Galois corresponding between Galois groups and Galois extensions. However, this correpondence is not the one the fundamental theorem of Galois theory states. To get it, we need to look closer. For the field extension side, we need to show that if $K/F$ is a Galois extension, then so are all $K/E$ where $E$ is an intermediate field of $K/F$. This follows immediately once one proves the following lemma.

**Lemma:** A field extension is a Galois extension if and only if it is the *splitting field* of a family of *separable polynomials*.
Note that, from this, one can see any Galois extension must be a *separable extension*.

For the subgroup side, one only need to notice that the Galois subgroups must be closed. Then, we get the Galois correspondence for a Galois extension $K/F$: 
$$
\array{
\\{\text{closed subgroups of }\mathrm{Gal}(K/F)\\} & \longleftrightarrow &
\\{\text{intermediate fields of }K/F\\}.\\\
H &
\longrightarrow &
K^H\\\
\mathrm{Gal}(K/E) &
\longleftarrow &
E.
}
$$

Note that under this corresponding, open subgroups of $\mathrm{Gal}(K/F)$ correspond finite subextensions of $K/F$.

### Second Galois Correspondence

Now, we restrict the map $H\mapsto K^H$ to the subposet of normal subgroups of $\mathrm{Gal}(K/F)$ and identify it with the opposite of the poset of quotient of $\mathrm{Gal}(K/F)$. Then, we have the following order-reversing map
$$
\array{
\\{\text{quotients of }\mathrm{Gal}(K/F)\\} & \longleftrightarrow &
\\{\text{intermediate fields of }K/F\\}.\\\
\mathrm{Gal}(K/F)/H &
\longmapsto &
K^H.
}
$$

One can see 
$$
\mathrm{Gal}(K^H/F) = \mathrm{Gal}(K/F)/H.
$$

In other word, $\mathrm{Gal}(K^H/F)$ is a quotient of $\mathrm{Gal}(K/F)$ with kernel $H$.

For an arbitrary field extension $E/F$, there is no need to be an epimorphism $$
\mathrm{Gal}(F)\longrightarrow\mathrm{Gal}(E/F).
$$ Here $\mathrm{Gal}(F)$ denotes the **absolutely Galois group** $\mathrm{Gal}(F\_{\mathrm{alg}}/F)$.
Note that, $\mathrm{Gal}(F\_{\mathrm{alg}}/F) = \mathrm{Gal}(F\_{\mathrm{sep}}/F)$, where $F\_{\mathrm{sep}}$ is the separable closure of $F$ and $F\_{\mathrm{sep}}/F$ is always Galois.

We define
**Definition:** A field extension $E/F$ is call a **normal extension** if any embedding $E\to F_{\mathrm{alg}}$ induces an automorphism of $E$ over $F$.
One can see that *Galois = normal + separable* if one has known the following lemma.
**Lemma:** A field extension is a normal extension if and only if it is the splitting field of a family of polynomials.

Now, one can now see that if $E/F$ is a normal extension, then there is a group homomorphism 
$$
\array{
\mathrm{Gal}(F) &
\longrightarrow &
\mathrm{Gal}(E/F). \\\
\sigma &
\longmapsto &
\sigma|_E,
}
$$ 

As any automorphism of a normal extension $E/F$ can be extended into an automorphism of $F_{\mathrm{alg}}/F$, the above homomorphism is surjective. The kernel of it is obviously the absolutely Galois group $\mathrm{Gal}(E)$.

In this way, we get a Galois connection:
$$
\array{
\\{\text{quotients of }\mathrm{Gal}(F)\\} & \longleftrightarrow &
\\{\text{normal extensions of }F\\}.\\\
\mathrm{Gal}(F)/H &
\longrightarrow &
F_{\mathrm{alg}}^H\\\
\mathrm{Gal}(E) &
\longleftarrow &
E.
}
$$

Let $K/F$ be another normal extension such that $E\subset K$. Then, by the Galois connection, we have $$\mathrm{Gal}(F\_{\mathrm{alg}}/K)<\mathrm{Gal}(F\_{\mathrm{alg}}/E).$$ Therefore there is a homomorphism $$
\mathrm{Gal}(K/F)\longrightarrow\mathrm{Gal}(E/F).
$$ fitting into the following commutative diagram $$
\array{
\mathrm{Gal}(F_{\mathrm{alg}}/F) \\\
\swarrow\qquad\qquad\searrow \\\
\mathrm{Gal}(K/F)\longrightarrow\mathrm{Gal}(E/F)
}
$$ and hence an epimorphism. In particular this holds for Galois extensions $K/F$.

In this way, we get a Galois correspondence:
$$
\array{
\\{\text{quotients of }\mathrm{Gal}(K/F)\\} & \longleftrightarrow &
\\{\text{normal subextensions of }K/F\\}.\\\
\mathrm{Gal}(K/F)/H &
\longrightarrow &
K^H \\\
\mathrm{Gal}(K/E) &
\longleftarrow &
E.
}
$$

### The Degree Encoding

Let $K/F$ be a field extension. The poset of closed subgroups of $G=\mathrm{Gal}(K/F)$ admits an order-preserving map $H\mapsto|H|$ and an order-reversing map $H\mapsto[G:H]$ to the poset of *supernatural numbers*. Moreover, we have
$$
|G| = |H|\cdot[G:H].
$$

Likewise, the poset of intermediate fields $E$ of $K/F$ admits an order-reversing map $E\mapsto[K:E]$ and an order-preserving map $E\mapsto[E:F]$ to the poset of supernatural numbers and we have
$$
[K:F] = [K:E]\cdot[E:F].
$$

The Galois correspondences suggest us to compare them. This is what Artin's theorem says.

**Artin's Theorem:** Let $K$ be a field and $G$ a closed subgroup of $\mathrm{Aut}(K)$. Then 
$$
|G| = [K:K^G].
$$ 

Note that when apply to Galois extensions $K/F$, the theorem implies
$$
|H| = [K:K^H],
\quad\text{and}\quad
[G:H] = [K^H:F].
$$

This post is long enough, so we may stop here.

## Reference

For the missing notions and proofs in algebra, see any textbook such as

- Serge Lang, *Algebra*, 3rd ed., Addison-Wesley, 1993.

As for the infinite case of Galois theory, especially the notion of profinite groups and supernatural numbers, see

- Michael D. Fried, Moshe Jarden, *Field Arithmetic*, Ergebnisse der Mathematik und ihrer Grenzgebiete 3, Folge 11 (3rd ed.), Springer-Verlag, 2008.