http://bhxb.buaa.edu.cn jbuaa@buaa.edu.cn DOI: 10.13700/j.bh.1001-5965.2014.0799

# 基于数据网格化方法的低轨辐射带建模技术

常峥1²，王咏梅\*」，田天³，张贤国(1．中国科学院 国家空间科学中心，北京100190；2．中国科学院大学 地球科学学院，北京100049;3.61741 部队，北京 100094)

摘要：地球辐射带中的高能带电粒子是引起航天器材料和器件性能退化甚至失效的主要空间环境因素.因此航天器设计中所采用的辐射带模型的准确程度对于航天器的生存能力和航天任务的完成质量至关重要.在利用我国自主辐射带高能粒子探测数据进行的辐射带建模中探测数据的空间网格化是一项非常重要的工作.介绍了我国辐射带探测数据的情况，以及辐射带建模的方法和步骤;重点研究了不同插值方法在低地球轨道(LEO)空间辐射带建模数据网格化中的应用，并开展了误差分析.研究结果表明:在各种常用的插值方法中反距离加权法、自然邻点法和最近邻点法适合工程化应用.其中，反距离加权法生成的数据网格对粒子通量的反演结果精度最高，该方法采用低阶距离时得到的反演结果更为合理，

关键词：空间环境；辐射带；数据网格；插值；反距离加权法；自然邻点法；最近邻点法

中图分类号：V221+.3；TB553  
文献标识码：A 文章编号:1001-5965(2015)12-2288-08

地球外层空间存在着一个区域其中充满地磁场捕获的高能质子和电子，这个区域被称为地球辐射带(以下简称为辐射带)[1].辐射带中的质子和电子能量较高[2],能够引起航天器材料和器件性能退化甚至失效[34].在地球空间运行的绝大多数航天器都要或多或少地穿越辐射带，遭遇高能粒子辐射.因此在航天任务的设计过程中，准确地定量估算航天器所处的空间辐射环境对于航天器设计的优化、运行安全的保障和任务的完成都至关重要.

目前国际和国内航天界普遍采用NASA编制的质子模型AP8和电子模型AE8来计算辐射带质子和电子的通量，并以此为基础评估辐射带对航天器的影响[35-6].目前我国可获得的AP8/AE8模型的最新版本分别完成于1976年和1983年，这两个版本使用的都是20世纪70年代以前的数据[7-8],观测资料比较陈旧,模型计算值与实际观测值经常存在较大偏差[469-2],使得这两个版本的模型应用到当前航天任务中存在时效局限性.NASA在后期对AP8/AE8模型进行了多次修订和补充形成了多种修正版本，并且于2006年联合美国多家单位开始开发用于替代AP8/AE8的辐射带质子和电子的新模型:AP9/AE9[6],但由于技术封锁我国目前还无法获得AP8/AE8的修正版本和AP9/AE9.因此，我国自主研发辐射带模型对于我国航天工程的可持续发展具有现实和战略的意义.地面高度为 $3 0 0 \sim 1 0 0 0 \mathrm { k m }$ 的轨道空间即低地球轨道(Low-EarthOrbitLEO)空间是大量应用卫星运行的区域[13].因此,这一区域是辐射带建模中最重要的区域之一.

# 1我国辐射带监测数据情况

我国从20世纪80年代开始对空间环境展开了大规模探测其中LEO空间辐射带高能粒子分布是探测的重点[14].截至到目前为止,已发射卫星中搭载有高能粒子探测器的卫星共有50余颗，其中LEO卫星超过30 颗.部分高能粒子探测仪器的卫星轨道、观测对象、能量范围、通道数和观测时段如表1所示.这些仪器的设计原理相同都

为半导体型探测器

不同仪器获得的探测数据在联合使用前，必须经过交叉定标[15].因此在建模过程中,研究人员对表1所列数据进行了同化处理，并以此为基础建立了LEO、中地球轨道(Medium-Earth Orbit，MEO)和同步轨道(Geosynchronous Orbit ,GEO）辐射环境数据库数据库包含了超过一个完整太阳活动周(11a)的LEO空间辐射带数据，可以用于LEO空间辐射带建模

表1高能粒子探测仪器参数  
Table1 High energy charged particle detector parameters   

<html><body><table><tr><td>卫星名称</td><td>轨道</td><td>观测对象</td><td>能量范围/MeV</td><td>通道数</td><td>观测时段</td></tr><tr><td>神舟四号、神舟五号</td><td>近圆轨道高度340km倾角42°</td><td>质子能谱 电子能谱</td><td>2.9~300 0.2~5.0</td><td>10 9</td><td>2002-2—2004-05</td></tr><tr><td>天宫一号</td><td>近圆轨道高度380km倾角43°</td><td>质子能谱 电子能谱</td><td>>1.5 >0.2</td><td>8 8</td><td>2011-0至今</td></tr><tr><td>风云三号A星、B星、C星</td><td>近圆轨道高度830km倾角98°</td><td>质子能谱 电子能谱</td><td>3~300 0.15~5.7</td><td>6 5</td><td>2008-05至今</td></tr><tr><td>风云一号C星、D星</td><td>近圆轨道高度860km倾角98°</td><td>质子能谱 电子通量</td><td>2.9~300 >1.6</td><td>5 1</td><td>1995-05—2010-06</td></tr><tr><td>实践五号</td><td>近圆轨道高度860km倾角98°</td><td>质子能谱 电子能谱</td><td>2.9~300 0.15~5.7</td><td>5 5</td><td>1999-05—2000-02</td></tr><tr><td>实践四号</td><td>大椭圆轨道近地点200 km， 远地点36000km 倾角28.5°</td><td>质子能谱 电子能谱</td><td>4~300 0.5~4</td><td>5</td><td>1994-02—1994-08</td></tr><tr><td>风云二号A星、B星</td><td>静止轨道</td><td>质子能谱 质子通量 电子通量</td><td>2.9~300 >1.1 >1.4</td><td>3 1</td><td>1997-06—1998-04 2000-06—2001-02</td></tr><tr><td>风云二号C星、D星、E星</td><td>静止轨道</td><td>质子能谱 电子通量</td><td>10~300 >0.35</td><td>1 3 2</td><td>2004-10至今</td></tr><tr><td>风云二号F星</td><td>静止轨道</td><td>质子能谱</td><td>>2 >4</td><td>6</td><td>2012-01至今</td></tr><tr><td></td><td></td><td>电子能谱</td><td>>0.2</td><td>11</td><td></td></tr></table></body></html>

# 2辐射带建模的方法

本文利用我国辐射带高能粒子的探测数据建立的自主辐射带模型和NASA的AP8/AE8均为经验模型即模型的基础是具有特定组织结构的数据，文中将这种具有特定组织结构的数据定义为表单.在辐射带模型中表单指的是能描述辐射环境某一给定时刻、给定空间环境状态下在所有空间维度上分布特征的粒子通量数据列表.AP8/AE8仅含有一组代表太阳活动高年和低年时对应高能粒子通量平均分布的表单，不能给出辐射带随地磁场长期变化而引起的缓变，也不能反映太阳活动周内的各种周期性变化和各种突发性扰动变化[16],因此称其为静态模型;代替它的AP9/AE9只能通过输出结果中的概率间接地反映各种变化对辐射带的影响[17]，说明AP9/AE9也不是真正意义上的动态模型

本文试图建立的自主辐射带模型的建模主要步骤如图1所示.从图1中可以看出模型输出结果是通过对模型数据中的4组表单进行查询、计算并将结果进行叠加后得到的，因此这4组表单是模型的核心内容.这4组表单分别给出辐射带的宁静状态、长期缓变状态、周期变化状态和扰动变化状态因此自主辐射带模型属于动态模型这也是该模型相比于AP8/AE8的最大改进之处.表单的建立流程如图2所示.同化后的数据在空间中离散分布必须先经过空间网格化处理，使数据

模型数据静态数据表单 静态平均结果输人参数 长期缓变数据表单 长期缓变结果 结果 输出结果叠周期性变化数据表单 周期性变化结果 加突发性变化数据表单 突发性变化结果

在空间中均匀分布后再进行分类处理生成各类数据库.因此空间网格化是建模中的重要步骤

建立表单空间、粒子入射方向、 静态数据观测数据 同 空间网格化 能谐、粒种 长表单变化 数据表单太阳活动周变化 周期性变化季节变化、27天周期变化数据表单地方时变化扰动事件分类、分级 突发性变化数据表单

3种轨道空间中LEO空间卫星最多，且LEO空间包含了多个不同高度的轨道，而MEO(特指高度为 $2 2 0 0 0 { \mathrm { k m } } .$ 倾角为 $5 5 ^ { \circ }$ 的卫星轨道)空间和GEO空间均仅包含单一轨道的若干颗卫星.因此LEO空间的数据网格化成为建模中的重点.

# 3LEO空间数据网格化

# 3.1 空间数据网格

鉴于LEO空间观测数据的分布特点，为了得到如图3所示的空间数据网格，本文采取了以下处理方法进行数据网格化：

1）利用11个轨道高度上的卫星观测资料，完成对应11个空间球面上的数据网格化.对于同系列卫星观测数据的使用原则是，利用其中部分卫星的观测资料完成插值，剩余卫星的观测资料用于对插值结果进行验证.

2）11个空间球面以外的空间，利用11个空间球面的数据网格，结合大椭圆轨道卫星的观测资料通过插值获得；11个空间球面之间的区域采用内插高度范围为 $3 0 0 \sim 3 4 0 \mathrm { k m } . 8 6 0 \sim 1 0 0 0 \mathrm { k m }$ 的区域采用外插，

![](images/df2b4abfa7b05edcd281693548566e09c984081f93667e4642d02b7c28666e5d.jpg)  
图2自主辐射带模型表单建立流程 Fig.2Procedure of creating data table in own radiation belts model   
图3LEO空间数据网格Fig.3Data grid of LEO space

# 3.2 可选用的插值方法

空间网格点上的粒子通量大小是通过对观测数据插值获得的，而插值中最关键的步骤是利用同一空间球面上观测数据进行插值得到该球面上的网格点通量.常用的插值方法包括反距离加权法（Inverse Distance Weighting ,IDW）[18]、克里格法（Kriging）[19]、自然邻点法（natural neigh-bor)[20]、最近邻点法（nearest neighbor）[21]、多元回归法（polynomial regression）[22]、最小曲率法（minimum curvature)[23-24]、C1 连续5次双变量插值法（quintic）[25-26]、改进谢别德法（modifiedShepard’s)[27-29]径向基函数法(Radial Basis Func-tion RBF)[30-31]、三角形剖分法（triangulation）[32-34]等.这些方法在基本原理、数学模型、计算效率等方面各不相同，但在使用中一般都需要输入辅助参数例如：克里格法需要输入所采用的变异函数的类型、变程、块金值、基台值[35];改进谢别德法需要输入节函数的两个影响半径[36];径向基函数法需要确定插值使用的径向基函数[37].

在应用插值方法时，由于网格点和观测数据分布在球面上因此插值形式应为球面插值;同时由于辐射带内的粒子通量分布服从幂律谱[38]因此计算中应采用对数插值.

使用空间球面上的网格点通量可以反演出该球面上任意位置的通量.通过对反演结果的误差分析可以确定网格点通量的精度，进而确定选取的插值方法是否合适.对反演结果的误差分析主要是对反演值( $| P \rangle$ 和观测值 $( o )$ 之差( $D = P - Q )$ 进行分析.误差分析包括两部分：计算各类误差成分在总误差中的比例和计算误差大小[39].本文采用均方误差(MeanSquareErrorMSE)来描述误差比例.MSE包括系统均方误差(systematic MSE)$\mathrm { M S E _ { s } }$ 和非系统均方误差（unsystematicMSE）$\mathrm { M S E } _ { \mathrm { u } }$ 其中 $\mathbf { M S E } _ { \mathrm { s } }$ 由3部分组成，包括MSE中的偏移成分(additive MSE) $\mathrm { M S E _ { a } }$ 、缩放成分（propor-tional MSE) $\mathrm { M S E } _ { \mathrm { { p } } }$ 和 $\mathrm { M S E _ { a } \setminus M S E _ { \mathrm { p } } }$ 互相依赖成分(interdependence MSE) $\mathrm { M S E _ { i } }$ .以上误差的计算方法由式(1）\~式(6)给出:

$$
\mathrm { M S E } = \frac { \displaystyle \sum _ { i = 1 } ^ { N } { ( P _ { i } - O _ { i } ) } ^ { 2 } } { N }
$$

$$
\mathrm { M S E } _ { \mathrm { a } } = a ^ { 2 }
$$

$$
\mathrm { M S E } _ { \mathrm { p } } = ( \textit { b } - 1 ) ^ { 2 } \frac { \displaystyle \sum _ { i = 1 } ^ { N } O _ { i } ^ { 2 } } { N }
$$

$$
\mathrm { M S E } _ { \mathrm { i } } = 2 a \left( \textit { b } - 1 \right) \overline { { O } }
$$

$$
\mathrm { M S E _ { s } = M S E _ { a } \ + \ M S E _ { p } \ + \ M S E _ { i } }
$$

$$
\mathrm { M S E _ { \mathrm { u } } \ = \ M S E - M S E _ { \mathrm { s } } }
$$

式中： $N$ 为观测点数; $\boldsymbol { P } _ { i }$ 和 $O _ { i }$ 分别为第 $i$ 点的计算值和观测值； $\bar { o }$ 为观测值的平均值; $\mathbf { \Omega } _ { a }$ 和 $b$ 分别为以 $o$ 为自变量、以 $P$ 为因变量采用最小二乘法拟合出的直线的截距和斜率，

本文采用RMSE、 $\mathrm { R M S E } _ { \mathrm { s } }$ 、 $\mathrm { R M S E } _ { \mathrm { u } }$ 、 $\mathrm { R M S E } _ { \mathrm { a } }$ 、$\mathrm { R M S E } _ { \mathrm { _ p } }$ 、 $\mathrm { R M S E } _ { \mathrm { i } }$ 来描述误差大小这6个参数值的量纲与粒子通量相同,大小分别等于MSE、 $\mathbf { M S E } _ { \mathrm { s } }$ 、$\mathrm { M S E _ { u } \setminus M S E _ { a } \setminus M S E _ { p } \setminus M S E _ { i } }$ 的平方根符号与MSE、$\mathrm { M S E _ { s } \setminus M S E _ { u } \setminus M S E _ { a } \setminus M S E _ { p } \setminus M S E _ { i } }$ 相同.同时,还采用了一致性系数 $d$ 来描述 $P$ 和 $o$ 的一致程度 $, d$ 的计算方法为

$$
d = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { N } ( P _ { i } - { { O } _ { i } } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { N } ( \mathrm { ~ } | P _ { i } ^ { \prime } | + | { { O } _ { i } ^ { \prime } } | ) ^ { 2 } }
$$

式中： $\boldsymbol { P } _ { i } ^ { \prime }$ 和 $O _ { i } ^ { \prime }$ 分别由式(8)和式(9)给出:

$$
P _ { i } ^ { \prime } { = } P _ { i } - { \bar { O } }
$$

$$
O _ { i } ^ { \prime } { = } O _ { i } \ - \ \bar { O }
$$

$d$ 的取值范围在 $0 . 0 \sim 1 . 0$ 之间 $\mathbf { \nabla } \mathcal { A }$ 越接近1.0表示计算值和观测值的一致性越高，

# 3.3 插值方法的应用

本文通过对轨道高度为 $6 3 0 \mathrm { k m }$ 的两颗卫星的观测数据的处理来说明空间球面上的数据网格化方法及精度评估标准.这两颗卫星为同系列卫星各自搭载了一台由中国科学院空间中心空间环境探测研究室研制的高能粒子探测器，两台探测器的工作原理、制造工艺和技术指标完全相同.该探测器可以对6个能道的高能质子通量和1个能道的高能电子通量同时进行观测.选定的观测数据为2010年8月29日至10月10日期间能量范围为 $3 \sim 5 \mathrm { M e V }$ 的质子通量，该时间段内空间环境始终保持宁静，得到的观测数据中不包含突发性空间环境扰动引起的质子通量变化.

数据处理的具体步骤如下：

1）利用其中一颗卫星的数据选取一种插值方法给定该方法所需的各项参数值得到卫星所处空间球面上的网格点通量网格划分以经度、纬度为单位每 $1 ^ { \circ }$ 作为一个网格.

2）使用网格点通量反演另一颗卫星各观测位置的通量反演采用趋势面插值法即在网格点中选取3个点此3个点形成的三角形是可以包围采样位置的最小三角形将网格点的经度、纬度作为 $x , y$ 坐标通量作为 $z$ 坐标 拟合出一个趋势面方程利用该方程计算出观测位置的通量.

3）将反演值与观测值进行比对，得到所选定插值方法在采用选定参数时的误差分析结果

在第3.2节给出的各种插值方法中，反距离加权法、自然邻点法、最近邻点法、克里格法和径向基函数法支持球面插值，克里格法和径向基函数法在使用中需要较多的人工干预才能得到精度较高的结果，不适于工程应用.因此，在实际建模中本文选择了反距离加权法、自然邻点法和最近邻点法进行对比.表2给出了这3种插值方法处理结果的误差分析对比改变反距离加权法的输入参数会得到不同的处理结果，表2给出的是其误差分析最优的结果.从表2给出的结果可以看出反距离加权法在最优状态下得到的处理结果的精度高于自然邻点法和最近邻点法原因在于其输入参数优化处理能够大幅减小系统偏差（RMSE）中的缩放成分 $( \mathrm { \ R M S E _ { \mathrm { p } } }$ ）自然邻点法和最近邻点法没有可调整的输入参数，反距离加权法有两个输入参数可以调整其计算原理为

表2采用反距离加权法、自然邻点法和最近邻点法处理结果的误差分析对比  
Table 2Error analysis comparison of processng results of IDW,natural neighbor and nearest neighbor   

<html><body><table><tr><td rowspan="2">方法</td><td rowspan="2">a</td><td rowspan="2">b</td><td>RMSE/</td><td>RMSEu /</td><td>RMSEg /</td></tr><tr><td>(cm-²·sr-1·s-1)</td><td>(cm-²·sr-1·s-1)</td><td>(cm-²·sr-1·s-1)</td></tr><tr><td>自然邻点法</td><td>-0.69511</td><td>1. 25167</td><td>71.685 75</td><td>46.59882</td><td>54.47382</td></tr><tr><td>最近邻点法</td><td>-0.48722</td><td>1.25192</td><td>73.88811</td><td>49.80222</td><td>54.58197</td></tr><tr><td>反距离加权法</td><td>-2. 19672</td><td>1.01709</td><td>48.64780</td><td>48.48342</td><td>3.99568</td></tr><tr><td>方法</td><td>RMSEa/ (cm-²·sr-1 ·s-1)</td><td>RMSEp/</td><td>RMSE; /</td><td>MSE/MSE</td><td>MSE/MSE</td></tr><tr><td>自然邻点法</td><td>0.69511</td><td>(cm-²·sr-1·s-1) 54.58076</td><td>(cm-²·sr-1·s-1) -3.48511</td><td></td><td></td></tr><tr><td>最近邻点法</td><td>0.48722</td><td>54.65784</td><td>-2.919 82</td><td>0.42256 0.454 31</td><td>0.57744 0.545 69</td></tr><tr><td>反距离加权法</td><td>2.19672</td><td>3.70774</td><td>-1.61477</td><td>0.99325</td><td>0.00675</td></tr><tr><td>方法</td><td>MSEa/MSE</td><td>MSEp /MSE</td><td>MSE; /MSE</td><td></td><td></td></tr><tr><td>自然邻点法</td><td></td><td></td><td></td><td>d</td><td></td></tr><tr><td>最近邻点法</td><td>0.00009</td><td>0.57971</td><td>-0.002 36 -0.00156</td><td>0.97811</td><td></td></tr><tr><td>反距离加权法</td><td>0.00004 0.00204</td><td>0.54721 0.00581</td><td>-0.00110</td><td>0.97678 0.98748</td><td></td></tr></table></body></html>

$$
\hat { v } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } v _ { i } / d _ { i } ^ { p } } { \displaystyle \sum _ { i = 1 } ^ { n } 1 / d _ { i } ^ { p } }
$$

式中： $\hat { v }$ 为待插值点的属性值，即网格点通量;$\boldsymbol { v } _ { i }$ 为参与插值的离散点属性即观测位置的通量；$d _ { i }$ 为观测位置和网格点的距离，因此，可以通过调整距离的阶数 $p$ 和观测数据的范围 $n$ 获得不同的插值结果而在实际应用中一般是通过改变搜索半径 $\boldsymbol { r }$ 来控制参与插值的观测数据的范围.

在计算中 将 $r$ 的范围确定为 $1 \sim 2 2 0 1 3 . 1 4 \mathrm { k m }$ 1其中 $1 ~ \mathrm { k m }$ 为观测点至网格点距离的最小值，$2 2 0 1 3 . 1 4 \mathrm { k m }$ 为卫星轨道球面上大圆的半周长.在此范围下，本文获得了 $p$ 从 $1 \sim 1 0$ 的处理结果.图4和图5所示分别为不同 $p$ 取值下的 $d$ 和RMSE的对比.从图4可以看出，当 $r < 1 0 0 0 ~ \mathrm { k m }$ 时不同 $p$ 取值下的结果基本相同；当 $r > 1 0 0 0 { \mathrm { k m } }$ 时在 $\dot { \boldsymbol { p } } = 1$ 和 $p = 2$ 的情况下 $d$ 会随着 $r$ 的增加迅速减小 在 $p \geqslant 3$ 的情况下 $d$ 基本保持不变，仍然维持较高水平.图5所示的RMSE的变化规律与$d$ 类似在 $p = 1 \cdot 2$ 和3的情况下最小RMSE值均小于 $p { \geqslant } 4$ 但获得最小RMSE的 $\boldsymbol { r }$ 各不相同.图4和图5的结果说明，在 $p \geqslant 4$ 的情况下，当 $r >$ $6 5 \mathrm { k m }$ 时不同 $p$ 值下 $d$ 和RMSE的变化规律几乎完全相同，说明此种情况下单纯增大 $r$ 不能影响插值结果的精度，这是由反距离加权法的原理决定的.从式(10)中可知 $\boldsymbol { \mathscr { p } }$ 增大会增加距离网格点较近的实测点在插值结果中的权重.因此，当 $\boldsymbol { r }$ 取值使得搜索范围包含全部对插值结果有主要作用的实测点后，增大 $\boldsymbol { r }$ 基本不会改变插值结果的精度.

![](images/144074dcf42bb5a13ba46bd70660535a83519587959276724d1ede6ef7337528.jpg)  
图4反距离加权法取不同 $p$ 时处理结果的 $d$ 对比Fig.4Comparison of processing results of $d$ withdifferent $p$ in IDW

![](images/19b3c5d477893bbeea8077b1b05c6220488c54df698db747c47770fbf97a533b.jpg)  
图5反距离加权法取不同 $p$ 时处理结果的RMSE对比Fig.5Comparison of processing results of RMSE withdifferent $p$ in IDW

图6给出了反演结果和观测结果的对比，反演结果采用反距离加权法处理获得 $\mathbf { \Omega } _ { \mathcal { I } }$ 从1取到10选定的 $r$ 使当前 $p$ 下反演结果的RMSE最小.

![](images/d7e692f788a0dbd00734f5f992fbf094e80e178a5d8d90dbad0ea255ac920d99.jpg)  
图6质子通量观测结果和网格数据反演结果对比  
Fig.6Proton flux comparison of observation and inversion result by data grid

从图6可以发现观测结果具有以下缺陷：

1）本底较高 基本维持在大于10/( $\mathrm { c m } ^ { 2 } \cdot \mathrm { s r } \cdot \mathrm { s } )$ （204号的水平这是由探测器几何因子较小决定的.2）通量范围在 $1 0 \sim 1 0 0 ,$ 《 $\mathrm { c m } ^ { 2 } \cdot \mathrm { s r } \cdot \mathrm { s } )$ 的区间内,观测结果抖动比较严重这是受仪器本底噪声和观测数据采用遥测分层值方式采集的共同影响造成的.

理想的网格数据给出的反演结果，应该可以对观测数据中出现的以上缺陷予以修正.对比图6给出的各阶反演结果，可以发现它们具有以下特点:

1）通量大于 $1 0 0 / ( \ \mathrm { c m } ^ { 2 } \ \bullet \ \mathrm { s r } \ \bullet \ \mathrm { s } )$ 时各阶反演结果与观测结果一致性均较高.2）通量小于100/( $\mathrm { c m } ^ { 2 } \cdot \mathrm { s r } \cdot \mathrm { s } )$ 时低阶( $p =$ 1 $\begin{array} { r } { p = 2 ^ { \cdot } } \end{array}$ ）反演结果具有较好的消除抖动的效果，对于本底以下的通量具有较好的外推效果

因此使用反距离加权法进行处理，当距离阶数 $p$ 选定为1或2时得到的反演结果合理程度更高;同时，根据图4和图5给出的误差分析结果选择合适的搜索半径 $\boldsymbol { r }$ ，可以使反演结果精度最高.

# 4结论

本文说明了自主辐射带模型属于动态模型的原因指出了自主模型相比于AP8/AE8的改进之处即可以给出各种辐射带周期性变化和扰动变化；讨论了辐射带自主建模的目标和思路，针对LEO空间数据网格化问题，根据目前我国自主探测数据的实际情况，使用了空间分层的方式对每一个卫星所处空间球面上的数据分别进行处理;在生成数据网格的插值计算中，根据各常用插值方法的特点选择反距离加权法、自然邻点法和最近邻点法作为考察的插值方法，通过对网格数据反演结果的误差分析和与观测结果的比对，确定反距离加权法具有更高的精度，且反距离加权法在采用低阶距离的情况下生成的数据网格得到的反演结果具有更高的合理性，并可以对实测数据中的一些缺陷进行弥补.

本文讨论的LEO空间数据网格化方法的评价标准建立在误差分析的基础上，是一种数值分析的方法.实际上辐射带的形成有着复杂的物理机制其内部高能带电粒子的分布也服从相应的物理规律因此辐射带建模不能脱离物理理论的指导.在后续工作中需要重点改进的地方是将物理理论与数值分析方法相结合，利用物理理论对数值分析方法进行完善，

# 参考文献(References)

[1] Bothmer V ,Daglis IA.Space weather: Physics and efects [M]. New York: Springer 2007: 154-159.   
[2]徐文耀.地球电磁现象物理学[M].合肥:中国科学技术大学 出版社 2009:388-389. Xu WY.Physics of electromagnetic phenomena of the earth [M].Heifei:University of Science and Technology of China Press 2009:388-389( in Chinese).   
[3]沈自才.空间辐射环境工程[M].北京:中国宇航出版社， 2013: 4-29. Shen Z C. Space radiation environmental engineering[M].Beijing:China Astronautic Publishing House ,2013:4-29(in Chinese).   
[4]姜景山,王文魁 都亨 等.空间科学与应用[M].北京:科学 出版社 2000:649-652. JiangJS,WangWK,DuH,etal.Space science and applications[M].Beijing: Science Press 200O:649-652(in Chinese).   
[5]褚桂柏.空间飞行器设计[M].北京:航空工业出版社,1996: 49-54. Chu G B.Space vehicle design [M].Beijing: Aviation Industry Press 1996: 49-54( in Chinese).   
[6] Ginet G P,O'Brien TP.Trapped radiation and plasma models requirements specification ,AE-9 /AP-9 [R].Washington ,D.C.: NASA 2009.   
[7]Vette JI. The AE-8 trapped electron model environment ,NASA STI/Recon Technical Report N,1991 92: 24228 [R]. Washington ,D.C.: NSSDC/WDC-A-R&S 1991.   
[8] Sawyer D M,Vette JI.AP-8 trapped proton environment for solar maximum and solar minimum ,NASA STI/Recon Technical Report N,1976,77: 18983[R].Washington,D.C.: NSSDC/ WDC-A-R&S ,1976.   
[9]王世金,叶宗海.实践四号卫星高能质子重离子探测器探测 数据初步分析[J].航天器工程1995 4(3)：1-7. Wang SJ,Ye Z H. Initial data analysis from the energetic proton and heavy ion detector on-board SJ-4 satelite[J].Spacecraft Engineering $, 1 9 9 5 \ A ( \ 3 ) : 1 - 7 ($ in Chinese) .   
[10]师立勤,王世金 叶宗海,等.实践五号高能粒子环境探测 结果[C]//实践五号卫星空间探测与试验成果学术会议论 文集.北京:中国空间科学学会空间探测专业委员会 2002: 51-61. ShiL Q,Wang SJ,Ye Z H.et al.Energetic particle environment detection results by SJ-5 satellite[C]//Symposium of the Scholar Meeting on Space Exploration and Test Results by SJ-5 Satelite.Beijing:SpaceExporation CommiteeofChinee Society of Space Research 2002: 51-61( in Chinese).   
[11]王世金 朱光武 梁金宝 等.FY-1C卫星空间粒子成分监测 器及其探测结果[J].上海航天 2001,18(2):24-28. Wang SJ,Zhu GW,Liang JB,et al.FY-C space particle composition monitor and the results detected[J].Aerospace Shanghai 2001 18(2):24-28(in Chinese).   
[12]Leonov A Cyamukungu M ,Cabrera J,et al.Pitch angle distribution of trapped energetic protons and helium isotope nuclei measured along the Resurs-01 No.4 LEO satelite[J]. Annales Geophysicae 2005 23(9):2983-2987.   
[13]王鹏 徐青 李建胜等.空间环境建模与可视化仿真技术 [M].北京:国防工业出版社 2012:92-95. Wang P Xu Q Li ${ \mathrm { ~ J ~ S ~ } } _ { \mathrm { { e t } } }$ al. Space environment modeling and visual simulation techniques [M].Beijing:National Defence Industry Press 2012:92-95(in Chinese).   
[14]王世金朱光武 梁金宝.我国空间环境天基监测网建设 [C]//中国空间科学学会空间探测专业委员会第十六次学 术会议论文集(上).北京:中国空间科学学会空间探测专 业委员会 2003:65-68. Wang S J Zhu G W Liang JB. Space-based space weather monitoring network building in China[C]//Symposium of the 16th Scholar Meeting Held by Space Exploration Committee of Space Science Society in China(I).Beijing: Space Exploration Committee Chinese Society of Space Research 2003: 65-68(in Chinese).   
[15]Friedel RHW,Bourdarie S,Cayton T E.Intercalibration of magnetospheric energetic electron data [J]. Space Weather ， 2005 3(9):2561-2570.   
[16]庄洪春.宇航空间环境手册[M].北京:中国科学技术出版 社 2000:140-148. Zhuang H C.Aerospace environmental handbok [M]. Beijing: China Science and Technology Press,2000:140-48(in Chinese).   
[17]O'Brien TP.A framework for next-generation radiation belt models[J].Space Weather 2005 3(7) :1891-1904.   
[18] Serón FJ,Badal JI Sabadell FJ.Spatial prediction procedures for regionalization and 3-D imaging of Earth structures [J]. Physics of the Earth and Planetary Interiors,20O1,123(2): 149-168.   
[19]Isaaks EH Srivastava R M.Applied geostatistics [M].New York: Oxford University Press,1989:279-322.   
[20]Watson D F.Contouring: A guide to the analysis and display of spatial data[J].Computer Methods in the Geosciences,1993, 19(10) : 1571-572.   
[21]Aurenhammer F.Voronoi diagrams:A survey of a fundamental geometric data structure [J]. ACM Computing Surveys (CSUR) 1991 23(3):345-405.   
[22]PIZOR P J.Principles of geographical information systems for land resources assessment [J]. Soil Science ,1987,144(4): 306.   
[23]BarrodaleISkea D,Berkley M,etal. Warping digital images using thin plate splines[J].Pattern Recognition 1993 26(2): 375-376.   
[24]Powell MJD.Tabulation of thin plate splines on a very fine two-dimensional grid,DAMTP 1992/NA2[R]. Cambridge: University of Cambridge,1992.   
[25]Akima H.Algorithm 761: Scattered-data surface fitting that has the accuracy of a cubic polynomial[J].ACM Transactions on Mathematical Software( TOMS) 1996 22(3) :362-371.   
[26]Renka RJ,Cline A K.A triangle-based $\mathrm { C ^ { 1 } }$ interpolation method[J]. Rocky Mountain Jourmal,1984 14(1) : 223-238.   
[27]Franke R,Nielson G.Smooth interpolation of large sets of scattered data[J].International Journal for Numerical Methods in Engineering,1980 15(11) :1691-1704.   
[28]Renka R J. Algorithm 790: CSHEP2D: Cubic shepard method for bivariate interpolation of scattered data[J].ACM Transactions on Mathematical Software（TOMS),1999 25(1) :70-73.   
[29] Shepard D.A two-dimensional interpolation function for irregularly-spaced data[C]//Proceedings of the 1968 23rd ACM National Conference.New York: ACM 1968:517-524.   
[30]Franke R.A critical comparison of some methods for interpolation of scatered data,NPS-53-79-003[R].Monterey ,CA: Naval Postgraduate School,1979.   
[31]Hardy R L.Theory and applications of the multiquadric-biharmonic method 20 years of discovery 1968-1988[J].Computers & Mathematics with Applications,1990 19(8-9):163-208.   
[32]Peucker TKFowlerRJ,Little JJ,etal.The triangulated irregular network [C]//International Symposium on Cartography and Computing: Applications in Health and Environment.Gaithersburg,Maryland:AmericanCongress on Surveying and Mapping ,1978:516-532.   
[33]Krajewski S A ,Gibbs B L. Understanding contouring:A practical guide to spatial estimation and contouring using a computer and basics of using variograms [M].Boulder ,CO: Gibbs Associates 2001: 20-25.   
[34]Lee D T,Schachter B J.Two algorithms for constructing a Delaunay triangulation[J].International Journal of Computer & Information Sciences ,1980 9(3) : 219-242.   
[35]侯景儒,尹镇南 李维明 等.实用地质统计学[M].北京:地 质出版社1998:45-50. HouJR,YinZN,LiWM,etal.Practical geologystatistics [M].Beijing: Geological Publishing House,1998:45-50（in Chinese) .   
[36]张维娜吕云霄吴美平.改进谢别德插值方法在地磁图构 建中的应用[J].导航与控制 2011,10(1):28-32. Zhang W N LvY X,Wu MP.Application of modified shepard interpolation in geomagnetic map[J].Navigation and Control， 2011 ,10(1) :28-32(in Chinese).   
[37]魏义坤 杨威刘静.关于径向基函数插值方法及其应用 [J].沈阳大学学报 2008 20(1):7-9. WeiYK,YangW,Liu J.Interpolation methodof radial basis function and its application[J].Journal of Shenyang University 2008 20(1):7-9(in Chinese).   
[38]涂传诒.日地空间物理学:行星际与磁层.下册[M].北京: 科学出版社,1988:118-127. Tu C Y.Sun-earth space physics: Interplanetary and magnetosphere （I) [M]. Beijing: Science Press ,1988: 118-27（in Chinese) .   
[39]Willmot CJ.On the validation of models[J].Physical Geography,1981 2(2) :184-194.

# Modeling technology of radiation belt in LEO based on data gridding methods

CHANG Zheng1²,WANG Yongmei\*’,TIAN Tian³ ,ZHANG Xianguo'

(1.National Space Science Center,Chinese Academy of Sciences,Beijing 1Oo19O,China; 2.College of Earth Science,University of Chinese Academy of Sciences,Beijing 1Ooo49,China; 3．Unit 61741,Beijing 100094,China)

Abstract:The energetic charged particle in the radiation belts of earth is the main environmental factor which can result in performance degradation and even failure of the material and device on spacecraft ,so the accuracy of radiation belts model which is being used during design phase of spacecraft is very important to spacecraft performance of space mision and survivability.In the development of radiation belts model based on ourown country'sdata from exploration of radiation belts,the gridding of discrete dataisa fundamental task．The key facts of data from Chinese exploration of radiation belts were introduced,the goal and road-map of modeling were described,theapplication of interpolation in griding of modeling of radiation belts in lowearth orbit(LEO） was discussed,and the significant errors were analysed.The result of interpolation indicates that in mainly interpolation methods ,inverse distance weighting（IDW）,natural neighbor and nearest neighbor are most suitable for engineering calculation,the particle flux which is inverted from data grid produced by IDW has the highest precision,and the result from IDW will be more accurate when IDW uses smallexponent of distance.

Key Words:space environment; radiation belts; data grid; interpolation; inverse distance weighting; natural neighbor; nearest neighbor