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
