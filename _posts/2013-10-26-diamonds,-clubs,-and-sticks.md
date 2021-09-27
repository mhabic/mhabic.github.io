---
layout: post
title: "Diamonds, clubs, and sticks"
math: true
---

$\newcommand{\stick}{\mid\mspace{-7mu} {\raise0.6em\hbox{$\bullet$}}}$

I want to use this post to once and for all clear up any confusion I might have about what could be called the guessing principles of set theory. 
A secondary goal is to finally be able to claim that I have used the unique and amusing notation related to these principles.

I will restrict my attention to $\omega_1$; all of the principles generalize to larger cardinals (and restrict to stationary subsets etc.), 
but this basic case should be enough for an illustration.

So let's start. I should first explain what I meant by "guessing principles". Another fitting name would be "anticipatory principles". 
Imagine a situation where one is performing an inductive construction of length $\omega_1$, with the goal being that the final object will satisfy some universal property. 
A reasonable strategy is then to diagonalize against all possible counterexamples while performing the construction. 
However, it might happen that there are simply too many possible counterexamples to deal with in $\omega_1$ many steps. 
Nevertheless, it is often the case that we do not in fact need the entire putative counterexample to prevent it becoming a true counterexample, 
but only some small fragment of it. If we can additionally ensure that these are never resurrected as possible counterexamples, our plan will go through. 
The only missing part is a coherent way of producing the fragments of possible counterexamples and here is where guessing principles come in.

The simplest guessing principle is $\stick$ (called the stick principle). 
A $\stick$-sequence is a sequence $\langle A_\alpha;\alpha<\omega_1\rangle$ of infinite subsets of $\omega_1$ such that every uncountable 
$A\subseteq \omega_1$ contains some $A_\alpha$. We say that $\stick$ holds if there is a $\stick$-sequence.

It is easily seen that CH implies $\stick$. Indeed, CH implies that there are only $\omega_1$ many countable subsets of $\omega_1$, so all of these can be taken for our $\stick$-sequence. 
On the other hand, $\mathrm{MA}\_{\omega_1}$ implies $\lnot \mid\mspace{-12mu} {\raise0.6em\hbox{$\bullet$}}$ (the hypothesis here can be considerably weakened). 
To see this, let $\langle A_\alpha;\alpha<\omega_1\rangle$ be a sequence of infinite subsets of $\omega_1$ and consider the poset $\mathrm{Add}(\omega,\omega_1)$, 
seen as adding a subset of $\omega_1$. For any given $\alpha$ it is dense in this poset that $A_\alpha$ is not contained in the generic object and thus, 
by $\mathrm{MA}\_{\omega_1}$, the sequence of the $A_\alpha$ fails to be a $\stick$-sequence.

A stronger guessing principle is $\clubsuit$ (called the club principle). A $\clubsuit$-sequence is a sequence of sets $A_\alpha$, 
indexed by limit ordinals $\alpha<\omega_1$, such that $A_\alpha$ is a cofinal subset of $\alpha$ and each uncountable subset of $\omega_1$ 
contains some $s_\alpha$. We say that $\clubsuit$ holds if there is a $\clubsuit$-sequence.

Of course, $\clubsuit$ implies $\stick$. On the other hand, since both $\text{CH}+\lnot\clubsuit$ and $\lnot\mathrm{CH}+\clubsuit$ 
are consistent (as shown by Jensen and Shelah, respectively), $\stick$ is in fact strictly weaker than $\clubsuit$.

We can, without too much effort, extract an apparently stronger formulation of $\clubsuit$. 
The claim is that a $\clubsuit$-sequence actually gets into any uncountable subset of $\omega_1$ stationarily often. 
To see this, let $A\subseteq \omega_1$ be uncountable and $C\subseteq\omega_1$ be club. By thinning out $A$ if necessary, 
we can assume that any limit point of $A$ is also a limit point of $C$, and is thus in $C$. Since the $A_\alpha$ form a $\clubsuit$-sequence, 
we have $A_\alpha\subseteq A$ for some $\alpha$. But then $\alpha$ is a limit point of $A$ and is in $C$.

The third and most renowned guessing principle is $\diamondsuit$ (the diamond principle). A $\diamondsuit$-sequence is a sequence of sets 
$\langle A_\alpha;\alpha<\omega_1\rangle$ such that $A_\alpha\subseteq \alpha$ and for each $A\subseteq\omega_1$ we have 
$A\cap\alpha=A_\alpha$ for stationarily many $\alpha$. We say that $\diamondsuit$ holds if there is a $\diamondsuit$-sequence.

It is not difficult to see that $\diamondsuit$ implies $\clubsuit$. In fact, these two principles are equivalent in the presence of CH. 
To see this, we let $\langle A_\alpha;\alpha<\omega_1\rangle$ be an enumeration of all countable subsets of $\omega_1$ with cofinal repetition 
and define $D_\alpha=\bigcup_{\gamma\in B_\alpha}A_\gamma$, where $B_\alpha$ is an element of the $\clubsuit$-sequence. 
One can then show fairly easily that the $D_\alpha$ form a $\diamondsuit$-sequence.

There is a multitude of variations of $\diamondsuit$, where one is either allowed countably many guesses at each stage, 
or one attempts to guess club often or even guess club often while simultaneously guessing the club itself, but I think this short description will suffice for now.