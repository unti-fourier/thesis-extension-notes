# Ordinary Banach amenability for the scalar-twisted counting-I algebra

**Work in progress.** 2026-11-26. 博論の拡張方針6の研究ノート。書面検証・有限位相照合。Lean 検証なし。論文・プレプリント・査読済み成果ではなく、優先性は主張しない。

## 定理と規約

\(G\) を非空の局所コンパクト Hausdorff étale groupoid、\(X=G^{(0)}\) とする。\(\sigma:G^{(2)}\to\mathbb T\) は連続な正規化 2-cocycle とする。複素数値 \(C_c(G)\) の twisted 畳み込みに counting の両側 raw \(I\)-norm を入れ、その完備化を \(A_\sigma\) とする。このとき
\[
 G\text{ が topologically amenable}
 \quad\Longleftrightarrow\quad A_\sigma\text{ が ordinary Banach amenable}.
\]
成立時の ordinary projective approximate diagonal の最良定数は \(1\)。単位空間のコンパクト性、第二可算性、cocycle が coboundary であることは仮定しない。topological amenability は連続確率系の net の左移動欠損がコンパクトな矢集合上一様に零に収束する意味で用いる。

\(q(\gamma)=\sigma(\gamma,\gamma^{-1})=\sigma(\gamma^{-1},\gamma)\) とする。この等号は cocycle 恒等式と正規化から従う。以下、
\[
 (a\ast_\sigma c)(\xi)=\sum\limits_{\alpha\eta=\xi}\sigma(\alpha,\eta)a(\alpha)c(\eta),
 \qquad a^{\ast_\sigma}(\xi)=\overline{q(\xi)}\,\overline{a(\xi^{-1})}.
\]
\(\|a\|_I\) は絶対値の range 行和と source 列和のそれぞれの上限の最大値。\(\ast\) 単独は位相を入れない counting 畳み込み、\(A_{\bf1}\) はその環、\(Ra(x)=\sum_{r\gamma=x}a(\gamma)\) は通常の行和である。\(|a\ast_\sigma c|\le |a|\ast|c|\) であるから積は contractive。正規化により \(P=C_0(X)\) の左右作用は \(r,s\) での乗算である。この規約は Austad–Ortega の出版版 §2.3 の (1)–(3)、プレプリントの (2.3)–(2.5) と一致する。同論文は第二可算の場合にこの環の \(C^\ast\)-uniqueness を扱う。ここで用いる untwisted の入力は、前回の書面検算における全開 bisection 分解ノルム \(\beta=\|\cdot\|_I\) と、amenable な \(G\) の \(A_{\bf1}\) が contractive approximate diagonal を持つという結果である。[Austad–Ortega, 2022, §2.3](https://arxiv.org/pdf/2005.06208#page=4) ／ [前ノートの untwisted の入力](06-etale-counting-i-sharp-constant.md)

## 逆矢の脚と局所的な貼り合わせ

\(Q_\sigma:A_\sigma\widehat\otimes_\pi A_\sigma\to A_\sigma\widehat\otimes_P A_\sigma\) を商写像、\(\pi_\sigma\) を twisted 積写像とする。開 bisection \(V\) に台をもつ \(f\in C_c(V)\) に対し、\(0\le v\le1,\ v\in C_c(V)\) を \(\operatorname{supp}f\) の近傍で \(1\) に取る。零延長により
\[
 J_\sigma(f)=f\otimes_P v^{\ast_\sigma}.
\]
第一脚の \(\eta\) と組になる第二脚の \(\eta^{-1}\) に \(\overline{q(\eta)}\) を置く。二つのチャート・cutoff が使える場合、両者の共通部分でともに \(1\) となる開近傍 \(W\) を台のまわりに取る。\(s(W)\) 内に台をもち \(s(\operatorname{supp}f)\) 上で \(1\) となる対角関数を第一脚の右から第二脚の左へ移すと、第二脚は一致する。局所的な線形性は共通 cutoff から従う。有限個の局所項の和が零なら、その台の合併上で和が \(1\) となる、開 bisection 被覆に従属した有限の連続分割を掛ける。各細片は元のチャートと分割のチャートの両方に属するので、各分割チャートで足すと零になる。これで \(J_\sigma\) は \(C_c(G)\) 上で整合する。各 bisection でのノルム評価を足して \(\|J_\sigma(f)\|\le\beta(f)=\|f\|_I\) となり、\(A_{\bf1}\) 全体に延長する。

\(V V^{-1}\subset X\) であり、\(f\ast_\sigma v^{\ast_\sigma}\) の単位での各項の位相は \(q(\eta)\overline{q(\eta)}=1\)。従って \(\pi_\sigma J_\sigma(f)=Rf\) を単位上の関数として得る。さらに、普通の射影テンソル積から \(A_{\bf1}\) への複素双線形写像
\[
 \Theta_\sigma(a\otimes c)(\eta)=q(\eta)a(\eta)c(\eta^{-1})
\]
は、\(\|\Theta_\sigma(a\otimes c)\|_I\le\|a\|_I\|c\|_\infty\le\|a\|_I\|c\|_I\) により contractive に延長する。両方の中間係数が \(s\eta\) で評価されるため \(P\)-balanced でもある。同じ記号をその商上でも用いると
\[
 \Theta_\sigma J_\sigma=\mathrm{id},\qquad
 R\Theta_\sigma(m)=(\pi_\sigma m)|_X .
\]
特に \(J_\sigma\) は等長である。

## 二つの位相計算

\(b\in C_c(U)\) は開 bisection 上の複素数値テストとし、\(0\le u\le1,\ u\in C_c(U)\) は \(\operatorname{supp}b\) の近傍で \(1\) とする。スカラー場の欠損を
\[
 \Delta_b p=b\ast p-((Rb)\circ r)\,p
\]
と定義する。最初の積は untwisted である。外側の作用は以下すべて twisted。次の恒等式が成り立つ。
\[
 bJ_\sigma(p)-J_\sigma(p)b=J_\sigma(\Delta_b p)\,u,                       \tag{1}
\]
\[
 \Theta_\sigma\big((bm-mb)\,u^{\ast_\sigma}\big)
       =\Delta_b\Theta_\sigma(m).                                          \tag{2}
\]

(1) の比較は代数的な balanced tensor の中でできる。一組の bisection チャート \(V_1,V_2\) 上の有限テンソル和は、そのチャート対の合成可能な \((\xi,\zeta)\) 上で \(\sum a_j(\xi)c_j(\zeta)\) が一致すれば同じ類になる。実際、各 \(c_j\) を \(r|_{V_2}\) で中間単位上に移し零延長した関数を \(\phi_j\) とすると、\(c_j=(\phi_j\circ r)v_0\) と書ける。ここで \(v_0\in C_c(V_2)\) は全第二脚の台で \(1\) である。\(\phi_j\) を第一脚へ移すと第一脚の和は \(\sum a_j(\phi_j\circ s)\) であり、これは上の合成可能対上の値で決まる。この局所計算で足りる。

\(p=f\in C_c(V)\) について、まず \(bJ_\sigma(f)\) と \(J_\sigma(b\ast f)u\) をチャート対 \((UV,V^{-1})\) で比較する。第一矢を \(\alpha\eta\) とした寄与では \(\alpha\in U,\eta\in V\) は一意で、第二矢は \(\eta^{-1}\) である。\(UV\) の cutoff を \(\operatorname{supp}(b\ast f)\) の近くで \(1\) に取ると、必要な等式は
\[
 \frac{\sigma(\alpha,\eta)}{q(\eta)}
   =\frac{\sigma((\alpha\eta)^{-1},\alpha)}{q(\alpha\eta)}.                \tag{3}
\]
これは三つ組 \(((\alpha\eta)^{-1},\alpha,\eta)\) に対する cocycle 恒等式そのものである。次に \(J_\sigma(f)b\) と \(J_\sigma(((Rb)\circ r)f)u\) は \((V,V^{-1}U)\) に入り、合成可能対 \((\eta,\eta^{-1}\alpha)\) 上で両辺の位相は \(\overline{q(\eta)}\sigma(\eta^{-1},\alpha)\)。係数は \(b(\alpha)=(Rb)(r\alpha)u(\alpha)\) により一致する。差を取って (1) を得る。有限和と連続延長で一般の \(p\) に移る。

(2) は \(m=a\otimes c\) で計算する。\(\xi=\alpha\eta\) で \(\alpha\in U,\ r\alpha=r\xi\) と書ける行では、\(\Theta_\sigma((b a)\otimes(c u^{\ast_\sigma}))(\xi)\) の二つの脚に \(\eta,\eta^{-1}\) が残る。積の位相は
\[
 q(\alpha\eta)\,\sigma(\alpha,\eta)\,
        \sigma(\eta^{-1},\alpha^{-1})\,\overline{q(\alpha)}
       =q(\eta).                                                          \tag{4}
\]
これは四つの矢 \(\alpha,\eta,\eta^{-1},\alpha^{-1}\) を内側から、または左右の二組から積にした場合の cocycle 恒等式である。スカラー係数は \(b(\alpha)\overline{u(\alpha)}=b(\alpha)\)。これが \(b\ast\Theta_\sigma(m)\) を与える。もう一項では \(b\ast_\sigma u^{\ast_\sigma}=Rb\) が単位上に載り、\(((Rb)\circ r)\Theta_\sigma(m)\) を与える。該当する \(\alpha\) がない行は両辺とも零である。有限テンソルの稠密性から (2) が従う。

## 順向きと定数

\(G\) が topologically amenable とする。前回の untwisted 定理による \(A_{\bf1}\) の contractive approximate diagonal を \(m_i^0\) とし、\(p_i=\Theta_{\bf1}(m_i^0)\) と取る。すると \(\|p_i\|_I\le1\)。(2) を自明 cocycle に使うと、各 bisection テストで \(\|\Delta_b p_i\|_I\to0\)。\(Rp_i=(\pi_{\bf1}m_i^0)|_X\) は単位の任意のコンパクト集合上で一様に \(1\) に近づく。実際、その集合上で \(1\) となる \(h\in C_c(X)\) に対し \((\pi_{\bf1}m_i^0)h\to h\) を単位上で評価すればよい。

(1) により相対テンソル \(J_\sigma(p_i)\) はノルム \(1\) 以下で漸近的に中心化する。積 \(Rp_i\) は一様有界で、コンパクト台テストの両端で一様に \(1\) に近づくため \(A_\sigma\) の両側近似単位として働く。テスト有限和の稠密性で \(A_\sigma\) の全元を扱える。

普通の射影テンソルへは、有限テスト・精度 \(\varepsilon>0\) ごとに商ノルムの \(\varepsilon\) 以内で持ち上げ、\(\widetilde P=P+\mathbb C1\subset C_b(X)\) の unitary 群の有限 Følner 平均を中間に掛ける。各項は \(a\otimes c\mapsto av\otimes v^{-1}c\) で、\(\pi_\sigma\) を保ち、外側作用と可換な isometry である。中間の \(\widetilde P\) は multiplier として作用し、定数の balancing は自動的に成り立つ。unitary \(t\) による balancing 差の平均は \(|Ft\triangle F|/|F|\) に両因子のノルムを掛けた量で抑えられる。unitary の線形包と閉包を取れば、有限個の商核元の平均を同時に小さくできる。各交換子からその商像のほぼ最小の持ち上げを引いた差にこれを適用する。結果のノルムは \(1+\varepsilon\) 以下で、漸近的な中心化と積の近似単位性が従う。最後に \(1+\varepsilon\) で割って contractive approximate diagonal を得る。非零環では \((\pi_\sigma m_i)a\to a\) が下界 \(1\) を与える。

## 逆向きは実際の Reiter 確率系を与える

今度は \(A_\sigma\) に bounded approximate diagonal \(m_i\) があるとする。\(w_i=\Theta_\sigma(m_i)\) と置く。積を単位上で読めば \(Rw_i\to1\) がコンパクト単位集合上一様である。証明は上と同じ対角 cutoff を使う。(2) より \(\|\Delta_b w_i\|_I\le\|bm_i-m_ib\|_\pi\to0\)。ここまで \(w_i\) は複素数値でもよい。

コンパクトな矢テスト \(L\) を有限個の開 bisection 内の \(0\le b_j\le1\) の plateau \(b_j=1\) で覆う。\(\alpha\in L\) がその plateau にあるなら、\(G^{r\alpha}\) 上で \(\Delta_{b_j}w_i\) は \(L_\alpha w_i^{s\alpha}-w_i^{r\alpha}\) に等しい。ここで \(L_\alpha\) は range 行の通常の左移動である。有限個の交換子で \(L\) 上の全変動欠損が一様に小さくなる。端点と任意の追加のコンパクト単位集合を含むコンパクト \(K\) を固定し、\(i\) を大きく取る。さらに \(w_i\) を \(I\)-norm で \(g\in C_c(G)\) に近似すると、行質量の追加誤差は \(\|g-w_i\|_I\)、左移動欠損の追加誤差は \(2\|g-w_i\|_I\) 以下である。従って \(K\) 上で \(|Rg|>1/2\) かつ \(L\) 上の欠損を任意に小さくできる。

\(N(x)=R|g|(x)\) は連続で、\(h(\eta)=|g(\eta)|/\max(N(r\eta),1/2)\) は非負の \(C_c\) 密度である。\(Rh\le1\) は全単位、\(Rh=1\) は \(K\) 上で成立する。\(L\) 上では両端の分母が \(1/2\) 以上で、絶対値の収縮性と行ノルム差の三角不等式から \(h\) の行欠損は \(g\) の高々 \(4\) 倍。全単位上で確率にするには、不足 \((1-Rh(x))\delta_{1_x}\) を各行に加える。端点では補正は零である。\(k\in C_c(G)\) に対する補正後の積分は \(R(kh)(x)+(1-Rh(x))k(1_x)\) で連続。\(L,K\) と精度で net を取ると、所要の連続な近似不変確率系を得る。非コンパクト \(X\) でのコンパクト台は補正前の \(h\) の性質である。列と net の定義域の違いは Renault の Definition 2.6 直後の比較も参照できる。[Renault (2013 preprint), §2](https://arxiv.org/html/1302.0636#S2)

## 位相の有限照合と範囲

\(H=(\mathbb Z/3)^2,\ \omega=e^{2\pi i/3}\)、\(\sigma(g,h)=\omega^{g_1h_2}\) とする。この cocycle は可換群上で対称でなく、coboundary ではない。\(g=(1,1)\) では \(q(g)=\omega^{-1}\)。従って \(\delta_g\otimes\delta_{-g}\) の twisted 積は \(\omega^{-1}\delta_0\) で、位相を省いた対角抽出の行和 \(1\) とは一致しない。

二単位の \(\{0,1\}\times H\times\{0,1\}\) にも同じ cocycle を引き、単位で正規化された 1-cochain \(\omega^{\lambda(i,g,j)}\), \(\lambda=(i+2j)g_1+i g_2+(i-j)^2\bmod3\) の coboundary を掛けた例で検算した。合成可能な全 \(648\) 対で (3), (4)、全 \(11664\) 三つ組で cocycle 恒等式を整数の mod \(3\) 演算で照合した。

対象は大域的な連続正規化スカラー cocycle と counting \(I\)-norm である。一般の円周中心拡張や局所自明な線束だけで定義される twist への拡張、先行性、Lean による全定理の形式化はこの書面の範囲外である。
