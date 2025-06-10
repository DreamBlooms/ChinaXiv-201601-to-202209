# 青贮发酵对玉米秸秆品质及菌群构成的影响

# 陶　莲  刁其玉\*

（中国农业科学院饲料研究所，农业部饲料生物技术重点实验室，北京100081）

摘 要：本研究旨在探讨青贮发酵对玉米秸秆感官指标、发酵品质、营养成分以及门、纲、目、科和属5个水平细菌群落构成及丰度的影响。将去穗后仍青绿的蜡熟期玉米秸秆切短揉搓至 $1 { \sim } 2 \mathrm { c m }$ ，将水分调节至 $6 5 \% { \sim } 7 0 \%$ 后，取青贮前样品（3个重复）和青贮后样品（3个重复）使用聚乙烯袋真空包装，室温贮藏45d后开启取样，运用实验室检测手段及MiSeq 高通量测序技术分析青贮前后玉米秸秆品质及菌群结构的变化。结果表明：1）青贮发酵 45 d后的玉米秸秆青贮饲料呈黄绿色，质地较好，呈酸香味。青贮发酵作用能够使玉米秸秆 pH迅速降低（ $\scriptstyle P < 0 . 0 5$ )，乳酸含量显著增加（ $\cdot P { < } 0 . 0 5 \$ )，中性洗涤纤维（NDF）及酸性洗涤纤维（ADF)含量有下降趋势( $\cdot P { > } 0 . 0 5$ )。2)玉米秸秆经过青贮发酵后，变形菌门（Proteobacteria）Y-变形菌纲（Gammaproteobacteria）、肠杆菌目（Enterobacteriales）、肠杆菌科（Enterobacteriaceae）和魏斯氏菌属（Weissella）菌群数量显著降低（ $\lceil P { < } 0 . 0 5 \rangle$ ；青贮发酵能够显著增加厚壁菌门（Firmicutes）、芽孢杆菌纲（Bacilli）、乳杆菌目（Lactobacillales）、乳杆菌科（Lactobacillaceae）、片球菌属（Pediococcus）和乳杆菌属（Lactobacillus）菌群数量（P<0.05)。3）青贮发酵改善玉米秸秆感官指标、发酵品质以及营养成分的同时，可以有效降低有害细菌的数量，增加有益菌的数量，从而可以降低致病菌对家畜健康存在的潜在风险。综上，通过实验室检测手段及Miseq高通量测序技术相结合，能够在分析青贮品质的同时，提供青贮前后整个菌落构成及丰度变化的信息，进而为发酵过程的调控提供依据。

关键词：MiSeq；玉米秸秆；青贮发酵；品质；细菌中图分类号：S816 文献标识码： 文章编号：

青贮饲料常被认为是乳酸菌发酵的产物，然而实际上是一个极其复杂的微生物共生体系，参与青贮过程的微生物种类非常多，包括青贮原料上附着的微生物、引起青贮饲料发酵的微生物以及引起青贮腐败变质的微生物等[1]。在青贮发酵过程中，菌落的构成及丰度是不断变化的，乳酸菌等少数优势种群对整个种群起决定作用[2]。为对青贮过程进行调控，促进青贮过程中有益菌种的生长，使青贮饲料迅速进入稳定状态，抑制有害菌的繁殖，从而降低干物质、蛋白质及可溶性糖等营养物质的损失率，提高青贮发酵品质，了解各种微生物的活动规律是非常有必要的，特别是青贮前后起主要作用的菌群的活动规律[3]。近些年来有关青贮过程中微生物种类和丰度的研究一直是国内外该领域研究的热点，这些研究主要包括：1）不同青贮阶段中微生物的动态变化，如乳酸菌、大肠杆菌、霉菌和酵母等[1-2,4]；2）不同青贮剂、青贮原料及青贮条件对青贮过程中微生物种类的影响[5-6]。我国玉米秸秆资源丰富，玉米秸秆青贮应用广泛，青贮后有机物消化率提高 $4 . 8 \% \sim 1 5 . 4 \%$ ，消化能提高 $0 . 2 3 \widetilde { \mathrm { \Omega } } \mathrm { \sim } 0 . 6 2 \mathrm { M J }$ 代谢能提高 $0 . 1 9 { \sim } 0 . 5 6 \mathrm { M J } ^ { [ 5 - 6 ] }$ 。然而目前有关玉米秸秆青贮饲料品质的研究较多，而对发酵前后微生物菌群变化的研究以及玉米秸秆青贮品质及细菌群落相关性的探讨较少。另外，目前有关青贮饲料中微生物研究的方法多采用传统的微生物平板纯培养方法、微平板分析方法、磷脂脂肪酸法以及分子生物学方法[变性梯度凝胶电泳(DGGE)/温度梯度凝胶电泳(TGGE)瞬时温度梯度电泳(TTGE)、16sRNA 基因的末端限制性片段分析技术(T-RFLP)、PCR-单链构象多态性(SSCP)、荧光原位杂交技术（FISH)、印记杂交、定量PCR、基因芯片J等，只能反映出样品中少数优势菌的信息，无法对样品中的微生物做到绝对定量，为微生物进化关系的研究提供的信息也很有限[7-8]。第二代测序技术MiSeq高通量测序平台采用边合成边测序原理，不仅可实现一次并行对几十万到几百万条DNA分子进行序列测定，而且在测序速度和测序通量上都有进一步提升，可以测定微生物从门、纲、目、科、属各个水平上的构成及丰度，具有测序深度高、利于鉴定低丰度群落物种的特点，已成为研究细菌和真菌群落多样性的首选之策[7-8]，目前此平台已在微生物多样性群落结构研究方面受到了广大学者的认可。然而截至目前，有关利用 MiSeq 高通量全基因组测序技术研究玉米秸秆青贮菌群群落及丰度的研究鲜有报道。本研究拟对玉米秸秆青贮前后品质及细菌群落进行系统分析，探明青贮发酵过程对玉米秸秆品质及细菌群落的影响，并分析青贮品质及细菌群落变化的关系，为微生物接种剂的研发及利用生物手段调控青贮发酵过程提供理论依据。

# 1材料与方法

# 1.1试验材料

玉米秸秆（comstraw）取自河北省保定市，品种为三北21，于2014年9月30日蜡熟期摘穗后部分叶片仍然青绿时，立即刈割。

# 1.2 试验设计

本试验共设置青贮前（pre-ensiling）和青贮后（post-ensiling）2个组，每组3个重复，各样品编号见表1。玉米秸秆刈割后，用青贮切碎揉搓机切短至 $1 { \sim } 2 ~ \mathrm { c m }$ ，将蒸馏水均匀喷洒在粉碎玉米秸秆上，将水分调节至 $6 5 \% \sim 7 0 \%$ ，取原料样品后，另取样品装入聚乙烯袋（24$\mathrm { c m } \times 4 0 \mathrm { c m } ,$ ，每袋 $1 \mathrm { k g }$ ，用真空包装机（型号DZ-280/2SD）抽真空并封口。原料样品置于冰盒中，迅速带回实验室， ${ \displaystyle - 2 0 ~ } ^ { \circ } \mathrm { C }$ 贮藏，青贮样品室温条件下（ $2 5 { \sim } 3 7 \ \mathrm { ~ \textdegree }$ ）贮藏，室温贮藏45d后开封取样，立即于-80℃保存，待检。

表1试验组设计及样品编号  
Table1The design of experiment groups and the number of samples   

<html><body><table><tr><td colspan="2">组别Groups</td><td colspan="2">样品编号 Number of samples</td></tr><tr><td>青贮前Pre-ensiling</td><td>青贮前1</td><td>青贮前2</td><td>青贮前3</td></tr><tr><td>青贮后 Post-ensiling</td><td>青贮后1</td><td>青贮后2</td><td>青贮后3</td></tr></table></body></html>

青贮前：玉米秸秆青贮原料。青贮后：发酵45d后的玉米秸秆青贮饲料。下表同。

Pre-ensiling: stuff of corn stalk silage.Post-ensiling: corn stalk silage of 45 d.The same as below.

# 1.3 测定项目与方法

1.3.1感观鉴定按德国农业协会（DLG）感官青贮评分标准及等级评定方法进行综合评定[9-10]。

# 1.3.2发酵品质及营养成分的测定

取玉米秸秆青贮前及青贮后样品 $2 0 \mathrm { g }$ ，加入 $1 8 0 \mathrm { m L }$ 蒸馏水，搅拌均匀，用组织捣碎机搅碎 $1 ~ \mathrm { m i n }$ ，先后用4层纱布和定性滤纸过滤，滤出草渣得到浸出液，再用pH测定仪测青贮料浸出液的 $\mathsf { p H } ^ { [ 1 1 ] }$ ；采用苯酚-次氯酸钠比色法测定氨态氮（ammonia nitrogen， $\mathrm { N H } _ { 3 }$ -N）含量[12]；采用烘箱干燥法测定干物质（drymatter，DM）含量；采用凯氏定氮法测定粗蛋白质（crude protein，CP）和总氮（total nitrogen，TN）含量[13]；采用范氏洗涤纤维法测定中性洗涤纤维（neutral detergent fiber，NDF）和酸性洗涤纤维（acid detergent fiber，ADF）含量[13];采用蒽酮分光光度法测定可溶性糖（water soluble carbohydrates，WSC）含量[14]；使用SHIMADZE-10A型高效液相色谱分析乳酸（lactic acid，LA）、乙酸（acetic acid，AA）、丙酸（propionic acid，PA）、丁酸（butyric acid，BA）含量，色谱柱：Shodex Rspak KC-811 S-DVB gel Column $3 0 \mathrm { m m } \times 8 \mathrm { m m }$ ，检测器：SPD-M10AVP，流动相：3mmol/L高氯酸，流速：1 mL/min；柱温 $5 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ，检测波长 $2 1 0 \mathrm { n m }$ ，进样量 $5 \mu \mathrm { L } ^ { [ 1 0 ] }$ 。

# 1.3.3 微生物种类及丰度的测定

# 1.3.3.1 DNA的提取

青贮原料及样品 DNA 的提取采用十二烷基苯磺酸钠（SDS）法[15]。称取 $0 . 5 \mathrm { g }$ 青贮原料及样品，加 $3 ~ \mathrm { m L }$ 磷酸盐缓冲液（PBS）（ $( 8 \mathrm { g N a C l }$ ，0.2 g KCL， $2 . 8 \ \mathrm { g \ N a _ { 2 } H P O _ { 4 } \cdot 1 2 H _ { 2 } O }$ ，0.2g $\mathrm { K H _ { 2 } P O _ { 4 } }$ ，加蒸馏水定容至 $^ { \mathrm { ~ 1 ~ L ~ } }$ ， $\mathrm { p H } 7 . 0 { \sim } 7 . 4 \rangle$ ，涡旋 $1 5 ~ \mathrm { m i n }$ ， $1 \ 7 9 0 \times g$ 室温离心 $5 ~ \mathrm { m i n }$ ，弃上清，向沉淀中再加入 $3 ~ \mathrm { m L }$ PBS，重复上述步骤2次。向沉淀中加 $1 ~ \mathrm { m L }$ 抽提缓冲液(50mmol/L Tris-HCI， 5 mmol/L EDTA, $3 \%$ SDS, $\mathrm { p H } 8 . 0 \AA$ ， $1 6 0 0 0 \times g .$ ， $4 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 离心 $5 \mathrm { m i n }$ ，取上清加入等体积异丙醇， $- 2 0 \mathrm { ~ \textdegree C }$ 沉淀1h， $1 2 \ 0 0 0 \ \mathrm { r / m i n }$ 、 $4 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 离心 $2 0 ~ \mathrm { m i n }$ ，弃上清，加入 $70 \%$ 乙醇洗涤沉淀，室温干燥沉淀 $5 ~ \mathrm { m i n }$ ，加入 $3 0 ~ \mu \mathrm { L }$ 蒸馏水重溶核酸，-20℃保存备用。采用琼脂糖凝胶电泳检测DNA的纯度和浓度，取适量的样品于离心管中，使用无菌水稀释样品至1 ng/μL。

# 1.3.3.2 定量PCR检测

PCR 扩增：稀释后的基因组DNA 为模板；测序区域 16SV4区，引物为 515F 5-GTGCCAGCMGCCGCGG-3和 806R 5-GGACTACHVGGGTWTCTAAT- $\cdot 3 ^ { \prime [ 1 6 ] }$ 。PCR反应体系为 $3 0 \mu \mathrm { L }$ ：Phusion?高保真PCRmix（新英格兰生物实验室） $1 5 \mu \mathrm { L }$ ，上、下游引物各 $0 . 2 \mu \mathrm { m o l / L }$ 以及 $1 0 \mathrm { n g }$ 的DNA 模板，加去离子水至终体积为 $3 0 \mu \mathrm { L } ^ { \left[ 1 7 \right] }$ 。PCR反应程序为：98 $\mathrm { { } ^ { \circ } C }$ 预变性1 min，98℃变性 $1 0 \mathrm { ~ s ~ }$ ，30个循环， $5 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 退火 $3 0 ~ \mathrm { s }$ ，72℃延伸 $6 0 ~ \mathrm { s }$ ， $7 2 \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ }$ 延伸 $5 \mathrm { m i n }$ 。

PCR产物的混样和纯化：PCR产物使用 $2 \%$ 浓度的琼脂糖凝胶进行电泳检测；根据PCR产物浓度进行等浓度混样，充分混匀后使用 $2 \%$ 的琼脂糖凝胶电泳检测 PCR 产物，使用Thermo Scientific 公司的Gene JET 胶回收试剂盒回收产物[18]。

# 1.3.3.3文库构建和测序

由北京诺禾致源生物信息科技有限公司测定。使用 New England Biolabs 公司的 NEBNext?UltraTM DNALibrary Prep Kit for Ilumina 建库试剂盒进行文库的构建，构建好的文库经过Qubit 定量和文库检测，合格后，使用MiSeq 高通量测序技术进行上机测序[7-8]。

# 1.3.3.4信息分析流程

使用CLUSTALW软件分析，序列相似性大于 $9 7 \%$ 时定义为相同的操作分类单元(operational taxonomic units，OTUs)。测序得到的原始数据(raw data)，存在一定比例的干扰数据(dirtydata)，为了使信息分析的结果更加准确、可靠，首先对原始数据进行拼接、过滤，得到有效数据(clean data)。然后基于有效数据进行OTUs 聚类和物种分类分析，并将 OTUs和物种注释结合，从而得到每个样品的OTUs和分类谱系的基本分析结果。再对OTUs 进行丰度、多样性指数等分析，同时对物种注释在各个分类水平上进行群落结构的统计分析[8]。

# 1.4 数据统计分析

试验数据采用SPSS19.0软件分析。玉米秸秆各样品的相异系数使用ANOVA程序进行差异显著性分析，门、纲、目、科和属各个水平上菌群丰度，玉米秸秆发酵品质和营养成分指标使用独立样本T-test过程进行均值差异显著性分析， $P { < } 0 . 0 5$ 为差异显著。

# 2 结果与分析

# 2.1玉米秸秆青贮饲料感官评定

青贮发酵 45d后的玉米秸秆青贮饲料3个重复的样品均呈黄绿色，在色泽上无明显差别；无霉变情况发生；质地较好，无粘手现象，呈酸香味。各样品的感官评定质量均达到了优良等级。

# 2.2玉米秸秆青贮前后发酵品质及营养成分

由表2可知，青贮发酵作用能够使玉米秸秆 $\mathsf { p H }$ 迅速降低 ( $\cdot < 0 . 0 5$ )，乳酸含量显著增加（ $\scriptstyle P < 0 . 0 5$ )，NDF、ADF及CP含量有下降趋势（ $P { > } 0 . 0 5$ )，而DM含量在青贮前后差异不显著 （ $\mathrm { P } { > } 0 . 0 5 \mathrm { ) }$ ，另外可知青贮发酵过程会消耗玉米秸秆中的WSC含量。

# 表2玉米秸秆青贮前后发酵品质及营养成分

Table 2The fermentation quality and nutrient composition of corn stalk of pre-ensiling and post  

<html><body><table><tr><td colspan="5">ensiling</td></tr><tr><td>项目Items</td><td>青贮前 Pre-ensiling</td><td>青贮后 Post-ensiling</td><td>均值标准 误</td><td>P值</td></tr><tr><td colspan="3"></td><td>SEM</td><td>P-value</td></tr><tr><td>发酵品质 Fermentation quality</td><td></td><td></td><td></td><td></td></tr><tr><td>pH</td><td>5.23</td><td>3.86</td><td>0.56</td><td>0.005</td></tr><tr><td>乳酸LA/(g/kg DM)</td><td>6.13</td><td>67.63</td><td>3.14</td><td>0.042</td></tr><tr><td>乙酸 AA/(g/kg DM)</td><td>1.99</td><td>15.88</td><td>1.64</td><td>0.039</td></tr><tr><td>丙酸 PA/(g/kg DM)</td><td>0.00</td><td>1.72</td><td>0.06</td><td>0.132</td></tr><tr><td>丁酸 BA/(g/kg DM)</td><td>0.00</td><td>0.00</td><td></td><td></td></tr><tr><td>氨态氮/总氮 AN/TN/(g/kg)</td><td>14.98</td><td>61.19</td><td>5.61</td><td>0.037</td></tr><tr><td>营养成分 Nutrient composition</td><td></td><td></td><td></td><td></td></tr><tr><td>干物质DM/(g/kg FM)</td><td>315.8</td><td>316.5</td><td>23.64</td><td>0.463</td></tr><tr><td>碳水化合物 WSC/(g/kg DM)</td><td>90.20</td><td>13.98</td><td>5.41</td><td>0.023</td></tr></table></body></html>

<html><body><table><tr><td>中性洗涤纤维 NDF/(g/kg DM)</td><td>629.61</td><td>582.31</td><td>30.65</td><td>0.902</td></tr><tr><td>酸性洗涤纤维 ADF/(g/kg DM)</td><td>357.17</td><td>322.21</td><td>21.06</td><td>0.646</td></tr><tr><td>粗蛋白质 CP/(g/kg DM)</td><td>81.18</td><td>75.59</td><td>4.97</td><td>0.089</td></tr></table></body></html>

# 2.3玉米秸秆青贮前后微生物种类及丰度变化

# 2.3.1 测序质量

经过过滤后6个样品得到总拼接序列数（total tags）为490251条，用于构建OTUs 别并且活动分类信息的Tags数目（taxon tags）为476217条，有效Tags数目达到 $9 7 . 1 4 \%$ 。序列相似性大于97%的水平上，总检测到OTUs数为7258个。由图1可知，各样品的稀释曲线均已趋于平坦，说明测序深度基本可以反映样品中绝大多数的微生物信息。相同序列数时，青贮前玉米秸秆菌群多样性高于青贮后样品，说明青贮发酵能够降低玉米秸秆菌群多样性。

![](images/771a314b69f89931195b1b040002ddcc177111814c4abf860142d31cb4cf73ba.jpg)  
图1青贮前后玉米秸秆菌群稀释曲线  
Fig.1Rarefaction cure of corn stalk microflora of pre-ensiling and post-ensiling

2.3.2 青贮前后玉米秸秆物种多样性相似性分析

由图2可知，青贮前和青贮后玉米秸秆共有OTUs为575个，青贮前特有OTUs为 832  
个，青贮后特有OTUs为161个，说明青贮前后菌群构成同时具有特异性和相似性。由表3

可知，玉米秸秆青贮前和青贮后2个组组内样品差异系数小，组间差异系数大，说明组样品重复性好，青贮前后玉米秸秆物种多样性存在明显差异。

![](images/ed3f165fa92fcb10713264565e835985104c8359fbe1337ff41790601abb800e.jpg)  
图2青贮前后玉米秸秆OTUs韦恩图  
Fig.2Venn graph of corn stalk OTUs of pre-ensiling and post-ensiling

# 表3玉米秸秆青贮前后菌落多样性相异系数

Table 3 Coefficient of dissimilar in corn stalk microflora diversity of pre-ensiling and post  
  

<html><body><table><tr><td colspan="7">ensiling</td></tr><tr><td>项目Items</td><td>青贮前1 Pre-ensiling 1</td><td>青贮前2 Pre-ensiling 2</td><td>青贮前3 Pre-ensiling 3</td><td>青贮后1 Post-ensiling 1</td><td>青贮后2 Post-ensiling 2</td><td>青贮后3 Post-ensiling 3</td></tr><tr><td>青贮前1Pre-</td><td>0.00</td><td>0.07</td><td>0.02</td><td>0.32</td><td>0.25</td><td>0.34</td></tr><tr><td>ensiling 1 青贮前2Pre-</td><td>0.07</td><td>0.00</td><td>0.08</td><td>0.29</td><td>0.22</td><td>0.30</td></tr><tr><td>ensiling 2 青贮前3Pre-</td><td>0.12</td><td>0.08</td><td>0.00</td><td>0.26</td><td>0.18</td><td>0.27</td></tr><tr><td>ensiling 3 青贮后1Post-</td><td>0.32</td><td>0.29</td><td>0.26</td><td>0.00</td><td>0.09</td><td>0.06</td></tr><tr><td>ensiling 1 青贮前2 Post-</td><td>0.25</td><td>0.22</td><td>0.18</td><td>0.09</td><td>0.00</td><td>0.11</td></tr><tr><td>ensiling 2 青贮前3Post-</td><td>0.34</td><td>0.30</td><td>0.27</td><td>0.06</td><td>0.11</td><td>0.00</td></tr><tr><td>ensiling 3 均值标准误</td><td>0.04</td><td>0.04</td><td>0.04</td><td>0.03</td><td>0.04</td><td>0.04</td></tr><tr><td>SEM P值P-value</td><td>0.005</td><td>0.004</td><td>0.018</td><td>0.002</td><td>0.021</td><td>0.003</td></tr></table></body></html>

# 2.3.3 不同组样品在各个水平上优势菌群的异同

由表4可知，在门水平上，玉米秸秆中变形菌门（Proteobacteria）和厚壁菌门

（Fimicules）菌群数量在青贮前占优势地位。青贮 $4 5 \mathrm { d }$ 后，变形菌门菌群数量显著降低（ $\scriptstyle P < 0 . 0 5 ,$ ，由 $78 . 0 8 \%$ 降低至 $5 0 . 9 0 \%$ ，厚壁菌门菌群数量显著增加（ $\scriptstyle P < 0 . 0 5 { \mathrm { , } }$ ，由$1 8 . 7 6 \%$ 增加至 $4 4 . 0 6 \%$ 。

# 表4青贮前后玉米秸秆门水平上菌群结构

Table 4Bacterial composition of pre-ensiling and post-ensiling corn stalk by phylum $\%$   

<html><body><table><tr><td>门Phylum</td><td>青贮前 Pre-ensiling</td><td>青贮后</td><td>均值标准误</td><td>P值</td></tr><tr><td>变形菌门 Proteobacteria</td><td>78.08</td><td>Post-ensiling 50.90</td><td>SEM 5.16</td><td>P-value 0.006</td></tr><tr><td>厚壁菌门Firmicutes</td><td>18.76</td><td>44.06</td><td>4.11</td><td>0.004</td></tr><tr><td>蓝菌门 Cyanobacteria</td><td>0.96</td><td>2.45</td><td>2.09</td><td>0.514</td></tr><tr><td>拟杆菌门 Bacteroidetes</td><td>1.77</td><td>1.74</td><td>0.30</td><td>0.928</td></tr><tr><td>放线菌门 Actinobacteria</td><td>0.37</td><td>0.76</td><td>0.05</td><td>0.001</td></tr><tr><td>无壁菌门Tenericutes</td><td>0.00</td><td>0.02</td><td>0.00</td><td>0.011</td></tr><tr><td>疣微菌门Verrucomicrobia</td><td>0.02</td><td>0.01</td><td>0.01</td><td>0.325</td></tr><tr><td>Armatimonadetes</td><td>0.01</td><td>0.01</td><td>0.00</td><td>0.076</td></tr><tr><td>WYO</td><td>0.00</td><td>0.00</td><td></td><td></td></tr><tr><td>Thermi</td><td>0.00</td><td>0.02</td><td>0.00</td><td>0.842</td></tr><tr><td>其他 Others</td><td>0.03</td><td>0.03</td><td>0.00 0.00</td><td>0.073 0.394</td></tr></table></body></html>

由表5可知，在纲水平上， $\gamma$ -变形菌纲（Gammaproteobacteria）、芽孢杆菌纲

（Bacilli）和α-变形菌纲（Alphaproteobacteria）菌群数量在青贮前玉米秸秆中占据前3位。青贮45d后， $\gamma$ -变形菌纲菌群数量显著降低（ $\scriptstyle P < 0 . 0 5 .$ ，由 $67 . 7 2 \%$ 降低到 $3 5 . 6 6 \%$ 。芽孢杆菌纲菌群数量显著增加（ $\cdot P { < } 0 . 0 5 )$ ，由 $1 8 . 6 8 \%$ 增加至 $4 3 . 9 4 \%$ 。α-变形菌纲菌群数量由$8 . 9 8 \%$ 增加至 $1 3 . 3 9 \%$ ，显著上升（ $\cdot P { < } 0 . 0 5 )$ 。

表5青贮前后玉米秸秆纲水平上菌群结构  
Table 5Bacterial composition of pre-ensiling and post-ensiling corn stalk by class $\%$   

<html><body><table><tr><td>纲Class</td><td>青贮前 Pre-ensiling</td><td>青贮后 Post-ensiling</td><td>均值标准误 SEM</td><td>P值</td></tr><tr><td>Y-变形菌 Gammaproteobacteria</td><td>67.72</td><td>35.66</td><td>6.16</td><td>P-value</td></tr><tr><td>芽孢杆菌纲Bacilli</td><td>18.68</td><td>43.94</td><td>4.10</td><td>0.006 0.004</td></tr><tr><td>α -变形菌纲 Alphaproteobacteria</td><td>8.98</td><td>13.39</td><td>1.46</td><td>0.039</td></tr><tr><td>Chloroplas</td><td>0.95</td><td>2.45</td><td>2.09</td><td>0.513</td></tr><tr><td>变形菌纲Betaproteobacteria</td><td>1.27</td><td>1.70</td><td>0.41</td><td>0.356</td></tr><tr><td>鞘氨醇杆菌纲 Sphingobacteriia</td><td>1.51</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>0.89</td><td>0.28</td><td>0.087</td></tr></table></body></html>

<html><body><table><tr><td>Flavobacteriia</td><td>0.24</td><td>0.83</td><td>0.04</td><td>0.000</td></tr><tr><td>放线菌纲 Actinobacteria</td><td>0.37</td><td>0.76</td><td>0.04</td><td>0.001</td></tr><tr><td>柔膜菌纲Mollicutes</td><td>0.00</td><td>0.02</td><td>0.00</td><td>0.011</td></tr><tr><td>梭菌纲 Clostridia</td><td>0.08</td><td>0.12</td><td>0.03</td><td>0.180</td></tr><tr><td>其他 Others</td><td>0.19</td><td>0.24</td><td>0.04</td><td>0.260</td></tr></table></body></html>

由表6可知，在目水平上，玉米秸秆青贮前肠杆菌目(Enterobacteriales)和乳杆菌目(Lactobacillales)菌群数量占据优势地位。青贮45d后，肠杆菌目菌群数量显著降低（ $P <$ 0.05)，乳杆菌目菌群数量显著增加（ $\cdot P { < } 0 . 0 5 )$ 。

Table 6Bacterial composition of pre-ensiling and post-ensiling corn stalk by order $0 \%$   

<html><body><table><tr><td>目Order</td><td>青贮前 Pre-ensiling</td><td>青贮后</td><td>均值标准误</td><td>P值</td></tr><tr><td>肠杆菌目 Enterobacteriales</td><td>58.11</td><td>Post-ensiling 43.89</td><td>SEM</td><td>P-value</td></tr><tr><td>乳杆菌目Lactobacillales</td><td></td><td></td><td>7.44</td><td>0.018 0.003</td></tr><tr><td>假单胞菌目Pseudomonadales</td><td>18.64 6.21</td><td>30.18</td><td>4.09</td><td>0.013</td></tr><tr><td>鞘脂单胞菌目Sphingomonadales</td><td></td><td>5.37</td><td>0.99</td><td></td></tr><tr><td>黄单胞菌目 Xanthomonadales</td><td>2.90</td><td>4.69</td><td>0.94</td><td>0.013</td></tr><tr><td>根瘤菌目Rhizobiales</td><td>2.26</td><td>3.17</td><td>1.16</td><td>0.213</td></tr><tr><td>Streptophyta</td><td>1.77</td><td>3.24</td><td>0.86</td><td>0.025</td></tr><tr><td>红螺菌目 Rhodospirillales</td><td>0.95</td><td>0.93</td><td>2.09</td><td>0.513</td></tr><tr><td>伯克氏菌目Burkholderiales</td><td>3.72</td><td>2.52</td><td>0.43</td><td>0.003</td></tr><tr><td>鞘脂杆菌目 Sphingobacteriales</td><td>1.25</td><td>1.60</td><td>0.41</td><td>0.345</td></tr><tr><td>其他 Others</td><td>1.51 2.67</td><td>1.41 3.01</td><td>0.28 0.31</td><td>0.087 0.180</td></tr></table></body></html>

由表7可知，在科水平上，青贮前玉米秸秆中菌群数量占前3位的分别是肠杆菌科（Enterobacteriaceae），明串珠菌科（Leuconostocaceae）和假单胞菌科（Pseudomonadaceae），青贮45d后，菌群数量占前3位的分别为乳杆菌科（Lactobacillaceae）、肠杆菌科和明串珠菌科。肠杆菌科和明串珠菌科菌群数量显著降低（ $\cdot P { < } 0 . 0 5 \$ )，乳杆菌科菌群数量显著增加（ $\cdot P$ $< 0 . 0 5 )$ 。

表6青贮前后玉米秸秆目水平上菌群结构  
表7青贮前后玉米秸秆科水平上菌群结构  
Table 7Bacterial composition of pre-ensiling and post-ensiling corn stalk by family $\%$   

<html><body><table><tr><td>科Family</td><td>青贮前</td><td>青贮后</td><td>均值标准误</td><td>P值</td></tr><tr><td></td><td>Pre-ensiling</td><td>Post-ensiling</td><td>SEM</td><td>P-value</td></tr><tr><td>肠杆菌科 Enterobacteriaceae</td><td>58.11</td><td>29.30</td><td>7.44</td><td>0.018</td></tr></table></body></html>

<html><body><table><tr><td>乳杆菌科 Lactobacillaceae</td><td>1.12</td><td>32.40</td><td>3.24</td><td>0.001</td></tr><tr><td>明串珠菌科 Leuconostocaceae</td><td>17.07</td><td>10.33</td><td>2.15</td><td>0.035</td></tr><tr><td>假单胞菌科 Pseudomonadaceae</td><td>5.76</td><td>1.65</td><td>0.84</td><td>0.008</td></tr><tr><td>鞘脂单胞菌科 Sphingomonadaceae</td><td>2.88</td><td>6.87</td><td>0.94</td><td>0.013</td></tr><tr><td>Xanthomonadaceae</td><td>2.26</td><td>3.97</td><td>1.16</td><td>0.214</td></tr><tr><td>醋酸杆菌科 Acetobacteraceae</td><td>3.67</td><td>0.85</td><td>0.44</td><td>0.003</td></tr><tr><td>根瘤菌科 Rhizobiaceae</td><td>0.70</td><td>1.56</td><td>0.38</td><td>0.088</td></tr><tr><td>Methylobacteriaceae</td><td>0.21</td><td>1.46</td><td>0.15</td><td>0.001</td></tr><tr><td>莫拉菌科 Moraxellaceae</td><td>0.45</td><td>0.37</td><td>0.15</td><td>0.591</td></tr><tr><td>其他 Others</td><td>7.76</td><td>11.26</td><td>2.78</td><td>0.278</td></tr></table></body></html>

由表8可知，在属水平上，青贮前玉米秸秆中菌群数量占前3位的分别是魏斯氏菌(weissella)、鞘氨醇菌（Sphingomonas）和Swaminathania属，分别为 $1 6 . 9 2 \%$ $2 . 2 6 \%$ 和 $2 . 2 2 \%$ 。青贮45d后菌群数量占前3位的分别为片球菌（Pediococcus）、魏斯氏菌和乳杆菌属（Lactobacillus），分别为 $2 2 . 6 5 \%$ ， $9 . 9 8 \%$ 和 $9 . 7 4 \%$ 。青贮后片球菌和乳杆菌菌群数量显著增加（ $\cdot P { < } 0 . 0 5 )$ ，魏斯氏菌属菌群数量显著降低（ $\cdot P { < } 0 . 0 5 \$ ）°

表8青贮前后玉米秸秆属水平上菌群结构  
Table 8Bacterial composition of pre-ensiling and post-ensiling corn stalk by genus   

<html><body><table><tr><td rowspan="2">属Genus</td><td>青贮前</td><td>青贮后</td><td>均值标准误</td><td>P值</td></tr><tr><td>Pre-ensiling</td><td>Post-ensiling</td><td>SEM</td><td>P-value</td></tr><tr><td>片球菌属Pediococcus</td><td>1.05</td><td>22.65</td><td>2.73</td><td>0.001</td></tr><tr><td>魏斯氏菌属Weissella</td><td>16.92</td><td>9.98</td><td>2.14</td><td>0.032</td></tr><tr><td>乳杆菌属Lactobacillus</td><td>0.07</td><td>9.74</td><td>0.53</td><td>0.000</td></tr><tr><td>鞘氨醇菌属Sphingomonas</td><td>2.26</td><td>5.48</td><td>0.71</td><td>0.010</td></tr><tr><td>嗜菌属Stenotrophomonas</td><td>1.59</td><td>2.85</td><td>0.95</td><td>0.257</td></tr><tr><td>假单胞菌属Pseudomonas</td><td>1.95</td><td>0.35</td><td>0.50</td><td>0.033</td></tr><tr><td>Swaminathania</td><td>2.22</td><td>0.40</td><td>0.37</td><td>0.008</td></tr><tr><td>不动杆菌属 Acinetobacter</td><td>0.45</td><td>0.37</td><td>0.15</td><td>0.592</td></tr><tr><td>Hymenobacter</td><td>1.14</td><td>0.17</td><td>0.17</td><td>0.005</td></tr><tr><td>欧文氏菌属Erwinia</td><td>1.13</td><td>0.13</td><td>0.30</td><td>0.030</td></tr><tr><td>其他 Others</td><td>71.21</td><td>47.88</td><td>4.70</td><td>0.008</td></tr></table></body></html>

# 3讨论

我国是世界上农作物秸秆生产量最大的国家之一，2010年全国秸秆理论资源量为8.4亿t，可收集资源量约为7亿t，其中，玉米秸秆资源量最大，约为2.43亿t，占秸秆可收集资源量的 $34 . 7 \% \%$ 。有研究报道玉米秸秆经过青贮处理后，玉米秸秆不仅能保持青绿饲料的青鲜状态，具有明显的酸甜芳香气味，与玉米秸秆相比饲料中的粗蛋白质含量可增加 $3 . 3 \% \sim$ $1 6 . 4 \%$ ，粗纤维含量降低 $5 \% \sim 1 5 \% ^ { [ 2 0 - 2 1 ] }$ 。本研究发现，经过青贮发酵45d后的玉米秸秆青贮饲料均呈黄绿色，在色泽上无明显差别，无霉变情况发生，质地较好，无粘手现象，呈酸香味。另外，青贮发酵作用能够使玉米秸秆NDF及ADF 含量有下降趋势，与其相符。而本研究中，玉米秸秆青贮后CP含量有下降趋势，与其不符，原因可能是玉米秸秆青贮后 $\mathrm { N H } _ { 3 }$ N含量由 $1 4 . 9 8 ~ \mathrm { g / k g \ T N }$ 上升到61.19 g/kg TN，从而消耗了部分粗蛋白质。

本研究通过MiSeq高通量测序发现，玉米秸秆在青贮后，菌落种类仅为青贮前的$5 2 . 3 1 \%$ ，其中共有菌种仅占玉米秸秆青贮前菌种数量的 $40 . 8 7 \%$ 。青贮发酵能够改变青贮饲料中群落结构及丰度，原因可能是青贮制作时会将空气排出形成一个封闭系统，为菌落的繁殖提供无氧环境，另外玉米秸秆中所含的可溶性糖等物质能够为菌落的繁殖提供底物，使得有益细菌迅速繁殖，降低青贮料pH，从而影响青贮过程中细菌群落的构成[22]。青贮发酵不仅改变了玉米秸秆的品质，同时改变了其菌落构成，这说明二者之间存在着巨大的相关性。

玉米秸秆中菌群数量占绝对优势的两个门为厚壁菌门和变形菌门。经过青贮发酵后，厚壁菌门菌群数量由 $1 8 . 7 6 \%$ 增加至 $4 4 . 0 6 \%$ ，厚壁菌门是原核生物系统进化树低GC含量的革兰氏阳性菌，主要有产芽孢、非产芽孢和支原体菌群，很多芽孢杆菌可以降解多种大分子化合物，如纤维素、淀粉、蛋白质等[2]。而玉米秸秆青贮后 NDF、ADF及CP含量均有下降趋势，由此可推断青贮饲料中纤维素及蛋白质等营养物质含量的部分变化可能是由厚壁菌门细菌引起的。变形菌门是革兰氏阴性细菌，是细菌中最大的一门，包括很多病原菌，如大肠杆菌、沙门氏菌、弧菌和螺杆菌等种类[23]。青贮饲料中的肠道细菌尽管被认为不属于致病菌，但因其会与乳酸菌竞争性利用糖类物质，同时降解蛋白质，产生影响青贮口味的毒素生物胺，并阻碍青贮饲料pH的降低。另外在青贮环境下肠道细菌还能将硝酸盐转化为亚硝酸盐[24]。而经过青贮发酵变形菌门菌群数量显著降低，由此可见，玉米秸秆中WSC 含量显著降低除部分被乳酸菌所利用外，有部分是被变形菌门细菌所利用，而青贮后CP含量的下降趋势和 $\mathrm { N H } _ { 3 ^ { - } } \mathrm { N }$ 含量的增加也与其有着密不可分的关系。另外，在纲、目和科水平上，同样发现青贮前玉米秸秆中占据绝对优势地位的含致病菌较多的 $\gamma$ -变形菌纲、肠杆菌目和肠杆菌科菌群数量均显著降低，而经过青贮发酵后芽孢杆菌纲、乳杆菌目和乳杆菌科菌群数量显著增加，这说明青贮过程改善玉米秸秆颜色、气味、质地、发酵品质以及营养成分的同时，可以有效降低有害细菌的数量，增加有益菌的数量，从而可以降低致病菌对家畜健康存在的潜在风险，改善家畜健康。

Cai等[25]从各个时期的水稻青贮中分离到了161株乳酸菌，根据形态和DNA序列分析，将这些菌株分类为乳球菌属、乳杆菌属、明串珠菌属、肠球菌属、片球菌属和魏斯氏菌属，这些菌株主要为同型发酵乳酸菌，占总数的 $6 6 \%$ 。Duniere 等[3]认为，玉米青贮中主要的细菌种类分别为类芽孢杆菌（Paenibacillus）、黄杆菌（Flavobacteriaceae）、鞘氨醇单胞菌、微小杆菌（Exiguobacterium）、根瘤菌、不动杆菌（Acinetobacter）和 Buchnera 菌。在本试验中，青贮后玉米秸秆上菌群数量为前10位的，分别是是片球菌、魏斯氏菌、乳杆菌属、鞘氨醇菌属、嗜菌属（Stenotrophomonas）、Swaminathania属、不动杆菌、假单胞菌属（Pseudomonas）、Hymenobacter属和欧文氏菌属（Erwinia）。研究结果的差异可能是由于细菌种类检测手段、试验样品、发酵时间和发酵方式等不同造成的。前人研究发现，青贮饲料发酵初期，片球菌起着非常重要的作用，植物原料在收获制作成青贮饲料后，最先进行发酵的是粪链球菌(Streptococcus faecalis)和肠膜明串珠菌(Leuconostoc mesenteroides)，接着被更耐酸的菌株，如植物乳杆菌(Lactobacillus plantarum)、短乳杆菌(Lactobacillus brevis)和布氏乳杆菌(Lactobacillus buchneri)等取代[26]。张想峰等[27]认为在青贮发酵后期起主要作用的是乳酸杆菌。杨杨等[28]认为，魏斯氏菌在青贮饲料发酵初期起重要作用，且在提高青贮饲料品质方而作用较小。本研究发现，玉米秸秆青贮45d后，片球菌菌群数量由 $1 . 0 5 \%$ 增加至 $2 2 . 6 5 \%$ 魏斯氏菌属菌群数量由 $1 6 . 9 2 \%$ 降低到 $9 . 9 8 \%$ ，乳杆菌属菌群数量由 $0 . 0 7 \%$ 增加至 $9 . 7 4 \%$ ，这说明片球菌和乳杆菌在青贮过程中繁殖迅速，发挥着重要作用。而魏斯氏菌属菌群数量青贮初期较高，青贮后期数量下降，说明其可能是在青贮初期发挥作用较大，与杨杨等[28]观点一致。与前人研究相比，采用Miseq高通量平台测序不仅能够确定整个菌落的构成，避免传统微生物鉴定方法只能反映出样品少数优势菌的信息，无法对样品中的微生物做到绝对定量的劣势，体现其极大的优越性。本试验仅对Miseq高通量平台测序技术对玉米秸秆青贮饲料青贮前后菌群结构及丰度进行了初步的摸索，而不同处理、品种、青贮时间等因素均可能对微生物种类产生影响，本课题组相关研究正在开展中。

# 4结论

$\textcircled{1}$ 玉米秸秆经过青贮发酵后颜色黄绿，质量良好，具有酸香味；pH迅速降低，乳酸含量显著增加，NDF及ADF含量有下降趋势。$\textcircled{2}$ 玉米秸秆经过青贮发酵后变形菌门、 $\gamma$ -变形菌纲、肠杆菌目、肠杆菌科、魏斯氏菌属菌群数量显著降低，厚壁菌门、芽孢杆菌纲、乳杆菌目、乳杆菌科、片球菌属和乳杆菌属菌群数量显著增加。$\textcircled{3}$ 通过实验室检测手段及Miseq高通量测序技术相结合，能够在分析青贮品质的同时，提供青贮前后整个菌落构成及丰度变化的信息，进而为发酵过程的调控提供依据。  
参考文献：  
[1]张慧杰.饲草青贮微生物菌群动态变化与乳酸菌的鉴定筛选[D].硕士学位论文.北京:中国农业科学院,2011.  
[2]杨文琦,龙宣杞,崔卫东.玉米青贮中细菌多样性分析[J].新疆农业科学,2013,50(8):1424-1433.  
[3] DUNIERE L,SINDOU J,CHAUCHEYRAS-DURAND F,et al.Silage processing and

strategies to prevent persistence of undesirable microorganisms[J].Animal Feed Science and Technol0gy,2013,182(1/2/3/4):1-15.

[4] SANTOS A O,AVILA C L S,SCHWAN R F.Selection of tropical lactic acid bacteria for enhancing the quality of maize silage[J].Journal of Dairy Science,2013,96(12):7777-7789.

[5]程银华,雷雪芹,徐廷生,等.揉丝微贮与传统青贮秸秆的微生物组成与营养成分分析[J].家畜生态学报，2013,34(4):41-44.

[6]李旭娇,玉柱.苜蓿青贮饲料中优良乳酸菌菌株的筛选[J].中国奶牛,2014(11-12):37-40.

[7] DEGNAN P H,OCHMAN H.Ilumina-based analysis of microbial community diversity[J].The ISME Journal,2012,6(1):183-194.

[8] CAPORASO J G,LAUBER C L,WALTERS W A,et al.Ultra-high-throughput microbial communityanalysison the Ilumina HiSeq andMiSeqplatforms[J].TheISME Journal,2012,6(8):1621-1624.

[9]张子仪.中国饲料学[M].北京:中国农业出版社,2000:194-201.

[10]玉柱,陶莲,陈燕,等.添加玉米秸秆对两种三叶草青贮品质的影响[J].中国奶牛,2009(4):15-18.

[11]HAN K J,COLLINS M,VANZANT E S,et al.Bale density and moisture effects on alfalfa round bale silage[J].Crop Science,2004,44(3):914-919.

[12] BRODERICK G A,KANG JH.Automated simultaneous determination of ammonia and total amino acids in ruminal fluid and in vitro media[J].Journal of Dairy Science,1980,63(1):64-75.

[13]张丽英.饲料分析及饲料质量检测技术[M].北京:中国农业大学出版社,2002:53-56,70-74.

[14] OWENS V N,ALBRECHT K A,MUCK R E,et al.Protein degradation and fermentation characteristics of red clover and alfalfa silage harvested with varying levels of total nonstructural carbohydrates[J].Crop Science,1999,39(6):1873-1880.

[15]BOKULICH N A,SUBRAMANIAN S,FAITH J J,et al.Quality-filtering vastly improves diversity estimates from Ilumina amplicon sequencing[J].Nature Methods,2O13,1O(1): 57-59.

[16]YOUSSEF N,SHEIK C S,KRUMHOLZ L R,et al.Comparison of species richness estimates obtained using nearly complete fragments and simulated pyrosequencing-generated fragments in16SrRNA Gene-Basedenvironmental surveys[J].Applied and Environmental Microbiology,2009,75(16):5227-5236.

[17]HESS M,SCZYRBA A,EGAN R,et al.Metagenomic discovery of Biomass-Degrading genes and genomes from cow rumen[J].Science,2011,331(6016):463-467.

[18]LUO C,TSEMENTZI D,KYRPIDES N,et al.Direct comparisons of Ilumina vs.Roche 454 sequencing technologies on the same microbial community DNA sample[J].PLoS One,2012,7(2):e30087.

[19]YUAN X F,LI P P,WANG H,et al.Enhancing the anaerobic digestion of corn stalks using composite microbial pretreatment[J].Journal of Microbiology and Biotechnology,2011,21(7):746-752.

[20] XUE F,ZHOU Z M,REN L P,et al.Influence of rumen-protected lysine supplementation on growth performance and plasma amino acid concentrations in growing cattle offered the maize stalk silage/maize grain-based diet[J].Animal Feed Science and Technology,2011,169(1/2):61-67.

[21] WANG R J,SUN Y H,ZHANG S T,et al.Two-step pretreatment of corn stalk silage for increasingsugarsproduction and decreasing the amount of catalyst[J].Bioresource Technology,2012,120:290-294.

[22]隋鸿园,侯成立,周雨霞.适合作青贮接种剂植物乳杆菌的筛选[J].饲料研究,2012(12):68-69.

[23]闫绍鹏,杨瑞华,冷淑娇,等.高通量测序技术及其在农业科学研究中的应用[J].中国农学通报,2012,28(30):171-176.

[24]李泽青,闫峻,张永芳,等.青贮发酵过程中主要微生物的活动规律及控制[J].广东畜牧兽医科技,2011,36(6):12-15.

[25]CAI Y M,SUYANANDANA P,SAMAN P,et al.Classification and characterization of lactic acid bacteria isolated from the intestines of common carp and freshwater prawns[J].Journal of General and Applied Microbiology,1999,45(4):177-184.

with paddy rice silage as determined by 16S ribosomal DNA analysis[J].Applied and Environmental Microbiology,2003,69(1):444-451.

[27] 张想峰,艾尼瓦尔·艾山,买热木尼沙·吾甫尔,等.新疆小芦苇青贮中乳酸杆菌的分离鉴定[J].新疆农业科学,2009,46(6):1327-1331.

[28]杨杨,石超,郭旭生.高寒草甸魏斯氏乳酸菌的分离鉴定及理化特性研究[J].草业学 报,2014,23(1):266-275.

# Effects of Ensiling on Quality and Bacteria Composition of Corn Stalk

TAO Lian DIAO Qiyu\*

(Key Laboratory ofFeed Biotechnology of the Ministry ofAgriculture, Feed Research Institute of Chinese Academy of Agricultural Sciences, Beijing 10o081, China)

Abstract: The objective of the present study was to investigate the effect of ensiling process of corn stalk silage on its sensory indicators, fermentation quality, nutrition composition and bacteria composition and abundance in phylum, class, order, family and genus. Green and dough stage corn stalk without ear was chopped to 1 to $2 \mathrm { c m }$ with water content of $6 5 \%$ to $70 \%$ . Each three samples were collcted and packaged by vacuum packager in polyethylene bags before and after ensiling process. After being stored at room temperature for 45 days,changes of the silage quality and bacteria composition were analyzed using laboratory testing methods and MiSeq sequencing technology. The results showed as follows: 1) the corn silage was yellow-green and had the good texture and smell after ensiling 45 days. The pH was rapidly increased ( $\scriptstyle ( P < 0 . 0 5$ ), the lactic acid content was significantly increased ( $\scriptstyle \cdot < 0 . 0 5$ ,while the content of neutral detergent fiber (NDF) and acid detergent fiber (ADF) had the downward trend ( $\mathrm { ( } P \mathrm { > } 0 . 0 5 \mathrm { ) }$ ). 2)After ensiling of corn silage, the numbers of Proteobacteria plylum，Gammaproteobacteria class,Enterobacterialesorder, Enterobacteriaceae family and Weissella genus were significantly decreased ( $\lceil P { < } 0 . 0 5 \rangle$ ,while the numbers of Firmicutes phylum, Bacilli class,Lactobacillales order, Lactobacillaceae family, and Pediococcus and Lactobacillus genus were significantly increased ( $\scriptstyle ( P < 0 . 0 5 )$ ; 3) Ensiling process could improve the sensory indicators,fermentation quality, nutrition composition with effectively reducing the amount of harmful bacteria and increasing the number of beneficial bacteria, which can reduce the potential risk to animal health pathogens exist. In conclusion, combing laboratory testing methods and MiSeq sequencing technology can provide the information of silage quality and the composition and abundance of bacteria, which can provide the basis for the regulation of the fermentation process.

Key words: MiSeq; corn stalk; ensiling; quality; bacteria