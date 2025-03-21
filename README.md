# 

## 坐标变换

一个直角坐标系由三个基向量描述： $\vec{i}$ 、 $\vec{j}$ 、 $\vec{k}$ ，坐标系 $(O,\vec{i},\vec{j},\vec{k})$ 下的点 $P(x,y,z)$ 可以表示为

$$
\begin{aligned}
\vec{OP}&=x\cdot \vec{i}+y\cdot \vec{j}+z\cdot \vec{k} \\
        &=
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot
\begin{bmatrix}
x \\
y \\
z \\
\end{bmatrix}
\end{aligned}
$$

现在我们有两个坐标系，一个 $(O,\vec{i},\vec{j},\vec{k})$ 和 $(O',\vec{i'},\vec{j'},\vec{k'})$，点 $P$ 在两个坐标系下的坐标分别为 $P(x,y,z)$ 和 $P(x',y',z')$ ，点 $O'$ 在坐标系 $(O,\vec{i},\vec{j},\vec{k})$ 下的坐标为 $O'(O_x',O_y',O_z')$

首先我们可以知道（其实对我来说就是直觉），存在一个非奇异矩阵，使得

$$
\begin{bmatrix}
\vec{i'} & \vec{j'} & \vec{k'} \\
\end{bmatrix}=
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot M
$$

重新表达一下 $\vec{OP}$ ，即

$$
\begin{aligned}
\vec{OP}&=\vec{OO'}+\vec{O'P}\\
        &=
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot
\begin{bmatrix}
O_x' \\
O_y' \\
O_z' \\
\end{bmatrix}+
\begin{bmatrix}
\vec{i'} & \vec{j'} & \vec{k'} \\
\end{bmatrix}
\cdot
\begin{bmatrix}
x' \\
y' \\
z' \\
\end{bmatrix} \\
    &=
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot
\begin{bmatrix}
O_x' \\
O_y' \\
O_z' \\
\end{bmatrix}+
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot M \cdot
\begin{bmatrix}
x' \\
y' \\
z' \\
\end{bmatrix}
\end{aligned}
$$

展开可得

$$
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot
\begin{bmatrix}
x \\
y \\
z \\
\end{bmatrix}=
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot
\begin{bmatrix}
O_x' \\
O_y' \\
O_z' \\
\end{bmatrix}+
\begin{bmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\end{bmatrix}
\cdot M \cdot
\begin{bmatrix}
x' \\
y' \\
z' \\
\end{bmatrix}
$$

整理可得

$$
\begin{bmatrix}
x' \\
y' \\
z' \\
\end{bmatrix}=M^{-1}
\cdot
\left(
\begin{bmatrix}
x \\
y \\
z \\
\end{bmatrix}-
\begin{bmatrix}
O_x' \\
O_y' \\
O_z' \\
\end{bmatrix}
\right)
$$