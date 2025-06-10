# K波段常温接收机噪声注入定标方法分析研究

王凯1,2.3，闫浩1,2.3，段雪峰1.3，马军1.2.3，陈卯蒸1,2.3，王洋1,2.3，曹亮1,2.3，

陈晨雨1.2，李鹏1,2

（1.中国科学院新疆天文台，新疆 乌鲁木齐 830011；2.中国科学院射电天文重点实验室,江苏 南京

210008;3.新疆微波技术重点实验室，新疆 乌鲁木齐830011）

摘 要：噪声注入定标方法作为厘米波段一种常规强度校准方式而被广泛使用。通过组建K波段常温接收机及其定标平台，在室内 $2 0 ^ { \circ } \mathrm { C }$ 下使用传统冷热负载法标定接收机噪声温度及噪声源温度，之后在室外 $\mathrm { - 7 ^ { \circ } C }$ 中使用同样方法再次标定上述参数，并利用室内标定的噪声源去进一步标定室外环境中接收机的噪声温度。测试结果表明，在环境温度变化约27度时，接收机噪声温度定标差异约为 $5 0 . 5 \%$ ，标准噪声源定标差异约为 $41 \%$ 。故此得知，如若将噪声注入法应用于常温接收机定标中，首先需考虑对接收机进行恒温处理，另外可采取对注入的标准噪声源进行温度补偿，使其可以更加精确的应用于二次定标当中，这也是本论文下一步计划开展的工作。

关键词：定标；接收机；噪声温度；冷热负载法；噪声注入中图分类号：P111.5；文献标识码：A

射电天文学是利用射电望远镜接收来自射电源的微波信号的观测学科[1]。微波接收机是射电天文重要的观测设备[2。经射电望远镜接收到的射电信号，首先被反射汇聚至接收机系统馈源的相位中心处3，后经低噪声放大器进行放大，并由滤波器滤出需要的工作频段，再与本振信号在混频器端进行混频等相关处理后,最终将中频信号传输至数字终端进行存储[45]，供天文学家进行相关处理。接收机系统的基本组成如图1所示。

![](images/17a2f7237ddf009fa439adfdf7e63dd9863e8796820e2ddcea3a7219cadba3fc.jpg)  
图1接收机系统  
Fig.1Receiversystem

接收机定标就是通过建立一个温度标尺，将其对射电源的强度响应等效的转换为一个温度值，之后再结合天线相关参数最终将其转换为天文意义上的流量密度[7]。一般方法就是用冷热负载法得到一个接收机强度及温度的响应比率 $\mathrm { \Phi _ { g } }$ （公式1），其中，常温黑体负载温度为Tamb，低温黑体负载温度为 $\mathrm { T _ { c o l d } }$ ,常温黑体负载功率输出 $\mathrm { V a m b }$ ,低温黑体负载功率输出Vcold。

$$
g = \frac { V _ { a m b } - V _ { c o l d } } { T _ { a m b } - T _ { c o l d } }
$$

结合这个强度及温度响应比率g，再控制天线对射电源做指向（ON）或者偏开（OFF)操作，得到射电源等效的温度值 $\mathrm { T _ { A } }$ (公式2)，其中指向射电源功率输出为VoN，偏开射电源

功率输出为VOFF。

$$
T _ { _ A } = \frac { V _ { O N } - V _ { O F F } } { g }
$$

最终，结合天线口径 $\mathrm { A } _ { \mathrm { p } }$ 及效率 $\eta _ { \mathrm { A } }$ ，就可以最终得到射电源的流量密度 $\mathrm { S v }$ (公式3)，其中 $\mathrm { ~ k ~ }$ 为玻尔兹曼常数。

$$
S _ { v } = { \frac { 2 \kappa T _ { A } } { \eta _ { A } A _ { p } } }
$$

接收机作为射电望远镜系统最核心的信号接收设备，其最重要的指标是灵敏度。通常使用噪声温度来表征接收机系统的灵敏度，更高的灵敏度意味着接收机可以探测更为微弱的射电信号。一般将接收机自身产生的热噪声称之为接收机的噪声温度，其也就是接收机自身的强度响应经校准后等效的温度值。

# 1接收机定标方法

# 1.1冷热负载法

冷热负载法被认为是接收机定标中最为经典的方法。根据普朗克黑体辐射原理得知，任何物体在不同温度下对外都有一定的热辐射，而且辐射强度和物体温度在一定范围内呈近似线性的关系[8]，冷热负载法正是根据这个原理得来。具体来说，在进行接收机噪声温度测试时，使用两个不同物理温度、宽带的黑体辐射源（如80K 液氮中的低温黑体负载和处于室温中 300K的常温黑体负载)，将它们分别放置在接收机馈源口面（第一级放大器或者混频器的前级)，这样不但可以使黑体负载吸收馈源外侧的微波辐射，还可以使不同温度黑体负载的辐射注入到接收机内部，以此对接收机进行噪声校准。冷热负载法测试如图2所示。

![](images/70bd4c7cdf9e51ba7164c32d5d3089917644ecd8059749ff443740218e5566ff.jpg)  
图2冷热负载法测试  
Fig.2 The test of cold and hot load method

将公式1扩展成为公式4，其中接收机噪声温度为Trec。执行完接收机噪声校准之后，再利用射电望远镜对射电源进行ON/OFF观测，便可以得到射电源等效的温度值，之后再结合天线效率及孔径便可以得到射电源的流量密度。

$$
g = \frac { V _ { a m b } - V _ { c o l d } } { T _ { a m b } - T _ { c o l d } } = \frac { V _ { a m b } } { T _ { a m b } + T _ { r e c } } = \frac { V _ { c o l d } } { T _ { c o l d } + T _ { r e c } }
$$

虽然冷热负载法在业界被公认是最好的接收机定标方式，但其也有一定局限性。主要由于接收机系统一般是安装于射电望远镜的接收机房内，在观测时，接收机会随着射电望远镜在方位及俯仰方向转动，而工程师无法在天线转动过程中采用冷热负载对接收机进行校准，尤其是无法提供冷负载进行校准，因此也就无法得到上述的响应比率 $\pmb { \mathrm { g } }$ 。

# 1.2 噪声注入法

鉴于上述天线观测过程中无法随时进行冷热负载法校准，故从接收机端注入标准噪声的方法被提出。该方法采取在接收机信号链路中注入一个标准的噪声信号（一个脉冲的噪声二极管，也叫噪声源)，观测前，先利用冷热负载法对标准噪声源进行校准，在得到标准噪声源等效的温度值以后，在观测中，使用这个定标后的标准噪声源再对射电源进行二次校准。由于标准噪声源方便在观测过程中随时开启或者关闭，所以该方法在厘米波段接收机定标中被广泛应用。

公式5是接收机标准噪声源 $\mathsf { T } \mathsf { c a l }$ 的计算公式，其中 $\mathsf { V } _ { \mathsf { C a l \_ O N } }$ 为黑体负载下开启噪声源的功率输出，Vcal_OFF为黑体负载下关闭噪声源的功率输出。

$$
T _ { c a l } = \frac { V _ { c a l \_ O N } - V _ { c a l \_ O F F } } { V _ { a m b } - V _ { c o l d } } \cdot \left( T _ { a m b } - T _ { c o l d } \right)
$$

执行完接收机噪声校准之后，再利用射电望远镜对射电源进行ON/OFF 观测，便可以得到射电源等效的温度值，见公式7，以此进一步开展流量密度的计算。

$$
T _ { _ A } = \frac { V _ { O N } - V _ { O F F } } { V _ { c a l \_ O N } - V _ { c a l \_ O F F } } \cdot T _ { _ { c a l } }
$$

噪声注入定标方法一般分为自由空间噪声注入和波导噪声注入两种。图3为自由空间噪声注入方法示意图，其标准噪声源放置在天线副反射面位置，正对向接收机波束方向，经过定标的噪声信号经过自由空间注入到接收机馈源内部进行校准。

![](images/e39152898eefa993e0a366c2837972c3da651c12d27e39a92c9468e2e0e49286.jpg)  
图3自由空间噪声注入模式 Fig.3 Free space noise injection mode

由于自由空间噪声源容易受到外界环境温度变化以及空间信号衰减等因素影响，在厘米波段接收机定标中，更多使用的是波导噪声注入方式。就是将标准噪声信号在接收机馈源的后级经定向耦合器注入到接收机内部[10]，以此建立温度标尺的校准方法。图4 为波导噪声注入方法示意图。

![](images/494c447b94b1b4a4557808b9e265985aa97fcf5c5685ec16299278d2efc35397.jpg)  
图4波导噪声注入模式  
Fig.4Waveguide noise injection mode

噪声注入法很好的解决了冷热负载法不能实时校准的问题，但在接收机系统中引入额外\*基金项目：国家自然科学基金资助项目（11903073，11603064，11973078，11903077）资助新疆维吾尔自治区自然科学基金资助项目（2019D01A99）资助中国科学院“西部之光”人才培养引进计划（2019-XBQNXZ-B-017)中国科学院天文台站设备更新及重大仪器设备运行专项经费支持作者简介：王凯，男，硕士，研究方向：接收机技术。Email:wangkai@xao.ac.cn

的器件，例如为了注入噪声添加的定向耦合器，会对整个系统引入额外的噪声。另外，对于常温接收机来说，同一温度下定标得出的TcaL值，也会在二次校准时由于温度变化而引入一定程度的差异。

# 2系统组建、测试及分析

为了开展厘米波段接收机强度校准相关研究（包括短厘米波段大气不透明度测量)，搭建一个具备噪声注入功能的K波段常温接收机及其测试平台，以便开展接收机噪声注入定标方法的分析与研究。

# 2.1K波段接收机

搭建的K波段常温接收机主要由馈源网络、噪声源、低噪声放大器、滤波器、混频器、介质本振、中频放大器等组成，如图5所示。该接收机射频工作带宽与南山 25 米天线 $^ { [ 9 ] } \mathrm { K }$ 波段制冷接收机工作频段相同 $( 2 2 \mathrm { - } 2 4 . 2 \mathrm { G H z }$ ，且带内包含南山站水汽辐射计23.8GHz测试频点)，采取超外差设计，射频信号经放大、滤波、混频后最终输出为 $3 . 9 5 { - } 6 . 1 5 ~ \mathrm { G H z }$ 的中频信号。为了降低成本，测试系统仅对接收机极化器[10输出的左旋信号进行了处理并开展相关的功率采集，右旋信号则直接在波同转换器后连接了匹配负载。故本文之后所有的测试数据均来自于左旋信号。

![](images/d99e56ea2ed0fecf26866d60eb5be0bd3df4e4df58c9d0cfab50b718390f92c7.jpg)  
图5K波段接收机结构示意图

上述K波段常温接收机馈源网络中的定向耦合器即是专门用于注入标准噪声信号的微波器件，标准噪声源选用NOISEWAVENW18G-15-CS，如图6所示

![](images/f1a2fe51839663318b4c4c97f5bf6e4365574a8302086b2dc31bcfa49dd63249.jpg)  
Fig.5The schematic diagram of K-band receiver   
图6定向耦合器及噪声源  
Fig.6 Directional coupler and noise source

K波段接收机实物如图7所示，将接收机左旋链路中的低噪声放大器及其后级的微波器件安装于一块铝板上，除了有助于整体固定在馈源网络后侧外，也便于各个有源器件的散热。

\*基金项目：国家自然科学基金资助项目（11903073，11603064，11973078，11903077）资助新疆维吾尔自治区自然科学基金资助项目（2019D01A99）资助中国科学院“西部之光”人才培养引进计划（2019-XBQNXZ-B-017）中国科学院天文台站设备更新及重大仪器设备运行专项经费支持  
作者简介：王凯，男，硕士，研究方向：接收机技术。Email:wangkai@xao.ac.cn

![](images/6f2a93df21ec011b89d794072dffd464f16c2360c9f791451b7f5de50b25da77.jpg)  
图7K波段接收机 Fig.7K-band receiver

# 2.2噪声注入法测试

首先，根据噪声级联计算方式，在温度为 $2 2 ^ { \circ } \mathrm { C }$ （室温）时，K波段接收机的噪声温度理论计算结果为406.5K（Eff.T的总和)，见表1所示。

Table1 Theoretical calculation of noise temperature of k-band receiver   

<html><body><table><tr><td>Gain(dB)</td><td>T(K)</td><td>NF(dB)</td><td>NoiseT(K)</td><td>Eff.T(K)</td></tr><tr><td>Mylar</td><td>-0.05</td><td>298 0.05</td><td>3.5</td><td>3.45</td></tr><tr><td>Feed</td><td>-0.2</td><td>298</td><td>0.2 14</td><td>14.21</td></tr><tr><td>OMT</td><td>-0.07</td><td>298 0.07</td><td>4.8</td><td>5.13</td></tr><tr><td>WCC</td><td>-0.4</td><td>298 0.4</td><td>28.8</td><td>30.9</td></tr><tr><td>LNA</td><td>30</td><td>298 3</td><td>296.6</td><td>350.07</td></tr><tr><td>10dB</td><td>-10</td><td>298 10</td><td>2682</td><td>3.17</td></tr><tr><td>Amp</td><td>30</td><td>298 3</td><td>296.6</td><td>3.5</td></tr><tr><td>BPF</td><td>-0.7</td><td>298</td><td>0.7 52.1</td><td>0.001</td></tr><tr><td>3dB</td><td>-3</td><td>298 3</td><td>296.6</td><td>0.004</td></tr><tr><td>Mixer</td><td>-8</td><td>298 8</td><td>1582.3</td><td>0.044</td></tr><tr><td>BPF</td><td>-0.5</td><td>298 0.5</td><td>36.4</td><td>0.006</td></tr><tr><td>Amp</td><td>30</td><td>298</td><td>3 296.6</td><td>0.058</td></tr></table></body></html>

在室温环境下，利用冷热负载法开展5组测试来标定K波段常温接收机的噪声温度及标准噪声源温度。5组噪声注入法测试数据和计算结果，以及与理论计算噪声温度（ $2 0 ^ { \circ } \mathrm { C }$ 下理论计算接收机噪声温度为403.7K）的比对误差，见表2。其中，Vamb_cal_oN为当常温黑体负载覆盖在接收机馈源口面、开启噪声源时，接收机对应的功率输出，Erec为冷热负载法测试出的Trec与K波段接收机在对应环境温度下噪声温度理论计算值的相对误差。

表1K波段接收机噪声温度理论计算  
表2室内测试数据及比对结果  

<html><body><table><tr><td colspan="7">Table2 Test data and comparison results for indoor</td></tr><tr><td>Tamb (℃)</td><td>Vamb (uW)</td><td>Tcold (℃)</td><td>Vcold (uW)</td><td>Vamb_cal_ON (uW)</td><td>Tcal (K)</td><td>Trec (K)</td><td>Erec (%)</td></tr><tr><td>20.6</td><td>74.35</td><td>-194.3</td><td>51.6</td><td>91.77</td><td>164.6</td><td>408.6</td><td>1.2</td></tr><tr><td>20.3</td><td>72.86</td><td>-194.3</td><td>51.07</td><td>89.64</td><td>165.3</td><td>424.1</td><td>5.1</td></tr><tr><td>19.9</td><td>72.69</td><td>-194.2</td><td>50.94</td><td>89.22</td><td>162.7</td><td>422.5</td><td>4.6</td></tr><tr><td>20.2</td><td>72.53</td><td>-194.2</td><td>50.71</td><td>88.76</td><td>159.4</td><td>419.3</td><td>3.9</td></tr><tr><td>19.8</td><td>72.26</td><td>-194.4</td><td>50.61</td><td>88.54</td><td>161.1</td><td>422</td><td>4.5</td></tr></table></body></html>

之后在室外环境下，利用冷热负载法同样开展了5组测试来标定K波段常温接收机的噪声温度及标准噪声源的温度值。5组噪声注入法测试数据和计算结果，以及与理论计算噪声

\*基金项目：国家自然科学基金资助项目（11903073，11603064，11973078，11903077）资助新疆维吾尔自治区自然科学基金资助项目（2019D01A99）资助中国科学院“西部之光”人才培养引进计划（2019-XBQNXZ-B-017）中国科学院天文台站设备更新及重大仪器设备运行专项经费支持  
作者简介：王凯，男，硕士，研究方向：接收机技术。Email:wangkai@xao.ac.cn

# 温度（ $- 7 ^ { \circ } C$ 下理论计算接收机噪声温度为366.5K）的比对误差，见表3。

<html><body><table><tr><td colspan="7">Table3 Test data and comparison results for outdoor</td></tr><tr><td>Tamb (℃)</td><td>Vamb (uW)</td><td>Tcold (℃)</td><td>Vcold (uW)</td><td>Vamb_cal_ON (uW)</td><td>Tcal (uW)</td><td>Trec (K)</td><td>Erec (%)</td></tr><tr><td>-6.5</td><td>126.94</td><td>-193.6</td><td>89.67</td><td>172.89</td><td>230.7</td><td>370.6</td><td>1.1</td></tr><tr><td>-6.8</td><td>124.74</td><td>-193.7</td><td>88</td><td>170.37</td><td>232.1</td><td>368.2</td><td>0.5</td></tr><tr><td>-7.2</td><td>124.02</td><td>-194</td><td>87.18</td><td>168.96</td><td>227.9</td><td>362.9</td><td>1</td></tr><tr><td>-6.5</td><td>117.57</td><td>-193.8</td><td>82.71</td><td>160.38</td><td>230</td><td>365</td><td>0.4</td></tr><tr><td>-7.3</td><td>116.57</td><td>-194.3</td><td>81.77</td><td>159.04</td><td>228.2</td><td>360.5</td><td>1.6</td></tr></table></body></html>

# 2.3测试数据分析

首先利用表2的5组室内冷热负载法的测试数据，对该方法测试接收机的噪声温度的精度进行了评估[]，5 组测量精度分别为 $4 . 7 1 \%$ 、 $5 . 0 6 \%$ 、 $5 . 0 6 \%$ 、 $5 . 0 1 \%$ 和 $5 . 0 7 \%$ 。之后，通过冷热负载法测试的接收机噪声温度与理论计算值进行对比，室内测试误差在 $1 . 2 \AA ^ { - 5 . 1 \% }$ 之间，室外测试误差在 $0 . 5 \mathrm { - } 1 . 6 \%$ 之间，从而也验证了该经典定标方法完全满足噪声温度测试需求（误差在 $1 0 \%$ 以内）。

公式7为已知标准噪声源温度值的情况下，根据Tcal值去求解接收机噪声温度的计算方法。从公式中我们可以看到，除Tcal值以外，还需要结合常温（或者低温）黑体的温度及对应的功率输出。

$$
\frac { V _ { c a l \_ o N } - V _ { c a l \_ o F F } } { T _ { c a l } } = \frac { V _ { a m b } } { T _ { a m b } + T _ { r e c } } = \frac { V _ { c o l d } } { T _ { c o l d } + T _ { r e c } }
$$

利用表3中常温黑体定标时的测试数据，使用室内环境（ $2 0 ^ { \circ } \mathrm { C }$ ）下标定的标准噪声源温度值（取自表2中Tcal的平均值162.6K)，去二次标定室外环境 $( - 7 ^ { \circ } \mathrm { C } )$ 的接收机噪声温度，可以得到室外低温环境下标准噪声源温度及接收机噪声温度的测试差异，如表4所示。

表3室外测试数据及比对结果  
表4室外噪声注入方法测试数据及比对结果  
Table4 Test data and comparison results of noise injection method for outdoor   

<html><body><table><tr><td>Tamb （℃)</td><td>Vamb (uW)</td><td>Vamb_cal_ON (uW)</td><td>Tcal (uW)</td><td>Ecal (%)</td><td>Trec (K)</td><td>Erec (%)</td></tr><tr><td>-6.5</td><td>126.94</td><td>172.89</td><td>230.7</td><td>41.9</td><td>182.7</td><td>50.2</td></tr><tr><td>-6.8</td><td>124.74</td><td>170.37</td><td>232.1</td><td>42.7</td><td>179.3</td><td>51.1</td></tr><tr><td>-7.2</td><td>124.02</td><td>168.96</td><td>227.9</td><td>40.2</td><td>182.9</td><td>50.1</td></tr><tr><td>-6.5</td><td>117.57</td><td>160.38</td><td>230</td><td>41.5</td><td>180</td><td>50.9</td></tr><tr><td>-7.3</td><td>116.57</td><td>159.04</td><td>228.2</td><td>40.3</td><td>180.6</td><td>50.7</td></tr></table></body></html>

# 3总结

本论文通过组建K波段常温接收机及其校准平台，在其上开展接收机噪声注入定标方法分析与研究。首先在室内环境 $2 0 ^ { \circ } \mathrm { C }$ 下，使用传统冷热负载法测试接收机噪声温度，并标定K波段接收机标准噪声源温度；然后将K波段接收机放置于室外环境 $. 7 \mathrm { ^ { \circ } C }$ 下，待接收机物理温度与环境温度相当时，再次使用传统定标方法获取接收机噪声温度及噪声源温度；之后利用室内环境标定的噪声源温度，结合常温黑体下切换噪声源通断，可以得到室外环境下使用噪声注入定标方法测试的接收机噪声温度。测试结果表明，在环境温度变化近27K时，标准噪声源温度差异约为 $41 \%$ ，经其二次标定的接收机噪声温度差异约为 $5 0 . 5 \%$ 。故此得知，常温接收机采取噪声注入定标方法需在环境温度相对稳定的前提下进行，例如采取类似制冷接收机低温杜瓦的方式，对接收机尤其是低噪放及其前级器件进行恒温处理。当环境温度变化范围较大时，考虑到可行性，最好采取实时校准的方式以减小误差，例如斩波轮法。未来拟开展不同环境温度下噪声注入方式的误差分析，期望以此对注入的标准噪声源温度进行补偿，使之对二次标定的接收机噪声温度或者射电源等效温度的误差在可以接受的范围。最终，希望相关的研究也可为新疆天文台QTT项目厘米波段接收机定标做技术参考。

# 参考文献

[1］王娜．新疆奇台110 米射电望远镜［J]．中国科学：物理学力学天文学，2014,44(8) :783-794.  
[2]陈卯蒸,刘奇，马军,王娜.大口径射电望远镜超宽带接收机技术发展[J].中国科学:物理学力学 天文学,2017,47(05):35-47.  
[3]项斌斌,王从思,王伟,等.基于机电耦合的反射面天线副面位置调整方法[J].系统工程与电子技术,2018，40(3):489-497.  
[4]马军,裴鑫,王娜,李健,王凯,刘艳玲.QTT 超宽带多波束信号接收与处理系统［J].中国科学：物理学 力学天文学,2019,49(09):6-18.  
[5]张海龙,朱艳,聂俊,袁建平,吴刚,刘俊,王杰,王万琼,冶鑫晨,托乎提努尔,张萌.新疆天文台 NSRT 观测数据存储系统［J].天文研究与技术,2018,15(02):181-187.  
[6]王凯,陈卯蒸,李笑飞,李健,项斌斌,闫浩,王洋.Ku 波段接收机噪声温度测试及分析［J].电子机械工程, $2 0 1 8 , 3 4 \left( 0 6 \right) : 1 3 - 1 6 + 2 1$   
[7]王凯,陈卯蒸,马军,李笑飞,闫浩,项斌斌.射电天文毫米波接收机强度校准[J].天文学报,2018,59(05) :3-16.  
[8]韩克祯,耿雪,张芳,葛筱璐,刘晓娟,秦华.关于黑体辐射曲线顶点问题的讨论[J].物理通报,2018(10):115-118.  
[9]陈勇,孙正文,闫浩,李健,李大磊,李笑飞,刘烽.新疆天文台26米望远镜L波段接收机线-圆偏振的转换［J」.天文研究与技术,2019,16(03):262-267.  
[10]陈卯蒸,马军，覃律，等.Q波段脊过渡正交模耦合器设计[J]．电子科技大学学报，201847(2): 178-182.  
Analysis and Research on Noise Injection Calibration Method of K-bandAmbient Temperature Receiver  
WANG Kai123,，YANHao2，UAXuefeng,AJun2,，CHENMaozheng,，WANGYangCAOLiang1:23,CHEN Chenyu12,LIPeng1.2

(1.Xinjiang Astronomical observatory, Chinese Academy of Sciences, Xinjiang, Urumqi, 830011, China;2.Key Laboratory of Radio Astronomy, Chinese Academy of Sciences,Nanjing 21o08, China;3.Key Laboratory of Microwave Technology, Xinjiang Uygur Autonomous Region, Xinjiang, Urumqi, 830011)

Abstract :Noise injection calibration method is widely used as a conventional amplitude calibration method in centimeter band receiver. Through the establishment of K-band ambient temperature receiver and its amplitude calibration platform,the traditional cold and hot load method is used to calibrate the receiver noise temperature and noise source temperature at indoor temperature of $2 0 ^ { \circ } \mathrm { C }$ ，and then the same method is used to calibrate the receiver noise temperature and noise source temperature at outdoor temperature of $- 7 ^ { \circ } \mathrm { C }$ ，and the indoor calibrated temperature noise source is used to further calibrate the receiver noise temperature in outdoor environment.The test results show that when the ambient temperature changes about 27 degrees, the difference of receiver noise temperature calibration is about $5 0 . 5 \%$ ，and the difference of standard noise source calibration is about $41 \%$ .Therefore,if the noise injection method is applied to the calibration of ambient temperature receiver, the receiver should be treated with constant temperature first，and the injected standard noise source can be compensated with temperature to make it more accurately applied to the secondary calibration, which is the next work of this paper.

Key Words: Calibration; Receiver; Noise temperature; Cold and hot load method; Noise injection