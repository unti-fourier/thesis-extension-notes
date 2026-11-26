# Absolute Hochschild classes for a free PSL2 suspension without invariant probability

**Work in progress.** Written verification only; not a paper, preprint, Lean formalization, or priority claim.

There is a free topologically nonamenable action of \(G=\mathrm{PSL}_2(\mathbb R)\) on a compact metrizable \(X\), without a \(G\)-invariant probability, and a quasi-invariant probability \(\mu\) on \(X\) for which \(H_b^2(F_2;\mathbb C)\) embeds split and seminorm-isometrically into
\[
HH^2_{\rm cont}(A,\mathcal B(C(X),L^\infty(X,\mu;\mathbb C)))
\]
for both the row and Bochner crossed Banach algebras \(A\). In particular, the conclusion does not require a nonamenable point stabilizer or an invariant probability for the entire action.

### The action

Take a genus-two closed hyperbolic surface group \(\Lambda<G\) as a torsion-free uniform lattice, with generators \(a_i,b_i\), \(i=1,2\), and relation \([a_1,b_1][a_2,b_2]=1\). Let \(q:\Lambda\to F_2=\langle u_1,u_2\rangle\) send \(a_i\) to \(u_i\), \(b_i\) to \(1\); let \(r:\Lambda\to F_2\) interchange these assignments. Then \(r\) restricts to an isomorphism on \(H=\langle b_1,b_2\rangle\): the map \(u_i\mapsto b_i\) is a right inverse of \(r\). In particular \(H\) is closed and nonamenable in \(G\).

The surface group is residually finite, for instance by surface subgroup separability ([Scott (1978), Subgroups of surface groups are almost geometric](https://doi.org/10.1112/jlms/s2-17.3.555)). On
\[
Y=\partial F_2\times\widehat\Lambda,\qquad
\ell\cdot(\xi,k)=(q(\ell)\xi,\ell k)
\]
left translation on the profinite factor makes the action free. Put \(X=G\times_\Lambda Y\) using \((g,y)\sim(g\ell,\ell^{-1}y)\). It is compact metrizable by local triviality over the compact metrizable \(G/\Lambda\) and compact metrizability of \(Y\). An element fixing \([g,y]\) must be conjugate by \(g\) to an element of \(\Lambda\) fixing \(y\); hence the induced action is free.

An invariant probability on \(X\) would lift to a \(G\)-left invariant and right-\(\Lambda\)-invariant Radon measure on \(G\times Y\) by summing over the countable covering fibres. For each measurable test in the \(Y\) variable, its measure in the \(G\) variable is a scalar multiple of left Haar. Thus the lift is Haar times a nonzero finite measure on \(Y\). Right invariance under \(\Lambda\) and unimodularity of \(G\) force the latter measure to be \(\Lambda\)-invariant. Its projection to \(\partial F_2\) would be \(F_2\)-invariant, impossible: the action of each \(u_i\) has north–south dynamics, forcing any invariant probability for that element to be supported on its two endpoints. The two pairs are disjoint.

On the other hand, give \(\partial F_2\) any quasi-invariant probability \(\nu\), for example a positive weighted orbit sum of a full-support probability. Set \(\lambda=\nu\otimes m_{\widehat\Lambda}\) on \(Y\). It is \(\Lambda\)-quasi-invariant and \(H\)-invariant because \(q|_H=1\). The copy of \(Y\) at \([1,Y]\) is \(H\)-invariant and gives an \(H\)-invariant probability on \(X\). If the \(G\)-action were topologically amenable, integrating an approximately equivariant Reiter field \(X\to L^1(G)_+\) against this probability would give \(H\)-almost invariant probabilities on \(G\). A Borel section of the left \(H\)-coset quotient gives an \(H\)-equivariant Borel map \(G\to H\); pushing forward contracts total variation and supplies a scalar Reiter net for \(H\), a contradiction.

### Degree two

Pull scalar classes back by \(r\), then include constants into \(L^\infty(Y,\lambda)\). There is a contractive left inverse in bounded cohomology: restrict from \(\Lambda\) to \(H\), integrate against the \(H\)-invariant \(\lambda\), and use \(r|_H\) to identify \(H\) with \(F_2\). Thus the map is seminorm-isometric.

Choose the measure class on the suspension given by invariant probability on \(G/\Lambda\) and \(\lambda\) in a Borel trivialization. The change of fibre coordinates is in \(\Lambda\), so this class is \(G\)-quasi-invariant; let \(\mu\) be its probability representative. The bounded induction module of \(L^\infty(Y,\lambda)\) identifies with \(L^\infty(X,\mu)\) by the suspension construction. Bounded Shapiro induction is isometric; see [Monod (2001), Proposition 10.1.3](https://doi.org/10.1007/b80626). The separable predual is \(L^1(X,\mu)\) with the pushforward action and the multiplication action of \(C(X)\). The pushforward is strongly continuous: the quasi-invariant Borel action gives a weakly measurable isometric representation on the separable predual, hence a Borel homomorphism into its isometry group with the strong topology, and therefore a continuous one. The [split absolute comparison](02-locally-compact-absolute-hh2-split-injection.md), Sections 3–4, now gives the stated split seminorm-isometric map for both completions.

For example, on the reduced syllables of a free word, sum the signs of their nonzero integer exponents. The bounded coboundary of this quasimorphism defines a scalar class of seminorm one by [Rolli (2009 preprint, v2), Propositions 2.4 and 3.8](https://arxiv.org/html/0911.4234v2). The same norm holds for complex coefficients by taking real parts. Its image gives the promised explicit nonzero class. The example concerns these coefficient modules and norms only, not a converse for arbitrary nonamenable actions.
