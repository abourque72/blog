---
layout: post
date: 2022-12-23
title: "Post 2: Current Research"
permalink: /2023-12-23.html
katex: true
order: 2
---

In this post I'll talk about my current research project.

I work with [Pramod Achar](https://www.math.lsu.edu/~pramod/){:target="_blank"}{:rel="noopener noreferrer"} (opens in new tab). Our goal is to give explicit models for so-called "global Schubert varieties" for $GL_n$. Let me first give intuition for these words (I will try to write so that an undergraduate that has taken classes in group theory and topology can get some ideas), and then I'll talk specifics.

# Intuition

## Algebraic groups

I was originally going to put this in the "formal" section, but truth be told I don't feel like explaining it formally. I also think it would be good for some undergrad readers to get intuition about this. The most familiar example of an algebraic group is \\(GL_n\\). You might be used to seeing notation like \\(GL_n(\R)\\) or \\(GL_n(\mathbb C)\\), which tells you what the entries of the matrices are allowed to be (e.g. real numbers or complex numbers). The algebraic group \\(GL_n\\) takes this a step back and essentially packages all of the groups \\(GL_n(R)\\) for rings (or really algebras over a ground field) into one object. Formally, it is a functor, or even a scheme. But the idea you should have is that, for any ring \\(R\\), an algebraic group \\(G\\) has a corresponding group \\(G(R)\\). There is extra compatibility (functoriality) and niceness (like being a scheme, and particularly reductiveness) that one often imposes, but \\(GL_n\\) has these properties, and we won't be mentioning them explicitly.

## Explicit models

What is an "explicit model"? To put it simply, the objects we are studying are defined in a very arcane way, and we want to find a simpler way to describe it. I don't really have any good examples of what this means, so hopefully you can piece together what I mean from my own work.

## Global Schubert varieties

What is a "global Schubert variety"? Well, before I get into specifics, I will talk about the steps involved to define it.

Global Schubert varieties live inside of the global affine Grassmannian. The global affine Grassmannian is made out of copies of the affine Grassmannian and a copy of the affine flag variety. We will also need to discuss the (spherical) Schubert cells and varieties, which live in the affine Grassmannian. Remember, everything we will do is for \\( GL_n \\).

The affine Grassmannian, \\( \mathcal Gr \\), is a certain topological space with a group action. The orbits of this group action are the (spherical) Schubert cells, denoted by \\( \mathcal Gr_\lambda \\). The parameter \\(\lambda\\) is a non-increasing sequence of \\(n\\) integers. The (spherical) Schubert varieties are the closures of these orbits.

The affine Grassmannian can be defined for any (sufficiently nice) algebraic group. In the case \\( GL_n \\), the affine Grassmannian can be identified with the set of objects called lattices. In other words, lattices allow us to give an explicit model for the affine Grassmannian of \\( GL_n \\). It is well-known what the conditions on a lattice are for it to be in the Schubert cells or varieties.

The affine flag variety, \\( \mathcal Fl \\), is similar. Of utmost importance is the explicit model we give it. In particular, for \\( GL_n \\), we can identify \\( \mathcal Fl \\) with the set of lattice chains. These are lists of \\( n \\) lattices with some extra conditions.

Finally, the global affine Grassmannian \\( \mathbf{Gr} \\) is built out of \\( \mathcal Gr \\) and \\( \mathcal Fl \\) in the following way: There is a continuous map $$ p:\mathbf{Gr}\to \mathbb C $$ such that

$$ p^{-1}(0)\cong \mathcal Fl, $$

$$ p^{-1}(\mathbb C^\times) \cong \mathbb C^\times \times \mathcal Gr. $$

Here, \\( \mathbb C^\times \\) is the set of non-zero complex numbers.

Here comes the hilarious part: even though I've been working on this project for almost two years, we only recently (within the month) realized that the objects that we've been using to understand \\(\mathbf{Gr}\\) were incorrect. By objects, I mean something like lattices or lattice chains. Because of the definition of \\(\mathbf{Gr}\\), we want some kind of object that depends on a complex number \\(y\\) and interpolates between lattices (when \\(y\neq0\\)) and lattice chains (when \\(y=0\\)). We originally used something called "\\(y\\)-lattice chains", but it turns out this gave us results that did not match up with pre-existing (and correct) results. Instead, we needed something that we call a "lattice family", which consists of a complex number and \\(n\\) lattices satisfying some extra conditions.

Anyway, now I can finally (loosely) define the global Schubert varieties. Under the isomorphism \\(p^{-1}(\mathbb C^\times)\cong \mathbb C^\times\times \mathcal Gr \\), we can consider \\(\mathbb C^\times\times\mathcal Gr_\lambda\\) as a subset of \\(\mathbf{Gr}\\). Its closure is what we call a global Schubert variety.

To reiterate, the goal of our project is to determine the conditions on a lattice family that tell you whether or not it is in a given global Schubert variety. To that end, we are almost done.

# Formal stuff

Now we go back through all of the previous talk with some actual math. While I tried to make the previous section undergrad-friendly, I make no attempt to do so in this section. In particular, I will use some buzz words that may mean nothing to an undergrad student, especially one that hasn't done much representation theory. However, if one ignores the fancy lingo and follows the math, it actually isn't too bad. One still only needs first courses in algebra and topology (I think). So, if you are reading this as an undergrad - try your best!

## Lattices and affine Grassmannians

We will use the power series ring \\(\mathbb O = \mathbb C[[t]]\\) and its fraction field, the Laurent series \\(\mathbb K = \mathbb C((t))\\). Also, fix positive integer \\(n\\) (for our \\(GL_n\\) in consideration).

A *lattice* is a free rank \\(n\\) \\(\mathbb O\\)-submodule of \\(\mathbb K^n\\). In particular, a lattice can be given by a \\(\mathbb K\\)-basis for \\(\mathbb K^n\\); it is the \\(\mathbb O\\)-span of that basis. The *standard lattice* is \\(\mathbb O^n\\), which corresponds to the standard basis \\(e_1,\dots,e_n\\).

The *affine Grassmannian* of an algebraic group \\(G\\) is the quotient \\(G(\mathbb K)/G(\mathbb O)\\). In the case \\(G=GL_n\\), this can be identified with the set of lattices. The reason for this is the orbit-stabilizer theorem: the group \\(GL_n(\mathbb K)\\) acts transitively on the set of lattices, and the stabilizer of any particular lattice is isomorphic to \\(GL_n(\mathbb O)\\). In fact, the stabilizer of \\(\mathbb O^n\\) is *exactly* \\(GL_n(\mathbb O)\\).

By construction, there is a natural action of \\(G(\mathbb O)\\) on \\(\mathcal Gr\\). The (spherical) (I will not use the word spherical anymore) *Schubert cells* \\(\Gr_\lambda\\) are the $$G(\O)$$-orbits, and they are labeled by dominant coweights $$\lambda$$ of \\(G\\). I won't explain what (dominant) coweights are in general, nor do you need to know what they are. For \\(GL_n\\), dominant coweight has a simple meaning (at least, up to an identification): it is a non-increasing sequence of \\(n\\) integers, written as \\(\lambda=(\lambda_1\geq\dots\geq\lambda_n)\\).

For each dominant coweight $\lam$, there is a convenient representative for $\Gr_\lam$. Let $\L^\lam$ be the lattice corresponding to the basis $t^{\lam_1}e_1,\dots,t^{\lam_n}e_n$. Then $\Gr_\lam$ is the $GL_n(\O)$-orbit of $\L^\lam$.

This definition is not hard to state, but at first glance it doesn't tell you much. If I give you a lattice $\L$, how can you tell if it is in $\Gr_\lam$ for some dominant coweight $\lam$? Luckily, there is a very nice description:

$$\Gr_\lam=\left\{ \L\in\Gr\mid t^{\lam_1}\O^n\subset \L \subset t^{\lam_n}\O^n \text{ and } \dim\frac{\L\cap t^i\O^n}{t^{\lam_1}\O^n}=\sum_{j=i}^{\lam_1-1}|\{ k\mid \lam_k\leq j \}|\right\}.$$

The second condition must hold for all integers $i$ satisfying $\lam_n\leq i\leq \lam_1$.

We also care about the *Schubert variety* associated to $\lam$, $\ol{\Gr_\lam}$. Once again, there is a nice description of this space:

$$\ol{\Gr_\lam}=\left\{ \L\in\Gr\mid t^{\lam_1}\O^n\subset \L \subset t^{\lam_n}\O^n \text{ and } \dim\frac{\L\cap t^i\O^n}{t^{\lam_1}\O^n}\ge\sum_{j=i}^{\lam_1-1}|\{ k\mid \lam_k\leq j \}|\right\}.$$

The second condition must hold for all integers $i$ satisfying $\lam_n\leq i\leq \lam_1$.

## Lattice chains and affine flag varieties

The assignment $t\mapsto 0$ induces a ring homomorphism $\O\to \C$, and that induces a map $\pi:G(\O)\to G(\C)$. Pick a Borel subgroup $B$ of $G$, and let $I=\pi^{-1}(B(\C)$. $I$ is called an Iwahori subgroup. The *affine flag variety* $\Fl$ of $G$ is then $G(\K)/I$.

If you don't know what a Borel subgroup is, that's fine. For $G=GL_n$, we pick $B$ to be the subgroup consisting of lower triangular matrices. That is, for each ring $R$, $B(R)$ is the group of invertible lower triangular matrices with entries in $R$. Correspondingly, $I$ will consist of elements in $GL_n(\O)$ that are "lower triangular mod $t$".

Furthermore, we can identify $\Fl$ with the set of lattice chains. A *lattice chain* $\ul\L$ is a nested sequence of $n$ lattices $L_1\supset L_2\supset\cdots \supset L_n$, with the further conditions that $L_n\supset tL_1$ and $\dim(L_i/L_{i+1})=1$ for $i= 1,\dots,n-1$. It also follows that $\dim(L_n/tL_1)=1$. The reasoning for the identification is the same as that with identifying $\Gr$ with the set of lattices. In particular, $I$ is the stabilizer of the *standard lattice chain*:

$$\O^n\supset t\O\oplus \O^{n-1}\supset\cdots\supset t\O^{n-1}\oplus\O.$$

## The end and global affine Grassmannian

Now, correctly defining the global affine Grassmannian $\bGr$ is beyond my own capability. You can find the original construction in Dennis Gatisgory's paper ["Construction of central elements in the affine Hecke algebra via nearby cycles"](https://arxiv.org/abs/math/9912074) (opens in new tab), or you can find a more expository (but still difficult) treatment in the in-progress book of Pramod Achar and Simon Riche, ["Central Sheaves on Affine Flag Varieties"](https://lmbp.uca.fr/~riche/central.pdf){:target="_blank"}{:rel="noopener noreferrer"} (opens in new tab and downloads pdf).

In any case, I will say that the core idea of $\bGr$ is that which I described in the previous section. Namely, it has a map to $\C$, such that over any non-zero complex number it looks like $\Gr$, and over $0$ it looks like $\Fl$.

Since our explicit model of $\bGr$ is in-progress, I am going to end the discussion here (just in case our ideas are wrong, again). However, I will definitely continue this post when we have checked our work!