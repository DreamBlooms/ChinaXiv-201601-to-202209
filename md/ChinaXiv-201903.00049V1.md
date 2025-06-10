# 基于永磁体温度场的海流永磁发电机的可靠性分析

![](images/8f8b01ea5ced5d11e6b4508c37471c7aeae99791355686a7d84a9fa64dfdd94a.jpg)

陈艳羚　汤天浩　谢　卫（上海海事大学电气传动与控制研究所 上海 201306)

陈艳羚  女 1992年生，硕士，研究方向为电力电子与电气传动。

摘要：海流发电机在海洋环境下工作，相比于风力发电机，其工作环境更恶劣，例如海水腐蚀、密封问题等，一旦海流发电机发生故障，吊装维修十分困难且成本很高，所以必须对其进行可靠性分析。本文通过建立电机可靠性模型，采用元器件应力分析法对电机进行可靠性预计，考虑到永磁体失效是永磁电机的特有故障，且永磁体高温下容易发生不可逆失磁，故对电机进行磁－热耦合仿真，并分析电机尺寸参数对永磁体温度及电机寿命的影响。

关键词：海流发电机 可靠性预计磁－热耦合仿真中图分类号：TM313

# Reliability Analysis of Marine Current Power Permanent Magnet Generator Based on Temperature Field of the Permanent Magnet

![](images/8f49bd34a6b4ffb5feab03e688bf440af2050ace6cc84b5042c5667513cb042a.jpg)

Chen YanlingTang Tianhao Xie Wei (Institute of electrical drive and control, Shanghai Maritime University Shanghai201306China ）

汤天浩男 1955年生，博士，教授、博士生导师。IEEE Senior Member。研究方向为新能源电能变换、电机与控制等。

Abstract: Marine current power generator works under the current, so its working environment is worse than wind power generator, such as sea water corrosion, sealing problems etc.,once the marine current power generator breaks down, lifting maintenance is difficult and the cost is very high,so it is necessary to analyze the reliability of the marine current power generator. Reliability model of the generator is established and parts stress analysis is used to predict its reliability. Considering the permanent magnet failure is the specific failure of permanent magnet generator and the irreversible demagnetization of permanent magnet occurs easily under high temperature, the magnetic-thermal coupling simulation for the generator is conducted and the effect of size parameters on the temperature of the permanent magnet and the life of the generator is analyzed.

Keywords: Marine current power generator, reliability prediction, magnetic-thermal coupling simulation

# 1 引言

海洋能作为可再生能源，具有可靠、稳定、对环境污染小等优点，日益受到国内外的重视。利用海流进行发电与风力发电相似，但具有更高的能量密度。然而，由于海流发电机要考虑更多的由海流环境条件而引起的问题，例如海水腐蚀及海洋生物附着现象、密封性、桨叶的气蚀损伤等，一旦海流发电机发生故障，维修困难且成本很高，所以必须对海流发电机进行可靠性分析，来降低电机投入使用后的故障率，减小昂贵的维修成本，并寻求延长电机使用寿命的途径。

海流发电机大多采用永磁电机。永磁体退磁是永磁电机的特有故障，而且永磁体在高温环境下容易发生不可逆退磁。电机在机电能量转换过程中所产生的损耗最终绝大部分变成热量[1]，造成电机温度上升，故本文对电机进行磁－热耦合仿真，并观察电机尺寸参数（定子槽宽、气隙长度及永磁体宽度）对永磁体温度及电机寿命的影响。

# 2 海流永磁发电机的可靠性建模及预计

可靠性模型是对系统及其组成单元之间的可靠性/故障逻辑关系的描述，可利用模型进行定量分配和预计，发现设计中的薄弱环节，以改进设计。

海流永磁发电机选择的结构为旋转磁极式（永磁体在转子上)，径向式磁路结构（永磁体直接面对气隙，漏磁小，易于实现对永磁体的冷却)。为了建立永磁电机的可靠性模型，就必须了解电机所有主要的功能单元，根据国军标《GJB299C—2006电子设备可靠性预计手册》[2]及美军标《MilitaryHandbook-Electronic Reliability Design Handbook》[3],可以查到元器件及组件的失效模式及其频数比，见表1。

表1元器件及组件的失效模式及其频数比  
Tab.1Failure mode distribution of parts   

<html><body><table><tr><td>元器件或部件名称</td><td>失效模式</td><td>比例(%)</td></tr><tr><td rowspan="3">同步电机</td><td>线圈故障</td><td>45</td></tr><tr><td>轴承故障</td><td>33</td></tr><tr><td>电刷故障</td><td>22</td></tr></table></body></html>

根据表1，可以确定电机的可靠性模型中包括绕组和轴承两个子单元。另外永磁体失磁是分析永磁电机可靠性中不可忽略的故障，故将永磁体也作为电机可靠性模型的一个单元，且建模采用的是串

联模型，综上所述，可以得到电机的可靠性模型如图1所示。

![](images/f34060c0482839b81efd32466192bdf5025f3b73d86298a7bbebaa266a467dc5.jpg)  
图1电机可靠性模型  
Fig.1Reliability model of the generator

同时采用元器件应力分析法对电机进行可靠性预计，根据国军标，可以查到绕组和永磁体的失效率计算公式，分别为

$$
\lambda _ { \mathrm { w i n d i n g } } = \lambda _ { \mathrm { b } } \pi _ { \mathrm { E } } \pi _ { \mathrm { Q } } \pi _ { \mathrm { K } } \pi _ { \mathrm { C } }
$$

$$
\begin{array} { r } { \lambda _ { \mathrm { P M } } = \lambda _ { \mathrm { b } } \pi _ { \mathrm { E } } \pi _ { \mathrm { Q } } } \end{array}
$$

式中， $\lambda _ { \mathrm { b } }$ 为基本失效率， $1 0 ^ { - 6 } / \mathrm { h }$ $\pi _ { \mathrm { E } }$ 为环境系数;  
$\pi _ { \mathrm { Q } }$ 为质量系数； $\pi _ { \mathrm { K } }$ 为种类系数； $\pi _ { \mathrm { { C } } }$ 为结构系数。

根据 $\mathrm { N P R D ^ { [ 4 ] } }$ (Non-electronic Parts ReliabilityData）《非电子部件可靠性数据》标准手册，可以直接查到一些机械部件的失效率，包括轴和轴承，轴的失效率为 $\lambda _ { \mathrm { a x i e } } = 7 . 8 2 8 ~ 0 \times 1 0 ^ { - 6 } / \mathrm { h }$ ，轴承的失效率为$\lambda _ { \mathrm { { b e a r i n g } } } = 3 . 1 1 1 4 \times 1 0 ^ { - 6 } / \mathrm { { h } } _ { \odot }$ 。

假设每个部件的寿命分布服从指数分布，电机运行 $1 ~ 0 0 0 \mathrm { h }$ 的可靠度为

$$
\lambda _ { \mathrm { s } } = \sum _ { i = 1 } ^ { 4 } \lambda _ { i }
$$

$$
R _ { \mathrm { s } } ( 1 0 0 0 ) = \mathrm { e } ^ { - \lambda _ { \mathrm { s } } t } = \mathrm { e } ^ { - \lambda _ { \mathrm { s } } \times 1 0 0 0 } \approx 0 . 9 0 6 5
$$

电机的平均故障间隔时间[5]（MTBF）为

$$
\mathrm { M T B F } = { \frac { 1 } { \lambda _ { \mathrm { { s } } } } } \approx 1 0 1 9 0 \mathrm { { h } } \approx 1 . 2 { \mathrm { { \# } } }
$$

这就是说，当电机投入使用后，预测1.2年后电机可能会出现故障，所以有必要在电机使用第一年之后停止使用，对其进行预防性维修，这样可以延长其偶然故障期，延长它的使用寿命。

# 3海流发电机中永磁体的故障物理分析及其温度场仿真

由于永磁体是海流发电机可靠性模型的重要组成之一，它会影响到电机的可靠度和使用寿命，且永磁体退磁是永磁电机的特有故障，因此有必要重点对永磁体进行失效分析，为了进一步分析永磁体的失效机理，本文选择从故障物理（也称为可靠性物理或失效物理）的角度去分析。

故障物理是专门研究产品故障机理的科学，以产品故障为核心，关心产品的故障机理或故障的根本原因，以物理、化学分析为基础，强调对故障的物理、化学过程的定量分析和描述[。图2主要概括了永磁体的失效机理。

![](images/8ee050bbb5e712596f5cff7100819a7075b5c3b087cb98054650eedd3de00282.jpg)  
图2永磁体的失效机理

本文选择从温度的角度去分析永磁体的退磁，由于钕铁硼的性能对温度有很高的依赖性，温度过高容易发生不可逆失磁，所以本文将建立永磁体的温度模型，对其进行温度场仿真，将损耗作为输入条件放入温度模型中。首先使用Maxwell对电机进行损耗仿真，将得到的损耗作为温度模型的热源，再使用AnsysWorkbench软件对海流永磁发电机进行磁－热耦合仿真，这样有限元模型和热模型可以互取损耗和温度量值，实现永磁体动态的退磁分析。

确定一下海流发电机的主要技术指标有：额定功率 $P _ { \mathrm { { N } } } = 1 \mathrm { { M W } }$ ；相数 $m = 3$ ；额定电压 $U _ { \mathrm { N } } = 6 9 0 \mathrm { V }$ 额定转速 $n = 1 2 \mathrm { r / m i n }$ 。

另外电机的主要尺寸为：定子内径 $D _ { i 1 } =$ $5 . 0 5 2 \mathrm { m }$ ；定子有效长度 $L _ { \mathrm { e f f } } = 0 . 6 2 4 ~ 3 \mathrm { m }$ 。

先对电机进行损耗仿真，电机损耗主要包括定子铁耗和铜耗，本文还考虑了永磁体的涡流损耗，仿真结果如图3所示。

之后进行温度场仿真，在温度场仿真过程中需要计算电机的对流换热系数，其中定子端面与电机内部空气之间的对流换热系数[为

$$
h _ { 1 } = \frac { 1 + 0 . 2 5 \nu } { 0 . 0 4 5 }
$$

转子端面与电机内部空气之间的对流换热系数[为

![](images/49e1e53bc3d1c2b1ddfbbe6c74db94cf6b23f7ee1bc59e703cf1ea044779799d.jpg)  
Fig.2Failure mechanism of permanent magnet   
Fig.3Loss contours of iron loss，copper loss and eddy current loss of permanent magnet

$$
h _ { 2 } = 2 8 \Big ( 1 + \sqrt { 0 . 4 5 \nu } \Big )
$$

式中， $\mathbf { \sigma } _ { \nu }$ 为空气的运动粘度。

对于海流发电机的工作环境温度，英国MCT公司已经建立了单桩固定支撑技术，并且认为是当前支撑海流发电机的最佳选择，但考虑到安装时起重的驳船以及叶片的直径大小，一般所选择海域的深度为 $2 0 \sim 4 0 \mathrm { m } ^ { \left[ 6 \right] }$ 。根据MCT公司的结论，将海流发电机放在海下 $2 0 \sim 4 0 \mathrm { m }$ ，在此范围的海水温度大致为 $1 5 \mathrm { { ^ circ C } }$ [10]，电机温度场仿真的环境温度设置为 $1 5 \mathrm { { ^ circ C } }$ ，仿真结果如图4、图5所示。

![](images/ee109dcb0e1c163712a9d865b56ba3fc6e952cc716c91c8b7a20f4ec119f02ec.jpg)  
图4海流发电机的温度云图及温度曲线 Fig.4Temperature contour and curve of the marine current power generator

![](images/5b04ed8c38316e0af1c3f57e6d74d82579de4bda9dbe233ecd1dc0a9c2f29981.jpg)  
Fig.5Temperature contour and curve of the permanent magnet

![](images/abc2cba56db39831f8ea14a35c54b45dce3da64240a51a0683459dd57c45598a.jpg)  
图5永磁体的温度云图及温度曲线

从整机的温度云图可以发现，绕组的温度最高，然后依次向周围散发热量。由于铜耗是电机的主要损耗，所以绕组是电机中温度最高的部分。

温度曲线中上面那条曲线代表的是电机的最高温度，下面那条曲线代表的是电机的最低温度。从整机的温度曲线可以发现，在500s的时候温度已经达到稳定，即电机的最高温度。因为永磁体的温度不会超过电机的最高温度，本文选择的永磁体钕铁硼，其稳态温度远远低于它的居里温度，所以永磁体不会发生不可逆退磁，可以正常工作。

# 4电机尺寸参数对永磁体温度的影响

电机温度过高会引起永磁体失磁，所以电机运行时需要观察永磁体的温度变化。本文将考虑电机尺寸参数（定子槽宽、气隙长度及永磁体宽度）是否会对永磁体的温度造成影响，分别将其3种尺寸增大 $10 \%$ 、 $20 \%$ 及 $30 \%$ 之后进行磁-热耦合仿真，观察不同工况下永磁体的温度，并找出哪个参数会对永磁体的温度造成最大的影响。

# 4.1定子槽宽对永磁体温度的影响

分别将定子槽宽增大 $10 \%$ 、 $20 \%$ 及 $30 \%$ ，仿真后得到其温度云图如图6所示。

![](images/dae991744c24701a47d5f582932ce63aeb7675ee127706deacaecaad8431593b.jpg)

![](images/ad6cc0039114a033d555390687fc4dd3db893a3a19bf7b7d5abf8818cab4950f.jpg)  
图6永磁体随槽宽变化的温度云图

从仿真得到的数据来观察它们的温度变化，发现当槽口的宽度逐渐增大时，永磁体的最高温度也呈现逐步上升的趋势。

# 4.2气隙长度对永磁体温度的影响

分别将气隙长度增大 $10 \%$ 、 $20 \%$ 及 $30 \%$ ，仿真后得到其温度云图如图7所示。

![](images/6ae0ffd33162ba2e6d693f2babf0261e0d9f45bf93b1dd890ffe2fd8f557cc7c.jpg)  
Fig.6Temperature contours of the permanent magnet with the change of slot width

![](images/1629400f671268b66ef4e9a0b29ffb1e9bf2c75cf5f765db4d694ec25b903ce8.jpg)  
图7永磁体随气隙长度变化的温度云图  
Fig.7Temperature contours of the permanent magnet with the change of air gap length

观察仿真得到的永磁体温度，发现永磁体的温度会随着气隙长度的增大而呈下降的趋势。

# 4.3永磁体宽度对永磁体温度的影响

这里考虑永磁体宽度增大 $10 \%$ 及增大 $20 \%$ 的情况，因为永磁体宽度增大 $30 \%$ 的时候，它的宽度超过了极距，超出了尺寸范围，这是不允许的。结果如图8所示。

从仿真得到的数据来看，当永磁体的宽度逐渐增大时，永磁体的温度呈逐渐下降的趋势。

接着计算永磁体温度随这3种尺寸变化的变化率，做出比较如图9所示。

从图9可以发现，永磁体随气隙长度变化的变化率是最大的，其次是槽宽，最后是永磁体宽度，所以气隙长度的变化对永磁体的温度影响最大，在之后设计电机的时候，应考虑气隙长度对永磁体温度的影响，最好增大气隙长度，可以降低永磁体的温度，以保证电机运行可靠，延长使用寿命。

![](images/09d35886674178c4493e2272aa7378771ab8a57591a637238070963963a593c4.jpg)  
图8永磁体随永磁体宽度变化的温度云图

# 5 电机尺寸参数对海流发电机寿命的影响

因为电机的尺寸参数会改变电机及永磁体的温度，而温度会对电机的寿命产生很大的影响，在可靠性分析中也包括对产品的寿命预估，想要得到可

靠性高的电机，故障率要低，其寿命也要长，所以本节将计算电机在不同尺寸参数下的寿命，观察电机尺寸参数和电机寿命的关系。

电机的寿命主要取决于电机绕组的绝缘寿命，温度会对电机绝缘寿命有显著影响，高温将加快绝缘材料的物理变化和化学反应速度，促进绝缘老化。通过多年的研究和数据总结出绝缘寿命与温度关系的经验公式[]

$$
\ln T = { \frac { E _ { \mathrm { a } } } { R \theta } } - G = { \frac { B } { \theta } } - G
$$

式中， $\theta$ 为绝缘材料的温度； $R = 8 . 3 1 7 9 / \mathrm { k g \cdot \mathrm { ~ ‰ ~ } }$ ： $E _ { \mathrm { a } }$ $G$ 为与绝缘材料和化学反应有关的常数。对于B级绝缘电机，有： $G = 1 5 . 5$ ， $B = 1 0 ~ 2 0 0$ 。再根据不同的电机温度求得电机绝缘寿命。

# 5.1定子槽宽对电机寿命的影响

根据之前电机的温度场仿真，得到了定子槽宽分别改变 $10 \%$ 、 $20 \%$ 及 $30 \%$ 的电机温度，分别代入式(8)，计算电机寿命。变化曲线如图10所示。

27 000000  
26 000 000  
25 500 000  
25 000000 原始 槽宽 槽宽 槽宽工况 增大 $10 \%$ 增大 $20 \%$ （204号 增大 $30 \%$ 不同工况

![](images/f83fbc9ff2c10ac0eeb99c8e156fca2586c061f844f323871976b4f2fd6bc744.jpg)  
Fig.8Temperature contours of the permanent magnet witl the change of PM width   
图9永磁体温度随3种尺寸变化的变化率 Fig.9The change rate of the permanent magnet temperature with the change of three kinds of sizes   
图10电机寿命随着槽宽的变化曲线  
Fig.10The curve of the life with the change of slot width   
图11电机寿命随着气隙长度的变化曲线  
Fig.11The curve of the life with the change of air gap length

随着定子槽宽的增大，电机温度上升，电机寿命随之降低，电机温度与电机寿命的关系呈反比。

# 5.2气隙长度对电机寿命的影响

根据之前仿真得到的气隙长度分别改变 $10 \%$ F$20 \%$ 及 $30 \%$ 的电机温度来计算电机寿命。变化曲线如图11所示。

29 000000 28 000000   
000   
机 24 000 000   
电 23 000 000 22 000000 21000 000 原始 气隙 气隙 气隙 工况 增大 $10 \%$ （204号 增大 $20 \%$ （204号 增大 $30 \%$ 不同工况

随着气隙长度增大，电机温度上升，电机寿命随之降低。

# 5.3永磁体宽度对电机寿命的影响

根据之前仿真得到的永磁体宽度分别改变 $10 \%$ 及 $20 \%$ 的电机温度来计算电机寿命。变化曲线如图12所示。

![](images/f9e626c864c0a6d695e3fdea1634be285bd8aa0bef88f35e6e5e7160267a706a.jpg)  
图12电机寿命随着永磁体宽度的变化曲线  
Fig.12The curve of the life with the change of the PM width

随着永磁体宽度增大，电机温度下降，电机寿命随之增大。

通过改变3种尺寸来观察电机的寿命，可以发现： $\textcircled{1}$ 电机的温度和电机的寿命呈反比，为了延长电机的寿命，就要降低电机的温度，可见温度的重要性。 $\textcircled{2}$ 随着定子槽宽和气隙长度的增大，电机的寿命随之降低，随着永磁体宽度增大，电机的寿命随之增大，所以为了延长电机的寿命，应该减小定子槽宽和气隙长度，增大永磁体宽度。

# 6 结论

本文考虑到海流发电机在海流环境下更容易发生故障，故主要从永磁体温度场的角度对海流发电机进行可靠性分析。

（1）对海流发电机进行可靠性建模及预计，同时也计算了其平均间隔故障时间。

(2）通过改变定子槽宽、气隙长度和永磁体宽度这3种尺寸，对永磁体进行磁-热耦合仿真，发现随着气隙长度和永磁体宽度的增大，永磁体的温度是呈降低的趋势，而随着槽宽的增大，永磁体的温度是呈上升的趋势，且气隙长度的变化对永磁体的温度造成的影响最大。

(3）计算并比较电机在不同尺寸下的寿命，发现电机的温度和电机的寿命呈反比关系，另外随着定子槽宽和气隙长度的增大，电机的寿命随之降低，随着永磁体宽度增大，电机的寿命随之增大。

参考文献  
[1] 李科，胡欲立．永磁直流电机温度场分析[J]．鱼雷技术，2010，18(3)：228-235.Li Ke,Hu Yuli. Temperature field analysisof permanent magnet DC motor[J]. TorpedoTechnology,2010,18(3): 228-235.  
[2] GJB299C—2006 电子设备可靠性预计手册[S]．北京：中国人民解放军总装备部，2006.  
[3] Department of defense. Military handbook-electronicreliability design handbook[S]. USA,1998.  
[4] William Denson, Greg Chandler, William Crowell,et al.Non-electronic parts reliability data[S]. Rome,1991.  
[5] 冯敬东，来萍．电子产品 MTBF 的意义及工程化计算方法[J]．电子产品可靠性与环境试验，2008,26(2): 15-24.Feng Jingdong, Lai Ping. Discussion on actualmeaning and calculating method of MTBF forelectronic product[J]. Electronic Product Reliabilityand Environmental Testing, 2008,26(2): 15-24.  
[6] 刘小龙，侯樱，赵文峰．海流发电机的发展和应用[J]．能源工程，2008(6)：20-23.Liu Xiaolong,Hou Ying, Zhao Wenfeng. Thedevelopments and applications of marine currentturbine[J]. Energy Engineering,2008(6): 20-23.  
[7]叶雪荣，苏博男，由佳欣，等．基于有限元法的永磁直流电机三维稳态温度场分析[J]．机电元件，2012，32(2): 40-44.Ye Xuerong, Su Bonan, You Jiaxin, et al. Analysisof three-dimensional steady temperature field ofpermanent magnet DC motor based on finite elementmethod[J]. Electromechanical Components,2012,32(2): 40-44.  
[8] 王树军，刘健，徐硕，等．小型定速风力发电机对$1 0 \mathrm { k V }$ 分布式配电网中静电电压稳定性的影响[J].电气应用，2016，35(17)：25-27.  
[9] 魏雪环，兰志勇，谢先铭，等．永磁体涡流损耗与永磁同步电机温度场研究[J]．电机与控制应用,2015，42(5): 28-31.Wei Xuehuan, Lan Zhiyong, Xie Xianming, etal.Research of eddy current loss of permanentmagnet and temperature filed of PMSM[J]. Electric