# 黑河流域绿洲变化的模式与稳定性分析

董敬儒¹，颉耀文12\*，段含明1，王晓云¹，李汝嫣¹（1.兰州大学资源环境学院，甘肃 兰州730000;2.兰州大学西部环境教育部重点实验室，甘肃 兰州730000;3.西华师范大学国土资源学院，四川南充 637002）

摘 要：本文旨在探索黑河流域绿洲近55a的时空变化模式与稳定性。基于1963—2017年的16期多源遥感影像，提取了55a黑河流域绿洲空间分布信息，使用叠置分析、格网化等方法，分析黑河流域绿洲变化模式与稳定性的时空特征。结果表明：黑河流域绿洲以波动变化模式为主，波动绿洲主要分布在灌溉保证程度差和土壤盐渍化的地区；扩张绿洲呈现早期向内填充、中后期向外扩张的模式；退缩绿洲主要分布在生态脆弱的绿洲边缘。黑河流域绿洲总体上逐渐趋向稳定，下游绿洲稳定性低于中游；中游及下游的金塔、鼎新绿洲波动主要发生在早期，而下游额济纳绿洲的波动主要发生在中期。

关键词：绿洲；变化模式；稳定性；遥感；GIS；黑河流域

绿洲是干旱区由于自然资源尤其是水资源的不均匀分布形成的一种特有的地理景观[1-3]。由于水文、土壤、地形、气候等资源良好的组合优势，绿洲对生命系统有较高的承载能力，是干旱区人类生存和发展的重要场所[4-7]。绿洲的景观基质是荒漠，在自然环境变化和人类活动等因素的影响下，绿洲与荒漠的互相转化，构成了干旱区两个方向相反但相互联系的地理过程——荒漠化与绿洲化[6.8-9]。绿洲变化是干旱区绿洲化和荒漠化相互博弈的产物，研究绿洲扩张与退缩的时空变化过程、特征与规律，有助于深入理解绿洲化和荒漠化的时空变化及发展机制，并从这两个干旱区基本生态过程的双向转化中揭示绿洲的稳定性[10-11]。

黑河流域开发历史悠久，其中游地区是我国西部重要的粮食基地，下游额济纳地区是重要的牧区。因地处干旱半干旱地区，在气候和人类活动的影响下，黑河流域中下游地区生态系统脆弱，面临天然林草退化、土壤盐渍化、湖泊干涸等严峻的生态问题[12-14]，绿洲的稳定性受到威胁。而绿洲的稳定性直接影响着区域社会稳定和生态安全[I]。研究黑河流域绿洲的时空变化与稳定性，对流域生态恢复和绿洲的可持续发展具有重要意义。该流域的绿洲变化及稳定性研究已经被广泛开展[15-17]。

目前，绿洲稳定性研究多侧重于定性分析和评价指标体系。胡汝骥等[18]、段汉民等[19]定性分析了水资源量与绿洲稳定性之间的关系，其分析结果较为宏观、概括。韩德麟[20]、王忠静等[21]、Luo 等[22]、Chao 等[23]引入水热平衡、景观指数、植被 NDVI、绿洲冷岛效应等指标，定量评价了绿洲的稳定性，而韩洪凌等[24]、王耀斌等[17]、张平等[25]则尝试建立了基于多重指标的绿洲稳定性评价模型。这些基于指标与模型的研究，着重分析绿洲稳定性的时间变化特征，缺乏空间特征的研究。Xie等[26]发展了格网化分析方法，有效探测了黑河绿洲稳定性的空间分布特征。该方法在黑河、石羊河等绿洲区得到了广泛的应用。但该方法对绿洲稳定性变化的时间特征分析尚不充分。本文以黑河绿洲为例，使用体现时间变化特征的叠置分析和格网化分析方法，从绿洲化与荒漠化双向转化的角度出发，旨在探索黑河绿洲近55a的时空变化模式与稳定性。

# 1研究区概况

黑河发源于祁连山，流经甘肃河西走廊，最终流入内蒙古额济纳旗的居延海[27]。黑河流域是我国第二大内陆河流域，地理位置 $9 6 ^ { \circ } 0 4 ^ { \prime } { \sim } 1 0 2 ^ { \circ } 0 0 ^ { \prime } \mathrm { E }$ ， $3 7 ^ { \circ } 4 1 ^ { \prime } { \sim } 4 2 ^ { \circ } 4 2 ^ { \prime } \mathrm { N }$ 。该流域大部分地区为大陆性干旱气候，上游祁连山地区年降水量 $3 0 0 { \sim } 5 0 0 \mathrm { m m }$ ，且有雪冰融水补给，是径流形成区；中游河西走廊年降水量为 $1 0 0 { \sim } 2 5 0 \mathrm { m m }$ ，是绿洲的主要分布区，绿洲集中在山麓冲积扇和冲积平原；下游地区年降水量小于 $5 0 \mathrm { m m }$ ，是极端干旱地区，绿洲主要分布在河流沿岸及尾闾三角洲[10]。黑河绿洲主要分布在流域的中下游地区。行政区划上涉及甘肃省张掖市的甘州区、民乐县、临泽县、高台县、山丹县和肃南县，酒泉市的金塔县、肃州区，嘉峪关市和内蒙古自治区阿拉善盟的额济纳旗。其中，金塔绿洲、鼎新绿洲与额济纳绿洲位于流域下游，其他绿洲位于流域中游(图1)。

![](images/d33bdf74e43f95648e08e18c498fc179d544a1076a74f8a30f0f954e2279f213.jpg)  
图1黑河流域现代绿洲空间分布示意图  
Fig1.Spatial distribution of modern oasis in Heihe River Basin

# 2 数据与方法

# 2.1数据来源与绿洲信息提取

在已有数据集(Xie 等[26)的基础上，本文以时相更具可比性的 2014 年影像替换原数据集中的 2013年数据，并增加2011、2017年的数据，拓展了数据的时间序列。各年影像来源与分辨率详见表1。在提取绿洲信息前，分别对新增数据进行了系统辐射纠正和大气校正。在此基础上计算归一化差值植被指数（NDVI）和归一化差值水体指数（NDWI)，然后采用阈值分割法提取绿洲信息。并利用目视判读对自动提取的绿洲边界进行修正，从而获得了各期绿洲边界数据。

本文的绿洲范围[3.28]，包括自然及人工植被、水体、居民地、工业用地及绿洲内小块的荒地、空地等。在提取绿洲信息的过程中，绿洲内部的非绿洲斑块面积达到36个像元时，被标记为荒漠；小于等于3个像元的孤立绿洲不再纳入绿洲。

Tab.1 The source and resolution of images   

<html><body><table><tr><td>数据年份</td><td>数据来源</td><td>分辨率/m</td></tr><tr><td>1963,1968</td><td>KeyHole</td><td>2.7~7.5</td></tr><tr><td>1973,1977</td><td>Landsat MSS</td><td>79</td></tr><tr><td>1980</td><td>KATE-200</td><td>8.9</td></tr><tr><td>1986,1990,1993,1996,1999, 2002,2006,2009,2011,2014,2017</td><td>Landsat TM/OLI</td><td>30</td></tr></table></body></html>

# 2.2研究方法

# 2.2.1绿洲变化模式分析

根据土地利用类型在绿洲与荒漠之间的转换以及绿洲边界的变动特征，将绿洲变化模式区分为稳定不变、扩张变化、退缩变化和波动变化4类（表2)。绿洲的变化模式主要通过对不同样本年绿洲边界进行叠置分析得到[26]。叠加两个邻近样本年所提取的绿洲数据，可检测出该时段内没有发生变化的区域，增加和减少区域通过排除后一期和前一期数据中无变化的区域确定。整个研究时段内，所有邻近样本年的无变化区域的重叠部分为稳定不变的绿洲，所有增加区域和所有减少区域的重叠部分为波动变化的绿洲，所有增加区域排除处于波动变化的区域为扩张变化的绿洲，同理可得退缩变化的绿洲。对扩张变化的区域，还要关注其发生的具体年份，以便与现实的土地利用情况进行对应和解释；退缩变化通常具有分散、碎小的特征，发生的具体年份暂不予分析。

表1影像数据来源及分辨率  
表2绿洲变化模式  
Tab.2 The patterns of oasis change   

<html><body><table><tr><td>变化模式</td><td>含义</td></tr><tr><td>稳定不变</td><td>在研究时段内绿洲边界一直没有发生变化</td></tr><tr><td>扩张变化</td><td>在研究时段内的15个样本年间隔中，只在一个间隔内从荒</td></tr><tr><td>退缩变化</td><td>漠转变为绿洲，之后不再变回荒漠 在研究时段内的15个样本年间隔中，只在一个间隔内从绿</td></tr><tr><td></td><td>洲转变为荒漠，之后不再变回绿洲</td></tr><tr><td>波动变化</td><td>在研究时段内的15个样本年间隔中，在多个间隔内发生绿</td></tr></table></body></html>

# 2.2.2绿洲空间稳定性分析

绿洲稳定性表现为空间和时间上的稳定性，即随时间的推移，绿洲的空间位置和范围基本不发生大的变化。而绿洲与荒漠之间频繁相互转换，意味着该区域绿洲处于无序的发展过程中。所以，本文基于时间序列数据，从绿洲与荒漠双向转化强度的角度揭示绿洲稳定性的空间分布。

本文采用格网化绿洲空间动态度和累积动态度模型测度绿洲空间稳定性。土地利用单一动态度是常用的描述土地利用变化动态特征的指标之一，能有效表示土地利用类型数量特征的变化[29]，但不能体现土地变化动态特征的空间分布。马宗义等[30]提出了一种将单一动态度运算限定到格网单元内，以反映绿洲的空间变化的方法[31]。Pontius 等[32]、Luo 等[33]指出，单一动态度仅反应土地利用类型面积净变化，忽略了土地利用类型空间分布变化，会低估土地利用类型的总变化。综合Pontius与Luo 等的观点，笔者发展了格网化绿洲空间动态度模型。该模型采用总变化面积替代了净变化：

$$
T _ { \mathrm { g r i d } _ { T _ { 2 } - T _ { 1 } } } = \frac { \Delta U _ { \mathrm { i n } } + \Delta U _ { \mathrm { o u t } } } { S _ { \mathrm { g r i d } } } \times 1 0 0 \%
$$

式中： $\Delta U _ { \mathrm { i n } }$ 、 $\Delta U _ { \mathrm { o u t } }$ 分别为研究时段格网内绿洲扩张和退缩的面积； $S _ { \mathrm { g r i d } }$ 为格网单元面积;

$T _ { 1 } , T _ { 2 }$ 分别为研究初期和末期; $T _ { \mathrm { g r i d } }$ 表示格网内两期绿洲变化的动态度，理论取值范围为[0,1]。

为反映绿洲在长时间序列中的稳定性，需进一步计算格网化绿洲空间累积动态度，公式如下：

$$
C T _ { \mathrm { g r i d } } = \sum _ { i = 1 } ^ { n - 1 } T _ { \mathrm { g r i d } _ { T _ { i + 1 } - T _ { i } } }
$$

式中： $n$ 为样本年数。 $C T _ { \mathrm { g r i d } }$ 为绿洲格网累积动态度，理论最小值为0，理论最大值为样本年间隔数，本文为15。累积动态度取值越小，绿洲越稳定；反之越不稳定。

考虑到农民垦荒的新增田地斑块的边长通常小于 $1 ~ \mathrm { k m }$ ，为减少农民个体行为及绿洲边界数据质量对分析结果的影响，使分析结果更好地反映绿洲的整体变化，本文将各样本年的绿洲提取结果格网化为 $1 \mathrm { k m } \times 1 \mathrm { k m }$ 的格网单元。然后，逐格网计算格网化绿洲动态度及累积动态度，以累积动态度表示的绿洲变化波动剧烈程度反映绿洲的稳定性。

使用决策树确定每个格网波动最强烈的时段，从而分析绿洲稳定性的时间变化特征（图2)。将格网的时间变化序列分割为大致均匀的3个时段（见3.2节)。当绿洲在时间过程上均匀变化时，3个时段各自的累积动态度百分比均接近 $33 \%$ ，其标准差接近于0。在本文中取标准差为 $5 \%$ ，来判定3个时段变化是否均匀。当3个时段的累积百分比的标准差小于 $5 \%$ 时，变化均匀，无明显主导变化时段；超过 $5 \%$ 时，进一步根据各时段累积百分比的大小排序和差值来确定主导变化时段。其中，最大值与中间值的差值大于等于 $10 \%$ 时，最大值所在时段为主导时段；差值小于 $10 \%$ 时，最大值与中间值所在的两个时段为共同主导时段。

![](images/4aa7db6e72c9003b2edbeb637f87db3d15e9e15638b21ec5202758ed052a914c.jpg)  
图2累积动态度主导时段决策树  
Fig 2.The decision tree of judging the dominant period of $C T$

# 3结果与分析

# 3.1绿洲变化模式

图3呈现了黑河绿洲变化模式的空间分布，面积占比情况如表3所示。其中，波动变化是绿洲变化的主体，占整体绿洲（即全部年份绿洲范围的并集）的 $5 4 . 4 7 \%$ ；稳定不变、扩张变化和退缩变化的绿洲分别占 $2 6 . 4 2 \% . 1 7 . 7 8 \%$ 和 $1 . 3 2 \%$ 。波动绿洲广泛分布在下游地区，稳定不变和扩张绿洲主要分布在中游地区，而退缩绿洲零散分布于整个流域。

表3各变化模式绿洲面积占比

Tab 3 The proportion of each pattern of oasis change   

<html><body><table><tr><td>变化模式</td><td>总体</td><td>中游</td><td>下游</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td></td><td>百分比/%</td><td>面积/km²</td><td>百分比/%</td><td>面积/km²</td><td>百分比/%</td><td>面积/km²</td></tr><tr><td>波动模式</td><td>54.47</td><td>5277.00</td><td>46.34</td><td>3222.08</td><td>75.16</td><td>2054.92</td></tr><tr><td>稳定模式</td><td>26.42</td><td>2559.82</td><td>33.05</td><td>2297.79</td><td>9.58</td><td>262.03</td></tr><tr><td>扩张模式</td><td>17.78</td><td>1722.87</td><td>19.49</td><td>1355.20</td><td>13.45</td><td>367.67</td></tr><tr><td>退缩模式</td><td>1.32</td><td>127.86</td><td>1.13</td><td>78.39</td><td>1.81</td><td>49.47</td></tr><tr><td>合计</td><td>100</td><td>9687.55</td><td>100</td><td>6953.46</td><td>100</td><td>2734.09</td></tr></table></body></html>

下游绿洲的波动较大。波动变化的面积占下游绿洲面积的 $7 5 . 1 6 \%$ ，且分布十分广泛。扩张变化的面积占 $1 3 . 4 5 \%$ 。早期（1963一1968年）的扩张多为原绿洲内部间隙的填充，斑块较小，这些斑块在金塔绿洲和额济纳尾闾绿洲内部均匀分布；新近的扩张主要是绿洲外缘的拓展，金塔绿洲东南部的羊井子湾乡（图 4b）和金塔绿洲东北部大庄子乡与鼎新绿洲之间酒航公路沿线（图4a）尤为显著，前者始于1980s，后者主要发生在2006 年以后。稳定不变的面积占 $9 . 5 8 \%$ ，较大的斑块分布在金塔县城和额济纳旗政府驻地附近。退缩变化的面积占 $1 . 8 1 \%$ ，均呈细碎斑块状，多分布在绿洲边缘。

中游绿洲的整体稳定性高于下游。其中，波动变化占中游绿洲总面积的 $4 6 . 3 4 \%$ ，集中分布区包括民乐绿洲的大部和临泽绿洲中部；此外，张掖、临泽、高台绿洲的沿河地区以及酒泉、嘉峪关绿洲北侧的边缘地区也有分布。稳定不变的面积占 $3 3 . 0 5 \%$ ，集中分布在张掖、酒泉和高台绿洲的内部。扩张变化的面积占 $1 9 . 4 9 \%$ ，嘉峪关绿洲（图4c）、酒泉绿洲东中部（肃南县明花乡前滩村，图4f)、高台绿洲西部（骆驼城镇、明花乡政府驻地，图4e）和张掖-民乐绿洲相接处（图4d）较为突出。其中，嘉峪关绿洲、骆驼城镇绿洲和明花乡政府驻地周围绿洲的扩张，分别始于20世纪60、70和90年代，早期多表现为远离绿洲主体的“飞地”，而后逐渐与附近的绿洲主体相连。明花乡前滩村以及张掖一民乐相接处的扩张主要发生在2006年以后，以蔓延式扩张为主。退缩变化的面积占 $1 . 1 3 \%$ ，斑块较小且零星分布，大多位于绿洲边缘。

![](images/496c6493f077c497fa53abed0b3df959deb1eda76a9cedf81804c308231b8b10.jpg)  
图3黑河绿洲变化模式分布

Fig 3.The spatial and temporal distribution of change patterns in Heihe River Basin

# 3.2绿洲稳定性

用格网累积动态度表现了格网单元绿洲的稳定性（图4)。由于地块的实际变化通常以小斑块的方式发生，单个斑块的规模小于 $1 \mathrm { k m } \times 1 \mathrm { k m }$ ，所以，累积动态度的实际值远小于理论最大值15。研究区内累积动态度的实际范围为[0,7.5]，但高值占比较少， $8 1 . 4 6 \%$ 的格网累积动态度小于2.5，超过一半的格网累积动态度小于1.04。高值的格网累积动态度反映了绿洲的强烈波动。从空间分布看，下游的整体动态度较高。其中，金塔绿洲西北的西坝乡与东北的东坝镇、鼎新镇附近的河道沿岸和水库周边、额济纳旗境内的沿河地带及尾闾绿洲中，均出现较为集中的高值分布区，格网累积动态度多超过3，稳定性较差。中游的高值格网占比相对较少，集中分布在民乐绿洲北部和临泽绿洲中部的鸭暖镇，但聚集度远不及下游聚集区。整体而言，中游多数格网的累积动态度较低，绿洲相对稳定；下游的高值格网占比大，绿洲波动剧烈。

![](images/e74dbcdc8608bac44dc4ea6445b900a626b34f41b078ebb2cfabf4c2b92f57ef.jpg)  
图4黑河流域绿洲格网化累积变化强度的时空分布  
Fig 4.The spatial and temporal distribution of CK inHeihe RiverBasin

Xie 等[26]对黑河绿洲发展阶段进行了划分。本文新增的2011年以后的绿洲变化趋势（图5),与该文中 2002—2009 年的变化趋势一致。故本文采用与Xie等[26]相似的时段划分方式，将黑河绿洲变化划为1963—1980、1980—2002、2002—2017年3个时段，分别记录为“早、中、后”3个时段。根据绿洲变化主导时段分析的结果，可以进一步将绿洲变化的时段划分为“早、早中、中、中后、后、早后、全”7种模式。

大多数绿洲波动具有时间连续性，呈跳跃性变化的早后模式占比仅 $1 . 9 7 \%$ ；连续变化的早中、中后和全时段模式占比也较少，分别为 $1 4 . 1 2 \%$ 、 $5 . 3 5 \%$ 和 $5 . 8 4 \%$ 。研究区绿洲波动主导时段为早、中和后3个单时段模式，分别占 $2 6 . 8 3 \%$ 、 $2 3 . 2 7 \%$ 和 $2 2 . 6 2 \%$ 。

全时段模式绿洲中 $54 . 8 2 \%$ 格网的累积动态度小于等于1，结合变化模式的空间分布可知，这些绿洲主要为稳定不变绿洲，最显著的是张掖绿洲；在主导时段为后期的绿洲中，累积动态度小于等于1的格网占比最高（ $7 5 . 7 2 \%$ )，主要为扩张变化绿洲，高台绿洲西侧骆驼城镇波动主导时段为中期的绿洲，也为扩张变化绿洲；以上区域绿洲并没有发生波动，动态度为0或仅是由于扩张引起的。因此，虽然主导时段为早期、中期和后期的绿洲格网数量较为相似，但是以后期、中期为主导时段的绿洲中有较高比例的扩张模式绿洲，所以，主要在早期发生波动的绿洲要远多于中期和后期，绿洲波动存在减弱趋势。

中游绿洲及下游的金塔绿洲和鼎新绿洲的波动主导时段主要为早期。其中，金塔绿洲波动较为剧烈的西坝乡和东坝镇主导波动时段为早期；鼎新绿洲波动剧烈的区域主要发生在早、中期，部分沿河区域波动主要发生在后期；民乐绿洲北部波动主导时段主要为早期和中期；临泽绿洲中部波动主导时段为早期，小部分为中期和全时段；而下游额济纳沿河绿洲及尾闾绿洲波动剧烈区域的主导时段为中期。随着时间的推移，绿洲呈现逐渐稳定的趋势，而以狼心山水文站为界，其上游绿洲主导时段为早期，其下游额济纳绿洲的主导时段为中期。

![](images/7f3a2f9e10173ea2608ae1b19bf22dcb4157c9521057dc7898e2559182f6be0c.jpg)  
图5黑河流域绿洲的面积变化  
Fig 5.Broken line diagram of oasis area variation in Heihe River Basin

# 4讨论

# 4.1典型扩张模式绿洲变化原因

绿洲的扩张变化在空间上存在两种模式，即绿洲主体内部碎部的填充和绿洲外部的向外拓展。前者主要发生在早期尤其是1963—1968年，后者主要发生在中后期。绿洲向外拓展存在两种方式，一种是在绿洲主体边缘逐步向外蔓延，典型斑块如，金塔县的羊井子湾乡、张掖-民乐绿洲的相接处和肃南县明花乡等处；另一种是与原绿洲主体有一定距离的区域形成飞地绿洲并逐渐向四周扩散，如金塔绿洲与鼎新绿洲之间的酒航公路沿线、嘉峪关市和高台县骆驼城镇的绿洲。

明花乡、骆驼城镇、羊井子湾乡绿洲发生显著扩张的原因与移民安置有关。明花乡是肃南县主要生态移民安置区，20世纪90年代初陆续有游牧民搬至明花乡且生活方式转变为以农耕为主[34]；羊井子湾乡、骆驼城镇是1983年开始的“两西移民”计划的重要移民安置基地[5]。酒航公路沿线绿洲从2006—2009 年开始发展，并在2009 年后有较大的扩张。该公路于 2005年全线通车，为绿洲在远离乡镇的区域发展提供了条件。张掖一民乐绿洲相接处的绿洲扩张主要发生在2006年后，多采用滴灌、喷灌等节水技术的高科技农业示范园等民营企业建设的农牧场，如民乐县的华瑞农业股份有限公司和金丰农业科技示范园区等，采用滴灌和指针式喷灌等节水灌溉技术[36]；张掖市甘州区前进村在国家强农惠农富农政策支持下，建立了村办股份制企业前进牧业的石岗墩牧场。与上述以农牧业发展为主的绿洲扩张不同，嘉峪关市的绿洲扩张主要是城镇化建设引起的。总体而言，黑河绿洲扩张的主体是耕地与农牧场，城镇化占比较小。耕地与农牧场的扩张，主要是由政策引导的移民和拓荒、交通设施建设和集体农场建设等原因引起的。

# 4.2典型波动模式绿洲稳定性及影响因素

近55a间，黑河绿洲波动明显，波动面积占绿洲总面积的 $5 4 . 4 7 \%$ 。灌溉保障程度低和土壤盐渍化是绿洲波动的最重要的原因。例如，金塔绿洲和额济纳绿洲分别位于北大河和黑河干流的尾闾部位，易受水资源短缺影响，且来水含盐量高[26]；临泽绿洲中部的新华镇、暖鸭乡等处于洪积扇扇缘地带，地势低洼、地下水埋深较浅[27]。上述3个区域是土壤盐渍化的高发区。盐渍化导致土壤生产能力下降，粮食产量低下，促使原有耕地的弃耕和新耕地的开垦，进而导致绿洲的频繁波动[37]。

河道变迁和水位变化是绿洲波动的另一个重要原因。例如，民乐绿洲位于祁连山北麓洪积扇地带，南北向纵贯其中的支流、汊道众多，耕地破碎，并缺乏大型的蓄水、引水和灌溉系统[38]，不同年份间耕作绿洲波动较大；鼎新绿洲和额济纳境内的沿河绿洲波动则更多与水位涨落有关，在水量较少的年份，沿河地带水位较低，裸露河滩被识别为“荒漠”，也会导致绿洲识别结果的差异。

随着时间的推移，绿洲波动存在减弱趋势。中游绿洲及下游金塔、鼎新绿洲波动的主导时段是早期。这与早期农业生产比较粗放、水利灌溉体系不完善有关。到中后期，随着水利灌溉条件的改善和生产方式的集约化，原有绿洲趋于稳定，绿洲变化以扩张为主。额济纳旗沿河绿洲及尾闾绿洲部分区域波动主导时段为中期，这与黑河干流水利建设有关。20 世纪90 年代，草滩庄分水枢纽工程、大墩门引水枢纽工程等先后建成拦水，导致额济纳旗境内黑河水量锐减，尾闾湖干涸，植被严重退化[39-41]，尾闾农业绿洲灌溉无法有效保障，波动频繁。2000 年开始实施黑河干流水量统一调度，有效保障了下游来水量[42]，植被退化趋势得到遏制，农业绿洲的灌溉保障度提高，绿洲波动趋势减弱、稳定性提高，这与王耀斌等[17,41]的研究结果一致。

应当特别说明的是，1973年和1977年的影像为LandsatMSS数据，分辨率较低且时相不佳。所以，这两个样本年提取绿洲数据精度较低，使绿洲早期的稳定性分析中增加了误差。

# 5结论

本文在相对较高的时间频率上，提取了1963—2017年黑河流域绿洲各时期的边界信息。在此基础上，通过叠加分析划分了绿洲空间动态的4种基本变化模式，即稳定不变、扩张变化、退缩变化和波动变化。并对提取结果进行格网化，采用累积动态度指标进一步分析了绿洲变化的稳定性和主导时段。本文的主要结论如下：

（1）研究时段内，黑河流域绿洲的变化模式以波动变化为主。波动变化的面积约占绿洲总面积的 $50 \%$ ，稳定不变和扩张变化的面积次之，退缩变化的面积较小。

（2）就绿洲动态的稳定性和主导时段特征而言，下游的稳定性较弱，绿洲的稳定性从早期向中后期逐渐增强。具体而言，下游绿洲的稳定性弱于中游；中游绿洲及下游的金塔和鼎新绿洲的波动主要发生在早期，而下游额济纳沿河绿洲和尾闾绿洲则主要发生在中期。

（3）绿洲动态的成因各异。从变化原因看，移民安置、农业生产技术革新等是绿洲扩张的主要原因；而土地盐碱化、河流变迁和水位变化等是绿洲波动变化的重要原因；水利相关科学技术的发展、政策实施与节水灌溉技术的进步，对绿洲稳定性提升和有序扩张具有重要意义。

与前人的研究相比，本文同时探测了绿洲变化的时间特征和空间特征，并将分析单元缩小到格网尺度，能更加有效地对变化进行定位和原因分析。但本文仅对绿洲稳定性的影响因素进行了定性分析，后续研究中应该从社会经济技术角度出发开展定量分析。

# 参考文献(References):

[1] 贾宝全，慈龙骏，韩德林，等．干旱区绿洲研究回顾与问题分析[J].地球科学进展,2000,15(4):381- 388.[Jia Baoquan,CiLongjun,Han Delin,et al.Review and problem analysis of oasis research inarid region[J]. Advance in Earth Sciences,2000,15(4): 381-388.]   
[2] 赵文智，庄艳丽．中国干旱区绿洲稳定性研究[J].干旱区研究,2008,25(2):155-162.[Zhao Wenzhi,Zhuang Yanli.Studyon the stability of oases in the arid areas in China[J].Arid Zone Research,2008,25(2):155-162.] [3] 汪久文．论绿洲、绿洲化过程与绿洲建设[J].干旱区资源与环境,1995,9(3):1-12.[Wang Jiuwen.Oasis, oasis making and oasis construction[J]. Journal of Arid Land Resources and Environment,1995,9(3): 1-12.] [4]崔卫国，穆桂金．绿洲演变动态监测的遥感分析[J]．地球信息科学,2004,6(3):105-107,125-127.[Cui Weiguo,Mu Guijin. Application of RS technology in the research of oasis dynamic change[J]. Geo-information Science,2004, 6(3): 105-107,125-127.]   
[5]樊自立．塔里木盆地绿洲形成与演变[J]．地理学报,1993,48(5): 421-427.[Fan Zili.A study on the formation and evolution of oases in Tarim Basin[J].Acta Geographica Sinica,1993,48(5): 421-427.]   
[6]申元村．绿洲发展面临的挑战、目标及 21 世纪发展研究展望[J].干旱区资源与环境,2000,14(1):1- 11.[Shen Yuancun. Development of oases in the 21st century challenge,direction and prospect[J]. Journal of Arid Land Resources and Environment, 20oo,14(1):1-11.]   
[7] 刘亚文，阿不都沙拉木·加拉力丁，阿拉努尔·艾尼娃尔，等.1989—2016 年吐鲁番高昌区绿洲时空格局 变化及其驱动因素[J]．干旱区研究，2018,35(4):945-953.[Liu Yawen,Abdushalam Jalaliding,Alanuer Aniwaer,et al. Spatiotemporal change of the oasis in Gaochang,Turpan and its driving factors duringthe period of 1989-2016[J].Arid Zone Research,2018,35(4): 945-953.]   
[8]罗格平，周成虎，陈曦，等．区域尺度绿洲稳定性评价[J]．自然资源学报,2004,19(4):519-524.[Luo Geping,Zhou Chenghu, Chen Xi,etal.Evaluation of the stabilityofthe oasis attheregional scale[J].Journal of Natural Res0urces,2004,19(4): 519-524.]   
[9]王涛．干旱区绿洲化、荒漠化研究的进展与趋势[J]．中国沙漠,2009,29(1):1-9.[Wang Tao.Review and prospect ofresearchonoasificationand desertification inarid region[J]. Journal ofDesert Research,2O09,29(1):1- 9.]   
[10]廖杰，王涛，薛娴．近 55a 来黑河流域绿洲演变特征的初步研究[J]．中国沙漠,2012,32(5):1426- 1441.[Liao Jie,Wang Tao,Xue xian. Oasis evolution in the Heihe River Basin during 1956-2010[J].Journal of Desert Research,2012,32(5): 1426-1441.]   
[11] 周跃志，潘晓玲，何伦志．绿洲稳定性研究的几个基本理论问题[J].西北大学学报(自然科学版),2004, 34(3):359-363.[Zhou Yuezhi,Pan Xiaoling,He Lunzhi. Several basic academic problems of oasis stability[J]. Journal of Nnorthwest University(Natural Science Edition)],2004,34(3): 359-363.   
[12]舒俭民，王家骥，郑丙辉，等．黑河流域生态环境恶化状况与治理建议[J].环境科学研究,1998,11(4): 57-59,63.[Shu Jianmin,Wang Jiaji, Zheng Binghui,et al.Eco-environmental degenerationand improving proposal in the Heihe River Basin[J].Research of Environmental Sciences,1998,11(4): 57-59,63.]   
[13]蒋兴国，郑洁．黑河流域跨省生态环境治理与可持续发展研究——以张掖为例[J].边疆经济与文化, 2017,(9): 11-15.[Jiang Xingguo,Zheng Jie.Study on trans-provincial eco-environment management and sustainable developmentin Heihe River Basin:Acase study of Zhangye[J].The Border Economy and Culture,2017,(9): 11-15.] [14]王雅，蒙吉军．黑河中游土地利用变化对生态系统服务的影响[J].干旱区研究,2017,34(1):200- 207.[Wang Ya, Meng Jijun.Effects of land use change on ecosystem services in the middle reaches of the Heihe River Basin[J]. Arid Zone Research,2017,34(1): 200-207.]   
[15]XiaoFY,GaoG Yao,Shen Q,etal.Spatio-temporalcharacteristics and driving forcesoflandscape structure changes in the middle reach of the Heihe River Basin from 1990 to 2015[J]. Landscape Ecology,2019,34(4): 755- 770.   
[16] 钱大文，巩杰，贾珍珍．绿洲化-荒漠化土地时空格局变化对比研究——以黑河中游临泽县为例[J].干 旱区研究,2016,33(1): 80-88.[Qian Dawen, Gong jie,Jia Zhenzhen. Analysis on the spatio-temporal evolution of oasis formation and desertification: A case study ofLinze County in the middle reaches of Heihe River, Gansu[J]. Arid Zone Research, 2016,33(1): 80-88.]   
[17] 王耀斌，冯起，刘光绣，等．极端干旱区额济纳绿洲稳定性评价研究[J].生态经济,2015,31(9):162- 165,190.[ Wang Yaobin,Feng Qi,Liu Guangxiu,etal.Studyon the oasis stability evaluation of extremearid region of Ejina[J]. Ecological Economy,2015,31(9): 162-165,190.]   
[18] 胡汝骥,姜逢清，王亚俊．正确认识中国干旱区绿洲的稳定性[J].干旱区研究,2010,27(3):319-323.[Hu Ruji,JiangFengqig, Wang Yajun.To haveacorrct understanding ofthe stabilityofoasis inarid lands ofChina[J]. Arid Zone Research,2010,27(3): 319-323.]   
[19]段汉明，苏敏，周晓辉．银川平原绿洲的稳定性与可持续发展[J].干旱区资源与环境,2006,20(1):1- 6.[Duan Hanming,Su Min, Zhou Xiaohui.The stability and sustainable development measures of Yinchuan Plain' S oasis[J]. Journal of Arid Land Resources and Environment, 20o6, 20(1): 1-6.]   
[20] 韩德麟．绿洲稳定性初探[J]．宁夏大学学报(自然科学版),1999,20(2):43-46.[ Han Delin.Elementary study of oasis constancy[J]. Journal of Ningxia University(Natural Science Edition),1999,20(2): 43-46.] [21]王忠静，王海峰，雷志栋．干旱内陆河区绿洲稳定性分析[J]．水利学报,2002,(5):26-30.[ Wang Zhongjing，Wang Hai-feng,Lei Zhidong. Stability analysis of oasis in arid region[J]. Journal of Hydraulic Engineering,2002,(5): 26-30.]   
[22]Luo GP,LuL,Yin CY,etal.Ananalysis ofoasis stability inarid areas: acase study inthe northern slope areas of the Tianshan Mountains[J]. Journal of Arid Land,20o9,1(1): 49-56.   
[23]ChaoL,Chen YN,LiXG,etal.Evaluationofoasis stabilityinthelowerreachesofthe TarimRiver[J].Jounal of Arid Land,2011, 3(2): 123-131.   
[24] 韩洪凌，李志忠．新疆玛纳斯河流域生态系统稳定性研究[J].干旱区资源与环境,2009,23(10):95- 99.[Han Hongling,Li Zhizhong. Research on ecosystem stability in Manas River Vally[J]. Journal of Arid Land Resources and Environment, 2009,23(10): 95-99.]   
[25] 张平，刘普幸．河西走廊瓜州绿洲生态系统稳定性评价与生态风险防御对策[J]．农业现代化研究,2009, 30(6): 731-734.[Zhang Ping,Liu Puxing.Ecosystem stability assessment and defensecountermeasures of ecological risk for Guazhou Oasis in Hexi Aisle[J]. Research of Agricultural Modernization,2009,30(6): 731-734.] [26] Xie YW,Zhao H, Wang G S.Spatio-temporal changes in oases in the Heihe River BasinofChina: 1963-2013[J]. Ecoscience,2015,22(1): 33-46.   
[27]杜巧玲，许学工，刘文政．黑河中下游绿洲生态安全评价[J]．生态学报,2004,24(9):1916-1923.[ Du Qiaoling, Xu Xuegong,Liu Wenzheng.Ecologicalsecurity assssment forthe oases in the middleand lower Heiher River[J]. Acta Ecologica Sinica, 2004,24(9): 1916-1923.]   
[28]韩德麟．关于绿洲若干问题的认识[J].干旱区资源与环境,1995,9(3):13-31[ Han Delin.Knowledge of a few issues on oasis[J]. Journal ofArid Land Resources and Environment,1995,9(3): 13-31.]   
[29]王秀兰，包玉海．土地利用动态变化研究方法探讨[J].地理科学进展,1999,18(1):83-89.[Wang Xiulan Bao Yuhai. Study on the methods of land use dynamic change research[J]. Progress in Geography,1999,18(1): 83- 89.] [30] 马宗义，颉耀文，余林，等．单一景观类型时空变化分析方法——以酒泉盆地绿洲化为例[J].地理科学 进展,2012,31(12): 1732-1738.[Ma Zongyi,Xie Yaowen,YuLin,etal. Models for analysis ofthe spatial-temporal changes ofasingle-type landscape: Acase study ofoasis-making process in Jiuquan Basin[J].Progressin Geography, 2012,31(12): 1732-1738.]   
[31] 鲁晖，颌耀文，张文培，等.1986—2015 年民勤县绿洲时空变化分析[J].干旱区研究,2017,34(6):1410- 1417.[Lu Hui, Xie Yaowen, Zhang Wenpei, et al. Spatiotemporal change of the oasis in Minqin County during the period from 1986 to 2015[J].Arid Zone Research,2017,34(6): 1410-1417.]   
[32] Pontius JRR G, Shusas E,Mceacherm M. Detecting important categorical land changes while accounting for persistence[J]. Agriculture, Ecosystems & Environment, 2004,101(2-3): 251-268.   
[33]Luo GP, Zhou C H,Chen X,et al. Amethodologyof characterizing status and trend of land changes in oases: A case study of Sangong River watershed, Xinjiang, China[J]. Journal of Environmental Management, 20o8,88(4): 775-783.   
[34] 李静，杨哲，刘继杰．生态移民之后的移民生计方式变迁与文化变迁——以甘肃省肃南县明花乡双海 子村为例[J].天水师范学院学报,2012,32(4):78-82.[Li Jing,Yang Zhe,Liu Jijie.The change oflivelihood mode and culture after ecological migration: A case study of Shuanhaizi Village, Minghua Township,Sunan County, Gansu[J]. Journal of Tianshui Normal University,2012,32(4): 78-82.]   
[35] 李骏．从两西移民看西部贫困地区人口迁移[J]．甘肃社会科学,2001,(5):54-57.[LiJun.Exploring the migration model of the poor areas in the western China from two western immigrants[J]. Gansu Social Sciences, 2001, (5): 54-57.]   
[36] 杨鹏举，张恒嘉．张掖市高效节水灌溉工程建设及运行管理[J]．农业科技与信息,2016,(34):117, 119.[Yang Pengju, Zhang Hengjia. Construction and operation management of eficient water-saving irigaton project in Zhangye[J]. Agricultural Science-Technology and Information, 2016,(34): 117,119.]   
[37] 王小军，陈翔舜，刘晓荣，等．河西走廊区沙漠化年度趋势变化分析研究[J]．甘肃科技,2014,30(9):1-4, 23.[Wang Xiaojun,Chen Xiangshun,Liu Xiaorong,etal. Research on trend of desertification in Hexi Corridor[J]. Gansu Science and Technology, 2014,30(9): 1-4,23.]   
[38]陈俊．民乐县节水型农业的现状与发展趋势[J]．农业科技与信息,2015,(13):76-78.[Chen Jun.Status quo and development trend of water-saving agriculture in Minle County[J]. Agricultural Science-Technology and Information,2015,(13): 76-78.]   
[39]甘肃省张掖市志编修委员会．张掖市志[M].兰州：甘肃人民出版社，1993:224-225.[Codification Committe of Chorography of Zhangye [M]. Gansu. Chorography of Zhangye[M]. Lanzhou: Gansu people's Publishing House,1993: 224-225.]   
[40]金塔县地方志编纂委员会．金塔县志[M].兰州：甘肃人民出版社，1992:220-222.[Codification Commitee of Chorography of Jinta. Chorography of Jinta[M].Lanzhou: Gansu People's Publishing House,1992: 220-222.]   
[41] 王耀斌．基于可持续发展的额济纳绿洲生态环境变化研究[J].甘肃联合大学学报(自然科学版),2010, 24(1): 58-63,66.[Wang Yaobin.A Study of eco-environmental changes based on sustaining development for Ejina Oasis[J]. Journal of Gansu Lianhe University(Natural Science Edition),2010,24(1): 58-63,66.]   
[42]赵清，黄维东．黑河水量统一调度及流域治理成效分析评价[J]．人民黄河,2015,37(8):60-63,97.[Zhao Qing,Huang Weidong. Analysis and evaluation on efect of water integrated regulation and comprehensive river basin management of Heihe River[J]. Yellow River,2015,37(8): 60-63, 97.]

# Pattern and stability analysis of oasis change in Heihe River Basin

DONG Jing-ru1, XIE Yao-wen1,2, DUAN Han-ming1, WANG Xiao-yun], LI Ru-yan1 (1. College of Earth and Environmental Sciences,Lanzhou University,Lanzhou 73ooo0,Gansu, China;   
2.KeyLaboratoryof Western China's Environmentalsystem (MinistryofEducation),LanzhouUniversityLanzhou 730000, Gansu, China; 3.College ofLand and Resources, China West Normal University, Nanchong 637o02,Sichuan,China)

Abstract:This article aims toexplore the spatiotemporal change pattern and stabilityofthe oasis in the Heihe River Basin inrecent 55 years.16 phases multi-source remote sensing images from 1963 to 2017 was adopted in this study. Based onthese data,the distribution information ofthe oases in Heihe River Basin was extracted.Then,the temporal and spatial characteristics of the change paterns and stability of oases in Heihe River Basin were analyzed using overlay analysis and grid transformed model. According to the conversion between oasis and desert and the change of oasis boundary,the change patern of oasis is divided into four categories: stable,expanding,shrinking and fluctuating.Meanwhile,the expansion year of expanding oasis was extracted, inorder to further correspond and explain with thereal land use situation.In this paper,the stabilityofoasis is measured by grid transformed models of spatial dynamic degree and cumulative dynamic degre.The single dynamic degree of land use can effectively represent the change ofland type and quantity characteristics.Ma Z proposed amethod to narow the single dynamic degree operation to the grid unit to reflect the spatial changes of the oasis.But Previous studies pointed out that single dynamic degree only reflects the net change ofland use,but ignores the change of spatialdistribution of land use.Therefore, we establish a grid transformed models of spatial dynamic degree and cumulative dynamic degree consideringthe total change toanalyzedthe spatial distribution of the stability ofoasis.Theresults show: Inthe past 55 years,the oasis in the Heihe River Basin is dominated by fluctuating patern.The fluctuating oasis is mainly distributed in areas with poor water source guarantee and saline-alkali land development.The expanding oasis appeared in the internal patches of the oasis in the early stage and expanded to the periphery of the oasis in the middle and late stage.The shrinking oasis is mainly distributed on theedgeof ecologically fragile oasis.The expansion of oasis in the early stage was mainly led by population growth and immigration policies, while the expansion of oasis after 20oo was mainly caused by the innovation of agricultural production technologies such as drip irrigation and sprinkling irigation. Oasis in Heihe River Basin gradually became stable.The stability of oasis in the lower reaches is lower thanthat in the middle reaches.The fluctuations of the oasis in the middle and lower reaches of (Jinta County and Dingxin County)mainly occurred in the early stage.While oasis in Ejina County fluctuated in the middle stage.The land salinization,broad-shallow and shifting channels of Heihe River are the important factors influencing oasis stability.Compared with previous studies,this paper constructed a time series of oasis dynamic degree on the basis of grid transformed method.It simultaneously detects the temporal and spatial characteristicsof oasis changes,and reduces the analysis unit to the grid scale,so that the changes of oasis can be located and analyzed more effectively.

Key words: oasis; change pattern; stability; remote sensing; GIS; Heihe River Basin

收稿日期：2019-10-16；修订日期：2020-03-17  
基金项目：国家自然科学基金项目(41471163,41530752)；兰州大学祁连山研究院开放课题[504000-(87080306)]资助。  
作者简介：董敬儒(1994-)，女，硕士研究生，研究方向为干旱区遥感应用研究.E-mail:dongjr17@lzu.edu.cn。  
通讯作者：頡耀文.E-mail: xieyw@lzu.edu.cn。