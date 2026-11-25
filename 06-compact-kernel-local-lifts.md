# A derivation criterion for étale quotients with compact kernel

**Work in progress.** Written-checked research note for a possible future paper. Not a submission, preprint, peer-reviewed result, or profile entry. Neither Lean verification nor priority is asserted.

## Statement

Let \(H\rightrightarrows X\) be a locally compact Hausdorff étale groupoid. Let \(\pi:\Sigma\to H\) be an extension that is the identity on units, has kernel isomorphic as a topological group bundle to \(X\times K\) for a compact Hausdorff group \(K\), and admits continuous local sections over open bisections covering \(H\). The sections identify \(\pi^{-1}(U)\) with \(U\times K\); in particular \(\pi\) is proper. On each range row of \(\Sigma\), sum the normalized Haar probabilities \(\omega_h\) of the torsors \(\pi^{-1}(h)\) over the corresponding row of \(H\). These probabilities are preserved under left and right torsor translations, including changes of coordinate by conjugation. They give a full continuous left Haar system.

Let \(A\) be the untwisted one-sided range-norm convolution completion for this system. The following are equivalent:

1. \(\Sigma\) is topologically amenable.
2. \(H\) is topologically amenable.
3. For every contractive Banach \(A\)-bimodule \(E\) whose essential core \(V=\overline{\operatorname{span}}AEA\) satisfies right diagonal type (M), all bounded derivations \(A\to E^*\) are inner.

Here the diagonal \(d_z\) for \(z\in C_0(X)\) acts on densities by multiplication by \(z\circ r\) on the left and by \(z\circ s\) on the right. Type (M) is \(\sum_j\|v d_{z_j}\|\le\|\sum_j z_j\|_\infty\|v\|\) for finite positive families, \(v\in V\). Neither compact units nor centrality, commutativity or total disconnectedness of the kernel is required. The final section removes global triviality of the kernel bundle.

## Forward implication

The clopen kernel completes to \(B=C_0(X,L^1(K))\). It is an ordinarily amenable Banach algebra: apply Johnson (1972), then [Ghamarshoushtari–Zhang (2015), Theorem 2.1](https://doi.org/10.1016/j.jmaa.2014.09.042), on \(X\) when compact or its one-point compactification otherwise. In the latter case pass to the closed ideal with bounded approximate identity by [Runde (2020), Proposition 2.3.3](https://doi.org/10.1007/978-1-0716-0351-2_2). There is no identification of a projective tensor norm with the sup norm here. Products of compact unit cutoffs and positive normalized continuous approximate identities of \(K\) give a two-sided contractive approximate identity \(e_i\) for \(B\) and for \(A\). Indeed for a compactly supported density, choose the cutoff to be one on both endpoint projections of its support; the two kernel translations approach the identity uniformly on the compact saturated support, which has uniformly bounded range-row mass by a finite bisection cover.

Restrict the original derivation to \(V^*\) and subtract an inner derivation there to get \(\delta\) zero on \(B\). On the essential predual, contractive multiplier actions extend by norm limits on \(AVA\), and their adjoints act weak-star continuously. The weak-star cluster point of \(\delta(me_i)\) for a two-sided multiplier \(m\) is uniquely specified by
\[
 \bar\delta(m)a=\delta(ma)-m\delta(a)\qquad(a\in A).
\]
Uniqueness follows from left essentiality of \(V\). This also gives the Leibniz rule, the bound \(\|\bar\delta(m)\|\le\|\delta\|\|m\|\), and \(\bar\delta(m)=0\) when \(me_i\in B\). In particular it vanishes on diagonal multipliers and on compactly cut off point masses along continuous kernel sections.

For a bisection lift \(\tau:U\to\Sigma\) and \(f\in C_c(U)\), write \(m_f\) for convolution by \(f(h)\delta_{\tau(h)}\) along the lift, and \(m_u^*\) for the inverse lift with conjugate cutoff. Left convolution moves at most one row at a time; right convolution reindexes a subset of each range row injectively and preserves the normalized probability on each torsor. Both operators thus have norm at most \(\|f\|_\infty\). The inverse changes of variables in the torsor integrals verify the two-sided multiplier identity. These formulas preserve compact support and continuity.

Choose \(u\in C_c(U,[0,1])\) equal to one near \(\operatorname{supp}f\) and set \(T_U(f)=\bar\delta(m_f)m_u^*\). A source cutoff on the common region where two choices of \(u\) are one proves cutoff independence, since \(\bar\delta\) kills the source diagonal. A lift change \(\tau'(h)=\tau(h)\kappa(sh)\) inserts a right kernel multiplier \(t\) in both \(m_f\) and \(m_u\), with \(\bar\delta(t)=0\) and \(tt^*=1\) on the relevant source support. Thus \(T_U(f)\) does not change. For \(\beta\in B\), conjugate the coefficient by \(\tau(h)\) from range to source, with a cutoff, to obtain \(\beta'\in B\) with \(\beta m_f=m_f\beta'\) and \(\beta'm_u^*=m_u^*\beta\). Hence \(T_U(f)\) commutes with \(B\). It also commutes with diagonal multipliers: approximate them on \(V\) by multiplying by \(e_i\), then pass to adjoints.

Partitioning a compact support by nonnegative bisection cutoffs now defines \(T:C_c(H)\to V^*\). If \(p=\sum_j p_j\) is such a partition and \(R\) is the counting range sum on \(H\), then \(T(p_j)=d_{Rp_j}\bar\delta(m_{u_j})m_{u_j}^*\). Dual type (M) and \(\sum_j|Rp_j|=R|p|\) give \(\|T(p)\|\le\|\delta\|\|p\|_r\). On a product bisection the product of lifts is a valid lift; using \(m_gm_v^*=d_{Rg}\) for a local term \(g\) and its cutoff \(v\) gives
\[
 T(f*p-((Rf)\circ r)p)m_u
   =m_fT(p)-T(p)m_f+\bar\delta(m_f)d_{Rp}.
\]
This follows by expanding \(\bar\delta(m_fm_g)m_v^*m_u^*\), summing over the partition of \(p\), and using the diagonal commutations and \(d_{Rf}m_u=m_f\). The local Reiter densities of the [étale criterion](06-etale-essential-core.md) make the left side tend to zero in norm; \(Rp\to1\) on compact source supports makes the last term tend to \(\bar\delta(m_f)\). A single weak-star cluster point of \(-T(p)\) therefore implements \(\bar\delta\) on all such \(m_f\), and commutes with \(B\).

Any \(a\in C_c(\pi^{-1}U)\) factors as \(\beta m_u\), using the kernel density \(\beta(rh,k)=a(k\tau(h))\) and a cutoff \(u=1\) on the projected support. Partitioning compact supports and using density proves implementation on \(A\). To return from \(V^*\) to \(E^*\), extend the implementer by Hahn–Banach and let \(d\) be the residual derivation. Its values belong to \(Y=V^\perp\), with \(AYA=0\). Expanding \(d(e_i a e_i)\) gives \(d(a)=am+ma\), where \(m\) is a weak-star subnet limit of \(d(e_i)\). A subnet limit \(m_L\) of \(e_i m\) satisfies \(am_L=am\) and \(m_La=0\). Thus \(2m_L-m\) implements the residual.

## Reverse implication and examples

Torsor averaging \(Qa(h)=\int a\,d\omega_h\) gives a contractive quotient algebra map onto the counting range completion of \(H\), split by the isometric algebra map \(p\mapsto p\circ\pi\). This follows by Fubini and Haar transport. Pullback and averaging of probability rows respectively preserve and contract the Reiter defect; properness handles compact arrow tests, so the two amenability conditions agree. The specified reverse witness of the [étale criterion](06-etale-essential-core.md) pulls back under \(Q\): surjectivity leaves its essential core unchanged, and \(Q(a d_z)=Q(a)J_Hz\) preserves the right diagonal action, with \(J_Hz\) the unit-space density. An implementer restricts to one for the witness on \(H\).

A noncentral example is the action groupoid of an irrational circle rotation by \(\mathbb Z\), extended by a second circle on which a degree-\(n\) arrow acts by \(z\mapsto z^{(-1)^n}\). A nonsplit example over the bundle \(\mathbb R\times\mathbb Z^2\) uses the circle-valued cocycle \(\exp(2\pi i x m_1n_2)\) in the fiber over \(x\). For \(x\notin\mathbb Z\) any lifts of the two standard generators have nontrivial commutator. Both bases are amenable.

This extends the [profinite central case](06-profinite-central-extensions.md) by a different argument. It does not settle arbitrary Haar groupoids, the two-sided \(I\)-norm completion, or ordinary Banach amenability of the range-norm algebra.

## Removing global triviality of the kernel bundle

The same theorem holds for a **locally trivial bundle of compact groups with fixed model fiber \(K\)**, rather than a global product \(X\times K\). Keep the local bisection lifts and normalized torsor Haar. No paracompactness of \(X\) is needed. Here is the additional written argument. Let \(B\) now denote the closure of the kernel densities, with the sup of the fiber \(L^1\) norms.

**A common approximate identity.** For a finite family of compactly supported test densities, cover their compact range and source projections by finitely many kernel charts. Choose positive cutoffs \(\phi_i\) supported inside those charts, of sum at most one and equal to one in sum near the projections. In each chart choose a positive continuous probability density on \(K\) supported sufficiently near the identity. Multiply by \(\phi_i\) and sum the resulting sections, extending by zero, to get a contractive \(e\in B\). In each chart, both kernel translations approach the identity uniformly on the compact saturated support of the tests. A finite bisection cover bounds the row mass of the support independently of the test point. Thus these \(e\), directed by finite tests and accuracy, form a two-sided approximate identity for \(A\) and \(B\).

**Delete the kernel restriction of the derivation.** The common approximate identity makes \(V=\overline{\operatorname{span}}BEB\). Restrict \(D|_B\) to \(V^*\), denoting the result by \(d\). Extend \(d\) contractively to the multipliers of \(B\) by the same weak-star argument used above. In particular \(d\) restricts there to a derivation on the scalar diagonal's sup-norm unitization. Averaging the bounded affine action of its abelian unitary group gives a diagonal implementer of norm at most \(\|d\|\). Subtract its inner derivation from \(d\), leaving \(\delta\), with \(\|\delta\|\le 3\|d\|\) and \(d_p\delta(b)=\delta(pb)=\delta(b)d_p\) for scalar \(p\in C_0(X)\) and \(b\in B\).

In a kernel chart \(U\), the ideal \(B(U)\) of sections vanishing outside \(U\) is \(C_0(U,L^1(K))\). These algebras admit ordinary approximate diagonals of norm at most one uniformly in \(U\). For \(C_0(U)\), average \(v\otimes v^{-1}\) over finite exponent boxes of the finitely many unitary generators needed to approximate a given test; use the sup-norm unitization, then diagonally cut off both factors to get tensors in \(C_0(U)\widehat\otimes_\pi C_0(U)\). For the group algebra use [Stokke (2004), Corollary 1.10](https://doi.org/10.4064/sm164-2-3). Interleave the two approximate diagonals by the contractive projective tensor map
\((f\otimes g,a\otimes b)\mapsto (fa)\otimes(gb)\).
For elementary tests the two commutator errors are exactly those of the two input diagonals, and the product is the pointwise product of their respective approximate identities. Density extends the conclusion without identifying the section norm with a projective norm.

The restriction of \(\delta|_{B(U)}\) to \(F_U^*\), where \(F_U=\overline{\operatorname{span}} B(U) V B(U)\), therefore has an implementer of norm at most \(\|\delta\|\), by taking a weak-star limit of the approximate diagonals mapped by \(a\otimes b\mapsto a\,\delta(b)|_{F_U}\). Choose a same-norm Hahn–Banach extension \(z_i\in V^*\) of this implementer for each of finitely many charts over a compact \(L\subset X\). Use nonnegative \(\phi_i\) as above, and choose \(0\le\psi_i\le1\) supported in the same chart with \(\psi_i=1\) near \(\operatorname{supp}\phi_i\). Set
\[
 \chi_L=\sum_i\phi_i,\qquad
 \eta_L=\sum_i d_{\phi_i} z_i d_{\psi_i}.
\]
A further cutoff supported in \(U_i\) and equal to one near both supports lets us test the local implementation only on \(B(U_i)\). The discrepancy annihilates \(F_{U_i}\) and disappears after the two cutoffs, since \(d_{\psi_i}v d_{\phi_i}\in F_{U_i}\) for \(v\in V\), by the common approximate identity. The scalar commutation of \(\delta(b)\) then gives the exact identity \(\operatorname{ad}_{\eta_L}(b)=\delta(\chi_L b)\). This does not presume the Hahn–Banach extensions \(z_i\) commute with the diagonal.

Dual type (M) gives \(\|\eta_L\|\le\|\delta\|\) with no dependence on the size or multiplicity of the cover. Since \(\chi_L b\to b\) in norm as \(L\) increases, a weak-star limit implements \(\delta\) on \(B\). Together with the diagonal implementer this gives a bound \(4\|D|_B\|\) for the implementation on \(V^*\) of the original kernel restriction. This bound concerns the restriction, not the derivation on \(A\).

After subtracting that kernel implementer on \(V^*\), the proof above applies unchanged: conjugation along an arrow is now a Haar-preserving isomorphism \(K_{sh}\to K_{rh}\); the difference of two lifts is a local kernel section; and the factorization \(a=\beta m_u\) defines \(\beta\) as a section on the kernel bundle. The split averaging quotient and the reverse witness are also unchanged. This still does not address non-locally-trivial kernel bundles or bases without bisection lifts.


## A sharper kernel-restriction lemma without local triviality

This subsection proves a **kernel restriction result**, not by itself the full equivalence. Retain local bisection lifts for \(\pi\), but let the kernel \(p:\mathcal K\to X\) be any proper locally compact Hausdorff group bundle with a continuous system of normalized Haar probabilities, allowing the compact groups \(K_x\) to vary in isomorphism type. Write \(B\) for the sup-row completion of the compactly supported continuous kernel densities. For every \(D:A\to E^*\) as in the theorem, \(D|_B\) is inner, with implementer bounded by \(\|D|_B\|\) on \(V^*\) and by \(3\|D|_B\|\) on \(E^*\).

First \(B\) has a common contractive two-sided approximate identity with \(A\). For a finite set of compactly supported tests on \(\Sigma\), their compact projected support \(C\subset H\) has compact inverse image: under a local lift it is a pullback of the proper kernel bundle, and a finite cover by compact subsets of such lift domains suffices. Among kernel elements over \(r(C)\cup s(C)\), those moving any test density by more than a prescribed error somewhere on this inverse image are contained in a compact set disjoint from the unit section, by continuity and properness. Choose a positive compactly supported bump in the complementary neighborhood of the units whose Haar integral is positive on the endpoint projections, using a finite cover. Divide by its continuous Haar integral where this is positive and multiply by a scalar cutoff equal to one on the endpoint projections. Both convolution errors are uniformly small there, hence in range norm by a finite bisection cover of \(C\). Directing the construction by tests and accuracy gives the approximate identity. In particular \(V=\overline{\operatorname{span}}BEB\).

The evaluation \(q_x:B\to L^1(K_x)\) is a metric quotient. Continuous functions on the compact fiber lift by Tietze extension and cutoff, and the continuity of \(y\mapsto\|q_y b\|_1\) allows every lift to be cut down with arbitrarily small excess norm. Completeness and density then give the claim. Write \(I_x=\ker q_x\). By the projective tensor universal property,
\[
 \ker(q_x\widehat\otimes_\pi q_x)=
 \overline{I_x\otimes B+B\otimes I_x},
\]
and the quotient norm equals the fiber projective norm. Indeed, the inverse to the quotient map on elementary products is given by taking arbitrary lifts modulo this closed sum; near-minimum-norm lifts make that bilinear map contractive.

Given finite \(F\subset C_c(\mathcal K)\) and \(\varepsilon>0\), take at \(x\) a norm-one approximate diagonal for \(L^1(K_x)\) ([Stokke (2004), Corollary 1.10](https://doi.org/10.4064/sm164-2-3)), and lift a finite decomposition by near-minimum-norm factors in \(B\). Its fiber commutator with \(b\in F\) is arbitrarily small, hence the lifted commutator is close in **global** projective norm to a finite sum in \(I_x\otimes B+B\otimes I_x\). Multiplying both tensor factors by a scalar cutoff equal to one near \(x\), with sufficiently small support, makes every such finite sum small in global projective norm: the factor belonging to \(I_x\) has a continuous norm profile vanishing at \(x\). The resulting tensor \(t_x\) has norm \(\le 1+\varepsilon\), global commutators \(\|bt_x-t_xb\|_\pi\le\varepsilon\), and \(\|q_y(\Pi(t_x)b-b)\|_1\le\varepsilon\) for \(y\) in some neighborhood of \(x\). Here \(\Pi\) is the product map.

Take nonnegative cutoffs \(\phi_j\) in finitely many such neighborhoods, with sum at most one and equal to one on the compact base support of \(F\). Write \(d=D|_{B,V^*}\), \(\Psi(a\otimes b)=a d(b)\),
\[
 u=\sum_j\phi_j\Pi(t_j),\qquad \eta=\sum_j d_{\phi_j}\Psi(t_j).
\]
The \(u\)'s form a bounded two-sided approximate identity for \(B\) as \(F\) increases and \(\varepsilon\) decreases: the product estimates give \(\|ub-b\|\le\varepsilon\), and global commutator estimates give \(\|bu-ub\|\le\varepsilon\) on \(F\), with the sup-row norm controlling the scalar sum. Applying the dual type (M) inequality to the sum for \(\eta\) and to the Leibniz identity
\[
 [b,\Psi(t_j)]=\Psi(bt_j-t_jb)+\Pi(t_j)d(b)
\]
gives \(\|\eta\|\le(1+\varepsilon)\|d\|\) and \(\|[b,\eta]-u d(b)\|\le\varepsilon\|d\|\) on \(F\). The cutoffs commute with \(b\) as multipliers; no commutation with \(\Psi(t_j)\) is assumed. Since \(u\) acts weak-star as an approximate identity on \(V^*\), a weak-star cluster point implements \(d\) with norm at most \(\|d\|\). To implement the restriction on \(E^*\), take a Hahn–Banach lift \(z\) and weak-star subnet limits \(y=\lim e_i z e_i\), \(m=\lim D(e_i)\) for the contractive common approximate identity. As in the off-core argument above, \(D(b)=[b,y]+bm+mb\), with \(bmc=0\) for \(b,c\in B\). Joint limits \(m_\ell=\lim e_i m\), \(m_r=\lim m e_i\) show that the two terms are implemented by \(m_\ell-m_r\), of norm at most \(2\|D|_B\|\). Neither bound here is claimed optimal.

For example, over \(\{0\}\cup\{1/n:n\ge1\}\), take \(K_{1/n}=\mu_n\subset\mathbb T\) and \(K_0=\mathbb T\). The bundle is proper and not locally trivial at \(0\); the uniform measures on \(\mu_n\) converge weakly to circle Haar measure by testing characters, so the continuity hypothesis holds. By contrast, setting every \(K_{1/n}=\{1\}\) makes Haar discontinuous: even a section with zero fiber norm at \(0\) can have norm one arbitrarily near \(0\) in the sup-row completion, so the cutoff argument cannot be inferred from properness alone.
