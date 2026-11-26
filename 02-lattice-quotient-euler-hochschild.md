# An Euler class in absolute Hochschild cohomology for a compact lattice quotient

**Work in progress.** This note gives a concrete written-checked application of the preceding comparison, not a paper, Lean formalization, or priority claim.

Let \(G=\mathrm{PSL}_2(\mathbb R)\), let \(\Lambda<G\) be a torsion-free cocompact lattice, and let \(X=G/\Lambda\) with invariant probability \(\mu\). Take \(W=L^\infty(X,\mu;\mathbb C)\), with the natural \(G\)-action and the multiplication action of \(C(X)\). For both \(A=L^1(G,C(X);\alpha)\) in the Bochner norm and \(A\) in the row-norm completion, there is an explicit class of seminorm \(1/2\) in absolute bounded Hochschild cohomology \(HH^2_{\rm cont}(A,\mathcal B(C(X),W))\). Twice the class has seminorm one. The module actions and the norms are those in the [split comparison note](02-locally-compact-absolute-hh2-split-injection.md), Sections 3–4.

At a basepoint \(o\) of the curvature \(-1\) hyperbolic plane, put
\[
c(s,t)=-\frac{\operatorname{Area}_{\rm or}(o,so,sto)}{2\pi}.
\]
This is the inhomogeneous representative from the oriented triangle cocycle. With \(\alpha_s(p)(x)=p(s^{-1}x)\), an explicit Hochschild representative, initially on compactly supported inputs, is
\[
F(a,b)(p)(x)=\int_G\int_G c(s,t)\,
 a(s)(x)\,b(t)(s^{-1}x)\,p(t^{-1}s^{-1}x)\,dt\,ds .
\]
The group cocycle identity yields the Hochschild cocycle identity by the split comparison. Integrating in \(t\) first bounds this by \(\tfrac12\|a\|_{\rm row}\|b\|_{\rm row}\|p\|_\infty\).

For the lower bound, restrict the absolute cochain to the subalgebra \(f\mapsto f1_X\) twice and evaluate its output at \(1_X\). The contractive group comparison returns the constant-valued group class in \(H^2_{\rm cb}(G,W)\); integrating \(W\) against the invariant \(\mu\) is a contractive equivariant retraction to complex scalar coefficients. The resulting scalar bounded Euler class restricts to \(\Lambda\) and pairs with the fundamental class of \(\Sigma=\Lambda\backslash\mathbb H^2\) with absolute value \(|\chi(\Sigma)|\), by the hyperbolic area representative and Gauss–Bonnet. The fundamental class has \(\ell^1\)-seminorm \(2|\chi(\Sigma)|\). Every representative of the scalar class must therefore have supremum norm at least \(1/2\); this argument applies equally to complex coefficients. The original class \([F]\) has that same lower bound by contractivity, and the displayed representative attains it.

The Euler class, its area representative and its surface pairing are standard; the assertion here is the application to the specified Banach algebras and module. No conclusion about other crossed-product norms or arbitrary coefficients is used. References: [Burger and Iozzi (2004), §1](https://www.numdam.org/article/ASENS_2004_4_37_1_77_0.pdf#page=2) for the bounded area class; [Bucher-Karlsson (2008), §1](https://arxiv.org/pdf/math/0703587#page=2) for the surface simplicial volume formula.
