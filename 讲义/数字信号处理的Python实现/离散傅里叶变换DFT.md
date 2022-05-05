## 离散傅里叶变换DFT

前面的讨论中对序列的长度未加任何限制，既可是无限长序列又可是有限长序列。对于只能在![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image187.png)的有限范围内考虑的序列，我们特引入简称为DFT的离散傅里叶变换，它本身也是有限长度序列，而不是连续函数。离散傅里叶变换不仅在理论上有重要意义，而且有快速计算的方法---快速傅里叶变换。因而离散傅里叶变换在各种实现数字信号处理的方法中起着重要作用。

### DFT的定义

离散傅里叶变换是对离散傅里叶级数的周期序列取主值，因为离散傅里叶级数虽是周期序列却只有个独立的复值，只要知道它的一个周期的内容，其它的内容也就知道了。只要把一个周期内的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image188.png)乘以对应的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image189.png)［这里的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image190.png)在![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image191.png)内取值，而![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image192.png)可在![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image193.png)内取值］，可得任意![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image192.png)下的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image194.png)；仅用![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image194.png)的一个周期的值［![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image192.png)只取区间![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image195.png)内的值］，就可得任意![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image190.png)[![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image190.png)可在区间
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image193.png)内取值］下的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image188.png)。如果同时限制时域和频域中的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image190.png)都只在区间![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image196.png)内取值,就得到了一个周期![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)的和一个周期![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image197.png)的间的对应关系

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image198.png)

(4-2-1)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image199.png)

(4-2-2)

上两式即称为有限长序列的离散傅里叶变换对。(4-2-1)式称为**离散傅里叶变换**，简称**DFT**；(4-2-2)式称为**离散傅里叶逆变换**，简称为**IDFT**。

**快速傅里叶变换（FFT)**是离散傅里叶变换的快速算法，它是根据离散傅里叶变换的奇、偶、虚、实等特性，对离散傅里叶变换的算法进行改进获得的。它对傅里叶变换的理论并没有新的发现，但是对于在计算机系统或者说数字系统中应用离散傅里叶变换，可以说是进了一大步。它考虑了计算机和数字硬件实现的约束条件，研究了有利于机器操作的运算结构，使DFT的计算时间缩短了1-2个数量级有效地减少了计算所需的存储容量。

>**Python实现案例**

[DFT的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/DFT.ipynb)

### 圆周卷积和线性卷积

#### 1线性卷积

假定![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image200.png)是列长为N的有限长序列,![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image201.png)是列长为M的有限长序列，二者的线性卷积为

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image202.png) | (4-2-3) |
|---|---|---------|

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)也是有限长序列，其列长可以这样来决定

从![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image203.png)看，序号![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image204.png)的区间为

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image205.png) | (4-2-4) |
|---|---|---------|

从![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image206.png)看，序号![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image207.png)的区间为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image208.png)

(4-2-5)

将上面两不等式相加，有

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image209.png) | (4-2-6) |
|---|---|---------|

在上述区间外不是![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image210.png)就是![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image211.png),因而![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image212.png)。所以![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)是一个n由零起到![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image213.png)的序列，列长为![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image214.png)(两序列长度之和减1)。

#### 2 圆周卷积

对![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image215.png)和![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image216.png)进行列长为L的圆周卷积![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image217.png)的情况。为此把列长为N的序列后面补上![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image218.png)个零值点，把列长为M的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image216.png)后面补上![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image219.png)个零值点各构成列长为的有限长序列。为了进行圆周卷积。我们先将![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image216.png),![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image215.png)进行周期延拓

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image221.png) ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image222.png)| (4-2-7) |
|---|---|---------|

则

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image223.png)  | (4-2-8) |
|---|---|---------|
|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image224.png)  | (4-2-9) |

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image225.png)的列长为L的周期卷积为

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image226.png) ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image227.png) | (4-2-10) |
|---|---|----------|

交换求和次序，有

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image228.png) ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image229.png) | (4-2-11) |
|---|---|----------|

上式表明：![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image215.png)、![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image216.png)的周期卷积是![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image215.png)、![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image216.png)的线性卷积![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image230.png)以为周期的延拓。

我们知道，圆周卷积就是周期卷积取主值序列，即

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image231.png)  | (4-2-12) |
|---|---|----------|

因此

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image232.png) | (4-2-13) |
|---|---|----------|

#### 3 线性卷积（有限长序列）与圆周卷积的关系

例如信号![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)通过系统![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image233.png)其输出为线性卷积![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image234.png)。以后将会看到，圆周卷积由于可以采用快速傅里叶变换技术，所以比线性卷积运算速度快。如果![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)，![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image235.png)都是有限长序列，能否用圆周卷积来取代线性卷积而不失真呢?为此必须弄清圆周卷积与线性卷积的关系，这是正确运用圆周卷积的关键。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image236.jpg)

图4.2.1 圆周卷积与线性卷积

(*a*)序列![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png) 
   (*b*)序列![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)
   (c)序列![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png)与![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)的线性卷积结果 

(d)![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png)与![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)的列长![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image239.png)的圆周卷积

(e) ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png)与![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)的列长![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image240.png)的圆周卷积 (f) ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png)与![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)的列长
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image241.png)的圆周卷积

由前面分析我们知道，线性卷积![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)具有![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image214.png)个非零序列值。因此，如果周期卷积的周期![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image242.png),则![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)的周期延拓就必然有一部分非零序列值要交叠起来，发生混淆。只有当![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image243.png)时，才不会发生交叠，这时![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)的周期延拓![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image244.png)中的每一个周期L内，前![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image214.png)个序列值正是序列![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)的值，而剩下的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image245.png)个点上序列则是补充的零值。

我们知道，圆周卷积就是周期卷积取主值序列，即

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image231.png) | (4-2-14) |
|---|---|----------|

因此

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image232.png) | (4-2-15) |
|---|---|----------|

所以要使圆周卷积与线性卷积相等，而不产生混淆的必要条件是

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image246.png) | (4-2-16) |
|---|---|----------|

符合(4-2-16)式的条件，则![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image247.png)，即

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image248.png) | (4-2-17) |
|---|---|----------|

综上所述可知:有限长序列![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png)，![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)的周期卷积是![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png)，![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)的线性卷积以周期期延拓。而圆周卷积是周期卷积去主值序列，当满足![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image246.png)的条件时，圆周卷积与线性卷积的结果是相同的。

>**Python实现案例**

求序列x=[3,11,7,0,-11,4,2]和h=[2,3,0,-5,2,1]的线性卷积。

[线性卷积的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E7%BA%BF%E6%80%A7%E5%8D%B7%E7%A7%AF.ipynb)

### 用DFT对连续时间信号逼近的问题

#### 1造成误差的三种可能现象

DFT的数学性质是确切的，但在许多信号处理的应用中，却很少作为一个最终目的被采用。我们对DFT感兴趣主要是因为它是连续傅里叶变换的一个近似。为了利用DFT对连续时间信号![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image249.png)进行傅里叶分析，则需先对![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image249.png)进行取样，得到![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)，再对进行DFT得![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image250.png)。![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image250.png)是![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)的傅里叶变换![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image117.png)在频率区间[0,2π]上的点等N间隔取样。这里![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image125.png)和![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image250.png)均为有限长序列。但是，由傅里叶变换理论可知，若信号的持续时间为有限长、则其频谱无限宽；若信号的频谱为有限宽，则其持续时间无限长。严格地讲持续时间有限的带限信号是不存在的。为能满足DFT的变换条件，实际上对频谱很宽的信号，为防止时域取样后产生频谱混叠失真，可用前置滤波器滤除幅度较小的高频分量，使连续时间信号的带宽小于折叠频率。对于持续时间很长的信号，取样点数太多以致无法存贮和计算，只好截取为有限列长进行DFT。从工程实际角度看，滤除幅度很小的高频分量和截去幅度很小部分的时间信号是允许的。由上述可见，用DFT对连续时间信号进行傅里叶分析必然是近似的，近似的准确程度严格地说是被分析波形的一个函数。特別要指出，两个变换之间的差异是因DFT需要对连续时间信号取样和截断为有限列长而产生的。这里主要有两个问题，即两变换间相对数值的确定；以及在计算的变换与所需的变换之间造成误差的三种可能现象：**混叠、栅栏效应和泄漏**。下面将分别讨论。

**①混叠现象**

假设所处理的离散时间信号是从连续时间函数取样得出的，或者为了分析的目的选取相应的连续时间信号作为参考。并假设所处理的信号是基带信号，在取样前已利用低通模拟滤波器进行前置滤波，以避免高于折叠频率的分量出现。这样为避免混叠现象，则要求取样频率

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image251.png) | (4-2-18) |
|---|-------------------------------------------------|----------|

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image252.png)为信号的最高频率，而取样周期T必须满足

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image253.png) | (4-2-19) |
|---|-------------------------------------------------|----------|

设![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image254.png)表示频率分量间的增量，它就是前面提到的频率分辨率![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image255.png)，![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image256.png)为最小记录长度，也就是前面提到的周期性函数的有效周期。![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image256.png)应按照所需的频率分辨率进行选择

|   |![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image257.png) | (4-2-20) |
|---|-------------------------------------------------|----------|

(4-2-19)和(4-2-20)两式说明了在高频容量与频率分辨率间存在着矛盾。增加高频容量，T就必然减小，在取样点数给定的情况下，记录长度必然缩短，从而降低了频率的分辨率。相反，要提高分辨率就必须要增加,在取样点数N给定时，必然导致T的增加，因而减少了高频的容暈。

在高频容量![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image258.png)与频率分辨率F两个参数中，保持其中一个不变而增加另一个的唯一办法，就是增加在一记录长度内的点数N,如果![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image258.png)和F都已给定，则N必须满足

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image259.png) | (4-2-21) |
|---|-------------------------------------------------|----------|

这是未采用任何特殊数据处理(例如加窗处理)情况下，为实现基本的DFT算法所必须满足的最低条件。

**②栅栏效应**

栅栏效应是因为用DFT计算频谱只限制为基频的整数倍而不可能将频谱视为一连续函数而产生的。就一定意义而言，栅栏效应表现为当用DFT计算一整个频谱，就好像通过一个“栅栏”来观看一个图景一样，只能在离散点的地方看到真实图景。如果不附加任何特殊处理，则在两个离散的变换线之间若有一特别大的频谱分量，将无法检测出来。

减少栅栏效应的一个方法就是在原记录末端填加一些零值点来变动时间周期内的点数， 并保持记录不变。从而在保持原有频谱连续形式不变的情况下，变更了谱线的位置。这样，原来看不到的频谱分量就能移动到可见的位置上。

必须注意，当在记录信号末端填加零点时，所用窗函数的宽度却不能由于增加了零点而按较长的长度选择，而必须按照数据记录的实际长度来选择窗函数。关于窗函数的有关知识将在下节介绍。

**③频谱泄漏**

实际工作往往需要把信号的观察时间限制在一定的时间间隔之内。设有一延伸到无限远处的离散时间信号![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image237.png)，其频谱为![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image260.png)（仅表示出周期频谱中周期的一部分）如图3-23所示。我们无法等待足够长的时间取用无限个数据，因而就要选择一段时间信号进行分析。

取用有限个数据，即将信号截断的过程，就等于将信号乘以窗函数。如果窗函数是一矩形窗函数，数据项数突然被截断，而窗内各项数据并不改变，如图中![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image238.png)所示。时域的截断，在频域相当于所研究的波形的频谱![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image260.png)与矩形窗函数频谱周期卷积过程。这一卷积造成的失真频谱见图3-23中的可以看到：频谱分量从其正常频谱扩展开来，称为“泄漏”。又如图3-24![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image261.png)所示的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image262.png)的频率![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image263.png)是![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image264.png)的整倍数，即

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image265.png) | (4-2-22) |
|---|-------------------------------------------------|----------|

这说明在处理长度![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image266.png)内有信号的k个整周期。这时由![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image267.png)构成的以![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image266.png)为周期的周期性信号是连续的。当![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image268.png)的频率不是![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image264.png)的整倍数时，则在![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image266.png)的处理长度内，就不是恰好为信号周期的整数倍，由![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image268.png)以![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image266.png)为周期进行周期延拓所得到的周期性信号就岀现了不连续点，如图3-24（b）所示，造成了频谱分量从其正常频谱扩展开来，在DFT等效滤波器组的各个副瓣将有大小不同的数值输出。我们再一次看到了频谱泄漏现象。

>**Python实现案例**

①混叠效应

[混叠效应的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E6%B7%B7%E5%8F%A0%E6%95%88%E5%BA%94.ipynb)

②栅栏效应

[栅栏效应的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E6%A0%85%E6%A0%8F%E6%95%88%E5%BA%94.ipynb)

③频谱泄露

[频谱泄露的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E9%A2%91%E8%B0%B1%E6%B3%84%E9%9C%B2.ipynb)

### 窗函数

下面讨论几种常用的窗函数及其主要性能指标。各窗函数的幅度响应以分贝形式表示，定义为

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image269.png)  | (4-2-23) |
|---|---|----------|

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image270.png)为![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image271.png)的傅里叶变换,![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image272.png)为该变换的直流值

#### 1矩形窗（Rectangular Window）

窗函数表达式推导

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image273.png) | (4-2-24) |
|---|---|----------|

式中N为偶数。对序列的截断，实际上就是加矩形窗，其对应的频谱为

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image274.png) | (4-2-25) |
|---|---|----------|

上述窗函数序列长为![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image275.png)个点。例如取偶数点，即令

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image273.png) | (4-2-26) |
|---|---|----------|

对应的谱函数为

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image276.png)  | (4-2-27) |
|---|---|----------|

以后我们就取上式所表示的函数为矩形窗频谱。

>**Python实现案例**

[矩形窗的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E7%9F%A9%E5%BD%A2%E7%AA%97.ipynb)

#### 2三角形窗（Triangular Window）

窗函数表达式推导

三角形窗又称巴特列特(Bartlett)窗。偶对称表达的三角形窗定义为

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image277.png)  | (4-2-28) |
|---|---|----------|

单边表示的三角形窗定义为

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image278.png) | (4-2-29) |
|---|---|----------|

它所对应的频谱函数为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image279.png)

(4-2-30)

其零点之间的主瓣宽度是矩形窗的两倍，第一个副瓣电平比主瓣峰值低26dB左右。三角形窗是最简单的、频谱函数![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image280.png)为非负的一种窗函数。

>**Python实现案例**

[三角形窗的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E4%B8%89%E8%A7%92%E5%BD%A2%E7%AA%97.ipynb)

#### 3汉宁窗（Hanning Window）

汉宁窗也称余弦平方窗或升余弦窗，其偶对称表示式为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image281.png)

(4-2-31)

单边表示为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image282.png)

(4-2-32)

所得到的频谱幅度函数为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image283.png)

(4-2-33)

汉宁窗是由三个互有频移的不同幅值的矩形窗频谱幅度函数相加而成，这将使副瓣大为抵消，能量更有效的集中在主瓣内，但却使主瓣加宽了一倍。

>**Python实现案例**

[汉宁窗的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E6%B1%89%E5%AE%81%E7%AA%97.ipynb)

#### 4海明窗（Hamming Window）

海明窗的偶对称表示为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image284.png)

(4-2-34)

单边表示为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image285.png)

(4-2-35)

在与汉宁窗相等的主瓣宽度下，海明窗通过调整相邻矩形窗频谱的大小，获得了更好的副瓣抑制。

>**Python实现案例**

[海明窗的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E6%B5%B7%E6%98%8E%E7%AA%97.ipynb)

#### 5布拉克曼窗（Blackman Window）

布拉克曼窗的偶对称表示为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image286.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image287.png)

(4-2-36)

单边表示

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image288.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image289.png)

(4-2-37)

单边表示的频谱幅度函数为

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image290.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image291.png)

(4-2-38)

布拉克曼利用更多的矩形窗频谱线性组合构成布拉克曼窗，得到更低的副瓣，但主瓣宽度却进一步加宽到矩形窗的三倍。

>**Python实现案例**

[布拉克曼窗的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E5%B8%83%E6%8B%89%E5%85%8B%E6%9B%BC%E7%AA%97.ipynb)

#### 6高斯窗（Gaussian Window）

已经知道，任何一种信号时宽T、频宽W之积TW满足下式

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image294.png) | (4-2-39) |
|---|---|----------|

在最小时宽频宽积即![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image295.png)的优化准则下得出的是高斯波形，因此，可选择高斯波形作窗函数。高斯波形是一直延伸到无穷大去的，但是若在波形三倍均方值的地方进行截断, 则误差很小。高斯窗如下式所示

|   |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image296.png) | (4-2-40) |
|---|---|----------|

有限长的高斯窗相当于高斯窗与矩形窗相乘。因此，有限长的高斯窗的频谱函数应是高斯窗频谱与矩形窗频谱的卷积，即

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image297.png)![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image298.png)  | (4-2-41) |
|---|---|----------|

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image299.png)是标准差值的倒数，是频谱宽度的一种度量。

>**Python实现案例**

[高斯窗的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E9%AB%98%E6%96%AF%E7%AA%97.ipynb)

#### 7凯泽窗（Kaiser Window）

凯泽窗的最优化准则是：对于有限的信号能量，要求确定一个有限时宽的信号波形，它使得频宽W内的能量为最大。凯泽窗的定义如下

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image300.png)  | (4-2-42) |
|---|---|----------|

式中![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image301.png)是零阶第一类修正贝塞尔函数。凯泽窗的频谱幅度函数可近似为

|   | ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image302.png)  | (4-2-43) |
|---|---|----------|

上面公式中的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/dsp_python/image303.png)是时宽、频宽积的一半。

>**Python实现案例**

[凯泽窗的Python实现](https://github.com/mmaayybelin/signal-processing_python/blob/main/Code/dsp_python/%E5%87%AF%E6%B3%BD%E7%AA%97.ipynb)
