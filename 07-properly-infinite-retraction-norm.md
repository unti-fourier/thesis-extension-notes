# The complement norm of a commutant retraction for properly infinite M

**Work in progress.** Written proof checked; not Lean-formalized, a paper, or a priority claim.

Let \(M\subseteq\mathbb B(H)\) be a von Neumann algebra with properly infinite unit \(1_M=I_H\), and let \(Q:\mathbb B(H)\to M'\) be a bounded \(M'\)-bimodule retraction. Then
\[
\|\mathrm{id}_{\mathbb B(H)}-Q\|=1+\|Q\|.
\]
In particular a norm-two complement is possible exactly for a contractive retraction, which is positive. The conclusion is conditional on existence of \(Q\), and no normality of \(Q\) is required. This extends the [infinite-dimensional compact-operator case](07-compacts-minimizing-commutant-projections.md).

Choose a contraction \(a\) with \(\|Q(a)\|>\|Q\|-\varepsilon\). The polar decomposition \(Q(a)=u|Q(a)|\) takes place in \(M'\), so \(x=u^*a\) is a contraction with \(Q(x)=|Q(a)|\). Choose a unit vector \(\xi\) with \(f(x)>\|Q\|-2\varepsilon\), where \(f=\omega_\xi\circ Q\).

Proper infiniteness yields a sequence of isometries \(v_n\in M\) with pairwise orthogonal range projections \(p_n=v_nv_n^*\). Set \(b_n=(1-p_n)x(1-p_n)-p_n\). It is a contraction and \(b_nv_n\xi=-v_n\xi\). Moreover \(f(b_n)\to f(x)\). Indeed, finite sums of the \(p_n\) with coefficients of modulus at most one have norm at most one, so each of the sequences \(f(p_n), f(p_nx), f(xp_n)\) is absolutely summable. For \(f(p_nxp_n)\) the same conclusion follows by bounding the finite block-diagonal sums \(\sum_n c_n p_nxp_n\) by \(\|x\|\) for \(|c_n|\le1\).

Since \(Q(b_n)\) commutes with \(v_n\), its vector entry at \(v_n\xi\) equals \(f(b_n)\). Consequently
\[
\|\mathrm{id}-Q\|\ge |1+f(b_n)|\longrightarrow 1+f(x).
\]
Let \(\varepsilon\) tend to zero and apply the triangle inequality for the other bound. Positivity at norm one follows also from the standard fact that a unital contractive map between unital \(C^*\)-algebras is positive, by composing with states of the codomain.

For an individual \(Q\) the proof only needs the norming vectors above to lie in \(eH\) for a projection \(e\in M\) with infinitely many orthogonal equivalent copies: use partial isometries \(v_n\) with source \(e\). No conclusion about finite von Neumann factors is asserted.
