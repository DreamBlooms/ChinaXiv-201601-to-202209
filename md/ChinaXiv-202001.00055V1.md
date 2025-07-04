# 民勤绿洲青土湖植被优势种地上生物量估算

张华，张玉红，张改改(西北师范大学地理与环境科学学院,甘肃兰州730070)

摘要：青土湖区域属于绿洲一荒漠过渡带，生态系统脆弱，极易发展为荒漠。梭梭、白刺和芦苇为青土湖区域的植被优势种,对其生态系统稳定与健康发展起着关键作用。以青土湖区域梭梭、白刺和芦苇为研究对象，利用空间分辨率为 $0 . 5 \mathrm { ~ m ~ }$ 的高分辨率遥感影像Worldview-2，采用辅以纹理特征的面向对象分类方法,提取梭梭和白刺的冠幅面积以及芦苇的分布面积;根据野外试验数据，建立梭梭和白刺地上生物量与冠幅面积、芦苇地上生物量与分布面积关系模型。利用关系模型、冠幅面积以及分布面积对青土湖区域植被优势种地上生物量进行了估算,实现了植被优势种地上生物量估算由“点”到“面”的转换。结果表明：(1）采取辅以纹理特征的面向对象分类方法取得了较高的分类精度，总体Kappa系数为 $8 7 . 9 \%$ ，总体精度达到 $9 1 . 3 \%$ 。（2）研究区植被优势种地上生物量总量为 $3 . 1 7 \times 1 0 ^ { 3 }$ t,其中梭梭地上生物量为 $0 . 5 4 \times 1 0 ^ { 3 }$ t,白刺地上生物量为 $0 . 9 0 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,芦苇地上生物量为 $1 . 7 3 \times 1 0 ^ { 3 }$ t,地上生物量芦苇 $>$ 白刺 $>$ 梭梭。该研究可以为深入研究青土湖区域生态恢复与碳储量提供参考。

关键词：地上生物量；植被优势种；Worldview-2；青土湖

生物量（biomass）是指生态系统某一时间各种植物成分单位面积有机物质的干重，直接反映生态系统植被生产力的大小，是衡量生态系统功能和结构稳定性的重要指标，对其进行估算是深入研究许多生态问题的基础[1-2]。近年来,国内外学者对生物量估算进行了大量的研究，既有不同生态系统或种群方面生物量估算[3-6],也有不同环境胁迫、人为干扰条件下生物量估算[7-9]。研究方法多样,有地面实测法、模型估算法和遥感估算法等[10-11]。其中，地面实测法精度高，但对生态系统的破坏性大且费时费力，无法扩大到更大区域。模型估算法是基于大量样本生物量数据与易测因子(冠幅、株高等)关系进行生物量估算，但均匀选取样地困难，难以对自然环境差异大的区域生物量进行整体估算。遥感估算法是运用影像光谱信息对生物量进行反演，其效率高,运用范围广[12],但主要集中于森林和草地生物量估算方面，在荒漠植被地上生物量估算方面尚处于探索阶段[1,13]。近年来,有学者[14-15]将遥感数据与模型估算法相结合对植被地上生物量进行估算,为植被生物量估算提供了重要参考。但由于干旱区植被分布稀疏，景观斑块小而破碎，这些研究或受遥感影像分辨率的限制,或受传统分类方法[16]的影响，植被分类精度较低，使生物量估算精度降低。基于此，本研究采用高分辨率遥感影像Worldview-2，利用辅以纹理的面向对象分类方法，使植被提取精度达到"冠幅”尺度，实现了地上生物量高精度估算。

青土湖区域位于民勤绿洲的北部边缘的荒漠一绿洲过渡带，是阻正腾格里沙漠和巴丹吉林沙漠合围的重要地带。由于植被物种单一，生态系统脆弱，青土湖区域土地荒漠化、盐碱化严重[17]。植被恢复是治理土地荒漠化的重要手段，而地上生物量是植被生长状况的重要评价指标。梭梭（Haloxylonam-modendron）、白刺（Nitrariatangutorum）和芦苇（Phragmitesaustralis）为青土湖区域的植被优势种[18-19],梭梭为多年生小乔木或灌木,耐干旱、高温和寒冷的生态环境,具有抗风蚀的能力[20],白刺枝条被沙半掩埋能萌生大量的侧根，可拦截和固定大量流沙形成固定沙丘，是进行防风固沙经常选取的物种[21]。芦苇为多年生草本,盐渍化和荒漠区的芦苇具有强大的根茎和根系系统，具有改善盐碱地的功能[22]。故梭梭、白刺和芦苇地上生物量估算对区域植被的恢复研究具有重要意义。

本研究以青土湖区域植被优势种梭梭、白刺和芦苇为研究对象，利用高分辨率遥感影像World-view-2，采用辅以纹理特征的面向对象分类方法，对植被优势种进行提取得到梭梭和白刺的冠幅面积以及芦苇的分布面积；根据野外试验数据，建立梭梭和白刺冠幅面积与地上生物量、芦苇分布面积与地上生物量的关系模型；利用关系模型以及冠幅面积、分布面积，对青土湖区域植被优势种地上生物量进行估算，首次实现了民勤绿洲地上生物量估算尺度由“点"到"面”的转换，以期为深入研究青土湖地区生态恢复和碳储量提供科学依据。

# 1 研究区概况

研究区为石羊河流域下游民勤绿洲北部边缘的青土湖区域，属于荒漠一绿洲过渡带，包括青土湖水域及其周围地区，总面积约 $3 0 . 3 3 ~ \mathrm { k m } ^ { 2 }$ （图1）。中心地理坐标为 $1 0 3 ^ { \circ } 3 7 ^ { \prime } \mathrm { E } _ { } , 3 9 ^ { \circ } 0 6 ^ { \prime } \mathrm { N }$ ,海拔 $1 \ 2 9 2 \sim 1 \ 3 1 0$ $\mathbf { m }$ ,年平均气温 $7 . 8 ~ \mathrm { { ^ { \circ } C } }$ ,年平均降水量 $8 9 . 8 ~ \mathrm { m m }$ ,7\~9月降水量占全年降水总量的 $73 \%$ ,潜在蒸发量达$2 \ 6 0 0 \ \mathrm { m m }$ 以上，石羊河是该区域唯一的河流。全年盛行西北风，夏秋季盛行东风，属于典型温带大陆性干旱荒漠气候。土壤以湖相沉积物为母质的沙土及壤质沙土为主[23]。植被类型为典型的荒漠植被,以低矮的灌木和草本植被为主。除优势种梭梭、白刺和芦苇外，还分布有伴生种怪柳（Tamarixramosis-sima）盐爪爪（Kalidiumfoliatum）猪毛菜（Salsolacollina)等。

# 2 数据与方法

# 2.1 数据获取

2.1.1 遥感数据与处理遥感数据采用2015年7月19日成像的Worldview-2遥感卫星影像，该卫星由美国于2009 年10月发射升空，包括1个全色波段 $4 5 0 \sim 8 0 0 ~ \mathrm { n m }$ )和4个多光谱波段，多光谱波段为蓝光波段( $4 5 0 \sim 5 1 0 ~ \mathrm { \ n m }$ ）、绿光波段（ $5 1 0 \sim 5 8 0$ nm）、红光波段( $( 6 3 0 \sim 6 9 0 ~ \mathrm { n m }$ ）、近红外波段( $7 7 0 \sim$ $8 9 5 \ \mathrm { n m }$ )，其中全色波段分辨率为 $0 . 5 \mathrm { ~ m ~ }$ ,多光谱波段分辨率为 $1 . 8 \mathrm { ~ m ~ }$ 。影像无云覆盖，质量较好，该时期植被生长旺盛，特征明显。影像的预处理在EN-VI5.1软件中完成。首先对影像进行多光谱与全色波段融合，得到分辨率为 $0 . 5 \mathrm { ~ m ~ }$ 的多光谱影像；其次，根据野外试验选取的道路交叉点、特殊建筑物等具有明显特征的地面控制点(GCP)20个，采用多项式对影像进行几何校正，使误差控制在一个像元内[24];最后对影像进行裁剪，选用 $1 2 0 6 5 \times 1 0 \ 0 5 4$

![](images/d5e7a23ff6a134b089334f1c89007f803c77d7880964f4e6b3effa561e8e02c5.jpg)  
图1研究区位置、Worldview-2影像4、3、2波段假彩色合成及采样点

Fig.1Locationof studyarea,falsecolorcomposite imagesof Worldview-2and the distribution of sampling points

个像元作为研究区。

2.1.2试验数据获取本研究于2017年8月 $1 2 \sim$ 18日进行了野外试验。考虑到研究区生态脆弱，直接收割植被获取其生物量对植被破坏性大且不易恢复，因此本研究通过建立样本生物量与易测因子的模型估算植被优势种地上生物量。参照前人的研究[25-27],本研究选取的梭梭易测因子为株高、冠幅东西长和南北长、枝数、枝高与枝基茎;白刺易测因子为冠幅面积;芦苇的易测因子为株高、株数;将生物量样本带回实验室，在 $8 5 ~ ^ { \circ } \mathrm { C }$ 烘箱中烘干至恒重，用精度为 $0 . 0 1 \mathrm { ~ g ~ }$ 的电子秤称得干重,即生物量。测定易测因子和采集生物量样本数据用于建立地上生物量估算模型，收集野外采样点信息用于分类和提取。

# （1）采样点试验数据

收集199个野外样点信息，包括20个地面控制点和179个典型地物采样点;在谷歌影像上随机选取难以到达区域采样点257个。野外以及谷歌影像选取的436个典型地物采样点中217个作为植被优势种分类训练样本，219个用于分类精度验证(表1)。

（2）植被优势种易测因子与生物量数据获取

梭梭：在梭梭典型分布区，随机选取52株不同长势与大小的梭梭，用卷尺测量每株的株高 $H _ { s s }$ （cm），冠幅东西长 $d _ { 1 } ( \mathrm { c m } )$ 与南北长 $d _ { 2 } \left( \mathrm { c m } \right)$ （测量值为植株东西、南北方向的最大长度），记录每株梭梭的总枝数并测量所有枝的基茎 $D _ { s } \left( \mathrm { c m } \right)$ 和高 $H _ { s }$ （cm）;随机选取其中的50枝作为标准枝并测量高和基茎，收割后用档案袋包装，带回实验室。梭梭冠

# 表1采样点信息

Tab.1Information of sample point   

<html><body><table><tr><td colspan="4">典型地物 训练样本 精度验证 合计</td></tr><tr><td>采样点</td><td>梭梭</td><td>21 21</td><td>179</td></tr><tr><td rowspan="7">谷歌影像采样点</td><td>白刺 26</td><td>26</td><td></td></tr><tr><td>芦苇</td><td>25 26</td><td></td></tr><tr><td>水体</td><td>23 11</td><td></td></tr><tr><td>梭梭</td><td>30</td><td>30 257</td></tr><tr><td>白刺</td><td>41 40</td><td></td></tr><tr><td>芦苇</td><td>25</td><td>55</td></tr><tr><td>水体</td><td>26 10</td><td></td></tr><tr><td>合计</td><td></td><td>217</td><td>219 436</td></tr></table></body></html>

幅面积计算公式如下[28]：

$$
C _ { s s } = \pi \times \Big [ \frac { d _ { 1 } } { 2 } \Big ] \times \Big [ \frac { d _ { 2 } } { 2 } \Big ]
$$

式中： $C _ { s s }$ 为梭梭的冠幅面积； $d _ { 1 }$ 为梭梭冠幅东西长；   
$d _ { 2 }$ 为南北长。

白刺：在白刺典型分布区选取52个白刺沙包，各沙包之间至少间隔 $5 0 \mathrm { ~ m ~ }$ ,在每个白刺沙包中心确定一个大小为 $0 . 5 \mathrm { ~ m ~ } \times 0 . 5 \mathrm { ~ m ~ }$ 的小样方，共52个样方，使用GPS记录样方中心的地理坐标，并使用相机对小样方进行垂直拍照;将小样方内白刺齐地收割，用档案袋包装，带回实验室。将白刺照片导入ArcGIS10.2中，对照片进行目视解译，计算得到其冠幅面积[29]

芦苇：距离青土湖最大水面边缘设置半径为$5 0 0 \mathrm { ~ m ~ } , 1 \mathrm { ~ } 0 0 0 \mathrm { ~ m ~ }$ 的样带，每个样带分别设置25个大小为 $1 \mathrm { ~ m ~ } { \times } 1 \mathrm { ~ m ~ }$ 的样方，共50个样方，记录每个样方内芦苇的株数并测量其株高，使用GPS记录每个样方中心的地理坐标;在每个样带选取5个样方，沿其对角线选取5株具有代表性的芦苇植株，共计50株，测量株高并齐地收割带回实验室。

# 2.2 研究方法

根据野外试验数据，建立植被优势种梭梭、白刺和芦苇地上生物量与易测因子回归模型，结合Worldview-2提取的梭梭和白刺的冠幅面积及芦苇的分布面积,对青土湖区域植被优势种地上生物量进行估算（图2）。

2.2.1辅以纹理特征的面向对象分类方法的植被优势种提取植被空间分布信息的高精度提取是准确估算生物量的基础。面向对象的分类方法可以充分利用高分辨率遥感影像的光谱、纹理信息提高信息的提取精度[30-31]。因此,本研究采用辅以纹理特征的面向对象分类方法[32]对研究区植被优势种进行分类，以提取青土湖区域植被优势种梭梭和白刺的冠幅面积及芦苇的分布面积。经过多次试验后，采用窗口大小为 $3 \times 3$ ,步长为1,移动方向45°对常用纹理特征均值（Mean）、对比度（Contrast）、方差（Variance）、协同性（Homogeneity）、相异性（Dissimi-larity)和熵值(Entropy)分别进行提取。通过对比分析，发现对比度特征生成的纹理影像能更好地区分地物，所以本研究将提取的对比度纹理信息与光谱信息进行融合。融合后的影像地物特征更加明显。

分割尺度的设置直接影响分类的效果[33]。因此本研究根据遥感影像中地物的特征及野外试验数据，经过多次试验，对影像进行了分层设置，采用多尺度分割方法分别对每层影像进行分割，并对相应的对象进行提取。在第一层中，对植被和水体进行了提取，其中形状因子为0.3，紧致度因子为0.5，分割尺度参数选为30。第二层中，将第一层分出的植被进一步细分为梭梭、白刺、芦苇,形状因子设为0.5,紧致度因子为0.5，由于白刺和梭梭在影像上斑块较小，所以分割尺度参数选为15。影像分割后，根据野外实地调查获取的采样点数据选取训练样本，采用最邻近分类法对影像进行植被优势种信息提取，最后对错分、漏分的对象进行手动改正，以提高分类精度。

![](images/b9920755ac6ad52e4df8cd66daa77bfe736f528bf8886cfba28f5400c5a9b626.jpg)  
图2研究方法框架  
Fig.2Research method framework

# 2.2.2植被优势种生物量建模

（1）梭梭地上生物量建模

枝生物量建模：在50枝梭梭样本中，随机选取其中的40枝建立单枝梭梭生物量与基茎和高的关系模型，剩余的10枝用于模型验证，建立模型如下（图3a）：

$$
W _ { s } = 6 . 1 7 3 \times \left( D _ { s } ^ { 2 } H _ { s } \right) ^ { 0 . 6 0 4 7 }
$$

式中： $\boldsymbol { \mathcal { W } } _ { s }$ 为单枝梭梭生物量 $( \mathbf { g } ) : D _ { s }$ 为单枝梭梭基茎 $\mathrm { ( c m ) }$ ; $H _ { s }$ 为单枝梭梭高 $\left( \mathrm { c m } \right)$ 。模型 $R ^ { 2 } = 0 . 7 7$ ，拟合效果较好。 $F = 6 0 . 2 5 > F _ { 0 . 0 0 1 }$ ,表明回归方程在$\alpha = 0 . 0 0 1$ 上显著，实测值与拟合值接近1:1线（图3b)。

株地上生物量建模：将每株梭梭枝的基茎和高带入式(2)得到每株梭梭的地上生物量;利用式(1)计算得到每株梭梭的冠幅面积。在52株梭梭中随机选取41株，建立单株梭梭地上生物量与冠幅面积模型，利用剩余的11株梭梭进行模型验证，建立模型如下（图4a）：

$$
W _ { s s } = 0 . 8 2 7 ~ 6 \times C _ { s s } ^ { \phantom { 0 . 9 1 8 5 } }
$$

式中： $\boldsymbol { W } _ { s s }$ 为单株梭梭地上生物量 $( \mathbf { g } ) ; C _ { s s }$ 为单株梭梭的冠幅面积( $\mathrm { c m } ^ { 2 }$ )。模型 $R ^ { 2 } = 0 . 7 9$ ,拟合效果较好。 $F = 1 2 3 . 9 3 > F _ { 0 . 0 0 1 }$ ,表明回归方程在 $\alpha = 0 . 0 0 1$ 上显著，实测值与拟合值接近1:1线（图4b）。

(2)白刺地上生物量建模

在野外获取的52个白刺样方数据中，随机选取40 个样方数据，建立白刺地上生物量与冠幅面积模型，利用剩余的12个样方数据进行模型验证。建立

![](images/8ddb63a5dd07a8f582c9740b1898d9def0112b0fae208b86f1b6390216fd7e31.jpg)  
Fig.3Fitted model（a）and verification（b）of $\mathrm { D } ^ { 2 } \mathrm { H }$ and aboveground biomass of single Haloxylon ammodendron

![](images/fcdec57a83c4d3bd6d66c86d350777b57006bed2fe5fb730dc6374b17ab91f4c.jpg)  
图3梭梭枝基茎和高与枝生物量关系模型(a)及模型验证(b)  
图4单株梭梭冠幅面积与地上生物量关系模型(a)与模型验证(b)

模型如下(图5a)：

$$
W _ { b } = 5 4 5 . 3 3 \times C _ { b } - 4 7 . 1 0 5
$$

式中： $\textstyle \boldsymbol { W } _ { b }$ 为白刺地上生物量 ${ \bf \Xi } ( \mathrm { \bf \Lambda g } ) : C _ { b }$ 为白刺的冠幅面积 $\left( { \bf m } ^ { 2 } \right)$ 。模型 $R ^ { 2 } = 0 , 7 4$ ,拟合效果较好。 $F =$ $1 0 7 . 5 > F _ { 0 . 0 0 1 }$ ,表明回归方程在 $\alpha = 0 . 0 0 1$ 上显著,

实测值与拟合值接近1:1线（图5b）。

# （3）芦苇地上生物量建模

在收割的50株芦苇样本中，随机选取35株建立株高与株地上生物量模型，剩余的15株进行模型验证。建立模型如下（图6a)：

![](images/6ecabe5174f982ea4fc46c70a30ff9c26a2fb4c1964131d48e110bfdd8d3d466.jpg)  
Fig.4Fitted model（a）and verification（b）of canopyarea and aboveground biomass of Haloxylon ammodendron   
图5白刺冠幅面积与地上生物量关系模型(a)与验证模型(b)

Fig.5Fitted model（a）and verification（b）of canopy area and aboveground biomass of Nitraria tangutorun

![](images/109b32921c8a74272c0f9ad5e244cd4203caa899ef8f1f4350d49f3d6c5a19b4.jpg)  
图6芦苇株高与地上生物量关系模型(a)及其模型验证(b)

Fig.6Fited model（a）and verification（b）of height and aboveground biomass of Phragmites australis

$$
W _ { l } = 0 . 0 0 0 \ 9 \times H _ { l } ^ { \textrm { \tiny 1 . 7 8 9 3 } }
$$

式中： $\textstyle \mathbf { \big | } \mathbf { \big | } _ { \mathit { l } _ { \mathbf { \Pi } } }$ 为单株芦苇生物量 ${ \bf \Xi } ( \mathrm { \bf ~ g } ) ; H _ { l }$ 为芦苇株高$\left( \mathrm { c m } \right)$ 。模型 $R ^ { 2 } = 0 . 8 0$ ,拟合效果较好。 $F = 7 0 . 2 2$ $> F _ { 0 . 0 0 1 }$ ,表明回归方程在 $\alpha = \mathrm { 0 . 0 0 1 }$ 上显著,实测值与拟合值接近1:1线（图6b）。

根据测量获得的每个样方中芦苇株高数据，利用式(5)计算出样方地上总生物量为 $7 ~ 0 3 9 . 5 0 ~ \mathrm { g }$ ,样方单位面积地上生物量为 $5 1 1 . 9 6 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ;建立芦苇分布面积与地上生物量关系模型如下：

$$
W _ { l w } = 5 1 1 . 9 6 \times S _ { l w }
$$

式中： $\boldsymbol { W } _ { l w }$ 为研究区芦苇地上生物量 $\left( \mathbf { g } \right) ; S _ { l w }$ 为研究区芦苇分布面积 $\left( \mathbf { m } ^ { 2 } \right)$ 。

# 3 结果与分析

# 3.1植被优势种提取精度评价

根据野外试验数据，通过建立混淆矩阵（Confu-sion matrix）（表2）对分类结果进行评价[34]。评价指标包括生产者精度、用户精度、Helden系数、Short系数和Kappa系数、总体精度、总体Kappa系数（表3）。

# 表2青土湖植被优势种提取混淆矩阵

Tab.2Confusion matrix of classification of dominant species of vegetation in Qingtu Lake   

<html><body><table><tr><td></td><td>梭梭</td><td>白刺</td><td>芦苇</td><td>水体</td><td>共计</td></tr><tr><td>梭梭</td><td>49</td><td>2</td><td>0</td><td>0</td><td>51</td></tr><tr><td>白刺</td><td>3</td><td>61</td><td>2</td><td>0</td><td>66</td></tr><tr><td>芦苇</td><td>0</td><td>7</td><td>70</td><td>4</td><td>81</td></tr><tr><td>水体</td><td>0</td><td>0</td><td>1</td><td>20</td><td>21</td></tr><tr><td>共计</td><td>52</td><td>70</td><td>73</td><td>24</td><td>219</td></tr></table></body></html>

# 表3青土湖植被优势种提取精度评价

Tab.3 Classification accuracy of dominant species of vegetation in Qingtu Lake   

<html><body><table><tr><td></td><td>梭梭</td><td>白刺</td><td>芦苇</td><td>水体</td></tr><tr><td>生产者精度</td><td>0.942</td><td>0.871</td><td>0.959</td><td>0.833</td></tr><tr><td>用户精度</td><td>0.960</td><td>0.924</td><td>0.864</td><td>0.952</td></tr><tr><td>Helden系数</td><td>0.951</td><td>0.897</td><td>0.909</td><td>0.889</td></tr><tr><td>Short系数</td><td>0.907</td><td>0.813</td><td>0.833</td><td>0.802</td></tr><tr><td>Kappa系数</td><td>0.924</td><td>0.816</td><td>0.948</td><td>0.903</td></tr><tr><td>总体精度</td><td></td><td>0.913</td><td></td><td></td></tr><tr><td>总体Kappa系数</td><td></td><td>0.879</td><td></td><td></td></tr></table></body></html>

经精度验证可得总体Kappa系数为 $8 7 . 9 \%$ ，总体精度达到 $9 1 . 3 \%$ 。采用多尺度分割方法和最邻近分类方法对高分辨率遥感影像进行植被优势种提取得到了较好的结果。其中，芦苇精度最高，其次为梭梭、白刺。

# 3.2植被优势种空间分布

根据Worldview-2遥感影像植被优势种提取结果,梭梭总冠幅面积 $0 . 1 6 ~ \mathrm { k m } ^ { 2 }$ ，占研究区总面积$0 . 5 \%$ ；白刺总冠幅面积 $1 . 7 \ \mathrm { k m } ^ { 2 }$ ，占研究区总面积$5 . 5 2 \%$ ;芦苇分布面积 $3 . 3 8 ~ \mathrm { k m } ^ { 2 }$ ，占研究区总面积的 $1 1 . 1 3 \%$ ;分布面积最大为芦苇,其次是白刺,最小为梭梭。

植被优势种空间分布存在着明显的差异（图7)。梭梭主要分布于青土湖区域东北部荒漠一绿洲过渡带上，呈点状规整分布;白刺分布于青土湖区域芦苇外围的沙丘上，在研究区有着广泛的分布；芦苇主要趋水呈片状分布。

# 3.3植被优势种地上生物量估算

根据Worldview-2提取的梭梭和白刺冠幅面积、芦苇分布面积(图7），结合建立的梭梭、白刺地上生物量与冠幅面积模型(式3、式4）、芦苇地上生物量与分布面积模型（式6），计算得到研究区植被优势种总地上生物量为 $3 . 1 7 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,其中梭梭总地上生物量为 $0 . 5 4 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,梭梭单位面积地上生物量为$1 7 . 7 1 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ;白刺总地上生物量为 $0 . 9 0 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ，白刺单位面积地上生物量为 $2 9 . 7 6 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ;芦苇总地上生物量为 $1 . 7 3 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,单位面积地上生物量为$5 6 . 9 7 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ 。

![](images/3e5fe0de80e7f48b09da57ed324461ba7748d8f3a670378c282f76591879a37e.jpg)  
图7梭梭和白刺的冠幅分布(a)和芦苇的分布区(b)  
Fig.7Distribution of canopy breadth of Haloxylon ammodendron,Nitraria tangutorum(a)and the distribution area ofPhragmites australis(b)

# 4结论

（1）本研究将模型估算法与遥感数据相结合对研究区植被优势种地上生物量进行估算，与传统的地上生物量模型估算法相比[25,27],在区域植被地上生物量估算方面显示其优势，既能对种群地上生物量进行高精度估算，又能克服以往地上生物量模型间接估算区域地上生物量的不足。

(2）根据Worldview-2提取的梭梭、白刺冠幅面积及芦苇分布面积，结合野外试验与室内实验数据建立的梭梭和白刺冠幅面积、芦苇分布面积与地上生物量模型，估算得到整个研究区的植被优势种总的地上生物量为 $3 . 1 7 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,其中芦苇总地上生物量最大,为 $1 . 7 3 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,样方单位面积为 $5 1 1 . 9 6 \mathrm { ~ g ~ }$ ：$\mathrm { ~ m ~ } ^ { - 2 }$ ,与赵文智等[35]对河西荒漠绿洲区芦苇地上生物量研究结果基本一致;其次是白刺,地上总生物量为 $0 . 9 0 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,单位面积地上生物量为 $2 9 . 7 6 \mathrm { ~ g ~ }$ ：

$\mathrm { ~ m ~ } ^ { - 2 }$ ,白刺地上生物量估算主要在样点尺度,区域研究较少;梭梭地上总生物量最小,为 $0 . 5 4 \times 1 0 ^ { 3 } ~ 1$ ，单位面积地上生物量为 $1 7 . 7 1 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ 。陶冶等[28]利用相对盖度与地上生物量模型对古尔班通古特沙漠梭梭地上生物量进行了的估算，得到梭梭单位面积地上生物量为 $5 . 5 \mathrm { ~ g ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,与本研究结果稍有差异，一方面由于研究区环境的差异，从而导致植被生长状况不同，另一方面与遥感数据相比，基于样地调查的植被相对盖度估算区域地上生物量误差相对较大，也会对研究结果产生影响。

（3）使用辅以纹理特征的面向对象分类方法从高分辨率遥感影像Worldview-2上提取研究区梭梭、白刺的冠幅面积以及芦苇的分布面积,总体Kappa系数为 $8 7 . 9 \%$ ,总体精度为 $9 1 . 3 \%$ ,说明使用辅以纹理特征的面向对象分类方法适于干旱区植被信息的提取。

（4）地上生物量尺度转换问题始终是生态学研究的重点和难点之一[28]，本文利用Worldview-2 遥感影像数据，实现了地上生物量估算由“冠幅”到“区域”的转换，即由“点”到“面”的转换，可以为区域地上生物量估算提供方法借鉴。但也存在着不足，由于荒漠植被根系大，延伸范围广，地下部分采样困难，且采样破坏性大，因此本研究只对该区域地上生物量进行了估算，而没有估算地下生物量，在以后应进一步研究。

# 参考文献(References)

[1]LAUENROTHW K,HUNT HW,SWIFTD M,et al.Estimating aboveground net primary production in grasslands:A simulation approach[J].Ecological Modelling,1986,33(2）:297-314.

[2]BARRACHINA M,CRISTOBAL J,TULLA AF.Estimating aboveground biomass on mountain meadows and pastures through remote sensing[J]. International Journal of Applied Earth Observations& Geoinformation,2015,38(2):184-192.

[3] HOUGHTONRA,LAWRENCEKT,HACKLERJL,etal.The spatial distribution of forest biomass in the Brazilian Amazon：A comparison of estimates[J].Global Change Biology,2OO1,7（7）： 731-746.

[4]TAHVANAINEN T,FORSS E.Individual tree models for the crown biomass distribution of Scots pine,Norway spruce and birch in Finland[J].Forest Ecology&Management,2008,255（3-4）:455- 467.

[5］李爽,张祖陆,周德民.湿地植被地上生物量遥感估算模型研究——以洪河湿地自然保护区为例[J].地理研究，2011，30(2):278-290.[LI Shuang,ZHANG Zulu,ZHOU Demin.An es-timation of aboveground vegetation biomass in a national naturalreserve using remote sensing|J」.Geographical Research,2O11,30(2):278-290.]

[6]张蕊,李飞,王媛,等.三江源区退化天然草地和人工草地生物量碳密度特征[J].自然资源学报，2018，33（2）：185-194.[ZHANGRui,LIFei,WANGYuan,etal.Characteristicsofbio-mass carbon density of degraded natural grassland and artificialgrassland in the“Three-River Headwaters”region[J].Journal ofNatural Resources,2018,33(2）:185-194.]

[7]贾文雄,王洁,张禹舜,等.祁连山南坡灌丛草甸生物量变化与水热因子的关系研究[J」.地理科学，2016，36（8）：1243-1251.[JIAWenxiong,WANG Jie,ZHANGYushun,etal.Biomassvariationof shrubberymeadowandrelationwithhumidityand heatfacts in the southern slop of the Qilian Mountains[J].ScientiaGeographica Sinica,2016,36(8）:1243-1251.]

[8］陈生云,刘文杰,叶柏生,等.疏勒河上游地区植被物种多样性和生物量及其与环境因子的关系[J].草业学报，2011，20（3）：70-83.[CHENShengyun,LIUWenjie,YEBaisheng,etal.Spe-cies diversity of vegetation in relation to biomass and environmentalfactors in the upper area of the Shule River[J].Acta PrataculturaeSinica,2011,20(3）:70-83.]

[9］李尚益,方晰,陈金磊,等.人为干扰对中亚热带森林生物量及其空间分布格局的影响[J].生态学报，2018,38（17）：6111-6124.[LI Shangyi,FANGXi,CHEN Jinlei,etal.Effects of different degree of anthropogenic disturbance on biomass and spatialdistribution in subtropical forests in Central Southern China[J].Acta Ecologica Sinica,2018,38（17）:6111-6124.]

[10」刘双娜，周涛，舒阳，等.基于遥感降尺度估算中国森林生物量的空间分布［J」.生态学报，2012，32（8）：2320-2330.［LIUShuangna,ZHOU Tao,SHU Yang,etal.The estimating of the spa-tial distribution of forest biomass in China based on remote sensingand downscaling techniques[J].Acta Ecologica Sinica,2012,32（8):2320 -2330.]

[11]RADLOFF,FRANSG T,MUCINA,et al.A quick and robust method for biomass estimation in structurally diverse vegetation [J].Journal of Vegetation Science,2007,18(5）:719 -724.

[12］李文娟,赵传燕,彭焕华,等.黑河上游天涝池流域灌丛地上生 物量空间分布［J].生态学报,2015,35（4）：1134-1141.［LI Wenjuan,ZHAO Chuanyan,PENG Huanhua,et al. The spatial distribution of the aboveground biomass shrub in Tianlaochi catchment in the upper reaches of Heihe River[J].Acta Ecologica Sinica,2015,35(4) :1134 -1141.]   
[13］何兴元,任春颖,陈琳,等.森林生态系统遥感监测技术研究进 展[J].地理科学,2018,38（7):997-1011.[HE Xingyuan, REN Chunying,CHEN Lin,et al. The progress of forest ecosystems monitoring with remote sensing techniques[J].Scientia Geographica Sinica,2018,38(7):997-1011.]   
[14］彭守璋,赵传燕,彭焕华,等.黑河下游怪柳种群地上生物量及 耗水量的空间分布［J].应用生态学报,2010,21（8）：1940- 1946.[PENG Shouzhang,ZHAO Chuanyan,PENG Huanhua,et al.Spatial distribution of Tamarix ramosissima above ground biomass and water consumption in the lower reaches of Heihe River [J].Chinese Journal of Applied Ecology,2010,21（8）:1940 - 1946.]   
[15］张华,赵传燕,张勃,等.高分辨率遥感影像GeoEye-1在黑河下 游怪柳生物量估算中的应用[J].遥感技术与应用,2011,26 (6）:713-718.[ZHANG Hua,ZHAO Chuanyan,ZHANG Bo,et al.The application of high resolution satelite imagery GeoEye-1 on the biomass estimation of Tamarix ramosissima in lower reaches of Heihe River Basin[J].Remote Sensing Technology and Application,2011,26(6) :713-718.]   
[16］陈君颖,田庆久.高分辨率遥感植被分类研究[J].遥感学报, 2007,11(2）:221-227.[CHEN Qunying,TIAN Qingjiu.Vegeta tion classification based on high-resolution satellite image[J]. Journal of Remote Sensing,2007,11(2):221-227.]   
[17］严子柱,尉秋实,李得禄,等.民勤青土湖盐碱化退耕地天然植 被的演替特征[J].中国农学通报,2014,30(16):1-6.[YAN Zizhu,WEI Qiushi,LI Delu,et al. Natural vegetation succession characteristics of Qingtu Lake salinization abandoned lands in Minqin[J]. Chinese Agricultural Science Bulletin,2014,30(16）:1- 6.]   
[18］赵鹏.民勤绿洲荒漠过渡带植被空间分布及其环境解释[D]. 兰州：甘肃农业大学,2014.［Zhao Peng.Spatial distribution of plant communities and environmental interpretation in Minqin oasis-desert ecotone[D]. Lanzhou: Gansu Agricultural University, 2014.]   
[19］刘淑娟,马剑平,刘世增,等.青土湖水面形成过程对荒漠植 物多样性的影响[J].水土保持通报,2016,36(1)：27－32. [LIU Shujuan,MA Jianping,LIU Shizeng,et al.Effectsof Qingtu Lake water area formation on diversity of plants in desert region [J].Bulletin of Soil And Water Conservation,2016,36（1）：   
27 -32.] [20］鞠强,贡璐,杨金龙,等.梭梭光合生理生态过程与干旱环境的 相互关系[J].干旱区资源与环境,2005,19(4)：201－204. [JU Qiang,GONG Lu,YANG Jinlong,et al. Interrelation between the process of photosynthetic physiological ecology of Haloxylon ammodendron and xeric environment[J].Journal of Arid Land Resources and Environment,2005,19(4）:201-204.] [21］何炎红,郭连生,田有亮.白刺叶不同水分状况下光合速率及 其叶绿素荧光特性的研究[J].西北植物学报,2005,25（11）：   
2226 - 2233.[HE Yanhong,GUO Liansheng,TIAN Youliang. Photosynthetic rates and chlorophyll fluorescence of Nitraria tangutorum at different leaf water potentials[J].Acta Bot Boreal-Occident Sin,2005,25(11) :2226 -2233.] [22］杨允菲,郎惠卿.不同生态条件下芦苇无性系种群调节分析 [J].草业学报,1998,7（2）:1-9.［YANG Yunfei,LANG Huiqing.A study of population regulation of Phragmiites communis as a clonal plant in diferent ecological[J].Acta Prataculturae Sinica,1998,7(2):1-9.] [23］陈政融,刘世增,刘淑娟,等.青土湖水面形成对区域典型植被 分布的影响[J].中国农学通报,2015,31（21)：177－183. [CHEN Zhengrong,LIU Shizeng,LIU Shujuan,et al. Effect of water body forming on the distribution of typical vegetation in Qingtu Lake[J]. Chinese Agricultural Science Bulletin,2015,31（21）:   
177 -183.] [24］蒙诗栎,庞勇,张钟军,等.WorldView-2 纹理的森林地上生物 量反演［J].遥感学报,2017,21（5）：812－824.［MENG Shiyue,PANG Yong，ZHANG Zhongjun,et al. Estimation of aboveground biomass in a temperate forest using texture information from WorldView-2[J].Journal of Remote Sensing,2017,21 (5) :812 -824.] [25］赵成义,宋郁东,王玉潮,等.几种荒漠植物地上生物量估算的 初步研究[J].应用生态学报,2004,15（1）：49－52.[ZHAO Chengyi,SONG Yudong，WANG Yuchao,et al.Estimation of aboveground biomass of desert plants [J]. Chinese Journal of Applied Ecology,2004,15(1）:49-52.] [26］魏小平,赵长明,王根轩,等.民勤荒漠绿洲过渡带优势植物地 上和地下生物量的估测模型(英文)[J].植物生态学报/Zhiwu Shengtai Xuebao,2005,29（6）: 878-883.[WEI Xiaoping, ZHAO Changming,WANG Genxuan,et al.Estimation of aboveand below-ground biomass of dominant desert plant species in an oasis-desert ecotone of Minqin China[J].Acta Phytoecologica Sinica,2005,29(6):878 -883.] 「27]彭王兰涂卫国句维桦 笔+寒沟白然保护区4种水深梯度

下芦苇分株地上生物量的分配与生长[J].应用与环境生物学 报,2008,14（2）:153-157.[PENG Yulan,TU Weiguo,BAO Weikai,et al.Aboveground biomass allocation and growth of Phragmitesaustralis ramets at four water depths in the Jiuzhaigou Nature Reserve,China[J].Chin JAppl Environ Biol,2008,14 (2):153\~157.]   
[28］陶冶,张元明.荒漠灌木生物量多尺度估测——以梭梭为例 [J].草业学报,2013,22(6）:1-10.[TAO Ye,ZHANGYuanming. Multi-scale biomass estimating of desert shrubs:A case study of Haloxylon ammodendron in the Gurbantunggut Desert,China [J].Acta Prataculturae Sinica,2013,22(6）:1-10.]   
[29]刘良云.植被定量遥感原理与应用[M].北京:科学出版社, 2014:93-105.［LIU Liangyun.Principles and applications of quantitative remote sensing for vegetation[M].Beijing:Science Press,2014:93-105.]   
[30］田甜,范文义,卢伟,等.面向对象的优势树种类型信息提取技 术[J].应用生态学报,2015,26(6):1665-1672.[TIAN Tian, FAN Wenyi,LU Wei,et al.An object-based information extraction technology for dominant tree species group types[J]. Chinese Journal of Applied Ecology,2015,26(6):1665 -1672.]   
[31]SMITH JR,CHANG S F.Automated binary texture feature sets for image retrieval[ C]//IEEE International Conference on Acoustics, Speech,and Signal Processing,Atlanta,GA,USA,1996:2239 - 2242.   
[32］张华,张改改,吴睿.基于GF-1卫星数据的面向对象的民勤绿 洲植被分类研究[J].干旱区地理,2017,40（4)：831－838. [ZHANG Hua,ZHANG Gaigai,WU Rui. Object-based vegetable classification based on GF-1 imagery in Minqin Oasis[J].Arid Land Geography,2017,40(4） :831 -838.]   
[33]BAATZ M,SCHAP E. Multiresolution segmentation: An optimization approach for high quality multi-scale image segmentation[C] / STROBL J, BLASCHKE T,GRIESEBNER G.Angewandte Geographische Informationsverarbeitung X II,Wichmann,Heidelberg,Germany,2000:12 -23.   
[34] CONGALTON R G,MEAD R A,ODERWALD R G.A quantitative method to test for consistency and correctness in photointerpretation[J].Photogrammetric Engineering & Remote Sensing,1983, 49(1) :69 -74.   
[35］赵文智,常学礼,李启森,等.荒漠绿洲区芦苇种群构件生物量 与地下水埋深关系[J].生态学报,2003,23(6)：1138-1146. [ZHAO Wenzhi,CHANG Xueli,LI Qisen,et al. Relationship between structural component biomass of reed population and ground water depth in desert oasis [J].Acta Ecologica Sinica,2003,23 (6):1138 -1146.

# Aboveground biomass estimation of the dominant species of vegetation in the Qingtu Lake at Minqin Qasis

ZHANG Hua， ZHANG Yu-hong， ZHANG Gai-gai (College of Geographyand Environment Science,NorthwestNormal University,Lanzhou730o7O,Gansu,China)

Abstract：The Qingtu Lakeareaat Minqin Qasis，Gansu Province,China belongs to the oasis-desert transition zone,and its ecological system is fragileand easy to develop intoadesert.As dominant speciesof vegetation in the Qingtu Lake area,Haloxylon ammodendron,Nitraria tangutorum and Phragmites australis play an important role in the stabilityand healthy development of ecological system.Therefore,we selected the Qingtu Lakearea as study area and took dominant speciesof the vegetationas the studyobjects.First,we applied object-oriented classification method with texture features to extractcanopy breadthof Haloxylon ammodendron,Nitraria tangutorumand distribution area of Phragmites australis by high-resolution remote sensing image with a spatial resolution of $0 . 5 \mathrm { ~ m ~ }$ (Worldview-2).Second,a model was established for therelationship between aboveground biomass and canopy breadth of Haloxylonammodendronand Nitraria tangutorumand aboveground biomassand distribution area of Phragmites australis based on the field test data.Third,weestimatedaboveground biomassof dominant species of vegetation with the modelcombined with thecanopyareaand distributionarea in the Qingtu Lake area,which hasachieved he conversion of aboveground biomass estimation of dominant species of vegetation from the“point”to the“area”.Results showed as follows:（1）Object-oriented classfication method with texture features achieved good classification results,the overall Kappa coefficient was $8 7 . 9 \%$ ,and the overall accuracy of $9 1 . 3 \%$ .（2）Total above ground biomass of the dominant of the vegetation in the study area was $3 . 1 7 \times 1 0 ^ { 3 } \mathrm { ~ t ~ }$ ,and the aboveground biomass of Haloxylon ammodendron ,Nitraria tangutorum,Phragmites australis was $0 . 5 4 \times 1 0 ^ { 3 } ~ \mathrm { { t } , 0 . 9 0 \times 1 0 ^ { 3 } ~ \mathrm { { t } , 1 . 7 3 \times 1 0 ^ { 3 } ~ } }$ t,respectively. Aboveground biomass was in the rank of Phragmites australis $>$ Nitraria tangutorum $>$ Haloxylon ammodendron.This paper could provide references for further study on ecological restoration and carbon reserve in Qingtu Lake area. Key words:aboveground biomass； vegetation dominant species；Worldview-2；Qingtu lake