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
