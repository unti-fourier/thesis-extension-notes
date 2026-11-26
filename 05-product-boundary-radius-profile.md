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

## More factors and the grid Cheeger problem

For the product of \(d\) free-group boundaries with all ranks at least two, use the sum of the standard word lengths and consider generator tests. Then, writing \(T_{d,R}=\{n\in\mathbb Z_{\ge0}^d:\sum_i n_i\le R\}\),
\[
 \Delta_d(R)=\frac1d\min_{\varnothing\ne F\subseteq T_{d,R}}\frac{|\partial_E F|}{|F|},
\]
where the undirected edge boundary is in all of \(\mathbb Z^d\). Iterating the positive ray compression above preserves the sum radius and bounds every transverse difference by its weighted \(\ell^1\) contraction. Conversely any simplex-grid field lifts to the product of rays. The resulting maximum of the grid shift variations is at least their average, whose lower bound is the edge Cheeger ratio divided by \(d\), by layer cake. Averaging the uniform probability of a minimizing set over coordinate permutations yields the reverse inequality by convexity. This last step occurs on the grid, so the free-group ranks need not agree.

A minimizing set may be taken coordinate-symmetric and downward closed. Compress each coordinate fiber to an initial interval. This retains its size and the simplex condition, reduces its own direction's boundary, and does not increase other directions' boundary because \(|A\triangle B|\ge\big||A|-|B|\big|\) for adjacent fibers. Previously obtained downward closure survives by inclusion of the corresponding fibers. Averaging the downward closed indicator over permutations and taking a nonempty level set of minimum ratio now gives a symmetric downward closed minimizer: all positive level-set ratios are at least the optimum, and layer cake gives equality in the aggregate.

For \(d=3,R=6\), the exact value is \(10/17\), while uniform probabilities on clipped cubes have best value \(16/27\). To see the finite certificate, the three plane projections of a symmetric downward closed set agree with a symmetric downward closed \(P\subseteq T_{2,R}\). Every direction's boundary is \(2|P|\). The maximal set with that projection consists of the triples in \(T_{3,R}\) whose three coordinate pairs all lie in \(P\). Each pair in \(P\) appears in a triple with third coordinate \(0\), so the projection really is \(P\). If \(h_i\) are the row sizes of \(P\), its maximal volume is
\[
 B(h)=\sum_{i=0}^R\sum_{0\le j<h_i}\min(h_i,h_j,R+1-i-j).
\]
The admissible profiles are nonincreasing nonnegative integer sequences with \(h_i\le R+1-i\) and \(j<h_i\) iff \(i<h_j\). At \(R=6\), their counts by \(h_0=1,\ldots,7\) are \(1,2,4,8,14,20,20\); the corresponding minima of \(17\sum_i h_i-5B(h)\) are \(12,28,18,0,8,27,46\). These integers can be reproduced by iterating each \(h_i\) from \(0\) to \(\min(7-i,h_{i-1})\) with \(h_{-1}=7\), then filtering on symmetry and nonemptiness. Equality occurs for \(h=(4,4,4,3,0,0,0)\), the projection of the clipped four-by-four-by-four cube with the permutations of \((3,3,0)\) removed. It gives volume \(51\) and projection size \(15\). For the clipped cubes alone the projection sizes and volumes are \((1,1),(4,8),(9,27),(16,54),(22,72),(26,81),(28,84)\), giving the claimed strict comparison. The reduction and integer certificate were checked in writing, not in Lean.
