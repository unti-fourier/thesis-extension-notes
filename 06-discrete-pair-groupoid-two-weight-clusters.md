# Two cluster values in the raw $I$-algebra of a weighted discrete pair groupoid

**Work in progress (2026-11-27).** Written-checked research notes for a possible future paper, not a paper, preprint, peer-reviewed article, or claim of priority. The results below have not been formalized in Lean.

Let $X$ be countably infinite and discrete, with point masses $w_i>0$ satisfying $\inf_i w_i>0$. Call $d>0$ a *cluster value* if every neighborhood of $d$ contains $w_k$ for infinitely many distinct indices $k$. Suppose that the positive cluster values are exactly $1$ and $q>1$, after a common rescaling.

Write $a_{ik}=w_k f(i,k)$ for a finitely supported pair-groupoid kernel. Convolution becomes ordinary matrix multiplication. Let $A_w$ be the completion in the norm
$
 \|a\|_I=\max\left\{\sup_i\sum_k|a_{ik}|,\ 
                 \sup_k\frac1{w_k}\sum_iw_i|a_{ik}|\right\}.
$
Write $\mathrm{AM}(A_w)$ for the infimum of the uniform bounds of approximate diagonals in the ordinary projective tensor product, as in [Johnson (1972)](https://doi.org/10.2307/2373751). Put
$
 \phi(t)=\lfloor t\rfloor+\{t\}^{2},\qquad c(t)=t/\phi(t),\qquad
 K_d=\sup_i c(w_i/d).
$
The quantity $K_d$ is the upper bound obtained by using only middle indices near $d$. [Single-cluster working note](https://github.com/unti-fourier/thesis-extension-notes/blob/main/06-discrete-pair-groupoid-weight-clusters.md)

**Theorem.** If $1<q\le2$ and $1\le w_i\le q$ for every $i$, then
$
 \boxed{\displaystyle
 \mathrm{AM}(A_w)=\min_{0\le\theta\le1}\ 
 \sup_i\left[(1-\theta)c(w_i)+\theta\,\frac q{w_i}\right].}
 \tag{1}
$
For fixed $\theta$, the supremum in (1) is the optimal bound among approximate diagonals whose two limiting middle-index masses are $1-\theta$ and $\theta$, in the sense defined below.

If $q=2$, the conclusion $\mathrm{AM}(A_w)=K_1=\min(K_1,K_2)$ holds under the assumptions of the first paragraph alone. In particular, weights below $1$ and weights unbounded above are allowed in this assertion.

### 1. An upper bound with the same coefficients at every outer index

Set $\theta_1=1-\theta,\ \theta_q=\theta$, and $B_i=\sum_{d\in\{1,q\}}\theta_d c(w_i/d)$. Fix a finite outer set $F$ and $1<s<\sqrt q$. For each $d$, take $N_d$ distinct middle indices $J_d$ outside $F$ with $d/s<w_k<sd$, where
$
 N_d\ \ge\ \sum_{i\in F}\left\lceil w_i/d\right\rceil .
$
The two bands are disjoint. We shall realize the tensor
$
 Z_F=\sum_{d\in\{1,q\}}\frac{\theta_d}{N_d}
        \sum_{i\in F,\ k\in J_d} E_{ik}\otimes E_{ki}.
 \tag{2}
$

For each outer row $i$, choose the color $d$ with probability $\theta_d c(w_i/d)/B_i$. Given this choice, put $r=w_i/d$. Form a list of slots with amplitudes $h$ consisting of $\lfloor r\rfloor$ ones and one additional slot of size $\{r\}$ if this is positive. Thus $\sum h=r$ and $\sum h^2=\phi(r)$.

Conditional on all row colors, choose **one uniform injection per color**, from the slots of **all** rows of that color into $J_d$. The choice of $N_d$ permits this even if every row chooses the same color. With independent signs $\epsilon_k$, put
$
 U_{ik}=\epsilon_k h/r,\qquad V_{ki}=\epsilon_k B_i h
$
when the slot $h$ of row $i$ is sent to $k$. All other entries are zero.

The absolute row sums of $U$ are at most $1$. Each used column $k$ has weighted column sum $dh/w_k\le s$. Each row of $V$ has at most one entry, of size at most $B_F=\max_{i\in F}B_i$. Its weighted column sum at $i$ is at most $B_i\sum_k w_k h/w_i\le sB_i$. Hence $\|U\|_I\|V\|_I\le s^2B_F$.

Averaging the signs cancels terms with distinct middle indices. At a common middle index, injectivity forces the two outer rows to coincide. Given that $i$ chose $d$, each of its slots lands at a prescribed $k\in J_d$ with probability $1/N_d$. The expected coefficient of $E_{ik}\otimes E_{ki}$ is therefore
$
 \frac{\theta_d c(r)}{B_i}\,
 \frac{B_i}{rN_d}\sum h^2=\frac{\theta_d}{N_d}.
$
This proves $\mathbb E(U\otimes V)=Z_F$, including exact agreement of the coefficient at every outer row.

The product of (2) is $P_F=\sum_{i\in F}E_{ii}$. For $a,b\in F$, both $E_{ab}Z_F$ and $Z_F E_{ab}$ equal $\sum_{d,k\in J_d}(\theta_d/N_d)E_{ak}\otimes E_{kb}$. Letting $F$ increase and $s\downarrow1$ gives an approximate diagonal by density of finite matrices. Using $s^{-2}Z_F$ gives the uniform bound $\sup_i B_i$ with the same limiting masses. This construction works for every $q>1$. Its finite rectangular tensors satisfy the generalized-diagonal identities of Blanco and Grønbæk. [Blanco–Grønbæk, 2009, Definition 3.2](https://arxiv.org/pdf/0804.1725#page=5)

### 2. The two masses of an arbitrary complex approximate diagonal

Let $(z_\alpha)$ be a $C$-bounded approximate diagonal. For $S\subset X$, define the contractive bilinear test
$
 \ell_i^S(a\otimes b)=\sum_{k\in S}a_{ik}b_{ki}.
$
The difference $\ell_i^S(z)-\ell_j^S(z)$ is the value on $E_{ji}z-zE_{ji}$ of the contractive test $a\otimes b\mapsto\sum_{k\in S}a_{jk}b_{ki}$. Thus this difference tends to zero for every fixed $i,j,S$.

Split $X$ into $C_1=\{k:w_k<\sqrt q\}$ and $C_q=X\setminus C_1$. At one fixed row, the pair of evaluations on these two sets lies in a compact bidisc. Take one subnet on which it converges to $(\zeta_1,\zeta_q)$. The commutator identity gives the same limits at every fixed row. The product condition on $E_{ii}$ gives $\zeta_1+\zeta_q=1$.

This **same subnet** works for every fixed narrower band $S_d(s)=\{k:d/s<w_k<sd\}$, $1<s<\sqrt q$. Indeed, for finite $P\subset X$,
$
 \sum_i|\ell_i^P(z)|\le |P|\,\|z\|_\pi .
$
For elementary tensors this follows by summing first over the row $k$ of the second factor. The projective norm gives the general case. Comparison with $L$ distinct outer rows now gives $\limsup_\alpha|\ell_i^P(z_\alpha)|\le |P|C/L$, hence this limit is zero. For a set of indices with $w_k>T$, the test has norm at most $w_i/T$, by column $i$ of the second factor. Within $[\inf w_i,T]$, the part of $C_d$ outside $S_d(s)$ is finite by the cluster hypothesis. Taking the subnet limit first and then $T\to\infty$ proves
$
 \ell_i^{S_d(s)}(z_\alpha)\longrightarrow\zeta_d .
 \tag{3}
$
In particular, $s\downarrow1$ may be taken after (3).

### 3. The sharp lower bound

Assume $1\le w=w_i\le q\le2$. For numbers $0\le x_k\le1$ on the two bands with $\sum_k d\,x_k\le w$, let $t$ be their sum on the light band. A sequence in $[0,1]$ of total mass at most $t$ has sum of squares at most $\phi(t)$, by concentrating its mass into ones and one remainder. Hence
$
 c(w)\sum_{\rm light}x_k^2+\frac{q^2}{w}\sum_{\rm heavy}x_k^2
 \le c(w)\phi(t)+\frac{(w-t)^2}{w}\le w .
 \tag{4}
$
For the last inequality the middle expression is convex on each of $[0,1]$ and $[1,w]$. Its values at $0,w$ are $w$. At $1$, use $c(w)(1+(w-1)^2)=w$ and $1/w\le c(w)$.

For $\|a\|_I,\|b\|_I\le1$, both $x_k=w|a_{ik}|/(ds)$ and $y_k=|b_{ki}|/s$ satisfy the constraints in (4). Weighted Cauchy–Schwarz, using $|a_{ik}b_{ki}|=s^2d x_ky_k/w$, gives
$
 c(w)\sum_{\rm light}|a_{ik}b_{ki}|
 +\frac q w\sum_{\rm heavy}|a_{ik}b_{ki}|\le s^2 .
$
Consequently the **single** functional
$
 \omega_1c(w)\ell_i^{S_1(s)}+\omega_q(q/w)\ell_i^{S_q(s)}
$
has projective-dual norm at most $s^2$ for every independent choice $|\omega_1|,|\omega_q|\le1$. Choose $\omega_d\zeta_d=|\zeta_d|$, apply (3), and let $s\downarrow1$. This proves $c(w)|\zeta_1|+(q/w)|\zeta_q|\le C$ for arbitrary complex tensors.

Since $|\zeta_1|+|\zeta_q|\ge1$, the number $\theta=|\zeta_q|/(|\zeta_1|+|\zeta_q|)$ gives the lower bound in (1) simultaneously at every row. For prescribed nonnegative limits $1-\theta,\theta$, it gives the bound at that particular $\theta$. Section 1 gives equality because $c(w_i/q)=q/w_i$. The supremum in (1) is a Lipschitz function of $\theta$, so its minimum is attained.

### 4. The ratio $1:2$ with unrestricted outer weights

Fix an outer row of weight $w$. In its bilinear test, replace each middle term in the heavy band by two copies, and retain one copy in the light band. For $n=2,1$, respectively, give each copy weight $w_k/n$ and entries $a'=a_{ik}/n,\ b'=b_{ki}$. This preserves the absolute product sum, the row sum of the first factor and the weighted column sum of the second. Every copy now has weight in $(1/s,s)$.

For unit-ball factors, the two lists $w|a'|/s$ and $|b'|/s$ have entries in $[0,1]$ and sums at most $w$. Their squared sums are at most $\phi(w)$. Thus the sum of $|a_{ik}b_{ki}|$ over both bands is at most $s^2/c(w)$. Applying (3) to their union yields $1=|\zeta_1+\zeta_2|\le C/c(w)$. Taking all outer rows gives $C\ge K_1$, and Section 1 with $\theta=0$ gives equality. The splitting takes place entirely inside a scalar bilinear test, so it applies also to outer weights outside $[1,2]$.

### 5. A strict improvement at $q=3/2$

Take the distinct weights $1+1/(1000n)$ and $3/2-1/(1000n)$, $n\ge1$. The two limiting rows give the lower bound
$
 \max\{1+\theta/2,\ (6/5)(1-\theta)+\theta\},
$
whose minimum is $8/7$ at $\theta=2/7$. For the full sequence, put $u=1001/1000,\ v=1499/1000$, and
$
 (a,b,g,e)=\bigl(c(u),q/u,c(v),q/v\bigr)
 =\left(\frac{1001000}{1000001},\frac{1500}{1001},
         \frac{1499000}{1249001},\frac{1500}{1499}\right).
$
The increasing line $a+(b-a)\theta$ and decreasing line $g+(e-g)\theta$ meet at $\theta_*=(g-a)/(b-a+g-e)\in(0,1/3)$. At this value, $u,v$ attain the supremum over all rows. Indeed, on $[1,u]$ we have $c'(w)>9/10$, so $(1-\theta_*)c(w)+\theta_*q/w$ is increasing there. On $[v,3/2]$ both summands decrease. The two selected rows also bound the objective below at every $\theta$, proving optimality. Therefore
$
 \boxed{\displaystyle
 \mathrm{AM}(A_w)=\frac{bg-ae}{b-a+g-e}
 =\frac{5997006000000}{5246008249001}.}
$
In particular,
$
 \frac87<\mathrm{AM}(A_w)<\frac87+\frac1{500}
 <\frac65\le\min\{K_1,K_{3/2}\}.
$
The last inequality follows by taking the outer weight to $3/2$ for $K_1$ and to $1$ for $K_{3/2}$.

Outside the stated regimes, Section 1 still gives an upper bound; this note does not assert an exact formula there.
