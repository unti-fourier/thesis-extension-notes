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

### Matrix algebras: exact minimum implementer norm

For \(A=M_d\) represented on \(\mathbb C^d\otimes K\) with multiplicity \(k=\dim K\ge 1\), the same commutant derivation has minimum implementer norm
\[
  2\left(1-\frac{1}{d\min(d,k)}\right).
\]
In particular the universal representation contains the trace GNS summand, so the value is \(2(1-d^{-2})\). In that representation the unique minimizer is \(I-Q_\tau\), where \(Q_\tau=(\tau\otimes\operatorname{id})(\,\cdot\,)\) is viewed as a projection onto \(1_d\otimes B(K)\), and \(\tau\) is normalized trace.

In fact, every bounded \(R\)-bimodule projection is \(Q_\varphi\) for a linear functional \(\varphi\) on \(M_d\) with \(\varphi(1)=1\). This follows by evaluating it on \(a\otimes 1\), whose image commutes with \(R\). Positivity of \(\varphi\) need not be assumed. Averaging \(I-Q_\varphi\) by Weyl conjugations yields \(I-Q_\tau\) without increasing the norm.

Write \(m=\min(d,k)\) and \(c=1/(dm)\). The map \(Q_\tau-cI\) is positive. To see this, on a finite-dimensional multiplicity space it suffices to check rank-one projections \(P=|\Omega\rangle\langle\Omega|\). If \(D=\operatorname{Tr}_{\mathbb C^d}(P)\), then \(Q_\tau(P)=d^{-1}1\otimes D\). Cauchy–Schwarz on the support of \(1\otimes D\) gives \(P\le r(1\otimes D)\), where \(r\le m\) is the Schmidt rank: in Schmidt coordinates \(\|(1\otimes D^{-1/2})\Omega\|^2=r\). For infinite \(K\), compress to finite-dimensional multiplicity subspaces; compression commutes with \(Q_\tau\), so the order inequality holds on all vector quadratic forms. Unless \(c=1\), \((Q_\tau-cI)/(1-c)\) is positive unital, hence contractive. This proves \(\|I-Q_\tau\|\le 2(1-c)\). The case \(c=1\) is \(d=1\) and the derivation is zero.

For equality, use a unit vector \(\Omega\) of Schmidt rank \(m\) with equal Schmidt coefficients. For its projection \(P\), the reflection \(2P-1\) has norm one and \((I-Q_\tau)(2P-1)\Omega=2(1-c)\Omega\). When \(m=d\), \(\langle\Omega,Q_\varphi(P)\Omega\rangle=d^{-2}\) for every \(\varphi(1)=1\). If \(\|I-Q_\varphi\|=2(1-d^{-2})\), equality in Cauchy–Schwarz on this same reflection forces \(Q_\varphi(P)\Omega=d^{-2}\Omega\). Writing out the matrix entries in the Schmidt basis gives \(\varphi(e_{ij})=\delta_{ij}/d\), proving uniqueness even among nonpositive slices.

The full-amplification constant is familiar as the diamond distance between the identity channel and the completely depolarizing channel, by trace duality. See [Pirandola et al. (2019), Fundamental limits to quantum channel discrimination](https://www.nature.com/articles/s41534-019-0162-y) for the channel context. Here it is the exact norm of the smallest implementer in the specific derivation test above. The calculation is verified in writing, not Lean.
