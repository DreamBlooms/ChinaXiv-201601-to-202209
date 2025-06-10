# 锁相环频率合成器最优环路带宽的选取

孙家星」孙越强²杜起飞²

(1.中国科学院大学,北京，100049;2.中国科学院 国家空间科学中心，北京，100190)

摘要：锁相环频率合成器环路带宽值的选取直接影响其输出相位噪声。基于此，本文首先介绍了锁相环的基本组成部分，然后分析了晶振、集成锁相芯片和压控振荡器相位噪声对频率合成器环路输出端的噪声影响，从而导出了最优环路带宽计算公式。并且通过基于 PE3236芯片的频率合成器的输出相位噪声测量对最优环路带宽公式正确性进行了验证。结果表明：当根据最优环路带宽公式取值时，锁相环频率合成器的输出相位噪声满足实际应用需求。

关键词：锁相环；频率合成器；环路带宽；相位噪声

# 中图分类号：TN911.8 文献标识码：A

# The Selection of the Optimum Loop Bandwidth of PLL Frequency

# Synthesizer

SUN Jia xing1 SUN Yueqiang ² DU Qifei ² (1.University of Chinese Academy of Sciences,Beijing,1Ooo49, CHN; 2.National Science Space Center, Chinese Academy of Science,Beijing,1OO190, CHN)

Abstract: The selection of bandwidth value of PLL frequency synthesizer has a direct influence on the output phase noise. Base on this,the paper first introduces the basic components of the PLL,and then analyzes the crystal Oscillator and integrated PLLchipand the voltage controlled oscillator phase noise on the output of the frequency synthesizer loop noise influence.So the formula forcalculating the optimal loop bandwidth is derived.Also the optimal loop bandwidth formula is verified by the measurement of the output phase noise of the frequency synthesizer based on the PE3236 chip.The results show that when the optimal bandwidth value according to the formula,the output phase noise of PLL frequency synthesizer meet the needs of practical application.

Key Words :Phase lock Loop; Frequency Synthesizer; Loop Width; Phase Noise EEACC:1350H

# 1引言

在通信系统中，锁相环频率合成器是产生本振频率的一种方法[1。该方法具有输出频率频谱纯度高和频率范围宽等优点，广泛应用于通信、航天和遥测等技术领域，是现阶段主流的频率合成技术。而环路输出相位噪声是锁相环频率合成器主要技术指标之一，它直接影响到整个通信系统的性能[2]。因此本文通过对影响环路输出的两类噪声分析，推导出环路带宽公式来选取最优环路带宽值。并且通过实验验证了该公式可以被应用在频率合成器环路带宽值的选取中。

联系作者：E-mail: sunjiaxing14@mails.ucas.ac.cn

# 2锁相环相位噪声模型

锁相环[3](Phase LockLoop,PLL)是一种允许用外部参考信号控制环路内部振荡器的频率和相位的电路，同时也是一个相位反馈控制电路。锁相环结构由四大部分组成，分别为鉴相器、低通滤波器、压控振荡器和分频器。

锁相环频率合成器[4中，噪声来源很多，考虑的实际应用，通常将这些噪声看作由外部输入。有源器件组成的环路滤波器等效噪声与其他噪声相比较数值较小，将其忽略。锁相环频率合成器环路相位噪声模型如下图所示。

![](images/7b2ce5c6670d4c689a0bbc5a963fc251e41cbd6d2446693c865c8486d8b8a2e8.jpg)  
图1环路相位噪声模型  
Fig.1 Loop phase noise model

在上图中，将锁相频率合成器相位噪声[5]来源分为两类：一类是低通型相位噪声；另一类是高通型相位噪声。低通型相位噪声为温补晶振和集成锁相芯片内部触发器导致的噪声。上图中集成锁相芯片噪声主要分为：数字分频器的触发相位噪声和鉴相器的触发相位噪声。根据锁相频率合成器输出相位噪声叠加在输出端，因此可以看做晶振经过倍频与压控振荡器频率进行鉴相，得到的晶振倍频相位噪声与集成锁相芯片内部相位噪声较为接近，因此不能忽略晶振对锁相环输出相位噪声的影响。

高通型相位噪声通常被称之为振荡器噪声。该锁相环路中压控振荡器的相位噪声主要是闪烁噪声和热噪声组成。

由于低通型和高通型噪声功率远小于信号功率，因此，这两类噪声对信号噪声谱密度的影响可以近似堪为独立无关处理。因此，环路输出的相位噪声谱密度可以表示为：

$$
S _ { \varphi o } ( \omega ) = S _ { \varphi l 0 } ( \omega ) + S _ { \varphi h 0 } ( \omega )
$$

式中， $\boldsymbol { \mathsf { S } } _ { \varphi l 0 } ( \omega )$ 为晶振和触发器共同作用时经过环路输出的相位噪声谱密度、 $\boldsymbol { \mathrm { S } } _ { \varphi h 0 } ( \omega )$ 为压控振荡器作用时经过环路输出的相位噪声谱密度。一般低通型噪声能量主要集中在低频部分。当环路带宽较窄[7]时候，如下公式。

$$
\left( \frac { s i n ^ { 2 } \left( \frac { \pi \omega } { \omega _ { r } } \right) } { \left( \frac { \pi \omega } { \omega _ { r } } \right) ^ { 2 } } \right) \approx 1
$$

晶振和集成锁相芯片内部相位噪声谱密度[8]可以表示为：

$$
S _ { \varphi r } ( \omega ) + S _ { \varphi j } ( \omega ) = h { \omega _ { r } } ^ { - 1 } + 4 \pi { \sigma ^ { 2 } } _ { \Delta t R } \omega _ { r }
$$

压控振荡器相位噪声谱密度可以表示为：

$$
S _ { \varphi v } ( \omega ) = h _ { - 1 v } \omega ^ { - 3 } + h _ { 0 v } \omega ^ { - 2 } + h _ { 1 v } \omega ^ { - 1 } + h _ { 2 v } \omega ^ { 0 } \approx h _ { - 1 v } \omega ^ { - 3 }
$$

式中， $h _ { - 1 v } \setminus h _ { 0 v } \setminus h _ { 1 v }$ 和 $h _ { 2 v }$ 分别为压控振荡器闪变噪声调频谱、白噪声调频谱、闪变噪

声调相谱和白噪声调相谱的幂律谱系数。实际中压控振荡器噪声谱中的闪变噪声调频谱为优势谱，因此将上式中后三项忽略。

# 3最优环路带宽

锁相环路低通滤波器采用高增益二阶环路，此时整个环路的传递函数的幅度频率特性为：

$$
\begin{array} { r } { | \mathrm { H } _ { l } ( j \omega ) | ^ { 2 } = \frac { \omega _ { n } { } ^ { 2 } ( \omega _ { n } { } ^ { 2 } + 4 \varepsilon ^ { 2 } \omega ^ { 2 } ) } { \omega _ { n } { } ^ { 4 } + 2 \omega _ { n } { } ^ { 2 } ( 2 \varepsilon ^ { 2 } - 1 ) \omega ^ { 2 } + \omega ^ { 4 } } ) } \end{array}
$$

$$
\begin{array} { r } { | \mathrm { H } _ { h } ( j \omega ) | ^ { 2 } = \frac { \omega _ { n } ^ { 4 } } { \omega _ { n } { } ^ { 4 } + 2 \omega _ { n } { } ^ { 2 } ( 2 \varepsilon ^ { 2 } - 1 ) \omega ^ { 2 } + \omega ^ { 4 } } ) } \end{array}
$$

式中 $| \mathrm { H } _ { l } ( j \omega ) | ^ { 2 } \cdot ~ | \mathrm { H } _ { h } ( j \omega ) | ^ { 2 }$ 分别为低通型相位噪声单独作用和高通型相位噪声单独作用时候环路的输出幅频特性。 $\varepsilon$ 和 $\omega$ 为阻尼系数和环路自然谐振频率[9]。

由环路输出相位噪声方差公式：

$$
\begin{array} { r } { \sigma ^ { 2 } { } _ { \varphi o } = 1 / 2 \pi \int _ { 0 } ^ { \infty } \mathsf { S } _ { \varphi o } ( \omega ) | \mathrm { H } ( j \omega ) | ^ { 2 } d \omega } \end{array}
$$

将上述公式分别代入环路输出相位噪声方差公式得：

$$
\begin{array} { r } { \sigma _ { \varphi r o } ^ { 2 } + \sigma _ { \varphi r o } ^ { 2 } = 1 / 2 \pi \int _ { 0 } ^ { \infty } ( S _ { \varphi r } ( \omega ) | \mathrm { H } _ { l } ( j \omega ) | ^ { 2 } + S _ { \varphi j } ( \omega ) | \mathrm { H } _ { l } ( j \omega ) | ^ { 2 } ) d \omega = \mathrm { h } _ { 2 } \mathrm { B } _ { L } } \end{array}
$$

$$
\sigma ^ { 2 } \varphi v o = { \frac { 1 } { 2 \pi \int _ { 0 } ^ { \infty } \mathsf { S } _ { \varphi v } ( \omega ) \mid \mathrm { H } _ { h } ( j \omega ) \mid ^ { 2 } d \omega } } = { \frac { 1 } { 2 \pi \int _ { 0 } ^ { \infty } { \frac { h _ { - 1 v } \omega d \omega } { { \omega _ { n } } ^ { 4 } + 2 { \omega _ { n } } ^ { 2 } ( 2 \varepsilon ^ { 2 } - 1 ) \omega ^ { 2 } + \omega ^ { 4 } } } } }
$$

$$
\begin{array} { r } { = \frac { h _ { - 1 \vartheta } ( 4 \varepsilon ^ { 2 } + 1 ) ^ { 2 } } { \pi ( 8 \varepsilon ) ^ { 3 } \mathrm { B } _ { L } ^ { 2 } \sqrt { \varepsilon ^ { 2 } - 1 } } l n \big [ ( 2 \varepsilon ^ { 2 } - 1 ) + 2 \varepsilon \sqrt { \varepsilon ^ { 2 } - 1 } \big ] } \end{array}
$$

令 $\begin{array} { r } { \mathrm { \partial } \mathrm { M } = \frac { h _ { - 1 v } ( 4 \varepsilon ^ { 2 } + 1 ) ^ { 2 } } { \pi ( 8 \varepsilon ) ^ { 3 } \sqrt { \varepsilon ^ { 2 } - 1 } } l n \big [ ( 2 \varepsilon ^ { 2 } - 1 ) + 2 \varepsilon \sqrt { \varepsilon ^ { 2 } - 1 } \big ] } \end{array}$ 得到下式：

$$
\sigma ^ { 2 } { } _ { \varphi o } = \mathrm { h } _ { 2 } \mathrm { B } _ { L } + M / { B _ { L } } ^ { 2 }
$$

$$
\begin{array} { r } { B _ { L } = \sqrt [ 3 ] { \frac { h _ { - 1 v } } { \mathrm { h } _ { 2 } } \frac { 2 ( 4 \varepsilon ^ { 2 } + 1 ) ^ { 2 } } { \pi ( 8 \varepsilon ) ^ { 3 } \sqrt { \varepsilon ^ { 2 } - 1 } } l n \big [ \big ( 2 \varepsilon ^ { 2 } - 1 \big ) + 2 \varepsilon \sqrt { \varepsilon ^ { 2 } - 1 } \big ] } } \end{array}
$$

当环路带宽处于某一值时，环路输出相位噪声方差为其极小值点，因此该频点为最优环路带宽值。当阻尼系数选取1-1.5之间时，该最优带宽值[10]为：

$$
\begin{array} { r } { \mathrm { B } _ { L } = ( \frac { 2 } { 5 } ) ^ { 3 } \sqrt { \frac { h _ { - 1 v } } { \mathrm { h } _ { 2 } } } } \end{array}
$$

# 4实验验证

此实验基于PE3236芯片的锁相环频率合成器进行。采用直接测量10MHz温补晶振相位噪声和芯片手册给出的触发器相位噪声进行相加所得的相位噪声谱密度在环路相位噪声近端表现为 $\mathrm { S } _ { \varphi r } ( \omega ) = \mathrm { h } _ { 2 } \omega ^ { - 1 } = 1 \times 1 0 ^ { - 1 1 } \omega ^ { - 1 }$ 。对中心频率为1.5GHz压控振荡器进行测量，可以得出其相位噪声谱密度为： $\mathsf { S } _ { \varphi r v } ( \omega ) = h _ { - 1 v } \omega ^ { - 3 } = 6 . 1 9 1 8 \omega ^ { - 3 }$ 。

将近似值代入最优环路带宽计算公式。得到环路带宽值为 $6 2 . 8 mathsf { K H z }$ 。

为了验证环路带宽计算公式近似值的正确性[1]，我们采用直接测量法来选取最优环路带宽。使用该方法时候，首先分别测量输出相位噪声中低通型和高通型相位噪声功率谱曲线[12]，然后将其相交点出的频率与计算公式所得到的值进行对比即可。当把锁相环路带宽设置很宽，则在环路带宽内测得的绝大部分是低通型噪声的功率谱曲线。而将环路带宽压的很窄，测量的环路输出相位噪声就是高通型的相位噪声的功率谱曲线[13]。如图(a)和(b)给出了环路带宽为300KHz 和环路带宽3Khz 时锁相环路输出频率相位噪声，其特点是当环路带宽处于两者交叉点的时候，环路带宽为最优环路带宽，而此处的环路带宽近似看作为63KHz。为了说明该环路更具有说明性，将锁相环环路带宽值设置为65KHz，如下图(c)所示。为进行对比说明，将实测结果进行对比，如图3所示。

![](images/461c9467cf064219e645c3cbebcb0cddde2d53e396590f46d2b233506a5b7c22.jpg)  
图2实际测试相位噪声  
Fig.2The actual test of phase noise

![](images/5fef3bbe2adb67bbb28eaea4586e55b4d04ff54e1a893667898074a326b3c623.jpg)  
图3实际测试相位噪声对比  
Fig.3 The contrast actual test of phase noise

经验证锁相环路最优环路带宽取值与计算公式所求值近似相等。实际测量压控振荡器相位噪声谱密度测量误差通常较大[14]，因此交点处的取值为近似取得，但不影响环路最优带宽取值判断。

# 5结束语

锁相环频率合成器的最优环路带宽是提高信号质量的有效措施[15]。通过对基于 PE3236芯片的锁相环频率合成器输出相位噪声的测试和结果分析，表明锁相环频率合成器最优环路带宽计算公式理论值和实际测试值比较吻合。因此按照最优环路带宽的计算公式所取的最优环路带宽值完全可以用于一些设备本振频率源的环路带宽值的选取。

实验中发现，晶振倍频后的相位噪声与集成锁相芯片内部相位噪声两者存在一定的差值。随着集成芯片行业不断发展，锁相频率合成器中集成锁相芯片内部噪声逐步被减弱，晶振的相位噪声在锁相频率合成器输出频率近端影响比较明显，呈现凸起现象。因此选取高性能的晶振对于频率合成器输出相位噪声有重要的作用。

# 参考文献

[1]远坂俊昭．锁相环电路设计与应用[M]．北京：科学出版社，2006:1-5.  
[2]张建斌．锁相与频率合成[M]．北京：科学出版社，2011:59-66.  
[3]郑继禹，张厥盛，万心平，等．锁相技术[M].西安：西安电子科技大学出版社，2012:5-70.  
[4]罗伟雄韩力原东昌，等.通信原理与电路[M].北京：北理工出版社，1999：30-55.  
[5]陈刚．锁相环路的相位噪声分析[J]．机械与电子，2009，15(3):112-113.  
[6]郭衍莹，刘兴术．微波锁相振荡器的相位噪声及其测量[J]．通信学报，1982，2(1):50-57.  
[7]郭衍莹．频率短期稳定度的测试及结果分析[J]．电子测量技术，1980，3(6):20-22.  
[8]王春晖，金小军，金仲和，等．锁相环中数字分频器对输出信号相位噪声和杂散的影响[J].  
宇航学报，2009，30(6):2334-2338.  
[9]李仲秋，曾全胜．锁相环相位噪声与环路带宽的关系分析[J].现代电子技术，2009,32(14):132-134.  
[10]吴文伟．选择低相位噪声频率合成器的最佳带宽[J].电信快报，2000，6(12):25-29.  
[11]王宇舟．三阶锁相环环路滤波器参数设计[J].电讯技术，2008,48(9):156-158.  
[12]袁雪林，张洪德，朱畅，等．一种改善频率合成器相位噪声的方法[J.现代雷达，2008,30(4):85-87.  
[13]蒲璞，崔庆林，蒲林．高速数字电路相位噪声测试研究[J].微电子学，2008,39(3):324-327.  
[14]百创．高性能低噪声锁相环分析与设计[D]．国防科学技术大学，2009.  
[15] Knight M F. lonospherie Seintillation Effects on Global Positioning System Receivers [D].  
Adelaide:TheUniversityof Adelaide,2000.

# 作者简介：

孙家星（1992一)，男，山东省德州市人，现为中国科学院大学硕士研究生，主要研究方向：射频电路设计。邮箱：sunjiaxingl4@mails.ucas.ac.cn

![](images/9300fc7d7279273c6275a25c446e0a2549a7c0594b91f4d0d2d7571f6863f415.jpg)