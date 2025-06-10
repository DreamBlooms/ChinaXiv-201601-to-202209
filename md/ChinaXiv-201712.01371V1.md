# 基于链接分析法对国内网络直播平台综合影响力的评价研究

史昱天」朱庆华」赵宇翔²陈晓威」(南京大学信息管理学院南京 210023)2(南京理工大学经济管理学院南京 210094)

摘要：【目的】探究如何利用链接分析法科学合理地对网络直播平台综合影响力做出客观评价。【方法】借助Google 和Alexa工具收集国内20家知名网络直播平台的相关链接数据，使用改进指标权重计算方法的灰色关联分析法，对这20家网站的综合影响力进行评价。【结果】获得网络直播平台影响力的综合排名，并依据此分析国内网络直播平台特征及现状。【局限】能获取全面数据的网络直播平台数量较少，故选取样本数量有限。【结论】中国当前网络直播平台的整体水平还不高，本文从链接角度出发，提出进一步提升平台影响力的方法策略。

关键词：链接分析 网络直播平台灰色关联分析影响力评价分类号：G350

# 1引言

网络直播(Webcast或NetworkBroadcast)这一概念的提出最早可以追溯到1995年，苹果公司成立网络直播小组对一场音乐会进行线上音频直播[1]。网络直播平台可以解释为能够稳定提供网络直播服务的网站或应用，然而受到网络带宽与传输速率的限制，网络直播平台在发展初期未能获得足够关注。随着近年来网络传输技术的日益成熟以及智能设备的普及，自2006年以来国外陆续出现了诸如 Twitch.tv(原Justin.tv)、Periscope、Younow、AfreecaTV等大型网络直播平台，其用户数量已达千万级，最大同时在线人数也均超过100万。而国内网络直播平台的出现相对较晚，在通讯工具"YY语音"的基础上，“YY直播"在2008 年上线运营，这也代表着国内第一家提供稳定网络直播服务的直播平台正式成立。在经历了短暂的发展瓶颈之后，自2014年初，中国网络直播产业在资本力量的强力推动下得到迅速发展，根据中国互联网络信息中心(CNNIC)发布的第39次《中国互联网络发展状况统计报告》显示，截至2016年12月，网络直播用户数量已经达到3.44亿，占网民总数的 $4 7 . 1 \%$ ，相较于2016年6月用户量增长近2000万，其中体育直播、游戏直播及真人聊天秀直播的用户使用率分别位于前三位，占比均超过了 $6 0 \% ^ { [ 2 ] }$ 。而艾媒咨询发布的《2016上半年中国在线直播市场研究报告》中预测未来数年网络直播仍将保持高速发展，到2018年网络直播用户数将达到4.6亿，平台数将超过300 家[3]。面对竞争日益激烈的网络直播市场，各大直播平台也采取各种措施提升网站影响力，进而提升用户流量和市场份额。

当前学界有关网络直播平台的研究还不多，部分学者选取当前较为成熟的直播平台作为案例研究的基础，总结其产品特色、运营模式、用户体验等方面的内容[4-7]，还有学者针对网络直播平台演化过程中出现的各种现象和问题，从内容质量、用户反馈等角度提出相应对策及建议[8-9]，整体而言国内外网络直播平台的研究还处于初级阶段。而对于网络直播平台影响力的统计排名大多基于内容丰富度或主播受关注度等融入评价者主观因素的定性评价方法，这种缺少客观量化数值的评价方法往往会因主播跳槽或直播内容更新而造成名次的大幅波动，并不能准确评估直播平台的真实实力。在情报学领域，针对网站的客观定量评价主要分为网站流量统计法和链接分析法两大类，常见的Alexa网站流量排名是将AlexaToolsBar嵌人到客户端浏览器中，从而监控用户访问的网站流量数据并对结果进行统计[10]。而网络链接分析法则是探究网站之间的链接关系及网站中网页信息资源丰富程度的重要研究手段，并能够从结构和内容上为网站的建设提供相应的服务对策，在发展过程中逐渐融合了搜索引擎、网络结构分析、社会网络分析等不同领域的研究方法，使其在网站分析和相应机构评价等方面获得了广泛的应用[11]。

目前国内外主要将网络链接分析方法用于大学网站评价、政府官网评估以及商业网站分析等方面[12-16],尚未发现采用链接分析法对网络直播平台影响力进行评价的相关研究。因此，本文将国内网络直播平台的链接数据作为客观反映平台实力方面的因素列人评价范围当中，对网络直播平台的链接结构及相应指标进行深入挖掘，采用改进指标权重计算方法的灰色关联分析法对网络直播平台综合影响力进行客观评价，获得基于链接角度的平台综合影响力排名。根据所得排名结果，从链接角度提出相应的建议及对策，提升网络直播平台影响力的整体水平，为网络直播平台的评估模式提供新的思路和研究方向。

# 2 研究方案设计

# 2.1 研究对象选取

笔者参考艾媒咨询发布的《2016上半年中国在线直播市场研究报告》中依据内容丰富度、主播知名度对国内网络直播平台的综合排名[3]，并结合 Alexa 网站的流量排名情况，共获得25家知名度较高的网络直播平台。由于部分网络直播平台，只提供移动端服务，无法获得基于网页链接的数据，故剔除此类直播平台。最终笔者选取20家网络直播平台作为链接分析的研究对象。

# 2.2 评价指标确定

链接分析法是运用搜索引擎或专业网站爬取工具，对网络中链接的数量、属性、对象、离散程度等数据进行爬取、分析，进而获取其内在规律的方法[17]。通过总结前人的研究成果中所选取的影响力评价指标并结合网络直播平台的链接特点，笔者选取9项指标作为综合评价网络直播平台影响力的依据，具体如表1所示。

表1链接指标含义及选取依据汇总表  

<html><body><table><tr><td>指标名称</td><td>指标含义</td><td>选取依据</td></tr><tr><td>网页数</td><td>使用搜索引擎检索到的某网站内的所有网页数</td><td>反映网站的整体规模大小及内容丰富程度[10]</td></tr><tr><td>总链接数</td><td>使用搜索引擎搜索到的链接到某网站的网页总数</td><td>反映网站的影响力与信息揭示程度的水平[17-18]</td></tr><tr><td>内链数</td><td>某网站范围内搜索得到的与该网站自身存在链接的 网页数</td><td>反映网站结构的完整度与层次性[19]</td></tr><tr><td>外链数</td><td>使用搜索引擎对某网站范围以外检索得到的指向该 网站的网页数</td><td>更加客观地反映网站质量及影响力[20-21]</td></tr><tr><td>网络影响因子</td><td>总链接数/网页数</td><td>网站被链的平均水平[22]</td></tr><tr><td>外部影响因子</td><td>外链接数/网页数</td><td>网站被外部网页链接的平均水平[23]</td></tr><tr><td>反链数</td><td>链接到所选网站的其他网站数量，若网页所属同一 网站，则只记录一次</td><td>从网站角度反映网站影响力大小[24]</td></tr><tr><td>DPV (Daily Pageviewer per Visitor)</td><td>单个用户一天时间内在该网站浏览网页数量的平均值客观上反映网站内容丰富度及用户参与度[25]</td><td></td></tr><tr><td>DTS (Daily Time on Site)</td><td>单个用户一天时间内在该网站停留的平均时间 (以秒作为单位)</td><td>反映网站内容对用户的吸引力水平[26]</td></tr></table></body></html>

# 2.3 研究工具选择

当前国内外网络链接分析的数据获取工具主要分为专业爬取工具和商业搜索引擎两类。诸如SocSciBot[27]、WebStat[28]、LinkDiscoverer[29]等专业爬取工具在一定程度上可以减少漏检、错检的发生，但往往会消耗大量时间资源和存储空间，且需要大量数据预处理工作，并不适用于网站规模较大的情境；而商业搜索引擎凭借其良好的检索效率、广泛的覆盖范围以及较高的稳定性等特点，逐渐得到众多研究者的青睐。前人研究中常用Google[10,24,26]、AltaVista[12,16]、必应[13]、百度[14]、All the web[15]等搜索引擎，但All theweb和AltaVista已在被Yahoo收购之后相继停止提供搜索服务，而必应和百度的网站覆盖度相对较低，结果的可信度不高。Google作为全球最大的搜索引擎，其涵盖范围广泛，收录网页众多，并且在一致性、稳定性方面均得到大多数学者的认可，故选择Google作为研究工具来获取20家网络直播平台的链接信息。结合Google搜索引擎的高级搜索命令和逻辑运算符使用规则，以斗鱼直播为例，确定了如表2所示的检索式来收集以上研究指标的具体数据。

表2搜索引擎链接查询检索式(以斗鱼直播为例)  

<html><body><table><tr><td>指标</td><td>检索式</td></tr><tr><td>网页数</td><td>site:www.douyu.com</td></tr><tr><td>网站总链接数</td><td>"www.douyu.com"</td></tr><tr><td>内部链接数</td><td>"www.douyu.com”site:www.douyu.com</td></tr><tr><td>外部链接数</td><td>网站总链接数-内部链接数</td></tr></table></body></html>

需要说明的是，国内有学者认为链接检索式应使用类似 site:douyu.com 而不包含www 的指令[16]，但由于douyu.com属于一级域名，此类检索式将会把该网站的二级域名诸如斗鱼社区(yuba.douyu.com)、斗鱼游戏(wan.douyu.com)等并不属于直播网站的链接加入检索结果，影响对其影响力评价的准确性，故本文选择二级域名www.douyu.com 构造检索式，仅针对提供直播服务的网站进行链接分析。而反链数、DPV、DTS三项指标则来源于Alexa 流量排名网站最近三个月的监测数据。

# 3数据处理

通过前述查询式获取的20家网络直播平台的链接数据(按照网页数降序排列)，如表3所示。

表3网络直播平台链接指标数据统计(按照网页数降序排列)  

<html><body><table><tr><td>网站名称</td><td>网页数</td><td>总链接数</td><td>内链数</td><td>外链数</td><td>网络影响</td><td>外部影响</td><td>反链数</td><td> DPV</td><td>DTS</td></tr><tr><td>YY LIVE</td><td>17 700 000</td><td>1 250 000</td><td>170 000</td><td>1 080 000</td><td>0.07</td><td>0.06</td><td>1210</td><td>4.18</td><td>243</td></tr><tr><td>六间房直播</td><td>7 850 000</td><td>119 000</td><td>73500</td><td>45500</td><td>0.02</td><td>0.01</td><td>948</td><td>6.10</td><td>831</td></tr><tr><td>触手直播</td><td>893000</td><td>68 600</td><td>51100</td><td>17 500</td><td>0.08</td><td>0.02</td><td>198</td><td>4.10</td><td>322</td></tr><tr><td>bilibili直播</td><td>420 000</td><td>290 000</td><td>164 000</td><td>126 000</td><td>0.69</td><td>0.30</td><td>2 945</td><td>9.00</td><td>633</td></tr><tr><td>熊猫直播</td><td>357000</td><td>425 000</td><td>363000</td><td>62 000</td><td>1.19</td><td>0.17</td><td>734</td><td>4.93</td><td>403</td></tr><tr><td>斗鱼直播</td><td>357 000</td><td>492 000</td><td>299 000</td><td>193 000</td><td>1.38</td><td>0.54</td><td>611</td><td>7.78</td><td>569</td></tr><tr><td>一直播</td><td>351000</td><td>36 900</td><td>25000</td><td>11 900</td><td>0.11</td><td>0.03</td><td>214</td><td>2.60</td><td>248</td></tr><tr><td>龙珠直播</td><td>349 000</td><td>149 000</td><td>65300</td><td>83 700</td><td>0.43</td><td>0.24</td><td>482</td><td>3.71</td><td>274</td></tr><tr><td>秀色秀场</td><td>340 000</td><td>38100</td><td>15 200</td><td>22 900</td><td>0.11</td><td>0.07</td><td>276</td><td>1.70</td><td>70</td></tr><tr><td>虎牙直播</td><td>273 000</td><td>288000</td><td>184000</td><td>104 000</td><td>1.06</td><td>0.38</td><td>712</td><td>4.10</td><td>301</td></tr><tr><td>酷狗直播</td><td>261000</td><td>66 900</td><td>30200</td><td>36 700</td><td>0.26</td><td>0.14</td><td>1 631</td><td>4.02</td><td>372</td></tr><tr><td>战旗直播</td><td>230 000</td><td>223 000</td><td>99 300</td><td>123 700</td><td>0.97</td><td>0.54</td><td>459</td><td>6.32</td><td>528</td></tr><tr><td>花椒直播</td><td>125 000</td><td>135 000</td><td>126 000</td><td>9000</td><td>1.08</td><td>0.07</td><td>236</td><td>5.60</td><td>359</td></tr><tr><td>美拍直播</td><td>105 000</td><td>159 000</td><td>105 000</td><td>54 000</td><td>1.51</td><td>0.51</td><td>567</td><td>3.17</td><td>208</td></tr><tr><td>CC直播</td><td>102 000</td><td>82 600</td><td>58100</td><td>24500</td><td>0.81</td><td>0.24</td><td>78</td><td>3.72</td><td>286</td></tr><tr><td>风云直播</td><td>51 300</td><td>78100</td><td>51300</td><td>26800</td><td>1.52</td><td>0.52</td><td>75</td><td>2.40</td><td>91</td></tr><tr><td>火猫直播</td><td>36 000</td><td>41 600</td><td>28 900</td><td>12 700</td><td>1.16</td><td>0.35</td><td>175</td><td>6.43</td><td>727</td></tr><tr><td>章鱼直播</td><td>20000</td><td>38300</td><td>20 000</td><td>18 300</td><td>1.92</td><td>0.92</td><td>1 235</td><td>6.50</td><td>304</td></tr><tr><td>全民TV</td><td>17 400</td><td>42 400</td><td>15 900</td><td>26500</td><td>2.44</td><td>1.52</td><td>284</td><td>2.00</td><td>191</td></tr><tr><td>KK直播</td><td>14000</td><td>10 600</td><td>3560</td><td>7040</td><td>0.76</td><td>0.50</td><td>89</td><td>3.70</td><td>194</td></tr></table></body></html>

可以发现，各个指标的排名状况差距很大，且每个指标的权重难以确定，所以很难直观测算不同直播平台影响力。

由于所列出的链接分析指标均为正向指标，其值的大小与影响力呈正相关关系，而邓聚龙等提出的灰色关联分析法适用于多指标的整体比较，能够查看各项指标的值所形成的数组与最优情况的吻合程度，其得分反映了与最优曲线的匹配程度，是有对比、有衡量的评价方法，能够综合各个指标的特性与优势[30-31],从而获得更为科学、客观、可靠的排序结果。因此，笔者选取灰色关联分析法对20家网络直播平台的9项指标进行综合排名，从而达到量化、序化的目的。其具体步骤如下：

(1）由于系统中各因素列中的数据可能因量纲不同而属于不同数量级，不便于后期处理时互相比较或在比较时难以得到正确结论。因此，在进行灰色关联度计算的过程中，一般要对数据进行无量纲化处理，以消除因数量级差异而导致的系统误差。笔者使用每个指标与该指标所在列总和相除的方法得到基于百分比的无量纲数值，结果保留小数点后4位有效数字。

(2）需要选取每个指标的对比标准，即参考数值，一般可以选择各指标的最优或最劣值作为参考，本文选择各指标中的最大值作为参考数值记作 $x _ { 0 } ( n )$ ， $n$ 为评价指标代号，所以各个指标的最大值分别为 $x _ { 0 } ( 1 )$ $x _ { 0 } ( 2 ) \cdots x _ { 0 } ( m ) , m$ 表示指标的个数，本文中 $\scriptstyle { m = 9 }$ 。各指标中的具体数值记为 $x _ { i } ( n ) ( 1 \ll i \ll 2 0 , i \in N )$ 。计算各指标中具体数值与其对应的参考值之间的差的绝对值，并从每项指标的差值中，分别选出最大值和最小值，记为max $| x _ { 0 } ( n ) - x _ { i } ( n )$ 和 $\operatorname* { m i n } \mid x _ { 0 } ( n ) - x _ { i } ( n ) \mid .$ 0

(3）从获得的 $\mathbf { \nabla } _ { m }$ 个指标的最大值与最小值集合中各自取出其中的最值，记为max max $\vert x _ { 0 } ( n ) - x _ { i } ( n ) \vert$ 和 min min $\mid x _ { 0 } ( n ) - x _ { i } ( n ) \mid$ ，所得数据如表4所示。

表4各指标数据灰色关联度  

<html><body><table><tr><td>域名</td><td>网页数</td><td>总链数</td><td>内链数</td><td>外链数</td><td>网络影响</td><td>外部影响</td><td>反链数</td><td>DPV</td><td>DTS</td></tr><tr><td>参考序列</td><td>0.5997</td><td>0.3121</td><td>0.1876</td><td>0.5217</td><td>0.1153</td><td>0.1532</td><td>0.2261</td><td>0.0978</td><td>0.1162</td></tr><tr><td>max| xo(n)-xi(n)|</td><td>0.5992</td><td>0.3094</td><td>0.1857</td><td>0.5183</td><td>0.1146</td><td>0.1526</td><td>0.2203</td><td>0.0793</td><td>0.1064</td></tr><tr><td>min| xo(n)- xi(n)l</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>max max|xo(n)-xi(n)|</td><td></td><td></td><td></td><td></td><td>0.5992</td><td></td><td></td><td></td><td></td></tr><tr><td>min min| x0(n)- xi(n)|</td><td></td><td></td><td></td><td></td><td>0</td><td></td><td></td><td></td><td></td></tr></table></body></html>

(4)计算关联系数：公式(1)分别计算每个比较序列与参考序列对应元素的关联系数，其中 $i { = } 1 , 2 , \cdots , 2 0$ $n { = } 1 , 2 , \cdots , \operatorname* { m } ; p$ 为分辨系数，在(0,1)内取值，若 $p$ 越小,关联系数间差异越大，区分能力越强，通常 $p$ 取0.5。

$$
\varsigma _ { i } \left( n \right) = \frac { \operatorname* { m i n } \operatorname* { m i n } \mid x _ { 0 } \left( n \right) - x _ { i } \left( n \right) \mid + p \times \operatorname* { m a x } \operatorname* { m a x } \mid x _ { 0 } \left( n \right) - x _ { i } \left( n \right) \mid } { \mid x _ { 0 } \left( n \right) - x _ { i } \left( n \right) \mid + p \times \operatorname* { m a x } \operatorname* { m a x } \mid x _ { 0 } \left( n \right) - x _ { i } \left( n \right) \mid }
$$

(5）计算加权系数：在已有研究中，大多学者是对各评价对象分析计算其各项指标与参考序列对应元素的关联系数的均值，以反映各评价对象与参考序列的关联关系，并将其称为关联序，如公式(2)所示。

$$
r _ { i } = \frac { 1 } { m } \sum _ { n = 1 } ^ { m } \varsigma _ { i } ( n )
$$

各个指标的重要程度并非完全相同，不同指标对最终影响力的作用水平存在差异，单纯计算算数平均值的方法会导致最终结果的误差，笔者认为需要对不同指标赋予相应的权重，从而提高关联序的客观性和准确性。本文采用计算信息熵值的方法对9项指标的权重进行评估，从而确定关联序的加权计算公式。在信息系统领域，信息熵代表的是信息无序程度，信息的熵值越大，信息的无序度越高，信息效用越低；相应地，如果信息熵值越小，信息无序度越低，信息的效用越高。因此，在权值确定过程中应用信息熵值判断信息效用的大小具备一定的合理性和可行性[2]。

按照以下步骤计算各项指标的信息熵值 $e _ { j }$ 。

$\textcircled{1}$ 假设每项指标中包含 $s$ 个样本，共有 $t$ 项指标，则初始样本的原始矩阵可以表示为 $X = \{ x _ { i j } \} _ { s \times t } ( 1 \ll i \ll s , 1 \ll$ $j \ll t )$ ，对原始数据集进行无量纲化处理，如公式(3)所示。

$$
y _ { i j } = \frac { x _ { i j } } { \displaystyle \sum _ { i = 1 } ^ { s } x _ { i j } } \quad 0 \ll y _ { i j } \ll 1
$$

得到标准化矩阵 $Y = \{ y _ { i j } \} _ { s \times t } ( 1 \ll i \ll s , 1 \ll j \ll t ) ~ ,$ 。

$\textcircled{2}$ 求出第 $j$ 项指标的信息熵值 $\boldsymbol { e } _ { j } ,$ 如公式(4)所示。

$$
e _ { j } = - k \sum _ { i = 1 } ^ { s } y _ { i j } \ln y _ { i j }
$$

其中， $k$ 的取值与样本数 $s$ 相关， $k = \left( \ln { s } \right) ^ { - 1 }$ 。本文中$k { = } 1 / \ln 2 0 \approx 0 . 3 3 4$ 。

$\textcircled{3}$ 由于信息熵 $e _ { j }$ 可以用来度量第 $j$ 项指标的数据效用价值，当完全无序时，熵值最大， $e _ { j } { = } 1$ ，此时 $e _ { j }$ 的数据对综合评价的效用值为零。因此，指标的信息效用价值取决于该指标的信息熵与1的差值hj，即h;=1-éj

$\textcircled{4}$ 利用信息熵计算指标权重，本质上是通过指标的信息效用价值来体现的。价值系数越大则说明该指标对评价的贡献度越高，相应的权重也应越大。将指标 $j$ 的权重记为$w ( j )$ ，可以用公式(5)表示。

$$
w ( j ) = \frac { h _ { j } } { \displaystyle \sum _ { j = 1 } ^ { t } h _ { j } }
$$

(6)计算加权关联序：将各项指标的关联系数乘以与其相对应的信息熵权值，并求和得到针对某一样本的加权关联序 $r _ { i } ^ { \prime }$ ，如公式(6)所示。

$$
r _ { i } ^ { \prime } { = } \sum _ { n { = 1 } } ^ { m } \varsigma _ { i } ( n ) { \times } w ( n ) 
$$

# 4结果与讨论

经过计算加权系数的处理步骤，笔者得到各个指标的权重值如表5所示。

表5各指标信息熵权重  

<html><body><table><tr><td>指标</td><td>信息熵权重</td></tr><tr><td>网页数</td><td>0.294</td></tr><tr><td>总链接数</td><td>0.103</td></tr><tr><td>内链数</td><td>0.043</td></tr><tr><td>外链数</td><td>0.185</td></tr><tr><td>网络影响因子</td><td>0.107</td></tr><tr><td>外部影响因子</td><td>0.158</td></tr><tr><td>反链数</td><td>0.070</td></tr><tr><td>DPV</td><td>0.014</td></tr><tr><td>DTS</td><td>0.026</td></tr></table></body></html>

可以看出，网页数、外链数和外部影响因子这三项指标的权重居于前三位，三者累加所占权重超过$60 \%$ ，说明这几项指标对于网络平台整体影响力的作用水平较高，而内链数、DPV、DTS的指标权重均不足 $5 \%$ ，说明这几项指标的数据对最终评价的影响程度较低。

通过计算每家网络直播平台的每项指标的关联系数，并将其分别与对应的信息熵权重相乘得到加权关联序，整理汇总得到如表6所示的经过标准化的统计数据以及按照加权关联序降序排名的情况。

表6标准化链接指标数据统计结果及加权关联序  

<html><body><table><tr><td rowspan="2">网站名称</td><td rowspan="2">网页数</td><td rowspan="2">总链 接数</td><td rowspan="2">内链数</td><td rowspan="2">外链数</td><td>网络</td><td>外部</td><td rowspan="2">反链数</td><td rowspan="2">DPV</td><td rowspan="2">DTS</td><td rowspan="2">加权 关联序</td></tr><tr><td>影响因子</td><td>影响因子</td></tr><tr><td>YY Live</td><td>0.5997</td><td>0.3121</td><td>0.0878</td><td>0.5217</td><td>0.0034</td><td>0.0061</td><td>0.0929</td><td>0.0454</td><td>0.0340</td><td>0.8444</td></tr><tr><td>bilibili直播</td><td>0.0142</td><td>0.0724</td><td>0.0847</td><td>0.0609</td><td>0.0327</td><td>0.0302</td><td>0.2261</td><td>0.0978</td><td>0.0885</td><td>0.5271</td></tr><tr><td>斗鱼直播</td><td>0.0121</td><td>0.1228</td><td>0.1545</td><td>0.0932</td><td>0.0652</td><td>0.0544</td><td>0.0469</td><td>0.0845</td><td>0.0795</td><td>0.5249</td></tr><tr><td>六间房直播</td><td>0.2660</td><td>0.0297</td><td>0.0380</td><td>0.0220</td><td>0.0007</td><td>0.0006</td><td>0.0728</td><td>0.0663</td><td>0.1162</td><td>0.5236</td></tr><tr><td>全民TV</td><td>0.0006</td><td>0.0106</td><td>0.0082</td><td>0.0128</td><td>0.1153</td><td>0.1532</td><td>0.0218</td><td>0.0217</td><td>0.0267</td><td>0.5159</td></tr><tr><td>熊猫直播</td><td>0.0121</td><td>0.1061</td><td>0.1876</td><td>0.0300</td><td>0.0563</td><td>0.0175</td><td>0.0563</td><td>0.0536</td><td>0.0563</td><td>0.5118</td></tr><tr><td>秀色秀场</td><td>0.0114</td><td>0.0094</td><td>0.0729</td><td>0.0110</td><td>0.0064</td><td>0.0094</td><td>0.0210</td><td>0.0185</td><td>0.0098</td><td>0.5072</td></tr><tr><td>章鱼直播</td><td>0.0007</td><td>0.0096</td><td>0.0103</td><td>0.0088</td><td>0.0906</td><td>0.0920</td><td>0.0948</td><td>0.0706</td><td>0.0425</td><td>0.5061</td></tr><tr><td>虎牙直播</td><td>0.0092</td><td>0.0719</td><td>0.0951</td><td>0.0502</td><td>0.0499</td><td>0.0383</td><td>0.0547</td><td>0.0445</td><td>0.0421</td><td>0.5000</td></tr><tr><td>战旗直播</td><td>0.0078</td><td>0.0557</td><td>0.0513</td><td>0.0598</td><td>0.0459</td><td>0.0541</td><td>0.0352</td><td>0.0687</td><td>0.0738</td><td>0.4986</td></tr><tr><td>美拍直播</td><td>0.0036</td><td>0.0397</td><td>0.0543</td><td>0.0261</td><td>0.0716</td><td>0.0517</td><td>0.0435</td><td>0.0344</td><td>0.0291</td><td>0.4950</td></tr><tr><td>风云直播</td><td>0.0017</td><td>0.0195</td><td>0.0265</td><td>0.0129</td><td>0.0720</td><td>0.0525</td><td>0.0058</td><td>0.0261</td><td>0.0127</td><td>0.4860</td></tr><tr><td>火猫直播</td><td>0.0012</td><td>0.0104</td><td>0.0149</td><td>0.0061</td><td>0.0547</td><td>0.0355</td><td>0.0134</td><td>0.0698</td><td>0.1016</td><td>0.4855</td></tr><tr><td>酷狗直播</td><td>0.0088</td><td>0.0167</td><td>0.0156</td><td>0.0177</td><td>0.0121</td><td>0.0142</td><td>0.1252</td><td>0.0437</td><td>0.0520</td><td>0.4848</td></tr><tr><td>花椒直播</td><td>0.0042</td><td>0.0337</td><td>0.0651</td><td>0.0043</td><td>0.0511</td><td>0.0072</td><td>0.0181</td><td>0.0608</td><td>0.0502</td><td>0.4827</td></tr><tr><td>龙珠直播</td><td>0.0118</td><td>0.0372</td><td>0.0337</td><td>0.0404</td><td>0.0202</td><td>0.0241</td><td>0.0370</td><td>0.0403</td><td>0.0383</td><td>0.4824</td></tr><tr><td>CC直播</td><td>0.0035</td><td>0.0206</td><td>0.0300</td><td>0.0118</td><td>0.0383</td><td>0.0241</td><td>0.0060</td><td>0.0404</td><td>0.0400</td><td>0.4777</td></tr><tr><td>KK直播</td><td>0.0005</td><td>0.0026</td><td>0.0018</td><td>0.0034</td><td>0.0358</td><td>0.0506</td><td>0.0068</td><td>0.0402</td><td>0.0271</td><td>0.4766</td></tr><tr><td>触手直播</td><td>0.0303</td><td>0.0171</td><td>0.0264</td><td>0.0085</td><td>0.0036</td><td>0.0020</td><td>0.0152</td><td>0.0445</td><td>0.0450</td><td>0.4725</td></tr><tr><td>一直播</td><td>0.0119</td><td>0.0092</td><td>0.0129</td><td>0.0057</td><td>0.0050</td><td>0.0034</td><td>0.0164</td><td>0.0282</td><td>0.0347</td><td>0.4681</td></tr></table></body></html>

# 44 数据分析与知识发现

为观察不同关联度得分的整体分布情况，以0.1作为区段划分标准，整理上述结果得到表7。

表7关联度分布  

<html><body><table><tr><td>区间</td><td>数量</td><td>所占比例</td><td>累积量</td><td>累积所占比</td></tr><tr><td>0.7及以上</td><td>1</td><td>5%</td><td>1</td><td>5%</td></tr><tr><td>(0.6, 0.7]</td><td>0</td><td>0</td><td>1</td><td>5%</td></tr><tr><td>(0.5, 0.6]</td><td>7</td><td>35%</td><td>8</td><td>70%</td></tr><tr><td>(0.4, 0.5]</td><td>12</td><td>60%</td><td>20</td><td>100%</td></tr></table></body></html>

可以看出，只有1家网络直播平台的加权关联度值在0.7以上，没有在0.6至0.7的中高分段的直播平台，有19家网络直播平台的加权关联度值集中在0.4至0.6区间内。由此可见，结合信息熵值的灰色关联分析法在评估网络直播平台影响力时能够发现实力突出的平台，但对中间部分的平台区分程度较低。这种情况与灰色关联分析的计算原理有关，对极端值的反映较为明显，而对中间值的敏感程度较低。

从网络直播平台的具体案例来看，其中 YY Live的关联度值最高，达到0.8444，远高于其他网站的加权关联序得分，YYLive作为国内第一家正式直播平台自创立至今已有接近10年的时间，其网页数、总链接数等指标的排名均位居前列，相比于近期成立的直播平台，YYLive拥有更为丰富的内容资源，可以吸引众多外部链接的导入。排名二、三位的bilibili 直播和斗鱼直播，都是近年来陆续上线的直播平台,bilibili直播的反链数与DPV数值均排在该指标的首位，依托bilibili视频网站的用户资源，以二次元文化作为主打直播内容，其弹幕直播的形式也给用户带来了更为互动化的观看体验；斗鱼直播的网络影响因子和外部影响因子两项指标的排名较高，说明在相同网页数量的条件下，能够获得更多的链接导人。斗鱼直播的前身是AcFun生放送直播，在2014年正式创立并将平台重新定位为以提供游戏直播服务为主，在经过数轮融资之后，平台规模、主播数量、直播丰富程度等都得到大幅度提升，开始向多元化的泛娱乐类直播平台转型，其整体实力和网络综合影响力增长迅速。

笔者注意到，影响力排名中最后两位的分别是触手直播和一直播，基于网络链接维度的综合影响力较低，各项指标的得分均不佳，这除了与平台成立时间较晚有关之外，还与其商业定位有密切联系。虽然触手直播和一直播都提供PC端的网页直播服务，但触手直播是主要针对手机游戏直播的平台工具，其主要用户集中在智能移动终端，如智能手机、平板电脑等，移动App观看直播依靠其便捷性、易用性的特征优势已被更多用户所接受；一直播在与新浪微博达成合作关系之后，依托社会化媒体的庞大用户基础，逐渐将直播重心转移到与移动端社交媒体的合作直播方面，而其Web端的链接结构整体水平与其他网络直播平台还有较大差距。

# 5讨论与建议

从网站综合影响力评价角度来看，除个别实力明显高于其他直播平台外，中国网络直播平台的网络影响力整体水平不高且较为均衡，少有具备突出实力的平台，网络直播产业还处于发展初级阶段，未来仍有较大的提升空间。笔者结合上述影响力评价结果，从链接角度出发为我国网络直播平台今后建设发展、平台影响力提升等方面提出以下建议。

(1）丰富直播内容，提升内部链接质量。

网络直播平台作为用户生成内容(UGC)的即时展示媒介，每时每刻有大量主播通过录制设备实时上传直播内容，这在一定程度上保证了各类直播内容的持续稳定更新，能够满足不同用户的观看需求，但同时也应注意到，过于庞杂的直播内容导致导航偏差、分类模糊、更新不及时等问题的出现。而从最终的排名结果中也可以发现，综合排名靠后的直播平台如KK直播、一直播的网页数、内链数也都相对较少，整体而言网站内部建设水平较低。因此，网络直播平台应成立监管网站内部链接的专业团队，在保证直播内容质量的同时，优化网站跨频道、跨主播的内部链接，减少不必要的多级跨越，确保网页之间的层级结构合理规范，为吸引外部链接、提升直播平台的影响力打下基础。

(2）建立合作机制，增加友情链接数量。

当前各大网络直播平台为获得更高的用户数量及用户依赖度，竞争十分激烈，许多平台不惜花费重金从竞争对手方引入高人气的当红主播，虽然在短期内能够提升用户数量，然而也带给网络直播平台巨大的经济压力，不利于平台的稳定和长期发展。平台之间良好的合作关系能够帮助网络直播平台行业建立有效的秩序和规范，从链接角度来说，一些大型平台相互之间建立友情链接，能够为访问者提供跨平台的便捷渠道，同时也可以提升各自的网站流量，进而提高整体的网络影响力，形成迭代优化的效果。而对于中小平台，如果能够建立与规模较大平台之间的友情链接，有助于提升自身的网站可见度，增加外部链接的数量。

(3)结合社交媒体，扩大平台传播范围。

近年来各类社交媒体伴随智能移动终端的普及而被人们所了解，社交媒体用户数量增长迅速，一些网络直播平台也与社交媒体开展了深度合作，如国外的Twitter添加了Periscope的视频直播功能、新浪微博开放了一直播的接入端口。而从链接角度来看，网络直播平台的运营者可以利用微博、贴吧、BBS论坛等社交媒体平台发布关于直播的通知公告，通过在评论或发帖的内容中加入直播链接URL地址的形式增加用户接入渠道，也可以利用网络主播的“网红效应”，以有奖转发、有奖评论等方式吸引粉丝参与，在社交网络中迅速传播链接地址，获取更高的用户流量和用户关注度。由此看来，与社交媒体的结合不仅可以提高网站外部链接数量，提升网站在整个网络环境下的权值水平，而且可以为网络直播平台的推广宣传提供有力帮助。

# 6结语

本研究基于链接分析方法探索国内网络直播平台的综合影响力，根据咨询机构的调研报告及流量排名情况，选取20家当前受关注程度较高的网络直播平台作为研究对象，之后通过Google和Alexa获取各网站的链接数据作为原始数据，采用结合信息熵值的灰色关联分析法，最终获得了各个网站的排名情况。通过对结果的分析讨论，笔者从链接角度为直播平台影响力的提升提出相关意见和建议，对完善网络直播平台的评价体系，促进直播平台的推广扩展具有一定的借鉴意义和参考价值。

# 参考文献：

[1] Wikipedia.Webcast[EB/OL].[2017-01-12]．https://en. wikipedia.org/wiki/Webcast.   
[2] 中国互联网络信息中心．中国互联网络发展状况统计报告 [R/OL].[2017-01-23].http://www.cnnic.net.cn/hlwfzyj/hlwxzbg/ hlwtjbg/201701/t20170122_66437.htm.(China Intermet Network Information Center. The 33rd Statistical Report of Chinese Internet Development [R/OL]. [2017-01-23]. http://www. cnnic.net.cn/hlwfzyj/hlwxzbg/hlwtjbg/201701/t20170122_66 437.htm.)   
[3]艾媒咨询.2016上半年中国在线直播市场研究报告[R/OL]. [2017-01-13]. htt://www.iimedia.cn/45009.html. (iiMedia Research.China's Live Webcast Market Report in the First Half Year of 2016[R/OL]. [2017-01-13]. http://www. iimedia.cn/45009.html.)   
[4]陈洪鑫．打造网络直播平台的五大策略—以 PPTV 第一 体育为例[J]．传媒，2016(7)：62-63．(Chen Xinhong.The Five Strategies to Build a Webcast Platform:An Example of PPTV the First Sport[J].Media,2016(7): 62-63.)   
[5]Pires K,Simon G. YouTube Live and Twitch:A Tour of User-generated Live Streaming Systems[C]//Proceedings of the 6th ACM Multimedia Systems Conference.ACM,2015: 225-230.   
[6]Zhang C，Liu J.On Crowdsourced Interactive Live Streaming: A Twitch.tv-based Measurement Study $[ \mathrm { C } ] / \AA$ Proceedings of the 25th ACM Workshop on Network and Operating Systems Support for Digital Audio and Video. ACM,2015: 55-60.   
[7]Dimaria-Ghalili R A,Ostrow L,Rodney K.Webcasting:A New Instructional Technology in Distance Graduate Nursing Education[J]. Journal of Nursing Education,2005,44(1):11.   
[8]张旻．热闹的"网红"：网络直播平台发展中的问题及对策 [J]．中国记者,2016(5):64-65.(Zhang Min.Lively KOL: Problems and Countermeasures in the Development of Webcast Platform[J]. Chinese Journalist,2016(5): 64-65.)   
[9]王松．我国网络直播平台发展中的问题与对策研究[J]．企 业改革与管理,2016(15):52-58.(Wang Song.Research on the Problems and Countermeasures in the Development of China'sWebcast Platform [J]. Enterprise Reform and Management, 2016(15): 52-58.)   
[10]陈太洋，任全娥．中外企业网站的链接分析与网络影响力 评价[J]．情报理论与实践，2008，31(4):614-619.(Chen Taiyang,Ren Quane.Link Analysis and Influence Evaluation of Chinese and Foreign Corporate Websites [J]. Information Studies: Theory & Application,2008,31(4): 614-619.)   
[11]文庭孝，王尧，杨雅惟，等．网络链接分析应用研究综述 [J]．图书情报知识，2011(4):84-91，96.(Wen Tingxiao, Wang Yao, Yang Yawei, et al. Review on the Application of Web Linkage-analysis [J]. Document Informaiton & Knowledge, 2011(4): 84-91, 96.)   
[12]陈太洋．我国大学图书馆网站链接的实证分析——以中国 “211工程"高校为例[J]．图书馆杂志,2007(3):43-49.(Chen Taiyang. Demonstration Analysis of University Library Website Link in China[J].Library Journal,2007(3): 43-49.)   
[13]陈悦，商慧子．中国省级政府网站的共链分析[J]．图书情 报工作，2011,55(11):130-133.(Chen Yue,Shang Huizi. Co-link Analysis of Chinese Provincial Government Websites [J].Library and Information Service,2011,55(11):130-133.)   
[14]李宗富，张向先．基于链接分析法的我国省级档案局网站 影响力评价研究[J]．情报科学，2016，34(5):142-147.(Li Zongfu, Zhang Xiangxian. Study of the Provincial Archives Bureau Website Impact Evaluation in China Based on the Link Analysis Method[J]. Information Science,2016,34(5): 142-147.)   
[15] 黄贺方，孙建军．基于链接分析的网站评价实证研究- 以四大门户网站为例[J].情报杂志，2011，30(1):74-77. (Huang Hefang,Sun Jianjun. Study on Web Evaluation Based on Link Analysis: A Case Study of the Four Portals[J]. Journal of Intelligence,2011,30(1):74-77.)   
[16] 汪传雷，汪涛，刘新妍．基于链接分析的 C2C 电子商务网 站分析—以三大C2C 购物网站为例[J]．现代情报，2012, 32(1):38-43.(Wang Chuanlei， Wang Tao,Liu Xinyan. Analysis on the C2C E-commerce Websites Based on Link Analysis[J]. Journal of Modern Information,2012,32(1): 38-43.)   
[17] 董江山，胡吉祥，邱均平．链接分析法及其应用[J]．情报 科学,2004,22(9):1081-1084,1099.(Dong Jiangshan,Hu Jixiang，Qiu Junping.Link Analysis Method and Its Application[J]. Information Science,2008,22(9):1081-1084, 1099.)   
[18]李芳玲，华薇娜．从湖北省高校网站评价看链接分析指标 的应用[J]．大学图书情报学刊，2016,34(1):107-113.(Li Fangling,Hua Weina.Application of Link Analysis Index in the Evaluation of University Websites in Hubei Province[J]. Journal of Academic Library and Information Science,2016, 34(1): 107-113.)   
[19]李江，殷之明．链接分析研究综述[J]．大学图书馆学报, 2008,26(2):51-58. (Li Jiang, Yin Zhiming.A Review on Link Analysis[J]. Journal of Academic Libraries,20o8,26(2): 51-58.)   
[20] 邓中华，孙建军，李江．国外链接指标研究综述[J]．情报 科学,2008,26(7): 1116-1120. (Deng Zhonghua, Sun Jianjun, Li Jiang.Review of Foreign Link-based Indicators [J]. Information Science,2008,26(7): 1116-1120.)   
[21]刘雁书，方平．利用链接关系评价网络信息的可行性研究 [J]．情报学报，2002,21(4):401-406.(Liu Yanshu,Fang Ping.Study on the Reliability of Link Popularity in Web Information Evaluation[J].Journal of the China Society for Scientific and Technical Information,2002,21(4): 401-406.)   
[22] Ingwersen P.The Calculation of Web Impact Factors[J]. Journal of Documentation,1998,54(2): 236-243.   
[23] Noruzi A.The Web Impact Factor: A Critical Review[J].The Electronic Library,2006,24(4):490-500.   
[24] 赵宇翔，彭希羨，孙建军．链接分析视角下国内 NGO 网 站综合影响力评价研究[J]．情报学报，2014，33(5): 549-560.(Zhao Yuxiang， Peng Xixian， Sun Jianjun. Evaluation on the Influence of Non-Government Organization Websites in China Based on Link Analysis[J].Journal of the China Society for Scientific and Technical Information,2014, 33(5): 549-560.)   
[25]程慧平．链接分析指标在大学网站排名评价中的有效性分 析[J]．信息资源管理学报,2012(3):46-51.(Cheng Huiping. Link Analysis Indexes Effectiveness Analysis on Evaluating University WebsitesRank [J].Journal of Information Resources Management, 2012 (3): 46-51.)   
[26]米云，金英伟．基于链接分析法的出版社网站评价研究[J]. 现代出版,2012(3):39-44.(Mi Yun,Jin Yingwei.Evaluation on the Websites of Publishing House Based on Link Analysis[J].Modern Publishing,2012(3): 39-44.)   
[27]Jeyashree S,Ravichandran R.Perspectives of Webometric Tools for Web Impact Assessment Studies:A Review[J]. International Journal of Library Science,2013,2(2): 43-48.   
[28]段宇锋．网络信息资源被链接次数的频数分布模型[J]．情 报科学,2005,23(10):1495-1498.(Duan Yufeng.Model of Frequency Distribution on the Hyperlinked Number of Network Information Resources [J]. Information Science, 2005,23(10): 1495-1498.)   
[29] Yang B,Qin J.Data Collection System for Link Analysis[C]// Proceedings of the 3rd International Conference on Digital Information Management. IEEE,2008:247-252.   
[30] 邓聚龙．灰色系统综述[J]．世界科学，1983(7)：1-5.(Deng Julong.Grey System Review[J]. World Science,1983(7): 1-5.)   
[31］谭学瑞，邓聚龙．灰色关联分析：多因素统计分析新方法 [J]．统计研究,1995(3):46-48.(Tan Xuerui,Deng Julong. Grey Correlation Analysis: New Methods for Multiple Factors Statistics[J]. Statistics Reseach,1995(3): 46-48.)   
[32]王靖，张金锁．综合评价中确定权重向量的几种方法比较 [J]．河北工业大学学报，2001，30(2):52-57.(Wang Jing, Zhang Jinsuo. Comparison of Several Methods for Determining Weight Vector in Comprehensive Evaluation[J].Journal of Hebei University of Technology,2001,30(2):52-57.)

# 作者贡献声明：

# 支撑数据：

史昱天：提出研究思路，撰写论文;  
朱庆华：论文最终版本修订;  
赵宇翔：修订论文;  
陈晓威：采集、清洗、分析数据。

支撑数据由作者自存储,E-mail:njusyt@qq.com。[1]史昱天.Link_data.xlsx.通过Google 搜索引擎和Alexa网页排名工具搜索得到的20家网络直播平台链接数据.[2]史昱天．Grey_analysis.xlsx.灰色关联分析法处理数据中间过程及结果.

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

收稿日期:2017-05-08  
收修改稿日期:2017-06-01

# Evaluating the Influence of China's Webcast Platforms Based on Link Analysis

Shi Yutian1Zhu QinghualZhao Yuxiang² Chen Xiaowei1 1(School of Information Management, Nanjing University,Nanjing 210023, China) 2(School of Economics and Management, Nanjing University of Science & Technology,Nanjing 210094, China)

Abstract: [Objective] The article tries to objectively evaluate the influence of China’s webcast Platforms with the help of link analysis.[Methods]First,weused Google search engine and Alexa.com tocolect the link data of 2O popular webcast platforms in China.Then,we examined their influence with a modified grey correlation analysis method. [Results] We obtained the ranking of 20 webcast platforms and analyzed their characteristics.[Limitations] We could notobtain comprehensive data from the webcast platforms and the smaple size was limited.[Conclusions]The oveal level of currnt webcast platform is not so good.This article proposes strategies to increasethe influence of webcast platforms.

Keywords: Link Analysis Webcast Platform Grey Relational AnalysisInfluence Evaluation