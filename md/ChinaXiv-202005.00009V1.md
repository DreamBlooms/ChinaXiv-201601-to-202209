# 河套灌区不同土地类型生长季蒸散发量估算及其变化特征

王燕鑫'，李瑞平'，李夏子²（1．内蒙古农业大学水利与土木建筑工程学院,内蒙古 呼和浩特010018；2．内蒙古气象科学研究所,内蒙古 呼和浩特010051)

摘要：为揭示不同土地类型蒸散发量 $( E T )$ 差异特征,基于SEBS(surface energy balance system)模型,结合气象数据、遥感影像及土地利用分类结果，对河套灌区2017年生长季日 $E T$ 进行SEBS模型估算，分析灌区 $E T$ 时空变化特征及不同土地类型的 $E T$ 差异。结果表明： $\textcircled{1}$ 通过实测数据和FAOPenman-Monteith(PM)计算值对SEBS 模型估算结果精度验证，蒸渗仪观测数据、涡度相关系统 $( E C )$ 、波文比能量平衡系统(BREB)和PM计算值的相对误差平均值分别为： $; 1 6 . 6 6 \% 1 8 . 3 4 \% , 1 4 . 9 3 \% , 1 4 . 0 3 \%$ ，表明SEBS模型可以用来估算河套灌区 $E T$ 。 $\textcircled{2}$ 生长季内,灌区日ET大小依次为：7月 $> 6$ 月 $> 5$ 月 $> 8$ 月 $> 9$ 月。日 $E T$ 呈单峰形变化,7月日 $E T$ 达到最大值 ${ \bf 5 . 2 1 \ m m \cdot d ^ { - 1 } , }$ 9月日 $E T$ 最小,为 $3 . 5 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 。 $\textcircled{3}$ 不同土地类型的日 $E T$ 大小依次为：水体 $>$ 林地 $>$ 耕地 $>$ 草地 $>$ 城市 $>$ 荒地。灌区内 $E T$ 分布与土地类型具有高度一致性,总体分类精度和Kappa 系数分别为 $8 0 . 6 3 \%$ 和 $0 . 7 5$ 。 $\textcircled{4}$ 在生长季的不同时间,水体 ET均处于较高值,7月日 $E T$ 达到最大值 $6 . 0 3 4 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } ,$ 9月日 $E T$ 值最小,为 $4 . 1 7 7 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 。其次林地日ET较大,7月日 $E T$ 值为 $5 . 9 7 7 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } , 9$ 月日 $E T$ 值为 $4 . 1 4 7 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 。耕地日 $E T$ 变化趋势与作物生长情况相一致,作物生长旺盛期 $E T$ 值达 $5 . 8 5 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ,作物收获期 $E T$ 值为 $3 . 9 5 2 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 。

关键词：生长季；蒸散发量；SEBS模型；Softmax分类方法；土地类型；河套灌区

蒸散发(ET)是地表水量和热量平衡的重要参量，是水分吸收能量从液态转变为气态的过程，包含土壤、水体和植被的蒸发、蒸腾，也是衡量植物生长状况和作物产量的重要指标[1]。蒸散发也是水循环和能量循环的重要组成部分，影响着区域乃至全球的生态、气候及农业生产，所以对蒸散发进行有效的估算是十分必要的。ET估算方法研究已有200多年的历史，传统的ET估算是基于点位的地面观测，只适用于林地、农地等小尺度范围。考虑到大区域陆面异质性和热传输过程的动态性，无法很好地将点位观测结果推广到区域尺度[2]。近年来,遥感技术具有大范围、实时、高效、费用低廉等优点，为估算大区域的地表ET开辟了一条新途径[3]。遥感技术可以在时间和空间上快速获取大面积的地物光谱信息，能及时反映出由于水分盈亏所引起的地表ET变化。王卫光等[4]使用 SEBS 模型结合 MODIS 数据与现有的MOD16、ETzhang蒸散发产品进行对比，结果显示SEBS模型的结果要优于蒸散发产品。王瑶[5]利用 SEBS 模型分析黑河中游作物需水量的时空分布格局，并对SEBS模型的输入参数进行了敏感性分析。张圆等[采用SEBS 模型对新疆昌吉州呼图壁县蒸散发量进行估算，反映了天山北坡典型县域蒸散量的时空变化特征。伴随遥感数据大量增多，且精度逐步提高，针对河套灌区ET研究有了更广泛的素材。张薇等 $^ { [ 7 ] } 2 0 0 9$ 年基于 MODIS 数据通过模型反演河套平原2006年日ET，并对河套平原ET 进行了分析。杨雨亭等[8]2012 年利用双源模型对河套平原潜在ET进行了对比研究，通过假设不同的植被覆盖状况，较为详细地比较了3种双源蒸散发模型在估算潜在ET以及区分潜在蒸发量与潜在腾发量时的模拟效果。这些研究为估算区域ET提供了可靠适用的理论基础。

内蒙古河套灌区属干旱气候区域，水资源短缺，总量上匮乏，且区域分布不均衡，农业生产主要靠引黄河水灌溉。目前，虽然针对河套灌区ET研究已有部分成果，但难以准确反映出整个灌区ET空间异质性。土地利用的方式对灌区ET也有显著的影响，ET随不同土地类型而异。明确ET实际时空格局变化特征，对于合理分配水资源、提高水资源利用率具有重要意义。本文基于SEBS模型估算灌区ET,定量研究不同土地类型生长季的ET时空变化规律及其差异特征，明确认识土地利用对ET的影响。对于调节灌区气候、保护生态环境,促进农业生产有着重要的现实意义，为进一步改善灌区土地合理利用、有效分配水资源提供一定的技术支持。

# 1研究区概况及数据来源

# 1.1 研究区概况

内蒙古河套灌区位于巴彦淖尔的磴口县、杭锦后旗、临河区、五原县、乌拉特前旗5个地区，东西约$2 5 0 ~ \mathrm { k m }$ ，南北约 $5 0 ~ \mathrm { k m }$ 。北依阴山山脉的狼山、乌拉山南麓洪积扇，南临黄河，东至包头市郊，西接乌兰布和沙漠,属中温带季风气候，地理坐标 $4 0 ^ { \circ } 1 2 ^ { \prime } \sim$ $4 1 ^ { \circ } 1 8 ^ { \prime } \mathrm { N } , 1 0 6 ^ { \circ } 2 0 ^ { \prime } \sim 1 0 9 ^ { \circ } 2 9 ^ { \prime } \mathrm { E }$ 。灌区地势平坦，西南高,东北低，海拔高度 $1 0 0 7 \sim 1 0 5 0 \mathrm { m }$ ，坡度$0 . 1 2 5 \% o \sim 0 . 2 \ \% o .$ 。实际灌溉面积约 $6 . \ 0 1 \ \times \ 1 0 ^ { 5 }$ $\mathrm { { h m } } ^ { 2 [ 9 ] }$ ,占总土地面积的 $5 1 . 2 \%$ 左右,引黄水量占灌区总耗水量的 $8 6 . 6 \%$ ，是灌区最重要的水分来源。灌区降水量少，蒸发量大，年平均降水量 $1 4 0 \sim 2 3 0$ $\mathbf { m } \mathbf { m }$ ,年平均蒸发量 $1 ~ 9 0 0 \sim 2 ~ 3 0 0 ~ \mathrm { m m }$ 。夏季高温干旱、冬季严寒少雪，无霜期短,封冻期长，全年以西风和西北风为主，日温差大，日照时间长。研究区高程及空间位置如图1所示。

# 1.2 数据来源

1.2.1遥感数据遥感影像是SEBS模型进行区域ET估算的必要条件，Landsat8遥感影像从地理空间数据云（http://www.gscloud. $\mathrm { c n / }$ )下载。利用遥感影像及SEBS模型反演区域ET，对影像数据的质量要求较高，综合考虑研究区作物种植时间及生长情况，选取河套灌区2017年生长季5一9月晴天条件且云量较少、图像质量较好的遥感影像进行ET分析。对影像数据分别进行辐射定标、FLASH大气校正等预处理，反演出SEBS模型，计算ET所需的遥感参数，包括地表温度、地表比辐射率、地表反照率、归一化植被指数、植被覆盖度、叶面积指数、植被高度、位移高度、表面粗糙度。

1.2.2气象数据及其他辅助数据地面气象数据来源于中国气象数据网（http://data.cma.cn/）及部分当地气象站。收集处理2017年研究区内及周边的14个气象站5一9月日值气象数据，气象站分布如图1所示。其中位于研究区域外的9个气象站主要用于局部空间插值，以保证研究区边界气象参数的空间插值结果连续平滑。气象数据包括日照时数、日平均气压、日地表压力、日平均气温、相对湿度、日平均风速、比湿。为提高SEBS模型估算精度，将不同气象参数进行Kriging空间插值，得到与遥感影像空间分辨率相同的气象栅格数据。

精度验证数据分为实测数据和计算数据两类。以FAOPenman-Monteith(PM)计算的灌区内5个气象站点的ET值作为理论数据，实测数据源自2017年5一9月临河试验地的蒸渗仪观测ET数据和分子地涡度相关（EC）及波文比能量平衡（BREB）系

![](images/57c06b7df562451b433caddb546caa0135eccd8af4f18299d8af16d4872511df.jpg)  
图1研究区高程及空间位置示意图  
Fig.1Schematic diagram of research area elevation and location

统得到的 $E T$ 值。

（1）蒸渗仪的观测数据获取

临河试验地实测 $E T$ 值采用微型蒸渗仪测定，测定设置因素分别为材料和尺寸。其中，内外桶材料均采用PVC材质，内桶直径 $1 0 \ \mathrm { c m }$ ,外桶直径15cm，内外桶深度均为 $2 0 \ \mathrm { c m }$ ,封底材料选用细纱布。于试验期间每天08：00采用精度 $0 . 1 \mathrm { ~ g ~ }$ 的电子天平（PL6001-L，MettlerToledoInc.,瑞士)对微型蒸渗仪称重，根据两次重量差，经面积换算再加上灌溉或降水量得到每天的 $E T$ 值。为保证测量数据的准确性，在田间不同位置布设7个相同规格的微型蒸渗仪，取其平均值。

（2）涡度相关及波文比能量平衡系统的观测数据获取

临河分子地安装了涡度相关及波文比能量平衡系统，于2017年5—9月底连续测量，均位于被同一作物所包围的观测场，为系统测量ET值提供了足够的获取长度。以自立式铁塔作为能量观测塔，分别架设涡度相关及波文比能量平衡系统，在作物最大冠层高度上方 $1 . 5 \mathrm { ~ m ~ }$ 处安装带有开放式红外 $\mathrm { H } _ { 2 } \mathrm { O }$ 和 $\mathrm { C O } _ { 2 }$ 分析仪的CSAT3三维超声波风速计（LI-

7500，LI-CORInc.，美国），测水平和垂直方向风速的脉动值，并在作物生育期经过一次位置调整。TCAV热电偶探头测土壤的平均温度，CS616土壤湿度传感器测土壤水分。在观测塔底部装有观测小屋，用于观测数据的读取、记录及临时处理。通量塔一侧的传感器通过线路与观测小屋相连接,数据以$1 0 ~ \mathrm { H z }$ 采样并使用CR3000数据记录仪以 $3 0 ~ \mathrm { m i n }$ 间隔记录。在通量塔的另一侧，架设高度为最大树冠上方 $1 \mathrm { ~ m ~ }$ 处,装有CNR4-L1O 净辐射计（Kipp&Zonen,荷兰)用于测量向上和向下的长短波净辐射及日照时数。在土壤表面以下约 $6 ~ \mathrm { c m }$ 处埋设两个HFPO1热流板（Hukseflux，荷兰），测一段时间内的地热通量。涡度相关及波文比能量平衡系统测得的通量数据通过EddyPro（LI-COR）软件进行峰值检测、频率响应校正、声波温度转换为实际温度等后台处理,并使用平面拟合方法和WPL（Webb-Pearman-Leuning)密度校正。使用前均进行坐标旋转、数据插补和求日平均等处理，以获得质量较高的实测数据[10]。利用两类ET值对 SEBS 反演的 ET结果进行变化趋势分析及精度检验，微型蒸渗仪与观测系统如图2所示。

![](images/befafb1b8862d55f03a90e03f71b2ea0f2fa709f9e0365597ddd8835d4e97305.jpg)  
图2微型蒸渗仪、涡度相关(EC)及波文比能量平衡(BREB)系统示意图  
g.2Schematic diagram of micro-lysimeter、eddy covariance( $( E C )$ and Bowen-ratio-energy-balance(BREB）syste:

# 2 研究方法和模型

$$
R _ { \mathrm { n } } = G _ { \mathrm { 0 } } + \lambda E T + H
$$

# 2.1 研究方法

2.1.1SEBS 模型计算SEBS 模型[1-15]利用已处理完成的地表参数和气象数据，对灌区的地表净辐射通量、显热通量及土壤热通量进行估算。任意时刻的地表能量平衡方程如下：

式中： $R _ { \mathrm { n } }$ 为地表获得的净太阳辐射通量（W·$\mathrm { ~ m ~ } ^ { - 2 }$ ） $G _ { 0 }$ 为土壤热通量( $\mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ),下垫面土壤中的热交换; $\lambda E T$ 为潜热通量 $\left( \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 } \right.$ ),下垫面与大气之间的水汽热交换,其中， $\lambda = 2 . 4 5 \times 1 0 ^ { 6 } \mathrm { ~ J ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ ，为水的汽化热； $E T$ 为蒸散量( $\mathrm { ~ ( ~ k g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 } \mathrm { ~ \cdot ~ s ~ } ^ { - 1 } \mathrm { ~ \cdot ~ }$ ） $H$ 为感热通量，也称为显热通量 $ { \langle \mathbb { W } \cdot \mathrm { ~ m ~ } ^ { - 2 } }$ )，下垫面与大

气湍流形成的热交换。

(1)净辐射 $( R _ { \mathrm { n } } )$ 公式为：

$$
R _ { \mathrm { n } } = \left( 1 - \alpha \right) R _ { \mathrm { s w d } } + R _ { \mathrm { l w d } } - \varepsilon \delta T _ { \mathrm { 0 } } ^ { 4 }
$$

式中： $\alpha$ 为地表反射率； $R _ { \mathrm { s w d } }$ 为下行太阳辐射; $R _ { \mathrm { 1 w d } }$ 为下行长波辐射； $\varepsilon$ 为地表比辐射率； $T _ { 0 } ^ { 4 }$ 为传感器测得的辐射地表温度 $( { \mathcal { C } } ) { \boldsymbol { \cdot } } { \boldsymbol { \delta } }$ 为斯蒂芬-波尔兹曼常数$( 5 . 6 7 \times 1 0 ^ { - 8 } )$ 。

(2）土壤热通量 $\left( { { G } _ { 0 } } \right)$ 公式为：

$$
\begin{array} { r } { G _ { \mathrm { 0 } } = R _ { \mathrm { n } } \big [ \Gamma _ { \mathrm { c } } + \big ( 1 - f _ { \mathrm { c } } \big ) \big ( \Gamma _ { \mathrm { s } } - \Gamma _ { \mathrm { c } } \big ) \big ] } \end{array}
$$

式中：假定土壤热通量和净辐射通量之间的比值对于完全植被覆盖的地区 $\Gamma _ { \mathrm { c } }$ 为0.05（植被覆盖较好区域);相对于裸土设定为 $\Gamma _ { \mathrm { { s } } }$ 为0.315（裸土区域）；在这两种极端条件之间则可以利用植被覆盖度 $( f _ { c } )$ 来进行插值计算，其中 $f _ { c }$ 能够通过遥感数据来确定，通过下式计算求得。

$$
f _ { c } = \frac { \mathrm { { N D V I - N D V I } _ { \operatorname* { m i n } } } } { { \mathrm { N D V I } } _ { \operatorname* { m a x } } - { \mathrm { N D V I } } _ { \operatorname* { m i n } } }
$$

（3）显热通量 $( H )$ 公式为：

在大气近地层中，根据大气边界层相似理论，有以下的关系：

$$
u = \frac { u _ { \ast } } { k } \left[ \ln \left( \frac { z - d _ { 0 } } { z _ { 0 \mathrm { m } } } \right) - \varPsi _ { \mathrm { m } } \left( \frac { z - d _ { 0 } } { L } \right) + \varPsi _ { \mathrm { m } } \left( \frac { z _ { 0 \mathrm { m } } } { L } \right) \right]
$$

$$
\theta _ { 0 } - \theta _ { \alpha } = \frac { H } { { k { u ^ { * } } \rho C _ { p } } } \left[ { \bf { l n } } \bigg ( \frac { z - d _ { 0 } } { z _ { 0 \mathrm { { h } } } } \bigg ) - \varPsi _ { \mathrm { { h } } } \bigg ( \frac { z - d _ { 0 } } { L } \bigg ) + \right.
$$

$$
\varPsi _ { \mathrm { h } } \left( \frac { z _ { \mathrm { 0 h } } } { L } \right) \Bigg ]
$$

$$
{ \cal { L } } = ~ - { \frac { \rho C _ { { } _ { p } } \theta _ { { } _ { v } } u _ { * } ^ { 3 } } { k g H } }
$$

式中： $z$ 为参考高度 $\mathbf { \Omega } ( \mathbf { \Omega } _ { \mathbf { m } } ) : u$ 为风速 $( \mathbf { m } \cdot \mathbf { s } ^ { - 1 }$ ）； $u ^ { * }$ 为摩擦风速 $( \mathbf { m } \cdot \mathbf { s } ^ { - 1 } ) ; d _ { 0 }$ 为零平面位移高度 $\left( \mathrm { ~ m ~ } \right) ; \boldsymbol { z } _ { 0 \mathrm { { m } } }$ 和 $z _ { \mathrm { 0 h } }$ 分别为动力学粗糙长度 $\mathrm { ~ ( ~ m ~ ) ~ }$ 和地表热传输粗糙长度 $( \mathbf { m } ) : \boldsymbol { \Psi } _ { \mathrm { m } }$ 和 $\psi _ { \mathrm { h } }$ 分别为动力学和热力学传输的稳定度订正函数； $\theta _ { 0 }$ 和 $\theta _ { \alpha }$ 分别为观测面和参考面高度的虚温 $( { \mathcal { \mathbf { C } } } ) _ { } ! L$ 为莫宁霍夫长度（m）; $H$ 为感热通量 $\left( \mathrm { \mathbb { W } } \cdot \mathrm { m } ^ { - 2 } \right.$ ）； $k$ 为卡尔曼常数; $\rho$ 空气密度 $( \mathbf { g } \cdot \mathbf { \partial }$ $\mathrm { ~ m ~ } ^ { - 3 }$ ）； $C _ { p }$ 为空气热容 $( { \bf J } \cdot { \bf g } ^ { - 1 } \cdot { \bf \mathcal { C } } ) ;$ $\theta _ { v }$ 近地表的位温 $( { \mathcal { C } } ) _ { : g }$ 重力加速度 $( \mathbf { m } \cdot \mathbf { s } ^ { - 2 } )$ 。摩擦风速 $( u )$ 感热通量 $( H )$ 、莫宁霍夫长度 $( L )$ 可以通过迭代以上3个求解方程得到，其他的变量通过气象观测信息结合遥感观测信息求得。

（4）日蒸散量 $( E T )$ 计算公式为：

假定在干燥地表环境下，由于土壤地表水分亏缺，导致土壤水分用于蒸发的量极少，此时潜热通量约为零,这种条件下，根据地表能量平衡方程，此时感热通量达到最大值，即干燥条件下的感热通量Hdry:

$$
H _ { \mathrm { d r y } } = R _ { \mathrm { n } } - G _ { \mathrm { 0 } }
$$

式中： $H _ { \mathrm { d r y } }$ 为干燥地表条件下的感热通量（W·$\mathrm { ~ m ~ } ^ { - 2 }$ );在土壤水分充足时，湿限条件下的感热通量$H _ { \mathrm { w e t } }$ 是通过FAOPenman-Monteith 公式得出：

$$
H _ { \mathrm { w e t } } = \Big [ \left( R _ { \mathrm { n } } - G _ { 0 } \right) - \frac { \rho C _ { p } } { r _ { \mathrm { e w } } } \cdot \frac { e _ { \mathrm { s } } - e } { r } \Big ] \Big / \left[ 1 + \frac { \Delta } { r } \right]
$$

$$
r _ { \mathrm { e w } } = \frac { 1 } { k u _ { * } } \left[ \ln \left( \frac { z - d _ { 0 } } { z _ { 0 \mathrm { h } } } \right) - \varPsi _ { \mathrm { h } } \left( \frac { z - d _ { 0 } } { L _ { \mathrm { w } } } \right) + \varPsi _ { \mathrm { h } } \left( \frac { z _ { 0 \mathrm { h } } } { L _ { \mathrm { w } } } \right) \right]
$$

$$
L _ { \mathrm { w } } = - \frac { \rho u _ { \ast } ^ { 3 } } { k g \cdot 0 . 6 1 \cdot \left( R _ { \mathrm { n } } - G _ { 0 } \right) / \lambda }
$$

其中，相对蒸发比 $\textstyle \varLambda _ { r }$ 定义为：

$$
\varLambda _ { r } = \frac { \lambda E } { \lambda E _ { \mathrm { { w e t } } } } = 1 - \frac { \lambda E _ { \mathrm { { w e t } } } - \lambda E } { \lambda E _ { \mathrm { { w e t } } } } = 1 - \frac { H - H _ { \mathrm { { w e t } } } } { H _ { \mathrm { { d r y } } } - H _ { \mathrm { { w e t } } } }
$$

蒸发比 $\varLambda$ 定义为实际蒸散发与可用能量的比值：

$$
\varLambda = \frac { \lambda E } { R _ { \mathrm { n } } - G _ { 0 } } = \frac { \varLambda _ { r } \cdot \lambda E _ { \mathrm { w e t } } } { R _ { \mathrm { n } } - G _ { 0 } }
$$

综合上式，可得到日 $E T$ 计算公式为：

$$
E T = 8 . 6 4 \times 1 0 ^ { 7 } \times A \times \frac { R _ { \mathrm { n } } - G _ { \mathrm { 0 } } } { \lambda \rho _ { \mathrm { w } } }
$$

式中： $E T$ 为单日蒸散量; $\varLambda$ 为蒸发比； $\rho _ { \mathrm { w } }$ 为水的密度。为了确定蒸发比的值，需要考虑在最干和最湿润两种极限状态下的能量平衡关系。

2.1.2土地利用分类参照2017年哨兵2号全国土地利用分类图及分类标准[16],通过全新的图像分类框架（ENVIClassificationFramework）提供的土地利用分类方法Softmax，将河套灌区的土地类型划分为水体、耕地、林地、城市（居民用地、建设用地）、草地和荒地6类。Softmax土地分类方法使用不同算法进行训练，充分利用对象的光谱特征、纹理特征与空间特征等，输入多波段组合的栅格图像和训练样本，在保证分割对象间的平均异质性最小和对象内像元间同质性最大的基础上，通过梯度下降法和迭代法对像元进行分割与合并，实现遥感图像不同地物类型分类。本研究利用损失曲线和混淆矩阵对土地分类精度进行评定。损失曲线是该分类方法对分类结果的初步判定。随迭代次数增加，损失曲线逐渐趋于零，变化趋势平稳时，可进行分类评估和图像分类。混淆矩阵是一种用来表示分类精度的标准格式,是由一组 $n \times n$ 的矩阵构成, $n$ 表示分类数， $\boldsymbol { P } _ { i j }$ 为参考数据 $i$ 类被分到分类数据 $j$ 类的样本数， $\boldsymbol { P } _ { i j }$ 为正确分类数， $\boldsymbol { P } _ { i + }$ 为分类得到的第 $i$ 类总和， $P _ { + j }$ 为分类数据的第 $j$ 类总和, $P$ 为样本总数。根据混淆矩阵法对分类结果精度评价，评价的指标主要有生产者精度（PA）用户精度（UA）、总体精度（OA)及Kap-pa系数（KIA）[17]

$$
\mathrm { P A } = { \frac { P _ { i j } } { P _ { i + } } }
$$

$$
\mathrm { U A } = { \frac { P _ { i j } } { P _ { _ { + j } } } }
$$

$$
\mathrm { O A } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } { P _ { i j } } } { P } }
$$

$$
\mathrm { K I A } = { \frac { P \sum _ { i = 0 } ^ { n } P _ { i j } - \sum _ { i = 0 } ^ { n } ( P _ { i + } P _ { + j } ) } { P ^ { 2 } } }
$$

# 2.2模型验证方法

利用不同方式得到的两类 $E T$ 值，对SEBS模型反演结果进行精度检验。一是以临河试验地蒸渗仪观测的ET数据、分子地涡度相关系统及波文比能量平衡系统得到的 $E T$ 值作为实测检验数据，二是以 PM 综合方程计算结果作为理论检验数据[18-21] 。PM模型的计算公式如下。

$$
E T _ { \mathrm { p u } } = \frac { 0 . 4 0 8 \Delta ( R _ { \mathrm { n } } - G _ { \mathrm { 0 } } ) + \gamma \displaystyle \frac { 9 0 0 } { T + 2 7 3 } u _ { \mathrm { 2 } } ( e _ { \mathrm { s } } - e _ { \mathrm { a } } ) } { \Delta + \gamma ( 1 + 0 . 3 4 u _ { \mathrm { 2 } } ) }
$$

式中： $\Delta$ 为饱和水汽压曲线斜率， $\mathrm { k P a } \cdot \mathrm { ^ { - 1 } } ; R _ { \mathrm { n } }$ 为地表净辐射量, $\mathrm { M J } \cdot \mathrm {  ~ m ~ } ^ { - 2 } \cdot \mathrm {  ~ d ~ } ^ { - 1 } ; G _ { 0 }$ 为土壤热通量,$\mathrm { M J } \cdot \mathrm { m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 }$ $\gamma$ 为干湿表常数， $\mathrm { k P a } \cdot \mathcal { C } ^ { \mathrm { ~ - 1 ~ } } ; u _ { 2 }$ 为2$\mathbf { m }$ 处风速， $\mathbf { m } \cdot \mathbf { \mathfrak { s } } ^ { - 1 } ; e _ { \mathrm { s } } \cdot e _ { \mathrm { a } }$ 为饱和水汽压、实际水汽压， $\mathrm { k P a } ; T$ 为平均温度， $\mathcal { \mathrm { C } }$ 。

# 3结果与分析

# 3.1 结果验证

3.1.1SEBS 模型反演结果验证根据实测数据对$E T$ 反演结果进行变化趋势分析及精度检验（表1）。从表1可知：研究区SEBS模型反演结果与3种实测 $E T$ 值变化趋势基本一致,SEBS模型反演结果与波文比观测值最接近，不同时间的相对误差差异较小，相对误差平均值为 $1 4 . 9 3 \%$ 。SEBS模型的反演结果与蒸渗仪、涡度系统观测值的相对误差平均值分别为 $1 6 . 6 6 \%$ 和 $1 8 . 3 4 \%$ 。

利用国际应用较广、公认的PM模型对SEBS模型反演结果进行点位精度验证(表2）。由表2可以看出：SEBS模型与PM模型的5个点位 $E T$ 值随时间变化趋势相一致，受不同气象参数的影响，五原的 $E T$ 估算结果与PM模型的 $E T$ 计算结果最接近，相对误差平均值为 $8 . 2 3 \%$ ,9月的相对误差最小，为$1 . 0 5 \%$ ,5、6月的相对误差接近且达到最大，相对误差为 $1 5 . 4 0 \%$ 。临河的 $E T$ 估算结果与PM模型的$E T$ 计算结果差异略大,相对误差平均值为 $2 0 . 9 4 \%$ ，7月两者的 $E T$ 结果较接近，相对误差为 $5 . 6 1 \%$ ,5月的差值较大，相对误差为 $2 7 . 6 1 \%$ 。受遥感影像质量与气象数据影响，不同点位的相对误差值在时间上分布不一致，导致SEBS模型反演结果的偏离程度不同。PM模型计算的5个气象站的相对误差平均值为 $1 4 . 0 3 \%$ ,均在允许的误差范围之内，SEBS模型估算整个河套灌区 $E T$ 具有较高的准确性和实用性。

表1不同月份SEBS模型计算值与实测结果对比  
Tab.1 Comparison of SEBS modelcalculated values and measured results   

<html><body><table><tr><td>月份</td><td>SEBS 估算值 /(mm·d-1)</td><td>波文比观测值 /(mm·d-1)</td><td>相对误差 /%</td><td>涡度系统观测值 /(mm·d-1)</td><td>相对误差 /%</td><td>蒸渗仪观测值 /(mm·d-1)</td><td>相对误差 /%</td></tr><tr><td>5</td><td>4.52</td><td>1</td><td>1</td><td>-</td><td>1</td><td>5.58</td><td>19.00</td></tr><tr><td>6</td><td>4.72</td><td>5.23</td><td>9.75</td><td>1</td><td>1</td><td>5.64</td><td>16.31</td></tr><tr><td>7</td><td>5.21</td><td>5.98</td><td>12.88</td><td>6.39</td><td>18.47</td><td>5.69</td><td>8.44</td></tr><tr><td>8</td><td>4.27</td><td>5.16</td><td>17.25</td><td>5.36</td><td>20.34</td><td>5.33</td><td>19.89</td></tr><tr><td>9</td><td>3.51</td><td>4.38</td><td>19.86</td><td>3.02</td><td>16.23</td><td>4.37</td><td>19.68</td></tr><tr><td>相对误差平均值</td><td></td><td></td><td>14.93</td><td></td><td>18.34</td><td></td><td>16.66</td></tr></table></body></html>

Tab.2Comparison of SEBS and PM calculated values at different weather stations   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">临河</td><td colspan="3">磴口</td><td colspan="3">杭锦后旗</td><td colspan="3">五原</td><td colspan="3">乌拉特前旗</td></tr><tr><td>SEBS /(mm· d-1)</td><td>PM /(mm· d-1)</td><td>相对 误差 /%</td><td>SEBS /(mm· d-1)</td><td>PM /(mm· d-1)</td><td>相对 误差 /%</td><td>SEBS /(mm· d-1)</td><td>PM /(mm· d-1)</td><td>相对 误差 /%</td><td>SEBS /(mm·</td><td>PM /(mm·</td><td>相对 误差 /%</td><td>SEBS /(mm·</td><td>PM /(mm·</td><td>相对 误差</td></tr><tr><td>5</td><td>4.022</td><td>5.556</td><td>27.61</td><td>4.788</td><td>5.662</td><td>15.44</td><td>4.641</td><td>5.344</td><td>13.15</td><td>d-1) 4.662</td><td>d-1) 5.510</td><td>15.39</td><td>d-1) 4.840</td><td>d-1) 5.836</td><td>17.07</td></tr><tr><td>6</td><td>4.488</td><td>5.684</td><td>21.04</td><td>4.929</td><td>6.278</td><td>21.49</td><td>4.889</td><td>5.742</td><td>14.86</td><td>4.715</td><td>5.573</td><td>15.40</td><td>4.938</td><td>6.519</td><td>24.25</td></tr><tr><td>7</td><td>5.465</td><td>5.790</td><td>5.61</td><td>5.779</td><td>6.978</td><td>17.18</td><td>6.324</td><td>5.792</td><td>9.19</td><td>5.707</td><td>5.597</td><td>1.97</td><td>5.852</td><td>6.592</td><td>11.23</td></tr><tr><td>8</td><td>3.819</td><td>5.094</td><td>25.03</td><td>4.643</td><td>5.081</td><td>8.62</td><td>4.431</td><td>5.152</td><td>13.99</td><td>4.593</td><td>4.957</td><td>7.34</td><td>4.583</td><td>5.801</td><td>21.00</td></tr><tr><td>9</td><td>3.175</td><td>4.256</td><td>25.40</td><td>4.276</td><td>4.503</td><td>5.04</td><td>4.278</td><td>4.465</td><td>4.19</td><td>3.935</td><td>3.894</td><td>1.05</td><td>4.141</td><td>4.512</td><td>8.22</td></tr><tr><td>相对误差</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>平均值</td><td></td><td></td><td>20.94</td><td></td><td></td><td>13.55</td><td></td><td></td><td>11.08</td><td></td><td></td><td>8.23</td><td></td><td></td><td>16.35</td></tr></table></body></html>

3.1.2土地利用分类结果验证以哨兵2号土地利用分类结果作为本研究土地分类参照标准，如图

3a所示。基于Landsat8遥感影像，通过Softmax分类方法得到灌区土地类型分类结果（图3b）。以Softmax作为分类器的土地利用分类结果生成损失曲线与分类混淆矩阵，损失曲线如图4所示。通过分类混淆矩阵进行精度评价，各分类类别的生产者精度和用户精度如表3所示。

![](images/a51fe06c003fdb1f71e2b29f58fb761929f4c8b509a6edc2e907278c7cddccb4.jpg)  
Fig.3Sentinel No.2 classification and Landsat8 classification

![](images/5a4071ccd240933963004233d6dc9af971042868b2f859d63a572d946f3f173b.jpg)  
图3哨兵2号土地分类与Landsat8土地分类  
图4损失曲线Fig.4Loss profile

表2不同气象站点SEBS模型计算值与PM计算值对比  
表3土地利用分类精度评价结果  
Tab.3Land use classification accuracy evaluation results   

<html><body><table><tr><td>类别</td><td>水体</td><td>耕地</td><td>城市 用地</td><td>林地</td><td>荒地</td><td>草地</td></tr><tr><td>水体</td><td>2142</td><td>10</td><td>516</td><td>24</td><td>58</td><td>198</td></tr><tr><td>耕地</td><td>10</td><td>3140</td><td>762</td><td>32</td><td>123</td><td>254</td></tr><tr><td>城市用地</td><td>0</td><td>0</td><td>5 155</td><td>64</td><td>382</td><td>90</td></tr><tr><td>林地</td><td>0</td><td>0</td><td>5</td><td>381</td><td>0</td><td>0</td></tr><tr><td>荒地</td><td>0</td><td>14</td><td>1 029</td><td>39</td><td>7 575</td><td>273</td></tr><tr><td>草地</td><td>0</td><td>3</td><td>62</td><td>32</td><td>54</td><td>421</td></tr><tr><td>分类总数</td><td>2152</td><td>3167</td><td>7 529</td><td>572</td><td>8192</td><td>1236</td></tr><tr><td>生产者精度 (PA/%)</td><td>99.54</td><td>98.83</td><td>78.47</td><td>75.09</td><td>92.47</td><td>76.50</td></tr><tr><td>用户精度 (UA/%)</td><td>67.19</td><td>70.80</td><td>90.42</td><td>66.87</td><td>84.54</td><td>73.61</td></tr><tr><td colspan="7">总体精度（OA）=80.63% Kappa系数（KIA）=0.75</td></tr></table></body></html>

通过损失曲线调整分类学习参数，得到最优分类结果。损失曲线逐渐趋于零，且变化趋势平稳时，可用于本次研究分类评估和图像分类。基于Land-sat8影像土地利用分类结果与哨兵2号分类结果的空间分布基本一致，Softmax作为分类器的总体分类精度为 $8 0 . 6 3 \%$ ,Kappa系数为0.75，分类可信度较高。灌区内林地只分布在道路两侧,导致林地的类别总和数较小且分类精度较低。城市用地中夹杂小面积其他土地类型，导致分类精度降低，

# 3.2SEBS 模型估算 $_ { E T }$ 结果分析

3.2.1日 $E T$ 时间变化特征灌区生长季ET反演结果如图5所示， $E T$ 值从5月开始逐渐上升，7月达到最大值，7—9月逐渐下降。总体呈单峰形分布，峰值出现在7月。整个河套灌区7月日 $E T$ 为$5 . 2 1 \ \mathrm { m m } \ \cdot \ \mathrm { d } ^ { - 1 }$ ,6月与5月的日 $E T$ 分别为4.72$\mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \ 、 4 . 5 2 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \ : , 8$ 月与9月的日 $E T$ 分别为 $4 . 2 7 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \cdot 3 . 5 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$

3.2.2日 $E T$ 空间差异特征结合河套灌区 $E T$ 时空分布图(图5)与土地利用分类图(图3），不同土地类型 $E T$ 随时间也会发生相应变化。灌区生长季内，水体湖区水量充沛，因此5一9月的水体湖区ET值较大，主要集中在乌梁素海、金马湖等。其次耕地ET主要影响因素是人为干预，灌区定期灌溉导致种植作物的耕地区域有充沛的水分供植物蒸腾与土壤蒸发。草地略大于荒地的ET,与荒地相比,草地有来自周边湖区或耕地区灌溉后少量用水、季节性降水所提供的水源补给。荒地含盐量较大且储水能力低，不适宜作物生长，导致长期荒置，ET变化较小，处于极低值，灌区的西南方向邻近磴口县的区域尤为明显。城市区域内一般夹杂小面积林地、水域、草地等用地类型，不同月份的城市用地ET值均处于中等水平，随时间变化不明显。ET高低区域间具有明显的分界，与不同土地类型的边界较一致，表明不同土地类型ET差异明显，所需水资源、土地利用方式也不相同，可以用来指导灌区内水资源管理分配与土地利用规划。

# 3.3不同土地类型ET差异分析

河套灌区受人类活动强烈影响，ET也受很多因素影响，不同的土地类型 $E T$ 也会存在明显差异。为进一步分析不同地物覆盖类型下的 $E T$ 变化规律,将灌区划分为水体、耕地、林地、城市（居民用地、建设用地）、草地和荒地6大类，不同土地类型的面积比例如表4所示，可以看出灌区主要由耕地、草地、荒地组成，占据灌区总面积的 $9 3 \%$ ，水体和林地的面积最小，仅占 $3 \%$ ,城市用地占 $4 \%$ 。

从图6可以看出， $E T$ 值从5月作物生长开始到7月逐渐升高，7一9月逐渐降低，灌区6类土地类型的ET变化趋势基本一致。水体与其他土地类型的下垫面不同，有充足的水分蒸发，因此以乌梁素海为典型代表的水体区域 $E T$ 最大。林地 $E T$ 仅次于水体，土壤水分长期较大，树木不断进行蒸腾蒸发。耕地ET的变化最为明显，6一7月耕地的ET急剧增大，是人为因素对其进行了大面积、水量充足的灌溉所致。草地、城市用地、荒地三者的 $E T$ 变化趋势基本一致,草地与荒地的 $E T$ 值基本相同，草地ET仅略高于荒地 $0 . 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ,两者无外界直接干扰,$E T$ 主要取决于降雨、土壤水分及地下水等。城市用地夹杂不同的土地类型， $E T$ 值仅受降水影响，与草地、荒地的 $E T$ 差异较小。

![](images/42eb1f9d9a5b025114ec7788d2fc2c57192dfd2bc4ac88f58fe4ff7731387b06.jpg)  
图5研究区逐月日蒸散发反演结果  
Fig.5Daily evapotranspiration results for the study area on a monthly basis

表4不同土地利用类型面积比例  
Tab.4Percentage areas of different land use types   

<html><body><table><tr><td>土地利用类型</td><td>水体</td><td>耕地</td><td>城市用地</td><td>林地</td><td>荒地</td><td>草地</td></tr><tr><td>面积比例/%</td><td>1.98</td><td>74.78</td><td>3.94</td><td>0.73</td><td>12.67</td><td>5.90</td></tr></table></body></html>

![](images/ea0f467afc10802d21061f737caf23cf0b76b7f6075847be07bafa49a3de5b99.jpg)  
图6不同土地利用类型蒸散对比 Fig.6Evapotranspiration comparisons for different land use types

# 4结论

本研究基于地表能量平衡系统建立的SEBS 模型，以气象数据及Landsat8遥感影像为源数据，得到内蒙古河套灌区2017年5—9月的日ET估算结果。将蒸渗仪观测数据、涡度相关及波文比实测数据作为实测值，PM模型计算结果作为理论值，对ET反演结果进行变化趋势分析及精度检验。土地利用分类方法Softmax将研究区分为6类，结合模型估算结果,对不同土地类型ET值进行差异分析。主要结论如下：

（1）实测数据和PM计算值对SEBS估算结果精度验证及变化进行趋势分析，估算结果的变化趋势与4种验证数据变化趋势相一致，相对误差在允许范围内，结果对于研究河套灌区的不同土地类型及区域ET具有较高应用价值。

（2）灌区生长季内日ET呈单峰形变化。ET值5月开始逐渐增大，到7月达到最大值，日ET值达

$5 . 2 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 。7-9月逐渐减小,9月日ET值最小,为 $3 . 5 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 。 $E T$ 值大小随时间变化呈正态分布。

（3）结合灌区土地类型分布与 $E T$ 值空间分布得知，不同土地利用类型的日 $E T$ 大小依次为：水体 $>$ 林地 $>$ 耕地 $>$ 草地 $>$ 城市 $>$ 荒地， $E T$ 值依次为 $: 5 . 0 0 7 \ \mathrm { m m } \ \cdot \ \mathrm { d } ^ { - 1 } \ . 4 . 9 0 4 \ \mathrm { m m } \ \cdot \ \mathrm { d } ^ { - 1 } \ . 4 . 7 4 2 \ \mathrm { m m } \ \cdot$ $\mathrm { d } ^ { - 1 } \ 、 4 . 6 9 4 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \ 、 4 . 6 7 0 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \setminus 4 . 6 4 3 \ \mathrm { m m } \cdot \$ $\textrm { d } ^ { - 1 }$ ， $E T$ 差异值分界与灌区土地类型的分布高度一致。

（4）生长季的不同时间，耕地的 $E T$ 变化趋势与作物生长情况相一致,水体、林地的 $E T$ 长期处于较高值，草地、城市用地与荒地的 $E T$ 较小，且三者的ET值相接近。

# 参考文献(References）:

[1］张荣华,杜君平,孙睿.区域蒸散发遥感估算方法及验证综述 [J].地球科学进展,2012,27（12）:1295-1307.[Zhang Ronghua,Du Junping,Sun Rui.Review of estimation and validation of regional evapotranspiration based on remote sensing[J].Advances in Earth Science,2012,27（12）:1295-1307.]   
[2］宋鑫博.基于MODIS 数据的湖西区地表蒸散发遥感估算[D]. 南京：南京师范大学,2013.［Song Xinbo.Study on Estimation of Evapotranspiration in Western Taihu Area based on MODIS Data [D].Nanjing:Nanjing Normal University,2013.]   
[3］傅国斌,刘昌明.遥感技术在水文学中的应用与研究进展[J]. 水科学进展,2001,12（4）:547-559.[Fu Guobin,Liu Changming.Advances in applications of remote sensing data to Hydrology [J].Advances in Water Science,2001,12(4）:547-559.]   
[4]王卫光,李进兴,魏建德,等.基于蒸散发数据同化的径流过程 模拟[J].水科学进展,2018,29(2）:159-168.[Wang Weiguang, Li Jinxing,Wei Jiande,et al.Runoff simulation by Hydrological Model based on the assimilated evapotranspiration[J].Advances in Water Science,2018,29(2):159-168.]   
[5］王瑶.基于 SEBS 模型的黑河中游作物需水量研究[D].兰州： 兰州大学,2012.［Wang Yao.Research on Crop Water Requirement in the Middle Reaches of Heihe River Basin based on SEBS Model［D].Lanzhou:Lanzhou University,2012.]   
[6]张圆,郑江华,刘志辉,等.基于Landsat8 遥感影像和 SEBS 模 型的呼图壁县蒸散量时空格局分析[J].生态科学,2016,35 (2）:26 -32.［Zhang Yuan,Zheng Jianghua,Liu Zhihui,et al. Spatial and temporal distribution of evapotranspiration in the Hutubi County based on Landsat8 data and SEBS Model[J].Ecological Science,2016,35(2):26-32.]   
[7］张薇,葡文静,王贵玲.基于遥感反演河套平原区域蒸发蒸腾 量研究［J].遥感信息,2009,10(6）:28-31,42.[ZhangWei, Lin Wenjing,Wang Guiling.Study on the distribution of the real e

vapotranspiration in Hetao Plain based on remote sense[J].Re

mote Sensing Information,2009,10(6) :28-31,42.]   
[8］杨雨亭,尚松浩.双源蒸散发模型估算潜在蒸散发量的对比 [J].农业工程学报,2012,28（24）:85-91.[Yang Yuting, Shang Songhao.Comparison of dual-source evapotranspiration models in estimating potential evaporation and transpiration[J].Transactions of the Chinese Society of Agricultural Engineering,2012,28 (24):85 -91.]   
[9］闫浩芳,史海滨,薛铸,等.内蒙古河套灌区 $E T _ { 0 }$ 不同计算方法 的对比研究[J].农业工程学报,2008,24（4）：103－106.[Yan Haofang,Shi Haibin,Xue Zhu,et al.Comparison of estimating $E T _ { 0 }$ （204号 with different methods in Hetao Irrigation District in Inner Mongolia[J].Transactions of the Chinese Society of Agricultural Engineering,2008,24(4）:103-106.]   
[10］张圣微,张鹏,张睿,等.科尔沁沙地典型区生长季蒸散发估算 及其变化特征［J].水科学进展,2018,29（6）：768－778. [Zhang Shengwei,Zhang Peng,Zhang Rui,et al. Estimation of growing season evapotranspiration and its variation in a typical area of Horqin Sandy Land[J].Advances in Water Science,2018,29 (6) :768 -778.]   
[11］王万同.基于遥感技术的区域地表蒸散估算研究[D].开封： 河南大学,2012.［Wang Wantong.Research on Regional Land Surface Evaportranspiration Estimation based on Remote Sensing Technology[D].Kaifeng:Henan University,2012.]   
[12］李根.蒸散对气候和土地利用/覆盖变化的响应及模型异质性 误差订正[D].南京：南京信息工程大学,2017.［LiGen.The Response of Evaportranspiration to Changes in Land use/Land Cover and Climate and the Model Heterogeneity Error Correction [D].Nanjing:Nanjing University of Information Science & Technology,2017.]   
[13］白亮亮.基于多源遥感数据的灌区农田蒸散发和土壤熵情反 演及应用[D].北京：中国水利水电科学研究院,2017.［BaiLiangliang. Inversion and Application of Agriculture Evaportranspiration and Soil Moisture in Irrigation District based on Multi-source Remote Sensing Data[D].Beijing:China Institute of Water Resources and Hydropower Research,2017.]   
[14］郝珈纬.基于 SEBS 模型的邯郸市蒸散发研究[D].邯郸：河北 工程大学,2O18.［Hao Jiawei. Study on Evapotranspiration based on SEBS Model in Handan[D].Handan:Hebei University of Engi

neering,2018.]

[15］张晓玉.基于SEBS模型的艾比湖流域蒸散发估算及时空变化 研究［D].乌鲁木齐：新疆大学，2018.［ZhangXiaoyu.Estimation of Temporal and Spatial Changes of Evapotranspiration in the Ebinur Lake Basin based on SEBS Model[D]. Urumqi: Xinjiang University,2018.]

[16]Peng Gong,Xuecao Li,Wei Zhang.4O- Year（1978 -2017）human settlement changes in China reflected by impervious surfaces from satelite remote sensing[J]. Science Bulletin,2019,64（11）: 756-763.   
[17］卢霞,赵倩,林雅丽,等.大丰麋鹿自然保护区土地利用/覆盖 变化监测研究[J].淮海工学院学报（自然科学版）,2018,27 (3）:74-81.[Lu Xia,Zhao Qian,Lin Yali,et al.Research on the land use/cover change monitoring in Dafeng Elk Nature Reserve [J]. Journal of Huaihai Institute of Technology(Natural Science Edition),2018,27(3):74 -81.]   
[18］郝珈纬,张安兵,王贺封,等.高分一号与Landsat8影像反演的 参考蒸散发研究[J].测绘科学，2018，43（11）：103-110，124. [Hao Jiawei,Zhang Anbing,Wang Hefeng,et al. Inversion study on reference evapotranspiration based on GF-1 and Landsat8 images[J].Science of Surveying and Mapping,2018,43（11）:103 - 110,124. ]   
[19］栾晓波.基于水文过程的作物生产水足迹量化方法研究［D]. 北京：中国科学院大学（中国科学院教育部水土保持与生态环 境研究中心）,2O18.［Luan Xiaobo.Researchon Quantitative Method of Crop Production Water Footprint based on Hydrological Process[D].Beijing: University of Chinese Academy of Sciences (Chinese Academy of Sciences and Ministry of Education Research Center of Soil and Water Conservation and Ecological Environment）,2018.]   
[20]Vinukollu RK,Wood EF,Ferguson CR,et al.Global estimates of evapotranspiration for climate studies using multi-sensor remote sensing data: Evaluation of three process-based approaches [J]. Remote Sensing of Environment,2011,115(3）:801-823.   
[21］孙丽,宋长春.三江平原典型沼泽湿地蒸散发估测[J].应用生 态学报,2008,19(9）:1925-1930.[Sun Li,Song Changchun. Estimation of evapotranspiration from a typical marsh in Sanjiang Plain[J].Chinese Journal of Applied Ecology,2008,19（9）: 1925 -1930.]

# Estimation and variability of evapotranspiration for different land types during the growing season in the Hetao Irrigation District

WANG Yan-xin'，LI Rui-ping'，LI Xia-zi² (1.WaterCoseancyndCilgelingerogoliiculualUersitytergn; 2.Insititueof Meteorological Research of Inner Mongolia,Hohhot O1oo51,Inner Mongolia,China)

Abstract：To reveal the diferences inevapotranspiration（ET）across diferent land types in the irrigation districts,the single-day $E T$ during the 2O17 growing season in the Hetao Irrigation District was estimated based on the surface energybalance system（SEBS）model,meteorological data,remote sensing images,and landuseclassification results for the irrigation districts.The SEBS model accuracy was verified using the measured $E T$ data and the calculated values obtained using the United Nations Food and Agriculture Organization Penman-Monteith（PM) model.The objective of this study was to analyze the temporal and spatial changes in $E T$ in the irrigation area and the differences in $E T$ across different land types.The results showed that（1） the average relative errors obtained based on the PM model,eddy covariance,Bowen ratio-energy balance system,and micro-lysimeter observation data were $1 4 . 0 3 \%$ ， $1 8 . 3 4 \%$ ， $1 4 . 9 3 \%$ ,and $1 6 . 6 6 \%$ ,respectively.The SEBS model exhibited a high application potential for studying the $E T$ across the Hetao Irrigation District.（2）During the growing season,the daily $E T$ values in the irrigation area exhibited the following relation：July $>$ June $>$ May $>$ August $>$ September.The daily $E T$ in the irrigation area had a unimodal distribution and reached the maximum value of $5 . 2 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ in July. The daily average $E T$ was the lowest in September at $3 . 5 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ .（3）The daily $E T$ values for different land types exhibited the following relation：water $>$ forest $>$ cropland $>$ grassland $>$ urban $>$ bare land. The $E T$ variability in the irrigation area was consistent with the land type.The overall clasificationaccuracyand kappa coeffcient for land use classification were $8 0 . 6 3 \%$ and 0.75,respectively.（4）The $E T$ value for water was the higher during different periods of the growing season；the daily $E T$ reached the maximum value of $6 . 0 3 4 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ in July,whereas the daily average $E T$ was the lowest in September at $4 . 1 7 7 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ . The $E T$ value for forest within the irrigation area was relatively large,with a daily $E T$ of $5 . 9 7 7 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ in July and $4 . 1 4 7 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ in September. The $E T$ value for cropland changed with the growth of the crops,reaching $5 . 8 5 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ during the vigorous growing period and （204号 $3 . 9 5 2 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ during the harvesting period.

Key words:growing season； evapotranspiration; SEBS model; Softmax clasification method; land types； Hetao Irrigation District