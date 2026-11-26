# Glimm 空間への従順性の降下に対する反例

研究途中経過（work in progress）。論文・プレプリント・査読済み成果ではありません。以下は書面検算済みで、Lean 形式化や先行研究に対する新規性の確認は行っていません。

2026年11月26日。可分な CCR 環（従って type I）と \(\Gamma=F_2\) の作用で、\(Z(A^{**})\) に値を取る正規な共変平均が存在する一方、\(\operatorname{Glimm}(A)\) 上の作用には固定点があり、位相的に従順でない例を構成する。以下の平均とは、\(\ell^\infty(\Gamma,Z)\) から定数列 \(Z=Z(A^{**})\) 上への共変条件付き期待値である。

## 二点商が課す必要条件

一般に、中心値平均 \(P\) と \(Z\) 上の \(\Gamma\)-不変状態 \(\omega\) があれば、
\[
 u\ \longmapsto\ \omega\!\left(P((u(t)1_Z)_{t\in\Gamma})\right)
\]
は \(\ell^\infty(\Gamma)\) の左不変平均である。従って群自身が従順となる。共変な可換商 \(A\twoheadrightarrow C_0(S)\) の \(S\) が不変 Radon 確率をもてば、その積分状態を商写像で引き戻し、\(A^{**}\) に正規拡張して \(Z\) に制限すれば \(\omega\) を得る。特に、二点の文字が固定または交換される商 \(\mathbb C^2\) には一様確率がある。非従順群に対してこの二点だけを固定 Glimm 点の上に置く方法は、中心値平均の段階で失敗する。以下ではその上に無限の自由軌道を置く。

## スペクトルの計算

\(Y=\Gamma\sqcup\{\infty\}\) を離散集合 \(\Gamma\) の一点コンパクト化、\(H=\ell^2(\Gamma)\)、\(D=\{M_f:f\in c_0(\Gamma)\}\subset\mathcal K(H)\) を対角コンパクト作用素環とする。左正則表現を \(\lambda\)、\(g\infty=\infty\) として
\[
 A=\{a\in C(Y,\mathcal K(H)):a(\infty)\in D\},\qquad
 (\alpha_g a)(s)=\lambda_g a(g^{-1}s)\lambda_g^*
\]
と置く。\(\lambda_gM_f\lambda_g^*=M_{f\circ g^{-1}}\) なのでこの式は作用を定める。無限遠での評価から共変な分裂拡大
\[
 0\longrightarrow I=c_0(\Gamma,\mathcal K(H))
 \longrightarrow A\longrightarrow c_0(\Gamma)\longrightarrow0
\]
を得る。右逆は \(f\mapsto(s\mapsto M_f)\)。理想と商は可分である。商上の作用は左移動で、不変確率をもたない。

原始イデアルは \(\mathcal K(H)\) への座標評価の核 \(P_s\ (s\in\Gamma)\) と、\(a(\infty)=M_f\mapsto f(h)\) の核 \(Q_h\ (h\in\Gamma)\) で尽きる。既約表現が \(I\) 上で非零なら、その制限は \(I\) の一つの座標既約表現であり、非退化性で延長は一意である。\(I\) を消す既約表現は商の文字である。全ての像がコンパクト作用素環または \(\mathbb C\) なので \(A\) は CCR である。作用は \(P_s\mapsto P_{gs}\)、\(Q_h\mapsto Q_{gh}\) である。

同じネット \(s\to\infty\) に対して \(P_s\to Q_h\) が **全ての \(h\)** で成り立つ。実際、\(a\notin Q_h\) なら \(f(h)\ne0\) で、\(\|a(s)-M_f\|\to0\) から結局 \(a\notin P_s\) となる。これを hull–kernel 位相の基本近傍に用いる。異なる二つの \(Q_h\) を分離できず、\(\operatorname{Prim}(A)\) は非 Hausdorff である。従って有界連続スカラー関数は全 \(Q_h\) で同じ値を取り、\(P_s\) 上の値は無限遠でその値に収束する。逆に各 \(\{P_s\}\) は座標理想により開、商 \(\mathcal K(H)\) の単純性により閉である。よって \(P_s\mapsto s,\ Q_h\mapsto\infty\) は \(Y\) への連続写像で、\(C_b(\operatorname{Prim}A)\) はちょうど \(C(Y)\) の引き戻しである。これで \(\operatorname{Glimm}(A)=Y\) とその位相・作用が決まる。\(\infty\) は固定点だから、そこで Reiter 確率を評価すれば群の近似不変確率になる。\(F_2\) は非従順なので \(Y\) 上の作用は位相的に従順でない。

## 普遍二重双対の中心と検出される作用

不変理想 \(I\) の中心台で普遍二重双対を分けると
\[
 A^{**}=I^{**}\oplus(A/I)^{**}
 \cong\ell^\infty(\Gamma,\mathbb B(H))\oplus\ell^\infty(\Gamma),\qquad
 Z=\ell^\infty(\Gamma)\oplus\ell^\infty(\Gamma).
\]
中心では両成分とも左移動である。\(F\in\ell^\infty(\Gamma,Z)\) に対して
\[
 (P F)_j(s)=F(s)_j(s)\qquad(s\in\Gamma,\ j=1,2)
\]
とすれば、座標の制限による正規な単位的 \(*\)-準同型で、定数列を固定する。\((\beta_gF)(t)=\alpha_g(F(g^{-1}t))\) に対し \((P\beta_g F)_j(s)=F(g^{-1}s)_j(g^{-1}s)=(\alpha_g PF)_j(s)\)。従って \(P\) は求める共変平均である。

Dauns–Hofmann の中心 multiplier は \(Z(\mathcal M(A))=C(Y)\) である。\(Y\) は可算で全有限 Radon 測度が原子的なので、標準の正規写像は
\[
 C(Y)^{**}=\ell^\infty(\Gamma)\oplus\mathbb C\ \longrightarrow Z,\qquad
 (v,c)\longmapsto(v,c\,1_\Gamma).
\]
この真の包含には共変な条件付き期待値による引き戻しも存在しない。もしあれば無限遠での評価と合成して \(Z\) 上の不変状態が得られ、上の \(P\) と合わせると \(F_2\) の不変平均になってしまう。ここが continuous-trace の中心同定を Glimm 空間へ移す際に失われる点である。

逆の含意はコンパクトな Glimm 空間 \(Y_0\) では保たれる。作用が位相的に従順なら、有限台に近似・正規化したスカラー Reiter 重み \(w_{i,t}\in C(Y_0)_+\) を中心 multiplier として \(P_i(F)=\sum_t w_{i,t}F(t)\) に用いる。正の単位的写像 \(P_i\) は定数を固定し、共変誤差は \(\|F\|\sup_{y\in Y_0}\sum_t|w_{i,t}(y)-w_{i,g^{-1}t}(g^{-1}y)|\to0\) 以下である。点ごとの ultraweak 集積点が共変条件付き期待値を与える。
