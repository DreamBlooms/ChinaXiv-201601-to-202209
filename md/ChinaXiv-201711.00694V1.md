编号：167010

# 基于高空化性能的对转泵喷推进器设计

胡雷俊」，曹琳琳\*1，车邦祥1，吴大转 1,2

(1 浙江大学 能源工程学院化工机械研究所，浙江 杭州310027;2 浙江大学 流体动力与机电系统国家重点实验室，浙江 杭州310027)

摘要：推进器将动力设备发出的机械能转化成推力以驱动航行体前进，是决定航行体性能的关键动力装置。随航速提升，推进器易遭遇空化、噪声与推进效率下降等问题。结合高速推进的需求以及对转泵的性能优势，本文提出对转泵喷推进器结构，通过前后转子串联、反向旋转的形式，以更高密度的能量转化模型替代传统模式，在同等设计参数下实现转子转速、叶片载荷均相对较低，从而提升航行体推进器的抗空化性能及相关声学性能。文中基于某航行体性能参数，通过相似换算设计了实验模型泵喷及其实验系统，并基于数值模拟对推进器性能进行了研究。结果表明，对转泵喷推进器叶片的欧拉能量分布及载荷模型明显优于单转子推进器叶片，抗空化性能也有明显提高。

关键词：泵喷推进器；水下航行体；对转泵；抗空化设计；叶片载荷分布中图分类号：TH312；U664.34 文献标识码：A

# Design of Contra-Rotating Waterjet Pump Based on High Cavitation Performances

HU Lei-Jun1, CAO Lin-Lin\*1, CHE Bang-Xiang',WU Da-Zhuan1,2 (1 InstituteofProcess Equipment, ColegeofEnergyEnginering,Zhejiang UniversityHangzhou310027,China; 2 State Key Laboratory ofFluid Power & Mechatronic Systems, Zhejiang University, Hangzhou 310027,China)

Abstract: The propulsor converts the power from engine into thrust to push autonomous underwater vehicle forward. With the increase of advance speed,the propulsoris possble to sufer with cavitation，deterioration of acoustics performances and propulsion eficiency. In this paper, the contra-rotating waterjet pump with two rotors rotating oppositely is introduced as a kind of propulsion device with high density of energy. Under same design specification, therotation speed,blade loading as wellas cavitation performances are supposed to be superior to the traditional single rotor type. Based on the parameters of certain vehicle,the experimental modeland system are designed in this paper. And the loading status and Euler energy distribution ofimpeler blade in contra-rotating type are distinctively more reasonable than the single rotor type,and the cavitation performances are obviously improved.

Key words: Waterjet pump; Autonomous underwater vehicle; Contra-rotating pump; High cavitation performances design; Blade pressure distribution

# 0引言

推进器将动力设备发出的机械能转化成推力以驱动水下航行体前进，因此航行体航行速度、所需推力及工作下潜深度等因素直接决定着推进系统的形式。现在航行体主流的推进器形式为单转子螺旋桨、对转螺旋桨、泵喷推进器及导管螺旋桨。从技术角度来看，无论是螺旋桨还是泵喷推进器，随着航行体航速与推进功率的提升，其推进系统通常遭遇一系列高转速带来的问题，其中最核心的即空化、噪声和推进效率[1,2.3]。

传统形式的推进器提升推进力多依靠提升转速来实现。随推进器转速增高，流体相对速度大幅提升，高转速推进器的空化现象很难避免。就叶片空泡本身而言，其生长及脱落伴随有剧烈的宽频破裂噪声，严重削减推进器声学性能[4]；空泡的生长及脱落不断改变着叶片表面压力分布，导致叶片非定常载荷增大，高速旋转中各叶片空泡发展程度又不尽相同，致使推进器遭遇强烈振动；抗空化性能较弱的推进器叶片，甚至遭遇空泡规模陡增，致使流道大范围堵塞，做功能力及推进效率急剧下降。因而，在保证同等推进能力下转速较低是推进器向高速推进方向发展时的一个重要思路。

对转泵是一种由前后两个对旋转子串联而成的水泵，其核心理念在于前转子的出流残余能量被后转子充分利用，转化成压力水头，实现水泵整体无旋出流，大幅度增加了其能量密度。后转子对扬程的贡献远远超出传统的后置定子，并可通过转速的调节来调整扬程以及扭矩在两个转子间的分配。通过充分利用前转子的出流能量，相对于同等设计参数(流量，扬程，比转速等)下的传统水泵，此类水泵在相关理论及实验研究中均被证实具有更低的转速、更高的水力效率，更紧凑的体积结构、更稳定的性能曲线以及更优的空化性能[5-8]。

对转泵的前述优势与高速水下航行体对推进系统的需求十分吻合，虽然在外观及内部流动机理上，这种对转泵与安装导管的对转螺旋桨有很多相似之处，但从推力产生机理上来看，对转式泵喷依然属于水泵范畴，利用转子叶片扬水、流道变化来实现系统高速水流喷射以提供推进力。

本文的主要内容即是提出将对转水泵理念引入泵喷推进系统，形成面向小型水下航行体的对转泵喷推进器概念。并基于某水下航行体性能参数，通过相似换算设计了实验模型泵喷及其实验系统，并借助数值计算技术对其进行了前期研究。

# 1对转泵喷推进器设计

# 1.1对转泵喷推进器参数

本文基于某水下航行体性能参数，通过相似换算设计了第一代实验模型泵喷推进器。在最初设计验证阶段，第一代实验模型泵喷设计为轴流转子形式，由前转子、后转子及喷管三部分构成。计算模型如图1所示。

图中水流方向为从右向左，从入口向出口看，前转子沿逆时针方向旋转，后转子沿顺时针方向旋转。计算域入口距离前转子前缘约两倍直径长度，出口距离导流锥尾部约三倍直径长度，此设置已经通过网格无关性验证。采用ANSYSTurboGrid16.0对旋转体进行网格划分，为方便生成结构化网格，在导流锥尾部以后增加了一个极细的虚拟轮毂，对于水力性能计算结果的影响可忽略。

![](images/912199d10faf81a9887353a28e99e97d3501ce9284e8a216dd236dbc99ee7393.jpg)  
图1对转泵喷推进器计算模型

Fig.1 Computational model of contra-rotating waterjet pump

泵喷关键设计参数如表1、表2所示。

# 表1对转泵喷推进器性能设计参数

Table 1 Performance design parameters of contra-rotating waterjet pump   
表2对转泵喷转子几何参数  

<html><body><table><tr><td colspan="5">1</td></tr><tr><td>H/m</td><td>扬程</td><td>流量 Q/ms-1</td><td>转速 n /min-1</td><td>比转速 推力 T/kN</td></tr><tr><td>前转子</td><td>7.2</td><td>0.212</td><td>2000</td><td>ns 764.7</td></tr><tr><td>后转子</td><td>7.2</td><td>0.212</td><td>2000</td><td>-</td></tr><tr><td></td><td></td><td></td><td>764.7</td><td></td></tr><tr><td>泵整体</td><td>14.4</td><td>0.212</td><td>- -</td><td>1.5</td></tr></table></body></html>

Table 2 Geometrical parameters of contra-rotating waterjet pump   

<html><body><table><tr><td colspan="5">Wuterjetpunp</td></tr><tr><td></td><td>轮缘直径</td><td>轮毂直径</td><td>叶顶间隙</td><td>叶片数</td></tr><tr><td></td><td>D, /mm</td><td>Dh /mm</td><td>tc /mm</td><td>Z</td></tr><tr><td>前转子</td><td>200</td><td>104</td><td>0.5</td><td>5</td></tr><tr><td>后转子</td><td>200</td><td>104</td><td>0.5</td><td>6</td></tr></table></body></html>

# 1.2对转泵喷转子设计方法

泵喷推进器的高空化性能设计从两方面入手：一方面，采用对转结构减小单极转子的叶片负荷，降低转子旋转的线速度；另一方面，在对转结构的基础上，进一步对叶片翼型进行载荷优化设计。

对旋转子采用等速差异化设计。为使对转结构容易实现，优先选择等速驱动，从而简化换向机构。考虑到前后转子面向来流的位置不同，前转子更侧重抗空化性能设计，后转子更侧重推进性能设计。另外，从与航行体的匹配性能来看，驱动系统本身的平稳性是相当重要的，为消除驱动机构的残余扭转力矩，前后转子之间需要满足扭矩平衡的约束条件。

翼型设计的原则在于翼型载荷的优化。考虑到转子叶顶部分空化性能变差的问题，利用翼型设计冲角的变化实现叶顶翼型载荷的轻微减少，同时达到削弱叶顶泄露流动的效果。5个设计剖面的翼型均采用NACA4位数系列，通过指定翼型骨线最高点的相对位置 $x _ { f } / l$ 从叶根到叶顶线性增加，即载荷点逐渐后移的方式，进一步实现叶顶的卸载以改善其空化性能。表3为最终确定的翼型设计参数。

表3翼型设计参数Table 3 Design parameters of profile  

<html><body><table><tr><td>设计截面</td><td>1(Hub)</td><td>2</td><td>3</td><td>4</td><td>5(Tip)</td></tr><tr><td rowspan="3">设计冲角i/ 前 相对位置xf/l 转</td><td>0.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.00</td></tr><tr><td>0.50</td><td>0.525</td><td>0.55</td><td>0.575</td><td>0.60</td></tr><tr><td>出口落后角δ/ 10.512</td><td>9.457</td><td>7.590</td><td>6.311</td><td>6.798</td></tr><tr><td>子 攻角α/°</td><td>8.617</td><td>5.902</td><td>3.328</td><td>1.984</td><td>0.863</td></tr><tr><td>后</td><td>设计冲角i/</td><td>0.00</td><td>1.00</td><td>1.00</td><td>1.00</td><td>0.00</td></tr><tr><td>转</td><td>相对位置xf/l</td><td>0.50</td><td>0.525</td><td>0.55</td><td>0.575</td><td>0.60</td></tr><tr><td>子</td><td>出口落后角δ/</td><td>13.331</td><td>11.332</td><td>9.492</td><td>7.731</td><td>7.165</td></tr></table></body></html>

<html><body><table><tr><td>攻角α/</td><td>8.068</td><td>6.008 4.118</td><td>2.726</td><td>1.242</td></tr></table></body></html>

# 1.3喷管设计方法

喷管的设计通过控制过流面积的变化来获得均匀稳定的流场，避免流动分离，减小损失。根据收缩比1.77，参考水洞收缩段设计经验值[9,10]，初定喷管长径比 $L / D { = } 1$ 。参照文献[1]中的曲线数据，选用五次方曲线，将其转化为面积变化。内导流锥曲线为抛物线，选取长径比1，得到其曲线方程。再由面积变化和内曲线方程计算出五次方外曲线方程，并对分界点进行过渡光滑处理。最终得到的喷管曲线如图2所示。对所设计的喷管进行数值计算，发现流场均匀稳定，无流动分离，说明喷管设计合理。

![](images/dbcfbed0eb0444d9c9cd6e7dc733af15b33afe38f97b664f867c0f5174f4af06.jpg)  
图2喷管曲线  
Fig.2Nozzle curve

# 1.4数值计算方法

本研究中的数值计算采用商业CFD 软件ANSYSCFX16.0进行。水力性能及内流特性的评估计算采用全流道非定常计算方法，而空化性能评估计算采用单流道定常两相流计算方法。采用ANSYSTurboGrid16.0对计算模型进行网格划分，并进行了网格无关性分析，最终确定的前转子单流道网格数约52万，后转子单流道网格数约35万，泵整体单流道总网格数约为87万。

边界条件设置如下：入口采用质量流量入口(BulkMassFlowRate)，出口采用开放式边界(Opening)，叶片和轮毂采用旋转壁面(RotatingWall)，外壳采用反向旋转壁面(CounterRotating

Wall)。

空化计算中介质选用25 摄氏度的水和水蒸气共两相，初始气相体积分数为0，初始液相体积分数为1。湍流模型采用SST模型，空化模型采用RayleighPlesset模型。求解格式为高阶求解模式的差分格式，均方根残差值设为1e-4。

# 2对转泵喷推进器的水力及空化特性

# 2.1水力性能

对转泵喷推进器的非定常水力性能数值计算结果如图3所示，设计工况下泵喷扬程约为 $H =$ $1 5 . 2 8 \mathrm { m }$ ，泵效率 $\eta { = } 9 0 \%$ ，推力 $T = 1 . 4 8 \mathrm { k N }$ 。由图3可见，对转泵喷的 $H { - } Q$ 曲线相对较陡峭，效率曲线在设计工况附近偏平稳，这与对转轴流泵的性能研究结果[5]一致。

![](images/b9763d48d79635e331bbc9a47ba45ba5ca43c3324caa499d1a7e9f4e9b1e906a.jpg)  
图3对转泵喷水力性能曲线  
Fig. 3 Performance curve of contra-rotating waterjet pump

# 2.2空化性能

为得到研究对象的空化特性曲线，本文通过改变出口的压力值进行数值计算，得到一系列有效空化余量 $N P S H _ { a }$ 和总扬程 $H$ 的对应关系。出口压力值从 $1 5 0 \mathrm { { k P a } }$ 开始一直降到 $5 0 \mathrm { { k P a } }$ ，对应 $N P S H _ { a }$ 值从$1 4 . 1 \mathrm { m }$ 降至 $7 . 7 \mathrm { m }$ 。每次计算利用上一次的计算结果作为初始条件，以提高计算效率。绘制出的对转泵喷转子的空化特性曲线如图4所示。

![](images/d99b76664724418680bdbdfc9f99a4528b19e9c8f1093293bfcd501be44a6f0c.jpg)  
图4对转泵喷转子的空化特性曲线  
Fig. 4 Cavitation curve of contra-rotating waterjet pump

取扬程下降 $3 \%$ 时的 ${ \cal N P S H } _ { a }$ 作为对转泵的空化余量的临界值。由空化特性曲线得，临界空化余量 $N P S H _ { c r } { = } 8 . 4 4 \mathrm { m }$ 。传统的空化比转速计算式如式(1)所示。

$$
C = \frac { 5 . 6 2 n \sqrt { Q } } { N P S H _ { r } ^ { 0 . 7 5 } }
$$

式中， $n \mathrm { / m i n ^ { - 1 } }$ 为转子转速， $N P S H _ { r } \ / \mathrm { m }$ 为必需空化余量。

按式(1)来计算对转泵的空化比转速。取$n { = } 2 0 0 0 \mathrm { r p m }$ ，用 $N P S H _ { c r }$ 代替 $N P S H _ { r }$ ，计算得空化比转速 $c { = } 1 0 4 5$ 。

但是由于对转泵采用两个转子对旋，用传统的空化比转速定义式不能体现其具体的空化性能。日本九州大学流体控制研究室的Furukawa $\mathbf { A } ^ { [ 5 ] }$ 等人曾推导了相同设计条件下，对转式轴流泵和传统轴流泵所满足的关系式如式(2)所示。

$$
\frac { D _ { R R } n _ { R R } } { D _ { R S } n _ { R S } } = \frac { 1 } { \sqrt { 3 } }
$$

式中，下标 $R R$ 和 $R S$ 分别代表对转泵和单转子泵。

根据式(2)，将对转泵换算成等效的单转子泵，得到等效的空化比转速 $\scriptstyle { C = 1 8 1 0 }$ 。

为进一步对比空化性能，我们选取了一台设计条件相同的单转子泵作比较。在其设计工况下，流量 $Q { = } 0 . 2 1 2 \mathrm { m } ^ { 3 } / \mathrm { s }$ ，扬程 $H = 1 3 . 1 5 \mathrm { m }$ ，泵效率 $\eta = 8 9 \%$ 计算得其临界空化余量 $N P S H _ { c r } { = } 1 2 . 6 \mathrm { m }$ ，空化比转速$C { = } 1 1 6 0$ 。由此可见对转泵的空化性能得到了显著的提高。

# 2.3局部欧拉能量分布

取叶片展向的5个设计截面，研究局部欧拉能量沿着轴线方向的分布。局部欧拉能量分布表征研究流面从转子入口到转子出口的能量增长过程，其定义式如式(3)所示。

$$
L E H { \left( m , s \right) } = \frac { \displaystyle \int _ { 0 } ^ { 2 \pi } \frac { U V _ { \theta } } { g } \cdot V _ { m } \mathrm { d } \theta } { \displaystyle \int _ { 0 } ^ { 2 \pi } V _ { m } \mathrm { d } \theta }
$$

式中， $\mathbf { \nabla } m$ 代表子午方向坐标， $s$ 代表展向坐标，$U$ 为圆周速度， $V _ { \theta }$ 为绝对速度的圆周分量， $V _ { m }$ 为绝对速度的圆周分量。

对转泵喷和同设计条件的单转子泵的局部欧拉能量分布曲线如图5所示。

![](images/253228a8037824dd16fcc6a81d082c6d5becc9907bebd169029a4921ef316ea6.jpg)  
图5局部欧拉能量分布曲线  
Fig.5Local Euler head distribution   
图6叶片载荷分布

由图可知，对转泵喷的两个转子分别承担了一部分载荷，而单转子泵则只靠一个叶轮承载全部载荷。另外，前转子曲线的斜率较小，说明叶片加载缓慢，后转子斜率偏大，说明能量密度高，这与我们等速差异化设计的理念相一致。而对于单转子泵，它的斜率明显更加陡峭，说明叶片能量梯度大，更容易发生空化和二次流现象。

# 2.4叶片载荷分布

绘制对转泵喷和同设计条件的单转子泵的叶片载荷分布曲线如图6所示。由图可知，单转子泵上叶片的最低压力明显低于对转泵，而且载荷分布非常不均匀，是典型的前部加载。而对转泵的每个叶片上的最低压力约为单转泵的一半，并且叶片载荷基本均匀分布，为中后部加载。因此对转泵的载荷分布明显优于单转子泵，抗空化性能得到了提高。

500 Front rotor 500 Rearrotor 500 RS type 400 -SPAN0.01 400 SPAN0.01 400 SPANO.01 SPAN0.25 SPAN0.25 SPAN0.25 300 SPANO.50 300 SPAN0.50 300 SPAN0.50   
00 SPAN0.75 Prr/ssneessd 200 SPAN0.75 edr 200 SPAN0.75 100 100   
ssnsssse 0 \*P 0 rssssse -100 -100 -100 -200 -200 P -200 -300 xf/1=0.5\~0.6 -300 xf1l=0.5\~0.6 -300 b xf/l=0.4 -400 -400 -400 0.00.10.20.30.40.50.60.70.80.91.0 0.00.10.20.30.40.50.60.70.80.91.0 0.00.10.20.30.40.50.60.70.80.91.0 Streamwise (0-1) Streamwise (0-1) Streamwise (0-1) (a）前转子载荷分布 (b）后转子载荷分布 (c）单转子泵载荷分布 (a) Blade loading distribution of front rotor (b) Blade loading distribution of rear rotor (c) Blade loading distribution of RS type

# 3结论

本文提出了对转泵喷推进器的概念，并基于某水下航行体性能参数，通过相似换算设计了第一代实验模型对转泵喷及其实验系统。简述了对转泵喷转子和喷管的设计方法，借用数值计算手段，展开对转泵喷推进器的水力性能和空化特性的研究，并与相同设计条件的一台单转子泵进行了对比。总体而言结论如下：

1）在设计工况下，实验模型对转泵喷扬程约为 $H = 1 5 . 2 8 \mathrm { m }$ ，泵效率 $\eta = 9 0 \%$ ，推力 $T =$ $1 . 4 8 \mathrm { k N } .$ 对转泵喷的 $H { - } Q$ 曲线相对较陡峭，效率曲线在设计工况附近偏平稳。  
2）实验模型对转泵喷的临界空化余量约为$N P S H _ { c r } { = } 8 . 4 4 \mathrm { m }$ ，按照传统空化比转速的计算式计算其空化比转速为 $C { = } 1 0 4 5$ 。换算成等效的单转子泵，得到等效空化比转速$\scriptstyle C = 1 8 1 0$ ，大于同等设计条件的单转子泵。同时，结合局部欧拉能量分布和叶片载荷分布可知，对转泵喷的抗空化性能得到了显著的提高。

# 参考文献

[1] AmslerR C,Thurston S.Review of marine propellers and ducted propeller propulsive devices [J]. Journal of Aircraft, 2012,3(3):255-261.   
[2] 王金华，严卫生，刘旭琳．自主水下航行器测试与研发 技术新进展[J]．鱼雷技术,2010,18(3):202-208. WANG Jinhua, YAN Weisheng, LIU Xulin.Development of Testing and Verification Techniques for Autonomous Underwater Vehicles[J]. Torpedo Technology, 2010, 18(3):202-208.   
[3] 郭就．鱼雷设计与发展趋势[J]．国防科技,2011, 32(2):8-13. GUO Qing.The Design and Development of the Torpedoes[J]. National Defense Science and Technology, 2011,32(2):8-13.   
[4] Van Oossanen P.Theoretical Prediction of Cavitation on Propellers[J].Marine Technology Society Journal,1977, 14 (4):391-409.   
[5] FurukawaA, Shigemitsu T,Watanabe S.Performance test and flow measurement of contra-rotating axial flow pump[J]. Journal of Thermal Science,2007,16(1):7-13.   
[6] Momosaki S, Usami S, Okuma K,et al. Experimental Study on Rotational Speed Control of Contra-Rotating Axial Flow Pump[C]. Proceedings of 3rd Asian Joint Workshop on Thermophysics and Fluid Science,2010.   
[7]Momosaki S,Usami S,Watanabe S,etal.Numerical simulation of internal flow in a contra-rotating axial flow pump[J].IOP Conference Series: Earth and Environmental Science,2010,12:12046.   
[8] Cao L,Watanabe S,Momosaki S,et al.Low Speed Design of Rear Rotor in Contra-Rotating Axial Flow Pump[J], International Journal ofFluid Machinery and Systems,2013,6:105-112.   
[9] Morel T.Comprehensive Design ofAxisymmetric Wind Tunnel Contractions[J]. Journal ofFluids Engineering Transactions of the ASME,1975,97:225-233.   
[10]Morel T.Design of Two-Dimensional Wind Tunnel Contractions[J]. Journal of Fluids Engineering Transactions of the ASME,1977,99:371-377.   
[11]周刚，汪家道，陈皓生等．小型高速水洞收缩段的优化 设计[J]．船舶力学,2009,04:513-521. ZHOU Gang,WANG Jiadao, CHEN Haosheng, et al. Optimized design of the contraction in a minitype high-speed water-tunnel[J]. Journal of Ship Mechanics, 2009,04:513-521.