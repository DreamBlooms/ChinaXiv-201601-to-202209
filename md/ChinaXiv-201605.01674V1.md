# 基于坐标系转换与QTM编码的天球面探测覆盖栅格化分析方法研究

杨震1,2 高辰1.2 牛文龙1,2 孟新1 李大林1

1(中国科学院空间科学与应用研究中心中国科学院复杂航天系统电子信息技术重点实验室北京 100190)

2(中国科学院大学北京 100049)

摘要提出一种基于坐标系转换与QTM编码的天球面探测覆盖栅格化分析方法，并对其计算精度和效率进行了实验分析，相比传统算法和经纬网格编码方法，该方法具有明显的效率和精度优势，能够满足以天球面为探测目标的空间科学卫星有效载荷探测覆盖分析和任务规划的需要，

关键词 天球面,覆盖分析,坐标系转换,QTM,编码中图分类号V44

# A Fast Calculation Method for Coverage Analysis of Space Telescope Based on Coordinates Transformation and QTM Code

YANG Zhen $^ { 1 , 2 }$ （20 GAO Chen $^ { 1 , 2 }$ NIU Wenlong $^ { 1 , 2 }$ （20 MENG Xin $\cdot ^ { 1 }$ （204 LI Dalin1

1(Key Laboratory of Electronicsand Information Technology for Space Systems,Center for Space Science and Applied Research，Chinese Academy of Sciences,Beijing 100190) 2(University of Chinese Academy of Sciences,Beijing 100049)

Abstract In sky coverage analysis, we present an effcient algorithm based on a coordinate transformation method to calculate the points on the boundary of detection feld. In this method, the complexity of coordinates transformation is reduced by building a new Celestial Coordinates. Based on this algorithm, QTM,a coding method that has many advantages can be used to manage the data calculated. The main contents of this topic include: to build the quantitative calculation model for sky coverage; to establish the rasterized expression method of sky coverage analysis results; and to verify the method,analyse the accuracy of the method,compare the efficiency with the attitudematrix transformation method and analytical method.

Key wordsCelestial surface, Cavalcade approach method, Coordination translation, QTM, Address code

# 0 引言

中国科学院空间科学先导专项计划在“十二五”期间发射5颗空间科学卫星,其中,硬X射线调制望远镜卫星和暗物质粒子探测卫星的探测对象是硬X射线、高能电子和伽马射线等宇宙辐射,将采用巡天观测、定点观测等不同观测模式对空间进行观测.在对这两颗卫星进行地面运行控制的过程中，需要频繁计算一定时间段内其探测载荷在不同位置、姿态和工作模式下的探测视场对探测目标或探测区域的覆盖情况，作为任务规划的输入条件和依据，这是通过任务规划方法寻求最优控制方案的前提条件[1].

天文观测等对天观测的观测对象和探测覆盖范围一般采用天球坐标系来描述，天球坐标系是天文学中常用的坐标系[2]．在天文学中，天球是一个假想的球，理论半径无限大，球心即地心.天空中所有物体均被投影到天球的球面上，基于地心赤道惯性坐标系[3]的天球与地球相对应,也具有天赤道和天极．其中天赤道即地赤道在天球上的投影，天极即地球极点在天球上的投影.天球面投影如图1所示．星空界面中RA（RightAscension）为赤经,表示天体投影点到春分点的角度距离，用时、分、秒来表示;偏差（Dec-lination）为赤纬，表示天体投影点到天赤道的角度距离,单位用度、分、秒来表示[4.

![](images/08a8c6568ab745391121befd76dab7dc8ab47cfed9df675ecff84c8626de7c70.jpg)  
图1天球面投影示意 Fig.1 Celestial projection

在近地卫星的天球面探测覆盖分析中，对于星体而言，卫星位置的变化可以忽略不计，其探测视场在天球面上投影的形状和大小保持不变，因而只需求解出观测矢量在天球面上投影点的赤经和赤纬即可求解天球面瞬时覆盖范围.

但是，当前中国在天球面覆盖分析方面的关注和研究较少，现有成熟的对地探测覆盖计算模型在应用于天球面覆盖分析时存在一些局限性，在效率及计算精度等方面难以满足天球面探测覆盖快速计算的要求，需要开展专门的覆盖分析方法研究．设计实现天球面探测覆盖分析方法，需重点解决的技术问题主要包括以下两个方面，

# (1)计算效率

在卫星运行控制过程中，一次任务规划涉及的时间周期非常长 (一个月甚至一年)，在如此大的时间跨度内，需按照一定时间步长根据地球公转、卫星轨道位置、姿态参数和工作模式等进行频繁计算,运算量巨大．如何在确保计算精度的前提下通过算法改进提高计算效率和速度，是工程实现中需要重点解决的问题.

# (2)覆盖计算结果的栅格化表达

由于有效载荷探测视场一般采用解析式的几何形状来描述，而任务规划算法需要以栅格化的覆盖计算结果作为输入，为实现对天球面剖分编码效率、数据处理精度及计算速度等各个指标的兼顾，应考虑选用合适的球面网格化方法来管理探测目标和探测区域，并实现计算结果的快速转换

# 1基于坐标系转换的天球面探测覆盖快速算法

# 1.1空间载荷探测视场的数学描述

对空间进行观测的卫星有效载荷探测视场，按其空间属性可以划分为以下两类[5].

(1）矩形锥视场

其视场形状可使用两个方向的张角 $\alpha , \beta$ 来描述矩形锥探测视场的4条边在天球面上的投影是4个顶点 $A , B , C , D$ 之间的球面大圆弧,有效载荷矩形锥视场在天球面上的探测覆盖范围是由这4条球面大圆弧所围成的区域，其中 $A B , C D$ 球面大圆劣弧长为 $\beta$ 而 $A D , B C$ 球面大圆劣弧长为 $\alpha$ ，如图2所示，

# (2）圆锥视场

其视场形状可使用圆锥的轴及半张角 $\lambda$ 来描述圆锥探测视场的轴与天球面的交点为 $P$ ，圆锥探测视场的各条母线与天球面的交点形成一个以 $P$ 为中心的球面小圆，有效载荷矩形锥视场在天球面上的探测覆盖范围是由以天球面 $P$ 点为圆心、半径为 $\lambda$ 的球面小圆所围成的区域，如图3所示.

# 1.2 快速求解算法

由空间载荷探测视场的数学描述分析可知，其覆盖求解可简化为球面大圆弧段的求解问题和已知圆心与球面半径的球面小圆求解问题．关于球面大圆的求解问题，在航空、航海等领域已有一些成熟算法，

洪德本提出了一种用解析法设计大圆航线的计算方法,并将其用于计算机解算[6],通过解算大圆航线，求出大圆航路上各点坐标、航向及航程.该算法利用球面三角余弦定理计算得到大圆航程，然后将大圆航程按一定间隔划分为若干段，各段的距离即为各航路点之间的航程，由球面三角正弦定理可得各段分割点 (即航路点)的坐标.该算法的计算比较简单，并且可以根据计算精度需要调整各分割点之间的间隔但是航线设计的主要目的是确定航向角，因而每个分割点均须计算航向角，增加了计算量，并且由于其近似认为在每个分割弧段内的航向角为恒定值，造成了累积误差，不能够适应天球面探测覆盖计算的需要.对于球面小圆的求解，通常采用在三维直角坐标系下求解出球面小圆各点的坐标值，再将其转换为经纬度坐标的方法.

![](images/566c6e01f972e75fad0f0586a7ca40cdd407eb085072b791a69fba570ff52c9a.jpg)  
图2矩形锥视场探测覆盖范围

针对上述算法的不足,本文提出一种基于坐标系转换的天球面探测覆盖快速算法，在天球坐标系下取任意一点 $N ^ { \prime }$ (其在天球坐标系下的坐标为赤纬 $\lambda _ { 0 }$ 赤经 $\varphi _ { 0 }$ ）作为新的天极点，以通过 $N ^ { \prime }$ 的天球面大圆弧为 $0 ^ { \circ }$ 赤经，建立新的球面坐标系，新建立的球面坐标系与天球坐标系的几何关系如图4所示.

![](images/eb3b7ad33831a560babc6295a7001debe9a19947abdc7ed6b7d4c8653745d242.jpg)  
图3圆锥视场探测覆盖范围

![](images/82a6456dbedfa84c02d6006270a196ec0fbb2432c82b8abd8c6dabf1dc6c8526.jpg)  
Fig.2Projection to the celestial surface of rectangle awl detection field   
Fig.3Projection to the celestial surface of circular cone detection field   
图4新建球面坐标系与原天球坐标系的几何关系 Fig.4 Relationship between the two celestial coordinates

新建立的球面坐标系与天球坐标系类似，也是球面坐标系，不同的是新建球面坐标系的 $Z$ 轴指向是 $N ^ { \prime }$ 点方向， $( \lambda _ { 0 } , \varphi _ { 0 } )$ 是 $N ^ { \prime }$ 点的天球坐标，与其垂直的大圆面为球面坐标系的赤道， $X ^ { \prime }$ 轴和 $Y ^ { \prime }$ 轴在其赤道平面内, $N ^ { \prime }$ 点和北天极点 $N$ 确定的子午线为零度子午线.天球面的一点由纬度 $\lambda ^ { \prime }$ (该点与球心 $O$ 点连线与赤道的夹角)和经度 $\varphi ^ { \prime }$ (过该点的子午面与过北天极点的子午面之间的夹角）来标识

对于天球面上任意一点，其在新建立的球面坐标系下的坐标 $( \lambda ^ { \prime } , \varphi ^ { \prime } )$ 与天球坐标系下的坐标 $( \lambda , \varphi )$ 之间的转换关系为[7]：

$$
\left\{ \begin{array} { l l } { \cos \lambda ^ { \prime } = - \cos \lambda \cos \lambda _ { 0 } - } \\ { \qquad \sin \lambda \sin \lambda _ { 0 } \cos ( \varphi - \varphi _ { 0 } ) , } \\ { \sin \varphi ^ { \prime } = \sin \lambda \sin ( \varphi - \varphi _ { 0 } ) \csc \lambda ^ { \prime } , } \\ { \cos \lambda = \cos \lambda \cos \lambda _ { 0 } - \sin \lambda ^ { \prime } \sin \lambda _ { 0 } \cos \varphi ^ { \prime } , } \\ { \qquad \sin ( \varphi - \varphi _ { 0 } ) = \sin \lambda ^ { \prime } \sin \varphi ^ { \prime } \csc \lambda . } \end{array} \right.
$$

根据探测视场边界的几何特点，建立新的天球面坐标系，在新的坐标系下进行求解，可以大幅度减少计算量.

# 1.3 算法实现

对于矩形锥探测视场,选取矩形视场一条边的一个顶点为新球面坐标系下的北极点，定义矩形视场该条边所在的半圆弧为新球面坐标系下的 $0 ^ { \circ }$ 赤经，则矩形锥视场该条边在新球面坐标系下经度为 $0 ^ { \circ }$ ，纬度范围在 $( 9 0 ^ { \circ } - \alpha )$ 或 $( 9 0 ^ { \circ } - \beta )$ 至 $9 0 ^ { \circ }$ 之间，然后依据式（1）可将矩形视场该条边上各点在天球面坐标系下的赤经赤纬坐标快速求出，如图5所示

对于圆锥探测视场，选取视场中心点为新球面坐标系下的北极点，则圆锥视场边界线在新球面坐标系下的经度在 $0 ^ { \circ }$ 至 $3 6 0 ^ { \circ }$ 之间,纬度为 $( 9 0 ^ { \circ } - \lambda )$ ，然后同样依据式（1）可将圆锥视场边界上各点在天球面坐标系下的赤经赤纬坐标快速求出，如图6所示.在算法的实现中，式（1）中的正弦函数在第一、二象限均为正，有时会出现两解．可以使用球面四联公式代替正弦公式进行求解运算，消除解的不确定性并提高计算精度[8].

![](images/3faf8f80f7b7205042e07042cbc80987d0183bc9db5e81bcffc25dd7892b05dd.jpg)  
图5矩形锥视场探测覆盖范围快速算法示意 Fig.5Sketch of the calculation of the rectangle awl detection field

![](images/e7b4372f461eddfa27586ecc99c413614f4c38d681c305c282582ae56f653a3b.jpg)  
图6圆锥视场探测覆盖范围快速算法示意 Fig.6Sketch of the calculation of the circular cone detection field

![](images/febbe229342b5bbf51d5bbeaa94bfbd05ace69945be37739ba0d5a709ba9cde0.jpg)  
图7正八面体的构造与编码  
Fig.7Establish and code of the regular octahedron

# 2基于QTM 编码的天球面探测覆盖栅格化表达

球面网格系统是一种等积投影系统，其精度可随网格精细程度增加而增加，适合于探测覆盖情况的分析和探测任务规划．在众多球面网格化算法中，Dutton[9-11] 提出的基于正八面体的球面四元三角网（Quaternary Triangular Mesh，QTM)，因其层次性结构，成为目前研究全球多尺度海量数据结构的有效管理方法之一[12].

# 2.1 QTM构造与编码

QTM基于正八面体进行构造，正八面体的上下两顶点与南北天极点重合，其棱分别与 $0 ^ { \circ }$ ， $9 0 ^ { \circ }$ ， $1 8 0 ^ { \circ }$ $2 7 0 ^ { \circ }$ 赤经, $0 ^ { \circ }$ 赤纬的投影重合[13]．如图7所示，其对应的编码为 $0 { \sim } 7$

随后，逐层对三角面进行编码，每一次细分中，一个三角面被分成4个新的三角面，中间三角形为0,左面三角形为2，右面三角形为3，上面或下面的三角形为1，如图8所示.

一个 $k$ 层的QTM编码由 $a _ { 0 } a _ { 1 } a _ { 2 } a _ { 3 } \cdot \cdot \cdot a _ { k }$ 表示,其中 $a _ { 0 }$ 为一个八分码，表示最初的正八面体的某一个面， $a _ { 1 } a _ { 2 } a _ { 3 } \cdot \cdot \cdot a _ { k }$ 为 $k$ 个四分码,表示第 $k$ 层的三角面片编码, $k = 6$ 时的QTM网络划分结果如图9所示.

# 2.2 赤经赤纬到QTM编码的转换算法

本文基于赵学胜等提出的行列逼近法（Caval-cade ApproachMethod)[12]进行赤经赤纬到QTM码的快速转换.这是一种球面小圆的剖分方法.其基本方法为，先根据剖分层次求出QTM的最大行列数，再根据所求点的经纬度计算对应的三角格网所在行列数，然后逐层递推求出对应的QTM编码.

# 3实验结果分析

基于所提出的坐标系转换与QTM编码方法，本文开发了一套天球面探测覆盖栅格化分析软件，对分析结果的正确性进行验证，如图10所示，并对该方法的精度和效率进行了分析.

# 3.1 计算效率分析

计算中所使用的实验平台为台式计算机．CPU型号为 Intel@ CoreTM 2 Duo E8400,主频 $3 . 0 \mathrm { G H z }$ 内存4GRAM;操作系统为WindowsXP.

![](images/8c018765cf09787f3867754021d4164b6dea92d1878e211481acf5cc1d8728e2.jpg)  
图8细分过程及其编码 Fig.8Subdivisions and its code

![](images/dcd0bf386a38b40c096b4e64063bb9090ca4018d8647a2ff3db8a535b3b50e6f.jpg)  
图9一个6层的QTM网格Fig.9A6-layer QTM mesh

表1计算1000个时相片段的矩形锥视场的效率对比 Table 1 Comparison in efficiency of rectangle awl detection field   

<html><body><table><tr><td>分辨率 /(")</td><td>大圆航迹 法耗时/ms</td><td>姿态矩阵转换 法耗时/ms</td><td>球面坐标系 转换法耗时/ms</td></tr><tr><td>36</td><td>2146</td><td>1166</td><td>827</td></tr><tr><td>18</td><td>4289</td><td>2334</td><td>1629</td></tr><tr><td>7.2</td><td>10 750</td><td>5792</td><td>4098</td></tr><tr><td>3.6</td><td>21550</td><td>11 588</td><td>8208</td></tr></table></body></html>

![](images/759a0aa1e668047b0ccd0ed29779480edf6aa289a81f7d57691f1b6dc68f4168.jpg)  
图108层编码下天球面覆盖计算结果示例.(a）圆锥视场(b)矩形视场

Fig.10Coverage inan 8-layer-QTMmesh basedon thecalculation:(a) circular cone detection field,(b)rectangle awl detection field

表2计算1000个时相片段的圆锥视场的效率对比  

<html><body><table><tr><td>分辨率/(")</td><td>姿态矩阵转换 法耗时/ms</td><td>球面坐标系 转换法耗时/ms</td></tr><tr><td>36</td><td>1371</td><td>845</td></tr><tr><td>18</td><td>2773</td><td>1678</td></tr><tr><td>7.2</td><td>6840</td><td>4163</td></tr><tr><td>3.6</td><td>13 610</td><td>9310</td></tr></table></body></html>

对于矩形锥视场的计算效率，这里采用球面坐标系转换算法与大圆航线解析法进行效率对比．计算1000个时相片段，结果列于表1(分辨率基于张角为 $1 0 ^ { \circ }$ 的情况)．可以看出，在计算1000个时相片段时,大圆航迹法每次都要计算航向,效率最低.基于坐标系转换法时，须先计算出视场在卫星本体坐标系下的覆盖情况，利用覆盖随卫星共同运动的特点，通过姿态矩阵计算天球面坐标系下的覆盖情况，效率大幅提升．二是利用球面坐标系，相比较于姿态矩阵，是二维坐标到二维坐标的转换，其效率也有一定提升.

对于圆锥视场，通常都是使用姿态矩阵转换法这一相对通用的计算方法．但是姿态矩阵法没有考虑视场本身所具有的一些特殊性质.对于圆锥视场，其在新建球面坐标系下为一赤纬圈，具有完全对称的特性,在计算时，利用对称性,仅需计算 $0 ^ { \circ } \sim 1 8 0 ^ { \circ }$ 的范围即可.效率对比结果列于表2 (分辨率基于圆锥张角 $1 0 ^ { \circ }$ 的情况).

# 3.2 QTM编码精度

QTM中某一级编码对应的三角格网边长可代表此级别的分辨率[13]．在天球面覆盖分析中，可用三角格网边长对应的球心角表示当前编码级别的分辨率.本文基于快速转换算法，利用经纬度平分法进行球面三角形的细分，其三角形在大小和形状上不可避免地有一些形变.以 $0 ^ { \circ }$ 赤纬所在边作为分辨率标准,对于 $k$ 层的QTM 编码,其在 $0 ^ { \circ }$ 赤纬上有 $2 ^ { k }$ 条边,则对应的球心角为 $9 0 ^ { \circ } \cdot 2 ^ { - k }$ ，即对于 $k$ 层的QTM,其分辨率为 $9 0 ^ { \circ } \cdot 2 ^ { - k }$ ·

Table 2 Comparison in efficiency of circular cone detection field   
表3整体计算效率 Table 3 Efficiency in all   

<html><body><table><tr><td>重复计算次数</td><td>矩形锥耗时/s</td><td>圆锥耗时/s</td></tr><tr><td>1000</td><td>1.071</td><td>0.867</td></tr><tr><td>5000</td><td>5.364</td><td>4.372</td></tr><tr><td>10000</td><td>10.811</td><td>8.686</td></tr></table></body></html>

在行列逼近法的算法中，因其只计算了奇数列，故存在额外的半个格网的误差[12]，综合分辨率约为 $1 . 5 \times 9 0 ^ { \circ } \cdot 2 ^ { - k }$ ．当QTM 的编码层数 $k$ 取19时，其综合分辨率可达到角秒量级.

# 3.3 栅格化覆盖分析的综合精度与效率

在实际工程应用中，QTM的编码层数选取以满足覆盖分析的实际精度需要为准，例如当卫星视场张角达到 $3 0 ^ { \circ }$ 时，取QTM的编码层数 $k = 1 2$ ，对应的栅格化覆盖分析精度为 $0 . 0 3 ^ { \circ }$ ，能够满足日常任务分析和规划的需求，其整体效率列于表3.

# 4结语

实验验证结果表明，本文所提出的天球面探测覆盖栅格化分析方法相比于非栅格化的覆盖分析方法，具有计算效率高，精度可控，计算结果易于存储和表达，交并运算算法易于实现等技术优势.在实际工程应用中，将分布在天球面上的探测目标(区域目标或点目标)按照QTM进行编码,表达为一个或一组编码值（一个球面三角形或者一系列球面三角形拼接得到的区域)，就可以直接通过编码检索的方法从探测覆盖分析结果中快速查找该目标的探测机会，从而很好地满足任务规划算法的输入需求

该方法在实际应用中还可根据工程约束条件，在分析结果的存储管理效率等方面进行进一步优化，

# 参考文献

[1]Liu Wei,Lin Baojun.An intelligentized controlling method for scanning the celestial sphere[J].J. Astron., 2006,27(6):1365-1368．In Chinese (刘薇，林宝军．卫星巡 天扫描运控模式方法的研究[J].宇航学报，2006，27(6):1365- 1368)   
[2] Qiao Shubo,Li Jinling,Sun Fuping，et al.Newly realization of celestial reference frame by stable sources selection[J].Acta Geodaet.Cartogr.Sin.,2010,39(2):120- 128．InChinese(乔书波，李金岭，孙付平，等.天球参考架的 稳定源选取及其最新实现[J].测绘学报，2010,39(2):120-128)   
[3]Hapgood MA.Space physics coordinate transformations: Auser guide[J].Planet Space Sci.,1992,40(5):711-717   
[4]Xu Mao,Kang Jianyong. Basic of Aeronautics Technology[M].Beijing:National Defense Industry Press,2008: 9-11.In Chinese(徐矛，康健勇.航天科技基础[M].北京：国 防工业出版社，2008:9-11)   
[5] Yang Zhen，Niu Wenlong，Gao Chen.Research on the payload coverage analysis of space science exploration [C]//64th International Astronautical Congress. Beijing:Chinese Society of Astronautics,2013 [6]Hong Deben.Planning ocean route in the way of analytical method[J].J.Dalian Maritime Univ.,1997,23(4):22-   
24．In Chinese (洪德本．解析法大圆航线的设计[J].大连海 事大学学报，1997,23(4):22-24) [7] Tu Chuanyi. Physics in Solar-Earth Space (Interplanetaryand Magnetosphere):Vol.2.Beijing:Science Press,   
1988:102-106．In Chinese(涂传诒．日地空间物理学（行星 际与磁层)：下册．北京：科学出版社，1988:102-126) [8] Liu Yingxian.Analytical method for determining the initial course of great circle track[J].J.Dalian Maritime Univ.，1997，23(4):25-28．In Chinese(刘英贤.公式法求大 圆始航向的探讨[J].大连海事大学学报，1997,23(4):25-28) [9] Dutton G.Encoding and handling geosptial data with hierarchical triangular meshes [C]//Proceeding of 7th International Symposium on Spatial Data Handling. Delft, Netherlands,1996 [10] Dutton G.Digital Map Generalization Using a Hierarchical Coordinate System[C]//Proceedings of Auto Carto. Seattle:ACSM/ASPRS:367-376 [11]Dutton G.Scale,Sinuosity and point selection in digital line generalization[J].Cartogr.Geogr.Inf.,1999,   
26(1):33-53 [12] Zhao Xuesheng,Chen Jun.Fast translating algorithm between qtm code and longitude/latitude coordination [J]. Acta Geod. Cartogr. Sin.,2008,32(3):272-277. In Chinese (赵学胜,陈军.QTM地址码与经纬度坐标的快速转换算 法[J].测绘学报，2008,32(3):272-277) [13] Song Shuhua,Cheng Chengqi,Guan Li,Wan Yuanwei, Yang Li. Analysis on global geodata partitioning models[J].Geogr. Geo-Inf. Sci.,2008,24(4):11-15. In Chinese (宋树华，程承旗，关丽．全球空间数据剖分模型分析[J]. 地理与地理信息科学,2008,24(4):11-15)