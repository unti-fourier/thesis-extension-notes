# A contractive raw I-norm diagonal for a nonsplit gauge groupoid

研究途中経過（work in progress）。論文・プレプリント・査読済み成果ではありません。書面検算のみで、Lean 形式化と新規性の確認は未実施です。

非空コンパクト Hausdorff 空間 \(X\) 上の局所自明な右主 \(H\) 束 \(P\) を考える。\(H\) は amenable かつ非 unimodular な局所コンパクト Hausdorff 群とする。以下の局所積表示をもつ連続 Haar 系について、局所基底測度が非原子的で full support なら、untwisted gauge groupoid \((P\times P)/H\) の raw \(I\)-完備化 \(A\) の Banach amenability 定数は \(1\) である。大域切断は仮定しない。外側 cutoff の質量は不均一でよい。Gram 補正後の積公式は \(C_c\) ではなく完備化 \(A\) の等式である。

### 1．遷移で左右の Haar 測度に掛かる係数

\(\lambda=\lambda_L\)、\(\lambda_R=\mathrm{inv}_*\lambda=\rho\lambda\) とします。局所切断を \(s_j=s_i t_{ij}\) と書くと、矢 \([s_i(x)h,s_j(y)]\) の座標変換は
\[
h'=t_{ii'}(x)^{-1}h\,t_{jj'}(y).
\]
この変換による \(\lambda\) の pushforward は \(\rho(t_{jj'}(y))\lambda\)、\(\lambda_R\) の pushforward は \(\rho(t_{ii'}(x))\lambda_R\) です。従って range 行と source 列の測度は、それぞれ
\[
d\mu_j(y)\,d\lambda(h),\qquad d\mu_i(x)\,d\lambda_R(h),
\qquad d\mu_j=\rho(t_{ij})\,d\mu_i
\tag{1}
\]
で貼り合います。

特に、基底上に一つの diffuse 測度 \(\mu\) を指定したとき、全チャートでそのまま \(\mu_i=\mu\) と置くには \(\rho(t_{ij})=1\) が必要です。一般には、台が各チャート内にある連続な 1 の分割 \((\chi_k)\) を使い、
\[
a_i=\exp\!\left(\sum\limits_k\chi_k\log\rho(t_{ki})\right),
\qquad \mu_i=a_i\mu
\]
と置けます。項は \(\operatorname{supp}\chi_k\) 上で定義してゼロ延長します。\(t_{kj}=t_{ki}t_{ij}\) より \(a_j/a_i=\rho(t_{ij})\) で、(1) を満たします。この補正に大域切断は要りません。

### 2．全域を覆い、全成分が正質量を持つ外側 cutoff

有限アトラス \(V_\alpha\) を、なお \(X\) を覆う \(W_\alpha\Subset V_\alpha\) に縮めます。有限個のテスト核に必要な振動幅を決め、空でない有限細分 \(U_i\Subset W_{\alpha(i)}\) を取ります。各 \(U_i\) は元の切断と測度を引き継ぎます。以下では
\[
\nu=\sum\limits_\alpha\mu_\alpha|_{\overline W_\alpha}
\]
を \(X\) 上の有限測度として使います。

1. 各 \(U_i\) から相異なる一点を選び、その周りに互いに素なコンパクト近傍 \(L_i\subset U_i\) を取ります。非原子的かつ full support なので、空でない開集合は無限個の点を含み、各 \(L_i\) は正質量です。**全 \(L_i\) を先に確保してから**、残りの点を、それを含む最初の \(U_i\) に割り当てます。こうして \(L_i\subset E_i\subset U_i\) を満たす Borel 分割が得られ、\(m_*=\min_i\mu_i(E_i)>0\) です。
2. \(0<\tau<m_*\) を選び、内正則性により \(L_i\subset K_i\subset E_i\) となるコンパクト集合を、\(\nu(X\setminus\bigcup_iK_i)<\tau\) となるように取ります。有限個の \(K_i\) は互いに素です。正規性により、\(K_i\) 上で \(1\)、互いに素な台を持つ \(0\le h_i\le1\) を \(\operatorname{supp}h_i\Subset U_i\) として取れます。
3. 別に、閉集合 \(F_i\subset U_i\) で \(X\) を覆い、\(F_i\subset O_i\Subset U_i\) とします。\(F_i\) 上で \(1\)、\(O_i\) の外で \(0\) の Urysohn 関数 \(g_i\) を取り、\(t_i=g_i/\sum_j g_j\) とします。分母は全点で \(1\) 以上です。そこで
   \[
   p_i=h_i+\left(1-\sum\limits_jh_j\right)t_i
   \]
   と置きます。すると全 \(X\) 上で \(\sum_i p_i=1\)、\(\operatorname{supp}p_i\Subset U_i\)、かつ \(p_i|_{K_j}=\delta_{ij}\) です。

従って \(w_i=\int p_i\,d\mu_i\) とすると
\[
w_i\ge m_*-\tau>0,\qquad
\int p_i(1-p_i)\,d\mu_i\le\tau,\qquad
\sum\limits_i w_i\le\nu(X).
\tag{2}
\]
中央の評価は、被積分関数が**すべての** \(K_j\) 上で消えることから従います。後述する外側 Gram 誤差は \(2\tau/(m_*-\tau)\) 以下です。細分を固定して \(m_*\) を得てから \(\tau\) を選ぶため、異なる細分に共通の最小質量は不要です。

### 3．Gram 逆と \(T\) の積公式が成立する空間

群測度と群密度にはそれぞれ
\[
\mathcal M_\rho=\left\{\sigma:\int_H(1+\rho)\,d|\sigma|<\infty\right\},
\qquad B_\rho=L^1(H,\lambda)\cap L^1(H,\lambda_R)
\]
を使います。測度の二つのノルムを \(\|\sigma\|_L=|\sigma|(H)\)、\(\|\sigma\|_R=\int\rho\,d|\sigma|\) とし、その最大を取ります。両方とも \(\rho(st)=\rho(s)\rho(t)\) により畳み込みに劣乗法的です。

\(b\mapsto b\lambda\) により、\(B_\rho\) は \(\mathcal M_\rho\) の閉両側 ideal です。実際、\(b\in C_c(H)\) とコンパクト台測度 \(\sigma\) の左右の積は、左 Haar に関してそれぞれ
\[
\frac{d(\sigma\ast(b\lambda))}{d\lambda}(h)
=\int b(t^{-1}h)\,d\sigma(t),\qquad
\frac{d((b\lambda)\ast\sigma)}{d\lambda}(h)
=\int \rho(t)b(ht^{-1})\,d\sigma(t).
\tag{3}
\]
いずれも連続コンパクト台です。一般の \(\sigma\) は有限 Radon 測度 \((1+\rho)|\sigma|\) のコンパクト制限で近似でき、\(C_c(H)\) は \(L^1((1+\rho)\lambda)\) に稠密です。従って (3) と劣乗法性から両側 ideal の主張が従います。

中間 cutoff \(q_j\) の質量を \(v_j>0\) とします。行列に入れるノルムと局所核は
\[
\begin{split}
\|C\|_{w,v}
 &=\max\left\{\max_i\sum\limits_j\|C_{ij}\|_L,\
          \max_j\frac1{v_j}\sum\limits_i w_i\|C_{ij}\|_R\right\},\\
J_{p,q}(C)(g)
 &=\sum\limits_{i,j}p_i(rg)\frac{q_j(sg)}{v_j}C_{ij}(h_{ij}(g)).
\end{split}
\]
コンパクト台の連続な群係数では、各項は自身のチャートからゼロ延長でき、\(J_{p,q}(C)\in C_c(G)\) です。(1) で一項ずつ行・列積分すると \(\|J_{p,q}(C)\|_I\le\|C\|_{w,v}\) なので、\(J\) は \(B_\rho\) の行列から \(A\) へ延長します。

中間点を二つの切断 \(s_j,s_k\) で書くと、次の脚の引数は \(t_{jk}(y)^{-1}u^{-1}h\) です。このため Gram に入る測度の向きは
\[
\mathcal G^q_{jk}=(t_{jk})_*
       \left(\frac{q_jq_k}{v_j}\mu_j\right),\qquad
J_{p,q}(C)\ast J_{q,r}(D)=J_{p,r}(C\mathcal G^qD).
\tag{4}
\]
重なりでの cutoff の台はチャートの共通部分内のコンパクト集合なので、各 Gram 測度はコンパクト台です。左行和は \(1\) 以下で、右列和は (1) により
\[
\frac1{v_k}\sum\limits_jv_j\|\mathcal G^q_{jk}\|_R
 =\frac1{v_k}\int q_k\sum\limits_jq_j\,d\mu_k\le1.
\]
対角成分は \(\alpha_j\delta_e\)、\(\alpha_j=v_j^{-1}\int q_j^2\,d\mu_j\) です。従って \(\gamma_q=\|I\delta_e-\mathcal G^q\|_{v,v}\le2\max_j(1-\alpha_j)\)。特に \(q=p\) では (2) の評価を使えます。

\(\gamma_q<1\) のとき、\(S_q=(\mathcal G^q)^{-1}\) は**測度行列環**で取ります。\(T_{p,q}(C)=J_{p,q}(CS_q)\) と定めることができるのは、\(CS_q\) の各成分が \(B_\rho\) に属するからです。Neumann 級数の第 \(n\) 部分和を \(S_q^{(n)}\) とすれば
\[
\|T_{p,q}(C)-J_{p,q}(CS_q^{(n)})\|_I
 \le \|C\|_{w,v}\frac{\gamma_q^{\,n+1}}{1-\gamma_q}.
\]
\(C\) が \(C_c(H)\) の行列なら右辺で近似する各核は \(C_c(G)\) に入ります。極限の台には条件を課しません。(4) をまず密度行列全体へ連続延長してから逆を代入すると、
\[
\boxed{\;
T_{p,q}(C)\ast T_{q,r}(D)
 =J_{p,r}\big((CS_q)\mathcal G^q(DS_r)\big)
 =T_{p,r}(CD)\quad\text{in }A .
\;}
\]
逆を掛ける側は右です。ここで測度行列同士を交換する操作はありません。さらに、有限テストを局所補間した核は \(J_{p,p}(C)=T_{p,p}(C\mathcal G^p)\) と書けます。この群テストには**直接の** Gram 行列が現れるので、(3) によりその成分は実際に \(C_c(H)\) です。後段で群テストの台を一つのコンパクトに取る手順も保たれます。

### 4．固定端 \(a,b\) の質量比と非自明例

中間脚には、一つのチャート内の正質量の diffuse コンパクト集合を使えば十分です。その中に質量 \(d_0/N\) の可測な片を \(N\) 個取り、各片のコンパクトな核の質量を \((1-\epsilon)d_0/N\) 以上、互いに素な開近傍の質量を \((1+\epsilon)d_0/N\) 以下にします。核上で \(1\) の bump を下向きに定数倍して、全ての質量を \(v=(1-\epsilon)d_0/N\) に揃えます。すると \(\sum_jq_j\le1\) で、\(\alpha_j\ge[(1-\epsilon)/(1+\epsilon)]^2\) です。全域を覆う性質は外側の \(p\) が担っています。

符号平均で一方の外端を \(a\)、他方を \(b\) に固定し、長さ \(k_a\) の中間ブロックを使います。内部移動を \(s\mapsto sz,\ t\mapsto z^{-1}t\) とし、\(r_a=k_av/w_a\) と置くと、二脚の右ノルムに掛かる係数は順に
\[
\frac{w_a\rho(z)}{k_av}=\frac{\rho(z)}{r_a},
\qquad
\frac{k_av}{w_b\rho(z)}
 =\frac{w_a}{w_b}\frac{r_a}{\rho(z)}.
\]
従って固定端の交換子評価に必要なのは \(\max(1,w_a/w_b)\) です。対角自身では \(b=a\) なのでこの損失はありません。外側の全 \(w_i\) と有限群テストを固定した後に群の Reiter 誤差を選び、最後に \(N\) を取る順序で足ります。比 \(c>1\) の modular 帯で得る対角自身の projective ノルム上界は \(c^4/[(1-\gamma_p)(1-\gamma_q)]\) で、これを \(1\) に近づけて再スケールすると contractive な近似対角を得ます。[直積の場合の符号平均](06-diffuse-nonunimodular-product-diagonal.md)・[Stokke (2004), Theorem 1.8](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=8)

具体例は \(H=\mathbb R\rtimes_2\mathbb Z\)、\((b,n)(c,m)=(b+2^nc,n+m)\) です。これは amenable で、\(\lambda_L=2^{-n}db\,d\#(n)\)、\(\lambda_R=db\,d\#(n)\)、\(\rho(b,n)=2^n\) です。円周上で \((1,k)\sim(0,(0,1)k)\) と貼った右主束に大域切断があれば、区間に引き戻した切断の整数座標は一定ですが、両端で \(1\) ずれるため矛盾します。局所角度の実数持ち上げを \(u\) とすると、\(u+1\) の切断は \(u\) の切断の右に \((0,1)\) を掛けたものです。円周の Lebesgue 測度から \(d\mu_u=2^u\,d\mu_{\mathbb T}\) と取れば \(d\mu_{u+1}=2\,d\mu_u\) となり、(1) と Gram の右列評価の係数をこの非自明束で直接確認できます。

### 5．有限テストへの適用

外側の細分を選ぶ段階で、固定した有限個のテスト核を各チャート対の群座標で表示する。初めに固定した縮小アトラスの閉包上では、いずれの表示も台の群方向が共通コンパクトに入り、両 Haar ノルムで連続である。細分ごとの代表点で標本化し、係数 \(C_{ij}\) に出発点側の質量 \(w_j\) を掛ければ \(J_{p,p}(C)\) は通常の partition-of-unity 補間になる。各重みを足す前にチャートごとの行・列積分をとると、その \(I\)-誤差は \(2\omega\sum_i w_i\) 以下である。ここで \(\omega\) は一端点を同じ細分内で変えた際の最大 Haar ノルムでの振動であり、\(\sum_i w_i\le\nu(X)\) は細分に依存しない。

補間を \(T_{p,p}(B)\), \(B=C\mathcal G^p\) と書き直して群テストを固定する。群テンソル \(m(s,t)=f(s)e(st)\) を符号平均に入れ、積と交換子に (4) と群密度の内部移動の性質を使う。交換子の固定端 \(a,b\) では、対応する群係数 \(b_0\) の交換子 \(b_0\cdot m-m\cdot b_0\) を入れ、上の質量比だけを追加する。左右とも積変数 \(st\) の台は、群テストを含む固定コンパクト \(K\) と固定単位近傍 \(U_0\) の \(KU_0\cup U_0K\) に収まる。従って右 Haar への移行で必要な modular 上界は、Reiter 密度 \(f\) の台に依存しない。積写像の像は \(T_{p,p}(I_ne)\) であり、\(e\) の台を単位元に縮めれば同じコンパクト上で両 Haar ノルムの左右近似が得られる。以上を有限テストと任意誤差について実行し、稠密性と再スケールを使う。非零代数なので最良定数の下界も \(1\) である。

この結果は局所自明かつ transitive な表示、非原子的な局所基底測度、untwisted convolution の範囲のものである。一般の Haar groupoid や任意の測度への拡張はここでは主張しない。
