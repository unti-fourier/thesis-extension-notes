# A right \(G_2\) coefficient that detects nuclearity

**Research note in progress (2026-11-26).** Direction 7. Written proof checked; not Lean-formalized. This is not a paper, preprint, or peer-reviewed publication. No priority claim is made.

Let \(A\) be a complex \(C^\ast\)-algebra, not necessarily unital or separable. Say a contractive \(A\)-bimodule \(E\) has right \(G_2\) if
\[
  \left(\sum_{i=1}^n\|\xi a_i\|^2\right)^{1/2}
  \le \|\xi\|\left\|\sum_{i=1}^n a_i\right\|
  \qquad(\xi\in E,\ a_i\in A_+).
\]
The following are equivalent:

1. \(A\) is nuclear.
2. Every bounded derivation \(A\to E^\ast\) is inner when \(E\) is a contractive bimodule, essential on both sides, with right \(G_2\).
3. The single derivation described below is inner.

### The coefficient

Let \(\pi:A\to B(H_u)=S\) be the universal representation and \(R=\pi(A)'\). Let \(V\subset B(S,S)\) consist of the bounded \(R\)-bimodule maps vanishing on \(R\). It is weak-star closed for the pairing with \(S\widehat\otimes_\pi S_1(H_u)\): evaluation against a trace-class operator is weak-star continuous, as are the output multiplications by a fixed element of \(R\). Thus \(V=E^\ast\), where \(E=(S\widehat\otimes_\pi S_1(H_u))/V_\perp\).

Give \(V\) the actions \((a\cdot T)(x)=\pi(a)T(x)\) and \((T\cdot a)(x)=T(x)\pi(a)\); these preserve \(V\). The predual actions on trace class are right and left multiplication by \(\pi(a)\), respectively. A contractive approximate identity acts on trace class in norm on both sides, by nondegeneracy, finite-rank approximation, and uniform boundedness. The projective tensor product and its quotient therefore give a contractive, two-sided essential \(E\).

### The estimate

For a rank-one trace-class operator \(u\otimes v^\ast\),
\[
 \left(\sum_i\|(u\otimes v^\ast)\pi(a_i)\|_1^2\right)^{1/2}
 =\|u\|\left(\sum_i\|\pi(a_i)^\ast v\|^2\right)^{1/2}
 \le \|u\|\|v\|\left\|\sum_i a_i a_i^\ast\right\|^{1/2}.
\]
A trace-class rank-one expansion and the triangle inequality in the finite \(\ell^2\)-sum extend the estimate to every trace-class operator. The same triangle inequality for projective tensor representations gives it on \(S\widehat\otimes_\pi S_1(H_u)\). Pass to \(E\) using a common lift for all the terms on the left and taking the infimum over lifts. Consequently
\[
  \left(\sum_i\|\xi a_i\|^2\right)^{1/2}
   \le \|\xi\|\left\|\sum_i a_i a_i^\ast\right\|^{1/2}.
\]
For positive \(a_i\), \(a_i^2\le \|\sum_j a_j\|a_i\), giving right \(G_2\) with constant one; the \(a_i\) need not commute. The same estimate holds for the canonical action of \(M(A)\), by the extension of the nondegenerate representation, with the norm on the right taken in \(M(A)\).

### The derivation

Set \(\partial_\pi(a)(x)=\pi(a)x-x\pi(a)\). It lies in \(V\) and the commutator identity makes \(\partial_\pi:A\to V\) a bounded derivation. If it is inner with implementer \(T\in V\), then \(Q=\operatorname{id}_S-T\) is a bounded \(R\)-bimodule map with range in \(R\), since \([\pi(a),Q(x)]=0\) for all \(a,x\). It fixes \(R\). Conversely any bounded \(R\)-bimodule projection \(S\to R\) gives an implementer \(\operatorname{id}_S-Q\). [Bunce and Paschke (1978)](https://doi.org/10.1090/S0002-9939-1978-0482252-3) give injectivity of \(R\) from such a projection. Injectivity is equivalent for a von Neumann algebra and its commutant, so \(A^{\ast\ast}\cong R'\) is injective, and [Choi and Effros (1977)](https://doi.org/10.1512/iumj.1977.26.26034) give nuclearity of \(A\). Conversely nuclearity gives innerness even without the restriction on \(E\), by [Haagerup (1983)](https://doi.org/10.1007/BF01394319).

The commutant-projection argument and predual quotient are part of the classical route to nuclearity, as in [Runde (2020), Theorems 5.1.24 and 7.2.7](https://doi.org/10.1007/978-1-0716-0351-2). The point of this note is the norm estimate which places that particular coefficient in the restricted class.

For a \(C^\ast\)-crossed product \(B\), the same construction can be applied to \(B\) itself. If the restricted coefficient condition tests right \(G_2\) only on the positive elements of the canonical coefficient algebra in \(M(B)\), or on the positive elements of its central multiplier algebra, the witness still qualifies by the multiplier estimate. Consequently universal innerness with either restriction, on contractive essential \(B\)-bimodules, is equivalent to nuclearity of \(B\), without a separate nuclearity hypothesis on the coefficient algebra. This is a test on the completed \(C^\ast\)-crossed product; it does not assert a result for a different Banach-algebra completion.
