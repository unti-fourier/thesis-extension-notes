# An absolute degree-two witness for nonamenable compact actions

**Work in progress, November 2026.** This is a research note toward a possible future paper, not a submission, a peer-reviewed publication, or a publication-list entry. No priority is claimed.

Let a countable discrete group \(\Gamma\) act on a nonempty compact Hausdorff space \(X\), and let \(A=C(X,\ell^1(\Gamma))\) be the complex row-norm algebra with the twisted product \((f u_g)(b u_h)=f\,{}^g b\,u_{gh}\), where \({}^g b(x)=b(g^{-1}x)\).

**Result.** The action is topologically amenable if and only if the continuous absolute Hochschild group \(HH^2(A,E^*)\) vanishes for every essential contractive \(A\)-bimodule \(E\) with right \(C(X)\)-action of type (M). Here type (M) means \(\sum_i\|\xi\cdot p_i\|\le\|\xi\|\|\sum_i p_i\|_\infty\) for each \(\xi\in E\) and each finite family of nonnegative \(p_i\in C(X)\). For a nonamenable action, the witness can be chosen with
$$
\|B_2\|=\inf_{L\in\mathcal B(A,E^*)}\|B_2-\delta_{\mathrm{HH}} L\|=1.
$$
The infimum is over all continuous absolute coboundaries, not just relative coboundaries. In particular the class also survives in reduced cohomology.

**Measure-theoretic input.** The nonamenable action gives [one positive measured Reiter gap](02-measurable-reiter-gap.md). In the construction of the compact metrizable factor, include continuous summable \(L^1\) approximants of all Radon–Nikodym derivatives of the quasi-invariant witness measure, along with the Reiter coordinates. The pushed-forward derivatives then pull back to the original derivatives, by the integration formula for pushforwards. This lets the Maharam action and its height coordinate lift to the original space without a disintegration of its Radon measure.

On the standard factor add a free Bernoulli coordinate, then take the restriction of the Maharam orbit relation to a finite height band. This pmp restriction is nonamenable: hyperfinite exhaustions of that band would lift to the integer-translated bands and hence to the whole Maharam relation. Averaging invariant witnesses over growing height intervals would then give a witness downstairs, contrary to the measured gap. Apply [Bowen–Hoff–Ioana (2018), Theorem A](https://arxiv.org/html/1509.01723#Thmmain1) to the Bernoulli extensions of the nonamenable ergodic pmp components. The two free generators and their inverses admit simultaneous measurable label selection on a positive-measure family of components; it is not legitimate to select a single possibly null component instead. Equality of the derivatives ensures that the lifted labelled action is still probability preserving. For the passage between amenability and hyperfiniteness used here, see [Connes–Feldman–Weiss (1981), Theorem 10](https://doi.org/10.1017/S014338570000136X).

**Cochain and lower bound.** The labelled free action supplies an invariant transverse measure \(m\) on a measurable quotient \(Q\) and an equivariant anchor \(\rho:Q\to X\). For the predual \(E=C(X)\widehat\otimes_\pi L^1(Q,m)\), right multiplication by \(p\in C(X)\) acts by the scalar \(p\circ\rho\) on the \(L^1\) variable. The identification with \(L^1(Q,m;C(X))\) gives type (M) by integrating pointwise scalar multiplication. If \(\xi\) denotes the transferred norm-one bounded group cocycle, the absolute cochain on monomials is
$$
B_2(fu_g,bu_h)(v)
 =\big[(f\,{}^g b\,{}^{gh}v)\circ\rho\big]\,\xi(g,h),
 \qquad v\in C(X).
$$
The row norm gives a contractive extension of this formula. Evaluation on \(u_g,u_h\) and then at \(1_X\) is a contractive cochain map back to group cochains; transverse averaging on the identity slice is a contractive left inverse to the group transfer. Thus arbitrary absolute primitives give group primitives without increasing norm, and [Rolli (2009), Propositions 2.4 and 3.8](https://arxiv.org/html/0911.4234#S3.p1.16) gives the matching lower bound.

**Amenable direction.** [Lykova (1999), Theorem 2.6](https://jot.theta.ro/jot/archive/1999-041-001/1999-041-001-002.pdf#page=10) compares absolute and \(C(X)\)-relative cohomology with dual coefficients. The relative complex identifies with group cochains in the \(C(X)\)-central part of the unital corner of the coefficient. Its predual is obtained by quotienting the corresponding corner by \(C(X)\)-commutators; type (M) descends since the same lift tests all the summands. The resulting bounded group cohomology vanishes by [Monod (2011), §1.B](https://arxiv.org/html/1004.0199#Thmpropx1). For this direction the given predual need not be essential.

**Verification.** The end-to-end argument, including the measurable-selection and cochain-comparison steps, has been independently checked in writing. Some intermediate Reiter and factor lemmas were checked in Lean 4.27. The full degree-two theorem has not been formalized in Lean.
