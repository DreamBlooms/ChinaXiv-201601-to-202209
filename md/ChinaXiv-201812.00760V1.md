# 降解不同牧草的瘤胃细菌群落多样性研究

徐　俊l²邬磊1\* 陈庆隆」胡丽芳」侯玉洁2,3赵国琦²孙建勇4吴斯骏1\*\*周瑶敏1\*\*

（1.江西省农业科学院，南昌 330200；2.扬州大学动物科学与技术学院，扬州 225009；3.南昌市农业科学院，南昌330008；4.新疆阿勒泰市第一牧场畜牧兽医站，阿勒泰 836500）摘要：本试验旨在通过高通量测序技术研究降解不同牧草的瘤胃细菌群落多样性。选择苜蓿、燕麦草、羊草和稻草为试验材料，分别将其粉碎后称取 $3 . 0 \ \mathrm { g }$ 放入尼龙袋投入瘤胃中，降解 24h后全部取出，洗净后提取总DNA，根据Miseq 高通量测序要求进行样品制备和上机分析。结果表明：1）属水平上，序列比对得到91个属，4种牧草上的优势菌属均为丁酸弧菌属、普雷沃氏菌属、纤维杆菌属和密螺旋体属。2）基于UniFrac 的加权主坐标分析，其第一主成分和第二主成分的贡献率分别为 $5 2 . 8 9 \%$ 和 $1 9 . 4 3 \%$ 。3）苜蓿、燕麦草、羊草和稻草中操作分类单元（OTU）数目分别为5778、6984、5220 和6018，4组牧草共享2913个OTU，占细菌总OTU数目的 $3 2 . 3 8 \%$ 。综合得出，4种不同牧草在相同降解时间下的微生物群落结构多样性存在明显差异。

关键词：牧草；细菌群落；高通量测序中图分类号：S816

反刍动物瘤胃中栖息着大量细菌、真菌和原虫等微生物，牧草纤维可在瘤胃微生物作用下降解为挥发性脂肪酸进而为机体供能，因此，深入研究纤维降解的微生物机制对于反刍动物高效利用牧草资源具有十分重要的意义。不同牧草的组织结构存在差异，其中豆科牧草（如苜蓿）主要由易降解的厚角组织、绿色组织和韧皮部组成，而禾本科牧草（如燕麦草和羊草）和稻草秸秆主要由厚壁组织、薄壁组织、维管束和韧皮部等组成，研究发现，微生物对细胞壁的吸附和降解与牧草组织结构及其类型密切相关1。在降解纤维的瘤胃微生物中，细菌在纤维降解过程中起决定性作用，尤其是与牧草紧密吸附的细菌[2]。黄色瘤胃球菌（Ruminococcus flavefaciens，R. flavefaciens）、白色瘤胃球菌（Ruminococcus albus，R.albus）和产琥珀酸丝状杆菌（Fibrobacter succinogenes,F.succinogenes）是3种主要纤维降解菌[3-5],有研究表明,细菌可以快速附着于黑麦草表面，且在薄壁组织和韧皮部中的细菌吸附量最多，尤其是黄色瘤胃球菌[]。Akin 等[7通过电子显微镜技术发现降解羊茅草和鸭茅草的纤维降解菌中有 $70 \%$ 是 $F .$ succinogenes 和R.flavefaciens。Koike 等[8]通过竞争性PCR研究了绵羊中 3种主要纤维降解菌对鸭茅茎秆的吸附和降解情况，培养 $5 \mathrm { m i n }$ 后发现， $F .$ succinogenes 和其他2种球菌（R.flavefaciens和R.albus）的数量可达茎秆干物质（DM）含量的 $1 0 ^ { 5 }$ 和 $1 0 ^ { 4 }$ 个/g， $2 4 \mathrm { h }$ 时 $F .$ succinogenes 和 $R .$ flavefaciens 的数量达到峰值，分别为茎秆DM含量的 $1 0 ^ { 9 }$ 和$1 0 ^ { 7 }$ 个/g，而 $R$ albus在 $4 8 \mathrm { h }$ 达到峰值，为茎秆DM含量的 $1 0 ^ { 6 }$ 个/g。然而，前人多集中在对几种主要纤维降解菌数量变化的研究[]，且研究手段多为显微镜技术和荧光定量PCR 技术等，有关高通量测序手段对嵌在牧草细胞壁内部的细菌群落结构多样性的研究鲜有报道。因此，本文选择我国奶牛场常用的苜蓿、燕麦草、羊草和稻草为研究对象，通过尼龙袋试验借助 Miseq 高通量测序技术从微生物群落结构多样性的角度探究不同牧草中纤维降解菌的差异，为进一步深入探索饲草降解率差异形成的原因和饲粮对瘤胃菌群的形成机理提供一定的理论基础。

# 1材料与方法

# 1.1 试验动物和饲养管理

选取3头安装有永久性瘤胃瘘管的健康、干奶期荷斯坦奶牛 $[ ( 6 0 0 \pm 1 5 ) \mathrm { k g } ]$ 根据 NRC（2001）3倍维持需要的营养标准，饲喂主要由玉米、豆粕、玉米青贮和稻草秸秆组成的全混合日粮（TMR），采集饲料样品放入 $6 5 \mathrm { ~ ~ \ } ^ { \circ } \mathrm { ~ C ~ }$ 烘箱中烘干$^ { 4 8 \mathrm { ~ h ~ } }$ ，测定初水分，然后过40目筛，测定样品粗蛋白质（CP）、粗脂肪（EE）、有机物（OM）[10]、粗灰分（Ash）、中性洗涤纤维（NDF）和酸性洗涤纤维（ADF）[]含量，非纤维性碳水化合物（NFC）含量可通过计算[非纤维性碳水化合物$( \% ) { = } 1 0 0 \cdot$ （粗蛋白质 $+$ 中性洗涤纤维 $^ +$ 粗脂肪 $+$ 粗灰分）]得出。钙（Ca）和磷（P）含量采用电感耦合等离子体原子发射光谱法测定[10]，饲粮组成及营养水平如表1所示，采用拴系式饲养，日喂2次，自由饮水表1饲粮组成及营养水平 (干物质基础)

Table1 Composition and nutrient levels of the diet（DM basis） %   

<html><body><table><tr><td>项目Items</td><td>含量Content</td></tr><tr><td colspan="2">原料 Ingredients</td></tr><tr><td>稻草秸秆 Rice straw</td><td>15.00</td></tr><tr><td>玉米青贮 Corn silage</td><td>35.00</td></tr><tr><td>全棉籽 Whole cottonseed</td><td>5.00</td></tr><tr><td>玉米 Corn 豆粕 Soybean meal</td><td>21.00</td></tr><tr><td>玉米干酒糟及其可溶物 Corn DDGS</td><td>10.00</td></tr><tr><td>磷酸氢钙 CaHPO4</td><td>10.00</td></tr><tr><td>食盐 NaCl</td><td>1.30</td></tr><tr><td></td><td>0.60</td></tr><tr><td>碳酸氢钠 NaHCO3</td><td>1.00</td></tr><tr><td>预混料 Premix1)</td><td>0.60</td></tr><tr><td>石粉 Limestone</td><td>0.50</td></tr><tr><td>合计 Total</td><td>100.00</td></tr><tr><td>营养水平 Nutrient levels2)</td><td></td></tr><tr><td>粗蛋白质CP</td><td>14.34</td></tr><tr><td>粗脂肪 EE</td><td>4.14</td></tr><tr><td>中性洗涤纤维NDF</td><td>37.87</td></tr><tr><td>粗灰分 Ash</td><td>8.78</td></tr><tr><td>非纤维性碳水化合物 NFC</td><td>34.78</td></tr><tr><td>钙Ca</td><td>0.66</td></tr><tr><td>磷P</td><td>0.38</td></tr></table></body></html>

1 每千克预混料含有 One kilogram of premix contained the follwing: VA 400 000 IU，VD 80 $0 0 0 \mathrm { I U }$ ，V $\mathrm { ~ E ~ } 2 ~ 0 0 0 \mathrm { ~ I U }$ ， $Z { \mathrm { n } } 5 0 0 0 { \mathrm { m g } }$ ，Se $4 0 \mathrm { m g }$ ， $\mathrm { M n } 2 0 0 0 \mathrm { m g }$ ，Fe $2 0 0 0 \mathrm { m g }$ ，Co $2 0 \mathrm { m g }$ ，Cu 1 （20 $2 0 0 \mathrm { m g }$ ， $\mathrm { ~ I ~ } 5 0 \ : \mathrm { m g }$ 。 2）营养水平为实测值。Nutrient levels were measured values.

# 1.2 试验材料

试验选用试验基地种植的长势和株高相近的初花期紫花苜蓿、抽穗初期燕麦草和羊草以及收割后的稻草，从根部切割后去掉叶子和叶鞘，剥离出茎秆作为试验材料。

# 1.3 试验方法

将4种牧草样品放入65℃烘箱中烘 $4 8 \mathrm { h }$ ，测定初水分，然后过40目筛，测定样品粗蛋白质、粗脂肪、有机物、中性洗涤纤维和酸性洗涤纤维含量，计算非纤维性碳水化合物含量。然后分别称取 $3 . 0 \ \mathrm { g }$ 粉碎好的苜蓿、燕麦草、羊草和稻草样品（ $2 \mathrm { m m }$ 筛）放入尼龙袋（8$\mathrm { c m } { \times } 1 2 \mathrm { c m }$ ，网孔孔径300目）中，每种牧草称取6份，每头牛2个重复，于晨饲前将 24个尼龙袋分别投放到3头奶牛瘤胃中，同时将尼龙绳栓在瘘管盖上固定，降解 $2 4 \mathrm { h }$ 后取出所有尼龙袋，放入冰水中停止发酵，分别将相同牧草的2个重复样品混合均匀，然后用冷水冲洗直到流出的水澄清为止，放入 ${ } ^ { - 8 0 } { } ^ { \circ } { \mathrm { C } }$ 低温冰箱（BCD-208KACJN，青岛海尔股份有限公司）保存。

测样时将牧草在冰上解冻，利用OMEGA试剂盒（M2327-02）提取总DNA，取经液氮粉碎的植物组织放入 $1 . 5 \mathrm { m L }$ 灭菌离心管中，立即加入己内酰胺（CPL）缓冲液涡旋，然后放入65℃水浴孵育 $1 5 \mathrm { m i n }$ ，加入氯仿：异戊醇（24:1）混合液，高速涡旋后高速离心，吸取上清液，依次加入核糖核酸酶、CXD 缓冲液、无水乙醇，涡旋15 s后转入吸附柱中离心，然后丢弃收集管和收集液，将吸附柱转入第2个新的收集管中，加入无水乙醇稀释、离心，再加入无水乙醇冲洗缓冲液、离心，将吸附柱转入一个新的 $1 . 5 ~ \mathrm { m L }$ 离心管中，加入预先预热的双蒸水孵育，离心 $3 \mathrm { m i n }$ ，将DNA洗脱后收集。对提取好的DNA样品用核酸蛋白分析仪（DU640，美国 Backman 公司）测定260 和 $2 8 0 \mathrm { n m }$ 处的吸光度值以及DNA 浓度，用 $1 \%$ 的琼脂糖凝胶通过电泳仪（DYY-6C 电泳仪，北京六一仪器厂）进行DNA质量检测。

根据细菌16SrDNA的V3区保守序列，设计通用引物338F： $5 ^ { \prime }$ -ACTCCTACGGGAGGCAGCAG- $\cdot 3 ^ { \prime }$ ，533R $5 ^ { \prime }$ -TTACCGCGGCTGCTGGCAC- $\cdot 3 ^ { \prime }$ ，PCR扩增采用 $2 5 \mu \mathrm { L }$ 反应体系： $2 . 5 \mu \mathrm { L } 1 0 { \times } \mathrm { P C R }$ Buffer， $1 \mu \mathrm { L }$ 引物（各 $1 0 \mathrm { \ : \mu m o l / L }$ ）， $2 \mu \mathrm { L }$ dNTP Mix（2.5 mmol/L）， $0 . 1 2 5 \mu \mathrm { L }$ DNA聚合酶（ ${ 5 . 0 } \mathrm { U / \mu L }$ ）， $2 0 \mathrm { n g { D N A } }$ 模板， $\mathrm { \ d d H _ { 2 } O }$ 补齐。反应程序为： $9 4 ^ { \circ } \mathrm { C }$ 预变性 $5 \mathrm { m i n }$ ; $9 4 ^ { \circ } \mathrm { C }$ 变性 $3 0 ~ \mathrm { s }$ ， $5 8 ^ { \circ } \mathrm { C }$ 退火 $3 0 ~ \mathrm { s }$ ， $7 2 ^ { \circ } \mathrm { C }$ 延伸 $3 0 ~ \mathrm { s }$ ，进行21个循环，最后 $7 2 ^ { \circ } \mathrm { C }$ 延伸 $5 \mathrm { m i n }$ ，结束后 $4 ^ { \circ } \mathrm { C }$ 保存。PCR 扩增产物用 $1 . 5 \%$ 琼脂糖凝胶电泳进行检测，然后使用 Axygen DNA 胶回收纯化试剂盒（Axy Prep DNA Gel Extration kit，AP-GX-500）对V3区扩增产物进行切胶回收纯化，经Biotek酶标仪（FLX800，美国伯腾仪器有限公司）对纯化好的PCR产物进行定量，为防止多样品混合测序容易产生不均一现象，需按测序要求将每一个待测样品进行等量混匀形成均一混合物，PCR混合物经质量控制后，采用标准的 Illumina TruSeq DNA文库制备流程构建 Ilumina 测序文库，最后按照 Ilumina Miseq 平台

上机进行 Barcoded Illumina Miseq 测序。

# 1.4 数据处理与分析

对原始序列数据进行质量控制得到有效序列，丢弃长度短于 $1 2 0 ~ \mathrm { b p }$ 、含有模糊碱基，引物碱基含2个以上的错配信息、单个碱基重复数超过6个的序列，获得优质序列。根据序列相似度为 $9 7 \%$ 的原则，将序列归为多个操作分类单元（operational taxonomicunit，OTU），并对序列进行聚类分析。

对生成的OTU信息进行细菌群落丰富度和多样性分析，其中丰富度指数用Chao1指数和 Ace 指数表示，多样性指数用 Shannon指数和 Simpson 指数表示，Shannon指数值越大，说明群落多样性越高，Simpson 指数值越大，说明群落多样性越低。在属水平上做聚类Heatmap 图，同时对微生物群落进行UniFrac 分析，比较不同牧草间的群落差异性。

# 1.5 统计分析

数据采用Excel2007进行整理，结果采用 SAS9.0 统计软件的PDIFF 模块进行方差分析和显著性检验，以 $P { < } 0 . 0 5$ 和 $P { < } 0 . 0 1$ 作为差异显著和极显著判断标准。

# 2 结果与分析

# 2.1 牧草营养水平

表2所示为4种牧草的营养水平，结果表明不同牧草的营养水平存在一定的差异，4种牧草的干物质和有机物含量相当，但是苜蓿的粗蛋白质含量则远远高于燕麦草、羊草和稻草，而苜蓿的中性洗涤纤维和粗纤维含量则比禾本科的燕麦草、羊草和稻草要低。

表2牧草营养水平(干物质基础)  
Table 2Ingredient composition of four forage（DMbasis）  

<html><body><table><tr><td>项目Items</td><td>干物质</td><td>有机物</td><td>粗蛋白质</td><td>中性洗涤纤维</td><td>粗纤维</td></tr><tr><td></td><td>DM</td><td>OM</td><td>CP</td><td>NDF</td><td>Ash</td></tr><tr><td>苜蓿Alfalfa</td><td>89.12</td><td>91.25</td><td>17.88</td><td>43.22</td><td>22.65</td></tr><tr><td>燕麦草 Oat hay</td><td>88.01</td><td>88.89</td><td>5.89</td><td>67.58</td><td>28.14</td></tr><tr><td>羊草Leymus chinensis</td><td>90.42</td><td>89.01</td><td>5.54</td><td>69.25</td><td>29.36</td></tr><tr><td>稻草 Rice straw</td><td>91.06</td><td>89.12</td><td>4.96</td><td>71.12</td><td>34.23</td></tr></table></body></html>

# 2.2 菌群结构丰富度和多样性

测序后，本研究12个测试样品共产生591378条有效序列，经质量控制后得到562727条高质量序列，平均序列长度为 $1 6 1 ~ \mathrm { b p }$ 。不同牧草降解过程中的菌群结构丰富度和多样性结果如表3所示。物种丰富度指数Chao 指数为 $5 6 0 3 { \sim } 7 2 9 3$ ，Ace 指数为 $7 4 5 5 { \sim } 9 7 9 2$ ，各组间 Chao 指数和 Ace 指数均差异不显著（ $P { > } 0 . 0 5$ ）。不同牧草对物种多样性指数Simpson指数有极显著影响（ ${ \scriptstyle \cdot } P { < } 0 . 0 1 { \scriptstyle \cdot }$ ），且苜蓿的 Simpson 指数最高，极显著高于其他牧草( $_ { \cdot P < 0 . 0 1 } )$ ;羊草的 Simpson 指数最低，极显著低于其他牧草（ $\scriptstyle \cdot - 0 . 0 1$ ）。这表明附着在不同牧草上的细菌多样性不同，且羊草物种多样性最高，首蓿最低。各组文库覆盖率均在 $94 \%$ 以上，说明每个样品测序量合理，可以很好地反映牧草中细菌群落种类和结构多样性。

表3不同牧草降解过程中的菌群结构丰富度和多样性结果  
Table 3Results of richiness and diversity of flora in process of different forages degradation   

<html><body><table><tr><td rowspan="2">项目 Items</td><td colspan="5">羊草</td><td rowspan="2">P值 P-value</td></tr><tr><td>苜蓿 Alfalfa</td><td>燕麦草 Oat hay</td><td>Leymus chinensis</td><td>稻草 Rice straw</td><td>SEM</td></tr><tr><td>Chao 指数 Chao index</td><td>6135</td><td>7293</td><td>5 603</td><td>5 700</td><td>884</td><td>0.54</td></tr><tr><td>Ace 指数 Ace index</td><td>8366</td><td>9 792</td><td>7455</td><td>7476</td><td>1052</td><td>0.41</td></tr><tr><td>Simpson 指数 Simpson index</td><td>0.019 4Aa</td><td>0.016 9Bb</td><td>0.012 5Cc</td><td>0.0151Bb</td><td>0.000 8</td><td><0.01</td></tr><tr><td>Shannon 指数 Shannon index</td><td>5.793 7</td><td>5.802 7</td><td>5.912 1</td><td>5.898 3</td><td>0.033 2</td><td>0.07</td></tr></table></body></html>

同行数据肩标不同小写字母表示差异显著（ $P { < } 0 . 0 5$ ），不同大写字母表示差异极显著（ $\scriptstyle P < 0 . 0 1$ ），相同或无字母表示差异不显著（ $P { > } 0 . 0 5$ ）。下表同。

In the same row, values with different small letter superscripts mean significant difference （20 $_ { ( P < 0 . 0 5 ) }$ ，and with different capital letter superscripts mean significant difference $( P { < } 0 . 0 1 )$ ， while with the same or no letter superscripts mean no significant difference $( P { > } 0 . 0 5 )$ .The same as below.

# 2.3 细菌组成和群落结构

在属水平上，序列比对得到的91个菌属中共有11个菌属的相对含量大于 $0 . 1 \%$ （表4），而其他鉴定出的菌属相对含量均较低，这表明吸附在牧草中的细菌含有很多相对丰度较低的菌属。在相对含量大于 $0 . 1 \%$ 的菌属中，不同牧草中均以丁酸弧菌属（Butyrivibrio）、普雷沃氏菌属（Prevotella）、纤维杆菌属（Fibrobacter）和密螺旋体属（Treponema）为优势菌属，且Butyrivibrio和Prevotella所占比例较高，分别占总序列的 $8 . 8 8 \% \sim 1 2 . 3 0 \%$ 和 $7 . 0 1 \% \sim$ $9 . 2 9 \%$ ，不同牧草对上述菌属存在极显著影响（ $_ { \cdot  { P } < 0 . 0 1 }$ ）。

表4基于细菌属水平相对含量大于 $0 . 1 \%$ （序列所占比例）的不同牧草比较分析  
Table 4Comparative analysis ofrelative abundance above $0 . 1 \%$ (percentage of sequences) under the bacterial genus level in different forages   

<html><body><table><tr><td>属</td><td>苜蓿</td><td>燕麦草</td><td>羊草</td><td>稻草</td><td>SEM</td><td>P值</td></tr><tr><td>Genus 丁酸弧菌属</td><td>Alfalfa</td><td>Oat hay</td><td>Leymus chinensis</td><td>Rice straw</td><td></td><td>P-value</td></tr><tr><td>Butyrivibrio</td><td>12.30Aa</td><td>9.44Bb</td><td>8.88Cc</td><td>9.80Bb</td><td>0.27</td><td><0.01</td></tr><tr><td>普雷沃氏菌属 Prevotella</td><td>9.29Aa</td><td>7.01Bb</td><td>9.17Aa</td><td>9.16Aa</td><td>0.25</td><td><0.01</td></tr><tr><td>密螺旋体属</td><td>3.81Cc</td><td>4.96Bb</td><td>7.01Aa</td><td>5.12Bb</td><td>0.29</td><td><0.01</td></tr><tr><td>Treponema 纤维杆菌属</td><td>3.38Bc</td><td>7.27Aa</td><td>6.14Ab</td><td>4.62Bb</td><td></td><td></td></tr><tr><td>Fibrobacter</td><td></td><td></td><td></td><td></td><td>0.40</td><td><0.01</td></tr><tr><td>瘤胃球菌属</td><td>1.82Bc</td><td>2.10Bb</td><td>2.53Aa</td><td>1.97Bb</td><td>0.03</td><td><0.01</td></tr><tr><td>Ruminococcus</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>厌氧原体属</td><td>0.81Aa</td><td>0.24Cc</td><td>0.42Bb</td><td>0.38Bb</td><td>0.02</td><td><0.01</td></tr><tr><td>Anaeroplasma</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>新月形单胞菌属</td><td>0.80Aa</td><td>0.16Cc</td><td></td><td></td><td></td><td></td></tr><tr><td>Selenomonas</td><td></td><td></td><td>0.22Cc</td><td>0.58Bb</td><td>0.03</td><td><0.01</td></tr><tr><td>解琥珀酸菌属</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.80a</td><td>0.68b</td><td>0.74b</td><td>0.83a</td><td>0.03</td><td>0.02</td></tr><tr><td>Succiniclasticum</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>毛螺旋菌属</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.75Bb</td><td>0.32Dd</td><td>0.45Cc</td><td>1.01Aa</td><td>0.02</td><td><0.01</td></tr><tr><td>Lachnobacterium</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>琥珀酸弧菌属</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.56Bb</td><td>0.32Cd</td><td>0.44Bb</td><td>0.99Aa</td><td></td><td></td></tr><tr><td>Succinivibrio</td><td></td><td></td><td></td><td></td><td>0.02</td><td><0.01</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>厌氧弧菌属</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Anaerovibrio</td><td>0.25Aa</td><td>0.12Bc</td><td>0.16Bb</td><td>0.29Aa</td><td>0.02</td><td><0.01</td></tr></table></body></html>

# 2.4 组间的相似性分析

通过颜色梯度及相似程度来反映不同牧草组在各分类水平上群落组成的相似性和差异性，图例不同颜色代表不同牧草组OTU 的相对丰度比例，由图1可知，12个样品共分成了2大簇，每个大簇下面又有4小簇，每小簇均为同一牧草的6个样品，这说明相同牧草3个平行样附着的细菌群落结构十分相似，可以很好地聚在一起，而不同牧草间群落结构存在明显差异。

![](images/58a99f599aecad597b4fe746a73f2a4a816aef5ade78db627490c0462e4e3d24.jpg)  
图1属水平下12个牧草样品聚类分析热图  
Fig.1Cluster analysis heat map under genus level of 12 forage samples

在本研究中，我们利用UniFrac的加权主坐标分析（PCoA）对降解不同牧草的细菌群落结构差异进行了研究，它是通过系统进化距离来衡量样品间距离，用于表征细菌群落结构的差异大小，PCoA可以将这种差异显示在二维或三维空间的PCoA图上，因此，图中距离越近的点表示2个样品的菌群结构越相似。由图2可知，基于UniFrac 的PCoA其第一主成分和第二主成分的贡献率分别为 $5 2 . 8 9 \%$ 和 $1 9 . 4 3 \%$ ，不同牧草间细菌群落结构差异明显，但相同牧草的3个样品可以很好地聚在一起，菌群相似度很高。

![](images/9335b63034521d066e933cc1d8f44b08b45cf9d46d02029edee2c20a5a8dd3e4.jpg)  
图2 $9 7 \%$ 相似性水平下12个牧草样品菌群结构Unifrac的加权主坐标分析图

Fig.2Principal coordinate analysis (PCoA) scores plot generated by UniFrac analysis at the $9 7 \%$ similarity level

of the 12 forage samples

通过统计不同牧草组中共有和独有的OTU数目，在 $9 7 \%$ 相似性水平下，4个组共产生8997个OTU，如图3所示，其中苜蓿、燕麦草、羊草和稻草中OTU数目分别为5778、6 984、5 220 和6018，4种牧草共享了2913个OTU，占细菌总OTU数目的 $3 2 . 3 8 \%$ ，苜蓿、燕麦草、羊草和稻草中独有的OTU数目分别为 $6 . 0 7 \%$ 、 $10 . 6 1 \%$ 、 $4 . 8 5 \%$ 和 $6 . 8 8 \%$ ，其顺序为燕麦草 $>$ 稻草 $>$ 苜蓿 $\mathrm { > }$ 羊草。由此可见，吸附在不同牧草上的细菌共享了约1/3的OTU，且不同牧草中存在一定比例独有的OTU。

![](images/7f3f5d6ad461058015112b71d05dd4edc5a49428ef6e353c3d8833bb1a920735.jpg)  
图3不同牧草组细菌群落共享和独有的OUT数目的Venn图分析

Fig.3Venn diagram analysis of OTU number shared and unique ofbacterial community among different forage

序列比对后发现，Butyrivibrio、Prevotella、Treponema 和Fibrobacter 是牧草中的优势菌属，这与饲喂上述4种牧草的奶牛其瘤胃液中的优势菌属种类相一致[12]。尽管不同牧草的优势菌属在种类上没有差异，但不同牧草组间细菌相对含量存在显著或极显著差异，这主要是因为不同牧草的营养组分、组织结构和吸附的微生物种类不同造成的，不同微生物会对不同底物产生不同的响应[12-13]。Butyrivibrio 是厚壁菌门（Firmicutes）中主要的纤维分解菌属，它们在纤维分解中发挥了重要作用，研究表明 Butyrivibrio 可以利用纤维素、淀粉和其他多聚糖为发酵底物，且苜蓿显著高于其他3种牧草，这可能与苜蓿中可发酵碳水化合物含量高于禾本科的燕麦草、羊草和稻草密切相关。Prevotella 中拥有高活性的半纤维素分解菌[14],并对植物非纤维多糖和蛋白质的降解至关重要[15]，Butyrivibrio 加上Prevotella 在苜蓿（ $2 1 . 5 9 \%$ ）中所占的比例明显高于燕麦草（ $1 6 . 4 5 \%$ ）、羊草（ $1 8 . 0 5 \%$ ）和稻草（ $1 8 . 9 6 \%$ ），这可能与苜蓿中的蛋白质和可发酵碳水化合物含量高有关，但这有待于进一步开展研究证实。尽管 Ruminococcus 和Fibrobacter 在瘤胃中丰度低于 Butyrivibrio 和Prevotella，但它们在牧草纤维的降解中也发挥了重要作用。除此之外，本研究中还发现多达80 种低丰度菌属，尽管丰度较低，但分泌的纤维素酶活或许很高，如真杆菌属（Eubacterium）、假丁酸弧菌属（Pseudobutyrivibrio）和颤螺旋菌属（Oscillbacter）等菌属，它们在纤维降解过程中发挥着重要作用[16]。

微生物可以快速吸附于细胞壁表面，但细胞壁降解速率及其程度受微生物与底物黏附程度、饲料理化特性和瘤胃消化动力学等因素的影响[17]。对不同底物（黑麦草叶、黑麦草茎和稻草秸秆）在山羊瘤胃 $2 4 \mathrm { h }$ 内微生物吸附的研究表明，吸附在不同纤维底物上的微生物在瘤胃降解前6h无显著差异，细菌总数在6h后逐渐稳定；变性梯度凝胶电泳（DGGE）图谱表明，底物在降解12和 $2 4 \mathrm { h }$ 后的微生物群落结构与降解6h后的微生物群落结构存在显著差异，这充分说明不同底物吸附的微生物会随时间的不同发生改变[18]。对吸附的微生物进行克隆文库的研究还发现Treponema 只在苜蓿样品中发现，在果园草中未发现[8]，然而，本研究中苜蓿等4种牧草中均能发现存在Treponema，该结果与果园草中的结论存在差异，这可能与本试验中使用的牧草品种、试验动物和饲喂饲粮等因素不同有关。研究发现细菌可在$1 5 \mathrm { m i n }$ 内快速吸附于黑麦草细胞壁中，且黄色瘤胃球菌更喜欢吸附在黑麦草叶的表皮、薄壁组织和韧皮部边缘[19]。以羊茅草和鸭茅草为底物的研究表明，吸附在牧草中的微生物大多是产琥珀酸丝状杆菌和黄色瘤胃球菌[7,20],它们占细菌总数的 $0 . 1 \% { \sim } 6 . 6 \%$ 和 $1 . 3 \% { \sim } 2 . 9 \% ^ { [ 2 1 . 2 3 ] }$ 上述结果与本研究中禾本科草(燕麦、羊草和稻草）的瘤胃球菌属含量均高于豆科草（苜蓿)的结果相一致，这可能与禾本科草中的纤维素含量高于苜蓿有关，研究发现瘤胃球菌属可发酵纤维素及其水解产物纤维二糖，而苜蓿草中的纤维素含量仅占 $2 2 . 6 5 \%$ ，均低于燕麦草、羊草和稻草。定植不同底物中的微生物细菌形态相似，但微生物数量显著不同，微生物数量在 $2 4 \mathrm { h }$ 时达到峰值，其中以杆球菌(Rod cocci),双球菌(Diplococci)和螺旋体门（Spirochaetes）含量最多[24]，这也是本研究中选择牧草降解 $2 4 \mathrm { h }$ 后取出进行微生物群落结构研究分析的原因。

从不同牧草细菌群落结构相似性的研究结果表明，12个样品在聚类分析热图中分为两大簇，4组不同牧草的3个样品又聚成小簇，由此可见，相同牧草的3个重复样品之间的微生物降解菌的群落结构十分相似，而不同牧草之间存在明显差异，这与细菌在属水平上各组间存在显著或极显著差异的结果相一致。与此同时，同为禾本科草的燕麦草和羊草最终聚成一大簇，这说明降解禾本科草的细菌群落结构更相似，这可能与燕麦草和羊草的细胞壁结构组成和营养成分相似有密切关系[25-26]，由表2中可以发现，燕麦草和羊草的粗蛋白质( $5 . 8 9 \%$ VS. $5 . 5 4 \%$ ）、中性洗涤纤维（ $67 . 5 8 \%$ VS. $6 9 . 2 5 \%$ ）和粗纤维（ $2 8 . 1 4 \%$ VS.29.36%）含量均相近，营养组分和细胞壁结构的相近可能是导致燕麦草和羊草中细菌群落结构相似的主要原因[12]。首蓿和稻草聚成了一大簇，它们之间的细菌群落结构更相似，这与先前通过扫描电镜和干物质降解率的研究发现苜蓿和稻草的降解存在相似性的结论相吻合[1,27]。在考虑物种丰度的UniFrac 的PCoA图中，4组牧草样品能够很好地分隔开，这与聚类分析热图的结果相一致。

# 4小结

通过高通量测序技术对降解4种牧草中的细菌群落结构差异性研究表明，4种不同牧草在相同降解时间下附着的微生物群落结构多样性存在明显差异。在属水平上，降解纤维的优势菌属主要是 Butyrivibrio、Prevotella、Fibrobacter 和 Treponema。

# 参考文献：

[1] 徐俊,侯玉洁,赵国琦,等.瘤胃微生物对苜蓿茎降解特性及超微结构的影响[J].动物营养学报,2014,26(3):776-782.

MCALLISTER T A,BAE H D,JONES G A,et al.Microbial attachment and feed digestion in the rumen[J].Journal of Animal Science,1994,72(11):3004-3018.

KOIKE S,KOBAYASHI Y.Development and use of competitive PCR assays for the rumen cellulolyticbacteria:Fibrobactersuccinogenes,Ruminococcusalbusand Ruminococcus flavefaciens[J].FEMS Microbiology Letters,2006,204(2):361-366.

[4] KRAUSE D O,DENMAN S E,MACKIE R I,et al.Opportunities to improve fiber degradation in the rumen:microbiology,ecology and genomics[J].FEMS Microbiology Reviews,2006,27(5):663-693.

TAJIMA K,AMINOV R I,NAGAMINE T,et al.Diet-dependent shifts in the bacterial population of the rumen revealed with real-time PCR[J].Applied and Environmental Microbiology,2001,67(6):2766-2774.

6] EDWARDS JE,HUWS S A,KIM E J,et al.Characterization of the dynamics of initial bacterial colonization ofnonconserved forage in the bovine rumen[J].FEMS Microbiology Ecology,2007,62(3):323-335.

[7] AKIN D E.Evaluation by electron microscopy and anaerobic culture of types of rumen bacteria associated with digestion of forage cell walls[J].Applied and Environmental Microbiology,1980,39(1):242-252.

8] KOIKE S,PAN J,KOBAYASHI Y,et al.Kinetics of in sacco fiber-attachment of representative ruminal cellulolytic bacteria monitored by competitive PCR[J].Journal of Dairy Science,2003,86(4):1429-1435.

[9] GHASEMI S,NASERIAN A A,VALIZADEH R,et al.Partial and total substitution of alfalfa hay by pistachio byproduct modulated the counts of selected cellulolytic ruminal bacteria attached to alfalfa hay in sheep[J].Livestock Science,2012,150(1/2/3):342-348.

[10]AOAC.Oficial methods of analysis[M].[s.n.]:Washington,D.C.,1980.

[11] VAN SOEST P J,ROBERTSON J B,LEWIS B A.Methods for dietary fiber,neutral detergent fiber,and nonstarch polysaccharides in relation to animal nutrition[J].Journal of Dairy Science,1991,74(10):3583-3597.

[12]徐俊.不同牧草来源的 NDF 在瘤胃中降解特性及其对细菌群落结构的影响[D].博士学位论文.扬州：扬州大学,2014

[13]刘艺端,余凯凡,朱伟云.食物主要成分与动物肠道微生物组成及其代谢的关系[J].世界华人消化杂志,2016,24(5):706-713.

[14] MATSUI H,OGATA K,TAJIMA K,etal.Phenotypiccharacterizationof polysaccharidases produced by four Prevotella type strains[J].Current Microbiology,2000,41(1):45-49.

[15] TAJIMA K,AMINOV R I,NAGAMINE T,et al.Rumen bacterial diversity as determined by sequence analysis of 16S rDNA libraries[J].FEMS Microbiology Ecology,1999,29(2):159-169.

16] EVANS N J,BROWN J M,MURRAY R D,et al.Characterization of novel bovine gastrointestinal tract Treponema isolates and comparison with bovine digital dermatitis treponemes[J].Applied and Environmental Microbiology,2011,77(1):138-147.

VARGA G A,KOLVER E S.Microbial and animal limitations to fiber digestion and utilization[J].The Journal of Nutrition,1997,127(5):819S-823S.

[18]

SUN Y Z,MAO S Y,YAO W,et al.DGGE and 16S rDNA analysis reveals a highly diverse and rapidly colonising bacterial community on different substrates in the rumen of goats[J].Animal,2008,2(3):391-398.

[19] LATHAM M J,BROOKER B E,PETTIPHER G L,et al.Adhesion of Bacteroides succinogenes in pure culture and in the presence of Ruminococcus flavefaciens to cell walls in leaves of perennial ryegrass (Lolium perenne)[J].Applied and Environmental Microbiology,1978,35(6):1166-1173.

[20] CHENG K J,STEWART C S,DINSDALE D,et al.Electron microscopy of bacteria involved in the digestion of plant cell walls[J].Animal FeedScienceand

Technology,1984,10(2/3):93-120.

[21] BRIESACHER S L,MAY T,GRIGSBY K N,et al.Use of DNA probes to monitor nutritional effects on ruminal prokaryotes and Fibrobacter succinogenes S85[J].Journal of Animal Science,1992,70(1):289-295.

[22] KRAUSE D O,DALRYMPLE B P,SMITH W J,et al.16S rDNA sequencing of Ruminococcus albus and Ruminococcus flavefaciens:design of a signature probe and its application in adult sheep[J].Microbiology,1999,145(7):1797-1807.

[23] LIN C Z,FLESHER B,CAPMAN W C,et al.Taxon specific hybridization probes for fiber-digesting bacteria suggest novel gut-associated Fibrobacter[J].Systematic and Applied Microbiology,1994,17(3):418-424.

[24] HO Y W,ABDULLAH N,JALALUDIN S.Micorbial Colonisation and degradation of some fibrous crop residues in the rumen of goats[J].Asian-Australasian Journal of Animal Sciences,1996,9(5):519-524.

[25]徐俊,侯玉洁,杨宏波,等.尼龙袋法研究燕麦草茎杆在瘤胃中降解超微结构的动态变化[J].中国畜牧杂志,2014,50(7):35-39.

[26]徐俊,侯玉洁,赵国琦,等.羊草茎在奶牛瘤胃中降解特性及其对食糜纤维分解菌数量的 影响[J].草业学报,2016,25(4):166-171.

[27] 徐俊,丁健,侯玉洁,等.稻草茎在奶牛瘤胃中的降解动态[J].江苏农业科学,2013,41(8):191-194.

Diversity of Ruminal Bacterial Communities in Different Forages Degradationi   
XU Jun12WU Lei1\*CHEN Qinglong1HU LifanglHOU Yujie23ZHAO Guoqi²SUN Jianyong4WU Sijun1\*\*ZHOU Yaomin1\*\* (1. Jiangxi Academy of Agricultural Sciences, Nanchang 330200, China; 2. College of Animal   
Science and Technology, Yangzhou University, Yangzhou 225009, China; 3. Nanchang Academy of Agriculture Science, Nanchang 330o08, China; 4. Institute of Animal Husbandry and Vet of State-Owned First Pasture, Aletai 836500, China)

Abstract: In this study, we used high throughput sequencing to investigate the diversity of ruminal bacterial communities in different forages degradation. Alfalfa,oat hay, Leymus chinensis and rice straw were choose as experimental materials, smashed and weighted $3 . 0 \ \mathrm { g }$ ，put in a nylon bag then put into the rumen, put out after degraded for $2 4 \mathrm { h }$ , washed and extracted the total DNA,and sample preparation and machine analysis were according for Miseq high throughput sequencing. The results showed as follows: 1) at the level of the genus, the sequence alignment obtained 91 genera,Butyrivibrio,Prevotella,Fibrobacter and Treponema were the dominant genera in the four forages. 2) Based on the principal coordinate analysis (PCoA) by UniFrac, the contribution rates of the first principal component and the second principal component were $5 2 . 8 9 \%$ and $1 9 . 4 3 \%$ respectively.3) The numbers of operational taxonomic units (OTU) of alfalfa, oat hay, Leymus chinensis and rice straw were 5 778,6 984,5 220 and 6 018,respectively,2 913 OTUs were shared by four forages and which got $3 2 . 3 8 \%$ of the total number of OTU in bacteria. These results showed that the diversity of bacterial communities were different in the four forages which degraded at the same time.

Key words: forage; bacterial community; high throughput sequencing