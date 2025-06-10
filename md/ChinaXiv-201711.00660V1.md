# 轴流压气机叶顶间隙泄漏流的周向传播特性实验研究

李继超」白冰12 耿少娟1\*聂超群1（1.中国科学院工程热物理研究所，北京100190）

（2．中国科学院大学，北京100190）

摘 要：在一台单转子低速轴流压气机上，以叶顶间隙泄漏流非定常性为切入点，通过实验测量沿弦向和周向的壁面非定常压力，分析了叶顶端区非定常波动特征沿叶片弦长的调频特性。研究了占主导地位的叶顶间隙泄漏流非定常波动沿周向的传播特征，进一步分析叶顶间隙泄漏流非定常性波动到失速先兆信号产生的演变规律。实验结果表明，由叶顶间隙泄漏流非定常性波动主导的叶顶端区流场在压气机节流过程中，其周向传播速度逐渐增加，直到失速先兆的产生。由此可以判断，叶顶间隙泄漏流非定常性是失速先兆信号分析和预测的流场依据，为澄清和理解叶顶间隙泄漏流非定常和失速先兆至失速的不同流动特征的统一流体力学机理提供指导。

关键词：压气机；叶顶间隙泄漏流非定常性；周向传播；失速先兆；功率谱密度；均方根中图分类号： 文献标识码：

# Experimental Investigation on Circumferential Propagation of Tip Leakage Flow in Axial Compressor

Li Jichao' Bai Bing1,2 Geng Shaojuan'\* Nie Chaoqun11 (1.Institute of Engineering ThermophysicsChinese Academy of SciencesBeijing 100190, China)

(2.University of Chinese Academy of SciencesBeijing 1oo19o, China

Abstract:Thecircumferentialpropagationof thedisturbancewhichisdominatedbytheunsteadinessof tipleakageflowhasben studiedbaseontheunsteady measurement alongthebladechordand circumferentialdirectionin this paper.Thentheevolutions from theunsteadinessoftipleakagefowtostallinceptionwiththrotlingofthecompresoareaalyedfurter.Texperimentalsults indicatethatthecircumferentialpropagationseedoftheunsteadytipleakageflowwillincreaseduringthethrotlingprocess,tis phenomenon willocursonlyaftertheappearanceoftheunsteadinessoftipleakageflow.Itdemonstrates thattheunsteadinessf tip leakageflowisthbasisofthanalysisandpredictionotallinceptio,andalsoprovidestegudanceofunderstandingofefo flow mechanism between the unsteady tip leakage flow and stallinception process.

Keywords:compresor;unsteadinessof tipleakageflow;circumferential propagation；stallinception；powerspectrumdensity; root-mean-square

# 0前言

旋转失速是压气机进入不稳定工作状态的主要因素，国际上对其进行了长达几十年的研究。早期主要关注失速现象本身的表现特征，如失速团、传播速度等，主要通过实验和系统建模进行研究[1-2]。为了有效预测和避免失速的发生，在失速先兆信号的检测和触发机理研究上进行了大量的研究[3-7]，这也成为了目前国际上已经形成的主/被动控制方法的

主要基础。

是失速先兆检测方法，另一个是前失速先兆特征—叶顶间隙泄漏流为主的叶顶端区流动特征。前者主要以麻省理工学院对长尺度失速先兆检测[3-4]和剑桥大学Dayl5对短尺度失速先兆检测的工作为代表。由于实际压气机失速先兆大多数表现为后者，这也引起了学者们的关注。Inoue 等发现在近失速工况叶顶区域表现出强烈的非定常性波动，且与叶片通过频率有关，这一现象可用于判断失速先兆的出现。Hoying等通过数值计算发现，在突尖失速先兆发展过程中，主流与叶顶间隙泄漏流动态平衡形成的交界面随着压气机节流向叶片上有移动。 $\mathrm { V o } ^ { [ 8 ] }$ 在一台低速轴流压气机上通过进一步的研究提出了突尖型失速先兆的判定准则，而且该准则同样适合于跨音轴流压气机[9]。对流场的认识和理解最终要服务于应用，国际上也有学者针对叶顶间隙泄漏流开展了相应的检测和控制工作[10-16]。Tahara 等[1]通过检测壁面压力锯齿波周期性的破坏程度，采用相关性分析法成功预测和控制压气机失速先兆的发生，并推测锯齿波的破坏与叶片顶部泄漏流有关。童志庭等[13]提出了基于自相关分析检测的微喷气控制策略，并成功地拓宽了压气机流动失稳裕度。本文作者[15-16]也设计了基于互相关分析检测壁面压力锯齿波破坏程度的叶顶喷气控制系统。大量实验和数值计算结果均表明，大间隙小流量工况附近叶顶端区表现出周期性非定常波动特征，并在越来越多的低速和跨音轴流压气机上得到了证实[17]。虽然不同研究者对这一现象的说法有所不同，但就所描述的现象本身来看并没有本质的区别，均与叶顶间隙泄漏流有着密切的关系。目前国际上广泛采用了一种说法是"旋转不稳定性”，文献[18-20]现象研究了叶顶端区非定常波动频率与轴向传播特征。文献[21]研究了叶顶间隙泄漏流周期性非定常波动主导的动叶端区非定常频率和流场特征，并从压差驱动的角度阐述了叶顶间隙泄漏流周期性非定常波动的出发机理。可以看出，国际上已初步认同了叶顶间隙泄漏流非定常性的存在及其在压气机失速过程中扮演的重要角色。但是仍然缺乏对叶顶间隙泄漏流非定常性与失速先兆内在联系的认识。剑桥大学的 Young[22]利用非轴对称间隙实验测量并分析了大间隙区域的叶顶非定常波动频率和周向传播特征。耿少娟[23]通过对一台低速轴流压气机进行全圆周数值模拟，考察了叶顶间隙泄漏流非定常周向传播特征及其在节流过程中的演变特征。中述￥工牛沛牛业红和触出药测

方法的分析可见，均聚焦在对叶顶间隙泄漏流主导的叶顶端区流动。而且失速先兆产生和传播与叶顶间隙泄漏非定常波动之间存在某种联系。本文以此为切入点，通过实验测量手段考察叶顶间隙泄漏流非定常波动在压气机节流过程中的周向传播特性，为理解和澄清从叶顶间隙泄漏流非定常波动到失速先兆之间的过渡提供依据。

# 1．实验台及测量方法

本文实验是在一台低速轴流压气机上完成，实验台的相关气动参数参见文献[24]。实验中为了获得详细的壁面弦向和周向非定常压力，采用的传感器安装方式如图1所示。在弦向同时安装三排动态压力传感器，以及在靠近叶片前缘位置沿周向布置两排动态压力传感器。实验中为了尽可能准确获得压气机的壁面流场以及保证压气机特性线的重复性，对特性线进行多次重复性实验，如图2所示。在重复性比较好的条件下，在进行相应的动态测量。

Trailing edge CH6 CH5 00 00 CH4 8 8 CH3 。 。 Q 。 Q ○ Q ○ 。 D O 。 Q CH2 。 ○ ? ○ ○ G 。 。 G ○ ○ 4 。 。 9 CH1 O 。 。 Leading edge Rotating direction

![](images/ca6459df02ab0eed24bfa71bc7978b28bf2ce14db8270fb95c7a89126e3eb78e.jpg)  
图1传感器安装方式  
Fig1.Arrangement of dynamic sensors   
图2压气机特性线  
Fig2.Characteristic line of the proposed compressor

# 2.叶顶间隙泄漏流非定常性的周向传播特性

首先根据图1中沿弦向布置的CH1-CH6传感器测量了不同流量工况的壁面静压云图，比较了大流量工况（ $\Phi { = } 0 . 5 8$ ）和近失速工况（ $\Phi { = } 0 . 4 8 \rangle$ 壁面静压云图。从图3和图4所示为三排传感器测得的不同流量工况的壁面云图，根据图中标注的旋转方向可以判断，单个叶片的传播速度和压气机旋转速度（NS）一致。因叶片旋转速度占主导作用，看不到任何其他扰动的产生和传播。而前面大量文献[17,24,25]已经得出对于叶顶间隙大于某一临界值之后，压气机在向失速点靠近过程中会产生很强的叶顶间隙泄漏流非定常性。为此，本文也从叶顶间隙泄漏流非定常性入手，对壁面静压扰动进行了分析。

![](images/482d197b9bde89d58c006f615d57d4c217d42f67ff6cfaab17ffe519de0d4f8a.jpg)  
图3 $\Phi { = } 0 . 5 8$ 时弦向三排传感器对应的压力云图Fig.3 Pressure contour of the three column sensors( $\Phi { = } 0 . 5 8 )$ （2

旋转方向  
旋 803 0000  
转 20 .10 15  
方 83012° 000 ?0 15  
向 830 31 5 10 NS 15Time(Blade passings)

图5对三个工况不同弦向位置的非定常压力进行了PSD分析。从图中可以明显看出0.4BPF左右特征频带的幅值随压气机节流而增加的趋势，而且前面已经证明该特征频带为叶顶间隙泄漏流非定常性[17]。从图中可以看出，在近失速工况时， $20 \%$ 弦长左右的位置叶顶间隙泄漏流非定常性非常强。在图中除了叶顶间隙泄漏流非定常性的周期性扰动以外，看不出其他任何扰动的存在。因此在接下来研究周向传播特性时，采用带通滤波的方式考察不同频带扰动的周向传播特性。

-Large flow coeffcient-e- Low flow coefficient-\* Near stall point 4000 40 3000 Axial location=-0.192 3000 Axial location=0.406 2000 2000 1000 1000 0 0 0 0.5 1 0 0.5 1 4000 4000 TAT   
iphte 3000 Axial location=0.01 3000 Axial location=0.624   
p   
Am 1000 1000 0 0 0 0.5 1 0 0.5 1 4000 4000 3000 Axial location=0.202 3000 Axial location=0.809 2000 2000 1000 1000 0 0.5 0 0.5 1 Normalized frequency(/Blade passing frequency)

根据前面的分析结果可以看出，叶顶间隙泄漏流的非定常性所分布的频带为0.26-0.6BPF。因此，首先对该频带进行了带通滤波，并重画了壁面压力谱，如图6所示，为压气机近失速工况—流量系数为0.48时的壁面静压云图。根据图中的旋转方向以及图1中三排弦向安装的传感器检测到的图中黑色箭头所示区域，可以明显判断出该频带信号存在周向传播特性，其传播速度大约为0.43NS。而在相同流量工况下对其他低于BPF的频带进行带通滤波时，如图7和图8所示，分别为对0.08-0.2BPF以及0.7-0.96BPF进行带通滤波之后壁面静压云图。相比于图6中叶顶间隙泄漏流非常明显的周向传播特性，图7和图8中并不存在任何周向传播现象。

![](images/3ddc1b960a2aedb95b0b575fb6b1c5ca32b59f6b2a3da4aa97c6f5a55e89a456.jpg)  
图5 壁面沿轴向非定常静压的PSD分布 Fig.5PSD distribution of sensors along the axial direction

在初步判断叶顶间隙泄漏流非定常性扰动在近失速工况存在周向传播特性之后。为了明确和证实压气机在节流过程周向传播特性的起始位置以及传播速度在节流过程中的变化，采用沿周向布置安装的传感器对叶顶间隙泄漏流非定常性扰动的周向传播特性进行了进一步研究。

![](images/3668b4a548867300aae2d844c061edaf92b55e9111f8e6c2552c83f382c30686.jpg)  
图4 $\Phi { = } 0 . 4 8$ 时弦向三排传感器对应的压力云图Fig.4 Pressure contour of the three column sensors( $\Phi { = } 0 . 4 8 )$ （  
图60.26-0.6BPF低通滤波之后 $\Phi { = } 0 . 4 8$ 时的壁面三排传感 器的压力云图 Fig.6 Pressure contour of the three column sensors( $\Phi { = } 0 . 4 8 )$ with 0.26BPF-0.6BPF band pass filter   
图70.08-0.2BPF低通滤波之后 $\Phi { = } 0 . 4 8$ 时的壁面三排传感 器的压力云图 Fig.7 Pressure contour of the three column sensors( $\Phi { = } 0 . 4 8 \dot { }$ with O.08BPF-0.2BPF band pass filter

![](images/d35d82f7af79ba9264e577238b94d5ad0af8ab86162a96d11b57438bbcacd674.jpg)  
图80.7-0.96 BPF 低通滤波之后 $\Phi { = } 0 . 4 8$ 时的壁面三排传感 器的压力云图 Fig.8 Pressure contour of the three column sensors( $\Phi { = } 0 . 4 8 \dot { }$ 1 with O.7BPF-0.96BPF band pass filter

# 3．叶顶间隙泄漏流非定常性的周向传播特征演变

前面分析了弦向布置三排传感器检测到的叶顶间隙泄漏流非定常性的周向传播特征，发现了只有叶顶间隙泄漏流非定常性对应频带扰动会发生低于压气机旋转速度的周向传播。为了更加详细的分析其在节流过程中周向传播速度的变化，在叶顶间隙泄漏流非定常性比较强的轴向位置，即轴向弦长为$20 \%$ 的地方沿周向布置了15个传感器。同时也叶片前缘布置了15个传感器用于捕捉从叶顶间隙泄漏流非定常性周向传播到失速先兆周向传播的动态过程

图9所示为在压气机节流过程中，不同流量工况下， $20 \%$ 轴向弦长位置叶顶间隙泄漏流频带（0.26-0.6BPF）的周向传播速度的变化过程。从图中可以看出，在大流量工况下，叶顶间隙泄漏流非定常性比较弱（图5的功率谱密度所示)，此时的周向传播速度仍然受叶片旋转速度的影响，其传播速度为1NS。而随着压气机节流阀的关闭，在流量系数为0.54时，开始出现了和叶片旋转速度不一样的传播速度，其速度为0.404NS。随着流量系数的不断减小，从图中黑色箭头显示的斜率即可判断，叶顶间隙泄漏流非定常性的周向传播速度不断增加，特别是在失速过程中（图9(e))，图中同时显示了叶顶间隙泄漏流非定常性的传播速度（0.48NS）和失速先兆的传播速度。失速先兆的传播速度与图10的周向均匀布置的9个传感器测得的压力脉动显示的传播速度一致，均为0.578NS。可以看出，叶顶间隙泄漏流非定常性的传播速度在不断向失速先兆传播速度过渡，也就是说，叶顶间隙泄漏流非定常性传播速度的不断加剧，最终会导致失速先兆的产生。

![](images/4450fd27c966edbd57cdd1b970915e92012a7a439da936899a744619db0c2675.jpg)  
图9压气机节流过程中 $20 \%$ 弦长处周向传播特性 Fig.9 Circumferential Propagation of the tip leakage flow at the location of $20 \%$ axial chord in the throttling process

![](images/57e66fe440f6242fb6092efb56e9c606e8da6d97b715a63a08fffeae5a274258.jpg)  
图10压气机失速先兆传播速度 Fig.10 Spike stall inception and its propagation

# 4.结论

本文在一台低速轴流压气机通过实验测量手段获取了详细的弦向和周向壁面非定常压力，研究了叶顶间隙泄漏流非定常性频谱特性、周向传播特性以及周向特征演变过程，为数值计算分析提供了依据。得出了以下几点结论：

1）在压气机节流过程中存在扰动周向传播的特征，只发生在叶顶间隙泄漏流非定常性出现之后。通过对不同频带信号进行带通滤波之后，发现只有叶顶间隙泄漏流非定常性所表征的扰动会发生周向传播现象。

2）压气机在节流过程中，叶顶间隙泄漏流非定常性产生之后，其周向传播速度会随着流量的进一步减小而增加。实验测得失速先兆周向传播速度为0.578NS，而在失速先兆产生之前，叶顶间隙泄漏流非定常性周向传播速度为0.48NS左右。这也就意味着失速先兆周向传播与叶顶间隙泄漏流非定常性周向传播之间有着直接的关系。

# 参考文献

[1]Takata H，Nagano S. Nonlinear Analysis of Rotating Stall [J]．ASME Journal of Engineering for Power,1972, 94(4):279-293   
[2]Day I J, Greitzer E M, Cumpsty N A. Prediction of Compressor Performance in Rotating Stall [J].ASME Journal of Turbomachinery, 1978,100(1): 1-14   
[3]Tryfonidis M,Etchvers O,Paduano JD,et al.Prestall Behaviour of Several High-speed Compressors [J].ASME Journal of Turbomachinery, 1995,117(1):62-80   
[4]Granier V H, Epstein A H, Greitzer E M. Rotating Waves as a Stal Inception Indication in Axial Compressors [J]. ASME Journal of Turbomachinery,1991,113(2):290-302   
[5]Day IJ. Active Suppression of Rotating Stall and Surge in Axial Compressors [J]. ASME Journal of Turbomachinery, 1993,115(1):40-47   
[6]Inoue M, Kuroumaru M, Iwamoto T, et al. Detection of a Rotating Stall Precursor in Isolated Axial Flow Compressor Rotors [J]．ASME Journal of Turbomachinery,1991, 113(2): 281-289   
[7]Hoying D A, Tan C S, Vo HD,et al. Role of Blade Passage Flow Structures in Axial Compressor Rotating Stall Inception[J].ASME Journal of Turbomachinery,1999, 121(4):735-742.   
[8]Vo HD, Tan C S, Greitzer E M. Criteria for Spike Initiated Stall.ASME Journal of Turbomachinery,2008,130(1): 011023-1-9.   
[9]Du J, Lin F, Zhang HW, Chen JY. Numerical Investigation on the Self-Induced Unsteadiness in Tip Leakage Flow for a Transonic Fan Rotor. ASME Journal of Turbomachinery, 2010,132(2):021017-1-9   
[10] Tahara N,Nakajima T,Kurosaki M,et al.Active Stall Control with Practicable Stall Prediction System Using Auto-Correlation, AIAA Paper, 2001-623   
[11] Dhingra M, Neumeier Y,Prasad JV R, et al. A Stochastic Model for a Compressor Stability Measure,ASME Paper 2006-GT-91182,2006.   
[12] Christensen D , Cantin P, Gutz D,et al. Development and Demonstration of a Stability Management System for Gas Turbine Engines[C]. ASME Paper, GT2006-90324.   
[13] TONG Zhiting,LI Lin,NIE Chaoqun,et al. Online Stall Control with the Digital Signal Processing Method in an Axial Compressor [C] ASME Paper, GT2009-59509.   
[14] 李继超，童志庭，林峰，聂超群．基于互相关分析的前 失速先兆检测分析[J].航空学报.2013,34(1):28-36 LI Jichao, TONG Zhiting, LIN Feng, et al. Detection and Analysis of Early Stall Warning Based on Cross-correlation [J].ActaAeronauticaetAstronauticaSinica. 2013,Vol.34(1): 28-36   
[15] 李继超，林峰，童志庭，聂超群．轴流压气机叶顶喷气 控制实验研究[J]．航空学报.2013,34(11):2464-2471. LI Jichao,LIN Feng, TONG Zhiting, et al. Experimental Investigation of Control with Tip Air Injection in an Axial Flow Compressor [J]. Acta Aeronautica et Astronautica Sinica. 2013,34(11) :2464-2471   
[16] Kameier F, Neise W. Experimental Study of Tip Clearance Losses and Noise in Axial Turbomachines and Their Reduction[J].ASME Journal of Turbomachinery,1997, 199(3):460-471.   
[17] 耿少娟．压气机叶顶间隙泄漏流对微喷气的非定常响应 机制与扩稳效果研究[D]．中国科学院工程热物理研究 生博士论文,2007.7 GENG Shaojuan. Numerical Investigation on the Unsteady Response of Compressor Tip Leakage Flow to Discrete MicroTip Injection and ItsEfect on Stability Enhancement [D]. Institute of Thermophysics,Chinese Academy of Science(in Chinese),2007.   
[18] Marz J, Hah C, Neise W. An Experimental and Numerical InvesitigationintotheMechanismsofRotating Instability[J]．ASME Journal of Turbomachinery，2002, 124(3): 367-374.   
[19] Mailach R, Lehmann I, Vogeler K. Rotating Instabilities in an Axial Compressor Originating from the Fluctuating Blade Tip Vortes [J]. ASME Journal of Turbomachinery, 2001,123(3):453-463.   
[20] Vo H D. Role of Tip Clearance Flow in Rotating Instabilitiesand NonsynchornousVibration[J].AIAA Journal of Propusion and Power, 2010, 26(3):556-561.   
[21]邓向阳．压气机叶顶间隙流动数值模拟研究[D].北京： 中国科学院工程热物理研究所，2006. DENG Xiangyang. Numercial Simulation of Tip Leakage Flow in Axial Compressor[D]. Institute of Thermophysics, Chinese Academy of Science(in Chinese), 2006.   
[22] Young A,Day I J,Pullan G.Stall Warning by Blade Pressure Signature Analysis[C]. ASME Paper, GT2011- 45850.

# ChinaXiv合作期刊

[23]耿少娟，张小玉，聂超群，黄伟光，张宏武．轴流压气机 叶顶端区流场周向传播特性及其预测[J].机械工程学报， 2012，48(16):130-137. GENG Shaojuan,ZHANG Xiaoyu,NIE Chaoquan,et al. Circumferential Propagation Characteristics of Flow Field in Rotor Tip Region and Its Prediction as Stall Precursor [J]．JournalofMechanicalEngineering，2012, 48(16):130-137   
[24]李继超.轴流压气机叶顶喷气扩稳技术—机理及智能调 控[D]．中国科学院工程热物理研究所博士论文,2012.9. LI Jichao.Stability Enhancement Technology of Tip Air Injection in Axial Flow Compressor-Mechanism and Intelligent Control[D].Institute ofThermophysics, Chinese Academy of Science(in Chinese),2012.   
[25]童志庭．轴流压气机叶尖泄漏涡、失速先兆、叶尖微喷 气非定常关联性的实验研究[D]．中国科学院工程热物 理研究生博士论文，2006.7. TONG ZhiTing. The Interactive Unsteady Mechanism between Tip Leakage Vortex，Stall Inception and Micro Tip Injection in Low-Speed Axial Compressor[D]. Institute of Thermophysics， Chinese Academy of Science (In Chinese),2006.