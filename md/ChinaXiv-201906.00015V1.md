# 基于模糊隶属度的雷电危险度等级评定

王秀英，王军，罗少辉，冯有成(青海省气象灾害防御技术中心，青海西宁 810001)

摘要：利用2013—2017年青海省西宁市测站半径 $1 0 ~ \mathrm { k m }$ 的闪电定位监测数据,选取地域范围一小时内的地闪数目和一小时内的最大雷电流幅值作为雷电危险度因子。确定因子分级的上下限和因子区间划分，计算出单因子雷电危险度等级的隶属度与权重。采用梯形分布函数和模糊统计方法确定雷电危险度因子的隶属度函数，根据隶属度函数得出模糊矩阵，并进行模糊矩阵复合运算，求出雷电危险度综合指数，得出雷电危险度等级。结果表明：根据建立的模糊综合评判方法能够全面、客观、准确地反映一次闪电过程的危险度状况，有效评定雷电危险度等级，评定结果较为客观地反映了雷击事件的实际状况，从而为气象防灾减灾、雷电灾害调查和雷击风险评估等业务提供科学性的决策服务和参考依据。

关键词：雷电流幅值；地闪数目；隶属度；雷电危险度综合指数文章编号： 1000-6060(2019)03-0534-08(0534\~0541)

雷电危险度等级[1-3]评定是根据雷电的自然属性和危险程度决定的，危险度等级评定的目的之一是灾害管理的需要，也是灾害风险性的重要组成部分。雷电活动规模(强度)和活动频次决定雷电造成的灾害风险度，一般雷电强度越大、频次越高，雷电造成的灾害风险越大。闪电定位系统的建立和应用，为闪电研究提供了基础，闪电监测成为一种新的气象现代化探测手段，观测资料中包括时间、经度、纬度、雷电流幅值、雷电流上升陡度5个参数,其参数可供研究人员在宏观上了解某一区域闪电的物理环境。雷电危险度等级的评定为救灾工作提供客观依据，能够快捷、简便、准确地为救灾工作掌握灾害情况，进而为决策部门提供科学依据，便于有关单位的决策和部署。

目前，国内已有不少研究者对此进行了探索并取得了一定进展。郭虎[4]根据1995—2005 年北京市18个区县的雷暴日和雷电灾害统计资料，首次提出了北京市雷电灾害易损性评估指标，采用4级分区法对上述指标进行了分级，初步建立了北京市雷电灾害的综合评估模式，形成北京市雷电灾害易损度区划。张雅斌等[5对雷暴系统的地闪时空分布规律进行了研究与分析，得出大气电场发展有4个典型阶段，并对各阶段主要特征与成因进行了解释。李家启等[建立了能对雷电灾害严重程度进行定量描述的综合评估模式和划分雷电灾害等级的标准。袁湘玲等[提出雷电灾害的潜在易损性和现实易损性概念，并将其作为雷电灾害易损性评估指标。上述研究包括闪电数据时空分布特征，建立雷电灾害评估指标体系，依据雷暴日和雷电灾害统计资料建立雷电易损度区划。总体看已有的文献缺少对雷电危险性的研究。雷电危险性反映了雷电可能产生的危害大小，实际雷灾造成危害的程度与雷电危险性有直接关系，雷电危险性越大，在低易损区发生灾害的等级依然很高，造成的灾害程度也会加大。因此，通过有效地方法评定与划分雷电危险度显得尤为迫切和重要。

模糊综合评价[8]是一种基于模糊数学原理,将难以定量的影响因素定量化，从而进行综合评价的方法。基于模糊数学的模糊聚类算法通过最小化其目标函数获得样本集的模糊划分，其应用在信息技术领域,如模式识别[9]和图像处理[10]。杨琳[11]等开创性探索了一种采用模糊聚类获取模糊隶属度进行土壤属性制图的方法。其研究应用表明，模糊隶属度加权平均的方法可以通过较少的建模点得到更好的预测效果。秦健[12]等运用模糊综合评价法对重庆市雷电灾害易损性进行了定量评价，得到雷电灾害易损性等级及分布。在运用模糊综合评判方法[13-15]进行雷电危险度评价的研究中,由于隶属函数确定的复杂性，目前尚无一套完整的且具有普遍意义的确定方法。本研究通过青海省西宁地区5a的地闪监测数据，模糊评价模型以建立的数据指标体系为依据，采用数值特征分析和模糊统计方法确定雷电危险度因子的隶属度函数，在确定各因子权重的基础上，将指标权重A与因素集 $R$ 相结合，进行雷电危险度多级评定。

# 1资料与方法

# 1.1 资料来源

文中使用资料为雷电监测资料，研究地理点为西宁市区，其周边有多个临县的闪电观测数据，使用距离该地理点最近的闪电观测数值来代表其雷电活动规律。因此选取2013—2017年西宁市测站半径$1 0 ~ \mathrm { k m }$ 的闪电定位系统记录的云地闪数据进行研究，落入该半径区域内的雷击视为影响灾害发生地的雷击。截止2015年底，青海省全省共布设了33

个闪电探测子站（图1）。

该系统为中国科学院空间中心研制的ADTD型地闪定位仪，由中国气象局统一装备。每个子站系统共有4个天线组成，包括GPS天线、平板电场天线、南北向和东西向磁场环状天线。每个单站都将测到的闪电发生时间、方位、电场和磁场信号实时传输给中心站，进行实时定位处理。定位系统经过优化处理后提供每个闪电发生的时间、经度、纬度、雷电流幅值和雷电流陡度等参数。

# 1.2 研究方法

1.2.1雷电危险度因子本研究选用地域范围内一小时内的地闪数目( $L N$ ，单位：个· $\ln ^ { - 1 }$ )和一小时内的最大雷电流幅值( $L I$ ，单位：kA)作为雷电危险度因子。

1.2.2雷电危险度等级雷电危险度等级划分为低危险度、中危险度、高危险度和极高危险度4个等级[16],划分标准见表1。

1.2.3特征函数若任意一个元素对 $( \boldsymbol { x } , \boldsymbol { y } ) \ \boldsymbol { R }$ ，则称 $x$ 和 $y$ 有关系 $R$ ,若任意一个元素对 $( \boldsymbol { x } , \boldsymbol { y } ) \ \boldsymbol { R }$ ，则称 $x$ 和 $y$ 无关系 $R$ ，用特征函数来表示的话，有：

$$
\mu _ { R } ( x , y ) = \left\{ { \begin{array} { l l } { 1 \qquad } & { ( x , y ) \in R } \\ { 0 } & { ( x , y ) \not \in R } \end{array} } \right.
$$

![](images/37ec7460cef62a5ca3594e1edd98879624f433bbba2dc6bbe4ff9d33b1289f43.jpg)  
图1青海省地闪定位网子站分布图  
Fig.1Distribution map of substations of lightning location network in Qinghai Province

表1雷电危险度等级划分标准表  
Tab.1Standard for the classification of lightning hazards   

<html><body><table><tr><td>雷电危险度等级</td><td>低</td><td>中</td><td>高</td><td>极高</td></tr><tr><td>雷电类别</td><td>弱雷电</td><td>中等雷电</td><td>强雷电</td><td>特强雷电</td></tr><tr><td>危险级别</td><td>一级</td><td>二级</td><td>三级</td><td>四级</td></tr></table></body></html>

1.2.4隶属度函数若 $U$ 中的任一元素 $x$ ,都有一个数 $A ( x ) \in [ 0 , 1 ]$ 与之对应，则称 $A$ 为 $U$ 上的模糊集， $A ( { \boldsymbol { x } } )$ 称为 $x$ 对 $A$ 的隶属度。当 $x$ 在 $U$ 中变动时， $A ( x )$ 就是一个函数，称为 $A$ 的隶属函数。隶属度 $A ( { \boldsymbol { x } } )$ 越接近于1，表示 $x$ 属于 $A$ 的程度越高，A$( x )$ 越接近于0，表示 $x$ 属于 $A$ 的程度越低。隶属度函数的设计是个关键的步骤，不同的隶属度函数设计方法对算法实现的难易程度，及其最终的分类结果都有很重要的影响。隶属度可以看作是样本与其所在类的几何中心之间的距离的线性函数[17]。各因子隶属度函数：

$$
A ( x ) = \beta _ { 0 } + \beta _ { 1 } x
$$

式中： $A ( x )$ 为隶属度， $x$ 为雷电危险度因子预报值，$\beta _ { 0 } \sqrt { \beta _ { 1 } }$ 为常数，且 $\beta _ { 1 } \not = 0$ 。

# 1.2.5雷电危险度综合指数雷电危险度等级划

分采用模糊矩阵复合运算方法[18],雷电危险度综合指数 $U$ 表示为：

$$
U = A \times R = \left[ \begin{array} { l l l l } { u _ { 1 } } & { u _ { 2 } } & { u _ { 3 } } & { u _ { 4 } } \end{array} \right]
$$

式中：A为雷电危险度因子 $L N$ 和 $L I$ 进行权重归一化处理后，组成的模糊矩阵； $R$ 为雷电危险度因子$L N$ 和 $\boldsymbol { { \mathbf { } } } L \boldsymbol { { I } }$ 进行分级后，求出每级的隶属度，组成的模糊矩阵。 $u _ { 1 } \setminus u _ { 2 } \setminus u _ { 3 } \setminus u _ { 4 }$ 、分别为一级、二级、三级、四级的雷电危险度综合指数。根据最大隶属度原则[18],综合指数最大值所在的级别即为雷电危险度等级,当出现两个最大值时,取与次大值最贴近的最大值所在的级别为雷电危险度等级。

# 2雷电危险度因子的隶属度

# 2.1雷电危险度因子分级

本文统计西宁市测站半径 $1 0 ~ \mathrm { k m }$ 范围内5a的雷电监测资料中每小时的地闪数目和最大雷电流幅值，为客观起见，绘制每小时的地闪数目和最大雷电流幅值的累计频数分布图。各因子的下限值为0，上限值取累计频数等于 $100 \%$ 所对应的因子值，如图2和图3所示， $^ { \textrm { 1 h } }$ 的地闪数目的上限值为98

![](images/284392185d53f1db9835840b1e46e714227ccbfd311ac6dacffeefa157bf6f11.jpg)  
Fig.2Cumulative frequency distribution of lightning stroke times per hour in the radius of Xining station $1 0 ~ \mathrm { k m }$

![](images/a1eea6221de3f90b72cbffcace36d1742b4971e03084e202e8356e4b8ff47488.jpg)  
图2西宁市测站半径 $1 0 ~ \mathrm { k m }$ 范围1h闪击次数累计频数分布图  
图3西宁市测站半径 $1 0 ~ \mathrm { k m }$ 范围1h最大雷电流幅值累计频数分布图

Fig.3Distribution of cumulative frequency of maximum lightning current amplitude within $1 0 ~ \mathrm { k m }$ radius of Xining station 个： $\mathbf { h } ^ { - 1 }$ ， $^ \mathrm { ~ 1 ~ h ~ }$ 的最大雷电流幅值的上限值为138 kA。

根据图2和图3，将西宁地区地闪数目和雷电流幅值两个危险度因子分级的上下限范围等间隔划分为4级， $E _ { 1 } \setminus E _ { 2 } \setminus E _ { 3 } \setminus 4 _ { 4 }$ 为分级临界值，所得结果见表2。

# 2.2 雷电危险度等级的隶属度函数

为了确定地闪数目和雷电流幅值这2个雷电危险度因子的隶属度,采用隶属函数法[19-20]。常用的隶属函数的确定方法有直觉法、推理法， $\boldsymbol { \cdot } \boldsymbol { F }$ 统计法和$F$ 分布等。由于各因子评价标准是以区间来划分的，符合梯形分布的特点，因此，采用的隶属函数为$F$ 分布中的梯形分布[21-22],用函数特征点值(0,0)$\left( E _ { 1 } , 1 \right) \left( E _ { 2 } , 0 \right) , \left( E _ { 1 } , 0 \right) \left( E _ { 2 } , 1 \right) \left( E _ { 3 } , 0 \right) , \left( E _ { 2 } , 0 \right)$ $\left( E _ { 3 } , 1 \right) \left( E _ { 4 } , 0 \right)$ ， $\left( E _ { 3 } , 0 \right) \left( E _ { 4 } , 1 \right)$ ,根据公式(2)求出各因子各级别隶属度函数的 $\beta _ { 0 }$ 和 $\beta _ { 1 }$ ,得出隶属度函数如表3所示。

Tab.2 Critical value of factor classification   

<html><body><table><tr><td>雷电危险度因子</td><td>E</td><td>E</td><td>E</td><td>44</td></tr><tr><td>地闪数目(LN)</td><td>24.5</td><td>49</td><td>73.5</td><td>98</td></tr><tr><td>雷电流幅值(LI)</td><td>34.5</td><td>69</td><td>103.5</td><td>138</td></tr></table></body></html>

表2各因子分级临界值  

<html><body><table><tr><td colspan="3">低(一级)</td><td colspan="3">中(二级)</td></tr><tr><td rowspan="4"></td><td>.1</td><td>x=E1</td><td></td><td>1</td><td>x =E2</td></tr><tr><td>A1（x）=</td><td>0<x<E1</td><td></td><td>A(x)=E(χ-E1)</td><td>E<x<E2</td></tr><tr><td>1 (x-E) E1</td><td>E<x≤E2</td><td></td><td>1 (x-E3) E1</td><td>E2<x≤E</td></tr><tr><td colspan="2"></td><td colspan="3">极高(四级)</td></tr><tr><td rowspan="4"></td><td>高(三级)</td><td></td><td></td><td></td><td></td></tr><tr><td>（x-E）</td><td>x=<x<E</td><td>A4(x)=</td><td></td><td></td></tr><tr><td>1(x-E4)</td><td>E<x≤E4</td><td></td><td></td><td>x=E</td></tr><tr><td>E1</td><td></td><td></td><td></td><td></td></tr></table></body></html>

根据表3，利用表2提供的地闪数目和雷电流幅值的分级临界值，得出西宁地区雷电危险度因子地闪数目和雷电流幅值的4个级别的隶属度函数，如表4所示。

# 表3梯形分布函数

Tab.3Trapezoidal distribution function   
表4雷电危险度因子的隶属度函数  
Tab.4Membership function of lightning hazard factor   

<html><body><table><tr><td colspan="3">地闪数日LN</td><td colspan="3">雷电流幅值LI</td></tr><tr><td rowspan="3">A(x）=</td><td>1.</td><td>x =24.5</td><td rowspan="3">1 1 A(x）=</td><td>x=34.5</td><td></td></tr><tr><td>1 24.5x</td><td>0<x<24.5</td><td>34.5x</td><td>0<x<34.5</td></tr><tr><td>1 24.5 (x-49)</td><td>24.5< x≤49</td><td>1 -34.5(x -69)</td><td>34.5<x≤69</td></tr><tr><td rowspan="3">A(x）=</td><td>1</td><td>x=49</td><td>1</td><td></td><td>x=69</td></tr><tr><td>1 24.5(x -24.5)</td><td>24.5<x<49</td><td>A(x）=</td><td>1 34.5(x-34.5)</td><td>34.5<x<69</td></tr><tr><td>1 24.5(x -73.5)</td><td>49 < x≤73.5</td><td></td><td>1 34.5(x-103.5)</td><td>69 < x≤103.5</td></tr><tr><td rowspan="4">A(x）=</td><td>1</td><td>x=73.5</td><td>1</td><td></td><td>x =103.5</td></tr><tr><td>1 24.5(x-49)</td><td>49 < x <73.5</td><td>A(x）=</td><td>1 34.5(x-69)</td><td>69 < x <103.5</td></tr><tr><td>1 -2 24.5(x-98)</td><td>73.5<x≤98</td><td></td><td>1 【-34.5(x -138)</td><td>103.5<x≤138</td></tr><tr><td></td><td></td><td>.1</td><td></td><td></td></tr><tr><td rowspan="3">A4(x)=</td><td>,1 1</td><td>x≥98</td><td>A4(x)=</td><td>1</td><td>x≥138</td></tr><tr><td>(x-73.5) 24.5</td><td>73.5<x<98</td><td></td><td>(x-103.5) 34.5</td><td>103.5<x<138</td></tr><tr><td>0</td><td>x =103.5</td><td></td><td>0</td><td>x=103.5</td></tr></table></body></html>

# 3应用案例分析

# 3.1 案例一

南凉虎台遗址公园位于西宁市城西区虎台一巷，公园南北长 $2 0 9 \mathrm { ~ m ~ }$ ,东西宽 $2 1 0 \mathrm { ~ m ~ }$ ，总占地面积为$6 0 \ 9 0 0 \ \mathrm { m } ^ { 2 }$ 。2013年8月23日傍晚发生雷电天气，闪电定位仪监测到从19：11时到20：10内共闪击95次，且 $^ { \mathrm { ~ 1 ~ h ~ } }$ 内的最大雷电流幅值为 $6 4 ~ \mathrm { k A }$ 。根据事故勘查和雷电灾害调查，此次雷击严重破坏了遗址中“西平王”的重点文物的原型，是近几年西宁市雷击灾害级别较大的一次。

根据表4的隶属度函数，已知地闪数目（ $L N =$ 95)和雷电流幅值( $L I = 6 4$ )的监测值，得出每个危险度因子的隶属度，见表5，并组成模糊矩阵 $R$ 。

表5雷电危险度各因子的隶属度  
Tab.5Membership of various factors of lightning hazard   

<html><body><table><tr><td>雷电危险度因子监测值</td><td>A(x)</td><td>A(x)</td><td>A(x)</td><td>A4(𝑥)</td></tr><tr><td>地闪数目(xLN=95)</td><td>0</td><td>0</td><td>0</td><td>0.88</td></tr><tr><td>雷电流幅值(Xu=64)</td><td>0.14</td><td>0.86</td><td>0</td><td>0</td></tr></table></body></html>

模糊矩阵 $R = \Big [ 0 \qquad 0 \qquad 0 \quad 0 . 8 8 \Big ]$

由表2和权重计算公式(4)计算雷电危险度各因子的权重，组成模糊矩阵 $A$ ○

$$
W _ { i } = \frac { C _ { i } } { S _ { i } }
$$

式中： $C _ { i }$ 为雷电危险度因子监测值, $S _ { i }$ 为与 $C _ { i }$ 对应的雷电危险度因子各级临界值的平均值， $\textstyle \mathbf { \big | } { \big | } { \big | } _ { i }$ 越大对总体雷电危险度影响越大。

$$
S _ { _ { L N } } = { \frac { 1 } { 4 } } { \left( 2 4 . 5 + 4 9 + 7 3 . 5 + 9 8 \right) } = 6 1 . 2 5
$$

$$
S _ { _ { L I } } = { \frac { 1 } { 4 } } ( 3 4 . 5 + 6 9 + 1 0 3 . 5 + 1 3 8 ) = 8 6 . 2 5
$$

$$
\begin{array} { c } { { W _ { _ { L N } } = 9 5 \bigg / 6 1 . 2 5 = 1 . 5 5 } } \\ { { } } \\ { { W _ { _ { L I } } = 6 4 \bigg / 8 6 . 2 5 = 0 . 7 4 } } \end{array}
$$

由权重归一化处理公式(5)对各因子进行归一化处理：

$$
\overline { { W _ { i } } } = W _ { i } { \Bigg / } \sum _ { i = 1 } ^ { n } W _ { i }
$$

$$
\begin{array} { c } { { \overline { { { W _ { L N } } } } = 1 . 5 5 \bigg / \left( 1 . 5 5 + 0 . 7 4 \right) = 0 . 6 8 } } \\ { { \overline { { { W _ { L I } } } } = 0 . 7 4 \bigg / \left( 1 . 5 5 + 0 . 7 4 \right) = 0 . 3 2 } } \end{array}
$$

得到模糊矩阵 $\begin{array} { r l } { A = \left[ 0 . 6 8 \ } & { { } 0 . 3 2 \right] } \end{array}$ 。由公式(3)计算雷电危险度综合指数 $U _ { \circ }$

雷电危险度综合指数

$$
\begin{array}{c} { \begin{array} { r l } { U = A \times R ~ = \left[ 0 . 6 8 ~ } & { 0 . 3 2 \right] \times { \left[ \begin{array} { l l l l } { ~ 0 } & { 0 } & { 0 } & { 0 . 8 8 } \\ { 0 . 1 4 } & { 0 . 8 6 } & { 0 } & { 0 } \end{array} \right] } } \\ { = \left[ 0 . 0 4 \quad \right]} & { 0 . 2 8 \quad } & { 0 } & { 0 . 6 0 } \end{array}  } \end{array} 
$$

# 3.2 案例二

2016年8月24日24时左右，互助县高寨乡曹家堡收费站发生1起雷电灾害事故。闪电定位仪从24：00 到00：08内共监测到闪击24次，最大雷电流幅值为 $6 7 ~ \mathrm { k A }$ 。此次雷电灾害事故造成收费站雨棚南面的LED显示牌5件电源整流器受损。根据事故勘查和雷电灾害调查，将此次事故鉴定为一般级别的雷电灾害事故。依照本研究中的研究方法，计算出此案例中模糊矩阵和雷电危险度综合指数。

雷电危险度综合指数

$$
\begin{array} { c c c c c } { { U = A \times R } } & { { = \left[ 0 . 6 8 } } & { { 0 . 3 2 \right] \times \left[ \begin{array} { c c c c c } { { 0 . 9 8 } } & { { 0 } } & { { 0 } } & { { 0 } } \\ { { } } & { { } } & { { } } & { { 0 } } \\ { { 0 . 0 6 } } & { { 0 . 9 4 } } & { { 0 } } & { { 0 } } \end{array} \right] } } \\ { { } } & { { } } & { { } } \\ { { \ = \left[ \begin{array} { c c c c c } { { 0 . 6 9 } } & { { 0 . 3 0 } } & { { 0 } } & { { 0 } } \end{array} \right] } } \end{array}
$$

南凉虎台遗址公园雷击案例雷电危险度综合指数最大值所在级别为第四级，雷电危险度处于极高雷电危险度等级。互助县高寨乡曹家堡收费站雷击案例雷电危险度综合指数最大值所在级别为第一级，雷电危险度处于低雷电危险度等级。该评定结果客观反映了雷击事件的实际情况，研究方法得出的结论与事故勘查和雷电灾害调查结果相符。

# 4讨论

在利用雷电流强度和频次进行雷电流活动特征研究分析过程中,国内其他研究人员[2.4.6,23]一般从造成雷电灾害的致灾因子、孕灾环境和承灾体系统出发，计算出评估值，得出雷电灾害发生的潜势等级。袁湘玲等[24]研究结果表明选取地闪密度和雷电流强度作为雷电灾害事件发生的可能性指标，结合生命易损模数和经济易损模数，得出雷电灾害风险分级方法，其实例应用结果表明对雷电灾害风险等级具有很好的区分性，然而其依据指标多，研究方法复杂，可操作性不强。

本研究则是以地闪频次和雷电流幅值为依据，以单个雷击事件为研究对象，确定地闪频次和雷电流幅值的上下限，采用梯形分布函数和模糊统计方法确定雷电危险度因子的隶属度函数，建立雷电危险度等级的模糊综合评判方法。针对一次雷击事件，根据建立的模糊综合评判方法评定此次雷击事件的危险度等级。在雷电危险度等级评价中，运用模糊综合评判法简单有效，相对于其它方法，该方法能较准确的给出不同雷电流幅值、不同地闪数目的雷电危险度等级，有较好的可操作性、科学性和适用性。再者，雷电灾害与其它灾害相比，致灾机理和作用范围都有所不同，传统划分的雷电低易损区域若发生强雷击事件，其造成的灾害远大于雷电高易损区发生的弱雷击事件。因此，进行雷灾风险分析应从雷灾本身的自然属性出发，其研究结果更具有意义和实际应用。

# 5结论

科学建立雷电危险度等级评定方法，可以较全面、客观、准确地反映一次雷击事件的危险度状况，将雷电活动的关注点从以往的易损区划转移到雷电危险度层面上，从而弥补以前仅从雷电灾害风险研究而忽略对雷电危险源研究造成的弊端。本文在青海省闪电定位监测数据的基础上，运用模糊隶属度函数,建立了西宁市雷电灾害危险度综合评定方法，通过实例应用分析进行综合评定。

（1）基于模糊数学理论，根据选定的2个雷电危险度评定因子，采用数值特征分析和模糊统计方法确定其隶属度函数，同时确定各因子的权重，建立模糊综合评判方法。

（2）利用建立的模糊综合评判方法对西宁地区雷击案例进行等级评定，评定结果较为客观地反映了雷击事件的实际状况，说明该评价方法在雷电危险度等级评定方面是可行的。

（3）该方法采用较少的建模点可以得到更好的结果，并且实例验证了本方法的可行性和有效性。本方法之所以得到较好的结果，主要是因为模糊隶属度中蕴含了雷电流幅值与地闪数目间关系的知识，其主要优点在于定性和定量的描述雷电危险度等级。

（4）雷电危险度等级评定研究对我省雷击灾害防御能力的增强具有重要意义和实际应用，其结果不仅为气象防灾减灾提供决策依据，还为雷电灾害风险区划和雷电灾害调查提供技术指标，为实现雷电灾害分级管理提供科学依据。

参考文献(References）   
[1］冯志泽.自然灾害等级划分及灾害分级管理研究[J].灾害学, 1996,11（1）:34-37.[FENG Zhize.Study on classification and management of natural disasters[J]. Journal of Catastrophology, 1996,11(1) :34 -37. ]   
[2]王凤娇,任钟冬,韦良文,等.雷电灾害等级划分及发生潜势指 标探讨［J].气象科技,2009,37（6）：744-747.［WANG Fengjiao,REN Zhongdong,WEI Liangwen,et al. Grade division and occurrence potential index of lightning disaster[J]. Meteorological Science and Technology,2009,37(6）:744-747.]   
[3］杨超,潘敖大,李娟,等.基于应急综合管理的气象灾害敏感单 位等级划分[J].灾害学,2018,33（1):27-31.[YANG Chao, PAN Aoda,LI Juan,et al. Grade division of meteorological disaster sensitive units based on emergency integrated management[J]. Journal of Catastrophology,2018,33（1）:27 -31.]   
[4]郭虎,熊亚军,扈海波.北京市雷电灾害灾情综合评估模式 [J].灾害学,2008,23（1）:14-17.[GUO Hu,XIONG Yajun, HU Haibo.Synthetic assessment model of lightning disaster in Beijing[J]. Journal of Catastrophology,2008,23（1）:14-17.]   
[5］张雅斌,高菊霞.高原东北侧灾害性雷暴的大气电场特征分析 [C]//第26届中国气象学会年会论文集.陕西省防雷中心， 2009:2068 -2074.[ZHANG Yabin,GAO Juxia. Characteristics analysis of atmospheric electric field during disastrous thunderstorms weather in northeastern Tibet[ C]//The proceedings of the $2 6 ^ { \mathrm { t h } }$ annual meeting of China Meteorological Society. Shaanxi Provincial Lightning Protection Center,2009:2068 -2074.]   
[6]李家启,秦健,李良福,等.雷电灾害评估及其等级划分[J].西 南大学学报（自然科学版）,2010,32（11）：140－144.［LI Jiaqi,QIN Jian,LI Liangfu,et al.Evaluation and grade partition of lightning disaster[J]. Journal of Southwest University（Natural Science Edition）,2010,32(11):140-144.]   
[7］袁湘玲,王振会,肖稳安,等.雷电灾害潜在与现实易损性分析 及区划研究—以黑龙江省为例[J].灾害学,2011,26(1)：20 - 25.[YUAN Xiangling,WANG Zhenhui,XIAO Wen'an,et al.A study on the potential and current vulnerability and regionalization for lightning disaster in Heilongjiang Province［J].Journal of Catastrophology,2011,26(1） :20-25.]   
「8］杨伦标.高英仪.模糊数学原理及应用「M].广州·华南理工大

学出版社,1992:15-69.[YANGLunbiao,GAO Yingyi.Principle and application of fuzzy mathematics[M].Guangzhou:South China University of Technology Press,1992:15-69.]

[9]TAN K S,LIM W H.Novel initialization scheme for fuzzy C-means algorithm on color image segmentation[J].Applied Soft Computing，2013,13(4):1832-1852.

[10]CHEN JS,PIDC,LIU ZP.An insensitivity fuzzy C-means clustering algorithm based on penalty factor[J].Journal of Software, 2013,8(9) :2379-2384.

[11］杨琳，朱阿兴，秦承志，等.运用模糊隶属度进行土壤属性制图 的研究——以黑龙江鹤山农场研究区为例[J].土壤学报， 2009,46(1):9-15.[YANGLin,ZHU Axin,QINChenzhi,et al. Soil property mapping using fuzzy membership:A case study of a studyarea in Heshan farm of Heilongjiang Province[J].Acta Pedologica Sinica,2009,46(1) :9-15.]

[12］秦健，覃彬全，陈闯，等.基于模糊综合评价法的雷电灾害易损性区划研究[J].西南大学学报（自然科学版）,2014,36（7）：176-182.[QIN Jian,QIN Binquan,CHEN Chuang,et al.Light-ning disaster vulnerability zoning research based on fuzzy compre-hensive evaluation[J].Journal of Southwest University（NaturalScience Edition）,2014,36(7）:176-182.]

[13］李俊晓，李朝奎，罗淑华，等.基于AHP模糊综合评价方法的泉州市水资源可持续利用评价[J].水土保持通报，2015，（1）：210-214,286.[LIJunxiao,LIChaokui,LUOShuhua,etal. Sus-tainable utilization evaluation of water resources in Quanzhou Citybased on AHP and fuzzy synthetic judgment[J].Bulletin of Soiland Water Conservation,2015,（1):210-214,286.]

[14］窦培谦.城市环境安全模糊综合评价方法研究[J].中国环境管理,2016,(2）:89-93.[DOU Peiqian.Research of urban fuzzycomprehensive evaluation method for environment security［J].Chinese Journal of Environmental Management,2O16,（2）:89-93.]

[15］张铁男，李晶蕾.对多级模糊综合评价方法的应用研究[J].哈尔滨工程大学学报,2002,23（3）:132-135.[ZHANG Tienan,LI Jinglei.Application of multi-step fuzzy comprehensive evaluation[J].Journal of Harbin Engineering University,20O2,23（3）：132 -135.]

[16］邹善勇，王淑一，邹皓羽，等.基于熵值赋权法的大连地区雷电 危险度可拓学评估[J].气象与环境学报，2016，32(6)：184- 189.［ZOU Shanyong,WANG Shuyi,ZOU Haoyu,et al.Extenics evaluation oflightning risk degree in Dalian region using an entropy weighting method[J].Journal of Meteorology and Environment, 2016,32(6):184-189.]

[17］杜喆，刘三阳，齐小刚.一种新隶属度函数的模糊支持向量机[J].系统仿真学报,2009，21（7）：1901-1903.［DUZhe，LIUSanyang,QI Xiaogang. Fuzzy support vector machine with newmembership function[J].Journal of System Simulation,2009,21(7):1901-1903.]

[18］王泉伟，刘建磊，杜朋召.模糊综合评价方法在边坡岩体卸荷程度分级中的应用[J].华北水利水电大学学报（自然科学版）,2016,37（6):89-92.[WANGQuanwei,LIUJianlei,DUPengzhao.Application of fuzzy synthesis assessment method inclassification of slope rock unloading[J].Journal of North ChinaUniversity ofWaterResourcesandElectricPower(Natural ScienceEdition）,2016,37(6) :89-92.]

[19］曹杰.基于相对隶属度和概率论耦合的水资源紧缺程度评价模型及其应用[J].江苏水利，2017，（11）：34-39，43.［CAOJie.Evaluation model and its application of water resources short-age degree based on relative membership degree and probabilitytheory[J].Jiangsu WaterResources,2017,（11）:34-39,43.][20］何荣，王斌.基于层次分析法的矿区建筑物损害程度模糊评价[J].河南理工大学学报（自然科学版），2017，36（1)：32-37.[HERong，WANG Bin.Fuzzy evaluation of damage degree ofbuildings based on analytic hierarchy process[J].Journal of HenanPolytechnic University（Natural Science）,2017,36(1）:32-37.][21］万中，梁文冬，卢宗娟.模糊数的隶属度区间分布函数[J].重庆理工大学学报（自然科学），2011，25（1）：107-112.［WANZhong,LIANG Wendong,LU Zongjuan.Study on the membershipinterval distribution function for fuzzy sets［J].Journal ofChongqing University of Technology（Natural Science）,2011,25(1):107-112.]

[22］郭文兵，刘义新，李小双.采动影响下建筑物损害程度的模糊聚类分析[J].采矿与安全工程学报，2007，24（3）：288-292.[GUOWenbin,LIU Yixin,LI Xiaoshuang.Fuzzy clustering analy-sis of mining induced damages of buildings[J]. Journal of Mining& Safety Engineering,2007,24（3）:288-292.]

[23］王敏，孔尚成，王秀英.青海东部地区雷电灾害易损性分析与 区划[J].气象科技，2018,46(2）:26-31.[WANGMin，KONG Shangcheng,WANG Xiuying.Vulnerability and regionalization of lightning disasters in eastern Qinghai[J].Meteorological Science and Technology,2018,46(2）:26-31.]

[24］袁湘玲，周倩，王振会，等.雷电灾害风险分级方法研究[J].灾 害学,2017,32（1）:412-416.[YUAN Xiangling,ZHOU Qian, WANG Zhenhui,et al.A study on the lightning disaster risk grading methods[J]. Journal of Catastrophology,2017,32（1）:412- 416.]

# Assessment of lightning hazard degree based on fuzzy membership

WANG Xiu-ying，WANG Jun，LUO Shao-hui， FENG You-cheng (Qinghai Meteorological Disaster Prevention Technology Center,Xining81Oooo,Qinghai,China)

Abstract:Assessment of lightning hazard grade is an important part of disaster risk evaluationand disaster management.The establishment of a scientific assessment method of lightning hazard grade can reflect the dangerous conditionofalightning strikeeventcomprehensively,objectivelyandaccurately.Itisurgentand importantto evaluate and divide the lightning hazard by efective ground method.Based on the monitoring data about ground flicker in Xining area of Qinghai Province,China for5 years,this paper takes the frequencyof ground flickerand the amplitude of lightningcurrntas risk factors to determinethe ground flicker frequencyand the upper and lower limits of lightning current amplitudeof theresearch data.The membership function of lightning hazard factor is determined byusing trapezoid distribution function and fuzz statistical method.Onthe basis of determining the weight of each factor,combining the index weight with the factorset,the multilevelassessment of lightning risk iscarriedout.The paper evaluates the lightning hazard degree of two cases and the results show that the fuzzy comprehensive evaluation method issimpleand effctive in theresearch methodof lightning hazard gradeevaluation,and its evaluation results objectivelyreflect theactual situation of lightning strike event andthe conclusionof the research method is consistent with theresultsof the accident investigationand lightning disaster investigation.Compared with other methods,this method can accurately give the lightning hazard grade of diffrent lightning current amplitude and different lightning number.

Key words：amplitude of lightning current；ground flicker number；degreeof membership；lightning hazard index

# 中亚沙尘暴国际会议(CADUC)在塔吉克斯坦召开

应塔吉克斯坦国家科学院院长法赫德·拉希米院士(FarhodRahimi)的邀请，中国科学院新疆生态与地理研究所党委副书记、纪委书记吉力力·阿不都外力研究员、中亚研究室副主任马龙副研究员等赴塔吉克斯坦,参加2019年4月7日—11日在塔吉克斯坦首都杜尚别召开的中亚沙尘国际会议(CADUC)。本次会议由塔吉克斯坦国家科学院主办，德国莱布尼兹对流层研究所(TROPOS)协办。来自中国、德国、美国、英国、俄罗斯、日本、伊朗、印度、巴基斯坦、土耳其、科威特、格鲁吉亚、塔吉克斯坦等国家的100 余名代表参加会议。

会议首要目标是将科学家聚集在一起，更深入地了解中亚以及全球干旱区沙尘/盐尘的性质，来源，传输过程以及对人类社会和环境的影响;加快推进中亚沙尘研究的国际化进程，提出中亚沙尘及其对气候影响的联合研究提案，为国家间的合作做出贡献。本次国际会议围绕源区大气沙尘调查，沙尘传输过程及机制;沉降区大气沙尘调查;灰尘的影响等四个主题进行了讨论,62人做了报告。吉力力·阿不都外力研究员以“Lakes in arid land and saltdust storms”为题做了大会报告,马龙副研究员以“Variation inaeolian environments recorded bythe particle size distri-bution of lacustrine sediments in Ebinur Lake，northwest China”为题与参会人员进行了学术交流。

会议期间，吉力力·阿不都外力等与德国马尔堡菲利普大学Christian Opp教授和Michael Groll副教授就中亚湖泊环境变化和盐尘暴方面的合作研究深入推进交换了意见，并提出了具体的实施方案。与伊朗德黑兰大学 AliDarvishi Boloorani副教授就哈萨克斯坦及“一带一路”沿线沙尘国际合作研究方案进行了深入讨论。