# 多会话商品信息搜寻行为、情境及影响因素研究

刘洪莲 张鹏翼 王军(北京大学信息管理系北京 100871)

摘要：【目的】研究电商用户在多会话网购过程中的商品信息搜寻的行为特征、会话时间间隔特征以及购物网站使用特征，并探究行为背后的情境、原因和动力。【方法】基于某电商网站4285个用户的1409160条访问日志，利用顺序分析和聚类分析方法挖掘用户信息搜寻行为特征，结合访谈研究行为背后的情境、原因等影响因素。【结果】多会话网购用户信息需求并不急切，较之搜索更倾向于查看商品详情；平均会话时间间隔为3-4天;继续原来购物任务的动力包括个人偏好、需求状态、支付能力、时间等方面的因素；用户主要通过搜索、购物车、收藏夹、同店或同款商品浏览、商品个性化推荐等途径回到原来购物任务。【局限】访谈结果受样本数量限制，不具有普适性。【结论】有助于理解用户的复杂网购行为，指导购物网站提高服务质量，改善用户体验。

关键词:多会话网络购物信息搜寻行为购物网站

分类号：G354

# 1引言

截至2014年12月，中国网络购物用户规模达到3.61亿，较2013年底增加5953万，增长率为 $1 9 . 7 \%$ 使用网络购物的比例从 $4 8 . 9 \%$ 提升至 $5 5 . 7 \%$ ，网络购物市场规模达2.8万亿[1]。随着网络购物的发展，其便利性和选择的多样性使得用户做出购物决策过程发生变化，在同一购物任务中，用户可能多次访问购物网站，经过多次信息搜寻、产品对比，最终才做出购物决策，这成为网络购物的显著特点[2]。

目前有部分研究利用点击流日志对网购用户信息行为以会话为单位进行建模，分析研究网购用户的行为特征[3-4]，较少关注经过多次会话的网络购物任务中用户商品信息搜寻的行为特征[2.5-6]，因此并不能深入理解网购用户经过多次访问作出购物决策的复杂信息搜寻行为。本文旨在探究用户多次访问购物网站过程中的商品信息搜寻的行为特征、会话时间间隔特征，并分析其情境、原因等影响因素。其中，信息搜寻行为特征包含用户在多会话网购过程中进行商品信息搜寻时的起始行为、结束行为、典型行为、行为转换特征及会话时间间隔特征，用户回到原来购物任务的途径；用户在什么情境和需求状态下会经过多次访问才做出购物决策；而用户中断购物的原因和重新回到原来购物任务的方式和渠道有助于更好地理解用户在多会话网络购物过程中的行为。

与本文研究相关的定义如下：会话是用户与服务器之间不中断的请求响应序列，用户的一次会话代表用户的一次网购过程[7]。本研究中，如果用户在完成一个动作之后连续45分钟没有进行任何动作[4]，则视为一个会话的结束，之后用户的第一个动作即为下一个会话的开始。购物任务指消费者进行商品信息搜寻活动、购买决策等一系列行为的集合[8]。在本研究中，购物任务可能在一次访问会话后结束，称之为“单会话”购物任务，也可能经多次访问会话结束，称之为“多会话"购物任务。

# 2相关研究

消费者的购物决策过程由若干阶段构成，包含购物问题识别、信息搜寻、评估选择、购买和购后反馈。消费者行为研究中的经典Engel-Kollat-Blackwell模型全面描述了消费者购物决策的过程：当消费者的实际状态无法达到期望状态时，就有了需求认知;进而开始搜寻信息来满足需求；消费者根据自己的内部信息和从外部搜集到的信息去评价和比较可能的选择，产生一定的偏好并最后确定要购买的商品，发生购买行为；购买后的评价会影响消费者以后的购买决策[9]。与传统购物决策不同，在线购物消费者在购物决策过程中，面临虚拟、交互式的购物环境，信息获取更为便利，选择范围也更大，因此消费者很难去全面评估所有可能的选择。网络购物的核心购买过程包括信息搜索、评估选择和购买三个阶段[10]。有研究将网络购物消费者的决策过程分为两个主要阶段：大范围地浏览大量商品，并从中找出一些偏好选择，小范围深入地对比选定的几款商品，并作出购买决策[11]。本文借鉴消费者行为模型的宏观过程，在整个购物过程中考察用户的信息查询行为；然而有关消费者行为的模型大多建立在传统零售用户的购物任务之上，在线购物是否具有类似的特征，还需要进一步验证。与传统购物不同，在线购物的信息查询成本大大降低，访问次数增加，对比评估的商品数量增多，但对于在线购物的消费者经过多次访问进行信息查询的研究非常少。

在信息行为领域，已有较多研究对文献或网页搜索任务中经过多个阶段完成搜索的用户进行分析和建模，如Lin 等提出的多会话信息搜寻模型(MultipleInformation Seeking Episodes,MISE)[l2包含8种模式,试图系统地解释信息检索者经过多次检索来解决同一问题的原因和过程；Vakkari基于任务的信息检索过程理论对论文写作中的信息检索过程进行建模，得出连续检索中的关键因素[13];Spink的连续检索模型对连续检索过程中影响检索结果的用户和系统因素都进行建模[14]；Komlodi 等提出的信息搜寻历史框架模型将信息检索历史描述为人与系统交互的选择，这一框架描述了影响信息检索历史记录使用的外部和内部因素[15]。信息行为研究主要集中在图书情报学领域，研究对象也主要针对文献或网页检索等，这些研究的结果对于理解多会话商品信息搜寻行为提供了研究思路和方法上的借鉴。商品信息查询较一般的信息查询，获得的信息更多是用于消费决策，因此本研究综合借鉴上述两个领域(消费者行为研究和信息行为研究)的研究成果。

# 3 研究方法

# 3.1 日志分析

本研究的原始数据集来自某互联网市场调查机构通过浏览器插件收集的用户在2013年5月份的浏览器访问日志，日志中的字段如表1所示。辅助数据源还包含用户注册数据，商品类目数据信息(共约14000商品类目，通过淘宝开放API获得①)。

表1浏览器端日志表结构  

<html><body><table><tr><td>字段</td><td>含义</td><td>字段</td><td>含义</td><td>字段</td><td>含义</td></tr><tr><td>id</td><td>记录ID</td><td>date</td><td>访问日期</td><td>site</td><td>访问站点</td></tr><tr><td>uid</td><td>用户ID</td><td>staytime</td><td>停留时间</td><td>domain</td><td>访问域名</td></tr><tr><td>ip</td><td>用户IP</td><td>URL</td><td>用户访问地址referURL来源地址</td><td></td><td></td></tr></table></body></html>

之前的研究在原始日志基础上定义并标记用户会话，并对用户访问的页面类型及用户行为类型进行标记[4]，得到可用日志数据表中的记录共有1409160条,涉及81759个访问会话，4285个用户。在识别多会话网络购物任务的基础上[16]，对用户在多会话网络购物过程中的信息搜寻行为特征进行研究。

本研究采用统计方法分析多会话购物过程中用户的会话时间间隔特征；使用MicrosoftSQLServerDataTools的顺序分析和聚类分析算法对用户的浏览和搜索行为序列进行挖掘和分析，分析用户在多会话网购过程中的行为转换特征，以及会话间的起始和结束行为特征。SQLServer顺序分析和聚类分析算法是一种混合算法，综合聚类分析方法和Markov 链分析，以对序列数据进行聚类。序列数据一般用于表示状态之间的一系列转换，例如本研究中用户的一系列商品搜索或页面点击操作。此算法检查所有转换概率，并测量数据集中所有可能序列之间的差异或距离，以确定使用哪些序列作为聚类分析的输人，在创建候选序列列表后，该算法将该顺序信息用作聚类分析的ExpectationMaximization(EM)方法的输入。在EM聚类分析中，此算法反复优化初始分类模型，计算数据存在于某个分类中的概率，当概率模型适合于数据时，算法终止。

# 3.2 用户访谈

根据日志得到的用户的人口统计学特征的比例进行抽样，开展深度访谈，作为对定量研究的补充。使用卡方检验发现多会话网络购物用户与单会话网络购物用户在性别 $\lambda ^ { 2 } { = } 5 4 . 9 4 9$ 5 $\scriptstyle \mathrm { \alpha = 0 . 0 0 0 } $ ）、职业分布（ $\lambda ^ { 2 } { = } 4 1 . 5 5 8$ $\scriptstyle \mathrm { \alpha = 0 . 0 0 0 } )$ 方面有显著差异，而在年龄( $\lambda ^ { 2 } { = } 8 . 1 6 7$ ， $\scriptstyle \alpha =$ 0.698)、学历 $\lambda ^ { 2 } { = } 3 . 9 7 7$ 。 $\scriptstyle \mathrm { \alpha = 0 . 7 8 2 } )$ 、收入水平分布 $( \lambda ^ { 2 } =$ 26.789, $\scriptstyle \mathrm { \alpha = 0 . 1 1 0 } )$ 等方面没有显著差异。参与多会话网络购物用户性别与职业的分布如图1所示，这里的职业是用户注册时填写的分类，专业人员指具有特定专业技能的人员，如程序员、医生等。

![](images/c0b1e6f608396a749b1e39608b9383e308672db816987a783456bfb8defee75f.jpg)  
图1多会话网购用户分布  
图2会话中搜索和浏览行为转换

根据多会话网购用户在职业、性别上的分布比例，同时兼顾方便取样的原则，最终选定15人为访谈对象，不同年龄和职业的人数如表2所示。

表2访谈对象性别和职业分布  

<html><body><table><tr><td></td><td>教育 工作者</td><td>行政/ 文员</td><td>管理 人员</td><td>在校 学生</td><td>销售 人员</td><td>专业 人员</td></tr><tr><td>男</td><td>1</td><td>1</td><td>1</td><td>2</td><td>1</td><td>1</td></tr><tr><td>女</td><td>1</td><td>3</td><td>1</td><td>1</td><td>2</td><td>1</td></tr></table></body></html>

访谈时间为2015年4月-2015年5月，采用电话访谈并且录音的方式，每位用户的访谈持续时间大约为20-30分钟。按照访谈的时间顺序对用户进行编码，并对用户访谈录音进行文字转录和内容分析。访谈内容包括5个方面共13个问题，内容涵盖购物过程、购物情境及原因、购物过程的中断原因及时间、重新回到原来购物任务的动力、回到原来购物任务的方法和途径等。

# 4结果

# 4.1 信息搜寻行为序列

以会话为单位，分别对一般的网络购物会话(不区分单会话与多会话购物任务)的搜索和浏览行为序列以及多会话网络购物任务会话中的搜索和浏览行为序列进行顺序分析和聚类分析，得到多会话网络购物任务的搜索(输入检索式检索)和浏览(查看商品详情)行为序列特征，如图2所示：

开始 开始  
0.54 0.35 0.46 0.65 0.88输入检索式检索 查看商品详情0.20 0.80结束 0.12 结束(a)一般网络购物会话开始 开始0.19 0.81  
0.71 0.29 0.95输入检索式检索 查看商品详情0.16 0.84结束 0.05 结束(b)多会话网络购物会话

由图2可知，与一般的网络购物会话相比，多会话网络购物用户更倾向于"查看商品详情”，以"查看商品详情"结束的概率较大；且在会话起始时“查看商品详情"的概率也较大，“输入检索式检索"的概率较小。从行为转换来看，与一般网络购物会话相比，前一行为是"输入检索式检索"时，多会话网络购物任务“输入检索式检索 $$ 输人检索式检索"的概率大于一般的网络购物会话，而“输人检索式检索 $$ 查看商品详情"的概率则较低；前一行为是“查看商品详情"时，多会话网络购物任务“查看商品详情 $$ 查看商品详情"的概率较大，而“查看商品详情 $$ 输人检索式检索"的概率低于一般网络购物会话。由此可见，用户在多会话网络购物任务中，更倾向于不断地输入检索式检索来搜寻信息；而在检索后查看商品详情的概率较低，即发现潜在商品的概率较低；在查看商品详情后再检索的概率也较低，说明用户如果发现所浏览的商品不满意，更倾向于不再继续检索。

利用卡方检验分析一般的网络购物会话与多会话网络购物会话中的频繁行为(出现频次最高的行为类型)分布、起始行为分布、结束行为分布以及行为转换状态分布是否有显著差异。结果如表3所示：

表3一般网络购物与多会话网络购物行为特征差异的卡方检验  

<html><body><table><tr><td></td><td>会话类型</td><td>行为或转换类型</td><td>概率</td><td>频数</td><td>Pearson 卡方值</td><td>渐进 Sig.(双侧)</td></tr><tr><td rowspan="4">频繁 行为</td><td rowspan="2">一般网络购物会话</td><td>输入检索式检索</td><td>0.2358</td><td>79 269</td><td rowspan="4">1 275.48</td><td rowspan="4">.000</td><td rowspan="2"></td></tr><tr><td rowspan="2">查看商品详情</td><td rowspan="2">0.7642</td><td rowspan="2">256 901</td></tr><tr><td rowspan="4">输入检索式检索</td><td></td></tr><tr><td rowspan="2">多会话网络购物会话 查看商品详情</td><td></td><td>0.1835</td><td>19 533</td></tr><tr><td></td><td>0.8165 86915</td><td rowspan="3"></td><td rowspan="3">.000</td></tr><tr><td rowspan="2">一般网络购物会话 起始 行为 多会话网络购物会话</td><td>输入检索式检索 查看商品详情</td><td>0.3500 0.6500</td><td>15 754 29257</td></tr><tr><td rowspan="2">输入检索式检索</td><td></td><td>0.1936</td><td>7413 2 520.64</td></tr><tr><td rowspan="2">一般网络购物会话</td><td rowspan="2"></td><td>查看商品详情</td><td>0.8064</td><td>30876</td><td rowspan="2"></td><td rowspan="2"></td></tr><tr><td>输入检索式检索</td><td>0.2046</td><td>9209</td></tr><tr><td rowspan="3">结束 行为</td><td rowspan="2">多会话网络购物会话</td><td>查看商品详情</td><td>0.7954</td><td>35802</td><td rowspan="3">323.42</td><td rowspan="3"></td><td rowspan="3">.000</td></tr><tr><td>输入检索式检索</td><td>0.1563</td><td>5985</td></tr><tr><td rowspan="2"></td><td>查看商品详情</td><td>0.8437</td><td>32 304</td></tr><tr><td rowspan="2">行为 转换 多会话网络购物会话</td><td rowspan="2">一般网络购物会话</td><td>输入检索式检索→输入检索式检索</td><td>0.5367</td><td>37 253</td><td rowspan="3">664.48</td><td rowspan="2">.000</td></tr><tr><td rowspan="2"></td><td rowspan="2">输入检索式检索→查看商品详情</td><td rowspan="2">0.4633</td></tr><tr><td>输入检索式检索→输人检索式检索</td><td>0.7060</td><td>32 500 10352</td></tr><tr><td rowspan="4">行为 转换</td><td rowspan="2">-般网络购物会话</td><td>输入检索式检索→查看商品详情</td><td>0.2940</td><td>5 665</td><td rowspan="2"></td><td rowspan="4"></td><td rowspan="4">.000</td></tr><tr><td>查看商品详情→查看商品详情</td><td>0.8825</td><td>14 845</td></tr><tr><td rowspan="2">多会话网络购物会话</td><td>查看商品详情→输入检索式检索</td><td>0.1175</td><td>25690</td><td rowspan="2">40 600.22 5215</td></tr><tr><td>查看商品详情→查看商品详情 查看商品详情→输入检索式检索</td><td>0.9532</td><td>66 055</td></tr></table></body></html>

从表3可知，一般网络购物与多会话网络购物的频繁行为、起始行为、结束行为和行为转换均存在显著性差异。

通过访谈探究用户此行为特征背后的原因，发现与用户所处的购物情境密切相关。用户进行多会话网络购物时的情境主要指用户在进行多会话网络购物时的需求状态。在进行多会话网络购物时，用户的需求状态主要有三种：不是特别需要；需要但不急切；需要但不确定商品的尺寸、质量、功能和使用方法。有10名访谈对象提到需要但不确定商品的尺寸、款式、质量、功能或使用方法;7名访谈对象提到需要但不急切；6名访谈对象提到在进行多会话网络购物时本来对商品不是特别需要。当用户需求状态为“不是特别需要"时，更倾向于通过浏览开始商品信息查询，即起始行为是“查看商品详情"的概率较大；当用户“需要但不确定商品的尺寸、质量、功能和使用方法"时，会更频繁地"查看商品详情"进行商品比对，以“查看商品详情"结束会话的概率也较大。

# 4.2 会话时间间隔

多会话网络购物任务的会话时间间隔指在同一购物任务中，相邻两会话之间的时间间隔，由后一会话开始时间减去前一会话开始时间。对多会话网络购物任务会话时间间隔进行基本统计，会话时间间隔的极大值为2595871秒，大约30.05天；均值为343109.55秒，大约为3.97天；中值和众数较接近，分别为2.00天和1.89天。多会话网络购物任务会话时间间隔的分布，如图3所示：

![](images/bb9c31c944edbd4479a92488785a2b305ebd0c301b1997015460b438bf144d3d.jpg)  
图3会话时间间隔分布

对两者做线性回归，拟合优度 $\mathrm { R } ^ { 2 } { = } 0 . 6 8 3 3$ ，同一个购物任务中的会话时间间隔近似幂律分布，即极少数的购物任务中会话时间间隔很长，而大多数购物任务中的会话时间间隔较短。

访谈结果显示，用户在多会话网络购物中中断购物的原因，与用户的购物情境有密切关系，即“需要但不确定商品的尺寸、款式、质量、功能或使用方法”“需要但不急切”或“不是特别需要"；此外，中断购物的原因还包括时间限制、被其他事情打断、碎片时间不足以做出购买决策、以及支付能力暂时不够等。用户重新回到原购物任务的动力包括：确实喜欢、确实需要、需求更加强烈、支付能力可以满足、无意中再浏览等。14名对象表示重新回到原来购物任务的动力包括“确实需要或需求更急切”，这类情况下回到原来购物任务是需求推动；6名访谈对象表示“确实喜欢那件商品(但不一定需要)";3名访谈对象表示可能是“闲逛无意中回来看一下";1名访谈对象表示在“支付能力可以满足"时会重新回来购买。

有7位访谈对象在多会话网络购物过程中相邻会话的间隔约为2-3天，其中3位甚至在当天就会继续访问购物网站，因为当时“有了明确的购物需求”，因此“不会等太长时间就会重新回来访问购物网站”；有6位访谈对象的间隔可能为几天到一、两周不等，并认为具体间隔多长时间受需求状态、决策阶段以及时间安排的影响；2位访谈对象的间隔较长，会间隔“一个月”、“两三个月”、甚至“半年”，因为“自己其实并不需要”，或者本身使用购物网站的频次就较低。这也与日志分析得出的极少数的购物任务中会话时间间隔很长，而大多数购物任务中的会话时间间隔较短，会话时间间隔的众数大约为2天的结论一致。

# 4.3返回原购物任务的途径

用户访谈结果显示，在回到原来购物任务时，用户使用的途径主要有再次搜索、购物车、收藏夹、同店或同款商品浏览、商品个性化推荐等。部分用户会在购物阶段前期通过搜索途径回到原来的购物任务，尤其是还未锁定几款小范围的商品，处在大范围的选择对比阶段时。还有部分用户习惯使用搜索来搜寻购物网站信息，搜索与否并不取决于购物阶段；或者在特定购物情境下会更多地依赖于搜索来找到之前浏览过的商品，此类情境指购物时有特定的品牌、店铺偏好，或特定购买某一款商品，

用户通过购物车回到原来购物任务的情况包括：在经过大范围浏览比较后选定几款商品加入购物车，后续过程中主要针对购物车中的商品进行对比选择;将喜欢或将来可能需要的商品加入购物车，此类情况一般是将购物车当收藏夹用，后续再次访问购物网站或者真正需要的时候再通过购物车浏览之前添加的商品。用户通过收藏夹回到原来购物任务的情况也包括两种：在经过大范围浏览比较后选定几款商品加入收藏夹，后续过程中主要针对收藏夹中的商品进行对比选择；将喜欢或将来可能需要的商品加入收藏夹，后续再次访问购物网站或者真正需要的时候再查看之前收藏的商品。从用户回到原来购物任务途径的分析可知，对部分用户而言，收藏夹和购物车的用途没有很大差别，尤其是在商品大范围选择阶段，将选定的小范围的几款商品加入收藏夹还是购物车，在很大程度上取决于个人使用习惯。

# 5 结语与讨论

本文采用定量(日志分析)和定性(用户访谈)结合的研究方法，探索多会话网络购物过程中用户的商品信息搜寻行为序列特征、会话时间间隔特征和购物网站使用特征，并探究行为特征背后的影响因素，包括购物情境、中断购物的原因和回到原来购物任务的动力。研究发现，用户在多会话网络购物过程中以“查看商品详情"开始和结束会话的概率较高，其频繁行为为“查看商品详情”，这取决于用户所处的购物情境。从行为序列的转换来看，用户更倾向于通过不断地“输人检索式检索"来搜寻信息，而在检索后查看商品详情的概率较低，即发现潜在商品的概率较低。用户中断购物的原因和回到原来购物任务的动力与用户的需求状态密切相关，这也影响了用户在多会话网购过程中的时间间隔。用户的会话时间间隔还受到其使用购物网站频次的影响。用户回到原来购物任务的途径主要有搜索、购物车、收藏夹、同店或同款商品浏览、商品个性化推荐等，这与用户所处的购物决策阶段及用户的购物网站使用习惯有关。

本文对用户在多会话网购过程中的信息搜寻行为序列特征、会话时间间隔特征和购物网站使用特征及其影响因素的研究有助于更深入地理解用户的复杂网购行为，进而更好地指导购物网站的导航设计和推荐策略。本文的局限在于，受日志数据中用户信息隐匿的限制，后期研究中所访谈的用户并非产生日志的用户，这导致无法对日志用户当时的购物情境、中断购物的原因、回到原来购物任务的动力和途径进行调查，无法还原用户当时的购物过程，只能尽量根据日志分析得出的多会话网络购物用户的人口统计学特征选择访谈对象，使其尽量与日志中用户的人口统计学特征分布一致。由于访谈方法本身的局限性，访谈结果在一定范围内具有代表性，但可能无法普适到其他人口统计学特征的用户群。在后续研究中可以对同一批用户运用日志分析和访谈相结合的方法，更深入地挖掘用户在多会话网络购物过程中的行为特征。

# 参考文献：

[1] 中国互联网络信息中心．2014年中国网络购物市场研究报 告[EB/OL].https://www.cnnic.net.cn/gywm/xwzx/rdxw/2015/ 201509/W020150908609566580083.pdf.(CNNIC.The 2014 Report of China's Online Shopping Market Research [EB/ OL]. https://www.cnnic.net.cn/gywm/xwzx/rdxw/2015/201509/ W020150908609566580083.pdf.)   
[2] Senecal S,KalczynskiPJ,Nantel J.Consumers’DecisionMaking Process and Their Online Shopping Behavior:A Clickstream Analysis[J]. Journal of Business Research,2005, 58(11): 1599-1608.   
[3]Moe W W. Buying, Searching,or Browsing: Differentiating Between Online Shoppers Using In-Store Navigational Clickstream [J].Journal of Consumer Psychology，2003, 13(1): 29-39.   
[4]袁兴福，张鹏翼，刘洪莲，等．基于点击流的电商用户会 话建模[J]．图书情报工作，2015，59(1):119-126.(Yuan Xingfu，Zhang Pengyi，Liu Honglian，et al． Modeling E-commerce User Session Behaviors Based on Click-through Sequences[J].Library and Information Service,2015,59(1): 119-126.)   
[5]Lee J, Podlaseck M, Schonberg E,et al. Visualization and Analysisof Clickstream Data of Online Storesfor Understanding Web Merchandising[A].// Applications of Data Mining to Electronic Commerce[M]. Springer, 2001: 59-84.   
[6]王蕾．基于信息需求的消费者网络信息搜寻行为研究[J]. 情报理论与实践，2013，36(7):90-93．(WangLei. InformationSeekingBehaviorResearchBasedon Information Need of Consumers [J]. Information Studies: Theory & Application,2013,36(7): 90-93.)   
[7]张文君，王军,徐山川．电商用户需求状态的聚类分析——以 淘宝网女装为例[J]．现代图书情报技术，2015(3)：67-74. (Zhang Wenjun,Wang Jun,Xu Shanchuan. The Probing of E-commerce User Need States by Page Cluster Analysis An Empirical Study on Women's Clothes from Taobao.com [J].New Technology of Library and Information Service, 2015(3): 67-74.)   
[8]Gillenson ML, Sherrell D L.Enticing Online Consumers: An Extended Technology Acceptance Perspective[J]. Information & Management, 2002,39(8): 705-719.   
[9]Engel JF，Blackwell R D，Miniard P W.Consumer Behavior[J]. Journal of Consumer Policy,1986, 9(4): 481.   
[10] Teo T S, Yeong YD.Assessing the Consumer Decision Process in the Digital Marketplace[J]. Omega,2003,31(5): 349-363.   
[11]Häubl G, Trifts V. Consumer Decision Making in Online Shopping Environments:The Effects of Interactive Decision Aids [J]. Marketing Science,2000,19(1): 4-21.   
[12] Lin S J, Belkin N J. Modeling Multiple Information Seeking Episodes [C]. In: Proceedings of the 63rd Annual Meeting of ASIS, 2000.   
[13] Vakkari P.A Theory of the Task-Based Information Retrieval Process: A Summary and Generalisation of a Longitudinal Study [J]. Journal of Documentation,20o1,57(1): 44-60.   
[14] Spink A. Multiple Search Sessions Model of End -User Behavior: An Exploratory Study[J].Journal of the American Society for Information Science,1996,47(8): 603-609.   
[15]Komlodi A，Soergel D.Attorneys Interacting with Legal Information Systems:Tools for Mental Model Building and Task Integration[J].Proceedings of the American Society for Information Science and Technology,2002,39(1):152-163.   
[16]刘洪莲，张鹏翼，王军．多会话网络购物商品信息搜寻行 为研究[J]．图书情报工作，2015，59(14):117-125.(Liu Honglian,Zhang Pengyi,Wang Jun．Product Information Seeking Behavior of Multi-session Online Shopping Tasks[J]. Library and Information Service,2015,59(14):117-125.)

# 作者贡献声明：

刘洪莲：数据分析，开展访谈，起草论文;  
张鹏翼：设计研究方案，修改论文;  
王军：提出研究思路，论文最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:pengyi@pku.edu.cn。  
[1]刘洪莲，张鹏翼，王军．访谈大纲.doc.用户访谈的大纲和问题列表.  
[2]刘洪莲，张鹏翼，王军．访谈用户.xls.受访用户人口统计学特征.  
[3]刘洪莲，张鹏翼，王军．聚类结果.csv.用户聚类分析结果.

收稿日期:2015-11-12   
收修改稿日期:2016-01-07

# Multi-session Product Information Seeking Behaviors, Motivation, and Influencing Factors

Liu HonglianZhang PengyiWang Jun (Department of Information Management, Peking University, Beijing 10o871, China)

Abstract:[Objective] This research aims to examine the information seeking behavior paterns and contextual factors of online shoppers’multi-sessionalactivities.[Methods]First, we analyzed1,409,160 logs ofanonline shopping Web site(generated by4,285users）to discover their information seeking behaviors.Second,weused in-depth interviews to explore the users’motivations.[Results] We found that multi-session shoppers were more likely to check detailed introductionto the products than simply browsing.The average interval between each sesion was 3to4days.Personal preferences,needs,financial abilityand time might lead the users to restore their previous sessions.Searching,shopping carts,bookmarks,browsing and personalized recommendation services were the major channels for users to restore previous sessions.[Limitations] Because ofthe limited number of participants,results fromthe interviews might not be generalizable to the whole population.[Conclusions]This research helps us understand the complex online shopping behaviors as well as improve services and user experience of E-commence Web sites.

Keywords: Multi-session online shoppingInformation seeking behaviorE-commerce Web site