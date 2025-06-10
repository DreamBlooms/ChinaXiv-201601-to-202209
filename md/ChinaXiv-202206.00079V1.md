# 基于遥感影像的黄河内蒙古段冰-水分类研究

翟涌光'，张鑫'，冀鸿兰，牟献友¹，张宝森²(1.内蒙古农业大学水利与土木建筑工程学院,内蒙古 呼和浩特010018;2.黄河水利委员会黄河水利科学研究院，河南 郑州450003)

摘要：及时获取凌汛期河冰和水体的空间分布特征，对于预测冰凌灾害、提高防凌信息化管理水平有重要意义。遥感技术是当前获取河冰和水体空间分布的最主要手段之一。但是，黄河水体有大量悬浮泥沙，这给基于遥感技术的高精度冰-水分类带来了挑战。以黄河内蒙古段为例，基于Landsat8OLI遥感影像数据，在利用归一化积雪指数(NDSI)及河道矢量数据排除无关地物的基础上,对比了近红外波段反射率值、归一化差异水体指数(NDWI)、归一化积雪指数(NDSI)、改进的归一化积雪指数(MNDSI)以及归一化差异未封冻水体指数(NDUWI)在黄河内蒙古段典型河道河冰、水体分类中的表现，计算各指标总体分类精度及Kappa系数并进行阈值稳定性分析。结果表明：在利用NDSI和高清历史影像排除河道外无关地物后，NDUWI在各子段影像中的总体分类精度和Kappa系数均达到 $9 0 . 0 0 \%$ 及0.90以上，其河冰、水体最优区分阈值大体分布于阈值中值附近。研究结果可为凌汛期黄河冰凌监测方法的选取以及冰上爆破位置的拟定提供依据。

关键词：河冰；遥感指数；阈值稳定性；不确定性；Landsat8；黄河内蒙古段文章编号：

冰凌由河流中的河水冻结、堆积而产生，在河道中堆积易引发冰塞、冰坝等现象，轻则河冰堆积上岸,重则造成漫堤、溃堤决口[1]。黄河内蒙古段河道形态多样,河势复杂,易产生冰凌灾害[2]。因此,准确提取河冰、水体信息对研究河冰生消过程、河冰空间变化以及冰凌洪水的研判至关重要。传统野外观测局限于“点对点”式的局部观测，无法获得完整的河冰信息，冰情观测受到限制。卫星遥感则具有观测范围大、时效性强、数据内容客观等优点，近些年在河冰研究领域已被广泛应用[3]。

目前，利用遥感技术提取河冰、水体信息主要以目视解译、单波段反射率阈值、归一化积雪指数(NDSI）、归一化差异水体指数(NDWI)以及改进的归一化积雪指数(MNDSI)与单波段阈值相结合的方法为主[4]。杨中华等[5基于“四星三源"模式，在国内最早将遥感技术应用于黄河冰情监测当中，限于当时卫星影像空间分辨率，作者仅进行大尺度宏观观测，并未进行局部河段微观分析；赵水霞等[基于Landsat8彩色合成影像对黄河什四份子弯道河冰过程及分布进行目视解译，但作者并未进行提取精度验证；Chu等[基于MODIS数据近红外波段监测了加拿大奴隶河河冰过程，作者并未确定河冰、水体在近红外波段的反射率值，而是假设当近红外波段的反射率最大时河道内均为河冰，而反射率最小时河道内均为水体；Chaouch等8利用MODIS可见光及近红外波段的阈值构建决策树，提取河冰信息并获取河冰范围;Dozier[9于1989年提出的用于监测积雪变化的雪信息提取NDSI指数，该指数对积雪与土壤的区分度较高，目前也被应用于大尺度冰川、湖冰等领域[10-13];Li等[14]利用NDSI对1999—2018年青藏高原八宝河河冰分布进行监测，而八宝河流域冬季河水完全封冻并不存在清沟(狭长型不

# 干旱区地理

结冰的裸露水面），提取任务主要以区分河冰与土壤像元为主，NDSI分类精度令人满意;牟献友等[15]根据黄河水体的光谱特征，以蓝色及绿色波段构建归一化差异未封冻水体指数（NDUWI），在利用NDSI排除土壤、树木等其他地物像元的基础上，进而利用NDUWI进行河冰、水体提取，但以水体作为切入点的提取方法的精度有待进一步验证;勾鹏等[6发现近红外波段与短波红外波段构建的归一化指数直方图中两峰值间距大于NDSI直方图中的两峰间距，有利于区分河冰、水体，由此建立改进的归一化差异积雪指数(MNDSI)对纳木错湖冰进行识别，取得很好的效果。综合来看，对于黄河河冰、水体的监测，当前遥感技术和卫星影像的时空分辨率已基本满足冰期黄河冰凌监测的能力，但单一使用遥感指数模型存在难以区分河冰、水体与土壤的问题，河道边界难以提取；同时，各指数模型对于黄河河冰、水体监测的精度还有待验证。

黄河内蒙古段由于其自身河道水力条件的特殊性，凌汛期易发生卡冰结坝现象，增加“武开河”的风险[17]。鉴于此，本文选取黄河内蒙古段5个试验河段为研究对象，基于Landsat8OLI遥感影像数据，在利用GoogleEarth历史高清影像结合NDSI指数模型排除河道外无关地物的基础上，使用近红外波段反射率值、NDWI、NDSI、MNDSI以及NDUWI,利用各指数阈值对河冰、水体进行分类，进而计算监测精度，对阈值的稳定性及方法的适用性进行评价，以期为遥感技术监测河流冰情及冰凌洪水的研判提供参考。

# 1研究区、数据与方法

# 1.1 研究区概况

研究区始于黄河内蒙古段海勃湾水库，终于万家寨水库库尾区，全长约为 $6 5 0 \mathrm { k m }$ ,整体皇“几"字形分布[18（图1)。分别在河段上、中、下游选取试验河段，河段类型包括过渡型、游荡型及弯曲型；过渡型河段浅滩多且河道摆动幅度大；游荡型河段淤积严重且经常发生河冰漫滩、偎堤等现象[19]。实验区内地物类型包括主槽冰、河滩冰、清沟及土壤，河冰主要以平滑、冲击岸冰为主要类型。河段每年12月初开始流凌，至翌年3月末河段冰凌全部消融，受来水条件、河道特性等因素影响，水体在河床内及河滩上结冰；在流速较大的急流、浅滩处或排水口处常出现狭长型不结冰的裸露水面(清沟）。

![](images/af6951fb28fe77eac6065942a8c8d8c7a052c61249716664ff980752f1cfbad6.jpg)  
图1研究区概况  
Fig.1Overview of the study area

# 1.2数据来源与处理

1.2.1Landsat8遥感影像河冰信息提取基于Landsat8OLI影像(后文简称L8影像)数据，数据获取自美国地质调查局官网（United StatesGeologicalSurvey,简称 USGS,https://earthexplorer.usgs.gov/),所用影像均为L1T级产品，该级别影像是使用地面控制点和数字高程模型数据进行精确校正的数据产品，误差小于0.4个像元。试验所用使用的影像为无云或河道及河道附近无云的影像数据。影像信息见表1。

1.2.2验证数据试验使用GoogleEarth历史高清影像作为参考影像，选取与L8影像拍摄日期同日或相近日期的历史高清影像，由于拍摄日期处在河冰稳定封冻的1一2月，L8影像与参考影像成像时间差内的河冰覆盖基本不变。基于参考影像目视解译出的各类主要地物矢量数据将用于分类精度评价。因参考影像的空间分辨率在亚米级，故目视解译的误差将忽略不计。

1.2.3数据预处理L8影像的预处理过程为辐射定标及大气校正。预处理过程利用集成在ENVI5.5版本中的辐射定标及FLAASH（Fast line-of-sightatmospheric analysisofspectralhypercubes)大气校正工具获得地表反射率数据。其中，FLAASH中大气模型参数根据影像拍摄日上午的大气柱水汽量确定，该数据获取自MODIS标准大气产品中的MOD05数据集（下载地址:http://ladsweb.nascom.nasa.gov）。大气校正参数见表1。

所有L8影像均经过堤防矢量数据进行裁剪，只保留两岸堤防间的部分。首先基于GoogleEarth历史高清影像目视解译绘制的河道矢量边界进行裁剪，排除大部分河道外无关地物，其次利用NDSI对河岸边缘土壤及其他无关地物进行二次排除。因实验区位于两岸堤防内的河道范围，相关法律规定堤防内部不得设立建筑、道路等设施且河滩地不得占用，故经堤防矢量裁剪后的影像数据可有效排除附近民居、道路、工厂等其他无关地物；又因河道内树木极少且处于冬季，故假定河道内仅有河冰、水体、土壤3种地物。而NDSI对土壤和冰雪的分类精度已有前人证实在此不再赘述[9。为尽可能保留全部河冰、水体像元，故以0作为土壤与河冰、水体的分类阈值，影像预处理及分类流程见图2，流程化处理后待提取像元仅为河冰与水体，几乎无其他无关地物。

表1Landsat8OLI遥感影像信息及大气校正参数  
Tab.1 Landsat 8 OLI remote sensing image information and atmospheric correction parameters   

<html><body><table><tr><td>Landsat 8 OLI 影像条带号</td><td>日期 (年-月-日）</td><td>平均大气柱 水汽量/g·cm²</td><td>混合层高度/km</td><td>Landsat 8 OLI 影像条带号</td><td>日期 (年-月-日)</td><td>平均大气柱 水汽量/g·cm-2</td><td>混合层高度/km</td></tr><tr><td>129.032</td><td>2014-01-17</td><td>0.29</td><td>1.42</td><td>129.032</td><td>2017-02-26</td><td>0.22</td><td>2.19</td></tr><tr><td>128.032</td><td>2016-02-01</td><td>0.19</td><td>1.69</td><td>127.032</td><td>2018-02-15</td><td>0.12</td><td>2.23</td></tr><tr><td>128.032</td><td>2018-02-22</td><td>0.10</td><td>1.20</td><td>128.032</td><td>2018-02-06</td><td>0.19</td><td>2.20</td></tr><tr><td>130.032</td><td>2020-02-10</td><td>0.13</td><td>1.43</td><td>129.032</td><td>2018-02-13</td><td>0.17</td><td>2.23</td></tr><tr><td>128.032</td><td>2020-02-28</td><td>0.22</td><td>0.96</td><td>127.032</td><td>2019-01-17</td><td>0.10</td><td>2.19</td></tr><tr><td>127.032</td><td>2015-02-23</td><td>0.17</td><td>2.10</td><td>128.032</td><td>2019-01-24</td><td>0.26</td><td>2.13</td></tr><tr><td>128.032</td><td>2015-02-14</td><td>0.12</td><td>2.12</td><td>129.032</td><td>2019-02-16</td><td>0.28</td><td>2.22</td></tr><tr><td>129.032</td><td>2015-02-21</td><td>0.23</td><td>2.13</td><td>127.032</td><td>2020-02-21</td><td>0.22</td><td>2.13</td></tr><tr><td>127.032</td><td>2016-02-10</td><td>0.21</td><td>2.22</td><td>128.032</td><td>2020-02-12</td><td>0.14</td><td>2.13</td></tr><tr><td>128.032</td><td>2016-02-01</td><td>0.22</td><td>2.13</td><td>129.032</td><td>2020-02-19</td><td>0.22</td><td>2.22</td></tr><tr><td>129.032</td><td>2016-02-08</td><td>0.15</td><td>2.19</td><td>127.032</td><td>2021-01-22</td><td>0.29</td><td>2.22</td></tr><tr><td>127.032</td><td>2017-02-28</td><td>0.11</td><td>2.14</td><td>128.032</td><td>2021-01-29</td><td>0.29</td><td>2.19</td></tr><tr><td>128.032</td><td>2017-02-19</td><td>0.13</td><td>3.65</td><td>129.032</td><td>2021-02-21</td><td>0.23</td><td>2.13</td></tr></table></body></html>

# 1.3研究方法

1.3.15种遥感指数模型选取5种遥感指数模型对黄河内蒙古段5个子段的河冰、水体进行分类，分别为：

（1）近红外波段反射率阈值法[。水体在近红外波段反射率值低，而冰雪的反射率较高，故适用于冰雪与水体的分类。分类算法如下：

$$
\mathrm { p i x e l } = \left\{ \begin{array} { l l } { \gamma \mathrm { k } \langle \mathrm { \Delta } / \mathrm { k } , \rho _ { \mathrm { N I R } } / 1 0 0 0 0 < \mathrm { t h r e s h o l d } } \\ { \vdots \mathrm { \overline { { n } } j \it { U } } / \mathrm { k } , \rho _ { \mathrm { N I R } } / 1 0 0 0 0 > \mathrm { t h r e s h o l d } } \end{array} \right\}
$$

式中： $\rho _ { \mathrm { N I R } }$ 为近红外波段反射率值;pixel为遥感影像像元点;threshold为阈值，下同。为节省储存空间，USGS发布L8影像数据的像元反射率值均放大注：NDWI表示归一化差异水体指数；NDSI表示归一化差异积雪指数；MNDSI表示改进的归一化差异积雪指数;NDUWI表示归一化未封冻水体指数。下同。

![](images/7c4ad1ed30bacf6981bb0650006cbd209053fcc31d342432ade73bb8153eb46e.jpg)  
图2影像预处理及分类实验流程图  
Fig.2 Flowchart of image preprocessing and classification experiment

10000倍，计算时除以10000将取值范围限制在0到  
1之间以便于与其他指数值进行比较。

(2）归一化差异水体指数(NDWI)阀值法[20]NDWI利用绿色波段与近红外波段构建归一化差异指数，是由McFeeters[20]提出的目前最为常用的陆表水体指数。因河道内并不涉及建筑用地，NDWI的缺点不会影响其对河冰、水体提取。分类算法如下：

式中： $\rho _ { \mathrm { G r e e n } }$ 为绿色波段反射率值,下同。

(3）归一化积雪指数(NDSI)阈值法[2I]。NDSI是由绿色波段与短波红外波段构建的归一化差异指数，此外其与MNDWI指数公式一致。MNDWI由徐涵秋[22]提出，因水体在SWIR波段的反射率值更低，较NDWI可有效区别水体与其他地物。分类算法如下：

式中： $\rho _ { \mathrm { { s w I R } } }$ 为短波红外波段反射率值,下同。

（4）改进的归一化差异积雪指数（MNDSI)[23]MNDSI利用近红外及短波红外波段构建归一化差异指数，而其计算方法与 ${ \mathrm { 0 u m a } }$ 等[23]提出的系列水体指数中的NDWI计算方法一致，该方法对水体边缘提取效果较好。分类算法如下：

(5）归一化差异未封冻水体指数(NDUWI)阈值法[15]。牟献友等[15]提出的NDUWI利用蓝绿波段构建归一化差异指数，并利用该指数对黄河内蒙古段河冰进行监测，

$$
\begin{array} { r } { ( \rho _ { \mathrm { G r e e n } } - \rho _ { \mathrm { B l u e } } ) / ( \rho _ { \mathrm { G r e e n } } + \rho _ { \mathrm { B l u e } } ) > \mathrm { t h r e s h o l d } ] } \\ { , ( \rho _ { \mathrm { G r e e n } } - \rho _ { \mathrm { B l u e } } ) / ( \rho _ { \mathrm { G r e e n } } + \rho _ { \mathrm { B l u e } } ) < \mathrm { t h r e s h o l d } ] } \end{array}
$$

式中： $\rho _ { \mathrm { { B l u e } } }$ 为蓝色波段反射率值。

1.3.2精度评价为比较各算法分类精度，利用总体分类精度 ${ { \left( { { p _ { 0 } } } \right. } }$ ，指对每一个随机样本，所分类的结果与检验数据类型相一致的概率,单位为 $\%$ )和Kap-pa系数( $\kappa$ ，基于混淆矩阵衡量河冰、水体分类精度的指标，介于[-1,1])评价各分类方法的提取精度（ $\dot { p _ { \mathrm { e } } }$ 为中间变量，表示偶然一致性，单位为 $\%$ ),其计算过程见式(6)\~(8)。根据各方法的提取结果列出河冰、水体混淆矩阵(表2)，并分别计算各指数分类

# 表2河冰、水体混淆矩阵

Tab.2 Confusion matrix of river ice and water body   

<html><body><table><tr><td></td><td>河冰真实值</td><td>水体真实值</td></tr><tr><td>河冰预测值</td><td>a11</td><td>α12</td></tr><tr><td>水体预测值</td><td>a21</td><td>a22</td></tr></table></body></html>

的 $p _ { 0 }$ 及 $\kappa$ 。Landis等[24]提出 $\kappa { > } 0 . 8 1$ 时分类几乎完全吻合，但为达到精确提取的目的，选取 $\kappa { > } 0 . 9$ 作为分类达到几乎完全吻合的标准。

$$
p _ { \scriptscriptstyle 0 } = a _ { \scriptscriptstyle 1 \scriptscriptstyle 1 } + a _ { \scriptscriptstyle 2 \scriptscriptstyle 2 } / a _ { \scriptscriptstyle 1 \scriptscriptstyle 1 } + a _ { \scriptscriptstyle 1 \scriptscriptstyle 2 } + a _ { \scriptscriptstyle 2 \scriptscriptstyle 1 } + a _ { \scriptscriptstyle 2 \scriptscriptstyle 2 }
$$

$$
\begin{array} { c } { { p _ { 0 } - u _ { 1 1 } \ \cdot \ u _ { 2 2 ^ { \prime } } u _ { 1 1 } \ \cdot \ u _ { 1 2 } \ \cdot \ u _ { 2 1 } \ \cdot u _ { 2 2 } } } \\ { { } } \\ { { p _ { \mathrm { e } } = \left\{ ( a _ { 1 1 } + a _ { 1 2 } ) \times ( a _ { 1 1 } + a _ { 2 1 } ) + ( a _ { 2 1 } + a _ { 2 2 } ) \right\} \times } } \\ { { ( a _ { 1 2 } + a _ { 2 2 } ) / ( a _ { 1 1 } + a _ { 1 2 } + a _ { 2 1 } + a _ { 2 2 } ) ^ { 2 } } } \\ { { \kappa = \left( p _ { 0 } - p _ { \mathrm { e } } \right) / \left( 1 - p _ { \mathrm { e } } \right) } } \end{array}
$$

# 2结果与分析

# 2.1河冰、水体分类结果

分别采用5种遥感指数模型对黄河内蒙古段河冰、水体信息进行提取，限于篇幅，仅展示2016年和2018年2期影像提取结果(图3、图4)。总体来看，基于NDSI结合GoogleEarth历史高清影像提取到的河道边界排除了土壤及河岸滩地上冰雪等地物，降低了无关地物对于后续总体分类精度及Kappa系数计算精度的影响，从分类效果来看，5种方法分类效果由高到低依次为：归一化未封冻水体指数、归一化差异水体指数、近红外波段反射率值、改进的归一化差异积雪指数、归一化差异积雪指数。在2018年影像中，NDSI较其余4种方法在河冰、水体信息提取上欠佳(图3），误分现象严重;NDWI与NDUWI在遥感影像中分类效果最佳，其中NDUWI总体分类精度和Kappa系数均达到 $9 5 . 0 0 \%$ 和0.90以上。

从5种遥感指数模型所对应的最大(最小)阈值来看(表3)，河冰、水体分类结果与阈值大小并无直接关系，NDSI阈值范围最大，但其分类结果在5个试验区并不稳定，NDWI与NDUWI阀值范围适中，但分类效果在5个试验区内分类结果较好。进一步分析发现，NDUWI在5期遥感影像中的河冰、水体最优区分阈值大体分布于阈值中值附近，如在2016年遥感影像中NDUWI的阈值为(0\~0.46)，最优阈值为0.21。

# 2.2阈值稳定性分析

2.2.1敏感性分析图5给出了试验区5期遥感影像河冰、水体分类精度对于阈值变化的响应。从各期影像中各方法的分类精度来看(表4)，在2020年的2期影像中近红外波段反射率阈值法在相较其他方法展现出最高的提取精度， $p _ { 0 }$ 及 $\kappa$ 分别为 $9 9 . 1 8 \%$ 、0.99及 $9 9 . 9 8 \% , 0 . 9 9 ; 2 0 1 4 . 2 0 1 6$ 年及2020年影像中NDUWI阈值法相较其他方法展现出最高的分类精度， $p _ { 0 }$ 及 $\kappa$ 分别为 $9 9 . 3 8 \% . 9 8 . 9 0 \% \ . 9 9 . 8 0 \%$ 及0.98、$0 . 9 7 , 0 . 9 9$ 。从各方法在各期影像中的分类表现来看，近红外波段反射率阀值法在2018年1期和2020年2期共3期影像中 $p _ { 0 }$ 及 $\kappa$ 均达到并超过了 $9 0 . 0 0 \%$ 及0.90,2014年和2016年影像中 $p _ { 0 }$ 未达到 $9 0 . 0 0 \%$ . $\kappa$ 未超过0.7；与近红外波段反射率阈值法相似，NDWI在前2期影像中分类效果不理想，在后3期影像中 $p _ { 0 }$ 及 $\kappa$ 均达到并超过 $9 0 . 0 0 \%$ 及0.90；NDSI在2014及2016年2期影像中 $p _ { 0 }$ 及 $\kappa$ 均达到并超过 $9 0 . 0 0 \%$ 及0.90，而在后3期影像中 $\kappa$ 出现为0的情况，说明误分、漏分现象严重;MNDSI在5期影像中 $p _ { 0 }$ 及 $\kappa$ 总体保持在 $8 5 . 0 0 \%$ 及0.80左右；NDUWI阀值法在5期遥感影像中的 $p _ { 0 }$ 及 $\kappa$ 均达到并超过了 $9 0 . 0 0 \%$ 及0.90。

![](images/1330b18724a43f1c7a06158eee8590237d56856aea4f7d35031f0d2c71d5ee16.jpg)  
注:po指对每一个随机样本，所分类的结果与检验数据类型相一致的概率; $\kappa$ 是Kappa系数。下同。  
图32016年2月1日5种遥感指数模型河冰、水体分类结果  
Fig.3Classification results of ice-water in five remote sensing models on February 1,2016

进一步分析发现(图5)，当采用适当阈值时，对于上述5种遥感指数模型，所能达到的最高精度从低到高排序依次为：NDSI、MNDSI、近红外波段反射率阈值法、NDWI、NDUWI。此外，从分类精度对阈值变化的响应机制来看，近红外波段反射率阈值法变化幅度最大，即在分类时只要阈值有微小的变动，就会造成提取结果的显著变化，总体精度差值为 $5 0 . 1 0 \%$ ;相比较而言，NDWI阈值变化对分类精度敏感程度较低，选取恰当阈值，便可得到较好的精度；对于其他3种指数模型，阈值对分类精度影响的敏感程度由低到高分别为：NDSI、MNDSI、NDUWI。总体来看，NDUWI对阈值变化的敏感程度较小，总体 $p _ { 0 }$ 及 $\kappa$ 较MNDSI高，在适当阈值内 $p _ { 0 }$ 及 $\kappa$ 更接近$100 \%$ 和1，分类精度高。

![](images/0518607a37f153fca0ef7fa46cdcf0743e8453702eeac44c0f0d1c0960410d0a.jpg)  
干旱区地理  
图42018年2月22日5种遥感指数模型河冰、水体分类结果  
Fig.4 Classfication results of ice-water in five remote sensing models on February 22,201

表35种遥感指数模型对应最大(最小)阈值范围   
Tab.3Maximum (minimum) threshold range of the five remote sensing models   

<html><body><table><tr><td>阈值范围</td><td>近红外波段反射率值</td><td>NDWI</td><td>NDUWI</td><td>NDSI</td><td>MNDSI</td></tr><tr><td>最小</td><td>0~0.37</td><td>0~0.37</td><td>0~0.22</td><td>0~0.86</td><td>-0.85~-0.05</td></tr><tr><td>最大</td><td>0~0.62</td><td>0~0.99</td><td>0~0.78</td><td>0~1.00</td><td>-0.98~0</td></tr></table></body></html>

注：NDWI表示归一化差异水体指数;NDUWI表示归一化未封冻水体指数;NDSI表示归一化差异积雪指数;MNDSI表示改进的归一化差异积雪指数。下同。

综合试验区5期提取结果发现，L8影像不同指数模型在同一研究区内阈值对河冰、水体提取精度的影响程度不同；相同指数模型在不同研究区内所能达到的提取精度不同，阈值对河冰、水体提取精度影响程度也不同；例如，在2016年遥感影像中，当选用一定阈值时，NDUWI精度最高，MNDSI次之；而在2018年影像中，NDUWI在一定阈值内精度最高，近红外波段反射率阈值法次之。

2.2.2不确定性分析基于遥感影像数据对黄河内蒙古段冰水信息提取中，由于主观和客观因素的存在，往往影响到最后的提取精度。例如，NDSI在2014年和2016年2期影像中分类精度较高，而在后3期影像的分类上差强人意。本研究的不确定性来源于以下几个方面：遥感影像的选取、人工目视解

1\~ NIR --NDWI NDSI -MNDSI -- NDUWI(a)2014年1月17日总体分类精度 12108 (b)2014年1月17日Kappa系数edey H0.8 0.60.6 0.40.20.4 A &888 0.0 6-0-0-0-0-0-0-0-0-1.0-0.8-0.6-0.4-0.2 0.0 0.2 0.40.6 0.81.0 -1.0-0.8-0.6-0.4-0.2 0.00.2 0.40.60.81.0阈值 阈值  
%/ 1.0 0.8 1.2 (c)2016年2月1日总体分类精度 xxeddey 18 0.6 1.2 (d)2016年2月1日Kappa系数0.6 0.40.20.40.0-1.0-0.8-0.6-0.4-0.20.0 0.2 0.40.6 0.81.0 -1.0-0.8-0.6-0.4-0.2 0.00.2 0.4 0.6 0.81.0阈值 阈值  
%d 1.0 0.8 1.2 (e)2018年2月22日总体分类精度 eddey 1088 0.6 1.2 (f)2018年2月22日Kappa系数0.40.6 oo88898888 0.20.4 0.0 0-0-0-0-0-0-0-0-0-0-0-1.0-0.8-0.6-0.4-0.20.00.2 0.40.60.81.0 -1.0-0.8-0.6-0.4-0.2 0.0 0.2 0.40.60.81.0阈值 阈值  
%d 1.0 1.2 (g)2020年2月10日总体分类精度 xeddey 1 1.2 (h)2020年2月10日Kappa系数0.8 0.60.40.6 0.2哈合合合合0.4 0.0-1.0-0.8-0.6-0.4-0.2 0.0 0.20.40.60.8 1.0 -1.0-0.8-0.6-0.4-0.20.0 0.2 0.40.6 0.81.0阈值 阈值  
%/@ 1.2 1.0 (i)2020年2月28日总体分类精度 eddey 1088 1.2 (j)2020年2月28日Kappa系数0.8 0.60.40.6 0.2---0-0-0-8-0-0-0-0-0-0-0-0-0--00.4 0.0 HO-Q-O-O HO--O-O-1.0-0.8-0.6-0.4-0.2 0.00.2 0.40.6 0.81.0 -1.0-0.8-0.6-0.4-0.2 0.0 0.2 0.4 0.6 0.81.0阈值 阈值

表45种遥感指数模型对应最高分类精度  
Tab.4 Highest classification accuracy of the remote sensing index models   

<html><body><table><tr><td>分类精度</td><td>近红外波段反射率值</td><td>NDWI</td><td>NDUWI</td><td>NDSI</td><td>MNDSI</td></tr><tr><td>p0/%</td><td>99.12</td><td>98.25</td><td>99.89</td><td>98.34</td><td>99.21</td></tr><tr><td>K</td><td>0.98</td><td>0.98</td><td>0.99</td><td>0.9</td><td>0.98</td></tr></table></body></html>

注 ${ \bf \sigma } : p _ { 0 }$ 指对每一个随机样本，所分类的结果与检验数据类型相一致的概率; $\kappa$ 是Kappa系数。

# 干吴区地理

译经验及研究区环境变化。冬季，由于河道上空雾、云及霾的存在，光学数据在冰情监测中可用数据量有限，每个试验区仅能甄选1\~2景可用于试验的影像[25]。本研究所采用的L8影像均为无云或河道及河道附近无云的影像数据，尽量保证试验数据的质量及可靠性。受客观因素影像，目前尚未引入其他卫星影像作为补充数据源。人工目视解译的误差主要来自混合像元，利用阈值模型计算的栅格数据一般包含多种地物信息，除河道内部少量平滑冰外[26（即静态岸冰，指平均流速低于河道临界流速的水力条件下，在河道内同时沿纵向和横向发展的表面较为光滑的河冰），少有纯净像元，特别是河道边界河冰、水体、积雪以及土壤之间界限难于准确拟定，在人为判别时易影响分类精度[27]。在变化环境方面，大气中水汽、气溶胶及臭氧、河道清沟内水体的含沙量、河岸边界土壤湿度等造成“同谱异质、同质异普"等现象，对边界提取、冰水情监测造成影响[28-29]。为了最大程度上降低河道边界提取中的误判,本研究设计了NDSI结合GoogleEarth历史高清影像对边界提取的流程化提取操作，使得土壤等无关地物最大程度得以排除。

# 3讨论

黄河内蒙古段全长约为 $6 5 0 ~ \mathrm { k m }$ ，东西跨度较大，整体呈“几"字形分布，野外冰情受到限制，基于遥感影像在冰情监测方面效果较好[18]。同时，黄河冰情信息监测受限于数据的时相分辨率以及天气条件，因此，常在研究中出现某一稳封期数据缺失的情况[6]。与传统的大尺度海冰(湖冰)冰情监测不同，由于黄河自身的泥沙特性以及河道淤积蔓延情况，本文研究基于L8影像,综合GoogleEarth历史高清影像和NDSI首先排除了河道外土壤、建筑及植被等无关地物，仅保留冰水信息以保证被研究像元的真实性，解决了河道边界河冰、水体信息难以识别的问题[30-33] O

本研究发现，遥感影像选取、河道上空气象条件以及河流水质条件是影响冰情监测提取精度的重要因素。在数据选取方面，由于冬季河道上空雾、云及霾的存在，不同指数分类阈值难以拟定，存在较大阈值波动情况，故应选用稳封期（即河冰不再沿河道横向发展)无云、雪且气象条件良好时期的卫星影像[34]。在冰水信息提取实验设计方面，NDSI虽不能精确区分河道内部冰情、水情信息，但该指数可结合历史高清影像作为分类化流程实验的第一步，即提取河道边界，排除研究对象外的无关地物，使真实河冰、水体像元尽最大限度得以保留[9]。

黄河内蒙古段河冰信息提取与前人大尺度海冰(湖冰)提取的研究相比，既具统一性，也具差异性。例如，海勃湾库区是典型的库区型河段，水流流速相对较小，河冰信息提取方法同海冰(湖冰)提取大体相同；巴彦高勒河段则为典型的游荡型河段，河段淤积严重，河冰漫滩现象严重，河冰信息提取受不确定因素增加。5种遥感指数模型在黄河内蒙古段冰情信息提取精度对阈值的响应不尽相同，近红外波段反射率阈值法提取精度对阈值响应较为敏感，即阈值的少量波动就会对提取精度产生较大影响；NDSI、MNDSI以及NDWI在流程化实验中提取精度对阈值响应适中，但精度略小于近红外波段反射率阈值法；NDUWI在多时相、多河段研究中表现出较高提取精度，同时发现其河冰、水体最优区分阈值大体分布于阈值中值附近。同时发现，凹岸侧模型指数值略大于凸岸侧，这可能与弯道处离心力的存在导致凹岸侧堆冰增加有关，故河道凹岸侧应加强堤岸防护[35-36]

黄河冰情遥感监测不仅受数据质量、气象条件以及光照等的影响，并且也受水位，流量以及上游水库防凌调度的影响[37-39]。例如：气温越高,河冰分布范围越小，稳封期清沟所占比例越大，已发生凌汛灾害；水位越高，河道与大气表面接触面积就越大，河冰冻结所需要的热量条件也随之增大，河冰分布范围增大，河冰漫堤风险随之增加等[40]。因此，在未来研究中，如何在模型中结合气象条件、水利条件等数据以及自动化提取冰水像元，同时结合水文站野外观测资料做对比分析，是一个值得考虑的方向，这可能会进一步提高凌汛期黄河河冰、水体情监测的时效性和准确性。

# 4结论

黄河内蒙古段河势复杂、地形地貌多样，基于遥感影像模型监测河冰、水体情分布不易获取且各指数模型的适用性尚未有人做出评估。针对上述问题，本文运用L8影像数据，通过设计实验方案提取河道边界，利用近红外波段反射率阈值、NDWI、NDSI、MNDSI及NDUWI5种遥感模型对研究区河冰、水体分布进行监测，进而分析各指数的阈值稳定性及不确定性，得出以下结论：

（1）基于NDSI与GoogleEarth历史高清影像结合的二次排除无关地物的实验方案在河冰、水体情监测时能较好的去除周围无关地物。

(2）NDUWI在黄河内蒙古段影像中的分类精度均达到 $9 0 . 0 0 \%$ 及0.90以上，总体分类精度较高，适用性较强，且NDUWI在5期遥感影像中的河冰、水体最优区分阈值大体分布于阈值中值附近；但NDUWI无法将土壤与河冰进行有效区分，使用前应先提取河道矢量边界，排除无关地物。

# 参考文献(References)

[1]李超,李畅游,李红芳.黄河(内蒙古段)弯道卡冰过程及数值模 拟研究[J].水力发电学报,2015,34(10):103-110.[Li Chao,Li Changyou,Li Hongfang.Study and simulation on ice jam process in river bends for Inner Mongolia reach of the Yellow River[J]. Journal of Hydroelectric Engineering,2015,34(10):103-110.]   
[2]高霈生,靳国厚.中国北方寒冷地区河冰灾害调查与分析[J].中 国水利水电科学研究院学报,2003,1(2):82-87.[Gao Peisheng, Jin Guohou.Investigation and analysis of river ice disaster in cold regions of North China[J]. Journal of China Institute of Water Resources and Hydropower Research,2003,1(2): 82-87.]   
[3]Jeffries M O,Morris K,Kozlenko N.Ice characteristics and processes,and remote sensing[J].Remote Sensing in Northern Hydrology Measuring Environmental Change,2Oo5,163: 63-90.   
[4]李浩杰,李弘毅,王建,等.河冰遥感监测研究进展[J].地球科学 进展,2020,35(10):1041-1051.[Li Haojie,Li Hongyi,Wang Jian,et al.Advances in remote sensing of river ice[J].Advances in Earth Science,2020,35(10): 1041-1051.]   
[5]杨中华,王卫东,马浩录.“四星三源"模式监测黄河凌汛的研究 与实践[J].科技导报,2006(4):64-67.[Yang Zhonghua,Wang Weidong,Ma Haolu.Monitoring ice flood of Yellow River with “four-satelite and three-resource”model[J]. Science & Technology Review,2006(4): 64-67.]   
[6]赵水霞,李畅游,李超,等.黄河什四份子弯道河冰生消及冰塞 形成过程分析[J].水利学报,2017,48(3):351-358.[Zhao Shuixia,Li Changyou,Li Chao,et al. Processes of river ice and ice-jam formation in Shensifenzi Bend of the Yellow River[J].Journal of Hydraulic Engineering,2017,48(3): 351-358.]   
[7]Chu T,Lindenschmidt K E.Integration of space-borne and air-borne data in monitoring river ice processes in the Slave River, Canada [J]. Remote Sensing of Environment,2016,181: 65-81.   
[8]Chaouch N,Temimi M,Romanov P,et al.An automated algorithm for river ice monitoring over the Susquehanna River using the MODIS data[J]. Hydrological Processes,2014,28(1): 62-73.   
[9]Dozier J. Spectral signature of alpine snow cover from the LANDSAT thematic mapper[J]. Remote Sensing of Environment,1989, 45: 9-22.   
[10] 李志杰,王宁练,陈安安,等.1993—2016年喀喇昆仑山什约克 流域冰川变化遥感监测[J].冰川冻土,2019,41(4):770-782. [Li Zhijie,Wang Ninglian,Chen An’an,et al. Remotesening monitoring of glacier changes in Shyok Basin of the Karakoram Mountains,993—2016[J]. JournalofGlaciologyand Geocrolo gy,2019,41(4): 770-782.]   
[11]高永鹏,姚晓军,刘时银,等.1956—2017年河西内流区冰川资 源时空变化特征[J].冰川冻土,2019,41(6):1313-1325.[Gao Yongpeng,Yao Xiaojun,Liu Shiyin,et al.Spatial-temporal variation of glacier resources in the Hexi interior from 1956 to 2017[J]. Journal of Glaciologyand Geocryology,2019,41(6): 1313-1325.]   
[12] 姚晓军,李龙,赵军,等.近10年来可可西里地区主要湖泊冰情 时空变化[J].地理学报,2015,70(7): 1114-1124.[Yao Xiaojun, Li Long, Zhao Jun,et al. Spatial-temporal variations of lake ice in the Hoh Xil region from 2000 to 2011[J].Acta Geographica Sinica,2015, 70(7): 1114-1124. ]   
[13] 陈鹏,王勇,张青,等.基于FY-3D/MERSI-ⅡI归一化积雪指数 和 MOD10A1的精度对比分析[J].干旱区地理,2020,43(2): 434-439.[Chen Peng,Wang Yong, Zhang Qing, et al. Comparison of the accuracy of normalized snow cover indices between FY-3D/ MERSI-II ndMODS[J].Aridand Geogaph,2020,43(2)434 439.]   
[14]Li HJ,LiHY,Wang J,etal.Monitoring high-altitude river ice distribution at the basin scale in the northeastern Tibetan Plateau from a Landsat time-series spanning 1999-2018[J]. Remote Sensing of Environment, 2020,247: 111915,doi: 10.1016/j.rse.2020. 111915.   
[15] 牟献友,宝山童,张宝森,等.基于遥感影像分析的1989—2019 年黄河内蒙古段河冰时空变化[J].冰川冻土,doi:10.7522/j. issn.1000-0240.2020.058.[Mou XianouBao Shantong,Zhang Baosen,et al.A satelite-based analysis on spatial-temporal distribution and variation of river ice in Inner Mongolia reach from 1989 to 2O19 based on remote sensing image interpretation[J]. Journal of Glaciology and Geocryology,doi:10.7522/j.issn.1000- 0240.2020.0058.]   
[16]勾鹏,叶庆华,魏秋方.2000—2013年西藏纳木错湖冰变化及 其影响因素[J].地理科学进展,2015,34(10):1241-1249.[Gou Peng,Ye Qinghua,Wei Qiufang.Lake ice change at the Nam Co Lake on the Tibetan Plateau during 2000—2013 and influencing factors[J].Progressin Geography,2015,34(10):1241-1249.]   
[17] 全栋,李超,路新川,等.黄河干流头道拐河段凌汛期小流量过 程变化及其影响因素研究[J].冰川冻土,2020,42(2):620-628. [Quan Dong,Li Chao,Lu Xinchuan,et al.A study of low discharge process and impacting factors of Toudaoguai reach in Inner

# 干吴区地理

干星 Mongolia of the Yellow River during ice flood period[J].Journal of Glaciology and Geocryology,2020,42(2): 620-628.]   
[18] 罗红春,冀鸿兰,郜国明,等.黄河什四份子弯道冰期水流及冰 塞特征研究[J].水利学报,2020,51(9):1089-1100.[Luo Hongchun, Ji Honglan,Gao Guoming,et al. Study on the characteristics offlow and icejam in Shisifenzi bend intheYellow River during the freeze-up period[J]. Journal of Hydraulic Engineering,2020,51 (9): 1089-1100.]   
[19]胡一三.黄河宁夏内蒙古河段河道整治[J].水利规划与设计, 2010(5):1-4.[Hu Yisan. River regulation of the Inner Mongolia reach of the Yellow River in Ningxia[J].Water Resources Planning and Design, 2010(5): 1-4.]   
[20]McFeeters S K.The use of the normalized difference water index (NDWI) in the delineation of open water features[J]. International Journal of Remote Sensing,1996,17(7): 1425-1432.   
[21]Hall D K, Riggs G A, Salomonson V V,et al. MODIS snow-cover products[J]. Remote Sensing of Environment,2002,83(1-2): 181-194.   
[22] 徐涵秋.利用改进的归一化差异水体指数(MNDWI)提取水体信 息的研究[J].遥感学报,2005,9(5):589-595.[Xu Hanqiu.A study on information extraction of water body with the modified normalized difference water index (MNDWI)[J]. Journal of Remote Sensing,2005,9(5): 589-595.]   
[23]Ouma YO,TateishiR.A waterindex forrapid mapping of shoreline changes of five east African Rift Valley lakes: An empirical analysis using Landsat TM and ETM $^ +$ data[J]. International Journal of Remote Sensing,2006,27(15): 3153-3181.   
[24] Landis JR, Koch G G. The measurement of observer agreement for categorical data[J]. Biometrics,1977,33(1): 159-174.   
[25] Claude C R, Bernier M, Gauthier Y,et al.Remote sensing of lake and river ice[J].Remote Sensing of the Cryosphere,2015,12: 273-306.   
[26] 李超.黄河(内蒙古段)河冰生消演变特性及数值模拟研究[D]. 呼和浩特:内蒙古农业大学,2015.[Li Chao.Study on characteristics river ice evolution and numerical simulation of the Yellow River (Inner Mongolia reach)[D].Hohhot: Inner Mongolia Agricultural University,2015.]   
[27] 田园,张雪芹,孙瑞.基于多源、多时相遥感影像的高原湖泊提 取及其不确定性——以西藏羊卓雍错流域为例[J].冰川冻土, 2012,34(3): 563-572.[Tian Yuan,Zhang Xueqin,Sun Rui.Extracting alpine lake information based on multi-source and multitemporal satelite images and itsuncertainty analysis:A case study in Yamzhog Yumco Basin,south Tibet[J]. Journal of Glaciology and Geocryology,2012,34(3): 563-572.]   
[28]Jonsson P,Eklundh L.Seasonality extraction by function fitting to time-series of satelite sensor data[J]. IEEE Transactions on Geoscience and Remote Sensing,2002, 40(8): 1824-1832.   
[29] Medina C, Gomez-Enri J,Alonso J,et al. Water volume variations in Lake Izabal (Guatemala) from in situ measurements and ENVISAT radar altimeter (RA-2) and advanced synthetic aperture radar (ASAR) data products[J]. Journal of Hydrology,2010,382(1- 4): 34-48.   
[30] 秦启勇,李雪梅,张博,等.2000—2019年赛里木湖湖冰物候特 征变化[J/OL].干旱区地理.[2021-09-26]. htp://kns.cnki.net/kcms/detail/65.1103.X.20210603.1505.004.html．[QinQiyong，Li Xuemei, Zhang Bo,et al. Change of ice phenology in the Sayram Lake from 2000 to 2019[J/OL].Arid Land Geography. [2021-09- 26].http://kns.cnki.net/kcms/detail/65.1103.X.20210603.1505.004. html. ]   
[31] 高永鹏,姚晓军,刘时银,等.冰川冰储量计算方法及发展趋势 [J].干旱区地理,2018,41(6):1204-1213.[Gao Yongpeng,Yao Xiaojun,Liu Shiyin,etal. Methods and future trendof ice volume calculation of glacier[J]. Arid Land Geography,2018,41(6): 1204- 1213.]   
[32] 庞毓雯,黄雨馨,巩志,等.基于多光谱遥感的湖冰物候监测方 法研究进展[J].海洋湖沼通报,2020(2):90-99.[Pang Yuwen, Huang Yuxin,Gong Zhi,et al.Advances in phenological monitoring of lake ice based on multi-spectral remote sensing[J]. Transactions of Oceanology and Limnology,2020(2): 90-99.]   
[33] 魏秋方,叶庆华.湖冰遥感监测方法综述[J].地理科学进展, 2010,29(7): 803-810.[Wei Qiufang, Ye Qinghua.Review of lake ice monitoring by remote sensing[J]. Progress in Geography,2010, 29(7): 803-810.]   
[34]Ulaby FT, Moore R K,Fung A K. Microwave remote sensing of alpine snow[J]. Institute of Electrical and Electronics Engineering, 2007,12(7): 1223-1227.   
[35] 许健,王掌权,任建威,等.原状黄土冻融过程渗透特性试验研 究[J].水利学报,2016,47(9):1208-1217.[XuJian,Wang Zhangquan, Ren Jianwei,et al. Experimental research on permeability of undisturbed loessduring the freeze-thaw process[J]. Journalof Hydraulic Engineering,2016,47(9): 1208-1217.]   
[36]王延贵,匡尚富.河岸崩塌类型与崩塌模式的研究[J].泥沙研 究,2014,12(1): 13-20.[Wang Yangui, Kuang Shangfu. Study of types and collapse modes of bank failures[J]. Journal of Sediment Research,2014,12(1): 13-20.]   
[37] 可素娟,吕光坊,任志远.黄河巴彦高勒河段冰塞机理研究[J]. 水利学报,200(7): 66-69.[Ke Sujuan,Lu Guangyin,Ren Zhiyuan. Study on mechanism of ice jam formation in Bayangaole section of Yellow River[J]. Journal of Hydraulic Engineering,2000 (7): 66-69.]   
[38] 秦毅,张晓芳,王凤龙,等.黄河内蒙古河段冲淤演变及其影响 因素[J].地理学报,2011,66(3):324-330.[Qin Yi, Zhang Xiaofang,Wang Fenglong,et al. Scour and silting evolution and its influencing factors in Inner Mongolia reach[J].Acta Geographica Sinica,2011,66(3): 324-330.]   
[39] 康玲玲,王云璋,陈发中,等.黄河上游宁蒙河段气温变化对凌 情影响的分析[J].冰川冻土,2001,23(3):318-322.[Kang Lingling,Wang Yunzhang, Chen Fazhong,et al. Analysis on effect of air temperature on ice jam floods at Ningmeng reaches of the Yellow River[J]. Journal of Glaciology and Geocryology,2001,23(3):

# Ice-water classification in Inner Mongolia reach of the Yellow River based on remote sensing images

ZHAI Yongguang'， ZHANG Xin'， JI Honglan'， MOU Xianyou’， ZHANG Baosen² (1.CollgeofWaterConservancyandCivilEngineering,InerongoliaAgriculturalUniversity,HohotOOl8,Innerogolia China; 2.Yellow River Institute of Hydraulic Research, Zhengzhou 45OoO3,Henan, China)

Abstract:Timelydeliveryof detailed informationon thespatial distributionof riverice during ice-flood season is highly valuable for predicting,and improving communication on,ice disaster. Remote sensing technology provides akey method for obtaining the spatial distribution of river ice.However, the large amount of suspended sediment in the Yellow River represents a challenge to high-precision discrimination between ice and water based on remote sensing technology.Taking the Inner Mongolia reach of the Yellow River as an example,this study compares and evaluates the performance offive indices in the clasification of river ice and water: nar-infrared reflectance;normalized difference water index (NDWI)； normalized difference snow index (NDSI)； improved normalized snow index (MNDSI)； and normalized diference unfrozen water index (NDUWI).The overall clasification accuracyand Kappa coeficient (a measure of reliability) were calculated for each index,and the threshold stability of each index was analyzed.The results show that NDUWI achieves the highest accuracy and reliability (Kappa coefficient） in each studied subregion. The overall classfication accuracy and Kappa coefficient of NDUWI are more than $9 0 . 0 \%$ and 0.90,respectively,and the optimal discrimination threshold between river iceand ice-free water is close to the median value.These results can providea basis forthe selection of ice monitoring methods and optimization of ice-blasting locations on the Yellow River during ice-flood season.

Key Words: river ice；remote sensing index;threshold stability；uncertainty；Landsat 8； Inner Mongolia reach of the Yellow River