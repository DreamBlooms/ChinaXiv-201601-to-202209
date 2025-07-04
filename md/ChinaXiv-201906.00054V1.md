# 基于指数分析法的乌鲁木齐市居住格局研究

柳雨杉¹，董晔1,2（1新疆师范大学地理科学与旅游学院,新疆乌鲁木齐830054;2新疆师范大学丝绸之路经济带城市发展研究中心,新疆乌鲁木齐830054)

摘要：乌鲁木齐作为新疆的首府城市，是中国西部地区重要的经济中心，在我国城市体系格局中发挥着重要的作用，通过研究乌鲁木齐市人口居住格局对乌鲁木齐城市空间规划提供指导。以乌鲁木齐市为研究区域，利用城市空间的扩展印证居住空间格局变化宏观特征，将“居住格局”作为切入点,利用莫兰指数并借助ArcGIS技术分析该区域不同属性人口的居住格局。结果显示：乌鲁木齐市城市居民用地主要沿西北方向的新市区延伸、西山方向扩展、沿东山方向扩展，并沿着老城区的外缘扩展；不同年龄人口中学龄人口和老年人口的聚集现象较为明显，劳动人口的聚集现象并不显著，不同受教育程度人口中小学及初中人口和大专以上人口比重指标Moran's【值较高，文盲人口比重指标Moran's $I$ 值相对较低，高中人口在空间上呈现负相关;2000—2016年所有区域学龄人口、老年人口空间分异指数都有所上升，劳动人口分异指数在沙依巴克区和水磨沟区有所下降，说明老龄化现象越来越明显，1990—2000年文盲人口在头屯河区处于相对分异状态,2000—2010年在新市区分异水平较高，1990—2010年小学及初中人口、高中人口以及大专以上人口分异现象逐渐减少，混居程度加深，居住分异现象减少。

关键 词：居住格局；空间分异；莫兰指数；乌鲁木齐市文章编号： 1000 -6060(2019)03-0698-08(0698\~0705)

居住格局是指特定区域内不同属性人口在空间上的排列与组合，是各属性人口居住的一种空间分布,反映了人存在的空间属性[1]。它反映一种属性所有成员在居住地点与另一个属性成员相互接触的机会[2-3]。我国对空间居住格局的研究大多是在发达与沿海城市[4-I],而西部地区研究也主要是在西安、呼和浩特、银川等城市[12-15]。然而乌鲁木齐市居住空间[16-18]的研究主要是空间演化历史[19]、居住空间分异[20-21]和城市区划[22],对于居住空间格局尚未进行系统定量研究。本文利用城市空间的扩展印证居住空间格局变化宏观特征，运用指数分析法并借助ArcGIS技术，对乌鲁木齐市居住空间格局从全局和局部进行测度定量研究，对其他城市居住格局研究和城市主体功能区的建设具有十分重要的参考意义。

# 1 研究范围及研究方法

# 1.1 研究范围

本文选取乌鲁木齐市天山区、沙依巴克区、水磨沟区、新市区和头屯河区，数据主要来源于乌鲁木齐市第四次（1990年）、第五次（2000 年）及第六次(2010年）人口普查分街道数据、乌鲁木齐市1990—2017年统计年鉴等相关统计资料;遥感数据为Landsat5TM影像和Landsat8OLI_TIRS影像，街道行政图来自乌鲁木齐市行政区划图，各街道面积数据利用Arcgis10．4提取得到。

# 1.2 研究方法

城市化进程中，居住空间规模的扩大往往与主城区在空间上的蔓延是同步的，而城市的扩展对早期形成的传统聚居区带来不小的冲击。GIS空间分析方法可以有效地印证研究城市空间的扩展和居住空间格局的宏观特征。

![](images/f5ff69ff259011bc52224c4ad384e05513cce0688d5d304329b7f1557ea45933.jpg)  
图1乌鲁木齐市研究区范围图Fig.1Research areas in Urumqi

（1）土地利用变化速率依据全国土地资源分类系统，结合研究区土地利用现状，通过监督分类，并进行精度验证，解译获得1990 年和2017年乌鲁木齐市4种土地利用类型，经过分类后运算，得到土地利用变化的定量数据。计算区域内土地利用变化，在土地利用转移矩阵的基础上，建立了土地利用变化速率模型[23]，其公式为：

$$
v = { \frac { S _ { b } - S _ { a } } { S _ { a } } } \times { \frac { 1 } { T } } \times 1 0 0 \%
$$

式中： $S _ { a } \ : , S _ { b }$ 分别为1990年和2017年某一种类型的数量， $T$ 为研究的年时， $\boldsymbol { v }$ 为研究时段内某一种类型的年变化速率。

(2)全局Moran's $I$ 指数全局Moran's $I$ 指数用以度量相邻空间分布对象属性值之间的关系。取值范围为[-1.0,1.0]，Moran's $I > 0$ 表示空间事物的属性值分布具有正相关性，Moran's $I < 0$ 表示空间事物的属性值分布具有负相关性，Moran's $I = 0$ 值表示空间事物的属性值不存在空间关系，即空间随机分布[24]。计算公式为：

$$
I = \frac { n \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } w _ { i j } ( y _ { i } - \bar { y } ) \left( y _ { j } - \bar { y } \right) } { ( \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } w _ { i j } ) \sum _ { i = 1 } ^ { n } \left( y _ { i } - \bar { y } \right) ^ { 2 } }
$$

全局Moran's $I$ 统计方法首先假设研究对象之间不存在任何空间相关性，然后通过 $Z$ -score得分检验假设是否成立。一般 $Z \mid > 2 . 5 8$ 时，拒绝零假设，即在 $9 9 \%$ 的概率下,研究对象之间存在空间自相关。

(3）空间分异指数又称本地化指数，是我国社会学者和城市地理学者分析居住空间分异通用指标[25]。空间分异指数的数学公式为：

$$
D \ = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \mid X _ { i } - Y _ { i } \mid } { 2 } } \quad ( i = 1 , 2 , \cdots , n )
$$

其中：

$$
X _ { i } \ = \frac { \displaystyle x _ { i } } { \displaystyle \sum _ { I + 1 } ^ { n } x _ { i } } \qquad Y _ { i } \ = \ \frac { \displaystyle y _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } y _ { i } }
$$

$D$ 表示分异指数， $i$ 表示统计数据的基本单元，$X _ { i }$ 指区域 $i$ 中 $x$ 群体(维、汉、回)居民人数占所有调查区域同一民族人口数的百分比, $Y _ { i }$ 表示居住于区域 $\mathbf { \chi } _ { i }$ 中其他群体人口数占所有调查区域其他民族人口数的百分比。 $D$ 的结果范围为0到 $^ { 1 , D } = 0$ 表示完全没有分异， $D = 1$ 代表完全分异， $D$ 值越大，居住空间分异度越大。

# 2主城区居住空间扩展研究

本文利用ENVI5.1软件对多期遥感影像以地面控制点为依据进行几何精校正和配准、波段合成、图像增强、图形裁剪等预处理，并对遥感影像的多光谱数据进行辐射定标，再利用FLAASH模块进行大气校正，以消除一些大气的影像的干扰。经过分类后运算，得到1990—2017年土地利用转移矩阵(表1)。

人口增长是城市规模扩大的根本原因，因此在土地利用类型中，居民用地所占比例最大，在城市空间扩展过程中，居民用地的分异现象也较明显。由表1可知，1990—2017年乌鲁木齐市区内居民用地面积有大幅度增加，而未利用地面积呈缩减趋势。居住用地面积年平均增长速率达 $4 . 8 0 \%$ ,这一变化主要来源于原城区外围未利用地向居民用地的转化。通过对1990年和2017年期间乌鲁木齐市城市居民用地进行叠加分析，得到乌鲁木齐市 $2 7 \ a$ 的居民用地扩展情况（图2）。

从图2分析发现，随着城市扩展居民用地面积也相应扩大，市中心居民用地密度明显比新城区高，在城市发展过程中，居民用地向新城扩展的趋势较为明显，根据乌鲁木齐市 $2 7 \ a$ 城市居民用地发展方向和趋势，乌鲁木齐城市空间扩展主要沿西北方向的新市区延伸、西山方向扩展、沿东山方向扩展，并沿着老城区的外缘扩展。城市的西北部和北部与农

# 表11990—2017年土地利用类型转移矩阵

Tab.1 Change matrix of land use in Urumqi from1990 to 2017   

<html><body><table><tr><td></td><td>绿地 面积</td><td>水体 面积</td><td>居民用 地面积</td><td>未利用 地面积</td><td>总 面积</td></tr><tr><td>水体面积</td><td>0.2</td><td>3.1</td><td>0.14</td><td>0.82</td><td>4.26</td></tr><tr><td>绿地面积</td><td>116.85</td><td>0.19</td><td>22.42</td><td>99.35</td><td>238.82</td></tr><tr><td>居民用地面积</td><td>65.48</td><td>0.48</td><td>107.55</td><td>106.98</td><td>280.49</td></tr><tr><td>未利用地面积</td><td>17.76</td><td>0.21</td><td>12.68</td><td>197.32</td><td>227.97</td></tr><tr><td>总面积面积</td><td>200.47</td><td>3.98</td><td>143.25</td><td>408.77</td><td>0</td></tr><tr><td>面积差值</td><td>39.61</td><td>0.28</td><td>137.58</td><td>-180.77</td><td>0</td></tr><tr><td>土地利用迁移 概率／%</td><td>19.76</td><td>6.94</td><td>96.04</td><td>-44.22</td><td>0</td></tr></table></body></html>

![](images/8cbab0f18647cace3417ee06a394239b0683b7dfa31a94fd700e9ebdd9d7be45.jpg)  
图21990—2017年乌鲁木齐市城市扩展情况Fig.2Urban expansion in Urumqi form 1990 to 2017

业区相连，城市空间的扩展阻力较小，趋势更加明显。2017年郊区居民用地明显扩大，表明城镇化正在向郊区发展。东北部的扩张受地形的影响，城市扩展明显受到抑制，扩张力度较弱。乌鲁木齐城市空间扩展的特点：

（1）地形条件下独特的发散式扩展变化，乌鲁木齐市是干旱区绿洲上形成的特大城市，城市的扩展顺应着水土资源与地形的约束[26]。乌鲁木齐地势起伏悬殊，南部、东北部高，中部、北部低，三面环山，城市形态受河谷地形的限制，呈北宽南窄的T字形，建成区北部的冲积平原目前是城市扩展的主要方向。

(2）城市空间扩展受到指向城市中心和指向交通路线的两种向心力，向心力来自工业化过程中的分工利益、规模经济、节约交易费用与土地投入等。交通线路成为空间扩展的伸展轴，对城市空间扩展有指向作用，使城市空间由集中走向分散、由市中心化走向郊区化。乌鲁木齐城市用地主要沿老城中心向外扩展，并向北部的新城区扩展，交通干线周围的土地也较先转化为居民用地。

(3)城市扩展出现内部填充阶段，资源的有限性及阶段性发展空间的有限性是导致城市向外扩展受到限制的主要门槛，扩展的能力受到分工利益、制度创新和技术进步的影响，城市用地在沿市中心、交通路线向外扩展的同时进行内部填充和更新，例如老城区改造、棚户的拆建、主体功能区的建设等。

# 3主城区居住格局研究

# 3.1 不同年龄人口居住格局

3.1.1全局空间自相关学龄人口、劳动人口、老年人口比重指标得分Moran's $I > 0$ ,虽然 Moran's $I$ 值相对较低，但三个指标值都 $> E ( I )$ ,说明不同年龄人口比例指标都存在空间自相关，即各指标都存在聚居现象，劳动人口聚集区域没有学龄人口和老年人口比重显著(表2）。

3.1.2空间分异指数由表3可知乌鲁木齐市各区不同年龄人口的居住空间分异：

（1）2000年学龄人口的空间分异指数平均值为0.089，其中水磨沟区的空间分异指数为0.141，处于相对分异水平；2016年学龄人口空间分异指数平均值处于0.116，处于中度分异状态。2000—2016年学龄人口空间分异指数上升了0.027，所有区域学龄人口空间分异指数都有所上升。

（2）2000年劳动人口的空间分异指数平均值为0.073，处于低度分异状态，其中天山区的劳动人口空间分异指数为0.016，说明劳动人口基本没有分异现象;2016年劳动人口空间分异指数平均值为0.073，其中新市区劳动人口空间分异指数达到0.173，处于中度分异状况。2000—2016年劳动人口空间分异指数上升了0.028，但是沙依巴克区和水磨沟区空间分异指数有所下降。

（3）2000年老年人口的空间分异指数平均值为0.097，其中沙依巴克区老年人口的空间分异指数为0.135，处于相对分异水平;2016年老年人口空间分异指数平均值为0.203，头屯河区老年人口空间分异指数达到0.316，处于中高度分异水平。2000—2016年老年人口空间分异指数平均值上升了0.105，所有区域老年人口空间分异指数都有所上升，说明老龄化现象越来越明显。

# 3.2不同受教育程度人口居住格局

3.2.1全局空间自相关文盲人口、小学及初中人口、大专人口比重指标得分Moran's $I > 0$ ,高中人口比重指标Moran's $I < 0$ ,但三个指标值都大于 $E ( I )$ ，说明不同受教育程度人口比例指标都存在空间自相关，即各指标都存在聚居现象（表4）。

各指标的空间自相关存在显著的差异性。小学及初中人口比重、大专以上人口比重指标Moran's $I$ 值较高，在0.13以上;文盲人口比重指标Moran'sI值相对较低，在0.09左右，高中人口在空间上呈现负相关，表明高中人口聚集区域没有小学及初中人口和大专人口比重显著。

Tab.2 Global Moran's I index of different age populations in Urumc   

<html><body><table><tr><td>指标</td><td>Moran's I</td><td>E(I)</td><td>VAR(I)</td><td>Z - score</td><td>P</td></tr><tr><td>学龄人口人口比重</td><td>0.067 532</td><td>-0.015 385</td><td>0.006 308</td><td>1.455 321</td><td>0.014 521</td></tr><tr><td>劳动人口人口比重</td><td>0.059 880</td><td>-0.015 385</td><td>0.004 173</td><td>0.104 728</td><td>0.916 502</td></tr><tr><td>老年人口人口比重</td><td>0.067 532</td><td>-0.015 385</td><td>0.005 842</td><td>1.333 566</td><td>0. 182 437</td></tr></table></body></html>

表2乌鲁木齐市不同年龄人口全局自相关指数表  
表32000和2016年乌鲁木齐市各区不同年龄人口空间分异指数  
ab.3Spatial Differentiation Index of different ages in Urumqi form 2ooo and 201   

<html><body><table><tr><td rowspan="2">研究区域</td><td colspan="2">学龄人口空间分异指数</td><td rowspan="2">时段差值 2000—2016</td><td colspan="2">劳动人口空间分异指数</td><td rowspan="2">时段差值 2000—2016</td><td colspan="2">老年人口空间分异指数</td><td rowspan="2">时段差值 2000—2016</td></tr><tr><td>2000</td><td>2016</td><td>2000</td><td>2016</td><td>2000</td><td>2016</td></tr><tr><td>天山区</td><td>0.016</td><td>0.108</td><td>0.092</td><td>0.016</td><td>0.064</td><td>0.047</td><td>0.016</td><td>0.175</td><td>0.159</td></tr><tr><td>沙依巴克区</td><td>0.093</td><td>0.108</td><td>0.015</td><td>0.073</td><td>0.066</td><td>-0.007</td><td>0.135</td><td>0.134</td><td>-0.001</td></tr><tr><td>新市区</td><td>0.083</td><td>0.166</td><td>0.083</td><td>0.083</td><td>0.173</td><td>0.090</td><td>0.083</td><td>0.203</td><td>0.120</td></tr><tr><td>水磨沟区</td><td>0.141</td><td>0.081</td><td>0.034</td><td>0.141</td><td>0.101</td><td>-0.040</td><td>0.141</td><td>0.185</td><td>0.044</td></tr><tr><td>头屯河区</td><td>0.076</td><td>0.117</td><td>0.041</td><td>0.050</td><td>0.099</td><td>0.049</td><td>0.111</td><td>0.316</td><td>0.205</td></tr><tr><td>平均</td><td>0.089</td><td>0.116</td><td>0.027</td><td>0.073</td><td>0.101</td><td>0.028</td><td>0.097</td><td>0.203</td><td>0.105</td></tr></table></body></html>

Tab.4Global Moran's Iindex of different education levels in Urumqi   
表51990、2000 和2010年乌鲁木齐市各区不同受教育程度人口空间分异指数  

<html><body><table><tr><td>指标</td><td>Moran's I</td><td>E(I)</td><td>VAR(I)</td><td>Z-score</td><td>P</td></tr><tr><td>文盲人口比重</td><td>0. 097 674</td><td>-0.015 385</td><td>0.00 0742</td><td>4.149 459</td><td>0.000033</td></tr><tr><td>小学及初中人口比重</td><td>0.136 283</td><td>-0.015 385</td><td>0.000 748</td><td>5.546 126</td><td>0.000 000</td></tr><tr><td>高中人口比重</td><td>-0.000 027</td><td>-0.015 385</td><td>0.000 734</td><td>0.566 749</td><td>0.000 885</td></tr><tr><td>大专以上人口比重</td><td>0.186 829</td><td>-0.015 385</td><td>0.00 0747</td><td>7.399 154</td><td>0.000000</td></tr></table></body></html>

表4乌鲁木齐市不同受教育程度人口全局自相关指数表  
Tab.5Spatial Differentiation Index of diferent education levels in Urumqi form199o,2oo0 and 201   

<html><body><table><tr><td rowspan="2">研究区域</td><td colspan="3">文盲人口空间分异指数</td><td colspan="3">小学及初中人口空间分异指数</td><td colspan="3">高中人口空间分异指数</td><td colspan="3">大专以上人口空间分异指数</td></tr><tr><td>1990</td><td>2000</td><td>2010</td><td>1990</td><td>2000</td><td>2010</td><td>1990</td><td>2000</td><td>2010</td><td>1990</td><td>2000</td><td>2010</td></tr><tr><td>天山区</td><td>0.016</td><td>0.066</td><td>0.202</td><td>0.016</td><td>0.082</td><td>0.284</td><td>0.016</td><td>0.028</td><td>0.124</td><td>0.016</td><td>0.139</td><td>0.276</td></tr><tr><td>沙依巴克区</td><td>0.130</td><td>0.206</td><td>0.279</td><td>0.468</td><td>0.221</td><td>0.210</td><td>0.071</td><td>0.124</td><td>0.098</td><td>0.324</td><td>0.358</td><td>0.278</td></tr><tr><td>新市区</td><td>0.083</td><td>0.102</td><td>0.487</td><td>0.113</td><td>0.221</td><td>0.155</td><td>0.049</td><td>0.110</td><td>0.100</td><td>0.255</td><td>0.275</td><td>0.193</td></tr><tr><td>水磨沟区</td><td>0.096</td><td>0.150</td><td>0.128</td><td>0.061</td><td>0.168</td><td>0.128</td><td>0.050</td><td>0.103</td><td>0.042</td><td>0.086</td><td>0.278</td><td>0.151</td></tr><tr><td>头屯河区</td><td>0.213</td><td>0.346</td><td>0.216</td><td>0.085</td><td>0.420</td><td>0.128</td><td>0.197</td><td>0.468</td><td>0.274</td><td>0.164</td><td>0.482</td><td>0.312</td></tr><tr><td>平均</td><td>0.108</td><td>0.174</td><td>0.262</td><td>0.149</td><td>0.222</td><td>0.181</td><td>0.077</td><td>0.166</td><td>0.127</td><td>0.169</td><td>0.307</td><td>0.242</td></tr></table></body></html>

3.2.2空间分异指数由表5可知乌鲁木齐市各区不同受教育程度人口的居住空间分异：

（1）1990年文盲人口的空间分异指数平均值为0.108，其中头屯河区的文盲人口相对处于分异状态，1990—2000 年期间文盲人口空间分异指数上升了0.066;2000 年，文盲人口空间分异指数平均值处于0.174,其中头屯河区的空间分异指数上升了0.133，处于中度分异状态，文盲人口空间分异指数在2000—2010年期间上升了0.088，其中新市区的空间分异指数上升了0.385，处于中高度分异水平。

（2）1990年小学及初中人口的空间分异指数平均值为0.149，其中沙依巴克区小学及初中人口的空间分异指数为0.468，1990—2000 年期间空间分异指数下降了0.247;2000 年小学及初中人口空间分异指数平均值为0.222，处于中度分异状态；小学及初中人口空间分异指数在2000—2010年期间下降了0.041，但天山区的小学及初中人口空间分异指数上升了0.202，说明小学及初中人口分异现象有所加剧。

（3）1990年所有区域高中人口空间分异指数小于0.200，高中人口空间分异指数在1990—2000年期间上升了0.089;2000年高中人口空间分异指数在头屯河区为0.468，相对于其他区域是最高，处于中高度分异状态，高中人口空间分异指数在2000—2010 年期间下降了0.039，其中头屯河区高中人口空间分异指数下降了0.194，说明高中人口分异现象逐渐缓解。

（4）1990年大专以上人口的空间分异指数的平均值为0.169，其中沙依巴克区的大专以上人口空间分异指数高达0.324，处于中度分异，其次新市区的大专以上人口空间分异指数为0.255，1990—2000 年期间大专以上人口空间分异指数上升了0.138；2000年大专以上人口空间分异指数平均值为0.307，处于中度分异状态，大专以上人口空间分异指数2010年下降了0.065，并且大部分区域的下降趋势较为显著，说明这期间大专以上人口的混居程度加深，居住分异现象减少。但天山区的大专以上人口空间分异指数上升了0.137，说明该区域大专以上人口还处于分异状态。

# 4结论

本文基于乌鲁木齐市人口普查及统计数据，借助ArcGIS10.4、ENVI5.0软件，对乌鲁木齐市居住格局进行定量研究，主要得到以下结论。

（1）受到地形、地貌、资源和环境等因素的影响，乌鲁木齐基本上沿着乌鲁木齐河向城北冲积平原扩展。乌鲁木齐市居住空间扩展的特点主要沿西北方向的新市区延伸、沿西山方向扩展、沿东山方向扩展，并沿着老城区的外缘独特的发散式扩展变化特征。

（2）不同年龄人口比例指标都存在空间自相关，即存在聚集现象，劳动人口聚集区域没有学龄人口和老年人口比重显著;不同受教育程度人口比例指标也存在聚集现象，小学及初中人口比重、大专以上人口比重指标Moran'sI值较高，文盲人口比重指标 Moran'sI值相对较低，高中人口在空间上呈现负相关,高中人口聚集没有小学及初中人口和大专人□比重显著。

（3）2000—2016年所有区域学龄人口空间分异指数都有所上升;劳动人口空间分异指数2000一2016年上升了0.028，但沙依巴克区和水磨沟区空间分异指数有所下降；2000一2016年，所有区域老年人口空间分异指数都有所上升，说明老龄化现象越来越明显。

（4）1990年文盲人口空间分异指数平均值为0.108，其中头屯河区的文盲人口相对处于分异状态,2000—2010年期间新市区分异水平较高；小学及初中人口空间分异指数在1990—2010年期间呈现下降趋势，说明小学及初中人口分异现象逐步得到缓解;高中人口空间分异指数在1990—2000 年期间上升了0.089,2000—2010 年期间下降了0.039，说明高中人口的分异现象逐渐减少；1990—2000 年期间大专以上人口空间分异指数上升，2000—2010年下降了0.065，并且大部分区域的下降趋势较为显著，说明这期间大专以上人口的混居程度加深，居住分异现象减少。

文中以城市空间的扩展印证居住空间格局变化宏观特征，运用莫兰指数得到不同人口属性的聚集程度，并利用ArcGIS制作分布图更直观的表现出不同人口属性的聚居区位，采用人口普查数据得出的结果更加客观、更具有说服力;利用GIS空间分析方法，通过对原始数据模型的观察和实验，可以实现统计学的空间可视性，并以此作为空间行为的决策依据。

# 参考文献（References)

[1］菲利克斯·格罗斯.公民与国家：民族、部族和族属身份[M].

王建娥，魏强（译），北京：新华出版社,2003.［GROSSFelines.Citizens and countries：Ethnic,tribal,and ethnic identity[M].WANG Jiane,WEI Qiang（Translation）,Beijing: Xinhua Publish-ing House,2003.]

[2]大卫·费特曼.民族志:步步深入[M].龚建华(译),重庆：重庆大学出版社,2013.［FETTERMAN David.Ethnography:Stepby step[M]. GONG Jianhua（Translation）. Chongqing:ChongqingUniversity Press,2013.]  
[3]FARLEY Reynolds. Residential segregation in urbanized areas ofthe united states in 197O:An analysis of social class and racialdifferences[J]. Demography,1977,14(11） :497-518.  
[4］谌丽,张文忠,李业锦,等.北京城市居住环境类型区的识别与评价［J].地理研究,2015,34（7）:1331－1342.[CHEN Li,ZHANG Wenzhong,LI Yejin,et al.Identification and evaluation ofresidential environment types in Beijing City[J]. Geographical Re-search,2015,34(7) :1331 -1342.]  
[5］廖邦固,徐建刚,宣国富,等.1947—2000年上海中心城区居住空间结构演变[J].地理学报,2008,75（2）:195-206.[LIAOBanggu,XU Jiangang,XUAN Guofu,et al.Evolution of residentialspace structure in Shanghai central city based on land use[J].Ac-ta Geographica Sinica,2008,75(2）:195-206.]  
[6］孙斌栋,吴雅菲.上海居住空间分异的实证分析与城市规划应对策略[J].上海经济研究,2008,27（12）:3-10.[SUN Bind-ong,WU Yafei.An empirical analysis of Shanghai'‘s residentialspatial differentiation and urban planning coping strategies[J].ShanghaiEconomic Review,2008,27(12）:3-10.]  
[7］廖邦固,徐建刚,梅安新.1947—2007年上海中心城区居住空间分异变化—基于居住用地类型视角［J].地理研究,2012，31（6）:1089 -1102.[LIAO Bangg,XU Jiangang,MEI Anxin.Evolution of residential differentiation in central Shanghai city(1947—2007）:A view of residential land-use types[J]. Geo-graphical Research,2012,31(6):1089 -1102.]  
[8］李志刚,杜枫.中国大城市的外国人“族裔经济区"研究——对广州"巧克力城”的实证[J].人文地理,2012,27(6)：1-6.[LI Zhigang,DUFeng.The transnational making of‘chocolate cit-y’ in Guangzhou[J].Human Geography,2012,27(6):1-6.]  
[9］李志刚,吴缚龙,肖扬.基于全国第六次人口普查数据的广州新移民居住分异研究[J].地理研究，2014，33（11）：2056-2068.[LI Zhigang,WU Fulong,XIAO Yang. Residential segrega-tion of new migrants in Guangzhou,China:A study of the $6 ^ { \mathrm { t h } }$ cen-sus[J].Geographical Research,2014,33（11）:2056 -2068.]  
[10］钟奕纯,冯健.城市迁移人口居住空间分异—对深圳市的实证研究[J].地理科学进展,2017,36（1)：125-135.［ZHONGYichun,FENG Jian.Residential spatial differentiation of migrantpopulation within the city:A case study of Shenzhen[J].Progressin Geography,2017,36(1）:125-135]  
[11］蒋亮,冯长春.基于社会——空间视角的长沙市居住空间分异研究［J].经济地理,2015,35(6）:78-86.[JIANG Liang,FENGChangchun.Thestudyofresidential diferentiationin Changshabasedonthesocial-spatial perspective[J]. Economic Geography,，

2015,35(6):78 -86.]

[12］王俊敏.呼和浩特市区的民族迁移与居住格局[J].西北民族 研究，1997,12（2）:279-280.［WANG Junmin.The pattern of ethnic migration and residence in theurban district of Hohhot[J]. Northwestern Journal ofEthnology,1997,12(2）:279-280.]

[13］马红艳.银川市回汉民族关系调查研究[D].北京：中央民族 大学,2O12.［MA Hongyan.Investigation and research on ethnic relations between Hui and Han in Yinchuan[D].Beijing:Minzu University of China,2012.]

[14］杨瑛,李同昇，冯小杰.西安市主城区居住空间住宅价格分布 格局与驱动机制[J].地域研究与开发，2015，34（5）：68-74. [YANG Ying,Li Tongsheng,FENG Xiaojie.Analysis on the pattern of the house price and its driving forces in the dwelling space in the urban district of Xi'an[J].Areal Research and Development,2015,34(5):68-74.]

[15］罗正文.转型期西安城市贫困阶层聚居及其形成机制研究 [D].西安：陕西师范大学,2015.［LUO Zhengwen.Study on the settlement of the urban poor stratum and its formation mechanism in the transitional period in Xi'an[D].Xi'an:Shaanxi Normal University,2015.]

[16］黄达远.乌鲁木齐城市社会空间演化及其当代启示[J].西北 民族研究,2011,26（1）:70-78.［HUANGDayuan.Social-spatial evolvement of Urumqi and its contemporary implications[J]. Northwestern Journal ofEthnology,2011,26（1）:70-78.]

[17］张利,雷军,张小雷，等.乌鲁木齐城市社会区分析[J].地理学 报,2012,67(6）:817-828.[ZHANGLi,LEIJun,ZHANGXiaolei,et al.Analysis of the urban social areas in Urumqi[J].Acta Geographica Sinica,2012,67(6) :817-828.]

[18］刘正江.乌鲁木齐市民族社区居住格局变迁动因研究[J].黑龙江民族丛刊,2014,30（4）：116-121.［LIU Zhengjiang.Studyon the change factors of residential pattern of Urumqi ethnic com-munity[J].Heilongjiang National Series,2014,30（4）:116-121.]

[19］董晔,安瓦尔·买买提明.城镇化进程中乌鲁木齐市少数民族农民工空间分布及生存状态研究[J].地理科学，2014,34（8）：963-97O.[DONG Ye,ANWAER Maimaitiming. Spatial distribu-tion and living situation of Urumqi ethnic minority migrant workersin the process of urbanization in Xinjiang[J].Scientia Geographica

Dinica,2014,54(8）:903-y/0.」   
[20］张力,李雪铭,张建丽.基于生态位理论的居住区位及居住空 间分异［J].地理科学进展,2010,29（12）：1548－1554. [ZHANG Li,LI Xueming,ZHANG Jianli.A study of residential location and residential space differentiation based on the niche theory[J].Progress in Geography,2010,29(12）:1548 -1554.]   
[21］姜巍,高卫东.居住空间分异——乌鲁木齐市在发展中面临的 严峻问题[J].干旱区资源与环境,2003,17（4)：43-47. [ JIANG Wei,GAO Weidong. Residential segregation:The most serious problem in the development of Urumqi[J].Journal of Arid Land Resources & Environment,2003,17(4) :43 -47.]   
[22］陈燕.新型城镇化战略对城市居住空间分异影响研究［J].南 京社会科学,2014,25（12）:23-29.[CHEN Yan.On the motivation research of urban residential space diferentiation based on the perspective of new urbanization strategy[J].Nanjing Journal of Social Sciences,2014,25(12）:23-29.]   
[23］张勃,张凯.干旱区绿洲空间分异演化研究—以黑河流域绿 洲为例[J].冰川冻土,2002,24（3）：414－420.[ZHANG Bo, ZHANG Kai. Study on the spatial differentiation and the evolution in arid regions:A case study for oases in Heihe river basin[J]. Journal of Glaciolgy and Geocryology,2002,24（3）:414-420.]   
[24］张凌云,李松,张洁,等.基于空间自相关的乌鲁木齐市民族居 住格局研究[J].干旱区资源与环境,2014（3）：50-56.［Zhang Lingyun,Li Song,Zhang Jie,et al.Analysis on ethnic residential spatial pattern in Urumqi city based on spatial autocorrelation[J]. Journal of Arid Land Resources and Environment,2O14（3） :50 - 56.]   
[25］王华菊.从居住隔离到教育隔离:南疆教育问题的考察[J].贵 州民族研究,2016，（2）:226-230.[WANGHuaju.From residential segregation to educational segregation:The study on education in south Xinjiang[J].Guizhou Ethnic Studies,2016,（2）： 226 -230.]   
[26］方创琳,黄金川,步伟娜.西北干旱区水资源约束下城市化过 程及生态效应研究的理论探讨[J].干旱区地理,2004,27（1)： 1-7.［FANG Chuanglin,HUANG Jinchuan,BU Weina. Theoretical study on urbanization process and ecological effect with the restriction water resource in arid area of northwest China[J].Arid Land Geography,2004,27（1） :1 -7.]

# Residential structure of Urumqi City based on index analysis method

LIU Yu-shan’， DONG Ye1,² (1College of Geographic Science and Tourism,Xinjiang Normal University,Urumqi 830o54,Xinjiang,China; CenterofSilkRoadEconomicBelt UrbanDvelopmentStudyXinjiangNormalUniversity,Urumqi83054,Xinjiang,China）

Abstract：As the capital cityof Xinjiang，Urumqi Cityis an important economiccenterin western China and plays an important role in theurban system of China.Itcould beof significance for theurban spatial planning of Urumqi City by studying the population living patern of the city.This paper takes Urumqi as the research area，uses he expansionof urban space to verifythe macro-characteristics ofthe change of residential patern，takes“residential pattern”as the breakthrough point，and uses Moran's $I$ and ArcGIS technology to analyze the residential pattern of different population attributes in this area.It is concluded thattheurban residential land in Urumqi extends mainlyin the northwest direction,the West Mountain direction，the East Mountain direction and theouter edge of the old urban area of the city.The agglomeration of middle-aged and old population in diferent age groups is more obvious, theagglomeration of working population is not significant,andthe population of primaryandsecondary schols and junior middle schols with diffrent educational levels and the population of large citiesare different.The Moran's $I$ （204号 value of the population of primaryandsecondary school and junior high schol population is higher than that of the population with diffrent education level,the Moran 's $I$ value of the illiterate population is relatively low,and the high schol population is negatively correlated in space.Te spatial diferentiation index of schoo-age population and theelderly populationhas increased inallregions from 2OoO to 2O16,and the labor population diferentiation index has declined in Shayibak District and Shuimogou District,indicating thatthe phenomenon of aging is becoming more and more obvious.In 2O,theiliterate population was in arelatively diffrent state in Toutunhe District. Thelevel of diferentiation wasrelatively high in the Xinshi Districtfrom 2OOO to 2O10.The population of primary and junior middle schools，senior middle schoolsand above juniorcolleges gradually decreased from 1990 to 2010, the degree of mixed living deepened,and the phenomenon of residential differentiation decreased.

Key words:Residential pattern；Spatial differentiation；Moran index；Urumqi City