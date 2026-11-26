# Contractive counting-I diagonals with linear propagation

**Work in progress.** 2026-11-26. 博論の拡張方針6の研究ノート。書面検証済み、Lean 検証なし。論文・プレプリント・査読済み成果ではなく、優先性は主張しない。

## 結論

\(G\) は非空のコンパクト単位空間 \(X\) をもつ局所コンパクト Hausdorff étale groupoid とし、counting Haar 系を使う。\(\ell:G\to[0,\infty)\) は連続かつ proper、単位上で零、反転対称、合成に劣加法的とする。\(B_t=\{\ell\le t\}\)、\(\beta_x(t)=|B_t\cap G^x|\)、\(G^x=r^{-1}(x)\) とし、すべての \(x\) と \(t>0\) で \(\beta_x(2t)\le C\beta_x(t)\), \(C\ge1\) を仮定する。\(A_\sigma\) は連続正規化スカラー \(U(1)\) 2-cocycle \(\sigma\) による raw counting \(I\)-norm 環で、自明 cocycle を含む。

\(R>0\)、および開 bisection 上の有限テスト \(b\in C_c(U_b)\) を取る。\(\operatorname{supp}b\subset B_{M_b},\ M_b\le R/2\) とする。任意の \(\rho,\varepsilon,\eta>0\) に対し、普通の射影テンソル積に有限テンソル \(Z\) が存在する。その有限表示の両脚は \(\{\ell<2R+\rho\}\) にコンパクト台をもち、積写像 \(\pi_\sigma\) と外側の双加群作用について
\[
 \pi_\sigma(Z)=1_X,\qquad 1\le\|Z\|_\pi\le1+\varepsilon,\qquad
 \|bZ-Zb\|_\pi\le K'_C\|b\|_\infty\,M_b/R+\eta,\qquad
 K'_C=4C^6(1+2C^2).
\]
縮小した \(Z_{\rm c}=Z/(1+\varepsilon)\) は、同じ台半径で
\[
 \|Z_{\rm c}\|_\pi\le1,\qquad
 \pi_\sigma(Z_{\rm c})=\frac{1_X}{1+\varepsilon},\qquad
 \|\pi_\sigma(Z_{\rm c})-1_X\|_I=\frac{\varepsilon}{1+\varepsilon}.
\]
交換子の上界も \(1+\varepsilon\) で割れる。有限テストを増やし \(R\to\infty,\ \varepsilon,\eta\downarrow0\) とすることで、両脚の台を制御した contractive approximate diagonal が得られる。

## 固定 source からの列の下界

以下、\(\ast\) と \(^{\ast}\) は untwisted の counting 畳み込みと随伴である。行和・列和を \(\mathcal R,\mathcal S\) とし、
\[
 w_R=(1-\ell/R)_+,\qquad d(x)=\mathcal Rw_R(x),\qquad
 p_R(\gamma)=w_R(\gamma)/d(r\gamma),\qquad D(y)=\mathcal Sp_R(y)
\]
とする。proper 性より \(w_R\in C_c(G)\) で、単位矢は \(d\ge1\) を与える。計数行和と列和はコンパクト台上の有限 bisection 分割から連続であり、\(\mathcal Rp_R=1_X\) である。この tent の重みは Austad–Bönicke の source 球上の重みを反転し、半径で割ったものである。両側 \(I\)-欠損の数値評価は前回の検算を用いる。[Austad–Bönicke (2026), §4, (4.1)–(4.2)](https://arxiv.org/html/2605.16013v3#S4.E1) ／ [前ノートの doubling 評価](06-etale-counting-i-doubling-propagation.md)

\(s\gamma=y,\ r\gamma=x,\ \ell(\gamma)\le R/2\) とする。左移動 \(\xi\mapsto\gamma^{-1}\xi\) は \(B_R\cap G^x\) を \(B_{3R/2}\cap G^y\) に単射で移す。従って
\[
 d(x)\le\beta_x(R)\le\beta_y(3R/2)\le\beta_y(2R)\le C^2\beta_y(R/2).
\]
この \(\gamma\) では \(w_R(\gamma)\ge1/2\)。そのような \(\gamma\) は反転によりちょうど \(\beta_y(R/2)\) 本ある。これらだけを固定列で足すと \(D(y)\ge1/(2C^2)\)。特に \(D^{-1}\in C(X)\) で \(\|D^{-1}\|_\infty\le2C^2\) となる。

## 対称化と符号付き欠損

\(D^{-1}\) を単位上の関数として
\[
 q=D^{-1}\ast p_R^\ast,\qquad
 h_R=p_R\ast q=p_R\ast D^{-1}\ast p_R^\ast
\]
と置く。\(q(\gamma)=p_R(\gamma^{-1})/D(r\gamma)\ge0\)。各 range 行の和は \(D(x)/D(x)=1\)、source \(y\) の列和は \(\|D^{-1}\|_\infty\mathcal Rp_R(y)\le2C^2\) である。ゆえに \(\|q\|_I\le2C^2\) である。

\(h_R\in C_c(G)\) は非負で、\(D^{-1}\) が実の対角関数なので \(h_R^\ast=h_R\)。\(\mathcal R(p_R\ast q)(x)=\sum\limits_{r\alpha=x}p_R(\alpha)\mathcal Rq(s\alpha)=1\)。反転対称性により \(\mathcal Sh_R=1_X\) でもあり \(\|h_R\|_I=1\)。\(\operatorname{supp}q\subset B_R\)、\(\operatorname{supp}h_R\subset B_RB_R\subset B_{2R}\) である。

\(\Delta_b f=b\ast f-((\mathcal R b)\circ r)f\) とする。第2項は対角関数 \(\mathcal Rb\) による左畳み込みなので、結合則から
\[
 \Delta_b h_R=(\Delta_b p_R)\ast q
\]
が厳密に成り立つ。任意の複素数値 \(k\) について \(|k\ast q|\le |k|\ast q\)。従って range ノルムでは \(\|k\ast q\|_r\le\|k\|_r\)、source ノルムでは \(\|k\ast q\|_s\le\|k\|_s\|\mathcal S q\|_\infty\)。前回の \(I\)-欠損定数 \(K_C=2C^4(1+2C^2)\) と合わせると
\[
 \|\Delta_b h_R\|_I\le2C^2\|\Delta_b p_R\|_I
 \le K'_C\,\|b\|_\infty M_b/R .
\]
ここで保たれるのは \(M_b/R\) の減衰率である。右畳み込みが一般に \(I\)-contractive にならないことは、三点の counting pair groupoid、\(\ell(i,j)=|i-j|,\ R=2\) で確認できる。このとき \(D=(11/12,7/6,11/12)\)、\(\mathcal Sq=(78/77,75/77,78/77)\)。単位元に右から \(q\) を掛けると \(I\)-norm は \(78/77\) になる。この例の全 \(34\) 個の部分置換の指示関数でも \(\Delta_b h_R=(\Delta_b p_R)\ast q\) を有理数演算で照合した。この例は右畳み込み作用素の評価であり、欠損定数 \(K'_C\) の最良性を意味しない。

## スカラー cocycle の場合を含む有限 lift

対称化する \(p_R,q,h_R\) はすべて通常のスカラー場として作る。確認済みの相対写像 \(J_\sigma:A_{\bf1}\to A_\sigma\widehat\otimes_{C(X)}A_\sigma\) は等長であり、\(\pi_\sigma J_\sigma(h_R)=\mathcal Rh_R=1_X\) は厳密。\(b\) と同じ bisection 内でその台の近くにおいて \(1\) となる \(0\le u_b\le1\) を用いると
\[
 bJ_\sigma(h_R)-J_\sigma(h_R)b=J_\sigma(\Delta_b h_R)u_b .
\]
右辺の \(\Delta_b\) は上で評価した untwisted のものなので、新たな cocycle 依存定数は生じない。[スカラー cocycle の局所恒等式 (1)](06-etale-scalar-twisted-counting-i-amenability.md)

全開 bisection による分解ノルム \(\beta(h_R)=\|h_R\|_I=1\) から、有限分解 \(h_R=\sum\limits_j f_j,\ f_j\in C_c(U_j)\) を \(\sum\limits_j\|f_j\|_\infty<1+\varepsilon\) と取れる。\(B_{2R}\) で \(1\)、\(\{\ell<2R+\rho\}\) にコンパクト台をもつ単一の連続な半径 cutoff を全項に点ごとに掛けて、和とコスト上界を保つ。\(v_j\in C_c(U_j\cap\{\ell<2R+\rho\})\) を \(0\le v_j\le1\)、局所化した \(f_j\) の台の近くで \(1\) とすると
\[
 z=\sum\limits_j f_j\otimes v_j^{\ast_\sigma}
\]
は \(J_\sigma(h_R)\) の普通の有限 lift である。長さの反転対称性により逆 bisection 側の脚も同じ開球に入り、\(\pi_\sigma z=1_X\)、\(\|z\|_\pi\le1+\varepsilon\) である。[全開 bisection での分解ノルム等式](06-etale-counting-i-sharp-constant.md)

商で小さい交換子ごとに、その商ノルムより \(\eta/2\) 未満しか増えない補助 lift を取る。\(bz-zb\) からそれを引いたものは balancing の核に属する。\(C(X)\) の unitary 群の中間 Følner 平均 \(H_F(a\otimes c)=|F|^{-1}\sum\limits_{v\in F}av\otimes v^{-1}c\) でこれら有限個の核元を同時に \(\eta/2\) 未満にできる。実際、unitary \(t\) の balancing 差は添字の平行移動により \(|Ft\triangle F|/|F|\) に両因子のノルムを掛けた量で抑えられ、線形包と閉包で十分である。平均は contractive で外側作用と可換、中間の両脚で \(v\circ s,\ v^{-1}\circ r\) を掛けるため台と積を保つ。\(Z=H_Fz\) は主張の三つの評価を満たす。補助 lift は \(Z\) の有限表示に登場しない。さらに \(\|\pi_\sigma Z\|_I=1\) から \(\|Z\|_\pi\ge1\) である。

有限テスト上で \(\|b\|_\infty\le1,\ M_b\le M\) とし、許容誤差を \(\delta>0\) とすれば、たとえば \(R>0,\ R\ge\max(2M,2K'_CM/\delta)\)、\(\varepsilon=\eta=\delta/2\) とすればよい。\(Z_{\rm c}\) は contractive で、交換子と積の誤差はともに \(\delta\) 以下である。テストを増やした極限は、bisection テストの線形包の稠密性と一様有界性により完備化全体に適用できる。

相対テンソル \(J_\sigma(h_R)\) ではノルム \(1\) と積 \(1_X\) が両立する。普通の有限テンソルに対しては、固定半径で両方の等号を同時に実現できるかは未検証。大域スカラー cocycle で与えられない一般の twist 線束への拡張も未検証である。
