# NVST终端仪器消旋平台载荷形变研究

梁昱1,²，李正刚1,³，许骏1,3（1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京100049;3.中国科学院天文大科学研究中心，北京100012)

摘要：研究了 $1 \mathrm { m }$ 新真空太阳望远镜(NewVacuumSolarTelescope，NVST)终端仪器消旋平台上平台的载荷形变情况。利用检测激光光斑在CCD探测器上的位移探测微小的形变。实验时，激光光源固定在稳定区域指向被测区域CCD探测器。通过质心算法计算CCD探测器靶面光斑质心数据，质心的变化量反映测量被测区域的形变量，仅研究重力方向的形变。通过多组实验及ANSYS仿真发现：上平台的3个悬臂边缘位置在旋转至 ${ 8 0 } ^ { \circ } \sim 2 { 0 0 } ^ { \circ }$ 区域出现的正、反转重力方向形变的明显不一致问题很大程度由驱动平面和轴承定位平面不一致及正、反转滚轮组不严格指向转台中心两个因素共同作用引起；3个悬臂中，一个悬臂在多个转动区域形变明显且对载荷敏感，一个悬臂部分区域对载荷敏感，均主要由于其与转台中心连接刚度较差引起。

关键词：消旋平台形变；质心算法； $1 \mathrm { m }$ 新真空太阳望远镜中图分类号：TH741 文献标识码：A 文章编号：1672-7673(2017)04-0511-08

望远镜位置固定的内史密斯(Nasmyth)焦点或库德(Coude)焦点，都存在视场旋转的问题。观测单个点源时，旋转相对较小，但如果观测目标为面源，则要让被测对象在焦面上相对于探测器的位置固定[1]。为抵消像场旋转，通常需要通过硬件或软件方式消旋。目前消旋方法主要有3类：后端仪器平台转动消旋、光学器件消旋及后期图像处理消旋[2-5]。

太阳是距离地球最近的恒星，主导着日地空间关系[6]。作为研究太阳物理不可或缺的科研装置,现役地平式太阳望远镜中，只有 $1 \mathrm { ~ m ~ }$ 太阳望远镜采用平台方式消旋，见表1。我国预研中的中国大型太阳望远镜(Chinese Large Solar Telescope，CLST）、中国巨型太阳望远镜(Chinese Giant Solar Telescope,CGST)则都考虑采用平台方式消旋[6-7]。

表1全球主要太阳望远镜消旋方式[8-14]  
Table 1 The derotator method of mainstream solar telescope   

<html><body><table><tr><td>望远镜</td><td>机架形式</td><td>口径/m</td><td>消旋方式</td><td>望远镜</td><td>机架形式</td><td>口径/m</td><td>消旋方式</td></tr><tr><td>NST</td><td>赤道式</td><td>1.6</td><td>后期数据处理</td><td>McMATH</td><td>赤道式</td><td>2.03</td><td>光学器件消旋</td></tr><tr><td> SST</td><td>地平式</td><td>1</td><td>数据处理消旋</td><td>ATST/预研</td><td>地平式</td><td>4</td><td>平台消旋/16.5m</td></tr><tr><td>NVST</td><td>地平式</td><td>1</td><td>平台消旋/6m</td><td>EST</td><td>地平式</td><td>4</td><td>光学器件消旋</td></tr><tr><td>GREGOR</td><td>地平式</td><td>1.5</td><td>光学器件消旋</td><td>CLST/预研</td><td>地平式</td><td>1.8</td><td>平台消旋/9 m</td></tr><tr><td>THEMIS</td><td>地平式</td><td>0.9</td><td>光学器件消旋</td><td>CGST/预研</td><td>地平式</td><td>8</td><td>待定/三层平台</td></tr></table></body></html>

布局在消旋平台上的后端仪器的精度对成像观测至关重要。目前还未见关于大型太阳望远镜消旋平台形变的相关研究工作。本文采用光源指向探测器，利用检测探测器靶面质心变化量计算被测区域形变量的方法对 $1 \mathrm { m }$ 太阳望远镜消旋平台上平台载荷形变问题进行了研究。该工作不仅有助于对现有仪器的工作环境进行评估，为后续仪器的装调提供有力参考，也可为我国后续研发的大型望远镜的旋转平台积累设计经验。

# 1研究方法

# 1. 1 悬臂及节点约定

$1 \mathrm { ~ m ~ }$ 太阳望远镜的后端仪器布局在消旋平台上，成像通道布局在上平台，见图1。本文坐标系约定： $X$ 轴为重力方向； $Y$ 轴为水平方向（与转台外径相切)； $Z$ 轴为水平方向(径向指向中心）。平台旋转位置约定悬臂1位置为 ${ 0 } ^ { \circ }$ ，2为 $9 0 ^ { \circ }$ ，3为 ${ 1 8 0 } ^ { \circ }$ ，依次类推。

![](images/2ea9da95483915eac27396780809f8823276e82285a5a292834ccd3775ca03cc.jpg)  
图1（a）上平台悬臂位置示意；（b）上平台实验位置示意Fig.1（a）Position of cantilevers on upper platform；（b）Experiment position on derotator platform

# 1. 2 研究内容

布局在 $1 \mathrm { m }$ 太阳望远镜上平台悬臂4的自适应光学系统的承载约为2000千克，且自适应光学系统工况稳定。这个承载量已经超出普通光路光学器件的总重，对于悬臂的承载本文不做进一步讨论。作为太阳望远镜的光学消旋平台，相对于承载，其动态稳定性更为关键，故本文仅研究上平台载荷形变的稳定性。

具体内容为： $X$ 轴平台静止时，上平台3个悬臂不同位置加载的静态质心数据；平台转动时3个悬臂在多工况下正、反转的动态质心数据，见表2。 $Y$ 轴、 $Z$ 轴未研究，理由如下：

(1)Y轴刚度较好，冲击载荷下仅 $8 ~ { \mu \mathrm { m } }$ 的响应，见图1（b）， $Y$ 轴形变对终端仪器的影响可忽略;

$( 2 ) Z$ 轴为光路非敏感方向，只影响光轴方向焦面位置，主要受离心力影响。 $1 \mathrm { ~ m ~ }$ 太阳望远镜所处位置的像场最大旋转速度为 $1 4 4 6 ^ { \prime \prime } / \mathrm { s } ^ { [ 1 5 ] }$ ，仿真中采用转速 $1 5 7 0 \mathrm { ^ { \prime } / s }$ 分析离心力水平方向形变为$0 . 1 2 \mathrm { n m }$ ，对像质影响不大。 $1 \mathrm { m }$ 太阳望远镜一天内的正常调节量在 $1 \mathrm { m m }$ 左右， $Z$ 轴形变可忽略。

表2实验采集内容  
Table 2 Contents of experiment data   

<html><body><table><tr><td></td><td>数据类型</td><td>采集内容</td><td>目的</td><td>备注</td></tr><tr><td rowspan="5">上平台</td><td>静态数据</td><td>不同角度质心</td><td>分析离散位置的质心</td><td>每隔30°采集一组数据</td></tr><tr><td></td><td>不同角度加载质心</td><td>分析离散位置质心的载荷影响</td><td></td></tr><tr><td>动态数据</td><td>正、反转质心</td><td>分析连续变化质心数据</td><td>多种工况的形变</td></tr><tr><td></td><td>正转、快速复位质心</td><td>分析速度影响</td><td></td></tr><tr><td></td><td>正、反转加载质心</td><td>分析载荷影响</td><td></td></tr><tr><td></td><td></td><td>正、反转无拖线质心</td><td>分析拖线影响</td><td></td></tr></table></body></html>

# 1.3形变采集原理

利用检测激光光斑在CCD探测器上的位移探测大型结构形变，通过探测器靶面光斑质心变化量计算被测区域形变量。由于悬臂4被AO占用，本文只采集悬臂1\~3的数据，光源固定在转台中心，探测器固定在距中心 $2 . 5 \mathrm { ~ m ~ }$ 的边缘被测区。增加减光片减小光强，防止CCD损坏。

实验仪器如下：

激光器：MRL-III- $6 7 1 { - } 5 0 ~ \mathrm { m W } /$ 长春新产业光电技术有限公司CCD：pco.4000 分辨率： $2 6 7 2 \times 4 0 0 8 / \mathrm { p c o }$ 减光片：UPAMOD4/成都超纯科技有限公司

# 1.4采集方法的可行性

考虑光源稳定性等背景噪声影响，采集平台静止 $4 0 \mathrm { m s }$ 和 $1 0 0 \mathrm { m s }$ 不同曝光时间质心变化的数据，曝光影响在一个像素( ${ \bf \{ 9 ~ \mu m } $ )左右，见表3。实际采集均采用 $1 0 0 ~ \mathrm { { m s } }$ 曝光，形变数据标准差

表3实验用激光器光束稳定性  
Table 3Stability of laser beam for experiment   

<html><body><table><tr><td rowspan="2">X轴/重力方向</td><td rowspan="2">/μm</td><td rowspan="2">悬臂1</td><td rowspan="2">悬臂2</td><td rowspan="2">悬臂3 /μm</td></tr><tr><td>/μm</td></tr><tr><td>曝光差值 40 ms/100 ms</td><td></td><td>1.59</td><td>2.86</td><td>11. 5</td></tr><tr><td>各数据标准差</td><td>40 ms</td><td>6.228</td><td>0.813 6</td><td>8.564 4</td></tr><tr><td>/STD</td><td>100 ms</td><td>4.3191</td><td>0.988 2</td><td>6.243 3</td></tr></table></body></html>

小于 $7 ~ \mu \mathrm { m }$ ，符合信噪比要求。为验证实验方法的灵敏性，人为推动消旋平台悬臂2的 $X$ 轴重力方向和 $Y$ 轴水平方向，检验悬臂对于冲击载荷的敏感性，信号灵敏性符合要求。 $X$ 轴的响应远大于 $Y$ 轴响应，见图2，其中，纵轴表示质心相对变化量，后文类似。

![](images/99f247640f3d2f44f3fefa94ea9ceb66041937a8aef7ab32ca0fa04f56c0566c.jpg)  
图2（a）手推重力方向 $X$ 轴响应/峰值 $2 0 0 ~ { \mu \mathrm { m } }$ ；（b）手推水平方向 $Y$ 轴响应/峰值 $8 ~ { \mu \mathrm { m } }$ Fig.2（a） The response of $X$ axis when push at $X$ axis/Peak value : $2 0 0 \mu \mathrm { m }$ ：（b）The response of $Y$ axis when push at $Y$ axis/Peak value: ${ 8 \mu \mathrm { m } }$

# 1. 5 数据预处理

采集的文件是FITS 文件，分辨率为 $2 6 7 2 \times 4 0 0 8$ 。实际激光光斑较小且质心位置的变化不大。为提高计算效率，截取 $1 0 0 0 \times 1 0 0 0$ 像元进行处理；为提高信噪比，进行了噪声滤波，具体参数根据每组FITS文件中的光斑位置、背景噪声确定，最后计算光斑质心数据。

# 2数据分析

3 个悬臂实验内容相同：(1)不同角度的质心静态数据；(2)综合考虑 $1 \mathrm { m }$ 太阳望远镜的消旋平台的具体工况，为分析速度、拖线、载荷的影响，采集了多个工况3个悬臂正、反转的动态数据。另外，为分析驱动力影响，模拟悬臂1在整个旋转过程中的质心变化趋势进行力学仿真，讨论了悬臂${ 8 0 } ^ { \circ } \sim 2 { 0 0 } ^ { \circ }$ 区域出现明显的正、反转形变不一致问题。

# 2.1静态数据

3个悬臂每隔 ${ 3 0 } ^ { \circ }$ 采集一组悬臂静态形变数据取均值绘图，除悬臂3的 ${ 3 0 } ^ { \circ }$ 、 ${ 1 2 0 } ^ { \circ }$ 两组数据，其余数据加载前后悬臂形变变化趋势符合良好，见图3、表4。对悬臂1的工况，利用ANSYS 进行力学仿真，悬臂边缘加载 $7 0 \mathrm { k g }$ 载荷，加载形变为 $2 8 8 ~ { \mu \mathrm { m } }$ ，与实际测量 $3 1 5 ~ { \mu \mathrm { m } }$ 相近。

悬臂1-X轴各个角度均值数据加载对比 悬臂2-X轴各个角度均值数据加载对比 悬臂3-X轴各个角度均值数据加载对比500 +加载前 400 +加载前 400 +加载前加载后 30 加载后 00 加载后200 200 200质 100 质 质0 上 1 0 上 J 00 50 100 150 200 0 50 100 150 200 0 50 100 150 200光谱仪对应角度/ 光谱仪对应角度/ 光谱仪对应角度/(a) (b) (c）

表43个悬臂在不同角度加载质心变化均值  
Table 4The mean data of centroid variation in each cantilever when load and offload   

<html><body><table><tr><td>变化方向</td><td>悬臂1/μm</td><td>悬臂2/μm</td><td>悬臂3/μm</td><td>悬臂3 排除 30°、120°</td></tr><tr><td>X轴</td><td>315</td><td>216</td><td>191. 46</td><td>246. 744 2 μm</td></tr></table></body></html>

注：加载为 $7 0 \mathrm { k g }$ 载荷添加在悬臂边缘。

# 2.2 动态数据

$1 \mathrm { m }$ 太阳望远镜光谱平台仅可实现 ${ \boldsymbol { 0 } } ^ { \circ } \sim 2 { 1 0 } ^ { \circ }$ 范围的旋转。实际可叠加3个悬臂工况反应整个平台旋转过程中的工况。将悬臂2的质心数据第1个点与悬臂1的 $9 0 ^ { \circ }$ 坐标的质心数据点叠加，悬臂3第1个质心数据与悬臂1的 ${ 1 8 0 } ^ { \circ }$ 点叠加。如图4（a)。横轴为平台旋转位置，纵轴为重力方向质心位置。3个悬臂独立实验，纵轴数据根据 $9 0 ^ { \circ }$ 、 ${ 1 8 0 } ^ { \circ }$ 悬臂交接处数据叠加到一起，表示质心变化相对量。实际采集过程中手动控制采集及转台转动，非严格在 $9 0 ^ { \circ }$ ： ${ 1 8 0 } ^ { \circ }$ 叠加。

![](images/eb6b6477d8e47273b8660baf821bcb99a67522c24b050177af1e6f0ed283ad46.jpg)  
图33个悬臂不同角度及加载CCD光斑质心数据Fig.3The centroid data when ofload and on load of each cantilever in different angles  
图4（a）正转：静态、动态数据叠加（上部为加载数据)；（b）正、反转数据对比分析Fig.4（a） Forward data：Superposition of static data and dynamic data（upper data represent on load）;(b）Comparative analysis of forward and reverse rotating of platform

注：图4(a)中， $^ +$ 为悬臂1正转数据； $>$ 为悬臂2正转数据； $\blacktriangle$ 为悬臂3正转数据；图4(b)中，+、>、 $\blacktriangle$ 表示与图4(a)一致，0为悬臂1的反转数据； $<$ 为悬臂2反转数据； $\times$ 为悬臂3反转数据。

考虑到影响平台形变的因素主要含驱动力、平台转速、平台拖线（目前消旋平台转动时线缆会拖拽移动，有一定阻力）、载荷等主要因素。分别采集3个悬臂在消旋平台旋转过程中正、反转；正转、快速复位；正、反转排除拖线干扰；含载荷正、反转的动态数据。证实除载荷外，拖线及速度对实验结果几乎无影响，见图5。

![](images/9d6dded289477bd9e256765895fc07e398464866b6281726dcca7f61416551b0.jpg)  
Fig.5Load effect of derotator platform when forward and reverse (Upper represent on load)

注： $^ +$ 为悬臂1正转数据； $>$ 为悬臂2正转数据； $\blacktriangle$ 为悬臂3正转数据；0为悬臂1的反转数据;  
<为悬臂2反转数据； $\times$ 为悬臂3反转数据。

# 2.3驱动力影响的仿真数据

$1 \mathrm { m }$ 太阳望远镜的平台转动通过布局在悬臂2、3之间的滚轮1及布局在悬臂3、4之间的滚轮2驱动，见图6(a)。由于装配间隙、环境温度等因素，滚轮存在径向指向圆心或远离圆心的分力。如图6（b），望远镜上平台驱动面和定位面不共面，两个平面的距离即提供了作用力臂，滚轮的驱动力存在径向分力，力和力臂共同作用产生绕水平轴的扭转力矩，该力矩最终导致悬臂重力方向的形变。

![](images/879df1e1b45d2e6f9ba01571cb032f1dbe3c211aa47c5ead8a8eec98f9c5d337.jpg)  
图5正反转载荷影响对比(上部为加载)  
图6（a）实际滚轮径向分力示意图；（b）上平台定位及驱动面示意图 Fig.6（a）Schematic diagram of the roller radial component of drive force ; (b）Schematic diagram of fix position and driving position

考虑悬臂2实际工况布局有大量仪器，其质量、位置布局参数不详，无法进行可靠仿真，悬臂 3质心不稳定（见图4、5），故模拟悬臂1的工况进行力学仿真：设定上平台静止，通过滚轮位置移动一定的角度模拟平台转到相同角度的状态。如图7（a），滚轮实际布局位置为 ${ 0 } ^ { \circ }$ 的状态。两对滚轮指向或远离圆心的径向分力可以两两组合为4种情况，仿真4种情况的悬臂1质心变化趋势见图7（b)。

由图7可知，当正转滚轮1远离，滚轮2指向圆心；反转滚轮1指向，滚轮2远离圆心时，悬臂1实验数据中 ${ 8 0 } ^ { \circ } \sim 2 { 0 0 } ^ { \circ }$ 区域的正、反转形变不一致和仿真数据变化趋势较吻合，见图8， ${ \boldsymbol { 0 } } ^ { \circ } \sim { 8 \boldsymbol { 0 } } ^ { \circ }$ 区域由于多种因素作用此处不做讨论。推断如下： ${ 8 0 } ^ { \circ } \sim 2 { 0 0 } ^ { \circ }$ 区域的正、反转形变不一致主要由两方面引起：（1)驱动力与轴承固定平面不一致，驱动力的径向分量产生额外的扭转力矩，该力矩产生的应力导致悬臂的应变变形；(2)实际正、反转的滚轮不同工作状态径向分力的方向相反(指向或远离转台中心），即产生形变的正、反转不一致。

![](images/0c4e03d4e4a1d19a9db48a123951e70ff02dc93fa897ee7f1e0c6f2f7d683520.jpg)  
Fig.7（a）Simulation of platform rotation with the roller positon change；（b）Simulation result

注：图7(b)米表示两个滚轮径向力指向远离圆心； $\bigcirc$ 表示两个滚轮径向力指向圆心； $\blacktriangleright$ 表示滚轮1远离，滚轮2指向圆心；表示滚轮1指向，滚轮2远离圆心。

![](images/385f35436a833736567fc52496aecbbde22f11296802a7a59ea4c105dae8677e.jpg)  
图7（a）滚轮位置变化模拟平台转动；（b）仿真结果  
图8（a）实际采集的质心变化趋势；（b）ANSYS仿真驱动力影响的质心变化趋势 Fig.8（a）Centroid variation trend collected by experiment；（b）Centroid variation trend affected by drive collected by ANSYS simulation 注：图8(a)中“ $^ +$ ”为悬臂1正转数据；“0”为悬臂1的反转动态数据； 图8(b)中 $\blacktriangleright$ 表示滚轮1远离，?表示滚轮1指向。

# 2.4上平台形变数据综合分析

(1)图3、表4可知，除悬臂1的 ${ 0 } ^ { \circ } \sim 1 { 0 } { 0 } ^ { \circ }$ 、悬臂3的 $2 { 1 0 } ^ { \circ }$ 、 ${ 3 0 0 } ^ { \circ }$ 附近区域，3个悬臂加载前后变化趋势符合良好。由图4(a)可知，除悬臂1加载后 ${ 0 } ^ { \circ } \sim 1 { 0 } 0 ^ { \circ }$ 区域静、动态数据符合较差，平台旋转大部分区域3个悬臂静态、动态质心数据及变化趋势叠加良好，图8(a)、（b)对比实验与仿真亦在${ \boldsymbol { 0 } } ^ { \circ } \sim { 8 \boldsymbol { 0 } } ^ { \circ }$ 区域出现偏差，推断载荷、驱动力等因素共同作用影响了悬臂1的 ${ 0 } ^ { \circ } \sim 1 { 0 } 0 ^ { \circ }$ 区域的应力应变,悬臂1对载荷敏感。悬臂3质心变化峰值 $2 5 0 ~ \mu \mathrm { m }$ ，在一定区域出现了一定的冲击载荷， $1 9 5 ^ { \circ } \sim 2 1 5 ^ { \circ }$ ，$2 8 5 ^ { \circ } \sim 3 0 5 ^ { \circ }$ 区域变化趋势异常在多组实验中重复出现， $3 0 0 ^ { \circ } \sim 3 3 0 ^ { \circ }$ 质心变化加载后消失，考虑悬臂3相对悬臂1、2质心变化较大，存在冲击载荷且受重力影响，可以推测其与转台连接刚度较差，对重力载荷敏感，对于悬臂3在多个区间的质心异常问题，排除驱动力、拖线、速度等因素，本文推断原因为悬臂3与转台中心连接刚度较差，不再做进一步讨论。

(2)由表3、图4(a）、图5可知，3个悬臂加载 $7 0 \mathrm { k g }$ 载荷存在 $2 0 0 { \sim } 3 0 0 ~ \mu \mathrm { m }$ 的形变。载荷对于质心变化有一定影响，但与悬臂刚度条件密切相关，悬臂1\~3对于载荷的敏感性不同，加载变化量悬臂 $1 >$ $3 > 2$ ，所以出现3个悬臂未加载叠加性较好，加载后叠加混乱的现象(纵轴是质心变化的相对量)。3个悬臂上实际布局的仪器等载荷 $2 > 3 > 1$ ，可认为是含预应力的载荷形变，刚度 $2 > 3 > 1$ ，与实验一致。综合考虑3个悬臂稳定性、刚度、载荷敏感性等因素，上平台仪器布局建议优先悬臂2，其次1、3。

(3)由图8可知，对于重复出现的悬臂在 ${ 8 0 } ^ { \circ } \sim 2 { 0 0 } ^ { \circ }$ 区域正、反转质心不一致问题。通过多组实验排除拖线、速度等其他因素影响，载荷会有一定影响，但相对较小。通过ANSYS 仿真悬臂1的工况推断：悬臂在 ${ 8 0 } ^ { \circ } \sim 2 { 0 0 } ^ { \circ }$ 区域正、反转质心不一致问题很大程度由驱动平面和轴承定位平面不一致及正、反转滚轮驱动力的径向分力方向相反共同作用引起。

# 3总结

上平台是 $1 \mathrm { m }$ 太阳望远镜光学成像通道的布局位置，对于高分辨成像极为重要。例如，望远镜的6563通道 $2 5 0 ~ { \mu \mathrm { m } }$ 的形变相当于CCD靶面上接近30个像素的漂移，极大影响成像质量。本文通过搭建激光光源指向探测器的简易光路，采集了望远镜消旋平台多个工况的形变数据，发现上平台3个悬臂在转台 ${ 8 0 } ^ { \circ } \sim 2 { 0 0 } ^ { \circ }$ 区域明显出现峰值 $1 1 0 \mu \mathrm { m }$ 的形变正、反转的不一致；悬臂3对于载荷敏感，消旋过程中出现峰值 $2 5 0 ~ \mu \mathrm { m }$ 左右的形变，载荷对悬臂1的 ${ 0 } ^ { \circ } \sim 1 { 0 } 0 ^ { \circ }$ 区域有一定的影响。通过多组实验及ANSYS 仿真，分析定位了产生上平台正、反转形变不一致，悬臂3的工况较差，悬臂1连接刚度差等问题的主要原因，为后续的仪器装调及平台改进工作提供了有力参考。

# 参考文献：

[1] 谭徽松，李银柱，金振宇.实测天体物理［M]．北京：国防工业出版社，2014：22-30.   
[2] Goode P R，Denker C J,Didkovsky L I，et al.1.6m Solar Telescope in Big Bear-THE NST [J].Journal of the Korean Astronomical Society，2003，36：125-133.   
[3] Scharmer G B，Bjelksjo K,Korhonen T K,et al. The 1-meter Swedish solar telescope [C]// Keil SL，Avakyan S V. Innovative Telescopes and Instrumentation for Solar Astrophysics : Proceedings of SPIE.2003：341-350.   
[4] Schmidt W，Luhe O V D，Volkmer R，et al.The 1.5 meter solar telescope GREGOR[J]. Astronomische Nachrichten，2012，333(9）:796-809.   
[5] Sánchez-Capuchino J,Colladosl M，Soltau D，et al. Current concept for the $4 \mathrm m$ European Solar Telescope（EST） optical design ［C]// International Optical Design Conference:Proceedings of SPIE.2010.   
[6] 刘忠，邓元勇，季海生，等.中国地基大太阳望远镜［J].中国科学：物理学力学 天文学， 2012，42(12):1282-1291. Liu Zhong，Deng Yuanyong，Ji Haisheng，et al.Ground-based giant solar telescope of China [J]. Scientia Sinica:Physica，Mechanica & Astronomica，2012，42(12）:1282-1291.   
[7] Rao Changhui,Gu Naiting，Zhu Lei,et al.1.8-m solar telescope in China:Chinese Large Solar Telescope [C]// Journal of Astronomical Telescopes， Instruments，and Systems:Proceedings of SPIE. 2015.   
[8] de la Cruz Rodriguez J,Lofdahl M G，Suterlin P，et al. CRISPRED:a data pipeline for the CRISP imaging spectropolarimeter [J]. Astronomy and Astrophysics，2015，573(3） : 1-13.   
[9] Volkmer R，Eisentrager P，Emde P，et al. Mechanical design of the solar telescope GREGOR [J].Astronomische Nachrichten，2012，333(9）:816-822.   
[10] Arnaud J，Mein P，Rayrole J. The solar telescope THEMIS[J]. Vistas in Astronomy，1985, 28: 567-569.   
[11] Pierce A K. The McMath solar telescope of Kitt Peak National Observatory ［J]. Applied Optics，1964，3(3):1337-1345.   
[12] McMullina JP，Rimmelea T R，Keil S L，et al. The Advanced Technology Solar Telescope: design and early construction [C] // Ground-based and Airborne Telescopes IV: Proceedings of SPIE.2012.   
[13] Sanquirce R，Murga G,G6mez A，et al. European Solar Telescope（EST） transfer optics [C] //Ground-based and Airborne Telescopes III:Proceedings of SPIE.2010.   
[14] Colladosl M，Bettonvil F，Cavaller L，et al. European solar telescope:progress status [J]. Astronomische Nachrichten，2010,331(6):615-619.   
[15] 柳光乾，付玉，程向明. $1 \mathrm { ~ m ~ }$ 太阳望远镜光谱仪像旋转及消旋控制［J].天文研究与技术 -国家天文台台刊，2012，9(1)：86-92. Liu Guangqian，Fu Yu, Chen Xiangming. Image-field rotation and control of counter rotation for the spectrograph of the 1m solar telescope of the Yunnan Observatory ［J]．Astronomical Research & Technology———Publications of National Astronomical Observatories of China，2012, 9(1) : 86-92.

# The Research of Deformation on Load about the Terminal Instruments Derotator Platform of NVST

Liang Yu $^ { 1 , 2 }$ ， Li Zhenggang g， ， Xu Jun $^ { 1 , 3 }$ (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 65o0l1,China,Email; yliang@ynao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China; 3.Center for Astronomical Mega-Science,Chinese Academy of Sciences，Beijing 1Ooo12,China)

Abstract：The deformation on load about the terminal instruments derotator platform of NVST is researched.When the upper platform is measured,the Laser light source is placedon thecenter of the platform and pointed to the CCD camera which is placed on the edge of the cantilever in the periphery platform.The centroid of the spot on the CCD target is computed using the centroid algorithm，whose variation presents the deformation.The deformation of gravity direction is researched.The direction of gravity is taken as X axis and the horizontal direction is taken as Yaxis which is only for reference.Through multiple sets of experiments and the simulation by ANSYS,it is foundthat thecentroid data of allcantilevers is obviously inconsistent when the derotator platform forward and reverse inthe range of 8O-20O degree，which is casued by the inconsistency of the drive plane and the positioning plane，and the roller group is not strictly pointing towardsthe center:One of thecantilevers is sensitiveto the load and its rigidity is worse than others，another cantilever is sensitive to the load in some areas，while both have poor stiffness of the connection with the central turntable.

Key words:Deformation of the derotator platform；Centroid algorithm；NVST