信号处理仿真
====
* ## Matlab信号处理工具箱

>### 1.功能介绍<br>
  Matlab的三十多个工具箱大致可分为两类：功能型工具箱和领域型工具箱。 功能型工具箱主要用来扩充Matlab的符号计算功能、图形建模仿真功能、文字处理功能以及与硬件实时交互功能，能用于多种学科。领域型工具箱具有很强的专业性。Matlab信号处理工具箱主要用途是对已产生的信号进行分析和处理，包括滤波、去重、频率分析等，是一种专业性很强的领域型工具箱。<br>
>### 2.函数介绍<br>

**滤波器分析**
|函数|	作用|
|:----:|:----:|
|abs	|幅度
|angle	|相位
|filternorm|	计算以2或inf为范数的数字滤波器
|freqs|	Laplace变换频率响应
freqspace|	频率响应步长
freqz	|z变换频率响应
fvtool|	滤波器可视化工具
grpdelay	|群延时
impz	|离散单位冲激响应
phasez	|数字滤波器相频特性
phasedelay	|数字滤波器相位延时
Unwrap|	纠正相位角产生更为平滑的相位图
Zerophase	|实滤波器的零极点响应
Zplane|	离散零极点图



**滤波器设计与实现**

| 函数       | 作用                         |
|------------|------------------------------|
| conv       | 卷积                         |
| conv2      | 二维卷积                     |
| convmtx    | 卷积矩阵                     |
| deconv     | 解卷积                       |
| fftfilt    | 基于FFT重叠相加法的FIR滤波器 |
| filter     | 滤波器实现                   |
| filter2    | 二维数字滤波                 |
| filtfilt   | 零相位数字滤波器             |
| filtic     | 计算直接Ⅱ型滤波器的初始条件  |
| latcfilt   | Lattice型滤波器的实现        |
| medfilt1   | 一维中值滤波                 |
| sgolayfilt | Savitzky-Golay滤波器实现     |
| sosfilt    | 二阶节滤波器实现             |
| upfirdn    | FIR滤波器的过采样和欠采样    |



**离散时间滤波器**

| 函数  | 作用                   |
|-------|------------------------|
| dfilt | 创建离散时间滤波器对象 |



**FIR滤波器设计**

| 函数      | 作用                                                |
|-----------|-----------------------------------------------------|
| cremez    | 具有非线性相位的等波纹FIR滤波器设计                 |
| fir1      | 基于窗函数的FIR滤波器——标准响应                     |
| fir2      | 基于窗函数的FIR滤波器——任意响应                     |
| fircls    | 构建最小平方滤波器，用于多通道滤波器组              |
| fircls1   | 构建最小平方滤波器，用于线性相位FIR低通或高通滤波器 |
| firgauss  | FIR高斯滤波器滤波器设计                             |
| firls     | 最小平方线性相位滤波器设计                          |
| firrcos   | 升余弦滤波器设计                                    |
| intfilt   | 插值FIR滤波器设计                                   |
| kaiserord | 利用Kaiser窗为FIR滤波器设计估值                     |
| remez     | 计算Parks-McClellan用以优化FIR滤波器设计            |
| remezord  | Parks-McClellan优化FIR滤波器阶次设计                |
| sgolay    | Savitzky-Golay型FIR平滑滤波器设计                   |



**IIR滤波器设计**

| 函数     | 作用                                   |
|----------|----------------------------------------|
| butter   | Butterworth滤波器设计                  |
| cheby1   | Chebyshev Ⅰ型滤波器设计 （通带等波纹） |
| cheby2   | Chebyshev Ⅱ型滤波器设计 （阻带等波纹） |
| ellip    | 椭圆滤波器设计                         |
| maxflat  | 数字Butterworth滤波器设计              |
| yulewalk | Yule-Walker滤波器设计                  |



**IIR滤波器阶数**

| 函数     | 作用                        |
|----------|-----------------------------|
| buttord  | Butterworth滤波器阶数估计   |
| cheb1ord | Chebyshev阶数估计           |
| cheb2ord | Chebyshev Ⅱ型滤波器阶数估计 |
| ellipord | 椭圆滤波器阶数估计          |



**模拟滤波器原型**

| 函数     | 作用                    |
|----------|-------------------------|
| besselap | Bessel滤波器原型        |
| buttap   | Butterworth滤波器原型   |
| cheb1ap  | Chebyshev Ⅰ型滤波器原型 |
| cheb2ap  | Chebyshev Ⅱ型滤波器原型 |
| ellipap  | 椭圆滤波器原型          |


**模拟滤波器设计**

| 函数    | 作用                    |
|---------|-------------------------|
| besself | Bessel滤波器设计        |
| butter  | Butterworth滤波器设计   |
| cheby1  | Chebyshev Ⅰ型滤波器设计 |
| cheby2  | Chebyshev Ⅱ型滤波器设计 |
| ellip   | 椭圆滤波器设计          |


**模拟滤波器变换**

| 函数  | 作用      |
|-------|-----------|
| lp2bp | 低通→带通 |
| lp2bs | 低通→带阻 |
| lp2hp | 低通→高通 |
| lp2lp | 低通→低通 |



**滤波器离散化**

| 函数     | 作用           |
|----------|----------------|
| bilinear | 双线性变换     |
| impinvar | 冲激响应不变法 |



**线性系统变换**

| 函数      | 作用                            |
|-----------|---------------------------------|
| latc2tf   | Lattice梯形结构到传输函数的变换 |
| polystab  | 是多项式具有稳定性              |
| polyscale | 在z域内计算多项式的根           |
| residuez  | z变换的留数展开                 |
| sos2ss    | 二阶节→状态空间                 |
| sos2tf    | 二阶节→传输函数                 |
| sos2zp    | 二阶节→零极点                   |
| ss2sos    | 状态空间→二阶节                 |
| ss2tf     | 状态空间→传输函数               |
| ss2zp     | 状态空间→零极点                 |
| tf2latc   | 传输函数→lattice结构            |
| tf2sos    | 传输函数→二阶节                 |
| tf2ss     | 传输函数→状态空间               |
| tf2zpk    | 传输函数→零极点                 |
| zp2sos    | 零极点→二阶节                   |
| zp2ss     | 零极点→状态空间                 |
| zp2tf     | 零极点→传输函数                 |





**窗函数**

| 函数           | 作用                      |
|----------------|---------------------------|
| bartlett       | Bartlett窗                |
| barthannwin    | 修正的Bartlett-Hanning窗  |
| blackman       | Blackman窗                |
| blackmanharris | 最小四项Blackman-Harris窗 |
| bohmanwin      | Bohman窗                  |
| chebwin        | Chebyshev窗               |
| flattopwin     | 平顶窗                    |
| gausswin       | Guassian窗                |
| hamming        | 汉明窗                    |
| hann           | Hann窗                    |
| kaiser         | Kaiser窗                  |
| nuttallwin     | 最小四项Blackman-Harris窗 |
| parzenwin      | Parzen窗                  |
| rectwin        | 矩形窗                    |
| triang         | 三角窗                    |
| tukeywin       | Tukey窗                   |
| wvtool         | 窗函数可视化工具          |
| window         | 计算特定窗函数            |



**窗对象**

| 函数   | 作用           |
|--------|----------------|
| sinwin | 创建一个窗对象 |





**信号变换**

| 函数          | 作用                          |
|---------------|-------------------------------|
| bitrevorder   | 将输入按位反序排列            |
| czt           | 线性z变换                     |
| dct           | 离散余弦变换                  |
| dftmtx        | 离散傅里叶变换矩阵            |
| digitrevorder | 将输入按数字反序排列          |
| fft           | 快速傅里叶变换                |
| fft2          | 二维快速傅里叶变换            |
| fftshift      | 交换向量的上下两部分          |
| goertzel      | 二阶Goertzel代数              |
| hilbert       | 离散时间解析信号的Hilbert变换 |
| idct          | 反离散余弦变换                |
| ifft          | 反快速傅里叶变换              |
| ifft2         | 反二维快速傅里叶变换          |



**倒谱分析**

| 函数   | 作用             |
|--------|------------------|
| cceps  | 复倒谱分析       |
| icceps | 复倒谱分析反变换 |
| rceps  | 实倒谱分析       |


**随机信号处理与功率谱分析**

| 函数        | 作用                                        |
|-------------|---------------------------------------------|
| cohere      | 相关函数估计                                |
| corrcoef    | 相关系数                                    |
| corrmtx     | 自相关系数矩阵                              |
| cov         | 协方差矩阵                                  |
| csd         | 互谱密度                                    |
| pburg       | 通过Burg方法进行功率谱密度估计              |
| pcov        | 通过协方差方法进行功率谱密度估计            |
| peig        | 通过Eigenvector方法进行功率谱密度估计       |
| periodogram | 通过周期图方法进行功率谱密度估计            |
| pmcov       | 通过改进的协方差方法进行功率谱密度估计      |
| pmtm        | 通过Thomson多个正交窗方法进行功率谱密度估计 |
| pmusic      | 通过MUSIC方法进行功率谱密度估计             |
| psdplot     | 点功率谱密度                                |
| pwelch      | 通过Welch方法进行功率谱密度估计             |
| pyulear     | 通过Yule-Walker AR方法进行功率谱密度估计    |
| rooteig     | 通过Eigenvector算法估计正弦频率和功率       |
| rootmusic   | 通过MUSIC算法估计正弦频率和功率             |
| tfe         | 传输函数估计                                |
| xcorr       | 互相关函数                                  |
| xcorr2      | 二维互相关函数                              |
| xcov        | 协方差函数                                  |



**参数建模**

| 函数     | 作用                                              |
|----------|---------------------------------------------------|
| arburg   | 通过Burg方法实现AR参数建模                        |
| arcov    | 通过协方差方法实现AR参数建模                      |
| armcov   | 通过改进的协方差方法实现AR参数建模                |
| aryule   | 通过Yule-Walker方法实现AR参数建模                 |
| ident    | 详见System Identification工具箱                   |
| invfreqs | 根据频响特性生成模拟滤波器                        |
| invfreqz | 根据频响特性生成数字滤波器                        |
| prony    | 生成Prony数字滤波器，其冲激响应等于给定的时间序列 |
| stmcb    | 生成IIR滤波器，给定其输入与输出序列               |



**线性预测**

| 函数      | 作用                                   |
|-----------|----------------------------------------|
| ac2rc     | 自相关序列到反射系数的转换             |
| ac2poly   | 自相关序列到预测多项式的转换           |
| is2rc     | 反正弦参数到反射系数的转换             |
| lar2rc    | 对数面积比到反射系数的转换             |
| levinson  | Levinson-Durbin递归                    |
| lpc       | 使用自相关的方法计算线性预测滤波器系数 |
| lsf2poly  | 线谱频率到预测滤波器系数的转换         |
| poly2ac   | 预测多项式→自相关系列                  |
| poly2lsf  | 预测多项式→线谱频率                    |
| poly2rc   | 预测多项式→反射系数                    |
| rc2ac     | 反射系数→自相关序列                    |
| rc2is     | 反射系数→正弦参数                      |
| rc2lar    | 反射系数→对数面积比参数                |
| rc2poly   | 反射系数→预测滤波器多项式              |
| rlevinson | 反Levinson-Durbin递归                  |
| schurrc   | Schur算法                              |



**多采样率信号处理**

| 函数       | 作用                      |
|------------|---------------------------|
| decimate   | 减小采样速率并重新采样    |
| downsample | 将采样速率减少整数倍      |
| interp     | 将采样速率增大整数倍      |
| interp1    | 产生一维插值              |
| resample   | 变换采样速率并重新采样    |
| spline     | 三次样条插值              |
| upfirdn    | FIR滤波器的过采样和欠采样 |
| upsample   | 对输入信号过采样          |



**波形产生**

| 函数      | 作用                      |
|-----------|---------------------------|
| chirp     | 扫频余弦信号              |
| diric     | Dirichlet（周期sinc）信号 |
| gauspuls  | 高斯射频序列产生器        |
| gmonopuls | 高斯脉冲序列产生器        |
| pulstran  | 脉冲序列产生器            |
| rectpuls  | 非周期矩形采样信号        |
| sawtooth  | 锯齿波                    |
| sinc      | sinc函数（辛克函数）      |
| square    | 方波                      |
| tripuls   | 非周期三角波采样信号      |
| vco       | 压控振荡器                |





**特殊操作**

| 函数       | 作用                                 |
|------------|--------------------------------------|
| buffer     | 信号向量到矩阵形式数据帧的缓冲器     |
| cell2sos   | 单元数组→二阶节矩阵                  |
| cplxpair   | 求向量的共轭对                       |
| demod      | 通信仿真解调                         |
| dpss       | Slepian序列                          |
| dpssclear  | 从数据库中删除Slepian序列            |
| dpssdir    | 删除Slepian序列所在数据库目录        |
| dpssload   | 从数据库中装载删除Slepian序列        |
| dpsssave   | 将删除Slepian序列保存到数据库中      |
| eqtflength | 对齐离散时间传输函数的长度           |
| modulate   | 通信仿真中的调制                     |
| seqperiod  | 寻找向量中长度最小的重复序列         |
| sos2cell   | 二阶节矩阵→单元数组                  |
| specgram   | 功率谱                               |
| stem       | 绘制离散时间序列                     |
| strips     | 带状图                               |
| udecode    | 将整数解码得到浮点数                 |
| uencode    | 将浮点数均匀量化并编码以得到整数输出 |



**图形用户接口**

| 函数    | 作用                 |
|---------|----------------------|
| fdatool | 滤波器设计和分析工具 |
| fvtool  | 滤波器可视化工具     |
| sptool  | 信号处理工具         |
| wintool | 窗函数设计和分析工具 |
| wvtool  | 窗函数可视化工具     |

>### 3.APP介绍<br>
Matlab信号处理工具箱主要包括信号处理工具箱（signal processing toolbox）、数字信号处理系统工具箱（DSP system toolbox）、统计与机器学习工具箱（statistics and machine learning toolbox）。
（1）信号处理工具箱Signal Processing Toolbox<br>
①介绍<br>
Signal Processing Toolbox是用来分析、预处理及提取均匀和非均匀采样信号的特征的工具箱，包含对信号的预处理部分（可用于滤波器设计和分析、重采样、平滑处理、去趋势和功率谱估计）的工具。对信号特征提取（如提取变化点、包络、波峰、信号模式量化信号相似性、 SNR 和失真）的工具。对振动信号进行模态和阶次分析。
<br>
②主要实现<br>
通过使用APP信号分析器（signal analyzer），在时域、频域和时频域同时预处理和分析多个信号，探查长信号并进行关注区域的提取，对信号进行滤波处理。
<br>

