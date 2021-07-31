# Flow Stability and Transition: Introduction


流动稳定性与转捩

<!--more-->

## 0. 流动稳定性简述

层流剪切层在高于某一雷诺数下会变得不稳定，这一具体雷诺数依赖于速度分布的形状。平板边界层在大约1600的雷诺数下会变得不稳定，但是在精心控制的试验下也有可能直到10000的雷诺数下依然稳定。如果平板边界层中的速度扰动增长到大约1/10来流速度，会发生二次失稳，导致流动在横流方向失去稳定性。对这些现象的精确描述需要从流动稳定性理论入手。

层流失稳通常导致流动向湍流的转变，但是也有可能转变为另一种层流状态，通常是更为复杂的状态。稳定性理论关注叠加在基本流上扰动的演化过程，在许多情况下，可以假设扰动足够小因此使得问题更加简化，最好能够足够简化以使用线性方程来描述扰动的演化，这被称为线性稳定性理论（linear stability theory or LST）。当扰动演化到其扰动速度为基本流的几个百分点时，非线性效应变得显著，此时线性方程不再能精确预测扰动的演化。尽管线性理论有其限制，但其对于理解扰动演化的物理机理以及寻找主导扰动模式（模态）有重要意义。

### 非线性扰动方程的导出

无量纲化的不可压流体的N-S方程
$$
\frac{\partial{u_i}}{\partial t} = -u_j\frac{\partial{u_i}}{\partial x_j} - \frac{\partial p}{\partial x_i}+\frac{1}{Re}\nabla^2u_i\\\\ \frac{\partial u_i}{\partial x_i} = 0
$$
使用$x_1$表示流向，$x_2$表示垂直方向，$x_3$表示展向。对于扰动的演化方程，可以考虑有一个基本流$(U_i, P)$和一个扰动状态$(U_i+u_i^{\prime},P+p^{\prime})$，两者都满足N-S方程，将两者代入N-S方程并相减后并忽略扰动量的$\prime$（方便起见）得到非线性扰动方程
$$
\frac{\partial{u_i}}{\partial t} =-U_j\frac{\partial{u_i}}{\partial x_j} -u_j\frac{\partial{U_i}}{\partial x_j} - \frac{\partial p}{\partial x_i}+\frac{1}{Re}\nabla^2u_i - u_j\frac{\partial u_i}{\partial x_j}\\\\ \frac{\partial u_i}{\partial x_i} = 0
$$
注意这里说他是非线性的是因为$u_j\frac{\partial u_i}{\partial x_j}$的存在，在小扰动假设下，这一项可以被忽略从而转化为线性方程。上面的扰动方程与初始/边界条件$u_i^0 = u_i(t=0)$构成初值问题。

为了描述初始扰动的发展，引入对其大小的一种描述。一种很自然的想法是度量扰动动能，即
$$
E_V = \frac{1}{2}\int_{V}u_iu_idV
$$
代表体积V内包含的扰动动能。

### 稳定性、临界雷诺数、扰动的空间演化

- 1.Stability

如果$U_i$是N-S方程的解，那么当施加在其上的扰动能量满足
$$
\lim_{t\to \infty}\frac{E_V(t)}{E_V(0)} \to 0
$$
那么这个解对于这个扰动是稳定的。

- 2.Conditional Stability

考虑到流动稳定与否可能与扰动的初始能量有关，引出条件稳定的定义：存在一个能量阈值$\delta>0$，当$E(0)<\delta$时$U_i$是稳定的，那么称这个解是条件稳定的。

- 3.Global Stability

条件稳定的一个特例给出全局稳定的定义：如果能量阈值$\delta \to \infty$，那么这个解全局稳定。

- 4.Monotonic Stability

最后，单调稳定性是在进一步限制扰动能量总是递减的基础上定义的，即
$$
\frac{dE_V}{dt}<0 \quad {\rm{for\ all}}\ t>0
$$

基于以上关于稳定性的定义，给出以下关于临界雷诺数的定义。

> 1. $Re_E$ (The Energy Reynolds number)  对于$Re < Re_E$流动单调稳定

这一临界雷诺数由能量理论给出（Joseph,1976）,使用Reynolds-Orr方程推导得到，下文细说。

> 2. $Re_G$ 对于$Re < Re_G$流动全局稳定

这一临界雷诺数难以在理论上推导，但是可以通过分岔分析决定。有一种猜想是这一雷诺数对应维持湍流的最低雷诺数，然而，这一猜想也不总是对的，在这时，需要定义一个临界雷诺数$Re_T$，在该雷诺数以下流动保持层流。

> 3. $Re_L$ 对于$Re > Re_L$流动线性不稳定或者非条件稳定

线性稳定性理论给出该临界雷诺数。在该雷诺数下，至少存在一个无穷小扰动是不稳定的。

{{< figure src="/images/flow-stability-1/critical.png" title="critical Reynolds numbers">}}

上图表示了几个临界雷诺数的简图，在其中的区域1，流动为单调稳定，也就是说任何形式的扰动都将会单调递减。而在区域2中，流动全局稳定，即扰动可能会增长，但是最终都将随时间演化而衰减。对于$Re> Re_G$,可能会出现不稳定性，在$Re_G$与$Re_L$之间的区域，流动为条件稳定：对于初始扰动能量在曲线以下的，其能量最终将会衰减，而高于能量曲线的扰动将导致不稳定的发生。这条曲线与$Re$坐标线的交点给出雷诺数$Re_L$，在区域4中总是存在一种形式的无穷小扰动使得流动不稳定。

前面关于稳定性的定义都是基于扰动的时间演化，在这种定义下，我们要么考虑局部扰动，假设在我们感兴趣的时间内体积$V$包含整个扰动，要么假设扰动在空间上是周期性的，而体积$V$包含一个或者多个完整周期。然而，对于这样一种扰动：即扰动是在空间中固定位置产生的，那么对稳定性的时间演化定义不再合适，需要做出修改。在这种情况下我们通常关注在扰动产生点下游扰动随空间坐标的增长情况，扰动的空间稳定性比其时间稳定性更为难以定义，因为扰动的度量不好选取。假设在平板流动中选取垂直于流动方向的扰动动能作为度量，那么可能出现以下的情况：在某一点处扰动动能为零但是其更下游处扰动并不消失。此时可以仅考虑流动在流向的稳定性，使用比如最大流向速度作为度量。

### Reynolds-Orr Equation

  使用前文得到的非线性扰动方程，对其乘以$u_i$后，并使用不可压缩流体散度为零的条件，可以得到
$$
u_i\frac{\partial u_i}{\partial t} = -u_iU_j\frac{\partial U_i}{\partial x_j}-u_iu_j\frac{\partial U_i}{\partial x_j}-u_i\frac{\partial p}{\partial x_j}+\frac{u_i}{Re}\nabla^2u_i-u_iu_j\frac{\partial{u_i}}{\partial x_j}\\\\ \Rightarrow u_i\frac{\partial u_i}{\partial t} = -u_iu_j\frac{\partial U_i}{\partial x_j} - \frac{1}{2}\frac{\partial}{\partial x_j}[u_iu_iU_j+u_iu_iu_j] - \frac{\partial (u_i p\delta_{ij})}{\partial x_j} +\frac{u_i}{Re}\nabla^2{u_i}\\\\ \Rightarrow u_i\frac{\partial u_i}{\partial t} = -u_iu_j\frac{\partial U_i}{\partial x_j} - \frac{1}{2}\frac{\partial}{\partial x_j}[u_iu_iU_j+u_iu_iu_j] - \frac{\partial (u_i p\delta_{ij})}{\partial x_j} + \frac{u_i}{Re}\nabla^2{u_i} \pm \frac{1}{Re}\frac{\partial u_i}{\partial x_j}\frac{\partial u_i}{\partial x_j}\\\\ \Rightarrow u_i\frac{\partial u_i}{\partial t} = -u_iu_j\frac{\partial U_i}{\partial x_j} - \frac{1}{Re}\frac{\partial u_i}{\partial x_j}\frac{\partial u_i}{\partial x_j} + \frac{\partial}{\partial x_j}[-\frac{1}{2}u_iu_iU_j-\frac{1}{2}u_iu_iu_j-u_ip\delta_{ij} + \frac{u_i}{Re}\frac{\partial u_i}{\partial x_j}]
$$
对上式在体积$V$中积分，并假设考虑局部扰动或者扰动在空间上具有周期性，即考虑其时间演化，得到Reynolds-Orr方程：
$$
\frac{dE_V}{dt} = -\int_{V}u_iu_j\frac{\partial U_i}{\partial x_j}dV-\frac{1}{Re}\int_{V}\frac{\partial u_i}{\partial x_j}\frac{\partial u_i}{\partial x_j}dV
$$
使用高斯散度定理，这里所有的梯度项在$V$上积分后都为零，并且非线性项也消失了。RHS中两项分别表示与基本流的能量交换以及粘性导致的能量耗散。前一项主导了扰动能量的增长而其中后一项则使得扰动能量衰减。第一项可以写成我们更熟悉的一种形式：
$$
u_iu_j\frac{\partial U_i}{\partial x_j} = u_iu_jD_{ij}\\\\ mean\ strain\ rate:\quad D_{ij} = \frac{1}{2}[\frac{\partial U_i}{\partial x_j} + \frac{\partial U_j}{\partial x_i}]
$$
非线性项的消失不禁让我们联想到：N-S方程中的非线性项对于扰动能量的演化不起作用，或者说可能非线性项保存了扰动能量。然而仔细一想会发现，这一结论基于扰动能量的定义，并不是一种天然的结果。

回到对于流动稳定性的讨论上，我们现在可以给出临界雷诺数$Re_E$的数学表达：在$Re_E$之上*任何*有限幅值的扰动能量都会单调递减，那么可以得

到：
$$
\frac{1}{Re_E} = \underset{u_i}{max} \{- \frac{\int_{V}u_iu_jD_{ij}dV}{\int_{V}\frac{\partial u_i}{\partial x_j}\frac{\partial u_i}{\partial x_j}dV}\} = \underset{u_i}{max}\frac{P(u_i)}{D(u_i)}
$$
其中$P(u_i)$和$D(u_i)$分别表示能量的产生和耗散泛函。由于R-O方程可以写为
$$
\frac{dE_V}{dt} = [- \frac{\int_{V}u_iu_jD_{ij}dV}{\int_{V}\frac{\partial u_i}{\partial x_j}\frac{\partial u_i}{\partial x_j}dV}-\frac{1}{Re}]\int_V{\frac{\partial u_i}{\partial x_j}\frac{\partial u_i}{\partial x_j}dV}
$$
如果假设$\tilde{u}_i$使得上式取得最大值，并使$u_i(t=0) = \tilde{u}_i$，那么
$$
\frac{dE(0)}{dt} = \int_{V}\frac{\partial \tilde{u}_i}{\partial x_j}\frac{\partial \tilde{u}_i}{\partial x_j}dV[\frac{1}{Re_E} -\frac{1}{Re}] > 0\quad if\ Re>Re_E
$$
这就意味着在雷诺数低于$Re_E$的情况下，所有初始扰动均单调递减。
为了求解临界雷诺数$Re_E$，我们假设速度场$u_i$可以写为以下的形式
$$
u_i = \tilde{u}_i+\epsilon \eta_i
$$

其中 $\tilde{u}$ 最大化$P(u_i)/D(u_i)$，而$\epsilon \eta_i$代表速度场与此速度场的小偏差。第一变分（first variation）为
$$
\frac{\partial}{\partial \epsilon}(\frac{1}{Re})|_{\epsilon=0}= \frac{1}{D}[\frac{\partial P}{\partial \epsilon}-\frac{P}{D}\frac{\partial D}{\partial \epsilon}]_{\epsilon=0}\\\\ =\frac{1}{D}[\frac{\partial P}{\partial \epsilon} -\frac{1}{Re}\frac{\partial D}{\partial\epsilon}]_{\epsilon=0} = 0
$$
由于有
$$
\frac{\partial}{\partial \epsilon}[-\int_{V}u_iu_jD_{ij}dV] = -2\int_{V}u_jD_{ij}\frac{\partial u_i}{\partial \epsilon}dV\\\\ \frac{\partial}{\partial \epsilon} [\int_{V}\frac{\partial u_i}{\partial x_j}\frac{\partial x_i}{\partial x_j}dV] = -2\int_{V}\frac{\partial ^2u_i}{\partial x_j\partial x_j}\frac{\partial u_i}{\partial \epsilon}dV
$$
最终我们得到
$$
u_jD_{ij} - \frac{1}{Re}\frac{\partial ^2 u_i}{\partial x_j\partial x_j} = 0
$$
这一关系给出$Re$的特征值问题，求解得到的最大特征值即为$Re_E$。如果假设扰动形式为
$$
u = \hat{u}(z)e^{i\alpha x+i\beta y}
$$
其中$\alpha$和$\beta$分别代表在两个方向上的波数，那么得到的$Re_E$是这两个参数的函数。一般情况下，方程只有无意义的零解，只有当$\alpha$，$\beta$，$Re$满足一定的关系时，才可能有非零解，这些参数满足的关系称为特征关系，而满足特征关系的参数称为特征值，相应的解就成为特征函数。寻找特征值和特征函数的问题一般就叫做特征值问题。如下图所示，给出了特征关系

{{< figure src="/images/flow-stability-1/ree.png" title="energy Reynolds number">}}

图中展示了在平板Couette流及平板Poiseuille流、Couette-Poiseuille流中的临界雷诺数与$\alpha$，$\beta$关系图。图中曲线最低点给出$Re_E$，以及最不稳定扰动的形式。

## 1. 不可压缩平行流稳定性的线性理论

平行流动，顾名思义，就是流线互相平行的流动过程，如平面Poiseuille流，Couette流等，或者有些流动如边界层流、自由剪切流可以近似为平行流，使用平行流理论处理。最典型的平行流是平面Poiseuille流，即压力梯度驱动下平行板之间的流动。
{{< figure src="/images/flow-stability-1/plane.png" title="plane Poiseuille flow">}}

在扰动能量的演化方程中，我们发现其瞬时增长率$\frac{1}{E_V}\frac{dE_V}{dt}$是与扰动幅值无关的（Henningson,1996）。或者说，对于一个有限幅值扰动，其在每一时刻的能量增长率都可以认为与某种形式的小扰动相同。因此有限幅值扰动的增长率可以使用线性方程描述，这一点与前文中提到的N-S方程中的非线性项能量守恒性是共通的。

下面从平面Poiseuille流入手推导描述粘性平行流动扰动模态的特征值方程：Orr-Sommerfeld方程。

### The Orr-Sommerfeld and Squire Equations

非线性扰动方程中舍去非线性项并使用平行流假设$U = U(y),V=0$，得到
$$
\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y} = 0\\\\ \frac{\partial u}{\partial t}+U\frac{\partial u}{\partial x}+v\frac{\partial U}{\partial y} = -\frac{1}{\rho}\frac{\partial p}{\partial x}+\frac{\mu}{\rho}(\frac{\partial ^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2})\\\\ \frac{\partial v}{\partial t}+U\frac{\partial v}{\partial x}=-\frac{1}{\rho}\frac{\partial p}{\partial y}+\frac{\mu}{\rho}(\frac{\partial ^2 v}{\partial x^2}+\frac{\partial^2 v}{\partial y^2})
$$
假设扰动的流函数及相应的速度具有形式
$$
\psi = \phi(y)e^{i(\alpha x-\omega t)}\\\\ u = \frac{\partial \psi}{\partial y} = \frac{\partial \phi}{\partial y}e^{i(\alpha x-\omega t)}\\\\ v = -\frac{\partial \psi}{\partial x} = -i\alpha \phi e^{i(\alpha x-\omega t)}
$$
代入线性化方程得到
$$
e^{i(\alpha x-\omega t)}(i\alpha \frac{\partial \phi}{\partial y} - i\alpha\frac{\partial \phi}{\partial y}) = 0\\\\ -\rho e^{i(\alpha x-\omega t)}[-i\omega \frac{\partial \phi}{\partial y}+i\alpha U\frac{\partial \phi}{\partial y}-i\alpha\phi\frac{\partial U}{\partial y} - \frac{\mu}{\rho}(-\alpha^2\frac{\partial \phi}{\partial y}+\frac{\partial ^3\phi}{\partial y^3})] = \frac{\partial p}{\partial x}\\\\ -\rho e^{i(\alpha x -\omega t)}[-\alpha \omega \phi + U\alpha^2 \phi-\frac{\mu}{\rho}(i\alpha^3\phi-i\alpha\frac{\partial^2 \phi}{\partial y^2})] = \frac{\partial p}{\partial y}
$$
为了消去压力扰动项，（2）式对y求偏导，（1）对x求偏导，相减得到
$$
-i\omega \frac{\partial^2 \phi}{\partial y^2}+i\alpha U\frac{\partial^2 \phi}{\partial y^2}-i\alpha \phi\frac{\partial ^2 U}{\partial y^2}+\frac{\mu}{\rho}(\alpha^2 \frac{\partial ^2 \phi}{\partial y^2}-\frac{\partial^4 \phi}{\partial y^4}) = -i\alpha[-\alpha \omega \phi +U\alpha^2 \phi + \frac{\mu}{\rho}(-i\alpha^3 \phi+i\alpha\frac{\partial^2 \phi}{\partial y^2})]
$$
整理后得到
$$
(U-\frac{\omega}{\alpha})(\frac{\partial^2 \phi}{\partial y^2}-\alpha^2\phi) + \frac{i\nu}{\alpha}(2\alpha^2\frac{\partial^2 \phi}{\partial y^2} - \frac{\partial^4 \phi}{\partial y^4} - \alpha^4 \phi) = 0
$$
此四阶常微分方程被称为O-S方程，当使用$c=\frac{\omega}{\alpha}$，对上式进行无量纲化：
$$
\bar{U} = \frac{U}{U_{\infty}},\quad \bar{\phi} = \frac{\phi}{U_{\infty \delta}},\quad \bar{c} = \frac{c}{U_{\infty}},\quad \bar{\alpha} = \alpha \delta,\quad Re_{\delta} = \frac{U_{\infty}}{\nu},\quad \xi = \frac{y}{\delta}
$$
得到其无量纲形式
$$
(\bar{U} - \bar{c})(\bar{\phi}^{''} - \bar{\alpha}^2\bar{\phi}) - \bar{U}^{''}\bar{\phi} + \frac{i}{\bar{\alpha} Re_{\delta}}(\bar{\phi}^{''''} - 2\bar{\alpha}^2\bar{\phi}^{''} + \bar{\alpha}^4\bar{\phi}) = 0
$$
求解O-S方程的特征值问题给出平行流的中性曲线（neutral curve），即给出了先行稳定与不稳定区之间的分界线。

当取$\alpha$为实数，扰动在$x$方向上是周期性的，取$\omega$为复数，$\omega = \omega_r + i\omega_i$，当$\omega_i >0$，扰动的模将随时间增大，层流不稳定，反之则稳定，这被称为时间模式。时间模式下，参数平面为$\alpha,Re$平面，中性曲线为$\omega_i = 0$的线。

当取$\omega$为实数，扰动在时间上是周期性的，$\alpha$为复数，若$\alpha_i>0$，层流稳定，反之则不稳定，扰动在所有空间点上保持周期幅值，在空间方向上变化，这被称为空间模式。空间模式下，参数平面为$\omega,Re$平面，中性曲线为$\alpha_i = 0$的线。

{{< figure src="/images/flow-stability-1/time.png" title="temporal problem">}}

{{< figure src="/images/flow-stability-1/spatial.png" title="spatial problem">}}

上图为线性理论得到的平面Poiseuille流的中性曲线，临界雷诺数$Re_L$约为5772.22。