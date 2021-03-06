# サポートベクターマシーン
教師あり学習の分類における数理モデル.
# サポートベクターマシーン（理論）
## 2クラス分類
入力データ$\bm{x}$対してラベルy(1or-1)を出力する分類方法.

### 決定関数
一般的に2クラス分類において、特徴ベクトル$\bm{x}$がどちらのクラスに属するか判定するために用いられる関数$f(\bm{x})$を決定関数といい、よく用いられる.$\bm{w}$はパラメータ、$b$はバイアス.※今回は線形の場合を考える
$$
f(\bm{x})=\bm{w}^{T}\bm{x}+b
$$

$$
\begin{equation*}
y=
sgnf(\bm{x})
=

\begin{cases}
1　& \text{($f(\bm{x})>0)$} \\
-1  & \text{($f(\bm{x})<0)$} 

\end{cases}
\end{equation*}
$$

### 分類境界
特徴ベクトルを分ける境界線を分類境界という.

## 線形サポートベクトル分類(ハードマージン→分類可能)
特徴ベクトルとラベルのセットを訓練データと呼ぶ.
$$
(\bm{x}_{i},y_{i}) \ (i=1,2,\cdots,n)
$$

分離可能な場合
$$
y_{i}f(\bm{x}_{i})>0(i=1,2,\cdots,n)
$$

※分離不可能な場合
$$
y_{i}f(\bm{x}_{i})<0(i=1,2,\cdots,n)
$$

$$
f(\bm{x}_{i})=0(i=1,2,\cdots,n)
$$
を考える.

分類境界を挟んで2つのクラスがどれくらい離れているかをマージンと呼ぶ.
SVMはマージンが大きいものが良い分類境界となる.この考え方をマージン最大化と呼ぶ.分類境界$f(x)=0$と最も近くにあるデータ$x_{i}$の距離は、以下のように示せる.
$$
\frac{|f(\bm{x_{i}})|}{||\bm{w}||}=\frac{y_{i}[\bm{w}^{T}\bm{x}_{i}+b]}{||\bm{w}||}
$$
ただし、
$$
||\bm{w}||=\sqrt{w^{2}_{1}+w^{2}_{2}+\cdots w^{2}_{n}}
$$
絶対値の定義から、
$$
\begin{equation*}
|\bm{w}^{T}\bm{x}_{i}+b|
=
\begin{cases}
\bm{w}^{T}\bm{x}_{i}+b　& \text{($\bm{w}^{T}\bm{x}_{i}+b\geq0)$} \\
-[\bm{w}^{T}\bm{x}_{i}+b]  & \text{($\bm{w}^{T}\bm{x}_{i}+b<0)$} 

\end{cases}
\end{equation*}
$$
訓練データのラベル$y_{i}とf(\bm{x})$の符号が全てのデータに対して一致している.
つまり、分類境界$f(\bm{x})=0$と分類境界から最も近くにあるデータ$x_{i}$との距離は次のように表現できる.
$$
\underset{i}{min}\frac{y_{i}[\bm{w}^{T}\bm{x}_{i}+b]}{||\bm{w}||}=\frac{M(\bm{w},b)}{||\bm{w}||}
$$
マージンを最大化することは、これを最大化することと等価だから、以下を求めれば良い.
$$
\underset{\bm{w},b}{max}[\underset{i}{min}\frac{y_{i}[\bm{w}^{T}\bm{x}_{i}+b]}{||\bm{w}||}]=\underset{w,b}{max}\frac{M(\bm{w},b)}{||\bm{w}||}
$$

ここで、上式の要素を整理すると、

$$
\underset{i}{min} [y_{i}[\bm{w}^{T}\bm{x}_{i}+b]]=M(\bm{w},b)
\Leftrightarrow
全てのiに対して
[y_{i}[\bm{w}^{T}\bm{x}_{i}+b] \geq M(\bm{w},b)(制約条件)
$$

$$
\underset{w,b}{max}\frac{M(\bm{w},b)}{||\bm{w}||}
$$
ここで、以下のように置く.
$$
\~{\bm{w}}=\frac{\bm{w}}{M(\bm{w},b)},\~{b}=\frac{b}{M(\bm{w},b)}
$$

要素を以下のように簡潔に示すことができる.

$$
\underset{i}{min} [y_{i}[\~{\bm{w}}^{T}\bm{x}_{i}+\~{b}]]=1
\Leftrightarrow
全てのiに対して
[y_{i}[\~{\bm{w}}^{T}\bm{x}_{i}+\~{b}] \geq 1
$$

$$
\underset{\~{w},\~{b}}{max}\frac{1}{||\~{\bm{w}}||}
$$


さらに、$\frac{1}{||\~{\bm{w}}||}$の最大化が$||\~{\bm{w}}||$の最小化と等価であること、そして$\frac{1}{2}||\~{\bm{w}}||^{2}$の最小化とも等価であることから以下のように変形できる.

$$
\underset{\bm{w},b}{min}\frac{1}{2}||\bm{w}||^{2},ただし,全てのiに対してy_{i}[\bm{w}^{T}\bm{x}_{i}+b]\geq 1
$$
※1/2は後の計算を簡潔にする為.

分類境界に最も近いデータ$x_{i}$が分類境界を支えていると解釈できるため$x_{i}$をサポートベクトルと呼ぶ.
## 線形サポートベクトル分類(ソフトマージン→分類不可能)
ソフトマージンは、分類不可能なデータに対応出来る様に拡張していく.上記の制約条件に対し、$\xi_{i}=\geq 0(i=1,\cdots,n)$という非負の変数（スラック変数）を導入し、緩和する.

$$
u_{i}[\bm{w}^{T}\bm{x_{i}+b}]\geq1-\xi_{i} (i=1,\cdots,n)
$$

ソフトマージンは、$f(x)=1$と$f(x)=-1$の間の距離をマージンと解釈し、このマージンを最大化しつつ、分類の誤差である$\xi_{i}$を最小化するように分類境界を決定する.この最適化は以下の様に示される.

$$
\underset{\bm{w},b,\bm{\xi}}{min}[\frac{1}{2}||\bm{w}||^{2}+C\sum_{i=1}^{n}\xi_{i}],ただしy_{i}[\bm{w}^{T}\bm{x_{i}}+b]\geq1-\xi_{i},\xi_{i}\geq0(i=1,\cdots,n)
$$
ただし、$\bm{\xi}=(\xi_{1},\cdots,\xi_{n})^{T}$

係数$C$は正則化係数と呼ばれる正の定数で、学習前に値を与えておく必要があるハイパーパラメータ.$C$の値の決定には,交差検証法等が用いられる.
## SVMにおける双対表現
ハードマージンの場合とソフトマージンの場合を見てきた.これの最適化を主問題という.しかし、この主問題と等価な双対問題が主に以下のメリットがあり用いられている.

* 主問題と比べて、双対問題の方が変数を少なくできる.
* 分類境界の非線形化を考える上で、双対問題の形式(双対形式)の方が有利となる.

### ラグランジュ関数
ラグランジュ関数は以下の様に示される.
$$
L(\bm{w},b,\bm{\xi},\bm{\alpha},\bm{\mu})=\frac{1}{2}||\bm{w}||^{2}+C\sum_{i=1}^{n}\xi_{i}-\sum_{i=1}^{n}\alpha_{i}[y_{i}[\bm{w}^{T}\bm{x_{i}+b}]-1+\xi_{i}]-\sum_{i=1}^{n}\mu_{i}\xi_{i}
$$
### 双対問題
双対問題は以下の最適化を指す.
$$
\underset{\bm{\alpha},\bm{\mu}}{max}\underset{\bm{w},b,\bm{\xi}}{min}L(\bm{w},b,\bm{\xi},\bm{\alpha},\bm{\mu})
$$
ただし、$\alpha_{i}\geq0,\mu_{i}\geq0(i=1,\cdots,n)$とし、$\bm{\alpha}=(\alpha_{1},\cdots,\alpha_{n})^{T},\bm{\mu}=(\mu_{1},\cdots,\mu_{n})^{T}$をそれぞれ相対変数という.


## カーネルを用いた非線形分離への拡張
線形分離が上手くいかない際に、より高次元に写像する必要が出てくる.しかし、そのままでは計算量が膨大になってしまう.直接計算することなく、カーネル関数を用いて高次元ベクトルの内積を見積もる方法をカーネルトリックという.

# サポートベクターマシーン（実装）


モジュールインポート

![1](images_Machinelearning_6/1.png)

## 線形分離可能の場合
### データ生成
![1](images_Machinelearning_6/2.png)
### データ可視化
![1](images_Machinelearning_6/3.png)
### SVM学習
![1](images_Machinelearning_6/4.png)
### SVM予測

#### 変数指定
![1](images_Machinelearning_6/5.png)
#### 予測
![1](images_Machinelearning_6/6.png)
#### 予測結果可視化
![1](images_Machinelearning_6/7.png)
## 線形分離不可能の場合
### データ生成
![1](images_Machinelearning_6/8.png)
### データ可視化
![1](images_Machinelearning_6/9.png)

### カーネルを用いた学習
![1](images_Machinelearning_6/10.png)

### 予測

#### 変数指定
![1](images_Machinelearning_6/11.png)

#### 予測

![1](images_Machinelearning_6/12.png)
#### 予測結果可視化
![1](images_Machinelearning_6/13.png)
## ソフトマージンSVM
### 重なり合いデータ生成
![1](images_Machinelearning_6/14.png)
### データ可視化
![1](images_Machinelearning_6/15.png)
### 学習
![1](images_Machinelearning_6/16.png)
### 予測
#### 変数指定
![1](images_Machinelearning_6/17.png)
#### 予測
![1](images_Machinelearning_6/18.png)
#### 予測結果可視化
![1](images_Machinelearning_6/19.png)
