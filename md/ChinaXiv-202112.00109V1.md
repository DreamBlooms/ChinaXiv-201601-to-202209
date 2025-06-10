# 新疆和田河径流丰枯评价及组合分析

黄星¹，陈伏龙¹，赵琪²，何朝飞¹，龙爱华1.3（1.石河子大学水利建筑工程学院,新疆 石河子832000；2.新疆维吾尔自治区水文局，新疆 乌鲁木齐830000；3.中国水利水电科学研究院,流域水循环模拟与调控国家重点实验室,北京100038)

摘要：基于同古孜洛克和乌鲁瓦提水文站1960—2016年年尺度与月尺度径流数据,分别采用均值标准差法和模糊集对分析法对和田河2大支流进行丰枯类别评价，并在此基础上优选模糊集对法和Copula函数法计算2条源流径流丰枯组合概率，同时分析2支流间互补的优劣性。结果表明：模糊集对法考虑了年内径流贡献度使评价结果更客观,玉龙喀什河枯水年占比最高,应提高枯水期水资源利用,喀拉喀什河平水年占比最高,表明喀拉喀什河常年来水稳定;统计法和Copula函数得出的丰枯概率存在差异性与数据使用、划分方式及源流区域海拔有关,2种方法结果均表现为异步丰枯概率大于同步丰枯概率,两支流具有较好互补性。该结果能更清晰的描述和田河径流丰枯状态及丰枯组合特性，可为和田河流域水资源调度提供参考和决策依据。

关键词：模糊集对法；Copula函数；均值标准差法；丰枯组合；和田河；新疆

河流资源作为维系自然稳定，保障生态需水的重要元素，是人类生产活动中不可或缺的资源，特别是在西北干旱区，河川径流对缓解绿洲生态系统水资源短缺的矛盾具有重要的作用。近年来，受全球气候变化影响，和田河流域丰枯变化规律也随之改变，该变化直接影响了和田河流域生态与社会发展需水的变换过程。因此，研究环境变化下和田河流域变化规律，对干旱区水资源的管理提供一定的参考价值[1-3]

径流丰枯划分是水文水资源计算分析中的重要内容，常用方法包括水文频率分析法、灰色分类、投影寻踪法、模糊聚类法、集对分析法等[4]。上述方法均可处理水文分类问题，但存在忽略径流年内分配,求解复杂及具有主观判断等不足现象[5-7]。虽然集对分析法弥补了上述不足，但未考虑边界模糊性及年内径流贡献程度问题[8-9]。因此,需要引入模糊理论和权重分析构建模糊集对方程，使得评价结果更为客观准确。

丰枯变化具有一定的规律，其规律性表现出：在相同时间条件下，多种水文要素的产生丰、枯情况的不同，即丰枯组合概率不同。通过水文年鉴及文献资料统计可知，和田河2支流(玉龙喀什河与喀拉喀什河)出现的丰枯组合在时间上存在重叠部分，因此，本文针对变化环境下的喀拉喀什河、玉龙喀什河1960一2016年径流量，综合采用模糊理论和权重分析构建模糊集对方程，对2支流丰枯组合概率进行分析，并对比Copula函数构建出的2支流间二维丰枯组合概率,以期为协调和田河流域生产、生活、生态(“三生")用水，缓解水资源供给矛盾，研究径流丰枯变化规律，评估径流丰枯类别可为流域内洪旱灾害的防治及水资源高效利用提供参考依据。

# 1研究区概况

和田河流域属新疆西南区域,位于塔里木盆地南缘和昆仑山北麓之间，地理坐标为 $7 7 ^ { \circ } 2 5 ^ { \prime } { \sim } 8 1 ^ { \circ } 4 3 ^ { \prime } \mathrm { E }$ $3 4 ^ { \circ } 5 2 ^ { \prime } { \sim } 4 0 ^ { \circ } 2 8 ^ { \prime } \mathrm { N }$ ，流域面积约 $4 8 8 7 0 \mathrm { k m } ^ { 2 }$ 。受昆仑山和帕米尔高原阻碍影响，印度洋暖湿气流难以进入流域内[],使得流域内形成干旱少雨，气温高，潜在蒸发大等大陆性气候。和田河干流由玉龙喀什河(简称玉河)与喀拉喀什河(简称喀河)汇聚形成(图1)，流经塔克拉玛干沙漠最终汇人塔里木河成为塔里木河"三源"之一[12]。和田河不仅承担向塔里木河输水任务，同时也维系着和田河周边地区的生态环境。随着南疆地区基础设施不断完善与经济投入，和田河流域人口基数与耕地面积快速上升，生态用水受生活、生产用水挤占，流域内的生态稳定性遭到威胁，若不及时合理分配水资源利用，将造成流域内土地荒漠化、生态失衡等问题[13]

![](images/58ca85ba87c57cddd5c576163a3b396838b7c31f1d28eec1d3313a1a11aa5548.jpg)  
图1和田河水系示意图Fig.1 Hotan River basin

# 2 ，数据与方法

在传统分析中，常以均值标准差法评判径流丰枯类别，该方法是以年径流数据为基础进行丰枯判别，忽略了年内时段径流量对年径流总量贡献的不同，同时该方法未考虑丰枯间的模糊性问题易导致评价结果偏颇，因此将模糊概念与权重计算加入集对分析中，采用模糊集对法对径流丰枯等级进行科学划分。对于径流丰枯变化规律的研究以统计法分析较多，而此方法需要大量数据作为支撑，以保证研究规律的精准性。采用模糊集对法判断径流丰枯类别，并在此评价结果上，由统计法计算出丰枯变化概率。采用Copula函数构建丰枯组合模型，用以对比统计法结果，以期探究径流丰枯变化规律。

研究数据采用同古孜洛克和乌鲁瓦提水文站1960一2016年实测逐月径流资料进行整理分析。

# 2.1均值标准差法

以年尺度径流数据为基础，通过相关公式划分5种丰枯类别区间，即：[0,𝑥,+𝑘s）、[χ+𝑘sj,χ+$k _ { 2 } s _ { j }$ ）、 $\big [ \bar { x } _ { j } + k _ { 2 } s _ { j } , \bar { x } _ { j } + k _ { 3 } s _ { j } \big )$ 、 $\big [ \bar { x } _ { j } + k _ { 3 } s _ { j } , \bar { x } _ { j } + k _ { 4 } s _ { j } \big )$ 、 $\big [ \bar { x } _ { j } + \big ]$ $k _ { 4 } s _ { j } , + \infty )$ ,其中 $\bar { x }$ 和 $s$ 为年平均流量的均值、标准差，系数经验取值分别为 $k _ { 1 } { = } { - } 0 . 9 , k _ { 2 } { = } { - } 0 . 3 , k _ { 3 } { = } 0 . 3$ ，$k _ { 4 } { = } 0 . 9 ^ { [ 1 4 ] }$ （204号

# 2.2模糊集对法

以月径流量为基础，通过构建模糊集对式判断玉河与喀河径流的丰枯等级。首先，以均值标准差法确定5种等级的区间范围[15]。由于等级标准符合越小越优的条件约束，因此采用偏小型函数进行模糊化并建立联系度公式，如公式(1)所示[16]

$$
\mu _ { { } _ { A _ { i } - B _ { m } } } =
$$

$$
\begin{array} { r l } & { \mu _ { s , - B _ { s } } ^ { \prime } = } \\ & { \{ \begin{array} { l l } { \displaystyle 1 } & { , x _ { i , \star } \leq S _ { 1 } } \\ { \displaystyle \frac { | S _ { 1 } + S _ { 2 } - 2 x _ { i , j } } { S _ { 2 } - S _ { 1 } } + \frac { 2 x _ { i , j } - 2 S _ { 1 } } { S _ { 2 } - S _ { 1 } } I _ { 1 } } & { , S _ { 1 } \leqslant x _ { i , j } < \frac { S _ { 1 } + S _ { 2 } } { 2 } } \\ { \displaystyle 1 } & { , S _ { 2 } + S _ { 3 } - 2 x _ { i , j } } \\ { \displaystyle S _ { s } - S _ { 1 } } & { I _ { 1 } + \frac { 2 x _ { i , j } - S _ { 1 } - S _ { 2 } } { S _ { 3 } - S _ { 1 } } I _ { 2 } , \frac { S _ { 2 } + S _ { 3 } } { 2 } \leqslant x _ { i , j } \leqslant \frac { S _ { 1 } + S _ { 2 } } { 2 } } \end{array}  } \\ & { \{ \begin{array} { l l } { \displaystyle 1 } & { S _ { 3 } + S _ { 4 } - 2 x _ { i , j } } \\ { \displaystyle \frac { S _ { 3 } + S _ { 4 } - 2 x _ { i , j } } { S _ { 4 } - S _ { 2 } } I _ { 2 } + \frac { 2 x _ { i , j } - S _ { 2 } - S _ { 1 } } { S _ { 4 } - S _ { 2 } } I _ { 3 } , \frac { S _ { 2 } + S _ { 3 } } { 2 } \leqslant x _ { i , j } \leqslant \frac { S _ { 3 } + S _ { 4 } } { 2 } } \\ { \displaystyle 1 } & { , S _ { 4 } - 2 x _ { i , j } } \\ { \displaystyle \frac { 2 S _ { 4 } - S _ { 3 } } { S _ { 4 } - S _ { 3 } } I _ { 3 } + \frac { 2 x _ { i , j } - S _ { 3 } - S _ { 4 } } { S _ { 4 } - S _ { 3 } } I } & { , \displaystyle \frac { S _ { 3 } + S _ { 4 } } { 2 } \leqslant x _ { i , j } < S _ { 4 } } \end{array}  } \end{array}
$$

式中： $I$ 为差异不确定分量系数，按经验取值法，可确定 $I _ { 1 } { = } { - } 0 . 5 , I _ { 2 } { = } 0 , I _ { 3 } { = } 0 . 5$ ，对立系数 $J { = } { - } 1$ ,联系数取值范围为 $- 1 \leqslant \mu _ { A _ { i } - B _ { m } } \leqslant 1 ^ { [ 1 7 ] }$ 。 $ { \mu } _ { { A } _ { i } - { B } _ { m } }$ 为集合 $A _ { i } ( i { = } 1$ ，$2 , \cdots , n )$ 与集合 $B _ { m } ( m { = } 1 , 2 , 3 , 4 , 5 )$ 的联系度， $S _ { 1 } { \sim } S _ { 4 }$ 为临界值， $x _ { i , j }$ 为样本值。

采用熵权法[18]判断年内径流量贡献比率，并将计算结果代人集对方程中，得到综合联系度公式(2)。

$$
\mu _ { _ { A - B } } = \sum _ { j = 1 } ^ { n } \lambda _ { j } \mu _ { _ { A _ { n } - B _ { m } } } = \sum _ { j = 1 } ^ { n } \lambda _ { j } a _ { j } + \sum _ { j = 1 } ^ { n } \lambda _ { j } b _ { j , \mathrm { ~ l ~ } } I _ { 1 } +
$$

$$
\sum _ { j = 1 } ^ { n } \lambda _ { j } b _ { j , \mathrm { ~ 2 } } I _ { 2 } + \sum _ { j = 1 } ^ { n } \lambda _ { j } b _ { j , \mathrm { ~ 3 } } I _ { 3 } + \sum _ { j = 1 } ^ { n } \lambda _ { j } c _ { j } J
$$

式中： $a \ 、 b \ 、 b \ 、 b \ 、 c$ 为联系度分量； $n$ 为研究对象指标数； $\lambda _ { j }$ 为第 $j$ 个指标对应的权重值; $\mu _ { A - B }$ 为集合联系数。

为避免系数选择存在主观干扰，采用置信度准

则对样本所属等级进行判断。如公式(3)所示：

$$
h _ { k } = f _ { 1 } + f _ { 2 } + \cdots + f _ { k } > \alpha
$$

式中: $f _ { i } { = } \sum _ { j { = 1 } } ^ { n } \lambda _ { j } a _ { j }$ ， $a _ { j }$ 为第 $j$ 个指标对应联系度分量， $n$ 为样本总数； $h _ { k }$ 为样本所属第 $k$ 级； $\alpha$ 为置信度，取值界定为[0.5,0.7][19]。

# 2.3Copula函数联合分布

Copula函数是连接多个变量边缘分布所构成的多维联合模型[20-21]。其假设单变量边缘分布分别为$F _ { x } ( x ) \ J _ { y } ( y )$ ,则对应存在二维联合分布 $F ( x , y )$ ,Copu-la函数则可以表示为：

$$
F ( x , y ) { = } C { \big [ } F _ { x } ( x ) , F _ { y } ( y ) { \big ] } { = } C ( u , v )
$$

式中： $\boldsymbol { u } _ { \boldsymbol { \cdot } \boldsymbol { v } }$ 为单变量的边缘分布。

根据函数表达式进行建模，其步骤主要为：(1)通过AIC(Akaike informationcriterion）检验和均方根误差(RMSE)检验对P-III分布、广义极值分布(GEV）、指数分布(EXP)和正态分布(Normal)进行拟合优选。（2）通过Kendall相关性检验计算Copula函数参数。（3）以AIC、RMSE检验Gumbel、Frank、Gaussian和Clayton函数与二维累计经验频率拟合效果。（4）以累积概率 $P _ { f } { = } 6 2 . 5 \%$ 和 ${ P _ { k } } \mathrm { { = } } 3 7 . 5 \%$ 为丰水、平水与枯水的分割频率[22]

# 3实例分析

# 3.1径流丰枯分类

3.1.1 基于均值标准差法径流丰枯分类根据均值标准差法对径流进行划分(表1)。

3.1.2 基于模糊集对法径流丰枯分类建立玉河、喀河1960—2016年月径流样本 $x _ { i , j } ( i { = } 1 , 2 , \cdots , 5 7$ $j { = } 1 , 2 , \cdots , 1 2 )$ ，并确定玉河和喀河不同指标数的临界值，表2为不同支流各月对应的临界值

将玉河和喀河不同时段的临界值和 $x _ { i , j }$ 带入式(1)，得到模糊处理后的联系度分量。以玉河1962年1月径流为例，对应样本为 $x _ { 1 9 6 2 , 1 } { = } 7 . 6 0 0$ ，介于 $S _ { 1 } \leqslant$ $x _ { 1 9 6 2 , 1 } { < } ( S _ { 1 } { + } S _ { 2 } ) / 2$ ，选取该条件对应的公式计算可知，样本 $x _ { 1 9 6 2 , 1 }$ 的联系度分量 $b _ { 1 }$ 隶属枯水年的程度为0.614，联系度分量 $\boldsymbol { a }$ 属于特枯水年的程度为0.396，同理，可求其他时段的联系度分量，

采用熵权法计算玉河、喀河各月权重，可知玉河权重值 $\lambda = \left( 0 . 0 8 2 4 5 , 0 . 0 4 7 0 7 , 0 . 0 2 9 4 2 , 0 . 0 6 9 4 7 , \right.$ 号0.09794，0.13113，0.10996，0.14607，0.06430，0.04725，0.04512）；喀河各月权重值 $\lambda { = } ( 0 . 0 3 8 7 5$

表1年平均径流分类标准  

<html><body><table><tr><td></td><td colspan="4">Tab.1 Classification standard of annual average runoff</td><td>/(m²·s-1)</td></tr><tr><td>类别</td><td>特枯</td><td>枯</td><td>平</td><td>丰</td><td>特丰</td></tr><tr><td>玉河</td><td><57.554</td><td><67.883</td><td><78.111</td><td><88.390</td><td>≥88.390</td></tr><tr><td>喀河</td><td><53.288</td><td><65.980</td><td><78.673</td><td><91.365</td><td>≥91.365</td></tr></table></body></html>

表2径流各月份临界值  
Tab.2 Classification standard of monthlyrunoff   

<html><body><table><tr><td rowspan="2">月份</td><td colspan="4">玉河</td><td colspan="4">喀河</td></tr><tr><td>S</td><td>S</td><td>S</td><td>S4</td><td>S1</td><td>S</td><td>S</td><td>S4</td></tr><tr><td>1</td><td>6.526</td><td>8.026</td><td>9.525</td><td>11.025</td><td>8.068</td><td>9.249</td><td>10.429</td><td>11.609</td></tr><tr><td>2</td><td>7.002</td><td>8.148</td><td>9.293</td><td>10.438</td><td>9.841</td><td>10.481</td><td>11.122</td><td>11.763</td></tr><tr><td>3</td><td>7.687</td><td>8.625</td><td>9.561</td><td>10.499</td><td>10.382</td><td>13.317</td><td>16.252</td><td>19.186</td></tr><tr><td>4</td><td>9.840</td><td>11.990</td><td>14.140</td><td>16.289</td><td>15.701</td><td>21.165</td><td>26.628</td><td>32.092</td></tr><tr><td>5</td><td>22.703</td><td>28.603</td><td>34.502</td><td>40.402</td><td>36.532</td><td>45.996</td><td>55.460</td><td>64.924</td></tr><tr><td>6</td><td>72.108</td><td>95.649</td><td>119.190</td><td>142.731</td><td>96.621</td><td>118.051</td><td>139.482</td><td>160.914</td></tr><tr><td>7</td><td>192.605</td><td>254.435</td><td>316.266</td><td>378.097</td><td>163.288</td><td>210.746</td><td>258.205</td><td>305.663</td></tr><tr><td>8</td><td>206.126</td><td>262.214</td><td>318.301</td><td>374.389</td><td>172.332</td><td>211.367</td><td>250.402</td><td>289.436</td></tr><tr><td>9</td><td>47.396</td><td>64.683</td><td>81.970</td><td>99.256</td><td>50.609</td><td>68.568</td><td>86.527</td><td>104.860</td></tr><tr><td>10</td><td>14.456</td><td>17.389</td><td>20.320</td><td>23.252</td><td>20.387</td><td>24.485</td><td>28.583</td><td>32.681</td></tr><tr><td>11</td><td>9.229</td><td>10.775</td><td>12.282</td><td>13.806</td><td>13.313</td><td>16.126</td><td>18.939</td><td>21.753</td></tr><tr><td>12</td><td>7.883</td><td>9.131</td><td>10.376</td><td>11.622</td><td>7.719</td><td>10.853</td><td>13.995</td><td>17.133</td></tr></table></body></html>

0.02170，0.08951，0.11829，0.09184，0.07064,0.10484，1.33360，0.12966，0.05954，0.06215，0.07943）。将权重值、联系度分量和差异不确定分量系数代人公式(2)中，可求得样本隶属某评价标准的可能性。样本 $x _ { 1 9 6 2 , 1 }$ 隶属各评价等级结果分别为 $: f _ { 1 } = 0 . 2 7 7 5 6 , f _ { 2 } = 0 . 4 8 0 6 1 , f _ { 3 } = 0 . 1 1 2 3 3 , f _ { 4 } = 0 . 0 9 5 4 2 , f _ { 5 } =$ 0.00349。依据置信度准则筛选样本隶属等级，取 $\scriptstyle . \alpha =$ 0.5，可知 $f _ { 1 } + f _ { 2 } > \alpha$ ，由此判断玉河1962年为枯水年，即$x _ { 1 9 6 2 , 1 }$ 属于ⅡI类标准。模糊集对法分类结果见表3。

从表3可知，在均值标准差法判断下，玉河近57a内共出现15次丰水年，20次枯水年，喀河近57a内共出现18次丰水年，26次枯水年；模糊集对分类结果表明：玉河丰水年有10次，枯水年有26次，平水年13次，喀河丰水年出现9次，枯水年18次及30次平水年。玉河、喀河径流丰枯均表现出，枯水年次数大于丰水年次数，符合干旱区水资源较少现象。这表明应重点关注玉河流域枯水年的水资源利用，而喀河来水较为平稳。

3.1.3丰枯差异分析对比2种丰枯评价方法结果可知，玉河1960年、1971年、1973年、1994年和2004年、喀河1961年、1966年和2014年为差异度最大年份，将各时段的临界值绘图连线作为临界线，以玉河1960年、1973年、1994年、2004年为差异代表年，分析代表年的径流过程(图2)。

由图2分析1960年径流过程，1—6月和10—12月的径流均在 $S _ { 2 }$ 以下，径流属于“枯"和"特枯"2种

# 表3径流丰枯分类结果

Tab.3Resultsofrunoffclassification   

<html><body><table><tr><td rowspan="2">年份</td><td colspan="2">模糊集对法</td><td colspan="2">均值标准差法</td><td rowspan="2">年份</td><td colspan="2">模糊集对法</td><td colspan="2">均值标准差法</td></tr><tr><td>玉河</td><td>喀河</td><td>玉河</td><td>喀河</td><td>玉河</td><td>喀河</td><td>玉河</td><td>喀河</td></tr><tr><td>1960</td><td>特枯</td><td>枯</td><td>丰</td><td>平</td><td>1989</td><td>枯</td><td>枯</td><td>特枯</td><td>枯</td></tr><tr><td>1961</td><td>丰</td><td>平</td><td>特丰</td><td>特丰</td><td>1990</td><td>平</td><td>平</td><td>平</td><td>丰</td></tr><tr><td>1962</td><td>枯</td><td>特枯</td><td>枯</td><td>特枯</td><td>1991</td><td>枯</td><td>平</td><td>枯</td><td>枯</td></tr><tr><td>1963</td><td>枯</td><td>枯</td><td>枯</td><td>枯</td><td>1992</td><td>特桔</td><td>枯</td><td>特枯</td><td>枯</td></tr><tr><td>1964</td><td>枯</td><td>枯</td><td>枯</td><td>枯</td><td>1993</td><td>特枯</td><td>枯</td><td>特枯</td><td>特枯</td></tr><tr><td>1965</td><td>特桔</td><td>特桔</td><td>特枯</td><td>特桔</td><td>1994</td><td>平</td><td>平</td><td>平</td><td>丰</td></tr><tr><td>1966</td><td>丰</td><td>枯</td><td>丰</td><td>丰</td><td>1995</td><td>平</td><td>枯</td><td>枯</td><td>枯</td></tr><tr><td>1967</td><td>平</td><td>平</td><td>平</td><td>丰</td><td>1996</td><td>平</td><td>平</td><td>平</td><td>枯</td></tr><tr><td>1968</td><td>枯</td><td>平</td><td>平</td><td>枯</td><td>1997</td><td>枯</td><td>平</td><td>枯</td><td>平</td></tr><tr><td>1969</td><td>枯</td><td>枯</td><td>枯</td><td>平</td><td>1998</td><td>平</td><td>平</td><td>平</td><td>枯</td></tr><tr><td>1970</td><td>平</td><td>平</td><td>平</td><td>平</td><td>1999</td><td>平</td><td>枯</td><td>平</td><td>枯</td></tr><tr><td>1971</td><td>平</td><td>平</td><td>特丰</td><td>平</td><td>2000</td><td>丰</td><td>平</td><td>丰</td><td>平</td></tr><tr><td>1972</td><td>枯</td><td>枯</td><td>枯</td><td>枯</td><td>2001</td><td>平</td><td>平</td><td>平</td><td>平</td></tr><tr><td>1973</td><td>枯</td><td>平</td><td>丰</td><td>平</td><td>2002</td><td>平</td><td>平</td><td>平</td><td>枯</td></tr><tr><td>1974</td><td>枯</td><td>枯</td><td>枯</td><td>枯</td><td>2003</td><td>平</td><td>平</td><td>平</td><td>丰</td></tr><tr><td>1975</td><td>枯</td><td>枯</td><td>枯</td><td>枯</td><td>2004</td><td>平</td><td>平</td><td>平</td><td>丰</td></tr><tr><td>1976</td><td>枯</td><td>枯</td><td>枯</td><td>枯</td><td>2005</td><td>丰</td><td>丰</td><td>丰</td><td>丰</td></tr><tr><td>1977</td><td>平</td><td>平</td><td>平</td><td>丰</td><td>2006</td><td>丰</td><td>丰</td><td>丰</td><td>丰</td></tr><tr><td>1978</td><td>平</td><td>丰</td><td>特丰</td><td>特丰</td><td>2007</td><td>平</td><td>平</td><td>平</td><td>平</td></tr><tr><td>1979</td><td>枯</td><td>平</td><td>枯</td><td>枯</td><td>2008</td><td>平</td><td>平</td><td>平</td><td>枯</td></tr><tr><td>1980</td><td>枯</td><td>平</td><td>枯</td><td>枯</td><td>2009</td><td>枯</td><td>平</td><td>枯</td><td>枯</td></tr><tr><td>1981</td><td>平</td><td>平</td><td>平</td><td>平</td><td>2010</td><td>特丰</td><td>丰</td><td>特丰</td><td>特丰</td></tr><tr><td>1982</td><td>枯</td><td>平</td><td>平</td><td>平</td><td>2011</td><td>特丰</td><td>丰</td><td>特丰</td><td>丰</td></tr><tr><td>1983</td><td>平</td><td>平</td><td>枯</td><td>丰</td><td>2012</td><td>特丰</td><td>特丰</td><td>特丰</td><td>丰</td></tr><tr><td>1984</td><td>枯</td><td>平</td><td>平</td><td>平</td><td>2013</td><td>特丰</td><td>平</td><td>特丰</td><td>平</td></tr><tr><td>1985</td><td>枯</td><td>平</td><td>平</td><td>枯</td><td>2014</td><td>平</td><td>特丰</td><td>平</td><td>枯</td></tr><tr><td>1986</td><td>特枯</td><td>枯</td><td>平</td><td>枯</td><td>2015</td><td>平</td><td>特丰</td><td>丰</td><td>特丰</td></tr><tr><td>1987</td><td>枯</td><td>枯</td><td>特枯</td><td>枯</td><td>2016</td><td>特丰</td><td>特丰</td><td>特丰</td><td>丰</td></tr><tr><td>1988</td><td>枯</td><td>平</td><td>平</td><td>丰</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

![](images/4b70d811446b46d5584a5030c3fd7551580c7f3d4485e21c704450ad6f34edea.jpg)  
图2代表年月径流过程分布  
Fig.2Represents the distributions of annual and monthly runoff process

状态，7月、9月径流在 $S _ { 3 } , S _ { 4 }$ 之间，分类结果属于“平”与“丰"之间，由于径流更接近 $S _ { 3 }$ ,属于“平"的概率更大，因此7月、9月分类等级为“平”，8月径流大于临界值 $S _ { 4 }$ ，属于“特丰”，因此判定玉河1960年为“特枯"水年。同理可分析其余差异年份。

差异原因在于模糊集对法考虑到年内径流对全年径流贡献程度不同，而玉河与喀河为季节性河流[23],具有汛期径流量大,非汛期径流量少的特点，因此在赋权后的模糊集对评价结果与均值标准法评价结果存在差异。而均值标准差法视各时段径流比重一致，从而扩大了年内时段中极端情况，导致评价结果偏大。通过计算可知，玉河1960年汛期径流权重为 $5 1 . 6 \%$ ,非汛期径流权重为 $4 9 . 4 \%$ ,两者相差不大，这表明，径流丰枯等级判定与径流量大小和年内径流的权重均相关。模糊集对法能综合考虑时程分配，能客观准确的表达年径流分类结果。

# 3.2径流丰枯组合分析

3.2.1基于模糊集对分析结果的丰枯组合概率分析上述丰枯评价方法均可分析径流丰枯状态，因模糊集对评价法能全面、客观反应出径流真实状态，以模糊集对评价结果为基础，基于玉河、喀河的月径流量数据，采用统计法分析玉河、喀河丰枯组合概率。

为方便计算，将径流分为丰、平、枯3类进行组合概率分析，将模糊集对法分类结果中的“特丰"归入“丰”，“特枯"归于“枯”，则2河共形成9种组合状态(表4)。

玉河和喀河同步丰枯概率为 $3 5 . 8 3 \%$ ，同丰的概率最小为 $2 . 7 7 \%$ ,同平、同枯的概率分别为 $1 7 . 5 4 \%$ 和$1 5 . 5 1 \%$ 。异步丰枯组合概率为 $6 4 . 1 7 \%$ ,大于同步丰枯组合概率，初步可断定，利于河流间的丰枯互补。玉丰喀枯的组合概率为 $5 . 5 4 \%$ ，玉枯喀丰的组合概率为 $7 . 7 5 \%$ ,表明玉河径流与喀河径流最佳丰枯互补概率较低。

3.2.2 基于Copula 函数丰枯组合概率分析 Copula函数是以玉河、喀河年径流量为基础，将其序列的经验频率分别与4种单变量边缘分布函数拟合(表5)。

从表5的结果可知，在AIC检验与RMSE检验下，玉河、喀河服从P-III分布检验值为最小值，因此以P-III分布作为2径流序列的最优边缘分布构建联合分布。

拟合二维联合频率和经验频率，并通过AIC和RMSE对拟合结果进行检验。在4种Copula函数类型中，Frank-Copula函数拟合效果最好，AIC、RMSE检验结果分别为-429.895,0.022。

通过Kendall相关计算得出系数 $\scriptstyle \tau = 0 . 6 2 9 5$ ,求得Copula参数值 $\scriptstyle \theta = 0 . 8 3 5 4$ □

根据丰枯划分频率，求解出Copula函数联合丰枯组合概率(表6)。

由表6可知，径流同步丰枯概率总计达到$4 8 . 3 \%$ ，其中同丰、同平、同枯的概率为分别为$8 . 4 1 \% . 1 8 . 4 8 \% . 2 1 . 4 1 \%$ ，同枯组合概率为9种组合状况中最高值，异步丰枯概率为 $5 1 . 7 \%$ ,其中,丰-枯最有利互补组合的组合概率为 $1 6 . 6 6 \%$ 。2支流整体组合概率表现出异步组合概率总和大于同步丰枯组合概率，说明2支流具有良好的互补性，且该结果与统计法得到的组合概率表现一致,说明Copula函

表4基于统计结果下的丰枯组合概率  
Tab.4 Probability of synchronous-asynchronous encounters based on statistical results   

<html><body><table><tr><td rowspan="2">河流</td><td colspan="4">丰枯同步概率/%</td><td colspan="7">丰枯异步概率/%</td></tr><tr><td>同丰</td><td>同平</td><td>同枯</td><td>合计</td><td>玉丰喀平</td><td>玉丰喀枯</td><td>玉平喀丰</td><td>玉平喀枯</td><td>玉枯喀丰</td><td>玉枯喀平</td><td>合计</td></tr><tr><td>玉河-喀河</td><td>2.77</td><td>17.54</td><td>15.51</td><td>35.83</td><td>9.23</td><td>5.54</td><td>5.26</td><td>10.52</td><td>7.75</td><td>25.85</td><td>64.17</td></tr></table></body></html>

# 表5变量拟合检验

Tab.5 Fitness test results   

<html><body><table><tr><td rowspan="2">分布状态</td><td rowspan="2">河流站点</td><td rowspan="2">检验方法</td><td colspan="4">分布类型</td></tr><tr><td>P-III</td><td>GEV</td><td>EXP</td><td>Normal</td></tr><tr><td>单变量分布</td><td>玉河</td><td>AIC</td><td>-405.534</td><td>-356.028</td><td>-392.461</td><td>-356.748</td></tr><tr><td rowspan="6">联合变量分布</td><td></td><td>RMSE</td><td>0.027</td><td>0.032</td><td>0.028</td><td>0.032</td></tr><tr><td>喀河</td><td>AIC</td><td>-410.029</td><td>-332.626</td><td>-367.053</td><td>-332.017</td></tr><tr><td></td><td>RMSE</td><td>0.026</td><td>0.034</td><td>0.03</td><td>0.035</td></tr><tr><td>玉河-喀河</td><td></td><td>Frank</td><td>Gumbel</td><td>Gaussian</td><td>Clayton</td></tr><tr><td></td><td>AIC</td><td>-429.895</td><td>-418.378</td><td>-408.106</td><td>-397.119</td></tr><tr><td></td><td>RMSE</td><td>0.022</td><td>0.024</td><td>0.027</td><td>0.03</td></tr></table></body></html>

表6基于Copula函数的丰枯组合概率  
Tab.6Probability of synchronous-asynchronous encounters of the Copula joint distributions   

<html><body><table><tr><td rowspan="2">河流</td><td colspan="4">丰枯同步概率/%</td><td colspan="7">丰枯异步概率/%</td></tr><tr><td>同丰</td><td>同平</td><td>同枯</td><td>合计</td><td>玉丰喀平</td><td>玉丰喀枯</td><td>玉平喀丰</td><td>玉平喀枯</td><td>玉枯喀丰</td><td>玉枯喀平</td><td>合计</td></tr><tr><td>玉河-喀河</td><td>8.41</td><td>18.48</td><td>21.41</td><td>48.3</td><td>5.76</td><td>8.33</td><td>5.76</td><td>11.76</td><td>8.33</td><td>11.76</td><td>51.7</td></tr></table></body></html>

数分析结果合理。

# 4讨论

对比模糊集对结果统计概率与Copula函数联合概率，两者结果整体相同，但丰枯组合概率有所不同，丰枯同步最大相差 $5 . 9 \%$ ,丰枯异步最大相差$1 4 . 0 9 \%$ 。因此，分析其造成差异原因可能存在：(1)Copula函数是基于年尺度数据构建联合分布函数，以联合概率计算出丰枯组合概率;模糊集对分析是以月尺度数据评价出年径流丰枯结果，利用统计方法计算出丰枯组合频率，两者在数据使用上有所不同。（2）Copula函数计算丰枯组合中利用 $3 7 . 5 \%$ 和$6 2 . 5 \%$ 的频率划分径流丰枯存在主观判断。（3）模糊集对结果得出的统计频率是通过近57a的径流资料而计算出了组合频率，水文序列长度有限，不能代表整体事件的概率，而Copula函数能从已知的二维联合频率趋势来推断较长时段的径流丰枯组合的概率。

同时借助于物理成因分析可知，玉河主要产流区西昆仑山和喀河产流区喀喇昆仑山对应的积雪冰川覆盖面积、海拔的不同。喀喇昆仑山冰雪覆盖面积较广、海拔较高且年均 $0 \mathrm { { ^ { \circ } C } }$ 等温线海拔为4200m左右;西昆仑山冰雪覆盖面积小于喀喇昆仑山，其最大融雪海拔介于 $3 8 0 0 { \sim } 4 0 0 0 ~ \mathrm { m }$ 之间，形成有效径流补给大于喀喇昆仑山冰雪补给，这点通过对比年径流量可以得到应证[24],由于不同海拔对应融雪速度不同，导致喀喇昆仑山冰雪融化时间比西昆仑山冰雪融化时间较为滞后，因此造成了丰枯异步概率较大的特征。

为提高水资源利用效率与经济发展，乌鲁瓦提水库作为重点建设项目于2002年修建在喀河出山□处,其控制流域面积 $1 9 9 8 3 { \mathrm { k m } } ^ { 2 }$ ，兴利库容达 $2 . 2 4 \times$ $1 0 ^ { 8 } \mathrm m ^ { 3 }$ ,对洪水具有显著削峰作用,使得汛期洪峰流量小于天然洪峰流量。相关研究表明，乌鲁瓦提水库的修建使喀河年内径流分配更为均匀，且通过水库提前泄洪排沙，使得喀河与玉河的同步丰枯概率较低[25]。本文将模糊集对评价结果与基于Copula函数方法计算的丰枯组合概率进行对比，2种方法得到结果均可以反应水文事件概率。在短期水文序列研究中，采用统计法得到的结果更易反映近年来流域丰枯的组合状况，为水资源合理优化配置提供参考依据。而从水利工程设计角度出发，采用Copula函数联合分布得到的组合概率能更好为水利工程设计提供支撑依据。同时本文所探讨的方法可为径流丰枯评价及组合分析提供更好的研究思路，为丰枯组合概率研究提供理论参考。

# 5结论

径流丰枯变化规律是流域水资源规划配置、管理的主要依据。研究径流丰枯评价及组合分析，可有效的反映径流丰枯变化情况，从而为流域水资源管理提供理论依据。本文基于均值标准差法及模糊集对分析方法，并结合Copula函数，探求和田河流域丰枯组合概率，其结论如下：

（1）在径流丰枯分类中，均值标准差法以年径流数据为基础，未考虑径流年内变化，导致评价结果较为片面。而相较均值标准差法，模糊集对分析方法考虑了年内径流分布和临界模糊问题对径流丰枯分类的影响，并以水文站各年份的月径流构建模糊联系度方程进行丰枯分类，使评价结果客观合理。(2）由模糊集对法可知，由于玉龙喀什河在枯水年占比较高，应提高枯水期水资源利用量；同时，喀拉喀什河平水年的占比较高，充分表现出喀拉喀什河常年来水较为稳定。(3）通过丰枯组合分析，2河流异步丰枯组合概率大于同步丰枯组合概率，径流互补性较好，且发生特大洪水概率较小，此研究可为流域水资源管理提供坚实的基础。

# 参考文献(References):

[1]余其鹰,张江辉,白云岗,等.1957—2018年和田河源流径流演 变特征[J].干旱区研究,2021,38(2): 494-503.[Yu Qiying,Zhang Jianghui,Bai Yungang,et al.Evolution characteristics of the headstream of the Hotan River headstream from 1957 to 2O18[J].Arid Zone Research,2021,38(2): 494-503.]   
[2]薛强.气候变化影响下的新疆和田河流域水资源变化特征研究 [D].西安:长安大学,2O20.[Xue Qiang.Variation Characteristics Assessment for Water Resources the Hotan River Basin in Xinjiang under Climate Change[D].Xi'an: Chang'an University,2020.]   
[3] 邓铭江,周海鹰,徐海量,等.塔里木河干流上中游丰枯情景下 生态水调控研究[J].干旱区研究,2017,34(5):959-966.[Deng Mingjiang, Zhou Haiying,Xu Hailiang,etal.Regulation of ecological water volume under high-or low-flow in the mainstream area of the Tarim River[J].Arid Zone Research,2017,34(5): 959-966.]   
[4] 王文圣.水文水资源集对分析[M].北京:科学出版社,2010. [WangWensheng.Set Pair Analysis of Water Resources and Hydrology[M].Beijing: Science Press,2010.]   
[5] 张春荣,纪淑娟，朱红梅.基于层次分析和灰色分析的水质风险 评价方法[J].水资源保护,2011,27(1):11-14.[Zhang Chunrong, Ji Shujuan,Zhu Hongmei.Water quality risk assessment based on analytic hierarchy process and gray analysis method[J]. Water Resources Protection,2011,27(1): 11-14.]   
[6]赵太想,王文圣,周秀平.一种径流丰枯分类的新方法研究[J]. 人民黄河,2006,57(5):12-13.[Zhao Taixiang,Wang Wensheng,   
[7]邓红霞,汤成友,李存军,等.基于模糊模式识别的径流特性分 析[J].四川大学学报(工程科学版),2006,49(3):29-33.[Deng Hongxia, Tang Chengyou, Li Cunjun,et al.Runoff characteristic analysis by fuzzy pattern recognition[J]. Journal of Sichuan University(Engineering Science Edition),2006,49(3): 29-33.]   
[8]李深奇,肖景西,覃光华,等.基于率定量化标准系数的 SPA年 径流预测[J]. 长江科学院院报,2016,33(1): 6-9.[Li Shenqi, Xiao Jingxi,Qin Guanghua,et al.Prediction of annual runoff based on SPA with calibration of quantitative standard coefficient[J].Journal of Yangtze River Scientific Research Institute,2O16,33(1): 6- 9.]   
[9]梁淑琪,王文圣,金菊良.农业干旱灾害风险模糊集对评价法及 其应用[J].水文,2019,39(1):1-6.[Liang Shuqi,Wang Wensheng,Jin Juliang.Assessment method based on fuzzy theory and set pair analysis and its application to agricultural drought disaster risk evaluation[J]. Journal of China Hydrology,2019,39(1):1-6.]   
[10] 周晓曦.气候变化和人类活动对和田河上游径流量的影响研究 [D].乌鲁木齐:新疆大学,2017.[Zhou Xiaoxi.The Impact of Climate Change and Human Activities on the Hotan River Runoff[D]. Urumqi: Xinjiang University,2017.]   
[11] 郭宏伟,徐海量,凌红波,等.和田河流域生态保护红线划定初 探[J].干旱地区农业研究,2017,35(6):235-243.[Guo Hongwei, Xu Hailiang,Ling Hongbo,et al.Preliminary studyon delimitation of ecological protection red line in Hotan River Basin[J].Agricultural Research in the Arid Areas,2017,35(6): 235-243.]   
[12] 董弟文,阿布都热合曼·哈力克,王大伟,等.近60年和田河源 流区径流特征及对气候变化的响应[J].中国水利水电科学研 究院学报,2018,6(6): 536-543.[Dong Diwen,Abdirahman Halik, Wang Dawei, et al. Characteristics of runoff and response to climate change in the Hotan River source area in recent six decades[J]. Journal of China Institute of Water Resources and Hydropower Research,2018, 6(6): 536-543.]   
[13]关东海,苏里坦·达尼尔汗.和田河流域生态敏感性分析[J].中 国水土保持科学,2013,11(增刊1): 41-47.[Guan Donghai, Sulitan Danierhan.Ecological sensitivity analysis of Hetian River Basin[J]. Science of Soil and Water Conservation,2013,11(Suppl. 1): 41-47.]   
[14] 郑威,于国荣,张代青.径流丰枯分类的投影寻踪-集对分析耦 合方法[J].水文,2020,40(2):17-22.[Zheng Wei,Yu Guorong, Zhang Daiqing. Annual runoff classfication based on projection pursuit and set pair analysis coupling method[J]. Journal of China Hydrology,2020,40(2): 17-22.]   
[15] 徐源蔚,李祚泳,汪嘉杨.基于集对分析的相似模型在地下水位 预测中的应用[J].水文,2015,35(6):6-10.[Xu Yuanwei,Li Zuoyong,Wang Jiayang. Similar forecast models of underground water level based on set pair analysis[J]. Journal of China Hydrology,2015,35(6): 6-10.]   
[16] 沈婕.梁忠民.王军.基干模糊集对分析的河湖水系连通风险评

估[J].水力发电,2020,46(11):1-5.[Shen Jie,Liang Zhongmin, Wang Jun.Risk assessment of river and lake system connectivity based on fuzzy set pair analysis[J]. Water Power,2O2O,46(11): 1- 5.]   
[17]王文圣,金菊良,丁晶,等.水资源系统评价新方法—集对评 价法[J].中国科学(E辑:技术科学),2009,39(9):1529-1534. [Wang Wensheng,Jin Juliang,Ding Jing,etal.A new approach to water resources system assessment: Set pair analysis method [J]. Science in China(Series E),2009,39(9): 1529-1534.]   
[18] 张志君,陈伏龙,龙爱华,等.基于模糊集对分析法的新疆水资 源安全评价[J].水资源保护,2020,36(2):53-58,78.[Zhang Zhijun, Chen Fulong,Long Aihua,et al.Xinjiang water resources security evaluation based on fuzzy set pair analysis[J].Water Resources Protection,2020,36(2): 53-58,78.]   
[19]胡惠兰,周亮广.淮河流域水资源短缺风险评估与时空分析[J]. 南水北调与水利科技,2017,15(6):59-65.[Hu Huilan,Zhou Liangguang. The risk assessment and space- time analysis of water resources shortage in Huaihe River Basin[J]. South-to-North Water Transfers and Water Science & Technology,2017,15(6):59- 65.]   
[20]Zhang Qiang,Xiao Mingzhong, Singh Vijay P. Uncertainty evaluation of copula analysis of hydrological droughts in the East River basin, China[J]. Global and Planetary Change,2O15,129:1-9.   
[21] 刘雪琴,李宁,吉中会,等.基于Copulas 函数的内蒙古强沙尘暴 特征及其灾害性研究[J].干旱区研究,2012,29(4):705-712. [Liu Xueqin,Li Ning,Ji Zhonghui,et al. Study on severe dust storms and their disasters in Inner Mongolia based on Copulas function[J].Arid Zone Research,2012,29(4): 705-712.]   
[22] 郑红星,刘昌明.南水北调东中两线不同水文区降水丰枯组合 性分析[J].地理学报,2000,55(5):523-532.[Zheng Hongxing, Liu Changming.Analysis on asynchronism-synchronism of region al precipitation in planned South-to-North water transfer areas[J]. Acta Geographica Sinica,2000,55(5):523-532.]   
[23] 黄领梅,沈冰.和田河汇入塔里木河径流演变及成因分析[J].水 资源与水工程学报,2012,23(2):26-28,32.[Huang Lingmei, Shen Bing.Analysis on runoff evolution and cause of Hotan River flowing into the Tarim River[J]. Journal of Water Resources and Water Engineering,2012,23(2): 26-28,32.]   
[24] 李成秀.昆仑山冰川和积雪变化的遥感监测[D].兰州:兰州大 学,2014.[Li Chengxiu.Remote Sensing Monitoring of Glacier and Snow Cover Changes in the Kunlun Mountain[D].Lanzhou: Lanzhou University,2014.]   
[25]王新.乌鲁瓦提水库建设对和田河的影响[J].水资源与水工程 学报,2014,25(1): 191-194.[Wang Xin. Study on influence of Wuluwati reservoir construction on Hotan River[J].Journal of Water Resources and Water Engineering,2014,25(1):191-194.]

# Evaluation and combination analysis of runoff in Hotan River, Xinjiang

HUANG Xing'， CHEN Fulong'， ZHAO Qi²， HE Chaofei'， LONG Aihua1,3 (1.Collegeof WaterConservancy&ArchitecturalEngineering,Shihezi University,Shihezi 832oo,Xinjiang,China; 2.Hydrology Bureau of Xinjiang Uygur Autonomous Region, Urumqi 83Oooo,Xinjiang, China; 3.State Key Laboratory of Simulation and Regulation of Water Cycle in River Basin,China Institute of Water Resources and Hydropower Research,Beijing 100O38, China)

Abstract: Studies on the different contributions of the runoffof the Hotan River in different time periods and synchronous-asynchronous encounter probability can provide a reference for the balance of industrial water, potable water,and water ecological environment and the improvement of water resource utilization effciency in the Hotan River Basin.Mean standard deviation and fuzzy set pair analysis methods are applied to evaluate the runoff wetness-drynessof the Yulong Kashi River and the Karakashi River.The possibility of inter-runoff water transfer and synchronous-asynchronous encounter probability is analyzed on the basis of fuzzy set pair method and copula function.The fuzzy set pair method reveals that the Yulong Kashi River had 10 and 26 wet and dry years,respectively.By comparison,the mean standard deviation method shows that the Yulong Kashi River had 15 and 20 wet and dry years,respectively.The Karakash River had 9 wet years.Furthermore,18 and 26 times in dry years were observed.In the fuzzy set pair method,the contribution ofannual runof and the influence of time history distribution are considered.Thus,evaluation results are more objective,and the difference in the probability of abundanceand dryness obtained bythe statistical method andthe copula function is the same as the data scale is related to the way of dividing the abundance and dryness.The results of the two methods demonstrate that the probability of asynchronous abundance and dryness is greater than that of synchronous abundance and dryness,and the two tributaries have good complementarity. They can more clearly describe the high and low runoff status and the characteristics of high and low runoff in the Hotan River.They can also provide a basis for making decisions on water resource dispatch in the Hotan River Basin.

Keywords: fuzzy set pair method; Copula function; mean standard deviation method; synchronous-asynchronous combined; Hotan River； Xinjiang