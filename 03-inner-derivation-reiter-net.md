# Recovering a Reiter net from one inner derivation

**Work in progress, November 2026.** A supporting note toward a possible future paper, not a submitted or peer-reviewed paper. No priority claim is made.

Let a second-countable locally compact Hausdorff group \(G\) act continuously on a nonempty compact Hausdorff space \(X\). Use the complex row algebra \(A=C(X,L^1(G))\) with twisted convolution and left Haar measure, and write \(P=C(X)\), \(\gamma(a)(x)=\int_G a_x(t)\,dt\), \(K=\ker\gamma\). The left action on \(P\) is \(A_a p(x)=\int a_x(t)p(t^{-1}x)\,dt\), so \(\gamma(a*b)=A_a\gamma(b)\). Write \(L_a\) for left convolution. Put
$$
K^\sharp=\overline{\operatorname{span}}\{\phi\circ L_b:\phi\in K^*,\ b\in A\}\subset K^*.
$$
Take a bounded linear section \(J\) of \(\gamma\), for example \(Jp\) with rows \(p(x)h\) for a fixed probability density \(h\). The coefficient is \(\mathcal B(P,(K^\sharp)^*)\), with left action dual to \(\eta\mapsto\eta\circ L_a\) on the target and right action by precomposition with \(A_b\). Define
$$
D_J^\sharp(a)(p)(\eta)=\eta\big(a*Jp-J(A_a p)\big).
$$
The difference is in \(K\); expanding the two terms shows the derivation identity. The following implication uses only innerness of this one derivation.

**From innerness to a section.** Suppose \(D_J^\sharp(a)=a\cdot S-S\cdot a\). For \(b\in A\) and \(\Phi\in A^*\), set
$$
B_b(p)(\Phi)=\Phi(b*Jp)-S(p)((\Phi|_K)\circ L_b).
$$
Testing innerness against \((\Phi|_K)\circ L_b\) gives \(B_b(A_a p)=B_{b*a}(p)\). Replacing \(\Phi\) by \(\Phi\circ L_a\) gives \(L_a^{**}B_b=B_{a*b}\). Testing against \(\ell\circ\gamma\), \(\ell\in P^*\), gives \(\gamma^{**}B_b(p)=\kappa_P(A_b p)\), with \(\kappa_P:P\to P^{**}\) canonical. The maps satisfy \(\|B_b\|\le(\|J\|+\|S\|)\|b\|\).

Let \((e_i)\) be the two-sided contractive approximate identity of constant probability-density rows supported near the identity. Since \(A_{e_i}p\to p\), the span of the \(A_a p\) is dense in \(P\). In fact every \(p\) can be written \(p=A_{Jp}1\), so \(\Sigma(p)=B_{Jp}(1)\). On this span the norm limit \(\Sigma(p)=\lim_i B_{e_i}(p)\) follows from \(e_i*a\to a\), and the uniform bound extends it to all of \(P\). Thus \(\gamma^{**}\Sigma=\kappa_P\) and \(L_a^{**}\Sigma(p)=\Sigma(A_a p)\). If \(U_t\) is the left translation multiplier on \(A\) and \(V_t p(x)=p(t^{-1}x)\), then \(U_tL_a=L_{U_ta}\) and \(A_{U_t a}=V_tA_a\) give \(U_t^{**}\Sigma=\Sigma V_t\), first on the same dense span. In particular \(m=\Sigma(1)\) is invariant and has mass one, but is not necessarily positive.

**Reiter normalization.** Approximate \(m\) weak-star by bounded rows using Goldstine and correct their mass with \(J\). Smooth the corrected rows by left convolution with one fixed compactly supported probability density. The translation defects tend weakly to zero and are equicontinuous in \(t\) in the row norm, by norm continuity of the translates of the smoothing density. For each compact group test, a finite cover and convexification therefore make the defects small in norm, uniformly on the test. Taking absolute values and normalizing each row changes defects by at most a factor of two, since every row before this operation has integral one. The resulting continuous probability fields are a Reiter net for the action.

**Verification.** The construction and Leibniz identity of \(D_J^\sharp\), and the identities \(B_b(A_a p)=B_{b*a}(p)\), \(\gamma^{**}B_b(p)=\kappa_P(A_b p)\), were checked in Lean 4.27. Lean 4.27 also checks the norm limit, the augmentation identity and the multiplier covariance for the actual section, including invariance of its value at the constant one. The positivity and Reiter normalization steps above were checked in writing. This note does not claim an end-to-end Lean formalization, or the opposite implication. For the continuous Reiter criterion see [Anantharaman-Delaroche (2002; preprint 2000), Proposition 2.2](https://arxiv.org/abs/math/0005014).
