---
layout: post
title: "I finally understand the Cantor--Schröder--Bernstein theorem"
math: true
---

The Cantor--Schröder--Bernstein theorem is fundamental to our understanding of cardinality. It essentially says that comparing cardinalities via injections gives rise to a sensible notion of size:

> **Theorem.** If $A$ and $B$ are sets and there are injections $f\colon A\to B$ and $g\colon B\to A$, then there is a bijection $h\colon A\to B$.

In other words, if a set $A$ is no bigger than another set $B$ and $B$ is no bigger than $A$, then they have the same size.

I saw a proof of this theorem towards the end of my first semester at university. I can't claim I understood it. It started by defining a countable collection of subsets of $A$, built out of applying $f$ and $g$ over and over. Somehow in the end, magically, this family of subsets gave rise to a bijection between $A$ and $g[B]$, and consequently between $A$ and $B$. But I was never comfortable about where the subsets came from and what the bijection $h$ is actually doing.

Since then I've seen other versions of the proof. Some of them work differently, by examining each element of $A$ and $B$, placing them in chains obtained by applying $f$ and $g$ successively, and then examining the type of these chains to define a bijection $h$. Others came with very elaborate and colorful pictures. Still others were versions of the argument in a different category (the Myhill isomorphism theorem in computability theory comes to mind). None of them really sparked understanding or gave me an intuitive idea of how the proof should work.

This semester I am teaching a tutorial in set theory, and as we were getting closer and closer to covering the Cantor--Schröder--Bernstein theorem, it seemed more and more urgent for me to actually understand what is going on in the proof. So I sat down, and found a proof (or at least a sketch of one) in which I actually understand where all the pieces come from.

*Proof:* We start with two injections $f\colon A\to B$ and $g\colon B\to A$ and we want to find a bijection $h\colon A\to B$. 
We will produce a series of approximation to $h$. First, we attempt to just use $f$, so we set $h_0=f$. But it might happen that $f$, and therefore $h_0$ is not surjective, meaning that $f[A]\neq B$. How will we hit all the $b$ that aren't in the range of $A$? The only reasonable option seems to be to use $g^{-1}$. It'll be convenient to call $B_0=f[A]=h_0[A]$ and $A_0=g[B\setminus B_0]$, so that our next approximation to $h$ will be $$h_1(a)=\begin{cases}g^{-1}(a);& a\in A_0\\ f(a);& a\notin A_0\end{cases}.$$
This function $h_1$ is onto $B\setminus B_0$ (because of the first clause), and one hopes that it will be onto $B_0$ as well. But that may not be the case, because $f$ needed all of $A$ as the domain to be onto $B_0$, and $A\setminus A_0$ might not be enough. On the other hand, we will be onto $B_1=f[A\setminus A_0]\subseteq B_0$. For the difference $B_0\setminus B_1$, we use $g^{-1}$ again, and define the next approximation as $$h_2(a)=\begin{cases} g^{-1}(a);& a\in A_0\cup A_1\\ f(a);& a\notin A_0\cup A_1\end{cases},$$
where $A_1=g[B_0\setminus B_1]$. Again, this $h_2$ is onto $B\setminus B_1$, but might not be onto all of $B$.

We continue in this way, making better and better approximations of our desired bijection $h$. In the end, the sequence builds a set $A_\infty=\bigcup_n A_n\subseteq A$, and we can define a function $$h_\infty(a)=\begin{cases} g^{-1}(a);& a\in C\\ f(a);& a\notin C\end{cases}.$$ It is then a routine (but good) exercise in set algebra to check that this really does define a bijection. $\square$

I'm not claiming this proof is new (in retrospect, all the ingredients were there in the other proofs I've seen), but the way it is structured, building better and better approximations to the desired bijection, makes it easier for me to understand where all the pieces are coming from and how they all fit together.