# 关于二面角影响扩张管道内角区附面层发展的数值研究

李嘉宾　田壮壮　季路成(北京理工大学大学宇航学院，北京 100081)

摘要固壁与固壁相交所成二面角对附近区域内附面层发展具有重要影响，尤其在风扇/压气机中，控制叶表与端壁相交二面角及其流向变化是调控角区分离的重要方向。本文以具有不同二面角的四种典型扩张管道(扩张角 $3 ^ { \circ }$ ）为模型案例，采用数值方法研究了不同二面角角下扩张管道内附面层发展规律，印证了二面角原理，并由数值计算结果拟合得到了分离位置经验公式。

关键词二面角、叶轮机、角区分离、附面层流动、扩张管道中图分类号：V211.6 文献标识码：A 文章编号：0253-231X(2017)05-0957-08

# Numerical Investigations on the Effects of Dihedral on the Development of Boundary Layer along Diffusion Pipes

LI Jia-Bin TIAN Zhuang-Zhuang JI Lu-Cheng A (School of Aerospaceand Engineering,Beijing Institute of Technology，Beijing 10o081,China)

AbstractThe dihedral angle between two intersected solid wall have great influence on the development of the boundary layersat the corner, especially on the fan or compressor. The controlling of the dihedral angle and its development along the streamwise is an important method to limiting the corner separation. This papr make an numerical investigation on four kinds of diffusion pipes with different dihedral angles.Through the numerical method, the law of the boundary layer development at different dihedral angle was investigated, which confrmed the dihedlal principle,and the dihedral principle is quantified through the investigation on diffusion pipesx.·

Key wordsdihedral angle； turbomachinery； corner separatlon; boundary layer flow; diffusionpipes.

# 0引言

固壁与固壁相交结构在流动构型中普遍存在,其所形成角区附面层流动异常复杂，角区二面角是其中关键影响因素。叶轮机中，叶片与端壁相交形成四个角隅，其流动以叶表和端壁附面层相交汇为主要特征，尤其叶片吸力面与端壁所形成的两个角隅因吸力面附面层比压力面厚得多而格外重要。在这里，特别是风扇/压气机中，二面角通常较小、沿流程递减且处于扩张流管的逆压环境，常会出现分离使风扇/压气机性能恶化。因此，在不断提高风扇/压气机负荷的发展进程中，充分认识角区流动机理、避免角区分离是重要环节，一直以来是相关领域的科研投入热点。例如，Joslyn[1］在某两级压气机上发现角区分离造成端区损失加倍。Dong 等[2]试验表明悬臂静叶由于叶根间隙流而减弱了角区分离。Breugelmans[3] 证实掠/倾叶片具有抑制二次流进而减弱角区分离的作用，而Barankiewicz[4]四级压气机试验表明，尽管使用了掠/倾叶片，高负荷运行工况下仍然出现角区分离。Gbadebo等[5]建立了预测极限流线和奇异点性质的拓扑规则，发现随奇异点数目增加，角区分离范围和损失都在增加。Lei[6]基于角区流动由基元叶栅和横向流动共同决定的认识，采用能够体现流向、横向压力梯度以及进口附面层状态的组合参数预测角区分离，取得了一定成功。

目前为止，有关角区附面层流动研究多在拓扑结构分析以及角区分离对叶轮机性能影响等方面，但极少关注角区附面层流动首先是以一定二面角相交的两个附面层交汇这一事实。鉴于此，本文以该物理认识为出发点，采用等水力半径的正三角形、正方形、正六边形、圆形截面管道模型孤立呈现固壁相交二面角分别为 $6 0 ^ { \circ }$ 、 $9 0 ^ { \circ }$ 、 $1 2 0 ^ { \circ }$ 、 $1 8 0 ^ { \circ }$ 时的附面层流动发展情况，采用3度扩张角来呈现类似风扇/压气机中出现的逆压环境影响。对这些模型在不同来流马赫数下的流动进行数值模拟，希望总结出不同二面角对角区附面层流动发展的影响规律。为不增加首次研究的复杂度，有关包含扩张角等参数影响的研究将在后续进行。

# 1二面角原理回顾

二面角概念最早由 Smith[7]在1963 年与掠概念同时提出，Lewis[8]进行了二者在叶轮机应用的研究，Debruge[9]推导了倒圆(看成是 $1 8 0 ^ { \circ }$ 二面角)对角区附面层流动的影响，但至此为止，尤其关于二面角对流动影响机理与使用规律，相关文献一直未给出深入明确阐释。以后的发展历程中，掠叶片技术在1990年代中后期取得突破性进展，而尽管有关联，弯叶片技术关注点却与二面角渐行渐远导致“正弯好还是反弯好”的疑问和公开文献中二面角尚未直接应用于指导设计的局面。

![](images/afe70ceb88a489fa2bf690c14d5fd2820ea5cea9e5d254460be8606fbb5b17e5.jpg)  
图1等效二维附面层位移厚度和动量损失厚度补偿假设与模型 Fig.1 The compensation hypothesis and model for equivalent two-dimensional boundary layer displacement thickness and momentum loss thickness

文献[10从二面角决定相交固壁附面层形态这一认识出发，基于“交汇区附面层状况由吸力面、端壁附面层相交以及对动量损失厚度和位移厚度搭叠部分的补偿决定”的假设，见图1所示，给出描述角区三维附面层的等效二维附面层模型，并结合Nash[11]二维附面层分离准则，建立了固壁交汇角区分离判定准则和以二面角视角控制角区流动规律如下：

1）二面角越小越容易分离，为避免角区分离，应使二面角尽可能大；

2）二面角 $\alpha$ 沿流向递减才有可能发生角区分 离，而二面角 $\scriptstyle { \alpha }$ 变化梯度绝对值越大，角区也就越 容易分离，为避免角区分离，应使二面角沿流向逐 渐增大，或者使面角沿流向逐渐减小过程尽量平缓， 尤其在二面角 $\alpha$ 较小的区域更应如此;

面角控制的尺度在附面层厚度量级上。

个正述二面角原理定性地指出了角区流动机理和控制方法，却未能精细展现二面角影响流动机理，也未能定量给出二面角与分离点位置等的关联关系。为此，本文以下采用雷诺平均N-S方程数值求解方法进行初步研究。

# 2数值模型

为排除流动构型具体几何结构及物理条件对所研究二面角问题的干扰，必须建立简单而有效的物理模型。在本文物理模型建构过程中，有两个要素需要考虑：一是要能在管道内流环境下考查不同二面角的影响二是要能体现恶劣的逆压环境影响。针对前者，本文采用等水力直径的正三角形、正方形、正六边形、圆形截面管道模型孤立呈现固壁相交二面角分别为 $6 0 ^ { \circ }$ 、 $9 0 ^ { \circ }$ 、 $1 2 0 ^ { \circ }$ 、 $1 8 0 ^ { \circ }$ 时的附面层流动发展情况；针对后者，采用3度扩张角来呈现类似风扇/压气机中出现的逆压环境影响，最终本文研究二面角影响所采用的流动构型几何模型如图2所示。

对这些模型在不同来流马赫数下的流动进行数值模拟，希望总结出不同二面角对角区附面层流动发展的影响规律。为不增加首次研究的复杂度，有关包含扩张角等参数影响的研究将在后续进行。

本文研究正三角形、正四边形、正六边形和圆形截面扩张管道的角区附面层交汇规律，如图5所示。4种截面形状扩张管道的进口水力直径均为100mm，管道长度均为 $1 0 0 0 \mathrm { m m }$ ，扩张角均为 $3 ^ { \circ }$ 。各扩张管道的进口截面的几何尺寸如表1所示：

计算使用的网格用ICEM生成，各种截面形状的网格量如表1所示，网格近壁最小间距为0.01$\mathrm { m m }$ ，各工况下计算得到的 $y ^ { + }$ 值均在10以下，各截面形状扩张管道网格拓扑如图3所示。

![](images/59ffa874d7b0a8fa2df02624ae6725ddfbec5d11831e0258d2207c2fd4f6057c.jpg)  
图2四种扩张管道几何模型示意图 Fig.2 The geometry of the four types diffusion pipes with different dihedral angles

# 表14种截面形状扩张管道几何与网格量

Table 1 The geometry of the diffusion pipes and the total number of the mesh points   

<html><body><table><tr><td>截面形状</td><td>二面角</td><td>边长/直径/mm</td><td>网格量/104</td></tr><tr><td>正三角形</td><td>60°</td><td>1732</td><td>49</td></tr><tr><td>正四边形</td><td>90°</td><td>100</td><td>67</td></tr><tr><td>正六边形</td><td>120°</td><td>57.7</td><td>69</td></tr><tr><td>圆形</td><td>180°</td><td>100</td><td>47</td></tr></table></body></html>

![](images/f7dbee5ee378a6fa17a58bf6b97412b1aab83dcc2f0e621445024504134f70c8.jpg)  
图3四种扩张管道网格拓扑示意图 Fig.3 The mesh topology of different diffusion pipes

设置进口边界条件总压 $1 0 1 3 2 5 \mathrm { P a }$ ，总温288.15

K；出口设置不同背压工况，得到一系列进口马赫数下的流场结果；壁面均为无滑移壁面，湍流模型为 $k \mathrm { . }$ $\varepsilon$ 模型；控制方程使用高阶离散格式进行空间离散。具体边界条件设置如图4所示。

图4扩张管道数值计算边界条件施加示意图  
![](images/f2ab5a0f5f9fcce40bde6c3060f277d94360806b383b61365ef545d047f16b66.jpg)  
4The boundary layer imposed at the numerical study

# 3数值模拟结果

在进口条件总压 $1 0 1 3 2 5 \ \mathrm { P a }$ ，总温288.15K固定不变的情况下，调整不同出口背压，得到不同进口马赫数下的扩张管道流动情况，不同截面扩张管道出口背压与进口马赫数的对应关系如表2所示。

# 表2不同扩张管道出口背压（kPa）与进口马赫数对应关系

Table 2 ·The outlet pressure and the corresponddiffusion pipes

<html><body><table><tr><td>Ma</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td><td>0.8</td></tr><tr><td>正三角形</td><td>98</td><td>96</td><td>93</td><td>90</td><td>88</td><td>86</td></tr><tr><td>正四边形</td><td>99</td><td>97.5</td><td>96</td><td>94</td><td>92.5</td><td>91.4</td></tr><tr><td>正六边形</td><td>99.5</td><td>98.3</td><td>97</td><td>95.5</td><td>94.5</td><td>93.5</td></tr><tr><td>圆型</td><td>99.8</td><td>98.7</td><td>97.5</td><td>96.5</td><td>95.5</td><td>94.5</td></tr></table></body></html>

从表2可以发现两个现象，1）为了获得更高的进口马赫数，出口背压应减小；2）随着二面角的增大，需要保证某一出口马赫数的背压不断增加，这也从侧面说明了二面角越小的扩张管道，其在同一进口马赫数下的堵塞情况越严重。

在进口马赫数为 $0 . 3 { \sim } 0 . 8$ 的情况下，四种正多边形截面扩张管道的分离起始位置 $P$ ，总压恢复系数$\omega$ ，壁面附面层失速前动量厚度 $\theta _ { 1 }$ ，位移厚度 $\delta _ { 1 }$ ，以及角区附面层失速前动量厚度 $\theta _ { 2 }$ ，位移厚度 ${ \delta } _ { 2 }$ 如表$3 { \sim } 8$ 所示，其中正六边形截面管道与圆形管道没有分离。

Table 3 The flow condition of the different diffusion pipes when inlet mach number is 0.3   

<html><body><table><tr><td>a/(）</td><td>P/mm</td><td></td><td>01/mm</td><td>02/mm</td><td>δ1/mm</td><td>82/mm</td></tr><tr><td>60</td><td>510</td><td>0.9936</td><td>1.54</td><td>4.03</td><td>2.26</td><td>11.33</td></tr><tr><td>90</td><td>980</td><td>0.9937</td><td>5.91</td><td>9.25</td><td>9.56</td><td>27.05</td></tr><tr><td>120</td><td>1</td><td>0.9953</td><td>7.68</td><td>10.1</td><td>13.55</td><td>23.64</td></tr><tr><td>180</td><td>1</td><td>0.9956</td><td>9.51</td><td>1</td><td>19.04</td><td>二</td></tr></table></body></html>

Table 4 The flow condition of the different diffusion pipes when inlet mach number is 0.4

表3 ${ \cal M } a = 0 . 3$ 下四种截面扩张管道流动情况   

<html><body><table><tr><td>a/(）</td><td>P/mm</td><td></td><td>01/mm/</td><td>02/mm</td><td>δ1/mm</td><td>82/mm</td></tr><tr><td>60</td><td>471</td><td>0.9836</td><td>1.33</td><td>3.49</td><td>1.97</td><td>10.01</td></tr><tr><td>90</td><td>959</td><td>0.9881</td><td>5.65</td><td>8.97</td><td>9.11</td><td>26.11</td></tr><tr><td>120</td><td>1</td><td>0.9888</td><td>79</td><td>10.19</td><td>13.83</td><td>24.18</td></tr><tr><td>180</td><td>二</td><td>0.9891</td><td>Y>9.77</td><td>1</td><td>19.04</td><td>二</td></tr></table></body></html>

表5 $M \mathbf { a } = \mathbf { 0 . 5 }$ 下四种截面扩张管道流动情况   

<html><body><table><tr><td>a/(）</td><td>P/mm</td><td>W</td><td>01/mm</td><td>02/mm</td><td>81/mm</td><td>2/mm</td></tr><tr><td>60</td><td>498</td><td>0.9897</td><td>1.45</td><td>3.81</td><td>2.15</td><td>10.87</td></tr><tr><td>90</td><td>967</td><td>0.9916</td><td>5.85</td><td>9.22</td><td>9.44</td><td>27.05</td></tr><tr><td>120</td><td>1</td><td>0.9922</td><td>7.68</td><td>10.08</td><td>13.6</td><td>23.75</td></tr><tr><td>180</td><td>二</td><td>0.9925</td><td>9.58</td><td>二</td><td>19.23</td><td>二</td></tr></table></body></html>

Table 5 The flow condition of the different diffusionpipes when inlet mach number is 0.5   
表 $6 \ll \frac { \hbar \hbar \mu \pm } { 2 } 0 . 6$ 下四种截面扩张管道流动情况   

<html><body><table><tr><td>a/(）</td><td>P/mm</td><td></td><td></td><td>01/mm</td><td>02/mm</td><td>δ1/mm</td><td>52/mm</td></tr><tr><td>60</td><td>443</td><td rowspan="5"></td><td>0.9746</td><td>1.11</td><td>2.93</td><td>1.6</td><td>8.42</td></tr><tr><td>90</td><td>938</td><td>0.9834</td><td>4.85</td><td>7.77</td><td>7.77</td><td>22.51</td></tr><tr><td>120</td><td>1</td><td>0.9848</td><td>7.99</td><td>10.38</td><td>14.27</td><td>24.95</td></tr><tr><td>180</td><td>二</td><td>0.9862</td><td>9.95</td><td>· e</td><td>20.28</td><td>1</td></tr></table></body></html>

表4 $\mathbf { { \mathit { M } } } \mathbf { { a } } \mathbf { = } \mathbf { { 0 . 4 } }$ 下四种截面扩张管道流动情况   
表7 $M \mathbf { { a } = 0 . 7 }$ 下四种截面扩张管道流动情况   

<html><body><table><tr><td>α/()</td><td>P/mm</td><td></td><td>0mm</td><td>02/mm</td><td>81/mm</td><td>2/mm</td></tr><tr><td>60</td><td>423</td><td>0.9666</td><td>X0.97</td><td>2.57</td><td>1.45</td><td>7.65</td></tr><tr><td>90</td><td>908</td><td>0.9797</td><td>4.24</td><td>6.92</td><td>6.75</td><td>19.63</td></tr><tr><td>120</td><td>1</td><td>0.9821</td><td>8.17</td><td>10.56</td><td>14.66</td><td>25.63</td></tr><tr><td>180</td><td>二</td><td>0.9832</td><td>10.2</td><td>1</td><td>21.0</td><td>1</td></tr></table></body></html>

Table 7 The flow condition of the different diffusion pipes when inlet mach number is 0.7

Table 6 The flow conditionf the different diffusion pipes when inlet mach number is 0.6   
表8 $M \mathbf { { a } = 0 . 8 }$ 下四种截面扩张管道流动情况   
Table 8 The flow condition of the different diffusion pipes when inlet mach number is 0.8   

<html><body><table><tr><td>a/(）</td><td>P/mm</td><td></td><td>01/mm</td><td>02/mm</td><td>δ1/mm</td><td>82/mm</td></tr><tr><td>60</td><td>390</td><td>0.9579</td><td>0.66</td><td>1.86</td><td>1.01</td><td>5.51</td></tr><tr><td>90</td><td>873</td><td>0.9768</td><td>1.16</td><td>2.19</td><td>1.77</td><td>4.83</td></tr><tr><td>120</td><td>1</td><td>0.9803</td><td>8.41</td><td>10.79</td><td>15.17</td><td>26.5</td></tr><tr><td>180</td><td>二</td><td>0.9802</td><td>10.53</td><td>二</td><td>21.95</td><td>二</td></tr></table></body></html>

上述给出了4种不同正多边形截面扩张管道在不同马赫数下的流动分离情况，以及轴向速度分布云图。从中可以看出，在同一马赫数下随着管道二面角的增大，流动分离起始位置沿流程向后增大，管道流动的总压恢复系数增大；而在同一管道二面角下随着进口马赫数的增大，流动分离起始位置沿流程向后减小，管道流动的总压恢复系数减小。

# 4经验规律分析

为得到流动在同一扩张角，不同马赫数和二面角下的流动分离规律，对上述得到的不同正多边形截面管道数据进行拟合整理，以期望能够得到指导叶轮机叶片角区二面角设计的经验公式。

# 4.1总压恢复系数

第三章给出了不同正多边形截面管道在不同进□马赫数下的总压恢复系数情况。图5为总压恢复系数等值云图，横坐标为进口马赫数，纵坐标为壁面交汇的二面角，从图中可以看出在 $1 0 ^ { \circ }$ 扩张角下,当管道二面角不变时，管道的总压恢复系数随着进口马赫数的增大而减小，在亚声速扩张管道中，进□马赫数增大会使壁面黏性系数增大，使得总压恢复系数减小。而当管道进口马赫数不变时，管道总压恢复系数随着管道壁面二面角的增大而增大，这也与前面阐述的二面角原理的定性结论相一致。从等值云图分布可以看出，尤其在高马赫数下，角对管道的总压恢复系数影响十分明显。

![](images/a20c7d61f8190d0f00e284fe21492c18e4bcfd81e22c3d297e1a5369ed3eab51.jpg)  
图5总压恢复系数等值云图  
Fig.5 Equivalent cloud map for total pressure loss coefficient

$$
\omega = f \left( M a , \alpha \right) = p _ { 0 0 } + p _ { 1 0 } \cdot M a +
$$

$$
p _ { 0 1 } \cdot \alpha + p _ { 1 1 } \cdot \alpha \cdot M a +
$$

$$
\begin{array} { c } { { \displaystyle \left( p _ { 0 2 } + p _ { 1 2 } \cdot M a \right) \cdot \alpha ^ { 2 } + p _ { 0 3 } \cdot \alpha ^ { 3 } } } \\ { { \displaystyle \left. \frac { \partial \omega } { \partial M a } = p _ { 1 0 } + p _ { 1 1 } \cdot \alpha + p _ { 1 2 } \cdot \alpha ^ { 2 } \right. } } \end{array}
$$

函数系数如表9所示，多项式拟合优度如表10所示。

![](images/ceb3e6571fc922aa54c5c2e90036db84785cffd920b73ff469e6cc20e2974523.jpg)  
图6总压恢复系数多项式拟合结果  
Fig.6 The polynomial fitting results of the total pressure loss

<html><body><table><tr><td colspan="2">coefficient 表9 多项式函数系数 Table 9 The coefficcient of the polynomial function</td></tr><tr><td>P00 et Y</td><td>1.019</td></tr><tr><td>p10</td><td>-0.1655</td></tr><tr><td>P01</td><td>0.0002483</td></tr><tr><td>P11</td><td>0.001994</td></tr><tr><td>P02</td><td>-6.16E-06</td></tr><tr><td>P12</td><td>-6.95E-06</td></tr><tr><td>P03</td><td>2.42E-08</td></tr></table></body></html>

为得到管道总压恢复系数对进口马赫数及壁面二面角的函数关系，对数值计算数据进行多项式拟合，拟合得到的曲面结果如图6所示，拟合得到的函数关系如下式所示，总压恢复系数与进口马赫数Ma一次相关，与壁面二面角 $\scriptstyle { \alpha }$ 三次相关。由总压恢复系数对马赫数的偏导数可知，在扩张角与壁面二面角确定的情况下，总压恢复系数对马赫数可近似看作线性变化关系。

表10多项式函数拟合优度  

<html><body><table><tr><td colspan="2">Table 10 The goodness of the fit</td></tr><tr><td>残差平方和 SSE</td><td>3.165E-05</td></tr><tr><td>R-square</td><td>0.9835</td></tr><tr><td>均方根误差RMSE</td><td>0.001365</td></tr></table></body></html>

# 4.2分离位置与最大分离速度

正多边形管道在不同马赫数下的分离位置如图8所示，从图中可以发现，在固壁二面角相同的情况下，分离位置随管道进口马赫数成二次函数关系，进口马赫数越大，管道的分离位置越靠前；而在进口马赫数相同的情况下，固壁二面角的大小对分离起始位置的影响非常明显，如图7所示，当壁面二面角从 $9 0 ^ { \circ }$ 到 $6 0 ^ { \circ }$ 变化时，分离起始位置提前了近 $5 0 \%$ 5可见内流流动中的角区固壁二面角设计对流动分离的影响之大。

![](images/b1102401ae428a936a8d5d54563e0f2f8fa6d7b7ca3f0c1c179697531d7cf354.jpg)  
图7不同马赫数下的分离位置

# 4.3附面层分离厚度

在二面角原理的第三条假设中交汇区附面层状况由吸力面、端壁附面层相交以及对动量损失厚度和位移厚度搭叠部分的补偿决定，即用 $\theta _ { \mathrm { e f } }$ 来近似角区附面层的动量厚度 $\theta _ { \mathrm { c o r n e r } }$ ，即

$$
\theta _ { \mathrm { e f } } = \theta _ { \mathrm { i n } } + \theta _ { \mathrm { a d d } }
$$

$$
\theta _ { \mathrm { i n } } = \sqrt { \theta _ { \mathrm { s u c } } ^ { 2 } + \theta _ { \mathrm { e w } } ^ { 2 } + 2 \theta _ { \mathrm { s u c } } \theta _ { \mathrm { e w } } \cos \alpha } \Big / \sin \alpha
$$

$$
\theta _ { \mathrm { a d d } } = \sqrt { \left( \theta _ { \mathrm { s u c } } ^ { 2 } + \theta _ { \mathrm { e w } } ^ { 2 } \right) \cos \alpha + 2 \theta _ { \mathrm { s u c } } \theta _ { \mathrm { e w } } } \Big / \left[ 2 \sin \left( \alpha / 2 \right) \right]
$$

其中 $\alpha$ 为吸力面与端壁相交的二面角，同理，角区等效二维附面层位移厚度也可以用动量厚度的方法来处理。

为了验证附面层几何搭叠假设的合理性，从数值计算结果中计算得到了管道分离前壁面中部以及角区的附面层动量厚度与位移厚度，由于数值计算中只有正三角形管道及正四边形管道存在流动分离，下面关于附面层分离前厚度值问题的讨论只采用正三角形与正四边形的数据。

图8展示了正三角形与正四边形截面管道的壁面中部分离前附面层厚度随管道进口马赫数的变化关系，从图中可以看出，正三角形截面管道由于壁面二面角较小，附面层厚度在较小的情况下就会发生分离，而正四边形截面管道能够容许的附面层厚度相比增大了 $2 { \sim } 3$ 倍；同时可以发现，在同一管道中，随着进口马赫数的增加，分离前的附面层厚度变小，说明主流速度通过影响壁面切应力的大小，对附面层的分离也具有一定的影响。

![](images/375976de75382cdc5ce16ec70a28cbd0debcc3336e3889c6d6de13b2e026631a.jpg)  
Fig.7 The detached position at different inlet Mach number   
图8远离角区的壁面中部位置处分离前附面层厚度随进口马赫 数的变化关系 Fig.8 The boundary layer thickness at the center of the wall changes with the inlet Mach number

将图8所示的壁面附面层厚度代入式(1)、式(2）中可计算得到二面角原理下角区附面层的厚度，图9展示了CFD计算得到的角区附面层高度与二面角原理计算得到的理论高度的对比。从中可以看到，基于附面层几何搭叠假设的二面角原理对角区附面层高度的计算存在一定的误差，动量损失厚度要小于动量损失厚度的理论值，而位移损失厚度要大于位移损失厚度的理论值，但在趋势上是完全一致的。因此，二面角原理对角区分离的定性预测是合理的。

![](images/19250666af6e1e456153a56603b6f324f3115f18ab0e2a3b0b066835dc8a15e4.jpg)

由前文所述，附面层形状因子 $H = \delta ^ { * } / \theta$ ，其值大小可以判断附面层分离与否，本文引入参数 $\mathbb { V } =$ $\mathrm { d } H / \mathrm { d } x$ ，其中 $\mathbf { \Psi } _ { x }$ 为无量纲管道的流向尺度，用以表征不同截面形状管道附面层的分离快慢。计算不同壁面二面角管道下的 $\psi$ 值如图10所示，从图中可以看出，进口马赫数对 $\psi$ 的影响不大， $\psi$ 值得大小在本文扩张角一定的情况下主要与壁面二面角有关，且二面角越小， $\psi$ 值越大，即壁面附面层越容易分离；随着二面角的增大， $\psi$ 值得增长率变大，即随着壁面二面角的减小，角区分离恶化速度并非成线性速度增加，而是恶化的越来越快。那么，角区分离恶化速度的快慢与壁面二面角的关系究竟怎样呢？

既然角区分离的恶化速度与进口马赫数基本无关，本文取同一壁面二面角管道在不同进口马赫数下 $\psi$ 的平均值 $\hat { \psi }$ 作为这一二面角下角区分离恶化速度的衡量值， $\hat { \psi }$ 随壁面二面角的变化规律如图11所示， $\hat { \psi }$ 值随壁面二面角的减小成指数型增长，对其进行函数拟合如式(3)所示。

$$
\bar { \psi } = 2 4 6 \cdot \mathrm { e } ^ { - 0 . 0 7 \alpha } + 3 . 2 \cdot \mathrm { e } ^ { - 0 . 0 0 3 \alpha }
$$

![](images/f7448150c0a0d6266a873255e4ae5613c1ad6c6180a018bf5e45157545b0ba2e.jpg)  
图10 不同壁面二面角管道下的 $\psi$ 值Fig.10 The $\psi$ value with different dihedral angle

![](images/69e1cf29768d7a0ba58976d57371f6c505396bf20d0f6b693b21d8b09570a060.jpg)  
图9角区附面层高度理论值与仿真值对比 Fig.9 The comparison of the theory value and the CFD value of the corner boundary layer thickness   
图11 $\hat { \psi }$ 随壁面二面角的变化规律 Fig.11 The $\bar { \psi }$ value with different dihedral angle

# 5结论

本文依据二面角原理设计数值计算，通过计算不同正多边形截面扩张管道的流动分离情况对二面角原理中的假设进行验证，并对二面角原理的结论进行了定量化研究。获得了以下结论：

1）在相同进口水力直径下，扩张角相同的异形扩张管道在达到相同马赫数时出口被压条件是不同的。其中从正三角形截面到圆形截面管道，二面角从 $6 0 ^ { \circ }$ 到 $1 8 0 ^ { \circ }$ 变化，出口背压单调增加，说明二面角越大，扩张管道的堵塞与损失越小。

2)在 $1 0 ^ { \circ }$ 扩张角下，当管道二面角不变时，管道的总压恢复系数随着进口马赫数的增大而减小；而当管道进口马赫数不变时，管道总压恢复系数随着管道壁面二面角的增大而增大；在低马赫数下二面角对管道的总压恢复系数影响较小，而在高马赫数下二面角对管道的总压恢复系数影响很明显；总压恢复系数与进口马赫数Ma一次相关，与壁面二面角 $\scriptstyle { \alpha }$ 三次相关。

3)在固壁二面角相同的情况下，分离位置随管道进口马赫数成二次函数关系，进口马赫数越大，管道的分离位置越靠前；而在进口马赫数相同的情况下，固壁二面角的大小对分离起始位置的影响非常明显。

4)基于附面层几何搭叠假设的二面角原理对角区附面层高度的计算存在一定的误差，动量损失厚度要小于动量损失厚度的理论值，而位移损失厚度要大于位移损失厚度的理论值，但在趋势上是完全一致的。因此，二面角原理对角区分离的定性预测是合理的。

5)某一二面角下角区分离恶化速度的衡量值随壁面二面角的减小成指数型增长，因此，二面角越小，角区流动越容易分离，且二面角对附面层形状因子沿流程的变化速度的影响为指数型的。

# 参考文献

[1] Joslyn H,and Dring R. Axial Compressor Stator Aerodynamics [J].Journal of Engineering for Gas Turbines and

Power,1985,107(2):485-493   
[2] Dong Y，Gallimore S,Hodson H. Three-Dimensional Flows and Loss Reduction in Axial Compressors [J]. Journal of Turbomachinary,1987,109(3):354-360   
[3]Breugelmans F,Carels Y,Demuth M.Influence of Dihedral on the Secondary Flow in a Two-Dimensional Compressor Cascade [J]. Journal of Engineering for Gas Turbines and Power,1984,106(3):578-584   
[4]Barankiewicz W,Hathaway M.Impact of Variable Geometry StatorHub Leakage inaLow Speed Axial Compressor [R].ASME Paper 98-GT-194,1998   
[5] Gbadebo S,Cumpsty N,Hynes T.Three-Dimensional Separations in Axial Compressors [J]. Journal of Turbomachinary,2005,127(2):331-339   
[6]LeiV,SpakovszkyZS,GreitzerEM.ACriterion forAxial Compressor Hub-Corner Stall [R].ASME Paper GT2006- 91332,2006   
[7] Smith L H,Yeh H.Sweep and Dihedral Effect in Axial Flow Tutbomachinery [J]. Journal of Basic Engineering, 1963.85 401-416   
[8] LewisR I, Hill JM. The Influence of Sweep and Dihedral in Turbomachinery Blade Rows [J]. Journal of Mechanical Engineering Science,1971,13(4):266-285 9]Debruge L L.The Aerodynamic Significance of Fillet Geometry in Turbocompressor Blade Rows [J].Journal of Engineering for Power,1980,102(11): 984-993   
[10]JI Lucheng,SHAO Weiwei,YI Weilin,et al.A Model for Describing the Influences of SUC-EW Dihedral Angle on Corner Separation [R].ASME Paper GT2007-27618,2007   
[11]Nash J,McDonald.The Calculation of Momentum Thickness in a Turbulent Boundary Layer at Mach Numbers up to Unity [C]//Aeronautical Research Council C P No 963, 1967 >

![](images/0a143c22c2030dae9134ae2a1b35e549c2eea8bf2643d8cea1c753bc9bb91f41.jpg)