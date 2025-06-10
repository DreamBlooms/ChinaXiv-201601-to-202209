# 天马望远镜K波段双模环型滤波器的研究

陈丽，李斌

(中国科学院上海天文台，上海200030)

摘要：低插入损耗、边带陡峭的带枝节的双模弯曲方环形带通滤波器，用于射电天文K波段(18-26.5GHz)多波束接收机的小型化集成下变频系统。该滤波器采用正交直连馈线，获得低插入损耗，再加载调谐枝节构成一个边带陡峭的宽带滤波器。从测量结果可知：单环滤波器的3dB 带宽为 $4 2 . 8 \%$ ，在17.4GHz-26.9GHz频带内的回波损耗小于-20dB，插入损耗为-1.05dB。15.1GHz-16GHz 和 28.1GHz-28.9GHz 的阻带抑制度大于 35dB；双环滤波器的3dB带宽为 $3 9 . 8 \%$ ，在17.7GHz-26.5GHz频带内的回波损耗小于-14dB，插入损耗为-1.27dB。12.8GHz-15.3GHz和27.9GHz-30.6GHz的阻带抑制度大于35dB。两个滤波器的测试结果和仿真结果吻合度很高。

关键词：多波束；天马望远镜；双模；带通滤波器;中图分类号：TN713.5文献标识码：A 文章编号：1672-7673(2018)02

K波段(18-26.5GHz)是射电天文学研究恒星形成，特别是大质量恒星形成十分重要的观测波段。多条氨分子谱线被认为是测定恒星形成区稠密分子云核密度及温度等物理条件的强有力工具，而22GHz水脉泽通常也与恒星形成区成协。在该波段还存在着如20.0GHz、23.1GHz、25.0GHz等甲醇脉泽谱线，这些脉泽线又通常与大质量恒星形成区成协，搜寻该类脉泽也是重要的研究课题[。多波束接收系统可以大幅提升射电望远镜的巡天效率，尽可能小的波束间隔保证了边沿波束的口径效率和方向图对称性，但同时也对接收通道的小型化提出了较高的要求。上海 $6 5 \mathrm { m }$ 天马望远镜正在研制K波段7波束接收机，其波束物理间隔仅为$1 1 0 \mathrm { m m }$ ，所以下变频系统将采用微波集成电路(MIC—Microwave Integrated Circuit)工艺。本文研究一个18-26.5GHz的微带宽带滤波器结构，它应用于K波段的集成下变频系统的第1级射频滤波，实现射频信号的镜像抑制，并抑制混频器的本振至链路系统的泄露。

![](images/1219d9476cda196b8f27f80146e294c18342a0da86c27bc4316d2ca000fd9419.jpg)  
图1K波段双波束接收机系统图  
Fig.1 Diagram of K band dual beam receiver

图1为K波段双波束接收机的系统架构图，该接收机已在天马望远镜上使用。本文研究的K波段微带滤波器是应用于K波段7波束接收机的下变频系统，K波段的双波束接收机的下变频系统是分立器件的组装，结构比较大，为了获得小型结构的下变频系统，准备采用MIC工艺设计K波段7波束接收机的下变频系统。

常见的宽带滤波器有：带枝节的多模环形滤波器、带SIR的多模滤波器和其他类型的多模滤波器[2]。带枝节的多模环形滤波器具有陡峭的边带特性，带SIR的多模滤波器阻带衰减缓慢，因设计需求是一个具有陡峭边带特性的宽带滤波器，故本文采用带枝节的双模弯曲方环滤波器。

在方环谐振器直连馈线的带阻结构上加载短接线形成的宽带滤波器不存在耦合缝隙，可以克服较大的插入损耗的缺陷[3]。

因本文设计的滤波器需要运用于K波段集成下变频系统，为了便于集成，需要在滤波器的输入输出进行一个GSGpad的设计，用于金丝线的架接。

# 1带枝节的弯曲方环宽带带通滤波器[4]

正交直连馈线弯曲方环双模带阻滤波器如图1，没有耦合缝隙，弯曲方环谐振器直连馈线。弯曲方环谐振器的周长计算公式如下：

$$
L _ { _ { r } } = n \times \lambda _ { _ { g } } ,
$$

其中， $n$ 为模式； $\lambda _ { g }$ 为波导长度。

该弯曲放环是双模带阻滤波器，取 $n = 2$ ，则可以得到：

$$
L _ { 2 } + 2 \times L _ { 1 } - 2 \times W = 2 \times \lambda _ { g } .
$$

该滤波器按图2虚线可以分成两个对称结构，可用奇偶模理论进行分析，分析的奇偶模

等效电路如图3。方环的特性阻抗是 $Z _ { \scriptscriptstyle 1 }$ ,输入输出的特性阻抗是 $Z _ { \ L _ { 0 } }$ 。

![](images/25f926419eace24acfdad9f16aa5cdf08680d1509755047c9a4c304ae9065b49.jpg)  
图2正交直连馈线弯曲方环带阻滤波器

Fig.2 Bandstop Filter using a meander ring resonator with direct-connected orthogonal feed lines

![](images/7dfc8ede8ab1da6d0819313a6d7c3170ce9d690b5cba2aa009cd6df9b77321e9.jpg)  
图3带阻滤波器的奇偶模等效电路  
Fig.3Equivalent circuit of even-old-method ofBandstop Filter

在正交直连馈线弯曲方环双模带阻滤波器上加载一对开路调节枝节，可以得到一个宽

带带通滤波器，如图4。开路调节枝节特性阻抗为 $Z _ { _ 2 }$ ,长度为 $\lambda _ { g } / 4$ 。根据带枝节的正方环滤

波器的理论可以得知，该滤波器的中心频率与方环周长和短路枝节的长度都有关系，滤波

的传输零点由特性阻抗比 $\scriptstyle a = Z _ { 1 } / Z _ { 2 }$ 决定[5]。当确定中心频率 $f _ { 0 }$ 后，可以通过调整特性阻抗

比 $a = Z _ { 1 } / Z _ { 2 }$ 的值获得想要的滤波器带宽。当 $a$ 取0.5-3.3,滤波器的带宽从 $3 2 \% - 5 5 \%$ 变化[5]。

![](images/50e9f98afd8f849e56cac3b25a95e44ee852377a9096da967aaa2b6f08147f58.jpg)  
图4加载短截线的弯曲方环双模带通滤波器

Fig.4 Dual-mode bandpass Filter Using meander square loop with Two Tuning Stubs

# 2滤波器设计

本文设计一个18-26.5GHz带宽的带通滤波器。选择介质基板的相对介电常数为2.2，厚

度为 $0 . 2 5 4 \mathrm { { m m } }$ 。先设计双模弯曲方环形带阻滤波器，为了方便设计，这里取 $Z _ { \scriptscriptstyle 1 } = Z _ { \scriptscriptstyle 0 } = 5 0 \Omega$ ，

根据（2）式计算得到 $L _ { 1 } = L _ { 2 } = 2 . 1 m m$ ，然后进行仿真，发现中心频率 $f _ { 0 }$ 有一点偏离

22.25GHz，然后再进行优化得到 $L _ { 1 } = L _ { 2 } = 1 . 8$ 1mm。

![](images/cdfbbeb6f3f3eb1c5367e64c99219855c34febf2c19ae6a619eb0a54050e8713.jpg)  
图5 $L _ { 1 } = L _ { 2 } = 2 . 1 m m$ 以及 $L _ { 1 } = L _ { 2 } = 1 . 8 1$ mm的带阻滤波器仿真结果

Fig.5 Simulated results of bandstop filter of $L _ { 1 } = L _ { 2 } = 2 .$ 1mm and $L _ { 1 } = L _ { 2 } = 1 . 8$ 1mm

中心频率除了和方环周长有关，还和加载枝节的长度有关，这里加载开路调节枝节长

度为 $\lambda _ { g } / 4 \AA ^ { [ 6 ] }$ ，然后进行仿真优化设计，得到 $L _ { 3 } = 2 . 4 5 m m$ 。本文设计18-26.5GHz的滤波器，

中心频率是 $2 2 . 2 5 \mathrm { G H z }$ ，然后进行仿真优化，得到 $L _ { 1 } = L _ { 2 } = 1 . 9 m m$ ， $L _ { 3 } = 2 . 1 9 m m$ 。特性

阻抗比

$$
\boldsymbol { a } = Z _ { 1 } / Z _ { 2 }
$$

的不同取值，可以得到不同的带宽，然后取

![](images/b478469aecd4532a61625896abc6f1d5d7bc42547e13771bb2bb17348de72c6e.jpg)

$a = 1 . 2 . 3$ 进行仿真，仿真结果如图6。最后优化得到 $\qquad W _ { _ { 2 } } = 0 . 2 3 m m$ 时，得到18-26.5GHz的1dB带宽滤波器，如图7。

![](images/0a5b71286848b481292e8157d7fe7df046b6003dfd89a980b822281d2e368f42.jpg)  
图6 $a$ 取不同值的仿真结果  
Fig.6 Simulated results of different a

![](images/60811db7a15605d70c27ae17072cda46873dad50abaf06d2f697378f61a177f5.jpg)  
图8单环谐振器的滤波器的实物图  
Fig.8 Photograph of Filter using one ring   
图9单环谐振器的滤波器仿真和测量结果图  
Fig.9 Measurement and Simulation of Filter using one ring

由图9可以得到，测试结果和仿真结果的吻合度很高。测试结果为中心频率22.15GHz，3dB带宽为 $4 2 . 8 \%$ ，在17.4GHz-26.9GHz频带内的回波损耗小于-20dB，插入损耗为-1.05dB，15.1GHz-16GHz和28.1GHz-28.9GHz的阻带抑制度大于35dB。

由测试结果可知，单环谐振器的滤波器，它的边带不是特别陡峭，同时带外抑制也不强，为了获得比较强的带外抑制，在这里增加一个方环形谐振器，结构如图10，实物图如图11。

两个谐振器之间由 $\lambda _ { g } / 4$ 的微带线进行级联。最后进行仿真优化确定级联的微带线长$\boldsymbol { L } \boldsymbol { \mathrm { c } } = 1 . 9 m m$ 。仿真和测试结果如图12。

++ Output

17.28mm 室 14.82mm 十十 I

![](images/055845e3210938d31a9b1e6d54f38089a9fbbf47922a0b10c9355113e124c8ec.jpg)  
图12双环谐振器的滤波器仿真和测量结果图  
Fig.12 Measurement and Simulation of Filter using two ring

由图12可以得到，测试结果和仿真结果的吻合度很高。测试结果为中心频率22.1GHz，3dB带宽为 $3 9 . 8 \%$ ，在17.7GHz-26.5GHz频带内的回波损耗小于-14dB，插入损耗为-1.27dB。12.8GHz-15.3GHz和27.9GHz-30.6GHz的阻带抑制度大于35dB。

# 3总结

本文通过在正交直连馈线弯曲方环双模带阻滤波器上加载一对开路调节枝节设计得到带通滤波器，设计了一个方环形谐振器滤波器和两个方环形谐振器滤波器，输入输出为$5 0 \Omega$ 馈线直连在弯曲方环谐振器上，在输入输出的对角上加载短路枝节，获得一个宽带滤波器。从仿真和测试结果看，两个滤波器都满足设计要求，其中两个方环形谐振器滤波器的带外抑制和边带陡峭度优于一个方环形谐振器滤波器，但插入损耗和回波损耗却比一个方环形谐振器滤波器较差。

参考文献：

[1]Purcell CR,Longmore SN，Walsh AJ,et al. The $\mathbf { H } _ { 2 } \mathbf { O }$ Southern Galactic Plane Survey: $\mathbf { N H } _ { 3 }$ (1,1) and (2,2) catalogues[J]. Mothly Notices of the Royal Astronomical   
Socity,2012,426(3):1972-1991.   
[2]张鲁红,杨雪霞,马哲旺.SIR 实现的新型毫米波UWB 滤波器[J].无线电通信技术, 2013,39(3) :53-56.   
Zhang Luhong, Yang Xuexia, Ma Zhewang. Novel Milimeter-wave ultra-wideband filter using stepped-impedance resonators[J]. Radio Communications Technology, 2013,39(3): 53-56.   
[3]王路超，金龙.一种基于正放环形谐振器的新型宽带带通滤波器[J].火控雷达技术， 2013,42(3) :75-77.   
Wamg Luchao,Jin Long.Anovel wide-band band-passfilter based onsquare ring resonator[J].Fire Control Radar Technology, 2013,42(3): 75-77.   
[4]李雅静，冯立营，刘新月.调谐短截线弯曲方环宽带带通滤波器设计[J].天津职业技术师 范大学学报，2016,26（3）:40-42.   
Li Yajing,Feng Liying,Liu Xinyue.Wideband bandpassfilter based on meander square loop using tuning stub[J]. Journal of Tianjing University of Technology and Education,2016,26(3): 40-42.   
[5] Cai Peng, Ma Zhewang, Guan Xuehui, et al. Compact millimeter-wave ultra-wideband bandpass filter using dual-mode ring resonator and multiple-mode parallel-coupled line   
structure[C]//Proceedings of Asia-Pacific Microwave Conference.2006: 163-166.   
[6] Hsieh L H, Chang K. Compact, low insertion loss, sharp rejection wideband bandpass filters using dual-mode ring resonators with tuning stubs [J] .IEEE Transaction on Microwave Theory and Technique，2003，51（4）：1241-1246.

# Study of K band Bandpass Filters Using dual-mode loop of Tian Ma telescope

Chen Li，Li Bin

(Shanghai Astronomical Observatory，Chinese Academy Sciences，Shanghai 20o30，China，Email:cl@shao.ac.cn)

Abstract:This paper presents a low insertion-loss, sharp-rejection,and wide-band dual-mode microstrip bandpass Filter using meander square loop with two tuning stubs,which apply to integrated down converter modules for Tian Ma K-band focal plane array. The designed filter is based on a bandstop filter, witch uses a meander ring resonator with direct-connected orthogonal feed lines, uses two tuning stubs to construct a wide-band passband with two sharp stopbands.

This paper presents a filter using one ring and a filter using two cascaded ring. The measured results show that 3dB bandwidth of the filter using one ring is $4 2 . 8 \%$ , a return loss of large than 20dB from 17.4GHz-26.9GHz, insertion-loss is -1.05dB,and two rejections of greater than 35dB within 15.1GHz-16GHz and 28.1GHz-28.9GHz.And the 3dB bandwidth of the filter using two cascaded ring is $3 9 . 8 \%$ ,a return loss of large than 14dB from 17.7GHz-26.5GHz,insertion-loss is -1.27dB,and two rejections of greater than 35dB within 12.8GHz-15.3GHz and 27.9GHz30.6GHz.The measured results of the two filter are highly consistent with the simulation results. Key words: multi beam; Tian Ma telescope;dual mode;bandpass filter;

项目类别：国家自然科学基金(11473060);国家自然科学基金 (11590784);科技部国际合作专项(2015DFA10720);国家高技术研究发展计划(863 计划)(2014AA123601)