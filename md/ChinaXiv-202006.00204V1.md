# 基于Sentinel-2A遥感数据对吉林白城市土壤含盐量的反演

马驰（辽宁省交通高等专科学校,辽宁 沈阳110122）

摘要：基于Sentiel-2A遥感数据,结合白城市表层土壤采样的全盐含量化验值,利用统计与拟合分析的方法，建立土壤盐渍化遥感监测模型,对研究区表层土壤含盐量进行反演分析。结果表明： $\textcircled{1}$ 研究区土壤的反射率与含盐量呈正相关,相关系数在Sentinel-2A第5波段（中心波长为 $0 . 7 0 5 ~ { \mu \mathrm { m } }$ )达到最大值，为 $r = 0 . 9 0 2$ ,利用第5波段反射率建立的土壤含盐量反演模型 $\mathrm { T S C } = 5 0 . 7 7 6 R _ { 5 } - 8 . 2 6 2$ ,模型的决定系数 $R ^ { 2 } = 0 . 8 1 3$ ,检验样本的均方根误差$\mathrm { R M S E } = 0 . 8 1 4 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ $\textcircled{2}$ 将反射率进行指数、幂、S 曲线等数学变换后，可以显著提高拟合精度,其中,第8波段反射率的幂函数变换后,建立土壤含盐量的单波段反演模型 $\mathrm { T S C } = 7 7 . 5 1 x ^ { 2 . 3 4 6 }$ 精度最好,模型的决定系数 $R ^ { 2 } = 0 . 8 8 8$ ：（204号 $\textcircled{3}$ 利用多元逐步回归分析的方法建立土壤含盐量的多波段反演模型 $\mathrm { T S C } = \mathrm { } - 1 3 . 8 1 0 + 3 8 . 9 7 3 R _ { 5 } \mathrm { ~ } - 1 4 . 1 2 2 e ^ { R _ { 5 } } \mathrm { ~ } +$ （204号 $2 3 . 8 9 6 R _ { 8 } ^ { 2 . 2 4 8 } + 1 . 7 4 3 \mathrm { l n } ( R _ { 9 } )$ ,模型的决定系数为 $R ^ { 2 } = 0 . 9 2 4$ ,检验样本的均方根误差为 $\mathrm { R M S E } = 0 . 7 3 6 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ 。

关键词：Sentinel $- 2 \mathrm { A }$ ；遥感；定量反演；盐渍土；白城市；吉林

土地盐渍化通常发生在干旱、半干旱地区，实时监测土壤含盐量对于土地盐渍化的防治、区域土壤生态环境的保护以及农业经济的可持续发展具有重要意义。遥感技术具有影像数据获取时间短、信息量丰富、生产成本低等优点，在土地盐渍化探测方面具有巨大潜力。

利用遥感技术对土地盐渍化研究主要经历了从定性分析到定量分析的过程，定性分析可采用目视解译提取遥感影像中的盐渍信息[1-2],也可根据盐渍土的光谱特征和纹理特征对遥感影像中的图斑进行自动分类[3-4];定量分析是利用遥感影像的光谱反射率与研究区土壤含盐量的测量值进行相关性分析，选取与土壤含盐量相关性最好的波段建立含盐量的反演模型，实现对研究区土壤含盐量的高精度监测[5-6]。20 世纪70年代,Rao 等[7]学者在研究盐渍化土壤与光谱反射率的关系时发现，随着土壤中含盐量的增加，可见光与近红外波段的光谱反射率随之增强;许迪等采用监督分类的方法，对Land-sat TM遥感影像进行处理，获得了宁夏青铜峡灌区土壤盐渍化的分布；何祺胜等 利用决策树分类的方法，对LandsatTM遥感影像进行处理，获得了库车河绿洲土地盐渍化信息;张雅丽等[10]利用地统计分析的方法，研究了艾比湖土壤含盐量的空间变异特征，获得了较好的研究效果。在利用遥感技术定量分析土壤盐渍化方面，国内外学者多选用LandsatTM/ETM等遥感数据,并取得了较高的分析精度，但是在数据源的选择方面暂时没有显著突破。据此，本研究以吉林省白城市为研究对象，利用Sentinel-2A遥感影像，结合研究区土壤含盐量的实验数据，定量反演研究区表层土壤的含盐量，为Sentinel-2A遥感影像在土壤成分探测等方面的应用提供参考。

# 1材料与方法

# 1.1 研究区概况

白城市位于吉林省西北部、松嫩平原西部，地理位置 $1 2 1 ^ { \circ } 3 8 ^ { \prime } \sim 1 2 4 ^ { \circ } 2 2 ^ { \prime } \mathrm { E }$ ， $4 4 ^ { \circ } 1 4 \sim 4 6 ^ { \circ } 1 8 ^ { \prime } \mathrm { N }$ ，东部与吉林省松原市接壤，南部与科尔沁左翼中旗毗邻，西部与科尔沁右翼中旗、突泉县相接，北部与黑龙江省泰来县、科尔沁右翼前旗、肇源县隔江相望，总面积$2 5 \ 6 9 2 \ \mathrm { k m } ^ { 2 }$ 。白城市地处温带大陆性季风气候区：冬长夏短，降水集中在夏季，雨热同期，春季干燥多风，夏季炎热多雨，雨热不均，秋季温和凉爽且短暂，冬季干冷，降雪较少。白城市东部、南部及北部地区湖泊众多，地势平坦，土壤排水不畅，是世界三大苏打盐渍土分布区之一。

# 1.2遥感影像获取与预处理

Sentinel-2A遥感卫星于2015年6月23日在法属圭亚那库鲁航天中心发射升空，重返周期为10d,影像数据的幅宽为 $2 9 0 ~ \mathrm { k m }$ ,包含13个波段，与

LandsatTM、ETM $^ +$ (重访周期为16d)等遥感影像相比，Sentinel-2A具有更高的空间分辨率、光谱分辨率及更短的重访周期，主要参数见表1。

本试验选择与土壤采样时间同步的4景Senti-nel-2A影像，遥感影像获取于2018年5月7日。影像的预处理工作包括辐射校正、大气校正、几何校正、影像拼接与裁剪等。利用欧空局提供的Sen2cor数据处理软件对Sentinel-2A遥感影像进行辐射校正与大气校正，实现将大气上层的表观反射率转化为大气下层的地表反射率；在Erdas软件中利用1:50000地形图对遥感影像进行几何校正及遥感影像的裁剪与拼接等工作。

表1Sentinel-2A与Landsat $\mathbf { E T M + }$ 参数对比  
Tab.1 Comparison of parameters between Sentinel-2A and Landsat $\mathbf { E T M + }$   

<html><body><table><tr><td colspan="5">Sentinel - 2A</td><td colspan="5">Landsat ETM +</td></tr><tr><td>波段号 (N)</td><td>波段名称</td><td>中心波长 /nm</td><td>波谱宽度 /mm</td><td>空间分辨率 /m</td><td>波段号 (N)</td><td>波段名称</td><td>中心波长 /mm</td><td>波谱宽度 /mm</td><td>空间分辨率 /m</td></tr><tr><td>1</td><td>深蓝</td><td>443</td><td>20</td><td>60</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>2</td><td>蓝</td><td>490</td><td>65</td><td>10</td><td>1</td><td>蓝</td><td>483</td><td>65</td><td>30</td></tr><tr><td>3</td><td>绿</td><td>560</td><td>35</td><td>10</td><td>2</td><td>绿</td><td>560</td><td>80</td><td>30</td></tr><tr><td>4</td><td>红</td><td>665</td><td>30</td><td>10</td><td>3</td><td>红</td><td>662</td><td>60</td><td>30</td></tr><tr><td>5</td><td>红边1</td><td>705</td><td>15</td><td>20</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>6</td><td>红边2</td><td>740</td><td>15</td><td>20</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>7</td><td>红边3</td><td>783</td><td>20</td><td>20</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>8</td><td>近红外</td><td>842</td><td>115</td><td>10</td><td>4</td><td>近红外</td><td>835</td><td>125</td><td>30</td></tr><tr><td>8A</td><td>窄近红外</td><td>865</td><td>20</td><td>20</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>9</td><td>水汽波段</td><td>945</td><td>20</td><td>60</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>10</td><td>卷云波段</td><td>1 375</td><td>30</td><td>60</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>11</td><td>短波红外</td><td>1610</td><td>90</td><td>20</td><td>5</td><td>短波红外</td><td>1 648</td><td>200</td><td>30</td></tr><tr><td>12</td><td>短波红外</td><td>2190</td><td>180</td><td>20</td><td>7</td><td>短波红外</td><td>2206</td><td>260</td><td>30</td></tr></table></body></html>

# 1.3 土壤采样及化验

于2018年5月7—9日在研究区进行土壤采样，共采得土壤样品56个，采样点均匀分布于研究区内（图1）。采样过程中采用4点采样法：在$3 0 \mathrm { ~ m ~ } \times 3 0 \mathrm { ~ m ~ }$ 范围内采取4个表层( $0 \sim 1 5 \ \mathrm { c m } ) ,$ 土壤样品并混合，收集 $1 ~ \mathrm { k g }$ 放入采样袋；利用手持GPS接收机获取采样点经纬度，用以确定采样点在遥感图像中的位置。将土样在实验室晾干、研磨，剔除土壤中的小石块及植物根须等杂质，并过 $1 \ \mathrm { m m }$ 筛。土壤中全盐含量的测试采用干残渣法。

# 1.4土壤含盐量与土壤反射率相关性分析

将56个土样分为两部分：随机选取42个作为建模样本，将建模样本土壤含盐量与采样点在Sen

![](images/e333e63ee7d4fc5a0c645e957ce8e23451327bea707b1ba0ad17f5ec917d327a.jpg)  
图1土壤采样点分布示意图 Fig.1The sketch map of soil sampling site

tinel-2A影像各波段的反射率进行相关性分析，相关性最好的波段作为土壤含盐量反演的敏感波段。

$$
r = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \left( x _ { i } - { \overline { { x } } } \right) \left( y _ { i } - { \overline { { y } } } \right) } { \displaystyle { \sqrt { \sum _ { i = 1 } ^ { n } \left( x _ { i } - { \overline { { x } } } \right) ^ { 2 } } } { \sqrt { \sum _ { i = 1 } ^ { n } \left( y _ { i } - { \overline { { y } } } \right) ^ { 2 } } } } }
$$

式中： $r$ 为土壤含盐量与反射率的相关系数; $x _ { i }$ 与 $\overline { { x } }$ 为土壤含盐量的实测值与平均值; $y _ { i }$ 与 $\mathit { \Pi } _ { \overline { { y } } } ^ { - }$ 表示土壤反射率的实测值与平均值。

国内外学者的研究结果表明，将反射率进行适当的数学变换后，可以有效削弱遥感影像中噪声的影响,提高与土壤含盐量的相关性[11-12]。本试验将Sentinel-2A影像各波段反射率 $( R )$ 进行倒数$( 1 / R )$ ）、对数（ $\mathbf { l n } R _ { \mathbf { \ell } } ^ { \dagger }$ ）、指数 $\left( \mathbf { e } ^ { R } \right)$ 、一阶微分 $( R ^ { \prime } )$ 、幂函数 $( R ^ { \mathrm { a } } )$ 、S曲线函数等数学变换，并与土壤含盐量进行相关性分析，相关性最好的波段作为土壤含盐量反演的敏感波段。

# 1.5反演模型建立及模型精度检验

利用SPSS软件将Sentinel-2A影像反射率与土壤含盐量进行逐步回归分析，建立研究区土壤含盐量的一元和多元反演模型。为了检验反演模型的精度与稳定性，将剩余的14个土样作为检验样本。模型的精度由模型的决定系数（coefficientofdeter-mination, $R ^ { 2 }$ )衡量， $R ^ { 2 }$ 越大表明模型的精度越高；模型的稳定性由均方根误差（root mean square error,RMSE)衡量，RMSE 越小表明模型的稳定性越好。

$$
R ^ { 2 } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } \big ( \hat { y } _ { i } - \overline { { y } } \big ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } \big ( y _ { i } - \overline { { y } } \big ) ^ { 2 } }
$$

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left( \hat { y } _ { i } - y \right) ^ { 2 } }
$$

式中： $y _ { i }$ 为含盐量实测值； $\overline { { y } }$ 为含盐量平均值； $\hat { y }$ 为含盐量反演值； $n$ 为建模(检验)样本个数。

# 2 结果与分析

# 2.1单波段反演模型的建立与检验

图2显示：研究区土壤含盐量与反射率呈正相关,且在第5波段达到最大值,相关系数 $r = 0 . 9 0 2$ 相关性最差的为第10波段，相关系数为 $r = 0 . 5 1 6$ 。以第5波段反射率建立研究区土壤含盐量的反演模型为 $\mathrm { T S C } = 5 0 . 7 7 6 R _ { 5 } \ : - \ : 8 . \ : 2 6 2$ ，模型的决定系数R²=0.813,模型的均方根误差RMSE=0.932g·$\mathbf { k g } ^ { - 1 }$ 。利用反演模型计算检验样本含盐量的估测值，与其实测值建立散点图（图3）。图3显示，研究区土壤含盐量的估测值和实测值较均匀的分布于1:1直线两侧,拟合模型为 $Y = 0 . 8 8 2 X + 1 . 7 8 5$ ,模型的决定系数 $R ^ { 2 } = 0 . 9 0 3$ ,均方根误差 $\operatorname { R M S E } = 0 . 8 1 4$ $\mathbf { g } \cdot \mathbf { k } \mathbf { g } ^ { - 1 }$ 。

![](images/ef54c44b0ce7879dcce0ca6571b9326b85dbe5f721d53c65bd1dee48c1166e80.jpg)  
图2各波段反射率与含盐量相关系数

![](images/bc2b458e63a12728629aae4a30ee010768b52110b53806aa4182193fa8575941.jpg)  
Fig.2Correlation coefficient of reflectivity and salt content   
图3单波段含盐量估测值与实测值散点图 Fig.3Comparison between predicted values and measured values of salt content single-band

选择反射率的倒数、对数、指数、幂函数、S函数及三次函数变换的精度最高的波段绘图（图4），图中显示，反射率经过合适的数学变换后与研究区土壤含盐量相关性显著提高。利用第2波段反射率建立的 S曲线反演模型 $\mathrm { T S C } = \mathrm { e } ^ { ( 4 6 5 3 - 0 . 6 1 8 / x ) }$ 精度最高,模型的决定系数 $R ^ { 2 } = 0 . 8 6 8$ ,均方根误差 $\mathrm { R M S E } =$ $0 . 8 5 1 \ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 }$ ;第5波段反射率建立的指数函数模型 $\mathrm { T S C } = 0 . 5 7 9 \mathrm { e } ^ { 7 . 7 4 1 x }$ 精度最高，模型的决定系数$R ^ { 2 } = 0 . 8 8 2$ ,均方根误差 $\mathrm { R M S E } = 0 . 8 4 2 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ ;第6波段反射率建立的三次方函数模型 $\mathrm { T S C } = - 0 . 1 2 6 -$ $5 . 7 4 x + 8 1 . 9 4 x ^ { 2 }$ 精度最高，模型的决定系数 $R ^ { 2 } = { }$ 0.881,均方根误差 $\mathrm { R M S E } = 0 . 8 4 3 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ ;第8波段反射率建立的幂函数模型 $\mathrm { T S C } = 7 7 . 5 1 x ^ { 2 . 3 4 6 }$ 精度最高，模型的决定系数 $R ^ { 2 } = 0 . 8 8 8$ ,均方根误差$\mathrm { R M S E } = 0 . 8 4 0 \textrm { g } \cdot \mathrm { k g } ^ { - 1 }$ ;第9波段反射率建立的对数模型 $\mathrm { T S C } = 3 9 . 3 3 + 1 8 . 3 9 \mathrm { l n } x$ 精度最高，模型的决定系数 $R ^ { 2 } = 0 . 7 5 2$ ,均方根误差 $\mathrm { R M S E } = 1 . 1 6 5 \mathrm { ~ g ~ } ^ { . }$ $\mathbf { k g } ^ { - 1 }$ 。

![](images/3a6bd1590a32a4fcf165aae70812c0d8a897d51461730d01c3d965e86989934b.jpg)  
图4含盐量的单波段反演模型  
Fig.4Single-band inversion model for salt content

# 2.2多波段反演模型的建立与检验

将Sentinel-2A影像各波段反射率（反射率的变换)与研究区土壤含盐量进行多元逐步回归分析，建立土壤含盐量的多波段反演模型（表2）。多元回归分析结果显示：利用Sentinel-2A影像多波段反射率(反射率变换)建立的研究区土壤含盐量多元反演模型，相对于单波段反演模型，模型的精度与稳定性均有所提升，其中，由第2、第6、第7波段反射率建立的含盐量多元反演模型 $\mathrm { T S C } \ =$ $- 1 1 . 4 3 6 + 5 2 . 4 5 8 R _ { 2 } - 7 6 . 0 4 4 R _ { 6 } + 9 0 . 2 9 2 R _ { 7 }$ ,模型精度提升较小,模型的决定系数 $R ^ { 2 } = 0 . 8 9 3$ ,均方根误差$\mathrm { R M S E } = 0 . 8 3 9 \mathrm { ~ g ~ } \cdot \mathrm { k g } ^ { - 1 }$ ;利用第5波段反射率、第5波段指数变换、第8波段幂函数变换、第9波段对数变换建立的多元反演模型 $\mathrm { T S C } = - 1 3 . 8 1 0 + 3 8 . 9 7 3 R _ { 5 } -$ $1 4 . 1 2 2 \mathrm { e } ^ { R _ { 5 } } + 2 3 . 8 9 6 R _ { 8 } ^ { 2 . 2 4 8 } + 1 . 7 4 3 \mathrm { l n } \left( R _ { 9 } \right)$ ,模型的精度与稳定性较单波段模型均有显著提升，模型的决定系数 $R ^ { 2 } = 0 . 9 2 4$ ,均方根误差 $\mathrm { R M S E } = 0 . 7 8 2 \mathrm { ~ g ~ } \cdot \mathrm { k g } ^ { - 1 }$ 。

表2多波段反演模型  
Tab.2Multi-band inversion model   

<html><body><table><tr><td>模型形式</td><td>入选波段</td><td>反演模型</td><td>R²</td><td>RMSE</td></tr><tr><td>反射率</td><td>R、R6、R7</td><td>TSC=-11.436 +52.458R-76.044R6 +90.292R7</td><td>0.893</td><td>0.839</td></tr><tr><td>倒数</td><td>R、R、R</td><td>TSC =32.062-8.142/R +4.382/R-1.377/R9</td><td>0.908</td><td>0.811</td></tr><tr><td>对数</td><td>R、R9</td><td>TSC =38.130 + 13.398ln(R）+6.293ln(R9)</td><td>0.896</td><td>0.835</td></tr><tr><td>指数</td><td>R、R、R8</td><td>TSC=-54.402 +78.412eR2-66.270eR3 +32.816eR8</td><td>0.907</td><td>0.803</td></tr><tr><td>幂函数</td><td>R5、R、Rg</td><td>TSC = -54.527 +38.455R2 281-8.767R²446 + 18.232R& 248</td><td>0.909</td><td>0.801</td></tr><tr><td>波段求和</td><td>R5、Rg</td><td>TSC =24.193（R5 +Rg）-8.621</td><td>0.898</td><td>0.834</td></tr><tr><td>混合模型</td><td>R、R8、Rg</td><td>TSC = -13.810 +38.973R5 -14.122eR5 +23.896R2248 +1.743ln(Rg)</td><td>0.924</td><td>0.782</td></tr></table></body></html>

![](images/adaa5487dd36e591fb505e83fc6cf3ab3b5025fc261c22236e65e1d43972bdad.jpg)  
图5多波段含盐量估测值与实测值散点图 Fig.5Comparison between predicted values and measured values of salt content multi-band

![](images/1b276dc30ef824d86d56ddcc2e41b7ea17cd0e86699ff5498293b7b4d9b2ac25.jpg)  
图6研究区土壤含盐量反演结果  
Fig.6Inversion map of soil salt content in research area

利用反演模型 $\mathrm { T S C } = - 1 3 . 8 1 0 + 3 8 . 9 7 3 R _ { 5 } \ .$ ，$1 4 . 1 2 2 \mathrm { e } ^ { R _ { 5 } } + 2 3 . 8 9 R _ { 8 } ^ { 2 . 2 4 8 } + 1 . 7 4 3 \mathrm { l n } ( R _ { 9 } )$ ,计算检验样本含盐量的估测值，与其实测值建立散点图（图5）。散点图显示，研究区土壤含盐量的估测值和实测值均匀的分布于 $1 : 1$ 直线两侧,拟合模型为 $Y =$ $0 . 8 4 5 X + 1 . 5 9 0$ ,模型的决定系数 $R ^ { 2 } = 0 . 9 3 8$ ，均方根误差 $\mathrm { R M S E } = 0 . 7 3 6 \mathrm { ~ g ~ } \cdot \mathrm { k g } ^ { - 1 }$ 。

利用反演模型 $\mathrm { T S C } = \mathrm { } - 1 3 . 8 1 0 + 3 8 . 9 7 3 R _ { 5 } \ -$ $1 4 . 1 2 2 \mathrm { e } ^ { R _ { 5 } } + 2 3 . 8 9 6 R _ { 8 } ^ { 2 . 2 4 8 } + 1 . 7 4 3 \mathrm { l n } ( R _ { 9 } )$ 反演研究区表层土壤含盐量并绘图（图6）。结果显示：白城市南部、西部及北部地区土壤盐渍化较严重，湖泊周围重度盐渍化分布较集中。土壤采样过程中发现，研究区西部、南部、北部地区湖沼众多且地势低平、排水不畅，容易形成土地盐渍化灾害。

# 3 讨论与结论

# 3.1 讨论

白城市表层土壤含盐量与Sentinel-2A影像反射呈正相关，相关系数在第5波段（波长 $0 . 6 9 0 \sim$ $0 . 7 2 0 ~ \mu \mathrm { m }$ )达到最大值，为 $r = 0 . 9 0 2$ ,其次是第8波段(波长 $0 . 7 2 7 \sim 0 . 9 5 7 ~ \mu \mathrm { m } \rangle$ ,相关系数为 $r = 0 . 8 6 9$ ，第7波段（波长 $0 . 7 6 3 \sim 0 . 8 0 3 ~ \mu \mathrm { m } )$ 相关系数为 $r =$ 0.865,该结果与刘焕军等[13-14]利用遥感技术研究土壤盐渍化时获得的结论相同或相近;将反射率进行指数、幂、S曲线、三次函数等数学变换后，可以显著提高反射率与土壤含盐量的相关性，该结果与栾福明等[15-16]研究的结论相同,其中,第8波段反射率的幂函数变换与土壤的含盐量相关性最好，所建立的单波段含盐量反演模型 $\mathrm { T S C } = 7 7 . 5 1 x ^ { 2 . 3 4 6 }$ ,决定系数 $R ^ { 2 } = 0 . \ 8 8 8$ ,均方根误差 $\mathrm { R M S E } = 0 . 8 4 0 \mathrm { ~ g ~ } \cdot$ （204号$\mathbf { k g } ^ { - 1 }$ ;利用多元逐步回归分析建立的土壤含盐量反演模型 $\mathrm { T S C } = - 1 3 . 8 1 0 + 3 8 . 9 7 3 R _ { 5 } - 1 4 . 1 2 2 \mathrm { e } ^ { R _ { 5 } } +$ 2 $3 . 8 9 6 R _ { 8 } ^ { 2 . 2 4 8 } \ + \ 1 . \ 7 4 3 \mathrm { l n } \ ( \ R _ { 9 } \ )$ ,其决定系数 $R ^ { 2 } \ =$ （200.924,检验样本的均方根误差 $\mathrm { R M S E } = 0 . 7 3 6 \mathrm { ~ g ~ } ^ { . }$ （204号$\mathbf { k g } ^ { - 1 }$ ,利用此模型反演研究区表层土壤含盐量获得了较好的效果，究其原因： $\textcircled{1}$ 本试验选择的遥感影像云覆盖率较小 $( \textless 1 \% )$ ，影像获取时间为5月初，此时研究区地表无绿色植被、冰雪覆盖，遥感影像可以真实反应地表信息； $\textcircled{2}$ 遥感影像的获取时间与土壤采样时间同步，有利于提高反演模型的精度； $\textcircled{3}$ 将反射率进行适当的数学变换后，有效削弱了遥感影像中噪声对土壤中盐分信息的影响; $\textcircled{4}$ 利用逐步回归分析的方法建立多元反演模型，剔除了遥感影像的冗余波段； $\textcircled{5}$ 将遥感影像进行辐射校正和大气校正，削弱了大气中水汽、臭氧、尘埃等对传感器成像的影响，获得了地表地物的真实反射率，有效提高了研究区土壤含盐量的反演精度。

然而，由于本试验中未能考虑表层土壤含水量对地表反射率的影响，成为引起研究区土壤含盐量反演误差的重要因素，在以后的工作中将进一步予以讨论。

# 3.2结论

（1）与Landsat系列遥感影像相比，Sentinel-2A遥感影像具有较高的空间分辨率与光谱分辨率，对地表细节的表达效果更佳，可以作为土壤含盐量遥感监测的数据源

（2）研究区表层土壤含盐量与Sentinel-2A影像各波段的反射率呈正相关，将反射率进行适当的数学变换后，可以有效提高土壤含盐量的反演精度。

（3）利用逐步回归分析的方法建立研究区土壤含盐量的多元反演模型，模型反演精度最高，用于反演白城市土壤含盐量并作图，获得了良好的效果。

# 奓考乂（Keierences）：

[1]Mougenot B,Pouget M,Epema G.Remote sensing of salt-ffected soils[J].Remote Sensing Reviews,1993,7:241 -259.   
[2]Dwivedi R S,Rao B R M.The selection of the best possible Landsat TM band combination for delineating salt-afected soils[J].International Journal of Remote Sensing,1992,13（11）:2051- 2058.   
[3］吴敏.新疆大黄山至奇台高速公路盐渍土遥感解译[J].公路 交通技术,2012(3）:31-37.[Wu Min.Remote sensing interpretation of salinized soil on Dahuangshan-Qitai expressway of Xinjiang[J].Technologyof Highway and Transport,2012（3）:31- 37.]   
[4］张佩民,张振德,李晓琴,等.青藏高原荒漠化遥感信息提取及 演变分析[J].干旱区地理,2006,29（5）：710-717.[Zhang Peimin,Zhang Zhende,Li Xiaoqin,et al.Desertification remote sensing information extraction from Qinhai-Tibet Plateau and evolution analysis[J].Arid Land Geography,2006,29（5）:710 - 717.]   
[5］张添佑,王玲,曾攀丽,等.基于MSAVI-SI特征空间的玛纳斯 河流域灌区土壤盐渍化研究[J].干旱区研究,2016,33（3）： 499 -505.[Zhang Tianyou,Wang Ling,Zeng Panli,et al. Soil salinization in the irrigated area of the Manas River Basin based on MSAVI-SI feature space[J].Arid Zone Research,2016,33（3）: 499 -505.]   
[6]李源,耿庆龙,赖宁,等.干旱区无覆膜滴灌冬小麦土壤盐分时 空演化特征［J].干旱区研究,2019,36（3）：582-588.［Li Yuan,Geng Qinglong,Lai Ning,etal. Spatiotemporal revolutionof soil salinityin winter wheat fields with diffrent yearsof drip irrigation without mulching in arid area[J].Arid Zone Research,2019, 36(3) :582 -588.]   
[7]Rao BR M,Sharma R C,Ravisankar T,et al.Spectral behaviour of salt-afectedsoilsJ].International JournalofRemoteSensing, 1995,16(12) :2125-2136.   
[8］许迪,王少丽,蔡林根,等.利用 NDVI指数识别作物及土壤盐 碱分布的应用研究[J].灌溉排水学报,2003,22(6)：5-8. [Xu Di,Wang Shaoli,Cai Lingen,et al.Applied study on identification of crops and salinity distribution by NDVI index[J]. Journal of Irrigation and Drainage,2003,22(6）:5 -8.]   
[9]何祺胜,塔西甫拉提·特依拜,丁建丽.基于决策树方法的干 旱区盐渍地信息提取研究——以渭干河－库车河三角洲绿洲 为例[J].资源科学,2006,28（6）:134-140.[He Qisheng, Tashpolat Tiyip,Ding Jianli.The extraction of saline soil information in arid area based on decision tree algorithm:A case study in the delta oasis of Weigan and Kuqa Rivers[J].Resource Science, 2006,28(6):134 -140.]   
[10］张雅莉,塔西甫拉提·特依拜,阿尔达克·克里木,等.艾比湖 湿地干湿季土壤水分和土壤盐分空间异质性研究[J].中国农 村水利水电,2017（1）:37-42.[Zhang Yali,Tashpolat Tiyip, Ardak Kelimu,etal.Monitoring heterogeneityofsoil salinity in dry and wet seasons in Xinjiang Ebinur Lake wetland[J].Rural Water Conservancy and Hydropower of China,2017(1）:37 -42.]   
[11］乔璐.哈尔滨城区土壤高光谱特性与TM遥感的定量反演 [D].哈尔滨：东北林业大学,2010.［Qiao Lu.Hyperspectral Characteristics of Soil and Quantitative Remote Sensing Inversion on TM Data in Harbin[D].Harbin;NortheastForestry University, 2010.]   
[12］马驰.基于HJ-1A 高光谱影像的土壤盐渍化遥感研究[J].干 旱区资源与环境,2014,28(2）:180-185.[Ma Chi.Research on soil salinization remote sensing of HJ-1A hyper spectral images [J]. Journal of Arid Land Resources and Environment,2014,28 (2) :180 -185.]   
[13］刘焕军,赵春江,王纪华,等.黑土典型区土壤有机质遥感反演 [J].农业工程学报,2011,28（7）:211-215.[Liu Huanjun, Zhao Chunjiang,Wang Jihua,et al. Soil organic matter predicting with remote sensing image in typical black soil area of Northeast China[J].Transactions of the Chinese Society of Agricultural Engineering,2011,28（7）:211-215.]   
[14］曾远文,陈浮,王雨辰,等.采煤矿区表层土壤有机质含量遥感 反演[J].水土保持通报,2013,33（2）:169-172.[Zeng Yuanwen,Chen Fu,Wang Yuchen,et al.Predicting surface soil organic mater contents with remote sensing images in mining areas[J]. Bulletin of Soil and Water Conservation,2013,33（2）:169- 172.]   
[15］栾福明,张小雷,熊黑钢,等.基于TM影像的荒漠-绿洲交错 带土壤有机质含量反演模型[J].中国沙漠,2014,34（4）：1080 -1086.[Luan Fuming,Zhang Xiaolei,Xiong Heigang,et al. Inversion models of soil organic matter in oasis-desert ecotone based on TM image reflectance[J]. Journal of Desert Research,2014,34 (4):1080-1086.]   
[16］李媛媛,李微,刘远,等.基于高光谱遥感土壤有机质含量预测 研究[J].土壤通报,2014,45(6):1313-1318.[Li Yuanyuan, Li Wei,Liu Yuan,etal.Study on theprediction of soil organic matter content based on hyperspectral remote sensing[J]. Chinese Journal of Soil Science,2014,45(6):1313 -1318.]

# Inversion of soil salt content based on Sentinel -2A remote sensing in Baicheng City,Jilin Province

MA Chi

(Liaoning College ofCommunication,Shenyang,Shenyang11O122,Liaoning,China)

Abstract:Soil salinization is one of the main types of land degradation,and poses a worldwide problem for resources and ecology.The western partof Jilin Province isthe largest soda saline soil areain China.Real-time monitoring of soil salt contentisof great importanceforthe preventionand controlof soilsalinization,the protectioofregional soil ecological environments，,and thesustainable development of the agricultural economy.Based on Sentinel-2A remote sensing imagedata for Baicheng city,this thesis established aremote sensing monitoring model of soil salinization through theuseof statisticsand fiting analysis,and analyzed thesalt content of topsoil in the studyarea.Firstly,radiometric correctionand atmosphericcorrection were carriedout inorder to eliminate the effects of atmospheric water vapor,methane,and ozone on the procesing of remote sensing images.Secondly,the reflectance is transformed intoreciprocal,logarithm,exponent,power,and Sfunction to weaken the influenceof noise in theremote sensing images.Finally,the sensitive bands ofsoil salinity in the studyarea wereobtained bycorrelation analysis,and the inversion model of soil salinity was established by multiple stepwise regression analysis.The results enable the following conclusions to be made.Soil reflectance was positively corelated with soil salt content, and the correlation coefficient reached a maximum in the Sentinel $- 2 \mathrm { A }$ band 5（center wavelength of $0 . 7 0 5 ~ { \mu \mathrm { m } }$ ）， which was $r = 0 . 9 0 2$ . The soil salt content inversion model $\mathrm { T S C } = 5 0 . 7 7 6 R _ { 5 } - 8 . 2 6 2$ was established using band 5 reflectance,a coefficient of determination of $R ^ { 2 } = 0 . 8 1 3$ ,and the root mean square error $\mathrm { R M S E } = 0 . 8 1 4 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ ： Thefiting accuracycan be improved significantly by transforming reflectance into exponential,power,and S functions.The precision of the single-band soil salinity inversion model $\mathrm { T S C } = 7 7 . 5 1 x ^ { 2 . 3 4 6 }$ is best after transforming the eighth-band reflectance into a power function,when the coefficient of determination of the model is $R ^ { 2 } = 0 . 8 8 8$ ； The correlation between soil salinityand reflectance can be improvedsignificantly by transforming thereflectance into exponential,power,and S-curve functions.The multivariate stepwise regression method was used to establish an inversion model of soil salinity as follows $\mathrm { T S C } = - 1 3 . 8 1 0 + 3 8 . 9 7 3 R _ { 5 } - 1 4 . 1 2 2 \mathrm { e } ^ { R _ { 5 } } + 2 3 . 8 9 6 R _ { 8 } ^ { 2 . 2 4 8 } + 1 . 7 4 3 \mathrm { l n } ( R _ { 9 } )$ ： The coefficient of determination of the model was $R ^ { 2 } = 0 . 9 2 4$ ,and the root mean square error of the test sample was （202 $\mathrm { R M S E } = 0 . 7 3 6 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ .Redundant bands were eliminated while the accuracy of the model was guaranteed.

Key words: Sentinel $- 2 \mathrm { A }$ ；remote sensing；quantitative inversion；saline soil；Baicheng City；Jilin Province