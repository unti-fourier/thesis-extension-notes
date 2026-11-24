# Étale groupoid の積分不変性から Reiter 場へ

**Work in progress, November 2026.** 後続論文に向けた途中経過であり、投稿論文、査読済み成果、業績一覧の項目ではありません。優先性は主張しません。

## 定理

\(G\rightrightarrows X\) は局所コンパクト Hausdorff étale groupoid、\(X\) は非空コンパクト、\(\lambda\) は full continuous left Haar system とする。\(A=A_r\) は \(C_c(G,\mathbb C)\) の range ノルム完備化、\(P=C(X,\mathbb C)\)。\(R\) は range 質量、\(L_a z=a\ast z\)、\(\ell_v z=(v\circ r)z\)、\(\Delta_a=L_a-\ell_{Ra}\) と書く。矢 \(\gamma:y\to x\) による左移動は
\[
 \Lambda_\gamma:L^1(G^y,\lambda^y)\longrightarrow L^1(G^x,\lambda^x),
 \qquad (\Lambda_\gamma z)(\eta)=z(\gamma^{-1}\eta)
\]
で、左 Haar 不変性による等長写像である。\(d_z(\gamma)=\|\Lambda_\gamma z_y-z_x\|_1\) とおく。

次の条件は同値である。

1. 次に定義する制限テスト付き derivation \(D_J^\sharp\) が inner である。ここで \(J:P\to A\) は \(RJ=\mathrm{id}_P\) を満たす有界線形切断である。
2. \(R^{\ast\ast}m=\kappa_P(1)\)、\(\Delta_a^{\ast\ast}m=0\) をすべての \(a\in A\) について満たす \(m\in A^{\ast\ast}\) がある。
3. 各コンパクト \(C\subset G\) と各 \(\varepsilon>0\) に対し、\(p\in C_c(G)_+\)、\(Rp=1\)、\(\sup_{\gamma\in C}d_p(\gamma)<\varepsilon\) が成り立つ。

係数を明記する。\(K=\ker R\)、\(K^\sharp=\overline{\operatorname{span}}\{\phi\circ L_a:\phi\in K^*,a\in A\}\)、\(E=P\widehat\otimes_\pi K^\sharp\) とする。\(M_a p=R(a(p\circ s))\) に対し
$
\langle D_J^\sharp(a),p\otimes\eta\rangle
 =\eta(a*Jp-J(M_a p)).
$
双対係数の左作用は \(K\) 上の左畳み込みの随伴、右作用は \(M_a\) による前合成である。

条件3は topological amenability の Reiter 表示である。条件2の入力には正値性もノルム1も仮定しない。以下ではまず counting Haar 系を用い、最後に所与の \(\lambda\) に戻す。

## Ample の局所テスト

開 bisection \(B\) では \(r|_B:B\to rB\)、\(s|_B:B\to sB\) がともに同相であり、\(x\in rB\) に対応する唯一の矢を \(\beta_x=(r|_B)^{-1}(x)\) とする。コンパクト開の \(B\) に対しては \(1_B\in C_c(G)\)、\(R1_B=1_{rB}\)。従って
\[
 (\Delta_{1_B}z)_x=\Lambda_{\beta_x}z_{s\beta_x}-z_x\quad(x\in rB),
 \qquad \|\Delta_{1_B}z\|_r=\sup_{\gamma\in B}d_z(\gamma).
\]
\(rB\) の外の行は零である。部分性は \(1_{B^{-1}}\ast1_B=1_{sB}\)、\(1_B\ast1_{B^{-1}}=1_{rB}\) にも現れる。ample なら任意のコンパクトな矢集合を有限個のこのような \(B\) で覆える。

## Hausdorff étale の cutoff

開 bisection \(B\) に台を持つ \(b\in C_c(B)\) を \(G\) に零延長する。\(x\in rB\) で \(Rb(x)=b(\beta_x)\)。\(\eta\in G^x\) を固定して畳み込みの和を展開すると、寄与しうる第1因子は \(\beta_x\) だけである。従って
\[
 (\Delta_b z)_x=b(\beta_x)(\Lambda_{\beta_x}z_{s\beta_x}-z_x),\qquad
 \|\Delta_b z\|_r=\sup_{\gamma\in B}|b(\gamma)|\,d_z(\gamma).                 \tag{1}
\]
ここでも \(x\notin rB\) の行は零。コアで計算した式は行ノルム連続性で \(z\in A\) にも延びる。

空でないコンパクト \(C\) を固定する。各矢のまわりで開集合 \(V\) の閉包がコンパクトで開 bisection \(B\) に含まれるように取り、有限被覆 \(V_1,\ldots,V_n\) を選ぶ。局所コンパクト Hausdorff 空間の cutoff により \(0\le b_j\le1\)、\(b_j\in C_c(B_j)\)、\(b_j=1\) on \(\overline{V_j}\) とできる。(1) から、すべての \(z\) に同じテストで
\[
 \sup_{\gamma\in C}d_z(\gamma)\le\max_{1\le j\le n}\|\Delta_{b_j}z\|_r.       \tag{2}
\]
ample の場合は \(b_j=1_{B_j}\) を取ればよい。被覆の重なりはこの上限評価に影響しない。

## 積分不変な元から正の Reiter 場へ

**質量補正。** Goldstine とコアのノルム稠密性により、\(m\) に弱スター収束する一様有界なネット \(v_i\in C_c(G,\mathbb C)\) を取る。具体的には Goldstine の近似をコアでノルム誤差 \(\delta\) まで近似し、\(\delta\downarrow0\) も添字に加える。\(Rv_i\rightharpoonup1\) は \(P\) の弱収束である。単位空間は clopen かつコンパクトなので、単位矢上の関数を零延長する等長切断 \(J_0:P\to C_c(G)\) が使える。
\[
 w_i=v_i+J_0(1-Rv_i).
\]
\(Rw_i=1\) が全ての \(i\) で厳密に成り立つ。任意の \(\Phi\in A^\ast\) に対し \((\Phi\circ J_0)(1-Rv_i)\to0\) なので、補正後も \(w_i\to m\) 弱スターであり、\(\|w_i\|_r\le1+2\|v_i\|_r\) である。

**同時凸化。** (2) のテストを先に選び、\((\Delta_{b_j}w_i)_{j=1}^n\) を最大ノルムの積 \(A^n\) に入れる。各座標で \(\Phi(\Delta_{b_j}w_i)\to m(\Phi\circ\Delta_{b_j})=0\)。有限積の双対汎関数は座標汎関数の和なので、ベクトル全体が弱く零に収束する。Hahn–Banach により各 tail の凸包の弱閉包とノルム閉包は一致する。従って任意の \(\tau>0\) に対し、同じ tail の \(w_i\) の一つの有限凸結合 \(w\) で
\[
 w\in C_c(G,\mathbb C),\qquad Rw=1,\qquad
 \max_{1\le j\le n}\|\Delta_{b_j}w\|_r<\tau .
\]
凸係数が全テストで共通であるため、(2) は \(C\) 全体で \(\sup_C d_w<\tau\) を与える。

**正の行への正規化。** \(t(x)=R|w|(x)=\|w_x\|_1\) は連続で \(t(x)\ge|Rw(x)|=1\)。\(p=|w|/(t\circ r)\) は連続コンパクト台、非負、\(Rp=1\)、\(\|p\|_r=1\) を満たす。\(u=\Lambda_\gamma w_{s\gamma}\)、\(v=w_{r\gamma}\)、\(\alpha=\|u\|_1\)、\(\beta=\|v\|_1\) と書く。左移動は絶対値を保つので
\[
 d_p(\gamma)=\left\| \frac{|u|}{\alpha}-\frac{|v|}{\beta}\right\|_1
 \le\frac{\|\,|u|-|v|\,\|_1+|\alpha-\beta|}{\alpha}
 \le 2d_w(\gamma).
\]
\(\tau=\varepsilon/2\) とすればよい。空の \(C\) では \(p=J_0(1)\) で十分。コンパクト集合を包含で、許容誤差を逆順で有向化すると正の Reiter ネットを得る。各 \(p\) は \(\int h\,p\,d\lambda^x=R(hp)(x)\) が \(h\in C_c(G)\) ごとに連続なので、連続な確率測度系を与える。

## 同値の確認

条件3のネットを \(p_i\) とする。行ごとに全ての第1因子を足し合わせると、\(a\in C_c(G)\) に対して
\[
 \|\Delta_a p_i\|_r\le\|a\|_r\sup_{\gamma\in\operatorname{supp}a}d_{p_i}(\gamma).
\]
\(\|\Delta_{a-c}p_i\|_r\le2\|a-c\|_r\) と稠密性により任意の \(a\in A\) でも欠損は 0 に収束する。単位球での弱スター集積点 \(m_+\) は条件2を満たす。各 \(p_i\) の正値性が極限に移り、\(\|R\|=1\) と \(R^{\ast\ast}m_+=\kappa_P(1)\) から \(\|m_+\|=1\) である。

\(D_J^\sharp\) が inner なら、実装元を \(S:P\to(K^\sharp)^*\) と書く。ここでは \(A\) が単位的なので \(K^\sharp=K^*\)。従って \(S\) を \(A^{**}\) に含めて \(\Sigma=\kappa_A J-S\) と置けば、inner の恒等式が \(\Sigma(M_ap)=L_a^{**}\Sigma(p)\) を与え、\(R^{**}\Sigma(p)=\kappa_P(p)\) となる。係数 \(v\in P\) を単位矢上の密度として \(A\) に入れれば、\(\Sigma(v)=\ell_v^{**}\Sigma(1)\) となる。よって \(m=\Sigma(1)\) が条件2を満たす。逆に条件2から \(\Sigma(p)=\ell_p^{\ast\ast}m\) とすると、\(R^{\ast\ast}\Sigma=\kappa_P\)。\(L_a\ell_p=L_{a(p\circ s)}\)、\(R(a(p\circ s))=M_a p\) により \(L_a^{\ast\ast}\Sigma(p)=\Sigma(M_a p)\)。従って \(\kappa_A J-\Sigma\) は \(\ker R^{\ast\ast}=(\ker R)^{\ast\ast}\) に値を取り、これを制限テスト上で評価すると \(D_J^\sharp\) の実装元になる。ここでは単位元 \(1_X\) があるので実際に \(K^\sharp=K^\ast\)（\(K=\ker R\)）である。この同値の対象はこの特定の derivation である。

位相的従順性を連続な確率測度系 \(x\mapsto\mu^x\) の近似不変性で定義した場合にも条件3が得られる。étale では \(h(\gamma)=\mu^{r\gamma}(\{\gamma\})\) は連続である。実際、開 bisection に台を持つ \(b\) が 1 となる近傍で \(h(\gamma)=\int b\,d\mu^{r\gamma}\) と書ける。各 \(x\) の行で質量 \(>1-\delta\) を持つ有限集合を選び、そこで 1 となる \(0\le\chi_x\le1\) を \(C_c(G)\) に取る。連続性と \(X\) のコンパクト性から有限個の \(\chi_x\) の最大 \(\chi\) で全行の質量 \(\int\chi\,d\mu^x>1-\delta\) を得る（\(0<\delta<1\)）。\(\chi h\) を各行で正規化した測度と \(\mu^x\) の全変動ノルム距離は高々 \(2\delta\)。従って矢の欠損の増加は高々 \(4\delta\) である。この compact-support 版への移行にも可算性は要らない。

**非 amenable の場合の有限テスト。** 条件3の否定により、あるコンパクト \(C\) と \(\rho>0\) について全ての正の規格化場 \(p\) が \(\sup_C d_p\ge\rho\) を満たす。(2) と正規化評価より、全ての \(Rw=1\) の複素コアで \(\max_j\|\Delta_{b_j}w\|_r\ge\rho/2\)。欠損ベクトルの集合は凸なので、任意の \(0<t<\rho/2\) についてこれを \(A^n\) の半径 \(t\) の開球から分離できる。得られるノルム1の汎関数の実部は全ての欠損ベクトル上で \(t\) 以上である。任意の \(R^{\ast\ast}m=\kappa_P(1)\) に上記の質量補正済み Goldstine ネットを用いてこの評価を極限に移すと、同じ有限個のテストが \(\max_j\|\Delta_{b_j}^{\ast\ast}m\|\ge t\) を検出する。\(t\uparrow\rho/2\) とすればよい。

## Étale 上の任意の full continuous Haar 系

\(c(x)=\lambda^x(\{1_x\})=R_\lambda(1_X)(x)\) は正かつ連続である。各 range ファイバーは離散で、左不変性により \(\lambda^{r\gamma}(\{\gamma\})=c(s\gamma)\)。従って \(Ua=(c\circ s)a\) は \(\lambda\) の range 完備化から counting の range 完備化への等長全射で、\(R_\# U=R_\lambda\)。\(s(\eta^{-1}\gamma)=s\gamma\) より \(U(a\ast_\lambda b)=Ua\ast_\# Ub\) となる。\(U\) は \(\ell_v\) と可換なので条件2も移る。counting で用いた \(b_j\)、\(p_i\) をそれぞれ \(c\circ s\) で割れば元の系のテスト、Reiter 密度となり、各行の確率測度とその移動欠損は一致する。従って compact open \(B\) の場合、range 質量が \(1_{rB}\) のテストは \(1_B/(c\circ s)\) であり、\(B=X\) ではこれが元の環の単位となる。

局所式 (1) の前提は、bisection が open で、その中の唯一の矢を行積分で検出できることである。非 étale の Lebesgue pair groupoid では局所同相のグラフは各行で零測度になり、同じテストを得られない。上の \(\Lambda_\gamma\) は二つのファイバーの間の写像である。

**検証と範囲（2026年11月24日）。** Lean 4.27 で、同じ有界複素線形切断 \(J\) に対する指定 derivation の innerness、不変二重双対元の存在、正のコンパクト台 Reiter 密度、連続な確率測度系の Reiter ネットの同値を、分割したモジュールの接続として型検査した。所与の full continuous Haar 系に対する対角切断も構成した。確率測度系から戻る際の密度は \(q(\gamma)=\chi(\gamma)h(\gamma)/(c(s\gamma)t(r\gamma))\)、\(t(x)=\int\chi\,d\mu^x\) であり、行質量は厳密に \(1\)、全変動距離は \(2\delta\) 未満、矢の欠損の増加は \(4\delta\) 以下になる。合わせた最終宣言の公理依存は Lean 標準の三公理のみ。旧モジュールを一括して再ビルドしたという意味ではない。

非空コンパクト単位空間をもつ局所コンパクト Hausdorff étale groupoid、所与の full continuous 左 Haar 系、片側 range ノルム、上記の特定の derivation が対象である。第二可算性は仮定しない。一般の非 étale Haar 系、非コンパクト単位空間、両側 \(I\)-ノルム、通常の Banach amenability に関する主張ではない。[Anantharaman-Delaroche–Renault（2000）](https://www.unige.ch/math/EnsMath/en/monographies/monographie-no-36)、Definitions 2.2.1–2.2.2、2.2.8 および Proposition 2.2.13 は標準の従順性の定式化を与える（同書の第二可算性仮定とは区別した）。
