# The radius profile of a product of two free-group boundaries

**Work in progress, November 2026.** This is a research note, not a submission or peer-reviewed paper. The argument was checked in writing, not in Lean. No priority claim is made.

Let \(F_r\times F_s\), \(r,s\ge2\), act on the product of its two boundaries. Use the union of the standard generators and support \(\{(g,h):|g|+|h|\le R\}\). The optimal maximum generator defect in the range \(\ell^1\) norm is
\[
 \Delta(R)=\min_{1\le m\le R+1}\frac{2m}{m^2-t_m(t_m+1)/2},
 \qquad t_m=(2m-R-2)_+.
\]
An attaining field is uniform over the pairs of ray depths \(0\le i,j<m,\ i+j\le R\). In particular, the full triangle gives \(4/(R+2)\), but \(R=3\) already improves this to \(3/4\) by discarding its two extreme axis vertices. As \(R\to\infty\), \(R\Delta(R)\to 2+\sqrt2\).

## Compression to the ray grid

Fix an end in each Cayley tree and turn a boundary field into a vertex field by translation to these fixed ends. Average successively under both end stabilizers as in the [one-tree argument](05-free-group-boundary-radius-profile.md). The two actions commute, so the resulting field is equivariant under both stabilizers, with each generator defect no larger and no increase in support radius.

For one tree, fix the type in the other tree and write \(f_{ij}\) for the mass per point of a type with \(i\) steps toward the end followed by \(j\) steps away. With \(q\) the number of children, let \(w_0=1\), \(w_j=q^j-q^{j-1}\) for \(j\ge1\). The type multiplicity is \(q^j\) at \(i=0\) and \(w_j\) at \(i\ge1\). Comparing a start with its parent changes the type to \((i-1,j)\) for \(i\ge1\) and to \((0,j+1)\) for \(i=0\). The variation in this slice is
\[
 V_q(f)=\sum_j w_j\sum_{i\ge1}|f_{ij}-f_{i-1,j}|
             +\sum_j q^j|f_{0j}-f_{0,j+1}|.
\]
For \(a^{(j)}=(f_{0j},f_{1j},\dots)\), set \(E(a)=(a_0,a_0,a_1,\dots)\), \(u_0=0\), and \(u_j=q^{j-1}\) for \(j\ge1\). Use the ray mass
\[
 C_q f=\sum_j\big((w_j-u_j)a^{(j)}+u_j E(a^{(j)})\big).
\]
This is positive and mass preserving with the stated multiplicities. It moves a position \(i\) at most to \(i+1\), and does so only if \(j\ge1\), so the radius is preserved. It is also a weighted \(\ell^1\) contraction on differences. The shift variation \(V_+(a)=|a_0|+\sum_{i\ge1}|a_i-a_{i-1}|\) is unchanged under \(E\). Since \(\sum_jw_j|f_{0j}|\le\sum_jq^j|f_{0j}-f_{0,j+1}|\) by telescoping the moduli, \(V_+(C_q f)\le V_q(f)\).

Apply this operation first in one factor and then in the other. The estimate on \(V_+\) controls the compressed direction, and the weighted \(\ell^1\) contraction controls the transverse direction. The resulting probability on the triangular ray grid has both shift defects bounded by the original defects. Conversely any probability on this grid defines a continuous field on the boundary product by using the two rays. For neighbors oriented at the same end, the corresponding ray coordinates differ by a one-step shift, so the two grid shifts give the exact defects.

## Optimizing on the grid

A nonempty level set in the triangle occupying \(a\) columns and \(b\) rows has at least \(2(a+b)\) boundary edges in the full integer grid. Compressing the coordinate values without changing their order shows that its cardinality is at most
\[
 C(a,b)=ab-\tfrac12 t(t+1),\qquad t=(a+b-R-2)_+ .
\]
The average of the two shift variations is half the integral of the level-set edge boundary. The integral of the level-set cardinalities is one. Thus \(\min_{a,b}(a+b)/C(a,b)\) is a lower bound on the maximum variation. For a fixed sum \(a+b\), balance maximizes \(C(a,b)\). For the odd sum case,
\[
 2C(m,m+1)\le C(m,m)+C(m+1,m+1):
\]
the second difference of the rectangle sizes is one and that of the removed triangular sizes is at most one. Hence an odd-sum ratio is no smaller than the better adjacent square ratio. The clipped squares attain the bound because each nonempty row and column is an interval and there are \(m\) of each. This proves the formula. For its asymptotic, in the clipped range \(C(m,m)/m=2R+3-m-(R+1)(R+2)/(2m)\), maximized to leading order at \(m\sim R/\sqrt2\). 
