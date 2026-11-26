# The raw I-amenability constant with one isolated atom

**Work in progress.** Written proof checked. This is not a paper, Lean formalization, or priority claim.

Let \(X=\{\star\}\sqcup Y\) be compact Hausdorff with \(\star\) isolated. Let the Radon probability \(\mu\) give mass \(p\in(0,1)\) to \(\star\), and assume that its restriction to \(Y\) is nonatomic with full support. Set \(d=1-p\). The raw \(I\)-norm completion \(A\) of the continuous convolution kernels of the pair groupoid has ordinary Banach amenability constant
\[
\operatorname{AM}(A)=\frac1d .
\]
Here the raw \(I\)-norm is the maximum of the supremal \(L^1(\mu)\) row and column norms. The proof does not use a restriction homomorphism to a finite subset.

## Lower bound

The kernel representation \(T:A\to\mathbb B(L^2(\mu))\) is contractive by the Schur test. For an elementary tensor set \(S_{a\otimes b}=T_a P_\star T_b\), with \(P_\star\) the rank-one projection for the atom. This defines a contractive map from the projective tensor product to trace-class operators and satisfies \(S_{a\cdot m-m\cdot a}=[T_a,S_m]\).

Let \(m\) run over a bounded approximate diagonal. For each finite orthonormal family \(f_1=1,f_2,\ldots,f_n\) of continuous functions in \(L^2(\mu)\), the differences \(\langle S_m f_j,f_j\rangle-\langle S_m1,1\rangle\) tend to zero: test the commutator against the continuous rank-one kernel \(f_j(x)\overline{1(y)}\). The sum of the absolute values of these diagonal entries is bounded by the trace norm of \(S_m\). There are arbitrarily large such families by density of \(C(X)\) and infinite dimensionality of \(L^2(\mu)\). It follows that \(\langle S_m1,1\rangle\to0\).

Meanwhile \(\langle T_{\pi(m)}1,1\rangle\to1\), by the approximate-identity property on the continuous rank-one kernel projecting onto \(1\). The contribution of \(I-P_\star\) between the two kernel factors therefore tends to one. The bilinear functional giving that contribution has norm at most \(d\):
\[
|\langle T_a(I-P_\star)T_b1,1\rangle|
\le \int_Y |(T_a^*1)(y)|\,|(T_b1)(y)|\,d\mu(y)
\le d\|a\|_I\|b\|_I.
\]
This proves the lower bound.

## Upper bound

Use the [equal-mass soft partitions](06-pair-groupoid-raw-i-amenability.md) on \(Y\) with its normalized measure; add the indicator of \(\star\). Write \(h_i\) for the resulting \(N+1\) weights and \(w_0=p,\ w_j=d/N\) for their integrals. Give matrices the weighted norm
\[
\|B\|_w=\max\left(\max_i\sum_j |B_{ij}|,\ \max_j\sum_i w_i|B_{ij}|/w_j\right).
\]
The map \(T(B)(x,y)=\sum_{ij}h_i(x)B_{ij}h_j(y)/w_j\) is contractive into raw \(I\) and satisfies \(T(B)*T(C)=T(BGC)\), where \(G_{jk}=\int h_j h_k\,d\mu/w_j\). The atom is its own identity block; the diffuse block is the symmetric stochastic Gram matrix from the soft-partition construction. Hence \(\|G-I\|_w\to0\) uniformly in \(N\) as the partition error tends to zero. For finitely many test kernels \(f\), use \(B_{ij}=w_j f(x_i,x_j)\) with \(x_i\) chosen in the relevant open sets (and \(x_0=\star\)). Then \(\|B\|_w\le \|f\|_\infty\) and \(T(B)\) approximates \(f\) uniformly.

The finite exact diagonal, with intermediate labels restricted to the diffuse part, is
\[
Z_N=\frac1N\sum_{i=0}^N\sum_{j=1}^N E_{ij}\otimes E_{ji}.
\]
It centralizes all matrix units and has product \(I\). For \(k=\lfloor pN\rfloor\ge1\), put \(r=pN/d\), so \(k<r\). To decompose \(Z_N\), choose uniformly a \(k\)-subset \(J\) of the diffuse columns for row zero, and injectively match the other \(N-k\) columns to uniformly chosen different diffuse rows. Before averaging, use a tensor \(a\otimes b\) supported on these pairs and their reverses. For \(j\in J\), the unscaled entries are \(a_{0j}=1/k,\ b_{j0}=1\), so that this block has norm bounds \(r/k\) and \(1\). Rescale its two factors reciprocally to make their norms at most \(\sqrt{r/k}\). For each matched diffuse pair, use entries \(\sqrt{N/(N-k)}\) in both factors. The two blocks have disjoint row and column support in each factor, so the whole product of norms is at most
\[
M_N=\max\left(\frac{N}{N-k},\ \frac{r}{k}\right)\longrightarrow\frac1d.
\]
Give both entries at each pair the same independent random sign. This eliminates all cross-pair terms. Each \(0,j\) pair is selected with probability \(k/N\) and has product \(1/k\); each diffuse \(i,j\) pair is selected with probability \((N-k)/N^2\) and has product \(N/(N-k)\). Therefore the average is exactly \(Z_N\).

Finally transfer \(Z_N\) by \(T\otimes T\). Its commutator on \(T(B)\) differs from the transferred exact matrix commutator by at most \(2\|B\|_w\|G-I\|_w M_N\). Its product is \(T(I+\Delta)\) with \(\|\Delta\|_w\le\|G-I\|_w M_N\), using the same twisted multiplication formula. Thus it acts as a two-sided approximate identity on interpolated kernels. The uniform approximation and a directed choice of test families, vanishing partition error and increasing \(N\) give the upper bound (or bound \(1/d+\epsilon\) for each \(\epsilon>0\)). No conclusion for an atom that is not isolated or for several atoms is asserted here.
