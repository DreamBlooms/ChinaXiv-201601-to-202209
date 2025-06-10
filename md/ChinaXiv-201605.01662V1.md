HuYun,ZhouBin,ZhaoHua.Researchofthefront-endsignalprocesingcircuitforthemagnetosphericelectricfeldinstrument (in Chinese). Chin. J. Space Sci., 2015,35(1):104-109,doi:10.11728/cjss2015.01.104

# 磁层电场仪前端信号处理电路研究

胡云¹周斌²赵华1

1(南京航空航天大学航天学院南京 210016)

2(中国科学院空间科学与应用研究中心北京 100190)

摘要针对磁层稀薄等离子体环境中的电场测量，设计了一种电场仪前端信号处理电路方案．双探针电场仪通过向等离子体输出驱动电流，测量两探针间的电位差，从而测量空间电场的探测仪器．在磁层稀薄等离子体环境下，等离子体阻抗较高，电场仪探针将工作在较高的工作电压上.若探针电压接近或超过电路耐压值，则可能会影响探测结果，甚至损坏电场仪.本文结合低偏置电流的电压跟随方案和反馈悬浮电源控制方案，解决了稀薄等离子体环境中电场测量的弱电流采样和高动态电位处理问题，并采用低噪声元件和特殊电路设计，控制电路噪声.测试结果显示,本方案可使探针适应 $\pm 1 0 0 \mathrm { V }$ 的悬浮电位,实现 $1 5 0 \mathrm { k H z }$ 带宽的电场信号测量，且噪声小于 $1 4 \mathrm { n V \cdot m H z ^ { - 1 / 2 } }$ ，满足目前空间电场仪测量精度需求.

关键词磁层，电场探测，低噪声，悬浮电源 中图分类号P354,V1

# Research of the Front-end Signal Processing Circuit for the Magnetospheric Electric Field Instrument

HU Yun1 ZHOU Bin² ZHAO Hua1

1(College of Astronautics,Nanjing University of Aeronautics and Astronautics,Nanjing 210016)   
2(Center for Space Science and Applied Research,Chinese Academy of Sciences,Beijing 100190)

AbstractA kind of front-end signal processng circuit of the electric field instrument,which would be used in the Earth's magnetosphere measurement, is investigated and presented in this work. The double-probe electric feld instrument outputs drive current to the ambient plasma environment, and measures the potential difference between the two probes to detect the electric field.Plasma impedance of the magnetosphere is high,so the probe of the electric field instrument will operate in a high voltage to match the electric current requirement.When the operating voltage is close to or surpasses the circuit threshold voltage,the measuring results would be affected,and the instrument will be possibly damaged. This paper adopts voltage scheme with low bias current and feedback foating power supply control scheme, to solve the weak current sampling problem and high dynamic potential handling problem in measuring the electric field of a thin plasma.Test results show that the circuit can make the probe adapt to the floating ground in the dynamic voltage range of $\pm 1 0 0 \mathrm { V }$ ， and measure the electric feld from DC to $1 5 0 \mathrm { k H z }$ ，with a low noise level below $1 4 \mathrm { n V \cdot m H z ^ { - 1 / 2 } }$ ， which meets the needs of electric field measurements in magnetosphere.

Key wordsMagnetosphere, Electric field detection, Low noise, Floating power supply

# 0 引言

# 1电流驱动式双探针电场探测原理

电场是研究空间物理的基本参数之一，其与空间磁场一起影响到带电粒子的运动和等离子体动力学过程.通过实验探测空间电场对于研究带电粒子运动和各种等离子体波动传播及其相互作用,认知空间区域内各种物理过程和等离子体传输机制有着重要科学意义.

测量等离子体中电场的方法主要分为两种.一种是双探针法，其原理是直接测量电场造成的电位梯度，特点是数据直观，而且测量频带宽 $( \mathrm { D C } \sim \mathrm { M H z } )$ 该技术已被广泛用于各种卫星，例如GOES2,ISEE1,Polar,Freja,Demeter,Themis 等[1-5]．另一种是粒子漂移法，通过测量发射的带电粒子因受 $\pmb { E } \times \pmb { B }$ 影响而产生的漂移轨迹和时间参数来间接测量电场，其特点是能够同时测量磁场和电场，但是测量频带窄( $\mathrm { 1 0 H z }$ 以内).2000年德国发射的CHAMP卫星搭载了粒子漂移计(Digital Ion Drift Meter,DIDM)[6].粒子漂移法被用于验证和补充双探针法而得到发展可以在某些情况下替代双探针法．2000年由欧空局发射的ClusterII同时搭载了双探针电场仪和电子漂移计 (Electron Drift Instrument，EDI)，目的是在各空间区域进行高精度的电场探测[7].

近年来中国在空间电场探测领域的研究不断深入．正在研制的电磁监测试验卫星是中国第一颗近地电磁场科学探测试验卫星，其上部署的电场仪由兰州空间技术物理研究所负责研制[8]．中国科学院空间科学与应用研究中心也进行了空间电场仪的研究，目前正在开展磁层-电离层-热层耦合小卫星星座探测计划．该计划将探测热层、电离层和磁层的电磁场，电场仪是其重要载荷之一．通过对磁层-电离层-热层的电场探测，实现研究平行电场的形成机制、低频等离子体波动对离子加速逃逸的作用和孤立波对粒子的非线性加速过程等科学目标.

双探针电场仪使用电探针测量浸入等离子体中的两点电位，根据电位差和距离计算电场，其工作原理如图1所示[9].图中 $U _ { a } , U _ { b }$ 分别为两个探针的电位， $\varPhi _ { a }$ ， $\varPhi _ { b }$ 分别为两个探针处的等离子体电位， $I _ { b }$ 为驱动电流.

根据理想等离子体分布模型，当探针电位相对于等离子体电位 $U > 0$ 时，电流与电压的关系如下[10]：

$$
\begin{array} { c } { { I = \displaystyle \frac { 1 } { 4 } e n _ { \mathrm { e 0 } } S _ { \mathrm { e } } \sqrt { \frac { 8 k T _ { \mathrm { e } } } { \pi m _ { \mathrm { e } } } } \Big ( 1 + \frac { e U } { k T _ { \mathrm { e } } } \Big ) - } } \\ { { \frac { 1 } { 4 } e n _ { \mathrm { i 0 } } S _ { \mathrm { i } } \sqrt { \frac { 8 k T _ { i } } { \pi m _ { i } } } \exp \Big ( \frac { e U } { k T _ { i } } \Big ) . } } \end{array}
$$

当 $U < 0$ 时，电流与电压的关系为：

$$
\begin{array} { c } { { I = \displaystyle \frac { 1 } { 4 } e n _ { \mathrm { e 0 } } S _ { \mathrm { e } } \sqrt { \frac { 8 k T _ { \mathrm { e } } } { \pi m _ { \mathrm { e } } } } \exp \Big ( \frac { e U } { k T _ { \mathrm { e } } } \Big ) - } } \\ { { \frac { 1 } { 4 } e n _ { \mathrm { i 0 } } S _ { \mathrm { i } } \sqrt { \frac { 8 k T _ { \mathrm { i } } } { \pi m _ { \mathrm { i } } } } \Big ( 1 + \frac { e U } { k T _ { \mathrm { i } } } \Big ) , } } \end{array}
$$

其中, $n _ { \mathrm { e 0 } } , \ n _ { \mathrm { i 0 } }$ 分别为电子和离子数密度; $S _ { \mathrm { e } }$ ， $S _ { \mathrm { i } }$ 分别为探针有效电子表面积和探针有效离子表面积； $k$ 为玻尔兹曼常数; $T _ { \mathrm { e } } , T _ { \mathrm { i } }$ 分别为电子和离子温度, $m _ { \mathrm { e } }$ $m _ { \mathrm { i } }$ 分别为电子和离子质量

![](images/1545dfe4048c5fcf6245f325746a1ec9032150bc0a55f8e66564b9614402e176.jpg)  
图1双探针式电场仪探测原理  
Fig.1Schematic representation of the double probe technique for electric field instrument. $U _ { a }$ ， $U _ { b }$ is the voltage of the probes; $\varPhi _ { a }$ ， $\varPhi _ { b }$ is the voltage of the plasma around the probes; $I _ { b }$ is the bias current

根据式(1）和式(2)，典型等离子体探针 $U { - } I$ 曲线如图2所示.在相同等离子体环境下，等离子体与电探针的耦合对于两个探针是相同的，即两个探针的伏安特性曲线理论上是一致的.因此星上测出的工作在相同电流下的探针电位差 $( U _ { a } - U _ { b } )$ 等于等离子体中两点之间的实际电位差 $\left( \boldsymbol { \phi } _ { a } - \boldsymbol { \phi } _ { b } \right)$ ．电场仪利用这一特点进行电场探测！

探针表面除电子和离子的注入外,表面光电子发射也会影响电场探测的精度.光电子电流近似计算公式如下[11].

当 $U < 0$ 时

$$
I _ { \mathrm { p h o t o } } = I _ { \mathrm { o } } = \pi r ^ { 2 } j _ { \mathrm { p h o t o } } ,
$$

当 $U > 0$ 时

$$
I _ { \mathrm { p h o t o } } = I _ { \mathrm { o } } [ \exp ( - U / 2 ) + 0 . 0 3 7 5 \exp ( - u / 7 . 5 ) ] .
$$

![](images/40b85ccc7611c1e29b65ac1ef1df274096e96f66a3615de5c3db638188990048.jpg)  
图2典型电探针的U-I曲线

其中, $U$ 为探针相对于等离子体的电位， $I _ { \mathrm { p h o t o } }$ 为表面光电子电流, $j _ { \mathrm { p h o t o } }$ 为表面光电子流密度, $\boldsymbol { r }$ 为传感器半径.

对于工作在空间中的探针，在一个长周期内光电子流密度可能会在 $1 . 5 { \sim } 8 \mathrm { n A } { \cdot } \mathrm { c m } ^ { - 2 }$ 的范围内变化[12]．GOES1和GOES2测得的光电子流密度约为 $3 \mathrm { n A } { \cdot } \mathrm { c m } ^ { - 2 [ 2 ] }$ ．假设在地球周围的光电子流密度为 $4 \mathrm { n A } { \cdot } \mathrm { c m } ^ { - 2 }$ ，以 $5 \mathrm { c m }$ 直径的球形传感器为例，每个传感器的光电子电流约为 $8 0 \mathrm { n A } ^ { [ 5 ] }$ .在稀薄的磁层等离子体中,探针与等离子体主要依靠光电子耦合．电场仪探针与周围等离子耦合会产生耦合阻抗．这里对两种典型等离子环境的电流-阻抗进行了仿真，仿真结果如图3所示，

在磁层稀薄等离子体环境下测量电场的特点是当探针驱动电流与光电子电流相当时，耦合阻抗较低 (约 $1 0 ^ { 7 } \Omega$ )，探针工作电压较低；当探针驱动电流与光电子电流偏差较大，耦合阻抗急剧增加，探针工作电压也随之快速升高．因此在磁层等离子体稀薄区域进行电场探测时，探针工作点应设置在耦合阻抗变化缓慢的区域，即驱动电流为 $- 1 0 0 \mathrm { n A }$ 为宜.由于等离子体稀薄区域空间环境变化剧烈，探针电位相对于航天器的动态范围约为 $\pm 1 0 0 \mathrm { V }$ ：为解决上述弱电流采样和高动态电位处理的问题,提出一种基于低偏置电流的电压跟随和反馈悬浮电源控制方案，设计了传感器前端信号处理电路，并严格控制了电路噪声.

![](images/9e366f51ebef390f065d8cab9a51f3b87a0524ebe3375cfa853a020cf5caa05f.jpg)  
Fig.2Typical voltage-current curve for electric probe   
图3典型等离子环境的电流-阻抗曲线.(a)对应电离层-等离子体稠密区域;(b)为仿真目标环境对应磁层远地轨道-等离子体稀薄区域.驱动电流 $8 0 \mathrm { n A }$

Fig.3Typical current-impedance curve of plasma environment.(a) corresponds to the ionosphere-plasma populated area; (b) is the target environment for simulation,corresponding to the magnetosphere at far-earth orbit-plasma thin area.The photocurrent is $8 0 \mathrm { n A }$ （204号

# 2 前端信号处理电路设计方案

# 2.1 总体设计

每个探针基本构造相同，其系统电路如图4所示．等离子体电位信号耦合到敏感探针的外表面，经过探针内部的前置放大器进行阻抗变换和测量，传输到悬浮电源部分、驱动电流部分和信号采集与控制部分.其中悬浮电源是为了前置放大器能够在大动态输入电位下正常工作,其基准跟随探针电位动态浮动，从而保证前置放大器的正常工作

探针与周围等离子体的耦合电阻高,前置放大电路的输入电阻必须远大于等离子体耦合电阻，才能确保测量直流及低频电场的准确度.而且探针信号的驱动能力非常小.假定驱动电流为 $- 1 0 0 \mathrm { n A }$ ，前置放大电路的输入电阻为 $1 0 ^ { 1 2 } \Omega$ ，等离子体耦合电阻为 $1 0 ^ { 7 } \Omega$ ，则放大器漏电流应小于 $1 \mathrm { p A }$ .除此之外，放大电路必须具有宽频带、低输入电容和低噪声电压等特点．在考察各种放大器后，选择OPA128JM作为前置放大器芯片，其相关参数列于表1.

![](images/aebd141efb44013b4ea930e03d1e798d7ecaa24ce0bcd2c715a18b66a37ab87e.jpg)  
图4总体电路

# 2.2 前置放大器设计

探针内部放置前置放大器,其基本原理是跟随电路，如图5所示．当偏流小至pA级时，就不能忽视印制基板、连接器等元件的绝缘材料以及从其表面流过的漏电流，应使用保护环围住OP放大器的反相输入口并将其接地

# 2.3 悬浮电源设计

由前文分析得出，探针电位相对于航天器的动态范围约为 $\pm 1 0 0 \mathrm { V }$ ：如果放大器在以卫星地作为基准的电源下工作，会导致信号饱和甚至击穿．为保障载荷安全，前置放大器采用悬浮电源供电，如图6所示，

![](images/e8e0426ae13614f5d76b436ba72fca57166b76f95211f180201bad0b90c252dc.jpg)  
图5前置放大器电路

![](images/38af101a3f3c20934f0056be61168146c81d31039238b55b42a4d75ee80ae34c.jpg)  
Fig.4Block diagram of the electronics   
Fig.5Diagram of preamplifier circuit   
图6悬浮电源电路  
Fig.6Diagram of floating power

# 表1 OPA128JM主要参数

Table 1 Main parameters of OPA128JM   

<html><body><table><tr><td>输入偏置电流/fA</td><td>共模阻抗</td><td>噪声电压/(nV·Hz-1/2)</td><td>转换速率/(V·μs-1)</td><td>单位增益带宽/MHz 输出阻抗/Ω</td><td></td></tr><tr><td>±150</td><td>1015Ω||2pF</td><td>15</td><td>3</td><td>1</td><td>100</td></tr></table></body></html>

注噪声电压对应噪声为 $1 0 \mathrm { k H z }$

探针电位经过高压电流驱动后进入DC-DC 转换器的二次电源.二次电源与一次电源隔离，可以将探针电位驱动到二次电源的地，将二次电源基准电位设置为探针电位.DC-DC 转换器的开关频率需大于工作频率才能避免对信号的干扰，

# 3试验与分析

这里使用并联的等效电阻 $( 5 0 \mathrm { M } \Omega )$ 、电容 $( \mathrm { 5 } \mathrm { p F } )$ 来模拟电场探测仪在磁层实际探测过程中传感器探针与等离子体环境之间的耦合电阻与耦合电容.通过示波器、数字采集器等测试电路的直流特性、交流特性和噪声特性，从而验证电路的准确性和精确性

# 3.1 直流线性度测试

实验主要目的是测试电场仪输出电压与输入电压的线性关系，评估电场仪线性度并验证量程.用直流电源分别给悬浮电源和输入端供电，改变输入直流电压，测量输出电压，其结果如图7所示，

测试结果显示，在 $\pm 1 0 0 \mathrm { V }$ 范围内，输出电压跟随输入电压浮动,并且与输入电压的线性度为 $1 0 0 . 0 0 \%$ 悬浮电源能为放大器提供浮动电源，保障电路正常工作.

# 3.2 交流频响测试

输入峰峰值为1V的交流正弦电压，调节输入电 压频率，用示波器测量电路输出电压的频率特性，测 试结果如图8所示.

测试结果显示，电路带宽为 $\mathrm { 1 5 0 k H z }$ ；并且在带宽内，输出电压相位滞后小于 $1 8 0 ^ { \circ }$ ，电路反馈稳定，不会发生震荡.

# 3.3 噪声测试

整个电路系统的噪声状况是电场探测的关键指标之一．通过将数字采集器的输入短路，检测设备的噪声底限，测得设备本底噪声约为 $1 0 \mathrm { n V \cdot m H z ^ { - 1 / 2 } }$ 再将电路的输入接地，用数字采集器采集输出端的数据.计算电路的噪声功率谱密度，结果如图9所示

图9中， $5 0 \mathrm { { H z } }$ 处尖峰是测试环境的工频噪声干扰, $8 0 \mathrm { k H z }$ 内噪声约为 $1 0 0 \mathrm { n V { \cdot } m H z ^ { - 1 / 2 } }$ ．电场仪两对称传感器间距离为 $1 0 \mathrm { m }$ ，则电场噪声约为$1 4 \mathrm { n V \cdot m H z ^ { - 1 / 2 } }$

ClusterII卫星电场仪交流噪声约为 $5 0 \mathrm { n V \cdot m H z ^ { - 1 / 2 } }$ 工作频带为 $1 0 0 \mathrm { k H z }$ ，与Cluster $\mathrm { I I }$ 卫星电场仪相比，本文所设计电路的精度有所提高.

![](images/bf36843307e0582ca9ca8c63a3a91cbbf32044d4e19aa6fff42ac313277bf74a.jpg)  
图7输出电压的直流特性  
Fig.7DC characteristics of the output

![](images/4709e91e7a3893b77fe09c21f9220dab3f894405988222346813ea47d4e9c219.jpg)  
图8输出电压的频率响应.(a）幅频特性,(b)相频特性 Fig.8Frequency response of output voltage.(a) Amplitude response,(b） phase response

![](images/52f4c31a6df5969502ee2e98647b4d979a2e782d17df08267691ed7903ec0dbc.jpg)  
图9输出电压高频噪声  
Fig.9High frequency noise of output voltage

# 4结论

空间电场探测可为空间天气研究、日地物理研究提供观测数据,对于推动空间科学的研究和发展具有重大意义.通过分析主要电场探测方法，对磁层等离子体环境特性进行了仿真．在磁层稀薄等离子体环境下，光电子影响显著，探针收集电流小；空间环境变化剧烈，电场仪工作电流一旦没有适应等离子体电流的变化，将导致探针工作点偏移，使探针电位突然显著增高.为能在这种环境下进行电场探测，本文采用低偏置电流的电压跟随方案和反馈悬浮电源控制方案，设计了针对磁层电场探测的电流驱动式双探针电场仪的前端信号处理电路．经测试该电路能适应 $\pm 1 0 0 \mathrm { V }$ 的动态电压，频带宽度为 $\mathrm { 1 5 0 k H z }$ ，噪声为 $1 4 \mathrm { { n V } \cdot \mathrm { { m H z } ^ { - 1 / 2 } } }$ ：

# 参考文献

[1]Heppner JP,Maynard N C,Aggson T L.Early results from ISEE 1 electric field measurements [J].Space Sci. Rev.,1978,22:777-789   
[2] Pedersen A,Cattell C A.Quasistatic electric field measurements with spherical double probes on the GOES and ISEE satellites [J]. Space Sci.Rev.,1984,37:269-312   
[3]Marklund G T,BlombergLG,Lindqvist PA,et al. The double probe electric field experiment on FREJA:Experiment description and first results[J].Space Sci. Rev., 1994，70:483-508   
[4] Harvey P,Mozer F S,Pankow D,Wygant J,et al.The electric field instrument on the POLAR satellite[J].Space Sci. Rev.,1995,71:583-796   
[5]BonnellJW,MozerF S,Delory G T,et al.The Electric Field Instrument (EFI) for THEMIS[J]. Space Sci. Rev., 2008,141:303-341   
[6] Reigber C,Lühr H,Schwintzer P.Announcement of opportunity for CHAMP[R], CH-GFZ-AO-001,2001:24-25   
[7]Eriksson A I,Andr'e M,Klecker B,et al.Electric field measurements on Cluster: comparing the double-probe and electron drift techniques [J].Ann.Geophys.,2006, 24:275-288   
[8] Wang Hongfei,Liu Yurong，Yan Zhen.Research of earthquake electromagnetic satellite mission planning system[J]. Chin.J. Space Sci.,2010,30(6):620-625.In Chinese（王红飞，刘玉荣，阎镇．地震电磁卫星任务规划系统研 究[J].空间科学学报，2010,30(6):620-625)   
[9]Jiao Weixin. Space Probe [M].Beijing:Beijing University Press，2002:273-304.In Chinese（焦维新.空间探测[M].北 京：北京大学出版社，2002:273-304)   
[10] Ding Songhe,Liu Yenan,Zhou Bin.Design of diagnostic instrument for space environment plasma [C]//The 24th Space Probe Academic Exchange Conference. Xi’an: Chinese Society of Space Science,2011． In Chinese（丁 松鹤，刘业楠，周斌．空间环境等离子体诊断仪器设计[C]//第 二十四届空间探测学术交流会议．西安：中国空间科学学会, 2011)   
[11] Fahleson U.Theory of electric field measures conducted in the magnetosphere with electric probes [J].Space Sci. Reu.,1967,7:238-262   
[12] Harri Laakso,Thomas L.Aggson,et al.Plasma gradient effects on double-probe measurements in the magnetosphere [J]．Ann.Geophys.,1995,13(2):130-146