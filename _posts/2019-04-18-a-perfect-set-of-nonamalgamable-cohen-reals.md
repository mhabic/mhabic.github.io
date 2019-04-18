---
layout: post
title: "A perfect set of nonamalgamable Cohen reals"
math: true
---

Here is a fun fact: adding one Cohen real actually adds a perfect set of pairwise mutually generic Cohen reals (and not just pairwise, but any finitely many of them
are mutually generic). This is not hard to see; instead of forcing with the usual form of Cohen forcing, we pretend we are using the poset whose
conditions are finite 0-1-labellings of the full binary tree of height $\omega$. Both of these forcings are countable, and are therefore equivalent.
In the tree version we can, along any particular branch, meet any Cohen dense set; even more, given any two branches, we can wait until they split
and afterwards meet any dense set from the forcing to add two Cohen reals along them. So this tells us that the set of (labels along the) branches of
the generic labelling is a perfect set of pairwise mutually generic Cohen reals (it is perfect because the generic labelling gives a continuous injection
from the Cantor space onto this set of Cohen reals).

Depending on how you look at it, this result may or may not be satisfying. For example, let $M$ be a countable transitive model of set theory.
So if we add a Cohen real $c$ to $M$, we will have in $M[c]$ a perfect set of pairwise mutually generic Cohen reals. But $M[c]$ is still a countable model,
so what it thinks is a perfect set of Cohen reals over $M$ is really just a puny countable set. On the other hand, looking from the outside we know very well that
there are continuum (or even comeagerly) many Cohen reals over $M$. Can we find an actual, honest perfect (in $V$!) set of pairwise mutually generic Cohen reals over $M$?
The answer is yes, and we only need to modify the construction from before a bit. Let us first consider what goes wrong in the argument above. The reason why
that construction fails to produce uncountably many Cohen reals is that $M$ has no way of referring to the branches of the binary tree that are not in $M$.
There is no reason to expect that, following the generic labelling along such an external branch, we obtain a real which is in any way generic over $M$.
But we can solve this problem by realizing that meeting a Cohen dense set is a finitary matter, and the finite initial segments of these external branches *are*
in $M$.

So what do we do? Let me sketch a construction that will produce a generic labelling of the binary tree such that the reals along *any* two branches of it (even the ones that
are very foreign to $M$) will give a pair of mutually generic Cohen reals over $M$. First we enumerate all the dense open subsets $\langle D_n;n<\omega\rangle$ of the forcing 
to add two Cohen reals in $M$; we may as well assume that $D_{n+1}\subseteq D_n$. 
We will build our generic labelling step by step. 

Suppose we are in the $n$th step, we are looking at the dense set $D_n$ and we have
labelled the entire tree up to level $\ell_n$. Enumerate every pair of nodes $(s,t)$ on level $\ell_n$. For the first such pair $(s_0,t_0)$, the labelling constructed thus far
gives us a pair of Cohen conditions $(p_0,q_0)$ by reading the labels along the path in the tree from the root to the nodes $s_0$ and $t_0$. Let $(p_0',q_0')$ be a stronger condition
in $D_n$; we may assume that $|p_0'|=|q_0'|$. Now extend the labelling by making sure that below each (eventual) successor node of $s_0$ of height $|p_0'|$, the new labelling will give
the Cohen condition $p_0'$, and the same for $t_0$ and $q_0'$. What have we done? We have ensured that in the generic labelling, *any* two branches (even ones external to $M$)
going through the nodes $s_0$ and $t_0$ will yield a pair of reals that meets $D_n$.

We now repeat the same process with all the other pairs of nodes $(s_i,t_i)$ on level $\ell_n$. In these steps, we have to be a bit careful, since we already have some parts of the
tree above level $\ell_n$ labelled. Therefore, when we consider the pair $(s_i,t_i)$, we should assign it Cohen conditions $p_i$ and $q_i$, where $p_i$ is given by the tallest successor
of $s_i$ that has been labelled thus far (all of these successors will give the same condition), 
and the same for $q_i$ and $t_i$. The rest of the construction proceeds as before. So when we have run through all of the pairs of nodes on
level $\ell_n$, we can say that in the generic labelling, *any* pair of branches that split below level $\ell_n$ yields a pair of reals that meets $D_n$.

The construction now moves on to the next open dense set $D_{n+1}$. In the end we will have labelled the entire tree. Moreover, if $f$ and $g$ are any two branches through the tree,
even if they are not in $M$, they split below some level $\ell_n$, and our construction guarantees that the reals given by the labelling along $f$ and $g$ meet every dense open set after $D_n$,
and are therefore mutually generic Cohen reals over $M$ (again, the construction could have been modified to ensure that any finitely many branches give mutually generic Cohen reals over $M$).

This construction is quite flexible, and one can use it to make perfect sets of Cohen reals with other properties as well.
In our paper [Set-theoretic blockchains]({% link publications.md %}), my coauthors and I started from a countable model $M$ of set theory and
produced arrangements of Cohen reals over $M$ realizing various patterns of amalgamability. We call a collection $A$ of Cohen reals over $M$
*amalgamable* if there is a Cohen extension $M[c]$ of $M$ such that $A\subseteq M[c]$. We were particularly interested in ensuring that
some combinations of the Cohen reals were nonamalgamable, and we achieved this by splitting a very bad real (for example, one that would
reveal $M$'s countability to $M$) between some of the Cohen reals in such a way that each of them separately was completely unaware of this
hidden information, but together they could recover the coded real (using a real as in the example, we actually achieve a very strong form of nonamalgamability,
where the collection of Cohen reals cannot even appear in any model of set theory of the same height as $M$).$\newcommand{\rest}{\upharpoonright}$

Mostowski essentially already knew how to produce finitely many pairwise nonamalgamable Cohen reals over $M$. We managed to push his argument to
produce countably many pairwise nonamalgamable Cohen reals as well (among other arrangements). However, all of our arguments are based on
various product forcing methods, and these product forcing notions must, naturally, exist in $M$. In particular, the proofs do not directly produce more than
countably many (pairwise nonamalgamable, say) Cohen reals. But surely we should be able to get a larger set of Cohens, where we have some control over their amalgamability properties. 
Monroe Eskew asked me this question some time ago, and here is something we managed to prove.

> **Theorem.** Suppose that $M$ is a countable model of ZFC. Then there is a perfect set of pairwise nonamalgamable Cohen reals over $M$.

*Proof:* The proof is a combination of the argument sketched above and the *blockchain argument* from our paper. We again enumerate all the Cohen dense open sets in $M$, but we also fix a
very bad real $z$ as described above. We construct a labelling of the binary tree much as before, but with a little twist. So suppose that we are at stage $n$ of the construction,
we are looking at the dense open set $D_n$ and we have labelled the entire tree up to level $\ell_n$. Enumerate all the nodes $t$ of heigh $\ell_n$, and consider the first such node $t_0$.
The existing labels up to $t_0$ give a Cohen condition $p_0$ which can be extended to some $p_0'\in D_n$. Extend the labelling to make sure that every (eventual) successor of $t_0$ of height
$|p_0'|$ will give the condition $p_0'$ under the extended labelling, and also (and this is where we deviate from the previous construction) that every (eventual) successor of every other node
$t_i$ of height at most $|p_0'|$ gets labelled with 0.

We now do the same with all the other nodes $t_i$, with the same caveat as before: when assigning a Cohen condition to $t_i$, we take the one determined by the tallest successor of
$t_i$ that has been labelled thus far (and the choice of successor will not matter). The successors of $t_i$ then get labelled in order to match a condition in $D_n$, and the successors
of the other $t_j$ get labelled with 0 as far as necessary.

After all the nodes $t_i$ on level $\ell_n$ have been considered, let $c_n$ be the first level not coloured thus far. We label every node on level $c_n$ with 1s and every node
on level $c_n+1$ with the bit $z(n)$. The construction then moves on to the next step, considering $D_{n+1}$.

Ultimately, this process will label the entire tree. Moreover, any branch through the tree will give rise to a Cohen real over $M$, since no matter how the branch passed through level $\ell_n$,
we made sure that the labelling along the branch met the dense set $D_n$. Finally, if $f$ and $g$ are any two branches and they split below level $\ell_n$, then our construction made sure
that the only times after $\ell_n$ that both of these two branches got a nonzero label were at $c_i$ and $c_{i+1}$ for $i\geq n$. This means that from the Cohen reals given by these two branches,
we can recover (a tail segment of) the bad real $z$, which means that these Cohen reals are not amalgamable. $\Box$

One can combine the two proofs in various interesting ways to obtain other properties. For example, it is not too hard to go from the described to two perfect sets of Cohen reals over $M$,
such that within each set any finitely many are mutually generic, but no two from distinct sets are amalgamable.