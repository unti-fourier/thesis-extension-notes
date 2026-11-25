# A Johnson-type criterion for Hausdorff étale groupoids

**Work in progress.** Research notes toward a possible future paper, not a submission, preprint, peer-reviewed publication, or profile entry. The result below has been checked in writing; the universal characterization has not been formalized in Lean. No priority claim is made.

Let \(G\) be a locally compact Hausdorff étale groupoid, \(X=G^{(0)}\), and \(\lambda\) a full continuous left Haar system. Let \(A\) be the completion of \(C_c(G)\) for the one-sided range norm
\[
\|f\|_r=\sup_{x\in X}\int_{G^x}|f(\gamma)|\,d\lambda^x(\gamma).
\]
Write \(P=C_0(X)\) for the diagonal in \(A\), normalized by the Haar mass of the unit. For a contractive Banach \(A\)-bimodule \(E\), put \(E_0=\overline{\operatorname{span}}(A E A)\). Require right diagonal type (M) on \(E_0\):
\[
\sum_j\|\xi h_j\|\le \Big\|\sum_jh_j\Big\|_\infty\|\xi\|\qquad(\xi\in E_0,\ h_j\in P_+).
\]

**Criterion.** The groupoid \(G\) is topologically amenable if and only if every bounded derivation \(A\to E^*\) is inner for every such \(E\). Neither compactness of the units nor essentiality of \(E\) is assumed. The algebra is the one-sided range completion, not the two-sided \(I\)-norm completion. This is not a characterization by ordinary Banach amenability; no universal statement for non-étale groupoids is claimed here.

## Proof

First use counting Haar. The map \(R:A\to P\) is the range sum. On compact sets, the Reiter condition uses positive \(p\in C_c(G)\) with \(Rp\le 1\), \(Rp\) uniformly approaching \(1\) on compact sets of units and \(\|\gamma p_{s\gamma}-p_{r\gamma}\|_1\) uniformly approaching zero on compact sets of arrows. Use a net indexed by the two compact sets and precision, not a sequence unless an exhaustion is available. For the equivalence with continuous probability fields, each such field has continuous point masses on open bisections. A finite family of compact arrow cutoffs captures uniformly almost all mass over the compact set of units being tested. Normalize the truncated field there, then taper it by a unit cutoff supported where the truncated mass is positive. Conversely, fill a subprobability's missing mass by the point mass at the unit; the increase in the defect at \(\gamma\) is at most the sum of the missing masses at \(r\gamma\) and \(s\gamma\).

For the forward implication first take a coefficient \(E\) satisfying (M) on all of \(E\). Subtract an inner derivation so that the resulting \(\delta\) vanishes on \(P\), using Banach amenability of the commutative \(C^*\)-algebra \(P\). For \(f\in C_c(B)\) on an open bisection \(B\), let \(0\le u\le1\) be a cutoff in \(C_c(B)\) equal to one near \(\operatorname{supp}f\), and set
\[
T_B(f)=\delta(f)u^* .
\]
For any two cutoffs choose a source cutoff equal to one on \(s(\operatorname{supp}f)\) and supported in the source of their common bisection neighborhood where both equal one. Right-multiplying \(\delta(f)\) by this source cutoff leaves it unchanged; left-multiplying either adjoint cutoff by it gives the same function. Thus the construction agrees on overlaps. A finite nonnegative partition on the compact support and a common refinement define a linear \(T\) on \(C_c(G)\). Moving a diagonal function from range to source along \(B\) gives \(T(hf)=hT(f)=T(f)h\).

For a partition \(f=\sum_j f_j\) on bisections, write \(f_j=(Rf_j)u_j\). Both \(u_j\) and \(u_j^*\) have range norm at most \(1\), so \(T(f)=\sum_j(Rf_j)\delta(u_j)u_j^*\). Dual type (C) gives
\[
\|T(f)\|\le \|\delta\|\big\|\sum_j|Rf_j|\big\|_\infty=\|\delta\|\|f\|_r.
\]
The complex phases can be approximated by \(z/(|z|+\varepsilon)\), and the final equality uses the nonnegative partition, not disjointness of its supports.

For bisection-supported \(f\) and its cutoff \(u\), use the product of cutoffs on an overlapping pair of composable bisections and apply the derivation identity. It gives \(T(f*p)=fT(p)u^*+\delta(f)(Rp)u^*\). Subtract \(T((Rf)p)\) and right-multiply by \(u\). Since \(u^*u=1\) on the relevant source support,
\[
T\big(f*p-(Rf)p\big)u=fT(p)-T(p)f+\delta(f)(Rp).
\]
The range norm of the argument of \(T\) is at most \(\|f\|_\infty\) times the supremum of the Reiter defects over \(\operatorname{supp}f\). Also \(\delta(f)(Rp)=\delta(f(Rp))\) converges to \(\delta(f)\), since the mass converges uniformly on \(s(\operatorname{supp}f)\). A single weak-star cluster point of \(-T(p)\) therefore implements \(\delta\) on every bisection and hence on \(A\).

For an arbitrary \(E\) apply this result to the restricted derivation into \(E_0^*\), lift its implementer by Hahn–Banach and subtract the lifted inner derivation. The residual \(d\) has values in \(Y=E_0^\perp\), with \(AYA=0\). The diagonal cutoffs give a two-sided contractive approximate identity \(e_i\). Take a weak-star cluster point \(m\) of \(d(e_i)\), and use two independent copies of that subnet in \(d(e_i a e_j)\). The middle term vanishes and \(d(a)=am+ma\). If \(m_L\) is a weak-star cluster point of \(e_i m\), then \(am_L=am\) and \(m_La=0\). Thus \(d(a)=a(2m_L-m)-(2m_L-m)a\).

For the reverse implication use the specified derivation from the [single-derivation criterion](06-etale-innerness-reiter.md) with \(K=\ker R\) and \(E=P\widehat\otimes_\pi K^\sharp\), where \(K^\sharp\) is the closure of the span of \(K^*\cdot A\). The direct range estimate \(\|\sum_jh_jk_j\|_r\le\|\sum_jh_j\|_\infty\max_j\|k_j\|_r\) gives right type (M) on \(K^*\) by duality. This passes to \(K^\sharp\) and to the projective tensor product by applying the estimate to one common tensor representation and then taking the infimum. The diagonal cutoffs give left essentiality on the \(P\) factor and right essentiality on \(K^\sharp\), since \((\varphi\cdot a)\cdot e_i=\varphi\cdot(ae_i)\). Thus this coefficient is in the tested class, and innerness of its derivation yields the Reiter condition.

Finally put \(w(x)=\lambda^x(\{1_x\})\). The units are clopen, so continuous Haar integration of a local unit cutoff shows that \(w\) is continuous; full support gives \(w>0\). Left invariance gives \(\lambda^{r\gamma}(\{\gamma\})=w(s\gamma)\). The map \(f\mapsto(w\circ s) f\) is a range-isometric algebra isomorphism to the counting completion: the weights on the two factors in a convolution term are \(w(s\eta)w(s\gamma)\). It maps the normalized diagonal \(p/w\) onto the ordinary diagonal and intertwines the range integrals. No global bound on \(w\) or its reciprocal is needed. It transports the coefficient hypothesis and the Reiter densities.

## References and scope

- Nicolas Monod (2010), [A note on topological amenability](https://arxiv.org/abs/1004.0199), Definition 1 and Proposition 2, for the type (M)/(C) terminology and duality in the compact setting. The dual inequality used here follows directly from the dual norm for \(C_0(X)\).
- Jean Renault (2013 preprint), [Topological amenability is a Borel property](https://arxiv.org/abs/1302.0636), Definitions 2.6–2.7 and Proposition 2.8, for the Reiter formulation. The proof above uses nets of local tests, not the \(\sigma\)-compact sequence formulation.
- The [companion note](06-etale-innerness-reiter.md) gives the reverse implication for the specified derivation with noncompact units and separates its written and Lean-checked parts. That verification does not cover the universal criterion in this note.
