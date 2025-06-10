# 新疆夏季行星边界层参数化方案模拟特征研究

张海亮，李火青，买买提艾力·买买提依明(中国气象局乌鲁木齐沙漠气象研究所，新疆 乌鲁木齐830002)

摘要：行星边界层参数化方案(PBL)对天气气候和大气环境的模拟与预报具有重要影响。通过基于单柱模式(SCM)的乌鲁木齐单点理想实验，以及新疆2019年8月15—18日的一次降水天气过程的模拟检验及诊断分析，研究了YSU、ACM2、BOULAC、GBM、MYJ和QNSE6种常用的PBL参数化方案模拟的大气比湿、位温等气象要素响应土壤湿度变化的特征。结果表明：土壤湿度增加时，使用不同PBL参数化方案模拟的低层大气都呈现出比湿增加、位温降低、边界层高度降低的显著特征;GBM、ACM2中,垂直水汽输送效率较低,大气比湿较低、位温较高、湍涡作用范围较大,降水偏漏报;QNSE、MYJ中,垂直水汽输送效率较高，大气比湿较高、位温较低,湍涡作用范围较小,降水偏空报；QNSE、MYJ模拟的 $2 \mathrm { m }$ 比湿最大;ACM2模拟的 $2 \mathrm { m }$ 比湿最小;夜间QNSE模拟的 $2 \mathrm { m }$ 温度最低；白天MYJ模拟的2m温度最高;QNSE、MYJ模拟的 $1 0 \mathrm { m }$ 风速最高。这些模拟特征与PBL方案水汽垂直输送效率的差异密切相关。

关键词：WRF；单柱模式；行星边界层参数化方案；土壤体积含水量

WRF是美国国家大气研究中心(NCAR)等单位研发的新一代中尺度区域天气数值预报模式，集成了丰富的物理过程参数化方案，在全球获得了广泛应用。PBL参数化方案则是为解决在大气动力方程数值计算中，网格无法解析的湍涡引起的动量、热量及水汽等垂直、水平输送，而设计的近似参数化方案[1]。大量研究表明,PBL参数化方案对天气气候和大气环境的模拟与预报具有重要影响，通过计算下垫面和大气之间的次网格热量、动量交换、能量耗散以及水汽等物质的输送，对WRF动力框架计算结果进行修订[2-7]。积云对流参数化方案对WRF的模拟非常重要，与水汽凝结加热及雷暴的中尺度演变特征密切关联[8-10]。本文主要聚焦于PBL参数化方案的模拟特征研究。

PBL参数化方案种类较多。按照大气雷诺平均方程的闭合形式可分为1阶闭合，1.5阶闭合以及2阶或更高阶闭合"；使用的闭合方程有动量形式的大气方程,也有谱形式的大气方程[12]。如何选择合适的边界层参数化方案，提高WRF等区域数值模式的预报技巧？目前已经有了较多的研究结果[13-18]。Banks等[15对8种PBL参数化方案在雅典模拟的结果进行了比较研究，指出不同PBL参数化方案对2$\mathrm { ~ m ~ }$ 温度 $\cdot 2 \mathrm { ~ m ~ }$ 湿度等气象要素的影响很大，在不同的气象条件下，非局地闭合的PBL参数化方案表现更优。张晓培等[使用4种PBL参数化方案模拟了2008年4月24—25日安徽黄山地区气象要素场变化特征，指出YSU方案模拟的 $2 \mathrm { ~ m ~ }$ 气温误差最小，ACM2方案模拟的 $2 \mathrm { m }$ 露点温度和 $1 0 \mathrm { m }$ 风速误差最小。王颖等[]使用3种边界层参数化方案(YSU，MYJ和ACM2)，模拟了2005年1月25—28日兰州市冬季地面温度和风速的变化，指出对兰州市冬季大气边界层地面温度日变化的模拟，MYJ方案优于YSU和ACM2方案。陈淑莹等[18]为探寻天山地区WRF模式中最优参数化方案组合，设计了6组物理参数化方案敏感性实验进行验证，发现不同参数化方案组合对预报的气象要素影响较大。这些研究成果对PBL参数化方案的应用具有积极的指导作用，指出了不同PBL参数化方案在不同的地区具有不同的适用性特征。

随着研究的深人，人们对不同PBL参数化方案在不同地区模拟存在差异的原因也更加关注。为探讨不同PBL参数化方案模拟差异的原因，黄文彦等[19]使用5种边界层方案模拟了美国北部森林地区边界层的热力和动力结构，指出YSU、ACM2方案在白天表现出强的湍流混合和卷夹，相比于局地MYJ、UW方案，模拟的对流边界层温度更高、湿度更低、混合层高度更高、感热通量更大。Hu等2o认为在德克萨斯州使用MYJ方案模拟的气温更冷、大气比湿更湿是由于边界层垂直混合强度和空气夹卷导致。这些研究从动力、热力等角度对不同PBL方案模拟差异的原因进行了研究，得到了非常有价值的成果。

然而，目前针对PBL方案水汽垂直输送模拟特征的研究工作还相对较少，水汽含量对大气温湿特征及局地次级环流都有重要影响，对于深人理解不同PBL方案的模拟特征差异具有积极的作用。同时，由于新疆地处中亚腹地,地理位置极为重要，目前针对新疆区域开展PBL参数化方案模拟特征的研究工作也较少。

基于此，为揭示不同PBL参数化方案在新疆区域的模拟特征，探究不同PBL参数化方案模拟的2m温度、 $. 2 \mathrm { m }$ 湿度差异的原因，对比不同PBL参数化方案在新疆区域的模拟结果的系统性偏差，本文采用单柱模式研究了6种典型的PBL参数化方案：YSU、ACM2、BOULAC、GBM、MYJ、QNSE模拟了大气比湿、位温对土壤湿度的响应特征;通过对新疆2019年8月15一18日的一次强降水天气过程的三维模拟检验及诊断分析，得到了高空及地面气象要素的预报结果检验特征和预报结果的系统偏差特征，为在新疆区域PBL参数化方案的应用提供科学依据。

# 1研究方法和数据来源

# 1.1研究方法

大气边界层中湍流和扩散过程与其他物理过程之间存在复杂的非线性相互作用1，为解耦不同物理过程的相互作用，通常采用单柱模式模拟物理参数化方案，同时关闭其他物理参数化方案[22-25]因此，选取单柱模式研究新疆夏季不同PBL参数化方案的模拟特征。具体实验方法：使用双周期侧边界条件，以运行单柱模式；为解耦其他物理过程的干扰，只打开辐射、陆面、PBL以及近地层参数化方案；位温上高下低，以保持大气层结稳定；通过改变土壤体积含水率对单柱模式进行强迫，研究不同PBL参数化方案条件下，模拟的大气比湿、位温响应土壤湿度的特征。实验参数如表1所示。

不同PBL参数化方案的模拟特征需要进行真实天气个例的检验，才能做出全面的应用评估[20]选取6种PBL参数化方案，对新疆2019年8月15—18日的一次强降水天气过程进行模拟分析，利用新疆区域14个探空站和105个国家地面气象站的观测数据对模拟结果进行检验，分析得到6种PBL参数化方案在新疆夏季的预报性能特征及系统偏差特征，这些特征与PBL参数化方案水汽垂直输送能力密切相关。检验指标为平均偏差(BIAS)与均方根误差(RMSE)。由于真实天气过程模拟的结果受到大气平流及其他物理参数化方案耦合作用的影响，不同PBL参数化方案的模拟特征趋势可能并不显著或出现背离。

WRF模拟区域采用2层模拟区域嵌套运行（图1),外层区域为中亚区域,格点分辨率为 $9  { \mathrm { k m } } \times 9  { \mathrm { k m } }$ 内层区域为新疆区域,格点分辨率为 $3 \mathrm { k m } \times 3 \mathrm { k m }$ 。

# 1.2数据来源

研究中使用的 $2 \mathrm { m }$ 温度、 $1 0 \mathrm { m }$ 风速 $\cdot 2 \mathrm { m }$ 比湿、高空风速、高空温度及位势高度数据来自于新疆气象局14个探空气象站数据和105个国家地面气象站提供的观测数据。WRF模式使用的背景场数据来自于NCEP全球预报系统(GFS)提供的 $0 . 2 5 ^ { \circ } { \times } 0 . 2 5 ^ { \circ }$ 的格点数据。

# 2结果与分析

# 2.1大气比湿与位温对土壤湿度的响应特征

土壤湿度增加时，因夏季对流边界层内湍流的强烈混合作用，土壤湿度能迅速影响到大气边界层顶[26-27]。图2揭示了在不同边界层参数化方案条件下，大气比湿响应土壤湿度变化的特征：当大气水汽含量未饱和时，土壤体积含水率与低层大气比湿呈非线性正比关系，土壤体积含水率越高，低层大气比湿就越大，高层大气比湿基本保持不变。图3揭示了在不同边界层参数化方案条件下，大气位温响应土壤湿度变化的特征：当大气水汽含量未饱和时，土壤体积含水率与低层大气位温呈非线性反比关系，土壤体积含水率越高，低层大气位温就越低，高层大气位温基本保持不变。结合图2和图3可知，当大气水汽含量未饱和时，土壤湿度持续增加时，低层大气湿度呈现持续增加，位温持续降低、湍涡作用高度持续降低的显著特征。这主要是由于在湿下垫面的强迫作用下，土壤湿度增加引起边界层大气湿度增加，液态水气化吸收大量潜热，低层大气位温持续降低，边界层湍动能的浮力分量减少，湍涡作用区域缩小，作用高度降低。

表1单柱理想实验初值参数配置  
Tab.1 Configurationof the SCMIdealExperiments   

<html><body><table><tr><td>垂直分层</td><td>土壤体积含水率/%</td><td>纬向风/(m·s=1)</td><td>经向风/(m·s=)</td><td>位温/K</td><td>比湿/(k·kg-1)</td><td>经纬度</td><td>起报世界时</td></tr><tr><td>60层</td><td>0.1</td><td>10</td><td>-7</td><td>302~320</td><td>0</td><td>43.78N</td><td>2019-08-15</td></tr><tr><td></td><td>0.2</td><td></td><td></td><td></td><td></td><td>87.65E</td><td>12:00 UTC</td></tr><tr><td></td><td>0.3</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

![](images/7679165af66ebc6e26ec1927fc29bb13d8299decb9732a5ef665f4f7daae0838.jpg)  
图1模拟区域地形高程  
Fig.1 Simulation domains   
注：纵坐标表示模式垂直坐标值（取值范围0.0\~1.0,0.0代表模式顶，1.0代表模式底）。  
图2不同土壤湿度与边界层方案对大气比湿的影响

利用不同PBL参数化方案进行模拟时，低层大气位温、比湿对土壤湿度的响应程度不同。GBM方案模拟结果显示，其低层大气比湿最小，大气位温最高，湍涡作用区域最大，湍涡作用高度最高，土壤湿度对大气比湿的影响最小，因此其水汽垂直输送效率最低。QNSE、MYJ、YSU方案模拟结果显示，其低层大气比湿较小，大气位温较低，湍涡作用区域较小，湍涡作用高度较低，土壤湿度对大气比湿的影响较大，因此其水汽垂直输送效率较高。在ACM2、BOULAC方案中，土壤湿度对大气的影响和

土壤湿度=0.1(a)YSU (b)ACM2 (c)BOULAC (d)MYJ (e) QNSE (f) GBM0.2 0.2 0.2 0.2 0.20.4 0.4 0.4 0.4 0.4  
0.6 0.6 0.6 0.6 0.6 0.6  
0.8 0.8 0.8 0.8 0.8 0.80204060 0204060 0204060 0204060 0204060 0204060土壤湿度=0.2(g)YSU (h)ACM2 (i) BOULAC (j)MYJ (k)QNSE (l) GBM8: 8: 8: 8 840.6 0.6 0.6 0.6 0.6  
0.8 0.8 0.8 0.8 0.8 0.80204060 0204060 0204060 0204060 0204060 0204060土壤湿度=0.4(m) YSU (n)ACM2 (o)BOULAC (p)MYJ (q)QNSE (r)GBM8: 8.21 8: 8:3 810.6 0.6 0.6 0.6 0.6  
0.8 0.8 0.8 0.8 0.8 0.80204060 0204060 0204060 0204060 0204060 0204060模拟时长/h 模拟时长/h 模拟时长/h 模拟时长/h 模拟时长/h 模拟时长/h0.00.40.81.21.32.02.42.83.23.64.04.4 4.85.2 5.66.0 6.46.87.2 7.68.08.48.89.29.6 10.0空气比湿 $( \mathbf { k } { \cdot } \mathbf { k } \mathbf { g } ^ { - 1 } )$

Fig.2 Impacts of different soil moisture and boundary layer schemes on the atmospheric specific humidity

土壤湿度=0.1(a)YSU (b)ACM2 (c)BOULAC (d)MYJ (e)QNSE (f) GBM0.2 0.2 0.2 0.2 0.2  
1 0.4 0.4 0.4 0.4 0.40.6 0.6 0.6 0.6 0.6  
0.8 0.8 0.8 0.8 0.8 0.80204060 0204060 0204060 0204060 0204060 0 204060土壤湿度=0.2(g)YSU (h)ACM2 (i) BOULAC (j)MYJ (k)QNSE (l) GBM0.2 0.2 0.2 0.2 0.20.4 0.4 0.4 0.4 0.40.6 0.6 0.6 0.6 0.6  
0.8 0.8 0.8 0.8 0.8 0.80204060 0204060 0204060 0204060 0204060 0204060土壤湿度=0.4(m) YSU (n) ACM2 (o)BOULAC (p)MYJ (q)QNSE (r) GBM0.2 0.2 0.2 0.2 0.20.4 0.4 0.4 0.4 0.4  
0.6 0.6 0.6 0.6 0.6 0.6  
0.8 0.8 0.8 0.8 0.8 0.80204060 0204060 0204060 0204060 0204060 0204060模拟时长/h 模拟时长/h 模拟时长/h 模拟时长/h 模拟时长/h 模拟时长/h二290 292 294 296298300 302304306308310312314316318320大气位温/K

水汽垂直输送效率介于GBM与QNSE、MYJ、YSU方案之间。

# 2.2不同PBL参数化方案的预报性能特征

2.2.1 高空气象要素预报性能特征 选择2019年8月15—18日00:00—12:00UTC的新疆区域14个探空站观测数据与WRF模拟结果进行对比。模拟的$7 0 0 \mathrm { { h P a } }$ 以下大气比湿为负偏差(图4a)，说明模拟的$7 0 0 \mathrm { { h P a } }$ 以下大气较实况偏干。 $4 0 0 \mathrm { { h P a } }$ 以下,QNSE模拟的比湿最高，次高为MYJ;ACM2模拟的比湿最低，次低为GBM；YSU、BOULAC模拟的比湿值介于两者之间，天气过程个例模拟结果与单柱模拟结果基本一致(图4a)。模拟的 $5 0 0 \mathrm { { h P a } }$ 以下大气位温为正偏差，说明模拟的 $5 0 0 \mathrm { { h P a } }$ 以下大气位温较实况偏暖。 $7 0 0 { \sim } 8 5 0 \mathrm { h P a }$ 之间，QNSE、MYJ模拟的位温较低；GBM、ACM2模拟的位温较高；YSU、BOULAC模拟的位温介于两者之间，天气过程个例模拟与单柱模拟的结果基本一致(图4b)。 $7 0 0 \mathrm { { h P a } }$ 以上,QNSE、MYJ模拟的位温明显高于其他方案，可能是QNSE、MYJ方案增加了对流层水汽含量，大气温室效应增强，导致模式高层大气变暖，需进一步研究。由于QNSE、MYJ模拟的 $7 0 0 \mathrm { { h P a } }$ 以上位温较其他边界层参数化方案明显偏高，导致 $5 0 0 ~ \mathrm { { h P a } }$ 以下,QNSE、MYJ模拟的位势高度较其他方案更低。 $5 0 0 \mathrm { { h P a } }$ 以下QNSE、MYJ模拟的位势高度较低，ACM2、GBM模拟的位势高度较高，YSU、BOULAC模拟的位势高度位于两者之间(图4c)。模拟的各气压层的风速变化无显著规律(图4d)。综上所述：QNSE、MYJ模拟的向上垂直水汽输送效率最高，所以其模拟的400hPa以下的比湿最大， $7 0 0 { \sim } 8 5 0 \ \mathrm { h P a }$ 温度最低，500hPa以下位势高度最低；ACM2、GBM模拟的向上垂直水汽输送效率最低，所以其模拟的 $4 0 0 \mathrm { { h P a } }$ 以下比湿最小, $7 0 0 { \sim } 8 5 0 \mathrm { h P a }$ 位温最高， $5 0 0 \mathrm { { h P a } }$ 以下位势高度最高。以上结果与单柱模式模拟的结果基本一致。

2.2.2地面气象要素预报性能特征与新疆区域105个国家气象站地面观测数据进行对比检验。模拟的 $2 \mathrm { m }$ 比湿均为负偏差(图5a,图5b)，说明模拟比湿较实况偏干。ACM2、GBM模拟的 $2 \mathrm { m }$ 比湿较小,均方根误差较大。QNSE、MYJ模拟的 $2 \mathrm { ~ m ~ }$ 比湿较大，均方根误差较小。YSU、BOULAC模拟的 $2 \mathrm { m }$ 比湿基本介于两者之间。结果表明，ACM2、GBM垂直水汽输送效率较低，QNSE、MYJ垂直水汽输送效率较高，与单柱理想实验模拟结果一致。模拟的 $2 \mathrm { m }$ 温度基本上为正偏差(图5c，图5d)，说明模拟温度较实况偏高。在夜间，QNSE、MYJ模拟的 $2 \mathrm { ~ m ~ }$ 温度较低，均方根误差较小;ACM2模拟的 $2 \mathrm { m }$ 温度较高，均方根误差较大。在日间,QNSE模拟的 $2 \mathrm { m }$ 温度最低，均方根误差最小;GBM模拟的 $2 \mathrm { m }$ 温度较高，与单柱理想实验模拟结果一致。MYJ模拟的 $2 \mathrm { m }$ 比湿较大,预期其模拟的 $2 \mathrm { m }$ 温度在日间应较低，但MYJ模拟的 $2 \mathrm { m }$ 温度在日间最高，这可能与MYJ方案中$2 \mathrm { m }$ 温度的计算方法有关。模拟的 $1 0 \mathrm { m }$ 风速为正偏差（图5e，图5f)，说明模拟的地面风速较实况偏高。QNSE、MYJ模拟的 $1 0 \mathrm { m }$ 风速最高，均方根误差偏大。综上所述，QNSE、MYJ方案的垂直水汽输送效率较高， $2 \mathrm { m }$ 比湿最大,夜间 $2 \mathrm { m }$ 温度最低， $1 0 \mathrm { m }$ 风速最大。GBM、ACM2方案的垂直水汽输送效率较低， $2 \mathrm { ~ m ~ }$ 比湿最小,夜间 $2 \mathrm { m }$ 温度较高， $1 0 \mathrm { ~ m ~ }$ 风速最小，与单柱理想实验结果基本一致。

![](images/b55377f723f8eda82d54b60464f74956f857e4d1b7a435080e7dec448855bd5d.jpg)  
图4不同边界层参数化方案高空气象要素预报偏差

![](images/05a831466672ea9b913bd78adca0d83d3a836c3672a5054cece3e6434f28ef99.jpg)  
Fig.4BIAS of upper air forecasts of WRF simulations with 6 PBLs respectively   
图5不同边界层参数化方案地面气象要素预报偏差和均方根误差Fig.5BIAS and RMSE of surface forecasts of WRF simulations with 6 PBLs respectively

2.2.3降水预报性能特征选取新疆区域105个国家气象站24小时累计降水的观测数据对模拟结果进行检验。将每个模拟时次不同量级降水的预报命中次数、预报未命中次数、漏报次数和空报次数分别累加求和，并计算不同量级的24小时降水预报技巧(TS)和降水偏差(BIAS)评分。小于等于24.1mm量级的24小时降水BIAS评分小于1，说明降水预报偏漏报，这从一定程度上反映了美国国家环境预报中心(NCEP)全球预报系统(GFS)背景场偏干。从图6a\~图6f可以看出，在不同等级降水量上，各PBL方案模拟的降水TS评分有较显著的差异。QNSE方案的TS评分较高,尤其在大于等于 $1 2 . 1 \ \mathrm { m m }$ 量级降水上，其TS评分最高，与其垂直水汽输送效率高，能够在大气中输送更多的水汽及GFS背景场偏干有关。各PBL方案模拟的降水BIAS指标有较显著的差异（图 $6 \mathrm { g } \sim$ 图61)。在大于等于 $0 . 0 1 \ \mathrm { m m }$ 量级的晴雨预报中，QNSE、MYJ模拟的降水预报BIAS指标偏大，反映了其模拟的大气水汽含量相对较多；ACM2、GBM的模拟的降水预报BIAS偏小，反映了其模拟的大气水汽含量相对较少。说明了QNSE、MYJ水汽垂直输送能力较强，而ACM2、GBM水汽垂直输送能力较弱。综上所述：QNSE、MYJ模拟中，水汽垂直输送效率较高，降水预报BIAS评分最高，偏向于空报，GBM、ACM2模拟中，水汽垂直输送效率较低，降水预报BIAS评分最低，偏向于漏报。

# 2.3PBL参数化方案模拟的系统性偏差特征

由于不同PBL参数化方案在水汽、动量和热量输送方面的差异，不同PBL参数化方案模拟的气象要素存在着系统性偏差。通过计算模拟区域逐小时所有格点气象要素的平均值(格点数540981)来研究不同PBL参数化方案存在的系统性偏差。利

0.70 0.50 0.5 0.65 (a)降水≥0.1mm 0.45 (b)降水≥3.1mm (c)降水≥6.1mm   
888 0.560.54 .52 0.590.580.57 0.40 0.35 0.380.39 0.35 0.350.36 T 0.4 0.3 0.300.33 0.36 0.31 0.30 0.30 0.2 0.45 0.25 0.40 0.20 0.1 0.5 0.6 0.6 (d)降水≥12.1mm 0.5 (e)降水≥24.1mm 0.5 (f)降水≥48.1mm 0.4   
众本SI 0.34 0.4 0.4 0.3 0.260.280.300.29 0.29 0.3 0.3 0.2 0.2 0.2 0.1 0.1 0.1 0.0 0.00.00.00.00.00.0 0.0 0.00.00.00.00.00.0   
ASAII 10098 0.810.82 8706055 (b)5降 水≥3.1m 0.50 80644 0645 40.42 0.460.42 0.7 0.71 0.4 0.2 0.3 0.6 0.2 0.0 (i)降水≥12.1mm (k)降水≥24.1mm 1.2 (l)降水≥48.1mm 0.8 1.5 1.37 1.0   
SII 0.6 0.51 0.61 0 51 0.560.50 0.48 1.2 1.001.00 1.11 0.8 0.9 0.6 0.4 0.6 0.37 0.42 0.4- 0.2 0.3 0.2 0.0 0.00.0 0.0 0.0 0.0 0.0 0.0 0.0 nsx ACACA POUULC fXW ISNO GRM nsx ZCAIA PUUALC fAW ISNO GRM nsx AAAA POUULC fAW ISNO GRM

用不同PBL方案模拟的 $2 \mathrm { m }$ 比湿存在系统性的偏差（图 $7 \mathrm { a }$ ）,QNSE、MYJ模拟的 $2 \mathrm { m }$ 比湿最大;ACM2模拟的 $2 \mathrm { m }$ 比湿最小；GBM与YSU模拟的 $2 \mathrm { m }$ 比湿相当。利用不同PBL方案模拟的 $2 \mathrm { m }$ 温度存在系统性的偏差(图7b)，夜间，QNSE模拟的 $2 \mathrm { m }$ 温度最低，其他方案差异不明显。利用不同PBL方案模拟的10$\mathrm { ~ m ~ }$ 风速存在系统性的偏差（图 $\mathrm { 7 c }$ ），QNSE、MYJ模拟的 $1 0 \mathrm { ~ m ~ }$ 风速最高；BOULAC模拟的 $1 0 \mathrm { ~ m ~ }$ 风速最低。这些系统性偏差与不同边界层参数化方案的垂直水汽输送效率的差异密切相关。

# 2.4PBL参数化方案模拟特征的应用

美国国家环境预报中心的GFS背景场的水汽偏差是不确定的（偏干或偏湿）。本研究使用的新疆2019年8月15日00时的GFS背景场与观测数据相比，低层水汽偏干，位温偏暖，降水预报偏漏报[28]。基于本研究揭示的不同PBL参数化方案垂直水汽输送能力的差异，在新疆区域，对于偏干的GFS背景场应使用QNSE、MYJ等水汽垂直输送效率较高的PBL参数化方案，以增加陆面对大气的水汽输送；而对于偏湿的GFS背景场，应使用GBM、ACM2等水汽垂直输送效率较低的PBL参数化方案，以减少陆面对大气的水汽输送

![](images/0ae953aa6cf8ab8c46607d442d2b5569a864cc872ac7e88f1edec90fc17f58a4.jpg)  
图7边界层参数化方案模拟的系统偏差Fig.7The systematic BIASofWRF simulationfor different PBLs respectively

# 3结论

（1）土壤湿度增加时，不同PBL参数化方案模拟的边界层大气都呈现比湿增加、位温降低、边界层高度降低的显著特征。但不同PBL参数化方案的垂直水汽输送效率存在差异，GBM、ACM2方案的垂直水汽垂直输送效率较低，选择其模拟的低层大气比湿较低、位温较高、边界层高度较高，降水预报偏向于漏报；QNSE、MYJ方案的水汽垂直输送效率较高，选择其模拟的低层大气比湿较高、位温较低、边界层高度较低，降水预报偏向于空报。

（2）不同PBL参数化方案模拟的系统性偏差特征,QNSE、MYJ模拟的 $2 \mathrm { m }$ 比湿最大;ACM2模拟的$2 \mathrm { ~ m ~ }$ 比湿最小;夜QNSE模拟的 $2 \mathrm { ~ m ~ }$ 温度在夜间最低；MYJ模拟的 $2 \mathrm { ~ m ~ }$ 温度在日间最高。QNSE、MYJ模拟的 $1 0 \mathrm { m }$ 风速最高。

(3）在新疆区域，对于偏干的GFS背景场应使用QNSE、MYJ等水汽垂直输送效率较高的PBL参数化方案，以增加陆面对大气的水汽输送；而对于偏湿的GFS背景场，应使用GBM、ACM2等水汽垂直输送效率较低的PBL参数化方案，以减少陆面对大气的水汽输送。

# 参考文献(Reference)

[1] Stull R B.An Introduction to Boundary Layer Meteorology[M]. Netherlands: Springer,1988.   
[2] Smith RK,Thomsen GL.Dependence of tropical-cyclone intensification on the boundary-layer representation in a numerical model [J].Quarterly Journal of the Royal Meteorological Society,2010, 136(652): 1671-1685.   
[3] Shin HH,Hong S Y. Intercomparison of planetary boundary-layer parametrizations in the WRF model for a single day from CASES99[J].Boundary-Layer Meteorology,2011,139(2): 261-281.   
[4] Cheng FY,Chin SC,Liu TH. The role of boundary layer schemes in meteorological and air quality simulations of the Taiwan area[J]. Atmospheric Environment,2012,54(7): 714-727.   
[5]Xie B,Fung JC H, Chan A,et al.Evaluation of nonlocal and local planetary boundary layer schemes in the WRF model[J]. Journal of Geophysical Research Atmospheres,2012,117(D12).   
[6]Huang W,Shen X,Wang W,et al. Comparison of the thermal and dynamic structural characteristics in boundary layer with different boundary layer parameterizations[J]. Chinese Journal of Geophysics,2014, 57(4): 543-562.   
[7]Cohen AE, Cavallo S M, Coniglio MC,et al.Areview of planetary boundary layer parameterization schemes and their sensitivity in simulating southeastern US cold season severe weather environmens[J]. Weather and Forecasting,2015,30(3): 591-612.   
[8]王建捷,周斌,郭肖容.不同对流参数化方案试验中凝结加热的 特征及对暴雨中尺度模拟结果的影响[J].气象学报,2005,63 (4): 405-417.[Wang Jianjie,Zhou bin,Guo Xiaorong.Numerical study on characteristics of condensational heating rates and their impacts on mesoscale structure of torrential rain simulation[J]. Acta Meteorologica Sinica,2005,63(4): 405-417.]   
[9]孙建华,赵思雄.一次罕见的华南大暴雨过程的诊断与数值模 拟研究[J].大气科学,2000,24(3):381-392.[Sun Jianhua, Zhao Sixiong. A diagnosis and simulation study of a strong heavy rainfall in south China[J]. Chinese Journal of Atmospheric Sciences, 2000,24(3): 381-392.]   
[10] 陈静,薛纪善,颜宏.物理过程参数化方案对中尺度暴雨数值模 拟影响的研究[J].气象学报,2003,61(2):203-218.[Chen Jing, Xue Jishan,Yan Hong.The impact of physics parameterization schemes on mesoscale heavy rainfall simulation[J].Acta Meteorologica Sinica,2003,61(2): 203-218.]   
[11] 孙文奇,李昌义.数值模式中的大气边界层参数化方案综述[J]. 海洋气象学报,2018,38(3):11-19.[Sun Wenqi,Li Changyi.A review of atmospheric boundary layer parameterization schemes in numerical models[J]. Journal of Marine Meteorology,2018,38(3): 11-19.]   
[12] Sukoriansky S,Galperin B,Perov V.Application of a new spectral theory of stably stratified turbulence to the atmospheric boundary layer over sea ice[J]. Boundary-Layer Meteorology,2005,117(2): 231-257.   
[13]Gibbs JA,Fedorovich E.Comparison of convective boundary layer velocity spectra retrieved from large-eddy- simulation and Weather Research and Forecasting model data[J]. Journal of Applied Meteorology and Climatology,2014,53(2): 77-394.   
[14] LeMone MA,Tewari M,Chen F,et al.Objectively determined fairweather CBL depths in the ARW-WRF model and their comparison to CASES-97 observations[J].Monthly Weather Review,2013, 141(1): 30-54.   
[15]Banks RF, Tiana-Alsina J,Baldasano,JM,et al. Sensitivity of boundary-layer variables to PBL schemes in the WRF model based on surface meteorological observations,lidar,and radiosondes during the HygrA- CD campaign[J]. Atmospheric Research,2016, 176-177: 185-201.   
[16] 张小培,银燕.复杂地形地区WRF模式四种边界层参数化方案 的评估[J].大气科学学报,2013,36(1):68-76.[ Zhang Xiaopei, Yin Yan.Evaluation of the four PBL schemes in WRF model over complex topographic areas[J]. Transactions of Atmospheric Sciences,2013,36(1): 68-76.]   
[17] 王颖,张镭,胡菊,等.WRF模式对山谷城市边界层模拟能力的 检验及地面气象特征分析[J].高原气象,2010,29(6):1397- 1407.[Wang Ying,Zhang Lei,Hu Ju,etal.Verification of WRF simulation capacity on PBL characteristic and analysis of surface meteorological characteristic over complex terrain[J]. Plateau Meteorology,2010,29(6): 1397-1407.]   
[18] 陈淑莹,胡琪,张弛,等.WRF模式在天山地区模拟能力的敏感 性评估[J].干旱区研究,2019,36(1):196-206.[Chen Shuying, Hu Qi,Zhang Chi,et al.Evaluation on the sensitivity of WRF model in the Tianshan Mountains[J].Arid Zone Research,2O19,36(1): 196-206.]   
[19] 黄文彦,沈新勇,王卫国,等.边界层参数化方案对边界层热力 和动力结构特征影响的比较[J].地球物理学报,2014,57(5): 1399-1414.[ Huang Wenyan, Shen Xinyong,Wang Weiguo, et al. Comparison of the thermal and dynamic structural characteristics in boundary layer with diferent boundary layer parameterizations[J]. Chinese Journal of Geophysics,2014,57(5): 1399-1414.]   
[20] Hu X M,Nielsen-Gammon JW, Zhang F.Evaluation of three planetary boundary layer schemes in the WRF model[J]. Journal of Applied Meteorology & Climatology,2010,49(9): 1831-1844.   
[21]Wang W,Shen X, Huang W.A comparison of boundary-layer characteristics simulated using diferent parametrization schemes[J]. Boundary-Layer Meteorology,2016,161(2): 375-403.   
[22]Cuxart J,Holtslag AA M, Beare RJ,et al. Single-column model intercomparison for a stably stratified atmospheric boundary layer [J]. Boundary-Layer Meteorology,2006,118(2): 273-303.   
[23] Ayotte K W,Sullvan PP,Anders Andren,et al.An evaluation of neutral and convective planetary boundary-layer parameterizations relative tolargeeddysimulatios[J].Boundary-Layer Meteoog 1996, 79(1-2): 131-175.   
[24] Pleim JE.A combined local and nonlocal closure model for the atmospheric boundary layer. Part I: model description and testing[J]. Journal of Applied Meteorology & Climatology,2007,46(9): 1383- 1395.   
[25]Angevine W M,Jiang H, Mauritsen T.Performance of an eddy diffusivity-mass flux scheme for shallow cumulus boundary layers[J]. Monthly Weather Review,2010,138(7): 2895-2912.   
[26] 赵建华,张峰,梁芸,等.大气边界层湍流相干结构研究进展[J] 干旱区研究,2019,36(6):1419-1430.[Zhao Jianhua, Zhang Feng,Liang Yun,et al. Research progress on turbulent coherent structure in atmospheric boundary layer[J].Arid Zone Research, 2019,36(6): 1419-1430.]   
[27] Zhang H,Liu J,Li H,etal.The impacts of soil moisture initialization on the forecasts of Weather Research and Forecasting model: A case study in Xinjiang,China[J]. Water,2020,12(7): 1892.

# Simulation characteristics of planetary boundary layer parameterizations: A case study in Xinjiang during summer

ZHANG Hailiang， LI Huoqing， Ali Mamtimin (Institute of Desert Meteorology,China Meteorological Administration,Urumqi 83OoO2,Xinjiang,China)

Abstract:Planetary boundary layer (PBL） parameterization has significant impacts on the simulation and prediction of climate,weather,and environmental air quality. Here,ideal experiments were conducted using the single-column model to study the response characteristics of specific humidity and potential temperatures on soil moisture under different PBL parameterizations.A heavy precipitation synoptic process in Xinjiang from 15th18th August 2019 was simulated and verified with six PBL parameterizations, including YSU,ACM2, BOULAC, GBM,MYJ,and QNSE.As the soil moisture increases,the simulated atmospheric boundary layer presents significant characteristics，namely，increasing specific humidity，decreasingpotential temperatures，and decreasing boundary layer height. In GBM and ACM2 cases,the vertical water vapor transport eficiency was low,atmospheric specific humidity was also low,the potential temperature was high,eddy action scope was large,and precipitation was underestimated. In QNSE and MYJ cases，the vertical water vapor transport effciency was high,atmospheric specific humidity was high,the potential temperature was low,eddy action scope was small, and precipitation was overestimated. The maximum $2 \mathrm { ~ m ~ }$ specific humidity was achieved using QNSE and MYJ,while the minimum $2 \mathrm { ~ m ~ }$ specific humidity was by ACM2.The lowest $2 \mathrm { ~ m ~ }$ temperature was achieved at nighttime using QNSE,while the highest $2 \mathrm { ~ m ~ }$ temperature was at daytime using MYJ.The highest $1 0 \mathrm { ~ m ~ }$ wind speed was achieved using QNSE and MYJ.These simulating characters are closely related to the differences in the vertical water vapor transport efficiency of the different PBL parameterizations.

Keywords: weather research and forecasting model; single column model; planetary boundary layer parameterization; soil moisture