# A norm-one approximate diagonal for a pair groupoid

**Work in progress, November 2026.** This is a written-checked research note, not a submission or peer-reviewed paper. No Lean verification or priority claim is made.

Let \(X\) be a compact metric space with a full-support nonatomic Radon probability \(\mu\). Complete the continuous kernels on \(X\times X\) in the Schur \(I\)-norm, the maximum of the suprema of integrated absolute rows and columns, with product given by kernel composition using \(\mu\). This Banach algebra \(A\) is amenable with amenability constant \(1\).

Measurable block kernels are not generally in this completion. On the Lebesgue interval the kernel equal to \(2\) on the two diagonal blocks of an equal two-part partition and \(0\) elsewhere has two constant row values at \(L^1\) distance \(2\), on opposite sides of the partition boundary. Continuous kernels have \(L^1\)-continuous rows, giving distance at least \(1\); the constant kernel \(1\) attains it.

Instead, partition \(X\) into finitely many positive-measure Borel cells of small diameter (use a finite separated net and Voronoi cells). Subdivide every cell of mass \(t\), using nonatomicity, into \(\lceil Nt\rceil\) equal pieces; as \(N\) increases their masses have ratio tending uniformly to one. Take a compact core \(K_i\) inside each final piece, leaving total mass \(\tau\) negligible relative to the smallest piece's mass. Small-diameter open neighborhoods of the pieces cover \(X\). Remove all other cores from each neighborhood: this remains an open cover, and any partition of unity \(p_i\) subordinate to it equals \(1\) on its own core. If \(m_i=\int p_i\,d\mu\), then \(m_{\max}/m_{\min}\to1\) and \(\tau/m_{\min}\to0\), since \(p_i\) differs from its piece's indicator only off the union of the cores.

With \(\|\cdot\|_{\rm S}\) the maximum of absolute matrix row and column sums, write
\[
 T(B)(x,y)=\sum_{i,j}p_i(x)B_{ij}p_j(y)/m_j,\qquad
 G_{ij}=\int p_ip_j\,d\mu/m_i .
\]
Then \(T(B)T(C)=T(BGC)\), and integrating rows and columns gives \(\|T\|\le m_{\max}/m_{\min}\). The diagonal deficit of \(G\), and its off-diagonal row and column sums, are each bounded by \(\tau/m_{\min}\). For columns use \(\sum_{i\ne j}p_i p_j=p_j(1-p_j)\), supported off the cores. Thus \(\|G-I\|_{\rm S}\le2\tau/m_{\min}\), and \(J(B)=T(BG^{-1})\) is an algebra homomorphism with \(\|J\|\le1+o(1)\).

The kernel \(T(I)\) has row and column integrals one and is supported within the chosen small distance of the diagonal. Uniform continuity of continuous kernels makes it a two-sided approximate identity in \(A\) as the diameter tends to zero; \(P=J(I)\) differs from it by \(o(1)\) in \(I\)-norm. Also \(PaP\) lies in \(J(M_n)\), first on continuous kernels by expansion of the two finite sums, then on all \(A\) by density and closedness of the finite-dimensional image.

The signed permutation matrices give a norm-one matrix diagonal by averaging \(u\otimes u^{-1}\) (the finite-group construction in [Grønbæk–Johnson–Willis, 1992 preprint, Proposition 3.2](https://arxiv.org/html/math/9209211v1#S3)). Map it by \(J\otimes J\) to \(D\). Its product is \(P\), its projective norm is at most \(1+o(1)\), and it commutes with \(PaP\). Thus \(\|aD-Da\|_\pi\le2\|D\|_\pi\|a-PaP\|_I\to0\). Rescaling by \(\max(1,\|D\|_\pi)\) yields an approximate diagonal bounded by one. A smaller bound is impossible since its products are an approximate identity in a nonzero algebra.

## Unequal weights on a finite pair groupoid

For a nonempty finite \(X\) and positive point masses \(m_i\), the algebra is isomorphic to a matrix algebra by \(a_{ij}=\sqrt{m_i m_j}f(i,j)\). Its amenability constant is one exactly when the weights are equal. For two weights \(m_1\ge m_2\), the exact constant is \((1+t)/2\), \(t=m_1/m_2\).

Indeed, all matrix diagonals have the form \(D_C=\sum_{i,j,k}c_{jk}E_{ij}\otimes E_{ki}\) with \(\operatorname{tr}C=1\), by centrality against matrix units and the product condition. In finite dimension the least possible projective norm of a diagonal equals the amenability constant by compactness. In dimension two, the canonical signed-permutation average has norm at most \((1+t)/2\): half of its terms have both factor norms one, and the exchange terms have both factor norms \(\sqrt t\). The bilinear test
\[
 \Phi(a,b)=a_{22}b_{22}+\tfrac{t+1}{2}a_{21}b_{12}+\tfrac{t-1}{2}a_{12}b_{21}
\]
has norm at most one, since \(\|a\|_I\ge |a_{22}|+\sqrt t\max(|a_{12}|,|a_{21}|)\) and likewise for \(b\). It takes the value \((1+t)/2\) on every \(D_C\), proving sharpness.

In arbitrary finite dimension, a norm-one diagonal would be a convex combination of products of two contractions in the projective unit ball, with products averaging to the identity. The normalized real trace exposes the identity in the Schur unit ball: equality forces every diagonal entry to be \(1\), then the row bound forces the off-diagonal entries to vanish. Thus each tensor factor is an invertible contraction with contractive inverse. In the integral-operator coordinates \(m_j f(i,j)\), it is simultaneously an isometry of \(\ell^\infty\) and of \(\ell^1(m)\), hence is a phase-weighted permutation that preserves the point masses. All first factors would then be block diagonal along equal-weight blocks. This contradicts the displayed description of \(D_C\) for unequal weights, because some \(c_{jj}\ne0\) and the corresponding terms \(E_{ij}\otimes E_{ji}\) run over every \(i\). Conversely, for equal weights the signed-permutation average gives a norm-one diagonal. Finite corner bounds alone are not being asserted for the infinite completion. This section was independently checked in writing.

## Infinite compact spaces and mixed measures

Let \(X\) be infinite compact Hausdorff and let \(\mu\) be a finite positive full-support Radon measure of total mass \(M\). Write \(d\) for its nonatomic mass. The amenability constant is \(M/d\) for \(d>0\); the algebra is not amenable for \(d=0\). The nonatomic part need not have full support.

For the lower bound, for a Borel set \(S\) use the bilinear test
\[
 B_S(a,b)=M^{-1}\int_S \Big(\int a(x,z)\,d\mu(x)\Big)
                          \Big(\int b(z,y)\,d\mu(y)\Big)d\mu(z).
\]
It has norm at most \(\mu(S)/M\). For a bounded approximate diagonal \(D_\alpha\), \(B_X(D_\alpha)\to1\) by testing the approximate identity of products on the constant kernel. If \(z\) is an atom of mass \(m_z\), the map \(K_z(a\otimes b)(x,y)=m_z a(x,z)b(z,y)\) has sup norm at most \(m_z^{-1}\|a\|_I\|b\|_I\). It intertwines outer convolution. Thus the \(K_z(D_\alpha)\) give bounded Hilbert–Schmidt operators on \(L^2(\mu)\) whose weak cluster points commute with the rank-one operators constructed from continuous functions. By density these cluster points are scalar identities and hence zero, because \(L^2(\mu)\) is infinite-dimensional. Therefore \(B_{\{z\}}(D_\alpha)\to0\). Removing finitely many atoms, then letting their total mass increase to \(M-d\), proves \(1\le(\sup_\alpha\|D_\alpha\|_\pi)d/M\).

For the construction, use two different continuous families. At the endpoints, take a partition \(p_i\) on a fine finite open cover and compact cores as above, but without balancing cell masses. A finite irredundant cover gives each cell a nonempty open subset and hence positive mass. For \(m_i=\int p_i\,d\mu\) and the same \(G\) as above, the core error gives both the absolute row-sum and the mass-weighted absolute column-sum bound \(\|G-I\|\le\varepsilon\) in the respective matrix norms. The weighted bound follows from \(m_iG_{ij}=m_jG_{ji}\). Put \(q_i=\sum_j(G^{-1})_{ij}p_j/m_j\); then \(\int q_i p_j=\delta_{ij}\) and
\[
 \max\{\max_i\|q_i\|_1,\|\sum_i m_i|q_i|\|_\infty\}\le (1-\varepsilon)^{-1}.
\]
The matrix units \(p_i\boxtimes q_j\), where \((p\boxtimes q)(x,y)=p(x)q(y)\), have sum of diagonal units \(P\) within \(\varepsilon/(1-\varepsilon)\) of the local approximate identity \(\sum_i p_i\boxtimes(p_i/m_i)\). Fine covers here mean small oscillation for the given finite collection of continuous kernels in both variables, which suffices also in the nonmetrizable case.

At the intermediate variable only, partition the nonatomic mass into \(N\) sets of mass \(t=d/N\). By inner and outer regularity, choose disjoint compact cores and then disjoint open neighborhoods with original \(\mu\)-mass at most \((1+\varepsilon)t\). Continuous cutoffs \(0\le u_l\le1\) supported there can satisfy \(\int u_l^2\ge(1-\varepsilon)t\). Put \(v_l=u_l/\int u_l^2\). Then
\[
 D=N^{-1}\sum_{i,l}(p_i\boxtimes v_l)\otimes(u_l\boxtimes q_i)
\]
has product \(P\) and commutes with all the matrix units. For the projective bound, assign disjoint blocks \(L_i\) of sizes \(k_i=\lfloor Nm_i/M\rfloor\) in the \(N\)-element index set. For sufficiently large \(N\) each \(k_i\ge(1-\varepsilon)Nm_i/M>0\). Apply a uniformly random cyclic shift to the blocks, and independent signs \(\sigma_l\). The tensor \(D\) is the average of \(U\otimes V\), where
\[
 U=\sum_{i,l\in L_i} k_i^{-1}\sigma_l\,p_i\boxtimes v_l,\qquad
 V=\sum_{i,l\in L_i}\sigma_l\,u_l\boxtimes q_i.
\]
Cross terms disappear by sign averaging and each \(l\) belongs to block \(i\) with probability \(k_i/N\). Disjoint supports of the \(u_l\) give \(\|U\|_I\le(M/d)/(1-\varepsilon)^2\) and \(\|V\|_I\le(1+\varepsilon)/(1-\varepsilon)\) by the row and weighted column estimates. The compression \(PaP\) lies in the matrix span, so the earlier centrality estimate applies. Refining the endpoint covers and sending \(\varepsilon\) to zero yields the upper bound \(M/d\) (rescale the tensors by factors tending to one if necessary). This includes isolated atoms, since only the intermediate cutoffs are chosen in neighborhoods of nonatomic cores. The proof is written-checked, not formalized.

## Restricted derivations for a purely atomic Haar measure

For infinite compact \(X\) with purely atomic full-support \(\mu\), the preceding failure of ordinary amenability does not extend to the right \(C(X)\)-type (M) condition. Namely, every bounded derivation \(D:A\to E^*\) is inner for a two-sided contractive Banach bimodule \(E\) with this condition on its essential core. This is a written result, not a Lean verification.

First take essential \(E\), and set \(W=E^*\). The dual type (M) inequality bounds \(\|\sum_i p_iw_i\|\) by \(\max_i\|w_i\|\) for every positive partition of unity (cf. [Monod, 2010 preprint, Proposition 2](https://arxiv.org/pdf/1004.0199#page=3)). A kernel \(k\) whose input and output support projections are disjoint has left-action norm on \(W\) at most its row norm. To see this when the row norm is at most one, choose cutoffs \(0\le\theta,\psi\le1\), with \(\theta=1\) on the output support, \(\psi=1\) on the support of \(\theta\), and both zero on the input support. For small positive \(t\), \(L=(1-t)M_\theta+tk\) acts contractively: the row sum is at most one and the column terms have disjoint support, with \(t\|k\|_{\rm col}\le1\). These estimates applied to convolution show that \(L\) acts contractively as a multiplier, and the contractive approximate identity extends this bound to essential modules and their duals. If \(\|w\|\le1\) and \(kw\ne0\), put \(y=kw/\|kw\|\). Then \(\|\psi y+(1-\psi)w\|\le1\), and \(L\) sends this vector to \((1-t)y+tkw\). Thus \(\|kw\|\le1\).

Use the earlier continuous partitions and Gram correction to get corners with matrix units \(e_{ij}=p_i\boxtimes q_j\), \(\sum_i p_i=1\), \(\|q_i\|_1\le2\), and \(P=\sum_i e_{ii}\) a bounded two-sided approximate identity. For each corner separately choose an atom of sufficiently small mass \(s>0\) and an open neighborhood \(O\) of it with \(\mu(O)<2s\) and \(\mu(O)\max_i\|q_i\|_\infty\le1\). Choose a continuous \(0\le u\le1\) supported there and equal to one at the atom, and put \(v=u/\int u^2\). Then \(\int vu=1\), \(\|u\boxtimes q_i\|_I\le2\). The left-action norm of \(1\boxtimes v\) on \(W\) is at most four: split its output with a cutoff supported in \(O\) and equal to one near \(\operatorname{supp}u\). The first part has \(I\)-norm at most two and the second has disjoint input and output supports and row norm at most two.

Now
\[
 \xi_P=\sum_i (p_i\boxtimes v)\cdot D(u\boxtimes q_i)
\]
has norm at most \(8\|D\|\) by type (M). Matrix-unit multiplication and the derivation rule give \(x\xi_P-\xi_P x=P D(x)\) for every \(x\in PAP\): move the matrix coefficients from multiplication on the left of \(p_i\boxtimes v\) to multiplication on the right of \(u\boxtimes q_i\), then use \(\sum_i(p_i\boxtimes v)(u\boxtimes q_i)=P\). Taking \(x=PaP\) and a weak-star cluster point of \(\xi_P\) implements \(D\). For a nonessential \(E\), restrict to the dual of \(\overline{\operatorname{span}}AEA\) and extend the implementer by Hahn–Banach. The residual derivation \(D'\) takes values in \(V=(\overline{\operatorname{span}}AEA)^\perp\), where \(AVA=0\). A weak-star cluster point \(\tau\) of \(D'(P)\) gives \(D'(a)=a\tau+\tau a\) by expanding \(D'(PaP)\). The weak-star cluster points of \(P\tau-\tau P\) implement this last derivation. Thus the example separates the restricted and ordinary notions even though the underlying topological groupoid is proper.
