# 基于WCDA水质监测分析\*

纪方12,3，张健欣1,3\*，陈明君²，李会财

（1.内蒙古工业大学电力学院，内蒙古呼和浩特010080;2.中国科学院高能物理研究所，北京100049；3.内蒙古机电控制重点实验室，内蒙古呼和浩特010051)

摘 要：水切伦科夫探测器阵列(WCDA)是高海拔宇宙线观测站(LHAASO)的主体探测之一，水作为探测器的唯一探测介质，水的洁净度将直接影响探测器对切伦科夫光的探测效率。为保证WCDA物理目标的实现，水衰减长度的实时测量和监测至关重要，是探测器正常运行和标定的关键工作之一。本实验分别介绍了水衰减长度测量装置和紫外可见分光光度计的工作原理，并通过不同波长的LED对各种样品水进行测量，将两种方法的数据结果进行对比分析，找出了两种装置的测量误差分别为$0 . 2 2 \mathrm { m }$ 和 $1 0 . 1 8 \mathrm { m }$ ，以及工业指标吸光度与科研指标水衰减长度之间的对应关系，并为GEANT4模拟确定了一种Querr水质模型，进一步推进了模拟的真实化。通过对WCDA一号水池水衰减测量装置的验证及从注水到稳定运行期间的水质监测的数据研究，总结了一套稳定可靠的水质监测方案，为二、三号水池的监测工作奠定了良好的基础。

关键词：LHAASO；水质监测；水衰减长度；吸光度中图分类号：TN152;X832 文献标识码：A

# 1引言

LHAASO-WCDA 实验的主要物理目标是实现甚高能伽马天文的全天候的观测，其中包括甚高能伽马源的探测与监测、能谱测量以及扩展形态的研究[1]。WCDA的总面积为 78,000 平方米，有效水深 $\scriptstyle 4 \mathrm { m }$ ，由3 个水池构成，共需要 350.000吨净化水。每个水池中被黑色隔光帘分隔成多个探测器单元，共3,120 个单元，每个单元大小为 $5 \mathrm { m } { \times } 5 \mathrm { m }$ 。在1号水池的每个单元底部中心位置安装一支光阴极朝上的8英寸PMT,用于接收广延大气簇射的次级粒子在水中产生的切伦科夫光。根据每个PMT上接收到的光子数目和光子到达时间，重建出原初粒子的簇射芯位、能量和方向[2]。在每个8英寸PMT旁边铺放置了一个1.5英寸的PMT，是用于扩大簇射芯区可测量的动态范围，从而实现高能宇宙线的高精度测量[3]。

水作为WCDA 探测器的关键探测介质，对长期运行的探测器阵列实验至关重要，水的衰减长度直接影响探测器的探测效率，水衰减长度越大，表示水质越好，光探测效率越高。不同实验对水质的要求也不近相同。CHIPS 实验中测量切伦科夫光的衰减长度随滤光时间的变化，研究了 $4 0 5 \mathrm { n m }$ 激光的透射特性，衰减长度高达 $1 0 0 \mathrm { m } ^ { [ 4 ] }$ 。中国大亚湾中微子实验中水的衰减长度要求为 $3 0 \mathrm { m }$ 以上[5]。LArTPC 探测器实验中测量出液氩中参杂的氮气分子与闪烁光之间的反应截面为 $( 7 . 1 4 { \pm } 0 . 7 4 ) { \times } 1 0 ^ { - 2 1 } \mathrm { c m } ^ { 2 }$ ·molecule¹。百亿分之二（ppm 水平）的掺杂浓度对应的衰减长度为 $3 0 \mathrm { m } \pm 3 \mathrm { m } ^ { [ 6 ] }$ 。KM2A 缪子探测器[7]（MD）组自行研制了一种测量装置，在 $8 \mathrm m$ 长的水箱中，安装多光源，达到快速测量水衰减长度的目的。通过对山上超纯水水样以及不同水质水样进行测量，验证该装置在 $1 0 0 \mathrm { m }$ 衰减长度的测量精度可以达到 $2 0 \% [ 8 ]$ 。

水衰减长度测量方法中，采用的是一种简便易行的直筒式的测量方法，通过改变测量装置中水位的高低来改变光在不同光程下的衰减，即可得到水样的水衰减长度[]。前期WCDA工程阵列样机实验中，通过数据研究分析，发现了一套利用单路计数能谱的第二个峰的峰位变化来监测水质的方法[10]。此方法需要结合直接测量装置的测量结果进行对比分析。GEANT4 模拟时需要给定不同波长下的水衰减长度参数，即需要给出一个和实验接近的水质模型，但通过调研得出 Smith 和Querry 两种水质模型[11]，需要通过测量确定一个合理的水质模型，为模拟提供可靠的参量。

本实验采用直筒式的测量方法得出一定波长下的水衰减长度，并同紫外可见分光光度计的测量结果进行对比，标定探测介质的衰减长度。并进一步通过不同波长LED的测量结果分析，为GEANT4模拟提供一组可靠的水质模型参数。

# 2水衰减长度测量装置

# 2.1测量装置的工作原理

水衰减长度测量装置是一个由LED灯、光筒、主水管、光电倍增管（PMT）组成的测量系统，在某一LED 波长下测量不同水位(h)的PMT接收的信号幅度 $A$ ， $A _ { 0 }$ 为LED的发光强度，根据水衰减长度定义λ：

$$
A = A _ { 0 } e ^ { - \mathrm { { h } } / \lambda }
$$

两边取自然对数得：

$$
\ln ( A ) = \ln ( A _ { 0 } ) + ( - h / \lambda )
$$

得到PMT接收到的信号幅值 $\ln ( A )$ 与水位高度 $\mathbf { h }$ 的线性关系，进而得到水样的 $\lambda$ 值，即斜率绝对值的倒数。

# 2.2 WCDA水衰减长度测量装置

如下图1所示为WCDA利用该测量原理设计的水衰减长度测量装置。测量步骤如下：第一，用待测水样自动清洗测量装置，以降低实验误差；第二，开启对应的电水阀和水泵开始注水，当水位达到 $1 . 1 \mathrm { m }$ 时，关闭电水阀和水泵，LED 和PMT 电源打开，PMT采集LED 的发光信号；第三，控制排水阀，改变测量装置中水的高度h，测量PMT接收到的信号幅值为A，记录保存实验数据；第四，根据水衰减长度计算公式拟合得到此水样的水衰减长度。

![](images/b830ba5f00cb3ce3755848b9acc2d7bd4693ab741ad2c52bb44ccd045534da6e.jpg)  
图1水衰减长度测量装置结构图  
Fig.1 Water attenuation length measuring device structure diagram

水衰减长度测量可以分为自动和手动测量两种方式。在慢控制系统的控制下，实现自动测量，单次水样测量每2小时完成一次，达到监测水质的目的。

# 2.3WCDA水衰减长度测量装置稳定性分析和测量结果

在正式测量之前，我们对该装置的稳定性进行了验证分析。利用该装置对水池内水的水质进行了27

日的监测，通过分析每日的数据误差，论证其系统测量稳定性。如图2为测量27日每日的测量误差，可以看出误差波动在 $0 . 2 2 \mathrm { m }$ 范围内，说明本装置测量稳定。

![](images/47ecc32ee46dc586f138e242146cc261714cace25e81d8eed82cb92f9daee4ae.jpg)  
图2水衰减长度测量装置测量误差

图3利用此装置测得在 $4 0 0 \mathrm { n m }$ 波长LED下水池水样的结果，图a为单次测量拟合得到的水衰减长度，测量误差小于 $3 \%$ ；图 $\boldsymbol { \mathbf { b } }$ 是长期测量结果，目前水池内的水质基本维持在 $7 . 5 3 \mathrm { m } \pm 0 . 2 1 \mathrm { m }$ ，总体测量误差小于 $5 \%$ 。

![](images/a1a2384409a3d3ca856e58c6b987984f8e5022bc82873c47f5ae306a34e98ed8.jpg)  
Fig.2Measurement error ofwaterattenuationlength measuring device   
图3测量装置测量结果  
Fig.3 Measuring device measuring results

为了和直接测量装置对比研究，本实验中还利用紫外可见分光光度计对同一水样进行测量，得出吸光

度和测量装置给出的水衰减长度的对应关系。

# 3紫外可见分光光度计工作原理

# 3.1紫外可见分光光度计工作原理

朗伯-比尔定律又称为光吸收基本定律。它表明物质对入射光产生吸收时，吸收强度与光程及吸收物质浓度之间的关系，是紫外吸收光谱和红外光谱定量分析的理论依据。

$$
A = \lg \left( I _ { 0 } / I \right) = \lg \left( 1 / T \right) = - \lg T = K C L
$$

其中 $A$ ：吸光度， $T$ ：透过率， $K$ ：吸光系数， $C$ ：样品浓度， $L$ ：光程， $I _ { 0 } / I$ ：入射光强度/透过光强度。

紫外可见分光光度计是由光源、单色器、样品室、检测器、放大控制系统和结果显示系统构成。本实验采用的是双光束，有两条光路和一个检测器，两条光路中分别放置参比和样品，光从单色器出来以后经斩波器，依次测定参比和样品。检测器是选用的光电倍增管，当它受到辐射照射后，吸收光子能量，并转变为可测量的物理量，将测试的样品结果显示保存在PC机上。该方法测量水样的吸光度是相对吸光度。

# 3.2WCDA紫外可见分光光度计

本次WCDA水质测量所使用的为安捷伦科技有限公司生产的Cary300型紫外可见分光光度计。首先打开电脑 Scan 软件和Cary300 设备，预热1个小时，再设置测量波长 $3 0 0 \mathrm { n m } { - } 7 0 0 \mathrm { n m }$ ，采样时间为0.2s，采样间隔为 $1 \mathrm { n m }$ ，样品室放入纯水样品进行基线校正，再进行对水样测量。各个水样经紫外可见分光光度计测量的结果是吸光度（Abs)，即：

$$
A b s = \lg ( I _ { 0 } / I )
$$

依据光的衰减遵从Beer定律，假定水的衰减长度为 $\lambda$ ，那么强度为 $I _ { \mathrm { 0 } }$ 的入射光通过 $L$ 长度的水样后的强度为：

$$
I = I _ { \mathrm { { 0 } } } { \bf { e } } ^ { - L / \lambda }
$$

分光计测量时 $L$ 取 $0 . 1 \mathrm { m }$ ，可计算出各个水样在每个波长下的水衰减长度为：

$$
\lambda { = } ( 1 / ( 1 0 A { \mathrm { b s } } \ln 1 0 ) )
$$

# 3.3WCDA紫外可见分光光度计

在正式测量之前，我们同样利用该装置对水池内水的水质进行了27日的监测，分析每日的数据误差，如图4为测量27日每日的吸光度转化为水衰减长度的测量误差，对该装置的稳定性进行了验证分析。可以看出误差波动在 $0 . 1 8 \mathrm { m }$ 范围内，说明本装置测量同样稳定。

![](images/e20a2b2cc37cb69cfd3a369bc1ec05307d986405eb155642444174cf20723931.jpg)  
图4紫外可见分光光度计测量误差  
Fig.4Measurement errorwithuv-visible spectrophotometer

紫外可见分光光度计在波长 $4 0 0 \mathrm { n m }$ 时测量各个水样吸光度如图5所示，纯水的吸光度基本为零，吸光度值越小，表明水样的透明度越高，水衰减长度数值越大。开始注水时，吸光度快速下降，是不断增加的水量对池水内污染物的稀释作用。循环站处理后的水的吸光度小于水池内水的吸光度，表明循环站处理有一定的净化水质的能力，但尚未达到设计要求。

![](images/20a1779da11b2ae22bcd7c25535197aa098b36a0e44d175427122074e149d2a5.jpg)  
图5紫外设备在 $4 0 0 \mathrm { n m }$ 波长下对不同水样的长期监测结果

Fig.5 Long-term monitoring results of different water samples at $4 0 0 \mathrm { n m }$ wavelength by ultraviolet equipment

# 4结果分析

由上述两种测量装置的测试误差分析可以看出，两种测量装置均仍存在一定误差，分析是由于目前WCDA水净化循环设备的不稳定，对测量的水样有影响。此外，紫外可见分光光度计测量时由于设备本身误差和每次取样时比色皿上会有不同程度不可避免的污染导致测量结果略微不同。但两种装置测量出的数据误差值都很小，均在可接受范围之内。随后我们利用两种装置对相同水样进行了测量及对比分析。

如图6是用水衰减长度测量装置在18日内对 WCDA水池内水的监测结果，水衰减长度是 $7 . 4 1 \mathrm { m } \pm$ $0 . 2 1 \mathrm { m }$ 。同时利用紫外可见分光光度计监测同一水样的结果经转化后，水衰减长度 $6 . 7 9 \mathrm { m } \pm 0 . 3 7 \mathrm { m }$ 。两种测量方法得到的水衰减长度结果在误差范围内是符合的。

![](images/d89f608107b4945310ec7ac1907f165e119a93e23cd129ca1b8bfb20516257c7.jpg)  
图6水池内水的水衰减长度  
Fig.6 The attenuation length of water in a pool

我们对两种装置测量出的数据进行了水质模型计算。下表1为通过水衰减长度测量装置和紫外可见分光光度计测量得到的水池内的水样在LED 波长 $3 6 5 \mathrm { n m }$ 、 $3 8 5 \mathrm { n m }$ 和 $4 0 0 \mathrm { n m }$ 下的水衰减长度，通过三个点得出水衰减长度与波长关系的斜率，分别是 $0 . 0 8 { \pm } 0 . 0 4$ 和 $0 . 1 0 { \pm } 0 . 0 2 \ \$ 。图7是水的吸收长度随波长的变化关系图，根据不同的实验结果，给出了两种水吸收长度模型。Smith 和Querry 水质模型的在相同条件下的斜率分别是 $0 . 7 9 \pm 0 . 0 5$ 和 $0 . 1 6 \pm 0 . 0 1$ 。两种装置测量出的数据计算出的斜率，均明确得出水池内水样更接近Querry 水质模型，因此GEANT4 模拟确定使用的水质模型为Querry水质模型。

表1测量数据  
Table.1measurement dat   

<html><body><table><tr><td></td><td>波长/nm</td><td>2/m</td><td>斜率</td></tr><tr><td rowspan="3">水衰减长度测 量装置测量 水池内水样</td><td>365</td><td>4.53</td><td rowspan="3">0.08</td></tr><tr><td>385</td><td>5.07</td></tr><tr><td>400</td><td>7.53</td></tr><tr><td rowspan="3">紫外可见分光 光度计测量 水池内水样</td><td>365</td><td>4.23</td><td rowspan="3">0.10</td></tr><tr><td>385</td><td>5.62</td></tr><tr><td>400</td><td>7.7</td></tr><tr><td rowspan="5">Smith 模型</td><td>360</td><td>26.24</td><td rowspan="5">0.79</td></tr><tr><td>370</td><td>33.01</td></tr><tr><td>380</td><td>44.20</td></tr><tr><td>390</td><td>51.10</td></tr><tr><td>400</td><td>56.84</td></tr><tr><td rowspan="3">Querry 模型</td><td>350</td><td>12.11</td><td rowspan="3">0.16</td></tr><tr><td>375</td><td>16.15</td></tr><tr><td>400</td><td>20</td></tr></table></body></html>

![](images/e6c77a3ebcfbde2acfb0b6d674389db2cac00d713863be97ec50189b4bfd77b8.jpg)  
图7两种水质模型  
Fig.7Two waterqualitymodels

# 5结论

本文对水衰减长度测量装置和紫外可见分光光度计两种装置的稳定性进行了验证分析，得出了两种装置的测量误差分别为 $0 . 2 2 \mathrm { m }$ 和 $0 . 1 8 \mathrm { m }$ 。利用两种装置对相同水样进行了对比测量分析，证明了两种装置在误差范围内，得到的监测结果相符。

利用水衰减长度测量装置和紫外可见分光光度计两种装置，分析不同LED 波长下监测得到的水池水样的水衰减长度，通过计算及对比分析，确定了GEANT4模拟中应采用Querry水质模型。

# 参考文献：

[1]中国科学院高能物理研究所.西藏羊八井宇宙线国家野外观测研究站的建设、运行与发展[J].中国科学院 刊,2010(4):461-464.   
[2] 曹臻,刘加丽，白云翔.物理学中的世纪难题：高能宇宙线的起源之“谜”[J].自然杂志,2009,31(6).   
[3] 曹臻,陈明君,陈松战,et al.高海拔宇宙线观测站 LHAASO 概况[J].天文学报,2019(3):1-16.   
[4] Amat F,Bizouard P,Bryant J,etal．Measuring the attenuation length of water in the CHIPS-M water Cherenkov detector[J]．Nuclear Instruments & Methods in Physics Research A，2017，844：108-115.   
[5] 路浩奇.大亚湾反符合水切伦科夫探测器及其模型研究[D].中国科学院研究生院,2009.   
[6] B．J.P． Jones et al．Journal of instrumentation 8，no．O7(July 24,2013):PO7011-P07011.   
[7] Zuo X,XiaoGFeng S,et al.Design and performances of prototype muon detectors ofLHAASO-KM2A [J].Nuclear Instrumentsand MethodsinPhysicsResearch Section A:Accelerators,Spectrometers,Detectorsand Associated Equipment,2015,789:143-149.   
[8] Cong L，Gang X，Shao huiF，et al.An apparatus to measure water optical atenuation length forLHAASO-MD[J]. Nuclear Instruments and Methods in Physics Research Section A: Accelerators,Spectrometers,Detectors and Associated Equipment, 2018, 892:122-126.   
[9] Li HC,Yao Z G,Yu C X,et al. A method to monitor and measure the water transparency in LHAASO-WCDAusing cosmic muon signals[J]． Chinese Physics C，2017，41(2):026002.   
[10]LiHC，YaoZG，Chen MJ，etal.Studyon single-channel signals of waterCherenkov detector arryforthe LHAASO project[J]．Nuclear Instruments and Methods in PhysicsResearch Section A:Accelerators，Spectrometers,Detectors and Associated Equipment，2017，854(Complete):107-112.   
[11]Steve J, Scott P. Optical Absorption of Water Compendium [DB/OL].[2018-09-01] http://omlc.org/spectra/water/abs/index.html.

# Based on WCDA water quality monitoring analysis

JI Fang1,2.3, ZHANG Jian-xin1.3\*, CHEN Ming-jun², LI Hui-cai² (1.College of Electric Power,Inner Mongolia University ofTechnology,Hohhot Inner Mongolia Ol0080,China; 2.Institute of High Energy Physics， Chinese Academy of Sciences， Beijing 1Oo049， China; 3.Inner Mongolia Electromechanical Control Laboratory，Hohhot Inner Mongolia OlOo51，China)

Abstract: The Water CherenkovDetector Arry(WCDA)is one ofthe main detectors of theHigh Altitude Cosmic Ray Observatory (LHAASO),water astheonlydetectionmedium,the water transparencywilldirectlyafectthedetectioneficiencyof Cherenkov Light.Inorder to ensure therealizationof WCDAphysical goals,thereal-time measurementand monitoringof waterattenuation lengthisveryvital,whichisoneoftekeytasksfortheoaloperatioandcalibrationofetector.tisexperiment,teorking principleof wateratenationength measuringdeviceandultraviolet-viblespectrophotometerisitroduced,andvarioussplesof wateraremeasuredbydiferent wavelengthLED,andthedataresultsof thetwomethodsarecomparedandanalyzed.The measurement errors of the two devices were found to be $0 . 2 2 \mathrm { m }$ and $0 . 1 8 \mathrm { m }$ ,the corresponding relationship between industrial index absorbance and wateratenuation lengthofsientificresearch indexisfound,andaQuerrwaterqualitymodelfortheGEANT4 simulationis establishedbysimulation,whichfurtherpromotes therealisationofsimulation.Through theverificationofWCDANo. 1 waterattenuationmeasuringdeviceandthedatastudyof waterqualitymonitoringfrom waterinjectiontostableoperation,etof stableandreliable waterqualitymonitoringschemeissummarized,whichprovidesalotofhelpforthemonitoringworkofNo.and No. 3 water pools.

Key Words: LHAASO; Water quality; Water attenuation; Absorbance