# 社会化推荐研究进展与发展趋势演化基于文献计量和社会网络分析的视角

# 李飞张健 王宗水

(北京信息科技大学经济管理学院北京 100192)(绿色发展大数据决策北京市重点实验室北京 100192)

摘要：【目的】从文献计量和社会网络分析的角度对社会化推荐进行内容特征及网络演化的研究，归纳领域研究热点和发展趋势。【方法】以WoS数据库为数据源，采用人工判读法、关键词共现、文献计量、社会网络分析及数据可视化等方法对样本数据进行数据挖掘和关联分析。【结果】检索到社会化推荐类文献3701篇，论文数量整体呈上升趋势，以发文量阈值为阶段划分标准，将社会化推荐的发展演化趋势划分为三个阶段，各阶段研究特征明显。【局限】仅以关键词为探究文献内容特征的依据，内容深度挖掘相对不足，其中阶段划分是为了分析研究内容及演化趋势的变化，并不存在统一的划分标准。【结论】我国学者在该领域的国际影响力逐年上升，领域研究内容方面阶段性变化特征明显，社会化媒介、协同过滤等传统研究方向一直保持较高关注度。

关键词:社会化推荐研究进展 发展趋势社会网络分析文献计量

分类号：TP393

# 1引言

“互联网 $+ ^ { , , }$ 、人工智能、4G/LTE、云计算等新兴技术产业的迅猛发展，使得快速低廉的网络通信设备得到了极大的应用普及。Web2.0、社会媒体、社交平台等网络应用的逐步推广，致使用户原创信息内容突增，频繁的用户交互，让更多带有社会关系属性的信息呈现出爆炸增长的态势[1]。面对海量异构信息过载问题，使用线上推荐系统可以为用户有效地过滤冗余信息，提高服务质量、减少成本投入和噪声影响[2-4]开放自由的网络环境和社交媒介极大提高了用户的参与程度[5]，为了缓解数据稀疏冷启动等问题，学者们将社会属性融入到传统的推荐框架中，构建以社会关系网络为主的轻量级知识体系，通过挖掘用户间协作及信任关系，提高整体系统的推荐质量及用户体验

新技术领域已表现出较好的发展前景和应用潜力，Facebook、LinkedIn、豆瓣网、微博、Last.fm等社交媒体中好友推荐服务展现出较为广阔的商业用途，文献[6-11]关于社会化推荐的研究也体现出学术界关注度的上升。近些年，伴随社交信息的不断增多，更深层次的社会关系网络被挖掘利用，学者们对社会化推荐类的研究呈现出全面、多元化等特点，Wang 等、Quijano-Sanchez等通过引入新的参数类型将用户社会化属性融人到传统的推荐框架，构建出数据紧密、扩展性较好的用户推荐框架[12-13]；Hotho 等受网页排序思想的启发提出大众分类搜索和FolkRank排序相融合的推荐算法[14]；Rendle 等借鉴物理学概念提出 RTF算法，利用张量分解进行高维数据降维排序[15]；Song等基于图聚类将用户资源关系用二分图表示，较好地提高了推荐算法的效率[16]；Abbasi 等通过将高层次标签特征和低层次图像特征进行组合训练，得到的混合特征向量分类器较好地提升了分类器的性能[17]；Eck等提出直接预测音频内容的方法，缓解了系统冷启动问题[18]；此外与传统推荐算法模型的结合仍旧保持着较高的关注度，矩阵分解[11]、协同过滤[19]等算法融合类的研究，针对阶段领域关键技术的评述性研究[20以及改进算法框架、调整模型参数、优化预测结果等研究[21-22]。但少有学者从文献计量和社会网络分析的角度对领域相关文献进行统计分析，更缺乏对本领域发展历程和研究内容的比较分析。

鉴于此，本文首先通过分析现阶段社会化推荐领域的研究现状，简述此领域所涉及的相关技术和应用场景，分析领域所面临的热点问题和主要挑战。为了进一步探究比较领域演化过程和发展趋势，本文以国际权威文献数据库WebofScience为基础样本数据源借助BICOMB2①、Pajek、Excel、CorelDRAW等工具，采用人工判读[23]、文献计量[24]、社会网络分析[25]、关键词共现[26]等方法，对样本数据进行文本挖掘和网络演化分析，并以论文量阈值为整体阶段演化的划分标准[27]，将社会化推荐划分成三个阶段，通过梳理关联阶段数据找出各阶段的发展状况，并根据整体趋势特征预测领域的研究前景和发展方向。

# 2社会化推荐相关研究

社会化推荐所涉及的社会网络分析技术源自复杂网络领域，是描述自然科学、管理科学、社会科学等复杂互联模型的有力工具。其中网络建模、社会影响力分析、社区检测、安全隐私等内容都在该领域占有较大的研究比重。

从社会学角度研究发现，相同社会群体中的用户可以形成相对安全的交互平台，用户间的决策会互相影响，相互联系的群体会受其周边环境等社会因素影响，而其群体内部用户行为兴趣表现出较高的相似性[28-29]。由于用户社会特性的突显，使得考虑关系链接属性的推荐系统，具有较高的预测精准度和个性化效果。并且社会关系属性的加入，可以更为真实地模拟现实生活中的推荐流程。社会化推荐类的研究本身基于社会网络分析理论，Siersdorfer等从方法特性角度提出概念定义“一种基于多维社会网络环境的用户推荐预测过程"[30],Guy 等根据应用平台定义为"一种借助社会媒介解决信息过载问题的方法技术"[31]，Arazy 等、Kazienko 等从多领域规则角度出发进行定义[32-33]，也有学者从构建系统框架角度进行定义[34]，其中文献[35]从广义和狭义两个层面进行定义。笔者通过归纳总结现阶段研究成果和相关文献，遵循文献[35]和第19届国际万维网大会(WWW2010)"社会推荐导论"中[36的界定方法从狭义层面给出本文定义：社会化推荐是一种结合社会网络与推荐系统的交叉学科，是以社会媒介为平台，在传统的推荐算法框架中融入用户社会属性信息，用以缓解数据稀疏冷启动、提高推荐效果性能的智能化信息过滤技术。

社会化推荐的主要生成技术是由传统推荐算法与社会化网络分析技术融合产生的。有学者通过量化社交关系、调整模型参数，提高新框架模型的可扩展性与适应性，如 STE[37]、SocialMF[38]、TrustWalker Mode[39]等，也有通过结合网络结构分析将用户关系信息填充至属性列表改进推荐过程的，如 SoNARS[40]、GLOSS[41]、社会网络协同过滤[42]等，还有从用户角度出发进行社会化推荐建模的[9-10]。商业模式的应用成熟也为社会化推荐提供了较为广阔的开发环境和基础数据来源，社会书签网站[43]、Twitter[44]、社交推荐电视[45]、Last.fm等都为用户提供了个性化推荐服务。总结现阶段技术发现多算法融合是研究趋势，协同过滤、矩阵分解以及概率模型等传统算法依旧是较常用的方法，张量分解是最近关注度较高的应用技术，其主要思想是通过将高维空间预测问题分解到低维度空间矩阵进行优化处理[15]。

目前社会化推荐应用受到了越来越多的关注，但传统推荐固有问题如数据稀疏冷启动现象等仍是当下研究所面临的主要难题。在数据表示层面，传统推荐系统大多为用户-项目双向二维数据结构表示，而社会化推荐则更多通过三元数组或超三角图(用户、资源、标签)三维数据结构来表示，如何提高算法模型可扩展性是未来一个有趣的研究方向。现阶段文献大多基于用户的评级预估，通过评分数值大小反映用户的喜好，如何更好地将非结构化数据和社会关系属性融入传统的推荐框架，某种程度上仍需进一步研究。大数据环境下新兴应用的推广成熟，进一步加剧了用户异构数据的井喷现象，像社会关系属性的确定及量化处理，跨社会媒体异构数据的分析，社会网络跨平台模型的建立，用户兴趣偏好的迁移捕捉等[46-48]一系列新问题的出现，还有待探索。

随着人工智能和深度学习研究的不断深人，社会化推荐在算法层面与新兴技术领域的融合，表现出较高的预测准确度和较好的推荐效果，如将协同过滤、timeSVD $^ { + + }$ 模型与 SDAE 框架结合解决冷启动问题[49];通过混合推荐使用深度神经网络进行项目内容特征学习，缓解电影评分预测中的数据稀疏问题[50，在Twitter应用平台上融人前馈神经网络进行标签字符学习，从而在深层次范围分析非结构化数据[51]；还有将社交网络纳人用户间的隐含层单元，借助RBM模型获取用户偏好提高兴趣学习的精准度[52]，以及借助并行递归神经网络结构p-RNN进行绘画建模扩充[53]。

通过对文献研究进行归纳总结，不难发现社会化推荐隶属于推荐系统与社会网络分析研究的交叉领域，通过引入用户社会关系可以有效缓解传统推荐系统所面临的数据稀疏冷启动等问题。但新网络环境下数据结构的变换、服务模式的部署、时变网络信息及其负面关系的处理等一系列技术问题，仍亟需深入探究解决。近些年，随着社交化推荐的快速发展，业内涌现出大量高水平的理论研究成果及应用系统，因此有必要对已现有文献进行知识梳理，通过统计计量和文本挖掘深人剖析此领域的发展历程和研究现状，为未来的研究提供理论依据。

# 3数据获取与方法选择

在现阶段社会化推荐研究发展的基础上，为了更进一步探究领域研究内容层面的特征关系和演化趋势，通过文本挖掘获取论文内容特征，使用文献计量[24]、关键词共现[2和数据可视化的方法，对现阶段国际主流期刊的文献进行系统的定量和定性分析，科学直观地表示此领域研究现状。

# 3.1 数据获取

选取WebofScience为样本数据来源，检索式为：主题 $\dot { \bf \Phi } = { \bf \Phi }$ ("social recommend\*")；研究方向 $\ c =$ ("COMPUTERSCIENCE")；时间跨度 $= ( ^ { 6 6 } 1 9 9 7 - 2 0 1 6 ^ { 3 9 } )$ ，数据库 $\mathbf { \Sigma } = \mathbf { \Sigma }$ “SCI-EXPANDED，SSCI，CPCI-S，CPCI-SSH，ESCI,CCR-EXPANDED,A&HCI,IC"；检索日期:“2017年1月21日”，检索结果为3701篇文献，经人工判读和数据预处理，删除无法获取及其与研究内容不相关的论文，最后筛选得到2899篇。

图1为全球整体论文数量的年度分布和发展趋势这些文献由85个国家和区域的2929位学者完成，其中论文量前 10 位的国家年度发文分布情况一并予以标注，统计结果是全球大部分论文来自少数几个高产国家，论文分布基本符合巴莱多定律。

![](images/5d24ce70b900ee170689c3bd82e4819002f976363fc6adef00ace918d4f39955.jpg)  
图1全球整体论文量和各国按年份的趋势

根据发文量年度数据分布表绘制论文增长变化曲线，从图1可以发现，全球整体研究呈现出类指数级上升趋势，趋势线回归公式为 $y = 0 . 1 2 2 4 1 5 4 3 2 x ^ { 3 }$ $- 7 3 4 . 2 2 7 8 3 4 5 x ^ { 2 } + 1 4 6 7 9 2 6 . 8 1 1 x - 9 7 8 2 6 5 7 3 1 . 1$ ，根据公式计算出判定系数 $R ^ { 2 } { = } 0 . 9 6 2 2 8 7 0 7 5$ ，接近1，表示回归方程拟合性较好，趋势线可信性较高。通过初步分析发文量发现：1997年-2008年的年论文量均小于100，合计占文献总量的比重也较少，仅为$1 1 . 0 7 \%$ ；2009年-2013年论文量分布在(100,350)区间内，总量占有比重为 $3 6 . 0 5 \%$ ；2014年-2016年论文量均大于350，合计发文量占整体的 $5 2 . 8 8 \%$ ，因此采用文献[27]的方法，按照论文量阈值将社会化推荐研究阶段分成：1997-2008、2009-2013、2014-2016三个阶段。通过进一步对比分析发现社会化推荐研究初期，由于相关理论缺乏、学科应用场景单一，导致相关科技文献发文量较少，但随着社交媒体的发展成熟、理论研究的不断深入及其相关学者和机构的关注度上升，发文量增长较快，特别是在2008年和2014年前后都有明显的文献扩增趋势①。自1997年代表性文献[54]发表以来，社会化推荐以其良好的发展前景和应用潜力引起了大量学者的关注，2009 年国际顶级会议RecSys开始设立社会化推荐的专题研讨会，其中报告分会场论文4篇(共28篇年度会议论文)，成为该领域中最为热点的应用研究之一②

# (1）各国论文量统计

从图1可以看出，论文量前10位的国家对社会化推荐的关注度整体随时间推移不断上升，此处统计以作者最新发表文章所列的第一单位所属国家为准，通过统计分析发现这些论文高产国家的发文量占全球的$8 4 . 9 4 \%$ 。根据各国论文量得到的全球论文地理分布如图2所示，由于涉及国家较多，此处仅对论文量前50名的国家进行标注，以不同的灰度标记来体现不同国家的论文量差异。

![](images/c21701321f3942554c716f7e0576a53ef2c40fd5bd8be8df627937422ad0c785.jpg)  
图2各国论文量地理分布(1997-2016)

由图2可知，除几个高产国家外，欧洲发达国家文献量明显较多，从论文引证的视角判断学术价值，发现早期的高水平论文几乎全部产生自欧美国家。我国此领域研究虽然起步较晚，但随着关注度的提高，论文量呈现逐年上升趋势，2010年论文量首超美国，总量占到整体的 $3 1 . 7 0 \%$ ；2017年国际人工智能协会首次考虑中国春节因素而决定改期①，体现出华人学者影响力的提高，但就论文整体的引用量相比欧美发达国家依旧较弱，业内主流核心期刊依旧较少，究其原因不难发现互联网起步较早是欧美发达国家的优势，然而随着国内政策、技术及其社交平台的快速发展，我国学者在全球的影响力和学术地位呈现出赶超之势。

# (2）主要期刊分布

从期刊分布角度统计论文量，发文量最高的前15个期刊如表1所示，通过InCites数据库获取期刊的影响因子和立即指数，合计论文量约占到整体的

$10 . 1 5 \%$ ，而且这些期刊全部来自欧美等发达国家，其中EXPERT SYSTEMS WITH APPLICATIONS、INFORMATION SCIENCES和KNOWLEDGE-BASEDSYSTEMS等期刊的发文量、质量及其影响力也呈现出一定的领先优势。进一步分析发现社会化推荐领域的高产期刊大多来自计算机科学、人工智能、信息系统、软件工程和管理科学等领域的专业期刊，此外，检索发现国际顶级学术会议和学协会，例如SIGIR、SIGKDD、IEEE和AAAI等每年也都会有大量此领域的论文发表，并对领域研究发展产生比较重要的影响。

表1全球发文量前15的期刊  

<html><body><table><tr><td>序号</td><td>期刊</td><td>出现频次</td><td>发文百分比</td><td>影响因子</td><td>立即指数</td><td>国家</td></tr><tr><td>1</td><td>EXPERTSYSTEMSWITHAPPLICATIONS</td><td>52</td><td>1.393</td><td>2.981</td><td>0.938</td><td>USA</td></tr><tr><td>2</td><td>INFORMATION SCIENCES</td><td>38</td><td>1.018</td><td>1.832</td><td>0.500</td><td>USA</td></tr><tr><td>3</td><td>KNOWLEDGE-BASED SYSTEMS</td><td>31</td><td>0.83</td><td>1.702</td><td>0.291</td><td>NETHERLANDS</td></tr><tr><td>4</td><td>NEUROCOMPUTING</td><td>29</td><td>0.777</td><td>2.392</td><td>0.563</td><td>NETHERLANDS</td></tr><tr><td>5</td><td>MULTIMEDIATOOLSANDAPPLICATIONS</td><td>29</td><td>0.777</td><td>1.331</td><td>0.125</td><td>NETHERLANDS</td></tr><tr><td>6</td><td>IEEETRANSACTIONS ONKNOWLEDGE AND DATA ENGINEERING</td><td>27</td><td>0.723</td><td>2.476</td><td>0.257</td><td>USA</td></tr><tr><td>7</td><td>ONLINE INFORMATIONREVIEW</td><td>25</td><td>0.67</td><td>1.152</td><td>0.077</td><td>ENGLAND</td></tr><tr><td>8</td><td>DECISION SUPPORT SYSTEMS</td><td>25</td><td>0.67</td><td>2.604</td><td>0.246</td><td>NETHERLANDS</td></tr><tr><td>9</td><td>IEEETRANSACTIONSONMULTIMEDIA</td><td>21</td><td>0.562</td><td>1.152</td><td>0.077</td><td>USA</td></tr><tr><td>10</td><td>JOURNAL OFUNIVERSALCOMPUTER SCIENCE</td><td>20</td><td>0.536</td><td>0.546</td><td>0.048</td><td>AUSTRIA</td></tr><tr><td>11</td><td>MULTIMEDIA SYSTEMS</td><td>19</td><td>0.509</td><td>1.410</td><td>0.349</td><td>GERMANY</td></tr><tr><td>12</td><td>JOURNALOF INFORMATIONSCIENCE</td><td>17</td><td>0.455</td><td>2.604</td><td>0.246</td><td>ENGLAND</td></tr><tr><td>13</td><td>KNOWLEDGEAND INFORMATION SYSTEMS</td><td>16</td><td>0.428</td><td>1.702</td><td>0.291</td><td>ENGLAND</td></tr><tr><td>14</td><td>JOURNAL OFTHE AMERICAN SOCIETYFOR INFORMATION SCIENCEAND TECHNOLOGY</td><td>15</td><td>0.402</td><td>2.452</td><td></td><td>USA</td></tr><tr><td>15</td><td>JOURNALOFMANAGEMENTINFORMATION SYSTEMS</td><td>15</td><td>0.402</td><td>3.025</td><td>0.098</td><td>USA</td></tr></table></body></html>

# (3）关键词统计

关键词是文献研究内容特征的高度概括和总结，通过文献中关键词共现往往可以较为有效地获取该领域的研究热点[55]。为避免不同阶段因样本量不同而引起的误差，此处采用定量分析选取各阶段引用量最高的500篇文献作为样本，高引用量在某种程度上不仅可以反映此领域研究的热点和趋势，还能体现此文献的领域研究重要性。采用BICOMB2对样本数据进行关键词提取，通过人工判读手动修改关键词列表，将大小写、单复数、同义词、缩写等具有相同含义的词汇进行合并处理以保持检索词汇一致性，通过Excel进行词频汇总统计排序。表2为三个阶段排在前10位的高频词汇，其中阶段一共有1405个关键词，词频 $\geqslant 2$ 的有573个，占阶段总词量的 $40 . 7 8 \%$ ；阶段二有2065个关键词，词频 $\geqslant 2$ 的有263个，占整体的 $12 . 7 3 \%$ ；阶段三有1390个关键词，词频 $\geqslant 2$ 的有176个，占整体的 $12 . 6 6 \%$ 。

表2三个阶段关键词词频统计  

<html><body><table><tr><td rowspan="2">序号</td><td colspan="2">阶段一</td><td colspan="2">阶段二</td><td colspan="2">阶段三</td></tr><tr><td>关键词</td><td>词频</td><td>关键词</td><td>词频</td><td>关键词</td><td>词频</td></tr><tr><td>1</td><td>recommender system</td><td>120</td><td>recommender system</td><td>134</td><td>recommender system</td><td>131</td></tr><tr><td>2</td><td>social network</td><td>65</td><td>social network</td><td>89</td><td>social network</td><td>76</td></tr><tr><td>3</td><td>collaborative filtering</td><td>37</td><td>ficil media/eolabatie</td><td>37</td><td>collaborative filtering</td><td>49</td></tr><tr><td>4</td><td>personalization</td><td>29</td><td>algorithms</td><td>36</td><td>social media</td><td>33</td></tr><tr><td>5</td><td>trust</td><td>26</td><td>social network analysis</td><td>26</td><td>location based social network</td><td>29</td></tr><tr><td>6</td><td>social network analysis</td><td>19</td><td> social tagging</td><td>22</td><td>algorithms</td><td>18</td></tr><tr><td>7</td><td>information retrieval/ experimentation</td><td>18</td><td>data mining</td><td>21</td><td>topic modeling</td><td>16</td></tr><tr><td>8</td><td>sogiatms/ontoatamin/</td><td>17</td><td>trust</td><td>18</td><td>socia recomendation/ atix</td><td>15</td></tr><tr><td>9</td><td>NLP</td><td>16</td><td>Personalization/Twitter</td><td>16</td><td>Twitter/Personalization/data mining/location recommendations</td><td>13</td></tr><tr><td>10</td><td>evaluation</td><td>15</td><td>experimentation</td><td>15</td><td>online social networks</td><td>12</td></tr><tr><td>频次累计百分比</td><td colspan="2">15.88%</td><td colspan="2">13.27%</td><td colspan="2"></td></tr></table></body></html>

# 3.2 研究方法

# (1）共词分析法

表述学科领域研究主题的关键词出现在同一文献中的现象称为关键词共现，以关键词在同一文献出现的频率为基础进行聚类分析常被用于探索潜在主题和学科间的发展联系及学术趋势演化[28,56]。相比其他文本分析方法，关键词共现使用定量分析法概述研究领域的热点，以客观数据呈现学科研究的现有水平[57-58],通过横向比较纵向分析形成的共现网络得到领域学科特点和关键词间亲疏关系[59-60]。本文使用共现指数来表示不同关键词间的关联程度，此处借鉴Ochiia系数法进行关键词共现的研究[61-62]，如公式(1)所示。

$$
O _ { m n } = \frac { C _ { m n } } { C _ { m } ^ { 1 / 2 } \times C _ { n } ^ { 1 / 2 } }
$$

其中, $O _ { m n }$ 为关键词 $m$ 和 $n$ 之间的Ochiia 系数, $C _ { m n }$ 为关键词 $i$ 和 $j$ 共现数, $C _ { m }$ 为关键词 $\mathbf { \nabla } _ { m }$ 出现总次数, $C _ { n }$ 为关键词 $n$ 出现总次数。

# (2）社会网络分析

作为社会化推荐的主要研究领域，社会网络分析源自复杂网络，是一种综合图论和数学模型的定量分析方法，主要针对网络成员间的社会关系，进行量化分析研究[25]。目前的社会网络分析软件较多，如Ucinet、Pajek、NetMiner和StOCNET等，本文借助BICOMB2生成关键词共现矩阵，使用Pajek辅助分析矩阵数据，构建关键词间的特征关系网络。依据链接网络结构的统计特性，分析归纳出社会化推荐的主题演化过程和结构变化规律。

网络结构特性可以从中心性、度分布、聚集度系数和网络平均度刻画描述[63-65]。本研究更关心各节点距离中心的程度，故选用接近度中心(Closeness Centrality)描述节点中心性，在构建的无向连通图中，节点 $\nu _ { i }$ 到节点$\nu _ { j }$ 的距离为 $d _ { i j } ,$ 则接近度中心性计算如公式(2)所示。

$$
C c ( \nu _ { i } ) = \frac { N - 1 } { \displaystyle \sum _ { j = 1 , j \neq i } ^ { N } d _ { i j } }
$$

在构建的关键词网络图中， $\mathbf { M }$ 为网络边数， $\mathrm { ~  ~ N ~ }$ 为网络节点数，则网络平均密度如公式(3)所示

$$
L = { \frac { 2 M } { N ( N - 1 ) } } 
$$

通过聚类系数来体现临近节点的集团性质， $C C _ { 1 }$ 表示具有一个邻接节点的聚集度系数，节点 $\mathbf { \sigma } _ { \nu }$ 直接连接且包含1个邻居节点的节点用 $\left| E ( G _ { 1 } ( \nu ) ) \right|$ 表示，

$d e g ( \nu )$ 表示关键词 $\mathbf { \sigma } _ { \nu }$ 的邻接节点数，如公式(4)所示。

$$
C C _ { 1 } = \frac { 2 \big | E ( G _ { 1 } ( \nu ) ) \big | } { d e g ( \nu ) \times ( d e g ( \nu ) - 1 ) }
$$

整体网络节点间亲密程度使用平均距离描述，网络中所有节点 $\nu _ { i }$ 的度 $k _ { i }$ 的平均度如公式(5)所示

$$
\left. k \right. = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } k _ { i }
$$

# 4 研究结果

# 4.1集聚系数三阶段比较

以词频统计结果为基础建构关键词共现系数矩阵，根据本文对社会化推荐的定义，此处主要研究推荐系统和社会网络两个方面，所以仅列出各阶段部分较具代表性的高频词汇在这两个方面的Ochiia系数，如表3所示。

表3三个阶段推荐系统和社会网络共现系数统计  

<html><body><table><tr><td colspan="2">阶段一</td><td>推荐系统 社会网络</td><td></td><td>阶段二</td><td></td><td>推荐系统</td><td>社会网络</td><td>阶段三</td><td></td><td>推荐系统</td><td>社会网络</td></tr><tr><td>关键词</td><td>词频</td><td>共现系数</td><td></td><td>关键词</td><td>词频</td><td>共现系数</td><td></td><td>关键词</td><td>词频</td><td></td><td>共现系数</td></tr><tr><td>协同过滤</td><td>37</td><td>0.41</td><td>0.06</td><td>社会化媒介</td><td>37</td><td>0.04</td><td>0.07</td><td>协同过滤</td><td>49</td><td>0.42</td><td>0.16</td></tr><tr><td>个性化</td><td>29</td><td>0.34</td><td>0.09</td><td>协同过滤</td><td>37</td><td>0.38</td><td>0.30</td><td>社会化媒介</td><td>33</td><td>0.12</td><td>0.04</td></tr><tr><td>信誉</td><td>26</td><td>0.18</td><td>0.26</td><td>算法</td><td>26</td><td>0.22</td><td>0.14</td><td>基于位置的 社会网络</td><td>29</td><td>0.08</td><td>0.06</td></tr><tr><td>社会网络分析</td><td>19</td><td>0.13</td><td>0</td><td>社会网络 分析</td><td>22</td><td>0.13</td><td>0</td><td>算法</td><td>18</td><td>0.04</td><td>0.08</td></tr><tr><td>信息检索</td><td>18</td><td>0.04</td><td>0.06</td><td>社会标签</td><td>21</td><td>0.15</td><td>0.02</td><td>主题建模</td><td>16</td><td>0.09</td><td>0.06</td></tr><tr><td>实验法</td><td>18</td><td>0.17</td><td>0.12</td><td>数据挖掘</td><td>19</td><td>0.10</td><td>0.04</td><td>社会化推荐</td><td>15</td><td>0.11</td><td>0.09</td></tr><tr><td>社会标签</td><td>17</td><td>0.38</td><td>0</td><td>信誉</td><td>18</td><td>0.08</td><td>0.22</td><td>矩阵分解</td><td>15</td><td>0.25</td><td>0.06</td></tr><tr><td>数据挖掘</td><td>17</td><td>0</td><td>0.03</td><td>个性化</td><td>16</td><td>0.13</td><td>0.16</td><td>Twitter</td><td>13</td><td>0.07</td><td>0.03</td></tr><tr><td>算法</td><td>17</td><td>0.15</td><td>0.21</td><td>Twitter</td><td>16</td><td>0.13</td><td>0.05</td><td>个性化</td><td>13</td><td>0.17</td><td>0</td></tr><tr><td>本体</td><td>17</td><td>0.07</td><td>0.06</td><td>实验法</td><td>15</td><td>0.11</td><td>0.05</td><td>位置推荐</td><td>13</td><td>0.07</td><td>0.03</td></tr><tr><td>自然语言处理</td><td>16</td><td>0.04</td><td>0.04</td><td>性能</td><td>14</td><td>0.14</td><td>0.11</td><td>数据挖掘</td><td>13</td><td>0.12</td><td>0.1</td></tr><tr><td>评估</td><td>15</td><td>0.05</td><td>0</td><td>聚类</td><td>14</td><td>0.07</td><td>0</td><td>在线社交 网络</td><td>12</td><td>0.1</td><td>0</td></tr><tr><td>标签</td><td>14</td><td>0.15</td><td>0.10</td><td>自然语言 处理</td><td>13</td><td>0.02</td><td>0</td><td>实验法</td><td>11</td><td>0.05</td><td>0.07</td></tr><tr><td>社会化</td><td>13</td><td>0.15</td><td>0.07</td><td>社会化推荐</td><td>12</td><td></td><td>0.03</td><td>社会影响</td><td>10</td><td>0.08</td><td>0.07</td></tr><tr><td>互联网</td><td>12</td><td>0.05</td><td>0.07</td><td>信息检索</td><td>12</td><td>0.02</td><td>0</td><td>好友推荐</td><td>9</td><td>0.03</td><td>0.11</td></tr><tr><td>机器学习</td><td>12</td><td>0.07</td><td>0.05</td><td>本体</td><td>12</td><td>0.12</td><td>0</td><td>链路预测</td><td>9</td><td>0.06</td><td>0.08</td></tr><tr><td>人为因素</td><td>11</td><td>0.06</td><td>0.11</td><td>群推荐</td><td>11</td><td>0.03</td><td>0.06</td><td>微博</td><td>9</td><td>0.09</td><td>0.04</td></tr><tr><td>P2P</td><td>11</td><td>0.08</td><td>0.19</td><td>评估</td><td>11</td><td>0.05</td><td>0.03</td><td>社会网络 分析</td><td>9</td><td>0.09</td><td>0</td></tr><tr><td>信息提取</td><td>11</td><td>0.06</td><td>0.07</td><td>主题建模</td><td>10</td><td>0</td><td>0.03</td><td>性能</td><td>9</td><td>0.06</td><td>0</td></tr><tr><td>信誉</td><td>10</td><td>0.06</td><td>0.31</td><td>大众分类</td><td>10</td><td>0.11</td><td>0</td><td>随机游走</td><td>9</td><td>0.03</td><td>0.11</td></tr><tr><td>合计</td><td>340</td><td>2.64</td><td>1.90</td><td>合计</td><td>313</td><td>2.03</td><td>1.31</td><td>合计</td><td>314</td><td>2.13</td><td>1.22</td></tr></table></body></html>

进一步归纳总结发现三个阶段呈现以下特点：

阶段一：各关键词与推荐系统的共现系数高于社会网络，协同过滤和社会化标签与推荐系统的共现系数分别为0.41和0.38，算法类关键词如矩阵因子分解、概率模型等保持较高的共现系数，信誉和信托机制与社会网络的共现系数达0.26和0.31，这表明此阶段揭示领域特性的关键词共现系数比较高，其中体现领域属性词汇如信息检索、自然语言处理、机器学习、信息抽取、本体、互联网等较多。本阶段社会化推荐研究呈现出多领域融合特点，发展趋势较为分散，研究内容偏向于文本处理，社会化推荐研究处于初步探索阶段，交叉学科特性表现明显。

阶段二：各关键词共现系数相比阶段一有所下降，社会网络与协同过滤共现系数高达0.30，说明学者们对社会网络和协同过滤间关系比较关注，社会化媒介、聚类、主题模型等算法应用类词频上升，方法属性词如数据挖掘与推荐系统的共现系数也有所上升，领域类的关键词较上一阶段明显减少，社会化推荐特性词汇关注度普遍提高，如群推荐、社会化推荐、大众分类法(Folksonomy)都具有较高的关注度。本阶段工具应用、算法技术类词汇较多，领域名称类词汇关注度下降，研究内容偏向于算法改进优化，社会化推荐研究处于算法优化模型扩展阶段。

阶段三：此阶段各个关键词与社会网络的Ochiia系数累计最低，推荐系统累计系数较上阶段有所上升，关键词与社会化网络共现系数为0的比例下降，随着GPS、无线通信网络发展成熟与位置相关的新兴技术应用获得较高的关注度，如基于位置的社会网络、位置推荐等，基于网络图的算法模型较为热门如链路预测、随机游走等，传统技术类关注度依旧较高如协同过滤、矩阵因子分解等，社交网络类研究较为集中如Twitter、微博等，个性化推荐历经三个阶段演化词频不断下降但关注度依旧较高，更能体现用户群体特性和社会关系的推荐类词汇关注度不断上升，如好友推荐和位置推荐等。

通过三个阶段的共现系数比较，推荐系统的共现系数一直高于社会网络，协同过滤、个性化、社会网络分析、实验法、数据挖掘、算法和社会化媒介在社会化推荐系统研究领域一直保持较高的词频，根据三阶段的共现系数累计统计发现推荐系统研究发展处于较为平稳的状态，社会网络经历三阶段演化累计系数不断下降，但其他同类关键词如社会关系网络等属于社会网络子类的关键词不断增多。而且关键词中体现用户社会化和群体化特性的应用也在不断增加，如朋友推荐、社区发现、群推荐等。

# 4.2基于网络中心性的三阶段比较

选取词频 $\geqslant 5$ 的关键词，根据公式(2)计算各个阶段关键词的中心性，借鉴文献[63]的方法将中心性划分为三个阶段，并分别在图3、图4和图5中展现出三个阶段的关键词中心性层次分布网络，其中：核心节点是$C c ( \nu _ { n } ) \geqslant 0 . 6 1$ 的 $\cdot$ 节点，中心节点为 $0 . 6 1 > C c ( \nu _ { n } )$ $\geqslant 0 . 5 1$ 的 节点，边缘节点为 $C c ( \nu _ { n } ) < 0 . 5 1$ 的 $\scriptscriptstyle \mathrm { ~ o ~ }$ 节点。

阶段一(1997-2008)：经统计词频 $\geqslant 5$ 关键词有54 个，其中2个核心节点分别是推荐系统和社会网络，中心性是0.70和0.63，处于中间层的有协同过滤、个性化和信誉，分别是0.58、0.54和0.52，有49个边缘节点占 $9 0 . 7 4 \%$ ，边缘节点占绝对多数。进一步研究分析发现，文本挖掘、本体论、文本分类等体现文本特性的节点都保持较高的度，且与其他节点连接较为密切，领域类节点电子商务、社会化书签、自然语言处理、知识管理等虽然为边缘节点但有较高的度。总结此阶段社会化推荐研究关系网络涉及领域较为广泛，研究内容呈现出多样性、分散性和多领域性等特点。

![](images/1a196d7baeb07085a34c0e1d2b43cbe9653b4aad128a656361f8686e5fb6681f.jpg)  
图3关键词中心性层次分布网络(阶段一)

![](images/c7f35393e42710ddd7bed4ecc5d4ab04c336c357ca5a07bb2600347314804c16.jpg)  
图4关键词中心性层次分布网络(阶段二)

![](images/51171d1e98c1a3fc09eb44f7b4fbc65fb64a689fb065fac535abe18edbbd48ea.jpg)  
图5关键词中心性层次分布网络(阶段三)

阶段二(2009-2013)：此阶段词频词频 $\geqslant 5$ 的关键词有60个，其中核心节点保持不变依旧是推荐系统和社会网络，中心性为0.79和0.73。此阶段中心节点28个，边缘节点30个，占总体的 $4 6 . 6 7 \%$ 和 $50 . 0 0 \%$ 。中心节点数较上一阶段明显上升。用户属性节点(如用户建模、个性化、个性化推荐等)与社会网络属性节点(如社会网络分析、社会媒介、社会标签、社会商务等)都具有较高的度，边缘节点如文档过滤、信息传播、普适计算等处于隔离位置(中心性为0)，新兴领域节点云计算、决策支持系统、Web2.0等虽然处于边缘节点但和其他节点连接较为密切，具有一定的研究热度。此阶段技术算法类节点如协同过滤、主题模型、聚类、矩阵因子分解等，在中心层占比较大，与其他节点联系较为紧密。

阶段三(2014-2016):此阶段词频词频 $\geqslant 5$ 的关键词有47个，其中核心节点是推荐系统、社会网络、协同过滤、基于位置网络和算法，中心性分别为0.90、0.75、0.73、0.65、0.65，推荐系统处于绝对核心位置。中心节点为35个，占总体的 $7 4 . 4 7 \%$ ，达到三个阶段最高比例；边缘层仅7个，占总体的 $14 . 8 9 \%$ 。较前两个阶段边缘节点数不断下降，核心节点和中间节点数不断上升。体现社会属性和物理位置的节点具有较高的关注度，如社会影响、信誉、链路预测、随机游走等，Facebook、Twitter、微博等应用类节点也具有较高的度。此阶段推荐应用类与其他节点联系较为紧密，也有一些新的研究点被学者们关注，如基于位置的推荐、位置社会网络。

# 4.3基于网络特征的三阶段比较

通过公式(3)公式(5)计算出三个阶段关键词网络的网络密度、集聚系数和网络平均度，结果如表4所示。三个阶段网络密度不断增加说明三个阶段关键词连接紧密程度不断上升，阶段二集聚系数为0.4141,体现出此阶段关键词节点联系程度较高；而阶段三为0.3865，说明此阶段联系程度较低；阶段一的网络平均度最低18.1429，体现出此阶段研究较为分散，而阶段二相比其他两个阶段研究内容较为集中。

表4三个阶段关键词网络结构特性指标统计  

<html><body><table><tr><td>网络特性指标</td><td>阶段一</td><td>阶段二</td><td>阶段三</td></tr><tr><td>网络密度</td><td>0.162</td><td>0.2122</td><td>0.2476</td></tr><tr><td>集聚系数</td><td>0.4039</td><td>0.4141</td><td>0.3865</td></tr><tr><td>网络平均度</td><td>18.1429</td><td>25.4667</td><td>23.2766</td></tr></table></body></html>

通过对比三个阶段的中心性、网络结构和网络特性，主要得出以下结论：

(1）三个阶段的中心性整体趋于稳定状态，其中  
体现社会属性和推荐应用的关键词越来越多，体现领  
域特性的关键词逐渐变少;(2）三个阶段关键词间链路网络紧密度不断提高;(3）随着阶段变化，中间层的节点数量逐步增加,  
边缘层节点数量相对减少，表明研究的关注点逐渐  
集中;(4)传统算法和主要研究领域一直保持较高的关  
注度，如协同过滤、个性化、社会网络分析、实验法、

数据挖掘、算法、社会媒体等;

(5）各阶段研究特性明显，与社交网络应用相关的研究不断增加，各个阶段都会出现新的研究热点，如张量分解、大众分类法等。

# 5结语

社会化推荐发展至今依旧是一个较新的研究领域，随着理论研究的不断深人，越来越多的复杂数学模型被引人到社会化推荐中，强调信息社会化属性的应用模型不断演化扩展，研究内容日趋丰富，系统可信性和安全隐私重视度不断提升，评价指标不断完善，但异构数据处理、跨平台用户画像构建、大数据处理等一些还处于探索阶段的问题，仍需进一步研究解决。

本文首先从学术研究角度归纳总结社会推荐领域论文的前沿方法和科研成果，通过挖掘分析WoS数据库中的2899 篇科学文献，深入探究比较了此领域的阶段研究特性和演化发展过程。结果表明全球发文量呈现类指数级上升趋势，我国这方面的研究虽然起步较晚但发展较快。各领域交叉学科联系紧密，模型构建多元化特性明显，研究内容经历多领域融合、算法优化、发展成熟等阶段，研究趋势表现为稳定集聚的状态。在未来几年随着云计算、人工智能和深度学习的发展深入，社会化推荐将会面临更多的机遇和挑战。

# 参考文献：

[1]赵宇翔，范哲，朱庆华．用户生成内容(UGC)概念解析及 研究进展[J]．中国图书馆学报，2012，36(5)：68-81.(Zhao Yuxiang，Fan Zhe,Zhu Qinghua.Conceptualization and Research Progress on User-Generated Content[J].Journal of Library Science in China,2012,36(5): 68-81.)   
[2] Resnick P， VarianH R. Recommender Systems[J]. Communications of the ACM,1997,40(3): 56-58.   
[3] Toffler A.Future Shock[M].New York:Amereon Ltd.,1970.   
[4] Lü L Y,Medo M,Yeung C H,et al．Recommender Systems[J].Physics Reports,2012,519(1):1-49.   
[5] 田莹颖．基于社会化标签系统的个性化信息推荐探讨[J]. 图书情报工作，2010，54(1):50-53.(Tian Yingying.On Personalized Information Recommendation Based on Social Tagging System[J].Library and Information Service,2010, 54(1): 50-53.)   
[6]Jäschke R, Marinho L, Hotho A,et al. Tag Recommendations in Social Bookmarking Systems[J].AI Communications, 2008,21(4): 231-247.   
[7]Rawashdeh M,Alhamid MF,Kim H N,et al.Graph-based Personalized Recommendation in Social Tagging Systems[C] //ProceedingsofIEEEInternationalConferenceon Multimedia and Expo Workshops (ICMEW),Chengdu, China. USA: IEEE,2014: 1-6.   
[8]Wu B X, Xiao J, Chen JM.Friend Recommendation by User Similarity Graph Based on Interest in Social Tagging Systems [C]//Proceedings of International Conference on Intelligent Computing.2015: 375-386.   
[9]Wu H, Yue K, Pei Y, et al. Collaborative Topic Regression with Social Trust Ensemble for Recommendation in Social Media Systems[J]. Knowledge-Based Systems,2016,97(C): 111-122.   
[10] Shi C,Liu J, Zhuang F,et al. Integrating Heterogeneous Information via Flexible Regularization Framework for Recommendation[J].Knowledge & Information Systems, 2015,49(3): 835-859.   
[11] Zhang Z, Liu Y, Xu G, et al. Recommendation Using DMF-based Fine Tuning Method[J]. Journal of Intelligent Information Systems,2016,47(2): 233-246.   
[12] Wang Z,Sun L,Zhu W,et al. Joint Social and Content Recommendation for User-generated Videos in Online Social Network[J]. IEEE Transactions on Multimedia,2013,15(3): 698-709.   
[13]Quijano-Sanchez L,Recio-Garcia JA,Diaz-Agudo B,et al. Social Factors in Group Recommender Systems[J].ACM Transactions on Intelligent Systems & Technology，2013, 4(1): Article No. 8.   
[14] Hotho A,Jäschke R,Schmitz C,et al. Information Retrieval in Folksonomies: Search and Ranking[C]//Proceedings of the 3rd European Conference on the Semantic Web: Research and Applications.2006: 411-426.   
[15] Rendle S,Marinho L B,Nanopoulos A,et al.Learning Optimal Ranking with Tensor Factorization for Tag Recommendation[C]//Proceedings of the 15th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining,Paris,France.New York: ACM,2009: 727-736.   
[16] Song Y, Zhuang Z,Li H,et al. Real-time Automatic Tag Recommendation[C]/Proceedingsofthe31stAnnual International ACM SIGIR Conference on Research& Development in Information Retrieval, Singapore.New York: ACM,2008: 515-522.   
[17] Abbasi R,Grzegorzek M, Staab S.Using Colors as Tags in Folksonomies to Improve Image Classification [EB/OL]. [2017-01-15]. https://www.researchgate.net/publication/2288 88951.   
[18] Eck D,Lamere P,Green S,et al.Automatic Generation of Social Tags for Music Recommendation[J].Advances in Neural Information Processing Systems,2007,20: 385-392.   
[19] Golbeck J. Generating Predictive Movie Recommendations from Trust in Social Networks[C]//Proceedings of the International Conference on Trust Management,Pisa,Italy. Berlin Heidelberg: Springer, 2006: 93-104.   
[20]孟祥武，刘树栋，张玉洁，等．社会化推荐系统研究[J]．软 件学报，2015，26(6):1356-1372.(Meng Xiangwu，Liu Shudong， Zhang Yujie， etal． Research on Social Recommender Systems[J].Journal of Software,2015,26(6): 1356-1372.)   
[21] Sun Z B, Han L X,Huang W L.Recommender Systems Based on Social Networks[J]. Journal of Systems and Software, 2015, 99(C): 109-119.   
[22]Baik J,Lee K,Lee S,et al. Predicting Personality Traits Related to Consumer Behavior Using SNS Analysis[J].New Review of Hypermedia and Multimedia,2016,22(3): 189-206.   
[23]唐果媛，张薇．国内外共词分析法研究的发展与分析[J]. 图书情报工作，2014，58(22):138-145.(Tang Guoyuan, Zhang Wei.Development and Analysis of Co-word Analysis Method at Home and Abroad[J]. Library and Information Service,2014,58(22): 138-145.)   
[24] 蒋颖．人文社会科学领域文献计量学研究[M].北京：社会 科学文献出版社,2013.(Jiang Ying.Biblometrics in Social Science and Humanities[M]. Beijing:Social Sciences Academic Press,2013.)   
[25] Scott J. Social Network Analysis:A Handbook[M].SAGE Publications,1991.   
[26] He Q. Knowledge Discovery Through Co-word Analysis[J]. Library Trends,1999,48(1): 133-159.   
[27]Dehdarirad T, Villarroya A,Barrios M.Research Trends in Gender Differences in Higher Education and Science:A Co-word Analysis[J]. Scientometrics,2014,101(1): 273-290.   
[28] Bonchi F,Castillo C,Gionis A,et al. Social Network Analysis and Mining for Business Applications[J].ACM Transactions on Intelligent Systems & Technology,2011,2(3): 1-37.   
[29] Social Network Analysis:A Brief Introduction [EB/OL]. [2017-01-05]. htp: //orgnet.Com/sna.html.   
[30] Siersdorfer S, Sizov S.Social Recommender Systems for Web 2.0Folksonomies[C]//Proceedingsofthe 20th ACM Conference on Hypertext and Hypermedia.New York:ACM, 2009: 261-270.   
[31] Guy I，Carmel D.Social RecommenderSystems[J]. Intelligent Systems Reference Library,2015,32(1): 3-42.   
[32] Arazy O， KumarN, Shapira B. Improving Social Recommender Systems[J].IT Professional，2009，11(4): 38-44.   
[33]Kazienko P,Musial K,Kajdanowicz T. Multidimensional Social Network in the Social Recommender System[J]. IEEE Transactions on Systems，Man & Cybernetics，Part A: Systems & Humans,2011,41(4): 746-759.   
[34] Ma H, Zhou D,Liu C,et al. Recommender Systems with SocialRegularization[C]//Proceedingsofthe4th International Conference on Web Search and Web Data Mining,Hong Kong,China.ACM,2011: 287-296.   
[35] Tang J, Hu X, Liu H.Social Recommendation: A Review[J]. Social Network Analysis and Mining,2013,3(4):1113-1133.   
[36]King I,Lyu M R，Ma H. Introduction to Social Recommendation[C]//Proceedings of the 19th International Conference on World Wide Web.New York:ACM,2010: 1355-1356.   
[37] Ma H, King I,Lyu M.Learning to Recommend with Social Trust Ensemble[C]//Proceedings of the 32nd International ACM SIGIR Conference on Research and Development in Information Retrievel. New York:ACM,2009:203-210.   
[38]Jamali M,Ester M.A Matix Factorization Technique with TrustPropagationsforRecommendationinSocial Networks[C]//Proceedings of the 4th ACM Conference on Recommender Systems.New York: ACM,2010:135-142.   
[39]Jamali M,Ester M.TrustWalker:A Random Walk Model for Combining Trust-based and Item-based Recommendation [C]/Proceedings of the 15th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York: ACM,2009: 397-406.   
[40] Carmagnola F，Vernero F,Grillo P. SoNARS:A Social Networks-basedAlgorithm forSocial Recommender Systems[C]//Proceedings of the International Conference on User Modeling,Adaptation,and Personalization. New York: Springer,2009.   
[41] Zhang R, Sun B,Kang W,et al. Gloss: A Social Networksbased Recommender System[C]/Proceedings of the 5th International Conference on Pervasive Computing and Applications (ICPCA).IEEE,2010: 122-127.   
[42]Viennet E. Collaborative Filtering in Social Networks: A Community-based Approach[C]//Proceedings of the 2013 International Conference on Computing，Management and Telecommunications.IEEE,2013:128-133.   
[43]Heymann P,Koutrika G,Garcia-Molina H.Can Social Bookmarking iImprove Web Search?[C]//Proceedings of the International Conference on Web Search and Web Data Mining. New York: ACM,2008:195-206.   
[44] Hannon J,Bennett M, Smyth B.Recommending Twitter Users toFollow Using Contentand Collaborative Filtering Approaches [C]//Proceedings of the 4th ACM Conference on Recommender Systems. New York: ACM,2011 .   
[45] Peleja F,Dias P,Martins F,et al.A Recommender System for the TV on the Web: Integrating Unrated Reviews and Movie Ratings[J]. Multimedia Systems,2013,19(3): 543-558.   
[46] Masthoff J,Gatt A.In Pursuit of Satisfaction and the Prevention of Embarrassment: Affective State in Group Recommender Systems[J]. User Modeling and User-Adapted Interaction,2006,16(3): 281-319.   
[47] Godoy D,Amandi A. User Profiling for Web Page Filtering [J].IEEE Internet Computing,2005,9(4): 56-64.   
[48] McNally K，O'Mahony M P, Smyth B.Personalized Recommender System Based on Social Relations[C]// Proceedings of the 24th Iranian Conference on Electrical Engineering (ICEE).IEEE,2016: 218-223.   
[49] Wei J,He J, Chen K,et al.Collaborative Filtering and Deep Learning Based Recommendation System for Cold Start Items[J].Expert Systems with Applications,2016,69(1): 29-39.   
[50] Wei J,He J, Chen K,et al. Collaborative Filtering and Deep Learning Based Hybrid Recommendation for Cold Start Problem[C]//Proceedings of the 14th IEEE International Conference on Dependable, Autonomic and Secure Computing. IEEE,2016: 874-877.   
[51]Tomar A,Godin F,Vandersmissen B,et al.Towards Twitter HashtagRecommendationUsingDistributedWord Representations and a Deep Feed Forward Neural Network [C]//Proceedings of the 3rd International Conference on Advances in Computing, Communications and Informatics (ICACCI).IEEE,2014: 362-368.   
[52] Nguyen T T,Lauw H W. Representation Learning for HomophilicPreferences[C]//ProceedingsoftheACM Conference on Recommender Systems.New York:ACM, 2016: 317-324.   
[53]Hidasi B,Quadrana M,Karatzoglou A,et al．Parallel Recurrent Neural Network Architectures for Feature-rich Session-based Recommendations[C]//Proceedings of ACM Conference on Recommender Systems. New York: ACM,   
2016: 241-248. [54] Kautz H,Selman B,Mehul S.Combining Social Networks and Collaborative Filtering[J]. Communications of the ACM,   
1997,40(3): 63-65. [55]李贺，袁翠敏，李亚峰．基于文献计量的大数据研究综述 [J]．情报科学,2014,32(6):148-155.(Li He,Yuan Cuimin, Li Yafeng.A Review of Big Data Research Based on Bibliometrics[J]. Information Science,2014,32(6):148-155.) [56] Callon M,Law J,Rip A. Mapping the Dynamics of Science and Technology [M].London: The Macmillan Press,1986:   
89-106. [57]张勤，马费成．国外知识管理研究范式—以共词分析为 方法[J]．管理科学学报,2007,12(6):65-75.(Zhang Qin,Ma Feicheng.On Paradigm of Research Knowledge Management: A Bibliometric Analysis[J]. Journal of Management Sciences in China,2007,12(6): 65-75.) [58]钟镇．知识图谱分析方法的可靠性检验研究——以共词分 析为例[J]．科学学研究，2015，33(5):647-653．(Zhong Zhen.The Reliability Testing of Knowledge Mapping: Case Study on Co-word Analysis[J]. Studies in Science of Science,   
2015, 33(5): 647-653.) [59]Wang Z,Zhao H,Wang Y. Social Networks in Marketing Research 2001\~2014:A Co-word Analysis[J]. Scientmetrics,   
2015,105(1): 65-82. [60] Ronda-Pupo G A,Guerras-Martin L A.Dynamics of the Evolution of the Strategy Concept 1962-2008:A Co-word Analysis[J]. Strategic Management Journal,2012,33(2):   
162-188. [61]Laydesdorff L.On the Normalization and Visualization of Author Co-citation Data: Salton's Cosine versus the Jaccard Index[J].Journal of the American Society for Information Science and Technology,2008,59(1): 77-85. [62]Worth D.Introduction to Modern Information Retrieval,3rd Edition[J].Australian Academic& Research Libraries,2013,

41(4):305-306.

[63]王宗水，赵红，刘宇，等．社会网络研究范式的演化、发展 与应用—基于1998-2014 年中国社会科学引文数据分析 [J]．情报学报，2015,34(12):1235-1245.(Wang Zongshui, Zhao Hong，Liu Yu，et al.Evolution，Development and Application of Social Network Paradigm: Evidence from CSSCI Database of China[J].Journal of the China Society for Scientific and Technical Information, 2015, 34(12): 1235-1245.)   
[64]司守奎，孙玺菁．复杂网络算法与应用[M].北京：国防工 业出版社,2016.(Si Shoukui, Sun Xijing.Complex Network Algorithms and Applications[M].Beijing:National Defense Industy Press,2016.)   
[65]De Nooy W.Exploratory Social Network Analysis with Pajek: Attributes and Relations [A]//Exploratory Social Network Analysis with Pajek[M].Oxford City:Cambridge University Press,2011:605-608.

# 作者贡献声明：

王宗水：提出研究思路及命题，文字校对;  
李飞：设计研究方案，进行实验，资料收集，撰写论文;  
张健，王宗水：论文最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:leefly $0 7 2 \textcircled { a } 1 2 6 . \textcircled { < } \mathrm { m }$ 。  
[1]李飞，张健，王宗水.支撑数据.xlsx.期刊年份分布数据，出  
版物统计数据，三个阶段词频统计结果、共现网络及节点中心性  
分布.收稿日期:2017-03-22收修改稿日期:2017-05-14

# Review of Social Recommendation with Bibliometrics and Social Network Analysis

LiFeiZhang JianWang Zongshui (School of Economics&Management,Beijing Information Science&Technology University,Beijing 100192, China) (Beijing Key Lab of Green Development Decision Based on Big Data, Beijing 100192, China)

Abstract:[Objective] Thispaper summarizes the content characteristicsand network evolution of social recommendation research basedon theofbibliometrics and social network analysis.[Methods]First,we colected the dataof social recommendation research from the Web of Science database.Then we analyzed the data with manual interpretation,keywordsco-occurrence analysis,bbliometrics,social networkanalysisanddata visualization.[Results] A total of 370l articles on social recommendation were retrieved,which have been increasing recently.Based on the threshold of papers published each year,we divided the development of social recommendation research into three distinctstages.[Limitations]We onlyused keywords to explore the characteristics oftherelevant documentcontents, which could be improved with in-depth text mining.There is lack ofuniform criterion to clasify the evolution stages of the related research.Our study only shows the changing of contents and development trends.[Conclusions]The international impacts of Chinese scholars have been rising in social recommendation studies,which highly focus on the topics of social media and collaborative filtering.

Keywords: Social Recommendation Research ProgressDevelopment Trend Social Network Analysis Bibliometrics

# OCLCResearch和LIBER合作研究科研管理系统中持久标识符的采用情况

OCLC Research 和欧洲研究图书馆协会(LIBER)于近日推出一个合作项目，以探索欧洲科研信息管理(ResearchInformation Management,RIM)基础设施中持久性标识符(Persistent IDentifiers,PID)的采用情况。该项目将为欧洲科研机构的科研信息管理的实施工作提供参考，为大学和研究图书馆等领导者提供一些有关各种规模的科研管理的新兴实践和所面临挑战的有用见解。

OCLC 首席战略师兼副总裁 Lorcan Dempsey 表示:“我们很高兴与 LIBER 合作。OCLC Research 对图书馆如何在校园和全国范围内推广和参与更广泛的研究支持计划一直很感兴趣，我们对研究数据管理和科研信息管理方面的问题研究越来越多，与LIBER的合作使我们能够扩展这些工作，并与欧洲著名图书馆合作研究这些重要问题。”

LIBER主席兼芬兰国家图书馆国家网络服务部主任 Kristina Hormia-Poutanen指出:“OCLC和LIBER此次合作研究将重点关注持久性标识符，这在研究数据管理中是起核心作用的。OCLC和LIBER都支持图书馆开发数字的、开放式的服务，这一合作为两个组织都提升了附加值。”

欧洲很多研究机构都在从事科研信息管理实践，以整理、保存和利用其机构科研过程相关的信息。随着技术、标准和网络信息的发展为互操作性和可发现性提供了新的机会，这些努力正在迅速扩大到国家层面甚至跨国层面。

在这项特别的合作研究中，将重点考察在三个欧洲国家(芬兰、德国和荷兰)的科研信息管理实践情况，密切关注持久性标识符的采用和整合情况及其在消除歧义和互操作性方面的作用。通过与高校、国家图书馆和信息通信技术组织中的实践者和利益相关者的一系列半结构化访谈，将进行国家科研信息管理基础设施案例研究，以及科研信息管理实践和持久性标识符整合的具体实例研究。

(编译自:http://www.oclc.org/en/news/releases/2017/201716dublin.html)

(本刊讯)