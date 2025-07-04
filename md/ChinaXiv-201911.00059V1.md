# WRF云微物理参数化方案对新疆暴雨模拟能力的TS评分分析

丁明月1,2， 王俐俐'，辛渝³，陈勇航}，杨莲梅³，梁倩'，刘琼'，刘統强1

（1．东华大学环境科学与工程学院,上海201620；2．北京金风慧能技术有限公司,北京100176;3．中国气象局乌鲁木齐沙漠气象研究所，新疆 乌鲁木齐830002)

摘要：在中尺度数值模式中,选用不同的参数化方案对降水的模拟和预测效果会有很大影响，合理选择参数化方案可以提高预测准确性。为此,本文使用中尺度预报模式 WRF3.8（weather research and forecasting model，WRF）版本，采用 $3 ~ \mathrm { k m }$ 和 $9 ~ \mathrm { k m }$ 两层嵌套网格,利用 ECMWF（European Centre for Medium Range Weather Forecasts）再分析资料作为初始场和边界条件,对新疆地区4次暴雨过程进行模拟,采用TS（threat score）评分评估了Lin方案、WSM6 方案、Thompson方案和 WDM6方案4种云微物理参数化方案对新疆地区暴雨模拟的适用性。结果表明：Thompson 方案在站点降雨量为小雨 $( 0 . 1 \sim 5 . 0 ~ \mathrm { m m } )$ 和中雨 $( 5 . 1 \sim 1 0 . 0 \ \mathrm { m m }$ )的预报模拟中具有优势,其他3种云微物理参数化方案均在不同程度上存在漏报情况,从相关系数上判断,Thompson方案模拟效果略优于其他方案,适用于多小雨、中雨的新疆地区,但4种云微物理参数化方案在大到暴雨降水等级的预报效果都不是很好,这也正是WRF模式在新疆地区需要改进的地方。

关键词：WRF；TS评分；云微物理；参数化方案；暴雨；模拟能力；新疆

强降水一直是中国最主要的灾害之一，位于干旱、半干旱地区的新疆发生强降水事件的概率虽小，但由于新疆地区生态环境脆弱，植被覆盖度小，河流、下垫面渗透力差，一旦发生强降水事件就会造成很大的损失。根据新疆气候中心气候影响评价报告显示，近10a来，新疆地区由于强降水所造成的灾害占当地气象灾害的 $3 6 \%$ ，对经济、人民生活造成巨大影响[1]。新疆地区的暴雨问题受到了国内科学家以及预报员的普遍关注，对于暴雨范围、强度的预报也一直是科研以及预报业务的重点，由于降水受到不同的微物理过程、动力过程的影响，在数值模式中选择合适的参数化方案可以为提高预报准确度提供参考。

在目前的模式预报降水中，普遍认为积云对流参数化过程对降水的影响最为显著，但在某些降水过程中，积云对流参数化过程并不起主要作用，如在大尺度强迫的层状云降水中，云微物理过程对降水总量起主要作用。张大林等[2-4]提出云微物理过程是大气中重要的湿物理过程之一，对模式模拟效果有着较大的影响。云微物理过程以及大气中其他相互作用过程是模式模拟存在偏差的主要原因，不同的云微物理参数化方案模拟降水效果不一，在实际的降水模拟预报中，选择何种方案最为合理需要深入研究。对此，国内外学者进行了大量研究,李安泰等[5]采用不同云微物理过程来模拟舟曲 ${ } ^ { \cdot } 8 \cdot 8 { } ^ { \cdot }$ 暴雨过程，认为采用不同云微物理参数化方案模拟的结果存在较大差异，而Kessler方案模拟的结果最好。廖镜彪等[采用不同微物理和积云对流参数过程对珠江三角洲一次暴雨的研究表明，Lin方案能够较好地模拟出降水的强度及落区，其他方案会出现明显的强度偏弱以及雨带较大的位置偏差。黄海波等[7对新疆2009 年5月25—26日大尺度暴雨过程进行了WRF模拟，认为不同微物理参数化方案在不同等级的降水中对降水的模拟效果区别较大，其中WSM3、Lin、WSM5方案分别在中到大雨、小雨、暴雨时模拟效果最好，Kessler方案则在所有方案中表现最差。以上研究结果均表明，不同的云微物理参数化方案的选择对降水的模拟和预报有重要影响。

本文主要通过新疆的4次典型暴雨个例，利用TS 评分标准，分析不同云微物理方案在新疆区域的适用性，为新疆业务预报系统选取合理的微物理方案提供参考。

# 1中尺度数值模式WRF

# 1.1 WRF模式简介

WRF（weather research and forecasting model）是先进中小尺度数值预报模式，包括NMM（nonhydro-static mesoscale model）和 ARW（advanced researchWRF)两个版本，是美国为了解决模式过多、不统一等问题，组织NCAR（国家大气研究中心）、NCEP（国家环境预报中心）EMC（环境仿真中心）、MMM（中小尺度气象处）CAPS（俄克拉荷马大学风暴分析和预测中心)和FRD（预测系统实验室预测研究办公室)与其他部门一起开发的[3]

# 1.2 微物理参数化方案

WRF模式包含14种微物理过程参数化方案，根据不同方案所考虑的水成物的类型，可以将微物理过程参数化方案分为单参数方案、不完全双参数方案和完全双参数方案。本文选取Lin、WSM6方案为单参数代表，Thompson、WDM6方案为双参数代表[3]

1.2.1Lin方案[8] 该方案考虑了云水、雨、雪、云冰和霰这5种水的模式，Lin方案在云微物理参数化方案发展过程中有着重要作用，是WRF中一个比较全面的方案，高分辨率实时数值预报也可以很好地应用。

1.2.2 WSM6方案[9] WSM6方案是由Hong等[10]提出的，该方案的不同之处在于不使用温度，而是根据冰的质量来判断冰粒子的浓度。WSM6方案对水汽、云水或云冰、雨或雪进行预报，以冰点为分界线，低于冰点的为云冰和雪，高于冰点的为云水和雨，对包含冰过程的有较高的计算效率，可以在业务操作中使用。

1.2.3Thompson 方案[11] 该方案改进于Reisner方案（1998年），主要针对冻雨事件的预测和一套微物理方案的设计，以提高飞机的安全性，通常用于高分辨率数值模拟[3]。

1.2.4 WDM6 方案[10] WDM6方案是在WSM6的基础上发展而来，除了预报与WSM6相同的云、冰、雨、雪、水汽和霰这6类水相变量以外，还包括云凝结核、云水和雨水的粒子数浓度，除此之外，WDM6还用来研究气溶胶对降水、云性质的影响

# 2资料选取与方法介绍

# 2.1 个例选取

选取新疆地区地面自动观测场2015—2016年$\AA 6 \mathrm { ~ h ~ }$ 累计降水达到暴雨( $> 2 4 ~ \mathrm { m m }$ )的天气过程，共计76个，在这76个天气过程中选取了4次短时强降雨的暴雨过程。

# 2.2 天气过程简介

图1为4个个例在模式初始时刻（UTC）500hPa 高度场，Case1（2015年6月14—15日）是一次中亚低涡降水过程，受到位于 $5 0 ^ { \circ } \sim 5 5 ^ { \circ } \mathrm { N } , 6 5 ^ { \circ } \sim 8 0 ^ { \circ }$ E 的中亚低涡的影响,在北疆大部、天山山区出现小到中雨，伊犁河谷东南部、昌吉州东部出现大到暴雨，天池出现大暴雨。Case2（2015年6月27—28日)低涡中心位于 $5 0 ^ { \circ } \sim 6 0 ^ { \circ } \mathrm { N } , 6 5 ^ { \circ } \sim 7 5 ^ { \circ } \mathrm { E }$ ，造成全疆大部出现小到中雨，乌鲁木齐以东的北疆沿天山、天山山区等地的大部地区等地出现大到暴雨。Case3(2015年9月20—21日)2个低涡分别位于 $5 5 ^ { \circ } \sim$ $7 0 ^ { \circ } \mathrm { N } , 7 0 ^ { \circ } \sim 8 0 ^ { \circ } \mathrm { E }$ 和 $3 0 ^ { \circ } \sim 4 0 ^ { \circ } \mathrm { N } , 6 0 ^ { \circ } \sim 6 5 ^ { \circ } \mathrm { E }$ ,在2个低涡的共同影响下，北疆大部、天山山区和哈密大部出现小到中雨，其中塔城北部、阿勒泰大到暴雨，塔城大暴雨( $7 2 . 6 \ \mathrm { m m }$ ）。Case4（2016年6月16—17日)受位于 $5 5 ^ { \circ } \sim 6 0 ^ { \circ } \mathrm { N } , 6 5 ^ { \circ } \sim 7 5 ^ { \circ } \mathrm { E }$ 低涡的影响，在北疆大部分地区有小到中雨,伊犁、博州、昌吉州出现大到暴雨。

# 2.3 试验设计

本研究所用模式为WRF3.8版本，采用两层嵌套网格，其中，粗网格区覆盖了整个中亚地区，水平分辨率为 $9 ~ \mathrm { k m }$ ,格点数为 $5 5 0 \times 4 6 0$ ,记为D01;细网格区覆盖了新疆地区，水平分辨率为 $3 ~ \mathrm { k m }$ ,格点数为 $6 5 8 \times 6 2 2$ ，记为D02。垂直方向为38层，模式层顶为 $5 0 \ \mathrm { h P a }$ ,积分步长为 $6 0 \mathrm { ~ s ~ }$ 。模拟区域如图2所示。采用每 $6 \mathrm { ~ h ~ } 1$ 次，空间分辨率为 $0 . 7 5 ^ { \circ } \times 0 . 7 5 ^ { \circ }$ 的ECMWF（欧洲中期天气预报中心)的再分析资料作为初始场和侧边界条件，使用WRF中尺度数值

![](images/24243dd955d51bf309bfb9b686152b88b192ed6b4b38a41eb43dcf4d4cacee92.jpg)  
图14个个例模式初始时刻 $5 0 0 ~ \mathrm { { h P a } }$ 天气形势图

![](images/f8c3e3d8f013705e188874730dcdd0dd7fc42536b5d50582c82fd15314c2bc6f.jpg)  
Fig.1 $5 0 0 ~ \mathrm { { h P a } }$ weather chart for four cases at model initial moment   
图2 WRF模式模拟区域  
Fig.2The model domains

模式进行模拟。

为了对比单参数Lin、WSM6和双参数Thompson与WDM6方案对新疆地区短时强降雨模拟的差异，除了使用不同的云微物理参数化方案外，其余的物理参数化方案设置完全一致。模式过程采用ACM2边界层方案[12]、RRTM长波辐射方案、Dudhia 短波辐射方案[13]、Revised MM5 与 Monin-Obukhov 近地层方案、Noah陆面过程方案，仅在D01使用Kain-Fritsch积云对流参数化方案[14-16]。设置详见表1。

表1参数化方案设置  
Tab.1 Design of the parameterization scheme   

<html><body><table><tr><td>物理过程</td><td>Case1</td><td>Case2</td><td>Case3</td><td>Case4</td></tr><tr><td>积云对流方案</td><td>D01:Kain-Fritsch D02 : none</td><td>1</td><td>1</td><td>1</td></tr><tr><td>边界层方案</td><td>ACM2</td><td>1</td><td>1</td><td>1</td></tr><tr><td>云微物理方案</td><td>Lin</td><td>WSM6</td><td>Thompson</td><td>WDM6</td></tr><tr><td>长波辐射方案</td><td>RRTM</td><td>1</td><td>1</td><td>1</td></tr><tr><td>短波辐射方案</td><td>Dudhia</td><td>1</td><td>1</td><td>1</td></tr><tr><td>近地层方案</td><td>Revised MM5 Monin-Obukhov</td><td>1</td><td>1</td><td>1</td></tr><tr><td>陆面过程方案</td><td>Noah</td><td>1</td><td>1</td><td></td></tr></table></body></html>

# 3模拟结果分析

为了了解模式模拟降水在新疆区域的总体性能，利用区域自动站观测降水进行评估。从图3a可以看出，Case1中模式经过 $6 \mathrm { ~ h ~ }$ 的时间后，4种云微物理参数化方案能够较好的再现降水过程，尤其是$6 \sim 1 8 \mathrm { ~ h ~ }$ 模拟降水趋势与观测十分相似，而 $1 8 \sim 2 4 \mathrm { ~ h ~ }$ 的模拟结果与观测偏差较大，Case3与Case1类似。与此相反，Case2与Case4在整个模拟期间没有相对集中的相似时间区间，这可能是输入的初始场和侧边界条件与实际情况有偏差。根据以上情况，对4个个例的降水场进行比较，选用开始模拟后 $6 \sim 1 8 \mathrm { ~ h ~ }$ 的累积降水场进行分析。

为了定量评估模拟效果，本文采用TS评分作为评价标准，进行小雨、中雨、大到暴雨的检验分析。TS 评分是目前使用较多的评估模式降水预报水平的标准之一，本文将模式模拟的结果距离反比插值到新疆地区区域自动站，然后对模拟结果做统计检验。

![](images/2f217e8934b9d1ee5097c3a98a46a6033e2bf5ec46612ec0fc601e553187e581.jpg)  
图34个个例区域自动站及4种云微物理参数化方案每小时降水量时间序列 Fig.3Time series of hourly precipitation at theautomatic stationsand in four kinds of cloud microphysical parameterization schemes for four cases

TS 评分的公式为[17]：

$$
\mathrm { T S } = { \frac { N _ { A } } { N _ { A } + N _ { B } + N _ { C } } }
$$

式中： $N _ { _ A }$ 为预报正确的站点数量； $N _ { _ B }$ 为空报的站点数量； $N _ { c }$ 为漏报的站点数。TS评分反映了预报降水位于某一等级的准确率，TS评分的值介于 $0 \sim 1$ 之间，TS评分的值越接近1代表其预报效果越好，相反，越接近0代表预报效果越差。

由于新疆位于干旱、半干旱地区，中国气象局制定的中国降水量级标准对于新疆地区来说过高，因此，新疆气象工作者针对新疆气候特点提出了适合本地区的降水量级标准[18]。本文结合新疆地区12h 累计降水标准,将 $0 . 1 \sim 5 . 0 ~ \mathrm { m m }$ 的降水称为小雨，$5 . 1 \sim 1 0 . 0 \ \mathrm { m m }$ 的降水称为中雨,大于 $1 0 . \mathrm { ~ 1 ~ } \mathrm { m m }$ 的大雨和暴雨统一称为大到暴雨。

从图 $\mathrm { 4 a }$ 可以看出,Thompson 方案在小雨和中雨的预报效果最好，其它3种方案均有不同程度的漏报。图4b中Thompson方案在小雨的预报效果比较好，WSM6在中雨的预报效果最好，由于网格过粗，Lin方案中的少量中雨和大雨在插值的过程中被略过，导致Lin方案的中雨和大到暴雨TS评分为0。4种云微物理参数化方案均对小雨的预报效果最好，中雨其次，大到暴雨的模拟效果最差。

由图5a中可以看出，Thompson方案在小雨预报效果最好，Thompson方案和WSM6方案在中雨的模拟效果最好。图5bThompson方案的小雨和中雨预报效果最好。该个例整体模拟效果不好，4种参数化方案均在小雨的预报上相对较好。

![](images/e3b9b8542c17f3852ec565ac04c7f7cf348d301c865dd891c28198d2cf380f0f.jpg)  
注：(a)使用4种参数化方案模拟结果中D02网格结果,D02网格分辨率为 $3 ~ \mathrm { k m }$ ;(b)使用4种参数化方案模拟结果中D01网格结果，D01网格分辨率为 $9 ~ \mathrm { k m }$ 。下同。

![](images/c8bace2b634934670ae028d5b426fcfc2dde1fd78425de2614cb08b34d710406.jpg)  
Fig.4TSof 12-hour accumulated precipitation in four cloud microphysical parameterization schemes from O0:00 UTC to 12:00 UTC on June 15，2015   
图52015年6月28日00：00—12:00的4种云微物理参数化方案 $^ { 1 2 \mathrm { ~ h ~ } }$ 累积降水TS 评分Fig.5TSof12-hour accumulated precipitation in four cloud microphysical parameterization schemes from O0:00 UTCto 12:00 UTC on June 28，2015

![](images/ab1088de3266849735b9ac2b471a634ceeff5260b992b25a916b2aae2ef80c9a.jpg)  
图42015年6月15日00：00—12：00的4种云微物理参数化方案 $^ { 1 2 \mathrm { ~ h ~ } }$ 累积降水TS 评分  
图62015年9月21日00:00—12:00的4种云微物理参数化方案 $^ { 1 2 \mathrm { ~ h ~ } }$ 累积降水 TS 评分Fig.6TSof 12-hour accumulated precipitation in four cloud microphysical parameterization schemes fromO0:00 UTCto 12:00 UTC on September 21，2015

图6为2015年9月21日00：00—12：00的4种云微物理参数化方案 $^ { 1 2 \mathrm { ~ h ~ } }$ 累积降水TS评分结果。该个例整体预报效果较好，尤其在大到暴雨的预报上，TS评分高于0.8。从 $3 ~ \mathrm { k m }$ 分辨率结果（图6a)看，各方案在小雨的预报差别不大，效果最好的是Lin方案，WSM6方案在中雨的模拟上优于其他方案,Thompson方案对大到暴雨的预报最理想。从$9 ~ \mathrm { k m }$ 分辨率结果(图6b)看，可以得出与 $3 ~ \mathrm { k m }$ 分辨率相同的结论。

图7为2016年6月17日00：00—12：00的4种云微物理参数化方案 $1 2 \mathrm { ~ h ~ }$ 累积降水TS评分结果。与Case1和Case2一样，4种云微物理参数化方案均对小雨的预报效果最好，中雨其次，大到暴雨的模拟效果最差。从 $3 ~ \mathrm { k m }$ 分辨率结果（图7a）看，Thompson方案对小雨的预报上效果最好，Lin方案在中雨和大到暴雨上的预报效果较好，从 $9 ~ \mathrm { k m }$ 分辨率结果（图7b）上看，Thompson方案在小雨和中雨上的预报效果最好。

为了综合评价不同的云微物理参数化方案对新疆地区暴雨个例的模拟效果，本文将4个个例模拟的 $0 { : } 0 0 { - } 1 2 { : } 0 0$ 共 $^ { 1 2 \mathrm { ~ h ~ } }$ 累计降水插值到区域自动站上，求出1185个站点的观测和模拟结果的相关系数，结果如表2。相关系数代表了模拟结果与实际观测结果之间的偏离程度，相关系数越大，代表模拟结果与实际值越接近。可以看出，平均TS评分较低的个例其相关系数也较低，不同个例间模拟结果与实测的相关系数差异较大，即TS评分较高的个例模拟结果也较好，不同个例之间模拟效果有较大差异，但总体来说,Thompson方案模拟效果略优于其他方案。

云微物理参数在中尺度数值模式中，包含霰粒子的方案主要适用于热带降雨（如WDM6），包含雹粒子的参数化过程主要用于实现中高纬深对流云降水过程（如Thompson 方案等）[18]，而新疆地区降水云多为深对流云和雨层云，本文所得结论Thompson方案更适用于新疆暴雨。

![](images/d9524c247ac34100371d9f9c720aca6668a9b9c1efc791e0dc4b7a4ddddcbae9.jpg)  
图72016年6月17日00：00—12：00的4种云微物理参数化方案 $^ { 1 2 \mathrm { ~ h ~ } }$ 累积降水TS评分Fig.7TS of 12-hour accumulated precipitation infour cloud microphysical parameterization schemes fromO0:00 UTCto 12:00 UTC on June 17,2016

表24种云微物理参数化方案模拟的 $\mathbf { 1 } 2 \textbf { h }$ 累计降水与区域自动站实况的相关系数表 Tab.2Correlationcoefficients between the simulatedand observed values of precipitation in four cloud microphysical parameterization schemes   

<html><body><table><tr><td rowspan="2">过程个例</td><td colspan="8">云微物理参数化方案</td></tr><tr><td colspan="4">3 km分辨率</td><td colspan="4">9 km分辨率</td></tr><tr><td></td><td>Lin</td><td>WSM6</td><td>Thompson</td><td>WDM6</td><td>Lin</td><td>WSM6</td><td>Thompson</td><td>WDM6</td></tr><tr><td>Case1</td><td>0.16</td><td>0.25 *</td><td>0.25 *</td><td>0.19</td><td>0.36</td><td>0.35</td><td>0.42 *</td><td>0.36</td></tr><tr><td>Case2</td><td>0.02</td><td>0.02</td><td>0.05*</td><td>0.03</td><td>0.02</td><td>0.05</td><td>0.05 *</td><td>0.04</td></tr><tr><td>Case3</td><td>0.75</td><td>0.75</td><td>0.76</td><td>0.78 *</td><td>0.71</td><td>0.71</td><td>0.72</td><td>0.76 *</td></tr><tr><td>Case4</td><td>0.19</td><td>0.22 *</td><td>0.21</td><td>0.19</td><td>0.26</td><td>0.26</td><td>0.29 *</td><td>0.26</td></tr></table></body></html>

注：黑色加粗带 $*$ 为最优方案;黑色加粗不带 $\ast$ 为最差方案。

从方案中水成物的粒子谱分布形式看，单参数方案固定截距 $N _ { 0 }$ ，使谱形的变化只取决于斜率 $\lambda$ ，为了提高粒子谱的自由度，双参数方案引入了数浓度方程，使谱形由截距 $N _ { 0 }$ 和斜率 $\lambda ~ 2$ 个参数决定，与自然变化更为接近，从而更为合理的模拟云和降水的物理过程，这与本文所得结论一致。

# 4结论

为比较不同云微物理参数化方案对降水的模拟效果，本文使用WRF3.8版本，采用两层嵌套网格，粗网格水平分辨率为 $9 ~ \mathrm { k m }$ ,细网格水平分辨率为3$\mathrm { k m }$ ,对4个不同的个例进行了分析，得出以下结论：

（1）从4个个例的每小时降水量看，中尺度天气模式WRF在进行 $2 4 \mathrm { ~ h ~ }$ 模拟时,6—18h的模拟结果相对贴近实测。

（2）在同一分辨率下，Thompson方案在小雨（号 $( 0 . 1 \sim 5 . 0 ~ \mathrm { m m } )$ )和中雨 $( 5 . 1 \sim 1 0 . 0 \ \mathrm { m m } )$ 的预报模拟中具优势，其他3种云微物理参数化方案均在不同程度上存在漏报情况，从整体上看，4个方案在大到暴雨的预报效果上不如中雨与小雨的预报效果。

（3）TS评分较高的个例模拟结果也较好，个例之间模拟效果有较大差异。从相关系数来判断，Thompson方案模拟效果略优于其他方案。

由于新疆地区降水偏少，最常出现小雨和中雨，而Thompson方案在小雨和中雨的降水等级预报效果较好，适用于新疆地区，但4种方案在大到暴雨降水等级的预报效果都不是很好，这也正是WRF模式在新疆地区需要改进的地方。

# 参考文献(References）：

[1]谢泽明,周玉淑,杨莲梅.新疆降水研究进展综述[J].暴雨灾害,2018,37(3）:204-212.[Xie Zeming,Zhou Yushu,Yang Li-anmei.Review of study on precipitation in Xinjiang[J].TorrentialRain and Disasters,2018,37(3):204-212.]  
[2]张大林.各种非绝热物理过程在中尺度模式中的作用[J].大气科学,1998,22(4）:548-561.[ZhangDalin.Rolesof variousdiabatic physical processes in mesoscale models[J].Chinese Jour-nal of Atmospheric Sciences,1998,22(4）:548-561.]  
[3］徐洪雄.互旋过程双台风相互作用及其环境主体水汽流影响[D].南京：南京信息工程大学,2013.［Xu Hongxiong.BinaryTropical Cyclone during Their Mutual Rotation and Its Response toEnvironmental Moisture Transport[D].Nanjing:Nanjing Universityof Information Science & Technolgy,2013.]  
[4]Zhang DL,Liu YB,Yau M K.A multiscale numerical study ofHurricane Andrew（1992）.Part V.Inner-core thermodynamics[J].MonthlyWeatherReview,2002,130:2745-2763.  
[5]李安泰,何宏让.不同云微物理参数化方案对舟曲" $8 \cdot 8$ ”暴雨过程模拟的影响[J].气象与减灾研究，2011，34（3）：9-16.

[Li Antai,He Hongrang.Impact of different cloud microphysical parameterization schemes on the numeric simulation result of“8· 8”rainstorm process in Zhouqu[J].Meteorology and Disaster Reduction Research,2011,34(3）:9-16.]

[6]廖镜彪,王雪梅,夏北成,等.WRF 模式中微物理和积云参数化 方案的对比试验[J].热带气象学报,2012,28（4）:461－470. [Liao Jingbiao,Wang Xuemei,Xia Beicheng,etal.The effects of diferent physics and cumulus parameterization schemes in WRF on heavy rainfall simulation in PRD[J].Journal of Tropical Meteorology,2012,28(4) :461-470.]   
[7］黄海波,陈春艳,朱雯娜.WRF 模式不同云微物理参数化方案 及水平分辨率对降水预报效果的影响[J].气象科技,2011,39 (5）:529-536.[Huang Haibo,Chen Chunyan,Zhu Wenna.Impacts of diferent cloud microphysical processes and horizontal resolutions of WRF model on precipitation forcast efect[J]. Meteorological Science and Technology,2011,39(5）:529-536.]   
[8]Lin Y L,Farley R D,Orville H D.Bulk parameterization of the snow field in a cloud model[J].Journal of Climate and Applied Meteorology,1983,22(6）:1 065 -1 092.   
[9]Lim K S S,Hong S Y.Development of an efective double-moment cloud microphysics scheme with prognostic cloud condensation nuclei（CCN）forweather and climatemodels[J].MonthlyWeather Review,2010,138:1 587 -1 612.   
[10]Hong SY,Lim KSS,LeeYH,etal.Evaluation of the WRF double-moment 6 -class microphysics scheme for precipitating convection[J].Advances in Meteorology,2014,2 010:707253,doi:10. 1155/2010/707253.   
[11]Thompson G,Field PR,Rasmussen R M,et al.Explicit forecasts of winter precipitation using an improved bulk microphysics scheme. Part II. Implementation of a new snow parameterization[J].Monthly Weather Review,2008,136:5 095-5 115.   
[12]Hu X M,Nielsengammon JW,Zhang F.Evaluation of three planetary boundary layer schemes in the WRF model[J].Journal of Applied Meteorology and Climatology,2010,49:1 831-1 844.   
[13］Dudhia J. Numerical study of convection observed during the winter monsoon experiment using a mesoscale two-dimensional model[ J]. Journal of Atmospheric Sciences,1989,46(20）:3 077-3107.   
[14]Kain JS,Fritsch JM. Convective parameterization for mesoscale models：The Kain-Fritsch scheme[J]. Meteorological Monographs, 1993,24(46) :165 - 170.   
[15]Kain JS.The Kain-Fritsch convective parameterization:An update [J]. Journal of Applied Meteorology,2004,43:170 -181.   
[16]Kain JS,WeissSJ,Bright DR,et al.Some practical considerations regarding horizontal resolution in the first generation of operational convection-allowing NWP[J].Weather and Forecasting, 2008,23:931- 952.   
[17］肖开提·多莱特.新疆降水量级标准的划分[J].新疆气象， 2005（3）:7-8.[Xiaokaiti Duolaite.Formulation of precipitation intensitystandardof Xinjiang[J].Bimonthly of Xinjiang Meteorology,2005(3):7 -8.]

[18]于晓晶，于志翔，唐永兰，等.不同云微物理方案对新疆冷锋暴 雪的预报影响分析[J].暴雨灾害，2017，36（1）：33-41.［Yu Xiaojing,Yu Zhixiang,Tang Yonglan,et al. Influence of different cloud microphysical schemes on forecasts of a cold-font snowstorm in Xinjiang[J].Torrential Rain and Disasters,2017,36(1）:33- 41.]

# TS Score of WRF Cloud Microphysical Parameterization Scheme to the Simulation Capability of Precipitation in Xinjiang

DING Ming-yue $^ { 1 , 2 }$ ，WANG Li-li1， XIN ${ \mathrm { Y u } } ^ { 3 }$ ，CHEN Yong-hang1， YANG Lian-mei³, LIANG Qian'，LIU Qiong'，LIU Tong-qiang' (1. College of Environmental Science and Enginering,Donghua University,Shanghai 2Ol62o,China;   
2.Beijing Jinfeng Huineng Technology Co.,Ltd,Beijing 10o176,China;   
3.Institute of Desert Meteorology,China MeteorologicalAdministration,Urumqi 83oo02,Xinjiang,China)

Abstract：In the weather research and forecasting model,different parameterization schemes affect significantly the precipitation prediction.It can improve the prediction accuracy to choose the appropriate parameterization schemes.In this paper,the3.8 version of WRF（weather research and forecasting model）was used to simulate four precipitation cases in Xinjiang using $3 ~ \mathrm { k m }$ and $9 ~ \mathrm { k m }$ two-layer nested grids and ECMWF（European Centre for Medium Range Weather Forecasts）reanalysis data as the initial fieldsand boundary conditions.The applicability of Lin scheme,WSM6 scheme,Thompson scheme and WDM6 scheme to precipitation simulation in Xinjiang is evaluated by TS（threat score） score.The results showed that the Thompson scheme was of an advantage in predicting light rain ( $\mathrm { 0 . 1 - 5 . 0 ~ m m }$ ）and moderate rain( $\left. 5 . 1 - 1 0 . 0 \ \mathrm { m m } \right.$ ）,and there were the missing forecasts on rainfall by otherthree schemes of cloud microphysical parameterization.According tothecorrelation coefficient,the simulation accuracy of Thompson scheme was slightly higher than that of other schemes,this scheme was suitable for Xinjiang, butthe four kinds of schemes were not very good in forecasting heavy precipitation,sothe schemes need to be improved for Xinjiang.

Key words:WRF；threat score；cloud microphysics；parameterization scheme；precipitation；simulation capability ； Xinjiang