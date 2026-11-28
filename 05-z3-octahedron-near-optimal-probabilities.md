# Near-optimal probability distributions on the integer octahedron

**Work in progress.** 2026-11-28

$O=\{x\in\mathbb R^3:\|x\|_1\le1\}$、$B_R=RO\cap\mathbb Z^3$ とする。$B_R$ 上の確率分布 $p$ を球外でゼロとし、$d_i(p)=\|\tau_{e_i}p-p\|_{\ell^1(\mathbb Z^3)}$、$D(p)=\max_{1\le i\le3}d_i(p)$、$\Delta_R=\min_p D(p)$ と書く。

## 近最適分布の極限

整数 $R\to\infty$ で $D(p_R)\le\Delta_R+o(R^{-1})$ とする。$Q=[-1/2,1/2)^3$ とし、セル $(k+Q)/R$ に密度 $f_R=R^3p_R(k)$ を置く。このとき $p_R$ の対称性を仮定せず、
$$
 f_R\ \longrightarrow\ \frac{\mathbf1_{E_\ast}}{|E_\ast|}
 \qquad\text{in }L^1(\mathbb R^3).
$$
ここで $J(f)=\sum_{i=1}^3|D_i f|(\mathbb R^3)$、$P_1(E)=J(\mathbf1_E)$ とし、$h_O$ は $O$ 内の正体積集合における $P_1(E)/(3|E|)$ の最小値とする。既報より $R\Delta_R\to h_O$ であり、$E_\ast$ は測度零を除いて唯一の最小集合である。[離散・連続比較](https://github.com/unti-fourier/thesis-extension-notes/blob/e2a91e14a8431c7c53dfafefed3e36dcc895e29d/05-z3-octahedron-continuum-cheeger-limit.md)・[対称性を仮定しない一意性](https://github.com/unti-fourier/thesis-extension-notes/blob/e2a91e14a8431c7c53dfafefed3e36dcc895e29d/05-z3-octahedron-cheeger-rigidity.md)

**証明。** 各セル面の面積は $R^{-2}$ で、その面を挟む密度の差は $R^3$ 倍の格子差である。球外との面も一度ずつ数えると
$$
 J(f_R)=R\sum_{i=1}^3 d_i(p_R)\le3R D(p_R)=3h_O+o(1).
$$
$f_R\ge0$、$\int f_R=1$ で、台は $(1+3/(2R))O$ に入る。従って BV コンパクト性により任意の部分列から $L^1$ 収束部分列を取れる。極限 $f$ は $O$ に支えられる質量1の非負関数で、変動の下半連続性から $J(f)\le3h_O$。一方、$E_t=\{f>t\}$ と置くと、方向別の coarea 公式と層別積分より
$$
 J(f)=\int_0^\infty P_1(E_t)\,dt
 \ge 3h_O\int_0^\infty |E_t|\,dt=3h_O .
$$
等号なので、ほとんどすべての $t>0$ で、正体積の $E_t$ は $E_\ast$ に測度同値である。層別積分と Fubini により $f$ は $\mathbf1_{E_\ast}$ の定数倍で、質量1がその定数を $1/|E_\ast|$ に決める。全ての集積点が一致し、全列の収束を得る。

## 固定半径での次善値による評価

$R\ge1$ を固定する。非空な $F\subseteq B_R$ について、$P(F)$ を全格子での無向辺境界数、$\phi(F)=P(F)/(3\#F)$、$u_F=\mathbf1_F/\#F$ とする。既報の $\Delta_R=\min_F\phi(F)$ を用いる。最小集合 $F_\ast$ が一意であれば、次善値との差 $\gamma_R=\min_{F\ne F_\ast}(\phi(F)-\Delta_R)$ は正であり、どの確率 $p$ にも
$$
 \|p-u_{F_\ast}\|_{\ell^1}\le
 \min\left\{2,\,\frac{2(D(p)-\Delta_R)}{\gamma_R}\right\}
$$
が成り立つ。[離散最適化と一意性判定、§§1・4](https://github.com/unti-fourier/thesis-extension-notes/blob/e2a91e14a8431c7c53dfafefed3e36dcc895e29d/05-z3-octahedron-exact-optimization.md)

実際、$F_t=\{p>t\}$ に重み $d\nu(t)=\#F_t\,dt$ を与えると、$\nu$ は $(0,\infty)$ 上の確率測度であり、空の層を除いて $p=\int u_{F_t}\,d\nu(t)$ である。離散 coarea により $\int\phi(F_t)\,d\nu(t)=\tfrac13\sum_i d_i(p)\le D(p)$。従って $F_t\ne F_\ast$ の層の重みは $(D(p)-\Delta_R)/\gamma_R$ 以下であり、その各層で確率間の距離は高々2である。

$3\Delta_R=a/b$ を既約分数（$b>0$）で表せば、$F\ne F_\ast$ では $bP(F)-a\#F$ が正の整数なので、$\gamma_R\ge 1/(3b\#B_R)$ も従う。

## 半径6〜10の有限計算

全格子の最小カットと downset 上の計算が一致した値を示す。上の整数 $a,b$ を使うと、始点側の格子点集合 $F$ のカット容量は $a\#B_R+bP(F)-a\#F$ である。$F_{\max}$ は包含最大の最適集合を表す。

| $R$ | $\#F_{\max}$ | $\Delta_R$ | $P(F_{\max})$ |
|---:|---:|---:|---:|
| 6 | 251 | $90/251$ | 270 |
| 7 | 311 | $98/311$ | 294 |
| 8 | 557 | $154/557$ | 462 |
| 9 | 649 | $162/649$ | 486 |
| 10 | 1039 | $234/1039$ | 702 |

上の二つの結論は書面証明である。表では5行の $bP(F_{\max})=a\#F_{\max}$ を整数算術で検算した。この5半径での離散最小集合の一意性は未判定であり、本補遺は Lean 未検証である。
