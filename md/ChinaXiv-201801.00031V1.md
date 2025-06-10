编号：2016-0252

# 磺化聚苯醚膜质子扩散的分子动力学模拟研究

韩旭辉，张鹏，马跃，李佳，王雨翔，周琼，周广刚，卢贵武（中国石油大学（北京）理学院，北京102249）

摘要：为了探究磺化聚苯醚(SPPO)用于质子交换膜燃料电池(PEMFCs)的性质，我们研究了 SPPO膜内部水和水合氢离子的分子扩散特性。构建含水量不同的SPPO膜的分子结构模型，采用分子动力学(MD)研究了平衡态模型的静态结构，发现元胞的密度随着含水量的增加而降低；同时通过分析径向分布函数(RDF)，发现在 SPPO 链上的磺酸根上的硫原子周围有水分子聚集，起到吸水和传导的作用，水合氢离子也更趋向于聚集在磺酸根附近。通过对分子运动轨迹的分析，计算了水和水合氢离子在 SPPO膜内的扩散系数 $D$ 和电导率 $\sigma$ ，研究结果表明，SPPO 膜的电导率随着膜内水含量的增加而增加，得到了与实验符合较好的结果。

关键词：质子交换膜；磺化聚苯醚；质子扩散；分子动力学模拟中图分类号：TK124 文件标识码：：A

# Molecular Dynamics Simulation Study of Proton Diffusion in Polymer

Electrolyte Membranes Based on Sulfonated Poly (phenylene oxide)

Han Xuhui, Zhang Peng, Ma Yue,Li Jia, Wang Yuxiang, Zhou Qiong, Zhou Guanggang, Lu Guiwu (China university of petroleum (Beijing), college of science; Beijing 102249)

AbstractTo explore the posibility of sulfonated poly（phenylene oxide）(SPPO) membrane for proton exchange membrane fuel cells(PEMFC)， molecular dynamics(MD) simulation technique was employed to investigate the molecular difusion characteristics of water and hydrogen ion in SPPO membrane of diferent water content. Through analysis the structure of the fully equilibrated amorphous polymericcell we find that the densitydecreased with the increase of water contents.According to the radial distribution function (RDF)ofcell,it was found that the water and hydrogen ion molecules tend to gathered in the sulfonate group of SPPO chains which made the sulfonate group take the conductive roles.Through the dynamic property analysis, we calculate the difusion coefficient of Water and hydrogen ion in the SPPO membrane,and the conductivity ofSPPO membrane.Withthe increase of water content,the diffusion coefficient of waterand hydrogen ion and the conductivityalso increases.Theresults coincide well with the experiments.

Key Words: Proton exchange membrane; sulfonated poly(phenylene oxide); Proton diffsion ; molecular dynamics simulation

# 0引言

燃料电池具有安全、高效、无污染、适用广、无噪声等特点，已成为当今世界能源领域的研究热点[1-2]。在几类重要的燃料电池分类中，聚合物燃料电池（PEMFCs）受到了广泛的关注[3]。

质子交换膜是一种由高分子材料制成的含有离子交换基团的一种阳离子交换薄膜，在PEMFCs 中起着质子传导、隔离燃料如氢气和甲醇与氧气和绝缘电子的作用，它是PEMFCs研究的重点和关键[4-5]。目前，只有全氟磺酸型质子交换膜(商品名为Nafion)

应用于燃料电池，但其高甲醇渗透率、耐热性差、高成本，是阻碍其应用于直接甲醇燃料电池（DMFCs）的主要原因[6-7]。磺化聚苯醚膜(SPPO)因具有较独特的性质而引起了广泛的关注[8]。以往对SPPO膜的研究主要集中在作为气体分离膜用于反渗透领域[9-10]，目前，也有不少将 SPPO 膜作为电解质材料用于燃料电池的研究报道[11-12]。

近几年，对于质子交换膜的分子动力学模拟研究已有大量的报道[13-15]。从理论上模拟及预测 SPPO膜性质，显得很有必要[16]。本文利用Materialsstudio(MS)软件平台构建了SPPO膜不同含水量的结构模型，模拟了水分子和水合氢离子在膜内的扩散行为，计算了对应的电导率。

# 1计算模型与模拟方法

为了研究水和水合氢离子在 SPPO 膜内的传导特性，构建了磺化度为 $50 \%$ ，聚合度为10的SPPO链，如图 1所示。其中图 1(a)和(b)分别为未磺化和磺化的SPPO单体结构模型，图1(c)为SPPO 链的构型。

![](images/a8901e3bb3b332a51c1d1fdbc224fbbdba4f90697c12dabfcce1f4dc266dcd47.jpg)  
图1未磺化(a)和磺化(b)的 SPPO 单体的模型和 SPPO 链(c)的分子模型  
Fig.1Chemical structures of non-sulfonated (a) and sulfonated (b) SPPO monomers used in the simulation. and SPPO chain (c) molecular model

利用Amorphouscell模块构建SPPO 膜的质子传导体系，图2为水和磺酸比 $\lambda { = } 5$ 、8、11、14（ $\lambda =$ 水分子个数/磺酸根个数）的 SPPO 膜的分子模型，具体元胞的参数如表1所示。

![](images/0e09ef404827203870988dbf60c9ad8fd6416a41f1efea37dce55d67a6a5d98e.jpg)  
图2 $\lambda { = } 5 ( \mathrm { a } )$ 、8(b)、11(c)、14(d)的元胞结构Fig 2The cell structure for $\lambda { = } 5$ (a)、8(b)、11(c)、14(d)

表1元胞参数Table 1 parameters of cell  

<html><body><table><tr><td>名称</td><td></td><td>水分子个数</td><td>水合氢离子个数</td></tr><tr><td>SPPO-5</td><td>5</td><td>200</td><td>50</td></tr><tr><td>SPPO-8</td><td>8</td><td>350</td><td>50</td></tr><tr><td>SPPO-11</td><td>11</td><td>500</td><td>50</td></tr><tr><td>SPPO-14</td><td>14</td><td>650</td><td>50</td></tr></table></body></html>

利用MS软件中的Forcite模块进行模型优化和分子动力学模拟，所有动力学模拟均选用COMPASS力场。COMPASS是以从头计算为依据的力场，采用从头计算和经验方法相结合的方式来计算力场中的参数。它是第一个把有机分子体系的力场与无机分子体系的力场统一的分子力场，能够模拟有机和无机小分子、高分子、一些金属离子、金属氧化物与金属[17]。

初始模型构建完成后，由于体系中的分子初始构象并不是能量最低的构象，因此需要利用退火过程对模型进行优化处理。采用最速下降法对元胞结构的能量和几何结构进行优化，通过退火模块模拟退火过程找到模型能量最低构象。最后，在正则系综下，设置体系温度为298K，动力学时间1.5ns，运行 SPPO膜质子传导的分子动力学模拟。本文采用的时间模拟步长均为1fs。

通过以上步骤得到不同含水量的模型的动力学运动轨迹，对其最终的模型结构和运动轨迹进行分析，得到元胞密度、体积和均方位移。

# 2结果与讨论

# 2.1元胞密度分析

对于非晶态元胞的动力学模拟来说，最重要的是要保证模拟元胞要处于完全平衡状态，以确保水分子和水合氢离子能够充分地扩散到处于平衡态SPPO膜中。为此引入温度、总能量和密度等参数，来观察体系是否已经处于平衡态。图3为体系的温度 $T$ 和总能量 $E$ 随时间 $\mathbf { \chi } _ { t }$ 变化的波动曲线，图中曲线波动很小即体系温度和总能量基本保持不变，表2为模拟的元胞的体积和密度，图3和表2反映出体系已经处于平衡状态。

![](images/df28ddd6a2ebc02b6ee29a4e9b12df045f82801662b8638fa186cbee4270329f.jpg)  
图3模拟体系温度和总能量随时间变化曲线 Fig.3Temperature and total energy of the dynamic simulation system

表2模拟元胞的密度和体积  
Table 2 density and volume of cell   

<html><body><table><tr><td>膜名称</td><td>密度/g/cm</td><td>体积/nm</td></tr><tr><td>SPPO -5</td><td>1.24</td><td>27.50</td></tr><tr><td>SPPO -8</td><td>1.21</td><td>32.00</td></tr><tr><td>SPPO-11</td><td>1.17</td><td>36.90</td></tr><tr><td>SPPO-14</td><td>1.14</td><td>40.76</td></tr></table></body></html>

# 2.2静态结构分析

图4(a)、(b)、(c)为 $\lambda { = } 5$ 的 SPPO-5 膜的径向分布函数（Radialdistributionfunction，RDF）。将磺酸根上的硫原子标记为S，水分子上的氧原子标记为$\mathrm { \Delta O _ { w } }$ ，水合氢离子上的氧原子标记为 $\mathrm { O } _ { \mathrm { h } }$ ，甲基上的碳原子标记为 $C _ { \mathrm { m } }$ ，苯环上的碳原子标记为 $\mathrm { C _ { b } }$ 。比较图4(a)中的两了个曲线我们发现 $\mathrm { S - O _ { h } }$ 曲线和 $\mathrm { \Delta S { - } O _ { w } }$ 曲线有明显的峰值， $\mathrm { \bf S } { - } \mathrm { \bf O } _ { \mathrm { h } }$ 曲线比 $\mathrm { \Delta S { - } O _ { w } }$ 曲线的峰值高。这是因为水合氢离子所带的正电与带负电磺酸根基团相互吸引导致水合氢离子更多的在磺酸根附近存在。将图4(a)中的曲线与图4(b)比较我们发现，在SPPO链上水合氢离子更趋向于在磺酸根周围，而不是甲烷和苯环等疏水基团。图4(c)中我们看到S-S、$\mathrm { O } _ { \mathrm { h } } \mathrm { - O } _ { \mathrm { h } }$ 的截断半径在 $0 . 4 \mathrm { n m }$ 以后，而图4(a)中 $\mathrm { \Delta S { - } O _ { h } }$ ，$\mathrm { \Delta S - O _ { w } }$ 的截断半径在 $0 . 4 \mathrm { n m }$ ，这也能说明磺酸根和水合氢离子相互吸引，相对于自身水合氢离子更趋向于聚集在磺酸根附近。对比 $\lambda { = } 8$ 、11、14的SPPO膜的RDF曲线也能发现相似的规律。

![](images/121de1ecee7248e31e891ae74249f181918f6eeb612d5e48f5c1575585d0140a.jpg)  
图4 (a) SPPO-5膜中 $\mathrm { S - O _ { h } }$ ， $\mathrm { \Delta S { - } O _ { w } }$ 径向分布函数;(b)SPPO-5膜中 $\mathrm { C _ { 6 } { - } O _ { \mathrm { h } } , C _ { \mathrm { m } } { - } O _ { \mathrm { h } } }$ 径向分布函数;(c) SPPO-5 膜中 S-S、 $\mathrm { O } _ { \mathrm { h } } \mathrm { - O } _ { \mathrm { h } }$ 径向分布函数  
Fig.4(a)RDFof $\mathbf { S } \mathbf { - } \mathbf { O } _ { \mathrm { h } }$ 、 ${ \bf { S } } { - } \mathrm { { O } } _ { \mathrm { { w } } }$ in SPPO membrane;(b)RDF of $\mathrm { { C _ { b } } \mathrm { { - } } \mathrm { { O _ { h } } } }$ 、 $\mathrm { \Delta C _ { m } { - } O _ { h } }$ in SPPO membrane ;(c) RDF of S-S、 $\mathrm { { O } _ { h } \mathrm { { - } \mathrm { { O } _ { h } } } }$ in SPPO membrane

# 2.3水和水合氢离子在膜中的扩散系数计算

初始模拟体系经过1.5ns的动力学模拟后，取动力学过程 $1 0 0 \mathrm { p s } { \cdot } 1 2 0 0 \mathrm { p s }$ 时间段，利用分析工具得到如图5所示的均方位移图。由于模型中水与水合氢原子的体积均很小，所以采用记录水和水合氢原子中氧原子的位置数据来计算扩散系数。将水中的氧（号 $( \mathrm { O } _ { \mathrm { w } }$ ）和水合氢离子中的氧（ $\mathrm { \cdot } \mathrm { O } _ { \mathrm { h } }$ ）分别标识。

![](images/1a4598769d2f74d883a75a60e3e34914d24c509481b57f2853bb27b95d8bf3c2.jpg)  
图5(a)不同含水量水分子的MSD；(b)不同含水量水合氢离子的MSD  
Fig.5(a) MSD of water at different water content;(b) MSD of hydronium ions at different water content

扩散系数 $D$

$$
D = \frac { a } { 6 }
$$

式（1）中： $\mathbf { \Delta } _ { a }$ 为对数据进行拟合得到均方位移(MSD)与时间的一次函数的曲线的斜率，将 $a$ 代入式(1)中得到扩散系数 $D$ 。

$$
\ { \sigma = \frac { D n e ^ { 2 } } { k T } }
$$

式（2）中： $k$ 为玻尔兹曼常数， $n$ 为元胞中水合氢离子的粒子个数， $T$ 为绝对温度， $e$ 为元电荷电量。将$D$ 代入式(2)，可计算得到体系的电导率。

表3为最终得到的水分子和水合氢离子的扩散系数及电导率，从表3中可以看出随着含水量的增加，水和水合氢离子的扩散系数随之增加。反映了水含量越多，膜就越湿润，质子的传导率就越大的客观事实。将水合氢离子的扩散系数代入到式(2)，计算得到相应的电导率如表3所示。由表3容易看出，随着扩散系数的增大，SPPO膜的电导率就越大，变化范围从 $0 . 0 0 5 6 \mathrm { - } 0 . 0 3 8 2 \mathrm { S / c m } .$ 龚春丽等[1]对 SPPO膜进行的电导率测试，测试磺化度 $40 . 1 \%$ 的SPPO膜时，其电导率为 $0 . 0 1 1 6 \ \mathrm { S / c m }$ ，与我们的模拟结果基本符合。

表3水分子、水合氢离子的扩散系数和电导率Table 3 Diffusion coefficient of water andhydronium ions and conductivity  

<html><body><table><tr><td>膜名称</td><td></td><td>Dw</td><td>Dh</td><td>σ/ S/cm</td></tr><tr><td>SPPO -5</td><td>5</td><td>0.0133</td><td>0.0050</td><td>0.0056</td></tr><tr><td>SPPO -8</td><td>8</td><td>0.0433</td><td>0.0150</td><td>0.0127</td></tr><tr><td>SPPO-11</td><td>11</td><td>0.0783</td><td>0.0250</td><td>0.0185</td></tr><tr><td>SPPO-14</td><td>14</td><td>0.1067</td><td>0.0500</td><td>0.0382</td></tr></table></body></html>

# 3结论

对SPPO膜的元胞进行了分子动力学模拟，研究结果表明，SPPO膜的密度随水含量的增加而下降，磺酸根承担质子传导的作用，水合氢离子相对更容易聚集到磺酸根附近。研究发现水分子和水合氢离子的扩散系数随着水含量的增大而变大，其电导率也是随着水含量的增加而增加，其规律与实验基本相符。

# 参考文献

[1] Song C.Fuel Processing for Low-temperature and HightemperatureFuel Cells: Challengesand Opportunities for Sustainable Development in the 21st Century[J].Catalysis Today,2002,77:17-49 [2] Vielstich W,Lamm A, Gasteiger H A.Handbook of Fuel Cells，Fundamental，Technology and Applications[J].Focus on Catalysts,2003,2003(8):7 [3] Ghasem B,Manouchehr N, Mohammad J H, et al. Molecular DynamicsSimulation Study of Proton Diffusion in Polymer Electrolyte Membranes Based on Sulfonated Poly (ether ether ketone)[J]. International Journal of Hydrogen Energy, 2012, 37(13):10256-10264 [4] Kreuer K D, Paddison S J, Spohr E, Schuster M. Transportin Proton Conductors for Fuel-cell

Applications: Simulations, Elementary Reactions, and Phenomenology[J].Chemical Reviews，2004, 104(10):4637-4678   
[5] Hickner M A, Ghassemi H, Seung K Y, et al. Alternative Polymer Systems for Proton Exchange Membranes (PEMs)[J]. 2004, 104(10):4587-4812   
[6] Rikukawa M, Sanui K. Proton-conducting Polymer ElectrolyteMembranesBasedonHydrocarbon Polymers[J]. Progress in Polymer Science，2000, 25(10):1463-1502   
[7] Kreuer K D. On the Development of Proton Conducting Polymer Membranes for Hydrogen and Methanol Fuel Cels[J]. Journal of Membrane Science, 2001, 185(1):29-39   
[8]汪传清，黄玉惠，丛广民．磺化聚苯醚的制备与表 征[J]．高分子学报,1995,04:488-493   
Wang Chuanqing,Huang Yuhui, Cong Guangmin. PreparationandCharacterizationofSulfonated PolyphenylEther[J].ActaPolymericaSinica, 1995,04:488-493   
[9] Geeta C，Ranka V, Takeshi M,et al Effects of Polymer Molecular Weight and Chemical Modification on the Gas TransportProperties of Poly(2,6-dimethyl-1,4-phenyleneoxide)[J].2000, 77(5):1137-1143   
[10] Fu Hongyong, Jia Lianda, Xu Jiping. Studies on the Sulfonation of Poly(phenylene oxide ）(PPO） and Permeation Behavior of Gases and Water Vapor Through Sulfonated PPO Membranes.II Permeation Behavior of Gasesand Water Vapor Through Sulfonated PPO Membranes [J]. Journal of Applied Polymer Science,1994, 51(8):1405-1409   
[11]庞金辉.侧链型磺化聚芳醚质子交换膜材料的制 备及其性能研究[D].吉林大学,2008   
Pang Jinhui， Synthesis and Properties of Sulfonated Poly(arylene ether)s with Sulfonic Acid Groups on Pendant [D].JiLin University,2008   
[12] 郭梅梅.磺化聚芳醚质子交换膜材料的设计及性 能研究[D].吉林大学,2010   
Guo Meimei，Design and Properties of Sulfonated Poly(arylene ether)s Proton Exchange Membranes[D].JiLin University, 2010   
[13]龚春丽,文胜,周毅等.磺化聚苯醚质子交换膜的 制备与性能研究[J].工程塑料应用,2007,35(7):43-46 Gong Chunli,Wen Sheng,Zhou Yi et al. Proton exchange membrane preparation and propertiesof sulfonated polyphenyleneoxide research[J]. Engineering Plastics Application, 2007,35(7):43-46 [14] Mauritz K A,Moore R B. State of understanding of nafion[J]. Chemical Reviews,2004;104:4535-4586 [15]Alberti G, Casciola M Solid state protonic conductors, present main applications and future prospects. Solid State Ion,2001,145:3-16   
[16]陈清.分子模拟方法在高分子质子交换膜和表面 活性剂中的若干应用研究[D].上海交通大学,2011 Chen Qing. Molecular Simulations on Proton Exchange Membrane and Surfactant Syatems[D]. Shanghai Jiao Tong University, 2011   
[17]梁太宁,杨小震.分子力场-COMPASS 简介[J].化 学通报（网络版）,2001,(1).   
Liang Taining， Yang Xiaozhen. Introductionto COMPASS Forcefield[J].Chemistry Online,2001,(1).

附页：作者：韩旭辉；地址：北京市昌平区府学路18 号中国石油大学（北京）理学院B座111室；手机：15010939211；邮箱：836385794@qq.com