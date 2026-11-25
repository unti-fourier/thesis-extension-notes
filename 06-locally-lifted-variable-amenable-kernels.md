# The locally lifted criterion for variable amenable kernel groups

**Work in progress.** This research note is not a submission, preprint, or peer-reviewed publication. The result is checked in writing, not in Lean. No priority claim is made.

Let \(q:\Sigma\to H\) be an open continuous surjective groupoid homomorphism fixing the unit space \(X\). Assume the arrow spaces are second-countable locally compact Hausdorff, \(H\) is étale, and every base arrow has a continuous lift on an open bisection. The kernel is a group bundle \(K\to X\) with a full continuous left Haar system \(\kappa_x\); assume every \(K_x\) is amenable. No local triviality of the bundle, compactness, or unimodularity of its fibers is required.

Use the counting-by-torsor left Haar system on \(\Sigma\) and its one-sided range-norm Banach algebra \(A\). Then the following are equivalent:

1. \(H\) is topologically amenable.
2. \(\Sigma\) is topologically amenable.
3. For every contractive \(A\)-bimodule \(E\) on whose essential core \(E_0=\overline{\operatorname{span}}AEA\) the right \(C_0(X)\)-multiplier action has type (M), every bounded derivation \(A\to E^*\) is inner.

The condition in (3) is \(\sum_j\|v d_{\phi_j}\|\leq\|v\|\|\sum_j\phi_j\|_\infty\) for \(v\in E_0\) and finite families of nonnegative \(\phi_j\in C_0(X)\); right multiplication by \(d_\phi\) on \(A\) multiplies a density by \(\phi\circ s\).

## The analytic changes from a fixed kernel

In a local lift \(\tau\), \((h,k)\mapsto\tau(h)k\) identifies the inverse image of the bisection with the pullback of \(K\) along \(s\). The fiber measure \((\tau(h)\,\cdot)_*\kappa_{s(h)}\) is independent of the lift by left invariance. Summation over the range fibers of \(H\) gives a full continuous left Haar system: test a compactly supported density on finitely many charts, and use Haar continuity in the source coordinates of each chart. Left multiplication takes each torsor measure to the torsor measure on the target.

For right translation, use the convention
\[
(\operatorname{Ad}_{\sigma^{-1}})_*\kappa_{r(\sigma)}
  = j(\sigma)\kappa_{s(\sigma)}.
\]
This factor is positive, multiplicative, and continuous. To see continuity, integrate a fixed nonnegative compactly supported kernel test function on both sides, choosing it so that the denominator is positive near \(s(\sigma)\). For \(\sigma\) in a compact neighborhood, the integration variables contributing on the left lie in a fixed compact set: they are conjugates of points of the test support by elements of that neighborhood. Continuity follows from integration against the pullback Haar system. Compare [Ionescu, Kumjian, Renault, Sims and Williams (2020 preprint), Lemma 2.4](https://arxiv.org/abs/2001.01312).

The right point-mass multiplier along \(\tau\) pushes a row measure forward, so its density is \(u(h)j(\tau(h))a(\sigma\tau(h)^{-1})\), with \(h\) determined by \(s(h)=s(\sigma)\) in the bisection. It is bounded in row norm by \(\|u\|_\infty\); the left multiplier has the same bound. For \(a\) supported in a chart, let \(u\) be one on its quotient support. The density of the kernel factor in \(a=\beta m_u^\tau\) is \(\beta(k)=j(\tau(h))^{-1}a(k\tau(h))\), with \(r(h)=p(k)\). The factor is inverted here and is not needed in the row operator norm. Compact support follows by mapping the compact support of \(a\) into the kernel coordinate.

For a common two-sided contractive approximate identity in the kernel algebra and \(A\), fix a compact union \(C\) of test supports. Use nonnegative kernel densities with row mass at most one, equal to one at the endpoints of \(C\), and with support shrinking to the units over those endpoints. To obtain them, choose a nonnegative compactly supported bump positive near these units, divide by its continuous row mass where this is positive, and multiply by a unit cutoff supported there. The left averages use \(a(k^{-1}\sigma)\), and the right averages use \(j(k)a(\sigma k^{-1})\). Both converge uniformly to \(a(\sigma)\) for the relevant composable pairs with \(k\) near the units. The supports of the errors are in one compact set, contained in \(C\cup\overline V C\cup C\overline V\) for a fixed relatively compact kernel neighborhood \(V\) of the endpoint units. Its row mass is bounded uniformly by the row integrals of a compactly supported bump. This proves convergence in the range norm as well. This argument requires neither a single common kernel coordinate group nor finite masses of whole torsors.

By the [ordinary Banach amenability of the kernel algebra](06-amenable-group-bundle-diagonals.md), remove an inner derivation in the original \(E^*\) to make \(\delta|_B=0\), where \(B\) is the embedded kernel algebra. Now use the [local-lift argument for fixed kernels](06-locally-lifted-amenable-kernel.md) on the essential core, with the row multipliers and the factorizations above. The argument uses only the two groupoid multiplier identities on intersections, the row bounds and the right type (M) estimate on the base diagonal, not fixed kernel coordinates. In particular the defects of two lift choices are kernel point translations, on which the extension of \(\delta\) is zero. The quotient Reiter averaging thus implements the restriction to \(E_0\) when \(H\) is amenable. Extend that implementer \(z\) to \(E^*\) with its norm unchanged. For the common approximate identity \(e_i\in B\), the equality
\[
e_i\delta(a)e_i=e_i(az-za)e_i=\delta(e_i a e_i)
\]
holds because \(e_i E e_i\subset E_0\) and \(\delta(e_i)=0\). Its difference from the commutator of \(a\) with \(e_i z e_i\) has norm at most \(2\|z\|\|e_i a-a e_i\|\). Take a weak-star cluster point to get an implementer on the original \(E^*\).

## Amenability transfer with variable fibers

For any compact \(F\subset K\) and compact \(Y\subset X\) containing \(p(F)\), there is a nonnegative compactly supported kernel density \(g\) with row masses at most one, equal to one on \(Y\), and with
\[
\sup_{k\in F}\int_{K_{p(k)}}|g(k^{-1}t)-g(t)|\,d\kappa_{p(k)}(t)<\varepsilon .
\]
At \(y\), apply group amenability to the compact test \(F\cap K_y\), extend a positive compactly supported density from the closed fiber, and normalize locally by its row mass. The defect is continuous locally: restricting \(k\) to a compact neighborhood puts both translated and untranslated supports in one compact set. If \(O_y\) is the resulting open subset of \(K\) with defect \(<\varepsilon\), then \(p(F\setminus O_y)\) is compact and excludes \(y\). Thus one neighborhood of \(y\) controls **every** vector of the compact test above that neighborhood. Patch over \(Y\) with nonnegative base weights. This is the fixed-compact-test argument of [Renault (2013 preprint), Theorem 3.5](https://arxiv.org/abs/1302.0636).

Now choose a base Reiter density \(p=\sum_j p_j\) with each nonnegative \(p_j\) compactly supported in a bisection admitting a lift \(\tau_j\). For a compact arrow test \(C\subset\Sigma\), transport a term over \(h\) by \(\eta\in C\) and compare it with a term over \(h'=q(\eta)h\). Their discrepancy is left translation by
\[
\tau_l(h')^{-1}\eta\tau_j(h)\in K_{s(h)}=K_{s(h')}.
\]
For each pair of charts, the composable test pairs with \(h\in\operatorname{supp}p_j\) and \(h'\in\operatorname{supp}p_l\) form a compact set, so the union of discrepancy images is compact. Use it as \(F\), with \(Y=s(\operatorname{supp}p)\), and put \(g\) into every torsor using the appropriate source coordinate. The resulting lifted density has the same row masses as \(p\). At matching quotient arrows, couple the chart mixtures on their common mass \(\min(p(h),p(h'))\). Its error is bounded by \(\varepsilon\) times that common mass; the unmatched mass costs the original base defect. Summing over a row yields at most the base defect plus \(\varepsilon\). This proves the forward topological implication. The reverse pushes probability fields down and tests on finitely many compactly supported local lifts of each compact base test.

For the reverse derivation implication, torsor integration is a contractive algebra map \(Q:A\to A_r(H)\) by left invariance and Fubini. A partition of unity on \(H\) applied to positive compactly supported chart densities with nonzero fiber integrals gives a nonnegative continuous density \(b\) with integral one on each torsor and support proper over \(H\). Hence \(f\mapsto(f\circ q)b\) is an isometric linear section. Pull back the [étale derivation witness](06-etale-essential-core.md) along \(Q\); surjectivity and compatibility with diagonal multipliers preserve the essential core and type (M), and any implementer descends to the base witness. No multiplicative section is needed.

For an ample quotient, the [clopen selection argument](06-locally-lifted-amenable-kernel.md#ample-quotients-continuous-lifts-are-automatic) makes the topological lift assumption automatic under the two second-countability hypotheses. This does not settle the general forward derivation criterion for a non-ample quotient without local lifts.
