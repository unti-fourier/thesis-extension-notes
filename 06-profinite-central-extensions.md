# Uniform innerness for profinite central extensions

**Work in progress.** Written-checked research notes for a possible future paper, not a submission, preprint, peer-reviewed result, or profile entry. No Lean or priority claim.

Let \(H\) be a locally compact Hausdorff étale groupoid with compact unit space \(X\). Let \(G\to H\) be a locally trivial central extension with kernel \(X\times K\), where \(K\) is a profinite abelian group. Equip \(G\) with the continuous left Haar system obtained by summing normalized Haar probabilities on the \(K\)-torsors over the arrows of \(H\). Write \(A\) for its one-sided range-norm convolution completion. The diagonal \(C(X)\) acts by range and source multipliers; it need not be supported by elements of \(A\).

**Forward implication.** Suppose that \(H\) is topologically amenable. Let \(E\) be a contractive Banach \(A\)-bimodule. If the right diagonal multiplier action on \(E_0=\overline{\operatorname{span}}AEA\) has type (M), every bounded derivation \(D:A\to E^*\) is inner with an implementer of norm at most \(6\|D\|\). This includes non-étale examples when \(K\) is infinite; the result does not assert the universal forward implication for arbitrary continuous Haar systems.

The compact-unit proof is given first. The final section removes compactness of the unit space.

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

## Converse

It is not necessary to assume \(H\) amenable in the statement of the criterion: for these extensions the innerness test in the proposition is equivalent to topological amenability of \(G\), and also to topological amenability of \(H\).

Let \(Q:A_r(G)\to A_r(H)\) be averaging over the full \(K\)-torsor and let \(\iota b=b\circ\pi\). The case \(N=K\) above gives \(Q\iota=\mathrm{id}\) and \(\iota Q(a)=e_K*a=a*e_K\). In particular \(Q\) is a contractive surjective algebra map. Pull back the specified derivation and coefficient bimodule from the [étale criterion](06-etale-essential-core.md) along \(Q\). The essential core is unchanged because \(Q\) is onto, and the right diagonal action is unchanged because \(Q(a m_p)=Q(a)J_Hp\). The pulled-back derivation is thus among those tested. Restricting its implementation to \(\iota(A_r(H))\) implements the original derivation on \(H\), proving its amenability by the étale criterion.

It remains to compare the two amenability conditions. Left translation maps the normalized Haar probability on a \(K\)-torsor to the normalized probability on its image torsor. It follows that the Reiter defect of \(\iota p\) on \(\gamma\) equals that of \(p\) on \(\pi(\gamma)\). Conversely the defect of \(Qq\) on \(\pi(\gamma)\) is bounded by that of \(q\) on \(\gamma\), by contraction under pushforward. Row masses are unchanged. Pullback preserves compact support because a locally trivial bundle with compact fiber over a locally compact Hausdorff base is proper; pushforward preserves compact support by continuity. In the pushforward estimate one can therefore test every compact set of arrows of \(H\) using its compact inverse image. This proves amenability is equivalent in both directions. The forward argument gives a uniform norm bound when amenability holds.


## Removing compactness of the unit space

The same equivalence and the same upper bound \(6\|D\|\) hold for arbitrary locally compact Hausdorff unit space \(X\), with \(C_0(X)\) in place of \(C(X)\). The kernel, local triviality, centrality and Haar normalization hypotheses are unchanged. This is a written proof, not a Lean verification.

The averaging operators \(P_N\) are still central contractive multiplier projections. Their ranges \(B_N=P_N A\) are closed ideals, still isometrically isomorphic via \(I_N\) to the counting range completions on \(G/N\), and their increasing union is dense by the compact-support argument above. The multiplier projection \(e_N\) need not be in \(A\). For \(\chi_i\in C_c(X,[0,1])\) equal to \(1\) near a growing compact subset of \(X\), use instead the elements \(c_i=e_Nm_{\chi_i}\in B_N\). They form a two-sided contractive approximate identity for \(B_N\): multiplication by \(c_i\) cuts down the range or source coordinate of \(P_Na\), respectively. This converges first on compactly supported functions and then in the completion.

The coefficient for the restriction of \(D\) is \(F_N=\overline{\operatorname{span}} B_NE B_N\subset E_0\). The right diagonal in the finite quotient acts on \(F_N\) by the original multiplier: \((b_1vb_2)(e_Nm_p)=b_1v(b_2m_p)\). Hence the type (M) constant is unchanged, and \(F_N\) is essential on both sides for the finite-quotient diagonal \(C_0(X)\) by the cutoff argument. Write \(d\) for the restriction of \(D|_{F_N}\) to this diagonal. Its extension to the sup-norm unitization by \(d^+(1)=0\) has \(\|d^+\|\le\|d\|\): for \(p,t\in C_0(X)\), the Leibniz rule gives \(p\,d(\chi_i)\,t\to 0\) in norm, so \(d(\chi_i)\to 0\) weak-star by essentiality and boundedness. Therefore \(d(h\chi_i)=h d(\chi_i)+d^+(h)\chi_i\to d^+(h)\) weak-star. Averaging the cocycle over the unitary group of the unitization implements \(d\) with norm \(\le\|D\|\). The [étale averaging estimate](06-etale-essential-core.md) for the remaining diagonal-zero derivation contributes at most \(3\|D\|\). Thus there is an implementer on \(F_N^*\) of norm at most \(4\|D\|\), independently of \(N\).

Here the formula involving \(D(e_N)\) is not available. Extend the \(F_N^*\) implementer by Hahn–Banach to \(z\in E^*\) with the same norm. Since \(c_i E c_i\subset F_N\), we have \(c_i D(a)c_i=c_i\operatorname{ad}_z(a)c_i\) for \(a\in B_N\), where \(\operatorname{ad}_z(a)=az-za\). Take joint weak-star limits \(y=\lim c_i zc_i\) and \(m=\lim D(c_i)\) along a subnet. The middle term of the Leibniz expansion of \(D(c_iac_i)\) differs from \(\operatorname{ad}_{c_i zc_i}(a)\) by at most \(2\|z\|\|c_i a-a c_i\|\); the other terms converge to \(ma+am\). It follows that
\[
D(a)=ay-ya+ma+am,\qquad a\in B_N .
\]
The Leibniz expansion of \(D(ac_i b)\), with \(a,b\in B_N\), gives \(amb=0\). Now take joint weak-star limits \(m_\ell=\lim c_i m\) and \(m_r=\lim m c_i\), in a second subnet. Then \(a m_\ell=am,\ m_\ell a=0,\ a m_r=0,\ m_r a=ma\). Thus \(y+m_\ell-m_r\) implements \(D|_{B_N}\) on the original \(E^*\), with norm at most \(6\|D\|\). A common weak-star cluster point along decreasing \(N\) implements \(D\) on the dense union and hence on \(A\).

For the converse the averaging retraction \(Q\) and the pullback of the specified étale witness work verbatim with the noncompact étale criterion. The identity \(\iota Q=P_K\) now denotes an equality of bounded maps, not multiplication by an element of \(A\). The same Reiter transport applies with compact tests as before; the densities need only have row mass \(1\) on compact sets under test, not on the whole noncompact unit space. This does not settle general continuous Haar systems, nor is the constant \(6\) claimed optimal.
