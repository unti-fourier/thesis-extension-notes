# A contractive raw I-norm diagonal over infinitely many atoms

研究途中経過（work in progress）。論文・プレプリント・査読済み成果ではありません。書面検算のみで、Lean 形式化・新規性の確認は未実施です。

**書面検算の結論は \(\mathrm{AM}(A)=1\) です。** \(X\) をコンパクト Hausdorff、\(\mu\) を無限個の原子をもつ純原子的な full-support 有限 Radon 測度、\(H\) を非 unimodular な amenable 局所コンパクト群とします。積 Haar 系を入れた \(X\times H\times X\) の untwisted raw \(I\)-完備化 \(A\) は、通常の projective norm で contractive な近似対角をもちます。原子が非孤立でも成立します。

### pair の trace obstruction を積分商に移せない理由

有限基底での非 amenability は、群の character \(\chi(b)=\int b\sqrt{\rho}\,d\lambda_L\) における非零の modular point derivation から従います。一方、無限純原子的な **pair** 環では、\(L^2(\mu)\) 上の有限個の原子への射影を使うと、近似対角の上界 \(C\) に対して \(1\le C\mu(X\setminus F)\) がすべての有限原子集合 \(F\) で必要になります。後者の射影は Hilbert 空間上で使うので、原子の孤立性は既存の証明にも不要です。以下では \(\mu(X)=1\) に正規化します。[有限基底の modular derivation](06-nonunimodular-shared-middle-compression.md)・[pair 環の有限階数 trace 評価](06-pair-groupoid-countable-atoms.md)

\(\lambda_R=\rho\lambda_L\) とし、\(QF(x,y)=\int_H F(x,h,y)\,d\lambda_L(h)\) と置きます。\(Q\) は \(C_c\) 上で積を保ちますが、非 unimodular な \(H\) では pair の列ノルムに関して非有界です。実際、質量 \(a\downarrow0\) の原子 \(y_a\) に対し、外正則性から
\[
0\le\phi\le1,\qquad \phi(y_a)=1,\qquad
s=\int_X\phi\,d\mu\in[a,2a]
\]
となる連続 cutoff を取れます。\(\{\rho<s\}\) 内に台を持つ左 Haar 確率密度 \(f\in C_c(H)_+\) を取り、\(F(x,h,y)=\phi(y)f(h)/s\) とすると
\[
\|F\|_{\rm row}=1,\qquad
\|F\|_{\rm col}=\frac{\|f\|_{L^1_R}}s\le1,\qquad
\|QF\|_{\rm row}=1,\qquad
\|QF\|_{\rm col}=\frac1s\longrightarrow\infty .
\]
右 Haar で積分すると、反転により今度は行ノルムが発散します。このため、pair の trace 下界を積分商で移す議論はここで止まります。unimodular の場合には左右の Haar が一致し、同じ \(Q\) が実際に contractive な全射になります。[unimodular 積の商写像](06-product-pair-unimodular-group.md)

### 無限個の原子から近似対角を作る方法

diffuse 版から変更するのは中間の脚です。**中間原子 \(j\) ごとに異なる \(z_j\in H\) を選び、二脚を \(s\mapsto sz_j,\ t\mapsto z_j^{-1}t\) と動かします。** 各項で積 \(st\) は保存され、列ノルムに現れる中間質量は \(v_j/\rho(z_j)\) になります。これを任意の精度で揃えられます。

実際、\(c>1\) を固定し、\(\rho(g)=A_0>1\) となる \(g\in H\) を取ります。各原子質量 \(v_j\) を \(v_j=A_0^{m_j}\theta_j\)、\(1\le\theta_j<A_0\) と書きます。\([1,A_0]\) を比 \(c\) 以下の有限個の区間で覆うと、ある \([\theta,c\theta]\) に無限個の \(\theta_j\) が入ります。この中から必要な有限個を選び、
\[
z_j=g^{m_j+L},\qquad V=\theta A_0^{-L}
\quad\Longrightarrow\quad
 V\le\frac{v_j}{\rho(z_j)}\le cV
\tag{1}
\]
とできます。\(L\) を大きくすれば \(V\) は任意に小さくなります。

非孤立原子でも、選んだ**有限個**の点には互いに素な開近傍を取り、各近傍の測度を \((1+\epsilon)v_j\) 以下にできます。点上で \(1\) の連続 bump を定数倍して \(\int q_j\,d\mu=v_j\) とすると
\[
\sum_jq_j\le1,\qquad
\frac{\int q_j^2\,d\mu}{v_j}\ge(1+\epsilon)^{-2}.
\]
従って中間の Gram 行列は対角で、単位行列との距離を任意に小さくできます。外側の cutoff \(p_i\) は有限テストの振動に合わせた被覆から作ります。冗長な開集合を除けば各開集合に相異なる一点を選べるので、その正測度近傍を先に確保する既存の構成が使えます。外側の質量 \(w_i=\int p_i\,d\mu>0\) は不均一で構いません。[外側 cutoff と Gram 補正後の積公式](06-diffuse-nonunimodular-gauge-groupoid.md)

**ノルムと中心化の検算。** 前報のコンパクト台群テンソル \(m(s,t)=f(s)e(st)\) と有限テストの交換子を含むコンパクト長方形を固定します。\(\rho(s)\in[\alpha,c\alpha]\)、\(\rho(t)\in[\beta,c\beta]\) の有限個の帯に分け、各帯で \(k_i=\lfloor w_i\alpha/V\rfloor\) とします。まず (1) の \(V\) を小さくして、全ての \(i,\alpha\) で
\[
\alpha/c\le k_iV/w_i\le\alpha
\]
とし、その後で \(N\ge\max_\alpha\sum_i k_i\) 個の原子を選びます。\(N\) 個の中間添字に長さ \(k_i\) の互いに素なブロックを置きます。割り当て \(j\mapsto i\) に対する二脚の成分を \(\varepsilon_j R_{z_j}u/k_i\)、\(\varepsilon_j L_{z_j^{-1}}v\) とします。ここで平行移動は左 Haar **密度の pushforward** です。

第一脚の左行和は \(\|u\|_L\)、右列和は \(\frac{w_i\rho(z_j)}{k_iv_j}\|u\|_R\) 以下です。第二脚の左行和は \(\|v\|_L\)、右列和は \(\frac1{w_i}\sum_{j\mapsto i}\frac{v_j}{\rho(z_j)}\|v\|_R\) です。従って (1) により二脚のノルムの積は
\[
c^4\max(1,\alpha\beta)\,\|u\|_L\|v\|_L
\]
以下です。固定した異なる外端 \(a,b\) で交換子を評価するときだけ、さらに \(\max(1,w_a/w_b)\) が掛かります。

独立符号の平均で異なる \(j\) の交差項が消え、巡回シフトの割当て確率 \(k_i/N\) と \(1/k_i\) の積は \(1/N\) です。従って全帯で同じテンソル写像が得られます。\(z_j\) は帯にも外端にも依存しません。各 \(j\) で
\[
(R_{z_j}u)\ast(L_{z_j^{-1}}v)=u\ast v
\]
が成り立ち、第一脚の左畳み込みと第二脚の右畳み込みもそれぞれの内部移動と可換です。このため、Gram 補正後も積は従来どおり \(T_{p,p}(I_ne)\)、固定端の交換子は同じ写像を群欠損 \(b\cdot m-m\cdot b\) に適用したものです。[群テンソルの積と欠損評価](06-diffuse-nonunimodular-product-diagonal.md)・[Stokke (2004), Theorem 1.8](https://www.impan.pl/shop/en/publication/transaction/download/product/90526#page=8)

両脚の Gram 補正のノルム上界の積を \(\Gamma\) とすると、対角の projective ノルムは \(\Gamma c^4\int |m(s,t)|\max(1,\rho(st))\,d\lambda_L^2\) 以下です。\(e\) の台で \(\rho\le c\) と取れば上界は \(\Gamma c^5\) です。交換子では \(st\) が有限テストの台 \(K\) と固定コンパクト単位近傍 \(U_0\) から作る \(KU_0\cup U_0K\) に入るため、同じ重みは有界です。外側質量を固定した後で群の Reiter 誤差を小さくでき、積は両 Haar ノルムで有限テストの近似単位になります。\(\Gamma\to1,\ c\downarrow1\) として上界で割れば contractive な近似対角が得られます。

有限基底との分岐は、(1) を満たす中間添字を**有限テストごとに必要な個数だけ**取れる点にあります。原子の質量比や減衰速度、各点の孤立性への追加仮定はありません。