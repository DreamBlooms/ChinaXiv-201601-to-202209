# 保护与监管视角下的颠覆性技术政策主题演化研究

王晨琳 刘晓娟

北京师范大学政府管理学院北京100875

摘要：[目的/意义]从我国对颠覆性技术的保护和监管需求出发，通过挖掘世界科技强国不同时期的颠覆性技术政策关注焦点和演进特征，为我国政策发展方向提供借鉴。[方法/过程]基于1990-2020 年间的颠覆性技术政策文件集，通过LDA 模型探索政策主题焦点分布，并引入时序因素构建DTM模型分析不同时期的政策主题内容和强度的演化情况，总结科技强国的关键政策经验。[结果/结论]本研究将科技强国的颠覆性技术政策发展划分为7个时期。研究发现，保护和监管视角下的政策焦点演化均存在衰减型、增长型和波动型3类。相对而言，在保护型政策主题更具集中性和连贯性，存在明显的领导型主题“阶段发展规划”；监管视角则没有固定的领导型主题，但主题融合范围更大，其中“跨域监管合作”是将各主题紧密关联的重要角色。

关键词：主题演化；颠覆性技术；政策量化；LDA；DTM分类号：TP391.1

# 引言

为了抢占未来发展战略制高点，世界各国在颠覆性技术创新赛道竞争激烈，美英日等主要科技强国已从国家主导创新的层面出台相关技术扶持和治理政策以引领世界产业格局。我国早在 2016 年《国家创新驱动发展战略纲要》[11中也提出要建成世界科技创新强国，发展引领产业变革的颠覆性技术，不断催生新产业、创造新就业。

然而目前我国颠覆性技术及相关产业政策还存在技术保护与监管方面的问题，包括顶层战略布局滞后[2]、应用层监管体系缺位[3]、政策施力结构性失衡[4]等。已有研究认为，可利用战略生态位管理[5]和负责任创新[的思想实现颠覆性技术的政策保护和监管需求。前者为早期易于天折、后期市场受挤压的颠覆性技术开辟专门的成长空间，保护技术研发和落地；后者聚焦颠覆性技术相关的社会利益、伦理可接受度和风险管理等问题，实现对创新过程的监管和治理。出于对解决我国颠覆性技术政策双重需求的考虑，本研究拟围绕技术保护与监管视角，对世界科技强国的颠覆性技术政策进行量化分析，深入挖掘其政策结构及变化规律以供参考借鉴。

作者简介：王晨琳，博士生；刘晓娟，教授，博士生导师，博士,E-mail:lxj_2007@bnu.edu.cn。

在研究视角上，政府主导的技术保护为前期处于边缘市场的颠覆性技术的研发持续推进提供了稳定保障，可直接影响创新效率，因此从保护视角分析世界科技强国的颠覆性技术政策颇具价值，也是现有研究的常见角度。技术监管则是为了更大程度地支持创新。颠覆性技术由于本身的不确定性和高风险性而可能产生无法预估的负面影响，通过适当的政府监管可将其对国家经济、安全和社会的危害降到最低[7]，因此从监管视角进行研究，可以帮助政府预防技术带来的潜在风险和创新损害，降低后期治理成本，进一步保障技术创造的高价值创新成果和知识产权。二者可使政府在鼓励创新和降低风险之间取得平衡，共同促进颠覆性技术及产业的高效持续发展。

在研究方法上，目前颠覆性技术政策量化的主要研究范式为通过政策工具编码进行静态的文本内容分析[8.9]，对动态的演化趋势探索较少。为了把握世界科技强国颠覆性技术政策的关注焦点和发展脉络，本研究将通过主题聚类的方法，深入政策文本内部进行主题挖掘与识别，并结合时序属性分析主题内容和主题强度的演化情况，一方面分析科技强国的颠覆性技术政策发展的总体趋势，一方面探索颠覆性技术在不同时期保护和监管方面关注焦点的变化。

# 1 相关研究

在颠覆性技术政策趋势研究中，早期有部分学者利用文献计量法分析创新政策发展的总体趋势，如 Schummer[1]运用文献计量法，按区域、国家、部门、学科等要素划分，对全球纳米技术领域的科技政策进行评价分析；彭纪生等[1]构建了创新政策计量模型，从政策力度、政策目标和政策措施三个维度探讨创新政策协同演变路径。此类研究依赖于数理统计结果，对政策焦点及演变特征的揭示仍然较为薄弱。

在近期研究中，通过文本计算来进行颠覆性技术政策主题演化分析的方法愈发受关注。黄萃[12指出，通过主题演化分析可从宏观特征层面了解政策的演进规律，在一定程度上预判政策发展趋势。相关研究的主要思想是构建主题聚类模型提取政策关注焦点，并结合时序因素和主题相似度发现政策演进路径与发展趋势。在主题聚类模型中，Blei 等[13]提出的潜在狄利克雷分配模型（Latent Dirichlet Allocation，LDA）广受认可，常用于分析离散数据（如文本语料库)，可在挖掘主题词的同时进行聚类，从单词和语义层面揭示长文本中的隐含主题。Isoaho 等[14]使用LDA模型对欧盟能源联盟所发布政策进行主题建模分析，发现基于词共现和关联概率分布的LDA可用于探索政策语料库中有意义的术语集群，保证聚类结果的可解释性。Zhou 等[15]对中国新能源汽车产业的中央政策进行主题聚类，提取政策主题、施策对象、关键过程和政策举措等维度探索政策演变。张涛等[16]分时期对我国人工智能政策进行LDA主题聚类和相邻时期主题相似度计算，研究各阶段政策主题焦点和演进路径，并通过桑基图进行可视化。华斌等[17]利用LDA模型、相似度计算及共词分析等方法对我国不同层级、不同阶段的高新技术产业政策进行主题挖掘，分析演化规律和脉络。王英泽等[18]对欧盟、英国、美国颠覆性技术政策文本数据进行LDA主题建模，对比各国政策主题词随时间的变化情况，总结政策文本的主题特征。

总的来说，目前围绕颠覆性技术政策主题演化的研究数据覆盖范围有限，大多仍集中在单一国家或地区，对全球先进国家政策经验的整体性探索较少。更关键的是，这些研究多关注政策对颠覆性技术的保护支撑措施，而未对技术高风险性的应对监管治理举措作更多探讨。此外，目前将动态主题演化建模的方法应用于政策文本分析的研究尚少。现有研究主要通过对各阶段政策进行LDA 聚类的方式来挖掘相对静态的政策焦点，系统性和动态性不足；Blei[19]在 LDA 模型的基础上引入时间动态的概念，提出了动态主题模型（Dynamic TopicModels，DTM），该模型在建模过程中即考虑了政策文档的时间影响，可用于分析政策焦点本身随着时间的动态演化情况。

# 2 数据与方法

# 2.1数据获取与处理

# 2.1.1 数据来源

本研究对美国、欧盟、日本和英国四个颠覆性技术发展位于前列的世界科技强国/地区的相关政策文件进行收集，所获取的政策文本均来源于公开的数据资料。为了提高所采集文本数据的精度，限定具体领域政策和综合性政策作为研究对象。综合考虑促进创新和降低风险的双重需求，参考《工程科技颠覆性技术发展展望》蓝皮书[20选择人工智能、量子信息、基因编辑这三种未来我国抢占战略制高点的颠覆性技术方向确定为具体技术领域。

具体检索策略为：在各国/地区的科技部门官方网站使用上述领域的关键词进行专项政策检索和下载。人工智能政策的检索词包括“artificial intelligence”、“AI”、“人工知能”（日语）等，量子信息政策的检索词包括“quantum information”、“quantum technology”、“QI"、“量子技術”（日语）等，基因编辑政策的检索词包括“genome editing"、“embryo editing”、“遺伝子治療”（日语）等。此外，由于涉及科学技术方面的战略规划类文件中也会提及颠覆性技术发展或相关科技创新活动，所以检索词还包括“disruptive technolog\*”、“disruptiveinnovation”、“統合イ／一ンョン”（日语）等。

本研究仅关注中央层级发布的文件，检索时间截至2020年12月31日。最终收集政策文件共92 份，最早可追溯至1990 年，覆盖跨度长达30年，分布情况见表1。Clayton M.

Christensen于九十年代提出“颠覆性技术”这一概念后，不少国家和地区逐渐意识到其对国家未来发展的重要影响，并纷纷采取措施推动和刺激颠覆性技术创新。因此可由本数据集分析世界科技强国随时间推进，其颠覆性技术政策发展的大致趋势和政策焦点的演化情况。

表1样本政策文件分布情况表  

<html><body><table><tr><td></td><td>美国</td><td>欧盟</td><td>日本</td><td>英国</td><td>总计</td><td>发布时间</td></tr><tr><td>人工智能</td><td>9</td><td>4</td><td>6</td><td>5</td><td>24</td><td>18 16 美</td></tr><tr><td>量子信息</td><td>7</td><td>8</td><td>4</td><td>5</td><td>24</td><td>14 总计</td></tr><tr><td>基因编辑</td><td>9</td><td>1</td><td>6</td><td>3</td><td>19</td><td>8</td></tr><tr><td>综合政策</td><td>3</td><td>4</td><td>6</td><td>12</td><td>25</td><td>6 4 2</td></tr><tr><td>总计</td><td>28</td><td>17</td><td>22</td><td>25</td><td>92</td><td>0 开 1990 2000 2001 2002 2005 2006 2009 2010 2011 2013 2014 2015 2016 2017 2018 2019 2020 年份</td></tr></table></body></html>

# 2.1.2 文本预处理

为了提高建模效果，本研究分为三个步骤进行文本预处理。首先进行语种转换。样本政策涉及英文和日文两种语言，由于语法结构和分词模式存在差异，因此本研究使用基于BERT 模型[21]的谷歌翻译进行日转英的语种转换处理。

其次进行文档抽取。由于部分政策文件本身可能包含大段与颠覆性技术及产业发展的政策举措弱相关甚至是无关的文本内容，比如对技术本身原理的描述、对持续性技术创新的促进计划等等，因此本研究通过内容分析法对原始文本进行半结构化处理，剔除无关文本，抽取出 5932个分析单元，每个分析单元视为模型的一份输入文档，按照战略生态位管理[22]和负责任创新[23]的思想对文档进行“保护”和“监管”分类。

最后进行文本清洗。此步骤包括文本分词、词形还原、去除停用词、构建文档-词频矩阵等过程。对于停用词，本研究在 pypi-stopwords、NLTK 英文停用词表的基础上自建颠覆性技术政策停用词表，除了剔除对政策主题建模没有贡献的连词、代词等，还特别在停用词中加入具有强烈的技术特征的词汇（比如 AI，quantum，embryo)，尽量模糊不同技术领域间的聚类偏差，确保输出主题紧密围绕通用型政策措施。

# 2.2政策主题模型构建

# 2.2.1 LDA主题聚类模型

本研究首先基于LDA理论，对颠覆性技术政策文本进行整体主题聚类建模，以挖掘三十年间的政策主题焦点。LDA 模型包含“文档-主题-词”三层结构，在多项式分布“文档-主题”分布和“主题-词”分布上分别加入狄利克雷共轭先验分布，形成贝叶斯框架结构。

本研究通过困惑度[24]（perplexity）和主题一致性[25]（coherence）综合确定LDA模型的最优主题数k。其中困惑度代表聚类结果与真实结果的差距，困惑度得分越低，代表模型的泛化性能越好。一致性指标用于衡量模型生成的主题下词语的语义关联是否更加紧密[26],本研究使用基于原始语料库的U_Mass 算法进行计算[27]。

从保护和监管两个视角分别计算LDA模型在不同主题数（n_topics $\in$ [3,30]，且n_topics$\in \mathbf { N } +$ ）下的困惑度和一致性得分如图1所示。对于保护视角，当主题数n_topics $\scriptstyle \operatorname { \mathtt { \beta } } = 7$ 时，困惑度曲线出现明显拐点（非首次拐点)，且此时一致性得分最高。对于监管视角，当主题数n_topics $^ { = 6 }$ 时，虽未出现明显拐点，但此时一致性得分最高；当n_topics $\scriptstyle \operatorname { \mathtt { i } } = 7$ 时，虽出现拐点，但一致性得分迅速下降。因此最终设定保护视角LDA 模型的最优主题数 $\scriptstyle \mathbf { k } = 7$ ，监管视角的最优主题数 $\scriptstyle \mathbf { k } = 6$ 。

![](images/916dd6ea5d1b1e56c42db8e310b23f662ef479fe9c37f4bfdb7d5821c3989557.jpg)  
图1保护和监管视角下LDA模型困惑度与一致性得分趋势

# 2.2.2 DTM动态主题模型

对于科技政策而言，技术本身随着时间不断发展进步，有必要在颠覆性技术政策的主题聚类中考虑时序因素。本研究使用动态主题模型DTM分析各主题随时间的演化趋势。该模型的核心思想是后一时刻的主题由前一时刻演化而来，从而展现主题变化。DTM将“文档-主题”分布和“主题-词”分布从LDA中的狄利克雷分布改进为逻辑正态分布，并使用高斯过程来建模主题演变。

本研究对文档时间窗口的划分原则为：使各时期的文件数（表1）、文档数（表2）处于相同数量级，便于后续分析对比。由于1990-2014年间的文件数和文档数相较其他年份更为分散，因此将其视为一个时期。最终将政策文档按照发布时间划分至1990-2014，2015,2016，2017，2018，2019，2020年七个时期，并对应设置DTM模型中的时间切片 time_slice。保护、监管视角各个时间窗口对应的文档数见表 2。

表2时间窗划分及对应文档数  

<html><body><table><tr><td>视角</td><td>时间窗</td><td>对应年份</td><td>文档数</td><td>视角 时间窗</td><td>对应年份</td><td>文档数</td></tr><tr><td rowspan="5">保护</td><td>时期1</td><td>1990-2014</td><td>384</td><td>时期1</td><td>1990-2014</td><td>430</td></tr><tr><td>时期2</td><td>2015</td><td>410</td><td>时期2</td><td>2015</td><td>128</td></tr><tr><td>时期3</td><td>2016</td><td>285</td><td>时期3</td><td>2016</td><td>102</td></tr><tr><td>时期4</td><td>2017</td><td>745</td><td>监管 时期4</td><td>2017</td><td>230</td></tr><tr><td>时期5</td><td>2018</td><td>619</td><td>时期5</td><td>2018</td><td>223</td></tr><tr><td>时期6</td><td>2019</td><td>849</td><td></td><td>时期6</td><td>2019</td><td>439</td></tr><tr><td></td><td>时期7</td><td>2020</td><td>816</td><td>时期7</td><td>2020</td><td>272</td></tr></table></body></html>

主题内容和主题强度是动态主题演化中最受关注的主题属性，分析这二者的演化趋势可以刻画颠覆性技术的政策主题变迁特征。其中，主题内容演化主要通过各主题的特征词（主题词）随时间推移出现的变动情况进行分析，反映每个主题的内部发展脉络，体现不同时期的主题间关联性。本研究使用余弦距离计算主题相似度，公式为：

$$
S i m \big ( T e p i c ^ { ( i ) } , T o p i c ^ { ( i + 1 ) } \big ) - c o s \theta - \frac { \sum _ { \ell = 1 } ^ { n } ( T o p i c _ { \ell } ^ { ( \ell ) } \times T e p i c _ { \ell } ^ { ( \ell + 1 ) } ) } { \sqrt { \sum _ { \ell = 1 } ^ { n } ( T o p t c _ { \ell } ^ { ( \ell ) } ) ^ { 2 } } \times \sqrt { \sum _ { \ell = 1 } ^ { n } ( T o p t c _ { \ell } ^ { ( \ell + 1 ) } ) ^ { 2 } } }
$$

（公式I）

将主题相似度结合相似度阈值 $\mathfrak { a }$ 来判定相邻时间窗口下主题的演化关系，通过多次主题建模实验设定 $\mathfrak { a }$ 。当 $\cos \theta \geq \mathtt { a }$ 时，相邻时期主题具有演化关系，包括继承、分裂、新生和消亡四种情况[28]（图 2)。

![](images/39cf69f8032af986b0b4564bff89590c1dbcda3e1b9c3319cd7465b0e8750a53.jpg)  
图2相邻时期主题演化关系示意图

主题强度演化将各时间窗口的主题强度值进行对比和可视分析，从而确定主题随时间推移受关注程度的变化情况，对于研究政策关注焦点的趋势预测具有重要参考价值。本研究采用文档-主题占比的方法计算主题强度，公式如下：

$$
\varphi _ { k } ^ { ( t ) } = \frac { \sum _ { d = 1 } ^ { N } \omega _ { k d } ^ { ( t ) } } { N ^ { ( t ) } }
$$

（公式II)

式中 $\omega _ { k \bar { d } } ^ { ( \ell ) }$ 为时间窗t中文档d的主题k所占的比例，也是第 $\mathbf { k }$ 个主题出现在第d个文档中的概率； $N ^ { ( t ) }$ 为时间窗t中的文档数量。

# 3分析与讨论

# 3.1主题焦点分布

# 3.1.1 技术保护视角

保护视角下颠覆性技术政策文本的主题聚类结果见表3。选取每个主题中概率前十的关键词作为主题词，通过主题-词汇分布提供的信息，对提取出的政策主题进行总结并命名，探索主题的内容含义。主题1是国际交流合作，侧重国际化前沿创新知识交流和外资引入；主题2是人才教育培训，侧重对颠覆性技术及产业的劳动技能和科研水平的教育；主题 3是数字基建部署，侧重为颠覆性技术发展提供数字化基础设施建设;主题4是官产学研协同，侧重各界共建颠覆性技术相关信息共享系统；主题5是阶段发展规划，侧重颠覆性创新管理组织在各时期对技术发展的规划安排；主题6是公私投资支持，侧重对颠覆性技术进行政府投资（公共投资）和企业投资（私人投资)；主题7是疫情背景举措，侧重维持疫情下对颠覆性技术及产业链的支持。

表3保护视角下主题聚类结果  

<html><body><table><tr><td>主题</td><td>主题词</td><td>主题描述</td></tr><tr><td>Topic1</td><td>innovation,echnologynteraional,goverment,inustry,ountry,colaboration,promote,investment,cdemia</td><td>国际交流合作</td></tr><tr><td>Topic 2</td><td>education, student,human,researcher,resource,skill,train,learn,school,support</td><td>人才教育培训</td></tr><tr><td>Topic 3</td><td>data,health,maintenance,environment,communication,promote,utilization,infrastructure,network,digital</td><td>数字基建部署</td></tr><tr><td>Topic 4</td><td>technology,university,ministry,science,information,industry,agriculture,system,food,cabinet</td><td>官产学研协同</td></tr><tr><td>Topic 5</td><td>technology,development,program,committee,science,conduct, provide,national,network,term</td><td>阶段发展规划</td></tr><tr><td>Topic 6</td><td>support,investment,innovation,technology,business,government,fund,sector,private,public</td><td>公私投资支持</td></tr><tr><td>Topic 7</td><td>infection,coronavirus,resource,support,promote,system,strengthen,maintenance,base,environment</td><td>疫情背景举措</td></tr></table></body></html>

# 3.1.2 技术监管视角

监管视角下颠覆性技术政策文本的主题聚类结果见表4。主题1为跨域协作监管，侧重政府进行全局统筹，领导国内业界、学界，联合国际社会，互相协作对颠覆性技术的合规研发和推广进行监管；主题2为社会伦理规制，侧重确保颠覆性技术发展和应用的合法性，保障公众隐私，增强用户信任感；主题3是金融资产管理，侧重对颠覆性项目资金申请的审查和管理；主题4是数据安全框架，侧重数据安全层面的监管，通过标准化和构建框架保障企业和公众权益；主题5是实验资格审查，侧重对风险性颠覆性实验资格进行审查，使其符合道德伦理要求和规范；主题6是监管队伍配备，侧重对研究人员进行道德伦理培训，降低研究过程和技术成果产生ELSI问题的可能性。

表4监管视角下主题聚类结果  

<html><body><table><tr><td>主题</td><td>主题词</td><td>主题描述</td></tr><tr><td>Topic1</td><td>technology,innovation,company,ustrytadard,governmnt,uiversityocial,sienc,intertioal</td><td>跨域协作监管</td></tr><tr><td>Topic 2</td><td>data,system, ensure,public,government, trust, ethical,protection,legal, privacy</td><td>社会伦理规制</td></tr><tr><td>Topic 3</td><td>fund,investment, venture,business,company,capital,project, technology,review,risk</td><td>金融资产管理</td></tr><tr><td>Topic 4</td><td>data,technology,government,innovation,support,standard,business,public,regulatory,framework</td><td>数据安全框架</td></tr><tr><td>Topic 5</td><td>commitee,information,NIH,licence,person,institution,review,guideline,subject, clinical</td><td>实验资格审查</td></tr><tr><td>Topic 6</td><td>system,ensure,process,researcher,decision,technology,data,project,train,impact</td><td>监管队伍配备</td></tr></table></body></html>

# 3.2主题演化特征

# 3.2.1 DTM聚类结果

DTM模型的主题数初始值设置与LDA最优主题数保持一致，即保护视角下每个时间窗口的主题数为7个，监管视角为6个。经过反复实验发现，保护视角的LDA主题“疫情背景举措”是DTM模型在时期7（2020年）出现的新主题，在前六个时期进行DTM聚类时，将主题数设置为7会出现重复类，因此最终将保护视角的DTM模型主题数设置为6个。

取概率排序TOP20 的DTM聚类结果主题词进行可视化呈现，不同时期的相同主题词填以相同颜色，示例见图3。由结果可知，不论是保护还是监管视角，DTM模型在各时期聚类的主题和LDA聚类结果基本吻合，说明颠覆性技术政策在各时期和总体层面的关注焦点保持一致。但各时期的各主题词权重位序发生升降变化，说明同一主题在不同时期的举措侧重发生变化。因此对主题内容和主题强度进一步分析，由主题内容流向观测更为具体的主题演进路径，由主题强度变化探测不同时期焦点变化的趋势。

时期 时期   
主题 1990-2014 2015 2016 2017 2018 2019 2020 主题 1990-2014 2015 2016 2017 2018 2019 2020 technology technology technology technology technology technology technology data data data data data data data innovation innovation inovation innovation innovation innovation innovation standard standard standard standard standard standard standard support support support support support support support technology technology technology technology technology service service industry industy industry industry industry industry industry service service service service service technology technology develop government government develop develop develop develop development development development framework framework framework product government develop develop skill skill skill ensure product produet market market market market framework challenge challenge challenge govermment challenge ensure skil market market product product product product market business program skill challenge government challenge challenge system regulatory framework development development development development programt buld programme ensure ensure govemnm government regulatory system regulat regulat regulato system system   
阶段发展规划 build fuade strae idsa 一 数据安全框 G deseapp esetno Md advance business national fund build fund programme infrastru infrastructure test test test security national fund strategy industrial opportunity opportunity opportunity regulat regulatic nsur est opportunity advance opportunity build strategy national national ensu safety egulatic security test skill market business future national global global safety ensut safety safety egul safety safety potenti opportunity advance nadonai developmen development security security security security safety regulatiot communicatior strategy strategy strategy market advanc

# 3.2.2 主题内容演化

设定保护视角下的政策内容演化的主题相似度阈值为0.7，监管视角下阈值为0.6，将主题演化关系绘制成桑基图（见图 4)。桑基图中方块代表不同时期的不同主题，边代表主题演化流向，边的粗细代表相邻时期的不同主题间相似度的大小。低于相似度阈值的边不予呈现，代表这些主题间不存在演化关系。通过桑基图可以发现政策主题内容随着时间推移产生的更新与变化。

保 1-人才教育培训 2-人才教育培训3-人才教育培训 4-人才教育培训 5-人才教育培训6-人才教育培训 7-人才教育培训 监 1-数据安全框架 2-数据安全框架3-数据安全框架4-数据安全框架5数据安全框架6-数据安全框架 7-数据安全框架  
护 管  
视 1-公私投资支持 2-公私投资支持 3-公私投资支持 4-公私投资支持 5-公私投资支持 6-公私投资支持 7-公私投资支持 视 1-监管队伍配备 2·监管队伍配备 3·监管队伍配备4监管队伍配备5-监管队伍配备6-监管队伍配备 7-监管队伍配备  
角 角5-官产学研协 产学研 7-官产学研协同 6-实验资格审查 7-实验资格审查1-宫产学研协同 2-官产学研协同3-官产学研协同 4-官产学研协同 i7-社会伦理规制5-国际交流合作 6-国际交流合作 7-国际交流合作1-国际交流合作 2-国际交流合作 3-国际交流合作 4-国际交流合作.7-跨域监管合作1-阶段发展规划 2-阶段发展规划 3-阶段发展规划 4-阶段发展规划 5-阶段发展规划 6-阶段发展规划 7-阶段发展规划 社会伦理 社会伦理规 社会伦理规 4-社会伦理规 5-社会伦理规制1-数字基建部署 2-数字基建部署 3-数字基建部著 4-数字基建部著 5-数字基建部 6-数字基建部图 7-数字基建部署 1·金融资产管理2·金融资产管理3-金融资产管理4金融资产管理 5-金融资产管理 6-金融资产管理 7-金融资产管理  
1990-2014 2015 2016 2017 2018 2019 2020 年份 1990-2014 2015 2016 2017 2018 2019 2020 年份

由图4可知，保护和监管视角下的颠覆性技术政策主题演化关系均有分裂和继承两种，不存在新生和消亡。总体上看，保护型政策的关注焦点更具集中性和连贯性，监管型政策主题演化路径更具关联性和融合性。

在单继承演化方面，保护视角的“人才教育培训”、“公私投资支持”和“数字基建部署"三种主题始终为稳定的单继承演化，说明科技强国对颠覆性技术的人力、资金和基建投入方面已基本具备系统深入的政策安排，不易受外部影响而发生变动。监管视角的“数据安全框架”和“监管队伍配备”两种主题稳定推进，也表明在数据治理和专门人才上的集中持续投入。

在分裂融合方面，保护视角下，“官产学研协同”与“国际交流合作”后期的交叉演化关系体现了国内外知识和市场的壁垒消解与深度融合；“阶段发展规划”与“国际交流合作”一直以来的交叉关系则说明了各阶段的战略布局都考虑了国际影响，可以预测今后科技强国会在颠覆性技术领域进一步拓宽战略视野，深化国内外合作，将统筹国内和国际两个大局作为贯穿始终的原则，最大发挥本国颠覆性技术的潜力和价值。监管视角下，“跨域监管合作”是将不同主题紧密关联起来的重要角色。由于该主题涉及的监管主体多样，包括政府、学界、业界、公众甚至是国际社会，因此既与学界主导的“实验资格审查”发生融合，又与公众关心的“社会伦理规制”持续关联，还与业界涉及的“金融资产管理”有所联系，最后继承了来自四种不同主题的支流，内容十分丰富。

# 3.2.3 主题强度演化

为了反映同一时期颠覆性技术政策对不同主题的关注侧重，以及同一主题在不同时期受关注度的变化，绘制保护和监管视角下主题强度演化折线图见图5，横轴为各时间窗口，节点表示在对应时间窗口文档集合中某主题占比（即主题强度)，从而呈现科技强国在颠覆性

技术保护与监管方面工作重心的转移情况。

![](images/01d86e3a1a3ebce301d46d919517e964e280dcb51bc5de4329f7a405150faeee.jpg)  
图5双视角下颠覆性技术政策主题强度演化折线图

由图5可知，保护视角与监管视角的政策主题均包含衰减型、增长型和波动型三种。保护型政策中，“阶段发展规划”属于衰减型主题，在2015年以前占据绝对焦点地位，随时间推进，与其他主题的强度差值逐渐减小，但主题强度始终属于高位，这体现了科技强国在技术保护方面早期重点关注政策统筹布局、后期倾向“规划先行、多措并举”的总体态势。“国际交流合作”和“官产学研协同”属于增长型主题，“数字基建部署”“公私投资支持”“人才教育培训”属于小幅波动型主题。在2018年时，六个主题间强度差距最小，主题分布最为平均，对于颠覆性技术的保护形式也最丰富。

与保护视角相比，监管视角下没有明显的领导型主题。其中，“实验资格审查”属于衰减型主题，在早期的热度较高。“跨域协作监管”和“金融资产管理”属于大幅波动型主题，前者在 2020 年主题热度回升，意味着新焦点的出现；后者始终保持相对热门的位置，说明对科研资金、企业资产的监管深受重视，把握经济命脉是应对风险研发行为和整治市场乱象的关键举措。“社会伦理规制”属于增长型主题，说明近些年科技强国逐渐加深对颠覆性技术带来的社会伦理冲突的认识，并对其进行有效的伦理规制。“监管队伍配备”和“数据安全框架”属于小幅波动型主题。2016年是“监管队伍配备”主题的转折点，这表示在该主题中发现了更具价值的焦点问题，2019 年时成为当年最热主题，随着解决举措的完善，此后主题强度降低。“数据安全框架”主题强度起伏不大，2015年后总体基本保持在中间位置，说明在数字化时代，数据安全、网络安全的监管和治理一直都是政府关注的对象。

# 4结论与建议

本研究围绕颠覆性技术保护和监管的政策需求，对美、日、欧、英等科技强国的政策主题进行焦点挖掘和演化分析，发现两种视角均存在衰减型、增长型和波动型三类主题，保护型政策的主题演进路径更为集中连贯，监管型政策主题间更为相关相容。为应对我国在颠覆性技术政策发展中存在的顶层设计、监管体系和政策协同等方面问题，本研究从科技强国的

政策经验中总结出如下可借鉴之处：

（1）重视顶层规划对颠覆性技术创新生态双循环的指引作用。我国可参考世界科技强国“规划先行、多措并举”的技术保护思维，特别注意打破目前细分领域中战略布局跟跑技术变革的被动局面，结合技术成长阶段需求和国家战略需求超前部署顶层规划，通过稳定深入的人力、资金和基建等要素的政策安排确保创新内循环，通过官产学研与国际知识、市场的合作实现创新外循环，高效畅通的创新生态双循环系统可进一步提高颠覆性技术保护空间的韧性和延展性。

（2）强化跨域合作在颠覆性技术监管治理体系中的桥梁角色。技术监管治理体系涉及多元监管主体，我国在搭建信息安全框架和配备专门监管机构的基础上，需加快颠覆性技术的道德、法律、风险研究进入国家主导的体制化阶段的进程，加强政府与学界、业界、公众甚至是国际社会之间的跨域协作监管，从点到面地构建由政府主导的全域、全时态、全民化的监管治理体系[29]，各方配合实现法律出台、标准制定、资格审查、金融监管等治理举措的顺利推进，从而有效预防技术市场垄断、遏止信息侵权行为的发生。

（3）提高政策协同在特殊时代下颠覆性技术发展的应变效用。当今世界正处于大变革中的后疫情时代，对颠覆性技术的施策举措的灵活性提出了更高要求，科技强国也十分关注在新冠疫情中的颠覆性技术政策措施。对此，我国一方面需注意跟踪落实阶段政策效益，防止因政策频繁变动和断层而危及政府信用或破坏良序创新环境；另一方面应重视部署颠覆性技术创新管理的突发事件预警体系和应急处置预案系统，从容应对全球性或民族性公共突发事件带来的技术发展危机。

本研究存在的局限为：在进行动态主题建模时，将DTM各时期主题数的初始值对标LDA 最优主题数，最终发现焦点主题在各时期和总体上具备一致性。但此过程导致了其他潜在的边缘主题被屏蔽的问题，缺少对非焦点主题的演化认知，比如可能出现本研究未探知到的主题的新增和消亡。未来拟增加DTM的聚类主题数以发现更多聚类效果，或对每个时期进行独立LDA聚类，再根据主题相似度判断演化关系，以此探索非焦点型政策主题的变迁过程。

# 参考文献

[1]中共中央，国务院．《国家创新驱动发展战略纲要》[EB/OL].[2016-05-19][2022-04-18]. http://www.gov.cn/gongbao/content/2016/content_5076961.htm.   
[2]叶珍珍,范琼,汤书昆.欧美量子科技政策及其背后相关科学家分析[J].世界科技研究与发 展,2021,43(01):77-88. [3]陈文进．中国基因编辑技术发展与政策促进研究[D].华中农业大学,2020.   
[4]张瑶,张光宇.双重视角下颠覆性创新的政策文本分析[J].技术经济与管理研究,2021(11): 35-40.   
[5]黄子洋,余翔,尹聪慧.颠覆性技术的政策保护空间研究—一基于战略生态位管理视角[J].科 学学研究,2019,37(04):607-616.   
[6]Van den Hoven J. Responsible Innovation Managing the Responsible Emergence of Science and Innovation in Society [J]Value Sensitive Design and Responsible Innovation,20l3:75-84. [7]DCMS. Digital Regulation: Driving growth and unlocking innovation[EB/OL]. [2022-06-13] [2022-09-02]. https://www.gov.uk/government/publications/digital-regulation-driving-growth-and -unlocking-innovation/digital-regulation-driving-growth-and-unlocking-innovation.   
[8]Lin C C, Yang C H, Shyuaa J Z. A comparison of innovation policy in the smart grid industry across the pacific: China and the USA[J]. Energy Policy, 2013(57):119-132.   
[9]唐德龙,马翔,廖思爱,丁堃,徐作圣.欧美量子通信产业创新政策量化比较研究[J].中国科技 论坛,2020(4): 160-170+179.   
[10]Schummer J. The global institutionalization of nanotechnology research: A bibliometric approach to the assessment of science policy[J]. Scientometrics,2007,70(3): 669-692.   
[11]彭纪生，仲为国，孙文祥.政策测量、政策协同演变与经济绩效:基础创新政策的实证研究 [J].管理世界,2008(9):25-36.   
[12]黄萃.政策文献量化研究[M].北京：科学出版社,2016:4.   
[13]Blei D M, Ng A Y, Jordan M I. Latent Dirichlet Allocation[J]. Journal of Machine Learning Research,2003, 3:993-1022.   
[14]Isoaho K, Moilanen F. A Big Data View of the European Energy Union: Shifting from‘a Floating Signifier’ to an Active Driver of Decarbonisation?[J]. Politics and Governance,2019, 7(1):28-44.   
[15]Zhou N, Wu QS, Hu XP. Research on the Policy Evolution of China's New Energy Vehicles Industry[J]. SUSTAINABILITY, 2020,12(9): 3629.   
[16]张涛,马海群.中国人工智能政策主题热点及演进分析[J].现代情报,2021,41(11):150-160. [17]华斌,康月,范林昊.中国高新技术产业政策层级性特征与演化研究—一基于 1991—2020 年6043 份政策文本的分析[J].科学学与科学技术管理,2022,43(01):87-106.   
[18]王英泽,化柏林.欧美国家颠覆性技术政策文本数据的主题建模分析研究[J].情报理论与实 践,2022,45(06): 39-47.   
[19]Blei D M, Lafferty JD. Dynamic topic models[C]/In Proceedings of the 23rd international conference on Machine learning,2006:113-120.   
[20]工程科技颠覆性技术战略研究项目组.工程科技颠覆性技术发展展望(2019)[M].北京：科 学出版社,2019.   
[21]Devlin J, Chang M W, Lee K, et al. Bert: Pre-training of deep bidirectional transformers for language understanding[J].arXiv preprint arXiv:1810.04805,2018.   
[22]Rip A. A Quasi-Evolutionary Model of Technological Development and a Cognitive Approach to Technology Policy[J]. RISESST,1992(2): 69-102.   
[23]HELLSTROM T. Systemic innovation and risk: technology assessment and the challenge of responsible innovation[J]. Technology in Society, 2003, 25(3): 369-384.   
[24]Wiki Pedia.Perplexity [EB/OL]. [2020-09-06][2021-12-03]. htps://n.wikipedia.org/wiki/ Perplexity.   
[25]Mimno D, Wallach H M, Talley E, McCallum A. Optimizing Semantic Coherence in Topic Models[C] //Proceedings of the Conference on Empirical Methods in Natural Language Processing.Association for Computational Linguistics,2011: 262-272.   
[26]陈果,吴微.细分领域 LDA 主题分析中选词方案的效果对比研究[JJ.情报理论与实 践,2019,42(06):138-143.   
[27]Keith S,Philip K M, David A, David B. Exploring Topic Coherence over many models and many topics[C]/Proceedings of the 2012 Joint Conference on Empirical Methods in Natural Language Processing and Computational Natural Language Learning. Korea: Association for Computational Linguistics, 2012: 952-961.   
[28]戴娣．基于LDA 模型的政府改革发展主题演化分析[D].中南财经政法大学,2019. [29]郭剑鸣,赵强.智慧社会视域下的政府监管创新：使命、困境与进路[J].社会科学战 线,2021(06):199-208.

# 作者贡献说明：

王晨琳：设计研究方案、数据收集与分析、论文撰写及修改；  
刘晓娟：提出研究主题与方向、论文最终版本修订。

# Research on Topic Evolution of Disruptive Technology Policies from the Perspective of Protection and Regulation

Wang Chenlin, Liu Xiaojuan

School of Government, Beijing Normal University, Beijing 100875

Abstract: [Purpose/Significance] Starting from China's demands for protection and regulation of disruptive technologies, this study provides reference for China's policy development direction by mining the focuses and evolution characteristics of related policies of the world's major powers. [Method/Process] Based on the set of disruptive technology policies during 1990-2020，the focuses distribution of policy topics is explored by LDA, and DTM is constructed by introducing time-series factors to analyze the evolution of the content and intensity of policy topics in different periods,and summarize the key policy experience of the major powers.[Result/Conclusion] This study divides the disruptive technology policies into seven periods. The evolution of policy focuses from the perspective of protection and regulation has three types: attenuation, growth and fluctuation. Relatively speaking,the protection policy topics are more centralized and coherent, and there is an obvious leadership topic "phased development planning". While the regulation perspective does not have a fixed leadership topic,but the topic integration range is larger, of which "cross domain regulatory cooperation" is an important role that closely links various topics. Keywords: Topic Evolution; Disruptive technology; Policy quantification; LDA; DTM