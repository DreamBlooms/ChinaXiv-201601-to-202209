# 新疆天文台26米望远镜L波段接收机线-圆偏振的转换

陈勇1.2，孙正文1，闫浩1，李健1，李大磊1，李笑飞1，刘烽1（1.中国科学院国家天文台新疆天文台，新疆乌鲁木齐 830011；2.中国科学院射电天文重点实验室，江苏南京 210008）

摘要：新疆天文台南山基地26米望远镜L波段接收机使用线偏振馈源接收电磁波信号用于脉冲星观测。分子谱线观测和VLBI国际联测需要圆偏振信号，因此希望此接收机还能够观测圆偏振信号。论述了将线偏振电磁波转换为圆偏振电磁波的方案，研究了 $9 0 ^ { \circ }$ 电桥在偏振转换中的作用，介绍了偏振转换的调试方法。在圆偏振模块中使用 $9 0 ^ { \circ }$ 电桥完成了线偏振信号到圆偏振信号的转换，两路圆偏振信号的隔离度达到了课题要求，满足圆偏振观测的需求。这种线偏振信号到圆偏振信号的转换方式不影响接收机的系统温度。

关键词：线偏振；圆偏振；转换； $9 0 ^ { \circ }$ 电桥

# 0引言

中国科学院新疆天文台南山基地26米射电天文望远镜L波段接收机可用于脉冲星观测、分子谱线观测和VLBI国际联测[1]等多项观测任务。

L波段接收机主要是为脉冲星观测而研制的，使用线偏振馈源接收电磁波信号，因此馈源输出的是线偏振信号；但是分子谱线观测和VLBI国际联测需要观测圆偏振信号，所以L波段接收机需要一个偏振转换装置完成线偏振信号到圆偏振信号的转换，用于接收圆偏振信号。在线偏振信号转换为圆偏振信号的过程中，必须保证右旋圆偏振信号和左旋圆偏振信号的相互隔离。

![](images/73d8054829e604c37fc995e8bf0b7e94760ee203ce72de9387b3b344a916ac60.jpg)  
图1圆偏振系统框图  
Fig.1Ablock diagram of the circular polarizer system

国内许多天文台都有将天线接收到的线偏振信号转换为圆偏振信号的需求[2.3.4,5.7]。新疆天文台26米射电天文望远镜L波段接收机圆偏振观测模式如图1所示，天线接收到的电磁波信号在线极化器中被转换为垂直和水平两路线偏振信号，这两路线偏振信号被杜瓦中的LNA放大后进入 $9 0 ^ { \circ }$ 电桥，通过 $9 0 ^ { \circ }$ 电桥完成线偏振信号到圆偏振信号的转换。这种偏振转换方式的好处是实现起来比较容易，不会对接收机的系统温度产生影响。

为了方便圆偏振观测模式和线偏振观测模式的切换，在接收机系统中做了一个可插拔的模块，观测脉冲星时在接收机上插入线偏振模块，观测分子谱线和VLBI联测时插入圆偏振模块，圆偏振观测模式和线偏振观测模式的切换非常方便。

\*基金项目：新疆维吾尔自治区自然科学基金青年项目(2017D01B53)资助，作者简介：陈勇，男，硕士．研究方向：天文仪器与方法，.Email：chenyong@xao.ac.cn

# 1原理

天线接收到的任意电磁波都可以被分解为右旋圆偏振电磁波和左旋圆偏振电磁波[8]。

$E _ { R } { = } A [ c o s ( \omega t { + } \varphi _ { r } ) \overrightarrow { e _ { x } } { + } s i n ( \omega t { + } \varphi _ { r } ) \overrightarrow { e _ { y } } ]$ (1) $E _ { L } { = } B [ c o s ( \omega t { + } \varphi _ { l } ) \overrightarrow { e _ { x } } - s i n ( \omega t { + } \varphi _ { l } ) \overrightarrow { e _ { y } } ] ( 2 )$

这一电磁波信号被天线接收后进入 $\mathrm { ~ L ~ }$ 波段馈源，在线极化器中被转变为水平线偏振信号和垂直线偏振信号，用电压形式表示为[5]：

$V _ { x } { = } a { \bullet } c o s ( \omega t { + } \varphi _ { r } ) { + } b { \bullet } c o s ( \omega t { + } \varphi _ { l } ) ( 3 )$ $V _ { y } { = } a { \bullet } s i n ( \omega t { + } \varphi _ { r } ) { - } b { \bullet } s i n ( \omega t { + } \varphi _ { l } ) ( 4 )$

由（3）、（4）可知，这两路线偏振信号中都包含有左旋圆偏振信号和右旋圆偏振信号，因此必须通过一定的方式将左、右旋圆偏振信号分离才能满足圆偏振观测的需求。分离左、右旋圆偏振信号是通过 $9 0 ^ { \circ }$ 电桥完成的。

图2是 $9 0 ^ { \circ }$ 电桥的结构原理图[9，它的特性是：由端口 $\textcircled{1}$ 输入的功率在端口 $\textcircled{2}$ 和端口 $\textcircled{3}$ 之间平分且有 $9 0 ^ { \circ }$ 相位差，端口 $\textcircled{4}$ 无输出（隔离端口）。 $9 0 ^ { \circ }$ 电桥的结构具有对称性，其任何一个端口都可以作为输入端口，两个输出端口总是在与输入端口相反的方向，隔离端口与输入端口在同一边。

![](images/6985ee4e568269525090f47e6e27ac7a03415de1d1bc8ca1a1402776a9162b01.jpg)  
图2 $9 0 ^ { \circ }$ 电桥的结构  
Fig.2The $9 0 ^ { \circ }$ Hybrid Coupler

$$
\begin{array} { r } { [ S ] = \frac { 1 } { \sqrt { 2 } } \left[ \begin{array} { c c c c } { 0 } & { - j } & { - 1 } & { 0 } \\ { - j } & { 0 } & { 0 } & { - 1 } \\ { - 1 } & { 0 } & { 0 } & { - j } \\ { 0 } & { - 1 } & { - j } & { 0 } \end{array} \right] } \end{array}
$$

(5）式为 $9 0 ^ { \circ }$ 电桥的 S矩阵[10]，由（5)式可知，当接收机接收到的两路线偏振信号 $V _ { x } , -$ ，$V _ { y }$ 分别接入 $9 0 ^ { \circ }$ 电桥的端口 $\textcircled{1}$ 和端口 $\textcircled{4}$ 时，端口 $\textcircled{2}$ 和端口 $\textcircled{3}$ 的输出为：

$$
\begin{array} { l } { { \nonumber { } _ { / _ { 2 } = \frac { 1 } { \sqrt { 2 } } \left( - j V _ { x } - V _ { y } \right) } } } \\ { { \nonumber } } \\ { { = \frac { 1 } { \sqrt { 2 } } \left[ a \bullet c o s ( \omega t + \varphi _ { r } ) e ^ { - j \frac { \pi } { 2 } } + b \bullet c o s ( \omega t + \varphi _ { l } ) e ^ { - j \frac { \pi } { 2 } } - a \bullet s i n ( \omega t + \varphi _ { r } ) + b \bullet s i n ( \omega t + \varphi _ { l } ) \right] } } \end{array} 
$$

$$
\begin{array} { r l } & { \quad \frac { \hat { \lambda } _ { 2 } } { 2 } \lVert \alpha \cos ( \Omega ^ { \perp } \theta ) \cos \theta - \frac { \lambda _ { 2 } } { 2 } \lVert \beta + \kappa \cos ( \Omega ^ { \perp } \theta ) ( \theta - \frac { \kappa } { 2 } ) - \alpha \sin ( \Omega ^ { \perp } \theta ) ( \theta - \frac { \kappa } { 2 } ) - \beta \sin ( \Omega ^ { \perp } \theta ) ( \theta ) \sin ^ { \perp } \theta \sin ( \theta ) \rVert ^ { 2 } \hat { \eta } \Biggr \} } \\ & { \quad \times \frac { \hat { \lambda } _ { 2 } } { 2 } \lVert \alpha \sin ( \Omega ^ { \perp } \theta ) - \theta \cos ( \Omega ^ { \perp } \theta ) ( \theta ) - 2 \alpha \sin ( \Omega ^ { \perp } \theta ) ( \theta - \frac { \kappa } { 2 } ) - \beta \sin ( \Omega ^ { \perp } \theta ) ( \theta - \theta ^ { \perp } ) \sin ^ { \perp } \theta \sin ^ { \perp } \theta \Bigr \} } \\ & { \quad = 2 \lVert \beta - \sin ( \Omega ^ { \perp } \theta ) \sin ^ { \perp } \theta \sin ^ { \perp } \theta \Bigr \} \sqrt { 2 } \mathrm { \normalfont ~ S } ^ { \perp } } \\ & { \quad \times \frac { \hat { \eta } _ { 2 } - \frac { \kappa } { 2 } } { 2 } \lVert \beta - \frac { \kappa } { 2 } \hat { \eta } _ { 2 } ^ { \mathrm { p } } \Bigr \} } \\ & { \quad = \frac { \frac { \hat { \lambda } _ { 2 } } { 2 } } { \mathrm { \normalfont ~ C } ^ { \perp } } - \alpha \sin ( \Omega ^ { \perp } \theta ) + \theta \cos ( \Omega ^ { \perp } \theta ) + \alpha \sin ( \Omega ^ { \perp } \theta ) \sin ^ { \perp } \theta - \frac { \kappa } { 2 } - \beta \sin ( \Omega ^ { \perp } \theta ) ( \theta - \frac { \kappa } { 2 } ) } \\ &  \quad \times \frac { \hat { \eta } _ { 2 } } { 2 } - \alpha \cos ( 2 \Omega ^ { \perp } \theta ) - \beta \cos ( 2 \theta ) + 2 \alpha \sin ( \Omega ^ { \perp } \theta ) + \beta \cos ( 2 \theta - \frac { \kappa } { 2 } ) - \beta \sin ( \Omega ^ { \perp } \theta ) \sin ^ { \perp } \theta \Bigr \} \mathrm { \normalfont ~ \frac { \kappa } { 2 } ~ } \\ & { \quad = \frac { \hat { \lambda } _ { 2 } } { \mathrm { \normalfont ~ C } ^ { \perp } } - \alpha \sin ( \Omega ^ { \perp } \theta ) - \beta \cos ( \Omega ^ { \perp } \theta ) + 2 \alpha \sin ( \Omega ^ { \perp } \theta ) } \\ &  \quad = \frac { \lambda _ { 2 } } { 2 } \lVert \alpha \cos ( 2 \Omega \theta ) ( \theta - \phi ^ { \perp } ) - \kappa \cos ( 2 \theta ) ( \theta - \phi ^ { \perp } ) - \lambda \end{array}
$$

从（6）式和（7）式我们可以看到，天线接收到的任意电磁波进入到 $9 0 ^ { \circ }$ 电桥后，在$9 0 ^ { \circ }$ 电桥的一个输出端口中只包含左旋圆偏振信号，在另外一个输出端口中只包含右旋圆偏振信号，从而实现了左、右旋圆偏振信号的分离。

# 2线偏振信号到圆偏振信号转换的实现

为了将线偏振信号转换为圆偏振信号，进入 $9 0 ^ { \circ }$ 电桥的两路线偏振信号必须功率值相等、相位相差 $\pm { \frac { \pi } { 2 } }$ ， $9 0 ^ { \circ }$ 电桥输出的两路信号才能分别为左旋圆偏振信号和右旋圆偏振信号。

在实际接收机系统中，电磁波信号在线极化器中被分为垂直线偏振和水平线偏振两路信号，这两路线偏振信号分别被LNA放大后进入 $9 0 ^ { \circ }$ 电桥。在这个过程中，线极化器、LNA以及连接它们的同轴电缆都会对这两路线偏振信号产生影响，使得这两路线偏振信号的增益和相位发生改变，因此在这两路线偏振信号进入 $9 0 ^ { \circ }$ 电桥之前必须对它们的增益和相位进行调整。

为了方便调整信号且不对线偏振观测产生影响，对增益和相位的调整是在圆偏振模块中进行的。通过调整衰减值来调整功率，通过调整电缆的长度来调整相位。

# 2.1功率调整

进入到 $9 0 ^ { \circ }$ 电桥的两路线偏振信号的功率值相等是形成圆偏振信号的必要条件之一，功率调整步骤如下：

（1）将频谱仪的频率范围设置为需要的频率范围。  
（2）将水平线偏振信号接入频谱仪，并记录功率值。  
（3）将垂直线偏振信号接入频谱仪，通过调整衰减器的值，使垂直线偏振信号的功率值等于水平线偏振信号的功率值。

# 2.2相位调整

相位调整是非常重要的一步，如果两路线偏振信号的相位差不合适，在 $9 0 ^ { \circ }$ 电桥输出端就不能很好的将左、右旋圆偏振信号分离。相位调整是通过调整同轴电缆长度的方法来实现的，由于波导——LNA输入、LNA 输出——杜瓦输出、杜瓦输出——插槽这几部分的电缆长度很难改变，因此我们通过调整圆偏振模块中插槽- $9 0 ^ { \circ }$ 电桥这段同轴电缆的长度来达到调整相位的目的。

微波在同轴电缆中的波长为 $\lambda { = } c / f \sqrt { \varepsilon _ { r } }$ ，同轴电缆的填充材料为聚四氟乙烯， $\varepsilon _ { r } = 2 . 1$ 。因此L波段接收机的中心频率 $f { = } 1 6 5 0 \mathrm { M H z }$ 在同轴电缆中对应的波长为 $\lambda { \approx } 1 2 5 . 5 \mathrm { m m }$ ，$\lambda / 4 { \approx } 3 1 . 4 \mathrm { m m }$ 。

使用矢量网络分析仪可以直接测出两路线偏振信号从LNA输入到 $9 0 ^ { \circ }$ 电桥输入之间的相位差[5，但是这种方法对于正在使用的 $\mathrm { ~ L ~ }$ 波段低温制冷接收机来说比较麻烦。我们在实际中通过使用 Tektronix MSO70404C 混合信号示波器来测量两路线偏振信号中心频率$f { = } 1 6 5 0 \mathrm { M H z }$ 的相位来调整两路线偏振信号的相位差。

相位调整步骤如下：

（1）将水平线偏振信号接入示波器，调整示波器的参数，使水平线偏振信号在示波器中显示的波形为余弦波。  
（2）将垂直线偏振信号接入示波器，调整垂直线偏振信号同轴电缆的长度，就可以改变垂直线偏振信号的波形，使其在示波器中显示的波形为正弦波。这时两路线偏振信号在中心频率处正好差四分之一波长。

![](images/7dd7bef257bfbc52fcc7851801baad6c984beece487a90ad6b0891aec421a986.jpg)  
图3 两路线偏振信号的相位差  
Fig.3 The relative phase of the two signals

# 3 测试

# 3.1 圆偏振测试

实测中用一个右旋圆偏振天线发送右旋圆信号，用频谱仪分别在L波段接收机右旋 圆偏振输出端和左旋圆偏振输出端接收信号。

![](images/72ca5e4ab258442fba66c3ec6a2da947b2a61cd8c3528aef42a707c45d3aac29.jpg)  
图4L波段接收机的圆偏振隔离

从图4中可以看到右旋圆偏振信号和左旋圆偏振信号在1.53GHz—1.72GHz的频率范围内实现了偏振隔离，这段频率也是VLBI联测需要的频率范围。在1.4GHz—1.5GHz的频率范围内偏振隔离没有达到预期目标，经过实际测试后发现这是因为两个LNA在不同频率上的相位一致性不好造成的。

# 3.2圆偏振观测

2017年5月25日，新疆天文台26米射电天文望远镜与欧洲VLBI网各台站联合观测，使用L波段接收机圆偏振进行条纹检测实验，实验获得了成功。图5是新疆天文台与德国Effelsberg100 米射电天文望远镜的相关干涉条纹[11],图 5(a)为左圆偏振相关干涉条纹,图 5(b)为右圆偏振相关干涉条纹。

![](images/2155359805545bd34d7e2484692790a42a1dc0c8ae7dae5e3a00af824b76fcf5.jpg)  
Fig.4Circular polarization isolation of the Lband receiver   
图5 L波段圆偏振条纹检测  
Fig.5L-band circular polarizationfringe test

# 4结论

新疆天文台L波段低噪声制冷接收机通过一个圆偏振转换模块，将线偏振信号转换为圆偏振信号，实现了左、右旋圆偏振信号的隔离，可使用线偏振馈源观测圆偏振信号。

# 参考文献：

[1] 杨文军，杨军，江悟，夏博，李健，崔朗，张华，李鹏，高志福.新疆天文台南山站DBBC2 数字终端系统的建立[J].天文研究与技术—国家天文台台刊，2018，15(1)：32-39.Yang Wenjun，Yang Jun，Jiang Wu，Xia Bo，LiJian，Cui Lang，Zhang Hua，LiPeng，GaoZhifu.Istaling a VLBI DigitalBackendwithDBBC2at NanshanStation，XinjiangAstronomical Observatory[J].Astronomical Research&Technology—Publications of National Astronomical Observatories of China，2018，15(1)：32—39.  
[2] 贾茹，李斌.天马望远镜 Ka波段宽带圆极化器研制[J].天文研究与技术—国家天文台台刊，2017，14(4)：488—494.JiaRu，LiBin.DevelopmentofKa-Band WidebandCircularPolarizer[J].Astronomical Research &Technology-PublicationsofNational Astronomical Observatories of China，2017，14(4):488—494.  
[3]王海伦，李斌.K波段宽带圆极化器设计[J].天文研究与技术—国家天文台台刊，2015，12(4)：455—460.Wang Hailun，Li Bin.ADesignof aK-Band Circular Polarizer[J].Astronomical Research & Technology-PublicationsofNational Astronomical Observatories of China，2015，12(4):455—460.  
[4]周德丽.基于FAST数字终端的线—圆偏振转换的研究[J].电子技术与软件工程，2018，4：97—98.ZhouDeli.Researchon linearpolarization to circularpolarization conversion basedonFAST digital terminal[J].ElectronicTechnology& Software Engineering，2018，4：97—98.  
[5]陈松麟.ADS 辅助实现线极化到圆极化的转换[J].中国科学院上海天文台年刊，2005，26：103—109.CHEN Songlin．Realizationof linear-circularpolarizationconversion withthe ADS[J].Annalsof Shanghai AstronomicalObservatoryChinese Academy of Sciences.2005，26:103—109.  
[6]苑婷婷，史俊，仲伟业，刘庆会，沈志强.Q波段宽带圆极化器设计与研究[J].中国科学院上海天文台年刊，2014，35：41-50.YUAN Ting-ting，SHI Jun，ZHONG Wei-ye，LIU Qing-hui，SHEN Zhi-qiang.Q-band Broadband Dual-circular PolarizerDesign[J].Annals of Shanghai Astronomical Observatory Chinese Academy of Sciences，20l4，35：41—50.  
[7] 王锦清，仲伟业.上海 65m射电望远镜 Ka波段极化器设计[J].中国科学院上海天文台年刊，2009，30：39—50.WANGJin-qing，ZHONGWei-ye.The Design Of SH65 Radio Telescope KaBandPolarizer[J]. Annals of Shanghai AstronomicalObservatoryChinese Academy of Sciences.2009，30：39——50.  
[8]冯亚伯，电磁场理论[M].成都：电子科技大学出版社，1995.  
[9]David M.Pozar.微波工程(第三版)[M].张肇仪，周乐柱，吴德明等译.北京：电子工业出版社，2006.David M.Pozar.Microwave Engineering(third Editon)[M].Beijing：Electronic Industry Press，2006.  
[10]廖承恩.微波技术基础[M].西安：西安电子科技大学出版社，1995.  
[11]http://www.evlbi.org/tog/ftp_fringes/N17L2/scan02/index.html.

# Conversion of line polarization to circular polarization in L band receiverof 26m Telescope inXinjiang Astronomical

Observatory

CHEN Yong12，SUN Zhengwen’，Yan Haol，Li Jian¹，Li Dalei1，Li Xiaofei’，Liu Feng1 (1.XinjiangAstrooicalbservatorNatioalstronoicalObertores,secadeyofiences,Ua; 2.Key Laboratory of Radio Astronomy,Chinese Academy of Sciences,Nanjing 21oo08,China)

Abstract：The L-band receivercan beusedfor pulsar observation，molecular line observationand international VLBI joint-observationsofthe6-metertelescopeatNanshaninXinjiangAstronomicalObservatoryChineseAcademyofSciences.The L-bandreceierisainlydevelopedforpusarbsevatios,itusesiearpoazationfeedtoeceeelectromageticsignals,oefeed outputs linearpolarizationsignals.Circularpolarizationsignalsarerequired inmolecularineobservationndtheinterationalVLBI jointobservations,WehopethattheL-bandreceivercanbeusedforbothlinearpolarizationsignalobservationandcircularpolarization signalobservation,spolaationconversiodeviceisusedtoonvertheinearlypolardsigaltoteicularlyoladsigalin theL-bandreceiver.Theisoationbetwenright-handcircularpolarizationsignaladleft-handcircularpolarizationsignalustbelarge enough,inteprocessofoertinglinarolaatiosigaltoulaolazatiosigal.etodofonveiglearolatio signal into circular polarization signal is given in this paper,a $9 0 ^ { \circ }$ Hybrid Coupler is used to convert the linear polarization signal to the circular polarization signal.and the role of the $9 0 ^ { \circ }$ Hybrid Coupler in polarization conversion is studied.If a signal is input at one port of the $9 0 ^ { \circ }$ Hybrid Coupler, the power of the signal at the two output ports of the $9 0 ^ { \circ }$ Hybrid Coupler will be equal, but the relative phase of the two signals are separated by $9 0 ^ { \circ }$ .If the phase difference between the two signals entering the $9 0 ^ { \circ }$ Hybrid Coupler is $9 0 ^ { \circ }$ ,the output signals in the $9 0 ^ { \circ }$ Hybrid Coupler willofset partof the power due to the phase delay.Therefore,the circular polarization signal can be exported at the output of the $9 0 ^ { \circ } ]$ Hybrid Coupler.The gain flatness and phase uniformity of the two LNAs must be very good in order to convertheliarlypadgnalintoularlypolarzdignalerisethoationoftetooutputcularlypoladigals will be poor.In this paper, the power value of the two signals entering the $9 0 ^ { \circ }$ Hybrid Coupler is equal by adding or reducing attenuators, and the phase difference between the two signals entering the $9 0 ^ { \circ }$ Hybrid Coupler is $9 0 ^ { \circ }$ by adjusting the length of the coaxial cable,thus theconversionfromlinearplarizationsignal tocircularpolarizationsigalisrealized.Theisolationofthetwocircularpolarzation signals metstherequirementsofthesubjects,thetwosignalscanbeusedcircularpolarzationobservation.Theconversionmodfrom linear polarization signal to circular polarization signal does not affect the system temperature of the receiver.

Key Words: linear polarization; circular polarization; polarization conversion; $9 0 ^ { \circ }$ Hybrid Coupler