---
layout: post
date: 2024-2-5
title: "Post 16: Overview of Infinity Categories"
permalink: /post16.html
katex: true
order: 16
---

In this post, I'll give an overview of the theory of infinity categories. In particular, I won't get into too many specifics. I will also start with some recollection of ordinary category theory, in case an interested reader has not seen it before.

---

Note for experienced readers: I'll be ignoring set theoretic (size) issues.

Note for the non-experienced readers: I will use vague words like "collection" that could be precisely defined (replacing it with "class" or "set" or "fixing a universe"), but I will not bother. These "collections" will have a notion of equality, i.e. a notion of saying when two elements of the collection are the same.

---

# Ordinary categories

Roughly speaking, a category consists of two collections and an operation: a collection of *objects*, a collection of *morphisms*, and an operation of *composition*.

A morphism has two objects of the category associated with it, called its domain and codomain. To say that morphism $f$ has domain $A$ and codomain $B$, we simply write $f:A\to B$. For each object $A$, there is a distinguished *identity* morphism $1_A:A\to A$.

Composition takes in two morphisms $f:A\to B$ and $g:B\to C$ and gives a unique morphism $g\circ f:A\to C$. Composition must satisfy two conditions:

1. For every morphism $f:A\to B$, we must have $1_B\circ f = f$ and $f\circ 1_A=f$.

2. For all morphisms $f:A\to B$, $g:B\to C$, $h:C\to D$, we must have $(h\circ g)\circ f = h\circ(g\circ f)$.

As some examples, sets and functions form a category, groups and group homomorphisms form a category, and topological spaces and continuous maps form a category.

Here is a definition that isn't strictly needed for us, but I will refer to it later:

- A morphism $f:A\to B$ is an *isomorphism* if there is a morphism $g:B\to A$ such that $f\circ g = 1_B$ and $g\circ f = 1_A$. Objects $A$ and $B$ are *isomorphic* if there is an isomorphism $f:A\to B$.

---

# Approaching $n$-categories

Now let's start to get meta. Is there a notion of morphism between categories? Yes. Roughly speaking, it must send objects to objects and morphisms to morphisms, in such a way that identity morphisms are sent to identity morphisms, and compositions are sent to compositions. Here is the full definition:

Given categories $\mc C$ and $\mc D$, a *functor* from $\mc C$ to $\mc D$, denoted by $F:\mc C\to \mc D$, consists of the following data:

- For each object $A$ of $\mc C$, there is an associated object $F(A)$ of $\mc D$.

- For each morphism $f:A\to B$ of $\mc C$, there is an associated morphism $F(f):F(A)\to F(B)$ of $\mc D$.

Furthermore, the data is subject to the following constraints:

- For all objects $A$ of $\mc C$, we have $F(1_A)=1\_{F(A)}$.

- For all morphisms $f:A\to B$ and $g:B\to C$ of $\mc C$, we have $F(g\circ f) = F(g)\circ F(f)$.

Now, up to certain size-related paradoxes, we could consider a category whose objects are categories and whose morphisms are functors. There is actually one very special feature of this "category". Namely, there is a notion of morphism between functors:

Given two functors $F,G:\mc C\to \mc D$, a *natural transformation* from $F$ to $G$, denoted $\eta:F\to G$, is the following collection of data:

- For each object $A$ of $\mc C$, an associated morphism $\eta(A):F(A)\to G(A)$ of $\mc D$.

Furthermore, we must have the following constraint:

- For each morphism $f:A\to B$ of $\mc C$, we must have $\eta(B)\circ F(f)=G(f)\circ\eta(A)$.

Let us return back to the main picture: we have a "category" whose objects are categories, but not only are there morphisms, there are also morphisms between morphisms! In particular, we have found a natural example of a *2-category*. To contrast, an ordinary category would be called a 1-category. The morphisms in a 2-category are sometimes called *1-morphisms*; the morphisms between morphisms are *2-morphisms*.

One can play this same game and try to axiomatize $n$-categories for all positive integers $n$. To construct examples and/or motivate the definitions, one could for instance develop a notion of functors between $(n-1)$-categories that ensures that the category of $(n-1)$-categories is an $n$-category.

This idea naturally gets very messy, very fast. However, if one tries to extend this notion to infinity, somehow things aren't so bad.

Warning: I'm now going to talk about infinity categories as if we have defined them, but we haven't! Just keep that in mind.

# Topological ideas

Infinity category theory is rooted in topology, specifically homotopy theory. In ordinary category theory, one often deals with *commutative diagrams* that enforce equality on some morphisms. On the other hand, topologists may want to consider situations where things aren't equal, but equal "up to homotopy". Furthermore, if you have a diagram that has a bunch of pieces that should be "homotopy commutative", you want to make sure that the various homotopies are compatible, or "coherent". It turns out that working in an infinity category is (one of) the "right" way(s) to do this.

On the other hand, you don't need to know homotopy theory (or really any topology) to be able to work with infinity categories. Just know that a lot of the language and motivation comes from homotopy theory.

There are two key examples of infinity categories that really illustrate how the theory mixes ordinary categories and topology. You can make an infinity category out of an ordinary category, and you can make an infinity category out of a topological space. In particular, given a category $\mc C$, there is an infinity category $N(\mc C)$ called the *nerve* of $\mc C$, and given a topological space $X$, there is an infinity category $\text{Sing}(X)$ called the *singular simplicial set* of $X$.

$\text{Sing}(X)$ belongs to a special class of infinity categories, called *Kan complexes*. Kan complexes are often referred to as spaces, since they share a lot of features with ordinary topological spaces. For instance, you can define their homotopy groups, and for $\text{Sing}(X)$, you recover (up to isomorphism) the homotopy groups of $X$.

Another thing you can do is construct a category out of an infinity category. In particular, there is a notion of homotopy between 1-morphisms $f,g:x\to y$ in an infinity category $\mc C$. The collection of objects and homotopy classes of 1-morphisms forms an ordinary category, called the *homotopy category* of $\mc C$.

---

# Definitions modulo details

Without getting into too much detail, let me give some definitions and state an important result. We will work in the category $\mc S$ of *simplicial sets*; I won't define these, and I don't want you to focus on what they are. Within this category are distinguished objects $\Delta^n$ and $\Lambda^n_j$, for all non-negative integers $j,n$ with $j\leq n$. Furthermore, for each non-negative $j,n$ with $0\leq j\leq n$, there is a natural morphism $i^n_j:\Lambda^n_j\to \Delta^n$.

We say that a simplicial set $\mc C$ is an *infinity category* if for any morphism $f:\Lambda^n_j\to\mc C$ with $0 \< j \< n$, there is a morphism $f':\Delta^n\to\mc C$ such that $f=f'\circ i^n_j$. Furthermore, $\mc C$ is a *Kan complex* if the above property is true when $j$ is also allowed to be $0$ or $n$.

Take it on faith that with the above definition, one can define the notions of 1-morphisms in an infinity category, and also what it means for a 1-morphism to be an isomorphism. We say that an infinity category $\mc C$ is an *infinity groupoid* if all 1-morphisms in $\mc C$ are isomorphisms. The following result is surprising (to me) and not easy to prove:

- An infinity category is a Kan complex if and only if it is an infinity groupoid.

---

# More topology - universal properties

Another instance of topology at play is with "mapping spaces". Often times we want to study the collection of morphisms between two objects in a category. Given an infinity category $\mc C$ and two objects $x,y$ of $\mc C$, one can define a simplicial set $\text{map}\_{\mc C}(x,y)$ that "morally" encodes the information of all morphisms between $x$ and $y$. A surprising result is this:

- $\text{map}\_{\mc C}(x,y)$ is a Kan complex.

Roughly speaking, this tells us that there is a (topological) space of morphisms from $x$ to $y$. One interesting point is that we use this to define universal properties in infinity categories. If you haven't seen universal properties, then compare the following two definitions:

1. An object $x$ in a category $\mc C$ is *initial* if for all objects $y$ in $\mc C$, there is a unique morphism $x\to y$.

2. An object $x$ in an infinity category $\mc C$ is *initial* if for all objects $y$ in $\mc C$, the mapping space $\text{map}\_{\mc C}(x,y)$ is contractible, meaning that all of its homotopy groups are trivial.

In other words, we replace uniqueness for contractibility. In ordinary topology, contractibility is equivalent to being homotopy equivalent to a point. Thus, one way to interpret $\text{map}\_{\mc C}(x,y)$ being contractible is that there is a unique morphism $x\to y$ *up to homotopy*.

---

# Classic results

I will mention here some classical category theory results that have counterparts in infinity category theory world:

- Yoneda's lemma

- A functor is an equivalence if and only if it is fully faithful and essentially surjective.

---

# Homological algebra

Warning: It is very possible that this section will make absolutely no sense; I'm not going to attempt to make it understandable for a general audience.

One of the reasons I am interested in infinity categories is that it provides a better setting for homological algebra than ordinary category theory. To quote Lurie, one of the problems with ordinary derived categories is that they "identify homotopic morphisms of chain complexes without remembering *why* they are homotopic". Some other problems are that the octahedral axiom for triangulated categories is an abomination, cones are not functorial, and the structure of a triangulated category consists of extra data, instead of satisfying certain properties.[^dts]

[^dts]: Namely, to define a triangulated category, you need to specify your distinguished triangles. It is not simply a category that satisfies special conditions.

The remedy is to study a certain class of infinity categories, namely the *stable* infinity categories. For a given abelian category $\mc A$, there is a stable infinity category $^\infty D(\mc A)$ whose homotopy category (defined earlier) is the ordinary derived category $D(\mc A)$. More generally, the homotopy category of a stable infinity category has a natural triangulated structure. You can also define $t$-structures.

The conditions for an infinity category to be stable are relatively pleasant, especially when compared to the axioms for triangulated categories.

Stable infinity categories also provide a natural setting for spectra in homotopy theory. Furthermore, there is a whole field of "higher algebra" where one "generalizes" algebraic structures to the infinity category world. I may write more on this in the future.

---

Footnotes: