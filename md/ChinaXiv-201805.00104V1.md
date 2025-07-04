# 基于故障树的南极天文光学望远镜镜面除霜系统的可靠性分析

冯晴晨1,2,3，李晓燕1,2

（1.中国科学院国家天文台南京天文光学技术研究所，江苏 南京210042；2.中国科学院天文光学技术重点实验室，江苏南京210042；3.中国科学院大学，北京100049)

摘要：我国的南极天文光学望远镜目前架设在环境恶劣的南极冰穹A地区，观测时处于无人值守的状态。由于观测时部分光学镜面暴露在外部环境中，镜面表面的冰雪霜会降低光学系统的透光效率和反射效率。望远镜镜面除霜系统旨在降低或消除冰雪霜对光学系统的影响。基于故障树分析法建立了望远镜镜面除霜系统失效的故障分析树，通过对故障树的定性和定量分析，得到系统的最小割集和引起故障的各基本事件的结构重要度排序。结合实测结果，有效地找出系统的薄弱环节，对于提高系统的可靠性，改进和完善系统提供了理论指导。

关键词：镜面除霜系统；故障树；可靠性分析；南极天文光学望远镜中图分类号：TH751 文献标识码：A 文章编号：1672-7673(2018)01-0111-08

南极冰穹A/C 因受人工光源干扰少、大气湍流小、视宁度极好、观测时间长等优点，被誉为地球上极佳的天文观测台址之一[1]。为研究诸如太阳系起源、早期宇宙和宇宙暗物质、暗能量等重大问题提供了新的机遇。近年来，我国积极开展南极天文学的研究，从2008年“中国之星”小望远镜阵在南极冰穹A架设成功开始，我国在冰穹A已经安装了一台“中国之星”小望远镜阵和两台南极巡天望远镜，获取了大量的观测数据，为开展超新星宇宙学、宇宙暗物质、系外行星及恒星形成原因等国际前沿领域的研究提供了宝贵的数据。

在南极架设的光学望远镜，进行天文观测时有一块或以上的光学镜面暴露在外部环境中，镜面附着的霜或雪影响镜面的透光效率，降低望远镜的极限星等。从形成机理来说，镜面附着物大致可以分为3种：(1)结霜，南极冰穹 A地区常年温度范围为 $- 3 0 \mathrm { ~ \textdegree C } \sim - 8 0 \mathrm { ~ \textdegree C }$ ，晴日居多，一天内温度变化普遍在十几度以上，相对湿度范围 $4 0 \% \sim 8 0 \% ^ { \textregistered }$ 。当环境空气的相对湿度较高，镜面温度低于环境空气的露点时，镜面就开始结霜，如图1（a)。结霜的特点是在镜面的分布比较均匀，与镜面的粘附力较强。（2）自然降雪，南极是地球上最干燥的大陆，越往南极内陆，降水越少，南极点附近的年平均降水量仅有 $5 \mathrm { m m }$ ，形态呈冰晶或雪。冰晶或雪落在镜面上，透光性较差，但与镜面的粘附力较弱，如图1(b)。（3)风吹雪，冰穹 A的气象监测表明，一年中有数次风速达到 $1 0 ~ \mathrm { m / s }$ 以上的大风天气，风吹雪形成雪暴，将雪吹在镜面上，透光性差，分布不均匀，且厚度较大，如图1（c）。

位于南极冰穹A的中国昆仑站目前还不具备人员越冬的条件，因此无法实现人工辅助处理镜面的霜和雪。南极天文望远镜的镜面除霜系统旨在无人值守的条件下，去除或减少镜面附着的霜和雪，降低或消除对镜面透光效率或反射效率的影响。针对3种附着物的形成机理，镜面除霜系统采用了不同的应对策略。

![](images/603d13fa5933921884f23ba25f745e7c1c4047d1714331e3f9a566c2c8d2f379.jpg)  
图1南极天文望远镜镜面的结霜(a)、降雪(b）和风吹雪（c)Fig.1Frost and snow on the mirror of Antarctica Astronomical Telescope

(1)近几年的监测表明，镜面的结霜可以分为晶体生长期、霜层生长期和霜层充分生长期。结霜应在晶体生长期及时去除，否则霜层生长速率将快速增大。ITO(铟锡氧化物)是一种半导体透明导电膜，有电阻特性。在镜面镀ITO导电膜，导电膜通电后产生的热效应可有效消除冰霜，阻碍冰霜的形成。(2)镜面上的自然降雪和风吹雪与镜面的粘附力较弱，应对策略是在望远镜的旁边安装吹风装置，通过管道对准镜面吹风，将雪吹落。还可以在风通道里安装加热装置，对通过的气流加热，吹出热风达到除雪的目的。

两种方法中，导电膜加热对去除降雪和落雪也有作用，但效率较低；吹风方法对去除结霜有效，但功率消耗较大，且需暂停观测将镜面移动到风口位置，不适合连续长时间使用。

# 1镜面除霜系统

基于以上分析建立的镜面除霜系统的功能框图如图2，镜面除霜系统由导电膜加热子系统和吹风子系统组成。

![](images/91ea4c020d9a0786d7cd97a242a86f711528a5b29522024c1b84ce63ec04c94e.jpg)  
图2镜面除霜系统功能框图  
Fig.2Function diagram of mirror defrosting system

导电膜加热子系统有主控制系统和备份控制系统。在主控制系统的一个控制周期内，首先通过温度传感器和温度采集模块获取镜面及环境的温度，计算机软件采用闭环控制算法调节导电膜两端电压，导电膜通电后，镜面温度上升，消除镜面上已有结霜并阻碍结霜的形成。镜面除霜的主控制系统根据镜面与环境温度差进行精确控制，具有合理输出电压、减少系统耗能的优点。备份控制系统是为了增加系统的可靠性而设置的冗余系统，直接由电控制器控制备份直流电源的开关。

吹风子系统装置包括电控制器、加热器、风机及送风管道。风机将空气抽出，通过送风管道将空气吹向镜面，还可以开启加热器增强吹风效果，加热器工作产生热空气，风机将热空气吹向镜面。

# 2镜面除霜系统的故障树分析

南极天文望远镜镜面除霜系统工作的可靠性直接决定了望远镜无人值守观测的效率和质量，利用故障树分析方法研究望远镜镜面除霜系统的可靠性，即对系统各种可能的故障原因，包括硬件、软件、环境、人为等因素进行分析，由上至下按照树状结构建立故障树图[2]，通过对故障树的定性和定量分析，找出造成系统故障的所有基本事件的组合和概率，最终找出系统的薄弱环节[3-4]，为系统进行故障诊断提供理论依据。

# 2.1故障树的建立

故障树是一种基于布尔代数的树形数据结构，它用事件符号、逻辑门符号和转移符号描述系统中各层事件的因果关系[5]。故障树的最上端是顶事件，顶事件是分析的最终对象。故障树各个分支末端的事件称为基本事件，基本事件是系统的故障点和最终故障原因。顶事件和基本事件之间是中间事件，中间事件是引起顶事件的原因，同时也是基本事件造成的结果。各个节点代表故障事件之间的逻辑关系[6]。故障树的分析是从顶事件出发，依据各事件内在的逻辑关系，逐级分析故障原因，直到故障的最终原因，即基本事件[5]。故障树图的常用事件符号如表1。

表1故障树常用符号  
Table1Common symbolsof fault tree   

<html><body><table><tr><td>名称</td><td>符号表示</td></tr><tr><td>顶事件/中间事件</td><td></td></tr><tr><td>基本事件</td><td></td></tr><tr><td>未开展事件</td><td></td></tr><tr><td>与门</td><td></td></tr><tr><td>或门</td><td></td></tr><tr><td>异或门</td><td></td></tr></table></body></html>

假设一个故障树由 $n$ 个独立的基本事件构成，设 $x _ { i }$ 为基本事件的状态，只取正常或故障两种状态，即只有0和1两种取值。 $\phi$ 表示顶事件的状态，取值情况和 $x _ { i }$ 相同，则可以表示为以下形式：

$$
x _ { i } = { \left\{ \begin{array} { l l } { 1 } \\ { 0 } \end{array} \right. }
$$

$$
\phi = \left\{ \begin{array} { c c } { { 1 } } & { { \mathrm { ~ \small ~ \displaystyle ~ \operatorname ~ { ~ \small ~ J D } | \pm | \dddot { \pi } ~ } \big / 4 \dddot { \pi } \underline { { { \xi } } } \pm \big ( \mathrm { ~ \small ~ E D 1 \pm / { \xi } | \vec { \xi } | \vec { \Xi } \big ) ~ } } } \\ { { 0 } } & { { \mathrm { ~ \small ~ \displaystyle ~ \operatorname ~ { ~ \small ~ \displaystyle ~ \operatorname ~ { ~ \Longrightarrow ~ } ~ } \alpha ~ } \big / 4 \pi \uparrow \bar { \pi } \underline { { { \xi } } } \pm \big ( \mathrm { ~ \small ~ E D 1 \pm \frac { \nu \pi } { 4 } \big ) ~ } } } \end{array} \right\}
$$

由于顶事件的状态完全由基本事件的状态决定，所以

$$
X = \left( x _ { i } \right) i = 1 , 2 , \cdots , n ,
$$

称 $\phi ( X )$ 为故障树的故障函数，用以在定性分析中计算最小割集。

对于任意一棵故障树，都可以简化成逻辑与门和逻辑或门以及基本事件的组合。其中，与门结构函数为

当只取0和1两种状态时，可以写成： $\begin{array} { r l } & { \displaystyle \varPhi ( X ) = \stackrel { n } { \underset { i = 1 } { \prod } } X _ { i } , } \\ & { \displaystyle \phi ( X ) = \prod _ { i = 1 } ^ { n } X _ { i } . } \\ & { \displaystyle \phi ( X ) = \bigcup _ { i = 1 } ^ { n } X _ { i } , } \\ & { \displaystyle \phi ( X ) = 1 - \prod _ { i = 1 } ^ { n } \left( 1 - X _ { i } \right) . } \end{array}$   
或门结构函数为  
当只取0和1两种状态时，可以写成：

利用逻辑门的布尔函数将顶事件的状态表示为基本事件状态变量的布尔表达式，以进行后续的定性和定量分析[7]。

镜面除霜系统旨在降低或消除冰雪霜对镜面透光效率或反射效率的影响。设定镜面除霜系统失效的定义为望远镜镜面透光率或反射率降为正常值的 $8 0 \%$ 以下。这是一个二态系统，即系统只分为“正常”和“失效”两种状态[8]。建立一个以镜面除霜系统失效为顶事件的故障树，分析总图如图3，其中各部分故障说明标号如表2。

![](images/44a738fac1f3bcadf54fce1c3d1fecb816f5388f16cfbaa0c721c5c849a2d1a5.jpg)  
图3镜面除霜系统失效故障树分析总图Fig.3Fault tree diagram of mirror defrosting system

表2镜面除霜系统失效故障树标号说明  
Table 2 Description of the labels in mirror defrosting system fault tree   

<html><body><table><tr><td>标号</td><td>故障说明</td><td>标号</td><td>故障说明</td><td>标号</td><td>故障说明</td></tr><tr><td>T</td><td>镜面除霜系统失效</td><td>E4</td><td>接口故障</td><td>X13</td><td>元器件老化</td></tr><tr><td>A</td><td>吹风失效</td><td>E</td><td>电缆故障</td><td>X14</td><td>散热不良</td></tr><tr><td>A</td><td>导电膜加热失效</td><td>E6</td><td>电源主要器件故障</td><td>X15</td><td>焊接脱落</td></tr><tr><td>A</td><td>其他原因</td><td>E7</td><td>过压过流保护</td><td>X16</td><td>负载短路</td></tr><tr><td>B</td><td>吹风机失效</td><td>F</td><td>超出额定负载</td><td>X17</td><td>计算机故障</td></tr><tr><td>B2</td><td>供电失效</td><td>X</td><td>未进行降额设计</td><td>X18</td><td>控制参数不适用</td></tr><tr><td>B</td><td>导电膜短路/断路</td><td>X</td><td>负载电流过大</td><td>X19</td><td>算法不适用</td></tr><tr><td>C</td><td>主供电失效</td><td>X</td><td>接线错误</td><td>X20</td><td>电磁器件故障</td></tr><tr><td>C</td><td>备份供电失效</td><td>X4</td><td>温度传感器损坏</td><td>X21</td><td>触点故障</td></tr><tr><td>D</td><td>温度差采集异常</td><td>X</td><td>传感器连接线故障</td><td>X22</td><td>执行机构故障</td></tr><tr><td>D2</td><td>计算机/软件故障</td><td>X6</td><td>模块连接线故障</td><td>X23</td><td>开关触点氧化</td></tr><tr><td>D3</td><td>线路故障</td><td>X</td><td>模块主要器件故障</td><td>X24</td><td>变频器故障</td></tr><tr><td>D4</td><td>电源输出故障</td><td>X</td><td>信号衰减或干扰</td><td>X25</td><td>焊点脱落</td></tr><tr><td>D5</td><td>控制开关失效</td><td>X</td><td>传输线缆故障</td><td>X26</td><td>导电膜老化</td></tr><tr><td>E</td><td>温度传感器故障</td><td>X10</td><td>通信端口故障</td><td>X27</td><td>电极之间短路</td></tr><tr><td>E</td><td>采集模块故障</td><td>X1</td><td>电连接器故障</td><td>X28</td><td>电连接器失效</td></tr><tr><td>E</td><td>信号传输故障</td><td>X12</td><td>电缆短路/断路</td><td></td><td></td></tr></table></body></html>

# 2.2故障树的定性分析

故障树的定性分析方法即遍历导致顶事件发生的所有可能的基本事件，对各类故障进行危险性分析。故障树的定性分析是故障树分析的核心部分，主要内容是计算故障树的最小割集。最小割集即能引起顶事件发生的最低限度基本事件的集合，最小割集中的任何一个基本事件不发生，则顶事件就不会发生，最小割集的数量决定了顶事件发生的可能性的数量[9]。求最小割集的方法有很多种，常用的方法主要有行列式法、结构法和布尔代数化简法，本文采用布尔代数化简法，这种方法是先列出故障树的布尔表达式，即故障树的结构函数，从第1层事件开始用逻辑变量表示，再用下一层的事件代替上一层，直到代完为止，最后再利用有关运算定律进行化简，整理后得到的每个逻辑积就是其中一个最小割集。运算过程如下：

${ \cal T } { = } A _ { 1 } { + } A _ { 2 } { + } A _ { 3 }$ ：  
$\begin{array} { r l } & { \begin{array} { c } { A _ { 1 } = \overset { i } { B _ { 1 } } + \overset { \lambda } { X _ { 2 5 } } ; \overset { \lambda } { A _ { 2 } } = B _ { 2 } + B _ { 3 } ; } \\ { B _ { 1 } = X _ { 2 3 } + \overset { \lambda } { X _ { 4 } } ; \overset { \lambda } { B _ { 2 } } = C _ { 1 } C _ { 2 } ; \overset { B _ { 3 } } { B _ { 3 } } = X _ { 2 5 } + X _ { 2 6 } + X _ { 2 7 } ; } \end{array} } \\ & { \begin{array} { r l } { C _ { 1 } = D _ { 1 } + D _ { 2 } + D _ { 3 } + D _ { 4 } ; \overset { \lambda } { C _ { 2 } } = D _ { 4 } + D _ { 5 } ; } \\ { D _ { 1 } = E _ { 1 } + E _ { 2 } + E _ { 3 } ; \overset { \lambda } { D _ { 2 } } = X _ { 1 7 } + X _ { 1 8 } + X _ { 1 9 } ; \overset { \lambda } { D _ { 3 } } = E _ { 4 } + E _ { 5 } ; \overset { \lambda } { D _ { 4 } } = E _ { 6 } + E _ { 7 } ; } \end{array} } \\ & { E _ { 1 } = X _ { 3 } + X _ { 4 } + X _ { 5 } ; \overset { E _ { 2 } } { E _ { 2 } } = X _ { 6 } + X _ { 7 } ; \overset { E _ { 3 } } { E _ { 3 } } = X _ { 8 } + X _ { 5 } ; \overset { E _ { 4 } } { E _ { 4 } } = X _ { 1 0 } + X _ { 1 1 } ; \overset { E _ { 5 } } { E _ { 5 } } = X _ { 1 2 } ; \overset { E _ { 6 } } = X _ { 1 3 } + X _ { 1 4 } + X _ { 1 5 } ; \overset { E _ { 7 } } { E _ { 7 } } = X _ { 1 7 } ; } \end{array}$ $E _ { 7 } = F _ { 1 } + X _ { 1 6 }$ ;$\boldsymbol { F } _ { 1 } = \boldsymbol { X } _ { 1 } + \boldsymbol { X } _ { 2 }$

顶事件表达式如下：

$$
\begin{array} { r l } & { \qquad T = X _ { 1 } + X _ { 2 } + A _ { 3 } + X _ { 1 3 } + X _ { 1 4 } + X _ { 1 5 } + X _ { 1 6 } + X _ { 2 3 } + X _ { 2 4 } + X _ { 2 5 } + X _ { 2 6 } + X _ { 2 7 } + X _ { 2 8 } + X _ { 3 } X _ { 2 0 } + X _ { 3 } X _ { 2 1 } + X _ { 3 } X _ { 2 2 } . } \\ & { \qquad X _ { 4 } X _ { 2 1 } + X _ { 4 } X _ { 2 2 } + X _ { 5 } X _ { 2 0 } + X _ { 5 } X _ { 2 1 } + X _ { 5 } X _ { 2 2 } + X _ { 6 } X _ { 2 0 } + X _ { 6 } X _ { 2 1 } + X _ { 6 } X _ { 2 2 } + X _ { 7 } X _ { 2 0 } + X _ { 7 } X _ { 2 1 } + X _ { 7 } X _ { 2 2 } + X _ { 8 } X _ { 2 0 } + X _ { 8 } X _ { 2 1 } . } \\ & { X _ { 9 } X _ { 2 0 } + X _ { 9 } X _ { 2 1 } + X _ { 9 } X _ { 2 2 } + X _ { 1 0 } X _ { 2 0 } + X _ { 1 0 } X _ { 2 1 } + X _ { 1 0 } X _ { 2 2 } + X _ { 1 1 } X _ { 2 0 } + X _ { 1 1 } X _ { 2 1 } + X _ { 1 1 } X _ { 2 2 } + X _ { 1 2 } X _ { 2 0 } + X _ { 1 2 } X _ { 2 1 } + X _ { 1 2 } X _ { 2 1 } + X _ { 1 2 } X _ { 2 2 } + X _ { 1 1 } X _ { 2 2 } . } \\ & { X _ { 1 7 } X _ { 2 1 } + X _ { 1 7 } X _ { 2 2 } + X _ { 1 8 } X _ { 2 0 } + X _ { 1 8 } X _ { 2 1 } + X _ { 1 8 } X _ { 2 2 } + X _ { 1 9 } X _ { 2 0 } + X _ { 1 9 } X _ { 2 1 } + X _ { 1 9 } X _ { 2 2 } . } \end{array}
$$

最小割集如下：

{X, $ \begin{array}  c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c \end{array}$ X （204号（20$\{ X _ { 1 0 }$ （20$\{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ~ \{ X _ { 1 : \tau } , ~ X _ { 2 : \tau } \} ,$ X共52个最小割集，其中一阶最小割集有13个，二阶最小割集有39 个。

# 2.3故障树的定量分析

故障树的定量分析有两方面的含义：（1)由基本事件的发生概率求出顶事件发生的概率；（2)进行基本事件的重要度分析，根据重要度的大小优先改进可靠性较低的故障点，最后根据定量分析的结果确定系统的安全性。

不考虑某个基本事件的发生概率，仅通过观察树的结构，以决定该事件的位置重要程度，称为该基本事件的结构重要度。结构重要度分析方法有两种：（1)通过计算得到各个基本事件的结构重要度系数，再按照系数的大小进行排序，确定最终的结构重要度次序；（2)近似判断，利用最小割集的情况进行判断排序。由于南极气候及环境条件极端，各器件的失效率还缺乏可信值，本文假定所有基本事件的发生概率相等，采用近似判断法。

分析如下：对于基本事件 $X _ { 1 }$ ，在所有的最小割集中出现1次，出现的最小割集是1个一阶割集;对于基本事件 $X _ { _ 2 }$ ，在所有的最小割集中出现1次，出现的最小割集是1个一阶割集；对于基本事件$X _ { 3 }$ ，在所有的最小割集中出现3次，出现的最小割集是3个二阶割集依此类推，得到表3。

根据近似判断法的原则，对表3进行初步分析可得，对各个基本事件的结构重要度而言：

$X _ { _ { 2 0 } } = X _ { _ { 2 1 } } = X _ { _ { 2 2 } }$ > $X _ { _ { 1 } } = X _ { _ { 2 } } = X _ { _ { 1 3 } } = X _ { _ { 1 4 } } = X _ { _ { 1 5 } } = X _ { _ { 1 6 } } = X _ { _ { 2 3 } } = X _ { _ { 2 4 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { _ { 2 5 } } = X _ { _ { 2 6 } } = X _ { 2 }$ X27=X28 $> X _ { _ 3 } = X _ { _ 4 } = X _ { _ 5 } = X _ { _ 6 } = X _ { _ 7 } = X _ { _ 8 } = X _ { _ 9 } = X _ { _ { 1 0 } } = X _ { _ { 1 1 } } = X _ { _ { 1 2 } } = X _ { _ { 1 7 } } = X _ { _ { 1 8 } } = X _ { _ { 1 9 } }$

表3结构重要度对照表  
Table 3Structure importance table   

<html><body><table><tr><td>基本事件</td><td>出现次数</td><td>割集阶数</td><td>基本事件</td><td>出现次数</td><td>割集阶数</td></tr><tr><td>X</td><td>1</td><td>1个一阶</td><td>X15</td><td>1</td><td>1个一阶</td></tr><tr><td>X</td><td>1</td><td>1个一阶</td><td>X16</td><td>1</td><td>1个一阶</td></tr><tr><td>X</td><td>3</td><td>3个二阶</td><td>X17</td><td>3</td><td>3个二阶</td></tr><tr><td>X4</td><td>3</td><td>3个二阶</td><td>X18</td><td>3</td><td>3个二阶</td></tr><tr><td>X</td><td>3</td><td>3个二阶</td><td>X19</td><td>3</td><td>3个二阶</td></tr><tr><td>X6</td><td>3</td><td>3个二阶</td><td>X20</td><td>13</td><td>13个二阶</td></tr><tr><td>X</td><td>3</td><td>3个二阶</td><td>X21</td><td>13</td><td>13个二阶</td></tr><tr><td>X</td><td>3</td><td>3个二阶</td><td>X22</td><td>13</td><td>13个二阶</td></tr><tr><td>X</td><td>3</td><td>3个二阶</td><td>X23</td><td>1</td><td>1个一阶</td></tr><tr><td>X10</td><td>3</td><td>3个二阶</td><td>X24</td><td>1</td><td>1个一阶</td></tr><tr><td>X11</td><td>3</td><td>3个二阶</td><td>X25</td><td>1</td><td>1个一阶</td></tr><tr><td>X12</td><td>3</td><td>3个二阶</td><td>X26</td><td>1</td><td>1个一阶</td></tr><tr><td>X13</td><td>1</td><td>1个一阶</td><td>X27</td><td>1</td><td>1个一阶</td></tr><tr><td>X14</td><td>1</td><td>1个一阶</td><td>X28</td><td>1</td><td>1个一阶</td></tr></table></body></html>

进一步对基本事件发生的概率以及引起顶事件故障的概率进行分析。假设每个基本事件发生的概率为 $P ( X _ { i } ) = 0 . 1$ ，则可以根据表3得到的数据计算得到基本事件 $X _ { i }$ 发生则顶事件发生的概率，经计算得

$$
P ( X _ { _ { 2 0 } } ) = P ( X _ { _ { 2 1 } } ) = P ( X _ { _ { 2 2 } } ) = 0 . 1 3
$$

$$
> P ( X _ { 1 } ) = P ( X _ { 2 } ) = P ( X _ { 1 3 } ) = P ( X _ { 1 4 } ) = P ( X _ { 1 5 } ) = P ( X _ { 1 6 } ) = P ( X _ { 2 3 } ) = P ( X _ { 2 4 } ) = P ( X _ { 2 5 } ) = P ( X _ { 2 6 } )
$$

$$
( X _ { 2 7 } ) = P ( X _ { 2 8 } ) = 0 . 1
$$

$$
\begin{array} { r } { \ L \succ P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } } ) = P ( X _ { \mathfrak { z } _ { 0 } } ) = P ( X _ { \mathfrak { z } _ { 1 } } ) = P ( X _ { \mathfrak { z } _ { 1 } } ) = P ( X _ { \mathfrak { z } _ { 2 } } ) = P ( X _ { \mathfrak { z } _ { 1 } } ) } \end{array}
$$

$$
P ( X _ { 1 8 } ) = P ( X _ { 1 9 } ) = 0 . 0 3
$$

将计算得到的数据用MATLAB进行分析，各基本事件的标号作为横坐标，顶事件故障概率作为纵坐标，得到如图4的曲线。

![](images/7b05a6aa3c81a6e55e1037d930e77ddf5368d53a3a5929800fd25cb25c9de05c.jpg)  
图4MATLAB计算仿真结果图 Fig.4Matlab sumilation of the results

# 2.4故障树分析的结果

通过对镜面除霜系统失效故障树进行定性与定量分析，共求得最小割集52个，其中一阶最小割集13个，二阶最小割集39个。一阶最小割集和出现次数最多的几个二阶割集的结构重要度较大，即对整个系统的影响程度较大。理论分析得到发生概率较大的故障点有：（1)导电膜主供电系统的电源输出故障、导电膜短路/断路、吹风失效故障；（2)导电膜备份控制系统的控制开关失效故障。发生概率较小的有导电膜主供电系统的温度差采集故障、计算机/软件故障和线路故障。

# 3实验与结论

本文介绍了南极天文望远镜镜面除霜系统的工作原理和系统组成结构，并通过故障树分析方法对系统的失效原因进行分析，旨在为系统的维护、改进和完善提供理论指导和依据。首先建立了一个以镜面除霜系统失效故障为顶事件的故障树，由故障树的定性分析得到系统共有52个最小割集，每个最小割集都是引起系统故障的可能原因；随后由故障树的定量分析得出了各个基本事件的结构重要度，由此推断各基本事件对顶事件发生的影响。根据分析结果，导电膜主供电系统的电源输出故障、导电膜短路/断路、吹风失效发生的概率最大，在系统的维护、改进和完善中，应优先考虑提高导电膜主供电系统的电源、导电膜线路以及吹风设备的可靠性。

# 参考文献：

[1] Masciadri E,Lascaux F,Hagelin S.Optical turbulence: site selection above the internal antarcticplateau with a mesoscale model [C]//Proceedings of SPIE.2010.  
[2] 吴晓敏，戴万田，王维城.霜晶生长的界面演变及机制分析［J].清华大学学报：自然科学版，2007，47(8)：1352-1355+1360.Wu Xiaomin，Dai Wantian，Wang Weicheng.Theoretical analysis of interface transformationduring frost crystal growth [J]. Journal of Tsinghua University: Science and Technology，2007,47(8) : $1 3 5 2 - 1 3 5 5 + 1 3 6 0$   
[3] 高国庆.基于故障树的自适应光学电控系统故障诊断专家系统的研究［D].北京：中国科学院大学，2016.  
[4] 高国庆，周璐春.基于故障树的自适应光学电控系统可靠性分析［J].激光与光电子学进展，2016(1)：46-52.Gao Guoqing，Zhou Luchun.Fault tree analysis on reliability of electronic control system ofadaptive optics [J]. Laser & Optoelectronic Progress，2016(1） : 46-52.  
[5] 付夏楠，黄垒，魏建彦.Mini_GWAC控制系统的故障诊断专家系统［J].天文研究与技术，2016，13(3):366-372.Fu Xianan，Huang Lei，Wei Jianyan. The fault diagnosis expert system of Mini_GWAC[J].Astronomical Research & Technology，2016，13(3）:366-372.  
[6] 段隽喆，李华聪.基于故障树的故障诊断专家系统研究［J].科学技术与工程，2009，9(7): 14-17.Duan Junzhe，Li Huacong. Based on fault tree's failure diagnosis expert system research [J].Science Technology and Engineering，2009，9（7）:14-17.  
[7] 金亮亮.基于故障树的航天器故障诊断专家系统研究［D].南京：南京航天航空大学，2008.  
[8] 梁芬，姜宏伟.基于FTA的焊接机器人故障诊断技术研究［J].机电工程，2014，31（8)：1067-1070.Liang Fen，Jiang Hongwei. Analysis welding robots diagnosis based on fault tree analysis [J].Journal of Mechanical & Electrical，2014，31（8）：1067-1070.  
[9] 倪绍徐，张裕芳.基于故障树的智能故障诊断方法［J].上海交通大学学报，2008，42(8)：1372-1375.Ni Shaoxu, Zhang Yufang. Intelligent fault diagnosis method based on fault tree [J]. Journal ofShanghai Jiaotong University，2008，42(8）: 1372-1375.

# Fault Tree Analysis on Reliability of Mirror Defrosting System of Antarctica Astronomical Telescope

Feng Qingchen $^ { 1 , 2 , 3 }$ , Li Xiaoyan $^ { 1 , 2 }$ （2 (1.National AstronomicalObservatories/NanjingInstituteof Astronomical Optics&Technology，Chinese Academyof Sciences, Nanjing 210042,China，Email： xyli@niaot.ac.cn； 2.Key Laboratory of Astronomical Optics & Technology，Chinese Academy of Sciences，Nanjing 210042,China; 3.University of Chinese Academy of Sciences，Beijing 10oo49，China)

Abstract：In Antarctic optical telescope operating in Dome A，Antarctic，some mirors are exposed to harsh environment when the telescope is observing.Frost snow and ice on the surface of the mirors degrade the transmission and reflection of the optical system.Telescope mirror defrosting system is aimed to settle this problem.In this paper，a fault tree of the mirror defrosting system based on FTA（Fault Tree Analysis）is established to make sure the system works reliably.After qualitative and quantitative analysis of the fault tree, a minimal cutsetof the system is obtained and the structure importance ranking of the basic events causing the fault appears.The analysis results show clearly the botle neck of the system and point out the way to improve the reliability of the system theoretically.

Key words:Defrosting system；Fault tree analysis；Reliability analysis；Antarctica astronomical telescope