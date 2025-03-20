# 投影

## 中心投影

推导过程可能不严谨，大概帮助自己理解

首先考虑 $z=1$ 的平面。各个点向**原点**在 $z=0$ 平面上进行投影，我们好理解，对于点 $(x, y, 1)$ ，投影之后的点也是 $(x, y, 1)$ ，对于 $(x, y, 4)$ ，投影为 $(\frac{x}{4}, \frac{y}{4}, 1)$ ，即变成 $z$ 分量为1的状态，哎呀大概理解一下就行了。这其实是一个从三维空间向二维空间跌落的过程，同样的我们可以推广到四维空间向三维空间跌落的过程，实际上是将一个点从四维空间落到 $w=1$ 这个三维空间内（类似 $z=1$ 这个平面的二维空间）

现在还有另一个现象，在二维空间的剪裁变换上，原来的点，经过 $\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ -\frac{1}{5} & 0 & 1 \end{bmatrix}$ 这个变换后，向点 $(5, 0)$ 的投影是不变的，这说明，当我们选取合适的剪切变换矩阵时，可以直接得到相应的投影

在三维空间中，点 $P(x, y, z)$ 写成列向量形式： $\begin{bmatrix}x \\ y \\ z\end{bmatrix}$ ，添加齐次坐标升维到四维空间，即 $\begin{bmatrix}x \\ y \\ z \\ 1\end{bmatrix}$ ，现在对它进行如下剪裁变换：

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & r & 1 \\
\end{bmatrix}
\cdot
\begin{bmatrix}
x \\
y \\
z \\
1 \\
\end{bmatrix}
=
\begin{bmatrix}
x \\
y \\
z \\
rz+1 \\
\end{bmatrix}
$$

转回三维空间中，即 $\begin{bmatrix}\frac{x}{rz+1}\\\frac{y}{rz+1}\\\frac{z}{rz+1}\\\end{bmatrix}$

现在再看另一边，相机位于 $C(0,0,c)$ ，一个点 $P(x,y,z)$ ，它在 $z=0$ 平面上的投影为 $P'(x',y',z')$ ，另定义：点 $P$ 在 $y=0$ 平面的投影点为 $B(x,0,z)$ ，在$z$轴上的投影为 $A(0,0,z)$ ，点 $P'$ 在 $x$ 轴的投影为 $D(x',0,0)$ ，在 $y$ 轴上的投影为 $E(0,y',0)$

可以知道 $\triangle CAB\sim\triangle COD$ ，有 $\frac{c-z}{c}=\frac{x}{x'}\rightarrow x'=\frac{x}{1-\frac{z}{c}}$

再根据前述推导，可知 $\frac{x}{rz+1}=\frac{x}{1-\frac{z}{c}}\rightarrow r=-\frac{1}{c}$

那么当相机位于 $z$ 轴上的 $C(0,0,c)$ 上时，按如下推导即可得到中心投影到 $z=0$ 平面上的中心投影

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & -\frac{1}{c} & 1 \\
\end{bmatrix}
\cdot
\begin{bmatrix}
x \\
y \\
z \\
1 \\
\end{bmatrix}
$$

=
\begin{bmatrix}
x \\
y \\
z \\
1-\frac{z}{c} \\
\end{bmatrix}
\rightarrow
\begin{bmatrix}
\frac{x}{1-\frac{z}{c}} \\
\frac{y}{1-\frac{z}{c}} \\
\frac{z}{1-\frac{z}{c}} \\
\end{bmatrix}
$$

$$
I_4 = \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
$$