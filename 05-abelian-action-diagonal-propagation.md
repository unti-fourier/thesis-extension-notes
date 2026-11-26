# Propagation of approximate diagonals for \(\mathbb Z^d\)-actions

**Research note in progress (2026-11-26).** Direction 5. Written-checked, not Lean-formalized, a paper, a preprint, or a peer-reviewed publication. No priority claim.

Let \(\mathbb Z^d\) act globally on a nonempty compact Hausdorff \(X\). Write \(A\) for the counting-\(I\) completion and \(U_g\) for the constant function \(1\) at group degree \(g\). On finite sums \(a=\sum_g a_g U_g\) the norm is the maximum of \(\sup_x\sum_g|a_g(x)|\) and \(\sup_x\sum_g|a_g(gx)|\). Both group coordinate truncations on \(A\) and multiplication in \(A\) are contractive.

### Box construction

For \(Q_R=[-R,R]^d\cap\mathbb Z^d\), choose a finite tensor \(D\) over \(C(X)\) with multiplication \(1\), projective norm \(1\), and arbitrarily small commutators on the finitely many coefficient functions transported by \(g\in Q_R\). Such \(D\) can be made by averaging \(v\otimes\bar v\) over a large finite exponent box for finitely many unitaries linearly spanning the tested functions; translating an exponent changes only the two boundary faces of the box. Form
\[
 T_R=|Q_R|^{-1}\sum_{g\in Q_R}U_g\cdot D\cdot U_{-g}.
\]
Its two group degrees are supported in \(Q_R\) and \(-Q_R\); each summand before averaging has multiplication \(1\) and norm at most \(1\), so the average has multiplication \(1\) and norm exactly \(1\). The coefficient commutators stay below the chosen tolerance. The overlaps of the translated boxes cancel exactly in the \(U_s\) commutator. Its norm is
\[
 \frac{|(Q_R+s)\triangle Q_R|}{|Q_R|}
 =2\left[1-\prod_{j=1}^d\left(1-\frac{|s_j|}{2R+1}\right)_+\right].
\]
The direct upper bound comes from the symmetric difference, and extraction below proves equality. In particular, the standard generators give \(2/(2R+1)\). The expression is bounded by \(2\|s\|_1/(2R+1)\); the commutator product rule gives propagation \(R=O(\varepsilon^{-1})\) for any fixed finite family of finite-propagation tests. Varying the tests and tolerances gives a norm-one bounded approximate diagonal by density.

### Extraction and sharpness in one dimension

The formula
\[
 \Phi(a\otimes b)_g(x)=a_g(x)b_{-g}((-g)x)
\]
defines a contraction into \(C(X,\ell^1(\mathbb Z^d))\), by taking the range sum of the first factor and bounding the second by its supremum norm. The row sum is \((\pi T)_0\) where \(\pi\) denotes multiplication, and under outer conjugation by \(U_s\) the extracted field is translated in both \(x\) and the group coordinate. For \(T_R\) the extracted field is the constant uniform probability on \(Q_R\), proving equality in the box error above.

For \(d=1\), let the two group supports of a tensor \(T\) be \(F,H\) with \(F\cap(-H)\) in an interval of \(W\) lattice points. Then its extracted field is supported in that same interval. Average it against an invariant probability on \(X\), which exists by Cesàro averaging. This gives a complex sequence \(c\); if \(\|\pi T-1\|_I\le\eta<1\) then \(|\sum c_g|\ge1-\eta\). Translation invariance, the total variation from zero to a coordinate of largest modulus and back, and the support bound yield
\[
 \|U_1T-TU_1\|_\pi\ge \sum_j|c_j-c_{j-1}|
      \ge 2\max_j|c_j|\ge 2(1-\eta)/W.
\]
For multiplication exactly \(1\) this is attained by an interval and the negative interval in the two legs. Thus the least error is \(2/W\) for interval width \(W\), with width counted in lattice points.

The rate for finite-propagation tests is not a rate for arbitrary fixed elements of the completion. For example in \(\ell^1(\mathbb Z)\) put \(a=\sum_{j\ge1}2^{-j}U_{4^j}\). With both legs in \(I=[-R,R]\) and \(R\le4^{j-1}\), the \(j\)-th shifted interval \(I+4^j\) is disjoint from \(I\) and all other shifted intervals. On the two isolated rectangles \((I+4^j)\times I\) and \(I\times(I+4^j)\), the commutator has total mass \(2^{1-j}\|T\|_\pi\) in \(\ell^1(\mathbb Z^2)\). When \(\pi T=1\), tolerance \(2^{-j}\) therefore requires \(R>4^{j-1}\).

Compare [Stokke (2004), Theorem 1.8](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=8) for group-algebra diagonals, and [de Jeu–El Harti–Pinto (2017), Theorem 2.4](https://math.leidenuniv.nl/reports/files/2016-06.pdf#page=5) for qualitative amenability of commutative-coefficient \(\ell^1\) crossed products of amenable groups. The rates above concern the specified counting-\(I\) completion and separate group support in the two legs, not a general propagation theorem for étale groupoids.
