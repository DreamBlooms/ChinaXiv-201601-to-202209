# 1961—2016年锡林河流域降水及平均气温变化特征及趋势

吴国栋¹²，薛河儒1，刘廷玺³

（1.内蒙古农业大学计算机与信息科学技术学院,内蒙古 呼和浩特010018；2.内蒙古农业大学理学院，内蒙古 呼和浩特010018；3.内蒙古农业大学水利与土木建筑工程学院,内蒙古 呼和浩特010018)

摘要：运用累积距平法和时间序列的非参数趋势分析法(ITA法和ITA-CB法),对我国半干旱草原型流域——锡林河流域1961—2016年近56a降水数据和平均气温数据进行分析，揭示了降水和均温的年内、年际和年代际的变化特征，并且分析了降水和均温的季节、年度的变化趋势。结果显示：1961—2016年锡林河流域的降水分布不均匀,在年内存在显著季节特征、年际上波动性强且差异明显。年降水量的平均变化趋势是下降，冬、春季降水上升，夏、秋季降水下降。特别是冬季降水上升明显且稳定，比春季降水上升趋势大。夏季降水高值区呈现加强的上升趋势、低值区呈现加强的下降趋势，从而出现极端天气的可能性变大。秋季降水下降的平均变化率较小，并在低值区和高值区显现上升趋势。平均气温以1987年为转折点呈现先降后升的总体变化特征，在年代际上表现为强烈的上升趋势。ITA和ITA-CB法的结果进一步反映了1961—2016年该区域年平均气温总体上升趋势显现出减缓的变化规律。春季和秋季的平均气温上升速率比夏、冬两季大，而且季节之间的温度差异呈现减小趋势。

关键词：ITA法；ITA-CB法；趋势；锡林河流域；降水；平均气温

# 文章编号：

时间序列可能存在增加或减少的趋势，国内外很多学者致力于研究如水质、温度、降水、径流量、蒸发量等时间序列的变化趋势。早期的学者采用Mann-Kendall(M-K）序列M-K、Spearman Rho 和Sen's slope等方法进行序列趋势分析[1-7]。这些方法都不仅要求所研究的序列长度足够大，而且要求序列满足正态分布，以及序列独立性。但是往往很多研究场合下，时间序列不能满足上述特征的要求。为了解决序列自相关的数据前提，一种预白化过程(Pre-whitening)被提出，即先对时间序列预白化，再探究预白化之后的序列趋势[8]。很快就有文章指出这样的处理方法会消除原始序列的一些重要趋势特征[9-10]

Sen提出一种改进的趋势分析方法(Innovativetrend analysis,简称ITA)[1-13]。由于该方法不会受限于序列相关性方面的要求，而且具有直观性，所以被广泛地应用于水质、蒸发量、降水、气温等时间序列的趋势分析中[14-18]。但是ITA法采用的是图像观察方式，缺少定量描述，使得面对复杂变化的序列图像，观测者很难做出明确结论。2018年，Alashan提出一种ITA的改进方法,称为ITA-CB(ITA-changeboxes），可以更加详尽、量化地分析时间序列可能存在的变化趋势[19]。此方法不同于常规的趋势分析方法，它把数据序列分成低值区、中值区和高值区结合整体进行趋势分析，不仅可以检测各区段趋势的存在性与增减性，而且可以计算趋势的相对变化率，并可探究趋势是在加强还是减弱。所以利用ITA-CB法可以分析数据序列整体及局部的变化趋

# 干吴区地理

势，特别是引入相对变化率指标来量化描述趋势的变化状况，这一特征是其他方法不具备的

大气降水被认为是干旱半干旱地区一种重要的水文资源，可以补给径流，并且影响地区水资源数量在时空上的分布，进而影响着地区生态环境的演替[20-22]。对于我国北方的半干旱草原型流域而言，降水对该地区的牧草产量和草原生态具有重要意义[23]。但是国内学者针对降水量的趋势分析多集中于非草原区，而对草原区的长时间序列降水趋势研究较少[24]。李玮等[23]运用M-K法从不同时间尺度分析了锡林河流域(半干旱草原型流域)近56a降水的趋势，但是未考虑序列的自相关性问题。多兰等[24]基于锡林浩特气象站降水日值资料(1960—2015年)，从季度和年度2个时间尺度，运用M-K方法进行了降水量趋势分析和突变检验。结果表明，锡林河流域年均降水量呈不显著下降趋势，春、夏、秋三季降水变化均不显著，而冬季呈显著上升趋势$( P { < } 0 . 0 5 )$ 。因受到方法所限，他们的结论只能是一种宏观性分析结果。如冬季降水表现出的显著上升趋势的变化细节如何;这种上升趋势快慢程度如何；其低、中、高3个区段如何变化等，这些细节问题仍需进一步了解。

伴随着全球变暖，气温变化也成为学者们关注的重点，气温影响着地区水循环、生态、植被等很多方面。内蒙古自治区是我国气候变化敏感的地区之一，是我国温带草地的典型区域。截至目前，研究人员针对草地类型区的气候影响及气温变化研究尚需深入[25]。

综上所述,研究干旱半干旱草原流域的降水与气温变化具有重要的现实意义。但是在已有文献中使用的M-K、Sen's slope等方法除了受到序列自相关性的影响而可能产生不准确结论之外，其结论也只是停留在整体和宏观层面上。ITA法不受序列自相关性的影响，ITA-CB法可以量化分析趋势在微观层面上的细节状况，将二者结合使用、相互补充，就可以更加详细地了解流域降水与气温的变化趋势。掌握这些细节性规律和变化趋势，就可以更好地为流域水资源的未来规划管理和科学使用提供理论基础，为实现可持续发展和草原生态保护提供技术支撑，为深入了解流域气温变化规律提供帮助。

本文基于锡林河流域的1961—2016年降水时间序列和平均气温值序列，首先对降水和气温的变化特征进行整体上的分析，揭示流域降水、气温的年内、年际、年代际的变化特征；然后再综合使用ITA和ITA-CB法，分别从宏观和微观角度研究降水和气温时间序列的前后2部分反映出的增加或减小趋势，以及它们的量化改变，以期更加详尽地探究流域内降水和气温的变化趋势。

# 1研究区概况与数据来源

锡林河流域是典型的半干旱草原型流域的代表，位于内蒙古自治区锡林郭勒草原，地理范围在$1 1 5 ^ { \circ } 2 5 ^ { \prime } { \sim } 1 1 7 ^ { \circ } 1 6 ^ { \prime } \mathrm { E } . 4 3 ^ { \circ } 2 4 ^ { \prime } { \sim } 4 4 ^ { \circ } 3 9 ^ { \prime } \mathrm { N }$ 之间，流域面积$1 0 5 4 2 \mathrm { k m } ^ { 2 [ 2 6 ] }$ (图1)。流域气候属于中温带半干旱大陆性季风气候，昼夜温差大、蒸发量大、降水量少。流域年均降水量大约 $3 0 0 ~ \mathrm { { m m } }$ ，主要集中于每年的6—8月，流域地下水资源极其匮乏[23]。流域是内蒙古自治区畜牧业发展的重要基地，也是锡林浩特市自然生态环境稳定的关键。

![](images/e8742a1dbc75f1abe527fcd5f7ded1766280fdb7199d6bbed09a132e7e39e5cb.jpg)  
图1锡林河流域及锡林浩特气象站位置 Fig.1 Location of the Xilinhe River Basin and meteorological stations

本文所用到的降水数据来源于国家气象科学数据中心 $( \mathrm { h t t p } { : } / / \mathrm { d a t a . c m a . c n } / )$ 的 $0 . 5 ^ { \circ } { \times } 0 . 5 ^ { \circ }$ 网格化地面月降水数据集。依照锡林河流域所处的经纬度范围筛选数据，共收集到1961—2016年共56a的月降水数据，按季度和年度整理。春季为当年的3—5月；夏季为6—8月；秋季为9—11月；冬季为当年12月和次年的1一2月。平均气温数据由锡林浩特气象站日均值数据得到，时间范围为1961年1月1日一2016年12月31日共 $5 6 \mathrm { a }$ ○

# 2研究方法

ITA法由 $\mathrm { S e n }$ 于2012年提出[19],其具体过程是,首先将原始数据序列均分为两部分后按升序排列，记第一部分为 $x _ { 1 } , x _ { 2 } , \cdots , x _ { n / 2 }$ ，记第二部分为 $\boldsymbol { y } _ { 1 }$ $y _ { 2 } , \cdots , y _ { n / 2 }$ ,其中 $n$ 为原始数据的个数。其次在直角坐标系中以第一部分为横轴，第二部分为纵轴，作散点图 $( x _ { i } , y _ { i } )$ ， $i = 1 , 2 , 3 , \cdots , n / 2$ ,并作出 $1 : 1 \left( 4 5 ^ { \circ } \right)$ 直线。如果散点都在 $1 : 1$ 直线的上(下)方，那么可以断定序列存在增加(减少)趋势。进而，若散点的分布接近平行于 $1 : 1$ 直线，则可以断定增加(减少)的趋势是单调的(图 $2 \mathrm { a }$ 。

本文首先计算序列的均值 $\mathit { \Pi } _ { \overline { { x } } }$ 和标准差 $s$ ,将序列中满足 $x < \overline { { x } } - s$ ， $\overline { { x } } - s < x < \overline { { x } } + s$ 和 $x > \bar { x } + s$ 的数据分别划分为低值、中值和高值区(图2b)。然后利用ITA法研究序列在3个区间内的变化趋势。这样处理的目的是为了更详尽地探究数据序列内部的变化趋势，同时也便于与ITA-CB法结合讨论。

ITA-CB法是研究ITA法中的数据变化率，即依次计算 $( y _ { i } - x _ { i } ) / x _ { i } \times 1 0 0 \%$ ， $i = 1 , 2 , \cdots , n / 2$ 后,统计每组中变化率的最小值、平均值和最大值，并且画出箱型统计图。变化率的平均值大于(或小于)0,反映了对应数值区的平均趋势是增大(或减小)的。如果箱型图内表示平均值的线段接近于最小值(或最大值)线段，那么可以认为趋势的变化率是负的(或正的)。也就是说，如果平均值线与最大值线的距离小(或大)，则说明变化趋势是加强(或减缓)。

![](images/78c00e31a66be842cc1d88885e6efa15a0ab26f92d2829cfac8e5d933879995f.jpg)  
图2趋势分类示意图  
Fig.2 Diagram of trend classifications

# 3结果与分析

# 3.1锡林河流域内降水和平均气温特征

3.1.1 降水和平均气温的年内特征根据图3、表1显示，流域年均降水量少，仅为 $2 9 6 . 3 ~ \mathrm { m m }$ ,且分布不均匀。最大降水量出现在7月，最小降水量是1月，分别占到全年降水量的 $2 7 . 8 \%$ 和 $0 . 6 \%$ 。在季节尺度上，年内降水主要集中于夏季(6一8月），占到年降水量的 $6 7 . 2 \%$ ；冬季降水最少，只占全年降水量的 $2 . 8 \%$ 。

流域内年均气温为 $2 . 6 ~ \mathrm { { ^ { \circ } C } }$ ,最高均温出现在7月，最低均温出现在1月。56a内夏季温度最高、冬季最低；夏季的均温差最小 $( 4 . 6 ~ \mathrm { ^ { \circ } C } )$ ，冬季均温差最大 $( 7 . 9 ~ \mathrm { ^ { \circ } C } )$ ，所以冬季气温变化比夏季剧烈。

![](images/8e3c5fd20c09dd093836baabcbabe697faca5bc5d70cc0139d35688a130aeda4.jpg)  
图3锡林河流域降水和平均气温的年内分配特征 Fig.3 Annual distribution characteristics of precipitation and average temperature in the Xilinhe River Basin

3.1.2降水和平均气温的年际特征采用累积距平法[27-28]得到图4,流域年降水量的极大值是2012年的 $4 9 1 . 6 ~ \mathrm { m m }$ ,比多年平均降水量多 $1 9 5 . 3 ~ \mathrm { m m }$ ;极小值是2005年的 $1 6 6 . 4 \ \mathrm { m m }$ ，比多年平均降水量少$1 2 9 . 9 \ \mathrm { m m }$ 。总体上，56a的年均降水量变化比较复杂，几个转折点主要是1965、1974、1979、1998年和2012年。降水量在1961—1973年偏少，在1990—1998年增加明显，在1999—2011年呈现显著下降趋

# 干旱区地理

表11961—2016年锡林河流域降水和平均气温的变化特征  
Tab.1Variationcharacteristicsof precipitationand average temperature in Xilinhe River Basin from1961to 201(   

<html><body><table><tr><td rowspan="2">项目</td><td rowspan="2">特征</td><td colspan="5">时期</td></tr><tr><td>年</td><td>春季</td><td>夏季</td><td>秋季</td><td>冬季</td></tr><tr><td>降水</td><td>多年平均值/mm</td><td>296.3</td><td>41.7</td><td>199.1</td><td>47.1</td><td>8.4</td></tr><tr><td rowspan="6">平均气温</td><td>占全年百分比/%</td><td>1</td><td>14.1</td><td>67.2</td><td>15.9</td><td>2.8</td></tr><tr><td>最大值/mm</td><td>491.6</td><td>98.9</td><td>333.0</td><td>100.2</td><td>21.4</td></tr><tr><td>最小值/mm</td><td>166.4</td><td>15.1</td><td>72.2</td><td>15.6</td><td>2.9</td></tr><tr><td>多年平均值/0.1°</td><td>26</td><td>41</td><td>198</td><td>35</td><td>-168</td></tr><tr><td>最大值/0.1℃</td><td>48</td><td>71</td><td>224</td><td>58</td><td>-131</td></tr><tr><td>最小值/0.1℃</td><td>6</td><td>10</td><td>178</td><td>7</td><td>-210</td></tr></table></body></html>

势，2012年之后接近或高于平均水平。

图5是关于均温的累积距平图，从图中可以看出，56a中年均温的极大值出现在2014年，为$4 . 8 ~ \mathrm { { ^ { 4 } C } }$ ，比多年平均气温高 $2 . 2 ~ \mathrm { ^ { 9 ~ C } }$ ;极小值出现在1969年，为 $0 . 6 ~ \mathrm { ^ { \circ } C }$ ，比多年平均气温低了 $2 . 0 \mathrm { { ^ { \circ } C } }$ 。较之降水量的年际变化，气温的年际变化要简单很多，从1961年到1987年总体表现为下降趋势；从此直到2016年呈现上升趋势。在上升期间有一次转折是2012年，这可能与2012年降水量突变有关。1999—2011年气温高于多年平均气温且呈上升趋势，但是同期的降水量比多年平均降水量低且下降明显。

![](images/34bffecac0ab05af90bb3e450f6915418627a46528631ab73887828fa4761ad2.jpg)  
图41961—2016年锡林河流域降水量的距平和累积距平Fig.4 Anomaly and cumulative anomaly of precipitation inthe Xilinhe River Basin from 1961 to 2016

![](images/c1b1652b7dd5117d68f3f502a9f1efd59e678f382441569e778779c09b8982b9.jpg)  
图51961—2016年锡林河流域平均气温的距平和累积距平

3.1.3 降水和平均气温的年代际特征图6显示了锡林河流域56a来降水与均温的年代际变化特征。20世纪90年代流域降水量比多年平均水平高，达到$3 3 1 . 7 \ \mathrm { m m }$ ;21世纪初的10a内降水偏少，只有$2 4 5 . 5 \ \mathrm { m m }$ ;其他年代的降水接近平均水平，略有微小波动。平均气温的变化，从20世纪60年代气温最低开始单调上升，直到21世纪的前10a内达到极大，然后在近年内有所下降。

# 3.2锡林河流域内降水和平均气温的变化趋势分析

应用ITA和ITA-CB法研究上文所述数据，将结果汇总到图7中。流域春季降水数据首先被分成前、后两部分，并按照第一部分的均值和标准差分成低值区、中值区和高值区3个组。计算每个组及全部数据的变化百分比（下文称之为趋势变化率），统计各组和整体的最小值、均值和最大值，绘成箱型图。以上过程重复应用于夏季、秋季、冬季和年度降水数据以及春季、夏季、秋季、冬季和年度的平均气温数据。

![](images/6e305f834d2e9529d83e60b92477334ef02796a0eeb8eff765e143ae5f143eb5.jpg)  
Fig.5 Anomaly and cumulative anomaly of temperature in the Xilinhe River Basin from 1961 to 2016   
图61961—2016年锡林河流域降水量和气温的年代际特征Fig.6Interdecadal features of precipitation and temperature inthe XilinheRiverBasin from1961 to 2016

![](images/7c5cd328ef353898fc49021fd81e980f243a8fa52d8a76642140b13265f11a19.jpg)  
图7ITA和ITA-CB法输出的1961—2016年锡林河流域的降水趋势  
Fig.7Precipitation trends in the Xilinhe River Basin obtained from ITAand ITA-CB from196l to 2016

由图7a1结果分析可知，锡林河流域春季降水在低值区和高值区均呈现上升趋势，平均趋势变化率分别是 $2 1 . 2 \%$ 和 $2 7 . 6 \%$ 。图7a2中，低值和高值的变化率均值线都接近各自的最大值线，说明春季降水的低值和高值所呈现的上升趋势有变强趋势。虽然ITA法未能反映春季降水在整体上呈现上升趋势，但是ITA-CB法反映出各组数据的平均变化率都是正数，可以认为春季降水的平均趋势是为上升。

夏季降水的低值区呈现下降趋势，平均变化率为 $- 1 9 . 5 \%$ ，高值区以 $1 1 . 2 \%$ 的平均变化率体现为上升趋势，而中值区以下降为主。从箱型图7b2可以看出，夏季降水低值的下降趋势的变化率平均值线靠近最大值线，所以下降趋势有加快倾向，同样高值区也存在相同情况。图7b1反映夏季降水的总体趋势不明确，但ITA-CB法显示趋势平均变化率为 $- 6 . 2 \%$ 。

秋季降水的低值区和高值区都反映出上升趋势，但从图7c2可以看出低值区的上升速率在微弱减小，而高值区的上升速率变大。秋季降水的中值区是下降趋势，平均速率为- ${ - 6 . 2 \% }$ 。从整体的平均变化率看，秋季降水显示微弱下降，变化率是 $- 0 . 3 \%$ ，而

且下降速率有减小趋势。

图7d1显示冬季降水呈现明显的上升趋势，图7d2显示低值区、中值区、高值区和整体的所有变化率均是正数，而且它们的上升速率有减小的趋势。整体的平均趋势变化率为 $2 8 . 3 \%$ ,且变化范围是从$6 . 5 \%$ 到 $5 0 . 0 \%$ 。

年度降水量在低值区和中值区呈现下降趋势，且它们的平均变化率分别是 $- 1 2 . 0 \%$ 和 $- 4 . 4 \%$ ，而高值区呈上升趋势(图7e1)。年度降水的平均变化率为 $- 2 . 4 \%$ ,反映出平均下降趋势，而且下降趋势在减缓(图7e2)。

根据图8中有关平均气温的ITA法输出结果，可以发现锡林河流域的平均气温在季节尺度和年度上的数据散点图几乎全部落于 $1 : 1$ 直线的上方，所以均表现出上升趋势。进一步，可以根据ITA-CB法的结果对气温的变化趋势做细化分析。

春季的平均气温在整体上呈明显的上升趋势，平均变化率大于 $5 0 . 0 \%$ ,且上升趋势在减缓。从分区的角度看，春季平均气温的低值区上升最快，但上升趋势在减缓;反而，中值区呈现一种加强的上升趋势，平均变化率为 $5 8 . 2 \%$ （图8a2）。

夏季的平均气温整体的趋势变化率为 $5 . 0 \%$ ，即呈现上升趋势，而且从图8b2可见其上升趋势没有明显的加强或减缓。同样的趋势也在夏季平均气温的中值区和高值区出现。但低值区表现出放缓的增长趋势，并且平均变化率为 $2 . 4 \%$ ○

![](images/9072ecb91bf8a6665bc71bb50d927a13baa7c6cf81c17d0c6189927fdf9684dd.jpg)  
图8ITA和ITA-CB法输出的1961—2016年锡林河流域的平均气温趋势  
Fig.8Temperature trends in the Xilinhe River Basin obtained fromITAand ITA-CB from 1961 to 2016

秋季的平均气温在低值区、中值区、高值区和整体都是上升趋势，平均变化率分别是 $7 6 . 8 \%$ 、$4 5 . 2 \% . 2 4 . 0 \%$ 和 $4 8 . 5 \%$ ,其中低值区的增加最快，但是增长趋势均在减缓(图8c2）。

冬季的平均气温在整体上平均变化率为 $8 . 2 \%$ ，是一种加强的增长趋势(8d2)。而且从分区角度观察也都是呈现加强的上升趋势，低、中、高值区的平均变化率分别是 $3 . 9 \% . 9 . 3 \%$ 和 $7 . 9 \%$ ○

年度平均气温在低值区的上升趋势最为明显，平均变化率为 $1 1 0 . 0 \%$ 。另外，中值区和高值区的平均变化率分别是 $7 1 . 4 \%$ 和 $4 4 . 5 \%$ ，所以年度平均气温在整体上反映出明显的上升趋势，总平均变化率为$7 2 . 5 \%$ (图8e2)。年均气温在各个区段上的上升趋势在过去 $5 6 \mathrm { ~ a ~ }$ 内是呈减缓趋势，并且以低值区和整体的减缓最为明显。

# 4结论

本文利用国家气象信息中心的 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 网格化地面月值降水数据集，依照锡林河流域所处的经纬度范围选取了1961—2016年近56a的月降水数据，并且利用锡林浩特气象站同期的日均值气温数据整理出月均气温数据，探析了56a内锡林河流域降水量和平均气温在年内、年际和年代际的变化特征，并应用ITA和ITA-CB法量化分析了降水量和平均气温在季度和年度上的变化趋势

变化特征包括：

（1）锡林河流域的降水在年内和年际的分布都极不均匀。年内分布集中于夏季，夏秋季降水量可达全年降水量的 $8 3 . 1 \%$ 。而年际分布复杂且波动性强，21世纪的最初10a内出现降水量连续低于平均水平的情况，造成降水量在短期内下降明显。

(2）流域的平均气温在年内表现为7月最高，1月最低；冬季温差大，夏季温差小。而其年际特征表现为先下降后上升的变化规律，转折点是1987年；年代际的特征是从1960s到2000s之间单调上升，随后略有下降。

变化趋势包括：

（1）56a来流域年降水量在低值区与中值区均呈现减小趋势，在高值区呈上升趋势，但年平均趋势为下降。同样在平均意义上，冬、春两季的降水上升，夏、秋两季降水下降，这与李玮等[23]的研究结果一致。进一步分析得到，冬季降水上升的趋势（平均变化率为 $2 8 . 3 \%$ )比春季(平均变化率为 $7 . 7 \%$ ））上升趋势大，春季降水在低值区和高值区的上升趋势都在加强。另外由于冬季降水上升率的最大和最小值均为正数，所以冬季降水的上升更加稳定和显著。夏季降水的平均下降速率比秋季的下降速率大，而且夏季降水低值区减小的趋势和高值区增大的趋势都在加强，表明干旱和洪涝的极端天气出现可能性变大。秋季降水整体上主要受到中值区的下降趋势的影响而呈现微弱下降趋势，低值区和高值区均呈现上升趋势。

(2）在过去56a间，流域的年均气温整体上呈现平均上升趋势，而且上升的趋势明显，其低值区的平均变化率达到 $1 1 0 . 0 \%$ 。由于低值区的上升速率在减缓，年均气温整体上呈现出放缓的上升趋势。春季和秋季的平均气温上升速率（分别为$5 4 . 5 \%$ 和 $4 8 . 5 \%$ )比夏季和冬季的上升速率大，且其上升趋势明显在减缓。同样的规律在春季、夏季和秋季的低值区，以及秋季的中值区均表现明显。另外，一年中气温最低的冬季呈现加速上升趋势，一年中气温最高的夏季呈现减缓的上升趋势。所以在过去56a中锡林河流域内的平均气温在逐年上升，而且四季间平均气温的差异在逐年减小。

# 参考文献(References)

[1]刘闻,曹明明,刘琪,等.1951—2012年渭河流域降水频次变化 特征分析[J].干旱区地理,2015,38(1):18-24.[Liu Wen,Cao Mingming,Liu Qi,et al.Frequency of precipitation for the Weihe River Basin during 1951—2012[J].Arid Land Geography,2015, 38(1): 18-24.]   
[2] Mann H B.Nonparametric tests against trend[J].Economitrica, 1945,13(3): 245-259.   
[3] Kendall MG.Rank correlation method[M].New York: Oxford University Press,1975.   
[4] 邱临静,郑粉莉,尹润生.1952—2008年延河流域降水与径流 的变化趋势分析[J].水土保持学报,2011,25(3):49-53.[Qiu Linjing,Zheng Fenli, Yin Runsheng. Trend analysis of precipitation and streamflow during 1952—2O08 in Yanhe River Basin[J]. Journal of Soil and Water Conservation,2011,25(3):49-53.]   
[5] Grace N,Sanayanbi H,Arnab B,et al. Spatial and temporal trends in high resolution gridded temperature data over India[J].Asia-Pacific Journal of Atmospheric Sciences,2019,55(4): 761-772.   
[6] Mehdi B,Abdol R Z,Mohammad M M,etal.Trend analysis of evapotranspiration applying parametric and non-parametric tech

# 干吴区地理

niques (case study: Arid regions of southern Iran)[J]. Sustainable Water Resources Management,2019,5(4): 1981-1994.   
[7]Nalley D,Adamowski J, Khalil B.Using discrete wavelet transforms to analyze trends in streamflow and precipitation in Quebec and Ontario (1954——2008)[J]. Journal of Hydrology,2012,475: 204-228.   
[8]Von S H. Misuses of statistical analysis in climate research[C]// von Storch H,Navarra A.Analysis of Climate Variability:Application of Statistical Techniques.New York: Springer,1995:11-26.   
[9]Yue S,Pllon P,Phinney B,et al. The influence of autocorrelation on the ability to detect trend in hydrological series[J].Hydrol Process, 2002,16(9): 1807-1829.   
[10]Bayazit M,Onoz B.To pre-whiten or not to pre-whiten in trend analysis?[J]. Journal of Hydrologic Science,2007,52(4): 611-624.   
[11] Sen Z.An innovative trend analysis methodology[J]. Journal of Hydrologic Engineering,2012,17(9): 1042-1046.   
[12]Sen Z. Trend identification simulation and application[J]. Journal of Hydrologic Engineering,2014,19(3): 635-642.   
[13] Sen Z.Innovative trend significance test and applications[J]. Theoretical and Applied Climatology,2017,127(3-4): 939-947.   
[14] 黄丹,刘再斌,蒋勤明,等.应用非参数的MK和ITA方法分析地 下水水质参数变化特征——以新三矿含水层为例[J].水资源 与水工程学报,2018,29(3): 7-13.[Huang Dan,Liu Zaibin,Jiang Qinming.Application of nonparametric Mann Kendall and innovative trend method analysis to groundwater quality parameters variation: A case study from aquifers in Xinsankuang coal mine[J]. Journal of Water Resources and Water Engineering,2018,29(3): 7-13.]   
[15]Wu H,Qian H. Innovative trend analysis of annual and seasonal rainfall and extreme values in Shaanxi,China,since the 1950s[J]. International Journal of Climatology,2016,37(5): 2582-2592.   
[16] Sonali P,Kumar N D.Review of trend detection methods and their application to detect temperature changes in India[J].Journal of Hydrology,2013,476: 212-227.   
[17] Elouissi A, Sen Z,Habi M.Algerian rainfall innovative trend analysis and its implications to Macta watershed[J].Arabian Journal of Geosciences,2016,9(4): 303.   
[18] Dabanli I, Sen Z,Yelegen M,et al. Trend assessment by the innovative-Sen method[J]. Water Resources Management,2016,30(14): 5193-5203.   
[19]Alshan S.An improved version of innovative trend analyses[J]. Arabian Journal of Geosciences,2018(11): 50-55.   
[20] 赵学敏,胡彩虹,张丽娟,等.汾河流域降水变化趋势的气候分 析[J].干旱区地理,2007,30(1):53-59.[Zhao Xuemin,Hu Caihong, Zhang Lijuan,et al. Climate analysis of precipitation change trend over the Fenhe River Basin[J].Arid Land Geography,2007, 30(1): 53-59.]   
[21]Lioubimtseva E, Colea R,Adams JM,et al. Impacts of climate and land-cover changes in arid lands of Central Asia[J]. Journal of Arid Environments,2005,62(2): 285-308.   
[22] 周梦甜,李军,朱康文.近15a新疆不同类型植被NDVI时空动 态变化及对气候变化的响应[J].干旱区地理,2015,38(4):779- 787. [Zhou Mengtian,Li Jun, Zhu Kangwen. Spatial-temporal dynamics of different types of vegetation NDVI and its response to climate change in Xinjiang during 1998—2012[J]. Arid Land Geography,2015,38(4): 779-787.]   
[23] 李玮,刘廷玺,格日乐吐,等.半干旱草原型流域不同时间尺度 降水特征分析[J].干旱区地理,2017,40(2):304-312.[Li Wei, Liu Tingxi, Geriletu,et al.Precipitation characteristics at different time scales for asemi-arid steppe watershed[J]. Arid Land Geography,2017,40(2): 304-312.]   
[24] 多兰,于瑞宏,张艳霞,等.锡林河流域降水量时空动态及对 NDVI的影响[J].中国草地学报,2019,41(231):63-72.[Duo Lan, Yu Ruihong,Zhang Yanxia,et al. Temporal and spatial dynamics of precipitation in Xinlin River Basin and its effect on NDE[J]. Chinese Journal of Grassand,2019,41(231): 6-72.]   
[25] 姜艳丰,尤莉,贾成朕,等.1961—2018年内蒙古平均气温突变 前后变化特征[J].内蒙古气象,2019(5):14-17.[Jiang Yanfeng, You Li,Jia Chengzhen,et al.Variation characteristic of mean temperature before and after abrupt transition in Inner Mongolia from 1961—2018[J].Meteorology Journal of Inner Mongolia,2019(5): 14-17.]   
[26] 宋小园,朱仲元,张圣微,等.锡林河流域气候变化特征诊断分 析[J].干旱区资源与环境,2016,30(4):151-158.[Song Xiaoyuan, Zhu Zhongyuan, Zhang Shengwei,et al. The diagnosis of climate change characteristics in Xilin River Basin[J].Journal of Arid Land Resources and Environment, 2016,30(4): 151-158.]   
[27] 魏凤英.现代气候统计诊断与预测技术[M].北京:气象出版社, 2007:43-46.[Wei Fengying.Modern climate statistical diagnosis andprediction technology[M]. Beijing:China Meteorological Press, 2007: 43-46.]   
[28] 冯文文,柳凤霞,钱会,等.气候变化背景下武功地区降水特征 [J].水土保持研究,2020,27(2):200-205.[Feng Wenwen,Liu Fengxia,Qian Hui,et al. Characteristics of precipitation in Wugong area under the background of climate change[J]. Research of Soil and Water Conversation,2020,27(2): 200-205.]

# Change characteristics and trends of precipitation and average temperature in the Xilinhe River Basin from 1961 to 2016

WU Guodongl²， XUE Heru'， LIU Tingxi³

(1.CollgeofComputerandInformationEngineering,InerMongoliaAgiculturalUniversity,Hohotl18,Innerongolia China;2.Collgeofience,InnerongoliaAgriculturalUniversityHohoto18,InerMongolia,Cina;3.CollgefWter Conservancyand CivilEngineering,InnerMongoliaAgriculturalUniversity,HohhotOloo18,Inner Mongolia,China)

Abstract: Atmospheric precipitation is considered an important hydrological resource in arid and semiarid areas because it can recharge runoff and afect the spatial and temporal distribution ofregional water resources,which in turn affect the regional ecological environment.Temperature is considered to afect many aspects of the region's water cycle,ecology,and vegetation. However,few studies have been conductedon the trend analysisof precipitation and temperature in steppe watersheds.Therefore,the main purpose ofthis article is to determine the precipitation and temperature trends in a semiarid steppe watershed of north China (the Xilinhe River Basin located in Iner Mongolia). Using the gridded monthly precipitation data of the China Meteorological Data Service Centre and the daily temperature data of the Xilinhot Meteorological Station,we used the cumulative anomaly method to briefly analyze the variation characteristics of precipitation and the average temperature in the basin.Further, the innovative trend analysis (ITA) and innovative trend analysis-change boxes (ITA-CB) methods were used to detect precipitation and temperature trends in the selected area.The results showed that precipitation in the Xilinhe River Basin was unevenly distributed, with significant annual seasonal characteristics and interannual strong undulation. Precipitation in a year was mainly concentrated in summer and autumn (about $8 3 . 1 \%$ of the total annual value).Precipitation was less during 1961—1973,increased significantly during 1990—1998,decreased significantly during 1999-2011,and was close to or greater thanthe average level after 2012.The average temperature of the basin had a large diference in winter and a small difference in summer; it decreased from l961 to 1987 and increased from 1988 to 2016.The results also showed that the annual precipitation presented a decreasing trend during the recent 56 years (1961—2016). On a seasonal scale,there was an increasing precipitation trend in winter and spring and a decreasing trend in summer and autumn. In particular,precipitation in winter rose significantly and steadily compared with that in spring.For precipitation in summer, its high-value areas showed an increasingly upward trend,and its low-value areas showed an increasingly downward trend.Thus,the posibilityof extreme weather becomes greater. In autumn, the average change rate of precipitation decline was small,and there was an increasing trend in the low- and high-value areas.Although the increasing trend of precipitation in winter and spring was significant,it had litle efect on the change in total precipitation for the whole year because of its limited total amount.With 1987 as the turning point,overall,the average temperature first fell and then rose onan annual scale.The results of ITA and ITA-CB further reflected that the overallincreasing trend of the average annual temperature in 56 years was slowing down.The average temperature rise rate in spring and autumn was greater than that in summer and winter. During the coldest winter of the year, the average temperature rose at anaccelerating rate.On the contrary,the temperature rise slowed down during the hottst summer.Therefore, it could be concluded that the temperature difference between seasons showed a decreasing trend.

KeyWords: innovative trend analysis (ITA)；innovative trend analysis-change boxes (ITA-CB)； trend;Xilinhe River Basin; precipitation; average temperature