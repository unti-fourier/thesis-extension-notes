# The right C(X) condition on the essential core

**Work in progress.** Written verification only; not a paper, preprint, Lean formalization, or priority claim.

Let a locally compact group act continuously on compact \(X\). Here \(A\) is either the Bochner crossed Banach algebra \(L^1(G,C(X);\alpha)\) or the corresponding row-norm completion, with a two-sided contractive approximate identity \((e_i)\). For a contractive \(A\)-bimodule \(E\), put \(E_0=\overline{\operatorname{span}}(A\cdot E\cdot A)\). Both actions on \(E_0\) are essential.

For \(p\in C(X)\) the right multiplier on the convolution algebra is \((bp)(t,x)=b(t,x)p(t^{-1}x)\). On \(E_0\) the corresponding right multiplier action is determined by
\[
 (a\cdot v\cdot b)\bullet p
 =\lim_i(a\cdot v\cdot b)\cdot(e_i p)
 =a\cdot v\cdot(bp).
\]
Indeed \(b(e_i p)=(be_i)p\), and the multiplier has norm at most \(\|p\|_\infty\) in either algebra. The maps \(z\mapsto z\cdot(e_i p)\) are uniformly bounded, so the limit extends to the closed core. If a right \(C(X)\)-action on \(E\) is compatible in the sense \((v\cdot b)\star p=v\cdot(bp)\), it restricts to this canonical action. In particular the right \(\ell^1\) estimate
\[
 \sum_{j=1}^n\|z\bullet p_j\|\le\Big\|\sum_{j=1}^n p_j\Big\|_\infty\|z\|,
 \qquad p_j\in C(X,[0,1]),
\]
is preserved with constant one. To state a theorem for arbitrary \(E\), it suffices to require the estimate on \(E_0\), where the canonical action is defined. It also suffices to test \(z\) in the dense span defining \(E_0\).

An unrelated commuting \(C(X)\)-action does not suffice. Take \(X=\{0,1\}\), the trivial group, and the regular module \(E=A=C(X)\). The action \(v\star p=p(0)v\) satisfies the estimate and commutes with both \(A\)-actions. But for canonical multiplication the two point indicators and \(z=1\) give left side two and right side one.

Now restrict a bounded derivation \(D:A\to E^*\) to \(E_0^*\). If that derivation is inner, extend its implementer \(t_0\) by Hahn–Banach and subtract the inner derivation of the extension. The residual derivation takes values in \(Y=E_0^\perp\), where \(A\cdot Y\cdot A=0\). The [essential-core correction](03-essential-core-sharp-correction.md) implements the residual inside \(Y\), with norm at most twice its derivation norm. No additional geometricity assumption is needed for this step. Thus the reduction from both actions essential to the condition on the core works separately for each algebra and does not prove the substantive essential-module theorem for either one.

### Why this does not transport a row theorem to the Bochner algebra

For a trivial action of \(\mathbb Z\) on a Cantor space \(X\), write \(A_B=\ell^1(\mathbb Z,C(X))\), let \(\chi(b)=\sum_t b(t)(x_0)\), and take \(E=A_B\) with its Bochner norm. Give it the left regular action and the right scalar action \(v\cdot b=\chi(b)v\). Both actions are unital and contractive, and canonical right \(C(X)\)-multiplication on \(E\) is \(v\bullet p=p(x_0)v\), which satisfies the right \(\ell^1\) estimate. The norm of left multiplication by \(b\) equals \(\|b\|_B\), by testing the unit. For \(N\) disjoint nonempty clopen sets, place their indicators at \(N\) distinct group coordinates. The resulting \(b\) has row norm one and Bochner norm \(N\). The left action consequently has no bounded extension to the row completion. Restriction along \(A_B\to A_{\rm row}\) goes the other way.

The general principle of reducing to the essential part is classical; the statements here concern compatibility with the specific right \(C(X)\) condition, and the failure of a change-of-norm shortcut. See also [Runde (2020), Amenable Banach Algebras](https://doi.org/10.1007/978-3-030-42353-0) for the essential-bimodule reduction in ordinary Banach-algebra amenability.
