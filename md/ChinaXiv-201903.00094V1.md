# 基于模糊控制与自适应步长相结合的光伏发电系统最大功率点跟踪研究

![](images/25f3ae46b37e508b73163cd3b461a426b3701c12deae0eca2151d70848521e44.jpg)

万庆祝张翅帆(北方工业大学电气与控制工程学院北京100144)

万庆祝男1975年生，博士，副教授，研究方向为分布式发电。

摘要：光伏发电已逐渐得到人们的重视和使用，根据光伏电池输出特性非线性的特点，采用了模糊控制的方法来进行最大功率点的跟踪。本文搭建了光伏发电系统的仿真模型，设计了模糊控制器，并为了弥补传统步长算法在光伏发电系统最大功率点跟踪上的缺陷，采用了自适应步长调整法来自动调整被控量。通过与传统定步长、变步长的仿真结果进行比较，得出了基于模糊控制的自适应步长调整法，可以快速实现光伏发电系统的最大功率点的跟踪控制，并使输出一直维持在稳定值。

关键词：光伏发电最大功率点跟踪 模糊控制自适应步长调整法中图分类号：TM73

# Research on Maximum Power Point Tracking of Photovoltaic Generation System Based on Fuzzy Control and Adaptive Step Combination

![](images/d21c02f727b915e2a23fca2a678abac7f48b0acc86325725bb40a0039506e220.jpg)

Wan QingzhuZhang Hongfan (North China University of TechnologyBeijing100144 China)

张翊帆女 1993年生，硕士研究生，研究方向为分布式发电。

Abstract: Solar power generation has been gradually getting people's attention and using，according to the characteristics of the output characteristic of PV cells, the fuzzy control method is used to track the maximum power point, which makes up the deficiency of the traditional control method.The simulation model of the photovoltaic power generation system is built, the fuzzy controller is designed,and in order to make up for the defects of the traditional step size algorithm in the maximum power point tracking of photovoltaic generation system, the adaptive step size adjustment method is adopted to adjust the controlled volume automatically. By comparing the simulation results with the traditional fixed step size and variable step size,the adaptive step size adjustment method based on fuzzy control can realize the maximum power point tracking control of photovoltaic power generation system,and the output value has been maintained at a stable value.

Keywords: Photovoltaic power generation, maximum power point tracking, fuzzy control,adaptive step size adjustment method

# 1 引言

太阳能是一种新型的绿色可再生能源，太阳能发电已普遍被人们认为是最清洁的发电方式，光伏发电系统面临的最大问题就是太阳能光伏阵列的光电转换效率太低，只有 $1 2 \% \sim 1 7 \% ^ { [ 1 ] }$ ，因此，光伏发电系统的最大功率点跟踪（MaximumPowerPointTracking，MPPT）问题已成为各国研究的焦点。

目前国内外研究主要集中于通过改进光伏发电系统的最大功率点控制算法，来实现光伏发电系统的最大功率输出。知名学者葛丽芳等提出了一种固定电压法来实现光伏发电系统MPPT，其主要原理是基于光伏电池的开路电压与最大功率点之间的耦合关系，来调节系统的工作点电压，达到最大功率输出。其优点是输出电压为固定值，易于控制；但当外界环境发生变化时，却无法实时跟踪光伏电池的输出状态，给光伏发电系统的输出功率造成大量的损失[2-3]。任玲等提出了一种扰动观察法，该方法操作简单，测量参数少，易于实现，是目前计算光伏发电系统MPPT最常用的方法[4]。其原理是给系统引入一个小的变化进行观测和比较，以此来判断和调节输出电压的变化方向，使光伏电池达到最大功率点，但是此方法的控制精度相对较低，反应速度比较慢，只适合外界环境变化不大的情况[5-6]。黄瑶等提出了一种电导增量法来求解光伏发电系统MPPT，该方法是通过光伏阵列输出的动态电导值和静态电导值的负数之间的关系来调整工作电压，实现最大功率点的跟踪。该控制方法能很快地检测到外界环境突然的变化，并进行追踪与调节，保证系统继续稳定运行，但是它的算法结构相对复杂，不易实现[7-8]。本文采用模糊控制[9]的方法进行光伏发电系统最大功率点的跟踪，可以弥补上述传统控制方法的缺点，达到比较理想的控制效果。

本文先对光伏电池和光伏发电系统的控制电路进行建模；然后介绍并比较了几种常用的步长算法。选用智能控制中模糊控制的理论，并采取模糊控制与自适应占空比步长相结合的算法，来实现光伏发电系统最大功率点的跟踪控制，设计了模糊控制器，与光伏电池的模型相结合，进行光伏发电系统的建模与仿真。最后对比分析了定步长调整法、变步长调整法以及自适应步长调整法的仿真结果，结果表明自适应步长调整法明显优于其他两种算法的控制效果。

# 2 光伏发电系统MPPT实验原理及控制电路

# 2.1光伏发电系统原理组成

光伏发电系统主要由光伏电池组件、控制电路、MPPT控制器和负载等组成。光伏电池的作用是将太阳能照射的光能转换为电能；控制电路采用DC-DC变换电路，由升压斩波变换电路构成[10]；MPPT控制器通过模糊控制与自适应步长相结合的算法实现其功能。光伏发电系统的等效电路图如图1所示。

![](images/68bce3c027e4d7105769fc8a933bd55d37319267cd23f4d9a97b719cee7d540f.jpg)  
图1光伏发电系统原理图

# 2.2光伏电池的建模与仿真

光伏电池模型可等效为一个电压源和一个二极管并联，再串联和并联上其内部的等效电阻，等效电路如图2所示。

![](images/c9900498eecaa0595756b7fbba8f3281e1a6f56d4f60ac6b91bf15d788eaa330.jpg)  
Fig.1Principle diagram of photovoltaic power generation system   
图2光伏电池等效模型  
Fig.2Equivalent model of photovoltaic cells

由图2可得出光伏电池的输出电流 $I$ 与输出电压 $V$ 的关系为

$$
I = I _ { \mathrm { p h } } - I _ { \mathrm { d } } = I _ { \mathrm { p h } } - I _ { \mathrm { o } } \left\{ \exp \left[ \frac { q ( V + R _ { \mathrm { s } } I ) } { A K T } \right] - 1 \right\} - \frac { V + R _ { \mathrm { s } } I } { R _ { \mathrm { s h } } }
$$

式中， $I _ { \mathrm { p h } }$ 为光伏电池经由光照射后所产生的电流；$I _ { \mathrm { d } }$ 为二极管电流； $R _ { \mathrm { s h } }$ 和 $R _ { \mathrm { s } }$ 分别为材料内部等效的并联和串联电阻； $T$ 为电池板表面温度（K）；$A$ 为电池板理想因数 $\left( { \cal A } = 1 \sim 2 \right)$ ； $q$ 为电子所含的电荷量（ ${ } ^ { ' } 1 . 6 \times 1 0 ^ { - 1 9 } \mathrm { C } )$ ； $K$ 为波尔兹曼常数（ $1 . 3 8 \times$ $1 0 ^ { - 2 3 } \mathrm { J / K }$ ）

$I _ { \mathrm { o } }$ 表示光伏电池板的逆向饱和电流，可表示为

$$
I _ { \mathrm { o } } = I _ { \mathrm { r } } \left[ \frac { T } { T _ { \mathrm { r } } } \right] ^ { 3 } \exp \left[ \frac { q E _ { \mathrm { g a p } } } { K _ { \mathrm { a } } } \left( \frac { 1 } { T _ { \mathrm { r } } } - \frac { 1 } { T } \right) \right]
$$

式中， $T _ { \mathrm { r } }$ 为光伏电池板的参考温度； $I _ { \mathrm { r r } }$ 为光伏电池在温度临界时的逆向饱和电流； $E _ { \mathrm { g a p } }$ 为半导体材料跨越能带间隙时所需的能量。

当光照较强时，光电流远远大于 $( V + I R _ { \mathrm { s } } ) / R _ { \mathrm { s h } }$ 故光伏电池的输出特性方程可简化为式 (3）。

$$
I = I _ { \mathrm { p h } } - I _ { \mathrm { o } } \left\{ \exp \left[ \frac { q ( V + R _ { \mathrm { s } } I ) } { A K T } \right] - 1 \right\}
$$

根据光伏电池输出特性的数学模型，本文选择Solarex $\mathrm { M S x } 6 0 ~ 6 0 \mathrm { W }$ 光伏电池阵列[11]进行建模，在Matlab软件中搭建仿真模型。

# 2.3MPPT控制电路

光伏发电系统的MPPT控制电路引入了DC-DC变换器[12]，采用Bo0st升压电路来实现光伏发电系统中最大功率点跟踪的功能，Boost电路原理图如图3所示。

![](images/877bc5d78697bf8302fc17501be85ca7ae395e600e4a881d3d3f1d791bda7cdd.jpg)  
图3升压斩波电路原理图  
Fig.3Boost chopper circuit schematic

Boost电路由开关 $\mathrm { \Delta V }$ 、二极管VD、储能电感 $L$ 和滤波电容 $C$ 以及负载 $R$ 组成。在理想状态下，电路中电感 $L$ 和电容 $C$ 均很大。Boost电路的输入输出关系为

$$
\frac { U _ { \mathrm { o } } } { U _ { \mathrm { i } } } = \frac { 1 } { 1 - D } \qquad 0 < D < 1
$$

由图3可知输入电阻为

$$
R = \frac { U _ { \mathrm { I } } } { I _ { \mathrm { I } } }
$$

式中， $U _ { \mathrm { I } }$ 为Boost电路输入电压； $I _ { \mathrm { I } }$ 为输入电流;  
$U _ { \mathrm { o } }$ 为输出电压； $I _ { \mathrm { o } }$ 为负载电流。

$R _ { \mathrm { L } }$ 为负载电阻，根据功率平衡，可得

$$
U _ { \mathrm { { I } } } I _ { \mathrm { { I } } } = { \frac { U _ { \mathrm { { o } } } ^ { 2 } } { R _ { \mathrm { { L } } } } }
$$

由式（4）～式（6）可得Boost电路的等效输入电阻为

$$
R = \left( 1 - D \right) ^ { 2 } R _ { \mathrm { L } }
$$

由此可见，通过调节占空比 $D$ ，即可改变Boost电路的输入电阻 $R$ ，如果使其刚好等于光伏电池的等效内阻，则光伏电池输出最大功率[13]。根据以上公式在Matlab中搭建Boost电路的仿真模型。

# 3模糊控制与自适应步长相结合的最大功率点跟踪算法

# 3.1传统步长算法

在扰动观察法中，可通过改变DC-DC变换器中Boost电路的占空比 $D$ 对系统进行观测和比较，实现最大功率点的跟踪控制。传统的步长算法有定步长调整法和变步长调整法。定步长调整法是指将步长调整值设为一固定参数，对下一时刻的占空比施加扰动，改变固定的步长值，使光伏电池运行在最大功率点[14]。这种算法对于扰动步长值的选取比较麻烦，控制精度也不够准确。变步长调整法是根据功率的变化率的几个不同阶段，赋予不同的步长调整值。根据当前时刻与前一时刻的功率变化，决定输出电压的调整方向，并根据功率的变化大小来调整步长的变化，这样可以更快速地跟踪到系统的最大功率点[15]。

# 3.2自适应占空比步长调整法

在传统的变步长调整法中，调整占空比 $D$ 时会产生如何判断步长调整值大小的问题，若调整值过大，会造成系统稳态误差增大；若调整值过小，跟踪时间就会变长，从而影响系统的动态响应特性。基于此，本文采用一种优化的变步长调整方法，加入一个步长调整值参数 $\mathbf { \nabla } _ { a }$ ，使系统能自动调整步长选择的大小，改善系统的稳态误差与动态响应问题[6]。自动调整器如下

$$
a ( k + 1 ) = M \frac { \left| \Delta P \right| } { a ( k ) }
$$

式中， $a ( k )$ 为占空比 $D$ 的步长调整值，在0和1之间变化； $\Delta P$ 是功率的变化量； $M$ 为一常数。

当外界环境因素突然变化较大时，一般的扰动观察法会认为是输出电压或电流的增减导致了输出功率的变化，在此情况下调整步长，可能会导致控制器远离最大功率点。式（8）可解决这一问题。当$\Delta P / a ( k )$ 较小时，说明此时只有占空比 $D$ 的变化来决定输出功率 $P$ 的大小，因此下一时刻占空比的步长调整值 $a ( k + 1 )$ 的变化不应过大；当 $\Delta P / a ( k )$ 较大时，表示功率 $P$ 的变化主要是由温度、光照强度等外界因素造成的，此时应增大 $a ( k + 1 )$ 来保证系统快速跟踪到最大功率点。当功率 $P$ 的波动变小后，调整器会认为系统已达到了最大功率点，将自动减小$a ( k + 1 )$ 的变化来维持系统的稳定输出。由此可见该方法具有很强的自适应性，因此称为自适应占空比步长调整法[17]。

# 3.3与自适应步长相结合的模糊控制器的设计

最大功率点跟踪控制一般是通过检测当前时刻的输出电压、电流值，得出此时的输出功率并与前一时刻比较，以此判断电压的调整方向[18]。这就需要设计两个控制循环结构来测量两个量。为了减小控制器的设计复杂程度，决定采用改变占空比 $D$ 的方法来调整系统的输入输出关系，并且为了解决在调节占空比 $D$ 时存在的调整步长大小的选择问题，本文采取了自适应步长调整法，加入了步长调整值$\mathbf { \Delta } _ { a }$ ，使系统通过当前时刻与前一时刻的输出功率的比较，自动调整步长的变化大小。

# 3.3.1输入、输出量的选择

模糊控制器的输入量是第 $n$ 时刻的功率变化量$E ( n )$ ，和第 $^ { n - 1 }$ 时刻的占空比步长调整值 $A ( n { - } 1 )$ 输出量是第 $n$ 时刻的占空比步长调整值 $A ( n )$ 。控制原理如图4所示。

![](images/3627c80f99417aee11a7f88c3c34747cdc346561a527d8ff8ea3678f83107b08.jpg)  
图4光伏系统模糊控制器原理图  
Fig.4Fuzzy controller principle of photovoltaic system

其中， $K _ { \mathrm { e } }$ ， $K _ { \mathrm { a } }$ 分别为量化因子，是将功率差实际值$e$ 和步长实际值 $\mathbf { \Omega } _ { a }$ 转换到模糊控制器的论域范围内，使其分别变为模糊值； $\mathrm { e } ^ { - T s }$ 是一个延迟环节。

# 3.3.2输入、输出模糊集的确定

对于输入、输出量的偏差大小，通过定义模糊集来表示。

将功率变化量 $E ( n )$ 定义为8个模糊集： $E ( n ) =$ {NB，NM，NS，NO，PO，PS，PM，PB}，取值范围为 $[ - 6 , ~ + 6 ]$ 。

将占空比步长调整值 $A ( n )$ 和 $A ( n { - } 1 )$ 定义为6

个模糊集： $A ( n ) = \{ \mathrm { N B }$ ，NM，NS，PS，PM，PB},$A ( n - 1 ) = \{ \mathrm { N B }$ ，NM，NS，PS，PM，PB}，取值范围为 $[ - 6 , ~ + 6 ]$ 。

NB，NM，NS，NO，PO，PS，PM，PB分别表示负大，负中，负小，负零，正零，正小，正中，正大的模糊概念。

# 3.3.3确定与自适应步长相结合的模糊控制规则

光伏电池的输出功率 $P$ 与占空比 $D$ 之间的特性关系，跟其与输出电压 $U$ 之间的关系类似，也呈非线性关系[19]，因此制定如下规则：

(1）若当前时刻的输出功率是增大的，则控制器维持前一时刻的步长调整方向；若当前时刻功率减小，则步长调整值取相反方向。

(2）在离最大功率点较远的地方，选择较大的步长调整值调整；在接近最大功率点处，则采用小步长来进行调整。

另外，考虑到外界条件对系统的影响，还添加了如下规则：

若因外界坏境因素变化而引起光伏电池的输出功率发生较大变化时，系统要通过自适应步长调整来自动进行调节。

模糊控制语言规则的一般形式为：如果“前提”，那么“结论”（If…Then…）。

对于光伏系统MPPT的控制，例如当功率变化量 $E ( n )$ 是负大 (NB)，前一时刻的占空比步长调整值 $a ( n { - } 1 )$ 也是负大（NB）时，说明输出功率在减小，而且离最大功率点较远，则此时占空比的步长调整值应与前一时刻的方向相反，并采取较大步长调整来加快跟踪速度。因此，输出量当前时刻的步长调整值 $a ( n )$ 应是正大 (PB)。

用语言规则形式来表示上述规则为：如果功率变化量为负大且前一时刻步长调整值为负大，那么当前时刻步长调整值为正大。

通过定义的输入、输出模糊集数量，共形成了48条规则。

# 3.3.4建立模糊控制规则表

根据上文所确定的与自适应步长相结合的模糊控制规则，建立的模糊控制规则表，见表1。

# 3.3.5确定隶属函数

通过Matlab中的Fuzzy工具箱来建立MPPT控制器的隶属函数，选择三角形作为隶属函数的形状[20]。光伏电池的输出功率在最大点的两侧是不对称的，因此三角形的形状也设置为不对称的。输入量和输出量的隶属函数如图5～图7所示。

表1MPPT模糊控制规则表  
Tab.1Fuzzy control rules table of MPPT   

<html><body><table><tr><td rowspan="2">A</td><td colspan="8">E</td></tr><tr><td>NB</td><td>NM</td><td>NS</td><td>NO</td><td>PO</td><td>PS</td><td>PM</td><td>PB</td></tr><tr><td>NB</td><td>PB</td><td>PM</td><td>PS</td><td>PS</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td></tr><tr><td>NM</td><td>PB</td><td>PB</td><td>PM</td><td>PS</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td></tr><tr><td>BS</td><td>PB</td><td>PB</td><td>PM</td><td>PS</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td></tr><tr><td>PS</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td><td>PS</td><td>PM</td><td>PB</td><td>PB</td></tr><tr><td>PM</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td><td>PS</td><td>PM</td><td>PB</td><td>PB</td></tr><tr><td>PB</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td><td>PS</td><td>PS</td><td>PM</td><td>PB</td></tr></table></body></html>

![](images/d996de3f2aea1e1ba3f86f6a88a150922231dd49378052066dfbc253eb19d3c8.jpg)  
图5功率变化量 $\boldsymbol { \mathscr { e } }$ 的隶属函数

# 4 光伏发电系统的仿真

# 4.1光伏系统仿真模型

光伏发电系统由PV模块、MPPT模块和控制电路模块三部分组成。仿真电路图如图8所示。

图8中，Transportdelay为延迟环节，实现系统一个采样周期的延迟。PV模块是由多个光伏电池组成的光伏阵列，本文选择Solarex $\mathrm { M S x } 6 0 ~ 6 0 \mathrm { W }$ 光伏电池阵列，在标准测试条件下，即光照强度$1 \ 0 0 0 \mathrm { W / m } ^ { 2 }$ ，温度为 $2 5 \mathrm { { ^ \circ C } }$ ，其基本参数见表2。PV模块与控制电路模块的模型均根据前文的公式搭建。负载为 $1 0 0 \Omega$ ，量化因子 $K _ { \mathrm { e } }$ 为0.01， $K _ { \mathrm { a } }$ 为200，用模糊控制器来实现MPPT的控制。

![](images/5ef00b5f270d4d95542112e22566cb28ab90fcc93859b8cbe637f320f5fb0197.jpg)  
图6 $n { - } 1$ 时刻步长调整值 $a ( n { - } 1 )$ 的隶属函数

![](images/476f8231e1746603c64917740d7a158c344d9c3a4254b343352bd0cc115b2eb9.jpg)  
Fig.6Membership function of $\left( n \mathrm { - } 1 \right)$ time step adjustmeni   
图7 $n$ 时刻步长调整值 $a ( n )$ 的隶属函数 Fig.7Membership function of $( n )$ time step adjustment value $a ( n )$

![](images/b71f631ddf45f7268eb6eab9e8df3150d390a0e2866b1dcd215df015a1461a79.jpg)  
Fig.5Membership function of power variation $e$   
图8光伏系统仿真电路图  
Fig.8Photovoltaic system simulation circuit

表2Solarex $\mathrm { M S x } 6 0 6 0 \mathrm { W }$ 标准测试条件下参数Tab.2Solarex $\mathrm { M S x } 6 0 6 0 \mathrm { W }$ parameters under standardtest conditions  

<html><body><table><tr><td>参数</td><td>典型值</td></tr><tr><td>最大功率Pm/W</td><td>59.9</td></tr><tr><td>峰值工作电流Im/A</td><td>3.5</td></tr><tr><td>峰值工作电压Um/V</td><td>17.1</td></tr><tr><td>短路电流Isc/A</td><td>3.74</td></tr><tr><td>开路电压Uoc/V</td><td>21.0</td></tr><tr><td>短路电流温度系数K/(mA/℃)</td><td>2.06</td></tr><tr><td>开路电压温度系数KT/(V/C)</td><td>-0.07</td></tr></table></body></html>

本文采取的是模糊控制与自适应步长相结合的MPPT算法，为了证明自适应步长调整法比其他方法能更加快速有效地实现光伏发电系统最大功率点跟踪的控制，本文还搭建了定步长调整法以及传统的变步长调整法的仿真模型，在同样的外界环境下(光照强度 $1 \ \mathrm { 0 0 0 W / m } ^ { 2 }$ ，环境温度 $2 5 \mathrm { { ^ \circ C } }$ )，与模糊控制法下的自适应步长调整法进行仿真结果的对比，仿真电路图如图9所示。

# 4.2仿真结果分析

模糊控制与自适应步长相结合算法的输出功率的仿真结果如图10所示。由仿真结果可知，当时间为0.015s时，系统输出最大功率，此时功率值为$1 \ 1 2 0 \mathrm { W }$ 左右。这说明经过模糊控制器的控制可使光伏发电系统迅速平稳地跟踪到最大功率点，并且在最大功率点几乎没有波动。

图9三种步长算法仿真电路图  
![](images/ac948013e257fdd893dad5ef3fdc8bf71a8b2c3fc6c007e60103eb22d7607e07.jpg)  
Fi.9Three step size algorithm simulation circuit

![](images/0aa5b0168ad647cc5b8e072e1e7c931071282f310b437390c716dc78759c00e8.jpg)  
图10输出功率 $P$ 变化曲线 Fig.10Output power $P$ curve

三种步长算法的仿真结果对比如图11所示。

通过图11可知，定步长算法实现的MPPT要经过0.15s才能完成，传统变步长算法要经过0.035s以后可以实现，已经快于定步长算法，而自适应步长调整法仅用了0.015s就实现了系统的最大功率点跟踪控制，明显优于前两种算法，并保证了系统良好的稳定性。

![](images/8a3be67e96432ec6cfd5bc5d9da6b51022508afd025ac2238917afd8480ef4c5.jpg)  
图11仿真结果对比图  
Fig.11Comparison of simulation results

# 5 结论

光伏发电系统是一个高度非线性系统，也很难用精确的数学模型来描述，因此采用模糊控制的方法进行光伏电池的最大功率点跟踪能有效弥补传统控制方法的不足。

本次设计用MPPT模糊控制器通过控制升压电路的占空比来调节光伏发电系统的输出功率，并采用了自适应步长调整法，使系统可以自动调整步长的变化量，为了证明这种步长算法的优化性，搭建了三种步长调整方法的仿真模型，将定步长调整法、传统变步长调整法以及自适应步长调整法的控制结果进行比较，在同样的外界环境条件下观察系统的输出波形。仿真结果表明，自适应步长调整法能明显优于其他两种算法的控制效果。因此，基于模糊控制的自适应步长调整法的最大功率点跟踪控制能使光伏发电系统快速达到最大功率点，并维持稳定的输出，保证系统一直工作在最佳状态。

# 参考文献

[1] 胡海峰．基于模糊PID控制的太阳能光伏发电系统的MPPT研究[D]．长沙：湖南大学，2011.  
[2] 葛丽芳，吴晓波，赵梦恋．基于固定电压法的太阳电池MPPT系统[J]．微电子技术，2008，38(5)：703-707.Ge Lifang,Wu Xiaobo,Zhao Menglian.Solar cellMPPT system based on fixed voltage method[J].Microelectronic Technology,2008,38(5): 703-707.  
[3] 丁倩．基于FPGA的MPPT控制技术研究[D]．西安：西安科技大学，2011.  
[4] 任玲，宗灶童．扰动观察法实现太阳能电池最大功率跟踪控制[J]．工业仪表与自动化装置，2010，66(2): 42-44.Ren Ling, Zong Zaotong. Maximum power trackingcontrol of solar cell by disturbance observer[J].Industrial Instrumentation and Automation,2010,66(2): 42-44.  
[5] 杨金焕．太阳能光伏发电应用技术[M]．北京：电子工业出版社，2009.  
[6] 胡义华，陈昊，徐瑞东，等．一种两阶段变步长最大功率点控制策略[J]．电工技术学报，2010,25(8): 161-166.Hu Yihua, Chen Hao, Xu Ruidong, et al. A two stagevariable step size maximum power point controlstrategy[J]. Transactions of China ElectrotechnicalSociety,2010,25(8): 161-166.  
[7] 黄瑶，黄洪全．电导增量法实现光伏系统的最大功率点跟踪控制[J]．现代电子技术，2008，58(22):18-19.Huang Yao, Huang Hongquan. Maximum powerpoint tracking control of photovoltaic system byconductance increment method[J]. Modern ElectronicTechnology,2008, 58(22): 18-19.  
[8] 王勉华，王小亮，韩琦．新型MPPT算法在光伏并网系统中的应用[J]．电子技术应用，2012,38(11): 73-76.Wang Mianhua,Wang Xiaoliang,Han Qi.Application of new MPPT algorithm in photovoltaicgrid connected system[J]. Application of ElectronicTechnology,2012,38(11): 73-76.  
[9] 连瑞娜．独立光伏发电系统MPPT的模糊 PID控制研究[D]．武汉：武汉理工大学，2011.  
[10]MukerjeA K e, Dasgupta N. DC power supply used asphotovoltaic simulator for testing MPPT algorithms[J].Renewable Energy,2007,25(6): 587-592.  
[11] 黄克亚．光伏发电系统最大功率点跟踪算法研究及实现[D]．江苏：苏州大学，2010.  
[12]Mao Meiqin, Yu Shijie,Su Jianhui. Versatile matlabsimulation model for photovoltaic array with MPPTfunction[J]. Journal of System Simulation, 2005,17(5): 1248-1251.  
[13]Kwon JungMin, Choi WooYoung,KwonBongHwan. Multi-mode MPPT control for improvedefficiency[C]. IEEE International Conference onSustainable Energy Technologies, 2008: 140-143.  
[14]丁天启，谷彩连．基于定步长扰动观察法的光伏电池最大功率点跟踪仿真[J]．沈阳工程学院学报：自然科学版，2016，12(1)：61-64.Ding Tianqi,Gu Cailian.Simulation of maximumpower point tracking of photovoltaic cells basedon fixed step perturbation method[J]. Journal ofShenyang Institute of Engineering:Natural ScienceEdition,2016,12(1): 61-64.  
[15] 王亚楠，杨旭红，王军成，等．一种新型变步长光伏最大功率点跟踪控制策略[J]．电气传动，2015,45(1): 54-57.Wang Yanan,Yang Xuhong,Wang Juncheng,et al.One novel variable step size strategy of MPPT forphotovoltaic system[J].Electric Drive,2015,45(1):54-57.  
[16] 潘东昱，张自强，董燕．两种光伏MPPT的算法及仿真实验[J]．实验室研究与探索，2013，32(1)：52-56.Pan Dongyu,Zhang Ziqiang,Dong Yan. Twokinds of algorithm and simulation experiment ofphotovoltaic MPPT[J].Laboratory Research andExploration,2013,32(1):52-56.  
[17] 叶秋香．光伏电池最大功率跟踪器的模糊控制及其应用[D]．上海：东华大学，2006.  
[18] Mu Yun,Hou Li.Design and simulation of twokinds of fuzzy PID controller based on matlab[J].Mechanical and Electronic,2007,29(6): 70-72.  
[19] Chen Jun,Hui Jing.Study on MPPT for photovoltaicgeneration based on fuzzy-control strategy[J].Modern Electronic Technology,2009,60(2):182-185.  
[20] 张礼胜，李全．基于模糊控制的光伏电池MPPT的设计[J]．现代电子技术，2009，32(15)：165-167.Zhang Lisheng,Li Quan.Design of photovoltaic cellMPPT based on fuzzy control[J].Modern ElectronicTechnol0gy,2009,32(15): 165-167.