# 拡張7　安定化群の位数が一様有界なときの行列再構成

> **Work in progress.** 博士論文の拡張方針7に関する研究ノート。投稿原稿・査読済み論文・業績一覧の項目ではない。この版では以下の主張と証明を文章で独立に検算した。Lean による形式検証と既存文献に対する新規性確認は済んでいない。

非空コンパクト Hausdorff 空間 $X$ に離散群 $\Gamma$ が作用し、$d=\sup_{x\in X}|\Gamma_x|<\infty$ とする。$\Lambda=\bigcup_x\Gamma_x$、群、共役軌道の数は無限でもよい。

## 結論

$A=C(X),\ M=A^{**},\ B=A\rtimes_r\Gamma,\ N=\ell^\infty(\Gamma,M),\ U=N/\iota M$（$\iota M$ は定数列）、$S=\mathbb B(\ell^2\Gamma)\bar\otimes M$。$W=CB_M(U,M),\ \mathcal V=CB_M^\Gamma(U,S)$。$\pi(f)_{tt}=\alpha_{t^{-1}}f,\ u_g=\lambda_g\otimes1,\ (\beta_g a)(t)=\alpha_g a(g^{-1}t),\ (\gamma_gY)_{s,t}=\alpha_gY_{sg,tg}$ とし、$\mathcal V$ は $\Phi\beta_g=\gamma_g\Phi$ を満たす写像からなる。値への乗法で $B$ が作用する。$U$ の $M$-作用は座標ごとの乗法から誘導される。$HH^1_{\rm cb}$ は cb derivation を inner derivation で割り、$H_b^1$ は有界1-cocycle を coboundary で割る。ここでは $\partial\xi(g)=g\xi-\xi$, $\operatorname{ad}_T(b)=[b,T]$ とする。

$p_k=\mathbf1_{\operatorname{Fix}(k)}\in M,\ H_k=C_\Gamma(k),\ g\star w=\alpha_gw\beta_{g^{-1}}$ とする。各軌道から一つの $k$ を選べば
$$
 HH^1_{\rm cb}(B,\mathcal V)
  \ \cong\ H_b^1(\Gamma,E)
  \ \cong\ \prod_{[k]\in\Lambda/{\rm Ad}\Gamma}^{\ell^\infty}
       H_b^1(H_k,p_kW),\qquad
 E=\prod_{k\in\Lambda}^{\ell^\infty}p_kW,\quad
 (g\diamond w)_k=g\star w_{g^{-1}kg}.
$$
右端は**各類の商ノルムの上限が有限な族**であり、その上限をノルムとする。群側どうしの同型は等長。Hochschild 側からの圧縮は縮小、逆のノルムは $2d$ 以下である。実際の inner と coboundary で割る。右端を各因子のコホモロジーを取った後の積として書くには、後述の実装元の一様評価を使う。$p_kW$ の入力には $\Gamma$ 全体の座標がある。

## 中心射影の重なりと測度

$\langle p_k,\mu\rangle=\mu(\operatorname{Fix}(k))$ は任意の正則正測度 $\mu\in M_*$ で成り立つ。有限集合 $J\subset\Gamma$ について
$$
 \left\langle\sum_{k\in J}p_k,\mu\right\rangle
  =\int_X|J\cap\Gamma_x|\,d\mu(x)\le d\mu(X).
$$
よって増加する有限部分和は $M_+$ で上限 $P\le d1$ をもつ。任意の忠実正規表現 $\sigma:M\to\mathbb B(\mathcal H)$ でこのネットは $\sigma(P)$ に強収束し（退化表現では $\sigma(1)\mathcal H$ 上で考える）、$\sum_k\|\sigma(p_k)\zeta\|^2\le d\|\zeta\|^2$。添字が非可算でも、和は有限部分和の上限である。位数 $d$ の安定化群をもつ点で評価すれば $\|P\|=d$。

$\Lambda$ が可算なら単調収束により $P$ は有界 Borel 関数 $x\mapsto|\Gamma_x|$ の $M$ における像である。非可算の場合、二つは実際に違い得る。$\mathbb T_{\rm d}\rtimes C_2$ が円に回転と鏡映 $r_a(x)=a\bar x$ で作用すると、各点の安定化群の位数は2。各鏡映は $x^2=a$ の二点を固定する。従って $P=1+p_{\rm at}$、ここで $p_{\rm at}=\bigvee_{x\in\mathbb T}p_{\{x\}}$。円の Haar 確率を $M$ 上の正規状態として読むと $p_{\rm at}$ の値は0で、$P\ne2\,1$ である。射影の重なりの上界には有限部分和だけで足り、全添字に共通する測度零集合の選択を要しない。

## 行と列の Schur 評価

行列 $a_{s,t}\in M_m(M)$ が $\|a_{s,t}\|\le C$ を満たし、$q_{s,t}=1_m\otimes\sigma(p_{t^{-1}s})$ に両側から支えられるとする。これは正則表現の $\pi(A)'$ の台である。$(s,t)$ 成分の交換子には $x\mapsto f(sx)-f(tx)$ が掛かり、生成する閉イデアルの零点が $\operatorname{Fix}(t^{-1}s)$ だからである。固定した列では $s\mapsto t^{-1}s$、固定した行では $t\mapsto t^{-1}s$ が全単射である。有限台ベクトル $\xi,\eta\in\ell^2(\Gamma,\mathcal H^m)$ に対し
$$
 \left|\sum_{s,t}\langle a_{s,t}\xi_t,\eta_s\rangle\right|
 \le C\left(\sum_{s,t}\|q_{s,t}\xi_t\|^2\right)^{1/2}
       \left(\sum_{s,t}\|q_{s,t}\eta_s\|^2\right)^{1/2}
 \le d C\|\xi\|\|\eta\|.
$$
これで行列は一意な有界作用素を定める。有限行・列の主圧縮の強極限なので $\mathbb B(\ell^2\Gamma)\bar\otimes M_m(M)$ に属する。評価は $m$ に依存しない。右帯を有限個ずつ取る場合にも、上の第1因子の平方和の尾部で各 $\xi$ 上の強収束が従う。ノルム収束は再構成の仮定に含めない。

$E_0$ を $E$ の作用を忘れた空間として
$$
 (\mathcal J f)(v)_{th,t}=f(t)_h(v),\qquad
 \mathcal J:\ell^\infty(\Gamma,E_0)\longrightarrow CB_M(U,\pi(A)'\cap S)
$$
とする。右帯の添字 $h$ が $\Lambda$ に属さない成分は零。入力 $v$ の行列増幅を上式の $a_{s,t}$ とし、さらに $f$ の行列増幅も合わせれば $\|\mathcal J\|_{\rm cb}\le d$。逆は各成分の読み出しで完全縮小である。

この再構成定数 $d$ は最良である。実際、行列 $a_{s,t}=p_{t^{-1}s}$ は位数 $d$ の $\Gamma_x$ に行・列を制限し、$p_{\{x\}}$ 上で評価すると全成分1の $d\times d$ 行列になる。$\Gamma\ne\{e\}$ ならこれは実際の $\mathcal J$ の入力でも実現する。$g_0\ne e$ を選び、$l(qF)=(F(e)-F(g_0))/2$ として $f(t)_h=p_hl$ と置く。$q:N\to U$ は商写像。$\|f\|\le1$ で、$F(e)=1,F(g_0)=-1,\|F\|=1$ においてこの行列が出る。従って有限 $\Lambda$ の場合も従来の $|\Lambda|$ を $d$ に改善できる。比較の逆に対する $2d$ は交換子評価による上界である。

## Derivation と軌道ごとの制限

$R\Phi=(p_k\Phi(\cdot)_{k,e})_k,\ j\xi(t)=t^{-1}\diamond\xi$ とする。共変性から $\mathcal Jj(E)$ は $\mathcal V$ のうち値が $\pi(A)'$ に入る部分であり、$R$ がその逆である。任意の $D$ の比較 cocycle は $g\mapsto R(D(u_g)u_g^*)$。逆に有界 cocycle $c:\Gamma\to E$ には $a_c(t)=c(t^{-1}),\ T_c=\mathcal Ja_c,\ D_c(b)(v)=[b,T_c(v)]$ を取る。右添字 $h=t^{-1}s$ は行・列の同時左移動で保存され、$(\ell_g a_c-a_c)(t)=t^{-1}\diamond c(g)$。よって $D_c(u_g)u_g^*=\mathcal Jj(c(g)),\ D_c|_A=0,\ D_c(B)\subset\mathcal V$。二重の行列増幅で交換子を評価すれば $\|D_c\|_{\rm cb}\le2d\|c\|_\infty$。$c=\partial\xi$ なら $j\xi-a_c$ は定数関数で、その $\mathcal J$ 像は $B'$ に入り $D_c={\rm ad}_{\mathcal Jj\xi}$。逆向きでは、`D` をまず `A` 上で零にする。$\mathcal V$ の閉単位球は点ごとの弱*位相でコンパクトである。実際、$S$ は双対空間で、有界な素の写像、全行列ノルムの評価、$M$-線形性、共変性はいずれも点ごとの弱*極限で保存される。単位的可換代数 $A$ のユニタリ群は可換なので、不変平均で $D(v)v^*$ を平均した元 $Q\in\mathcal V$ を取れる。cocycle 等式から $D(v)v^*=Q-vQv^*$ となり、$D|_A=\operatorname{ad}_{-Q}|_A$（ユニタリの線形包が $A$ 全体）。そこで $D'=D-\operatorname{ad}_{-Q}$ と置く。

比較を定義するときは、$\Phi\mapsto R\Phi$ が共役作用 $\Phi\mapsto u_g\Phi u_g^*$ と $\diamond$ を intertwine することに注意する。実際、成分 $(k,e)$ は $(g^{-1}k,g^{-1})$ に移動し、共変性で $(g^{-1}kg,e)$ の成分に戻る。従ってこの圧縮は cocycle と coboundary を保ち、ノルムは1以下である。$D'|_A=0$ なら $u_ga=\alpha_g(a)u_g$ を微分して $D'(u_g)u_g^*$ の値が $\pi(A)'$ に入ると分かる。従って $D'$ は圧縮した cocycle から上の $D_c$ として復元できる（両者は $A$ と全 $u_g$ 上で一致する）。これで最初の同型と両方向のノルム評価が従う。

一軌道では $r_jkr_j^{-1}=j,\ r_k=e$ を選ぶ。$h\in H_k\mapsto c(h)_k$ という制限の逆は $\widetilde b(g)_j=r_j\star b(r_j^{-1}g r_{g^{-1}jg})$ で、両写像は縮小である。制限して戻した差は $\partial(j\mapsto c(r_j)_j)$ で、この実装元のノルムも $\|c\|_\infty$ 以下。したがって軌道数にかかわらず、群側は一様有界な軌道 cocycle 族を**一様有界な実装元をもつ** coboundary 族で割ったものに等しい。これは次数1の Eckmann–Shapiro 対応を一様に適用した計算である。[Monod（2001）、命題10.1.3](https://link.springer.com/chapter/10.1007/3-540-44962-0_5) ／ [Moraschini–Raptis（2023）、命題2.3.3](https://arxiv.org/html/2105.02821)

## なぜこの係数では因子の商ノルムだけでよいか

次の補題で実装元の一様性を独立に確認する。可換 von Neumann 代数 $D$ を単位的可換 $C^*$ 代数 $C$ の単位を共有する部分環とし、群 $H$ が包含を保ち、$D$ 上で正規に作用するとする。$V$ を $C\to D$ の有界 $D$-線形写像で $D$ 上零となるものの空間とする。値が可換なので cb ノルムは作用素ノルムに等しい。群作用 $hw=\alpha_h w\beta_{h^{-1}}$ の変位を $\delta=\sup_h\|h w-w\|$ とすると、群・代数に依存しない評価
$$
 \operatorname{dist}(w,V^H)\le 300\,\delta
$$
が成り立つ。ここで300は軌道に依存しない一つの上界である。

**正写像の近似。** まず正の $D$-線形写像 $L:C\to D$ を扱う。可換な $D,C^{**}$ の標準 Hilbert 空間を $K_D,K_C$ とし、後者で $C$ の元は乗法作用素として表す。任意の正規正汎関数 $\mu\in D_*$ について
$$
 V_L\sqrt\mu=\sqrt{\mu\circ L}
$$
は $D$-線形な作用素 $K_D\to K_C$ を定める。右辺は $C$ 上の任意の正汎関数を $C^{**}$ の正規汎関数として扱うため、$L$ の正規性は要らない。実際、$\mu,\nu$ を $\rho=\mu+\nu$ に対する密度 $a,b\in D_+$ で書けば、$D$-線形性から $(a\rho)\circ L=a(\rho\circ L)$。平方根ベクトルの和は $(\sqrt a+\sqrt b)\sqrt\rho$ なので上の指定は正錐で加法的となり、複素線形に延びる。$V_L^*cV_L=L(c),\ \|V_L\|\le\sqrt{\|L\|}$。正写像 $L,L'$ に対し $\|V_L-V_{L'}\|^2\le\|L-L'\|$ である。これは単位正ベクトルで二測度の共通支配測度を取り、$(\sqrt a-\sqrt b)^2\le|a-b|$ を積分すればよい。任意の単位ベクトルは正の平方根ベクトルに $D$ の偏角を掛けて書ける。群作用は両標準空間にユニタリとして作用し $V_{hL}=hV_L$ を満たす。[Haagerup（1975）、von Neumann 代数の標準形](https://doi.org/10.7146/math.scand.a-11606)

この $D$-線形作用素の空間を $\mathscr T$ とする。可換な $D$ の標準表現では $D'=D$ なので任意の二元 $T,Z\in\mathscr T$ について $T^*Z\in D$。有界な軌道 $\mathscr O=HV_L$ に対し $r(T)=\sup_{Z\in\mathscr O}(T-Z)^*(T-Z)\in D_+$ と置く。二候補 $T_1,T_2$ を $r(T_1)\le r(T_2)$ となるスペクトル射影とその補射影で貼り合わせると、二つの半径の小さい方が点ごとに実現する。よって $r(T_i)\downarrow r_*=\inf_T r(T)$ となる有界な候補のネットを取れる（初めに $r(0)$ と小さい方を取る）。平行四辺形の恒等式から
$$
 (T_i-T_j)^*(T_i-T_j)/4
 \le (r(T_i)+r(T_j))/2-r_* .
$$
従って $T_i$ は強 Cauchy。作用素の $D$-線形性は強閉であり、強極限 $Y$ はすべての $Z\in\mathscr O$ に対し $(Y-Z)^*(Y-Z)\le r_*$ を満たす。同じ不等式により最小点は一意。群が半径の順序を保つので $Y$ は群不変で、$\|Y-V_L\|\le\sup_h\|hV_L-V_L\|$。これより $Q(c)=Y^*cY\in D$ は不変な正の $D$-線形写像であり、$\|L\|\le R,\ \sup_h\|hL-L\|\le\delta$ なら
$$
 \|L-Q\|\le 2\sqrt{R\delta}+\delta .
$$

**定数上零の条件。** 自己共役な $w$ は $w=w^+-w^-$ と書ける。$w^+(a)=\sup_{0\le b\le a}w(b)$（$a\ge0$）で、可換な定義域の区間分解から加法性を得る。$D$ の正可逆元による乗法で区間を移し、極限を取れば $D$-線形性が従う。$|S^+-T^+|\le|S-T|$ と $\||S-T|(1)\|\le\|S-T\|$ はこの上限式から従う。従って $w^\pm$ のノルムは $\|w\|$ 以下、各変位は $\delta$ 以下である。上で得た不変な近似 $Q_\pm$ について $T=Q_+-Q_-,\, L=Q_++Q_-$ と置く。$T(1)/L(1)$ を $L(1)$ の台の外で零とすれば、有界な不変元 $\lambda\in D$ になる。$T-\lambda L$ は $D$ 上零の不変写像で、補正のノルムは $\|T(1)\|\le\|T-w\|$。複素 $w$ を自己共役な実部・虚部に分けて足すと、$r=\operatorname{dist}(w,V^H)$ は $r\le16\sqrt{\|w\|\delta}+8\delta$ を満たす。不変元を引いて $\|w\|\downarrow r$ とすると、$\delta=0$ なら $r=0$、それ以外では $r/\delta\le(8+\sqrt{72})^2<300$。これで補題が従う。

各軌道に $D=p_kM,\ C=p_kN,\ H=H_k$ を適用すると、商 $U$ と $M$-線形性により上の $V$ は $p_kW$ と等長に同じである。従って coboundary は各因子で閉。さらに $\sup_k\|\partial w_k\|<\infty$ なら、不変元を引いて同じ coboundary を実装する一様有界な $w_k'$ を選べる。以上で軌道ごとの類への写像の単射性が従う。商ノルムが一様有界な類族は、各商ノルムから同じ $\varepsilon>0$ 以内の代表を選び持ち上げられる。これで全射性と等長性も従う。この実装元の議論は、一般の Banach 係数に対する積との交換を仮定していない。

## 無制限の直積を排除する例

円 $\mathbb R/\mathbb Z$ 内の可算無限ランクの自由アーベル部分群 $L$ を取る（1と合わせて有理数体上一次独立な実数列の像で生成できる）。$\Gamma=(L\rtimes\{\pm1\})\times F_2$ を $X=\mathbb T\times\widehat{F_2}$ に、回転・鏡映と左移動で作用させる。安定化群の位数は高々2。鏡映 $r_a(x)=a-x$ の共役軌道は $a\bmod 2L$ で分類され、無限にある。$L$ は2捩れをもたないので $H_{r_a}=\langle r_a\rangle\times F_2$。

各軌道で $j_a(h)(qF)=p_{r_a}(F(h)-F(e))$ を取る。円の一固定点での Dirac 測度と $\widehat{F_2}$ の Haar 確率の積を出力に、$F_2$ のスカラー列の引戻しを入力に用い、$F_2$ に制限すれば $j_a$ は同じ古典的 Johnson 類に縮小写像で移る。この類の商ノルムは正である。零に近づけられれば、質量1の汎関数の変位を零に近づけられ、全変動の正規化の弱*集積点が $F_2$ の不変平均となる。よって互いに異なる軌道 $a_n\bmod2L$ に置いた $n[j_{a_n}]$ は、個々には正当な類で、商ノルムの上限は無限。無制限の直積には含まれるが、ひとつの cb derivation の像には入らない。[Brodzki–Niblo–Nowak–Wright（2012）、定義18・定理B](https://arxiv.org/html/1004.0295)
