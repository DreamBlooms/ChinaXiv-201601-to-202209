# 基于小波包阈值法的脉冲星信号去噪方法研究

邵广盛¹刘志杰\*」 余秋雨² 游善平「(贵州省信息与计算科学重点实验室 贵阳 550001)(四川大学网络空间安全学院，成都 610207)

摘要：小波变换去噪只对信号的低频部分进行分解和处理，忽略了信号的高频部分的分解与处理，无法对信号的整个频段信息的有效提取，进而影响脉冲星信号去噪的效果。鉴于此，本文提出利用小波包阈值法对脉冲信号进行分析，针对小波包分解后的系数选用不同的阈值函数处理。实验结果表明，使用该方法进行脉冲星信号的去噪效果得到了提高，其中脉冲星信号的信噪比、峰值信噪与平滑度指标都有相应的得到了改善，为脉冲信号的去噪提供了一种新的思路。

关键词：小波包分解；阈值法；脉冲星信号；去噪中图法分类号 P162.5 文献标志码A

2016年脉冲星观测研究利器FAST在贵州平塘落成，自此我国开始了依靠国内设备发现脉冲星的零突破。脉冲星是宇宙中的一类奇妙天体，是验证强引力场、强磁场和高密度等极端物理环境下物理规律的“天然实验室”[1。作为脉冲星研究的利器，FAST采用19 波束多波束接收机系统每天8小时对天区进行大规模巡天搜素，搜寻并接收脉冲星发出的电磁波脉冲信号，依据电磁脉冲信号确定天区中是否存在脉冲星。众所周知，处在遥远星空中的脉冲星距地球约 $3 0 0 0 ^ { \sim } 5 5 0 0 0$ 光年，脉冲星发出的脉冲信号到达地球且成功被专用仪器接收的信号能量十分微弱，整个脉冲信号淹没在极强的噪声中[2,3]。因此，脉冲星信号的去噪在整个脉冲星信号的检测和发现中显得至关重要。

小波变换作为一种多分辨分析方法能够同时在时域和频域上对信号进行分析，由于其具有时域局部化和多分辨特性而被业内人士称之为“数学显微镜”，非常适合处理非平稳信号[4]。脉冲星信号是一种典型的非平稳信号，朱晓明[5]等人提出小波分析运用到脉冲星信号去噪。他们认为小波分析可以更好的对非平稳信号进行消噪处理，因而小波变换替代了传统的傅里叶变换，在脉冲星信号的处理上大显身手。此后研究者们对小波变换去除脉冲星信号噪声进行了大量的研究，阎迪等人探索了极大极小原理、Stein无偏似然原理的脉冲星降噪方法；柯熙政等人尝试了改进阈值函数以提高脉冲星信号去噪效果，提出了软硬折中阈值函数、指数型阈值函数处理脉冲星小波分解系数，获得了较好的效果。

小波变换既能够较好的去除信号的噪声，又能较好的保持原有信号的数据，是处理信号的相对理想的工具。但小波变换主要是针对低频段信息的提取和分析，对于信号的高频段信息则经常忽略掉，这对于整个信号分析的精确度产生较大的影响。小波变换去噪是在小波函数中选择一种合适的信号处理基函数，利用小波基函数进行小波分解，根据不同阈值函数的处理结果进行对信号的重构，从而达到小波变换去噪。小波变换去噪在小波基函数的选择和阈值函数选择的不同而出现不同的去噪效果，使得小波去噪效果存在了一定的随机性[8]。

随着小波理论的进一步发展，小波包分析逐步进入研究者们的视野。小波包分析是小波分解的一般化，具有更好的信号去噪能力，既能够像小波分析一样对信号的低频部分进行分解，也能够对信号的高频部分进行分解，能更好地提取各频段的有用信息。小波包理去噪方法在图像、地震信号、心电信号、海波信号等领域不断应用，刘秀平等[9开始尝试将小波包滤波方法与X射线脉冲星脉冲噪声滤除进行结合，但并没有对小波包去噪进行系统的分析，鉴于此，本文提出将小波包阈值法应用到脉冲星信号的去噪分析中，系统分析各种阈值函数获得的去噪效果，实验显示小波包阈值法与传统的小波变换法相比，脉冲星信号的去噪效果得到了明显的提高，为脉冲星信号的研究提供一些思路。

# 1小波变换与小波包变换

# 1.1小波变换方法

观测信号可以看作为 $f ( t )$ ，满足：

$$
f ( t ) = s ( t ) + n ( t )
$$

其中 $f ( t )$ 为接收到的原始信号即含噪信号， $n ( t )$ 是方差为 $\sigma ^ { 2 }$ 的噪声，服从 $n ( 0 , \ \sigma ^ { 2 } )$ 分布，$s ( t )$ 为需要提取的去噪后的信号。一维含噪信号 $f ( t )$ 按照小波级数展开可以得到 $\mathbf { n }$ 个分辨率小波的线性组合，具体的小波变换为：

$$
\begin{array} { r } { W _ { f } \left( \psi _ { j , k } \right) = 2 ^ { \frac { j } { 2 } } \int _ { R } \overline { { f \psi } } \left( { } ^ { j } n - k \right) d _ { x } } \end{array}
$$

其中 $W _ { f } \left( \psi _ { j , k } \right)$ 为 $L ^ { 2 } ( R )$ 中取到的小波基 $\psi _ { j , k }$ 的离散小波变换，小波变换系数由上式确定。

# 1.2小波包变换方法

小波包变换是小波变换的拓展，具备小波变换处理观测信号低频部分的能力，同时能够较好的分解观测信号的高频部分，收集观测信号各个频段的有用信息，进而提高去噪精度。具体的小波包变换为：

$$
\begin{array} { r } { \left\{ \varphi ( x ) = \sqrt { 2 } \sum _ { n \in Z } h _ { n } \varphi ( 2 x - n ) \right. } \\ { \left. \psi ( x ) = \sqrt { 2 } \sum _ { n \in Z } \operatorname { g } _ { n } \varphi ( 2 x - n ) \right. } \end{array}
$$

其中 $\varphi ( x )$ 和 $\psi ( x )$ 分别为信号在 $\operatorname { L } ^ { 2 } ( R )$ 上多分辨分析中的尺度函数和小波函数，其中滤波器系数为 $h _ { n }$ 和 $\mathbf { g } _ { n }$ ，他们分别满足的条件为：

$$
\begin{array} { c } { { \sum _ { n \in Z } h _ { n } \varphi ( 2 x - n ) = \delta _ { k l } } } \\ { { \sum _ { n \in Z } h _ { n } = \sqrt { 2 } } } \\ { { \mathrm { g } _ { n } = ( - 1 ) ^ { 2 } h _ { n - 1 } } } \end{array}
$$

# 2小波包多阈值去噪法

# 2.1小波包分解与重构

小波包理论中的小波包变换具有分解与重组的性质[10]，具体小波包分解算法的数学表达式为：

$$
\begin{array} { r } { w _ { j + 1 } ^ { 2 n } ( k ) = \sum _ { l \in Z } h _ { l - 2 k } w _ { j } ^ { n } ( l ) } \end{array}
$$

$$
\begin{array} { r } { w _ { j + 1 } ^ { 2 n + 1 } ( k ) = \sum _ { l \in Z } \mathbf { g } _ { l - 2 k } w _ { j } ^ { n } ( l ) } \end{array}
$$

其中 $w _ { j } ^ { n } ( k )$ 表示在分解尺度为 $j$ 上的第 $\overset { \cdot } { n }$ 条分叉树上的第 $k$ 个小波包分解系数，而 $w _ { j + 1 } ^ { 2 n } ( k )$ 和 $w _ { j + 1 } ^ { 2 n + 1 } ( k )$ 表示 $w _ { j } ^ { n } ( k )$ 的两个分叉，具体相应的小波包重构算法的数学表达式为：

$$
\begin{array} { r } { w _ { j } ^ { n } ( k ) = \sum _ { l \in Z } h _ { k - 2 l } w _ { j + 1 } ^ { 2 n } ( l ) + \sum _ { l \in Z } \operatorname { g } _ { k - 2 l } w _ { j + 1 } ^ { 2 n + 1 } ( l ) } \end{array}
$$

其中 $w$ 为信号进过小波包分解后得到的分解系数； $h$ ， $g$ 为小波包分解的滤波器系数;$j , ~ n$ 为小波包分解中各分解节点的编号； $\boldsymbol { l } , \ \boldsymbol { k }$ 则为信号进行小波包分解所在的分解层数。

# 2.2最优小波包基的确定

小波包分析处理观测信号时，对信号进行小波包分解。小波包分解与小波分解有所不同，小波包分解是按照二叉树的形式进行分解，信号的低频和高频部分都进行相应的完全二叉树的形式进行分解。信号分解的层数会直接影响信号的去噪效果，处理的信号在进行逐层分解过程中必须要确定一个最优分解层数。分解层次过低会引起频段中混有有用信号，分解层次过高时亦会使得结果有误差[]。在小波分析去噪过程中分解层数过多会造成信号信息量的丢失，从而导致信噪比下降，影响最终的计算效果。在小波分析的实际应用中，分解尺度一般的取 $3 { \sim } 5 ^ { [ 1 2 ] }$ ，在本文的研究中取作5进行对比分析。

小波包变换中存在着多种小波构成的基底库，因此需要根据所处理信号的特性，结合代价函数的评价标准进行选择。选择小波函数时需要充分考虑脉冲信号的特点，选择能够满足给定区间的紧支性和足够的消失矩，以便能够更加有效地去除脉冲信号掺杂的噪声，提取出真正的目标脉冲信号。为了从符合脉冲星信号特点的小波基函数中确定小波基函数，本节选取了SymN、CoifN、DbN、Bior 系列小波以及Haar小波进行了比较分析。为了便于比较分析，本节中统一采用固定阈值规则，利用不同的小波基进行5层分解，分析结果如表1、表2、表3、表4所示。其中N表示小波阶数、SymN、CoifN、DbN、BiorN分别表示 Symlets、Coiflets、Daubechies、Biorthogonal 系列小波。

Table 2.1 The SNR of Pulsar signal denoised by SymN,CoifN and DbN series wavelet bases   

<html><body><table><tr><td rowspan="2">阶数N</td><td>Sym N</td><td>Coif N</td><td>Db N</td></tr><tr><td>SNR</td><td>SNR</td><td>SNR</td></tr><tr><td>1</td><td></td><td>104. 495421</td><td>93.487519</td></tr><tr><td>2</td><td>104.028278</td><td>122. 461700</td><td>104.028278</td></tr><tr><td>3</td><td>113.023734</td><td>137.609002</td><td>113.023734</td></tr><tr><td>4</td><td>117. 713573</td><td>150.993809</td><td>121. 279292</td></tr><tr><td>5</td><td>128.273024</td><td>163. 244416</td><td>128.628087</td></tr><tr><td>6</td><td>135.525030</td><td>174.287862</td><td>135.497251</td></tr><tr><td>7</td><td>142. 075414</td><td>176.879722</td><td>142. 056956</td></tr><tr><td>8</td><td>148.166205</td><td>172.385781</td><td>148.189196</td></tr><tr><td>9</td><td>153.963343</td><td>171. 814606</td><td>154.003296</td></tr><tr><td>10</td><td>159.679101</td><td>172. 627403</td><td>159.637559</td></tr><tr><td>11</td><td>161.617158</td><td>175.312769</td><td>165.295176</td></tr><tr><td>12</td><td>170.280179</td><td>176. 374491</td><td>170. 247172</td></tr><tr><td>13</td><td>173.439558</td><td>180.927850</td><td>172.002886</td></tr><tr><td>14</td><td>178.031220</td><td>177. 493286</td><td>177. 478973</td></tr><tr><td>15</td><td>176.211857</td><td>176.077450</td><td>182.380212</td></tr></table></body></html>

表2.2SymN、CoifN、DbN系列小波基的脉冲星信号去噪后信噪比

表2.1SymN、CoifN、DbN系列小波基的脉冲星信号去噪后信噪比  
Table2.2The SNR of Pulsar signal denoised by SymN,CoifN and DbN series wavelet bases   

<html><body><table><tr><td rowspan="2">阶数N</td><td>Sym N</td><td>Coif N</td><td>Db N</td></tr><tr><td>RMSE</td><td>RMSE</td><td>RMSE</td></tr><tr><td>1</td><td></td><td>1.1590260180636194e+38</td><td>1.159937964771207e+38</td></tr><tr><td>2</td><td>1.159105137508623e+38</td><td>1.1591729484203662e+38</td><td>1.1591051375086237e+38</td></tr><tr><td>3</td><td>1.15902630444004e+38</td><td>1.159201733565514e+38</td><td>1.1590263044471583e+38</td></tr><tr><td>4</td><td>1.1591290190598036e+38</td><td>1.1591803200172715e+38</td><td>1.1593325604448439e+38</td></tr><tr><td>5</td><td>1,1589381807874201e+38</td><td>1.1591317586993424e+38</td><td>1.159134635851061e+38</td></tr><tr><td>6</td><td>1.1590973148920641e+38</td><td>1.1590666107944755e+38</td><td>1.1590291941601505e+38</td></tr><tr><td>7</td><td>1.159204508875512e+38</td><td>1.1590039338852231e+38</td><td>1.1591823177722796e+38</td></tr><tr><td>8</td><td>1.1590881427106949e+38</td><td>1.1589613392166439e+38</td><td>1.1591410945254123e+38</td></tr></table></body></html>

表2.3BiorN系列小波基的脉冲星信号去噪后信噪比和均方根误差  

<html><body><table><tr><td>9</td><td>1.1589676535028293e+38</td><td>1.1589479802663968e+38</td><td>1.1590081322083972e+38</td></tr><tr><td>10</td><td>1.1590847694307965e+38</td><td>1.158964702074117e+38</td><td>1.1590547974489843e+38</td></tr><tr><td>11</td><td>1.1589516584680341e+38</td><td>1.1590042562137324e+38</td><td>1.1591076638631676e+38</td></tr><tr><td>12</td><td>1.1591001911149105e+38</td><td>1.1590495391531836e+38</td><td>1.1590266700820342e+38</td></tr><tr><td>13</td><td>1.158990764381691e+38</td><td>1.1590798965814301e+38</td><td>1.1590067783780341e+38</td></tr><tr><td>14</td><td>1.1590776721200966e+38</td><td>1.1590759265506637e+38</td><td>1.15905305165149e+38</td></tr><tr><td>15</td><td>1.1590080833152019e+38</td><td>1.159035404037832e+38</td><td>1.1590402208654303e+38</td></tr></table></body></html>

Table 2.3The SNR and RMSE of Pulsar signal denoised by SymN,CoifNand DbN series wavelet base   

<html><body><table><tr><td rowspan="2">阶数N</td><td colspan="2">Bior N</td></tr><tr><td>SNR</td><td>RMSE</td></tr><tr><td>1.1</td><td>93.487519</td><td>1.159937964771207e+38</td></tr><tr><td>1.3</td><td>92.882619</td><td>1.161230305420237e+38</td></tr><tr><td>1.5</td><td>92.564777</td><td>1.1621428245153362e+38</td></tr><tr><td>2.2</td><td>113.496536</td><td>1.1620257884498562e+38</td></tr><tr><td>2.4</td><td>114.275923</td><td>1.1593361263215988e+38</td></tr><tr><td>2.6</td><td>114.380095</td><td>1.1591729507026387e+38</td></tr><tr><td>2.8</td><td>114.370066</td><td>1.1592514421028786e+38</td></tr><tr><td>3.1</td><td>121.556228</td><td>1.4888560080440952e+38</td></tr><tr><td>3.3</td><td>131.610178</td><td>1.1712494267787645e+38</td></tr><tr><td>3.5</td><td>133.428810</td><td>1.1611795518841145e+38</td></tr><tr><td>3.7</td><td>133.791348</td><td>1.1596986873497866e+38</td></tr><tr><td>3.9</td><td>133.895611</td><td>1.1592749724774778e+38</td></tr><tr><td>4.4</td><td>128.219091</td><td>1.159259591601108e+38</td></tr><tr><td>5.5</td><td>139.266704</td><td>1.1592072048905078e+38</td></tr><tr><td>6.8</td><td>143.374262</td><td>1.15912528098707e+38</td></tr></table></body></html>

表2.4Haar系列小波基的脉冲星信号去噪后信噪比和均方根误差

Table2.4 The SNR and RMSE of Pulsar signal denoised by Haar wavelet bases   

<html><body><table><tr><td rowspan="2">阶数N</td><td colspan="2">Haar</td></tr><tr><td>SNR</td><td>RMSE</td></tr><tr><td></td><td>93.487519</td><td>1.159937964771207e+38</td></tr></table></body></html>

从以上四张表中统计的均方误根误差(RMSE)和信噪比(SNR)可以看出利用SymN、CoifN、DbN、BiorN、Haar 5种小波进行脉冲星信号去噪的整体上较好，其中 SymN系列小波的效果最好，CoifN小波次之，Bior $N$ 小波最差。此外小波基阶数不同其去噪效果也不同，单个小波基而言，Sym5 去噪效果最好。因此本文中选取了近似对称的紧支集正交小波Symmlet5作为小波基函数。因此对脉冲信号进行小波包分析，分解层数为5次，得到最优小波包基，也就是小波包分解的最优化树。

# 2.3多阈值函数的选择

利用小波包变换处理信号的过程中经常会出现"翻转"现象，也就是在信号经过高通滤波器时会进行的一种频率交叠现象，从而导致分解的小波包系数出现频率大小顺序错位。即信号的低频部分从小到大排列，信号的高频部分则是从大到小排列。因此在进行小波包阈值处理之前需要先对小波包变换后的小波包系数进行排序，再根据排序好的小波包系数选取对应的信号处理阈值。

小波包分析中常用的阈值选取准则有四种，分别为 sqtwolog（固定形式）阈值准则、rigrsure（自适应）阈值准则、heursure（启发式）阈值准则、minimaxi（极大极小值）阈值准则，本文采用 sqtwolog（固定形式）阈值准则对信号进行处理。对信号分解后每层的系数选定阈值以后，需要确定对信号处理的阈值函数。常用的阈值函数有软阈值函数、硬阈值函数。其中硬阈值函数采用的是将所有绝对值不大于阈值入的所有元素用零取代，这样容易造成处理后的信号不连续。硬阈值函数表达式为

$$
\begin{array}{c} \begin{array} { r } { \overline { { w _ { \jmath } ^ { n } } } = \left\{ { w _ { \jmath } ^ { n } } , \frac { } { } \left| w _ { j } ^ { n } \right| \geq \lambda \right. } \\ { \left. \qquad \right. \left| 0 , \frac { } \end{array} \right.} \left| { w _ { j } ^ { n } } \right| < \lambda   \end{array}
$$

软阈值函数则克服了硬阈值函数的不足，有效避免信号间断的产生，具有较好的连续性。然而在面临小波系数较大时，经过阈值函数处理以后容易造成信号的高频部分损失，进而影响信号的重构。软阈值函数的表达式为

$$
\overline { { w _ { _ { J } } ^ { n } } } = \left\{ \begin{array} { l l } { \mathrm { s i g n } \big ( w _ { _ { j } } ^ { n } \big ) ~ ( \left| w _ { _ { j } } ^ { n } \right| - \lambda ) ~ , ~ \left| w _ { _ { j } } ^ { n } \right| \geq \lambda } \\ { 0 , ~ } & { \left| w _ { _ { j } } ^ { n } \right| < \lambda } \end{array} \right.
$$

鉴于软、硬阈值函数的处理信号时都存在各自的不足，都有一定的局限性，研究人员提出了软硬阈值折中法，具体的表达式为

$$
\overline { { { w _ { j } ^ { n } } } } = \left\{ \begin{array} { l l } { \mathrm { s i g n } \big ( w _ { j } ^ { n } \big ) ~ ( \left| w _ { j } ^ { n } \right| - \alpha \lambda ) ~ , } & { \left| w _ { j } ^ { n } \right| \geq \lambda } \\ { 0 , } & { \left| w _ { j } ^ { n } \right| < \lambda } \end{array} \right.
$$

式子中的 $\alpha$ 取值范围为 $0 \leq \alpha \leq 1$ ，当 $\alpha$ 取值为0时相当于硬阈值函数，当 $\alpha$ 取值为1时相当于软阈值函数，适当的调整 $\alpha$ 的大小可以得到更好的信号去噪效果。

# 3脉冲星信号去噪分析

本实验中采用的脉冲信号来源于Parkes 脉冲星实际观测数据，该数据经过PSESTO 去干扰、消色散以后得到.dat数据文件。该数据文件以二进制形式记录，采样频率为 $1 0 2 4 \mathrm { H z }$ 。

![](images/e30645dd3eb6203d5bb34a55c83466b87953610d847545e836d90786ea2d5300.jpg)  
图1消色散后得到的信号

![](images/099f18d20043f2272defca1f4dc35ff5515ed1ea1c226d56434396898a1daa8a.jpg)  
图2消色散后得到信号的功率谱  
Fig1 The dispersion一limited signal

Fig2 The power spectrum of The dispersion一limited signal

图1中为原始脉冲信号消色散以后得到的图形，图2位原始脉冲信号消色散后所得信号的功率谱，本文实验室对目标脉冲星信号文件按照 Symmlet5进行小波包分解，分解层数为5层，分别选择了小波分析的硬阈值、软阈值、软硬折中阈值函数，采用固定阈值 sqtwolog（固定形式）阈值准则进行阈值处理。

为了更好的比较采用不同的去噪方法获得的信号去噪效果，本文参照文献[13]采用信噪比（SNR）、峰值信噪比（PSNR）、平滑度指标(r)作为评价指标进行比较最终产生的去噪效果，信噪比越大、峰值信噪比越大、平滑度指标越小则去噪效果越佳。具体公式定义如下：

（1）信噪比指的是信号和噪声的具体计算公式为：

$$
\begin{array} { r } { S N R = 1 0 l o g _ { 1 0 } [ \sum _ { i = 1 } ^ { m } f ( i ) ^ { 2 } ) / ( \sum _ { i = 1 } ^ { m } s ( i ) ^ { 2 } - f ( i ) ^ { 2 } ) ] } \end{array}
$$

（2）均方根误差的具体计算公式为：

$$
\begin{array} { r } { R M S E = \sqrt { \frac { 1 } { m } \sum _ { i = 1 } ^ { m } ( s ( i ) - f ( i ) ) ^ { 2 } } } \end{array}
$$

（3）峰值信噪比指的是信号的最大功率和噪声功率之间的比值，用PSNR表示，具体公式为：

$$
\begin{array} { r } { P S N R = 1 0 \ : l o g _ { 1 0 } [ m a x ( f ( i ) ^ { 2 } ) / \frac { 1 } { m } * ( \sum _ { i = 1 } ^ { m } s ( i ) ^ { 2 } - f ( i ) ^ { 2 } ) ] } \end{array}
$$

（4）平滑度指的是去噪后信号的差分数的方差根和信号之间的差分数的方差跟之间的比值，常用 $\mathbf { r }$ 表示，具体公式为：

$$
\scriptstyle \mathtt { r } = \sum _ { i = 1 } ^ { m - 1 } [ ( f ( i + 1 ) - f ( i ) ) ^ { 2 } ] / \sum _ { i = 1 } ^ { m - 1 } [ ( s ( i + 1 ) - s ( i ) ) ^ { 2 } ]
$$

以上计算公式中 $s ( i )$ 表示含噪信号， $f ( i )$ 为去噪后的信号。

以下分别为小波变换去噪法、小波包变换采用不同阈值处理法处理信号后的结果图、功率谱图以及去噪后的各评价指标汇总表。

![](images/bef24f9f071fd8afbfd6f2e43f7fb58b6add9a47951a484e936dafa79e77f576.jpg)

![](images/0277661f7a635f1fc95b29044494f8128cab350c38ff330a626baccec2723db9.jpg)  
Fig3 the result of de-noised with soft threshold   
图4小波硬阈值去噪后的信号

![](images/a1d2fbf801c6bad9eacfc544d7fd19503d32665c25e1e3a3db91d304ab6f7be9.jpg)  
图3小波软阈值去噪后的信号  
Fig4 the result of de-noised with wavelet soft threshold   
图5小波软、硬阈值折中法去噪后的信号  
Fig 5 the result of de-noised with wavelet soft and hard threshold

![](images/4343b12df2061e718a7e31fc56fef514d257bb5e163d631c526989e1517f8dee.jpg)  
图6小波阈值法去噪后信号的功率谱

Fig6 power spectrum of the result of de-noised with wavelet packet threshold method

![](images/725bff49dd0ba8eaef10fb6f01b55d21eac79e19da253a2a2fd670935a3256d1.jpg)  
图7小波包软阈值去噪后的信号

Fig7 the result of de-noised with wavelet packet soft threshold

![](images/5dfbc84edec068e4adf9322532c35f231f892b11e25bdd333ee5c3587528e6ed.jpg)  
Fig8 the result of de-noised with wavelet packet hard threshold

![](images/4f30d0e0514b2a8b9a8c84b7dfb5ca587d70595b1cd73d8762c31e1dc0f9f167.jpg)  
图8小波包硬阈值去噪后的信号  
图9小波包软、硬折中阈值去噪后的信号

Fig 9 the result of de-noised with wavelet packet soft and hard threshold

![](images/0fd02115d08d3cb49744ca60a7a4618d1539eefb9ed9b8d0d1e3a33f6d82671d.jpg)  
图10小波包阈值法去噪后信号的功率谱

Fig1O power spectrum of the result of de-noised by wavelet packet threshold method

表3.1小波、小波包变换去噪效果表  
Table 3.1De-noised effect table of wavelet and wavelet packet transform   

<html><body><table><tr><td>index</td><td>r</td><td>SNR</td><td>PSNR</td><td>RMSE</td></tr><tr><td>Wavelet packet soft threshold method</td><td>0.000068</td><td>128.751565</td><td>50.216641</td><td>1.1590332361351423e+38</td></tr><tr><td>Wavelet soft threshold method</td><td>0.000068</td><td>128.568456</td><td>50.205368</td><td>1.1590069073995974e+38</td></tr><tr><td>Wavelet packet hard threshold method</td><td>0.000068</td><td>128.574093</td><td>50.216641</td><td>1.1590332361351423e+38</td></tr><tr><td>Wavelet hard threshold</td><td>0.000070</td><td>127.619843</td><td>48.308142</td><td>1.1589152710109917e+38</td></tr><tr><td>method Wavelet packet soft and</td><td>0.000068</td><td>128.574093</td><td>50.216641</td><td></td></tr><tr><td>hard thresholding method Wavelet soft and hard</td><td>0.000069</td><td>128.273024</td><td>49.614505</td><td>1.1590332361351423e+38 1.1589381807874201e+38</td></tr></table></body></html>

由表3.1可知采用小波包阈值法在脉冲星信号去噪方面相比于小波变换去噪能够取得相对较好的效果，尽管小波包变换各类阈值函数处理之后，得到的均方根误差变化并不是十分明显，但是在信噪比、峰值信噪比以及平滑度方面都有相应的提升。如实验显示，采用小波包硬阈值法与小波变换硬阈值法相比，其平滑度降低至0.000068、信噪比提高至128.574093dB、峰值信噪比提高至50.216641dB，小波包软阈值、软硬折中阈值法去噪在去噪效果的评价指标上都有其相应的提升。

# 4总结与展望

本文针对小波变换在去噪方面存在的不足，提出了使用小波包阈值法对脉冲星信号去噪进行处理。小波包阈值法处理首先需要对小波包分解后的系数进行按照从小到大的顺序排列，之后采用固定阈值准则求出阈值，利用常见的软阈值函数、硬阈值函数、软硬折中阈值函数对小波包变换后的小波包系数进行处理，利用处理后的信号进行重构，从而得到去噪后的信号。文章首先从理论方面对小波包阈值法去噪进行了相关论述，之后通过实验进行验证了小波包阈值法去除脉冲星信号噪声的效果优于小波分解法。为了使实验结果得到量化标准，本文采用了信号去噪效果评价指标信噪比、峰值信噪比、平滑度以及均方根差进行量化比较不同方法去噪的效果。实验结果表明小波包阈值法去噪较小波变换有更好的取消效果。由于目前本文只使用了Symmlet5小波基和固定阈值准则对选用的Parkes 脉冲星信号进行了测试，是否适用于其他脉冲星信号、是否其他小波基或者阈值准则也能够获得同样的去噪效果有待进一步探索研究。

# 5致谢

感谢对本实验研究提供数据支持的贵州省信息与计算重点实验室以及四川大学网络空间安全学院余秋雨博士对研究的支持与帮助。

# Research on denoising method of pulsar signal based on Wavelet Packet ThresholdMethod

Shao Guangsheng',Liu Zhijie\*1,Yu Qiuyu², youshanping 1(Guizhou Key Laboratory of information and computing science,Guiyang 550001) 2(School ofCyberspace Security, Sichuan University, Chengdu 610207)

Abstract: Wavelet transform de-noising only decomposes and processes the low-frequency part of the signal, neglects the decomposition and processing of the high-frequency part of the signal, which can not effectively extract the whole frequency band information of the signal,thus affecting the denoising effect of pulsar signal. In view of this,this paper proposes to use wavelet packet threshold method to analyze pulse signal,and selects different threshold functions to process the coeficients after wavelet packet decomposition. The experimental results show that the denoising effect of pulsar signal is improved by using this method,and the signal-to-noise ratio,peak signal noise and smoothness index of pulsar signal are improved correspondingly, which provides a new idea for the denoising of pulsar signal.

Keywords: Wavelet packet decomposition; Threshold method; Pulsar signal; Denoising

# 参考文献

[1]闫振,沈志强.FAST———脉冲星观测研究的利器[J].科技导报,2017,35(24):16-19. Yan Zhen, Shen Zhiqiang.Fast: a powerful tool for pulsar observation and research [J]. Science and technology guide, 2017,35 (24): 16-19.   
[2]汪丽,柯熙政,倪广仁.基于小波变换的脉冲星弱信号的去噪方法研究［J].天文研究与技 术,2008(01） :49-54.   
Wang Li, Ke Xizheng, Ni Guangren. Research on denoising method of pulsar weak signal based on wavelet transform [J]. Astronomical research and technology, 2Oo8 (O1): 49-54.   
[3]李建勋,柯熙政,汪丽.基于高阶统计量自适应滤波的毫秒脉冲星信号处理[J].西安理工大 学学报,2009,25(01):76-79.   
Li Jianxun, Ke Xizheng, Wang Li. Millisecond pulsar signal processing based on adaptive filtering of higher order statistics [J]. Journal of Xi'an University of technology,2OO9,25 (O1): 76-79. [4]Rioul O,Vetterli M. Wavelets and signal processing[J]. IEEE Signal Processing Magzine, 1991,10, 8(4): $1 4 { \sim } 3 8$   
[5]朱晓明,廖福成,唐远炎.基于小波分析的脉冲星信号消噪处理［J].天文学   
报,2006(03) :328-335. Zhu Xiaoming,Liao Fucheng, Tang yuanyan. Pulsar signal denoising based on wavelet analysis [J].Acta astronomica Sinica, 2006 (03): 328-335   
[6]阎迪,许录平,谢振华.脉冲星信号的模糊阈值小波降噪算法［J].西安交通大学学 报,2007(10) :1193-1196.   
Yan Di, Xu Luping, Xie Zhenhua. Wavelet denoising algorithm with fuzzy threshold for pulsar signal [J]. Journal of Xi'an Jiaotong University, 2007(1O): 1193-1196.   
[7]柯熙政,汪丽,倪广仁.改进的小波阈值消噪法应用于脉冲星弱信号处理[J].西安理工大 学学报,2008(01） :18-21.   
Ke Xizheng, Wang Li, Ni Guangren. Application of improved wavelet threshold denoising method in pulsar weak signal processing [J]. Journal of Xi'an University of technology, 2O08 (O1): 18-21. [8]高迎东,王宏力，由四海,冯磊,何贻洋,刘珂.基于小波基函数选取与改进阈值函数的脉冲 星信号去噪算法研究[J].电光与控制,2020,27(04):15-19.   
Gao Yingdong, Wang Hongli, you Sihai, Feng Lei, he Yiyang, Liu Ke. Research on pulsar signal denoising algorithm based on wavelet basis function selection and improved threshold function [J]. Electro Optics and control, 2020,27 (04): 15-19.   
[9]Liu Xiuping,Yuan Wei,Han Lili,Jing Junfeng,Xu Jian,Su Zebin,Sun Haifeng. X-ray pulsar signal de-noising for impulse noise using wavelet packet[J]. Aerospace Science and   
Technology,2017,64.   
[10]阎妍,行鸿彦.基于小波包多阈值处理的海杂波去噪方法[J].电子测量与仪器学 报,2018,32(08) :172-178.   
Yan Yan, Xing Hongyan. Sea clutter denoising method based on wavelet packet multi threshold processing [J]. Journal of electronic measurement and instrumentation, 2018,32 (O8): 172-178. [11]谭文才,张秋菊.小波包多阈值去噪的一种改进方法[J].江南大学学报(自然科学 版),2012,11(02):178-181.   
Tan Wencai, Zhang Qiuju. An improved method of wavelet packet multi threshold denoising [J]. Journal of Jiangnan University (NATURAL SCIENCE EDITION),2012,11 (02): 178-181. [12]徐晨,赵瑞珍,甘小冰.小波分析·应用算法[M].北京:科学出版社,2004.   
Xu Chen, Zhao Ruizhen, Gan Xiaobing. Wavelet analysis and application algorithm [M]. Beijing: Science Press,2004.   
[13]赵杰,杨英,惠力,王志,初士博,刘茂科.小波包节点分段阈值降噪在水声监听中的应用 [J].应用声,2019,38(06):1015-1024.   
Zhao Jie, Yang Ying, Hui Li, Wang Zhi, Chu Shibo, Liu maoke. Application of wavelet packet node segmentation threshold denoising in underwater acoustic monitoring [J]. Applied sound, 2019,38 (06): 1015-1024.