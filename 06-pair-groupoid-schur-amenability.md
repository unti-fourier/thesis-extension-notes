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

## Constant discrete amenable isotropy

The restricted result extends to the product groupoid \(X\times\Gamma\times X\), with the product Haar system from the purely atomic measure on \(X\) and counting measure on a countable discrete amenable group \(\Gamma\). The implementer bound on the essential core is still \(8\|D\|\). Write \(k[h]\) for a pair kernel supported at group coordinate \(h\), and use the preceding \(a_i=p_i\boxtimes v\), \(b_i=u\boxtimes q_i\) in each matrix corner. The bound \(\|b_i[h^{-1}]\|_I\le2\) holds since the group coordinate is a singleton. The left-action bound of \((1\boxtimes v)[h]\) is at most four, by the preceding argument at the identity coordinate and the isometric group-translation multiplier. The pair approximate identity placed at the identity group element is an approximate identity for the entire algebra, first on the compactly supported kernels and then by density.

For a finite left Følner set \(F\), put \(\xi_{P,F}=|F|^{-1}\sum_{h\in F}\sum_i a_i[h]D(b_i[h^{-1}])\). For each \(h\) use the dual type (M) estimate on \(p_i\), then average over \(h\), obtaining \(\|\xi_{P,F}\|\le8\|D\|\). For \(x=e_{kl}[s]\) the difference \(x\xi_{P,F}-\xi_{P,F}x-P[e]D(x)\) is the difference of sums of \(a_k[t]D(b_l[t^{-1}s])\) over \(sF\) and over \(F\), each divided by \(|F|\), by the derivation rule and the change \(t=sh\). Its norm is bounded by \(8\|D\|\,|sF\triangle F|/|F|\). This uses no commutativity of \(\Gamma\). First take a weak-star limit at a fixed corner, then along the corners to get an implementer on the whole algebra as above. For infinite \(X\), summing over \(\Gamma\) is a contractive surjective homomorphism onto the pair algebra, so ordinary amenability still fails in the purely atomic case. This is a written check of this product class only.

## Constant locally compact isotropy and the modular function

For a compact Hausdorff space \(X\) with at least two points and a finite purely atomic full-support Radon measure, the essential-module result extends to \(X\times G\times X\) for every amenable locally compact group \(G\), including non-unimodular ones. The bound is again \(8\|D\|\). This is a written check for the product Haar system, not a Lean verification or a general groupoid theorem.

Write \(\lambda\) for left Haar measure and \(\lambda_R=\mathrm{inv}_*\lambda=q\lambda\). If \(K[f](x,s,y)=K(x,y)f(s)\), then the raw \(I\)-norm is the maximum of \(\|K\|_{\mathrm{row}}\|f\|_L\) and \(\|K\|_{\mathrm{col}}\|f\|_R\), using the \(L^1\) norms for \(\lambda\) and \(\lambda_R\). In formulas involving \(\delta_t\), convolution refers to convolution of measures and we identify the result with its density relative to \(\lambda\). Right translation preserves the left norm and scales the right norm by \(q(t)\); specifically \((f*\delta_t)(s)=q(t)f(st^{-1})\).

The disjoint-support left-action estimate above applies unchanged: a multiplier of the form \((1-t)M_\theta+tk\) contracts the raw \(I\)-norm by testing both Haar fibers, and extends to the essential module using a contractive approximate identity. The latter follows by tensoring the positive contractive endpoint partitions with normalized positive group kernels whose support tends to the identity and whose right norm tends to one, and rescaling if necessary.

In the matrix-corner construction choose \(u,v\) at the small atom as before, now with \(\|v\|_1\le3/2\). Choose \(u',v'\) at a different atom with disjoint supports, \(\int v'u'\,d\mu=1\) and \(\|v'\|_1\le3/2\). For a cutoff \(\chi=1\) near \(\operatorname{supp}u\), with support disjoint from \(\operatorname{supp}u'\), the \(1-\chi\) part of \((1\boxtimes v)[f]\) has disjoint input and output supports. For the other part use
\[
(\chi\boxtimes v)[f]=\lim_\beta
  (\chi\boxtimes v')[f]*(u'\boxtimes v)[r_\beta],
\]
where \(r_\beta\) are positive left-normalized group approximate units supported near the identity. Each factor has disjoint endpoint supports. Since \(f*r_\beta\to f\) in both Haar norms, the resulting left-action bound is \(\|v\|_1(1+\|v'\|_1)\|f\|_L\le4\|f\|_L\), with no dependence on \(\|f\|_R\).

Use a nonnegative compactly supported left Reiter density \(\rho\) of left mass one, with support \(K\), for a compact test set \(S\ni e\). The standard Reiter averaging construction is discussed by [Stokke (2004), Theorem 1.8](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=8). In the non-unimodular case right-translate \(\rho\) as a measure until \(q(h)\ge2\sup_S q\) for \(h\in K\cup SK\); this preserves left Reiter defects. Choose a nonnegative left-normalized kernel \(k\) supported sufficiently near \(e\), with \(\|k\|_R\le2\). With \(f_h=\delta_h*k\) and \(g_h=k*\delta_{h^{-1}}\), we have \(\|f_h\|_L=\|g_h\|_L=1\) and \(\|g_h*\delta_s\|_R=q(s)\|k\|_R/q(h)\le1\) on the test sets. In the unimodular case both norms agree and no translation is needed. Thus \(\|b_i[g_h*\delta_s]\|_I\le2\); the first-factor left-action bound of four gives
\[
\xi_{P,\rho,k}=\int \rho(h)\sum_i a_i[f_h]D(b_i[g_h])\,d\lambda(h),
\qquad
\|\xi_{P,\rho,k}\|\le8\|D\|.
\]
For \(x=e_{ab}[\varphi]\) supported in the group direction in \(S\), the derivation identity and \(h\mapsto sh\) give
\[
\|x\xi_{P,\rho,k}-\xi_{P,\rho,k}x-P[j]D(x)\|
 \le8\|D\|\int |\varphi(s)|\,\|\delta_s*\rho-\rho\|_L\,d\lambda(s),
\quad j=\int\rho(h)f_h*g_h\,d\lambda(h).
\]
After selecting \(\rho\), shrink the support of \(k\) so that \(h(\operatorname{supp}k)^2h^{-1}\) lies in a prescribed identity neighborhood uniformly over \(K\). Then \(j\) forms an approximate identity in both norms. Take weak-star cluster points first at a fixed corner, then over corners, using \(P[\delta_e]aP[\delta_e]\to a\) and essentiality to pass multiplier limits to the predual. This gives an implementer of norm at most \(8\|D\|\).

For a **one-point base** with mass normalized to one and non-unimodular \(G\), the conclusion fails even for an amenable \(G\). The character \(\chi(f)=\int f\sqrt q\,d\lambda\) is contractive by Cauchy–Schwarz. The functional \(d(f)=\int f\sqrt q\log q\,d\lambda\) is bounded in the raw \(I\)-norm since \(\sqrt q|\log q|\le C(1+q)\). The character identity for \(q\) and the logarithm product rule give \(d(f*g)=\chi(f)d(g)+d(f)\chi(g)\). This is a nonzero derivation into the symmetric scalar bimodule defined by \(\chi\), which is essential and satisfies type (M), but all its inner derivations vanish. The two-point argument above does not identify the raw \(I\)-algebra with the usual left-Haar \(L^1(G)\).

## Detecting nonamenable constant isotropy with a single derivation

The converse holds without a restriction on the number of points and, for the construction below, without atomicity: let \(X\) be nonempty compact Hausdorff with a full-support finite Radon measure and \(G\) locally compact Hausdorff. Normalize \(\mu(X)=1\) (rescale kernels if necessary). If \(G\) is nonamenable, there is a non-inner derivation of norm at most two for the raw \(I\)-algebra of \(X\times G\times X\), into the dual of an essential contractive bimodule satisfying right \(C(X)\)-type (M).

Let \(F\) be the bounded continuous functions \(w\) on \(G\) for which \(g\mapsto w(g\,\cdot)\) is continuous in sup norm; let \(V=F/\mathbb C1\), \(b(g)=\delta_g-\delta_e\) in \(V^*\). The right action \((w\cdot g)(t)=w(gt)\) gives \(b(gh)=g\cdot b(h)+b(g)\). Use
\[
 E=C(X)\widehat\otimes_\pi L^1(X,\mu;V)
\]
with \(A\) acting on the first factor from the left by the integrated kernel and on the second from the right by convolution with the \(V\)-action. Precisely,
\[
 (ap)(x)=\int a(x,g,y)p(y)\,d\lambda(g)d\mu(y),
 \quad
 (\eta a)(y)=\int a(x,g,y)(\eta(x)\cdot g)\,d\lambda(g)d\mu(x).
\]
Both action norms are bounded by the row norm. Right multiplication by positive functions from \(C(X)\) on the second factor satisfies type (M) by the \(L^1\) norm, then on \(E\) by the projective norm. On the left, the rank-one kernels \(p(x)k(g)\), where \(k\ge0\) has left mass one, send the constant function to \(p\). On the right, \(k(g)q(y)\) sends a constant \(V\)-section \(w\) to \(q(y)(w\cdot k)\); these span a dense subspace as \(k\) concentrates at the identity. Thus \(E\) is essential.

The formula
\[
 \langle D(a),p\otimes\eta\rangle
  =\int a(x,g,y)p(y)\langle b(g),\eta(x)\rangle
      \,d\mu(x)d\lambda(g)d\mu(y)
\]
extends by the row bound since \(\|b(g)\|\le2\). The cocycle rule gives the derivation identity by splitting \(b(gh)\) in the convolution integral. If \(D(a)=aT-Ta\), take the constant kernel \(J(f)(x,g,y)=f(g)\) for \(f\in C_c(G)\) and test on \(1\otimes\underline w\) for constant \(V\)-sections. With \(\xi(w)=T(1\otimes\underline w)\) this gives, weak-star,
\[
 \int f(g)\,[b(g)-g\cdot\xi+\xi]\,d\lambda(g)=0.
\]
Continuity against each \(w\) and full support of \(\lambda\) imply \(b(g)=g\cdot\xi-\xi\) for every \(g\). Thus \(\delta_e-\xi\) on \(F\) is invariant and has mass one. Its total variation, normalized, is an invariant mean (equivalently use the measure representation on the spectrum of \(F\)). This contradicts nonamenability by the locally compact invariant-mean criterion; see [Pestov and Schneider (2023 preprint / 2025 journal), §1](https://arxiv.org/pdf/2301.07828). No comparison with the ordinary amenability of the raw \(I\)-algebra is needed.

Together with the preceding written sufficiency result, for a purely atomic full-support compact base of at least two points this restricted condition is equivalent to amenability of the constant isotropy group. This is a written verification, not formalization. 

## Removing atomicity in the constant-isotropy criterion

The assumption of pure atomicity in the sufficient direction above can be dropped. For every compact Hausdorff \(X\) with at least two points and every full-support finite positive Radon measure, the right \(C(X)\)-type (M) condition for the raw \(I\)-algebra of \(X\times G\times X\) detects amenability of the locally compact group \(G\). If \(G\) is amenable, the bound \(8\|D\|\) on the implementer still holds for essential coefficients.

Use the continuous partitions and Gram correction described above. For clarity, to do this with an arbitrary Radon measure, start with a finite irredundant open cover on which the prescribed test kernels have small oscillation. Each member has a nonempty relatively exclusive open subset in the sense that \(U_i\setminus\bigcup_{j\ne i}U_j\) can be arranged to have nonempty interior: first use a finite open cover and a subordinate closed shrinking, and remove redundant members of the closed cover. Each remaining closed cell then has a private open subset contained in its associated open set. Reserve a positive-measure compact set in each of these disjoint subsets. Assign the remaining points to the open sets in order, giving a Borel partition \(S_i\subset U_i\) with positive masses. By compact inner regularity, choose disjoint compact cores \(K_i\subset S_i\) leaving total measure \(\tau\) arbitrarily small. A subordinate continuous partition \(p_i\) can be chosen with \(p_i=1\) on \(K_i\). This makes the row and weighted-column Gram errors at most \(2\tau/\min_i\int p_i\,d\mu\), which can be made arbitrarily small relative to the fixed cell masses. No hypothesis on the measure of cell boundaries is needed.

After choosing and correcting the partition, fix \(B=\max_i\|q_i\|_\infty\). If \(X\) is infinite, choose \(N>\max(1,\mu(X)B)\) disjoint nonempty open sets with disjoint closures. Some \(O\) has positive mass less than \(1/B\). Put \(u=1\) on a compact core of \(O\) of mass greater than \(2\mu(O)/3\), with \(0\le u\le1\) supported in \(O\), and \(v=u/\int u^2\,d\mu\). Then \(B\|u\|_1\le1\) and \(\|v\|_1\le3/2\). A second open set supplies disjoint cutoffs \(u',v'\) with \(\|v'\|_1\le3/2\). If \(X\) is finite, use the point partition and take \(u\) at the lightest point; then \(B\|u\|_1=1\), and another point supplies the second cutoff. The estimates for the two factors used in the averaging step remain \(2\) and \(4\), and the previous weak-star limit gives the same bound. Together with the explicit necessary-direction derivation, this proves the stated equivalence. The one-point non-unimodular exception remains. This is a written verification only.
