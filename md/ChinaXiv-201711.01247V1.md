# O2O服务用户分类的潜在类别分析与应用

刘平峰王贝雷洁(武汉理工大学经济学院武汉 430070)

摘要：【目的】实现O2O(Online to Ofline)模式下较为客观精准的用户分类，对不同用户群体制定相应的服务策略。【方法】设计基于潜在类别分析(LCA)的O2O用户分类模型，使用LCA方法对用户进行分类，以餐饮团购O2O为例验证LCA方法应用于O2O用户分类的简单高效性。【结果】将用户分为潜力型、忠诚好奇型、谨慎型和挑剔型4类，针对不同的用户类型，分析其潜在特征和潜在群体类型，并据此提出相关营销策略。【局限】对用户特征使用二分类方法，人为对源数据进行处理，在进行二分类时分界线的选定具有主观性。【结论】LCA可以实现O2O用户分类及精准营销，扩展了潜在类别模型的应用范围。

关键词：020 潜在类别分析用户分类营销分类号：F713.36 G35

# 1引言

随着移动互联网的发展，O2O服务能够在线上线下协同为客户提供更佳体验，在餐饮、旅游、娱乐、零售、婚嫁和汽车等行业得到迅猛发展。由于能够实时获取用户交易数据与行为数据，一对一精准营销，在线上电子商务中得到广泛应用。但O2O 服务线下信息的实时获取仍旧是难点，因而很难实现O2O用户的一对一精准营销。可行的办法是依据O2O用户线上和线下的特征对用户进行分类，针对不同类别用户的特征制定不同的营销策略。

虽然目前关于互联网用户分类的研究有很多，但主要采用K-means[1]、K-medoids[2-3]、KNN[4]等分类方法，其K值和聚类个数是人为主观根据经验设定，并没有准确的依据。而且国内研究者侧重从行为和人口统计维度[5]对用户进行分类，如Guan等根据用户行为属性和基本属性建立分类模型，缺少对用户的心理特征分析，对用户特征分析不全面。也有研究使用结构方程模型[7]、因素分析法[8]对用户特征进行统计分析，而O2O用户属性特征变量(如心理特征)属于分类变量，结构方程模型、因素分析等方法并不能处理分类变量，需要用能够处理分类变量的方法对O2O用户进行分类。此外，在理论上，O2O服务是一个新兴的研究领域，国内对O2O服务用户分类研究较少，不能满足分类需求。

潜在类别分析(Latent ClassAnalysis,LCA)具有能够处理分类变量、不用预先设定分类个数等特点，避免了预先设定分类个数的主观性，已被广泛应用于对心理、情绪和行为诊断[9-13]等问题研究群体潜在异质性。本文借鉴LCA优点将其应用于O2O用户分类，结合O2O用户心理和行为特征建立最优潜在类别模型，依据客观数据实现用户精准分类，根据分类结果的潜在特征提出相应营销策略，解决了线上线下资源难以整合的问题。本文使用真实调查数据验证了LCA应用于O2O用户分类的有效性。

# 2020用户特征分析及用户属性抽取

O2O(Online to Offline)概念是Rampell在 2010 年8月提出的，至今并没有统一的定义。2013 年张波[14]提出，O2O就是在移动互联网时代，生活消费领域通过线上和线下互动的一种新型商业模式，并且正延伸到各行各业。O2O模式即是线上交易或预定线下消费体验，具体消费流程如图1所示。比如在美团上搜索火锅店信息，进行火锅餐券团购，在线上完成付款后用户会收到系统发出的验证码，用户在有效期内去实体店消费，消费时出示验证码即可，用餐结束，可选择对该店进行评价，购买过程完成。传统的网购并没有线下实体店消费这一环节，而线下消费是核心，线上无法控制核心体验。

![](images/1ee82b62dc552691eb00b19308107cb3666b3b40efd4243909ce6206b067cada.jpg)  
图1O20消费流程  
图2基于LCA的O2O用户分类流程

O2O 服务改变了人们的生活方式和用户特征[14-18]、需求,O2O服务用户有以下特点：

(1）碎片化。移动互联网时代，智能手机、4G 网络、手机二维码和电子凭证等技术手段的发展，导致信息的传播、获取方式和个人消费行为进入“碎片化”模式，用户迅速在各种信息之间跳转，从而导致营销渠道(微博、微信、论坛、视频网站、地铁、广告牌、小传单等)的碎片化，以充分利用用户碎片化的时间。未来的O2O就是把线下的细微流量整合起来，在适当的地点，适当的时间，将适当的商品(服务)以适当的数量和适当的价格提供给适当的使用者。根据时间碎片化和渠道碎片化的特征，选择用户的消费时间和用户的商品信息获取渠道作为用户属性。

(2）涉及线上和线下。O20的营销渠道、支付方式等都涉及到线上和线下。用户的体验和分享、O2O闭环最终完成都是线上和线下的共同作用。因此，选择支付方式、用户来源渠道作为用户属性。

(3)追求便捷性。各种移动支付和定位技术的发展，让支付和取得电子凭证变得方便快捷，促进了O2O的发展，使商家和用户之间形成一种“点对点"的关系，实现用户随时随地预订或消费，方便服务商随时更新商品或活动信息并传递给用户，采用多种渠道进行低成本营销。这种消费和信息获取的便捷性提高了用户的消费频率，因此，选择用户的消费频率作为用户属性。

(4)情感化。O2O 新商业模式下，个体行为倾向于相信自己的主观感觉和朋友推荐而非冷静的头脑。比如，接收到一些新事物的推送信息，好奇心较强的用户就会去消费；当用户购物过程中想要休息或者感到饥饿时正好收到餐馆推送的优惠活动，就可能会下单去餐馆消费；听到朋友对某种商品的推荐，也可能会去消费。此时，商品的距离、价格、个人收人、个人对新鲜事物的态度以及对他人评价的态度等都会对用户的消费产生影响，因此选择这些影响因素作为用户属性。

根据的O2O用户特点及已有相关研究[18-20]，本文中抽取相应的用户属性包括：基本属性、行为属性、心理属性三个维度的特征属性，具体如表1所示：

表1用户属性列表  

<html><body><table><tr><td>属性维度</td><td>属性名</td><td>属性定义</td></tr><tr><td rowspan="2">基本属性</td><td>性别</td><td>用户性别</td></tr><tr><td>个人收入</td><td>用户个人月收入 用户每个月使用O2O服</td></tr><tr><td rowspan="2">行为属性</td><td>月消费频率</td><td>务的次数</td></tr><tr><td>支付方式</td><td>用户进行消费时所选择的 付款方式</td></tr><tr><td rowspan="8">心理属性</td><td>距离偏好</td><td>用户对商品或服务的距离 的关注程度</td></tr><tr><td>时间偏好</td><td>用户偏好于在什么时间消 费(周末或非周末)</td></tr><tr><td>价格偏好</td><td>用户对商品或服务的价格 的关注程度</td></tr><tr><td>评价偏好</td><td>用户对商品评价或服务评 价的关注程度</td></tr><tr><td>信息获取渠道</td><td>用户通过什么渠道获得商 品或服务信息</td></tr><tr><td>对新鲜事物的态度</td><td>用户对新事物的接受程度</td></tr></table></body></html>

# 3基于LCA的O2O用户分类方法

# 3.1 用户分类流程

基于LCA的O2O用户分类主要是根据O2O用户的特征，选取相关属性建立潜类别模型(Latent ClassModel,LCM)，利用Mplus中模型拟合方法，对LCM模型进行拟合，选择最优模型，对模型进行参数化以及归类分析。图2为分类流程图：

数据准备，收集相关O2O用户数据  
1  
选择用户属性，建立潜类别分类模型(LCM)  
依据调查数据，分析AIC、BIC等指标，选择最优模型  
利用Mplus程序，计算概率分布值，进行模型参数化  
通过归类计算得到用户分类结果

# 3.2基于LCA的O2O用户分类建模

根据上文选取的O2O用户属性，基于LCA方法建立O2O用户分类模型，如图3所示。LCA的使用的基本假设是各外显变量(用户属性)之间具有局部独立性。而LCM是以零模型为假设的模型，即假设外显变量之间具有完全独立性，从零模型开始逐渐增加潜在类别的个数，比较各模型的评价指标，从而确定最优模型，利用潜在类别变量来解释外显变量之间的关联，进而维持外显变量之间的局部独立性。

![](images/78feb9b353ed95b3b01008261eada24f2712d9bc383ebe660e95e5f8e90a6d81.jpg)  
图3 O20用户分类模型

LCA数学模型如公式 $( 1 ) ^ { [ 2 1 ] }$ 所示：

$$
\pi _ { \mathrm { i j k } } ^ { \mathrm { A B C } } { = } \sum _ { \mathrm { t = 1 } } ^ { \mathrm { T } } \pi _ { \mathrm { t } } ^ { \mathrm { X } } \pi _ { \mathrm { i t } } ^ { \mathrm { A X } } \pi _ { \mathrm { j t } } ^ { \mathrm { B X } } \pi _ { \mathrm { k t } } ^ { \mathrm { C X } }
$$

其中,X为潜变量，有 $\mathfrak { t } ( { \mathrm { t } } { = } 1 , 2 , \cdots , \mathrm { T } )$ 个类别;A、B、C为三个用户属性，属性值分别为 $\mathrm { i } , \mathrm { j } , \mathrm { k } _ { \mathrm { ~ \circ ~ } } \ \pi _ { \mathrm { i j k } } ^ { \mathrm { A B C } }$ 表示潜类别模型联合概率。 $\pi _ { \mathrm { t } } ^ { \mathrm { X } }$ 为潜变量 $\mathrm { \Delta } \mathrm { X }$ 属于第 $\mathrm { ~  ~ t ~ }$ 个类别时的概率，且 $\sum _ { \mathrm { t = 1 } } ^ { \mathrm { T } } \pi _ { \mathrm { t } } ^ { \mathrm { X } } = 1$ □ $\pi _ { \mathrm { i t } } ^ { \mathrm { A X } }$ 表示在X属于第t个类别条件下 $\mathbf { A } { \ = } \mathbf { \dot { l } }$ 的条件概率，即 $\scriptstyle \mathrm { P ( A = i | X = t ) }$ ，其他同理。

# 3.3模型拟合及参数估计方法

对于探索性LCA，通常依据Pearson- $\cdot \chi ^ { 2 }$ 、似然比卡方、AIC 准则(Akaike Information Criterion)和 BIC准则(Bayesian Information Criterion)等[21]统计指标确定潜在类别数量。其中AIC、BIC是潜类别模型中使用最为广泛的评价指标。Lin 等[22指出当样本的数量超过1000时宜采用BIC指标，而低于1000则AIC更佳。本文选择 AIC、BIC、SSBIC(Sample-Size AdjustedBIC)、Pearson $\cdot \chi ^ { 2 }$ 及Entropy(熵)值作为拟合的评价指标。其中AIC、BIC、SSBIC、Pearson- $\cdot \chi ^ { 2 }$ 值均为越小越好，Entropy 指的是某种事件不确定性的大小，值越大表明事件的不确定性越大。

潜类别模型进行参数估计时主要使用极大似然(MaximumLikelihood,ML)法，其迭代过程常用的算法有多种，Mplus软件在处理二分变量时默认使用MLR(Maximum Likelihood Estimator with Robust

StandardErrors)方法求得各个变量的条件概率和潜在类别概率。该方法是一种修正的边际极大似然估计，在Mplus中称为MLR，标准误差采用Sandwich估计法，适应于非正态数据和小样本估计。具体MLR解释见参考文献[23]和Mplus用户手册[24]

# 3.4归类

根据参数估计结果，对O2O服务用户进行归类，以便根据分类结果为企业提供合适的O2O社会化营销和分类管理策略。具体分归类步骤如下：

(1）根据公式(1)计算用户潜类别模型联合概率。

(2）依据贝叶斯后验概率理论对每个个体进行潜在分类，计算公式如下：

$$
\pi _ { \mathrm { t i j k } } ^ { \mathrm { X A B C } } = \frac { \pi _ { \mathrm { i j k t } } ^ { \mathrm { A B C X } } } { \displaystyle \sum _ { \mathrm { t = 1 } } ^ { \mathrm { T } } \pi _ { \mathrm { i j k t } } ^ { \mathrm { A B C X } } }
$$

其中， $\pi _ { \mathrm { t i j k } } ^ { \mathrm { X A B C } }$ 为潜在类别概率，且 $\sum _ { \mathrm { t = 1 } } ^ { \mathrm { T } } \pi _ { \mathrm { t i j k } } ^ { \mathrm { X A B C } } = 1$ $\pi _ { \mathrm { i j k t } } ^ { \mathrm { A B C X } }$ 表示 $\mathrm { \Delta } \mathrm { X }$ 属于第 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 个潜在类别，且各用户属性分别为i、j、k水平时的概率，∑ABC $\sum _ { \mathfrak { t } = 1 } ^ { \mathrm { T } } \pi _ { \mathrm { i j k t } } ^ { \mathrm { A B C X } }$ ABCX表示T个类别概率之和。根据公式(2)确定用户属于哪一类。

# 4实证分析

# 4.1源数据采集及预处理

本研究资料为餐饮团购O2O的用户使用情况调查数据。由于餐饮O2O本身涉及到的群体比较广泛，收入属性对餐饮影响不大，设计调查问卷时删除了该属性。采用网络问卷调查法，即通过"问卷星"平台设计生成问卷，并发填写问卷的链接到同学、老师、朋友、亲友QQ群和朋友圈进行问卷填写邀请，问卷填写时间为2015年4月22日到4月26日，共收回收问卷338份，其中有效问卷327份，有效率达 $9 6 . 7 5 \%$ O

结合所选用户属性对所得数据进行预处理，根据数值分布情况将相关选项进行合并，如：调查问卷中的第3题的选项每月1-2次、很少使用和没用过这三个选项合并为：2次以下；大于2次改为：2次以上，就形成了表2中的题目B；将调查问卷中的第6题选项中优惠活动、实体店宣传和其他活动三个选项归为：优惠及活动，最后一项为：朋友推荐，就形成了表2中的题目E；同理，将第7题的前两项归为一项：有限制的接受，后一项为：很乐意接受，就形成了题目F；将第8题的多选题，选项中选择为关注，不选择为不关注，该题目可表示为表2中的题目G、H、I；问卷中选项为两项的题目不变，一共整理得到9个观测变量,经过预处理后的基本情况如表2所示：

表2327名被调查者对问卷的回答基本情况统计  

<html><body><table><tr><td>题目</td><td>基本情况</td><td>N</td><td>%</td></tr><tr><td rowspan="2">A性别</td><td>男</td><td>156</td><td>47.7</td></tr><tr><td>女</td><td>171</td><td>52.3</td></tr><tr><td rowspan="2">B月使用频率</td><td>2次及以上</td><td>177</td><td>54.1</td></tr><tr><td>2次以下</td><td>150</td><td>45.9</td></tr><tr><td rowspan="2">C支付方式</td><td>线上</td><td>298</td><td>91.1</td></tr><tr><td>线下</td><td>29</td><td>8.9</td></tr><tr><td rowspan="2">D使用时间</td><td>非工作日</td><td>263</td><td>80.4</td></tr><tr><td>工作日</td><td>64</td><td>19.6</td></tr><tr><td rowspan="2">E信息获取渠道</td><td>优惠及活动</td><td>272</td><td>83.2</td></tr><tr><td>朋友推荐</td><td>55</td><td>16.8</td></tr><tr><td rowspan="2">F对新事物的态度</td><td>有限制的接受</td><td>290</td><td>88.7</td></tr><tr><td>很乐意接受</td><td>37</td><td>11.3</td></tr><tr><td rowspan="2">G对价格的敏感度</td><td>不关注</td><td>59</td><td>18</td></tr><tr><td>关注</td><td>268</td><td>82</td></tr><tr><td rowspan="2">H对距离的敏感度</td><td>不关注</td><td>171</td><td>52.3</td></tr><tr><td>关注</td><td>156</td><td>47.7</td></tr><tr><td rowspan="2">I是否关注他人评价</td><td>不关注</td><td>83</td><td>25.4</td></tr><tr><td>关注</td><td>244</td><td>74.6</td></tr></table></body></html>

为了方便数据的统计分析，再对数据进行预处理性别"男"记为"0”“女"记为"1"，月使用频率"2次及以上"记为"0”、“两次以下"记为“1",C、D、E、F、G、H、I题目依次同理标记。

# 4.2 模型拟合与选择

Mplus是进行潜在类别分析的主流软件，因此选用Mplus软件对O2O用户数据进行潜在类别分析。表3中给出了相关拟合指标的结果。

表3潜类别模型拟合结果  

<html><body><table><tr><td>指标 模型</td><td>AIC</td><td>BIC</td><td>SSBIC</td><td>P-x²</td><td>Entropy</td></tr><tr><td>1 classes</td><td>3099.923</td><td>3134.033</td><td>3105.485</td><td>962.429</td><td>0</td></tr><tr><td>2 classes</td><td>3038.507</td><td>3110.561</td><td>3050.249</td><td>644.487</td><td>0.556</td></tr><tr><td>3 classes</td><td>3020.569</td><td>3130.478</td><td>3038.491</td><td>437.170</td><td>0.664</td></tr><tr><td>4 classes</td><td>3009.024</td><td>3156.832</td><td>3033.126</td><td>407.043</td><td>0.770</td></tr><tr><td>5 classes</td><td>3014.338</td><td>3200.016</td><td>3044.670</td><td>387.528</td><td>0.825</td></tr><tr><td>6 classes</td><td>3021.562</td><td>3245.170</td><td>3058.024</td><td>379.763</td><td>0.860</td></tr><tr><td>7 classes</td><td>3037.323</td><td>3298.831</td><td>3079.996</td><td>341.591</td><td>0.853</td></tr></table></body></html>

由于各指标均为越小越好，Lin 等[22]指出当样本的数量超过1000时宜采用BIC指标，而低于1000则AIC更佳。因此对于AIC和BIC以AIC最小为标准，这时选择为四分类，而SSBIC的值也是四分类最小，$\scriptstyle \mathrm { P - } \chi ^ { 2 }$ 增加到五分类并没有明显改善，同时考虑到模型的简洁性，应选择四分类模型，而此时的熵值也在可接受范围内，综合考虑各指标，选择四分类模型为最优模型。

# 4.3 模型参数估计

按照四类别潜在类别分析模型，运行Mplus软件，对潜类别概率和潜类别下各项目条件概率进行估计，结果如表4所示。可知，题目G中结果1代表的关注价格的用户，在4个类别中占比都很高，说明被调查者对价格比较关注；题目C中结果0代表的线上支付，可以看出Class1、Class2、Class4分别有 $8 7 . 4 \% . 7 8 . 7 \%$ 、$8 2 . 8 \%$ 的人选择线上支付方式；题目B中Class2和Class4 中月消费频率大于两次分别有 $8 2 . 6 \%$ 、 $6 2 . 8 \%$ 同时，题目A中Class2和Class4中女性占比分别为$7 9 . 5 \%$ 、 $56 . 9 \%$ ；相应地，Class1和Class3中月消费频率小于两次的占比较高的人群在A中显示为男性比例居高，可知女性月消费频率高于男性。

表49个条目的条件概率和潜在类别概率  

<html><body><table><tr><td rowspan="2">题目</td><td rowspan="2">结果</td><td colspan="4">潜类别条件概率</td></tr><tr><td>Class1</td><td>Class2</td><td>Class3</td><td>Class4</td></tr><tr><td rowspan="2">A</td><td>0</td><td>0.615</td><td>0.205</td><td>0.585</td><td>0.431</td></tr><tr><td>1</td><td>0.385</td><td>0.795</td><td>0.415</td><td>0.569</td></tr><tr><td rowspan="2">B</td><td>0</td><td>0.4</td><td>0.826</td><td>0.257</td><td>0.628</td></tr><tr><td>1</td><td>0.6</td><td>0.174</td><td>0.743</td><td>0.372</td></tr><tr><td rowspan="2">C</td><td>0</td><td>0.874</td><td>0.787</td><td>0.449</td><td>0.828</td></tr><tr><td>1</td><td>0.126</td><td>0.213</td><td>0.551</td><td>0.172</td></tr><tr><td rowspan="2">D</td><td>0</td><td>0.933</td><td>0.93</td><td>0.206</td><td>0.836</td></tr><tr><td>1</td><td>0.067</td><td>0.07</td><td>0.794</td><td>0.164</td></tr><tr><td rowspan="2">E</td><td>0</td><td>0.891</td><td>0.761</td><td>0.767</td><td>0.97</td></tr><tr><td>1</td><td>0.109</td><td>0.239</td><td>0.233</td><td>0.03</td></tr><tr><td rowspan="2">F</td><td>0</td><td>0.878</td><td>1</td><td>0.532</td><td>1</td></tr><tr><td>1</td><td>0.122</td><td>0</td><td>0.468</td><td>0</td></tr><tr><td rowspan="2">G</td><td>0</td><td>0.207</td><td>0.238</td><td>0.527</td><td>0.04</td></tr><tr><td>1</td><td>0.793</td><td>0.762</td><td>0.473</td><td>0.96</td></tr><tr><td rowspan="2">H</td><td>0</td><td>0.783</td><td>1</td><td>0.655</td><td>0</td></tr><tr><td>1</td><td>0.217</td><td>0</td><td>0.345</td><td>1</td></tr><tr><td rowspan="2">I</td><td>0</td><td>0.634</td><td>0</td><td>0.146</td><td>0</td></tr><tr><td>1</td><td>0.366</td><td>1</td><td>0.854</td><td>1</td></tr><tr><td colspan="2">潜类别概率</td><td>0.364</td><td>0.168</td><td>0.073</td><td>0.395</td></tr></table></body></html>

具体来说，有 $3 6 . 4 \%$ 的被调查者属于Class1，此类中男性居多占 $6 1 . 5 \%$ ， $60 \%$ 的人月消费频率在两次以下， $89 . 1 \%$ 的人通过优惠活动获取商家的产品或服务，$9 3 . 3 \%$ 的人在非工作日消费，大部分人对距离、评价信息不关注，但有 $6 3 . 4 \%$ 的人关注价格，该类人群的特点是消费频率不但较关注价格，来源渠道为优惠及活动，只要宣传得当，消费潜力很大，可将其定义为"潜力型"用户；有 $1 6 . 8 \%$ 的被调查者属于Class2，此类人群不同于Class1，女性居多，占 $7 9 . 5 \%$ ，有 $82 . 6 \%$ 的用户月消费频率大于两次，该类人群 $100 \%$ 关注价格，消费频率高、愿意接受新事物，可将其定义为“忠诚好奇型"用户；有 $7 . 3 \%$ 的被调查者属于Class3，此类用户区别于前两类的特征主要有： $7 9 . 4 \%$ 的用户选择在工作日消费, $76 . 7 \%$ 通过朋友推荐获得商家的产品或服务信息，而且该类用户中有 $5 5 . 1 \%$ 的人选择线下支付方式，显著高于其他三类， $8 5 . 4 \%$ 的用户都关注评价，尽量避免风险，可定义为"谨慎型"用户；有 $3 9 . 5 \%$ 的被调查者被分到Class4，其与Class2在大多数属性上比例差别不大，但是明显不同的是他们对服务或商品的价格、距离和评价都非常关注，比较挑剔，可定义为“挑剔型"用户。

# 4.4潜在分类结果

对最优模型进行参数化后，根据所得各个类别的潜类别概率和各个条目的条件概率计算分类到各个类别的后验概率，通过公式(1)及公式(2)计算分类概率，依据后验概率最大原则得到分类结果，如表5所示。其中，Class1-Class4的人数分别为119、55、24和129。

表5潜在类别模型个体分类结果  

<html><body><table><tr><td colspan="2">原始数据</td><td colspan="4">分类概率</td><td rowspan="2">结果</td></tr><tr><td>{ABCDEFGHIJ}</td><td>频数</td><td>Calss1</td><td>Class2</td><td>Class3</td><td>Class4</td></tr><tr><td>111111111</td><td>0</td><td>0.0039</td><td>0</td><td>0.9961</td><td>0</td><td>Class3</td></tr><tr><td>111111110</td><td>0</td><td>0.0385</td><td>0</td><td>0.9615</td><td>0</td><td>Class3</td></tr><tr><td>111111101</td><td>0</td><td>0.0075</td><td>0</td><td>0.9925</td><td>0</td><td>Class3</td></tr><tr><td>：</td><td>：</td><td>：</td><td></td><td>：</td><td>…</td><td>：</td></tr><tr><td>000000100</td><td>8</td><td>0.6392</td><td>0</td><td>0.3608</td><td>0</td><td>Class1</td></tr><tr><td>000000010</td><td>1</td><td>0.9932</td><td>0</td><td>0.0068</td><td>0</td><td>Class1</td></tr><tr><td>000000001</td><td>2</td><td>0.4650</td><td>0.5182</td><td>0.0168</td><td>0</td><td>Class2</td></tr><tr><td>000000000</td><td>0</td><td>0.9964</td><td>0</td><td>0.0036</td><td>0</td><td>Class1</td></tr></table></body></html>

# 4.5 结果讨论

表5是根据模型得到的分类结果，而分类结果背后有其潜在的分类原因。根据表5给出的结果，针对不同的类型，分析其潜在特征和潜在群体类型，并据此提出相关营销策略，具体情况如表6所示：

表6潜在类别结果讨论  

<html><body><table><tr><td>类别</td><td>潜在特征</td><td>潜在群体</td><td>营销策略</td></tr><tr><td>潜力型 (Class1)</td><td>对产品或服务要求学生、刚入秒杀活动、有奖转 不高、对O2O模式 职者，男性发、抽奖、营销送实 了解不多，关注优惠居多 活动</td><td></td><td>物、增加推广渠道</td></tr><tr><td>忠诚 好奇型 (Class2)</td><td>对新事物感兴趣、多为女性 好奇心强</td><td></td><td>新品试吃、标题党营 销、星座测试、晒美 食文化等增加趣味</td></tr><tr><td>谨慎型 (Class3)</td><td>对风险敏感、对产职业男性 品或服务质量要求 高，可能收入水平 比较高</td><td></td><td>塑造品牌形象、提供 详实全面的信息、提 供多种支付方式等 进行引导性消费营销</td></tr><tr><td>挑剔型 (Class4)</td><td>再次消费可能性 大、消费频率高、 对产品和服务质量 要求高，可发展为 忠诚用户</td><td>收入较高 的女性</td><td>会员折扣、赠送电子 礼品、会员优惠日双 倍积分，提高用户 粘性</td></tr></table></body></html>

# 5结语

本文利用LCA方法对加入心理行为的O2O用户进行分类，用客观的概率作为判断依据，分析潜在群体异质性，弥补了聚类分析的武断性，分类结果更加客观、符合实际，解决了线上线下资源难以整合问题，为企业的营销和管理提供客观依据，有助于提升用户体验，提高服务商运营效率。而且Mplus 软件处理潜类别模型时具有程序简单、处理迅速、综合性强等特点。LCA假设条件是外显变量具有局部独立性，但局部独立性很难在实际情况中实现，需要通过模型来设限，这也是LCM在技术上存在的提高空间，这时就需要选取最客观的指标确定最优模型，来研究O2O用户分类，这将是LCA应用于O2O领域下一步的工作重点。

# 参考文献：

[1] Rahman M A,Islam M Z.A Hybrid Clustering Technique Combining a Novel Genetic Algorithm with K-Means [J]. Knowledge-Based Systems,2014,71:345-365.   
[2] Zadegan S MR,Mirzaie M,Sadoughi F.Ranked K-medoids: A Fast and Accurate Rank-based Partitioning Algorithm for Clustering Large Datasets [J]. Knowledge-Based Systems, 2013,39:133-143.   
[3] 马箐，谢娟英．基于粒计算的 K-medoids 聚类算法[J]．计 算机应用,2012,32(7):1973-1977.(Ma Qing,Xie Juanying. New K-medoids Clustering Algorithm Based on Granular Computing [J]． Journal of Computer Applications,2012, 32(7): 1973-1977.)   
[4]李威．移动互联网用户行为分析研究[D].北京：北京邮电 大学,2013.(Li Wei.The Research on Mobile Internet User Behavior [D].Beijing:Beijing University of Posts and Telecommunications,2013.)   
[5] 胡慕海，蔡淑琴．基于情境偏好知识超图的移动用户细分 研究[J].管理学报,2011,8(10):1509-1516.(Hu Muhai,Cai Shuqin.The Model of Mobile Customer Segmentation Based onHypergraph of ContextPreferenceKnowledge [J].Chinese Journal of Management,2011,8(10): 1509-1516.)   
[6] Guan JF,Dai Y,Zhang M,et al.Evaluation Research for Internet Users/Services Attributes Extraction and Classification [J].The Journal of China Universities of Posts and Telecommunications,2013,20(S1): 81-85.   
[7]MacCallum R C,Austin JT.Applications of Structural Equation Modeling in Psychological Research [J].Annual Review of Psychology,2000,51: 201-226.   
[8]Bartholomew D J,Knott M.Latent Variable Models and Factor Analysis [M]. The 2nd Edition. Edward Arnold,1999.   
[9]Kang J, Ciecierski C C, Malin E L, et al. A Latent Class Analysis of Cancer Risk Behaviors Among US College Students [J].Preventive Medicine,2014,64:121-125.   
[10] 黎志华，尹霞云，蔡太生，等．留守儿童情绪和行为问题 特征的潜在类别分析：基于个体为中心的研究视角[J]．心 理科学,2014,37(2):329-334.(Li Zhihua,Yin Xiayun,Cai Taisheng,et al. Latent Class Analysis of the Characteristics of Left-Behind Children's Emotional and Behavioral Problems: The Person-Centered Perspectives [J]. Journal of Psychological Science,2014,37(2):329-334.)   
[11]张洁婷，焦璨，张敏强．潜在类别分析技术在心理学研究 中的应用[J]．心理科学进展，2010,18(12)：1991-1998. (Zhang Jieting,Jiao Can, Zhang Minqiang.Application of Latent ClassAnalysis in Psychological Research [J]. Advances in Psychological Science,2010,18(12): 1991-1998.)   
[12] Jackson N,Denny S,Sheridan J,et al. Predictors of Drinking Paterns in Adolescence: A Latent Class Analysis [J]. Drug and Alcohol Dependence,2014,135: 133-139.   
[13]Ward R M, Cleveland MJ,Messman-Moore TL.Latent Class Analysisof College Women's Thursday Drinking[J]. Addictive Behaviors,2013,38(1): 1407-1413.   
[14]张波.O2O 移动互联网时代的商业革命[M].北京：机械工 业出版社，2013:11．(Zhang Bo．O2O-Commercial Revolution of the Mobile Internet Era [M].Beijing: China Machine Press, 2013: 11.)   
[15] Tai C L,Hong J Y,Chang C M,et al.Determinants of Consumer's Intention to Participate in Group Buying [J]. Procedia-Social and Behavioral Sciences,2012,57: 396-403.   
[16] Ahn T,Ryu S,Han I. The Impact of the Online and Offline Features on the User Acceptance of Internet Shopping Malls [J]. Electronic Commerce Research and Applications,2005, 3(4): 405-420.   
[17] 张玉峰，周磊，杨威，等．电子商务团购消费者感知风险 研究[J]．情报科学，2011，29(10):1505-1508．(Zhang Yufeng,Zhou Lei, Yang Wei,et al. Research on Customer Perceived Risks by Customers in E-Commerce Group Buying [J].Information Science,2011,29(10): 1505-1508.)   
[18]张春霞．团购 2.0 用户的消费特征及心理研究[D].北京: 北京邮电大学，2012．（Zhang Chunxia．Research on Consumption Characteristics and Psychology of GroupBuying2.O [D]. Beijing: Beijing University of Posts and Telecommunications,2012.)   
[19]Kumar N,Benbasat I.Research Note: The Influence of Recommendations and Consumer Reviews on Evaluations of Websites [J].Information System Research,2006,7(4): 425-439.   
[20]刘英姿，吴昊．客户细分方法研究综述[J]．管理工程学报, 2006,20(1):53-57.(Liu Yingzi,Wu Hao.A Summarization of Customer Segmentation Methods [J].Journal of Industrial Engineering and Engineering Management，20o6，20(1): 53-57.)   
[21]Hagenaars J A,McCutcheon A L.Applied Latent Class Analysis [M].Cambridge University Press,2002:56-58.   
[22]Lin T H,Dayton C MModel Selection Information Criteria for Non-Nested Latent Class Models [J].Journalof Educational and Behavioral Statistics,1997,22(3):249-264.   
[23]刘红云，骆方，王玥，等．多维测验项目参数的估计：基于 SEM 与 MIRT 方法的比较[J]．心理学报，2012，44(1): 121-132.(Liu Hongyun,Luo Fang，Wang Yue,et al.Item Parameter Estimation for Multidimensional Measurement: Comparisons of SEM and MIRT Based Methods [J].Acta Psychologica Sinica,2012,44(1):121-132.)

[24]Mplus User's Guide [EB/OL].[2015-04-25]. http://www. statmodel.com/.

# 作者贡献声明：

刘平峰：提出研究思路，设计研究方案，论文最终版本修订;  
王贝：论文起草，进行实验;  
王贝，雷洁：采集、清洗和分析数据。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版 http://www.infotech.ac.cn。[1]王贝.338_338_2.xls.餐饮O2O用户使用情况调查数据.[2]王贝．附件1餐饮O2O用户使用情况调查.doc.餐饮O2O用户使用调查问卷.

收稿日期:2015-08-03   
收修改稿日期:2016-01-15

# Using Latent Class Analysis to Classify O2O Service Users

Liu PingfengWang Bei Lei Jie (School of Economics,Wuhan University of Technology, Wuhan 430070, China)

Abstract: [Objective] This study clasified the Online to Ofline (O2O)service users accurately,which could lead to more appropriate service strategies for diferent user groups.[Methods] We first designed an O2O user classification model based on the Latent Class Analysis (LCA).Then, we classified the catering service O2O customers to examine the simplicityand eficiencyof this new model.[Results]We grouped theusers into four categories and found their latent classes, which helped the O2O service providers develop diferent marketing strategies.[Limitations] Applying the proposed method to classify users might have some subjective factors involved.[Conclusions] The LCA model could help us beter categorize and target the O2O service users, which expanded the applicable scope of this model.

Keywords: Online to OfflineLatent Class AnalysisUsers classificationMarketing