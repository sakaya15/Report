# 線形代数
本レポートは,演習に焦点を当て,記述する.
## 固有値・固有ベクトル
ある$n$次の正方行列$A$に対して,
$$A\bm{x}=\lambda \bm{x}$$
を満たす$n$次元ベクトル$\bm{x}(\neq 0)$と実数$\lambda$が存在する時,
$\lambda$を$A$の**固有値**、$\bm{x}$を$\lambda$に対する**固有値ベクトル**という.
## 固有値・固有ベクトルの求め方
Ex.

$$
A=
\begin{pmatrix}
   3 & 2 & 0 \\
   0 & 2 & 0 \\
   0 & 0 & 1
\end{pmatrix}
$$
に対する固有値・固有ベクトルを求めよ.

$$
A\bm{x}=\lambda \bm{x}　\\
(A-\lambda E)\bm{x}=0　
$$

$\bm{x}\neq 0$より, 

$$
|A-\lambda E|=0 
$$

サラスの公式から,固有値$\lambda$は

$$
(3-\lambda)(2-\lambda)(1-\lambda)=0 \\
\lambda=3,2,1
$$

$$
\begin{pmatrix}
   3 & 2 & 0 \\
   0 & 2 & 0 \\
   0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
\begin{pmatrix}
   3x_{1}+2x_{2} \\
   2x_{2} \\
   x_{3} 
\end{pmatrix}
$$

$\lambda=3の時,$

$$
\begin{pmatrix}
   3x_{1}+2x_{2} \\
   2x_{2} \\
   x_{3} 
\end{pmatrix}
=
3
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
$$
よって,$x_{2}=0,x_{3}=0$

したがって,固有ベクトルは

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
t_{1}
\begin{pmatrix}
   1 \\
   0 \\
   0 
\end{pmatrix}
(t_{1}は0でない任意定数).
$$


$\lambda=2の時,$

$$
\begin{pmatrix}
   3x_{1}+2x_{2} \\
   2x_{2} \\
   x_{3} 
\end{pmatrix}
=
2
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
$$
よって,$x_{1}=-2x_{2},x_{3}=0$

したがって,固有ベクトルは

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
t_{2}
\begin{pmatrix}
   2 \\
  -1 \\
   0 
\end{pmatrix}
(t_{2}は0でない任意定数).
$$


$\lambda=1の時,$

$$
\begin{pmatrix}
   3x_{1}+2x_{2} \\
   2x_{2} \\
   x_{3} 
\end{pmatrix}
=
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
$$
よって,$x_{1}=0,x_{2}=0$

したがって,固有ベクトルは

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
t_{3}
\begin{pmatrix}
   0 \\
   0 \\
   1 
\end{pmatrix}
(t_{3}は0でない任意定数).
$$


## 固有値分解
ある$n$次の正方行列$A$に対して,$A$の固有値$\lambda$と固有ベクトル$v$から,


$A=V \Lambda V^{-1}$

のように変換することを**固有値分解**という.

## 固有値分解の求め方
Ex.

$$
A=
\begin{pmatrix}
   2 & 1 \\
   0 & 6 
\end{pmatrix}
$$
を固有値分解せよ.

$$
A\bm{x}=\lambda \bm{x}　\\
(A-\lambda E)\bm{x}=0　
$$

$\bm{x}\neq 0$より, 

$$
|A-\lambda E|=0 
$$
$$
\begin{vmatrix}
   2-\lambda & 1 \\
   0 & 6-\lambda 
\end{vmatrix}
=0
$$
固有値は,

$$
(2-\lambda)(6-\lambda)=0 \\
\lambda=2,6
$$
$$
\begin{pmatrix}
   2 & 1 \\
   0 & 6 
\end{pmatrix}
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
=
\begin{pmatrix}
   2x_{1}+x_{2} \\
   6x_{2} 
\end{pmatrix}
$$

$\lambda=2の時,$

$$
\begin{pmatrix}
   2x_{1}+x_{2} \\
   6x_{2} 
\end{pmatrix}
=
2
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
$$
よって$x_{2}=0$

固有ベクトルは,

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
=
t_{1}
\begin{pmatrix}
   1 \\
   0 
\end{pmatrix}
(t_{1}は0でない任意定数)
$$


$\lambda=6の時,$

$$
\begin{pmatrix}
   2x_{1}+x_{2} \\
   6x_{2} 
\end{pmatrix}
=
6
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
$$
よって$4x_{1}=x_{2}$

固有ベクトルは,

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
=
t_{2}
\begin{pmatrix}
   1 \\
   4 
\end{pmatrix}
(t_{2}は0でない任意定数)
$$

ここで,

$$
\begin{pmatrix}
   1 & 1 \\
   0 & 4 
\end{pmatrix}
^{-1}
$$
を求める.

$$
\begin{vmatrix}
1 & 1 \\
0 & 4 \\
\end{vmatrix}
\neq
0
$$
より,逆行列は存在する.

$$
\begin{pmatrix}
   1 & 1 \\
   0 & 4 
\end{pmatrix}
^{-1}
$$

$$
\rightarrow
\left(
\begin{array}{cc|cc}
   1 & 1 & 1 & 0 \\
   0 & 4 & 0 & 1
\end{array}
\right)
$$
2行目を-1/4かけて1行目に足す.

$$
\rightarrow
\left(
\begin{array}{cc|cc}
   1 & 0 & 1 & -1/4 \\
   0 & 4 & 0 & 1
\end{array}
\right)

$$
2行目を1/4かける.

$$
\rightarrow
\left(
\begin{array}{cc|cc}
   1 & 0 & 1 & -1/4 \\
   0 & 1 & 0 & 1/4
\end{array}
\right)
$$
よって逆行列は,

$$
\begin{pmatrix}
   1 & -1/4 \\
   0 & 1/4
\end{pmatrix}
$$
したがって,

$$
\begin{pmatrix}
   2 & 1 \\
   0 & 6 
\end{pmatrix}
=
\begin{pmatrix}
   1 & 1 \\
   0 & 4 
\end{pmatrix}
\begin{pmatrix}
   2 & 0 \\
   0 & 6 
\end{pmatrix}
\begin{pmatrix}
   1 & 1 \\
   0 & 4 
\end{pmatrix}
^{-1}
=
\begin{pmatrix}
   1 & 1 \\
   0 & 4 
\end{pmatrix}
\begin{pmatrix}
   2 & 0 \\
   0 & 6 
\end{pmatrix}
\begin{pmatrix}
   1 & -1/4 \\
   0 & 1/4
\end{pmatrix}
$$

## 特異値分解
正方行列ではない$m\times n$行列Mに対し,

$$
M\bm{v}=\sigma \bm{u} \\
M^{T}\bm{u}=\sigma \bm{v}
$$
上記の式が成り立つ特殊なベクトル$\bm{v}$,$\bm{u}$,係数$\sigma$をそれぞれ,**右特異ベクトル**,**左特異ベクトル**,**特異値**という.

この特異ベクトルが存在する場合,($m\times m$の直交行列U,$n\times n$の直交行列V,$m\times n$の対角成分に特異値をもちその他は0の行列Sとする)

$$
M=USV^{-1}=USV^{T} \ (直交行列より)
$$
上記のように分解することを**特異値分解**という.

## 特異値分解の求め方
Ex.

$$
M=
\begin{pmatrix}
   1 & 2 & 3 \\
   3 & 2 & 1
\end{pmatrix}
$$
を特異値分解せよ.

ここで,

$$
MM^{T}
=
\begin{pmatrix}
   1 & 2 & 3 \\
   3 & 2 & 1
\end{pmatrix}
\begin{pmatrix}
   1 & 3 \\
   2 & 2 \\
   3 & 1 
\end{pmatrix}
=
\begin{pmatrix}
   14 & 10 \\
   10 & 14 
\end{pmatrix}
$$

固有値分解を行うと,

$$
MM^{T}\bm{x}=\lambda \bm{x}　\\
(MM^{T}-\lambda E)\bm{x}=0　
$$

$\bm{x}\neq 0$より, 

$$
|MM^{T}-\lambda E|=0 
$$
$$
\begin{vmatrix}
   14-\lambda & 10 \\
   10 & 14-\lambda 
\end{vmatrix}
=0
$$
固有値は,

$$
(\lambda-24)(\lambda-4)=0 \\
\lambda=24,4
$$
$$
\begin{pmatrix}
   14 & 10 \\
   10 & 14 
\end{pmatrix}
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
=
\begin{pmatrix}
   14x_{1}+10x_{2} \\
   10x_{1}+14x_{2} 
\end{pmatrix}
$$

$\lambda=24$の時,

$$
\begin{pmatrix}
   14x_{1}+10x_{2} \\
   10x_{1}+14x_{2} 
\end{pmatrix}
=
24
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
$$
よって,$x_{1}=x_{2}$

固有ベクトルは,

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
=
t_{1}
\frac{1}{\sqrt{2}}
\begin{pmatrix}
   1 \\
   1 
\end{pmatrix}
(t_{1}は0でない任意定数)
$$


$\lambda=4$の時,

$$
\begin{pmatrix}
   14x_{1}+10x_{2} \\
   10x_{1}+14x_{2} 
\end{pmatrix}
=
4
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
$$
よって,$x_{1}=-x_{2}$

固有ベクトルは,

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} 
\end{pmatrix}
=
t_{2}
\frac{1}{\sqrt{2}}
\begin{pmatrix}
   1 \\
   -1 
\end{pmatrix}
(t_{2}は0でない任意定数)
$$
したがって,固有値分解すると

$$
\begin{pmatrix}
   14 & 10 \\
   10 & 14 
\end{pmatrix}
=
\begin{pmatrix}
   1/\sqrt{2} & 1/\sqrt{2}  \\
   1/\sqrt{2}  & -1 /\sqrt{2} 
\end{pmatrix}
\begin{pmatrix}
   24 & 0 \\
   0 & 4 
\end{pmatrix}
\begin{pmatrix}
   1/\sqrt{2}  & 1/\sqrt{2}  \\
   1/\sqrt{2}  & -1/\sqrt{2}  
\end{pmatrix}
^{-1}
$$
と表せる.

続いて,

$$
MM^{T}
=
\begin{pmatrix}
   1 & 3 \\
   2 & 2 \\
   3 & 1 
\end{pmatrix}
\begin{pmatrix}
   1 & 2 & 3 \\
   3 & 2 & 1
\end{pmatrix}
=
\begin{pmatrix}
   10 & 8 & 6 \\
    8 & 8 & 8 \\
    6 & 8 & 10 
\end{pmatrix}
$$
固有値分解すると,

$$
|MM^{T}-\lambda E|=0 
$$
$$
\begin{vmatrix}
   10-\lambda & 8 & 6 \\ 
   8 & 8-\lambda & 8 \\
   6  & 8 & 10-\lambda
\end{vmatrix}
=0
$$
サラスの公式から,

$$
\begin{equation*}
\begin{split}
(10-\lambda)(8-\lambda)(10-\lambda)+164\lambda-800 
&=-\lambda^{3}+28\lambda^{2}-96\lambda \\
&=-\lambda(\lambda-24)(\lambda-4) 
\end{split}
\end{equation*}
$$

よって固有値は,

$$
\lambda=24,4,0
$$

$$
\begin{pmatrix}
   10 & 8 & 6 \\
    8 & 8 & 8 \\
    6 & 8 & 10 
\end{pmatrix}
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
\begin{pmatrix}
   10x_{1}+8x_{2}+6x_{3} \\
    8x_{1}+8x_{2}+8x_{3} \\
    6x_{1}+8x_{2}+10x_{3}
\end{pmatrix}
$$

$\lambda=24$の時,

$$
\begin{pmatrix}
   10x_{1}+8x_{2}+6x_{3} \\
    8x_{1}+8x_{2}+8x_{3} \\
    6x_{1}+8x_{2}+10x_{3}
\end{pmatrix}
=
24
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
$$
よって,$x_{1}=x_{2}=x_{3}$

固有値ベクトルは,

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
s_{1}
\frac{1}{\sqrt{3}}
\begin{pmatrix}
   1 \\
   1 \\
   1 
\end{pmatrix}
(s_{1}は0でない任意定数).
$$

$\lambda=4$の時,

$$
\begin{pmatrix}
   10x_{1}+8x_{2}+6x_{3} \\
    8x_{1}+8x_{2}+8x_{3} \\
    6x_{1}+8x_{2}+10x_{3}
\end{pmatrix}
=
4
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
$$
よって,$x_{1}=-x_{3},x_{2}=0$

固有値ベクトルは,

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
s_{2}
\frac{1}{\sqrt{2}}
\begin{pmatrix}
   1 \\
   0 \\
   -1 
\end{pmatrix}
(s_{2}は0でない任意定数).
$$

$\lambda=0$の時,

$$
\begin{pmatrix}
   10x_{1}+8x_{2}+6x_{3} \\
    8x_{1}+8x_{2}+8x_{3} \\
    6x_{1}+8x_{2}+10x_{3}
\end{pmatrix}
=
0
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
$$
よって,$x_{1}=x_{3}=(-1/2)x_{2}$

固有値ベクトルは,

$$
\begin{pmatrix}
   x_{1} \\
   x_{2} \\
   x_{3} 
\end{pmatrix}
=
s_{3}
\frac{1}{\sqrt{6}}
\begin{pmatrix}
   1 \\
   -2 \\
   1 
\end{pmatrix}
(s_{3}は0でない任意定数).
$$

したがって,固有値分解すると,

$$
\begin{pmatrix}
   10 & 8 & 6 \\
    8 & 8 & 8 \\
    6 & 8 & 10 
\end{pmatrix}
=
\begin{pmatrix}
    1/\sqrt{3}  & 1\sqrt{2} & 1\sqrt{6} \\
    1/\sqrt{3}  & 0 & -2\sqrt{6} \\
    1/\sqrt{3}  & -1\sqrt{2} & 1\sqrt{6} 
\end{pmatrix}
\begin{pmatrix}
    24 & 0 & 0 \\
    0 & 4 & 0 \\
    0 & 0 & 0 
\end{pmatrix}
\begin{pmatrix}
    1/\sqrt{3}  & 1\sqrt{2} & 1\sqrt{6} \\
    1/\sqrt{3}  & 0 & -2\sqrt{6} \\
    1/\sqrt{3}  & -1\sqrt{2} & 1\sqrt{6} 
\end{pmatrix}
^{-1}
$$

よってMを特異値分解すると,

$$
M=
\begin{pmatrix}
   1 & 2 & 3 \\
   3 & 2 & 1
\end{pmatrix}
=
\begin{pmatrix}
   1/\sqrt{2}  & 1/\sqrt{2}  \\
   1/\sqrt{2}  & -1/\sqrt{2}  
\end{pmatrix}
\begin{pmatrix}
   2\sqrt{6} & 0 & 0 \\
   0 & 2 & 0
\end{pmatrix}
\begin{pmatrix}
    1/\sqrt{3} & 1/\sqrt{3} & 1/\sqrt{3} \\
    1\sqrt{2} & 0 & -1\sqrt{2} \\
    1\sqrt{6}  & -2\sqrt{6}  & 1\sqrt{6}  
\end{pmatrix}
$$