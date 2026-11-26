# Raw I-amenability for the product of a compact pair groupoid and a unimodular group

**Work in progress.** Written verification only; not a paper, Lean formalization, or priority claim.

Let \(X\) be nonempty compact Hausdorff with a finite full-support Radon measure, and \(H\) a unimodular locally compact group. Give the untwisted transitive groupoid \(X\times H\times X\) the product Haar system. Let \(A\) be the raw \(I\)-norm completion, and \(P\) the corresponding pair-groupoid completion on \(X\). Then
\[
\operatorname{AM}(A)=
\begin{cases}
\operatorname{AM}(P), & H\text{ amenable},\\
+\infty, & H\text{ not amenable}.
\end{cases}
\]
Here \(+\infty\) means there is no bounded approximate diagonal. In particular for infinite \(X\) and amenable \(H\), [the pair-groupoid classification](06-pair-groupoid-countable-atoms.md) gives \(\mu(X)/\mu_{\rm nonatomic}(X)\), with the infinite value if the measure is purely atomic. The finite-base conclusions are those for \(P\).

Rescale \(\mu\) to a probability; rescaling kernels by the same mass factor gives an isometric algebra isomorphism. Write \(B=L^1(H)\) with left Haar measure, also right Haar by unimodularity. For separated kernels \(a\boxtimes b\), the raw \(I\)-norm is exactly \(\|a\|_I\|b\|_1\); both endpoint estimates multiply by the same \(L^1\)-norm. Separated sums are dense, by uniform approximation on compact support with a fixed compact support enlargement in \(H\). Convolution on separated kernels is factorwise. Thus a bounded approximate diagonal of \(P\) and one of \(B\) shuffle and map into \(A\widehat\otimes_\pi A\), with projective norm at most the product of their bounds. Centrality and the approximate-identity condition follow on separated kernels, hence on \(A\) by uniform boundedness and density. If \(H\) is amenable, \(B\) has a contractive approximate diagonal by [Stokke (2004), Corollary 1.10](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=9).

Integration over \(H\) gives a contractive algebra homomorphism \(A\to P\) by unimodularity and Fubini. It is onto: \(\|a\boxtimes u\|_I=\|a\|_I\) for a nonnegative \(u\in C_c(H)\) of integral one, so this section extends to all \(a\in P\). Consequently an approximate diagonal for \(A\) descends to one for \(P\) with no increase in its bound.

To detect amenability of \(H\), use the algebra map \(j:B\to A\) given by kernels constant at the endpoints, \(j(b)(x,h,y)=b(h)\). This is a homomorphism since \(\mu(X)=1\). A contractive map \(R:A\widehat\otimes_\pi A\to B\widehat\otimes_\pi B\) on elementary continuous kernels is
\[
R(F\otimes G)=\int_X
  \left(\int_X F(x,\cdot,y)\,d\mu(x)\right)
  \otimes
  \left(\int_X G(y,\cdot,z)\,d\mu(z)\right)\,d\mu(y).
\]
The column bound for \(F\) and the row bound for \(G\) bound its projective norm. Fubini and \(\mu(X)=1\) show that \(R\) intertwines the two outer actions of \(B\) through \(j\). If \(E:A\to B\) integrates both endpoints, then \(\pi_B R=E\pi_A\), \(E j=\mathrm{id}_B\), and \(E\) is a contractive \(B\)-bimodule map for these actions. Applying \(R\) to any bounded approximate diagonal of \(A\) yields one of \(B\) by testing against \(j(b)\); hence \(H\) must be amenable by Stokke's same corollary.

This proof does not treat a nonunimodular isotropy group (its column uses right Haar and its row uses left Haar) or a nonsplit transitive groupoid (the displayed argument uses a global group coordinate).
