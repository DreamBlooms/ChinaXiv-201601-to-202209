# 全球标本数字化建设及共享发展趋势

陈建平¹，许哲平 2\*(1.上海辰山植物园，上海 201602；2.中国科学院文献情报中心，北京 100190)

摘要：标本数字化建设是生物多样性保护和利用的重要工作基础，通过标本数据的整合分析，能够在生物分类学、生态学、生物工程、生物保护、粮食安全、生物多样性评估、教学教育和人类社会活动等方面提供数据支撑。为了了解全球标本数字化建设工作的现状以及数据共享的策略与技术发展趋势，通过对比为中国的标本数字化建设工作提供建议，该文分别调查梳理了北美洲、南美洲、欧洲、非洲、亚洲和大洋洲地区的标本数字化和平台建设情况，对标本数据共享现状和趋势从数据使用协议、新技术新方法和公众科学等方面进行了分析，为中国国内的标本数字化工作提出了工作建议，包括：加强标本数字化建设、管理和动态更新方面的协同机制建设，确保实物资源和数字化资源信息的同步；加强数据整理和发布，促进数据质量的提升，充分开放数据使用协议，减少数据使用的阻碍；加强对新技术的学习和引入，特别是开源软件、机器学习和人工智能技术的应用，能够在标签快速识别、自动鉴定和属性数据提取等方面发挥作用；加强区域和国际合作，推动数据的整合应用；推动公众科学项目发展，促进野外采集、室内整理、在线纠错、数据产品研发等工作的开展。

关键字：标本数字化,数据共享,GBIF,公众科学,生物多样性

# Global specimen digitization and sharing trends

CHEN Jianpingl， XU Zheping2\* (1. Chenshan Botanical Garden,Shanghai 201602,China; 2.National Science Library, Chinese Academy of Sciences,Beijing 100190, China)

收稿日期：2021-05-13

基金项目：科技部基础性工作专项（2015FY110200）：中国科学院文献情报领域引进优秀人才计划；中国科学院A类战略性 先导科技专项（XDAl905000）［Supported bya grant from the Basic Work Special Project of the National Ministryof Science and Technologyof China (2015FY110200)；Talent Introducing Plan in the fieldof Library and Information Science in the Chinese Academy of Sciences；Strategic Priority Research Program of the Chinese Academy of Sciences (Grant No.XDA19050000)]。

作者简介：陈建平（1974-），硕士，高级工程师，长期从事生物多样性信息学研究及信息平台建设工作，（E-mai1）chen jianping@csnbgsh.cn。

\*通讯作者：许哲平，博士，副研究馆员，长期从事生物多样性信息学以及科学数据管理与利用的研究工作，（E-mail）xuzp@mail.las.ac.cn。

Abstract: The digitization of specimens is an important basis for the conservation and utilization of biodiversity. Through the integrated analysis of specimen data, it can provide data support in taxonomy, ecology, bioengineering, biological protection, food security, biodiversity assessment, human social activities and education and other aspects. At present， the development situation varies from country to country. In order to understand the current status of global specimen digitization work, as well as data sharing strategies and technology development trends, through comparison, provide suggestions for China's specimen digitization work, this article summarizes the status of specimen digitization and platform construction in North America, South America, Europe,Africa, Asia and Oceania, and reviews the status and trends of specimen data sharing from data use agreements, new technologies and methods，and citizen science using. After comparison and analysis with the current situation in China, proposed work suggestions, including strengthening the construction of coordination mechanisms in the digital construction， management and dynamicupdateofspecimens, ensuringthe synchronization of physical resources and digital resource information; strengthening data collation and publishing, promoting data quality improvement, fully opening data use agreements, and reducing data use obstacles; strengthen the learning and introduction of new technologies, especially the application of open source software, machine learning and artificial intelligence technologies, which can play a role in rapid tag identification, automatic identification and attribute data extraction; strengthen regional and international cooperation to promote data. The integration and application of data products; promote the development of citizen science projects，and promote the development of field collection，indoor sorting，online error correction，and data product research and development.

Key words: specimen digitization, data sharing, GBIF, citizen science, biodiversity

# 1.引言

过去 450年的时间里，科研人员收集的植物标本数量超过3.81亿，分布在全球3000 多个标本馆中 (Krishtalka etal.，2016；Thiers，2017)。通过标本数据的整合分析，能够在生物分类学、生态学、生物工程、生物保护、粮食安全、生物多样性评估、人类社会活动和教学教育等方面提供重要支撑(Culley et al.,2013；Heberling et al.,2017；Soltis et al.,2017；Willisetal.，2017;马克平等，2018;张健，2017)。在2012年，GBIF 在综合众多专家意见的基础上发布了全球生物多样性信息学展望报告(GBIO）（Hobern etal.,2012）。该报告从文化、数据、实证和知识理解四个层次对未来全球的生物多样性数据相关的研究做了展望，并将标本采集数据作为五类基础数据源之一（其他四类数据源为出版物材料、野外观测、基因测序和自动化遥感观测），为标本数据的整合和应用指明了方向。

在全球范围内，过去十年通过GBIF（生物多样性信息机构）、CoL（全球生物物种名录）、EOL（网络生命大百科）和 BHL（生物多样性历史文献图书馆）等生物多样性数据项目的推动，生物标本数据的汇聚和共享进展迅速。以全球最大的生物多样性观测数据平台——GBIF

（全球生物多样性信息机构）为例（GBIF，2021），目前观测记录（Occurrences）数据总量为16.97亿条，其中传统标本馆的数字化标本数据为1.85亿条（占比整个平台数据的$1 0 . 9 \%$ ），其中动物（8637万条，占比 $4 6 . 5 \%$ ）、植物（8586万条，占比 $4 6 . 2 \%$ ）、菌物（707万条，占比 $3 . 8 \%$ ）。其中，这些标本数据分布的前10个国家是美国（3546万条）、巴西（1258万条）、澳大利亚（1216万条）、墨西哥（892万条）、加拿大（796万条）、日本（609万条）、哥斯达黎加（526万条）、挪威（452万条）、西班牙（404万条）、瑞典（366万条）。为了进一步加强对全球馆藏资源的整合，GBIF在2019年还启动了全球科学馆藏注册系统项目（GRSciCol1）（GBIF,2021)，收集研究机构、馆藏和相关工作人员的数据，涵盖了所有相关学科，包括地球与空间科学、人类学、考古学、生物学和生物医学以及农业、兽医学和技术等应用领域，增补了标本数据的元数据与相关背景信息，提升了数据质量。

本文通过梳理世界各大洲的标本数字化建设情况，对标本数据共享现状和趋势进行了调研，与我国当前的建设情况进行对比和分析，在数字化建设与共享服务、协同机制、国际合作和公众科学等方面提出了相应的建议。

# 2.数字化建设

# 2.1北美洲标本数字化建设

北美的标本数字化以美国的iDigBio平台为代表，iDigBio是一个跨机构合作的综合性生物多样性数据平台，是北美地区标本数字化的门户网站（iDigBio,2021）。目前已经数字化的标本记录数量为1.28亿条（植物占 $4 7 \%$ ），多媒体文件记录3917万条（植物占 $8 2 . 5 \%$ ），总共1688个数据集。2017年前是iDigBio数字化工作开展最为迅猛的阶段。2017年至今，数据量则呈现出平稳的上升趋势。在项目组织上，iDigBio将参加单位（数据源）的融入划分为四个阶段，分别是准备、协商、行动、数据汇总，按照参加单位所处的阶段，有序开展工作，使得项目能够稳定持续地推进。

在数据规范与标准上，iDigBio有详细的标本数字化文件规范、图像存储规范、图像处理规范、图像使用规范，使得数字化工作有明确的操作标准。其规范与标准在iDigBio官网上都有开放性的文档说明。基本原则可以概括为：采集图像尽量采用设备的极限分辨率，保证采集质量，图像应该采用无损压缩格式永久存档，图像处理应避免人为过分修饰，处理图像应该基于原始图像，避免误差积累，应尽量为用户提供最佳质量。

在标本数字化技术上，iDigBio将数字化任务划分为五个核心任务集：

（1）数字化前期：主要是标本实体的修复与规范化整理工作。（2）图像采集：使用专业单反数码相机或者高清标本扫描仪进行图像采集。（3）图像处理：包括9个常规工作，分别是质量控制、条形码获取、格式转换、颜色亮度调整、图像修剪、图像叠加增强、图像编辑、文件传输、图像内文字识别。（4）电子数据获取：是指提取或输入标签数据到数据库的过程。具体的工作方法可以是自动化或手工输入，手段包括OCR 图像文字识别、语音输入、键盘输入等。（5）地理位置的描述与地标化处理：即将文本描述的地名，审核并标注出精确的经纬度坐标点，建议附上误差范围、坐标系等参数。

# 2.2欧洲标本数字化建设

欧洲的植物标本馆历史悠久，馆藏丰富，学术机构众多，机构间也形成了良好的合作关系，其中欧洲分类学联盟 CETAF（Consortiumof European Taxonomic Facilities）是最大的分类学研究网络，包括了5000多会员，联盟下机构保存了全球 $8 0 \%$ 已描述的生物多样性标本与数据。BioCASe（The Biological Collection Access Service ）是 CETAF 推动下创建的数据标准与软件基础体系，指导着标本的数据化与数据共享。BioCASe数据标准主推ABCD 标准，在软件系统上提供了全方位的解决方案，包括适用于创建数据平台的BioCASePortal系统，以及适用于数据提供者的 BioCASe Provider Software（BPS）系统，以及网站监控、数据质量检查的工具。BioCASe是GBIF的成员节点，在数据标准、应用系统、共享政策上对GBIF 有着重要的影响。通过 BioCASe的数据整合，欧洲各国的标本数据最终通过GBIF 进行共享发布。除了CETAF与BioCASe以及GBIF外，欧洲各国的标本馆、植物园等分类学相关机构也普遍都创建了自己的网站系统，各类专题性的网络数据库非常丰富，还有大量的数据并未纳入GBIF的共享范围。部分数据库因为起步早、积累丰富，已经成为行业内的基础数据库，成为事实上的国际标准与基础平台，如国际植物名称索引（IPNI）等专题数据库。

在俄罗斯，从2014年开始，国立莫斯科大学开始进行标本数字化项目（Alexey P.Seregin,2018），形成了“国家生物系统仓储银行”计划（Seregin A．P．（Ed.）,2021），包括两个子项目，分别是莫斯科数字标本馆和俄罗斯植物分布图集，并通过在iNaturalist上创建的“FloraofRussia”项目来维护图库。目前已经累计形成标本113万份，图片111万张，物种3.9万个，地标化数据66万条，标签46万张、0CR记录66万条。

在法国，国家自然历史博物馆的植物标本馆（馆代码为P）的数字化建设也积累了丰富的经验（Le Bras et al.，2017）。该标本馆的第一个专业化工具Vaillant 数据库在1980 年代中期就开发出来了。从1993年开始建设现在的标本数据库 Sonnerat，该数据库目前不仅用来存放博物馆自身馆藏的标本，同时也是一个法语国家的标本馆网络系统（e-ReColNat项目）。大规模的数字化计划则是从2008年资助的Renobota项目开始的。下面是该标本馆数字化建设的历史发展表。

表1法国国家自然历史博物馆的植物标本馆数字化项目列表  
Table 1 List of Herbarium Digital Projects at the National Museum of Natural History   

<html><body><table><tr><td colspan="4">01 Tidrce</td></tr><tr><td>项目名称 Project name</td><td>时间段 （年) Time span (Year)</td><td>资助方 Funder</td><td>主要结果 Main output</td></tr><tr><td>热带亚洲和美洲的莎</td><td>2001~2003</td><td>博物馆内部</td><td>完成3.1万份数字化标</td></tr><tr><td>草科植物数字化项目</td><td></td><td>Internal project</td><td>本。</td></tr><tr><td>Cyperaceae</td><td></td><td></td><td>Completed 31,000</td></tr><tr><td>Digitalization</td><td></td><td></td><td>digital specimens</td></tr><tr><td>Project in Tropical</td><td></td><td></td><td></td></tr><tr><td>Asia and America</td><td></td><td></td><td></td></tr><tr><td>GBIF</td><td>2002~2004</td><td>GBIF</td><td>第一个全球数字化项目，</td></tr></table></body></html>

超过5.18万份标本被数字 化，开发了一个模式标本 的搜索引擎。   
The world's first   
global digitization   
project. More than   
51,800 specimens have been digitized,and a search engine for type specimens has been   
developed.   
完成3.1万份数字化标   
本，并做了精确地地标配 准工作。

千年种子库项目 2004\~2008 英国邱园Millennium Seed Kew GardenBank

<html><body><table><tr><td colspan="3">2004~2006：非洲植</td><td rowspan="2">The digitization of 31,000 specimens with accurate geographic coordinating was completed. 完成18.6万份数字化标本 （其中17.7万份模式标 本） Completed 186,000</td></tr><tr><td>全球植物项目 The Global Plants Initiative</td><td>梅隆基金会 物倡议（API） Andrew W. Mellon 2007~2008：拉丁美 Foundation. 洲植物倡议（LAPI) 2009~2015：全球植 物倡议（GPI） 2004-2006:African</td></tr><tr><td>(API);2007-2008:</td><td>Latin American Plants Initiative (LAPI)</td><td></td></tr><tr><td>Lamarck标本数字化</td><td>2004</td><td>国家研究中心 完成1.9万份标本数字化</td></tr><tr><td>项目 Lamarck Specimen</td><td>Centre for</td><td>The National Completed the digitization of 19,000</td></tr><tr><td>Digitization</td><td>Scientific</td><td>specimens</td></tr><tr><td>Project</td><td>Research</td><td></td></tr><tr><td>Auguste de Saint- 2009</td><td>圣保罗植物园研究</td><td>9 300份标本完成数字</td></tr></table></body></html>

Hilaire虚拟植物标 本室项目 Auguste de SaintHilaire Virtual Herbarium Pro ject

所，环境信息中心， 化，并做了细化处理圣保罗市安帕洛佩斯 Complete the基萨大学基金会 等 digitization of 9 300specimens

Sao Paulo   
Botanical Garden Research   
Institute,   
Environmental   
Information   
Center，Amparo   
Peschisa   
University   
Foundation of Sao Paulo,etc.   
博物馆内部   
Internal project

Renobota项目 2008\~2013 Renobota Project

$> 5 0 0$ 万份标本被数字化， 并完成了图像和标签数字 化工作。   
More than 5 million   
specimens with images and labels were   
digitized   
数字化标本48.8万   
Completed 488 000   
digitized specimens.   
Les Herbonautes 项 2012\~2019   
目   
Les Herbonautes   
Project   
La Maison de la   
Chimie基金会， $\mathrm { e ^ { - } }$   
ReColNAt，国家自然   
历史博物馆   
La Maison de la   
Chimie Foundation,   
e-ReColNAt,   
National Museum of   
Natural History   
欧盟基金   
EU funds

Open Up! 2013

38.5万份被提供到了 Europeana 平台 385 000 digital specimen records were submitted to the Europeana platform

<html><body><table><tr><td>Reflora项目 Reflora Pro ject</td><td>2014~2016</td><td>国家研究中心</td><td>提供30万张图片数据，并</td></tr><tr><td></td><td></td><td>The National</td><td>与里约热内卢联邦大学国</td></tr><tr><td></td><td></td><td>Centre for</td><td>家博物馆合作，建立虚拟</td></tr><tr><td></td><td></td><td>Scientific</td><td>的植物标本室。</td></tr><tr><td></td><td></td><td>Research</td><td></td></tr><tr><td></td><td></td><td></td><td>Provide 300 000 picture</td></tr><tr><td></td><td></td><td></td><td>data，and cooperate</td></tr><tr><td></td><td></td><td></td><td>with the National</td></tr><tr><td></td><td></td><td></td><td>Museum of the Federal</td></tr><tr><td></td><td></td><td></td><td>University of Rio de</td></tr><tr><td></td><td></td><td></td><td>Janeiro to establish a</td></tr><tr><td>e-ReColNat</td><td>2013-</td><td>国家研究中心，国家</td><td>virtual herbarium. 数字化植物标本964万</td></tr><tr><td></td><td></td><td>自然历史博物馆</td><td>Completed the</td></tr><tr><td></td><td></td><td>National Research</td><td>digitization of 9.64 million plant specimens</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>Center，National</td><td></td></tr><tr><td></td><td></td><td>Museum of Natural</td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>History</td><td></td></tr></table></body></html>

# 2.3非洲标本数字化建设

非洲的植物资源调查与积累起步于殖民地时期宗主国的植物调查，目前有大量非洲标本分散于欧洲各国的标本馆中，随着欧洲标本的数字化工作已经被逐步上网共享，如比利时的皇家中非博物馆，英国邱园的非洲植物计划等，都创建了专题标本数据库，这些数据最终大多通过GBIF 对外共享。而非洲各国自身的标本馆建设与网络平台还在起步阶段，通过与其他发达国家开展合作研究，很多项目正在展开，标本数字化还有很大的潜力。以南非国家生物多样性研究所(SANBI)为例，已经创建了独立的网站与专题数据库（SANBI,2021），也参加了世界植物在线、千年种子库等国际合作项目，以及非洲植物POSA项目、国家植被数据库NVD等项目，推动了自有标本资源的数字化，目前公开共享的数据大部分是通过GBIF发布。肯尼亚国家博物馆的东非植物标本馆（East African Herbarium）拥有热带非洲最大的植物学收藏，目前拥有700,000 多条植物标本及相关记录，它是热带非洲最重要的国家级数据中心，研究主要集中在东非植物的分类、分布、开发利用与保护方面。数据管理技术方面，除了GBIF平台外，BRAHMS 系统在非洲应用较为广泛，为肯尼亚国家博物馆、南非 BLFU标本馆等多个机构均提供了技术支持（East African Herbarium，2021；BLFU，2021）。

总之，非洲的标本数字化工作基础资料在欧洲，主要通过GBIF共享数据，自有标本资料与数字化工作外部依赖性很强，工作空白区较多，未来的潜力很大。

# 2.4南美洲标本数字化建设

南美的大量历史标本都保存于美国、欧洲的各个研究所与大学的标本馆中。除了巴西外，各国的标本馆数字化建设程度都比较低，目前能够获取的标本数据基本都来自GBIF，按植物标本记录统计，巴西约有700万，哥伦比亚139.2万，秘鲁80.7万，阿根廷72.2万，玻利维亚 52.6万。在独立的信息系统建设上，巴西的体系比较完整，很有特色。巴西的标本数字化工作主要体现在 speciesLink 平台中(speciesLink,2021)，截至 2021年4月15 日已经上线的数据包括了534个数据集，1521.9 万在线记录，其中1129.5万条记录具有地理坐标，378.5万记录包含图像，53.2万模式标本，其中藻类真菌与植物标本合计有1097万记录在线。从2002年至今，数字化标本量呈现稳定上升的趋势。在数字标本管理系统方面，speciesLink 的精细化实时管理技术十分突出，其指标系统indicators，可以详细展示每天新增的数据集、标本记录、地标化记录等量化指标。其数据清理系统，可以在线展示出数字标本中存在的问题类型与错误统计，诸如必填字段的空缺、地理坐标缺失、地标错误（如位置在海中）、重复的编号、怀疑出错的学名人名、地名错误等，很多问题都附上了自动化的建议，问题可以逐级展开，可跟踪到具体的标本记录本身，可供随时修订。其工具与应用软件服务十分丰富，提供了十余套专业软件服务，涉及到数据管理、地标化与地图应用、物种数据库管理、物种分布模型、物种查询浏览器插件、网络平台管理、专业量化指标系统等方面。

# 2.5大洋洲标本数字化建设

澳大利亚虚拟植物标本馆是一套在线资源库(AVH,2021)，可在线访问澳大利亚和新西兰植物标本数据，总数量超过666万份（来自23家澳大利亚和新西兰的标本馆）。后随澳大利亚生物图集(ALA)项目的开展，AVH被合并到ALA中一起发展（ALA,2021）。在ALA中，与AVH同级别的数据合作伙伴还包括在线动物馆藏记录集（OZCAM）、澳大利亚种子银行合作伙伴（ASBP）和默里达令盆地管理局（MDBA）。

新西兰总的植物标本超过140万件，拥有世界上最多的南极植物标本数据，约有64万件。2011年，新西兰虚拟标本馆（NZVH）正式启动，这是一个拥有11个标本馆数据的虚拟合作网络，可以在线提供70万件标本的查询和检索。该系统是由澳大利亚虚拟标本馆（AVH）提供软件和技术支持。随后，该项目也被合并到AVH中，并最终成为ALA的一部分。

# 2.6亚洲地区

截至目前，亚洲地区由于民族多、语言复杂，以及经济和科研工作相对落后的原因，数字化工作还任重道远。尽管中国大陆和台湾、印度、日本、韩国等国在生物多样性数据库建设方面有比较好的基础,，但大多数亚洲国家尚没有完善的生物多样性数据库，标本数字化建设工作相对落后。以GBIF上东南亚国家的标本数量及其贡献国家来看（表2），该地区的标本绝大多数并不是由本国发布的，而是欧美国家数字化后发布，还有些国家尚无任何数字标本共享，急切需要内外部力量合作，来共同推动该地区的标本数字化建设工作。

表2GBIF上东南亚国家的数字化标本情况（截止2021年04月15日）  
Table 2 Digital specimens of Southeast Asian countries on GBIF（ Due April 15, 2021)   

<html><body><table><tr><td>国家</td><td>标本数</td><td>国家排</td><td>TOP3数据发布国家</td></tr><tr><td>Country</td><td>Specimens</td><td>名</td><td>Top 3 Data publishing country</td></tr></table></body></html>

<html><body><table><tr><td></td><td></td><td>Country ranking</td><td>国家1和数量 No.1 Country & Specimens</td><td>国家2和数量 No.2 Country & Specimens</td><td>国家3和数量 No.3 Country & Specimens</td></tr><tr><td>泰国 Thailand</td><td>483 883</td><td>11</td><td>美国：193 745 The United States</td><td>荷兰：116 601 Netherlands</td><td>英国：63 970 United Kingdom</td></tr><tr><td>印度尼西亚 Indonesia</td><td>1 631 211</td><td>9</td><td>荷兰：870 899 Netherlands</td><td>美国：310 216 The United States</td><td>英国：98 720 United Kingdom</td></tr><tr><td>柬埔寨 Cambodia</td><td>38257</td><td></td><td>法国：11 232 France</td><td>美国：10 450 The United States</td><td>日本：5979 Japan</td></tr><tr><td>老挝 Laos</td><td>75 349</td><td></td><td>美国：24 701 The United</td><td>英国：19 250 United Kingdom</td><td>法国：9639 France</td></tr><tr><td>缅甸</td><td>65 833</td><td></td><td>States 美国：50164 The United</td><td>英国：8043 United Kingdom</td><td>荷兰：3976 Netherlands</td></tr><tr><td>Burma 马来西亚</td><td>425 071</td><td>16</td><td>States 荷兰：215 231</td><td>美国：149 856</td><td>英国：40 819</td></tr><tr><td>Malaysia 菲律宾</td><td>558 903</td><td>24</td><td>Netherlands 美国：401 800</td><td>The United States 荷兰：103 426</td><td>United Kingdom 瑞典：20 949</td></tr><tr><td>Philippines 新加坡</td><td>19 632</td><td></td><td>The United States 美国：7879</td><td>Netherlands 英国：6071</td><td>Sweden 荷兰：4 371</td></tr><tr><td>Singapore 东帝汶</td><td>14 468</td><td></td><td>The United States 澳大利亚：</td><td>United Kingdom 荷兰：1 945</td><td>Netherlands 美国：554</td></tr><tr><td>Timor-Leste 越南</td><td>267 770</td><td>7</td><td>Australia 10 598 美国：96 949</td><td>Netherlands 法国：57 283</td><td>The United States 荷兰：21580</td></tr></table></body></html>

基于此，我国科研人员在亚洲生物多样性保护和数据库网络计划（ABCDNet，2021）的基础上提出了亚洲植物多样性数字化计划（Mapping Asia Plant，简称 MAP），分东南亚、南亚、西亚、中亚、北亚(俄罗斯亚洲部分)和东北亚等6个区域推进工作，从文献出版物和标本数据整理入手，正在逐步推进亚洲地区的生物多样性数字化建设与共享合作。

# 3.标本数据共享现状和趋势

# 3.1GBIF平台上的数据共享现状

GBIF 是全球标本数据最大的共享平台，通过对GBIF上各大洲的参与国家和数据发布情况进行分析统计，可以了解全球标本数据的总体共享情况（表3）。可以看到欧美国家的数据贡献占了全球的绝大部分，发展中国家的贡献相对有限，与国际经济文化的发展水平密切相关，但发展中国家潜力巨大，将是未来标本数据增长的基础。

表3 参与GBIF数据发布的国家统计  
Table 3 Statistics of countries participating in the publishing of GBIF data   

<html><body><table><tr><td>区域 Region</td><td>国家数 Country number</td><td>参与国家列表 Countries</td><td>数据发布者 Data providers</td><td>数据量（万条） Data volume (10 K</td></tr><tr><td>北美洲 North America 欧洲 Europe</td><td>2 21</td><td>美国、加拿大 The United States, Canada 安道尔、白俄罗斯共和国、比利 时、丹麦、爱沙尼亚、芬兰、法</td><td>293 664</td><td>56 219.7 54 726</td></tr><tr><td></td><td></td><td>国、德国、冰岛、爱尔兰、卢森 堡、荷兰、挪威、波兰、葡萄牙、 斯洛伐克、斯洛文尼亚、西班牙、 瑞典、瑞士、英国 Andorra，Republic of Belarus, Belgium， Denmark， Estonia, Finland， France， Germany, Iceland, Ireland, Luxembourg, Netherlands， Norway， Poland, Portugal， Slovakia, Slovenia, Spain， Sweden， Switzerland,</td><td></td><td></td></tr><tr><td>大洋洲 Oceania</td><td>3 8</td><td>United Kingdom 澳大利亚、新西兰、汤加 Australia, New Zealand， Tonga 阿根廷、巴西、智利、哥伦比亚、 哥斯达黎加、墨西哥、秘鲁、乌拉</td><td>368</td><td>8 647.2</td></tr><tr><td>南美洲 South America</td><td></td><td>圭 Argentina，Brazil，Chile, Colombia，Costa Rica，Mexico, Peru， Uruguay</td><td>368</td><td>5 648.4</td></tr><tr><td>非洲 Africa</td><td>22</td><td>安哥拉共和国、贝宁、喀麦隆、中 非共和国、刚果民主共和国、厄瓜 多尔、加纳、几内亚、肯尼亚、利 比里亚、马达加斯加、马拉维、马 里、毛里塔尼亚、尼日尔、尼尔利 亚、南非、南苏丹、坦桑尼亚、多</td><td>159</td><td>3005.1</td></tr></table></body></html>

# ChinaXiv合作期刊

<html><body><table><tr><td rowspan="2">亚洲 6 Asia</td><td rowspan="2"></td><td>哥、乌干达、津巴布韦 Angola， Benin， Cameroon, Central Africa，Congo，Ecuador, Ghana，Guinea，Kenya，Liberia, Madagascar，Malawi，Mali, Mauritania, Niger，Nigeria, South Africa， South Sudan, Tanzania， Togo， Uganda, Zimbabwe</td><td></td></tr><tr><td>日本、韩国、越南、中国（包括台 68 湾）、菲律宾、尼泊尔 Japan， South Korea，Vietnam, China (including Taiwan),</td><td>1 736.2</td></tr><tr><td>总计 Total</td><td>Philippines， Nepal 62</td><td>1920</td><td>129 982.6</td></tr></table></body></html>

# 3.2数据使用协议和声明

标本数据在共享和流通之前，需要明确其使用协议，用户才能合法使用和加工。在 2013年，GBIF对1.2万个数据集中的4.16亿条数据记录做了数据协议的总体分析后发现，只有$1 0 \%$ 的数据集拥有协议声明。而数据协议竟然有432种，这极大地阻碍了数据的共享和流通（Peter Desmet,2013）。在这个调研的基础上，GBIF管理委员会进行了广泛的沟通和咨询，对混乱的数据协议做了梳理，要求将所有的现有协议都等同地设置为以下三个协议中：CCO、CC BY和CC BY-NC。经过梳理之后，目前的数据协议占比情况是：CC01.0（56.7%）、CC BY4.0( $2 7 . 6 \%$ ）、CC BY-NC 4.0（15.7%）。通过对北美和澳大利亚的标本数据平台的共享协议（表4）分析，可以看出CC0和CC BY是最受欢迎的共享协议。但目前仍然有大量的标本馆平台，数据界面没有明确标识使用协议，部分数据使用还需要繁琐的线下申请和审批流程，制约了数据流通和再利用。

表4典型标本平台的数据使用协议  

<html><body><table><tr><td>Table 4 Data usage agreement of the main specimen platforms</td><td rowspan="2">国家或区域</td><td rowspan="2">数据量 Data volume</td><td rowspan="2">共享协议类别 Data usage agreement</td></tr><tr><td>平台名称 Platform</td></tr><tr><td>name GBIF 全球</td><td></td><td>166×106</td><td>CC0 1.0、CC BY 4.0、CC BY-NC</td></tr><tr><td></td><td>Global</td><td></td><td>4.0</td></tr><tr><td rowspan="3">iDigBio</td><td>北美</td><td>120×106</td><td>Public-domain or CC0、CC</td></tr><tr><td>North America</td><td></td><td></td></tr><tr><td></td><td></td><td>BY、CCBY-SA、CCBY-NC和CC BY-NC-SA</td></tr><tr><td rowspan="2">AVH</td><td>澳大利亚</td><td>0.66×10</td><td>CC BY 4.0</td></tr><tr><td>Australia</td><td></td><td></td></tr></table></body></html>

# 3.3新技术和新方法

在标本数字化与数据共享的技术与方法上，受到IT技术突飞猛进的影响，在几乎所有应用环节都出现了革新。在数字影像的获取上，流水线式作业的高速扫描系统使得海量标本的快速数字化成为可能，在提升图像质量方面，针对分类学研究的需要，为了强化分类学特征，出现了高清扫描仪、标本的侧光摄影术以及结合解剖镜的显微摄影。在动物标本数字化中，还出现了三维高清影像获取设备等新创举。在野外调查工作中，高清数码相机、智能手机、手持GPS 等智能设备应用普遍，获取了海量的带有精确地理坐标的植物活体影像数据，为标本提供了丰富的背景资料，某些情况下甚至替代标本成为唯一的凭证资料。

在数据管理与发布方面，除了GBIF官方提供的IPT（集成发布工具包）之外，还有BRAHMS (Botanical Research and Herbarium Management System，植物研究和标本馆管理系统)应用比较广泛，由英国牛津大学植物系历经数十年研制而成，广泛用于标本馆、植物园、树木园、种子库等科研单位，可提供数据管理与在线发布。

在数据挖掘与分析方面，基于GBIF数据已有大量的数据分析工具和代码，可对标本和观测数据进行分析和挖掘，仅GitHub 网站上，GBIF 相关的开源代码库就有686个，其中R语言85 个，Python 语言 54个，Java 语言 52个，JavaScript 语言51个。iDigBio、BioCASe、AVH、NSII等平台也都有专门的应用工具专栏。不同开发语言的数据访问工具包也逐步完善，可以通过数据接口与应用程序快速整合，提供灵活高效的编程环境。例如iDigBio提供的Python开发包，使得编程访问iDigBio数据非常顺畅，加上Python 科学计算与人工智能的应用生态，可为数据开发者提供强大的技术支持。国内的软件工具开发领域也正在繁荣，如用于标本馆管理的 herblabel（ZHANG et al.，2017），用于分类树构建与分析的 Taxonomic TreeTool在线工具（Taxonomic TreeTool，2021），用于生物多样性数据清洗、统计与分析的ipybd（Ipybd,2021)，在技术实力，以及应用效果上都令人印象深刻，具有极强的实用性。

随着人工智能深度学习技术的突破，图像识别App 进入了实用期，互联网巨头如谷歌、微软、腾讯、百度等均有专题应用，也公布了开放的API，人工智能识别已经成为一项公共基础服务。应用于生物学领域，就出现了一批生物图像识别的App，如识别植物的形色、花伴侣，用于识别标本的标本馆伴侣等，虽然在覆盖的物种数量、识别精度上还处于起步阶段，但已经在公众科学、科普领域取得了全社会的关注与认可，对常见植物的识别准确率已经能够满足普通公众的日常需求，通过实践证明了人工智能巨大的应用潜力。未来还需要在识别中加入地理因素，充分利用分类学知识，尤其是标本数据，强化训练，扩大识别范围，让人工智能技术获得更多的应用场景。另外在种子鉴定、花粉鉴定、品种鉴定、有害入侵物种自动鉴定等细分领域也将大有可为，让分类学知识通过人工智能服务于社会。标本数字化提供的大量数据，将是人工智能时代机器学习的重要基础。

# 3.4公众科学的发展

标本数字化工作和公众科学探索意愿的结合，催生了各种公众科学项目的诞生。如邱园网站提供了19世纪信件识别、真菌特征补全、植物和真菌标本标签识别和手机珍稀植物保护计划等公众可参与项目。大英历史博物馆开展了兰花观察者（Orchid Observers）的公众科学项目，通过公众参与获得数据，使用兰花作为模型，用于深入研究气候对英国植物区系的影响。

北美地区的iDigBio平台也提出了公众可参与的众包项目以及LiveScience项目。目前影响最大的项目是iNatrualist，它通过移动App 为野外考察提供了非常便捷的工具，创建了在线社区，将分类学家与生物爱好者基于兴趣组织起来，通过众包方式收集了大量的生物影像资料，为科学研究提供了丰富的第一手资料。这些项目拉近了公众与标本馆、数据库的距离，将科学研究、科普宣传与社会服务结合在一起，通过灵活的工作策略，获得了普遍的认同。

与国际趋势类似，中国的公众科学活动经过多年的发展，也形成了多种层次多种方式的公众科学信息平台。包括基于论坛、微博、即时通讯工具等通用公众信息交流平台上的兴趣群组，也包括基于移动 App、微信小程序、Web App 等专用工具的兴趣群组。例如中国自然标本馆（CFH）、中国植物图像库（PPBC）、Biotracks、形色、花伴侣、绿途等，均有大量的科学家与爱好者加入。

这些公众科学平台积累了大量的野外观测资料，是对传统标本数据重要的补充，部分资料可以代替标本成为研究的重要凭证。通过整理与审核，其中高质量的数据可以作为标本数据库中的新型数据资源类型，成为标本数字化资源库的正式组成部分。

# 4.讨论和建议

通过梳理全球标本数字化的现状和进展，与国际相比，国内标本数字化建设与数据共享已经取得了非常好的成效，并具有自己的优势，但仍然存在一些问题，需要努力解决。包括：标本数字化多是基于数据汇缴的项目制管理，进行集中共享，缺少后期的分布式数据网络节点建设，形成了中心强，节点弱的格局，数据质量的持续更新缺乏相应的机制支持。数据共享方面存在共享协议不规范，标识不明确，尤其是在多语言的互联网环境下，大规模数据使用授权上，仍然需要线下沟通，对数据复用造成困扰。另外，在新技术应用、国际合作以及公众科学方面，虽有良好的基础，但还缺乏亮点项目与应用。通过与国际趋势的对比，结合实际情况，提出以下建议：

（1）加强数字化建设、管理和动态更新方面的协同机制建设，确保实物资源和数字化资源信息的同步。加强标本数据与其他生物多样性数据的融合，成为这个学科的重要资源拼图。（2）加强数据整理和发布，促进数据质量的提升，特别是最为重要的分类学和时空信息等。充分开放数据使用协议，利用CC0或者CC BY协议来减少数据使用的阻碍。充分利用GBIFIPT工具对数据对外发布，并通过文献引用的跟踪，分析标本数据在不同领域的应用和服务情况。通过数据的共享服务，通过数据使用，获得数据反馈，获得数据更新，提升数据质量。（3）加强对新技术的学习和引入，特别是机器学习和人工智能技术的应用，能够在标签快速识别分类、标本自动辅助鉴定和特征属性的数据提取等方面发挥作用。加强针对标本数据的开源代码研究。（4）加强区域和国际合作，加强数据的汇聚和整合。通过MAP等区域或国际合作项目来推动跨国家或跨区域的数据建设和共享，带动薄弱国家的标本数字化建设。（5）加强公众科学项目的合作和推广，让专业人员和大众爱好者参与进来，促进标本数据的野外采集、室内整理、在线纠错、数据产品研发等工作的开展。

参考文献：   
ABCDNet: Asia Biodiversity Conservation and Database Network[EB/0L].(2021-04-15) http://www. abcdn. org   
Alexey P. Seregin， 2018. The Largest Digital Herbarium in Russia is now available online[J]． TAX0N，67(2) :463-467   
AVH: The Australasian Virtual Herbarium [EB/0L]. (2021-04-15) https://avh.chah.org.au Culley，T. M. 2013. Why vouchers matter in botanical research[J]． APPL PLANT SCI 1(11) 1300076.   
East African Herbarium [EB/OL]. (2021-04-15) http://eaherbarium. museums.or.ke/ Geo Potts Herbarium (BLFU)， 2021. [EB/OL]. (2021-4-15) https://herbaria. plants.ox.ac.uk/bol/blfu/   
Global Biodiversity Information Facility (GBIF)， 2021. GBIF Registry of Scientific Collection(GRSciCol1)[EB/0L].(2021-04-15） https://www.gbif.org/en/grscicol1   
Global Biodiversity Information Facility (GBIF)， 2021. Occurrence Search.([EB/OL]. (2021-04-15) https://www.gbif.org/occurrence/search   
Hobern D， Apostolico A， Arnaud E， 2012. Global Biodiversity Informatics Outlook: Delivering biodiversityknowledge in the information age[EB/OL]. (2021-04-15) https://doi.org/10. 15468/6jxa-yb44   
IntegratedDigitizedBiocollections (iDigBio)， 2021. [EB/OL]. (2021-04-15) https://www.idigbio.org/   
Ipybd-Powerful Data Cleaner For Biodiversity[EB/OL]. (2021-05-13) https://github.com/leisux/ipybd   
J. Mason Heberling， Bonnie L. Isaac， 2017. Herbarium specimens as exaptations: New uses for old collections[J]. AMER J BOT,104:1-3.   
Krishtalka L， Dalcin E,Ellis S， 20l6. Accelerating the discovery of biocollections data. Copenhagen: GBIF Secretariat.[EB/0L] (2021-04-15) http://www. gbif.org/resource/83022   
Le Bras G, Pignal M, Jeanson ML， 20l7. The French Muséum national d'histoire naturelle vascular plant herbarium collection dataset. Sci Data. 2017 Feb 14;4:170016. doi: 10.1038/sdata.2017.16.[EB/0L] (2021-4-15) https://pubmed.ncbi.nlm.nih.gov/28195585/ MA KP,2017. Mapping Asia Plants: A cyberinfrastructure for plant diversity in Asia[J]. BIODIV SCI，25(1):1-2[马克平,2107．亚洲植物多样性数字化计划[J]．生物多样性，25(1)：1- 2]   
MA KP， ZHU M, JI LQ,2018. Establishing China Infrastructure for Big Biodiversity Data［J]．BULL CAS，33(8)：838-845．［马克平，朱敏，纪力强，2018．中国生物多样性大数据平 台建设［J].中国科学院院刊，33(8)：838-845] Peter Desmet,2013. Analyzing the licenses of all 11, $0 0 0 +$ GBIF registered datasets [EB/0L]. (2021-04-15) http://peterdesmet.com/posts/analyzing-gbif-data-licenses.html Seregin A. P. (Ed.),2021. Moscow Digital Herbarium: Electronic resource.-Moscow State University， Moscow. [EB/0L]. (2021-04-15) https://plant.depo.msu.ru/   
Soltis，P. S. 2017. Digitization of herbaria enables novel research[J]. AMER J BOT 104: 1-4.   
speciesLink [EB/0L]. (2021-04-15) http://www.splink.org.br/   
Taxonomic Tree Tool (TTT)[EB/0L]. (2021-04-15) http://ttt.biodinfo.org/   
The South African National Biodiversity Institute (SANBI） Website [EB/OL]. (2021-04-15) https://www. sanbi.org/   
Thiers，B. 20l7. The World's herbaria 2016:A summary report based on data from Index Herbarium. [EB/0L]. (2021-04-15) http://sweetgum.nybg.org/science/ih/   
Wilkinson，M. D.，M. Dumontier，I. J. Aalbersberg，2016. The FAIR Guiding Principles forscientific data management and stewardship. Scientific Data 3:160018. [EB/0L] (2021-04-15) https://doi.org/10.1038/sdata.2016.18   
ZHANG J,2017. Biodiversity science and macroecology in the era of big data[J].BIODIV SCI,25(4)，355-363．[张健,2017.大数据时代的生物多样性科学与宏生态学[J]．生物多样 性,25(4):355-363.]   
ZHANG JL,ZHU HL,LIU JG,2016.Principles behind designing herbarium specimen labels and the Rpackage‘herblabel’[J]．Biodiv Sci,24(12)：1345-1352.[张金龙，朱慧玲，刘金 刚,2016．植物标本标签设计的原则及R程序包 herblabel[J].生物多样性，24(12)：1345-1352.]