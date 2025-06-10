# SAGE测光巡天数据处理方法研究

郑捷1²，赵刚1,²，王炜1,，范舟‘，赵景昆1，谈克峰

1中国科学院光学天文重点实验室（国家天文台），北京100101,²中国科学院大学天文与空间科学学院，北京100049,中国科学院南美天文中心，国家天文台，北京100101

摘要 SAGE 是自主设计的能够准确计算恒星大气参数以及消光的新测光系统。对北天除银盘外共计约12,000 平方度的天区开展了SAGE 系统测光巡天，计划获取约5亿颗恒星的高精度测光数据。单次曝光条件下 $1 0 0 \sigma$ 完备星等 $u _ { S C } \sim 1 7 . 3$ ， $\nu _ { S A G E } { \sim } 1 6 . 8$ （AB星等）。这为研究银河系提供宝贵的测光资料。介绍了巡天专用的数据处理程序的研究和开发，主要研究了针对单幅图像的快速自动化处理过程，重点介绍数据改正、天体测量校正、测光和流量定标过程，以及数据结果和数据质量检测等。

关键字测光;巡天;测光系统;数据处理程序中图分类号：P111 文献标识码：A 文章编号：1672-7673(2018)

为了能够更高效、更精确地获得恒星的大气参数，结合多种测光系统的优势，并加入全新设计的滤光片，组成了新测光系统：SAGE 系统。该系统由8个滤光片组成：Stromgren-Crawford u，SAGE $\mathbf { v }$ ，SDSSg、r，i，DDO51，Hα wide，Hα narrow（依次简称为 usc, VsAGE,g,r,i,DDO51, $\mathrm { H a } _ { \mathrm { w } }$ $\mathrm { H a } _ { \mathrm { n } }$ ）。8片滤光片透过率曲线见图1，中心波长和带宽等见表1。SAGE 系统的详细介绍见文[1]，文[1]还详细介绍了 SAGE 巡天的方案和科学目标等。SAGE 测光系统可以提供关于恒星元素丰度和银河系演化（Stellar Abundance andGalactic Evolution，SAGE）的大量信息。自 2013 年起计划进行 Stromgren-Crawford 巡天[2]，之后改用更加优秀的SAGE 测光系统进行原巡天计划。

对北天的 SAGE 系统测光巡天计划覆盖大约12,000 平方度的天区，高精度测光 $( \mathsf { S } / \mathsf { N } { = } 1 0 0 \sigma )$ 完备星等覆盖范围为 $\mathrm { u _ { S C } } \sim 1 1 . 0 - 1 7 . 5$ 等， $\mathrm { v _ { S A G E } } \sim 1 0 . 0 - 1 6 . 5$ 等， $\mathrm { g r i } \sim 9 . 0 - 1 5 . 5$ 等，相当于类太阳恒星的完备距离为 $\sim 1 \mathrm { k p c }$ 。 $5 \sigma$ 探测极限 $\mathrm { u } _ { \mathrm { S C } } \sim 2 1 . 5$ 等， $\mathbf { v } _ { \mathrm { S A G E } } \sim 2 1$ 等， $\mathrm { g r i } \sim 1 9 . 5$ 等，到太阳邻域 $\sim 6 . 4 \mathrm { k p c }$ 的距离。本巡天于2015年展开，计划在4-5 年内完成测光巡天观测以及流量定标、天测定标，得到一个深度均匀的北天 SAGE 测光星表，并利用该星表开展一系列以银河系为主的科学研究。

表1SAGE 测光系统定义Table 1 The SAGE photometric system  

<html><body><table><tr><td>波段</td><td>usc</td><td>VSAGE</td><td>g</td><td>r</td><td>i</td><td>DD051</td><td>Han</td><td>Hαw</td></tr><tr><td>中心波长 (A)</td><td>3425</td><td>3950</td><td>4770</td><td>6231</td><td>7625</td><td>5130</td><td>6563</td><td>6563</td></tr><tr><td>带宽（A)</td><td>300</td><td>290</td><td>1387</td><td>1373</td><td>1526</td><td>154</td><td>29</td><td>136</td></tr></table></body></html>

![](images/d06bbe47beffb7f8dd5a86ba12eca394908a9324097dff07c54b2e3380e40bc3.jpg)  
图1归一化后的SAGE 测光系统滤光片透过率曲线 Fig.1 The normalized transmission curves of the SAGE filters

# 1巡天观测

本巡天覆盖赤纬 $\mathrm { D e c } > { - 5 ^ { \circ } }$ 的北天天区，并且避开了亮星密集的银盘部分（银纬 $| b | < 1 0 ^ { \circ } ~$ ），以避免了过多的亮星以及图像污染。此外，基特峰和南山站秋冬季气象条件较好，为集中观测秋冬季天区，以期在有限的时间内获取较为优质的观测数据，避开了 $1 2 ~ \mathrm { { h r } < R . A . < 1 8 ~ \mathrm { { h r } } }$ 的区域。图2展示了本巡天计划覆盖的约12,000平方度天区。

为了便于流量校正，每个观测天区和相邻天区之间都留重叠区域。在制定巡天规划时，以同一赤纬为一个条带，划分天区。在同一赤纬，相邻天区之间有约 $2 0 \%$ 的重叠，而不同赤纬之间，南北条带之间也有约 $2 0 \%$ 的重叠。图3展示了Bok 望远镜6352号观测天区与相邻天区之间的重叠情况，南山一米望远镜观测天区重叠情况类似，但是不同望远镜由于视场大小不同，天区划分并不相同。此外，图中仅展示了视场的外轮廓，CCD 内部的拼接缝未体现。

本巡天使用了3 台望远镜共同完成观测工作：美国亚利桑那大学斯图尔德天文台位于基特峰的博克90英寸（约 $2 . 3 ~ \mathrm { ~ m ~ } ^ { \cdot }$ ）望远镜(The 90-inch Bok Telescope at Steward Observatory of The University ofArizona,USA，简称 Bok 望远镜)，中国科学院新疆天文台南山观测站的 $1 \mathrm { m }$ 大视场望远镜（简称南山一米望远镜，NOWT），以及乌兹别克斯坦科学院兀鲁伯天文研究所迈丹内克天文台 $1 \mathrm { ~ m ~ }$ 蔡司望远镜（MAOZeiss-1000 Telescope, Maidanak Astronomical Observatory, Ulugh Beg Astronomical Institute, UBAI，简称MAO 望远镜）。

![](images/8bfd8284e85bf27066191b5b6db11776d7f26048afb74dbb6eac425290aa0844.jpg)  
图2SAGE巡天计划覆盖天区 Fig.2 Overlap between survey fields

![](images/76816dd03bc8bc8e56d941f2d9a8cad79b3d742b6635f8ceece1e529931e5d05.jpg)  
图3巡天天区重叠情况示意图 Fig.3 Overlap between survey fields

# 1.1Bok望远镜

Bok 望远镜一台口径90英寸（约 $2 . 3 \mathrm { ~ m ~ }$ ）的赤道式望远镜，隶属于美国亚利桑那大学斯图尔德天文台，位于基特峰，北纬 $3 0 ^ { \circ } 5 7 ^ { \prime } 4 6 ^ { \prime \prime } . 5$ ，西经 $1 1 1 ^ { \circ } 3 6 ^ { \prime } 0 1 ^ { \prime \prime } . 6$ ，海拔高度 $2 0 1 7 \mathrm { m }$ ，典型视宁度优于1.5"。

本巡天使用Bok 望远镜位于主焦点的90Prime 大视场相机，终端设备由4块蓝敏背照式 $4 \mathrm { K } \times 4 \mathrm { K }$ CCD拼接而成。视场的大小约为 $1 . 0 8 ^ { \circ } \ \times 1 . 0 3 ^ { \circ }$ ，每像元大小（pixel-scale）约 $ { 0 . 4 5 4 " }$ 。CCD之间有接缝（赤经方向宽约约 $1 6 6 "$ ，赤纬方向宽约约 54"）。为提高读出速度，每个CCD 由4门并行读出。在选用慢速读出模式下，全视场读出需要约 $3 7 \ s$ ，读出噪声约6-10个电子。90Prime的布局如图4，图中单位为像元数且并未完全按照比例绘制。

![](images/377440b9493df310ba5d054dd140f345e7ef5b2d7a777b309e26f9895dea994c.jpg)  
图490Prime 拼接式相机布局示意图，图中单位为像元，并未完全按比例绘制Fig.4 Layout of 90Prime,unit is pixel，not to scale

由于 Bok 望远镜口径相对另外两台望远镜较大，集光性能强，台址大气透明度较高，而且相机在蓝端效率较高，所以用于蓝端的两个窄波段usc 和VsAGE 的观测。

# 1.2 南山 $1 \mathsf { m }$ 望远镜

中国科学院新疆天文台的 $1 \mathrm { ~ m ~ }$ 大视场望远镜位于乌鲁木齐市西南的南山观测站，北纬 $4 3 ^ { \circ } 1 6 ^ { \prime } 4 5 " . 0$ 东经 $8 7 ^ { \circ } 1 0 ^ { \prime } 3 8 " . 3$ ，海拔高度约 $2 0 8 1 \mathrm { ~ m ~ } ^ { \left[ 3 \right] }$ ，平均视宁度约为 $2 . 0 "$ 。该望远镜为地平式，主焦点上配备了大视场相机，有效视场约 $1 . 5 ^ { \circ } \times 1 . 5 ^ { \circ }$ ，装备有 $4 K \times 4 K$ 蓝敏背照式CCD，由4个门进行并行读出。典型的读出时间约 $4 0 \ s$ ，读出噪声约8-10个电子。本巡天使用了该望远镜配备的 $\mathrm { S D S S ~ g , ~ r , }$ i滤光片。望远镜采用文[4]开发的电控系统软件进行控制。

由于SDSS 完成了北天的大部分天区，和本巡天计划天区之间有约9000 平方度的重叠且深度满足要求。所以只需要对SDSS覆盖之外约3000平方度进行补充观测即可。

# 1.3MAO 望远镜

乌兹别克斯坦科学院兀鲁伯天文研究所的MAO 望远镜目前正在进行技术改造，改造之后将具有 $3 7 ^ { \prime } \times$ 37'的视场。该望远镜为赤道式 $1 ~ \mathrm { ~ m ~ }$ 反射式望远镜，位于迈丹内克观测站，北纬 $6 6 ^ { \circ } 5 3 ^ { \prime } 4 7 "$ ，东经$3 8 ^ { \circ } 4 0 ^ { \prime } 2 2 ^ { \prime \prime }$ ，海拔高度约 $2 5 9 3 \mathrm { ~ m } ^ { \left[ 5 \right] }$ 。计划在MAO 望远镜上进行 $\mathrm { H } \alpha _ { \mathrm { w } }$ 和 $\mathrm { H } \alpha _ { \mathrm { n } }$ 的观测。

# 1.4观测进度

本巡天自 2015 年秋季开始正式观测。截止 2017 年底，各波段进展见表 2。Bok 望远镜的usc 和 VsAGE观测预计将于2019 年完成，而在南山 $1 \mathrm { ~ m ~ }$ 的 $\mathbf { g } , \mathbf { r } , \mathrm { ~ i ~ }$ 波段在2018年可以观测完成。MA0望远镜目前正在升级改造中，预计于2018 年可以开始进行观测。

Table 2 The progress of the SAGE survey (by the end of 2017)   

<html><body><table><tr><td>波段</td><td>usc</td><td>VSAGE</td><td>g</td><td>r</td><td>i</td></tr><tr><td>天区数</td><td>12364</td><td>11376</td><td>3359</td><td>3354</td><td>3353</td></tr><tr><td>覆盖面积(deg2)</td><td>7913</td><td>7280</td><td>3359</td><td>3354</td><td>3353</td></tr><tr><td>完成百分比 (%)</td><td>69.7</td><td>64.2</td><td>79.0</td><td>78.8</td><td>78.8</td></tr></table></body></html>

# 2 图像预处理

图像预处理主要对图像本身进行改正，消除设备带来的不一致性，以及由设备引起的部分图像缺陷。主要包括过扫描改正（overscan）、本底改正（bias）、平场改正（flat-field）、串扰改正（crosstalk）等步骤，但是对暗流（darkcurrent）不做改正。

# 2.1过扫描改正

在 Bok 望远镜和南山1m望远镜拍摄的图像中，都提供了过扫描区，过扫描区表达了图像读出时的电压水平，是针对本幅数据的本底。图5展示了Bok望远镜的每个门过扫描区和图像区之间的布局关系，单位为像元（未按比例绘制）。南山1m 望远镜的过扫描区分布与此类似，但是宽度为32像元。

改正时，程序对每一门图像的过扫描区逐行取中值，然后对图像区的每一行数据，减去该行对应的过扫描区中值，完成过扫描改正。由于过扫描区数据起伏较大，因此对求出的中值进行了高斯平滑。平滑前后的过扫描区片段如图6。

对于所有的单次曝光图像，包括本底、平场、科学图像等，都是先进行过扫描改正，然后再进行后续处理。

![](images/c6dd45e6394175a075b912a072ace813476261701fb21c39430e94f581ec5e09.jpg)  
图5Bok望远镜过扫描区分布示意图，未按比例绘制（像元） Fig.5 Layout of image and overscan of Bok，not to scale (pixel)

![](images/5d8fe31d473b686506f49407d4295013e78a7124231841b0c0f776775bfca3b9.jpg)  
图6overscan 片段（红色）以及平滑后的曲线（蓝色) Fig.6 ADU of overscan region (red) and a smoothed curve (blue)

# 2.2 本底改正

观测人员在每个晚上的观测前后各拍摄一组本底，通常为各10幅。对每一幅本底图像进行过扫描改正后，对每个像元的多次观测取中值得到本底的结构。在后续的平场图像和科学图像数据处理时，在进行了自身的过扫描区改正之后，都会利用合并之后的本底结构进行改正。

# 2.3暗流

Bok 望远镜和南山1m望远镜都采用液氮制冷的方式，CCD 在冷却之后，暗流很小。经测定，Bok 望远镜的CCD 暗流约为 $7 . 2 \mathrm { e } ^ { - } / \mathrm { p i x e l / h r }$ ，而南山 $1 \mathrm { m }$ 望远镜则不超过 $2 \mathrm { e } ^ { - }$ /pixel/hr。由于本巡天采用的曝光时间都小于 $6 0 \ : s$ ，暗流带来的影响相比读出噪声等可以忽略不计，因此未进行暗流改正。

# 2.4平场改正

# 2.4.1Bok望远镜平场改正

在 Bok 望远镜观测时，在每夜观测前后都为每个波段各拍摄一组（通常是10 幅）圆顶平场（domeflat），并进行合并。圆顶平场的优点是不受天气条件影响，单幅ADU 值高（通常控制在20,000 至30,000），信噪比高，能够比较好地反映像元之间的差异性。但是圆顶平场的照明并不能很好地反映望远镜上的真实入射情况。另外一方面，利用每晚实际观测得到的科学图像（每晚大约200到400幅）进行中值合并，得到当晚的超级平场。超级平场反映了真实的望远镜照明分布，例如比较均匀的入射光场，和观测时相同的光路等。但是由于单幅科学图像的天光背景约在20-40ADU（随波段不同），即使将每个晚上的全部图像合并，超级平场的ADU 值较低，信噪比仍不高，不能反映像元之间的各像元差异，不适合直接用于平场改正。因此，参考北京-亚利桑那巡天（Beijing-Arizona Sky Skuvey，BASS）[]的数据处理方法，利用二维高斯平滑后的超级平场对圆顶平场进行大尺度的照明改正，这样既充分利用超级平场改正了照明分布的大尺度结构，也发挥了圆顶平场的高信噪比优势，改正了CCD 像元之间的效率差异。

# 2.4.2南山 $ { \mathrm { 1 m } }$ 望远镜平场改正

南山1m 望远镜没有提供圆顶平场，所以在每晚的黄昏和晨光时间，对每个波段各拍摄若干幅天光平场。天光平场兼顾了较高的信噪比，以及真实的照明情况，是进行平场改正的最佳选择。但是天光平场的观测受到天气影响大，且观测时间窗口短，观测次数较少，容易出现没有适合的天光平场的情况。同时，

由于南山1m 望远镜视场较大，天光平场也存在照明不均匀的问题。因此同样也需要利用当晚的超级平场进行照明改正。

在采用天光平场进行平场改正时，如果遇到当天晚上未拍摄天光平场，或者拍摄不理想的情况下，通常使用时间最近的天光平场代替。

# 2.5串扰及其改正

在多门读出的相机中，当图像中出现饱和星像时，会发生串扰现象。即当一个门的图像中出现饱和时，在其他门读出的图像的相应位置也会出现镜像映射。通常镜像信号和原始信号之间的数之比 $1 0 ^ { - 4 }$ 量级。在源信号同一CCD 的其它门的串扰（Intra-CCD crosstalk），相关系数较大且为正相关，而其它CCD上的串扰（Inter-CCDcorsstalk）则相关系数较小，且大部分为负相关。

通过分析出现串扰现象的图像中串扰源信号和镜像信号之间的相关系数，然后将镜像信号从原始图像中扣减。同样使用 Bok 望远镜进行观测的 BASS 巡天[]，也采用了类似的方法。

(b)

图7展示了Bok 望远镜观测图像上一个典型的串扰现象，以及修正后的数据。图7(a)为一亮星在其他门图像相应位置引起的串扰，图7(b)为改正后的结果。其中右下角门为串扰原始信号，上面的两个门为其它CCD中的门，下方3个门则为串扰源信号所在CCD的其它门。

![](images/fddabfe79f731316cfc8bf93599dc21b3f8f3779aa9eeacd2f47b922c6f6e0c2.jpg)  
图7改正前后的串扰现象 (a)原始数据； (b)改正后数据；箭头所指向为串扰源以及镜像信号 Fig.7 Crosstalk and correction result. (a)original; (b)corrected;source and mirrored signal are pointed.

# 3天体测量定标

天体测量定标的目的是找到图像坐标系和天球坐标系之间的转换关系，在观测时指向的基础上进行校正，最终确定探测的每个源的精确天球坐标。

# 3.1位置定标和图像扭曲（distortion）改正

本程序使用由 Emmanuel Bertin开发的成熟且被广泛使用的天文软件 SCAMP[7]进行天体测量定标。在处理中采用两轮迭代，从而满足初始的较大误差和最终的较高精度。第1轮处理时，采用较大的匹配误差限制，这样可以适应初始FITS文件头中的信息不够精确的情况；第2轮则采取较小的匹配限制，在第1轮初步校正的基础上，能够得到较为精确的最终结果。使用 SCAMP 软件所采用的重要参数见表3。

表3SCAMP重要参数设置Table 3 The configuration of major parameters for SCAMP  

<html><body><table><tr><td>参数</td><td>第1轮取值</td><td>第2轮取值</td><td>说明</td></tr><tr><td>MATCH</td><td>Y</td><td>Y</td><td>是否进行模式匹配</td></tr><tr><td>MATCH_NMAX</td><td>0</td><td>0</td><td>匹配选星上限，0为自动选择</td></tr><tr><td>PIXSCALE_MAXERR</td><td>2</td><td>1.5</td><td>像元比例尺最大误差倍数</td></tr><tr><td>POSANGLE_MAXERR</td><td>5.0</td><td>2.0</td><td>最大方位角偏差（度)</td></tr><tr><td>POSITION_MAXERR</td><td>10.0</td><td>1.0</td><td>最大位置偏差(角分)</td></tr><tr><td>MATCH_RESOL</td><td>0</td><td>0</td><td>匹配分辨率，0为自动</td></tr><tr><td>MATCH_FLIPPED</td><td>N</td><td>N</td><td>是否允许翻转坐标轴匹配</td></tr><tr><td>CROSSID_RADIUS</td><td>25.0</td><td>2.0</td><td>匹配半径(角秒)</td></tr><tr><td>SOLVE_ASTROM</td><td>Y</td><td>Y</td><td>是否计算天测结果</td></tr><tr><td>PROJECTION_TYPE</td><td>SAME</td><td>SAME</td><td>投影类型</td></tr><tr><td>DISTORT_DEGREES</td><td>3</td><td>3</td><td>图像扭曲多项式阶数</td></tr></table></body></html>

标准星方面，采用PPMX（Position and Proper Motions eXtended）星表[8作为天测参考星表。PPMX星表收录了全天约1800万颗恒星的坐标，空间分布均匀。坐标精度高，赤经和赤纬方向误差约 $0 . 0 2 "$ ；星表中恒星亮度适中， $8 5 \%$ 以上星等为 $1 0 . 0 \ \mathrm { \ m a g } < V < 1 5 . 0 \ \mathrm { \ m a g }$ ，与本巡天的观测深度接近，可以很好地与观测图像中的源进行匹配。并且PPMX 星表体积较小，便于在观测现场进行快速数据处理。后续数据处理中计划改用PPMXL[9]等星表进行高精度数据处理。

通常天体测量定标的目的是拟合图像坐标 $( x , y )$ 到天球坐标 $\textstyle ( \alpha , \delta )$ 的转换公式，然后利用该公式计算探测到源的天球坐标。

先将图像坐标系转换为以图像中心为原点的坐标系，并用 $\left( u , \nu \right)$ 表示这个坐标系下的坐标。在不考虑图像扭曲的情况下，使用FITS 文件头中的 $C D i _ { - } j$ 字段 $( i , j$ 取值1,2）所表达的线性转换矩阵 $C D$ ，可以将 $( u , \nu )$ 转换为以角度为单位的过渡平面直角坐标 $( \xi , ~ \eta )$ ，随后根据球面投影计算对应的天球坐标 $\textstyle { \left( \alpha , \delta \right) }$ ，目前使用的球面投影模式是正切投影（TAN模式）。线性转换公式：

$$
\begin{array} { r } { ( \boldsymbol { \xi } ^ { \prime } ) = C D \times \binom { u } { v } , C D = \binom { C D _ { 1 1 } } { C D _ { 2 1 } } } \end{array} C D _ { 1 2 } ) .
$$

由于本巡天使用的望远镜相机视场较大（大于1平方度），并且相机都位于主焦点，焦面实际上为曲面，所以需要对图像进行扭曲（distortion）改正。通常的做法是利用高阶多项式进行拟合。在多种图像扭曲表达方式中，本程序选择 (Simple Imaging Polynomial, SIP)[10]作为图像扭曲的表达形式。SIP 在(1)式提供的线性转换的基础上，利用多项式修正函数 $f , \ g$ 对 $( u , \nu )$ 进行修正，得到：

$$
{ \binom { \xi } { \eta } } = C D \times { \binom { u + f ( u , v ) } { v + g ( u , v ) } } .
$$

在修正函数 $f$ 和 $g$ 中，用 $A _ { p q }$ 和 $B _ { p q }$ 表示多项式单元 $u ^ { p } V ^ { q }$ 的系数，可以写出函数 $f , \ g$ 的形式如(3)式。其中，A_ORDER 和 $B _ { . }$ ORDER表示在 $u , ~ \nu$ 两个方向的阶数，通常二者相同。经过实践测试，本巡天选择$A _ { - } 0 \mathrm { R D E R } = B _ { - } 0 \mathrm { R D E R } = 3$ 。

# 3.2天体测量定标误差

天体测量定标的误差来自多方面。(1)星像的中心位置判断需要通过拟合估计，会带来误差；(2)使用的参考星表提供的坐标自身带有误差，本巡天选用的PPMX星表在赤经、赤纬方向上各有约0.02"的误差；（3）星表提供的自行信息带有误差；（4）在进行匹配时，参考星和图像星之间有一定的坐标差容忍度。所以，最终得到的天体坐标，与其真实值之间存在误差。

# 3.2.1天体测量定标外部误差

通过对比图像中探测到的源与参考星表（PPMX星表）之间的差异，将其作为天体测量定标的外部误差。图8展示了随机选择的一幅图像的天体测量定标外部误差分布图。可以看出天体测量的精确性比较高，标准差约0.1"，并且在赤经、赤纬方向上偏差很小。

![](images/24c17cebf1bc2e1084dbb9c463488c1032547742fa5d3131c427d3ea6d7ee796.jpg)  
图8典型的天体测量定标外部误差Fig.8 External error of the astrometric calibration

# 3.2.2天体测量定标内部误差

通过匹配相邻天区重叠部分的天体，可以得到天体位置定标的内部误差。除了相邻天区的重叠部分，还有一些天区进行了多次观测，也提供了内部定标误差的数据来源。此外，同一个天区的不同波段观测结果，也可以用来得到内部误差。图9展示了对同一天区的两次观测的天体测量定标内部误差，图中可以看

出，双向误差分别为 $\delta _ { \mathrm { R A . } } = 0 . 0 1 4 " { \pm } 0 . 1 4 5 ^ { \prime }$ 和 $\delta _ { \mathrm { { D e c } } } = - 0 . 0 0 2 ^ { \prime \prime } \pm 0 . 1 6 6 ^ { \prime \prime }$ ，弥散很小，并且在两个方向的偏差可以忽略不计。

![](images/4ad64d7fb2b542beb109f427848107a1d4d5c0f5552a7ade0af8d66623c2255b.jpg)  
图9典型的天体测量定标内部误差Fig.9 Internal errors of the astrometric calibration

# 4流量定标

在流量定标上，通常有两种方式。（1）使用测光标准星，在测光夜进行多次观测，得到不同大气质量下的消光情况，并拟合出大气消光曲线，以此计算不同大气质量下的大气消光值，从而对每一幅图像进行大气消光改正，得到视星等；（2）利用已有的巡天星表，和待测天区之间重合的部分进行定标。前者比较复杂，并且要求在测光夜进行，但是定标精度高，并且独立性好；后者操作上简单很多，但是依赖于已知星表的精度，并且在未直接重叠的天区，通过重叠区传递进行定标会损失一定精度。

# 4.1定标方法

对于 SDSS g、r、i 波段，采用 APASS(The AAVSO Photometric All-Sky Survey)[11]、SDSS、Pan-STARRS1（Panoramic Survey Telescope and Rapid Response System）[12]等星表作为流量定标参考。APASS 提供了6千多万颗恒星的测光数据，空间分布上覆盖了全天；深度适中， $1 0 . 0 \ \mathrm { m a g } < V < 1 7 . 0$ mag的恒星超过 $9 0 \%$ ， $7 0 \%$ 以上恒星的g、r、i波段误差小于0.1，和我们的观测深度相比有重叠，适合进行定标。后期将观测流量标准星，提高定标精度。

而对于Usc、VsAGE、DDO51、 $\mathrm { H } \alpha _ { \mathrm { w } }$ 、 $\mathrm { H } \alpha _ { \mathrm { n } }$ 等 5个波段，从经过高精度流量定标的恒星光谱库CALSPEC[13]和 NGSL[14]中选择了与本巡天天区重合或邻近的天区中，光谱型覆盖较全面（A到K型以及白矮星），星等约12至15等，且非变星的恒星的光谱，和滤光片透光率曲线进行卷积，可以得到这些恒星的视星等，可以作为流量定标标准星使用。

在每个观测夜都会对标准星进行5至8次观测，然后通过拟合得到以（4）式描述的大气消光曲线。大气消光曲线是仪器星等相对大气质量的变化曲线。为方便分析，仪器星等被统一归算到1s曝光的仪器星等。由于在相同大气质量下不同波长处的消光略有不同，还需要进行颜色改正。定义 $k _ { \mathrm { x , a } }$ 为大气质量改正系数， $k _ { \mathrm { x , c } }$ 是颜色改正系数，而 $k _ { \mathrm { x } , 0 }$ 是仪器零点。然后利用该消光曲线对当晚的科学观测数据进行流量定标。

$$
\begin{array} { r l } & { u _ { c a l i } - u _ { i n s t } = k _ { \mathrm { u , a } } \times a i r m a s s + k _ { \mathrm { u , c } } \times ( u _ { c a l i } - v _ { c a l i } ) + k _ { \mathrm { u , 0 } } } \\ & { v _ { c a l i } - v _ { i n s t } = k _ { \mathrm { v , a } } \times a i r m a s s + k _ { \mathrm { v , c } } \times ( u _ { c a l i } - v _ { c a l i } ) + k _ { \mathrm { v , 0 } } } \end{array}
$$

图10和图11是2017年9月 Bok 望远镜上观测数据得到的消光曲线，分别为23日usc波段和24日VSAGE 波段。其中 $\mathrm { \ u _ { \mathrm { S C } } }$ 消光曲线为 $0 . 6 1 2 \times$ airmass $^ +$ 0.338mag，拟合残差标准差为 $0 . 0 0 3 3 { \mathrm { ~ m a g } }$ ，VSAGE消光曲线为 $0 . 4 4 3 \times \mathrm { \ a i r m a s s { + 0 . 2 4 1 \mathrm { \ m a g } } }$ ，拟合残差标准差为 $0 . 0 1 5 4 \mathrm { \ m a g }$ 。符合本巡天的精度要求。

后面将在测光夜集中进行流量定标工作，每晚观测 20-30次标准星，从而获得更高的定标精度，预计5-7个测光夜完成所有天区的定标。

![](images/3ac4fbdb1081be6ba9640750c80d9fd68664bad57090d278fed7820173d84860.jpg)  
Fig.10 The atmospheric distinction curve 2017-09-23 Bok uSC

![](images/a3703cad57cc0dd3896e7b664b39693614a45c9fdd89675f3cb310bf48348e35.jpg)  
图10大气消光曲线  
图11大气消光曲线 Fig.11 The atmospheric distinction curve 2017-09-24 Bok vSAGE

# 4.2定标误差

如图3，每个观测天区和每个相邻天区之间都有约 $2 0 \%$ 的面积重叠，利用重叠区内匹配到的源可以进行多次观测的误差分析，此外还随机选择了部分天区进行多次观测，以分析观测质量。图12和图13 展示了某个天区在两次观测中定标的差异。图中红色曲线为每个星等差异的标准差。

![](images/aa9a689d875d7b3af0887de2801690f8a20ca687aa2655b5f680d576f61d4af1.jpg)  
图12uSC波段流量定标误差与星等关系图Fig.12 The error of uSC flux calibration VS mag

![](images/778ab1611a12f245a2dfe24594687cf2f1a551a8f66dddc33d8d1638bbc885db.jpg)  
图13vSAGE波段流量定标误差与星等关系图 Fig.13 The error of vSAGE flux calibration VS mag

# 5 天体测光

# 5.1图像源探测

本巡天数据处理程序调用成熟且广泛应用的测光数据处理软件 Source Extractor(以下简称 SE)[15]对图像进行测光，包括源探测、源定位、源累计探测器计数等。测量所用的重要参数及取值见表4。相比传统常用的图像处理工具包 IRAF（the Image Reduction and Analysis Facility）[16]，SE 调用方便，速度快，便于集成到数据处理程序中，而且SE 能够一次性完成源探测以及测光，不需要分多步进行，还可以同时进行多种模式、多种孔径测光，效率较高。

SE 提供了多种测光模式，例如传统的圆孔径测光，根据给定的孔径进行测光，得到流量信息（FLUX_APER），并计算出对应的仪器星等（MAG_APER）。同时，根据天光背景信息，以及流量的泊松统计误差计算该星的流量误差（FLUXERR_APER）与星等误差（MAGERR_APER）。如果给定了多个孔径，SE 会依次进行不同孔径测光，并且输出一系列结果。此外，SE 还提供了多种不同模型对星像进行测光，常用的如自动孔径测光（MAG_AUTO）、等亮度轮廓测光（MAG_ISOCOR）、Petrosian 模型测光（MAG_PETRO）等。其中Petrosian模型主要用于河外星系的测光，虽然河外星系并非本巡天的主要科学目标，但是对于巡天中观测到的河外星系进行尽可能的记录和处理，也是十分有意义的工作。

除了测光信息，SE也提供了大量关于星像轮廓的信息，如伸长率（ELONGATION）、半高全宽（FWHM）、轮廓椭圆拟合的长短轴、倾斜角等，还提供了多种不同方式得到的星像中心坐标。

参考 SDSS 巡天、BASS 巡天（Beijing-Arizona Sky Survey）等，本巡天也选择自动孔径测光模式作为主要输出。自动孔径模式具有较好的适应性，能够自动根据星像的半高全宽进行选择孔径，并且采用椭圆孔径而非圆孔径，对恒星的流量能够进行比较全面、精确的估算。与此同时，也提供多种不同测光模式（包括不同孔径）的测光结果供用户选择。此外，还对孔径测光进行了生长曲线改正，以期取得精度较高的测光结果。

表 4 Source Extractor 重要参数设置Table 4 The configuration of major parameters for Source Extractor  

<html><body><table><tr><td>参数</td><td>取值</td><td>说明</td></tr><tr><td>DETECT_MINAREA</td><td>5</td><td>探测目标时最小面积要求</td></tr><tr><td>DETECT_THRESH</td><td>4.0</td><td>探测目标时最低探测下限</td></tr><tr><td>ANALYSIS_THRESH</td><td>4.0</td><td>分析目标时最低探测下限</td></tr><tr><td>PHOT_AUTOPARAMS</td><td>2.5,3.5</td><td>MAG_AUTO 参数，Kron 因子和最小半径</td></tr><tr><td>SATUR_LEVEL</td><td>45000.0</td><td>像元饱和上限1</td></tr><tr><td>MAG_ZEROPOINT</td><td>25.0</td><td>仪器星等零点</td></tr></table></body></html>

1：饱和上限为进行曝光时间归一化以及增益归一化之前的数值。

# 5.2孔径测光以及孔径改正

本程序利用SE的APERTURE测光程序计算源的圆孔径测光流量。

对于孔径测光，孔径大小的选择是影响测光质量的重要因素。孔径增大时，源的流量能够更多地包括在其中，因此对流量的估计就更加完备。但是随着孔径的增大，天光背景噪声也更多地被包含进去，对暗源的信噪比影响尤为明显。因此需要根据源的亮度选择合适的孔径。另外一方面，为了正确进行流量定标，同一图像中的源应以相同的方式进行测光。为了提高暗源的信噪比，利用图像中孤立的、信噪比高的、非饱和的亮星，求出仪器星等相对孔径的变化曲线，即孔径生长曲线，然后利用该曲线对其他源进行孔径校正。通过生长曲线进行孔径改正测光比单一孔径测光能够较好地提高处理质量[17-18]。

由于焦面的不同区域的点扩散函数（Point Spread Function,PSF）不同，导致孔径生长曲线也不同，为此本程序对每个门分别进行校正。以 Bok望远镜为例，探测器阵列一共由16个门进行读出，图 14是一组典型的生长曲线。每个区域表示对应门，绿色标记表示符合条件的亮星在不同测光孔径的星等，红色曲线为采用的改正曲线。

![](images/f74db340604100dd82eb7bc901c40cb3e703c200e2919ac6384ac9d313fdfe50.jpg)  
图14用亮星得到的每个门的孔径生长曲线  
Fig.14 The growth curves of brightest stars in each amplifier

根据Bok望远镜在2017年9月共15个观测夜的观测数据，对视宁度、测光零点、天光背景亮度等信息进行了统计分析。

# 6.1视宁度（seeing）

根据 SE给出的图像中孤立的亮星的半高全宽（fullwidth at half maximum,FWHM）作为依据进行统计分析基特峰观测站的视宁度条件，约为 $1 " . 5 { \pm } 1 " . 0$ 。考虑到望远镜和相机本身对星像的展宽，这个数值略高于站点的真实视宁度。图15展示了上述观测图像的视宁度分布。

![](images/d4f9983167a7ed31a26b1eb7ed9f4e7f3e5c5a1ba022dba925a3a6291e796f92.jpg)  
图152017年9月Bok望远镜观测图像视宁度分布Fig.15 The distribution of seeing at Bok telescope in Sep，2017

# 6.2测光零点

测光改正零点是仪器星等和视星等之间的改正常数，反映了观测时的大气等因素对流量的影响。在进行流量定标时，为了避免不同曝光时间带来的影响，所有图像被归一化到一秒曝光的流量。图16是2017年9月观测数据的测光零点的分布，其中 $\mathrm { \ u _ { \mathrm { S C } } }$ 波段1612 幅图像，VsAGE波段1465 幅。

![](images/6d3cfb414cc7533502aaa17ae270e71018f596b24053b7db8165198ff5c98b91.jpg)  
图16 测光零点分布 Fig.16 The distribution of zeropoint

# 6.3天光背景亮度

天光背景是影响观测质量，尤其是极限星等的重要因素。图17展示了usc和 VsAGE 波段的天光背景分布。由于对夜天光的流量使用恒星的测光零点进行定标，而恒星的测光零点还受观测时大气质量的影响，所以定标得到的夜天光流量与实际略有不同。相比基特峰之前的天光背景监测[19]，亮度基本相似。

![](images/e6385d73f9f3463fcaa1c148b5f9091e58dbed1c97789844211467e35918f4da.jpg)  
图17夜天光背景亮度分布 Fig.17 The distribution of night sky brightness

# 7总结和展望

本文介绍 SAGE 测光巡天的数据处理过程和处理程序原理，并对数据处理精度进行了分析。本数据处理程序可以对不同望远镜取得的数据进行统一的处理，并且得到足够精度的数据。目前本数据处理程序主要针对单次曝光图像进行处理，多次观测图像堆叠、相互校正等等，还需要后续继续完善。

SAGE 测光系统，是一个自主设计的对恒星大气参数非常敏感的系统。SAGE 测光巡天自2015年开始利用3台望远镜协作完成约5亿颗恒星的8种颜色的观测。通过测光数据，还将得到高空间分辨率的可靠的星际消光分布。本巡天项目对恒星物理、银河系结构和演化等研究将是非常宝贵的观测遗产，同时也将河外天体的研究提供大量的观测数据。

# 致谢

感谢中国科学院新疆天文台马路正高级工程师、艾力·伊沙木丁研究员、刘进忠副研究员等的大力支持与配合，感谢一米大视场天文望远镜观测助手白春海、冯国杰、牛虎彪、张轩、许竞、王勇、马树国、蒲广新、阿布都等的辛勤工作。在观测以及数据处理过程中，还得到了中国科学院国家天文台蒋兆基研究员、葛亮博士、北京师范大学苑海波博士等人的帮助，在此一并表示感谢。

# 参考文献

[1］范舟，赵刚，王炜，等．SAGE 测光系统介绍［J]．天文学进展，（已投稿）．

Z. Fan,G. Zhao，W. Wang，and et al. The Introduction of SAGE Survey - The Photometric System [J]. Progress of Astronomy， submitted.   
[2] Wang W， Zhao G, Chen Y Q，et al． Stromgren-Crawford uvbyβ all sky survey - towards understanding of the Galaxy [C]//Proceedings IAU Symposium. 2013:326-330.   
[3］张阿丽，张晋，程宗颐．乌鲁木齐天文站南山GPS 跟踪站的地心坐标精确测定［J]．中国科学院上海 天文台年刊，2003(24):34-38. Zhang Ali， Zhang Jin， Cheng Zongyi. The precise determination of the geocentric coordinates of the Nanshan GPS tracking station of Urumqi Astronomical Station [J]. Annual Journal of Shanghai Astronomical Observatory， 2003(24) :34-38.   
[4]葛亮，王金虎，卢晓猛．1.26 米红外望远镜电控系统软件设计与实现［J]．天文研究与技术，2015, 12(3) :317-322. Ge Liang， Wang Jinhu, Lu Xiaomeng. Design and implementation of software for operations of the servo system of the 1.26m infrared telescope of the NAO[J]. Astronomical Research & Technology，2015， 12(3):317-322.   
[5]Ulugh Beg Astronomical Institute. Maidanak astronomical observatory. http://www.maidanak.uz， 2018.   
[6] Zou H, Zhang T M, Zhou Z M,et al. The first data release of the Beijing-Arizona Sky Survey [J]． The Astronomical Journal，2017，153:276(14pp).   
[7] Bertin E.Automatic astrometric andphotometric calibration with SCAMP[C]// Astronomical Data Analysis Software and Systems XV ASP Conference Series. 2006.   
[8] Röser S， Schilbach E， Schwan H,et al. PPM-Extended (PPMX） - a catalogue of positions and proper motions [J]. Astronomy and Astrophysics， 2008， 488(1) :401- 408.   
[9] Roeser S， Demleitner M, Schilbach E. The PPMXL catalog of positions and proper motions onthe ICRS. combining USNO-B1.0 and the Two Micron All Sky Survey （2MASS） ［J]． The Astronomical Journal， 2010，139(6) :2440-2447.   
[10]Shupe D L， Moshir M, Li J，et al. The SIP convention for representing distortion in FITS image headers [C]// Astronomical Data Analysis Software and Systems XIV ASP Conference Series. 2005.   
[11]Henden A A， Levine S, Terrell D,et al． APASS - the latest data release [C]//American Astronomical Society Meeting. 2015.   
[12]K. C. Chambers and et al. The Pan-STARRS1 Surveys [J]． ArXiv， 2016.   
[13]Bohlin R C. Hubble Space Telescope CALSPEC flux standards: Sirius (and Vega）[J]． The Astronomical Journal， 2014，147(6) :127(9pp).   
[14]Heap S R， Lindler D. Revived STIS. II. properties of stars in the Next Generation Spectral Library [C]// American Astronomical Society Meeting. 2010.   
[15]Bertin E, Arnouts S. SExtractor: software for source extraction [J]. Astronomy and Astrophysics Supplement，1996,117:393- 404.   
[16]D. Tody. The IRAF Data Reduction and Analysis System [J]. Procspie，1986， 627:733.   
[17]温元斌，郑永刚，周凌云，等．IRAF 软件孔径测光参数与测光误差的研究［J]．昆明理工大学学报: 理工版，2007，51(3):44-47. Wen Yuanbin， Zheng Yonggang， Zhou Lingyun， et al. Research on aperture photometric parameters and photometric errors with IRAF ［J]. Journal of Kunming University of Science and Technology :Science and Technology， 2007， 51(3) :44 - 47.   
[18]曾开华，彭青玉．高精度恒星孔径测光注释［J]．天文研究与技术—国家天文台台刊，2010, 7(2) :124-131. Zeng Kaihua， Peng Qingyu. Notes on high precision aperture photometry of stars [J]. Astronomical Research & Technology—Publications of National Astronomical Observatories of China， 2010, 7(2) :124-131.   
[19]Pilachowski C A，Africano JL，Goodrich B D，et al． Sky brightness at the Kitt Peak National Observatory [J]. Publications of the Astronomical Society of the Pacific，1989, 101(642) : 707 - 712.

# Research on the Data Reduction of the SAGE Photometric Sky Survey

Zheng Jie 1.2, Zhao Gang 1.2, Wang Wei 1.3, Fan Zhou 1, Zhao Jingkun 1, Tan Kefeng 1 1Key LaboratoryofOpticalAstronomy,NationalAstronomicalObservatories,ChineseAcademyofiences,Beijg0l 2Schoolof Astronomy and Space Science,University ofChinese Academy of Sciences,Beijing l00049 3ChineseAcdeofeeoucterftroiCilttetroioltrocle Chinese Academy of Sciences,Beijing 100101

Abstract SAGE photometric system is a self-designed system, which can provide accurate stellar atmosphere parameters and extinction. The actual $1 0 0 \sigma$ depths of the single-epoch images are $u _ { S C } \sim 1 7 . 3$ and $\nu _ { S A G E } \sim 1 6 . 8$ (AB magnitude).We are performing a SAGE photometric sky survey of the northern sky，covering about 12.,000 squared degrees and over 5OO million stars.This willbe valuable data in research of the Milky Way.This paper introduces the research and development of the pipeline for the survey,particularly the data reduction procesof a single exposure.The procedures include bias and flat correction，astrometric calibration,photometry and flux calibration. This paper also introduces the main results and data quality produced by the pipeline.

Keyword Photometry; Survey;Photometric System; Pipeline