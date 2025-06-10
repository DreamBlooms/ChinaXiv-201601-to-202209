# 基于遥感指数的区县级生态环境评价

张亚球¹，姜放¹，纪梦达'，姜海山‘，王子彦²（1.长春工程学院勘查与测绘工程学院，吉林 长春130021;2.桂林理工大学测绘地理信息学院，广西 桂林541004)

摘要：基于遥感生态指数(RSEI)能够对生态环境实现快速的监测和评价,RSEI的提出为遥感生态评价提供了一种新的方法。针对RSEI的应用问题,本研究选取吉林省长春市主城区、内蒙古赤峰市翁牛特旗中东部半干旱区、青海省西宁市北川河自然保护区为试验区,分别在指数优化和细节表征两方面进行了研究，从近20个指数中选定最优指数并将以主成分分析法和多元线性回归法得到的结果进行细节表征对比,旨在探索适用于区县级的生态评价方法。结果表明：(1）以固定指数构成的RSEI模型在细部表征较差,存在较多误判;(2）同样使用PCA法以优化后的指数构建的RSEI(NEW)模型对细节信息的保留较前者要好,在主城市区的结果相较于其余模型更好；（3）利用逐步多元线性回归模型以优化后的指标参与构建的MLR(RSEI在半干旱区和生态区的结果最佳。试验表明,以最优指数参与的多元线性回归模型能够较好的保留细部特征,对复杂环境的区县级小区域生态评价具有较强的适用性。

关键词：生态评价；遥感指数；多元线性回归；主成分分析；遥感生态指数(RSEI)

2006年国家环保局通过了《生态环境状况评价技术规范(试行)》（以下简称"技术规范")，给出了生态环境状况指数(EcologicalIndex,EI)的计算公式，许多学者开始尝试使用EI进行环境评价，但EI计算所需数据主要依赖土地利用分类和统计数据，在数据收集上存在很大难度。近年来，有学者开始研究基于遥感影像的改进EI计算，以专家打分、层次分析、隶属函数等方法确定权重以计算EI指数，但所选取的数据存在较大差异，难以形成指标上的统一。徐涵秋借助主成分分析法结合绿度、干度、湿度、热度4个指标创建了完全基于遥感影像的遥感生态指数(Remote Sensing Ecological Index,RSEI)并在福州市进行了验证，结果表明RSEI与EI指数存在较好的一致性。RSEI的提出使得完全基于遥感数据的生态质量快速评价更容易实现，得到了许多学者的青睐。王士远等使用RSEI对长白山生态环境进行了评价；李鸿芝3使用RSEI对巢湖流域生态质量的时空变化进行了分析；宋美杰等4将RSEI应用于锡林郭勒草原的生态评价研究。

RSEI模型的提出是应用于福州市主城区生态环境评价,指数的选择为NDVI、NDBSI、LST、Wet,但是并未给出指数的选择依据，并且PCA法容易忽视细节，不适合区县级小区域生态评价，同时很多指数都有着一定的局限性。例如，NDVI在中度植被覆盖度地区适用性较好，当其应用在半干旱区、生态区研究时，指数灵敏度有所降低，可能会对结果产生不确定性影响。不同的研究区差异较大，以固定的4个指数评价受地域、气候、降水等因素综合影响的复杂环境状况的可行性有待验证。

戚涛5将专家打分法提取的EI作为因变量以9个指标构建了回归方程与主成分分析法得到的结果进行环境评价，结果表明主成分分析法的结果会忽视较多细节，更适用于大范围的研究；周文英发现以土地覆盖、景观指数、降水、气温、高程、坡度等多个指标参与草原湿地环境评价可以更真实客观地反映生态环境状况。

由于目前没有通用遥感生态指数，因此本文在前人研究基础上，进行延续性探索。在指数选择上综合考量了近20个指数，以相关度选取最优参数，在方法上选择了逐步多元线性回归和主成分分析法分别确定各指标权重构建模型，并进行细节表征对比。旨在给出指数的选择依据，同时探寻适用于区县级小区域的模型构建方法生态质量评价方法。

# 研究区及试验数据

研究区包括城市区、半干旱区、生态保护区三类，分别是地处东北平原腹地，介于东部山地湿润与西部平原半干旱区之间的过渡带的吉林省长春市主城区；地处大兴安岭西南段科尔沁沙地西部的内蒙古自治区赤峰市翁牛特旗中东部的半干旱区;以及位于青藏高原和黄土高原过渡地带的青海省西宁市大通县北川河自然保护区涉及的5个乡镇。

试验数据包括：Landsat8影像数据，获取自美国地质勘查局USGS(https://earthexplorer.usgs.gov/) 3期影像为2014年9月7日的长春市主城区数据、2015年8月15日的翁牛特旗半干旱区数据、2015年8月21日的北川河自然保护区影像数据。图像成像清晰，云量低于 $3 \%$ ,数据经过辐射定标、大气校正、镶嵌、裁剪等预处理；DEM数据获取自地理空间数据云（http://www.gscloud.cn/)提供的ASTER GDEM$3 0 \mathrm { ~ m ~ }$ 数据; $\mathrm { P M } _ { 2 . 5 }$ 数据获取自NASA（https://search.earthdata.nasa.gov/)相对应年份的 $\mathrm { P M } _ { 2 . 5 }$ 全球格网数据；NPP-VIIRS夜间灯光数据获取自美国国家海洋和大气管理局NOAA(https://ngdc.noaa.gov/）,研究区的行政区划数据获取自Open Street Map(https://wiki.openstreetmap.org/）

# 2 试验内容

# 2.1试验模型

RSEI即遥感生态指数，利用湿度、绿度、热度、十度4个直接反映生态环境质量优劣的指标对生态环境质量变化进行评价，以湿度指数(Wet）、归一化植被指数(NDVI)、地表温度指数(LST)、裸土指数(NDBSI)分别对应4个指标，以主成分分析法选取第一主成分构建RSEI。其遥感定义为：

$$
{ \mathrm { R S E I } } { = } f ( \mathrm { W e t , N D V I , L S T , N D B S I } )
$$

# 2.2试验指数选择

完全基于遥感影像的生态评价可以用水热指数和植被覆盖表示。本文结合前人的研究，借助ENVI5.5软件，在指数选取上对多指数进行综合考量。选择了绿度、干度、湿度、热度4个指标进行模型构建。参考前人的研究成果，绿度指数选择了几种常见的植被指数，即比值植被指数(RVI)增强型植被指数(EVI）、NDVI,同时针对研究区有低矮灌木和稀疏植被覆盖区，因此，引用对土壤背景有抑制的MSAVI指数。考量到部分研究区植被覆盖差异较大，部分指数不适用于低、高植被覆盖区，此处引用Zhang等7利用光谱分解模式推导的较适用于植被监测的通用归一化植被指数（UniversalNormal-izedVegetationIndex,UNVI),绿度指数计算公式参考文献[7-9」；干度指数选择了：建筑用地指数(IBI）、裸土指数(SI）、NDBSI、归一化差值建筑用地指数(NDBI),干度指数计算公式参考文献[10-11];考虑到3个研究区皆存在植被覆盖，因此，引用归一化水指数(NDWI)监测植被水分，以及归一化差异湿度指数(NDMI）、归一化差分水体指数(MNDWI)，湿度指数计算参考文献[12-13」；同时考虑到缨帽变换较好地抑制了山体阴影，突出了背景地物和纹理特征，因此引入了K-T变换的湿度（Wetness）、绿度（Greeness）、亮度分量(Brightness）[14];使用大气校正法计算了LST,由于研究区有干旱区，因此,选取了2种基于Ts-NDVI特征空间提取的条件温度植被指数（VTCI)，温度植被干旱指数(TVDI)，此处统称为热度指数，热度指数计算参考文献[15-16」。本文拟采用RSEI为因变量构建多元线性回归模型，为了避免单一因变量可能会影响分析的结果，又考虑到"技术规范"中EI指数所需数据较复杂且难以获取。因此本研究参考了徐永明[7以夜间灯光数据、全球 $\mathrm { P M } _ { 2 . 5 }$ 格网数据以及遥感影像构建的EI指数作为第二因变量参与分析。

# 2.3主要试验内容

分别以RSEI和EI作为因变量，对城市区、半干旱区、生态保护区进行研究，以多指数作为自变量分析相关性选择最优参数进行主成分分析和构建线性回归方程，同时对方程的合理性进行验证，并将得到的结果进行对比。用水体掩膜裁去水体部分，提取指数并标准化至 $0 \sim 1 0 0$ 之间。主要试验如下：

（1）以NDVI、NDBSI、LST和Wet计算RSEI

应用主成分分析法分别计算3个研究区的RSEI，根据文献4的研究，仅选取第一主成分构建的RSEI模型会丢失很多细节，而PCA法得到的第四主成分存在较多噪声点。考虑到影像信息大多聚集在前两个主成分，因此本研究选取第一、第二主

# 表1RSEI主成分分析结果

Tab.1 Principal component analysis of RSEI   

<html><body><table><tr><td>研究区</td><td>主成分</td><td>NDBSI</td><td>LST</td><td>WET</td><td>NDVI</td><td>特征值</td><td>特征值 贡献率/%</td></tr><tr><td rowspan="4">长春市 主城区</td><td>PC1</td><td>-0.64222</td><td>-0.48257</td><td>0.34267</td><td>0.4871</td><td>970.51843</td><td>85</td></tr><tr><td>PC2</td><td>-0.2707</td><td>0.67423</td><td>0.66842</td><td>-0.15919</td><td>101.04461</td><td>9</td></tr><tr><td>PC3</td><td>-0.24459</td><td>0.55889</td><td>-0.52052</td><td>0.59739</td><td>54.4442</td><td>5</td></tr><tr><td>PC4</td><td>0.67413</td><td>0.0138</td><td>0.406</td><td>0.61686</td><td>12.27399</td><td>1</td></tr><tr><td rowspan="4">翁牛特旗 干旱区</td><td>PC1</td><td>-0.4782</td><td>-0.44141</td><td>0.54732</td><td>0.52624</td><td>1 115.715</td><td>88</td></tr><tr><td>PC2</td><td>-0.09052</td><td>0.87128</td><td>0.44528</td><td>0.18547</td><td>110.9511</td><td>9</td></tr><tr><td>PC3</td><td>0.57072</td><td>0.01622</td><td>-0.24244</td><td>0.78437</td><td>23.33182</td><td>2</td></tr><tr><td>PC4</td><td>0.66137</td><td>-0.21391</td><td>0.66588</td><td>-0.27099</td><td>15.05911</td><td>1</td></tr><tr><td rowspan="4">北川河 自然保护区</td><td>PC1</td><td>-0.30185</td><td>-0.56237</td><td>0.5064</td><td>0.57981</td><td>2 360.491</td><td>77</td></tr><tr><td>PC2</td><td>0.51551</td><td>0.47965</td><td>-0.69936</td><td>-0.12278</td><td>570.6199</td><td>19</td></tr><tr><td>PC3</td><td>0.67015</td><td>-0.66968</td><td>-0.02138</td><td>0.31933</td><td>108.8653</td><td>3</td></tr><tr><td>PC4</td><td>0.4405</td><td>0.07212</td><td>0.50397</td><td>-0.73944</td><td>32.73108</td><td>1</td></tr></table></body></html>

成分构建RSEI(表1)。

(2）以最优指数构建模型RSEI(NEW)、EI(NEW)

分别以RSEI、EI生态指数为因变量，贯穿全影像随机拾取60000个样本点以相关性绝对值选取最优指数，以主成分分析法确定每个主成分的权重，选取前2个主成分构建指数优化后的RSEI(NEW)、EI(NEW),相关性分析结果见表2。

由表2可知，在主城区2个因变量选择的最优指数均为UNVI、NDMI、NDBSI、VTCI；在半干旱区，以EI为因变量选取的最优指数为EVI、Wet、NDMI、TVDI,以RSEI为因变量选取的最优指数为UNVI、NDMI、NDBI、TVDI;在生态区，EI与其余指数相关性较低，因此，仅以RSEI为因变量选取最优指数。由于研究区位于高海拔地区，热度因子变化较小因此相关度较低，故此处引用地形因子(DEM)参与相关性分析，相关度为-0.666,则选取UNVI、NDBSI、NDMI、DEM作为生态区的最优指数。

（3）以最优指数构建线性回归方程MLR(RSEI)和 MLR(EI)

分别使用表2中以RSEI、EI为因变量选取的最优参数构建逐步多元线性回归模型以确定权重和常数项。以主城区为例，根据下式进行多元线性回归模型构建：

$$
\mathrm { M L R } ( \mathrm { R S E I } ) { = } \alpha _ { 0 } + \alpha _ { 1 } \mathrm { U N V I } + \alpha _ { 2 } \mathrm { N D M I } +
$$

$$
\alpha _ { 3 } \mathrm { { N D B S I } } + \alpha _ { 4 } \mathrm { { V T C I } }
$$

式中： $\alpha _ { i } ( i \mathrm { = 1 } , 2 , 3 , 4 )$ 表示各个参数的权重； $\alpha _ { 0 }$ 表示常数项。

根据不同因变量选取的最优指数按研究区分别构建多元线性回归方程，各参数的显著性检验概率$P$ 值皆小于显著性水平0.05,说明建立的模型恰当。

长春市主城市区模型如下：

$\mathrm { M L R ( E I ) } = 0 . 0 3 3 \mathrm { U N V I } + 0 . 6 5 2 \mathrm { N D M I } -$ (3)$1 . 0 0 7 \mathrm { N D B S I } - 0 . 0 5 4 \mathrm { V T C I } + 1 3 . 4 2 9$   
$\mathrm { M L R } ( \mathrm { R S E I } ) { = } 0 . 4 9 1 \mathrm { U N V I } + 0 . 2 2 5 \mathrm { N D M I } -$ (4)$0 . 4 0 2 \mathrm { N D B S I } - 0 . 1 6 7 \mathrm { V T C I } + 1 7 . 8 2 8$ 翁牛特旗半干旱区模型如下：  
$\mathrm { M L R ( E I ) } { = } 0 . 1 7 7 \mathrm { E V I - } 0 . 2 0 2 \mathrm { N D B I + } 0 . 1 7 5 \mathrm { W e t - }$ (5)$0 . 0 4 7 \mathrm { T V D I } + 1 6 . 5 6 1$ $\mathrm { M L R ( R S E I ) } = 0 . 7 7 9 \mathrm { U N V I } - 0 . 2 1 6 \mathrm { N D B I } +$ (6)$0 . 1 6 3 \mathrm { N D M I } - 0 . 2 7 8 \mathrm { T V D I } + 3 2 . 4$ 北川河自然保护区模型如下：$\begin{array} { r } { \mathrm { M L R } ( \mathrm { R S E I } ) = 0 . 2 2 7 \mathrm { U N V I } + 0 . 6 5 0 \mathrm { N D M I } - \phantom { 0 . 0 0 0 0 0 } } \\ { 0 . 3 8 8 \mathrm { N D B S I } - 0 . 4 9 \mathrm { D E M } + 3 0 . 9 9 4 \phantom { 0 . 0 0 0 0 } } \end{array}$ (7)

# 3细部表征分析

# 3.1长春市主城区

在上述模型构建后，需要对优化前和优化后的指数在细节表征上对比，旨在寻找适合于区县级小范围的生态监测的方法。由不同方法及参数计算的主城市区整体情况如图1所示。

由图1可以看出，长春市主城区EI计算结果在城市中心区呈现偏黄，即城市中心区生态优于城市边缘，与实际情况不符；由MLR(EI)构建的模型在城市东部地区表征不好，即将森林区判别为生态较差地区，与实际情况不符。因此，将由EI指数参与构

# 表2相关性分析

Tab.2 Correlation analysis   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">绿度相关性</td><td colspan="3">干度相关性</td><td colspan="3">湿度相关性</td><td colspan="3">热度相关性</td></tr><tr><td></td><td>EI</td><td>RSEI</td><td></td><td>EI</td><td>RSEI</td><td></td><td>EI</td><td>RSEI</td><td></td><td>EI</td><td>RSEI</td></tr><tr><td rowspan="6">长春市</td><td>Green</td><td>0.70</td><td>0.91</td><td>Bright</td><td>-0.55</td><td>-0.55</td><td>Wet</td><td>0.67</td><td>0.82</td><td>LST</td><td>-0.61</td><td>-0.85</td></tr><tr><td>RVI</td><td>0.76</td><td>0.89</td><td>SI</td><td>-0.82</td><td>-0.97</td><td>NDMI</td><td>0.79</td><td>0.97</td><td>VTCI</td><td>0.65</td><td>0.88</td></tr><tr><td>EVI</td><td>0.60</td><td>0.75</td><td>IBI</td><td>-0.81</td><td>-0.97</td><td>NDWI</td><td>-0.70</td><td>-0.90</td><td>TVDI</td><td>-0.65</td><td>-0.87</td></tr><tr><td>NDVI</td><td>0.75</td><td>0.93</td><td>NDBI</td><td>-0.78</td><td>-0.97</td><td>MNDWI</td><td>-0.45</td><td>-0.64</td><td></td><td></td><td></td></tr><tr><td>MSAVI2</td><td>0.67</td><td>0.85</td><td>NDBSI</td><td>-0.82</td><td>-0.98</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>UNVI</td><td>0.79</td><td>0.98</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="6">翁牛特旗半 干旱区</td><td>Green</td><td>0.60</td><td>0.96</td><td>Bright</td><td>-0.6</td><td>-0.79</td><td>Wet</td><td>0.68</td><td>0.98</td><td>LST</td><td>-0.25</td><td>-0.28</td></tr><tr><td>RVI</td><td>0.62</td><td>0.95</td><td>SI</td><td>-0.61</td><td>-0.97</td><td>NDMI</td><td>0.63</td><td>0.97</td><td>TVDI</td><td>-0.54</td><td>-0.86</td></tr><tr><td>EVI</td><td>0.66</td><td>0.96</td><td>IBI</td><td>-0.25</td><td>-0.29</td><td>NDWI</td><td>-0.63</td><td>-0.93</td><td>VTCI</td><td>0.53</td><td>0.85</td></tr><tr><td>NDVI</td><td>0.65</td><td>0.95</td><td>NDBI</td><td>-0.62</td><td>-0.98</td><td>MNDWI</td><td>-0.64</td><td>-0.92</td><td></td><td></td><td></td></tr><tr><td>MSAVI</td><td>0.61</td><td>0.97</td><td>NDBSI</td><td>-0.61</td><td>-0.95</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>UNVI</td><td>0.64</td><td>0.98</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="6">北川河 自然保护区</td><td>Green</td><td>0.01</td><td>0.31</td><td>Bright</td><td>-0.01</td><td>-0.31</td><td>Wet</td><td>0.01</td><td>0.87</td><td>LST</td><td>0.01</td><td>0.06</td></tr><tr><td>RVI</td><td>0.17</td><td>0.78</td><td>SI</td><td>-0.02</td><td>-0.90</td><td>NDMI</td><td>0.02</td><td>0.91</td><td>TVDI</td><td>0.01</td><td>0.06</td></tr><tr><td>EVI</td><td>0.09</td><td>0.78</td><td>IBI</td><td>-0.02</td><td>-0.91</td><td>NDWI</td><td>-0.01</td><td>-0.78</td><td>VTCI</td><td>0.01</td><td>-0.07</td></tr><tr><td>NDVI</td><td>0.02</td><td>0.81</td><td>NDBI</td><td>-0.02</td><td>-0.91</td><td>MNDWI</td><td>-0.01</td><td>-0.39</td><td></td><td></td><td></td></tr><tr><td>MSAVI</td><td>0.01</td><td>0.75</td><td>NDBSI</td><td>-0.02</td><td>-0.91</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>UNVI</td><td>0.021</td><td>0.89</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

![](images/cbc7d434c66f8808c2d01cee637ca10cd6026bc9b055d599c9fca878236c69b1.jpg)  
图1长春市主城区各评价模型结果  
Fig.1 Results of evaluation models in main urban area of Changchun

建的模型剔除,选取RSEI、MLR(RSEI)和RSEI(NEW)继续进行细节对比(图2)。

将图像标准化至 $0 \sim 1 0 0$ ，五等分进行细节对比数值越大代表生态越好。通过GoogleEarth地理链接查看实际地表发现第a列主要为建筑和植被混合区，植被覆盖较为集中，根据判读比对，发现MLR(RSEI)和RSEI存在较严重细节忽略现象，RSEI(NEW)细节表征相对较好；第b列图像中心为低矮植被覆盖,覆盖度较低,四周为农田,则RSEI(NEW)的表征结果相对较好;第c列为规则建筑群，由对比

a） (b） C  
(1) 三趙記 套  
(2)生态等级0\~20  
(3) 注 20\~4040\~60心 60\~8080\~100RSEI(NEW) MLR(RSEI) (RSEI)

可以发现,RSEI(NEW)和MLR(RSEI)能够较好的识别规则建筑群，而在RSEI中会将建筑群连通，对复杂的地表识别会存在细节丢失的现象。对比发现细节表征优劣顺序为： ${ \mathrm { R S E I } } ( { \mathrm { N E W } } ) { \mathrm { > M L R } } ( { \mathrm { R S E I } } ) >$ RSEI。

# 3.2翁牛特旗中东部半干旱区

由不同方法及参数计算的半干旱区整体情况如图3所示。

根据实际情况，EI和MLR(EI)的结果对农田覆盖区的判别与实际不符，原因可能是参与EI计算的数据分辨率较低，故排除EI和MLR(EI)结果。对剩下的四个结果进行细节对比(图4)。

通过GoogleEarth地理链接，查询实际的地表情况发现，第a行的图像中心点位于规则的农作物种植区，由图4可知，MLR(RSEI)能够保留农田之间的较宽道路，而以固定指数计算的RSEI则完全将此忽略，由最优参数组成的RSEI也能保留一定的细节；第b行上半区域为沙地，生态情况较差，而RSEI明显划分的结果存在错误;第c行为稀疏的林地种植区，生态环境较差且右侧有无植被覆盖区，因此，在图像上应呈现出一小块生态较差的地区。图4中，RSEI和EI(NEW均将此处忽略。则试验得到的结果精度为:MLR(RSEI)>RSEI(NEW) $\mid >$ EI(NEW)>RSEI。

# 3.3北川河自然保护区

由不同方法及参数计算的北川河生态保护区整体情况如图5所示。

将图像标准化至0\~100，五等分进行细节对比。图6第a行为研究区北部的高山顶部，海拔近$4 0 0 0 \mathrm { ~ m ~ }$ ，因此生态环境较差。但本研究区选择的影像为8月，根据地理链接参考实际地貌，除了部分海拔较高区域以外，绿色植被覆盖较高，但RSEI的评价结果将成片区域判为生态差，与实际情况不符。优化后RSEI(NEW)判读精度有所提高，其中，以最优指数构成的多元线性回归模型得到的结果最好；第b行为山脊和山谷地区，地势较为陡峭，此时RSEI的判别精度较低，引入DEM指数为变量构成的RSEI(NEW)识别地物的精度则有所改善;第3行是海拔 $3 0 0 0 \mathrm { m }$ 左右的向阳坡，仅山顶部为无植被覆盖，此处RSEI的判别精度依旧较低。

![](images/9bd222f425514d61221fcce5c3d5fc4bdef1eb6f0abf24ef33ac41efde4fd0bb.jpg)  
图2长春市主城区生态评价细节对比  
Fig.2 Comparison of ecological evaluation details in main urban areas of Changchun   
图3翁牛特旗各评价模型结果   
Fig.3Results of evaluation models in Ongniud Banner

![](images/3e11d8b86679d13a31fa06f482ee0e237deb18bc21bdf920fef76ab57ab2cff3.jpg)  
Fig.4Comparison of ecological evaluation details in Ongniud Banner

![](images/4f7f30c67528f52d32cbdb107d0e1b617817d9bcb176b980b6c0e3fdecd68bc7.jpg)  
图4翁牛特旗生态评价细节对比  
图5北川河自然保护区各评价模型结果  
Fig.5Results of evaluation modelsin Beichuan riverNature Reserve

根据试验，即使本研究选取前2个主成分构成RSEI的总贡献率达到 $9 0 \%$ 以上，尽可能地减少主成分分析法丢失的细节，但在细节表征上结果依然较差，在复杂的城市区有严重的建筑物连通现象，在半干旱区和高海拔地区对复杂地貌判读较差；以最优指数构建的结果优于RSEI,能够较好地适用于城市区、半干旱区和自然保护区；以RSEI为因变量选取的最优指数构建的多元线性回归模型结果总体上最好，通过查看实际地貌发现其精度较高，通过对3个研究区的试验可发现其适用性较强。

# 4结论

由于目前没有统一的通用遥感生态指数，本研究使用2个因变量选取最优指数，并将由主成分分析法和多元线性回归法得到的结果与RSEI模型结果进行对比分析。根据对不同研究区域的试验，得到如下结论：

（1）以RSEI得到的结果在主城市区对规则建筑群的生态环境评价容易形成连通，对复杂地貌的灵敏度不高；在半干旱区，对大片干旱区中的块状植被容易造成误判;在地形起伏较大的高海拔生态保护区，热度值变化较小且相关性较低，容易造成大片区域的误判。

（2）以RSEI为因变量选取的最优指数构建的RSEI(NEW),在细节上相较于RSEI细部表征较好，以最优指数构建的RSEI(NEW)能够较好地保留复杂地表信息，在主城市区的结果较好。

![](images/1e6148705234ef5d2b4ded7eb23543158ecde3ca84bfa745433f9d2508de130c.jpg)  
图6北川河自然保护区生态评价细节对比 Fig.6Comparison of ecological evaluation details in Beichuan river

（3）以RSEI为因变量构成的多元线性回归模型整体上对细部信息保留最好，更接近地表真实情况。

（4）在地形起伏较大地区，应当考虑以地形因子代替热度因子。

(5）通过对城市区、半干旱区、生态保护区的模型对比发现，利用光谱分解模式构建的通用归一化植被指数(UNVI)相比于NDVI、EVI、MSAVI等常见的植被指数，在遥感生态研究上更具适用性。

将使用固定4个指数借助主成分分析法构建的遥感生态指数(RSEI)应用于复杂因素影响下的区县级小区域生态环境评价，由于主成分分析法自身会忽略较多细节，因此，评价结果较差，不适用于小区域的研究。同样借助于主成分分析法，以优化后的指数代替固定4个指数后的结果要优于RSEI。使用优化后的指数以多元线性回归法确定权重的MRL(RSEI)模型，更适用于区县级小区域生态环境监测。

# 参考文献(References):

[1]徐涵秋.城市遥感生态指数的创建及其应用[J].生态学报, 2013,33(24):7853-7862.[Xu Hanqiu.A remote sensing urban ecological index and its application[J].Acta Ecologica Sinica, 2013,33(24): 7853-7862.]   
[2] 王士远,张学霞,朱彤,等.长白山自然保护区生态环境质量的 遥感评价[J].地理科学进展,2016,35(10):1269-1278.[Wang Shiyuan, Zhang Xuexia, Zhu Tong,et al.Assessment of ecological

environment quality in the Changbai Mountain Nature Reserve based on remote sensing technology[J].Progress in Geography, 2016,35(10): 1269-1278. ]

[3]李鸿芝.基于RSEI的巢湖流域生态环境质量时空变化分析[J] 安徽农业科学,2019,47(16):82-86.[Li Hongzhi. Temporal and spatial changes of ecological environment quality in Chaohu Basin based on RSEI[J]. Journal of Anhui Agricultural Sciences,2019, 47(16): 82-86. ]   
[4]宋美杰,罗艳云,段利民.基于改进遥感生态指数模型的锡林郭 勒草原生态环境评价[J].干旱区研究,2019,36(6):1521-1527. [Song Meijie,Luo Yanyun,Duan Limin. Evaluation of ecological environment in the Xinlin Gol steppe based on modified remote sensing ecological index model [J]. Arid Zone Research, 2019,36 (6): 1521-1527.]   
[5]戚涛.基于遥感的区域植被生态环境质量综合评价研究[D].武 汉：华中科技大学,2007. Qi Tao.The Study of Regional VegetationEcological Environment Quality IntegrativeEvaluation Based-on Remote Sensing [J].Wuhan: Huazhong University of Science and Technology,2007.]   
[6]周文英.基于遥感技术的草原湿地生态环境评价方法研究[D]. 成都：电子科技大学,2014.[Zhou Wenying,Research on Prairie Wetlands Ecological Environment Evaluation Method Based on Remote Sensing Technology[D]. Chengdu: University of Electronic Science and Technology of China,2014.]   
[7]孙勇.应用遥感数据对植被指数提取分析[D].哈尔滨:东北林 业大学,2017.[Sun Yong. The Application of Remote Sensing Technology to Extract and Analyse Vegetation Index[D].Haerbin: Northeast Forestry University,2017.]   
[8]Zhang Lifu,Qiao Na, Muhammad Hasan Ali Baig. Monitoring vegetation dynamics using the universal normalized vegetation index (UNVI):An optimized vegetation index- VIUPD[J]. Remote Sensing Letters,2019,10(7): 629-638.   
[9]胡顺石,张辰璐,乔娜,等.基于IDL语言的植被指数UNVI软件 插件[J].遥感学报,2019,23(5):952-958.[Hu Shunshi, Zhang Chenlu,Qiao Na,et al.Universal normalized vegetation index (UNVI) and UNVI software based on IDL[J]. Journal of Remote Sensing,2019,23(5): 952-958.]   
[10] 高鹏文,阿里木江·卡斯木,图尔荪阿依·如孜,等.哈密市生态 环境效益时空分析[J].干旱区研究,2020,37(4):1057-1067. [GAO Pengwen,Kasim Alimujiang,Ruzi Tursunayi,et al. Temporal and spatial analysis of ecological environment improvement in Hami City[J]. Arid Zone Research,2020,37(4):1057-1067.]   
[11] 许剑辉,赵怡,肖明虹,等.基于空间自回归模型的广州市NDVI 和 NDBI与气温关系研究[J].国土资源遥感,2018,30(2):186- 194.[Xu Jianhui, Zhao Yi, Xiao Minghong,et al.Relationship of air temperature to NDVIand NDBIin Guangzhou Cityusing spatial autoregressive model[J].Remote Sensing for Land & Resources,2018,30(2): 186-194.]   
[12]刘小磊.覃志豪.NDWI与NDVI指数在区域干旱监测中的比较

分析——以2003年江西夏季干旱为例[J].遥感技术与应用，

2007(5): 6O8-612.[Liu Xiaolei, Qin Zhihao. Comparative analysis between NDWI and NDVI indices in regional drought monitoring [J].Remote Sensing Technology and Application, 2O07(5): 6O8-612]   
[13] 李斌,王慧敏,秦明周,等.NDVI、NDMI与地表温度关系的对比 研究[J].地理科学进展,2017,36(5):585-596.[Li Bin,Wang Huimin,Qin Mingzhou,et al.Comparative study on the correlations between NDVI,NDMI and LST[J].Progress in Geography,2017, 36(5): 585-596.]   
[14]Baig MHA, Zhang L, Shuai T,et al. Derivation of a tasselled cap transformation based on Landsat 8 at-satellite reflectance[J]. Remote Sensing Letters,2014,5(4-6): 423-431.   
[15] 郭锯,王小平.遥感干旱应用技术进展及面临的技术问题与发 展机遇[J].干旱气象,2015,33(1):1-18.[Guo Ni,Wang Xiaoping.Advances and developing opportunities in remote sensing of drought[J].Arid Meteorology,2015,33(1): 1-18.]   
[16]黄资或.基于多源遥感数据的干旱/半干旱地区表层土壤水反 演方法研究[D].广州:华南农业大学,2016.[Huang Ziyu.The Study of Soil Moisture Retrieval Method Based on Multi-source Remote Sense Data in Arid and Semi-arid Area[D].Guangzhou: South China Agricultural University,2016.]   
[17]徐永明.ENVI遥感软件综合实习教程[M].北京:科学出版社, 2019:214-233.[Xu Yongming,ENVI Remote Sensing Software Integrated Practice Course[M]. Beijing: Science Press,2O19:214- 233.]

# Assessment of the ecological environment at district and county level based on remote sensing index

ZHANG Ya-qiu'， JIANG Fang'，JI Meng-da'， JIANG Hai-shan’， WANG Zi-yan² (1.Schoolof Prospecting and Surveying Engineering,Changchun Instituteof Technology,Changchun 130021, Jilin,China; 2.College of Geomatic Engineering and Geoinformation, Guilin University of Technology, Guilin 541004, Guangxi, China)

Abstract: A remote sensing (RS)ecological index can be used for rapid supervision and evaluation of anecological environment.The proposition of aremote sensing ecological index (RSEI) provides a new method for RS ecological evaluation.To testthe application of RSEI,we selected regions inthe main urbanareaof Changchun City,Jilin Province;thesemi-aridareain the middleand eastof Ongniud Banner,Chifeng City,Inner Mongolia;and the Beichuan River Nature Reserve,Xining City,Qinghai Province for index optimization and detail representation assessments.The best index of nearly 2O was chosen and the detail representation results were compared using principal component analysis (PCA) and multiple linear regression.The aim of this study was to explore the ecological assessment methods applicable to districts and counties.Theresults showed that the RSEI model comprised offixed indexesdoes not perform welland had more misjudgment.The RSEI(NEW) model,which is also constructed using the PCA method with theoptimized index,retains more detailed information thanthe former,and the results in the main urban area were beter than the remaining models.When a stepwise multiple linear regression (MLR) model is used to optimize the index,the MLR (RSEI) involved produced the best results in semiarid and ecological areas.The experiment demonstrated thatthe MLR model with optimal index participation has strong applicability to small districts and counties,retaining detailed characteristics.

Keywords:ecological evaluation;remote sensing index；multivariate linearregression;principal component analysis;remote sensing ecological index