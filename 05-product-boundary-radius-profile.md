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

For the clipped cube, maximize the volume-to-projection ratio \(V/A\). It is \(t\) for \(0<t\le1/3\); for \(1/3\le t\le1/2\) it is \((1-u^3/6)/(3-u)\), \(u=3-1/t\). Its derivative has the sign of \(g(u)=2u^3-9u^2+6\), strictly decreasing on \((0,1)\), and its maximum at the unique zero \(u_*\) equals \(u_*^2/2\). For \(1/2\le t\le1\), writing \(v=1-t\), the ratio is \((1-3v^3)/(3(1-2v^2))\le5/12\), since \((1-2v)(1+2v-6v^2)\ge0\); above \(t=1\) it is unchanged. Thus the best clipped-cube perimeter ratio is \(12/u_*^2\). Since \(g(11/12)=-19/864<0\), it exceeds \(1728/121>612/43\). In particular the three-factor limiting constant \(h_3/3\) is at most \(204/43\); the next section computes its exact value. This comparison is checked in writing, not in Lean.

## Exact three-factor continuum constant

Let \(c_*\) be the unique root in \((0,1/6)\) of
\[
Q(c)=1-9c+9c^2+(15+12\sqrt2)c^3.
\]
Then \(h_3=2/c_*\), and the limiting three-factor constant is
\(\lim_{R\to\infty}R\Delta_3(R)=2/(3c_*)\simeq 4.73144905\).
A minimizing set is \(\Sigma_3\) cut by \(x_i\le 1-(2+\sqrt2)c_*\) and \(x_i+x_j\le1-c_*\). This is a global bound for finite-perimeter subsets, not just an optimization within this family. It does not classify all minimizing sets.

For a symmetric downward-closed union of grid cubes inside \(\Sigma_3\), write its coordinate projection in the sector \(x\ge y\) as \(0\le y\le t(x)\). Put \(B=\int t(x)\,dx\) and \(I=\int\int_0^{t(x)}\min(y,1-x-y)\,dy\,dx\). Then \(P_1=12B\) by slicing, and \(|E|\le6I\) by restricting to the sector \(x\ge y\ge z\) and multiplying by six.

For \(0<c<1/6\) set \(a=1-(2+\sqrt2)c,\ b=1-c,\ s=b/2\), and let \(t_c=\min(x,b-x)\) up to \(a\) and zero after \(a\). This is the projection of the stated two-cut candidate. To bound \(I-cB\), let \(\eta\) be the supremum of the diagonal coordinates \((y,y)\) in the projection. Downward closure gives \(t(x)\le\eta\) and \(t(x)=x\) for \(x<\eta\). If \(\eta\le2c\), the estimate \(\int_0^t(\min(y,1-x-y)-c)\,dy\le t^2/2-ct\le0\) suffices. Otherwise \(t=t_c\) for \(x<2c\); for each \(x\ge2c\), the integral is maximized at \(t_c(x)\). Indeed, for \(2c\le x\le1/3\), compare the endpoints of the quadratic \(t^2/2-ct\). For \(1/3\le x\le s\), compare \(t=0\) with \(t=x\), since the integrand changes sign at most once from negative to positive on the allowed interval. The value at \(t=x\) is a concave quadratic in \(x\) on this range and positive at both endpoints. For \(x\ge s\), with \(L=1-x\), the integrand is nonpositive when \(L\le2c\); otherwise compare \(t=0\) with \(t=L-c\), whose value is \((L-(2+\sqrt2)c)(L-(2-\sqrt2)c)/4\). For \(L\ge2c\) this is nonnegative exactly up to \(x=a\).

Writing \(\Phi(c)\) for the value of \(I-cB\) at \(t_c\), the bound is thus \(I-cB\le\max(0,\Phi(c))\). The moving boundary at \(x=s\) cancels, the endpoint at \(x=a\) has zero integral, and the moving upper limit for \(s\le x\le a\) has zero integrand. Hence
\[
\Phi'(c)=-\int t_c=-\bigl(1/4-c/2-(5/4+\sqrt2)c^2\bigr),\quad
\Phi(0)=1/36,\quad 36\Phi(c)=Q(c).
\]
In particular the root exists and is unique by strict decrease and opposite endpoint signs. At \(c=c_*\) all such cube unions satisfy \(P_1\ge(2/c_*)|E|\). For the candidate, the third coordinate is free to run up to \(\min(y,1-x-y)\) because both extra cuts are tested on the largest coordinates, giving equality.

For the global lower bound, compress a lattice minimizing set along each coordinate to initial intervals. This preserves cardinality, decreases edge boundary, and preserves downward closure in any previously compressed axis. Average the resulting indicator over coordinate permutations and use discrete layer cake; some nonempty level set remains minimizing and is symmetric and downward closed. Scaling its union of unit cubes by \(1/(R+3)\) gives one of the sets considered above. Thus \(3(R+3)\Delta_3(R)\ge 2/c_*\). The continuum comparison already proved above now yields \(h_3\ge2/c_*\). Also \(Q(9/64)>0\) (use \(\sqrt2>7/5\)), so \(2/c_*<128/9<612/43\), strictly improving the earlier rational candidate without numerical rounding.

The calculation and reduction were checked in writing, not in Lean. [Kawohl and Novaga (2008), Theorem 5.1](https://cvgmt.sns.it/document/1248/#page=8) treats bounded planar convex domains, not this three-dimensional case. Priority for this exact simplex value remains unverified.

## Exact finite three-factor profile

Write \(H_R=3\Delta_3(R)\) for the finite edge Cheeger constant. It can be computed in \(O((R+1)^2)\) integer arithmetic operations. Compress and symmetrize as above, and let \(P\) be the common coordinate projection of a minimizing downset. The boundary is \(6|P|\), so keep \(P\) fixed and fill all triples whose three coordinate pairs belong to \(P\). This keeps the projection (append a zero to any pair) and only improves the ratio. To count these triples, take \(x\ge y\ge z\); once \((x,y)\) belongs to the projection, the third coordinate runs from zero through \(m=\min(y,R-x-y)\).

For a pair \(x\ge y\) let \(p_{xy}=2\) off the diagonal, \(1\) on it, and let \(v_{xy}\) count the allowed triples with all distinct permutations counted once. For \(x>y\), \(v_{xy}=6(m+1)-3\mathbf1_{\{m=y\}}\); for \(x=y\), \(v_{xy}=3(m+1)-2\mathbf1_{\{m=y\}}\). In the half-projection the ratio is \(6\sum p_{xy}/\sum v_{xy}\). It suffices to try
\[
\begin{gathered}
\lceil(R+1)c_*\rceil\le j\le\lceil(R+3)c_*\rceil,\qquad b=R+1-j,\\
0\le k\le\lfloor R/2\rfloor,\qquad k\le a\le\max(k,b),\\
\{0\le y\le x\le k\}\ \cup\
\{k<x\le a,\ 0\le y\le\min(k,b-x)\}.
\end{gathered}
\]
There are at most two values of \(j\). The first triangle is forced by the last diagonal point \((k,k)\); do not apply the extra cut to that forced part.

Indeed let \(c_R=2/H_R\) and, for a trial \(c>0\), maximize \(\sum(v_{xy}/3-cp_{xy})\) at fixed \(k\). Above the forced triangle the objective for row \(x\) is twice the sum of \(\min(y+1/2,R-x+1-y)-c\) over its initial interval. With \(b=R+1-\lceil c\rceil\), the summands are first negative then nonnegative through \(\min(k,b-x)\), with any later admissible summands strictly negative. Compare the entire sum through this endpoint with the empty row. The largest maximizing endpoints decrease with \(x\), since allowed endpoints decrease and each shared summand is nonincreasing with \(x\); thus the separately chosen rows give an allowable downset. At \(c=c_R\) the maximum is zero, and \(c_R\) lies between \((R+1)c_*\) and \((R+3)c_*\) by the continuum comparison. This proves the stated candidate list. The row weights are sums of at most two arithmetic progressions. Increment \(k\) to accumulate the forced triangles and increment \(a\) to accumulate extra rows; this gives the quadratic operation count. The two ceilings can be decided exactly by signs of \(Q\) at rational bounds.

At \(R=6\), \((k,a,b)=(2,3,5)\) gives projection size \(15\) and volume \(51\), so \(H_6/3=10/17\). At \(c_R=17/15\), row \(x=4\) has positive last summand but negative total; it remains empty. Rounding both continuous caps independently to the nearest integer already fails at \(R=4\): \((2,3)\) yields \(4/5\), while the exact value is \(18/23\), obtained by \((2,4)\). The finite formula was checked in writing and compared on \(0\le R\le8\) with direct enumeration of all symmetric downward-closed projections. No Lean verification is claimed.

## Projection formula in all dimensions

Write \(m=d-1\) and \(w(u)=\min(\min_i u_i,1-\sum_i u_i)\) on \(\Sigma_m\). Then for \(d\ge2\)
\[
 \frac2{h_d}=\max_{\substack{P\subseteq\Sigma_m\ \mathrm{downset}\\|P|>0}}
       |P|^{-1}\int_P w(u)\,du.
\]
Here a downset contains every nonnegative vector coordinatewise below any of its points. The maximum is attained by a symmetric closed downset.

To verify the reduction, compress every coordinate fiber of a finite-perimeter competitor to an initial interval of equal length. Its variation in that coordinate does not increase by slicing. In every other direction, use that the symmetric difference of two initial intervals is their length difference and apply this inequality to translation difference quotients. Compression preserves previously imposed coordinate monotonicity. Averaging the resulting indicator over permutations and applying coarea and layer cake gives a symmetric downset of no larger ratio. Its positive-length coordinate projections agree up to identification; call this projection \(P\). Every fiber is an initial interval, so the perimeter is \(2d|P|\). Keeping \(P\) fixed, fill all points of \(\Sigma_d\) whose largest \(m\) coordinates belong to \(P\). Any other coordinate projection of such a point lies in \(P\) by downward closure. The smallest coordinate ranges from zero to \(w(u)\) when the other coordinates are \(u\); almost every \(u\in P\) has \(w(u)>0\). Thus the projection is unchanged up to null sets and the filled volume is \(d\int_P w\). Symmetrizing an arbitrary downset \(P\) via averaging and thresholding preserves or improves some level's average because \(w\) is symmetric. For attainment, take closures, which only change a null boundary, and a Hausdorff-convergent maximizing subsequence. A fixed positive lower bound on the average forces every member to contain a fixed positive cube, since \(w(u)\le\min_i u_i\). On the interior and exterior of the limit, Hausdorff convergence and downward closure give pointwise convergence away from its null boundary. Hence both the volume and the integral converge.

For the finite lattice, use the same saturation, counting ties. If \(\alpha\) is a nonincreasing \(m\)-tuple in the half-projection, let \(n_t\) be its multiplicity of \(t\), \(N_\alpha=m!/\prod_t n_t!\), and \(L_\alpha=\min(\alpha_m,R-\sum_i\alpha_i)\). Its projection weight is \(N_\alpha\) and its volume weight is \(dN_\alpha\sum_{t=0}^{L_\alpha}(1+n_t)^{-1}\). This gives the finite weighted-average formula by taking the weighted sums and then twice the reciprocal, with the maximum taken over nonempty downsets in the ordered projection.

In dimension four, the independent-row maximization used in dimension three does not carry over merely by fixing the diagonal point. In fact let \(c=2/h_4\). The full simplex projection has weight average \(1/16\) (integrate the level volumes of \(w\)); slicing a symmetric four-dimensional competitor gives \((3/4)P_1(E)\ge h_3|E|\). Hence \(1/16\le c\le (3/4)(2/h_3)<3/28\). The diagonal width \(\eta\) of an optimal symmetric projection satisfies \(\eta>2c\): all last-coordinate lengths \(T\) are at most \(\eta\) and \(w\le z\), with strict integral inequality \(\int T^2<\eta\int T\) on the forced triangle. For \(x=7/20\) the row contributions at \(y_-=1/16\) and \(y_+=3/14\) are \(T^2/2-cT\) on \(0\le T\le\min(y,\eta)\), since \(x+3y_+<1\). The independently optimal row is empty at \(y_-\) and positive at \(y_+\); this violates downward closure, and the strict inequalities persist on neighborhoods. This is an obstruction to that proof method, not a classification of minimizers or a value for \(h_4\).

These reductions were checked in writing, not in Lean; priority is unverified.

## Integer min-cut certification for fixed dimension

In the ordered projection above, denote each projection weight by \(b_\alpha\) and its integer volume weight by \(a_\alpha\). For a nonempty downset \(D\), write \(A(D)=\sum_Da_\alpha,\ B(D)=\sum_Db_\alpha\). With \(\rho=\max_D A(D)/B(D)\) the exact edge Cheeger ratio is \(2d/\rho\) and the product profile is \(2/\rho\).

At a rational trial \(p/q\), give vertex \(\alpha\) weight \(c_\alpha=q a_\alpha-p b_\alpha\). Let \(S^+=\sum(c_\alpha)_+\). Add arcs from the source to positive-weight vertices and from negative-weight vertices to the sink, with capacities their absolute weights. Give each downhill order arc \(\alpha\to\alpha-e_i\) capacity \(S^++1\) when that decrement preserves the ordered tuple. These arcs generate the componentwise order: to reach a smaller tuple, repeatedly decrement the rightmost coordinate still greater than its target. The empty cut has capacity \(S^+\), so a minimum cut crosses no order arc. With \(D\) its source side (apart from the source), its capacity is \(S^+-\sum_Dc_\alpha\). Consequently \(\rho>p/q\) precisely when the min-cut is less than \(S^+\). At the optimum, a nonempty downset with \(qA(D)=pB(D)\) and an integer flow of value \(S^+\) certify both bounds without solving the optimization again.

The denominators of all attained ratios are at most \(B_{\max}=\binom{R+d-1}{d-1}\), so distinct ratios differ by at least \(1/B_{\max}^2\). Binary search on the grid of denominator \(B_{\max}^2+1\) in \([0,R+1]\), using strict tests and retaining the latest feasible witness, eventually leaves a bracket narrower than that separation; the witness in the bracket has the exact optimal ratio. This takes \(O_d(\log(R+2))\) min-cuts on graphs with \(O_d((R+1)^{d-1})\) vertices and arcs and \(O_d(\log(R+2))\)-bit capacities. Edmonds–Karp gives \(O_d((R+1)^{3(d-1)}\log(R+2))\) arithmetic operations as one elementary bound. Neither all downsets nor all candidate fractions need be enumerated.

For \((d,R)=(4,4)\), the downset generated by \(211\) gives \(A=44,B=20\). At \(p/q=11/5\) the only positive weights are \(c_{111}=14,c_{211}=27\). Send their full source flow along order arcs \(211\to111:8,\ 211\to210:19,\ 111\to110:22,\ 110\to100:19,\ 210\to200:13,\ 100\to000:6\), and out to the sink from \(000,100,200,110,210\) in amounts \(6,13,13,3,6\). Every capacity and conservation equality is satisfied, so the flow value \(41\) certifies \(H_{4,4}=40/11\), \(\Delta_4(4)=10/11\). This agrees with direct enumeration of the 43 nonempty downsets. The min-cut calculation also agrees with the three-dimensional section formula through \(R=8\).

The maximum-closure method is due to [Picard (1976), §§4–5](https://doi.org/10.1287/mnsc.22.11.1268); min-cut for fractional binary optimization has precedent in [Picard and Queyranne (1982)](https://doi.org/10.1002/net.3230120206). The integer orbit weights, denominator bound and reconstruction above are specific to the simplex application. Written and small-case computational checks only, not Lean verification.

## Analytic four-dimensional bounds

The four-dimensional constant satisfies
\[
 \frac{116}{5}<\frac8{1-\exp(-6/h_3)}<h_4\le\frac{67032000}{2793629}<24 .
\]
In a symmetric minimizing downset, let \(V\) be the volume, \(P\) one coordinate projection, \(B=|P|\), and \(\ell(y)\) the fiber length over \(y\in P\). At height \(t\) the section lies in \((1-t)\Sigma_3\). Slicing the first three directional perimeters and using Jensen gives
\[
6B\ge h_3\int_0^1\frac{|E_t|}{1-t}\,dt
=h_3\int_P-\log(1-\ell)\,dy
\ge-h_3 B\log(1-V/B).
\]
The ratio is \(8B/V\). Equality in Jensen forces the fibers to have a common length \(s\); by symmetry the indicator on \([0,s]^4\) is independent of each coordinate in turn and therefore constant a.e. This would be a cube, with ratio at least \(32\), excluded by the following trial set. The strict rational lower estimate follows from \(c_*=2/h_3<31/220\) by the sign of \(Q(31/220)\) (use \(\sqrt2<99/70\)), and \(\log(29/19)>2(z+z^3/3+z^5/5)>93/220\) for \(z=5/24\).

For a rational upper certificate, scale by \(49\) and bound the sums of the largest \(1,2,3,4\) coordinates by \(20,35,45,49\), respectively. With only the coordinate caps and total-sum cap, the projection volume and the four-dimensional volume are \(46669/6\) and \(991681/8\) by inclusion–exclusion. The three-coordinate cuts remove \(1022/3\) and \(9008/3\), respectively: the distinct triple cuts do not overlap, and for total of the triple \(49-u\) use density \((11+u)^2/2\) on \(0\le u\le4\); the fourth variable contributes length \(u\). After these cuts the pair violations are disjoint as well. For pair sum \(40-v\), \(0\le v\le5\), use density \(v\), remaining individual caps \(5+v\), and remaining pair cap \(9+v\). The removals are \(3\int_0^5 v(5+v)\,dv=625/2\) and \(6\int_0^5 v[(5+v)^2-(1+v)^2/2]\,dv=18225/4\). The final scaled volumes are \(7125\) and \(2793629/24\); the ratio is the displayed rational bound after rescaling. An independent rational triangulation check gives the same volumes.

For every merely clipped cube \([0,a]^4\cap\Sigma_4\), its unscaled volumes obey \(B_a>3V_a\). For \(0<a\le1/3\) use \(B_a=a^3\), \(V_a\le a^4\) and strict volume loss at \(a=1/3\). For \(1/3\le a\le1/2\), inclusion–exclusion gives \(24(B_a-3V_a)=(1-t)^4/27+t^3(1-t)/2+t^4/4\), \(t=6a-2\). For \(1/2\le a\le1\) it gives \(1-12(1-a)^3a\ge1/4\); \(a\ge1\) gives the whole simplex. Thus the three-cut set strictly improves the entire clipped cube family. The exact value of \(h_4\) remains open in this note. Written and rational-arithmetic checks only, not Lean.
