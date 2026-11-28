# Haar 系の単位密度変更と raw $I$ ノルムの鋭さ

*公開草稿（work in progress）。書面検算のみ。優先性は未確認。*

全節で $V$ は、元の Haar 系 $\lambda$ で測った入力を、密度変更後の $\lambda_d$ で測る写像とする。軌道内密度比の上限を $D$ とすると一般上界は $\sqrt D$ である。以下ではこの値を局所テストで達成する十分条件と、上界 $2$ に対して実際のノルムが $5/4$ となる例を示す。

## 1. 元の Haar 系から変更後の系への写像

$G\rightrightarrows X$ を非空の局所コンパクト Hausdorff groupoid、$\lambda=(\lambda^x)$ を full continuous 左 Haar 系とする。$G^x=r^{-1}(x)$、$G_y=s^{-1}(y)$、$G_y^x=G^x\cap G_y$ と書き、$G_y$ には反転による押し出し $\lambda_y=(\mathrm{inv})_\ast\lambda^y$ を入れる。range 行は終点 $x$、source 行は始点 $y$ を固定する。

$$
R_\lambda F(x)=\int_{G^x}F\,d\lambda^x,\qquad
S_\lambda F(y)=\int_{G_y}F\,d\lambda_y,\qquad
\|a\|_{I,\lambda}=\max\{\|R_\lambda|a|\|_\infty,\|S_\lambda|a|\|_\infty\}.
$$

$A_\lambda$ は untwisted な複素畳み込み環 $C_c(G)$ のこのノルムでの完備化とする。連続関数 $d:X\to(0,\infty)$ で密度を変更すると、左移動が始点を保つことと反転の定義から

$$
\lambda_d^x=(d\circ s)\lambda^x,\qquad
(\lambda_d)_y=(d\circ r)\lambda_y
$$

となる。正値性と $(d\circ s)C_c(G)\subset C_c(G)$ により $\lambda_d$ も full continuous 左 Haar 系である。以下の記号を用いる。

$$
\omega(\gamma)=\frac{d(r\gamma)}{d(s\gamma)},\quad
D=\sup_{\gamma\in G}\omega(\gamma),\quad
c(\gamma)=\sqrt{d(r\gamma)d(s\gamma)},\quad
(Va)(\gamma)=\frac{a(\gamma)}{c(\gamma)} .
$$

完備化への延長を仮定せず、$N(V)=\sup_{\|a\|_{I,\lambda}\le1,\ a\in C_c(G)}\|Va\|_{I,\lambda_d}$ と定める。

**命題 1（一般上界）.** $D<\infty$ なら $V:A_\lambda\to A_{\lambda_d}$ は Banach $\ast$-環同型で、$N(V)=\|V\|\le\sqrt D$、$\|V^{-1}\|\le\sqrt D$ である。

実際、合成可能な対で $c(\eta)c(\eta^{-1}\gamma)=d(s\eta)c(\gamma)$ となる。これを $\lambda_d^{r\gamma}$ による畳み込み積分に代入すると $(Va)\ast_{\lambda_d}(Vb)=V(a\ast_\lambda b)$ を得る。反転で $c$ は変わらないので $a^\ast(\gamma)=\overline{a(\gamma^{-1})}$ も保たれる。第2節と第3節で使う出力の両行は

$$
R_{\lambda_d}|Va|(x)=\int_{G^x}|a|\,\omega^{-1/2}\,d\lambda^x,\qquad
S_{\lambda_d}|Va|(y)=\int_{G_y}|a|\,\omega^{1/2}\,d\lambda_y .
\tag{1}
$$

反転で $\omega$ は逆数になるので、どちらの因子も $D^{-1/2}$ 以上、$D^{1/2}$ 以下である。$C_c(G)$ 上で $V$ は全単射で、逆は $\Phi f=cf$ である。従って二側の評価が完備化にも移る。必要な一様性は同じ軌道に属する二点の密度比に関するものである。

## 2. 始点の等方群が零集合となる矢での下界

**命題 2（局所条件）.** $\gamma:y\to x$ について $\lambda^y(G_y^y)=0$ とする。このとき $N(V)\ge\sqrt{d(x)/d(y)}$ である。この条件を満たす矢上での $\omega$ の上限が $D$ に等しければ、$D<\infty$ では $\|V\|=\sqrt D$、$D=\infty$ では $V$ は $C_c(G)$ 上で非有界となる。

**局所テストの構成.** 任意の開近傍 $U\ni\gamma$ と $0<\varepsilon<1$ を固定する。左不変性により全ての $z$ で $\lambda^z(G_y^z)=0$ である。実際、$y$ から $z$ への矢による左移動は $G_y^y$ を $G_y^z$ に移し、そのような矢がないときは $G_y^z$ が空である。

$\gamma$ で正の $h\in C_c(U)_+$ を零延長する。full support より $S_\lambda h(y)>0$ なので、定数倍してこの値を $1$ にする。$b=h/\max\{1,(S_\lambda h)\circ s\}$ と置けば $S_\lambda b\le1$ かつ $S_\lambda b(y)=1$ となる。$K=\operatorname{supp}b$ とする。各 $z\in r(K)$ に対し、有限 Radon 測度 $\nu_z=s_\ast(b\lambda^z)$ は $\nu_z(\{y\})=0$ を満たす。外正則性により $\nu_z(O_z)<\varepsilon$ となる開近傍 $O_z\ni y$ がある。$\psi_z(y)=1$、$0\le\psi_z\le1$ の $\psi_z\in C_c(O_z)$ を取ると、

$$
R_\lambda\big[b(\psi_z\circ s)\big](z)=\int_X\psi_z\,d\nu_z<\varepsilon .
$$

Haar 系の連続性によりこの不等式は $z$ の近傍でも成り立つ。これらの近傍で $r(K)$ を有限被覆し、対応する $\psi_z$ の最小値を $\psi$ とする。$a=b(\psi\circ s)$ の台は $U$ に含まれ、$S_\lambda a=\psi S_\lambda b\le1$、$S_\lambda a(y)=1$ である。$R_\lambda a$ は $r(K)$ 上で連続かつ $\varepsilon$ 未満、その外で零なので、$\|R_\lambda a\|_\infty<\varepsilon$ となる。

従って $\|a\|_{I,\lambda}=1$ である。任意の $0<L<\sqrt{\omega(\gamma)}$ に対して $U=\{\sqrt\omega>L\}$ を選ぶと、(1) の出力 source 行は $y$ で $L$ を超える。これで命題 2 の下界が従う。

**標準 Haar 系の変換 groupoid との関係.** unimodular な局所コンパクト Hausdorff 群 $H$ が $X$ に連続に作用する場合、標準 Haar 系では零集合条件を課さずに $N(V)=\sqrt D$ が成り立つ。矢を $[t,y]:y\to ty$ と書き、$0<L<\sqrt{d(t_0y_0)/d(y_0)}$ を取る。反転不変な Haar 測度 $m$ に対する積分が $1$ の $k\in C_c(H)_+$ を、$\sqrt{d(ty_0)/d(y_0)}>L$ が保たれる $t_0$ の近傍に取り、$0\le\psi\le1$、$\psi(y_0)=1$ の $\psi\in C_c(X)$ を選ぶ。$a([t,y])=k(t)\psi(y)$ に対して $S_\lambda a=\psi$、$R_\lambda a(x)=\int_H k(t)\psi(t^{-1}x)\,dm(t)\le1$ である。(1) の source 行は $y_0$ で $L$ を超える。

## 3. 二点基底での厳密値

$X=\{0,1\}$、$G=X\times\mathbb T\times X$ とし、矢 $(i,t,j)$ の終点は $i$、始点は $j$ とする。元の Haar 系は円周の正規化 Haar 確率 $m$ と基底重み $(\mu_0,\mu_1)=(1,1/4)$ から作る。密度を $(d(0),d(1))=(1,4)$ とする。変更後の基底重みは $(\mu_0d(0),\mu_1d(1))=(1,1)$、密度比の上限 $D=4$ は $0\to1$ の矢で達成される。

任意の複素核 $a$ に対し $A_{ij}=\int_{\mathbb T}|a(i,t,j)|\,dm(t)$ と置く。$m$ は反転不変なので、入力の range 行は $\sum\limits_j\mu_j A_{ij}$、入力の source 行は $\sum\limits_i\mu_i A_{ij}$ である。任意の非負行列 $A$ は群変数に一定の連続核で実現できる。出力 $Va$ では各成分が $A_{ij}/\sqrt{d(i)d(j)}$ となり、変更後の重みはともに $1$ である。従って $A=\bigl(\begin{smallmatrix}u&v\\w&z\end{smallmatrix}\bigr)$ と書けば、入出力の四つの周辺和は次の通りである。

| 固定する端点 | 入力 $a$ を元の $\lambda$ で測る | 出力 $Va$ を変更後の $\lambda_d$ で測る |
| --- | --- | --- |
| range $i=0$ | $u+v/4$ | $u+v/2$ |
| range $i=1$ | $w+z/4$ | $w/2+z/4$ |
| source $j=0$ | $u+w/4$ | $u+w/2$ |
| source $j=1$ | $v+z/4$ | $v/2+z/4$ |

**上界.** $\theta=\max\{v,w\}$ と置くと、入力の四つの周辺和がすべて $1$ 以下であることは $u+\theta/4\le1$、$\theta+z/4\le1$ と同値である。特に $0\le\theta\le1$。出力ノルムは次の二項の大きい方である。

$$
u+\theta/2=(u+\theta/4)+\theta/4\le5/4,\qquad
\theta/2+z/4=(\theta+z/4)-\theta/2\le1 .
$$

**達成.** 群変数に一定の非負核を次の行列で与える。

$$
A=\begin{pmatrix}3/4&1\\1&0\end{pmatrix},\qquad
\left(\frac{A_{ij}}{\sqrt{d(i)d(j)}}\right)_{ij}
=\begin{pmatrix}3/4&1/2\\1/2&0\end{pmatrix}.
$$

入力の range 二行と source 二行はすべて $1$、出力の range と source の値はどちらも $(5/4,1/2)$ である。ゆえに **$\|V:A_\lambda\to A_{\lambda_d}\|=5/4<2=\sqrt D$** となる。

添字の向きは $0\to1$ の成分だけでも確かめられる。$A_{10}=1$ だけを残した入力では range $i=1$ が $1$、source $j=0$ が $1/4$ である。各 Haar 行は円周 Haar の有限和なので点原子を持たず、pair groupoid への射影には大域切断 $(i,j)\mapsto(i,1,j)$ がある。それでも $\lambda^y(G_y^y)=\mu_y>0$ であり、この成分で source の質量だけを $1$ に上げると入力の range 制約を破る。

ここで計算した定数は、指定した二つの Haar 系の間の写像 $V$ の作用素ノルムである。$D<\infty$ のとき ordinary Banach amenability は命題 1 の同型で保存される。局所自明な gauge groupoid での既存の $\mathrm{AM}=1$ は、無限コンパクト基底、full-support な局所基底測度、amenable かつ非 unimodular な構造群のもとでの近似対角の定数である。一般の Haar groupoid の topological amenability と raw $I$ 環の ordinary Banach amenability との同値は別の問題である。
