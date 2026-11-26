# Propagation of counting-I diagonals under uniform doubling

**Work in progress.** 2026-11-26. 博論の拡張方針6の研究ノート。書面検証済み、Lean 検証なし。論文・プレプリント・査読済み成果ではなく、優先性は主張しない。

## 主張

\(G\) は局所コンパクト Hausdorff étale groupoid、\(X=G^{(0)}\) は非空コンパクトとする。畳み込みは untwisted、Haar 系は counting とする。\(\ell:G\to[0,\infty)\) は連続、proper で、単位上で零、反転に対称、合成に劣加法的とする。行と列の和を \(\mathcal R,\mathcal S\)、\(A\) を両側の raw counting \(I\)-norm による完備化と書く。
\[
 B_t=\{\ell\le t\},\quad \beta_x(t)=|G^x\cap B_t|,\quad
 \beta_x(2t)\le C\beta_x(t)\quad(x\in X,\ t>0),\qquad C\ge1 .
\]
ここで \(G^x=r^{-1}(x)\)。反転により半径球の source ファイバーの濃度も \(\beta_x(t)\) である。\(\beta_x(t)\) と前回の bisection 分解ノルム \(\beta(f)\) は別の量である。

\(R>0\) で \(w_R=(1-\ell/R)_+\)、\(d_x=(\mathcal Rw_R)(x)\)、\(p_R(\eta)=w_R(\eta)/d_{r\eta}\) とする。有限個のテスト \(b\in C_c(U_b)\) を取り、\(U_b\) は開 bisection、\(\ell\le M_b\le R/2\) が \(\operatorname{supp}b\) で成り立つとする。各 \(b\) を零延長し、
\[
 \Delta_b p_R=b\ast p_R-((\mathcal R b)\circ r)\,p_R,\qquad
 K_C=2 C^4(1+2 C^2)
\]
と置く。このとき
\[
 \mathcal R p_R=1_X,\qquad \|\mathcal S p_R\|_\infty\le2C^3,\qquad
 \|\Delta_b p_R\|_I\le K_C\|b\|_\infty M_b/R .
\]

任意の \(\rho,\varepsilon>0\) に対し、普通の射影テンソル積 \(A\widehat\otimes_\pi A\) に有限テンソル \(D\) があり、両脚が \(O=\{\ell<R+\rho\}\) にコンパクト台を持つ有限表示を選べる。さらに
\[
 \pi(D)=1_X,\qquad
 \|p_R\|_I\le\|D\|_\pi\le\min\{2C^3,\ \|p_R\|_I+\varepsilon\},\qquad
 \|bD-Db\|_\pi\le K_C\|b\|_\infty M_b/R+\varepsilon
\]
が指定した全テストで同時に成り立つ。\(\pi\) は畳み込み積写像である。例えば \(\|b\|_\infty\le1,\ M_b\le M\) の有限テストで欠損 \(\delta>0\) を指定するなら、\(R>0,\ R\ge\max(2M,2K_CM/\delta)\) と \(\varepsilon=\delta/2\) で足りる。有限テストを増やし、\(R\to\infty,\ \varepsilon\downarrow0\) とすれば bounded approximate diagonal になる。開 bisection 上のコンパクト台関数の有限和は \(C_c(G)\) 全体を張り、対角は一様有界なので完備化にも移る。

## 行・列の計算

proper 性により \(B_t\) はコンパクトで、有限 bisection 被覆から \(N_t=\sup_x\beta_x(t)<\infty\)。連続コンパクト台関数の counting 行和は連続である（有限 bisection 分割で確認できる）。単位矢の tent 値は \(1\)、\(B_{R/2}\) では \(w_R\ge1/2\)。従って \(d_x\ge(\beta_x(R/2)+1)/2\)、\(p_R\in C_c(G)_+\)、\(\operatorname{supp}p_R\subset B_R\)、\(\mathcal Rp_R=1_X\)。

\(\eta:y\to x\) による左移動 \(G^y\to G^x\) は全単射で長さを高々 \(\ell(\eta)\) 増やす。\(\ell(\eta)\le R+M\), \(0\le M\le R/2\) なら
\[
 \beta_y(R/2)\le\beta_x(R/2+\ell(\eta))\le\beta_x(2R)
       \le C^2\beta_x(R/2).
 \tag{1}
\]
まず \(p_R\) 自身を固定列 \(s\eta=y\) で足す。長さ \(R\) 以下の項が \(\beta_y(R)\) 個以下で、(1) により各項は \(2C^2/\beta_y(R/2)\) 以下。従って列和は \(2C^3\) 以下である。実は \(N=N_{R/2}\) とすると、上の \(d_x\) の下界からこの列和の上界に \(N/(N+1)\) を掛けられる。行和は \(1\) なので \(\|p_R\|_I\le\max(1,2C^3N/(N+1))<2C^3\)。この固定 \(R\) ごとの余裕をテンソルの持ち上げに使う。

次に \(M=M_b\) とし、\(r\eta=x\) とする。寄与がありうる場合、\(U_b\) に唯一の \(\alpha:z\to x\) があり \(b(\alpha)\ne0\)。\(m=\ell(\alpha)\le M\) とおくと
\[
 \Delta_b p_R(\eta)=b(\alpha)
 \left(\frac{w_R(\alpha^{-1}\eta)}{d_z}-\frac{w_R(\eta)}{d_x}\right).
\]
逆元と劣加法性により二つの長さの差は高々 \(m\)。tent 値の差は \(m/R\) 以下で、どちらかの値が非零なら \(\ell(\eta)\le R+M\)。左移動で \(d_z\) を \(G^x\) 上の和に書き直し、次いで \(\alpha^{-1}\) で球を \(G^z\) に移すと
\[
 |d_x-d_z|\le(m/R)\beta_x(R+M),\qquad
 \beta_x(R+M)\le\beta_z(R+2M)\le C^2\beta_z(R/2)\le2C^2d_z .
 \tag{2}
\]
\(w'=w_R(\alpha^{-1}\eta),\ w=w_R(\eta)\) と書けば括弧は
\((w'-w)/d_x+w'(d_x-d_z)/(d_xd_z)\) である。従って
\[
 |\Delta_b p_R(\eta)|\le
  \|b\|_\infty\,\frac{M}{R}(1+2C^2)\,
     \frac{\mathbf1_{B_{R+M}}(\eta)}{d_{r\eta}}.
 \tag{3}
\]
固定行では \(\beta_x(R+M)/d_x\le2C^2\)。固定列では (1) により \(1/d_{r\eta}\le2C^2/\beta_y(R/2)\)、項数は反転により \(\beta_y(R+M)\le C^2\beta_y(R/2)\)。それぞれの絶対値の和を (3) で評価すると、二側の \(I\)-欠損について主張の定数を得る。\(M=0\) のとき tent の欠損は厳密に零である。

## 台を保つ普通のテンソル

前回の \(\beta(f)=\|f\|_I\) を \(p_R\) に適用する。\(p_R=\sum\limits_j g_j,\ g_j\in C_c(U_j)\) で \(\sum\limits_j\|g_j\|_\infty<\min(2C^3,\|p_R\|_I+\varepsilon)\) と取れる。\(B_R\) 上で \(1\)、\(B_{R+\rho/2}\) の外で零の連続な半径 cutoff \(0\le h\le1\) を一つ取る。\(g_j\) を点ごとの積 \(h g_j\) に置換しても和は \(p_R\) で、コストは増えない。各項の台は \(U_j\cap O\) のコンパクト部分集合になる。\(v_j\in C_c(U_j\cap O),\ 0\le v_j\le1\) を、置換後の \(g_j\) の台の近くで \(1\) となるよう選ぶ。\(v_j^\ast\) の台は \(U_j^{-1}\cap O\) に入る。ここで長さの対称性を用いる。[前回の分解ノルム等式と相対対角](06-etale-counting-i-sharp-constant.md)

\(z=\sum\limits_j g_j\otimes v_j^\ast\) は所望の台とノルム上界を持つ。商写像を \(q:A\widehat\otimes_\pi A\to A\widehat\otimes_{C(X)}A\) と書くと \(qz=J(p_R)\) である。各 \(g_j\ast v_j^\ast\) は単位上に支えられ、そこで \(\mathcal Rg_j\) となるので \(\pi(z)=1_X\)。前回の局所積恒等式
\[
 q(bz-zb)=bJ(p_R)-J(p_R)b=J(\Delta_b p_R)u_b
\]
で \(u_b\in C_c(U_b)\) は \(b\) 用のノルム \(1\) 以下の cutoff である。\(\|J(a)\|\le\|a\|_I\) より、この商像のノルムは \(\|\Delta_b p_R\|_I\) 以下。

各商像の持ち上げ \(t_b\) を、そのノルムが商ノルムより \(\varepsilon/2\) 未満しか増えないように選ぶ。\(k_b=bz-zb-t_b\) は balancing 関係の閉線形包に入る。\(C(X)\) の unitary 群の有限 Følner 平均を
\[
 H_F(a\otimes c)=|F|^{-1}\sum\limits_{v\in F} (a\ast v)\otimes(v^{-1}\ast c)
\]
とする。これは contractive で、\(qH_F=q,\ \pi H_F=\pi\)、外側の左右作用と可換である。unitary \(t\) の elementary balancing 差に対し、平均後のノルムは \(|Ft\triangle F|/|F|\) に両因子のノルムを掛けた量で抑えられる。\(C(X)\) は unitary の線形包で、unitary 群は可換なので、有限個の \(k_b\) を同時に \(\|H_F k_b\|<\varepsilon/2\) とできる。従って \(D=H_Fz\) は所望の交換子評価を持つ。実際の \(D\) の第一脚は \(v\circ s\)、第二脚は \(v^{-1}\circ r\) を掛けたものだから、それぞれ元の脚の台を保つ。補助持ち上げ \(t_b\) はノルム評価だけに登場し、半径による台制約を要しない。平均 \(F\) は指定した有限テストと精度に依存する。

## 定性的な定数 1 との関係

\(\Theta(a\otimes c)(\eta)=a(\eta)c(\eta^{-1})\) は \(\|\Theta(a\otimes c)\|_I\le\|a\|_I\|c\|_\infty\) より contractive に延長し、両方の中間係数が \(s\eta\) で評価されるので \(C(X)\)-balanced である。従って \(\Theta(D)=p_R\) であり、固定 tent のこの相対対角を持ち上げたものはどれも \(\|D\|_\pi\ge\|p_R\|_I\) を満たす。

三点 \(\{0,1,2\}\) の counting pair groupoid で \(\ell(i,j)=|i-j|,\ R=2\) とすると \(d=(3/2,2,3/2)\)、列和は \((11/12,7/6,11/12)\) である。従ってその半径では \(\|D\|_\pi\ge7/6\)。この環の ordinary amenability 定数は \(1\) であり、固定した正規化 tent の制約と全 approximate diagonal にわたる最良定数は区別される。

## 原典との照合

Austad–Bönicke の v3 の (4.1) は source 球で \(R-\ell(\gamma)\) に \(1_Y(r\gamma)\) を掛けて和を取り、(4.2) はその \(Y=X\) の場合 \(V_R(x)\) を定める。対称性と反転から今回の分母は正確に \(d_x=V_R(x)/R\)。上の固定列における (1)–(3) の欠損評価と、普通の射影テンソルの両脚への台制御はここでの計算である。[Austad–Bönicke, 2026, v3, §4, (4.1)–(4.3)](https://arxiv.org/html/2605.16013v3#S4.E1)

Proposition 4.14 は標準語長に関して semi-saturated な \(\mathbb Z^d\) の部分作用に一様 doubling を与え、証明では \(C=2^{2d}\) が使える。Proposition 4.15 はコンパクト Hausdorff 基底、可算離散群、群の proper length のもとで comparison admissibility とすべての部分作用域 \(X_g\) の閉性を同値とする。各部分作用域はもともと開である。閉性があれば有限半径球は有限個のコンパクト開ラベル bisection の和で、誘導長は連続かつ proper。従ってコンパクト基底、clopen な部分作用域、標準語長に関して semi-saturated な \(\mathbb Z^d\) 部分作用には今回のテンソル評価が適用できる。全域作用の例は円周の無理回転である。4.14 単独ではコンパクト台を、4.15 単独では doubling を保証しない。[同論文, §4.1, Propositions 4.14–4.15](https://arxiv.org/html/2605.16013v3#S4.SS1)
