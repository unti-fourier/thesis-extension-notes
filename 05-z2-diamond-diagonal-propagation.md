# Sharp diagonal propagation on the integer diamond

**Work in progress.** 2026-11-26. 博論の拡張方針5の研究ノート。書面検証済み、Lean 検証なし。論文・プレプリント・査読済み成果ではなく、既存文献に対する優先性は主張しない。

$G=\mathbb Z^2$、$S=\{\pm e_1,\pm e_2\}$、$B_R=\{g:\|g\|_1\le R\}$ とし、$R$ は非負整数とする。$\tau_s p(g)=p(g-s)$ と書く。菱形のスカラー公式は、以下で対称化と coarea により証明する。これを counting-$I$ の近似対角に移すと、両脚の同時制約の下でも同じ値を達成する。

## スカラー公式

$\Delta_R=\min_{p\in\operatorname{Prob}(B_R)}\max_{s\in S}\|\tau_s p-p\|_1$ とする。$0\le u\le R$ に対して $m=2u+1$、$t=(2u-R)_+$、$S_u=B_R\cap[-u,u]^2$ とおくと
$$
\Delta_R=\min_{\varnothing\ne F\subset B_R}\frac{|\partial_E F|}{2|F|}
=\min_{0\le u\le R}\frac{2m}{m^2-2t(t+1)}.
$$
$\partial_E$ は全格子の無向辺境界で、菱形の外へ出る辺も数える。最適な $S_u$ 上の一様確率が最小値を達成する。

各方向の欠損を $V_i(p)=\|\tau_{e_i}p-p\|_1$ とおく。負の生成元も同じ欠損になる。$F_z=\{p>z\}$ について layer cake は
$$
V_1(p)+V_2(p)=\int_0^\infty|\partial_E F_z|\,dz,\qquad
1=\int_0^\infty |F_z|\,dz
$$
を与える。従って最大欠損は辺境界比の最小値以上である。逆に、任意の $F$ の一様確率とその座標交換像を半々で平均すれば、各方向の欠損は $|\partial_E F|/(2|F|)$ 以下になる。これで第一の等号が従う。

第二の等号のため、確率を座標交換と二座標の符号反転からなる8対称性で平均する。最大欠損は増えず、二方向の欠損は等しい。以下、対称な非空のレベル集合 $F$ を考える。二つの座標射影は共通の集合 $P=-P$ で、$|\partial_E F|\ge4|P|$ である。各非空の行と列が少なくとも二本の境界辺を持つためである。$u$ を $P$ の正の値の個数とし、それらを小さい順に $1,\dots,u$ に、負の値も同じ絶対値の順位に写す。両座標にこの単射をかけると絶対値の和は増えず、像は $S_u$ に収まる。$C_u=|S_u|$ とする。

- $0\in P$ なら $|P|=m$ かつ $|F|\le C_u$ である。
- $0\notin P$ なら $|P|=m-1>0$ で、像は $S_u$ 内の座標軸上の $2m-1$ 点と互いに素である。$|F|\le(m-1)^2$ も用いると、$C_u/m\ge(|F|+2m-1)/m\ge |F|/(m-1)$ を得る。

いずれも $|\partial_E F|/(2|F|)\ge 2m/C_u$ を与える。$S_u$ では各行・列の切片は区間で、両方向とも一様確率の欠損が $2m/C_u$ に等しい。四隅から各 $t(t+1)/2$ 点を除くことで $C_u=m^2-2t(t+1)$ となる。

$R=0,1,2,3,4,5$ での最適値は順に $2,\ 6/5,\ 2/3,\ 10/21,\ 14/37,\ 14/45$。例えば $R=2$ では $u=0,1,2$ の候補が $2,\ 2/3,\ 10/13$ である。$R\ge1$ では $C_u/m$ は $m\le R+1$ で $m$、$m\ge R+1$ で $4R+2-m-2R(R+1)/m$ に等しい。後者は実数 $m=\sqrt{2R(R+1)}$ で最大となるので、その両隣の奇数を比較すれば足りる。特に $R\Delta_R\longrightarrow 1+1/\sqrt2$。

## 行抽出と鋭いテンソル下界

非空コンパクト Hausdorff 空間 $X$ 上の global $G$-action を取り、$\alpha_g(f)(x)=f((-g)x)$、$U_g f U_{-g}=\alpha_g(f)$ とする。$A$ は $a=\sum_g a_gU_g$ の有限和に
$$
\|a\|_I=\max\left\{\sup_x\sum_g|a_g(x)|,\ \sup_y\sum_g|a_g(gy)|\right\}
$$
を入れた完備化で、$\pi:A\widehat\otimes_\pi A\to A$ は積写像とする。テンソル $T$ の第一・第二脚の群台を $F,H$ に制限するとは、座標切断で $(P_F\otimes P_H)T=T$ となることをいう。以下では両方を $B_R$ に制限する。下界だけには $F\cap(-H)\subset B_R$ で十分である。

行抽出 $\Phi(a\otimes b)_g(x)=a_g(x)b_{-g}((-g)x)$ は $C(X,\ell^1(G))$ への縮小写像に延びる。単純テンソルの絶対値の行和が $\|a\|_I\|b\|_I$ 以下だからである。行和は $(\pi T)_0$、行の台は $F\cap(-H)$ に入り、
$$
\Phi(U_s\cdot T\cdot U_{-s})_g(x)=\Phi(T)_{g-s}((-s)x)
$$
が成り立つ。$X$ 上には二生成元に同時に不変な Radon 確率 $\nu$ が存在する。実際、任意の $x_0$ の軌道を $[0,n-1]^2\cap G$ で平均して弱 $\ast$ 集積点を取ればよい。これには作用の不変確率の full support は不要である。

$c_g=\int_X\Phi(T)_g(x)\,d\nu(x)$ とする。上の共変性と不変性により $\|\tau_s c-c\|_1\le\|U_s\cdot T-T\cdot U_s\|_\pi$。$\|\pi T-1\|_I\le\eta<1$ なら $\|c\|_1\ge|\sum_g c_g|\ge1-\eta$ である。複素数の絶対値は距離を増やさず、$|c|/\|c\|_1$ は $B_R$ 上の確率だから
$$
\max_{s\in S}\|U_s\cdot T-T\cdot U_s\|_\pi\ \ge\ (1-\eta)\Delta_R.
$$
この下界にはテンソルの正性もノルム1の仮定も要らない。

積を正確に1にした上界を確認する。$p$ を最適な $S_u$ 上の一様確率とし、係数テンソル $D\in C(X)\otimes C(X)$ で $\pi D=1$、$\|D\|_\pi=1$ となるものを使う。任意の有限な係数テスト $\mathcal E$ と $\delta>0$ に対し、$\alpha_{-g}f$（$g\in S_u,f\in\mathcal E$）と $D$ の交換誤差を同時に $\delta$ 以下にできる。実際、有限個の係数をユニタリ $u_1,\ldots,u_k$ とその逆元の線形結合に書き、$v_j=\prod_i u_i^{j_i}$ に対する $v_j\otimes\overline{v_j}$ を $j\in\{0,\ldots,N-1\}^k$ で平均すればよい。各ユニタリとの交換誤差は $2/N$ 以下。ユニタリへの分解には実の縮小元 $h$ に対し $h=\mathrm{Re}(h+i\sqrt{1-h^2})$ を使える。

$$
T_p=\sum_g p(g)\,U_g\cdot D\cdot U_{-g}
$$
は $\pi T_p=1$、$\|T_p\|_\pi=1$ で、二脚の群台は $S_u,-S_u\subset B_R$ に入る。添字を $g\mapsto g+s$ と移すと、$U_s$ との交換誤差は $\|\tau_s p-p\|_1$ 以下。抽出行 $\Phi(T_p)(x)$ は全点で $p$ なので同じ下界も成立する。係数テストの交換誤差は $\delta$ 以下のままである。よって正規化したテンソルの最大生成元欠損は $\Delta_R$ を達成し、$R\to\infty$ と係数近似を合わせると $A$ の bounded approximate diagonal を得る。係数を持つ作用についての結論は、ここで扱った global $\mathbb Z^2$-action に対するものである。

群環における Følner 確率からの近似対角の構成には Stokke の一次文献がある。本記録の固定菱形での等号は上の有限格子と行抽出の証明に基づく。[R. Stokke (2004), Theorem 1.8](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=8)
