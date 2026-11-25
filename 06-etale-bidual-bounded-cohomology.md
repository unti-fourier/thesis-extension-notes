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
