# Minimizing commutant projections for the compact operators

**Work in progress.** Written verification only; this is not a paper, a Lean formalization, or a priority claim.

Let \(A=\mathcal K(H)\) for an infinite-dimensional complex Hilbert space \(H\), and write its universal representation in the form \(H\otimes K\), with multiplicity space \(K\ne0\). For every bounded bimodule retraction \(Q:\mathbb B(H\otimes K)\to 1\otimes\mathbb B(K)\), where the bimodule actions are by the displayed commutant,
\[
\|I-Q\|=1+\|Q\|.
\]
In particular among these retractions the minimum of \(\|I-Q\|\) is two, and the minimizers are precisely the state slices, not necessarily normal ones. This is a refinement in the type-I factor example of the [universal commutator test note](07-right-g2-nuclearity.md), not a characterization for general \(C^*\)-algebras.

Indeed, the retraction's value on \(x\otimes1\) must commute with \(1\otimes\mathbb B(K)\) and thus is \(\varphi(x)1\) for a bounded functional \(\varphi\) on \(\mathbb B(H)\) with \(\varphi(1)=1\). Multiplying on both sides by rank-one operators on \(K\) determines every matrix coefficient of \(Q(T)\) as the value of \(\varphi\) on the corresponding \(H\)-valued matrix coefficient of \(T\). These coefficients give the usual slice and the operator norm bound \(\|Q\|\le\|\varphi\|\); testing \(x\otimes1\) gives equality. Conversely every such functional defines a retraction by this formula.

Choose a contraction \(x\) with \(\varphi(x)\) real and arbitrarily close to \(\|\varphi\|\). For an infinite sequence of mutually orthogonal rank-one projections \(p_n\) on \(H\), put \(x_n=(1-p_n)x(1-p_n)-p_n\). Each \(x_n\) is a contraction, and \(\varphi(x_n)\to\varphi(x)\). For this last claim, every bounded functional \(\psi\) has \(\sum_n|\psi(p_n)|\le\|\psi\|\), by summing finitely many orthogonal projections with phases. Apply this to \(\varphi\) and to the functionals obtained by multiplying by \(x\) on the left or right. Also \(\| \sum_{n\in J}\lambda_n p_nxp_n\|\le\|x\|\) for finite \(J\) and phases \(\lambda_n\), so \(\varphi(p_nxp_n)\to0\). No normality is needed.

On \(p_nH\otimes K\), the operator \((I-Q)(x_n\otimes1)\) is the scalar \(-1-\varphi(x_n)\). Letting \(n\) increase and then taking \(x\) asymptotically norming gives \(\|I-Q\|\ge 1+\|\varphi\|\); the other inequality is the triangle inequality. A unital functional on a unital \(C^*\)-algebra has norm one exactly when it is a state. For orthogonal unit vectors, the signed slice \((1+t)\omega_{e_1}-t\omega_{e_2}\) instead gives \(2+2t\) for \(t>0\), so nonpositive slices approach but never attain the optimum.
