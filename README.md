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
まず、$p$次元の特徴を持つ$n$個のデータの行列$X$があるとする。
$$
X=\left(
\begin{matrix}
    x_{11} & \cdots  & x_{1p} \\
    \vdots & \ddots & \vdots \\
    x_{p1} & \cdots & x_{pp} 
\end{matrix}
\right)
$$
$$
S=\left(
\begin{matrix}
    s_{11} & \cdots  & s_{1p} \\
    \vdots & \ddots & \vdots \\
    s_{p1} & \cdots & s_{pp} 
\end{matrix}
\right)
$$

### SVD(Singular Value Decomposition : 特異値分解)
行列を3つの行列の積に分解し重要度の低い列ベクトルを削ることで、低次元の行列を得る。