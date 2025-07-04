# Wurster流化床内颗粒流动特性实验研究

车汉桥1,2吴 蒙1,2 叶佳敏1王海刚1,2(1．中国科学院工程热物理研究所，北京100190;2．中国科学院大学，北京 100049)

摘要为研究Wurster 流化床内颗粒流动规律，本文利用12-4-8 组合电极电容层析成像(Electrical CapacitanceTomography，ECT）传感器对 Wurster 流化床冷态实验和加湿实验过程进行监测，得到了ECT 重构图像以及颗粒浓度时变曲线。首先，根据冷态实验数据比较了不同操作条件下流化床内颗粒流态和浓度波动特性；在此基础上，通过加湿实验数据分析了包衣液流率对于颗粒流动的影响。本文研究表明，ECT传感器适用于Wurster 流化床过程关键参数在线测量和故障诊断，从而为反应过程的优化提供支持，

关键词Wurster 流化床；电容层析成像；颗粒浓度中图分类号：TM934.2 文献标识码：A 文章编号:0253-231X(2017)03-0548-05

# Experimental Study of the Gas-solid Flow in a Wurster Fluidized Bed

CHE Han-Qiao $^ { 1 , 2 }$ （204号 WU Meng1,2 YE Jia-Min1 WANG Hai-Gang $^ { 1 , 2 }$ （20 (1.Institute of Engineering Thermophysics,Chinese Academy of Sciences，Beijing 100190,China; 2.University of Chinese Academy of Sciences，Beijing 10oo49,China)

Abstract To investigate the flow behavior in a Wurster fluidized bed and optimize the coating process, one set of 12-4-8 combined electrical capacitance tomography (ECT) sensor was used to monitor the cold flow and wetting process in a Wurster fuidized bed,ECT images and solid concentration curves were obtained based on the measurement results. Firstly, the solid flow regime and concentration fluctuation with diffrent operation parameters were compared based on the cold test. Secondly, the effect of solution flow rate on the gas-solid flow was analyzed based on the wetting test.Finally, an optimized strategy for the process control of coating process was discussed based on experiment results. Key wordsWurster fluidized bed; electrical capacitance tomography; solid concentration

# 0引言

Wurster流化床是一种底喷形式的流化床，常用于药物微丸的包衣和干燥过程[1]。Wurster 流化床主要特点是中间区域存在导流管，运行过程中颗粒在气动力的作用下围绕导流管产生稳定的床内循环，而这种循环使得Wurster流化床的包衣效果优于其他类型的装置[2]。

包衣成品质量与流化床操作条件密切相关，如流化风速、包衣温度、喷液速率等。如果生产过程操作条件没有得到合理调控，可影响产品质量，甚至引发颗粒循环停滞或者黏连结块[3]。由于Wurster 流化床结构复杂，运行过程往往处于“黑匣子”状态，目前尚缺乏有效的监测手段。ECT作为一种非侵入式测量方法，能在不干扰颗粒流动的条件下对流化床内物质分布进行重构，非常适合多相流的测量。此外，ECT还具有成像快速、成本低的优点。然而，目前将ECT应用于Wurster流化床监测的相关研究还比较少，而且仅针对单一区域的测量[4]。因此，本研究将基于ECT传感器实现Wurster流化床导流管内外区域的同步测量，通过冷态实验和加湿实验研究流化床内颗粒流动特性，为Wurster流化床生产过程优化提供参考。

# 1 实验原理

# 1.1 实验装置及原理

实验装置结构如图1所示。流化床主体用有机玻璃制成，分为上下两部分。上部为直径 $2 6 0 \mathrm { m m }$ 圆柱形体，下部连接倾角为 $9 ^ { \circ }$ 的圆锥形体。流化床内导流管由不锈钢制成，直径为 $6 5 ~ \mathrm { m m }$ ，长 $\mathrm { 1 5 0 ~ m m }$ 0布风板位于导流管下方，两者间隙可调节。布风板中央区域开孔率面积比为 $3 5 \%$ ，其他区域 $4 \%$ 。供风装置主要包括罗茨风机和空气加热器，可以调节风速、风温。喷雾装置包括蠕动泵、空气压缩机、双流体喷嘴(Schlick 970).

![](images/ff76e3945cfc02fbd47344558b3bbb69b3b58fcd21a18f07eb9bb80df6eba8f8.jpg)  
图1实验系统图Fig.1 Experimental set up

由于Wurster流化床内部存在导流管，颗粒流动区域是被分隔成两部分，即包衣区域和环形区域。针对这种结构，实验采用图2所示的12-4-8组合ECT传感器，以实现导流管内外两区域的同时测量。其中，流化床外壁面 12 电极与导流管外壁 4电极组合来测量环形区域的颗粒浓度；导流管内壁8电极用来测量包衣区域的颗粒浓度；两区域的测量同步进行。

![](images/8ed952c9ddd43d4c8ea9b35070c9db973d9cd5d81fcabfb9534f6d8dd2759af1.jpg)  
图212-4-8组合电极ECT传感器 Fig.2 12-4-8 combined electrodes ECT sensor

ECT成像采用Landweber迭代算法，其计算形式如下：

$$
G ^ { n + l } { = } G ^ { n } \cdot \left( 1 { + } \lambda \right) { + } { \alpha } \cdot S ^ { T } \cdot \left( C _ { N } { - } S \cdot G ^ { n } \right) \left( 1 { + } \lambda \right)
$$

其中， $\scriptstyle { C _ { N } }$ 为测量得到的归一化电容向量，在每个测量循环中，ECT传感器在环形区域和环形区域分别测得120 和 28个电容值； $s$ 为敏感场矩阵， $\pmb { G }$ 为图像灰度向量， $\alpha$ 和 $\lambda$ 分别为迭代步长、松弛因子。

实验中颗粒浓度基于图像灰度矩阵 $G$ 计算：

$$
\beta = \vartheta \cdot \frac { \displaystyle \sum _ { i = 1 } ^ { K } G _ { i } \left( x , y \right) a _ { i } \left( x , y \right) } { \displaystyle \sum _ { i = 1 } ^ { K } a _ { i } \left( x , y \right) }
$$

式中， $\vartheta$ 为固定床颗粒孔隙率，对于本实验用颗粒为0.62； $\mathbf { \Omega } _ { a }$ 为像素点的面积， $K$ 为指定区域内像素数。

# 1.2实验工况

实验选择平均粒径为 $5 1 0 \mu \mathrm { m }$ 糖丸作为床料。为了便于分析比较，分别进行了冷态实验和加湿实验。冷态实验只改变基本操作条件：床料质量 $( M )$ 、导流管-布风板间隙 $( H )$ 、流化风速 $( V )$ ，不喷洒包衣液，相应实验工况如表1所示。

# 表1冷态实验工况

Table 1 Process parameters for cold test   

<html><body><table><tr><td>工况编号</td><td>M/kg</td><td>H/mm</td><td>V/m·s-1</td></tr><tr><td>1</td><td>2</td><td>10</td><td rowspan="4">0.48~3.86</td></tr><tr><td>2</td><td>3</td><td>10</td></tr><tr><td>3</td><td>2</td><td>20</td></tr><tr><td>4</td><td>3</td><td>20</td></tr></table></body></html>

颗粒加湿实验基本设置如表2所示，实验过程利用蒸馏水作为喷洒介质。因此，经过干燥后颗粒性质可恢复到加湿前状态，在单次实验中包含了多组加湿并干燥过程。

表2加湿实验工况  
Table 2 Process parameters for wetting test   

<html><body><table><tr><td>M/kg</td><td>H/mm</td><td>T/C</td><td>V/m·s-1</td></tr><tr><td>2.1</td><td>20</td><td>>40</td><td>0~3.6</td></tr></table></body></html>

# 2结果和讨论

# 2.1动态成像结果

图3为不同操作条件下被测区域断面颗粒浓度ECT重构图像。可以看出，环形区域颗粒流动均呈密相流，而包衣区域为稀相流。造成这种现象的原因是，在布风板的调节下，包衣区域的空气流速远远大于环形区域。

![](images/064b4f23485bfe2ab8158397c173747741a75fdcac4fe7ad90b32b710494812b.jpg)  
图3不同操作条件下断面典型颗粒分布Fig.3 Typical solid distributions in cross section

对于导流管-布风板间隙为 $1 0 ~ \mathrm { m m }$ 的工况，在流化风速小于 $2 . 1 9 ~ \mathrm { m / s }$ 时，环形区域颗粒处于最小流化状态。风速上升为 $2 . 7 4 ~ \mathrm { m / s }$ 后，流态转变为泡状流。而提高间隙为 $2 0 ~ \mathrm { m m }$ 后，在风速为 $2 . 1 9 \ \mathrm { m / s }$ 时就已呈现泡状流。可见，提高间隙有利于环形区域的气泡产生。

图4为实验过程拟三维ECT成像结果，横坐标表示断面尺寸，纵坐标表示时间轴。拟三维ECT成像利用300帧(时间长度约为6s）二维断面图像依次叠加而成。拟三维图像能更直观显示颗粒分布随时间动态变化过程。图中显示，随着流化风速的增加，导流管外部气泡密度明显增加，且大多位于贴近导流管外壁的位置；同时，包衣区域颗粒浓度明显下降且波动增强。结合图3、图4可以看出，在间隙为 $1 0 ~ \mathrm { m m }$ 时，包衣区域中央位置颗粒浓度普遍高于近壁区域，而间隙为 $2 0 ~ \mathrm { m m }$ 时，包衣区域颗粒浓度分布趋势与之相反，这也说明了间隙大小对于包衣区域颗粒流动有明显影响。

![](images/e043976a67285219fdfe1b4b8b52398c1877a44c7325e05edd28f9b6691365b2.jpg)  
图4ECT拟三维成像 Fig.4 Qusi-3D ECT images

# 2.2不同操作条件对颗粒浓度的影响

图5所示为不同导流管－布风板间隙下颗粒浓度随风速变化曲线。颗粒浓度为依照式(2）得到的断面平均值。可以看出， $1 0 ~ \mathrm { m m }$ 间隙（工况2）下包衣区域颗粒浓度略低于 $2 0 ~ \mathrm { m m }$ 工况 (工况 4)，这说明提高间隙尺寸可以促进床内颗粒循环。

图6对比了间隙为 $2 0 \mathrm { m m }$ 时(工况3、4)，不同初始床料质量下的颗粒浓度。可以看出，包衣区域颗粒浓度受初始床料质量影响不大。图中还显示，环形区域颗粒浓度随初始质量增加而升高，这是由于床料初始质量增加后，料位提高，处在环形区域内ECT敏感区域颗粒浓度增高。

# 2.4颗粒浓度的波动

图7为两种流化风速下的颗粒浓度随时间变化曲线。在风速为 $1 . 5 8 ~ \mathrm { m / s }$ 下，颗粒浓度波动幅度较小；而随着风速增加至 $2 . 7 4 ~ \mathrm { m / s }$ ，包衣区域和环形区域的颗粒浓度波动幅度明显增大，这反映流动稳定性降低。可见，操作条件会影响到颗粒浓度的波动状态。对于流化床包衣过程，包衣液是以恒定流率喷洒的，在包衣区域的颗粒浓度剧烈波动不利于包衣的均匀性。

![](images/3b46739562bfd8aad19107daee2b587f875e75006df7b9980503dc6c7640e839.jpg)  
图5不同导流管－布风板间隙下颗粒浓度Fig.5Solid concentration with different gap heights

![](images/bc17b6642f68ea28999e54cd2a449463bdbf292deb2497766bfac1dee6ac322d.jpg)  
图6不同初始床料质量下颗粒浓度Fig.6 Solid concentration with different mass load

为综合比较不同工况下包衣区域颗粒的波动状态，进一步计算了该区域内颗粒浓度时变数据的标准差。图8列出了各冷态实验工况颗粒浓度波动标准差 $( \sigma )$ 随流化风速变化曲线。由图8可知，间隙为 $1 0 ~ \mathrm { m m }$ 时（工况1、2）颗粒波动标准值明显小于间隙为 $2 0 ~ \mathrm { m m }$ 的工况(工况3、4)，并且在风速较低时 $\mathrm { { ( < 3 ~ m / s ) } }$ ，这种趋势更加明显。这表明减小导流管－布风板间隙可以提高包衣区域的颗粒流动稳定性。

# 2.5流化床加湿实验

颗粒湿度是一项重要参数，在包衣过程中要维持颗粒湿度的相对稳定，防止因为颗粒湿度过大引起的失流和颗粒凝聚现象。鉴于此，在冷态实验的基础上进行了加湿实验，实验基本设置见表2。加湿实验持续 $7 5 ~ \mathrm { m i n }$ ，图9为实验过程颗粒浓度随时间变化曲线。其中，在图中A、B、C、D所示4个时间区间内进行加湿，A、C、D区间喷液流率为 $2 5 ~ \mathrm { m L / m i n }$ B区间为 $2 0 ~ \mathrm { { m L / m i n } }$ ；在A、B、C处流化风速为2.7$\mathrm { m } / \mathrm { s }$ ，D处增加到 $3 . 6 ~ \mathrm { m / s }$ 。可以看出，环形区域和包衣区域的颗粒浓度都随着风速和喷液速率的调整而显著变化。

![](images/3790cd6e5f25cd6ac99795a700516503e4f774887aae851bf5504296bced7dcf.jpg)  
图7颗粒浓度随时间变化曲线 (工况 2)Fig.7 Average solid concentration versus time(case 2

![](images/1ec14c396512b3c2b1d02ea57f846f2927315ff51286d6e358a5b46012893b30.jpg)  
图8包衣区域颗粒浓度波动标准差 Fig.8 Standard deviation of solid concentration in coating zone

图9显示，A、C两区间出现了包衣区域颗粒浓度迅速下降而环形区域颗粒浓度迅速上升的趋势，这显示流化床内颗粒已经出现失流，需要及时停喷干燥。与之相比，B、D两区间内颗粒浓度变化比较平稳，且环形区域内保持泡状流，表明颗粒正常流动。对比时间段A、B可以看出，在流化风速为2.7$\mathrm { m } / \mathrm { s }$ 下，可以允许的加湿速率为 $2 0 ~ \mathrm { { m L / m i n } }$ ；对比时间段C、D可以看出，当流化风速增加至 $3 . 6 ~ \mathrm { m / s }$ 后，可以允许的加湿速率增加到 $2 5 ~ \mathrm { m L / m i n }$ ，这是因为随着流化风速的增加，流化风对颗粒的干燥能力提高。由以上分析可知，在Wurster流化床基本操作条件确定后，存在最大允许的喷液速率，而通过增加流化风速可以提高最大允许喷液流率。

![](images/4c2103bf91acdffb790817fe7e0931df247fb374def5e7a6338cf12c27d0ce2b.jpg)  
图9加湿实验过程颗粒浓度变化曲线 Fig.9 Variation in solid concentration in wetting test

mm的工况，由于环形区域不容易产生气泡，并且包衣区域颗粒流动稳定性好，这有利于包衣的均匀性,适用于包衣液流率较小且对包衣层质量要求严格的精细包衣，如缓释、肠溶包衣[5]。

对于间隙为 $2 0 ~ \mathrm { m m }$ 的工况，其包衣区域颗粒流动稳定性较差，但是在环形区域的流化风速小，容易产生气泡，这有利于防止失流现象和局部的颗粒凝结，允许较大的包衣液流率。所以，这种配置适用于对于包衣均匀度要求低的快速包衣过程，如掩味包衣[5]。

# 4结论

本文利用ECT传感器对Wurster流化床冷态实验和加湿实验过程颗粒流动进行了监测，主要结论如下：

1）不同的操作条件直接决定颗粒的流态、浓度和波动性质。其中，导流管-布风板间隙的影响最为明显。较大的间隙有利于环形区域气泡生成，并可提高包衣区域颗粒浓度，但同时颗粒流动稳定性会下降；2）包衣液流率过高可在短时间内引起失流，提高包衣液流率需要同时加大流化风速;3)较小的导流管-布风板间隙有利于颗粒的均匀包衣，而较大的间隙有利于快速包衣，可根据生产需要进行调整。

# 3流化床包衣操作条件的选择

对于Wurster流化床操作参数的选择应考虑两种因素：首先是避免颗粒失流现象，因为失流往往导致严重的颗粒凝聚、结块；其次是保证同一批次下颗粒均匀包衣。在这两种因素的基础上再考虑能耗、生产效率等因素。

从图3中可以看出，在冷态实验中即使较小的风速也能保证环形区域处于最小流化状态。而当包衣液喷洒时会增加颗粒间的黏滞力，使失流的发生可能性增加。所以，控制失流主要应选择合适包衣液流率。

通常认为，颗粒包衣均匀度取决于两个变量，即流化床内颗粒的循环时间分布和单次循环包衣量分布[5]，所以包衣区域颗粒浓度大幅波动都不利于均匀包衣。另有研究发现，环形区域内的气泡也对包衣效果不利[6]。

基于以上分析，对于导流管-布风板间隙为10

# 参考文献

[1]Da Silva,Butzge J,Nitz M,et al.Monitoring and Control of Coating and Granulation Processes in Fluidized BedsA Review [J].Advanced Powder Technology, 2014, 25(1): 195-210   
[2]Hampel N,Peglow M,et al. Continuous Pellet Coating in a Wurster Fluidized Bed Process [J].Chemical Engineering Science,2013,86:87-98   
[3] Wang H, Sennior P,Mann R,et al.Online Measurement and Control of Solids Moisture in Fluidised Bed Dryers [J]. Chemical Engineering Science,2009,64(12):2893-2902   
[4] Ge R,YeJ,WangH,et al.Measurement of Particle Concentration in a Wurster Fluidized Bed by Electrical Capacitance Tomography Sensors [J].AIChE Journal, 2014, 60(12): 4051-4064   
[5] Turton R.Challenges in the Modeling and Prediction of Coating of Pharmaceutical Dosage Forms [J].Powder Technology,2008,181(2): 186-194   
[6]Wang L.K,Heng P,Liew C.V.Classification of Annular Bed Flow Patterns and Investigation on Their Influence on the Bottom SprayFluid Bed Coating Process [J].Pharmaceutical research,2010,27(5):756-766