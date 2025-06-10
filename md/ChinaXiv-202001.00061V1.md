# 基于不同算法等高线曲率的提取与分析

王宁'，姚志宏²（1西北大学城市与环境学院,陕西西安710127；2华北水利水电大学测绘与地理信息学院,河南郑州450045）

摘要：等高线曲率是一个重要的地形属性，反应了地形表面在水平方向的凹凸性,表达了地表物质运动的发散和汇合模式。基于安塞县县南沟小流域的矢量等高线数据和DEM,分别利用圆拟合算法(相邻三点法、间隔三点法和最小二乘法)和曲面拟合模型(E模型、S模型和Z模型)提取等高线曲率，通过对实地地形的对比分析，结果表明：(1）在矢量等高线数据的计算结果中，三点拟合法计算结果相比最小二乘法结果差异大，对等高线曲率空间格局分布描述更准确；(2）最小二乘法计算的结果频数分布集中程度最高，两种三点拟合法计算结果频数曲线差别微小；(3）在栅格数字高程模型的计算结果中,基于S模型计算结果在空间格局上较E模型和Z模型的结果差别大,基于E模型的计算结果对等高线曲率描述效果更好。结果能准确说明采用不同算法计算等高线曲率的差别，对在实际数字地形分析中有重要的意义，可为等高线曲率计算提供重要参考。

关键词：数字地形分析；DEM；等高线曲率；圆拟合算法

地面曲率是对地形表面上一点扭曲变化程度的定量化度量因子[1]。等高线曲率是通过该点的等值面(水平面)与地表交线的曲率,等高线曲率表达了地表物质运动的汇合和发散模式[2]。与坡度、坡向等基本地形参数一样，等高线曲率在数学定义上是明确且唯一的,具有确定的表达式[3]。目前,对坡度、坡向和流域网络分析等的研究比较深入，而对等高线曲率等地形曲率的研究较少。基于栅格数据结构提取分析曲率,FLORINSKY[4]通过误差传播定律对常用的四种曲率模型进行了分析比较，通过计算在中心点处各个方向的偏导数来计算曲率的精度，给出了曲率误差和数字高程模型(DEM)误差的关系式。SCHMIDT[5]通过实验操作在光滑的数学曲面和实地DEM数据对3种曲率计算模型进行了研究。但FLORINSKY和SCHMIDT在探讨等高线曲率方面的研究较少，更缺少对矢量等高线的研究。而基于矢量数据结构提取分析曲率,张亮[提出圆拟合的方法，并没有进行详细对比不同拟合方式之间对结果的影响。基于上述原因，本研究利用不同算法提取等高线曲率并进行对比分析和评价，讨论设计新的基于矢量数据格式的等高线曲率计算方法，以期为DEM分辨率的确定提供科学依据，弥补前人研究的不足，且对推进数字地形分析的研究具有重要意义。

# 1等高线曲率提取算法

# 1.1基于矢量数据的等高线曲率算法

1.1.1三点拟合法如果三点不在一条直线上则可确定唯一的圆,中间节点处的曲率用半径的倒数表示;如果三点共线,则直接赋曲率值0[7]

如图1所示为等高线的一部分，假设 $\boldsymbol { r }$ 为三点$( P _ { i - 1 } , P _ { i } , P _ { i + 1 } )$ 构成的三角形外接圆半径,则半径的倒数 $1 / r$ 即可认为是在点 ${ \mathbf { } } P _ { \mathrm { { } } _ { i } }$ 处的曲率[8]。根据海伦公式、正弦定理、三角形面积公式即可推导出等高线曲率计算公式：

$$
C _ { c } = 1 / r = \frac { \sqrt { \left( a + b + c \right) \left( a + b - c \right) \left( a + c - b \right) \left( b + c - a \right) } } { a b c }
$$

式中： $C _ { c }$ 表示节点 $\boldsymbol { P } _ { i }$ 处的等高线曲率 $( \mathrm { r a d } \cdot \mathrm { m } ^ { - 1 }$ ）；$a , b$ 和 $\scriptstyle { \begin{array} { l } { c } \end{array} }$ 分别表示线段 $P _ { i - 1 } P _ { i }$ ， $P _ { i } P _ { i + 1 }$ ， $P _ { i - 1 } P _ { i + 1 }$ 的

![](images/c3fdbe276977f759ed324ce7a8ac4c40dddef34c70591785445119f9ea77b1e6.jpg)  
图1三点拟合法计算等高线曲率示意图 Fig.1Three-point fitting method for calculating contour curvature

![](images/7e5077303c31fd0659182b5fcdf08d51103e2c45fcb58ed735e184c148d32d27.jpg)  
图2最小二乘法计算等高线曲率示意图

长度。

1.1.2最小二乘法 最小二乘法是利用最小化误差的平方和寻找最佳拟合函数匹配该组数据。如图2,样本集 $( X _ { i } , Y _ { i } ) \ i = ( 1 , 2 , 3 \cdots N )$ 为等高线上一组节点,， $d _ { i }$ 为样本集中点到圆心 $( A , B )$ 的距离, $R$ 为拟合圆的半径，取半径倒数 $1 / R$ 即为在所选样本集中的等高线曲率。根据圆曲线方程、最小二乘法推求拟合圆半径，得到利用最小二乘法求得的等高线曲率公式为：

$$
C _ { c } = 1 \bigg / \ R = 2 \bigg / \sqrt { a ^ { 2 } + b ^ { 2 } - 4 c }
$$

$$
\begin{array} { l } { \displaystyle { c = - \frac { \sum \left( X _ { i } ^ { 2 } + Y _ { i } ^ { 2 } \right) + a \sum X _ { i } + b \sum Y _ { i } } { N } , } } \\ { \displaystyle { } } \\ { \displaystyle { C = \big ( N \sum X _ { i } ^ { 2 } - \sum X _ { i } \sum X _ { i } \big ) , } } \\ { \displaystyle { D = \big ( N \sum X _ { i } Y _ { i } - \sum X _ { i } \sum Y _ { i } \big ) } } \end{array}
$$

$$
\begin{array} { l } { { E = N \displaystyle \sum X _ { i } ^ { 3 } ~ + N \displaystyle \sum X _ { i } \sum Y _ { i } ^ { 2 } ~ - ~ \sum ~ ( X _ { i } ^ { 2 } ~ + Y _ { i } ^ { 2 } ) ~ \sum X _ { i } } } \\ { { { \cal G } = ( N \displaystyle \sum Y _ { i } ^ { 2 } ~ - ~ \sum Y _ { i } \displaystyle \sum Y _ { i } ) , } } \end{array}
$$

$$
H = N \sum X _ { i } ^ { 2 } \sum Y _ { i } + N \sum Y _ { i } ^ { 3 } - \sum ( X _ { i } ^ { 2 } + Y _ { i } ^ { 2 } ) \sum Y _ { i }
$$

# 1.2基于格网DEM的等高线曲率算法

曲率计算的实现主要包括对地形曲面求一阶导、二阶导和混合导，对于DEM数据曲率计算的实现，是利用局部曲面拟合或者对局部窗口进行差分计算求取[2,9-10] 。

通过 $3 \times 3$ 局部窗口如图3中的各个高程点$\left( x _ { i } , y _ { i } , Z _ { i } \right) \left( i = 1 , 2 , \cdots , n \right)$ ，为了求取各个偏导数，以最小二乘法来计算多项式中的系数，然后按照等高线曲率计算公式[]

$$
\boldsymbol { C _ { c } } = - \frac { \boldsymbol { q } ^ { 2 } \boldsymbol { r } - 2 p \boldsymbol { q } s + \boldsymbol { p } ^ { 2 } \boldsymbol { t } } { \left( \boldsymbol { p } ^ { 2 } + \boldsymbol { q } ^ { 2 } \right) ^ { 3 / 2 } }
$$

式中 $: p = \frac { \partial f } { \partial x } , \ q = \frac { \partial f } { \partial y } , \ r = \frac { \partial ^ { 2 } f } { \partial x ^ { 2 } } , \ t = \frac { \partial ^ { 2 } f } { \partial y ^ { 2 } } , \ s = \frac { \partial ^ { 2 } f } { \partial x \partial y }$

基于格网DEM提取等高线曲率，因为对地形曲面拟合所采取的方法不同，会导致计算的5个参数$p , ~ q , ~ r , ~ s , ~ t$ 的值有所不同，从而会使最终计算的等高线曲率值有所差别,本文主要探讨3种方法拟合地形曲面而对提取的等高线曲率产生的影响。3种方法分别为二次曲面方法（EVANS[1]方法）、限制二次曲面方法(SHARY[12-13]方法)和不完全四次曲面方法（ZEVENBERGEN[14]方法）。

# 1.3等高线曲率的算法实现

1.3.1基于矢量数据的等高线曲率计算本研究基于Net环境下的C#程序开发技术编写程序，提取等高线曲率。具体等高线曲率提取流程如图4，主要步骤为：（1）对原始矢量等高线数据进行拓扑检查和错误修复，包括对等高线交叉、自相交、悬挂点等方面的错误修复。（2）使用ArcMap中的FeatureVerticesToPoints工具将拓扑修复后的矢量等高线图层转换为点图层，利用AddXYCoordinates工具为等高线节点图层添加坐标。（3）利用C#编写程序，以添加了节点坐标的点图层中的“ORIG_ID”字段（存储了节点所属等高线的索引号）为基础读入同一条等高线上节点的坐标数据，用上文推导的公式(1)和(2)分别计算等高线曲率并存储于点图层属性表的curvature字段中。（4）对矢量点格式曲率结果进行空间分析，完成利用不同圆拟合算法基于矢量数据的等高线曲率的提取与分析。

![](images/705401824a8020f423fbdfc56bc23b3c0503c1e80b0447ba9ae8ed4d5cbf02d9.jpg)  
Fig.2Least squares method for calculating contour curvature   
图3 $3 \times 3$ 局部窗口示意图Fig.3 $3 \times 3$ partial window diagram

![](images/3c99a6e3c6a9c9a4399e92113823bdaa677a948a1d72444ee35755f37e698ed9.jpg)  
Fig.4Flow chart of contour curvature extraction which base on vector data

1.3.2基于格网DEM的等高线曲率计算 图5为基于格网DEM的等高线曲率提取流程图：（1）在ArcMap中加载原始DEM数据,利用Toolbox中Ras-ter to ASCII工具将原始DEM数据转化为文本格式的 DEM文档。（2）利用C#编程实现3种方法对等高线曲率的计算，得到文本格式的等高线曲率文档。（3）将文本格式的曲率在ArcMap中利用转换工具ASCIItoRaster转换成栅格格式曲率。（4）对栅格格式曲率结果进行空间分析，完成利用不同算法基于DEM等高线曲率的提取与分析。

DEM数据 Rasterto ASCIDEM文本文档 -VS计算曲率等高线曲率.txtASCll to Raster栅格格式等高线曲率空间分布图 ←结果分析 栅格格式曲率

# 2试验区与基础数据

选择位于陕北安塞县县南沟流域的两个试验区的矢量等高线数据和利用ANUDEM软件插值生成的栅格DEM数据，如图6、7、8、9所示。该流域地处黄土丘陵沟壑区的第二副区、半干旱森林草原地区。该地区海拔 $1 \ 0 7 0 \sim 1 \ 4 2 9 \ \mathrm { ~ m ~ }$ ,地面相对起伏 $2 6 0 \mathrm { ~ m ~ }$ ，地面坡度 ${ \geqslant } 3 0 ^ { \circ }$ 达一半以上。该流域沟壑林立，地表破碎复杂，水土流失异常明显，适用于本研究对等高

![](images/59fb1248f9d3b31d0ea0df496437642c86a85a5d5f0f851dc4b4862bfd74f020.jpg)  
图4基于矢量格式的等高线曲率提取流程图  
图6样区1矢量等高线数据Fig.6Sample area1 vector data

![](images/6c185b96a6054056618cceeec34a0fd20a5d8c6061da0db9363db44be9cb19ab.jpg)  
图5基于DEM的等高线曲率提取数据流程图Fig.5Flow chart of contour curvature extractionwhichbase on DEM  
图7样区2矢量等高线数据Fig.7Sample area 2 vector dData

![](images/f8ccfbd42840ba31966314f96181f148cad075fed65c068b69e7b4293cfd08fa.jpg)  
图8样区1栅格DEM数据Fig.8Sample area1 DEM

![](images/8e7a30ad776da55324c1e9ad4093e259380369280279b08ce5597a424b39abee.jpg)  
图9样区2栅格DEM数据Fig.9Sample area 9 DEM

线曲率的提取分析。

# 3 结果与分析

# 3.1基于矢量等高线曲率结果分析

实验数据1选自图6县南沟流域的一部分，实验数据2选自图7另一块县南沟小流域的一部分，两部分选取的原则都是在地形变化较为复杂的地区，从而计算的等高线曲率值大小跨度范围相对大，分类效果较为明显，便于对不同算法计算结果的比较分析。实验1,2计算的等高线曲率结果如图10，11。结果表明：利用三点拟合法计算的等高线曲率比利用最小二乘法计算的等高线曲率大，曲率在空间分布上存在着明显差异;同一种方法(三点拟合法)提取等高线曲率，选点方式不同，得出的等高线曲率在空间分布上差异不明显。在等高线比较弯曲，变化复杂的地区曲率大，而在等高线比较平直，变化较小的地区曲率小;在地形特征线山谷线和山脊线周围等高线曲率较大，而在非地形特征线的地区曲率较小，结果符合实地地形情况。

# 3.2基于矢量等高线曲率结果统计分析

将两个地区的矢量点格式的等高线曲率值导入Excel进行频率统计，得到如图12不同方法拟合等高线曲率频率曲线。通过对图12等高线曲率频率曲线分析，结果表明：在3种拟合算法计算等高线曲率中，最小二乘法集中程度最高，相邻三点法和间隔三点法集中趋势差别微小;采用不同拟合算法对等高线曲率的计算，最小二乘法计算结果与三点法计算结果差别较大,结果值偏小,曲线表明该流域曲率值集中分布在区间(0，0.4)中。

对两个样区曲率值进行统计分析可见（表1），样区1等高线曲率计算结果为相邻三点法与间隔三点法计算结果相差微小，样区2等高线曲率计算结果为相邻三点法与间隔三点法计算结果略有差别;在两个样区中，最小二乘法计算的结果明显偏小。

# 3.3基于DEM等高线曲率结果分析

基于不同曲面拟合模型的样区1，2的等高线曲率计算结果(图13、图14)可以看出：

（1）基于S模型计算出的结果较基于E模型和Z 模型计算的结果在空间格局上差别大，棱角分明;基于E模型计算的结果较基于Z模型计算的结果在地形特征线附近的曲率值差别更大，显示效果更清晰。

（2）在等高线曲率计算结果图上能够清晰地看到有关的地形特征线，并且地形特征线的分布与实地情形相符合，分布格局也合理;等高线曲率值在地形特征线山脊线或山谷线周边较大，并且越靠近山顶曲率值越大；曲率值的正负反映了地形的凹凸变化，对地形特征线的勾绘是正确的。

# 3.4基于DEM等高线曲率结果统计分析

在ArcMap中利用属性分类工具对基于3种曲面拟合算法提取的等高线曲率结果进行分区统计分析发现：对于同一个样区，采用不同的曲面拟合算法来计算基于DEM的等高线曲率值的区间分布有差别，但频数的分布趋势趋于一致，都在0值邻域内集中（图15、图16）。

(a)相邻三点法 (b)间隔三点法 (c)最小二乘法乔泰会

![](images/f8d48e700b54e6f35fec8594a93aa40063b6d97e8058d7c6b3de99dd24772f3e.jpg)  
干吴区地理  
图10实验1计算的等高线曲率  
图11实验2计算的等高线曲率

![](images/c0352176aa1a3e2d1c4d7072fe8cb0bd4fa10d092131f5bd0d34636e659bb98c.jpg)  
Fig.10 Contour curvature computed from experiment 1   
Fig. 11 Contour curvature computed from experiment 2   
图12不同方法拟合等高线曲率频率曲线  
Fig.12Frequency curve of contour curvature fitted by different methods

表1两样区等高线曲率统计表  
Tab.1 Contour curvature statistics for two sample areas   

<html><body><table><tr><td></td><td>方法</td><td>Min</td><td>Max</td><td>Mean</td><td>标准</td><td></td><td>方法</td><td>Min</td><td>Max</td><td>Mean</td><td>标准</td></tr><tr><td>样区1</td><td>相邻三点法</td><td>0</td><td>0.903 28</td><td>0.042 836</td><td>0.057 136</td><td>样区2</td><td>相邻三点法</td><td>0</td><td>2. 662 044</td><td>0.082 330</td><td>0.135 489</td></tr><tr><td></td><td>间隔三点法</td><td>0</td><td>0.903 28</td><td>0.043 663</td><td>0.057 490</td><td></td><td>间隔三点法</td><td>0</td><td>1.461 236</td><td>0.051 528</td><td>0.066 736</td></tr><tr><td></td><td>最小二乘法</td><td>0</td><td>0.206 361</td><td>0.004 040</td><td>0.011 317</td><td></td><td>最小二乘法</td><td>0</td><td>0.127 311</td><td>0.000 110</td><td>0.001 513</td></tr></table></body></html>

![](images/3595b9fedaa0aa2befacda0528f40028269847cccf4f26fe52cc5012e6698232.jpg)  
Fig.13 Contour curvature computed from sample area 1

![](images/84b100cbe0f787fff7c255a2315615f0d2dc7985baa121e8f49294fa018d5698.jpg)  
图13样区1等高线曲率计算结果

![](images/5907a3420b83f3ea68dd194b8e4060490f2a19f77f0a7e33d8d67610498a91da.jpg)  
Fig.14Contour curvature computed from sample area 2   
图15样区1等高线曲率频数区间分布

![](images/f87daef5a78ab5dab02e816bc841eb4abe49b4a91bb4a4462d44a6d6ddb22f75.jpg)  
图14样区2等高线曲率计算结果  
Fig.15Frequency interval distribution of contour curvature from sample area 1   
图16样区2等高线曲率频数区间分布  
Fig.16Frequency interval distribution of contour curvature from sample area 2

进一步对样区1和样区2进行等高线曲率数值的统计分析可见（表2），对于同一样区，采用E模型计算的结果值域和均值与S模型结果值差别小，但与Z模型计算的结果值差别大，且根据标准差Z模型曲率结果值更加集中。

表2两样区等高线曲率统计表  
Tab.2 Contour curvature statistics for two sample areas   

<html><body><table><tr><td></td><td>方法</td><td>Min</td><td>Max</td><td>Mean</td><td>STD</td></tr><tr><td rowspan="2">样区1</td><td>E模型</td><td>-2 114</td><td>1982</td><td>-0.075 40</td><td>14.760 23</td></tr><tr><td>S模型</td><td>-2 985</td><td>1 915</td><td>-0.08630</td><td>21.157 34</td></tr><tr><td rowspan="4">样区2</td><td>Z模型</td><td>-1 703</td><td>2 166</td><td>-0.026 85</td><td>12.347 80</td></tr><tr><td>E模型</td><td>-797</td><td>313</td><td>- 17.674 528</td><td>103.776 805</td></tr><tr><td>S模型</td><td>- 791</td><td>352</td><td>-28.142 857</td><td>102.319 521</td></tr><tr><td>Z模型</td><td>-298</td><td>285</td><td>-4.503 226</td><td>74.582 656</td></tr></table></body></html>

![](images/ceb4ddbe21ac7791c4a664549f1dc26d2744b7fb01603931edb4be1f7f918211.jpg)  
(a)样区1基于矢量和DEM等高线曲率结果叠合图

![](images/7b81c19991d3d4c81d8814c12cf7e043b4da420aba639e677098d6f419a58b30.jpg)  
(b)样区2基于矢量和DEM等高线曲率结果叠合图

# 3.5基于矢量数据和基于DEM提取的等高线曲率的比较

基于相邻三点法和E模型计算的等高线曲率结果,对矢量数据结果和栅格DEM结果进行比较，选取样区1和样区2地面相对起伏较大，地形特征线附近的区域进行矢栅结果对比，结果如图17所示。分析图17以及结合图13、14可以看出，基于矢量数据和基于DEM提取的等高线曲率值在空间格局上差别不大，均能够说明等高线的弯曲变化，在地形特征线周边，等高线曲率的变化也一致;基于规则格网DEM计算出来的结果更加平滑细腻。

# 4讨论

本文仅对基于不同算法提取等高线曲率进行了对比分析，在基于矢量等高线数据不能区分曲率正负的情形下仍需进一步研究。本文暂提供解决思路：以图18所示等高线为例， $\mathbf { A } _ { 1 } , \mathbf { B } _ { 1 }$ 和 $\mathrm { C } _ { 1 }$ 分别表示等高线上三点， $\mathbf { A } _ { 1 }$ 和 $\mathbf { C } _ { 1 }$ 两点确定唯一直线，取线段$\mathbf { A } _ { 1 } \mathbf { C } _ { 1 }$ 中点 $\mathbf { D } _ { 1 }$ ,判断点 $\mathbf { B } _ { 1 }$ 处高程值和点 $\mathbf { D } _ { 1 }$ 处高程值大小，即可解决基于矢量等高线不能区分曲率正负的情形，判断依据参照公式（4）。

$E _ { \scriptscriptstyle B } < E _ { \scriptscriptstyle D }$ ,曲率取“ $^ +$ ”（如图18点 $\mathbf { B } _ { 2 }$ 和点 $\mathbf { D } _ { 2 }$ ） $E _ { B } > E _ { D }$ ,曲率取“-”（如图18点 $\mathbf { B } _ { 1 }$ 和点 $\mathbf { D } _ { 1 }$ ）(4) $E _ { \scriptscriptstyle B } = E _ { \scriptscriptstyle D }$ ,曲率取“0”

式中： $E _ { B }$ 为B点高程值； $E _ { p }$ 为D点高程值。

![](images/b0d739863a0650a49de38e95300ef818680a915f666015d14b5f83cdff9cc9df.jpg)  
图17同一地区不同格式的元数据等高线曲率提取对比Fig.17Comparison of contour curvature from differentformats in the same region  
图18示例等高线Fig.18Example contour

在后续研究中将落脚点着重放在算法实现方向，以期能达到更为理想的结果，更好的改进原有算法的不足，为确定合适DEM的分辨率提供重要参考。

# 5结论

本研究基于矢量等高线数据和栅格DEM,分别利用圆拟合算法和曲面拟合模型提取等高线曲率并进行对比分析，通过设计新的基于矢量数据格式的等高线曲率计算方法，为DEM分辨率的确定提供科学依据，弥补因基于等高线派生的DEM数据计算而引起的精度损失。结论如下：

（1）三点拟合法计算的曲率值较最小二乘法的结果大，空间分布上存在明显差异;同一种方法（三点拟合法)提取等高线曲率，选点方式不同，曲率值在空间分布上差异不明显。利用三点法计算的结果曲率值频数分布总体趋势一致，并在一定值域内集中，但最小二乘法计算的等高线曲率值高度集中于（0，0.02]的范围内。

（2）基于规则格网DEM提取的等高线曲率较平滑，体现了格网数据的结构优势，进一步解释了格网数据应用广泛的原因；基于S模型计算的结果较基于E模型和Z模型计算的结果在空间格局上差别大,基于E模型的结果对地形特征的描述更好，更符合实地情形。

# 参考文献(References)

[1] 牟乃夏，刘文宝，王海银，等.ArcGIS10地理信息系统教程 [M].北京：测绘出版社,2012：360-361.［MOUNaixia,LIU Wenbao,WANGHaiyin,et al.ArcGIS1O tutorial;From beginner to master[M].Beijing:Surveying and Mapping Press,2012: 360 -361．]   
[2] 周启鸣，刘学军.数字地形分析[M].北京：科学出版社,2006： 35-42.［ZHOU Qiming,LIU Xuejun.Digital terrain analysis [M].Beijing:Science Press,2006:35 -42.]   
[3] LIU Xuejun.On the accuracy of the algorithms for interpreting grid-based digital terrain model[D].Wuhan:Wuhan University, 2002.   
[4]FLORINSKY IV.Accuracy of local topographic variables derived from digital elevation models[J].INT J Geographical Information Science,1998,12(1) :47 -61.   
[5]SCHMIDT J,EVANS I S,BRINKMAN J. Comparison of polynomial models for land surface curvature calculation[J]. Geographical Information Science,2003,17(8）:797 -814.   
[6]张亮,杨勤科,兰敏.等高线曲率计算方法研究[J].水土保持 研究,2014,21（3）:125-129.[ZHANG Liang,YANG Qinke, LAN Min.Studyon thealgorithm of contour curvature in topographic map[J].Research of Soil and Water Conservation,2014, 21(3):125-129.]   
[7］刘学军,王叶飞,曹志东,等.基于DEM 的地形曲率计算模型 误差分析[J].测绘科学,2006,（5）:50-53,5.[LIU Xuejun, WANG Yefei,CAO Zhidong,et al.Error analysis on DEM-based terrain curvatures models[J].Science of Surveying and Mappin, 2006,(5) :50-53,5.]   
[8］同济大学数学教研室.高等数学上册[M].第四版.北京：高等 教育出版社,2002:207-217.[The Department of Mathematics of Tongji University. Higher mathematics[M]. $4 ^ { \mathrm { t h } }$ Ed. Beijing : Higher Education Press,2002:207-217.]   
[9]WILSON JP.Digital terrain modeling[J]. Geomorphology,2012, 137(1) :107 - 121.   
[10］杨昕,汤国安,刘学军,等.数字地形分析的理论、方法与应用 [J].地理学报,2009,64（9）:1058-1070.[YANG Xin,TANG Guoan,LIU Xuejun,etal.Digital terrain analysis:Theory,method and application[J].Acta Geographica Sinica,2009,64（9）： 1058 -1070.]   
[11]EVANS I S.Land surface derivatives: History,calculation and further development[C]//Proceedings of Geomorphometry,Nanjing, 2013:105-108.   
[12]SHARY PA.Land surface in gravity points classification by a complete system of curvatures[J].Mathematical Geology,1995,27 (3) :373 -390.   
[13]SHARY PA,SHARAYA L S,MITUSOV AV.Fundamental quantitative methods of land surface analysis[J].Geoderma,2002,107 (1-2):1-32.   
[14］ZEVERBERGEN L W,THORNE C R.Quantitative analysis of land surface topography[J]. Earth Surface Processes and Landforms,1987,12(1) :47 - 56.

# Extraction and analysis of the contour curvature based on different algorithms

WANG Ning'， YAO Zhi-hong² (1College of Urban and Environmental Science,Northwest University,Xi'an 710127,Shaanxi,China; 2College of Surveyingand Geo-Informatics,North China University of Water Resources and Electric Power, Zhengzhou 450046,Henan,China)

Abstract：Contour curvature isoneof the fundamental topographic indicators that reflects theconvexities in the horizontal directionof the topographical surface and expresss the divergence andconfluence paterns of the motion of the surface maters.Calculating the contour curvature can measure the information conversion rateof the DEM interpolated by the vector contours,and providea reference for setting the appropriate DEM resolution.This study based on vector contour data and DEM of Xiannangou watershed in Ansai County,Shaanxi Province,China,using thecircle fiting algorithms（adjacent three-point method,interval three-point method and least square method）and surface fiting models（Evans model,Shary modeland Zevenbergen model）to calculate the contour curvature respectively.Thecomparative analysis betweenthereal topographyof the site and the computational results indicated as follows:（1）Theresults from thethree-point fiting methodare different from the results using the least squares method,and the former describes the spatial pattrn distribution of the contour curvature more accurately.（2）The frequency distributionof theresults calculated bythe leastsquares method is the highest,andthediference between thefrequencycurves of the two three-point fiting methods is small.（3）In thecalculation resultsof the DEM,the results from the S-model displayalarger diffrence than thatbythe E-model and the Z-model in the spatial pattern. The calculation results based on the E-model have a better efect on the contourcurvature description.Thediference presented by this paper when using diferent algorithms to calculate the contour curvature provides important reference in retrieving the contour curvature information in the practical digital terrain analysis.

Key Words:digital terrain analysis；digital elevation model（DEM）；contour curvature；circle fiting algorithms