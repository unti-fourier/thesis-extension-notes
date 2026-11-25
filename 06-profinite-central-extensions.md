# Uniform innerness for profinite central extensions

**Work in progress.** Written-checked research notes for a possible future paper, not a submission, preprint, peer-reviewed result, or profile entry. No Lean or priority claim.

Let \(H\) be a locally compact Hausdorff topologically amenable étale groupoid with compact unit space \(X\). Let \(G\to H\) be a locally trivial central extension with kernel \(X\times K\), where \(K\) is a profinite abelian group. Equip \(G\) with the continuous left Haar system obtained by summing normalized Haar probabilities on the \(K\)-torsors over the arrows of \(H\). Write \(A\) for its one-sided range-norm convolution completion. The diagonal \(C(X)\) acts by range and source multipliers; it need not be supported by elements of \(A\).

**Proposition.** Let \(E\) be a contractive Banach \(A\)-bimodule. If the right diagonal multiplier action on \(E_0=\overline{\operatorname{span}}AEA\) has type (M), every bounded derivation \(D:A\to E^*\) is inner with an implementer of norm at most \(6\|D\|\). This includes non-étale examples when \(K\) is infinite; the result does not assert the universal forward implication for arbitrary continuous Haar systems.

## Finite quotients and their norms

For an open subgroup \(N\subseteq K\) let \(d=[K:N]\), let \(H_N=G/N\), and write \(\pi_N:G\to H_N\). The function \(e_N=d1_{X\times N}\) is a compactly supported norm-one central idempotent. Left convolution by it averages over left \(N\)-translations; right convolution averages over right \(N\)-translations. These agree by centrality of the extension and inversion invariance of Haar probability on \(N\). Thus the image of this average is the corner \(A_N=e_NAe_N\).

The normalized counting model of the finite quotient embeds via
\[
I_N b=d(b\circ\pi_N).
\]
On each range fiber the mass over any one quotient arrow is \(1/d\); substituting into the range integral proves the isometry. In convolution it cancels one of the two factors \(d\), proving multiplicativity. An \(N\)-invariant compactly supported function descends, so \(I_N\) has image \(A_N\) after completion. Decreasing \(N\) gives an increasing family of corners. For \(f\in C_c(G)\), averaging over \(N\) converges uniformly on its compact \(K\)-saturated support. The projection of that support to \(H\) is covered by finitely many bisections, so all range rows on the support have uniformly bounded Haar mass. Hence the averages converge in range norm, and the union of the corners is dense.

Each \(H_N\) has the Reiter property: if \(p\) is a counting Reiter density on \(H\), its pullback divided by \(d\) is a counting density on \(H_N\) with the same row masses and the same defect above each arrow. The preimage of a compact support remains compact by local triviality and the compact finite fiber. This is a direct special case of the extension mechanism in Anantharaman-Delaroche–Renault (2000), [Amenable Groupoids](https://www.unige.ch/math/EnsMath/en/monographies/monographie-no-36), §5.1.

## Implementers on one common dual space

Fix \(e=e_N\). The unital corner coefficient \(E_N=eEe=eE_0e\) has right diagonal type (M): the diagonal element \(I_N(p)\) acts there by the original multiplier \(m_p\), since \(I_N(p)=e m_p\). The compression and inclusion between its dual and \(E^*\) are contractive, using the contractive projection \(\xi\mapsto e\xi e\). Thus the corner restriction \(eD(\,\cdot\,)e\) is implemented in \(eE^*e\) by a vector of norm at most \(4\|D\|\), uniformly in \(N\). For this bound, first implement the restriction to \(C(X)\) by averaging the bounded cocycle over its abelian unitary group, which gives norm at most \(\|D\|\). The remaining derivation has norm at most \(3\|D\|\); applying the averaging estimate in the [étale criterion](06-etale-essential-core.md) gives the other \(3\|D\|\).

For \(a=eae\) the full derivation satisfies
\[
D(a)=eD(a)e+a\,t_e-t_e\,a,\qquad t_e=eD(e)-D(e)e.
\]
Indeed \(eD(e)e=0\) and expanding \(D(eae)\) gives the two missing off-corner terms. The correction has norm at most \(2\|D\|\). The resulting vectors all lie in the same radius-\(6\|D\|\) weak-star compact ball of \(E^*\). On each fixed corner the implementation equations hold for every subsequent smaller \(N\); a cluster point thus implements the original \(D\) on the dense union and then on \(A\).

The bisection identity in the finite model becomes \(I_N(g)I_N(v)^*=m_{R g}e_N\) when \(g,v\) are supported on the same bisection and \(v=1\) near \(\operatorname{supp}g\). The term on the right acts as a diagonal on the corner only. One cannot simply replace such a convolution by the diagonal in operator norm on all of \(A\): already on \(L^1(\mathbb T)\), \(\|I-L_h\|=2\) for any positive probability density \(h\). Test on normalized functions supported on shrinking arcs: their convolution with \(h\) tends in norm to \(h\), whereas their distance to \(h\) tends to \(2\). This is a limitation of that approximation, not a counterexample to a general innerness result.
