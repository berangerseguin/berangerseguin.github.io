---
layout: post
title:  "Dreaming of a GT-ometry"
---

$$\newcommand{\Q}{\mathbb{Q}}$$
$$\newcommand{\Qbar}{\bar{\Q}}$$
$$\newcommand{\C}{\mathbb{C}}$$
$$\newcommand{\GT}{\widehat{\mathcal{GT}}}$$
$$\newcommand{\F}{\mathbb{F}}$$
$$\newcommand{\Spec}{\mathrm{Spec}\,}$$
$$\newcommand{\piet}{\pi_1^{\text{ét}}}$$
$$\newcommand{\pigeom}{\pi_1^{\text{géom}}}$$
$$\newcommand{\id}{\mathrm{id}}$$
$$\newcommand{\Out}{\mathrm{Out}}$$
$$\newcommand{\Aut}{\mathrm{Aut}}$$

In this post, I suggest a weird idea, which may very well be naive or well-known, but that I felt like recording.
Can we see varieties equipped with an outer action of the Grothendieck-Teichmüller group on their geometric étale fundamental group as actual geometric objects defined over "something small", as if we were doing "algebraic geometry over $$\GT$$"?

### outer galois actions

Consider an algebraic variety $$X$$ over $$\Q$$, geometrically connected and equipped with a geometric basepoint $$x \in X(\Qbar)$$ which we never write explicitely.
Denote by $$X_{\Qbar}$$ the extension of scalars $$X \underset{\Spec \Q}{\times} \Spec \Qbar$$, and denote by $$\pigeom(X)$$ the étale fundamental group of $$X_{\Qbar}$$.
Denote also by $$G_{\Q}$$ the absolute Galois group $$\mathrm{Gal}(\Qbar\mid\Q)$$.
We have an exact sequence:

$$ 1 \to \pigeom(X) \to \piet(X) \to G_{\Q} \to 1.$$

Since $$\pigeom(X)$$ is a normal subgroup of $$\piet(X)$$, $$\piet(X)$$ has an inner action on $$\pigeom(X)$$ via conjugacy.
Two lifts of a $$\sigma \in G_{\Q}$$ into an element of $$\piet(X)$$ act on $$\pigeom(X)$$ similarly up to conjugacy by an element of $$\pigeom(X)$$.
Therefore, we have an outer action of $$G_{\Q}$$ on the geometric fundamental group $$\pigeom(X)$$ (which is the profinite completion of the topological fundamental group):

$$ G_{\Q} \to \Out(\pigeom(X)) = \Out(\widehat{\pi_1(X(\C))}). $$

Moreover, each $$\Q$$-point of $$X$$ induces a lift of this outer action to an actual action $$G_{\Q} \to \Aut(\pigeom(X))$$, well-defined up to global conjugacy by an element of $$\pigeom(X)$$.

### outer GT-actions

Now, for some varieties (most importantly, and quite tautologically, for the moduli stacks of curves $$\mathcal{M}_{g,n}$$), people have found ways to extend the outer action of $$G_{\Q}$$ into an action of the Grothendieck-Teichmüller group $$\GT$$.
This "extension property" looks a lot like a "descent result", suggesting that these varieties are somehow defined over a "field" smaller[^1] than $$\mathbb{Q}$$, whose absolute Galois group is $$\GT$$...

We can even guess what the "$$\GT$$-points" should be (in good cases, guided by Grothendieck's section conjectures): they are lifts of the outer $$\GT$$-action into an action $$\GT \to \Aut(\pigeom(X))$$, modulo conjugacy by an element of $$\pigeom(X)$$!


Let us be even more radical — anabelian-geometry like — and take as the *definition* of a $$\GT$$-variety[^2] that it is an extension of $$\GT$$ by a finitely generated profinite group.
Morphisms have a good candidate definition too, inspired by anabelian conjectures for hyperbolic curves: if $$1 \to A \to B \to \GT \to 1$$ and $$1 \to A' \to B' \to \GT \to 1$$ are two extensions, a morphism between them is a morphism $$B \to B'$$, which commutes with the surjections to $$\GT$$, and considered modulo conjugacy by an element of $$A'$$.

This principle gives rise to a category of "geometric-like" objects for any group $$G$$, which I call $$G$$-ometries (defined carefully below).
A variety over $$\Q$$ induces a $$G_{\Q}$$-ometry, and the "$$\GT$$-varieties" presented above are the $$\GT$$-ometries.

### first G-ometrical constructions: points

Fix a profinite group $$G$$.
Let us write explicitly the definitions suggested in the last paragraphs:

**Definition ($$G$$-ometry):**
A *$$G$$-ometry* $$X$$ is a profinite group -- denoted by $$\piet(X)$$ -- equipped with a continuous surjection $$\piet(X) \to G$$ whose kernel -- denoted by $$\pigeom(X)$$ -- is a finitely generated profinite group.
The surjection $$\piet(X) \to G$$ is called the *structural morphism* of $$X$$.

**Definition (morphism of $$G$$-ometries):**
A morphism between two $$G$$-ometries $$X$$ and $$Y$$ is the class, modulo conjugacy by an element of $$\pigeom(Y)$$, of a group morphism $$\piet(X) \to \piet(Y)$$ which commutes with the structural morphisms.

**Definition ($$G$$-points):**
The *point* $$\star$$ is the $$G$$-ometry corresponding to the identity morphism $$\id_G: G \to G$$.
A *$$G$$-point* of a $$G$$-ometry $$X$$ is a morphism of $$G$$-ometries $$\star \to X$$.
We denote by $$X(G)$$ the set of $$G$$-points of $$X$$.

A $$G$$-point is the equivalence class of the section of the structural morphism under the conjugacy action of $$\pigeom(X)$$.
It also corresponds to a lift of the outer action $$G \to \Out(\pigeom(X))$$ into an actual action $$G \to \Aut(\pigeom(X))$$.
A $$G$$-ometry which admits a $$G$$-point is a split extension of $$G$$, the section corresponding to the $$G$$-point.
In this case, $$\piet(X)$$ is realized as a semi-direct product $$\pigeom(X) \rtimes G$$.

The funny game is to attempt doing geometry with $$G$$-ometries -- and especially constructing "usual" spaces using these purely group-theoretic objects.
For example:

**Definition (extension of scalars):**
Let $$H$$ be an open subgroup of $$G$$.
The *extension of scalars* $$X_H$$ of $$X$$ to $$H$$ is the $$H$$-ometry obtained by letting $$\piet(X_H)$$ be the subgroup of $$\piet(X)$$ consisting of elements which are mapped to elements of $$H$$ by the structural morphism.

Note that $$\pigeom(X_H) = \pigeom(X)$$, and the outer action of $$H$$ on $$\pigeom(X)$$ is the restriction of the outer action of $$G$$

The $$H$$-points of $$X$$ to be the $$H$$-points of $$X_H$$, and we let $$X(H) = X_H(H)$$.
If $$Y$$ is a $$H$$-ometry, we say that it is *defined over $$G$$* if $$Y$$ is isomorphic to $$X_H$$ for some $$G$$-ometry $$X$$.

Let $$X$$ be a $$G$$-ometry and $$H$$ be a normal open subgroup of $$G$$.
Denote by $$\varphi : G \to \Aut(H)$$ the morphism induced by conjugacy.
Consider an element $$g \in G$$ and an $$H$$-point of $$X$$, represented by a morphism $$x : H \to \Aut(\pigeom(X))$$.
Define $$g.x$$ to be the class of $$x \circ \varphi(g)$$ modulo conjugacy by an element of $$\pigeom(X)$$, which is an $$H$$-point.
This is well-defined since replacing $$x$$ by another representative $$\alpha^{-1} x \alpha$$ with $$\alpha \in \pigeom(X)$$ leads to:

  $$ (\alpha^{-1} x \alpha) \circ \varphi(g) = \alpha^{-1} (x \circ \varphi(g)) \alpha$$

which defines the same $$H$$-point as $$x \circ \varphi(g)$$.

Hence, we have defined an action of $$G$$ on the set $$X(H)$$ of $$H$$-points of $$X$$.

A quick sanity check:

----

**Proposition:**
An $$H$$-point of $$X$$ which extends to a $$G$$-point of $$X$$ is invariant under the action of $$G$$.

**Proof:**
By hypothesis, we have a morphism $$\tilde x : G \to \Aut(\pigeom(X))$$ whose restriction $$x : H \to \Aut(\pigeom(X))$$ represents the $$H$$-point in question.
Let $$g \in G$$.
For all $$h \in H$$ we have:

$$ (x \circ \varphi(g))(h) = x (g^{-1}hg) = \tilde x(g)^{-1} x(h) \tilde x(g) $$

and thus $$x \circ \varphi(g)$$ defines the same $$H$$-point as $$x$$. ■

----

Let $$X(\bar G)$$ denote the inductive limit, indexed by normal open subgroups $$H$$ of $$G$$, of the sets $$X(H)$$.
Then $$G$$ acts on the set $$X(\bar G)$$.

### G-ometrical covers

Let $$X$$ be a $$G$$-ometry.
In what follows, "cover" always means "finite étale connected cover":

**Definition (geometric/algebraic cove r):**
A *geometric (resp. algebraic) cover* of $$X$$ is a conjugacy class of open subgroups of $$\pigeom(X)$$ (resp. $$\piet(X)$$).
These subgroups are called *markings* of the cover.
A cover consisting of a single normal subgroup (i.e. there is a single marking) is said to be *Galois*.

The degree of a cover is the index of the corresponding subgroups.
The Galois closure of a cover is the cover corresponding to the normal closure of any of its markings. 
The outer action of $$G$$ on $$\pigeom(X)$$ induces an action of $$G$$ on geometric covers of $$X$$.

**Definition (geometrically connected):**
An algebraic cover of $$X$$ is *geometrically connected* if its markings, when intersected with $$\pigeom(X)$$, form a single conjuacy class of subgroups of $$\pigeom(X)$$.

A geometrically connected algebraic cover of $$X$$ induces, by intersection with $$\pigeom(X)$$, a geometric cover of $$X$$.

**Definition (defined over $$G$$):**
An algebraic cover of $$X$$ is *defined over $$G$$* if the composition of inclusion (of any marking) into $$\piet(X)$$ with the structural morphism is surjective and its kernel is a profinite finitely generated group.
A geometric cover of $$X$$ is *defined over $$G$$* if it is obtained as the intersection with $$\pigeom(X)$$ of a geometrically connected algebraic cover of $$X$$ which is defined over $$G$$.

Geometrically connected covers defined over $$G$$ are themselves $$G$$-ometries.

A quick sanity check:

----

**Proposition:**
The group $$G$$ acts trivially on geometric covers which are defined over $$G$$.

**Proof:**
Consider an open subgroup $$H$$ of $$\piet(X)$$, which defines a geometrically connected algebraic cover of $$X$$ defined over $$G$$.
We have an exact sequence:

$$ 1 \to H \cap \pigeom(X) \to H \to G \to 1 $$

Take an element $$g \in G$$ and an arbitrary lifting $$\bar g \in H$$, and in particular $$\bar g \in \piet(X)$$ is a lifting of $$g$$ in $$\piet(X)$$.
The outer action of $$g$$ on $$\pigeom(X)$$, and subsequently the action of $$g$$ on geometric covers of $$X$$, is induced by conjugation by $$\bar g$$.
Since $$H \cap \pigeom(X)$$ is normal in $$H$$ and $$\bar g \in H$$, conjugacy by $$\bar g$$ leaves it unchanged, so $$g$$ acts trivially on the corresponding geometric cover. ■

----

Let us mention that a *rationally marked $$G$$-ometry* is an extension of $$G$$ by a profinite finitely generated group equipped with a splitting (defined up to conjugacy by an element of $$\pigeom(X)$$), that a *marked cover* (geometric or algebraic) is an open subgroup of a fundamental group (instead of a conjugacy class of subgroups), and that a *rationally marked cover* is an open subgroup $$H$$ of $$\piet(X)$$ which surjects onto $$G$$, equipped with a splitting $$G \to H$$, defined up to conjugacy by an element of $$\ker(H \to G)$$.

### applications

F. Pop[^3] has characterized $$G_{\mathbb{Q}}$$ as the largest group which has outer actions on the geometric étale fundamental groups of all regular quasiprojective $$\mathbb{Q}$$-varieties, which are compatible with all $$\mathbb{Q}$$-morphisms.
It seems then that understanding how different $$\GT$$ and $$G_{\Q}$$ actually are (and whether they are, actually, different) mostly amounts to understanding how often the outer Galois action on $$\pigeom$$ can be extended into a $$\GT$$-action: each variety for which this is shown to be the case brings $$\GT$$ "a little closer" to $$G_{\Q}$$. (notably, Ihara and Matsumoto have proved such extension results for algebraic configuration spaces)

One of the reasons why a geometry over $$\GT$$ may be of use is because it transforms this question into a (virtually) geometrical question: we are mostly looking at the """fields""" of definition of $$G_{\Q}$$-ometries, and trying to show that they are actually "defined over $$\GT$$", i.e. that $$\GT$$ has an outer action on the geometric fundamental group that extends the Galois action.
This rephrases the question in a language more familiar to algebraic geometers.
An understanding as to how far this idea of "synthetic", "group-based", "scheme-free" algebraic geometry can be pushed, and in particular an attempt to construct various varieties (moduli spaces in particular) directly in the language of $$G$$-ometries (or a more sophisticated version of that idea), could be a useful tool to see how the methods usually used to compute fields of definition of varieties (notably, descent criteria) may admit generalizations, or philosophical equivalents, in this language.

**Bonus question:**
What could be said of the whole étale homotopy type?
Such a generalization is clearly needed if one wishes to have a more faithful view of the geometry of things that are not hyperbolic curves.
See <a href="https://arxiv.org/abs/1504.01068">this</a>.

### footnotes

[^1]: Wait — is this anyhow related to $$\F_1$$? Many candidate definitions of a $$\F_1$$-scheme have been proposed. It would be interesting if any of these had any link with the existence of an outer $$\GT$$-action on a geometric étale fundamental group.

[^2]: This notion may or may not be related to the objects Mochizuki calls "anabeloids" (see <a href="http://pagine.dm.unipi.it/tamas/iutlecture.pdf">here</a>), I am unsure about that.

[^3]: <a href="https://www2.math.upenn.edu/~pop/Research/files-Res/2018-12-24_IOM.pdf">This was only published in 2019</a>, although everyone apparently knew that Pop had proven the result since 2002. See also <a href="https://arxiv.org/abs/1211.4608">this</a> and <a href="https://user.math.uzh.ch/ayoub/PDF-Files/Anabel.pdf">that</a>. What about <a href="https://www2.math.upenn.edu/~pop/Research/files-Res/Linear-GT_arXiv.pdf">this</a> and <a href="https://www2.math.upenn.edu/~pop/Research/files-Res/2021-11-01_PapuVol_rm.pdf">that</a>?
