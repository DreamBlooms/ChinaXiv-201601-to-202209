# 换流站接地网替代直流接地极运行的方案研究

谢惠藩 谭波²潘卓洪³ 童雪芳² 董晓辉²（1.中国南方电网有限责任公司广州 5106232.中国电力科学研究院 武汉4300743.武汉大学武汉 430074)

![](images/73008046d773f3712b0a2ad743298eb3ebd941b75573abe61dafa326eebfc6f0.jpg)

谢惠藩男 1980年生，博士，主要研究方向为电力系统分析运行与保护控制。

摘要：直流输电无接地极运行有助于尽早实现双极送电，换流站接地网替代直流接地极是目前最有效的措施。换流站接地网替代直流接地极情况下可能存在人身和二次设备安全问题、变压器直流偏磁危害、接地网发热和腐蚀问题。论文对这些问题进行逐一分析，最后综合各影响因素提出了直流输电控制策略的要求，即单极故障联跳双极、不平衡电流控制和双极同步解闭锁。研究工作为直流输电新型的无接地极运行方式提供了有效参考，相关控制策略在南方电网普侨特高压直流输电工程中得到了良好的应用。

关键词：换流站接地网 直流接地极 接地网发热和腐蚀 中图分类号：TM726.1

# Application Analysis on Converter Station Grounding Grid as DC Grounding Electrode

![](images/4bd8f88a0d32c736aa2b5365c47fd2d2257f3c00bf6694bf1375ffbda1130432.jpg)

Xie Huifan'Tan $B o ^ { 2 }$ Pan Zhuohong³ Tong Xuefang² Dong Xiaohui² (1.China Southern Power Grid Guangzhou 510623 China 2.China Electric PowerResearch Institute Wuhan 430074 China 3.Wuhan UniversityWuhan 430074 China)

谭波男1985年生，博士，主要研究方向为电力系统接地与电磁兼容。

Abstract: HVDC without grounding electrode is helpful to achieve bipolar transmission as soon as possible, replacing DC grounding electrode with converter station grounding grid is the most effective measure so far. However, there may be personal and secondary equipment safety problem,transformer DC biasing,heating problem and corrosion problem of the grounding grid. This paper analyses these problems one by one,and puts forward the requirements of DC transmission control strategy, namely, unipolar failure coupling bipolar,unbalanced current control, bipolar synchronization lock and unlock. This paper provides effective reference for HVDC without grounding electrode operation mode, the related control strategies are applied in the Puqiao UHVDC transmission engineering of Chinese southern power grid.

Keywords: Convertor station, grounding grid, DC grounding electrode, heating and corrosion of grounding grid

# 1 引言

直流接地极作为直流输电的工作接地[1]，对直流输电系统安全稳定运行起着十分重要的作用。在直流接地极建设过程中，征地和选址等外部原因常常导致接地极不能如期投产，从而影响直流输电工程的投运。随着我国大容量直流输电工程的大量建设，为了尽早实现送电，甚有必要研究直流系统的无接地极运行方式[2]。

目前高压直流输电工程无接地极运行的最有效方案是使用换流站接地网充当直流接地极以实现双极运行。站内接地网代替直流接地极双极运行将带来许多问题，包括对人身和二次设备安全的影响、系统内变压器直流偏磁、接地网发热和腐蚀、直流输电调整运行方式等。如何分析和克服上述问题均需深入开展大量的研究。

论文提出了高压直流输电工程无接地极运行的整体需求，分别对人身和二次设备安全，变压器直流偏磁、接地网发热和腐蚀等问题展开分析，最后综合各影响因素提出对直流输电控制策略的要求。研究工作为直流输电新型的无接地极运行方式提供有效参考，相关控制策略在南方电网普侨特高压直流输电工程中得到了良好的应用。

# 2换流站接地网替代直流接地极总体分析

换流站接地网替代直流接地极的问题主要包括以下几个方面[3-5]：

（1）严格保证站内人员和二次设备的安全。(2）保证换流变压器以及系统内其他变电站内  
的变压器免受严重的直流偏磁危害。(3）确保接地引下线和接地网本体不会出现温  
升超标的问题。（4）接地网腐蚀问题及其应对措施。

上述四个方面是换流站接地网替代直流极运行需要重点考虑的因素，这些因素确定的边界条件将作为直流输电的控制要求。下面将对上述因素开展逐一分析。

# 3 人身和二次设备安全

# 3.1人身安全问题分析

分析人身安全必须明确不同工况下的人身安全判据。考虑到换流站接地网替代直流极运行会面对长期的直流电流和暂态故障的瞬态电流，所以人身安全判据包括两个：

(1）稳态判据。站内接地网的最大接触电位差 $U _ { \mathrm { t } }$ 满足DL/T437—2012《高压直流接地极技术导 则》和DL/T5224—2014《高压直流输电大地返回 系统设计技术规程》的要求

$$
U _ { \mathrm { t } } \leqslant 5 0
$$

而站外人员的最大接触电位差 $U _ { \mathrm { t } }$ 则需要满足

$$
U _ { \mathrm { t } } \leqslant 7 . 4 2 + 0 . 0 0 8 \rho _ { \mathrm { s } }
$$

式中， $\rho _ { \mathrm { s } }$ 为表层土壤电阻率。

稳态判据为两种情况，一种是站内人员的安全，另外一种是站外人员的安全。站内人员的安全是以式（1）为标准的，稳态最大接触电位差按50V取，取最大接触电位差与地电位升高的比值 $k _ { \mathrm { t } }$ ，并令直流输电入地电流为 $I _ { \mathrm { f } }$ ，列出接触电位差表达式必须满足的边界条件，有

$$
U _ { \mathrm { t } } \leqslant k _ { \mathrm { t } } R I _ { \mathrm { f } } < 5 0
$$

折算允许入地电流 $I _ { \mathrm { f } }$ 为

$$
I _ { \mathrm { f } } < \frac { 5 0 } { k _ { \mathrm { t } } R }
$$

按式（4）可算出允许的入地电流上限，结果见表1。结果表明，为了保证人身安全，换流站接地网允许通过的直流电流可能低至 $5 0 0 \mathrm { A }$ 。该稳态判据为制定入地电流抑制策略提供参考，也可以用于指导运行和设计。

（单位：kA）

表1允许入地电流Tab.1 Tolerant current  

<html><body><table><tr><td rowspan="2">k</td><td colspan="5">R/Ω</td></tr><tr><td>0.1</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td></tr><tr><td>0.10</td><td>5.00</td><td>2.50</td><td>1.67</td><td>1.25</td><td>1.00</td></tr><tr><td>0.15</td><td>3.33</td><td>1.67</td><td>1.11</td><td>0.83</td><td>0.67</td></tr><tr><td>0.20</td><td>2.50</td><td>1.25</td><td>0.83</td><td>0.63</td><td>0.50</td></tr></table></body></html>

由于换流站连接有多条输电线路，这些线路的避雷线是和换流站接地网相连的。对于公众和电力系统人员可接触到的地上杆塔，避雷线－杆塔系统会导致直流故障时高电位引外的问题。如果直流故障持续时间长，加上杆塔和线路数目众多，站外人员触电的风险不容忽视。由于杆塔接地设计并不考虑触电问题，论文建议对杆塔接地进行均压改造。若不具备改造条件，建议换流站不做长时间单极运行，推荐单极故障联跳双极以保证站外人员的安全。

(2）暂态判据。单极故障联跳双极时，站内接地网的最大接触电位差 $U _ { \mathrm { t } }$ 满足GB/T50065—2011《交流电气装置的接地设计规范》的要求

$$
U _ { \mathrm { t } } = { \frac { 1 7 4 + 0 . 1 7 C _ { \mathrm { s } } \rho _ { \mathrm { s } } } { \sqrt { t _ { \mathrm { s } } } } }
$$

式中， $C _ { \mathrm { s } }$ 和 $\rho _ { \mathrm { s } }$ 分别为表层衰减系数和表层土壤电阻率； $t _ { \mathrm { s } }$ 为故障持续时间。

考虑两种情况，站内无高阻层（ ${ \mathit { \Omega } } ^ { \prime } C _ { \mathrm { s } } \rho _ { \mathrm { s } } \approx 1 0 0 { \mathit { \Omega } } ,$ 和有高阻层（ $C _ { \mathrm { s } } \rho _ { \mathrm { s } } \approx 3 ~ 0 0 0$ ）这两种情况，近似有

$$
U _ { \mathrm { t } } = k _ { \mathrm { t } } R I _ { \mathrm { f } } < \frac { 6 8 4 } { \sqrt { t _ { \mathrm { s } } } } \big ( \sharp _ { \sf H } ^ { \bf \Gamma } \big | \beta \mathrm { H } \big | \Xi \big )
$$

$$
U _ { \mathrm { t } } = k _ { \mathrm { t } } R I _ { \mathrm { f } } < \frac { 1 9 1 } { \sqrt { t _ { \mathrm { s } } } } \left( \nmid \nVDash \right. \nmid \frac { \kappa } { 2 \ddots }
$$

从式（6）和式（7）的对比可以看出，高阻层对提高接触电位差允许值的重要作用。由式（6）和式（7）折算电流的允许作用时间为

$$
\begin{array} { r } { t _ { \mathrm { S } } < \left( \frac { 6 8 4 } { k _ { \mathrm { t } } R I _ { \mathrm { f } } } \right) ^ { 2 } } \\ { t _ { \mathrm { S } } < \left( \frac { 1 9 1 } { k _ { \mathrm { t } } R I _ { \mathrm { f } } } \right) ^ { 2 } } \end{array}
$$

按式（8）和式（9）可算出允许的入地电流上限。结果表明，使用高阻层可以提高暂态电流的作用时间。以普侨特高压直流为例，单极故障联跳双极时0.1s瞬态电流可能高达16kA。使用高阻层时为了保证满足暂态判据，16kA电流作用时间可以控制在0.18s内，故满足要求。若不使用高阻层，6kA电流作用时间必须控制在 $1 4 \mathrm { m s }$ 内，这超出了目前直流输电工程的控制能力。综上所述，论文推荐站内敷设高阻层以保证人身安全。

# 3.2二次设备安全

二次设备的安全需要结合单极故障联跳双极的运行工况来考虑，这个暂态过程与交流故障相近，而一般换流站的交流故障在电流幅值和持续上均大于直流单极故障联跳双极的情况，鉴于在交流故障下二次设备是满足安全运行要求的，故直流故障情况下也是能够满足安全要求的。另外，交直流同时故障概率极低，故无需校核混合故障情况下的二次设备安全。

# 4 接地网发热分析

接地网发热分析需要考虑引下线热稳定性和接 地网的温升。

# 4.1接地引下线的热稳定性校验

单极故障联跳双极的运行工况下，GB/T50065—2011《交流电气装置的接地设计规范》要求接地引下线截面积必须满足

$$
S _ { \mathrm { g } } \geqslant \frac { I _ { \mathrm { g } } } { C } \sqrt { t _ { \mathrm { e } } }
$$

式中， $S _ { \mathrm { g } }$ 为引下线的最小截面积（ $\cdot \mathrm { m } \mathrm { m } ^ { 2 }$ ）； $I _ { \mathrm { g } }$ 为流过引下线的直流电流（A）； $C$ 为热稳定系数； $t _ { \mathrm { e } }$ 为电流持续时间(s)。

按普侨特高压直流的实际工况，计算在不同故障电流和持续时间情况下的引下线最小截面积，结果见表2。

# 表2不同故障电流和故障时间对应的最小截面积

Tab.2Minimum section area of various fault current and duration   

<html><body><table><tr><td>Ig/kA</td><td>te/s</td><td>Sg/mm²</td></tr><tr><td>3.0</td><td>2.0</td><td>64.6</td></tr><tr><td>9.0</td><td>1.0</td><td>128.6</td></tr><tr><td>12.0</td><td>0.2</td><td>76.7</td></tr><tr><td>16.0</td><td>0.1</td><td>72.3</td></tr></table></body></html>

表2结果表明，这个截面积小于一般交流故障电流热稳定的最小面积，故引下线是能够完全满足直流故障电流热稳定需要的。

# 4.2接地网的暂态温升校验

接地极的稳态温升计算公式有

$$
\tau _ { { \mathrm { m } } } = \frac { I ^ { 2 } R ^ { 2 } } { 2 \lambda \rho }
$$

由于采用了单极故障联跳双极的控制策略，接地网并不会承受长时间的直流电流，此时需要考虑暂态温升，其表达式为

$$
\tau = \tau _ { _ { \infty } } \left( 1 - { \mathrm e } ^ { - \frac { t } { T _ { \tau } } } \right)
$$

式中， $\tau _ { \mathrm { { o } } }$ 为土壤的稳定温升； $T _ { \mathrm { r } }$ 为土壤升温的时间常数。 $T _ { \mathrm { r } }$ 与局部的接地导体面电流密度有关，即

$$
T _ { \mathrm { r } } = { \frac { \tau _ { \omega } \gamma } { J ^ { 2 } \rho } } = { \frac { \gamma I ^ { 2 } R ^ { 2 } } { 2 \lambda J ^ { 2 } \rho ^ { 2 } } }
$$

对导体表面电流密度 $J$ 作如下简化：大地返回电流注入接地网时，接地导体上的表面电流分布是不均匀的。定义一个接地网的平均线电流密度为

$$
C _ { 0 } = \frac { I } { L }
$$

式中， $I$ 为返回电流； $L$ 为接地网导体的长度之和。

设最大的线电流密度为

$$
C _ { \mathrm { m a x } } = k C _ { 0 } = k \frac { I } { L }
$$

式中， $k$ 为接地网导体的电流不均匀系数。此时，最大的面电流密度为

$$
J _ { \mathrm { m a x } } = { \frac { C _ { \mathrm { m a x } } } { S } } = { \frac { k I } { L S } }
$$

计算取得发热时间常数 $T _ { \mathrm { r } }$ 后，通过暂态温升计算式(12)，就可以得出换流站接地网代替直流极后的允许运行时间公式为

$$
t _ { \mathrm { m } } = - T _ { \mathrm { r } } \log \left( 1 { - } \frac { \tau _ { \mathrm { m } } } { \tau _ { \mathrm { \omega } } } \right)
$$

由于 ${ \tau _ { \mathrm { { o } } } } \ll { \tau _ { \mathrm { { m } } } }$ ，故式（17）可近似为

$$
t _ { \mathrm { m } } \approx \frac { \tau _ { \mathrm { m } } } { \tau _ { \mathrm { \omega } } } T _ { \mathrm { r } }
$$

取 $k$ 为 $5 \sim 1 0$ ，大地返回电流 $3 \mathrm { k A }$ ，换流站接地网导体总长度分别取典型值 $2 0 \mathrm { k m }$ ，截面尺寸为$5 0 ~ \mathrm { m m } \times 7 ~ \mathrm { m m }$ ，大地电阻率在 $5 0 \sim 5 0 0 ~ \Omega \cdot \mathrm { m }$ 之间，计算得到发热时间常数 $T _ { \mathrm { r } }$ ，如图1所示。

式（18）表明，在 $t _ { \mathrm { m } }$ 时间内必须把注入接地网的大地返回电流抑制到稳态温升的安全水平之内，否则会造成局部土壤烧结，使接地网不能正常工作。极端情况下，发热时间常数 $T _ { \mathrm { r } }$ 可能低至2h，故3kA大地返回电流的允许运行时间只有 $5 \mathrm { m i n }$ 。理论上，接地网存在边沿效应，接地网四周边沿的接地体的表面电流密度较大，如果能够给边沿导体加段焦炭床，降低电流不均匀系数，就可以大大地提高发热时间常数。

# 5 接地网腐蚀分析

假设一年内直流输电工程的不平衡电流达到规程的上限，即 $1 \%$ 的额定电流。按目前主要的3kA

![](images/79ced9adb9ac292b4a248ba4df6953c445b9f8340f9b4fa0ba9c32f483b360af.jpg)  
温升的时间常数(h)，接地网总长度 $= 2 0 0 0 0 0 \mathrm { m }$   
图1温升时间常数  
Fig.1The time constant of temperature rise

级定额电流的直流输电工程来计算，参照前面的接地网发热分析引入的电流不均匀系数 $k$ ，可知接地网局部的最大腐蚀量 $G$ 为

$$
G = \frac { 1 ^ { 0 } \zeta _ { 0 } \times 3 0 0 0 \times 2 7 . 9 3 \times 3 6 5 \times 2 4 \times 3 6 0 0 \times 5 0 \% k \mu } { 9 6 4 9 0 L } y
$$

$$
= m [ L _ { 1 } L _ { 2 } - ( L _ { 1 } - \delta ) ( L _ { 2 } - \delta ) ] = m \delta ( L _ { 1 } + L _ { 2 } - \delta )
$$

式中， $y$ 为设计运行年限；取 $k$ 为 $5 \sim 1 0$ $\mu$ 为入地电流系数，典型值可取为0.1。分流系数考虑站内变压器中性点安装隔直电容和线路避雷线连接换流站地网的情况下，换流站入地电流只是直流输电单极大地返回电流的一部分。 $\mu$ 与线路出线数目、避雷线直流电阻、杆塔接地电阻和对侧系统的位置有关，一般情况下 $\mu < 0 . 3$ 。

换流站接地网的导体总长度为 $2 0 \sim 4 0 \mathrm { k m }$ ，取导体的截面尺寸为 $5 0 \mathrm { m m } \left( L _ { 1 } \right) \ \times 7 \mathrm { m m } \left( L _ { 2 } \right)$ 。把上述数据代入式 (19)，就可以计算得到均匀下的腐蚀厚度 $\delta$ 。计算时分别取换流站的设计年限 $y$ 为30年和50年，腐蚀厚度随电流不均匀系数和接地网导体总长度的关系，如图2和图3所示。

一般情况下，不平衡运行电流造成的截面的腐蚀量与接地网的设计寿命有关，30年可取 $0 . 4 ~ \mathrm { m m }$ 50年取 $0 . 7 ~ \mathrm { m m }$ 。在接地网设计阶段就应该充分考虑不平衡电流造成的腐蚀量并适当加大接地导体的截面积。

通过适当调整两极之间的电流（正极大于负极)，令换流站站内接地网做负极运行，即送端的电流方向为从地网流入中性母线，就可以避免不平衡电流造成的站内接地导体腐蚀。另外，如果能够进一步控制不平衡度，该腐蚀厚度也能够得到很好的控制。本文认为不平衡运行电流造成腐蚀是可以避免的，但需要增加换流站附近 $1 0 \sim 2 0$ 级杆塔接地极的导体截面积，以防止换流站分流造成的杆塔接地体腐蚀。

![](images/32d7ce8e493dfde948e66780a25f5d2075209b4989651f7bbcf410059b8b72a6.jpg)  
图2设计年限为30年时的腐蚀厚度

![](images/4d31740b785fdfd16a425ede8d2d85f6a5013f1c12b7ac3c21294c60ab4c60cd.jpg)  
Fig.2The corrosion thickness when the designed operating life is 30 years   
图3设计年限为50年时的腐蚀厚度 Fig.3The corrosion thickness when the designed operating life is 50 years

另外，由于使用单极故障联跳双极的控制策略，这个极短时的电流造成的接地网腐蚀是极轻微的。

# 6 直流输电控制策略

直流输电控制策略要求三点：单极故障联跳双极、不平衡电流控制和双极同步解闭锁。

（1）单极故障联跳双极。为了防止持续的单极返回电流入地造成人员安全和接地网发热问题，应该尽量减少入地电流时间，采取措施尽量保证双极同步解锁。参考普侨特高压直流的运行经验，建议在解锁及功率升降过程中选用双极功率模式运行，这样软件修改较少，双极功率参考值和升降速率直接下发给直流站控，由直流站控通过高速控制总线发送至双极的极控系统，通信延时较短，可以保证双极功率同步变化。实际中要求整个联跳过程时间在 $1 0 0 \mathrm { { m s } }$ 以内。

需要补充说明的是，采用单极故障联跳双极控制策略后，普侨特高压直流需要对送端云南电网切机 $3 ~ 5 0 0 \mathrm { M W }$ 以保证系统的稳定运行。单极故障联跳双极要作深入分析以确保其对系统稳定运行的影响。

(2）不平衡电流控制。直流运行过程中，可能由于设备或环境温度等因素导致一极电流受限制而降低，此时极间功率转移起作用，使得另一极增大，双极出现不平衡电流。因此需要在程序中增加双极电流同步跟随功能，以保证双极平衡运行。若为了控制入地电流方向，减少接地网腐蚀，可在解锁之后，功率升至设定值并保持稳定运行时，将双极切换为电流控制，独立设置双极电流参考值。

(3）双极同步解闭锁。参考普侨特高压直流的运行经验，双极同步解闭锁应作如下四点改进：

1）禁用双极运行方式下由运行人员下发的闭锁单阀组、单极功能，仅保留闭锁双极功能，且闭锁命令经由直流站控通过控制总线下发至双极极控系统，尽可能保证命令同步性。

2）本极对另外一极控制保护闭锁及紧急停运的响应功能，即双极通过直流站控快速共享闭锁和紧急停运信息，本极收到另外一极上述信息后，执行紧急停运顺序。

3）本极对另外一极的停运命令不区分闭锁或紧急停运，一律执行紧急停运顺序，缩短停运时间，尽可能保证双极停运同步。

4）同一极不再区分单个或多个阀组闭锁、紧急停运信息，任何一个阀组需要闭锁或紧急停运，除执行正常顺序外，再均由极控执行本极紧急停运顺序并将信息通过直流站控传送给另外一极。

# 7 结论

（1）论文提出了换流站接地网替代接地极的新思路，提出了高压直流输电工程无接地极运行的整

体需求。

(2）通过对人身和二次设备安全、变压器直流偏磁、接地网发热和腐蚀等问题的分析，论文提出了综合各影响因素的直流输电控制策略。(3）为了确保站内外人员的人身安全，要求直流输电使用单极故障联跳双极和双极同步解闭锁的控制方式。（4）为了避免直流电流腐蚀接地网导体，要求直流输电使用不平衡电流控制方式。(5）使用单极故障联跳双极、不平衡电流控制和双极同步解闭锁的控制策略后，接地网不会出现过热问题。(6）本文工作为直流输电新型的无接地极运行方式提供有效参考，相关控制策略在南方电网普侨特高压直流输电工程中得到了良好的应用，经过近一年运行，各项指标表现良好，完全满足运行要求。

# 参考文献

[1] Hannestad.HVDC ground electrode design.Finalreport[R]. International Engineering Company, Inc,1981.  
[2] 张勇，谢惠藩，梅勇，等．普侨直流普洱换流站内接地网替代接地极双极运行方案[J]．电力系统自动化，2016，40(9)：135-141.Zhang Yong,Xie Huifan,Mei Yong,et al. Analysison bipolar of puqiao UHVDC with station groundmat replacing electrode in puer rectifying station[J].Automation of Electric Power Systems,2016,40(9):135-141.  
[3] 国家能源局．DL/T437—2012高压直流接地极技术导则[S]．北京：中国电力出版社，2012.  
[4] 施红，陈政，冯蕾，等．郑州换流站接地网优化设计[J]．电力系统及其自动化学报，2014，26(12)：85-90.Shi Hong,Chen Zheng,Feng Lei,et al.Optimaldesign of grounding grid of zhengzhou converterstation[J].Proceedings of the CSU-EPSA,2014,26(12): 85-90.  
[5]王东，骆建龙，杨灿．特高压换流站接地网施工控制方法[J]．湖南电力，2015，35(3)：53-55.Wang Dong,Luo Jianlong, Yang Can. An ideaof software application in construction controlofgrounding grid in UHVDC converter station[J].Hunan Electric Power, 2015,35(3): 53-55.  
[6] 中华人民共和国住房和城乡建设部．GB/T50065—2011 交流电气装置的接地设计规范[S]．北京：中国计划出版社，2012.  
[7] 马福．雷击变电所地电位干扰及防护措施研究[D]．长沙：长沙理工大学，2009.  
[8] 何艳娇．变电站弱电设备防雷保护的研究[D]．长沙：长沙理工大学，2007.  
[9] 俞培祥，余虹云，潘海兰．变电所接地导通测试的分析[J]．江苏电器，2007(3)：59-63.Yu Peixiang, Yu Hongyun, Pan Hailan. Analysis oftest for ground connection in substations[J]. JiangsuElectrical Apparatus, 2007(3): 59-63.  
[10]章文俊，钱毅，张凤新，等．准东—华东 $\pm 1 ~ 1 0 0 \mathrm { k V }$ 特高压送端换流站接地极及接地极线路规划[J].电气应用，2016，35(15)：66-69.  
[11]常，王明磊，许崇武，等．接地网网内电位差的均衡优化[J]．电网技术，2008，32(22)：98-102.Chang Yong,Wang Minglei, Xu Chongwu, et al.Equilibrium optimization of potential differenceswithin grounding mesh[J]. Power SystemTechnology,2008,32(22): 98-102.  
[12]张露，黄文武，文习山，等．接地网内电势差的计算模型[J]．高电压技术，2014，40(4)，1045-1051.Zhang Lu, Huang Wenwu, Wen Xishan, et al.Modeling of grounding inter-potential difference[J].High Voltage Engineering,2014, 40(4),1045-1051.  
[13]南方电网科院研究院．糯扎渡电站送电广东特高压直流输电工程双极平衡运行接地网作临时接地方式研究[R]．2012.  
[14]国家能源局．DL/T 5224—2014 高压直流输电大地返回系统设计技术规程[S]．北京：中国计划出版社，2014.