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
