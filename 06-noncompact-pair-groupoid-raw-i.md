# 非コンパクトな pair groupoid の raw \(I\)-ノルムと近似対角（WIP）

**研究途中のノート。** 書面で検算した結果であり、論文・プレプリント・査読済みの成果・Lean 形式化ではありません。先行研究に対する優先性は未確認です。

非空な局所コンパクト Hausdorff 空間 \(X\) と、full support を持つ正 Radon 測度 \(\mu\) を考える。**点原子を含まないコンパクト集合が任意に大きな質量を持てば、pair groupoid の raw \(I\)-ノルム環は contractive な近似対角を持つ。** 一方、非原子的部分の質量が \(1\) でも、質量 \(j\) の原子を各 \(j\ge1\) に加えた例では、有界近似対角が存在しない。可算離散空間の counting measure では定数は \(1\) であり、原子の重みが結論に影響する。

複素核 \(C_c(X^2)\) に
\[
 (a\ast b)(x,y)=\int_X a(x,t)b(t,y)\,d\mu(t),\qquad
 \|a\|_I=\max\left\{
    \sup_x\int_X|a(x,y)|\,d\mu(y),\
    \sup_y\int_X|a(x,y)|\,d\mu(x)
 \right\}
\]
を入れ、その完備化を \(A_X\) とする。以下、\(\mathrm{AM}(A)\) は、通常の射影テンソル積 \(A\widehat\otimes_\pi A\) における有界近似対角の最適定数を表す。積写像を \(\pi\) とすると、近似条件は各 \(a\in A\) に対する \([a,m_\alpha]\to0\) と \(\pi(m_\alpha)a\to a\) である。groupoid の \(I\)-ノルムの規約は Muhly–Williams（2008）の式 (1.3)、Banach amenability の近似対角による特徴づけは Johnson（1972）に従う。[Muhly–Williams, 式 (1.3)](https://arxiv.org/pdf/0806.1022#page=6)・[Johnson, *Approximate Diagonals and Cohomology of Certain Annihilator Banach Algebras*](https://doi.org/10.2307/2373751)

## 1　コンパクトな両端から近似対角を移す

**局所化命題。** \(1\le C<\infty\) とする。各コンパクト集合 \(L\subset X\) と各 \(\eta>0\) に対し、\(L\subset O\) となる相対コンパクトな開集合があり、\(K=\overline O\) と制限測度 \(\mu|_K\) について \(\mathrm{AM}(A_K)\le C+\eta\) が成り立つとする。このとき \(\mathrm{AM}(A_X)\le C\) である。

まず \(\mu|_K\) は \(K\) に full support を持つ。実際、\(V\subset X\) が開で \(V\cap K\ne\varnothing\) なら、\(V\cap O\) は \(X\) の非空開集合であり、\(\mu(V\cap K)\ge\mu(V\cap O)>0\) である。

**有限次元での延長。** 有限個のテスト \(a_j\in C_c(X^2)\) の台の両射影を \(L\) に入れ、\(r_j=a_j|_{K^2}\) とする。\(r_j\) を含む任意の有限次元空間 \(E\subset C(K^2)\)、有限個の指定積 \(u,v,w=u\ast_Kv\in E\)、および \(\delta>0\) に対し、線形写像 \(J:E\to C_c(X^2)\) を
\[
 (Je)|_{K^2}=e,\qquad Jr_j=a_j,\qquad
 \|J\|_{I,K\to I,X}\le1+\delta,\qquad
 \|Ju\ast Jv-Jw\|_{I,X}<\delta
 \tag{1}
\]
と取れる。

実際、\(r_j\) の張る部分では \(H_{r_j}=a_j\) と置く。各 \(a_j\) が \(K^2\) の外で消えるため、この指定は線形関係を保つ。補空間の基底は、コンパクト Hausdorff 空間 \((X^2)^+\) 上で実部・虚部を Tietze 延長し、\(K^2\) 上で \(1\) のコンパクト台 cutoff を掛ける。こうして線形な延長 \(e\mapsto H_e\) を得る。ここで必要な正規性は一点コンパクト化が与える。

\(E\) の \(I_K\)-単位球はコンパクトで、その上で \(M_E=\sup\|H_e\|_\infty<\infty\) である。\((x,e)\mapsto\int_K|H_e(x,y)|\,d\mu(y)\) は連続で、\(x\in K\) では \(1\) 以下だから、\(K\) の一つの近傍で全単位球について \(1+\delta/2\) 以下になる。列にも同じ評価を取る。相対コンパクトな近傍 \(U_0\supset K\) を固定し、外正則性で近傍 \(K\subset U\subset U_0\) を縮めて \(\mu(U\setminus K)M_E<\delta/2\) とする。\(K\) 上で \(1\) の \(0\le h\le1\), \(h\in C_c(U)\) により \(Je(x,y)=h(x)h(y)H_e(x,y)\) と置けば、(1) のノルム評価とテストの厳密な復元が従う。

積については
\[
 D_{uv}(x,y)=\int_K H_u(x,t)H_v(t,y)\,d\mu(t)-H_w(x,y)
\]
が連続で \(K^2\) 上で消える。コンパクト性により、有限個の指定積すべてについて \(\sup_{U^2}|D_{uv}|\) を任意に小さくできる。中間変数の因子 \(h(t)^2\) は \(K\) 上で \(1\) なので、行と列のいずれについても積誤差は
\[
 \mu(U_0)\left(\sup_{U^2}|D_{uv}|+
       \mu(U\setminus K)\|H_u\|_\infty\|H_v\|_\infty\right)
\]
以下である。\(h\) を選ぶ前に \(U\) を縮めれば (1) を得る。

**射影ノルムでの移送。** ここでは \(E\) を選ぶ順序が重要である。まず \(A_K\widehat\otimes_\pi A_K\) の近似対角から、指定テストで両誤差が \(\eta\) 未満、ノルムが \(C+2\eta\) 以下の元を選ぶ。これを \(C(K^2)\odot C(K^2)\) の有限テンソル \(m\) で \(\eta\) 未満に近似する。この置換でテスト \(r_j\) の交換子誤差の増分は \(2\eta\|r_j\|_I\) 以下、積誤差の増分は \(\eta\|r_j\|_I\) 以下である。

次に、\(m\) と **各** \([r_j,m]\) について、因子のノルム積の和がそれぞれの射影ノルム \(+\eta\) 未満となる、代数的に正確な有限和表示を選ぶ。これは、稠密な \(C(K^2)\) 上の有界双線形形式が \(A_K\) に同じノルムで延長し、代数的テンソルの射影ノルムがその双線形形式で計算できるためである。これらすべての表示を選んだ後で、その因子、交換子を展開する積、\(\pi_Km\)、\((\pi_Km)\ast_K r_j\) を一つの \(E\) に入れる。[Grothendieck（1955）, *Produits tensoriels topologiques et espaces nucléaires*](https://doi.org/10.1090/memo/0016)

\(m=\sum\limits_{\ell=1}^N u_\ell\otimes v_\ell\) を上で選んだ表示とし、\(M=(J\otimes J)m\)、\(S_m=\sum\limits_{\ell=1}^N(\|u_\ell\|_I+\|v_\ell\|_I)\) と置く。(1) から
\[
\begin{aligned}
 \|M\|_\pi
 &\le (1+\delta)^2(\|m\|_\pi+\eta),\\
 \|[a_j,M]\|_\pi
 &\le (1+\delta)^2(\|[r_j,m]\|_\pi+\eta)
          +\delta(1+\delta)S_m,\\
 \|(\pi_XM)\ast a_j-a_j\|_I
 &\le N\delta\|a_j\|_I+\delta
          +(1+\delta)\|(\pi_Km)\ast_K r_j-r_j\|_{I,K}.
\end{aligned}
\]
第二式の第一項には交換子自身の小さい表示を使った。\(N,S_m\) の決定後に \(\delta\) を選べるため、これらに \(K\) にわたる一様上界は要らない。有限テストと精度でネットを取り、\(C+o(1)\) の上界を \(C\) にリスケールする。稠密性で \(A_X\) の全テストについて近似対角となり、局所化命題が従う。

## 2　中間変数に使える非原子的質量

コンパクト版から用いる入力は次の式である。無限コンパクト Hausdorff 空間 \(K\) 上の有限 full-support Radon 測度について、その非原子的部分の質量を \(d_K>0\) とすると
\[
 \mathrm{AM}(A_K)=\frac{\mu(K)}{d_K}.
 \tag{2}
\]
これは粟津光（2026）のコンパクト pair groupoid に関する WIP の結果である。確率測度での定式化からは、\(\mu|_K\) をその全質量 \(m_K\) で割るとき核を \(a\mapsto m_Ka\) と移せば、積とノルムがともに保たれる。非原子的部分自体の full support は仮定しない。[非原子的な場合](https://github.com/unti-fourier/thesis-extension-notes/blob/aedd8ca5a4d0d3d31e65048338b83095c5d7bd6b/06-pair-groupoid-raw-i-amenability.md)・[有限個の点原子を持つ場合](https://github.com/unti-fourier/thesis-extension-notes/blob/aedd8ca5a4d0d3d31e65048338b83095c5d7bd6b/06-pair-groupoid-finite-point-atoms.md)・[可算無限個の点原子を持つ場合](https://github.com/unti-fourier/thesis-extension-notes/blob/aedd8ca5a4d0d3d31e65048338b83095c5d7bd6b/06-pair-groupoid-countable-atoms.md)

いま
\[
 \sup\bigl\{\mu(D):D\subset X\text{ はコンパクトで、すべての }x\in D
                         \text{ について }\mu(\{x\})=0\bigr\}=\infty
 \tag{3}
\]
とする。外端のテストを含む相対コンパクトな開集合 \(W\) を先に固定する。(3) から質量の大きな \(D\) を取り、外正則性と局所コンパクト性で \(D\subset V\Subset X\)、\(\mu(\overline V\setminus D)<1\) とする。\(K=\overline{W\cup V}\) は無限コンパクトである。有限 Radon 測度の各原子は一点に集中するので \(d_K\ge\mu(D)\) であり、
\[
 \frac{\mu(K)}{d_K}\le 1+\frac{\mu(\overline W)+1}{\mu(D)} .
\]
右辺を \(1\) に任意に近づけて局所化命題を使えば、**\(\mathrm{AM}(A_X)=1\)** を得る。下界 \(1\) は非零のテストに対する積条件から従う。\(\sigma\)-compact な \(X\) では、(3) は非原子的部分の全質量が無限であることと同値である。

Lebesgue 測度を持つ \(\mathbb R\) では、テストの両端を内部に含む閉区間を取れば、すでに (2) の比が \(1\) である。可算離散空間の counting measure では別の構成がある。有限集合 \(F\) 上の行列単位を \(E_{ij}\) とすると
\[
 m_F=\frac1{|F|}\sum\limits_{i,j\in F}E_{ij}\otimes E_{ji}
\]
は符号付き置換行列 \(U\) にわたる \(U\otimes U^{-1}\) の平均である。各脚の絶対行和・列和はともに \(1\) で、\(\pi(m_F)=\sum\limits_{i\in F}E_{ii}\) だから \(\|m_F\|_\pi=1\) である。\(m_F\) は有限角と可換で、その角の核のゼロ延長は積とノルムを保つ。したがって \(F\) を広げると contractive な近似対角を得る。この例では (3) の左辺は \(0\) である。有限行列群の平均の公式は Grønbæk–Johnson–Willis（1994）, Proposition 3.2 にもある。[Grønbæk–Johnson–Willis, Proposition 3.2](https://arxiv.org/pdf/math/9209211#page=8)

## 3　有限の正の非原子的質量を持つ反例

\(Y=[0,1]\)、\(X=Y\sqcup\mathbb N_{\ge1}\) を位相的直和とし、
\[
 \mu=dt+\sum\limits_{j\ge1}j\,\delta_j
\]
とする。各 \(Y\sqcup\{1,\ldots,k\}\) はコンパクト開で、その核環は (2) により amenable である。一方、**\(A_X\) に有界近似対角は存在しない。**

\(T_a\) を \(L^2(\mu)\) 上の核作用素とする。各行で重み \(|a(x,y)|\) を使って Cauchy–Schwarz を適用し、次に列について積分すると \(\|T_a\|\le\|a\|_I\) を得る。この表現は完備化に延長する。[Schur（1911）, 行・列評価の原論文](https://doi.org/10.1515/crll.1911.140.1)

\(e_j=\mathbf1_{\{j\}}/\sqrt j\) とし、\(P_T\) を \(e_1,\ldots,e_T\) の張る空間への直交射影とする。\(P_T\) は区間成分ではゼロである。上界 \(C\) の近似対角 \(m_\alpha\) が存在すると仮定する。写像
\[
 \Phi_T(a\otimes b)=T_aP_TT_b
\]
は trace class に値を取り、\(\|\Phi_T\|_{\pi\to S_1}\le\|P_T\|_{S_1}=T\) である。従って \(S_{\alpha,T}=\Phi_T(m_\alpha)\) は \(\|S_{\alpha,T}\|_{S_1}\le TC\) を満たす。また外側の左右作用を保つため、固定した \(T\) と任意のテスト \(u\) に対し
\[
 \|[T_u,S_{\alpha,T}]\|_{S_1}
 \le T\|[u,m_\alpha]\|_\pi\longrightarrow0 .
\]

各 \(|e_j\rangle\langle e_n|\) は連続コンパクト台の核で実現される。これとの交換子の \((j,n)\) 成分を取ると、\(S_{\alpha,T}\) の \(j\) 番目と \(n\) 番目の対角成分の差がゼロに収束する。相異なる \(N\) 個の対角成分の絶対値の和は、正値性を仮定せず trace norm 以下である。従って \(n,T,N\) を固定して \(\limsup_\alpha\) を取ると
\[
 \limsup_\alpha|\langle S_{\alpha,T}e_n,e_n\rangle|\le TC/N .
\]
ここで \(N\to\infty\) とすれば左辺はゼロになる。一方、\(|e_n\rangle\langle e_n|\) に対する積条件は \(\langle T_{\pi(m_\alpha)}e_n,e_n\rangle\to1\) を与える。

最後に、\(\|a\|_I,\|b\|_I\le1\) の連続コンパクト台核について残差を評価する。
\[
 \big|\langle T_a(1-P_T)T_b e_n,e_n\rangle\big|
 \le n\int_{Y\sqcup\{j>T\}}|a(n,y)b(y,n)|\,d\mu(y)
 \le \frac1n+\frac nT .
\]
実際、\(Y\) 上では \(a\) の列と \(b\) の行から両因子がそれぞれ \(1/n\) 以下で、\(\mu(Y)=1\) である。原子 \(j>T\) では \(a\) の第 \(n\) 行から \(|a(n,j)|\le1/j\le1/T\)、\(b\) の第 \(n\) 列から \(\int|b(y,n)|\,d\mu(y)\le1\) を得る。この有界双線形評価を射影テンソル積に延長して \(m_\alpha\) に適用すると、各固定 \(n,T\) について
\[
 1\le C\left(\frac1n+\frac nT\right)
\]
となる。まず \(T\to\infty\)、次に \(n\to\infty\) とすれば矛盾する。こうして非 amenability は全体の環で直接従う。(3) は十分条件であり、非コンパクト基底についての一般分類は残る。
