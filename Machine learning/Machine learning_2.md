# 非線形回帰モデル

# 非線形回帰（理論）
複雑な非線形構造を内在する現象に対して、非線形回帰モデルを用いる.
## 基底展開法
線形回帰モデルを基底展開法に適用することで、非線型回帰を行う.※$\bm{w}$は線形であることに注意.(linear-in-parameter)  
$y_{i}$:目的変数、$w_{0}$:切片、$w$:パラメータ、$\phi(\bm{x_{i}}):基底関数、$$\epsilon_{i}$:誤差とした時、
$$
y_{i}=w_{0}+\sum^{m}_{j=1}w_{j}\phi_{j}(\bm{x_{i}})+\epsilon_{i}
$$

これを**基底展開法**という.
また、$\phi$を**基底関数**という.
## 基底展開法の求め方
以下のように線形回帰と同様の枠組みで推定が可能.
### 説明変数
$$
\bm{x_{i}}=(x_{i1},x_{i2},\cdots,x_{im})
$$

### 非線形関数ベクトル
$$
\bm{\phi}(\bm{x_{i}})=(\phi_{1}(\bm{x_{i}}),\phi_{2}(\bm{x_{i}}),\cdots,\phi_{k}(\bm{x_{i}}))^{T}\in \mathbb{R}^{k}
$$

### 非線形関数の計画行列
$$
\Phi^{(train)}=(\bm{\phi}(\bm{x_{1}}),\bm{\phi}(\bm{x_{2}}),\cdots,\bm{\phi}(\bm{x_{n}}))^{T}\in \mathbb{R}^{n\times k}
$$
### 最尤法による予測値
$$
\bm{\hat{y}}=\Phi(\Phi^{(train)T}\Phi^{(train)})^{-1}\Phi^{(train)T}\bm{{y}}^{(train)}
$$

### よく用いられる基底関数
* 多項式関数
$\phi_{j}=x^{j}$
* ガウス型基底関数
$\phi_{j}(x)=exp\{\frac{(x-\mu_{j})^{2}}{2h_{j}}\}$
* スプライン関数/ Bスプライン関数


## 未学習と過学習
### 未学習
学習データに対して、十分小さな誤差が得られないモデルの状態を**未学習**という.
* (対策)モデルの表現力が低いため、表現力の高いモデルを利用する
### 過学習
小さな誤差は得られたが、テスト集合誤差との差が大きいモデルの状態を**過学習**という.

* (対策1) 学習データの数を増やす

* (対策2) 不要な基底関数(変数)を削除して表現力を抑止(AICによるモデル選択等)

* (対策3) 正則化法を利用して表現力を抑止


## 正則化法(罰則化法)
正則化項(モデルの複雑さに伴って増加する)を用いて最小化することによってモデルの複雑さを軽減することが可能.
$$
\bm{\hat{y}}=\Phi(\Phi^{(train)T}\Phi^{(train)})^{-1}\Phi^{(train)T}\bm{{y}}^{(train)}
$$

## 汎化性能
学習に使用したデータではなく、未知のデータに対する予測性能を指す.
## モデルの検証
* ホールドアウト法
* クロスバリデーション(交差検証)

# 非線形回帰（実装）
### 1.Googleドライブのマウント
任意のgoogleアカウントでログインし、認証コードを入力して実行を行う.

![1](images_Machinelearning_2/1.png)

### 2.モジュールインポート
![2](images_Machinelearning_2/2.png)

### 3.ある関数からデータを作成
![3](images_Machinelearning_2/3.png)

### 4.線形回帰
![4](images_Machinelearning_2/4.png)
### 5.カーネル回帰にリッジ推定量を適用したモデル(scikit-learnのKernelRidge有り)
![5](images_Machinelearning_2/5.png)
### 6.カーネル回帰にリッジ推定量を適用したモデル(scikit-learnのKernelRidge無し)
![6](images_Machinelearning_2/6.png)
### 7.多項式を基底関数とした非線形回帰
![7](images_Machinelearning_2/7.png)
### 8.カーネル回帰にラッソ推定量を適用したモデル
![8](images_Machinelearning_2/8.png)
### 9.サポートベクターマシン
![9](images_Machinelearning_2/9.png)
### 10.kerasを用いた深層学習
![10](images_Machinelearning_2/10.png)
![11](images_Machinelearning_2/11.png)
![12](images_Machinelearning_2/12.png)