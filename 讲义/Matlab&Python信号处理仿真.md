信号处理仿真
====
* ## Matlab信号处理工具箱

>### 1.功能介绍<br>
  Matlab的三十多个工具箱大致可分为两类：功能型工具箱和领域型工具箱。 功能型工具箱主要用来扩充Matlab的符号计算功能、图形建模仿真功能、文字处理功能以及与硬件实时交互功能，能用于多种学科。领域型工具箱具有很强的专业性。Matlab信号处理工具箱主要用途是对已产生的信号进行分析和处理，包括滤波、去重、频率分析等，是一种专业性很强的领域型工具箱。<br>
>### 2.函数介绍<br>
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
>### 3.APP介绍<br>
Matlab信号处理工具箱主要包括信号处理工具箱（signal processing toolbox）、数字信号处理系统工具箱（DSP system toolbox）、统计与机器学习工具箱（statistics and machine learning toolbox）。
（1）信号处理工具箱Signal Processing Toolbox<br>
①介绍<br>
Signal Processing Toolbox是用来分析、预处理及提取均匀和非均匀采样信号的特征的工具箱，包含对信号的预处理部分（可用于滤波器设计和分析、重采样、平滑处理、去趋势和功率谱估计）的工具。对信号特征提取（如提取变化点、包络、波峰、信号模式量化信号相似性、 SNR 和失真）的工具。对振动信号进行模态和阶次分析。
<br>
②主要实现<br>
通过使用APP信号分析器（signal analyzer），在时域、频域和时频域同时预处理和分析多个信号，探查长信号并进行关注区域的提取，对信号进行滤波处理。
<br>
