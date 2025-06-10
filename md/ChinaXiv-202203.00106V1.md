# 地貌形态多尺度综合分类方法

杨维涛1,23，孙建国123，马恒利1.23，黄卓1,2.3(1.兰州交通大学测绘与地理信息学院，甘肃 兰州730070；2.地理国情监测技术应用国家地方联合研究中心，甘肃 兰州 730070；3.甘肃省地理国情监测工程实验室,甘肃 兰州 730070)

摘要：地貌形态对象往往大小悬殊,跨越特定的空间尺度。现有的地貌形态自动分类方法尚未充分顾及该特点,分类精度受到制约。利用地貌形态的大小为尺度，提出1种涉及尺度跨越性的地貌形态多尺度综合分类方法，该方法由多尺度分割、按尺度顺序筛选和多尺度合并3个步骤构成。其中,按尺度顺序筛选是1个以多尺度特征提取和监督分类为基础、以小尺度(小尺寸)优先和概率最大化为准则的被分类对象迭代确认过程。以黄土高原为例的试验结果表明,该方法简便可靠(总体精度可以达到 $7 5 . 1 6 \%$ ,Kappa系数可以达到0.71),可用于地貌形态精细化分类。

关键词：地貌形态；分类；多尺度；黄土高原

地貌形态指客观存在的地表几何特征，是诸多自然因素和人文过程形成与演化的边界条件[1-3]地貌形态分类是按照特定的分类标准划分不同类型地貌形态的主观过程，广泛应用于生态建模4、土壤制图[5和滑坡防治等诸多领域。地貌形态分类一般利用数字高程模型(DEM)或其他数据源进行[-8],包括人工和自动2种实现方式。人工分类具有较高的准确性,但速度慢、成本高且可重复性差9。自动分类大致又可分为基于像元的分类和基于对象的分类。相比而言，后者以图像分割所得单元为分类对象，更加符合人的空间认知过程，分类效果明显改善[10-11]

地貌形态复杂多样，常见的地貌形态类型也多种多样，这给地貌形态的划分造成了诸多困难。迄今为止，基于对象的地貌形态分类精度仍然不够理想。一个重要原因是，人类感兴趣的同类地貌形态往往具有多尺度性或尺度跨越性[12]。一方面,不同类型地貌形态之间可能具有整体上的尺度差异。例如，在一个范围较大的地形起伏区，河谷平地的范围一般比其他地貌形态狭小，但因其对生产和生活的便利性而成为感兴趣对象。对于这种情况，现有研究采用了分层识别策略，即在不同分割尺度下提取不同类型的地貌形态对象[13-14]。但是,多个最优分割尺度的选择需要多次试验和目测判断，过程繁琐且随意性较大[15-16]。另一方面，同一类型地貌形态的不同对象也常常具有尺度差异。例如，台塬的面积十分悬殊，可达数倍甚至更大，任何单一尺度的分割和分类结果总是不够理想。对于此类情形，现有研究还少有顾及。

因此，开发能够充分考虑跨尺度特点的地貌形态分类方法十分必要。本文提出一种考虑尺度跨越性的地貌形态多尺度综合分类方法（AMulti-Scale Integrated Classfication Method for Landforms ,以下文中简称为：MSIC），旨在避免以往研究针对不同类型地貌形态选择最优分割尺度的主观性，同时能够提取不同尺度上的同一类型地貌形态对象。拓展了地貌形态分类方法的研究思路，实现了地貌形态精细化分类，可为编制精细化地貌形态图谱提供技术支持，对于当地土地的合理化利用，水土流失的有效防治，降低自然灾害发生等方面均有积极的意义。

# 1研究方法

# 1.1MSIC步骤和原理

MSIC由多尺度分割、按尺度顺序筛选和多尺度合并三部分构成(图1)。多尺度分割是利用eCogni-tion的多尺度分类算法人为定义一系列尺度，获得各尺度分割对象。按尺度顺序筛选是1个以多尺度特征提取和监督分类为基础、以小尺度(小尺寸)优先和概率最大化为准则的被分类对象迭代确认过程(图2)。概率最大化是影像分类的一般依据，而小尺度优先则是为了保证在进行大尺度对象的提取和分类时能够剔除具有空间包含关系的小尺度对象的影响。多尺度合并是将各尺度分类筛选出的地貌进行合并，得到地貌形态分类结果。

具体描述为以下7个步骤：

第一步：多尺度分割。人为确定系列尺度，利用现有多尺度分割算法分割DEM，获得多尺度对象。

第二步：特征提取。逐尺度提取对象单元特征，包括地形属性、纹理特征以及其他可能有助于改善分类效果的地形特征。

第三步：监督分类。借助于实地考察或者高分辨率遥感影像等方式选择训练样本，进行监督分类得到多尺度的预分类信息。

第四步：最小尺度被分类对象的筛选。以小尺度优先和概率最大化为准则，筛选确认被分类对象。

第五步：多尺度对象的更新。从多尺度对象中剔除当前最小尺度，并将本次被分类对象从其他所有尺度对象中裁除。

第六步：循环。从当前执行最小尺度的下一尺度开始，重复执行第二步至第五步，直至执行完所有尺度。

第七步：多尺度合并。将各尺度上筛选出的已确认对象合并，得到完整的地貌形态类型图。

# 1.2精度评价

分类精度评价是对分类结果与真实地表地物接近程度的检验。精度评价是图像分类进行信息提取或土地利用/土地覆盖分类中必不可少的一部分，同时也是地貌形态识别不可或缺的环节。精度评定指标选择总体精度（OverallAccuracy，简称OA),制图精度(Producer'sAccuracy,简称PA）,用户精度(User'sAccuracy,简称UA)以及Kappa系数[17]。

总体精度是通过混淆矩阵对角线数据之和与样本总数的比值。该评价参数反映了图像自动分类中所有地物类别的总体精度，但是它并不能体现注： $\mathrm { a , b , \cdots , n ; c , d , \cdots , m }$ 为多尺度分割后的被分类对象，P为分类后验证概率。大尺度被分类对象包含小尺度分类对象，因而，当$\mathrm { P ( a ) { = } m a x \{ P ( a ) , P ( b ) , \cdots , P ( n ) \} }$ ，故a被确定;因 $\mathrm { P ( c ) } { \neq } \mathrm { m a x } \{ \mathrm { P ( c ) } , \mathrm { P ( d ) } , \cdots$ $\mathrm { P } ( \mathrm { m } ) \}$ ，故c不被确定。被分类对象被确定后，从所有尺度中裁剪出这个对象，从下一尺度循环算法，直至所有尺度结束。

![](images/4127d97239235831f95e4f9fe6a286048689a8d5eb1007e986c39db655d9f27e.jpg)  
图1MSIC流程 Fig.1 MSIC process

![](images/c7896fe0bcf876621153f803c4fdce4117000d7cdb793f5584fa4cc13e2976e1.jpg)

图2MSIC的小尺度优先与概率最大化准则示意图Fig.2 Schematic diagram of small scales priority andprobabilitymaximizationcriteria forMSIC

每个地物类别的精度情况。

$$
\mathrm { O A } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } m _ { i i } } { N } }
$$

PA又被称之为生产者精度，表示在所有实测类型为第 $i$ 类的样本中，被正确地分类也是第 $i$ 类的样本所占的比例。制图精度是对生产者分类精度的度量方式。

$$
\mathrm { P A } = \frac { m _ { i i } } { \displaystyle \sum _ { i = 1 } ^ { n } m _ { k i } }
$$

UA反映了某一类正确地提取该类样本度。

$$
U A = \frac { m _ { i i } } { \displaystyle \sum _ { i = 1 } ^ { n } m _ { i k } }
$$

Kappa系数能够准确的反映整体的地物分类精度，能够反映与验证数据的一致性，客观的评价出分类结果的精度。

$$
{ \mathrm { K a p p a } } = { \frac { N \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } m _ { i j } - \sum _ { i = 1 } ^ { n } m _ { i j } \times \sum _ { j = 1 } ^ { n } m _ { i j } } { N ^ { 2 } - \displaystyle \sum _ { i = 1 } ^ { n } m _ { i j } \times \sum _ { j = 1 } ^ { n } m _ { i j } } }
$$

式中： $i$ 和 $j$ 均为样本类别数； $N$ 为样本总数； $m$ 为对应类别个数； $k$ 为地物类别数。

# 2 试验

# 2.1试验区及数据

试验区位于中国黄土高原西部（ $1 0 6 . 1 0 ^ { \circ } \sim$ $1 0 6 . 7 6 ^ { \circ } \mathrm { E } , 3 5 . 7 1 ^ { \circ } { \sim } 3 6 . 2 7 ^ { \circ } \mathrm { N } )$ ,海拔 $1 1 3 2 { \sim } 2 9 3 2 \mathrm { m }$ ,地势西北高，东南低，区内有塬、璨、昴、河谷平原等典型地貌形态(图3)。试验区 $3 0 \mathrm { ~ m ~ }$ 空间分辨率的DEM从地理空间数据云下载(http://www.gscloud.cn/）。传统的地貌形态分类主要以典型地形因子为分类特征[18-19],另外一些研究还在地形因子的基础上考虑了地形纹理特征因子[]。近年来,有学者提出了地貌形态元素的概念及其提取方法[20-21],并且认为地貌形态元素的空间结构信息对于地貌形态分类十分有利[9。因此,本文依据地形因子、地形纹理和地貌形态元素结构信息共3类特征进行地貌形态分类。

# 2.2多尺度分割和样本采集

利用eCognitionDeveloper 9.0.3提供的多尺度分割算法对DEM进行分割。尺度的大小根据地貌形态的大小确定合适的尺度。除分割尺度外，其余参数均为默认值。经反复试验，分割尺度系列确定为 $1 0 0 \phantom { . } 2 0 0 \phantom { . } 4 0 0 \phantom { . } 8 0 0 \phantom { . } 1 2 0 0$ 和2000。手工数字化参考张宗祜主编的《中国黄土高原地貌类型图》22中的试验区部分，共包括基岩山地、平梁沟谷、缓梁沟谷、宽梁沟谷、狭梁沟谷、低丘缓谷、缓峁沟谷、河谷阶地、残塬沟谷、宽塬沟谷、盆地和塬共12种地貌形态。以其中图斑的 $3 0 \%$ 作为训练样本，所有图斑均作为验证样本。

# 2.3特征提取

（1）地形因子。地形因子多种多样，存在一定的相关性和信息冗余。采用雪氏熵值法确定相关性较低的地形因子，利用雪氏熵值法[18]对剩余备选地形因子进行量化筛选,最终确定高程、坡度、山体阴影、地表曲率和坡度变率、地形起伏度和高程变异系数7个因子参与分类。

![](images/dfe1c46bcc203775b8f821b49d2a0b2e98fed5079c90d733744fdcbc29f6b392.jpg)  
图3研究区示意图  
Fig.3Schematic diagram of the study area

(2）地形纹理。Haralick等23提出的灰度共生矩阵(GLCM)在图像纹理分析中得到广泛应用。考虑到工作量和GLCM之间的相关性，根据前人经验，选择了高程变异、坡度均值、坡度熵、阴影均值、阴影方差、阴影熵、阴影相关性、阴影角二阶矩、阴影相异性、阴影同质性和阴影对比度11个纹理特征。

# 表1MSIC精度

（3）地貌形态元素结构信息。首先，利用Jasie-wicz等[20]的方法提取形态元素图层；然后，利用GeoPAT[24]中的Co-occurrence直方图工具为每个尺度的每个单元提取空间结构信息；最后，利用主成分分析法获取前3个主成分。

# 3结果与分析

# 3.1MSIC分类精度

图4是MSIC方法的分类结果。研究区东南部主要为大范围基岩山地，西北部主要分布连片的残塬沟谷和缓梁沟谷，中部区域地貌形态类型多样且大小实体交错分布。表1为各种地貌形态的制图精度(PA)和用户精度(UA)。基岩山地的UA最高$( 7 9 . 7 0 \%$ ，塬的UA最低 $( 5 1 . 6 0 \%$ )，表明基岩山地的分类结果错分情况较低，而塬的分类结果错分情况较高。残塬沟谷的PA最高 $( 8 9 . 4 7 \% )$ ，源的PA最低1 $4 5 . 1 4 \%$ )，表明残塬沟谷的形态特征明显，不容易漏分，而塬容易出现漏分现象。总体精度为$7 5 . 1 6 \%$ ,Kappa系数为0.71，说明MSIC方法具有一定的实用性。

![](images/a12f395f40a11944ff9497484e4316d6e26823d33d427d2118db5a364b5eda2a.jpg)  
图4MSIC结果 Fig.4 MSIC results

Tab.1 Accuracy evaluation of MSIC   

<html><body><table><tr><td>类别</td><td>UA/%</td><td>PA/%</td><td>类别</td><td>UA/%</td><td>PA/%</td></tr><tr><td>基岩山地</td><td>79.70</td><td>70.23</td><td>残塬沟谷</td><td>74.12</td><td>89.47</td></tr><tr><td>狭梁沟谷</td><td>71.01</td><td>76.96</td><td>宽塬沟谷</td><td>73.05</td><td>68.67</td></tr><tr><td>宽梁沟谷</td><td>72.5</td><td>84.41</td><td>低丘缓谷</td><td>72.28</td><td>74.12</td></tr><tr><td>平梁沟谷</td><td>70.38</td><td>86.25</td><td>河谷阶地</td><td>65.74</td><td>76.47</td></tr><tr><td>缓梁沟谷</td><td>69.56</td><td>58.94</td><td>盆地</td><td>76.53</td><td>66.58</td></tr><tr><td>缓峁沟谷</td><td>73.55</td><td>87.72</td><td>塬</td><td>51.6</td><td>45.14</td></tr><tr><td>总体精度</td><td colspan="2">75.16%</td><td>Kappa系数</td><td colspan="2">0.71</td></tr></table></body></html>

# 3.2MSIC与单一尺度分类精度对比

图5为单尺度系列 $1 0 0 , 2 0 0 , 4 0 0 , 8 0 0 , 1 2 0 0$ 和2000的分类结果。与图4对比可以发现，小尺度上的地貌形态结果与MSIC结果相似度较高，但是地貌形态过于细碎，过分割现象十分明显；大尺度地貌形态斑块较大，较小的地貌形态被淹没，欠分割现象比较突出。例如，图5中窗口A的地貌形态应是基岩山地，但在较小尺度(100、200和400)分类结果中夹杂着狭梁沟谷和盆地，在较大尺度(800、1200和2000)上则少有混分。窗口B的地貌形态应为缓昴沟谷，较小尺度上少有混分，但在较大尺度上出现了错分情况。

表2为各单尺度分类精度与MSIC的总体精度、Kappa系数。单尺度 $1 0 0 , 2 0 0 , 4 0 0 , 8 0 0 , 1 2 0 0 , 2 0 0 0$ 的分类总体精度分别为 $4 2 . 3 0 \% , 4 8 . 9 1 \% , 4 7 . 8 4 \%$ 、$4 8 . 6 6 \%$ ） $3 2 . 1 9 \%$ 和 $2 4 . 9 8 \%$ ,Kappa系数为0.36、0.43、0.42、0.43、0.25和 $0 . 1 6$ 。可见，200尺度上的总体精度和Kappa系数均最高,总体精度为 $4 8 . 9 1 \%$ ,Kappa系数为0.45。MSIC的总体精度和Kappa系数高于任何一种单尺度，高出200尺度 $2 6 . 2 5 \%$ 和 $0 . 2 6$ ○

为进一步说明MSIC相对单尺度分类方法的优势，根据斑块大小，将研究区地貌形态分成"大型地貌形态”、“中等地貌形态"和"小型地貌形态"3个等级，分别用G1，G2和G3表示。利用验证数据对合并后的地貌形态进行精度评价(表3)。MSIC在G1、G2和G3等级中，PA和UA均大于 $8 0 \%$ ，分类精度高。而各单尺度中，G1在小尺度(100和200)PA和UA均较小，在大尺度(1200和200)PA和UA均较

![](images/4a9247ded1d77bbaf3b14ec1518c1f04a882431b23191ed9603df208b40f12cc.jpg)  
图5单一尺度分类结果  
Fig.5Single scale classification results

# 表2MSIC与单一尺度分类精度对比

Tab.2 Comparison ofMSIC and single scale classification accuracy   

<html><body><table><tr><td></td><td>总体精度/%</td><td>Kappa系数</td></tr><tr><td>尺度100</td><td>42.30</td><td>0.36</td></tr><tr><td>尺度200</td><td>48.91</td><td>0.45</td></tr><tr><td>尺度400</td><td>47.84</td><td>0.42</td></tr><tr><td>尺度800</td><td>48.66</td><td>0.43</td></tr><tr><td>尺度1200</td><td>32.19</td><td>0.25</td></tr><tr><td>尺度2000</td><td>24.98</td><td>0.16</td></tr><tr><td>本文方法</td><td>75.16</td><td>0.71</td></tr></table></body></html>

大。G2在小尺度和大尺度PA和UA均较小，在中间尺度(400和800)PA和UA均较大。G3在小尺度PA和UA均较大，在大尺度(1200和200)PA和UA均较小。

# 4讨论

地貌形态的多尺度或跨尺度特性使得单一尺度的分割和分类往往不能达到用户的需求。本文提出的MSIC以小尺度(小尺寸)优先和概率最大化为准则，对地貌形态对象进行迭代确认分类，旨在从小尺度上分辨小型地貌形态，从大尺度上识别大型地貌形态。试验结果验证了MSIC的可行性。

Xiong等[25]提出过基于小流域的地貌形态分类方法。该方法需要获取临界流域大小的阈值。若阈值过大，小流域分割的太大，可能1个小流域不止1种地貌形态;若小流域分割的太小，可能由于数据分辨率不足而产生地貌类型错误。王乐等[13]尝试利用层次分类法进行地貌形态分类，但同样对流域阈值的选择依赖较大，最佳流域阈值需要依靠多次试验，以人为筛选为主，主观性较大。与上述2种方法相比，MSIC虽然也涉及到多尺度分割，但是尺度的选择不像传统方法要求那么高，可以人为规定一系类尺度。当然，设定的尺度越多，分类精度必然越高，但计算量越大。

MSIC在其他的遥感影像分类中也具有广泛的应用潜力。广义的讲，地貌形态分类属于遥感影像分类中的一类。在遥感影像分类中，面向对象的分类方法主要以同种地物类型同一尺度为主。对于同种地物类型而言，也普遍存在跨尺度的现象（尤

# 表3地貌形态分级精度评定

Tab.3 Classification accuracy evaluation of landforms   

<html><body><table><tr><td rowspan="2"></td><td colspan="2">G1</td><td colspan="2">G2</td><td colspan="2">G3</td></tr><tr><td>PA/%</td><td>UA/%</td><td>PA/%</td><td>UA/%</td><td>PA/%</td><td>UA/%</td></tr><tr><td>100</td><td>59.43</td><td>58</td><td>70.61</td><td>75.75</td><td>80.16</td><td>87.95</td></tr><tr><td>200</td><td>58.95</td><td>65.73</td><td>71.7</td><td>77.68</td><td>75.74</td><td>73.09</td></tr><tr><td>400</td><td>61.88</td><td>71.57</td><td>77.72</td><td>75.81</td><td>72.8</td><td>75.99</td></tr><tr><td>800</td><td>65.64</td><td>65.84</td><td>75.03</td><td>81.93</td><td>60.71</td><td>68.14</td></tr><tr><td>1200</td><td>77.45</td><td>77.19</td><td>73.5</td><td>79.57</td><td>55.81</td><td>62.9</td></tr><tr><td>2000</td><td>79.56</td><td>77.86</td><td>67.25</td><td>68.43</td><td>46.25</td><td>55.54</td></tr><tr><td>MSIC</td><td>88.89</td><td>75.27</td><td>80.33</td><td>82.77</td><td>88.29</td><td>88.39</td></tr></table></body></html>

其在高分辨率遥感影像中）。因此在遥感分类时，单一尺度可能并不能满足实际的需求。MSIC不仅能够避免不同地貌形态最优尺度的选择，而且能够处理同一类型地貌形态对象跨尺度的情况，因而可能应用于面向对象的遥感分类中来解决这一问题。

# 5结论

现有的地貌形态自动分类方法尚未充分顾及地貌形态对象跨尺度的分类难题，分类精度受到制约。本文提出了1种考虑尺度跨越性的地貌形态多尺度综合分类方法。以黄土高原为例的试验得出以下结论：

（1）MSIC总体精度为 $7 5 . 1 6 \%$ ,Kappa系数为0.71,分类精度较高。(2）MSIC在G1、G2和G3等级中，PA和UA均大于 $8 0 \%$ ,既识别出了小型地貌形态，也分出了大型地貌形态，可用于地貌形态精细化分类。

本文尝试从地貌形态的属性出发，以地貌形态的大小为尺度划分单元，进行地貌形态多尺度分类，虽取得了不错的效果，但是文章只考虑了地貌形态的形态特征因素，地貌形态作为形态和成因的复杂结合体，试验中对于地貌形态的成因方面尚未考虑，在今后研究中：

（1）应该既考虑地貌形态的形态特征，也考虑  
地貌形态的成因。（2）本研究中采用的试验参数具有区域性，是  
针对研究区地貌形态对应设定的，应用于其他研究  
区时须做相应调整。（3）MSIC对地貌形态进行自动分类时，采用常  
规的监督分类，效率较低，可尝试在后续研究中，考

虑机器学习算法进行分类，提高分类精度和效率。

(4）如何优化尺度选取，实现尺度自适应的分类算法，同时寻找更能反应地貌形态特征的因子组合，以期达到更好的分类效果。

# 参考文献(References）:

[1]田丹,刘爱利,丁浒,等.地貌形态类型面向对象分类法的改进 [J].地理与地理信息科学,2016,32(2):46-50.[Tian Dan,Liu Aili,Ding Hu,et al.Improvement of object-oriented classification method for landform types[J]. Geography and Geo-Information Science,2016,32(2): 46-50.] [2]李炳元,潘保田,程维明,等.中国地貌区划新论[J].地理学报,   
2013,68(3):291-306.[Li Bingyuan,Pan Baotian, Cheng Weiming,et al. Research on geomorphological regionalization of China [J].Acta Geographica Sinica,2013,68(3): 291-306.] [3]Deniz G,Toprak V,Strobl J. Object-based classification of landforms based on their local geometry and geomorphometric context [J].International Journal of Geographical Information Science,   
2011,25(6): 1011-1023. [4] MacmillanRA,MoonDE,Ray A.et al.Automated predictive ecological mapping ina Forest Region of B.C.Canada,2O01-2005 [J].Geoderma,2007,140(4): 353-373. [5]秦承志,卢岩君,邱维理,等.模糊坡位信息在精细土壤属性空 间推测中的应用[J].地理研究,2010,29(9):1706-1714.[Qin Chengzhi,Lu Yanjun,Qiu Weili,etal.Application of fuzzy slope positions in predicting spatial distribution of soil property at finer scale[J]. Geographical Research,2010,29(9): 1706-1714.] [6] 邱海军,崔鹏,胡胜,等.陕北黄土高原不同地貌类型区黄土滑 坡频率分布[J].地球科学,2016,41(2):343-350.[Qiu Haijun, Cui Peng,Hu Sheng,et al. Size- frequency distribution of landslides in different landforms on the Loess Plateau of Northern Shaanxi[J].Earth Science,2016,41(2): 343-350.] [7]汤国安,那嘉明,程维明.我国区域地貌数字地形分析研究进展 [J].测绘学报,2017,46(10):1570-1591.[Tang Guo'an,Na Ji

aming,Cheng Weiming.Progress of digital terrain analysis on re

gional geomorphology in China[J].Acta Geodaetica et Cartographica Sinica,2017,46(10): 1570-1591.]   
[8]程维明,周成虎,申元村,等.中国近40年来地貌学研究的回顾 与展望[J].地理学报,2017,72(5):755-775.[Cheng Weiming, Zhou Chenghu, Shen Yuancun,et al. Retrospect and perspective of geomorphology researches in China over the past 4O years[J]. Acta Geographica Sinica,2017,72(5): 755-775.]   
[9]王彦文,秦承志.地貌形态类型的自动分类方法综述[J].地理与 地理信息科学,2017,33(4):16-21.[Wang Yanwen,Qin Chengzhi.Review of methods for landform automatic clasification[J]. Geography and Geo-Information Science,2017,33(4): 16-21.]   
[10]Gonzalo-Martin C,Lillo-Saavedra M,Menasalvas E,et al. Local optimal scale in a hierarchical segmentation method for satelite images An OBIA approach for the agricultural landscape[J]. Journal of Intelligent Information Systems,2016,46(3): 517-529.   
[11] 王晓峰,延雨,李月皓,等.银川市湿地景观演变及其驱动因素 [J].干旱区研究,2021,38(3): 855-866.[Wang Xiaofeng, Yan Yu, Li Yuehao,et al.Wetland landscape evolution and its driving factors in Yinchuan[J].Arid Zone Research,2021,38(3): 855-866.]   
[12]周成虎,程维明,钱金凯.数字地貌遥感解析与制图[M].北京: 科学出版社,2009:4-9.[Zhou Chenghu,Cheng Weiming,Qian Jinkai.Digital Geomorphological Interpretation and Mapping from Remote Sensing[M]. Beijing: Science Press,2009: 4-9.]   
[13] 王乐,周毅,李阳.面向子流域单元的典型黄土地貌分类研究 [J].干旱区研究,2019,36(6):1592-1598.[Wang Le, Zhou Yi,Li Yang.Classification of typical loess landforms in subcatchments [J]. Arid Zone Research,2019,36(6): 1592-1598.]   
[14]Maria Dekavalla, Demetre Argialas. Evaluation of a spatially adaptive approach for land surface classification from digital elevation models[J]. Taylor & Francis,2017,31(1O):1-23.   
[15] 常直杨,孙伟红,王建,等.青藏高原及其邻近地区地貌类型划 分[J].山地学报,2017,35(1):1-8.[Chang Zhiyang,Sun Weihong,Wang Jian,et al. Object-oriented method based on classification of geomorphic type in the Tibet Plateau and adjacent regions[J]. Mounta in Research,2017,35(1): 1-8.]   
[16] 曹泽涛,方子东,姚瑾,等.基于随机森林的黄土地貌分类研究 [J].地球信息科学学报,2020,22(3): 452-463.[Cao Zetao,Fang Zidong,Yao Jin,et al.Loess Landform classification based on random forest[J]. Journal of GeoInformation Science,2020,22(3):

4J∠-405.] [17] 陈春秀,陈蜀江,徐世薇,等.多特征辅助下的GF-6WFV影像 准噶尔山楂识别研究[J].干旱区研究,2021,38(2):553-561. [Chen Chunxiu, Chen Shujiang,Xu Shiwei, et al. Crataegus songarica recognition using Gaofen-6 wide-field-view data assisted by multiple features[J]. Arid Zone Research,2021,38(2): 553-   
561.] [18] 曹伟超,陶和平,孔博,等.利用最佳地形特征空间进行地貌形 态自动识别——以西南地区为例[J].武汉大学学报(信息科学 版),2011,36(11):1376-1380.[Cao Weichao,Tao Heping,Kong Bo,et al. Topographic automatic recognition based on optimal topography feature space: Taking Southwest China as an Example [J].Geomatics and Information Science of wuhan University,2011,   
36(11): 1376-1380.] [19] 王丽娜,丁文广,许丹阳.基于DEM的甘肃省地貌形态特征分 类[J].水土保持通报,2019,39(1):264-269.[Wang Lina,Ding Wenguang,Xu Danyang.DEM- Based geomorphological features of Gansu Province[J].Bulletin of Soild and Water Conservation,   
2019,39(1): 264-269.] [20] Jasiewicz J, Stepinski TF. Geomorphons: A patern recognition approach to classification and mapping of landforms[J]. Geomorphology,2013,182: 147-156. [21] 康鑫,王彦文,秦承志,等.多分析尺度下综合判别的地形元素 分类方法[J].地理研究,2016,35(9):1637-1646.[Kang Xin, Wang Yanwen, Qin Chengzhi, et al.A new method of landform element classificationbased on multi- scale morphology[J]. Eographical Research,2016,35(9): 1637-1646.] [22] 张宗祜.中国黄土高原地貌类型图[M].北京:地质出版社,   
1985.[Zhang Zonghu. Geomorphic Types of Loess Plateau in China[M]. Beijing: Geological Publishing House,1985.] [23]Haralick R M, Shanmugam K, Dinstein I. Textural features for image classification[J]. IEEE Transactions on Systems, Man, and Cybernetics,1973,SMC-3(6): 610-621. [24]Jasiewicz J, Netzel P, Stepinski T.GeoPAT: A toolbox for patternbased information retrieval from large geospatial databases[J]. Computers & Geosciences,2015,80: 62-73. [25] Xiong Liyang, Zhu Axing, Zhang Lei,et al. Drainage basin objectbased method for regional- scale landform classification: A case study of loess area in China[J]. Physical Geography,2018,39(6):   
1-19.

# A multi-scale integrated classification method for landforms

YANG Weitao123,，SUN Jianguo123，MA Hengli12，HUANG Zhuol12.3   
(1.FacultyofGeomatics,Lanzhou Jiaotong University,Lanzhou 73oo7o,Gansu,China;2.National-Local Joint   
Engineering Research Centerof Technologies and Applications forNational Geographic State Monitoring,Lanzhou   
730070,Gansu, China;3.Gansu Provincial Engineering Laboratory for National Geographic State Monitoring, Lanzhou 730070,Gansu, China

Abstract: Landform objects span a broad range of sizes.Existing automatic landform classification methods do not fully consider size,however，which restricts classification accuracy.This study proposes a multi- scale integrated classification method forlandform thatconsiders the size of diffrent features.The method consists of three steps: multi-scale segmentation,screening according to scale order,and multi-scale merging. The screening according to scale order is an iterative confirmation process of classified objects based on multi-scale feature extraction and supervised clasification,with small scale (small size) priority and probability maximization as criteria.According to experimental results from the Loess Plateau,the method is simple and reliable(overall accuracy reached $7 5 . 1 6 \%$ and the Kappa coefficient reached O.71） and can be used for detailed classification of landform.

Keywords: landforms; classification; multi-scale; Loess Plateau

# 欢迎订阅2022年《干旱区研究》

《干旱区研究》是由中国科学院新疆生态与地理研究所和中国土壤学会共同主办的，以干旱区水、土、生物、气候四种可再生资源的研究为主要内容的综合性学术期刊,其内容包括干旱区生态及其生态系统与环境;干旱区自然资源的动态变化及相互作用；干旱区与大气圈、水圈、生物圈、岩石圈和人类活动之间的相互作用;干旱区生态与建设;全球变化与干旱区；干旱区减灾、防灾;先进技术在干旱区开发与研究中的应用。依靠广大的科学工作者，开展广泛而深入的基础理论研究，为我国培养和造就大批的干旱区资源与环境的科技人才。本刊适合从事干旱区研究的专家、学者、科技人员及相关院校师生阅读参考。

国内统一刊号:65-1095/X,本刊为国际大16开本,双月刊,312页，单月15日出版,每册70元。

欢迎新老客户及时到当地邮局订阅，邮发代号：58-37。若有漏订者可直接搜淘宝店、微店店铺名称“中科期刊"或扫描下方二维码进行订阅。

编辑部地址：乌鲁木齐市北京南路818号  
邮编：830011  
电话：0991-7827349  
E-mail: azr@ms.xjb.ac.cn  
http://azr.xjegi.com