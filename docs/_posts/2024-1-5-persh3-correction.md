---
layout: post
date: 2024-1-5
title: "Post 8: Correction to Perverse Sheaves Part 3"
permalink: /post8.html
katex: true
order: 8
---

You don't need to read this post if you read Part 3 after January 5 2024.

In my last post, Perverse Sheaves Part 3, I mistakenly gave this as the definition of equivalence of roof diagrams:

- Two roof diagrams from $X$ to $Y$, $(f:A\to Y, s:A\to X)$ and $(g:A\'\to Y,t:A\'\to X)$, are equivalent if there are morphisms $a:A\'\'\to A$ and $b:A\'\'\to A'$ in $S$ such that $s\circ a = t\circ b$ and $f\circ a=g\circ b$.

However, it has now been updated to say:

- Two roof diagrams from $X$ to $Y$, $(f:A\to Y, s:A\to X)$ and $(g:A\'\to Y,t:A\'\to X)$, are equivalent if there are morphisms $a:A\'\'\to A$ and $b:A\'\'\to A'$ such that $s\circ a = t\circ b$ is in $S$ and $f\circ a=g\circ b$.

I'm not 100% certain that these aren't equivalent, but just in case, I decided to correct it.

Thankfully, these conditions *are* equivalent when $S$ is the collection of quasi-isomorphisms in the homotopy category, which is why I made this mistake in the first place.