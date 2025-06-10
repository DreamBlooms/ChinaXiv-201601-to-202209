# GWAC海量星表数据处理的数据库系统选型研究

万萌1,2,3，吴 潮'，Ying Zhang³，徐洋l，魏建彦1（1.中国科学院国家天文台，北京100012；2.中国科学院大学，北京100049；3.荷兰国家数学与计算机科学研究中心，阿姆斯特丹1098 XG)

摘要：为应对我国的宽视场地基广角相机阵在大数据管理和实时处理上带来的挑战，提出一种基于列存储数据库MonetDB的时序数据处理与管理系统设计方案。本方案充分利用MonetDB兼具数据处理和管理于一体的数据库平台特点，通过将交叉认证等核心数据处理算法内嵌于数据库中，从而实现将“计算带到数据中”的设计理念。同时，对本方案开展了多项关键技术的研究与测试：TPC-H基准性能测试；大数据加载能力测试及优化研究；基于MonetDB的Zone算法实现与测试；可定制函数开发功能的测试。初步的预研结果表明，列存储切实可行，同时对本设计方案作详细的介绍。提出的基于列存储 MonetDB数据库设计的海量星表数据处理应用方案，是高效的数据处理与管理为一体的天文数据库解决方案。

关键词：天文数据库；架构设计；MonetDB；实时分析；交叉认证

1图分类号：TP311 文献标识码：A 文章编号：1672-7673(2016)03-0373-09

现代天文观测和数据处理技术的发展，使得时域天文观测朝着更大的视场和更高的时间采样率方向发展成为可能，也给现代时域天文观测注入了新的活力，如超新星尤其是爆发早期超新星的发现，伽玛暴光学余辉的快速响应观测，微引力透镜事件的发现与后随观测等都得益于现代时域天文观测和数据处理技术的发展。

我国兴建中的地面广角相机阵（Ground Wide Angle Camera，GWAC），由36台口径为 $1 8 ~ \mathrm { c m }$ 的广角望远镜组成，每台望远镜配备 $4 \mathrm { k } \times 4 \mathrm { k }$ 的CCD探测器。整个相机阵的天区覆盖5000平方度，时间采样率为 $1 5 \mathrm { ~ s ~ }$ 。每个观测夜对固定天区目标的持继观测长达 $4 \sim 5 \mathrm { ~ h ~ }$ 。从观测视场的大小和观测时间的采样频度上，地面广角相机阵在时域天文观测中具有特殊的优势。巨大的数据量和高时间采样率，对数据的管理和处理提出极大的挑战。

地面广角相机阵的星表数据指标是：星表数据每幅图像大约有 $1 . 5 \times 1 0 ^ { 5 }$ 条记录，整个相机阵在$1 5 \mathrm { ~ s ~ }$ 内共产生 $5 . 4 \times 1 0 ^ { 6 }$ 条记录，每晚约有 $2 4 0 0 \times 3 6 = 8 6 4 0 0$ 幅图，大约 $2 \mathrm { T B }$ 。对数据库管理系统的要求：（1)快速的大数据人库能力，所有相机阵 $1 5 \mathrm { ~ s ~ }$ 内产生的观测星表人库时间控制在 $1 5 \mathrm { ~ s ~ }$ 以内，每个观测夜的 $2 \mathrm { T B }$ 星表最晚完成入库时间保证在下一个观测夜开始前；（2)在数据高速采集下能够完成实时分析，面对持续不断的高密度海量星表的快速关联计算能力，即每个CCD每15s产生的星表数据与参考星表相关联形成光变曲线。

对于地基广角相机阵，最直接的数据库管理和处理系统的设计方案是数据库(仅为数据存储) $^ +$ 外围的程序(完成快速的运算)。文「1]通过对关键技术交叉认证的研究开发了基于空间等经纬网格的天区分区算法，使得交叉认证计算实现了极大的提速；利用图形处理器的平行计算优势，文[2]实现了图形处理器加速图像相减处理的方法；文[3]开发了利用图形处理器加速天文中常用的点源提取程序SEXtractor；文[4]开发了基于图形处理器的加速星表的交叉认证算法，该方案的好处是思路直接，许多技术是成熟的，缺点是数据库不断与处围程序交换，带来不必要的输入输出时间损耗，多方程序组合缺少整体的优化。

著名数据库专家 Jim Gray 成功开发了SDSS 巡天数据库管理系统 Skyserver，他提出了 Zone 算法 $\textcircled { 1 } \textcircled { - 2 }$ ，即利用数据库的 SQL 直接实现多维空间索引取代经典的分层三角网格算法（HierarchicalTriangular Mesh，HTM)，从而减少数据的交互，速度得到提升。这就是大规模科学计算和数据库架构设计的原则：将计算带到数据中来，而不是把数据放到计算中去的设计理念[5]。受这一思想的启发，提出将地基广角相机阵的数据处理和数据管理合成到一个数据库平台的设计思路。

合适的数据库平台是实现这一设计思想的关键，因为传统的数据库平台不具备大数据快速处理的能力。LSST项目针对天文大数据的需求提出开发全新的数据库 SciDB，因为处于开发活跃期，SciDB的稳定性和实用性还有待检验。MonetDB是一款开源的内存列存储数据库平台 $\textcircled { 3 }$ ，具有内部存储模型按列分块、占用存储空间小、运行时查询优化等优势。MonetDB底层物理存储模型与传统数据库有非常显著的不同，关系表经过垂直切分，每一列存储在一个单独的（ID，value)键值对表中，称作二元关系表（Binary Assciation Table，BAT）。二元关系表左边一列，叫做头部，是对象ID（OID）；右侧一列叫尾部，包含属性的值。头部和尾部分别用一个数组实现。使用列存储数据库的方式使得查询语句的执行只需要访问用到的列。当同一类型的属性存在于连续内存，可以获得较高的压缩比和缓存命中率。同时，MonetDB的内核是建立在类“array”结构上的可编程的关系代数机，这种友好的结构能最大限度地利用硬件的性能实时响应用户的需求。而且，MonetDB 执行引擎中缓存敏感的数据结构算法可以在运行时优化多级内存系统。

可以看出，表的数据量越大，尤其是当查询语句比重越大，就越适合使用列存储数据库。因为如果数据量很大，而查询访问的列比很小，即所有查询语句访问的列数和总列数的比例越小，使用列查询越能降低 SQL语句查询时间，越适合使用列存储。

综上所述，MonetDB适合要求快速取回结果的海量数据分析型在线分析处理（Online AnalyticalProcessing，OLAP)的应用和存储，这与地面广角相机阵需要提供的查询服务属于同一类型，非常适合应用于天文数据库。

大型射电望远镜巡天项目低频阵列（Low-FrequencyArray，LOFAR）利用MonetDB完成了数据处理系统TKPpipeline，其星表数据一年约为 $4 0 \mathrm { T B } ^ { [ 6 ] }$ ；SDSS 的 SQL Server 管理数据库曾被成功移植到MonetDB上[7]，并通过了对斯隆数字巡天项目中的SDSSBESTDR7近4TB数据的管理测试。因此选取列存储数据库MonetDB作为系统的开发平台。

为研究和验证以上设计思路的可行性，根据地基广角相机阵数据处理流程(如图1)开展了TPC-H基准性能测试以验证其载入和分析能力，大数据加载速度的测试与研究。通过MonetDB的自定义函数接口功能测试实际自定义函数的开发功能；核心算法交叉认证条带（Zone)算法在MonetDB上的实现与测试。最后，详述了基于MonetDB的海量星表数据管理和处理的初步方案。

![](images/b207f0c0b770684b2ab5eda258147c605de28619089febd2660b174dba0d091c.jpg)  
图1地基广角相机阵数据处理流程图Fig.1The flow chart of GWAC data processing

# TPC-H基准测试与比较

为测试 MonetDB的实际表现，进行了TPC-H基准测试并比较了与传统数据库平台PostgreSQL及MySQL 的差异。TPC-H是模拟决策支持类应用的一个测试集。天文数据库日常提供的服务也属于数

据分析类应用，适合选择TPC-H作为测试集。

TPC-H测试包括22条选择查询语句。测试流程为先用DBGEN工具产生测试数据，加载程序装载数据到3种数据库后，数据库处于初始状态，未进行其他任何操作。此时将22条查询顺序执行一遍，分别记录3种数据库22条查询的总响应时间。测试环境同上，MySQL版本为5.6.16。测试环境具体情况如表1。

图2为 MonetDB 和 PostgreSQL、MySQL 的TPC-H $\mathrm { S F } { = } 1 \left( 1 ~ \mathrm { G B } \right)$ 数据量基准性能测试结果对

表1测试环境具体情况表  
Table1 Parameters of the test   

<html><body><table><tr><td>Software and hardware of testing platform</td><td>Database</td><td>Version</td></tr><tr><td rowspan="2">Dawn A650Sercer，CPU： Dual-Core AMD Opteron (tm) Processor 2214 HE，4GB</td><td>MonetDB</td><td>Feb2013-SP2</td></tr><tr><td>PostgreSQL</td><td>9.2.0</td></tr><tr><td>RAM,OS：Fedora release 18</td><td>MySQL</td><td>5. 6.16</td></tr></table></body></html>

比，具体代码见 $\textcircled{4}$ 。可以看出22条查询总时间MonetDB 消耗只有PostgreSQL的约1/15，MySQL的$1 / 1 3 7$ ，单条查询提速至少3倍。造成查询响应时间存在较大差异的主要原因是TPC-H业务类型是在线数据分析类型，数据量大，查询语句比重大，复杂的查询多，符合适合列存储数据库的典型指标。表的数据量越大，就越适合使用列存储数据库，尤其是当查询语句比重也很大时，则使用列查询能显著降低 SQL语句查询的时间。如果查询访问的列比，即所有查询语句访问的列数和总列数的比例越小，越适合列存储。这解释了对于大表 Lineitem上的连接、且查询访问列比低的查询的Q18、Q19、Q21，MonetDB响应速度领先数十倍的原因。可见MonetDB列存储数据库在分析式查询时具有较强优势。MonetDB 在 TPC-H测试中的表现相对于 MySQL 和PostgreSQL具有明显的优势，MySQL 表现最差，而PostgresSQL 居中。

![](images/94dfde4845d1d6ec6026f46cb7606ca0f9d386ef50f27dccbfc1dda8ff6eae05.jpg)  
图2MonetDB 和 PostgreSQL、MySQL TPC-H1G基准测试 Fig.2Benchmark results of MonetDB，PostgreSQL，MySQL TPC-H1G

# 2关键算法与功能分析测试

根据地基广角相机阵数据处理需求，处理速度要求在15s的采样时间间隔内完成数据的所有处理；功能上要求匹配出瞬变源并能生成光变曲线。进行如下关键算法和功能的测试：大数据的加载能力；交叉认证算法的实现；扩展处理功能的开发实现。

# 2.1大数据加载测试

大数据加载测试主要分为两种情况。测试(1)：数据库随着加载数据量的增加对加载速度的影响；测试(2)：影响加载速度因素的测试分析。

测试(1)的方法为通过仿真1000个20列 $\times 2 0$ 万行 $\textcircled{5}$ 类似于实际观测的星表数据，连续加载到被测试的数据库中，分析加载速度的变化。测试平台的软硬件环境如图3。测试的具体实现过程：对仿真的星表，使用大文件导入库命令COPYBINARYINTO：

COPY BINARY INTO tablename FROM('path_to_file $\_ { ^ { 0 ^ { \prime } } }$ ，'path_to_file_1..,'path_to_file_ $. 1 9 ^ { \prime }$ ）；

分别对 MonetDB和PostgreSQL进行加载能力的对比。图3是对 MonetDB 进行数据加载测试的结果，图4是PostgresSQL 的测试结果。对比两图得出如下结论：（1)MonetDB 随着数据库单表数据的增加，对注入的速度无明显影响，平均每个星表文件数据的载入时间为 $0 . 9 4 \mathrm { ~ s ~ }$ 。而PostgresSQL则在载入500个星表文件后，速度明显降低，平均载入速度为 $6 . 0 \mathrm { ~ s ~ }$ 。MonetDB没有出现速率陡降现象，这与MonetDB 是内存数据库相关，表现在磁盘存取、内外存的数据传递、缓冲区管理、排队等待及锁的延迟方面均比磁盘数据库快很多。（2)MonetDB每隔几十个文件会有一个突跳点，加载时间突然提高至10s左右。主要原因是由于MonetDB需要时间将数据写到磁盘，而导致的输入输出开销。这是在今后使用中需要解决的一个问题，希望能通过提高数据写入硬盘的频度来解决。

测试(2)的目标：对 MonetDB 进行更大量星表数据的压力加载测试，以测试在大数据下的数据加载性能。

![](images/fd6f01e4cf3b18cfd86b0891bd22f414c8c8d8d3bce672fe8de705955c84945c.jpg)  
图3MonetDB单表数据加载测试  
Fig.3Load test of MonetDB's single table

![](images/3a71bed9b9ba747690f3f68e6be54696a36771938b34e544576195bd1c9b90e4.jpg)  
图4PostgreSQL单表数据加载测试Fig.4Load test of PostgreSQL's single table

测试方法：仿真星表86400个，每个星表约175,000行，包含22列属性数据。每个列文件大小为1.4M，数据量总共 $2 . 4 7 \mathrm { T B }$ 。按顺序不断往数据库注入星表数据。

测试平台：CPU：2 sockets Intel Xeon CPU E5-2690 v2 $@$ 3.00 GHz.40 processor；内存： ${ 8 \times 1 6 \mathrm { G B } }$ 操作系统：Scientific Linux release 6.5，Linux kernel: $2 . 6 . 3 2 - 3 5 8 . { \mathrm { e l } } 6 . { \mathrm { x } } 8 6 \_ 6 4$ 。

测试结果如图5，载入速度基本是缓慢的线性变化。平均每个星表的载入时间 $1 . 7 5 \mathrm { ~ s ~ }$ ，总载入时间$4 2 \mathrm { h }$ 。86400个星表相当于36个CCD向一个数据表注人，所以实际使用应比压力测试的结果还要好。

在测试过程中还发现一个现象：MonetDB的数据载人速度与星表文件大小有一个反常的关系，16MB星表文件的载入整体速度要比 $1 . 3 4 ~ \mathrm { M B }$ 星表数据快2.5倍，具体关系见图6。主要原因是较大的文件读取单元可以更好地利用磁盘输入输出，从而提高了文件的载入速度。对于地面广角相机阵，每个星表数据列文件约 $1 \sim 2 ~ \mathrm { M B }$ ，因此，存在进一步优化的空间，在实际使用中需要通过调整MonetDB内置参数对比进行优化。

![](images/b59d79899dfde6e2d3cc4556525da312686333836ec41dcecf130f33c8ebdd3d.jpg)  
图5MonetDB86400个二进制星表，单表数据加载累加时间曲线Fig.5864OO binary catalogs of MonetDB,loadingtime curve of single table data

![](images/c80cbd3a12a29fb1d09964cb542f0ee0dbbf9d7871c56b8c3355429542cdb4b7.jpg)  
图6MonetDB不同数据块，10008个二进制星表，单表数据加载速度测试Fig.6Different MonetDB data block，1OoO8 binarycatalogs，loading speed test of single table data

# 2.2交叉认证算法的实现

交叉认证是地面广角相机阵巡天中搜索瞬变源和光变曲线生成的关键算法。交叉认证问题必须依靠有效的分区策略，通过将天区按赤纬进行条带分区，将天区划分成一个个水平条带，每个源有一个属于自己的条带属性，交叉认证前首先比较条带属性可以大大降低比较次数。条带可集成到数据库内部，减少了数据输入输出的时间损耗。

表2是一个mini-GWAC $\textcircled{6}$ 用到的实际星表案例，MonetDB在16GB内存的服务器上所作的 $2 0 ^ { \prime \prime }$ 半径误差内交叉认证的测试结果，条带高度 $2 0 ^ { \prime \prime }$ 。测试环境为：Intel Core i7-2600K CPUQuad-Core $@$ $3 . 4 0 \ : \mathrm { G H z }$ ，8 MCache，4GB内存，Scientific Linux 6.4，linux kernel 2.6.32，MonetDB $\mathrm { J a n } 2 0 1 4$ 版本和PostgreSQL 9.3.0版本。

使用的 SQL 语句为

select $\mathrm { \Pi _ { x 0 } }$ .id as id1，tO.id as id2 from extractedcatalog $\mathbf { \pi } _ { \mathrm { { x 0 } } }$ ，template t0 where $\mathrm { \Delta _ { x 0 } }$ .zone between floor(tO.decl-O.Oo56）and floor( $\mathrm { t 0 . d e c l } { + 0 . 0 0 5 6 } )$ ）--zone filter and $\mathrm { _ { x 0 . d e c l } }$ between $\mathrm { 1 0 . d e c l { - 0 . 0 0 5 6 } }$ and $\mathrm { t 0 . d e c l } { + 0 . 0 0 5 6 }$ --dec filter and $3 6 0 0 *$ DEGREES $( 2 * \mathrm { A S I N } ( \mathrm { S Q R T ( \left( \ x 0 . x - t 0 . x \right) * \left( x 0 . x - t 0 . x \right) + ( x 0 . y - t 0 . y ) * ( x 0 . y - t 0 . y ) } ) ) $ $+ \big ( \mathrm { \ x 0 . z - t { 0 . z } } \big ) \ \ast \big ( \mathrm { \ x 0 . z - t { 0 . z } } \big ) \ \big ) / 2 ) \ \big ) < 2 0$ ： --accurate computation

表2 测试结果表明，同样使用条带算法，MonetDB Jan2014比PostgreSQL加速比达17倍。同时,测试两个具有17万条记录的星表进行交叉认证，所需时间大约为 $4 . 3 ~ \mathrm { s }$ 。

# 2.3用户自定义函数功能测试

MonetDB 提供了用户自定义函数（User DefinedFunctions，UDF)对外接口以利于扩展内核功能，用户可以灵活地根据实际需要添加自定义函数。MonetDB装配语言的多层架构结构如图7。用户自定义函数层首先被 MAL解释器识别（MonetDB Assembly Language，SQL 语句解析成 MAL，提供给内核执行），然后由 SQL 编译器识别。为了大批量数据导人，开发了UDFColumncopy，直接将 ASCII文件导入底层列存储单元（BinaryAssociation Table，BAT）。

# 表2MonetDB、PostgreSQL有无 zone 1.5万 $\mathbf { \nabla } \times \mathbf { 1 } . 2$ 万条交叉认证

Table 2 $\mathbf { 1 5 k } \times \mathbf { 1 2 k }$ rows of cross-match MonetDB Postgres with/without zone   

<html><body><table><tr><td>Catalogue A 15218 rows Catalogue B 12540 rows</td><td>Matched rows /条</td><td>time /s</td></tr><tr><td>MonetDB Feb2013 版无 zone</td><td>12 027</td><td>302</td></tr><tr><td>MonetDB Feb2013 版+zone</td><td>12 027</td><td>4.2</td></tr><tr><td>MonetDB Jan2014 版无 zone</td><td>12 027</td><td>238</td></tr><tr><td>MonetDB Jan2014 版+zone</td><td>12 027</td><td>1.8</td></tr><tr><td>PostgreSQL 9.3.0版+zone</td><td>12 027</td><td>30.8</td></tr></table></body></html>

![](images/e23a32f5242e7ce48fdf82e2f0ec6d756cee80b5d8f3d596e5e8781b6364e0e4.jpg)  
图7MonetDB架构及与用户定义函数的关系 Fig.7The architecture of MonetDB and its relationship with UDF

自定义函数Columncopy 的实现过程如下（开发语言为C语言）：

（1）81_svom.mal文件用于MonetDB 服务器启动时自动加载这个用户自定义函数;  
（2）81_svom.sql文件向 SQL 函数列表加入columncopy 函数签名，也用于自动加载；  
（3）Makefile.ag 向编译器引入新模块依赖的库文件信息；  
（4）svom.c，svom.h为用户自定义函数实现文件;

<html><body><table><tr><td>函数</td><td>解释</td></tr><tr><td>_append_bat(sql，t，cname，b)</td><td>将结果BATb追加到表t某列后。</td></tr><tr><td>BATnew(TYPE_void，TYPE_int，nr_rows）;</td><td>创建一个二元关系表。</td></tr><tr><td>columncopy （tablename，columnname,</td><td>SQL函数，将文件filename里的columnrows</td></tr><tr><td>columnrows， filename)</td><td>行导入到 tablename 表的 columnname 列中。</td></tr></table></body></html>

（5）svom.mal 定义MAL 函数地址和对应的 SQL签名的映射;（6）columncopyUDF函数，将BAT结构追加到数据库中该表存储结构的后面完成导入;（7）用户自定义函数与源代码一同编译，注册成为数据库服务器的内置函数，调用方式：

sql>call columncopy（tablename，columnname,columnrows，filename）。

此次用户自定义函数为今后复用设计其他用户自定义函数，扩展MonetDB服务器的能力打下了良好的基础。

# 3初步设计方案

考虑每个相机的并列关系，每个相机对应一个数据库单元，36个数据库单元最终由一台控制服务器连接，控制服务器负责数据库单元的添加和连接。这种设计的好处是数据库单元只需负责自身CCD的存储和计算，在物理上完成了数据表的分割。分布式数据库架构见图8。分布式的数据库各数据表的名称和功能见表3。

![](images/b93b1eb85570e490d18b399c32ee68bcd4c81b785c05c3b06064115a76c24ae1.jpg)  
图8分布式数据库阵列架构  
Fig.8Distributed architecture of Database array

表3分布式的数据库各数据表的名称和功能  
Table 3The name and function of each table in the distributed database   

<html><body><table><tr><td>表单名称</td><td>功能</td></tr><tr><td>image</td><td>每幅原始图像在这个表里有一个唯一标识，每行代表一幅图像。</td></tr><tr><td>targets</td><td>每一幅原始FITS 图像，经过 SEXtractor程序提取的点源记录到这个表。一个源可能 在观测中多次出现，每次出现时的观测指标全部源源不断地插入targets 表中。</td></tr><tr><td>uniquecatalog</td><td>每一行代表一个唯一化的源，uniquecatalog 里的每一行可能与 targets 里的多行相关联， 它的位置、星等等信息是targets 表里多个源的均值。这个表通过 associatedsource 表把 所有这个源在 targets 表的出现绑定在一起，所以uniquecatalog可以看做是寻找一个 特定源的光变曲线的入口。</td></tr><tr><td>associatedsource</td><td>targets 表和uniquecatalog表匹配上的关联都存在这个表内。</td></tr><tr><td>tempuniquecatalog</td><td>临时表，targets 表与uniquecatalog 表交叉的临时结果。</td></tr><tr><td>transient</td><td>保存检测到的暂现源。</td></tr></table></body></html>

通过观测目标星表与模板星表的交叉认证，如果能与模板星表匹配的则进入时序测光通道进行光变曲线的处理并进行管理。如果从模板星表无法找到匹配星，则认为是瞬变源(候选体)。其中流量相对定标的过程为：将交叉认证匹配上的两两星对之间(观测星与模板星匹配组)计算出流量比率，并取这一组的流量比率中值记为 $R m$ ，然后修正所有观测星的星等计算公式为 $n o r m a g = - 2 . 5 \mathrm { l o g } \ ( \mathit { f l u x } \cdot \mathit { R m } )$ ，其中normag为相对流量定标后的观测星表的星等；flux为观测星的流量。相对流量定标把测光星等都定标到模板星表一致的水平，这样光变曲线是一个有意义的相对光变量。所有瞬变源都存放于transient,所有光变曲线存放于 associatedsource。

将交叉认证的匹配情况分成4种，即多对多、一对多、一对一、无匹配。多对多：剪除“多对多”关联以防止数据库爆炸，简化成一对多关系，继续处理。一对多：分配新的unique id 给uniquecatalog 表新插入的源，替代旧的uniqueid。新的一对多关联插入assciatedsource，设定为 $\mathrm { t y p e } = 2$ 插入新unique id与旧 targets id 关联，这是为给被取代的unique id 新位置，标记 tpye $= 6$ 。清空被一对多取代的原有分枝。一对一：插人 tempuniquecatalog 中的一对一关联到 associatedsource 表中，标记为type $= 3$ 。无匹配：插入新的源到uniquecatalog，插入这些新的关联到 associatedsource，设置为 type $= 4$ 。判断暂现源候选插入transient表。至此所有提取物处理完毕。

本系统通过以上设计完成地基广角相机阵的数据处理和管理功能。具体的代码开展与系统优化及最后的测试，将是下一步工作的主要内容。

# 4讨论与总结

我国兴建中的地基广角相机阵面临着大数据处理和管理的挑战：每台相机每15s产生 $1 . 5 \times 1 0 ^ { 5 }$ 条记录，总相机数为36台，并且要求实时处理和入库管理。为应对挑战，提出一种充分利用数据库兼具大数据管理和处理于一身的特点，基于MonetDB的大数据处理和管理的系统设计方案。本方案的计设特点是通过 MonetDB 自身具有大数据处理的特点，将核心数据处理功能内嵌于数据库内，减少因数据管理和处理分属于两个系统所带来的输入输出时间损耗。为验证MonetDB数据库宽视场海量时序数据的处理与管理的可行性，开展多方的测试和预先研究。

预研阶段主要通过了以下测试：（1)TPC-H基准测试。本测试主要针对数据库决策能力，测试结果表明：MonetDB具有明显的表现优势，PostgreSQL次之，MySQL最差。（2)开展关键算法与功能测试。大数据加载能力测试表明，MonetDB 相对于PostgreSQL具有明显的优势。86400个星表相当于 $9 6 \mathrm { { h } }$ （204号的时表数据，平均每个入库时间为 $1 . 7 5 \mathrm { ~ s ~ }$ 。载入时间随着载入数据量的增长缓慢线性增长。这个时间基本能满足项目要求，但仍存在优化的空间。研究发现星表文件的大小与载入速度有一个反常的关系，可以能过MonetDB的内置函数进行优化。同时，将数据存储表按不同观测夜进行分割，从而提高载人速度。交叉认证 Zone 索引算法的实现与测试表明，MonetDB 相对 PostgresSQL 具有更快的处理速度，每17万条记录认证需要时间为 $4 . 3 \mathrm { ~ s ~ }$ 。通过调研和与MonetDB开发人员讨论表明，通过调整MonetDB的内置参数，能进一步优化交叉认证的时间。并预期认证每17万条的记录可以在小于1s内完成。基于MonetDB 用户自定义函数的接口，开发Columncopy批文件导入函数，表明 MonetDB 可以为以后的系统开发提供方便灵活的接口。

基于调研与测试结果，提出本方案的初步设计构架。本方案主要完成两大数据处理功能：瞬变源的实时搜索和海量光变曲线的生成与管理。确立分布式数据库的架构方式，整个系统由36个并列的数据库单元组成，每个数据库单元对应一个独立望远镜且功能相同。一个主控数据库单元管理各个数据库单元。对单独的数据库单元设计了表单的结构及相互关系。同时描述了相对流量定标的实现过程。该设计方案从理论上分析是切实可行的，但实际开发与测试必须经过大量的优化及调试，这将是下一步工作的重点内容。

总之，通过研究工作，找到一种可行的应对地面广角相机阵大数据挑战的数据处理与管理为一体的系统设计方法，将为MonetDB 在中国天文界的大数据处理和管理的应用打下基础。

# 参考文献：

[1] 徐洋，吴潮，万萌，等．用于光学瞬变源搜寻的交叉认证快速算法［J］.天文研究与技术 国家天文台台刊，2013，10(3)：273-282. Xu Yang，Wu Chao，Wan Meng，et al. A fast cross-identification algorithm for searching optical transient sources ［J]．Astronomical Research & Technology— PublicationsofNational Astronomical Observatories of China，2013，10(3）：273-282.   
[2] Zhao Y，Luo Q，Wang S，et al. Accelerating astronomical image subtraction on heterogeneous processors [C]// 2013 IEEE 9th International Conference on Escience.2013：70-77.   
[3] Zhao B，Luo Q，Wu C. Parallelizing astronomical source extraction on the GPU [C]// 2013 IEEE 9th International Conference on Escience.2O13：88-97.   
[4] Wang S， Zhao Y，Luo Q，et al. Accelerating in-memory cross match of astronomical catalogs [C]//2013 IEEE 9th International Conference on Escience.2013：326-333.   
[5] Szalay A S，Blakeley JA. Gray's laws:database-centric computing in science [M]. United States of America：Microsoft Research.2OO9：5-11.   
[6] Scheers L H A. Transient and variable radio sources in the LOFAR sky:an architecture for a detection framework ［D].Amsterdam：University of Amsterdam，2011.   
[7] Ivanova M，Nes N，Goncalves R，et al. MonetDB/SQL Meets SkyServer:the challenges of a scientific database [C]//19th International Conference onScientific and Statistical Database Management. 2007：13.

# A Pre-research on GWAC Massive Catalog Data Storage and Processing System

Wan Meng1,2.3，Wu Chao’，Ying Zhang³，XuYang1，WeiJianyan1 (1.National Astronomical Observatories，Chinese Academy of Sciences，Beijing 10012,China,Email：cwu $@$ nao.cas.cn ; 2.UniversityofChinese AcademyofSciences，Beijing10049,China；3.CentrumWiskunde&Informatica，Amsterdam，1098XG)

Abstract: GWAC（Ground Wide Angle Camera） poses huge challenges in large-scale catalogue storage and real-time processng of quick search of transientsamong wide field-of-view time-series data.Firstly，this paper proposes a concept to employ databases' functions such as fast data processing and paralelism，which will improve system performance and availability through the integration of data storage and computing platform.To understand the feasibility of Column-store MonetDB in vast catalogue management，we carry out a variety of pilot experiments on key technologies.We conduct TPC-H benchmark，data loading benchmark and optimization，and key algorithm testing of astronomical source association，all compared with the traditional row store database.Then，we use MonetDB to realize cross-match Zone algorithm.UDF function is developed for customizable data loading.Test results show that MonetDB database has a remarkable performance in big data management and it is eficient in real-time data processing:it has the ability to deal with 2.5Tcatalog data. In the end we propose a wide field of view massive time serial observation data processing solution using the in-memory column store database MonetDB.The experimental results confirm the feasibilityof this scheme. The design plan of MonetDB-based massive catalogue data processing solution is an eficient astronomical database solution that combines data processing and data management.

Key words:Astronomical database；Architecture design；MonetDB；Real-time analysis；Source association