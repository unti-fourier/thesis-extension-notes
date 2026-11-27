# The absolute Hochschild comparison in every finite degree

**Work in progress.** A research note, not a paper, preprint, peer-reviewed publication, or priority claim.

**Verification status (2026-11-27).** The all-degree split injection and quotient-seminorm equality were checked in Lean 4.27.0 for the **row completion with anchored coefficients**: the predual is a separable Bochner space with a strongly continuous isometric action and covariant multiplication along the measurable anchor. The Bochner-algebra variant and the counterexample to strict retraction below are checked in writing only.

The [degree-two comparison](02-locally-compact-absolute-hh2-split-injection.md), with its precise coefficient hypotheses and norms, extends to every finite degree \(n\ge0\):
\[
 H_{\rm cb}^n(G;W)\ \longrightarrow\
 HH_{\rm cont}^n(A,\mathcal B(C(X),W)).
\]
The arrow is contractively split on cohomology and preserves the quotient seminorm. Here \(G\) is locally compact second countable and \(W=V^*\) is the dual of a separable strongly continuous isometric representation. For Bochner \(A\) use the unital contractive weak-star continuous covariant representation \(\pi\) of \(C(X)\) on \(W\). For row \(A\) use the measurable equivariant anchor and multiplication action of the degree-two note. There is no unimodularity assumption.

### Map and retraction on the Haar cochain complexes

Write \(t_j=s_1\cdots s_j\), \(t_0=e\). For bounded weak-star measurable inhomogeneous group kernels \(c\), set
\[
 \Phi_n(c)(a_1,\ldots,a_n)(p)
 =\int_{G^n}^{w^*}
 \pi\!\left(\left[\prod_{j=1}^n\alpha_{t_{j-1}}(a_j(s_j))\right]\alpha_{t_n}(p)\right)c(\mathbf s)\,d\mathbf s .
\]
In degree zero this reads \((\Phi_0(w))(p)=\pi(p)w\). Work on compactly supported continuous coefficients first. Scalar Fubini after pairing with the predual is legitimate by the integrated Bochner norm bound. In the row case the pointwise estimate integrates over the group variables in reverse order; the last coefficient is evaluated at \(t_{n-1}^{-1}x\), so its integral is bounded by its row norm regardless of earlier variables, and iteration gives the product of row norms. This proves contractivity for all \(n\).

In the Hochschild differential each term has the same total coefficient \(\prod_{j=1}^{n+1}\alpha_{t_{j-1}}(a_j(s_j))\,\alpha_{t_{n+1}}(p)\). The leading term applies \(U_{s_1}\) to the group kernel by covariance. Each internal term merges \(s_j,s_{j+1}\) by the left Haar substitution \(u=s_js_{j+1}\); it introduces no modular factor. The last term acts on \(p\) by the integrated right module action and drops the final group variable from \(c\). Thus the alternating sum gives \(\partial_{\mathrm{HH}}\Phi_n=\Phi_{n+1}d_G\), including degree zero.

For an arbitrary absolute Hochschild cochain \(B_n\), restrict each input to \(i(f)(s)=f(s)1_X\) and evaluate the output at \(1_X\). This is a contractive cochain map into the \(L^1(G)\) complex with the integrated left action and augmentation on the right, because evaluation is a bimodule map after this restriction. Multilinear integration is the isometric identification \(J_n\) of that complex with the weak-star measurable Haar kernel complex: use \(L^1(G^n;V)^*=L^\infty_{w^*}(G^n,W)\), with the separable predual as in the earlier note. The two constructions satisfy \(\mathcal R_n\Phi_n=J_n\) exactly. Therefore \(J_n^{-1}\mathcal R_n\) is a contractive left inverse on measurable cochains. In particular, the seminorm lower bound applies against every absolute Hochschild coboundary, not only those initially in the image.

### Continuous cochains versus measurable cochains

To recover a continuous homogeneous cochain, first homogenize the Haar kernel, then average each vertex \(x_j\) independently against a fixed translated probability bump \(p_0(x_j^{-1}y_j)\,dy_j\), \(p_0\in C_c(G)_+\). This is equivariant and commutes with alternating vertex deletion since each bump has mass one. It is contractive, and its values are norm continuous by \(L^1\)-continuity of translation of the bump. For continuous inputs the standard prism homotopy connects this smoothing to the identity: in degree \(n\), sum the \(n\) terms with sign \((-1)^i\), evaluating the input at \((x_0,\ldots,x_i,y_i,\ldots,y_{n-1})\) and integrating the \(y\)'s independently against their translated bumps. Alternating deletion telescopes to smoothing minus identity. The homotopy has norm at most \(n\) in degree \(n\). Thus after converting back to continuous cochains the splitting holds on cohomology. This uses the homogeneous resolution of [Burger and Monod (2002), Theorem 2](https://people.math.ethz.ch/~burger/pub/2002_Continuous_bounded-cohomology.pdf#page=2), not independent smoothing of inhomogeneous increments.

An exact contractive cochain retraction into the continuous model need not exist. For \(G=\mathbb R\), a point \(X\), and real scalar trivial coefficients, degree one would retract \(L^\infty(\mathbb R)\) onto \(C_b(\mathbb R)\) with norm one. Such a unital map is positive. Testing continuous functions supported on the positive and negative sides forces the image of \(1_{(0,\infty)}\) to be one on the positive side and zero on the negative side, which is impossible by continuity. Thus the distinction between cochain splitting in the measurable model and cohomological splitting in the continuous model is essential.
