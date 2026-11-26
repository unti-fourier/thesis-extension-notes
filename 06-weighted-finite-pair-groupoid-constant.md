# The amenability constant of a weighted two-point pair groupoid

**Work in progress.** This is a written-checked research note, not a paper, a Lean formalization, or a priority claim.

Let \(p_1\ge p_2>0\) be the weights of a two-point pair groupoid. The ordinary Banach amenability constant for its raw \(I\)-norm convolution algebra is
\[
\mathrm{AM}(A)=\frac{p_1+p_2}{2p_2}.
\]
In particular, even compact pair groupoids need not have contractive approximate diagonals. This contrasts with the nonatomic case of the [continuous partition construction](06-pair-groupoid-raw-i-amenability.md).

## Weighted matrix norm

For a kernel \(k\), write \(a_{ij}=p_j k(i,j)\). Convolution becomes ordinary matrix multiplication, and the norm becomes
\[
\|a\|_w=\max\left(\max_i\sum_j |a_{ij}|,\ \max_j p_j^{-1}\sum_i p_i|a_{ij}|\right).
\]
The optimum over bounded approximate diagonals equals the minimum over exact diagonals by finite-dimensional compactness.

## Two-point optimum

Let \(r=p_1/p_2\). Conjugate the signed permutation group by \(P\mapsto W^{-1/2} P W^{1/2}\), where \(W=\operatorname{diag}(p_1,p_2)\). Averaging \(U\otimes U^{-1}\) gives the usual matrix diagonal \(\frac12\sum_{i,j}E_{ij}\otimes E_{ji}\): conjugation preserves it. Each diagonal signed permutation contributes projective cost one; each conjugated swap and its inverse have norm \(\sqrt r\), giving cost \(r\). Thus the projective norm of this diagonal is at most \((1+r)/2\).

For the reverse estimate, use the bilinear form
\[
\Phi(a,b)=a_{22}b_{22}+\tfrac{r-1}{2}a_{12}b_{21}
                         +\tfrac{r+1}{2}a_{21}b_{12}.
\]
Each contraction \(a\) obeys \(|a_{21}|\le 1-|a_{22}|\) by its second row and \(r|a_{12}|\le 1-|a_{22}|\) by its second weighted column. Consequently, for contractions \(a,b\), \(|\Phi(a,b)|\le xy+(1-x)(1-y)\le1\), where \(x=|a_{22}|\) and \(y=|b_{22}|\). The norm is exactly one by \(a=b=E_{22}\). Matching the matrix units in the centrality identities shows that every diagonal is of the form \(\sum_{i,j,k}c_{jk}E_{ij}\otimes E_{ki}\), where \(\operatorname{tr}c=1\) is the product condition. Its value under \(\Phi\) is \((1+r)/2\), proving the lower bound.

## More than two weights

On any finite base with strictly positive weights, the weighted algebra is amenable, and its constant is one exactly when the weights are all equal. For equal weights use signed permutations directly. Conversely, a norm-one diagonal lies in the convex hull of tensors \(a\otimes b\) of contractions, because that set is compact in finite dimension. The normalized real trace of \(ab\) is at most one by the row-norm bound. Since the product of the diagonal is the identity, every term with positive coefficient attains trace one. Every diagonal entry of such an \(ab\) is then one and its row norm is at most one, so \(ab=I\). Thus \(a,b\) are inverse isometries for \(\ell^\infty\), hence permutation matrices with unimodular nonzero entries. Contractivity of both in the column norm forces the permutation to preserve the weights. When at least two weights differ, for every \(j\) there is an \(i\) of different weight. The coefficient of \(E_{ij}\otimes E_{ji}\) vanishes in all the tensors in the convex combination, so the form of a diagonal gives \(c_{jj}=0\) for all \(j\), a contradiction.

No formula for larger unequally weighted finite bases or lower bound for mixed measures is asserted here. In particular, restriction of kernels to two atoms inside a larger groupoid does not preserve convolution.

For a general source on obtaining diagonals by symmetrized finite matrix averages, see [Grønbæk, Johnson and Willis (1992 preprint), Proposition 3.2](https://arxiv.org/html/math/9209211#S3).
