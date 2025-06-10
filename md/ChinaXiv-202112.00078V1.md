# 西藏地区潜在蒸散量变化特征及灰色模型预测初探

史继清}，边多¹，杨霏云²，甘臣龙³，樊栋樑²(1.西藏自治区气候中心,西藏 拉萨850000；2.中国气象局气象干部培训学院,北京100081;3.墨竹工卡县气象局，西藏 拉萨 850000)

摘要：基于西藏地区38个气象站点1981—2019年逐日气象资料，采用Penman-Monteith模型、趋势分析、Morlet小波分析、Mann-Kendall检验、经验正交函数法(Empirical orthogonal function,EOF)和灰色模型探究潜在蒸散量( $\mathrm { \cdot E T _ { 0 } } )$ 的时空演变规律以及未来ET的变化趋势。结果表明：在时间尺度上，西藏地区 $\mathrm { E T _ { 0 } }$ 平均为 $5 9 7 . 1 2 \mathrm { m m }$ ,1981—2001年呈显著的减少趋势、2002—2019年呈显著的增加趋势( $_ { \scriptstyle P < 0 . 0 1 } )$ ；西藏全区及五大气候区年均 $\mathrm { E T _ { 0 } }$ 均呈现增加趋势(除东南部)，且均以33a的周期震荡为第一主周期。在空间尺度上，年 $\mathrm { E T _ { 0 } }$ 主要呈现由中部中心向西南和东南逐步递减的分布特征，高值中心集中在沿江一线，低值中心位于南部地区。年 $\mathrm { E T _ { 0 } }$ 发生突变的站点主要分布在南部边缘地区、沿江一线和东北部，发生时间集中在20世纪80年代。构建的 $\mathrm { G M } ( 1 , 1 )$ 预测模型预测精度均值为 $8 7 . 8 5 \%$ ，可用于西藏年均 $\mathrm { E T _ { 0 } }$ 日期序列的中长期预测，预测结果显示，除东南部年ET的预测值有明显下降，其他区域均呈现上升态势。

关键词：Penman-Monteith模型；潜在蒸散量；时空分析；灰色模型；西藏文章编号：

潜在蒸散量( $\mathrm { E T _ { 0 } } \rangle$ 是天气气候条件决定的下垫面蒸散过程的能力,是土壤层水分变化的重要指标[1],是区域水资源开发和评价依据2，同时在气候干湿状况、作物水分盈亏和植被净初级生产力[3-5等方面均得到了广泛应用。

近年来，诸多专家学者在ET的模拟、时空演变规律、驱动因素及对气候变化的响应等领域展开了大量的研究[6-7]。秦鹏程等[6]、Wilber等[8]、拉巴等[9、钟巧等[10]分别采用Thornthwaite法、人工神经网络模型（Artificialneuralnetwork,ANN）、地表能量平衡模型（Surface energy balance system,SEBS）、彭曼模型(Penman-Monteith,P-M),估算了湖北、秘鲁高地、藏北那曲、博斯腾湖流域等地的 $\mathrm { E T _ { 0 } }$ ，并进行了相关分析。其中，由联合国粮农组织FAO(1998年)推荐的Penman-Monteith模型[],既考虑了作物的生理特征，又考虑了空气动力学参数的变化，具有较充分的理论依据和较高的计算精度，得到较为广泛的应用[12-14]。目前针对西藏地区ET的研究多停留在局部区域、少量站点、较早时段，内容主要涉及年、季节ET时空变化趋势及成因分析等方面。例如杜军等[15]利用西藏"一江两河"主要农区4个气象站点资料，分析了农田ET空间分布、年代际变化特征以及讨论了影响ET变化的气象因子；杨永红等重点分析了7个站点逐日、逐月 $\mathrm { E T _ { 0 } }$ 年内变化规律;毛飞等[17]分析了那曲地区气温、降水和潜在蒸散的地理分布以及年内、年际变化规律;何慧根等[18]讨论了动力、热力和水分因子对潜在蒸散的影响;张娜等[19]采用曼-肯德尔法(Mann-Kendall,M-K)对西藏年际ET进行趋势检验及空间插值分析;唐小萍等2基于全球气候变暖背景，分析了西藏雅江中游地区 $\mathrm { E T _ { 0 } }$ 时空分布特征以及贡献率。

综上，已有的研究对西藏尤其是西藏不同气候区 $\mathrm { E T _ { 0 } }$ 及未来ET变化的研究较少，本文根据温克刚等[2的研究，将西藏划分为那曲中西部等五大气候区，通过分析各气候区ET的变化特征，探讨其突变性、周期性及灰色模型对未来ET的适用性，旨在为西藏节水灌溉、合理调配水资源及干旱监测提供科学依据。

# 1材料与方法

# 1.1研究区概况与数据来源

西藏位于祖国西南边陲，是青藏高原的主体，地理坐标在 $2 6 ^ { \circ } 5 0 ^ { \prime } \sim 3 6 ^ { \circ } 5 3 ^ { \prime } \mathrm { N } , 7 8 ^ { \circ } 2 5 ^ { \prime } \sim 9 9 ^ { \circ } 0 6 ^ { \prime } \mathrm { E }$ 之间。气温低、积温小、昼夜温差大、干湿季明显，年平均气温为 $- 2 . 4 { \sim } 1 2 . 1 \ ^ { \circ } \mathrm { C }$ ,年降水量 $6 6 . 3 { \sim } 8 9 4 . 5 ~ \mathrm { m m }$ ，年日照时数 $1 4 4 3 . 5 { \sim } 3 5 7 4 . 3 \mathrm { h }$ 。

本文所需气象数据来源于西藏自治区气象局提供的1981—2019年西藏地区38个气象站点的逐日气象资料，包括平均气温、最高气温、最低气温、平均风速、日照时数和平均相对湿度。其中，西藏根据气候区域划分为那曲中西部(那曲、班戈、申扎、当雄、安多、狮泉河、普兰、改则)、沿江一线(拉萨、泽当、日喀则、江孜、浪卡子、拉孜、尼木、贡嘎、墨竹工卡、加查、南木林）、南部边缘地区(聂拉木、定日、隆子、错那、帕里）东北部(昌都、丁青、索县、嘉黎、比如、洛隆、类乌齐)和东南部(林芝、波密、察隅、左贡、芒康、米林、八宿)图1)。

# 1.2研究方法

1.2.1Penman-Monteith修正公式潜在蒸散量$\mathrm { E T _ { 0 } }$ 由联合国粮农组织FAO(1998年)推荐的彭曼公

![](images/6503aef452828b99571240b65b4950f12258c48ff96e1164a5860878cdc8c601.jpg)  
图1西藏地区38个站点及5个分区的空间分布 Fig.1 Spatial distribution of the 38 stations and 5 zones in Tibet

注：基于审图号为藏S(2021)007号的标准地图制作，底图无修改。下同。

式计算得到，计算公式如下：

$$
\mathrm { E T } _ { \mathrm { 0 } } = \frac { 0 . 4 0 8 \Delta \big ( R _ { \mathrm { n } } - G \big ) + \gamma \frac { 9 0 0 } { T + 2 7 3 } U _ { \mathrm { 2 } } \big ( e _ { \mathrm { s } } - e _ { \mathrm { a } } \big ) } { \Delta + \gamma \big ( 1 + 0 . 3 4 U _ { \mathrm { 2 } } \big ) }
$$

式中： $\mathrm { E T _ { 0 } }$ 为潜在蒸散量； $R _ { \mathfrak { n } }$ 为地表净辐射 $( \mathrm { M J } \cdot \mathrm { m } ^ { - 2 }$ .$\mathbf { d } ^ { - 1 }$ ； $G$ 为土壤热通量 $( \mathrm { M J \cdot m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 } )$ $U _ { 2 }$ 为 $2 \mathrm { m }$ 高处风速 $\left( \mathbf { m } \cdot \mathbf { s } ^ { - 1 } \right)$ ; $e _ { \mathrm { s } }$ 为饱和水汽压 $\left( \mathrm { k P a } \right)$ ; $e _ { \mathrm { a } }$ 为实际水汽压$\left( \mathrm { { k P a } } \right) ; \Delta$ 为饱和水汽压曲线斜率 $\left( \mathrm { { k P a } } \cdot \mathrm { { ^ { \circ } C ^ { - 1 } } } \right)$ ； $\gamma$ 为干湿表常数 $\left( \mathrm { { k P a } } \cdot \mathrm { { ^ { \circ } C ^ { - 1 } } } \right)$ 。各因子具体计算公式参照文献[22]

# 1.2.2小波分析和突变分析

本文选用Morlet小波分析 $\mathrm { E T _ { 0 } }$ 在时频两域的变化特征[23]。Mann-Kendall的检验方法是非参数统计方法，该方法不易受异常值干扰，样本无需遵从一定的分布，可以用于对 $\mathrm { E T _ { 0 } }$ 的趋势显著性分析和突变检验[24]

1.2.3自然正交分解（EOF）自然正交函数（又称经验正交函数)，无固定的函数形式，图形是由场本身来决定的，它具有收敛快又能更好地反映出场的基本结构特征。EOF分析既可以取空间不同站点进行分解，也可以对同一站点的不同时间、不同高度等多种要素进行综合分析。EOF分解成的时间和空间部分，具有正交性的特点，用前几个方差贡献比较大的空间函数(模态)即可拟合出原矩阵的主要特征[25-26] C

1.2.4灰色模型预测灰色预测的基本思路是通过对某一个可看作灰色系统的研究对象，建立灰色模型进行预测。灰色系统模型的建立无需大量样本数据和有规律的样本分布，且工作量小预测精度高，逐渐被用于近期、短期以及中长期的系统预测[27]。本文基于Matlab实现灰色预测过程，包括对原始数据进行累加、构造累加矩阵与常数向量、求解灰参数以及将参数代人预测模型进行数据预测等内容[28]

# 2结果与分析

# 2.1 $\mathbf { E T _ { 0 } }$ 时空分布特征

2.1.1西藏 $\mathbf { E T _ { 0 } }$ 的变化特征近39a来西藏那曲中西部和沿江一线 $\mathrm { E T _ { 0 } }$ 的多年均值比较接近，分别为$6 6 3 . 2 5 ~ \mathrm { m m }$ 和 $7 2 8 . 9 1 \ \mathrm { m m }$ ,南部边缘和东南部 $\mathrm { E T _ { 0 } }$ 较接近，分别为 $5 1 0 . 1 4 ~ \mathrm { m m }$ 和 $5 3 7 . 4 2 ~ \mathrm { m m }$ ,而东北部最少，为 $4 3 6 . 2 8 ~ \mathrm { m m }$ 。全区年均 $\mathrm { E T _ { 0 } }$ 为 $5 9 7 . 1 2 \ \mathrm { m m }$ ，1981—2001年呈显著的减少趋势,2002—2019年呈显著的增加趋势 $\left( P < 0 . 0 1 \right)$ ），下降、上升率分别为$8 8 . 4 1 \ \mathrm { m m \cdot ( 1 0 a ) ^ { - 1 } \cdot 1 0 9 . 7 0 \ \mathrm { m m \cdot ( 1 0 a ) ^ { - 1 } } }$ （图2a）；2个不同时间段的高值区均分布在那曲中西部和沿江一线，其余研究区属于低值区（图 $2 \mathrm { b } \mathrm { \sim } \mathrm { c }$ （其他气候区图省略)。

2.1.2西藏年 $\mathbf { E T _ { 0 } }$ 的EOF分析运用经验正交函数(EOF)对西藏地区年 $\mathrm { E T _ { 0 } }$ 的标准值进行分解，分析结果表明，前5个特征向量特征值的累积贡献率达到$8 1 . 3 \%$ ，但只有前3个特征根的误差范围不重叠。通过North显著性检验，累积贡献率接近 $7 1 . 3 \%$ ，因此这3个特征根可以很好地解释西藏近 $3 9 \mathrm { ~ a ~ }$ 的 $\mathrm { E T _ { 0 } }$ 主要时空分布特征。第一模态(EOF1)特征向量的方差贡献率为 $5 1 . 5 \%$ ，在整个研究区域均为正值，表明1981—2019年西藏的年 $\mathrm { E T _ { 0 } }$ 变化趋势在空间上具有高度的一致性。年 $\mathrm { E T _ { 0 } }$ 高值中心位于沿江一线，低值中心位于南部地区，整体空间分布呈现出由中部中心向西南和东南逐步递减的分布特征(图3a)。

在经验正交函数(EOF)分解中，时间系数为正时，表现为西藏地区年ET增加。第一模态(EOF1)时间系数(图3d)可以看出，1981—1989年、2007年、2009—2010年、2012年、2014—2019年的时间系数大于零，表明这5个时段西藏地区年ET呈上升趋势，这与西藏年蒸散的变化趋势相吻合，反之，其他时间段年ET呈下降趋势。

第二模态(EOF2)的贡献率为 $1 2 . 1 \%$ ,西藏年$\mathrm { E T _ { 0 } }$ 在空间上表现为西藏中西部正值中心与西藏东南部负值中心呈相反的空间变化特征；正值主要分布在阿里地区、日喀则中西部和那曲市大部，其余为负值区(图3b)。再结合EOF2时间系数可以看出（图3e），1981—1990年主要表现为西藏中西部的$\mathrm { E T _ { 0 } }$ 减少，而东南部增加，1990—2005年东西部 $\mathrm { E T _ { 0 } }$ 减增交替变化，直到21世纪10年代中期开始出现相反的变化趋势,即西藏中西部ET大幅度增加，而西藏东南部呈递减趋势。

第三模态(EOF3)的贡献率为 $6 . 0 \%$ ,该模态下西藏 $\mathrm { E T _ { 0 } }$ 呈现中南、东南正值中心与西北部负值中心的分布特征；正值主要集中在昌都和林芝市大部、日喀则市中部及山南市东部，其余区域为负值区（图3c）。从EOF3时间系数发现（图3f)，1981—2019年EOF3时间系数在正负间振荡，表明西藏地区ET年际间的变化趋势显著。

# 2.2ET突变分析

2.2.1西藏年 $\mathbf { E T _ { 0 } }$ 变化趋势分析西藏地区38个站点1981—2019年年ETo的Kendall趋势系数空间分布如图4a，从图中可以看出，Kendall趋势系数为负值的气象站点有15个，其中贡嘎、隆子、八宿站 $\mathrm { E T _ { 0 } }$ 下降趋势非常显著，其Kendall趋势系数分别为$^ { - 4 . 6 3 } \cdot ^ { - 2 . 6 7 }$ 和-4.53。Kendall趋势系数为正值的台站共23个，占总站点数量的 $6 1 \%$ ，主要集中在那曲中西部和南部边缘地区，且西藏最长连续无降水日数的高值区主要位于干旱与半干旱气候区2，可见该区域气候出现了暖干化现象，这与王娜[3提出的"西藏部分地区呈现暖干化趋势(藏北、藏西北干旱、半干旱区）,气温升高带来蒸发量和干旱灾害大机率发生"观点相吻合；此外，狮泉河、聂拉木、拉萨、帕里、索县站和米林站的上升趋势均达到显著性水平 $( P _ { 0 . 0 5 } { = } 1 . 9 6 )$ 。

![](images/e9242ce27de7baca752212a22f41c6fc0268b8b1b22fd8a76c105da6f5f0d8ca.jpg)  
图2全区潜在蒸散量(ET)年际变化及空间变化  
Fig.2Interannual and spatial variations of $\mathrm { E T _ { 0 } }$ in the whole region

![](images/07ba7311336cb168c4a7a6dec117ca25a165f4022d9d12aa2892989d9392da58.jpg)  
图3西藏年ET的经验正交函数(EOF)模态分析 Fig.3EOF modal analysis of $\mathrm { E T _ { 0 } }$ in Tibet

2.2.2西藏年 $\mathbf { E T _ { 0 } }$ 突变分析利用Mann-Kendall方法对研究区38个气象站点进行突变分析，并结合滑动 $\mathbf { \chi } _ { t }$ 检验和Yamamoto法进行校验（图4b）。本文针对Yamamoto法，基于时间序列（1981—2019年），人为设置某一时刻为基准点，基准点前后长度分别取$n _ { 1 } = n _ { 2 } = 3 , n _ { 1 } = n _ { 2 } = 5$ ，结果发现仅那曲站和当雄站发生2次突变，20个站发生1次突变，其余站未发生突变。38个气象站点的突变年份中（表略），在20世纪80年代发生突变的台站最多（13个），其次是21世纪10年代(8个)。发生突变的站点主要分布在南部边缘地区、沿江一线和东北部，其中南部边缘地区所属站点全部发生突变，且出现年 $\mathrm { E T _ { 0 } }$ 上升的突变（除隆子站），表明该区域年 $\mathrm { E T _ { 0 } }$ 变化具有强敏感性；未发生突变的站点主要集中在那曲中西部。结合图4a可知，发生突变的Kendall系数正负值数量均等，表明这些站点的 $\mathrm { E T _ { 0 } }$ 经历了上升或下降变化，

# 2.3ET周期变化特征

为进一步了解西藏地区年ET的周期性，本文利用Morlet小波变换对1981—2019年全区及5大气候区年 $\mathrm { E T _ { 0 } }$ 时间序列进行分析，全区、沿江一线年均$\mathrm { E T _ { 0 } }$ 在30\~35a时间尺度振荡较为明显，表现为“正-负"交替，表明近39a来全区、沿江一线 $\mathrm { E T _ { 0 } }$ 经历了“偏大-偏小"交替过程;而在11a时间尺度也存在较为密集的正负交替，表明该区域 $\mathrm { E T _ { 0 } }$ 在短时间尺度上存在更多"偏大期"和"偏小期"(图5a、5c)。通过小波方差检验确定全区、沿江一线年均 $\mathrm { E T _ { 0 } }$ 在33a时间尺度上达最高小波方差，即为第一主周期，此外在11a的时间尺度上对应第二主周期（图 $5 \mathrm { g }$ 、5i)。那曲中西部年平均 $\mathrm { E T _ { 0 } }$ 在 $3 0 { \sim } 3 5 \mathrm { ~ a ~ } , 2 0 { \sim } 2 5$ a和3\~8a时间尺度呈现交替过程(图5b)，加之方差验证(图5h),第一主周期为 $3 3 \mathrm { ~ a ~ }$ ,第二、三主周期分别在22a和 $3 \mathrm { ~ a ~ }$ 。图5d表明南部边缘地区在30\~35a存在正负交替的周期振荡，而在8\~12a存在密集正负交替，进一步通过图5j可见，小波方差图有3个峰值，其3个主周期分别是33a、8a和 $1 2 \mathrm { ~ a ~ }$ 。图5e中，东北部大时间尺度在 $3 0 { \sim } 3 5 \mathrm { ~ a ~ }$ ，目前处于偏大时期，小时间尺度3\~8a较为密集，结合图5k来看， $3 3 \mathrm { ~ a ~ }$ 和8a分别是第一、二主周期。图5f显示东南部大时间尺度在 $3 0 { \sim } 3 5 \mathrm { ~ a ~ }$ ,小时间尺度 $3 { \sim } 5 \mathrm { ~ a ~ } , 8 { \sim } 1 2$ a时间尺度交替相对密集，通过图51检验，小波方差图有4个峰值,共4个主周期分别是 $3 3 \mathrm { a } , 2 2 \mathrm { a } , 1 2 \mathrm { : }$ a和 $5 \mathrm { ~ a ~ }$ 。

![](images/1959e787144bbe49612e73be37470c4956da44805742e86276b14b0ff1522360.jpg)  
干辛区地理  
图4西藏地区 $\mathrm { E T _ { 0 } }$ 的Kendall趋势系数和气象站点突变分布  
Fig.4 Kendall trend coefficient of $\mathrm { E T _ { 0 } }$ and mutation distribution of weather stations in Tibet

# 2.4灰色预测模型

灰色预测模型 $\mathrm { G M } ( 1 , 1 )$ 建立的条件，当且仅当灰参数 $a \in \left( - 2 , 2 \right)$ ,且原始序列的级比 $\sigma ^ { ( 0 ) } ( \textit { k } ) \in ( 0 . 1 3 5 3 ,$ 7.389)全部满足[31]。本文拟通过对1981—2019年全区38个站点年均 $\mathrm { E T _ { 0 } }$ 日期序列建立 $\mathrm { G M } ( 1 , 1 )$ 模型、级比和残差检验，得到各站点模型中的参数等结果(表1)。由表可见，该模型灰参数 $a \geq - 0 . 3$ 且 $a \in$ (-2.2)，加上级比是平滑的，符合灰色系统理论范畴;预测精度检验在 $8 0 \%$ 以上的站点有33个（25个三级、8个二级），占研究站点总数的 $8 7 \%$ ,故本文构建的 $\mathrm { G M } ( 1 , 1 )$ 模型适用于西藏年均ET日期序列的中长期预测。

剔除不合格建模的5个站点，分别构建全区及5大气候区的灰色模型(表略），并根据各预测模型分别得出西藏2020—2039年和2020—2050年年均$\mathrm { E T _ { 0 } }$ 的预测值。分析发现，东南部年均 $\mathrm { E T _ { 0 } }$ 有明显下降趋势，其他区域均呈现上升态势（南部边缘地区上升最快），且两组预测值的气候倾向率基本无变化。以上结论与赵俊芳等[32]在IPCC温室气体未来排放情景A2(国内或区域资源情景，其输出结果作为预测未来2011—2050年西藏地区干湿状况的输入数据)下得出“除零星地区外，西藏地区参考作物蒸散量均呈增加趋势，且增长幅度较大的地区位于日喀则市南部的边缘地带”相吻合。ET的变化必然是受到西藏气候的影响，最终其变化趋势将直接影响到当地的水资源及生态状况

# 3讨论

本文基于EOF分析、小波分析和灰色预测模型，深人研究西藏地区及5大气候区ET的时空演变规律及未来变化趋势。结果表明：西藏地区近39aET整体上呈上升趋势，1981—1988年处于ET大值区，1989年后处于低值区，2005年起又持续回升，这与张璐等[4]对锡林河流域、穆文彬等[7对若尔盖湿地、张娜等[19]对西藏ET得出的结论较一致，与拉巴等[9]对藏北那曲、钟巧等[]对博斯腾湖流域平原区

(a)全区 (b)那曲中西部2 42 220 0 40Qz100 1 40 0 -2 0s04008000008 0 -21985199019952000 20052010 2015小波系数 19851990 19952000 2005 2010 2015小波系数年份 年份(c)沿江一线 (d)南部边缘地区2 220 9 a 0 20 010 W d 08 8 -2 10 qx -20 00 000001985 1990 1995 2000 2005 2010 2015 小波系数 1985 1990 1995 2000 2005 2010 2015 小波系数年份 年份(e)东北部 (f)东南部  
2 2 0 2L 0 00.500 0 0 -2 y 00 100 O R o bec -2g 0 1 20 01985 1990 1995 2000 20052010 2015小波系数 1985 1990 1995 2000 2005 2010 2015小波系数年份 年份16(g)全区 10「 (h)那曲中西部 16「 (i)沿江一线1414  
美 美业 4 86 284 422 2八05 10 15 20 253035 40 05 10 1520 25303540 0510152025303540时间尺度/a 时间尺度/a 时间尺度/a10「(i)南部边缘地区 16 (k)东北部 7「 (l)东南部14 68 12美发业 6 8 美业 544 34 2220 51015202530 35 40 05101520 25303540 0 5 10 1520 25303540时间尺度/a 时间尺度/a 时间尺度/a

ET得出的结论不同，可见地域差异会对变化趋势产生一定的影响。西藏中西部为蒸散高值中心，在干旱、半干旱区，植被稀疏可能易导致强蒸发；西藏东南部的ET明显小于中西部地区，该区域多为森林和草原区，具有相对较好的植被分布以及湿润和半湿润气候，表现出ET低值区，这与杨永红等6对西藏高原区、曹雯等[33]对中国西北区大蒸散分布区域较吻合。

那曲中西部在2009年前呈缓慢下降趋势（图略），这与卓嘎等[34]关于藏西北地区潜在蒸散呈现显著减少趋势的结论基本吻合;沿江一线上升率极小，1981一2005年表现为不同程度的减小趋势（图

# 干旱区地理

表1各站点 $\mathbf { G M } ( \mathbf { 1 } , \mathbf { 1 } )$ 模型的参数和检验结果  
Tab.1 Parameters and test results of $\mathbf { G M } ( \mathbf { 1 } , \mathbf { 1 } )$ model at each site   

<html><body><table><tr><td rowspan="2">气候区</td><td rowspan="2">站点</td><td colspan="2">模型中的参数</td><td rowspan="2">预测精度/%</td><td rowspan="2">级比(</td><td rowspan="2">气候区</td><td rowspan="2">站点</td><td colspan="2">模型中的参数</td><td rowspan="2">预测精度/%</td><td rowspan="2">级比(</td></tr><tr><td>a</td><td>u</td><td></td><td>u</td></tr><tr><td>那</td><td>那曲</td><td>-0.0036</td><td>424.38</td><td>86.55</td><td>0.61~1.66</td><td>南部</td><td>聂拉木</td><td>a -0.0076</td><td>421.78</td><td>91.60</td><td>0.78~1.21</td></tr><tr><td>曲</td><td>班戈</td><td>-0.0016</td><td>657.56</td><td>89.71</td><td>0.62~1.51</td><td>边缘 地区</td><td>定日</td><td>-0.0025</td><td>670.98</td><td>88.46</td><td>0.80~1.31</td></tr><tr><td>中 西</td><td>申扎</td><td>0.0012</td><td>710.82</td><td>87.12</td><td>0.65~1.32</td><td></td><td>隆子</td><td>0.0037</td><td>752.32</td><td>93.24</td><td>0.80~1.19</td></tr><tr><td>部</td><td>当雄</td><td>-0.0043</td><td>443.73</td><td>81.01</td><td>0.58~1.63</td><td></td><td>错那</td><td>-0.0064</td><td>258.23</td><td>89.19</td><td>0.76~1.31</td></tr><tr><td></td><td>安多</td><td>0.0008</td><td>508.92</td><td>87.29</td><td>0.65~1.44</td><td></td><td>帕里</td><td>-0.0071</td><td>310.47</td><td>88.95</td><td>0.63~1.27</td></tr><tr><td></td><td>狮泉河</td><td>-0.0061</td><td>740.05</td><td>91.36</td><td>0.77~1.24</td><td>东</td><td>林芝</td><td>-0.0006</td><td>483.09</td><td>87.46</td><td>0.65~1.82</td></tr><tr><td></td><td>普兰</td><td>-0.0011</td><td>784.19</td><td>94.75</td><td>0.80~1.18</td><td>南 部</td><td>波密</td><td>-0.0034</td><td>353.26</td><td>87.46</td><td>0.77~1.35</td></tr><tr><td></td><td>改则</td><td>0.0003</td><td>862.05</td><td>92.26</td><td>0.78~1.37</td><td></td><td>察隅</td><td>0.0002</td><td>575.12</td><td>81.51</td><td>0.74~1.52</td></tr><tr><td>沿</td><td>拉萨</td><td>-0.0079</td><td>693.78</td><td>90.42</td><td>0.46~1.62</td><td></td><td>左贡</td><td>-0.0031</td><td>403.29</td><td>86.99</td><td>0.74~1.78</td></tr><tr><td>江 一</td><td>泽当</td><td>0.0047</td><td>1001.80</td><td>87.58</td><td>0.57~1.78</td><td></td><td>芒康</td><td>0.0007</td><td>467.01</td><td>85.04</td><td>0.66~1.27</td></tr><tr><td>线</td><td>日喀则</td><td>-0.0105</td><td>526.21</td><td>85.61</td><td>0.70~1.40</td><td></td><td>米林</td><td>-0.0034</td><td>327.10</td><td>90.58</td><td>0.79~1.31</td></tr><tr><td></td><td>江孜</td><td>0.0009</td><td>688.26</td><td>86.10</td><td>0.68~1.28</td><td></td><td>八宿</td><td>0.0073</td><td>1227.70</td><td>89.23</td><td>0.53~1.42</td></tr><tr><td></td><td>浪卡子</td><td>-0.0009</td><td>592.48</td><td>90.30</td><td>0.70~1.34</td><td>东</td><td>昌都</td><td>-0.0148</td><td>349.23</td><td>74.83</td><td>0.62~1.42</td></tr><tr><td></td><td>拉孜</td><td>-0.0003</td><td>884.31</td><td>79.57</td><td>0.46~1.62</td><td>北 部</td><td>丁青</td><td>-0.0055</td><td>321.21</td><td>79.52</td><td>0.68~1.84</td></tr><tr><td></td><td>尼木</td><td>-0.0060</td><td>514.40</td><td>63.90</td><td>0.60~1.87</td><td></td><td>索县</td><td>-0.0083</td><td>369.50</td><td>80.44</td><td>0.64~1.68</td></tr><tr><td></td><td>贡嘎</td><td>0.0113</td><td>924.95</td><td>88.36</td><td>0.56~1.35</td><td></td><td>嘉黎</td><td>-0.0038</td><td>298.42</td><td>87.83</td><td>0.73~1.39</td></tr><tr><td></td><td>墨竹工卡</td><td>-0.0012</td><td>792.12</td><td>88.23</td><td>0.71~1.32</td><td></td><td>比如</td><td>0.0059</td><td>427.13</td><td>83.81</td><td>0.66~1.21</td></tr><tr><td></td><td>加查</td><td>-0.0012</td><td>634.69</td><td>89.50</td><td>0.73~1.43</td><td></td><td>洛隆</td><td>0.0022</td><td>732.76</td><td>88.66</td><td>0.66~1.36</td></tr><tr><td></td><td>南木林</td><td>0.0063</td><td>678.85</td><td>59.13</td><td>0.44~1.44</td><td></td><td>类乌齐</td><td>0.0019</td><td>375.38</td><td>85.66</td><td>0.62~1.57</td></tr></table></body></html>

注：参数 $\textit { a } , \textit { u }$ 为 $\mathrm { G M } ( 1 , 1 )$ 预测模型待定系数;a为模型的发展系数； $u$ 为内生控制系数。

略），这与杜军等[15]1971—2005年西藏“一江两河”结论较为一致。文中EOF1下，“1981—1989年 $\mathrm { E T _ { 0 } }$ 呈增加态势、1990一2006年呈减少趋势"正好印证了毛飞等[7]对那曲市1961—2000年潜在蒸散“1983一1989年为偏高期、1989年以后为偏低期"的研究结论；相较唐小萍等2研究，拉萨ET呈明显增加趋势、江孜和泽当 $\mathrm { E T _ { 0 } }$ 分别表现不显著和显著的减少趋势与本文结论吻合，但日喀则结论相反，可能由于研究年份存在较大差别(1961—2009年）的缘故。Kendall趋势系数为正值的台站偏多，与杨永红等[1得出的结论相反，究其原因本文涉及38个站点均值，而杨永红研究选择的是5个不同年代际的7个典型站点，故各有缘由解释;38个站中发生突变的时间集中在20世纪80年代，与张娜等[19]得出的西藏各气候区Pettitt法突变结果基本吻合。

本文着重对西藏5大气候区 $\mathrm { E T _ { 0 } }$ 的变化特征、其突变性、周期性及未来ET的走势做了详尽分析，但由于当前西藏保持多年连续气象资料的国家标准气象监测站密度稀疏、空间分布不均，新增站点时间序列较短等因素，进行ET突变和周期性分析时会存在偏差，后续研究尤其是针对不同区域时应合理增加前期时间序列。另外，虽然本文构建的GM(1,1)预测模型大多通过残差检验，但均未达到一级(好)等级，且出现5个不合格的样点，后期需进行残差修正，以提高模型的适用性。

# 4结论

（1）本文选取38个站点相同时间序列最新数据，围绕西藏不同气候区进行 $\mathrm { E T _ { 0 } }$ 的相关研究，从时间尺度来看，西藏地区 $\mathrm { E T _ { 0 } }$ 多年平均值在1981—2001年时间段为 $5 8 8 . 0 5 ~ \mathrm { m m }$ ,下降速率为 $8 8 . 4 1 \ \mathrm { m m }$ $( 1 0 \mathrm { a } ) ^ { - 1 }$ ;在2002—2019年时间段为 $6 0 7 . 7 1 \ \mathrm { m m }$ ，上升速率为 $1 0 9 . 7 0 \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,且2个不同时间段的高蒸散区均集中在那曲中西部和沿江一线。从空间格局来看，西藏地区年 $\mathrm { E T _ { 0 } }$ 主要呈现由中部中心向西南和东南逐步递减的分布特征，高值中心集中在沿江一线，低值中心位于南部地区;其次在空间上表现为西藏中西部正值中心与西藏东南部负值中心反向的变化特征。

（2）正是由于增加了2013—2019年时间序列，Kendall趋势系数发生了较大变化，得出西藏地区贡嘎、隆子、八宿站ET下降趋势非常显著(Kendall趋势系数 $< - 1 . 9 6 \AA$ ；正值区主要集中在那曲中西部和南部边缘地区，且狮泉河、聂拉木、拉萨、帕里、索县站和米林站的上升趋势均达到显著性水平(Kendall趋势系数 ${ \mathrm { > } } 1 . 9 6$ )。那曲站和当雄站潜在蒸散量在1984年和2013年均发生2次突变，其余台站发生1次或未发生突变；发生突变的站点主要分布在南部边缘地区、沿江一线和东北部，时间集中在20世纪80年代。

(3）39a来全区、沿江一线潜在蒸散量的变化主要以33a和11a的周期震荡为主，那曲中西部具有 $^ { 3 3 } \mathrm { a } , 2 2$ a和3a主周期,南部边缘地区存在 $3 3 \mathrm { ~ a ~ }$ 8a和12a的周期，东北部显著周期出现在33a和$8 \mathrm { ~ a ~ }$ ，东南部则在 $3 3 \mathrm { a } , 2 2 \mathrm { a } , 1 2 \mathrm { : }$ a和5a产生。

（4）首次利用灰色系统理论预测未来 $\mathrm { E T _ { 0 } }$ ，预测结果显示，东南部年均ET有明显下降趋势，其他区域均呈现上升态势。

# 参考文献(References)

[1]曹永强,肖春柳,李元菲.河北省春季潜在蒸散量变化特征与成 因[J].水土保持研究,2019,26(5):195-209.[Cao Yongqiang, Xiao Chunliu,Li Yuanfei. Charcteristics and causes of potential evapotranspiration in spring in Hebei Province[J].Research of Soil and Water Conservation,2019,26(5): 195-209.] [2] 徐宗学.水文模型[M].北京:科学出版社,2009.[Xu Zongxue. Hydrological modelling[M].Beijing:Meteorological Press,2009.] [3] Brutsaert W,Parlange MB.Hydrologic cycle explains the evaporation paradox[J]. Nature,1998,396(6706): 30. [4] 张璐,朱仲元,张圣微,等.近59a锡林河流域潜在蒸散发及地 表干湿状况变化趋势分析[J].干旱区地理,2020,43(4):997-   
1003.[Zhang Lu,Zhu Zhongyuan,Zhang Shengwei,et al. Trends of potential evapotranspiration and surface wet conditions in the Xilin River Basin in recent 59 years[J].Arid Land Geography,   
2020,43(4): 997-1003. [5] 赵志平,吴晓莆，李果,等.2009—2011年我国西南地区旱灾程 度及其对植被净初级生产力的影响[J].生态学报,2015,35(2):   
350-36O.[Zhao Zhiping,Wu Xiaofu,Li Guo,etal.Drought severity and its impact on vegetation net primary productivity in southwest China from 2009 to 2011[J].Acta Ecologica Sinica,2015,35 (2): 350-360.] [6] 秦鹏程,刘敏,刘志雄,等.湖北省潜在蒸散估算模型对比[J].干 旱气象,2014,32(3):334-339.[Qin Pengcheng,Liu Min,Liu Zhixiong,et al.Comparison of potential evapotranspiration estimation models in Hubei Province[J].Journal of Arid Meteorology,2014, 32(3): 334-339.]   
[7]穆文彬,孙素艳,马伟希,等.若尔盖湿地潜在蒸散量演变特征 及影响因素分析[J].高原气象,2019,38(4):716-724.[Mu Wenbin,Sun Suyan,Ma Weixi, etal.Analysis on evolution characteristics and influencing factors on evapotranspiration of Zoige wetland [J]. Plateau Meteorology,2019,38(4): 716-724.]   
[8]Wilber L Q,Ricardo Z B,Pedro,et al.Can artificial neural networks estimate potential evapotranspiration in Peruvian highlands? [J].Modeling Earth Systems and Environment,2019,5(4):1911- 1924.   
[9]拉巴,除多,德吉央宗.基于SEBS 模型的藏北那曲蒸散量研究 [J].遥感技术与应用,2012,27(6): 919-926.[La Ba,Chu Duo, Deji Yangzong.Studyonevapotranspiration in northern Tibet based on SEBS model[J].Remote Sensing Technology and Application,2012,27(6): 919-926.]   
[10] 钟巧,焦黎,李稚,等.博斯腾湖流域潜在蒸散发时空演变及归 因分析[J].干旱区地理,2019,42(1):103-112.[Zhong Qiao,Jiao Li,Li Zhi,et al.Spatial and temporal changes of potential evapotranspiration and its attribution in the Bosten Lake Basin[J].Arid Land Geography,2019,42(1): 103-112.]   
[11]Allen R G,Pereira L S,Raes D, et al. Crop evapotranspiration: Guidelines for computing crop water requirements[R].FAO Irigation and Drainage Pape 56,Rome,1998.   
[12]Song X Y,Lu F, Xiao W H,et al.Performance of 12 reference evapotranspiration estimation methods compared with the PenmanMonteith method and the potential influences in northeast China [J]. Meteorological Applications,2019,26(1): 83-96.   
[13]Yang Y,Chen R S,Song Y X,etal. Sensitivity of potential evapotranspiration to meteorological factors and their elevational gradients in the Qilian Mountains,northwestern China[J]. Journal of Hydrology,2019,568: 147-159.   
[14] Zhao YF,Zou XQ, Cao L G,et al. Spatiotemporal variations of potential evapotranspiration and aridity index in relation to influencing factors over southwest China during 1960—2013[J]. Theoretical and Applied Climatology,2018,133(3-4): 711-726.   
[15] 杜军,边多,拉巴,等.1971—2005年西藏主要农区农田蒸散量 变化特征及其与环境因子的关系[J].冰川冻土,2009,31(5): 815-821.[DuJun,Bian Duo,La Ba,etal.Changesinevapotranspiration in the main agriculture areas of central Tibet and its relation to the environment factors in 1971—2005[J]. Journal of Glaciology and Geocryology,2009,31(5): 815-821.]   
[16] 杨永红,张展羽,阮新建.西藏参考作物蒸发蒸腾量的时空变异 规律[J].水科学进展,2009,20(6): 775-781.[Yang Yonghong, Zhang Zhanyu,Ruan Xinjian. Spatiotemporal variation of reference evapotranspiration in Tibet[J].Advances in Water Science, 2009, 20(6): 775-781.]   
[17]毛飞,卢志光,张佳华,等.近40年那曲地区气候特征分析[J]. 高原气象,2007,26(4): 708-715.[Mao Fei,Lu Zhiguang, Zhang

# 干旱区地理

Jiahua,et al.Analysis on climate characteristics in Naqu in recent   
40 years[J]. Plateau Meteorology,2007,26(4): 708-715.] [18] 何慧根,胡泽勇,荀学义,等.藏北高原季节性冻土区潜在蒸散 和干湿状况分析[J].高原气象,2010,29(1):10-16.[He Huigen, Hu Zeyong, Xun Xueyi, et al. Analysis on potential evaptranspiration and dry-wet conditions in seasonal frozen soil region of northern Tibetan Plateau[J].Plateau Meteorology,2010,29(1): 10-16.] [19] 张娜,金建新,佟长福,等.西藏参考作物蒸散量时空变化特征 与影响因素[J].干旱区研究,2017,34(5):1027-1034.[Zhang Na, Jin Jianxin,Tong Changfu,et al. Spatiotemporal variation of evapotranspiration of referred crops and the affcting factors in Tibet[J].Arid Zone Research,2017,34(5): 1027-1034.] [20] 唐小萍,罗礼洪,卓玛,等.气候变化对西藏雅鲁藏布江中游地 区潜在蒸散量的影响分析[J].高原山地气象研究,2011,31(3):   
49-53.[Tang Xiaoping,Luo Lihong, Zhuo Ma, et al. Impact analysis of climate change on potential evapotranspiration over midstream of Yarlung Zangbo River in Tibetan Plateau[J].Plateau and Mountain Meteorology Research,2011,31(3): 49-53.] [21] 温克刚,刘光轩.中国气象灾害大典(西藏卷)[M].北京:气象出 版社,2007: 21-25.[Wen Kegang,Liu Guangxuan. Encyclopedia of Chinese meteorological disasters (Tibet Volume)[M].Beijing: Meteorological Press,2007: 21-25.] [22] 甘臣龙.基于作物生育期的潜在蒸散的时空演变特征及R/S分 析[J].西藏科技,2015(5):53-56,59.[Gan Chenlong.Spatiotemporal evolution characteristics and R/S analysis of potential evapotranspiration based on crop growth period[J]. Tibet Science and Technology,2015(5): 53-56,59.] [23] 李红瑛,薛羽,曹二佳,等.近50年来乌兰察布市水分盈亏量时 空变化特征[J].干旱区资源与环境,2019,33(12):145-151.[Li Hongying,Xue Yu,Cao Erjia,et al.Spatiotemporal variation characteristics of waterdeficit in Ulanqab during the latest 5O years[J]. Journal of Arid Land Resources and Environment,2019,33(12):   
145-151.] [24]Liu HJ,LiY,JosefT,etal. Quantitativeestimatioofclimatecnge effects on potential evapotranspiration in Beijing during 1951—2010 [J]. Journal of Geographical Sciences,2014,24(1): 93-112. [25]Jung J. Spatial analysis of the vulnerability to meteorological hazards in Korea[J]. Journal of Climate Research,2018,13(3): 211-229. [26]赵峰,毕硕本,李兴宇,等.基于EOF和REOF的1470—1911年 黄河中下游地区旱涝空间分布特征分析[J].干旱区地理,   
2019,42(4): 799-809.[Zhao Feng,Bi Shuoben,Li Xingyu,et al. Spatial characteristics of drought/flood disasters based on EOF and REOF in the middle and lower reaches of the Yellow River[J]. Arid Land Geography,2019,42(4): 799-809.]   
[27] Cheng ML,Shi G J, Xiang M Y.On the improvement of the parameter estimation of the grey model GM(1,1) and model application [J]. Communications in Statistics-Simulation and Computation, 2020, 49(5): 1367-1384.   
[28] 郭建平,陈玥煜,赵俊芳.新疆棉花热量指数的灰色预测方法 [J].干旱区地理,2010,33(5): 710-715.[Guo Jianping,Chen Yueyi, Zhao Junfang.Grey forecasting model of heat index of coton in Xinjiang[J]. Arid Land Geography,2010,33(5): 710-715.]   
[29] 张核真,尼玛吉,多吉次仁.近50年西藏最长连续无降水日数 变化特征[J].中国农学通报,2016,32(35):151-154.[Zhang Hezhen,Ni Maji,Duoji Ciren.Variation characteristics of the longest continuous no-precipitation days in Tibet in recent 5O years[J]. Chinese Agricultural Science Bulletin,2016,32(35): 151-154.]   
[30] 王娜.对构建西藏生态安全屏障的几点思考[J].西藏发展论坛, 2011(3):43-46.[Wang Na. Some thoughts on the construction of ecological security barrier in Tibet[J]. The Theoretical Platform of Tibetan Development,2011(3): 43-46.]   
[31] 史战红,刘敏,牛雪娜.基于灰色预测的甘南农牧民收入趋势分 析[J].甘肃科学学报,2019,31(6):8-11.[Shi Zhanhong,Liu Min, Niu Xuena.Trend analysis of incomes and herdsmen in Gannan Tibetan Autonomous Prefecture based on grey prediction[J]. Journal of Gansu Sciences,2019, 31(6): 8-11.]   
[32] 赵俊芳,郭建平,房世波,等.未来气候情景下西藏地区的干湿 状况变化趋势[J].中国农业气象,2011,32(1):61-66.[Zhao Junfang, Guo Jianping,Fang Shibo,et al. Trends of Tibet’s dry-wet condition under future climate scenario[J]. Chinese Journal of Agrometeorology,2011,32(1): 61-66.]   
[33] 曹雯,申双和,段春锋.中国西北潜在蒸散时空演变特征及其定 量化成因[J].生态学报,2012,32(11):3394-3403.[Cao Wen, Shen Shuanghe, Duan Chunfeng. Temporal-spatial variations of potential evapotranspiration and quantification of the causes in northwest China[J].Acta Ecologica Sinica,2012,32(11): 3394-3403.]   
[34]卓嘎,尼玛央珍,唐小萍.1980—2009年西藏西北部潜在蒸散 时空分布特征及其影响因素[J].干旱区研究,2016,33(4):698- 707.[Zhuo Ga, Nima Yangzhen, Tang Xiaoping. Spatiotemporal distribution of potential evapotranspiration and its influencing factors in northwest Tibet from 198O to 2009[J].Arid Zone Research, 2016,33(4): 698-707.]

# Variation characteristics of potential evapotranspiration and the forecast of grey model in Tibet

SHI Jiqing'， BIAN Duo'， YANG Feiyun²， GAN Chenlong³， FAN Dongliang²(1.Tibet ClimateCenter,Lhasa85oo,Tibet,China;2.China MeteorologicalAdministrationTrainingCentre,Beijing10081,China;3.Maizhokunggar Meteological Bureau, Lhasa 85Oooo,Tibet, China)

Abstract: This paper aims to provide a scientific basis for water-saving irrigation,the rational allocation of water resources,and drought monitoring in Tibet, China.We use the Penman-Monteith model,trend analysis,Morlet wavelet analysis,Mann-Kendall tests,theempirical orthogonal function,andgray models to explore the spatiotemporal evolution of potential evapotranspiration (ETo) in Tibet and thecentral and western regions of Nagqu as wellas the trend of future $\mathrm { E T _ { 0 } }$ changes based on daily meteorological data collected from 1981 to 2019 at 38 meteorological stations in the region. The results demonstrate that on the time scale, the average $\mathrm { E T _ { 0 } }$ in Tibet is $5 9 7 . 1 2 ~ \mathrm { m m }$ . It also exhibited a significant decreasing trend from 198l to 2O01 and a significant increasing trend from 2002 to 2019 $( P { < } 0 . 0 1 )$ ). In these two distinct time periods, high evapotranspiration was concentrated in the central and western areas of Nagqu and along the river line. In the first mode (EOF1),the annual $\mathrm { E T _ { 0 } }$ change trend in Tibet had a high degree of consistency in space,mainly exhibiting a gradually decreasing distribution fromthe center of the central area to the southwest and southeast.The high-value center is concentrated along the river line,and the low-value center was located in the southern region. Concerning space,the positive center of central and western Tibet and the negative center of southeastern Tibet are reversed.The stations with positive Kendalltrend coeffcients are mainly concentrated in the central and western regions of Nagqu and the southern marginal area, where the climate has been warming and drying.The sites exhibiting abrupt changes in annual $\mathrm { E T _ { 0 } }$ are mainly distributed in the southern marginal area along the river line and the northeast and were concentrated in time.In the 198Os,two mutations occurred in the potential evapotranspiration at Nagqu and Dangxiong stations,whereas one or no mutations occurred at each of the remaining stations.The annual average $\mathrm { E T _ { 0 } }$ both of Tibet as a whole and of the five major climate zones exhibited an increasing trend (except in the southeast),and the 33 year cyclic oscillation was the first main cycle. Additionally, there was a cycle of11 ain the whole region and along the river line.The midwest of Nagqu had cycles of 22 a and $3 \mathrm { ~ a ~ }$ ,the southern marginal area had cycles of 8 a and $1 2 \mathrm { ~ a ~ }$ ，the northeast had a cycle of $8 \mathrm { ~ a ~ }$ ，and the southeast had main cycles of 22 a and 12 a. The constructed gray model (GM; 1,1) used for prediction had gray parameters $a { \geqslant } - 0 . 3$ and $a \in ( - 2 , 2 )$ ,and the level ratio was in a smooth state,meaning it can be used to predict future $\mathrm { E T _ { 0 } }$ . The average prediction accuracy was $8 7 . 8 5 \%$ , so we predicted the medium- and long-term average annual $\mathrm { E T _ { 0 } }$ date series for Tibet. The forecast results revealed that except for the significant decline in the forecast value of the annual $\mathrm { E T _ { 0 } }$ in the southeast, all other regions are exhibiting an upward trend, and the southern edge shows the steepest increase.

Key words: Penman-Monteith model; evapotranspiration; spatiotemporal analysis； grey model; Tibet