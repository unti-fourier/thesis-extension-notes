# Off-diagonal corners detect nonpositive slices

**Work in progress.** Written proof checked; not Lean-formalized and not a priority claim.

For \(A=M_n(\mathbb C)\oplus\mathcal K(H)\), \(n\ge2\) and \(H\) infinite dimensional, represent \(A\) universally on \((\mathbb C^n\otimes K_0)\oplus(H\otimes K_\infty)\). A bounded commutant-bimodule retraction \(Q\) annihilates the off-diagonal blocks and acts by unital functional slices \(\varphi,\psi\) on the two diagonal blocks. Then \(\|I-Q\|=2\) exactly when both slices are states. Importantly, the norm is taken over operators on the full Hilbert space, not only over the two diagonal blocks.

If \(\psi\) is not a state, the infinite diagonal corner already has norm \(1+\|\psi\|>2\), by the [compact-operator calculation](07-compacts-minimizing-commutant-projections.md). If both slices are states, \(Q\) is contractive and this same corner yields equality at two.

Suppose that \(\psi\) is a state and \(\varphi\) is not. Then there is a rank-one projection \(p\) on \(\mathbb C^n\) with \(\alpha=\varphi(p)\notin[0,\infty)\): otherwise the spectral theorem would give positivity on the entire finite algebra. Choose a rank-one projection \(q\) orthogonal to \(p\). On the full space let \(U\) act by \(\overline\alpha/|\alpha|\) on \(p\otimes 1_{K_0}\) and by the identity elsewhere. Fix unit multiplicity vectors in both blocks. Let \(v\) be a unit vector whose finite component is in the direction of \(q\) tensored with the first multiplicity vector, with squared norm \(s\), and whose infinite component has squared norm \(1-s\) in direction \(u\) tensored with the other multiplicity vector. Set \(S=U(I-2|v\rangle\langle v|)\). Then \(S\) is unitary and \(Sv=-v\). Computing the two diagonals of \(S\) gives
\[
\operatorname{Re}\langle Q(S)v,v\rangle
 =1+s(|\alpha|-\operatorname{Re}\alpha)
       -2s^2\operatorname{Re}\varphi(q)
       -2(1-s)^2\psi(|u\rangle\langle u|).
\]
An orthonormal sequence in \(H\) has rank-one projections with state values tending to zero, whether or not the state is normal. Thus for fixed \(s\) one obtains
\[
\|I-Q\|\ge 2+s(|\alpha|-\operatorname{Re}\alpha)
                     -2s^2\operatorname{Re}\varphi(q).
\]
Since the coefficient of \(s\) is positive, taking small positive \(s\) proves strict inequality. This proof uses the mixed corners of \(S\) and makes no claim for general direct sums of infinite-dimensional algebras.
