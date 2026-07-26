# 尚硅谷大模型技术之数学基础 V1.2.1

## 第 1 章 高等数学

### 1.1 导数

#### 1.1.1 导数的概念

导数（derivative）是微积分中的一个概念。函数在某一点的导数是指这个函数在这一点附近的变化率（即函数在这一点的切线斜率）。导数的本质是通过极限的概念对函数进行局部的线性逼近。

当函数$f$的自变量在一点$x_0$上产生一个增量$h$时，函数输出值的增量$\Delta y$与自变量增量$\Delta x$的比值在$\Delta x \to 0$
时的极限如果存在，即为$f$在$x_0$处的导数，记作$f' (x_0)$、$\frac{df}{dx} (x_0)$或$\left.\frac{df}{dx}\right|_{x=x_0}$。
$$
f' (x_0)=\lim_{\Delta x \to 0}\frac{f (x_0+\Delta x)-f (x_0)}{\Delta x}
$$

例如在运动学中，物体的位移对于时间的导数就是物体的瞬时速度：$v=\frac{dx}{dt}$。

#### 1.1.2 基本函数的导数

| 说明           | 公式                                      | 例子                          |
|----------------|-------------------------------------------|-------------------------------|
| 常数的导数     | $(C)'=0$                                  | $(3)'=0$                      |
| 幂函数的导数   | $(x^\alpha)'=\alpha x^{\alpha-1}$         | $(x^3)'=3x^2$                 |
| 指数函数的导数 | $(a^x)'=a^x\ln a$                         | $(3^x)'=3^x\ln3$              |
|                | $(e^x)'=e^x$                              | —                             |
| 对数函数的导数 | $(\log_a x)'=\frac{1}{x\ln a}$            | $(\log_3 x)'=\frac{1}{x\ln3}$ |
|                | $(\ln x)'=\frac{1}{x}$                    | —                             |
| 三角函数的导数 | $(\sin x)'=\cos x$                        | —                             |
|                | $(\cos x)'=-\sin x$                       | —                             |
|                | $(\tan x)'=\sec^2 x=\frac{1}{\cos^2 x}$   | —                             |
|                | $(\cot x)'=-\csc^2 x=\frac{-1}{\sin^2 x}$ | —                             |

#### 1.1.3 导数的求导法则

| 说明           | 公式                                            |
|----------------|-------------------------------------------------|
| 两函数之和求导 | $(f+g)'=f'+g'$                                  |
| 两函数之积求导 | $(fg)'=f'g+fg'$                                 |
| 两函数之商求导 | $\left(\frac{f}{g}\right)'=\frac{f'g-fg'}{g^2}$ |
| 复合函数的导数 | 若$f(x)=h[g(x)]$，则$f'(x)=h'[g(x)]·g'(x)$      |

示例：求函数 $f (x)=x^4+\sin (x^2)-\ln (x)e^x+7$ 在 $x=3$ 处的导数。
$$
\begin{align*} f' (x)&=4x^{3}+\cos (x^2)·2x-\left (\frac{e^x}{x}+\ln (x)e^x\right)+0 \\ &=4x^3+2x\cos (x^2)-\frac{e^x}{x}-\ln (x)e^x \\ f' (3)&=108+6\cos (9)-\frac{e^3}{3}-\ln (3)e^3 \end{align*}
$$

#### 1.1.4 利用导数求极值

导数等于零的点称为函数的驻点（或极值可疑点），在这类点上函数可能会取得极大值或极小值。进一步判断则需要知道导数在附近的符号。

例如，$f (x)=x^3$ 在 $x=0$ 处导数为0，但并不会取得极大值或者极小值。

#### 1.1.5 二阶导数

##### 1）二阶导数的概念

在微积分中，函数的二阶导数是函数导数的导数。粗略来说，某个量的二阶导数描述该量变化率变化的快慢。例如物体位置对时间的二阶导数是物体的瞬时加速度，即该物体速度随时间的变化率：$a=\frac{dv}{dt}=\frac{d^2x}{dt^2}$。

函数$f$的二阶导数通常记作$f''$、$\frac{d^2y}{dx^2}$或$\frac{d}{dx}\left (\frac{dy}{dx}\right)$。

##### 2）二阶导数与函数凹凸的关系

函数的二阶导数描述了函数图像的凹凸方向和程度。

- 若二阶导数在某区间恒为正，则函数在该区间向上弯（也称下凸函数）。
- 若二阶导数在某区间恒为负，则函数在该区间向下弯（也称上凸函数）。

若函数的二阶导数在某点左右异号，则图像由向上弯转为向下弯，或反之。这种点称之为拐点。若二阶导数连续，则在该点处二阶导数为0。但反之二阶导数为0的点不一定是拐点。如$f (x)=x^4$
，在$x=0$处有$f''(0)=0$，但$f (x)$在实数系上无拐点。

驻点极值判定规则：

1. 若$f' (x)=0$，$f''(x)<0$，则$f$在$x$取得极大值。
2. 若$f' (x)=0$，$f''(x)>0$，则$f$在$x$取得极小值。
3. 若$f' (x)=0$，$f''(x)=0$，则该点可能是拐点，也可能是极大值点或极小值点。

### 1.2 偏导与梯度

#### 1.2.1 偏导数

多元函数示例：$f (x,y)=x^2+xy+y^2$

可将其中一个元素$x$看作常数，此时$f$可看作关于另一元素$y$的函数。
$f_x (y)=x^2+xy+y^2$
在$x=a$固定的情况下，可计算$f_x$关于$y$的导数：
$f_{x=a}' (y)=a+2y$

这种导数称为偏导数，一般记作：
$$
\frac{\partial f}{\partial y} (x,y)=x+2y
$$

更一般地来说，一个多元函数$f (x_1,x_2,…,x_n)$在点$(a_1,a_2,…,a_n)$处对$x_i$的偏导数定义为：
$$
\frac{\partial f}{\partial x_i} (a_1,a_2,…,a_n)=\lim_{\Delta x_i \to 0}\frac{f (a_1,…,a_i+\Delta x_i,…,a_n)-f (a_1,…,a_i,…,a_n)}{\Delta x_i}
$$

#### 1.2.2 方向导数

偏导数可以看作是多元函数$f$沿某个自变量轴方向的变化率。

如果我们任意选取一个方向$l$，那么在某个点$(x_0,y_0)$处，二元函数$f (x,y)$沿着这个方向的变化率可以用极限定义为：
$$
\frac{\partial f}{\partial l} (x_0,y_0)=\lim_{\Delta l \to 0}\frac{f (x_0+\Delta x,y_0+\Delta y)-f (x_0,y_0)}{\Delta l}
$$

这里，$\Delta l$ 就是沿方向$l$的微小改变量，$\Delta x= \Delta l·\cos\alpha$，$\Delta y= \Delta l·\cos\beta$。

根据全微分公式，上式可以表示为：
$$
\frac{\partial f}{\partial l} (x_0,y_0)=f_x (x_0,y_0)\cos\alpha+f_y (x_0,y_0)\cos\beta
$$
其中$f_x (x_0,y_0)$、$f_y (x_0,y_0)$ 表示点$(x_0,y_0)$处$f$对$x$、$y$的偏导数；$\cos\alpha$、$\cos\beta$是方向$l$
的方向余弦，即$l$方向的单位方向向量可以表示为$l_0= (\cos\alpha,\cos\beta)$。

这个“沿某个方向的变化率”，就被称为$f (x,y)$沿方向$l$的方向导数。

#### 1.2.3 梯度

多元函数$f (x_1,…,x_n)$关于每个变量$x_i$都有偏导数$\frac{\partial f}{\partial x_i}$，在点$a= (a_1,a_2,…,a_n)$
处，这些偏导数定义出一个向量：
$$
\nabla f (a)=\left[\frac{\partial f}{\partial x_1} (a),\frac{\partial f}{\partial x_2} (a),…,\frac{\partial f}{\partial x_n} (a)\right]
$$
这个向量称为$f$在点$a$的梯度，记作 $\nabla f (a)$ 或者$\mathrm{grad}\ f (a)$。

示例：$f (x,y)=x^2+xy+y^2$在$(1,1)$处的梯度为$[3,3]$。

梯度向量表示的方向，就是函数在这一点处，方向导数取最大值的方向。换句话说，梯度的方向，就是函数值变化最快的方向。

# 第 2 章 线性代数

## 2.1 标量与向量

### 2.1.1 标量与向量的概念

1）标量（scalar） 标量是一个单独的数，只有大小。

2）向量（vector） 向量由标量组成，有大小有方向。 行向量：$\begin{pmatrix}2&5&8\end{pmatrix}$
列向量：$\begin{pmatrix}2\\5\\8\end{pmatrix}$

### 2.1.2 向量运算

1）向量转置：列向量转置结果为行向量
$$
x=\begin{pmatrix}2\\5\\8\end{pmatrix},\quad x^T=\begin{pmatrix}2&5&8\end{pmatrix}
$$

2）向量相加：对应元素相加
$$
\begin{pmatrix}2\\5\\8\end{pmatrix}+\begin{pmatrix}1\\3\\7\end{pmatrix}=\begin{pmatrix}3\\8\\15\end{pmatrix}
$$

3）向量与标量相乘：标量与向量每个元素相乘
$$
3×\begin{pmatrix}2\\5\\8\end{pmatrix}=\begin{pmatrix}6\\15\\24\end{pmatrix}
$$

4）向量内积：又称向量点乘，两向量对应元素乘积之和，结果为标量
$$
\langle x,y \rangle = \left\langle \begin{pmatrix}2\\5\\8\end{pmatrix},\begin{pmatrix}1\\3\\7\end{pmatrix} \right\rangle=2+15+56=73
$$

两向量之间夹角表示为
$$
\cos\theta=\frac{\langle x,y \rangle}{\sqrt{\langle x,x \rangle}}
$$

### 2.1.3 向量范数

范数（norm）是具有“长度”概念的函数。 1）L0范数（也称0范数）
$\|x\|_0=$非零元素的个数 例：$x=\begin{pmatrix}0\\2\\-1\end{pmatrix},\ \|x\|_0=2$

2）L1范数（也称和范数或1范数）
$$
\|x\|_1=\sum_{i=1}^m |x_i|=|x_1|+…+|x_m|
$$
例：$x=\begin{pmatrix}0\\2\\-1\end{pmatrix},\ \|x\|_1=0+2+1=3$

3）L2范数（也称欧几里得范数或2范数）
$$
\|x\|_2=\left (\sum_{i=1}^m |x_i|^2\right)^{\frac{1}{2}}=\sqrt{|x_1|^2+…+|x_m|^2}
$$
例：$x=\begin{pmatrix}0\\2\\-1\end{pmatrix},\ \|x\|_2=\sqrt{0+4+1}=\sqrt{5}$

4）Lp范数
$$
\|x\|_p=\left (\sum_{i=1}^m |x_i|^p\right)^{\frac{1}{p}}=\left (|x_1|^p+…+|x_m|^p\right)^{\frac{1}{p}}
$$

在numpy中，可以利用linalg.norm 函数方便地计算向量的范数。

## 2.2 矩阵与张量

### 2.2.1 矩阵的概念

一个$m×n$的矩阵（matrix）是一个有m行n列元素的矩形阵列。用$\mathbb{R}^{m×n}$表示所有$m×n$实数矩阵的向量空间。
$$
\begin{bmatrix}1&2\\3&5\\4&8\end{bmatrix} \in \mathbb{R}^{3×2}
$$

1）方阵：行数等于列数的矩阵
$$
\begin{bmatrix}1&2\\3&4\end{bmatrix} \in \mathbb{R}^{2×2}
$$

2）对角矩阵：主对角线以外元素全为0的方阵
$$
\begin{bmatrix}1&0&0\\0&5&0\\0&0&9\end{bmatrix}
$$

3）单位矩阵：主对角线元素全为1的对角矩阵
$$
I_{3×3}=\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}
$$

### 2.2.2 矩阵乘法

1）矩阵乘法运算 两个矩阵的乘法仅当矩阵$A$的列数和矩阵$B$的行数相等时才能定义。如$A∈\mathbb{R}^{m×n}$，$B∈\mathbb{R}^{n×p}$
，它们的乘积$AB∈\mathbb{R}^{m×p}$
$$
[AB]_{ij}=a_{i1}b_{1j}+a_{i2}b_{2j}+…+a_{in}b_{nj}=\sum_{r=1}^n a_{ir}b_{rj}
$$

示例：
$$
\begin{bmatrix}1&0&2\\-1&3&1\end{bmatrix}×\begin{bmatrix}3&1\\2&1\\1&0\end{bmatrix}=\begin{bmatrix}1×3+0×2+2×1&1×1+0×1+2×0\\ (-1)×3+3×2+1×1& (-1)×1+3×1+1×0\end{bmatrix}=\begin{bmatrix}5&1\\4&2\end{bmatrix}
$$

特别地，矩阵与单位矩阵相乘等于矩阵本身：
$AI=A\ (A∈\mathbb{R}^{m×n},\ I∈\mathbb{R}^{n×n})$ 或 $IA=A\ (I∈\mathbb{R}^{n×n},A∈\mathbb{R}^{n×m})$

2）矩阵乘法的性质 矩阵乘法满足结合律、左分配律和右分配律。不满足交换律即$AB≠BA$。

- 结合律：$(AB)C=A (BC)$
- 左分配律：$(A+B)C=AC+BC$
- 右分配律：$A (B+C)=AB+AC$

### 2.2.3 矩阵转置

1）矩阵转置运算 矩阵$A∈\mathbb{R}^{m×n}$的转置是一个$n×m$的矩阵，记为$A^T$。其中$[A^T]_{ij}=a_{ji}$
$$
A=\begin{bmatrix}1&2\\3&5\\4&8\end{bmatrix}∈\mathbb{R}^{3×2},\quad A^T=\begin{bmatrix}1&3&4\\2&5&8\end{bmatrix}∈\mathbb{R}^{2×3}
$$

2）矩阵转置的性质

- $(A^T)^T=A$
- $(A+B)^T=A^T+B^T$
- $(kA)^T=kA^T$
- $(AB)^T=B^TA^T$

### 2.2.4 矩阵的逆

对于方阵$A$，如果存在另一个方阵$A^{-1}$，使得$AA^{-1}=I$成立，此时$A^{-1}A=I$也同样成立。称$A^{-1}$为$A$的逆矩阵。
$$
\begin{bmatrix}1&2\\3&5\end{bmatrix}×\begin{bmatrix}-5&2\\3&-1\end{bmatrix}=\begin{bmatrix}1× (-5)+2×3&1×2+2× (-1)\\3× (-5)+3×5&3×2+5× (-1)\end{bmatrix}=\begin{bmatrix}1&0\\0&1\end{bmatrix}=I
$$

### 2.2.5 其他矩阵运算

1）矩阵的向量化
$\mathrm{vec} (A)$：将矩阵$A$按列排列成$mn×1$列向量；
$\mathrm{rvec} (A)$：将矩阵$A$按行排列成$1×mn$行向量。

例：
$$
A=\begin{bmatrix}1&2\\3&4\end{bmatrix},\quad \mathrm{vec} (A)=\begin{pmatrix}1\\3\\2\\4\end{pmatrix},\quad \mathrm{rvec} (A)=\begin{pmatrix}1&2&3&4\end{pmatrix}
$$

2）矩阵的内积
$A,B∈\mathbb{R}^{m×n}$，$\langle A,B \rangle=\langle \mathrm{vec} (A),\mathrm{vec} (B) \rangle=\sum a_{i,j}b_{i,j}$
，结果为标量。

3）矩阵的Hadamard积
$A \bigodot B$，$(A \bigodot B)_{ij}=a_{ij}b_{ij}$，同尺寸矩阵逐元素相乘。

4）矩阵的Kronecker积
$A \bigotimes B$，将$A$每个元素乘以完整矩阵$B$，输出$mp×nq$矩阵。

### 2.2.6 张量

张量（tensor）可视为多维数组，是标量，1维向量和2维矩阵的n维推广。

## 2.3 矩阵求导

矩阵求导的本质就是函数对变元的每个元素逐个求导，只是写成了向量、矩阵的形式。

符号规定：

- $x=[x_1,x_2,…,x_m]^T∈\mathbb{R}^m$为实向量变元。
- $X∈\mathbb{R}^{m×n}$为实矩阵变元。
- $f (x)∈\mathbb{R}$为实标量函数；$f (X)∈\mathbb{R}$为实标量函数。
- $f (x)∈\mathbb{R}^p$为实向量函数。

### 2.3.1 典型计算场景

（1）标量$f (x)$对向量$x$求导
$$
\frac{\partial f (x)}{\partial x}=\left[\frac{\partial f}{\partial x_1},\frac{\partial f}{\partial x_2},…,\frac{\partial f}{\partial x_m}\right]^T
$$

示例：$f (x_1,x_2)=x_1^2+x_1x_2+2x_2^2$
$$
\frac{\partial f (x)}{\partial x}=\begin{pmatrix}2x_1+x_2\\x_1+4x_2\end{pmatrix}
$$

（2）标量$f (X)$对矩阵$X$求导 结果矩阵尺寸与$X$完全一致：
$$
\frac{\partial f (X)}{\partial X}= \begin{bmatrix} \frac{\partial f}{\partial x_{11}} & \frac{\partial f}{\partial x_{12}} & … & \frac{\partial f}{\partial x_{1n}} \\ \frac{\partial f}{\partial x_{21}} & \frac{\partial f}{\partial x_{22}} & … & \frac{\partial f}{\partial x_{2n}} \\ \vdots & \vdots & \ddots & \vdots \\ \frac{\partial f}{\partial x_{m1}} & \frac{\partial f}{\partial x_{m2}} & … & \frac{\partial f}{\partial x_{mn}} \end{bmatrix}
$$

（3）向量$f (x)$对标量$x$求导
$$
f (x)=\begin{pmatrix}f_1 (x)\\f_2 (x)\end{pmatrix}=\begin{pmatrix}2x^2+3x+1\\\sin x\end{pmatrix},\quad \frac{\partial f (x)}{\partial x}=\begin{pmatrix}4x+3\\\cos x\end{pmatrix}
$$

（4）向量$f (x)$对向量$x$求导（雅可比矩阵）
$$
\frac{\partial f (x)}{\partial x}= \begin{bmatrix} \frac{\partial f_1}{\partial x_1} & \frac{\partial f_2}{\partial x_1} & … & \frac{\partial f_p}{\partial x_1} \\ \frac{\partial f_1}{\partial x_2} & \frac{\partial f_2}{\partial x_2} & … & \frac{\partial f_p}{\partial x_2} \\ \vdots & \vdots & \ddots & \vdots \\ \frac{\partial f_1}{\partial x_m} & \frac{\partial f_2}{\partial x_m} & … & \frac{\partial f_p}{\partial x_m} \end{bmatrix}^T ∈ \mathbb{R}^{p×m}
$$

### 2.3.2 常用求导结果

$$
\begin{align*} \frac{\partial x^T a}{\partial x}&=\frac{\partial a^T x}{\partial x}=a \\ \frac{\partial x^T x}{\partial x}&=2x \\ \frac{\partial Ax}{\partial x}&=A^T \\ \frac{\partial x^T A}{\partial x}&=A \\ \frac{\partial x^T A x}{\partial x}&= (A^T+A)x \\ \frac{\partial a^T X b}{\partial X}&=ab^T \\ \frac{\partial a^T X^T b}{\partial X}&=ba^T \\ \frac{\partial a^T X X^T b}{\partial X}&=ab^T X+ba^T X \\ \frac{\partial a^T X^T X b}{\partial X}&=Xb a^T+Xa b^T \end{align*}
$$

### 2.3.3 梯度矩阵

1）标量函数梯度向量
$$
\nabla_x f (x)=\frac{\partial f (x)}{\partial x}=\left[\frac{\partial f}{\partial x_1},\frac{\partial f}{\partial x_2},…,\frac{\partial f}{\partial x_m}\right]^T
$$

2）矩阵变元梯度矩阵
$$
\nabla_X f (X)=\frac{\partial f (X)}{\partial X} ∈ \mathbb{R}^{m×n}
$$

3）黑塞矩阵（Hessian Matrix）
$$
H (x)=\left[\frac{\partial^2 f}{\partial x_i \partial x_j}\right]_{n×n}
$$

# 第 3 章 概率论

## 3.1 概率

### 3.1.1 概率的概念

概率是对事件发生的可能性的度量。通常将事件$A$的概率写作$P (A)$。

### 3.1.2 概率的计算

| 事件                 | 概率                                                    |
|----------------------|---------------------------------------------------------|
| A                    | $P(A)∈[0,1]$                                            |
| 非A                  | $P(\overline{A})=1-P(A)$                                |
| A和B（联合概率）     | $P(A∩B)=P(A                                             |B)P(B)=P(B|A)P(A)$<br>独立时：$P(A∩B)=P(A)P(B)$ |
| A或B                 | $P(A∪B)=P(A)+P(B)-P(A∩B)$<br>互斥时：$P(A∪B)=P(A)+P(B)$ |
| B条件下A（条件概率） | $P(A                                                    |B)=\frac{P(A∩B)}{P(B)}=\frac{P(B|A)P(A)}{P(B)}$ |

示例：袋内10个球，6红4蓝，不放回抽2球 事件A：第一个红球；事件B：两球都是红球 1）联合概率$P (A∩B)$
$$
P (A)=\frac{6}{10},\quad P (B|A)=\frac{5}{9},\quad P (A∩B)=\frac{5}{9}×\frac{6}{10}=\frac{1}{3}
$$
2）条件概率$P (A|B)$
$$
P (B)=\frac{C_6^2}{C_{10}^2}=\frac{1}{3},\quad P (A|B)=\frac{P (A∩B)}{P (B)}=1
$$

## 3.2 概率分布

概率分布，是指用于表述随机变量取值的概率规律。事件的概率表示了一次试验中某一个结果发生的可能性大小。如果试验结果用变量$X$
的取值来表示，则随机试验的概率分布就是随机变量的概率分布，即随机变量的可能取值及取得对应值的概率。

### 3.2.1 均匀分布

均匀分布也叫矩形分布，它表示在相同长度间隔的分布概率是等可能的。 均匀分布由两个参数$a$和$b$定义，通常缩写为$U (a,b)$。 概率密度：
$$
P (x)= \begin{cases} \frac{1}{b-a}, & a
<x<b \\ 0, & \text{其他} \end{cases}
$$

### 3.2.2 正态分布

正态分布（Normal Distribution）也称高斯分布，是常见的连续概率分布。若$X～N (\mu,\sigma^2)$，概率密度函数：
$$
f (x)=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{ (x-\mu)^2}{2\sigma^2}}
$$
$\mu$为期望（位置参数），$\sigma^2$为方差（尺度参数）；$\mu=0,\sigma^2=1$为标准正态分布。

中心极限定理：大量独立随机变量样本均值趋近正态分布。

## 3.3 贝叶斯定理

### 3.3.1 全概率公式

完备事件组$A_1,A_2,…,A_n$，则
$$
P (B)=\sum_{i=1}^n P (B|A_i)·P (A_i)
$$

### 3.3.2 贝叶斯公式

$$
P (A|B)=\frac{P (B|A)·P (A)}{P (B)}
$$

- $P (A|B)$：后验概率
- $P (B|A)$：似然概率
- $P (A)$：先验概率
- $P (B)$：证据，由全概率计算

示例：疾病发病率1%，患病检测阳性95%，无病检测阳性5%，求阳性时真实患病概率。
$$
P (\text{阳性})=0.95×0.01+0.05×0.99=0.059
$$
$$
P (\text{疾病}|\text{阳性})=\frac{0.0095}{0.059}≈0.161
$$

## 3.4 似然函数

### 3.4.1 似然函数的概念

概率：已知参数，预测观测；似然：已知观测，反推参数。

模型$P (X|\theta)$，似然函数：$L (\theta|X)=P (X|\theta)$

独立同分布样本$X= (x_1,x_2,…,x_n)$：
$$
L (\theta|X)=\prod_{i=1}^n P (x_i|\theta)
$$
对数似然（转乘积为求和）：
$$
\log L (\theta|X)=\sum_{i=1}^n \log P (x_i|\theta)
$$

### 3.4.2 极大似然估计

寻找使似然函数最大的参数$\theta$。

示例：抛硬币3次，2正1反，$\theta$为正面概率。
$$
L (\theta|X)=C_3^2 \theta^2 (1-\theta)
$$
取对数求导置0：
$$
\log L=\log3+2\log\theta+\log (1-\theta)
$$
$$
\frac{d\log L}{d\theta}=\frac{2}{\theta}-\frac{1}{1-\theta}=0
$$
解得$\theta=\frac{2}{3}$，即极大似然估计值为$\frac{2}{3}$。