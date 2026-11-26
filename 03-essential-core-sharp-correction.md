# A sharp correction bound for essential-core reduction

**Work in progress.** Written proof checked; not Lean-formalized and not a priority claim. This is a research note, not a paper or a publication-list entry.

Let \(A\) be a Banach algebra with a contractive two-sided approximate identity \((e_i)\), and \(E\) a contractive Banach \(A\)-bimodule. Let \(E_0=\overline{\operatorname{span}}(A E A)\). Write \(\operatorname{ad}_t(a)=a\cdot t-t\cdot a\). If a bounded derivation \(D:A\to E^*\) is implemented on restriction to \(E_0\) by \(t_0\in E_0^*\), fix any extension \(\widetilde t_0\) and put \(d=D-\operatorname{ad}_{\widetilde t_0}\). There is \(c\in E_0^\perp\) with
\[
d=\operatorname{ad}_c,\qquad \|c\|\le 2\|d\|.
\]
Thus \(\widetilde t_0+c\) implements \(D\) and still restricts to \(t_0\). The constant is optimal, even for each fixed nonzero \(A\) with a contractive two-sided approximate identity. The bound is on the correction for the specified extension, not on the smallest implementer for \(D\).

## Upper bound

Write \(Y=E_0^\perp\); then \(d(A)\subseteq Y\) and \(A\cdot Y\cdot A=0\). Pass to a subnet with \(d(e_i)\to m\) weak*, where \(m\in Y\) and \(\|m\|\le\|d\|\). For \(a,b\in A\),
\[
b\cdot d(ae_i)=(ba)\cdot d(e_i)
\]
by the annihilation identity. Passing to the limit gives \(b\cdot d(a)=(ba)\cdot m\). Expanding \(d(e_i a)\) and taking its limit now gives \(d(a)=a\cdot m+m\cdot a\).

Take any weak* cluster point \(c\) of \(e_i\cdot m-m\cdot e_i\). It belongs to \(Y\) and has norm at most \(2\|m\|\). Multiplying by \(a\) on the left kills \(a\cdot m\cdot e_i\) and gives \(a\cdot c=a\cdot m\) in the limit. Multiplying on the right likewise gives \(c\cdot a=-m\cdot a\). This proves the bound.

## Sharpness

Let \(\kappa:A\to A^{**}\) be the canonical embedding and give \(M=A^{**}\oplus A^{**}\) the norm \(\|(x,y)\|=\max(\|x\|,\|y\|,\|x-y\|)\). This is a dual norm: the graph \((x,y,x-y)\) is weak* closed in the threefold maximum-norm dual sum. Put \(a\cdot(x,y)=(a\cdot x,0)\) and \((x,y)\cdot a=(0,y\cdot a)\), using the canonical weak*-continuous actions of \(A\) on \(A^{**}\). These actions are contractive, have \(A M A=0\), and are dual to actions on the predual of \(M\); its essential core is zero. The map \(d(a)=(\kappa(a),\kappa(a))\) is a derivation of norm one. Any implementer obeys \(a\cdot x=\kappa(a)\) and \(y\cdot b=-\kappa(b)\), so
\[
a\cdot(x-y)\cdot b=2\kappa(ab).
\]
For \(\|a\|=1\) and \(b=e_i\) this yields \(\|x-y\|\ge 2\|ae_i\|\to2\). In particular for \(A=\mathbb C\) the implementer is \((1,-1)\), of norm two.

For the qualitative essential-core reduction, see [Runde (2020), Proposition 2.1.9](https://link.springer.com/chapter/10.1007/978-1-0716-0351-2_2). The estimate here is stated separately from that reference.
