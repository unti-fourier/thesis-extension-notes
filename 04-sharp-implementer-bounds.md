# Sharp implementer bounds for topologically amenable actions of locally compact groups

**Work in progress, November 2026.** This is a note toward a possible future paper, not a submission, a peer-reviewed publication, or a publication-list entry. No priority claim is made.

Let a second-countable locally compact Hausdorff group $G$ act continuously and topologically amenably on a nonempty compact Hausdorff space $X$. The group itself may be nonamenable. Give the complex algebra $A=C(X,L^1(G))$ its twisted convolution and row norm $\|a\|=\sup_{x\in X}\int_G|a(x,t)|\,dt$, using left Haar measure.

Let $F=E^\ast$ carry the adjoint actions of a contractive $A$-bimodule $E$. The coefficient hypothesis is right type (M) on $E_0=\overline{\operatorname{span}}\,A\cdot E\cdot A$. This means that its induced $C(X)$-action satisfies $\sum_j\|\xi\cdot p_j\|\le\|\xi\|\,\|\sum_j p_j\|_\infty$ for $\xi\in E_0$ and finite families $p_j\ge0$ in $C(X)$.

**Theorem.** Every bounded derivation $D:A\to F$ is inner. For each fixed action, the least uniform constant $K$ for which one can choose an implementer $z\in F$ satisfying
$$
D(a)=a\cdot z-z\cdot a,\qquad \|z\|\le K\|D\|
$$
is **2** over the stated coefficient class. It is **1** over either of the two subclasses defined by left essentiality or right essentiality of the predual, with the opposite side unrestricted. Here left and right essentiality mean $\overline{\operatorname{span}}\,A\cdot E=E$ and $\overline{\operatorname{span}}\,E\cdot A=E$, respectively. The bound is also at most **1** on their intersection; the examples below do not establish sharpness on that intersection. If the action has an invariant probability measure, no type (M) assumption is needed for these bounds.

### Proof sketch: why the upper bound changes

Suppose first that $E$ is left essential. For $c\in A$ set $(J_c y)(\xi)=y(\xi\cdot c)$ for $y\in E_0^\ast$ and $\xi\in E$. Each $J_c$ is weak-star continuous. Averaging the affine orbit associated to the restricted derivation first over phases in $C(X)$ and then against an action Reiter field gives a single $y$ with
$$
\|J_c y+D(c)\|\le\|D\|\,\|c\|\qquad(c\in A).
$$
For nonamenable $G$, the proof keeps each row of a Reiter field $r$ at mass one while making the column mass $x\mapsto\int_G r_t(tx)\,dt$ uniformly small. Finite quadratures approximate the column mass uniformly and the coefficient average weak-star. Pieces with disjoint sources and disjoint targets admit contractive partial inverses, which give the joint estimate above. The map $T(c)=J_c y+D(c)$ then satisfies $T(ab)=T(a)\cdot b$. For a contractive two-sided approximate identity $(e_i)$, the negative of a weak-star cluster point of $T(e_i)$ implements $D$.

If $E$ is right essential, use $(K_c y)(\xi)=y(c\cdot\xi)$ instead. The estimate is
$
\|K_c y-D(c)\|\le \|D\|\,\|c\|\qquad(c\in A).
$
This does not follow just by reversing the left-essential proof: the type (M) assumption is still on the right action on $E_0$. In the finite Reiter quadrature, pairing the two factors with prescribed product cancels the contribution from the implementer on $E_0$. The quadrature and row-mass errors tend to zero on each finite family of tests before the norm bound is taken. For $T(c)=K_c y-D(c)$ the core implementer identity gives $T(ab)=a\cdot T(b)$. Thus for any weak-star cluster point $w$ of $T(e_i)$ we have $a\cdot w=T(a)$ and $w\cdot a=K_a y$, so $-w$ implements $D$ with norm at most $\|D\|$.

If the action has an invariant probability measure, integrating an action Reiter field against it produces scalar Reiter functions for $G$. In that case scalar Reiter averaging gives the estimates without using type (M).

For general $E$, apply the left essential bound to $D_L(a)=D(a)|_{E_L}$, where $E_L=\overline{\operatorname{span}}\,A\cdot E$. For a common subnet of a contractive approximate identity $(e_j)$, the pointwise weak-star limit of $\phi\mapsto [\xi\mapsto\phi(e_j\cdot\xi)]$ gives a contractive bimodule section $I:E_L^\ast\to E^\ast$, which lifts the implementer. The remaining derivation has the form $a\mapsto a\cdot t$, where $t$ is the weak-star limit of $D(e_j)$ along that same subnet and $a\cdot t\cdot b=0$. A weak-star cluster point of $e_j\cdot t$ implements this remainder at cost at most $\|D\|$.

### Examples giving equality

- **Constant 2.** Give the weak-star closed graph $\{(s,r,s-r):s,r\in A^{\ast\ast}\}$ the maximum norm. In pair coordinates let $a\cdot(s,r)=(a\cdot s,0)$ and $(s,r)\cdot a=(0,r\cdot a)$. The derivation $D(a)=(a,a)$ has norm one. Every implementer satisfies $a\cdot(s-r)\cdot b=2ab$. Taking $a=e_i$ and $\|b\|=1$ forces $\|s-r\|\ge2$. The pair $(e,-e)$ attains two for any weak-star cluster point $e$ of $(e_i)$ in $A^{\ast\ast}$.
- **Constant 1.** Take $E=A$ with regular left action and zero right action. For $\ell\in A^\ast$ of norm one, $D(a)=\ell\cdot a$ has norm one since $\ell\cdot e_i\to\ell$ weak-star. Its unique implementer is $-\ell$ by density of the span of products in $A$.

For the right-essential constant **1**, use the regular right action and zero left action on $E=A$, and $D(a)=a\cdot\ell$. The identical approximate-identity argument gives norm one and unique implementer $\ell$.

All these examples have $E_0=0$ and hence satisfy the coefficient hypothesis.

**Known inputs.** Claire Anantharaman-Delaroche (2002; preprint 2000), Proposition 2.2(1),(3) and Example 2.7(1), gives the continuous Reiter characterization and its scalar case. Nicolas Monod (2011), Proposition 2(i), records type (M)/(C) duality for real modules. Pairing with $E_0$ gives the required left type (C) estimate on $E_0^\ast$ over the complex scalars. [Anantharaman-Delaroche](https://arxiv.org/abs/math/0005014) · [Monod](https://arxiv.org/abs/1004.0199)

**Proof status.** The locally compact theorem, including the right-essential endpoint, has a written proof and an independent written audit. Related Lean checks cover selected finite identities. The full theorem has not been formalized in Lean.

## Finite-radius implementation and a fixed Schreier coefficient

Let a finitely generated discrete group \(\Gamma\) act on nonempty compact Hausdorff \(X\), and fix a pointed transitive \(\Gamma\)-set \((\Omega,o)\). On \(V=C(X,\ell^1\Omega)\) use the row action of \(A=C(X,\ell^1\Gamma)\) by permutation and translation, and let \(K\) be the mass-zero submodule. Let \(K_R\) be the mass-zero rows supported in \(U_R=B_Ro\). Set \(J_w(f)=fw\) and \(D_\Omega(a)=aJ_{\delta_o}-J_{\delta_o}a\) with values in \(\mathcal L(C(X),K^{**})\), the dual of \(C(X)\widehat\otimes_\pi K^*\). The coefficient has right type (M) by the dual of the row sup-norm inequality and the projective norm. Measure the defect on the standard group generators and require \(T(1_X)\in K_R^{**}\). Then
\[
 \inf_T\max_{s\in S}\|(D_\Omega-\operatorname{ad}T)(\delta_s)\|
 =\inf_{p\in C(X,\operatorname{Prob}(U_R))}
     \max_{s\in S}\sup_{x\in X}\|\lambda_s p_x-p_{sx}\|_1.
\]
For the upper bound use \(T=J_{\delta_o-p}\), which even has range in \(K_R\) and norm at most two. For the lower bound test on \(1_X\). In the finite sup-norm sum of copies of \(K\), let \(L(z)=(\delta_s z-z)_s\) on \(K_R\). Quotient by the closure of its range; the bidual quotient kills \(L^{**}T(1_X)\) and preserves the norm of the image of the target. This gives the lower bound by the original norm distance to \(L(K_R)\). Replace the resulting mass-one rows by their real parts and then by their normalized positive parts. The latter operation is 1-Lipschitz on real mass-one rows: for \(A=\|w^+\|\ge B=\|v^+\|\ge1\) use \(\|w^+/A-v^+/B\|\le(\|w^+-v^+\|+|A-B|)/A\), with \(|A-B|\le\|w^--v^-\|\). This preserves support and commutes with the permutations.

For \(\Omega=\Gamma\) this is the regular Reiter profile. Pushing forward gives a smaller or equal profile for every pointed quotient; the supremum including the regular case gives exactly the regular value. A *fixed* quotient can nevertheless add information. Take \(F_2=\langle u,v\rangle\), \(q:F_2\to Q=C_2*\mathbb Z\) imposing \(q(u)^2=1\), and \(\tau\) interchanging \(u,v\). On the same space \(\partial Q\), use the actions factoring through \(q\) and \(q\circ\tau\), but always let \(\Omega=Q\) act through \(q\). The regular profiles agree at every radius by relabeling. The fixed-quotient profile of the first action is \(2/(R+1)\), while the second is at least \(1/3\) for all \(R\).

For the first value, uniform mass on the first \(R+1\) ray vertices gives the upper bound (compare [Dranishnikov and Januszkiewicz, 1999 preprint, Proposition 1](https://arxiv.org/abs/math/9911245)). For the tree lower bound, choose word lifts of the vertices of the right Cayley tree of \(Q\) by lifting each edge to one generator step. Any field with generator defect \(\varepsilon\) then yields a probability \(\mu_h\) supported in each tree ball of radius \(R\), with neighboring distance at most \(\varepsilon\), by translating \(p_{\sigma(h)^{-1}x_0}\) for fixed \(x_0\). Orient away from an end and move randomly to one of two children. The expected remaining visits to a fixed radius-\(R\) ball define functions \(H_h\) between zero and \(R+1\): from distance \(j\le R\) the bound is \(R-j+1+2\sum_{i=1}^j2^{-i}\), and outside use first entry. They satisfy \(H_h-\mathbb E H_{\mathrm{child}}=\mathbf1_{B(h,R)}\). Pairing with \(\mu_h\) and telescoping, the error per step is at most \((R+1)\varepsilon/2\) since the difference of two probabilities has mass zero. Thus \(\varepsilon\ge2/(R+1)\). For the second action, \(v^2\) and \(uv^2u^{-1}\) fix every point but their images under \(q\) freely generate a rank-two subgroup. The two words and their inverses give total displacement at most \(12\varepsilon\), whereas the four-regular forest's edge boundary, integrated over probability level sets, gives total displacement at least \(4\). This separates the profiles at \(R=6\).

Finally, any nonempty topologically amenable action \(X\) has this fixed-quotient profile no larger than any other nonempty compact action \(Y\). Given a field on \(Y\), transport it to \(X\) by averaging \(p_{gy_0}\) against a regular Reiter field \(m_x(g)\) on \(X\). The support in \(U_R\) remains fixed and the defect increases by at most the defect of \(m\), which can be made arbitrarily small. Hence all topologically amenable actions have the same value for this coefficient at each radius. The separation requires retaining the marked quotient, and does not distinguish two amenable actions. These statements are written checks, not Lean verification.

### Normal quotients: the vanishing defect and quantitative lifting

For \(Q=\Gamma/N\), let \(\delta_Q(X)=\inf_R\Delta_Q(X,R)\). Zero means exactly the existence of continuous common-finite-support, approximately equivariant probability fields on \(Q\) over \(X\). This is relative amenability of the **given action** in the sense of [Ji, Ogle and Ramsey (2012), Definition 4.5 and Proposition 4.6](https://arxiv.org/abs/1109.2821), not an existential condition over all compact actions and not necessarily a field on \(X/N\).

If \(N\curvearrowright X\) is amenable, a specified common-finite-support quotient field \(p\) can be lifted with exact pushforward and arbitrarily small increase in generator defect. Choose a section \(\sigma:Q\to\Gamma\). For the finite set of words \(c(s,t)=\sigma(q(s)t)^{-1}s\sigma(t)\in N\) with \(t\) in the common support and \(s\in S\), choose a Reiter field \(\nu\) for the \(N\)-action with error at most \(\eta\). Then
\[
 P_x=\sum_t p_x(t)\lambda_{\sigma(t)}\nu_{\sigma(t)^{-1}x}
\]
has \(q_*P_x=p_x\). In the \(s\)-translate of each summand use the \(c(s,t)\) Reiter error and then replace the mass by \(p_{sx}(q(s)t)\); adding gives \(d_S^\Gamma(P)\le d_S^Q(p)+\eta\). The reverse inequality follows by pushforward. In particular \(\delta_\Gamma(X)=\delta_Q(X)\) under this hypothesis, and arbitrary \(\Gamma\)-actions satisfy
\[
 \Gamma\curvearrowright X\text{ is amenable}\quad\Longleftrightarrow\quad
 \delta_Q(X)=0\text{ and }N\curvearrowright X\text{ is amenable}.
\]
The other direction restricts the regular Reiter field along an \(N\)-equivariant map \(\Gamma\to N\) on left \(N\)-orbits. For related qualitative lifting see [Ozawa (2006), Proposition 11](https://arxiv.org/abs/math/0501555).

For finite \(N\), uniform probability on each coset gives an exact defect-preserving lift, with \(\Delta_\Gamma(X,R+D_N)\le\Delta_Q(X,R)\le\Delta_\Gamma(X,R)\), \(D_N=\max_{n\in N}|n|_S\). Averaging \(p\) over \(N\) also descends the fixed-radius problem to \(X/N\). For general \(N\) this descent can fail: kill one generator of \(F_3\) to obtain \(F_2\), and act on the end boundary of \(F_3\). The regular boundary fields push to the quotient, but every orbit of the kernel on the boundary is dense. Indeed a conjugate \(rwr^{-1}\) of the killed generator can send a given end into any prescribed initial-word cylinder by extending the word to \(r\) that is not a prefix of that end and ends in a letter other than \(w^{\pm1}\). Thus continuous functions to Hausdorff spaces factoring through \(X/N\) are constant, which cannot give a Reiter field for the nonamenable quotient.

For \(\Gamma=F_2\times\mathbb Z\), \(N=F_2\times\{0\}\) and the one-point action, the quotient profile is \(2/(2R+1)\) by the uniform interval (the variation of any interval-supported probability is at least twice its maximum). The regular limiting defect is one: push to \(F_2\) for the lower bound, and use increasingly large free-group balls times a fixed three-point interval for the upper bound. If \(Q\) is exact, then equality of the two zero conditions for **all** nonempty compact \(X\) is equivalent to amenability of \(N\): for necessity pull back the amenable \(Q\)-action on \(\beta Q\) along \(q\), so \(N\) acts trivially, and use the preceding criterion; see [Ozawa (2000)](https://arxiv.org/abs/math/0002185). Exactness of \(Q\) cannot be dropped in this universal statement: if \(Q\) is nonexact and \(\Gamma=F_2\times Q\), the quotient condition would imply a regular Reiter field for the restricted \(Q\)-action, so both zero conditions are false on every such \(X\). Written check, not Lean.
