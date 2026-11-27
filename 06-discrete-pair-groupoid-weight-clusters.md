# Amenability constants for weighted discrete pair groupoids with a positive cluster value

**Work in progress (2026-11-27).** A written-checked research note toward a possible future paper. This is not a paper, preprint, peer-reviewed publication, or priority claim. The proof here has not been formalized in Lean.

The raw $I$-algebra of the discrete pair groupoid with weights $w_n=1+1/n$, $n\ge2$, has ordinary Banach amenability constant **$6/5$**. All its weights are distinct and exceed their limit. More generally, a positive lower bound on the weights and a unique positive cluster value give an exact formula. When the weights also approach zero, amenability depends on the total mass carried by the small weights.

## Statement

Let $X$ be countably infinite and discrete, with pairwise distinct weights $0<w_i<\infty$. Give $X$ the measure $\sum_i w_i\delta_i$. Under the identification $a_{ij}=w_j f(i,j)$, convolution of finitely supported pair-groupoid kernels becomes ordinary matrix multiplication. Write $A_w$ for the completion in the raw $I$-norm
$
 \|a\|_I=\max\left\{
     \sup_i\sum_k |a_{ik}|,\quad
     \sup_k\frac1{w_k}\sum_i w_i|a_{ik}|
 \right\}.
$
Thus $E_{ij}$ denotes the ordinary matrix unit and corresponds to the kernel $w_j^{-1}\mathbf1_{\{(i,j)\}}$.

Let $\mathcal D$ consist of the $d>0$ for which every neighborhood of $d$ contains $w_k$ for infinitely many **indices** $k$. Assume throughout that $\mathcal D\ne\varnothing$. Put
$
 m=\inf_i w_i,\qquad W(t)=\sum_{w_k<t}w_k,\qquad
 c(r)=\frac{r}{\lfloor r\rfloor+\{r\}^2},\qquad
 K_d=\sup_i c(w_i/d).
$

**Theorem.**

1. If $m>0$, then $A_w$ is amenable. For every $d\in\mathcal D$,
   $
      \mathrm{AM}(A_w)\le K_d\le\max\{4/3,d/m\}.
   $
   If $\mathcal D=\{d\}$, then $\mathrm{AM}(A_w)=K_d$. The weights may be unbounded above.
2. If $m=0$, then $A_w$ is amenable exactly when $W(t)=\infty$ for every $t>0$. In that case $\mathrm{AM}(A_w)=1$.

Here $\mathrm{AM}$ is the infimum of the bounds of approximate diagonals in the ordinary projective tensor product. We use Johnson’s bounded approximate diagonal criterion and write $\pi$ for multiplication. See B. E. Johnson (1972) and A. Blanco and N. Grønbæk (2009), §2. [Johnson](https://doi.org/10.2307/2373751) · [Blanco–Grønbæk, §2](https://arxiv.org/pdf/0804.1725#page=3)

## What disappears through finitely many middle indices

Suppose $(z_\alpha)$ is an approximate diagonal of bound $C$. Matrices act contractively on $H=\ell^2(X,w)$. Indeed, rowwise Cauchy–Schwarz gives
$
 \sum_i w_i\Big|\sum_k a_{ik}\xi_k\Big|^2
 \le \Big(\sup_i\sum_k|a_{ik}|\Big)
          \sum_k|\xi_k|^2\sum_i w_i|a_{ik}|
 \le \|a\|_I^2\|\xi\|_H^2 .
$
Write $T_a$ for this representation and $e_i=w_i^{-1/2}\mathbf1_{\{i\}}$. For finite $P\subset X$, let $Q_P$ be the orthogonal projection onto the corresponding basis vectors. The map
$
 S_P(a\otimes b)=T_aQ_PT_b
$
intertwines the outer actions and has projective-to-trace norm at most $|P|$. Its $i$-th diagonal entry on an elementary tensor is exactly $\sum_{k\in P}a_{ik}b_{ki}$. The two changes of orthonormal coordinates cancel.

For every fixed $P,i$,
$
 \langle S_P(z_\alpha)e_i,e_i\rangle\longrightarrow0.                 \tag{1}
$
To see this, choose $L$ distinct basis vectors including $e_i$, and let $U$ cycle them while fixing their orthogonal complement. Each $U^j-I$ is represented by a finite matrix. Consequently $S_P(z_\alpha)$ commutes asymptotically with each fixed $U^j$ in trace norm. Averaging the $i$-th entry of $U^jS_P(z_\alpha)U^{-j}$ gives the trace of the $L$-dimensional compression divided by $L$. Its absolute value is at most $|P|C/L$, also for complex, nonpositive tensors. Take the net limit superior first and then $L\to\infty$. In contrast, the product condition on $E_{ii}$ gives $(\pi z_\alpha)_{ii}\to1$.

## The sharp estimate at a single positive cluster

Fix $i$, put $r=w_i/d$, and let $J_s=\{k:d/s<w_k<sd\}$, where $s>1$. For $\|a\|_I,\|b\|_I\le1$, the four bounds needed on this band are
$
 \begin{array}{c|cc}
    &\text{pointwise bound}&\text{sum over }J_s\\ \hline
    r|a_{ik}| & s & r\\
    |b_{ki}| & 1 & sr .
 \end{array}
$
The first line uses column $k$ and row $i$ of $a$. The second uses row $k$ and column $i$ of $b$. After dividing both lines by $s$, each vector has entries in $[0,1]$ and sum at most $r$. Its squared $\ell^2$-norm is at most $\lfloor r\rfloor+\{r\}^2$. Indeed, moving mass from a smaller fractional entry to a larger one until an entry reaches $0$ or $1$ increases the sum of squares. Cauchy–Schwarz now gives
$
 \sum_{k\in J_s}|a_{ik}b_{ki}|\le \frac{s^2}{c(r)}.                 \tag{2}
$

Suppose $m>0$ and $\mathcal D=\{d\}$. For $B>sd$, the set $P=\{k:w_k\le B\}\setminus J_s$ is finite. Otherwise infinitely many distinct indices in the compact set $[m,B]\setminus(d/s,sd)$ would yield another positive cluster value. On $w_k>B$, column $i$ gives $|b_{ki}|\le w_i/B$, and row $i$ of $a$ bounds the remaining sum by $w_i/B$. These scalar bilinear estimates extend to the projective tensor product. Applying (1) to the finite remainder gives
$
  1\le C\left(\frac{s^2}{c(r)}+\frac{w_i}{B}\right).
$
The approximate-diagonal limit is taken with $B,s,i$ fixed. Sending $B\to\infty$ and then $s\downarrow1$ proves $C\ge c(w_i/d)$.

For the upper bound, take any $d\in\mathcal D$ and any nonempty finite outer set $F$. For $i\in F$, form a list $h_{i,l}$ of $\lfloor r_i\rfloor$ ones followed by the positive fractional part, if present, where $r_i=w_i/d$. Thus
$
 \sum_l h_{i,l}=r_i,\qquad
 \sum_l h_{i,l}^2=r_i/c(r_i).
$
After fixing the total number $N$ of slots, choose **$N$ distinct indices** in $J_s\setminus F$. Denote their set by $J$. Assign them to the slots by a uniform random bijection. For the index $k$ assigned to $(i,l)$, put
$
 U_{ik}=\epsilon_k h_{i,l}/r_i,\qquad
 V_{ki}=\epsilon_k c(r_i)h_{i,l},
$
using independent uniform signs and zero elsewhere. The row bound of $U$ is $1$, and its weighted column bound is at most $s$, since each used column has a single entry with weighted size $dh_{i,l}/w_k$. The row and weighted column bounds of $V$ are at most $\max_{i\in F}c(r_i)$ and $s\max_{i\in F}c(r_i)$, respectively.

Averaging the signs kills the cross terms. Each slot receives a prescribed $k$ with probability $1/N$. Hence
$
 Z_F=\mathbb E(U\otimes V)
     =\frac1N\sum_{i\in F,\,k\in J}E_{ik}\otimes E_{ki},
 \qquad \|Z_F\|_\pi\le s^2\max_{i\in F}c(r_i).
$
Its product is exactly $P_F=\sum_{i\in F}E_{ii}$. For $a,b\in F$, both $E_{ab}\cdot Z_F$ and $Z_F\cdot E_{ab}$ equal $N^{-1}\sum_{k\in J}E_{ak}\otimes E_{kb}$. Taking $F$ upwards and $s\downarrow1$ gives the approximate diagonal by density. Scaling by $s^{-2}$ gives bound $K_d$, with product $s^{-2}P_F$. Finally, $c(r)=1/r$ for $r<1$, and $c(r)^{-1}=1-\{r\}(1-\{r\})/r\ge3/4$ for $r\ge1$.

The finite rectangular product and commutation identities fit Blanco–Grønbæk’s generalized diagonals (2009, Definition 3.2). The canonical square-matrix average is Grønbæk–Johnson–Willis (1994, Proposition 3.2). The estimates above use the two specific weighted matrix norms on the rectangular factors. [Blanco–Grønbæk, Definition 3.2](https://arxiv.org/pdf/0804.1725#page=5) · [Grønbæk–Johnson–Willis, Proposition 3.2](https://arxiv.org/pdf/math/9209211#page=8)

## Weights approaching zero

If $W(t)<\infty$, take a finite $P\subset\{k:w_k<t\}$. On elementary tensors with both factors in the unit ball,
$
 \left|(ab)_{ii}-\sum_{k\in P}a_{ik}b_{ki}\right|
 \le \frac1{w_i}\sum_{\substack{w_k<t\\k\notin P}}w_k+\frac{w_i}{t}.
$
The first term uses $|a_{ik}|\le w_k/w_i$ and $|b_{ki}|\le1$. The second uses $|b_{ki}|\le w_i/t$ and the row sum of $a$. Apply (1) before exhausting the finite-mass tail by $P$. This yields $1\le Cw_i/t$ for every $i$, which rules out a bounded approximate diagonal when $m=0$.

Conversely, suppose $W(t)=\infty$ for every $t>0$. Fix $F$ and write $v=\min_{i\in F}w_i$. Choose a finite $J$ outside $F$ with $w_k<\tau$ and $D=\sum_{k\in J}w_k\ge\sum_{i\in F}w_i$. Partition a circle of circumference $D$ into cells of lengths $w_k$. Place disjoint half-open arcs of lengths $w_i$ on the same circle and rotate these arcs together by a uniform shift. Assign $k$ to $i$ when the midpoint of cell $k$ belongs to arc $i$.

Each $k$ is assigned to $i$ with probability exactly $w_i/D$. The assigned cells lie in arc $i$ enlarged by $\tau/2$ at each end, even across the origin of the circle. Their total mass is therefore at most $w_i+\tau$. On an assigned pair use $U_{ik}=\epsilon_k w_k/w_i$ and $V_{ki}=\epsilon_k$. The weighted columns of $U$ and rows of $V$ are bounded by $1$. The other two bounds are at most $1+\tau/v$. Thus
$
 \mathbb E(U\otimes V)
 =\sum_{i\in F,\,k\in J}\frac{w_k}{D}E_{ik}\otimes E_{ki},
 \qquad
 \|\mathbb E(U\otimes V)\|_\pi\le(1+\tau/v)^2.
$
The coefficient is $(w_k/w_i)(w_i/D)=w_k/D$, independent of the outer index. The shift average is a finite convex combination because assignments change at finitely many angles. The product and centrality identities hold exactly. Choosing $\tau/v\to0$ after fixing each $F$, and rescaling as above, gives a contractive approximate diagonal. The product condition on $E_{ii}$ gives the matching lower bound $1$.

## Examples and limits

For $w_n=1+1/n$, $n\ge2$, one has $c(w_n)=n(n+1)/(n^2+1)$, with maximum $6/5$ attained at $n=2,3$. Adjoining the distinct weights $4+1/n$ gives two positive cluster values: the bound from $d=1$ is at most $4/3$, whereas $K_4=4$. An individual cluster bound need not be optimal when the cluster is not unique.

The finite-middle argument only forces a fixed diagonal entry to vanish; it does not force the full trace to vanish. No exact formula for arbitrary sets of several positive cluster values, or classification when $m>0$ and there is no positive cluster value, is asserted here.

[Related noncompact pair-groupoid examples](06-noncompact-pair-groupoid-raw-i.md).
