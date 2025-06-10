# 面向子流域单元的典型黄土地貌分类研究

王乐¹²，周毅²，李阳1,2

1.陕西师范大学地理科学与旅游学院,陕西 西安710119；2．地理学国家级实验教学示范中心,陕西 西安71011摘要：基于格网DEM的数字地貌形态类型自动划分是当前地貌研究的热点。根据基本分析单元的粒度大小,可将现有的分类方法划分为以栅格为分析单元和不规则坡面多边形为分析单元。然而，上述2种方法都无可避免地存在分类结果中地貌实体不完整性的问题。本文将分析单元提升至小流域级别，提出面向“细胞”级的微小尺度的子流域为分析对象的分类思想,利用GIS 空间分析方法,构建子流域地理属性数据库,依据研究区已有的地貌资料,遴选出高程、起伏度、平均坡度、坡谱偏度4个核心分类指标,采用层次分类法,设定相应的地形因子阈值,将陕西省铜川市耀州区划分为:河漫滩、黄土残塬、黄土台塬、陡坡冲沟、垛峁状丘陵沟壑、石质小起伏平缓中山、石质小起伏陡峭中山以及水域等8大类型。分类结果最大程度保证了地貌实体的相对完整性，与用GPS 进行的实地采样观测结果对比分析表明,该方案的分类精度达到 $8 8 . 1 9 \%$ ，可望成为基于面向子流域单元进行数字地貌分类研究的有益探索。

关键词：子流域；地貌分类；流域分割；格网DEM；铜川；陕西

地貌类型的划分研究一直以来都是地理学的重要命题之一。近年来，随着现代数字高程模型（DEM）、高分辨率遥感影像数据的出现，为数字地貌类型的划分提供了诸多新的研究方法和研究思路。地貌作为自然地理环境组成要素之一，它对其他要素及地理环境整体特征有着广泛而深刻的影响。不同尺度下的地貌形态类型划分研究，不仅是认识自然环境空间分异的基础,同时也是规划、布局人类生存区域，使之达到人与环境和谐统一的基本依据。但是，基于不同尺度所进行的地貌形态类型划分，会极大地影响到分类结果和分类精度。因此，开展黄土地貌类型的划分研究具有十分重要的现实意义[1-5] O

根据基本分析单元的粒度大小，可将基于栅格DEM数据进行地貌分类的研究归纳为2种类型，分别代表着2种不同的分析思想。最基本也最常用的是以规则格网(grid)为分析单元的思想。其基本思路是将具有相似地理属性的栅格单元聚类,从而实现地貌形态类型划分。该方法所面临的最大问题是分类结果不能保证地理实体的完整性[6-10];其次，是以不规则坡面多边形（polygon）为分析单元的思想。该基本思想认为，连续的地表是由不可微的、平面多边形构成，根据多边形坡度差异，实现地貌形态类型的划分[11-15]。然而由于地形坡面剖分的不确定问题，导致分类模型的结果与实际地表存在差异。

我国学者也在基于DEM进行地貌形态类型自动划分方面进行了有益尝试。Cheng等[2]对于我国数字地貌分类系统的结构和内容做相应研究。李炳元等基于DEM利用海拔高程指标实现了我国全域尺度下的地貌分类。刘德林等[利用DEM数据与遥感图像相结合的方法，建立了黄土小流域地貌分类体系。肖飞等[1利用 SRTM数据,实现了山体单元的自动提取。刘爱利等[1基于 $1 : 1 \ 0 0 0 \ 0 0 0$ 的$1 ~ \mathrm { k m }$ 分辨率数字高程模型，利用监督、非监督分类的方法，实现我国全域范围内地貌制图等。由于我国地形情况复杂，存在众多走向多变的大型山体，这就使得对地貌分类指标测算范围问题还存在较大分歧[9,16],特别是利用传统的规则分析窗口计算起伏度指标具有极大的不确定性(2,16-18]。基于这种现状，在充分考虑地形分类指标特性，尤其是地形起伏度等对于分析尺度极为敏感的指标的稳定性基础上[16,18],本文提出了基于高分辨率 DEM 数据,采用面向“细胞”级的微小粒度的子流域为分析对象的分类思想[19-23],将微小尺度的子流域单元作为基本地形划分单元，结合多地形指标的复合分类方法，实现黄土高原复杂地貌区分类，为今后类似尺度范围下的地貌形态类型划分提供方法借鉴。

子流域作为区域地貌的“细胞”，是地貌系统中自然存在的、相对封闭独立的地理单元，具有地貌形态类型的相对均一性、统一性和完整性等特征。以子流域单元为基本分类单位，不仅可以保证起伏度等区域性地形指标求算的合理性和有效性[16,18],同时能够凸显分类结果边界与自然地理边界吻合等优势，这也是提出本方法的立意和出发点。

# 研究区域与数据

本文选择陕西省铜川市耀州区作为研究区域。该区域地处鄂尔多斯地台与渭河地堑之间，基本地貌形态类型包括石质山地、高原丘陵沟壑、川道台塬，地貌复杂，类型丰富。该区介于 $3 4 ^ { \circ } 5 0 ^ { \prime } \sim 3 5 ^ { \circ } 2 0 ^ { \prime }$ $\mathrm { ~ N ~ } _ { \mathrm { { s } } } 1 0 8 ^ { \circ } 3 4 ^ { \prime } \sim 1 0 9 ^ { \circ } 0 6 ^ { \prime } \mathrm { { E } }$ ,属暖温带大陆性半干旱气候区，光热充足，降水量少，南北气候差异较大，日照百分率达 $5 3 \%$ ,年平均气温 $1 2 . 3 0 \mathrm { ~ \textdegree C }$ 。地势西北高，东南低，高程起伏为 $5 4 3 \sim 1 ~ 7 1 2 . 5 0 ~ \mathrm { ~ m ~ }$ ，总面积为$1 ~ 6 1 3 . 6 4 ~ \mathrm { k m } ^ { 2 }$ ,平均沟壑密度 $1 . 1 9 \ \mathrm { k m } \cdot \mathrm { k m } ^ { - 2 }$ ,侵蚀模数达 $1 ~ 5 0 2 ~ \mathrm { t } \cdot \mathrm { k m } ^ { - 2 }$ ,水土流失面积占总土地面积的 $7 8 . 6 0 \%$ ，是黄河中游水土流失比较严重的地区之一。

实验所用数据为陕西省测绘局生产的 $2 5 \mathrm { ~ m ~ }$ 分辨率(1:50000)DEM，制作过程严格依照国家测绘局关于建立数字高程模型的标准进行。DEM数据采用高斯－克吕格投影，1980国家大地坐标系，1985高程坐标基准。此外，河网水系数据由DEM自动生成，根据2005年陕西省测绘地理信息局所制DOM(1:50000)校正，满足分类精度要求。实验所需软件平台为ESRI公司的ArcGIS10.4系统。图1利用DEM生成的耀州区的位置图和地貌晕渲图。

![](images/08afc33ee37600dc414789b37e6ffd90431c21550ac9f9595cffb55454f7e37d.jpg)  
图1耀州区位置及地貌晕渲图  
Fig.1Location and hillshade map of the study area

# 2地貌分类方案

# 2.1 基本思路

分类的核心处理过程包括3个步骤。第一步，利用数字地形分析方法将研究区域地形尽可能的“细胞”化，即将其分割为内部地理属性均一的子流域单元，实现连续地表的子流域级离散化;第二步，利用GIS空间分析方法建立子流域地理属性库；第三步，利用复合阈值分析法，以子流域综合地理属性为依据，实现流域类型的归类，从而实现研究区地貌

形态类型的自动分割。

# 2.2地貌分类方案

耀州区地貌属过渡类型，地貌复杂多样。故而有必要建立具有科学性、系统性、逻辑性的分类方案，根据该方案可进行耀州区主体地貌形态类型的划分。参考西北大学黄土高原研究中心耀县地貌研究资料[24-25],制作耀州区地貌分类系统方案(表1)。

# 2.3分类指标选取

本着系统性、可实现性以及指标间的相对独立性原则，参考前人在地貌分类研究中所使用的分类因子[3.9],顾及耀州区地貌形态类型的典型性以及在流域尺度下指标选取的合理性(9,26],依据耀州地貌分类方案，本文选取了绝对高程、起伏度、平均坡度、坡谱偏度作为分类的主要指标，由于河漫滩地区和台塬区坡度差异不大，而后者距离河道均在200m 以上，故而使用距河道距离作为区分判别指标。

绝对高程指标是经典数字地貌分类的核心指标，也是DEM数据所包含的最基本的地理信息。根据1987年制定的中国1:1000000地貌图图例系统标准，子流域高程指标是选取流域内最高点高程赋值给流域斑块属性作为分类依据（图2a）。

高程起伏度是区分地表突出物高差的重要指标[16],在诸多地貌自动分类研究中都有使用。然而，传统的窗口分析法所提取起伏度指标存在不确定性。如果分析窗口过大，在滤波时会漏掉规模较小，但却对地貌起控制作用的地理实体;如果分析窗口过小，则不能保证滤波窗口可同时覆盖主山脉的脊部与谷部，导致计算出的起伏度不能客观地反映地理实体的实际高差[16]。本文以子流域单元为分析最小粒度，可以克服窗口分析法的上述不足，使分类结果更加客观（图2b）。

表1耀州区地貌形态分类方案   
Tab.1 Classification scheme of topographic features in Yaozhou District   

<html><body><table><tr><td>地貌形态类型</td><td></td><td>平均坡度</td><td>高程</td><td>地貌特征</td><td>土地利用类型</td></tr><tr><td rowspan="5">山 地 峭中山 谷 区</td><td>黄土覆盖小起伏陡>18°，谷底地10°>1250m，起伏高度在 ~18°</td><td></td><td>200~500 m</td><td>位于该区北部，面积占总面积的针阔叶林为主,山间盆地、坪 56.20%左右；山高谷深,河谷下切严地上有农耕区,分布有少量草 重；为该区主要河流发源地;有石质基甸 岩出露</td><td></td></tr><tr><td>缓中山</td><td>坡超过35°</td><td>200~500 m</td><td>黄土覆盖小起伏平 10°~18°,单斜背>1250m,起伏高度在 位于该区东北部;多单面山、单斜脊,朝 旱地农耕、城镇用地为主,宜 向河谷面,坡度平缓</td><td>林宜牧</td></tr><tr><td>黄土覆盖低山'</td><td></td><td>高度200~1000m，起伏 高度在 200~500 m</td><td></td><td></td></tr><tr><td>操峁状丘陵沟壑</td><td>及沟底有少量在100~300m</td><td></td><td>15°~30,垛顶 950~1250m,起伏高度 位于该区中部;黄土覆盖,切、冲沟发 垛顶部多梯田,陡峭坡面宜 育，以璨、峁、丘为主;水土流失严重,土林、宜草</td><td></td></tr><tr><td>黄土残塬</td><td>10°以下坪地 <8°</td><td></td><td>壤侵蚀剧烈 950~1250m,起伏高度位于该区中部，穿插在丘陵沟壑区之旱地农耕区,果木、经济林</td><td></td></tr><tr><td rowspan="6">道 台 区</td><td></td><td></td><td>在150m</td><td>间;塬面略向东南倾斜，面积小于15 km²</td><td></td></tr><tr><td>水域 川黄土台塬</td><td>1°~8°</td><td></td><td>处于沮河中游,面积约1.3 km² <950 m,起伏高度在100 位于该区南部;塬面平坦,西北稍高,塬 旱地农耕区,果木、经济林</td><td></td></tr><tr><td>塬陡坡冲沟</td><td></td><td>m</td><td>间洼地星罗棋布;面积大于25 km² 大部分坡度≥25°<950m,起伏高度在120 南部,台塬四周;多有常年流水,走向为水土流失区,宜林宜草</td><td></td></tr><tr><td>河漫滩地</td><td><8°</td><td>~200 m <950m，起伏高度在50沮河中游，滩面平坦，呈三角状</td><td>西北东南走向</td><td>区治所在，城镇用地，旱地农</td></tr><tr><td></td><td></td><td>m</td><td></td><td>耕地</td></tr></table></body></html>

主：1表示该区域中不存在;2为桃曲坡水库所在地，可利用地形图进行勾绘(据张哲夫1990）

![](images/25d8246caa1b7999424b1fbe79385c585c9f589ad8ee877fdf6f075e2a3ef50f.jpg)  
图2小流域各地理属性空间分布  
Fig.2Spatial distribution of geographic attributes in sub-watersheds

平均坡度指标是绝大多数经典地貌分类方法中使用的核心指标，主要用来区分陡坡冲沟与黄土台塬。坡谱偏度(skewness)是区域坡度统计数据分布不对称性的有效指标。其公式为：

$$
{ \mathrm { s k e w n e s s } } = { \sqrt { \frac { 1 } { 6 n } } } \sum _ { i = 1 } ^ { n } \left( { \frac { P _ { i } - { \bar { P } } } { \sigma } } \right) ^ { 3 } 
$$

式中： $n$ 为分级数; $\boldsymbol { P } _ { i }$ 为每一级别坡度的频率; $\bar { P }$ 为平均频率; $\sigma$ 为标准差。当坡谱是 $3 ^ { \circ }$ 等差分级时， $n$ 为30。该指标和平均坡度联合使用，可以将平均坡度相近但存在深切沟谷的流域与平缓地表流域分离[16]。图2c、2d分别为平均坡度、坡谱偏度的分布图。

地表曲率也是地貌分类的重要指标，本文却并没有采用。主要是因为地表曲率是衡量坡面局部形态指标，坡度的二阶导数，如将其应用为衡量流域地形属性的整体指标，则失去曲率指标的本来物理意义，从而影响分类结果的可信度。

# 2.4技术流程及阈值设定

大地构造运动对地表形态起控制性作用，其直接结果导致地貌形态类型间绝对高程的差异。因此，绝对高程指标应作为一级地貌形态类型（山地、丘陵、台地或平原)划分的主要依据。对于断裂活动、流水侵蚀等对地表的修饰作用，以及地壳隆升程度的空间分异所造成的地形起伏差异，均可通过二级地貌形态类型划分指标—起伏度指标实现[16]作为局部地形属性指标的坡度及坡谱偏度指标，是精细地貌形态类型划分的核心指标，在本文方法中，作为第三级分类指标使用。

鉴于此，针对耀州地区，利用子流域分割的方法进行地貌形态类型划分，具体操作如下：

首先,创建子流域地理数据库。以O'Callaghan等[27]所设计的汇流算法提取汇水流域。子流域分割所参照的上游汇流累积阈值是通过从小到大，50、75、100、125、150等以25为间隔递增的多次反复实验获得[28],其标准是所分割出的子流域能够涵盖区域内山体的谷和脊，同时又保证分割单元面积尽可能小。子流域划分比对实验结果发现，当汇流累积阈值为300时，所分割的子流域能兼具地貌类型的完整性与形态的单一性特征。根据流域分割得到的4016个子流域单元，制作矢量子流域图层，为后续子流域聚类分割的数据基础。然后，利用GIS空间分析功能，获取该区域的坡度图层、河网水系图层，再基于子流域矢量数据，利用区域统计分析操作，分别获取子流域绝对高程、相对起伏、平均坡度、坡谱偏度以及距河网距离等地理属性，并将上述各属性编辑导入子流域地理数据库。至此，进行地貌分类的数据预处理阶段完成。

其次，将地貌按照层次分类进行。通过借鉴西北大学黄土高原研究中心耀县地貌研究资料而制作出的耀州区地貌分类系统方案，结合基于汇流累积量的阈值取值而划分的4016个子流域单元，将具有相似地理属性的地貌形态，依据选取出的高程、起伏度、平均坡度和坡谱偏度等因子的层次，按先后顺序依次进行地貌形态类型的划分。

最后，具体的实现过程表现为：以耀州地貌分类方案中的绝对高程值 $9 5 0 \mathrm { ~ m ~ } , 1 \ 2 5 0 \mathrm { ~ m ~ }$ 作为一级地貌形态类型分界点，将耀州区地貌分为3部分：北部石质山地区、中部黄土丘陵沟壑区以及南部台塬川道区。分类后地貌大区类型中会出现飞地子流域现象，依照改动面积不超过 $3 \%$ 的原则，参照实际地貌将小面积飞地子流域去除。随后分别在3个大区中，按照地形起伏度、平均坡度次序，实现每个大区中二级、三级地貌形态类型的划分，具体分类值及流程如图3所示。其中，对于黄土丘陵沟壑区残塬的提取，需要评价子流域内平均坡度和坡谱偏度2个指标，以平均坡度小于 $8 ^ { \circ }$ 、坡谱偏度 $0 . 2 7 \sim 1 . 5 0 \$ 为依据，将含有切沟的塬面流域和平整塬面分开，以平整塬面流域为种子，使用区域增长算法，获得平整的塬面区域。然后以塬面区域为种子，按照坡度小于 $8 ^ { \circ }$ 的原则，使用区域增长算法，获取完整塬面。黄土台塬的提取方法与此相同。对于河漫滩的提取需借助河流数据。具体判别条件是坡度小于 $8 ^ { \circ }$ ，并且与河流相交，与河流 $2 ~ \mathrm { k m }$ 缓冲区有 $70 \%$ 以上共有区域。利用该方案对耀州区地貌形态类型的划分结果如图4所示。

# 2.5 精度评价

本研究采用实地多点考察验证的方法检验分类结果。为此，在2018年7月，笔者与所在课题组成员利用GPS在耀州地区实地随机标定了127个观察点的地貌形态类型，采样点位置如图5所示。经过对比，有112个观察点地貌形态类型与分类结果一致,分类准确率达到 $8 8 . 1 9 \%$ ，显示了较好的分类结果。与分类结果差异较大的15个观察点，均靠近自动分区边界。造成这一结果的主要原因是由于流域分割时使用统一分割阈值，导致在地貌形态类型起伏较小区域出现斑块面积较大的子流域，增大了分析粒度。在进一步的研究中，应考虑设计自适应的子流域分割算法，提高DEM的格网分辨率，同时结合专家知识进行修正，可望进一步增加分类的精确性。

![](images/66cb32e2f32db6732436e790c86a46d3681aaa32a24a0a75f7991231f0811908.jpg)  
图3基于子流域分割的地貌形态类型划分技术流程

![](images/2f26742ebe73cb091f9748acc8fb97a582334e883816b3dcc469512be4b161e2.jpg)  
Fig.3Technique process of topographic features based on sub-drainage segmentation   
Fig.4Types of topographic features in Yaozhou District

![](images/65dcb6a1702a80320f6e0eed155f044cb0cca901d37966903f7e625a5c90dc09.jpg)  
图4陕西省铜川市耀州区地貌形态类型   
图5GPS控制点分布图Fig.5Spatial distribution of GPS points

# 3结论

（1）本文所提出的利用子流域作为地貌形态分类"细胞"(基本单元)的思想，可使地形因子的求算纳入到自然的、客观存在的子流域范围内，成为稳定的因子，较为有效地避开了因分析窗口尺度范围变化而引起的地形因子的不稳定性。

（2）本文首次尝试了基于 $2 5 \mathrm { ~ m ~ }$ 的分辨率格网DEM,采用面向"细胞"级的微小粒度的子流域为分析对象的分类思想，利用GIS空间分析方法，依据小流域属性区域差异特征，实现在中小（区域)尺度下黄土复杂地貌区地貌分类。实验表明，利用本文所设计的方法，可将陕西省耀州地区划分为：河漫滩、黄土残塬、黄土台塬、陡坡冲沟、梁峁状丘陵沟壑、石质小起伏平缓中山、石质小起伏陡峭中山以及水域等8大类型,其分类精度达 $8 8 . 1 9 \%$ ,验证了该分类方法的合理性和正确性。

(3）该分类思想最大的特点在于，避免了传统的以栅格单元为分析对象所造成的分类结果中地貌实体不完整的现象，最大程度保证分类界线与自然地理界线相吻合，分类思想更符合我国传统的地貌分类观念。

（4）笔者提出的地貌形态类型划分方法属于探索性研究，对于中小尺度范围、高分辨率DEM的流域具有较高的分类精度。虽然实现了区域地貌类型的合理划分，但尚有不足之处，有待于今后研究工作的深入开展和改进。如何考虑在保证流域自动分割准确的基础上，使其适用于较大尺度范围、低分辨率DEM数据中流域分割，并取得较好的分类精度，进而构建起体系完善的基于小流域单元思想的地貌形态类型划分方法，这将成为后续研究关注的重点。

致谢：中国科学院地理科学与资源研究所程维明研究员、秦承志研究员以及日本东京首都大学HitoshiSaito博士在本文的撰写过程中提出大量的宝贵意见，作者在此表示感谢。

# 参考文献(References）：

[1]李钜章.中国地貌形态基本类型数量指标初探[J].地理学报, 1982,37（1）:17-26.[Li Juzhang.A prelimitary study on the quantitative index of basic types of geomorophologic from in China [J].Acta Geographica Sinica,1982,37(1）:17-26.]   
[2] Cheng Weiming,Zhou Chenghu,Li Bingyuan,et al. Structure and contents of layered classification system of digital geomorphology for China[J].Journal of Geographical Sciences,2011,21(5）:771 -790.   
[3] 李炳元,潘保田,韩嘉福.中国陆地基本地貌类型及其划分指 标探讨[J].第四纪研究,2008,28（4）:535-543.[Li Bingyuan, Pan Baotian,Han Jiafu.Basic terrestrial geomorphological types in China and their circumscriptions[J].Quaternary Sciences,2008, 28(4) :535-543.]   
[4］赵力强,张律吕,王乃昂,等.巴丹吉林沙漠湖泊形态初步研究 [J].干旱区研究,2018,35（5）:1001-1011.[Zhao Liqiang, Zhang Lvlv,Wang Nai'ang,etal.Morphology of the lakes in the Badain Jaran Desert[J].Arid Zone Research,2018,35(5）:1 001 -1 011.]   
[5]Deng Yongxin.New trends in digital terrain analysis:Iandform defi nition,representation,and classification[J].Progress in Physical Geography,2007,31(4） :405-419.   
[6]刘德林,李壁成.黄土高原小流域土地类型分类及制图研 究——以固原市上黄试区为例[J].生态经济,2009,25（1）：32 -33,37.[Liu Delin,Li Bicheng. Classification and mapping of land type in small watershed in Loess Plateau: Take Shanghuang test area in Guyuan as an example[J].Ecological Economy,2009, 25(1) :32 -33,37.]   
[7]姚永慧,周成虎,孙然好,等.基于多源数据的山地地貌数字解 译[J].山地学报,2007,25（1）:122-128.[Yao Yonghui,Zhou Chenghu,SunRanao,etal.Digitalmappngof mountainlandforms based on multiple source data[J].Mountain Research, 2007,25(1) :122 -128.]   
[8]闾国年,钱亚东,陈钟明.基于栅格数字高程模型提取特征地 貌技术研究[J].地理学报,1998,53(6）:562-569.[Lv Guonian,Qian Yadong,Chen Zhongming.Automated extraction of the characteristics of topography from grid digital elevation data[J]. Acta Geographica Sinica,1998,53(6）:562-569.]   
[9]程维明,周成虎,柴慧霞,等.中国陆地地貌基本形态类型定量 提取与分析[J].地球信息科学学报,2009,11(6):725-736. [Cheng Weiming,Zhou Chenghu,Chai Huixia,et al.Quantitative extraction and analysis of basic morphological types of land geomorphology in China[J]. Journal of Geo-Information Science,2009,11 (6) :725 -736.]   
[10］肖飞,张百平,凌峰,等.基于DEM 的地貌实体单元自动提取 方法[J].地理研究,2008,27（2）:459-466.[Xiao Fei,Zhang Baiping,Ling Feng,et al.DEM based auto-extraction of geomorphic units[J].Geographical Research,2008,27(2）:459-466.]   
[11]刘爱利,汤国安.中国地貌基本形态 DEM 的自动划分研究 [J].地球信息科学,2006,8(4）:8-14,5.[Liu Aili,Tang Guoan.DEM based auto-classification of Chinese landform[J]. Journal of Geo-Information Science,2006,8(4）:8-14,5.]   
[12]秦承志,朱阿兴,施迅,等.坡位渐变信息的模糊推理[J].地理 研究,2007,26(6):1165-1175.[Qin Chengzhi,Zhu Axing,Shi Xun,et al.Fuzzy inference of spatial gradation of slope positions [J]. Geographical Research,2007,26(6）:1 165-1 175.]   
[13]Hossein S,Robert B,Forood S,et al.Landform classification from a digital elevation model and satellite imagery[J]. Geomorphology， 2008,100:453 -464.   
[14]Demoulin A,Bovy B,Rixhon G,et al.An automated method to extract fluvial terraces from digital elevation models:The Vesdre valley,a case study in Eastern Belgium[J]. Geomorphology,2007, 91:51 -64.   
[15]MacMillan RA,Pettapiece W W,Nolan S C,et al.A generic procedure for automatically segmenting landforms into landform elements using DEMs,heuristic rules and fuzzy logic[J].Fuzzy Sets and Systems,2000,113:81-109.   
[16]涂汉明,刘振东.中国地势起伏度研究[J].测绘学报,1991,20 (4）:311-319.[Tu Hanming,Liu Zhendong.Study on relief amplitude in China[J].Acta Geodaetica et Cartographica Sinica, 1991,20(4) :311-319.]   
[17］汤国安，赵牡丹,李天文，等.DEM提取黄土高原地面坡度的不 确定性[J].地理学报,2003,58（6）：824-830.[Tang Guoan, Zhao Mudan,Li Tianwen,et al.Modeling slope uncertainty derived from DEMs in Loess Plateau[J].Acta Geographica Sinica,2003, 58(6) :824 -830.]   
[18］朱红春,陈楠,刘海英,等.自 $1 : 1 0 \ 0 0 0$ 比例尺DEM 提取地形 起伏度——以陕北黄土高原的实验为例[J].测绘科学,2005， 30(4）:86 -88,7.[Zhu Hongchun,Chen Nan,Liu Haiying,et al. Research on the relief based on 1:1O OOO DEMs:A case study in the Loess Plateau of north Shaanxi Province[J].Science of Surveying and Mapping,2005,30(4）:86-88,7.]   
[19]田丹,刘爱利，丁浒,等.地貌形态类型面向对象分类法的改进 [J].地理与地理信息科学,2016,32（2）:46-50,43.[Tian Dan,Liu Aili,Ding Hu,et al. Improvement of object-oriented classification method for landform types[J].Geography and Geo-Information Science,2016,32(2) :46-50,43.]   
[20］胡凡盛,杨太保,王晶,等.基于面向对象分类的马兰冰帽变化 与气候响应[J].干旱区研究,2017,34(5）：1018-1026.[Hu Fansheng,Yang Taibao,Wang Jing,et al.Variation of the Malan Ice Cap and its response to climate change based on object-oriented extraction method[J].Arid Zone Research,2017,34(5）:1 018- 1 026.]   
[21]常直杨，孙伟红,王建,等.青藏高原及其邻近地区地貌类型划 分[J].山地学报,2017,35（1）：1-8.[Chang Zhiyang,Sun Weihong,Wang Jian,et al.Object-oriented method based on classification of geomorphic type in the Tibet Plateau and adjacent regions[J]. Mountain Research,2017,35(1）:1-8.]   
[22］王耕,李素娟,张兴国.基于DEM的淮河源地貌形态类型划分 [J].水土保持通报,2018,38（2）:292-296.[WangGeng,Li Sujuan,Zhang Xingguo.Classification of geomorphic forms of Huaihe River source based on DEM[J].Bulletin of Soil and Water Conservation,2018,38(2):292-296.] [23］胡最,聂阳意.基于DEM的湖南省地貌形态特征分类[J].地 理与地理信息科学,2015,31(6）:67-71.[Hu Zui,Nie Yangyi.DEM-based landform taxonomic features of Hunan Province [J].Geography and Geo-Information Science,2015,31（6）:67-   
71.] [24]张少伟,郭勇,权红花.陕西省地理国(省)情监测中的基本地 貌类型及划分指标[J].测绘标准化,2012,28（4)：13-16. [Zhang Shaowei,Guo Yong,Quan Honghua.Fundamental relief types and their classification index used in provincial geographic conditions monitoring in Shaanxi[J]. Standardization of Surveying and Mapping,2012,28(4):13-16.] [25]张哲夫.耀县之地貌[C]//西北大学黄土高原研究中心.耀县 生态经济综合开发试验研究文集.西安：陕西人民出版社，   
1990:4-6.[Zhang Zhefu.The geomorphology of Yaoxian County [C]//Loess Plateau Research Center of Northwest University.The Experimental Research Paper on the Comprehensive Development of Ecological Economy in Yaoxian COUNTY.Xi'an：Shaanxi People's Publishing House,1990:4 -6.] [26]柴慧霞，程维明,乔玉良.中国"数字黄土地貌”分类体系探讨 [J].地球信息科学,2006,8（2）:6-13.[Chai Huixia,Cheng Weiming,Qiao Yuliang. Classification system of 1:1 Ooo ooo digital loess geomorphology in China［J].Journal of Geo-Information Science,2006,8(2):6-13.] [27]O'Callaghan JF,Mark D M.The extraction of drainage networks from digital elevation data[J].Computer Vision,Graphics and Image Processing,1984,28(3） :323 -344. [28]郭中小，魏永富，廖梓龙，等.锡林河流域地下水位管理阈值研 究[J].干旱区研究,2017,34（3）:479-486.[Guo Zhongxiao, Wei Yongfu,Liao Zilong,et al. Threshold values of groundwater level management in the Xilin River Basin[J].Arid Zone Research,2017,34(3) :479 -486.]

# Classification of Typical Loess Landforms in Subcatchments

WANG Le'²，ZHOU Yi1²，LI Yang1,2 (1.School of Geography Science and Tourism,Shaanxi Normal University,Xi'an 710119,Shaanxi,China; 2.National Experimental Teaching Demonstration Center for Geography,Xi'an 710119,Shaanxi,China)

Abstract：Inthis paper,the analysis unitswere upgraded to the minor drainage basin level,andthe subcatchments of the micro-scaleoriented tothe“cell’level were proposed as theclassification idea of analysis object.The GIS spatial analysis wasused to constructthe geographic attribute database for subcatchments based onthe available geomorphic dataof the study area.Four key clasification indicators including the elevation,relief degree of land surface,average slope and slope skewness were selected.The hierarchical clasification method was used to set the thresholdsof thecorresponding topographicfactors,and8typesoflandforms,i.e.theflood plains,residualloesstableland,loess platform,steep-slope gully,girder-like hillygully,small rockyundulating temperatemid-mountain, small stoneundulating steep-mountain and waters in Yaozhou District of Tongchuan City,Shaanxi Province were divided.The relative integrity of the landforms was maintained in the clasificationas much as possible.Compared with the field sampling observations performed by GPS,the clasification accuracy of the study wasas high as $8 8 . 1 9 \%$ ,which is expected to be a digital geomorphological classification based on subcatchment.

Key words:subcatchment；landform classification； drainage basin；grid DEM； Tongchuan； Shaanxi