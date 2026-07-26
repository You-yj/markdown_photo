# 最美公式之一：Maxwell 方程组

## 数学基础知识

在正式推导 Maxwell 方程组之前，我们先简单回顾几个重要的数学概念与定理。这些工具将帮助我们描述电场、磁场在空间中的积分与微分关系。

我们统一约定：  

- $\mathbf r = (x,y,z)$；
- 设 $\mathbf{F}(\mathbf r,t)=\big(P(\mathbf r,t),Q(\mathbf r,t),R(\mathbf r,t)\big)$ 为空间中的向量场；
- $S$ 为定向封闭曲面，$S$ 的单位法向量为 $\mathbf{n}$ ，取 $S$ 上的面元 $\mathrm d S$，定义**有向面元** $\mathrm d\mathbf S = \mathbf{n}\,\mathrm d S$；
- $V$为 $S$ 围成的体积，取 $V$ 上的体积元 $\mathrm dV$；
- $L$ 为定向封闭曲线，取 $L$ 上的线元 $\mathrm d l$，定义**有向线元** $\mathrm d\mathbf l$；
- 引入 $\nabla$ 算子 ：$\nabla = \left( \frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z} \right)$。

<div align="center">
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_1.png?raw=true" width="300" />
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_2.png?raw=true" width="300" />
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_3.png?raw=true" width="300" />
</div>
### 第二型曲面积分

对于 $\mathbf{F}$，定义通过 $\mathrm d S$ 的流量为 $\mathrm d N = \mathbf{F} \cdot \mathrm d\mathbf S = \mathbf{F} \cdot \mathbf{n}\,\mathrm d S$。

关于 $S$ 的第二型曲面积分为：
\[
\oiint_S \mathbf{F} \cdot \mathrm d\mathbf S = \oiint_S \mathbf{F} \cdot \mathbf n \,\mathrm d S
\]
这表示向量场 \(\mathbf{F}\) 通过封闭曲面 $S$ 的**通量**，它刻画向量场的场线从曲面内部向外穿出的净流量。

**高斯公式(散度定理)**将封闭曲面的通量与三重积分(体积分)联系起来：
$$
\oiint_S \mathbf{F} \cdot \mathrm d\mathbf S=\iiint_V (\nabla \cdot \mathbf{F}) \,\mathrm d V
$$

### 第二型曲线积分

对于 $\mathbf{F}$，沿$L$ 的第二型曲线积分为  ：
\[
\oint_L \mathbf{F} \cdot \mathrm d\mathbf l
\]
这表示向量场 \(\boldsymbol{F}\) 沿闭合定向曲线 L 的**环量（环流）**。

**斯托克斯公式(旋度定理)**将闭合曲线的环流与第二型曲面积分联系起来：
$$
\oint_L \mathbf{F} \cdot \mathrm d\mathbf l = \iint_{S_L} (\nabla \times \mathbf{F}) \cdot \mathrm d\mathbf S_L
$$
其中 $\partial S_L=L$。

## 物理量描述

| 电学物理量   | 符号                | 单位符号            | 单位中文名   | 磁学物理量 | 符号                | 单位符号       | 单位中文名 |
| ------------ | ------------------- | ------------------- | ------------ | ---------- | ------------------- | -------------- | ---------- |
| 电压         | $U$                 | $\mathrm{V}$        | 伏特         | 电流       | $I$                 | $\mathrm{A}$   | 安培       |
| 电场强度     | $\mathbf E$         | $\mathrm{V/m}$      | 伏特每米     | 磁场强度   | $\mathbf{H}$        | $\mathrm{A/m}$ | 安培每米   |
| 电位移矢量   | $\mathbf{D}$        | $\mathrm{C/m^2}$    | 库仑每平方米 | 磁感应强度 | $\mathbf{B}$        | $\mathrm{T}$   | 特斯拉     |
| 电场强度通量 | $\Phi_{\mathbf{E}}$ | $\mathrm{V\cdot m}$ | 伏特·米      | 磁通量     | $\Phi_{\mathbf{B}}$ | $\mathrm{Wb}$  | 韦伯       |
| 电位移通量   | $\Phi_{\mathbf{D}}$ | $\mathrm{C}$        | 库仑         | —          | —                   | —              | —          |

> - 工程应用中，电感应强度有更专业的名字：**电位移矢量**或**电通密度**
> - 为了对称性，把磁感应强度更换：**磁通密度**。单位为 $\mathrm{Wb} / \mathrm{{m}^2}$

电通量 $\Phi_{\mathbf E}$：穿过某一曲面的电场线总条数，是标量（带有正负），源头是所有电荷，而电通量 $\Phi_{\mathbf D}$ 源头只有自由电荷；磁通量 $\Phi_{\mathbf B}$：穿过某一曲面的磁感应线总条数，是标量（带有正负）。

这里我们用 $\mathbf E$ 和 $\mathbf{B}$ ，而不用 $\mathbf{D}$ 和 $\mathbf{H}$ 。其实 $\mathbf E$ 和 $\mathbf{D}$ 可以相互转化， $\mathbf D$ 和 $\mathbf{H}$ 也是： $\varepsilon\mathbf E=\mathbf D$，$\mathbf B=\mu\mathbf H$（**线性介质**中）。其中 $\varepsilon$ 为电容率， $\mu$为磁导率。

结合数学基础知识部分：若问题放到静电场场景时， $\mathbf{F}$ 即为 $\mathbf E$；放到磁场场景时， $\mathbf{F}$ 即为 $\mathbf B$。

<div align="center">
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_4.png?raw=true" width="350" />
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_5.png?raw=true" width="350" />
</div>
---

## Maxwell 方程组的推导

### 1. 高斯电场定律（Maxwell 的第一个方程）

**高斯电场定律**告诉我们：通过一个闭合曲面的电通量与曲面内包含的电荷量成正比。

通过一个闭合曲面的电通量我们可以结合之前叙述的第二型曲面积分来求：

**匀强电场中：**穿过一个平面 $S_P$ 的电场线数目即电通量： $\Phi_\mathbf E=\mathbf E \cdot \mathbf S_P$；而对于**一般电场**以及闭合曲面 $S$ 的情形，我们可以取面元 $dS$ ，面元近似为平面，且在微元范围内 $\mathbf {E}$ 近似为常矢量，故结合数学基础知识、上述情形以及高斯电场定律：
$$
\oiint_S \mathbf{E} \cdot \mathrm d\mathbf S = \frac{Q}{\varepsilon_0}
$$
其中 $Q$ 为闭合曲面内包含的电荷量， $\varepsilon_0$为真空介电常量(也称为真空电容率、电常数，是电容率 $\varepsilon$ 在真空中的量)

**或者：**
$$
\iiint_V (\nabla \cdot \mathbf{E}) \,\mathrm d V= \frac{Q}{\varepsilon_0}= \frac{1}{\varepsilon_0} \iiint_V \rho \,\mathrm d V \to \nabla \cdot \mathbf{E}=\frac{\rho}{\varepsilon_0}
$$
其中 $\rho$ 为电荷密度：单位体积内包含的**自由电荷**的电量，不包含介质极化产生的束缚电荷，因为束缚电荷的影响已经隐含在（真空）介电常数中了。**标量**，只描述空间某点电荷聚集的多少，没有方向。

于是我们得到了**Maxwell 的第一个方程**的积分与微分形式：
$$
\begin{align}
\oiint_S \mathbf{E} \cdot \mathrm d\mathbf S &= \frac{Q}{\varepsilon_0} \quad \text{积分形式} \\
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \quad\text{微分形式}
\end{align}
$$

### 2. 高斯磁场定律（Maxwell 的第二个方程）

电场有这样的规律，那磁场有没有这种规律：通过一个闭合曲面的磁通量与曲面内包含的磁荷量成正比。

没有。自然界中，正负电荷可以独立存在，遗憾的是还没发现**单独的 “磁荷(磁单极子)”**，故磁感应线与电场线不同。

**高斯磁场定律**告诉我们：磁场中任意一个闭合曲面，穿入闭合曲面的磁感线条数一定等于穿出的条数。即：磁场是无源的，不存在磁荷来发出或吸收磁场线，磁场线进去多少就出去多少，通过一个闭合曲面的磁通量一定为零。

类比Maxwell 的第二个方程，我们可以得到**Maxwell 的第二个方程**的积分与微分形式
$$
\begin{align}
\oiint_S \mathbf{B} \cdot \mathrm d\mathbf S &=0 \quad \text{积分形式} \\
\nabla \cdot \mathbf{B} &= 0 \quad\text{微分形式}
\end{align}
$$

### 3. 法拉第电磁感应定律（Maxwell 的第三个方程）

**楞次定律**：变化的磁通量所感生出来的电场会再次激发出磁场，这个磁场会阻碍原有磁通量的变化

**电场环流**：对应于数学基础知识中的第二型曲线积分中的环流。当通过一个曲面的磁通量发生变化时，会在曲面的边界**感生出一个环绕磁感线的电场**。若将一个单位正电荷放入感生出的电场中，**感应电动势会等于将这个正电荷移动一周后电场力所做的功**(电场环流就是这个正电荷放入感生出的电场中，移动一周后电场力所做的功)：
$$
\oint_L \mathbf{E} \cdot \mathrm d\mathbf l
$$

<div align="center">
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_6.png?raw=true" width="350" />
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_8.png?raw=true" width="350" />
</div>

**法拉第电磁感应定律**告诉我们：当通过回路所包围面积的磁通量发生变化时，回路中产生的**感应电动势与磁通量对时间的变化率成正比**。

再结合电场环流可以得到：
\[
\oint_L \mathbf{E} \cdot \mathrm d\mathbf l = -\frac{\mathrm d}{\mathrm d t} \iint_{S_L} \mathbf{B} \cdot \mathrm d\mathbf S_L
\]

其中负号为楞次定律的数学表现 。

**或者**：
$$
\iint_{S_L} (\nabla \times \mathbf{E}) \cdot \mathrm d\mathbf S_L= -\frac{\mathrm d}{\mathrm d t} \iint_{S_L} \mathbf{B} \cdot \mathrm d\mathbf S_L= -\iint_{S_L} \frac{\partial \mathbf{B}}{\partial t}  \cdot \mathrm d\mathbf S_L \to \nabla \times \mathbf{E}=-\frac{\partial \mathbf{B}}{\partial t}
$$
于是我们得到了**Maxwell 的第三个方程**的积分与微分形式：
$$
\begin{align}
\oint_L \mathbf{E} \cdot \mathrm d\mathbf l &= -\frac{\mathrm d}{\mathrm d t} \iint_{S_L} \mathbf{B} \cdot \mathrm d\mathbf S_L \quad \text{积分形式} \\
\nabla \times \mathbf{E}&=-\frac{\partial \mathbf{B}}{\partial t} \quad \quad\quad\quad\quad\quad\,\text{微分形式}
\end{align}
$$

### 4. 安培-麦克斯韦定律（Maxwell 的第四个方程）

**安培环路定理**给出了电流和它所激发的磁场之间的规律，它告诉我们通电导线的周围会产生围绕电流的磁场，磁场环流等于其所包含的电流总量乘上一个常数：

> 磁场环流可以类比电场环流得到

$$
\oint_LB\cdot\mathbf dl=\mu_0I
$$

其中 $\mu_0$ 是 磁导率 $\mu$ 在真空中的量。

<div align="center">
    <img src="https://github.com/You-yj/markdown_photo/blob/main/%E6%9C%80%E7%BE%8E%E6%96%B9%E7%A8%8B%E7%BB%84%E4%B9%8B%E4%B8%80%EF%BC%9AMaxwell%E6%96%B9%E7%A8%8B%E7%BB%84/Figure_9.png?raw=true" width="350" />
</div>

若把安培环路定理作为Maxwell第四个方程，很容易发现其中的不对称性。

由Maxwell 的三个方程推导过程中我们知道：**变化的磁通量会产生电场。那变化的电通量不应该也会产生磁场？**

于是Maxwell修正了安培环路定理，**将变化的电通量加入其中**，得到**安培-麦克斯韦定律**。它告诉我们：感生磁场的环流等于曲面包含的电流加上穿过曲面的电通量变化率，于是我们得到：
\[
\oint_L \mathbf{B} \cdot \mathrm d\mathbf l = \mu_0 I + \mu_0 \varepsilon_0 \frac{\mathrm d}{\mathrm d t} \iint_{S_L} \mathbf{E} \cdot \mathrm d\mathbf S_L
\]

**或者**：
$$
\iint_{S_L} (\nabla \times \mathbf{B}) \cdot \mathrm d\mathbf S_L = \mu_0 I + \mu_0 \varepsilon_0  \iint_{S_L} \frac{\partial \mathbf{E}}{\partial t} \cdot \mathrm d\mathbf S_L=\mu_0\iint_{S_L} \mathbf J\cdot\mathbf S_L+\mu_0 \varepsilon_0\iint_{S_L} \frac{\partial \mathbf{E}}{\partial t} \cdot \mathrm d\mathbf S_L\\\\\downarrow\\\
\nabla \times \mathbf{B}=\mu_0\mathbf J+\mu_0 \varepsilon_0\frac{\partial \mathbf{E}}{\partial t}
$$
其中 $\mathbf J$ 为电流密度（矢量，描述电荷朝哪个方向、以多大速率流动，既有大小，又有流动方向）。

于是我们得到了**Maxwell 的第四个方程**的积分与微分形式：
$$
\begin{align}
\oint_L \mathbf{B} \cdot \mathrm d\mathbf l &= \mu_0 I + \mu_0 \varepsilon_0 \frac{\mathrm d}{\mathrm d t} \iint_{S_L} \mathbf{E} \cdot \mathrm d\mathbf S_L \quad \text{积分形式} \\
\nabla \times \mathbf{B}&=\mu_0\mathbf J+\mu_0 \varepsilon_0\frac{\partial \mathbf{E}}{\partial t}  \quad \quad\quad\quad\quad\quad\:\,\text{微分形式}
\end{align}
$$

---

## Maxwell 方程汇总

\[
\boxed{
\begin{aligned}
\oiint_S \mathbf{E} \cdot \mathrm d\mathbf S &= \frac{Q}{\varepsilon_0} \\[6pt]
\oiint_S \mathbf{B} \cdot \mathrm d\mathbf S &= 0 \\[6pt]
\oint_L \mathbf{E} \cdot \mathrm d\mathbf l &= -\frac{\mathrm d}{\mathrm d t} \iint_S \mathbf{B} \cdot \mathrm d\mathbf S \\[6pt]
\oint_L \mathbf{B} \cdot \mathrm d\mathbf l &= \mu_0 I + \mu_0 \varepsilon_0 \frac{\mathrm d}{\mathrm d t} \iint_S \mathbf{E} \cdot \mathrm d\mathbf S
\end{aligned}
}
\]

\[
\boxed{
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\[6pt]
\nabla \cdot \mathbf{B} &= 0 \\[6pt]
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\[6pt]
\nabla \times \mathbf{B} &= \mu_0 \mathbf{J} + \mu_0 \varepsilon_0 \frac{\partial \mathbf{E}}{\partial t}
\end{aligned}
}
\]

这组方程以极简的数学形式囊括了电磁学的基本规律，被誉为“最美的公式”之一。

这种Maxwell方程组也称为**时域Maxwell方程组**（因为方程**含对时间偏导**，描述任意随时间变化的瞬态电磁场）。当然，就像前面说的，也可将 $\varepsilon_0$、 $\mu_0$换成 $\varepsilon$、 $\mu$ （真空 $\to$ 介质）， $\mathbf E$ 转化为 $\mathbf{D}$ ， $\mathbf B$ 转化为 $\mathbf{H}$ ，得到不同形式的方程组。

# 时谐Maxwell方程组

> 在实际中，广泛存在这样一类电磁场：空间中任意一点的场量都随时间按正弦（或余弦）规律做简谐变化。例如广播电视、通信的载波信号等。对于这种场，我们称之为**时谐场**。
>
> 处理时谐场时，一个核心“规定”是采用**复数表示法**（也称相量法）。其优势在于能将复杂的**含时**偏微分方程，转化为更简单的**不含时**复数方程。
>
> 1. 约定：使用复指数形式
>
>    一个关键的约定是，用复指数函数 $e^{jωt}$ 或 $e^{-iωt}$ 来表示正弦变化
>
> 2. 选择：时间因子 $e^{jωt}$ 与 $e^{-iωt}$
>
>    这是最核心的“规定”差异。不同学科或文献会采用不同的约定：
>
>    - **约定一**：采用 $e^{jωt}$ 因子（常见于工程领域）；
>    - **约定二**：采用 $e^{-iωt}$ 因子（常见于物理和光学领域）。
>
>    **这会影响后续所有公式的符号**，比如麦克斯韦方程组中旋度项的符号、阻抗定义、以及复介电常数的虚部符号等。**因此，在阅读文献或使用软件时，首要任务是确认其所采用的时间因子约定。**

1. **假设介质为线性、各向同性且非色散**：

   - 线性：$\mathbf{D}=\varepsilon\mathbf{E},\mathbf{B}=\mu\mathbf{H}$，没有非线性效应；
   - 各向同性：$\varepsilon,\mu$ 不是张量，只是标量；
   - **非色散**：$\varepsilon,\mu$ 和频率 $\omega$ 无关。

2. **时谐假设**：$\mathbf{E}(\mathbf{r},t)=\boldsymbol{E}(\mathbf{r})e^{-\mathrm{i}\omega t}$

   - $\mathbf{E}(\mathbf{r})$：**复振幅（相量）**，只跟位置 $\mathbf{r}$ 有关，不含时间；
   - $e^{-\mathrm{i}\omega t}$：全场共用的时间振荡项；
   - 真实物理场取实部：$\mathbf{E}_{\text{real}}=\mathrm{Re}\big[\boldsymbol {E}(\mathbf {r})e^{-\mathrm{i}\omega t}\big]$。(复数场本身无物理意义，所有可观测电磁场、电压、电流都必须取实部)

3. 关键操作：\(\displaystyle\frac{\partial}{\partial t} \mapsto -\mathrm{i}\omega\) 

   数学验证：\(\frac{\partial}{\partial t}\big(\boldsymbol{E}(\mathbf{r})e^{-\mathrm{i}\omega t}\big) =\boldsymbol{E}(\mathbf{r})\cdot(-\mathrm{i}\omega)e^{-\mathrm{i}\omega t} =-\mathrm{i}\omega\cdot \big(\boldsymbol{E}(\mathbf{r})e^{-\mathrm{i}\omega t}\big)\)

   也就是说：**对时间求导等价于直接乘 \(-\mathrm{i}\omega\)**。 空间算子 \(\nabla,\nabla\times\) 只作用于空间部分 \(\boldsymbol{E}(\boldsymbol{x})\)，不受影响。

至此，可以推出 **频域(时谐)Maxwell方程组**：
$$
\mathbf{E}(\mathbf{r},t)=\boldsymbol{E}(\mathbf{r})\mathrm{e}^{-\mathrm{i}\omega t},\quad
\mathbf{B}(\mathbf{r},t)=\boldsymbol{B}(\mathbf{r})\mathrm{e}^{-\mathrm{i}\omega t}.\quad
\rho(\mathbf{r},t)=\rho(\mathbf{r})\mathrm{e}^{-\mathrm{i}\omega t},\quad
\mathbf J(\mathbf{r},t)=\boldsymbol{J}(\mathbf{r})\mathrm{e}^{-\mathrm{i}\omega t}
$$

\[
\boxed{
\begin{aligned}
\nabla \cdot\boldsymbol{E} &= \frac{\rho}{\varepsilon_0} \\[6pt]
\nabla \cdot \boldsymbol{B} &= 0 \\[6pt]
\nabla \times \boldsymbol{E} &= \mathrm{i}\omega \boldsymbol{B} \\[6pt]
\nabla \times \boldsymbol{B} &= \mu_0  \boldsymbol{J}  -\mu_0 \varepsilon_0\mathrm{i}\omega \boldsymbol{E}
\end{aligned}
}
\]

**该频域表述将时间依赖吸收进复系数之中，使问题转化为关于空间变量的复值偏微分方程系统。**

# 旋度型亥姆霍兹方程

通过**消去磁场变量**的情形下，上述一阶系统可化约为电场的二阶旋度方程，工程计算中偏好 \(\boldsymbol{E},\boldsymbol{H}\) 体系，这里就用这个体系（介质可均匀 / 非均匀）。

此时频域Maxwell方程组变为：
\[
\boxed{
\begin{aligned}
\nabla \cdot\boldsymbol{E} &= \frac{\rho}{\varepsilon} \\[6pt]
\nabla \cdot \boldsymbol{H} &= 0 \\[6pt]
\nabla \times \boldsymbol{E} &= \mathrm{i}\omega\mu \boldsymbol{H} \\[6pt]
\nabla \times \boldsymbol{H} &=  \boldsymbol{J}  - \mathrm{i}\omega \varepsilon\boldsymbol{E}
\end{aligned}
}
\]

## 为什么要 “消去磁场”？

时谐 Maxwell 是**一阶耦合方程组**：同时包含 \(\boldsymbol{E},\boldsymbol{H}\) 两个未知矢量。数值计算（有限元、有限差分）中，未知场量越多计算代价越高；数学上可对法拉第旋度方程两侧同时取旋度，消去中间变量 \(\boldsymbol{H}\)，得到只含电场 \(\boldsymbol{E}\) 的单未知量二阶矢量偏微分方程，称为**旋度型亥姆霍兹方程**

## 简单推导思路

$$
\nabla\times\boldsymbol{E}=\mathrm{i}\omega\mu \boldsymbol{H} \implies \boldsymbol{H}=\dfrac{1}{\mathrm{i}\omega\mu}\nabla\times\boldsymbol{E}
$$

把 \(\boldsymbol{H}\) 代入安培-麦克斯韦定律
$$
\nabla\times\left(\frac{1}{\mathrm{i}\omega\mu}\nabla\times\boldsymbol{E}\right) =\boldsymbol{J}-\mathrm{i}\omega\varepsilon\boldsymbol{E} \to \nabla\times\left(\mu^{-1}\nabla\times\boldsymbol{E}\right) = \mathrm{i}\omega \boldsymbol{J} + \omega^2\varepsilon \boldsymbol{E}
$$
移项整理，定义波数 $k=\omega\sqrt{\mu\varepsilon}$，等效源项 $\boldsymbol{f}=\mathrm{i}\omega \boldsymbol{J}$，得到旋度型亥姆霍兹方程：
$$
\nabla\times(\mu^{-1}\nabla\times\boldsymbol{E}) - k^2 \varepsilon \boldsymbol{E} = \boldsymbol{f}
$$
其中**波数**是刻画问题尺度的核心参数。波数的倒数对应电磁波的特征波长，其大小直接决定了解的振荡频率与空间变化尺度。
