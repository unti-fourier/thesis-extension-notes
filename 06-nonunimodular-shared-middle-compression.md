# The shared-middle compression fails in the nonunimodular raw I-norm

**Work in progress.** Written proof checked; not a paper, Lean formalization, or priority claim.

Take the untwisted product \(X\times H\times X\), where \(X\) is compact Hausdorff with a full-support Radon probability and \(H\) is locally compact. Write \(\lambda_L,\lambda_R\) for left Haar and its image under inversion, and \(q=d\lambda_R/d\lambda_L\). The raw \(I\)-norm uses \(\lambda_L\) in rows and \(\lambda_R\) in columns. Let \(A\) denote the completion; let \(B=L^1(\lambda_L)\cap L^1(\lambda_R)\) with the maximum norm and left-Haar convolution.

**The group corner.** The constant endpoint kernel with group coordinate \(\delta_e\) defines a norm-one idempotent multiplier; its actions on \(A\) average, respectively, the range or source endpoint. It gives the corner of kernels constant in the endpoints, isometric to \(B\). When \(H\) is nondiscrete this multiplier need not be in \(A\). The linear retraction averaging both endpoints is contractive, but need not be multiplicative.

**The obstruction.** The natural shared-middle map on continuous elementary tensors is
\[
\mathcal R(F\otimes G)=\int_X
  \left(\int_X F(x,\cdot,y)\,d\mu(x)\right)
  \otimes
  \left(\int_X G(y,\cdot,z)\,d\mu(z)\right)\,d\mu(y).
\]
This retains the product identity of the [unimodular argument](06-product-pair-unimodular-group.md). If \(X\) is infinite and \(H\) is nonunimodular it is unbounded into \(B\widehat\otimes_\pi B\). Indeed, arbitrarily small positive open-set masses are available by full support and disjoint neighborhoods. By inner regularity and continuous cutoffs one obtains \(0\le v\le1\) with \(s=\int v>0\) arbitrarily small and \(\int v^2\ge s/2\). Nontriviality of the positive character \(q\) gives nonnegative continuous compactly supported \(f,g\) such that
\[
\|f\|_L=\|g\|_R=1,\qquad \|f\|_R,\ \|g\|_L\le s
\]
(by choosing the supports where \(q<s\) and \(q>1/s\)). Put \(F(x,h,y)=v(y)f(h)/s\) and \(G(y,h,z)=v(y)g(h)/s\). Both have raw \(I\)-norm one. Their image is \((\int v^2/s^2)f\otimes g\), of projective norm at least \(1/(2s)\).

**Two remaining implications.** For a finite base, each pair-algebra entry has both of its group norms controlled by a reciprocal point mass, so \(\mathcal R\) into \(B\widehat\otimes_\pi B\) is bounded. The product and bimodule identities transfer any bounded approximate diagonal to \(B\). Nonunimodular \(H\) make \(B\) nonamenable: the character \(f\mapsto\int f\sqrt q\,d\lambda_L\) admits the nonzero bounded point derivation \(f\mapsto\int f\sqrt q\log q\,d\lambda_L\). Boundedness follows from \(\sqrt q\,|\log q|\le C(1+q)\), and the derivation identity follows from multiplicativity of \(q\). A point derivation into a symmetric scalar module cannot be inner unless it is zero.

For any such base, the same \(\mathcal R\) with target \(L^1(\lambda_L)\widehat\otimes_\pi L^1(\lambda_L)\) is contractive: bound the second interior factor by the uniform left row bound and integrate the first in both endpoints using that same left row bound. For \(b\in B\), multiplication through the constant-endpoint \(b\) gives the required module identities, and \(B\) is dense in ordinary left-Haar \(L^1\). The endpoint integration of the product is also contractive into left-Haar \(L^1\). Thus an approximate diagonal for \(A\) descends to one for ordinary \(L^1(H)\), and \(H\) must be amenable by [Stokke (2004), Corollary 1.10](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=9).

Unboundedness of \(\mathcal R\) into the raw group norm does not by itself decide ambient amenability on any infinite base.
