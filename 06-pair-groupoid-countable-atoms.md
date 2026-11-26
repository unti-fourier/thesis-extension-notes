# Compact pair groupoids with countably many point atoms

**Work in progress.** Written proof checked; not a paper, Lean formalization, or priority claim.

Let \(\mu\) be a full-support Radon probability on a compact Hausdorff space \(X\), with infinitely many distinct point atoms and nonatomic part of mass \(d\). The raw \(I\)-norm completion \(A\) of continuous kernels of the pair groupoid satisfies
\[
\operatorname{AM}(A)=
\begin{cases}
d^{-1}, & d>0,\\
+\infty, & d=0.
\end{cases}
\]
In particular, an infinite purely atomic full-support measure gives a nonamenable Banach algebra even though its pair groupoid is topologically amenable. The proof permits dense atoms. The finite purely atomic case is [different](06-weighted-finite-pair-groupoid-constant.md).

## Lower bound

For a finite set \(F\) of atoms, let \(P_F\) be the finite-rank projection onto their span in \(L^2(\mu)\). With \(T_a\) the Schur representation, the map \(a\otimes b\mapsto T_aP_FT_b\) has projective-to-trace norm at most \(|F|\). If \(m\) is from a bounded approximate diagonal of bound \(C\), then its image \(S_m\) asymptotically commutes with continuous rank-one operators. The proof in the [finite-atom note](06-pair-groupoid-finite-point-atoms.md) applies to this fixed \(F\): on any finite continuous orthonormal system containing \(1\), all diagonal entries of \(S_m\) become close to its entry at \(1\), while the sum of their absolute values stays bounded by \(|F|C\). Thus \(\langle S_m1,1\rangle\to0\).

The product condition gives \(\langle T_{\pi(m)}1,1\rangle\to1\). The difference is the contribution through \(I-P_F\); its defining bilinear form is bounded by \(\mu(X\setminus F)\) by the column norm on the first factor and row norm on the second factor. Therefore \(1\le C\mu(X\setminus F)\). Exhausting the atoms gives \(1\le Cd\). Existence of a bounded approximate diagonal characterizes ordinary Banach amenability; none exists for \(d=0\).

## Upper bound when \(d>0\)

Fix finitely many test kernels and choose a finite Borel partition contained in a fine open cover as in the finite-atom note (first shrink the open sets so their closures stay in the chosen sets). Within each cell, collect *all* its atoms into one measurable set, and give this set a single label of target weight equal to its aggregate mass if positive. The resulting list of positive atomic-label weights is finite and fixed before choosing the number \(N\) of nonatomic labels. Split the nonatomic part into \(N\) pieces, each within the relative tolerance of mass \(d/N\) and subordinate to the same cover, by rounding the numbers of labels per cell. By Radon inner regularity, choose disjoint compact cores in the pieces, with total missing mass arbitrarily small compared with the minimum target weight for this fixed \(N\). No splitting of an atom is used. Closures of the positive-mass Borel pieces cover \(X\) by full support and lie in their assigned open sets.

The soft partition adjustment, exact-weight interpolation, and dimension-free detailed-balance Gram estimate in the finite-atom note use only these core masses and cover conditions, not whether an atomic label denotes a singleton. Thus the argument gives contractive transport from the weighted matrix norm and test-kernel approximations. The signed matching argument also applies unchanged, assigning \(\lfloor Na_j\rfloor\) diffuse columns to each fixed aggregate atomic-label weight \(a_j>0\), and matching the remaining columns to diffuse rows. Its projective bounds converge to \(1/d\) because \(\sum_j a_j=1-d\) and the positive \(a_j\) are fixed while \(N\) grows. The transport errors tend to zero with the partition tolerance. Directing over the tests and tolerances yields the upper bound. In particular there is no estimate comparing the mass left out of a finite set of *points* to the smallest retained point mass; only compact cores of finitely many Borel sets are needed.
