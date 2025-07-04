# 基于大数据的文化心理分析

吴胜涛1,2 吴舒涵 朱廷劭²1（厦门大学社会与人类学院，厦门 361005）²（中国科学院心理研究所，北京100101）3（厦门大学新闻与传播学院，厦门 361005)

（通讯作者:吴胜涛,Email: commuagent@163.com or michaelstwu@xmu.edu.cn; 朱廷劭: Email:tszhu@psych.ac.cn)

# 摘要

摘要：本文旨在回顾研究者近年来使用大数据方法分析文化价值观以及社会变迁、生态地理效应的研究。在社会变迁方面，谷歌电子图书语料库、社交媒体和文学语料库被用来展示伴随城市化以及短期内经济放缓的文化变迁；在生态地理方面，研究者基于Twitter或新浪微博文本语料库，考察了“一带一路”沿线国家或地区的文化多样性，中国农村与城市地区的文化价值失调与主观幸福感，以及中国不同城市的空气污染与文化适应。此外，本文还讨论了传统研究方法和大数据分析法的结合使用，以及文化大数据分析的各种挑战和未来前景。

摘要：大数据，文化，价值观，社会变迁，生态地理

# Cultural analysis based on big data: Evidence from social change and ecological geography

Michael Shengtao WU1 ,2 Shuhan WU³Tingshao ZHU² 1(School of Sociology and Anthropology, Xiamen University, Xiamen 361005) 2 (Institute of Psychology, Chinese Academy of Sciences,Beijing 100101)   
3 (School of Journalism and Communication, Xiamen University, Xiamen 361005)   
(Corresponding Author, Michael Shengtao WU, Email: commuagent@163.com or michaelstwu@xmu.edu.cn; Tingshao ZHU, Email: tszhu@psych.ac.cn)

# Abstract

This paper aims to review our recent studies using big data to unpack cultural values and their functions in response to social change and ecological geography. On social change,Google digitized books, social media,and literature corpus were used to demonstrate the cultural shift along with urbanization over past decades and economic recession in a short period. And on ecological geography, tweets or Sina micro-blogs were analyzed to examine the cultural diversity across Belt-Road societies,cultural value mismatch and welbeing in rural versus urban areas in China,and air pollution and cultural adaption in Eastern versus Western cities in China. In addition, we recommend a combined use of traditional method and bid data,and the limitations and future directions are also discussed.

Keywords: Big data, culture, value, social change, ecological geography

随着移动互联网技术的发展，基于在线网络和通信记录的大数据正深刻影响着我们的生活、工作和思维。大数据技术的历史并不长，但从近十年的大量文献来看，它已经成为当前哲学、自然科学和社会科学领域关注的重要问题，并为社会科学研究提供了继实验、理论、仿真之后的第四种研究范式，甚至催生出了计算社会科学这一独立学科的诞生[1-2]。

早期的大数据心理研究多集中在基本情绪、消费决策等相对直观的心理概念上，针对文化、性格等抽象心理概念的大数据研究则相对较少[3]。然而，随着计量语言学和机器学习技术的发展，基于大数据的文化心理分析也变得切实可行。本文从时间、空间两个维度，回顾了研究者使用大数据方法来分析文化价值观及其社会变迁、生态地理效应的研究；进而，对主要的语料库以及特征词典、机器学习模型进行了梳理，并对文化大数据分析的挑战和前景进行了讨论。

# 1大数据的特征和优势

一般意义上讲，大数据是指无法在可容忍的时间内用传统IT技术和软硬件工具对其进行感知、获取、管理、处理和服务的数据集合[4]。大数据具有庞大、方便、精确和经济便宜的特性，因此迅速在各个研究领域中展露头角，也逐渐成为社会科学的新工具[5]。与传统的数据研究方法相比，大数据具有无可比拟的优越性。首先在数据量方面，大数据具有比传统数据分析更大、更全面的数据量，能够同时分析大量数据；第二，在结构方面，大数据有结构化、半结构化和无结构化三种形式，传统的数据通常是结构化的，易于标注和存储，而现在Facebook，Twitter，YouTube以及其他用户产生的绝大多数数据都是非结构化的；第三，在数据来源方面，传统的数据分析收集的数据覆盖面低，较为集中，而大数据收集的数据则覆盖面广，分散性强；第四，在数据处理速率方面，传统数据分析时效低、速度慢，而大数据处理是即时的、速度快，速度能够与数据产生的速度相匹配。

目前利用大数据对文化心理的分析主要有两种方法：第一种是基于词典的频次分析，如通过对数字、表情和语言等方面的关键词进行分析，研究个体或群体的情绪、价值观等，这是一种相对简单、粗糙的分析3；第二种是基于模型的预测分析，如通过机器学习模型对用户的个性、价值观和意识形态进行识别，这种方法更加精确，对心理特征的把握也更全面[5]。

利用上述两种分析路径，可以对文化心理进行时间、空间两个维度的分析：在时间维度上，可以进行社会变迁背景下的趋势分析，例如，文化在城市化和全球化等背景下的历史变迁，经济波动带来的价值改变，不同年代人物的性格变化;在空间维度上，可以进行生态地理分析，例如，文化在某一特定政治、经济框架内的地区差异，不同户籍制度造成的城乡差异，不同生态环境下的文化适应。

本文旨在回顾研究者使用大数据分析文化价值及其社会变迁、生态地理效应的研究。同时，我们还讨论了大数据的伦理和方法局限，以及未来需要对传统方法和大数据方法进行交互验证的必要性。

# 2时间分析

首先，从时间的角度，研究者利用谷歌电子图书、社交媒体和文学语料库，对城市化背景下以及经济新常态以来的文化变迁进行了分析。在分析方法上，主要采用了基于关键词词典或特征行为的频次分析和基于机器学习的预测模型。

# 2.1历史发展与文化变迁

文化的形式多种多样，但几乎所有涉及文化的概念都被构造为个人和群体之间的关系，强调个体价值、目标的文化通常被称之为个体主义，强调群体价值、目标的文化通常被称之为集体主义一一个体主义/集体主义也是讨论最为广泛的文化心理概念[。众多研究表明，物质财富的增长和社会生态由农村向城市的转变是当今社会最重要的变化趋势之一；进而，文化价值也发生了巨大变化一一世界范围内均出现了个体主义增强的趋势，集体主义在减弱或受到挑战[8]。

人类文化常常体现在语言当中[9],而Google 电子图书恰好提供了一个巨大的、跨度上百年的语料库，其中语言特征可以用来识别文化价值观及其历史变化趋势[1010。基于个体主义关键词（如自我、独特）和集体主义关键词（如集体、服从）的趋势分析表明，随着社会现代化、城市化变迁，英语、汉语中的个体主义词汇使用越来越频繁，而集体主义词汇使用越来越少、或相对稳定[11-13]；以第一人称单数作为个体主义指标的分析表明，美式英语、汉语、法语、德语、西班牙语、希伯来语、意大利语、俄语在二战以后均表现出个体主义上升的趋势[13-14]。

为了进一步从社会变迁的角度研究文化及其行为特征的变化，研究者还对中、美两国1960-2008 年间的情感表达进行了分析[15]。长期以来，爱和感情一直被认为是人类的基础需求，人类天生具有情感交流的能力，通过言语行为（如说“爱你”、“喜欢你”）和非言语行为（如拥抱、亲吻）来传达爱意和建立亲密关系[16]。同时，人类行为又是文化的产物，城市化和全球化带来的个体主义价值观势必影响了人们对亲密关系和爱的表达方式，个体主义文化更加强调言语或非言语情感的直接表达8。研究使用了谷歌电子图书的美式英语、简体中文语料库来检测情感行为关键词在1960年至2008年间的变化，以及它们与个体主义增长之间的关系。结果表明，尽管情感关键词在中文图书中的出现频率低于英文书籍，但二者在近几十年来均呈显著上升趋势。此外，个体主义与中美书籍中情感词汇的出现频率呈正相关。这些结果进一步证明，文化变化影响情感交流方式，即情感交流在适应个体主义的城市环境过程中变得更加流行[5]。

# 2.2经济波动中的文化变迁

文化是人类适应环境的结果，而环境的变化不仅表现在长时程的历史变迁，也表现在短时程的经济波动，后者也会引起人类文化的短期调整。最近的研究表明，在个体主义为主流价值观、且不断增强的美国社会，大萧条时期的青少年却表现出集体主义（如关注他人和环保主义）的增加，并显示出个体主义（如物质主义）减少或趋于平缓的一些迹象[17。此外，随着经济繁荣或失业率减少时，美国人会更可能给新生儿起不常用的名字，拥护孩子的自主权，并偏爱自我中心的音乐；相反，当经济衰退或失业率增加时，美国人更愿意鼓励孩子帮助他人和被他人喜欢，更加喜欢表达他人取向的音乐。[18]。

尽管改革开放以来，中国经历了增长奇迹，但2010年以后经济增长放缓，GDP增长率从 $10 . 6 \%$ 降至 2012年的 $7 . 7 \%$ ，下降了近三个百分点[19]。为了进一步探究文化作为对生态变化的回应，是否可以或者在何种程度上发生短时程的适应性改变，研究者对 2010到2016年期间的集体主义行为进行了分析[20]。

通过大数据在文化趋势分析的运用，本研究对新浪微博活跃用户的行为足迹进行了分析。从文化的角度来看，提及他人或与他人交谈（如微博上的“@UserName”行为）是互依自我的体现，可以作为集体主义行为的指标[17]。结果显示，用户的集体主义（提及或与他人交谈）在七年中发现了显著变化，集体主义的峰值出现在 2011-2012年的经济衰退期，而在2013-2016 年经济回到正轨时，集体主义又回到了常态。这表明，中国社交媒体上的文化行为也会随着经济波动而上升或下降[20]。上述研究揭示了文化在短期内的演变，即文化在适应生态环境方面不是稳定不变的，而是灵活多变的。

# 2.3文学作品中的文化变迁

个体的人格或性格是基因、环境交互作用的结果，因此，深深嵌套在其赖以传承的文化传统里[21]，也生动地呈现在该文化的日常语言和文艺作品里[22-23]。尽管在个体层面，性格是一个人对现实稳定的态度和习惯化的行为方式，但在社会层面，不同的时代往往会鼓励不同的性格，进而导致理想性格的不同。例如，随着现代化和城市化变迁，开放性和外向性人格变得更加重要，因为生活新时代的个体需要更多探索外部世界和更加轻松自由的人际关系[24-25]。

近几年来，随着计算机自然语言和机器学习技术的日益成熟，通过人工智能方法对小说人物性格及其背后的文化特征进行分析已经成为可能。本研究采用中国科学院心理研究所计算网络心理实验室研发的“文心”中文心理分析系统和大五人格预测模型[26]，对各个人物的性格进行文学智能分析。首先，选定小说文本，分别提取小说人物的全部对话；然后进行分词，并根据"文心"系统对分词得到的所有词汇进行词汇统计，得到词类分布结果；最后，基于大五人格预测模型得到各个人物的大五人格预测分数。

通过上述方法，研究者对《平凡的世界》这一反映改革开放初期普通中国人成长、奋斗故事的小说人物进行分析。结果发现，年轻一代的知识青年孙少平、田晓霞在开放性得分上要高于他们家庭中的长子孙少安、田润叶，这反映了经历改革洗礼的孙少平和田晓霞接受新思想、喜爱冒险的性格特点[27]。此外，我们还分析了金庸小说中的35位女侠进行文学智能分析，结果发现，相对于传统女侠（如相夫教子的双儿），现代女侠（如聪明不羁的赵敏）在外向性得分更高，这反映了二战后中国女性独立自信、敢爱敢恨的新形象[28]。上述研究通过文学智能分析的呈现的不同人物性格画像，反映新时代的人物心理特点。

# 3空间分析

从空间的角度，研究者利用Twitter、新浪微博等社交媒体数据，考察了“一带一路"沿线的文化多样性，中国农村与城市地区的文化价值失调和主观幸福感，以及中国东、西部城市的空气污染与文化适应。

# 3.1“一带一路”沿线的文化差异

文化是影响区域合作、经贸往来的重要因素，如个体主义者更愿意与他人建立经贸合作关系，而集体主义者的经贸合作意愿相对较低，并且在交易对象选择上更偏好熟人[29]。因此，分析“一带一路”沿线国家或地区的民心特点，并找到有效的合作交往模式，是关系到国家战略实施的重大问题。但是，由于地域辽阔、民族众多，且地缘政治、经济、文化因素（如原苏联影响、欧美国家殖民、宗教传统等）异常复杂，传统的抽样统计调查无法做到全样本分析，也很难通过统计调查的方式让作答者准确地主观报告，社交媒体大数据可以提供一个海量、及时的用户行为痕迹的精准数据库，还可以通过建模对某个领域和问题进行预测分析。因此，吴胜涛等人结合文化心理学和大数据分析技术，利用社交媒体Twitter数据来分析“一带一路”沿线国家或地区的自我表征特点（独立性或个体主义），以探究区域合作交往的行为模式，即：自我表征是独立，还是互依；人际关系偏好是陌生人之间的普遍信任，还是熟人间的特殊信任[30]。

研究者以社交媒体Twitter单数第一人称代词的使用比例（自我独立性）作为个体主义指标，并进行归一化处理，获得“一带一路”沿线69个国家或地区个体主义文化的分布情况；然后，为了获得“一带一路”沿线国家或地区社会信任情况，提取世界价值观调查（WVS）数据库中28个“一带一路”沿线国家或地区的社会信任度（普遍信任、特殊信任），并建立个体主义与社会信任的训练模型。最后，以个体主义为自变量、社会经济学变量为控制变量（如人均GDP、基尼系数和城市人口比例），建立社会信任的线性回归预测模型，对“一带一路'沿线国家或地区社会信任分数进行预测[30]。

结果表明，“一带一路”沿线国家或地区在个体主义文化指标上存在较大的变异，且主要受欧美国家殖民历史和当地宗教传统的影响，其中欧美国家殖民历史是个体主义最大的影响因素；此外，个体主义较高的国家或地区更依赖陌生人之间的普遍信任，而较少依赖熟人之间的特殊信任；同时，根据结果可将69 个“一带一路”沿线国家或地区分成三类：第一为欧美模式，即非伊斯兰的后殖民国家或地区，具有较高的个体主义；第二为伊斯兰模式，即信仰伊斯兰教的后殖民国家或地区，具有较高的集体主义；第三为苏联模式，原苏联所属或未被欧美殖民过的国家，其行为特点介于个体主义和集体主义之间[30]。

此外，研究者还基于100万微博活跃用户，运用词频分析的方法绘制了中国个体主义/集体主义的心理地图[31]。具体而言，采用已经得到验证的中文文本分析软件“文心”系统，利用以往基于个体主义/集体主义的跨文化研究提到的与个体主义、集体主义有关的词汇，经过讨论后得到个体主义词汇53个、集体主义词汇64个；然后，根据被试标注的“注册地点”来统计不同省、市、自治区的个人主义/集体主义的词频，比较个体主义和集体主义在省级层面的地区差异。结果发现，南方人的个体主义高于北方人，海外用户的个体主义高于国内用户、集体主义低于国内用户，证明在一个国家内部也存在个体主义/集体主义的地区差异。

# 3.2城市化与文化价值失调

从进化的角度来看，集体主义具有“抗精神病理”的适应价值。大量的研究表明，集体主义对社会绑定和人类福祉发挥着重要的作用，集体主义越高的人主观幸福感也越高（如较多的积极情绪、较少的消极情绪），在资源匮乏、环境威胁条件下该效应尤为明显[32。然而，随着现代社会变迁与快速城市化，个体主义不断增长，集体主义受到挑战，人们难免会出现个人-环境的文化价值失调一一内心一直习惯或坚守着集体主义文化价值观，而外部的生态环境却突然变了，于是就容易体验到心理压力或不幸福。

研究者以城市化水平为调节变量，检验集体主义与主观幸福感的关系，并假设：在低城市化水平地区，集体主义与幸福感的相关较强；在高城市化水平地区，集体主义与幸福感的相关较弱。此外，考虑到以往的小样本调查难以回答城市化这样的宏观问题，本研究采用以词频分析为基础的微博大数据分析和全国大样本调查数据相结合的方法，进行群体和个体两个水平的分析[3]。

研究一基于微博基本情绪词表（Weibo-5BML）［34]，对 2014年中国大陆31 个省/市/自治区的160万微博活跃用户的微博内容进行情感分析，结果发现：总体而言，省级水平的集体主义分数显著地负向预测微博用户的消极情绪（如悲伤、愤怒、恐惧、厌恶）；城市化水平对集体主义与消极情绪的关系起调节作用，即在城市化较低的地区（如贵州、甘肃），集体主义与微博用户消极情绪显著负相关，在城市化较高的地区（如北京、上海）这一关系则不显著；对于积极情绪（如快乐），集体主义的效应不显著，城市化水平的调节作用也不显著。

研究二基于中国家庭追踪调查 2010 年全国近3万人的个体访谈数据[35]，采用多水平回归模型分析，结果发现：个体的集体主义显著正向预测积极情绪、负向预测消极情绪；城市化水平对集体主义与主观幸福感的关系起到调节作用，即在城市化水平较低的地区，集体主义越高则积极情绪越多、消极情绪越少；而在城市化水平较高的地区，集体主义对积极情绪、消极情绪的影响均不显著。

随着急剧的社会变迁，乡土中国及其孕育的集体主义文化价值观正在发生分化，本研究通过社交媒体的群体分析和全国样本的个体分析，揭示了中国社会快速城市化过程中个人-环境失调的民意现实以及主观幸福感的社会心理机制。一方面，在近年来快速发展的城市里，总体属于集体主义的中国人或许并没有立即适应商业、陌生人为主的生态环境，因而出现了价值失调，并感受到较低的幸福感；另一方面，一些仍然生活、工作在乡土环境（或者流动地生活在城市边缘）的人，却主动或被动地置身于个体主义的价值诱惑中，这种价值失调也会带来较低的幸福感。值得注意的是，本研究用传统的大样本调查数据重复验证了微博大数据的结果，克服了单纯采用大数据可能导致结果不精确的局限。

# 3.3空气污染与文化适应

大量研究表明，文化会受到生态环境的影响，例如，在相对恶劣的生态环境下，人们会更多地表现出互依型的文化，在性格上也更倾向于自保，与自我成长有关的外向性、开放性和尽责性相对较低[3。而在多种成因理论中，气候一经济理论（Climato-Economic Theory）同时考虑了自然环境和社会环境对个体主义一集体主义的影响，从经济发展和气候环境交互作用的角度检验了个体主义一集体主义的成因，并且进行了跨文化验证[3]。空气污染是工业社会新出现的环境威胁，正对人类的生存条件和广泛的心理与行为产生根本性的影响。因此研究假设，空气污染能够正向预测该地区居民的集体主义倾向、负向预测个体主义倾向。

研究者选取北京、上海、成都三个城市/城区2015 年和 2016 年两年的以 PM2.5为主要污染物的空气质量数据。选取理由是：这三个城市分别可以代表北方、南方、西部，经济发展水平、整体空气质量均存在一定的差异，并且 $2 0 1 5 \sim 2 0 1 6$ 年的污染天数较多。原始数据以小时为采样单位，指标为空气质量指数（AirQualityIndex，AQI），数值越大表示污染越严重。对于微博数据，参考前人研究的关键词[13.38]，并考虑到微博内容的特点，共确定了个体主义关键词27个、集体主义关键词36个，进而使用正则表达式对每一条微博进行关键词搜索匹配，然后对频次进行加合分别得到个体主义、集体主义的分数。此外，根据“http：//t.cn”、“http：//m．weibo．cn”等关键词排除了转发外网站链接或可能涉及广告的微博，并根据微博文本剔除了重复的微博。

最后，我们对日期水平的空气污染程度和个体主义、集体主义微博进行相关分  
析，并建立日期水平的个性主义、集体主义与空气污染的多水平回归建模3。结  
果表明，从总体来看，空气污染与个体主义显著负相关，与集体主义显著正相关当空气污染比较严重时，人们会意识到所在群体内所有个体的生理和心理都  
共同受到了空气污染的威胁；同时，研究结果也存在一定的地区差异性，对于成  
都市居民，空气污染对个体主义、集体主义的预测效果显著，但对于北京市和上  
海市的居民这一效应并不显著，即经济发展水平与空气污染对个体主义和集体主

义表达起调节作用。这一模型在一定程度上支持了气候一经济理论，即恶劣的气候环境在低收入水平的地区会带来更高的集体主义倾向。

# 4局限与展望

虽然大数据分析已经在社会科学研究领域展露头角，相对于传统方法具有难以比拟的优势，但利用大数据进行文化分析仍然具有一定的局限性。

首先，数据收集方面，网络大数据有许多不同于传统科学数据的特点，包括多源异构、交互性、时效性、社会性、突发性和高噪声等，不但非结构化数据多，而且数据的实时性强，大量数据都是随机动态产生3，因此通过大数据搜集到的很多信息是重复的或者是没有意义的，会造成一些没必要的资源浪费。

其次，在数据精确性方面，即便计算机技术和数据采集技术的飞速发展，但大数据分析得出的结果仍是不够精确的，线上的分析主要基于对于语义的猜测，大数据分析中的频次分析提取的关键词具有多义性，因此得到的信息是不准确的。

再次，在数据使用方面，虽然进行文化分析的最终目的是谋求不同国家和文化之间的相互理解，了解对方差异，最终促进共同发展，但是某些霸权主义国家会利用大数据文化分析的结果来干预其他国家的政治事务和文化战略，最终使得大数据文化心理分析演变成为攻击其他国家的武器。

最后，在数据隐私和安全方面，虽然基于大数据的文化心理分析是针对集体或者地区的文化心理，但由于群体的文化数据是基于每一个个体数据集成得来的，因此收集和分析数据仍然会涉及个人隐私。随着在线网络服务和网络用户的增长，个体使用网络的机会增多，因此个人隐私问题得到了日益广泛的关注，如何平衡和把握个人隐私和研究需要之间的关系仍需要进一步考虑和探讨。

因此，在今后的研究中，需要努力克服大数据在文化心理分析方面的局限性。首先，为了提高数据的精确性，可以将线上大数据分析和线下传统数据分析相结合，即与直接信息相结合，同时作为数据收集和分析的算法模型也需要进一步发展和精确。第二，为了避免数据分析结果被滥用，全球研究者应共同谋求相应的解决措施和共通的数据法律来解决基于大数据的国家或地区文化心理分析的不当使用。第三，应将研究伦理置于大数据分析的首位，将保护个人隐私作为首要准则，推动建立数据隐私保护相应的法律法规。

# 5总结

总之，本文回顾了研究者近年来将大数据分析方法应用到文化心理及其社会变迁、生态地理效应等多个领域的研究。具体而言，研究者采用了频次分析、行为分析和预测模型等方法，对文化心理进行了时间趋势分析和空间地理分析，为文化心理研究提供了全新的研究思路和分析方法。

然而，值得注意的是，大数据并不只是心理学数据采集方式的改变以及统计分析方法的数据驱动化，或者研究对象样本量的增加[40。基于大数据的文化心理分析，在为传统文化心理学研究提供新方法的同时，也具有极高的政治、经济和文化应用价值，同时也存在巨大的伦理和政治风险。

# 参考文献：

(eds.），The Fouth Paradigm: Data - Intensive Scientific Discovery，Microsoft Corporation, 2009，pp.xvii - xxxi.   
[2] Lazer D,Pentland A,Adamic L,Aral S, Barabasi A-L,Brewer D,et al. Computational Social Science[J]． Science，2009，323(5915) :721-724.   
[3] Golder S A, Macy M W. Diurnal and seasonal mood vary with work, sleep,and daylength across diverse cultures[J]. Science，2011，333(6051) :1878-1881.   
[4]李国杰．大数据研究：未来科技及经济社会发展的重大战略领域——大数据的研究现状与科学思考［J]. 中国科学院院刊，2012，27(06):647-657.   
[5] Kosinski M.， Matz S.，Gosling S.，Popov V.，& Stillwell D. Facebook as a research tool for the social sciences: opportunities， challenges， ethical considerations， and practical guidelines[J]． American Psychologist，2015，70(6): 543-556.   
[6]李学龙，龚海刚．大数据系统综述[J]．中国科学：信息科学，2015，45(01)：1-44.   
[7] Hofstede G. Culture’s consequences，(2nd.ed.）[M]． Beverly Hills，CA:Sage，2001. [8] Greenfield P. M. The changing psychology of culture from l800 through 2000[J]. Psychological Science，2013，24(9):1722-1731.   
[9] Kashima Y.，& Kashima E. S. Individualism,GNP,climate,and pronoun drop:Is individualism determined by affluence and climate,or does language use play a role?[J] Journal of Cross-Cultural Psychology，2003，34(1)：125-134.   
[10] Michel J.B.，Shen Y. K.，Aiden A.P.，Veres，A.，Gray M. K.，The Google Books Team， Aiden,E.L. Quantitative analysis of culture using millions of digitized books. Science, 2011, 331(176): 176-182.   
[11] Greenfield P.M. Linking social change and developmental change: Shifting pathways of human development[J]．Developmental． Psychology，2009，45(2):401-418.   
[12] Zeng R.，and Greenfield P. M. Cultural evolution over the last 40 years in china: Using the Google Ngram Viewer to study implications of social and political change for cultural values[J]. International Journal of Psychology，2015，50(1): 47-55.   
[13] Twenge JM, Campbell W K,Gentile B. Changes in pronoun use in American books and the rise of individualism，1960-2000[J]． Journal of Cross-Cultural Psychology，2013，44(3): 406-415. [14] Yu F.，Peng T.，Peng K.，Tang S.，Chen C. S.，Qian X.，et al. Cultural value shifting in pronoun use[J]． Journal of Cross-Cultural Psychology，2015，47(2):310-316.   
[15] Wu M S,Li B, Zhu L, Zhou C. Culture change and affectionate communication in China and the United States: Evidence from Google digitized books l960-2008[J]. Frontiers in Psychology， 2019, 10: 1110.   
[16] Floyd K.，Hesse C.，and Generous M. A.“Affection exchange theory: A bioevolutionary look at affectionate communication,” in Engaging Theories in Interpersonal Communication[M],2nd Edn, eds D.O. Braithwaite and P. Schrodt (Thousand Oaks，CA:Sage)，2015.   
[17] Park H.，Twenge J. M.，& Greenfield P. M. The great recession: Implications for adolescent values and behavior[J]. Social Psychological and Personality Science，2014， 5(3):310-318. [18] Bianchi E C. American individualism rises and falls with the economy: Cross-temporal evidence that individualism declines when the economy falters[J]. Journal of Personality and Social Psychology，2016，111(4): 567-584.   
[19] Wang S.，& Yang Y. The long-term trend of economic growth and quantitative characteristics of the economic“New Normal”in China (in Chinese)［J]. Economic Research Journal, 2017,6: 46-59. [20] Wu M. S.，Li B.，Zhu，L.，Jiao D.，& Zhu T. Connecting with Others in Economic Downturn: A Big Data Analysis of Collectivism from 2010 through 2016. Proceedings of The Academic Forum on Research into Social Mentality and Social Psychological Services under the New Era (p.p. 81-86). Marietta, Georgia: American Scholars Press， Inc.   
[21] Mccrae R. R.,& Terracciano A. Personality profiles of cultures: Aggregate personality traits. J Pers Soc Psychol，2005，89(3):407-425.   
[22]严家炎．金庸小说与传统文化[J]．中国文化研究，1998，21(3)：67-74.   
[23] Mehl M. R.，Gosling S. D.，& Pennebaker J. W. Personality in its natural habitat: Manifestations and implicit folk theories of personality in daily life[J]. Journal of Personality and Social Psychology，2006，90(5):862-77.   
[24] Chen X.，Chen H.,Li D.，& Wang L.Early childhood behavioral inhibition and social and school adjustment in Chinese children: A five-year longitudinal study[J]. Child Development, 2009,80(6): 1692-1704.   
[25] Zhou C.，Yiu W. Y. V.，Wu M. S.，& Greenfield M. P. Perception of cross-generational differences in child behavior and parent socialization:A mixed-method interview study with grandmothers in China[J]. Journal of Cross-Cultural Psychology，2018，49(1):62-81.   
[26] Zhao N.， Jiao D.，Bai S.，and Zhu T. Evaluating the validity of simplified Chinese version of LIWC in detecting psychological expressions in short texts on social network services[J]. PLoS One，2016，11(6):e0157947.   
[27］吴育锋，刘洪飞，焦冬冬，吴胜涛，朱廷劭．小说人物性格的文学智能分析：以《平凡的世界》为例 [J]．中文信息学报，2018，32(7)：128-136.   
[28] Wu M. S.，Cai J.，Ma-Kellams C.，Li T.，& Zhu T. The modern versus traditional heroines: A five-factor personality model based on the linguistic analysis of Chinese novels[J]. 2019, Manuscript under review.   
[29] HofstedeG J， Jonker C M, Verwaart T. Individualism and collectivism in trade agents. In: Nguyen N T,BorzemskiL,Grzech A,et al (eds). New Frontiers in Applied Artificial Intelligence. IEA/AIE 2008. Lecture Notes in Computer Science, 2008, 5027. Berlin， Heidelberg: Springer. [30]吴胜涛,周阳,傅小兰,刘晓倩,刘天俐,朱廷劭.“一带一路”沿线文化与合作交往模式探究：基于社交 媒体大数据的心理分析[J].中国科学院院刊,2018,33(3)：298-307.   
[31］任孝鹏，向媛媛，周阳，朱廷劭．基于微博大数据的中国人个体主义/集体主义的心理地图．内蒙古 师范大学学报，2017，46(6)：1-6.   
[32] Chiao J. Y.，& Blizinsky K. D. Culture-gene coevolution of individualism-collectivism and the serotonin transporter gene[J]. Proceedings of the Royal Society B: Biological Sciences，2010, 277(1681) : 529-537.   
[33] Wu M. S.，Zhou C.，Chen H.,Cai H.，& Sundararajan,L. Cultural value mismatch in urbanizing China: A large-scale analysis of collectivism and happiness based on social media and nationwide survey[J]． International Journal of Psychology，2018，53(2): 54-63.   
[34]董颖红,陈浩,赖凯声,乐国安.微博客基本社会情绪的测量及效度检验[J].心理科学，2015，38(5)： 1141-1146.   
[35] Xie Y.，Zhang X. B,Tu P.，& Ren Q. China Family Panel Studies (CFPS)．Ann Arbo，MI. 2018. https://doi.org/10.3886/ICPSR36524.v2   
[36] Wei W.，Lu J.G.，Galinsky A.D.，Wu H.，Gosling S. D.Rentfrow，P.J,Wang，L.Regional ambient temperature is associated with human personality[J]. Nature Human Behaviour, 2017,1(12):

890-895.

[37] Van de Vliert，E.，Yang，H.，Wang，Y.，& Ren，X. Climato-economic imprints on Chinesecollectivism[J]. Journal of Cross-Cultural Psychology，2013，44(4):589-605.  
[38] Xu Y.，& Hamamura T. Folk beliefs of cultural changes in China[J].Frontiers in Psychology,2014，5:1066.  
[39]包寒吴霜,吴胜涛,郑昊,陆海蓉,郑伟,戴炜,陆梭,朱廷劭.雾霾下的自我:空气污染与个体主义-集体主义的大数据分析[J].社区心理学研究,2018,6(02)：71-85.  
[40]喻丰,彭凯平,郑先隽.大数据背景下的心理学:中国心理学的学科体系重构及特征[J].科学通报,2015,60(Z1): 520-533