# A contractive approximate diagonal for a compact pair groupoid

**Work in progress.** Written proof checked; not Lean-formalized and not a priority claim. This is a research note, not a paper or a publication-list entry.

Let \(X\) be a nonempty compact Hausdorff space with a nonatomic full-support Radon probability \(\mu\). On continuous kernels on the pair groupoid \(X\times X\), use convolution over \(\mu\) and the raw \(I\)-norm (the maximum of the supremum of the \(L^1\)-row norms and the supremum of the \(L^1\)-column norms). Its completion has a contractive approximate diagonal, so its ordinary Banach amenability constant is \(1\). This is not a claim about general Haar systems or pair groupoid corners of nontrivial stabilizer bundles.

## Equal-mass continuous weights

Fix a finite collection of kernels to test. Take a finite open cover on which the kernels oscillate uniformly by at most \(\eta\) separately in each variable. Partition \(X\) into Borel sets subordinate to this cover. For large \(N\), assign to each set of positive mass \(a_j\) a positive integer \(n_j\), with sum \(N\), by rounding \(Na_j\) with bounded rounding error. Nonatomicity splits that set into \(n_j\) pieces of mass \(a_j/n_j\). Thus each piece has mass between \((1-\varepsilon/2)/N\) and \((1+\varepsilon/2)/N\). Null sets can be ignored here. By Radon inner regularity choose disjoint compact cores in the pieces, leaving total mass at most \(\varepsilon/(2N)\) outside the cores. Each core is contained in its assigned open set.

Choose cutoffs taking value one on the cores, with pairwise disjoint supports subordinate to their assigned open sets, and distribute the leftover weight by an arbitrary continuous partition subordinate to the original cover. A zero-mass piece of the original Borel partition is not needed as an extra index: the open sets assigned to positive-mass pieces cover a dense union of those pieces, and to ensure a cover of all \(X\) one may first pick a smaller open cover with closures inside the original sets, assign pieces using the smaller sets, and take closures of the positive-mass pieces. Their finite union is all \(X\) by full support. The result is a continuous partition \(v_i\), subordinate to the original cover, with \(N\int v_i\le1+\varepsilon\) and \(N\int v_i^2\ge1-\varepsilon\). For example, an index receives no weight on any other compact core, so its integral is at most the mass of its own piece plus the total missing mass.

Set \(p_i=(v_i-\int v_i)/(1+\varepsilon)+1/N\). The weights are nonnegative, sum to one, integrate to \(1/N\), and differ from \(v_i\) by at most \(2\varepsilon/(1+\varepsilon)\) in pointwise \(\ell^1\). Indeed \(p=(v+\varepsilon q)/(1+\varepsilon)\) for a constant probability vector \(q\). Also \(p_i\ge v_i/(1+\varepsilon)\).

## Transporting finite diagonals

Give \(M_N(\mathbb C)\) the maximum row- and column-sum norm. For \(T(B)(x,y)=N p(x)^{\mathsf T}B p(y)\), exact equal mass gives \(\|T\|\le1\) and \(T(B)*T(C)=T(BGC)\), where \(G=N\int pp^{\mathsf T}\). The matrix \(G\) is symmetric stochastic and its diagonal entries are at least \((1-\varepsilon)/(1+\varepsilon)^2\). Consequently \(\|G-I_N\|\le2(1-(1-\varepsilon)/(1+\varepsilon)^2)\), independently of \(N\).

With \(x_i\) in the open set of weight \(v_i\), put \(B_{ij}=f(x_i,x_j)/N\). Then \(\|B\|\le\|f\|_\infty\), and the interpolation \(T(B)\) approximates each test kernel \(f\) uniformly as \(\eta,\varepsilon\to0\), by subordination for \(v\) and the pointwise \(\ell^1\) estimate for \(p-v\).

Average \(U\otimes U^{-1}\) over the finite signed permutation group. This is a norm-one matrix diagonal \(D\): signs eliminate terms with unequal matched indices, and permutations give \(D=N^{-1}\sum_{i,j}E_{ij}\otimes E_{ji}\). The element \((T\otimes T)D\) has projective norm at most one. On \(T(B)\) its centrality error is at most \(2\|B\|\|G-I_N\|\), by comparison with the exact matrix diagonal identity. Its product is \(T((\operatorname{tr} G/N)I_N)\), since averaging \(UGU^{-1}\) gives a scalar matrix. The twisted product formula shows that this acts as a two-sided approximate identity on the interpolated tests. Density and the uniform bound on the diagonals extend both limits to the completion. The nonzero completion forces any approximate diagonal bound to be at least one.

For the finite-matrix diagonal method, see [Grønbæk, Johnson and Willis (1992 preprint), Proposition 3.2](https://arxiv.org/html/math/9209211#S3).
