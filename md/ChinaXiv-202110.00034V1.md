# 基于GoogleEarthEngine的干旱区水资源承载现状精准核算以新疆生产建设兵团为例

李婧昕}²，许尔琪1，张红旗1（1.中国科学院地理科学与资源研究所,陆地表层格局与模拟重点实验室,北京100101;2.中国科学院大学，北京100049)

摘要：近年来，水资源利用超载导致新疆生产建设兵团(下称“兵团")生产生态问题频发，科学精准评估水资源承载现状能够为兵团社会经济发展和生态环境治理提供重要参考。兵团社会经济用水中绝大部分为灌溉用水，因此耕地面积数据精度显著影响水资源承载现状评价结果，然而现实中耕地面积统计数据存在一定偏差，增加了水资源承载现状评估的不确定性。基于此，通过引入Google Earth Engine(GEE)大数据平台和净耕地系数,精确修订耕地面积;并模拟常规灌溉、膜上灌溉和混合灌溉3种灌溉用水情景，构建三生用水核算体系，对兵团及各师水资源承载现状进行精准评估。结果表明：兵团耕地校正系数为1.27，说明兵团耕地面积有约 $2 7 \%$ 的偏差;在与实际用水相近的混合灌溉情景中，基于耕地面积统计数据的兵团总需水量为 $1 0 6 . 4 5 { \times } 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ，相对兵团总引水量尚有 $9 . 2 0 \%$ 余量；通过GEE校正耕地面积后，兵团总需水量为 $1 2 5 . 6 4 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，超载 $7 . 1 6 \%$ ，且13个师中仅四师和十师2个师用水量不超载，表明灌溉用水过度占用有限的水资源量、挤占大量生态用水，是导致兵团水资源超载和生产生态问题频发的关键。本研究实现了对兵团水资源承载现状的科学精准评估，能够为兵团水资源利用及优化配置、区域可持续发展提供参考。

关键词：水资源承载现状；精准核算；Google Earth Engine；新疆生产建设兵团；灌溉用水；超载程度文章编号：

水资源是干旱区社会经济发展和维护生态环境稳定的决定性资源和制约因素[1-3]。农业是新疆生产建设兵团(下称"兵团”)最大的需水部门，其用水占比超过总用水量的 $9 0 \% ^ { [ 4 ] }$ ,且绝大多数为种植业灌溉用水。随着耕地规模急剧扩张，兵团总引水量也从1990年的 $9 2 . 9 5 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 增加至2016年的$1 3 0 . 1 5 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ,增幅高达 $4 0 . 0 2 \%$ ，但仍有研究表明，增加的引水量低于同期由耕地规模扩张带来的灌溉需水增量[5],导致生态环境保护和农业可持续发展压力日趋增大[6-7]

在实际农业生产过程中，利用灌溉节水技术可以在一定程度上缩减缺水差额[8-9],但更多则是通过挤占生态用水来满足灌溉需求，由此也导致兵团辖区及其周边生态环境问题频发[6-7]。在非农垦区，水资源过度开发利用导致河流断流、尾闾湖泊干枯等现象时有发生[10-I],部分区域植被覆盖度显著降低[5]。在农垦区，高效节水技术的广泛应用导致农田排盐能力减弱[12]，作物根系周围板结，盐渍化现象严重[13-14],而主要依靠灌溉回归水和渠系渗漏水维持的农田防护林也出现不同程度的衰退[12.5]；新开垦耕地常以缩减荒漠-绿洲交错带为代价，造成大量团场耕地与沙漠毗邻，土地沙化问题日益严重5；另外，一些农垦区受到当地地表水缺乏等因素限制，只能依靠打新井、打深井的方式维持灌溉，导

# 干吴区地理

致个别地区地下水超载严重[15-18] O

由此可知，若要实现兵团社会经济和生态环境的可持续发展，必须基于科学精准的水资源承载现状评估，研判水资源超载程度，严格控制社会经济用水总量,保障足够的生态流量[12.19]。其中,对灌溉需水量的测算是重中之重[20]。但实际上，耕地面积的统计过程往往存在一些不确定因素[12.20],直接影响到水资源承载现状评估的精度。GoogleEarth En-gine (GEE)云计算平台能够免费获取海量中高分辨率影像，为研究区耕地精确解译提供了便利[2I-22]。本研究围绕灌溉用水这一核心要素，一方面，在样地精度评估的基础上，获取耕地解译数据和净耕地系数反演数据[23-24],对大范围耕地面积进行精确核算；另一方面，对用水的不同行业、不同地区进行差异化分项测算，构建兵团三生用水核算体系，以期对兵团水资源承载现状进行精准评估。

# 1研究区概况

新疆生产建设兵团（下称“兵团”)组建于1954年，承担着国家赋予的屯垦成边的职责[5]，下辖14个师，其中十一师为建工师,其余13个师为农业生产师。由于十一师用水量非常有限,故未纳入兵团总需水量核算范围。各师区位分布情况见表1。北疆地区灌溉节水水平较高且气候相对湿润，8个师以 $5 4 . 9 9 \%$ 的兵团总用水量支持了 $6 9 . 0 6 \%$ 的总耕地面积;南疆4个师主要沿塔里木盆地边缘分布，并以$4 2 . 2 1 \%$ 的兵团总用水量支持了 $2 8 . 8 6 \%$ 的总耕地面积；东疆仅有十三师分布，用水总量和耕地面积占兵团比例分别为 $2 . 8 0 \%$ 和 $2 . 0 7 \%$ 。

# 表1新疆生产建设兵团各师所在区位分布情况统计

Tab.1 Spatial locations of each division of Xinjiang   

<html><body><table><tr><td colspan="2">Production and Construction Corps</td></tr><tr><td>分布</td><td>师名</td></tr><tr><td>北疆</td><td>四师、五师、六师、七师、八师、九师、十师、十二师</td></tr><tr><td>南疆</td><td>一师、二师、三师、十四师</td></tr><tr><td>东疆</td><td>十三师</td></tr></table></body></html>

注：分布在多个地区的师，以主体区位判断。

# 2数据与方法

# 2.1数据来源

兵团及各师水资源总量和供水量数据通过查找兵团统计年鉴、地方水资源公报、政府公报获得，由于目前2018年各师供水量数据并未发布，而近10a来兵团引水量基本稳定在 $1 2 0 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 上下，故本研究中以2017年各师供水量为基准，对2018年兵团及各师水资源承载现状进行评估。此外，兵团及各师总耕地面积、总播种面积、主要作物种植规模、人口、工业增加值等数据均由《兵团年鉴》和《新疆生产建设兵团统计年鉴》获取。

# 2.2兵团水资源承载现状分析

考虑到兵团各师、各团场相对分散的分布在新疆维吾尔自治区内，辖区河道内生态用水量难以计量，故本文中仅考虑用于城镇绿化等所需的河道外生态用水。在此背景下，本文中水资源承载现状是指，当前社会经济发展水平下，理论上社会经济和生态需水量相对于实际供水量的超载程度。计算公式如下：

$$
C = \frac { D - S } { S }
$$

式中： $C$ 为水资源承载现状 $( 1 0 ^ { 8 } \mathrm { m } ^ { 3 } ) ; D$ 为研究区理论需水量 $( 1 0 ^ { 8 } \mathrm { m } ^ { 3 } ) ; S$ 为实际供水量( $( 1 0 ^ { 8 } \mathrm { m } ^ { 3 } )$ 。当 $C <$ 0,区域水资源利用不超载， $C$ 的绝对值代表当前水资源利用率； $C > 0$ ，区域水资源利用超载，承载现状代表当前水资源利用超载程度， $C$ 越大，表明超载程度越严重。参考《全国水资源承载能力监测预警技术大纲(修改稿)》中水量承载状况判别规则，制定水资源承载现状判断标准为：当 $C < - 0 . 1$ 时，区域水资源利用不超载；当- $- 0 . 1 < \mathrm { C } \leqslant 0$ 时，区域水资源利用处于临界状态；当 $C > 0$ 时，水资源利用超载。将 $0 . 1 <$ $C { \lesssim } 0 . 2 , 0 . 2 { < } C { \leqslant } 0 . 5$ 和 $C > 0 . 5$ ，分别设定为水资源利用一般超载、中度超载和严重超载3个水平。

# 2.3基于GEE大数据平台的作物播种面积校正

为了提高承载现状评估结果的准确性，本研究通过GEE云计算平台提供的海量中分辨率影像对各师辖区内的耕地进行提取，并基于GoogleEarth选取高分辨率影像样区，初步计算耕地面积;再通过样地选取，得到耕地中除去田埂等非灌溉面积占比的净耕地系数，实现对研究区需灌溉的净耕地面积的精准测算。

首先，筛选GEE数据库中2018年覆盖兵团辖区并经过大气校正的全部Landsat-8影像，将所选影像的每个波段、每个像元取中值进行合成，生成无云影像集合，并利用随机森林(RF)分类器进行解译。

将合成后的Landsat-8影像的各个波段作为RF分类器的输入参数，设置参数treenumber为100,采样范围设置为 $3 0 ~ \mathrm { m } { \times } 3 0 ~ \mathrm { m }$ ，并覆盖兵团无云影像集合进行耕地和非耕地解译。在GoogleEarth随机选取各1000个耕地和非耕地高清数据作为训练样本，并抽取了844个耕地样本数据作为验证点，解译总体精度为 $9 5 . 3 8 \%$ ，精度较高，可以满足后续分析。

本研究中以师为单位，依据兵团耕地规模确定样方数,并计算净耕地系数。其中，一师、六师和八师为40个样方，十二、十三和十四师为20个，其余师为30个，共计390个样方，样方面积设置为300$\mathrm { m } { \times } 3 0 0 \mathrm { m }$ 。基于GoogleEarth高分辨率影像,提取并统计各个样地的总面积和该样方非耕地的总面积，计算样地的净耕地系数，以此实现对各师耕地面积的校正，并进一步校正作物播种面积如下：

$$
{ S _ { n i } } ^ { \prime } = S _ { n i } \times \frac { A _ { i } ^ { \prime } \times I _ { i } } { A _ { i } } = S _ { n i } \times T _ { i }
$$

式中： ${ { S _ { n i } } ^ { \prime } }$ 代表校正后第 $i$ 师第 $n$ 种作物的播种面积$( \mathrm { h m } ^ { 2 }$ ； $S _ { n i }$ 代表校正前第 $i$ 师第 $n$ 种作物的播种面积$\left( \mathrm { h m } ^ { 2 } \right)$ ） ${ A _ { i } } ^ { \prime }$ 为遥感解译得到的第 $i$ 师耕地面积( $\left( \mathrm { h m } ^ { 2 } \right)$ ：$I _ { i }$ 为第 $i$ 师净耕地系数； $A _ { i }$ 为统计数据中第 $i$ 师耕地面积 $( \mathrm { h m } ^ { 2 } ) ; T _ { i }$ 为耕地校正系数。

# 2.4兵团需水量计算

2.4.1 兵团总需水量及各项需水量计算兵团实际需水量包括经济社会需水量和生态需水量2个部分，其中，经济社会需水量包括生活需水量和生产需水量，生态需水量在本文中仅包括河道外生态需水量,具体计算公式如下[25]：

$$
W { = } W _ { \mathrm { s } } + W _ { \mathrm { p } } + W _ { \mathrm { E } }
$$

式中： $W$ 表示总需水量 $( 1 0 ^ { 8 } \mathrm { m } ^ { 3 } ) ; W _ { \mathrm { s } } , W _ { \mathrm { P } }$ 和 $W _ { \mathrm { E } }$ 分别表示生活、生产和生态需水量( $\left( 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \right)$ 。生产和生态需水量的分项计算公式如下：

$$
W _ { \mathrm { p } } = W _ { \mathrm { N A } } + W _ { \mathrm { A } }
$$

$$
W _ { \mathrm { { N A } } } = W _ { \mathrm { { c } } } + W _ { \mathrm { { G } } }
$$

$$
W _ { \mathrm { { A } } } = W _ { \mathrm { { z } } } + W _ { \mathrm { { L } } } + W _ { \mathrm { { D } } }
$$

$$
W _ { \mathrm { { E } } } = W _ { \mathrm { { R 0 } } }
$$

式中： $W _ { \mathrm { N A } }$ 和 ${ \mathbb { W } } _ { \mathrm { A } }$ 分别表示非农业生产需水量和农业生产需水量 $( 1 0 ^ { 8 } \mathrm m ^ { 3 } )$ ; $W _ { \mathrm { c } }$ 和 $W _ { \mathrm { G } }$ 分别表示城镇公共需水量和工业需水量 $( 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } ) ; W _ { \mathrm { z } } , W _ { \mathrm { L } \setminus W _ { \mathrm { D } } }$ 分别表示种植业需水量、牲畜需水量和林草地灌溉需水量( $1 0 ^ { 8 }$ $\mathbf { m } ^ { 3 }$ ； $W _ { \mathrm { { R 0 } } }$ 表示河道外生态需水量( $( 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } )$ 。兵团总需水量及各部门需水量为各师对应需水量之和。

2.4.2种植业需水量计算种植业需水量依据作物灌溉定额及经GEE精确校正后的播种面积进行测算。根据中国工程院25对新疆水资源供需情况的调查研究，在估算兵团总需水量时对北疆、南疆和东疆各师各项用水定额实行差异化计算；同时作物灌溉定额根据《新疆维吾尔自治区地方标准一一农业灌溉用水定额(DB65/3611—2014)》（下称《标准》)和项目组实地考察情况，共设定了3个情景(表2)：

(1) $7 5 \%$ 常规灌溉情景(“常规"情景)：参与计算的作物按照《标准》中 $7 5 \%$ 灌溉保证率的常规灌溉定额数值计算，由于灌溉节水技术的发展，该情景会对部分作物需水量产生一定程度高估，可认为是种植业需水量的上限值，即高需水情景。

（2) $7 5 \%$ 膜上灌情景（“膜上"情景）：按照《标准》中 $7 5 \%$ 灌溉保证率的膜上灌定额数值计算，对于一些较少应用节水技术进行灌溉的作物，该情景会对作物需水量产生一定程度低估，可认为是种植业需水量的下限值，即低需水情景

(3）混合灌溉情景（“混合"情景）：综合了《标准》中不同灌溉定额标准和实地考察情况，针对不同作物实际主要灌溉模式，分别设置相应的灌溉定额。根据实地调研，棉花在种植过程中广泛采用了较高水平的节水灌溉技术，因此将 $7 5 \%$ 灌溉保证率的膜上灌溉定额量作为棉花的需水量；对于小麦，玉米和水稻等粮食作物， $7 5 \%$ 灌溉保证率的常规灌溉量相对实际灌溉量普遍偏低，故最终的灌溉定额是在 $7 5 \%$ 常规灌溉定额基础上增加了 $5 0 \%$ 和 $7 5 \%$ 常规灌溉定额的差值部分，使其更接近实际灌溉量；其他作物采用 $7 5 \%$ 灌溉保证率的常规灌溉定额进行计算。

由于南疆地区土壤盐碱含量普遍较高，每年必须在种植前对耕地、园地等进行一次灌溉压盐[12.26-28]。考虑到兵团种植业生产节水技术水平较高[5],根据实际调研情况,将灌溉压盐定额统一设置为 $1 9 5 0 \mathrm { m } ^ { 3 } { \cdot } \mathrm { h m } ^ { - 2 }$ ，压盐灌溉所需水量分别计入耕地及园地种植需水量中。最终，种植业需水量计算方法为：

$$
\mathrm { W Z } _ { i } ( r ) = \left\{ \sum _ { n } \left[ Q _ { { \scriptscriptstyle n i } } \times S _ { { \scriptscriptstyle n i } } ( r ) \right] + 1 3 0 \times \left[ s ( i ) \times A _ { { \scriptscriptstyle n i } } ( r ) \right] \right\} \times 1 0 ^ { - 8 }
$$

式中： $n$ 为该师主要作物类型; $\mathbb { W } Z _ { i } ( r ) \operatorname { , } S _ { n i } ( r )$ 和 $A _ { n i } ( r )$ 为条件 $r$ 的函数，当计算校正前第 $i$ 师种植业需水量

# 干辛区地理

表2兵团主要作物"常规”、“膜上"和"混合"情景灌溉定额统计  
Tab.2 Statistics of main crops irigation norm of conventional,above mulch and mixed irrigation scenarios in Xinjiang Production and Construction Corps   

<html><body><table><tr><td rowspan="2">作物</td><td colspan="3">北疆</td><td colspan="3">南疆</td><td colspan="3">东疆</td></tr><tr><td>常规灌溉</td><td>膜上灌溉</td><td>混合灌溉</td><td>常规灌溉</td><td>膜上灌溉</td><td>混合灌溉</td><td>常规灌溉</td><td>膜上灌溉</td><td>混合灌溉</td></tr><tr><td>小麦</td><td>4725</td><td>3660</td><td>5160</td><td>5115</td><td>3945</td><td>5580</td><td>5220</td><td>4050</td><td>5700</td></tr><tr><td>玉米</td><td>4800</td><td>3720</td><td>5235</td><td>5310</td><td>4110</td><td>5805</td><td>6480</td><td>5025</td><td>7050</td></tr><tr><td>水稻</td><td>12405</td><td>9420</td><td>13530</td><td>13980</td><td>10800</td><td>15255</td><td>1</td><td>1</td><td>1</td></tr><tr><td>薯类</td><td>4725</td><td>4035</td><td>4725</td><td>5265</td><td>4500</td><td>5265</td><td>5400</td><td>4650</td><td>5400</td></tr><tr><td>油菜</td><td>4815</td><td>3915</td><td>4815</td><td>5325</td><td>4095</td><td>5325</td><td>5175</td><td>4050</td><td>5175</td></tr><tr><td>葵花</td><td>4845</td><td>3855</td><td>4845</td><td>5565</td><td>4260</td><td>5565</td><td>5775</td><td>4470</td><td>5775</td></tr><tr><td>豆类</td><td>4260</td><td>3285</td><td>4260</td><td>5070</td><td>3900</td><td>5070</td><td>5445</td><td>4230</td><td>5445</td></tr><tr><td>棉花</td><td>5835</td><td>4515</td><td>4515</td><td>6600</td><td>5625</td><td>5625</td><td>7650</td><td>5895</td><td>5895</td></tr><tr><td>甜菜</td><td>5325</td><td>4125</td><td>5325</td><td>5715</td><td>4425</td><td>5715</td><td>1</td><td>1</td><td>1</td></tr><tr><td>苜蓿</td><td>4575</td><td>3540</td><td>4575</td><td>5115</td><td>3975</td><td>5115</td><td>5295</td><td>4125</td><td>5295</td></tr><tr><td>蔬菜</td><td>5520</td><td>4260</td><td>5520</td><td>6435</td><td>4950</td><td>6435</td><td>6255</td><td>4845</td><td>6255</td></tr><tr><td>葡萄</td><td>5970</td><td>4620</td><td>5970</td><td>6510</td><td>5025</td><td>6510</td><td>9225</td><td>7170</td><td>9225</td></tr><tr><td>瓜类</td><td>4695</td><td>3615</td><td>4695</td><td>5370</td><td>4170</td><td>5370</td><td>5580</td><td>4305</td><td>5580</td></tr><tr><td>果树</td><td>6195</td><td>4980</td><td>6195</td><td>7275</td><td>5640</td><td>7275</td><td>8295</td><td>6375</td><td>8295</td></tr></table></body></html>

注：“-"表示该区域无此类作物种植。

WZi时， $r { = } 1 \ , S _ { n i } ( r ) { = } S _ { n i } , A _ { n i } ( r ) { = } A _ { n i }$ ；当计算校正后第 $i$ 师需水量 $\mathrm { W } { \mathbf { Z } _ { i } } ^ { \prime }$ 时， $r { = } 2 , S _ { n i } ( r ) { = } S _ { n i } ^ { \prime }$ ， $A _ { n i } ( r ) { = } A _ { n i } ^ { \phantom { * } }$ $Q _ { n i }$ 代表第i师第 $n$ 种作物灌溉定额 $\left( \mathrm { m } ^ { 3 } \cdot \mathrm { h m } ^ { - 2 } \right) .$ ; $s ( i )$ 为判别函数，若 $i$ 师位于南疆地区，即一师、二师、三师和十四师，则 $s ( i ) \mathrm { = } 1$ ,否则 $s ( i ) { = } 0 ; C$ 为第 $i$ 师耕地面积 $\left( \mathrm { h m } ^ { 2 } \right)$ ）

2.4.3非种植业需水量计算非种植业需水包括生活需水，生产需水中的城镇公共需水、工业需水和农业需水（林草地灌溉需水和牲畜需水），生态需水中的河道内及河道外生态需水[25],具体计算过程见表3。

# 3结果与分析

# 3.1耕地校正系数及种植规模分析

13个师解译校正前后的播种面积和耕地校正系数如图1所示。总体上看，兵团耕地校正系数为1.27，表明兵团总体有约 $2 7 \%$ 的耕地未纳入统计。从师级看，13个农业生产师中五师耕地校正系数高达1.48,六师耕地校正系数最低，仅为1.11。从地域看，北疆8个师、南疆4个师和东疆1个师平均耕地校正系数分别为1.26、1.28和1.31，虽然东疆校正系数最高，但这一区域内仅有十三师，从师级来看该师校正系数位列第四位；北疆总体校正系数最低，但系数最高和最低的师均位于北疆，虽然八师耕地校正系数1.24低于兵团平均水平，但由于该师耕地规模远高于其他师，超过 $3 0 { \times } 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ ,故其校正后种植规模仍为最大值;南疆十四师耕地面积校正后为$1 . 4 0 { \times } 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ ,为各师最小值。根据地域统计,北疆8个师、南疆4个师和东疆1个师播种总面积分别为$1 1 0 . 7 6 \mathrm { ~ h m } ^ { 2 } \cdot 4 6 . 8 5 { \times } 1 0 ^ { 4 } \mathrm { ~ h m } ^ { 2 }$ 和 $3 . 4 6 \times 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ ，分别占兵团总播种面积的 $6 8 . 7 6 \% . 2 9 . 0 9 \%$ 和 $2 . 1 5 \%$ 。

# 3.2兵团需水量分析

基于耕地统计数据，“常规”“膜上"和"混合"3种灌溉情景兵团总需水量分别为 $1 1 5 . 8 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ）$9 6 . 5 3 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 和 $1 0 6 . 4 5 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ,各师存在显著差异(图2)。相比于 $1 1 7 . 2 4 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 的兵团实际工程供水总量，3种情景耗水均未超载，但“常规"和"混合"灌溉情景已处于需水临界状态，余量分别为 $1 . 1 7 \%$ 和$9 . 2 0 \%$ 。兵团农业用水占比极高，“常规”、“膜上"和“混合"3种灌溉情景的农业需水量占总需水量比例分别为 $9 5 . 6 8 \% . 9 4 . 9 8 \%$ 和 $9 5 . 3 0 \%$ ，表明农业生产规模决定了各师需水量的大小。

基于遥感耕地校正数据，“常规”、“膜上"和"混合"3种灌溉情景下，兵团总需水量分别为 $1 3 7 . 6 5 \times$ $1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } , 1 1 4 . 2 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } , 1 2 5 . 6 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ，比统计数据计算所得兵团总需水量高约 $2 0 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 。只有“膜上”灌溉情景的需水量未超过兵团实际 $1 1 7 . 2 5 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 的供水量，“常规"和"混合"情景总需水量均超出实际供水量。

表3兵团各项需水(除种植业外)计算方法及说明  
Tab.3 Calculation method andillustration of each water requirement (except planting irrigation water requirement) of Xinjiang Production and Construction Corps   

<html><body><table><tr><td>非种植业需水需水项</td><td></td><td>计算方法</td><td>灌溉定额参考来源</td></tr><tr><td>生活需水</td><td>城镇居WS=QS×P×365/10"</td><td>民生活式中:WS.代表第i师生产需水量(10"m);QS为第i师人 区水资源公报,将北疆、南疆和东疆(下文分别以N、S和E 需水均生产用水定额[L·(d·人)];Pi为第i师人口数量(人)。表示)人均生活用水定额分别设定为155L·d'、130L·d</td><td>结合中国工程院对新疆水资源供需情况调研分析[25和地 和140L·d'，各师人员均按照城镇居民计。</td></tr><tr><td>生产需水</td><td>农业-林WD=QD×AD×R/10 畜需水 农业-牲v</td><td>草地灌式中:WDi代表第i师林地/草地灌溉需水量(10m);QDi、草地综合灌溉定额分别为4950m·hm(N）、7050 m· 溉需水AD:为第i师林地/草地灌溉定额(m·hm2)和灌溉面积 hm2(S)和6000m·hm2(E);将3个地区林草地灌溉用水 需水与草地灌溉需水之和为林草地灌溉总需水。 WL=∑(Qq×M)+∑(Qu×M)×365/10" 式中:WL为第i师牲畜需水量(10"m);Qu和Qu分别为 50L·(d·头)(E);小牲畜需水量均为10L·(d·头)。 第i师大牲畜(牛、马和驴)和小牲畜(羊和猪)需水定额</td><td>根据中国工程院已有研究2和项目组实地考察结果，林 (hm);Ri为第i师林地/草地灌溉面积比例,最终林地灌溉总量分别与林草地总面积作比可知,灌溉的林草地面积 占总林草地面积平均比例分别约为8%、4%和4%。 根据中国量程院有研·d和）目实地调d研结果，大</td></tr><tr><td></td><td>工业 需水</td><td>[L·(d·头)-];Ma和Mbi分别为第i师大牲畜和小牲畜数量 (头）。 WG=IAV×IG ×(1-D)=IAV×QGi 元工业增加值用水量降幅(%);QCi为当前年份万元工(E),由此可得万元工业增加值用水量分别为39.43×10</td><td>根据《新疆生产建设兵团年鉴》和《兵团年鉴》中可获取 式中：WG:代表第i师工业需水量(10"m);IAVi为第i师 的数据,2017年各师工业用水量平均值分别为0.08×10 当年工业增加值(10元);IG和D:分别为前一年份万元m(N)、0.22×10"m(S)和0.24×10m(E),工业增加值分 工业增加值用水量[10m·(10元)-]和近10a来平均万别为18.00×10元(N）、30.80×10"元(S)和55.90×10元</td></tr><tr><td>生态需水</td><td>城镇公WC=QC×P×365/10"</td><td>业增加值用水量[10m·(10元)]。 共需水式中:WC代表第i师生产需水量(10m);QCi为第i师人 共用水定额分别为19L·d'(N)、18L·d'(S)和23L·d 均生产用水定额[L·(d·人)];Pi为第i师人口数量(人)。 河道外 WRO=QE;×P:×365/10"</td><td>m·(10元)-'(N)、71.43×10m·(10元)-1(S)和42.84×10 m·(10元)-(E)。 根据已有研究结论2并结合兵团实际情况，人均城镇公 (E)。 结合已有研究25和课题组实地考察结果，城镇人均生态</td></tr></table></body></html>

![](images/ac938886a6398bc8d1a4d38c66012acb18353a87aa73481a081bbeb4c0baaae4.jpg)  
图1校正前后兵团各师耕地面积、播种面积及耕地校正系数 Fig.1Cultivated land area,sown area,and the cultivated area correction coefficients of each division before and after correction in XinjiangProduction and Construction Corps

3种灌溉情景下(图2)，一师的总需水量均为最高值，八师次之；十二师为最低值,九师、十师、十三师和十四师的需水也相对较低。对于混合灌溉情景，由于粮食作物(水稻、小麦和玉米）、棉花和其他作物的灌溉定额不同，各师总需水量还受种植结构的影响。多数师粮食种植规模小于棉花规模，故粮食需水量的增加被棉花需水量的减少所抵消，仅有四师和九师在"混合"灌溉情景的需水量略大于“常规"情景，其余师"混合"灌溉情景均为中需水量。

“混合"情景下各师需水分项基本以种植业为主(表4)。九师是兵团唯一没有棉花种植的师，故“混合”情景需水量 $4 . 5 4 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 高于“常规”情景$4 . 4 2 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 的需水量。另外，四师的水稻、小麦和玉

# 干旱区地理

![](images/d990679ca4a1280948134a47f9bce31d1b4e10bd79f43d503f702364c173cd6d.jpg)  
图2基于校正耕地数据的新疆生产建设兵团"常规” “膜上"和"混合"灌溉情景总需水量对比 Fig.2 Total water requirement comparison of conventional, above mulch and mixed irrigation scenarios based on the corrected cultivated land area data of Xinjiang Production and Construction Corps

来等粮食作物播种面积为各师最高，占主要种植作物面积的 $5 2 . 5 1 \%$ ，而棉花播种面积占比仅为$9 . 6 1 \%$ ，使得该情景下总需水量达到 $9 . 9 9 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 比 $7 5 \%$ 常规灌溉情景 $9 . 7 6 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 的需水量还高出$0 . 2 3 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。

各师中，虽然十二师总需水量为兵团最低值，仅为 $2 . 2 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，但该师农业需水占比为各师最低的 $8 4 . 9 2 \%$ ,其他产业及生活生态用水相对较高，生活需水、工业需水、城镇公共需水和河道外生态需水4项分别以 $3 . 3 2 \% \ 、 1 1 . 0 6 \% \ 、 0 . 4 1 \% \ 、 0 . 3 0 \%$ 的比重位列全师第一位，说明十二师工业化水平相对较高。与之相比，南疆十四师总需水量 $2 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,其需水规模与十二师最为接近,但农业用水占比为各师最高值 $9 8 . 0 6 \%$ ，导致除农业用水外几乎无水可用，其中工业用水占比仅为 $0 . 2 7 \%$ ,为各师最低值，表明其工业发展规模较小。

# 3.3兵团需水超载程度分析

3.3.1基于统计数据的水资源承载现状以统计数据计算的混合灌溉情景为依据，分析各师水资源承载现状(表5)。兵团总供水量为 $1 1 7 . 2 5 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ，混合灌溉情景总需水量为 $1 0 6 . 4 5 { \times } 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ,需水量并未超载。该情景下共计6个师不超载，2个师处于临界状态，其他5个师则出现不同程度超载，其中，八师水资源超载量最高，达 $1 . 9 8 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,而九师超载状态程度最高；四师和十师的水资源富余量较高，分别达到 $4 . 7 9 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 和 $4 . 3 6 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。

从区域看，南疆二师、三师不超载，一师、十四师一般超载，超载程度为 $4 . 7 0 \%$ 和 $3 . 2 5 \%$ ;东疆十三师属中度超载，超载程度为 $2 7 . 3 4 \%$ ;处于严重超载的九师和超载水量最多的八师均位于北疆，另外，北疆五师和十二师供水盈余为 $9 . 1 9 \%$ 和 $4 . 9 1 \%$ ,处于需水量临界状态;四师、五师、六师、七师和十师水资源有较大富余，四师和十师富余比率高达 $3 7 . 4 0 \%$ 和 $6 3 . 4 7 \%$ 。

表4基于校正耕地数据的新疆生产建设兵团混合灌溉情景需水量  
Tab.4Water requirement of mixed irrigation scenario based on the corrected cultivated land area of Xinjiang production and Construction Corps   
$/ 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$   

<html><body><table><tr><td rowspan="2">师名</td><td rowspan="2">农业需水 合计</td><td colspan="3">农业需水类别</td><td rowspan="2">生活 需水</td><td rowspan="2">工业 需水</td><td rowspan="2">城镇公共 需水</td><td rowspan="2">河道外 生态需水</td><td rowspan="2">总需 水量</td></tr><tr><td>农作物</td><td>牲畜</td><td>林草地</td></tr><tr><td>一师</td><td>27.89</td><td>27.77</td><td>0.10</td><td>0.02</td><td>0.18</td><td>0.43</td><td>0.03</td><td>0.02</td><td>28.54</td></tr><tr><td>二师</td><td>10.34</td><td>9.78</td><td>0.54</td><td>0.02</td><td>0.11</td><td>0.24</td><td>0.02</td><td>0.01</td><td>10.71</td></tr><tr><td>三师</td><td>12.63</td><td>12.36</td><td>0.25</td><td>0.02</td><td>0.12</td><td>0.18</td><td>0.02</td><td>0.01</td><td>12.97</td></tr><tr><td>四师</td><td>9.53</td><td>8.65</td><td>0.83</td><td>0.05</td><td>0.14</td><td>0.29</td><td>0.02</td><td>0.01</td><td>9.99</td></tr><tr><td>五师</td><td>5.94</td><td>5.39</td><td>0.53</td><td>0.01</td><td>0.07</td><td>0.04</td><td>0.01</td><td>0.01</td><td>6.07</td></tr><tr><td>六师</td><td>11.03</td><td>9.79</td><td>1.20</td><td>0.04</td><td>0.21</td><td>0.40</td><td>0.03</td><td>0.02</td><td>11.68</td></tr><tr><td>七师</td><td>10.17</td><td>9.61</td><td>0.53</td><td>0.03</td><td>0.14</td><td>0.14</td><td>0.02</td><td>0.01</td><td>10.47</td></tr><tr><td>八师</td><td>17.23</td><td>16.92</td><td>0.27</td><td>0.05</td><td>0.37</td><td>0.63</td><td>0.05</td><td>0.03</td><td>18.32</td></tr><tr><td>九师</td><td>4.45</td><td>3.66</td><td>0.75</td><td>0.04</td><td>0.05</td><td>0.03</td><td>0.01</td><td>0.00</td><td>4.54</td></tr><tr><td>十师</td><td>2.88</td><td>2.67</td><td>0.20</td><td>0.02</td><td>0.06</td><td>0.09</td><td>0.01</td><td>0.01</td><td>3.04</td></tr><tr><td>十二师</td><td>1.93</td><td>1.01</td><td>0.91</td><td>0.01</td><td>0.08</td><td>0.25</td><td>0.01</td><td>0.01</td><td>2.27</td></tr><tr><td>十三师</td><td>4.15</td><td>3.04</td><td>1.10</td><td>0.01</td><td>0.06</td><td>0.30</td><td>0.01</td><td>0.00</td><td>4.53</td></tr><tr><td>十四师</td><td>2.46</td><td>2.21</td><td>0.24</td><td>0.01</td><td>0.03</td><td>0.01</td><td>0.01</td><td>0.00</td><td>2.50</td></tr><tr><td>合计</td><td>120.64</td><td>112.86</td><td>7.45</td><td>0.32</td><td>1.61</td><td>3.03</td><td>0.22</td><td>0.15</td><td>125.64</td></tr></table></body></html>

注：数据合计数由于单位或小数位取舍而产生的计算误差，均未作机械调整。

表5基于统计数据的新疆生产建设兵团混合灌溉情景水资源承载现状  
Tab.5 Water resources carrying capacity of mixed irrigation scenario based on statistics of Xinjiang Production and Construction Corps   

<html><body><table><tr><td>师名</td><td>总供水量/10m</td><td>总需水量/10m</td><td>超载程度/%</td><td>不超载</td><td>临界状态</td><td>一般超载</td><td>中度超载</td><td>严重超载</td></tr><tr><td>一师</td><td>23.08</td><td>24.16</td><td>4.70</td><td></td><td></td><td>√</td><td></td><td></td></tr><tr><td>二师</td><td>10.84</td><td>9.42</td><td>-13.10</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>三师</td><td>12.71</td><td>11.02</td><td>-13.26</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>四师</td><td>12.80</td><td>8.01</td><td>-37.40</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>五师</td><td>5.00</td><td>4.54</td><td>-9.19</td><td></td><td>√</td><td></td><td></td><td></td></tr><tr><td>六师</td><td>12.90</td><td>10.79</td><td>-16.34</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>七师</td><td>9.39</td><td>7.85</td><td>-16.45</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>八师</td><td>13.38</td><td>15.36</td><td>14.77</td><td></td><td></td><td>√</td><td></td><td></td></tr><tr><td>九师</td><td>2.33</td><td>3.99</td><td>70.87</td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>十师</td><td>6.86</td><td>2.50</td><td>-63.47</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>十二</td><td>2.31</td><td>2.20</td><td>-4.91</td><td></td><td>√</td><td></td><td></td><td></td></tr><tr><td>十三</td><td>3.25</td><td>4.14</td><td>27.34</td><td></td><td></td><td></td><td>√</td><td></td></tr><tr><td>十四</td><td>2.39</td><td>2.47</td><td>3.25</td><td></td><td></td><td>√</td><td></td><td></td></tr></table></body></html>

# 3.3.2基于遥感耕地校正数据的水资源承载现状

基于遥感校正耕地数据估算的混合灌溉情景总需水量为 $1 2 5 . 6 4 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ，超出实际可供水量$7 . 1 6 \%$ ，表明兵团水资源利用已经超载，且局部地区水资源供需矛盾更加突出(图3和表6)。仅四师和十师2个师的水资源不超载，二师、六师和十二师3个师处于水资源临界状态，其他师均存在不同程度超载情况，其中3个师处于一般超载状态，4个师中度超载,1个师严重超载。水资源超载的各师中，一

十四师 □超载量 十三师 A 总需水量 十二师 ZA 总供水量 十师 A 九师 ZZZA 八师 A   
名 七师 A   
师六师 五师 ZLZA 四师 三师 A 二师 ZA 一师 Z 1 -5 0 5 10 15 20 25 30 水量统计/10m

师超载最严重，高达 $5 . 4 6 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,主要是其农业生产规模过大和农业生产条件制约造成。八师超载量处于兵团第二位，这是由于其耕地规模高居兵团第一，尽管节水技术先进，但是规模过大，导致水资源超载严重，超载量达到了约 $4 . 9 4 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。从水资源超载程度上看，九师水资源超载程度仍为最高，随后为中度超载的十三师、八师、一师和五师。

# 4结论

本文利用GEE大数据平台，通过精确遥感解译，对兵团实际耕地面积及种植规模进行测度，同时，构建了完善的三生用水核算体系，实现了兵团三生用水的精准核算，为兵团水资源利用、优化配置及区域可持续发展提供参考。得出以下结论：

（1）兵团耕地校正系数为1.27，说明兵团总体有约 $2 7 \%$ 的耕地未纳人统计，各师校正系数则介于1.11\~1.48。由统计数据计算的 $7 5 \%$ 常规灌溉情景、$7 5 \%$ 膜上灌情景和混合灌溉3种情景兵团总需水量分别为 $1 1 5 . 8 7 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } . 9 6 . 5 3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ 和 $1 0 6 . 4 5 \times 1 0 ^ { 8 }$ $\mathbf { m } ^ { 3 }$ ,相比于 $1 1 7 . 2 4 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 的兵团实际工程供水总量，3种灌溉情景需水量均未达到超载;经遥感校正数据后，3种情景兵团总需水量分别为 $1 3 7 . 6 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ）$1 1 4 . 2 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } , 1 2 5 . 6 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ，仅 $7 5 \%$ 膜上灌溉情景未超载。

（2）对比耕地面积校正前后混合灌溉情景的兵团需水量可知，校正前兵团水资源并未超载，尚有$9 . 2 0 \%$ 余量，而校正后则显示兵团水资源总量超载

# 干旱区地理

表6基于校正耕地数据的新疆生产建设兵团混合灌溉情景水资源承载现状  
Tab.6Water resources carrying capacity of mixed irrigation scenario based on corrected cultivated land area of Xinjiang Production and Construction Corps   

<html><body><table><tr><td>师名</td><td>总供水量/10m</td><td>总需水量/10m</td><td>超载程度/%</td><td>不超载</td><td>临界状态</td><td>-般超载</td><td>中度超载</td><td>严重超载</td></tr><tr><td>一师</td><td>23.08</td><td>28.54</td><td>23.67</td><td></td><td></td><td></td><td>√</td><td></td></tr><tr><td>二师</td><td>10.84</td><td>10.71</td><td>-1.18</td><td></td><td>√</td><td></td><td></td><td></td></tr><tr><td>三师</td><td>12.71</td><td>12.97</td><td>2.01</td><td></td><td></td><td>√</td><td></td><td></td></tr><tr><td>四师</td><td>12.80</td><td>9.99</td><td>-21.92</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>五师</td><td>5.00</td><td>6.07</td><td>21.42</td><td></td><td></td><td></td><td>√</td><td></td></tr><tr><td>六师</td><td>12.90</td><td>11.68</td><td>-9.45</td><td></td><td>√</td><td></td><td></td><td></td></tr><tr><td>七师</td><td>9.39</td><td>10.47</td><td>11.55</td><td></td><td></td><td>√</td><td></td><td></td></tr><tr><td>八师</td><td>13.38</td><td>18.32</td><td>36.92</td><td></td><td></td><td></td><td>√</td><td></td></tr><tr><td>九师</td><td>2.33</td><td>4.54</td><td>94.60</td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>十师</td><td>6.86</td><td>3.04</td><td>-55.63</td><td>√</td><td></td><td></td><td></td><td></td></tr><tr><td>十二师</td><td>2.31</td><td>2.27</td><td>-1.96</td><td></td><td>√</td><td></td><td></td><td></td></tr><tr><td>十三师</td><td>3.25</td><td>4.53</td><td>39.18</td><td></td><td></td><td></td><td>√</td><td></td></tr><tr><td>十四师</td><td>2.39</td><td>2.50</td><td>4.70</td><td></td><td></td><td>√</td><td></td><td></td></tr></table></body></html>

$7 . 1 6 \%$ ，且13个师中仅有2个师需水量未超载，而已有研究发现的兵团耕地盐渍化、植被退化以及地表水断流、地下水水位下降等现象，是水资源超载的有力实证[5,12.20.25],由此可知,准确修正耕地面积是实现水资源承载现状精准评估的关键；而本文构建的完善的三生用水核算体系，丰富了用水细节及用水结构，成为水资源承载现状精准分析的重要因素[2.25]

(3）根据《新疆生产建设兵团统计年鉴》并结合本文计算结果可知，农业以 $9 6 . 0 1 \%$ 的经济用水占比仅产出了 $2 1 . 6 9 \%$ 的产值，而工业和服务业以 $2 . 9 5 \%$ 的经济用水产出了 $7 8 . 3 1 \%$ 的产值，仅仅依靠农业难以拉动兵团经济发展,必须坚持"以水定地”[12.20],在保障粮食安全的前提下,转变生产方式[29-30],保障新型工业化与城镇化用水。另外，兵团辖区内水资源分布与经济社会发展格局并不完全匹配，各地区各师超载原因有所不同，迫切需要加快流域水资源配置，加强精细管理,全面提高水资源承载能力[2,20,25,31]

# 参考文献(References)

[1] Tan M H, Zheng L Q. Increase in economic efficiency of water use caused by crop structure adjustment in arid areas[J]. Journal of Environmental Management,2019(230): 386-391.   
[2] Yang G,Li F D,Chen D,et al.Assessment of changes in oasis scale and water management in the arid Manas River Basin,north western China[J]. Science of the Total Environment,2O19(691): 506-515.   
[3] 黄会平,张岑.基于3S的干旱区土地利用/覆被变化及其对水 资源的影响分析——以张掖市甘州区为例[J].水土保持研究, 2009,16(4): 270-274.[Huang Huiping,Zhang Chen.LUCC and analysis of water resources effect in arid area: A case of Ganzhou District, Zhangye,Gansu Province[J].Research of Soil and Water Conservation,2009,16(4):270-274.]   
[4]邵双林,陈红艳.新疆生产建设兵团水资源利用情况及用水水 平评价[J].水利规划与设计,2010(3):38-39,49.[Shao Shuanglin,Chen Hongyan. Evaluation of water resources utilization and water use level of Xinjiang Productionand Construction Corps[J]. Water Conservancy Planning and Design,2010(3): 38-39,49.]   
[5]周宏飞,吴波,王玉刚,等.新疆生产建设兵团农垦生态建设的 成就、问题及对策刍议[J].中国科学院院刊,2017,32(1):55- 63.[Zhou Hongfei,Wu Bo,Wang Yugang,et al.Ecological achievement of Xinjiang Production and Construction Corps and its problems and countermeasures[J]. Bulletin of Chinese Academy of Sciences,2017,32(1): 55-63.]   
[6]程钢.石河子垦区农业开发与绿洲生态演变研究[D].石河子: 石河子大学,2013.[Cheng Gang.Agricultural development and oasis ecosystem evolution in Shihezi reclamation zone:Based on the analysis about the ecosystem service function[D]. Shihezi: Shihezi University,2013.]   
[7]封玲.石河子水资源利用方式对绿洲生态环境的影响[J].石河 子大学学报(哲学社会科学版),2005,19(2):9-12.[Feng Ling. Influence to oasis ecological environment owing to the way of water resources in Shihezi[J]. Journal of Shihezi University (Philosophy and Social Science Edition),2005,19(2): 9-12.]   
[8]Chen Z K,Niu YP,Zhao R H,et al. The combination of limited irrigation and high plant density optimizes canopy structure and improves the water use eficiency of cotton[J].Agriculture Water Manage,2019(218): 139-148.   
[9]Yang G, Tian L J,Li X L,et al. Numerical assessment of the effect of water-saving irrigation on the water cycle at the Manas River Basin oasis,China[J]. Science of the Total Environment,2020(707): 135587,doi: 10.1016/j.scitotenv.2019.135587.   
[10] 李年亮.新疆兵团第十三师水资源配置与优化模拟研究[D].西 安：西安理工大学,2019.[Li Nianliang.Water resources allocation and optimization simulation of Xinjiang Corps Thirteenth Division[D]. Xi'an: Xi'an University of Technology,2019.]   
[11] 张敏.新疆兵团高效节水灌溉发展中存在的问题与解决思路 [J].节水灌溉,2013(7):79-80.[Zhang Min. Preliminary analysis of existing problemsand solutions of water-saving irigation development in Xinjiang Construction Crops[J].Water Saving Irrigation,2013(7): 79-80.]   
[12] 中国工程院.“新疆水土资源可持续利用与生态文明建设"专题 报告与调研报告[R].北京:中国工程院,2014.[Chinese Academy of Engineering. Special report and research report on “Sustainable Utilization of Water and Soil Resources and Ecological Civilization Construction in Xinjiang"[R]. Beijing: Chinese Academy of Engineering, 2014.]   
[13] 李明思,刘洪光,郑旭荣.长期膜下滴灌农田土壤盐分时空变化 [J].农业工程学报,2012,28(22):82-87.[Li Mingsi,Liu Hongguang,Zheng Xurong.Spatiotemporal variation for soil salinity of field land under long-term mulched drip irrigation[J]. Transactions of the Chinese Society of Agricultural Engineering,2012,28(22): 82-87.]   
[14]王振华,杨培岭,郑旭荣,等.膜下滴灌系统不同应用年限棉田 根区盐分变化及适耕性[J].农业工程学报,2014,30(4):90-99. [Wang Zhenhua,Yang Peiling, Zheng Xurong,et al. Soil salinity changes of root zone and arable in cotton field with drip irrigation under mulch for diferent years[J]. Transactions of the Chinese Society of Agricultural Engineering,2014,30(4): 90-99.]   
[15] 李红山,李杰军,吴瑞,等.浅谈兵团农田防护林存在的问题及 对策[J].甘肃林业科技,2007,32(3):79-81.[Li Hongshan,Li Jiejun,Wu Rui,et al.Simple discussion on problems existed in forest for farm protection and countermeasures[J]. Journal of Gansu Forestry Science and Technology,2007,32(3): 79-81.]   
[16] 刘艳珍.兵团农八师地下水现状与对策[J].水利科技与经济, 2011(17):36-37,44.[Liu Yanzhen. Status quo and countermeasures of underground water of Agricultural Eighth Division[J]. Water Conservancy Science and Technology and Economy,2011(17): 36-37, 44.]   
[17] 王东,孟涛,王云智.新疆石河子市地下水超采现状分析及对策 [J].地下水,2007,29(2):78-80.[Wang Dong,Meng Tao,Wang Yunzhi. Status quo analysis and countermeasures of underground water overdraft in Shihezi City,Xinjiang[J].Ground Water,2007, 29(2): 78-80.]   
[18] 吴彬.石河子市地下水系统演化规律与水环境效应研究[D].乌 鲁木齐：新疆农业大学,2007.[Wu Bin.Study on groundwater system evolvement law and water environment effect of Shihezi City[D]. Urumqi: Xinjiang Agriculture University,2007.]   
[19] 王静,刘海隆,王玲.气候变化背景下玛纳斯河流域绿洲适宜规 模研究[J].干旱区地理,2019,42(1):113-120.[Wang Jing, Liu Hailong,Wang Ling. Suitable oasis scale in Manas River Basin in the context of climate change[J].Arid Land Geography,2019,42 (1): 113-120.]   
[20] 中国工程院.新疆可持续发展中有关水资源的战略研究[R].北 京：中国工程院,2012.[Chinese Academy of Engineering. Study of strategy on water resources in sustainable development of Xinjiang[R]. Beijing: Chinese Academy of Engineering,2012.]   
[21] Hu YF,Hu Y.Land cover changes and their driving mechanisms in Central Asia from 2001 to 2017 supported by Google Earth Engine[J]. Remote Sensing,2019,11(5): 554,doi: 10.3390/rs110505 54.   
[22] 胡云锋,商令杰,张千力,等.基于GEE平台的1990年以来北京 市土地变化格局及驱动机制分析[J].遥感技术与应用,2018, 33(4): 573-583.[Hu Yunfeng, Shang Lingjie, Zhang Qianli, et al. Land change patterns and driving mechanism in Beijing since 1990 based on GEE platform[J]. Remote Sensing Technology and Application,2018,33(4): 573-583.]   
[23] 李建军,罗格平,丁建丽,等.近50a人工灌排技术进步对玛纳 斯河流域耕地格局变化的影响[J].自然资源学报,2016,31(4): 570-582.iJiajepgingJnlal ress in artificial irigation and drainage technology on the change of cultivated land pattern in the past 5O years in Manasi River Watershed[J]. Journal of Natural Resources,2016,31(4): 570-582.]   
[24] 禹朴家,徐海量,乔木,等.利用CBERS数据测算净耕地系数的 可行性分析[J].干旱区研究,2009,26(6):846-851.[Yu Piaojia, Xu Hailiang,Qiao Mu,etal.Arableland in the Manas River Basin based on CBERS data[J].Arid Zone Research,20O9,26(6): 846-851.]   
[25] 陈志恺,王浩.新疆水资源供需发展趋势、合理配置与可持续利 用研究[R].北京:中国工程院,2012.[Chen Zhikai,Wang Hao. Research on the supplyand requirement development trend,ratio nal allocation and sustainable utilization of water resources in Xinjiang[R]. Beijing: Chinese Academy of Engineering,2012.]   
[26] 焦会青,盛钰,赵成义,等.基于COMSOL软件的绿洲盐渍化土 壤中多离子耦合运移模型构建[J].农业工程学报,2018,34(5): 100-107.[Jiao Huiqing,Sheng Yu, Zhao Chengyi,et al. Modeling of multiple ions coupling transport for salinized soil in oasis based on COMSOL[J]. Transactions of the Chinese Society of Agricultural Engineering,2018,34(15): 100-107.]   
[27] 王振华.典型绿洲区长期膜下滴灌棉田土壤盐分运移规律与灌 溉调控研究[D].北京:中国农业大学,2014.[Wang Zhenhua. Salt movement trends in coton fields with long-term drip irrigation under mulch in typical oasis and irrigation management[D]. Beijing: China Agricultural University,2014.]   
[28] 王成,姚宝林,王兴鹏,等.棉花膜下滴灌干播湿出土壤水盐变 化与耗水规律试验研究[J].中国农村水利水电,2012(10):25- 30.[Wang Cheng,Yao Baolin,Wang Xingpeng,et al. Soil salt transfer law and water consumption characteristics for cotton with drip irrigation under mulch with dry sowing and wet seeding[J]. China Rural Water and Hydropower,2012(10): 25-30.]   
[29] 李光明,邓杰.产业支撑、生态保护与城市可持续发展研究- 以乌鲁木齐为例[J].干旱区地理,2016,39(4):868-876.[Li Guangming, Deng Jie. Industry supporting, ecology protection and urban sustainable development: A case of the Urumqi[J].Arid Land Geography,2016,39(4): 868-876.]   
[30]方创琳.天山北坡城市群可持续发展战略思路与空间布局[J]

# 干旱区地理

干旱区地理,2019,42(1): 1-11.[Fang Chuanglin.Strategic thinking and spatial layout for the sustainable development of urban agglomeration in northern slope of Tianshan Mountains[J].Arid Land Geography,2019,42(1): 1-11.]

[31]张晓宇,许端阳,卢周扬帆,等.基于系统动力学的阿拉善"三 生"用水系统演化模拟与调控[J].干旱区资源与环境,2019,33 (8):107-113.[Zhang Xiaoyu,Xu Duanyang,Luzhou Yangfan,et al.Evolution simulation and regulation of production-living-ecological water system in Alax based on system dynamics[J]. Journal of Arid Land Resources and Environment, 2019,33(8): 107-113.]

# Accurate calculation of water resources carrying status in arid areas based on Google Earth Engine: A case study of Xinjiang Production and Construction Corps

LI Jingxin'²，XU Erqi'，ZHANG Hongqi' (1.Key LaboratoryofLandSurfacePaternandSmulation,InstituteofGeographicciencesand Natural Resources Research, Chinese AcademyofSiences,Beijing0olo1,China;2.UniversityofChineseAcademyofSciences,Beijing0o049,China)

Abstract: In recent years,a series of production and ecological environmental problems have occurred frequently because of the overloading of water resources utilized by the Xinjiang Production and Construction Corps (XJPCC） in China. Assessing the water carrying capacity of an area can precisely provide reference to socioeconomic development and ecological environment management of the XJPCC.Considering that irrigation water accounts for most of the total socioeconomic water consumption of the XJPCC,the precise level of cultivated land area significantly influences the accurate assessment of the water carrying status. However, the statistics of cultivated land area shows inaccuracies,which increase the uncertainty in the water carrying status assessment.For these reasons,the Google Earth Engine (GEE) platform and netcultivated land coefficient were used to precisely obtain the proportion of cultivated land in this research.In this study,three scenarios were simulated on the basis of different irrigation quotas; these scenarios were the conventional irigation,irigation on a plastic film,and mixed standard irrigation scenarios.The total water requirement under the three scenarios could be regarded as the maximum,minimum,and middle values of the XJPCC theoretically. Besides the estimation of the irigation water requirement for planting,a“living-production-ecology” water resources utilization accounting system was constructed for the accurate assessment of the water resource carrying status of the total XJPCC and of each division.The results show that the correction coeficient of cultivated land of the XJPCC is 1.27,which indicates that the inaccuracy in statistics is approximately $2 7 \%$ . In the mixed standard irrigation scenario,the scenario closest to the existing situation,the total water demand of the XJPCC was $1 0 6 . 4 5 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ before the correction of the inaccuracy in the actual cultivated land use value; in this scenario, a $9 . 2 0 \%$ surplus in the total water diversion of the XJPCC was calculated. However,considering the revised cultivated land area,the total water demand was $1 2 5 . 6 4 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ , and it was found that the water resource utilization overloading rate was $7 . 1 6 \%$ ,and only 2 of 13 divisions‘water resource utilization were within the carrying capacity. Irigation water use required more than the existing water resources and therefore used ecological water,which became the critical factor in the overload of water resources utilization. Our study realizes the accurate and scientific asessment of the water resource carying capacity of the XJPCC and provides a reference for utilizing and optimizing water resources and the sustainable development of agriculture.

Key words: water resources carrying status； accurate calculation； Google Earth Engine； Xinjiang Productionand Construction Corps；irrigation water; overload rate