---
layout: post
title: "Characterizing forcing extensions"
math: true
---

Last week at the CUNY set theory seminar I presented a proof of an old theorem of Bukovský, which characterises those pairs of models which are set-generic extensions. It turns out that these are precisely those pairs which satisfy a familiar covering property. This result, which seems to have been forgotten for a while, has gathered attention recently, particularly (as far as many of the people at CUNY are concerned) due to its use by Usuba in his work on set-theoretic geology and proving the downward directed grounds hypothesis. In my presentation I didn’t quite get to lay out everything as neatly as I would have liked, so I am writing this post in the hope of giving a fuller account.

As mentioned, the key property that Bukovský isolated is a kind of covering property between a pair of models. We may focus on the case of the relationship between the universe $V$ and an inner model $M\subseteq V$; for us an *inner model* will be a transitive proper class model of ZFC. We work throughout in GBC (we can even dispense with class choice), so, in particular, there is no need for inner models to be definable.

> **Definition 1.** Let $M\subseteq V$ be an inner model and let $\kappa$ be regular in $M$. We say that $M$ uniformly $\kappa$-covers $V$ if for any function $f\colon \alpha\to M$ with $\alpha$ an ordinal and $f\in V$ there is another function $F\colon \alpha\to M$ in $M$ such that $f(\xi)\in F(\xi)$ and $\|F(\xi)\|^M<\kappa$ for all $\xi<\alpha$.

That is to say, $F\in M$ covers the function $f\in V$, giving fewer than $\kappa$ many guesses at each coordinate. This property is well-known to all students of forcing and all the introductory texts that I know present the following key fact.

> **Theorem 2.** Let $\mathbb{P}$ be a $\kappa$-cc poset and let $G\subseteq\mathbb{P}$ be generic over $V$. Then $V$ uniformly $\kappa$-covers $V[G]$.

*Proof:* Fix a function $f\colon \alpha\rightarrow V$ in $V[G]$ and a name $\dot{f}$ for it. There is some $\gamma$ so that it is forced that $\dot{f}$ maps into $V_\gamma$. We can thus find, for each $\xi<\alpha$, a maximal antichain $Z_\xi\subseteq\mathbb{P}$ deciding the values of $\dot{f}(\xi)$. Now we just let $F(\xi)$ be the set of the possible values given by the conditions in $Z_\xi$. $\Box$

Bukovský's remarkable result is that the uniform covering property precisely characterises the set-forcing extensions.

> **Theorem 3.** (Bukovský, 1973) Let $M\subseteq V$ be an inner model and let $\kappa$ be regular in $M$. The following are equivalent:
>
>1. $V$ is a $\kappa$-cc generic extension of $M$; that is, there are a poset $\mathbb{P}\in M$ and a filter $G\in V$ such that $\mathbb{P}$ is $\kappa$-cc in $M$ and
>$G\subseteq \mathbb{P}$ is generic over $M$ and $V=M[G]$.
>
>2. $M$ uniformly $\kappa$-covers $V$.

We already saw the forward implication as theorem 2. The majority of the work, not surprisingly, goes into proving the converse. Starting from the hypothesis that $M$ uniformly $\kappa$-covers $V$, the argument can be divided into three fairly self-contained steps:

1. If $A\in V$ is a set of ordinals (or even $A\subseteq M$) then $M(A)$ is a $\kappa$-cc generic extension of $M$. Here $M(A)$ is the least transitive model of ZFC
extending $M$ and containing $A$.

2. There is a set of ordinals $A\in V$ such that $M(A)$ is a terminal $\kappa$-cc generic extension of $M$; that is, there is no inner model $N$ such that $M\subset N\subseteq V$ and $M(A)\subseteq N$
is a $\kappa$-cc generic extension.

3. If $M(A)$ is the terminal extension from the previous step, then $M(A)=V$.

As it turns out, step 1 is the hardest to prove. Therefore we shall make the steps in reverse, starting from 3 and working our way back to 1.

Step 3 follows quite easily from the other two. Specifically, assume that $M(A)\neq V$. Since all of our models satisfy choice, there must be a set of ordinals $B\in V\setminus M(A)$. If we knew that $B$ was $\kappa$-cc generic over $M(A)$, this would contradict our assumption on the maximality of $M(A)$.

> **Lemma 4.** Suppose $M$ uniformly $\kappa$-covers $V$ and $M\subseteq N\subseteq V$ and $\kappa$ remains regular in $N$. Then $N$ uniformly $\kappa$-covers $V$.

*Proof:* Fix a function $f\colon \alpha\to N$ in $V$. There is an ordinal $\gamma$ such that the range of $f$ is contained in $V_\gamma^N$. Let us pick an injection $\psi\colon V_\gamma^N\to \mathrm{Ord}$ in $N$. Since $M$ uniformly $\kappa$-covers $V$ we can find a covering function $F\colon \alpha\to \mathrm{Ord}$ for $\psi\colon f$ in $M$. But then the function $\xi\mapsto \psi^{-1}[F(\xi)]$ is a covering function for $f$ in $N$. $\Box$

Returning to the argument from before, we can now apply step 1 to the pair $M(A)\subseteq V$ to conclude that $B$ really is $\kappa$-cc generic over $M(A)$, giving us the contradiction and completing step 3.

The key realisation for step 2 is the following lemma:

> **Lemma 5.** Let $\mathbb{P}$ be a separative $\kappa$-cc poset. Then $\mathbb{P}$ adds a subset of $\kappa$.

*Proof:* It shall suffice to prove that $\mathbb{P}$ is not $\leq\kappa$-distributive. This is because, if $\mathbb{P}$ adds a function $f\colon \kappa\to\mathrm{Ord}$,
then the range of $f$ can be covered by a set of size $\kappa$ in $V$, by theorem 2. Modulo some coding, the function $f$ is then determined by a subset of this covering set.

So now assume toward a contradiction that $\mathbb{P}$ is $\leq\kappa$-distributive. This means that any family of at most $\kappa$ many maximal antichains in $\mathbb{P}$ has a
common refinement. This allows us to build a tree $T$ in $\mathbb{P}$ as follows:

* the root of $T$ is the top condition of $\mathbb{P}$;
* every node in $T$ has at least two immediate successors;
* every level of $T$ is a maximal antichain in $\mathbb{P}$.

We can build $T$ inductively; the successor steps are easy and we use distributivity to pass through limit steps. Specifically, $\leq\kappa$-distributivity allows us to build the tree $T$ up to height (at least) $\kappa+1$. But now take any condition $p$ from the $\kappa$th level of $T$ and consider the branch it determines through $T$. Since every node on the branch is splitting, any one-off-the-branch antichain determined by this branch will have size $\kappa$. But this of course contradicts the $\kappa$-cc. $\Box$

Seen differently, the proof basically shows that a $\kappa$-cc poset cannot be $(\kappa,\kappa)$-distributive.

Let $A\in V$ be a set of ordinals coding $\mathcal{P}(\kappa)$, so that $\mathcal{P}(\kappa)^V\in M(A)$. We claim that $M(A)$ is the required terminal $\kappa$-cc extension of $M$. The set $A$ is definitely $\kappa$-cc generic over $M$ by step 1. On the other hand, if $M(A)$ were not terminal, there would be a further $\kappa$-cc generic extension $M(A)\subseteq N\subseteq V$ and, by lemma 5, there must be a new subset of $\kappa$ in $N$. But $M(A)$ contains all the subsets of $\kappa$ in $V$ by construction. This completes step 2.

In order to deal with step 1 with some elegance we need to introduce some terminology.

> **Definition 6.** Let $\kappa,\lambda$ be cardinals. We shall denote by $\mathbb{B}(\kappa,\lambda)$ the free $\kappa$-complete Boolean algebra on the generators $e_\alpha$ for $\alpha<\lambda$.

By $\kappa$-complete we mean that suprema of sets of size less than $\kappa$ exist. Freeness can be interpreted in two ways. We can think of it in terms of a universal property: any map of the generators into a $\kappa$-complete Boolean algebra extends to a $\kappa$-complete homomorphism on the whole $\mathbb{B}(\kappa,\lambda)$. Alternatively, we can think of $\mathbb{B}(\kappa,\lambda)$ as being built in stages, starting from the generators and at each stage taking complements and size $<\kappa$ suprema of what we had constructed before, and modding out by the minimal obvious relations. This latter viewpoint suggest yet another one. We can also view the generators $e_\alpha$ for $\alpha<\lambda$ as representing the propositional formulas $\alpha\in \dot{A}$, where $\dot{A}$ is a predicate, and $\mathbb{B}(\kappa,\lambda)$ being the Lindenbaum algebra of infinitary formulas built from these atomic formulas via negations and size $<\kappa$ disjunctions. In my talk I suggested that $\mathbb{B}(\kappa,\lambda)$ could, for intuitive purposes, be replaced by $\mathrm{Add}(\kappa,\lambda)$, but this is misleading, as I will discuss after theorem 7.

Note that, if $\kappa<\kappa'$, then $\mathbb{B}(\kappa,\lambda)$ embeds as a $\kappa$-complete subalgebra into $\mathbb{B}(\kappa',\lambda)$. We will henceforth see these algebras as nested. There is also another kind of nesting.

> **Theorem 7.** Let $M$ be an inner model. Then $\mathbb{B}(\kappa,\lambda)^M$ embeds into $\mathbb{B}(\kappa,\lambda)^V$ as an $M$-$\kappa$-complete subalgebra; that is, there is a homomorphism
> $f\colon\mathbb{B}(\kappa,\lambda)^M\to\mathbb{B}(\kappa,\lambda)^V$ such that for any set $X\subseteq\mathbb{B}(\kappa,\lambda)^M$ in $M$ of size $\|X\|^M<\kappa$ we have
> $f(\bigvee X)=\bigvee_{x\in X}f(x)$. In fact, $f$ can be taken to extend the identity map on the generators.

In particular, the theorem implies that $f$ maps small maximal antichains of $\mathbb{B}(\kappa,\lambda)^M$ into maximal antichains in $\mathbb{B}(\kappa,\lambda)^V$. I will not give a proof of this result, but I want to point out a subtlety in the statement, which caused a lot of issues in my talk. It may seem that one can give a simple counterexample to the theorem. The one brought up in my talk was as follows: supposing that $\kappa$ and $\lambda$ were sufficiently large, let $u_r$, for some real $r\in M$, be the conjunction of the generators or their complements according to $r$. Then it should be the case that $\bigvee_r u_r=1$ in $\mathbb{B}(\kappa,\lambda)^M$. But if $V$ has more reals than $M$, then $\bigvee_{r\in M} f(u_r)\neq 1$ in $\mathbb{B}(\kappa,\lambda)^V$, contradicting the theorem. The subtlety arises in the claim that $\bigvee_r u_r=1$ in $\mathbb{B}(\kappa,\lambda)^M$. This would be the case if $\mathbb{B}(\kappa,\lambda)^M$ were $(\omega,2)$-distributive, since then $\bigvee_r u_r=\bigwedge_n(e_n\lor\lnot e_n)=1$, but in general this will fail. In fact, by freeness, there is a $u\in \mathbb{B}(\kappa,\lambda)^M$ which is compatible with every $e_n$ and their complements but incompatible with every $u_r$.

We now know that $\mathbb{B}(\kappa,\lambda)^M$ is essentially a $M$–$\kappa$-complete subalgebra of $\mathbb{B}(\kappa,\lambda)^V$. This will allow us to pull down information from the algebra in $V$ to the algebra in $M$. The foremost is the following lemma.

> **Lemma 8.** Subsets of $\lambda$ in $V$ correspond uniquely to $M$-$\kappa$-complete ultrafilters on $\mathbb{B}(\kappa,\lambda)^M$.

*Proof:* Given an ultrafilter $U$, we can simply assign to it the set $A=\\{\alpha\in\lambda; e_\alpha\in U\\}$. Conversely, given a set $A\subseteq\lambda$ in $V$ there is, by freeness, a unique $\kappa$-complete ultrafilter $U$ on $\mathbb{B}(\kappa,\lambda)^V$ which contains or omits the generators according to $A$. But then $U\cap \mathbb{B}(\kappa,\lambda)^M$ is an $M$–$\kappa$-complete ultrafilter on $\mathbb{B}(\kappa,\lambda)^M$, since the latter is an $M$–$\kappa$-complete subalgebra of $\mathbb{B}(\kappa,\lambda)^V$. It is easy to check that these two assignments are inverse to each other. $\Box$

Given $A\subseteq\lambda$ we will denote by $U_A^\kappa$ the corresponding ultrafilter on $\mathbb{B}(\kappa,\lambda)^M$. Clearly $M(U_A^\kappa)=M(A)$, but there is no reason to believe that $U_A^\kappa$ is in any way generic over $M$. In fact, $\mathbb{B}(\kappa,\lambda)^M$ will not be $\kappa$-cc, so we have not quite finished with step 1 of theorem 2. We will use the uniform covering property to thin out $\mathbb{B}(\kappa,\lambda)^M$ to a $\kappa$-cc poset which the residue of $U_A^\kappa$ will be generic for.

Let $f_A$ be the function that, given a maximal antichain $Z\subseteq \mathbb{B}(\kappa,\lambda)^M$ in $M$, gives the element of the intersection $Z\cap U_A^\kappa$, if such an element exists, and gives some arbitrary element of $Z$ if not. This function will, in general, only exist in $V$. But since $M$ uniformly $\kappa$-covers $V$, we can find a covering function $F_A$ for $f_A$ in $M$; we may also assume that $F_A(Z)\subseteq Z$ for all $Z$. Essentially, the function $F_A$ represents $M$ trying to guess where the potential generic filter coding $A$ will meet the antichains of $\mathbb{B}(\kappa,\lambda)^M$. We will use this guess to remove the inessential parts of the antichain $Z$.

We work for a while in $M$. Let $\theta$ be a sufficiently large cardinal (much larger than $\|\mathbb{B}(\kappa,\lambda)\|$). Define a subset of $\mathbb{B}(\theta,\lambda)$ by

$$T_A = \left\{ \bigvee Z \longrightarrow \bigvee F_A(Z); Z\subseteq \mathbb{B}(\kappa,\lambda)\text{ a maximal antichain} \right\} \subseteq \mathbb{B}(\theta,\lambda)$$

It should be noted that, while $\bigvee Z=1$ in $\mathbb{B}(\kappa,\lambda)$, it need not be the case that $\bigvee Z=1$ in $\mathbb{B}(\theta,\lambda)$.

We wish to see that $\bigwedge T_A\neq 0$ in $\mathbb{B}(\theta,\lambda)$. This will follow if we can show that 

$$\left(\bigvee Z\longrightarrow \bigvee F_A(Z)\right)\in U_A^\theta$$ 

for all $Z$, by the $M$–$\theta$-completeness of $U_A^\theta$. So assume that $\bigvee Z\in U_A^\theta$. By the completeness of $U_A^\theta$, we can find a $u\in Z\cap U_A^\theta$. But note that also 

$$u\in Z\cap U_A^\theta\cap \mathbb{B}(\kappa,\lambda)= Z\cap U_A^\kappa$$ 

so $f_A(Z)=u$. Therefore $u\leq \bigvee F_A(Z)\in U_A^\theta$.

We are ready to define the poset which will add the set $A$ over the model $M$. Let

$$ \mathbb{P}_A=\left\{ u\in\mathbb{B}(\kappa,\lambda); 0<u\leq\bigwedge T_A \text{ in }\mathbb{B}(\theta,\lambda)\right\} $$

In the Lindenbaum algebra view of $\mathbb{B}(\kappa,\lambda)$, the poset $\mathbb{P}_A$ is essentially the Lindenbaum algebra where we add the infinitary inference rules coming from $T_A$; that is, from $\bigvee Z$ we are allowed to infer $\bigvee F_A(Z)$.

> **Lemma 9.** $\mathbb{P}_A$ is $\kappa$-cc in $M$.

*Proof:* Work in $M$ and let $Z\subseteq \mathbb{P}_A$ be a maximal antichain. Then $F_A(Z)$ is a subset of $Z$ of size $<\kappa$. We shall show that any element of $Z$ is compatible with some element of $F_A(Z)$. It will follow that $Z=F_A(Z)$ has size $<\kappa$.

So pick $u\in Z$ and fix some $\theta$-complete ultrafilter $U$ on $\mathbb{B}(\theta,\lambda)$ with $u\in U$. Then also $\bigwedge T_A\in U$, so, in particular, $(\bigvee Z\longrightarrow \bigvee F_A(Z))\in U$. Since $u\leq \bigvee Z\in U$ we also have $\bigvee F_A(Z)\in U$ and, by $\theta$-completeness, there is some $u'\in F_A(Z)\cap U$. But then $0<u\wedge u'\leq \bigwedge T_A$, meaning that $u$ is compatible with $u'$ in $\mathbb{P}_A$. $\Box$

> **Lemma 10.** The filter $G_A=U_A^\kappa\cap \mathbb{P}_A$ is $\mathbb{P}_A$-generic over $M$.

Proof: Let $Z\subseteq \mathbb{P}_A$ be a maximal antichain in $M$. Then $\|Z\|<\kappa$, so the join $\bigvee Z$ exists in $\mathbb{B}(\kappa,\lambda)$ and agrees with the join in $\mathbb{B}(\theta,\lambda)$. It follows that $\bigvee Z\in \mathbb{P}_A$ and, since $Z$ was maximal, $\bigvee Z$ must be the top condition of $\mathbb{P}_A$. Then $\bigvee Z\in G_A$, so we can use the $\kappa$-completeness of $U_A^\kappa$ to find a $u\in Z\cap G_A$. $\Box$

Since $A$ and $G_A$ are interdefinable over $M$ (we have just constructed $G_A$ from $A$ and $\mathbb{P}_A$ and it is easy to read off $A$ from $G_A$), this ultimately shows that $M(A)=M[G_A]$ is a $\kappa$-cc generic extension of $M$, finishing the proof of step 1.