# 黄河流域夜晚灯光数据与经济发展时空格局演变分析

张远生1，曹智伟²，\*，韦蔚²，胡洁²，金鑫²(1.天津大学，天津300072;2.黄河勘测规划设计研究院有限公司，河南 郑州 450003)

摘要：系统性掌握黄河流域经济发展时空格局演变规律能为整个流域高质量发展提供重要决策依据。目前，GDP是衡量经济发展格局的主要参考依据，然而GDP统计数据存在口径不统一、空间分辨率低等缺点，难以精准刻画经济发展的时空演变格局特征。夜晚灯光数据以其相对客观的特征，对其进行有效反映。本文通过对1992-2013年全国夜晚灯光数据的校正和处理，获得全国及流域夜晚灯光数据影像，进行经济空间聚合分析，以及与相关因子进行对比分析。研究结果表明：经济空间聚合高的区域分布在黄河河道附近，从黄河上游到下游，热力强度逐渐增强，并且以省会城市为核心区，向外扩散，呈现了在老的聚合点聚合度加剧的情况下，聚合区域有向周边分散的趋势；夜晚灯光数据的变化趋势与GDP的变化趋势具有一定的相似性，并且与城镇化率、人口数量、第三产比例、人均公园绿地面积、流域发展指数（Basin Development Index，BDI）具有一定的相关性；流域9省的夜晚灯光数据整体变化趋势与全国灯光数据的变化趋势基本一致，呈稳定上升的趋势，但整体值均低于全国的夜晚灯光数据，并且差距有所扩大，黄河流域高质量发展迫在眉睫。

关键词：夜晚灯光数据；黄河流域；时空格局；经济发展

中图分类号：

文献标识码：A

# 1引言

黄河流域是一个复杂的巨系统，由河流子系统、生态环境子系统和人类经济子系统组成，涉及自然、经济、社会、生态等各方面的要素，各个子系统之间存在协同、竞争、博弈等关系，为解决国家重大问题提供基础保障。人类经济子系统作为其中的重要组成部分，主要涉及经济、三产、人口等因素，常规的的评价模式是以GDP单一指标为主，如何对其空间格局发展情况进行客观评价，需要新的方法和客观指标来支撑经济的发展趋势研究。早期对于经济发展时空格局演变研究，王维等人运用综合评价模型法对长江经济带地级及以上城市经济、环境、社会发展水平及区域发展水平进行时空定量分析，赵明华等人运用熵权TOPSIS信息熵法确定指标权重，运用ESDA法进行山东省17地市空间集聚性和差异性分析2，何伟纯等人运用Theil指数、探索性空间分析和多元线性回归等方法研究2005—2014年河南省县域经济的时空差异、格局演变以及动力机制，Chung等基于SES（SocialEconomicStatus）方法和政府统计数据测度了1976-2010年香港各区之间的经济发展差异，以上主要以GDP、人均收入等统计数据表征经济发展水平，存在统计数据存在口径不统一、可比价换算复杂等问题，而且统计数据一般为均质的面板数据，空间分辨率较低，难以表现行政区内部经济发展的空间异质性。因此，借助更客观、尺度更精细的数据有助于更全面地研究经济发展的时空格局特征。

夜间灯光数据能探测到地球表面发出的亮光，是研究人类活动的有效数据源。DMSP卫星传感器可获取来自城市、乡镇及其他有持久光源的场所，且去除了云、光火及油气燃烧等偶然噪声影响的稳定夜间灯光影像[4。国内外的学者对此进行了大量的研究，主要集中在城市空间信息提取扩展研究、城市空间特征灯光数构建研究、人口密度及热岛效应研究、经济发展状况研究、电力能源消耗量研究以及城市化对生态环境影响研究等方面[5]，其中，郭恒梅等人基于4年的DMSP/OLS夜间灯光数据，选

用加权标准差椭圆、引力模型与社会网络分析等方法,对淮海经济区经济空间格局演化与城市中心性进行测度。李建忠[7等人利用回归分析以及修正后重力模型，定量分析赣南与闽西地区夜间灯光数据与社会经济数据之间的关系，但对于流域级别，特别是与水相关要素的相关性分析，鲜见报道。

本文首次以黄河流域为研究对象，结合黄河生态保护和高质量发展的国家战略，宏观分析了夜晚灯光数据在反演经济时空格局演变中重要作用，揭示了经济发展与流域要素的相关密切关系，为黄河流域经济格局研究提供相对客观的参考依据。

# 2数据源与数据校正

# 2.1数据源

本次研究涉及使用数据包括3类：矢量数据、栅格数据和统计数据，数据具体参数如下表1所示：

表1数据主要参数  

<html><body><table><tr><td>数据类型</td><td>数据名称</td><td>数据来源</td><td>比例尺/分辨率</td><td>数据时间</td></tr><tr><td rowspan="3">矢量数据</td><td>全国省级行政区</td><td></td><td>1:100万</td><td></td></tr><tr><td>划</td><td></td><td></td><td></td></tr><tr><td>流域界 DMSP/OLS夜晚灯</td><td>美国国家海洋和大气管</td><td>1:100万</td><td></td></tr><tr><td>栅格数据</td><td>光数据</td><td>理局</td><td>1km</td><td>1992-2013</td></tr><tr><td rowspan="6">统计数据</td><td>GDP</td><td>各省统计年鉴</td><td></td><td>1992-2013</td></tr><tr><td>流域用水总量</td><td>《中国水资源公报》</td><td></td><td>1992-2013</td></tr><tr><td>城镇化增长率</td><td>各省统计局官方网站近 四十年统计年鉴</td><td></td><td>1992-2013</td></tr><tr><td>第三产比例</td><td>各省统计局官方网站近</td><td></td><td>1992-2013</td></tr><tr><td>人均公园绿地面</td><td>四十年统计年鉴</td><td></td><td></td></tr><tr><td></td><td>各省统计局官方网站近</td><td></td><td>1992-2013</td></tr><tr><td></td><td>积</td><td>四十年统计年鉴</td><td></td><td></td></tr><tr><td></td><td>典型区域湿地面</td><td>根据Landsat卫星遥感</td><td></td><td></td></tr><tr><td></td><td>积变化率</td><td>影像解译得到</td><td></td><td>1992-2013</td></tr></table></body></html>

栅格影像数据主要使用美国国防气象卫星（Defense Meteorological Satellite Program,DMSP）搭载的业务型线扫描传感器（Operational Linescan System,OLS）获取的数据。由于其独特的光电放大能力使其能在夜间探测到地表微弱的近红外辐射，因此，该传感器获取的夜间灯光影像被越来越多的用来研究人类活动。

但传感器获取的数据不能直接使用，因为传感器在获取地表信息的过程中会受到大气层的吸收和散射、太阳高度角、地形起伏度、传感器校准[8等因素的影响，所以，不同传感器获取的同一年度的影像之间有差异，同时不同传感器在获取影像时没有进行星上辐射校正[9]，造成了同一个卫星传感器获取的连续不同年度的影像间相同位置的像元值之间存在异常波动。长时间序列的DMSP/OLS夜间灯光影像数据集存在的这些问题导致多传感器获取的不同年度的影像间没有连续性，因此，该数据集在长时间尺度的应用研究时，必须进行相互校正。另外，由于传感器光谱分辨率的限制，城市中心区域的像元值存在饱和现象，稳定灯光影像像元DN值是6-bit量化，直接决定了DN值范围是0\~63，造成了影像中很多区域特别是城市中心区域DN值到达63以后就不再上升达到饱和状态，城市中心地带的差异不明显。因此需要对夜光数据进行校正，主要包括影像的相互校正和饱和校正、影像间连续性校正。

早在 20 世纪90 年代，Hall等[10]和Lenney 等[]在研究中提出在连续的多时相的遥感影像中存在相对稳定的像元，而其可提取作为不变的目标区域（其在多时相的遥感影像之间存在一种特定的转换关系)。2009 年，Elvidge 等[9以 Sicily 为不变动的参考区域，以F121999为参考数据集，将待校正影像与F121999参考数据集进行比较建立回归方程。该方法较适用于全球夜间灯光数据的校正，对于某一国家尺度的适用性不强。2012年LIU $Z ^ { [ 1 2 ] }$ 等，卢秀[13]等提出了适合中国区域的夜间灯光影像的校正方法，统计分析了中国主要城市1992一2008 年的GDP 统计数据和建成区面积数据，确定黑龙江省的鸡西市为校正中国区域的不变动参考区域，实现长时间序列DMSP/OLS夜间灯光数据的相互校正、年内融合和年际间校正。

# 2.2数据校正

# （1）数据预处理

搜集到的稳定灯光数据的范围为全球数据，坐标系统为WGS84，分辨率为30”。针对中国区和流域九省区进行了裁剪。

（2）相互校正与饱和校正

影像的相互校正和饱和校正，通过选取不变目标区域的方法，使用辐射定标产品数据中的合适年份合适传感器的数据，对待校正影像进行二次回归模型计算，完成校正工作。根据卢秀[13]等人的研究，确定黑龙江省的鸡西市为不变区域，选取已经经过饱和校正的辐射定标产品数据中的2006年F16传感器数据作为参考数据集，1992-2013年34期待校正的稳定灯光影像作为待校正数据集，使用鸡西市范围进行裁剪，分别统计DN值，进行二次回归模型计算，如公式（1）所示。

$$
\mathrm { D N c { = } a { * } D N ^ { 2 } { + } b { * } D N { + } c }
$$

式中，DN表示待校正稳定灯光影像像元DN值；DNc表示校正后的稳定灯光影像像元DN值；a、b、c表示不同的回归参数。为保证稳定灯光影像中的无灯光值区域（DN值 $\scriptstyle = 0$ ）在校正前后保持一致，对DN值等于0的像元进行掩膜处理，不参与公式（1）的计算。通过公式（1）计算出稳定灯光影像二次回归模型的模型参数，对稳定灯光影像进行饱和校正、相互校正。

# （3）年内融合校正

出现年内数据重叠的年份为1994年和1997-2007年，对重叠年份数据，进行像元值比较计算，如果两个年份对应的像元值都为0，则该像元的DN值为0，否则取两个年份像元值的平均值为该像元的值。如公式（2）所示。

$$
D N _ { ( n , i ) } = \left\{ \begin{array} { l r } { 0 \qquad } & { D N _ { ( n , i ) } ^ { a } = 0 \mathrm { ~ } \mathcal { H } D N _ { ( n , i ) } ^ { b } = 0 } \\ { \left( { D N _ { ( n , i ) } ^ { a } + D N _ { ( n , i ) } ^ { b } } \right) } & { \mathrm { ~ } \mathcal { H } \mathcal { H } \mathrm { ~ } } \end{array} \right.
$$

式中， $D N _ { ( n , i ) } ^ { a }$ ， $D N _ { ( n , i ) } ^ { b }$ 分别表示第 $\mathfrak { n }$ 年相互校正后的 2个不同传感器获取的夜间灯光影像中的 $\mathrm { ~ i ~ }$ 像元的 DN 值； $D N _ { ( n , i ) }$ 表示校正后的第n 年影像中i像元的DN 值。

（4）年际间校正

对于年际间校正，根据中国城市化程度不断加剧的情况，可假设在前一年影像中探测为城市斑块的亮值像元在后一年影像中不能消失[4]，因此，可假设前一年的夜间灯光影像中的亮值像元，在后一年影像中相同位置的像元依然保持为亮值像元，前一年夜间灯光影像中的亮值像元的DN值，应不大于后一年影像中相同位置的亮值像元DN值[12]。当后一年影像中的像元DN 值等于0时，前一年的影像中相同位置的像元DN也应该等于0;当后一年影像中的像元DN值不等于0时，前一年影像中的像元DN值应不大于后一年影像中的相同位置像元DN值。校正方程公式（3）所示：

$$
D N _ { ( n , i ) } = \left\{ \begin{array} { l l } { 0 \qquad } & { D N _ { ( n + 1 , i ) } = 0 } \\ { D N _ { ( n - 1 , i ) } \qquad } & { D N _ { ( n + 1 , i ) } > 0 \mathscr { L } D N _ { ( n - 1 , i ) } > D N _ { ( n , i ) } } \\ { D N _ { ( n , i ) } \qquad } & { \mathscr { R } \mathscr { L } } \end{array} \right.
$$

式中， $D N _ { ( n - 1 , i ) }$ 、 $D N _ { ( n , i ) }$ 、 $D N _ { ( n + 1 , i ) }$ 分别表示经过相互校正、饱和校正、年内融合后 的夜晚灯光影像的 $\mathrm { ~ i ~ }$ 像元的DN值。

（5）影像校正结果

经过对1992-2013 年34 期待校正的稳定灯光影像进行相互校正、饱和校正、年内融合、年际间校正等处理，形成的22年时间序列的夜晚灯光影像产品，并使用中国国界范围（不包含南海诸岛）和黄河流域9省范围进行分别裁剪，得到流域及流域九省的夜晚灯光影像最终产品。由于篇幅有限，仅对1992年和2013年处理前后的影像进行展示（如图1、图2所示)，并且对校正前后的DN值累计值进行统计（如图3所示)，可以看出：校正前的夜晚灯光数据具有离散型，通过相互校正与饱和校正、年内融合校正、年际间校正夜晚灯光数据呈稳定的上升状态，连续性得到有效改善。

![](images/d81b124b08d01556e6fc2b1cb0a1829bf10feab894eb11755a0fe51cb05adcb4.jpg)  
（a）1992全国校正前 （b）1992全国校正后

![](images/9dd39a49f0095c0da76b25be6a76c3326b79fe3433ada6bbe90a62e64ce04b99.jpg)  
（c）1992流域九省校正后

![](images/f7cceb60143ab58a405a391623120e9b84a6bdb6f5d4b0e4943ec71af402295d.jpg)  
图1校正前后1992年全国及流域九省夜晚灯光数据影像

![](images/a2c7e49100d345b5f22e7835981d2c14d34a69095fa2bf373b8b9d455e7d536f.jpg)  
图2校正前后2013年全国及流域九省夜晚灯光数据影像

# 3研究方法

![](images/73b4b516ce7b57727d94e451af83dc8523f27cee14419f277dea07121b515911.jpg)  
图3校正前后亮度像元总DN值对比图  
图41992-2013年核密度分析图

热力图（HeatMap）是通过密度函数进行可视化用于表示地图中点的密度的热图。强调空间位置和基本的空间分布特征。它使人们能够独立于缩放因子感知点的密度。点要素核密度分析用于计算每个输出栅格像元周围的点要素的密度。每个点上方均覆盖着一个平滑曲面。在点所在位置处表面值最高，随着与点的距离的增大表面值逐渐减小，每个输出栅格像元的密度均为叠加在栅格像元中心的所有核表面的值之和，即热力高的地方说明当地的夜晚灯光比较密集，热力中心的转移说明了夜晚灯光密集区的转移。核函数以Silverman 的著作°（1986 年版，第76页，equation4.5）中描述的四次核函数为基础。

(1) 未加权距离计算，如公式（4）所示：

$$
\begin{array} { r } { S D = \sqrt { \frac { \sum _ { \bar { i } = 1 } ^ { n } ( x _ { \bar { i } } - \bar { X } ) ^ { 2 } } { n } } + \sqrt { \frac { \sum _ { \bar { i } = 1 } ^ { n } ( y _ { \bar { i } } - \bar { Y } ) ^ { 2 } } { n } } + \sqrt { \frac { \sum _ { \bar { i } = 1 } ^ { n } ( z _ { \bar { i } } - \bar { Z } ) ^ { 2 } } { n } } } \end{array}
$$

其中：xi、yi和zi是要素i的坐标；{X，Y， $\bar { z } \}$ 表示要素的平均中心； $\mathfrak { n }$ 等于要素总数。

(2） 带宽计算，如公式（5）所示：

$$
\begin{array} { r } { { S e a r c h R a d i u s } = 0 . 9 * \operatorname* { m i n } \left( S D , \sqrt { \frac { 1 } { I n ( 2 ) } } * D _ { m } \right) * n ^ { - 0 . 2 } } \end{array}
$$

其中：Dm 是（加权）平均中心的（加权）中值距离； $\mathbf { n }$ 是没有使用 population 字段的点数，如果提供了population字段，则 $\mathbf { n }$ 是population 字段值的总和；SD 是标准距离。（3）新（x，y）位置的预测密度由以下公式（6）确定：

$$
\begin{array} { r } { D e n s i t y = \frac { 1 } { ( r a d i u s ) ^ { 2 } } { \sum _ { i = 1 } ^ { n } } \left[ \frac { 3 } { \pi } * p o p _ { i } ( 1 - ( \frac { d i s t _ { i } } { r a d i u s } ) ^ { 2 } ) ^ { 2 } \right] } \end{array}
$$

其中： $\mathrm { i } { = } 1 , . . . , \mathrm { ~ n ~ }$ 是输入点。如果它们位于（x，y）位置的半径距离内，则仅包括总和中的点；popi是i点的 population 字段值，它是一个可选参数；disti 是点i和（x，y）位置之间的距离。

通过对反映经济空间聚合的核密度分析图（如图4）进行对比分析，可以看出：流域九省，核密度高值区集中在黄河沿岸，从黄河上游到下游，热力强度逐渐增强，并且以省会城市为核心区，向外扩散；随着时间的推进，高密度分布区域不断扩大，说明随着人口的增加和经济的发展，经济空间聚合越来越密集；中密度分布区在不断向外扩张，说明经济空间聚合区在逐渐分散化。

# 3.2相关性分析

（1）与GDP相关性分析

![](images/f1215eae4bab797755df839b14d1ab3bf4055b768a4900ed653d7e88affb9e4e.jpg)  
（a）1992年

![](images/d1d3cbe9d737336b2d352748b43390a8eb9670a61e2cee134565a6ea378e3bee.jpg)  
图51992、2013年流域九省灯光指数与GDP对比图

对黄河流域9省的GDP数据与夜晚灯光数据进行比较（由于篇幅有限，仅展示1992年和 2013年的对比图，如图5)，相同年份的夜晚灯光数据与GDP 对比，显示夜晚灯光数据的变化趋势与GDP的变化趋势具有一定的相似性；不同年份的夜晚灯光数据与GDP的变化对比，显示随着经济的快速发展，城市扩张，人口数量增加，夜晚灯光数据有了很大的提高，与GDP的增长幅度基本一致。

（2）与不同评价指标相关性分析

![](images/2885fbdd5f80d4bd7d5af695eb2cfb24fc4afe05bd2d0cd59cf635fdb631b7a0.jpg)  
(a） 流域九省夜晚灯光变化趋势

![](images/d13bdccb8d54acfda144fc494f807cc1e3e67359f00ec1b926d9af26bcdb65ab.jpg)  
（b）流域九省用水总量变化趋势

![](images/74ff8d4790d873b4710188cfe11e1075d4b01849553288fdb8976f130d624417.jpg)  
（c）流域九省城镇化率变化趋势

![](images/018a9b928904fea4750d73c136b5a3c568c350fa9b2f5613c36757df0db0aeea.jpg)  
（d）流域九省人口总量变化趋势

![](images/1c134d6e418284b6c4571a19f19fab61ce36727fd663790d77678565e1b3889f.jpg)  
图6不同评价指标相关性分析图

对1992-2013年流域九省夜晚灯光数据与用水总量数据变化趋势进行对比（如图6)，发现相关性不大：流域夜晚灯光数据成平稳的上升趋势，而流域用水总量先是缓慢的下降后，在2003年出现断崖式下降后，又逐年缓慢上升，可能黄河流域的用水控制政策有关；与城镇化率、人口数量、第三产比例、人均公园绿地面积变化趋势基本相似，呈逐年缓慢上升状态。

![](images/869240524fe5beb3a54b785e85ab3adbaaa94944dab492ab12b5084fb2e71d7e.jpg)  
（3）流域夜晚灯光数据与全国夜晚灯光数据相关性分析  
图7流域九省夜晚灯光数据与全国夜晚灯光数据对比图

黄河流域9省的夜晚灯光数据与全国灯光指数进行对比分析（如图7)，发现流域9省的夜晚灯光数据整体变化趋势与全国灯光指数的变化趋势基本一致，呈稳定上升的趋势；但流域9省的夜晚灯光数据整体值均低于全国的夜晚灯光数据，并且差距有所扩大，说明黄河流域9省经济发展相对滞后，可能与黄河的水资源短缺有关，黄河流域自古以来人口众多，相对贫困，黄河流域高质量发展迫在眉睫。

（4）流域夜晚灯光数据与BDI流域发展指数相关性分析

![](images/a7221dbc9b7e98ae5a7a0d0e04ec23a503bece0d8f8aae954a565e07d6423bbc.jpg)  
图8BDI变化趋势

BDI流域发展指数是分析流域发展情况的一个综合性指标，通过对多因素系统为表征发展质量提供参考依据。经过黄河流域9省的夜晚灯光数据与BDI流域发展指数对比（如图8)，可以看出，两者具有很强的相关性，变化趋势基本相似，呈稳定上升趋势，说明人类经济活动对流域发展质量产生了很大的影响。

# 4结果及分析

黄河流域是一个复杂巨系统，包括了自然、经济、社会、生态等各方面的要素。随着人类活动的加剧，系统的不确定性增加。用经济高质量发展，提升人民幸福感为宗旨的角度，评价社会经济发展质量的社会发展指数尤为重要。流域夜晚灯光数据在黄河流域的应用，是宏观尺度下，从新的客观视角对社会发展类指数的量化补充，不仅可以表征人类经济子系统的发展情况，而且与河流健康指数和环境演变指数一起组成流域发展指数体系，进而表征流域发展巨系统的发展情况，为新时期综合治理、系统治理、源头治理，统筹推进各项工作提供决策依据。

# 5结论与讨论

本次研究是夜晚灯光数据首次在黄河流域的应用，通过对1992-2013年全国夜晚灯光数据的相互校正、饱和校正、年内融合、年际间校正获了相对准确的全国夜晚灯光数据影像。经过流域九省夜晚灯光数据与流域内各省社会发展类指数对比，以及全国与流域九省的夜晚灯光数据的对比分析，得到以下结论：

（1）相同年份，夜晚灯光数据的变化趋势与GDP的变化趋势具有一定的相似性；不同年份间，夜晚灯光数据有了很大的提高，与GDP的增长幅度基本一致；并且与城镇化率、人口数量、第三产比例、人均公园绿地面积、流域发展指数 BDI具有一定的相关性。

（2）经济空间聚合高的区域分布在黄河河道附近，从黄河上游到下游，热力强度逐渐增强，并且以省会城市为核心区，向外扩散，呈现了在老的聚合点聚合度加剧的情况下，聚合区域有向周边分散的趋势。

（3）流域9省的夜晚灯光数据整体变化趋势与全国灯光指数的变化趋势基本一致，呈稳定上升的趋势；但流域9省的夜晚灯光数据整体值均低于全国的夜晚灯光数据，并且差距有所扩大，黄河流域高质量发展迫在眉睫。

夜晚灯光数据具有长时间序列性、易获得性、客观性，是流域巨系统中客观评价经济发展质量的重要客观指标之一，为客观分析流域发展质量提供重要参考依据。如何深挖夜晚灯光数据背后隐藏的价值，更好地辅助流域水资源合理配置，可以作为下一步的研究重

# 点。

参考文献：[1] 王维，陈云,王晓伟，文春生.长江经济带区域发展差异时空格局研究[J].长江流域资源与环境,2017,26(10):1489-1497.[2 赵明华，郑元文.近10年来山东省区域经济发展差异时空演变及驱动力分析[J].经济地理，2013，33(01):79-85.[3]Chung RY,LaiFT,Chung GK,etal.Socioeconomicdisparityinmortalityriskswidenedacrossgenerations duringapideconomic development in Hong Kong:Anage-period-cohortanalysis from1976to 2010[J].Annals of Epidemiology,2018,28(11):743-752.[4]Elvidge CD,Baugh KE,KihnEA,etal.Mappingcitylightswith nightime data fromtheDMSPoperational lin-escansystem [J]. Photogrammetric Engineering and Re-mote Sensing,1997, 63(6):727-734.[5]王鹤饶，郑新奇，袁涛.DMSP/OLS 数据应用研究综述[J].地理科学进展，2012，31(01):11-19.[6]郭恒梅，马晓冬.基于夜间灯光数据的淮海经济区经济空间格局演化及中心性测度[J].地理与地理信息科学，2020,$3 6 ( 0 2 ) ; 3 4 - 4 0 + 1 2 5$ [7] 李建忠，郑著彬，张润飞，林琳，杨虹.赣南与闽西地区经济空间格局的夜光遥感研究——以原赣南、闽西苏区为例[J].赣南师范大学学报，2020，41(03):83-90.[8] 张鹏强，余旭初，刘智，等.多时相遥感图像相对辐射校正[J].遥感学报，2006，10(3):339-344.[9]ELVIDGECD,ZISKIND,AUGHKE,etal.Afifteen yearrecordof global natural gas glaringderivedfromsatelitedata[J].Energies，2009，2(3) :595-622.[10] HallFG,StrebelDE,Nickeson JE,etal.Radiometricrectification-toward acommonradiometricresponseamongmultidate, multisensor images [J]. Remote Sensing of Environment, 1991,35(1):11-27.[1]Leney MP,WoodcockCE,ColinsJB,etal.The statusof agricultural lands inEgypt: Theuseof multitemporal NDVIfeatures derived from Landsat TM[J]. Remote Sensing of Environment, 1996,56(1):8-20.[12]Liu Z,He C,ZhangQ,et al.Extracting the dynamicsof urban expansionin China usingDMSP-OLS nightimelightdatafrom 1992 to 2008 [J].Landscape and Urban Planning,2012,106(1):62-72.[13]卢秀，李佳，段平，等.中国区域 DMSP /OLS 夜间灯光影像的校正[J].测绘通报，2019(7):127-131.DOI:10.13474/j.cnki.11-2246.2019.0234.[14]何春阳，史培军，李景刚，等.基于DMSP/OLS 夜间灯光数据和统计数据的中国大陆 20 世纪90年代城市化空间过程重建研究 [J].科学通报，2006，51(7):856-861.[15]Bernard. W. Silverman.Density Estimation for Statistics and Data Analysis [M].CRC Press:2018-02-19.

（通讯作者：曹智伟 E-mail：zhiwei.cao@outlook.com）

# Evolution analysis of nightlight data and economic development spatio-temporal pattern in the Yellow River Basin

ZHANG Yuansheng¹，CAO Zhiwei²\*，WEI Wei²，HU Jie²，JIN Xin² （1.Tianjin university,Tianjin 300072，China; 2.Yellow River Engineering Consulting Co.,Ltd, Zhengzhou 450o03,China)

Abstract: It is an important decision-making basis for the high-quality development of the whole basin in mastering the evolution of the spatio-temporal pattern in the economic development of the Yellow River Basin systematically. At present, GDP is the main reference to measure the pattern of economic development, however， GDP statistics have the disadvantages of not uniform caliber and low spatial resolution, it is difficult to accurately characterize the evolution pattern of economic development in space and time. The nightlight data reflect it effectively with its relatively objective characteristics. Through the correction and processing of the national nightlight data from l992 to 2013, this paper obtains the national and watershed nightlight data images,conducts economic spatial aggregation analysis, and compares and analyzes the relevant factors. The results show that the areas with high economic spatial aggregation are distributed near the Yellow River channel， from the upper reaches to the lower reaches of the Yellow River， the heat intensity is gradually increasing， and the provincial capital city is the core area， spreading outwards, showing the tendency of the polymerization area to disperse to the surrounding area under the condition that the polymerization of the old polymerization point is intensified; The basin development index BDI has a certain correlation， the overall trend of nightlight data in 9 provinces of the basin is basically consistent with the change trend of the national nightlight data, showing a steady upward trend, but the overall value is lower than the national nightlight data, the high-quality development of the Yellow River basin is imminent.

Key words: nightlight data; the Yellow River Basin; the spatio-temporal pattern； economy development

# 作者贡献声明：

张远生：提出研究思路，设计研究方案；  
曹智伟：论文起草；  
韦蔚：采集、清洗和分析数据；  
胡洁，金鑫：论文最终版本修订。