# 中短期任务的太阳质子事件通量预报研究

崔延美，师立勤，刘四清（中国科学院国家空间科学中心，北京100190)

摘要:太阳质子事件通量的预测对航天器的抗辐射加固设计和宇航员的出舱活动具有重要意义。针对1年以下的中短期航天任务,对太阳活跃年和太阳平静年分别统计了太阳质子事件和大于10MeV质子事件通量的发生概率,分析得到太阳质子事件通量分布基本符合对数正态分布。在此基础上,计算出了一定置信度下1年以下不同航天任务期内的质子事件通量分布，为执行中短期航天任务提供了太阳质子事件通量预测的依据。

关键词：太阳质子事件；太阳质子通量;航天任务;预报

中图分类号：P35 文献标识码:A 文章编号:1674-5825（2015)06-0597-06  
DOI:10.16329/j.cnki.zrht.2015.06.011

# Study on Forecast of Solar Proton Event Fluence during Short and Medium Term Missions

CUI Yanmei，SHI Liqin，LIU Siqing (National Space Science Center，Chinese Academy of Sciences，Beijing 1OO190，China)

Abstract: Forecasting the solar proton event fluence is very important to guarantee the safety of spacecrafts and astronauts.Within various periods less than 1 year，the occurrence probabilities of the solar proton events and their fluences were analyzed for solar active years and solar quiet years , respectively. It is found that the probability distributions of solar proton event fluence basically satisfy the log-normal distributions.Based on this，solar proton event fluence can be forecasted with some given confidence levels for diferent duration space missions ranging from 1 day to 365 days.

Key words: solar proton events； solar proton fluences； space mission; forecast

# 1引言

太阳质子事件是最具破坏性的空间天气现象之一。太阳上发生爆发活动时，会喷射出大量的高能带电粒子，它们以每秒几千、几万、甚至十几方千米的速度，最快十儿分钟就可以到达地球，使地球周围的高能带电粒子数量增加数千倍，甚至上万倍。由于绝大部分的粒子是质子，因此把这种事件称之为太阳质子事件。

太阳质子事件威胁着地球磁层和大气层外航天器的安全，使卫星上的电子元器件失效，还会对宇航员造成伤害，严重影响着人类的航天活动。

因此，在航天器的设计阶段或者在人类从事太空活动任务期间，都需要提前预知太阳质子事件的发生状况，以采取相应措施规避不必要的风险。然而，太阳质子事件是一种小概率事件，在其产生、加速机理还没完全确定的条件下，对其进行预报是十分困难的。

对于持续1年以上的航天任务，当前国际上应用比较普遍的质子事件通量模型有King模型[]、JPL 模型[2-3]、ESP[4-9]模型及 MSU模型[10]King 模型是建立的第一个太阳高能质子通量的经验统计模型。模型提出后取得了一定的成效，在很长一段时间被视作执行航天任务期间太阳质子积分通量的标准预报模型。但该模型只采用第20 太阳活动周的活跃年份数据,统计数据较少;且模型中对太阳黑子数和年均太阳质子累计通量呈线性相关的假设并不成立。JPL模型解决了King 模型存在的问题，它采用了近三个太阳活动周的太阳质子事件数据。在统计分析的基础上，JPL模型中应用了以下假设：太阳质子事件的发生是随机的，事件的爆发概率满足泊松统计分布；质子事件通量服从对数正态分布;太阳质子事件只发生在太阳活动周的连续7个活跃年中，且爆发频率一致。JPL模型对持续时间超过一年的航天任务能预报不同能量范围的质子积分通量水平。JPL模型的第二个版本JPL-91是目前公认较好的太阳质子事件长期预报模型，被推荐用于航天任务的设计规划[1]。ESP 模型采用了更充分的观测数据作为统计基础，不仅预测太阳质子积分通量，还能够给出最恶劣情况的太阳质子事件。MSU模型则是由莫斯科州立大学开发的，模型的一个版本《太阳高能粒子通量和峰值流量的概率模型第一部分：质子》已经是俄罗斯国家标准（GOSTR25645.165-2001），并被推荐为国际标准（ISO TS 15391）[12]。在总结吸取国外模型方法的基础上,李婷婷等人[13]利用人造卫星开始用于探测太阳高能粒子以来至2007年4个太阳活动周的数据,探讨了太阳活动性对质子事件发生概率的影响因素，评估了不同太阳活动水平下的质子通量，建立了新模型。

对于持续1年以下的中短期航天任务，国内外还没有建立起太阳质子事件通量预测的应用模型。在考虑太阳质子事件通量时，通常借鉴历史上曾经发生的最恶劣事件或者某一次普通质子事件进行分析，缺乏统计依据。本文将利用1967—2014年期间的太阳高能粒子观测数据，统计1年以下不同时间段中的太阳质子事件的发生，给出1—365天不同时间段的太阳质子事件和质子通量的发生概率。在此基础上，初步建立起中短期太阳质子事件通量模型，从而为中短期航天任务提供太阳质子事件通量预测的依据。

# 2 数据处理

我们采用的太阳质子数据主要来自OMNI网站[14]。OMNI网站整合了1967年以来的1小时精度的高能粒子观测数据，其中2005 年之前的数据来自IMP卫星的观测，2006年之后的数据来自GOES卫星的观测。本文选用的数据时间段为1967—2014年，能段为 $> 1 0 \mathrm { ~ M e V }$ 。缺值数据时，采用插值法进行补充。由于2001年—2003 年中有大段数据缺值，我们采用GOES卫星观测的数据[15进行了补充。

Feynman等人定义：当 $> 1 0 \ \mathrm { M e V }$ 的质子通量日均值大于1PFU时就认为发生了质子事件;当 $> 1 0 \ \mathrm { M e V }$ 的质子通量日均值连续两天低于1PFU 时则认为该质子事件结束。本研究中，由于要考虑的任务期会很短，因此不考虑质子事件的持续性，只对 $> 1 0 \mathrm { ~ M e V }$ 的质子通量日均值大于1PFU的时段进行太阳质子通量的计算，不满足该条件的时段则认为没有质子事件发生，太阳质子通量计为0。同时，我们将太阳活跃年和太阳平静年分别进行考虑。太阳活跃年指一个太阳活动周中极大年的前2.5年到后4.5年，活动周中的其余4个年份则为太阳平静年。在我们的数据统计样本中，考虑的太阳活跃年包括1967一1972年，1977—1983 年，1987—1993 年，1998—2004年，2010一2014年，共计32 年;其余16 年则为太阳平静年。总体来看，在太阳活跃年，质子事件发生天数多，太阳质子年积分通量高;在太阳平静年，质子事件发生天数少甚至是不发生，太阳质子年积分通量低（图1）。

![](images/7baf4229c09a126c823194b2622ebd63fbc373ebbdcdbc89227ad50acf2b8254.jpg)  
图1太阳质子事件发生与太阳活动周的关系 Fig.1The relationship between the production of solar proton events and the solar cycle

从上到下依次是太阳黑子数、太阳质子年积分通量、年质子事件发生天数随时间的变化。

# 3统计分析

从经验上来看，任务期越长，遭遇到质子事件的概率越大，可能遭遇到的太阳质子通量越高。而且，在太阳活跃年遭遇到质子事件的概率要高于太阳平静年。对样本中所有太阳活跃年和太阳平静年，我们分别统计分析了太阳质子事件和太阳质子通量的发生概率。

通过时间窗口滑动，可以得到不同任务期的质子事件发生状态和太阳质子积分通量。具体方法是：假定总样本天数为 $N$ ,当任务期为 $n ( \ 1 , 2 , 3 , 4$ ，$\cdots 3 6 5 )$ 天时，进行逐日的时间窗口滑动,滑动步长为 $^ { \mathbf { \alpha } _ { n - 1 } }$ ,可以得到 $N - n + 1$ 组任务期为 $n$ 天的样本。在任务期 $n$ 天内只要有质子事件发生就认定发生了质子事件，对 $N \mathrm { \Delta } n + 1$ 组样本中的太阳质子日积分通量进行累计，可得到 $n$ 天任务期的太阳质子通量的数值。在此基础上，统计 $N \not { p } \to 1$ 组样本中发生质子事件的样本所占地比例，就得到了 $n$ 天任务期中发生质子事件的概率;以太阳质子通量的数值为样本，统计超过以一系列通量值为阈值的样本所占比例,就得到 $n$ 天任务期中太阳质子通量的发生概率。例如，在23太阳活动周的活跃年1998—2004 年中，共有2557天，当任务期 $n = 2$ 天时，通过逐日的时间窗口滑动，得到 $N \not { – } n + 1 = 2 5 5 7$ $- 2 + 1 = 2 5 5 6$ 组样本，对这些样本分别进行太阳质子日通量的累计，就得到2556组任务期为2天的太阳质子通量的数值。其中，有504组样本有质子事件发生，则发生质子事件的概率为 $5 0 4 / 2 5 5 6 =$ 0.197。对太阳质子通量数据,若取 $1 0 ^ { 7 } \mathrm { p } \cdot \mathrm { c m } ^ { - 2 }$ 为阈值，则超过该通量值的太阳质子通量数据有226组,得到在2天的任务期中，发生超过 $1 0 ^ { 7 } \mathrm { ~ p } \cdot \mathrm { c m } ^ { - 2 }$ 质子通量的概率为： $2 2 6 / 2 5 5 6 = 0 . 0 8 8$ 9

图2分别展示不同任务期的质子事件发生率：（a)为太阳活跃年中太阳质子事件发生率随任务期时间的变化;（b)为太阳平静年中质子事件发生率随任务期时间的变化。由图可见，随着任务期时间的延长，太阳质子事件发生率逐渐增大。在相同时间长度的任务期中，太阳活跃年中的质子事件发生率要远高于太阳平静年。例如，任务期20天时，太阳活跃年中的质子事件发生率约为0.5;太阳平静年中的质子事件发生率仅约为0.15。在太阳活跃年中，当任务期为100 天时，太阳质子事件的发生率已超过了0.9，随着任务期时间的进一步延长，质子事件的发生率逐步趋近于1，并最终等于1。在太阳活动平静年，即使对于所考虑的最长任务期365天，太阳质子事件的发生率最大也仅为0.74。

![](images/5e561676cc63f3abcd5e6e8eb730c4a329a443c3007fa162aeb3cd808ef41e99.jpg)  
图2不同任务期的太阳质子事件发生率 Fig.2The production probability of solar proton $\mathbf { e - \partial }$ vents with different space mission periods from 1day to 365 days

红线是对黑色散点的指数拟合。

质子事件发生率随任务期时间的散点分布可由指数函数进行拟合，拟合公式如式(1)：

$$
y = A  { \mathrm { e } } ^ { x / t } + y _ { 0 }
$$

式中 $y _ { 0 } \setminus A \setminus t$ 分别为指数函数的偏移、幅度与衰减常数。对应太阳活跃年和太阳平静年，拟合参数的各取值见表1，拟合结果见图2。

表1太阳质子事件发生率进行指数拟合的参数 Table 1 The fitting parameter values of exponential functions for the production probability of solar proton events   

<html><body><table><tr><td>参数</td><td>太阳活跃年</td><td>太阳平静年</td></tr><tr><td>yo</td><td>0. 992</td><td>0.818</td></tr><tr><td>A</td><td>-0.822</td><td>-0.750</td></tr><tr><td>t</td><td>- 40.588</td><td>- 169.557</td></tr></table></body></html>

图3给出了在太阳活跃年和太阳平静年中，任务期时间分别为1天、2天、5天、10天、20天、30天、50天和100天时，太阳质子通量的发生概率。从图中可以看到，随着通量值的提高，发生大的太阳质子通量的概率逐渐降低。随着任务期的时间延长，以相同通量为阈值的太阳质子通量的概率逐渐增大。在相同的任务期中，太阳活跃年中的质子通量发生概率要远高于太阳平静年。如，在太阳活跃年，任务期为20天时，发生超过1$\times 1 0 ^ { 7 } \mathrm { ~ p } { \cdot } \mathrm { c m } ^ { - 2 }$ 质子通量的可能性为0.333,当通量阈值提高到 $1 \times 1 0 ^ { 9 } \ \mathrm { p } ^ { \bullet } \mathrm { c m } ^ { - 2 }$ 时,发生超过该阈值的太阳质子通量的可能性下降至0.055。当任务期为30天时,发生超过 $1 \times 1 0 ^ { 7 } \ \mathrm { p } ^ { \bullet } \mathrm { c m } ^ { - 2 }$ 和 $1 \times 1 0 ^ { 9 } \ \mathrm { p } ^ { \bullet } \mathrm { c m } ^ { - 2 }$ 的太阳质子通量的可能性分别为0.443和0.084，均高于任务期为20天的情况。当在太阳平静年,任务期为20天时,发生超过 $1 \times 1 0 ^ { 7 } \ \mathrm { p } ^ { \bullet } \mathrm { c m } ^ { - 2 }$ 和 $1 \times 1 0 ^ { 9 } \ \mathrm { p } \cdot \mathrm { c m } ^ { - 2 }$ 的太阳质子通量的可能性分别为0.102和0.018，均低于太阳活跃年任务期20天的情况。

值得注意的是，并非随着任务期时间的延长，发生大的太阳质子通量的概率可以一直增大下去。

到达一定通量阈值后，太阳质子通量的发生概率会存在一个截止值。如在太阳平静年，任务期时间从20 天到100 天,均未出现超过 $5 \times 1 0 ^ { 9 } \ \mathrm { p } ^ { * } \mathrm { c m } ^ { - 2 }$ 的太阳质子通量发生，见图3（b）。

# 4模型建立

在实际航天任务的评估中，通常要求给出一定置信度下任务期的质子通量。置信水平是以概率分布函数为基础的统计量。 $9 5 \%$ 的置信度意味着 $9 5 \%$ 的概率不会出现超过给定质子通量的情况，也就是只有 $5 \%$ 的可能出现超过给定质子通量的情况， $8 0 \%$ 的置信度也就意味着只有 $20 \%$ 的可能出现超过给定质子通量的情况。

对太阳活跃年和太阳平静年，在假定不同任务期时间1一365天中，我们分别比较了太阳质子通量分布与对数正态分布的关系。图4显示了太阳活跃年期间，假定任务时间为5天和100天时太阳质子通量的分布。图中纵轴是对数坐标下的质子通量，横轴是正态分布坐标下样本中通量小于给定值的比例，也就是质子通量与( $i \times 1 0 0 )$ /$( N + 1 )$ 的关系， $i$ 是某一样本通量值在所有样本

rrrtreeeitiriee 1.000 etreetrieeriie 1.000 1daymission 2day mission ---5daymission   
0.100 I1 ----10 day mission 0.100   
0.010 lu11 0.010 -50daymission 20daymssion = 100daymission   
0.001 L LI 1 0.001 uu u I   
106 107 108 109 1010 1011 106 107 108 109 1010 1011   
Cumulative SPE fluencecm² Cumulative SPEfluencecm-2 (a)太阳活跃年 (a） Solar active years   
U1111 1daymission 20daymission 2daymission 30daymission --5daymission 50daymission ---10 daymission 100 day mission   
0.100 0.100   
0.010 1111 010   
0.001 1 L1L Lul 111 1 0.001 1l Luul L 1   
106 107 108 109 1010 10 106 107 108 109 1010 1011   
CumulativeSPEfluencecm2 Cumulative SPEfluencecm2 (b）太阳平静年 (b)Solar quiet years

从最小到最大排序中的排序数， $N$ 是样本总数。如果太阳质子的通量分布符合对数正态分布，图中的数据将分布在一条直线上。从图中可以看出，多数数据分布在一条直线上，即太阳质子通量分布基本符合对数正态分布，即其概率密度函数为式(2):

$$
f ( \ F ) = \frac { 1 } { \sqrt { 2 \pi } \sigma } \mathrm { e x p } \ [ \frac { - \ ( \ \mathrm { l g } F - \mu ) \ ^ { 2 } } { 2 \sigma } \ : ]
$$

式中， $F$ 为任务期的太阳质子通量， $\sigma$ 是通量对数的标准偏差， $\mu$ 是通量对数的期望值。 $\sigma$ 和 $\mu$ 的数值都可以从太阳质子事件的通量分布图中拟合获得。在航天任务中，大的太阳质子通量更为关注，因此我们只对 $5 0 \%$ 概率以上的数据点进行了直线拟合。对于太阳活跃年和太阳平静年中的其他任务时间段，太阳质子通量分布也基本都符合对数正态分布。对应不同任务期， $\sigma$ 和 $\mu$ 的拟合取值见表2。

![](images/4256c00f3172f7bf3daf2aa7792ba92a1ec1d1b42ec8fa6cc1fe468681d7f91b.jpg)  
图4太阳活跃年中任务时间为5天和50天时太阳质子 通量的分布 Fig.4The distribution of solar proton fluences in solar active years   
图5任务期时间为50天时的质子通量概率分布 Fig.5The probability distribution of solar proton fluenceswith 50days space mission

表2太阳质子通量对数正态分布参数  
Table 2The parameter values of lognormal distribution for solar proton fluences   

<html><body><table><tr><td rowspan="2">任务期 时间/天</td><td colspan="2">太阳活跃年</td><td colspan="2">太阳平静年</td></tr><tr><td>0</td><td>μ</td><td>0</td><td>μ</td></tr><tr><td>1</td><td>1.81</td><td>4.00</td><td>2.37</td><td>1. 85</td></tr><tr><td>5</td><td>1.86</td><td>4.85</td><td>2.44</td><td>2.61</td></tr><tr><td>10</td><td>1. 79</td><td>5.48</td><td>2.35</td><td>3.33</td></tr><tr><td>20</td><td>1. 65</td><td>6.25</td><td>2.20</td><td>4.19</td></tr><tr><td>50</td><td>1.24</td><td>7.47</td><td>1.95</td><td>5.33</td></tr><tr><td>100</td><td>0.99</td><td>8.25</td><td>1.81</td><td>6.06</td></tr><tr><td>200</td><td>0.73</td><td>8.94</td><td>1.43</td><td>7.06</td></tr><tr><td>300</td><td>0.63</td><td>9.26</td><td>1.08</td><td>7. 76</td></tr></table></body></html>

利用该方法我们可以计算出在一定置信度下不同航天任务期的质子通量。图5中给出了太阳活跃年和平静年期间，任务期时间为50天时的质子通量概率分布。通过查找纵坐标对应曲线点的横坐标，可以得到某种置信度下的质子通量。如，在太阳活跃年，当任务期时间为50天时，要求给出$9 5 \%$ 的置信度下的质子通量。通过查找图5中对应任务期的质子通量概率曲线，可以得到纵坐标$1 \% \sim 9 5 \%$ 对应的曲线点横坐标为 $3 . 3 \times 1 0 ^ { 9 } \ \mathrm { p } ^ { \bullet } \mathrm { c m } ^ { - 2 }$ ，该通量值即为满足要求的质子通量。

1.000 1.000 50.pM   
0.010 0.010 G 心 03 .. 1 ..\*3++\* 111   
0.001 . ： 理 0.001 1 ： 来 106 107 10810°10101011 10107 10810°101°101 Fluence cm-2 (a)太阳活跃年 (b)太阳平静年 (a)Solaractiveyears (b)Solar quiet years

# 5结论

准确计算任务期内可能遭遇的太阳质子事件通量水平，可以为航天器的抗辐射加固设计和宇航员的出舱防护提供重要的依据。本文利用1967一2014年期间共48年的太阳高能粒子观测数据，统计分析了太阳质子事件的发生规律。针对持续1年以下的航天任务，我们对太阳活跃年和太阳平静年分别分析研究了在1一365天不同时间段中的太阳质子事件和大于 $1 0 \ \mathrm { M e V }$ 质子通量的发生概率。进而，通过对比太阳质子通量分布与对数正态分布的关系，得到太阳质子通量分布基本符合对数正态分布。以该关系为基础，我们计算出了一定置信度下，1年以下航天任务期内的质子通量分布，初步建立起了中短期太阳质子事件通量模型。

本文初步建立的太阳质子事件通量模型已经能够为航天器执行中短期任务提供太阳质子事件通量预测。不过，该模型只提供了 $> 1 0 \ \mathrm { M e V }$ 的太阳质子通量的分布，对于更高能量的质子通量分布并未涉及。在以后的工作中，将继续完善模型。值得注意的是：模型适用的任务期时间为1年以下，对1年以上航天任务期的太阳质子事件通量预测则需参考太阳质子通量的长期预测模型。

# 参考文献(References)

[1] King，J.H. Solar proton fluences for 1977-983 space missions[J]．Journal of Spacecraft and Rockets，1974,11(6): 401-409.   
[2] Feynman J，Armstrong TP,Dao-GibnerL，et al.New interplanetary proton fluence model[J].Journal of Spacecraft and Rockets，1990，27(4):403-410.   
[3] Feynman J,SpitaleG，WangJ，et al．Interplanetaryproton fluence model:JPL 1991［J]．Journal of Geophysical Research-All Series，1993，98(A8):13-281.   
[4] Xapsos M A，Summers GP，Shapiro P，et al.New techniques for predicting solar proton fluences for radiation effects applications[J]．Nuclear Science，IEEE Transactions on, 1996，43(6):2772-2777.   
[5] Xapsos MA，Summers GP,Burke EA.Extreme value analysis of solar energetic proton peak fluxes[J]．Solar Physics, 1998,183(1): 157-164.   
[6] Xapsos MA，SummersGP，Burke EA.Probability model for peak fluxes of solar proton events[J]．Nuclear Science, IEEE Transactions on，1998，45(6):2948-2953.   
[7］Xapsos M A，Summers G P,Barth JL，et al.Probability model for worst case solar proton event fluences［J].Nuclear Science，IEEETransactionson，1999，46(6)：1481-1485.   
[8] Xapsos MA，Summers GP，BarthJL，et al．Probability model for cumulative solar proton event fluences [J].Nuclear Science，IEEE Transactions on，2000，47(3)：486-490.   
[9] Xapsos MA，BarthJL，Stassinopoulos EG，et al.Characterizing solar proton energy spectra for radiation efects applications［J]．Nuclear Science，IEEE Transactions on，2000, $4 7 ( 6 ) : 2 2 1 8 { \ - } 2 2 2 3$ ：   
[10] Nymmik R A．Averaged energy spectra of peak flux and fluence values in solar cosmic ray events [C]//International Cosmic Ray Conference.1993, $3 ( 7 ) : 2 9$ ：   
[11] SheaMA，SmartDF，AdamsJH,etal.Toward a descriptive model of solar particles in the heliosphere[C]//Interplanetary Particle Environment.JPLPublication,1988，88-28.   
[12] ISO 15391.Space Environment（Natural and Artifical） Probabilistic model for fluences and peak fluxes of solar energetic particles:PartIProtons[S].2004.   
[13] 李婷婷，师立勤，刘四清．太阳质子通量模型研究[J]. 空间科学学报，2010，30(3)：205-210. Li tingting，Shi liqin,Liu siqing.Research on the Solar Proton Fluence Model[J],Chin.J. Space Sci.,2010,30(3): 205-210.(in Chinese)   
[14] NASA/Goddard Space Flight Center.Paths to Magnetic field, Plasma，Energetic particle data relevant to heliospheric studiesand resident at Goddard’s Space Physics Data Facility [EB/OL].2015.http://omniweb.gsfc.nasa.gov/   
[15] National Centers for Environmental Information.GOES Space Environment Monitor-Data Access [EB/OL].2015．http: // www.ngdc.noaa.gov/stp/satellite/goes/dataaccess.html