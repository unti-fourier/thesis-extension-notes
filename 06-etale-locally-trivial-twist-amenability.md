# Ordinary Banach amenability for locally trivial twists

**Work in progress.** 2026-11-26. 博論の拡張方針6の研究ノート。書面検証済み、Lean 検証なし。論文・プレプリント・査読済み成果ではなく、優先性は主張しない。

## 結論と規約

\(G\ne\varnothing\) を局所コンパクト Hausdorff étale groupoid、\(X=G^{(0)}\) とする。\(L\to G\) は局所自明な複素 Fell line bundle で、単位上の標準切断を \(1_x\) と書く。これは局所自明な円周中心拡張に付随する twist の規約である。\(A_L\) を \(C_c(G,L)\) の完備化とし、
\[
 \|a\|_I=\max\left(\sup_x\sum\limits_{r\gamma=x}|a(\gamma)|,\ 
                           \sup_x\sum\limits_{s\gamma=x}|a(\gamma)|\right)
\]
を用いる。和は基底 \(G\) の矢を数える。\(A_L\) が ordinary Banach amenable であることと \(G\) が topologically amenable であることは同値で、成立時の最良の射影近似対角定数は \(1\)。\(X\) のコンパクト性、第二可算性、大域単位枠は仮定しない。topological amenability にはコンパクト矢集合上一様な連続確率系の net を用いる。

円周拡張の関数表示では \(F(z\tilde\gamma)=\bar z F(\tilde\gamma)\) の規約を採る。線束では積 \(L_\alpha\times L_\eta\to L_{\alpha\eta}\) は双線形・結合的でノルムは積となり、随伴は反線形で \(e e^\ast=1_{r\gamma},\ e^\ast e=1_{s\gamma}\) が単位ベクトル \(e\in L_\gamma\) に対して成立する。畳み込みはこの積の counting 和、随伴は \(a^\ast(\gamma)=a(\gamma^{-1})^\ast\)。自明化できる開 bisection は積・逆で閉じ、\(UV\) の枠には \(e_U(\alpha)e_V(\eta)\) が使える。原典ではより広い局所 Hausdorff の場合も扱われているが、以下の証明は矢空間が Hausdorff の場合の通常の連続コンパクト台切断を用いる。[Austad–Raum (arXiv v3, 2025), Definition 2.5, Remark 2.7](https://arxiv.org/html/2301.01027v3#S2.SS5) ／ [Bardadyn–Kwaśniewski–McKee (arXiv v4, 2025), §4, Lemma 4.2, (4.4)–(4.6)](https://arxiv.org/html/2303.09997v4#S4)

## 枠を持つ bisection への細分のコスト

\(\mathcal T\) を \(L\) が自明化できるすべての開 bisection とする。スカラー関数について、\(f=\sum\limits_j f_j,\ f_j\in C_c(U_j),\ U_j\in\mathcal T\) にわたる \(\sum\limits_j\|f_j\|_\infty\) の下限を \(\beta_{\mathcal T}(f)\) とする。ここで
\[
 \beta_{\mathcal T}(f)=\beta(f)=\|f\|_I .
\]
第二の等号は前回の全開 bisection の結果。第一の等号には次の局所確認が要る。[全開 bisection に対するスカラーのノルム等式](06-etale-counting-i-sharp-constant.md)

任意の開 bisection \(U\) と \(f\in C_c(U)\) を取り、\(\operatorname{supp}f=K\subset O\Subset U\) とする。\(\|\Phi\|_{\beta_{\mathcal T}^\ast}\le1\) とすると、\(\overline O\) の有限個の自明化チャートと連続分割により、\(\Phi|_{C_c(O)}\) は一様ノルムで有界、従って有限複素 Radon 測度 \(\mu\) で表される。\(V\subset O\) が \(\mathcal T\) に属せば \(C_c(V)\) でテストして \(|\mu|(V)\le1\)。\(K\) を有限の自明化チャートに従属する互いに素な Borel 片に分け、内正則性で各片にコンパクト \(K_j\) を取り、全損失を \(\delta\) 未満とする。\(K_j\) をそれぞれのチャート内かつ \(O\) 内にある互いに素な開近傍で囲む。その合併はもとの一つの \(U\) に含まれる bisection で、開近傍が互いに素なので各枠が貼り合わさり、この合併自身が \(\mathcal T\) に入る。よって \(|\mu|(K)\le1+\delta\)。\(\delta\downarrow0\) と Hahn–Banach により \(\beta_{\mathcal T}(f)\le\|f\|_\infty\)。任意の全開 bisection 分解に適用すれば \(\beta_{\mathcal T}\le\beta\) を得る。逆不等式は分解の包含から従う。これが有限細分の個数による損失を除く。

## 相対対角と二つの方向の局所式

\(P=C_0(X)\) を単位上に埋め込む。コンパクト単位では \(P=C(X)\)。\(A_{\bf1}\) は untwisted スカラーの \(I\)-環、\(R\) はスカラーの range 行和、\(\pi_L\) は線束の畳み込み積写像とする。\(V\in\mathcal T\)、連続単位枠 \(t\)、スカラー \(f\in C_c(V)\) とする。\(0\le v\le1,\ v\in C_c(V)\) は \(\operatorname{supp}f\) の近傍で \(1\) とし、
\[
 J_L(f)=(f t)\otimes_P(vt)^\ast
\]
と置く。二つのチャートや cutoff に対し、共通部分で両 cutoff が \(1\) である \(K=\operatorname{supp}f\) の近傍 \(W\) を取る。枠の変更 \(t'=\lambda t\) の位相は、中間単位 \(y=s\eta=r(\eta^{-1})\) で \(\lambda((s|_W)^{-1}y)\) と書ける。\(s(K)\) 上で \(1\) の \(C_c(sW)\) cutoff を掛けてから零延長すれば、この位相を balancing で第一脚から第二脚へ移せる。逆脚の \(\bar\lambda\) と相殺し、cutoff だけが残り、それも \(f\) 上で \(1\) である。これで表示が一致する。局所和が零という関係には、各点で、その点を台に含むすべての項のチャート内にあり、残りの項の台を避ける近傍を取る。台の有限合併の上で和が \(1\) となる連続分割をこの有限被覆に従属させると、各片の関係は一つのチャートで線形性から従う。従って \(J_L\) は大域的に線形で、\(\|J_L(f)\|\le\beta_{\mathcal T}(f)=\|f\|_I\) により完備化へ延長する。

\(\Theta_L(a\otimes c)(\eta)\) は \(a(\eta)c(\eta^{-1})\in L_{r\eta}=\mathbb C1_{r\eta}\) のスカラーとする。この標準積は複素双線形であり、\(\|\Theta_L(a\otimes c)\|_I\le\|a\|_I\|c\|_\infty\)。中間係数は両側とも \(s\eta\) で評価されるので \(\Theta_L\) は \(P\)-balanced である。\(t(\eta)t(\eta)^\ast=1_{r\eta}\)、\(VV^{-1}\subset X\) から
\[
 \Theta_LJ_L=\mathrm{id},\qquad
 \pi_LJ_L(f)=Rf\ \text{（単位上）},\qquad R\Theta_L(m)=(\pi_Lm)|_X .
\]
特に \(J_L\) は等長である。

テスト \(b\in C_c(U,L)\) を枠 \(e\) で \(b=B e\) と書き、\(u\in C_c(U),\ 0\le u\le1\) を \(\operatorname{supp}b\) の近くで \(1\) に取り、\(c=u e\) とする。下の \(\ast\) はスカラーの untwisted 積であり、外側の双加群作用には \(A_L\) の積を使う。
\[
 bJ_L(p)=J_L(B\ast p)c,\qquad
 J_L(p)b=J_L(((RB)\circ r)p)c.                                             \tag{1}
\]
実際、\(p\) が枠 \(t\) の \(V\) に台をもつとき、\(UV\) に積の枠 \(e(\alpha)t(\eta)\) を選ぶ。第一式の右側の逆脚は、寄与する \((\alpha\eta,\eta^{-1})\) 上で
\((e(\alpha)t(\eta))^\ast e(\alpha)=t(\eta)^\ast\) となり、左側と一致する。第二式は \((\eta,\eta^{-1}\alpha)\) 上で両方とも逆脚に \(t(\eta)^\ast e(\alpha)\) を持ち、\(B(\alpha)=(RB)(r\alpha)u(\alpha)\) を使う。第一式ではチャート対 \((UV,V^{-1})\)、第二式では \((V,V^{-1}U)\) 内の比較で足りる。一つの枠付きチャート対では、各第二脚のスカラー係数を range 座標で中間単位に移し、共通 cutoff と枠を残せば、balancing によりすべての係数を第一脚に移せる。従ってそのチャート対の合成可能対で確認した係数の一致が代数的な balanced tensor の等号を与える。大域的なテンソル評価写像の単射性は用いない。

\(\Delta_Bp=B\ast p-((RB)\circ r)p\) と書くと、逆側にも
\[
 \Theta_L\big((bm-mb)c^\ast\big)=\Delta_B\Theta_L(m)                       \tag{2}
\]
が成り立つ。\(m=a\otimes d\) の第一項を \(\alpha\eta\) で評価すると \(b(\alpha)[a(\eta)d(\eta^{-1})]c(\alpha)^\ast\)。角括弧は \(s\alpha\) 上のスカラーで、\(e(\alpha)\) による移送で同じスカラーが \(r\alpha\) に現れる。係数は \(B(\alpha)u(\alpha)=B(\alpha)\)。第二項は \(b\ast_L c^\ast=RB\) が単位上に載ることから従う。局所枠を替えると \(B\) と \(c\) が同時に変わる。零延長したスカラー係数 \(B\) は選んだ枠に依存する。

## 両方向と台制御

順向きには前回の untwisted 定理による contractive approximate diagonal \(m_i^0\) と \(p_i=\Theta_{\bf1}(m_i^0)\) を取る。自明線束の (2) により \(\Delta_Bp_i\to0\) が \(I\)-norm で成立し、\(\|p_i\|_I\le1\)。\(Rp_i=(\pi_{\bf1}m_i^0)|_X\to1\) はコンパクト単位集合上一様である（その集合上で \(1\) の対角関数に近似単位を作用させる）。(1) により \(J_L(p_i)\) は漸近的に中心化し、積 \(Rp_i\) は \(A_L\) の両側近似単位となる。枠付きテストの有限和は \(C_c(G,L)\) を張る。

普通の射影テンソルには商ノルムの \(\varepsilon\) 以内で持ち上げる。各交換子からその商像のほぼ最小の持ち上げを引いた有限個の核元を、中間の \(P+\mathbb C1\) の unitary \(v\) による \(a\otimes d\mapsto av\otimes v^{-1}d\) の有限 Følner 平均で小さくできる。実際、unitary による balancing 差では添字の平行移動の境界で評価でき、unitary の線形包と閉包で足りる。各項は外側作用と可換な isometry で積を保ち、その平均は contractive である。非コンパクト単位でも \(v\) は multiplier として働く。\(1+\varepsilon\) で割り有限テストと精度の net を取ると contractive approximate diagonal を得る。非零環での下界は \((\pi_L m_i)a\to a\) より \(1\)。

逆には \(A_L\) の bounded approximate diagonal \(m_i\) に対し \(w_i=\Theta_L(m_i)\) と取る。行和 \(Rw_i\to1\) は同じ対角 cutoff によりコンパクト上一様。(2) において \(B\) を値 \(1\) の plateau をもつ非負関数、\(b=B e\) と選ぶ。plateau の矢 \(\alpha\) では \(\Delta_B w_i\) の \(r\alpha\) 行は通常の左移動差 \(L_\alpha w_i^{s\alpha}-w_i^{r\alpha}\)。任意のコンパクト矢テストは有限個の枠付き plateau で覆える。\(w_i\) を \(g\in C_c(G)\) で \(I\)-近似し、端点と指定したコンパクト単位集合で \(|Rg|>1/2\) としつつ、行欠損を任意に小さくする。\(h=|g|/\max((R|g|)\circ r,1/2)\) はその単位集合上で行和 \(1\)、全単位上で行和 \(1\) 以下。絶対値は収縮的で、両端の分母が \(1/2\) 以上なので正規化後の欠損は \(g\) の高々 \(4\) 倍である。\((1-Rh(x))\delta_{1_x}\) を足せば全単位で確率。これは \(k\in C_c(G)\) に対し \(R(kh)(x)+(1-Rh(x))k(1_x)\) が連続で、テストの端点では補正は零である。従ってコンパクト矢集合上一様な連続 Reiter 確率系の net が得られる。

台の条件も保持できる。スカラー \(p\in C_c(G)\) の台を含む反転対称な開集合 \(O\) 内で、\(\beta_{\mathcal T}\) のほぼ最小分解の全項に共通の cutoff を掛ける（\(p\) の台で \(1\)）。逆脚の cutoff も各 \(U_j\cap O\) 内で選べるため、通常の有限 lift の両脚が \(O\) に入る。中間の unitary は両脚で \(v\circ s,\ v^{-1}\circ r\) を掛けるのでこの台を保つ。任意の線束テスト \(b\) 自身についても、\(|b|=\sum\limits_j g_j\) を枠付きチャートでほぼ最小に分解し、\(H=\sum\limits_j|g_j|\) として \(b_j=b|g_j|/H\)（\(H=0\) では零）とすればよい。\(|b_j|\le |g_j|\) から連続性が従い、\(\sum b_j=b\)、各台は \(\operatorname{supp}b\cap\operatorname{supp}g_j\) 内に入る。コストは \(\|b\|_I\) に任意に近くできる。

特にコンパクト単位・連続 proper 対称長さ・一様 doubling \(C\) の場合、前回の対称スカラー確率密度 \(h_R\) をそのまま使える。有限テスト \(\operatorname{supp}b\subset\{\ell\le M_b\},\ M_b\le R/2,\ R>0\) と任意の \(\rho,\varepsilon,\eta>0\) に対し、両脚が \(\{\ell<2R+\rho\}\) にコンパクト台をもつ普通の有限テンソル \(Z\) が存在し、
\[
 \pi_L Z=1_X,\quad \|Z\|_\pi\le1+\varepsilon,\quad
 \|bZ-Zb\|_\pi\le 4C^6(1+2C^2)\|b\|_I M_b/R+\eta .
\]
(1) を各 \(b_j\) に使い、相対交換子の評価で分解コストの下限を取り、上記の有限 lift と平均を行えばよい。\(b\) が一つの bisection に支えられれば \(\|b\|_I=\|b\|_\infty\)。\(Z/(1+\varepsilon)\) は contractive で積は \(1_X/(1+\varepsilon)\)。固定半径の普通の有限テンソルで積 \(1_X\) とノルム \(1\) を同時に達成することは未確認である。[前ノートの対称密度と欠損定数](06-etale-counting-i-contractive-propagation.md)

## 大域枠を持たない例

\(S^2\) 上で \(E_0\) を自明線、\(E_1\) を赤道の貼り合わせ関数 \(z\mapsto z\) を持つ Hopf 線束とする。\(G=S^2\times(\{0,1\}\times\{0,1\})\) で、矢 \((x,i,j)\) の線を \(\operatorname{Hom}(E_j(x),E_i(x))\) とし、合成と随伴を使う。\(1,0\) 成分は Hopf 線束であり、大域単位枠があれば赤道の貼り合わせ関数は二つのディスクに延びる関数の比となって巻き数零になるので矛盾する。各 range 行の二矢に与えた一様確率は連続かつ厳密に左不変である。従ってこの非自明な線束の counting \(I\)-環にも定数 \(1\) が適用される。
