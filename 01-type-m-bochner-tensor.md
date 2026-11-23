# Type (M) 加群の row 完備化と Bochner (L^1)

**Work in progress, November 2026.** 後続論文に向けた途中経過であり、投稿論文、査読済み成果、業績一覧の項目ではありません。優先性は主張しません。

方針③ではスカラー核のねじり畳み込みと積のノルム評価を扱った。方針①の中心に置くのは、その row 完備化 $S$ に係数加群 $E$ を入れると、点ごとの加群作用が複素線形等長同型 $E\widehat\otimes_{C(X),\pi}S \simeq L^1(G,\mu;E)$ を与える、という補題である。

## 仮定と同定

$G$ を第二可算局所コンパクト Hausdorff 群、$\mu$ を正則左 Haar 測度、$X$ を非空コンパクト Hausdorff 空間とし、$R=C(X,\mathbb C)$ と置く。複素 Banach 空間 $E$ は単位的な複素双線形右 $R$ 加群で、各 $e\in E$ で $f\mapsto e\cdot f$ はノルム連続とする。Type (M) の仮定は、任意の $e$ と任意の有限族 $p_i\in C(X,\mathbb R)_+$ に対する次の評価である。非負の実関数は自然に $R$ に含める。[Nicolas Monod（2011年刊行、2010年プレプリント）、式 (M)](https://arxiv.org/abs/1004.0199)

$$
\sum_i\|e\cdot p_i\|\ \le\ \|e\|\,\Big\|\sum_i p_i\Big\|_\infty .
$$

$K=C_c(G,R)$ に $\rho(k)=\sup_{x\in X}\int_G|k(t)(x)|\,d\mu(t)$ を入れる。写像 $\iota k(x)=[t\mapsto k(t)(x)]$ は方針③のノルム公式と稠密性により、$\widehat K^\rho$ から $S=C(X,L^1(G,\mu;\mathbb C))$ への全射等長同型に延びる。$R$ は $S$ に $(fs)(x)=f(x)s(x)$ で作用し、$j(h)(x)=h$ は $X$ に関する定数プロファイルである。

$Y=L^1(G,\mu;E)$ とする。$H=E\widehat\otimes_{R,\pi}S$ は、$T=E\otimes_R S$ に半ノルム $\pi(z)=\inf_{z=\sum_i e_i\otimes s_i}\sum_i\|e_i\|\|s_i\|$（有限分解）を入れた分離完備化で、$\eta:T\to H$ を標準写像とする。$A:S\to\mathcal L(E,Y)$ は $A(\iota k)e=[t\mapsto e\cdot k(t)]$ で定まる係数作用である。複素線形縮小写像 $I:H\to Y$ と $J:Y\to H$ に求める公式は、すべての $e\in E$、$s\in S$、有限測度の可測集合 $F\subseteq G$ について

$$
I\eta(e\otimes s)=A(s)e,\qquad J(\mathbf1_F e)=\eta(e\otimes j(\mathbf1_F)).
$$

後者の右辺の族が $H$ を閉加法群として生成すれば、$IJ=\mathrm{id}_Y$、$JI=\mathrm{id}_H$ が従い、$J$ は $I$ を逆とする等長全射になる。

## 証明の要点

1. **複素係数での定数 $1$。** 有限個の $f_i\in R$ を、共通の非負の単位分割 $p_j$ により $\sum_j f_i(x_j)p_j$ で一様近似する。三角不等式で各 $\|e\cdot p_j\|$ に掛かる係数は $\sum_i|f_i(x_j)|$ なので、(M) より $\sum_i\|e\cdot f_i\|\le\|e\|\sup_x\sum_i|f_i(x)|$ を得る。単関数の各セルの測度を係数に掛け、Bochner $L^1(G,\mu;R)$ で近似すると $\int_G\|e\cdot k(t)\|\,d\mu(t)\le\|e\|\rho(k)$。従って $A$ は一意に延び、$\|A\|\le1$ である。

2. **Balancing と定数プロファイル。** $A(\iota k)(e\cdot f)$ と $A(f\,\iota k)e$ はともに $[t\mapsto e\cdot(fk(t))]$ である。$\iota K$ の稠密性で $A(s)(e\cdot f)=A(fs)e$ が従う。$h\in C_c(G,\mathbb C)$ には核 $k(t)=h(t)1_R$ を使うと、単位性から $A(jh)e=he$ を得る。ここで $he=[t\mapsto h(t)e]$。スカラー核の $L^1$ 稠密性でこの式は全 $h\in L^1(G,\mu;\mathbb C)$ に延びる。Balancing と第1項の評価から、純テンソル上の $I$ は $H$ 上の縮小写像を定める。$J$ は互いに素なセルの単関数上で上の公式を線形に延ばす。共通細分で表示独立性が従い、$\|j(\mathbf1_F)\|=\mu(F)$ より像のノルムは $\sum_i\mu(F_i)\|e_i\|$ 以下である。これは元の単関数の $L^1$ ノルムなので、$J$ は縮小的に $Y$ 全体へ延びる。

3. **両側合成。** $A(j(\mathbf1_F))e=\mathbf1_F e$ より $IJ$ は各ベクトル値指示関数を固定し、その線形包は $Y$ に稠密である。一方、分割の一で各 $s\in S$ を $\sum_j f_j j(h_j)$ で一様近似できる。各 $h_j$ をスカラー単関数で近似し、係数を balancing で $E$ 側へ移すと、$\eta(e\otimes j(\mathbf1_F))$ の線形包は $H$ に稠密となる。複素定数も $e$ に吸収できるので、閉加法群としての生成性も従う。これらの元はすべて $J(Y)$ に属する。$JI$ は $IJ=\mathrm{id}_Y$ により $J(Y)$ 上で恒等、従って $H$ 上で恒等である。最後に $\|y\|=\|I(Jy)\|\le\|Jy\|\le\|y\|$。

## 検証範囲

Lean 4.27.0 では、row 等長同型 `rowEquiv` と、積分評価を入力とする $A$ の延長・balancing・定数プロファイル公式を検証済みである。`completed_tensor_connection` は同じ $S$ と $H$ を使い、評価写像の存在と純テンソル公式、指示関数テンソルの閉加法群としての生成性、指定した縮小写像 $J$ のセル公式を引数にして、両側合成と等長性まで型検査している。Type (M) からの積分評価およびこれら三入力については、旧ソースの個別定理と仮定・型を書面で照合した。旧定理を名前で同時に読み込む一括検証は未実施である。
