# CN 53-1189/P ISSN 1672-7673

# 嫦娥二号CCD立体相机图像质量分析

王奋飞1,²，任鑫1,²，刘建军1,²，李春来1,2(1.中国科学院国家天文台，北京100012；2.中国科学院月球与深空探测重点实验室，北京100012)

摘要：嫦娥二号卫星作为我国第2颗成功发射的月球探测器，搭载的CCD立体相机在轨运行期间获得覆盖全月的 $7 \mathrm { m }$ 分辨率图像，给月球科学家提供了重要的研究基础数据。开展了对CCD立体相机图像质量情况的全面分析，为后续数据处理算法的选择、图像数据判读和科学数据应用等提供参考。从图像客观评价角度出发，得出嫦娥二号图像与现有国外同分辨率数据的图像质量相当。重点分析了需要注意的几个质量问题，如嫦娥二号图像存在明显的地域特征，图像压缩使质量受损，存在一定的条带噪声，相邻轨道间图像定位偏差大等，这些质量问题在后续图像处理中需重点关注。

关键词：嫦娥二号；CCD立体相机；图像质量；月球中图分类号：P236 文献标识码：A 文章编号：1672-7673(2016)01-0093-07

2010年10月1日，作为我国探月二期工程的技术先导星嫦娥二号卫星在西昌卫星发射中心成功发射，直接进入奔月轨道，经过1次轨道中途修正顺利进入轨道高度为 $1 0 0 ~ \mathrm { k m }$ 的环月轨道。嫦娥二号其中一项重要的任务目标是利用CCD立体相机在 $1 5 \ \mathrm { k m }$ 近月点对嫦娥三号任务预选着陆区开展高分辨率成像试验，并且在 $1 0 0 \mathrm { k m }$ 环月圆轨道，获取分辨率优于 $1 0 \mathrm { ~ m ~ }$ 的月球表面图像。2010年10月24日，嫦娥二号卫星上的两线阵CCD立体相机首次开机工作，并成功获取了前视与后视两个视角的图像数据。至2011年5月，嫦娥二号卫星CCD立体相机完成了对月球成像全部的探测任务。在整个任务期间，共获取607轨图像数据。文[1-2]介绍了嫦娥二号立体相机的设计和关键技术；文[3]对在轨图像数据进行了成像分析；文[4]对立体相机数据预处理方法与流程进行了说明，并初步评价了图像数据的质量。在此基础上，本文对立体相机图像数据的质量问题进行全面的分析和总结，重点指出数据使用者在后续数据处理和应用中需要注意的几个问题，比如嫦娥二号月球图像区域性特征、图像噪声、相邻轨道间几何定位偏差大等质量问题。

# 1数据

# 1. 1 CCD立体相机

CCD 立体相机是搭载在嫦娥二号卫星上的主要有效载荷之一，采用时间延时积分电荷耦合元件（Time Delayand Integration Charge Coupled Device，TDICCD），以线阵推扫成像方式沿卫星飞行方向获取前视与后视两个视角的两线阵图像条带[1]。两条线阵共用一套光学系统，平行安装在焦平面上，像元数为6144元，像元尺寸为 $1 0 . \mathrm { ~ 1 ~ \mu m \times 1 0 . ~ 1 ~ \mu m }$ ，相机光轴与卫星本体坐标系 $+ Z$ 轴平行。图1给出了CCD立体相机在轨道高度为 $1 5 \mathrm { k m }$ 和 $1 0 0 \mathrm { k m }$ 的成像原理[5]，其空间分辨率随轨道高度的变化有所不同：在 $1 0 0 \mathrm { k m }$ 轨道上，空间分辨率约为 $7 \mathrm { m }$ ，成像幅宽约为 $4 3 \ \mathrm { k m }$ ；在 $1 5 \mathrm { k m }$ 轨道上，空间分辨率约为 $1 . 5 \mathrm { m }$ ，幅宽约为$9 . 2 \mathrm { k m }$ 。图像数据在星上有不压缩、2倍、4倍、8倍等4种压缩模式。实际数据获取过程中， $1 0 0 \mathrm { k m }$ 图像采用8倍压缩， $1 5 \mathrm { k m }$ 图像采用4倍压缩。CCD相机设置了16级、32级、48级、64级及96级五档积分级数，0.7、1.0和2.0三档增益，积分级数和增益的设置由光照条件和月表平均反射率等因素决定。

![](images/e101e706404921b886fe5cbda8c8db9a2598793907a8680b42c1812fe347c98d.jpg)  
图1CCD立体相机在轨道高度为 $1 5 \mathrm { k m }$ 和 $1 0 0 \mathrm { k m }$ 成像原理示意图 Fig.1The schematic diagram of the CCD stereo camera imaging at the height of $1 5 \mathrm { k m }$ and $1 0 0 \mathrm { k m }$

# 1. 2 数据获取情况

CCD立体相机在卫星进入工作轨道后，光照条件允许（太阳高度角 $\geqslant 5 ^ { \circ }$ )的情况下，开机获取图像数据，实际拍图过程中也获取了极区附近太阳高度角小于 $5 ^ { \circ }$ 的月面区域。CCD相机的开机工作时间见表1。

表1嫦娥二号卫星CCD相机工作时间安排  
Table1 The schedule for the opening session of CE-2 CCD stereo camera   

<html><body><table><tr><td>飞行阶段</td><td>时间节点</td><td>说明</td></tr><tr><td>发射入轨</td><td>2010-10-01</td><td>发射</td></tr><tr><td rowspan="3">正飞</td><td>2010-10-06~2010-10-23</td><td>进入月球环绕工作轨道，状态链路调整</td></tr><tr><td>2010-10-24~2010-11-01</td><td>CCD 相机开机，在轨测试虹湾区1.5m成像试验</td></tr><tr><td>2010-11-02~2011-01-22</td><td>全月球7m分辨率成像</td></tr><tr><td>侧飞</td><td>2011-01-23~2011-04-22</td><td>CCD相机关机</td></tr><tr><td>正飞</td><td>2011-04-22~2011-05-20</td><td>第1项拓展试验：南北极极区补拍</td></tr><tr><td></td><td>2011-05-20~2011-05-23</td><td>第2项拓展试验：第2次虹湾1.5m成像试验</td></tr></table></body></html>

(1)在轨测试阶段

北京时间2010年10月24日16时49分，嫦娥二号卫星上的两线阵CCD立体相机首次开机工作，并成功获取了前视与后视两个视角的图像数据。北京时间 2010年10月26日21时27分，嫦娥二号卫星成功进入 $1 0 0 \ \mathrm { k m } \times 1 5 \ \mathrm { k m }$ 椭圆试验轨道，对嫦娥三号任务预选着陆区开展高分辨率成像试验，经过约2天的环月飞行，总共获取了19 轨图像数据。

# (2) $1 0 0 \mathrm { k m }$ 全月成图

从2010年11月2日开始正式转入长管运行阶段，至2010年11月29日，CCD立体相机共获取341轨数据，实现了在现有的轨道倾角下所有区域的数据完全覆盖(除6轨数据有少量缝隙)。从2010年11月30日开始至12月20日，CCD立体相机对第1次覆盖过程中的6处缝隙进行了补拍，获得29轨补缝数据。至此，除南北极区，CCD立体相机实现了全月球图像覆盖，共获取了370轨图像数据。

# (3)扩展任务

2011年1月23日至4月22日，卫星处于侧飞阶段，CCD立体相机关机。从4月23日开始，逐步开展嫦娥二号的拓展任务。第1项拓展任务是调整卫星的轨道倾角参数，对南北极极点漏洞进行补拍。至5月20日，获得图像数据168轨，实现了全月球图像覆盖。2011年5月20日，开始进行第 2

项拓展任务，卫星调整轨道高度，再次降至近月点 $1 5 ~ \mathrm { k m }$ 轨道高度，对虹湾地区进行高分辨率成像，至5月23日，共获取了16轨图像数据。至此，CCD 相机共获取607轨图像数据。随后，CCD立体相机关机，进入第3项拓展任务，卫星离开月球，飞向拉格朗日点。

# 2图像数据质量分析

# 2.1与国外同类图像质量评价对比

图像质量是指人们对一幅图像视觉感受的主观反映。从判别方法来分，图像质量的评价可以分为主观判别方法和客观判别方法。主观判别方法是指以人的视觉效果作为评判准则，由观察者对图像质量作出判断。客观判别方法是指用可定量分析的数学模型表达人对图像的主观感受。主观判别方法一般与视觉效果符合较好，但这些主观标准的构成受判读过程中人为因素的影响。而客观判别方法从理论出发，经过各种数学计算定量地分析，得到图像质量的科学指标，其理论性强，快速稳定，能给出定量数据。因此，本文从客观评价角度对嫦娥二号立体相机图像的质量进行评价。常用的一些衡量客观质量评价指标主要有灰度均值、灰度方差、灰度值动态范围、信息熵、清晰度、边缘强度等[6]。

为了更全面地评价嫦娥二号图像，本文选取成像区域相同、成像条件相似、空间分辨率相近的图像数据作为参考对比数据，分别计算嫦娥二号图像和参考图像的客观评价指标，并加以比较。对于 $1 0 0 \mathrm { k m }$ 轨道高度获取的 $7 \mathrm { m }$ 分辨率图像，选取了嫦娥二号图像的轨道号为第190轨，位于Apollo15登月点附近的图像数据，比较了相同地理位置的嫦娥二号图像与日本月神号探测器（Selenological and EngineeringExplorer，SELENE) $7 . 4 \mathrm { m }$ 分辨率图像，客观评价指标计算结果见表2。对于 $1 5 \mathrm { k m }$ 轨道高度获取的 $1 . 5 \mathrm { m }$ 分辨率图像，选取了嫦娥二号图像的轨道号为第239轨，与相同地理位置的美国月球勘测轨道飞行器(Lunar Reconnaissance Orbiter，LRO) $1 . 5 \mathrm { m }$ 分辨率图像进行比较，客观评价指标对比结果见图2。

表2嫦娥二号图像与日本月神号图像数据客观评价结果  
Table 2The objective image quality evaluations of CE-2 and Kaguya   

<html><body><table><tr><td>文件名</td><td>均值</td><td>方差</td><td>平均梯度</td><td>信息熵</td><td>清晰度</td><td>边缘强度</td></tr><tr><td>CE-2数据</td><td>57. 922 5</td><td>25.003 2</td><td>2. 049</td><td>5.908 4</td><td>2.478 2</td><td>18. 772 8</td></tr><tr><td>日本月神号数据</td><td>49.023</td><td>26.4821</td><td>1. 2219</td><td>6. 492 5</td><td>1.200 8</td><td>12.862 6</td></tr><tr><td>偏差</td><td>8. 899 5</td><td>-1. 478 9</td><td>0.8271</td><td>-0.584 1</td><td>1. 277 4</td><td>5.9102</td></tr></table></body></html>

![](images/0735fadbcc991290556e00fc7248310cb06d8155b9317d769ef2a0f209701cf1.jpg)  
图2美国月球勘测轨道飞行器数据与嫦娥二号图像客观评价指标比较 Fig.2The comparison of the objective image quality indicators between US LRO and CE-2 data

图像质量客观指标的对比分析结果表明，嫦娥二号在 $1 0 0 ~ \mathrm { k m }$ 轨道高度获取的 $7 \mathrm { m }$ 分辨率图像，与日本SELENE $7 . 4 \mathrm { { m } }$ 分辨率图像相比，嫦娥二号图像在灰度均值、清晰度、边缘强度等方面要优于SELENE 数据，在方差、平均梯度、信息熵等方面相当；嫦娥二号在虹湾 $1 5 \ \mathrm { k m }$ 轨道高度获取的 $1 . 5 \mathrm { m }$ 分辨率图像，与美国月球勘测轨道飞行器卫星的 $1 . 5 \mathrm { m }$ 分辨率图像相比，各项客观评价指标相当。

但是，嫦娥二号图像有几个质量问题在进行后续数据处理和应用时值得关注。主要有以下几方面的问题：一是月球图像具有明显的地域性差异，选择数据处理算法时需要考虑不同地域图像的适应性；二是部分区域图像存在压缩质量受损以及图像噪声等问题，后期数据处理时需要考虑图像去噪和图像增强处理；三是相邻轨道间图像的平面位置偏差大，需要考虑采用摄影测量平差方法进行轨道优化。

# 2.2月球图像质量地域性差异特征

与地球遥感图像相比，月球图像反照率、对比度等都偏暗。月球表面地物类型单一，月表图像的纹理信息主要是由撞击坑、山脉、月溪等月面地形的光照阴影形成，随着光照条件、目标物几何形态、地形起伏等的变化，图像纹理特征变化很大。选择6种具有不同地貌特点的月面区域，基本涵盖了月球影像的绝大部分特征，共33个区域图像对全月球影像进行了分析，试验区空间分布情况和客观评价指标计算结果分别见图3和表3，得出以下两个结论：

（1)月球图像具有明显的地域特征，高地图像的亮度、对比度、图像层次和清晰程度、所包含的纹理信息等方面都明显好于月海图像(图4);(2)无论是高地还是月海，高纬度地区的图像质量好于低纬度地区。因此，在选择图像处理算法的时候必须充分考虑月球影像的数据特点及质量的地域性特征。

![](images/9dfc560cc56c95bc5fa9ebb7f71dd4208f9dd25f3300fb0d451876473bde42b2.jpg)  
图3高地图像(左图）和月海图像对比(右图)  
Fig.3The comparison of images captured at the highland（left）and the mare（right)

# 2.3 图像压缩和噪声问题

嫦娥二号图像在星上采用了图像压缩，地面解压后的图像带来了一定的质量损失，月海图像较高的地区质量损失明显。此外，嫦娥二号影像有带通噪声和随机噪声（图5)。后续图像处理中需要考虑，比如在选择图像匹配算法的时候需要考虑图像噪声的影响，匹配算法对噪声具有一定的鲁棒性。

表3立体相机图像质量评价区客观质量指标平均值  
able 3The average value of the objective image evaluation indicators for the CCD stereo ca   

<html><body><table><tr><td>地貌特点</td><td>均值</td><td>方差</td><td>平均梯度</td><td>信息熵</td><td>清晰度</td><td>边缘强度</td></tr><tr><td>高地地区</td><td>88</td><td>21. 071</td><td>3.202</td><td>5.805</td><td>3.168</td><td>31. 410</td></tr><tr><td>月海地区</td><td>41</td><td>4. 138</td><td>0.870</td><td>3. 470</td><td>0.893</td><td>7. 654</td></tr><tr><td>海陆交汇</td><td>46</td><td>7. 675</td><td>1. 046</td><td>4.230</td><td>1. 099</td><td>9. 601</td></tr><tr><td>山脉</td><td>53</td><td>10. 333</td><td>1. 278</td><td>4. 796</td><td>1. 328</td><td>12. 194</td></tr><tr><td>辐射纹</td><td>70</td><td>13. 374</td><td>1. 720</td><td>5.441</td><td>1. 816</td><td>16. 659</td></tr><tr><td>其他</td><td>76</td><td>61. 479</td><td>7. 729</td><td>7. 157</td><td>7.564</td><td>80.183</td></tr></table></body></html>

![](images/de37759b56d08e65fa54cd17435667ed221b4cd86421e00e5b2de03075299a86.jpg)  
Fig.4The comparison of images captured at the highland(left）and the mare（right)

# 2.4相邻轨道位置偏差问题

卫星轨道与姿态的稳定度和测量精度，对CCD图像数据的质量和几何定位精度具有很大的影响。为了评估卫星轨道与姿态对全月球图像质量的影响，尤其是几何定位精度的影响，本文利用测控系统提供的数据，结合CCD影像数据，对卫星在轨运行期间的轨道和姿态进行了系统的分析，以评价其对图像数据初始定位结果的影响程度。

本文选取轨道号从301到640中的334轨前视图像，除极点外这些数据对月球的覆盖率在$9 9 \%$ 以上。相邻轨道图像在赤道处重叠度约为 $2 4 \%$ ，随着纬度的增加，重叠度亦增加。在相邻轨道图像的重叠区域提取同名像点，用于分析相邻轨道数据的相对定位误差。在334轨数据中，共选取了约22000个均匀分布的同名像点，计算了这些同名像点在相邻轨道图像上的位置偏差，位置偏

![](images/5c800a0c0ceefb3654fbd096d6d0fca43a2d97a42f26c638ae6b1d2bcc75c945.jpg)  
图4高地图像(左图）和月海图像对比(右图)  
图5嫦娥二号图像局部地区存在条带噪声现象 Fig.5The stripe noises in the regional image of CE-2

差的平均值为 $1 8 7 . 6 9 0 \mathrm { m }$ ，最大值为 $2 6 6 7 . 5 9 0 \mathrm { m }$ ，最小值为 $0 . 4 1 1 \mathrm { ~ m ~ }$ ，标准差为 $2 1 1 . 5 1 8 \mathrm { m }$ ，图6给出了定位偏差的分布情况。可以看出，绝大部分区域超过了2像素( $1 4 ~ \mathrm { m } \dot { }$ ，占 $9 9 . 4 \%$ ，不能满足像素级“无缝”镶嵌的要求，图像数据需要在几何定位的基础上进行几何配准处理。

![](images/9e11fa80954df609191dde782a2bc984d80fbf8abbbbe005bfd60bd36d06db4b.jpg)  
图6嫦娥二号相邻轨道图像初始定位结果偏差空间分布图  
Fig.6The spatial distribution of the location deviation in the initial positioning between adjacent images

# 3结语

本文从客观评价角度对嫦娥二号图像质量进行了评价，得出其图像质量与国外同类数据相比质量相当，表明嫦娥二号相机数据具有较好的应用前景。但是原始图像质量具有区域性特征，存在若干质量问题，在后续图像处理应用特别是图像匹配算法设计上要重点考虑。相邻轨道图像平面位置偏差分析表明，偏差的平均值为 $1 8 8 \mathrm { ~ m ~ }$ ，是原始图像分辨率的几十倍甚至近百倍。因此，采用原始的卫星轨道和姿态数据无法实现全月图像数据的无缝镶嵌和高精度绝对定位，在后续图像数据处理应用中需要考虑采用摄影测量平差处理的方法，对原始的轨道和姿态数据进行优化处理，提高原始图像数据的相对和绝对定位精度，以满足各种应用需要。

# 参考文献：

[1] 赵葆常，杨建峰，汶德胜，等.嫦娥二号卫星CCD立体相机设计与验证［J].航天器工程，2011，20(1):14-21.Zhao Baochang，Yang Jianfeng，Wen Desheng，et al. Chang'e-2 lunar orbiter CCD stereo cameradesign and validation ［J]. Spacecraft Engineering，2011，20(1）：14-21.  
[2] 赵葆常，唐茜，薛彬.“嫦娥二号”卫星CCD立体相机的关键技术［J].航天返回与遥感，2013，34(4) : 43-51.Zhao Baochang，Tang Qian，Xue Bin.Key technologies of CE-2 CCD stereo camera ［J].Spacecraft Recovery & Remote Sensing，2013，34(4）: 43-51.  
[3] 赵葆常，李春来，黄江川，等.嫦娥二号月球卫星CCD立体相机在轨图像分析［J]．航天器工程，2012，21(5)：1-7.Zhao Baochang，Li Chunlai，Huang Jiangchuan，et al. Analysis on in-orbit CCD stereo cameraimages of Chang'e-2 lunar satellite [J]. Spacecraft Engineering，2O12，21(5） : 1-7.  
[4] 刘建军，任鑫，谭旭，等.嫦娥二号CCD立体相机数据预处理与数据质量评价［J]．武汉大学学报：信息科学版，2013，38(2)：186-190.Liu Jianjun，Ren Xin，Tan Xu，et al. Lunar image data preprocessing and quality evaluation ofCCD stereo camera on Chang'E-2 [J]. Geomatics and Information Science of Wuhan University,2013，38(2): 186-190.  
[5] 高兴烨，刘建军，任鑫，等.嫦娥二号探测器在轨运行视景仿真系统的研究与实现［J］．天文研究与技术——国家天文台台刊，2012，9(2)：114-120.Gao Xingye，Liu Jianjun，Ren Xin，et al.Research and implementation of a visual simulationsystem of orbital motion of the Chang’E-2 ［J].Astronomical Research & TechnologyPublications of National Astronomical Observatories of China，2012,9(2）：114-120.  
[6] 胡良梅，高隽，何柯峰.图像融合质量评价方法的研究［J]．电子学报，2004（S1）：218-221.Hu Liangmei，Gao Jun，He Kefeng. Research on quality measures for image fusion [J]. ActaElectronica Sinica，2004(S1） :218-221.

# Image Quality Evaluation of the CCD Stereo Camera of Chang' E-2 Lunar Satellite

Wang Fenfei $^ { 1 , 2 }$ ，Ren Xin $^ { 1 , 2 }$ ， Liu Jianjun $^ { 1 , 2 }$ ， Li Chunlai $^ { 1 , 2 }$ （2 (1.National Astronomical Observatories，Chinese Academyof Sciences，Beijing 10ool2，China,Email；renx@nao.cas.cn; 2.Key Laboratory of Lunar and Dep Space Exploration，Chinese Academy of Sciences，Beijing 1Oo0l2,China)

Abstract：The CCD stereo camera carried by the Chang'e-2，which is China’s second lunar probe satellite，successfully scanned the full coverage of the lunar surface at $7 \mathrm { m }$ spatial resolution during its operation.Those images are served as important data basis in relevant lunar scientific activities.However,til now,most studies have paid few attentions to its quality isues，which could introduce errors and uncertainties in the subsequent analysis，such as the image processing algorithm selection，the image interpretation and the scientific data application.In this study，we conducted a comprehensive objective assessment on the image quality ofthe CCD stereo camera.We found that the quality of the images captured by the Chang'e-2 is equivalent to that offoreign satelitesat the same spatial resolution.We also analyzed several quality issues that needs special concern in the following image processing，such as the distinct geographic patterns exist in Chang'e-2 images，the image compression induced quality reduction，stripe noises，large location deviation between adjacent images.

Key words: Chang'E-2；CCD stereo camera；Image quality；Moon