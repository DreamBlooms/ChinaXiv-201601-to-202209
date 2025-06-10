# 高速涡轮泵额定工况空化特性及压力脉动预测

张皓晨 左志钢 刘树红 吴玉林（清华大学，水沙科学与水利水电工程国家重点实验室北京100084)

摘要：本文通过SSTk-ω湍流模型和 ZGB空化模型对某种涡轮泵进行了空化流场计算，得到了其水力性能曲线和空化性能曲线，对设计工况下涡轮泵内部流场和压力脉动特性进行了分析。结果表明，涡轮泵易在三个位置发生空化，诱导轮前后的压力脉动主要由诱导轮叶片通过频率决定，蜗壳内部压力脉动受动静干涉影响较大。

关键词：涡轮泵；诱导轮；空化；压力脉动；数值模拟中图分类号： V4342 文献标识码：A

# Characteristics of Cavitation and Prediction of Pressure Fluctuation at Rated Condition in High-speed Turbopump

Zhang Hao-ChenZuo Zhi-GangLiu Shu-HongWu Yu-Lin (State Key Laboratory of Hydroscience and Engineering,Tsinghua University,Beijing 1Ooo84, China)

Abstract: This paper used SST $\mathbf { k }$ -@ turbulence model and ZGB cavitation model to simulate cavitation flow field in a turbopump. Its hydraulic performance curves and cavitation performance curves were obtained and the inner flow distribution and pressure fluctuation characteristics in this turbopump were analyzed under the design point. Results show that there are three cavitation regions,and the pressure fluctuation in the front of inducer and behind the inducer is determined by the inducer blade passing frequency. Rotor-stator interaction impacts the pressure fluctuation in the volute.

Key words: turbopump; inducer; cavitation; pressure fluctuation; numerical simulation 0引言

对于液体火箭发动机，涡轮泵是关键部件之一，但是随着涡轮泵向高速大功率密度发展，对于涡轮泵的空化性能有着更高的要求。在涡轮泵中，诱导轮是提高主泵空化性能的主要途径，虽然诱导轮可以在一定空化条件下运行，但是仍然会产生稳定性问题。1999 年日本H-II火箭发射器发射失败，发动机残骸在海中发现，根据分析，LE-7发动机的涡轮泵诱导轮中发生了空化不稳定性现象，导致发动机出现故障，最后火箭发射器坠落[1];P&W公司为NASA研发航天飞机主发动机的改进型高压液氧涡轮泵，研制中空化引起了严重的振动现象，导致诱导轮叶片被破坏，试验也因此提前停止[2]。因此研究涡轮泵内部空化流场及压力脉动有助于其内部流动稳定性的分析和优化。

由于涡轮泵空化实验不易开展，因此目前研究其内部流动的方法主要是数值模拟。M.M.Athavale等人[3使用了CFD-ACE $^ +$ 软件，采用全空化模型和标准湍流模型k-ε模型，其中蒸汽输运方程是基于Rayleigh-Plesset方程和其它条件导出，计算了 SSME 涡轮泵的诱导轮和离心泵的流场。该文通过捕捉流场中细微变化，发现了在不同情况下空泡长度的变化和空泡所在的区域。HosangadiA等人[4和DormeyD等人l5采用标准k-ε模型对单一诱导轮进行了数值计算，模拟了其内部空化，分析其不稳定问题原因。本文通过使用Fluent软件对某一涡轮泵内空化流场进行了模拟，分析了其内部空化区域及产生原因，并且讨论了影响内部压力脉动的原因。

# 1数值计算方法

本文对涡轮泵进行建模，将其划分为进口段、诱导轮、离心轮、蜗壳、出口段五部分，全流道几何模型见图1。采用六面体对进出口及蜗壳进行网格划分；采用四面体对诱导轮和离心轮进行网格划分，对于诱导轮叶尖和管壁之间的间隙进行加密。涡轮泵主要参数及计算边界条件见表1。为了保证结果的准确性，本文进行了网格无关性验证，见图2，本文使用547万网格进行计算。

# 表1涡轮泵参数及计算条件

Tab.1 Parameters of turbopump and simulation conditions

涡轮泵参数  

<html><body><table><tr><td colspan="2">设计转速(r/min) 40000</td></tr><tr><td>设计流量(L/s) 进口压力(Pa)</td><td>3.1 202650</td></tr><tr><td>诱导轮叶片数</td><td>2</td></tr><tr><td>离心轮叶片数</td><td>6长6短</td></tr><tr><td>计算条件</td><td></td></tr><tr><td>相流模型</td><td>混合物模型</td></tr><tr><td>湍流模型</td><td>SSTk-@ 模型</td></tr><tr><td>空化模型</td><td>ZGB 模型</td></tr><tr><td>进口条件</td><td>速度进口</td></tr><tr><td>出口条件</td><td>压力出口</td></tr><tr><td>压力速度耦合</td><td>SIMPLEC算法</td></tr><tr><td></td><td></td></tr><tr><td>差分方法</td><td>二阶迎风格式</td></tr><tr><td>温度</td><td>20℃</td></tr><tr><td>工质</td><td>水/水蒸汽</td></tr><tr><td>时间步长(s)</td><td>2.083x10-6</td></tr><tr><td>收敛残差</td><td>10-5</td></tr></table></body></html>

![](images/1caccabc69a719f8b237fe52572d0f6363deb7f19209b4e31d6b5a2ef5310b9e.jpg)  
图1涡轮泵全流道几何模型 Fig.1 Profile of turbopump

![](images/be353e6d1b3dbbb248f5dd22f7ff17b7682ed4e69d50ba7d5211b800a29c65b2.jpg)  
图2网格无关性验证Fig.2 Grid-independent verified

# 2定常计算结果分析

本文采用定常数值模拟方法，预测了涡轮泵的外特性曲线，如图3所示。对于本文的涡轮泵来说，在约1.1Q0 附近处，效率出现最大值；在设计工况下，效率为 $67 \%$ ，设计工况下的扬程达到了 $5 3 2 \mathrm { m }$ 。本文改变进口压力，得到涡轮泵的空化性能曲线（图4)。临界空化点一般取效率下降 $3 \%$ 的工况点，从图中可以发现设计工况对应的是临界空化点，推测本文使用的涡轮泵仍存在优化的空间。

![](images/3455bfe2fa8a9526fc6c1d6d342d3b43b660e8b7b49b71022c0c7698f8e38ba5.jpg)  
图3水力性能曲线 Fig.3 Hydraulic performance curves

![](images/ac983fb3ceba011a2f0b29da8ec34cb81a3903c0fabf0c5e960fb3f91b5ad13d.jpg)

图4空化性能曲线  
Fig.4 Cavitation performance curves  
诱导轮两个叶片的吸力面和压力面的压力分布如图5所示，可以看出诱导轮内的低压区

有两个位置，一个是诱导轮叶片进口轮缘处，另一个是诱导轮叶片出口靠近轮毂处。可以从图中看出，诱导轮两个叶片的吸力面的压力变化趋势是一致的，压力面亦如此，同时压力面的压力比吸力面大。

![](images/c51938738f5cdb90bee870c541e4e6916971a88185d00711f9574302e448fd13.jpg)  
图5诱导轮压力分布 Fig.5 Pressure in the inducer blades

图6显示诱导轮轴截面的流线分布情况，可以看出在诱导轮叶片进口处有回流涡存在，这是诱导轮的进口回流现象。诱导轮的进口回流包含了垂直轴面方向的漩涡和绕流线的回旋流这两类。这是因为诱导轮旋转的叶片对流体的作用力不均匀，由于离心力的作用，在诱导轮叶片外缘处与轮毂处之间会产生压差，但是由于叶片始终旋转着，这种运动压差也一直保持着，因此会造成流体从叶片进口外缘倒流到进口管段，这些回流部分在主流中会使得主流做旋转运动。同时在实际运行状态下，实际液流角会比设计工况下的液流角小一些，这会使得诱导轮叶片进口前缘产生不均匀的圆周速度分量，圆周速度分量产生了绕流线的漩涡。诱导轮进口回流会造成局部低压。

![](images/d69e76482abd21946dfec30e21e1839cb0bfe72454ae302aebc0ba8e6f0755d5.jpg)

设计工况下涡轮泵流道内部的空化区域见图7a。空化区域主要发生在三个地方，分别在诱导轮叶片入口轮缘处，诱导轮出口靠近轮毂处，离心轮长叶片吸力面进口处，这三个区域都是低压区。在相同工况下，计算了无诱导轮时离心叶轮内部的空化流场。对于离心叶轮内空化区域（图7b），可以看到没有诱导轮的条件下，离心叶轮内部空化从离心轮进口一直延伸到各个流道的中后段。通过对比可以发现，诱导轮能改善离心叶轮内的空化性能。

![](images/071d69d634536cb48a558fdd0363389a98d8e52dfbee9fa207bc0ad5ebe4b499.jpg)  
图6诱导轮回流涡 Fig.6Backflow vortex in inducer   
图7涡轮泵空化区域 Fig.7 Cavitation regions in turbopump

![](images/28d3538dde42670333aa4e1650eec1d4f33a4a7952d88048306c0f8d4b65a3d8.jpg)  
图8诱导轮出口压力与速度分布 Fig.8Pressure and velocity in inducer outlet

在诱导轮叶片入口轮缘处，空化区域狭长，流体的相对速度较大，叶片没有对流体做功，流体对诱导轮叶片边缘造成很大的速度冲击，使得压力较低，同时诱导轮进口回流也会造成局部压力降低，当压力低于水的饱和蒸汽压，于是会产生空化区域。

高速涡轮泵的流量系数小，容易发生脱流失速的问题。脱流失速现象最先发生在轮毂位置处，这会导致在出口处发生压力和速度的分布不均的现象，如图8所示，又由于诱导轮中离心力的作用，液体被甩到轮缘处，所以轮缘处压力大，轮毂处压力小，这就会产生出口位置的涡流区，并且出口涡流区和离心轮的进口回流也有很大关系。出口涡流会使得流体能量损耗，此部分的总压有所降低，同时出口速度分布不均，在低压位置的速度比较大，于是很容易发生空化，使得诱导轮的出口靠近轮毂处有一部分空化区域。由于诱导轮的出口部分区域有空化，并且诱导轮的出口存在涡流，这都会严重影响到离心轮空化性能，因此离心轮长叶片吸力面的进口处会有空化。

# 3空化非定常结果

为了检测流场压力脉动情况，本文共布置了20个监测点，如图9所示。监测点1-4均匀分布在诱导轮叶片进口前，监测点5-8均匀分布在诱导轮叶片出口至离心轮入口之间，监测点9-20均匀分布在蜗壳内部。

![](images/6f9b72b694e0f87a6724a577e9161ebb759696a85ee1b881a2eb26d05d6a14aa.jpg)  
图9测点位置定义Fig.9Locations of monitor points

对压力脉动进行傅里叶变换(FFT)，得到的频域图如图10所示。诱导轮前的压力脉动的主频为诱导轮叶片通过频率。诱导轮和离心轮之间的压力脉动的主频为诱导轮叶片通过频率，并且主频在周向幅值变化很大，次频为3倍诱导轮叶片通过频率，同时离心叶片通过频率也对此区域的压力脉动产生影响，但是变化不大，故在诱导轮叶片旋转对于诱导轮出口处的压力脉动会造成很大影响。蜗壳内各流道出口位置的压力脉动的频率有诱导轮、离心轮叶片通过频率及其二次谐频，从图中发现蜗壳内的4倍转频的幅值变化比较大，测点16（位于隔舌附近）的4倍转频的幅值很高，同时离心轮叶片通过频率的压力脉动幅值变化比较大，这是由于旋转的叶轮和蜗壳动静干涉引起的。

![](images/5f2cdbb1e8aec51fa85263d2856c4a956a26313bc9fe4ace93d56f47a74d5387.jpg)

![](images/39355722aa284725b2f50cabd3381071045fd8a53ce44a11ef470cb8090d2f25.jpg)  
图10各测点压力频域图Fig.10 Pressure at frequency domain

# 4结论

采用ZGB空化模型可以预测涡轮泵内空化流动。涡轮泵内主要发生空化的区域为诱导轮叶片进口边缘处、诱导轮出口靠近轮毂处、离心轮叶片进口处。本文计算的涡轮泵仍有改进空间，可以通过改变诱导轮进出口角及离心叶片进口角来优化。涡轮泵诱导轮前压力脉动主频为诱导轮叶片通过频率，诱导轮和离心轮之间的压力脉动受诱导轮旋转影响较大，蜗壳内压力脉动受动静干涉影响较大。

# 参考文献

[1] Ono A, Warashina S,Tomaru H,et al.Development of Cryogenic Turbopumps for the LE-7A Engine[J]. IshikawajimaHarima EngineeringReview,2003,43(5):156-160.   
[2]Ryan R S.The Space Shutle Main Engine liquid oxygen pump high-synchronous vibration issue, the problem, the resolution approach, the solution[J]. Space,1994, 94(31):53.   
[3] Athavale MM, Singhal A K.Numerical analysis ofcavitating flows in rocket turbopump elements[Cl//37th AIAAJoint Propulsion Conference. 2001.   
[4] Hosangadi A,Ahuja V,Ungewiter R J,et al. Numerical study ofa flat plate inducer:comparison of performance in liquid hydrogen and water[C]//Proceedings of the 42nd AIAA/ASME/SAE/ASEE Joint Propulsion Conference & Exhibit.2006: 7210-7222.   
[5] DormeyD,Griffin L,Marcu B,et al. Unsteady flow interactions between the LH2 feed line and SSME LPFP inducer[J].AIAA Paper,2006, 5073.