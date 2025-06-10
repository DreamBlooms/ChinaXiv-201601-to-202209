# 新型微带反射阵单元的设计及其应用

薛飞1²王宏建¹易敏‘刘广1,2

1（中国科学院空间科学与应用研究中心微波遥感技术重点实验室，北京100190）²（中国科学院大学，北京 100049)

摘要提出了一种单层的具有多谐振结构的微带反射阵单元,利用 HFSS 对其反射相位特性进行仿真分析，获得了约 $4 3 0 ^ { \circ }$ 的反射相位动态范围，并且反射相位曲线的线性度较好。根据此单元设计了一个工作在Ku波段的微带反射阵，用指数渐变槽线（Vivaldi）天线作为该反射阵的馈源。仿真结果表明,在中心频率处增益可达27.1dB,半功率波瓣宽度均为 $4 . 9 6 ^ { \circ }$ ，在 $1 2 \mathrm { G H z } . 1 5 . 5 \mathrm { G H z }$ 的频带内增益波动约2dB，具有较宽的频带。将此Vivaldi天线和反射阵天线进行加工测试，得到的测试结果与仿真结果吻合的较好。

关键词 微带反射阵，多谐振结构，Vivaldi天线，宽频带

# Design of a Novel Multi-resonance Microstrip Reflectarray Element

# and Its Application

Xue Fei1,2 WANG Hong-jian1 YI Min1Liu Guang1,2 l(Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences,Beijing,100190) 2 ( University of Chinese Academy of Sciences， Beijing,100049)

AbstractA novel single layer microstrip reflectarray element with multi-resonance structure is proposed in this paper. HFSS is used to analyze the reflect phase for the designed element. About $4 3 0 ^ { \circ }$ reflect phase range is obtained with the reflect phase curve nearly linear. A microstrip reflectarray composed of the proposed element is designed for $\mathtt { K u }$ band and a Vivaldi antenna is used as the feed. The results indicate that the gain reaches $2 7 . 1 \mathrm { d B }$ at the center frequency,and the half power beamwidth is $4 . 9 6 ^ { \circ }$ . The gain changes less than 2dB in the range of $1 2 { \cdot } 1 5 . 5 \mathrm { G H z }$ which shows that the reflectarray has wide band. The Vivaldi antenna and the reflectarray is manufactured and tested,and a well coincide is obtained between the simulation results and the test results.

Key wordsmicrostrip reflectarray, multi-resonance structure, Vivaldi antenna, wide band

# 引言

微带反射阵列天线是一种结合了抛物面反射天线和微带阵列天线优势的天线阵，以重量轻、体积小、价格便宜、易于制造特别是易于和其他物体共形、易与微带电路集成等优点，自1978年提出来后就受到了很高的重视并得到快速的发展。与一般抛物面反射天线类似，微带反射阵列天线不需要馈电网络，不存在寄生辐射和阻抗插入损耗，因此辐射效率较高。微带反射阵是由馈源和一组具备移相功能的微带辐射单元组成的，在馈源的照射下，每一个单元通过自身对入射波的移相功能，使反射波在特定方向上实现同相叠加，从而在该方向发出高增益波束。

传统的微带反射阵列天线的带宽通常都较窄，它的带宽受到很多因素的影响，比如馈源的带宽、阵元的带宽、不同位置单元的空间相位延迟以及单元间距等[1，其中阵元带宽和不同位置单元的空间相位延迟这两个因素是最为关键的。理想的宽带反射阵单元的反射相位曲线应在不同频率处是相互平行的，并且与入射波的入射角无关，通过合理的选择单元的形式和结构可以得到较为理想的宽带反射阵单元。较大的焦径比可以减小空间相位延迟对带宽带来的影响，但是馈源的照射效率会受到影响，所以在设计反射阵天线时需要折衷考虑。分形天线结构的自相似性使得天线可以多频工作2，增加天线的工作带宽，它的自加载特性也使得天线的带宽得到了展宽。将分形技术与微带天线的设计相结合，在移动通信和卫星通信及其他宽频带应用系统中具有很大的应用潜力。

Vivaldi天线是由Gibson在1979年提出的一种天线形式[3]，该天线属于非频变天线，具有超宽的工作频带、良好的辐射定向性、输入阻抗稳定、结构简单、造价低廉、平面易集成等特点。Vivaldi天线由一端较窄的槽线过渡到另一端较宽的槽线构成，槽线过渡呈指数变化规律。由于其平面结构对于反射波的遮挡很小，因此采用该天线作为微带反射阵的馈源，可以很好地解决正馈时的馈源遮挡问题。

为了将馈源辐射出来的波转变成一个聚焦波束，从每个反射单元反射出去的波必须有合适的相移。相移补偿有四种典型的方式：一是在微带贴片上加载不同长度的相位延迟线来实现不同的相移[4]。二是通过改变微带反射单元的尺寸大小来实现相位补偿，通过合理设计每个贴片的尺寸来调节反射波相位以补偿从馈源到每个贴片由于空间距离不同而造成的相位延迟[5]。三是将相同的圆极化微带单元旋转不同的角度来实现不同的相移[。四是通过在贴片或贴片下的地板上加载不同长度的缝隙来实现相位补偿。本文中采用改变反射单元尺寸大小的方法来实现相位补偿。

文章中提出的单层的具有分形结构的多谐振反射阵单元可以在获得线性度较好的反射相位曲线的同时能提供约为 $4 3 0 ^ { \circ }$ 的反射相位范围。利用该单元设计了一个微带反射阵，使用Vivaldi天线对其进行馈电，仿真结果表明在中心频率处增益达到了27.1dB，在12GHz—15.5GHz的频带内，增益波动约2dB。

# 1微带反射阵的基本原理

为了在指定方向上将球面波波前转换成平面波波前，阵列单元的反射相位曲线范围不得小于 $3 6 0 ^ { \circ }$ 。传统的结构简单的单层单元很难在达到 $3 6 0 ^ { \circ }$ 相移的同时具有线性度较好的反射相位曲线，尤其在谐振长度附近，反射相位曲线随尺寸变化的斜率较大，导致天线的带宽很窄，同时增加了加工难度。通常来说，可以通过增加介质厚度的方法来平滑反射相位曲线，但是这样会使得反射相位的范围减小从而达不到 $3 6 0 ^ { \circ }$ 的要求。文献[8]中采用多层贴片叠加的结构来获得平滑的并且相移范围大于 $3 6 0 ^ { \circ }$ 的反射相位曲线，然而多层贴片叠加结构带来的问题是增加了设计复杂度和加工难度，同时加大了天线造价。单层多谐振单元结构可以很好的满足反射相位曲线的范围要求和线性度要求。文献[9]采用圆环和圆的组合的方式获得了约为 $3 8 0 ^ { \circ }$ 的移相范围。本文提出的分形结构就是一种采用多谐振特性的单元，在满足反射相位曲线线性度及范围要求的同时还能提供较宽的带宽。

如图1所示的坐标系，根据阵列天线理论，对于辐射方向为 $\left( \theta _ { 0 } , \ \phi _ { 0 } \right)$ 的反射阵表面相位分布为：$\phi ( x _ { i } , y _ { i } ) { = } { - } k _ { 0 } \sin \theta _ { 0 } \cos \phi _ { 0 } x _ { i } - k _ { 0 } \sin \theta _ { 0 } \sin \phi _ { 0 } y _ { i }$ (1)

其中 $k _ { 0 }$ 为真空中的传播常数， $\left( x _ { i } , y _ { i } \right)$ 是第 $i$ 个单元的中心坐标。同时，各阵元的反射相位等于其入射相位加上自身引入的补偿相位，即：

$$
\phi ( x _ { i } , y _ { i } ) = - k _ { 0 } d _ { i } + \phi _ { R } ( x _ { i } , y _ { i } )
$$

其中 $d _ { i }$ 代表馈源相位中心到第 $i$ 个贴片单元的距离， $\phi _ { R } ^ { } ( x _ { i } , y _ { i } )$ 为第 $i$ 个单元反射系数相位，也就是该单元所需的补偿相位。由(1)式和(2)式可得，各单元所需的移相值为：$\phi _ { R } ( x _ { i } , y _ { i } ) = k _ { 0 } \big [ d _ { i } - \big ( x _ { i } \cos \phi _ { 0 } + y _ { i } \sin \phi _ { 0 } \big ) \mathrm { s i n } \theta _ { 0 } \big ]$

通过 (3)式可以计算出各个单元所需补偿的相位，然后根据单元的反射相位曲线得出每个单元的尺寸。

![](images/f26c0022a02ddc265337769ccd4c456115559a6b98af2830d02140a905294792.jpg)  
图1微带反射阵列天线原理图[11]

# 2新型分形单元的设计及分析

本文设计的具有宽频带的反射阵单元采用单层多谐振结构，单元结构如图2所示。该单元结构简单，易于工程实现。为了得到较大的相移范围和线性度较好的反射相移曲线，在介质材料和接地板之间增加一层空气层（实际加工测量中采用介电常数接近空气的泡沫材料)。

该单元具有分形结构，最外边六边形边长为 $a$ ，介质的介电常数 $\varepsilon _ { r } = 2 . 2$ ，厚度为$h _ { \scriptscriptstyle 1 }$ ，空气层厚度为 $h _ { 2 }$ ，介电常数约为1.06。采用文献[10]中提出的WGA对单元的反射相位进行分析，得到单元的反射相位曲线。单元工作在 $\mathrm { K u }$ 波段，栅格周期L取为 $1 3 \mathrm { m m }$ 文中采用HFSS对单元的反射相位特性进行仿真分析。

当 $a$ 从 $1 . 5 \mathrm { m m }$ 增加到 $6 \mathrm { m m }$ ，分析不同的 $h _ { 1 }$ 和 $h _ { 2 }$ 的值对反射相位的影响。由图3可以看出，当 $h _ { 1 } = 0 . 5 \mathrm { m m }$ 和 $h _ { 1 } = 0 . 7 \mathrm { m m }$ 时，反射相位曲线的线性度均较好且相位变化范围较大，文章选择 $h _ { \scriptscriptstyle 1 } = 0 . 5 \mathrm { m m }$ 。图4表明了不同空气层厚度 $h _ { 2 }$ 对单元反射相位曲线的影响，从图中可以看出 $h _ { 2 }$ 对单元反射相位曲线有较大的影响。当 $h _ { 2 } = 0 \mathrm { m m }$ 时，反射相位几乎没有变化，当 $h _ { 2 } = 3 \mathrm { m m }$ 时反射相位曲线的相位变化范围较大，且线性度最好，故本文选择 $h _ { 2 } = 3 \mathrm { m m }$

![](images/3514dcf85595b1890933f05eb4b988711b31f825176de591f73f4b474d39a562.jpg)  
图2单元结构示意图

![](images/877b4d146cc638446e66258f5771b8c8d107807948065983c2569ee1243bb5e8.jpg)  
图3介质层厚度对反射相位的影响 $( h _ { 2 } = 3 m m )$

综上，当 $h _ { 1 } = 0 . 5 \mathrm { m m }$ $h _ { 2 } = 3 \mathrm { m m }$ ，从曲线可以看出，随着单元尺寸 $a$ 从 $1 . 5 \mathrm { m m }$ 到 $6 \mathrm { { m m } }$ 变化时，相移范围约为 $4 3 0 ^ { \circ }$ ，满足了微带反射阵单元的相移范围不小于 $3 6 0 ^ { \circ }$ 的要求。

文章对六边形单元、六边形环单元以及本文提出的具有多谐振结构的单元在中心频率处的反射相位进行了比较，如图5所示。由图中曲线可以看出，本文所设计的结构单元的反射相位变化范围较大并且线性度也较好。

![](images/2297f6e0c0ef7552b8aa71751be0d39245f1360b6a9c2f812ded9372e3d0e791.jpg)  
图4空气层厚度对反射相位的影响( $\cdot h _ { \scriptscriptstyle 1 } = 0$ .5mm)

![](images/65ae4e33c6c965338b42552c0512b28de8e489fbde4c7dd2a6d3c47ed942d276.jpg)  
图5不同单元结构的反射相位曲线

# 3微带反射阵的设计及结果

利用上文中提出的新型单元，设计了一个工作在 $\mathrm { K u }$ 波段的微带反射阵列天线来验证文章该单元的有效性，该阵列结构如图6所示。阵列直径 $\mathrm { D } { = } 3 2 5 \mathrm { m m }$ ，介质层厚度（204号 $h _ { \scriptscriptstyle 1 } = 0 . 5 \mathrm { m m }$ $\varepsilon _ { r } = 2 . 2$ ,泡沫层厚度 $h _ { 2 } = 3 \mathrm { m m }$ 介电常数约为1.06， $_ { \mathrm { L } = 1 3 \mathrm { m m } }$ ，馈源的相位中心与阵列中心的距离 $\mathrm { F } { = } 2 6 0 \mathrm { m m }$ ，焦径比$\mathrm { F / D = } 0 . 8$ ，由于Vivaldi天线的平面结构对反射波的遮挡很小,故本文采用Vivaldi天线作为馈源。该Vivaldi天线的加工样机及实测方向图如图7和图8所示。

文章中所设计的平面微带反射阵（Vivaldi天线作为其馈源)的仿真方向图如图9所示，可以看到在 $\mathrm { K u }$ 波段的中心频率处增益可以达到 $2 7 . 1 \mathrm { d B }$ ，半功率波瓣宽度均为 $4 . 9 6 ^ { \circ }$ 。对于E面（yoz面）方向图，副瓣可以达到-16dB，对于 $\mathrm { ~ H ~ }$ 面（xoz 面)，副瓣约为-20dB。不同频率处的仿真增益方向图如图10所示。可以看到在12GHz—15.5GHz的频带范围内增益波动约2dB，具有较宽的频带。

![](images/3759cc57e7dff6c63fe61043e7ec4657ef952d3050abf9238acb2e9c9532465a.jpg)  
图7Vivaldi天线的加工样机

![](images/4bc098574b7bb5e85a24bb2096e433776164df904edb262bfd1360e81980f9d2.jpg)  
图8Vivaldi天线在中心频率处的实测方向图

![](images/d353ee9977e6486d8af2b11ecd2a2cd71eaf0cf459b291add0aaf6222c5b4154.jpg)  
图9反射阵在中心频率处仿真的增益方向图

![](images/c97b598d16d60834aa63c652e3bde6351750378ad5a306640c5952303fe4f074.jpg)  
图6微带反射阵列天线模型

![](images/2b5153c2132c314a26385a47a0cc787412d8203768b4abb30afbf37a4b1ce3cd.jpg)  
图10反射阵在不同频率处的仿真增益

为了验证上述单元及阵列设计的工程可用性，对微带反射阵列天线进行加工，图10 给出了该微带反射阵在中心频率处实测的E面和H面方向图。从图中可以看出在该频率处实测方向性系数为27.1dB。E面方向图的半功率波瓣宽度为 $5 . 3 ^ { \circ } , \mathrm { H }$ 面为 $4 . 9 ^ { \circ }$ ，与仿真结果的差别主要是由于加工误差和测试误差造成的。此外，较为简易的工装也会使得测试结果变差。但是总体说来与仿真结果吻合的较好。

![](images/f84f71d0fc19bae7dbf377d8bbfeb63990b3d8d83f1260eccb197f54132352da.jpg)  
图11微带反射阵的实测方向图

# 4结论

提出了一种新型的多谐振单元作为平面微带反射阵的阵元，该单元具有宽频带特性，并且为单层结构，结构简单，易于实现。采用该单元设计了一个微带反射阵列天线，使用Vivaldi天线对其进行馈电，仿真结果表明，该反射阵具有较宽的带宽。将该微带反射阵进行加工并在微波暗室中进行测试，测试结果与仿真结果吻合的较好。由该单元组成的微带反射阵具有高增益、宽频带、低副瓣的特性，具有较高的工程应用价值。

# 参考文献

[1]D．Pozar，S.D.Targonski，H.D.Syrigos.Design of  
millimeterwave microstrip reflectarrays[J].IEEETrans.  
Antennas Propagat.,1997,45(2):287-296.  
[2]HaraPrasadRV,PurushottamY,MisraVC,etal.Microstrip  
fractalpatchantenna formultibandcommunication[J].  
ElectronicsLetters,2000,36(14):1179-1180.  
[3] 徐志，刘其中，章传芳，等.改进型vivaldi天线[J]．电波  
科学学报，2008，23(3):471-475.Xu Z,Liu Q Z,Zhang CF,et al.Modified vivaldi antenna [J].Chinese Journal of Radio Science,2008,23(3):471-475.[4]R.D.Javor,X.-D.Wu，and K.Chang.Design andperformance of a microstrip reflectarray antenna[J].IEEE Trans.Antennas Propagat..1995, 43(9):932-939.  
[5]D.M.Pozar,S.D.Targonski,R.Pokuls.A shaped-beammicrostrip patch reflectarray[J]. IEEE Trans. Antennas Propagat.,1999,47(7):1167-1173.  
[6]J.Huang and R.Pogorzelski.A Ka-Band MicrostripReflectarray with Elements Having Variable Rotation Angles[J].IEEE Trans.Antennas Propagat.,1998,46(5):650-656.  
[7]E.Carrasco，M.Barba,and J.A.Encinar.Reflectarrayelement based on aperture-coupled patches with slots and lines ofvariable length[J]．IEEE Trans.Antennas Propagat.2007,55(3):820-825.  
[8] J.A. Encinar. Design of two-layer printed reflectarray usingpatches of variable size[J]. IEEE Trans.Antennas Propagat. 2001,49(10):1403-1410.  
[9]郑文泉，万国宾，马鑫，等．一种新型单层微带反射阵天线单元的分析[J]．电波科学学报，2013，28(5)：915-919.ZhengWQ，WanG B,Ma X,et al.A novel single-layermicrostrip reflectarray element[J].Chinese Journal of RadioScience,2013，28(5):915-919.  
[10] Tsai,F.-C.E.,M.E.Bialkowski.An Equivalent WaveguideApproach to Designing of Reflectarrays Using Variable-SizeMicrostripPatches[J].Microw.Opt.Technol.Lett.,2002,34(3):172-175.  
[11] 周丹晨，微带反射阵列天线研究，南京航空航天大学硕士学位论文，2011.  
ZhouDanchen，Research on Microstrip ReflectarrayAntennas[D], NUAA,2011.薛飞（ $1 9 8 9 - { \dot { , } }$ ，男，陕西人，中国科学院大学电磁场与微波技术博士生，主要从事星载天线的研究与设计。  
王宏建（ $1 9 6 9 - \rangle$ ，男，河南人，中国科学院空间科学与应用研究中心研究员，主要研究方向为电磁场与微波技术。