# 情報理論
## 自己情報量・シャノンエントロピーの定義
### 自己情報量
自己情報量は以下のように定義する.

$$
I(x)=-\log(P(x))=\log(W(x))
$$

### シャノンエントロピー
シャノンエントロピーは以下のように定義する.(自己情報量の期待値)

$$
H(x)=\mathbb{E}(I(x))=-\mathbb{E}(\log(P(x))=-\Sigma(P(x)\log(P(x)))
$$

## KLダイバージェンス・交差エントロピー
### KLダイバージェンス
KLダイバージェンスは以下のように定義する.(確率分布PとQの違いを表す)

$$
D_{KL} (P||Q)=\mathbb{E}_{x \verb|~| P} \left(\frac{P(x)}{Q(x)}\right)
$$

### 交差エントロピー
交差エントロピーは以下のように定義する.

$$
\begin{equation*}
\begin{split}
H(P,Q)
&=H(P)+D_{KL} (P||Q)\\
&=-\mathbb{E}_{x \verb|~| P}\log Q(x)\\
&=-\Sigma_{x}P(x)\log Q(x)
\end{split}
\end{equation*}
$$