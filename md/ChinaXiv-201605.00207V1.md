# 电磁波在大面积等离子体片中传播特性的分析

夏俊明 徐跃民 孙越强　霍文青　孙海龙　白伟华 柳聪亮　孟祥广

Analysis of propagation properties of electromagnetic waves through large planar plasma sheets Xia Jun-MingXu Yue-MinSun Yue-QiangHuo Wen-QingSun Hai-LongBai Wei-HuaLiu Cong-Liang Meng Xiang-Guang

引用信息 Citation: Acta Physica Sinica,64,194202 (2015) DOl: 10.7498/aps.64.194202   
在线阅读View online: http://dx.doi.org/10.7498/aps.64.194202   
当期内容View table of contents: http://wulixb.iphy.ac.cn/CN/Y2015/V64/I19

您可能感兴趣的其他文章Articles you may be interested in

阿基米德螺旋微纳结构中的表面等离激元聚焦Focusing surface plasmon polaritons in archimedes' spiral nanostructure物理学报.2015,64(19):194201 http://dx.doi.0rg/10.7498/aps.64.194201

用四台阶相位板产生涡旋光束 Generation of vortex beams by the four-step phase plates 物理学报.2015,64(18):184202 http://dx.doi.org/10.7498/aps.64.184202

（204号 $( 1 + 2 )$ 维各向同性介质中的旋转椭圆空间光孤子（20 $( 1 + 2 )$ dimensional spiraling elliptic spatial optical solitons in the media without anisotropy物理学报.2015,64(15):154202 http://dx.doi.0rg/10.7498/aps.64.154202

平面金属等离激元美特材料对光学Tamm态及相关激射行为的增强作用 Optical Tamm state and related lasing efect enhanced by planar plasmonic metamaterials 物理学报.2015,64(11):114202 http://dx.doi.0rg/10.7498/aps.64.114202

基于简单透镜列阵的可调焦激光均匀辐照光学系统研究 Study on a zooming optical system based on simple lens array used for laser uniform irradiation 物理学报.2015,64(5):054201 http://dx.doi.0rg/10.7498/aps.64.054201

# 电磁波在大面积等离子体片中传播特性的分析

夏俊明1)2)t 徐跃民1) 孙越强1) 霍文青1) 孙海龙1) 白伟华1) 柳聪亮1) 孟祥广1)

1)(中国科学院空间科学与应用研究中心,北京100190)2)(中国科学院大学,北京 100190)(2015年3月5日收到;2015年5月14日收到修改稿）

脉冲磁约束线形空心阴极放电形成的大面积等离子体片可应用于等离子体天线、隐身及模拟超音速飞行器表面的等离子体鞘套．本文首次利用实测等离子体片电子密度时空分布和横向场传播矩阵法，研究了电磁波在等离子体片中反射率、透射率、吸收率随频率及脉冲放电时间的变化特征.结果表明：极化方向平行磁场的电磁波，在小于截止频率的低频带内具有较高的反射率和吸收率,增大电流，反射率增加,吸收率下降，在大于截止频率的高频带内反射率和吸收率较低，增大电流，透射率下降，吸收率升高；极化方向垂直磁场的电磁波在高混杂谐振频率附近存在吸收率明显增强的吸收带，谐振吸收峰值与放电电流无关；脉冲放电期间，电磁波的反射率、透射率与吸收率由不稳定过渡到稳定的时间约为 $1 0 0 ~ \mu \mathrm { s }$ 。过渡时间随着放电电流的增加而增大，极化方向垂直磁场、小于截止频率的电磁波在稳定放电阶段谐振吸收较强.本文的研究成果对利用等离子体片实现对电磁波的稳定高反射作用具有重要意义，

关键词:线形空心阴极，磁化等离子体片，电子密度分布，横向场传播矩阵法

PACS: 42.25.Bs, 52.77.-j, 52.70.-m

DOI: 10.7498/aps.64.194202

# 1引言

脉冲磁约束线形空心阴极[1在增强型辉光放电模式[2下形成的等离子体片具有面积大、电子密度高、稳定性好的优点，其在微波领域具有重要的应用价值．20世纪90年代初，美国海军实验室(Naval Research Laboratory，NRL)Agile Mirror项目中，研究人员首次将这种大面积等离子体片代替金属面板应用于X波段微波波束切换[2-4]．1998年Manheimer等[5]对这种大面积等离子体片在新型微波器件中的应用进行了研究．2014年Gillman等[6利用这种大面积等离子体片模拟超音速飞行器表面的等离子体鞘套，对消减黑障的途径进行了实验探索．不同的微波应用领域对等离子体片的电磁特性需求不同，例如，当等离子体片应用于等离子体反射面天线时，需要其具有高的反射率、低的透射率、低的吸收率[4]；当等离子体片应用于隐身及模拟再入飞行器表面的等离子体鞘套时，需要其具有高的反射率、高的吸收率、低的透射率[7].Larigaldie等[8利用实测脉冲放电电流和理想的电子密度分布模型得到的等离子体片厚度向电子密度分布，通过数值计算研究极化方向平行磁场的电磁波透射信号的演化过程．Cheng等[9,10]和Ding等[11]通过实验，研究了极化方向平行磁场的C波段电磁波的吸收、反射、透射特性随脉冲放电电流和工作气压的变化规律．Huo等[12]通过实验,对极化方向垂直磁场的电磁波的吸收特性随磁场强度的变化规律进行了研究，

电磁波在大面积等离子体片中的传播特性受电磁波频率、极化方向及等离子体片自身特性等诸多因素的影响，Larigaldie等的数值计算方法由于对电子密度分布进行了假设而不够准确，而Cheng等和Ding等的实验由于受实验条件限制，只考虑了某一变量而没有对电磁波在等离子体片中的传播特性进行较全面地研究.本文利用电子密度时空分布诊断结果和数值分析相结合的方法，较准确、全面地研究了电磁波在等离子体片中传播时，电磁波极化方向、频率、脉冲放电电流和脉冲放电时间对电磁波反射率、透射率和吸收率的影响

# 2横向场传播矩阵法

传播矩阵法是一种分析非均匀媒介中电磁波传播特性的解析方法，Negi和Singh[13最早利用传播矩阵法(propagator matrix method,PMM)研究了球面分层媒介中的热传递过程，Rokhlin和Wang[14]首次将传播矩阵法扩展应用到分析分层各向异性媒介中波的传播过程．横向场传播矩阵法是一种利用场量切向分量连续性边界条件分析非均匀媒介中电磁波传播特性的解析方法，郑宏兴等[15]利用横向场传播矩阵法得到了分层各向异性介质的反射系数和透射系数的解析表达式，Yin等[16]利用横向场传播矩阵法计算了一个理想的非均匀磁化等离子体模型的电磁波反射系数、透射系数、吸收系数．本文首次利用实测等离子体片电子密度时空分布，采用横向场传播矩阵法,研究了电磁波在等离子体片中反射率、透射率、吸收率随频率及脉冲放电时间的变化特征.

# 2.1 磁化等离子体片分层模型

大面积等离子体片的产生和参数采集装置如图1所示．放电阴极为黄铜制作的线形凹槽状空心阴极，长度、宽度、深度分别为 $6 0 ~ \mathrm { c m }$ ， $1 . 6 \ \mathrm { c m }$ ，$1 . 2 ~ \mathrm { c m }$ ，阳极是由黄铜制作的金属圆板，其与阴极相对放置于圆柱形有机玻璃放电腔体中心，间距$6 0 ~ \mathrm { c m }$ ．与树脂玻璃放电腔体同轴放置一对亥姆霍兹线圈，加载直流电流后，其在放电腔体内产生均匀磁场用于约束等离子体成片状结构，磁场大小在0—350Gs ( $\mathrm { ~ 1 ~ G s = 1 0 ^ { - 4 } ~ T } )$ 内连续可调．脉冲电压源输出频率为 $5 0 ~ \mathrm { H z }$ 、脉宽 $2 0 0 ~ \mu \mathrm { s }$ 、电压值在0一 $6 ~ \mathrm { k V }$ 连续可调的放电脉冲,其经过一个 $9 0 ~ \Omega$ 的限流电阻 $R _ { 1 }$ 加载到阴阳电极两端，电路中并联一个 $2 0 0 0 \Omega$ 的电阻 $R _ { 2 }$ ，用于在放电结束后快速释放电极间储存的电能．输入输出比为 $1 ~ \mathrm { A } / 1 0 0 ~ \mathrm { m V }$ 的Pearson线圈用于测量等离子体放电电流，所测信号由示波器读取，示波器利用衰减后的脉冲电压源信号作为触发源．实验所用气体为氮气，纯度为$9 9 . 9 9 9 \%$ ，由气阀从树脂玻璃腔体顶部注入，气体流量计控制注气的快慢,放电过程中流量计与位于放电腔体底部的真空泵一同维持工作气压保持动态平衡．郎缪尔探针为半径 $0 . 2 ~ \mathrm { m m }$ ，长度 $4 ~ \mathrm { m m }$ 的钨圆柱体，由真空腔体顶部插入，用于诊断等离子体片的电子密度,其位置固定在竖直方向距离线形空心阴极 $3 0 \ \mathrm { c m }$ 、水平方向偏离等离子体面中心约$1 0 ~ \mathrm { c m }$ 的位置.

![](images/9b956017d1111cce31e48c455fb5f98b3d503987ec8529181c6cf30d0e62750a.jpg)  
图1大面积等离子体片的产生及参数采集装置

Fig.1.Experimental devicefor generating large planar plasma sheet and diagnosis of plasma parameters.

实验研究表明[17-22]，脉冲磁约束线形空心阴极放电形成的大面积等离子体片水平方向和竖直方向电子密度变化不大，在磁场小于200Gs时，厚度向电子密度关于厚度中心对称、峰值电子密度位于厚度中心并且厚度向电子密度分布可用高斯函数进行数值拟合，本文利用郎缪尔探针实测的厚度向 $3 \ \mathrm { c m }$ 的电子密度时空分布，经过数据处理后，将实验生成的等离子体片理想化为稳态、碰撞、无限大、厚度为 $3 \ \mathrm { c m }$ 的非均匀磁化等离子体片，按图2建立了等离子体片分层模型．图2中，以约束磁场 $B$ 的方向为 $x$ 轴正方向，以等离子体片法线为 $z$ 轴，指向左侧为 $z$ 轴正方向，建立直角坐标系，左侧空气与等离子体片的交界面为 $z = 0$ 平面，$z = z _ { 0 }$ ， $z _ { 1 }$ ， $z _ { 2 }$ ， $z _ { 3 }$ ，…， $z _ { n - 1 }$ ， $z _ { \mathrm { n } }$ 等 $n + 1$ 个面将厚度向非均匀的等离子体片划分为 $n$ 层近似均匀的小等离子体片并用序号 $1 , 2 , 3 , \cdots$ ， $n$ 表示，图中序号0和 $n + 1$ 表示空气层．平面电磁波从左侧空气层垂直入射，入射面为 $x o z$ 面，平面电磁波极化方向可沿平行磁场与垂直磁场两个方向进行分解，平行磁场方向(平行 $x$ 轴)的电波为横磁波(transversemagnetic waves,TM波)，垂直磁场方向(平行于 $y$ 轴)的电磁波为横电波(transverse electric waves,TE波).

![](images/bacc7195282f41837d7e1aafe53961bd0c889e822b072962b1ce255d5e5ecd1e.jpg)  
图2等离子体片分层模型  
Fig.2.The layered model of plasma sheet.

一般认为等离子体的磁导率和自由空间的磁导率 $\mu _ { 0 }$ 相同；每一片等离子体片的相对介电常数在一阶扰动近似下可用二阶张量形式表示为

$$
\begin{array} { r } { \frac { \omega _ { \mathrm { p } } ^ { 2 } } { \sigma ( \omega - \mathrm { i } \nu ) } \qquad 0 \qquad \ 0 } \\ { 0 \qquad 1 - \frac { \omega _ { \mathrm { p } } ^ { 2 } ( \omega - \mathrm { i } \nu ) } { \omega \left[ ( \omega - \mathrm { i } \nu ) ^ { 2 } - \omega _ { \mathrm { g } } ^ { 2 } \right] } \quad - \frac { \mathrm { i } \omega _ { \mathrm { p } } ^ { 2 } \omega _ { \mathrm { g } } } { \omega \left[ ( \omega - \mathrm { i } \nu ) ^ { 2 } - \omega _ { \mathrm { g } } ^ { 2 } \right] } \quad . } \\ { 0 \qquad \frac { \mathrm { i } \omega _ { \mathrm { p } } ^ { 2 } \omega _ { \mathrm { g } } } { \omega \left[ ( \omega - \mathrm { i } \nu ) ^ { 2 } - \omega _ { \mathrm { g } } ^ { 2 } \right] } \quad 1 - \frac { \omega _ { \mathrm { p } } ^ { 2 } ( \omega - \mathrm { i } \nu ) } { \omega \left[ ( \omega - \mathrm { i } \nu ) ^ { 2 } - \omega _ { \mathrm { g } } ^ { 2 } \right] } \quad } \end{array} .
$$

忽略离子的贡献后，上式中，ωp = V $\omega _ { \mathrm { p } } = { \sqrt { \frac { n _ { \mathrm { e } } q ^ { 2 } } { m _ { \mathrm { e } } \varepsilon _ { 0 } } } }$ 为等离子体中电子振荡圆频率,其中 $n _ { \mathrm { e } }$ ， $m _ { \mathrm { e } }$ ， $q$ 分别为电子密度、电子质量、电子电荷量, $\varepsilon _ { 0 }$ 为真空介电常数;$\omega$ 为入射波的角频率; $\nu = \frac { p _ { \mathrm { n } } } { k _ { \mathrm { B } } T _ { \mathrm { n } } } \sigma _ { \mathrm { e n } } \sqrt { \frac { 8 k _ { \mathrm { B } } T _ { \mathrm { e } } } { \pi m _ { \mathrm { e } } } }$ 8kBTe为电子与中性气体的碰撞频率 (忽略电子的其他碰撞),其中 $p _ { \mathrm { n } }$ ， $T _ { \mathrm { n } }$ 为中性气体的气压与温度(近似为常数$3 0 0 ~ \mathrm { K } \ '$ ),， $k _ { \mathrm { B } } T _ { \mathrm { e } }$ 为以 $\mathrm { e V }$ 单位的电子温度(实验诊断结果在1.5— $3 . 5 ~ \mathrm { e V }$ 间变化，计算时取常数 $2 . 5 ~ \mathrm { e V }$ ), $k _ { \mathrm { B } }$ 为玻尔兹曼常数, $\sigma _ { \mathrm { e n } }$ 为电子与中性原子的碰撞截面(近似为常数 $3 . 7 3 2 5 \times 1 0 ^ { - 2 0 } m ^ { 2 } )$ $\omega _ { \mathrm { g } } = { \frac { q B } { m _ { \mathrm { e } } } }$ B为电子磁回旋角频率．为简单起见，令

$$
\varepsilon _ { 1 } = 1 - \frac { \omega _ { \mathrm { p } } ^ { 2 } ( \omega - \mathrm { i } \nu ) } { \omega \left[ ( \omega - \mathrm { i } \nu ) ^ { 2 } - \omega _ { \mathrm { g } } ^ { 2 } \right] } ,
$$

$$
\varepsilon _ { 2 } = - \frac { \omega _ { \mathrm { p } } ^ { 2 } \omega _ { \mathrm { g } } } { \omega \left[ ( \omega - \mathrm { i } \nu ) ^ { 2 } - \omega _ { \mathrm { g } } ^ { 2 } \right] } ,
$$

$$
\varepsilon _ { 3 } = 1 - { \frac { \omega _ { \mathrm { p } } ^ { 2 } } { \omega ( \omega - \mathrm { i } \nu ) } } ,
$$

则(1)式可简化为

$$
\varepsilon _ { \mathrm { r } } = { \left[ \begin{array} { l l l } { \varepsilon _ { 3 } } & { 0 } & { 0 } \\ { 0 } & { \varepsilon _ { 1 } } & { \mathrm { i } \varepsilon _ { 2 } } \\ { 0 } & { - \mathrm { i } \varepsilon _ { 2 } } & { \varepsilon _ { 1 } } \end{array} \right] } ~ .
$$

# 2.2分层等离子体片中的状态矢量和本征波

磁化等离子体片中，麦克斯韦方程的两个旋度方程为

$$
\nabla \times \pmb { { \cal E } } = - \mathrm { i } \omega \mu _ { 0 } \pmb { { \cal H } } ,
$$

$$
\nabla \times \pmb { H } = \mathrm { i } \omega \varepsilon _ { 0 } \pmb { \varepsilon } _ { \mathrm { r } } \cdot \pmb { E } ,
$$

将(2)式代入(3b)式经过数学代换消去 $\scriptstyle { E }$ 和 $H$ 的 $z$ 轴分量后可得矩阵形式的状态方程[12,13]

$$
\begin{array} { r l } & { \frac { \partial } { \partial x } \left[ \begin{array} { l } { \Delta _ { x } } \\ { \Delta _ { y } } \\ { \Delta _ { x } } \\ { \left. M _ { x } \right. } \end{array} \right] } \\ & { = \left[ \begin{array} { l l l l } { 0 } & { 3 } & { 0 } & { - \mathrm { i } \omega \omega } \\ { 0 } & { 3 } & { \frac { \mathrm { i } \omega } { \mathrm { i } x } } & { 0 } \\ { 0 } & { 0 } & { \left( \frac { \mathrm { i } \omega - \mathrm { i } \omega } { \mathrm { i } x } \right) } & { 0 } & { 0 } \\ { - \mathrm { i } \omega \omega \omega _ { x } } & { 0 } & { 0 } & { \sqrt { 1 } } \end{array} \right] } \\ & { \qquad \left[ \begin{array} { l } { \Delta _ { x } } \\ { \Delta _ { y } } \\ { \omega } \end{array} \right] } \\ & { \qquad \left[ \begin{array} { l } { \Delta _ { y } } \\ { \Delta _ { z } } \\ { \omega } \end{array} \right] . } \end{array}
$$

(4)式可简写为本征方程的形式

$$
\frac { \partial } { \partial z } { \cal S } = C { \cal S } ,
$$

式中 $s$ 称为状态矢量， $C$ 称为耦合矩阵． (5)式是一个本征值问题,场量 $E , H \propto \exp ( - \mathrm { i } k _ { z } z )$ ，因此，本征值 $\lambda = - \mathrm { i } k _ { z }$ ，耦合矩阵共有四个本征值，分别对应沿正负 $z$ 方向传播的本征波，由等离子体理论知，在图2所示的传播模型中本征波为沿正负 $z$ 方向传播的寻常波(O波)和非寻常波(X波)． (5)式的通解为

$$
\begin{array} { r } { \pmb { S } ( z ) = \pmb { A } \cdot \exp ( \pmb { \lambda } z ) \cdot \pmb { B } , } \end{array}
$$

其中, $\pmb { A } = \left[ \pmb { A } _ { 1 } \ \pmb { A } _ { 2 } \ \pmb { A } _ { 3 } \ \pmb { A } _ { 4 } \right]$ 是一个为 $4 \times 4$ 的矩阵,称为本征矩阵, $A _ { j } ( j = 1 , 2 , 3 , 4 )$ 是对应于耦合矩阵 $c$ 的第 $j$ 个本征值 $\lambda _ { j }$ 所对应的归一化本征向量;$\exp ( \lambda z )$ 是一个对角阵，其对角元素为 $\exp ( \lambda _ { 1 } z )$ ，$\exp ( \lambda _ { 2 } z )$ ， $\exp ( \lambda _ { 3 } z )$ ， $\exp ( \lambda _ { 4 } z )$ ．本征值的排列应使前两行元素对应上行波 ( $z$ 轴正向)，后两行元素对应下行波 ( $z$ 轴负向); $B$ 是 $4 \times 1$ 的列向量,其元素代表上行波和下行波的幅值.

# 2.3 横向场的传播矩阵

当电磁波在同一小磁化等离子体片 $m$ 内传播时,将(6)式变换为

$$
\begin{array} { r } { { \bf S } _ { m } ( z ) = { \bf A } _ { m } \cdot \exp [ { \bf \lambda } _ { m } ( z - z ^ { \prime } ) ] \cdot { \bf A } _ { m } ^ { - 1 } \cdot { \bf A } _ { m } } \end{array}
$$

$$
\times \exp ( \lambda _ { m } z ^ { \prime } ) \cdot B _ { m }
$$

$$
= P _ { m } ( z , z ^ { \prime } ) \cdot S _ { m } ( z ^ { \prime } ) ,
$$

式中， $\begin{array} { r } { P _ { m } ( z , z ^ { \prime } ) = { A _ { m } } \cdot \exp [ \pmb { \lambda } _ { m } ( z - z ^ { \prime } ) ] \cdot { A _ { m } ^ { - 1 } } } \end{array}$ 为电磁波在第 $m$ 层内从 $z ^ { \prime }$ 点到 $z$ 点的传播矩阵.

当电磁波跨越第 $\mathrm { m }$ 层和第 $\mathrm { m } { + } 1$ 层的界面$z ~ = ~ z _ { m + 1 }$ 传播时，由场的切向分量连续性边界条件有

$$
S _ { m + 1 } ( z = z _ { m + 1 } ) = S _ { m } ( z = z _ { m + 1 } ) .
$$

由(7)，(8)式可得电磁波穿越整个等离子体片时的状态矢量

$\begin{array} { r l } { { } } & { { S _ { n + 1 } ( z = z _ { \mathrm { n } } ) } } \\ { { } } & { { = S _ { \mathrm { n } } ( z = z _ { \mathrm { n } } ) = P _ { \mathrm { n } } ( z _ { \mathrm { n } } , z _ { n - 1 } ) S _ { \mathrm { n } } ( z _ { n - 1 } ) } } \\ { { } } & { { = P _ { \mathrm { n } } ( z _ { \mathrm { n } } , z _ { n - 1 } ) S _ { n - 1 } ( z _ { n - 1 } ) } } \\ { { } } & { { = P _ { \mathrm { n } } ( z _ { \mathrm { n } } , z _ { n - 1 } ) P _ { n - 1 } ( z _ { n - 1 } , z _ { n - 2 } ) S _ { n - 2 } ( z _ { n - 2 } ) = \cdots } } \\ { { } } & { { = \displaystyle \prod _ { l = n } ^ { 1 } P _ { l } ( z _ { l } , z _ { l - 1 } ) S _ { 0 } ( z _ { 0 } ) = P ( z _ { \mathrm { n } } , z _ { 0 } ) S _ { 0 } ( z _ { 0 } ) , ( 9 ) } } \end{array}$ 式中 $P ( z _ { \mathrm { n } } , z _ { 0 } ) = \prod _ { l = n } ^ { 1 } P _ { l } ( z _ { l } , z _ { l - 1 } )$ 为电磁波从 $z _ { 0 }$ 传播到 $z _ { \mathrm { n } }$ 的总传播矩阵，

# 2.4反射率、透射率与吸收率

在图2所示的传播模型中，区域0中既有入射波又有反射波，根据(6)式,区域0中状态矢量 $s$ 可由沿正向和负向传播的两部分之和表示为

$$
\begin{array} { r l } { \pmb { S } ( z = z _ { 0 } ) = \pmb { A } _ { 0 + } \cdot \exp ( \pmb { \lambda } _ { + } z _ { 0 } ) \cdot \pmb { B } _ { 0 + } } & { { } } \\ { + \pmb { A } _ { 0 - } \cdot \exp ( \pmb { \lambda } _ { - } z _ { 0 } ) \cdot \pmb { B } _ { 0 - } } & { { } } \end{array}
$$

区域 $n + 1$ 中只有透射波，状态矢量 $s$ 表示为

$$
\begin{array} { r } { \pmb { S } ( z = z _ { \mathrm { n } } ) = \pmb { A } _ { n + 1 - } \cdot \exp ( \pmb { \lambda } _ { n + 1 - } z _ { \mathrm { n } } ) } \\ { \times \pmb { B } _ { n + 1 - } , } \end{array}
$$

(10)，(11)式中下标 $+ , -$ 分别表示沿 $z$ 轴正向和负向传播的电磁波，定义整个等离子体片的反射系数矩阵 $R$ 和透射系数矩阵 $T$ 分别为

$$
\begin{array} { l } { { B _ { \mathrm { 0 + } } = R \cdot B _ { \mathrm { 0 - } } , } } \\ { { B _ { n + 1 - } = T \cdot B _ { \mathrm { 0 - } } , } } \end{array}
$$

其中， $B _ { 0 - }$ 表示区域0中的入射波幅度，

$$
\begin{array} { r } { { \bf R } = \left[ \begin{array} { l } { R _ { \mathrm { I , I } } ~ R _ { \mathrm { I , I I } } } \\ { R _ { \mathrm { I I , I } } ~ R _ { \mathrm { I I , I I } } } \end{array} \right] , { \bf T } = \left[ \begin{array} { l } { T _ { \mathrm { I , I } } ~ T _ { \mathrm { I , I I } } } \\ { T _ { \mathrm { I I , I } } ~ T _ { \mathrm { I I , I I } } } \end{array} \right] , } \end{array}
$$

${ \pmb R } ( { \pmb T } )$ 的四个元素分别表示反射 (透射)波中I型波与 $\mathrm { I I }$ 型波的耦合关系，例如， $R _ { \mathrm { I , I I } }$ 表示I型波入射

时,反射波为Ⅱ型波的反射系数.将(10), (11),(12) 式代入到(9)式中可得

$$
\begin{array} { r l r } {  { \boldsymbol { A } _ { n + 1 } \cdot \exp ( \lambda _ { n + 1 } z _ { \mathrm { n } } ) \cdot [ \begin{array} { l } { 0 } \\ { T } \end{array} ] } } \\ & { } & \\ & { } & { = P ( z _ { \mathrm { n } } , z _ { 0 } ) \boldsymbol { A } _ { 0 } \cdot \exp ( \lambda _ { 0 } z _ { 0 } ) \cdot [ \begin{array} { l } { R } \\ { I } \end{array} ] . } \end{array}
$$

由于区域0和区域 $n + 1$ 中介质为空气，I型波与II型波退化为TE波与TM波，并且在图2所示电磁波传播模型中，不存在TE波与TM波之间的耦合[16], $R _ { \mathrm { I , I I } } = R _ { \mathrm { I I , I } } = T _ { \mathrm { I , I I } } = T _ { \mathrm { I I , I } } = 0 .$ （20

对于TE波(具有 $E _ { y }$ ， $H _ { x }$ 分量):

对于TM波(具有 $H _ { y } , E _ { x }$ 分量):

反射率 $P _ { \mathrm { r T M } } = \left| R _ { \mathrm { I I , I I } } \right| ^ { 2 }$ 透射率 $P _ { \mathrm { t T M } } = \left| T _ { \mathrm { I I , I I } } \right| ^ { 2 }$ 吸收率 $P _ { \mathrm { a T M } } = 1 - \left| R _ { \mathrm { I I , I I } } \right| ^ { 2 } - \left| T _ { \mathrm { I I , I I } } \right| ^ { 2 } .$

若已知磁场 $B$ 、气压 $P$ 及厚度向电子密度分布，利用上述横向场传播矩阵法可以分别得到TE波、TM波的反射率、透射率及吸收率.

# 3计算结果及分析

在气压为 $\mathrm { 1 5 0 ~ P a }$ ，磁场为 $1 5 0 ~ \mathrm { G s }$ 条件下,利用脉冲磁约束线形空心阴极放电装置形成放电电流为 ${ 1 \mathrm { A } , 2 \mathrm { A } , 3 \mathrm { A } , 4 \mathrm { A } }$ 的四种大面积等离子体片，等离子体片面积为 $6 0 ~ \mathrm { c m } \times 6 0 ~ \mathrm { c m }$ ，空心阴极宽度为$1 . 6 ~ \mathrm { c m }$ ．采用郎缪尔探针诊断测得等离子体片厚度方向上电子密度及其随脉冲放电时间的演化分布，如图3所示．图中厚度向距离的 $0 ~ \mathrm { m m }$ 对应等离子体片的厚度中心，坐标值的正负分别代表厚度中心的两侧，坐标大小代表与厚度中心之间的距离，脉冲放电时间包括了等离子形成后到熄灭前主要的放电阶段(不包含放电的初始及熄灭阶段).

![](images/a01079becfc70791dc60b62a5adb93e3d871f61c2d36fa313fba90ac221ac20c.jpg)  
图3等离子体片厚度向电子密度及其随脉冲放电时间的时空分布图(a)1A;(b)2A;(c)3A;(d)4A Fig.3.Electron density 2-D distribution in the thickness direction and its evolution with diferent discharge current peak values: (a) $I = 1$ A;(b) $I = 2$ A;(c) $I = 3 \mathrm { ~ A ~ }$ ；(d) $I = 4$ A.

由图3可知，等离子体片厚度方向上电子密度随脉冲时间是变化的，在脉冲放电前期约 $1 0 0 ~ { \mu \mathrm { s } }$ 时间内，存在一个不稳定放电阶段．统一选取脉冲放电稳定阶段内放电时间为 $1 7 0 ~ \mu \mathrm { s }$ 时的厚度方向上电子密度代表整个等离子体片的电子密度分布用来计算电磁波在不同放电电流等离子体片中的传播特性， $1 7 0 ~ \mu \mathrm { s }$ 时不同放电电流等离子体片厚度向电子密度如图4所示．图4中放电电流为1A,2A,3A，4A时，等离子体片的峰值电子密度约为$4 . 3 \times 1 0 ^ { 1 6 } \ \mathrm { m ^ { - 3 } }$ ， $7 . 1 \times 1 0 ^ { 1 6 } \ \mathrm { m ^ { - 3 } }$ ， $1 . 0 \times 1 0 ^ { 1 7 } ~ \mathrm { m ^ { - 3 } }$ $1 . 3 \times 1 0 ^ { 1 7 } \ \mathrm { m ^ { - 3 } }$ ，其对应的理想电磁波截止频率约为1.8 GHz,2.4 GHz,2.8 GHz,3.2 GHz. 由等离子体理论可知，TM波垂直入射时，其极化方向平行于磁场,在等离子体内对应于寻常波(O波),TE波垂直入射时，极化方向垂直于磁场，在等离子体内对应于非寻常波 (X波).非寻常波(X波)在传播过程中存在高混杂谐振吸收[12]，高混杂谐振吸收圆频率 $\omega _ { \mathrm { U H } }$ 为

$$
\omega _ { \mathrm { U H } } ^ { 2 } = \omega _ { \mathrm { p e } } ^ { 2 } + \omega _ { \mathrm { g } } ^ { 2 } ,
$$

磁回旋圆频率 $\omega _ { \mathrm { g } }$ 约为 $2 . 6 \ \mathrm { G H z }$ ，将圆频率转换为频率值，由(16)式可计算得到峰值电子密度对应的最大高混杂谐振频率 $f _ { \mathrm { U H } }$ 约为 $1 . 9 \ \mathrm { G H z }$ ， $2 . 4 ~ \mathrm { G H z }$ 2.8 GHz,3.2 GHz.

![](images/564a6438f03404c335dbea06cb8bcbae4545a2f7969e0e31ca4193fcea22f09b.jpg)  
图4 $1 7 0 ~ \mu \mathrm { s }$ 时,等离子体片厚度向电子密度分布 Fig.4.Electron density distribution in the thickness direction when the sampling time was $1 7 0 ~ \mu \mathrm { s }$

按图2所示等离子体片分层模型，将图4中非均匀等离子体片沿厚度向均匀地分为300层,利用本文第2部分所述横向场传播矩阵法，计算得到不同放电电流等离子体片的反射率、透射率、吸收率随电磁波频率的变化规律，如图5(a),(b),(c)所示.图中红色曲线与黑色曲线分别为TE波与TM波的计算结果．由图可知，以截止频率为分界点，等离子体片对电磁波具有明显的“低阻高通”特征，TM波在小于截止频率的低频带内具有较高的反射率和吸收率，电流增大，反射率增加，吸收率下降；在大于截止频率的高频带内透射率高，吸收率低，增大电流，透射率下降，吸收率升高；由图5(c)可知TE波在最大高混杂谐振频率附近存在高混杂谐振吸收带，其谐振吸收峰值与放电电流无关,其他电磁波传播特性与TM波相同，

![](images/7a3b25106aca9217b7dbf5ef0f3c0ae4aa3e75ec04d95fc56d1704099db2f5e8.jpg)  
图5 $1 7 0 ~ \mu \mathrm { s }$ 时，等离子体片的反射率、透射率、吸收率随电磁波频率的变化曲线 (a)反射率;(b)透射率;(c)吸收率  
Fig.5.Reflection rate,transmission rate and absorption rate versus wave frequency when the sampling time is $1 7 0 ~ \mu \mathrm { s }$ ：(a）reflection rate;(b） transmission rate;(c) absorption rate.

对上述传播特性可做如下解释，当入射电磁波的频率远大于等离子体的截止频率时，等离子体片中电子来不及响应电磁场的振荡，因此，反射率与吸收率比较小，透射率很大，当电磁波频率远小于等离子体中电子的振荡频率，电磁波很容易与电子相互作用而被反射与吸收，因此反射率与吸收率较大,透射率很小．由图4可知，放电电流增加，等离子体片厚度向电子密度整体增大，因此，对于同一频率入射电磁波，反射率升高,透射率下降,低频带内小于截止频率的电磁波由于反射严重，可被吸收与透射的电磁波很少，因此，吸收率随着放电电流

![](images/f634bc3a8fc77211dfbc42ee6cb9e1905e75991b6ae4ce53778828f2774e3da7.jpg)  
图61GHz电磁波在等离子体片中的反射率、透射率、吸收率随脉冲放电时间的变化 (a)反射率;(b)透射率;(c)吸收率

Fig.6.Reflection rate,transmission rate and absorption rate versus pulse discharge time for 1 GHz electromagnetic wave:(a) reflection rate;(b) transmission rate;(c) absorption rate.

的增加而降低，高频带内大于截止频率的电磁波，虽然反射率也随着放电电流的增加而增大，但是，由于反射率本身较小并且电子数增加，从而导致吸收效果随放电电流增大而增强.

为了分析电磁波在等离子体片中的传播特性随脉冲放电时间的变化特性，选用1GHz频率远小于截止频率与4GHz频率远大于截止频率的电磁波，利用图3所示的厚度向电子密度时空分布计算得到反射率、透射率、吸收率随脉冲放电时间的变化曲线，如图6、图7所示.

![](images/50f501e708c45ec255b411d9434f8d21beff57a5ee7e034c49c2699413321ef5.jpg)  
图74GHz电磁波在等离子体片中的反射率、透射率、吸收率随脉冲放电时间的变化曲线 (a)反射率;(b)透射率;(c)吸收率

Fig.7.Reflection rate,transmission rate and absorption rate versus pulse discharge time for 4 GHz electromagnetic wave:(a) reflection rate;(b) transmission rate;(c)absorption rate.

由图3、图6、图7可知与等离子体片厚度向电子密度分布随脉冲放电时间的变化规律相对应，在整个脉冲放电过程中，电磁波的反射率、透射率与吸收率也经历了一个由不稳定向稳定过渡的过程并且过渡时间随放电电流的增加而增大，稳定的电磁波传播特性阶段恰好与等离子体片放电时间100μs之后的稳定放电阶段相对应．图6(c)与图7(c)中吸收率变化曲线，再次印证了吸收率在低频带与高频带内随放电流变化规律截然相反，此外，由图还可以发现，TE波的高混杂谐振吸收在稳定放电阶段，对低频电磁波的影响非常明显，而对高频电磁波，在非稳定放电阶段影响明显．因此，为了使入射的低频率电磁波具有稳定的高的反射率，应避免使用TE波，即入射波的频率应平行磁场

# 4结论

等离子体片对电磁波具有明显的“低阻高通”特征，在小于截止频率的低频带内由于电子可以响应电磁波的振荡，因此，反射率和吸收率较高，与之相反，在大于截止频率的高频带内电子与电磁波相互作用弱，反射率与吸收率较低、透射率比较高．与TM波相比，TE波在高混杂谐振频率附近存在一个吸收率明显增强的吸收带，其产生物理机理为高混杂谐振吸收，谐振吸收的峰值与放电电流大小无关．随着放电电流的增大，等离子体片电子密度整体升高，使得反射率升高、透射率下降,这与Ding等[11]的实验结果一致；小于截止频率的低频带内,吸收率随着放电电流的增大而减小，但在大于截止频率的高频带内变化规律相反．在脉冲放电过程中，由于等离子体片厚度向电子密度分布在约100us后才基本稳定，电磁波的传播特性经历了一个由不稳定向稳定过渡的过程,过渡时间随着放电电流的增加而增大，稳定放电阶段的TE波谐振吸收较强．因此，为了使等离子体片对入射波具有稳定的高反射率，等离子体片脉冲放电时间应至少大于$1 0 0 ~ { \mu \mathrm { s } } .$ 。放电电流应足够大使其临界截止频率远大于入射电磁波频率，入射波极化方向与形成磁化等离子体片的磁场平行.

# 参考文献

[1] Caillault L, Larigaldie S 2002 J. Phys.D:Appl. Phys. 35 1010   
[2] Mathew J, Fernsler R F,Meger RA,Gregor JA,Murphy D P, Pechacek R E,Manheimer W M 1996 Phys. Rev. Lett. 77 1982   
[3] Manheimer W M 1991 IEEE Trans. Plasma Sci.19 1228   
[4] Fernsler R F,Manheimer W M, Meger R A,Mathew J, Murphy D P, Pechacek R E, Gregor JA 1998 Phys. Plasmas 5 2137   
[5] Manheimer W M, Fernsler R F,Gitlin M S 1998 IEEE Trans. Plasma Sci. 26 1543   
[6] Gillman E D,Amatucci W E 2014 Phys. Plasmas 21 060701   
[7] Zhuang Z W, Yuan N C,Liu S B,Me J J 2005 Plasma Stealth Technology (Beijing:Science Press) p46 (in Chinese)[庄钊文，袁乃昌，刘少斌,莫锦军 2005 等离子体隐身 技术(北京：科学出版社)第46 页]   
[8] Larigaldie S,Caillault L 20OO J. Phys.D:Appl. Phys. 33 3190   
[9] Cheng Z F, Ding L,Xu Y M,Liang C, Jian F S 2009 Chin.J.Radio Sci.241137(in Chinese)[程芝峰,丁亮, 徐跃民,梁超,鉴福升 2009 电波科学学报 24 1137]   
[10] Cheng ZF,Xu YM,Liang C,Ding L, JianF S, Zhu X 2010 Chin.J.Radio Sci.24 1137 (in Chinese）[程芝峰, 徐跃民,梁超，丁亮，鉴福升，朱翔 2010 电波科学学报 24 1137]   
[11] Ding L, Huo W Q, Yang X J, Xu Y M 2012 Plasma Sci. Technol.14 9   
[12] Huo W Q,Guo S J, Ding L,Xu Y M 2013 Plasma Sci. Technol. 15 979   
[13] Negi J G, Singh R N 1968 Pure Appl. Geophys. 70 74   
[14] Rokhlin S I, Wang L 2002 J. Acoust. Soc. Am. 112 822   
[15] Zheng H X, Ge D B 2000 Acta Phys.Sin. 49 1702 (in Chinese）[郑宏兴，葛德彪 2000 物理学报 49 1702]   
[16] Yin X, Zhang H, Sun S J, Zhao Z W,Hu Y L 2013 Prog. Electromagn. Res.137 159   
[17] Mathew J, Meger R A, Fernsler R F,Gregor JA 1996 Rev. Sci. Instrum. 67 2818   
[18] Leonhardt D,Walton S G,Blackwell D D,Amatucci W E,Murphy D P,Fersnelr RF,Meger R A 2001 J. Vac. Sci. Technol. A 19 1367   
[19] Blackwell D D,Walton S G,Leonhardt D, Murphy D P, Fernsler R F,Amatucci W E, Meger R A 2001 J. Vac. Sci. Technol. A 19 1330   
[20] Zhang L, Zhang H X, Yang X Z, Feng C H, Qiao B, Wang L 2003 Chin. Phys. Lett.20 1984   
[21] Lock E H,Fernsler R F,Walton S G 2008 Plasma Sources Sci. Technol. 17 025009   
[22] Wan J, Jia XL,Yang JH,Wang SG 201O IEEE Trans. Plasma Sci. 38 2006

# Analysis of propagation properties of electromagnetic waves through large planar plasma sheets’

Xia Jun-Ming1)2)t Xu Yue-Min1） Sun Yue-Qiang1）Huo Wen-Qing1）Sun Hai-Long1) Bai Wei-Hua1) Liu Cong-Liang1）Meng Xiang-Guang1)

1)(Center for Space Science and Applied Research,Chinese Academy of Sciences,Beijing 100190,China)

2)(University of Chinese Academy of Sciences,Beijing 1oo19o,China) (Received 5 March 2015; revised manuscript received 14 May 2015)

# Abstract

Large planar plasma sheets，generated by a linear hollow cathode in pulse discharge mode under magnetic confinement,canbe used in the feldof plasma antenna, plasma stealth,and simulation of a plasma layer surrounding vehicles traveling at hypersonic velocities within the Earth's atmosphere.Firstly,to investigate the propagation properties of electromagnetic wavesat different frequenciesand polarization,the transverse feld transfer matrix method is introduced.Secondly,the measured electrondensitytemporaland spatial distributionandthetransverse field transfer matrix method areutilized tocalculate the reflection,transmission and absorption of electromagnetic waves by large planar plasma sheets withdiferentcurrents.Finall,1GHz (less thanthecritical cut-off frequency) electromagnetic wavesand4 GHz (greater than the critical frequency)electromagnetic waves are chosen to investigate the evolution of propagation properties during the pulsed discharge period.Results show that both the reflection and absorption of the electromagnetic waves aregreater for theirpolarization direction paraleltothatof magnetic field,and their frequencies lower thanthecriticalcut-offrequencyandasthedischargecurrentsrise,thereflectioincreases whiletheabsorption decreases.However both thereflectionand absorption of theelectromagnetic waves with their polarization direction perpendicular to the magnetic field direction and their frequency greater than thecritical cut-offrequency become less, andasthe discharge currents rise,both therefectionand absorptionwillincrease.Fortheelectromagnetic waves with their polarization direction perpendicular tothe magneticfeld direction,there isan upper hybridresonance absorption band near the upper hybrid resonance frequencies,in which the absorption is significant but the absorption peak value is not affected bythe discharge currnt.The propagation characteristicsof theelectromagnetic waves with polarization direction perpendicular tothe magnetic field directionare the sameas thatof the electromagnetic waves with the polarization direction paralel to the magnetic feld direction,except theupper hybrid resonance absorption.During the pulse discharge period,the propagation characteristic of the electromagnetic waves experiences an unstable phase before reaching steady states.The transition time is about 10O μs and increases as the discharge currnt rises.The upper hybrid resonance absorption is significant during the phase of steady state for waves with frequency lower than thecriticalcut-offrequencyand polarization directionparaleltothe magneticfield direction.Fortheapplicationsofa large planar plasma sheet to refect electromagnetic waves effctivelyand steadily,the pulse discharge period shouldbe larger than1OO μs,and its dischargecurrent should be large enough to make the critical cut-offrequency greater than the frequency of incident wave,and its polarization direction should be paralel to the magnetic field direction.

Keywords: linear hollow cathode,magnetized plasma sheet，electron density distribution, transverse field transfer matrix method

PACS: 42.25.Bs, 52.77.-j, 52.70.-m

DOI: 10.7498/aps.64.194202