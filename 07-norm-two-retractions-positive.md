# Norm-two commutant retractions are positive in infinite dimension

**Work in progress.** Written proof checked; not a paper, Lean formalization, or priority claim.

Let \(M\subseteq\mathbb B(H)\) be a concrete unital infinite-dimensional von Neumann algebra, and \(N=M'\). If \(Q:\mathbb B(H)\to N\) is a bounded \(N\)-bimodule retraction, then
\[
\|\mathrm{id}-Q\|\ge2,\qquad
\|\mathrm{id}-Q\|=2\ \Longleftrightarrow\ Q\text{ is positive}.
\]
No normality or separability is required. This result does not assert existence of a positive retraction.

**Vectors with small compression.** Suppose \(e\in Z(M)=Z(N)\) and \(eM\) is infinite dimensional. For any \(m\) choose \(m\) orthogonal nonzero projections in \(eM\) and a unit vector in the range of each. Their Fourier combinations give \(m\) orthonormal unit vectors \(w_j\in eH\) with the same vector state \(\omega\) on \(N\): the off-diagonal terms vanish since \(N\) commutes with the projections, and the squared coefficients are all \(1/m\). Write \(P_w=|w\rangle\langle w|\). By testing the bounded functional \(\omega\circ Q\) on finite sums of the orthogonal projections \(P_{w_j}\) with phases,
\[
\sum_{j=1}^m |\langle Q(P_{w_j})w_j,w_j\rangle|\le\|Q\|.
\]
Taking \(m\) large makes the scalar arbitrarily small for some \(w_j\). At \(e=1\), testing \(I-2P_{w_j}\) yields the lower bound two. A positive retraction is unital and contractive, so it gives equality.

**Excluding nonpositive retractions.** Central corners are preserved by bimodularity and have complement norm bounded by the full complement norm. Split \(N\) into its diffuse part and its atomic type-I central summands. On the diffuse part the [finite-rank annihilation argument](07-diffuse-commutant-retraction-norm.md) proves the stronger formula \(1+\|Q_{\rm corner}\|\). On an atomic central summand \(z\), write \(zH=H_0\otimes K_0\) with \(zM=\mathbb B(H_0)\otimes 1\). If \(H_0\) is infinite dimensional, the [properly infinite argument](07-properly-infinite-retraction-norm.md) proves the same formula. It remains to exclude a nonpositive slice \(\varphi\) on a finite-dimensional \(H_0\), where the slice identification follows by compressing against rank-one operators on \(K_0\).

Choose a rank-one projection \(p\) in \(\mathbb B(H_0)\) with \(\alpha=\varphi(p)\notin[0,\infty)\), and a unit product vector \(h\in zH\) perpendicular to \((p\otimes1)zH\), in the direction of a rank-one projection \(q\perp p\) on \(H_0\). The unitary \(U\) is \(\bar\alpha/|\alpha|\) on \((p\otimes1)zH\) and the identity elsewhere. Since \(M\) is infinite dimensional and \(zM\) is finite dimensional, the previous vector estimate applies in \((1-z)H\). Choose \(w\) there with \(|\langle Q(P_w)w,w\rangle|\) arbitrarily small. For \(0<s<1\), put \(v=\sqrt{s}\,h+\sqrt{1-s}\,w\) and test \(U(I-2P_v)\) on \(v\). This unitary sends \(v\) to \(-v\); the off-diagonal blocks vanish after applying \(Q\). Its image under \(Q\) has real vector entry
\[
1+s(|\alpha|-\operatorname{Re}\alpha)-2s^2\operatorname{Re}\varphi(q)
 -2(1-s)^2\operatorname{Re}\langle Q(P_w)w,w\rangle.
\]
Let the last term tend to zero. The strictly positive linear term then forces \(\|\mathrm{id}-Q\|>2\) for small \(s\). Thus at equality every corner map is positive, which gives positivity of \(Q\) because its range lies in the block-diagonal algebra \(N\).
