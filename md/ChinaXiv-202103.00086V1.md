# 内蒙古地区近地面臭氧浓度时空分异及主导气象因子探讨

陈志青'，邵天杰'，赵景波²，曹军骥²，岳大鹏1(1.陕西师范大学地理科学与旅游学院,陕西 西安710119；2.中国科学院地球环境研究所，气溶胶化学与物理重点实验室，陕西 西安710061)

摘要：利用内蒙古地区2017年12个盟市的空气质量监测数据,研究了 $\mathrm { ~ O } _ { 3 }$ 浓度的时空分布特征，基于GAM模型探讨了气象因素对 $\mathrm { O } _ { 3 }$ 浓度变化及分布的影响。结果表明：内蒙古地区12个盟市均存在不同程度的 $\mathrm { O } _ { 3 }$ 浓度超标情况； $\mathrm { O } _ { 3 }$ 月均浓度呈先升高后降低的变化特征,4—9月 $\mathrm { O } _ { 3 }$ 浓度最高,污染最为严重,且在7月达到全年最高值( $1 3 6 ~ \mu \mathrm { g }$ $\mathbf { m } ^ { - 3 }$ );地域规律呈现出内蒙古中部地区 $\mathrm { O } _ { 3 }$ 浓度最高，西部地区 $\mathrm { O } _ { 3 }$ 浓度居中，东部地区 $\mathrm { O } _ { 3 }$ 浓度较低的特征。通过构建GAM模型对内蒙古地区12个盟市影响 $\mathrm { \Delta O } _ { 3 }$ 浓度变化的主导气象因子进行识别,发现气温是影响整个内蒙古地区 $\mathrm { O } _ { 3 }$ 浓度变化的最主要气象因子，而相对湿度、日照时数、风速分别是内蒙古东部、中部和西部地区影响 $\mathrm { O } _ { 3 }$ 浓度变化的第二主导气象因子。

关键词：臭氧；时空分布；气象因子；GAM模型；内蒙古地区

$\mathrm { O } _ { 3 }$ 是天然大气的重要微量成分，也是造成城市光化学烟雾污染的主要化学成分[]。近几年来，随着城市化和工业化的快速发展， $\mathrm { ~ O } _ { 3 }$ 浓度快速增加，其被认为是影响当今环境质量仅次于 $\mathrm { P M } _ { 2 . 5 }$ 的重要大气污染物[2-3]。光化学反应是城市近地面 $\mathrm { O } _ { 3 }$ 的主要来源[4]，气象因素对 $\mathrm { O } _ { 3 }$ 的生成、积累、扩散有重要影响[5-6]。科学认识 $\mathrm { O } _ { 3 }$ 浓度的变化规律及其影响因素，对 $\mathrm { \Delta O } _ { 3 }$ 污染的科学防控具有重要意义。国内外学者基于气象因素对 $\mathrm { O } _ { 3 }$ 浓度的影响方面进行了大量的研究并得到了大致相同的结论[7-9]： $\mathrm { O } _ { 3 }$ 浓度与太阳辐射强度、气温、日照时数等呈正相关关系；与降水，相对湿度、风速等呈负相关关系。

现有的对 $\mathrm { O } _ { 3 }$ 浓度影响因素的研究主要通过相关分析[10-11]、多元线性回归分析[12]、地理探测器[13]]灰色关联模型[14]等统计学方法完成。这些方法基本建立在假设 $\mathrm { O } _ { 3 }$ 浓度与影响因素之间呈线性相关关系的基础上，实际上大气污染物是受多因素驱动的复杂非线性时间变化系列[15-16]。因此,运用一个能够解决响应变量与解释变量之间呈非线性关系的模型来探讨气象因素对 $\mathrm { O } _ { 3 }$ 浓度变化影响的研究，具有一定的科研价值和理论意义。内蒙古地区地域广袤，横跨东北、华北、西北三大区，各地区气象条件差异较大，组合变化复杂，因此，影响 $\mathrm { O } _ { 3 }$ 的主导气象因子也有所差异。本研究运用广义相加模型(generalizedadditive model,GAM)构建 $\mathrm { O } _ { 3 }$ 浓度变化与气象因素之间的非线性模型，对内蒙古地区12个盟市影响 $\mathrm { O } _ { 3 }$ 浓度变化的主导气象因子进行识别，深入探讨气象因子对 $\mathrm { O } _ { 3 }$ 浓度变化的影响特征，以丰富内蒙古地区 $\mathrm { O } _ { 3 }$ 污染研究的内容。

# 数据来源与研究方法

# 1.1数据来源

$\mathrm { O } _ { 3 }$ 浓度数据来自2017年环境保护部在内蒙古地区设置的12个环境空气质量国控点的自动监测。数据在全国城市空气质量实时发布平台(http:/106.37.208.233:20035/)下载，为保证数据质量，对数据的有效性、异常值分别按照《环境空气质量标准》（GB3095-2012)和《环境监测质量管理技术导则》(HJ630-2011)进行判断和处理。根据《环境空气质量指数(AQI)技术规定(试行)》(HJ633-2012)中的评价标准选取 $\mathrm { O } _ { 3 }$ 日最大 $8 \mathrm { ~ h ~ }$ 滑动平均浓度（以下简称为‘ $\mathrm { ^ { \cdot } O _ { 3 } } – 8 \mathrm { h } ^ { \prime \prime }$ )作为 $\mathrm { O } _ { 3 }$ 日评价指标， $\mathrm { \Delta O } _ { 3 }$ 日最大 $8 \mathrm { ~ h ~ }$ 滑动平均浓度第90百分位数（以下简称为‘ $\mathrm { \Delta \mathrm { \Omega ^ { \cdot } O _ { 3 } } } \mathrm { - } 8 \mathrm { h } \mathrm { - \Omega }$ 90")作为 $\mathrm { O } _ { 3 }$ 年评价指标。

气象资料在中国气象科学数据共享网(http://cdc.cma.gov.cn)下载,选取其中的地面气象资料的日值数据部分。由于每个城市都有至少2个以上的气象站点，考虑到数据的代表性水平，每个城市选取1个距离市区最近的气象站作为气象要素的数据来源。主要数据包括气温（TEMP）降水量(PREC），风速(WIND）、日照时数(SH)和相对湿度(RH)等气象要素，数据及原始数据文件已经过严格的质量控制和检查。

# 1.2研究方法

广义可加模型（generalized additive model,GAM)是广义线性模型和可加模型的结合形式，是1个由数据驱动的非参数回归模型，该模型通过对解释变量进行光滑函数拟合创建，能够很好地解决呈非线性关系的响应变量与解释变量之间的数据分析问题[17-18]。利用R语言的mgcv包中的 $\mathrm { g a m }$ 函数创建GAM模型：

$$
g ( \mu ) { = } a + f _ { 1 } ( x _ { 1 } ) + f _ { 2 } ( x _ { 2 } ) + \cdots + f _ { p } ( x _ { p } ) + \varepsilon
$$

式中： $\mu$ 是相应变量的期望值， $g ( \mu )$ 是连接函数： $f _ { p }$ 是连接解释变量的平滑函数； $x _ { p }$ 是解释变量； $\mathbf { \Omega } _ { a }$ 是截距；$\varepsilon$ 是随机变量。

在建模之前，根据响应变量的分布特征确定连接函数，利用方差膨胀因子(VIF)对解释变量之间的共线性问题进行诊断。在建模过程中，为同时保证曲线的拟合优度和拟合光滑度，可能会出现过拟合，为保证所建立模型的可靠性,利用R语言的gamcheck对模型进行验证。

# 2结果与讨论

# 2.1 $\mathbf { 0 } _ { 3 }$ 浓度时空分布特征

2.1.1 $\mathrm { O } _ { 3 }$ 浓度总体概况2017年内蒙古地区12个盟市 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 的平均值为 $1 4 2 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ,低于全国平均值 $1 4 9 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ,其中,呼伦贝尔市的 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 最低 $( 1 1 1 ~ \mu \mathrm { g } \cdot \mathrm { m } ^ { - 3 } )$ ,乌兰察布市的 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 最高(167$\mu \mathrm { g } \cdot \mathrm { m } ^ { - 3 } ,$ 。根据《环境空气质量评价技术规范（试行)》的规定，当城市一年内 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 浓度大于160$\mu \mathrm { g } \cdot \mathrm { m } ^ { - 3 }$ 时，该城市的年度评价结果为超标。12个盟市中，有2个城市超标，超标城市比例为 $1 6 . 6 7 \%$ 。经统计，各城市均存在 $\mathrm { O _ { 3 } { - } 8 h }$ 日均值超过《环境空气质量标准》（GB3095-2012)中二级标准的现象（图1)，12个盟市累计超标天数共为275d,占总监测天数的 $6 . 2 8 \%$ 。各城市超标天数变化范围在 $1 \sim 5 1 \mathrm { ~ d ~ }$ ，平均超标天数为22.75d,其中，超标天数在 $2 0 \sim 4 2$ d之间的比例最大，共6个城市，占总监测城市的$5 0 \%$ 。

2.1.2 $\mathrm { ~ O } _ { 3 }$ 浓度月变化特征由图2可知，内蒙古地区 $\mathrm { \Delta O } _ { 3 }$ 月均浓度呈倒"V"形单峰变化的特征，1一7月随温度的逐渐升高， $\mathrm { O } _ { 3 }$ 月均浓度逐渐上升，8—12月随温度的降低， $\mathrm { \Delta O } _ { 3 }$ 月均浓度逐渐下降，最大值出现在

![](images/587b0716e23bf70aeddfe129466c15b290e9d84775a69e4db88a53c2a62b4437.jpg)  
图12017年内蒙古地区各城市 $\mathrm { O _ { 3 } } \mathrm { - } 8 \mathrm { h } \mathrm { - } 9 0$ 浓度和超标天数  
Fig.1 The $\mathrm { O _ { 3 } } \mathrm { - } 8 \mathrm { h } \mathrm { - } 9 0$ and the number of days exceeded in each city in Inner Mongolia in 2017

7月（ $1 3 6 ~ \mu \mathrm { g } \cdot \mathrm { m } ^ { - 3 } ,$ ,最低值出现在12月（ $5 8 ~ \mu \mathrm { g } \cdot \mathrm { m } ^ { - 3 } ,$ 。其中，4—9月为 $\mathrm { O } _ { 3 }$ 污染最为严重的时期， $\mathrm { O } _ { 3 }$ 平均浓度变化范围在 $1 0 4 \sim 1 3 6 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ,平均值为 $1 1 9 ~ \mu \mathrm { g }$ ：$\mathbf { m } ^ { - 3 }$ 。 $\mathrm { ~ O } _ { 3 }$ 超标天数的月分布特征也呈中间高两边低的倒"V"形，在 $\mathrm { O } _ { 3 }$ 浓度最高的7月， $\mathrm { O } _ { 3 }$ 超标天数全年最高达到 $9 8 \mathrm { ~ d ~ }$ ，占全年 $\mathrm { O } _ { 3 }$ 总超标天数的 $3 5 . 2 7 \%$ ，6月次之， $\mathrm { ~ O } _ { 3 }$ 超标天数92d,占全年 $\phantom { + } 0 _ { 3 }$ 总超标天数的$3 3 . 4 5 \%$ 。其中，4—9月 $\mathrm { O } _ { 3 }$ 超标天数累计为274d，占全年 $\mathrm { O } _ { 3 }$ 总超标天数的 $9 9 . 6 4 \%$ ，1月、2月、10月、11月和12月均未出现 $\mathrm { O } _ { 3 }$ 超标。

内蒙古地区 $\mathrm { \Delta O } _ { 3 }$ 月均浓度呈倒"V"形单峰变化，这与南方的长三角城市群[19]、珠三角城市群[20]等 $\mathrm { O } _ { 3 }$ 月均浓度变化曲线呈“M"形不同，南方这些城市 $\mathrm { O } _ { 3 }$ 月均浓度出现中间的谷值主要是由于梅汛期的存在造成的。在这一时段，通常日照时数较少，降水量和相对湿度较高，对 $\mathrm { \Delta O } _ { 3 }$ 的清除和消耗作用占主导，不利于 $\mathrm { O } _ { 3 }$ 的生成和增加。内蒙古地区全年降水较少，对 $\mathrm { O } _ { 3 }$ 浓度的消耗和清除作用比较微弱，这种作用还可能被温度和太阳辐射对 $\mathrm { \Delta O } _ { 3 }$ 的正向作用抵消。4一9月，属于温带大陆性季风气候的内蒙古地区，日照时数达到全年最高( $1 6 5 8 \mathrm { h } )$ ，气温的高值也集中出现在这一时段，强太阳辐射和高温等作为生成 $\mathrm { O } _ { 3 }$ 光化学反应发生的有利环境条件，有利于高浓度 $\mathrm { O } _ { 3 }$ 的生成。9月至次年4月，太阳辐射强度较弱，温度较低，整体大气活性减弱，生成 $\mathrm { O } _ { 3 }$ 光化学反应的速率减弱， $\mathrm { O } _ { 3 }$ 浓度较低。

![](images/81d181687a5c5498f679995a0c04c23e9eb169079e399811ffc5f50d92767580.jpg)  
图2 $\mathrm { \Delta O } _ { 3 }$ 浓度与超标天数月均分布  
Fig.2Monthly average distribution of $\mathrm { O } _ { 3 }$ concentration and over-standard days   
注：底图源自中国政区图[审图号：GS(2016)2923号]，未对边界进行修改。  
图32017年内蒙古地区 $\mathrm { O _ { 3 } } \mathrm { - } 8 \mathrm { h } \mathrm { - } 9 0$ 及超标天数的空间变化  
Fig.3Spatial variation of the $\mathrm { O _ { 3 } } \mathrm { - } 8 \mathrm { h } \mathrm { - } 9 0$ concentration and the number of days exceeding the standard in Inner Mongolia in 2017

2.1.3 $\mathrm { ~ O } _ { 3 }$ 浓度空间分布特征由图3可知， $\mathrm { ~ O } _ { 3 }$ 浓度的高值区主要分布在中部地区的乌兰察布市，呼和浩特市，鄂尔多斯市和包头市， $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 的变化范围为 $1 5 6 \sim 1 6 7 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ,平均值为 $1 6 1 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ,是内

100E 110E 120E 100E 110E 120O3-8h-90/(μg·m-3)  
No0s 12-120 布 呼伦贝尔 No0s No0s 超12 布 呼伦贝尔 Noos128\~136 4呼和浩特 26\~40 4呼和浩特136\~144 5包头 >41 5包头  
4504 152\~160 144\~152 6乌海 7鄂尔多斯 2 4554 N04 6乌海 7鄂尔多斯 2. 44锡林郭勒 赤峰 锡林郭勒 赤峰巴彦淖尔5 3 N0v 巴彦淖尔5 No00  
No04 阿拉善盟 N04 阿拉善盟 +670 300km1100E 110E 120E 100E 110E 120E

蒙古地区 $\mathrm { O } _ { 3 }$ 高污染城市的集中地区，2017年的2个年评价指标超标的城市都在这一区域，且鄂尔多斯市的 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 达到 $1 5 8 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ，接近超标；西部地区的阿拉善盟、乌海市和巴彦淖尔盟 $\mathrm { O } _ { 3 }$ 浓度值居中， $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 的变化范围为 $1 4 1 \sim 1 5 5 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ，平均值为 $1 4 9 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ $\mathrm { O } _ { 3 }$ 浓度的低值区主要分布在东部地区的呼伦贝尔市、兴安盟、锡林郭勒盟、赤峰市和通辽市, $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 的变化范围为 $1 1 1 \sim 1 3 9 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ ，平均值为 $1 2 4 ~ { \mu \mathrm { g } } \cdot \mathrm { m } ^ { - 3 }$ 0 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h }$ 超标天数的空间分布与 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h } { - } 9 0$ 的区域分布基本一致，同样表现为中部地区(平均超标天数 $3 9 . 7 5 \mathrm { ~ d } ) >$ 西部地区（平均超标天数 $2 4 . 3 3 \mathrm { d } ) >$ 东部地区(平均超标天数 $8 . 2 \ : \mathrm { d }$ )。

# 2.2GAM模型的构建

呼和浩特市地处内蒙古中部,是内蒙古地区 $\mathrm { O } _ { 3 }$ 污染最严重的地区。以呼和浩特市为例，利用GAM模型对 $\mathrm { O } _ { 3 }$ 浓度变化与影响因素进行拟合，来分析 $\mathrm { O } _ { 3 }$ 浓度变化的主导影响因素及影响特征。根据文献[21-23]疏理，选取了对 $\mathrm { O } _ { 3 }$ 浓度变化影响较大的气温（TEMP）、降水量（PREC）、风速（WIND）、日照时数(SH)）、相对湿度(RH)等5个气象因子作为解释变量。

2.2.1变量预分析选取的解释变量之间可能存在的多重共线性关系会使模型估计失真，影响估计结果的准确性。利用Eviews10对所选5个解释变量的多重共线性进行方差膨胀因子(VIF)分析(表1)，当$\mathrm { V I F } > 5$ 时，认为解释变量存在多重共线性，结果表明，本文所选解释变量的VIF值均小于5,解释变量之间不存在多重共线性问题。在建模前需要对响

# 表1影响因素多重共线性诊断结果

Tab.1 Results of multiple co-curve test of influencing factors   

<html><body><table><tr><td>指标</td><td>气温</td><td>日照时数</td><td>降水</td><td>风速</td><td>相对湿度</td></tr><tr><td>VIF</td><td>1.672</td><td>2.517</td><td>1.447</td><td>1.386</td><td>2.731</td></tr></table></body></html>

应变量的分布特征进行分析以确定连接函数， $\mathrm { O } _ { 3 ^ { - } }$ 8h浓度变化作为响应变量，经计算，2017年呼和浩特市 $\mathrm { O _ { 3 } } \mathrm { - } 8 \mathrm { h }$ 的偏度为0.387，峰度为-0.438，并利用SPSS软件绘制QQplot图，发现 $\mathrm { O _ { 3 } } \mathrm { - } 8 \mathrm { h }$ 基本呈正态分布。因此，采用恒等联系函数作为连接函数，将解释变量以线性组合的方式来连接响应变量。

2.2.2单因子影响因素分析对于选定的气温、日照时数、降水量、风速、相对湿度等5个影响因素，每次选择一个作为解释变量， $\mathrm { O } _ { 3 }$ 浓度作为响应变量，逐一构建GAM模型，来分析每个气象因素对响应变量 $\mathrm { O } _ { 3 } { - } 8 \mathrm { h }$ 的影响显著性、方差解释率及拟合优度(表2)。其中， $F$ 统计值是判断影响重要性的指标，各气象因子的 $F$ 统计值越大，其对 $\mathrm { O } _ { 3 }$ 影响就越大； $P$ 值代表假设检验结果的显著性水平，一般取显著性水平为 $P < 0 . 0 5 ; R ^ { 2 }$ 指示回归拟合优度，取值范围为[0,1，且 $R ^ { 2 }$ 越接近1,表明回归拟合效果越好；自由度值是判断解释变量与响应变量之间相关关系的指标，当自由度值为1时，表明影响因素与 $\mathrm { O } _ { 3 }$ 浓度变化间是线性关系，当自由度值大于1时，表明影响因素与 $\mathrm { O } _ { 3 }$ 浓度变化间是非线性关系，且值越大非线性关系越显著。

由表2可知，风速，降水量的 $P$ 值分别为0.214和0.6，均大于显著性水平0.05,未通过显著性检验，不具有统计学意义。气温、日照时数、相对湿度在$P { < } 0 . 0 0 1$ 水平下显著影响 $\mathrm { O } _ { 3 }$ 浓度变化，表明气温、日照时数、相对湿度单独作为 $\mathrm { O } _ { 3 }$ 浓度变化解释变量具有统计学意义。其中，气温和日照时数的方差解释率较高（ $2 7 \% \sim 7 5 . 3 0 \%$ ），调整 $R ^ { 2 }$ 较大( $0 . 2 6 \sim$ 0.749），表明GAM模型拟合优度较好；相对湿度的方差解释率较低( $5 . 4 7 \%$ ，调整 $R ^ { 2 }$ 较小(0.0496)，表明GAM模型拟合优度较差。气温、日照时数和相对湿度的自由度都大于1，表明这3个影响因素均与 $\mathrm { \Delta O } _ { 3 }$ 浓度呈非线性关系。

表2呼和浩特市 $\mathbf { O } _ { 3 }$ 浓度与单个影响因子的GAM模型拟合结果  
Tab.2 TheGAMfittingresultsof $\mathbf { O } _ { 3 }$ concentration and a single meteorological factor in Hohhot   

<html><body><table><tr><td>平滑效应项</td><td>估计自由度</td><td>参考自由度</td><td>F</td><td>P</td><td>R</td><td>方差解释率/%</td></tr><tr><td>S(TEMP)</td><td>6.001</td><td>7.486</td><td>145.1</td><td><2e-1***</td><td>0.749</td><td>75.30</td></tr><tr><td>S(PREC)</td><td>1</td><td>1</td><td>1.548</td><td>0.214</td><td>0.0015</td><td>0.43</td></tr><tr><td>S(WIND)</td><td>1.675</td><td>2.127</td><td>0.617</td><td>0.6</td><td>0.000964</td><td>0.56</td></tr><tr><td>S(SH)</td><td>4.841</td><td>6.005</td><td>21.42</td><td><2e-1***</td><td>0.26</td><td>27</td></tr><tr><td>S(RH)</td><td>1.941</td><td>2.46</td><td>8.223</td><td>0.000169***</td><td>0.0496</td><td>5.47</td></tr></table></body></html>

注：\*\*\*表示在0.001水平上显著。下同。

2.2.3多影响因素GAM模型的构建、分析及验证进一步选取5个气象因子作为解释变量， $\mathrm { ~ O } _ { 3 }$ 浓度为响应变量，利用 $\mathrm { O } _ { 3 }$ 和这5个气象因素共同构建GAM模型进行多因素的相关性分析(表3)，以分析气象因素对 $\mathrm { O } _ { 3 }$ 浓度的综合影响。

# 表3呼和浩特市 $\mathbf { O } _ { 3 }$ 浓度与5影响因子的GAM模型拟合结果

Table3 The GAM fittingresults of $\mathbf { O } _ { 3 }$ concentration and five meteorological factors in Hohhot   

<html><body><table><tr><td>平滑效应项</td><td>估计自由度</td><td>参考自由度 F</td><td></td><td>P</td></tr><tr><td>S(TEMP)</td><td>5.936</td><td>7.343</td><td>112.112</td><td><2e-16**</td></tr><tr><td>S(PREC)</td><td>1.000</td><td>1.000</td><td>1.282</td><td>0.258</td></tr><tr><td>S(WIND)</td><td>4.826</td><td>5.939</td><td>1.624</td><td>0.128</td></tr><tr><td>S(SH)</td><td>5.897</td><td>7.225</td><td>4.922</td><td>2.19e-05****</td></tr><tr><td>S(RH)</td><td>1.000</td><td>1.000</td><td>0.171</td><td>0.679</td></tr></table></body></html>

由表3可知，风速、降水量、相对湿度的 $P$ 值均大于0.05，未通过在0.05水平下的显著性检验，不具有统计学意义。气温和日照时数的 $P$ 值均在0.001水平下显著影响 $\mathrm { O } _ { 3 }$ 浓度变化。多因子模型的调整$P ^ { 2 }$ 为0.781,方差解释率为 $7 9 . 3 \%$ 。因此，剔除在多因子分析中未通过显著性检验的风速、降水量和相对湿度，重新利用GAM模型进行多因素的相关性分析(表4)。

重新分析后，气温和日照时数的 $P$ 值在0.001水平下显著影响 $\mathrm { O } _ { 3 }$ 浓度变化，且拟合模型的调整 $R ^ { 2 }$ 为

# 表4呼和浩特市 $\mathbf { O } _ { 3 }$ 浓度与2影响因子的GAM模型拟合结果

Tab.4 The GAM fitting results of $\mathbf { O } _ { 3 }$ concentration and two meteorological factors in Hohhot   

<html><body><table><tr><td>平滑效应项</td><td>估计自由度</td><td>参考自由度</td><td>F</td><td>P</td></tr><tr><td>S(TEMP)</td><td>6.792</td><td>8.426</td><td>99.609</td><td><2e-16****</td></tr><tr><td>S(SH)</td><td>6.346</td><td>7.817</td><td>6.304</td><td>1.87e-07****</td></tr></table></body></html>

0.798，方差解释率为 $7 9 . 6 \%$ ，较5因子的GAM模型拟合结果要好，说明此GAM模型拟合较优，气温、日照时数与 $\mathrm { O } _ { 3 }$ 浓度间的相关性较强。进一步通过值的大小判断解释变量的影响程度，发现气温的 $F$ 值(99.609)远大于日照时数的 $F$ 值(6.304），说明气温是呼和浩特市影响 $\mathrm { O } _ { 3 }$ 浓度变化的最主要气象因素。

通过上述建模过程后，获得气温、日照时数的平滑回归函数，并得到气温、日照时数对 $\mathrm { ~ O } _ { 3 }$ 浓度的影响效应图(图4)，以此来具体分析气温、日照时数与 $\mathrm { O } _ { 3 }$ 浓度变化间的相关关系。由图4可以看出，气温与 $\mathrm { O } _ { 3 }$ 浓度呈复杂的非线性关系，整体表现为先降低后升高的特点，当气温小于 $- 1 0 \mathrm { { ^ { \circ } C } }$ 时， $\mathrm { O } _ { 3 }$ 浓度随气温下降而降低；当气温大于 $- 1 0 \ \mathrm { { ^ circ C } }$ 后， $\mathrm { O } _ { 3 }$ 浓度随气温升高而增加，特别是在温度大于 $2 0 \ \%$ 后， $\mathrm { ~ O } _ { 3 }$ 浓度上升速度明显加快。日照时数与 $\mathrm { O } _ { 3 }$ 浓度也呈非线性的正相关关系， $\mathrm { ~ O } _ { 3 }$ 浓度随日照时数的增加呈缓慢波动上升的趋势。综上表明较高的温度和较强的太阳辐射有利于 $\mathrm { O } _ { 3 }$ 浓度的增加。

为了保证模型质量和可信度，进一步利用R语言中的gam.check代码对模型拟合结果进行验证。在样本分位数与理论分位数的QQ图中(图5)，样本点基本都在直线上，表明样本数据来自正态分布总体；在线性预测值与残差散点图中，残差呈随机分布状态，没有明显的趋势；在残差直方图中，残差值出现在0附近的频率较高；在拟合值和响应值的散点图中,模型拟合后的响应值和拟合值基本呈 $y = x$ 型分布，匹配程度较高。整体表明模型拟合质量较好。

# 2.3内蒙古地区 $\mathbf { O } _ { 3 }$ 污染的主导气象因子分析

利用上述对呼和浩特市进行分析的相同方法对内蒙古地区其他城市创建GAM拟合模型。在经过对解释变量预处理、单因子和多因子GAM建模、对模型进行分析检验后，利用 $F$ 统计值，最终确定出主导各城市 $\mathrm { ~ O } _ { 3 }$ 浓度变化的2大主要因子。表5按照重要性等级统计了每个城市影响 $\mathrm { O } _ { 3 }$ 浓度变化的2大主要气象因子。

![](images/ed46132e8cf4fe439a86b78e8950a9bf5cceade566c3080c27349d4c898548d7.jpg)  
图4气温、日照时数对 $\mathrm { O } _ { 3 }$ 浓度变化的影响效应  
Fig.4Effect of air temperature、sunshine duration on the variation of $\mathrm { O } _ { 3 }$ concentration

![](images/9c08fc591583787a2b6b5d9b8f450ccf782bf43f1447e7760269faf58a2ca780.jpg)  
图5GAM模型残差检验结果  
Fig.5The residual test results of GAM

整体来看，气温对于整个内蒙古地区的 $\mathrm { O } _ { 3 }$ 浓度变化影响最大，12个盟市中重要性级别为1的气象因子全部为气温，且气温的 $F$ 值远远高于排在第2位的影响因子。研究表明，温度影响 $\mathrm { O } _ { 3 }$ 的光化学生成速率，且温度越高，就越有利于光化学反应的进行[24]。降水量对 $\mathrm { O } _ { 3 }$ 浓度的影响最小，12个城市中对$\mathrm { O } _ { 3 }$ 浓度影响最大的2个气象因子中均没有降水量这一气象因子,降水量一般与 $\mathrm { O } _ { 3 }$ 浓度呈负相关关系，但是由于内蒙古地区全年降水量较少，2017年年均降水量仅为 $2 8 3 \mathrm { m m }$ ，对 $\mathrm { O } _ { 3 }$ 浓度及其前体物的冲刷作用不显著，甚至其负向作用可能被气温等因素的正向作用抵消。

在内蒙古中部地区的4个城市(呼和浩特市、包头市、鄂尔多斯市和乌兰察布市)中， $\mathrm { O } _ { 3 }$ 浓度最高的呼和浩特市和乌兰察布市的重要性级别为2的气象因子是日照时数，包头市为风速，鄂尔多斯市为相对湿度。日照时数与太阳紫外辐射强度呈正相关关系，而紫外辐射为 $\mathrm { O } _ { 3 }$ 的光化学过程提供能量来源，加速光化学反应的发生，为 $\mathrm { O } _ { 3 }$ 的生成提供条件[25]。因此，日照时数与 $\mathrm { O } _ { 3 }$ 浓度呈正相关关系，而风速和相对湿度一般与 $\mathrm { O } _ { 3 }$ 浓度呈负相关关系[7]。经分析，整个内蒙古地区的日照时数具有从中部 $( 2 8 2 4 \mathrm { h } )$ -东部 $( 2 9 8 7 \mathrm { h } )$ -西部（ $( 3 2 0 0 \mathrm { h } )$ 逐渐升高的特点，而年平均气温表现为东部(年平均气温 $5 . 4 3 ~ \mathrm { \textdegree C }$ )-中部(年平均气温 $7 . 4 4 ^ { \circ } \mathrm { C }$ )-西部(年平均气温 $9 . 5 3 ~ \mathrm { { ^ circ C } }$ )逐渐升高的特点，日照时数、气温的空间分布格局与 $\mathrm { O } _ { 3 }$ 浓度的空间分布格局并不一致。研究表明，大气污染物与气象因素的交互作用对污染物浓度变化产生最主要的影响作用[15],中部地区作为内蒙古经济发展最快的城市群[26]，较高的经济发展水平和较快的经济发展速度增加了 $\mathrm { O } _ { 3 }$ 前体物的人为排放源，使得中部地区的前体物排放量最高。可见，气温和日照时数对 $\mathrm { O } _ { 3 }$ 浓度的正向作用和前体物排放量的共同影响，导致中部地区成为 $\mathrm { O } _ { 3 }$ 浓度高值区。

表5内蒙古地区12个盟市影响 $\mathbf { O } _ { 3 }$ 浓度的主要影响因素  
Tab.5 Themainmeteorological factorsimpacting $\mathbf { O } _ { 3 }$ concentration for12 citiesin Inner Mongolia   

<html><body><table><tr><td rowspan="3">城市</td><td colspan="4">重要性级别</td></tr><tr><td colspan="2">1</td><td colspan="2">2</td></tr><tr><td>影响因子</td><td>F</td><td>影响因子</td><td>F</td></tr><tr><td>呼和浩特市</td><td>TEMP</td><td>99.609</td><td>SH</td><td>6.304</td></tr><tr><td>包头市</td><td>TEMP</td><td>79.946</td><td>WIND</td><td>9.390</td></tr><tr><td>鄂尔多斯市</td><td>TEMP</td><td>53.984</td><td>RH</td><td>4.392</td></tr><tr><td>乌兰察布市</td><td>TEMP</td><td>159.143</td><td>SH</td><td>3.408</td></tr><tr><td>阿拉善盟</td><td>TEMP</td><td>136.250</td><td>WIND</td><td>45.32</td></tr><tr><td>巴彦淖尔市</td><td>TEMP</td><td>78.850</td><td>WIND</td><td>11.349</td></tr><tr><td>乌海市</td><td>TEMP</td><td>245.635</td><td>WIND</td><td>19.884</td></tr><tr><td>锡林郭勒盟</td><td>TEMP</td><td>159.143</td><td>SH</td><td>3.408</td></tr><tr><td>赤峰市</td><td>TEMP</td><td>53.984</td><td>RH</td><td>4.392</td></tr><tr><td>通辽市</td><td>TEMP</td><td>72.087</td><td>RH</td><td>12.995</td></tr><tr><td>兴安盟</td><td>TEMP</td><td>19.171</td><td>RH</td><td>6.584</td></tr><tr><td>呼伦贝尔盟</td><td>TEMP</td><td>69.671</td><td>RH</td><td>32.391</td></tr></table></body></html>

在内蒙古西部地区的3个城市(阿拉善盟、巴彦淖尔市和乌海市)中，重要性级别为2的气象因子均为风速。研究表明，风速对上风向大气污染物有扩散作用的同时，也可能对下风向城市造成输入性污染[20]。进一步对 $\mathrm { O } _ { 3 }$ 浓度与风速进行相关性分析，发现风速与 $\mathrm { O } _ { 3 }$ 浓度在0.01水平上显著正相关，相关系数为0.258。内蒙古西部地区地处中纬度西风带，周边地区高浓度的 $\mathrm { O } _ { 3 }$ 输送可能是内蒙古西部地区 $\mathrm { \Delta O } _ { 3 }$ 浓度的重要来源。

在内蒙古东部地区的5个城市(锡林郭勒盟、赤峰市、通辽市、兴安盟和呼伦贝尔盟)中，有4个城市重要性级别为2的气象因子是相对湿度，只有锡林郭勒盟是日照时数。可见，在内蒙古东部地区气象因子对 $\mathrm { O } _ { 3 }$ 浓度的影响程度为：气温 $>$ 相对湿度 $>$ 日照时数。相对湿度对 $\mathrm { O } _ { 3 }$ 浓度的影响主要表现在三方面：一是水汽蕴含的 $\mathrm { H } , \mathrm { O H }$ 自由基参与消耗 $\mathrm { O } _ { 3 }$ 的化学反应[27]；二是高湿环境利于 $\mathrm { O } _ { 3 }$ 的干沉降，对 $\mathrm { O } _ { 3 }$ 有一定的清除作用[28]；三是水汽存在消光机制，能使太阳辐射衰减，从而减弱光化学反应的发生速率[29]。进一步对东部地区相对湿度与 $\mathrm { O } _ { 3 }$ 浓度进行相关分析，结果表明，相对湿度与 $\mathrm { O } _ { 3 }$ 浓度在0.01水平下显著负相关，相关系数为-0.223。整个内蒙古地区的平均相对湿度具有从东部( $4 9 \%$ )-中部 $( 4 7 \% )$ -西部1 $41 \%$ )逐渐递减的特征，较高的相对湿度对 $\mathrm { O } _ { 3 }$ 的清除和消耗作用[30],使得东部地区成为 $\mathrm { O } _ { 3 }$ 浓度低值区。

# 3结论

（1）2017年内蒙古地区12个盟市均存在不同程度的 $\mathrm { O } _ { 3 }$ 浓度超标现象。一年中的4一9月是 $\mathrm { O } _ { 3 }$ 污染最严重的月份，且在7月达到 $\mathrm { O } _ { 3 }$ 浓度峰值。（2）内蒙古地区 $\mathrm { O } _ { 3 }$ 浓度存在明显的空间分异特征，总体表现为中部地区 $>$ 西部地区 $>$ 东部地区。(3）气温是影响内蒙古地区 $\mathrm { O } _ { 3 }$ 浓度变化最主要的气象因子，而相对湿度、日照时数、风速分别是内蒙古东部、中部、西部地区影响 $\mathrm { O } _ { 3 }$ 浓度变化的第二主导气象因子。

# 参考文献(References):

[1]陈仁杰,陈秉衡,阚海东.上海市近地面臭氧污染的健康影响评 价[J].中国环境科学,2010,30(5):603-608.[Chen Renjie,Chen Bingheng,Kan Haidong.Health impact assessment of surface ozone pollution in Shanghai[J].China Environmental Science, 2010,30(5): 603-608.]   
[2]张小电,孙俊英,王亚强,等.我国雾-霾成因及其治理的思考 [J].科学通报,2013,58(13):1178-1187.[Zhang Xiaoye,Sun Junying,Wang Yaqiang,et al. Factors contributing to haze and fog in China[J]. Chinese Science Bulletin,2013,58(13):1178-1187.]   
[3]同丽嘎,李雪铭,张靖,等.包头市典型城市绿地及周边 $\mathrm { P M } _ { 2 . 5 }$ 对 比分析[J].干旱区研究,2018,35(3):562-567.[Tongliga,Li Xueming, Zhang Jing, et al. $\mathrm { P M } _ { 2 . 5 }$ Concentration over typical urban green spaces in Baotou city and its peripheral regions[J].Arid Zone Research,2018,35(3): 562-567.]   
[4] Wang Y,Hopke PK,Xia X,et al. Source apportionment of airborne particulate matter using inorganic and organic species as tracers [J].Atmospheric Environment, 2012, 55(3): 525-532.   
[5]严仁嫦,叶辉,林旭,等.杭州市臭氧污染特征及影响因素分析 [J].环境科学学报,2018,38(3):1128-1136.[Yan Ren'e,Ye Hui, Lin Xu,et al. Characteristics and influence factors of ozone pollution in Hangzhou[J].Acta Scientiae Circumstantiae,2O18,38(3): 1128-1136.]   
[6]刘芷君,谢小训,谢旻,等.长江三角洲地区臭氧污染时空分布 特征[J].生态与农村环境学报,2016,32(3):445-450.[Liu Zhijun,Xie Xiaoxun,Xie Min,et al. Spatio-temporal distribution of ozone pollution over Yangtze river delta region[J]. Journal of Ecology and Rural Environment,2016,32(3): 445-450.]   
[7]黄小刚,邵天杰,赵景波,等.基于GAM模型的西安市 $\mathrm { O } _ { 3 }$ 浓度影 响因素解析[J].环境科学,2020,41(4):1535-1543.[Huang Xiaogang,Shao Tianjie, Zhao Jingbo,et al.Influencing factors of ozone concentration in Xi'an based on Generalized Additive Models [J].Environmental Science,2020,41(4): 1535-1543.] [8]齐冰,牛或文,杜荣光,等.杭州市近地面大气臭氧浓度变化特 征分析[J].中国环境科学,2017,37(2): 443-451.[Qi Bing,Niu Yuwen, Du Rongguang,et al. Characteristics of surface ozone concentration in urban site of Hangzhou[J]. China Environmental Science,2017,37(2): 443-451.] [9]Wang T, Xue L, Brimblecombe P,et al. Ozone pollution in China: A review of concentrations,meteorological influences,chemical precursors，and effects [J]. Science of the Total Environment,   
2016,575: 1582-1596. [10] 易睿,王亚林,张殷俊,等.长江三角洲地区城市臭氧污染特征 与影响因素分析[J].环境科学学报,2015,35(8):2370-2377. [YiRui,Wang Yalin,Zhang Yinjun,etal.Pollution characteristics and influence factors of ozone in Yangtze River Delta[J].Acta Scientiae Circumstantiae,2015,35(8): 2370-2377.] [11] 陈志青,邵天杰,赵景波.近3a内蒙古地区臭氧浓度时空变化 及其影响因素[J].干旱区研究,2019,36(4):990-996.[Chen Zhiqing, Shao Tianjie, Zhao Jingbo. Spatiotemporal variation of ozone concentration and its influential factors in Inner Mongolia in recent 3 years[J]. Arid Zone Research,2019,36(4): 990-996.] [12] 赵旭辉,董昊,季冕,等.合肥市 $\mathrm { O } _ { 3 }$ 污染时空变化特征及影响因 素分析[J].环境科学学报,2018,38(2):649-660.[Zhao Xuhui, Dong Hao,Ji Mian,etal.Analysis on the spatial-temporal distribution characteristics of $\mathrm { O } _ { 3 }$ and its influencing factors in Hefei City [J].Acta Scientiae Circumstantiae,2018,38(2): 649-660.] [13] 黄小刚,邵天杰,赵景波,等.长三角城市群臭氧浓度的时空分 异及驱动因素研究[J].长江流域资源与环境,2019,28(6):   
1434-1445.[Huang Xiaogang,Shao Tianjie, Zhao Jingbo,et al. Spatio-temporal differentiation of ozone concentration and its driving factors in Yangtze River Delta Urban Agglomeration[J].Resources and Environment in the Yangtze Basin,2019,28(6):1434-   
1445.] [14]南国卫,孙虎.基于灰色关联模型对陕西省 $\mathrm { O } _ { 3 }$ 浓度影响因素分 析[J].环境科学学报，2017,37(12):4519-4527.[Nan Guowei, Sun Hu.Analysis of the driving factors of ${ \bf O } _ { 3 }$ in Shaanxi Province based on grey correlation mode[J].Acta Scientiae Circumstantiae,   
2017,37(12): 4519-4527.] [15] Qian Z M, He Q C,Lin HM,et al. Association of daily causespecific mortality with ambient particle air pollution in Wuhan,China [J].Environmental Research,2007,105(3): 380-389. [16] 贺祥,林振山.基于GAM 模型分析影响因素交互作用对 $\mathrm { P M } _ { 2 . } ,$ 浓度变化的影响[J].环境科学,2017,38(1):22-32.[He Xiang, Lin Zhenshan. Interactive effects of the influencing factors on the changes of $\mathrm { P M } _ { 2 , \ 5 }$ concentration basedon GAM model[J]. Environmental Science, 2017,38(1): 22-32.] [17] 贾彬,王彤,王琳娜,等.广义可加模型共曲线性及其在空气污 染问题研究中的应用[J].第四军医大学学,2005,26(3):280- 283.[Jia Bin,Wang Tong,Wang Linna,et al. Concurvity in generalized additive model in study of air pollution[J]. Journal of the Fourth Military Medical University,2005,26(3): 280-283.]   
[18] 胡成媛,康平,吴锴,等.基于GAM 模型的四川盆地臭氧时空分 布特征及影响因素研究[J].环境科学学报,2019,39(3):809- 820.[Hu Chengyuan, Kang Ping,Wu Kai, et al. Study of the spatial and temporal distribution of the ozone and its influence factors over Sichuan Basin based on generalized additive model[J].Acta Scientiae Circumstaniae,2019,39(3): 809-820.]   
[19] 黄小刚,赵景波.2016年长三角城市群 $\mathrm { O } _ { 3 }$ 浓度的时空变化规律 [J].中国环境科学,2018,38(10): 3611-3620.[Huang Xiaogang, Zhao Jingbo.Spatial-temporal variation of ozone in Yangtze River Delta urban agglomeration in 2O16[J].China Environmental Science,2018,38(10):3611-3620.]   
[20] 黄小刚,邵天杰,赵景波,等.气象因素和前体物对中国东部 $\mathrm { O } _ { 3 }$ 浓度分布的影响[J].中国环境科学,2019,39(6):2273-2282. [Huang Xiaogang, Shao Tianjie, Zhao Jingbo, et al.Impact of meteorological factors and precursors on spatial distribution of ozone concentration in Eastern China[J]. China Environmental Science, 2019,39(6): 2273-2282.]   
[21] 曹庭伟,吴锴,康平,等.成渝城市群臭氧污染特征及影响因素 分析[J].环境科学学报,2018,38(4):1275-1284.[Cao Tingwei, Wu Kai, Kang Ping,et al. Study on ozone pollution characteristics and meteorological cause of Chengdu-Chongqing urban agglomeration[J].Acta Scientiae Circumstantiae,2018,38(4): 1275-1284.]   
[22] 安俊琳,王跃思,孙扬.气象因素对北京臭氧的影[J].生态环境 学报,2009,18(3): 944-951. [An Junlin,Wang Yuesi, Sun Yang. Assessment of ozone variations and meteorological effects in Beijing[J].Ecology and Environmental Sciences,2009,18(3): 944- 951.]   
[23] 贾梦唯,赵天良,张祥志,等.南京主要大气污染物季节变化及 相关气象分析[J].中国环境科学,2016,36(9):2567-2577.[Jia Mengwei, Zhao Tianliang,Zhang Xiangzhi,et al. Seasonal variations in major air polutants in Nanjing and their meteorological correlation analyses[J]. China Environmental Science,2016,36 (9): 2567-2577.]   
[24] 吴错,康平,王占山,等.成都市臭氧污染特征及气象成因研究 [J].环境科学学报,2017,37(1): 4241-4252.[Wu Kai, Kang Ping,Wang Zhanshan,et al. Ozone temporal variation and its meteorological factors over Chengdu city[J].Acta Scientiae Circumstantiae,2017,37(11): 4241-4252.]   
[25] 洪盛茂,焦荔,何曦,等.杭州市区大气臭氧浓度变化及气象要 素影响[J].应用气象学报,2009,20(5):602-609.[Hong Shengmao,Jiao Li, He Xi,et al. The variation of ozone concentrations in urban districts of Hangzhou and their relationship with meteorological factors [J]. Journal of Applied Meteorological Science,2009, 20(5): 602-611.]   
[26]王芳,高晓路.内蒙古县域经济空间格局演化研究[J].地理科 学,2014,34(7): 818-824.[Wang Fang,Gao Xiaolu. Spatial pattern evolvement of the economy in Inner Mongolia at the county level[J]. Geographic Science,2014,34(7): 818-824.]   
[27]刘晶淼,丁裕国,黄永德,等.太阳紫外辐射强度与气象要素的 相关分析[J].高原气象,2003,22(1):45-50.[Liu Jingmiao,Ding Yuguo,Huang Yongde,et al. Correlation analyses between intensity of solar ultraviolet radiation and meteorological elements[J].Plateau Meteorology,2003,22(1): 45-50.]   
[28]Jacob D J,Winner D A.Effect of climate change on air quality[J]. Atmospheric Environment,2009,43(1):51-63.   
[29]Kavassalis S C,Murphy JG. Understanding ozone-meteorology correlations:A role for dry deposition[J].Geophysical Research Letters,2017,44(6): 2922-2931.   
[30] 陈义珍,赵丹,柴发合,等.广州市与北京市大气能见度与颗粒 物质量浓度的关系[J].中国环境科学,2010,30(7):967-971. [Chen Yizhen,Zhao Dan,Chai Fahe,et al.Correlation between the atmospheric visibility and aerosol fine particle concentrations in Guangzhou and Beijing[J]. China Environmental Science,2010, 30(7): 967-971.]

# Spatial-temporal differentiation of near-surface ozone concentration and dominant meteorological factors in Inner Mongolia

CHEN Zhi-qing'， SHAO Tian-jie'， ZHAO Jing-bol²， CAO Jun-ji²， YUE Da-peng' (1.School ofGeography and Tourism,Shaanxi Normal University,Xi'an 71o119,Shaanxi，China;   
2. Key Laboratory ofAerosol Chemistry and Physics,Institute of Earth Environment, Chinese Academy of Sciences,Xi'an 710061,Shaanxi,China)

Abstract: Spatial and temporal ozone (O3)distribution characteristics were examined using air quality monitoring datafrom 12 leagues and cities in Inner Mongolia in 2O17.The impact of meteorological factors on ${ \bf O } _ { 3 }$ concentration and distribution was explored using a generalized additive model (GAM). Above-standard $\mathrm { O } _ { 3 }$ concentration was observed in 12 leagues and cities in Inner Mongolia to varying degrees.The average monthly ${ \bf O } _ { 3 }$ concentration showed a trend of increasing before decreasing over the span of a year,peaking with the worst pollution from April to September and reaching the annual maximum( $( 1 3 6 ~ \mu \mathrm { g } \cdot \mathrm { m } ^ { - 3 } )$ in July. Regional regularity was as follows: ${ \bf O } _ { 3 }$ concentration was the highest incentral Inner Mongolia,moderate in western Inner Mongolia,and lower in eastern Inner Mongolia.The dominant meteorological factors on $\mathrm { O } _ { 3 }$ concentration change in Inner Mongolia were identified by constructing a GAM. Temperature was the primary meteorological factor afecting $\mathrm { O } _ { 3 }$ concentration in all areas; relative humidity,sunshineduration,and windspeed were the secondary dominantfactors ineastern,central,and western Inner Mongolia, respectively.

Keywords:ozone;spatial and temporal distribution;meteorological factors；GAM; Inner Mongolia