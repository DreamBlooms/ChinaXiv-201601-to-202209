# 基于数值模拟的格尔木地区地下水位致灾性抬升机理研究

汪生斌1,2.3，祁泽学1.2.3，苏世杰1,2.3，吴萍1.2.3（1.青海省环境地质重点实验室，青海 西宁810007；2.青海省环境地质勘查局，青海 西宁 810007;3.青海九零六工程勘察设计院,青海 西宁 810007)

摘要：根据收集的格尔木地区地下水位动态资料、各水库出人库流量资料以及泉集河实测资料等,基于数值模拟方法,分析了温泉水库、南山口一级电站以及洪水等因素对格尔木河地下水位上升程度的影响。结果表明：格尔木市地下水位的上升是南山口一级电站、洪水以及温泉水库调节共同作用的结果。南山口一级电站的蓄水使得市区地下水位上升 $0 . 4 4 \mathrm { m }$ ;洪水使得市区地下水位 $4 . 3 2 \mathrm { m }$ ;温泉水库的调节作用，使地下水位下降 $0 . 2 7 { \mathrm { ~ m ~ } }$ ;地下水的大规模开采有助于抑制地下水位的上升。

关键词：地下水；水位上升；数值模拟；洪水；格尔木地区

格尔木是青海的重要城市之一，地处柴达木盆地。全国最大的干涸内陆盐湖一一依托察尔汗盐湖位于其中，是目前全国最大的钾肥工业生产基地。格尔木地区气候干旱，但受格尔木河等源自昆仑山河流的补给作用，区域内地下水资源较为丰富。地下水位周期性上升现象持续出现，1977年以来，格尔木河上流陆续修建了温泉水库、大干沟水库电站、小干沟水库电站、乃吉里水库电站、南山口一级水库电站等水利设施[1]。随着水利工程的不断建设完善以及大洪水的发生，近20a来格尔木地区地下水位处于历史较高水平。2010年，格尔木市出现了地下水位上升造成的严重地质灾害，大部分的农田无法耕种，沼泽湿地面积不断扩大，地卜水大量泄出地表，渍水泛滥成灾，致使建筑物损失和倒塌，工厂、学校、企业单位、居民点、商场等面临搬迁，直接损失达 $6 . 0 \times 1 0 ^ { 7 }$ 元左右，间接损失难以估计[2]①

长期的地下水位抬升不仅造成城市水文环境的变化，还会产生其他潜在的危害。如造成土壤的盐渍化，地下水对岩土及建筑物的腐蚀增强，细粉砂液化出现管涌等现象，出现地下洞室基础上浮、建筑物失稳等现象[3]。因此，查明地下水位上升的原因，对格尔木地区的地质灾害预防具有至关重要的作用。已有的研究表明：格尔木地区的地下水位抬升可能是天然洪水与水利工程修建共同作用的结果[21①。然而,这些研究只提供了地下水位变化与某些关键因素的定性关系，未建立机理模型对地下水位致灾性抬升过程进行定量分析。

本文的研究目标，是建立格尔木地区的地下水非稳定流场数值模型，考虑水利工程的作用设置不同的模拟情景，评价2009—2010年地下水位致灾性抬升的主要成因，用于预测格尔木地下水位的变化趋势，并用2011—2018年地下水位的相关数据进行了验证，以便为格尔木市预防地下水位抬升导致的灾害提供决策依据。

# 1研究区概况

格尔木地区位于柴达木盆地南缘(图1)，深居内陆、地处高原，冬季寒冷，夏季凉爽，昼夜温差大，干燥少雨，风速强劲，沙尘暴多等高原气候特征，属典型的高原内陆盆地干旱气候。主要河流为：格尔木东河、格尔木西河、红旗河、金水河、巴水河、清水河。

![](images/9cb1288d21529dd1ce91078d2947406a5a863329490493249c3a530dadecffe1.jpg)  
图1研究区位置示意图  
Fig.1 Study areas location map

格尔木地区山前冲洪积平原地带，沉积了巨厚的第四系松散沉积物，为地下水赋存提供了良好的空间。中、上更新统为冰碛、冰水、冲洪积地层，岩性主要为砂卵砾石、泥质砂砾石，岩层颗粒普遍较粗，松散，相应的孔隙度、给水度也大，在接受地表水的垂直渗漏补给后，成为地下水分布和赋存的主要空间。地下水类型主要为扇区的第四系松散岩类孔隙潜水和溢出带前缘的少量承压水。

# 2 数据来源

数学模型涉及的数据主要有：（1）青海省格尔木市水文站提供的1959—2017年的断面流量观测数据；（2）格尔木市水库管理处提供的1980—2017年乃吉里水库等出库入库流量资料；(3）1992—1997年柴达木综合地质勘查局多次实测的格尔木市渠系入渗量；(4）格尔木市水利部门发布的2008—2017年渠系灌溉量；（5）2008—2017年格尔木市主要泉集河的实测资料；（6）1990年以来，格尔木市地下水位长观孔的实测数据。

# 3原理与方法

# 3.1地下水流数值模拟方法

选用瑞士联邦苏黎世理工大学开发的Process-ing ModflowPro集成软件进行区域地下水非稳定流的数值模拟[4]②。模拟范围是格尔木河流域平原区，包括地下水流场模型和河流-泉集河模型[4-51②③。以高斯投影地图为底图，用正方形网格对建模区进行剖分，坐标系与公里网平行，剖分为 $1 \ \mathrm { k m } { \times } 1 \ \mathrm { k m }$ 正方形网格，与地图公里网一致，南北向剖分101格，东西向62格，有效面积 $5 1 9 7 { \mathrm { k m } } ^ { 2 }$ 。分别用平均水文过程和典型年组合水文过程模拟4种方案下的地下水变化趋势，评价2009—2010年格尔木市地下水位致灾性抬升的主要成因。模型的应力期(stress peri-od)时间长度为月，计算的时间步长为天。

# 3.2地下水位抬升的模拟情景方案

为分析2009—2010年地下水位上升机理，弄清各因素对地下水环境影响程度，设定5种情景开展模拟分析。各情景方案如下：

方案一：该方案为参照背景，情景中无温泉水库调节、南山口一级电站未蓄水并且考虑乃吉里电站渗漏，模拟2008之前地下水状态，作为分析其他各影响因素参照背景。

方案二：专门考虑温泉水库调节对地下水的影响，与方案一相比，将格尔木水文3站径流过程替换为温泉水库调节后的多年(1959—2007年)平均过程。其他模型设置与方案一完全相同。与参照背景模拟结果相比较，可分离温泉水库调节对地下水环境影响。

方案三：专门考虑南山口一级电站水库渗漏对地下水影响，在方案二基础上，增加南山口一级电站渗漏，其他与方案二设置相同。该方案与参照背景方案比较，可分离温泉水库调节、一级电站渗漏共同作用对地下水的影响。与方案二模拟结果比较，可分离一级电站渗漏对地下水环境的影响。

方案四：考虑2008—2012年连丰、特大洪水影响，在方案三基础上，即在温泉水库调节、乃吉里水库与南山口电站水库渗漏基础上，接续模拟2008—2012年河流连丰、特丰环境地下水过程。格尔木水文3站径流过程取2008—2012年3站流量，各水源群开采量取2008—2012年实际开采量，其他与方案三相同。该方案与方案三结果比较，可分离连丰、特大洪水对地下水环境的影响。

方案五：将2011—2018年实际地表水、水库实际调水、地下水开采量以及规划水源情况等带入模型，进一步验证原有模型并且模拟洪水退却时水位的变化情况。

# 4各模拟方案结果对比分析

# 4.1方案一模拟结果

该方案模拟结果作为其他方案参照背景，以便分离各种因素对环境的影响。模拟水均衡分析结果见表1，浅层地下水模拟流场见图2，潜水地下水位埋深见图3。

在参照条件下，格尔木河3站入境量 $7 . 8 9 \times 1 0 ^ { 8 }$ $\mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } ( 2 1 6 . 2 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 } )$ ,其中，河水渗漏补给 $5 . 4 9 \times$ $1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 1 5 0 . 3 4 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ ,灌溉引水 $1 . 7 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ：$\mathrm { a ^ { - 1 } } ( 4 8 . 1 { \times } 1 0 ^ { 4 } \mathrm { m ^ { 3 } } { \cdot } \mathrm { d ^ { - 1 } } )$ ,两者消耗占入境流量的 $9 2 \%$ ,剩余 $0 . 6 3 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } ( 1 7 . 7 6 \times 1 0 ^ { 4 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 } )$ ,加上格尔木西河溢出量 $1 . 0 2 { \times } 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 2 7 . 9 5 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ ,累计有$1 . 6 5 { \times } 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 4 5 . 1 5 { \times } 1 0 ^ { 4 } \mathrm { ~ m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ 经格尔木西河流向东达布逊湖，其中部分消耗于沿途蒸发，余者入东达布逊湖。

在格尔木河天然水文条件下，平原区多年平均地下水总补给量为 $6 . 3 8 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 1 7 4 . 8 8 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ ，其中水文3站至乃吉里水库段渗漏补给 $0 . 7 3 \times 1 0 ^ { 8 }$ $\mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 2 0 . 0 3 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ ，占总量的 $1 1 . 5 \%$ ,乃吉里水库至市区河段渗漏 $4 . 7 6 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ ，占 $7 4 . 6 \%$ ,两者之和为河水向地下总补给量 $5 . 4 9 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 1 5 0 . 3 4 \times$ $1 0 ^ { 4 } ~ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ ，占 $8 6 . 1 \%$ ,即地下水补给量绝大部分由河水转化形成，其他补给 $0 . 8 9 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ ，仅占$1 3 . 9 \%$ 。

参照背景设置为拟稳定条件，泉水和蒸发具有与补给量相对应的排泄特征，总排泄与总补给量相等，亦为 $6 . 3 8 { \times } 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } \big ( 1 7 4 . 8 8 { \times } 1 0 ^ { 4 } \mathrm { ~ m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } \big )$ ,其中泉(集河)水排泄 $2 . 3 3 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } ( 6 3 . 7 8 \times 1 0 ^ { 4 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 } )$ ，占$3 6 . 5 \%$ ,蒸发 $3 . 2 4 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } ( 8 8 . 7 4 \times 1 0 ^ { 4 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 } )$ ，占$5 0 . 7 \%$ ,即地下水排泄绝大部分消耗于泉水溢出和蒸发,地下水开采量 $0 . 3 7 { \times } 1 0 ^ { 8 } \mathrm { { m } ^ { 3 } { \cdot } a ^ { - 1 } ( 1 0 . 2 5 { \times } 1 0 ^ { 4 } \mathrm { { m } ^ { 3 } { \cdot } d ^ { - 1 } ) } }$ ，仅占 $5 . 8 \%$ ,向北部荒漠(沙漠、盐漠)地下径流 $0 . 4 4 \times$ $1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 1 2 . 1 1 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ (大部分耗散于北部荒漠区浅埋带蒸发),仅占 $6 . 9 3 \%$ ○

# 4.2方案二模拟结果

本方案分析结果与背景方案相比较，分离出温泉水库调节对地下水的影响。

与参照背景相比较，经温泉水库调节使得格尔木河流量在枯期相对增大，汛期相对减少，改变了年内径流过程,使得地下水入渗量在年内朝着均一

# 表1各方案均衡要素

Tab.1 Results ofwater balance for different scenarios   

<html><body><table><tr><td></td><td>地下水均衡要素</td><td>方案一</td><td>方案二</td><td>方案三</td><td>方案四</td><td>方案五</td></tr><tr><td rowspan="7">地下水补给</td><td>格尔木河沿途渗漏补给</td><td>130.51</td><td>128.75</td><td>111.13</td><td>169.49</td><td>133.09</td></tr><tr><td>乃吉里电站水库渗漏</td><td>20.03</td><td>20.03</td><td>20.036</td><td>20.03</td><td>20.29</td></tr><tr><td>南山口一级电站水库渗漏</td><td>0</td><td>0</td><td>26.96</td><td>29.96</td><td>21.00</td></tr><tr><td>扇区沟谷渗漏补给</td><td>9.46</td><td>9.46</td><td>9.46</td><td>9.46</td><td>10.77</td></tr><tr><td>渠系灌溉渗漏补给</td><td>14.78</td><td>14.78</td><td>14.78</td><td>14.78</td><td>16.79</td></tr><tr><td>昆仑山地下径流补给</td><td>0.104</td><td>0.10</td><td>0.10</td><td>0.10</td><td>0</td></tr><tr><td>补给项合计</td><td>174.88</td><td>173.12</td><td>182.46</td><td>243.82</td><td>202.08</td></tr><tr><td>地下水排泄</td><td>开采地下水</td><td>10.25</td><td>10.25</td><td>10.25</td><td>14.3</td><td>100</td></tr><tr><td></td><td>格尔木河与泉集河溢出</td><td>63.78</td><td>63.54</td><td>65.59</td><td>77.55</td><td>59.86</td></tr><tr><td>浅埋带与沼泽湿地蒸发</td><td></td><td>88.73</td><td>87.22</td><td>94.49</td><td>113.97</td><td>40.27</td></tr><tr><td>向北部荒漠区径流</td><td>12.12</td><td>12.12</td><td></td><td>12.14</td><td>12.17</td><td>1.97</td></tr><tr><td>排泄项合计</td><td>174.88</td><td>173.12</td><td></td><td>182.46</td><td>217.99</td><td>202.08</td></tr><tr><td colspan="2">地下水补给-排泄均衡差</td><td>0</td><td>0</td><td>0</td><td>25.83</td><td>0</td></tr><tr><td rowspan="5">地表水分析</td><td>格尔木河(三站)入境量</td><td>216.23</td><td>216.23</td><td>216.23</td><td>382.08</td><td>223.7</td></tr><tr><td>灌溉引水</td><td>48.49</td><td>48.49</td><td>48.49</td><td>48.49</td><td>48.49</td></tr><tr><td>格尔木河干流沿河渗漏+库区渗</td><td>150.53</td><td>148.77</td><td>158.11</td><td>219.48</td><td>174.38</td></tr><tr><td>格西河及汇入支流溢出</td><td>63.78</td><td>63.54</td><td>65.59</td><td>77.55</td><td>76.32</td></tr><tr><td>向北部荒漠(盐漠)径流</td><td>80.98</td><td>82.49</td><td>75.21</td><td>191.67</td><td>59.9</td></tr></table></body></html>

![](images/dd49b225cbfe4fd2b66c67c1c60e151d778b268db2b28997ed46b7572536af41.jpg)  
图2格尔木河位置示意图及方案一模拟的潜水等水位线

Fig.2Schematic diagram of the Golmud River and modeling results of phreatic water table for the scenario-1化的方向发展，但未改变补给总量。水库调节后，河流总渗漏量变化不多，略微减少，泉水和地下水蒸发亦略有下降(表1)。尽管总渗漏量变化不多，由于枯期流量增大,流量随季节变化更加平稳，沿河地带地下水位有一定变化，市区地下水位平均下降 $0 . 2 7 { \mathrm { ~ m ~ } }$ ,年内水位变幅略减小，由原 $2 . 0 7 \mathrm { ~ m ~ }$ 降为$1 . 7 5 \mathrm { m }$ ,由此可见，温泉水库的调节作用使得地下水水位不升反降，故而温泉水库调节不是诱发市区水位上升因素。

![](images/c718ae4e117fe57f4e8f144339186f738297a0b369fcfbe198e95cdfd0ade478.jpg)  
图3溢出带附近潜水埋深(方案一)

# 4.3方案三模拟结果

本方案计算结果与背景方案、水库调节方案比较，可分离出一级电站渗漏对地下水环境影响

本方案水均衡分析列于表1。一级电站水库渗漏影响地下水位变幅等值线见图4。

据模拟分析，2008年南山口一级电站蓄水后，电站水库大量渗漏，河流总渗漏量增加，与方案二相比，渗漏量与渗漏位置都发生了明显改变。格尔木河上段增加电站渗漏 $2 6 . 9 6 \times 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } ( 3 . 1 2 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 } )$

![](images/f6555a3693ee6df801552e2ec033ba3d91ad910e4544de1513c75ec79affdce3.jpg)  
Fig.3Depth to water table in the near overflow zone (scenario-1)   
图4南山口一级电站诱发的地下水变幅等值线 Fig.4Increment of groundwater level induced by the first Nanshankou power station

导致下游河水流量有所降低，使格尔木河下段渗漏减少 $1 7 . 6 2 \times 1 0 ^ { 4 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 }$ ,抵削后河流渗漏总量增加$9 . 3 4 \times 1 0 ^ { 4 } ~ \mathrm { { m } } ^ { 3 } { \cdot } \mathrm { { d } } ^ { - 1 }$ ，诱发地下水流场、市区地下水位、泉水流量等地下水环境发生变化，

在格尔木河洪积扇调节作用下，一级电站渗漏对环境影响具有滞后性，形成稳定影响需滞后10a时间(图5、图6)。以市区水位变化为例，一级电站蓄水初期，因河流下段渗漏量减少，市区水位不仅不升，反而下降，3a后恢复到蓄水前地下水位，经缓慢调整，5a后上升幅度达到稳定影响值的 $6 3 \%$ ,10a后水位影响达到稳定。泉集河滞后溢出特征与水位过程相似。电站水库2008年8月开始蓄水，按3a滞后期估算，至2011年(3a)，水库渗漏影响才刚刚显现。

![](images/bb88d784399724b6254a104cead107d8511a86484c5dc9729b32a4bee91e48b5.jpg)

![](images/82d49e256c7da4cdea2f6ae171c94fc9e73a8f29d09a9871eadc185a8b495c74.jpg)  
图5市区地下水位对南山口一级电站的滞后响应过程 Fig.5The delayed response of groundwater level in the urban area to the first Nanshankou power station   
图6南山口一级电站水库渗漏，泉集河溢出量滞后调整过程  
Fig.6Nanshankou first-level power station reservoir leakage, Quanji river overflow lag adjustment process curve

电站水库渗漏对区域地下水流场影响：水库渗漏影响至稳定后，与方案二相比，电站水库附近形成水位上升中心，上升幅度约 $2 0 ~ \mathrm { m }$ ，上升范围波及整个扇区，北部延伸至泉水溢出带(图5)。影响稳定后，泉集河排泄流量增大，增量 $2 . 0 5 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ；与蓄水发电前相比，影响至稳定后，市区水位升高$0 . 4 4 \mathrm { m }$ （图4）。

南山口一级电站水库蓄水后，对水环境影响具有明显滞后性,滞后期 $3 \mathrm { ~ a ~ }$ ，达稳定需 $1 0 \mathrm { a }$ ；电站水库渗漏 $2 6 . 9 6 \times 1 0 ^ { 4 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 }$ ，使格尔木河下段渗漏减少$1 7 . 6 2 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ,两者抵削后格尔木河渗漏量净增$9 . 3 4 \times 1 0 ^ { 4 } ~ \mathrm { { m } } ^ { 3 } \cdot \mathrm { { d } } ^ { - 1 }$ ;泉集河溢出增量 $2 . 0 6 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ 、市区地下水位比蓄水发电前平均升高 $0 . 4 4 \mathrm { m }$ ,对地下水环境有一定影响。

# 4.4方案四模拟结果

本方案以2008年流场作为初始条件，格尔木河流量过程修改为2008—2012年实际连丰水文过程，一级电站水库2008年8月蓄水，各水源群取2008—2012年实际开采量。

2008年格尔木河径流量 $9 . 0 5 \times 1 0 ^ { 8 } ~ \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a } ^ { - 1 }$ L $\left( 2 4 7 . 9 5 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } \right)$ ，属偏丰年( $P { = } 2 5 \%$ . $P$ 指河水流量）,2009—2012年，格尔木河径流量为 $1 0 . 9 5 \times 1 0 ^ { 8 }$ /$1 8 . 9 5 { \times } 1 0 ^ { 8 } , 1 2 . 4 5 { \times } 1 0 ^ { 8 } , 1 3 . 4 3 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 }$ ，连续 $4 \mathrm { a }$ 都超过二十年一遇的丰水年，其中，2010年为千年一遇特大丰水年。2009—2012年水均衡分析、与各方案对比结果见表1。

对比不同方案泉集河溢出增量：2009—2012年，在考虑滞后因素情况下，一级电站蓄水（方案三)泉集河溢出水量，比蓄水前(方案二)仅增加 $0 . 7 \times$ $1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ，而特丰、连丰年泉集河溢出水量比方案二增加 $1 3 . 3 2 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ,比方案三增加 $1 2 . 6 2 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 }$ ：$\mathbf { d } ^ { - 1 }$ ,即特丰、连丰年泉集河增量超过一级电站蓄水影响6倍以上。各主要因素对地下水位抬升至灾的影响程度：在考虑滞后因素情况下，至2012年，一级电站蓄水引起市区水位升幅 $0 . 4 4 \mathrm { ~ m ~ }$ ，而洪水引起水位升幅 $4 . 3 2 \mathrm { m }$ ，即洪水发生年对市区水位升幅的影响超过一级电站渗漏8倍以上。

通过对比泉集河溢出量、市区水位升幅表明，2010—2012年市区水位上升、泉集河流量增加等地下水环境变化，主要是格尔木河特丰、连丰造成的，虽一级电站蓄水有一定的支持作用，与格尔木河特丰、连丰相比很弱。

为考察2012年以后地下水演化趋势，本方案预测时间延长5a,2012年后河水流量，设定为多年平均值。采用数学模型对地下水位阈值进行模拟[6],结果表明，假设后续为平水年，3a后，市区地下水位将逐渐回落至阈值水位标高 $2 8 0 5 . 5 \mathrm { ~ m ~ }$ 以下(图7)，预测的整体变化趋势与图4实测数据基本一致。

![](images/9f546daa02320bf3136f22213f6e4c0945dd64f4010b86acd9f6d9bd21df11fa.jpg)  
图7方案四模拟的市区地下水位长期变化 Fig.7Modeling results of the long-term groundwater level variation in the urban

# 4.5方案五模拟结果

本方案在方案四的基础上将时间序列延长至2017年，并将水源开采量调整为已批复的格尔木河冲洪积扇地下水开采量 $1 0 0 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ○

该方案下开采地下水 $1 0 0 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ,地下水环境有明显变化，水位埋深增大，泉水、蒸发减少，向下游盐湖区水流减少。开采水量 $9 5 \%$ 来自夺取泉水和蒸发，泉水由 $4 . 4 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 } ( 1 2 0 . 6 { \times } 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ 减少至 $2 . 1 9 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } ( 5 9 . 9 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 } )$ ;蒸发由 $2 . 2 3 \times$ $1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } ( 6 1 . 2 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { d } ^ { - 1 } )$ 减少至 $1 . 4 7 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ $( 4 0 . 3 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 } )$ 。泉水流量和蒸发量减少程度在可接受范围。开采后格尔木西河和泉集河减少人湖水量 $1 . 8 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 }$ 。对盐湖矿区采卤等用水有一定影响，建议通过那棱格勒河调水工程(已竣工)缓解。

综上所述，格尔木河特丰、连丰年洪水，是引起市区及其北部地下水位上升的决定因素，南山口一级电站水库渗漏起次要作用。温泉水库调节对格尔木市区的地下水位抬升没有影响。

# 5结论

针对格尔木市地下水位上升至灾的原因，本文从地下水数学模型的角度，通过对可能的因素进行了分析，得出以下结论：

（1）格尔木市地下水位的上升是南山口一级电站、2010年大洪水以及温泉水库调节共同作用的结果。南山口一级电站蓄水使得泉集河流量增大 $0 . 7 \times$ $1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ，市区地下水位上升 $0 . 4 4 \mathrm { m }$ ；连续特丰年产生的洪水使得泉集河流量增大 $1 3 . 3 2 \times 1 0 ^ { 4 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ，市区地下水位 $4 . 3 2 \mathrm { m }$ 温泉水库起调节作用，使地下水位向稳定方向发展，该水库修建后市区地下水位下降 $0 . 2 7 { \mathrm { ~ m } }$ 地下水开采量达到规划的 $1 0 0 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ 时，泉集河泄出量减少了 $6 0 . 7 { \times } 1 0 ^ { 4 } \ \mathrm { m } ^ { 3 } { \cdot } \mathrm { d } ^ { - 1 }$ ,有助于抑制地下水位的上升。

(2）格尔木地区地下水位上升机理：由于2008年以来格尔木河连续丰水年，特别是2010年发生的大洪水和水库渗漏作用，改变了格尔木河在冲洪积扇上的流态，增强了河流主要是下河段河水渗漏强度，增大了地下水补给的增加量，因而也增大了地下水储存量的增加量，有限空间内储存量的增加必然会导致地区地下水位剧烈上升。

(3）利用数学模型预测了5种不同的方案，认为本次地下水位上升的主要原因是2008年以来格尔木河连续丰水年，特别是2010年发生的大洪水造成的，南山口一级水库渗漏所起作用比前者弱很多，大规模开采地下水有助于抑制地下水位的上升，而温泉水库对地下水位上升基本无影响。

（4）数学模型预测结果表明：按2012年后按照平水年设定输人条件，3a后地下水位将逐渐回落至临界水位以下，可缓解水位上升灾情。

# 参考文献(References):

[1]宋寿鹏.格尔木地区水资源开发的环境效应分析[D].西安：西 北大学,2Oo6.[Song Shoutao.Analysis of Environmental Effects of Water Resources Development in Golmud Region[D].Xi'an: Northwest University,2006.]   
[2] 汪生斌.格尔木市地下水位上升的初步原因及防治对策[J].西 部探矿工程,2012,24(8):179-180,187.[Wang Shengbin. The primary reasons and countermeasures for the rise of groundwater level in Golmud City[J].Western Prospecting Project, 2O12,24(8): 179-180,187.]   
[3]张衎.岩土工程勘察设计和施工过程中的水文地质问题分析 [J].工程建设与设计,2018(20): 87-88,125.[Zhang Kan.Analysis of hydrogeological problems in geotechnical engineering survey and design and construction[J]. Engineering Construction and Design,2018(20): 87-88,125.]   
[4]寇文杰.格尔木河流域地下水数值模拟[J].水文地质工程地质, 2013,40(1):34-4O.[Kou Wenjie.Numerical simulation of groundwater in Golmud River Basin[J].Hydrogeology& Engineering Geology,2013,40(1):34-40.]

[5]祁泽学,汪生斌,王万平,等.格尔木河冲洪积平原地下水开采 潜力分析[J].人民黄河,2018,40(6):66-71,76.[Qi Zexue, Wang Shengbin,WangWanping,et al.Analysis on the groundwater exploitation potential of Gulmohe alluvial plain[J]. Yellow River,2018,40(6): 66-71,76.]

[6]郭中小,魏永富,廖梓龙,等.锡林河流域地下水位管理阈值研究[J].干旱区研究,2017,34(3):479-486.[Guo Zhongxiao,WeiYongfu,Liao Zilong,et al.Threshold values of groundwater levelmanagement in the Xilin River Basin[J]. Arid Zone Reaearch,2017,34(3): 479-486.]

# Study on mechanisms of geological hazards caused by groundwater level rising in the Golmud area based on numerical simulation

WANG Sheng-bin123，QI Ze-xuel23，SU Shi-jie123，WU Ping123   
(1.Key Lab of Geo-environment Qinghai province,Xi'ning 810o07,Qinghai,China;2.EnvironmentaL   
Geological Prospecting Bureau of Qinghai Province,Xi'ning 810oo7,Qinghai,China;3. Qinghai 906 Engineering Survey and Design lnstitute,Xi'ning 81ooO7,Qinghai,China)

Abstract:From 2OO9 to 2010,the groundwaterlevelin Golmud continued torise significantly,theareaof marshes and wetlands continued to expand,and a large amount of groundwater leakedoutof thesurface,resulting in waterloggingand flooding.As aresult,buildings were damaged andcolapsed,farmland was flooded,shopping malls were flooded,and some bungalows caused cracks orcolapses in the wals.Residential buildings were greatly threatened.All of these caused great economic losss.In this paper,based on the collected long series of groundwater level dynamic data,the inflow and outflow data of various reservoirs and the measured data of the Quanji River combined with a mathematical model were used to analyze the causes of the riseof groundwater level. It was found that the direct cause of the groundwater level rise that led to disaster was flooding.

Keywords:groundwater; level rise; numerical simulation; flood; Golmud area