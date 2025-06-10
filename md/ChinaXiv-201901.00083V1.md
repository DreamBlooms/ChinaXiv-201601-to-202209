# 基于Logistic回归模型的内蒙古多伦县土地沙漠化驱动力分析

阿如旱，都来，盛艳，阿斯那(内蒙古农业大学沙漠治理学院,内蒙古呼和浩特010011)

摘要：以内蒙古多伦县1960、1975、1987、1995、2000、2005年的土地沙漠化矢量数据及2010 年2015年的遥感影像、地形图为主要数据来源，运用NEVI5.0和ArcGIS10.2软件提取8个时期土地沙漠化空间信息,划分为轻度沙漠化、中度沙漠化、重度沙漠化、严重沙漠化等不同类型进行时空分异特征分析。通过选取海拔高程、年均气温、降水量、平均风速、牲畜数量、第一产业、居民点距离等统计数据，运用Logistic 回归模型定量分析了土地沙漠化动力机制，为京津风沙源区防治土地沙漠化,改善生态环境提供科学理论依据。结果表明：1960—2015年间多伦县土地沙漠化面积呈减少趋势,其中1960—1995年间呈发展趋势,1995—2015年间呈减少趋势;1960—1995年间各类土地沙漠化增长的主导因子是第一产业和居民点距离;而在1995—2015年间影响各类土地沙漠化的主导因子是降水量、牲畜数量、第一产业和居民点距离。未来将继续控制牲畜数量、实施土地沙漠化治理政策来逆转土地沙漠化发展。

关键词：土地沙漠化；驱动力；Logistic 回归模型；内蒙古多伦县文章编号： 1000-6060(2019)01-0137-07(0137\~0143)

人口扩张和工业化过程加速带来经济高速发展的同时也导致了水土流失、土地荒漠化、生物多样性减少等生态环境问题日益突出[1]。1977 年联合国荒漠化会议召开以后，“荒漠化”作为一个生态环境问题被世界所公认[2]。我国是世界上受荒漠化危害最严的国家之一[3]。作为荒漠化的一种主要类型，沙漠化（与风蚀活动相关的荒漠化）对我国北方干旱区生态环境和社会经济的影响尤为重要[4]。土地沙漠化是当今世界最为严峻的生态环境问题之_[5]。沙漠化(沙质荒漠化)是干旱、半干旱及部分半湿润地区由于人类不合理经济活动和脆弱环境相互作用而造成土地生产力下降，土地资源丧失，地表呈现类似荒漠景观的土地退化，是荒漠化的一种最重要的类型[6]。土地沙漠化作为极其严重的环境和社会经济问题困扰着当今世界，威胁着人类的生存和发展[7-8],是一种人类活动与自然环境不相协调导致的以风沙活动为主要标志的土地退化过程[9]。在一个区域,如果土壤中水分含量不能支撑一定数量植物正常生长，会造成该地区植物稀疏及土壤中有机质缺乏,最终形成土地沙漠化[10]。深入理解沙漠化过程中驱动力的作用机理，系统评价各驱动因子在沙漠化过程中的相对作用是有效开展沙漠化防治的基础和关键[11]。尽管人类活动和气候变化作为沙漠化过程的两大驱动力已经得到共识，然而由于不同地区土地沙漠化驱动因素不同，同一地区不同时间段土地沙漠化的成因也可能不同，造成了沙漠化过程监测与其原因研究的脱节[12]。因此，土地沙漠化中自然因子与人文因子影响程度的定量分析对阐述在不同时空尺度下土地沙漠化驱动力作用机理及制定土地沙漠化防治措施都有十分重要的意义。内蒙古多伦县位于浑善达克沙地东南端，是以牧为主的农牧交错区，气候干旱、风沙较大[13]。由于土地沙漠化面积的迅速扩大及其程度加剧，严重影响人民生活水平提高和制约着多伦县社会经济可持续发展。利用遥感与地理信息系统技术,提取1960—2015 年的多伦县土地沙漠化信息，运用Logistic回归模型对其土地沙漠化驱动因子进行定量分析，借此为京津风沙源区的研究提供新方法，同时可为多伦县防治沙漠化，改善和恢复生态环境提供科学依据。

# 1研究区概况与研究方法

# 1.1 研究区概况

内蒙古多伦县位于锡林郭勒盟的南端阴山北麓东端,属于京津风沙源区[14],地理坐标在 $1 1 5 ^ { \circ } 3 0 ^ { \prime } \sim$ $1 1 6 ^ { \circ } 5 5 ^ { \prime } \mathrm { E } \lrcorner 4 1 ^ { \circ } 4 5 ^ { \prime } \sim 4 2 ^ { \circ } 3 9 ^ { \prime } \mathrm { N }$ 之间，东与河北省围场县接壤,南与河北省丰宁、沽源二县交界，西与正蓝旗为邻，北与赤峰市克什克腾旗毗连(图1）。县境南北长约 $1 1 0 ~ \mathrm { k m }$ ,东西宽约 $7 0 ~ \mathrm { k m }$ ，总面积3863$ { \mathrm { k m } } ^ { 2 }$ 。县境内地形为四周高、中间低的半环形盆地,海拔1 $1 5 0 \sim 1 ~ 8 0 0 ~ \mathrm { ~ m ~ }$ ,地貌属低山丘陵，气候属于温带半干旱向半湿润过渡的典型大陆性气候,年平均降水量 $3 8 5 . 5 ~ \mathrm { m m }$ ,年平均风速 $3 . 6 \mathrm { ~ m ~ } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ ,无霜期$1 0 0 \mathrm { ~ d ~ }$ 左右。土壤以栗钙土和风沙土为主，地带性植被为典型草原植被。县辖两镇三乡（多伦诺尔镇、大北沟镇、西干沟乡、大河口乡、蔡木山乡）、64个行政村、8个社区。

2016 年末多伦县总人口 $1 1 . 0 5 \times 1 0 ^ { 4 }$ 人，国内生产总值 $8 3 . 7 1 4 1 \times 1 0 ^ { 8 }$ 元,比上年增长 $2 . 1 \%$ 。其中,第一产业值为 $9 . 5 0 4 \ 4 \times 1 0 ^ { 8 }$ 元,增长 $3 . 2 \%$ ；第二产业值为 $5 5 . 6 9 0 \ 9 \times 1 0 ^ { 8 }$ 元,增长 $- 0 . 5 \%$ ；第三产业值为 $1 8 . 5 1 8 \mathrm { ~ 8 ~ } \times 1 0 ^ { 8 }$ 元,增长 $1 0 . 1 \%$ 。年末牲畜存栏头数为 $2 1 . 5 2 \times 1 0 ^ { 4 }$ 头只,增长 $- 1 5 . 6 \%$ 。其中,大牲畜 $1 0 . 5 7 \times 1 0 ^ { 4 }$ 头只，增长 $1 1 . 5 \%$ ；羊 $8 . 7 3 \times$

![](images/557342cbbde6521c07b28ac3a4a1362f0d4d866a14672a68247e6baac59207b0.jpg)  
图1多伦县地理位置示意图  
Fig.1Geographical position diagram of Duolunr County

$1 0 ^ { 4 }$ 只,增长 $- 3 7 . 5 \%$ ；猪 $2 . 2 2 \times 1 0 ^ { 4 }$ 头,增长 $7 . 8 \%$ 。

# 1.2 数据来源

本研究基于已有的研究积累（1960、1975、1987、1995、2000、2005年的不同类型土地沙漠化矢量数据）[15],再以统一解译标准提取 2010 和 2015 的土地沙漠化空间信息，从而形成了研究区8个时期不同土地沙漠化类型的空间分布信息。驱动力分析所需的数据主要包括统计年鉴数据、气象数据、地形数据等。气象数据来自内蒙古气象局信息服务中心，为了保证气象资料的完整性及持续性，选取了研究区气象台站的年均气温、降水量、平均风速等要素。地形数据是通过数字化研究区 $1 : 5$ 万地形图获取的。社会经济数据来源于1961—2016年的《内蒙古多伦县国民经济与社会发展统计资料汇编》和《锡林郭勒盟统计年鉴》、《改革开放30年的内蒙古》(1978—2008）。

# 1.3 研究方法

1.3.1土地沙漠化空间信息提取在ENVI5.0软件下对2010年和2015年的遥感影像进行432波段组合假彩色合成拼接、裁剪，在ArcGIS10.2下对照地形图及2005年的已配准遥感影像、土地利用现状图及野外实地调查点，选择明显地物作为地面控制点，与遥感影像上的同名控制点建立位置关系，将2010年与2015年的遥感影像进行配准，误差不得大于三个像元；依据《中国北方沙漠化土地分类分级表》[16]和确立解译标志和解译精度,将研究区土地沙漠化分类系统划分为轻度沙漠化、中度沙漠化、重度沙漠化、严重沙漠化和非沙漠化5类[17],提取2010 年和2015年的土地沙漠化数据，为避免遗漏较小面积的图斑，规定面积大于 $6 \times 6$ 个像元的图斑均要上图;通过实地调查点及GoogleEarth的辅助，利用ENVI5.0软件混淆矩阵工具对2010年和2015年土地沙漠化矢量数据进行精度评价，得到的解译精度分别为 $8 6 . 1 \%$ 和 $8 7 . 5 \%$ ,均超过 $8 6 \%$ 。当Kappa系数大于0.75时,影像分类精度较高[18]解译精度达到了要求。

1.3.2土地沙漠化动态分析各类土地沙漠化的动态变化将采用增长量、增长率、发展速度等动态指标进行分析。其中，增长量 $\mathbf { \sigma } = \mathbf { \sigma }$ 本期数－上期数，是指某现象在一定时期增长或减少的绝对量，可以有正负数，正表示增加，负表示减少；增长率 $\mathbf { \sigma } = \mathbf { \sigma }$ (本期数－上期数)/上期数，反映本期比上期水平增长了百分之多少或多少倍；发展速度 $\mathbf { \sigma } = \mathbf { \sigma }$ 本期数/上期数，是说明事物发展快慢程度的动态相对数，表示本期水平是上期水平的几倍或百分之几，发展速度大于 $100 \%$ （或1)表示上升，小于 $100 \%$ （或1)表示下降。

1.3.3土地沙漠化驱动因子筛选及处理根据多伦县实际情况和驱动因子选取标准，从自然和社会经济两方面选取年均降水量、年均气温、平均风速、第一产业、居民点距离、牲畜数量等驱动因子，分别计算出1960—1995年和1995—2015年两个时间段相应指标数据的多年平均值，借助ArcGIS10.2平台上的join工具以多伦县各村为研究单位分别赋予相应地区，且每个驱动因子作为一个矢量图层，实现驱动因子空间化，无量纲化、共线性检验等处理，最后将每个驱动因子矢量图转换为分辨率为 $3 0 \mathrm { ~ m ~ }$ 的栅格图层。

1.3.4Logistic $\boxed { \pmb { \bigtriangledown } }$ 归模型本研究中各类土地沙漠化 $( Y )$ 是二分类因变量，当各类土地沙漠化面积发生变化时 $Y = 1$ ，否则， $Y = 0$ 。假设影响各类土地沙漠化面积发生变化的6个要素,即自变量 $( X _ { i } )$ $( i = 1 , 2 , \cdots , k )$ ，各类土地沙漠化面积发生变化（ $\mathbf { \nabla } \cdot Y = 1 \mathbf { \dot { \theta } } ,$ 的概率为 $P$ 。假定 $x _ { 1 }$ ， $x _ { 2 }$ ， $\boldsymbol { x } _ { 3 }$ ……·是与 $Y$ 相关的一组变量， $P$ 是某事件发生变化的概率，则没有发生变化的概率为 $( 1 - P )$ ,将比数 $P / ( 1 - P )$ 取对数得 $\ln [ P / ( 1 - P ) ]$ ，即对 $P$ 作Logistic 变换，记为$\log \dot { \mathrm { i t } } ( P )$ ,其计算公式见参考文献[19]。使用Wald 统计量对模型回归系数进行检验，取显著性水平为0.05，当解释变量Wald所对应的概率 $P$ 值小于给定的显著性水平，则认为该解释变量的回归系数与零有显著差异，应保留在方程中；反之不能通过显著性检验被去除[20]

为避免数据的空间自相关性，通过ArcGIS10.2中的create randompoint工具，生成了均匀分布在整个研究区域的 $n$ 个观测点,通过extract value to point工具分别在土地沙漠化变化差别较为显著的1960—1995年和1995—2015年研究阶段的轻度沙漠化、中度沙漠化、重度沙漠化、严重沙漠化土地影响因子栅格图上提取相应变化值（即0和1），最后保留具有变化值的200个样本点，作为Logistic回归模型的建模数据。对于每个模型均选取随机抽样的200个点，确保因变量的0和1观测值就有相等的数量，不相等的抽样比例只会影响模型的常数项，不会影响自变量在模型中的回归系数[21-22] ○

# 2 结果与分析

# 2.1多伦县土地沙漠化动态变化特征分析

多伦县1960—2015 年间土地沙漠化面积变化可分为两个阶段：1960一1995年间是土地沙漠化发展时期;1995—2015 年间是土地沙漠化逆转时期（图2）。在前一段时期总土地沙漠化面积由1960年的 $2 1 5 . 0 0 ~ \mathrm { k m } ^ { 2 }$ 增加到1995年的 $8 5 4 . 8 8 ~ \mathrm { k m } ^ { 2 }$ ，而到后一段时期减少到2015年的 $1 8 6 . 1 6 ~ \mathrm { k m } ^ { 2 }$ ,总体上呈减少趋势。其中，轻度沙漠化及中度沙漠化面积变化幅度最大，在发展时期分别由 $9 1 . 8 5 ~ \mathrm { k m } ^ { 2 }$ 和$2 7 . 3 8 ~ \mathrm { k m } ^ { 2 }$ 增加到 $3 8 8 . 9 4 ~ \mathrm { k m } ^ { 2 }$ 和 $2 7 7 . 9 2 ~ \mathrm { k m } ^ { 2 }$ ,在逆转发展时期分别减少到2015年的 $7 0 . 4 7 ~ \mathrm { k m } ^ { 2 }$ 和$4 4 . 5 4 ~ \mathrm { k m } ^ { 2 }$ 。20 世纪60 年代初,沙漠化土地零散分布在城南沙带和北部地区，到1995年时连片分布在蛇皮河及一家河、吐力根河东南侧、城南沙带周围地区，到2015年时零星分布在大河口乡、蔡木山乡、西干沟乡、多伦诺尔镇南部等地方。

轻度沙漠化面积变化是匀速增加到最高峰，1995年后呈现了匀速减少的趋势。其中，1960—1995 年轻度沙漠化增长 $2 9 7 . \ 0 9 \ \ \mathrm { \ k m } ^ { 2 }$ ,增长率为3.23，发展速度为4.23，表明这期间轻度沙漠化以4.23 的发展速度,增加了 $2 9 7 . 0 9 ~ \mathrm { k m } ^ { 2 }$ ; 1995—2015年增长了 $- 3 1 8 . 4 7 ~ \mathrm { k m } ^ { 2 }$ ,增长率为-0.82,发展速度为0.18，表明1995年后，轻度沙漠化以0.18的发展速度减少了 $3 1 8 . 4 7 ~ \mathrm { k m } ^ { 2 }$ 。

中度沙漠化面积变化是1960—1995 年先增加后减少的趋势，但1995—2000年间无明显减少现象。其中，1960—1995 年中度沙漠化增长 250.54$\mathrm { k m } ^ { 2 }$ ,增长率为9.15,发展速度为10.15,表明这期间中度沙漠化以10.15的发展速度增加了250.54$\mathrm { k m } ^ { 2 }$ ;1995—2015 年中度沙漠化增长了－233.38$\mathrm { k m } ^ { 2 }$ ,增长率为-0.84,发展速度为0.16,表明这期间，中度沙漠化以0.16的发展速度减少了233.38km²。

![](images/f8b9563b121e584165f5187fe53f2d036d8572590ec2e21cbb90df1681728b12.jpg)  
图2多伦县各类土地沙漠化面积变化柱状图 Fig.2Change of desertification area of various land in Duolun County

重度沙漠化面积变化是1960—2000年变化波动平缓，而2000年之后2005年达到了最高峰，然后有逐渐减少的趋势。其中，1960一1995 年重度沙漠化增长了 $6 6 . 6 3 ~ \mathrm { k m } ^ { 2 }$ ,增长率为2.00,发展速度为3.00,1995—2015 年间的增长面积为 $- 4 9 . 8 3 \ \mathrm { k m } ^ { 2 }$ ，增长率为-0.50。

严重沙漠化面积变化是1960年2000 年间稳定的小幅度增加的趋势，但近些年有明显的逐渐减少趋势。其中,1960—1995年严重沙漠化的增长为$2 5 . 6 2 ~ \mathrm { { \ k m } } ^ { 2 }$ ,增长率为0.41,发展速度为1.41,1995—2015 年严重沙漠化增长了 $- 6 7 . 0 4 ~ \mathrm { k m } ^ { 2 }$ ,增长率为-0.76，发展速度为0.24。

# 2.2多伦县土地沙漠化驱动力分析

采用Logistic回归模型的Enter进入法进行逐步回归计算，得到各土地沙漠化驱动因子估计结果（表1、表2、表3、表4）。

2.2.1轻度沙漠化由回归模型参数Wald统计量(表1)可知，1960—1995 年轻度沙漠化增加的较为重要的解释变量为第一产业。从回归系数可知，第一产业负向显著影响土地沙漠化，说明第一产业值越小、发展越差时其他类型的土地沙漠化会转为轻度沙漠化的概率增加。根据Wald统计量可知，第一产业的贡献率为2.999，大于牲畜数量。1995—2015年间牲畜数量正向影响土地沙漠化，随着牲畜数量的增加会使土地沙漠化更加恶化。

2.2.2中度沙漠化由回归系数(表2)可知，在1995一2015年中度沙漠化面积减少的较为重要的变量是降水量和牲畜数量。根据Wald统计量可知，降水量和牲畜数量的贡献率分别为3.075和3.852。模型中降水量的回归系数为正，表明降水量的增加会使中度沙漠化转为轻度沙漠化的概率增加。牲畜数量在 $9 5 \%$ 的置信区间上正向影响中度沙漠化，说明随着牲畜数量增加，中度沙漠化会越严重。

Tab.1Estimation of the driving force model of mild desertification land change   
表2中度沙漠化土地变化驱动力模型估计结果  

<html><body><table><tr><td></td><td></td><td>回归系数</td><td>标准误差</td><td>Wald统计量</td><td>自由度</td><td>显著性水平</td><td>发生比率</td></tr><tr><td>1960—1995</td><td>第一产业</td><td>-0.002</td><td>0.001</td><td>2.999</td><td>1</td><td>0.083</td><td>0.998</td></tr><tr><td>1995—2015</td><td>牲畜数量</td><td>0.068</td><td>0.026</td><td>6.834</td><td>1</td><td>0.009</td><td>1.000</td></tr></table></body></html>

Tab.2Estimation of the driving force model of heavy moderate desertification land change   
表3重度沙漠化土地变化驱动力模型估计结果  

<html><body><table><tr><td></td><td></td><td>回归系数</td><td>标准误差</td><td>Wald统计量</td><td>自由度</td><td>显著性水平</td><td>发生比率</td></tr><tr><td>1995—2015</td><td>降水量</td><td>0.128</td><td>0.073</td><td>3.075</td><td>1</td><td>0.079</td><td>1.137</td></tr><tr><td></td><td>牲畜数量</td><td>0.096</td><td>0.048</td><td>3.852</td><td>1</td><td>0.050</td><td>1.000</td></tr></table></body></html>

表1轻度沙漠化土地变化驱动力模型估计结果  
表4严重沙漠化土地变化驱动力模型估计结果  

<html><body><table><tr><td colspan="2"></td><td>回归系数</td><td>标准误差</td><td>Wald统计量</td><td>自由度</td><td>显著性水平</td><td>发生比率</td></tr><tr><td rowspan="2">1960—1995</td><td>居民点距离</td><td>-0.001</td><td>0.001</td><td>4.948</td><td>1</td><td>0.026</td><td>0.999</td></tr><tr><td>第一产业</td><td>0.002</td><td>0.001</td><td>2.807</td><td>1</td><td>0.094</td><td>1.002</td></tr><tr><td rowspan="2">1995-2015</td><td>平均风速</td><td>- 103.523</td><td>42.729</td><td>5.870</td><td>1</td><td>0.015</td><td>0.000</td></tr><tr><td>居民点距离</td><td>0.002</td><td>0.000</td><td>24.361</td><td>1</td><td>0.000</td><td>1.002</td></tr></table></body></html>

Tab.3Estimation of the driving force model of heavy desertification land change   
Tab.4Estimation of the driving forces model of severe desertification land change   

<html><body><table><tr><td></td><td></td><td>回归系数</td><td>标准误差</td><td>Wald统计量</td><td>自由度</td><td>显著性水平</td><td>发生比率</td></tr><tr><td>1960—1995</td><td>居民点距离</td><td>-0.001</td><td>0.000</td><td>4.185</td><td>1</td><td>0.041</td><td>0.999</td></tr><tr><td></td><td>第一产业</td><td>0.007</td><td>0.003</td><td>7.793</td><td>1</td><td>0.005</td><td>1.007</td></tr><tr><td>1995—2015</td><td>第一产业</td><td>0.001</td><td>0.000</td><td>4.490</td><td>1</td><td>0.034</td><td>1.001</td></tr></table></body></html>

2.2.3重度沙漠化1960—1995 年重度沙漠化增加的较为重要的解释变量是居民点距离和第一产业。根据Wald统计量可知，分别贡献率为4.948和2.807。第一产业的回归系数为正，说明第一产业在$9 0 \%$ 的置信区间上正向显著影响土地沙漠化，随着第一产业的增加，重度沙漠化增加的概率增大；居民点距离的回归系数为负，表明随着居民点距离的减少，重度沙漠化面积增加的概率增大。在1995—2015年重度沙漠化减少的重要解释变量是平均风速和居民点距离。由Wald统计量可看出居民点距离的贡献率较大，贡献率为24.361。从回归系数可知，居民点距离在 $9 9 \%$ 的置信区间上正向显著影响重度沙漠化，表明随着居民点距离的加大，重度沙漠化面积减少的概率会增加。平均风速在 $9 9 \%$ 的置信区间上负向显著影响重度沙漠化，随着平均风速的加大会使土地沙漠化越严重。

2.2.4严重沙漠化1960—1995 年间严重沙漠化面积增加显著性影响的是居民点距离和第一产业，显著性水平均在0.05以下。根据Wald统计量可知，贡献率分别为4.185和7.793。从回归系数可知，居民点距离在 $9 5 \%$ 的置信区间上负向显著影响严重沙漠化，说明居民点距离越接近时别的类型的土地沙漠化会变成严重沙漠化的概率会提高。第一产业在 $9 9 \%$ 的置信区间上正向影响严重沙漠化，即第一产业的正向发展会增加土地沙漠化的严重化发展的概率。1995—2015 年间严重沙漠化面积减少的较为显著的驱动因子是第一产业。第一产业的回归系数为正，说明这期间内的第一产业的增加会提高严重沙漠化面积扩大的概率。

# 3结论与讨论

# 3.1结论

（1）1960—2015年多伦县土地沙漠化总体呈现波动中减少趋势，并且存在明显阶段性特征。1960一1995年土地沙漠化发展较快,年增长率达到$1 8 . 2 8 ~ \mathrm { k m } ^ { 2 }$ ,这与同期人口迅速增长及草场超载有关，尤其是第一产业的发展加大了土地沙漠化扩展；1995—2015年土地沙漠化发展呈逆转趋势，减少了$1 2 8 . 8 4 ~ \mathrm { k m } ^ { 2 }$ ,年减少率达到 $6 . 4 4 ~ \mathrm { k m } ^ { 2 }$ 。这与同期实施的京津风沙源治理工程、退耕还林、禁牧舍饲和生态移民等重点生态建设工程密切相关。

（2）1960—1995 年间轻度沙漠化与第一产业值之间呈负相关，即第一产业值越小时，其他土地沙漠化类型会转为轻度沙漠化的概率较大。1995—2015年间轻度沙漠化与牲畜数量之间呈正相关，表明随着牲畜数量的增加会使轻度沙漠化往恶化方向发展;1995—2015年间中度沙漠化与牲畜数量之间呈正相关，说明随着牲畜数量的增加会使中度沙漠化面积增加。中度沙漠化与降水量之间也呈正相关，表明降水量的增加会使中度沙漠化转为轻度沙漠化增加；1960—1995年间重度沙漠化与居民点距离之间呈负相关，表明随着居民点距离的加大，重度沙漠化增加的概率增大。重度沙漠化与第一产业之间呈正相关，随着第一产业的增加，重度沙漠化增加的概率增大。1995—2015 年间重度沙漠化与平均风速之间呈显著的负相关，随着平均风速的加大会使土地沙漠化越严重。重度沙漠化与居民点距离之间呈正相关，表明随着居民点距离的加大，重度沙漠化面积减少的概率会增加;1960—1995年间严重沙漠化与居民点距离之间呈负相关，说明居民点距离越接近时别的类型的土地沙漠化变成严重沙漠化的概率会提高。1960—2015 年间严重沙漠化与第一产业之间一直呈正相关，说明第一产业增加会提高严重沙漠化的面积。

（3）在1960—2015年的55a来多伦县土地沙漠化呈现逆转趋势，存在明显阶段性特征。1960一1995年间正是盲目发展时期，第一产业正兴起，人口数量不断上升导致居民点距离越来越近，加上牲畜数量快速增加和气温变暖23是导致土地沙漠化恶化的主要原因；1995—2015年间年平均降水量呈减少趋势，对土地沙漠化逆转不利，但及时的控制牲畜数量及土地沙漠化治理工程对土地沙漠化逆转起到了有效作用。总之，牲畜数量减少及政府沙漠化治理工程对土地沙漠化逆转起到了一定的作用，继续控制牲畜数量，实施退耕还林还草等措施来逆转土地沙漠化的发展。第一产业已明显超过年均气温、降水量、平均风速对土地沙漠化发生、扩展与逆转过程的影响。第一产业对土地沙漠化影响明显，是土地沙漠化的重要驱动因素。

# 3.2讨论

在半干旱区土地沙漠化研究领域已经引起学者们的广泛关注，且对自然因素和人文驱动因素进行定量分析一直是该领域的研究者致力解决的难题。多伦县土地沙漠化过程是自然因素与人类活动的双重作用下产生的，人为因素的贡献率为 $5 7 . 2 9 \%$ ，自然因素的贡献率为 $1 3 . 1 6 \%$ ，自然与人为因素共同作用的贡献率为 $1 6 . 7 6 \%$ [13］。显然,多伦县土地沙漠化诱发过程中人为因素作用强度处于较高的水平，这可能与其地处荒漠与草原的过渡地带,生态本底比较脆弱，农业生产条件的变动比较频繁有关。本研究运用Logistic回归模型分析1960—2015年的多伦县沙漠化动态变化驱动力机制，同样发现社会经济因素为主要驱动因子，尤其受到第一生产的影响。1960一1995年间第一产业发展、人口数量增加、牲畜数量增加和气温变暖是土地沙漠化发展主要因素，1995一2015年间年牲畜数量的减少和土地沙漠化治理工程的实施是土地沙漠化逆转的主要因素。这与高晓霞[24]等对浑善达克沙地动态的研究结果基本一致。但与丁文广[25]等对海西蒙古族藏族自治州沙漠化的研究结果不一致，其原因在于所选研究区位置不同有关，内蒙古多伦县降水量呈减少趋势，而海西州降水量呈增加趋势。

# 参考文献(References）

[1］张晓东,刘湘南，赵志鹏,等.农牧交错区生态环境质量遥感动 态监测—以宁夏盐池为例[J].干旱区地理,2017,40（5）： 1070 -1078.[ ZHANG Xiaodong,LIU Xiangnan,ZHAO Zhipeng, et al.Dynamic monitoring of ecology and environment in the agropastral ecotone based on remote sensing:A case of Yanchi County in Ningxia Hui Autonomous Region[J].Arid Land Geography, 2017,40(5):1070-1078.]   
[2］张建香,张多勇,刘万锋,等.基于ESAI的黄土高原荒漠化风 险评估[J].水土保持通报,2017,2（37）：339－344.［ZHANG Jianxiang,ZHANG Duoyong,LIU Wanfeng,et al.ESAI based assessment of desertification risk in Loess Plateau[J].Bulletin of Soil and Water Conservation,2017,2(37） :339-344.]   
[3］吴亚平,潘高峰,彭尔兴,等.锡北地方铁路风沙防治措施研究 [J].干旱区地理,2016,39（6）:1247-1254.[WU Yaping， PAN Gaofeng,PENG Erxing,et al. Sand flow control measures of the Xitieshan to North Hobson local railway[J].Arid Land Geography,2016,39(6) :1247-1254.]   
[4］王涛.荒漠化治理中生态系统、社会经济系统协调发展问题探 析——以中国北方半干旱荒漠区沙漠化防治为例[J].生态学 报,2016,22(36）:7045-7048.[WANG Tao.Study on the coordinated development of ecosystem and socio-economic system in desertification control：A case study of desertification control in semiarid area in North China[J].Acta Ecologica Sinica.2O16,22 (36):7045-7048.]   
[5] 王娅,周立华,魏轩.基于社会-生态系统的沙漠化逆转过程 脆弱性评价指标体系［J].生态学报,2018,38（3）：1－12. [WANGYa,ZHOULihua,WEI Xuan,etal.An evaluation index system of vulnerability of the desertification reversion process based on the socio-ecological systems theory[J].Acta Ecologica Sinica, 2018,38(2):1-12.]   
「6]T文广.陈利珍.李丹璐.等.1975—2014 年晋西北地区沙漠

化动态变化趋势研究［J].干旱区地理,2016,39（5）:994- 1003.[DING Wenguang,CHNE Lizhen,LI Danlu,et al. Dynamic change trend of desertification in northwest Shanxi Province during 1975—2014[J].Arid Land Geography,2016,39（5）: 994- 1003.]   
[7]CARROLL C,MERTON L,BURGER P. Impact of vegetation cover and slope on runoff,erosion,and water quality for field plots on a range of soil and water quality for field plots on a range of soil and spoil materials on central Queensland coalmines[J].Australian Journal of Soil Research,2000,38(2）:313-327.   
[8］康相武,吴绍洪,刘雪华.浑善达克沙地土地沙漠化时空演变 规律研究［J].水土保持学报,2009,23（1）:1-6.［KANG Xiangwu,WU Shaohong,LIU Xuehua. Research on spatio-temporal change of sandy desertification in Hunshandake[J]. Journal of Soil and Water Conservation,2009,23(1):1-6.]   
[9］王涛.中国沙漠与沙漠化[M].石家庄;河北科学技术出版社, 2003:16.[WANG Tao.Desert and aeolian desertification in China [M].Shijiazhuang: Hebei Science and Technology Press,2003: 16.]   
[10］张莉秋,张红,李皎,等.晋北沙漠化地区1980—2014 年的气 候变化[J].中国沙漠,2016,36（4）:1116－1125.［ZHANG Liqiu,ZHANG Hong,LI Jiao,et al. Climate change in sandy desertification areaof the Northern Shanxi from 1980 to 2014[J]. Journal of Desert Research,2016,36(4):1116-1125.]   
[11]ROLAND G,MOHAMMAD I. Assessment of rangeland degradation and development of a strategy for rehabilitation[J]. Remote Sensing of Environment,2004,90(4） :490-504.   
[12］马永欢,周立华,朱艳玲,等.近50 年来盐池县土地沙漠化驱 动因素的时间变化[J].干旱区研究,2009,26(2）：249-253. [MA Yonghuan,ZHOU Lihua,ZHU Yanling,et al. Time series variation in the driving factors leading to land desertification in Yanchi County over the last 5O years[J].Arid Zone Research, 2009,26(2):249 -253.]   
[13］阿如旱,扬持.内蒙古多伦县沙漠化驱动因素影响的累加效应 分析[J].中国沙漠,2007,27（6）:936-941.[Aruhan,YANG Chi.Cumulative impacts of driving factors on desertification in Duolun country of Inner Mongolia[J].Journal of Desert Research, 2007,27(6) :936 -941.]   
[14］于宝乐,吴文俊,赵学军,等.内蒙古京津风沙源治理工程土壤 风蚀控制效益研究［J].干旱区研究,2016,6（33）：1278- 1286.［YU Baole,WU Wenjun,ZHAO Xuejun,et al.Benefits of soil wind erosion control of the Beijing-Tianjin Sand Source Control Project in Inner Mongolia[J].Arid Zone Research,2016,6(33）: 1278 -1286.]   
[15］阿如旱.近50a京津沙源边缘区土地沙漠化时空变化规律及 其发展态势研究［D].呼和浩特：内蒙古大学,2007.［Aruhan. Study on temporal and spatial variation of land desertification and its development trend in the fringe of Beijing-Tianjin[D].Hohhot : Inner Mongolia University,2007.]   
[16］王涛,吴薇,薛娴,等.近50 年来中国北方沙漠化土地的时空 变化[J].地理学报,2004,59(2）:203-212.[WANG Tao,WU Wei,XUE Xian. Spatial-temporal changes of sandy desertified land during last5 decades in northern China[J].Acta Geographica Sinica,2004,59(2):203-212.]   
[17］阿如旱,扬持.内蒙古多伦县土地沙漠化景观格局变化特征 [J]．应用生态学报,2007,18（11）:2520－2525.[Aruhan, YANG Chi. Dynamic changes of land scape pattern during desertification in Duolun County of Inner Mongolia[J].Chinese Journal of Applied Ecology,2007,18（11）:2520-2525.]   
[18］常学礼，王玮,韩艳,等.祁连山中部素珠链峰地区冰川斑块动 态分析[J].自然资源学报，2013,28（2）：266-276.［CHANG Xueli,WANGWei,HAN Yan.Glacier patch dynamics in the SuzulianPeak area of the middleQilian Mountains[J].Journal of Natural Resources,2013,28(2):266 -276.]   
[19]HOSMER D W,LEMESHOW S.Applied logistic regression[M]. $2 ^ { \mathrm { n d } }$ ed.New York:John Wiley and Sons,2000:156-164.   
[20］王济川,郭志刚.Logistic 回归模型：方法与应用[M].北京：高 等教育出版社,2001.［WANG Jichuan,GUO Zhigang.Logistic regression model:Methods and applications[M].Beijing:Higher Education Press,2001.]   
[21］谢花林，李波.基于Logistic回归模型的农牧交错区土地利用 变化驱动力分析[J].地理研究，2008，27（2）：294-304.［XIE Hualin,LI Bo.Driving forces analysis of land-use pattern changes based on Logistic regression model in the farming-pastoral zone [J].Geographical Research,2008,27(2）:294-304.]   
[22］姜广辉,张凤荣.基于Logistic 回归模型的北京山区农村居民 点距离变化的驱动力分析[J].农业工程学报，2007，23（5）： 81-87.[JIANG Guanhui,ZHANG Fengrong.Analysis of the driving forces of change of rural residential areas in Beijing mountainous areas based on Logistic regression model[J].Transactions of the CSAE,2007,23(5):81-87.] [23］阿如旱，车敏.近60年多伦县气候特征变化分析[J].内蒙古 师范大学学报（自然科学汉文版），2017，46（3）：426－430. [Aruhan,CHE Min.Analysis on the characteristics of climate change in recent 6O years in Duolun County of Inner Mongolia[J]. Journal of Inner Mongolia Normal University（Natural Science Edition).2017,46(3) :426-430.] [24］高晓霞,温璐,刘华民,等.基于Logistic 回归模型的浑善达克沙 地动态及其驱动力分析[J].内蒙古大学学报（自然科学版），   
2016,47(6):625-634.[GAO Xiaoxia,WEN Lu,LIU Huamin,et al.Dynamics changes and driving forces analysis of Otindag sandy land based on Logistic regression model[J]. Journal of Inner MongoliaUniversity(Natural Science Edition）,2016,47(6):625-634.] [25］丁文广，耿怡颖，张慧琳，等.近40a海西蒙古族藏族自治州沙 漠化时空变化及驱动力分析［J].沙漠与绿洲气象，2017，11 (3）:1-8.[DING Wenguang,GENG Yiying,ZHANG Huilin,et al.Analysis on spatial-temporal evolution of desertification and its driving force over Haixi Mongolian and Tibetan Autonomous Prefecture in recent 4O years[J].Desert and Oasis Meteorology,   
2017,11(3):1-8.]

# Driving forces on land desertification in Duolun County Inner Mongolia based on Logistic regress model

Aruhan，DU Lai， SHENG Yan，Asina (CollegeofEcologicalTenvironmentofInnerongoliaAgriculturalUniversity,HohhotOol1,InnerongoliaChina)

Abstract：Taking thedesertification vectordataof1960,1975,1987,1995,2000and 2005 inDuolun Countyof Inner Mongolia,China and the remote sensing images and topographic maps of 2O1O in 2O10 as the main data sources,using ENVI5.Oand ArcGIS10.2 software to extract the spatial informationof desertification in8 periods, thecharacteristicsofdesertification in diferent desertification typessuchasmild desertification,moderatedesertification,heavy desertificationand severe desertification wereanalyzed in spatialand temporal diferences.Duolun County is located inthe desertand steppe transitional zone,ecological background is more fragile,agricultural production conditions change more frequently,and the process of desertification induced by human factors atahigh level of intensityfor nearlyhalfacentury.According totheactual situationof the studyarea,statisticaldata such as elevation,average annual temperature,precipitation,verage wind speed,number of livestock,primary industryand residential area were selected.Logistic regresion model was used to analyze quantitatively thedynamic mechanism of desertification.The results showed thatthearea of desertification in Duolun County decreased from196O to 2015, with a tendencyof increasing from 1960 to1995and a decreasing trend from1995 to 2015.The dominant factorto varioustypes of desertification growth from 196O to 1995 was primary idustryand residential areas；and in 1995— 2015 thedominant factor affcting various types of land desertification was precipitation,livestock,primary industry andresidential distance.In the future,we willcontinue to control the number of livestock and implement the policy of desertification control to reverse the development of land desertification.

Key words:land desertification；driving forces；Logistic regression model；Duolun County of Inner Mongolia