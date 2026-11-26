# Exact bounded cohomology in degree one for Hausdorff étale groupoids

**Work in progress, November 2026.** A research note toward possible future papers, not a submission or peer-reviewed publication. The degree-one argument below was checked in writing, not in Lean. No priority claim is made.

Let \(G\rightrightarrows X\) be second-countable, locally compact, Hausdorff and étale. For a continuous Banach bundle \(E\) with enough local continuous sections and an isometric continuous \(G\)-action, set \(Y_0=X\), \(Y_1=G\), \(Y_2=G^{(2)}\). Write \(\rho_n\) for the range of the first arrow (the identity for \(n=0\)), \(B_n=\Gamma_0(Y_n,\rho_n^*E)\), and \(C^n=B_n^{**}\). Then
\[
 G \text{ is topologically amenable}
 \quad\Longleftrightarrow\quad H^1(C^\bullet)=0
       \text{ for every such }E
 \quad\Longleftrightarrow\quad [b]=0 .
\]
The last test uses the mass-zero bundle \(V_x=\ker(\ell^1(G^x)\to\mathbb R)\) and \(b(\gamma)=\delta_{1_{r\gamma}}-\delta_\gamma\). Here \(H^1\) takes the quotient by the actual image of the differential, not its closure. The use of the entire section space's bidual is essential to the argument; this is not a statement about continuous fiberwise primitives, or a complex defined modulo a chosen quasi-invariant measure.

## The complex

A functional \(\ell\) on a section space \(\Gamma_0(Y,F)\) is dominated by a finite positive regular measure \(\mu_\ell\) of mass \(\|\ell\|\). One constructs it from the positive functional on \(C_0(Y)\) sending \(f\ge0\) to \(\sup_{\|t(y)\|\le f(y)}|\ell(t)|\). Additivity follows by splitting \(t\) in the proportions \(f/(f+g)\), \(g/(f+g)\) and, in the reverse direction, aligning scalar phases. Thus every bounded continuous section defines an element of \(\Gamma_0(Y,F)^{**}\) by pairing with \(\ell\) using compact cutoffs; the result agrees with evaluation on the original section space. For each term \(P\) of a cochain differential, the preadjoint is \(\ell\mapsto[t\mapsto\widetilde\ell(Pt)]\), where the tilde denotes this extension. Hence
\[
 d^0v(\gamma)=v(r\gamma)-\gamma v(s\gamma),\qquad
 d^1c(\gamma,\eta)=c(\gamma)+\gamma c(\eta)-c(\gamma\eta)
\]
extend weak-star continuously. Cutting off the resulting sections identifies the extensions with the formulas on bounded continuous sections. The identity \(d^1d^0=0\) then extends by weak-star density. On a bisection, the local section space is identified by the range map with the corresponding section space over the unit space.

## Averaging

For topologically amenable \(G\), take continuous Reiter probabilities \(m_i^x\) on the range fibers. The counting Haar version can be obtained from the densities in [Renault (2015), Proposition 2.8](https://arxiv.org/html/1302.0636#S2) by adding the missing mass at \(1_x\); the added mass tends uniformly to zero on compact unit sets. Define \(A_i c(x)=\sum_h m_i^x(h)c(h)\) and \(Q_i k(\gamma)=\sum_\eta m_i^{s\gamma}(\eta)k(\gamma,\eta)\). They are contractions on the respective section spaces vanishing at infinity: continuity follows locally from the continuous compactly supported density and the unit term; for compactly supported input the output support lies in the compact range image or first-coordinate projection of the input support. General input follows by norm approximation. Expanding the identities above gives the error
\[
 (d^0 A_i+Q_i d^1-I)c(\gamma)=
 \int c(h)\,d(m_i^{r\gamma}-\gamma_*m_i^{s\gamma})(h).
\]
For any compactly supported scalar cutoff \(0\le\chi\le1\) on \(G\), the localized operator has norm at most the supremum Reiter defect on \(\operatorname{supp}\chi\). Taking second adjoints gives the same bound on \(B_1^{**}\). If \(d^1z=0\), choose a weak-star cluster point \(v\) of \(A_i^{**}z\), which have norm at most \(\|z\|\). For every \(\chi\), \(\chi(d^0v-z)=0\). Compact cutoffs exhaust the regular tests in norm, yielding \(d^0v=z\).

## Recovering topological amenability

If \(d^0v=b\) in \(B_1^{**}\) for \(v\in B_0^{**}\) with coefficients in \(V\), approximate \(v\) weak-star by a bounded net \(v_j\) from \(B_0\). For each compact arrow set \(K\), use a compactly supported cutoff \(\chi=1\) on \(K\). The actual sections \(\chi(d^0v_j-b)\in B_1\) converge weakly to zero. Convex combinations therefore yield a section \(w\in B_0\) with \(\sup_K\|d^0w-b\|<\varepsilon\). Each \(u_x=\delta_{1_x}-w_x\) has mass one. Absolute value and normalization yield continuous probabilities \(|u_x|/\|u_x\|_1\) with defect at most \(2\varepsilon\) on \(K\). Exhausting compact arrow sets gives topological amenability.

For a countable discrete group acting on a compact Hausdorff space, the cochains identify with bounded group cochains valued in \(\Gamma(X,E)^{**}\), and the mass-zero test becomes the Johnson class in [Brodzki–Niblo–Nowak–Wright (2012), Theorem B](https://arxiv.org/pdf/1004.0295#page=2). The [continuous-section version](06-continuous-bounded-cocycles.md) instead gives approximation on compact sets; exactness there can fail even for an ample groupoid.

## General continuous Haar systems and all positive degrees

The same bidual complex works for a second-countable locally compact Hausdorff groupoid \(G\) with a full continuous left Haar system. For every continuous isometric Banach bundle \(E\) as above, use the same \(B_n\) on composable \(n\)-tuples for all \(n\ge0\). Topological amenability implies \(H^n(C^\bullet)=0\) for every \(n\ge1\), with a primitive of norm at most the cocycle norm. Conversely, the first class for the mass-zero \(L^1\) bundle already detects topological amenability.

To see the forward implication, use continuous Reiter probabilities \(m_i^x\) and the operator \(A_i^n\) integrating a final arrow against \(m_i^{s\gamma_{n-1}}\) (against \(m_i^x\) when \(n=1\)). On compactly supported input the support of the output lies in the compact projection of the input support, by dropping the last coordinate, or by taking range if \(n=1\). For continuity, over a neighborhood of any tuple integrate with a local compact cutoff in the last variable, approximate the integrand on the compact set of composable tuples by sums of scalar functions times local bundle sections, and use continuity of the measure field for the scalar integrals. A cutoff can capture all but arbitrarily small mass uniformly on compact unit sets: choose such a cutoff locally at each unit by regularity and continuity, then take a finite subcover. This also shows that the second adjoint agrees with averaging on bounded continuous sections, by cutting off a bounded input and testing on a compact subset of the shorter tuple space. In particular \(A_i^n:B_n\to B_{n-1}\) is contractive.

Retain \(d^0\) above, and use the standard inhomogeneous differential (first arrow acts, neighboring arrows compose with alternating signs, last arrow is dropped) in positive degrees. Take \(H_i^1=(A_i^1)^{**}\), and \(H_i^n=(-1)^n(A_i^n)^{**}\) for \(n\ge2\). The inserted last arrow's own deletion gives \(+c\). All earlier faces cancel except the pair that either combines \(\gamma_n\) and the inserted arrow or drops \(\gamma_n\) before averaging. On actual sections their difference is
\[
 \big((d^{n-1}H_i^n+H_i^{n+1}d^n-I)c\big)(\gamma_1,\ldots,\gamma_n)
 =
 \int c(\gamma_1,\ldots,\gamma_{n-1},h)\,
      d\big(m_i^{r\gamma_n}-(\gamma_n)_*m_i^{s\gamma_n}\big)(h).
\]
After any compact cutoff of norm at most \(1\), the norm bound is the supremum of the Reiter defect on the last-coordinate projection of its support, with no factor depending on the degree. The localized operator is the second adjoint of its restriction to actual \(C_0\) sections. As above, take a weak-star cluster point of \(H_i^n z\) and use norm approximation of regular tests by compact cutoffs to obtain the asserted exact primitive.

For the converse, use the Haar \(L^1\) bundle of range fibers, defined by row restrictions of \(C_c(G)\), and its mass-zero subbundle. Full Haar support gives positive local \(C_c(G)\) test functions with nonzero row integral near each unit. Normalize them locally and patch by a locally finite partition of unity to get a continuous probability section \(p\), and use \(b_p(\gamma)=p_{r\gamma}-\gamma p_{s\gamma}\). The same localized Goldstine and convexity argument gives Reiter probabilities, replacing the unit Dirac by \(p\). The class is independent of \(p\) by the coboundary formula for the difference of two choices.

[Terra (2010 thesis, 2011 preprint), Theorem 0.2](https://arxiv.org/pdf/1103.2439#page=7) gives a related locally compact transformation-group criterion using group bounded cohomology with dual type (M) coefficients. [Sarti–Savini (2023 preprint, revised 2025), Theorem 4](https://arxiv.org/html/2304.07765) is a vanishing implication for measured groupoids with measurable coefficients. The regular section tests used here are not tied to a measure class. No general comparison isomorphism with those complexes, formalization, or priority claim is asserted.

## Pullbacks and Morita equivalence

This complex is not limited to amenable groupoids. Let \(q:Z\to X\) be a continuous open surjection between second-countable locally compact Hausdorff spaces. The pullback groupoid has arrows \((z,g,z')\) with \(qz=r(g)\), \(qz'=s(g)\). For the pullback coefficient bundle, the forgetful map induces an isometric isomorphism in every degree (for the quotient seminorm on ordinary cohomology, and the norm on reduced cohomology).

To prove this, fix a continuous probability system \(\kappa^x\) supported on the fibers of \(q\). It exists by [Blanchard's lemma as stated in Williams (2016), Lemma 2.3](https://arxiv.org/pdf/1501.04077#page=3): start from the full Radon system, normalize positive compactly supported tests locally, and patch by a partition of unity on \(X\). Denote the pullback on cochains by \(P\), and define \(T\) by lifting every vertex \(x_j\) of a composable simplex independently with \(\kappa^{x_j}\) and averaging the lifted cochain. These maps are contractions. Deleting a vertex integrates out one probability, so \(T\) commutes with the differential and \(TP=I\).

The composite \(PT\) is homotopic to the identity. For an original simplex with lifted vertices \(z_0,\ldots,z_m\), first sample \(w_0,\ldots,w_m\) independently over the corresponding base vertices. Insert the prism term with lifted vertices
\[
 (z_0,\ldots,z_j,w_j,\ldots,w_m)
 \qquad (0\le j\le m)
\]
at sign \((-1)^j\), using the arrow over the unit between \(z_j,w_j\), then average. Adjacent arrows incident with a sampled vertex share that sample. In standard bar signs the interior faces cancel and the two end faces give \(dK+Kd=PT-I\); for the convention on \(d^0\) above reverse the sign of \(K^1\). The bound is \(\|K^{m+1}\|\le m+1\).

These operators need not preserve \(C_0\). They do act on bounded continuous sections and preserve uniformly bounded convergence on each compact set: on any compact parameter set the sampling probabilities are uniformly tight, so finitely many sampled coordinates can be confined to compact sets with arbitrarily small error. Product integration there preserves continuity by approximation by sums of products of scalar test functions and local bundle sections. Thus, for \(S=P,T,K\), its preadjoint is obtained by evaluating a regular test against \(St\) using output cutoffs for \(t\in C_0\). Bounded compact-open convergence shows that the weak-star extension agrees with the original formulas on bounded continuous sections. The two cochain identities extend by weak-star density. On cohomology the contractions \(P,T\) are mutual inverses, proving isometry and independence of the chosen sampling system.

For a second-countable locally compact Hausdorff principal equivalence bibundle \(W\) with open anchors \(a,b\), apply the result to both anchors. The groupoids \(a^*G\) and \(b^*H\) are isomorphic: the arrow over \(g\) with endpoints \(w_0,w_1\) corresponds to the unique \(h\) with \(w_0h=gw_1\). Thus the bidual cohomology groups are naturally isometric for coefficients identified isometrically on these pullbacks, including trivial coefficients. A related transfer for differentiable cohomology with surjective submersions is [Brahic (2026), Theorem 5.2.2](https://arxiv.org/pdf/2611.21212#page=14). The present argument uses regular tests and compares seminorms; it is checked in writing, not in Lean, and no priority claim is made.

## Comparison for a single locally compact group

For a second-countable locally compact group \(G\) and trivial real coefficients, the natural integration map from the usual bounded continuous cochains to \(M(G^n)^*\) induces an isometry on cohomology, both before and after reduction. Here \(M\) denotes the finite signed Radon measures, so \(M(G^n)^*=C_0(G^n)^{**}\).

Restriction \(R\) to the Haar-absolutely-continuous measures gives the \(L^\infty(\lambda^n)\) cochain complex. It is a contractive cochain map: face maps preserve absolute continuity of the pushed-forward measures, by Fubini and translation of a Haar coordinate. Fix a probability \(\mu=\rho\lambda\) with continuous compactly supported density. In homogeneous coordinates smooth a Haar cochain by replacing every vertex \(x_i\) by \(x_i h_i\), with independent \(h_i\sim\mu\). The resulting distribution of the inhomogeneous differences is absolutely continuous even for a fixed input simplex: the sampled vertices have a product Haar density, and passing to the first vertex and consecutive differences preserves product Haar measure. The smoothing \(S\) is continuous by total-variation continuity of translates of \(\mu\); it is contractive and commutes with the differential.

Use the prism with mixed vertices \((x_0,\ldots,x_j,x_jh_j,\ldots,x_nh_n)\), with sign \((-1)^j\). Its preadjoint on a finite Radon test measure is to take the product with the sampling probabilities and push forward under the difference map of this mixed list (set \(x_0=1\) for inhomogeneous inputs). This gives finite Radon tests, so the prism is well-defined on the entire bidual. On continuous inputs it is the usual continuous averaging prism. The same end-face calculation as above gives a homotopy from the identity to \(JSR\) on the bidual, and to \(SRJ\) on continuous cochains, with \(J\) denoting the integration embedding. Thus \(J\) and \(SR\) are inverse contractions on cohomology. The use of independent smoothing in every coordinate is important: a mixed prism applied just to Haar classes can have no continuous representative. For example, on \(\mathbb R\) with additive coordinates, \(K^2\) sends \(f(a,b)=\mathbf1_{(0,\infty)}(a)\) to \(g\mapsto\mu((0,\infty))-\mathbf1_{(0,\infty)}(g)\).

For the usual Haar model see [Burger–Monod (2002), Theorem 2](https://www.epfl.ch/labs/egg/wp-content/uploads/2020/06/gafa.pdf#page=2). The comparison just proved is for trivial real coefficients; the general Banach bundle comparison does not follow. Even the trivial group has degree-zero terms \(E^{**}\) here versus \(E\) in the usual complex, which prevents the corresponding isomorphism for nonreflexive \(E\). The argument is checked in writing, not in Lean.

## What is lost by evaluating only at points

Point evaluation, followed by the second adjoint, gives a contractive cochain map to the complex of all bounded cochains on the underlying abstract groupoid with the fiber biduals as coefficients. In degree \(n\), these evaluations restrict the original functional to the closed span of point-supported tests. This span is the \(\ell^1\)-sum of the dual fibers: the lower norm bound for a finite sum follows by choosing near-norming local sections at distinct points, multiplied by cutoffs with disjoint supports. Thus restriction is onto in each degree by Hahn–Banach, with kernel the annihilator of this span. It need not be injective on cohomology.

Let \(\Gamma=F_2\) act by left translations on its profinite completion \(X\). Residual finiteness makes the action free; the normalized Haar probability \(\nu\) is invariant and nonatomic. The coefficient bundle for the mass-zero test identifies with \(I=\ell^1_0(\Gamma)\), and its cocycle is \(b(g,x)=\delta_e-\delta_g\). Abstractly, choose one representative in each orbit and express \(x=k_xt\) for its chosen representative \(t\). The bounded assignment \(v(x)=\delta_e-\delta_{k_x}\) satisfies \(v(gx)-g v(x)=b(g,x)\). The chosen transversal is not Haar-measurable: its countably many disjoint translates would cover \(X\) with equal measures, which cannot occur.

On the regular section bidual, any primitive would give, by the second adjoint of integration against the invariant \(\nu\), a vector \(w\in I^{**}\) with \(w-gw=\delta_e-\delta_g\). Then \(\delta_e-w\), viewed in \(\ell^1(\Gamma)^{**}\), has mass one and is invariant. Its normalized variation gives an invariant mean, contradicting nonamenability. Thus \(b\) detects a genuine difference between the two complexes even for a free étale transformation groupoid. For the discrete action criterion see [Brodzki–Niblo–Nowak–Wright (2012), Theorem B](https://arxiv.org/pdf/1004.0295#page=2). The comparison is checked in writing, not in Lean.
