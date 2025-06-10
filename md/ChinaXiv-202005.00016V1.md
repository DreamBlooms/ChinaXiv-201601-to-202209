# 柴达木盆地极端气候时空趋势及周期特征

葛根巴图²，魏巍³，张晓¹，杨晓晖1，时忠杰¹（1．中国林业科学研究院荒漠化研究所,北京10091；2．中国林业科学研究院沙漠林业实验中心,内蒙古磴口015200;3．北京林业大学水土保持学院，北京100083)

摘要：利用柴达木盆地8个气象站1960—2014年气温和降水的日值数据,分析该区域极端气候的时空变化趋势、周期特征及极端降水对南亚季风和西风环流变化的响应。结果表明;1960—2014 年柴达木盆地极端温度总体表现出显著的变暖趋势,变化幅度在空间上表现为由西向东逐渐降低;极端降水频率、降水量和降水强度均有所增加,但中西部地区变化速率远小于东部,仅连续无雨日数通过了显著性检验。平均温差、霜冻日数、冷夜日数的周期特征较弱,结冰日数和生长季日数的显著周期都有变长的趋势,而最低气温的显著周期有变短趋势;极端降水指标均有显著的周期特征,其中连续无雨日数和最大5日降水量的显著周期有变短趋势。同时,南亚季风环流与各极端降水指标间相关振荡的凝聚性很强，具有较强的关联性;而西风环流只与普通日降水强度存在着较强的共振关系。研究结果可为柴达木盆地可持续发展和生态环境保护提供理论与实践参考。

关键词：极端气候；时空趋势；周期特征；交叉小波变换；柴达木盆地

目前，全球气候变化已是不争的事实，IPCC第五次报告也再次明确,气候变暖是毋庸置疑的[1]。由于极端气候事件(暴雨洪涝、干旱、低温冷害、高温热浪等)对气候变化更为敏感[2],且对生态系统和人类社会的影响也更为显著[3-4],受到了国内外研究人员的高度关注[5]。在全球尺度上,极端气温呈显著变化， $70 \%$ 以上地区冷夜日数显著减少，而热夜日数呈显著增加趋势;极端降水也普遍呈现显著增加趋势,但是空间连续性较差[6]。Zhou 等[7]分析了1960—2010年中国极端气候变化发现,极端暖指标和极端冷指标分别呈显著上升和下降趋势，极端降水变化呈现出明显的空间复杂性，但影响范围不如极端气温广泛；尹红等利用1960一2017年中国均一化逐日气候数据分析了2017年中国极端气温和降水特征，表明中国区域多个极端气温指数达到或者接近历史极值,极端降水则接近正常年[8]。Wang等利用1961—2012年中国西北干旱区地面温度和降水日值0.5度格点数据分析表明，西北干旱区极端气温的变化趋势与气候变暖保持一致，极端降水和湿润日数呈增加趋势[9]。此外,还有很多学者从极端气候变化的季节差异、周期特征等不同的角度对中国各个区域极端气候变化开展了研究[10-12] 。

柴达木盆地位于青藏高原东北部，为阿尔金山、祁连山和昆仑山众多高山所环绕，受西风环流和高原季风的共同影响，气候寒冷干燥、降水稀少，是我国气候变化较为敏感的区域[13]。由于自然资源丰富，柴达木盆地素有“聚宝盆”之称，但因气候条件恶劣所引起的水资源匮乏、土地荒漠化、农业减产和生态环境恶化等一系列问题，成为制约其发展的重要因素[14]。因此,加强该地区气候研究,对于指导该地区资源合理开发利用和生态建设均具有重要的理论和现实意义。鉴于此，本文基于柴达木盆地8个气象站近55a的气象数据,研究了极端气候的变化趋势和周期特征，以期为区域可持续发展和生态环境保护提供理论与实践参考。

# 数据与方法

# 1.1 数据

采用中国气象局气象数据中心（http://data.cma.cn/site/index.html)发布的中国地面气候资料日值数据集1960一2014年柴达木盆地8个气象站的日最高气温、日最低气温、日降水数据等资料，气

88E 90°E 92°E 94°E 96°E 98E金出 冷湖 N△ N68尔 连阿 山德令哈祁漫塔 N小灶火 8图例 格 格尔木 诺木洪 都兰·气象站 山海拔/m16619 昆 Z2638 0 75150225300 km 仑 山 50象台站分布如图1所示。大气环流的数据则采用李建平等（http：//ljp.gcess.cn/dc t/page/65610）提供的南亚季风指数（SASMI）、北大西洋涛动指数(NAO)数据。

# 1.2 研究方法

为保证数据质量，首先采用RClimDex程序（ht-tp://etccdi.pacificclimate.org/software.shtml）对获取到的气象数据进行缺失值检验;异常值则采用直方图法进行检验，对于出现的异常值，参考前后几天该站数据或者同一天周边其他气象站数据，视情况进行调整或删除；并采用RHtestV4软件对数据的均一性进行检验，惩罚最大F检验结果显示8个气象站均不显著(0.05水平），这表明参与统计的8个气象站数据资料均一性良好。然后从世界气象组织（WMO)推荐的27个极端气候指标（http://cccma.seos.uvic.ca/ETCCDMI/list_27_indices.html）中选取8个气温指标和5个降水指标(表1），其计算过程在RclimDex程序中完成。极端气候的变化趋势采用非参数MK检验，变化量则采用非参数Sen's斜率计算。由于MK检验和Sen's斜率计算会受时间序列的自相关影响，因此，在检验前先对各气象站极端气候指标进行预白化处理[15]。极端气候的周期特征采用连续小波变换来检测[16],与大气环流的相关分析采用交叉小波变换[17],计算过程在Matlab中完成。

# 2结果与分析

# 2.1极端气候指标的时空趋势

2.1.1极端气温如图2a 和表2 所示,柴达木盆地1960一2014年的平均温差总体呈显著性减小趋势,为 $0 . 2 9 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } ;$ 8个气象站中只有诺木洪和都兰呈现增大趋势，但变化幅度较小，分别为$0 . 0 1 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ } ( \mathrm { ~ 1 0 a ~ } ) ^ { \ - 1 }$ 和 $0 . 0 7 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 }$ ,其余各站

# 表1极端气候指标及其定义

Tab.1 Definition of extreme climate indices used in this study   

<html><body><table><tr><td></td><td>指标</td><td>单位</td><td>定义</td></tr><tr><td>极端 气温</td><td>平均温差：DTR</td><td>℃</td><td>日温差的平均值</td></tr><tr><td>指标</td><td>霜冻日数FDO</td><td>d</td><td>日最低气温（TN）<0℃ 的日数</td></tr><tr><td></td><td>生长季长度：GSL</td><td>d</td><td>至少6日的日平均气温> 5℃的初日与<5℃的终</td></tr><tr><td></td><td>结冰日数：IDO</td><td>d</td><td>日间的日数 日最高气温（TX）<0℃</td></tr><tr><td></td><td>最高气温：TXx</td><td>℃</td><td>的日数 年、月最高气温的最大值</td></tr><tr><td></td><td>最低气温：TNn</td><td>℃</td><td>年、月最低气温的最小值</td></tr><tr><td></td><td>暖昼日数：Tx90p</td><td>d</td><td>日最高气温（TN）>90% 分位数的日数</td></tr><tr><td></td><td>冷夜日数：Tn10p</td><td>d</td><td>日最低气温（TN）<10%</td></tr><tr><td>极端</td><td>连续无雨日数：CDD</td><td>d</td><td>分位数的日数 最长连续无降水日数</td></tr><tr><td></td><td>降水年降水量：PRCPTOT</td><td>mm</td><td>≥1 mm 降水日累积量</td></tr><tr><td>指标</td><td>日最大降水量：Rx1d</td><td>mm</td><td>日最大降水量</td></tr><tr><td></td><td>连续5日降水量：Rx5d</td><td>mm</td><td>连续5日最大降水量</td></tr><tr><td></td><td>普通日降水强度 SDII</td><td>mm·d-1</td><td>年降水量或≥1mm 日数</td></tr></table></body></html>

均表现出显著减小趋势,以德令哈和格尔木变化幅度最大，分别为 $0 . 6 2 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ~ ) ~ } ^ { - 1 }$ 和 $0 . 6 8 \mathrm { ~ \textdegree C }$ ：(10a) $^ { - 1 }$ （表3）。霜冻日数（图2b）结冰日数（图2d)、冷夜日数(图2e)也均呈持续减少趋势，且通过了显著性检验,变化幅度分别为 $5 . 4 6 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 } .$ 、$5 . 1 3 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ 和 $3 . 9 3 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ;参与统计的8 个气象站均通过了显著性检验、呈减少趋势,以茫崖的变化幅度最大，分别为 $1 0 . \ 0 7 \ \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ~ ) ~ } ^ { - 1 } .$ 、$7 . 5 2 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ 和 $6 . 2 1 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ,都兰的霜冻日数和冷夜日数变化幅度最小，分别为 $2 . 5 1 \textrm { d } \cdot$ (10a) $^ { - 1 }$ 和 $1 . 5 8 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ,冷湖的结冰日数变化幅度最小，,为 $3 . 5 5 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ （表3）。生长季长度以 $4 . 0 4 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ 的趋势显著增加（图2c），参与统计的8个气象站均呈现增加趋势，只有都兰未通过显著性检验,变化幅度为 $1 . 4 7 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ，以茫崖的增加幅度最大,为 $6 . 3 2 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ （表3）。暖昼日数以 $2 . 1 2 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ 的趋势显著增加（图$2 \mathrm { g }$ ),8个气象站均通过了显著性检验，以茫崖增加趋势最大，为 $3 . 5 2 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ，德令哈最小，为$1 . 4 4 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ （表3）。最高气温和最低气温均表现为波动上升，且均通过了显著性检验，上升趋势分别为 $0 . 3 0 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ } ( 1 0 \mathrm { a } ) ^ { \mathrm { ~ - 1 ~ } }$ 和 $0 . 7 9 \mathrm { ~ \textcircled { C } ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 }$ ；最高气温上升趋势以茫崖最大，为 $0 . 5 4 ~ \mathrm { ^ { \circ } C }$ ：

![](images/88fb46357b089b4c05747a4ed768523c3c648312f3fc006816f454de3eea1beb.jpg)  
注：黑色实线代表线性趋势，虚线为9a滑动平均曲线。  
图2极端气温的标准化距平  
Fig.2Regionally averaged anomaly series of the extreme temperature

表21960—2014年柴达木盆地极端气候变化趋势 Tab.2Trends per decade of extreme climate over Qaidam basin during 196O -2014   

<html><body><table><tr><td>指标</td><td>单位</td><td>1960—2014 年</td></tr><tr><td>DTR</td><td>C·(10a)-1</td><td>-0.29(-0.52，-0.07)</td></tr><tr><td>FD0</td><td>d·(10a)-1</td><td>-5.46( -7.57，-3.34)</td></tr><tr><td>GSL</td><td>d·(10a)-1</td><td>4.04(2.70,5.39)</td></tr><tr><td>ID0</td><td>d·(10a)-1</td><td>-5.13(-6.11，-4.15)</td></tr><tr><td>Tn10p</td><td>d·（10a）-1</td><td>-3.93(-5.26，-2.59)</td></tr><tr><td>TNn</td><td>C·(10a）-1</td><td>0.79(0.31,1.27)</td></tr><tr><td>Tx90p</td><td>d·(10a)-1</td><td>2.12 (1.50,2.74)</td></tr><tr><td>TXx</td><td>C·(10a)-1</td><td>0.30(0.11,0.48)</td></tr><tr><td>CDD</td><td>d·(10a)-1</td><td>-5.19( -9.94，-0.44)</td></tr><tr><td>PRCPTOT</td><td>mm·（10a）-1</td><td>6.10(-0.67,12.88)</td></tr><tr><td>Rx1d</td><td>mm·（10a）-1</td><td>0.50(-0.10,1.1)</td></tr><tr><td>Rx5d</td><td>mm·（10a）-1</td><td>1.01(-0.33,2.36)</td></tr><tr><td>SDII</td><td>mm·d-1·（10a)-1</td><td>0.11(0.00.0.23)</td></tr></table></body></html>

注：黑体表示该指标在区域上变化显著,括号内为该指标 $9 5 \%$ 置信区间范围。

（10a）-',最低温度上升趋势以格尔木最大,为1.67$\mathrm { ~ \textit ~ { ~ C ~ } ~ } \cdot \left( 1 0 \mathrm { { a } } \right) ^ { - 1 }$ （表3）。

2.1.2极端降水如图3a和表2所示，柴达木盆地1960—2014年连续无雨日数以 $5 . 1 9 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ 的趋势显著减少;参与统计的8个气象站中，大柴旦、诺木洪和都兰表现为增加趋势，但均不显著且变化幅度较小，分别为 $0 . 8 3 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ~ ) ~ } ^ { - 1 } \mathrm { ~ , ~ } 0 . 3 1 \mathrm { ~ d ~ } \cdot$ (10a) $^ { - 1 }$ 和 $0 . 8 3 \mathrm { ~ d ~ } \cdot \mathrm { ~ } ( 1 0 \mathrm { a } ) ^ { \mathrm { ~ } ^ { - 1 } }$ ,其余5个气象站均表现为减少趋势，其中茫崖、冷湖、德令哈变化显著，变化幅度分别为 $1 2 . \ 9 6 \ \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ~ ) ~ } ^ { - 1 }$ 、10.51 d·(10a) $^ { - 1 }$ 和 $8 . 8 9 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 } \cdot$ （表3）。年降水量（图3b)和普通日降水强度(图3e)均呈现波动增加，但并未通过显著性检验,变化幅度分别为 $6 . 1 \ \mathrm { m m } \cdot \$ (10a) $^ { - 1 }$ 和 $0 . 1 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ;参与统计的8个气象站中，只有德令哈和都兰的年降水量呈现显著增加趋势，变化幅度分别为 $2 0 . 4 5 \mathrm { \ m m } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ~ ) ~ } ^ { - 1 }$ 和 $1 7 . 8 3 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,冷湖、德林哈、诺木洪、都兰注：黑色实线代表线性趋势，虚线为9a滑动平均曲线。

表3柴达木盆地各气象站极端气候指标变化趋势的显著性及变化量 Tab.3Significance and magnitude of extreme climate in each station   

<html><body><table><tr><td>指标</td><td>茫崖</td><td>冷湖</td><td>小灶火</td><td>大柴旦</td><td>德令哈</td><td>格尔木</td><td>诺木洪</td><td>都兰</td></tr><tr><td>DTR</td><td>-0.32 ***</td><td>-0.28 ***</td><td>-0.15 **</td><td>-0.37 ***</td><td>-0.62 ***</td><td>-0.68 ***</td><td>0.01</td><td>0.07 *</td></tr><tr><td>FD0</td><td>-10.07 ***</td><td>-3.24 ***</td><td>-6.81 ***</td><td>-4.92 ***</td><td>-6.01***</td><td>-6.94 ***</td><td>-3.14 ***</td><td>-2.51**</td></tr><tr><td>GSL</td><td>6.32 ***</td><td>2.19 *</td><td>4.43 ***</td><td>4.17 ***</td><td>4.00 ***</td><td>5.72 ***</td><td>4.05 ***</td><td>1.47</td></tr><tr><td>ID0</td><td>-7.52 ***</td><td>-3.55 ***</td><td>-5.67 ***</td><td>-5.07 ***</td><td>-5.47 ***</td><td>-4.25 ***</td><td>-4.70 ***</td><td>-4.82 ***</td></tr><tr><td>Tn10p</td><td>-6.21***</td><td>-3.14 ***</td><td>-3.07***</td><td>-3.79 ***</td><td>-4.93 ***</td><td>-5.82***</td><td>-2.85 **</td><td>-1.58 ***</td></tr><tr><td>TNn</td><td>0.95 ***</td><td>0.35 *</td><td>0.31</td><td>0.73 ***</td><td>1.62 ***</td><td>1.67 ***</td><td>0.44 **</td><td>0.25</td></tr><tr><td>Tx90p</td><td>3.52 ***</td><td>1.47 ***</td><td>2.57 ***</td><td>1.74 ***</td><td>1.44***</td><td>1.93 ***</td><td>2.72 ***</td><td>1.54 ***</td></tr><tr><td>TXx</td><td>0.54 ***</td><td>0.00</td><td>0.61 ***</td><td>0.34 *</td><td>0.11</td><td>0.14</td><td>0.46 **</td><td>0.18</td></tr><tr><td>CDD</td><td>-12.96 *</td><td>-10.51*</td><td>-8.78</td><td>0.83</td><td>-8.89 **</td><td>-2.35</td><td>0.31</td><td>0.83</td></tr><tr><td>PRCPTOT</td><td>1.08</td><td>0.87</td><td>1.69</td><td>3</td><td>20.45 ***</td><td>1.62</td><td>2.30</td><td>17.83 ***</td></tr><tr><td>Rx1d</td><td>0.04</td><td>0.08</td><td>0.29</td><td>-0.12</td><td>1.51 *</td><td>-0.26</td><td>1.01 *</td><td>1.44 *</td></tr><tr><td>Rx5d</td><td>-0.14</td><td>0.06</td><td>0.28</td><td>0.63</td><td>4.33 ***</td><td>-0.31</td><td>0.75</td><td>2.54 **</td></tr><tr><td>SDII</td><td>0.00</td><td>0.17 ***</td><td>0.04</td><td>0.00</td><td>0.22 **</td><td>-0.06</td><td>0.21*</td><td>0.32 ***</td></tr></table></body></html>

注：-表示下降趋势； $\ast$ 表示在0.05 水平上显著， $* *$ 表示在0.01水平上显著， $\ast \ast \ast$ 表示在0.001水平上显著

![](images/d1b84166801bf9494eb62a4c14b7deec51ab0f8293580048222fa4a248a4bab7.jpg)  
图3极端降水的标准化距平  
Fig.3Regionally averaged anomaly series of the extreme precipitation

的普通日降水强度呈现显著增加趋势，变化幅度分别为 $0 . 1 7 , 0 . 2 2 , 0 . 2 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ·(10a) $^ { - 1 }$ 和0.32$\mathrm { \ m m } \cdot \mathrm { d } ^ { - 1 } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 }$ ,其余各站均未通过显著性检验（表3）。日最大降水量(图3c）和连续五日降水量(图3d)均呈现波动增加，但未通过显著性检验，变化幅度分别为 $0 . \ 5 \ \mathrm { \ m m } \ \cdot \ ( \ 1 0 \mathrm { a } ) \ ^ { - 1 }$ 和 $1 . 0 1 \ \mathrm { m m }$ ：（10a）-1;参与统计的8个气象站中，只有德林哈、诺木洪和都兰的日最大降水量呈现显著增加趋势，变化幅度分别为 $1 . 5 1 \_ 1 . 0 1 \ \mathrm { m m } \cdot \left( \mathrm { 1 0 a } \right) ^ { - 1 }$ 和1.44$\mathrm { { m m } \cdot ( 1 0 \mathrm { { a } ) ^ { - 1 } } }$ ,德令哈和都兰连续5日最大降水量通过显著性检验，变化幅度分别为4.33和2.54$\mathrm { { m m } \cdot ( 1 0 \mathrm { { a } ) ^ { - 1 } } }$ ,其余各站均未通过显著性检验（表3);此外,有个别气象站（茫崖、大柴旦、格尔木）呈现减少趋势，但变化幅度较小。

# 2.2极端气候指标的连续小波分析

2.2.1极端气温如图4a所示，平均温差的能量密度分布以低频为主，存在 $2 . 1 9 \sim 2 . 7 6$ a和 $2 . 4 6 \sim$ 2.76a的振荡周期，分别在1962—1966 年和1975—1976 年通过了 $9 5 \%$ 红噪声检验。霜冻日数(图4b)能量密度分布以低频为主，存在 $2 . 1 9 \sim 2 . 3 1$ a和$2 . 6 0 \sim 3 . 0 9$ a 的振荡周期,分别在1961—1962 年和1997—1998年通过了 $9 5 \%$ 红噪声检验。结冰日数（图4c）存在 $2 . 4 6 \sim 4 . 1 3$ a的振荡周期,并在1987—1998年通过了 $9 5 \%$ 红噪声检验且能量密度在1989—1992年最大，具有显著的频域周期特征，1995—1998年能量偏向周期值较大区域;此外，结冰日数还存在 $2 . 4 6 \sim 2 . 7 6$ a 的振荡周期在1963—1965 年通过了 $9 5 \%$ 红噪声检验。冷夜日数(图4d)

的能量密度分布以低频为主，只有 $2 . 1 9 \sim 2 . 9 2$ a的振荡周期在1967—1970年通过了 $9 5 \%$ 红噪声检验。生长季长度(图4e)存在 $2 . 0 7 \sim 2 . 7 6 \$ a和$2 . 7 6 \sim 3 . 4 7$ a的振荡周期，分别于1967—1974年和2004—2011年通过了 $9 5 \%$ 红噪声检验。暖昼日数(图4f)存在 $2 . 1 9 \sim 2 . 4 6$ a和2.19\~4.38a的振荡周期，分别在 2005—2007 年和 2005—2014 年通过了 $9 5 \%$ 红噪声检验，但后者大部分处于COI之外。最高气温（图 ${ 4 \mathrm { g } }$ )存在一个明显的 $2 . 6 0 \sim 3 . 9 0 \mathrm { ~ } \mathfrak { s }$ 的振荡周期且能量密度最大，具有显著的频域周期特征，在1965—1970年通过了 $9 5 \%$ 红噪声检验。最低气温(图4h)存在 $2 . 1 9 \sim 2 . 9 2$ a 的主振荡周期,在1986—1992年通过了 $9 5 \%$ 红噪声检验;此外，还存在一个 $3 . 4 7 \sim 3 . 6 8$ a的振荡周期，仅在1976 年通过了 $9 5 \%$ 红噪声检验。

2.2.2极端降水如图5a 所示，柴达木盆地1960—2014年连续无雨日数存在 $3 . 2 8 \sim 4 . 9 1 \$ a的主振荡周期，在1976—1986年通过了 $9 5 \%$ 红噪声检验，能量密度在1980—1984 年最大，在通过红噪声检验的其他时域相对较弱，1978—1982年能量集中且偏向于周期值较小区域;此外，还有 $3 . 2 8 \sim$ 3.68a的振荡周期在1962—1964年通过了 $9 5 \%$ 红噪声检验，但处于COI之外。年降水量(图5b)存在$3 . 2 8 \sim 3 . 6 8 \$ a的振荡周期，在1962—1964年通过了$9 5 \%$ 红噪声检验。普通日降水强度(图5c)存在$3 . 4 7 \sim 3 . 9 0 \$ a $、 7 . 8 0 \sim 9 . 2 8$ a和 $2 . 0 7 \sim 2 . 6 0 \$ a的振荡周期，分别在1965—1968 年、1973—1980 年和1979—1984年通过了 $9 5 \%$ 红噪声检验，以1973—1980 年能量密度最大。日最大降水量(图5d)存在$2 . 0 6 \sim 2 . 7 6$ a和 $2 . 3 2 \sim 2 . 6 0$ a的振荡周期，分别在1976—1980 年和 2009—2011 年通过了红噪声检验;此外,还存在 $4 . 9 1 \sim 6 . 1 9$ a的振荡周期,在2005—2011年通过了红噪声检验，但处于COI之外。连续5日最大降水量(图5e)存在 $3 . 4 7 \sim 3 . 9 \$ a和 $2 . 0 7 \sim 3 . 1 0 \mathrm { ~ a ~ }$ 的振荡周期，分别在1966一1970年和1975—1981年通过了 $9 5 \%$ 红噪声检验。

# 2.3季风环流、西风环流与极端降水的交叉小波变换

由图6a所示，在COI区域内，SASMI和连续无雨日数通过 $9 5 \%$ 红噪声检验的主共振周期为$2 . 3 1 \sim 3 . 6 8 \mathrm { ~ a ~ }$ ;在此周期上，二者有显著共振关系，振荡的凝聚性最强,交叉相位为 $1 3 5 . 3 6 ^ { \circ } \pm 1 8 . 6 3 ^ { \circ }$ ，即连续无雨日数滞后1.13a左右。其中， $\pm 1 8 . 6 3 ^ { \circ }$ 为相位角计算中的卷积误差，由于其并不改变交叉相位的符号，因此，这种相位变化是相对稳定的，在此周期上连续无雨日数随着南亚季风指数的变化而变化。此外，还存在 $4 . 1 3 \sim 4 . 6 4$ a和 $2 . 6 0 \sim 3 . 2 8 \$ a的共振周期分别在1982—1987年和1991—1995年通过了红噪声检验,但涵盖时域较短，其他周期上连续无雨日数和南亚季风指数的共振能量较低，没有通过 $9 5 \%$ 红噪声检验。

由图6b所示，在COI区域内，SASMI和年降水量通过 $9 5 \%$ 红噪声检验的主共振周期为 $2 . 6 0 \sim$ 3.68a;在此周期上，二者具有显著共振关系，振荡的凝聚性最强，交叉相位为 $- 4 9 . 0 6 ^ { \circ } \pm 2 1 . 5 2 ^ { \circ }$ ，即年降水量变化提前0.43a左右。 $\pm 2 1 . 5 2 ^ { \circ }$ 为相位角计算中的卷积误差，由于其并不改变交叉相位的符号，因此这种相位变化是相对稳定的。此外，还有$2 . 3 2 \sim 2 . 4 6$ a 的共振周期在1977—1978年通过了红噪声检验，但涵盖时域较短，其他频段上年降水量和南亚季风指数的共振能量较低，没有通过 $9 5 \%$ 红噪声检验。

由图6c所示，在COI区域内，SASMI和日最大降水量通过 $9 5 \%$ 红噪声检验的主共振周期分别为$3 . 1 0 \sim 3 . 4 7$ a和 $2 . 0 7 \sim 2 . 7 6$ a,交叉相位分别为$- 9 1 . 3 6 ^ { \circ } \pm 2 2 . 9 0 ^ { \circ }$ 和 $5 . 0 2 ^ { \circ } \pm 5 3 . 1 8 ^ { \circ }$ ，由于后者卷积误差为 $\pm 5 3 . 1 8 ^ { \circ }$ ，改变了交叉相位的符号，故SASMI和日最大降水量在 $2 . 0 7 \sim 2 . 7 6 \$ a的共振周期不稳定，而在 $3 . 1 0 \sim 3 . 4 7$ a 的共振周期上，日最大降水量变化提前 $0 . 8 3 \mathrm { ~ a ~ }$ 左右。其他频段上日最大降水量和南亚季风指数的共振能量较低，没有通过 $9 5 \%$ 红噪声检验。

由图6d所示，在COI区域内，SASMI和连续5日最大降水量通过 $9 5 \%$ 红噪声检验的主共振周期分别为 $2 . 9 2 \sim 3 . 6 8$ a和 $2 . 0 7 \sim 2 . 7 6 \mathrm { ~ a ~ }$ ；在此周期上，二者有显著共振关系，振荡的凝聚性最强。其中，在 $2 . 9 2 \sim 3 . 6 8 \$ a的共振周期上，SASMI和连续5日最大降水量的交叉相位为 $- 8 1 . 8 2 ^ { \circ } \pm 3 9 . 1 0 ^ { \circ }$ ,即连续5日最大降水量变化提前0.75a左右；在$2 . 0 7 \ \sim 2 . \ 7 6$ a的共振周期上，其交叉相位为$7 0 . 3 9 ^ { \circ } \pm 5 6 . 8 3 ^ { \circ }$ ,即连续5日最大降水量变化滞后0.47a左右，二者卷积误差均不改变交叉相位符号，因此变化是稳定的。

由图6e所示，在COI区域内，SASMI和普通日降水强度通过 $9 5 \%$ 红噪声检验的主共振周期为$2 . 9 2 \sim 3 . 6 8 \mathrm { ~ a ~ }$ ;在此周期上有显著共振关系，振荡的

![](images/69996dc255395051f22824e2ae1f6e5129f5e4b000cae69ed39510479e20e29d.jpg)

注：红色与蓝色分别表示能量密度的峰值和谷值，反映了主导波动组分时频变换的局部性和动态性特征，颜色深浅表示能量密度的相对变化[18]。黑色粗实线圈闭的值通过了 $9 5 \%$ 置信水平的红噪声检验,黑色细实线包络显示了COI（Cone of influence,小波影响锥,表示连续小波变换的数据边缘效应影响较大的区域）区域[19]。下同。

![](images/c6468791f179ba7a3f178f28309553b76dabc2095ad4538cf5d5be459555e6d7.jpg)  
图4极端气温指标的连续小波变换  
Fig.4Continuous wavelet transform of extreme temperature indices   
图5极端降水指标的连续小波变换  
Fig.5Continuous wavelet transform of extreme precipitation indices

![](images/bd172f568b7857478ff6166732effa6ec7728705a90411053b3869043a359528.jpg)  
注：箭头方向表示二者的相位关系，其中箭头指向由左向右表示同相位，由右向左表示反相位，箭头垂直向上则表示极端降水指标变化提前南亚季风环流指数和北大西洋涛动指数1/4个周期，箭头垂直向下则表示极端降水指标变化滞后南亚季风环流指数和北大西洋涛动指数1/4个周期。  
图6极端降水指标与南亚季风环流指数和北大西洋涛动指数的交叉小波变换 Fig.6Cross wavelet transform of extreme precipitation indices with SASMI and NAO

凝聚性最强，SASMI和普通日降水强度的交叉相位为 $- 8 9 . 2 1 ^ { \circ } \pm 2 4 . 2 8 ^ { \circ }$ ,即普通日降水强度变化提前0.82a左右。卷积误差为 $2 4 . 2 8 ^ { \circ }$ ,由于其并不改变交叉相位的符号，这种相位变化是相对稳定的。此外，还有 $2 . 1 9 \sim 2 . 6 0$ a和 $2 . 7 6 \sim 3 . 1 0$ a 的共振周期分别在1978—1980 年和1990—1992 年通过了红噪声检验，但涵盖时域较短，其他频段上连续无雨日数和南亚季风指数的共振能量较低，没有通过 $9 5 \%$ 红噪声检验。

由图6f\~6j可知，在COI区域内，NAO 和各极端降水指标通过 $9 5 \%$ 红噪声检验的主共振周期涵盖时域均较短，只有普通日降水强度和 NAO 在1974—1987 年存在 $8 . 2 6 \sim 8 . 7 6$ a的主共振周期有显著共振关系,振荡的凝聚性最强。在此周期上,普通日降水强度和NAO的交叉相位为 $- 1 3 3 . 7 9 ^ { \circ } \pm$ $7 . 5 4 ^ { \circ }$ ,即普通日降水强度变化提前3.15a左右。卷积误差为 $7 . 5 4 ^ { \circ }$ ，由于其并不改变交叉相位的符号，这种相位变化是相对稳定的。

# 3结论与讨论

# 3.1结论

（1）1960—2014年，柴达木盆地极端气温显著上升，极端降水的频率、降水量和降水强度也均有所增加，总体呈暖湿化趋势。

(2）在空间上，极端气温的变化幅度表现为由西向东逐渐降低，而极端降水的变化幅度则与极端气温相反，以东部地区更为显著。

（3）极端气温的周期特征较弱，结冰日数和生长季长度的显著周期有变长趋势，最低气温有变短趋势；极端降水指标具有较强的周期特征，连续无雨日数和最大5日降水量的显著周期有变短趋势。

# 3.2讨论

1960一2014年，柴达木盆地极端气温总体呈现出显著的变暖趋势，具体表现为所有极端气温指标均通过显著性检验,其中 $\mathrm { T x 9 0 p \Omega , T X x \Omega , T N n }$ 和GSL呈上升趋势，而 $\mathrm { T n 1 0 p }$ 、FDO、IDO和DTR呈下降趋势，且后者下降较前者的上升趋势更为明显，这与青藏高原中东部地区极端气温趋势分析的结论是基本一致的[20],主要归因于全球气候变暖导致极端气候事件的增多[21]。参与统计的8个气象站绝大多数指标均通过了显著性检验，位于北部的冷湖和东南部的都兰变化幅度较小，其余6个气象站的变化幅度均较大，尤以位于西部的茫崖最为明显，在空间上变化幅度呈现出由西向东逐渐降低的趋势，这可能是植被覆盖变化的经向地带性分布和高原季风变化所导致的[22]。连续小波变换的结果表明,DTR、FD0、$\mathrm { T n } 1 0 \mathrm { p }$ 的周期特征较弱，虽然有部分周期通过了显著性检验，但涵盖时域较短;IDO和GSL的显著周期都有变长的趋势，而最低气温有变短趋势。

极端降水的频率、降水量和降水强度均有所增加，但除了CDD外，其余指标变化趋势并不显著。从空间上看，极端降水的变化趋势恰与极端气温相反，位于盆地东部的德林哈和都兰的降水量以及降水强度远大于中西部地区，虽然中西部其他6个气象站呈现出湿润化的趋势，但变化幅度较小且并不显著，个别气象站的降水量和降水强度还有减小趋势。根据王可丽等[23]对我国西北地区水汽输送的研究，柴达木盆地中西部的水汽输送主要受西风环流的控制，而东部则受南亚季风的影响。本研究中，SASMI和各极端降水指标的交叉小波变换表明二者有很强的共振关系，而NAO仅与SDII间存在较强的共振关系，加之西风环流所携带水汽含量较少，这可能是柴达木盆地极端降水呈现上述空间变化特征的主要原因。连续小波变换的研究表明，5个极端降水指标均有显著的周期特征，其中连续无雨日数和最大5日降水量的显著周期有变短趋势。

柴达木盆地内分布有我国的第5大沙漠——柴达木盆地沙漠，植被恢复对该区荒漠化防治至关重要[24]。从本研究的结果来看,IDO、FDO、 $\mathrm { T n } 1 0 \mathrm { p }$ 等极端冷指标的减少使植被避免低温冻害的影响;其次，极端气温的上升能够改善早春植物萌发所需的土壤热力状况，从而促使其提前萌发，PRCPTOT的增加可以改善植物生长季的土壤水分条件，进而促进植物生长并推迟植物枯萎时间，延长植物生长季长度，本研究中 $\mathrm { G S L } 4 . 0 4 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ) ~ } ^ { - 1 }$ 的上升趋势和近年来该区域植被变化的相关研究[25]也同样证实了这一点。最后，CDD的减少可以避免植物受长期干旱胁迫的影响,SDII、Rx1d和 $\mathrm { R x } 5 \mathrm { d }$ 的增加使得降雨向土壤更深层入渗[26],从而增加植被可利用水量和深根植物生长所需的水分补给。由此可见，柴达木盆地极端气候变化趋势可能对该区的植被恢复有较大的促进作用，应进一步加强人工促进植被恢复工作，加速该区域的生态环境修复。

# 参考文献（References）:

[1]IPCC.Climate Change 2013:The Physical Science Basis.Contribution of Working Group I to the Fifth Assessment Report of the Intergovernmental Panel on Climate Change[M].Cambridge:Cambridge University Press,2013:1-1552.   
[2]Katz R W,Brown B G.Extreme events in a changing climate:Variability is more important than averages[J].Climatic Change, 1992,21(3):289-302.   
[3]Salinger MJ,Grifiths G M.Trends in New Zealand daily temperature and rainfall extremes[J]. International Journal of Climatology, 2001,21(12):1437 -452.   
[4] Bennett KE,Walsh JE.Spatial and temporal changes in indices of extreme precipitation and temperature for Alaska[J].International Journal of Climatology,2015,35（7）:1434-1452.   
[5]Li Zongxing,He Yuanqing,Wang Puyu,et al.Changes of daily climate extremes in southwestern China during 1961 - 2008[J]. Global and Planetary Change,2012,80:255-272.   
[6] AlexanderLV,Zhang X,Peterson TC,et al.Global observed changes in daily climate extremes of temperature and precipitation [J].Journal of Geophysical Research,2006,111（D05109）.   
[7]Zhou B,Xu Y,Wu J,et al. Changes in temperature and precipitation extreme indices over China:analysis of a high resolution grid dataset[J]. International Journal of Climatology,2016,36（3）： 1051 -1066.   
[8］尹红,孙颖.基于ETCCDI指数 2017 年中国极端温度和降水特 征分析[J].气候变化研究进展,2019,15(4)：363-373.［YinHong,Sunying.Characteristics of extreme temperature and precipitation in China in 2O17 based on ETCCDI indices[J].Climate Change Research,2019,15(4） :363 -373.]   
[9]Wang Y,Zhou B,Qin D,et al.Changes in mean and extreme temperature and precipitation over the arid region of northwestern China:observation and projection[J].Advances in Atmospheric Sciences,2017,34(3):289 -305.   
[10］高妍,冯起,李宗省,等.祁连山讨赖河流域1957-2012 年极 端气候变化[J].中国沙漠,2014,34(3）:814-826.［Gao Yan， Feng Qi,Li Zongxing,et al.The variation of climate extremes in the Taolaihe River Basin in the Qilian Mountains of China during 1957 - 2012[J].Journal of Desert Research,2014,34(3）:814-826.]   
[11］蔡新玲,吴素良,贺皓,等.变暖背景下陕西极端气候事件变化 分析[J].中国沙漠,2012,32（4）:1095-1101.[Cai Xinling, Wu Suliang,He Hao,et al. Change of extreme Climate Events in Shaanxi Province under global warming background[J]. Journal of Desert Research,2012,32(4）:1095-1101.]   
[12］刘学智,李王成,苏振娟,等.1962-2015 年宁夏平均气温和极 端气温的变化特征［J].干旱区研究,2018,35（5）：1173- 1180.[Liu Xuezhi,Li Wangcheng,Su Zhenjuan,etal. Change of mean temperature and extreme temperature in Ningxia during the period of 1962 -2015[J]. Arid Zone Research,2018,35（5）: 1173 -1180.]   
[13］陈涛,宋友桂,李云,等.柴达木盆地末次盛冰期与全新世大暖 期风沙活动的对比研究［J].干旱区研究 2016,33（4）：877- 883.[Chen Tao,Song Yougui,Li Yun.Wind-blown sand activities in the Qaidam basin during the last glacial maximum and the holocene megathermal period[J].Arid Zone Research,2016,33（4）： 877 -883.]   
[14］张娟,肖宏斌,徐维新,等.1971-2010 年柴达木盆地可降水量 变化特征及其与气象条件分析[J].资源科学,2013,35（11）： 2289 -2297.[Zhang Juan,Xiao Hongbing,Xu Weixin.Precipitable water variation and its impact factors in recent 4O years in Qaidam basin[J]. Resources Science,2013,35(11):2289 -2297.]   
[15]Yue S,Pilon P,Phinney B,et al. The influence of autocorrelation on the ability to detectrend in hydrological series[J].Hydrological Processes,2002,16(9) :1807 -1829.   
[16]Torrence C,Compo G P.A practical guide to wavelet analysis[J]. Bulletin of the American Meteorological Society,1998,79（1）:61 -78.   
[17]Grinsted A,Moore JC,Jevrejeva S.Application of the cross wavelet transform and wavelet coherence to geophysical time series[J]. Nonlinear Processes in Geophysics,2004,11(5/6) :561-566.   
[18］王亚敏,张勃,郭玲霞,等.地磁Ap 指数与太阳黑子数的交叉 小波分析及R/S分析[J].地理科学,2011,31(6)：747-752. [Wang Yamin,Zhang Bo,Guo Lingxia,et al. Cross wavelet analysis and R/S analysis of relationship between geomagnetic Ap idex and sunspot number[J]. Scientia Geographica Sinica,2011,31 (6):747 -752. ] [19］祁晓凡,杨丽芝,韩晔,等.济南泉域地下水位动态及其对降水 响应的交叉小波分析[J].地球科学进展,2012,27(9)：969-   
978.[Qi Xiaofan,Yang Lizhi,Han Ye,et al. Cross wavelet analysis of groundwater level regimes and precipitation-groundwater level regime in Ji'nan Spring Region[J].Advances in Earth Science,   
2012,27(9) :969-978.] [20]You Q,Kang S,Aguilar E,et al. Changes indailyclimate extrmes in the Eastern and central Tibetan Plateau during 1961 - 2005 [J].Journal of Geophysical Research,2Oo8,113,（D7）. [21］游庆龙,康世昌,闫宇平,等.近45 年雅鲁藏布江流域极端气 候事件趋势分析[J].地理学报,2009,64（5）：592-600.［You Qinglong,Kang Shichang,Yan Yuping,et al.Trends in daily temperature and precipitation extremes over the Yarlung Zangbo River basin during 1961-2005[J]. Acta Geographica Sinica,2009,64 (5):592 -600.] [22］李林,申红艳,李红梅,等.柴达木盆地气候变化的区域显著性 及其成因研究[J].自然资源学报,2015,30（4）：641-650.［Li Lin,Shen Hongyan,Li Hongmei,etal.Regional diffrencesof climate change in Qaidam Basin and its contributing factors[J]. Journal of Natural Resources,2015,30(4）:641-650.] [23］王可丽,江灏,赵红岩.西风带与季风对中国西北地区的水汽 输送[J].水科学进展,2005,16（3）:432-438.[Wang Keli, Jiang Hao,Zhao Hongyan.Atmospheric water vapor transport from westerly and monsoon over the Northwest China[J].Advances in Water Science,2005,16(3）:432-438.] [24］赵串串,胡慧,董旭,等.柴达木盆地土地荒漠化生态安全评价 [J].林业调查规划,2009,34（4）:22-26.［Zhao Chuanchuan, Hu Hui,Dong Xu.Evaluation on ecological security of desertification in Chaidamu Basin[J].Forest Inventory and Planning,2009,   
34(4) :22 -26.] [25］徐浩杰,杨太保.柴达木盆地植被生长时空变化特征及其对气 候要素的响应[J].自然资源学报,2014,29（3）：398－409. [Xu Haojie,Yang Taibao.Spatial-temporal variations of vegetation activities and its responses to climatic factors in the Qaidam Basin [J]. Journal of Natural Resources,2014,29(3）:398-409.] [26]Knapp A K,Hoover DL,Wilcox KR,et al. Characterizing diferences in precipitation regimes of extreme wet and dry years:implications for climate change experiments[J].Global Change Biology,2015,21(7) :2624 -2633.

# Spatiotemporal trends and periodic features of climate extremes over the Qaidam Basin,China,during 196O -2014

Gegen Batu²，WEI Wei³，ZHANG Xiao’，YANG Xiao-hui1，SHI Zhong-jie1 (1.Institute of Desertification Studies,Chinese Academy of Forestry,Beijing 1Oo091,China; 2.Experimental Center for Desert Forestry,Chinese Academy of Forestry,Dengkou O152O0,Inner Mogolia,China; 3.College of Water and Soil Conservation,Beijing Forestry University,Beijing 1Ooo83,China)

Abstract：In this study,the meteorological data obtained from eight weather stations enabled theanalysis of the spatiotemporal trends and periodic features of the climate extremes over the Qaidam Basin from 196O to 2014.The responses of the precipitation extremes to the South Asian summer monsoon and westerly circulation were also examined.Theresults indicated that the variabilityand trends inthe Qaidam Basin demonstrate asignificanttendency toward warm conditions from l96O to 2O14 and thatthe magnitudeof this trend decreased fromthe west to the east on aregional scale.The changes in extreme precipitation indicated that the frequency,intensity,andamountof heavy precipitation increased over time;consecutive dry days were considered to be significant.The trend magnitudes in the central and western regions were considerably less than those in the eastern region.The periodic features of he diurnaltemperature range,frost days,and cold night frequency were weaker than those of other extreme temperature indices；the ice days and length of the seasons werelonger,whereas the coldestnights were shorter.Allthe extreme precipitation indices exhibited obvious periodic features,and the significant periods of the consecutive dry days and maximum five-day precipitation tended toreduce with time.Meanwhile,the coherence of theoscilation with respect to each extreme precipitation index based on the South Asian summer monsoon as wellas their correlations are particularly strong;however,onlythe simpledaily intensityindexexhibiteda significantand steadyoscilation with westerly circulation.The resultsof this studymay provide theoretical and practical references forachieving sustainable development and ecological protection in the Qaidam Basin.

Key words:climate extremes；spatiotemporal trend； periodic feature；cross wavelet transform；Qaidam Basin