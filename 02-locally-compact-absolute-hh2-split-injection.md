# \(L^1(G)\) の比較を使った crossed product への次数 2 の移送

研究途中経過（work in progress）。論文・プレプリント・査読済み成果ではありません。Lean 形式化および文献上の初出の確認は未実施です。

2026年11月26日。左 Haar 測度を \(ds\)、\(G\) を局所コンパクト第二可算群とする。書面で得た結論は、下記の係数とノルムの下での半ノルム等長な split injection
\[
 H_{\rm cb}^2(G,W)\ \longrightarrow\
 HH_{\rm cont}^2(A,\mathcal B(C(X),W)).
\]
\(HH_{\rm cont}\) はすべての有界多重線型 cochain を使う absolute Hochschild cohomology である。鍵は、\(A\) 内の実際の部分代数 \(f\mapsto f1_X\) に制限すると \(L^1(G)\) の積分比較を回収できることである。その比較と、個々の絶対 cochain を multiplier に strict 延長する操作は性質が異なる。

## 1. 一次出典と \(L^1(G)\) の係数

Burger–Monod (2002), §1.9, p.245 は、可分な連続 Banach \(G\)-加群 \(V\) の双対 \(V^\ast\) について、連続有界群コホモロジーと \(L^1(G)\) の Banach 環コホモロジーが一致することを述べ、Johnson (1972), Proposition 2.3 を指定している。ここで使う片側の形式は、\(W=V^\ast\) 上で左は群表現の積分、右は augmentation \(\varepsilon(f)=\int f(s)\,ds\) である。essential 性は前双対の条件である。§1.2, Proposition 1.2.2 は、双対側でノルム連続となる部分が一般には双対全体より小さくなり得ることも説明する。Johnson の原本の命題本文は今回直接参照できず、命題番号と比較の帰属は Burger–Monod の本文で確認した。半ノルム等長性については以下の核の計算を使う。[Burger–Monod, 2002, §§1.2, 1.9](https://people.math.ethz.ch/~burger/pub/2002_Continuous_bounded-cohomology.pdf#page=27)・[Johnson, Memoirs AMS 127, 1972](https://doi.org/10.1090/memo/0127)

両側の形も今回使う範囲で確認できる。\(B=L^1(G)\)、\(V\) を可分な contractive Banach \(B\)-双加群で \(\overline{BV}=\overline{VB}=V\) とし、\(W=V^\ast\) に転置した左右作用を入れる。正の質量 1 の近似単位 \((e_i)\) により、\(\delta_s\) は \(V\) の両側に作用する。左作用は \((\delta_s*e_i)v\) の、右作用は \(v(e_i*\delta_s)\) のノルム極限である。積 \(bv\)、\(vb\) の稠密性と \(L^1\) 平行移動のノルム連続性から、両群作用は強連続である。\(\delta_{s^{-1}}\) が逆で両者は等長、左右は可換する。表現延長の一般定理もこの極限を与える。以後 \(w\mapsto\delta_s w\delta_{s^{-1}}\) を \(W_{\rm Ad}\) の左群作用とする。[Dirksen–de Jeu–Wortel, 2009, Theorems 4.1, 4.3](https://arxiv.org/pdf/0904.3268#page=11)

\(c\in L^\infty_{w^\ast}(G^n,W_{\rm Ad})\) は非斉次群 cochain とし、\(t_i=s_1\cdots s_i\)、\(t_0=e\) と書く。\(f_i\in B\) に対して
\[
 J_nc(f_1,\ldots,f_n)=
 \int_{G^n}^{w^\ast}
 \Big(\prod_i f_i(s_i)\Big)\,c(s_1,\ldots,s_n)\cdot\delta_{t_n}\,d\mathbf s .
 \tag{1}
\]
実際、絶対 \(n\)-cochain 全体は \((B^{\widehat\otimes_\pi n}\widehat\otimes_\pi V)^\ast=L^1(G^n;V)^\ast=L^\infty_{w^\ast}(G^n,W)\) と等長に同一視できる。第一のテンソル同一視は長方形上の単関数の稠密性から従う。最後の双対は可分な前双対での弱スター核表示であり、\(W\) に Radon–Nikodym 性を仮定しない。核 \(K(\mathbf s)\) からは \(c(\mathbf s)=K(\mathbf s)\cdot\delta_{t_n^{-1}}\) と戻す。前双対上の強連続性により捻りは弱スター可測で、各点で等長である。Hochschild 微分の先頭では \(\delta_{s_1}\) の左作用を共役作用に直し、内部では \(u=s_js_{j+1}\) と左移動し、末尾では右から \(\delta_{s_{n+1}}\) を掛ける。全項の右因子が \(\delta_{t_{n+1}}\) に揃い、\(\partial_{\rm HH}J_n=J_{n+1}d_G\) となる。右作用が augmentation の応用では (1) の右因子は恒等である。[Burger–Monod, 2002, §1.2 と Theorem 2](https://people.math.ethz.ch/~burger/pub/2002_Continuous_bounded-cohomology.pdf#page=2)

群側で使うのは \(G\) の Haar 類に関する標準複体である。斉次形は
\[
 (\mathcal Hc)(x_0,\ldots,x_n)
 = x_0\cdot c(x_0^{-1}x_1,\ldots,x_{n-1}^{-1}x_n).
\]
増分と初点の座標変換は逐次左移動で Haar 積を保つ。逆には、不変な斉次核をこれらの座標に書き、\(x_0^{-1}\) を作用させると、初点の左移動で不変になる。Fubini により a.e. の増分で初点に関して a.e. 定数である。実際、二初点 \(x_0,ux_0\) で値が a.e. 一致し、\(u\mapsto ux_0\) は Haar の測度類を保つ。可分な前双対の可算なテストで例外を共通化できる。その定数は初点を Haar と同値な確率で平均して回収できる。両方向は交代削除と非斉次微分を結び、等長である。この標準複体が \(H_{\rm cb}\) を所定の半ノルムで計算することは Burger–Monod の Theorem 2 を左平行移動 \(G\curvearrowright G\) に用いる。Sarti–Savini の固定係数の場合、\((Y,m)\) は標準 Borel 準不変確率空間、係数は一つの可分前双対 \(V_0\) の双対で矢印がその反傾等長作用を持ち、\(V=L^1(Y,m;V_0)\)、\(W=L^\infty_{w^\ast}(Y,m;V_0^\ast)\) と取れる。同論文の定理 1 と §5 式 (20) がまさにこの群複体を与える。[Sarti–Savini, arXiv:2304.07765v2, 定理 1・§5](https://arxiv.org/html/2304.07765v2#S5)

## 2. 近似単位の使い方と strict 延長の反例

有界な、同時に弱スター連続な核 \(K(s,t)\) について、(1) の核積分に \(\delta_s*e_i,\delta_t*e_i\) を入れると、台が単位に縮む質量 1 の \(e_i\) により \(K(s,t)\) が弱スター極限として戻る。これは前双対の各元でテストしたスカラー連続性から従う。

任意の絶対 2-cocycle に同じ極限を要求することはできない。\(G=\mathbb R\)、係数は両側 augmentation の \(\mathbb C\)、\(\ell(f)=\int_0^\infty f(t)\,dt\)、\(B_2=\partial_{\rm HH}\ell\) とする。\(e_u^+=u^{-1}\mathbf1_{(0,u)}\)、\(e_u^-=u^{-1}\mathbf1_{(-u,0)}\) は、ともに \(u\downarrow0\) で両側 contractive 近似単位となり、multiplier の strict 位相で \(\delta_0\) に収束する。任意の \(\varepsilon(a)=1\) に対して
\[
 B_2(a,e_u^\pm)=\ell(e_u^\pm)-\ell(a*e_u^\pm)+\ell(a)
   \longrightarrow
   \begin{cases}1 &(+),\\0 &(-).\end{cases}
\]
従ってこの 2-coboundary でさえ、元の値を保つ各変数 strict-to-weak-star 連続な延長を持たない。この差が、module 作用の延長定理を任意のコチェインに適用できない理由である。

実際の連続**斉次** cochain に戻したければ、正の近似単位から質量 1 の \(p\in C_c(G)\) を一つ固定し、\(p_x(t)=p(x^{-1}t)\) と置く。核から得た斉次 cochain \(F\) に
\[
 (\mathsf S_nF)(x_0,\ldots,x_n)=
  \int^{w^\ast} F(y_0,\ldots,y_n)\prod_{j=0}^n p_{x_j}(y_j)\,d\mathbf y
 \tag{2}
\]
を施す。\(x\mapsto p_x\) の \(L^1\) 連続性と核の有界性から値はノルム連続であり、\(\|\mathsf S_n\|\le1\)。左移動と可換で、各頂点の積分が 1 だから交代削除とも可換である。群不変な類に対して得た連続代表は各群元で点ごとに共変である。実際、固定した群元について等式は a.e. に成立し、両辺は連続で Haar 積は全台を持つ。

連続な \(F\) で \(\mathsf S-\mathrm{id}\) を埋める homotopy は、\(n\ge1\) で
\[
 (K_nF)(\mathbf x)=\sum_{i=0}^{n-1}(-1)^i
  \int F(x_0,\ldots,x_i,y_i,\ldots,y_{n-1})
            \prod_{j=i}^{n-1}p_{x_j}(y_j)\,d y_i\cdots d y_{n-1}.
\]
交代削除を展開すると境の頂点以外の項は対で相殺し、境の項が telescope して \(dK+Kd=\mathsf S-\mathrm{id}\) となる。連続入力では優収束と \(p_x\) の \(L^1\) 連続性から各項は連続である。可測な弱スター核にも同じ計算を前双対でテストできる。自由変数 \(x_0,\ldots,x_i\) の a.e. の切片で、残る全 \(y_j\) の積分は Haar に絶対連続なので代表を取り替えてよい。(2) は連続 cochain への鎖写像で、合成はコホモロジー上で恒等となる。Burger–Monod (1999), Proposition 2.4 による正則化を使い、同論文では係数自体を可分とする点に留意して、ここでは固定可分前双対の弱スター核で必要な検算を行った。[Burger–Monod, 1999, Proposition 2.4](https://ems.press/content/serial-article-files/31465?nt=1#page=9)

## 3. \(C(X)\) による crossed product と左逆

\(X\ne\varnothing\) はコンパクト Hausdorff、\(D=C(X)\) とし、\(\alpha_s p(x)=p(s^{-1}x)\) は \(D\) 上強連続とする。まず \(A_1=L^1(G,D;\alpha)\) を Bochner ノルムで取り、積は \((a*b)(u)=\int a(s)\alpha_s(b(s^{-1}u))\,ds\)。\(X\) の距離化可能性は使わない。\(W=V^\ast\) は上記の群作用 \(U_s\) を持ち、追加データとして unital contractive 表現 \(\pi:D\to\mathcal B(W)\) があり、各 \(\pi(p)\) は弱スター連続で
\(U_s\pi(p)U_s^{-1}=\pi(\alpha_s p)\) と仮定する。群表現は可分な前双対上の強連続等長作用の反傾作用である。[de Jeu–Messerschmidt–Wortel, arXiv:1305.2304, Definition 5.4](https://arxiv.org/pdf/1305.2304#page=17)

\(N=(D\widehat\otimes_\pi V)^\ast=\mathcal B(D,W)\) 上で
\[
 \tau(a)p=\int a(s)\alpha_s(p)\,ds,\qquad
 \Pi(a)w=\int^{w^\ast}\pi(a(s))U_sw\,ds,\qquad
 a\cdot T=\Pi(a)T,\quad T\cdot b=T\tau(b).
\]
共変性と \(u=st\) により \(\Pi,\tau\) は表現で、二つの作用は可換する。各 \(\Pi(a)\) の前転置は \(v\mapsto\int (U_s)_\ast\pi(a(s))_\ast v\,ds\)。これはまず \(C_c(G,D)\) 上 Bochner 積分で定まり、ノルム連続に延びる。\(i:B\to A_1,\ i(f)(s)=f(s)1_X\) は等長な代数準同型である。\(i(e_i)\) は \(A_1\) の両側 contractive 近似単位でもある。左からの積は \(a(\cdot)\mapsto\alpha_s(a(s^{-1}\cdot))\) の平均で、この作用は有限個の単純テンソル上の検算と稠密性から \(L^1(G;D)\) で強連続である。右からの積は単純テンソル上でスカラー \(L^1(G)\) の右側の近似単位に帰着する。\(i(e_i)\) は前双対の両側でも恒等に強収束する。左側は \(\tau(i(e_i))p\to p\)、右側は \(\Pi(i(e_i))_\ast v\to v\) を純テンソルに適用すればよい。従って \(D\widehat\otimes_\pi V\) は essential である。

\(n=1,2,3\) に対して次の積分を \(C_c(G,D)\) 上で定める。
\[
 (\Phi_n c)(a_1,\ldots,a_n)(p)=
 \int_{G^n}^{w^\ast}
 \pi\!\left(\Big[\prod_{j=1}^{n}\alpha_{t_{j-1}}(a_j(s_j))\Big]\alpha_{t_n}(p)\right)
 c(s_1,\ldots,s_n)\,d\mathbf s .
 \tag{3}
\]
係数に掛ける \(D\) 値関数はノルム連続で、前双対とのペアリングは可測である。積分の評価は \(\|c\|_\infty\|p\|\prod_j\|a_j\|_{A_1}\) 以下なので (3) は全 \(A_1\) へ一意に延びる。\(\partial_{\rm HH}\Phi_n=\Phi_{n+1}d_G\)（\(n=1,2\)）を確かめると、先頭項では \(U_{s_1}\pi(d)=\pi(\alpha_{s_1}d)U_{s_1}\)、各内部項では twisted convolution と \(u=s_js_{j+1}\)、末尾項では \(\tau(a_{n+1})p\) を使う。Fubini で全項を同じ積分に揃えると (3) の共通の乗数の下に非斉次微分が残る。ここには右 Haar への変数変換はない。

任意の absolute cochain \(B_n\) を
\[
 (\mathsf R_n B_n)(f_1,\ldots,f_n)
   =B_n(i(f_1),\ldots,i(f_n))(1_X)
 \quad(f_j\in L^1(G))
 \tag{4}
\]
で戻す。\(P(T)=T(1_X)\) は \(i(B)\) に制限した双加群写像である。左作用は \(U(f)=\int^{w^\ast}f(s)U_s\,ds\)、右は \(\tau(i(f))1_X=\varepsilon(f)1_X\) から augmentation になる。従って \(\mathsf R_n\) は contractive な鎖写像で、(3) に代入すると \(\mathsf R_n\Phi_n=J_n\) が cochain として成り立つ。この \(J_n\) は右 augmentation の (1) である。特に \(J_n^{-1}\mathsf R_n\) が Haar 核の模型での contractive な左逆であり、群コホモロジーと absolute \(HH^2\) の商半ノルムは像上で等しい。連続斉次の模型での戻りは \(\mathsf S_n\mathcal H J_n^{-1}\mathsf R_n\) で、合成は (2) の正則化になる。\(1_X\) は \(T\) の定義域のベクトルで、(4) のすべての代数入力は \(L^1\) 関数である。

## 4. 行ノルムで検証できる係数と残る入力

方針2で使う非離散版の一候補を明示的に \(A_{\rm row}=\overline{C_c(G,D)}^{\|\cdot\|_{\rm row}}\)、\(\|a\|_{\rm row}=\sup_{x\in X}\int_G|a(s)(x)|\,ds\) と定める。この完備化の Banach 空間は \(C(X,L^1(G))\) と等長に一致する。各 \(a\in C_c(G,D)\) の値域はノルム相対コンパクトなので \(x\mapsto a(\cdot)(x)\) は \(L^1\) 連続である。逆にコンパクト \(X\) 上の有限な 1 の分割と \(C_c(G)\) の \(L^1\) 稠密性により、任意の連続場を \(\sum_k p_k(x)f_k(s)\) の形で一様近似できる。ここで (3) が延びることは一般の essential 性からは出ない。Sarti–Savini の上記 \(W=L^\infty_{w^\ast}(Y,m;V_0^\ast)\) に、さらに \(G\)-同変な可測 anchor \(\rho:Y\to X\) があり、\(\pi(p)\) を \(p\circ\rho\) によるスカラー乗算とする場合には延びる。各 \(p\circ\rho\) の可測性と各 \(s\) についての a.e. の共変性で足りる。\(\alpha\) の強連続性により、群変数にノルム連続な \(D\) 値関数を可分な値域で単関数近似でき、これらの乗数は同時可測になる。弱スター核 \(c\) は \(G^n\times Y\) の同時可測な弱スター代表を持つ。これは \(L^1(G^n;L^1(Y;V_0))=L^1(G^n\times Y;V_0)\) の双対を取ることで分かる。

\(x=\rho y\) とし (3) の絶対値を見積もると、使う積分は
\[
 \int_{G^n}\prod_{j=1}^n
    |a_j(s_j)(t_{j-1}^{-1}x)|\,d\mathbf s
       \ \le\ \prod_{j=1}^n\|a_j\|_{\rm row}.
\]
最終変数から順に積分すれば、これはすべての \(x\) で成立する。Fubini により \(m\)-a.e. の \(y\) で \(\|c(\mathbf s)(y)\|\le\|c\|_\infty\) を使える。従って \(\Phi_n\) は行ノルムでも contractive である。同じ一変数評価で \(\tau,\Pi\) も contractive になる。\(\Pi\) では \((U_sw)(y)\) のノルムが積測度 a.e. に \(\|w\|\) 以下であることを、反傾等長作用・準不変性・Fubini から使う。既に得た前転置は等しい作用素ノルムで延長される。行ノルムでの積の連続性も同じ二重積分評価から従う。\(\|a\|_{\rm row}\le\|a\|_{A_1}\) と稠密性により \(i(e_i)\) はこの完備化の両側 contractive 近似単位でもある。\(i\) は行ノルムでも等長なので (4) と \(\mathsf R\Phi=J\) が保たれ、実際にこの \(A_{\rm row}\) にも同じ半ノルム等長な移送がある。

例えば \(Y=X\) がコンパクト距離化可能で \(m\) が準不変 Borel 確率なら、\(\rho=\mathrm{id}\) が追加の乗数条件を満たす。上の anchor がある場合、前双対は射影テンソルの結合則と Bochner 単関数の稠密性により \(L^1(Y;D\widehat\otimes_\pi V_0)\) と等長で、右 \(C(X)\) 作用は \(Y\) 変数での \(p\circ\rho\) の乗算である。したがって \(p_j\ge0\) なら \(\sum_j\|v\cdot p_j\|=\|v\cdot\sum_jp_j\|\le\|\sum_jp_j\|_\infty\|v\|\) で、右 type (M) も保たれる。非零の入力類があればその半ノルムが移る。Sarti–Savini の比較だけでは所望の非零類や \(\rho:Y\to X\) は作られず、逆向きの因子写像 \(X\to Y\) だけではここで用いた \(C(X)\) 乗数は定まらない。ほかの crossed-product ノルム、任意の係数に対する同型、一般の非離散作用の逆向きは未検証である。今回の成果は書面証明である。
