---
layout: post
title: "An interesting way to kill and resurrect measurability"
math: true
---

I want to present a peculiar forcing notion that I found out about recently from a paper by Apter and Shelah. 
I mainly find it interesting since it is another way of killing a large cardinal,
which nevertheless can be undone relatively easily. The main example I knew of before was the sainted Kunen argument: one can add a 
homogeneous Suslin tree to a cardinal $\kappa$, which obviously destroys its weak compactness, but if one then simply forces
with that Suslin tree to add a branch to it, the whole two-step iteration amounts to just adding a Cohen subset to $\kappa$,
and so, if one was a bit careful ahead of time, the weak compactness of $\kappa$ will be resurrected in this extension.
By using tricks like this, one can design iterations by which many/all large cardinals below some point get destroyed,
and the newly least large cardinal has some property of interest.

The other appealing feature of the forcing I will describe is that it very easily accommodates violations of
GCH. It is likely that one could take products and run many versions of Kunen's argument side by side, but
this new forcing incorporates this option much more naturally.

The source for this are the papers
> Apter, Arthur W.; Shelah, Saharon. On the strong equality between supercompactness and strong compactness. Trans. Amer. Math. Soc. 349 (1997), no. 1, 103--128. DOI: [https://doi.org/10.1090/S0002-9947-97-01531-6](https://doi.org/10.1090/S0002-9947-97-01531-6).
>
> Apter, Arthur W.; Shelah, Saharon. Menas' result is best possible. Trans. Amer. Math. Soc. 349 (1997), no. 5, 2007--2034. DOI: [https://doi.org/10.1090/S0002-9947-97-01691-7](https://doi.org/10.1090/S0002-9947-97-01691-7).

Ok, so let us get to it. We are given a cardinal $\kappa$ and asked to design a forcing so that in
the extension $\kappa$ will definitely not be measurable, but without doing anything too drastic, so that there will still be
hope of resurrecting its measurability. After some deliberation, we get the idea that we might want to add some subsets to
$\kappa$ which cannot be measured. We can even decide to go all out and try to get a family of sets which is not measured
by any countably complete nonprincipal ultrafilter on $\kappa$. We will achieve this last property in a very heavy-handed way,
by making sure that the intersection of any countable collection of these new sets, or their complements, is bounded
in $\kappa$.

That is the idea, and it is not hard to come up with a poset that might do something like what we want.
So let $\newcommand{\A}{\mathbb{A}} \A$ have conditions of the form $(p,Z)$ where the working part $p$
is a uniform condition in the Cohen forcing $\DeclareMathOperator{\Add}{\mathrm{Add}} \Add(\kappa,\kappa^+)$, meaning
that all of its nonempty columns have the same height, and $Z$ is a side condition, consisting of countably many
countable subsets of the domain of $p$ (i.e. the set of nonempty columns of $p$). 
The side condition $Z$ will contain our promises about the intersections; by putting a set of columns into $Z$ we are promising
that the intersection of the sets arising from those columns, or their complements, will not get any new elements from now on.
Why is $Z$ countable? We are not sure yet, but it is aesthetically pleasing, so let's leave it for now. 
The ordering in $\A$ is what you might expect: we say that $(p',Z')$ is stronger than $(p,Z)$ if the working
part $p'$ is stronger than $p$ in the Cohen sense, if the side condition $Z'$ gets bigger, and if for any
$z\in Z$ the new part $p'\setminus p$ above $z$ has no rows of either all 0s or all 1s. This is where the promises
kick in: if a condition $p$ makes a promise about a set of columns $z$ then those sets (or their complements)
will not have any elements in common above the height of $p$.

This seems to work OK, and it is not hard to see that the forcing $\A$ will add $\kappa^+$ many new
subsets to $\kappa$. Moreover, we really have killed the measurability of $\kappa$.

**Claim.** $\kappa$ is not measurable after forcing with $\A$.

*Proof sketch:* Suppose that a condition $(p,Z)$ forces that $\dot{U}$ is a nonprincipal ultrafilter on $\kappa$. We will
find a stronger condition that forces that $\dot{U}$ is not countably complete. For each $\alpha<\kappa^+$
let $(p_\alpha,Z_\alpha)$ be an extension of $(p,Z)$ that decides whether the $\alpha$th set added by
the generic gets into $\dot{U}$ or its complement does. A $\Delta$-system argument shows that we may
thin out the index set to $I$ so that all conditions indexed by $I$
force that it is their designated set in the generic that is in
$\dot{U}$, the domains of the working parts form a $\Delta$-system, and the side conditions agree
on the root. Now pick some countable $I'\subseteq I$ and let $(p_\infty,Z_\infty)$ be the componentwise
union of the $(p_\alpha,Z_\alpha)$ for $\alpha\in I'$, also adding $I'$ into $Z_\infty$.
This can be seen to be a condition, and it forces that the intersection of the generic sets indexed
by $I'$ is bounded in $\kappa$, and therefore cannot be an element of $\dot{U}$. $\Box$

However, the countability of the side conditions is looming in the background.
The forcing is very far from having any appreciable closure, so it seems unlikely that
the damage it does to the large cardinal properties of $\kappa$ can be easily undone. We could try
to increase the size of the side conditions, perhaps allowing $Z$ to have any size below $\kappa$.
But this would also lead to problems, this time with the density arguments. Note that, as soon as
we allow side conditions of size continuum, we will get conditions whose working part cannot be extended anymore:
it could be that the side condition contains the whole powerset of the domain of the working part.
So this is not a good way to go. Nevertheless, to hope for any kind of closure, we must allow larger side
conditions, but at the same time, these side conditions cannot be allowed to "concentrate" on any
part of $\kappa^+$.

Apter and Shelah solve this by restricting the kind of promises we can make in the side conditions.
Fix a ladder system $\vec{X}=\langle x_\alpha; \alpha\in S^{\kappa^+}_\omega\rangle$ (the restriction
to countable cofinality is immaterial, but lets us avoid some complications). The forcing
$\A(\vec{X})$ is just like $\A$, except that the side conditions can now contain only elements
of $\vec{X}$, and there is no explicit restriction on the size of the side condition. 
Is this any better than our previous attempt? While the side conditions now
will not concentrate anywhere too much, have we really avoided the issue from before where some conditions just could
not be extended? And, have we not inadvertently broken the proof sketch above? After all, there doesn't seem to be
a reason why there should be any set like $I'$ from the proof on the ladder system at all.

We can save the proof by having $\vec{X}$ be a very special kind of ladder system: a $\clubsuit_{\kappa^+}(S^{\kappa^+}\_\omega)$-sequence.
In this situation the ladder system will definitely have a set $I'$ as in the proof, so $\A(\vec{X})$ will still kill measurability,
provided that we can show that the generic will actually add new subsets to $\kappa$. We are back at the issue of extendibility
of conditions, as it might be that even the index set $S^{\kappa^+}\_\omega$ might be too thick. 
The solution is to further restrict the ladder system $\vec{X}$: one can show that if $\vec{X}$ is supported not on
all of $S^{\kappa^+}\_\omega$, but on some nonreflecting stationary subset of it, then one can essentially replace
$\vec{X}$ with an equivalent ladder system $\vec{Y}$ whose elements are pairwise disjoint.

This then is the final setup: if $S\subseteq \kappa^+$ is a nonreflecting stationary set consisting of points of countable
cofinality and $\vec{X}$ is a $\clubsuit_{\kappa^+}(S)$-sequence, then $\A(\vec{X})$ is a $<\kappa$-closed forcing
which forces that $\kappa$ is not measurable.

This is all well and good, but we wanted to also be able to resurrect the measurability of $\kappa$. The final step is the following
theorem (which I will not prove).

> **Theorem.** Suppose $\kappa$ is inaccessible and let $\mathbb{S}$ be the forcing to add a nonreflecting stationary set $S\subseteq\kappa^+$
> of points of countable cofinality, let $\mathbb{C}$ be the forcing to shoot a club disjoint from $S$ and suppose that $\vec{X}$ is a
> $\clubsuit_{\kappa^+}(S)$ sequence in $V[S]$. Then the forcing $\mathbb{S}*(\A(\vec{X}) \times \mathbb{C})$ is equivalent to
> $\Add(\kappa^+,1) * \Add(\kappa,\kappa^+)$.

So the only thing we need to do to recover the measurability of $\kappa$ after killing it with the forcing we did before (given that we suitably prepared ahead of time) is to
kill the nonreflecting stationary set that supported the ladder system. You might wonder where the $\clubsuit_{\kappa^+}(S)$-sequence comes from, but in fact
the forcing $\mathbb{S}$ actually forces such a sequence into existence (given some extra cardinal arithmetic we could even get versions of $\diamondsuit$).

So there you have it. A ready-to-use forcing to kill and, if needed, resurrect the measurability of a cardinal. It is easy enough to 
also incorporate a violation of GCH into the forcing $\A$ by simply taking wider working parts: instead of $\Add(\kappa,\kappa^+)$ work
with $\Add(\kappa,\kappa^{++})$ or something even bigger and modify the other forcings accordingly.