# 射电天文接收机四通道均衡放大模块研制

宁云炜1.2.3，闫浩1.2.3，曹亮1.2.3，马军1.2.3，李笑飞1.2.3，刘峰1.2.3，陈勇1.2.3(1.中国科学院新疆天文台，新疆 乌鲁木齐 830011；2.中国科学院射电天文重点实验室，江苏 南京 210008；3.新疆微波技术重点实验室，新疆 乌鲁木齐 830011)

摘要：射电天文接收机中频系统是接收机的重要组成部分，接收机的L、S、C、K波段的左圆极化和右圆极化信号在高频仓通过下变频成为中频信号。中频信号通过同轴电缆传送到观测室。观测室距离射电望远镜高频仓较远，因此线损较大，且不同频率的信号损耗不同，频率越高损耗越大，导致中频信号功率较小且增益平坦度随频率增加而降低。设计了四通道均衡放大模块，提高中频信号增益并补偿增益平坦度。该模块的均衡器采用了集总元件和微带线相结合的方式，具有结构紧凑、易于集成、成本低的优点。测试结果表明，在6倍频带宽内，均衡量≥8dB，均衡后功率平坦度 ${ \leq } 3 . 5 \mathrm { d B m }$ ，回波损耗<-15dB，满足了射电天文中频检测系统的要求。

关键词：均衡器；放大模块；接收机； 射电天文；阻抗匹配中图分类号：TN81 文献标识码：A 文章编号：1

# 0 引言

新疆天文台南山25米射电望远镜建成于1993年，2016年对25米射电望远镜进行了整体改造升级，改造后天线口径为26米。改造后的26米射电望远镜主要工作在L、S、C、K频段。射电天文接收机位于26米双反射面天线的副反射面后的馈源仓，从馈源接收到的高频信号通过接收机的下变频器变为中频信号。中频信号通过同轴电缆从馈源仓连接到监控室。因为同轴电缆距离较长，导致中频信号线损较大，且不同频段的中频信号经过馈线时，线损不同，导致中频信号在输出功率在每个频点不一样。为了弥补同轴电缆的损耗和维持中频信号的增益平坦性，且中频信号需要等功率分成四路输出，其中三路信号分别进入脉冲星消色散终端、VLBI系统终端和连续谱观测终端，另外一路急如中频监视模块，如图1所示。因此需要四通道均衡放大模块提供经过均衡后的输出功率曲线。

2018年，南山25米射电望远镜更换了新的中频电缆，更换的电缆规格为安德鲁LDF4-50A$2 { \times } 5 4$ 米和迈可博 ${ \mathrm { H } } 0 8 2 { \times } 3 0 $ 米，在100MHz-600MHz频段，新中频电缆的插损是原电缆的一半。为了对新电缆传输的中频信号的功率进行均衡放大，需要研制新的均衡放大模块，以满足射电天文接收机中频系统的要求。

![](images/aae25397ff0b62d2b00d173096d45e2b248007936d1dc8e64e3e68d38c3266a1.jpg)  
图1中频系统框图

# 1总体方案设计

南山26米射电望远镜各频段中频信号经过同轴电缆后的线损如图2所示，从系统整体规划的角度出发，首先考虑如何实现系统整体性能的最优化，再根据单元组件的具体指标需求，结合单元组件选择最优的设计方案。

# 1.1均衡放大模块链路设计

四通道均衡放大模块首先要实现中频信号的功率均衡和放大，由图2可知，在L、S、C、K四个频段的中频信号中，K频段右旋极化的功率信号斜率最大，最高功率和最低功率的插值为9dBm。S频段左旋极化的信号功率斜率最小，插值为3dBm。如果把均衡电路置于功率

![](images/2291a18ebc04bf8cd5a54087c764e89a2785f5fddd5033137d78cace57bf8c26.jpg)  
Fig.1Block diagram of intermediate frequency system   
图2南山26米射电天文接收机各频段中频信号线损

Fig.2IF signal line loss in each frequency band of nanshan $2 6 \mathrm { m }$ radio astronomy receiver

放大器之后[1]，放大器的功率放大效能会进一步增加各频段的斜率[2]，导致均衡器的设计难度增加[3]，因此把均衡器置于功率放大器之前。要实现四通道输出，需要在功率放大器后再加一个1分4功率分配器，整个链路如图3所示。

![](images/36eb23fe403b0e779ac056aeb4aa1526c0259c09c91eaeecdcecac4ddae522fe.jpg)  
Fig.3 the block diagramofFour-channel equalized amplifiermodule

# 1.2链路本身的功率平坦度

均衡放大模块最核心的功能是对中频信号经过线损的功率平坦度进行补偿，均衡放大模块里的功率放大器和功率分配器两个器件本身特性也会对功率平坦度产生影响，这在考虑用均衡电路对中频信号的功率平坦度进行补偿时，必须考虑进去[4。本设计采用的功率放大器为Minicircuit公司的GVA- ${ \cdot 6 0 + }$ ，工作频率为10MHz-5000MHz，在整个频带内具有较好的增益平坦度。但是由于放大器本身的米勒效应，导致放大器在中频 $1 0 0 \mathrm { M H z - 6 0 0 M H z }$ 内的增益平坦度还是不一致，并和线损的增益平坦度呈现相同的趋势，低频增益大，高频增益小。功率放大器的增益如图4所示。功率分配器采用的Minicircuit公司的JS4PS- $\cdot 1 \mathsf { W } +$ ，工作频率为5MHz-1000MHz。功率分配器1路通道输入，4路通道输出，4个通道的插损损耗如图5。

![](images/23b57500564e7bcc5365e6e6d4f15837f94962217b9a6ebd7983bcc983ce54f7.jpg)  
图3四通道均衡放大模块链路框图  
图5功率分配器插入损耗   
Fig.5 Power Divider insertion loss

![](images/66ca902c284f8afcaaf8e1d2ee6749e1c0d006c2f0faab29fdd51e9a65f99e0f.jpg)  
图4功率放大器增益  
Fig.4 Power amplifier gain

# 2总体方案设计

均衡器是四通道均衡放大模块最核心的器件。射频均衡器按照是否需要供电来区别，可以分为有源和无源均衡器，一般工程上采用无源均衡器较多。

常用的无源均衡器从结构上可以分为波导型、同轴型和微带型[6-9]，表1比较了三种类型的均衡器的特性。本设计首先排除了同轴和波导均衡器，这两种均衡器体积大、重量重且不

# 表1无源均衡器比较

Tab.1 Passive equalizer comparison   

<html><body><table><tr><td></td><td>Microstrip equalizer</td><td>Coaxial equalizer</td><td>Waveguide equalizer</td></tr><tr><td>Bearing power</td><td>small</td><td>big</td><td>very big</td></tr><tr><td>Integration</td><td>high</td><td>low</td><td>low</td></tr><tr><td>Design difficulty</td><td>easy</td><td>difficult</td><td>difficult</td></tr><tr><td>Cost</td><td>low</td><td>high</td><td>high</td></tr><tr><td>Volume and Weight</td><td>small</td><td>medium</td><td>big</td></tr></table></body></html>

易集成。微带均衡器成本低、且易于集成，非常适合微波频段的均衡器设计。本设计的均衡器要求工作在中频100MHz-600MHz频段，由于微带均衡器的微带线长度和频率成正比，按照此频段设计的微带均衡器版图面积过大，导致加工成本大幅提高且不易集成。最后综合考虑，本设计采用集总元件和微带线结合的均衡器电路设计[10]。集总元件包括村田公司贴片电容、电感和电阻，微带线除了连接集总元件的作用外，还通过调谐微带线的长度和宽度调谐均衡器的阻抗匹配。这种集总元件和微带线结合的方式，能极大减小电路版图面积，从而降

![](images/adb780a5fcb2bb5c0adc8d978cba394d4bdd5372aebb2c01ecf07f7790b5fc0e.jpg)  
图6计算机优化设计流程  
Fig.6 Computer optimized design process of equalizer circuit topology structure

低加工成本，且易于集成。

2.1均衡器设计的理论分析

均衡器不像其它的无源器件如功分器、耦合器和滤波器等设计理论成熟。均衡器目前理论设计有原型电路归纳法、实频法[11]和达林顿网络综合法，这三种理论设计方法在指导实际设计的工程问题时，都有一定的局限性

计算机优化设计方法从具有均衡特性的电路拓扑结构出发，是一种基于计算机仿真的设计方法，在建立电路模型的基础上，通过计算机优化仿真来逼近要求的相应均衡量。

计算机优化设计法的主要步骤是首先根据指标要求选出合适的电路拓扑结构，然后合理的选择初值和扫参优化类型。很多仿真软件都可以用来进行均衡器的设计，如HFSS、CST和 ADS 等等。ADS 仿真软件在仿真板级电路具有速度快，建模容易的优点，本设计采用ADS 仿真软件进行整个四通道均衡放大模块的设计。计算机优化设计法最重要的就是确定初始电路拓扑结构，初始电路结构直接决定了仿真时间和最后的结果。计算机优化仿真设计步骤如图6所示。

# 2.2均衡器仿真设计

通过对各种集总元件均衡器电路结构的尝试，最后确定均衡器的拓扑如图7所示。均衡器的均衡效应主要由集总元件完成，集总元件间用微带线连接。除了连接作用外，通过优化微带线的长度和宽度，可以更好的和功率放大器匹配，以改善驻波。均衡器电路仿真完成后，

![](images/119538d4d0a17d5523634f1815621bfb19c75d82b95ebd4e1d61991e62afa286.jpg)  
图7均衡器电路拓扑结构

![](images/92539535a32b44954aa133584965f3e721c63f9af3e2a2e293a8077367908202.jpg)  
Fig.7 Equalizer circuit topology   
图8四通道均衡放大模块回波损耗仿真结果

Fig.8 Simulation results of return loss of four-channel amplifier module

![](images/2672be8f10929abcbb6dcf760c9da7deaa8da06d66d139f21050c41460b4bb1f.jpg)  
图9四通道均衡放大模块均衡量仿真结果

Fig.9 Equalization simulation results of four-channel equalization amplification module把功率放大器和功分器的S参数生成 snp 文件，和均衡器一起进行整个链路的方针。ADS的原理图仿真没有考虑实际微带电路的寄生和耦合效应，为了仿真结果和实际电路更接近，需要把原理图生成版图，并且把理想电容、电感模型替换为村田公司提供的实际的电容、电感模型。通过计算机的优化，最后整个四通道均衡放大模块的回波损耗如图8所示，均衡特性如图9所示。

# 3 四通道均衡放大模块加工调试测试

版图仿真全部完成后，去掉集总元件及功率放大器和功分器模型，把微带线版图导入AutoCAD，在AutoCAD中添加功率放大器直流偏置外围电路，并在版图适当地方加入大面积通孔铺地，以减少信号之间的串扰。电路板加工采用Rogers公司的基板。四通道均衡放大模块的电路板加工实物如图10所示。把集总元件、功率放大器及功分器焊接到电路板，并把电路板放入加工好的腔体。

![](images/225106b556839942b9b37bf562f8d004d3ebcbfcd9670dabf0a9415cd982b743.jpg)  
图10四通道均衡放大模块电路版图  
Fig.10 Four-channel equalization amplifier module circuit layout

![](images/9fb61b4d9d67b1dc77a6bffa1d1c904f01f98f144e1d11adc38efb52e7709e66.jpg)  
图11四通道均衡放大模块完整实物

最后把四通道均衡放大模块INPUT端口和中频同轴电缆连接，其它OUTPUT端口连接匹配负载，频谱仪和OUTPUT1端口连接进行测试，如图11。测试结果和仿真结果会有误差，可以通过微调均衡器集总电容、电感和电阻的值及功率放大器的直流偏置来对整个均衡放大模块的均衡量进行调整，以达到最佳值。图12为频谱分析仪测试中频信号经过四通道均衡放大模块其中一个通道的功率。和图1比较，各频段的中频信号的功率平坦度都得到了明显改善。剩余三个通道的功率所和图12所示功率相似，和所示通道有 $\pm 0 . 2 \mathrm { d } \mathrm { b m }$ 的波动。端口隔离度优于-40dB。

![](images/5acb5c405ceaf89b740e21756677c6882d9444f66472f3980e4661ebb2b8ce34.jpg)  
Fig.11 Complete physical objectof four-channel equalization amplifier module   
图12中频信号经过均衡放大模块的功率  
Fig.12 power of IF signal through equalization amplifier module

# 4结语

本文使用ADS仿真软件，采用计算机优化设计法设计了射电天文接收机的中频信号四通道均衡放大模块。为了减少电路板面积，降低成本，采用了集总元件和微带线相结合的方式。该均衡放大模块兼顾了射电天文接收机L、S、C、K四个频段及其左旋和右旋共8种信号通过下变频后的中频信号，对中频信号的线损进行功率均衡，改善中频信号的功率平坦度。测试结果表明，8种中频信号的功率平坦度都得到了明显改善，达到了射电天文接收机

中频监测系统的指标要求。

#

参考文献：   
[1］谢青梅，陈辑，王志刚，等.W波段微波功率模块的研制[J].微波学报，2018，34(S2)：30-32 XIEQ M,Chen J,WANG ZG,et al.Development of ${ \mathbb W }$ band microwave power module [J].Journal of Microwaves, 2018，34(S2)：30-32   
[2]CARTER MA,ANDREW Z,CLARK M,etal.High Efficiency E-Band MPM Power amplifier for high-resolution airborne radar in Proc[C].London，UK:IEEE,2017.   
[3]GOURAV C,GAURAV A.Non-Reflective Broadband Microwave Gain Equalizer for EW Applications[C].Mumbai, India:IEEE,2019.   
[4] KONDAKOV DV,LAVROVAP,IVANOV SI,etal．The frequencydiscriminator in 20-2250 MHz frequency band with parallel low and high frequency equalizer channels[C].Saratov,Russia: IEEE,2016.   
[5] YASUSHI I,HIROAKI T.L-band SiGe HBT active differential equalizers with variable inclination and position of the positive or negative gain slopes[C].London,UK:IEEE,2106.1015-1018.   
[6]徐阳. $3 \mathrm { m m }$ 增益均衡器关键技术研究[D].成都：电子科技大学，2019. Xu Yang.Research on Key Technology of 3mm Gain Equalizer[D].Chengdu:UNIVERSITY OF ELECTRONIC SCIENCE AND TECHNOLOGY OF CHINA,2019.   
[7］李玺．三毫米功率均衡技术研究[D].成都：电子科技大学，2020. LI X.Studyon Technologyof 3mm Power Equalization[D].Chengdu:UNIVERSITYOF ELECTRONIC SCIENCE AND TECHNOLOGY OF CHINA,2020.   
[8] CHIA C,WEITF,YO S.Miniaturized wideband bandpass filter in IPD technology with passive equalizer to improve the flatness of insertion loss response[C].Kyoto,Japan:IEEE,2017.75-78.   
[9] HAO P,ZHAOFJ，JUN D,et al．Substrate Integrated Waveguide Equalizersand Attenuators With Surface Resistance[J].IEE Transactions on Microwave Theory and Techniques,2020,Volume:68(4):1487-1495.   
[10] XU X N,LI W.A novel design and realization of microstrip lumped-like amplitude equalizer[C].Bei jing, China: IEEE，2016.   
[11]PIERRE J，JACQUES NB. Microwave Amplifier and Active Circuit Design Using the Real Frequency Technique[M]． Canada:Wiley-IEEE Press,2016.207-218.

# ，The Design of four channel equalization amplifier module for radio astronomy receiver

Ning Yunwei123,Yan Hao123,CaLiang123,Ma Jun123,Li Xiaofei1.23,Liu Feng12,Chen Yong 1.2.3

(l.XinjiangAstronomicalevatoryinecademyfiences,Uui,in;Keyboatoryfdto ChineseAcadeyofiences,anjingo8,ina;3.injangKeyboratoryofcroveecnlogyUruqi3ina)

Abstract: IF system of radio astronomy receiver is an important part of the receiver. The left circular polarization and right circular polarization signals of L,S, C and K bands in the receiver become IF signals through down conversion in the high frequency bin. IF signals are transmited to the observation chamber by coaxial cable.The observation chamber is far from the radio telescope's high frequency chamber，so the line loss is large,and the signal loss at different frequencies is different. The higher the frequency is,the greater the loss is,resulting in the lower power of intermediate frequency signal and the decrease of gain flatness with the increase of frequency. A four-channel equalization amplifier module is designed to improve the gain of if signal and compensate the gain flatness.The equalizer of this module adopts the combination of lumped element and microstrip line，which has the advantages of compact structure，easy integration and low cost. The test results show that the equalization amplifying module can meet the requirements of intermediate frequency system of radio astronomy receiver with equalization measure $\geq 8 \mathrm { d B }$ , power flatness $\leq 3 . 5$ dbm and return loss ≤-15dB within 6x frequency band width.

Key words: equalizer; Amplifier Module; receiver; radio astronomy; impedance matching

基金项目：基金项目：新疆维吾尔自治区自然科学基金青年基金(2020D01B60),国家自然科学基金资助项目(11903073)资助作者简介：宁云炜 $( 1 9 8 0 - )$ ，男，辽宁丹东人，硕士，主要从事射频微波电路与天线方面的研究通信作者：闫浩男硕士主要从事射电天文接收机方面的研究