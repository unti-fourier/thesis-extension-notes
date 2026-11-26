# Diffuse commutants and norm-two retractions

**Work in progress.** Written verification only; not a paper, Lean formalization, or priority claim.

Let \(N\subseteq\mathbb B(H)\) be a unital von Neumann algebra with no nonzero minimal projections. For every bounded \(N\)-bimodule retraction \(Q:\mathbb B(H)\to N\),
\[
\|\mathrm{id}-Q\|=1+\|Q\|.
\]
In particular, if a retraction of complement norm two exists, it is positive and contractive. This includes \(N=R'\) for the hyperfinite \(\mathrm{II}_1\) factor \(R\) in standard form. The formula is conditional on the existence of \(Q\), and does not require normality.

**Finite-rank annihilation.** Consider \(k=|\alpha\rangle\langle\beta|\). If \(z=Q(k)\ne0\), choose a nonzero spectral projection \(p=1_{[\delta,\infty)}(|z|)\) in \(N\) for some \(\delta>0\). Split \(p\) into \(m\) nonzero orthogonal projections in \(N\), using absence of minimal projections. One of these, \(e\), has \(\|e\beta\|\le\|\beta\|/\sqrt m\). By right modularity and the lower spectral bound on \(p\),
\[
\delta\le\|ze\|=\|Q(ke)\|\le\|Q\|\,\|\alpha\|\,\|\beta\|/\sqrt m.
\]
Arbitrary \(m\) gives a contradiction. Thus \(Q\) annihilates finite-rank operators and hence their norm closure.

**Norming perturbation.** Choose a contraction \(a\) and a unit vector \(\xi\) with \(c=\|Q(a)\xi\|>0\) as close as desired to \(\|Q\|\). Put \(\eta=Q(a)\xi/c\), and let \(p_\xi,p_\eta\) be the rank-one projections on these unit vectors. The operator
\[
b=(1-p_\eta)a(1-p_\xi)-|\eta\rangle\langle\xi|
\]
is a contraction: its first term maps \(\xi^\perp\) into \(\eta^\perp\), its second maps \(\xi\) isometrically to \(-\eta\), and the corresponding domain and range summands are orthogonal. The difference \(b-a\) has finite rank, so \(Q(b)=Q(a)\), and \((b-Q(b))\xi=-(1+c)\eta\). The triangle inequality supplies the upper bound and the norming choice of \(c\) gives equality. The same argument works for any retraction annihilating the compact operators, regardless of how this is proved. At norm one, positivity follows by testing the unital contractive map against states of \(N\).

For the hyperfinite \(\mathrm{II}_1\) example, positive retractions exist: average conjugations by the unitary groups of the nested matrix subfactors generating \(R\), and take a point-ultraweak cluster point. It fixes \(R'\), is \(R'\)-bimodular, and its range commutes with each subfactor, hence with \(R\). This gives an actual minimizer. Compare the distinct [properly infinite domain argument](07-properly-infinite-retraction-norm.md), which uses isometries in the commutant of the range rather than diffuseness of the range.
