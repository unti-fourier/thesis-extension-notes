# A contractive raw I-norm diagonal for a diffuse nonunimodular product groupoid

**Work in progress.** Written verification only; not a paper, preprint, Lean formalization, or priority claim.

Let \(X\) be nonempty compact Hausdorff, with a full-support nonatomic Radon probability \(\mu\). Let \(H\) be an amenable nonunimodular locally compact Hausdorff group. For the split untwisted groupoid \(X\times H\times X\) with its product Haar system, the raw \(I\)-norm convolution completion \(A\) has a contractive approximate diagonal in \(A\widehat\otimes_\pi A\). In particular its amenability constant is one. The raw norm is the maximum of the supremum of the left-Haar row integrals and the supremum of the right-Haar column integrals. This applies to Lebesgue measure on \([0,1]\) and the real \(ax+b\) group. It does not assume clopen cells. It is not a claim about nonsplit groupoids, mixed atomic/diffuse measures, or Morita invariance of the raw norm.

Write \(\lambda\) for left Haar and \(\rho\lambda\) for right Haar (the inverse image of left Haar under inversion). In this convention \(\rho\) is a positive character. Norms of group densities are denoted \(\|\cdot\|_L,\|\cdot\|_R\).

### Continuous endpoint partitions and products

For finite compactly supported continuous test kernels, choose a finite open cover of \(X\) on which each endpoint varies by at most \(\omega\) in the maximum of the two Haar norms, uniformly in the other endpoint. Use a subordinate measurable partition with positive masses (first reserve disjoint compact positive-mass sets in the finitely many nonempty cover elements). Split each piece into equal pieces with counts obtained by rounding \(n\) times its mass, so that each resulting cell \(S_i\) satisfies \(|n\mu(S_i)-1|<\eta/3\), for large \(n\). This uses nonatomicity. Choose disjoint compact cores \(K_i\subset S_i\) losing total mass less than \(\eta/(3n)\). A subordinate continuous partition \(v_i\) can be made to agree with the cell indicators on all the cores: take disjoint continuous cutoffs equal to one on the corresponding cores, and distribute the remaining pointwise mass by any continuous subordinate partition. With \(\theta=(1+\eta)^{-1}\), set
\[
p_i=\theta v_i+1/n-\theta\int v_i\,d\mu.
\]
The added constants are nonnegative and sum to \(1-\theta\). Thus \(p\) is a continuous partition of unity with exact masses \(1/n\), \(\sum_i|p_i-v_i|\le 2(1-\theta)\) pointwise, and \(n\int p_i^2\ge \theta^2(1-\eta)\). The linear interpolant of a test kernel at representative cell points, with weights \(v_i(x)v_j(y)\), has uniform error \(2\omega\) in the maximum Haar norm. Replacing \(v\) by \(p\) costs at most \(4(1-\theta)\sup_{x,y}\|F_{xy}\|_{\max(L,R)}\). This gives raw \(I\)-norm approximation with uniform endpoint control, not just approximation in measure.

For partitions \(P,Q\) of lengths \(a,b\) with equal masses within each partition, put \(J_{P,Q}(C)=b\sum_{i,j}P_i C_{ij}Q_j\) and \(G_Q=(b\int Q_iQ_j)\). The maximum of row sums of left norms and \((b/a)\) times column sums of right norms bounds \(\|J_{P,Q}(C)\|_I\). Since \(G_Q\) is symmetric stochastic, the maximum absolute row and column sums of \(G_Q-I\) are bounded by \(g=2(1-\theta^2(1-\eta))\). For small \(\eta\), \(T_{P,Q}(C)=J_{P,Q}(CG_Q^{-1})\) therefore costs at most \((1-g)^{-1}\) and satisfies \(T_{P,Q}(C)*T_{Q,R}(D)=T_{P,R}(CD)\) exactly. The approximating interpolants above are in the range of \(T_{p,p}\).

### The weighted tensor estimate

Fix a compact rectangle for two group variables \(s,t\). The left-Haar-density pushforwards \(u\mapsto R_z u\) by \(s\mapsto sz\) and \(v\mapsto L_{z^{-1}}v\) by \(t\mapsto z^{-1}t\) preserve left norms and multiply right norms by \(\rho(z)\) and \(\rho(z)^{-1}\), respectively. They preserve the convolution product of the two legs. The first pushforward commutes with left convolution; the second commutes with right convolution. Choose \(z\) with \(\rho(z)\sup_s\rho(s)<1\), using nonunimodularity.

Use an inner partition \(\psi\) of length \(N\), with the same Gram bound. Map \(u\otimes v\) to
\[
\mathcal D(u\otimes v)=\frac1N\sum_{i=1}^{n}\sum_{j=1}^{N}
 T_{p,\psi}(E_{ij}R_z u)\otimes T_{\psi,p}(E_{ji}L_{z^{-1}}v).
\]
Write \(\mathcal D_{ab}\) for the variant with outer endpoints fixed to \(a,b\) and only the middle index summed. To estimate these maps, split the rectangle into finitely many modular bands \(\rho(s)\in[A_0,cA_0]\), \(\rho(t)\in[B_0,cB_0]\), where \(c>1\). Choose \(N\) large and then \(k=\lfloor N\rho(z)A_0/n\rfloor\), so that \(r=nk/N\) is between \(\rho(z)A_0/c\) and \(\rho(z)A_0\). Place disjoint blocks of \(k\) middle indices at the \(n\) outer indices, uniformly cycling their positions together; put an independent sign on each middle index. In the first leg put the signed density \(R_z u/k\) on the blocks, and in the second put \(L_{z^{-1}}v\) with the same signs on the transposed blocks. The expected product of coefficients is \(1/N\) exactly when both index pairs match and zero otherwise: unmatched middle indices cancel by signs, and distinct blocks are disjoint. The fixed-endpoint version uses one block and the same \(k\). Thus the average is the displayed tensor, independent of \(k\).

In the rectangular matrix norms the product of the two leg norms is bounded by
\[
\max(\|u\|_L,\rho(z)\|u\|_R/r)
 \max(\|v\|_L,r\|v\|_R/\rho(z))
 \le c^3\max(1,A_0B_0)\|u\|_L\|v\|_L .
\]
Gram correction costs at most \((1-g)^{-2}\) for the two legs. By summing on rectangle simple functions, then taking \(L^1\) limits band by band, both maps satisfy
\[
\|\mathcal T(\ell)\|_\pi
 \le (1-g)^{-2}c^3
 \int |\ell(s,t)|\max(1,\rho(st))\,d\lambda(s)d\lambda(t).
\]
On the compact rectangle, each measurable leg is approximable by continuous compactly supported group functions in both Haar norms. The tensor estimate is in the Banach projective norm, not just a pointwise kernel norm.

### Approximate diagonal

For the finite group coefficient tests \(b_0\) in the interpolant matrices, fix a compact containing their supports and the identity, and fix a compact neighborhood \(U_0\) of the identity. Choose probability densities \(f,e\) with compact support, with \(f\) nearly left invariant on the test compact and \(e\) nearly central there, supported in an arbitrarily small neighborhood \(U\subseteq U_0\) with \(\sup_U\rho\le c\). For the latter one can average the conjugates of a sufficiently small probability bump against \(f\); the compact support of \(f\) ensures all conjugates remain in \(U\), and the defect of centrality is bounded by the left Reiter defect of \(f\). As in [Stokke (2004), Theorem 1.8](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=8), \(m(s,t)=f(s)e(st)\) has left product mass one, \(\pi_H m=e\), and \(\|b_0\cdot m-m\cdot b_0\|_{L^1(\lambda^2)}\to0\).

Use one compact rectangle containing \(m\) and all the finitely many commutators, and set \(D=\mathcal D(m)\). The product identity and the two convolution compatibilities give
\[
\pi_A(D)=T_{p,p}(I_n e),\qquad
[T_{p,p}(E_{ab}b_0),D]=\mathcal D_{ab}(b_0\cdot m-m\cdot b_0).
\]
For \(m\) the product \(st\) lies in \(U\), so \(\|D\|_\pi\le (1-g)^{-2}c^4\). For the commutators \(st\) lies in the product of the fixed test compact with \(U_0\) in either order. The weight \(\max(1,\rho(st))\) is bounded by a constant independent of the Reiter support of \(f\). The same fixed compact controls the right-Haar norms of \(e*b_0-b_0\) and \(b_0*e-b_0\) by their left-Haar norms, which can be made arbitrarily small by first shrinking \(U\). Thus fix the outer partition and finite interpolants first, shrink \(U\), make the Reiter defect as small as needed, and only then choose the rectangle, \(z\), and \(N\). By density, letting \(\omega,\eta,c-1\) tend to zero yields the approximate-diagonal conditions on the whole algebra. Dividing each candidate by its displayed norm bound gives a contractive net without changing its limit properties. The lower bound one follows from \(\pi_A(D)F\to F\) for a nonzero \(F\) and contractivity of multiplication.
