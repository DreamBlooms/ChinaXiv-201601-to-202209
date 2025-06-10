# 基于脉冲激光定位的SRAM单粒子门锁事件率预估

余永涛1²，韩建伟\*‘，封国强」，蔡明辉(1．中国科学院 空间科学与应用研究中心，北京100190；2．中国科学院大学，北京100049)

摘要：器件单粒子门锁效应(SEL)预估方法一般是建立在只有一个敏感体积单元的长方体(RPP)模型上静态随机存储器(SRAM)单粒子门锁敏感区的定位试验结果表明敏感体积单元不仅有一个.利用脉冲激光定位SRAMK6R4016V1D单粒子门锁效应敏感区的试验结果对器件在轨SEL事件率进行了修正计算.首先利用脉冲激光定位SRAMSEL敏感区，获得敏感区的分布情况并确定整个器件敏感体积单元的数量.然后针对不同的空间轨道、辐射粒子以及敏感体积厚度和敏感体积单元数进行了相应的器件SEL事件率计算，并对计算结果进行了分析讨论.结果表明,重离子引起的 SEL事件率随敏感体积单元数量的增大而减小；修正敏感体积单元数量对预估质子引起的SEL事件率非常必要，否则将会过高评估质子直接电离作用对SEL事件率的贡献，

关键词:SEL事件率；敏感区定位；敏感体积单元；质子直接电离；静态随机存储器；脉冲激光

中图分类号：V520.6；TN4  
文献标识码：A 文章编号:1001-5965(2015)04-0609-07

当空间辐射环境中的高能带电粒子入射到航天器电子设备中的CMOS器件时，易诱发单粒子门锁效应（SEL,SingleEventLatchup）,导致器件失效甚至航天器仪器故障.单粒子门锁效应一直以来都是国内外单粒子效应研究的热点随着半导体工艺尺寸的减小，亚微米器件应用于航天设备后表现出对单粒子门锁效应的极端敏感性[13].根据器件地面辐射模拟试验数据和航天器轨道的辐射环境模型预估器件在轨单粒子效应对正确选用宇航半导体器件、提高航天器寿命和可靠性具有重大的现实意义对评价半导体器件的抗单粒子效应能力也具有重要的指导作用和

参考价值.

多数单粒子效应预估程序都是建立在RPP（RectangularParallelepiped）敏感体积模型基础上模拟入射粒子在敏感体积内的能量沉积.对于器件单粒子门锁在轨预估，单粒子门锁效应没有类似于存储类器件单粒子翻转效应存储位单元的概念因而在预估计算时多是假设整个器件只存在一个敏感体积单元（SV,SensitiveVolume).近年来，一系列脉冲激光定位静态随机存储器（SRAM)单粒子门锁效应敏感区的试验结果[4-7]表明SRAM器件的SEL敏感区是由许多具有周期性的较小尺寸的SEL敏感区构成的，即SRAM

SEL敏感体积单元的数量不是只有一个，这将会对SRAM器件空间SEL事件率预估产生影响.如文献[4]和文献[7]的论述在只有一个敏感体积单元的假设下，在进行SEL事件率预估时，根据试验测得的截面数据建立的RPP模型的横向尺寸很大离子倾斜入射时电荷收集路径很长线性能量传输(LETLinearEnergy Transfer)值低而射程长的离子倾斜入射到器件敏感区时也可沉积足够的电荷而诱发SEL.在各向同性辐射环境中粒子倾斜入射的可能性很大，入射倾角大于等于 $6 0 ^ { \circ }$ 的粒子比例为 $5 0 \%$ .实际情形是SRAMSEL敏感体积的横向尺寸是有限的，离子倾斜入射时电荷收集路径也是有限的.与真实情况相比假设整个器件只存在一个敏感体积单元的传统预估方法最终会得到一个相对保守的事件率预估结果.对于修正敏感体积单元数量以改进SEL事件率预估，以往的工作多是进行定性讨论，没有系统地论述如何修正以及敏感体积单元数量的修正对SEL事件率预估有多大程度的影响

本文工作主要分为3部分，一是利用脉冲激光定位SRAMK6R4016V1DSEL敏感区，获得不同尺度下敏感区的分布情况，进而确定器件敏感体积单元的数量；二是针对地球同步轨道和极轨道2种典型空间轨道辐射环境，利用OMERE软件计算不同条件下器件在轨SEL事件率；最后对比讨论不同情况下敏感体积单元数对SEL事件率预估结果的影响，

# 激光定位试验

1.1脉冲激光定位SEL敏感区试验系统及方法

脉冲激光单粒子效应(SEE)敏感区定位成像系统示意图如图1所示.主要有4部分构成：脉冲激光辐照装置、单粒子效应检测系统、电动移动台、同步控制装置.利用聚焦后的脉冲激光对被测器件进行逐点辐照同时利用单粒子效应检测系统实时检测被测器件的单粒子效应，利用移动台实现被测器件不同区域的扫描测试，同步控制装置将脉冲激光辐照、单粒子效应检测、电动移动台移动同步控制起来，并将每个辐照位置的激光脉冲注量、单粒子效应数据、物理坐标对应起来传输到计算机最终将单粒子效应敏感位置显示为二维图像.

![](images/c5655df13dd3305d0585d0c20036f07fa975aeca21bfb1df92f0f1d7523e57bc.jpg)  
图1脉冲激光SEE敏感区定位成像系统示意图 Fig.1Schematic of pulsed laser facility for SEE sensitivity mapping

SEL敏感区定位测试流程图如图2所示.首先是初始化被测器件和设定试验测试条件，包括使被测器件正常工作、使激光聚焦定位在测试原点及调节脉冲激光能量等.然后开始脉冲激光辐照同时利用单粒子效应检测系统实时监测被测器件的供电电流，一旦电流值超过设定的限值对被测器件断电.脉冲激光能量和SEL的电流值以及辐照位置对应的物理坐标会被记录下来，这个坐标就是发生SEL的物理位置.断电延时一段时间后检测系统恢复被测器件供电接着移动台移动一定的距离到下一个测试位置重复以上过程，直到完成对所选区域的扫描测试，最终可以获得器件测试区域内的SEL敏感位置分布图.

![](images/30bfd382f78b31f201aad416ace97df985aaf23b88cce7b975247c31f22d6e77.jpg)  
图2SEL敏感区定位测试流程图 Fig.2State diagram of SEL sensitivity mapping

# 1.2脉冲激光定位SEL敏感区试验及结果

试验样品为SAMSUNGSRAMK6R4016V1D，容量为 $2 5 6 \mathrm { K } \times 1 6$ bit,工作电压为 $\left( 3 . 3 \pm 0 . 3 \right) \mathrm { V }$ -芯片大小为 $0 . 4 6 \times 0 . 5 2 \mathrm { c m } ^ { 2 }$ .这款器件在重离子试验中表现出对SEL非常敏感[8].为避开器件正面金属层对激光的阻挡作用，激光辐照试验采用背部辐照方法.根据不同的测试尺度移动台的步距分别设定为 $1 0 ~ 5 ~ , 1 ~ \mu \mathrm { m }$ .测试过程中，激光光斑直径约为 $1 . 7 \mu \mathrm { m } ^ { \left[ 9 \right] }$ 每个测试位置辐照1个激光脉冲，各点的脉冲激光能量相同.

不同尺度及扫描步距下SEL敏感区位图如图3所示.图中浅色带状区域是SEL敏感位置，深色背景是器件的显微图片.如图3(a)所示，首先对整个器件的上半部分进行测试，占器件总面积的1/2，激光辐照扫描的步距是 $1 0 ~ \mu \mathrm { m }$ ,可以看出SEL敏感区位于SRAM器件存储阵列部分，而周围的电路部分对SEL不敏感.为了更好地表现SEL敏感区分布情形对其中局部区域进行放大，如图3(b)所示敏感区表现出明显的带状分布图形.增加激光辐照扫描定位精度移动步距减小为$5 \mu \mathrm { m }$ .如图3（c)所示，对其中大小为 $2 0 0 ~ \mu \mathrm { m } \times$ $2 0 0 \mu \mathrm { m }$ 的区域进行测试,结果显示SEL敏感区仍具有周期性的重复结构，在该测试区域内约有$4 \times 9$ 个周期结构.最后进一步减小激光辐照扫描的步距为 $1 \mu \mathrm { m }$ 使用能量稍高于SEL阈值能量的脉冲激光对上述周期结构中的一个进行SEL敏感区测试.如图3(d)所示在 $2 0 \mu \mathrm { m } \times 3 0 \mu \mathrm { m }$ 的区域内SEL敏感区表现出周期性图形由5个单一SEL敏感区组成，

![](images/27e6a7f351f299e7b2de078c2864a89d0aa862b3c04e443fc0beae925cd3a643.jpg)  
图3不同尺度及扫描步距下SEL敏感区位图  
Fig.3SEL sensitivity mappings at different scales with different scanning steps

从图3(a)中可以看出整个器件的存储阵列部分对SEL的敏感性没有显著差异，而且器件SEL的电流均在 $2 5 0 \sim 3 0 0 ~ \mathrm { m A }$ 范围内，因而认为器件所包含的众多SEL敏感区对辐照的敏感性是一致的.根据以上的试验结果和测试器件的相关信息，可计算整个器件包含单一SEL敏感区的数量.在器件的上半部分存储阵列区域在竖直方向上的尺寸为 $2 2 0 0 ~ \mu \mathrm { m }$ ,而敏感区在横向上共有64条周期结构，而在竖直方向上 $2 0 0 ~ \mu \mathrm { m }$ 范围内共有9 个周期结构 ，而其中一个周期结构包含5 个单一SEL敏感区.则在不同的扫描步距的情况下整个器件包含SEL敏感体积的数量 $N$ 估算如下：

$$
1 0 \mu \mathrm { m } ; N = 2 \times 6 4 = 1 2 8
$$

$$
5 \ \mu \mathrm { m } ; N = 2 \times 6 4 \times 2 2 0 0 \times 9 / 2 0 0 = 1 2 6 7 2
$$

$$
1 ~ { \mu \mathrm { m } } ; N = 2 \times 6 4 \times 2 2 0 0 \times 9 \times 5 / 2 0 0 = 6 3 ~ 3 6 0
$$

# 2 SEL事件率修正计算

通过以上试验获得了不同定位尺度下SRAMK6R4016V1D单粒子门锁效应敏感区的二维周期分布图.SEL敏感区的周期性分布对器件SEL在轨事件率预估具有重要的影响.在预估器件SEL事件率时，一般利用试验测得的门锁阈值和截面数据根据RPP模型进行计算.经典的预估方法是假设整个器件只有一个敏感体积单元，收集沉积在敏感体积内的电荷，沉积电荷量与离子穿过敏感体积的路径相关.根据试验测得的截面数据建立的经典RPP模型的横向尺寸很大，离子倾斜入射时电荷收集路径很长因而低LET值而长射程的离子倾斜入射到器件敏感区时也可沉积足够的电荷而诱发SEL.而激光定位的试验结果表明，SRAMSEL敏感区具有周期重复性，在相邻的敏感区之间存在不敏感的区域.离子入射到任意单一SEL敏感区都可使整个器件发生SEL，而单一SEL敏感区的横向尺寸远小于经典模型的横向尺寸.这样传统的SEL事件率预估方法将会高估SEL截面最终给出比真实情况更保守的结果，这可能会对正确评估和选用宇航器件产生重大影响.

根据以上试验结果及分析，类似于存储器件“存储单元"的概念认为SRAM器件SEL敏感区由 $N$ 个敏感体积单元组成.为了表现SEL事件率随敏感体积单元数量的变化趋势在以下部分将通过计算对比在不同的敏感体积单元数情况下器件在轨SEL事件率.器件在轨SEL事件率计算的基础是器件地面模拟试验截面数据、器件所在轨道的空间环境辐射模型和高能粒子与器件相互作用模型.K6R4016V1DSRAM重离子测试结果及韦伯拟合参数如表1所示[8].

# 表1K6R4016V1DSRAM重离子测试结果及韦伯拟合参数[8

Table1 K6R4016V1D SRAM heavy ion test result and Weibull parameters [8]   

<html><body><table><tr><td rowspan="2">参数</td><td rowspan="2">LET阈值/ （MeV·cm² · mg-1)</td><td rowspan="2">饱和 截面/cm²</td><td rowspan="2">尺度参数W/</td><td rowspan="2">形状 参数S</td></tr><tr><td>mg-1) (MeV·cm² ·</td></tr><tr><td>数值</td><td>1.0</td><td>0.06</td><td>9</td><td>3.5</td></tr></table></body></html>

所有计算都是采用OMERE ${ \mathrm { V } } 3 . 6 ^ { [ 1 0 ] }$ 软件.为了研究不同轨道辐射环境下敏感体积单元数对SEL事件率的影响，选取地球同步轨道(GEO)0 $3 5 ~ 8 7 0 ~ \mathrm { k m } ~ , 0 ^ { \circ } )$ 和极轨低地球轨道（LEO)0 $\textrm { 8 0 0 k m } 9 8 ^ { \circ } ) 2$ 种典型空间轨道，重离子辐射环境模型为银河宇宙线，质子辐射环境模型为俘获带质子模型 $\mathrm { A P 8 } \mathrm { m i n }$ 采用 $3 . 0 \ \mathrm { m m }$ Al等效屏蔽，不考虑太阳活动异常.器件在轨SEE预估过程中，一般根据器件工艺确定RPP模型的敏感体积厚度,对于CMOS/epi工艺一般取 $2 ~ \mu \mathrm { m } ^ { [ 1 1 ] }$ ，但对于单粒子门锁效应这可能不再适用，因而在计算敏感体积厚度时还取 $3 ~ { \mu \mathrm { m } } ^ { \left[ 5 \right] }$ .对应不同的敏感体积单元数量SEL敏感体积横向尺寸如表2所示.

表2SEL敏感体积横向尺寸  
Table 2Lateral dimensions of SEL sensitive volume   

<html><body><table><tr><td rowspan="2">参数</td><td colspan="4">SV数量</td></tr><tr><td>1</td><td>128</td><td>12 672</td><td>63360</td></tr><tr><td>横向尺寸/</td><td>2450 ×</td><td>271.6 ×</td><td>21.8×</td><td rowspan="2">9.7×9.7</td></tr><tr><td>μm²</td><td>2450</td><td>217.6</td><td>21.8</td></tr></table></body></html>

# 2.1 重离子SEL事件率

对应不同的敏感体积单元数和敏感体积厚度利用OMERE计算的地球GEO轨道重离子SEL事件率如图4所示.

![](images/963fe2a8dcec60f107dbc8a8fc2d40c85b44f00e58453346a9c2405e281db6fb.jpg)  
图4地球GEO 轨道重离子SEL事件率 Fig.4Heavy ion SEL predicted rates of GEO

从图4中可以看出随着敏感体积单元数量的增大SEL事件率逐渐减小,SEL事件率对敏感体积厚度变得敏感.在敏感体积厚度为 $2 \mu \mathrm { m }$ 而敏感体积单元数量由1增加到63360时SEL事件率由0.45（day·device）-减小到o.28（day $\cdot$ device) -1 .另外，当敏感体积单元数较小时SEL事件率与敏感体积厚度基本无关；当敏感单元数增大到12672和63360时敏感体积厚度增大,SEL事件率明显减小.

图5为极轨道重离子SEL事件率.可以看出极轨道辐射环境下的计算结果与同步轨道的计算结果表现出同样的趋势.在敏感体积厚度为$2 ~ \mu \mathrm { m }$ 而敏感体积单元数量增加到63360时，SEL事件率由0.14（day $\cdot \cdot$ device）-减小到0. 08 (day $\cdot$ device) -1 .

![](images/ec8385971a0d1bfa2c2fb062b1e5ddda8f443d3b5aee1a156e6210c057ab1f9e.jpg)  
图5极轨道重离子SEL事件率 Fig.5Heavy ion SEL predicted rates of polar LEO

# 2.2质子 SEL事件率

对于空间辐射环境中质子诱发的SEL，主要针对LEO极轨道考虑俘获带质子诱发的SEL，质子环境模型采用 $\operatorname { A P 8 } \operatorname* { m i n }$ ，使用SIMPA等效模型计算质子SEL截面.SIMPA是一个基于重离子数据计算质子SEE的半经验模型，计算质子SEE截面的公式为[12]

$$
\sigma _ { \mathrm { { p } } } ( E _ { \mathrm { { p } } } ) = \int _ { E _ { \mathrm { { s } } } } \sigma _ { \Pi } ( E ) \phi ( E , E _ { \mathrm { { p } } } ) \mathrm { d } E
$$

式中 $\rho _ { \mathrm { p } } ( E _ { \mathrm { p } } )$ 为质子能量为 $E _ { \mathrm { { p } } }$ 时的 SEE 截面;$\sigma _ { \Pi } ( E )$ 为重离子 SEE 的截面; $E _ { \mathrm { s } }$ 为重离子试验的单粒子效应阈值能量; $\phi ( \textit { E } , \boldsymbol { E } _ { \mathrm { p } } )$ 是入射能量为 $E _ { \mathrm { p } }$ 的质子在敏感体积内沉积能量为 $E$ 的概率.公式中各项参数是根据质子与Si核反应的MonteCarlo模拟以及质子沉积能量测量结果确定的极轨道质子SEL事件率(OMERESIMPA)如图6所示

从图6中可以看出，对应同样的敏感体积厚度敏感体积单元数对SEL事件率计算没有影响.敏感体积厚度增加SEL事件率略有减小

利用SRIM计算了 $2 \mathrm { M e V }$ 和 $1 0 \mathrm { M e V }$ 质子LET值随粒子在Si中穿透深度的变化.在Bragg峰附近质子的 LET值可达到 $0 . 5 ~ \mathrm { M e V } \cdot \mathrm { c m } ^ { 2 } \cdot \mathrm { m g } ^ { - 1 }$ ，，$1 0 \mathrm { M e V }$ 质子在Si中射程可达 $7 1 0 \mu \mathrm { m }$ .质子直接电离作用对SEE的贡献通常是忽略不计的，但对于SEE 阈值较低的器件则需要考虑[13-4].这款器件SEL阈值低、截面大，俘获带质子的能量范围为$0 . 1 \sim 4 0 0 \mathrm { M e V }$ 高能质子倾斜入射时有效LET值可以远高于测试器件的LET阈值，质子的直接电离作用也可能会对SEL产生贡献

![](images/1c8e3e85f1dea4274ed74df13490fbeb5c02581cbb9849c6efd9b2d31b627a29.jpg)  
图6极轨道质子SEL事件率(OMERESIMPA) Fig.6Proton SEL predicted rates of polar LEO(OMERE SIMPA)

图7是利用OMERE得到的极轨道俘获带质子LET谱.利用质子的LET谱和重离子截面测试数据进行了SEL事件率计算，最终结果如图8所示.

![](images/5ea3f2460531414109bdba526e3c574d91816527730d0db27f059fb400a71c68.jpg)  
图7极轨道俘获带质子LET谱

![](images/5f910e061cfdff8b9d4380bba3f5b66940b664b32f52ea6a111e5ea0275ddbb9.jpg)  
Fig.7Trapped proton LET spectrum of polar LEO   
图8极轨道质子直接电离SEL事件率 Fig.8Proton SEL predicted rates of polar LEO by direct ionization

从图8中可以看出，计算结果与重离子SEL事件率计算结果相似，但敏感体积单元数对SEL事件率有很大影响.在敏感体积厚度为 $2 ~ { \mu \mathrm { m } }$ 时，敏感体积数由1增加到63360,SEL事件率减小了3个数量级.在敏感体积厚度为 $3 ~ { \mu \mathrm { m } }$ 时敏感体积数由1增加到63360,SEL事件率减小了4个数量级.

# 3 敏感体积单元数量对SEL事件率的影响

# 3.1 重离子SEL事件率

2.1节针对地球同步轨道和极轨道利用OMERE计算分析了敏感体积单元数对重离子SEL事件率的影响2种轨道的计算结果所表现出的趋势是一致的，

对应同样的敏感体积厚度，随着敏感体积单元数增加SEL事件率逐渐减小.当敏感体积单元数从1增加到128时SEL事件率变化不大.当敏感体积单元数增大到12672和63360时，SEL事件率明显减小.敏感体积厚度为 $3 ~ { \mu \mathrm { m } }$ 时对应地球同步轨道和极轨道SEL事件率分别减小了$4 8 . 7 \%$ 和 $5 5 . 1 \%$ .对于其他情形敏感体积单元数修正引起的改变更小.器件在轨SEL预估涉及众多因素相对于地面模拟试验数据、飞行试验数据、空间辐射环境模型和粒子与器件相互作用模型等因素带来的误差[15]敏感体积单元数的影响不大.

另外当敏感体积单元数比较小时SEL事件率与敏感体积厚度基本无关.特别是按照传统的SEL预估方法敏感体积单元数量为1对应2种敏感体积厚度的情况，SEL事件率计算结果基本相等.当敏感体积单元数增大到12672和63360时敏感体积厚度增大,SEL事件率明显减小.敏感体积厚度的增大相当于增大了临界电荷量因而随着敏感体积厚度的增大SEL事件率减小.当敏感体积单元数为1，根据试验的截面数据建立的敏感体积单元的横向尺寸远大于纵向尺寸.空间辐射环境中的多数重离子具有低LET值而长射程的特点.这些倾斜入射的重离子在敏感体积内沉积的电荷量要高于临界电荷量，临界电荷量的小幅度增加对SEL事件率基本没有影响因而敏感体积厚度改变对传统SEL事件率预估几乎没有影响，

# 3.2质子 SEL事件率

2.2节针对极轨道分别利用OMERESIMPA模型和俘获带质子的LET谱计算分析了俘获带质子引起的SEL事件率.利用OMERESIMPA计算在相同的敏感体积厚度下敏感体积单元数对SEL事件率计算没有影响.根据SIMPA模型的计算方法质子引起单粒子效应是通过核反应产生二次离子导致，不需要考虑入射质子空间方向上的差异，而敏感体积单元数量的修正影响的就是倾斜入射的粒子因而质子SEL事件率与敏感单元数无关.另外即使能够获得完整的质子单粒子效应面地面辐照试验数据，根据Bendel双参数公式拟合截面进而预估质子单粒子效应敏感体积单元数对结果也没有影响，

考虑到这款器件SEL阈值低、截面大，利用俘获带质子LET谱和重离子测试数据进行了SEL事件率计算.敏感体积单元数对SEL事件率有很大影响.在敏感体积厚度为 $2 ~ { \mu \mathrm { m } }$ 时敏感体积数由1增加到63360SEL事件率减小了3个量级.这与俘获带质子有密切关系，根据计算的质子LET谱和对应能谱，能够通过直接电离作用引起SEL 的是具有低LET值、高能量、长射程的质子.对这款器件的计算表明能量至少大于 $1 0 \mathrm { M e V }$ 的质子倾斜入射才可能通过直接电离诱发被测器件发生SEL.经过敏感体积单元数修正后敏感体积单元的横向尺寸大幅减小，这些质子沉积的电荷不足以引起SEL.

对比图5、图6与图8，在敏感体积厚度为$2 ~ \mu \mathrm { m }$ 的情况下敏感体积数为1时质子直接电离引起的SEL事件率比质子核反应引起的SEL事件率及宇宙线重离子引起的SEL事件率高一个量级在敏感体积数为63360时，质子直接电离引起的SEL事件率可以忽略.这说明敏感体积单元数的修正对SEL事件率计算的影响很大，否则将会严重高估质子直接电离作用对SEL事件率的贡献[13].另外对于质子直接电离引起的 SEL事件率敏感体积单元数修正后SEL事件率对敏感体积厚度非常敏感 敏感体积厚度从 $2 \mu \mathrm { m }$ 增加到$3 \mu \mathrm { m }$ SEL事件率减小了1个量级.总之无论是重离子SEL事件率预估还是质子的SEL事件率估，敏感体积单元数修正后SEL事件率对敏感体积厚度变得相对敏感，

最后需要说明的是，以上计算分析了在不同的轨道、粒子、敏感体积厚度等条件下敏感体积单元数对SRAMK6R4016V1DSEL事件率预估的影响.SEL事件率预估结果还与器件本身的抗辐射参数有关.质子单粒子效应预估有许多种不同的计算方法[16]本文采用的是基于重离子测试数据计算质子SEL事件率的SIMPA模型对于其他方法计算结果的影响有待于进一步研究.另外激光定位SEL敏感区的试验结果表明单一SEL敏感区的长宽比很高，而本文主要关注的问题是敏感体积单元数量，在计算中设定敏感体积的长宽相等这也是后续需要改进的部分.

# 4结论

利用脉冲激光定位SRAMK6R4016V1D单粒子门锁效应敏感区的试验结果对器件在轨SEL事件率进行了改进计算.结论如下：

1）脉冲激光具有快速准确定位SEL敏感区的优势，可以在一定精度下确定器件的SEL敏感单元数量.测试器件的SEL敏感区具有周期重复性是由63360个单一SEL敏感体积单元组成.

2）对于重离子引起的SEL事件率当敏感体积单元数较小时，SEL事件率基本不随敏感体积单元数而变化；当敏感体积单元数增大到63360时SEL事件率的减小较明显SEL事件率减小的最大幅度约为 $5 0 \%$ ：

3）敏感体积单元数对质子核反应引起的SEL事件率没有影响这与采用的计算模型有关；但敏感体积单元数量的修正对计算质子直接电离引起的SEL事件率非常必要，否则将会过高评估质子直接电离作用对总的SEL事件率的贡献

# 参考文献(References)

[1]Page Jr TE,Benedetto JM.Extreme latchup susceptibility in modern commercial-off-the-shelf( COTS)monolithic $1 \mathrm { M }$ and $4 \mathrm { M }$ CMOS static random-access memory( SRAM) devices [C] //Radiation Effects Data Workshop.Seattle:IEEE 2O05:1-7.   
[2]韩建伟张振龙封国强等.单粒子锁定极端敏感器件的试 验及对我国航天安全的警示[J].航天器环境工程，2008， 25(3) :265-267. HanJW,Zhang ZL,FengGQ,et al.The radiation test of SRAM devices for extreme single event latch-up susceptibility and awarning to our aerospace safety[J].Spacecraft Environment Engineering 2008 25(3):265-267(in Chinese).   
[3]余永涛封国强陈睿,等.SRAMK6R4016V1D单粒子门锁 及防护试验研究[J].原子能科学技术,2012,46(增刊)： 587-591. YuYT,FengGQ,ChenR,etal.Experimental study on single event latchup of SRAM K6R4016V1D and its protection technology[J].Atomic Energy Science and Technology 2012 46( Suppl.):587-591(in Chinese).   
[4]Burnell AJChugg A M,Harboe-Srensen R.Laser SEL sensitivity mapping of SRAM cells [J].IEEE Transactions on Nuclear Science 2010 57(4):1973-1977.   
[5]Faraud E Pouget V Shao K et al. Investigation on the SEL sensitive depth of an SRAM using linear and two-photon absorption laser testing[J].IEEE Transactions on Nuclear Science 2011， 58(6) :2637-2643.   
[6]Dodds NA Hooten N C,Reed R A,et al.SEL-sensitive areamapping and the effects of reflection and difraction from metal lines on laser SEE testing[J].IEEE Transactions on Nuclear Science 2013 60(4):2550-2558.   
[7］余永涛封国强陈睿,等.CMOS SRAM器件单粒子锁定敏 感区的脉冲激光定位试验研究[J].航天器环境工程2014， 31(2) :150-153. YuYT Feng GQ ChenR et al.Research of SEL sensitive region of CMOS SRAM by pulsed laser mapping facility[J]. Spacecraft Environment Engineering $, 2 0 1 4 \ , 3 1 ( 2 ) : 1 5 0 \mathrm { - } 1 5 3 ($ in Chinese) .   
[8]Ferlet-CavroisV,Muschitiello M,Alessio D M.Single event latch-up( SEL) analysis of the $2 5 6 \mathrm { ~ k ~ } \times \ : 1 6$ SRAM samsung K6R4016V1D-TC10 ,RA0660 [R].Noordwijk:ESA/ESTECTEC-QEC 2013.   
[9]Yu Y T Feng G Q ChenR et al.Laser SEU sensitivity mapping of deep submicron CMOS SRAM[J].Journal of Semiconductors , 2014 35(6):064011--064011-4.   
[10]OMERE softwareversion 3.6[CP/OL].http://www.trad.fr/ OMERE-Software.html.   
[11]Petersen EL Pickel JC AdamsJH,etal.Rate prediction for single event effects-a critique[J].IEEE Transactions on Nuclear Science 1992 39(6) :1577-1599.   
[12]Douct B ,Patin Y Buisson J et al.Characterization of proton interactions in electronic components [J].IEEE Transactions on Nuclear Science 1994 41(3):593-600.   
[13]Bezerra F,EcoffetR Lorfevre E etal.CARMEN2/MEX:an inflight laboratory for the observation of radiation effectson electronic devices[C]//12th European Conference on Radiation and its Effects on Components and Systems(RADECS). Piscataway NJ:IEEE 2011:607-614.   
[14]Artola L ,Velazco R Hubert G et al.In flight SEU/MCU sensitivity of commercial nanometric SRAMs:operational estimations [J].IEEE Transactions on Nuclear Science ,2O11 ,58(6): 2644-2651.   
[15]Bezerra FLorfevre E,Ecoffet R,et al.In flight observation of proton induced destructive single event phenomena[C]//European Conference on Radiation and its Effects on Components and Systems（RADECS).Piscataway,NJ:IEEE,2OO9:126- 132.   
[16]Petersen E L.Approaches to proton single-event rate calculations[J].IEEE Transactions on Nuclear Science,1996, 43(2) :496-504.

# SEL rate prediction for SRAM using pulsed laser sensitivity mapping

YU Yongtao¹²,HAN Jianwei\*’,FENG Guoqiang' ,CAI Minghuil (1.National Space Science Center,Chinese Academy of Sciences,Beijing 1Oo19O,China; 2.University of Chinese Academy of Sciences,Beijing 1OoO49,China)

Abstract: The classical approaches for single event latchup (SEL） rate prediction are based on the rectangular parallelepiped（RPP)model of only one sensitive volume.However,the experiment results of SEL sensitivity mapping of static random access memory（SRAM) show that the device has not only one sensitive volume（SV).The in-flight SEL rate of the device was corrected using the experiment results of pulsed laser SEL sensitivity mapping of SRAM K6R4016V1D.The SEL sensitivity maps of the SRAM by pulsed laser were first obtained and then the SV number of the device was calculated.The SEL rates of the device were predictedand discussed for different space orbits,radiation particles,SVthicknesses and SVnumber in particular. The results show that SEL rate caused by heavy ion decreases with SV number. The corrction of the SV number is essential for SEL rate due to proton direct ionization；otherwise,the contributionof direct ionization of protons to SEL rate would be greatly overestimated.

Key Words: SEL rate; sensitivity mapping; sensitive volume; direct ionization of proton; SRAM;pulsed laser