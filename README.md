# 次元削減
データの次元数(特徴量)を減らす。

次元削減の目的
- データの圧縮
- データの解釈
- データの可視化

## 手法
### PCA(Principal Component Analysis : 主成分分析)
射影したデータの分散が最大となるような軸を選ぶことで、データの次元数を減らす。
#### 計算方法
まず、 $p$ 次元の特徴を持つ$n$個のデータがあり、それが次のようなデータ行列 $X$ で表されている：

$$
X=\left(
\begin{matrix}
    x_{11} & \cdots  & x_{1p} \\
    \vdots & \ddots & \vdots \\
    x_{p1} & \cdots & x_{pp} 
\end{matrix}
\right)
$$

データ行列 $X$ を用いると、分散共分散行列 (variance-covariance matrix) $S$ が次のように求まる：

$$
S=\left(
\begin{matrix}
    s_{11} & \cdots  & s_{1p} \\
    \vdots & \ddots & \vdots \\
    s_{p1} & \cdots & s_{pp} 
\end{matrix}
\right)
$$

ただし：

$$
s_{jk} = \frac{1}{n}
$$

分散共分散行列 $S$ に対して、次の行列式を解くと固有値 $\lambda$ が求まる：

$$
\left|
\begin{matrix}
    s_{11}-\lambda & \cdots  & s_{1p} \\
    \vdots & \ddots & \vdots \\
    s_{p1} & \cdots & s_{pp}-\lambda 
\end{matrix}
\right|=0
$$

上記の行列式を解くと、 $p$ 個の固有値：

$$
\lambda_{1} \geq \cdots \geq \lambda_{p} \geq 0
$$

が得られる。数値の大きい固有値に対応する固有ベクトルから順に第1主成分、 $\cdots$ 、第 $p$ 主成分となる。

### SVD(Singular Value Decomposition : 特異値分解)
行列を3つの行列の積に分解し重要度の低い列ベクトルを削ることで、低次元の行列を得る。