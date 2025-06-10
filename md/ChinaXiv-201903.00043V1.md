# 变频空调用PFC电感的仿真研究

景　馨」　王春芳　王世伟² 王放（1.青岛大学自动化与电气工程学院青岛 2660712.青岛云路新能源科技有限公司青岛266109）

![](images/ac1b3eb3a33de5b94f096d59bc795de093f3246cb2c58b1d023983c5fc852b23.jpg)

景馨女1993年生，硕士研究生，研究方向为电力电子电磁热耦合场仿真技术。

摘要：针对变频空调用功率因数校正（PFC）电路中的电感在运行时存在局部过热、温升较高的情况，本文采用电磁热耦合仿真对其进行了优化设计。通过有限元分析，搭建了PFC电感三维电磁热场的仿真模型，利用电磁仿真计算得出PFC电感的功率损耗，并将其作为热源进行了热场模拟。通过改变绕组的匝数和磁心的尺寸，模拟了四组不同的设计方案，分别进行了磁场－热耦合分析，从中给出了优化设计方案。实际运行表明，优化后的PFC电感有效降低了温升和损耗，设计方法对于其他电感器件的设计具有参考价值。

关键词：变频空调PFC 电感 有限元 电磁热场中图分类号：TM402

# Simulation Study of PFC Inductor for Variable Frequency Air Conditioner

Jing Xin'Wang Chunfang1Wang Shiwei² Wang Fangl (1.Qingdao UniversityQingdao266071 China 2.Qingdao Yunlu Energy Technology Co.LtdQingdao 266109 China ）

![](images/288897d9c7b00db11b47a345944c7fdd5f4a6949b76bd422321cd6e3454fa6e5.jpg)

王春芳男 1964年生，博士，教授，研究方向为电能变换技术及新能源开发技术。

Abstract: In view of the local overheating and the higher temperature rise of the inductance in the power factor correction (PFC) circuit of the inverter air conditioner during operation, the electromagnetic coupling simulation is adopted to optimize the design of the inductor.The three-dimensional electromagnetic thermal field simulation model of PFC inductor is established by the finite element analysis method.The power loss of each component of the reactor is calculated by electromagnetic simulation,and the thermal field is simulated as a heat source.By changing the number of turns and the size of the magnetic core, four different design schemes are simulated. The magnetic field thermal coupling analysis is carried out, and the optimal design scheme is given. The actual operation shows that the optimized PFC inductor effectively reduces the temperature rise and loss,and the design method is of reference value for the design of other inductors.

Keywords: Variable frequency air conditioner, power factor correction inductance, finite element analysis,electromagnetic thermal field

# 1 引言

随着电力电子技术的发展及人民生活水平的提高，变频空调已逐渐占据了空调市场的主流地位。相比传统定频空调，变频空调具有高效、节能和静音等诸多优点，越来越被广大用户所青睐[1]。为了减少变频空调对电网的谐波污染，通常会在变频空调中增加功率因数校正（PFC）电路。PFC电感是PFC电路中的关键元件，其磁心结构及电气参数的优化设计至关重要，不当设计会造成电感局部温升过高，甚至会造成空调损坏。针对PFC电感的设计，文献[2]提出了一种混合磁路PFC电感，各个材料均可以发挥长处，既可以使磁路得到平衡，还可以降低高频损耗。文献[3]提出了一种贴片耦合电感的设计方案，两个反向耦合绕组的磁通相互抵消，显著地降低了铁氧体中的磁通，提高了功率电感的饱和电流。文献[4]对非晶磁性PFC电感的设计进行了详细分析，实验结果表明，铁基非晶磁性材料具有饱和磁通密度高、温度稳定性好的特点。

本文以变频空调用PFC电感为研究对象，采用相同的电感模型，选取四种不同结构的磁心进行模拟设计，利用有限元软件分别进行磁场和温度场仿真，分别得到了铁损和铜损的具体数值，通过分析、比较，从中得到了温升较低的设计方案。

# 2 PFC电感的电磁热耦合场数值分析

# 2.1PFC电感的电磁场计算数学模型

PFC 电感工作在正常情况下，产生的损耗主要包括铜损与铁损，铜损一般是指存在于绕组线圈里的欧姆损耗，磁滞损耗是铁损的主要组成部分[5]。

整体损耗可以表达为

$$
P = P _ { \mathrm { C u } } + P _ { \mathrm { F e } }
$$

PFC电感的三维模型由涡流区与非涡流区组成。以下为控制方程

$$
\boldsymbol { \nabla } \times \frac { 1 } { \mu } \boldsymbol { \nabla } \times \boldsymbol { A } - \boldsymbol { \nabla } \frac { 1 } { \mu } \boldsymbol { \nabla } \cdot \boldsymbol { A } + \sigma \frac { \partial \boldsymbol { A } } { \partial t } + o \boldsymbol { \nabla } V = 0
$$

$$
\nabla \left( - \sigma \frac { \partial A } { \partial t } - \sigma \nabla V \right) = 0
$$

式中， $\sigma$ 为电导率（ $\mathrm { { . s / m } ) }$ ； $\boldsymbol { \mu }$ 为磁导率（ $\mathrm { { ( H / m ) } }$ ； $\boldsymbol { V }$   
为标量电位（V）； $A$ 为矢量磁位； $t$ 为时间。

非涡流区的控制方程为

$$
\nabla \times \frac { 1 } { \mu } \nabla \times \boldsymbol { A } - \nabla \frac { 1 } { \mu } \nabla \cdot \boldsymbol { A } = 0
$$

# 2.2PFC电感的温度场计算数学模型

热传导、热对流和热辐射是PFC电感正常运行中产生损耗主要的途径。考虑到PFC电感内部空气对流较为缓慢且热辐射较弱，在热损耗分析时仅考虑PFC电感的热传导方式。

在计算温度场时，热传导方程为

$$
\rho C _ { \mathrm { p } } \frac { \partial \theta } { \partial t } - \nabla \cdot ( k \nabla \theta ) - P = 0
$$

式中， $\rho$ 为密度 $( \mathrm { k g / m } ^ { 3 } )$ ； $C _ { \mathfrak { p } }$ 为比热容 $( \mathrm { J / ( k g \cdot K ) } )$ ，$\theta$ 为温度（℃）； $k$ 为热导率（ $\mathrm { W } / ( \mathrm { m } \cdot \mathrm { K } ) ,$ ； $P$ 为生热率 $\mathrm { \Delta W / m ^ { 3 } }$ ）

对于散热的边界条件，即为PFC电感与空气接触的外表面，公式表达为

$$
- \lambda \frac { \partial \theta } { \partial n } = \alpha ( \theta _ { \mathrm { 0 } } - \theta _ { \mathrm { f } } )
$$

式中， $\alpha$ 为表面散热系数（ $\mathrm { W } / ( \mathrm { m } ^ { 2 } \cdot \mathrm { K } )$ ）； $\theta _ { 0 }$ 为发热体温度 （ $\mathrm { ~ \mathcal ~ { ~ C ~ } ~ } ,$ ； $\theta _ { \mathrm { f } }$ 为环境温度 $\big ( \mathrm { ‰ }$ 。

# 2.3PFC电感的电磁热耦合场计算

在分析PFC电感的电磁热耦合场计算和运行过程时，涡流损耗与线圈中产生的焦耳热是各个部件会出现温升的主要原因。

根据磁场和涡流场分析，可以得到电感产生的涡流损耗为

$$
P _ { \mathrm { F e } } = \frac { 1 } { \sigma } \big | J \big | ^ { 2 }
$$

$$
J = \nabla \times \frac { 1 } { \mu } \nabla \times \boldsymbol { A }
$$

而由于PFC电感中的非涡流区所引起焦耳损耗，可由以下公式得出

$$
P _ { \mathrm { C u } } = R I ^ { 2 }
$$

式中， $R$ 为线圈的电阻 $( \Omega )$ ； $I$ 为通入线圈的电流有效值（A）。

# 3PFC电感的电磁热耦合场建模

# 3.1变频空调用PFC的电路拓扑

变频空调用PFC电路如图1所示。电感 $L$ 为 PFC 电感，工频AC220V输入经整流、PFC功率因

数校正电路后为变频电路供电[]。PFC 电感 $L$ 在充放电过程中，因设计不当，容易出现温升过高，从而降低了空调的可靠性。

![](images/d73dfb790208b6e6c6306699ac556f255b57015926308f0a23e7b83a98310c8b.jpg)  
图1变频空调用PFC电路  
Fig.1PFC circuit for variable frequency air conditioner

# 3.1.1PFC电路的工作参数

设通过PFC电感 $L$ 的电流为 $I _ { \mathrm { d } }$ ，电容 $C$ 的电压为 $U _ { \mathrm { d } }$ ，输入电流为 $i _ { 2 }$ 。交流输入电压 $U _ { \mathrm { i } }$ : 220VAC,$5 0 \mathrm { { H z } }$ 。额定输出电压 $U _ { \mathrm { o } }$ ： $3 8 0 \mathrm { V }$ 。输入功率 $P _ { \mathrm { i n } }$ $2 . 2 \mathrm { k W }$ 。开关频率： $f _ { \mathrm { s } } { = } 4 0 \mathrm { k H z }$ 。

# 3.1.2电感量的计算

（1）计算最大峰值线电流 $I _ { \mathrm { p k } }$ 。

$$
I _ { \mathrm { p k } } = { \frac { \sqrt { 2 } P _ { \mathrm { i n } } } { U _ { \mathrm { i } } } } = { \frac { \sqrt { 2 } } { 2 2 0 } } \times 2 2 0 0 { \mathrm { A } } \approx 1 4 . 1 4 { \mathrm { A } }
$$

(2）电感上的纹波电流 $\Delta I$ (纹波电流系数为0.2)。

$$
{ \Delta I = 0 . 2 I _ { \mathrm { p k } } = 0 . 2 \times 1 4 . 1 4 \mathrm { A } = 2 . 8 \mathrm { A } }
$$

(3）计算输入电压峰值的占空比 $D$ 。

$$
D = \frac { ( U _ { \mathrm { _ o } } - U _ { \mathrm { i n } } ) } { U _ { \mathrm { _ o } } } = \frac { 3 8 0 - 3 1 1 . 1 } { 3 8 0 } = 0 . 1 8
$$

此处， $U _ { \mathrm { i n } }$ 为额定输入电压的峰值， $U _ { \mathrm { i n } } = 2 2 0 \times$ ${ \sqrt { 2 } } \approx 3 1 1 . 1 \mathrm { { V } } .$ 。

(4）电感量计算。

$$
L = { \frac { U _ { \mathrm { i n } } D } { f _ { \mathrm { s } } \Delta I } } = { \frac { { \sqrt { 2 } } \times 2 2 0 \times 0 . 1 8 } { 4 0 0 0 0 \times 2 . 8 } } \mathrm { H } \approx 5 \times 1 0 ^ { - 4 } \mathrm { H }
$$

式中， $f _ { \mathrm { s } }$ 为开关频率。

因此，由式（11）～式（13）可知，当电流纹波系数控制在0.2时，电感值取 $5 0 0 ~ \mu \mathrm { ~ H ~ }$ 较为合适。

# 3.2磁性材料的选择

在磁器件的研究中，磁性材料的选择是至关重要的一部分，根据矫顽力的不同，磁性物质可以由软磁材料和永磁材料组成。本文最初选取了六种材料进行对比，综合表1中6种材料的特性，选择了成本低、损耗小的由青岛云路先进材料公司生产的雾化铁硅铝。

对于绕组线型的选择，本文选择了漆包扁铜线。

表1磁性材料特性对比  
Tab.1 Comparison of magnetic material properties   

<html><body><table><tr><td>特性</td><td>气雾化铁硅铝</td><td>非晶磁粉心</td><td>高磁通粉心</td><td>铁镍钼粉心</td><td>破碎铁硅铝粉心</td><td>铁硅粉心</td></tr><tr><td>成分组成</td><td>Fe-Si-Al</td><td>Fe-Si-B</td><td>Fe-Ni</td><td>Fe-Ni-Mo</td><td>Fe-Si-Al</td><td>Fe-Si</td></tr><tr><td>居里温度/℃</td><td>600</td><td>415</td><td>500</td><td>400</td><td>600</td><td>700</td></tr><tr><td>Bs/Gs</td><td>10500</td><td>15 600</td><td>17 000</td><td>7500</td><td>10 500</td><td>18100</td></tr><tr><td>损耗(mW/cm)(100kHz，0.1T)</td><td>320</td><td>750</td><td>450</td><td>450</td><td>650</td><td>1500</td></tr><tr><td>%Ldc @100 0e(60u)(%)</td><td>56</td><td>68</td><td>77</td><td>53</td><td>48</td><td>74</td></tr><tr><td>相对成本</td><td>低</td><td>中</td><td>高</td><td>高</td><td>低</td><td>低</td></tr></table></body></html>

与传统的铜线相比，在电气特性相同的情况下，扁铜线能够实现机器自动绕线，省掉了人工绕线的时间。

# 3.3电磁热耦合场建模

本文利用电磁热场仿真软件，运用有限元法，针对PFC电感进行了磁场瞬态分析及瞬态热场温度分布分析。利用仿真软件，首先进行磁场分析，获得了铁损耗曲线与铜损耗曲线，以此作为热分析模块的热源，这种方法称为载荷传递法。在对不同的场进行分析时，其中一个场的分析结果可以被视作载荷施加在其他的场中，使得这两个场得到耦合[。

耦合分析流程图如图2所示。

首先输入磁心、绕组等材料的参数与属性，加载电流密度，依据式（2）～式（4）进行电磁场计算、分析，得到温度场所需要加载的热源，即热生成率 $P$ ，之后开始进行温度场的分析，这个过程依据由式（5）和式（6）提供[8]。

# 4PFC电感仿真分析及优化设计

在电感的设计优化过程中，需要将多种参数列入考量范围，其中包括设计参数和工艺参数，设计参数主要包括电感的体积与形状，线圈匝数与形状等，而工艺参数则包括衬底电阻率、金属厚度等，因工艺参数不可随意改变，所以本文主要对较为容易改变的设计参数进行PFC 电感的优化[]。

![](images/ceccd7cb1d23f45566538cd7cf1f9a30f29be60aaa45fb4aeb1f122a7b745203.jpg)  
图2耦合分析流程图

经理论分析计算，PFC电感的损耗与其铁心尺寸、绕组匝数密切相关。而根据“热路”欧姆定律

$$
\Delta T = R _ { \mathrm { t h } } P
$$

式中， $R _ { \mathrm { t h } }$ 为电感表面到外部环境的外热阻（W/℃），温升又与损耗有着直接关系。

表2为四种方案中电感磁心的规格，其中方案一为企业最初设计的PFC电感方案，其在实验过程中存在温升过高的问题。而温升过高会导致PFC电感的饱和磁感应强度下降，影响电感的正常充放电过程，并且温升过高所带来的直接问题是造成局部过热，加速老化，增加损耗，影响系统效率。本文在方案一的基础上，在保证不改变初始电感量并且符合电感在实际电路中的设计要求的前提下，通过改变磁心尺寸和线圈匝数，又设计了三种规格的电感方案来进行比较。

表2四种方案电感磁心规格  
Tab.2 Inductance core specification for four schemes   

<html><body><table><tr><td></td><td>a/mm</td><td>b/mm</td><td>c/mm</td><td>d/mm</td></tr><tr><td>方案一</td><td>42</td><td>43</td><td>18</td><td>16</td></tr><tr><td>方案二</td><td>36.6</td><td>61.6</td><td>39</td><td>14.4</td></tr><tr><td>方案三</td><td>42</td><td>50</td><td>24</td><td>16.5</td></tr><tr><td>方案四</td><td>42</td><td>46</td><td>20</td><td>16.5</td></tr></table></body></html>

在磁场仿真时，磁心采用前文提到的雾化铁硅铝。在仿真软件里搭建起PFC电感三维非线性数学模型。为了使实验结果更加接近于现实环境条件下的结果，对电感的实际尺寸创建模型。电感磁心主视图、剖面图如图3所示。

![](images/0746fa62e8db1bc52e253d4c312757876767fad129674e4b3db34d1a11988ec4.jpg)  
图3PFC电感磁心剖面图  
Fig.3PFC inductance core profile

在四种方案中，方案一绕组为 $0 . 4 \times 4$ 漆包扁铜线36圈 $\times 2$ 串联；方案二绕组为 $0 . 4 \times 4$ 漆包扁铜线45圈 $\times 2$ 串联；方案三和方案四绕组为 $0 . 4 \times 4$ 漆包扁铜线50圈 $\times 2$ 串联。

由于无法直接在仿真软件中加入实际电流波形，所以对电流波形进行采样，取100个时间点进行仿真，当时间为 $0 . 0 0 5 \ 0 0 6 \mathrm { s }$ ，step为50时，电流值取到最大[10]。仿真得到的电流波形如图4所示。

![](images/279dd3fc9277a0211b7d566913537de295d9f0ad38be87aef6bd7ea62b47f2ac.jpg)  
Fig.2The flow chart of the magnetic-thermal coupling analysis   
图4选取100个点的电流波形  
Fig.4Selected current waveforms of 100 points

# 4.1四种方案的PFC电感磁感应强度模拟

经仿真，四种方案的PFC电感磁感应强度分布云图分别如图5～图8所示。

从图5～图8可以看到，由于四种方案PFC电感磁心的几何尺寸不尽相同，使得其磁阻不同，开口气隙处的截面积不同，从而导致其磁感应强度分布值不尽相同，从图中可以看出，四种方案PFC电感的磁感应强度上下对称，且电感绕组处的磁心的磁感应强度更强一些，方案一电感的磁感应强度分布在 $7 . 7 \times 1 0 ^ { - 5 } \sim 8 . 5 \times 1 0 ^ { - 3 } \mathrm { T }$ ，方案二电感的磁感应强度分布在 $1 . 0 \times 1 0 ^ { - 3 } \sim 7 . 4 \times 1 0 ^ { - 3 } \mathrm { T }$ ，方案三电感的磁感应强度分布在 $7 . 5 \times 1 0 ^ { - 5 } \sim 5 . 1 \times 1 0 ^ { - 3 } \mathrm { T }$ ，方案四电感的磁感应强度分布在 $2 . 0 \times 1 0 ^ { - 4 } \sim 5 . 1 \times 1 0 ^ { - 4 } \mathrm { T } _ { \circ }$ 可以看出，方案四的磁感应强度要明显小于其他方案的磁感应强度，因此，方案四的电感结构更不容易达到饱和的状态，也可以间接反映出方案四相比于前三种方案局部过热的情况得到了改善，使得系统更加可靠[11]

![](images/fe44a92449b9c03c746188c8c36692244cfd747a17bf96339fb3c56722f0cc29.jpg)  
图5方案一PFC 电感磁感应强度分布云图Fig.5Scheme 1 PFC magnetic induction intensitydistribution nephogram

![](images/ca10565c8fdd4b42b43c7d7a0f1479256684f7c35f6d3d593d6ac28c6884d828.jpg)

![](images/d40489ab7822a8262c094f59f7f9a46e048f027a20b27d6029e4f58973fe44e2.jpg)  
图6方案二PFC电感磁感应强度分布云图Fig.6Scheme 2 PFC magnetic induction intensitydistribution nephogram

![](images/cca22cd34bda84d06c2b9463356bb792ddee2032ed1efad29227f36ef3c88347.jpg)  
图8方案四PFC电感磁感应强度分布云图 Fig.8Scheme 4PFC magnetic induction intensity distribution nephogram

# 4.2四种方案的PFC电感温度分布模拟

经仿真，四种方案的PFC电感温度分布云图分别如图9～图12所示。

![](images/2054ec773773aa7a88559ee3eb5a35569af805700ec418283bafa4b15d640fba.jpg)  
图9方案一PFC电感温度分布云图

![](images/9a55f0bd07554075940be780212665b1c9d4e4604da34c6fec94d66f95fcd18a.jpg)  
图7方案三PFC电感磁感应强度分布云图 Fig.7Scheme 3 PFC magnetic induction intensity distribution nephogram   
Fig.9Scheme 1 PFC inductance temperature distribution nephogram   
图10方案二PFC电感温度分布云图  
Fig.10Scheme 2 PFC inductance temperature distribution nephogram

由图 $9 \sim$ 图12可以看出，方案一～四的温度分布大致相似，方案一电感温度分布在 $9 6 . 7 \sim 9 9 . 7 \mathrm { { \stackrel { \circ } { C } } }$ ，方案二电感温度分布在 $1 1 3 . 5 \sim 1 1 4 . 6 \mathrm { ^ c C }$ ，方案三电感温度分布在 $8 5 . 7 \sim 8 6 . 9 \mathrm { ^ \circ C }$ ，方案四电感温度分布$8 3 . 5 \sim 8 4 . 5 \mathrm { ^ c }$ 。因此方案四最高温度最低，且温度梯度分布比其他三种方案有显著的降低。由此可知，方案四设计的电感结构有效降低PFC电感的温升。

![](images/4ef28d475e7e62577056c4a0127f7fefbb85b51cd89216886be69e91ac8fe5ce.jpg)  
图11方案三PFC 电感温度分布云图Fig.11Scheme 3 PFC inductance temperaturedistribution nephogram

![](images/d3ccf23b2b724c28e922d7f86cb0a9a3d7cc430ef0b3c52c69a772bb95650f41.jpg)  
图12方案四PFC电感温度分布云图Fig.12Scheme 4 PFC inductance temperaturedistribution nephogram

# 4.3PFC电感损耗

从以上对PFC电感的磁场仿真以及温度场仿真可知，方案四所设计的电感结构可以有效降低温升，提高系统的效率。本文还具体分析计算了四种电感结构铁损和铜损的具体数值。以便更直观清晰地比较四种结构的损耗和温升，四种方案一个周期内铜损曲线如图13～图16所示。

由图13可以看出方案一铜损最大值为 $6 . 6 8 \mathrm { W }$ 根据磁场仿真结果选取step35-step65，在 $4 0 \mathrm { k H z }$ 进行铁损计算，铁损为1.9W。

同样的，也对方案二、三、四的铜损和铁损进行了仿真、分析和计算。

经过仿真分析及与方案一求解过程相同的计算，可以分别得到四种方案的铜损、铁损和温升数据，结果见表3。

![](images/9aed351bb6c0500e6884248433c411ce8a561711b5a864aad51db3b857669525.jpg)  
图13方案一PFC电感一个周期内铜损

![](images/577ebc9b093be3a1c9226c8e5cf0d380ed15a48fc0e986056f2442e23d58bdf3.jpg)  
Fig.13Scheme 1 PFC inductance copper loss in one cycle   
图14方案二PFC电感一个周期内铜损

![](images/00c4bd27574cd4c9dfffe6301be16ad6b49aa834744f9337250afb5e3fd8ee71.jpg)  
图15方案三PFC电感一个周期内铜损

![](images/87c4eab97ff228b276761569b06095613f55f6421764c7a9344f3a36f222c3e4.jpg)  
Fig.14Scheme 2 PFC inductance copper loss in one cycle   
Fig.15Scheme 3 PFC inductance copper loss in one cycle   
图16方案四PFC电感一个周期内铜损  
Fig.16Scheme 4 PFC inductance copper loss in one cycle

# 表3四种方案比较

Tab.3 Comparison of four schemes   

<html><body><table><tr><td></td><td>最高温度/C</td><td>室温/℃</td><td>铜损/W</td><td>铁损/W</td></tr><tr><td>方案一</td><td>99.7</td><td>21.6</td><td>6.68</td><td>1.9</td></tr><tr><td>方案二</td><td>114.6</td><td>21.6</td><td>8.40</td><td>3.2</td></tr><tr><td>方案三</td><td>86.9</td><td>21.6</td><td>6.58</td><td>1.7</td></tr><tr><td>方案四</td><td>84.5</td><td>21.6</td><td>6.58</td><td>1.9</td></tr></table></body></html>

从表3可以看出，温升从小到大排序：方案四$<$ 方案三 $<$ 方案一 $<$ 方案二，铁损与铜损之和从小到大排序：方案三 $<$ 方案四 $<$ 方案一<方案二，因此方案三和方案四优于方案一和方案二，并且通过对图 $5 \sim$ 图12的分析，在方案三和方案四的比较中，两种方案电感损耗非常接近，但是由于两种方案磁路结构的不同，方案三电感最高温度和温度梯度分部均高于方案四，即方案三电感整体发热情况高于方案四，且最高温度过高会出现局部过热问题，因此方案四为最优方案。

# 4.4试验验证

图17为青岛云路公司制造的实际电感模型，在环境温度 $2 1 ^ { \circ } \mathrm { C }$ 下，经测试，第一种方案线圈最高点温度是 $1 0 1 ^ { \circ } \mathrm { C }$ ，第二种方案线圈最高点温度为$1 1 8 ^ { \circ } \mathrm { C }$ ，第三种方案线圈最高点温度是 $9 4 ^ { \circ } \mathrm { C }$ ，第四种方案线圈最高点温度是 $9 2 ^ { \circ } \mathrm { C }$ ，由此可见，实际测试与仿真的趋势性大体相同，方案四温升最低。

![](images/1ee491f9339464d544466aa2b2590b8c8acb19e6807065b33eb424aa57b49be4.jpg)  
图17实际电感模型 Fig.17 Actual inductance model

# 5 结论

通过对四种PFC电感方案的电磁热场模拟对比分析可知，方案四的磁感应强度要低于其他方案，所以方案四相比于其他三种方案相对不容易达到饱和状态，同时，方案四在仿真中最高温度最低，铜损和铁损也较小，并且通过实验得到了验证，在初

始电感量保持不变的前提下，方案四的设计方案相较于传统方案成本增加不大，但是铁心损耗相对较小，温升情况得到了显著的优化。因此方案四的电感方案可以有效降低损耗、减少温升，从而避免了局部过热，提高了系统整体效率，可以作为企业进行大批量生产的理论依据。

# 参考文献

[1] Sahid M R,Azli N A,Muhamad N D. Study on the performance of the boost power factor correction(PFC)circuit with variable inductor current sense resistor values[C]. Power Electronics and Drive Systems of the Fifth International, 2003.   
[2] 江明，邵革良．变频空调用混合磁路PFC 电感设 计[C]．第三届国际制冷技术交流会，珠海，2014.   
[3] Zhigang Dang,Jaber A,Abu Qahouq. On-chip coupled power inductor for switching power converters[C]. Twenty-Ninth Annual IEEE DaFort Worth Applied Power Electronics Conference and Exposition, TX, USA, 2014.   
[4] 曾敏，姜立新，江伟．变频空调中功率因数校正电 感的设计[J]．华南理工大学学报，2006，34(11)： 20-24. Zeng Min, Jiang Lixin, Jiang Wei. Design of PFC inductor in variable frequency air conditioner[J]. Journal of South China University of Technology, 2006,34(11): 20-24.   
[5] 孙超，王春芳，郑建芬，等．大功率LLC谐振变 换器中谐振电感的优化研究[J]．大功率变流技术, 2015，16(4): 80-84. Sun Chao,Wang Chunfang, Zheng Jianfeng,et al. Optimization research on resonant inductor in high power LLC resonant converter[J]. High Power Converter Technology,2015,16(4): 80-84.   
[6] Leonavicius V, Dufly M, Boeke U, et a1. Comparison of realization techniques for PFC inductor operating in dis-continuous conduction mode[J]. IEEE Transactions on Power Electronics,2004,19(3): 531-541.   
[7] 林抒毅，许志红．交流电磁阀三维温度特性仿真分 析[J]．中国电机工程学报，2012，32(36)：156- 164. Lin Shuyi, Xu Zhihong. Simulation and analysis on the three-dimensional temperature field of AC solenoid valves[J]. Proceedings of the CSEE,2012, 32(36):156-164.   
[8] Biro O,Preis K.On the use of the magnetic vector potential in the finite-element analysis of 3-D eddy current[J]. IEEE Transaction on Magnetics,1989, 25(4): 3154-3159.   
[9] 张跃鲤，张文俊．硅集成电感元件的分析、设计 与优化[J]．半导体学报，2005，26(S1)：268- 272. Zhang Yueli, Zhang Wenjun.Analysis,design,and optimizationof Si inductors[J]. Chinese Journal Of Semiconductors,2005,26(S1):268-272.   
[10] 魏芝浩，王春芳，李震，等．动态非线性负载用 单管逆变ICPT系统参数优化[J]．电气工程学报，

2017，12(8):21-27. Wei Zhihao,Wang Chunfang,Li Zhen,et al.The parametre optimization of single switch inverter ICPT system for dynamic nonlinear load[J]. Journal of electrical engineering,2017,12(8): 21-27. [11] 陈为，毛行奎，罗恒廉，等．高频电感器线圈损 耗分析与交错气隙布置[J]．电工技术学报，2003, 18(6): 73-76. Chen Wei,Mao Xingkui,Luo Henglian,et al. Winding loss analysis and staggered air-gap arrangement for high-frequency inductors[J]. Transactions of China Electrotechnical Society, 2003,18(6): 73-76.