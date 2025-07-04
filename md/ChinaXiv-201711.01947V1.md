# 基于VSM的美国一流大学图书馆网站导航文本调查与分析

尹相权 李书宁

(北京师范大学图书馆 北京 100875)

摘要：【目的】通过分析美国一流大学图书馆网站导航文本的特点，为国内大学图书馆导航建设提供建议。【方法】结合一流大学应具有一流学科、一流教师和一流学生的思路选取选取15所美国一流大学图书馆，基于标签云和文本挖掘模型VSM，分析导航文本词维度上的共性和特异性，并结合《2016年美国图书馆状况报告》进行数据验证。【结果】与人工调研相比，基于VSM模型的统计方法可以更直观、快速地给出基础调研结果，调研结果可供进一步深度文本分析参考。【局限】仅选取一级导航、二级导航和首页标题板块概况导航文本。【结论】基于文本数据挖掘模型的统计方法可以更直观、快速地给出基础调研结果，为高校图书馆网站导航建设提供参考。

关键词：美国大学图书馆网站导航向量空间模型 调查分析分类号：G250.7

# 1引言

互联网时代，图书馆网站转变为图书馆内容展示和服务的主要窗口，通过图书馆网站获取信息已成为用户利用图书馆资源的一种基本方式。随着近年图书馆信息资源量和服务内容的增加，包括提供文献资源、提供图书馆服务介绍信息、提供图书馆消息、促进与读者的交流互动等，图书馆网站要承载的内容远远超出了原有的限度。而用户的需求也日趋多样化，要能够在图书馆网站以最快的速度找到自己所需要的东西，由于图书馆网站所承载的内容有限，且往往有很多相对独立的资源管理系统与服务模块，这势必会造成相当多的内容被隐藏，图书馆服务无法更好地为读者所用，读者也无法知道图书馆还有哪些服务。在这种情况下，作为提供给用户的最直接、最方便的网站内容访问工具，图书馆网站导航就变得非常有意义，而且伴随着信息超载，这种导航将越来越有意义。图书馆网站导航主要指位于网页页眉区域的，在页眉横幅图片上边或下边的一排水平导航文字，它起着链接图书馆网站的各个页面的作用。另外，考虑到首页亦可提供一个简便快捷的操作入口，帮助用户快速定位到所需要的资源，图书馆首页各个栏目的标题也应该纳人图书馆导航的范畴。

图书馆网站应完善导航功能，有针对性地把物理上分散的、杂乱无章的信息资源重新组织，使网络用户能够快捷地找到自己所需要的信息[1]。国内著名大学在建设图书馆网站时，大多参考了国外著名大学的图书馆网站。以清华大学图书馆为例，其在改版时将图书馆网站的信息和资源的组织、揭示与布局作为重要课题，并参考了国外著名大学图书馆网站[2-3]。但是国内著名大学图书馆大多重点描述了参考国外大学图书馆网站之后的实施，没有对导航调研方法进行描述和分析。因此，本文选取15所美国一流大学图书馆的导航文本，借助向量空间模型VSM进行研究，以期为国内图书馆网站导航建设提供参考。

# 2美国一流大学图书馆导航文本分析

# 2.1 数据收集

按照一流大学应具有一流学科、一流教师和一流学生的思路选取10 所美国一流大学[4]。另外，考虑到美国大学图书馆显著的社会服务特点，为考察图书馆的社会服务，在10所大学的基础上，又增加了5所大学[5]。最终选取的15所大学图书馆分别为：哈佛大学图书馆、斯坦福大学图书馆、麻省理工学院图书馆、耶鲁大学图书馆、普林斯顿大学图书馆、哥伦比亚大学图书馆、芝加哥大学图书馆、加州理工学院图书馆、宾夕法尼亚大学图书馆、加州大学伯克利分校图书馆、康奈尔大学图书馆、加州大学戴维斯图书馆、田纳西大学图书馆、北卡罗莱纳州立大学图书馆以及西北大学图书馆。

在PeterMorville 提出的用户体验蜂巢模型(UserExperienceHoneycomb)中，可寻性是用户体验的主要指标之一，主要通过导航与定位体现[。依据其理论,一级导航、二级导航和首页板块标题可以代表一个网站内容的主要导航组织方式，因此，本文选取一级导航、二级导航和首页板块标题文本作为分析对象。

首先，人工收集这15所大学图书馆的一级导航、二级导航和首页板块标题，并进一步根据导航文字的语义进行归一化处理，即清洗和转换工作。例如,“About”、“ABOUT”、“About us"和"About the library”,经统一大小写和文本替换工作后，统一文字为"aboutus";"Help"和"GetHelp"统一为"gethelp"；拆分并列词组，把“Search&Find"拆分为两个词条“search"和“find"，把“toolsforprospectivestudentsl currentstudents|facultyorstafflalumniorfriends”拆分为"toolsfor prospective students"、“tools for current students”、“tools for faculty or staff'和‘toolsfor alumniorfriends”。针对不同层次的分析目标，提供一级导航文字统计分析、首页板块统计分析和导航文字在导航词维度上的统计分析。

# 2.2 文本统计分析方法

在对文本进行统计分析时，主要考察文本的特性以及文本与文本之间的相似性。为了更清晰地对导航文本进行解析，本文首先利用标签云对导航文本整体进行直观描绘，之后，通过统计方法对文本进行特征抽取，用于表征各个文本的特性，并进一步在文本表征的基础上进行文本相似度计算，挖掘文本和文本之间隐含的相似性。每个文本的特征向量可通过降维处理并打印，形成文本的摘要信息，供特性分析使用。

标签云是一套相关的标签以及与此相应的权重。权重影响使用的字体大小或其他视觉效果。标签字体越大，此条目在网站中出现的次数越多。标签云在直观展示网站的显著内容时十分适用，可用于各个网站导航之间的共性分析。通常典型的标签云有30至150个标签，当文本较多时，标签云的直观性会降低。

本文采用的文本相似性计算方法为较为经典的向量空间模型(Vector Space Model,VSM)。VSM将对文本内容的处理简化为向量空间中的向量运算，并且它以空间上的相似度表达语义的相似度7。其中，导航文本的相似度通过两个多维向量的夹角的余弦值来表征。两个向量的夹角越小，余弦值越高，代表导航文本之间相似度越高。

具体而言，假设有M个导航文本，对每个导航文本进行特征提取，假设特征为N维，可以得到$\mathbf { M } { \times } \mathbf { N }$ 的特征向量矩阵F，将其映射到VSM模型中，可以得出 M个文本中任意两个文本的特征距离。本文采用向量的余弦距离作为它们之间的语义距离。假设有导航文本A和导航文本B，则它们的语义距离如公式(1)所示。

$$
d i s ( A , B ) = \cos \left( { \frac { \displaystyle { \overline { { A } } } \cdot { \overline { { B } } } } { \displaystyle { | \overline { { A } } | \cdot | \overline { { B } } | } } } \right) = \cos \left( { \frac { \displaystyle { \sum _ { i = 1 } ^ { N } { a _ { i } b _ { i } } } } { \displaystyle { \sqrt { \sum _ { i = 1 } ^ { N } { a _ { i } ^ { 2 } \cdot \sum _ { i = 1 } ^ { N } { b _ { i } ^ { 2 } } } } } } } \right)
$$

本文选择 TF-IDF(Term Frequency-Inverse DocumentFrequency)方法。TF-IDF的主要思想是：如果某个词或短语在一个文本中出现的频率高，并且在其他文本中很少出现，则认为此词或者短语具有很好的类别区分能力。

VSM处理的文本需要分词、去停用词等操作，考虑到导航文字中词条和词条之间有明显物理间隔，本文把一组导航词作为一个词组进行处理，首先对词组进行归一化预处理，并计算每个词组的TF-IDF值，由此，各个网站内容的表示形式转换为词组的TF-IDF值向量，基于该向量进行相似度计算并选取相似度阈值，挖掘各个导航文本之间潜在的关联，并选取各导航文本TF-IDF值最高的10维特征，打印为导航文本的关键词组，分析各个网站导航的特性。

# 2.3 结果分析

首先利用标签云分别直观展示一级导航文字共性和首页板块标题的共性。之后，为进一步探索具体导航文本之间的相似性，利用VSM对每个网站的导航文字，包括一级导航文字、二级导航文字、首页板块标题文字，进行语义相似度分析，并打印出各个大学图书馆导航文本的特征向量，结合《2016年美国图书馆状况报告》[8进行分析。

# (1）导航直观共性分析

在对导航词进行预处理之后，对15所一流大学图书馆的一级导航文字进行汇总，导人开源标签云生成器 TAGUL[9中，生成一级导航标签云，如图1所示。可见，美国一流大学网站中，关于我们(aboutus)、研究支持(research support)、服务(services)、帮助(get help)、数据集(collections)、图书馆们(libraries)、研究(research)、检索(search)和寻找(find)占据了显著位置，说明这些导航词在各大学图书馆一级导航中出现的频率较高。

g the library databases get help research supportnate people requesting tools SerUicescatalogsruar libraries borrowing askus using the libraries search toolsfind visitaboutusmra contactus friends libraryservices givingCollections access Sexhibitsresearch search

同样，利用首页板块标题文字生成首页板块标题标签云，如图2所示，新闻(news)、检索(search)、发现(find)、活动(events)模块是比较通用的模块。

ftnd research assisstano services research tools for faculty or staffTexhibits searchethelp find for rfra relocation featuredre. news experts libraries guide tools for prospective students libraryhours's "course reservesevents contactus quick links askalibrarian resources

(2）基于VSM的导航共性分析

基于VSM的网站余弦相似度计算结果表明，各个网站之间的相似度偏低(均低于0.30)。说明各个大学图书馆在建设网站导航时，并不存在过度借鉴现象,这与实际情况相符合，也说明了本文选取的文本相似度计算方法的可靠性。同时，如导航文本直观共性分析所示，有些导航词会在多个大学图书馆导航中出现,为了进一步探索网站之间的共性，选定相似度阈值0.20，发现7对组合存在弱相似性，为了直观表示，用实线关联具有一定相似性的高校，如图3所示，哈佛大学图书馆与斯坦福大学图书馆、麻省理工学院图书馆等具有一定的弱相似性，从打印的特征表示向量中可以看出，图书馆们(libraries)、活动(events)和员工目录(staffdirectory)等导航词对相似度值有一定贡献。

![](images/72210a144312fa754d246fdc307907827edc6629b5c5d20debda9c4cb291f405.jpg)  
图1美国15所一流大学图书馆一级导航标签云  
图2美国15所一流大学图书馆首页板块标题标签云  
图3与哈佛大学图书馆具有弱相关性的6所大学图书馆及相似度

(3）基于VSM的导航特性分析

为了进一步考察各个大学导航文本的特性，本文打印了各个大学的导航词组特征向量，按照词的TF-IDF值从高到低的顺序，选取排序前10位的特征词组进行人工分析，如表1所示。

共性(将超过1/3大学存在的特征词作为共性)：在15所大学中，有11所大学把图书馆们(libraries)作为重点展示对象，其中，有10所大学的第一位特征词均为图书馆；7所大学中检索(search)相关特征词显著；6所大学有研究指南特征词(guides)；6所大学有活动通知(events)，其中有2处显示为news andevents;6所大学显著提供了员工指南(staffdirectory)；5所大学有关于我们(aboutus)特征词。通过这些共性导航词，不难发现，一流大学图书馆大多把展示资源(图书馆、员工、关于我们)和服务(检索、研究指南)放在显著位置。与国内大学不同的是，这15所一流大学图书馆大多把活动通知与新闻分开展示，并且把活动通知放在更显著的位置。

表115所一流大学图书馆Top10 导航文字  

<html><body><table><tr><td>图书馆</td><td>Top10 导航文字</td></tr><tr><td>斯坦福大学</td><td>libraries,access for persons with limited mobility，jobs,collecting areas，events，computing(equipment & services),privileges,search tools,chat, course guides</td></tr><tr><td>康奈尔大学</td><td>faq for instructors,research data management services,equipment,computing,how to submit course reserves, library spaces,help,search tips: catalog,research guides,search</td></tr><tr><td>耶鲁大学</td><td>libraries,guide to using special collections,getit @yale (borrow direct,interlibrary loan,scan & deliver),find ejournals bytitle,search worldcat,policies,elischolar,search,search librarycatalog(orbis),services forpersons with disabilities</td></tr><tr><td>哥伦比亚大学</td><td>recommend a title for purchase,deposit your research,technology,borrow direct, interlibrary loan,computing, policies,butler library lockers,room reservation, study spaces</td></tr><tr><td>加州大学伯克利分校</td><td>libraries,hours and maps,reserve a study room,news and events,renew,staff directory,research help,how to find,online exhibits,about us</td></tr><tr><td>芝加哥大学</td><td>libraries,copyright info,borrowdirect,employment,database finder,chapters,privileges,otherlocalcollctions, research centers,library surveys</td></tr><tr><td>北卡罗莱纳州立大学</td><td>libraries,googlescholar,interlibrary loan,staff directory,filmfinder,tours,search,give tothe library,course reserves,visitor information</td></tr><tr><td>西北大学</td><td>libraries,resources,contact the library,tools for alumni,events,interlibrary loan,search tools,visit,guides, tools for graduate students</td></tr><tr><td>普林斯顿大学</td><td>libraries,today's hours,borrow direct,study spaces and lockers,news and events,recommend a purchase,staff directory, new catalog,about us,research guides</td></tr><tr><td>加州理工学院</td><td>publish on demand,site map,archives,howdo i.?,caltech open access policy faq,software available,aboutus, ask a librarian,friends of the caltech libraries,copyright support</td></tr><tr><td>哈佛大学</td><td>libraries,initiatives,archives,contribute your research,events,e-resources,resources for alumni,departments, staff directory,get it services</td></tr><tr><td>田纳西大学</td><td>ut dissertations,employment,give tothe libraries,the librarysociety,staff directory,librariesa-z,renewitems, citing sources, music library, research guides</td></tr><tr><td>宾夕法尼亚大学</td><td>libraries,resources,penn's libraries,createa video,staf directory,subjects/collctions,tools,tutorials fortools, search,digitalpenn</td></tr><tr><td>麻省理工学院</td><td>scholarly publishing,galeries,tip faq,events,use policy,more search options,your account,about us,citation software, study spaces</td></tr><tr><td>加州大学戴维斯分校</td><td>libraries,melvyl,requesta book/article,subject guides,digital scholarship,engineering,borowing/circulation, carlson health sciences,about us,exhibits</td></tr></table></body></html>

通过观察表1中的各网站导航的前10维特征向量，本文总结了其体现的部分特色服务，如下：

$\textcircled{1}$ 斯坦福大学图书馆的特征向量中，位列第2的特征词(组)为"access forpersonswith limitedmobility"，展示了该网站对残疾人的支持服务；位列第6的特征词：computing(equipment&services)展示了其对计算相关服务的支持。

$\textcircled{2}$ 耶鲁大学图书馆，与斯坦福大学类似，对残疾人的服务也有所体现(services for persons with disabilities)。另外，耶鲁大学图书馆的特色—Orbis在线图书馆目录系统(OnlineLibraryCatalog)也出现在特征向量中。

$\textcircled{3}$ 哈佛大学图书馆和西北大学图书馆分别有显著的为校友提供的信息，其中，哈佛大学体现在第8位特征词，西北大学为第4位。

$\textcircled{4}$ 加州大学戴维斯分校图书馆(UCDavis)的在线图书馆目录系统Melvyl体现在了第2位。另外，第8位特征词(carlsonhealthsciences)体现其医疗健康相关特色数据。

$\textcircled{5}$ 麻省理工学院图书馆的学术出版服务(scholarlypublishing)位列特征向量的第1位。

这些特征向量表明，各大学图书馆均有其服务侧重点，可满足不同用户、不同领域的技术需求，例如斯坦福大学的计算相关服务、耶鲁大学的Orbis在线图书馆目录系统、普林斯顿大学的新目录系统、加州大学戴维斯分校的Melvyl在线图书馆目录系统、加州大学戴维斯分校的医疗健康相关数据、麻省理工学院的学术出版服务等。另外，各个大学图书馆在开展社会服务方面各有特色，包括残疾人服务和校友服务等。以上结果也印证了《2016年美国图书馆状况报告》中的表述：图书馆在积极开展服务转型以满足用户技术需求[8]。

此外，上述报告中也提到，调查表明学生和教职工认可大学图书馆在展示研究技术、增强学生读写能力和管理课程资源等方面的价值。大学图书馆正在通过科技界和数字化学术中心探寻激励学生成功的创新方法[8]。以上内容在本文的数据中也能找到对应的数据支持。研究技术(research techniques):所有大学图书馆均有涉及，具体体现为帮助、指南、目录、检索和发现等；管理课程资源(course reserves):康奈尔大学(第5位)、北卡罗莱纳州立大学(第9位)、斯坦福大学(第10位)；科技界(publishing on demand):加州理工学院(第1位)、麻省理工学院(第1位)；数字化学术中心(digitalscholarship):加州大学戴维斯分校(第5位)。

总之，通过特征向量，可以迅速了解各大学图书馆导航文本之间的共性和特异性，并进一步为解析图书馆当前重点以及发展方向提供数据基础。需要注意的是，特征向量表示的是网站导航的代表性文本而非全部文本。例如，完整的网站导航文本中，除了斯坦福大学和耶鲁大学、北卡罗莱纳州立大学、加州大学伯克利分校、哥伦比亚大学、康奈尔大学等均有提及残疾人相关服务，但是只有前者体现在Top10 导航文字中。

# 2.4对国内高校图书馆网站导航建设的启示

调研结果对国内高校图书馆网站导航建设有如下启示：

(1）各个大学图书馆在建设网站导航时，可应用但不仅限于以下共性导航词：一级导航词可以考虑选取关于我们、研究支持、服务、帮助、数据集、图书馆们、研究、检索和寻找等共性导航词；在首页板块中，可以选取新闻、检索、发现和活动等共性板块；在整个导航文本中，图书馆们、检索、研究指南、活动、员工目录和关于我们具有一定的普遍性，可供选取。

(2)在建设导航过程中，应避免过度借鉴现象，一方面在导航词中加人图书馆特色元素，例如，如果图书馆有特色编目，可在编目导航词中加入特色编目简称。另一方面可以参考国外大学，在导航中区分用户类别，例如残疾人、校友、学生等。更重要的是，应顺应时代发展的要求，重点拓展特色服务，包括社会服务，激励学生创新的技术服务等。

# 3结语

本文以15所美国一流大学图书馆的网站导航文字作为调研对象，基于VSM模型对导航文本进行导航词维度上的统计，直观展示了各网站导航的共性和特异性，并结合《2016年美国图书馆状况报告》进行数据验证。通过分析发现:

一级导航文本中，多数图书馆重点在于展示其资源和服务，包括关于我们、研究支持、服务、帮助、数据集、图书馆们、研究、检索和寻找等；在首页板块中，新闻和事件、检索和快速链接模块是比较通用的模块。

网站整体导航文本之间的相似度偏低，各个网站的特性向量有显著差异，在给定相似度阈值的条件下，只有哈佛大学图书馆与斯坦福大学图书馆、麻省理工学院图书馆等6所大学图书馆具有一定的弱相似性;图书馆们、检索、研究指南、活动、员工目录和关于我们等特征词具有一定的普遍性；从各个特征向量中,可以找到以残疾人服务为例的相关社会服务特征词，并有特征词与《2016年美国图书馆状况报告》中关于高校图书馆的现状描述相呼应。

结果表明，较人工调研方法，基于文本数据挖掘模型的统计方法可以更直观、快速地给出各个图书馆网站导航的共性和特异性的直观分析结果，可供国内建设一流大学图书馆网站参考。

# 参考文献：

[1] 相丽玲，董小燕，屈宝强．从网页设计看高校图书馆的网 站建设[J]．情报学报,2004,23(2):204-208.(Xiang Liling, Dong Xiaoyan，Qu Baoqiang. Study of the Website Construction of Colleges and Universities Library from the Web Page Design[J].Journal of the China Society for Scientific and Technical Information,2004,23(2):204-208.)

[2]范爱红，邵敏，赵阳．大学图书馆网站设计理念的探析与 实践——清华大学图书馆网站改版案例研究[J].大学图书 馆学报,2006,24(3):38-42.(Fan Aihong，Shao Min,Zhao Yang.Discussion and Practice on the Principles of University Library Website Design——A Case Study of the Tsinghua University Library Website Redesign[J].Journal of Academic Libraries,2006,24(3): 38-42.)   
[3]范爱红，姚飞，姜爱蓉．清华大学图书馆新版网站的设计 特色与读者调查分析[J]．大学图书馆学报，2011，29(5): 66-69.(Fan Aihong,Yao Fei, Jiang Airong.The Features of the New Website of Tsinghua University Library and the Website Survey Analyses[J].Journal of Academic Libraries, 2011,29(5):66-69.)   
[4] 叶鹰．美国一流大学及其图书馆调研报告[J].大学图书馆 学报，2002,20(3):5-8.(Ye Ying.A Survey on the Top Universities and Their Libraries in the United States[J]. Journal of Academic Libraries,2002,20(3):5-8.)   
[5] 谢丽娟，郑春厚．美国高校图书馆社会服务发展现状及启 示[J]．中国图书馆学报，2009,35(2):93-97.(Xie Lijuan, Zheng Chunhou. Social Services of Academic Libraries in USA: Reality and Inspirations[J]. Journal of Library Science in China,2009,35(2): 93-97.)   
[6] Semantic Studios.User Experience Design [EB/OL].[2016- 10-15]. http://semanticstudios.com/user_experience_design/.   
[7] Vector Space Model [EB/OL]. [2016-10-15].https://en. wikipedia.org/wiki/Vector_space_model.   
[8] American Library Association.The State of American's Libraries [R/OL]. [2016-10-16]. http://www.ala.org/news/ sites/ala.org.news/files/content/state-of-americas-libraries-20 16-final.pdf.   
[9] TAGUL[CP/OL].[2016-10-15].https://tagul.com/.

# 作者贡献声明：

尹相权：提出研究思路，设计研究方案，进行实验，采集、清洗和分析数据，起草论文;  
李书宁：设计研究方案，论文修改。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:yinxq@lib.bnu.edu.cn。  
[1]尹相权，李书宁．美国一流大学图书馆网站导航文本.xlsx.  
美国一流大学图书馆网站导航文本及VSM结果.  
[2]尹相权，李书宁.WebsiteAnalysis.rar.VSM源码 for网站导航数据.

收稿日期:2016-11-22   
收修改稿日期:2017-01-24

# Analyzing Website Navigation Features of Top U.S. Academic Libraries

Yin Xiangquan Li Shuning (Beijing Normal University Library, Beijing 10o875, China)

Abstract:[Objective] This paper studies the navigation features of top academic library websites from the United States,aiming to improve the servicesoftheirChinese counterparts.[Methods]First,we identifiedlibrarywebsitesof the top15 U.S.universities and downloaded their navigation texts.Second, we analyzed the similaritiesand differences amongthese texts with tag cloud and Vector Space Model.Finaly,we examined our findings with the“2O16 State of America'sLibraries Report".[Results]The proposed method was intuitive and generated analysis results fast,which could befurther processed with text mining techniques.[Limitations]Onlyretrieved the firstand,second levelsof navigation as wellas titles of the homepages.[Conclusions]The proposed model provides useful information for the academic libraries in China.

Keywords: U.S.Academic Libraries Website NavigationsVSM Investigation and Analysis