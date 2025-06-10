# CN 53-1189/P ISSN 1672-7673

# 新疆天文台在线交叉证认服务

张海龙}²，聂俊²，赵青，冶鑫晨¹，王杰1（1.中国科学院新疆天文台，新疆 乌鲁木齐830011；2.中国科学院射电天文重点实验室，江苏 南京 210008；3.天津科技大学，天津 300222)

摘要：新疆天文台数据中心的海量数据星表在线交叉证认服务可实现远程URL、本地上传带有UCD信息的VOTable格式文件两种星表数据输入方式，可实现对数据中心已发布的天文数据进行交叉证认。证认得到的结果可以通过SAMP协议发送到标准虚拟天文台工具中进行数据可视化等相关处理，并支持HTML、CSV、FITS Table、JSON等多种数据输出方式。通过并行计算技术与伪球面天区划分技术大大提高了海量星表数据的交叉证认速度。

关键词：数据中心；虚拟天文台；交叉证认；星表数据中图分类号：TP3-05 文献标识码：A 文章编号：1672-7673(2017)03-0347-09

随着信息技术、制造技术的快速发展，天文学已经进入了全波段巡天观测时代，来自不同天文观测设备的多波段观测数据快速增长，如何实现海量天文数据的融合、研究天体在各波段的特性，是目前天文研究急需解决的问题之一。

交叉证认计算是多波段天文观测数据融合的基础，也是多波段天文学研究的前提。交叉证认操作是典型的数据密集型计算，近年来多国的计算机专家在交叉证认方面进行了系统的研究并提出了较好的解决方案。图灵奖获得者JimGray 曾是美国虚拟天文台①负责交叉证认问题的首席科学家，最早提出解决交叉证认问题必须依靠并行计算技术[1]。Jim Gray 为美国虚拟天文台设计了基于微软 SQLServer 的纯 SQL 指令[2-5]交叉证认服务 OpenSkyQuery，从而为斯隆数字巡天（Sloan Digital Sky Survey，SDSS)的数据访问平台整合了多家天文台的数据集。由于十年前的计算机硬件性能、内存容量、软件等诸多条件限制，且当时提出的方法在实现上受限于MSSQL数据库系统，交叉证认的数据规模相对较小，单次证认的条数限制在5000 条以内。英国虚拟天文台（AstroGrid)②在其网站上提供了简单的交叉证认服务[6-8]，但效率不高且无法实现大规模数据交叉证认。目前各大天文数据中心均提供各自的交叉证认服务，如VizieR③、Simbad④、Aladin、 $\mathrm { N E D } ^ { \textcircled { 6 } }$ 等。

我国近年来新建了诸多天文科学装置，在观测选源及数据处理过程中不得不依赖交叉证认技术，国家重大科学工程郭守敬望远镜光谱确认过程的核心就是交叉证认。在这样的背景下，我国多位科技工作者在高效交叉证认方面取得了一些成果：文[9-11]提出了一种基于HTM球面索引和 KD-Tree 的快速交叉证认算法，该方法的效率适用于几十万条到几百万条的中等数据量。文[12]利用Python 多核并行方法大大提高了交叉证认速度。文「13]利用贝叶斯假设检验相关方法对射电星表交叉证认进行了尝试，应用在SWIRE和ATLASCDF-S星表证认中，并取得了较好的效果。

# 1交叉证认原理

# （1）距离公式

以图1中的两点 $A$ 、 $B$ 为例，它们分别来源于星表 $A$ 和星表 $B$ ，设其坐标分别为 $( \alpha _ { 1 } , \delta _ { 1 } ) \ 、 ( \alpha _ { 2 } , \delta _ { 2 } )$ ，它们之间的球面角距离 $d$ 可以按如下步骤计算：

$$
\mid \alpha _ { 1 } \ : - \ : \alpha _ { 2 } \mid \leqslant 1 8 0 ^ { \circ } , \angle A N B = \mid \alpha _ { 1 } \ : - \ : \alpha _ { 2 } \mid
$$

$$
\left| \alpha _ { 1 } - \alpha _ { 2 } \right| > 1 8 0 ^ { \circ } , \angle A N B = 3 6 0 ^ { \circ } - \left| \alpha _ { 1 } - \alpha _ { 2 } \right|
$$

根据球面余弦定理：

$$
\angle A O B = \cos \angle A O N { \cos \angle B O N } +
$$

$$
\sin \angle A O N \mathrm { s i n } \angle B O N \mathrm { c o s } \angle A N B
$$

$$
{ \bf \xi } = \sin \delta _ { 1 } \sin \delta _ { 2 } \ + \ \mathrm { c o s } \delta _ { 1 } \mathrm { c o s } \delta _ { 2 } \mathrm { c o s } ( \alpha _ { 1 } \ - \ \alpha _ { 2 } )
$$

$$
d = \angle A O B = \operatorname { a r c c o s } [ \sin \delta _ { 1 } \sin \delta _ { 2 } \ +
$$

$$
\mathrm { c o s } \delta _ { 1 } \mathrm { c o s } \delta _ { 2 } \mathrm { c o s } \big ( \alpha _ { 1 } - \alpha _ { 2 } \big ) \top
$$

当 $A , B$ 两点之间角距离很小时， $\delta \approx ( \delta _ { 1 } + \delta _ { 2 } ) / 2$ 所以有 $d ^ { 2 } = [ ( \alpha _ { 1 } - \alpha _ { 2 } ) \mathrm { c o s } \delta ] ^ { 2 } + ( \delta _ { 1 } - \delta _ { 2 } ) ^ { 2 }$

(2)证认成功的判断公式

$$
\begin{array} { c } { d = \sqrt { [ \left( \alpha _ { 1 } \mathrm { ~ - ~ } \alpha _ { 2 } \right) \mathrm { c o s } \delta ] ^ { 2 } \mathrm { ~ + ~ } ( \delta _ { 1 } \mathrm { ~ - ~ } \delta _ { 2 } ) ^ { 2 } } } \\ { \leqslant 3 \sqrt { { r _ { 1 } } ^ { 2 } \mathrm { ~ + ~ } { r _ { 2 } } ^ { 2 } } } \end{array}
$$

其中， $r _ { 1 }$ 和 $r _ { 2 }$ 为两个星表的误差半径，也就是当两点之间的距离满足上式时，可以认为两点证认成功，互为匹配的对应体。

![](images/fcfbd020728436ac297b807060445aa5b6d3b7e6d42706688548d2fcf60e34f0.jpg)  
图1球面两点交叉证认原理 Fig.1Crossmatch principle

# 2德国天体物理虚拟天文台

新疆天文台数据中心以德国天体物理虚拟天文台（German Astrophysical Virtual Observatory，$\mathrm { G A V O } ^ { \textregistered }$ )为基础框架建设，本文涉及的交叉证认服务是新疆天文台数据中心提供的服务之一。德国天体物理虚拟天文台的实现遵循了国际虚拟天文台联盟（International Virtual Observatory Alliance， $\mathrm { I V O A } ^ { \textcircled { 8 } }$ 的标准和协议，是德国天文学家对扩展和使用虚拟天文台做出的贡献之一。

虚拟天文台能够实现的主要功能有：

(1)通过定义良好的标准及协议实现或改善天体测量学、光度学、光谱学、时间序列等天文数据的发布与检索服务；（2)使用标准的数据检索与查询方式，让天文学家很容易发现、访问和使用相关天文观测数据;（3)确保数据不会凭空消失，保证正确地描述、访问与理解数据;(4)提供虚拟天文台标准软件帮助天文学家获取及分析数据。

# 3伪球面分区技术

伪球面索引本质是将天球以特定几何形状进行区块划分，将球面划分成等面积或不等面积的 $N$ 份空间。在建立索引时根据编码或是坐标信息对天球面所有区块进行系统编码，并对编码排序，在检索时首先以某一赤经 $( R A )$ 、赤纬(DEC)为基础计算所对应的区块，进而在区块内部再逐一比对。通过区块划分及编码可以实现真实的天体目标与球面区块间的对应关系，通过区块的编码可实现针对赤经、赤纬二维空间到一维的映射。目前应用最广泛的几种伪球面索引方法为分层三角网格（Hierarchical Triangular Mesh，HTM）、HEALPix@（Hierarchical Equal Area isoLatitude Pixelisation,HEALPix）及 $\mathrm { Q } 3 \mathrm { C } ^ { \mathrm { ( I I ) } }$ （Quad Tree Cube）。

Q3C 是一种新的伪球面索引方法，是专为开源数据库PostgreSQL设计的一款开源、高效锥形检索、交叉证认及其它空间搜索的索引模式，源代码可以从网站获取。

Q3C 的天区划分方法跟HTM、HEALPix类似，也采用在伪球面上划分四边形实现天球划分，将一球体假想为立方体，在立方体每个面上构造一个四叉树，利用四叉树结构生成二维坐标码（或正整数编码)。由于初始立方体只有6个面，使用3位二进制数可以编码与面的映射关系。这种划分很容易实现立方体的表面中心投影到球体上，四叉树结构也可以自动被球体继承。如图2通过不同层次的划分最终球面被划分成由多个四边形组成的面。这种划分有两个优点：（1)该天区划分方式及所进行的计算非常简单，因为球体和立方体表面的映射仅仅是中心投影，应用的三角函数运算不多；（2）由于计算方法比HTM和HEALPIX相对简单，对于层级划分较深时仍不影响检索的性能。Q3C在四边形区域使用了四叉树结构及特殊表查询加速计算算法，使其在多层级划分时仍能保持良好的效率。Q3C在天区划分方面有别于HTM与HEALPix，其划分的天区面积不完全相同，并非等面积划分。

Q3C 索引方法将球面各点一一映射为整数(称为IPIX值)，并确保某一个点附近的IPIX 值相差不多。这为创建球面索引及在球体上快速搜索奠定了基础，为了有效地利用索引，每一次查询首先要对预匹配的赤经、赤纬进行IPIX值计算，从而得到相应划分位置。如图3，当确定了某一小块天区后，其内每个像素代表的IPIX值是连续的，因此满足条件的数据可以快速地从数据库中获取。

![](images/b87092c53061778885c539bbca3026e0e17d6e7dea979a1f2294534fed973c80.jpg)  
图2Q3C天区划分Fig.2Q3C Sphere Segmentation

![](images/f7cf1cece372e158ba5e7b5b17d5af1fe3064bd8bfdbb9f6ffcab6da3efefee4.jpg)  
图3Q3C锥形检索④Fig.3 Q3C Cone Query

Q3C 索引技术针对PostgreSQL开源数据库设计，为锥形检索、交叉证认等技术进行了优化，由于采用中心投影方式减少了大量的三角函数计算，从而提高了检索效率，本文经过测试最终选择Q3C索引技术。

# 4交叉证认实现

# 4.1数据服务器配置

新疆天文台数据服务器的配置如表1，服务器承担数据归档、发布、检索、下载及各种计算相关服务，交叉证认服务是数据服务器提供的诸多服务之一。

表1数据服务器配置信息  
Table 1 Configuration information of data servers   

<html><body><table><tr><td>配件</td><td>规格参数</td><td>数量</td></tr><tr><td>CPU</td><td>Intel  Xeon  CPUE5-2692 v2@ 2.20 GHz</td><td>2</td></tr><tr><td>内存</td><td>8GB</td><td>8</td></tr><tr><td>硬盘(OS)SAS</td><td>300 GB</td><td>2</td></tr><tr><td>硬盘（DATA）SATA</td><td>4 TB</td><td>12</td></tr><tr><td>主板</td><td>Intel Corporation C6OO/X79 series chipset</td><td>1</td></tr><tr><td>附加网络接口</td><td>IB Card 56 Gbps</td><td>1</td></tr></table></body></html>

# 4.2交叉证认数据源格式

新疆天文台数据中心交叉证认服务网址：htp://data.xao.ac.cn/crossq/match/form，交叉证认服务名称为“XAO DC Custom Uploading Crossmatcher”，可通过新疆天文台数据中心链接进入服务。服务可实现本地文件及远程URL两种方式上传数据星表，对于本地已保存的VOTable文件可直接上传，对于远程服务器上满足格式的文件直接给出 URL 即可，文件格式可参考 http://data.xao.ac.cn/static/cross_match。

交叉证认服务接受的文件需严格满足VOTable格式，其中要指定赤经、赤纬字段的UCD 信息,其格式如下：

<？ xml version ${ \bf \tau } = { \bf \tau } ^ { , } 1 . 0 { \bf \tau } ^ { , } { \bf \tau } _ { ? } >$ <VOTABLE version $= " 1 . 3 "$ xmlns:xsi $\mathbf { \tau } = \mathbf { \tau }$ "http://www.w3.org/2001/XMLSchema-instance” xmln http://www.ivoa.net/xml/VOTable/v1.3”xmlns:stc $\ c =$ "http://www.ivoa.net/xml/STC/v1.30”> <RESOURCE name $\mathbf { \tau } = \mathbf { \tau }$ ” crossMatchCatalog" $>$ （204号 <TABLE name $\ c =$ ”cross_match”nrows $\ c =$ "5”> <DESCRIPTION $\mathrm { > }$ OnlyRA&DEC neededin the table. ${ < }$ DESCRIPTION> <FIELD datatype $\ c =$ ”double”name $\ c =$ ”ra”ucd $\mathbf { \tau } = \mathbf { \tau }$ " pos.eq.ra; meta.main”/> <FIELD datatype $\ c =$ ”double”name $\ c =$ ”dec”ucd $\ c =$ " pos.eq.dec ;meta.main"/> <DATA> <TABLEDATA> <TR> <TD>336.5396994</TD> <TD>-29.9669121</TD> </TR> <TR> <TD>340.8337065</TD> <TD>-34.8434972</TD>

</TR> <TR> <TD>340.8296062</TD> <TD>-34.4649278</TD> </TR> <TR> <TD>340.8304808</TD> <TD>-34.4992970</TD> </TR> <TR> <TD>340.0254577</TD> <TD>-30.8180950</TD> </TR> </TABLEDATA> </DATA> </TABLE> </RESOURCE> </VOTABLE>

TABLEDATA字段代表具体要进行交叉证认源的位置信息，至少要包含某个源的赤经、赤纬坐标。例子中给出了5个源的具体信息，实际在证认过程中可以根据需要适当修改。

# 4.3交叉证认页面

新疆天文台数据中心交叉证认服务?目前只支持较新的浏览器访问，对于IE 浏览器需关闭兼容视图。如图4，交叉证认前台页面由几部分组成，其中最左侧菜单内容为链接与交叉证认服务的基本信息，图中右上部分为服务的说明，简单介绍了服务性质及所允许的上传文件信息，Tablesavailablefor ADQL 链接可以查看数据中心支持ADQL 服务的所有表信息，service info 链接可以查看针对交叉证认服务的相关信息。

在服务中包含 Local file、Remote URL、Target Table、Search radius、Table、Output format 等6个字段。其中Local file、Remote URL两个字段代表输入源，文件格式为VOTable。Local file 支持本地文件上传，Remote URL 支持给定的远程URL 文件。Target Table 字段指在数据中心已发布且支持 ADQL表的集合，可以根据需要选择星表进行匹配。Searchradius 字段代表搜索半径，可根据交叉匹配的两个星表的误差半径给出具体搜索半径值。可参考公式 $3 \sqrt { { r _ { 1 } } ^ { 2 } + { r _ { 2 } } ^ { 2 } }$ 确定搜索半径，其中 $r _ { 1 }$ ， $r _ { 2 }$ 为两星表的误差半径。Table字段后面的Limit to代表匹配成功后浏览器页面输出数据条数，这个数值不宜调得过大，因为数据返回量大时严重影响浏览器响应时间，默认Limitto值为100，如果匹配成功数据条数超过限制值，用户可根据需要自行调整。Output format字段代表匹配成功数据输出的数据格式，目前支持 HTML、Text VOTable、JSON、FITS Table、CSV 格式输出，具体数据输出格式可根据需要调整。

在图4中 Remote URL 指定 htp://data.xao.ac.cn/static/cross_match，Target Table 中指定 ppmxl.main(星表记录数10亿条左右)星表为目标星表，Table中Limit to给定限制为1000，Search radius 限定 $0 . 0 0 1 ^ { \circ }$ ，Output format中指定HTML输出格式。参数确定后点击GO按钮，可得到图5所示共匹配成功757条数据及相应的参数信息。点击QuickPlot可实现图6的数据可视化，绘图操作可自行选择字段及所绘点的样式，点击 Send via SAMP 可将结果发送到标准虚拟天文台工具[14]（如TOPCAT)中,进行数据再处理。

![](images/ad6cca36d9f8859df20f46227065eb4f1fcfcbcf28ab4b9e3bbae3a038f092e4.jpg)  
14卷  
图4交叉证认页面  
Fig. 4Crossmatch page   
图5 匹配结果  
Fig.5Crossmatch Results

□ x XAO DC Custom Uploac X G q3c index - Google搜索 × data.xao.ac.cn/cross/q/match/form ☆ XAO XAO DC Custom Uploading Crossmatcher Home Parameters Help Local file:Fileupload" Service info Remote URL: http://data.xao.ac.cn/static/cross_match Search radius: 0.001 Metadata Target Table:ppmxl.main Identifier ivo://xaovo/cross/q/matc Result Description A plain positional crossr Matched: 757 Keywords Send via SAMP Quick Plot Catalogs Creator Id [deg] RA [deg] Dec E_raepraE_deepde [deg] [deg] PM(RA) [deg/yr] PM(Dec) [deglyr] PM(RA) PM(Dec) Err. Err. #obs' Author: Hailong Zhangg [deg/yr][deg/yr] 2009-06-30T10:32:00Z Created 1270486784963202545 335.159448 -28.396266 3.69e-05 3.69e-05 1.1647e-05 -5.3861e-06 2.17e- 06 2.17e-06 3 Data updated 1270486784963202545335.159448 -28.396266 3.69e-05 3.69e-05 1.1647e-05 -5.3861e-06 $^ { 2 . 1 7 e . } _ { 0 6 }$ 2.17e-06 3 2015-0-1901 1271723434119163981 336.874314-28.562427 4.53e-05 4.53e-05 3.4861e-06 6.8306e-06 $^ { 2 . 1 7 e . } _ { 0 6 }$ （24 2.17e-06 2 Service info 1271723434119163981336.874314-28.562427 4.53e-05 4.53e-053.4861e-06 6.8306e-06 $^ { 2 . 1 7 e . } _ { 0 6 }$ 2.17e-06 2 1272238947138844943 338.898195 -27.889961 4.53e-05 4.53e-05 -1.5117e-05 -1.8694e-06 2e-06 2e-06 2 Try ADQL to query our 1272238947067022759 338.898547 -27.889473 3.69e-053.69e-05-1.8022e-05 1.4861e-06 1.81e- 1.81e-06 3

![](images/b21f5ec84fd17ee44ae2dc6ebfa843c502cc8c3b4b01d82358ac4e26526f2863.jpg)  
图6 匹配结果可视化  
Fig.6Results visualization

# 4.4认证结果比较

国内近几年在交叉证认方面的研究成果详见文[11-13,15]，由于文献中提供的方法没有提供在线的测试平台，数据直接从文献中引用，具体测试结果见表2。

表2证认结果比较  
Table 2 Cross-match results comparison   

<html><body><table><tr><td></td><td>星表A(行)</td><td>星表B(行)</td><td>分割方法</td><td>耗时/min</td></tr><tr><td>高丹等人程序</td><td>811117</td><td>470992970</td><td>HTM(10级）</td><td>407</td></tr><tr><td>裴彤等人程序</td><td>811117</td><td>470992970</td><td>HTM(6级)</td><td>2</td></tr><tr><td>本文程序</td><td>800000</td><td>470992970</td><td>Q3C(29级)</td><td><1</td></tr><tr><td>裴彤等人程序</td><td>100106811</td><td>470992970</td><td>HTM(8级)</td><td>10</td></tr><tr><td>赵青等人程序</td><td>100106811</td><td>470992970</td><td>HEALPix</td><td>32</td></tr><tr><td>本文程序</td><td>103319647</td><td>910468688</td><td>Q3C(29级)</td><td><8</td></tr></table></body></html>

# 4.5交叉证认实验结果分析

对于图4规模的交叉证认时间返回值大概为 $0 . 0 0 1 ~ \mathrm { m s }$ ，采用Q3C29级划分及并行计算技术，大大加快了匹配速度。综合分析表2结果，本文实现的在线交叉证认平台效率要明显高于同行结果。在数据服务器上提供4000、20000条记录的VOTable文件供同行测试，由于服务器负载情况限制在数据量大时（源星表数据超过50万行，或数据文件超过 $2 0 ~ \mathrm { M B }$ ，匹配10亿量级星表)匹配时间可能达到分钟量级，这取决于上传星表时间及网络带宽，在本地服务器上测试过程中两个操作的浏览器返回时间均在秒量级，文件名分别为 cross_match，cross_match_20000。

# 5总结

实现了国内首个在线交叉证认平台，新疆天文台数据中心在线交叉证认服务支持本地上传及URL两种源表文件输入方式，文件输入支持标准的VOTable格式。在数据中心已发布的星表均可以作为交叉证认的目标星表，在证认中提供了搜索半径选项方便同行测试，支持多种证认结果数据输出格式。通过伪球面天区划分技术与并行计算技术大大提高了交叉证认速度，使万量级对亿量级的星表证认时间消耗在毫秒量级。

致谢：感谢天文学科技领域云项目成员对新疆天文台数据中心建设的支持。数据中心测试与数据的预处理在新疆天文台Taurus 高性能计算系统上完成。

# 参考文献：

[1] Nieto-Santisteban M A， Thakar A R， Szalay A S. Cross-matching very large datasets [C/OL]. https ://esto.nasa.gov/conferences/nstc2007/papers/Nieto-Santisteban_Maria_A10P2_NSTC-07- 0074.pdf.   
[2] Gray J，Szalay A，Fekete G. Using table valued functions in SQL Server 2OO5 to implement a spatial data library [J/OL]. https://arxiv.org/ftp/cs/papers/0701/0701163.pdf.   
[3] Gray J,Nieto-Santisteban M A，Szalay A S. The zones algorithm for finding points-near-a-point or cross-matching spatial datasets [J/OL].(2007）[2016-09-09]. htps://arxiv.org/ftp/cs/ papers/0701/0701171.pdf.   
[4] Gray J，Szalay A S,Thakar A R，et al. There goes the neighborhood：Relational algebra for spatial data search [J/OL]. https://arxiv.org/ftp/cs/papers/O408/0408031.pdf.   
[5] Gray J，Szalay A，Budavári T,et al. Cross-matching multiple spatial observations and dealing with missing data [J/OL]. https://arxiv.org/ftp/cs/papers/O701/0701172.pdf.   
[6] Joins S，Revisted S I. Technical report of AstroGrid [J/OL]. http://wiki.astrogrid.org/bin/ view/Astrogrid/SpatialIndexing.   
[7] Zhao Q，Sun J, Yu C，et al.A paralleled large-scale astronomical cross-matching function [C]. International Conference on Algorithms and Architectures for Parallel Processing. Springer Berlin Heidelberg，2009：604-614.   
[8] Rajendra Bose，Robert G. Mann，Diego Prina-Ricotti，AstroDAS:Sharing Assertions across Astronomy Catalogues through Distributed Annotation，Proceedings of the International Provenance and Annotation Workshop ［J]. Chicago，2006(4145）:193-202   
[9] 高丹，张彦霞，赵永恒.海量多波段星表数据的交叉证认的实现［J].天文研究与技术 国家天文台台刊，2005，2(2)：186-193. Gao Dan，Zhang Yanxia， Zhao Yongheng. The realization of crossOidentification based on huge multi-wavelength catalog data ［J].Astronomical Research and Technology一 —Publications of National Astronomical Observatories of China，2005，2(2）：186-193.   
[10] Gao Dan. A system integrated with query，cross-matching and visualization [J]. SPIE The International Society for Optical Engineering，2006(6274）:14.   
[11] 高丹，张彦霞，赵永恒．中国虚拟天文台交叉证认工具的开发和应用［J]．天文学报， 2008，49(3): 348-358. Gao Dan，Zhang Yanxia， Zhao Yongheng. The development and application of the cross-match tool of China-VO ［J]. Acta Astronomica Sinica，2008，49(3）: 348-358.   
[12] 裴彤，张彦霞，彭南博，等.Python 多核并行计算在海量星表交叉证认中的应用［J]．中 国科学 物理学 力学 天文学，2011，41(1)：102-107. Pei Tong， Zhang Yanxia，Peng Nanbo，et al. The application of multi-core paralel computing using python language in cross-matching of massive catalogues [J]. Scientia Sinica Physica, Mechanica & Astronomica，2011，41（1）：102-107.   
[13] Fan Dongwei， Budav S T R，Norris P R，et al. Matching radio catalogs with realistic geometry : application to SWIRE and ATLAS[J]. Monthly Notices of the Royal Astronomical Society, 2015，451(2) : 1299-1305.   
[14] 张海龙，Markus Demleitner，王娜．新疆天文台脉冲星数据检索［J]．天文研究与技术， 2016，13(4): 473-480. Zhang Hailong，Markus Demleitner，Wang Na. Using the Xinjiang Astronomical Observatory pulsar data archive [J]. Astronomical Research & Technology，2016,13(4）: 473-480.   
[15] 赵青．面向海量数据的高效天文交叉证认的研究［D].天津：天津大学，2010.

# Xinjiang Astronomical Observatory Data Center Custom Uploading Crossmatcher

Zhang Hailong $^ { 1 , 2 }$ ，Nie Jun $^ { 1 , 2 }$ ，Zhao Qing³，Ye Xinchen1，Wang Jie1 (1.XinjiangAstronomicalObservatory,ChineseAcademyofSciences，Urumqi83ol1,China,Email：zhanghailong@xaoac.cn; 2.Key Laboratory of Radio Astronomy，Chinese Academy of Sciences，Nanjing 21ooo8,China; 3.Tianjin University of Science & Technology，Tianjin 300222,China)

Abstract：Xinjiang Astronomical Observatory（XAO） data center is infrastructure for scientific research needs in astronomy and provides scientific data service.The online custom uploading crossmatcher service of XAO data center accepts two kinds of inputs，remote URL and uploading the local file which must meet the requirements of VOTable format and contain the Unified Content Descriptors（UCD).Identified results can be sentto the standard Virtual Observatory tols for data visualization and other related processing via Simple Application Messaging Protocol（SAMP）.The crossmatcher supports HTML，CSV，FITS Table and JSON, etc.data output formats.By using Q3C sky indexing scheme and paralel computing technologies，the crossmatch efficiency is increased greatly.

Key words: Data center；Virtual Observatory；Crossmatch； Catalog