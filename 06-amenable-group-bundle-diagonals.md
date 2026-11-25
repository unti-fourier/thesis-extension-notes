# Norm-one Banach amenability for \(L^1\) group bundles

**Work in progress.** This is a research note toward a possible future paper, not a submission, preprint, or peer-reviewed publication. The proof below has been checked in writing, not in Lean. No priority claim is made.

Let \(p:K\to X\) be a second-countable locally compact Hausdorff group bundle with nonempty unit space and a full continuous left Haar system \((\lambda_x)\). Define the Banach algebra \(B\) by completing \(C_c(K)\), with fiberwise convolution, in
\[
\|b\|=\sup_{x\in X}\|b_x\|_{L^1(K_x,\lambda_x)} .
\]
Then \(B\) is Banach amenable exactly when every group \(K_x=p^{-1}(x)\) is amenable. In the affirmative case it has an approximate diagonal of norm at most one in the ordinary Banach projective tensor product. Its amenability constant is one. Neither local triviality, properness of \(p\), nor finite Haar mass is required.

## The evaluation quotients

For \(b\in C_c(K)\), the function \(x\mapsto\|b_x\|_1\) belongs to \(C_c(X)\) by continuity of the Haar system, applied to \(|b|\). Uniform approximation shows the corresponding function belongs to \(C_0(X)\) for all \(b\in B\). Pointwise multiplication by \(C_0(X)\) acts by central multipliers and is nondegenerate. The evaluation \(q_x:B\to L^1(K_x,\lambda_x)\) has dense image: every compactly supported continuous function on the closed fiber extends to one on \(K\), by Tietze extension followed by a compactly supported cutoff equal to one on its support. For \(b\in B\), multiplying by a positive base cutoff of norm one equal to one at \(x\) preserves \(q_xb\), and by shrinking the support one can make the resulting norm at most \(\|q_xb\|+\varepsilon\). Thus the induced map out of \(B/\ker q_x\) is isometric and has complete, dense image, so \(q_x\) is a metric quotient. The same norm continuity, with cutoffs vanishing in a neighborhood of \(x\), gives \(\ker q_x=\overline{C_0(X\setminus\{x\})B}\). Here functions on the open complement act by zero extension.

## Construct a diagonal in the balanced quotient

Let \(T=B\widehat\otimes_\pi B\), let \(N\) be the closed linear span of \(\phi b\otimes c-b\otimes \phi c\), for \(\phi\in C_0(X)\), and let \(P=T/N\). The multiplication \(\Pi:T\to B\) factors through \(P\). By the pointwise supremum norm, \(B\) is locally \(C_0(X)\)-convex. Apply [Paravicini (2008), Theorem 1.2 and Propositions 1.4–1.5](https://www.uni-muenster.de/FB10/mjm/vol_1/mjm_vol_1_10.pdf): \(P\) has norm equal to the supremum of its fiber norms, its fiber at \(x\) is \(L^1(K_x)\widehat\otimes_\pi L^1(K_x)\), and the norm of any section of \(P\) is upper semicontinuous as a function of the base point. This is a statement about the **quotient** norm, not the norm on \(T\). For example, for two trivial groups over two points, the tensor from distinct point idempotents has projective norm one and vanishes in \(P\).

Assume every \(K_x\) is amenable. Fix \(F\subset C_c(K)\) finite and \(\varepsilon>0\), and let \(L\subset X\) be the union of the images of their compact supports. For each \(x\in L\), [Stokke (2004), Corollary 1.10](https://www.impan.pl/shop/en/publication/transaction/download/product/90526) gives a tensor in the fiber of norm at most one for which the commutator and multiplication errors at \(q_x(F)\) are less than \(\varepsilon\). Lift it to an element of \(P\) using the fiber quotient. By upper semicontinuity, there is an open neighborhood \(U_x\) where the lift has fiber norm less than \(1+\varepsilon\) and all the commutator errors are less than \(\varepsilon\). By continuity of the fiber norms in \(B\), shrink \(U_x\) to obtain the same bound on the multiplication errors. Use a finite subcover and nonnegative functions \(\phi_j\in C_c(U_{x_j})\) with \(\sum_j\phi_j=1\) on \(L\) and \(\sum_j\phi_j\leq1\) everywhere. The weighted sum \(\bar d\in P\) of the local lifts has norm at most \(1+\varepsilon\), commutators with \(F\) of norm at most \(\varepsilon\), and \(\|\Pi(\bar d)a-a\|\leq\varepsilon\) for \(a\in F\). Outside \(L\) each \(a_x\) is zero, so the multiplication estimate does not require the cutoffs to sum to one there.

## Lift the estimates to the ordinary tensor product

Choose \(d\in T\) lifting \(\bar d\) with \(\|d\|\leq1+2\varepsilon\). For \(|u|=1\) in the unitization \(C_0(X)+\mathbb C1\), define the isometry \(S_u(b\otimes c)=ub\otimes\bar u c\). It commutes with both outer \(B\)-actions, and \(\Pi S_u=\Pi\). The closed span of the ranges of \(S_u-I\) is exactly \(N\). Indeed, differences from \(S_u-I\) are balancing differences, since constant terms in \(u\) cancel. Conversely, each scalar multiplier is a finite linear combination of unitaries in that unitization (write each self-adjoint contraction as \((u+\bar u)/2\)), and
\[
(S_u-I)(b\otimes uc)=ub\otimes c-b\otimes uc.
\]

Each \([a,d]\), \(a\in F\), differs by less than \(2\varepsilon\) from an element of \(N\). Approximate those finitely many elements of \(N\) by finite sums of differences, involving a common list \(u_1,\ldots,u_s\). The operators \(S_u\) commute, so the contractive average
\[
R_n=\prod_{j=1}^{s}\left(\frac1n\sum_{k=0}^{n-1}S_{u_j}^{\,k}\right)
\]
satisfies \(\|R_n(S_{u_j}-I)\|\leq2/n\) for each \(j\), by telescoping. Taking sufficiently large \(n\) gives commutators of \(R_nd\) with \(F\) arbitrarily close to the original quotient error bound, now measured in the ordinary projective norm. Multiplication is unchanged and the norm is at most \(1+2\varepsilon\). Normalize by \(1+2\varepsilon\) and direct the choices by finite tests and error tolerances to obtain the claimed norm-one approximate diagonal. Uniform boundedness and density extend the estimates to every \(a\in B\). Nonzero test elements and the contractivity of \(\Pi\) imply the lower bound one. Conversely, an approximate diagonal passes to each evaluation quotient, so the same corollary of Stokke forces every \(K_x\) to be amenable.

In a groupoid extension, this settles innerness of the restriction of a derivation to a kernel subalgebra of this form, when that algebra is represented in the ambient algebra with the stated fiber norm. No geometric condition on the coefficient is needed for that restriction. It does not by itself settle the full derivation criterion for arbitrary ambient groupoids or remove local lifts in the forward implication.
