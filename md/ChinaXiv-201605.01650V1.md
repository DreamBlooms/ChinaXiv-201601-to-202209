# 探空火箭回收伞结构的开伞动载仿真分析

周伟²杨萱杨华³(1．中国科学院空间科学与应用研究中心北京100190;2.中国科学院大学,北京100049;3.内蒙古电子信息职业技术学院 内蒙古 呼和浩特010011)

摘要:针对某型号探空火箭回收伞的结构优化设计，对伞衣承受开伞动载能力与结构敏感参数的关系做了详细的研究。从解决开伞动载模型紧耦合特性难题的思路出发应用计算机建模与仿真方法建立了伞衣结构与冲击气流耦合分析的模型。通过调整伞衣结构参数对伞衣结构对开伞动载的响应做了比较分析。仿真结果表明伞衣辐射加强带附近、伞衣伞绳连接处和伞顶孔附近是环缝伞伞衣的结构薄弱环节给出了相应的增强措施，讨论了结构敏感参数与结构承载能力的关系。研究证明了上述仿真方法在结构设计中的有效性,为优化设计提供了切实可行的依据。

关键词:探空火箭;回收系统;回收伞;最大开伞动载中图分类号：V448.15 文献标识码:B

# Inflation Impact Load Simulation Analysis of Structure of Parachute for Sounding Rocket Recovery

ZHOU Wei1 '² YANG Xuan1 YANG Hua³ (1.Center for Space Science and Applied Research,Chinese Academy of Sciences,Beijing 100190,China; 2．University of Chinese Academy of Sciences,Beijing 1OOO49,China; 3.Inner Mongolia Electronic Information Technical College,Hohhot Inner Mongolia O1OO11,China)

ABSTRACT:This paper discussed in detail the relation between the inflation impact load bearing capability and he structural sensitive parameter.Starting from solving tight-coupling characteristics of inflation impactload,and using the computational modeling and numerical simulation method,the model of couplinganalysis between the structure and impact airflow was built.Byadjusting structural parameters,theresponse of thecanopy structure wasanalyzed and compared.The simulationresult shows thatthe weak parts ofring slot parachute includethe vicinityofradial reinforcing bands,theconnection betweenthecanopyandropeandthe neighboring region of the top hole.Strengthening measures and the relation between structural sensitive parameters and load bearing capabilitywere discusedaccordingly.Research in the paper proves the validityof the simulation method for structural design.Conclusions provide the solid basis for the optimization design.

KEYWORDS: Sounding rocket; Recovery system; Recovery parachute; Maximum inflation impact load

# 1引言

探空火箭是高度在40到300公里之间临近空间原位探测的唯一手段。自前以子午工程为开端的中国科学院空间中心火箭探空项目前已经进入了快速发展的阶段[1-2]。科学研究对临近空间探测不断增加的的需求以及十三五期间的箭上微重力科学实验的计划均对箭头的回收提出了较高的要求[3]。拟采用回收伞来作为箭头回收的主要方式。为使其结构强度能满足任务要求，同时由于箭头资源有限，应尽量实现轻量化对回收伞工作过程中受到的冲击载荷的仿真分析是必要的。伞衣充满时最大开伞动载可能导致伞衣上薄弱部分撕裂破坏导致回收任务的失败。

作为航天器回收的主要手段国内外科研工业部门已经对控制回收伞开伞动载的方法做了深入的研究。多种伞衣结构类型以及例如伞衣底边收口的控制方法在飞行试验[4-5]中得到了应用 取得了成功的经验。基于传统估算方法计算开伞动载下结构强度的软件系统[得到了开发与应用。近年来也采用数值仿真方法对特种降落伞开伞动载随时间变化的规律做了研究[]。但是，一直以来在国内外公开的设计资料中没有讨论过伞衣结构参数对开伞动载特性的直接影响[8]。在传统设计路线中以经验估算法来校核伞衣结构强度的方法也存在过大的设计冗余。

本文以探空火箭回收的环缝伞为例，基于开伞动载特性动力学模型的紧耦合特点，通过计算机建模和数值仿真方法对伞衣承受开伞动载能力与结构敏感参数的关系做了研究探讨。其结论具有创新性，为回收伞结构优化设计提供了直接依据。

# 2开伞动载的理论模型

# 2.1 开伞动载的来源

回收伞的开伞动载是指其在开伞过程中受到的最大冲击载荷。回收伞的结构强度通常决定于其承受最大开伞动载的能力。在开伞过程中伞结构受到的冲击作用主要发生在拉直阶段和充气阶段，而充气阶段的冲击载荷占主导因素[]。充气阶段是指伞系统从全长拉直到完全充满的过程，是回收伞工作过程中物理过程最为复杂的阶段。在特别短的时间内伞衣织物柔性结构体从收拢状态迅速变化到半球形的充满状态，发生了很大的变形同时伞衣附近的空气流场状态也发生了剧烈变化伴随着涡旋生成与脱落。伞衣结构与空气流场紧耦合相互作用。

在充气阶段伞的阻力面积迅速增大，系统下降速度突然减小。由于伞衣充满时间一般特别短暂约为0.01s至0.1s 的量级所以开伞的瞬间会给整个系统带来冲击载荷，为最大开伞动载。此时，在伞衣的薄弱的地方有可能会被撕裂。

# 2.2开伞动载的动力学模型

开伞动载特性由伞衣结构模型与冲击气流的相互作用来决定。如图1所示尺寸为 $b \times d$ 的伞衣带条可划分为如图所示四个单元 $E l m 1 - 4$ 单元节点记为 $i ( \textit { i } = \textit { i j k l } , m \textit { n } ) \ ,$ 该结构受到无穷远来流的冲击作用，其初始密度、压强、温度和速度矢量分别为 $\rho _ { \infty } \ p _ { \infty } \ , T _ { \infty } \ \stackrel { \longrightarrow } { , }$ 在各个节点上产生的等效外载荷记为 $p _ { i }$ 。各节点由此发生的位移记为 $\left\{ \delta \right\} _ { i }$ ,应变记为$\left\{ \varepsilon \right\} _ { i }$ 应力记为 $\{ { \sigma } \} _ { i }$ 。

![](images/7952e029c75737cd7018987082b621fb2fa041fd1ca09ffefff05a29b8e86cfb.jpg)  
图1伞衣结构与冲击气流的相互作用

为求得伞衣结构在开伞动载下的响应，首先由结构动力学关系可得下式：

节点位移{8}可由总体刚度方程求得:

$$
\{ R \} \ = \ [ K ] \{ \delta \}
$$

式中 $[ K ]$ 和 $\{ R \}$ 分别为总体刚度矩阵和外载荷。其中外载荷

$\{ R \}$ 即为开伞冲击载荷只与冲击气流的压强有关即

$$
\{ R \} \ = \{ p \} ^ { T }
$$

为了求解式(1），冲击气流的压强则必需从流动控制方程组求解得到。

由质量守恒、动量平衡和能量守恒关系得:

$$
\frac { \partial \rho } { \partial t } + \nabla \cdot ( \rho \vec { v } ) = 0
$$

$$
\rho \frac { \vec { d v } } { d t } = - \Delta p
$$

$$
\rho { \frac { d e } { d t } } + p \nabla \bullet { \vec { v } } = 0
$$

其中 $\boldsymbol { \mathscr { e } }$ 为比内能欧拉方程式(4）是对于无粘气流假设。式（5）对于无外界传热及粘性耗散假设。

在量热完全气体假设下状态方程与比内能有下式：

$$
\begin{array} { c } { p \ = \rho R T } \\ { e \ = \ c _ { v } T } \end{array}
$$

式中 $R$ 为气体常数 $\boldsymbol { \mathscr { \varepsilon } } _ { v }$ 为等容比热。

由方程(3）-（7）可以求解出 $\rho \stackrel {  } { , } p \ e \ , T$ 共五个未知量，所以该方程组封闭。

为了能够求解以上五个方程则还需要边界条件与初始条件。在伞衣带条面上有

$$
\overrightarrow { v _ { n } } \ = \overrightarrow { v _ { n } } \mid _ { e l m } \ = \ \frac { d } { d t } ( \ [ N ] \{ \delta \} _ { i } ^ { e } )
$$

式中 $[ N ]$ 为单元的形函数矩阵。

在初始时刻有

$$
\begin{array} { r } { \rho = \rho _ { \infty } } \\ { \stackrel {  } { \nu } = \stackrel { \longrightarrow } { v _ { \infty } } } \\ { p = p _ { \infty } } \\ { T = T _ { \infty } } \end{array}
$$

从以上两类动力学方程组可以看到结构动力学方程与流动控制方程存在相互耦合的关系只有联立求解才能得到结果。基于以上开伞动载动力学模型由于其紧耦合特点所以使用数值仿真方法成为求解开伞动载特性与结构参数关系的关键所在。

# 3开伞动载的数值仿真流程

回收伞充气阶段发生的变形是从伞衣底部流入的空气与伞衣结构相互作用的结果。显式非线性瞬态动力学仿真分析工具MSC.Dytran提供了流固耦合功能模块，在分析中将伞衣结构用拉格朗日单元来表示将空气流动用欧拉单元来表示并建立起两者耦合的关系[10]。在仿真分析中,通过定义耦合面的方式，在单元节点上传递冲击载荷 $\{ R \}$ ,实现两个域的耦合求解。仿真分析以耦合面单元节点位移 $\{ \delta \}$ 为自变量，以迭代的方式进行，经过数次循环至耦合面单元节点位移不再发生变化。伞衣单元的应力 $\{ \sigma \}$ 与应变 $\{ \varepsilon \}$ 可由下式得到式中[S]与[B]为其转换矩阵。

$$
\{ { \sigma } \} { } ~ = { } ~ [ S { } ~ ] { } \{ { \delta } \}
$$

$$
\{ \varepsilon \} = [ B ] \{ \delta \}
$$

综合流固耦合方法与有限元方法通过耦合计算的迭代过程，以输出结果的安全系数为判据，建立如图2所示的仿真分析流程。

![](images/df9e70f99d9bf085a4b2adb7d93f04b661de47bbfc1eea08063bf07b4367a01b.jpg)  
图2仿真分析流程

# 4回收伞开伞动载特性的分析

# 4.1回收伞伞衣结构特征

本算例中的回收伞伞衣类型为环缝伞,其主要的技术指标如表1所示。

表1回收伞的主要技术指标  

<html><body><table><tr><td>伞衣类型</td><td>名义面积/m²</td><td>开伞高度/km</td><td>拉直速度/m/s</td></tr><tr><td>环缝伞</td><td>28.3</td><td>5.2</td><td>50</td></tr></table></body></html>

伞衣的平面展开结构如图3所示。伞衣由6圈同心宽织物块缝制而成每条织物块宽度在 $1 0 0 \mathrm { m m }$ 以上,水平织物块之间留有缝隙。伞衣一共24幅，每一幅两侧缝有辐射加强带，作为主要承载结构。辐射加强带从伞顶孔一直延伸到伞衣底边在伞衣底边处与伞绳相连接。在伞顶孔边缘、开缝边缘和伞衣底边缘上缝制了加强筋。这些加强筋沿水平的经向与辐射加强带相垂直，也组成同心的圆，有效防止织物块被撕裂。为有效增强结构承载能力，在每一幅上缝制了数条沿径向的垂直带横跨过伞衣上的开缝。

# 4.2结构分析模型

以伞衣折叠状态为分析的初始状态。在有限元分析模型中将水平织物块与辐射缝合部划分成三节点三角形膜单元它们构成了受到冲击载荷作用的耦合面。垂直带、织物边缘的加强筋和伞绳则由一维seatbelt单元来模拟。回收箭头用四边形壳单元来建模，假设为刚体模型按照质量等效的原则赋予单元质量 $1 9 0 \mathrm { k g }$ 。主伞系统与伞衣的结构分析模型如图4所示。

进入伞衣内部的气流欧拉域用三维六面体单元来建模，该欧拉域的范围大于伞衣的运动范围，使得在充满前始终与伞衣相耦合。气流的初始条件定义为环境压强 $5 2 7 2 0 \mathrm { P a }$ 环境空气密度 $0 . 7 2 \mathrm { k g } / \mathrm { m } ^ { 3 }$ 环境空气比内能 $1 8 3 0 5 6 \mathrm { J / k g }$ 。根据织物锦纶66格子绸实际物理特性，定义其透气性参数为0.$0 0 4 ^ { [ 9 ] }$ 。材料力学参数如表2所示。

![](images/6d5ea85d4cb68110dd285a1b0544e4606cb54b761299bd753090f3bb52145881.jpg)  
图3伞衣平面展开结构特征

![](images/85c327363740d749e467a2e6e49e096b9891fa61b3c042d5572e66c6fadeecaa.jpg)  
图4主伞系统与伞衣结构分析模型

表2伞衣材料力学参数  

<html><body><table><tr><td>密度p</td><td>弹性模量E</td><td>泊松比μ</td><td>抗拉强度σ</td></tr><tr><td>1.14 ×10³kg/m³</td><td>2.92GPa</td><td>0.4</td><td>83MPa</td></tr></table></body></html>

# 4.3伞衣结构对开伞动载的响应

在最大开伞动载下伞衣最大应力水平的安全系数反映了结构承受开伞动载的能力。通过改变结构参数来获得多种工况下结构的响应值其数据可以用于以质量最小为自标的优化设计中。如表3所示根据结构参数不同在本算例中设置了三对工况a-f相应的结构参数值依次增加。在分析结果中根据最大应力安全系数和重量的比较，工况e为优选。其具体结构参数如表4对开伞动载的响应如图5-6。

表3三对工况的结构参数变化  

<html><body><table><tr><td>工况</td><td>a</td><td>b</td><td>C</td><td>d e</td><td>f</td></tr><tr><td>结构</td><td></td><td>↑</td><td>个</td><td></td><td>↑</td></tr><tr><td>参数</td><td>每幅垂直带数量增加</td><td></td><td>经向一维加强筋尺寸增加</td><td></td><td>水平带条厚度增加</td></tr><tr><td>变化</td><td></td><td></td><td></td><td>→</td><td>→</td></tr><tr><td></td><td>水平带条、辐射加强带厚度增加</td><td></td><td>经向一维加强筋、垂直带尺寸增加</td><td></td><td></td></tr></table></body></html>

表4工况e的结构参数值(按照圆形展开平面计算)  

<html><body><table><tr><td colspan="3">工况e每幅缝制5条垂直带</td><td>共计：16.8kg</td></tr><tr><td>结构组成</td><td>面积/长度/数量</td><td>厚度/尺寸/密度</td><td>质量</td></tr><tr><td>水平织物块(伞孔附近)</td><td>4.23m²</td><td>0.22mm厚</td><td>1.06kg</td></tr><tr><td>水平织物块(余下部分)</td><td>19.00m²</td><td>0.2mm厚</td><td>4.33kg</td></tr><tr><td>辐射缝合部</td><td>2.15m²</td><td>1.2mm厚</td><td>2.94kg</td></tr><tr><td>伞顶孔加强筋</td><td>4.01m</td><td>截面尺寸：10mm宽1.5mm厚</td><td>0.07kg</td></tr><tr><td>缝边加强筋</td><td>104.55m</td><td>截面尺寸：10mm宽2.0mm厚</td><td>2.38kg</td></tr><tr><td>底边加强筋</td><td>18.85m</td><td>截面尺寸：20mm宽1.5mm厚</td><td>0.65kg</td></tr><tr><td>垂直带</td><td>321.50m</td><td>截面尺寸:10mm宽1.0mm厚</td><td>3.66kg</td></tr><tr><td>伞绳</td><td>24根×每根5.52m</td><td>密度0.0130kg/m</td><td>1.72kg</td></tr></table></body></html>

![](images/495da41ce330fe86cf21bafb56d796c9f513c302f898bbd3c0c9c711c6b229e4.jpg)  
图5工况e伞衣应力云图1

![](images/0b60bb62c9dbdd69e849105344802d969675cf4bdb20c816a9752d78048b6e05.jpg)  
图6工况e伞衣应力云图2

分析结果表明，在0.11s内伞衣基本充满，结构承受的冲击载荷在0.075s至0.11s之间达到最大值。伞衣结构上产生的最大应力水平约为 $6 0 \mathrm { { M P a } }$ 在不同时刻位置分别在辐射加强带与水平织物块连接处和伞绳伞衣连接处,如上图所示。工况e的安全系数 ${ \bf S } _ { \mathrm { F } }$ 为材料抗拉强度与开伞动载下最大应力值之比，计算可得1.38。根据推荐的降落伞安全系数标准满足要求。

# 4.4 结果讨论与分析

通过以上三对工况对比分析得到结构参数与安全系数的关系如表5所示。从应力云图结果中可以得出以下结论：在如上的回收伞结构形式下最大应力发生的位置经常在辐射加强带的附近、伞绳与伞衣连接处和伞顶孔附近。对以上结构薄弱环节的改进是提高伞衣结构承载能力的重点。在优化设计过程中可采用以下措施：1）增加每幅的垂直带数量；2）增加伞绳与伞衣连接处局部的织物厚度;3）增加伞顶孔加强筋圈数。

从表5可见通过以上三个结构敏感参数的调整伞衣承受开伞动载的能力得到了显著提高。其中增加每幅的垂直带数量最为有效。对比工况a-f的变化随结构增强其安全系数逐步提高的趋势验证了数值仿真方法的有效性。一般来说在最大应力值满足一定的安全系数条件下，为了实现伞衣结构的优化应该对以下参数进行调整:1）每幅的垂直带数量、2)经向的一维加强筋截面尺寸、3)水平织物块厚度、4)辐射加强带厚度和5)垂直带截面尺寸。

表5结构敏感参数与安全系数的关系  

<html><body><table><tr><td colspan="2">结构敏感参数</td><td>工况</td><td>最大应力/MPa</td><td>安全系数SF</td><td>结构重量/kg</td></tr><tr><td>每幅垂直带数n</td><td>3</td><td>a</td><td>82</td><td>1.01</td><td>12.4</td></tr><tr><td></td><td>5</td><td>b</td><td>76</td><td>1.09</td><td>13.6</td></tr><tr><td>经向 一维加强筋</td><td>缝边加强筋10mm×1.5mm， 伞衣底边加强筋10mm×1.8mm。</td><td>C</td><td>67</td><td>1.24</td><td>15.2</td></tr><tr><td>截面尺寸</td><td>缝边加强筋10mm×2.0或1.2mm，</td><td>d</td><td>63</td><td>1.32</td><td>15.4</td></tr><tr><td>(宽b×厚d) 水平织物厚度b</td><td>伞衣底边加强筋20mm×1.5mm。</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.20mm</td><td>e</td><td>60</td><td>1.38</td><td>16.8</td></tr><tr><td></td><td>0.25mm</td><td>f</td><td>56</td><td>1.48</td><td>18.2</td></tr></table></body></html>

# 5结论

本文采用计算机辅助工程方法对回收伞结构在开伞冲击载荷下的响应做了仿真分析。为了实现满足安全系数要求且重量最轻的设计自标，文中指出了伞衣结构优化设计中的结构敏感参数,给出了薄弱环节的加强方法，讨论了伞衣承载能力与结构敏感参数的关系。通过多组工况对比给出了较优工况的分析结果其性能能满足探空火箭对回收分系统的要求。本文的结论对下一步的结构优化设计提供了直接的依据。

# 参考文献:

[1]中国科学院空间科学与应用研究中心中国科学院高技术研究与发展局．子午工程建设进展[J]．中国科学院院刊，201025(6):685-689.  
[2] 杨萱等．子午工程探空火箭伸杆展开机构技术研究[J]．空间科学学报，201333(6)：678-682.  
[3] 刘成，姜秀杰．空间环境之火箭探测[J]．现代物理知识，2012 24(5):25 -28.  
[4] Marcus Horschgen,Horst Pfeuffer,Thomas Janke.European Re-covery System(ERS) [C].Proceeding of the 19th ESA Symposiumon European Rocket and Balloon Programmes and Related Re-search．Bad Reichenhall,Germany:ESA SP-671,2009.  
[5]林斌．联盟号载人飞船降落伞系统介绍和分析[J]．航天返回与遥感，200021(4):1-6.  
[6] 余莉等．降落伞设计软件的研制[J]．计算机仿真，200421(12):66-69.  
[7] 马晓东等．涡环旋转伞系统开伞充气过程仿真研究[J]．航天返回与遥感， $2 0 1 3 3 4 ( 2 ) : 1 - 7$   
[8] 程涵，余莉，李胜全．基于ALE的降落伞充气过程数值仿真[J]．南京航空航天大学学报 $2 0 1 2 \ A 4 ( \ 3 ) : 2 9 0 \_ 2 9 3 .$   
[9] EG尤因，TW纳克， $\texttt { H W }$ 比克斯比．回收系统设计指南[M]．北京:航空工业出版社，1988.  
[10] 《降落伞技术导论》编写组．降落伞技术导论[M]．北京：国防工业出版社，1977.  
[11]卞文杰，万历，吴莘馨．瞬态动力学CAE 解决方案MSC.Dyt-ran基础教程[M]．北京:北京大学出版社，2004.

# [作者简介]

厦

周伟(1991-）男(汉族）安徽霍邱人硕士研究生主要研究领域为飞行器结构设计CAD/CAE;杨萱(1959-）女(汉族）北京人 研究员 硕士生导师主要研究领域为航天器结构分系统设计;杨华(1962-）男(汉族）北京人 副教授 主要研究领域为机械结构计算机辅助设计教学。

# （上接第93页）

[3]ZhangLi Xin,Bai Zheng Feng,Zhao Yang,Cao XiBin.Dynamicresponse of solar panel deployment on spacecraft system consideringjoint clearance[J]．Acta Astronautica,2012 \$1(1):174-185.  
[4]李逍然．大型太阳能帆板模态参数在轨辨识研究[D]．哈尔滨工业大学,2013.  
[5] 李东旭．挠性航天器结构动力学[M]．北京:科学出版社，2010.  
[6] 林家浩张亚辉．随机振动的虚拟激励法[M].北京:科学出版社，2004:60-63.  
[7] 宋向华安伟光蒋运华.任意随机激励下结构随机振动分析的一种数值方法[J]．振动与冲击，2013 32(13)：147-152，169.

[8]李璐．基于虚拟激励法的火箭仪器舱随机振动研究[D]．大连理工大学，2011.

# [作者简介]

C

宋向华(1986-）男(汉族）,河南省商丘市人，博士研究生主要研究领域为结构随机振动、动力可靠性分析;安伟光(1943-），男（汉族），黑龙江省哈尔滨市人教授主要研究领域为结构随机振动分析，结构

可靠性分析;

王杰方(1987-）女(汉族）湖北省荆门市人博士研究生主要研究领域为结构振动分析、优化设计结构可靠性分析。