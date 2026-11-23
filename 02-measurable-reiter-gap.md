# A measurable Reiter gap and a compact metrizable factor

**Work in progress, 24 November 2026.** This is a research note toward possible future papers, not a submitted or peer-reviewed paper or a publication-list entry. No priority claim is made.

Let a countable discrete group \(\Gamma\) act continuously on a nonempty compact Hausdorff space \(X\). Write \((s\cdot p)(t)=p(s^{-1}t)\) for translation on \(\operatorname{Prob}(\Gamma)\subset\ell^1(\Gamma)\), and set
\[
D_s(m,x)=\|s\cdot m(s^{-1}x)-m(x)\|_1.
\]
Suppose that for a fixed finite \(F\subset\Gamma\) and \(\varepsilon>0\), every continuous probability field \(q\) supported on a single finite subset of \(\Gamma\) (uniformly in \(x\)) has \(D_s(q,x)\ge\varepsilon\) at some \((x,s)\in X\times F\).

**A single measure for all measurable fields.** Given strictly positive weights \(w_g\) with \(\sum_g w_g=1\), there is a Radon probability \(\lambda\) on \(X\) such that the quasi-invariant Radon probability \(\mu=\sum_g w_g\,g_*\lambda\) satisfies
\[
\sum_{s\in F}\int_X D_s(m,x)\,d\mu(x)\ge w_e\varepsilon
\]
for every probability field \(m\) whose coordinates are measurable for the completion of \(\mu\). The measure \(\mu\) does not depend on \(m\). No metrizability or second countability of \(X\) is assumed.

**Proof.** In the real space \(C(X\times F)\), the functions majorizing at least one \(D(q)\) form a convex set by convexity of the norm. This set is disjoint from the open convex set \(\{f:\max f<\varepsilon\}\). Separation gives a nonzero positive functional, since the first set is closed under addition of nonnegative functions. Normalize and represent it by a Radon probability \(\Lambda\) on \(X\times F\). Testing the separating inequality on constants tending to \(\varepsilon\) gives \(\int D(q)\,d\Lambda\ge\varepsilon\). Let \(\lambda\) be its \(X\)-marginal. The finite sum of defects integrated against \(\lambda\) dominates the labelled integral. All weights are positive, so the orbit average is quasi-invariant; it is Radon by finite-sum approximation, and it dominates \(w_e\lambda\). This proves the bound for continuous finite-support fields.

To pass to a measurable field \(m\), use the finite sum of the measures \((s^{-1})_*\mu\), \(s\in F\cup\{e\}\). First truncate the rows to a finite set, sending the lost mass to \(e\); the integrated \(\ell^1\) error goes to zero by dominated convergence. Approximate the remaining coordinates in \(L^1\) for the sum measure by continuous functions, using Radon regularity. Project the resulting finite vectors continuously to the probability simplex (for example, use the Euclidean nearest-point projection; all norms on this finite-dimensional space are equivalent). This yields a single \(q\) with arbitrarily small integrated row error \(E=\|m-q\|_1\) for each measure. The absolute difference of the \(s\)-defect integrals is at most \(\int E\,d\mu+\int E\,d((s^{-1})_*\mu)\), so the same bound passes to \(m\).

**A factor preserving the infimum for this test.** For a continuous equivariant quotient \(\pi:X\to Y\), push the measure forward to \(\nu=\pi_*\mu\) and pull probability fields back. Their integrated defects agree term by term, so the infimum for \(Y\) is at least the infimum for \(X\). There is a compact metrizable \(Y\) for which equality holds for this fixed \(F,\mu\): choose a sequence of continuous finite-support fields \(q_n\) approaching the infimum by the approximation above, and use the image of \(X\) under the countably many coordinates \(x\mapsto q_n(g^{-1}x)(t)\) for \(g\in\Gamma\) and \(t\) in the support of \(q_n\). The action on the image is induced by permuting the \(g\)-coordinates. Each \(q_n\) descends, giving the reverse inequality.

**Verification and scope.** The single-measure statement was checked in Lean 4.27; the factor and equality of infima in the final paragraph were checked by a written proof. The factor construction does not give an equivariant section, and the equality of infima does not lift Hochschild classes back to \(X\). In particular, this note does not establish nonvanishing of continuous Hochschild \(H^2\).
