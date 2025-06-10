# 基于景观生态安全的神木市生态廊道识别与优化

吴金华，刘思雨，白帅(长安大学土地工程学院，陕西 西安710054)

摘要：以优化生态格局为出发点,对神木市景观生态安全进行评价。综合运用主成分分析法、自然断点法、MCR（Minimum Cumulative Resistance,MCR)模型,获取神木市生态安全格局的分布状况,并在此基础上提取生态源地，采用最小累积阻力模型构建生态廊道以优化生态景观格局。结果表明：神木市景观生态安全状况分为5级，1级区域多位于西北部,少部分分布在东南部及北部边缘地区,2级、3级区域在全域呈碎片化相间分布，4级、5级区域分别受人类活动和自然条件影响，在中部建设用地区成集中连片分布,东南部沟壑纵横区成碎片化分布;神木市生态廊道共121条，其中有 $1 9 . 0 8 \%$ 的生态廊道独立存在， $4 3 . 5 1 \%$ 的生态廊道未与主要生态廊道群相连；设计新增生态廊道10条，总长 $7 6 . 6 9 \mathrm { k m }$ 。通过新增生态廊道,完善生态廊道网络,加强独立生态廊道与生态源地的联系,对优化神木市景观生态环境，构建生态安全格局具有重要的参考意义。

关键词：生态廊道；景观生态安全评价；MCR模型；神木市

随着城市化进程的加快，大量的生态用地、农用地被城市建设不断“侵蚀”，景观格局碎片化现象严重，城市生态安全受到了巨大的威胁。因此，在生态保护与经济社会发展相矛盾的背景下，了解现有景观生态安全状况，分析景观生态安全，优化景观环境显得尤为重要[1-2]。景观生态安全评价作为生态安全评价的一个重要方面，从景观生态学的角度对区域生态安全状况进行评价，理清生态系统功能与过程的相互关系，对景观组分进行数量结构和空间结构上的调节，合理配置土地资源，实现土地利用生态、经济、社会三大效益的最优化

早期的国外学者更多关注自然生态系统，通过构建一系列保护制度，划分不同保护等级的土地类型，从而实现保护生物多样性的目标。近年来，随着生态系统服务评估的发展，生态安全格局的研究逐渐过渡到以自然生态系统为主，与经济社会系统耦合的阶段。从土地利用优化配置和景观生态规划两个方面进行研究,Shaygan等[3]通过对Taleghan河流域的土地利用配置进行优化来达到构建生态安全格局的目的。我国对于生态安全格局的研究始于20世纪90年代，许多学者以景观格局优化、土地利用结构优化、生态系统敏感性等为切入点进行了大量研究[4]。俞孔坚[5]首次提出了"生态源地-阻力面-格局”三步构建生态安全格局的方法，并在很多研究中得以应用[6]。但随着研究的深入，越来越多的研究发现生态安全格局构建仍然存在着一些问题[7-10],如对生态功能和过程影响的研究还不够深入，不能满足景观格局优化的理论指导要求、反映生态安全格局的动态变化等。

已有研究以生态廊道适宜性分析、廊道网格构建为主[1],少有基于景观生态安全评价结果考虑廊道构建。基于此，本研究在景观生态安全评价的基础上，提取生态源地，构建最小累积阻力面，运用最小累积阻力模型识别现有生态廊道，通过新增生态廊道，优化神木市生态网络，对构建神木市高等级景观生态格局及提高生态安全具有重要意义。

# 1研究区概况与方法

# 1.1 研究区概况

神木市位于陕西省北端，是晋陕蒙三省交界地带，东北部与和府谷县相接，西北部与内蒙古伊金霍洛旗相连，东南部和山西省兴县隔黄河相望，具体位置如图1所示。神木市土地生态环境脆弱，西北部为风沙草滩区，地势较平坦；东南部为黄土丘陵沟壑区，地形破碎，沟壑纵横，水土流失严重;境内水资源充沛，黄河、窟野河、秃尾河等河流在境内穿过；土壤类型多样,矿产资源丰富，尤其煤炭储量丰盈且分布广泛。

![](images/efb5c6d4cbc2f7d89452e0a198a994450ea699d0acf454557bda86d3e256c12e.jpg)  
图1研究区示意图  
Fig.1 Sketch map of the study area

# 1.2数据来源

采用的数据包括土地利用现状数据、自然资源和社会经济数据、DEM数据。土地利用现状数据为神木市自然资源和规划局提供的2017年土地利用现状数据；自然资源和社会经济数据来源于神木市2017年《统计年鉴》、《国民经济和社会发展统计公报》；DEM数据来源于 BIGEMAP（www.bigemapcom），通过Globalmapper转化数据格式，利用Arc-GIS提取DEM坡度值后生成。

# 1.3 研究方法

最小累积阻力模型(MinimumCumulativeResis-tance,MCR)最早被Knaapen等[12]学者用于景观规划、物种扩散、保护生物学等领域，后来俞孔坚[5将其进行修改并用于生态廊道识别和生态安全格局构建。MCR模型通过计算生态流经过基面累积耗费的代价，寻找最小耗费距离，即最小累积阻力路径。最小累积阻力模型公式如下：

$$
\mathrm { M C R } = f \operatorname* { m i n } \sum _ { j = n } ^ { i = m } ( D _ { i j } R _ { i } )
$$

式中：MCR表示最小累积阻力值： $f$ 表示最小累积阻力与生态过程的正相关函数; $D _ { i j }$ 表示从生态源地 $j$ 到目的地单元i的空间距离； $R _ { i }$ 表示单元 $i$ 对某物种运动的阻力系数； $\operatorname* { m i n }$ 表示单元 $i$ 对于不同的源取累积阻力最小值。

# 2结果与分析

# 2.1景观生态安全评价

2.1.1指标选取综合考虑研究区实际情况和数据资料的全面性、可获取性，本研究将景观生态安全评价的影响因素分为外部及内部。外部影响因素主要考虑自然条件、人类活动、水源位置、土地利用景观类型等外界因素对景观生态安全的影响，选取坡度、距水体的距离、距道路的距离、距居民点的距离和土地利用类型5个评价因子；内部影响因素是从景观角度出发,选取斑块密度[13]、景观蔓延度[14-15]、景观散布与并列指数[16] 景观丰度[17]和景观均匀度指数[14]5个景观指数作为评价因子，描述区域景观特征。在Fragstats4.2软件中以村为单位计算分值，并运用自然断点法科学客观的进行因子分级，构建景观生态安全评价指标体系(表1)。

2.1.2权重确定运用主成分分析法计算权重可以客观地确定权重大小，避免人为因素对权重结果的影响，也可以将多指标问题转化为少量指标的问题，把问题变得简单直接，使研究结果更加客观科学。

经过KMO检验与巴特利特球形度检验后，数据的KMO值大于0.7，这表明该研究适用于主成分分析法，巴特利特球形度检验的显著性为0,说明非常显著，可以进行主成分分析。经主成分变换后，每一个主成分都包含原始变量的信息载荷，取前6个累计贡献率达到 $8 3 \%$ 的主成分，可充分反映神木市生态安全信息，所得方差贡献率作为主成分权重，各指标权重确定结果见表1。

2.1.3景观生态安全等级利用多因素综合评价法计算神木市景观生态安全指数，根据自然断点法，

# 表1景观生态安全评价体系

Tab.1 Landscape ecological security evaluation system   

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">评价因子</td><td colspan="5">因子分级</td><td rowspan="2">权重</td><td rowspan="2">权重和</td></tr><tr><td>1级</td><td>2级</td><td>3级</td><td>4级</td><td>5级</td></tr><tr><td rowspan="6">外 部 条 件</td><td>坡度/()</td><td>≤2</td><td>2~6</td><td>6~15</td><td>15~25</td><td>>25</td><td>0.13</td><td>0.53</td></tr><tr><td>距离水体的距离/m</td><td>≤500</td><td>500~1000</td><td>1000~1500</td><td>1500~2000</td><td>>2000</td><td>0.06</td><td></td></tr><tr><td>距离道路的距离/m</td><td>>5000</td><td>3000~5000</td><td>2000~3000</td><td>1000~2000</td><td>≤1000</td><td>0.09</td><td></td></tr><tr><td>距离居民点的 距离/m</td><td>>2000</td><td>1500~2000</td><td>1000~1500</td><td>500~1000</td><td>≤500</td><td>0.13</td><td></td></tr><tr><td>土地利用类型</td><td>面、水库水面草地</td><td></td><td>林地、河流水园地、天然 耕地、设施农用地、农 面、湖泊水 草地、人工村道路、坑塘水面、沟 渠、田坎、沿海滩涂、 内部滩涂、沼泽地</td><td></td><td>城市、建制镇、村庄、街巷 0.12 用地、风景名胜及特殊用 地、采矿用地、铁路用地、 公路用地、机场用地、港口 码头用地、管道运输用地、 水工建筑用地、其他草地、</td><td></td><td></td></tr><tr><td>斑块密度</td><td><10.98</td><td>10.98~17.50</td><td>17.50~23.29</td><td>23.29~31.30</td><td>沙地、裸地、盐碱地、冰川 及永久积雪 ≥ 31.30</td><td>0.07</td><td>0.47</td></tr><tr><td>部 条 指数 件</td><td>景观散布与并列</td><td><38.62</td><td>38.62~45.73</td><td>45.73~52.57</td><td>52.57~61.38</td><td>≥ 61.38</td><td>0.06</td><td></td></tr><tr><td rowspan="4">景观丰度</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>景观蔓延度指数</td><td>≥74.25</td><td>65.56~74.25</td><td>60.94~65.56</td><td>54.84~60.94</td><td><54.84</td><td>0.13</td><td></td></tr><tr><td></td><td>≥10</td><td>8.00~10.00</td><td>7.00~8.00</td><td>6.00~7.00</td><td><6.00</td><td>0.09</td><td></td></tr><tr><td>景观均匀度指数</td><td>≥0.69</td><td>0.60~0.69</td><td>0.53~0.60</td><td>0.41~0.53</td><td><0.41</td><td>0.12</td><td></td></tr></table></body></html>

将全市景观生态安全区分为5个等级，分值在1.67\~2.54为1级， $2 . 5 5 { \sim } 2 . 8 0$ 为2级，2.81\~3.04为3级，3.05\~3.32为4级，3.33\~4.26为5级，从1级景观生态安全区到5级景观生态安全区安全程度逐渐降低，如图2所示。

1级景观生态安全区多位于神木市西北部，呈现集中连片的特点，少部分分布在东南部及北部边缘地区，呈现碎片化分布的特点，原因在于西北地区地势平坦，多为林地与草地，居住密度较低，人类活动不频繁，有利于景观环境保护以及景观生态安全。2级、3级景观生态安全区在全域多呈现碎片化相间分布，这两级安全区主要位于坡度较小、距离水体较近、距离中心居民区较近的地区，土地利用多以分布于山腰与山底的耕地为主。4级、5级景观生态安全区连片化与碎片化特征共同出现，主要分布在中部和东南部，中部地区建设用地多且连片，受到人类活动的影响较大，东南部区域沟壑纵横、景观破碎化程度较高，景观生态安全易受影响，

# 2.2生态廊道优化

2.2.1生态源地提取生态源地的提取是构建生态廊道识别模型的基础。生态源地对于维护区域景观生态安全，保证人类生存安全，促进生态环境可持续发展具有重要的生态意义，是生态保护的原则与底线[18-19]。生态源地与生态安全具有很强的相关性，一般来说生态源地是生态功能较强、生物多样性较好、物质、能量流动较为顺畅的区域，其识别方法多样，林地、草地、水域等土地利用类型都可作为生态源地进行识别定义。本研究将景观生态安全评价与生态源地选择结合，除选取常规意义上的生态源地外，还参考景观生态安全评价结果。考虑土地分布、结构、数量以及其他影响因素，选取满足以下条件的土地为神木市生态源地：（1）选取面积大于 $1 5 0 \mathrm { h m } ^ { 2 }$ 的林地、河流、湖泊以及面积大于 $0 . 5 \mathrm { h m } ^ { 2 }$ 的水库水面以及生态安全控制区内的全部土地作为生态源地。（2）选取评价结果中的1级景观生态安全区的土地作为景观生态源地。

![](images/0dc772ec50660ba5d18231a3a5d383b99ef57d3f405d6305595b695ccc22bc1e.jpg)  
图2神木市景观生态安全评价结果  
Fig.2Evaluation results oflandscape ecological security in Shenmu City

由生态源地提取结果图可知(图3)，生态源地在神木市西北部多集中连片分布，以西部的尔林兔镇、锦界镇、麻家塔办事处、大保当镇及高家堡镇为主要区域，其余地区生态源地呈零散点状分布，密度不大。总体来看，神木市区域内点状分布的生态源地有连片趋势，但未能集中分布，分散状态明显，景观生态环境安全状况空间分布差异较大。

2.2.2最小累积阻力面确定物种对于景观的利用，物质在生态环境中的流动、运行都需要克服不同的阻力[20]。以表1中选取的景观生态安全评价因子作为阻力因子，评价等级划分标准作为阻力等级划分标准，评价级别作为阻力分值，分值越大，说明阻力越大，分值越小，说明阻力越小。以最小累积阻力模型(MCR)为基础，计算神木市最小累积阻力面。

受到距离、位置、坡度、地形、地貌等因素的制约，所得到的阻力值数量庞大且不尽相同。利用自然断点法按照阻力值大小进行分区：0\~1079.13为1级累积阻力区，1079.14\~3083.22为2级累积阻力区，3083.23\~5626.88为3级累积阻力区， $5 6 2 6 . 8 9 \sim$ 9403.83为4级累积阻力区，9403.84\~19655.55为5级累积阻力区。由图4可知，阻力值越大，越不利于景观生态环境的优化，阻力值越小，说明区域内进行景观的物质交流与维持所受到的阻力越小，越有利于景观生态环境的优化和生态安全的发展。对比图3和图4,生态源地及其附近区域，阻力值小，远离生态源地的区域，则阻力值较大。

2.2.3生态廊道识别与优化以MCR模型形成的最小累积阻力图为基础，确定生态廊道位置。目前神木市生态廊道共有121条，总长度为 $7 9 7 . 2 0 ~ \mathrm { k m }$ 其中有 $1 9 . 0 8 \%$ 的生态廊道独立存在，有 $4 3 . 5 1 \%$ 的生态廊道未与南北主要生态廊道群连通。按照其长度，利用自然断点法进行分级(图5)，将其分为三级生态廊道： ${ \geqslant } 1 2 . 9 5 \ \mathrm { k m }$ 为1级，共9条，总长度为$1 6 4 . 9 2 \mathrm { k m } ; 6 . 0 0 { \sim } 1 2 . 9 5 \mathrm { k m }$ 为2级，共49条，总长度为$4 4 1 . 0 3 ~ \mathrm { k m }$ ： $< 6 . 0 0 \ \mathrm { k m }$ 为3级，共63条，总长度为

![](images/0a4d5a537041f46eea77903940b1f57932c6ed9fb9781a182d1140bf46146c85.jpg)  
图3生态源地提取结果   
Fig.3Ecological source extraction results

![](images/3ac73a7a98191c28b4e78dc8f30aafb3a92acbddf1d3da1145e111e99ae0437f.jpg)  
图4最小累积阻力图  
Fig.4 Minimum cumulative resistance map

![](images/9fc2effdf90e462d0ad62443325a47642cb0458d1892e874c52e152a6b053598.jpg)  
图5生态廊道识别及优化图  
Fig.5 Ecological corridor identification and optimization map

$1 9 1 . 2 5 \mathrm { k m }$ 。神木市整体来看，相邻镇域大多数生态廊道独立存在，北部与南部的生态廊道亦呈现断开态势，生态廊道整体未实现连通。

针对神木市现有生态廊道中存在的南北部不连通问题，充分考虑生态源地、累积阻力、原生态廊道、交通条件、水系等本底条件，设计增加10条生态廊道，总长度为 $7 6 . 6 9 \ \mathrm { k m }$ ,长度增加约 $9 . 6 2 \%$ ,新增生态廊道分布情况见表2。临近河流的生态廊道，可扩展河岸两旁的防护林、绿地面积，打造滨河绿带；与交通网络重叠的生态廊道，应依托原有交通干线，拓宽道路两侧绿化带，建设绿色道路廊道;位于人类活动频繁而导致景观破碎，生态安全等级较低区域的生态廊道，应同时赋予生态廊道提高生态安全等级、美化生活环境等功能，大力建设公园廊道;林草茂盛区域、沟壑纵横区域的生态廊道，要依托区域的本底条件，采取生态系统自主恢复与人工恢复相结合的方法，实施水土保持、植树造林等工程，构建森林生态廊道。

表2新增生态廊道  
Tab.2 New ecological corridor   

<html><body><table><tr><td>生态廊道级别</td><td>编号</td><td>廊道长度/km</td><td>位置</td></tr><tr><td>二级廊道</td><td>1</td><td>6.74</td><td>尔林兔镇</td></tr><tr><td></td><td>2</td><td>11.16</td><td>锦界镇、麻家塔办事处交界</td></tr><tr><td></td><td>3</td><td>10.09</td><td>高家堡镇、大保当镇交界</td></tr><tr><td></td><td>4</td><td>9.59</td><td>高家堡镇</td></tr><tr><td></td><td>5</td><td>7.39</td><td>太和寨、花石崖镇交界</td></tr><tr><td></td><td>6</td><td>6.59</td><td>栏杆堡镇</td></tr><tr><td></td><td>8</td><td>8.04</td><td>店塔镇</td></tr><tr><td></td><td>10</td><td>7.87</td><td>大柳塔镇</td></tr><tr><td>三级廊道</td><td>7</td><td>4.69</td><td>麻家塔办事处、神木镇交界</td></tr><tr><td></td><td>9</td><td>4.53</td><td>孙家岔镇、大柳塔镇交界</td></tr></table></body></html>

2.2.4优化结果分析生态廊道由景观生态学中的“廊道"这一概念演化而来，是指具有保护生物多样性，过滤污染物，防止水土流失，防风固沙，调控洪水等生态服务功能的廊道类型[21]。当外部威胁造成了格局内部变化及功能丧失时，廊道功能会降低甚至消失。因此，在景观管理及规划时，连接度十分重要，缺少连接度可能会导致生境隔离22。西北部地区是神木市生态源地集中分布的区域，物质、能量扩散的阻力小，等级较高的生态廊道呈现小规模聚集的特征，但整体连通性不足，通过新增1号、2号生态廊道将独立存在的小规模生态源地与主要生态源地相连接，同时形成了融会贯通的生态廊道群，实现了西北部地区生态源地间生态流的良好流通；新增3号、4号、5号生态廊道使生态环境脆弱的南部区域的生态廊道形成网络化态势,增强了南部生态脆弱区物质与能量的流通，提高了生态环境安全性;6号廊道作为边缘廊道与中部廊道贯通的桥梁，打破因人类活动产生的阻隔，将零星分布的生态源地串联起来以实现东部地区生态系统的生态服务功能；7号生态廊道，将北部与南部的主要生态廊道相连,增强了南北部的互通互联;8号、9号、10号新增廊道主要作用是将边缘生态廊道与东北地区的主要生态廊道相连，减少独立生态廊道数量，提高生态廊道的稳定性，提升东北地区生态安全稳定性。新增10条生态廊道从保护原有生态源地与生态廊道出发，充分考虑本底条件，建立与相邻生态源地相适应的廊道，从而改善景观破碎、物质流通不畅、生态源地不均等问题，优化神木市生态安全格局。

在进行生态廊道优化时，并未对所有生态廊道进行连接，一方面由于部分生态廊道周围阻力较大，若强行建设，消耗资源过多；另一方面是部分3级生态廊道在位于生态安全控制区内，级别较低、阻力较小、受到较好保护且极有可能在与神木市接壤的行政区范围内存在生态廊道，因此不进行优化。

# 3讨论

主成分分析法具有较强客观性、减少数据冗余、突出主要信息的优势[23],在客观确定权重的基础上，利用自然断点法依据区域生态安全综合得分将生态安全区划分为5个等级，如实反映神木市生态安全状况。基于MCR模型的生态安全研究较传统方法在影响因子的生态过程表达、空间可视化等方面具有一定优势[24]，使大尺度景观分析的实际操作成为可能，实现了定性与定量的深入研究23，被越来越广泛地应用于生态评价、土地利用、城市规划等方面。

本研究通过提取常规意义上的生态源地，如林地、草地、湖泊等土地类型以及生态安全控制区内的全部土地，根据生态安全评价结果,将1级景观生态安全区纳入生态源地，丰富了生态源地的确定方法，也使生态源地的确定更加符合当地的现实状况。基于MCR模型识别生态廊道，使得廊道的层次更加丰富、定位更加明晰，在综合考虑神木市本底条件、阻力面、生态廊道等多重因素，新增10条不同等级、不同类型的廊道，可以为神木市生态格局优化提供参考价值。本研究仍存在一些局限性，建立景观生态安全评价体系时，对景观指标进行了分级，但目前对于分级标准尚未形成统一定论，不同景观指标对于生态安全的影响有待进一步研究；在规划生态廊道时，并未对优化后的生态环境效益进行数学评价与建模分析，因此优化效果尚未有具体结果，有待于今后深入研究和完善。

# 4结论

综合运用主成分分析和MCR模型等方法，基于“源地-阻力面-廊道"的研究范式，对神木市生态廊道进行识别与优化，优化景观格局。主要得出如下结论：

（1）神木市景观生态安全状况分为5个等级，从1级到5级，生态安全水平逐渐降低。位于2级景观生态安全区的土地面积最大，其次为3级、1级、4级景观生态安全区，5级景观生态安全区面积最小。在景观生态安全评价基础上提取的生态源地存在空间分布不均的特征，集中分布在西北部地区，包含尔林兔镇、锦界镇、麻家塔办事处、大保当镇及高家堡镇，其余地区呈零星分布。

（2）利用自然断点法，将神木市按照累积阻力值大小划分为5级区域。从1级到5级，阻力值越来越大。阻力值越小，距离生态源地越近，阻力值越大，距离生态源地越远。

(3）基于MCR模型，识别神木市现存生态廊道共121条，其中约有 $1 9 . 0 8 \%$ 的生态廊道独立存在，约有 $4 3 . 5 1 \%$ 的生态廊道未与南北主要生态廊道群连通。

# 参考文献(References)：

[1]韩文权,常禹,胡远满,等.景观格局优化研究进展[J].生态学杂 志,2005,24(12): 1487-1492.[Han Wenquan, Chang Yu,Hu Yuanman,et al. Research advance in landscape pattern optimization [J]. Chinese Journal of Ecology,2005,24(12): 1487-1492.]   
[2]岳德鹏,王计平,刘永兵,等.GIS与RS技术支持下的北京西北 地区景观格局优化[J].地理学报,2007,62(11):1223-1231. [Yue Depeng,Wang Jiping, Liu Yongbing, et al. Landscape pattern optimization based on RS and GIS in Northwest of Beijing[J]. Acta Geographica Sinica,2007,62(11): 1223-1231.]   
[3]Shaygan M, Alimohammadi A, Mansourian A,et al. Spatial multiobjective optimization approach for land use allcation using NSGA-II[J].IEEE Journal of Selected Topics in Applied Earth Obser vation & Remote Sensing,2014,7(3): 906-916.   
[4]刘洋,蒙吉军,朱利凯.区域生态安全格局研究进展[J].生态学 报,2010,30(24):6980-6989.[Liu Yang,Meng Jijun, Zhu Likai. Progress in the research on regional ecological security pattern[J]. Acta Ecologica Sinica,2010,30(24): 6980-6989.]   
[5]俞孔坚.生物保护的景观生态安全格局[J].生态学报,1999,19 (1): 8-15.[Yu Kongjian. Landscape ecological security patterns in biological conservation[J]. Acta Ecologica Sinica, 1999,19(1): 8- 15.]   
[6]陈德权,兰泽英,李玮麒.基于最小累积阻力模型的广东省陆域 生态安全格局构建[J].生态与农村环境学报,2019,35(7):826- 835.[Chen Dequan,Lan Zeying,Li Weiqi. Construction of land ecological security in Guangdong Province from the perspecitve of ecological demand[J]. Journal of Ecology and Rural Environment, 2019,35(7): 826-835.]   
[7]魏伟,蕾莉,范雯,等.基于累积耗费距离理论的石羊河流域水 土资源优化配置[J].生态学杂志,2015,34(2):532-540.[Wei Wei,Lei Li,Fan Wen,et al.Water-soil resources optimization based on accumulative cost resistance model in Shiyang River basin[J]. Chinese Journal of Ecology,2015,34(2): 532-540.]   
[8]周锐,王新军,苏海龙,等.平顶山新区生态用地的识别与安全 格局构建[J].生态学报,2015,35(6):2003-2012.[Zhou Rui, Wang Xinjun, Su Hailong,et al.Identification of ecological land and construction of safety pattern in Pingdingshan New Area[J]. Acta Ecologica Sinica,2015,35(6): 2003-2012.]   
[9]陆禹,余济云,陈彩虹,等.基于粒度反推法的景观生态安全格 局优化—以海口市秀英区为例[J].生态学报,2015,35(19): 6384-6393.[Lu Yu,She Jiyun,Chen Caihong,et al.Landscape ecological security pattrn optimization based on the granularity inverse method: A case study in Xiuying District, Haikou[J].Acta Ecologica Sinica,2015,35(19): 6384-6393.]   
[10]唐丽,罗亦殷,罗改改,等.基于粒度反推法和MCR模型的海南 省东方市景观格局优化[J].生态学杂志,2016,35(12):3393- 3403.[Tang Li,Luo Yiyin,LuoGaigai,etal.Landscapeaer optimization based on the granularity inverse method and MCR model in Dongfang City,Hainan Province[J]. Chinese Journal of Ecology,2016,35(12): 3393-3403.]   
[11]郑好,高吉喜,谢高地,等.生态廊道[J].生态与农村环境学报, 2019,35(2): 137-144.[Zheng Hao,Gao Jixi,Xie Gaodi,et al. Ecological corridor[J]. Journal of Ecology and Rural Environment, 2019, 35(2): 137-144.]   
[12]Knaapen Jan P,Schefer Marten,Harms Bert. Estimating habitat isolation in landscape planning[J]. Landscape & Urban Planning, 1992, 23(1): 1-16.   
[13] 付刚,肖能文,乔梦萍,等.北京市近二十年景观破碎化格局的 时空变化[J].生态学报,2017,37(8):2551-2562.[Fu Gang, Xiao Nengwen, Qiao Mengping, et al. Spatial-temporal changes of landscape fragmentation paterns in Beijing in the last two decades[J]. Acta Ecologica Sinica,2017,37(8): 2551-2562.]   
[14] 李青圃,张正栋,万露文,等.基于景观生态风险评价的宁江流 域景观格局优化[J].地理学报,2019,74(7):1420-1437.[Li Qingpu, Zhang Zhengdong, Wan Luwen, et al.Landscape pattern optimization in Ningjiang River basin based on landscape ecological risk assessment[J].Acta Geographica Sinica,2019,74(7):1420 1437.]   
[15] 李振民,高青,周恺,等.景观连通性理论在城市土地适宜性评 价与优化方法中的应用[J].地理研究,2013,32(4):720-730. [Li Zhenmin, Gao Qing,Zhou Kai,et al. The application of landscape connectivity theory in urban ecology suitability assessment and optimization[J]. Geographical Research,2013,32(4):720- 730.]   
[16] 黄宁,杨绵海,林志兰,等.厦门市海岸带景观格局变化及其对 生态安全的影响[J].生态学杂志,2012,31(12):3193-3202. [Huang Ning, Yang Mianhai, Lin Zhilan,et al.Landscape pattern changes of Xiamen coastal zone and their impacts on local ecological security[J]. Chinese Journal of Ecology,2012,31(12): 3193- 3202.]   
[17]王思远,张增祥,周全斌,等.中国土地利用格局及其影响因子 分析[J].生态学报,2003,23(4): 649-656.[Wang Siyuan,Zhang Zengxiang,Zhou Quanbin,et al.Analysis of landscape patterns and driving factors of land use in China[J].Acta Ecologica Sinica, 2003,23(4): 649-656.]   
[18] 彭建,赵会娟,刘焱序,等.区域生态安全格局构建研究进展与 展望[J].地理研究,2017,36(3): 407-419.[Peng Jian, Zhao Huijuan, Liu Yanxu, et al. Research progress and prospect on regional ecological security pattrn construction[J]. Geographical Research, 2017,36(3): 407-419.]   
[19] 吴茂全,胡蒙蒙,汪涛,等.基于生态安全格局与多尺度景观连 通性的城市生态源地识别[J].生态学报,2019,39(13):4720- 4731.[Wu Maoquan, Hu Mengmeng, Wang Tao,etal.Recognition of urban ecological source area based on ecological security pattern and multi-scale landscape connectivity[J].Acta Ecologica Sinica,2019,39(13): 4720-4731.]   
[20] 喻锋,李晓兵,王宏.生态安全条件下土地利用格局优化——以 皇甫川流域为例[J].生态学报,2014,34(12):3198-3210.[Yu Feng,Li Xiaobing,Wang Hong. Optimization of land use pattern based on eco-security: A case study in the Huangfuchuan watershed[J].Acta Ecologica Sinica,2014,34(12): 3198-3210.]   
[21] 蒙倩彬.基于生物多样性保护的城市生态廊道研究[D].北京: 北京林业大学,2016.[Meng Qianbin.Studyon Urban Ecological Corrdor based on Biodiversity Conservation[D].Beijing:Beijing Forestry University,2016.]   
[22]叶鑫,邹长新,刘国华,等.生态安全格局研究的主要内容与进 展[J].生态学报,2018,38(10):3382-3392.[Ye Xin,Zou Changxin,Liu Guohua,et al. Main research contents and advances in the ecological security pattern[J]. Acta Ecologica Sinica,2018,38 (10): 3382-3392.]   
[23] 潘竟虎,刘晓.基于空间主成分分析和最小累积阻力模型的内 陆河景观生态安全评价与格局优化——以张掖市甘州区为例 [J].应用生态学报,2015,26(10):3126-3136.[Pan Jinghu,Liu Xiao.Assessment of landscape ecological security and optimization of landscape pattern based on spatial principal component analysis and resistance model in arid inland area: A case stdy of Ganzhou District, Zhangye City,Northwest China[J]. Chinese Jour nal of Applied Ecology,2015,26(10): 3126-3136.]   
[24] 黄木易,岳文泽,冯少茹,等.基于MCR模型的大别山核心区生 态安全格局异质性及优化[J].自然资源学报,2019,34(4):771- 784.[Huang Muyi,Yue Wenze,Feng Shaoru,et al.Analysis of spatial heterogeneity of ecological security based on MCR model and ecological pattrn optimization in the Yuexi county of the Dabie Mountain Area[J]. Journal of Natural Resource,2O19,34(4): 771-784.]

# Identification and optimization of ecological corridors in Shenmu City based on landscape ecological security

WU Jinhua, LIU Siyu, BAI Shuai (School of Land Engineering,Chang'an University,Xi'an 71Oo54, Shaanxi, China)

Abstract: In this study,the ecological security of the Shenmu City landscape was evaluated to optimizing its ecological pattern.Principal component analysis,the natural break point method,and the multivariate curve resolution (MCR) model were used to obtain the distribution of the ecological security patern in Shenmu City, China.Then,the ecological source area was extracted and the MCR model was used to construct the ecological corridor that optimizes the ecological landscape pattern. The results showed that the landscape security of Shenmu City is divided into five levels: The first level area is mostly located in the northwest,with a few areas distributed in the southeast and the northern margial areas; the secondary and tertiary regions are distributed in fragmented phases throughout the whole region; due to the impact of human activities and natural conditions, the fourth and fifth level regions are concentrated and distributed inthe central constructionarea,with the southeast gully crisscross area of fragmented distribution. Of the 121 ecological corridors in Shenmu City, $1 9 . 0 8 \%$ exist independently,and $4 3 . 5 1 \%$ are not connected to the main ecological corridor group.Thus,1O new ecological corridors were designed,with a total length of $7 6 . 6 9 ~ \mathrm { k m }$ to improve the ecological corridor network and strengthen the connection between the independent ecological corridors and the ecological source land.The results ofthis study are of great significance to optimize the landscape ecological environment of Shenmu City and to construct an ecological security pattern.

Keywords: ecological corridor； landscape ecological security evaluation; minimum cumulative resistance model; Shenmu City