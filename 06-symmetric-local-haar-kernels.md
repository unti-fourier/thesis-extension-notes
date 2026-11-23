# Symmetric local probability kernels for a Haar groupoid

**Work in progress, 24 November 2026.** This is a supporting research note, not a submitted or peer-reviewed paper. No priority claim is made.

Let \(G\) be a locally compact Hausdorff groupoid with nonempty compact unit space \(X\) and a continuous left Haar system \((\lambda^x)_{x\in X}\) of full support on the range fibres. For a real \(f\in C_c(G)\), write \(f^\vee(\gamma)=f(\gamma^{-1})\), \(Rf(x)=\int f\,d\lambda^x\), and \(Sf=R(f^\vee)\).

**Claim.** For every open neighbourhood \(U\) of \(X\) in \(G\), there is a nonnegative \(q\in C_c(G)\) supported in \(U\) such that \(q=q^\vee\) and \(Rq=Sq=1\). The construction does not use properness or amenability.

Choose a neighbourhood \(V\) of \(X\) with \(VV^{-1}\subset U\), with products taken only for pairs of common source. To see that such a \(V\) exists, start in a relatively compact neighbourhood of \(X\). If every smaller neighbourhood contained a bad pair, a subnet of these pairs would converge to two units with the same source, hence to the same unit. Their products would converge to that unit, contradicting closedness of \(G\setminus U\).

Choose a nonnegative \(h\in C_c(G)\), supported in \(V\) and strictly positive at all units. This is possible by compactness of \(X\) and local bump functions. Full fibre support gives \(Rh>0\); Haar continuity gives a continuous \(Rh\). Replace \(h\) by \(f=h/(Rh\circ r)\), so \(Rf=1\). Put \(m=Sf\), which is continuous and strictly positive for the same reasons.

Define
$$
b(\eta)=\frac{f(\eta)}{\sqrt{m(s\eta)}},\qquad q=b*b^\vee .
$$
The usual groupoid convolution and involution give \(q\in C_c(G)\), \(q^\vee=q\), and support in \((\operatorname{supp}b)(\operatorname{supp}b)^{-1}\subset V V^{-1}\). Nonnegativity holds pointwise. Further, \(R(b^\vee)=\sqrt m\), since the denominator in \(b^\vee\) is constant on each range fibre. Left invariance and Fubini give
$$
Rq(x)=\int_{r^{-1}(x)} b(\eta)\,R(b^\vee)(s\eta)\,d\lambda^x(\eta)
=\int_{r^{-1}(x)} f(\eta)\,d\lambda^x(\eta)=1 .
$$
Symmetry now gives \(Sq=1\). The same construction cannot give a single compactly supported kernel of global range mass one for noncompact \(X\), since the range of a compact support is compact.

**Pair groupoid.** For \(G=X\times X\) with a full-support Radon probability \(\mu\) on the second coordinate, one can also use \(K(x,y)=\sum_j\varphi_j(x)\varphi_j(y)/\int\varphi_j\,d\mu\). Take a finite nonnegative partition of unity subordinate to a cover with each support square contained in \(U\) and omit identically zero terms. The kernel is symmetric and integrating in either variable returns the partition sum.

**Approximate identities.** Direct the neighbourhoods of \(X\) by reverse inclusion and choose \(q_U\) as above. The same net is a norm-one two-sided approximate identity for both the range and the \(I\)-norm completions of \(C_c(G)\), where \(\|f\|_I=\max(\|R|f|\|_\infty,\|S|f|\|_\infty)\). For a fixed \(f\in C_c(G)\), the two convolution errors have support in one compact set \(T\) once the neighbourhoods are small. In the left convolution formula subtract \(f(\gamma)\) using \(R q_U=1\); in the right formula change variables by inversion and left translation, then subtract it using \(S q_U=1\). Compactness of the composable pairs with the first arrow near the units gives uniform smallness of \(f(\eta^{-1}\gamma)-f(\gamma)\) and \(f(\gamma\eta^{-1})-f(\gamma)\) on the corresponding supports. Choose a nonnegative \(\chi\in C_c(G)\) equal to one on \(T\cup T^{-1}\). The uniform bound \(\|h\|_I\le\|R\chi\|_\infty\|h\|_\infty\) for \(h\) supported in \(T\) gives convergence on \(C_c(G)\); density and submultiplicativity extend it to the completions. Lean 4.27 checks the convergence on \(C_c(G)\) for a net with the stated masses and shrinking support. Choosing the net from the existence theorem and passing to the completions were checked in writing.

**Verification and scope.** The pair-groupoid formula and the general compact-unit existence theorem stated here were checked in Lean 4.27, with no second-countability assumption. This includes supplying the normalized input, continuity of convolution, and both mass and support conclusions. This note proves no amenability characterization. For the standard Haar convolution algebra, see [Renault (1980), Chapter II, §1](https://doi.org/10.1007/BFb0091072) and [Williams (2019), Propositions 1.33–1.34](https://www.ams.org/bookpages/surv-241).
