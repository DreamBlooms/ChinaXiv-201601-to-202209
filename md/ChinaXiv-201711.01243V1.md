# 基于电子病历利用支持向量机构建疾病预测模型

# 以重度急性胰腺炎早期预警为例

张晔」张晗」尹玢璨」 赵玉虹²1（中国医科大学医学信息学院 沈阳 110122)2(中国医科大学附属盛京医院沈阳110004)

摘要：【目的】为构建疾病预测模型，以重度急性胰腺炎早期预警为例，提出一种基于支持向量机的疾病预测模型构建方法。【方法】基于支持向量机LIBSVM3.11，采用优化后的径向基核函数产生的分类器，同时结合统计学单因素及多因素 Logistic 回归分析方法，进行特征变量选取，提出一种简单易行的重度急性胰腺炎早期预警模型。【结果】所构建重度急性胰腺炎预警模型准确率达 $70 . 3 7 \%$ 。最终纳入模型变量包括白细胞计数、血清钙离子、血清脂肪酶、收缩压、舒张压及胸腔积液。【局限】样本量有限，主要采用支持向量机构建疾病预测模型，未来可建立系统，突出临床应用价值。【结论】支持向量机可构建疾病预测的最优模型，进一步建立系统，辅助临床决策。

关键词：支持向量机重度急性胰腺炎 预警临床决策

分类号：TP393 G35

# 1引言

电子病历(ElectronicMedicalRecord，EMR)即基于计算机的病人记录，是对医疗数据进行电子化保存、管理、传输和重现，主要包括门诊EMR、住院EMR、急诊EMR，其中住院EMR由病历首页、入院记录、病程记录、手术(医嘱)记录单、检查报告单等组成[1]。基于EMR可获得准确、完整的医疗资料，提示和警示医疗人员，提供临床决策支持。电子病历的核心价值在于临床决策支持，即应用统计分析、数据挖掘等方法，辅助临床决策，对疾病早期预警或特定结局事件发生监测起到重要作用。

随着医疗卫生信息化的发展，电子病历辅助临床决策功能需求增多。建立临床决策支持系统，可减少临床实践过程中误诊或漏诊的出现，同时还可减少医疗资源占用，解决医疗拥挤等问题。

# 2相关研究

目前多数临床决策支持应用研究包括疾病诊断、危险因素或复发与否等预测。例如：心力衰竭诊断金标准的制定[2]、阿尔兹海默病进展预测[3]、心肺骤停或死亡事件发生预测[4]以及传染病症状监测系统的创建[5]等。虽然此类研究近年来发展速度较快，然而多数目的在于制定临床标准，或者是已有预测方法的比较评估及新预测方法的提出，并没有完全与临床实际应用接轨。真正的辅助临床决策，不仅仅是建立预测模型或评判预测方法，而是在于如何提高医生工作质量，例如缩短诊疗时间、避免过度医疗、减少医疗差错等。

常用的决策方法有机器学习、统计分析及规则归纳法等，机器学习以支持向量机(SupportVector

Machine,SVM)、人工神经网络为主。其中,Kim 等[6]分别基于人工神经网络和SVM建立晚期前列腺癌术前预测模型;Kim等7基于SVM建立乳腺癌复发预测模型；吕奕等[基于SVM提出一有效的肠癌肝转移预测模型。支持向量机是由Vapnik 等提出的一套学习算法，是寻找稳健分类模型的一种代表性算法[9]。针对不同领域、不同类型数据(医学数据、金融数据、生物数据等)，有研究者把 SVM 和其他分类方法进行预测模型的性能比较，结果发现SVM算法在分类性能、泛化能力、建模计算量等方面具有明显优势[10]。SVM的基本思想是定义最优线性超平面，进而基于Mercer核展开定理，通过非线性映射 $\phi$ 。把样本空间映射到一个高维乃至于无穷维的特征空间，使在特征空间中可以应用线性学习机的方法解决样本空间中的高度非线性问题[]。近年来，随着 SVM核函数的嵌人，医学领域中越来越多的临床决策研究者开始应用SVM构建预测模型。疾病预测模型建立本质上是一个分类问题。疾病预测分类具有样本数量有限、维数较高等特点，原理上符合SVM的适用条件，因为SVM作为一种专门针对小样本的算法，既不同于基于大数定律的传统统计方法，同时也不同于其他机器学习方法如人工神经网络等要求大样本数据，且会出现网络结构难以确定、过学习、欠学习、学习时间长等问题。本研究基于电子病历首次病程记录和实验室检验数据，应用支持向量机构建重度急性胰腺炎疾病预测模型，旨在提出一种简单易行的早期预警模型，以期进一步建立系统，辅助临床决策。

# 3研究框架与方法

疾病预测主要涉及疾病诊断、进展或复发等预测，实质上就是“是"与“否"的二分类问题。基于支持向量机构建疾病预测模型具体流程如图1所示：

![](images/9d62b9d5bc48bf63f678bb309434c9a134b5214edc1bdab2ce3baf477e17abb5.jpg)  
图1基于支持向量机构建疾病预测模型流程  
图2LIBSVM所需数据格式

(1）数据下载收集：确定研究变量及结局变量指标。根据EMR首页疾病ICD编码，查询下载相应疾病EMRs，下载内容包含首次病程记录、实验室检验报告等。而后根据纳入排除标准纳入符合标准的病历。将纳人病历分为训练集、测试集。

(2）数据预处理：如若病历下载内容包括首次病  
程记录，则需对文本进行汉语分词处理，可应用中国  
科学院计算技术研究所的NLPIR软件[11]对各EMR首  
次病程记录的症状特征词初步分词；经初步分词后，  
如若需要，可基于规则和专业词典针对词义否定识别  
进行分词调整；调用NLPIR软件程序抽取所调整症状  
特征词(关键词)，核心代码如下所示：{int nCount $\ O =$ NLPIR_ImportUserDict("userdic.txt");NLPIR_FileProcess("Test.txt","Result.txt",1);sResult=NLPIR_GetFileKeyWords("test.txt");printf("Keywordsare: $\scriptstyle \ln \% \mathbf { s } \ln ^ { \prime }$ ',sResult);}

(3）疾病预测模型建立：基于MATLAB2010a平台，选用LIBSVM3.11工具箱[12]进行支持向量机分类建模。调用函数xlsread将数据集Excel文件读入转换成所要求的矩阵格式，如图2所示：

<labell><index11>:<value11>... <indexlm>:<valuelm> <label2><index21>:<value21>..<index2m>:<value2m> <label $\mathfrak { n } ^ { > }$ <index n1>:<value nl>.. <index nm>:<value nm>

其中label为样本结局变量标签，index为研究变量,value 为变量属性值。调用函数mapminmax 将数据归一化至[-1,1]，以统一变量量纲，同时简化计算。

SVM解决非线性问题关键在于引入核函数类型及参数的选择。通过调整参数t，调整核函数类型(包括线性、多项式、径向基、sigmoid函数)；采用网格搜索寻找最优核参数(c，g)；采用最优参数进行分类模型训练，依据留一法计算预测模型准确率，以高者为优，确定最终预测模型及函数表达式。核心代码如下：

$> >$ bestcv $= 0$ ，   
for $\log 2 \mathsf { c } = - 5 : 5$   
for $\log 2 \mathrm { g } = - 5 : 5$   
$\mathrm { c m d } = [ \mathrm { ' - v ~ 5 ~ - c ~ ' , ~ n u m 2 s t r ( 2 ^ { \wedge } l o g 2 c ) , ~ ' - g ~ ' , ~ n u m 2 s t r ( 2 ^ { \wedge } l o g 2 g ) } ] ;$ $\mathbf { c v } =$ svmtrain(aptr_label,aptr_instl,cmd);   
if( $\mathrm { c v } > =$ bestcv), bestcv $\mathbf { \Psi } = \mathbf { c v }$   
bestc $= 2 { \mathrm { \land l o g 2 c } }$   
bestg $= 2 { \mathrm { \sim } } \log 2 \mathrm { \mathrm { g } }$   
end   
fprintf $( \% ) \mathrm { ~ ‰ ~ }$ (best $c { = } \% \mathrm { g }$ $\mathrm { g { = } \% g }$ ,rate $= \% \textcircled { \mathrm { g } } \backslash \mathrm { n } ^ { \prime }$ ,log2c,log2g, cv, bestc,bestg,bestcv);   
end   
end   
$\gg$ model $\ O =$ svmtrain(aptr_label,aptr_inst1,'-t -c-g); $\gg$ [predict_label,accuracy]=svmpredict(apte_label,apte_inst,model):

(4）特征变量选取：依据数据分布情况选用不同方法进行单因素统计学分析(独立样本T检验或双样本Kolmogorov-Smirnov 检验或卡方检验)初步筛选变量；而后将P值小于0.2的变量纳入Logistic 回归分析，选取最终高预测性能变量， $\mathrm { P } { < } 0 . 0 5$ 具有统计学意义。

(5）疾病预测模型再建立：依据所选取特征变量,再次基于 SVM 构建疾病预测模型，比较预测性能前后是否有所提高。

# 4研究过程

# 4.1 分类模型建立

# (1）研究对象

随机抽取辽宁省某医院去识别化的2013年1月至2015年3月主诊断为急性胰腺炎(Acute Pancreatitis,AP)的电子病历323例，其中非重度203例、重度120例。纳入标准为：住院病例；出院诊断中主诊断为急性胰腺炎；腹痛发作时间小于30天。排除标准为：转院、二次入院病例；慢性胰腺炎、胰腺肿瘤；所研究变量数据不全。

# (2）研究变量

参考Up To Data 临床顾问数据库[13]中列出的 AP严重程度危险因素，最终选取的研究变量 $( \mathrm { n } { = } 2 0 )$ 包括：年龄、白细胞计数、红细胞比积、尿素、肌酐、 $\mathrm { K } ^ { + }$ /$\mathrm { { N a } ^ { + } }$ 、 $\mathrm { C a } ^ { 2 + }$ 、血清淀粉酶、血清脂肪酶、体温、心率、呼吸频率、血压(收缩压/舒张压)、腹痛发作时间，以及是否神清、是否器官衰竭、是否胰腺坏、是否有胸腔积液存在。

# (3）结局变量

根据国际AP专题研讨会最新修订的AP分级和分类系统,AP可分为三级：轻度AP(Mild Acute Pancreatitis,MAP)、中度 AP(Moderately Severe Acute Pancreatitis,MSAP)、重度 AP(Severe Acute Pancreatitis, SAP)[14]。本研究选用出院诊断重度急性胰腺炎与否作为结局变量。

# (4）数据预处理

研究中所纳入变量包括4项分类变量，即"是否神清”、“是否器官衰竭”、“是否胰腺坏死”、“是否存在胸腔积液”，以文字描述形式在首次病程记录中出现，需进行汉语分词处理。将纳入样本按 $3 : 1$ 分为训练集$( \mathrm { n } { = } 2 4 2 )$ 和测试集 $\scriptstyle ( \ n = 8 1$ )，针对训练集，NLPIR软件初步分词处理各EMR首次病程记录的病例特点，包括：现病史、既往史、体格检查辅助检查。需向NLPIR分词软件中添加用户词典，包括：ICD-10编码对应术语,中文 MeSH 主题词(款目词)，中文数据库中相应主题词、关键词，对添加的预测指标词进行关键词标记(Key)；经初步分词后，基于规则(人工制定)和专业词典(AP诊治标准中标准术语)针对词义否定识别进行分词调整；调用NLPIR软件抽取所调整疾病严重程度特征词(描述上述4项分类变量)，标记诊断结果(是否SAP)；针对测试集：初步分词、分词调整、特征词抽取步骤细节除 NLPIR 软件添加用户词典外，其余相同。测试集中向NLPIR用户词典中另外添加训练集中所抽取的特征词。

# (5）建立分类预测模型

基于训练集数据建立上述20个变量与结局变量间的分类预测模型，再基于测试集计算所建立模型预测准确率。本研究选用默认参数值，分别选择不同的核函数进行分类建模。预测性能如表1所示：

表1不同核函数分类预测性能  

<html><body><table><tr><td>核函数</td><td>c</td><td>g</td><td>V</td><td>Sv</td><td>bsv</td><td>trA</td><td>teA</td></tr><tr><td>线性</td><td>1</td><td>/</td><td>242</td><td>179</td><td>171</td><td>69.83%</td><td>67.90%</td></tr><tr><td>多项式</td><td>1</td><td>0.05</td><td>242</td><td>182</td><td>178</td><td>60.33%</td><td>69.14%</td></tr><tr><td>径向基(RBF)</td><td>1</td><td>0.05</td><td>242</td><td>183</td><td>178</td><td>59.09%</td><td>70.37%</td></tr><tr><td>sigmoid</td><td>1</td><td>0.05</td><td>242</td><td>184</td><td>176</td><td>62.81%</td><td>62.96%</td></tr></table></body></html>

(注：v:交叉验证折数；sv:支持向量数;bsv:边界支持向量数;trA:训练集准确率,teA:测试集准确率。)

选用径向基核函数，结合网格搜索和交叉验证方法选择最优参数，预测性能如表2所示：

表2径向基参数优化前后预测性能  

<html><body><table><tr><td>方法</td><td>C</td><td>g</td><td>v</td><td>sv</td><td>bsv</td><td>trA</td><td>teA</td></tr><tr><td>未优化</td><td>1</td><td>0.05</td><td>242</td><td>183</td><td>178</td><td>59.09%</td><td>70.37%</td></tr><tr><td>网格搜索</td><td>16</td><td>0.0625</td><td>242</td><td>175</td><td>159</td><td>69.01%</td><td>67.90%</td></tr></table></body></html>

(注v:交叉验证折数；sv:支持向量数；bsv:边界支持向量数;trA:训练集准确率,teA:测试集准确率。)

# (6)特征变量选取

对纳入研究变量进行特征变量选取，确定高预测性能变量。采用SPSS19.0进行统计学分析。变量筛选结果如表3所示：

表3单因素分析结果  

<html><body><table><tr><td>变量</td><td>缩写</td><td>是否 SAP t(p)</td><td>是否 SAP z(p)</td><td>是否 SAP x² (p)</td></tr><tr><td>年龄</td><td>Y</td><td>0.313(0.755)</td><td>/</td><td>/</td></tr><tr><td>白细胞计数</td><td>WBC</td><td>-4.784(0.000)*</td><td>/</td><td>/</td></tr><tr><td>红细胞比积</td><td>HCT</td><td>-0.528(0.598)</td><td>/</td><td>/</td></tr><tr><td>钾</td><td>K+</td><td>0.114(0.909)</td><td>/</td><td>/</td></tr><tr><td>收缩压</td><td>SBP</td><td>-1.342(0.181)*</td><td></td><td>/</td></tr><tr><td>尿素</td><td>Urea</td><td>/</td><td>1.425(0.035)</td><td>/</td></tr><tr><td>肌酐</td><td>Cr</td><td>/</td><td>0.518(0.951)</td><td>/</td></tr><tr><td>钠</td><td>Na+</td><td>/</td><td>1.164(0.133)*</td><td>/</td></tr><tr><td>钙</td><td>Ca2+</td><td>/</td><td>2.972(0.000)*</td><td>/</td></tr><tr><td>血清淀粉酶</td><td>AMY</td><td>/</td><td>1.270(0.080)*</td><td>/</td></tr><tr><td>血清脂肪酶</td><td>LPS</td><td>/</td><td>2.043(0.000)*</td><td>/</td></tr><tr><td>体温</td><td>T</td><td>/</td><td>1.317(0.062)*</td><td>/</td></tr><tr><td>心率</td><td>P</td><td>/</td><td>2.043(0.000)*</td><td>/</td></tr><tr><td>呼吸频次</td><td>R</td><td>/</td><td>0.800(0.544)</td><td>/</td></tr><tr><td>舒张压</td><td>DBP</td><td>/</td><td>1.879(0.002)*</td><td>/</td></tr><tr><td>腹痛发作时间</td><td>/</td><td>/</td><td>1.133(0.153)*</td><td>/</td></tr><tr><td>器官衰竭</td><td>OF</td><td>/</td><td>/</td><td>**(0.018)*</td></tr><tr><td>精神状态</td><td>/</td><td>/</td><td>/</td><td>0.581(0.446)</td></tr><tr><td>胰腺坏死</td><td>PN</td><td>/</td><td>/</td><td>**(0.372)</td></tr><tr><td>胸腔积液</td><td>PE</td><td>/</td><td>/</td><td>14.238(0.000)*</td></tr></table></body></html>

(注：若两类样本数据为连续型变量且均服从正态分布，单因素分析选用T检验；若两类样本数据为连续型变量但不均服从正态分布，单因素分析选用 Kolmogorov-Smirnov 检验；若两类样本数据为分类变量，单因素分析选用卡方检验; $*$ ：单因素分析 $\mathsf { p } { < } 0 . 2$ ，纳入Logistic 回归分析; $^ { * * }$ ：采用Fisher's精确检验。）

经单因素分析纳入Logistic回归分析的变量有白细胞计数(WBC)、收缩压(SBP)、尿素(Urea)、钠 $( \mathrm { N a } ^ { + } )$ 、钙 $( \mathrm { C a } ^ { 2 + } )$ 、体温(T)、心率(P)、舒张压(DBP)、血清淀粉酶(AMY)、血清脂肪酶(LPS)、腹痛发作时间、器官衰竭(OF)、胰腺坏死(PN)、胸腔积液(PE)。经 Logistic回归分析，最终纳入特征变量有：白细胞计数、血清钙离子、血清脂肪酶、收缩压、舒张压以及是否伴有胸腔积液。Logistic回归方程如公式(1)所示：

$\mathrm { P = 1 } / \{ 1 + \mathrm { e x p } [ - ( 4 . 7 6 7 + 0 . 1 2 6 ^ { \circ } \mathrm { W B C } ^ { \prime } - 3 . 1 4 2 ^ { \circ } \mathrm { C A } ^ { \prime } + 0 . 0 0 1 ^ { \circ } \mathrm { L P S } ^ { \prime } - $

$$
0 . 0 2 7 ^ { \prime } \mathrm  S B P ^ { \prime } + 0 . 0 5 9 ^ { \prime } D B P ^ { \prime } - 2 . 1 5 7 ^ { \prime } P E ^ { \prime } ) ] \}
$$

(7）分类预测模型再建立

选用径向基核函数，结合网格搜索和交叉验证方法选择最优参数。c最优值为2，g最优值为1，模型支持向量数为180，训练集和测试集准确率分别为$6 5 . 2 9 \%$ 、 $70 . 3 7 \%$ 。最终决策函数如下：

$$
{ \mathrm { P r e d i c t } } _ { - } { \mathrm { y } } = { \mathrm { s i g n } } { \left( \sum _ { \mathrm { i } = 1 } ^ { \mathrm { n } } { \mathrm { W } } _ { \mathrm { i } } \exp ( - \mathrm { g a m m a } \parallel { \mathrm { x } } _ { \mathrm { i } } - \mathbf { x } \parallel ^ { 2 } ) - 0 . 3 8 8 \right) }
$$

其中, $\left| \left| \mathbf { X } _ { \mathrm { i } } - \mathbf { X } \right| \right| ^ { 2 }$ 为二范数距离, $\mathfrak { n }$ 代表支持向量的个数即180；对于每一个i: $\mathbf { W _ { i } = }$ model.sv_coef(i)，即支持向量的系数, $\begin{array} { r } { \mathbf { X } _ { \mathrm { i } } \mathrm { = m o d e l . S V s ( i , : ) } . } \end{array}$ ，即支持向量矩阵。X是待预测样本,gamma 是参数 $\mathbf { g }$ 0

# 4.2分类模型预测性能评价

采用测试集数据对预测模型的准确率进行客观评估，其中SAP类设为正类、非SAP类设为负类，使用准确率衡量模型预测性能。计算公式如下：

准确率(A) $\scriptstyle =$ （真正 $. +$ 真负)/总样本数

本研究测试集81个样本中，正类样本数30，负类样本数51，其中真正样本数14，假负样本数16，假正样本数8，真负样本数 43。计算得准确率(A)为$70 . 3 7 \%$ 。

# 4.3 对比实验

另选用Logistic回归分析、决策树和人工神经网络方法进行对比实验。训练集、测试集样本同SVM建立模型所用。采用WEKA3.7.13软件包实现上述算法,WEKA是一基于Java语言编写的数据挖掘机器学习软件，包括完整的数据处理工具、学习算法和评价方法[15]。就分类问题，可选择不同分类算法(贝叶斯、决策树、多层感知器、支持向量机等)建立不同分类器。本文分别选择“Classifier”下“Logistic”、“J48”、"MultilayerPerceptron"实现Logistic 回归分析、决策树和人工神经网络算法，选择默认参数，对于训练集同样采用留一法建立模型。最终通过分类模型的评估量化度量模型预测性能。三种方法与SVM建模后筛选特征变量后再建模预测准确率比较如表4所示：

表4不同方法预测准确率比较  

<html><body><table><tr><td>方法</td><td>v</td><td>trA</td><td>teA</td></tr><tr><td>Logistic</td><td>242</td><td>95.87%</td><td>62.96%</td></tr><tr><td>决策树</td><td>242</td><td>99.59%</td><td>62.96%</td></tr><tr><td>人工神经网络</td><td>242</td><td>97.52%</td><td>64.20%</td></tr><tr><td>SVM</td><td>242</td><td>65.29%</td><td>70.37%</td></tr></table></body></html>

(注:v:交叉验证折数;trA:训练集准确率,teA:测试集准确率。)

# 5 结果及讨论

由表1可知，不同核函数所对应的分类模型的预测准确率存在一定的差别，针对测试集数据，本实验中多项式核函数和径向基核函数的预测准确率较高，且支持向量的个数较为理想。本实验选用SVM构建重度急性胰腺炎早期预警模型，是由于SVM基于核函数实现升维，可解决非线性分类和回归问题；SVM的最终决策函数只由少数的支持向量决定，计算的复杂性取决于支持向量数，而不是纳入的研究变量数;相较于其他方法，建立SVM 模型所需的人为干预少,可保证模型的客观性，因此SVM常用来解决医疗数据分类和回归建模问题。应用SVM解决非线性问题多选用径向基函数作为核函数。原因是其适合非线性关系；其模型复杂度较好，优于多项式；其数值计算易实现。选用网格搜索和交叉验证的参数寻优方法，虽然所得结果不一定是理论上的最优，但也能够满足一定条件下的最优。本实验选用径向基核函数，并结合网格搜索和交叉验证方法选择最优参数。由表2参数优化前后对比可知，参数优化不仅能够提高模型预测准确率，同时还可以减少支持向量个数，从而简化预测函数。

基于SVM所建立的SAP预测模型，其预测准确率较为理想，说明支持向量机方法可用于建立疾病预测模型，通过核函数选择和参数寻优可以对模型预测性能进行优化。支持向量机所建立模型虽具有较好预测性能，但在临床实际中模型中变量不一定都与预测结局高度相关甚至相关，因此模型建立后特征变量选择尤为重要[16]

根据数据分布不同针对各分布数据选择不同单因素分析方法，目的在于初步筛选变量，剔除非高度相关变量或者某些同效变量，同时减少进入Logistic回归分析所需样本数。所选变量具体从AP炎性反应、特征酶变化及伴发症影响AP严重程度进展。基于所选变量再建预测模型，预测模型准确率较前提高。说明基于特征选取简化数据维数，不仅能够摆脱与预测任务不相关的数据、显著减少所需的训练集样本数量，同时还能够提高模型预测性能。

在对比实验中，如表4所示，Logistic回归分析、决策树和人工神经网络三种方法，训练集准确率较SVM高，但测试集准确率均较SVM低。原因在于此三种方法在构建模型时，以经验风险最小为原则，可能存在过拟合的现象。疾病预测模型的建立最终问题是寻找稳健分类模型，SVM作为一种以结构风险最小化原理为基础的算法，权衡训练样本的平均预测误差与模型的复杂度，以经验风险和置信区间的和最小为目标，所建立的分类模型具有较好的鲁棒性。因此测试集准确率较为理想。

# 6结语

随着医院信息化的建设，电子病历其核心价值即临床决策支持将成为未来发展的方向。本研究基于SVM，以重度急性胰腺炎为例，基于电子病历构建疾病预测模型。本研究特点包括：以重度急性胰腺炎为例，尝试采用文字型及数值型医疗数据建立疾病早期预警模型，以期进一步建立决策系统；选用支持向量机建立预测模型后结合统计学分析方法筛选特征变量，而后再基于特征变量建立最终预测模型，提高预测准确率的同时简化模型。研究也存在不足，表现在临床应用方面。在今后的研究中，将进一步根据所建立模型创建决策系统，突出其临床应用价值。此外，以临床需求为出发点，增加样本数，应用决策方法构建疾病预测模型，并且如何服务于临床，也是从事临床决策支持研究者应共同努力的方向。

# 参考文献：

[1] 雷健波．电子病历的核心价值与临床决策支持[J]．中国数 字医学，2008,3(3):26-30.(Lei Jianbo.Clinical Decision Support and the Core Value of Electronic Medical Record [J]. China Digital Medicine,2008,3(3):26-30.)   
[2]Byrd R J, Steinhubl S R, Sun J,et al. Automatic Identification of Heart Failure Diagnostic Criteria,Using Text Analysis ofClinical Notes from Electronic Health Records [J]. International Journal of Medical Informatics,2014,83(12): 983-992.   
[3]Ye J,Farnum M, Yang E,et al. Sparse Learning and Stability Selection for Predicting MCI to AD Conversion Using Baseline ADNI Data [J].BMC Neurology，2012．DOI: 10.1186/1471-2377-12-46.   
[4] Alvarez C A,Clark C A,Zhang S,et al.Predicting out of Intensive Care Unit Cardiopulmonary Arrest or Death Using Electronic Medical Record Data [J].BMC Medical Informatics and Decision Making,2013.DOI: 10.1186/1472- 6947-13-128.   
[5]Matheny M E,Fitzhenry F,Speroff T,et al. Detection of Infectious Symptoms from VA Emergency Department and Primary Care Clinical Documentation [J]. International Journal of Medical Informatics,2012,81(3):143-156.   
[6]Kim S Y,Moon S K,Jung D C,et al.Pre-Operative Prediction of Advanced Prostatic Cancer Using Clinical Decision Support Systems:Accuracy Comparison between Support Vector Machine and Artificial Neural Network [J]. Korean Journal of Radiology,2011,12(5): 588-594.   
[7]Kim W, Kim K S,Lee J E,et al. Development of Novel Breast Cancer Recurrence Prediction Model Using Support Vector Machine [J]. Journal of Breast Cancer,2012,15(2): 230-238.   
[8]吕奕，王清．一种基于概率校正和集成学习的肠癌肝转移 预测模型[J]．计算机应用与软件，2011,28(9):48-51.(Lv Yi，Wang Qing.A Probability Calibration and Ensemble Learning Based Colorectal Cancer Liver Metastasis Prediction Model [J]. Computer Applications and Software, 2011,28 (9): 48-51.)   
[9]王星,等．大数据分析：方法与应用[M]．北京：清华大学 出版社,2013: 68-90.(Wang Xing,et al.Big Data Analysis: Methods and Applications[M]. Beijing: Tsinghua University Press,2013:68-90.)   
[10]陈永义，熊秋芬．支持向量机方法应用教程[M]．北京：气 象出版社，2011:6-10．(Chen Yongyi，Xiong Qiufen. Application of Support Vector Machines Tutorial [M]. Beijing: China Meteorological Press,2011:6-10.)   
[11]ICTCLAS 2014 [EB/OL].[2015-03-25].http:/ictclas.nlpir. org/.   
[12]LIBSVM—A Library for Support Vector Machines [EB/OL]. [2015-03-25].http://www.csie.ntu.edu.tw/\~cjlin/libsvm/.   
[13]Up To Data [EB/OL]. [2015-03-25].http://www.uptodate. com/contents/search.   
[14]Banks P A,Bollen TL,Dervenis C,et al.Classification of AcutePancreatitis--2012:RevisionoftheAtlanta Classification and Definitions by International Consensus [J]. Gut, 2013,62(1): 102-111.   
[15]袁梅宇．数据挖掘与机器学习—WEKA 应用技术与实践 [M].北京：清华大学出版社，2014:2.(Yuan Meiyu.Data MiningandMachineLearning——WEKA Application Technology and Practice [M].Beijing:Tsinghua University Press,2014: 2.)   
[16]刘勘，朱怀萍，刘秀芹．基于支持向量机的网络伪舆情识别 研究[J].现代图书情报技术，2013(11):75-80.(Liu Kan,Zhu Huaiping,Liu Xiuqin. Detection of Internet Deceptive Opinion BasedonSVM[J].New Technology ofLibraryand Information Service,2013(11): 75-80.)

# 作者贡献声明：

张晔：设计研究方案，负责实验，采集、清洗和分析数据，论文起草及最终版本修订;  
张晗：提出研究思路，修改论文;  
尹玢璨：采集、清洗和分析数据。  
赵玉虹：提出研究思路，修改论文。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储，可通过电子邮件向作者索取，E-mail:1332457636@163.com。[1]张晔，赵玉虹.ap.xls.急性胰腺炎电子病历纳入样本变量数据.[2]张晔，赵玉虹.apdic.txt.急性胰腺炎专业词典.

收稿日期:2015-09-21  
收修改稿日期:2015-12-07

# Building Disease Prediction Model Using Support Vector Machine Case Study of Severe Acute Pancreatitis

Zhang Ye’Zhang Han1Yin Bincan’Zhao Yuhong2 1 (Department of Medical Informatics, China Medical University, Shenyang 110122, China) 2(Shengjing Hospital of China Medical University, Shenyang 110004, China)

Abstract: [Objective] This study developed a disease prediction model based on the support vector machine,using electronic medical records of the severe acute pancreatitis patients.[Methods] We first adjusted the kernel type and parameter values of the support vector machine method to get an optimized prediction model.Then, we combined it with univariable and multivariable logistic regresion analysis methods to select features'variable.Finaly, we proposed a simplified early warning model for the severe acute pancreatitis.[Results] The new model's prediction accuracy rate is $70 . 3 7 \%$ .Variables used by this model include: white blood cell count,serum calcium,serum lipase,systolic blood pressure,diastolic blood pressure and pleural effusion.[Limitations] Because of the smallsample size,we only used this support vector machine method to develop the new disease prediction model. In the future, we willtryto establish a larger examination system for the clinical trial.[Conclusions] Support vector machine can help us develop an optimal disease prediction model. A new system based on this model could support our clinical decision makings.

Keywords: Support Vector Machine Severe acute pancreatitisEarly warning Clinical decision

# 欢迎订阅2016年《现代图书情报技术》 (月刊)

《现代图书情报技术》杂志是由中国科学院文献情报中心主办的学术性、信息管理技术类专业期刊。1980年创刊,原名《计算机与图书馆》，1985年更名为《现代图书情报技术》，是国内图书馆学、情报学领域唯一一份技术性刊物，连续多次被授予"中国图书馆学优秀期刊"荣誉称号。

期刊定位面向国内信息技术领域的科研人员，跨图书馆学、情报学、信息科学等几大学科，以报道信息技术的研发与应用为主体，倡导原创性科研论文，同时兼顾应用实践型文章。

月刊：国际通行16开版本  
国内邮发代号：82-421  
地址：北京中关村北四环西路33 号(100190)  
E-mail: jishu@mail.las.ac.cn

定价：80元/期，全年定价：960元国外邮发代号：M4345电话/传真:010-82624938网址:http://www.infotech.ac.cn