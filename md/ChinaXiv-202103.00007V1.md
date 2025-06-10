# 极点对称模态分解下陕西气候变化特征及影响因素

申雨晨，李双双，延军平，武亚群，汪成博(陕西师范大学地理科学与旅游学院，陕西 西安710119)

摘要：全球变暖背景下，受人类活动和气候系统波动共同影响，气候要素响应具有非线性、非平稳特征，如何识别气候变化多时间尺度信息，是当前研究的热点话题。基于1970—2017年气温和降水逐日数据，辅以滑动平均、趋势分析和极点对称模态分解(ESMD)等方法，对陕西3大地理单元气候时空特征进行分析，进而探讨不同海区厄尔尼诺指数与气温、降水变化的响应关系。结果表明：1970—2017年，陕北气候变化经历“暖干-冷湿-暖湿”的变化过程;关中和陕南气候在20世纪80—90年代末呈现暖干化，随后增温停滞，降水增多，近期再次呈现暖干化；利用ESMD对陕西气温和降水变化信号进行分解，发现区域气温响应变暖停滞，是受年代波动影响，周期为9.2\~11.5a左右；从趋势项分析，除陕北气温平稳波动之外，关中和陕南气温增速并未减缓;在影响因素上，不同海区海温异常与陕西气温、降水变化相关性存在差异。其中，气温影响主要在中国东部海区，且与NINOA区、黑潮区海温显著正相关；影响降水变化的关键海区在赤道太平洋，即赤道太平洋中部海温异常偏高时，关中和陕南降水呈现下降，而赤道太平洋东部海温异常偏高，陕北降水减少更为明显。

关键词：极点对称模态分解；气候变化；时空分析；陕西省

# 文章编号：

全球环境变化是当前研究的热点领域，尤其是气候变化引发的极端天气事件、陆地表层自然地域系统动态响应备受学界关注[1-3]。1951—2012年地球表面温度上升速率为 $0 . 1 2 ^ { \circ } \mathrm { C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,中国大陆地表温度上升速率为 $0 . 2 3 ^ { \circ } \mathrm { C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 [ 4 ] }$ 。气候变暖导致中国气温上升，部分温度带明显北移，寒温带范围缩小,冰川萎缩[5]。中国大部分地区出现变干或变湿，且降水呈现极端化，夏季城市内涝频繁发生[6-8]与气温上升相比，中国降水量并未呈现出明显的线性趋势[9]

在研究方法上，对于气温和降水的分析，多数研究基于线性回归分析、距平分析、小波分析、正交分解等方法，对气温或降水变化进行趋势、突变或周期性分析[10-13]。然而气温和降水变化影响因子众多，既有自然因素，还包括人类活动，二者相互叠加，使得气候变化具有非线性、非平稳性变化特征[14]不同周期变化的叠合影响，使得线性拟合区域气候变化趋势存在不足[15]。因此,基于信号检测分析技术，王金良等人提出极点对称模态分解(Extreme-point symmetric mode decomposition,ESMD)方法,是对“希尔伯特-黄变换(Empirical mode decomposi-tion，EMD)"方法的新发展，现已被广泛运用到海洋科学、大气科学、机械信号分析等领域[16-19]

在影响因素上，国内外学者对不同流域、不同地理单元气候时空变化特征和影响因素进行大量研究，重点关注厄尔尼诺-南方涛动(ENSO）、大西洋多年代际震荡和北极涛动等海气环流异常对区域气候的影响[20-23]。值得一提的是,与气候要素相似，海温环流异常多存在年代或年际变化，如ENSO具有典型3\~7a周期变化，太平洋年代涛动具有准10a的年代变化，是驱动区域气候异常的关键因子[24]已有研究中，对气候要素进行简单的线性相关或不去趋势，人类活动作用和气候系统波动信息叠加，势必会影响遥相关分析的结论。

基于此，本文利用ESMD方法，对陕西1970—2017年气温和降水时间序列的周期性、非线性趋势进行分析，并选取17个海温指数，识别影响陕西气候变化的关键海区，以期为区域适应气候变化提供理论基础。

# 1资料与方法

# 1.1 研究区概况

陕西 $\mathrm { 1 0 5 ^ { \circ } 2 9 ^ { \prime } } \mathrm { \sim } 1 1 1 ^ { \circ } 1 5 ^ { \prime } \mathrm { E } , 3 1 ^ { \circ } 4 2 ^ { \prime } \mathrm { \sim } 3 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { N } )$ 位于中国中部地区，是西北地区门户，丝绸之路经济带的重要节点，气候类型多样，地貌单元复杂，从北向南依次包含毛乌素沙地、黄土高原、关中平原、秦岭山地和汉江谷地[25]。其中，秦岭是中国南北分界线，长城沿线则是重要的农牧分界线(图1)。在三大地理单元中，陕南为北亚热带气候，关中为暖温带，陕北为暖温带向温带气候的过渡地区，年降水量从北向南依次为： $4 0 0 { \sim } 6 0 0 ~ \mathrm { m m }$ （陕北）、500\~700$\mathbf { m } \mathbf { m }$ (关中）和 $7 0 0 { \sim } 9 0 0 \mathrm { m m }$ （陕南）[26]

![](images/b4e5938061ae234ec00e27004047893a57f526e76883f846535286698f7c1f34.jpg)  
图1陕西省气象站点空间分布图 Fig.1 Meteorological stations distribution in Shaanxi Province

注：该图基于国家测绘地理信息局标准地图服务网站下载的审图号为GS(2016)1600号的标准地图制作，底图无修改。

# 1.2数据来源

陕西气温和降水数据来源于国家气候中心，为确保数据的完整性和连续性，将研究时间确定在1970—2017年。依据《陕西省基层台站简史》,城固站1957年5月建站，1971年迁至城固县谢家井村南，使得前期资料丢失；因此，其数据时段为1971年1月一2017年12月。吴堡站1959年2月在绥德寇家塬成立，1962年5月因精简机构，吴堡气象站撤销，1970年7月在原址恢复成立吴堡气象站；因此，吴堡气象站数据从1970年7月—2015年12月。与此类似，还有米脂站和子洲站，起止时间分别是1970年3月和1970年5月。在影响因素方面，全球不同海区海气环流指数，来源中国气象局国家气候中心气候变化与预测研究室发布的130相关气候系统指数集。17种海气环流指数，主要类型为：具有3\~7a周期ENSO事件，10a左右周期的北太平洋年代震荡指数，反映年际变化的准两年震荡指数，对应极点对称模态分析的信号，以识别陕西气候异常的遥相关的海区(表1)。

# 1.3研究方法

1.3.1极点对称模态分解法本文运用ESMD方法反映气温和降水的长期变化情况和多尺度震荡变化。ESMD对数据进行自适应处理，不需要预先取定基函数或窗口长度，其分解的模态频率、振幅可变,适用于非线性非平稳信号，解决了EMD总能量投射到固定频率点的不合理，也克服了集合经验模态分解(EEMD)加入白噪音对信号分解产生的干扰,有利于分析数据在时间尺度上的频率变化[19]。1.3.2谐波分析谐波分析，将有气候要素的时间序列，表示成为有限个正弦波的叠加，可对时间序列进行周期分析[27]。本文利用谐波分析，对陕西气候要素ESMD分量进行周期量化，为探讨不同海区海温异常对陕西气候影响提供基础。具体方法如下：对给定的气候要素时间序列,经过分析检验取 $p$ 个主要周期(即谐波)叠加作为估计值，然后利用回归方差表示各谐波方差贡献量，确定时间序列的主周期[28]

$$
Y _ { t } = A _ { 0 } + \sum _ { k = 1 } ^ { p } A _ { k } \sin ( W _ { t } t + \mathcal { Q } _ { k } )
$$

式中： $Y _ { t }$ 为时间序列信号； $A _ { 0 }$ 为0次谐波振幅值； $A _ { k }$ 为$k$ 次谐波振幅; $Q _ { k }$ 为谐波初相位; $W _ { t } { = } 2 { \pi } k T \ ( k { = } 1 , 2 , cdots ,$ $p )$ 为谐波频率; $T$ 为基本周期; $p$ 为谐波次数； $\mathbf { \chi } _ { t }$ 为时

# 干旱区地理

表1不同海区海气环流指数  
Tab.1 Indices of ocean-atmosphere circulation on different sea areas   

<html><body><table><tr><td>序号</td><td>海气环流</td><td>定义</td></tr><tr><td>1</td><td>NINO1+2区</td><td>0~10S、80~90W区域内，海表温度距平的区域平均值</td></tr><tr><td>2</td><td>NINO3区</td><td>5S~5N、90~150W区域内，海表温度距平的区域平均值</td></tr><tr><td>3</td><td>NINO 4区</td><td>5°S~5N、150W~160E区域内，海表温度距平的区域平均值</td></tr><tr><td>4</td><td>NINO 3.4区</td><td>5S~5N、120~170W区域内，海表温度距平的区域平均值</td></tr><tr><td>5</td><td>NINOW区</td><td>0~10N、140~180E区域内，海表温度距平的区域平均值</td></tr><tr><td>6</td><td>NINOC区</td><td>10S~090~180W区域内，海表温度距平的区域平均值</td></tr><tr><td>7</td><td>NINOA区</td><td>25~35N、130~150E区域内，海表温度距平的区域平均值</td></tr><tr><td>8</td><td>NINO B区</td><td>0~10N、50~90E区域内，海表温度距平的区域平均值</td></tr><tr><td>9</td><td>PDO</td><td>北太平洋年代际振荡指数,20oN以北的北太平洋地区,海表温度距平经验正交函数分解(EOF)第1模态 的时间系数</td></tr><tr><td>10</td><td>AMO</td><td>大西洋经向模海温指数,21S~32N、74W~15E区域内,海表温度(左场)和经、纬向10m风场(右场)最大 协方差分析结果中海表温度场(左场)的时间系数</td></tr><tr><td>11</td><td>QBO</td><td>准两年振荡指数，赤道地区30hPa纬向风平均值</td></tr><tr><td>12</td><td>NAT</td><td>大西洋海温三极子指数,0°~60°N、0~80°W区域内,海表温度距平(去除线性趋势)经验正交函数分解 (EOF)第一模态作为投影模态,月海温距平场在去除全球海温增暖影响后对该模态投影系数的标准化序列</td></tr><tr><td>13</td><td>SOI</td><td>南方涛动指数,指标准化塔希提与达尔文站月平均海平面气压之差的序列的标准化值</td></tr><tr><td>14</td><td>NCP</td><td>中部型厄尔尼诺-南方涛动(ENSO)指数</td></tr><tr><td>15</td><td>NEP</td><td>东部型厄尔尼诺-南方涛动(ENSO)指数</td></tr><tr><td>16</td><td>KCSST</td><td>黑潮区海温指数，指35N、140~150E及25°~30N、125°~150E区域内,海表温度距平的区域平均值</td></tr><tr><td>17</td><td>WPWP</td><td>西太平洋暖池强度指数，指30oS~30N、120~180E范围,海表温度超过28.0C的区域内，格点海表温度 与28.0C之差乘以格点面积的累积值.</td></tr></table></body></html>

间序列。

# 2结果与分析

# 2.1陕西气候变化趋势

1970一2017年，陕西气温呈现"南高北低"的格局(图2)，其中，3个地理分区年均温关系如下：陕北$( 9 . 5 ^ { \circ } \mathrm { C } )$ <关中( $1 2 . 4 ^ { \circ } \mathrm { C } \ : )$ <陕南( $\mathrm { 1 3 . 9 ~ \mathrm { ^ { \circ } C } } \mathrm { ) }$ )。同时，全省平均气温呈波动上升趋势，上升速率为 $0 . 2 9 \ ^ { \circ } \mathrm { C }$ ·$( 1 0 \mathrm { a } ) ^ { - 1 }$ ,略高于全国平均陆地升温速率 $0 . 2 3 \ ^ { \circ } \mathrm { C }$ ：$( 1 0 \mathrm { a } ) ^ { - 1 [ 4 ] }$ ;对于各区气温变化趋势而言，关中和陕北气温上升速率均为 $0 . 3 1 ~ { } ^ { \circ } \mathrm { C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,高于陕南地区（204 $\left[ 0 . 2 3 ^ { \circ } \mathrm { C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } \right]$ ,三者上升速率均通过0.01显著水平检验，说明近 $4 8 \mathrm { ~ a ~ }$ 陕西气温上升显著。

在降水变化上，陕西从南向北逐渐由“湿润-半湿润"向"半干旱-干旱"转变，各区年降水量也由南向北逐渐减少，年均降水关系如下：陕北(482.1$\mathbf { m m } ) <$ 关中 $( 5 7 2 . 9 \ \mathrm { m m } ) <$ 全省 $\left( 6 4 1 . 2 \mathrm { ~ m m } \right) <$ 陕南$\mathrm { 8 7 1 . 6 \ m m }$ )。在变化趋势上，由于陕西地处内陆，降水年际波动较大，并未呈现明显线性趋势。其中，陕北降水逐年增加,上升速率为 $1 1 . 3 8 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ，而关中降水呈现下降趋势 $\left[ - 5 . 4 3 \mathrm { \ m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } \right]$ ，陕南$\left[ - 2 . 3 4 \mathrm { \ m m } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 } \right]$ 降水下降速率略低于关中，但是上述降水变化趋势并不显著，均未通过0.05显著水平检验。

1970—2017年陕西气候呈现暖干化，但是变化过程具有阶段性。具体变化过程可分为4个阶段：

1970—1984年，陕西年均温为 $1 1 . 6 ~ \mathrm { ^ { \circ } C }$ ,整体呈下降趋势，下降速率为 $- 0 . 2 5 \mathrm { ~ } \mathrm { } ^ { \circ } \mathrm { C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ;年均降水量为 $6 7 0 . 3 ~ \mathrm { m m }$ ,呈现增加趋势，增加速率为 $1 1 1 . 6 \mathrm { m m }$ $( 1 0 \mathrm { a } ) ^ { - 1 }$ 。其中，陕北、关中和陕南气温变化一致，表现为先平稳波动后下降；降水与气温对应，前期平稳波动后期增加。

1984—1999年，陕西年均温为 $1 1 . 8 ~ \mathrm { ^ { q } C }$ ,且进入快速增长期,上升速率为 $0 . 8 9 ~ \mathrm { ^ { \circ } C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ;降水明显下降，下降速率为 $7 9 . 5 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,气候趋于暖干化，上述变化在3个分区变化具有一致性，而且陕北气温增加尤为明显。

1999—2012年，陕西年均温为 $1 2 . 4 ~ \mathrm { ^ { \circ } C }$ ，气温整体稳定且略有下降，下降速率为 $- 0 . 4 2 \ \mathrm { ^ { \circ } C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ；降水明显增加，陕北和陕南增加速率分别为 $8 5 . 2 \mathrm { m m }$ 0$( 1 0 \mathrm { a } ) ^ { - 1 }$ 和 $1 6 2 . 7 \ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ，远高于关中地区[70.0$\mathrm { m } \mathrm { m } { \cdot } ( 1 0 \mathrm { a } ) ^ { - 1 } \big ]$ ,区域气候呈现冷湿化。

![](images/d2bdf87e92c235de306f24c08a9417772ac9dd89b283ab800fff316a284ab1ac.jpg)  
图21970—2017年陕西气候变化特征  
Fig.2 Characteristics of climatic change in Shaanxi Province during 197O—2017

2012—2017年，陕西年均温为 $1 2 . 7 ~ \mathrm { ^ { \circ } C }$ ，气温增速有所回升，上升速率为 $1 . 3 4 ~ \mathrm { { ^ { \circ } C } \cdot ( 1 0 a ) ^ { - 1 } }$ ;降水稳定波动，但是陕北降水依然维持增加，气候格局呈现“南部暖干，北部暖湿"的空间分异

# 2.2陕西气候变化空间特征

通过前文分析发现，陕西气温波动上升，降水轻微下降，气候呈现暖干化。但是，不同区域之间，气温和降水响应阶段和变化趋势存在差异。若以1970—2017年整个时段为时间窗口，计算气候要素变化趋势，分析陕西气温和降水空间变化特征，势必会掩盖真实的变化结论。例如，陕北地区1976—2017年降水呈现"V"字型变化，以1998年为转折点，前期降水下降，后期降水上升，以整体时段计算趋势变化，降水可能无明显趋势，结果就忽略了近年来陕北降水呈现极端化的事实。

因此，选取陕西气候变化4个具有特殊性的时段，即1984—1999年陕西气温上升最快期，1999—2012年陕北气温下降最快期、1983一1995年关中降水下降最快期，以及1998一2017年陕北降水上升最快期，分析全球变暖背景下，陕西各站点气温和降水空间响应的差异性(图3)。具体规律如下：

1984—1999年陕西气温上升最快期（图3a）。可以看出，除部分站点气温变化相对较慢之外，陕西全区气温均呈快速上升，尤其关中和陕北2个区域，气温上升幅度要高于陕南地区。

1999一2012年陕北气温下降最快期（图3b）。这个时期与全球变暖停滞一致，说明陕西全区气温均呈现出增速减缓或者下降，与全球多数区域规律相似。同时，陕西气温变化具有特殊性，即陕北气温下降速率明显要快于关中和陕南。

1983—1995年关中降水下降最快期（图3c）。与陕西气温相对应，气温快速上升，降水持续减少，区域气候呈现暖干化，此时陕北地区降水下降幅度相对较小，关中和陕南是降水大幅下降的主要区域。

1998—2017年陕北降水上升最快期（图3d）。此时段，陕西全区除部分站点降水呈现不显著下降趋势外，多数区域降水呈现增加趋势，仅是增加幅度存在差异性，其中陕北降水增幅最为显著，陕南次之，关中降水增幅相对较小。

综上所述，1970一2017年陕西气温变化具有明

(a)陕西气温上升最快期(1984—1999年) (b)陕北气温下降相对快期(1999—2012年)4.0 2.0陕北 关中 陕南 陕北 关中 陕南 华山太白3.0 华山 0.02.0 -2.0 nwMw0 10 20 304050607080 0 10 20 304050607080气象站点序号 气象站点序号(c)关中降水下降最快期(1983—1995年) (d)陕北降水上升最快期(1998—2017年)3.0 陕北 二 关中 陕南 4.0 陕北 关中 陕南  
销 W 1 华山 2.0  
趋 0.0 N MMWMwW M A0.0-3.0：0 10 20 30 40 50 60 70 80 0 10 20 304050 60 70 80气象站点序号 气象站点序号Mann-Kendall趋势值曲线 趋势零值线

显阶段性，在20世纪80年代中期一90年代末，区域气温整体快速上升，降水以关中和陕南下降最为明显，气候呈现暖干化;到20世纪初，前期暖干化有所逆转，尤其是陕北地区，气温先下降后上升，降水持续增加，区域气候呈现出“暖干化 $$ 冷湿化 $$ 暖湿化"的交替特征，而关中和陕南气温维持高位停滞，降水轻微增加，气候呈现“暖干化 $$ 暖湿化”的转变。

# 2.3陕西气候多尺度变化特征

气候变化并不单纯受大气或地表等因素影响，气候要素序列蕴含信息，既包括人类活动造成的影响，也有自然因子的冷暖周期，两者叠加或抵消形成时间序列年代波动特征[16]。因此，利用ESMD方法，对陕西气温和降水进行极点对称模态分解分析，所得周期信号结果如下：

# （1）气温变化特征

对陕西气温进行ESMD分析，可将关中和陕南气温分解为3个模态分量和1个趋势分量，陕北气温分解为2个模态分量和1个趋势分量，其顺序依次反映原始气温序列由高频到低频的震荡变化。对各模态分量进行谐波分析，结果如表2所示，获得气温年际和年代变化特征（图 $4 \mathrm { a } \mathrm { \sim } \mathrm { c }$ ）。

年际变化特征(模态1)。陕西3个分区气温年际变化特征周期具有相似性，主要包括3.7a和4.0a,其中4.0a为最主要变化周期。

年代变化特征(模态2一模态3)。陕西气温年代变化特征周期包括6.9a、9.6a、16.0a和 $2 4 . 0 \mathrm { a }$ ，且其均通过 $9 5 \%$ 置信水平，即其均为陕西气温的主要变化周期。

趋势变化特征 $( R )$ 。从趋势项 $R$ 的变化可以看出，关中气温经历了1970一1983年的气温低位平稳波动和1983—2015气温快速上升期，陕南气温呈快速的线性上升，陕北气温呈现出“低位波动一快速上升一高温波动"的阶梯状变化。

在方差贡献率上，陕北、关中和陕南气温第一本征模态函数(Intrinsic mode function,IMF1)方差贡献依次为： $3 4 . 1 \%$ ） $2 6 . 1 \%$ 和 $2 6 . 7 \%$ ,三者大致相当，均小于趋势项贡献率，说明增温趋势对原始序列影响较大。其中关中趋势 $R$ 贡献率最高 $( 4 2 . 1 \% )$ ，陕南趋势贡献最低 $( 3 3 . 5 \%$ )。

值得一提的是，1998—2012年，陕西3个分区气温增温速率的下降或减缓，主要来自于关中、陕南IMF3的年代分量，以及陕北的IMF2和趋势分量。也就是说，区域气温响应全球变暖停滞，主要是年代变化特征，周期为9.2\~11.5a左右；从趋势项分析，除陕北气温平稳波动之外，关中和陕南气温增速并未减缓。

# (2）降水变化特征

对陕西降水进行ESMD分析，可将关中和陕北降水分解为3个模态分量和1个趋势分量，将陕南降水分解为2个模态和1个趋势分量，与气温ESMD分解结果一致，依次反映原始降水序列由高频到低

表2陕西气温和降水各分量的方差贡献率和准周期  
Tab.2Variance contribution and quasi-period of precipitation and temperature IMF in Shaanxi   

<html><body><table><tr><td>分区</td><td>气候因子</td><td>指标</td><td>IMF1</td><td>IMF2</td><td>IMF3</td><td>R</td></tr><tr><td>陕北地区</td><td>气温</td><td>周期</td><td>4.0a</td><td>9.6 a/8.0 a</td><td>1</td><td>1</td></tr><tr><td></td><td></td><td>贡献率</td><td>34.1%</td><td>26.4%</td><td>1</td><td>39.5%</td></tr><tr><td></td><td></td><td>F值</td><td>9.6</td><td>6.2/5.7</td><td>1</td><td>1</td></tr><tr><td></td><td>降水</td><td>周期</td><td>2.5 a/2.2 a</td><td>6.9 a-6.0 a-4.8 a-4.4 a</td><td>12.0 a/9.6 a</td><td>1</td></tr><tr><td></td><td></td><td>贡献率</td><td>40.7%</td><td>20.8%</td><td>11.9%</td><td>26.6%</td></tr><tr><td></td><td></td><td>F值</td><td>10.0/3.6</td><td>4.5/4.6/4.2/4.3</td><td>10.5/14.6</td><td>一</td></tr><tr><td>关中地区</td><td>气温</td><td>周期</td><td>4.0 a</td><td>6.9 a</td><td>24.0 a-16.0 a</td><td>1</td></tr><tr><td></td><td></td><td>贡献率</td><td>26.1%</td><td>18.9%</td><td>12.8%</td><td>42.1%</td></tr><tr><td></td><td></td><td>F值</td><td>9.8</td><td>28.1</td><td>14.1-6.1</td><td>1</td></tr><tr><td></td><td>降水</td><td>周期</td><td>3.7 a</td><td>9.6 a/6.9 a</td><td>24.0 a/16.0 a</td><td>1</td></tr><tr><td></td><td></td><td>贡献率</td><td>49.6%</td><td>24.2%</td><td>14.9%</td><td>11.3%</td></tr><tr><td></td><td></td><td>F值</td><td>3.5</td><td>27.6/6.6</td><td>32.3/12.0</td><td>1</td></tr><tr><td>陕南地区</td><td>气温</td><td>周期</td><td>4.0 a/3.7 a</td><td>6.9 a/9.6 a</td><td>24.0 a/48 a</td><td>1</td></tr><tr><td></td><td></td><td>贡献率</td><td>26.7%</td><td>20.1%</td><td>19.7%</td><td>33.5%</td></tr><tr><td></td><td></td><td>F值</td><td>6.4/3.7</td><td>18.0/7.2</td><td>32.2/6.8</td><td>一</td></tr><tr><td></td><td>降水</td><td>周期</td><td>2.2 a</td><td>12.0 a-9.6 a-6.9 a</td><td>一</td><td>1</td></tr><tr><td></td><td></td><td>贡献率</td><td>44.2%</td><td>29.2%</td><td>一</td><td>26.6%</td></tr><tr><td></td><td></td><td>F值</td><td>4.1</td><td>4.5/23.6/4.4</td><td>二</td><td>二</td></tr></table></body></html>

注： $F$ 值为气候要素ESMD分解量谐波周期显著性检验值。IMF1、IMF2、IMF3、R分别为ESMD信号分界的第1\~3本征模态函数和变化趋势量。

频的震荡变化(图4d\~f)。

年际变化特征(模态1)。降水年际变化特征周期主要为2.2\~2.5a和 $3 . 7 \mathrm { ~ a ~ }$ ,即陕西降水变化具有准2\~3a周期和准4a周期，这与气温变化周期具有一定相似性。

年代变化特征(模态2一模态3)。降水年代变化特征周期包括 $6 . 0 \textrm { a } . 6 . 9 \textrm { a } . 9 . 6$ a和 $1 2 . 0 \mathrm { ~ a ~ }$ ,且其均通过 $9 5 \%$ 置信水平，其中，陕西降水主要变化周期为 $9 . 6 \mathrm { ~ a ~ }$ ，与刘闻等[25]对于陕西年降水量变化周期研究相似。

趋势变化特征 $( R )$ 。从趋势项 $R$ 的变化可以看出，陕西3个分区降水变化过程略有差异。共同表现为：以1998年为转折点，前期降水下降，后期降水持续上升，特别是关中和陕北地区增幅尤为明显，三者差异在于20世纪70年代降水波动特征以及2000年后降水变化趋势

在方差贡献率上，陕西各分区降水趋势 $R$ 贡献率均较低，且以年际波动IMF1贡献最大，说明区域降水以 $2 . 0 { \sim } 4 . 0$ a为周期的年际震荡为主，长时间年代波动IMF3并非主导信息量。这与ENSO周期

2.0\~7.0a相对应，也符合中国东部季风区准2.0a的周期规律。

综上所述，陕西降水量主要集中在夏秋两季，受东亚夏季风影响，而夏季风年际尺度变率，主要为准2.0a和 $3 . 0 { \sim } 7 . 0 \mathrm { ~ a ~ }$ ，其中准4.0a周期，准8.0a周期与庞轶舒等29对东亚夏季环流多齿轮耦合周期分析，发现影响夏季风强度、水汽输送、冷暖空气交汇的驱动力，主要形态突出表现为年际尺度2.0\~6.0a周期类似。

# 2.4海温异常对陕西气候的影响

利用ESMD方法，将气温和降水趋势信息滤除，与17个海温指标进行相关分析，发现陕西不同分区气候响应海区存在明显差异（图5)。具体结果如下：

（1）气温响应关系。NINOA区、黑潮区海温(KCSST)与陕西3个子区气温变化呈现显著正相关，NINOA区相关系数分别为：陕北（0.58）关中（0.49)和陕南(0.53），KCSST相关系数分别为：陕北(0.53）关中(0.35)和陕南(0.41），说明中国东部海区海温异常偏高时，陕西气温往往偏高;而赤道中东太平洋海温异常，如NINO $1 { + } 2$ 区，NINO3.4区，与陕西气温异常关系相对较弱。

![](images/0b3fcae559e4225d8350b6ac3822ef87c46af46b9669ad5ca43c3ff192f238b1.jpg)  
  
图4基于极点对称模态分解(ESMD)的陕西气温和降水周期信息特征分析  
Fig.4 Periodic analysis of temperature and precipitation in Shaanxi Province based on ESMI

(2)降水响应关系。与气温相关海区不同，降水高相关区主要位于赤道中东太平洋，而且不同分区响应区域有所差异。其中，陕北高相关主要为：NINO $1 + 2$ 区 $\left( - 0 . 3 1 \right)$ 、NINO3区(-0.34)和NEP区$( - 0 . 3 8 )$ ，关中高相关主要为：NINO4区 $( - 0 . 3 1 )$ 、NINO3.4区（-0.31），陕南降水相关海区与关中相似。说明当赤道太平洋中部海温异常偏高，发生中部型厄尔尼诺时，关中和陕南降水往往呈现下降趋势，而赤道太平洋东部海温异常偏高，陕北降水减少更为明显;反之，上述海区海温异常偏低，形成拉尼娜事件，发生极端降水风险逐渐增加

# 3结论与讨论

利用1970一2017年逐日气温和降水资料，运用ESMD分解方法，对陕西气候转型特征进行精细化分析，探讨不同时间尺度气温和降水的周期特征，选取17个不同海区厄尔尼诺指数，识别影响陕西气候年际变化的关键海区，得到结论如下：

![](images/d108bb479b21cdb4d368ecab3ef369f80f4fa49700b0b8f4b5ac0ff46332852c.jpg)  
图5不同海区海温指数与陕西气候变化的相关性分析  
Fig.5 Correlation analysis between sea surface temperature anomaly and climate changes in Shaanxi Province

（1）1970—2017年，陕西3个分区气温整体呈现阶段式上升，其中，1998一2012年区域气温增速有所减缓，陕北气温甚至呈现下降趋势；与降水趋势相结合，陕北气候变化经历了“暖干化 $$ 冷湿化$$ 暖湿化"的转变，而关中、陕南气候变化总结为：20世纪80一90年代末暖干化，随后增温停滞，降水增多，近期气温增速，降水减少。

(2）利用ESMD对陕西气温和降水变化信号进行分解，获得多个波动周期，气温变化以趋势项为主导，降水变化以年际波动为主导。其中，区域气温响应全球变暖停滞，主要是年代变化特征，周期为9.2\~11.5a左右;从趋势项分析，除陕北气温平稳波动之外，关中和陕南气温增速并未减缓

(3）陕西气温和降水的影响因素存在空间差异。其中，气温影响因素主要在中国东部海区，与NINOA区和黑潮区海温指数显著正相关；降水影响海区主要分布在赤道太平洋地区，当赤道太平洋中部海温异常偏高，特别是发生中部型厄尔尼诺时，关中、陕南降水往往呈现下降趋势，而赤道太平洋东部海温异常偏高，陕北降水减少更为明显。

前文只讨论了陕西气温和降水的变化周期，对于气温和降水周期性变化的原因并没有深入分析，未来还需结合环流诊断进行研究；不同区域受外界环境影响不同，加之多环流因子存在相互作用，如何结合ESMD信号分解方法，从综合视角分析各因素对陕西气候变化的相对贡献率，是未来陕西气候研究的主要探索方向。

在研究方法上，利用ESMD信号分解方法，对陕西3个自然地理单元气温和降水进行去趋势分析，受到趋势项信息量贡献高低的影响，使得年际或年代波动信息提取存在不确定性。本文结论尚不能充分回答：原始序列与去趋势序列相比，是否在不同海区海温相关分析中存在优劣问题。也就是说，海温序列和气候要素序列，由于ESMD滤除趋势项

# 干旱区地理

信息量差异，可能导致结论存在不确定性。在未来研究中，以挖掘可预警的信号为目的，以原始序列和去趋势序列为基础，定量化海温异常与陕西气候变化的准确率或漏报水平，也是值得探索的方向。

# 参考文献(References)

[1]郑景云,方修琦,吴绍洪.中国自然地理学中的气候变化研究 前沿进展[J].地理科学进展,2018,37(1):16-27.[Zheng Jingyun,Fang Xiuqi,Wu Shaohong.Recent progress of climate change research in physical geography studies from China[J]. Progress in Geography,2018,37(1): 16-27.] [2]秦大河.气候变化科学与人类可持续发展[J].地理科学进展,   
2014,33(7):874-883.[Qin Dahe. Climate change science and sustainable development[J]. Progress in Geography,2014,33(7):   
874-883.] [3]卞娟娟,郝志新,郑景云,等.1951—2010年中国主要气候区划 界线的移动[J].地理研究,2013,32(7):1179-1187.[Bian Juanjuan,Hao Zhixin, Zheng Jingyun,et al. The shift on boundary of climate regionalization in China from 1951 to 2O1O[J]. Geographical Research,2013,32(7): 1179-1187.] [4]IPCC. Climate change 2013: The physical science basis: Working Group Icontribution to the fifth assessment report of the Intergovernmental Panel on Climate Change[M]. Cambridge & New York: Cambridge University Press,2013: 1-8. [5]郑景云,尹云鹤,李炳元.中国气候区划新方案[J].地理学报,   
2010,65(1):3-12.[Zheng Jingyun,Yin Yunhe,Li Bingyuan.A new scheme for climate regionalization in China[J].Acta Geographica Sinica,2010,65(1): 3-12.] [6]Hu YL,Wang S G,Song X P,et al.Precipitation changes in the mid-latitudes of the Chinese mainland during 1960—2014[J]. Journal of Arid Land,2017,9(6): 924-937. [7]那音太,秦福莹,贾根锁,等.近54a蒙古高原降水变化趋势及 区域分异特征[J].干旱区地理,2019,42(6):1253-1261.[Na Yintai,Qin Fuying,Jia Gensuo,et al. Change trend and regional differentiation of precipitation over the Mongolian Plateau in recent 54 years[J]. Arid Land Geography,2019, 42(6): 1253-1261.] [8]高涛,谢立安.50年来中国极端降水趋势与物理成因研究综述 [J].地球科学进展,2014,29(5): 577-589.[Gao Tao,Xie Li'an. Study on progressof the trends and physical causes of extreme precipitation in China during the last 5O years[J].Advances in Earth Science,2014,29(5): 577-589.] [9]苑全治,吴绍洪,戴尔阜,等.1961—2015年中国气候干湿状况 的时空分异[J].中国科学:地球科学,2017,47(11):87-96.[Yuan Quanzhi,Wu Shaohong,Dai Erfu,et al. Spatio-temporal variation of the wet-dry conditions fiom 1961 to 2015 in China[J]. Science China: Earth Sciences,2017,47(11): 87-96.] [10]王冰,刘启权,罗琳,等.1981—2011年川南山区地温和气温的 变化特征[J].干旱区地理,2019,42(6):1322-1329.[Wang Bing,

Liu Qiquan,Luo Lin,et al. Change characteristics of soil surface

temperature and air temperature in the mountainous region of southern Sichuan from 1981 to 201[J].Arid Land Geography, 2019,42(6): 1322-1329.]   
[11] 陈颖,贾孜拉,拜山.新疆冬季气温年际异常的主模态及其成 因分析[J].干旱区地理,2019,42(2): 223-239.[Chen Ying,Jia Zila,Bai Shan.Annual variation of winter temperature and its causes in Xinjiang[J].Arid Land Geography,2019,42(2):223- 239.]   
[12]Ma L,Li H, Liu T,et al. Abrupt temperature change and a warming hiatus from 1951 to 2014 in Inner Mongolia,China[J]. Journal of Arid Land,2019,11(2): 192-207.   
[13]周正朝,胡娜娜,周华.西安市气温和降水变化趋势分析[J].干 旱区研究,2012,29(1): 27-34.[Zhou Zhengchao,Hu Nana, Zhou Hua.Analysison the change trendof temperatureand precipitation in Xi'an during the period of 1961—2009[J].Arid Zone Research,2012, 29(1): 27-34.]   
[14]丁一汇,王会军.近百年中国气候变化科学问题的新认识[J] 科学通报,2016,61(10):1029-1041.[Ding Yihui,Wang Huijun. Newly acquired knowledge on the scientific issues related to climate change over the recent 1OO years in China[J]. Science Bulletin,2016,61(10): 1029-1041.]   
[15]柏玲,刘祖涵,陈忠升,等.开都河源流区径流的非线性变化特 征及其对气候波动的响应[J].资源科学,2017,39(8):1511- 1521.[Bai Ling,Liu Zuhan, Chen Zhongsheng,et al. Runoff nonlinear variation and responses to climate fluctuation in the headwater region of the Kaidu River[J]. Resources Science,2O17,39(8): 1511-1521. ]   
[16] 王金良,李宗军.极点对称模态分解方法:数据分析与科学探 索的新途径[M].北京:高等教育出版社,2015:25-26.[Wang Jinliang,Li Zongjun. Extreme-point symmetric mode decomposition method[M]. Beijing: Higher Education Press,2015: 25-26.]   
[17]赵直,徐晗.极点对称模态分解下中国新疆温度变化趋势的区 域特征[J].地理研究,2014,33(12):2358-2366.[Zhao Zhi, Xu Han.The research of temperature variation trends over Xinjiang in China by extreme-point symmetric mode decomposition method[J]. Geographical Research, 2014,33(12): 2358-2366.]   
[18]Qin Y,Li B, Chen Z,et al. Spatio-temporal variations of nonlinear trends of precipitation over an arid region of northwest China according to the extreme-point symmetric mode decomposition method[J].International Journalof Climatology，2018,38(5):2239- 2249.   
[19] 李双双,延军平,孔锋,等.极点对称模态分解下西安高温天气 的趋势特征[J].地理研究,2018,37(1):209-219.[Li Shuangshuang,Yan Junping,Kong Feng,et al. The nonlinear trends of high temperature weather in Xi'an by extreme-point symmetric mode decompositionmethod[J].Geographical Research,2018,37(1): 209-219.]   
[20] 孙艺杰,刘宪锋,任志远,等.1960—2016年黄土高原多尺度干 旱特征及影响因素[J].地理研究,2019,38(7):1820-1832.[Sun Yijie,Liu Xianfeng,Ren Zhiyuan,etal. Spatiotemporal variations of multi- scale drought and its influencing factors the Loess Plateau from 1960 to 2016[J].Geographical Research,2019,38(7): 1820-1832.]   
[21]Xiao M, Zhang Q,Singh VP.Spatiotemporal variations of extreme precipitation regimes during 1961—2O1O and possible teleconnections with climate indices across China[J]. International Journal of Climatology,2017,37(1): 468-479.   
[22]Stepote H, Jones S E O,Fox H. Correlations between extreme atmospheric hazards and global teleconnections:Implications for multihazard resilience[J].Reviews of Geophysics,2018,56(1): 50-78.   
[23]Frazier AG,Timm OE,Giambellua TW,et al.The influence of ENSO,PDO and PNA on secular rainfall variations in Hawaii[J]. Climate Dynamics,2018,51(5-6): 2127-2140.   
[24]Xiao M, Zhang Q,Singh VP. Influences of ENSO,NAO,IOD and PDO on seasonal precipitation regimes in the Yangtze River Basin, China[J]. International Journal of Climatology,2O15,35(12): 3556-3567.   
[25]刘闻,曹明明,宋进喜,等.陕西年降水量变化特征及周期分析 [J].干旱区地理,2013,36(5):865-874.[Liu Wen,Cao Ming

ming,Song Jinxi,et al. Spatio-temporal distribution and temporal

periodicity of annual precipitation in Shaanxi Province[J]. Arid Land Geography,2013,36(5): 865-874.]   
[26]何艳芬,张亮.陕西省1980—2006年气候变化时空特征研究 [J].干旱区资源与环境,2011,25(11): 59-63.[He Yanfen,Zhang Liang.Temporal and spatial characteristics of climatic change from 198O to 2OO6 in Shaanxi Province[J]. Journal of Arid Land Resources and Environment, 2011,25(11): 59-63.]   
[27] 袁莹莹,殷水清,谢云,等.我国风蚀区风速日变率时空变化特 征[J].干旱区地理,2018,41(3): 480-487.[Yuan Yingying,Yin Shuiqing,Xie Yun,et al. Temporal and spatial characteristics of diurnal variations of wind speed in wind erosion areas over China [J].Arid Land Geography,2018,41(3): 480-487.]   
[28]唐启义.DPS数据处理系统):实验设计，统计分析及数据挖掘 [M].四版.北京:科学出版社,2017:899.[Tang Qiyi.DPS data processing system: Experimental design, statistical analysis and data mining[M]. $4 ^ { \mathrm { t h } }$ ed.Beijing: Science Press,2017: 899.]   
[29]庞轶舒.东亚夏季环流多齿轮耦合特征及其对中国夏季降水 异常的影响分析[J].大气科学,2019,43(4):875-894.[Pang Yishu.Coupling wheels in the East Asian summer monsoon circulations and their impacts on precipitation anomalies in China[J]. Chinese Journal of Atmospheric Sciences,2019,43(4): 875-894.]

# 欢迎投稿与订阅

《干旱区地理》创刊于1978年，由中国科学院新疆生态与地理研究所、中国地理学会主办、科学出版社出版的综合性学术期刊。本刊办刊宗旨是反映干旱区地理学及其分支学科、边缘学科和交叉学科的新理论、新技术和新方法。系中国自然科学核心期刊、全国优秀地理期刊、中国科技论文统计源期刊及中国科学引文数据库核心期刊。目前，在干旱区地学领域具有较高影响力的学术期刊。欢迎国内外地学及相关学科的科研人员、高等院校师生投稿。投稿系统:htp://alg.xjegi.com。

《干旱区地理》在国内外公开发行，国际刊号ISSN1000-6060,国内刊号:CN65-1103/X，大16开，双月刊，每期定价50元，全年300元。

欢迎单位和个人订阅《干旱区地理》。订阅方式包括：

（1）各地邮局订阅：邮发代号58-45。  
（2）科学出版社期刊发行部：联系电话010-64017032/64017539。(3）网上购买：搜索淘宝、微店铺名称：中科期刊 $$ 干旱区地理。编辑部地址：乌鲁木齐市北京南路818号45号楼《干旱区地理》编辑部邮编：830011  
电话：0991-7827350  
E-mail: aridlg@ms.xjb.ac.cn  
网址:http://alg.xjegi.com

# Spatiotemporal climate variation and its influencing factors in Shaanxi Province based on extreme-point symmetric mode decomposition

SHEN Yuchen， LI Shuangshuang， YAN Junping， WU Yaqun， WANG Chengbo (School of Geography and Tourism,Shaanxi Normal University,Xi'an 71Ol19,Shaanxi, China)

Abstract: Against the background of global warming aected by human activities and climate system fluctuations,climate response is non-linear and nonsmoothed.A hot topic is how to identify multiple-time scale information about climatic change.The spatiotemporal characteristics of climate change were analyzed for three geographical sub-regions of Shaanxi Province by sliding average,trend analysis,and extreme-point symmetric mode decomposition (ESMD) methods,using daily temperature and precipitation data between 1970 and 2017 and the discussing the tele-correlation between sea surface temperature (SST) in 17 diferent sea areas and the regional temperature and precipitation changes.The main SST indexes included El Nino-Southern Oscilation,Pacific Decadal Oscillation,Atlantic Multi-decadal Oscilation,Quasi-Biennial Oscilltion (QBO),and Kuroshio Currnt T (KCSST).The results showed that from 1970 to 2017,the mean annual temperature in Shaanxi rose significantly, with step-change points in 1984,1999,and 2012.In detail,climate change innorthern Shaanxi involved warmingdrying,cooling-weting,and warming-weting, whereas in Guanzhong Plain and southern Shaanxi, there was warmingdrying from 1970 to 1999.Since 1999,the regional climate of these two regions exhibited a warming hiatus,and it was not until 2012 that intensified warming and decreasing precipitation have become more obvious.The ESMD of temperature and precipitation signals showed a non-linear upward trend,which implied changes on decadal scales (9.2-11.5 a) in response to the warming hiatus.The temperature increased in Guanzhong Plain and southern Shaanxi,except fora slight decline in northern Shaanxi in 1999—2017. Spatial differences exist in the influencing factors of temperature and precipitation in Shaanxi Province.The SST of eastern China is the dominant influencing factor for annual and decadal temperature variability. Temperatures generally increase in Shaanxi with positive SST anomaly for both NINO A and KCSST. Additionally, positive SST anomalies in the central equatorial Pacific cause decreasing precipitation in both Guanzhong Plain and southern Shaanxi. Less precipitation was expected in northern Shaanxi with increasing positive SST anomalies centered in the eastern equatorial Pacific,commonly known as the East Pacific type of El Nino.The above results could provide insights for the regional response and risk management of extreme precipitation resulting from global climate change. However, it shouldbe noted thatthe connections between the SSTand climate anomalies in Shaanxi Province are not clear. Hence,future work should determine the SST-forced heat and moisture stress anomalies to explain rainfall variations.

Key words: extreme-point symmetric mode decomposition (ESMD)； climate change; spatiotemporal analysis; Shaanxi Province