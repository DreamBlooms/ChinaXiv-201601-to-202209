Lomb-ScarglePeriodogram方法研究耀变体3C454.3长周期光变特性陆林，张皓晶，张欢，马凯旋(云南师范大学 物理与电子信息学院，云南 昆明 653092)

摘 要：本文从 SMARTS 数据库和之前文献中,收集了耀变体 3C 454.3(z = 0.859) ）光学波段B、V、R和红外波段J、K的数据,时间从2008年6月份到 2017年7月份之间近十年.分别获得了光学B波段891组、 $\mathsf { v }$ 波段855组、R波段877组、J波段860 组和K波段751组共4234 组数据.使用这些观测数据，用LombScargle Periodogram(LSP)方法和加权小波Z变换法(WWZ)研究了各个波段的周期,结果表明：(1)3C 454.3在光学和红外波段都有 454天的周期光变；(2)五个波段存在 454 天的长周期光变，由此得到 3C 454.3 中心黑洞质量为： $M \approx 0 . 2 4 \times 1 0 ^ { 6 } M _ { \mathrm { e } }$ 和辐射区半径为： $R \approx 3 . 6 8 \times 1 0 ^ { 8 } K m$ ;(3)通过长周期光变分析，预期耀变体3C454.3在2021年6月左右，将再次爆发。

关键词：蒙特卡洛模拟；加权小波Z变换；黑洞质量；辐射区半径中图分类号：P141.5 文献标识码：A 文章编号：

# 0引言

耀变体的多波段的光变时标是一个重要的物理参数，耀变体的长周期光变时标可以帮助我们研究天体的中心黑洞质量,内部结构,辐射区域等问题,目前研究此类问题的方法很多,有结构函数法,离散相关函数法(DCF),period4方法，功率谱(PSD),Jurkevich 方法,加权小波Z变换法(WWZ),LombScargle Periodogram(LSP)方法".由于天体的光学波段和红外波段的数据观测受天气设备等多种因素的影响，观测数据在时间序列上不连续,在光变周期的研究中引入了较大的误差,结果的精确度一直是该研究领域的热点问题.在文献[5]中对这个天体的光学和红外波段的数据都采用了功率谱(PSD)分析方法,也得到了与本文相同的结果，但是在功率谱方法中要求数据为等间隔，所以在文献[5]中对相邻的数据进行了平均插值处理,这样可能会对原始数据的真实性有所损害,还引入了人为主观的因素，而且还可能会带来其他叠加对周期的干扰.本文从SMARTS和文献[5]中收集到了耀变体3C 454.3（z = 0.859）[3]的准同时性光学波段近十年的数据.采用了LSP方法来对耀变体3C 454.3的非均匀数据进行分析,在LSP方法中则不需要对数据进行插值处理,但是在LSP方法的功率谱结果中可能会出现虚假的峰值,为了进一步的评估功率谱结果峰值的可信度,通过模拟大量光变曲线，并采用LSP方法计算模拟光变曲线的功率谱，对模拟光变曲线的功率谱结果进行抽样,估计出相应波段的置信度，通过置信度可以评估所出现峰值的可靠性,我们就可以得出更为准确的准周期，并且在分析结果中我们看到,所得到的周期就只一个，而没有其他的周期干扰,将这种模拟大量光变曲线的方法称作为蒙特卡洛模拟方法，为了验证蒙特卡洛模拟方法所得到结果的可靠性和可行性,我们采用这五个波段的数据,用加权小波Z变换(WWZ)方法进行长周期光变分析，[4]也得到相同的结果,并通过张雄等人文献中”标准差公式，计算相应波段的置信度,得出了可靠的准周期,从而验证了蒙特卡洛模拟方法所得到结果的可行性和准确性.在本文中首次将耀变体3C 454.3光学B,V,R和红外J,K波段的离散数据应用加权小波Z变换法(WWZ),和蒙特卡洛模拟方法来研究相应波段的光变周期,为耀变体的长周期光变的研究找到了一种新方法，

通过WWZ和蒙特卡洛模拟方法可以很好的得到非平稳信号的准周期，大大提高了相应周期的计算精度，从而得到更加准确的准周期.在这两种方法中我们得到了五个波段都存在约为454天的准光变周期.从长周期的研究中我们可以得到3C 454.3中心黑洞质量和辐射区半径，从而为活动星系核(AGN)的物理模型的研究提供重要参数

# 1观测数据和研究：

如图1所示的为来自于SMARTS数据库和文献[5]的耀变体3C 454.3光学B,R,V波段和红外J,K波段的数据所给出的光变曲线,横轴为儒略日(MJD),纵轴为星等值(MAG):

![](images/58f2b3bd97fd17d9635ce9cf091345e476346587bfc1e6a7959f10ff54c36bd2.jpg)  
图1： 红色的为光学B波段的光变曲线,橙色的为光学V波段的光变曲线,蓝色的为光学R波段的光变曲线,紫色的为红外J波段的光变曲线,黑色的为红外K波段的光变曲线

The red,orange,and blue,line represents a light curve in the optical B-Band,V-Band, R-Band,the pupre,and black line represents a light curve in the infrared J-Band,and K-Band,respectively.

采用流量与星等的转化关系,将以上的五个波段的星等值转化为流量值,公式如下[14]：

$$
F = 1 0 ^ { - { \frac { m } { 2 . 5 } } } \times 3 6 4 0 J y
$$

F为每一个波段所对应的流量值，单位为Jy，m为所对应波段的星等值.

# 1.1光变曲线的长周期分析：

从SMARTS 数据库和文献[5]中获得星等的数据之后,通过流量与星等的转化公式得到了各个波段的流量数据.接下来本文将采用蒙特卡洛模拟和加权小波Z变换法(WWZ)来计算各个波段的周期和各自的置信度.即用如图1所示的光变曲线数据获得流量数据之后,采用LSP方法得到相应的光变周期和蒙特卡洛模方法得到相应的置信度估计，为了检验蒙特卡洛模拟方法置信度评估的可行性和准确性,我们通过了加权小波Z变换法(WWZ),计算了相对应波段的光变周期,通过标准差公式,我们计算了相应的加权小波Z变换周期的置信度.

# 1.2应用LombScargle Periodogram(LSP)方法分析长周期光变:

计算隐藏在噪声中的周期性信号是天文数据时间序列分析中的一个重要目标.LSP 方法可以对非均匀采样的时间序列周期图进行相位修正处理，能够在一定范围内对非均匀采样的时间间隔引起的误报周期进行修正,并且LSP方法不要求数据是均匀的时间序列，不用对其进行插值，从而减少了人为因素对数据的干扰.因此,LSP 方法能很好的寻找隐藏在噪声中的准周期振荡光变.现在假定有这么一组时间序列 $\mathbf { \nabla } _ { X } ( \mathbf { \nabla } _ { t { } _ { j } } )$ ， $( j = 1$ ，2,$3 . \ldots \ldots \hat { M }$ ，则时间序列的 LSP 的功率谱由以下的公式所给出, $\mathrm { P } _ { x } ( \omega _ { j } )$ 以角

率 $( \omega _ { j } = 2 \pi \nu _ { j } )$ )为变量的功率谱函数,基本形式如下：

$$
P _ { x } ( \omega _ { j } ) = \frac { 1 } { 2 } \left\{ \frac { \displaystyle \sum _ { j = 1 } ^ { N } [ x ( t _ { j } ) - \overline { { x } } ] \cos \omega _ { j } ( t _ { j } - \tau ) } { \displaystyle \sum _ { j = 1 } ^ { N } \cos ^ { 2 } \omega _ { j } ( t _ { j } - \tau ) } + \frac { \displaystyle \sum _ { j = 1 } ^ { N } [ x ( t _ { j } ) - \overline { { x } } ] \sin \omega _ { j } ( t _ { j } - \tau ) } { \displaystyle \sum _ { j = 1 } ^ { N } \sin ^ { 2 } \omega _ { j } ( t _ { j } - \tau ) } \right\}
$$

这里的 $\overline { { x } } = \frac { 1 } { N } { \sum _ { j = 1 } ^ { N } } x ( t _ { j } )$ 为时间序列的平均值, $N$ 为数据的个数， $\tau$ 为相应的时间的相位修正：

$$
\tan ( 2 \omega _ { j } \tau ) = \frac { \displaystyle \sum _ { j = 1 } ^ { N } \sin ^ { 2 } \omega _ { j } t _ { j } } { \displaystyle \sum _ { j = 1 } ^ { N } \cos ^ { 2 } \omega _ { j } t _ { j } }
$$

对于图1的光变曲线是一个非均匀的时间序列,要得到里面所隐藏真实周期是非常困难的.采用以上的LSP 等式分析真实数据的功率谱结果,但是由于这些结果中会出现虚假峰值，使得我们很难判别真实的周期频率，所以为了解决这个问题我们需要对这些功率谱的峰值进行置信度的评估，

1.3蒙特卡洛模拟方法和置信度评估：

AGN 的功率谱一般呈红噪声幂律分布即： $\textit { P } \propto \textit { f } ^ { - \alpha }$ ,为了获得功率谱指数α，对所得到的功率谱结果取对数,并进行一元线性回归拟合,可获得功率谱指数α值.图2中的横坐标频率f的对数值,纵坐标为功率谱结果的对数值,红色直线为相应的一元线性拟合直线,图中直线的斜率为相应的功率谱指数α.

![](images/a8b995c802988a9cb04ab60f183406bb24c883496f3f7fe95db20acdb2a837e5.jpg)  
Fig.2 Logarithmic coordinate fittingof power spectruminoptical B,R,Vbands andinfrared J,K bands

通过以上的一元线性回归拟合,我们得到了光学和红外波段的各个幂律指数值α.基于功率谱指数α和真实数据,模拟了5000条光变曲线,对模拟的光变曲线使用LSP方法逐一进行计算,获得模拟光变曲线的功率谱结果,并对这些模拟光变曲线的功率谱结果进行置信度抽样,可得到各个波段不同的置信度曲线,最终将真实数据的功率谱和置信度曲线整合，即可得到准确的周期频率.

# 1.3LSP方法的置信度评估结果：

图3中分别为光学B,R,V波段,和红外J,K波段的蒙特卡洛模拟LSP 方法结果,图3中纵轴为相应波段的功率谱值,横轴为相应的频率 $\boldsymbol { f }$ ，单位为 ${ \mathsf { d } } ^ { - 1 }$ ,红色曲线代表了真实数据的功率谱结果，黑色的曲线代表了置信度为： $9 9 . 7 \%$ ，紫色的曲线代表了置信度为：$9 9 \%$ ，橙色的曲线代表了置信度为： $9 5 \%$ ，我们取超过置信度曲线 $9 9 . 7 \%$ 的峰值为所对应的周期频率,如图中黑色箭头所指的位置.

Fig.3 Confidence assessment results of optical B,R,V bands and infrared J,K bands

![](images/7950d18908b05ba5eed432557fb3c33da085497052ddb2cda1d0d95b6a8afd8b.jpg)  
图3光学BRV波段和红外JK 波段的置信度评估结果

![](images/71941ac8869e37f8945949d98b25453c363383a4872b106e79584be88d399d6f.jpg)

由图3我们看到了在光学B,R,V和红外J,K波段都只存在一个很明显的峰值超过了$9 9 . 7 \%$ ，如图3中箭头所指的位置，相应的峰值频率保留四位小数分别都为$f = 0 . 0 0 2 2 ( d ^ { - 1 } )$ .所以获得光学和红外波段都存在约为 454 天的周期,通过这样的方法我们得到了与之前文献[5]中相同的结果,并且通过这种方法不会引入其他干扰结果为了检验以上方法的可行性和准确性,我们通过了加权小波 Z变换法(WWZ)[1],计算了相应波段的周期.由于标准差和置信度的关系,我们计算了相应的加权小波Z变换功率谱的置信度,本文中采用通过之前文献[4]中所给出的正太分布的标准差公式.

# 2加权小波Z 变换法(WWZ) 分析长周期光变:

在经典的时间频率分析中一般采用傅里叶变换和小波分析方法,但是由于天文数据往往都是非等间距的离散数据,在使用傅里叶变换和小波变换来分析天文数据时需要对数据进行插值处理变成均匀的数据,这样对数据的真实性由很大的损害，并且在使用傅里叶变换来处理这些非等间距的数据时可能还会出现伪周期,所以在基于小波变换的基础上 Foster[17]提出了加权小波Z变换(WWZ),这样不仅可以更加有效的处理非等间距的时间序列的周期,还可以一定程度上的反应出周期的稳定性.加权小波Z变换是将时间序列投影到三个正交归一的基函数上，即 ${ } ^ { 1 } \phi _ { 1 } ( t _ { i } ) = 1 , \phi _ { 2 } ( t _ { i } ) = \cos \left[ \omega ( t - \tau _ { 0 } ) \right] , \phi _ { 3 } ( t _ { i } ) = \sin \left[ \omega ( t - \tau _ { 0 } ) \right]$ ,在投影上做了统计加权 $\omega _ { i } = \exp \left[ - c \omega ^ { 2 } ( t _ { i } - \tau _ { 0 } ) \right]$ ，将数据的不均匀通过权重调节,避免了周期分析时受到数据过密的影响,其中使用的母函数为 Morlet 小波[17],wWZ 的定义为:

$$
W W Z = \frac { ( N _ { e f f } - 3 ) V _ { y } } { 2 ( V _ { x } - V _ { y } ) }
$$

且这个等式的分子分母分别满足自由度为 $N _ { e f f } \mathrm { ~ - ~ } 3$ 和2的F分布.其中 $\mathit { N _ { e f f } }$ 为有效数据点个数， $V _ { x }$ ， $V _ { y }$ 分别为观测数据和模拟函数的加权变量，即：

$$
\mathrm { N } _ { e f f } \ = \frac { \displaystyle \left[ \sum \exp \left[ - 2 c \omega ^ { 2 } ( t _ { i } \ - \tau _ { 0 } ) ^ { 2 } \right] \right] ^ { 2 } } { \displaystyle \sum \exp \left[ - 2 c \omega ^ { 2 } ( t _ { i } \ - \tau _ { 0 } ) ^ { 2 } \right] }
$$

$$
V _ { _ x } = \frac { \displaystyle \sum _ { i } \omega _ { i } x ^ { 2 } ( t _ { i } ) } { \displaystyle \sum _ { \lambda } \omega _ { _ \lambda } } - \left[ \frac { \displaystyle \sum _ { i } \omega _ { i } x ^ { 2 } ( t _ { i } ) } { \displaystyle \sum _ { \lambda } \omega _ { _ \lambda } } \right] ^ { 2 }
$$

$$
V _ { _ { y } } = \frac { \displaystyle \sum _ { i } \omega _ { i } y ^ { 2 } ( t _ { i } ) } { \displaystyle \sum _ { \lambda } \omega _ { \lambda } } - \left[ \frac { \displaystyle \sum _ { i } \omega _ { i } y ^ { 2 } ( t _ { i } ) } { \displaystyle \sum _ { \lambda } \omega _ { \lambda } } \right] ^ { 2 }
$$

等式中 $c$ 为衰减因子, $\tau _ { \scriptscriptstyle 0 }$ 为时移, $\omega$ 为尺度因子, $\omega _ { \lambda }$ 0 $\langle \lambda = 1 , 2 , 3 , \ldots \ldots \mathtt { n } )$ 为对应的测试频率.

Fig.4 the WWZ analysis resultsand corresponding to periodic frequency in the从以上的WWZ结果图中可以得到在光学B,R,V和红外J,K波段左边彩图红色部位对应了右图的功率谱曲线所出现的峰值频率的位置为相应的周期频率的出现的位置,通过白噪声检验采用[4], $\sigma = \left( \sum _ { i = 1 } ^ { M } \delta _ { i } ^ { 2 } \bigg / M - 1 \right) ^ { 1 / 2 }$ ,这个等式对于正态分布的总体是成立的,等式中 $\delta _ { i } = m _ { i } - \overline { { m } }$ 为相应波段的每一个功率值， $\overline { { m } }$ 相应波段功率的平均值,M 为相应的离散功率谱个数，通过这个等式计算以上各个波段的功率谱的标准差，由于正太分布置信度与标准差的关系，我们可以获得各个波段的功率谱的置信度，采用3倍标准差所对应的置信度 $9 9 . 7 \%$ ，所以图4中右图的蓝色直线取3倍的标准差值.通过以上的结果各个波段周期频率出现的位置都为 $f = 0 . 0 0 2 2 ( d ^ { - 1 } )$ ，所以光学和红外都存在约为 454 天的周期.并且其置信度都超过了 $9 9 . 7 \%$ ,这个结果与上面的蒙特卡洛模拟LSP方法的结果一致.综上我们得到了耀变体3C 454.3在光学B,R,V和红外J,K波段的周期都为454天，

![](images/53155e4e2b0df0651f46b8d0893a44152e39ee13437985c8288fffb5738763d7.jpg)  
图4光学B,R,V波段和红外J,K波段的WWZ分析结果和相应的周期频率.

大约为1.244年.

# 3．3C454.3中心黑洞质量和辐射区域半径的估计：

# 3.1中心黑洞质量估计：

中心黑洞质量的研究也是人们极为感兴趣的,耀变体中心有一个超大质量黑洞，很多辐射现象是由中心黑洞所引起的.通过长时标光变能够获得中心黑洞的质量，假设由薄吸积盘理论引起的长周期光变,那么由之前文献中[的公式:

$$
t _ { b u r t s } = 4 . 5 2 \beta _ { 0 . 1 } ^ { - 0 . 6 2 } M _ { 6 } ^ { 1 . 3 7 } y r s
$$

等式中， $\beta$ 为黏度参数， $M _ { \mathrm { 6 } } ~ = ~ M \big / 1 0 ^ { 6 } M _ { \mathrm { e } }$ 为中心黑洞质量约化单位,吸 积 率 $\dot { M }$ 和广义应力张量参数 $\mu$ ，当 $\mu = 0 . 5$ ， $\begin{array} { r } { \stackrel { \mathrm {  ~ g ~ } } { M } = \left. M _ { E } \right/ \varepsilon } \end{array}$ $M _ { \scriptscriptstyle E }$ 是爱丁顿吸积率， $\varepsilon$ 是吸积效率.爆发时间间隔主要取决于 $\mu$ ．Horiuchill 和 Kato(1990)建议到 $\mu = 0 . 5$ 时,磁场的逃逸速率会更低.此时,热极限周期时间为tcyc= 2tburts：

$$
t _ { _ { c y c } } = 9 . 0 \beta _ { 0 . 1 } ^ { - 0 . 6 2 } M _ { 6 } ^ { 1 . 3 7 } y r s
$$

等式中 $\beta _ { 0 . 1 } = \beta / 0 . 1$ ，所以当 $\beta = 0 . 1$ ， $\mu = 0 . 5$ ， $M = 0 . 2 M _ { C }$ ，时我们采用五个波段的1.244年的周期得到中心黑洞的质量约为: $M \approx 0 . 2 4 \times 1 0 ^ { 6 } M _ { \mathrm { e } }$ .这个结果是由于利用薄吸积盘理论的分析方法,没有考虑到黑洞的自旋的影响,所以比一般的平谱射电类星体的中心黑洞质量偏小.

# 3.2辐射区半径：

对于耀变体的长周期光变的现象，目前还没有最佳的物理模型解释,现有的理论为双黑洞模型[8]，薄盘的热不稳定性模型[8],和螺旋喷流等模型[9].如果是薄盘不稳定性造成的，可从所搜集的数据中获得各个波段的星等变化情况：

表格1.每个波段的幅值变化  
Table 1.the variation of magnitude in each band.   

<html><body><table><tr><td>Wavebands</td><td>MaximUm</td><td>Minimum</td><td>Difference</td></tr><tr><td>B</td><td>17.337</td><td>13.946</td><td>3.373</td></tr><tr><td>V</td><td>16.756</td><td>13.448</td><td>3.308</td></tr><tr><td>R</td><td>16.585</td><td>12.97</td><td>3.615</td></tr><tr><td>J</td><td>15.092</td><td>11.012</td><td>4.08</td></tr><tr><td>K</td><td>15.017</td><td>9.188</td><td>5.829</td></tr></table></body></html>

由以上表格1,可以看见,在光学和红外波段都具有较为剧烈的变化，并且红外波段的变化幅度比光学波段的变化更加剧烈.采用薄盘不稳定性分析长周期T[8]，通过长周期 T[8]可

以确定出热不稳定性产生的区域[8],等式如下[8]：

$$
T = 3 . 2 \times 1 0 ^ { - 4 } \beta ^ { 2 } ( x ^ { \frac { 1 } { 2 } } ( x - 1 ) M _ { 8 } ) y r s
$$

等式中 $x = \left. R \right/ R _ { g } , R _ { g }$ 为相应的施瓦西半径, $\beta$ 为黏滞系数, $\mathrm { \Delta M _ { 8 } ~ = ~ M / 1 0 ^ { 8 } M _ { \odot } }$ .这里我们取： $T \approx 1 . 2 4 4 y r s$ ，中心天体黑洞质量为： $M \approx 0 . 2 4 \times 1 0 ^ { 6 } M _ { \mathrm { e } }$ .所以我们得到辐射区域半径为: $R \approx 3 . 6 8 \times 1 0 ^ { 8 } K m$ ·

# 4.结果

对耀变体3C 454.3的光学波段和红外波段的研究中,本文采用了LSP方法得到了各个波段的周期并评估了所出现的峰值频率的置信度,得到了更为可靠的结果,并采用了WWZ 方法验证蒙特卡洛模拟评估置信度方法的结果,我们发现了：

(1）两种方法都在光学B,R,V 波段和红外J,K 波段发现了454天,约为1.244年的光变周期,通过蒙特卡洛模拟评估置信度方法,我们清楚的看到了对于五个波段都只有一个峰值频率超过了 $9 9 . 7 \% $ ，并且没有引入其他干扰结果.而为了进一步的验证这种方法的可行性,我们对这五个波段采用了WWZ的分析方法,也得到了与蒙特卡洛模拟方法一致的结果，都为454天，约1.244年.

(2）对于中心的超大质量黑洞,通过之前文献所给出的长周期与黑洞质量的公式,结合了本文中的五个波段共同的长周期数据我们得到了中心黑洞的质量为： $M \approx 0 . 2 4 \times 1 0 ^ { 6 } M _ { \mathrm { e } }$ ,这个结果由于是利用薄吸积盘理论的分析方法,没有考虑到黑洞的自旋的影响,所以比一般的平谱射电类星体的中心黑洞质量偏小,辐射区半径为： $R \approx 3 . 6 8 \times 1 0 ^ { 8 } K m$ ,计算所得到的辐射区半径相比之前文献[°所给出的辐射区半径在相应的施瓦西半径下要小,由于之前文献[10]中所采用的黑洞质量要比本文中所用的黑洞质量大，所以此处我们所得的辐射区半径是合理的，  
(3）通过以上的计算,我们预期耀变体3C 454.3在2021年6月左右,将再次爆发.我们将用云南天文台丽江的2.4米光学望远镜做进一步实测验证我们的结果.为用蒙特卡洛模拟方法研究耀变体的长周期光变寻求观测证据.

致谢：真诚致谢 SMARTS 团队和吴月承等人在文献［5]中所提供的光学和红外的星等数据.

# 参考文献:

[1] Foster G .Time Series Analysis by Projection. I. Statistical Properties of Fourier Analysis[J].Astronomical Journal,1996,111(1):541.   
[2]Rejkuba M, Minniti D, Silva D R.Long period varibles in NGC 5128-1.catalogue[J].Astronomy and Astrophysics,2003,406(1).   
[3]Sarkar Arkadipta et al. Multiwaveband quasi-periodic oscillation in the blazar 3C 454.3[J].Monthly Notices of the Royal Astronomical Society, 2020, 501(1) : 50-61.   
[4]Zhang X, Zheng Y G ,Li Z,et al. Optical CCD Photometry of the Variability of the BL Lacertae object ON231 in a Low State[J].Publications of the Astronomical Society of Japan,2008(2):145-160.

[5]吴月承,张皓晶,等.平谱射电类星体 3C454.3 的中长周期光变特性研究[J].天文研究与技术,2020,17(01):1-7.

Wu Yuecheng,Zhang Haojing,et al.The Medium and Long Period Light Variation Characteristics of FSRQ 3C 454.3[J]. Astronomy Research and Technology,2020,17(01):1-7.   
[6]Ren G W,Zhang H J,Zhang X ，et al. Detection of a high-confidence quasi-periodic   
Oscillation in radio light curve of the high redshift FSRQ PKS J0805-0111[J]. 2O20,21:075   
[7]Zhang X,Xie G Z,Bai JM .A historical light curve of 3C 345 and its periodic analysis[J]. Astronomy &Astrophysics,1998,330(2):469-473.   
[8]Wallinder FH,Kato S ，Abramowicz M A .Variability of the central region in active galactic nuclei[J].Astronomy & Astrophysics Review,1992,4(2):79-122.   
[9] Valtaoja E,Tersranta H,Tornikoski M,et al.Radio Monitoring of OJ 287 and Binary Black Hole Models for Periodic Outbursts[J]. Astrophysical Journal,2008, 531(2):744.   
[10]袁聿海.Blazars的中心黑洞质量[J].广州大学学报(自然科学版),2012,11(03):32-38. YUAN Yu-hai. The central black hole of blazars[J]. Journal of GuangzhouUniversity(Natural Science Edition),2012,11(03):32-38.

Studying the properties of long-period light variation about blazar 3C 454.3 with the methods for Lomb-Scargle Periodogram Lu Lin， Zhang Hao-Jing Zhang Huan， Ma kai-Xuan (Department of Physics,Yunnan Normal University,Kunming 65oo92,China)

Abstract: In order to study some feature of optical and infrared radiation in this paper. The data are collected from SMARTS dataset and other literature about blazar 3C 454.3( $\scriptstyle \cdot = 0 . 5 8 9 ,$ ),which are the optical bands B,V,R and infrared bands J, K.The data covered from June 2OO8 to July 2017 about decade, were obtained with 891 groups in B-band, 855 groups in V-band,877 groups in R-band,86O groups in J-band, and 751 groups in K-band, there are 4,234 points of data. Using the observed data, we employ LombScargle Periodogram (LSP) and The Weighted Wavelet Z-Transform(WWZ) method to study the possible periods in each band, the results show that: (1) There is a period of 454 days in both optical and infrared bands of 3C 454.3 ; (2) Using a period of 454 days,we obtain the mass of black hole about the 3C 454.3,approximate

to $: M \approx 0 . 2 4 \times 1 0 ^ { 6 } M _ { \mathrm { e } }$ andthe radius of radiation region: $R \approx 3 . 6 8 \times 1 0 ^ { 8 } K$ m.(3)Through these analyses, the blazar 3C 454.3 will burst out again around June 2021.

Key words: Monte Carlo Simulation, The Weighted Wavelet Z-Transform, the mass of black hole,Radius of radiation region