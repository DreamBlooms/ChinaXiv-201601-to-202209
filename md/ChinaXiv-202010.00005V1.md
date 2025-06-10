# Caladine-English折板吸能器的能量吸收能力分析

孙博华\*†+陈品元\*\*(西安建筑科技大学土木工程学院，西安710055)\*(西安建筑科技大学力学技术研究院,西安710055)(宁波大学力学与机械工程学院，宁波315211)

摘要本文在Zhang-Yu工作的基础上，对Caladine-English 折板吸能器的能量吸收能力进行了细致分析.我们利用Maple软件对Caladine-English折板吸能器的Zhang-Yu吸能器方程编写了通用程序，并首次求得了吸能器的广义坐标（转角）随时间的变化规律.在此基础上,对于不同参数变化对Caladine-English折板吸能器的能量吸收能力的影响进行了比较研究,其中为了刻画结构的吸能能力,定义了吸能因子.为了更好的了解吸能器的运动受参数变化的影响，我们计算了吸能器动力学的相图.经过大量的数值模拟,发现从吸能能力上看,4折板吸能器应当是"质量敏感"型吸能器,完全支持Zhang-Yu的结论:即Caladine-English折板吸能器是"质量敏感"型吸能器.

关键词 质量敏感性,吸能结构,初始缺陷,四铰链模型,Maple中图分类号：0342 文献标识码：A doi:

# Energy absorbing capacity analysis of the Caladine-English crooked plates energy absorber

Sun Bohua\*\*+Chen Pinyuan\* \*（School ofCivil Engineering,Xi'an UniversityofArchitectureand Technology,Xi'an7lOo55,China) \*（InstituteofMechanicsandTechnology,Xi'an UniversityofArchitectureandTechnology,Xi'an7oo,China) †(Facultyof Mechanical Engineering& Mechanics,Ningbo University,Ningbo 315211,China)

Abstract Basedon Zhang-Yu's work,this paperanalyzesthe energyabsorptioncapacityofthe Caladine-English crooked plates energy absorber in detail.Weused Maple software to write a general program forthe Zhang-Yu energyabsorber equationofthe Caladine-Englishcrooked plates energyabsorber,andforthe firsttimeobtainedthegeneralizedcoordinate (rotation angle)of the energy absorber over time.On this basis,a comparative study was made on the influence of different parameter changes on the energy absorption capacityof Caladine-English crooked plates energy absorber.In order to define the energy absorption factor,theenergyabsorption capacity of the structure was described.In order to beter understand the efect of the movement of the energy absorber by parameter changes,we calculated the phase diagramofthe energyabsorberdynamics.Afteralotofnumerical simulations,itis found that the 4crooked plates energy absorber should bea“masssensitive”typeof energy absorberinterms ofenergyabsorptioncapacity,whichfully supports Zhang-Yu’sconclusion: the Caladine-English crooked plates energy absorberis“Mass sensitive”type energyabsorber.

Key Words mass sensitivity,energy absorbing structure,initial imperfection, four-hinge model, Maple

# 引言

力学现象.结构在服役状态难免会受到冲击荷载的的吸收，由于金属在不可逆的塑性应变阶段能够吸收大量能量，而被广泛加工为承受碰撞和冲击的吸能结构或者吸能器.在通常的弹塑性力学中，由于讨论的都是准静态问题，即这时荷载是缓慢地施加于材料或结构上,相应的变形响应也比较缓慢,所以惯性力可以忽略不计.但是，在工程实际中遇到的动态问题，在突然的强荷载作用下，材料或结构的变形速度很快，这时就材料的应变率和结构惯性的影响比较重要.就是说吸能器或者结构的设计需要考虑应变率和惯性对于吸能能力的影响[1-19].

![](images/0105274e3efa7100a96de5c2f8b3c13150f1a9435b85dea0d4900abe4b178b60.jpg)  
图1 (a)第I类典型结构模型(b)第II类典型结构模型  
Fig.1 (a)Type Itypical structure model (b)Type II typical structure

model

对于(图1)中的二种典型吸能结构，Calla-dine和English[1]指出材料应变率敏感性和惯性效应是第Ⅱ类结构速度敏感性的主要原因.显然,深入研究第ⅡI类结构的敏感性，对于设计能量吸收结构以及确定动态模型试验的尺度率十分重要

Lee和Symonds首次采用刚塑性模型研究了梁在强动载荷下的动力响应，并提出了移行铰的概念[20].此后，围绕梁在冲击荷载下的动态响应,结构冲击动力学有了长足发展[21-30].Booth等[4]在做薄钢板结构的动力试验时发现,相较于缩比尺寸试件,原型结构的变形和碰撞时间更大.Calladine等[1.3]在试图解释上述现象时发现，依照准静态载荷-位移曲线的整体形状,能量吸收结构大致可以分为两种类型：第I类具有一条相对"平坦"的载荷-位移曲线,而第ⅡI类结构的曲线"快速上升”,随后"急剧下降”.对两类结构他们设计了两组试验，发现第Ⅱ类结构的变形对碰撞速度要比第I类更敏感.换而言之，在总的输入动能恒定不变的情况下，由高速度碰撞得到的最终变形比低速度碰撞的最终变形要小，这种速度敏感现象第ⅡI类结构比第I类结构更为显著.

Yu等[2.5,19]根据两个物体间非弹性碰撞的经典理论提出四铰链模型，研究了落锤碰撞速度和质量比与碰撞时瞬时能量损失之间的关系，深刻地揭示了“速度敏感性"的实质是“质量敏感性”，同时强调了“初始几何缺陷"对“速度敏感性"的显著影响Tam和Calladine[27]进行了大量试验,发现折板响应由两相组成．第一相是折板轴向压缩,持续时间短暂;第二相是四铰链模型动力响应阶段，即刚杆绕塑性铰转动阶段.下文将会沿用这一表述

Su等[28,29]在Zhang-Yu理论模型的基础上考虑了弹性变形，并成功预测到了峰值荷载．Karagiozo-va等[30.31]利用板结构动态弹塑性屈曲的模型,综合考虑了惯性效应和材料应变率效应，对折板动力行为进行了细致研究.他们理论预测的结果与Tam等[27]试验结果大致相同.Honig等[32]基于弹-黏塑性模型,采用有限元软件ABAQUS,对碰撞作用下具有初始缺陷的折板进行了模拟．模拟结果与Tam 等[27]试验结果大体一致.卢文浩等[33]采用有限元软件ABAQUS,模拟了两类典型的能量吸收结构在铁锤动态冲击下的力学行为，他们发现：Ⅱ类结构惯性敏感性较I类结构显著；能量吸收结构的反力的峰值大小与冲击速度相关，冲击速度越大，结构反力的峰值也越大.

从目前所能看到的文献，对于第II类典型结构模型的分析工作，以Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 的工作具有代表性．由于这项杰出的工作发表于30多年前的1989年，可能限于当时的数值计算能力,Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 没有给出基本变量转动角度 $\theta ( t )$ 的时间变化规律和数值曲线.由于第Ⅱ类典型结构是很好的吸能结构，为了可以对这种吸能结构的吸能机理进一步的了解，所以有必要在Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 工作的基础上,利用现代的计算手段对其进行更加细致地分析和解剖．特别是希望可以对Zhang- $\mathrm { Y u } ^ { [ 2 ] }$ 的一个观点，即认为第Ⅱ类典型结构不是“速度敏感性"的，而是“质量敏感性"的科学判断，做出定性到定量的科学支持.

本文在Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 工作的基础上,运用工程计算软件Maple，首次求解了非线性的Zhang-Yu吸能器技术方程，得出了第Ⅱ类结构在落锤动态冲击下的不同时刻的折角与角速度的动力学.通过与Tam等[27]中的试验结果比较，验证了Zhang $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 中模型的合理性，同时总结出折板动力响应第二相一一刚杆绕铰转动阶段的一些规律.具体讲，在第2节，给出了求解Zhang-Yu方程的完整的Maple程序，和典型问题的数值计算数据，这里的程序和数据便于后续者复现计算和比较使用．在第3节，对不同参数的变化对于吸能能力的影响进行了细致的数值分析.在第4节，细致计算分析了吸能器动力学的相图在不同参数变化影响下的行为.最后，总结了7点结论，其中特别是确认了Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 认为第ⅡI类结构是"质量敏感性"的科学论断.

# 1折板吸能器理论模型和Zhang-Yu控制方程

表1符号表Table1 symbol table  

<html><body><table><tr><td>论文中参数</td><td>含义</td></tr><tr><td>T</td><td>系统在任一时刻的动能</td></tr><tr><td>T0</td><td>t=0时刻系统动能</td></tr><tr><td>Uo</td><td>初始输入动能</td></tr><tr><td>0</td><td>折板转角</td></tr><tr><td>0</td><td>初始折角</td></tr><tr><td>θ</td><td>角速度</td></tr><tr><td>0</td><td>t=0时刻角速度</td></tr><tr><td>M0</td><td>准静态完全塑性弯矩</td></tr><tr><td>00</td><td>准静态屈服应力</td></tr><tr><td>M1, M2</td><td>四铰链模型主动力矩</td></tr><tr><td>V</td><td>落锤碰撞初速度</td></tr><tr><td>m</td><td>折板质量</td></tr><tr><td>G</td><td>落锤质量</td></tr><tr><td>n</td><td>能量吸收系数</td></tr><tr><td>b</td><td>试样的宽度</td></tr><tr><td>h</td><td>试样的厚度</td></tr><tr><td>L</td><td>试样的有效长度</td></tr><tr><td>p</td><td>材料的密度</td></tr></table></body></html>

采用Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 中的四铰链模型(图2)-第ⅡI类试件可以简化成通过塑性铰连接的四根刚性杆，塑性铰处的弯矩 $M _ { 1 }$ 和 $M _ { 2 }$ 可视为主动力矩.其中L和 $\mathbf { m }$ 分别为每根杆的长度和质量，所有参量含义见表格1．假设初始速度为 $V _ { 0 }$ 的刚体G撞击样品的顶部(图2)中的点A,并且在撞击后一直沿点A向下移动.相对应的公式如下:

![](images/db61dffb19aba26021e48d53f6a278ec1268041185f7e24847df1ba329e0da62.jpg)  
图2第II类结构的四铰链模型  
Fig.2 Four-hinge model of type II structure

$$
T = { \frac { 2 } { 3 } } m L ^ { 2 } { \dot { \theta } } ^ { 2 } + 2 L ^ { 2 } ( m + G ) \sin ^ { 2 } \theta { \dot { \theta } } ^ { 2 }
$$

系统在任一时刻的势能为 $\begin{array} { r l r } { V } & { { } = } & { 0 } \end{array}$ ，所以，系统的Lagrange(拉格朗日)是 $L ~ = ~ T ~ - ~ V ~ = ~ { \frac { 2 } { 3 } } m L ^ { 2 } \dot { \theta } ^ { 2 } ~ + ~$ $2 L ^ { 2 } ( m + G ) \sin ^ { 2 } \theta \dot { \theta } ^ { 2 }$ .由于虚扭转 $\delta \boldsymbol { \theta }$ 产生的虚功为 $\mathbf { \nabla } \cdot \delta W =$ $- 4 ( M _ { 1 } + M _ { 2 } ) \theta .$ ，使用系统的广义荷载是 $\begin{array} { l l l } { { Q } } & { { = } } & { { { \frac { \delta W } { \delta \theta } } = } } \end{array}$ $- 4 ( M _ { 1 } + M _ { 2 } )$

由拉格朗日方程 $\begin{array} { r } { \frac { d } { d t } \frac { \partial L } { \partial \dot { \theta } } - \frac { \partial L } { \partial \theta } = Q } \end{array}$ ，可以推导出系统运动的微分方程[34]

$$
{ \ddot { \theta } } + { \frac { L ^ { 2 } ( m + G ) \sin \theta \cos \theta { \dot { \theta } } ^ { 2 } + M _ { 1 } + M _ { 2 } } { L ^ { 2 } \left[ { \frac { 1 } { 3 } } m + ( m + G ) \sin ^ { 2 } \theta \right] } } = 0
$$

此二阶微分方程的初始条件可由在冲击载荷情况下的拉格朗日方程得到，即

$$
\dot { \theta } _ { 0 } = \frac { G V _ { 0 } \sin \theta _ { 0 } } { 2 L \left[ m / 3 + ( m + G ) \sin ^ { 2 } \theta _ { 0 } \right] }
$$

其中 $\theta _ { 0 }$ 和 $\dot { \theta } _ { 0 }$ 分别是 $\begin{array} { r l r } { t } & { { } = } & { 0 } \end{array}$ 时刻的折角0和角速度 $\dot { \theta }$ 值.这里的公式的推导取自Zhang $\cdot \mathrm { Y u } ^ { [ 2 ] }$ ，将方程(3)称为Zhang-Yu方程.

参考Symonds等提出的Cowper-Symonds本构关系,Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 推导出折板的刚粘塑性模型和刚塑性模型的动态弯矩表达式如下：

刚粘塑性模型：

$$
M _ { 1 } = \left\{ \begin{array} { l } { { M _ { 0 } \left[ 1 + \left( 1 . 9 4 \times 1 0 ^ { - 3 } \dot { \theta } \right) ^ { \frac { 1 } { 5 } } \right] \stackrel { \scriptscriptstyle \perp \psi } { \equiv } 0 } } \\ { { \leqslant M _ { 0 } \qquad \quad \stackrel { \scriptscriptstyle \underline { { \mathrm { x f } } } } { \equiv } \dot { \theta } = 0 } } \end{array} \right.
$$

$$
M _ { 2 } = \left\{ \begin{array} { l l } { M _ { 0 } \left[ 1 + \left( 3 . 8 8 \times 1 0 ^ { - 3 } \dot { \theta } \right) ^ { \frac { 1 } { 5 } } \right] \stackrel { \simeq V } { \stackrel { \simeq } { \longrightarrow } } \dot { \theta } > 0 } \\ { \leqslant M _ { 0 } \quad } & { \stackrel { \cong V } { \stackrel { \cong } { \longrightarrow } } \dot { \theta } = 0 } \end{array} \right.
$$

刚塑性模型：

$$
M _ { 1 } = M _ { 2 } = \left\{ { \begin{array} { l } { M _ { 0 } \quad \quad \stackrel { \scriptscriptstyle \mathrm { \scriptscriptstyle : } \Psi } { = } 0 } \\ { \leqslant M _ { 0 } \stackrel { \scriptscriptstyle \mathrm { \scriptscriptstyle : } \Psi } { = } 0 } \end{array} } \right.
$$

其中 $M _ { 0 } = b h ^ { 2 } \sigma _ { 0 } / 4$ 是准静态完全塑性弯矩， $\sigma _ { 0 }$ 是准静态的屈服应力.

# 2折板吸能器问题的Maple程序和典型计算结果数据

由于Zhang-Yu方程具有强烈的非线性特性，其线性化的方程不能提供任何有价值的物理信息，解析求解不可能，所以本文将对Zhang-Yu方程进行数值模拟．为了便于结果验证和今后读者跟进复现这里的研究,本文特别使用软件Maple编写了通用程序,数值计算使用了Maple的4阶Runge-Kutta方法的求解器rkf45,使得求解这个问题可以到达很高的精度，同时避免了读者编写程序的不适用的问题

从文献看，Zhang- $\mathrm { \cdot } \mathrm { Y u } ^ { [ 2 ] }$ 文献中给出了部分数值结果,但没有给出转角 $\theta ( t )$ 的结果.由于转角 $\theta ( t )$ 是这个系统的基本未知量,有必要给出详细的计算和结果，为了便于读者自己计算和应用这里的结果,特地提供刚粘塑性模型A组的完整程序如表2，其余六组改变相应G, $V _ { 0 }$ 取值即可

相关系统参数与文献[1,2]中所使用的数值相同这些是样品的宽度, $b = 5 1 [ m m ]$ 试样的厚度, $h = 1 . 6 [ m m ]$ 样品的有效长度, $2 { \cal L } = 5 0 [ m m ]$ 单块折板重量, $m = 0 . 0 1 6 [ k g ]$ 准静态完全塑性弯矩, $M _ { 0 } = 9 . 7 9 [ N \cdot m ]$ 铁锤的初始动能， $U _ { 0 } ~ = ~ 1 2 2 [ J ]$ ，表3给出了铁锤的质量G和碰撞速度 $V _ { 0 }$ 七种组合.根据两类塑性理论,$\theta _ { 0 } ~ = ~ 1 . 1 4 6 ^ { \circ } , 2 . 6 ^ { \circ } , 4 ^ { \circ }$ 三种初始折角，分为六组进行分析.

# 表3计算数据取自CALLADINE-ENGLISH[1]

Table3 Calculateddataare takenfrom CALLADINE-ENGLISH[1]

<html><body><table><tr><td rowspan="2">Code</td><td colspan="2">G</td><td colspan="2">Vo</td></tr><tr><td>(kg)</td><td>Drop height (m)</td><td></td><td>(ms-1)</td></tr><tr><td>A</td><td>4.55</td><td>2.74</td><td></td><td>7.33</td></tr><tr><td>B</td><td>6.88</td><td>1.81</td><td></td><td>5.96</td></tr><tr><td>C</td><td>9.83</td><td>1.27</td><td></td><td>5.00</td></tr><tr><td>D</td><td>13.8</td><td>0.907</td><td></td><td>4.22</td></tr><tr><td>E</td><td>18.9</td><td>0.660</td><td></td><td>3.60</td></tr><tr><td>F</td><td>26.1</td><td></td><td>0.479</td><td>3.07</td></tr><tr><td>G</td><td>35.1</td><td>0.355</td><td></td><td>2.64</td></tr></table></body></html>

为了便于读者比较，现给出A组 $G$ 二$4 . 5 5 [ k g ] , V _ { 0 } \ = \ 7 . 3 3 [ m \cdot s ^ { - 1 } .$ 情况下计算数据，在20组不同时刻折角0和的对应值，详细数据见表格4

# 3各种参数变化对折板吸能器的吸收能量能力的影响

# 3.1变形角度对能量吸收的影响

为了更好对比初始缺陷敏感性,在Zhang- $\mathrm { \cdot } \mathrm { Y u } ^ { [ 2 ] }$ 两组初始折角 $\theta _ { 0 } ~ = ~ 1 . 1 4 6 ^ { \circ } , \theta _ { 0 } ~ = ~ 4 ^ { \circ }$ 的基础上，增设一组 $\theta _ { 0 } = 2 . 6 ^ { \circ }$ .不同组合的折角θ随时间t的关系图如下：

![](images/3023b067a44c737331a84fc2a82eb56255fae92e2061e281360265b751eca412.jpg)  
图3表3中七组G $V _ { 0 }$ 对应数值下,初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时刚粘塑性模型 $\theta ( t )$ 图像

in Table 3

![](images/f6e59bf756b31896275dd2b0d71d2cdfd9dbf8b109a0553f140ad4f89f5fc10e.jpg)  
Fig. 3 $\theta ( t )$ image of rigid-viscoplastic model with initial folding angle $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and $V _ { 0 }$   
图4表3中七组G $V _ { 0 }$ 对应数值下,初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时刚塑性模型 $\theta ( t )$ 图像  
Fig. 4 $\theta ( t )$ image of rigid-plastic model with initial foldingangle

表2刚粘塑性模型A组程序示例  
Table 2 Example of group A program for rigid viscoplastic model   

<html><body><table><tr><td>步骤</td><td>刚粘塑性模型(程序)</td></tr><tr><td>赋值</td><td>L := 25/1000 m := 0.016 G := 4.55 v_O := 7.33</td></tr><tr><td>本构模型</td><td>MLO := 9.79 convert(piecewise(x<0,0,x>0,M-0·(1+( Heaviside M_1 := MHeaviside (dif(t),t)) +2.80650451 Heaviside (di(t),t)(dif(t),t))1/5 convert piecewisex<0,0,x>0,M_0· 1+000·x Heaviside</td></tr><tr><td>微分方程</td><td>M_2 := M_0Heaviside(dif(t),t)) +3.225143455 Heaviside (diff(t),t)(dif(0(t),t))1/5 a := L²·(m + G)· sin(0(t))·cos(t))· dif(t),t) ·diff(t),t) + M_1 + M_2 b := L²·( + (m + G)· sin(t))· sin(0(t))</td></tr><tr><td>初始条件0=1.146°</td><td>sys := diff(0(t),t,t)+ =0 bcs := 0(0)= 1.146π,D(0)(0) = G·v_0·sin(1-146) 2.L(m+(m+G)sin(11）)</td></tr><tr><td>解方程</td><td>sol := dsolve ({ sys,bcs},numeric,output =listprocedure) T := ·m· L² .(dif(0(t),t)² + 2· L² · (m+ G) · (sin(0(t)))² · (diff(t),t))²</td></tr><tr><td>方程</td><td>H:= n:=1-H</td></tr><tr><td>绘图</td><td>gl := plots:-odeplot (sol,[t,(t)]， t = 0..0.89067682e-3,color = red,legend = 0) hl := plots:-odeplot (sol,[t,H],t = 0.0.89067682e-3,color = red,legend=A) f1 := plots:-odeplot(sol,[t,n],t =0.0.89067682e-3,color = red,legend=A)</td></tr><tr><td>初始条件0 = 4° 解方程</td><td>bcs_2:= 0(0)= ,D(0)(0) = G·v-0-sin(） (m+(m+G)sin())</td></tr><tr><td></td><td>sol_2:= dsolve ({ sys,bcs_2},numeric,output =listprocedure) g2 := plots:-odeplot(sol_2,[t,0(t)]， t= 0..0.51093006e-2,color = blue,legend = 0)</td></tr><tr><td>绘图</td><td>h2 := plots:-odeplot (sol_2,[t,H],t = 0..0.51093006e-2,color= blue,legend=A) f2 := plots:-odeplot(sol_2,[t,n],t = 0..0.51093006e-2,color = blue,legend=A)</td></tr><tr><td>初始条件0 = 2.6°</td><td>bcs-3:= 0(0)= 2,D((0)=2 Gv-0sin() 2.L(m+(m+G)sin(²）²)</td></tr><tr><td>解方程 绘图</td><td>sol.3:= dsolve ({ sys,bcs_3},numeric,output =listprocedure) g3 := plots:-odeplot (sol_3,[t,0(t)]， t= 0..0.35142103e-2,color = black,legend = 0)</td></tr></table></body></html>

表4A组 $G = 4 . 5 5 [ k g ]$ $V _ { 0 } = 7 . 3 3 [ m \cdot s ^ { - 1 } .$ 计算结果数据表  
Table 4 When $G = 4 . 5 5 [ k g ]$ $V _ { 0 } = 7 . 3 3 [ m \cdot s ^ { - 1 } ]$ ,calculated results data table in group A   

<html><body><table><tr><td colspan="3">刚粘塑性模型= 1.146</td><td colspan="3">刚粘塑性模型 =4°</td><td colspan="3">刚塑性模型 = 1.146°</td><td colspan="3">刚塑性模型θ = 4°</td></tr><tr><td>t[ms]</td><td>0</td><td>[rad/s]</td><td>t[ms]</td><td>0</td><td>[rad/s]</td><td>t[ms]</td><td>0</td><td>[rad/s]</td><td>t[ms]</td><td>0</td><td>[rad/s]</td></tr><tr><td>0</td><td>0.0200</td><td>1863.2881</td><td>0</td><td>0.0698</td><td>1688.8352</td><td>0</td><td>0.0200</td><td>1863.2881</td><td>0</td><td>0.0698</td><td>1688.8352</td></tr><tr><td>0.0468</td><td>0.0734</td><td>760.5072</td><td>0.2689</td><td>0.2583</td><td>418.1586</td><td>0.1595</td><td>0.1401</td><td>428.5202</td><td>0.7424</td><td>0.4265</td><td>267.3300</td></tr><tr><td>0.0936</td><td>0.1021</td><td>505.3475</td><td>0.5308</td><td>0.3393</td><td>289.8303</td><td>0.3190</td><td>0.1947</td><td>280.9162</td><td>1.4848</td><td>0.5876</td><td>180.9920</td></tr><tr><td>0.1404</td><td>0.1226</td><td>383.7338</td><td>0.8067</td><td>0.4142</td><td>213.2657</td><td>0.4785</td><td>0.2337</td><td>214.1282</td><td>2.2272</td><td>0.7060</td><td>141.7471</td></tr><tr><td>0.1872</td><td>0.1387</td><td>308.8665</td><td>1.0756</td><td>0.4658</td><td>173.2901</td><td>0.6380</td><td>0.2644</td><td>173.5131</td><td>2.9696</td><td>0.8017</td><td>117.6900</td></tr><tr><td>0.2340</td><td>0.1519</td><td>256.4686</td><td>1.3445</td><td>0.5084</td><td>145.0008</td><td>0.7975</td><td>0.2897</td><td>145.1565</td><td>3.7120</td><td>0.8824</td><td>100.6927</td></tr><tr><td>0.2808</td><td>0.1629</td><td>216.8262</td><td>1.6134</td><td>0.5444</td><td>123.4842</td><td>0.9570</td><td>0.3110</td><td>123.6722</td><td>4.4544</td><td>0.9521</td><td>87.6050</td></tr><tr><td>0.3276</td><td>0.1723</td><td>185.2092</td><td>1.8823</td><td>0.5752</td><td>106.1670</td><td>1.1165</td><td>0.3293</td><td>106.4785</td><td>5.1968</td><td>1.0131</td><td>76.9165</td></tr><tr><td>0.3744</td><td>0.1803</td><td>159.0061</td><td>2.1512</td><td>0.6017</td><td>91.6778</td><td>1.2760</td><td>0.3452</td><td>92.1613</td><td>5.9392</td><td>1.0667</td><td>67.8005</td></tr><tr><td>0.4212</td><td>0.1872</td><td>136.6418</td><td>2.4201</td><td>0.6246</td><td>79.1916</td><td>1.4355</td><td>0.3588</td><td>79.8710</td><td>6.6816</td><td>1.1140</td><td>59.7620</td></tr><tr><td>0.4680</td><td>0.1931</td><td>117.1026</td><td>2.6890</td><td>0.6444</td><td>68.1783</td><td>1.5950</td><td>0.3707</td><td>69.0607</td><td>7.4240</td><td>1.1557</td><td>52.4841</td></tr><tr><td>0.5148</td><td>0.1982</td><td>99.7020</td><td>2.9579</td><td>0.6614</td><td>58.2798</td><td>1.7545</td><td>0.3809</td><td>59.3591</td><td>8.1664</td><td>1.1921</td><td>45.7540</td></tr><tr><td>0.5616</td><td>0.2025</td><td>83.9569</td><td>3.2268</td><td>0.6758</td><td>49.2445</td><td>1.9140</td><td>0.3897</td><td>50.5020</td><td>8.9088</td><td>1.2237</td><td>39.4231</td></tr><tr><td>0.6084</td><td>0.2061</td><td>69.5164</td><td>3.4957</td><td>0.6880</td><td>40.8904</td><td>2.0735</td><td>0.3971</td><td>42.2945</td><td>9.6512</td><td>1.2507</td><td>33.3847</td></tr><tr><td>0.6552</td><td>0.2090</td><td>56.1206</td><td>3.7646</td><td>0.6979</td><td>33.0834</td><td>2.2330</td><td>0.4032</td><td>34.5872</td><td>10.3936</td><td>1.2733</td><td>27.5605</td></tr><tr><td>0.7020</td><td>0.2114</td><td>43.5761</td><td>4.0335</td><td>0.7058</td><td>25.7243</td><td>2.3925</td><td>0.4081</td><td>27.2619</td><td>11.1360</td><td>1.2917</td><td>21.8917</td></tr><tr><td>0.7488</td><td>0.2130</td><td>32.7292</td><td>4.3024</td><td>0.7118</td><td>18.7425</td><td>2.5520</td><td>0.4119</td><td>20.2218</td><td>11.8784</td><td>1.3058</td><td>16.3333</td></tr><tr><td>0.7956</td><td>0.2143</td><td>20.5345</td><td>4.5713</td><td>0.7159</td><td>12.0960</td><td>2.7115</td><td>0.4146</td><td>13.3846</td><td>12.6208</td><td>1.3159</td><td>10.8502</td></tr><tr><td>0.8424</td><td>0.2150</td><td>9.9420</td><td>4.8402</td><td>0.7183</td><td>5.7864</td><td>2.8710</td><td>0.4162</td><td>6.6780</td><td>13.3632</td><td>1.3220</td><td>5.4138</td></tr><tr><td>0.8906</td><td>0.2153</td><td>0.0125</td><td>5.1090</td><td>0.7191</td><td>0.0052</td><td>3.0313</td><td>0.4167</td><td>0.0020</td><td>14.1050</td><td>1.3240</td><td>0.0042</td></tr></table></body></html>

$\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ under the corresponding values of seven groups of G and $V _ { 0 }$

![](images/a8dc634b059ffe2e1fd85409b10724ebdba69410e123a14ba40a6bdf96fdedbe.jpg)  
图6表3中七组 ${ \bf G } , V _ { 0 }$ 对应数值下,初始折角 $\theta _ { 0 } = 2 . 6 ^ { \circ }$ 时刚塑性模型0(t)图像

![](images/2227b00ceb96c8b5eb17e4cc1cee617957f4965de3d6b818c3c76fac0fe8877f.jpg)  
图5表3中七组G， $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 2 . 6 ^ { \circ }$ 时刚粘塑性模型 $\theta ( t )$ 图像

in Table 3

![](images/de560b11517e749ea1a9794de7cb1fe454b3ed9330b62b9764fec8bfcfec3423.jpg)  
Fig. 6 $\theta ( t )$ image of rigid-plastic model with initial folding angle $\theta _ { 0 } = 2 . 6 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and $V _ { 0 }$   
Fig. 5 $\theta ( t )$ image of rigid-viscoplastic model with initial folding angle

$\theta _ { 0 } = 2 . 6 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and $V _ { 0 }$

Fig.7 0(t) image of rigid-viscoplastic model with initial folding angle $\theta _ { 0 } = 4 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and $V _ { 0 }$ in

![](images/06c218882108dbf7f5cbb934b1143cde8c5a3f2c17c3a2571c8c0da317bac709.jpg)  
图7表3中七组 ${ \bf G } , V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 4 ^ { \circ }$ 时刚粘塑性模型0(t)图像

Fig. 8 $\theta ( t )$ image of rigid-plastic model with initial foldingangle $\theta _ { 0 } = 4 ^ { \circ }$ under the corresponding values of seven groups of G and $V _ { 0 }$ in

Table3

图例中A、B、C、D、E、F、G分别对应于表2中G, $V _ { 0 }$ 取值情况.以图3中A组蓝线为例进行说明：图中蓝线表示 $\scriptstyle \mathbf { G } = 4 . 5 5$ [kg], $V _ { 0 } = 7 . 3 3 [ m \cdot s ^ { - 1 } ]$ (见表3中A组数据),采用刚粘塑性理论模型,在初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时计算所得到的折角 $\theta$ 与时间t的关系图.从以上图形可以得到以下结论：

(1)当落锤输入动能 $U _ { 0 } = 1 2 2 [ J ]$ 为定值时，随着速度 $V _ { 0 }$ 逐渐减小(落锤重量G相应增大)，最终折角0增大,即碰撞损失的能量减少．这与文献[1,2.30.31,33]中所得到的第ⅡI类结构“速度/质量敏感性"的结论是完全一致的.

(2)随着初始折角 $\theta _ { 0 }$ 的增大，无论是刚粘塑性模型还是刚塑性模型，A-G组中相邻组之间最终折角θ的差值明显减小，质量敏感性减弱，而且结构变形的速度更加缓慢．这与Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 中强调的"初始几何缺陷"对“质量敏感性"的显著影响是吻合的.

(3)当 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，尽管速度 $V _ { 0 }$ 不断改变,其快速变形阶段变形速率保持一致；但是随着初始折角 $\theta _ { 0 }$ 的增大，不同组间变形速度随着 $V _ { 0 }$ 改变明显分层，初始速度 $V _ { 0 }$ 越大(G相应越小)，变形速度越快．余同希等[19]给出了解释:当初始折角较小时,横向惯性对折板吸能器的动力行为起支配作用，

(4)与刚塑性模型相比，刚粘塑性模型最终转角大幅 降低,且其变形过程更加迅速.这可能是考虑了塑性 流动与应变率效应导致的.

# 3.2质量比和初始速度对能量吸收的影响

在系统响应的第二相，刚性杆稳定地绕着四个铰转动，其最终转角与系统第一相碰撞后剩余的能量 $T _ { 0 }$ 成正比．Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 推导出公式(8)并指出,当 $U _ { 0 } = G V _ { 0 } ^ { 2 } / 2$ 不变时，初速度 $V _ { 0 }$ 的改变是由质量G的改变导致的．为了进一步看出初始速度 $V _ { 0 }$ 和 $T _ { 0 }$ 之间的关系.由公式(8)绘出了 $T _ { 0 } / U _ { 0 } { - } G / m$ 和 $T _ { 0 } / U _ { 0 } - V _ { 0 }$ 的图像.图中实线、虚线、点划线分别代表初始折角 $\theta _ { 0 }$ 等于 $1 . 1 4 6 ^ { \circ }$ 、 $2 . 6 ^ { \circ }$ 、 $4 ^ { \circ }$ 的情况.

![](images/c307e4894361f42513b13ef6072a03ed7f9dfebfac16539d286de99bc5e2d2f1.jpg)  
Table 3   
图9 $T _ { 0 } / U _ { 0 }$ 与 $\mathrm { { G / m } }$ 的关系图

![](images/40155ebd84f1adec19f3488b553698278065115d0ba96fce7b2f789fdd1551b5.jpg)  
图8表3中七组G $V _ { 0 }$ 对应数值下,初始折角 $\theta _ { 0 } = 4 ^ { \circ }$ 时刚塑性模型0(t)图像  
Fig. 9 The diagram of $T _ { 0 } / U _ { 0 }$ and $\mathrm { G / m }$   
图 $1 0 \ T _ { 0 } / U _ { 0 }$ 与初始速度 $V _ { 0 }$ 的关系图  
Fig.10 The diagram of $T _ { 0 } / U _ { 0 }$ and the initial velocity $V _ { 0 }$

从上图可以看出,

(1)在碰撞的瞬时有部分能量损失，质量比 $\mathbf { m } / \mathbf { G }$ 越大，初始速度 $V _ { 0 }$ 越大，能量损失的越多.(2)初始缺陷对质量敏感性影响十分显著.随着初始折角 $\theta _ { 0 }$ 的增大,质量敏感性极大削弱，而且随着质量比的增大( $\cdot \mathrm { \Delta } V _ { 0 }$ 相应的增大),削弱的程度越明显，

为了进一步了解系统响应的第二相的能量耗散情况，将求解出的数值解代入方程(1)绘出了如下情况的 $T / U _ { 0 } - t$ 的关系图.以下图形根据三种不同初始折角值和两种塑性理论分为六组：

![](images/bd12e1af2a0cadf771f4a7297aecb7e865b321e5d8ad0f9483cdd13626480287.jpg)  
图11表3中七组G, $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时刚粘塑性模型 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ 图像

Fig. 11 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ image of rigid viscoplastic model with initial folding angle $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ under the corresponding values of seven groups of G

and $V _ { 0 }$ in Table 3

![](images/a2162ecb4f74cd19d5c5cdace906bf6add602d8569f228912516809a3cae1049.jpg)  
图12表3中七组G， $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时刚塑性模型 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ 图像

Fig. 12 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ image of rigid plastic model with initial folding angle $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ under the corresponding values of seven groups of G and $V _ { 0 }$

in Table 3

Fig. 14 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ image of rigid plastic model with initial folding angle $\theta _ { 0 } = 2 . 6 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and $V _ { 0 }$

in Table 3 and $V _ { 0 }$ in Table 3

![](images/bc6cef4c57ecbc3313d1a45eb9da36551c1ff3ac834b3fe294503c78503c41ee.jpg)  
图14表3中七组 ${ \bf G } , V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 2 . 6 ^ { \circ }$ 时刚塑性模型 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ 图像

Fig. 13 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ image of rigid viscoplastic model with initial folding angle $\theta _ { 0 } = 2 . 6 ^ { \circ }$ under the corresponding values of seven groups of G

![](images/c874b0c3aa84235f6b0b046a42ce51dfcdefcf1e90a9f7569ba121d56c0b2e03.jpg)  
图13表3中七组G， $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 2 . 6 ^ { \circ }$ 时刚粘塑性模型 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ 图像

![](images/1b2008606b9db4d9dc60d7d0b6a34ac728870f9f97390e732b6a6b52d4bfa631.jpg)  
图16表3中七组 ${ \bf G } , V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 4 ^ { \circ }$ 时刚塑性模型 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ 图像

Fig. 15 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ image of rigid viscoplastic model with initial folding angle $\theta _ { 0 } = 4 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and

$V _ { 0 }$ in Table 3

![](images/b87b1ed07bce0b003db172d88f7bdeaf6ff7d2bd60c1b822732f44b8d657fc88.jpg)  
图15表3中七组 ${ \bf G } , V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 4 ^ { \circ }$ 时刚粘塑性模型 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ 图像

Fig. 16 $\begin{array} { r } { \frac { T } { U _ { 0 } } ( t ) } \end{array}$ image of rigid viscoplastic model with initial folding angle $\theta _ { 0 } = 4 ^ { \circ }$ under the corresponding values of seven groups of G and

$V _ { 0 }$ in Table 3

图例中A、B、C、D、E、F、G分别对应于表3中G, $V _ { 0 }$ 取值情况.以图11中A组蓝线为例进行说明：图中蓝线表示 $\cdot G = 4 . 5 5 [ k g ] , V _ { 0 } = 7 . 3 3 [ m \cdot s ^ { - 1 } ]$ (见表3中A组数据)，采用刚粘塑性理论模型,在初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时计算所得到的能量比 $T / U _ { 0 }$ 与时间t的关系图.从上列图形中可以看出：

(1)t等于0的时刻， $T _ { 0 }$ 的值与图9保持一致,且刚粘塑性模型与刚塑性模型没有差异.(2)质量比 $\mathbf { m } / \mathbf { G }$ 越大(初始速度 $V _ { 0 }$ 越大)，系统响应的第二相耗能越快,而初始折角 $\theta _ { 0 }$ 减缓这种趋势(3)刚粘塑性模型与刚塑性模型耗能趋势总体保持一致，后者耗能时间大约是前者的两到三倍.

# 3.3折板吸能器的吸收能量能力分析

为了定量的预测结构的吸能能力，引入一个能量吸收系数

$$
\eta ( t ) = \frac { U _ { 0 } - T } { U _ { 0 } } = 1 - \frac { T } { U _ { 0 } } .
$$

![](images/6fb7635a76f637bd5c54a82bfd8ced767d54e106fe0e5453b9736298692ab61c.jpg)  
图17表3中七组G $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时刚粘塑性模型能量吸收系数 $\eta ( t )$ 图像

![](images/d993cec2acd92184ab5da2915f1dd315653f78c1c0d21a20a5f80ae91189bcc4.jpg)  
图20表3中七组G， $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 2 . 6 ^ { \circ }$ 时刚塑性模型能量吸收系数 $\mathbf { \dot { \eta } } _ { \eta ( t ) }$ 图像

Fig. 17 $\eta ( t )$ image of rigid viscoplastic model with initial folding angle $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ under the corresponding values of seven groups of G and $V _ { 0 }$

Fig. $2 0 \eta ( t )$ image of rigid plastic model with initial folding angle $\theta _ { 0 } = 2 . 6 ^ { \circ }$ under the corresponding values of seven groups of G and $V _ { 0 }$

in Table 3

![](images/b629c6165e07be50d88ce52c8ee63465d8b19109ebcbe2e18b8227bce868bd8a.jpg)

![](images/2869d6baf77f7134b840ecb2d089d02be0ccfb75e95cccafd81abc11518069de.jpg)  
图21表3中七组G $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 4 ^ { \circ }$ 时刚粘塑性模型能量吸收系数 $\mathbf { \dot { \eta } } _ { \eta ( t ) }$ 图像  
Fig. 21 $\eta ( t )$ image of rigid viscoplastic model with initial folding angle

Table 3

Fig. 18 $\eta ( t )$ image of rigid plastic model with initial folding angle $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and $V _ { 0 }$ $\theta _ { 0 } = 4 ^ { \circ }$ under the corresponding values of seven groups of G and $V _ { 0 }$ in

![](images/deca0d2225d83cf420c95d0945b11280690083946c2bd371512ba68f33711584.jpg)  
图22表3中七组G， $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 4 ^ { \circ }$ 时刚塑性模型能量吸收系数 $\eta ( t )$ 图像  
Fig. 22 $\eta ( t )$ image of rigid plastic model with initial folding angle

![](images/b6701e70b415922c1f6248e293f40f5c930b222a4d44dadd1f078ab740dddd42.jpg)  
图18表3中七组 ${ \bf G } , V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时刚塑性模型能量吸收系数 $\eta ( t )$ 图像  
图19表3中七组G， $V _ { 0 }$ 对应数值下，初始折角 $\theta _ { 0 } = 2 . 6 ^ { \circ }$ 时刚粘塑性模型能量吸收系数 $\eta ( t )$ 图像

$\theta _ { 0 } = 4 ^ { \circ }$ under the corresponding values of seven groups of $\mathbf { G }$ and $V _ { 0 }$ in

Table 3

Fig. 19 $\eta ( t )$ image of rigid viscoplastic model with initial folding angle$\theta _ { 0 } = 2 . 6 ^ { \circ }$ under the corresponding values of seven groups of G and $V _ { 0 }$ 图例中A、B、C、D、E、F、G分别对应于表3中 $G , V _ { 0 }$ 取值情况.以图17中A组蓝线为例进行说明：图中蓝线表示 $\cdot G = 4 . 5 5 [ k g ] , V _ { 0 } = 7 . 3 3 [ m \cdot s ^ { - 1 } ] ($ (见表3中A组数据),采用刚粘塑性理论模型,在初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时计算所得到的能量吸收系数 $\mathbf { \dot { \eta } }$ 与时间t的关系图.

从上列图形中可以看出：随着质量G的增大(初速度 $V _ { 0 }$ 相应减小)，能量吸收系数 $\dot { \eta }$ 相应减小；初始折角 $\theta _ { 0 }$ 对能量吸收系数 $\eta$ 影响显著， $\theta _ { 0 }$ 越小，对 $\overset { \cdot } { \eta }$ 影响越显著,这与之前得到的结论是一致的.

对于时亥 $\begin{array} { r l r l r l } { \parallel { t } } & { { } } & { = } & { { } } & { 0 . } \end{array}$ 联立方程(1)和(3),Zhang和 $\mathrm { Y u } ^ { [ 2 ] }$ 得到

$$
\frac { T _ { 0 } } { U _ { 0 } } = \left\{ 1 + \frac { m } { G } \left( 1 + \frac { 1 } { 3 \sin ^ { 2 } \theta _ { 0 } } \right) \right\} ^ { - 1 } < 1
$$

所以, $t = 0$ 时刻的能量吸收系数是 $\begin{array} { r } { \eta ( 0 ) = 1 - \frac { T _ { 0 } } { U _ { 0 } } } \end{array}$ 是

$$
\eta ( 0 ) = { \frac { { \frac { m } { G } } \left( 1 + { \frac { 1 } { 3 \sin ^ { 2 } \theta _ { 0 } } } \right) } { 1 + { \frac { m } { G } } \left( 1 + { \frac { 1 } { 3 \sin ^ { 2 } \theta _ { 0 } } } \right) } }
$$

式中Uo= G是撞击物体的初始动能,To是碰撞后瞬 间系统动能,即公式(9)中T在 $t = 0$ 时的值.

![](images/ac7301d86c44087f45cebdc3eee38a1ceb9c84bd6870c3fc8b4e38a0af21897c.jpg)  
图23公式 $\begin{array} { r } { ( 9 ) \eta _ { 0 } - \theta _ { 0 } - \frac { m } { G } } \end{array}$ 三维图

$\eta ( 0 ) = 1 - T _ { 0 } / U _ { 0 }$ 表示在初始时刻，系统有能量损失，初始角度 $\theta _ { 0 }$ 的影响很小，质量比 $m / G$ 的影响比较显著，既杆的重量 $m$ 越大，吸收刚体质量 $\boldsymbol { \cdot } \boldsymbol { G }$ 冲击的能量能力越强.

![](images/5af36239e1655d6b66faa52d4a0bfe7538a26a181b13ae5a69bf5fdd151683cd.jpg)  
Fig. $\begin{array} { r } { 2 3 \eta _ { 0 } - \theta _ { 0 } - \frac { m } { G } } \end{array}$ three-dimensional diagram of formula (9)   
图24刚粘塑性A组 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时 $\eta ( t ) - \theta ( t ) - t$ 三维曲线图 Fig.24 Three-dimensional graph of $\eta ( t ) - \theta ( t ) - t$ for rigid viscoplasticity group a with $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$

# 4转速动力学相图分析

# 4.1初始缺陷变化的动力学相图分析

为了定量分析初始缺陷对于吸能结构的影响，以A组数据为例，下面给出了刚粘塑性和刚塑性模型下不同初始折角的 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图.

图 25刚粘塑性模型A组：不同初始折角 $\theta _ { 0 } = i ^ { \circ } / 2$ 下 $\textstyle { \overbrace { \theta \mathrm { ~ - ~ } { \frac { d \theta } { d t } } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

![](images/e89f6c6f34bd11c8b8b918c7b2765fe0ad69c3c00d40e89992d0aa7f9124f63b.jpg)  
图 26 刚塑性模型A组：不同初始折角 $\theta _ { 0 } = i ^ { \circ } / 2$ 下 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

![](images/e9cfdc2d2650c93c24f2fca671980fca279cf13223696385fb5180c56ba2e8d1.jpg)  
Fig. 25 Rigid viscoplastic model group A: $\textstyle { \theta - { \frac { d \theta } { d t } } }$ rotational speed phase diagram with different initial folding angles $\theta _ { 0 } = i ^ { \circ } / 2$ ,where $\mathrm { i } { = } 1 , 2 . . . 1 0$   
Fig. 26 Rigid plastic model group A $\textstyle { \theta - { \frac { d \theta } { d t } } }$ rotational speed phase diagram with different initial folding angles $\theta _ { 0 } = i ^ { \circ } / 2$ ,where $\mathrm { i } { = } 1 , 2 { \dots } 1 0$

其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$ ，相对应的曲线初始折角为 $\theta _ { 0 } \ = \ i ^ { \circ } / 2$ （204号以图25中蓝线 $\mathrm { i } = 1$ 为例进行说明：图中蓝线表示 $G =$ $4 . 5 5 [ k g ] , V _ { 0 } = 7 . 3 3 [ m \cdot s ^ { - 1 } ] ($ (见表3中A组数据),采用刚粘塑性理论模型，在初始折角 $\theta _ { 0 } = 0 . 5 ^ { \circ }$ 时计算所得到的转角 $\theta$ 与角速度 $\textstyle { \frac { d \theta } { d t } }$ 的转速相图.

从以上相图可以看出：(1)刚粘塑性模型和刚塑性模型计算出的在相平面中的运动轨迹大致相同;(2)在 $\theta _ { 0 } \leqslant 2 ^ { \circ }$ 时，随着初始折角的增大,初始角速度和最终折角值也增大(碰撞损失能量减少)这与之前得到的结论一致; $( 3 ) \theta _ { 0 } = 0 . 5 ^ { \circ }$ 和 $| \theta _ { 0 } = 1 ^ { \circ }$ 时,折板吸能器运动轨迹与其他各组存在明显差异，此时初始角速度大幅降低(碰撞损失能量增大),折板吸能器吸能能力优异，这也能更好看出初始缺陷对折板吸能器动态行为的显著影响！

# 4.2初始碰撞速度变化的动力学相图分析

为了定量分析初始碰撞速度 $V _ { 0 }$ 对于吸能结构的影响，在保证输入动能 $U _ { 0 } ~ = ~ 1 2 2 [ J ]$ 不变的情况下,下面给出了刚粘塑性和刚塑性模型下初始折角分别为 $1 . 1 4 6 ^ { \circ }$ 、4时的不同初始碰撞速度 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图.

![](images/af9e818229492ee61f7936760098c37b79706aa8678ad9a20d5ede122a481ff0.jpg)  
图27刚粘塑性模型组： $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，不同初始碰撞速度 $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$ 下 $\textstyle { \overbrace { \theta \mathrm { ~ - ~ } { \frac { d \theta } { d t } } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

Fig.27 Rigid viscoplastic model: when $\textstyle \theta _ { 0 } = 1 . 1 4 6 ^ { \circ } , \theta - { \frac { d \theta } { d t } }$ rotational speed phase diagram with different impact velocities $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$

![](images/885a868ea72174ace9cc3541ed7ac6b14f09e2fb13bfd83691ed6dcf8d035377.jpg)

![](images/8b38afd42ece9ec7cd0613bfd6347f4059d0eab708190e86936c5dad5b45a673.jpg)  
图30刚塑性模型组： $\theta _ { 0 } = 4 ^ { \circ }$ 时，不同初始碰撞速度 $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$ 下 $\textstyle \overtheta - { \frac { d \theta } { d t } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

Fig.30 Rigid plastic model: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speedphase diagram with different impact velocities $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$ ,where其中 $\mathrm { i } { = } 1 , 2 { \dots } 1 0$ ，相对应的曲线初始碰撞速度为 $V _ { 0 } ~ =$ $i [ m \cdot s ^ { - 1 } ]$ ．以图27中蓝线 $\mathrm { i } { = } 1$ 为例进行说明：图中蓝线表示落锤初始碰撞速度 $V _ { 0 } = 4 [ m \cdot s ^ { - 1 } ]$ ，采用刚粘塑性理论模型,在初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时计算所得到的转角 $\theta$ 与角速度 $\textstyle { \frac { d \theta } { d t } }$ 的转速相图.

从以上相图可以看出：(1)当初始折角很小时，相平面折板吸能器运动轨迹较为混乱，随着初始折角增大，相图分布趋于规律且运动趋势类似;(2)初始碰撞速度很小时，速度的改变对折板吸能器吸能能力影响显著，且随着初始碰撞速度的增大折板吸能器吸能能力减弱.

Fig.28 Rigid plastic model group:when $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ , the phase diagram of $\textstyle { \theta - { \frac { d \theta } { d t } } }$ under different initial collision speeds $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$

# 4.3落锤质量G变化的动力学相图分析

为了定量分析落锤质量对于吸能结构的影响，在保证输入动能 $\begin{array} { r l r } { U _ { 0 } } & { { } = } & { 1 2 2 [ J ] } \end{array}$ 不变的情况下，下面给出了刚粘塑性和刚塑性模型下初始折角分别为 $1 . 1 4 6 ^ { \circ }$ 、 $4 ^ { \circ }$ 时不同落锤质量的 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图.

![](images/c6ef4ebc0d5290308d363aa0a7c31726b3575e36cb70604e8a24b64eba0d4ad4.jpg)  
图28刚塑性模型组： $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，不同初始碰撞速度 $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$ 下 $\textstyle \overbrace { \theta \mathrm { - } \ \frac { d \theta } { d t } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$   
图29刚粘塑性模型组： $\theta _ { 0 } = 4 ^ { \circ }$ 时，不同初始碰撞速度 $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$ 下 $\textstyle { \boldsymbol { \theta } } - { \frac { d \theta } { d t } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

Fig.29 Rigid viscoplastic model: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speed phase diagram with different impact velocities $V _ { 0 } = i [ m \cdot s ^ { - 1 } ]$ ,where

![](images/ab061dd7697cad2c34df20de880547dc8a20f6057c4c2d6f555fbaed57b01e76.jpg)  
图 31 刚粘塑性模型组: $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时,不同落锤质量 $G = 4 i [ k g ]$ 下 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

Fig. 31 Rigid viscoplastic model: when $\textstyle \theta _ { 0 } = 1 . 1 4 6 ^ { \circ } , \theta - { \frac { d \theta } { d t } }$ rotational speed phase diagram with different drop weights $G = 4 i [ k g ]$ ，where

![](images/578fb214692f369f09d6cf5ac6fff1f01b0076a50a7d48d99234465d8bbf38d3.jpg)  
图32刚塑性模型组： $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，不同落锤质量 $\boldsymbol { G } = 4 i [ k g ]$ 下 $\begin{array} { r } { \theta - { \frac { d \theta } { d t } } } \end{array}$ 转速相图,其中 $\mathsf { i } { = } 1 , 2 . . . 1 0$

Fig.32 Rigid plastic model: when 0 = 1.146°,0-d rotational speedphase diagram with different drop weights $G = 4 i [ k g ]$ ,where $\mathrm { i } { = } 1 , 2 { \dots } 1 0$ （204其中 $\mathrm { i } { = } 1 , 2 . . . 1 0 ,$ 相对应的曲线落锤质量为 $G \ : = \ : 4 i [ k g ]$ =以图31中蓝线 $i = 1$ 为例进行说明：图中蓝线表示落锤质量 $\mathit { G } = 4 [ k g ]$ ，采用刚粘塑性理论模型,在初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时计算所得到的转角 $\theta$ 与角速度 $\textstyle { \frac { d \theta } { d t } }$ 的转速相图.

![](images/155076a8a352dd30e43a4cc7dc09d1ae0dd5fd3eba2ec746925c22619598058a.jpg)  
图 33 刚粘塑性模型组: $\theta _ { 0 } = 4 ^ { \circ }$ 时,不同落锤质量 $G = 4 i [ k g ]$ 下 $\textstyle \overtheta - { \frac { d \theta } { d t } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$ （204号

![](images/8ed44b9712590a226c17bc2d1fbd2e9b3990f48e97de5af71c14bd34e1448d80.jpg)  
Fig. 33 Rigid viscoplastic model: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speed phase diagram with different drop weights $G = 4 i [ k g ]$ ,where $\mathrm { i } { = } 1 , 2 { \dots } 1 0$ （204号   
Fig.34 Rigid plastic model: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speed phase diagram with different drop weights $G = 4 i [ k g ]$ ,where $\mathrm { i } { = } 1 , 2 . . . 1 0$

从以上相图可以看出：(1)刚粘塑性模型和刚塑性模型计算出的在相平面中的运动轨迹大致相同;(2)当落锤质量变化时，初始折角很小的情况下，折板吸能器运动轨迹十分相似,部分重叠,即此时折板吸能器吸能能力变化很小.随着初始折角增大，相图呈规律分布，此时随着落锤质量增大折板吸能器吸能能力显著增强，

# 4.4折板质量 $\mathbf { m }$ 变化的动力学相图分析

为了定量分析折板质量 $\mathbf { m }$ 对于吸能结构的影响,在保证输入动能 $U _ { 0 } ~ = ~ 1 2 2 [ J ]$ 不变的情况下，下面给出了刚粘塑性和刚塑性模型下初始折角分别为 $1 . 1 4 6 ^ { \circ }$ 、 $4 ^ { \circ }$ 时不同折板质量的 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图.

![](images/d182ce7e449ab833a7a6bac77b12adb25c318a7b3a6233ddc8f0628057b6e650.jpg)  
图35刚粘塑性模型A组： $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，不同折板质量 $m = 0 . 0 1 \cdot i [ k g ]$ 下 $\textstyle { \overbrace { \theta \mathrm { ~ - ~ } { \frac { d \theta } { d t } } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$ （204号

Fig35Rigidvisopa: $\textstyle \theta _ { 0 } = 1 . 1 4 6 ^ { \circ } , \theta - { \frac { d \theta } { d t } }$ rotational speed phase diagram with different drop weights $m = 0 . 0 1 \cdot i [ k g ]$ ,where

![](images/67428224669b1a40310ce8928c0fb2bb5944956a5045c65d216d12a6243ea60b.jpg)  
图36刚塑性模型A组： $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，不同折板质量 $m = 0 . 0 1 \cdot i [ k g ]$ 下 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$ （204号

Fig. 36 Rigid plastic model: when $\textstyle \theta _ { 0 } = 1 . 1 4 6 ^ { \circ } , \theta - { \frac { d \theta } { d t } }$ rotational sped phase diagram with different drop weights $m = 0 . 0 1 \cdot i [ k g ]$ ,where

![](images/50877ab67b476dab5b1ca878923e626b231545e525177c3c529f6823b9c51432.jpg)  
图 34 刚塑性模型组: $\theta _ { 0 } = 4 ^ { \circ }$ 时,不同落锤质量 $G = 4 i [ k g ]$ 下 $\textstyle \theta - { \frac { d \theta } { d t } }$ 转速相图，其中 $_ { 1 = 1 , 2 \dots 1 0 }$   
图37 刚粘塑性模型A组: $\theta _ { 0 } = 4 ^ { \circ }$ 时,不同折板质量 $m = 0 . 0 1 \cdot i [ k g ]$ 下 $\textstyle { \overbrace { \theta \mathrm { ~ - ~ } { \frac { d \theta } { d t } } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

Fig.37Rigidviscoplastcodel: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speed phase diagram with different drop weights $m = 0 . 0 1 \cdot i [ k g ]$ ,where

![](images/5ce17174625972bba4b19037be54ba81bb18c74437546e7958655e8f6f03c802.jpg)  
图38刚塑性模型A组: $\theta _ { 0 } = 4 ^ { \circ }$ 时，不同折板质量 $m = 0 . 0 1 \cdot i [ k g ]$ 下 $\textstyle \overtheta - { \frac { d \theta } { d t } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 { \ldots } 1 0$ （204

Fig. 38 Rigid plastic model: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speedphase diagram with different drop weights $m = 0 . 0 1 \cdot i [ k g ]$ ,where其中 $\mathrm { i } { = } 1 , 2 . . . 1 0 .$ 相对应的曲线折板质量为 $ { m } = \ 0 . 0 1$ $i [ k g ]$ ，以图35中蓝线 $i = 1$ 为例进行说明：图中蓝线表示折板质量 $m = 0 . 0 1 [ k g ]$ ，采用刚粘塑性理论模型,在初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时计算所得到的转角 $\theta .$ 与角速度 $\textstyle { \frac { d \theta } { d t } }$ 的转速相图.

从以上相图可以看出：刚粘塑性模型和刚塑性模型计算出的在相平面中的运动轨迹大致相同；值得注意的是，当 $m \leqslant 0 . 0 3 [ k g ]$ 时,随着折板质量的增加，碰撞瞬间损失能量迅速增加，折板吸能器运动轨迹变化很大.随着折板质量继续增大，相图变化不明显，对折板吸能器吸能影响减弱

# 4.5折板与落锤质量比 $\mathbf { m } / \mathbf { G }$ 的动力学相图分析

为了定量分析折板与落锤质量比 $\mathbf { m } / \mathbf { G }$ 对于吸能结构的影响,在保证输入动能 $U _ { 0 } = 1 2 2 [ J ]$ 不变的情况下，下面给出了刚粘塑性和刚塑性模型下初始折角分别为 $1 . 1 4 6 ^ { \circ }$ 、 $4 ^ { \circ }$ 时不同质量比的 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图.

![](images/ec36d65534450f9012c7ae3b66039b9d0c1fa17399e7960e0528fac03ca4ac93.jpg)  
图39刚粘塑性模型A组： $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时,不同质量比 $\begin{array} { r } { m / G = \frac { 1 } { 3 0 0 \cdot i } } \end{array}$ 下 $\textstyle { \theta - { \frac { d \theta } { d t } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$ （204号

Fig.39 Rigid viscoplastic model: when $\textstyle \theta _ { 0 } = 1 . 1 4 6 ^ { \circ } , \theta - { \frac { d \theta } { d t } }$ rotational speed phase diagram with different mass ratios $\begin{array} { r } { m / G = \frac { 1 } { 3 0 0 \cdot i } } \end{array}$ ,where

![](images/b7d0e9b5a11d86d9f4311efc92110797a80be10aa38d24046f6f3c8ccded48d9.jpg)  
图40刚塑性模型A组： $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，不同质量比 $\begin{array} { r } { m / G = \frac { 1 } { 3 0 0 \cdot i } \operatorname { T } \theta - \frac { d \theta } { d t } } \end{array}$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 { \ldots } 1 0$ （20

Fig. 40 Rigid plastic model: when $\textstyle \theta _ { 0 } = 1 . 1 4 6 ^ { \circ } , \theta - { \frac { d \theta } { d t } }$ rotational speed phase diagram with diferent mass ratios $m / G = { \frac { 1 } { 3 0 0 \cdot i } }$ ,where $\mathrm { i } { = } 1 , 2 . . . 1 0$

![](images/143c5a8f81e3924aaedd9fe916a57700ef85432e78f0572e07e7d488571ab6e0.jpg)

Fig. 41 Rigid viscoplastic model: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speed phase diagram with different mass ratios $\begin{array} { r } { m / G = \frac { 1 } { 3 0 0 \cdot i } } \end{array}$ , where $\mathrm { i } { = } 1 , 2 . . . 1 0$

![](images/6d6d5f8f027df580661783543c95acf78673849fb2585b88976a204181e75696.jpg)  
图41 刚粘塑性模型A组: $\theta _ { 0 } = 4 ^ { \circ }$ 时,不同质量比 $m = 0 . 0 1 \cdot i [ k g ]$ 下 $\textstyle { \overbrace { \theta \mathrm { ~ - ~ } { \frac { d \theta } { d t } } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 { \dots } 1 0$ （20  
图42 刚塑性模型A组: $\theta _ { 0 } = 4 ^ { \circ }$ 时,不同质量比 $\begin{array} { r } { m / G = \frac { 1 } { 3 0 0 \cdot i } } \end{array}$ 下 $\textstyle { \overbrace { \theta \mathrm { - } { \frac { d \theta } { d t } } } }$ 转速相图,其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$

Fig. 42 Rigid plastic model: when $\begin{array} { r } { \theta _ { 0 } = 4 ^ { \circ } , \theta - \frac { d \theta } { d t } } \end{array}$ rotational speedphase diagram with diferent massratios $\begin{array} { r } { m / G = \frac { 1 } { 3 0 0 \cdot i } } \end{array}$ , where $\mathrm { i } { = } 1 , 2 . . . 1 0$ 其中 $\mathrm { i } { = } 1 , 2 . . . 1 0$ 相对应的曲线质量比为 $\begin{array} { r } { { \bf \nabla } [ m / G = \frac { 1 } { 3 0 0 \cdot i } } \end{array}$ .以图39中蓝线 $\mathbf { \Phi } _ { i } ~ = ~ 1$ 为例进行说明：图中蓝线表示质量比 $m / G = { \textstyle \frac { 1 } { 3 0 0 } }$ ，采用刚粘塑性理论模型,在初始折角 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时计算所得到的转角 $\theta$ 与角速度 $\textstyle { \frac { d \theta } { d t } }$ 的转速相图.

从以上相图可以看出：(1)刚粘塑性模型和刚塑性模型计算出的在相平面中的运动轨迹大致相同,特别是初始折角较大时近乎重叠.但是，当初始折角很小时，随着质量比的变化相图明显分层，即质量比对折板吸能器吸能能力影响显著;(2)当质量比变化时，初始折角对相图变化的影响相较于其他几组更小.

# 5结论

本文采用工程计算软件Maple数值计算的方法，在输入动能恒定时，对7组不同质量G(初始速度)的落锤进行了折板的动态行为研究，重点分析了不同塑性理论、不同初始折角、不同质量G(初始速度)对折板结构动态行为的影响，得到如下主要结论：

(1)"速度敏感性"与碰撞时的瞬时能量损失密切相关，随着初始速度 $V _ { 0 }$ 增大，能量损失增大，结构最终变形减小.此能量损失取决于质量比 $\mathrm { G / m }$ 和初始折角 $\theta _ { 0 }$ ．因为输入动能 $U _ { 0 }$ 不变时，质量G的改变引起了初始速度 $V _ { 0 }$ 的改变.因此Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 中将"速度敏感性"称为“质量敏感性”

(2)"质量敏感性"受到结构"初始缺陷"的强烈影响，随着第ⅡI类结构的初始折角 $\theta _ { 0 }$ 的增加，质量敏感性会严重减弱，而且随着质量比增大( $\cdot \mathrm { \Delta } V _ { 0 }$ 相应的增大)最终位移的差距越明显，

(3)刚塑性模型和刚粘塑性模型第一相碰撞能量损失相同，但是与刚塑性模型相比,刚粘塑性模型最终转角大幅降低,且其变形过程更加迅速.这可能是考虑了塑性流动与应变率效应导致的，

(4)当 $\theta _ { 0 } = 1 . 1 4 6 ^ { \circ }$ 时，尽管落锤质量G不断改变,其快速变形阶段变形速率保持一致；但是随着初始折角 $\theta _ { 0 }$ 的增大，不同组间变形速度随着G改变明显分层，落锤质量G越小，变形速度越快

(5)质量比越大,系统响应的第二相耗能越快,而初始折角 $\theta _ { 0 }$ 减缓这种趋势，

(6)折板吸能结构的设计改进,由上文分析可知,质量比 $\mathrm { m } / \mathrm { G }$ 越大,初始折角越小,碰撞损失能量越多，能量吸收系数 $\eta$ 越大.故在冲击物质量G定值时，保证折板强度的情况下，增大折板质量和减小初始折角更有利于吸收能量，且 $\theta _ { 0 } \leqslant 1 . 5 ^ { \circ }$ 时吸能效果更为理想，可以采用密度较大的材料，并通过适当增加折板长度来达到优化吸能性能的目的.

(7)本文的研究结论(1)(2)与Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 推导的理论结果一致,也和文献[1,3]中的实验结果、文献[33]中有限元模拟结果相吻合.这完全支持了Zhang- $\cdot \mathrm { Y u } ^ { [ 2 ] }$ 文中关于第II类结构的“质量敏感性"的科学论断

此外，本文也给出了折板动力行为第一相到第二相的转变过程以及第二相的动态特征，并就折板吸能结构的设计改进提供了一些建议，希望能够给相关研究者提供一些参考.

致谢：余同希教授是国际结构弹塑性动力学等领域的著名学者，本文是基于余先生的一项研究成果2,作者希望以此文向余先生致敬.同时，作者还想感谢研究生戴远帆，郭晓琳，吴凡对论文中图3-图8的整理和提供的一些宝贵建议，

# 参考文献

1 Calldine CR,English R W.Strain-rate and inertia effects in the collapse of two types of energy-absorbing structure.Int.J.Mech.Sci, 1984,26: 689-701   
2 Zhang TG, Yu TX.A note on a'velocity sensitive’ energy-absorbing structure. Int. J. Impact Engng,1989,8: 43-51   
3 Calldine C R.An investigation of impact scaling theory. In: Jones N,Wierzbicki T.In Structural Crashworthiness.London,1983.169- 174   
4 Booth E, Collier D,Miles J.Impact scalability of plate steel structures.In: Jones N,Wierzbicki T.In Structural Crashworthiness. London,1983.136-168   
5 余同希,邱信明.冲击动力学.北京:清华大学出版社,2011.(Yu Tongxi,Qiu Xinming.Impact dynamics.Beijing: Tsinghua University Press,2011(in Chinese))   
6 Atkins A G.On the number of cracks in the axial splitting of ductile metal tubes.Int.J.Mech. Sci.,1987,29:115-121   
7 余同希，章亮炽．塑性弯曲理论及其应用．北京：科学出版社, 1992.(Yu Tongxi, Zhang Liangchi. Plastic Bending: Theory and Applications.Beijing: Science Press,1992 (in Chinese))   
8 Stronge WJ, Yu TX.Dynamic Models for Structural Plasticity. London: Springer-Verlag,1993   
9 余同希,华云龙．结构塑性动力学引论.合肥：中国科技大学出 版社,1994.(Yu Tongxi, Hua Yunlong.Introduction to Structural Plasticity Dynamics.Hefei: University of Science and Technology of China Press,1994 (in Chinese))   
10 Yu TX,Zhang LC.Plastic Bending:Theory and Applications. World Scientific, Singapore,1996   
11 Yu TX,Zhang LC,Reid SR. Interaction between reflected elastic flexural waves and a plastic 'hinge' in the dynamic response of pulse loaded beams.Int.J. Impact Engng,1997,19: 457-475.   
12 Reid SR, Yu TX, Zhang LC.An elastic-plastic hardening-sodtening cantilever beam subjected to a force pulse at its tip:a modelfor pipe whip. Proc.R. Soc.Lond. A 1998,454: 997-1029   
13 Gao ZY, Yu TX,Lu G.A study on type I structure. part I : a modified one-dimensional mass-spring model. Int. J. Impact Engng, 2005,31: 895-910   
14 Gao ZY, Yu TX, Lu G.A study on type II structure. part II: dynamic behaviour of a chain of pre-bent plates. Int. J. Impact Engng, 2005,31: 911-926   
15 Olabi A G,Morris E,Hashmi M S J. Metalic tube type energy absorbers: A synopsis. Thin. Wall. Struct.,2007,45:706-726   
16 赵桂平，卢天健．多孔金属夹层板在冲击载荷作用下的动态响 应.力学学报,2008,02:194-206 (Zhao Guiping,Lu Tianjian. Dynamic response of porous metal sandwich plate under impact load. Chinese Journal of Theoretical and Applied Mechanics,2008,02: 194-206 (in Chinese))   
17 Chai GB,Manikandan P.Low velocity impact response of fbremetal laminates-a review. Compos. Struct.,2014,107:363-381   
18Fang H,BiJ,ZhangC,etal.A constitutive model of aluminum foam forcrash simulations.Int.J.NonlinearMech.,2017,9O:124-136   
19 余同希,卢国兴，张雄.能量吸收：结构与材料的力学行为和塑性 分析.北京：科学出版社,2019.（Yu Tongxi,Lu Guoxing,Zhang Xiong.Energy absorption:mechanical behavior and plasticity analysis of structures and materials.Beijing:Science Press,2O19 (in Chinese))   
20 Lee E H, Symonds P S.Large plastic deformations of beams under transverse impact.J.Appl.Mech,1952,19:308-314   
21Bodner SR,SymondsP S.Experimental and theoretical investigation of the plastic deformation of cantilever beams subjected to impulsive loading.J.appl.Mech,1962,29:719-728   
22Martin JB.A note on the uniqueness of solutions for dynamically loaded rigid-plastic and rigid-viscoplastic continua.J.Appl. Mech., 1966,33:207-209   
23Martin JB,SymomdsP S.Mode approximations for impulsively loaded rigid-plastic structures.J.Eng.Mech.Div.,1966,92:43-66   
24 Jones N.Plastic failure of ductile beams loaded dynamically. J. Eng. Ind.,1976,19:131-136   
25Shen W Q,Jones N.A failure criterion for beams under impulsive loading.Int.J.Impact Engng,1992,12:101-121   
26GrzebietaRH,MurrayNW.Energy absorption of an initially imperfect strut subjected to an impact load.Int.J.Impact.Engng, 1986,4(3):147-159   
27 TamLL,Calldine CR.Inertia and strain-rate effects in a simple plate-structure under impact loading.Int.J.Impact Engng,1991, 11: 349-377   
28Su XY,Yu TX,Reid SR. Inertia-sensitive impact energy-absorbing structures part I：effects of inertia and elasticity.Int.J.Impact Engng,1995,16:651-672   
29Su XY,Yu TX,Reid SR.Inertia-sensitive impact energy-absorbing structures part II: effects of strain rate.Int.J. Impact Engng,1995, 16: 651-672   
30Karagiozova D,Jones N.Some observations on the dynamic elasticplastic bucking of a structural model.Int.J. Impact Engng,1995, 16:621-635   
31Karagiozova D,Jones N.A note on the inertia and strain-rate effects in the tam and calladine model. Int.J.Impact Engng,1995,16: 637-649   
32Honig A, Stronge W J.Dynamic bucking of an imperfect elastic, visco-plastic plate.Int.J.Impact Engng,200o,24: 907-923   
33 卢文浩，鲍荣浩.动态冲击下能量吸收结构的惯性敏感性的数值 模拟分析.振动与冲击,2004,23(3):54-60(Lu Wenhao,Bao Ronghao.Numerical simulation study on the inertia sensitiveness of energyabsorbing structures under impact loading.Journal of Vibration and Shock,2004,23(3): 54-60 (in Chinese))   
34Landau L.D.,Lifshitz.Mechanics,3rd ed.E.M.:Pergamon Press, 1976