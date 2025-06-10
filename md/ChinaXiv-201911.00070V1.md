# LHAASO一MD光电倍增管的性能测

#

吴文雄1²，左雄²，肖刚²，张毅²，贾焕玉¹,王辉1

（1.西南交通大学，成都611756;2.中国科学院高能物理研究所，北京100049）摘要：高海拔宇宙线观测站（LHAASO）的核心科学目标是探索高能宇宙线起源以及相关的宇宙演化、高能天体运动和新物理前沿的研究。通过大面积铺设 $\mu$ 子探测器（MD）极大的压低宇宙射线背景，从而提高高能伽马射线探测的灵敏度。作为MD的核心部件之一的光电倍增管（PMT）负责接收水中的切伦科夫光子并将其转换成电信号输出，因此PMT的性能好坏直接影响MD的性能。稻城实验室 $2 \%$ 抽样测试结果表明PMT的各性能达到MD的指标要求，与批量测试结果的相对偏差小于 $2 \%$ 。

关键词：光电倍增管；高海拔宇宙线观测站；测试中图分类号：TN152文献标识码：A

# 1引言

针对当前宇宙射线研究的核心问题，我国物理学家提出了高海拔宇宙线观测站计划，用来探索高能宇宙射线起源，全天区扫描伽马射线源以及洛伦兹不变性破坏、暗物质和量子引力等新物理[1]。正在中国四川省稻城县海子山建设的高海拔宇宙线观测站是一个混合地面探测器阵列，主要由三部分组成：1平方公里地面簇射粒子阵列（KM2A），面积达到78000平方米的水切伦科夫探测器阵列（WCDA）和广角切伦科夫望远镜阵列（WFCTA）［2」。

其中KM2A包括5195个电磁粒子探测器(ED)和1171个 $\mu$ 子探测器(MD）。光电倍增管作为MD的核心部件，在安装前必须对MD光电倍增的性能进行测试，主要测试 PMT 的单光电子谱、高压响应、非线性、暗噪声计数率等[3」。而 MD 中的1171支PMT需要在中国科学技术大学进行批量测试，挑选PMT 满足的指标要求为PMT 在工作高压下的增益为 $2 \mathrm { x } 1 0 ^ { 6 }$ ；工作高压下的单光电子谱峰谷比要大于2；暗噪声计数率在 $2 \mathrm { m v }$ 值下要小于 $5 ~ \mathrm { k H z }$ ；阳极电流的非线性大于 $2 5 ~ \mathrm { m A }$ ；阳极等效电流大于或等于 $1 . 6 \mathrm { ~ A ~ }$ 。为了验证科大测试的结果和处于高原上PMT性能是否正常，因此需要在四川省稻城县海子山上跟中国科学技术大学测试条件几乎相同的情况下对PMT进行抽样测试，一方面要满足上述的指标要求，另一方面要跟中国科学技术大学批量测试数据的相对偏差，也即系统误差保持在 $2 \%$ 以内。

# 2测试平台搭建

PMT 的性能主要包括单光电子谱，高压响应，暗噪声及线性度等各种参数，为了研究PMT 的性能，搭建了基于VME/NIM混合总线机箱及其插件的测试平台，其中主要的插件有扇入扇出（N625），16通道的组合放大器（N979B），8通道的前沿甄别器（N842），双量程16通道的电荷转换器（V965），32通道的计数器（V830），8通道的波形数字转换器（V1751）。如图1是PMT各性能的测试框图。

单光电子谱测试过程是用信号发生器产生两路同步信号，一路使LED灯发光，然后LED灯在距离PMT光阴极 $1 0 \ \mathrm { c m }$ 处直射在其光阴极上，PMT阳极产生的信号经过10倍的放大器后经示波器上观察服从泊松分布后接入QDC 测试通道；另一路为标准的 NIM信号经扇入扇出后作为触发门信号接入QDC。

高压响应测试过程与单光电子谱的测试方法一样。

暗噪声测试过程为处于暗箱中的PMT在工作高压的条件下工作半个小时，此时 PMT暗噪声计数率波动很小，后将PMT阳极信号放大10倍，接入甄别器设置 $2 \mathrm { m V }$ 阈值，然后过阈的信号送入计数通道，测试单位时间内过阈的信号数目。

阳极与打拿极幅值比的测试是用信号发生器产生两路同步信号，一路激励LED灯发光，LED 光源经光纤传输后照射在PMT光阴极上，PMT 阳极产生的信号经衰减器衰减2倍后接入FADC测试通道，打拿极的信号经放大器放大10倍后接入FADC测试通道;另一路为标准的NIM信号作为触发门信号接入FADC。

阳极的非线性测试过程为经信号发生器激励光源发出的光经过两路独立的光纤照射在光电倍增管的光阴极上，使LED1和LED2 单独发光和同时发光，PMT 阳极的输出信号经衰减器后接入FADC，另一路为标准的NIM信号接入FADC。打拿极的非线性与阳极不同的就是PMT 打拿极的输出信号直接接入FADC[4]。

![](images/3c5616765463d0aec24db57d7967efbce3d6475ae55855dbea11e1b5aff2d21e.jpg)  
图1PMT测试框图

# 3 插件标定

为了对PMT 的精确测量，需要对一些关键插件进行标定，其中标定的插件主要有电荷转换器V965，波形数字转换器V1751与放大器N979B。

V965 的标定为信号发生器调出两路同步信号，第一路为标准NIM信号经扇入扇出作为触发门信号接入V965；第二路为 $5 0 \mathrm { n s }$ ， $- 5 0 \mathrm { m V }$ 的波形经过扇入扇出接入V965测试通道进行测试，然后将这两路信号接入高精度的示波器上取波形分析电荷量。

V1751的标定为信号发生器调出两路同步信号，第一路为标准NIM信号作为触发门信号接入V1751；第二路为 $5 0 \mathrm { n s }$ ， $- 5 0 \mathrm { m V }$ 的波形同时接入V1751测试通道进行测试，然后将这两路信号接入高精度的示波器取波形分析幅值。

N979的标定为信号发生器调出 $5 0 \mathsf { n s }$ ， $- 1 0 0 \mathrm { { m V } }$ 的波形接到高精度示波器上，从示波器上取波形分析幅值，之后将此信号接入N979 后再接到示波器上分析幅值。

下表为插件V965，V1751和N979B 的标定数据。其中N979B有两种放大倍数和每个通道分别有1、2两个输出。

表1插件标定的数据  

<html><body><table><tr><td>插件</td><td colspan="2">通道</td><td>Gain</td></tr><tr><td rowspan="3">V965</td><td rowspan="3">00</td><td>High range</td><td>0.2347±0.004pC/ADC count</td></tr><tr><td>Low range</td><td>0.02946±0.0005pC/ADC count</td></tr><tr><td colspan="2">00</td><td>1.024±0.04mV/ADC count</td></tr><tr><td>V1751 插件</td><td colspan="2"></td><td></td></tr><tr><td rowspan="4">N979</td><td rowspan="2">00</td><td>通道 1</td><td>放大倍数 1.93±0.01</td></tr><tr><td>2</td><td>1.96±0.01</td></tr><tr><td rowspan="2">08</td><td>1</td><td>10.2±0.05</td></tr><tr><td>2</td><td>9.98±0.05</td></tr></table></body></html>

# 4测试结果分析

通过在稻城海子山用VME/NIM混合机箱对LHAASO—MD 光电倍增管进行抽样测试，一方面可以检验MD挑选PMT的指标要求是否合格，一方面也可以与中国科学技术大学批量测试数据进行对比。

# 4.1光电倍增管的性能分析

# 4.1.1单光电子谱

为了精确测量PMT 的单光电子谱，将LED光源调节到足够弱，使得PMT基本处于单光子照射下。实验测量的数据分布如下公式：

$$
S ( x ) = { \frac { e ^ { - p 1 } } { \sqrt { 2 \pi } p ^ { 3 } } } \exp \left[ - { \frac { ( x - p 2 ) ^ { 2 } } { 2 p { 3 } ^ { 2 } } } \right] + \sum _ { n = 1 } ^ { 3 } { \frac { p 1 ^ { n } e ^ { - p 1 } } { n ! } } { \frac { 1 } { \sqrt { 2 \pi \mid n } p { 5 } } } \exp \left[ - { \frac { ( x - p 2 - n p 4 ) ^ { 2 } } { 2 n p { 5 } ^ { 2 } } } \right]
$$

式中，p1是泊松分布的期望值，代表测量的光信号的平均值；p2 和p3 是pedstal 电荷峰的平均值和标准方差； $\mathsf { p 4 }$ 和 p5 是单光电子电荷峰的平均值和标准方差。

![](images/9a9a9ad70a5ce132f19c0b2945bdca0af802b96da0da72588fada9f71c1d1acd.jpg)  
图2工作高压下单光电子谱

图2为PMT在1259.6V 电压下的单光电子谱,可以得出增益为 $2 . 2 2 \mathrm { x } 1 0 ^ { 6 , }$ ,峰谷比为2.5,能量分辨率为 $33 \%$ 。

# 4.1.2高压响应

光电倍增管的高压响应曲线反应了PMT的增益随所加高压变化关系。实验中采用高压响应曲线测量法，测量PMT输出电荷和所加高压关系，光电倍增管的增益G对工作高压V的变化有如下公式：

$$
G = A \bullet V ^ { \{ \ u { \ u { \ u { \ u { \ u } } } \ u { \ u { \ u { \ u { \ u } } } } } \ v { \ u } \} }
$$

下图为光电倍增高压响应曲线图，横坐标为取对数的高压，纵坐标为取对数所对应的电荷值，从图上可以得出PMT的beta值为6.867。

![](images/d754d06af03e15520903b39a37d8486b1084586f2269d942e0634f3a7cfb0ba6.jpg)  
图3高压响应曲线

# 4.1.3暗噪声

下图为PMT暗噪声计数率，横坐标为阈值，纵坐标为暗噪声，可以看出随着阈值的上升，暗噪声在不断的下降，而在 $2 \mathrm { m V }$ 阈值下的暗噪声为 $3 3 1 8 \mathrm { H z }$ ，满足MD挑选光电倍增管为 $2 \mathrm { m V }$ 下暗噪声要小于 $5 \mathrm { K H z }$ 。

![](images/3c56851812ed62cd085e245c87e3b764c965bd9bbefd07162181d8cadd897926.jpg)  
图4暗噪声

# 4.1.4阳极和打拿极的幅值比

下图为阳极和打拿极的幅值比，横坐标为打拿极的幅值，纵坐标为阳极的幅值，他们的幅值比是139.4。

![](images/51017271133f869f3525809200b0907fd5fd6511b420e73c8aa12c0bd3ec6065.jpg)  
图5阳极和打拿极的幅值比

# 4.1.5非线性

图6分别为阳极和打拿极非线性的测试结果图，横坐标为两个LED灯单独发光的电流之和，纵坐标为非线性，设置非线性指标 $5 \%$ ，由图可以得出阳极的非线性为 $3 1 . 4 \mathrm { m A }$ 打拿极的非线性为 $1 3 ~ \mathrm { m A }$ ，因此得出阳极的等效电流为1.81A，满足阳极非线性大于 $2 5 ~ \mathrm { m A }$ ，等效电流大于或等于 $1 . 6 \mathrm { A }$ 。

![](images/f4ef2dffc39fce985434f739004ab36c44f7f81bc574320dfadf4f30b7a8777a.jpg)  
图6阳极和打拿极的非线性

# 4.1.6 小结

综上PMT性能测试可以得出达到了MD挑选PMT的指标要求。

# 4.2批量数据对比

本次在四川省稻城县海子山上抽样测试了20支PMT 的性能，每只PMT 性能都达到了MD 的指标要求。下图为稻城海子山批量测试数据与中国科学技术大学测试数据的相对偏差即（ $\bf V _ { \mathrm { - d } } \mathrm { - } \mathbf { V } _ { \mathrm { - k } }$ ） $/ \mathrm { V _ { - k } }$ ， $\mathrm { \Delta V _ { - d } }$ 为稻城海子山测试的数据， $\mathrm { v _ { \mathrm { - k } } }$ 为中国科学技术大学测试的数据。

下图中，图7-10 四幅图的横坐标分别为工作高压，阳极非线性，阳极和打拿极的幅值比，等效阳极电流与科大测试的相对偏差，纵坐标为事例计数，各参数的相对偏差平均值均小于 $2 \%$ ，两套测试系统间的系统偏差较小；稻城测试系统测量误差小于 $4 \%$ ，中国科学技术大学测试系统测量误差小于 $3 \%$ ，其相对偏差的测量误差估算结果为小于 $5 \%$ ，与图中测试结

果相符。

![](images/c373ba7075fa0be9ce40716f11f22a0681ce1ca3131263ba8d6161a21fa40bc1.jpg)  
图7工作高压的相对偏差

![](images/0904d72fc1d5f4f40fd7c69412a761261736e2834c4c555de03a8e6ccb410578.jpg)  
图8阳极非线性的相对偏差

![](images/fea53450fcfc8f2c20adb68be7b5e96588cb7500067739a7dafc275c49ee86a9.jpg)  
图9阳极和打拿极比值的相对偏差

![](images/c8dbc5f5ee7eaaf0b222b46e468d28e2a49361b691c46c8542520d2b7e14d3e3.jpg)  
图10等效阳极电流相对偏差

下图11-12分别为暗噪声和峰谷比的对比，横坐标为光电倍增的编号，纵坐标分别为对应的暗噪声和峰谷比，可以看到在海子山测试的暗噪声相对中国科学技术大学的基本要大，而峰谷比相对中国科学技术大学的要小，主要的原因是海子山上测试环境相对中国科学技术大学实验室测试环境要差，各种施工，测试用的电，宇宙线干扰等等。但是从图上也可以看出在 $2 \mathrm { m v }$ 的阈值下暗噪声小于 $5 \mathrm { k H z }$ ,峰谷比都大于2，也满足MD挑选光电倍增管的需求。

4000 科大→稻城608 3318   
3500   
3000 2324241 2280 2098 1969   
2000 1501680 127/362 12   
1500 1117 914909 946 858800 874826 826   
1000 2 4 573 536 483 298 258   
500 0 8080S G 183545 808845 444044 S42 S4545 S5335S S/4 442 553555 S33355 533545 5 35444 Photomultiplier tube number

![](images/52f88f3c8185e23e519945890888b87df3fea8295875c5011bc039afe07f751c.jpg)  
图11 暗噪声的对比  
图12峰谷比的对比

因此可以得出稻城海子山上抽样测试的PMT的性能一方面满足MD 的指标要求，一方面与中国科学技术大学的相对偏差小于 $2 \%$ 。

# 5结论

通过搭建了基于VME/NIM混合总线机箱及其插件的测试系统，并对其一些关键插件进行标定，得到这些插件的精确的参数，最后用这套测试系统在稻城海子山上对LHAASO—MD光电倍增管性能进行抽样测试，验证了大尺寸光敏探头的性能一方面达到

MD 的指标要求，另一方面与中国科学技术大学测试的批量数据对比的相对偏差小于 $2 \%$ 。

# The performance test of LHAASO-MD photomultiplier

Wenxiong $\mathrm { W u } ^ { 1 2 }$ , Xiong $\mathrm { Z u o } ^ { 2 }$ ,Gang Xiao², Yi Zhang², Huanyu Jia1,Hui wang

(1.Southwest Jiaotong University, ChengDu 611756;

2.Institute of High Energy Physics,Chinese Academy of Sciences,Beijing 100049)

Abstract:Exploring the origins of high-energy cosmic rays and related cosmic evolution, high-energy celestial movements,and new physical frontiers is the uppermost scientific objective of the large high altitude air shower observatory (LHAASO).The large-area moun detector (MD) immensely reduces the background of cosmic ray,which can greatly enhance the sensitivity of high-energy gamma ray detection.A photomultiplier tube (PMT), one of the vital components of the MD,is responsible for receiving Cherenkov electrons in the water and converting it into an electrical signal output, which would directly affects the performance of MD.The metrical results of $2 \%$ samples from Daocheng Lab show that the performance of PMT meets the requirements of MD,and the relative deviation from the batch test results is less than $2 \%$

Keywords:PMT;LHAASO;measurement

# 参考文献：

[1]ZenC.Afutureprojectattibet:thelrgeighaltitudeairshowerobservatory(LAAO)[J].inesePsicsC1,4(2):49[2]左雄．博士论文-LHAASO-KM2A 缪子探测器设计与性能研究[J].2015.  
[3]王旭.LHAASO-KM2A 中光电倍增管的性能研究与批量测试[D].济南：山东大学,2012.  
[4]赵晓坤.LHAASO 实验中大动态范围光电倍增管性能研究[D].中国科学技术大学,2017.