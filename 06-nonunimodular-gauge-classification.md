# Raw I-amenability of locally trivial gauge groupoids with nonunimodular isotropy

研究途中経過（work in progress）。論文・プレプリント・査読済み成果ではありません。書面検算のみで、Lean 形式化や新規性の確認は未実施です。

**無限コンパクト基底では、局所基底測度が full support であれば、原子の有無や配置によらず \(\mathrm{AM}(A)=1\)** です。ここで \(H\) は amenable かつ非 unimodular な局所コンパクト Hausdorff 群、\(A\) は局所自明な右主 \(H\)-束 \(P\to X\) の gauge groupoid \((P\times P)/H\) に付随する untwisted raw \(I\)-完備化です。

非 amenable な \(H\) についても、この非自明束上で独立に必要条件を示せます。したがって、非空コンパクト Hausdorff 基底、full continuous Haar 系（局所積表示は下記）、**非 unimodular** な \(H\) の範囲で、通常の Banach amenability 定数の分類は
\[
\mathrm{AM}(A)=
\begin{cases}
1,&X\text{ が無限で }H\text{ が amenable},\\
+\infty,&X\text{ が有限、または }H\text{ が nonamenable}
\end{cases}
\]
となります。

### 二つの中間 cutoff で全測度を扱える理由

有限アトラスを、なお \(X\) を覆う \(W_\alpha\Subset V_\alpha\) に縮めます。\(X\) が無限なら、少なくとも一つの \(W=W_\alpha\) は無限です。このチャートの局所基底測度 \(\mu_W\) は有限で full support です。有限 Radon 測度の原子は点に集中するので、\(\mu_W\) は **正の非原子的部分をもつか、無限個の点原子をもつか** の少なくとも一方です。両方とも欠けば、有限集合が \(\mu_W\) の全質量を担い、\(W\) の full support に反します。以下の質量はすべて、この一つのチャートの実際の \(\mu_W\) で測ります。

- **非原子的部分が正の場合。** 可算個の点原子を除いた \(W\) の中に、正測度のコンパクト集合 \(K\) を取れます。\(0<d_0<\mu_W(K)\) を固定し、\(K\) 内に質量 \(d_0/N\) の可測片を \(N\) 個取ります。各片のコンパクトな核の質量を \((1-\epsilon)d_0/N\) 以上にし、それらを互いに素な開近傍で包みます。ここで**原子も含む \(\mu_W\) 自身の外正則性**を使えば、各近傍の質量を \((1+\epsilon)d_0/N\) 以下にできます。核上で \(1\) の bump を定数倍すると、中間 cutoff \(q_j\) の質量はすべて \(v_j=(1-\epsilon)d_0/N\) となり、\(\int q_j^2\,d\mu_W/v_j\ge[(1-\epsilon)/(1+\epsilon)]^2\) です。原子が \(W\) に稠密でもこの評価は保たれます。
- **点原子が無限個ある場合。** \(\rho=d\lambda_R/d\lambda_L\) とし、\(a=\rho(g)>1\) を固定します。原子質量を \(v_j=a^{m_j}\theta_j\)、\(1\le\theta_j<a\) と書くと、任意の \(c>1\) に対し、ある比 \(c\) 以下の区間 \([\theta,c\theta]\) に無限個の \(\theta_j\) が入ります。そこから必要な個数を選び、\(z_j=g^{m_j+L}\) とすれば
  \[
  V\le\frac{v_j}{\rho(z_j)}\le cV,\qquad V=\theta a^{-L}.
  \]
  \(V\) を小さくしてから中間添字の個数を決められます。選んだ有限個の原子には、各質量が \((1+\epsilon)v_j\) 以下の互いに素な開近傍を取れます。点上で \(1\) の bump を積分が \(v_j\) になるように縮めると、\(\int q_j^2\,d\mu_W/v_j\ge(1+\epsilon)^{-2}\) です。ここでも孤立点や、原子の尾部と最小質量との比較は不要です。

**外側の正質量**には別の理由があります。有限テストの振動に合わせたチャート被覆から冗長な要素を除くと、各 \(U_i\) に他の要素に属さない一点を選べます。それらの周りに互いに素なコンパクト近傍 \(L_i\subset U_i\) を先に確保します。full support より \(\mu_i(L_i)>0\) です。残りを被覆順に割り当て、有限基準測度 \(\sum_\alpha\mu_\alpha|_{\overline W_\alpha}\) でコンパクトな核の外の測度を \(\tau\) 未満にします。既存の連続分割の構成で、全 \(X\) 上 \(\sum_i p_i=1\)、\(\operatorname{supp}p_i\Subset U_i\)、各核上 \(p_i=\delta_{ij}\) とできます。従って
\[
w_i=\int p_i\,d\mu_i\ge\mu_i(L_i)>0,\qquad
\int p_i(1-p_i)\,d\mu_i\le\tau .
\]
有限被覆を固定してから \(\tau\) を選べば、外側の Gram 誤差も任意に小さくなります。[局所表示と Gram 補正](06-diffuse-nonunimodular-gauge-groupoid.md)

### 非自明束で内部移動が貼り合う箇所

局所切断を \(s_j=s_i t_{ij}\) と書くと、基底測度は \(d\mu_j=\rho(t_{ij})\,d\mu_i\) で変換します。この係数は既存の Gram 行列の右列評価に含まれています。今回の中間添字はすべて一つのチャート \(W\) にあるので、両脚が中間点で使う切断は同じ \(s_W\) です。Gram 補正後の正確な積公式 \(T_{p,q}(B)\ast T_{q,p}(C)=T_{p,p}(BC)\) を先に適用すると、添字 \(j\) で必要な群の等式は
\[
(R_{z_j}u)\ast(L_{z_j^{-1}}v)
 =u\ast\delta_{z_j}\ast\delta_{z_j^{-1}}\ast v=u\ast v
\]
です。これで外側の遷移と \(z_j\) を交換する仮定が消えます。[局所表示と Gram 補正](06-diffuse-nonunimodular-gauge-groupoid.md)

二つの構成で符号平均に渡す量は同じ \(e_j=v_j/\rho(z_j)\) です。等質量の場合は共通の \(z\) を選び、原子の場合は上の \(z_j\) を選びます。群の帯 \(\rho(s)\in[\alpha,c\alpha]\) で \(V\le e_j\le cV\)、\(\alpha/c\le k_iV/w_i\le\alpha\) となる長さ \(k_i\) のブロック \(J_i\) を使うと、二脚の列評価に現れる係数は
\[
\max_{j\in J_i}\frac{w_i}{k_i e_j}\le\frac c\alpha,\qquad
\frac1{w_i}\sum_{j\in J_i}e_j\le c\alpha .
\]
異なる外端 \(a,b\) の交換子にだけ \(\max(1,w_a/w_b)\) が加わり、これは群の Reiter 誤差を選ぶ前に固定されます。従って二つの Gram 誤差を \(\gamma_p,\gamma_q\) とすると、以前の符号平均はどちらの場合も projective norm が \(c^5/[(1-\gamma_p)(1-\gamma_q)]\) 以下です。積と交換子の恒等式は上の中間点での相殺によって保たれます。この上界を \(1\) に近づけて再スケールすれば、contractive な近似対角が得られます。[局所表示と Gram 補正](06-diffuse-nonunimodular-gauge-groupoid.md)

### \(H\) の amenability が必要な理由

これは中間 cutoff の構成とは独立です。一つのチャート \(U\) を選び、\(0\le\chi\in C_c(U)\) を \(\int\chi^2\,d\mu_U=1\) とします。\(B=L^1(H,\lambda_L)\) と置き、\(b\in C_c(H)\) に対し \(\iota(b)_{UU}(x,z)=\chi(x)b\chi(z)\) をゼロ延長します。中間点を有限 Borel 分割 \(E_j\subset W_j\) に分け、\(y\in E_j\) について
\[
c_F(y)=\int_U\chi(x)F_{Uj}(x,y)\,d\mu_U(x),\qquad
r_G(y)=\int_U G_{jU}(y,z)\chi(z)\,d\mu_U(z)
\]
とします。群座標のノルムを左 Haar の \(L^1\) に取ると、
\[
\sum_j\int_{E_j}\|c_F(y)\|_L\,d\mu_j(y)\le\|\chi\|_1\|F\|_{\rm row},
\qquad
\sup_y\|r_G(y)\|_L\le\|\chi\|_\infty\|G\|_{\rm row}.
\]
従って \(\Xi(F\otimes G)=\sum_j\int_{E_j}c_F(y)\otimes r_G(y)\,d\mu_j(y)\) は \(A\widehat\otimes_\pi A\to B\widehat\otimes_\pi B\) に有界に延長します。コア上では各積分の被積分関数は、該当するコンパクトなチャート部分上の連続な \(L^1\) 値関数から得られます。

両外端を \(\chi\) で積分する写像を \(P(F)=\iint\chi(x)F_{UU}(x,z)\chi(z)\,d\mu_U(x)d\mu_U(z)\) とすると、同じ中間切断での Fubini と \(\int\chi^2=1\) から
\[
\pi_B\Xi=P\pi_A,\qquad
\Xi[\iota(b),D]=[b,\Xi D],\qquad
P(F\ast\iota(b))=P(F)\ast b,\qquad P\iota(b)=b .
\]
したがって \(A\) の有界近似対角 \(D_\alpha\) があれば、\(\Xi D_\alpha\) はまず \(C_c(H)\) のテストで、次に有界性と稠密性により全 \(B\) で近似対角になります。ゆえに \(L^1(H,\lambda_L)\) は amenable であり、\(H\) も amenable です。この必要方向には大域切断も、raw \(I\) の群 corner への amenability の継承も使いません。

最後に、有限非空 Hausdorff 基底は離散で、主束には大域切断があります。この場合は既存の有限重み行列の結果が適用でき、\(\rho\ne1\) なら bounded modular point derivation により非 amenable です。これが冒頭の分類の有限側です。[有限基底の証明](06-nonunimodular-shared-middle-compression.md)

この Haar 系の局所積表示は、各 range fiber における安定化群の左不変性から得られる。実際、チャートの source 部分に台をもつ非負連続関数を掛けて群座標に押し出すと、その測度は左 Haar の定数倍になる。群座標に質量一の連続コンパクト台関数を取って定数を読み取れば、局所基底の Radon 測度が得られる。積関数で照合すれば局所積表示が従い、range 間の左移動により source 側の局所基底測度は共通になる。これは局所自明表示のある gauge groupoid の議論であって、一般の Haar groupoid への主張ではない。

中間原子による構成は[直積の場合](06-infinite-atomic-nonunimodular-product-diagonal.md)を使う。群の近似対角と `L¹(H)` の amenability から H の amenability を得る箇所は [Stokke (2004), Theorem 1.8 and Corollary 1.10](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=8) を参照。
