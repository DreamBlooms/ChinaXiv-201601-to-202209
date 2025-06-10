# 台风活跃季月活动频次指数的构建及其应用

陈璇

（中国人民解放军75839部队，广东广州510510）

摘要：台风活动频次为每年汛期气象会商重要内容之一，目前所使用的方案主要以数值模拟结果为主，且无法进行定量分析。本文采用NCEP月平均高度场资料，基于其偏差信息，利用同化模型中的代价函数构建了一些表征西北太平洋5—10月间月尺度台风活动频次的指数，并利用这些指数构建了台风活跃季月活动频次指数模型。分析结果表明，该指数序列与台风频次序列相关性可达0.7，且指数模型能很好地表征台风活跃季月频次信息，可为台风月尺度活动频次预测提供参考。

关键词：偏差；指数；台风频次；西北太平洋中图分类号：P731 文献标志码：A

西北太平洋是全球热带气旋活动最为活跃的区域，其中南海作为“海上丝绸之路”的关键水域之一，受热带气旋影响尤为显著，台风活动对于海洋开发建设有着重要影响。已有的统计结果表明，西北太平洋活动的热带气旋约占全球热带气旋总数的 $3 0 \% ^ { [ 1 ] }$ 到 $3 3 \% ^ { [ 2 ] }$ ，全年皆可以有热带气旋生成；所生成的热带气旋中，约有2/3会发展成台风[2]，其中登陆我国的约占生成总数的 $2 6 \% ^ { [ 3 ] }$ 。我国学者很早就开始关注台风，陈秋士等[分析了15个台风个例，总结出 $2 0 0 \mathrm { { h P a } }$ 高度场上有利于台风形成的3种流场类型；李崇银给出了赤道西风或西南季风的加强以及中等强度冷空气影响下有利于台风生成的物理机制；李肖雅等认为热带气旋的生成位置可能与季风涡旋的Rossy波能量频散有关；王允宽等将研究重点放在冷空气对台风的影响上；陈笑晨等[8则注意到了澳大利亚冷空气活动对台风的影响；丁一汇等系统比较分析了多台风季和少台风季的大尺度系统差异；吴国雄[1]分析了海温对台风形成的影响。随着对海气系统理解的进一步加深，一些研究进一步揭示了热带季节内振荡[1l-1]、厄尔尼诺现象[3、14]、南极涛动[15]、北太平洋涛动[6]等气候因素与台风的关系。

每年的5—10月是西北太平洋台风活动活跃季[17]，该时期与我国夏季强降水时间段相吻合，台风（活动）频次为每年汛期气象会商的一个关键内容。目前，主流的预报方案是以数值预报的解释为主，数值预报的解释方法多以历年统计结果为参考依据，主要包括 ENSO（ElNino-Southem Oscillation）指数、西北太平洋副高指数和北太平洋涛动指数等。但这些指数与台风活动频次相关性并不高，在台风活动活跃季，南极涛动与台风年活动频次的相关系数为-0.48（相关的显著水平为 $9 9 \%$ ）[15]，北太平洋涛动则为0.37（相关的显著水平为 $9 5 \%$ ）[6]；北太平洋海冰[18-19]（北太平洋海冰面积指数）与台风（年）生成频次间的相关系数为0.4（相关的显著水平为 $9 9 \%$ ）。

在实际业务应用中，除了预测年台风频次外，还涉及月尺度上台风活动频次的预测，然而较少有文献给出较为实用的方法。前文所列文献所涉及的内容均与台风年活动频次有关：范可等分析前一年12月至当年5月（冬春季）的北太平洋海冰指数对当年台风活动频次的影响；王会军等则选取每年6—9月的北太平洋涛动指数构建当年台风活动频次的分析模型。这些指数没有明显意义上的超前或滞后关系，从时间上来看，更像是因果关系的截取。因此，在业务应用中，构建一个较为实用的台风月频次预报模型颇具应用价值。此类模型所选取或构建的因子应与台风频次具有较好的超前或同期相关关系；除此之外，还应具有以下特点：（1）所构建的指数具有较好的全局特性；（2）对于月尺度数据，台风以扰动或者偏差的形式存在于相应数据（如月平均高度场）中；（3）从人工神经网络等算法上分析，指数的构建方式应相当于图像处理中的池化操作，将重要的信息累积，剔除冗余量；（4）相比于神经网络等智能算法的黑箱特点来说，所构建的指数统计含义更加明确。

据此，本文利用NCEP再分析高度场资料构建了一批指数，基于这些指数，建立了台风月频次模型；第一节主要介绍这些指数的构建方法，第二节给出台风月频次模型的检验效果。

# 1数据与方法

# 1.1指数构建

构建能表征台风活跃季月频次的指数，需要将对台风活动有影响的要素、与台风活动相关联的区域综合起来。结合前人的分析和研究结果，本文着重选取两个区域参与指数构建：大区（ $0 ^ { \circ } { \sim } 3 6 0 ^ { \circ } \mathrm { ~ E ~ }$ $- 9 0 ^ { \circ } { \sim } 9 0 ^ { \circ } \mathrm { N }$ ）和小区（低纬西太平洋： $1 2 0 ^ { \circ } { \sim } 1 7 0 ^ { \circ } \mathrm { E }$ ， $0 ^ { \circ } { \sim } 2 5 ^ { \circ } \mathrm { ~ N ~ }$ ）区域。采用这两个区域参与构建指数源于西北太平洋台风活动的特点：

1） 西北太平洋台风活动较为频繁，约占全球热带气旋总数的 $1 / 3 ^ { [ 1 ] }$ ，是全球的活跃要素；2） 多种天气/气候现象[6-8,12-16,18-19]均与台风有一定联系；3） 算法所需考虑的全局性使得大区应纳入考虑范围;4）小区涵盖台风活动的主要区域[11及对台风活动有较大影响的西太暖池区域[20]，总体上能反映  
源地的特点，这个特点在大区中可能会被掩盖;5）在台风活动初期，台风的影响未必能在整层大气中有明显的体现，即小区指数与台风频次的  
相关性不见得有多高，但这种影响应当被纳入进去;6）基于越赤道气流对台风影响[8的考虑，本文将小区扩展到赤道附近;7）本文主要关注台风月频次，故而选取区域应与台风活动区域关联较为紧密，其他区域对台风

活动的影响可能没有小区直接。

综合而言，分成大区和小区两个部分是因为所选取的算法既要表征整体特征，也要凸显源地特点，故而将两个区域分开。参与构建指数的要素主要为： $2 0 0 \mathrm { { h P a } }$ 高度场[4]、 $5 0 0 \mathrm { { h P a } }$ 高度场和 $8 5 0 \mathrm { { h P a } }$ 高度场。

选取 $5 0 0 \mathrm { { h P a } }$ 和 $8 5 0 \mathrm { { h P a } }$ 主要是因为这两个层次在日常的预报中较为常用；只选取高度场而不采用其它要素场是因为其它与速度相关的要素（水汽通量、散度、涡度）及水汽分布等均能在高度场中有所反映：高度场可以表征大尺度流场特征；在海上，月平均水汽分布与高度场，尤其是 $5 0 0 \mathrm { { h P a } }$ 副高活动区域、低空辐合辐散区域等配合紧密。此外，散度、涡度、垂直速度等均是诊断量，计算的误差和偏差在量级上难以控制，不易提取特征，故而未将其列入考虑范畴。

在指数构建过程中，必须将全局特征纳入指数中[21-22]。因此，本文选取三维变分同化中的代价函数[23]用于构建指数，其中代价函数中的误差均由偏差替代（由于选用的是格点再分析资料，故而构建指数的代价函数不包含观测部分）：

1）计算要素场H（要素场维度为 $m { \times } n$ ）的偏差 $\mathsf { H } _ { b i a s }$ ${ \sf H } _ { b i a s } = { \sf H } - { \sf H } _ { m e a n }$ (1)式中， ${ \sf H } _ { m e a n }$ 为要素场H的气候平均态，可用H的多年平均值替代，基于该偏差场序列构建偏差协方差矩阵 ${ \sf H } _ { 1 }$ ( $\mathbf { \lambda } _ { m } \times \mathbf { \lambda } _ { m }$ ）和 $H _ { 2 }$ ( $\mathbf { \lambda } _ { n \times n }$ ）。

2）利用Chen[22]给出的代价函数计算方法构建指数 $I _ { h }$ $I _ { h } \mathrm { = T r a c e ( ^ T \mathsf { H } } _ { b i a s } \mathsf { H } _ { 1 } \mathsf { H } _ { b i a s } \mathsf { ) } + \mathrm { T r a c e ( \mathsf { H } } _ { b i a s } \mathsf { H } _ { 2 } ^ { \mathsf { T } } \mathsf { H } _ { b i a s } \mathsf { ) }$ 式中，Trace为计算矩阵迹的算子，上标T表示矩阵的转置运算。

# 1.2数据、模型及检验方法

本文以NCEP再分析月平均高度场资料构建相关指数(http://www.esrl.noaa.gov/psd/data/gridded/data.ncep.reanalysis.html），该资料空间分辨率为 $2 . 5 ^ { \circ } { \times } 2 . 5 ^ { \circ }$ ，时间分辨率为1个月；所采用的台风数据来源于中国气象局热带气旋资料中心（http://tcdata.typhoon.org.cn/zjljsjj_sm.html）提供的CMA最佳路径数据集[24]（1979 年1月至2016年6月），各月台风频次见图1（若某个台风跨月，则在所跨的月份中各计1次）。

![](images/f969a80c3c5ab2f5029a4f90254586977a89693cd334cc802b2003650928de07.jpg)  
图1西北太平洋台风活跃季台风频次示意，其中，Average表示各月多年平均值

Fig.1 The frequency of typhoon in the concentrated period of typhoon activity in the Western North Pacific,in the figure, Average is the multi-year average.

本文以逐步回归模型[25作为主要的应用模型，第2节中主要检验模型所选用的因子是否具有代表性：首先通过生成6个随机数挑选出6个年份的数据构建对比库（随机对比检验部分：PART_R），以其余数据固定选择的指数因子；其后在交叉对比检验部分（共分为PART1、PART2和PART3三个部分），采用相同的因子建模并进行对比检验，以验证所选的指数因子的可靠性。

# 2指数指示效果及模型效果检验

# 2.1指数指示效果

本文共构建了6个关于台风月活动频次的指数，这些指数与台风频次序列的相关性分析见表1,表中超前指的是指数超前1个月，即每年的4—9月的指数序列对应于5—10月的台风序列，相关系数采用Pearson 相关系数。

表1各个指数与台风频次的相关系数  
Tab.1 The correlation coefficients of each index and the monthly frequency of typhoons   

<html><body><table><tr><td>指数类型</td><td>同期</td><td>超前</td></tr><tr><td>200 hPa（大区）</td><td>0.2971</td><td>0.7436</td></tr><tr><td>500 hPa（大区）</td><td>0.2579</td><td>0.7247</td></tr><tr><td>850hPa（大区）</td><td>-0.0322</td><td>0.4910</td></tr><tr><td>200 hPa（小区）</td><td>0.2393</td><td>0.0939</td></tr><tr><td>500 hPa（小区）</td><td>-0.1088</td><td>0.1434</td></tr><tr><td>850 hPa（小区）</td><td>0.4211</td><td>0.1593</td></tr></table></body></html>

6 个指数中，同期指示效果较好的（相关系数绝对值大于0.3以上）为 $8 5 0 \mathrm { { h P a } }$ 小区的指数，具有超前指示效果的为大区的3个指数。在超前效果较好的3个指数中， $2 0 0 \mathrm { { h P a } }$ 和 $5 0 0 \mathrm { { h P a } }$ 的大区指数要远高于北太平洋海冰、南极涛动、ENSO 等指数，其相关系数在0.7以上，基本可以表征每年5—10月间逐月台风频次，具有明显的实用价值（超前相关）。

# 2.2指数模型效果检验

经逐步回归筛选，入选的因子包括 $2 0 0 \mathrm { { h P a } }$ 的大区指数（超前）、 $5 0 0 \mathrm { { h P a } }$ 的小区指数（同期和超前）和 $8 5 0 \mathrm { h P a }$ 的小区指数（同期）。台风月频次模型形式如式（3）：

$$
p { = } a _ { 1 } { ^ * } I _ { 5 0 0 { _ { - } ^ { s } } { _ { - } } b } { + } a _ { 2 } { + } a _ { 3 } { ^ * } I _ { 5 0 0 { _ { - } ^ { s } } { _ { - } } m } { + } a _ { 4 } { ^ * } I _ { 8 5 0 { _ { - } ^ { s } } { _ { - } } m } { + } a _ { 5 } { ^ * } I _ { 2 0 0 { _ { - } ^ { b } } { _ { - } } b }
$$

式中， $p$ 代表当月台风活动频次， $a _ { i }$ 代表权重系数， $I$ 代表对应指数，其中，下标数字代表高度场层次，$g$ 代表全球， $s$ 代表小区， $m$ 代表同期， $b$ 代表超前。在后期的应用过程中，可以在此基础上，将同期的指数用数值预报进行替换，同时采用逐步回归模型，校准入选参数，已达成预报效果。

本文主要采用相关系数（CC）、平均误差（ME）、平均绝对误差（MAE）、均方根误差

（RMSE），模式输出与台风月频次（观测）完全一致占对比检验序列中的比例（ $P _ { 1 0 0 \% }$ ）、模式输出与观测的误差绝对值小于等于1个占比（ $\cdot P _ { 1 }$ ）、误差绝对值小于等于2个占比（ $P _ { 2 }$ ）以及误差绝对值小于等于3个占比（ $\mathbf { \rho } _ { P _ { 3 } }$ ）等参数用以综合对比检验模型（3）的可靠性和回报效果（模型（3）通过显著性检验）。

在随机对比检验部分，通过随机数生成器，任意生成6年作为对比年（本文生成的6年为：1986年、1999年、2002年、2008年、2011年、2016年），余下年份用于构建回归方程（3）的系数。交叉检验部分的三个分组依次为：顺序1，1990年9月至2016年6月参与构建回归模型，1979年1月至1990年8月用于对比检验（预测值与观测值差异分布如图3）；顺序2，1990年9月至2002年6月用于对比检验（预测值与观测值差异分布如图4），其余数据参与构建回归模型；顺序3，2002年7月至2016年6月用于对比检验（预测值与观测值差异分布如图5），其余数据参与回归模型构建。各对比部分模型系数如表2：

<html><body><table><tr><td>对比组</td><td>a1</td><td>a2</td><td>a3</td><td>a4</td><td>a5</td></tr><tr><td>随机</td><td>-0.5362</td><td>-78.9403</td><td>-0.3808</td><td>0.7018</td><td>1.9832</td></tr><tr><td>顺序1</td><td>-0.4477</td><td>-69.3302</td><td>-0.4639</td><td>0.6640</td><td>1.7842</td></tr><tr><td>顺序2</td><td>-0.5750</td><td>-72.9784</td><td>-0.2500</td><td>0.7527</td><td>1.7658</td></tr><tr><td>顺序3</td><td>-0.4314</td><td>-84.3862</td><td>-0.4238</td><td>0.6425</td><td>2.1020</td></tr></table></body></html>

表2中的各个系数相对稳定在一个区间内，其中， $5 0 0 \mathrm { { h P a } }$ 小区指数与台风频次呈负相关关系（ $a _ { 1 }$ 和 $a _ { 3 }$ ）， $8 5 0 \mathrm { { h P a } }$ 小区指数（同期）和 $2 0 0 \mathrm { { h P a } }$ 全球指数（超前）（ $a _ { 4 }$ 和 $a _ { 5 }$ ）与台风频次呈正相关关系，且全球指数所占比远高于小区指数。据此可以看出 $2 0 0 \mathrm { { h P a } }$ 全球指数的趋势变化对于台风频次趋势变化的影响较大（由最小二乘法可得出以下结论：如果某一信号可由其他信号线性叠加而成，则该信号趋势变化等于各个组成信号的趋势变化乘以叠加权重）。

随机对比检验结果见表3、图2，交叉对比检验结果见表4、图3—5，图中observation指的是基于CMA台风最佳路径数据统计得到的每个月台风活动频次数据。

表2各对比组部分模型权重系数 Tab.2 Weight Coefficients in the model of different comparison parts   
表3回归结果的随机检验部分（PARTR）  
Tab.3 The part of random testof regression results（PART_R)  

<html><body><table><tr><td>CC</td><td>ME</td><td>MAE</td><td>RMSE</td><td>P100%</td><td>P</td><td>P2</td><td>P</td></tr><tr><td>0.8363</td><td>-0.2500</td><td>1.1250</td><td>1.4811</td><td>0.3125</td><td>0.6563</td><td>0.9062</td><td>1.0000</td></tr></table></body></html>

![](images/7a96bd67e70d911be268a3750a7816a34923066bda8496192b1232bcad76da3d.jpg)  
图2观测序列和回归序列对比（a）及误差（观测与模型结果之差）分布（b）：（PART_R)  
Fig.2(a)Thecomparisonbetween theseriesofobservationand model-outputs; (b)the errordistribution (observation-model

output): (PART_R)

表4回归结果的交叉检验部分  
Tab.4 The part of cross test of regression results   

<html><body><table><tr><td>对应图示</td><td>CC</td><td>ME</td><td>MAE</td><td>RMSE</td><td>P100%</td><td>P1</td><td>P2</td><td>P</td></tr><tr><td>图2</td><td>0.7917</td><td>0.7714</td><td>1.4571</td><td>1.8663</td><td>0.2571</td><td>0.6286</td><td>0.8143</td><td>0.9000</td></tr><tr><td>图3</td><td>0.8167</td><td>-0.1286</td><td>1.3857</td><td>1.7356</td><td>0.2286</td><td>0.5571</td><td>0.8429</td><td>0.9857</td></tr><tr><td>图4</td><td>0.8073</td><td>-0.6667</td><td>1.3333</td><td>1.5315</td><td>0.1905</td><td>0.6429</td><td>0.8571</td><td>0.9762</td></tr></table></body></html>

![](images/9c388d38cb25f5a0d5109c56afc02024eb03eaeceabe5d2b08ab0fcd1d201ee9.jpg)  
图3观测序列和回归序列对比（a）及误差（观测与模型结果之差）分布（b）：（PART1）

Fig.3(a)Thecomparisonbetweentheseriesofobservationandmodel-outputs; (b)theerordistribution (observation-model

output): (PART1)

![](images/cf52135bcc299d3a1f6a271c208713603435f45298e299c8a941dd88e9fda402.jpg)  
图4观测序列和回归序列对比（a）及误差（观测与模型结果之差）分布（b）：（PART2）

Fig.4(a)Thecomparisonbetweenthe seriesofobservationandmodel-outputs; (b)theerordistribution (observation-model

output): (PART2)

![](images/fa1fb8e97e0fffb3994f053de833c7b7836f6aab3df552d317dd2fab7d016dbf.jpg)  
图5观测序列和回归序列对比（a）及误差（观测与模型结果之差）分布（b）：（PART3）

Fig.5(a)Thecomparisonbetween theseriesofobservationand model-outputs;(b)the erordistribution (observation-model

output): (PART3)

对比检验结果表明，预报结果与观测结果的走势基本吻合：回归结果与观测的相关性基本维持在0.8（在随机检验部分，由于用以建模的样本库随着随机数的变化而变动，其结果可能存在差异），输出误差在2个占比以内基本上控制在 $80 \%$ ，输出误差在1个以内占比基本控制在 $60 \%$ 左右，且随机检验部分和交叉检验部分均包含一般年和ENSO，总体而言模型结果具有一定的参考价值。在台风活跃季内的月预报业务中，预报员需预报次月台风个数，次月台风个数的预报量为m—n个（如6—8个），在这种预报方案下，本文所给出的指数模型的预报结果基本可以直接使用。

# 3结论

1）在西北太平洋台风活跃季，本文所构建的部分指数与台风月频次有着较好的相关关系：基于小区的低层指数与台风活动频次的同期相关性较好（0.4211）；而两个大区指数（ $2 0 0 \mathrm { { h P a } }$ 、 $5 0 0 \mathrm { { h P a } }$ ））与台风活动频次超前相关性极好，相关系数均达0.7以上（ $2 0 0 ~ \mathrm { { h P a } }$ 大区指数对应相关系数为

0.7436， $5 0 0 \mathrm { { h P a } }$ 大区指数对应相关系数为0.7247）。这3个指数在台风月频次预测和分析中具有参考价值。

2）模型（3）输出结果与台风活动频次的相关性维持在0.8左右，模型输出与观测之间误差的绝对值在2个以内约占对比样本总数的 $80 \%$ ，1个以内占 $60 \%$ 左右，完全击中约占 $20 \%$ （表3、4），在西北太平洋台风活跃季，基于这些指数构建的模型在台风月频次预测中具有一定的应用价值。

# 参考文献：

[1]World Meteorological Organization. Global guide to tropical cyclone forecasting [R]. GENEVA: WMO,2017.  
[2]陈联寿，端义宏，宋丽莉，等.台风预报及其灾害[M].北京：气象出版社，2012：1-4.  
[3]陈玉林，周军，马奋华.登陆我国台风研究概述[J].气象科学，2005，25(3)：319-329.  
[4]陈秋士，桑建国.大尺度运动对台风形成影响的天气分析[J].气象学报，1965，37(4)：486-497.  
[5]李崇银.环境流场对台风发生发展的影响[J].气象学报，1983，41(3)：275-284.  
[6] 李肖雅，吴立广，宗慧君.季风涡旋影响西北太平洋台风生成初步分析[J].大气科学学报，2014，37(5): 653-664.  
[7]王允宽，刘俊清，黄中华.台风形成中冷空气作用的模拟实验[J].大气科学，1988，12(4)：374-381.  
[8]陈笑晨，智协飞，赵欢，等.澳大利亚冷空气活动对西北太平洋热带气旋生成的影响[J].大气科学学报，2017，40(1)：61-70.  
[9]丁一汇，ER莱特.影响西太平洋台风形成的大尺度环流条件[J].海洋学报，1983，5(5)：561-574.  
[10]吴国雄.海温异常对台风形成的影响[J].大气科学，1992，16(3)：322-332.  
[11]李维京.现代气候业务[M].北京：气象出版社，2002：160-163.  
[12] 潘静，李崇银，宋洁.MJO活动对西北太平洋台风的调制作用[J].大气科学，2010，34(6)：1059-1070.  
[13] 周伟灿，沈海波，赵海坤.热带季节内振荡对西北太平洋台风生成的大尺度环境的影响[J].大气科学学报，2015，38(6)：731-741.  
[14] 张宏杰，武亮，黄荣辉.两类ElNino型对西北太平洋季风槽及热带气旋生成的可能影响[J].气候与环境研究，2018，23(2)：150-160.  
[15]王会军，范可.西北太平洋台风生成频次与南极涛动的关系[J].科学通报，2006，51(24)：2910-2914.  
[16]王会军，孙建奇，范可．北太平洋涛动与台风和飓风频次的关系研究[J].中国科学(D辑)，2007，37(7): 966-973.  
[17]寿邵文.中国天气概论[M].北京：气象出版社，2012：345-347.  
[18]范可．北太平洋海冰，一个西北太平洋台风生成频次的预测因子?[J].中国科学：地球科学，2007，37(6): 851-856.  
[19]范可．西北太平洋台风生成频次的新预测因子和新预测模型[J].中国科学：地球科学,2007，37(9): 1260-1266.  
[20] 李克让，周春平，沙万英.西太平洋暖池基本特征及其对气候的影响[J].地理学报，1998，53(6):511-519.  
[21]陈璇，郑崇伟，张伟涛，等.更为广义的线性回归模型及其气象应用[J].解放军理工大学学报自然

科学版，2017，18(2)：144-149.[22] 陈璇，游小宝，郑崇伟，等.一种新的线性回归模型及其应用示例 [J].大气科学，2019，43(2):389-400.[23] Chen Xuan.A preliminary study on dimension-reduction algorithm for variational methods in threedimensions [OL]. [2019-09-28]. https://www.preprints.org/manuscript/201801.0293/v1.[24] Ying Ming, Zhang Wei, Yu Hui,et al. An overview of the China Meteorological Administration tropicalcyclone database [J]. Journal of Atmospheric and Oceanic Technology, 2014,31: 287-301.[25]黄嘉佑.气象统计分析与预报方法[M].北京：气象出版社，2004：81-100.

# The establishment of the indexs on the monthly frequency of typhoon during active season and its application

CHEN Xuan (The 75839 Army of the PLA, Guangzhou 510510, China)

Abstract: The prediction for the frequency of typhoon is one of important contents in the flood season meteorological consultation. At present, the schemes used in the consultation are mainly based on modeloutputs,and not suitable for qualitatively analysis.In this paper,the monthly average data of height from NCEP (National Centers for Environmental Prediction) and the deviation information based on the average data are applied for establishing some indexes characterizing the monthly numbers of typhoon in western North Pacific by using the cost function of data assmilation models,and an index model for the monthly frequency of typhoon during active season is established.The results show that, the correlation between the indexes series and the typhoon frequency series can reach O.7,and the model based on the indexes is a good indicator of the monthly frequency information ofthe typhoon active season,which has a good reference value for the monthly frequency prediction of typhoon.

Keywords:deviation; index; typhoon; western North Pacific