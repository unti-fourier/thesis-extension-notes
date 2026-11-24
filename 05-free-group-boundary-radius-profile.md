# The sharp Reiter radius profile of a free group boundary

**Work in progress, November 2026.** This is a research note toward possible future papers, not a submitted or peer-reviewed paper. No priority claim is made.

Let \(F_r\), \(2\le r<\infty\), have its standard symmetric generating set \(S\), right Cayley tree \(T\), and usual left action on \(\partial F_r\). For a nonnegative integer \(R\), use the closed word ball \(B(e,R)\). Among all continuous fields of probabilities \(p_\xi\) supported in this one ball, the exact range-row defect is
$$
\inf_p\ \max_{s\in S}\sup_{\xi\in\partial F_r}
  \|s p_\xi-p_{s\xi}\|_1=\frac{2}{R+1}.
$$
The \(\ell^1\) norm here is the sum of absolute values. The source-side condition in the full groupoid \(I\)-norm is not included.

**Upper bound.** Give equal mass to the first \(R+1\) vertices, including the identity, on the ray to \(\xi\). The two rays being compared start at adjacent vertices and point to the same end; the initial segments share exactly \(R\) vertices. Hence their probabilities differ by \(2/(R+1)\). This ray average is the classical construction in [Dranishnikov–Januszkiewicz (1999), Proposition 1](https://arxiv.org/abs/math/9911245).

**Lower bound.** Fix \(\xi_*\in\partial F_r\) and put \(\mu_v=v p_{v^{-1}\xi_*}\). These are probabilities on \(B(v,R)\), and their maximum variation \(\varepsilon\) across edges is bounded above by the defect of \(p\). We show that *any* such family on the vertices satisfies \(\varepsilon\ge 2/(R+1)\).

Orient the tree away from an end. Starting at \(v\), choose one of its \(q=2r-1\) children uniformly at every step. Let \(H_v(z)\) be the expected total number of visits to \(B(z,R)\). If \(k=d(v,z)\le R\), let \(L\) count the common initial edges of the random path and the geodesic to \(z\). The number of visits is \(R-k+2L+1\); moreover \(\Pr(L\ge j)\le q^{-j}\) for \(1\le j\le k\). Thus \(H_v(z)\le R-k+1+2k/q\le R+1\). For a starting point outside \(B(z,R)\), condition on first entrance. Consequently \(0\le H_v(z)\le R+1\) everywhere.

For the first random child \(W\), the visit recursion gives \(H_v-\mathbb E_v H_W=1_{B(v,R)}\) as functions of \(z\). Pair with \(\mu_v\) and write \(A_v=\langle H_v,\mu_v\rangle\). The difference \(\mu_W-\mu_v\) has mass zero, so centering \(H_W\) at \((R+1)/2\) gives
$$
1=A_v-\mathbb E_v A_W+\mathbb E_v\langle H_W,\mu_W-\mu_v\rangle
  \le A_v-\mathbb E_v A_W+(R+1)\varepsilon/2.
$$
Telescoping the expected inequalities over \(N\) steps gives \(1\le (R+1)/N+(R+1)\varepsilon/2\), proving the claim as \(N\to\infty\).

The same upper construction from a fixed end and the lower bound for arbitrary vertex fields compute the closed-ball profile of the regular tree as well. See [Gal (2008), Definitions 2.1.1 and 2.1.3](https://doi.org/10.4171/GGD/31) for the quantitative property A profile, and [Bell–Nagórko (2025 online; 2021 preprint), Theorem 9.1 and §9.3](https://arxiv.org/html/2109.04891#S9.SS3) for related finite large-girth problems and finite subtree boundary effects. The action profile of [Nowak (2008), Definitions 3.1–3.2](https://doi.org/10.1016/j.aim.2008.04.012) minimizes support cardinality rather than radius.

**Verification.** Both bounds were independently checked in writing. This note makes no Lean or full \(I\)-defect claim.

## Contrast: actions admitting an invariant probability

Let \(F_r\) act on a compact Hausdorff space \(X\) admitting an invariant probability \(\nu\). Write \(d=2r\), \(q=d-1\), \(B_R=B(e,R)\), and \(N=|B_R|\). For \(p:X\to\operatorname{Prob}(B_R)\) put \(d_s(x)=\|s p_x-p_{sx}\|_1\). Each of
\[
 \max_s\sup_x d_s(x),\qquad
 d^{-1}\sum_s\sup_x d_s(x),\qquad
 \sup_x d^{-1}\sum_s d_s(x)
\]
has minimum \(c_R=2q^R/N=(2/d)(d-2+2/N)\). **If \(\nu\) has full support, the unique minimizer for each objective is the constant uniform field on \(B_R\).** This applies to the profinite completion with its Haar probability. The value tends to \(2-2/r\), unlike the boundary value above.

**Value and interior equality.** The mean \(u=\int p_x\,d\nu(x)\) satisfies \(\int d_s\,d\nu\ge\|su-u\|_1\). If \(U_t=\{g:u(g)>t\}\) and \(c(U_t)\) counts its components in the left Cayley tree, then
\[
 \frac1d\sum_s\|su-u\|_1
 =\frac2d\int_0^\infty\bigl[(d-2)|U_t|+2c(U_t)\bigr]\,dt
 \ge\frac2d(d-2+2\|u\|_\infty)\ge c_R.
\]
The last bound is an equality only for \(u=N^{-1}\mathbf1_{B_R}\), whose shift loses \(q^R\) coordinates in each direction. The constant field realizes this bound. At equality even for the integrated objective \(d^{-1}\sum_s\int d_s\,d\nu\), the coordinates outside the shifted-ball overlap already account for \(c_R\) after integration. The overlap therefore has no defect. With full support and continuity this gives \(p_{sx}(sg)=p_x(g)\) on each interior edge at every \(x\). Hence \(p_x(g)=f(g^{-1}x)\) on \(B_R\), where \(f(x)=p_x(e)\) and \(T_{B_R}f=1\) for \(T_A f(x)=\sum_{g\in A}f(g^{-1}x)\). Conversely every such nonnegative continuous \(f\) minimizes the integrated objective.

**Boundary equality and uniqueness.** Interior equality gives \(d_s(x)=2T_{E_s}f(x)\), where \(E_s=\{g\in B_R:sg\notin B_R\}\): the overlap agrees and the two remaining masses are equal. For \(R\ge1\), each element of the sphere \(H_R\) of radius \(R\) belongs to exactly \(q\) of the \(E_s\). Equality for even the smallest of the three supremum objectives forces the continuous function \(\sum_s d_s(x)\) to be identically \(dc_R\), since its average already has that value and \(\nu\) has full support. Therefore, for \(v=f-1/N\), \(T_{B_R}v=T_{H_R}v=0\) and then \(T_{B_{R-1}}v=0\). The radial identity
\[
 (T_S-dI)T_{B_j}=T_{H_{j+1}}-qT_{H_j}\qquad (j\ge1)
\]
has coefficients \(0,-q,1\) at lengths below \(j\), equal to \(j\), and equal to \(j+1\), respectively. It gives the same vanishing at each lower radius and finally \(v=T_{B_0}v=0\). The \(R=0\) case has only one possible field.

For the integrated objective alone, take \(R=1\), the quotient \(F_r\to\mathbb Z/(2r+1)\) with \(a_i\mapsto i\), and \(f=\mathbf1_{\{\overline0\}}\). The ball maps bijectively onto the quotient, so \(T_{B_1}f=1\) and the field of point masses minimizes the integrated objective. At \(x=\overline1\) and \(s=a_1\) its shifted mass is at \(a_1^2\) outside \(B_1\), so the supremum defect is \(2\). Pullback gives the same distinction on the profinite completion.

The scalar lower bound is the Cayley-tree edge count and coarea. The additional conclusion here is the classification of the equality case for continuous fields. The defect convention agrees with [Nowak (2008), Definition 3.1](https://doi.org/10.1016/j.aim.2008.04.012) after reindexing, while Definition 3.2 optimizes support cardinality at a prescribed error. This section was independently checked in writing; no Lean verification, full \(I\)-norm statement, or priority claim is made.
