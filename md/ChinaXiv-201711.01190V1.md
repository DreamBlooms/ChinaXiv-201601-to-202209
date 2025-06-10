# 三种数据挖掘算法在电子病历知识发现中的比较

牟冬梅」　任　珂²

(吉林大学公共卫生学院长春 130021)2(武汉大学信息管理学院 武汉 430072)

摘要：【目的】从异构的电子病历数据中发现疾病危险因素，为数据挖掘与知识发现提供借鉴。【方法】选取集各种结构为一身的临床电子病历数据，利用决策树、逻辑回归和神经网络三种数据挖掘算法分别建立疾病危险因素预测模型，对三种预测模型进行比较分析和统计学评价。【结果】决策树预测模型在查准率、召回率上高于逻辑回归和神经网络，在总体性能上决策树最优，但三者差别不大。【局限】未对电子病历属性进行优化选择。

【结论】决策树在危险因素的发现与疾病的预测方面优于逻辑回归和神经网络。研究中建立基于数据挖掘算法的异构数据源知识发现框架，为今后领域知识发现和知识库构建以及数据挖掘算法的选择提供一定借鉴和参考。

关键词：知识发现电子病历 数据挖掘算法 预测模型

分类号：G202

# 1引言

随着大数据(BigData)概念的提出及大数据时代的到来，情报学研究范畴已经明显呈现出大数据的典型特征[1]。大数据具有的数据量大、处理速度快、数据类型繁多和价值密度低这“4V"特征，为情报学提出新挑战，尤其大数据种类繁多、结构多样、质量参差不齐，情报学领域信息加工需要向数据清洗、规范集成和整合不断拓展。美国管理学家罗素·艾可构建了DIKW(Data-Information-Knowledge-Wisdom) 体 系 [2-3],Zeleny区分了DIKW体系中的各个元素[4],CIO时代网对其内容与价值进行分析[5，王曰芬认为文献计量法和内容分析法是实现DIKW转换的关键算法[6]。DIKW体系为情报学提供了巨大的发展空间，同时也指明情报学研究的目的和内涵，情报学需要在数据清洗的基础上，通过自然语言处理、概念映射等情报学方法进行数据标准化、规范化，再利用内容分析、科学计量分析、社会网络分析等多样化数据分析算法，通过数据挖掘提取内在的隐性知识，实现知识发现，为用户提供嵌入式的个性化精准化服务。

目前医疗数据是最为复杂的数据，最能体现大数据种类多、来源多、用途多的特征，本研究选取临床电子病历(ElectronicMedicalRecord,EMR)数据，在情报学知识发现框架指导下，利用决策树、逻辑回归和神经网络等数据挖掘算法分别建立疾病的危险因素预测模型，并对三种预测模型进行评价。本研究规范情报学方法在医学领域知识发现的流程，探索从复杂的数据中找到知识之间有效关联及知识发现的最佳算法，为今后数据处理和知识发现提供一定借鉴和参考;另一方面，可以为临床医生的诊断提供数据支持，为疾病防控人员提供可视化依据，对妊高症"预防-诊断-治疗-预后"全过程提供科研数据支持；数据挖掘方法应用于疾病的危险因素研究，可以加强对医疗大数据信息的开发与利用。

# 2基于数据挖掘算法的异构数据源知识发现框架

基于数据挖掘算法的异构数据源知识发现遵循科学领域逻辑框架内的知识发现研究[，在知识处理流程中关注数据规范，对不同来源的数据在异质领域本体融合基础上实现数据语义规范化，进而深入探讨主题模型、关联数据分析及机器学习等方法，是实现高效领域知识发现的一条必经之路，其流程主要有4步，如图1所示：

![](images/230b9f78078688cfd34ec6a4b0fedef0847f6035dd41315292486dd3452f874c.jpg)  
图1基于数据挖掘算法的异构数据源知识发现框架

(1）利用数据库技术完成数据采集。涉及多个数据来源，如医生工作站的诊断报告、护士工作站的患者社会特征数据、影像室所保存的图像数据、实验室所保存的实验室检查结构化数据和手术室的用药及检测数据报告等，不同来源的数据呈现多种结构，将不同结构的数据进行结构化，存放在数据库中。

(2）数据清洗。完成数据去标识化，数据类型的规范化，缺省值处理，自然语言处理和语义标注。其关键技术为自然语言处理和语义标注。

(3）预测模型构建。运用机器学习中的监督学习方法[10]，进行疾病危险因素的预测模型构建。从大量多维度的数据中挖掘出有价值的情报，分析数据背后的知识。数据挖掘技术包括许多算法，按照训练的数据有无标签，分为监督学习算法、无监督学习算法和特殊算法，本研究应用开源软件 $\mathbb { R } ^ { [ 1 0 ] }$ 建立数据挖掘模型。在R中通过运用决策树、逻辑回归和神经网络三种数据挖掘算法对相关数据分别进行处理分析，包括去掉缺省值、发现异常点、对数据进行唯一化处理和对相关的类目进行关联分析等，最终建立合理有效的数据挖掘模型，利用R软件的相关函数进行模型可视化展示，并通过模型对数据进行预测，从而得到有效的处理结果。

(4）模型评价。对预测模型利用统计学方法进行评价，评价指标包括查准率、召回率、正确率和F值。

# 3疾病危险因素预测模型构建

# 3.1 数据来源

研究数据来自长春市某三级甲等医院的电子病历，包含2014年1月1日至2015年4月30日就诊于该所医院的31443名孕妇的就诊信息，由信息中心人员进行数据抽取建立Excel数据库(见图2)。数据包括:病人的基本信息(科室、年龄、登记号、性别、民族、职业、文化程度、婚姻状况、收入)；生活和工作习惯信息(吸烟情况、饮酒情况、工作压力及精神压力)；病史信息(既往史、家族史)；常规体检数据(身高、体重)和实验室检查数据(收缩压、舒张压、总胆固醇、甘油三酯、低密度胆固醇、高密度胆固醇、空腹血糖、血红蛋白)；诊断结果。每名患者都严格按照医学诊断标准进行诊断，并且按照电子病历的格式，在既往史、家族史和诊断结果中用自然语言形式进行详细描述。

<html><body><table><tr><td></td><td>年龄</td><td>登记号</td><td>性别</td><td>民族</td><td>职业</td><td>文化程度</td><td>婚姻</td><td>吸烟</td><td>饮酒</td><td>既往史</td><td>身高cm</td><td>体重Kg</td></tr><tr><td></td><td>35</td><td>295405</td><td>女</td><td>汉族</td><td>二</td><td>大学或以上已婚</td><td></td><td>无</td><td>无</td><td>否认肝炎、结杉</td><td>160</td><td>80</td></tr><tr><td></td><td>29</td><td>245642</td><td>女</td><td>汉族</td><td>无</td><td>大学或以上已婚</td><td></td><td>无</td><td>无</td><td>否认其他重大疫</td><td>156</td><td>78</td></tr><tr><td></td><td>29</td><td>245642</td><td>女</td><td>汉族</td><td>无</td><td></td><td>已婚</td><td>无</td><td>无</td><td>患者否认重大疾</td><td>156</td><td>77</td></tr><tr><td></td><td>32</td><td>157760</td><td>女</td><td>汉族</td><td>无</td><td>高中/中专</td><td>已婚</td><td>无</td><td>无</td><td>既往健康，无高</td><td>167</td><td>82</td></tr><tr><td></td><td>31</td><td>186432</td><td>女</td><td>汉族</td><td>职员</td><td>高中/中专</td><td>已婚</td><td>无</td><td>无</td><td>患者否认重大疾</td><td>153</td><td>59.5</td></tr><tr><td></td><td>34</td><td>122794</td><td>女</td><td>汉族</td><td>无</td><td>高中/中专</td><td>已婚</td><td>无</td><td>无</td><td>既往健康，无高</td><td>151</td><td>86</td></tr><tr><td></td><td>28</td><td>94276</td><td>女</td><td>汉族</td><td>技术干部</td><td></td><td>已婚</td><td>无</td><td>无</td><td>患者否认其他重</td><td>160</td><td>68</td></tr><tr><td></td><td>29</td><td>36740</td><td>女</td><td>汉族</td><td></td><td>大学或以上已婚</td><td></td><td>无</td><td>无</td><td>健康，否认结核</td><td>155</td><td>74</td></tr><tr><td></td><td>34</td><td>44392</td><td>女</td><td>汉族</td><td>无业</td><td></td><td>已婚</td><td>无</td><td>无</td><td>患者因“异位好</td><td>160</td><td>68</td></tr><tr><td></td><td>33</td><td>114062</td><td>女</td><td>汉族</td><td>无</td><td>大学或以上已婚</td><td></td><td>无</td><td>无</td><td>否认重大疾病史</td><td>155</td><td>70</td></tr><tr><td></td><td>33</td><td>146330</td><td>女</td><td>汉族</td><td>职员</td><td>大学或以上已婚</td><td></td><td>无</td><td>无</td><td>否认肝炎、结核</td><td>168</td><td>73</td></tr><tr><td></td><td>43</td><td>293197</td><td>女</td><td>汉族</td><td>无</td><td></td><td>离婚</td><td>无</td><td>无</td><td>良好</td><td>160</td><td>52</td></tr><tr><td></td><td>32</td><td>1019</td><td>女</td><td>汉族</td><td></td><td>高中/中专</td><td>已婚</td><td>无</td><td>无</td><td>否认肝炎结核病</td><td>160</td><td>81</td></tr><tr><td></td><td>30</td><td>42243</td><td>女</td><td>汉族</td><td>无</td><td></td><td>已婚</td><td>无</td><td>无</td><td>既往健康，无高</td><td>158</td><td>60</td></tr><tr><td></td><td>32</td><td>106048</td><td>女</td><td>汉族</td><td>职员</td><td>大学或以上已婚</td><td></td><td>无</td><td>无</td><td>健康。否认肝炎</td><td>168</td><td>79</td></tr><tr><td></td><td>28</td><td>225887</td><td>女</td><td>汉族</td><td>职员</td><td>高中/中专</td><td>已婚</td><td>无</td><td>无</td><td>患者否认其他重</td><td>158</td><td>72</td></tr><tr><td></td><td>28</td><td>120532</td><td>女</td><td>汉族</td><td>无</td><td>初中</td><td>已婚</td><td>无</td><td>无</td><td>患者否认其他重</td><td>160</td><td>70</td></tr><tr><td></td><td>28</td><td>4929</td><td>女</td><td>汉族</td><td>无业</td><td>高中/中专已婚</td><td></td><td>无</td><td>无</td><td>患者否认其他重</td><td>158</td><td>62</td></tr></table></body></html>

# 3.2 数据清洗

(1）提取有效属性列

由于数据中有些属性对于预测模型无影响或影响极小，加入分析可能会形成噪音(如入院日期、登记号等)，在提取有效属性列阶段，将噪声属性列去掉，保留有意义的属性列。研究中主要采用人工抽取的方式进行属性列提取，加大提取的准确性和有效性。

# (2)自然语言处理

对电子病历中既往史、家族史和入院诊断、出院诊断等自然语言描述的非结构化信息进行处理。首先进行二分类判别，对既往史、家族史以标点符号为分隔符进行数据提取，对分离出的疾病名称数据以及出入院诊断中的疾病名称进行概念映射，映射到统一医学语言系统(Unified Medical Language System,UMLS)下的国际疾病分类法ICD10中，方便之后数据挖掘模型对数据的有效识别。

(3）文本数据数值化

在数据挖掘模型中，神经网络只能处理数值型变量，因此为了便于数据挖掘模型的建立，在本阶段将定性数据改为数值型变量。例如，在“婚姻状况"属性列中，设"离婚"为1,“已婚"为2,“未婚"为3,“丧偶"为4,“其他"为5等。

# (4）缺省值处理

由于电子病历记录不规范，存在病人记录不完整的现象，这些病人记录会影响最终模型的建立和挖掘但由于这些缺省值并不多，因此使用R软件将含有这些缺省值的数据去掉，以呈现更好的挖掘效果。

通过上述步骤完成基本数据准备，使数据呈现可处理状态，也使数据库中的数据可以更加清晰简明地表述出来，最终得到29901条数据，如图3所示：

<html><body><table><tr><td>年龄</td><td>婚姻</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>吸烟饮酒既往史家族史身高cm体重Kg收缩压mmHg舒张压mmHg总胆固醇甘油三酯低密度胆固醇高密度胆固醇空腹血糖血红蛋白</td><td></td><td></td><td></td><td>编号</td><td>合并结果</td></tr><tr><td>28</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>160</td><td>84</td><td>110</td><td>70</td><td>3.41</td><td>4. 97</td><td>0.88</td><td>0.97</td><td>10.99</td><td>83. 00</td><td>30648</td><td>是</td></tr><tr><td>45</td><td>2</td><td></td><td>1</td><td>2</td><td>2</td><td>1</td><td>160</td><td>65</td><td>110</td><td>70</td><td>6.15</td><td>1. 85</td><td>3.98</td><td>1. 80</td><td>5.06</td><td>119. 00</td><td>14172</td><td></td></tr><tr><td>31</td><td>2</td><td></td><td>2</td><td>2</td><td>1</td><td>2</td><td>171</td><td>101</td><td>110</td><td>70</td><td>6.47</td><td>4. 22</td><td>4. 07</td><td>1. 56</td><td>5. 63</td><td>67.00</td><td>11280</td><td>香</td></tr><tr><td>45</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>158</td><td>56</td><td>120</td><td>80</td><td>3.43</td><td>1. 14</td><td>1. 79</td><td>1. 07</td><td>4.46</td><td>79.00</td><td>30615</td><td>香</td></tr><tr><td>28</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>168</td><td>72</td><td>90</td><td>60</td><td>5.68</td><td>2. 65</td><td>3.55</td><td>1. 60</td><td>4. 87</td><td>133.00</td><td>18358</td><td>香</td></tr><tr><td>34</td><td>2</td><td></td><td>2</td><td>2</td><td>1</td><td>2</td><td>160</td><td>61</td><td>90</td><td>60</td><td>8.35</td><td>2.02</td><td>5.94</td><td>2. 01</td><td>4.00</td><td>109.00</td><td>1664</td><td>否</td></tr><tr><td>29</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>168</td><td>65.5</td><td>110</td><td>80</td><td>6.00</td><td>1. 08</td><td>2. 34</td><td>2. 61</td><td>7. 54</td><td>94. 00</td><td>15500</td><td></td></tr><tr><td>29</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>155</td><td>70</td><td>100</td><td>60</td><td>6.88</td><td>3.25</td><td>3.93</td><td>2.30</td><td>3.95</td><td>113.00</td><td>8015</td><td></td></tr><tr><td>28</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>162</td><td>87</td><td>130</td><td>80</td><td>4. 57</td><td>4.45</td><td>1.81</td><td>1. 87</td><td>6.02</td><td>76. 00</td><td>26497</td><td>香</td></tr><tr><td>39</td><td>2</td><td></td><td>2</td><td>2</td><td>1</td><td>1</td><td>155</td><td>55</td><td>120</td><td>70</td><td>5. 66</td><td>0. 69</td><td>3.37</td><td>1. 16</td><td>5.67</td><td>79. 00</td><td>18622</td><td>香</td></tr><tr><td>27</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>152</td><td>61</td><td>110</td><td>70</td><td>6.77</td><td>2. 17</td><td>3.55</td><td>2.20</td><td>4. 57</td><td>85.00</td><td>8862</td><td>否</td></tr><tr><td>25</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>165</td><td>74</td><td>120</td><td>80</td><td>4. 79</td><td>1.40</td><td>2.52</td><td>1. 07</td><td>4. 90</td><td>90.00</td><td>25259</td><td>香</td></tr><tr><td>21</td><td>2</td><td></td><td>1</td><td>2</td><td>2</td><td>2</td><td>155</td><td>55</td><td>110</td><td>70</td><td>6.19</td><td>2. 59</td><td>2. 76</td><td>2. 32</td><td>4.93</td><td>105.00</td><td>13787</td><td>香</td></tr><tr><td>30</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>160</td><td>80</td><td>100</td><td>70</td><td>6.86</td><td>5.30</td><td>2. 77</td><td>3.03</td><td>6.55</td><td>120.00</td><td>8170</td><td>香</td></tr><tr><td>43</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>158</td><td>56</td><td>120</td><td>80</td><td>4.92</td><td>4. 06</td><td>2. 17</td><td>1. 04</td><td>5.31</td><td>87. 00</td><td>24470</td><td>香</td></tr><tr><td>27</td><td>2</td><td></td><td>2</td><td>2</td><td>2</td><td>2</td><td>160</td><td>76</td><td>100</td><td>70</td><td>8.09</td><td>3. 95</td><td>4.03</td><td>1.97</td><td>4. 34</td><td>133.00</td><td>2277</td><td>否</td></tr><tr><td>31</td><td>2</td><td></td><td>2</td><td>2</td><td>1</td><td>2</td><td>155</td><td>61</td><td>110</td><td>70</td><td>4.98</td><td>3.25</td><td>2.48</td><td>1.85</td><td>4. 70</td><td>97.00</td><td>24057</td><td>香</td></tr></table></body></html>

# 3.3 妊娠高血压综合征的危险因素预测模型构建

针对挖掘妊娠高血压综合征(Pregnancy-inducedHypertension，简称妊高症)危险因素来进行上述算法的实证研究。在完成上述数据准备处理阶段的工作后，为了研究的一致性和严谨性，三种数据挖掘算法都应使用相同的训练集和测试集，将数据按照 $7 : 3$ 的比例分为训练集数据和测试集数据，选取 $70 \%$ （即22010条数据)的数据作为训练集，建立数据挖掘模型以及挖掘妊高症危险因素；剩余 $30 \%$ (即9433条数据)的数据作为测试集，用来测试算法性能。随后在R中对训练集和测试集数据的缺省值进行删除，最终结果为：训练集数据20940条，测试集数据8961条。

# (1）决策树模型

决策树作为一种监督学习方法，可以用于分类和预测，在其树型结构中，每个节点和分支都具有一定的含义：决策树通过不断细化的分支(即分类标准),将错综复杂的数据分为若干类型，用叶子节点对其进行表示，因此决策树可以对数据进行直观明确的分类。本研究采用ID3算法构建决策树模型。要构造尽可能小的决策树，关键在于选择合适的产生分支的属性。而ID3算法的核心正是通过采用信息增益的方式来选择能够最好地将样本分类的属性[12]。

设 $\mathrm { E } = \mathrm { D } _ { 1 } \times \mathrm { D } _ { 2 } \times \cdots \times \mathrm { D } _ { \mathrm { n } }$ 是 $\mathbf { \bar { n } }$ 维有穷向量空间，其中 $\mathrm { D _ { j } }$ 是有穷离散符号集,E中的元素 $\mathbf { e } = < \mathbf { v } _ { 1 }$ ， $\mathbf { v } _ { 2 }$ ，,${ \bf v } _ { \mathrm { n } } >$ 为例子,其中 $\mathrm { v _ { j } } \in \mathrm { D _ { j } } , \mathrm { j } { = } 1 , 2 , 3 , \ \cdots , \mathrm { n _ { \circ } }$ 设 ${ \bf s } _ { 1 }$ ， ${ \bf s } _ { 2 }$ ，…, $\mathbf { s } _ { \mathrm { m } }$ 是E的 $\mathbf { m }$ 个例子集。假设向量空间E中的这 $\mathrm { ~ m ~ }$ 个例子集的大小为 $\mathrm { S _ { i } }$ ,ID3 基于以下两个假设[13]:

(1）在向量空间E上的一棵正确决策树对任意例子的分类概率同E中这 $\mathbf { \rho } _ { \mathrm { m } }$ 个例子的概率一致。

(2）一棵决策树能对一个例子做出类别判断所需的熵为:

$$
\mathrm { E n t r o p y } ( \mathrm { s } _ { 1 } , \mathrm { s } _ { 2 } , . . . , \mathrm { s } _ { \mathrm { m } } ) = - \sum _ { \mathrm { i } = 1 } ^ { \mathrm { m } } \mathrm { p } _ { \mathrm { i } } \log _ { 2 } ( \mathrm { p } _ { \mathrm { i } } )
$$

其中， $\mathfrak { p } _ { \mathrm { i } }$ 用 $\mathbf { S _ { i } } / \mathbf { s }$ 来估算。

如果以属性 $\mathrm { \bf A }$ 作为决策树的根. $\mathrm { \bf A }$ 具有 $\mathbf { v }$ 个值，它将E分成 $\mathbf { v }$ 个子集 $\{ \mathrm { E } _ { 1 } , \mathrm { E } _ { 2 } , \cdots , \mathrm { E } _ { \mathrm { v } } \}$ ，假设 $\mathrm { E _ { i } }$ 中含有$\mathrm { S } _ { \mathrm { i } } ( \mathrm { i } { = } 1 , 2 , \cdots , \mathrm { m } )$ ，那么子集 $\mathrm { E _ { i } }$ 所需的期望信息是 $\mathrm { E ( A ) }$ ○

$$
\mathrm { E n t r o p y } ( \mathrm { A } ) = - \sum _ { \mathrm { j = 1 } } ^ { \mathrm { v } } ( \mathbf { s } _ { \mathrm { l j } } + \mathbf { s } _ { \mathrm { 2 j } } + \cdots + \mathbf { s } _ { \mathrm { m j } } ) / { \textrm { s } } \times \mathrm { E n t r o p y } ( \mathbf { s } _ { \mathrm { l j } } , \mathbf { s } _ { \mathrm { 2 j } } , \cdots , \mathbf { s } _ { \mathrm { m j } } )
$$

因此，以属性A为根的信息增益是：

$$
\operatorname { G a i n } ( \mathrm { A } ) = \operatorname { E n t r o p y } ( \mathrm { A } ) ( \mathrm { s } _ { 1 } , \mathrm { s } _ { 2 } , \cdots , \mathrm { s } _ { \mathrm { n } } ) - \operatorname { E n t r o p y } ( \mathrm { A } )
$$

ID3选择使Gain(A)最大的属性 $\mathbf { A } ^ { * }$ 作为根节点，对$\mathbf { A } ^ { * }$ 的不同取值对应的E的v个子集 $\mathrm { E _ { i } }$ 递归调用上述过程生成 $\mathbf { A } ^ { * }$ 的子节点，从而生成一棵树。

使用R软件，利用 rpart 函数包和 rpart.plot 函数包对危险因素进行挖掘。将训练集中有关最终妊高症的诊断结果(即"是"与"否")作为最终的分类结果(即根节点),将患者的体检属性变量作为分类条件进行分析，将影响最终诊断的危险因素及其数据范围用决策树展现出来，并将其可视化。由于决策树分支太多，过于复杂，容易产生过拟合现象，对预测测试集数据丧失意义，因此利用CP(Complexity Parameter)即复杂度参数进行剪枝。CP随决策树复杂度的增加而减小，当增加一个节点引起的分类精确度的变化量小于决策树复杂度变化量的CP倍时，须剪去该节点。一般选择错判率最小值对应的CP值来修树。在CP值等于0.0048时，获得既能够很好拟合训练集数据，又能很好预测测试集数据的决策树，而且对于危险因素来说，在最终得到的决策树中，强调了“收缩压”、“舒张压”、“空腹血糖"和"甘油三酯"这四个属性，根据决策树的路径显示：当收缩压大于 $1 3 8 \mathrm { m m H g }$ ，同时舒张压大于 $9 2 { \mathrm { m m H } } \mathrm { \mathrm { g } }$ 、甘油三酯大于 $1 . 7 \mathrm { m m o l / L }$ 时，是主要危险因素；而当收缩压大于$1 3 8 \ \mathrm { m m H g }$ ，但舒张压小于 $9 2 \mathrm { m m H g }$ 时，若空腹血糖小于 $5 \ \mathrm { m m o l / L }$ 、舒张压大于 $8 6 \mathrm { m m H g }$ 且甘油三酯大于$2 . 6 \mathrm { m m o l / L }$ 时，也是患妊高症的危险因素。

(2）逻辑回归模型对妊高症危险因素挖掘

逻辑回归(Logistic Regression,LR)模型中最常使用梯度下降法来获得代价函数的最小值，通过给予一定的优化条件，使方法得到更好的分类界限[14]。由于逻辑回归模型构造简单、结果方便易懂，因此在疾病防治领域有着广泛的应用，是数据挖掘方法在医学领域应用的一个典型方法。

设P为某事件发生的概率，取值范围为[0,1],1-P为该事件不发生的概率，将 $\mathsf { P } / ( 1 { - } \mathsf { P } )$ 取自然对数$\ln ( \mathrm { P } / ( 1 { - } \mathrm { P } ) )$ ，即对 $\mathrm { ~ \bf ~ P ~ }$ 作logit转换，记为logitP,则logitP的取值范围为 $( - \infty , + \infty ) \sb { \circ }$ 以 $\mathrm { ~ \bf ~ P ~ }$ 为因变量，建立线性回归方程[15]:

$$
\log \mathrm { i t P } = \alpha + \beta _ { \mathrm { l } } \mathrm { x } _ { \mathrm { l } } + \cdots + \beta _ { \mathrm { m } } \mathrm { x } _ { \mathrm { m } }
$$

可得:

$$
\mathrm { P } = { \frac { \exp ( \alpha + \beta _ { 1 } \mathrm { x } _ { 1 } + \cdots + \beta _ { \mathrm { m } } \mathrm { x } _ { \mathrm { m } } ) } { 1 + \exp ( \alpha + \beta _ { 1 } \mathrm { x } _ { 1 } + \cdots + \beta _ { \mathrm { m } } \mathrm { x } _ { \mathrm { m } } ) } }
$$

该模型即为逻辑回归模型，是普通多元线性回归模型的推广，但它的误差项服从二项分布而非正态分布，模型中 $\alpha$ 为常数, $\beta _ { \mathrm { i } } ( \mathrm { i = 1 , ~ } \cdots , \mathrm { m } )$ 为逻辑回归系数。

使用R软件，利用 $\mathrm { { g l m } }$ 函数和MASS函数包对危险因素进行挖掘。由于逻辑回归模型没有参数，因此不需要对参数进行调整，为了得到既能很好拟合训练集，又能很好预测测试集数据的模型，需要选择合适的属性，此属性即为模型挖掘的危险因素。通过对变量进行合理选择，得到合理的逻辑回归模型及其可视化图谱。逻辑回归模型通过8次费舍尔得分迭代，筛选出有意义的属性变量为"年龄”、“体重 $\mathrm { K g ^ { , \dag } }$ 、“收缩压 $\mathrm { m m H g ^ { , } }$ 、“舒张压 $\mathrm { m m H g } ^ { \prime }$ 和“空腹血糖”，通过这5个属性变量，在R中建立针对妊高症诊断的最合理模型，如果将这5个属性以“ $\mathrm { X } _ { 1 } \mathrm { - X } _ { 5 }$ ”分别表示,Y为患者最终是否患病的结果(Y值只能为0或1)，则笔者提出的最终逻辑回归公式可以表示为：

$$
\mathrm { Y } = - 2 5 . 4 5 - 0 . 0 5 \mathrm { X } _ { 1 } + 0 . 0 3 \mathrm { X } _ { 2 } + 0 . 1 7 \mathrm { X } _ { 3 } + 0 . 0 1 \mathrm { X } _ { 4 } - 0 . 2 1 \mathrm { X } _ { 5 }
$$

根据公式(6进行计算，以说明患者是否真正患有妊高症。通过重新建立逻辑回归模型，使之包含“年龄”、“体重Kg”、“收缩压 $\mathrm { { m m H g } ^ { , } }$ 、“舒张压 $\mathrm { \ m m H g ^ { \prime } }$ 和"空腹血糖"等5个属性，不仅建立起基于训练集数据的逻辑回归模型，也筛选出影响妊高症的危险因素。

(3）神经网络模型对妊高症危险因素挖掘

神经网络(NeuralNetwork)是一个包含输入层、隐藏层和输出层的数据挖掘方法，神经网络方法的内在本质是：结果与输入层的特征值无关，是与隐藏层的方法密切相关的，神经网络模型可以快速地学习任意的特征项。数据挖掘软件中通常运用反向传播方法使代价函数最小。神经网络可以运用于分类和回归问题具有极强的容错性和鲁棒性[16]

神经网络中每个神经元都是一个简单的计算装置，其特性由简单的数学函数所描述。神经元i接收其他神经元传递来的输入信息，根据和函数neti进行加权平均，根据传递函数 $\mathrm { f _ { i } }$ 产生输出信息，输出信息又按照网络的拓扑结构传递到下一个神经元。笔者应用McClelland 等于1986 年提出的函数[17]，公式如下:

$$
\mathrm { I _ { i } = \sum _ { j } w _ { i j } \mathrm { x _ { j } + Q _ { i } \quad \mathrm { x _ { i } ^ { \prime } = f _ { i } = \frac { 1 } { 1 + e ^ { - n e t _ { i } } } } } }
$$

其中， $\mathrm { \Delta I _ { i } }$ 为神经元i的输入； $\bf { x } _ { i } ^ { \prime }$ 为神经元i的输出; $\mathbf { W _ { \mathrm { i j } } }$ 为神经元i, $\mathrm { ~ j ~ }$ 之间的连接权； $\mathrm { \Delta Q _ { i } }$ 为神经元i的偏置。

每一条连接弧都被赋予一定的数值表示连接弧的连接强度。正的权值表示影响的增加，负的权值表示影响的减弱。在前向网络中，神经元间前向连接，同层神经元互不连接，信息只能向着一个方向传播。前向网络的连接模式用权值向量W表示。在网络中，权值向量决定着网络如何对环境中的任意输人做出反应。同样，网络也是通过不断调整权值完成整个学习过程。

用神经网络挖掘算法对训练集数据进行处理时，运用R中的nnet函数包和mlbench函数包。通过不断实验，改变隐藏层数目和阈值，不断优化神经网络模型。最后得到一个含有10个隐藏层，阈值为0.01的神经网络模型。

(4）妊高症危险因素挖掘结果

对于诊断妊高症来说，危险因素起着至关重要的作用，在本文的研究数据中，一共包含16个属性，但并不是全部属性都在某种程度上导致了妊高症的发生，研究中通过决策树、逻辑回归和神经网络三种数据挖掘模型，找到真正起作用的危险因素，具体的挖掘结果如表1所示：

表1妊高症主要危险因素挖掘效果对比  

<html><body><table><tr><td>对比项</td><td>决策树</td><td>逻辑回归</td><td>神经网络</td></tr><tr><td>是否可看出挖 掘的危险因素</td><td>是</td><td>是</td><td>否</td></tr><tr><td>挖掘的危险 因素属性</td><td>收缩压、舒张压、年龄、体重、 空腹血糖、甘油收缩压、舒张压、 三酯</td><td>空腹血糖</td><td>无</td></tr><tr><td>表现危险因 素的方式</td><td>决策树路径 (带有具体数值)</td><td>数学公式</td><td>无(黑盒 模型)</td></tr></table></body></html>

从表1可以看出，在挖掘妊高症危险因素方面决策树能提炼出危险因素的属性组合和数值；逻辑回归只能分析危险因素的属性；神经网络则无法获知属性和数值。因此决策树在妊高症危险因素挖掘中直观性最好，且决策树运用最少的属性就可以判断出患者是否得病，说明其代表性也最强。通过这些危险因素的挖掘，可以对临床医生的诊断起到辅助作用，对妊高症疾病的预防和预后起到指导作用。

# 4模型评价

# 4.1 评价指标

大数据分析中，利用上述三种数据挖掘模型对测试集数据进行预测，以四格表为数据基础，运用查准率(Precision)、召回率(Recall)、正确率和F值[18这4个指标评价数据挖掘算法的性能。

各个指标具体的含义为：

$$
\because 1 ^ { \underline { { \star } } } = \frac { 2 \mathrm { P R } } { \mathrm { P } + \mathrm { R } }
$$

在医学领域，TP(True Positive)表示真阳性的病例数，即医生诊断的结果和数据挖掘结果都是妊高症的病例数；TN(True Negative)是真阴性，即机器诊断结果不是妊高症而且医生诊断也不是的病例数;FN(False Negative)是假阴性，即机器诊断结果是妊高症，但是医生的诊断却不是的病例数；FP(FalsePositive)是假阳性，即机器诊断结果不是妊高症，但是医生诊断结果却是妊高症的病例数。P是查准率，R是召回率。

查准率越高，说明算法的敏感性越高；召回率越高，说明算法的特异性越好；正确率越高，说明算法的精确度越好;F值越大，说明算法的总体性能越好[19]。

# 4.2 三种模型预测结果

利用建立好的三种数据挖掘模型和处理好的测试集数据对妊高症患病与否进行预测，利用四格表[20]数据分别计算查准率、召回率、正确率和F值，并对三种模型进行评价，如表2-表4所示：

表2决策树模型预测妊高症数量结果  

<html><body><table><tr><td rowspan="2">患者真实诊断 得病与否</td><td colspan="2">决策树预测患者得病与否</td><td rowspan="2">合计</td></tr><tr><td>香</td><td>是</td></tr><tr><td>香</td><td>8608</td><td>45</td><td>8 653</td></tr><tr><td>是</td><td>137</td><td>171</td><td>308</td></tr><tr><td>合计</td><td>8 745</td><td>216</td><td>8961</td></tr></table></body></html>

表3逻辑回归模型预测妊高症数量结果  

<html><body><table><tr><td rowspan="2">患者真实诊断 得病与否</td><td colspan="2">逻辑回归预测患者得病与否</td><td rowspan="2">合计</td></tr><tr><td>香</td><td>是</td></tr><tr><td>否</td><td>8 611</td><td>42</td><td>8653</td></tr><tr><td>是</td><td>168</td><td>140</td><td>308</td></tr><tr><td>合计</td><td>8779</td><td>182</td><td>8961</td></tr></table></body></html>

表4神经网络模型预测妊高症数量结果  

<html><body><table><tr><td rowspan="2">患者真实诊断 得病与否</td><td colspan="2">神经网络预测患者得病与否</td><td rowspan="2">合计</td></tr><tr><td>香</td><td>是</td></tr><tr><td>香</td><td>8631</td><td>38</td><td>8 669</td></tr><tr><td>是</td><td>162</td><td>130</td><td>292</td></tr><tr><td>合计</td><td>8793</td><td>168</td><td>8961</td></tr></table></body></html>

# 4.3不同数据挖掘算法性能对比分析

通过对决策树、逻辑回归和神经网络三种算法在R中运行、建模和预测数据时所表现的不同特点，对其在TP、FP、FN、TN、查准率、召回率、正确率、F值方面进行对比研究，验证其应用于妊高症时的性能，为算法的选择提供依据，如表5所示：

表5三种数据挖掘算法性能指标对比  

<html><body><table><tr><td>算法</td><td>TP FP FN TN</td></tr><tr><td>137 45</td><td>查准率 召回率 正确率 F值 8 608 55.52% 79.71% 97.97% 0.65</td></tr><tr><td>决策树</td><td>171</td></tr><tr><td>168 42</td><td>0.57</td></tr><tr><td>逻辑回归 140 神经网络 130</td><td>8 611 45.45% 76.92% 97.66%</td></tr></table></body></html>

通过表5可以看出，在查准率一项中，三种算法的性能比较为：决策树 $\mathrm { > }$ 逻辑回归 $>$ 神经网络，这也是其敏感度排名；在召回率一项中，性能比较为：决策树 $>$ 神经网络 $>$ 逻辑回归，这也是其特异性排名；在正确率一项中，性能比较为：决策树 $\mathrm { > }$ 神经网络 $>$ 逻辑回归，这也是其精确度排名；最后，由于查准率和召回率是一组此消彼长的评价指标，单个运用不能总体评价算法的性能，因此用F值对算法的综合性能进行评价，结果为：决策树 $\mathrm { \Sigma > }$ 逻辑回归 $\approx$ 神经网络。综合以上指标可以看出，决策树的性能最好，神经网络的性能略好于逻辑回归，但相差不大。整体来看，三种监督学习算法的性能都非常强。

# 4.4 结果分析

从上述挖掘模型的建立和模型评价方面进行分析，认为:

(1）在疾病危险因素研究方面，决策树能提炼出危险因素的属性组合和数值，而逻辑回归只能分析危险因素的属性列，根据公式(6)对筛选的危险因素属性进行计算得出得病与否的结论，而神经网络由于其黑盒性特征无法提供预测危险因素的可能性，因此决策树在妊高症危险因素挖掘中直观性最好。决策树运用最少的属性就可以判断出患者是否得病，说明其代表性最好。

(2）预测妊高症发病方面，综合各指标可以得出，对于诊断、预防和预后妊高症来说，决策树的性能最好，神经网络次之，而逻辑回归最差，可能是由于逻辑回归的二分类性能和神经网络的“黑盒性"特征所致。

(3）决策树算法运用最少的属性即可得到最优模型，因此是适合于妊娠高血压综合征危险因素挖掘及最终疾病诊断的最优算法。

# 5结语

数据挖掘算法从大数据中挖掘出有用的知识以辅助决策，已成为国际上知识发现领域最前沿的研究方向之一，将数据挖掘算法与自然语言处理、概念映射、本体论等理论和技术结合，通过数据采集、数据清洗、模型建立和模型评价4方面所建立起的异构数据源知识发现框架能快速实现情报的收集和分析。数据挖掘作为一个可从繁杂的信息中进行知识发现的工具，将不再局限于单纯技术层面的研究，而是越来越多与其他应用学科进行交叉融合，因此情报人员应该嵌入到学科实现嵌入式学科服务，同时从研究中还发现，不同的数据挖掘算法对于不同的知识发现有不同的效果，应该具有针对性进行选择，从而更好地对相关领域人员进行决策支持服务。

# 参考文献：

[1]曾建勋，魏来．大数据时代的情报学变革[J]．情报学报, 2015,34(1):37-44.(Zeng Jianxun,WeiLai.The Changes of Information Science in Big Data Era [J]. Journal of the China Society for Scientific and Technical Information,2015,34(1): 37-44.)   
[2] AckoffR L.From Data to Wisdom [J].Journal of Applies Systems Analysis,1980(16): 3-9.   
[3] Bellinger G,Castro D，MillsA．Data， Information, Knowledge,and Wisdom [EB/OL].[2015-11-24]. http://www. systems-thinking.org/dikw/dikw.htm.   
[4] ZelenyM. Human SystemsManagement: Integrating Knowledge,Management and Systems [M]. Singapore:World Scientific,2005:15-16.   
[5] CIO 时代网.DIKW：数据、信息、知识、智慧的金字塔层 次体系[EB/OL].[2014-11-24].http://www.ciotimes.com. (CIO Network Era.DIKW:Pyramid Hierarchy of Data Information，Knowledge,Wisdom [EB/OL].[2014-11-24]. http://www.ciotimes.com.)   
[6] 王日芬．文献计量法与内容分析法综合研究的方法论来源 与依据[J]．情报理论与实践，2009，32(2):21-26.(Wang Yuefen.The Source and Basis of the Methodology of Synthetic Research with Bibliometric Method and Content Analysis Method [J]． Information Studies:Theory& Application,2009,32(2): 21-26.)   
[7]王丽伟，李梅，牟冬梅，等．一种面向知识服务的领域知 识发现流程及实例研究[J]．情报学报，2015，34(1)：45-52. (Wang Liwei,Li Mei,Mu Dongmei,et al．A Knowledge Service-oriented Domain Knowledge Discovery Process[J]. Journal of the China Society for Scientific and Technical Information,2015,34(1): 45-52.)   
[8]徐戈，王厚峰．自然语言处理中主题模型的发展[J]．计算 机学报，2011,34(8):1423-1436.(Xu Ge,Wang Houfeng. The Development of Topic Models in Natural Language Processing [J]. Chinese Journal of Computers, 2011, 34(8): 1423-1436.)   
[9]何清，李宁，罗文娟，等．大数据下的机器学习算法综述 [J]．模式识别与人工智能,2014,27(4):327-336.(He Qing, Li Ning,Luo Wenjuan, et al. A Survey of Machine Learning Algorithms for Big Data [J].PR&AI,2014,27(4): 327-336.)   
[10]唐慧丰，谭松波，程学旗．基于监督学习的中文情感分类 技术比较研究[J]．中文信息学报，2007,21(6):88-94,108. (Tang Huifeng，Tan Songbo,Cheng Xueqi.Research on Sentiment Classification of Chinese Reviews Based on Supervised Machine Learning Techniques [J]. Journal of Chinese Information Processing,2007,21(6): 88-94,108.)   
[11]侯亚君．R 语言在数据挖掘中的运用[J]．晋城职业技术学 院学报,2014,7(2): 63-65.(Hou Yajun. On the Application of R Language in Data Mining [J]. Journal of Jincheng Institute of Technology,2014,7(2): 63-65.)   
[12]杨静，张楠男，李建，等．决策树算法的研究与应用[J]．计 算机技术与发展，2010,20(2):114-116,120.(Yang Jing, Zhang Nannan,Li Jian,et al. Research and Application of Decision Tree Algorithm [J]. Computer Technology and Development,2010,20(2): 114-116,120.)   
[13] 洪家荣，丁明峰，李星原，等．一种新的决策树归纳学习 算法[J]．计算机学报,1995,18(6):470-474.(Hong Jiarong, Ding Mingfeng,Li Xingyuan,et al.A New Algorithm of Decision Tree Induction [J]. Chinese Journals of Computers, 1995,18(6): 470-474.)   
[14]邢秋菊，赵纯勇，高克昌．基于GIS 的滑坡危险性逻辑回 归评价研究[J]．地理与地理信息科学，2004，20(3):49-51. (Xing Qiuju， Zhao Chunyong，Gao Kechang.Logical Regression Analysis on the Hazard of Landslide Based on GIS [J].Geography and Geo-Information Science, 2004, 20(3): 49-51.)   
[15]邬伦，刘瑜，张晶，等．地理信息系统—原理、方法和应 用[M].北京：科学出版社,2001.(Wu Lun,Liu Yu,Zhang Jing，et al.Geographical Information System- -Theory, Method,Application [M].Beijing:Science Press,2001.)   
[16]王春峰，万海晖，张维．基于神经网络技术的商业银行信 用风险评估[J]．系统工程理论与实践，1999(9):24-32. (Wang Chunfeng，Wan Haihui,Zhang Wei．Credit Risk Assessment in Commercial Banks Using Neural Networks [J]. System Engineering Theory and Practice,1999(9):24-32.)   
[17]McClelland JL,Rumelhart D E,Hinton G E.Parallel Distributed Processing:Explorations in the Microstructure of Cognition [M].Cambridge,MA:MIT Press,1986.   
[18] Zhang Y,Cui H,Burkell J,et al．A Machine Learning Approach for Rating the Quality of Depression Treatment Web Pages [C]. In: Proceedings of iConference 2014.   
[19]Manning CD,Schutze H,Raghavan P.信息检索导论 [M]. 王斌译．北京：人民邮电出版社，2010:105-107，196-200. (Manning C D,Schutze H,Raghavan P. Introduction to Information Retrieval [M]. Translated by Wang Bin. Beijing: Posts & Telecom Press,2010:105-107,196-200.)   
[20]赵莹．配对四格表资料的条件Logistic 回归模型的Bayes 分析 [J]．数理医药学杂志,2010,23(5):505-506.(Zhao Ying.Bayes Analysis of Conditional Logistic Model for Paired Fourfold Table Data [J].Journal of Mathematical Medicine,2010,23(5): 505-506.)

# 作者贡献声明：

牟冬梅：提出研究思路，设计研究方案和技术路线，论文撰写与定稿;任珂：研究过程的实施，数据清洗及数据分析，论文撰写。

# 利益冲突声明：

牟冬梅，任珂在本文研究中使用了长春市妇产医院的电子病历数据。

# 支撑数据：

支撑数据[1]见期刊网络版 http://www.infotech.ac.cn；支撑数据[2-3]由作者自存储,E-mail:moudm@jlu.edu.cn。  
[1]牟冬梅，任珂.prog_code.rdf.疾病预测模型实验环境、程序代码与结果.  
[2]牟冬梅，任珂.trainingData.csv.妊娠高血压预测模型训练数据集.  
[3]牟冬梅，任珂.testingData.csv.妊娠高血压预测模型测试数据集.

收稿日期:2016-02-19   
收修改稿日期:2016-03-26

# Discovering Knowledge from Electronic Medical Records with Three Data Mining Algorithms

Mu DongmeiRen $\mathrm { K e } ^ { 2 }$ 1(School of Public Health, Jilin University, Changchun 130021, China) 2(School of Information Management, Wuhan University, Wuhan 430072, China)

Abstract: [Objective]This empirical study tries to identifyrisk factors fordiseases fromthe heterogeneous Electronic Medical Records (EMR).[Methods]First, we colected EMR with various data structures.Second,we built models to predict risk factors for diseases with the helpof three algorithms (i.e.,decision-making tree,logistic regression and neutral network).Finally,we compared and evaluated these models statisticall.[Results] The Decision Tree Model achieved higher recall and precision rates than the Logistic Regression and Neural Network ones. However,there was no significant diference among them.[Limitations] We did notoptimize the EMR's properties.[Conclusions] The Decision Tree Model does a beter job than the Logistic Regression and Neural Network models in discovering the risk factors to predict diseases.The framework of knowledge discovery based on data mining algorithms,provides some directions for future research.

Keywords: Knowledge discoveryElectronic medical recordData mining algorithmsPrediction model