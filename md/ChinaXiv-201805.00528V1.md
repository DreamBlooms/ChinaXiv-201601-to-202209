# FITS变长数组在暗物质卫星数据存储中的应用研究

杨晓艳[1,2]，石涛[1,2]，李冰[1,2]，孙小涓[1,2]，卢晓军[3]  
（1中国科学院空间信息处理与应用系统技术重点实验室北京1001902中国科学院电子学研究所北京1001903中国国际工程咨询公司北京100048)

摘要：FITS 是空间天文领域广泛使用的一种数据格式，空间天文数据文件通常采用定长数据结构存储为FITS文件。作为我国首颗发射的空间科学卫星，暗物质粒子探测卫星科学数据源包具有长度可变的特点。在暗物质卫星数据处理过程中，急需设计支持可变长度数据的存储结构和处理方法。设计了一种支持长度可变数组的FITS格式，并实现了采用该数据结构的数据处理、存储和管理。应用于暗物质卫星地面处理中，验证结果表明，该方法实现了编辑级产品数据存储，显著降低了产品数据量，节约了存储空间，同时提升了处理效率。

关键词：FITS； 变长数据结构；空间天文；暗物质卫星中图分类号：P172.2文献标识码：A 文章编号:1672-7673(2018)

FITS（Flexible Image Transport system）①是一种在空间天文领域广泛使用的数据格式[1]，目的是为了传输、分析和归档天文科学数据文件。自20世纪80年代FITS 格式被国际天文联合会（IAU）确认为国际标准以来，大部分天文数据以FITS格式在世界各地的数据中心存储和交换。

美国Chandra@卫星、Swift③卫星、欧洲EXOSAT@卫星等国际知名的天文卫星数据，欧洲低频射电干涉阵列（LowFrequencyArray，LOFAR）、澳大利亚望远镜致密阵列（Australia Telescope Compact Array，ATCA）[2]等地基天文观测数据，以及我国HXMT卫星3数据均采用FITS格式存储。以中国科学院国家天文台为首的中国天文学界联合建设了中国虚拟天文台（China-VO）[4]，针对系统中FITS文件检索与访问方面的问题，文[5-6]进行研究并构建了FiHAS系统。

通常情况下，空间天文数据采用定长数组的方式存储为FITS文件。FITS格式文件由整数个长度为2880 字节的报头和数据单元（Header andData Unit,HDU）组成，其数据单元区采用长度固定的ASCII表或者二进制表存储。但是，暗物质粒子探测卫星的科学数据源包长度随有效载荷探测模式、粒子击中状态的不同而不同，定长数据的存储方式无法满足其数据存储的需要；同时，暗物质卫星是一颗空间天文卫星，出于数据共享的需求，其编辑级产品文件必须采用FITS格式存储。因此，需要根据暗物质卫星的数据特点，设计并实现一种数组长度可变的FITS格式数据存储方案。

# 1FITS数据格式

FITS 数据格式能够在国际天文领域得到广泛应用，其原因之一是其自描述性和灵活性。标的 FITS 文件由一个主HDU和一定数量的扩展HDU组成，每个HDU都包括头单元和数据单元两部分。其中，主HDU的头单元包含该文件对应的卫星名称、生产日期等总体描述信息，支持扩展定义，数据单元为空；扩展HDU的头单元包含本HDU数据起始结束时间、参考坐标系、各列数据类型等元数据信息，也支持扩展定义，数据单元中以ASCII表或二进制表的行列存储数据信息?。标准的FITS文件结构如表1。

表1FITS文件结构示意Table1FITSFile structure  

<html><body><table><tr><td>HDU</td><td>Primary HDU</td><td colspan="2">Extension HDU</td><td>…</td><td colspan="2">Extension HDU</td></tr><tr><td>内容</td><td>Header Unit （Primary ）</td><td>Header Unit (Extension)</td><td>Data Unit</td><td></td><td>HeaderUnit (Extension)</td><td>Data Unit</td></tr><tr><td>大小</td><td>2880*N</td><td>2880*N</td><td>2880*N</td><td>：</td><td>2880*N</td><td>2880*N</td></tr><tr><td>类型</td><td>ASCII 码</td><td>ASCII码</td><td>二进制 表\ASCII 表</td><td></td><td>ASCII码</td><td>二进制 表\ASCI表</td></tr></table></body></html>

数据单元以ASCII表或二进制表形式存储二维数组，每行长度固定，每列的数据类型需保持一致。FITS格式支持的数据类型包括：逻辑型（L），bit型（X），字节型（B），16位整型（I），32位整型（J），64位整型（K），单精度浮点型（E），双精度浮点型（D）。

另外，FITS格式的灵活性还支持对变长数组进行存储，存储方法为在文件头单元中定义一组特殊关键字，指定变长数组起始位置的偏移量和数据总长度。变长数组的实体数据并不存放在数据单元中，而是存放在数据单元之后的heap区域中。

# 2暗物质卫星数据特点和存储要求

暗物质粒子探测卫星是中国科学院空间科学战略性先导科技专项中首批确定的五颗科学卫星之一，旨在通过高精度测量高能电子和伽玛射线能谱及其空间分布进行暗物质粒子探测，寻找和发现宇宙暗物质粒子，对其可能的宇宙空间分布进行研究。暗物质卫星已于2015年12月发射。

暗物质卫星有效载荷获取的科学观测数据以及卫星平台采集的工程数据通过数传通道下传至地面，经过帧同步、虚拟信道分离、源包提取、验证排序、排重、拼接/切分等处理后按照 FITS格式输出为编辑级产品，完成产品归档存储，并分发给科学应用系统。主要处理流程如图1。

![](images/ec865fa6ef695b27f3f8a09e696c97173110733fdd5b19f717c31edf5461dba7.jpg)  
图1暗物质卫星数据处理、存储及分发流程  
Fig. 1 data processing, storage and distribution processes of DAMPE

暗物质卫星数传数据中，卫星平台采集的表示载荷、平台工作状态的工程数据长度是固定的按照通用的定长方式存储即可；而科学观测数据源包由30个数据帧队列组成，总长度可变，源包结构以及各数据帧最大长度如表2。

表2暗物质卫星科学数据源包结构  
Table 2 The science data source package structure of DAMPE   

<html><body><table><tr><td>序号</td><td colspan="2">数据帧类型</td><td>最大数据帧长/bit</td></tr><tr><td>1</td><td colspan="2">触发逻辑包</td><td>12</td></tr><tr><td>2</td><td colspan="2">中子探测器数据帧</td><td>18</td></tr><tr><td>3</td><td colspan="2">+X方向塑闪、 Si、BGO数据</td><td>178</td></tr><tr><td>4</td><td rowspan="6">帧</td><td>+X方向塑闪数据帧 +X方向SiFEE1数据帧</td><td>2000</td></tr><tr><td>5</td><td>+X方向SiFEE2数据帧</td><td>2000</td></tr><tr><td>6</td><td>+X方向BGOFEE1数据帧</td><td>302</td></tr><tr><td>7</td><td>+X方向BGOFEE2 数据帧</td><td>302</td></tr><tr><td>8</td><td>+X方向BGO FEE3 数据帧</td><td>158</td></tr><tr><td>9</td><td>+X方向BGOFEE4 数据帧</td><td>302</td></tr><tr><td>10~16</td><td colspan="2">-X方向塑闪、Si、BGO 数据帧</td><td>5242</td></tr><tr><td>17~23</td><td colspan="2">+Y方向塑闪、Si、BGO 数据帧</td><td>5242</td></tr><tr><td>24~30</td><td colspan="2">-Y方向塑闪、Si、BGO 数据帧</td><td>5242</td></tr><tr><td colspan="4">暗物质卫星科学数据源包总长度 20998</td></tr></table></body></html>

暗物质卫星每轨下传的数传数据中，科学数据源包数量为60万左右，按照每个源包20998 字节的最大长度计算，单个文件大小为11.73GB。但实际上，由于科学数据帧的实际长度与有效载荷模式、粒子击中状态有关，而且星上可能会对数据进行压缩，因此，科学数据源包长度是变化的。尤其是硅阵列探测器，总共有7万多个通道，绝大多数情况下，没有大击中事例发生，其大多数通道没有响应，并不输出科学数据。如果按照最大数据量存储，会造成暗物质卫星科学数据文件量偏大，导致数据处理和应用的难度增加、效率降低，以及存储资源的巨大浪费。

针对暗物质卫星科学数据源包特点及其存储需求，需要设计并实现一种能够支持变长

数据的FITS文件存储方案。

# 3FITS可变长存储方案设计与实现

如上所述，暗物质卫星科学数据源包长度变化范围比较大，以下针对其数据特点和存储需求，设计数据存储方案，并采用 $\scriptstyle \mathbf { C } + +$ 语言调用CFITSIO[12]完成软件实现。暗物质卫星数据存储方案设计如下：

（1）文件头改造。

在通用的定长数组存储方案中，文件头中用关键字tform指定数据类型，包括L、X、B、I、J等类型。在暗物质卫星变长数据存储方案中，tform将赋值为rPt(emax)或rQt(emax)两种特殊类型。其中， $\boldsymbol { r }$ 为计数，可以是0、1或者不出现；P、Q为数组描述符类型，分别表示32位、64位有符号整数；t为数据类型代码；emax为数据长度最长的字节数。根据暗物质卫星数据类型，设置tform $\mathbf { \tau } _ { | = }$ 1QB（emax），表示数组描述符类型为64位有符号整数，实体数据按字节类型存储，emax值从实际数据中提取。

另外，关键字theap 表示heap 区域的开始位置，省略时默认值为数据单元长度，表示heap 区域直接从数据单元的下一个字节开始；如果取值大于默认值，表示heap区域与数据单元区域之间有一定的间隔。pcount为间隔大小与heap 区域大小之和。暗物质卫星变长数据存储方案中，theap 取默认值，pcount为科学源包数据的字节数，该参数值从实际数据中提取。

（2）调用fits_create_tbl函数，创建FITS文件。函数调用方式如下：fits_create_tbl(fitsfile \*fptr, int tbltype,LONGLONG naxis2,int tfields,char \*type[],char  
\*tform[], char \*tunit[], char \*extname, int \*status)其中，fptr表示准备创建的暗物质卫星编辑级产品FITS文件；tbltype表示数据单元区表格类型，ASCII_TBL表示ASCII表，BINARY_TBL表示二  
进制表，暗物质卫星数据采用二进制表存储;naxis2表示暗物质卫星科学数据源包总行数，该参数从实际数据中提取；tfields表示参数个数，暗物质卫星科学数据源包产品仅有CCSDS源包1个参数列;ttype表示参数名称，命名为CCSDS;tform表示参数类型，如上文所述，设置tform $\mathbf { \tau } _ { \mathsf { l } } =$ 1QB(emax);tunit表示参数度量单位，CCSDS源包没有单位；extname表示扩展HDU的名称，命名为Sci_Src。

（3）写入数组描述符。

数组描述符是一个 $N ^ { * } 2$ 的二维矩阵， $N$ 为变长数组的总行数，第1列定义数组中各行数据的长度，第2列定义各行数据起始位置在整个heap区域的偏移量，取值均为正整数，存储在数据单元中。暗物质卫星变长数据存储方案中，创建两个 $N$ 维索引数组，分别命名为index_len[M]，index_offset[M]， $N$ 表示暗物质卫星科学数据源包总行数，从实际数据中提取每行长度，存入index_len数组，提取每行数据起始位置偏移量，存入index_offset数

组。（4）在heap 区域中写入变长数组数据。

变长数组实体逐行存在heap 区域中，由于theap 取默认值，因此，存储起始位置就是数据单元结束符的下一个字节。然后，根据数组描述符取值，确认各行数据的起始位置和各行长度，调用 fits_write_col函数，将暗物质卫星科学数据源包数据逐行写入FITS文件 heap区域，函数调用方式如下：

int fits_write_col(fitsfile \*fptr, int datatype, int colnum,LONGLONG firstrow,LONGLONG firstelem,LONGLONG nelements,DTYPE \*array, $>$ int \*status)

其中，fptr表示准备写入的暗物质卫星编辑级产品FITS文件;datatype表示写入方式，暗物质卫星数据按字节写入，该参数设置为TBYTE;colnum表示行号，从第1行开始；firstrow表示起始写入的行号，从1开始；firstelem表示该行的第一个元素；nelements为该行数据长度，取值为 index_len[N];\*array为准备写入该行的CCSDS源包数据的存储位置，设置为p+index.index[N].offset，其中p为位置指针。

按照上述方案，暗物质卫星数据FITS文件中扩展HDU的存储结构如下：

<html><body><table><tr><td rowspan="2">【文件头】</td><td rowspan="2">【数据单元】 存储暗物质卫星数据数组 描述符</td><td>【heap】</td></tr><tr><td>存储暗物质卫星科学源包 数据实体</td></tr></table></body></html>

# 4效果验证

为了验证上述存储方案在产品文件数据量、存储效率、处理效率等方面的性能，选择2016年4月29日（2041圈）、2016年6月5日（2605圈）、2017年7月3日（8595圈）、2017年7月25日（8923圈）、2017年8月30日（9478圈）共5轨暗物质卫星数传数据中科学源包类数据的编辑级产品文件进行分析。表3对定长FITS方案存储与变长方案存储的暗物质卫星编辑级产品文件大小进行了对比。

表3两种格式下FITS文件数据量对比Table 3 Comparison of the two format file sizes  

<html><body><table><tr><td>序号</td><td>源包数量</td><td>源包最大长</td><td>定长FITS格式文</td><td>暗物质产品实际</td><td>数据量降低</td></tr><tr><td></td><td>（个）</td><td>度 (字节)</td><td>件大小（GB)</td><td>文件大小（GB)</td><td>(%)</td></tr><tr><td>1</td><td>507797</td><td>20998</td><td>9.93</td><td>1.16</td><td>88.36</td></tr><tr><td>2</td><td>328236</td><td>20998</td><td>6.42</td><td>0.76</td><td>88.21</td></tr><tr><td>3 4</td><td>610706</td><td>20998</td><td>11.94</td><td>1.49</td><td>87.56</td></tr><tr><td></td><td>725230</td><td>20998</td><td>14.18 10.35</td><td>1.72</td><td>87.85</td></tr><tr><td>5</td><td>529467</td><td>20998</td><td></td><td>1.29</td><td>87.56</td></tr></table></body></html>

# 5结果与讨论

真实数据的验证结果表明，针对暗物质卫星的数据产品存储特点，本文提出的基于FITS格式的变长数组存储方案能够将文件数据量降低 $8 8 \%$ 左右，极大地节省了数据存储空间；同时，由于文件数据量的有效降低，数据的处理速度、产品的归档速度和应用效率都得到了明显提升。

本文提出的基于FITS格式的可变数组存储方案能够扩展应用到其他数据长度变化的天文数据存储中，该方案能够有效降低数据存储量，降低效率取决于实际数据长度与最大数据长度的平均比例。

# 参考文献

[1] Hanisch R J,Farris A, Greisen E,et al.Definition of the Flexible Image Transport System (FITS) [J].Astronomy & Astrophysics,2001,376: 359-380.   
[2] Murphy T，Lamb P，Owen C， et al. Data storage,processing, and visualization for the Australia telescope compact array[J]. Publications of the Astronomical Society of Australia， 2006，23(1):2 5-32.   
[3] 赵海升，葛明玉,李正恒，等.一种天文卫星数据预处理方法[J].天文研究与技术,2017,14(6): 376-381. Zhao Haisheng, Ge Mingyu, Li Zhengheng, et al. A method of data preprocessing for astronomical satellite [J] .Astronomical Research & Technology, 2017,14(6):376-381.   
[4] 崔辰州，赵永恒.中国虚拟天文台体系结构[J].天文研究与技术—国家天文台台刊，2004, 1(2): 140-151. Cui Chenzhou, Zhao Yongheng. Architecture of Chinese Virtual Observatory[J]. Astronomical Res earch& Technology—Publications of National Astronomical Observatories of China,2004, 1(2): 140-151.   
[5] 崔辰州，李文,于策，等.FITS 数据文件的检索与访问[J].天文研究与技术—国家天文台台 刊，2008,5(2): 116-123. Cui Chenzhou, Li Wen, Yu Ce, etal, Search an location ofFITS data files [J].Astronomical Resear ch & Technology—Publications of National Astronomical Observatories of China,2008,5(2): 116-123.   
[6] 张海龙，冶鑫晨,李慧娟，等.天文数据检索与发布综述[J].天文研究与技术，2017,14(2):21 2-228. Zhang Hailong, Ye Xinchen, Li Huijuan, et al. Astronomical data query and release review[J]. Astr onomical Research & Technology, 2017,14(4):212-228.

# Application Research of FITS Variable-Length Arrays in

# DAMPE Data Storage

Yang Xiaoyan[1,2],， Shi Tao[1,2],Li Bing[1,2], Sun Xiaojuan[1,2],Lu Xiaojun[3] 1. Key Laboratory of Technology in Geo-spatial Information Processing and Application System, Chinese Academy of Sciences, Beijing 100190, China 2. Institute of Electronics, Chinese Academy of Sciences, Beijing 10o190, China 3. China International Engineering Consulting Corporation, Beijing 10oo48, China

Abstract: FITS (Flexible Image Transport system) is a data format widely used in space astronomy, and astronomical data files are usually stored in a fixed-length data structure as FITS files. As the first space science satellite in our country, DAMPE (Dark Matter Particle Explorer) satelite's science data source package has the characteristics of variable length. In DAMPE data processing process, it is urgent to design a storage structure and processing method that supports variable length data. This paper designed a FITS format that supports variable-length arrays and implemented DAMPE data processing, storage, and management with this data structure. The validation with real data of DAMPE indicated that this method was successfully applied to editing grade products storage of DAMPE, not only significantly reducing the amount of product data, saving storage space, but also improving the speed of data processing.

Keyword: FITS; Variable-length arrays; Astronomy; DAMPE