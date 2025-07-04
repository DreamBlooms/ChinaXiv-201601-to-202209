# 变频柜在风电机组塔底工作的散热研究

陈　明　陈永军　李力森（华锐风电科技（集团）股份有限公司北京 100086)

![](images/8e0f7eb19a3903eb866889a8b0e2293764d50ae1f3a763e7ec216ee81e46d43d.jpg)

陈明男1984年生，硕士，高级工程师，从事风力发电机组部件设计研发工作。

摘要：针对目前风电行业中较常见的变频柜等电气元件下置的方案，进行了优势分析和缺点比较。以质量、动量和能量守恒定律以及标准湍流模型为建模理论基础，通过CFD流体软件的计算，对塔筒底部变频柜工作环境的速度场和温度场进行了数值分析。通过分析结果可以得出，加装了轴流风机进行强制通风换热的塔筒底部空间的温度环境能够满足变频柜等各个电气部件正常工作的要求，同时，结合结构设计和布局中的不合理之处，提出建议改进。本文提出的塔底空间风冷散热方案的计算，不仅对风电机组结构布局的合理性有着重要意义，对风电机组机舱内及各个散热部件的计算也具有一定的借鉴价值。

关键词：塔筒底部 风电机组 变频柜 温度场中图分类号：TM614

# Study of Heat Dissipation of Frequency Converter of Wind Turbine Tower Bottom

![](images/502b319aa6393a82792feffe6e90fe04551a829893b68c627a6d809cfd585c85.jpg)

Chen Ming Chen Yongjun Li Lisen （Sinovel Wind Group Co.,Ltd. Beijing100086 China )

陈永军男1979年生，硕士，中级工程师，从事风力发电机塔筒设计研发工作。

Abstract: For the current wind power industry, the more common converter cabinet and other electrical components under the program,the advantages of analysis and comparison of shortcomings. Based on the law of mass, momentum and energy conservation and the standard turbulence model, the velocity field and temperature field of the working environment of the converter cabinet at the bottom of the tower are analyzed by CFD fluid software.Through the analysis of the results can be obtained, the installation of axial fan for forced ventilation heat transfer tower bottom space temperature environment to meet the frequency cabinet and other electrical components of the normal work requirements,combined with structural design and layout of the unreasonable To make suggestions for improvement.The calculation of air cooling and cooling scheme in the bottom of the tower is not only important for the rationality of the wind turbine structure,but also has some reference value for the calculation of the heat dissipation parts in the engine room.

Keywords: Tower bottom, wind turbine, frequency converter, temperature field

# 1 前言

随着风电机组单机容量持续增大，高海拔及海上风电机组的出现，风电机组运行过程中电气元件温度过高的问题越来越突出，风电机组因高温停机或限功率运行的情况时有发生[1]。风电机组额定功率增大，大功率电气元件运行时会产生大量的热量，尤其是变频器，运行时发热量高达几十千瓦以上。这些电气元件所在位置环境温度的稳定对机组运行至关重要[2]。电气元件的散热问题不仅会影响到电气部件及其相邻机械部件的稳定性和使用寿命，甚至会直接影响到风电机组的发电效率和经济效益。因此，对变频柜等电气元件所处环境通风散热问题的研究也就显得越来越重要。

# 2 变频柜等电气元件下置的优势

随着目前大功率机组和低风速机组的不断安装运行，塔筒的直径和高度也都在不断加大，使得塔筒底部空间直径一般都大于 $5 \mathrm { m }$ 。空间的不断加大，给变频器等电气元件下置安装带来了可操作性，在不另外增加土地使用面积和地面建筑的前提下，变频柜下置成为了众多风电厂商的研究重点。变频柜、辅助变压器和塔基控制柜等电气部件的下置有着明显的经济和技术优势，具体如下。

(1）便于电气部件的维护和更换。电气部件尤其是变频柜里的部件，需要定期的维护和更换，部件发生故障的频率也比较高。把变频柜放置于塔筒内部的最底端，维护时不但可以节省大量的人力、物力和时间成本，空间位置上也更便于工作操作，提高工作效率。快速安全的电气部件维护，也可以有效提高风电机组的可利用小时数，增加业主的售电收入。

（2）有利于提高机组的安全性。电气部件下置后，可以优化机舱内的结构空间，减少机舱整机的重量和体积，有效减少偏航轴承、塔筒法兰等重要部件的载荷，进而提高风电机组整体的安全性能。

(3）有利于提高机组的经济性。除了后期维护费用的显著减少外，部分电气部件的下置，也有利于机组的设计成本下降。减少机舱的重量和体积，减轻塔筒的用钢量，优化线路线缆的线路设计等措施都可显著提高机组的经济性，降低机组的发电成本，使得机组在市场上更具有竞争力。

（4）防火能力增强。风电机组机舱的防火重点在于预防，几乎不研究扑救措施。风电机组都是高空运行，人员上机扑救火情具有极大的伤亡风险。发生严重火灾后，目前尚没有任何有效的扑救措施，只能等机组自然燃烧后再进行处理，火警专业人士到场后多是着重于防患二次火灾或者人员伤害，不会采取风电机组的灭火措施。电气部件下置后，即使这些部件发生火灾也不会殃及到整个机组，而且火灾发生后也能采取积极的措施及时进行扑救，减少不必要的损失。

当然，电气部件下置后也会有新的问题需要解决。塔筒底部入口处的人员安全防护、空间设计优化等问题，不解决好会造成新的技术和维护问题。尤其是塔筒底部的通风散热方案的研究，对塔筒电气部件的稳定安全运行至关重要，有必要进行细致的研究分析。

# 3塔底主要散热方式介绍

将变频柜等电气元件放置于塔筒底部是各大风电公司研究和实践的主要方向。相关研究文献表明，只利用塔筒的烟筒效应散热，塔筒内的空气会产生温升效应，不能满足电气元件的工作要求。现有的塔筒冷却方式主要有以下几种：一种是在塔筒壁上开孔，利用水冷冷却器对塔筒内外的空气进行热交换，该方案成本高且耗费工时多；一种是单纯依靠热空气的烟囱效应及塔筒壁来散热，该方案因为塔筒壁的热交换能力有限，在环境温度较高时会造成局部过热，直接影响到电气部件的稳定运行；还有一种就是目前各大风电厂商研究较多的形式，即在塔筒上开通风孔，安装轴流风机通风与塔筒外进行换热，必要时可以同时安装进风和出风风机，塔筒壁自然散热和使用烟筒效应都属于辅助散热方式。使用这种散热方式，需计算轴流风机的换热能力是否满足变流器等电气部件的散热需求[3]。

使用第三种方式时，技术人员一般使用工程算法对轴流风机的功率和塔筒内的散热情况进行估算，容易造成与实际情况偏离的计算结果，而方案一旦实施了如需改造费用就会增加很多，所以有必要使用严谨的传热公式进行计算，同时结合CFD仿真，对变流器所处的塔底空间进行散热计算，以确定塔筒内的空气流量和结构设计是否能满足变流器的散热需求，由此确定具体的通风冷却方案[4]。

# 4 机舱散热建模

# 4.1塔筒计算的守恒定律

塔筒内安装强制通风系统，由自然进风口和排风口形成塔筒与外部气体环境的热交换系统。塔筒内气体假定为不可压缩气体，在恒定功率轴流风机的作用下定常流动，遵守质量、动量和能量守恒定律。用整体求解方法计算塔筒底部空间内气体流动和温度场分布。设舱内气体在 $x$ 、 $y$ 和 $z$ 方向上的速度分量分别为 $u$ ， $\mathbf { \Phi } _ { \nu }$ 和 $w$ ，气体压力为 $p$ ，气体比热容为 $C _ { \mathfrak { p } }$ ，气体传热系数为 $k$ ，气体瞬时温度为 $T$ 则舱内气流的统一控制方程描述如下

（1）塔底内气体不可压缩，满足流体连续性方程

$$
\frac { \partial u } { \partial x } + \frac { \partial v } { \partial y } + \frac { \partial w } { \partial z } = 0
$$

(2）塔底内气体在各个速度方向上的分量满足动量守恒方程

$$
\rho \left( { \frac { \partial u u } { \partial x } } + { \frac { \partial u v } { \partial y } } + { \frac { \partial u w } { \partial z } } \right) = - { \frac { \partial p } { \partial x } } + \mu \left( { \frac { \partial ^ { 2 } u } { \partial x ^ { 2 } } } + { \frac { \partial ^ { 2 } u } { \partial y ^ { 2 } } } + { \frac { \partial ^ { 2 } u } { \partial z ^ { 2 } } } \right)
$$

$$
\rho \left( { \frac { \partial u w } { \partial x } } + { \frac { \partial w } { \partial y } } + { \frac { \partial w v } { \partial z } } \right) = - { \frac { \partial p } { \partial y } } + \mu \left( { \frac { \partial ^ { 2 } v } { \partial x ^ { 2 } } } + { \frac { \partial ^ { 2 } v } { \partial y ^ { 2 } } } + { \frac { \partial ^ { 2 } v } { \partial z ^ { 2 } } } \right)
$$

$$
\rho \left( \frac { \partial u w } { \partial x } + \frac { \partial v w } { \partial y } + \frac { \partial w w } { \partial z } \right) = - \frac { \partial p } { \partial z } + \mu \left( \frac { \partial ^ { 2 } w } { \partial x ^ { 2 } } + \frac { \partial ^ { 2 } w } { \partial y ^ { 2 } } + \frac { \partial ^ { 2 } w } { \partial z ^ { 2 } } \right) ( \rho - 1 ) \mathrm { ~ d ~ } z
$$

(3）不考虑塔底内气体的粘性耗散，满足能量 守恒方程

$$
\rho \left( { \frac { \partial u T } { \partial x } } + { \frac { \partial u T } { \partial y } } + { \frac { \partial u T } { \partial z } } \right) = { \frac { k } { c _ { _ \mathrm { p } } } } \left[ { \frac { \partial } { \partial x } } \left( { \frac { \partial T } { \partial x } } \right) + { \frac { \partial } { \partial y } } \left( { \frac { \partial T } { \partial y } } \right) + { \frac { \partial } { \partial z } } \left( { \frac { \partial T } { \partial z } } \right) \right]
$$

# 4.2塔底内气体的湍流模型

塔筒底部空间内气体在轴流风机作用下以一定流速定常流动，因此其雷诺数较大。因塔筒底部空间内安装有变频柜，辅助变压器，塔基控制柜等电气部件，空间内气体受其复杂布局结构的影响，气流组织形态呈现复杂湍流。为描述空间内气体湍流状态，采用Launder和Spalding提出的 $k { - } \varepsilon$ 湍流模型。 $k { - } \varepsilon$ 湍流模型是简单而标准的湍流模型，可有效解决高雷诺数的流体湍流问题。 $k { - } \varepsilon$ 湍流模型方程为

$$
\begin{array} { c } { { \displaystyle \frac { \partial } { \partial t } ( p k ) + \frac { \partial } { \partial x _ { _ { 1 } } } ( p k u _ { _ { 1 } } ) } } \\ { { { } } } \\ { { = \displaystyle \frac { \partial } { \partial x _ { _ { 3 } } } \Biggl [ \Biggl ( \left( \frac { \mu } { \sigma _ { _ { k } } } \frac { \mu _ { _ { k } } } { \sigma _ { _ { k } } } \right) \frac { \partial k } { \partial x _ { _ { j } } } \Biggr ] + G _ { _ { \mathrm { { k } } } } + G _ { _ { \mathrm { { b } } } } + \rho \varepsilon - Y _ { _ { \mathrm { { M } } } } + S _ { _ { \mathrm { { k } } } } } } \\ { { { } \displaystyle \frac { \partial } { \partial t } ( p \varepsilon ) + \frac { \partial } { \partial x _ { _ { 1 } } } ( p \varepsilon u _ { _ { 1 } } ) } } \\ { { { } = \displaystyle \frac { \partial } { \partial x _ { _ { 3 } } } \Biggl [ \Biggl ( \mu + \frac { \mu _ { _ { t } } } { \sigma _ { _ { c } } } \Biggr ) \frac { \partial \varepsilon } { \partial x _ { _ { j } } } \Biggr ] + G _ { _ { \mathrm { { l } } \varepsilon } } \frac { \varepsilon } { k } ( G _ { _ { k } } + G _ { _ { 3 } \varepsilon } ) G _ { _ { \mathrm { { b } } } } - G _ { _ { 2 \varepsilon } } \frac { \varepsilon ^ { 2 } } { k } + S } } \end{array}
$$

式中， $G _ { \mathrm { k } }$ 为气体层流速度梯度产生的湍流动能； $G _ { \mathrm { b } }$ 为由浮力产生的湍流动； $Y _ { \mathrm { M } }$ 为在可压缩湍流中过渡的扩散产生的波动，由于塔底气体不可压缩，故可忽略不计； $S _ { \mathrm { k } }$ 和 $S _ { \varepsilon }$ 为用户定义的源项，通常也可忽略不计； $\sigma _ { \mathrm { k } }$ 和 $\sigma _ { \mathrm { { s } } }$ 分别为 $k$ 方程和 $\boldsymbol { \varepsilon }$ 方程的湍流普朗特数。

$$
\sigma = \frac { \mu C _ { \mathrm { p } } } { k }
$$

式中， $C _ { \mathfrak { p } }$ 为舱内气体的比热容； $\mu$ 为粘度系数； $k$ 为热导率。据此，舱内气体的普朗特数 $\sigma _ { \mathrm { k } }$ 和 $\sigma _ { \mathrm { { \varepsilon } } }$ 分别取1.0和1.3。

# 4.3塔底速度场和温度场计算的边界条件

因本计算主要分析轴流风机对气体流速和温度场的影响，因此忽略影响不大的塔筒烟筒效应和塔壁散热的能力，选取塔筒筒节的最下一节作为分析对象。计算模型如图1所示，主要包括塔筒门结构用于自然进风，轴流风机出口、变频柜、辅助变压器和塔基控制柜等电气部件。其中，变频柜有3个排风扇，会对塔底的空气流场造成较大的影响，因此在建模计算中必须体现出来[5]。

![](images/63d99a9d52fcd6fd1ff343faf366bf6cf346fbb2fa5a17f18170be7c9732f0ca.jpg)  
图1计算模型框线图  
Fig.1Frame line graphics of the model

根据风电行业的相关标准规定和轴流风机厂所给风机的具体参数，以及相关电气部件厂商所给的各个部件参数，同时结合部分风场的现场采集数据，设定塔底流场和温度场分析的具体边界条件见下表。

# 表塔底流场和温度场计算参数

Tab．Calculation parameters for tower bottom   

<html><body><table><tr><td></td><td>压力差/Pa</td><td>最大出风量/(m/h)</td><td>速度/(m/s)</td><td>散失系数</td><td>散热功率/(W/m)</td><td>导热系数/(W/m²·K)</td></tr><tr><td>变频柜内风扇1</td><td>793</td><td>6620</td><td>5.86</td><td>5.82</td><td>22 761</td><td>2267</td></tr><tr><td>变频柜内风扇 2</td><td>839</td><td>2200</td><td>2.54</td><td>6.49</td><td>7 639</td><td>1800</td></tr><tr><td>变频柜内风扇3</td><td>817</td><td>3827</td><td>4.11</td><td>6.18</td><td>12187</td><td>2016</td></tr><tr><td>出风口</td><td></td><td></td><td>11.9</td><td></td><td></td><td></td></tr><tr><td>辅助变压器</td><td></td><td></td><td></td><td></td><td>1166</td><td></td></tr><tr><td>塔基控制柜</td><td></td><td></td><td></td><td></td><td>890</td><td></td></tr></table></body></html>

散失系数为

$$
k _ { _ \mathrm { L } } = 7 . 0 - 0 . 2 \nu
$$

导热系数为

$$
h = 1 4 6 9 . 1 + 1 2 6 . 1 1 \nu + 1 . 7 3 \nu ^ { 2 }
$$

式中， $\nu$ 为速度。该两处计算公式均非标准计算公式，皆为推导拟合公式。

为保证模型的计算精度，初步建模完成后，对计算模型进行了网格无关性和步长独立性验证，同时为了保证计算网格的质量，计算模型使用了软件的网格自适性功能设置，使得网格在计算过程中能对模型的重要区域自动进行网格优化和加密处理，以保证最终模型的计算精度。

# 5 计算结果与分析讨论

变频柜内的3个散热风扇处于塔筒底部的计算空间中，会对塔底的速度场和温度场的计算造成较大的影响。变频柜的出风口边界条件即为塔底区域计算的内部边界条件，所以有必要对变频柜内部及出风口的速度场计算，以便对塔底的速度场和温度场计算时能够更好地设置边界条件，变频柜内速度场计算结果云图如图2所示。

由图可以看出，变频柜的5个进风口进风速度基本相同，但是3个出风口的出风速度相差较大，最大的速度相差将近两倍。如此大的速度流量差，必然会对塔筒内的气体流动造成较大的影响。出风口面的速度分布相对较为均匀，所以塔底计算时该处边界条件可以简化为整个平面速度均匀通过。

![](images/84133ea4e974646d24fcda78ab82bb0b3fb491379c7fd33554cadb7015d64455.jpg)  
图2变频柜内部速度场三维云图  
Fig.2Velocity contour of the frequency converter interior

结合已有计算结果和供应商提供的各项参数，对塔筒底部空间进行速度场和温度场的计算，计算结果的速度场三维云图如图3和图4所示。

由计算结果可以看出，变频器的3个风扇对塔筒底部空间内的气体速度场有着较大影响，气体速度最大的区域便在该区域。通过塔筒门上的百叶窗进入塔底的气体，与变频器排出的气体，呈垂直角度混合方向略微出现偏转后，吹向塔筒壁面。然后气体方向呈现出螺旋向上的趋势，直至气体从塔底空间的上部轴流风机排风口处排出。塔底筒节内有两个分隔层，相邻分隔层之间只有入口处是相通的，由图可以看出，上层的气体流量较小，流体通过塔筒分隔层入口后，同样呈现为螺旋上升趋势。

可以看出，塔底空间内的速度场内没有出现较大的湍流区域，整体的流通效果尚可。由计算结果也可以看出，轴流风机的位置可以向下移动一下，以便能更快的排出塔底空间内过热的气体。塔底的温度场分布如图5所示。

![](images/cfd61535c704adbd04e07513bb7f5747b2c00419ccef8b4bff9bc433f306eed7.jpg)  
图3塔底速度场塔筒门处的三维云图 Fig.3Velocity contour of the tower door

![](images/80871cfa157be00ffa476c6b76bda2f1dc1f36ec805f2b7db7cd3bb4f93f3840.jpg)  
图4塔底速度场分析空间内的三维云图Fig.4Velocity contour of the simulation domain

由图可以看出，塔底空间内的温度场分布情况相对没有速度场分布那么明显，只有变频柜风扇出口处温度场的温度梯度相对大一些，但是温差也仅有几K。以塔筒所在位置为基点，温度相对较高的区域主要分布于两侧塔筒壁的区域，分隔层以下区域温度呈现为下低上高的趋势，符合进风口在下、出风口在上的结构设计和塔筒的烟筒效应。塔筒分隔层的上部区域相对于分隔层下部区域温度大$5 \sim 6 \mathrm { K }$ ，这是因为该分隔区域内有热源辅助变压器，但是却没有通风风机造成的，此处的通风散热结构也有进一步改进的空间。塔筒分隔层上部的区域，因为有人孔的通风效果，人孔附近温度较低，其他区域温度相对较高且分布均匀。鉴于图片不能表述具体的温度值，将塔筒侧、塔筒门对面以及左右两侧的筒壁温度值随着筒壁高度的变化做成对比曲线，如图6和图7所示。

![](images/8b7d0cf3d5dafebb91c0796ed9ac9c61242cba1cf37b2e43f3117eb24aeec8a6.jpg)  
图5塔底温度场不同角度的三维云图Fig.5Temperature contour of the tower bottom

![](images/b38ac0ae38de7be174a4224269ad603fc405e35096e1287c9290e47e13acc810.jpg)  
图6塔底温度场前后侧温度对比曲线

![](images/c30ba271c8a6b3c049fb6f8e285e7281eee71db98f1fe1e1ea8b9f1a33934c27.jpg)  
Fig.6Temperature comparison curves of tower bottom between front and rear   
图7塔底温度场左右侧温度对比曲线  
Fig.7Temperature comparison curves of tower bottom between left and right

由对比曲线图可以看出，受到塔筒门进风口以及变频柜散热风扇的影响，塔筒门侧的筒壁温度在$2 \mathrm { m }$ 以下的区域出现剧烈变换，随着高度升高至 $2 \mathrm { m }$ 以上时，温度曲线变得逐渐平稳。塔筒门对面以及左右两侧的温度则一直相对稳定，上下波动均不超1K。这种现象的分布形态和形成原因前文均已论述，此处不再重复。

总体来说，塔筒底部分隔板以下通风散热效果良好，整体比环境温度高 $1 6 \sim 1 8 \mathrm { K }$ ，其中环境温度设置为300K，电气部件的正常运行温度要求不高于$3 2 8 \mathrm { K }$ 。该环境温度下，变频柜等电气部件的运行温度满足风电行业相关标准和电气部件自身要求的温

度。如夏季遇极端高温天气，风电运维人员应注意增加塔筒底部空间的通风设施，以保证设备的安全稳定运行。塔筒底部分隔板以上区域，通风散热效果较差，需要适当增加散热措施或者调整结构布局改善散热效果。

本次分析结果与某国外变频器厂商的计算结果基本一致，但是与风场的实际测量值相比，计算得出的环境温度比风场测量环境温度值 (秋冬季数值)略高，初步分析可能是因为风场目前处于秋冬季节，较低的环境温度有利于塔筒筒壁散热，同时多风的气候条件也有利于塔筒筒壁的自然散热。另外，塔筒的烟筒效应也会对底部空间的散热造成一定的影响，这也说明计算模型及计算方法有待进一步的研究和改进。

# 6 结论

该计算模型以塔筒底部的散热分析计算实例阐述了模型建立的理论基础和建模分析方法，计算结果较为理想，国内一般风场的常温环境下塔筒内的温度环境都能满足电气部件的安全稳定运行。如遇极端高温天气，则需要暂时停机或者采取其他降温措施以保证整个风电机组的平稳运行。考虑到电气部件放置于塔筒底部的种种技术优势和经济成本的节省，在保证塔筒底部结构安全的情况下，适当增加塔底散热所需的成本，依然是各个风电机组的优先选择项。

本计算的计算理论和建模方法，对风电机组的机舱内通风散热计算分析、齿轮箱油温分析等具有一定的借鉴价值。风电行业的技术人士只有不断进行技术改进和方法创新，才能推动风电行业平稳健康发展。

# 参考文献

[1] 陈效国，刘衍选，蔡晓峰．关于风电机组塔底部分散热方案的探讨[J]．风能，2014(8)：100-103.  
[2] 胡青．风电变频器水冷系统的一种流量设计方案[J].水电与新能源，2012(4)：68-71.Hu Qing.A flow design plan of wind powerconverter water cooling system[J]. Hydropower andNew Energy, 2012(4): 68-71.  
[3] 董红云，王晓，宋建秀，等．风电机组塔筒通风散热计算[J]．科技展望，2016，26(17)：94-95.  
[4] 马铁强，孙德滨，苏阳阳，等．风力发电机组机舱结构散热性能分析方法[J]．计算机辅助工程,

2016，25(3):63-68，73. Ma Tieqiang,Sun Debin,Su Yangyang,et al. Analysis method on heat dissipating performance of nacellestructure of wind turbine generator system[J].Computer Aided Engineering,2016, 25(3): 63-68, 73. [5] 董红云，高首聪，宋建秀，等．风电机组塔筒内 大功率风冷变流器的散热研究[J]．大功率变流技

术，2017(1):50-54.Dong Hongyun,Gao Shoucong,Song Jianxiu, et al.Research on heat dissipation of high-power air-cooled converter in wind turbine tower[J].HighPower Converter Tenchnology,2017,(1):50-54.[6] 戴金水，吕敬，朱淼，等．大型海上风电场经VSC－HVDC并网的次同步振荡阻尼特性分析[J].电气应用，2016，35(8)：51-56.