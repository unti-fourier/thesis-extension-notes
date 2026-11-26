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

## Passing to a continuous simplex

Let \(h_d\) be the infimum of \(P_1(E)/|E|\) over positive-volume finite-perimeter sets \(E\subset \Sigma_d=\{x_i\ge0:\sum_i x_i\le1\}\), with \(P_1(E)=\sum_i |D_i\mathbf1_E|(\mathbb R^d)\). This counts the entire perimeter, including faces on the simplex boundary. Then for every \(R\ge0\)
\[
 \frac{h_d}{d(R+d)}\le \Delta_d(R)\le \frac{h_d}{d(R+1)}.
\]
In particular \(R\Delta_d(R)\to h_d/d\). For \(d=2\) this and the exact formula above give \(h_2=4+2\sqrt2\).

For the lower bound put a unit cube at each vertex of a set in \(T_{d,R}\), extending in the positive coordinate directions. The resulting volume is its cardinality and its anisotropic perimeter is exactly the edge boundary. The union lies in \((R+d)\Sigma_d\). For the upper bound shrink \(E\) about the simplex barycenter by \(1-\delta\) and then dilate by \(R+1\), giving \(A\) strictly inside \((R+1)\Sigma_d\). For \(u\in[0,1)^d\) sample the lattice set \(F_u=\{n:n+u\in A\}\). Every sampled integer coordinate is nonnegative and every coordinate sum is an integer less than \(R+1\), so \(F_u\subset T_{d,R}\). Integrating over \(u\), the cardinality is \(|A|\) and the direction-\(i\) edge count is \(\int_{\mathbb R^d}|\mathbf1_A(x+e_i)-\mathbf1_A(x)|\,dx\), at most \(|D_i\mathbf1_A|(\mathbb R^d)\). The last bound follows by integrating the fundamental theorem of calculus for smooth approximants obtained by mollification, then taking the \(L^1\) limit. The finite Cheeger bound holds for every sampled set, including the empty one with both counts zero. Therefore \(d\Delta_d(R)|A|\le P_1(A)\); let \(\delta\) decrease to zero and take the infimum over \(E\). The comparison is checked in writing, not in Lean.

## Clipped cubes are not optimal in the continuous three-simplex

In \(\Sigma_3\), intersect \([0,1/2]^3\) with the additional inequalities \(x_i+x_j\le5/6\) for every pair. The resulting \(E\) has \(P_1(E)/|E|=612/43\), strictly better than every \(C_t=[0,t]^3\cap\Sigma_3\). Indeed, all coordinate fibers of these downward closed symmetric polytopes are intervals; therefore \(P_1\) is six times the area of a single coordinate projection. The projection of \(E\) removes a right triangle of leg \(1/6\) from the half-unit square and has area \(17/72\). Each removed volume is \(\int_0^{1/6}s^2\,ds=1/648\) (set \(s=1-x_i-x_j\)). The three cuts are disjoint under the half-unit caps and the simplex inequality. Hence \(|E|=5/48-3/648=43/432\).

For the clipped cube, maximize the volume-to-projection ratio \(V/A\). It is \(t\) for \(0<t\le1/3\); for \(1/3\le t\le1/2\) it is \((1-u^3/6)/(3-u)\), \(u=3-1/t\). Its derivative has the sign of \(g(u)=2u^3-9u^2+6\), strictly decreasing on \((0,1)\), and its maximum at the unique zero \(u_*\) equals \(u_*^2/2\). For \(1/2\le t\le1\), writing \(v=1-t\), the ratio is \((1-3v^3)/(3(1-2v^2))\le5/12\), since \((1-2v)(1+2v-6v^2)\ge0\); above \(t=1\) it is unchanged. Thus the best clipped-cube perimeter ratio is \(12/u_*^2\). Since \(g(11/12)=-19/864<0\), it exceeds \(1728/121>612/43\). In particular the three-factor limiting constant \(h_3/3\) is at most \(204/43\); its exact value is not established here. This comparison is checked in writing, not in Lean.
