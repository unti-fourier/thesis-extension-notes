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

## Testing all words of length at most two

At \(R=1\), testing all words of length at most two instead of generators alone changes the boundary value to
\[
 \inf_p\ \max_{|g|\le2}\sup_x\|g p_x-p_{gx}\|_1
 =\frac{2(4r-1)}{4r+1}.
\]
In fact this holds for any nonempty action space. Write \(d=2r\) and let \(t=1-\varepsilon/2\) for a field with defect \(\varepsilon\). Every test then has overlap (sum of pointwise minima) at least \(t\). For each \(s\in S\), the only shared coordinate in \(B_1\cap s^2 B_1\) is \(s\). Testing at \(s^{-2}x\) therefore gives \(p_x(s)\ge t\) for every \(x\). Thus \(p_x(e)\le1-dt\). A one-letter test at \(x\) has only two shared coordinates and its overlap is at most \(p_x(e)+p_{sx}(e)\le2(1-dt)\). Consequently \(t\le2/(2d+1)\).

The constant field giving the center mass \(1/(2d+1)\) and each neighbor \(2/(2d+1)\) attains the bound: one-letter overlap consists of two contributions \(1/(2d+1)\), and two-letter overlap is a single midpoint of mass \(2/(2d+1)\). Equality in the one-letter bound forces both center masses to be \(1/(2d+1)\) at every test, so the neighbor masses must all equal their lower bound too. This gives uniqueness. The value is \(14/9\) for \(F_2\). In contrast, the ray field at \(\xi=s^\infty\), tested against \(s^2\), has disjoint supports and defect \(2\). Radius zero leaves only one possible field, so radius one is the first failure of optimality of the ray field for this test set.

This extension of the calculation was independently checked in writing; no Lean, full \(I\)-defect or priority claim is made.

## Radius two for the two-letter test on \(F_2\)

With \((R,L)=(2,2)\) the exact boundary value is \(6/5\). The unique optimal field is
\[
 p_\xi=\tfrac25\delta_e+\tfrac15\delta_{\xi_1}+\tfrac25\delta_{\xi_1\xi_2}.
\]
For this field, two adjacent starts toward the same end give overlap \(2/5\). At distance two, the overlap is \(2/5\) when one start lies on the other's ray, and \(3/5\) when the two rays meet at the midpoint. This improves the uniform ray average's defect \(4/3\).

Here is a lower bound for arbitrary continuous fields. Choose the end by the uniform nonbacktracking distribution. Orient the tree with each parent toward that end. At a vertex write \(a,b,c\) for the *expected* masses at the vertex, parent and grandparent, and \(J,D_1,D_2\) for expected total masses at the siblings, children and grandchildren. To evaluate an overlap, choose a child uniformly (one of three), then a grandchild by a second uniform child choice if needed. Recentring the end at the chosen child leaves its marginal distribution unchanged: the inserted first letter is uniform among the four, the conditional second letter is uniform among the three allowed letters, and the later transition probabilities are unchanged. Thus the expected masses at the child or grandchild have the same marginals.

If all tests have overlap at least \(t\), the child comparison gives
\[
 t\le 2b+J+(D_1+D_2)/3 .
\]
In the common support, bound the parent's coordinate from the original row and the original vertex from the child's row, giving the two terms \(b\). Bound the chosen child from the original row, the child's siblings from the child's row, and the children of the chosen child from the original row. The grandchild comparison gives
\[
 t\le (a+c)/2+(D_1+D_2)/3 .
\]
Its common support is the radius-one ball about the intermediate child. At the original vertex use the mean of the two masses to bound their minimum; at the intermediate child and its children use the original row. Adding the second inequality four times to the first gives \(5t\le 2-J-(D_1+D_2)/3\). This proves the lower bound \(2(1-t)\ge6/5\).

At equality the three off-ray expected masses vanish, hence by continuity and full support they vanish at every end. The grandchild comparison now shares only the original vertex, forcing both the center and grandparent masses to be at least \(2/5\) at every end. The parent mass is therefore at most \(1/5\); the child comparison then forces both parent masses involved to be \(1/5\). Normalization forces the other two masses to be \(2/5\). The certificate is a written calculation, not a Lean verification or a claim of priority.

## Radius three for the two-letter test on \(F_2\)

At \((R,L)=(3,2)\) the exact boundary defect is \(12/13\); if the probabilities are restricted to the first four ray vertices, the best value is \(1\). For the unrestricted upper bound, orient the tree toward the boundary point, and put mass \(2/13\) at each of the first four ray vertices \(g_0,g_1,g_2,g_3\). Put mass \(1/13\) at each of the three children of \(g_0\) and at the two children of \(g_2\) other than \(g_1\). Two starts at distance at most two are a parent and child, grandparent and grandchild, or siblings. The respective overlaps are \(7/13,7/13,8/13\): the minima on the common ray account for \(6,4,6\) units, and the listed branch vertices account for \(1,3,2\) units.

For the lower bound, the type \((i,j)\) records \(i\) parent steps and then \(j\) child steps from the row's center. Write \(A_i,D_j,J_{ij}\) for types \((i,0),(0,j),(i,j)\), with \(i,j>0\) where appropriate. Also use these symbols for their expected mass **per vertex** under the uniform nonbacktracking law on ends. Write \(x_\beta\) for the mass for a generic type, and \(n_\beta\) for its multiplicity. Then \(\sum_\beta n_\beta x_\beta=1\). Recentring at a uniformly chosen child or grandchild preserves the end's distribution, as in radius two.

For a descendant \(w\) at depth \(\ell=1,2\), a point of type \(\beta=(i,j)\) relative to \(w\) has type \(\alpha_\ell=((i-\ell)_+,j+(\ell-i)_+)\) relative to the original center. Fix the end and average over the choice of \(w\). Every vertex of type \(\alpha_\ell\) is selected with probability \(n_\beta/n_{\alpha_\ell}\), since the rooted tree automorphisms fixing the parent ray act transitively on the vertices of that type. This is a counting argument on locations, not a symmetry assumption on the rows. Thus if every overlap is at least \(t\), comparison along a depth-\(\ell\) path gives
\[
 t\le Q_\ell=\sum_\beta n_\beta \min(x_\beta,x_{\alpha_\ell(\beta)}),
\]
with masses outside the ball zero. The following table bounds the contributions to the two weighted sums, using \((b+c)\min(x,y)\le bx+cy\).

| Type | Multiplicity | Parent-step contribution to \(2Q_1\) | Two-step contribution to \(11Q_2\) |
| --- | ---: | --- | --- |
| \(A_0\) | 1 | \(2D_1\) | \(11D_2\) |
| \(A_1\) | 1 | \(2A_1\) | \(11D_1\) |
| \(A_2\) | 1 | \(A_1+A_2\) | \(7A_0+4A_2\) |
| \(A_3\) | 1 | \(2A_2\) | \(4A_1+7A_3\) |
| \(D_1\) | 3 | \(6D_2\) | \(33D_3\) |
| \(D_2\) | 9 | \(18D_3\) | 0 |
| \(D_3\) | 27 | 0 | 0 |
| \(J_{11}\) | 2 | \(4J_{11}\) | \(22D_2\) |
| \(J_{12}\) | 6 | \(12D_2\) | \(66D_3\) |
| \(J_{21}\) | 2 | \(4J_{11}\) | \(8D_1+14J_{21}\) |

Summing gives \(13t\le 2Q_1+11Q_2\le7-12D_2-72D_3-6J_{11}-42J_{12}\le7\). If all mass is on the ray, \(Q_2\le(A_0+A_1+A_2+A_3)/2=1/2\), and the uniform ray field attains this overlap at the worst distance-two test. These are finite written certificates, independently checked; no Lean verification or priority claim is made.

## A finite linear program for every radius and test length

For every \(r\ge2\) and integers \(R,L\ge0\), the boundary defect with word ball support \(B_R\) and all tests \(|g|\le L\) is the minimum variation among arbitrary probability fields on the regular tree with the same support radius and distance tests. Both are computed by a finite rational linear program. In particular, there is a rational minimizer on the boundary depending only on the first \(R\) letters.

Fix an end \(\omega\) and let \(P\) be its stabilizer in the full tree automorphism group with the topology of pointwise convergence. Its Busemann kernel is the increasing union of the compact subgroups fixing successive vertices of an \(\omega\)-ray; the quotient is \(\mathbb Z\), split by translation along a line to the end. See [Cartwright–Kaimanovich–Woess (1994), §2.D](https://www.numdam.org/item/10.5802/aif.1433.pdf#page=11). There is a left invariant mean on bounded continuous functions that are uniformly norm continuous under left translation. In fact, Haar averages over those increasing compact subgroups have a kernel-invariant weak-star cluster point. Averaging its translates along successive powers of the splitting translation preserves kernel invariance by normality, and any cluster point is also translation-invariant by the Cesàro end-term estimate.

For an arbitrary vertex field \(\mu_v\), average the coordinates \(g\mapsto\mu_{g^{-1}v}(g^{-1}z)\) with this mean. Each is fixed under left multiplication by the open subgroup fixing \(v,z\), hence meets the required uniform continuity. The averaged row still has mass one by finite support, is supported in \(B(v,R)\), and has no larger variation on any pair at distance at most \(L\), by positivity and the triangle inequality on the finite union of the two balls. The field is \(P\)-equivariant. This argument does not use amenability of \(P\) with the discrete topology.

An ordered pair of vertices is classified under \(P\) by the lengths \((i,j)\) of the two paths to the first common vertex of their rays to \(\omega\). Indeed, a correspondence on the two paths and their common tail extends by matching the rooted side trees. For \(i+j\le R\) let \(x_\alpha\), \(\alpha=(i,j)\), be the mass of each point of that type from the row's center, and \(n_\alpha\) its multiplicity. If \(q=2r-1\), these multiplicities are \(1\) for \(j=0\), \(q^j\) for \(i=0<j\), and \((q-1)q^{j-1}\) for \(i,j>0\). For each start-pair type \(\sigma\) of distance at most \(L\), let \(c^\sigma_{\alpha\beta}\) count common support points of types \(\alpha,\beta\) from the two starts. These integers are obtained by enumerating the radius-\(R\) balls about any representative pair.

Maximize \(0\le t\le1\) subject to
\[
 x_\alpha\ge0,\quad \sum_\alpha n_\alpha x_\alpha=1,\qquad
 0\le y_{\alpha\beta}\le x_\alpha,\quad
 y_{\alpha\beta}\le x_\beta,\qquad
 \sum_{\alpha,\beta}c^\sigma_{\alpha\beta}y_{\alpha\beta}\ge t
 \quad\text{for every }\sigma .
\]
The \(y\)'s can always be raised to their upper bounds, so this tests the exact overlaps. The optimum \(t^*\) gives defect \(2(1-t^*)\). Conversely, the LP field at an end \(\eta\) puts mass \(x_{(i,|z|-i)}\) at \(z\in B_R\), with \(i\) the common prefix length of \(z,\eta\). This is continuous and the comparisons for \(h\) are the tree comparison of starts \(e,h\) oriented toward the same end \(h\eta\). For the other inequality, any boundary field gives a vertex field by \(\mu_v=v p_{v^{-1}\omega}\). Thus the optimization values agree.

There is also a finite dual certificate using only subsets \(U\) of the support-type set. Put \(n(U)=\sum_{\alpha\in U}n_\alpha\) and \(c^\sigma(U)=\sum_{\alpha,\beta\in U}c^\sigma_{\alpha\beta}\). For any normalized mass vector \(x\), integrating its level sets decomposes its overlaps into one convex combination of the overlap vectors \(c^\sigma(U)/n(U)\). Conversely, a convex combination of the corresponding normalized indicator vectors gives at least that combination of overlaps, by concavity of the minimum. Finite minimax therefore gives
\[
 t^*=\min_{\substack{w_\sigma\ge0\\\sum_\sigma w_\sigma=1}}
     \max_{U\ne\varnothing}
        \frac{\sum_\sigma w_\sigma c^\sigma(U)}{n(U)} .
\]
For the underlying graph optimization, see [Bell–Nagórko (2021 preprint), §2](https://arxiv.org/html/2109.04891#S2), applied to the graph of pairs at distance at most \(L\) and with the prescribed balls taken in the original tree. The finite orbit reduction above is checked in writing, not in Lean; no priority claim is made.

## Uniform asymptotics from a sampled walk

For \(L\ge1\), the profile above satisfies
\[
 \frac{2L}{R+L}\ \le\ \Delta_{\le L}(R)\
 \le\ \min\{2,\,2L/(R+1)\}.
\]
The upper bound uses the uniform measure on the first \(R+1\) ray vertices: for starts at distance at most \(L\), each ray reaches the common tail by step \(L\).

For the lower bound, observe the outward random walk in the first proof only at multiples of \(L\). When starting at distance \(k\le R\) from the center of the test ball, with \(J\) shared initial edges with the path toward the center, its visits to the ball last through time \(R-k+2J\). Thus the number of sampled visits is \(1+\lfloor(R-k+2J)/L\rfloor\). The bound \(2\mathbb E J\le 2k/q\le k\) gives an expected count at most \(M=1+R/L\). If the initial point is outside the ball, condition on first entrance and the current sampling phase. The visits after entrance form one interval of integer times; the phase offset can only decrease the count compared to starting the sampling at entrance. The same \(M\) applies. The occupation recursion with the sampled transition and the centered test \(H-M/2\) now gives \(1\le M/N+M\varepsilon/2\) after \(N\) steps, exactly as in the generator case. In this lower bound only distance-\(L\) comparisons are used.

In particular \(R\Delta_{\le L}(R)\to2L\) for fixed \(L\), and \(\Delta_{\le L}(R)/(2L/R)\to1\) uniformly when \(1\le L\le m(R)=o(R)\). These bounds are independently checked in writing, not in Lean.

## The longest nontrivial test length

For \(R\ge2\), put \(q=2r-1\), \(m=2r q^{R-1}\) and \(t_R=1-\Delta_{\le 2R}(R)/2\). Then
\[
 \frac1{m+R/2}\le t_R\le\frac1{m+1},
 \qquad
 q^R(2-\Delta_{\le 2R}(R))\longrightarrow\frac{2r-1}{r}.
\]
If only lengths \(2R-1\) and \(2R\) are tested, the optimal overlap is \(1/(m+1)\). For all tests the displayed bounds coincide at \(R=2\).

For the upper bound on overlap, take any vertex field whose overlaps at the tested distances are at least \(t\). Every point at radius \(R\) has mass at least \(t\), since it is the only common point for a pair of radius-\(R\) balls with that midpoint at distance \(2R\). At distance \(2R-1\) the common support contains only the two middle vertices, each lying at radius \(R-1\) from one of the starts. If \(M\) is the supremum of an individual radius-\((R-1)\) mass, the two-point comparison forces every radius-\((R-1)\) mass to be at least \((t-M)_+\). Take a row with a mass close to \(M\) and count at least one other point on that layer. Thus \(1\ge mt+M+(t-M)_+\ge(m+1)t\). For just the two longest distances put unit weights on the entire outer sphere and on the single ancestor at depth \(R-1\) toward the end. For distance \(2R-1\) one of the two middle vertices is such an ancestor of one start, and for distance \(2R\) the midpoint is on both spheres. This attains the bound.

For all distances use weight one on the whole outer sphere, weight one on each positive ray depth \(j<R\) of parity opposite to \(R\), and, for odd \(R\), weight \(1/2\) at the start. The total is \(m+R/2\). At even distance \(2k\), one common sphere vertex is found by going \(R-k\) steps off the segment from its midpoint. At odd distance \(\ell\), let \(a,b\) be the two distances to the ray meeting point. If \(\ell>R\), take \(a\ge b\) and the ray point at depth \(j=\ell-R\) from the first start; it lies on the segment and on the other start's sphere. If \(\ell<R\), take \(a<b\) and \(j=R-(b-a)\); the ray point is on the common tail at distance \(R\) from the other start. Both depths have the required parity. If \(\ell=R\) is odd, the two starts contribute \(1/2\) each. Thus the unnormalized overlap is always at least one, proving the lower bound and hence the limit. These estimates are independently checked in writing, not in Lean.
