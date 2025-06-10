# 干旱区地膜覆盖农田下垫面对东亚 气候效应的数值模拟

赵舒曼},²，左洪超¹，卫翔谦}³，杨宾¹4，武利阳'，王士新

（1．兰州大学大气科学学院，甘肃 兰州730000；2．中国科学院大气物理研究所大气边界层物理与大气化学国家重点实验室,北京100029;3．中国辐射防护研究院,山西 太原03006；4．中国人民解放军63898 部队,河南 济源459000)

摘要：农田铺设地膜是目前我国干旱半干旱地区采用较广泛的耕作方式。为了研究大面积地膜覆盖对东亚区域的气候效应,基于地膜试验观测与理论研究,建立了地膜覆盖的地—气一水热传输过程模型,并将地膜覆盖农田下垫面模块引入区域气候模式 $\mathtt { R e g C M 4 }$ 和WRF模式中,对17a夏季气候进行模拟试验。通过RegCM4模式输出的降水量、土壤温度、土壤湿度、感热通量和潜热通量等参量,与试验观测值、理论值进行对比,并通过WRF模式输出结果进行验证。结果表明：加入地膜覆盖农田下垫面模块的区域气候模式能够较为真实的描述其下垫面特征。进一步分析模拟结果发现,通过地膜覆盖影响近地面水热传输并作用于区域位势高度场、风场,进而影响大范围水汽输送,最终造成我国西北、华南地区降水减弱，西南地区和淮河流域降水增加。

关键词：地膜覆盖； $\operatorname { R e g C M } 4 . 3$ ；WRFV3.6；数值模拟；气候效应；干旱区

陆面过程是大气圈与地球各个圈层之间进行物质、能量交换体系中的重要组成部分，地一气相互作用的热力、动力过程研究推动了大气科学领域的发展[1-3]。而干旱区占陆地面积 $40 \%$ 左右，地表生态脆弱、物理特征复杂(4-7],对气候变化响应敏感且受人类活动影响较大[8]；加之大气的非均一性,使得干旱区的变化对其它区域气候产生连锁效应[9]。因此，研究干旱区人类活动对陆面过程的作用有助于进一步了解及预测未来天气、气候的变化情况，对当前人类活动有一定指导意义[10]。近年来,干旱区农业种植方式发生了变化，而农田作为陆地生态系统中的重要成分,其天气、气候效应不容忽视[1；干旱区农田的气候效应值得研究。

近30a来，针对干旱区农作物大面积推广地膜种植，以期保温、保湿，提高农田作物耐寒、抗旱的特效，使农业环境较为恶劣的地区同样可以大量种植农作物[12-13]。研究表明,农田被地膜覆盖后会导致近地层微气象环境变化,如地表辐射平衡改变[14]土壤热通量变化[15]、表层土壤水分蒸发和热量散失受阻，直接影响地表与近地层的物质、能量交换[16-18]。近年来已经有学者关注地膜覆盖农田的微物理过程并开展试验观测研究,如陆莎等[19]在内蒙古阿拉善左旗通过农田一地膜对比观测试验，研究地膜对地表水热传输、大气能量平衡过程的影响；Yang 等[20]在观测基础上,开发了一套适用于研究干旱区地膜覆盖农田下垫面陆面过程的新模式（TBLSHAW_MULCH）。然而，单独陆面过程模式可模拟铺设地膜所带来的近地层物理量变化，却无法模拟局地地膜铺设对较大范围环流、水汽输送及区域降水的改变。大面积铺设塑料薄膜对大尺度水汽输送等物理过程及区域气候变化[21-22]不可忽视,却研究甚少。因此，有必要在气候数值模型中引入地膜覆盖农田下垫面模型，针对大范围地膜覆盖农田对天气、气候变化所产生的影响进行模拟研究。

本文在现有研究[20]和观测试验的基础上,建立地膜覆盖的地一气一水热传输过程模型，并在$\mathrm { R e g C M } \ 4 . 3$ 模式耦合的BATS（biosphere-atmospheretransferscheme)数值模型和WRFV3.6模式中引入地膜覆盖农田下垫面子模块，将两种模式模拟结果进行比较、验证;在模式成功表征地膜覆盖农田所产生的增大土壤温度、湿度及感热输送、减小潜热输送等效应的基础上，以 $\mathrm { R e g C M } ~ 4 . 3$ 模式模拟结果为例，针对地膜覆盖农田近地层微气象效应对大尺度环流、东亚夏季风降水所产生的影响及机理,具体分析干旱区地膜覆盖农田对东亚气候系统产生的影响。

# 1试验设计及资料

# 1.1地膜覆盖农田下垫面模型的建立

研究表明，农田灌溉会改变近地层波文比[23-24],使得潜热分配比重增加,感热分配相对减少，带来土壤的冷却降温;同时灌溉使得土壤湿度增加，蒸发量相应增大，大气中水汽含量增加，近而导致云的覆盖量增加;并通过对流输送造成灌溉下游地区降水增加，并间接影响陆地一海洋热对流，从而影响季风[25]

与未铺设地膜的农田相比，铺设地膜后灌溉仍然会增加土壤湿度(这一点由内蒙古地膜试验观测数据可见，图略），但土壤水分蒸发基本被阻断，降低了该区域上空大气水汽含量及云覆盖量，使本区域范围内降水减少；土壤水分蒸发的阻断使得土壤中更多的水分用于植被吸收蒸腾以及经土壤渗透汇入地下水径流。理论上讲，由地膜覆盖所影响的云量变化经过对流输送可能导致下游降水减少，同时局地对流引起较大尺度的对流输送的改变，也会影响周边甚至更大区域；二者共同作用，改变了区域水循环状况并间接影响陆地一海洋热对流和季风，影响区域降水情况，其综合效应将会在模式中验证。与此同时，蒸发潜热减少会相应带来土壤温度升高；而我国西北地区所使用地膜基本为偏白色透明薄膜，会增大地表反照率。结合内蒙古地膜试验观测数据可知（图略），相较未铺设地膜的下垫面而言，地膜下垫面的表层土壤温度、湿度以及向上长波辐射较高，潜热通量较低，确实有增温、保湿的效果。

上述农田覆盖地膜的区域气候效应的理论基于内蒙古地膜观测试验和现有研究，需要模式进一步验证。基于现有研究及地膜试验观测数据，本文建立土壤一地膜一植被一近地面层水汽、热量传输体系，形成新的地膜覆盖农田下垫面类型引入数值模式,通过对比试验研究农田覆盖地膜后近地层物理量及大范围区域气候的影响。本研究为简化数值计算过程作出假设，基于以下假设建立地膜覆盖农田

物质、能量传输方案：

（1）地膜覆盖农田，使得土壤层向大气的水汽输送完全阻断[4]；

（2）忽略薄膜与土壤间的空气，假设地膜层紧 贴土壤,温度与土壤保持一致;

（3）地膜透光性良好，忽略其对太阳辐射影响。

普通农田与地膜覆盖农田下垫面物质能量交换的物理过程如图1所示。对于感热输送有 $H _ { f } =$ $H _ { g 1 } + H _ { f 0 }$ ;潜热输送同理， $E _ { \scriptscriptstyle f } = E _ { \scriptscriptstyle g 1 } + E _ { \scriptscriptstyle f 0 }$ 。植被潜热输送可表示为 $H _ { f } = \rho _ { a } \delta _ { f } C _ { p } C _ { D } V _ { a } \left( T _ { a f } - T _ { a } \right) , H _ { g 1 } = \rho _ { a } C$ $\big [ C _ { \mathrm { { S o I L C } } } \delta _ { f } U _ { a f } \big ] ( T _ { g 1 } - T _ { a f } )$ ;相应地,潜热输送过程表示 $: E _ { f } = \rho _ { a } c _ { a } (  q _ { a f } - q _ { a }  ) , E _ { g 1 } = \rho _ { a } C _ { G } f _ { g } ( 1 - \varphi ) (  q _ { g s } -  \frac { } { }  $ $q _ { a f } ^ { \quad }$ ),式中各字母代表物理意义见表1。

表1模式物理过程参数意义对应表  
Tab.1Physical meanings of the parameters in the model   

<html><body><table><tr><td>参数</td><td>物理意义</td><td>参数</td><td>物理意义</td></tr><tr><td>H</td><td>植被感热输送</td><td>Hg</td><td>植被下方土壤向冠层 下方空气输送感热</td></tr><tr><td>Hfo</td><td>冠层内叶片向冠层大 气输送感热</td><td>CsOILC</td><td>土壤与植被之间的传 输系数</td></tr><tr><td>Sf</td><td>植被覆盖面积占格点 百分比</td><td>Cp</td><td>空气比热</td></tr><tr><td>CD</td><td>土壤、植被间空气阻 力系数</td><td>Va</td><td>风力强度</td></tr><tr><td>Tg1</td><td>土壤温度</td><td>Taf</td><td>植被与土壤之间的气 温</td></tr><tr><td>qaf</td><td>植被与土壤之间空气 的湿度</td><td>qgs</td><td>土壤水蒸气饱和状态 湿度</td></tr><tr><td></td><td>植被覆盖区域地膜覆 盖比例</td><td></td><td></td></tr></table></body></html>

下垫面能量守恒方程：

$$
R - H - L E - G _ { 0 } = 0
$$

$$
H = H _ { s } + H _ { m } + H _ { f }
$$

$$
E = E _ { s } + E _ { f }
$$

式中： $R$ 代表地表吸收净辐射; $H$ 为感热输送; $H _ { f }$ 、$H _ { \mathfrak { m } } \cdot H _ { s }$ 分别为植被、地膜覆盖土壤、未覆盖地膜土壤分别向近地面空气的感热输送； $E _ { s } \setminus E _ { f }$ 为未覆盖地膜土壤、植被对空气的潜热输送。假设地膜覆盖完全切断了土壤向大气的水汽输送且完全覆盖，则地膜覆盖农田下垫面 $E _ { s } = 0$ C

$$
h _ { \boldsymbol { s } } = S _ { \boldsymbol { g } } - L _ { f } S _ { \boldsymbol { m } } - F _ { \boldsymbol { s } } - L _ { \boldsymbol { v } } F _ { \boldsymbol { q } }
$$

$$
\frac { \partial S } { \partial t } = P _ { _ r } ( 1 - \delta _ { f } ) - R _ { s } + L _ { s } + S _ { _ m } - D _ { _ \omega } - F _ { q }
$$

$$
\boldsymbol { F } _ { q } = \boldsymbol { F } _ { q f } + \boldsymbol { F } _ { q s }
$$

$$
\alpha = \left\{ \begin{array} { l l } { 0 . 2 6 \mathrm { e } ^ { ( 0 . 2 1 - 0 . 0 0 3 \theta ) } } & { , c < 0 . 3 3 } \\ { ( 0 . 2 6 - 0 . 0 8 c ) \mathrm { e } ^ { ( 0 . 2 1 - 0 . 0 0 3 \theta ) } , 0 . 3 3 \leqslant c \leqslant 0 . 6 5 } \\ { 0 . 1 8 \mathrm { e } ^ { ( 0 . 2 1 - 0 . 0 0 3 \theta ) } } & { , c > 0 . 6 5 } \end{array} \right.
$$

地表土壤能量平衡方程如(4)式，其中 $\boldsymbol { F } _ { s }$ 代表下垫面(土壤和植被)向大气的感热输送。表层土壤含水量平衡方程如(5)式， $s$ 为土壤含水量; $\boldsymbol { P } _ { \boldsymbol { r } }$ 为土壤在降水过程接收的水分； $\delta _ { f }$ 代表植被比例; $R _ { s }$ 代表地表径流水分流失； $L _ { s }$ 代表水分传输（下层土壤向上层）； $S _ { m }$ 代表冰雪融化； $D _ { { \scriptscriptstyle w } }$ 为植物滴落到土壤的水分； $\boldsymbol { F } _ { q }$ 表示下垫面（植被 $\boldsymbol { F } _ { \boldsymbol { q } f }$ 和未加地膜的土壤$F _ { _ { q s } }$ )向大气的水汽通量输送。此外,地膜的覆盖对地表反照率也有所改变，因此，与试验场观测数据相结合并经过验证,引入土壤反照率参数化算法〔如（7)式所示]。式中 $\alpha$ 为反照率； $\boldsymbol { \mathscr { c } }$ 表示植被覆盖所占面积比例。

根据上述机理构建地膜覆盖农田下垫面水分、热量传输平衡过程及反照率算法，构建新的地膜覆盖农田下垫面类型,尽可能反映地膜覆盖农田的实际情况。

# 1.2 模拟方案设计

将"地膜覆盖农田”下垫面类型引入数值模式 进行模拟，对照组为普通农田下垫面，实验组为地膜

(a)普通农田 (b)地膜覆盖农田↑  
土壤直接蒸发 直接蒸发的潜热 植被潜热 冠层蒸发 降 植夜潜热 冠层蒸发 降水 凝结沉降 冠层感热 土壤感热水 结沉 ?降← 冠层 热 裸土沉降 冠层内潜热 裸土沉降 内感热1 = 向植 被的热 冠层 凝结 向植 被的热 塑料地膜 二 冠层 凝结 向植被 的感热 地表径流1 地表径流2 00 2C mmm m融雪 士壤热通量 土壤湿度通量 地下径流 融雪 土壤热通量 土壤湿度通量 地下径流

注：水循环以实线表示，能量变化以虚线表示。

![](images/d429698185ab873cf508319cee5ba1e8bf376252b1b3db81912a878d7a0bd33e.jpg)  
图1下垫面物质能量交换的物理过程示意图  
Fig.1Physical process diagram of the material energy exchange in two underlying surfaces.   
图2模拟区域的土地使用类型分布  
Fig.2 Simulated area and vegetation coverage

3.灌溉农田和牧场 7.草地 11.落叶阔叶林15.混交林 19.裸地或低植被覆盖地 23.裸露地面苔原  
4.混合旱地/灌溉农田和牧场8.灌木 12.落叶针叶林 16.水体 20.草本苔原 24.冰雪

模拟结果进行对比、验证。

覆盖农田下垫面。研究区域的土地类型分布如图2a所示，图2b中阴影区域为试验对比区域，在此区域内采用地膜覆盖农田下垫面。由于我国西北大部分地区干旱少雨，农业生产中铺设地膜保温保湿的现象较为普遍，因此，选择该地区进行敏感性试验具有较好的代表性。模拟时间为1995一2011年，每年5月1日起到9月1日结束，以每年5月份的模拟作为 spinup,选取每年6一8月作为模拟结果,对普通农田下垫面和农田覆盖地膜下垫面输出状况进行对比分析。

1.2.1 RegCM模式参数设定 $\mathrm { R e g C M } \ 4 . 3$ 模式模拟采用Lambert 投影,模拟区域中心点位于 $9 8 ^ { \circ } \mathrm { E }$ ，$3 2 ^ { \circ } \mathrm { N }$ ,格点间距为 $6 0 ~ \mathrm { k m }$ ,格点数量为 $1 3 0 \times 1 2 0$ 。垂直方向14层，顶层边界为 $5 0 \ \mathrm { h P a }$ 。边界方案采用指数松弛，积云对流方案选用Grell方案。模拟时间步长为 $1 0 0 \mathrm { ~ s ~ }$ ，每 $3 0 ~ \mathrm { m i n }$ 计算一次太阳辐射，每 $6 0 0 \mathrm { ~ s ~ }$ 调用一次陆面过程模型。

1.2.2WRF模式参数设定WRF模式投影方式和中心经纬度与 $\operatorname { R e g C M }$ 一致。采用两重网格嵌套，外层区域格点数为 $1 1 2 \times 1 0 0$ ,网格距 $6 0 ~ \mathrm { k m }$ ;内层嵌套区域为地膜覆盖农田下垫面控制区，格点数为$1 6 6 \times 7 9$ ，网格距 $2 0 ~ \mathrm { k m }$ ，垂直分为35层。参数化方案具体选取：rrtm长波辐射方案、rrtmg 短波辐射方案、Monin-Obukhov（Janjic）近地层方案、Thompson云微物理参数化方案、RUC陆面参数化方案、Mel-lor-Yamada-Janjic边界层参数化方案、Kain-Fritsch积云参数化方案。模拟时间步长为 $3 0 \mathrm { ~ s ~ }$ 。

# 1.3 数据资料

RegCM模式的初始场、边界驱动数据选用NNRP2资料，侧边界条件 $6 \textup { h }$ 更新一次，采用OISST海温驱动场资料。WRF模式采用欧洲中心（ECM-WF) $1 ^ { \circ } \times 1 ^ { \circ }$ 分辨率的格点资料作为初始场和边界条件，侧边界条件每 $6 \textup { h }$ 更新一次。

# 2 两种模式模拟地表参量对比

为观察加入地膜后近地面气象参数的差异、分析气候模拟的可行性、增加模拟可信度，选取$\operatorname { R e g C M }$ 模式和WRF模式在2011年的模拟结果，对加入地膜前后和模式之间进行对比，并分析地膜在地一气交换中的作用。由于两种模式土壤分层不同，为避免插值误差，此处未将WRF模拟 $5 \ \mathrm { c m }$ 土层土壤温度和含水量插值到 $\operatorname { R e g C M }$ 的 $1 0 \ \mathrm { c m }$ 土壤层进行对比，仅比较趋势。以2011年模拟结果为例，将图2b中红色方框( $3 6 ^ { \circ } \sim 3 8 ^ { \circ } \mathrm { N }$ ， $1 0 6 ^ { \circ } \sim 1 0 8 ^ { \circ } \mathrm { E }$ ）内模拟结果进行区域平均，选取可准确表征地一气相互作用过程中下垫面状态变化的降水，土壤湿度、温度、地表感热、潜热输送进行对比分析。

由图3各参量变化趋势可见，模拟地膜覆盖农田下垫面与普通农田下垫面特征量有显著区别，地膜覆盖农田下垫面潜热通量普遍小于普通农田下垫面，降水量也偏小;虽然两种模式所取表层土壤深度不同,但都模拟出了地膜覆盖农田的表层土壤温度、土壤含水量及感热通量大于普通农田这一现象;WRF模式地膜下垫面降水表现出一定滞后，降雨量大部分小于无地膜覆盖的地区； $5 \ \mathrm { c m }$ 处土壤含水量离地表较近，很大程度上受到地表降雨量的影响，因此与降雨量变化呈现出相似状态一无地膜覆盖的地区土壤含水量大于地膜覆盖地区，且两种下垫面下土壤含水量峰值出现时间与模拟降水峰值出现时间一致。尽管两个模式在对降水模拟的差距带来了土壤含水量的差距，但仍然可以看出，铺设地膜后土壤含水量下降幅度减小（尤其是5月9日降水发生之后);此外，土壤的温度、湿度、感热通量、潜热通量的变化趋势在两种模式中的模拟基本一致，表示地膜模型在两种模式中能够得到较为可信的刻画。

以RegCM模拟结果为例，将图3a\~3e作为一组进行分析。降水因素对其他下垫面特征量变化过程有直观的影响;在一次降水过程发生之前的时间段内，土壤含水量随时间递减。由于普通农田下垫面蒸发量大于地膜覆盖农田，土壤含水量递减速度也远高于地膜覆盖农田。在降水过程发生之后，不同下垫面土壤含水量的差异才得以减小。同时，土壤含水量的不同带来蒸发差异进而影响了地表温度。整体而言，由于地膜在一定程度上阻止了土壤水分蒸发，因而地膜覆盖农田下垫面的地表温度普遍高于普通农田。降水发生前的一段时间，随着土壤含水量不断减小，蒸发带走的热量有所减少，因而地膜覆盖农田与普通农田的表层土壤温差减小；而降水过程的发生增大了表层土壤含水量，进而使得两种下垫面模拟结果地表温差增大。

地膜覆盖农田下垫面的土壤温度高于普通农田，根据观测资料，同等条件下地膜覆盖农田感热输送强度远远高于普通农田，图3d较好表征了这一特点。由图3d可见，土壤含水量较高时，地膜覆盖农田下垫面与普通农田下垫面的感热差异较大；而该

uu/鲁 2015105 (a)RegCM模式 农田 --地膜覆盖农田4.40353025201510 (b)RegCM模式  
王 45 (c)RegCM模式  
℃ wWWW 办 WwwwwwwM200100-100500 (e)RegCM模式400300200100 AAM20 (f)WRF模式  
/鲁 151050.28 (g)WRF模式0.260.220.200.180.1650 (h)WRF模式  
王 4030 WwWMMWMMWMW  
P 20 W600 (i)WRF模式400 WMWA200 MAAAAN-200500 (j)WRF模式400300200100AA2011-05-04 2011-05-11 2011-05-18 2011-05-25 2011-06-01 2011-06-08日期/年-月-日

差异随着土壤含水量的降低而逐渐减小。同理，图3e潜热输送走势图显示，地膜覆盖农田下垫面潜热输送远低于普通农田潜热输送量，这与观测结果相接近。当普通农田土壤含水量较高时，地表潜热输送增加、感热输送减少；当土壤含水量极低时，地表潜热输送减小、感热输送增加，与地膜覆盖农田下垫面变化趋势差异减小。

上述分析表明，在区域气候模式中增加地膜覆盖农田下垫面模块后，下垫面特征量的模拟结果与理论相符。这说明模式可以较准确地刻画铺设地膜的农田下垫面特征。通过两种模式模拟结果的对比也可以看出，加入地膜覆盖农田下垫面类型后，两种模式对下垫面特征量变化趋势的模拟基本一致，模拟结果较为可信。

# 3地膜覆盖农田下垫面气候效应分析

通过对比RegCM和WRF模式对地膜效应的模拟可见，地膜的作用在两种模式中有着类似的表现。比较地膜覆盖农田与普通农田的模拟结果可见，本文所选方法能够较为贴切地表现出地膜对农田下垫面地一气相互作用的影响。因此，以 $\operatorname { R e g C M }$ 模式模拟结果分析地膜铺设的气候效应。

# 3.1 环流形势

比较分析6一8月有地膜方案与无地膜方案在$8 5 0 \ \mathrm { h P a }$ 风场、位势高度场之差(图4)可见，地膜覆盖农田方案使试验区域上空 $8 5 0 \ \mathrm { h P a }$ 位势高度降低，风速增加;对西南气流向西北转向、加强有促进作用。6月份，地膜方案使得参照试验区域风场增强，气压降低，呈现气旋性环流距平；副热带高压向北推进的同时，我国东北地区也出现高压区。西南气流增强，加强了来自印度洋的水汽输送;气流经华中向西北转向，气流的交汇为我国中部带来水汽。7月环流形势较6月有所不同：参照试验区域低压下游出现较强的反气旋环流距平区域，同时低压系统的东南方向，即四川、重庆、湖南交接地区生成较弱的反气旋。三者相互作用促进了西南气流向西北、华北方向的输送，促进华北地区降水形成的同时，也削弱了华南地区来自南海的水汽输送。总体来看，地膜的铺设使得7月季风环流有向西偏移的趋势。8月份参照试验区域仍表现出较强的气旋状态，与之相伴的是华北、东北、江淮流域大范围的高压区，二者配合使得西南气流的西北输送更加顺畅；北部反气旋性高压南下至江淮流域,影响面积增大;受其影响，华中、华北、东北降水得到增强，而华东、华南降水减弱。 $5 0 0 ~ \mathrm { { h P a } }$ 高度环流形势与 $8 5 0 \ \mathrm { h P a }$ 不同。地膜方案加强了试验控制区域的负位势高度变化，减弱了 $3 0 ^ { \circ } \sim 4 0 ^ { \circ } \mathrm { N }$ 之间的西风气流，而增强了 $4 0 ^ { \circ } \sim$ $5 0 ^ { \circ } \mathrm { N }$ 之间的西风气流，使 $3 0 ^ { \circ } \sim 4 0 ^ { \circ } \mathrm { N }$ 之间区域夏季风环流呈现向西偏移的趋势（图略）。

# 3.2 降水量分布变化

加入地膜覆盖后，地表向大气的水汽输送受到抑制；大范围的地膜使用必将影响此区域内大气层的水汽输送，使得产生降水的条件不能满足，进而对该区域降水带来抑制作用。虽然地膜铺设导致的环流变化在图4所示参照试验区域所造成的气旋环流有利于外界水汽输入，抵消掉当地水汽的减少，但通过降雨量的模拟可以看出，地膜会导致参照试验地区降雨量减少。加入地膜前后夏季平均总降水量的模拟(图5)可以验证这一理论。由加入地膜前后对注：地膜方案减去无地膜方案,单位： $\mathbf { m } \cdot \mathbf { s } ^ { - 1 }$ 、位势米。

![](images/d71e64bae82273ac654466267621b0ecbf2d165f51b5fb7796db72eccafb8c89.jpg)  
图4 $8 5 0 \ \mathrm { h P a }$ 风场、位势高度场偏差   
Fig.4 $8 5 0 \ \mathrm { h P a }$ wind field and potential field deviation

![](images/9c5d5cf85629af439ae932648200db33b871f57a2b47feda97b05bcecd6ed4b7.jpg)  
Fig.5Average total rainfall in summer

![](images/fa8569a691e0ecf2e8a67380d1da837f2edddeef406ec3164ae8d0b7cd5a3ea3.jpg)  
图5夏季平均总降水量  
图6多年平均日降水序列  
Fig.6Multi-year averaged daily precipitation series

比（图5c)可见，参照试验区域降水普遍减少；同时，四川一华北一东北沿线降水有显著增强，结合前文中地膜对环流形势的影响不难发现，该区域正是加入地膜后气旋与反气旋交汇、风场增强的区域。此外，考虑地膜效应之后，华南大部分地区降水减少，特别是广东、广西一带减少尤为明显;这与地膜覆盖农田下垫面加剧该区域位势高度正距平、减小水汽输送气流作用密不可分。

# 3.3 不同区域降水变化

根据模拟结果中地膜对不同区域影响结果不同，将全国划分为西北、西南、淮河流域、华南4个气候特征区域，分别讨论地膜覆盖农田下垫面对降水变化的影响。在参照试验区(图6a)明显可见，地膜覆盖农田下垫面模拟降水量始终小于普通农田。这与地膜覆盖农田下垫面向大气的水汽输送减少，导致上升气流中水汽供应不足有关。两种方案的差距自6月底开始拉大，至8月差异值达到最大。与参照试验区域相反的是，西南地区（图6b)的降水呈现增加趋势。相较其他区域，西南区域受参照试验区域影响最大。该区域降水增多主要是由于四川、重庆一带处于低气压控制区，地膜方案使西北区域的气旋性环流与西南的气旋性环流相连，加强了西南至西北的气流辐合。由(图6b)也可以看出，6月份地膜覆盖农田下垫面模拟降水略高于普通农田，7、8月差异突增

此外，地膜覆盖使得淮河流域降水波动幅度增大，在所选时间段内半数以上降水偏多。淮河流域降水主要受副高控制，地膜方案使试验控制区域气压减小，促进了副高向西北方向移动，淮河流域一带受副高推进影响，降水增多。而地膜方案对华南地区降水有削减作用，这是由于地膜下垫面使得东南沿海一带呈反气旋性环流的特征，副高控制时间延长。

# 4小结

本文基于试验观测和现有理论研究，建立了地膜覆盖农田的地一气一水热传输过程模型，提出一种新的地膜覆盖农田下垫面类型并引入区域气候模式 $\mathrm { R e g C M } \ : 4$ 和WRF模式,分别在西北干旱区设置控制区域进行多年夏季气候模拟试验。通过对模拟结果的分析，得到以下结论：

（1）对比地膜覆盖农田下垫面方案与普通农田方案地表参量的模拟情况表明，模式中新引入地膜下垫面方案后，模拟地膜覆盖农田下垫面潜热输送及降水小于普通农田，而感热输送、土壤表层温度、土壤表层含水量均大于普通农田；这与观测及现有理论相符合，说明模型能够对土壤与近地面大气物质、能量交换过程进行较好的表征。对比两种不同的数值模式结果发现，二者较为一致地反映出加入地膜覆盖农田后地表参量的变化规律，模拟结果

可信。

（2）地膜覆盖农田下垫面通过影响局地近地层参量的变化，进而改变环流形势。由多年平均环流形势可见，设置地膜覆盖农田下垫面的试验控制区，对流层下层气压降低，呈低压特征， $5 0 0 \ \mathrm { { h P a } }$ 对流层位势高度升高，气流上升运动受抑制；低层低压推动了副热带高压向西北内陆方向移动。总体而言，参照试验区域的低压与其东南侧高压区交汇，促使西南气流沿四川一华中一华北一东北一线水汽输送增强，而华南地区气流减弱。

（3）通过17a模拟地膜覆盖农田下垫面对我国夏季降水分布的影响可见，加入地膜后，夏季我国四川一华中一华北一东北一线降水普遍增多;这与地膜覆盖农田影响下四川一华中一华北一线西南—南向气流增强从而导致来自孟加拉湾水汽输送加强有关。同时，地膜试验控制区、华南大部分地区降水呈减少趋势，与该区域地膜覆盖农田下垫面影响下正位势高度场距平及风场水汽输送作用减弱有关。将研究区域划分为四个气候特征区域，可见西北地区地膜覆盖农田下垫面的铺设对参照试验区和华南地区降水效应减弱，而对西南地区和淮河流域效应增加。

由于本文RegCM模式所选的参数化方案和WRF模式所选方案不同，算法存在差异，因此模拟降水、感热和潜热等物理量在数值和变化上并非完全一致;此外，两种模式的土壤分层情况不同，考虑到插值到同一土壤层会带来更大误差，因此，在比较土壤温度和湿度时，本文仅比较两种模式模拟的趋势。尽管如此，两种模式对地膜作用的模拟均呈现出相似的变化趋势，这在一定程度上表明地膜覆盖农田模型构建的合理性。此外，由于计算资源的限制,本文采用 $\operatorname { R e g C M }$ 模拟地膜覆盖农田的气候效应时，仅选取了一种使用比较广泛的计算方案；而60km 的模拟分辨率不够细致，因此，数值模拟过程尚有改进的余地。此外，植被、土壤的物理参数在地一气相互作用过程中发挥着重要作用，陆面过程与气候变化的数值模拟研究需要结合遥感、实地观测等多方面的资料。因此，观测范围更广、观测物理量更细致的长期观测试验，对于细化模式的物理参数化方案是必不可少的。这样的观测和数值模拟研究应朝着更加细致详尽描述实际大气运动、物质能量交换的机制方向发展。

# 参考文献(References）：

[1]Chen F,Dudhia J. Coupling an advanced land surface-hydrology model with the Penn State-NCAR MM5 modeling system.Part II: Preliminary model validation[J].Monthly Weather Review,2001, 129(4) :587 -604.   
[2]Sellers PJ,Mintz Y,Sud Y C,et al.A simple biosphere model （SiB）for use within general circulation models[J]. Journal of the Atmospheric Sciences,1986,43(6） :505-531.   
[3]杜冰,左洪超,杨扬,等.3个陆面过程模式对一次暴雨前后的 模拟性能检验与对比[J].干旱区研究,2016,33（1):38－48. [Du Bing,Zuo Hongchao,Yang Yang,et al. Test of simulating effects for three land surface models Noah,SHAW and CLM 4.0: Before and after a rainstorm[J].Arid Zone Research,2016,33 (1):38-48.]   
[4］杨启东.干旱半干旱区两种典型下垫面的陆面过程模拟研究 [D].兰州：兰州大学,2012.[Yang Qidong.Simulation Research of Land Surface Process over Two Typical Underlying Covers in the Arid and Semi-arid Areas〔D]. Lanzhou: Lanzhou University, 2012.]   
[5]申元村.拓展中国绿洲研究,促进干旱区域可持续发展[J].干 旱区研究,2007,24（4）:415-415.[Shen Yuancun.Continuing the oasis study and promoting the sustainable development in arid areas in China[J].Arid Zone Research,2007,24（4）: 415- 415.]   
[6]赵舒曼,左洪超,郭阳,等.WRF 模式不同参数化方案组合对干 旱区一次暴雨模拟的对比分析[J].干旱区研究,2016,33(6)： 1 157-1 166.[Zhao Shuman,Zuo Hongchao,Guo Yang,et al. Simulation on a rainstorm in arid region by different combinations of parameterization schemes of WRF[J].Arid Zone Research, 2016,33(6) :1 157 -1 166.]   
[7］王炳钦,江源,董满宇,等.1961—2010 年北方半干旱区极端降 水时空变化[J].干旱区研究,2016,33（5）:913-920.[Wang Bingqin,Jiang Yuan,Dong Manyu,et al. Spatiotemporal variations of extreme precipitation in the semiarid region in North China during the period of 1961-2010[J].Arid Zone Research,2016,33 (5):913 -920.]   
[8］陈继伟.人类活动对干旱区农田地气相互作用的影响[D].兰 州：兰州大学,2013.[Chen Jiwei.The Impact of Human Activities on Land and Atmosphere Interaction over Cropland in the Arid Area[D].Lanzhou:Lanzhou University,2013.]   
[9］朱德琴,高晓清.陆面过程模式 SSiB 在中国西北典型干旱区 使用性能的检验[J].高原气象,2005,24（6）：872－879.[Zhu Deqin,Gao Xiaoqing.Validation of SSiB model in typical arid region of Northwest China[J].Plateau Meteorology,2005,24（6）： 872 -879.]   
[10］陈伏龙,王怡璇,吴泽斌,等.气候变化和人类活动对干旱区内 陆河径流量的影响;以新疆玛纳斯河流域肯斯瓦特水文站为 例[J].干旱区研究,2015,32（4）:692-697.[Chen Fulong， WangYixuan,Wu Zebin,etal.Impacts of climate change and human activities on runoff of continental river in arid areas:Taking Kensiwate Hydrological Station in Xinjiang Manas River Basin as an example[J].Arid Zone Research,2015,32(4）:692-697.]   
[11]Li T,Grant R F,Flanagan L B. Climate impact on net ecosystem productivity of a semi-arid natural grassland: Modeling and measurement[J].Agricultural and Forest Meteorology,2004,126（1）: 99 - 116.   
[12］王俊,李凤民,宋秋华,等.地膜覆盖对土壤水温和春小麦产量 形成的影响[J].应用生态学报,2003,14（2）：205－210. [Wang Jun,Li Fengmin,Song Qiuhua,etal.Effects of plastic film mulching on soil temperature and moisture and on yield formation of spring wheat[J]. Chinese Journal of Applied Ecology,2003,14 (2):205 -210.]   
[13]Chakraborty D,Nagarajan S,Aggarwal P,et al.Effct of mulching on soil and plant water status,and the growth and yield of wheat (Triticum aestivum L.）in a semi-arid environment[J].Agricultural Water Management,2008,95(12）:1 323-1 334.   
[14]Ham JM,Kluitenberg G J. Modeling the efect of mulch optical properties and mulch-soil contact resistance on soil heating under plasticmulch culture[J].Agricultural and Forest Meteorology, 1994,71(3/4) :403 -424.   
[15]Dahiya R,Ingwersen J,Streck T.The effect of mulching and tillage on the water and temperature regimes of a loess soil; Experimental findings and modeling[J].Soil and Tillage Research,2007,96 (1) :52 -63.   
[16］陈继伟,左洪超.干旱区地膜覆盖农田下垫面反照率的观测研 究[J].干旱区研究,2014,31（3）:397-403.［ChenJiwei,Zuo Hongchao.Albedo of cropland covered with plastic film in an arid area in Northwest China[J].Arid Zone Research,2014,31（3）): 397 -403.]   
[17]Ramakrishna A,Tam H M,Wani SP,et al.Effect of mulch on soil temperature,moisture,weed infestation and yield of groundnut in Northern Vietnam[J].Field CropsResearch,2006,95(2）:115 125.   
[18]Cook HF,Valdes G SB,Lee H C.Mulch effects on rainfall interception,soil physical characteristics and temperature under Zea mays.L[J].Soil and Tillage Research,2006,91(1):227-235.   
[19］陆莎,左洪超,郭阳,等.荒漠下垫面陆面过程模式中重要参数 的修正及模拟效果分析[J].干旱区研究,2017,34（3）：551- 563.[Lu Sha,Zuo Hongchao,Guo Yang,et al. Modification and simulation of key parameters in land surface process in desert underlying surface[J].Arid Zone Research,2017,34（3）:551 563.]   
[20]Yang Q,Zuo H,Xiao X,et al.Modelling the effects of plastic mulch on water,heat and $\mathrm { C O } _ { 2 }$ fluxes over cropland in an arid region[J]. Journal of Hydrology,2012,452/453(4）:102 -118.   
[21]刘辉志,董文杰,符淙斌,等.半干旱地区吉林通榆“干旱化和 有序人类活动”长期观测实验[J].气候与环境研究,2004,9 (2）:378-389.[Liu Huizhi,Dong Wenjie,Fu Congbin,et al.The long-term field experiment on aridification and the ordered human activity in semi-arid areaat Tongyu,Northeast China[J].Climatic and Environmental Research,2004,9(2）:378 -389.]   
[22]温晓霞,韩思明,赵风霞,等.旱作小麦地膜覆盖生态效应研究 [J].中国生态农业学报,2003,11（2）:93-95.[Wen Xiaoxia, Han Siming,Zhao Fengxia,et al. Research on ecological effect of wheat with plastic film in dry land[J].Chinese Journal of Eco-Agriculture,2003,11(2):93-95.]   
[23]Kueppers L M,Snyder M A,Sloan L C.Irrigation cooling effect: Regional climate forcing by land-use change[J].Geophysical Research Letters,2007,34(3):doi:10.1029/2006GL028679.   
[24]SacksWJ,Cook BI,Buenning N,et al.Effects of global irrigation

on the near-surface climate[J].Climate Dynamics,20o9,33（2- 3):159 -175. [25]Puma MJ,Cook BI.Effects of irrigation on global climate during the 2Oth century[J]. Journal of Geophysical Research-Atmospheres,2010,115（D16):751-763.

# Numerical Simulation of Climate Effect in East Asia by Plastic Film Mulching Farmland in Arid Area

ZHAO Shu-man $^ { 1 , 2 }$ ，ZUO Hong-chao’， WEI Xiang-qian1,3， YANG Bin $^ { 1 , 4 }$ ， WU Li-yang'， WANG Shi-xin' (1.Collge of Atmospheric Sciences,Lanzhou University,Lanzhou 73oooo,Gansu,China; 2.State KeyLaboratoryoftmosphericBoundaryLayerPhysicsandAtmosphericChemistry,InstituteofAtmosphericPhysics， Chinese Academy of Sciences,Beijing 100029,China ; 3．China Institute for Radiation Protection,Taiyuan O3ooo6,Shanxi,China ; 4.Unit 63898 of Chinese Peoples' Liberation Army,Jiyuan 459000,Henan,China)

Abstract:Asan effctive way offarming,plastic film mulchingon farmland is widely used inarid and semiarid areas in China.Inorder to studytheclimateefectof plastic film mulchingon farmlandin East Asia,in this research amodel of heat-water transfer process on mulched farmland was developed basedon carrying out the experimental observation and theoretical research and introducing the mulched farmland module into RegCM4 and WRF model to carry out a climate simulation experiment in summer for 17 years.The outputed parameters,such as precipitation,soil moisture content,surface soil temperature,sensible heat fluxand latent heat flux,were compared by RegCM4 model with the experimental observation and theoretical value,and the parameters were verified by the outputtd resultsof WRF model.The result showed that,after mulching plastic film,the regional climate model can beused to exactly describe the characteristics of farmland underlying surface.Further comparison revealed that the potential fieldand wind field could be changed bymulching plastic film through influencing heat and water transfer near surface,and the water vapor transmision wasaffcted,resulting in areduction of precipitation in northwestern and southwestern parts of China,but an increase of precipitation in southwest China and the Huai River Basin.

Key Words:plastic film mulching；RegCM 4.3；WRFV3.6； numerical simulation；climatic efect； Arid Land