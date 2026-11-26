# A bounded approximate diagonal for an amenable ample groupoid

**Research note in progress (2026-11-26).** Direction 6. Written proof checked; not Lean-formalized, a paper, a preprint, or a peer-reviewed publication. No priority or sharpness claim.

Let \(\mathcal G\) be a topologically amenable Hausdorff ample groupoid, with counting Haar system. Write \(R,C\) for summation on range and source fibres, respectively, and let \(A\) be the completion of \(C_c(\mathcal G)\) in the two-sided norm \(\|f\|_I=\max(\|R|f|\|_\infty,\|C|f|\|_\infty)\). Then \(A\) has a bounded approximate diagonal of bound arbitrarily close to \(2\). This gives ordinary Banach amenability, not just innerness in a restricted class of coefficients, by [Johnson (1972)](https://doi.org/10.2307/2373751).

## Two-sided transport

First suppose \(X=\mathcal G^{(0)}\) is compact. Put \(\mathcal U=\{u\in C_c(\mathcal G)_+:Ru=1\}\), and \(T_u h=C((h\circ r)u)\). Then \(T_{a*u}=T_uT_a\). For \(w\ge0\) in \(C(X)\),
\[
 \inf_{u\in\mathcal U}\|T_uw\|_\infty
 =\sup\bigl(\{0\}\cup\{\sigma(w):\sigma\text{ invariant Radon probability on }X\}\bigr).
\]
The lower bound follows by integrating against invariant measures. For the upper bound, suppose that every \(\|T_uw\|_\infty\ge t>0\). Separating the convex set of these functions \(T_uw\) from \(\{h:\max h<t\}\) gives a positive normalized functional \(\mu\) with \(\mu(T_uw)\ge t\) for all \(u\). Positivity follows by testing the separating functional on arbitrary negative directions in the open set. On each clopen \(E\) set \(\nu(E)=\inf_u\mu(T_u1_E)\). The infima on the parts of a finite clopen partition can be optimized independently: paste finitely many kernels \(u_i\) by \(\sum_i (1_{E_i}\circ r)u_i\). Thus \(\nu\) is additive and \(0\le\nu\le\mu\), and extends to a Radon measure by the density of clopen step functions. Pasting for step functions and monotone upper and lower uniform approximations for positive continuous functions give \(\nu(h)=\inf_u\mu(T_uh)\) for \(h\ge0\). For a compact open bisection \(B\), set \(a_B=1_B+1_{X\setminus r(B)}\). It lies in \(\mathcal U\), with \(T_{a_B}1_{r(B)}=1_{s(B)}\). Taking the infimum over \(a_B*u\) gives \(\nu(r(B))\le\nu(s(B))\); use \(B^{-1}\) for the reverse. Applying this to clopen restrictions of \(B\) proves invariance. Hence \(\nu(w)\ge t\) and \(\nu(X)\le1\), proving the desired upper bound.

Given finitely many compact open bisections \(B_j\), write \(b_j=1_{B_j}-1_{r(B_j)}\). The ordinary Reiter condition gives \(f\in\mathcal U\) with \(\|R|b_j*f|\|_\infty<\delta\), for arbitrarily small \(\delta>0\). For a fixed \(M>0\) apply the transport identity to \(w=Cf+M\sum_j C|b_j*f|\). Every invariant probability integrates \(w\) to at most \(1+M n\delta\), where \(n\) is the number of tests. Given \(\varepsilon>0\), choose \(M>(1+\varepsilon)/\varepsilon\) and \(\delta\) sufficiently small, then take \(u\in\mathcal U\) with \(\|T_uw\|_\infty<1+\varepsilon\). The kernel \(p=f*u\) satisfies
\[
 Rp=1,\qquad \|p\|_I\le1+\varepsilon,\qquad \|b_j*p\|_I<\varepsilon.
\]
Indeed right convolution preserves the row mass of a nonnegative kernel; the column of \(|b_j*p|\) is bounded by \(T_uC|b_j*f|\le M^{-1}T_uw\). In particular one does not force the columns to be probabilities.

## Diagonal and norm estimate

Use the balanced projective product over \(P=C(X)\), with balancing on the middle legs. On a compact open bisection \(B\), set \(J(1_B)=1_B\otimes_P1_{B^{-1}}\). Under disjoint compact open subdivision the mixed terms vanish by the disjoint source projections, so this extends linearly to compactly supported locally constant functions.

For \(N|f|\) integer-valued, regard each arrow as having that many copies. The numbers of copies at either endpoint are bounded by \(k=N\|f\|_I\). Process the finitely many compact open bisection pieces and their copies in order. At each arrow, at most \(2k-2\) colours have been used at its two endpoints. Choose the first free colour, on a finite clopen subdivision determined by the source and range sets of previously coloured pieces. Each of \(2k-1\) colours is therefore a bisection, and contributes one tensor of norm at most \(1/N\), with the phase of \(f\) in the first leg. By approximation this proves \(\|J(f)\|\le 2\|f\|_I\) on \(A\); locally constant functions are dense on each compact support contained in finitely many bisections. The zero function needs no colouring.

Write \(\pi\) for multiplication. For \(c=1_B\), \(e=1_{r(B)}\) one has
\[
 \pi J(p)=Rp,\qquad cJ(p)-J(p)c=J((c-e)*p)c.
\]
For the second equality, on a bisection \(D\), the left-multiplied term is supported on the restriction \(r(D)\subset s(B)\) and matches \(J(c*1_D)c\); the right-multiplied term restricts \(r(D)\) to \(r(B)\) and matches \(J(e*1_D)c\). Thus the transport kernels give balanced diagonals with multiplication \(1\), norm at most \(2(1+\varepsilon)\), and arbitrarily small commutators on finitely many bisections.

For a finite clopen partition \(\mathcal P\) of \(X\), apply to the ordinary projective product the contraction
\[
  H_{\mathcal P}(a\otimes b)=\sum_{Q\in\mathcal P}a1_Q\otimes1_Qb.
\]
It is the average of simultaneous multiplication of the middle legs by the same random sign function. It preserves multiplication, commutes with the outside actions, and kills balancing differences for functions constant on partition members. By norm approximation and contractivity it converges to zero on the entire balancing kernel as the partition is refined. Lift the balanced diagonal with arbitrarily small norm loss. For each tested commutator, subtract a small lift of its balanced class; the remainder is in the kernel, and one common refinement makes all such remainders small. Applying \(H_{\mathcal P}\) gives ordinary approximate diagonals with the claimed bound.

## Noncompact unit space

Adjoin one point at infinity to the clopen unit component, leaving the topology on the nonunit arrows unchanged and adding no nonunit arrows at the new point. This gives a Hausdorff ample groupoid. For a compact test of nonunit arrows its two endpoint sets are compact in \(X\). A continuous Reiter probability field can be cut on a finite union of compact open bisections retaining mass at least \(1-\theta\) uniformly at those endpoints (choose finitely many arrows in each fibre and use compactness and continuity). Add any missing mass at units, including the new point; on the tested endpoints this changes each row by at most \(2\theta\) in \(\ell^1\). The new groupoid is topologically amenable. The same compact-support cut-and-fill also supplies the \(C_c\) Reiter densities used above when \(X\) is compact.

Given a finite test of compactly supported functions in the original algebra, take a compact open unit projection \(e\) covering all endpoints of their supports. Compress a compact-unit approximate diagonal by \(a\otimes b\mapsto ea\otimes be\); the image belongs to the original ordinary projective product, the compression is contractive, and the tested elements commute with \(e\) and satisfy \(ea=a=ae\). The compressed diagonal has multiplication \(e\) and approximates centrality on the tests. Density and the uniform bound give the claim for \(A\).

## The converse for Hausdorff étale groupoids

If the counting-Haar \(A\) is Banach amenable, then \(\mathcal G\) is topologically amenable, even without ample or compact-unit hypotheses. The implication is already obtainable by passing the bounded approximate diagonal through the contractive dense homomorphism into \(C_r^\ast(\mathcal G)\) (the norm estimate is Schur's test), applying [Connes (1978)](https://doi.org/10.1016/0022-1236(78)90088-5), and using the nuclearity criterion of [Takeishi (2014), Theorem 5.4](https://ems.press/journals/prims/articles/12617) for the trivial line bundle. Here is a direct extraction of the Reiter net in the Banach algebra.

Set \(\Theta(a\otimes b)(\eta)=a(\eta)b(\eta^{-1})\). The estimate \(\|\Theta(a\otimes b)\|_I\le\|a\|_I\|b\|_\infty\) makes \(\Theta\) contractive on the ordinary projective product, and \(R\Theta(m)=\pi(m)|_X\). Take a real cutoff \(c\) supported on an open bisection \(B\), put \(e_c=c*c^\ast\), and let \(z=\Theta(m)\). For \(\gamma\in B\), \(r(\eta)=r(\gamma)\), the pointwise formula is
\[
 \Theta(cmc^\ast-e_cm)(\eta)
   = |c(\gamma)|^2\bigl(z(\gamma^{-1}\eta)-z(\eta)\bigr).
\]
For an elementary tensor, the two weighted legs of \(cmc^\ast\) are evaluated at \(\gamma^{-1}\eta\) and its inverse \(\eta^{-1}\gamma\); density gives the stated formula. The left-hand side has \(I\)-norm at most \(\|c\|_I\|mc^\ast-c^\ast m\|_\pi\). For any compact arrow set, choose finitely many bisection cutoffs with \(c=1\) on neighbourhoods covering it. Centrality of an approximate diagonal then gives uniform row defect tending to zero on this compact set.

Take the diagonal net in \(C_c(\mathcal G)\otimes C_c(\mathcal G)\) using norm approximation, so \(z\in C_c(\mathcal G)\). With a unit cutoff equal to one on a compact set \(L\) covering the tested sources and ranges, the multiplication condition of the diagonal gives \(Rz\to1\) uniformly on \(L\). Consequently \(t=R|z|\ge1/2\) there eventually. Put \(q(\eta)=|z(\eta)|/\max(t(r(\eta)),1/2)\). It has row mass at most one everywhere and exactly one on \(L\). Absolute values do not increase row defects, and the difference of the two row masses is bounded by the same defect, so normalization multiplies the defect on tested arrows by at most four. Finally, add \(1-Rq\) at the units to make a global continuous probability field. That addition vanishes on all tested endpoints, preserving the estimate. The compact set and tolerance index a Reiter net. Compact support here is asserted for \(q\), not for the globally normalized field if \(X\) is noncompact.

Thus for Hausdorff ample groupoids topological amenability and Banach amenability of the two-sided counting completion are equivalent. The direct converse, like the forward construction, is written-checked, not Lean-formalized.
