# 塔里木河干流上游洪水演进规律分析与数值模拟

王远见},²，董其华1,²，周海鹰（1黄河水利委员会黄河水利科学研究院,河南郑州450003；2水利部黄河水沙重点实验室,河南郑州450003；3塔里木河流域管理局,新疆库尔勒841000)

摘要：塔里木河流域的水文特性在过去几十年内发生了深刻变化,源流的年径流总体增加，而干流发生量级洪水的频次与洪峰流量也有显著增长，干流防洪压力不断增长。通过从洪水传播时间、削峰率、耗水率三个方面对塔里木河干流上游(肖夹克一英巴扎)分河段展开系统分析，揭示了干流上游洪水传播的一般规律;在此基础上构建了一维水沙演进的数学模型,模型通过 2010 年洪水验证后，模拟了2017年干流洪水演进过程，模拟结果精度较高，显示了该数学模型的合理性和广阔的应用前景。研究成果不但从科学上揭示了中亚代表性内陆多沙河流的洪水特性，对于塔里木河干流的防洪管理与洪水资源化利用也有重要意义。

关键词：洪水演进规律；水沙演进；数学模型；塔里木河干流中图分类号：P333 文献标识码：A 文章编号

塔里木河是我国最长的内陆河流，位于天山南麓，从西往东流经塔克拉玛干大沙漠北缘。塔里木河干流从阿克苏河、叶尔羌河及和田河等三河汇合的肖夹克至台特玛湖，河道全长 $1 \ 3 2 1 \ \mathrm { k m }$ ,流域面积$1 . 7 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,属平原型河流[1]。在三源流中,阿克苏河、和田河是塔里木河干流发生洪水的主要来源,而且以阿克苏河为主[2]。王远见等[3]对过去50多年塔里木河“三源一干”各站点年径流的趋势变化分析表明，塔里木河源流的年径流量总体增加，尤以阿克苏河径流显著增加；而干流发生量级洪水的频次和洪峰流量也有显著增长[4]。这与整个新疆地区近年来的径流变化趋势是相符的[5-7]

塔里木河干流的洪水问题一直受到国内外学者的研究和关注。王玉峰等[8]曾就1956—2000 年塔里木河干流洪水特性，包括洪水传播时间、消峰率和耗水量等进行了系统研究，并采用1957—2000年资料拟合了塔里木河干流各河段年耗水量与来水量关系式;张建岗[9]等采用2005—2013年资料拟合了各河段年河道综合损失与来水量关系式;丛振涛等[10]建立了塔里木河干流河道水均衡模型，分析了塔里木河干流沿程水量的消耗和演变规律。但2001年实施了塔里木河生态抢救工程，2002年以后又开展了塔里木河干流近期治理工程,在边界条件和水沙条件都发生显著变化后，针对塔里木河干流洪水传播时间及洪峰削减率等定量分析与研究仍较缺乏。而对耗水量而言，目前沿程耗水分析成果在时空尺度上无法满足洪水计算与预报的需要。

数值分析方法对于了解洪水演进过程具有其独特的优势和特色。在数值模拟方面，蒋艳["]尝试应用MIKE11模型中的HD水动力学模块、NAM降雨径流模块和FF实时校正模块建立了阿克苏河流域洪水预报模拟系统，并对阿克苏河流域1999年夏季洪水预报过程进行模拟;李园园等[12 基于CCHE2D河流泥沙模型，对乌斯满河口上下 $2 . 6 ~ \mathrm { k m }$ 的河段汛期泥沙冲淤和河床变形问题进行二维数值模拟；王亚军[13]以塔里木河上游的洪泛区为研究对象，利用洪水水文水力学数学模型和GIS 洪水仿真模型模拟了塔里木河上游的洪水演进过程和实现了洪水的可视化管理。总体上，塔河流域由于地处西北内陆干旱区域，观测条件差，数据收集困难，边界条件复杂，沿程分散耗水巨大[14],汛期来沙较多且河床冲淤变化显著[15]等因素,针对汛期水沙演进的数值模拟研

究仍处于起步阶段。

本文拟应用资料分析方法，揭示塔里木河干流分河段洪水传播时间、削峰率和耗水率的时空演变规律,并在此基础上建立一维水沙演进数学模型，实现对干流洪水演进的准确模拟。本文研究结果将为塔里木河干流防洪安全与洪水资源利用工作的开展提供坚实的技术支撑。

# 研究区概况

塔里木河干流(图1)全程可分为三段，上游由三源流交汇处的肖夹克至英巴扎，全长 $4 9 5 ~ \mathrm { k m }$ ，沿程有阿拉尔、新其满、英巴扎三个控制性水文站；中游由英巴扎至恰拉，全长 $3 9 8 ~ \mathrm { k m }$ ,沿程有乌斯满、恰拉两个控制性水文站；下游由恰拉至台特玛湖，全长$4 2 8 ~ \mathrm { k m }$ ,沿程有大西海子水文站。其中阿拉尔站和新其满站1956年设立，为国家基本水文站，测验项目较全，资料系列较长;英巴扎站从1992年开始观测，有20a以上的观测资料，其余乌斯满、恰拉、大西海子等站的数据资料均不满 $1 0 \mathrm { ~ a ~ }$ 。考虑资料的连续性和匹配性，本研究重点针对塔里木河干流的上游阿拉尔一新其满、新其满一英巴扎的洪水演进过程展开规律分析和数值模拟。

# 2洪水演进规律分析

# 2.1洪水传播时间及削峰率

2.1.1 阿拉尔—新其满河段对1958—2010年阿拉尔站洪峰流量大于 $8 0 0 ~ \mathrm { m } ^ { 3 } \cdot \mathrm { s } ^ { - 1 }$ 的 60 场洪水进行统计，点绘了阿拉尔洪峰流量与阿拉尔一新其满河段洪峰传播时间（图2）、河段洪峰削峰率（图3）之间的关系。

由图2可知，阿拉尔一新其满河段洪峰传播时间集中在 $1 . 5 \sim 3 \mathrm { ~ d ~ }$ ,该类洪水大多为尖瘦型洪水，洪峰明显；一少部分洪峰传播时间在3.5～5d,该类洪水均为矮胖型洪水，洪峰判断有一定的困难；且传播时间有随新其满洪峰流量增大而增加的趋势。2005年前后阿拉尔一新其满河段洪峰传播时间没有明显区别。

由图3可以看出，阿拉尔一新其满河段洪峰削峰率集中在 $1 5 \% \sim 4 8 \%$ 之间,平均 $24 \%$ 。2005年前后阿拉尔一新其满河段洪峰削峰率没有明显区别。

2.1.2 新其满—英巴扎河段因英巴扎站1992 年才正式设立水文站，现有资料年份较少，仅能找到上述60 场洪水中对应的16 场洪水（1996—2010 年）。对这16场洪水进行统计，点绘了新其满洪峰流量与新其满一英巴扎河段洪峰传播时间及相应洪峰削峰率之间的关系（图4、图5）。

![](images/7e426144aee9ae181a1120d1da442a644bfbb6ac567c9607a376648173f9aa6d.jpg)  
图1塔里木河流域图Fig.1Map of the Tarim River Basin

![](images/d0cc904c5baf889bd9b693b74cefe42b2f53ad0da043c1e233698c697ddbb100.jpg)  
图2阿拉尔一新其满河段洪峰传播时间与来水关系 Fig.2Relationship between the travel time of peak flood and inflow from Aral to Xinqiman

![](images/48113f1a54c4f5b56d35c0fa310c05885ed4b5813b5a2c5b4232865d85f35134.jpg)

可以看出，新其满一英巴扎河段洪峰传播时间集中在 $2 \sim 1 0 \mathrm { ~ d ~ }$ ，且传播时间显著有随新其满洪峰流量增大而增加的趋势；相应洪峰削峰率集中在$3 1 . 5 \% \sim 6 4 . 4 \%$ 之间,平均 $5 0 \%$ 。

![](images/529a246529ebeb526f37459916f330dde2e3d7664591875fd690b3f81f0d8197.jpg)  
图3阿拉尔一新其满河段洪峰削峰率与来水关系 Fig.3Relationship between the peak clipping rate and inflow from Aral to Xinqiman   
图4新其满一英巴扎河段洪峰传播时间与来水关系 Fig.4Relationship between the travel time of peak flood and inflow from Xinqiman to Yingbazha

![](images/320470a6ed2af3227e5ba4772187eebd2329ddb91964157894d8eaf04aa2373c.jpg)  
图5新其满一英巴扎河段洪峰削峰率与来水关系 Fig.5Relationship between the peak clipping rate and inflow from Xinqiman to Yingbazha

# 2.2 耗水率

本次采用2005—2016年资料统计了阿拉尔一新其满各河段年汛期各月耗水量与来水量关系（表1)。从表中可以看出，阿拉尔一新其满、新其满一英巴扎2个河段6月和7月耗水量分别占来水量的$3 6 \% \sim 5 6 \%$ ,8月和9月2河段耗水率均较前两个月有所下降，降至 $2 3 \% \sim 2 8 \%$ ，这可能与河道前期干涸、前期来水中渗漏比较严重、农业灌溉引水及生态引水比例高有关。此外，两河段引水占来水量比例在 $6 . 4 \% \sim 1 0 . 8 \%$ 之间，各月份引水量占来水比例变化不大。

表1塔里木河干流阿拉尔一水量损失比例(2005—2016)   
Tab.1 Water lossratio from Aral to Yinbazha in 2005 to 2016   

<html><body><table><tr><td>项目</td><td>月份</td><td>阿拉尔一新其满 新其满一英巴扎</td></tr><tr><td>河道长度／km</td><td>189</td><td>258</td></tr><tr><td>耗水率／%</td><td>6</td><td>44.0 55.5</td></tr><tr><td>(耗水/来水)</td><td>7 36.1</td><td>44.0</td></tr><tr><td rowspan="7">引水占来水比例／% (2010—2015)</td><td>8 23.0</td><td>27.8</td></tr><tr><td>24.4</td><td>25.9</td></tr><tr><td>9 6 10.8</td><td>7.0</td></tr><tr><td>7</td><td>8.7 9.0</td></tr><tr><td>8 6.4</td><td>7.0</td></tr><tr><td>9</td><td></td></tr><tr><td>8.3</td><td>8.8</td></tr></table></body></html>

# 3模型的建立及求解

# 3.1 模型原理

本研究构建的一维水沙演进数学模型选用的描述水流与泥沙运动的基本方程为[16]：

水流连续方程

$$
\frac { \partial _ { i } } { \partial t } + \frac { \partial Q _ { i } } { \partial x } - q _ { L i } = 0
$$

水流运动方程

$$
\frac { \partial Q _ { i } } { \partial t } + \frac { \partial } { \partial x } \bigg ( \alpha _ { 1 i } \frac { Q _ { i } ^ { 2 } } { A _ { i } } \bigg ) + \alpha _ { 2 i } \frac { Q _ { i } } { A _ { i } } q _ { L i } + g A _ { i } \bigg ( \frac { \partial Z _ { i } } { \partial x } + \frac { Q _ { i } ^ { 2 } } { K _ { 1 } ^ { 2 } } \bigg ) = 0
$$

泥沙连续方程

$$
\frac { \partial ( \ Q _ { i } S _ { i } ) } { \partial t } + \frac { \partial ( \ A _ { i } V _ { i } S _ { i } ) } { \partial x } + \ \sum _ { j = 1 } ^ { m } K _ { 1 i j } \alpha _ { \ast i j } f _ { 1 i j } \ \times
$$

$$
b _ { i j } \omega _ { s i j } ( f _ { 1 i j } S _ { i j } - S _ { * i j } ) - S _ { L i } q _ { L i } = 0
$$

河床变形方程

$$
\frac { \partial Z _ { _ { b i j } } } { \partial t } - \frac { K _ { _ { 1 i j } } \alpha _ { \ast i j } } { \rho ^ { \prime } } \omega _ { s i j } ( f _ { _ { 1 i j } } S _ { _ { i j } } - S _ { \ast i j } ) = 0
$$

式(1）\~（4)中，角标 $\mathbf { \chi } _ { i }$ 为断面号；角标 $j$ 为子断面号， $m$ 为子断面数; $Q$ 为流量； $A$ 为过水面积; $\mathbf { \Phi } _ { t }$ 为时间； $x$ 为沿流程坐标； $Z$ 为水位； $K$ 为断面流量模数;$\alpha _ { 1 }$ 为动量修正系数； $q _ { L } , S _ { L }$ 分别为河段单位长度侧向入流量及相应的含沙量; $\omega _ { s }$ 为泥沙浑水沉速； $s$ 为含沙量； $\boldsymbol { S } _ { \ast }$ 为水流挟沙力； $\gamma _ { 0 }$ 为淤积物干容重； $\rho ^ { \prime } =$ $1 / \gamma _ { 0 } ; b$ 为断面宽度; $\boldsymbol { Z } _ { b }$ 为断面平均河床高程； $\smash { \{ f _ { 1 } ^ { \prime } \} }$ 为泥沙非饱和系数； $K _ { 1 }$ 为附加系数; $\alpha _ { \ast }$ 为平衡含沙量分布系数。

模型计算采用非耦合解法[17],方程（1）、（2）、(3)采用四点隐式差分格式离散[17-18],式(4)采用差分格式离散。

# 3.2模型验证与计算

3.2.1边界条件模型验证与计算范围从塔里木河上游的阿拉尔水文站一下游的阿西木耶，干流河道长度约 $8 6 7 ~ \mathrm { k m }$ ,但由于实测资料的缺乏，故本文仅比对阿拉尔一英巴扎河段的模拟结果。初始地形及初始床沙级配采用2011年汛前大断面，床沙组成资料采用2016年采集数据，根据断面形态对初始地形概化。选取2010年洪水作为模型模拟验证洪水，2017年洪水作为模型模拟应用洪水。

# 3.2.2 2010年洪水验证

（1）洪水概况2010 年塔里木河干流阿拉尔站共发生2场洪水，第1场洪水发生于6月份，最大流量 $8 8 2 ~ \mathrm { m } ^ { 3 } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ (6月21日16时);第1场洪水发生于7\~9月，该场洪水历时 $2 \ \mathrm { m o n }$ ,洪量大,洪峰高0 $\mathrm { ~ 1 ~ } 9 4 0 \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ s ~ } ^ { - 1 } .$ ）,呈现多峰型。洪水从阿拉尔传到新其满尚能保持峰形，当演进至英巴扎时洪水过程发生坦化，至乌斯满洪水流量降至 $1 6 0 \sim 2 0 0 ~ \mathrm { ~ m } ^ { 3 }$ ：s-左右(图6)。

（2）模型计算概况模型计算时段取为2010年6月1日8时 $\sim 1 0$ 月9日8时，共 $1 3 0 \mathrm { ~ d ~ }$ 。

对2010年沿程引水进行统计，阿拉尔一新其满河段实测引水量占阿拉尔水量 $6 \%$ ，与2010—2015年平均值相当;新其满一英巴扎河段实测引水量占新其满水量 $14 \%$ ，较 2010—2015 年平均值偏大。根据前述对2005—2015 年耗水率及引水比例的统计成果，阿拉尔一新其满河段8月多年平均耗水率为 $23 \%$ ,新其满一英巴扎河段多年平均河损率为$2 7 . 8 \%$ 。考虑两河段引水所占来水的比例，则2010年阿拉尔一新其满和新其满一英巴扎两河段总的耗水率分别取为 $23 \%$ 和 $3 5 \%$ （图7）。

（3）模型验证结果图8点绘了新其满和英巴扎2010年实测与模拟洪水过程。可以看出，新其满计算的洪水过程其峰形与传播过程与原型都是非常相似的，仅在局部存在一些误差;英巴扎计算洪水过程中峰现时间与实测基本一致；2010年2场洪水中，新其满、英巴扎洪峰计算值与实测值基本一致（表2）。其中1号洪峰计算值与实测值的差值相对实测值的比例较2号洪峰大，这可能是计算过程中采用同一耗水率造成的。2010 年1号洪峰比2号洪峰偏小,而相应1号洪峰实测耗水率是偏大的，而本次计算过程中采用洪水期平均耗水率,相对1号洪峰实测耗水率是偏小的，造成1号洪峰计算值较实测值偏大。

![](images/6cbc8cd2d12f34ff6e1b688de772ea3625aaec8637ea007f2fcfc886e165fbce.jpg)  
图62010年塔里木河干流洪水过程Fig.6Flood process in the mainstream of TarimRiver in 2010

![](images/2bbc1e602e6a1d5ebb08a82befa48ded618a32dd2de37a3bfab4df2b5a0edd00.jpg)  
图7“2010 洪水"阿拉尔一英巴扎河段耗水量

![](images/db2ebe2ac61c695db678c789397f67d8d146dad4b3499940dd5202473123eba1.jpg)  
Fig.7Water consumption from Aral to Yingbazha in 2010

表2计算结果与实测结果对比  
Tab.2Calculated results and measured results in 2010   

<html><body><table><tr><td>水文站</td><td>项目</td><td>1号洪峰／m·s-1</td></tr><tr><td rowspan="2">新其满</td><td>实测</td><td>663</td></tr><tr><td>计算</td><td>739</td></tr><tr><td rowspan="4">英巴扎</td><td>计算一实测</td><td>76</td></tr><tr><td>实测</td><td>379</td></tr><tr><td>计算</td><td>490</td></tr><tr><td>计算一实测</td><td></td></tr></table></body></html>

# 3.2.32017年洪水模拟计算

（1）洪水概况2017年塔里木河干流洪水来的比较早，截止到2017年7月26日，塔里木河干流共发生3个洪水过程(图9）。5～6月份塔里木河干流洪水主要由阿克苏河洪水组成，7月份塔里木河洪水由阿克苏河和和田河洪水共同组成。7月洪水是2017年度最大洪水过程。

由图9可知，本次洪水阿拉尔从7月3日开始上涨,至7月12 日阿拉尔洪峰达到 $\mathrm { ~ 1 ~ } 0 1 0 \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ ，随后有所降落，至7月17日洪水再次上涨，至7月20日阿拉尔洪峰达到 $1 ~ 2 6 0 ~ \mathrm { m } ^ { 3 } \cdot \mathrm { s } ^ { - 1 }$ ,在7月24日略有回落,随后洪水再次上涨至 $\mathrm { ~ 1 ~ } 2 0 0 \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ 后再次回落。

![](images/01a03445b15af84e35bfabdf75271dfbd4cd863d8a7b4233f4692ac790d08b79.jpg)  
图8“2010 年洪水"洪水演进对比Fig.8Comparison of flood routing in 2010  
图92017年塔里木河干流洪水实测流量过程  
Fig.9Flood process in the mainstream of Tarim River in 2017

（2）模型计算概况模型计算时段取为2017年5月1日8时至7月26日8时，共 $8 7 \mathrm { ~ d ~ }$ 。根据2017年7月27\~8月1日洪水查勘，阿拉尔一新其满河段耗水率 $20 \%$ 左右，考虑2017年洪水较多年平均提前 $1 \ \mathrm { m o n }$ ,本次阿拉尔一新其满河段耗水率采用前述8月多年平均耗水率 $23 \%$ ；相应新其满一英巴扎河段耗水率也采用前述8月多年平均耗水率$2 7 . 8 \%$ （图10）。

（3）模型计算结果图11点绘了新其满和英巴扎2017年实测与模拟洪水过程。可以看出，计算的洪水过程中峰现时间与实测基本一致;2017年洪水中，新其满、英巴扎洪峰计算值与实测值基本一致（表3）。

![](images/30484e4f908a6bb144d604931ccd4cac4f89e262833a613e9d9db1ed81766967.jpg)  
图10“2017 洪水"洪水阿拉尔一英巴扎河段水量损失 Fig.10Water consumption from Aral to Yingbazha in 2017

![](images/2609987dcdccb1360c7712460965e327a78073f9ba9d4e5f9e0cf48159af0ba8.jpg)  
图11“2017洪水"洪水演进对比  
Fig.11Comparison of flood routing in 2017

表3计算结果与实测结果对比  
Tab.3Calculated results and measured results in 2017   

<html><body><table><tr><td>水文站</td><td>项目</td><td>洪峰／m·s-1</td></tr><tr><td rowspan="3">新其满</td><td>实测</td><td>1100</td></tr><tr><td>计算</td><td>1150</td></tr><tr><td>计算一实测</td><td>50</td></tr><tr><td rowspan="3">英巴扎</td><td>实测</td><td>706</td></tr><tr><td>计算</td><td>750</td></tr><tr><td>计算一实测</td><td>44</td></tr></table></body></html>

# 4结论

本文对1958—2010 年阿拉尔站洪峰流量大于$8 0 0 ~ \mathrm { m } ^ { 3 } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ 的 60 场洪水开展了统计分析,分析了洪峰传播时间、洪峰削峰率和耗水率的时空演变规律，并在此基础上构建了一维水沙演进数学模型，实现了塔河干流洪水演进过程的模拟，得到如下结论：

（1）阿拉尔一新其满洪峰传播时间，尖瘦型洪水为1.5\~3d，但矮胖型洪水为3\~5d，削峰率大多$1 5 \% \sim 4 8 \%$ 之间，平均 $2 4 \%$ ;新其满一英巴扎洪峰传播时间 $2 \sim 1 0 \mathrm { ~ d ~ }$ ,削峰率为 $3 1 . 5 \% \sim 6 4 . 4 \%$ ,平均$5 0 \%$ 。

(2）阿拉尔一新其满、新其满一英巴扎2个河段6月、7月耗水量分别占来水量的 $3 6 \% \sim 5 6 \%$ ,8月和9月降至 $2 3 \% \sim 2 8 \%$ ,两河段引水占来水量比例在 $6 . 4 \% \sim 1 0 . 8 \%$ 之间，各月份引水量占来水比例变化不大。

（3）本研究开发的塔里木河干流一维水沙演进数学模型在2010年、2017年两个汛期得到了成功应用，显示了该模型在塔河流域开展应用的广泛前景。

# 参考文献(References)

[1］新疆维吾尔自治区人民政府.塔里木河流域近期综合治理规划报告[M].北京：中国水利水电出版社，2002：7-12.［Xin-jiangUygur Autonomous Region People’s Government.Recentcomprehensive management plan report of Tarim River Basin[M].Beijing:China Water Power Press,2002:7-12.]

[2］雷志栋,甄宝龙,尚松浩,等.塔里木河干流水资源的形成及其利用问题[J].中国科学：E辑,2003,33（5）：473-480.［LEIZhidong,ZHEN Baolong,SHANG Songhao,etal.Formation and u-tilization of aterresources in mainstream of Tarim River[J].Sci-ence in China:SeriesE,2003,33(5):473-480.]

[3］王远见,江恩慧,郜国明,袁峡.塔里木河三源一干近50a汛期 径流时空分布规律研究[C]//中国水力发电工程学会水文泥 沙专业委员会2017年学术研讨会，长沙，2017.［WANGYuanjian,JANG Enhui,GAO Guoming,et al.Research on spatial-temporal distribution of flood period of three source rivers and mainstream of Tarim River in recent 5O years[C]//China Hydroelectric Engineering Society Hydrology and Sediment Specialized Committee 2017 Symposium,Changsha,2017.]

[4］陈亚宁,徐长春,杨余辉,等.新疆水文水资源变化及对区域气候变化的响应[J].地理学报，2009，64（11）：1331－1341.[CHEN Yaning,XU Changchun,YANG Yuhui,etal.Hydrologyand water resources variation and its responses to regional climatechange in Xinjiang[J].Acta Geographica Sinica,2009,64（11）：1331 -1341.]

[5］王秋香,崔彩霞,姚艳丽.新疆不同区域洪灾受灾面积变化趋势及多尺度分析［J].地理学报，2008，63（7）：769-779[WANGQiuxiang,CUI Caixia,YAO Yanli,etal.Variation trendsand multi-scale analysis of flood affected area in various regions ofXinjiang.Acta Geographica Sinica,2008,63（7） :769-779.]

[6]姜逢清，胡汝骥,杨跃辉.新疆洪灾时间序列突变及其气候原因分析［J].冰川冻土，2004，26（6）：674－681.［JIANGFengqing,HURuji,YANG Yuehui.Abrupt change in the time se-quences of flood disaster in Xinjiang and its possible climatic rea-sons[J].Journal of Glaciology and Geocryology,2OO4,26（6）：674 -681.]

[7］周海鹰,沈明希,陈杰,等.塔里木河流域60a来天然径流变化 趋势分析[J」.干旱区地理，2018，41（2）：221-229.［ZHOU Haiying,SHEN Mingxi,CHENJie,et al.Trendsof natural runoffs in the Tarim River Basin during the last 6O years[J].Arid Land Geography,2018,41（2）:221-229.]

[8］王玉峰,李伟佩,宋伟华,等.塔里木河干流径流演变规律分析研究报告［R].黄河勘测规划设计有限公司，2007：10.［WANGYufeng,LIWeipei,SONGWeihua,et al.Analysis ofrunoff evolu-tion law in the mainstream Tarim River[R].Yellow River Engi-neering Consulting Co.,Ltd.,2007:10.]

[9]张建岗,刘新华,等.塔里木河流域"四源一干"河道损失规律

研究[R].塔里木河流域管理局、新疆大学,2015.［ZHANG Jiangang,LIU Xinhua,et al. Runoff loss of Four Source Rivers and Mainstream of Tarim River[R].Tarim River Basin Administration,Xinjiang University,2015.]   
[10］丛振涛,周海鹰,雷志栋,等.塔里木河下游输水过程的分析与 模拟[J].水科学进展,2003,14（3）;276-279.[CONG Zhentao ZHOU Haiying LEI Zhidong,et al.Analyses and simulations of the water transfer from the lower Tarim River[J].Advances in Water Science,2003,14(3）:276-279.]   
[11］蒋艳.塔里木河流域水文过程分析与模拟[D].北京:中国科 学院地理科学与资源研究所,2006.［JIANG Yan.Analysis and simulation of the hydrological process in the Tarim River Basin [D].Beijing: Institute of Geographic Sciences and Natural Resources Research,CAS,2006.]   
[12］李园园,牧振伟,徐乐,等.塔里木河流域乌斯满河段平面二维 水沙数值模拟［J].水电能源科学,2015，（10)：72-75.［LI Yuanyuan,MU Zhenwei,XU Le,et al.Two dimensional numerical modeling for flow and sediment transport in Uthman Reaches of Tarim River Basin[J].Water Resources and Power,2O15,（10）： 72 -75.]   
[13］王亚军.基于GIS 的二维洪泛区洪水过程仿真研究［J].水利 科技与经济,2016,22（6）:99-102.[WANG Yajun.Simulation of flood process in two dimensional flood based on GIS[J].Water Conservancy Science and Technology and Economy,2016,22(6): 99 - 102.]   
[14］苟树生,张雄文,王彦国,等.近50 年来塔里木河干流水量、水 质及耗水分析[J].干旱区研究,2010,27(6）:861-870.[GOU Shusheng,ZHANG Xiongwen,WANG Yanguo,et al. Analysis on runoff volumes,water quality and water consumption of the Tarim River in recent 50 years[J].Arid Zone Research,2010,27（6）: 861 -870.]   
[15］王延贵,胡春宏.塔里木河干流引水灌溉及其对河道冲淤的影 响[J].水利水电技术,2003,34（1）:48-51.[WANG Yanguo, HU Chunhong. Study on irrigation diversion and its influence on Tarim River[J]. Water Resources and Hydropower Engineering. 2003,34(1) :48 -51.]   
[16］张红武,黄远东,赵连军,等.黄河下游非恒定水沙数学模型— I:模型方程与数值方法[J].水科学进展,2002,13（3)：265- 270.[ZHANG Hongwu,HUANG Yuandong,ZHAO Lianjun,et al. A mathematical model for steady sediment transport in the Lower Yellow River—I:Model equations and numerical method[J].Advances in Water Science,2002,13(3）:265-270.]   
[17］谢鉴衡.河流模拟[M].北京：水利电力出版社,1990.［XIE Jianheng.River simulation［M].Beijing：China Water& Power Press,1990. ]   
[18]WU Weiming. Computational river dynamics[M]. London：Taylor & Francis Group,2007.

# Analysis and numerical simulation of flood routing of upper reaches of the Mainstream of Tarim River

WANG Yuan-jian1²，DONG Qi-hua1.²，ZHOU Hai-ying (1Yellow River Institute of Hydraulic Research,Zhengzhou 45ooO3,Henan,China; 2Key Laboratoryof Yellow River Sediment of the Ministryof Water Resources,Zhengzhou 45oo03,Henan,China; 3Xinjiang Tarim River Basin Management Bureau,Korla 841ooo,Xinjiang,China)

Abstract：The hydrological characteristics of Tarim River Basin,Xinjiang,China have undergone profound changes in the past decades.Theannual runoffof the origin increased while the frequency and the peak discharge of magnitude floods in the main stream increased significantly,which lead to the increase of flood protection pressure. In 2001,the Tarim river ecological rescue project was implemented,and the recent governance project of the Tarim River main stream was carried out after 2OO2.After the boundary conditions and water and sediment conditions changed significantly,there is stillalack of quantitativeanalysisandresearch onthe floodtravel timeand peakclipping rate of the mainstream Tarim River.This paper systematicallyanalyzed flood characteristics in the upper reach of the mainstream of the Tarim River（Xiaojiake-Yingbazha reach）from three aspects:Flood travel time, peak-clipping rate and water consumption rate,which revealed the general law of flood transmission in the upper reaches of the main stream.The travel time of peak flood is gathered in $1 . 5 - 5 \mathrm { ~ d ~ }$ from Aral to Xinqiman,and the average peak-clipping rate is $24 \%$ .The travel time of peak flood is gathered in $2 - 1 0 \mathrm { ~ d ~ }$ from Xinqiman to Yingbazha,and the average peak-clipping rate is $50 \%$ .The water consumption rate is gathered in $3 6 \% - 5 6 \%$ from Xinqiman to Yingbazha,and the average peak-clipping rate is $50 \%$ . The water consumption rates are $3 6 \% \sim 5 6 \%$ at Aral-Xinqiman reach and Xinqiman-Yingbazha reach in June and July.In Augustand September,the water consumption rates of the two reaches are gathered in $23 \% - 2 8 \%$ . A one-dimensional mathematical model of water and sediment evolution is constructed.Afterthe verification period using flood events in 2010,the model simulated the main streamflood evolution processin 2O17and the simulation results with high accuracy was obtained when the flow peak of Aral exceeds $8 0 0 ~ \mathrm { m } ^ { 3 } \cdot \mathrm { s } ^ { - 1 }$ ,which indicated the rationality and wide application prospect of the model. The results of thisstudy havescientificallyrevealed the floodcharacteristics of therepresentative inland sandyrivers in Central Asia,and have important significance for flood-control managementand flood-water resources utilizationof the Tarim River.

Key words:flood routing；water and sediment evolution；numerical model；main stream of Tarim River