# 基于视频信息的城市路段交通安全状态评估方法研究

蔡延光1，陈骋逵1，蔡颢1,²，黄何列1，戚远航1(1．广东工业大学 自动化学院，广州 510006;2.奥尔堡大学 健康科学与工程系，丹麦 奥尔堡 9220)

摘要：城市道路交通安全状态实时评估是智能交系统的重要研究内容。针对现有交通安全状态实时评估方法的评估效果不理想的问题，建立了基于视频信息的城市路段交通安全状态评估方法。首先，分析了基于视频信息的交通流参数快速检测方法；然后，从车速离散度的角度提出了影响城市路段交通安全状态的路段车速离散度的概念；最后，建立了基于路段车速离散度的城市路段交通安全状态评估方法。实验表明，所提方法能够实时合理地对城市道路的安全状态水平进行评估，评估结果可以为交通管理部门制定有效的城市路段交通安全改进方案提供相应的依据。

关键词：智能交通；道路交通安全；视频信息；车速离散度中图分类号：TP391.4 doi: 10.3969/j.issn.1001-3695.2017.07.0697

# Safety state evaluation method of urban road traffic based on video information

Cai Yanguang1, Chen Chengkui1, Cai Hao1,², Qi Yuanhang' (1.Schoolof Automation Guangdong Universityof Technology,Guangzhou 510o06,China;2.DeptofHealth Science& Technology,Aalborg University,Aalborg 9220,Denmark)

Abstract:Thereal-timesafetystate evaluationofurbanroadtrafficisanimportantresearchcontentofintellgent transportation system (ITS).Focusingontheproblemthattheevaluationresultsofthe existing traficsafetystatereal-time evaluation methods areunsatisfactory,this paper proposedasafetystate evaluation method ofurbanroad traffic basedonvideo information.Firstly this paperanalyzed therapid detectionmethodoftraficflow parameters based onvideo information.Then,it proposed the concept of velocitydispersionofurban road from the pointof viewofvehicle speed dispersion.Finall,it establishedasafety stateevaluation methodofurbanroadtrafficbasedonroad velocitydispersion.Theexperimentalresultsshowthattheproposed methodcan evaluate the safetystate levelofurbanroadtraffic inreal tmeandinareasonable way,.Andthe evaluation result can provide thecorresponding basis for the trafic management department to develop effectiveurban road trafic safety improvement program.

Key Words: intelligent transportation system; road safety; video information; vehicle velocity dispersion

# 0 引言

随着智能交通系统(ITS)的快速发展和部署，通过视频信息实时获取交通流参数已成为主要信息获取手段。作为智能交通系统的重要研究内容，利用视频信息对道路安全状态进行实时评估是提高城市道路交通安全水平的有效途径，已引起了国内外学者的广泛关注[1\~4]。文献[5]分析了平均车速、车速标准差对路段事故率的影响机理，发现路段事故率与车速离散性的相关系数最大。文献[6]采用灰色关联特征向量法和灰色关联分析法构建了区域道路交通安全评价指标体系，并确定了指标权重。

文献[7]利用核密度估计建立了事故概率密度函数，并综合考虑事故位置特征和历史数据的影响，提出了基于经验贝叶斯方法的安全状态评估模型。文献[8]采用层次分析法对道路交通安全评价中的信息量少、决策时间短的问题进行了研究。以上评估方法虽然能够对交通安全状态进行评估，但在评估实时性和准确性方面还不能较好的满足智能交通系统的要求。

针对现有评估方法的评估效果不佳的问题，本文提出了一种新的城市路段交通安全状态评估方法。首先，本文通过对视频交通信息的快速检测与识别,从车辆本身角度出发找出影响交通安全的所有的车辆因素；然后，通过对影响安全的因素的分析，从车速离散度的角度得出影响城市路段交通安全状态的路段车速离散度的概念；最后，建立了基于路段车速离散度的城市路段交通安全状态评估方法,并对所提评估方法进行了实验分析。

# 1 基于视频信息的交通参数检测方法

监控摄像的运用在现代智能交通领域已经越来越广泛和普遍，通过对视频信息的提取分析本文可以定性、定量的得到交通运行安全状态。城市道路通常都安装有监控摄像头，通过基于视频的交通信息快速检测和识别，本文可以获取该交叉口的交通流参数（车流量和车速）等道路交通信息。

基于视频的交通信息快速检测和识别是指以机器视觉技术为核心[9-10]，研究基于机器视觉的路面交通参数自动检测与交通突发事件自动识别等技术。通过开发复杂交通场景下的交通视频检测与交通状况智能识别，解决复杂环境下交通信息参数和交通突发事件的快速、准确检测问题。

# 1.1基于视频信息的路段车速检测

对于城市道路交通来说，交通流参数主要包括进入交叉口的车速。基于视频的车速检测即视频运动目标信息检测跟踪等问题，运动目标检测就是从视频图像序列中检测出感兴趣的运动目标，这是智能视觉的基础，任何对运动目标运动特性的研究都是以运动目标检测为前提的。

常用的运动目标检测方法有背景差分法和基于运动分析法。背景差分法的核心是背景建模，通过比较图像与背景模型判断出属于前景点还是背景点。常用的背景建模方法有单高斯模型，Stauffer 等提出了一种混合高斯模型的建模方法[1]。基于运动分析的方法主要包括光流法和帧间差法[12]。基于运动分析方法，本文可以根据一前一后的两个帧图像中车辆的位移差，计算出车辆的行驶速度，通过运动目标检测分离出运动车辆目标。在图像中划定一个检测区域，当 $t _ { 0 }$ 时刻车辆进入该检测区域时记录当前帧图像，在车辆即将行驶出红色检测区域时刻 $t _ { 1 }$ 记录该帧图像，经过红色区域的时间为 $\Delta t = t _ { 1 } - t _ { 0 }$ 。基于简易的摄像机标定方法，由于本文的目的是为了获取车辆的实际速度，而不是车辆在图像中的移动像素速度，速度单位也不是像素/时间，而应该是公里/小时。因此，必须找到移动像素数和实际距离的关系。图1为一般道路监控摄像机中连续两帧图像间车辆经过时的一个侧面示意图。

![](images/170c5385f3751e8506da9c07c2e4a30a70f6a34c9e1c710f68fcf4137864e34f.jpg)  
图1t0和t1时刻的侧面示意图

图1中，道路交通系统摄像头的拍摄俯角一般不小于 $6 0 ^ { \mathrm { o } }$ 视距 $\boldsymbol { \mathscr { c } }$ 以及检测点与摄像头之间的距离 $y$ 一般较大。当 $\Delta t$ 很小时，与 $y$ 相比， $\Delta y$ 就显得很小了。当忽略图中拍摄俯角的变化，仅考虑由 $\theta$ 产生的透视，则设定检测区域内的所有点对于摄像头的仰角都不变，为 $\theta _ { \circ }$

在图像中划定的检测区域的宽度刚好为一个车道的宽度（在我国三级以上的多车道公路机动车车道的宽度约为 $3 . 5 \mathrm { m } \mathrm { \ddot { \Omega } }$ )，则根据划定区域的实际像素大小就可以方便的确定车辆通过划定检测区域的位移。

设垂直方向上，检测区域对应的路面实际距离为 $d \textrm { m }$ ，此时有

$$
\frac { 1 8 0 } { \ d \cos \theta } = \frac { 1 2 0 } { 3 . 5 }
$$

前面设定不考虑视觉透视效果的影响，因此，可以认为，在图像中垂直方向距离相等，其对应的实际距离也应当相等：

$$
\frac { y _ { 0 } } { 1 8 0 } = \frac { \Delta y } { d }
$$

$$
d = 3 . 5 \times { \frac { 1 8 0 } { 1 2 0 \cos \theta } } = 3 . 5 \times { \frac { 3 } { 2 \cos \theta } } = { \frac { 2 1 } { 4 \cos \theta } }
$$

从而得出测速的计算公式为

$$
\nu = \frac { d } { \Delta t }
$$

当运动目标通过划定的检测区域时，运动目标发生的位移即为 $d$ ，设置图3-7道路交通系统架设的监控摄像头摄像角度 $\theta$ ${ = } 6 0 ^ { \circ }$ ，则得出 $d = 1 0 . 5 \mathrm { m }$ 。

车速检测过程如图2所示。运用该方法可以较简单快速又不失准确性的得到车速信息。

![](images/5c9e2bcf07caded6773d37654420ed8fd088734ce01b670ab30173c90b36c1a0.jpg)  
图2车速检测

# 1.2基于视频信息的路段车流量检测

通过在检测视频中设置虚拟的检测区域方式：在视频图像的每个车道的区域上设置一个矩形的检测区域。每当有车辆经过在车道中绘制的检测区域时，该检测区域内的视觉信息将会发生很大的变化，这将是判断车辆是否经过检测区域的重要依据。检测过程中，对每一帧图像上的检测区域内的数据分析，判断前景中的运动目标是否通过检测矩形框，分别统计每条车道检测区域内通过的车辆数目。

常用的虚拟检测的方法有矩形检测区域、检测线的形式，本文采用的是设置矩形检测区域的方式如图3所示。保证设置的矩形检测区域中的两条平行的检测线与道路成垂直关系，检测区域的大小应保证与车道宽度相同，具体应用过程中，由于道路交通监控视频的远近可能有些许差别，两条垂直于车道的检测线之间的距离需考虑拍摄远近的影响。

![](images/9142f7a4b98dc96e8c75f14aebf843c5f5b5c4ccf79a0e107babda440b2a08f6.jpg)  
图3虚拟检测区域示意图

具体车流量检测算法是，通过检测出运动目标，将运动目标看成一个个团块处理，计算出每个团块的中点：

$$
\left\{ { \begin{array} { l } { \displaystyle x = x _ { 1 } + { \frac { W } { 2 } } } \\ { \displaystyle y = y _ { 1 } + { \frac { H } { 2 } } } \end{array} } \right.
$$

其中， $( x , y )$ 为运动目标的中点坐标； $( x _ { 1 } , y _ { 1 } )$ 为图像中检测出运动目标区域的起始坐标； $W$ 、 $H$ 分别为运动目标区域的宽和高。

接着再根据求得运动目标得中心点坐标，以检测区域的宽为直径绘制圆形边缘图。

当边缘图中圆形运动目标的中心点通过相应车道绘制的检测矩形区域时，则这条车道的车流量加1。车流量检测效果如图4所示。

![](images/3866adb6e1eabf580bf53930bd2ca1b9b5fabd341089fd0ffa909cdc78434385.jpg)  
图4路段车流量检测

# 2 城市路段交通安全状态评估方法

# 2.1车速离散

车速离散产生的机理起于每个不同的驾驶员个体的不同驾驶选择，即便是相同的道路条件不同的驾驶员也会选择不同的速度行驶，反映到宏观层面就是路段的车速离散现象。此外，交通流特性及道路特性也会给予驾驶员一定影响，致使速度离散。

目前关于车速离散的研究中，国内外学者已根据不同研究目的提出多种关于车速离散的描述方法，被普遍认可的表达方式有断面车速标准差 $S D ^ { [ 1 3 ] }$ 和平均速差 $A S D ^ { [ 1 4 ] }$ 。断面车速标准差是可有效表现样本离散程度的指标之一，能表示测量时间内单个车辆对比于全部车辆的平均速度的离散状况，以往研究中有较多应用[15]。标准差越高，样本个体车速越离散，但其更注重于描述断面车速的离散程度，如果要表达整个路段的离散程度还需其他处理方式；平均速差能够从空间位置上反映相邻车辆速度差异关系，但与断面车速标准差一样，它更能着眼于断面的车速离散，对于路段的整体性并没有涉及。

# 2.2基于车速离散度的路段交通安全状态评估方法

本文提出的路段车速离散概念，能够反映出路

段整体的稳定行驶状态，从单车的角度可使用单车速度波动幅度的概念反映单车行驶的稳定性，继而推断出路段整体的稳定性。

已有成果表明，车速和速度变化率是影响车辆行驶安全的主要数值[16]，即车速波动幅度。因此，提出基于路段的车辆速度离散度 $\varphi _ { L }$ 的概念，则有如下的表达形式：

$$
\varphi _ { L } = { \frac { S L } { \overline { { V } } } }
$$

其中:

$$
S L = \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { M } ( V _ { 8 5 , i } - \overline { { V } } _ { 8 5 } ) ^ { 2 } } { M - 1 } }
$$

$$
\overline { { V } } _ { 8 5 } = \frac { \displaystyle \sum _ { i = 1 } ^ { M } V _ { 8 5 , i } } { M }
$$

其中，85位车速表示在该路段行驶所有车辆中，有 $8 5 \%$ 的车辆行驶速度在此速度之下，仅有 $1 5 \%$ 的车辆速度高于此值（车速累积频率曲线)，该值能有效客观的展示该路段的车速。 $S L$ 为路段上断面85位车辆速度的标准差； $\overline { { V } }$ 为通过整条道路车辆的平均行驶速度； $\overline { { V } } _ { 8 5 }$ 为通过所有断面的85位车速的平均值；$V _ { 8 5 , i }$ 为通过第 $i$ 个断面的85位车速； $M$ 为路段的速度检测的断面总数。

式(7(8)中，断面总数 $M$ 是唯一需要主观确定的值，断面划分的越细致，计算的结果就越精确，但过于密集的断面会给检测过程带来较大困难。在方便观测计算的前提下，尽可能的增加断面数量，可保证计算结果的合理性。在本文数据处理时，断面间距保持在 $5 0 \mathrm { m }$ 左右，既便于观测，又不会因为断面较少导致结果丧失合理性。

将路段由路段车速离散度划分为四个等级：安全A、较安全B、基本安全C、不安全D。通过对广州市多个路段的历史交通数据及事故轻重程度进行统计分析，评价指标分类标准如表1所示。其中， $\overline { { \varphi } } _ { L }$ 为路段安全运行状态时的车速离散度的平均值。

表1路段交通安全评估指标分类标准  

<html><body><table><tr><td>安全类别</td><td>安全A</td><td>较安全B 基本安全C</td><td>不安全D</td></tr><tr><td>路段车速离散度φ%</td><td>2 2 0~ 亚~L</td><td>2 ~</td><td>2 >3</td></tr></table></body></html>

# 2.3评估方法流程

基于路段速度离散度的道路交通安全状具体评估步骤如下：

a)输入：路段划分的检测断面数 $M$ （正整数）、通过第 $i$ $( i { = } 1 , 2 , . . . , M )$ 个断面的85位车速 $V _ { 8 5 , i }$ 、通过整条道路车辆的平均行驶速度 $\overline { { V } }$ 。

b)计算道路的路段车速离散度；按式(8)计算路段的车速离散度 $\varphi _ { L }$

c)计算道路安全状态下的路段车速离散度的平均值，具体步骤包括：

(a)对每个该路段处于安全运行状态下样本 $\textit { j } ( j { = } 1 , 2 , . . . , K )$ $K$ 为样本总数，计算样本 $j$ 的路段车速离散度 $\varphi _ { L , j }$ ，初始 $j { = } 1$ 。

(b)输入第 $j$ 个该路段处于安全运行状态下样本的相应参数：路段划分的检测断面数 $M$ （正整数）、通过第 $\textit { i } ( i { = } 1 , 2 , . . . , M )$ 个断面的85位车速 $V _ { 8 5 , i } .$ 通过整条道路车辆的平均行驶速度 $\overline { { V } }$ 。

(c)根据步骤b)中确定的路段的车速离散度 $\varphi _ { L }$ 计算方法计算得到样本 $j$ 的路段车速离散度 $\varphi _ { L , j }$ ， $\varphi _ { L , j } = \varphi _ { L }$ 。

$( \mathrm { d } ) j { = } j { + } 1$ 。如果 $j { \le } K$ ，转步骤(b)。

(e)按(9)式计算路段安全状态下的车速离散度的平均值 $\overline { { \varphi } } _ { \scriptscriptstyle L }$ ：

$$
\overline { { \varphi } } _ { L } = \frac { \displaystyle \sum _ { j = 1 } ^ { K } \varphi _ { L , j } } { K }
$$

f)将步骤b)计算出的路段车辆速度离散度 $\varphi _ { L }$ 与路段交通安全状态评估分级标准区间匹配，得到路段车辆速度离散度 $\varphi _ { L }$ 所属的安全等级区间，该区间所对应的道路安全状态等级即为该路段安全状态的评估结果。

![](images/71c93bd7c0e77f625914d8a003078569f7da6ec5b45e43407405de4569f0b355.jpg)  
图5路段交通安全状态评估方法流程图

表2路段安全状态下的样本车速离散度  

<html><body><table><tr><td></td><td>Π６８Ｌ９Ｓ→εＺ１</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>样本号</td></tr><tr><td></td><td>0</td><td></td><td>三 8</td><td>8</td><td>6 6</td><td></td><td></td><td>8.67</td><td>三</td><td>10.95 路段车速离散度φ (%)</td></tr></table></body></html>

e)输出道路交通安全状态的评估结果。

路段交通安全状态评估方法具体流程如图5所示。

# 3 实验与分析

# 3.1确定参数 $\overline { { \varphi } } _ { _ L }$

本节采用广州市某路段10个样本的交通数据进行分析。经过分析和筛选，当路段划分的检测断面数 $\scriptstyle { M = 8 }$ 时，实验效果较好。统计该路段处于安全状态下的样本车速离散度如表2所示。

通过表2可以得出安全状态下车速离散度得平均值$\overline { { \varphi } } _ { L } = 1 1 . 4 8 \%$ 。那么，对应安全A、较安全B、基本安全C、不安全D四个安全状态的路段车速离散度 $\varphi _ { L }$ 的取值区间分别为[0,5.74]、(5.74,11.48]、(11.48,17.22]、 $( 1 7 . 2 2 , + \infty )$

# 3.2路段安全状态评估

本节将采用本文提出方法对某路段的安全状态进行评估。通过分析实时视频信息，得到通过该路段第 $i$ 个断面的85位车速 $V _ { 8 5 , i }$ （ $\mathrm { k m / h }$ ）分别为： $V _ { 8 5 , 1 } { = } 4 4 . 9$ 、 $V _ { 8 5 , 2 } { = } 4 8 . 0$ 、 $V _ { 8 5 , 3 } { = } 5 0 . 8$ 、$V _ { 8 5 , 4 } { = } 4 2 . 9$ 、 $V _ { 8 5 , 5 } { = } 5 0 . 0$ 、 $V _ { 8 5 , 6 } { = } 5 3 . 0$ 、 $V _ { 8 5 , 7 } { = } 3 5 . 6$ 、 $V _ { 8 5 , 8 } { = } 5 0 . 6$ ；通过整条道路车辆的平均行驶速度 $ \overline { { V } } = 5 0 . 6 \mathrm { { k m } / h }$ 。

由式（9）计算得出路段车速离散度 $\varphi _ { L } = 1 0 . 9 5 \%$ 。将计算出的路段车辆速度离散度与路段交通安全状态评估分级标准区间匹配，得到路段车辆速度离散度 $\varphi _ { L }$ 所属的安全等级区间为$\left( \frac { \overline { { { \varphi } } } _ { L } } { 2 } , \overline { { { \varphi } } } _ { L } \right] = \left( 5 . 7 4 , 1 1 . 4 8 \right]$ 全状态，则可以得到该路段安全状态的评估结果为较安全状态。

# 4 结束语

本文从车速离散度的角度提出了影响城市路段交通安全状态的路段车速离散度的概念，并结合视频识别技术建立了基于路段车速离散度的路段交通安全状态评估方法。该方法可以根据视频信息计算出该路段的实时车速离散度，然后根据实时车速离散度对道路交通安全状态进行实时的评估。实验表明，该方法实施简单，能够对道路安全状态作出合理评价，评价结果可以为交通管理部门制定有效的城市路段交通安全改进方案提供相应的依据。所提方法可以利用城市道路已有的监控设备，而无须再多花费资金用于该评估方法的实施，做到了在有限资金下改善城市路段交通安全状态。

# 参考文献：

[1]孙璐，游克思．城市道路交通安全评价研究综述[J]．华东公路，2015(1): 3-6.  
[2]盖靖元．基于车速离散度的路段交通安全评估方法研究[D].南京：东南大学,2016.  
[3]Dobromirov V,Evtiukov S,Duncheva E,et al.Methodology and results ofthe traffic safety evaluation on the saint petersburg ring road [J]Transportation Research Procedia,2017,20:151-158.  
[4]方雪洋．混合交通环境下车速离散对交通安全的影响机理研究 [D].南京：东南大学,2015.  
[5]吴义虎，武志平．基于平均车速和车速标准差的路段安全分析方法[J].公路交通科技,2008,25(3):139-142.  
[6]Cao Binru,Liu Yong,Qian Wuyong,et al. Construction of the evaluationsystem for regional road traffic safety and application based on a greyintegrated evaluationmodel[C]//Proc of IEEE International Conference onGrey Systems and Intelligent Services.2015: 395-403.  
[7]Li Yaoping,Li Jianlin,Li Bin,et al. Study on Road Trafic Safety EvaluationBased on Improved Bayes Model[J].Applied Mechanics & Materials,2011,97-98: 489-493.  
[8]Wang Yafei, Zhang Dongxue.Evaluation of road trafic safety in Huai Yindistrict of Jinan city based on AHP [J].Applied Mechanics& Materials,2014,505-506:1167-1171.  
[9]魏武，张起森，王明俊，等．基于计算机视觉和图像处理的交通参数检测[J].信息与控制,2001,30(3):257-261.  
[10]王春波，张卫东，张文渊．复杂交通环境中车辆的视觉检测[J].上海交通大学学报,2000,34(12):1680-1682.  
[11] Stauffer C,Grimson W EL.Learning patterns of activity using real-timetracking[J].IEEE TransonPattern Analysis& Machine Intelligence,2000,22 (8): 747-757.  
[12]邵文坤，黄爱民，韦庆．目标跟踪方法综述[J].影像技术,2006(1):17-20.  
[13] Park.YJ,Mirandamoreno L F.Estimation of speed differentials on ruralhighwaysusing multilevel models [C]//Proc of the 89th Annual Meeting ofTransportation Research Board.2010:1-6.  
[14]王昊，王炜，陆建，等．基于跟驰理论的车速离散度定义及特性[J].东南大学学报：自然科学版,2009,39(1):161-165.  
[15]任彦铭，李铁柱，孙婵．城市主干路路段车速分布特性研究[J].交通运输工程与信息学报，2013,11(3):98-105.  
[16]杨院，韦玮．基于安全度的高速公路车辆行驶速度评价研究[J]．西华大学学报自然科学版,2009,28(3):39-42.